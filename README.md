# eZ Google Translate extension for eZ Publish

An extension that allows for esay translation of content in multilingual websites using eZ Publish.

Based on translation services from Google ($$), Microsoft, Frengly, Mymemory.

Please note that not all of these services support translation from/to all languages.

Also they might have limitatins on the number of translation requests per day.


# Requirements

- eZJSCore extension
- eZPubish 4.x (NB: the provided templates have been tested with eZP 4.6 and 2012.1 only)
- for most translation providers, an account has to be created


# Technicalities

- provides a javascript function "eztranslate" to translate texts.
  This function can be used by developers in any template they want
  (as long as they do not forget to include the "parts/tsengineload.tpl" template first)

- uses ezjscore for translation calls, thus avoiding saame-origin ajax limitations

- by default adds interface elements ("translate" links) to the "translate content" page
  This happens for designs admin, admin2, ezwebin

- translatabale datataypes: string, text, image (the ALT tag), keywords


# FAQ

- q: this does not work
  a1: did you clear the template cache?
  a2: you might have datatype-editing templates already overridden in another extension, please check
  a4: you can test translation by hand: POST to /ezjscore/call/googletranslate::translate::eng-GB::fre-FR, with a POST variable named "text"
  a3: firebug is your friend
