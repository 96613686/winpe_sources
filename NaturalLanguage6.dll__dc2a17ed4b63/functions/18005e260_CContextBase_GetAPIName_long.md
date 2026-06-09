# CContextBase::GetAPIName(long)

- ea: `0x18005e260`
- end: `0x18005e507`
- name: `?GetAPIName@CContextBase@@QEBAPEBGJ@Z`
- size: `679`
- prototype: `const unsigned __int16 *__fastcall(CContextBase *__hidden this, int)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001a260`
- `0x180057140`
- `0x180057bd0`

## callees

- `0x18005e260`

## string_xrefs

- `0x18005e2d9`: `IsComputingCompounds`
- `0x18005e2e6`: `IsComputingInflections`
- `0x18005e2f3`: `IsComputingLemmas`
- `0x18005e300`: `IsComputingExpansions`
- `0x18005e30d`: `IsComputingBases`
- `0x18005e31a`: `IsComputingPartOfSpeechTags`
- `0x18005e375`: `IsComputingHyphenation`
- `0x18005e3a9`: `IsSpellForcingCompoundSuggestions`
- `0x18005e3d0`: `IsSpellVerifyAutoReplace`
- `0x18005e493`: `IsKoreanAuxCombine`
- `0x18005e4ad`: `IsKoreanCompoundNounProc`
- `0x18005e4f8`: `IsReturnAutoReplace`

## pseudocode

```c
const unsigned __int16 *__fastcall CContextBase::GetAPIName(CContextBase *this, int a2)
{
  const unsigned __int16 *result; // rax

  switch ( a2 )
  {
    case 0:
      return L"MaxSentences";
    case 1:
      return L"IsSingleLanguage";
    case 2:
      return L"IsSimpleWordBreaking";
    case 3:
      return L"UseRelativeTimes";
    case 4:
      return L"IgnorePunctuation";
    case 5:
      return L"IsCaching";
    case 6:
      return L"IsShowingGaps";
    case 7:
      return L"IsShowingCharacterNormalizations";
    case 8:
      return L"IsShowingWordNormalizations";
    case 9:
      return L"IsComputingCompounds";
    case 10:
      return L"IsComputingInflections";
    case 11:
      return L"IsComputingLemmas";
    case 12:
      return L"IsComputingExpansions";
    case 13:
      return L"IsComputingBases";
    case 14:
      return L"IsComputingPartOfSpeechTags";
    case 15:
      return L"IsFindingDefinitions";
    case 16:
      return L"IsFindingDateTimeMeasures";
    case 17:
      return L"IsFindingPersons";
    case 18:
      return L"IsFindingLocations";
    case 19:
      return L"IsFindingOrganizations";
    case 20:
      return L"IsFindingPhrases";
    case 21:
      return L"IsComputingHyphenation";
    case 22:
      return L"IsSpellChecking";
    case 23:
      return L"IsSpellAlwaysSuggesting";
    case 24:
      return L"IsSpellSuggestingMWEs";
    case 25:
      return L"IsSpellForcingCompoundSuggestions";
    case 26:
      return L"IsSpellUsingDialects";
    case 27:
      return L"IsSpellVerifyOnly";
    case 28:
      return L"IsSpellVerifyAutoReplace";
    case 29:
      return L"IsSpellContinued";
    case 30:
      return L"IsSpellCaseSensitive";
    case 31:
      return L"SpellLexDataID";
    case 32:
      return L"IsSuggestFromMainLexOnly";
    case 33:
      return L"IsIgnoreAllCaps";
    case 34:
      return L"IsIgnoreMixedDigits";
    case 35:
      return L"IsIgnoreRomanNumerals";
    case 36:
      return L"IsFindRepeatWord";
    case 37:
      return L"IsIgnoreSingleLetter";
    case 38:
      return L"IsContextSpell";
    case 39:
      return L"IsIgnoreUrls";
    case 40:
      return L"IsFrenchAccentedUppercase";
    case 41:
      return L"FrenchReform";
    case 42:
      return L"IsGermanPrereform";
    case 43:
      return L"IsKoreanAuxCombine";
    case 44:
      return L"IsKoreanMissSpellDictSearch";
    case 45:
      return L"IsKoreanCompoundNounProc";
    case 46:
      return L"IsArabicStrictAlefHamza";
    case 47:
      return L"IsArabicStrictFinalYaa";
    case 48:
      return L"IsHebrewPartialScript";
    case 49:
      return L"IsHebrewMixedScript";
    case 50:
      return L"GermanReform";
  }
  result = 0;
  if ( a2 == 51 )
    return L"IsReturnAutoReplace";
  return result;
}

```

## disassembly

```asm
0x18005e260  test    edx, edx
0x18005e262  jnz     short loc_18005E26C
0x18005e264  lea     rax, aMaxsentences; "MaxSentences"
0x18005e26b  retn
0x18005e26c  cmp     edx, 1
0x18005e26f  jnz     short loc_18005E279
0x18005e271  lea     rax, aIssinglelangua; "IsSingleLanguage"
0x18005e278  retn
0x18005e279  cmp     edx, 2
0x18005e27c  jnz     short loc_18005E286
0x18005e27e  lea     rax, aIssimplewordbr; "IsSimpleWordBreaking"
0x18005e285  retn
0x18005e286  cmp     edx, 3
0x18005e289  jnz     short loc_18005E293
0x18005e28b  lea     rax, aUserelativetim; "UseRelativeTimes"
0x18005e292  retn
0x18005e293  cmp     edx, 4
0x18005e296  jnz     short loc_18005E2A0
0x18005e298  lea     rax, aIgnorepunctuat; "IgnorePunctuation"
0x18005e29f  retn
0x18005e2a0  cmp     edx, 5
0x18005e2a3  jnz     short loc_18005E2AD
0x18005e2a5  lea     rax, aIscaching; "IsCaching"
0x18005e2ac  retn
0x18005e2ad  cmp     edx, 6
0x18005e2b0  jnz     short loc_18005E2BA
0x18005e2b2  lea     rax, aIsshowinggaps; "IsShowingGaps"
0x18005e2b9  retn
0x18005e2ba  cmp     edx, 7
0x18005e2bd  jnz     short loc_18005E2C7
0x18005e2bf  lea     rax, aIsshowingchara; "IsShowingCharacterNormalizations"
0x18005e2c6  retn
0x18005e2c7  cmp     edx, 8
0x18005e2ca  jnz     short loc_18005E2D4
0x18005e2cc  lea     rax, aIsshowingwordn; "IsShowingWordNormalizations"
0x18005e2d3  retn
0x18005e2d4  cmp     edx, 9
0x18005e2d7  jnz     short loc_18005E2E1
0x18005e2d9  lea     rax, aIscomputingcom; "IsComputingCompounds"
0x18005e2e0  retn
0x18005e2e1  cmp     edx, 0Ah
0x18005e2e4  jnz     short loc_18005E2EE
0x18005e2e6  lea     rax, aIscomputinginf; "IsComputingInflections"
0x18005e2ed  retn
0x18005e2ee  cmp     edx, 0Bh
0x18005e2f1  jnz     short loc_18005E2FB
0x18005e2f3  lea     rax, aIscomputinglem; "IsComputingLemmas"
0x18005e2fa  retn
0x18005e2fb  cmp     edx, 0Ch
0x18005e2fe  jnz     short loc_18005E308
0x18005e300  lea     rax, aIscomputingexp; "IsComputingExpansions"
0x18005e307  retn
0x18005e308  cmp     edx, 0Dh
0x18005e30b  jnz     short loc_18005E315
0x18005e30d  lea     rax, aIscomputingbas; "IsComputingBases"
0x18005e314  retn
0x18005e315  cmp     edx, 0Eh
0x18005e318  jnz     short loc_18005E322
0x18005e31a  lea     rax, aIscomputingpar; "IsComputingPartOfSpeechTags"
0x18005e321  retn
0x18005e322  cmp     edx, 0Fh
0x18005e325  jnz     short loc_18005E32F
0x18005e327  lea     rax, aIsfindingdefin; "IsFindingDefinitions"
0x18005e32e  retn
0x18005e32f  cmp     edx, 10h
0x18005e332  jnz     short loc_18005E33C
0x18005e334  lea     rax, aIsfindingdatet; "IsFindingDateTimeMeasures"
0x18005e33b  retn
0x18005e33c  cmp     edx, 11h
0x18005e33f  jnz     short loc_18005E349
0x18005e341  lea     rax, aIsfindingperso; "IsFindingPersons"
0x18005e348  retn
0x18005e349  cmp     edx, 12h
0x18005e34c  jnz     short loc_18005E356
0x18005e34e  lea     rax, aIsfindinglocat; "IsFindingLocations"
0x18005e355  retn
0x18005e356  cmp     edx, 13h
0x18005e359  jnz     short loc_18005E363
0x18005e35b  lea     rax, aIsfindingorgan; "IsFindingOrganizations"
0x18005e362  retn
0x18005e363  cmp     edx, 14h
0x18005e366  jnz     short loc_18005E370
0x18005e368  lea     rax, aIsfindingphras; "IsFindingPhrases"
0x18005e36f  retn
0x18005e370  cmp     edx, 15h
0x18005e373  jnz     short loc_18005E37D
0x18005e375  lea     rax, aIscomputinghyp; "IsComputingHyphenation"
0x18005e37c  retn
0x18005e37d  cmp     edx, 16h
0x18005e380  jnz     short loc_18005E38A
0x18005e382  lea     rax, aIsspellcheckin; "IsSpellChecking"
0x18005e389  retn
0x18005e38a  cmp     edx, 17h
0x18005e38d  jnz     short loc_18005E397
0x18005e38f  lea     rax, aIsspellalwayss; "IsSpellAlwaysSuggesting"
0x18005e396  retn
0x18005e397  cmp     edx, 18h
0x18005e39a  jnz     short loc_18005E3A4
0x18005e39c  lea     rax, aIsspellsuggest; "IsSpellSuggestingMWEs"
0x18005e3a3  retn
0x18005e3a4  cmp     edx, 19h
0x18005e3a7  jnz     short loc_18005E3B1
0x18005e3a9  lea     rax, aIsspellforcing; "IsSpellForcingCompoundSuggestions"
0x18005e3b0  retn
0x18005e3b1  cmp     edx, 1Ah
0x18005e3b4  jnz     short loc_18005E3BE
0x18005e3b6  lea     rax, aIsspellusingdi; "IsSpellUsingDialects"
0x18005e3bd  retn
0x18005e3be  cmp     edx, 1Bh
0x18005e3c1  jnz     short loc_18005E3CB
0x18005e3c3  lea     rax, aIsspellverifyo; "IsSpellVerifyOnly"
0x18005e3ca  retn
0x18005e3cb  cmp     edx, 1Ch
0x18005e3ce  jnz     short loc_18005E3D8
0x18005e3d0  lea     rax, aIsspellverifya; "IsSpellVerifyAutoReplace"
0x18005e3d7  retn
0x18005e3d8  cmp     edx, 1Dh
0x18005e3db  jnz     short loc_18005E3E5
0x18005e3dd  lea     rax, aIsspellcontinu; "IsSpellContinued"
0x18005e3e4  retn
0x18005e3e5  cmp     edx, 1Eh
0x18005e3e8  jnz     short loc_18005E3F2
0x18005e3ea  lea     rax, aIsspellcasesen; "IsSpellCaseSensitive"
0x18005e3f1  retn
0x18005e3f2  cmp     edx, 1Fh
0x18005e3f5  jnz     short loc_18005E3FF
0x18005e3f7  lea     rax, aSpelllexdataid; "SpellLexDataID"
0x18005e3fe  retn
0x18005e3ff  cmp     edx, 20h ; ' '
0x18005e402  jnz     short loc_18005E40C
0x18005e404  lea     rax, aIssuggestfromm; "IsSuggestFromMainLexOnly"
0x18005e40b  retn
0x18005e40c  cmp     edx, 21h ; '!'
0x18005e40f  jnz     short loc_18005E419
0x18005e411  lea     rax, aIsignoreallcap; "IsIgnoreAllCaps"
0x18005e418  retn
0x18005e419  cmp     edx, 22h ; '"'
0x18005e41c  jnz     short loc_18005E426
0x18005e41e  lea     rax, aIsignoremixedd; "IsIgnoreMixedDigits"
0x18005e425  retn
0x18005e426  cmp     edx, 23h ; '#'
0x18005e429  jnz     short loc_18005E433
0x18005e42b  lea     rax, aIsignoreromann; "IsIgnoreRomanNumerals"
0x18005e432  retn
0x18005e433  cmp     edx, 24h ; '$'
0x18005e436  jnz     short loc_18005E440
0x18005e438  lea     rax, aIsfindrepeatwo; "IsFindRepeatWord"
0x18005e43f  retn
0x18005e440  cmp     edx, 25h ; '%'
0x18005e443  jnz     short loc_18005E44D
0x18005e445  lea     rax, aIsignoresingle; "IsIgnoreSingleLetter"
0x18005e44c  retn
0x18005e44d  cmp     edx, 26h ; '&'
0x18005e450  jnz     short loc_18005E45A
0x18005e452  lea     rax, aIscontextspell; "IsContextSpell"
0x18005e459  retn
0x18005e45a  cmp     edx, 27h ; '''
0x18005e45d  jnz     short loc_18005E467
0x18005e45f  lea     rax, aIsignoreurls; "IsIgnoreUrls"
0x18005e466  retn
0x18005e467  cmp     edx, 28h ; '('
0x18005e46a  jnz     short loc_18005E474
0x18005e46c  lea     rax, aIsfrenchaccent; "IsFrenchAccentedUppercase"
0x18005e473  retn
0x18005e474  cmp     edx, 29h ; ')'
0x18005e477  jnz     short loc_18005E481
0x18005e479  lea     rax, aFrenchreform; "FrenchReform"
0x18005e480  retn
0x18005e481  cmp     edx, 2Ah ; '*'
0x18005e484  jnz     short loc_18005E48E
0x18005e486  lea     rax, aIsgermanpreref; "IsGermanPrereform"
0x18005e48d  retn
0x18005e48e  cmp     edx, 2Bh ; '+'
0x18005e491  jnz     short loc_18005E49B
0x18005e493  lea     rax, aIskoreanauxcom; "IsKoreanAuxCombine"
0x18005e49a  retn
0x18005e49b  cmp     edx, 2Ch ; ','
0x18005e49e  jnz     short loc_18005E4A8
0x18005e4a0  lea     rax, aIskoreanmisssp; "IsKoreanMissSpellDictSearch"
0x18005e4a7  retn
0x18005e4a8  cmp     edx, 2Dh ; '-'
0x18005e4ab  jnz     short loc_18005E4B5
0x18005e4ad  lea     rax, aIskoreancompou; "IsKoreanCompoundNounProc"
0x18005e4b4  retn
0x18005e4b5  cmp     edx, 2Eh ; '.'
0x18005e4b8  jnz     short loc_18005E4C2
0x18005e4ba  lea     rax, aIsarabicstrict_0; "IsArabicStrictAlefHamza"
0x18005e4c1  retn
0x18005e4c2  cmp     edx, 2Fh ; '/'
0x18005e4c5  jnz     short loc_18005E4CF
0x18005e4c7  lea     rax, aIsarabicstrict; "IsArabicStrictFinalYaa"
0x18005e4ce  retn
0x18005e4cf  cmp     edx, 30h ; '0'
0x18005e4d2  jnz     short loc_18005E4DC
0x18005e4d4  lea     rax, aIshebrewpartia; "IsHebrewPartialScript"
0x18005e4db  retn
0x18005e4dc  cmp     edx, 31h ; '1'
0x18005e4df  jnz     short loc_18005E4E9
0x18005e4e1  lea     rax, aIshebrewmixeds; "IsHebrewMixedScript"
0x18005e4e8  retn
0x18005e4e9  cmp     edx, 32h ; '2'
0x18005e4ec  jnz     short loc_18005E4F6
0x18005e4ee  lea     rax, aGermanreform; "GermanReform"
0x18005e4f5  retn
0x18005e4f6  xor     eax, eax
0x18005e4f8  lea     rcx, aIsreturnautore; "IsReturnAutoReplace"
0x18005e4ff  cmp     edx, 33h ; '3'
0x18005e502  cmovz   rax, rcx
0x18005e506  retn
```
