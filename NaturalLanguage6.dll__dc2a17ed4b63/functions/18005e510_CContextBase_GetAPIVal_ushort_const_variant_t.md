# CContextBase::GetAPIVal(ushort const *,_variant_t &)

- ea: `0x18005e510`
- end: `0x18005f2f0`
- name: `?GetAPIVal@CContextBase@@QEBA_NPEBGAEAV_variant_t@@@Z`
- size: `3552`
- prototype: `bool __fastcall(CContextBase *__hidden this, const unsigned __int16 *, struct _variant_t *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180057140`

## callees

- `0x180009790`
- `0x180024954`
- `0x180041974`
- `0x18005e510`
- `0x1800b0010`

## string_xrefs

- `0x18005e739`: `ComputingCompounds`
- `0x18005e722`: `IsComputingCompounds`
- `0x18005e767`: `IsComputingInflections`
- `0x18005e77e`: `ComputingInflections`
- `0x18005e750`: `Compounds`
- `0x18005e7da`: `IsComputingLemmas`
- `0x18005e7f1`: `ComputingLemmas`
- `0x18005e836`: `IsComputingExpansions`
- `0x18005e84d`: `ComputingExpansions`
- `0x18005e87b`: `IsComputingBases`
- `0x18005e892`: `ComputingBases`
- `0x18005e8d7`: `ComputingPartOfSpeechTags`
- `0x18005e8c0`: `IsComputingPartOfSpeechTags`
- `0x18005eaba`: `IsComputingHyphenation`
- `0x18005ead1`: `ComputingHyphenation`
- `0x18005ebfc`: `ForcingCompoundSuggestions`
- `0x18005ebce`: `IsSpellForcingCompoundSuggestions`
- `0x18005ebe5`: `SpellForcingCompoundSuggestions`
- `0x18005eccb`: `VerifyAutoReplace`
- `0x18005ecb4`: `SpellVerifyAutoReplace`
- `0x18005ec9d`: `IsSpellVerifyAutoReplace`
- `0x18005ef9b`: `KoreanAuxCombine`
- `0x18005eff7`: `KoreanCompoundNounProc`
- `0x18005ef84`: `IsKoreanAuxCombine`
- `0x18005efe0`: `IsKoreanCompoundNounProc`
- `0x18005f0ef`: `ReturnAutoReplace`
- `0x18005f0dc`: `IsReturnAutoReplace`

## pseudocode

```c
char __fastcall CContextBase::GetAPIVal(CContextBase *this, const unsigned __int16 *a2, struct _variant_t *a3)
{
  __int64 v6; // rdx
  __int64 v7; // rdx

  if ( !(unsigned int)CMN_CompareStringNoCaseW(a2, L"MaxSentences")
    || !(unsigned int)CMN_CompareStringNoCaseW(a2, L"NLDP_SENTENCE_COUNT")
    || !(unsigned int)CMN_CompareStringNoCaseW(a2, L"NSents") )
  {
    v7 = *((unsigned int *)this + 3);
    goto LABEL_187;
  }
  if ( (unsigned int)CMN_CompareStringNoCaseW(a2, L"IsSingleLanguage")
    && (unsigned int)CMN_CompareStringNoCaseW(a2, L"SingleLanguage") )
  {
    if ( (unsigned int)CMN_CompareStringNoCaseW(a2, L"IsSimpleWordBreaking")
      && (unsigned int)CMN_CompareStringNoCaseW(a2, L"SimpleWordBreaking") )
    {
      if ( (unsigned int)CMN_CompareStringNoCaseW(a2, L"UseRelativeTimes")
        && (unsigned int)CMN_CompareStringNoCaseW(a2, L"UseRelativeTimes") )
      {
        if ( (unsigned int)CMN_CompareStringNoCaseW(a2, L"IgnorePunctuation")
          && (unsigned int)CMN_CompareStringNoCaseW(a2, L"IgnorePunctuation") )
        {
          if ( (unsigned int)CMN_CompareStringNoCaseW(a2, L"IsCaching")
            && (unsigned int)CMN_CompareStringNoCaseW(a2, L"Caching") )
          {
            if ( (unsigned int)CMN_CompareStringNoCaseW(a2, L"IsShowingGaps")
              && (unsigned int)CMN_CompareStringNoCaseW(a2, L"ShowingGaps")
              && (unsigned int)CMN_CompareStringNoCaseW(a2, L"Gaps") )
            {
              if ( (unsigned int)CMN_CompareStringNoCaseW(a2, L"IsShowingCharacterNormalizations")
                && (unsigned int)CMN_CompareStringNoCaseW(a2, L"ShowingCharacterNormalizations")
                && (unsigned int)CMN_CompareStringNoCaseW(a2, L"CharacterNormalizations") )
              {
                if ( (unsigned int)CMN_CompareStringNoCaseW(a2, L"IsShowingWordNormalizations")
                  && (unsigned int)CMN_CompareStringNoCaseW(a2, L"ShowingWordNormalizations")
                  && (unsigned int)CMN_CompareStringNoCaseW(a2, L"WordNormalizations") )
                {
                  if ( (unsigned int)CMN_CompareStringNoCaseW(a2, L"IsComputingCompounds")
                    && (unsigned int)CMN_CompareStringNoCaseW(a2, L"ComputingCompounds")
                    && (unsigned int)CMN_CompareStringNoCaseW(a2, L"Compounds") )
                  {
                    if ( (unsigned int)CMN_CompareStringNoCaseW(a2, L"IsComputingInflections")
                      && (unsigned int)CMN_CompareStringNoCaseW(a2, L"ComputingInflections")
                      && (unsigned int)CMN_CompareStringNoCaseW(a2, L"Inflections")
                      && (unsigned int)CMN_CompareStringNoCaseW(a2, L"NLDP_SECTION_INFL_MORPH")
                      && (unsigned int)CMN_CompareStringNoCaseW(a2, L"InflForms") )
                    {
                      if ( (unsigned int)CMN_CompareStringNoCaseW(a2, L"IsComputingLemmas")
                        && (unsigned int)CMN_CompareStringNoCaseW(a2, L"ComputingLemmas")
                        && (unsigned int)CMN_CompareStringNoCaseW(a2, L"Lemmas")
                        && (unsigned int)CMN_CompareStringNoCaseW(a2, L"SectionLemmas") )
                      {
                        if ( (unsigned int)CMN_CompareStringNoCaseW(a2, L"IsComputingExpansions")
                          && (unsigned int)CMN_CompareStringNoCaseW(a2, L"ComputingExpansions")
                          && (unsigned int)CMN_CompareStringNoCaseW(a2, L"Expansions") )
                        {
                          if ( (unsigned int)CMN_CompareStringNoCaseW(a2, L"IsComputingBases")
                            && (unsigned int)CMN_CompareStringNoCaseW(a2, L"ComputingBases")
                            && (unsigned int)CMN_CompareStringNoCaseW(a2, L"Bases") )
                          {
                            if ( (unsigned int)CMN_CompareStringNoCaseW(a2, L"IsComputingPartOfSpeechTags")
                              && (unsigned int)CMN_CompareStringNoCaseW(a2, L"ComputingPartOfSpeechTags")
                              && (unsigned int)CMN_CompareStringNoCaseW(a2, L"PartOfSpeechTags")
                              && (unsigned int)CMN_CompareStringNoCaseW(a2, L"PosTags") )
                            {
                              if ( (unsigned int)CMN_CompareStringNoCaseW(a2, L"IsFindingDefinitions")
                                && (unsigned int)CMN_CompareStringNoCaseW(a2, L"FindingDefinitions")
                                && (unsigned int)CMN_CompareStringNoCaseW(a2, L"Definitions") )
                              {
                                if ( (unsigned int)CMN_CompareStringNoCaseW(a2, L"IsFindingDateTimeMeasures")
                                  && (unsigned int)CMN_CompareStringNoCaseW(a2, L"FindingDateTimeMeasures")
                                  && (unsigned int)CMN_CompareStringNoCaseW(a2, L"DateTimeMeasures") )
                                {
                                  if ( (unsigned int)CMN_CompareStringNoCaseW(a2, L"IsFindingPersons")
                                    && (unsigned int)CMN_CompareStringNoCaseW(a2, L"FindingPersons")
                                    && (unsigned int)CMN_CompareStringNoCaseW(a2, L"Persons") )
                                  {
                                    if ( (unsigned int)CMN_CompareStringNoCaseW(a2, L"IsFindingLocations")
                                      && (unsigned int)CMN_CompareStringNoCaseW(a2, L"FindingLocations")
                                      && (unsigned int)CMN_CompareStringNoCaseW(a2, L"Locations") )
                                    {
                                      if ( (unsigned int)CMN_CompareStringNoCaseW(a2, L"IsFindingOrganizations")
                                        && (unsigned int)CMN_CompareStringNoCaseW(a2, L"FindingOrganizations")
                                        && (unsigned int)CMN_CompareStringNoCaseW(a2, L"Organizations") )
                                      {
                                        if ( (unsigned int)CMN_CompareStringNoCaseW(a2, L"IsFindingPhrases")
                                          && (unsigned int)CMN_CompareStringNoCaseW(a2, L"FindingPhrases")
                                          && (unsigned int)CMN_CompareStringNoCaseW(a2, L"Phrases") )
                                        {
                                          if ( (unsigned int)CMN_CompareStringNoCaseW(a2, L"IsComputingHyphenation")
                                            && (unsigned int)CMN_CompareStringNoCaseW(a2, L"ComputingHyphenation")
                                            && (unsigned int)CMN_CompareStringNoCaseW(a2, L"Hyphenation") )
                                          {
                                            if ( (unsigned int)CMN_CompareStringNoCaseW(a2, L"IsSpellChecking")
                                              && (unsigned int)CMN_CompareStringNoCaseW(a2, L"SpellChecking")
                                              && (unsigned int)CMN_CompareStringNoCaseW(a2, L"Checking") )
                                            {
                                              if ( (unsigned int)CMN_CompareStringNoCaseW(
                                                                   a2,
                                                                   L"IsSpellAlwaysSuggesting")
                                                && (unsigned int)CMN_CompareStringNoCaseW(a2, L"SpellAlwaysSuggesting")
                                                && (unsigned int)CMN_CompareStringNoCaseW(a2, L"AlwaysSuggesting") )
                                              {
                                                if ( (unsigned int)CMN_CompareStringNoCaseW(
                                                                     a2,
                                                                     L"IsSpellSuggestingMWEs")
                                                  && (unsigned int)CMN_CompareStringNoCaseW(a2, L"SpellSuggestingMWEs")
                                                  && (unsigned int)CMN_CompareStringNoCaseW(a2, L"SuggestingMWEs") )
                                                {
                                                  if ( (unsigned int)CMN_CompareStringNoCaseW(
                                                                       a2,
                                                                       L"IsSpellForcingCompoundSuggestions")
                                                    && (unsigned int)CMN_CompareStringNoCaseW(
                                                                       a2,
                                                                       L"SpellForcingCompoundSuggestions")
                                                    && (unsigned int)CMN_CompareStringNoCaseW(
                                                                       a2,
                                                                       L"ForcingCompoundSuggestions") )
                                                  {
                                                    if ( (unsigned int)CMN_CompareStringNoCaseW(
                                                                         a2,
                                                                         L"IsSpellUsingDialects")
                                                      && (unsigned int)CMN_CompareStringNoCaseW(
                                                                         a2,
                                                                         L"SpellUsingDialects")
                                                      && (unsigned int)CMN_CompareStringNoCaseW(a2, L"UsingDialects") )
                                                    {
                                                      if ( (unsigned int)CMN_CompareStringNoCaseW(
                                                                           a2,
                                                                           L"IsSpellVerifyOnly")
                                                        && (unsigned int)CMN_CompareStringNoCaseW(
                                                                           a2,
                                                                           L"SpellVerifyOnly")
                                                        && (unsigned int)CMN_CompareStringNoCaseW(a2, L"VerifyOnly") )
                                                      {
                                                        if ( (unsigned int)CMN_CompareStringNoCaseW(
                                                                             a2,
                                                                             L"IsSpellVerifyAutoReplace")
                                                          && (unsigned int)CMN_CompareStringNoCaseW(
                                                                             a2,
                                                                             L"SpellVerifyAutoReplace")
                                                          && (unsigned int)CMN_CompareStringNoCaseW(
                                                                             a2,
                                                                             L"VerifyAutoReplace") )
                                                        {
                                                          if ( (unsigned int)CMN_CompareStringNoCaseW(
                                                                               a2,
                                                                               L"IsSpellContinued")
                                                            && (unsigned int)CMN_CompareStringNoCaseW(
                                                                               a2,
                                                                               L"SpellContinued")
                                                            && (unsigned int)CMN_CompareStringNoCaseW(a2, L"Continued") )
                                                          {
                                                            if ( (unsigned int)CMN_CompareStringNoCaseW(
                                                                                 a2,
                                                                                 L"IsSpellCaseSensitive")
                                                              && (unsigned int)CMN_CompareStringNoCaseW(
                                                                                 a2,
                                                                                 L"SpellCaseSensitive")
                                                              && (unsigned int)CMN_CompareStringNoCaseW(
                                                                                 a2,
                                                                                 L"CaseSensitive") )
                                                            {
                                                              if ( !(unsigned int)CMN_CompareStringNoCaseW(
                                                                                    a2,
                                                                                    L"SpellLexDataID")
                                                                || !(unsigned int)CMN_CompareStringNoCaseW(
                                                                                    a2,
                                                                                    L"LexDataID") )
                                                              {
                                                                v7 = *((unsigned int *)this + 72);
                                                                goto LABEL_187;
                                                              }
                                                              if ( (unsigned int)CMN_CompareStringNoCaseW(
                                                                                   a2,
                                                                                   L"IsSuggestFromMainLexOnly")
                                                                && (unsigned int)CMN_CompareStringNoCaseW(
                                                                                   a2,
                                                                                   L"SuggestFromMainLexOnly") )
                                                              {
                                                                if ( (unsigned int)CMN_CompareStringNoCaseW(
                                                                                     a2,
                                                                                     L"IsIgnoreAllCaps")
                                                                  && (unsigned int)CMN_CompareStringNoCaseW(
                                                                                     a2,
                                                                                     L"IgnoreAllCaps") )
                                                                {
                                                                  if ( (unsigned int)CMN_CompareStringNoCaseW(
                                                                                       a2,
                                                                                       L"IsIgnoreMixedDigits")
                                                                    && (unsigned int)CMN_CompareStringNoCaseW(
                                                                                       a2,
                                                                                       L"IgnoreMixedDigits") )
                                                                  {
                                                                    if ( (unsigned int)CMN_CompareStringNoCaseW(
                                                                                         a2,
                                                                                         L"IsIgnoreRomanNumerals")
                                                                      && (unsigned int)CMN_CompareStringNoCaseW(
                                                                                         a2,
                                                                                         L"IgnoreRomanNumerals") )
                                                                    {
                                                                      if ( (unsigned int)CMN_CompareStringNoCaseW(
                                                                                           a2,
                                                                                           L"IsFindRepeatWord")
                                                                        && (unsigned int)CMN_CompareStringNoCaseW(
                                                                                           a2,
                                                                                           L"FindRepeatWord") )
                                                                      {
                                                                        if ( (unsigned int)CMN_CompareStringNoCaseW(
                                                                                             a2,
                                                                                             L"IsIgnoreSingleLetter")
                                                                          && (unsigned int)CMN_CompareStringNoCaseW(
                                                                                             a2,
                                                                                             L"IgnoreSingleLetter") )
                                                                        {
                                                                          if ( (unsigned int)CMN_CompareStringNoCaseW(
                                                                                               a2,
                                                                                               L"IsContextSpell")
                                                                            && (unsigned int)CMN_CompareStringNoCaseW(
                                                                                               a2,
                                                                                               L"ContextSpell") )
                                                                          {
                                                                            if ( (unsigned int)CMN_CompareStringNoCaseW(
                                                                                                 a2,
                                                                                                 L"IsIgnoreUrls")
                                                                              && (unsigned int)CMN_CompareStringNoCaseW(
                                                                                                 a2,
                                                                                                 L"IgnoreUrls") )
                                                                            {
                                                                              if ( (unsigned int)CMN_CompareStringNoCaseW(
                                                                                                   a2,
                                                                                                   L"IsFrenchAccentedUppercase")
                                                                                && (unsigned int)CMN_CompareStringNoCaseW(
                                                                                                   a2,
                                                                                                   L"FrenchAccentedUppercase") )
                                                                              {
                                                                                if ( !(unsigned int)CMN_CompareStringNoCaseW(a2, L"FrenchReform") )
                                                                                {
                                                                                  v7 = *((unsigned int *)this + 76);
LABEL_187:
                                                                                  _variant_t::operator=(a3, v7);
                                                                                  return 1;
                                                                                }
                                                                                if ( (unsigned int)CMN_CompareStringNoCaseW(
                                                                                                     a2,
                                                                                                     L"IsGermanPrereform")
                                                                                  && (unsigned int)CMN_CompareStringNoCaseW(
                                                                                                     a2,
                                                                                                     L"GermanPrereform") )
                                                                                {
                                                                                  if ( (unsigned int)CMN_CompareStringNoCaseW(a2, L"IsKoreanAuxCombine")
                                                                                    && (unsigned int)CMN_CompareStringNoCaseW(a2, L"KoreanAuxCombine") )
                                                                                  {
                                                                                    if ( (unsigned int)CMN_CompareStringNoCaseW(a2, L"IsKoreanMissSpellDictSearch")
                                                                                      && (unsigned int)CMN_CompareStringNoCaseW(a2, L"KoreanMissSpellDictSearch") )
                                                                                    {
                                                                                      if ( (unsigned int)CMN_CompareStringNoCaseW(a2, L"IsKoreanCompoundNounProc")
                                                                                        && (unsigned int)CMN_CompareStringNoCaseW(a2, L"KoreanCompoundNounProc") )
                                                                                      {
                                                                                        if ( (unsigned int)CMN_CompareStringNoCaseW(a2, L"IsArabicStrictAlefHamza")
                                                                                          && (unsigned int)CMN_CompareStringNoCaseW(a2, L"ArabicStrictAlefHamza") )
                                                                                        {
                                                                                          if ( (unsigned int)CMN_CompareStringNoCaseW(a2, L"IsArabicStrictFinalYaa")
                                                                                            && (unsigned int)CMN_CompareStringNoCaseW(a2, L"ArabicStrictFinalYaa") )
                                                                                          {
                                                                                            if ( (unsigned int)CMN_CompareStringNoCaseW(a2, L"IsHebrewPartialScript")
                                                                                              && (unsigned int)CMN_CompareStringNoCaseW(a2, L"HebrewPartialScript") )
                                                                                            {
                                                                                              if ( (unsigned int)CMN_CompareStringNoCaseW(a2, L"IsHebrewMixedScript")
                                                                                                && (unsigned int)CMN_CompareStringNoCaseW(a2, L"HebrewMixedScript") )
                                                                                              {
                                                                                                if ( !(unsigned int)CMN_CompareStringNoCaseW(a2, L"GermanReform") )
                                                                                                {
                                                                                                  v7 = *((unsigned int *)this + 79);
                                                                                                  goto LABEL_187;
                                                                                                }
                                                                                                if ( (unsigned int)CMN_CompareStringNoCaseW(a2, L"IsReturnAutoReplace") && (unsigned int)CMN_CompareStringNoCaseW(a2, L"ReturnAutoReplace") )
                                                                                                  return 0;
                                                                                                LOBYTE(v6) = *((_BYTE *)this + 320);
                                                                                              }
                                                                                              else
                                                                                              {
                                                                                                LOBYTE(v6) = *((_BYTE *)this + 315);
                                                                                              }
                                                                                            }
                                                                                            else
                                                                                            {
                                                                                              LOBYTE(v6) = *((_BYTE *)this + 314);
                                                                                            }
                                                                                          }
                                                                                          else
                                                                                          {
                                                                                            LOBYTE(v6) = *((_BYTE *)this + 313);
                                                                                          }
                                                                                        }
                                                                                        else
                                                                                        {
                                                                                          LOBYTE(v6) = *((_BYTE *)this + 312);
                                                                                        }
                                                                                      }
                                                                                      else
                                                                                      {
                                                                                        LOBYTE(v6) = *((_BYTE *)this + 311);
                                                                                      }
                                                                                    }
                                                                                    else
                                                                                    {
                                                                                      LOBYTE(v6) = *((_BYTE *)this + 310);
                                                                                    }
                                                                                  }
                                                                                  else
                                                                                  {
                                                                                    LOBYTE(v6) = *((_BYTE *)this + 309);
                                                                                  }
                                                                                }
                                                                                else
                                                                                {
                                                                                  LOBYTE(v6) = *((_BYTE *)this + 308);
                                                                                }
                                                                              }
                                                                              else
                                                                              {
                                                                                LOBYTE(v6) = *((_BYTE *)this + 300);
                                                                              }
                                                                            }
                                                                            else
                                                                            {
                                                                              LOBYTE(v6) = *((_BYTE *)this + 299);
                                                                            }
                                                                          }
                                                                          else
                                                                          {
                                                                            LOBYTE(v6) = *((_BYTE *)this + 298);
                                                                          }
                                                                        }
                                                                        else
                                                                        {
                                                                          LOBYTE(v6) = *((_BYTE *)this + 297);
                                                                        }
                                                                      }
                                                                      else
                                                                      {
                                                                        LOBYTE(v6) = *((_BYTE *)this + 296);
                                                                      }
                                                                    }
                                                                    else
                                                                    {
                                                                      LOBYTE(v6) = *((_BYTE *)this + 295);
                                                                    }
                                                                  }
                                                                  else
                                                                  {
                                                                    LOBYTE(v6) = *((_BYTE *)this + 294);
                                                                  }
                                                                }
                                                                else
                                                                {
                                                                  LOBYTE(v6) = *((_BYTE *)this + 293);
                                                                }
                                                              }
                                                              else
                                                              {
                                                                LOBYTE(v6) = *((_BYTE *)this + 292);
                                                              }
                                                            }
                                                            else
                                                            {
                                                              LOBYTE(v6) = *((_BYTE *)this + 287);
                                                            }
                                                          }
                                                          else
                                                          {
                                                            LOBYTE(v6) = *((_BYTE *)this + 286);
                                                          }
                                                        }
                                                        else
                                                        {
                                                          LOBYTE(v6) = *((_BYTE *)this + 285);
                                                        }
                                                      }
                                                      else
                                                      {
                                                        LOBYTE(v6) = *((_BYTE *)this + 284);
                                                      }
                                                    }
                                                    else
                                                    {
                                                      LOBYTE(v6) = *((_BYTE *)this + 283);
                                                    }
                                                  }
                                                  else
                                                  {
                                                    LOBYTE(v6) = *((_BYTE *)this + 282);
                                                  }
                                                }
                                                else
                                                {
                                                  LOBYTE(v6) = *((_BYTE *)this + 281);
                                                }
                                              }
                                              else
                                              {
                                                LOBYTE(v6) = *((_BYTE *)this + 280);
                                              }
                                            }
                                            else
                                            {
                                              LOBYTE(v6) = *((_BYTE *)this + 279);
                                            }
                                          }
                                          else
                                          {
                                            LOBYTE(v6) = *((_BYTE *)this + 278);
                                          }
                                        }
                                        else
                                        {
                                          LOBYTE(v6) = *((_BYTE *)this + 35);
                                        }
                                      }
                                      else
                                      {
                                        LOBYTE(v6) = *((_BYTE *)this + 34);
                                      }
                                    }
                                    else
                                    {
                                      LOBYTE(v6) = *((_BYTE *)this + 33);
                                    }
                                  }
                                  else
                                  {
                                    LOBYTE(v6) = *((_BYTE *)this + 32);
                                  }
                                }
                                else
                                {
                                  LOBYTE(v6) = *((_BYTE *)this + 31);
                                }
                              }
                              else
                              {
                                LOBYTE(v6) = *((_BYTE *)this + 30);
                              }
                            }
                            else
                            {
                              LOBYTE(v6) = *((_BYTE *)this + 29);
                            }
                          }
                          else
                          {
                            LOBYTE(v6) = *((_BYTE *)this + 28);
                          }
                        }
                        else
                        {
                          LOBYTE(v6) = *((_BYTE *)this + 27);
                        }
                      }
                      else
                      {
                        LOBYTE(v6) = *((_BYTE *)this + 26);
                      }
                    }
                    else
                    {
                      LOBYTE(v6) = *((_BYTE *)this + 25);
                    }
                  }
                  else
                  {
                    LOBYTE(v6) = *((_BYTE *)this + 24);
                  }
                }
                else
                {
                  LOBYTE(v6) = *((_BYTE *)this + 23);
                }
              }
              else
              {
                LOBYTE(v6) = *((_BYTE *)this + 22);
              }
            }
            else
            {
              LOBYTE(v6) = *((_BYTE *)this + 21);
            }
          }
          else
          {
            LOBYTE(v6) = (**(__int64 (__fastcall ***)(CContextBase *))this)(this);
          }
        }
        else
        {
          LOBYTE(v6) = *((_BYTE *)this + 19);
        }
      }
      else
      {
        LOBYTE(v6) = *((_BYTE *)this + 18);
      }
    }
    else
    {
      LOBYTE(v6) = *((_BYTE *)this + 17);
    }
  }
  else
  {
    LOBYTE(v6) = *((_BYTE *)this + 16);
  }
  _variant_t::operator=(a3, v6);
  return 1;
}

```

## disassembly

```asm
0x18005e510  mov     [rsp+arg_0], rbx
0x18005e515  mov     [rsp+arg_8], rsi
0x18005e51a  push    rdi
0x18005e51b  sub     rsp, 20h
0x18005e51f  mov     rbx, rdx
0x18005e522  mov     rdi, rcx
0x18005e525  mov     rcx, rbx
0x18005e528  lea     rdx, aMaxsentences; "MaxSentences"
0x18005e52f  mov     rsi, r8
0x18005e532  call    CMN_CompareStringNoCaseW
0x18005e537  test    eax, eax
0x18005e539  jz      loc_18005F2D3
0x18005e53f  lea     rdx, aNldpSentenceCo; "NLDP_SENTENCE_COUNT"
0x18005e546  mov     rcx, rbx
0x18005e549  call    CMN_CompareStringNoCaseW
0x18005e54e  test    eax, eax
0x18005e550  jz      loc_18005F2D3
0x18005e556  lea     rdx, aNsents; "NSents"
0x18005e55d  mov     rcx, rbx
0x18005e560  call    CMN_CompareStringNoCaseW
0x18005e565  test    eax, eax
0x18005e567  jz      loc_18005F2D3
0x18005e56d  lea     rdx, aIssinglelangua; "IsSingleLanguage"
0x18005e574  mov     rcx, rbx
0x18005e577  call    CMN_CompareStringNoCaseW
0x18005e57c  test    eax, eax
0x18005e57e  jz      loc_18005F2CB
0x18005e584  lea     rdx, aSinglelanguage; "SingleLanguage"
0x18005e58b  mov     rcx, rbx
0x18005e58e  call    CMN_CompareStringNoCaseW
0x18005e593  test    eax, eax
0x18005e595  jz      loc_18005F2CB
0x18005e59b  lea     rdx, aIssimplewordbr; "IsSimpleWordBreaking"
0x18005e5a2  mov     rcx, rbx
0x18005e5a5  call    CMN_CompareStringNoCaseW
0x18005e5aa  test    eax, eax
0x18005e5ac  jz      loc_18005F2C3
0x18005e5b2  lea     rdx, aSimplewordbrea; "SimpleWordBreaking"
0x18005e5b9  mov     rcx, rbx
0x18005e5bc  call    CMN_CompareStringNoCaseW
0x18005e5c1  test    eax, eax
0x18005e5c3  jz      loc_18005F2C3
0x18005e5c9  lea     rdx, aUserelativetim; "UseRelativeTimes"
0x18005e5d0  mov     rcx, rbx
0x18005e5d3  call    CMN_CompareStringNoCaseW
0x18005e5d8  test    eax, eax
0x18005e5da  jz      loc_18005F2BB
0x18005e5e0  lea     rdx, aUserelativetim; "UseRelativeTimes"
0x18005e5e7  mov     rcx, rbx
0x18005e5ea  call    CMN_CompareStringNoCaseW
0x18005e5ef  test    eax, eax
0x18005e5f1  jz      loc_18005F2BB
0x18005e5f7  lea     rdx, aIgnorepunctuat; "IgnorePunctuation"
0x18005e5fe  mov     rcx, rbx
0x18005e601  call    CMN_CompareStringNoCaseW
0x18005e606  test    eax, eax
0x18005e608  jz      loc_18005F2B3
0x18005e60e  lea     rdx, aIgnorepunctuat; "IgnorePunctuation"
0x18005e615  mov     rcx, rbx
0x18005e618  call    CMN_CompareStringNoCaseW
0x18005e61d  test    eax, eax
0x18005e61f  jz      loc_18005F2B3
0x18005e625  lea     rdx, aIscaching; "IsCaching"
0x18005e62c  mov     rcx, rbx
0x18005e62f  call    CMN_CompareStringNoCaseW
0x18005e634  test    eax, eax
0x18005e636  jz      loc_18005F29E
0x18005e63c  lea     rdx, aCaching; "Caching"
0x18005e643  mov     rcx, rbx
0x18005e646  call    CMN_CompareStringNoCaseW
0x18005e64b  test    eax, eax
0x18005e64d  jz      loc_18005F29E
0x18005e653  lea     rdx, aIsshowinggaps; "IsShowingGaps"
0x18005e65a  mov     rcx, rbx
0x18005e65d  call    CMN_CompareStringNoCaseW
0x18005e662  test    eax, eax
0x18005e664  jz      loc_18005F296
0x18005e66a  lea     rdx, aShowinggaps; "ShowingGaps"
0x18005e671  mov     rcx, rbx
0x18005e674  call    CMN_CompareStringNoCaseW
0x18005e679  test    eax, eax
0x18005e67b  jz      loc_18005F296
0x18005e681  lea     rdx, aGaps; "Gaps"
0x18005e688  mov     rcx, rbx
0x18005e68b  call    CMN_CompareStringNoCaseW
0x18005e690  test    eax, eax
0x18005e692  jz      loc_18005F296
0x18005e698  lea     rdx, aIsshowingchara; "IsShowingCharacterNormalizations"
0x18005e69f  mov     rcx, rbx
0x18005e6a2  call    CMN_CompareStringNoCaseW
0x18005e6a7  test    eax, eax
0x18005e6a9  jz      loc_18005F28E
0x18005e6af  lea     rdx, aShowingcharact; "ShowingCharacterNormalizations"
0x18005e6b6  mov     rcx, rbx
0x18005e6b9  call    CMN_CompareStringNoCaseW
0x18005e6be  test    eax, eax
0x18005e6c0  jz      loc_18005F28E
0x18005e6c6  lea     rdx, aCharacternorma; "CharacterNormalizations"
0x18005e6cd  mov     rcx, rbx
0x18005e6d0  call    CMN_CompareStringNoCaseW
0x18005e6d5  test    eax, eax
0x18005e6d7  jz      loc_18005F28E
0x18005e6dd  lea     rdx, aIsshowingwordn; "IsShowingWordNormalizations"
0x18005e6e4  mov     rcx, rbx
0x18005e6e7  call    CMN_CompareStringNoCaseW
0x18005e6ec  test    eax, eax
0x18005e6ee  jz      loc_18005F286
0x18005e6f4  lea     rdx, aShowingwordnor; "ShowingWordNormalizations"
0x18005e6fb  mov     rcx, rbx
0x18005e6fe  call    CMN_CompareStringNoCaseW
0x18005e703  test    eax, eax
0x18005e705  jz      loc_18005F286
0x18005e70b  lea     rdx, aWordnormalizat; "WordNormalizations"
0x18005e712  mov     rcx, rbx
0x18005e715  call    CMN_CompareStringNoCaseW
0x18005e71a  test    eax, eax
0x18005e71c  jz      loc_18005F286
0x18005e722  lea     rdx, aIscomputingcom; "IsComputingCompounds"
0x18005e729  mov     rcx, rbx
0x18005e72c  call    CMN_CompareStringNoCaseW
0x18005e731  test    eax, eax
0x18005e733  jz      loc_18005F27E
0x18005e739  lea     rdx, aComputingcompo; "ComputingCompounds"
0x18005e740  mov     rcx, rbx
0x18005e743  call    CMN_CompareStringNoCaseW
0x18005e748  test    eax, eax
0x18005e74a  jz      loc_18005F27E
0x18005e750  lea     rdx, aCompounds; "Compounds"
0x18005e757  mov     rcx, rbx
0x18005e75a  call    CMN_CompareStringNoCaseW
0x18005e75f  test    eax, eax
0x18005e761  jz      loc_18005F27E
0x18005e767  lea     rdx, aIscomputinginf; "IsComputingInflections"
0x18005e76e  mov     rcx, rbx
0x18005e771  call    CMN_CompareStringNoCaseW
0x18005e776  test    eax, eax
0x18005e778  jz      loc_18005F276
0x18005e77e  lea     rdx, aComputinginfle; "ComputingInflections"
0x18005e785  mov     rcx, rbx
0x18005e788  call    CMN_CompareStringNoCaseW
0x18005e78d  test    eax, eax
0x18005e78f  jz      loc_18005F276
0x18005e795  lea     rdx, aInflections; "Inflections"
0x18005e79c  mov     rcx, rbx
0x18005e79f  call    CMN_CompareStringNoCaseW
0x18005e7a4  test    eax, eax
0x18005e7a6  jz      loc_18005F276
0x18005e7ac  lea     rdx, aNldpSectionInf; "NLDP_SECTION_INFL_MORPH"
0x18005e7b3  mov     rcx, rbx
0x18005e7b6  call    CMN_CompareStringNoCaseW
0x18005e7bb  test    eax, eax
0x18005e7bd  jz      loc_18005F276
0x18005e7c3  lea     rdx, aInflforms; "InflForms"
0x18005e7ca  mov     rcx, rbx
0x18005e7cd  call    CMN_CompareStringNoCaseW
0x18005e7d2  test    eax, eax
0x18005e7d4  jz      loc_18005F276
0x18005e7da  lea     rdx, aIscomputinglem; "IsComputingLemmas"
0x18005e7e1  mov     rcx, rbx
0x18005e7e4  call    CMN_CompareStringNoCaseW
0x18005e7e9  test    eax, eax
0x18005e7eb  jz      loc_18005F26E
0x18005e7f1  lea     rdx, aComputinglemma; "ComputingLemmas"
0x18005e7f8  mov     rcx, rbx
0x18005e7fb  call    CMN_CompareStringNoCaseW
0x18005e800  test    eax, eax
0x18005e802  jz      loc_18005F26E
0x18005e808  lea     rdx, aLemmas; "Lemmas"
0x18005e80f  mov     rcx, rbx
0x18005e812  call    CMN_CompareStringNoCaseW
0x18005e817  test    eax, eax
0x18005e819  jz      loc_18005F26E
0x18005e81f  lea     rdx, aSectionlemmas; "SectionLemmas"
0x18005e826  mov     rcx, rbx
0x18005e829  call    CMN_CompareStringNoCaseW
0x18005e82e  test    eax, eax
0x18005e830  jz      loc_18005F26E
0x18005e836  lea     rdx, aIscomputingexp; "IsComputingExpansions"
0x18005e83d  mov     rcx, rbx
0x18005e840  call    CMN_CompareStringNoCaseW
0x18005e845  test    eax, eax
0x18005e847  jz      loc_18005F266
0x18005e84d  lea     rdx, aComputingexpan; "ComputingExpansions"
0x18005e854  mov     rcx, rbx
0x18005e857  call    CMN_CompareStringNoCaseW
0x18005e85c  test    eax, eax
0x18005e85e  jz      loc_18005F266
0x18005e864  lea     rdx, aExpansions; "Expansions"
0x18005e86b  mov     rcx, rbx
0x18005e86e  call    CMN_CompareStringNoCaseW
0x18005e873  test    eax, eax
0x18005e875  jz      loc_18005F266
0x18005e87b  lea     rdx, aIscomputingbas; "IsComputingBases"
0x18005e882  mov     rcx, rbx
0x18005e885  call    CMN_CompareStringNoCaseW
0x18005e88a  test    eax, eax
0x18005e88c  jz      loc_18005F25E
0x18005e892  lea     rdx, aComputingbases; "ComputingBases"
0x18005e899  mov     rcx, rbx
0x18005e89c  call    CMN_CompareStringNoCaseW
0x18005e8a1  test    eax, eax
0x18005e8a3  jz      loc_18005F25E
0x18005e8a9  lea     rdx, aBases; "Bases"
0x18005e8b0  mov     rcx, rbx
0x18005e8b3  call    CMN_CompareStringNoCaseW
0x18005e8b8  test    eax, eax
0x18005e8ba  jz      loc_18005F25E
0x18005e8c0  lea     rdx, aIscomputingpar; "IsComputingPartOfSpeechTags"
0x18005e8c7  mov     rcx, rbx
0x18005e8ca  call    CMN_CompareStringNoCaseW
0x18005e8cf  test    eax, eax
0x18005e8d1  jz      loc_18005F256
0x18005e8d7  lea     rdx, aComputingparto; "ComputingPartOfSpeechTags"
0x18005e8de  mov     rcx, rbx
0x18005e8e1  call    CMN_CompareStringNoCaseW
0x18005e8e6  test    eax, eax
0x18005e8e8  jz      loc_18005F256
0x18005e8ee  lea     rdx, aPartofspeechta; "PartOfSpeechTags"
0x18005e8f5  mov     rcx, rbx
0x18005e8f8  call    CMN_CompareStringNoCaseW
0x18005e8fd  test    eax, eax
0x18005e8ff  jz      loc_18005F256
0x18005e905  lea     rdx, aPostags; "PosTags"
0x18005e90c  mov     rcx, rbx
0x18005e90f  call    CMN_CompareStringNoCaseW
0x18005e914  test    eax, eax
0x18005e916  jz      loc_18005F256
0x18005e91c  lea     rdx, aIsfindingdefin; "IsFindingDefinitions"
0x18005e923  mov     rcx, rbx
0x18005e926  call    CMN_CompareStringNoCaseW
0x18005e92b  test    eax, eax
0x18005e92d  jz      loc_18005F24E
0x18005e933  lea     rdx, aFindingdefinit; "FindingDefinitions"
0x18005e93a  mov     rcx, rbx
0x18005e93d  call    CMN_CompareStringNoCaseW
0x18005e942  test    eax, eax
0x18005e944  jz      loc_18005F24E
0x18005e94a  lea     rdx, aDefinitions; "Definitions"
0x18005e951  mov     rcx, rbx
0x18005e954  call    CMN_CompareStringNoCaseW
0x18005e959  test    eax, eax
0x18005e95b  jz      loc_18005F24E
0x18005e961  lea     rdx, aIsfindingdatet; "IsFindingDateTimeMeasures"
0x18005e968  mov     rcx, rbx
0x18005e96b  call    CMN_CompareStringNoCaseW
0x18005e970  test    eax, eax
0x18005e972  jz      loc_18005F246
0x18005e978  lea     rdx, aFindingdatetim; "FindingDateTimeMeasures"
0x18005e97f  mov     rcx, rbx
0x18005e982  call    CMN_CompareStringNoCaseW
0x18005e987  test    eax, eax
0x18005e989  jz      loc_18005F246
0x18005e98f  lea     rdx, aDatetimemeasur; "DateTimeMeasures"
0x18005e996  mov     rcx, rbx
0x18005e999  call    CMN_CompareStringNoCaseW
0x18005e99e  test    eax, eax
0x18005e9a0  jz      loc_18005F246
0x18005e9a6  lea     rdx, aIsfindingperso; "IsFindingPersons"
0x18005e9ad  mov     rcx, rbx
0x18005e9b0  call    CMN_CompareStringNoCaseW
0x18005e9b5  test    eax, eax
0x18005e9b7  jz      loc_18005F23E
0x18005e9bd  lea     rdx, aFindingpersons; "FindingPersons"
0x18005e9c4  mov     rcx, rbx
0x18005e9c7  call    CMN_CompareStringNoCaseW
0x18005e9cc  test    eax, eax
0x18005e9ce  jz      loc_18005F23E
0x18005e9d4  lea     rdx, aPersons; "Persons"
0x18005e9db  mov     rcx, rbx
0x18005e9de  call    CMN_CompareStringNoCaseW
0x18005e9e3  test    eax, eax
0x18005e9e5  jz      loc_18005F23E
0x18005e9eb  lea     rdx, aIsfindinglocat; "IsFindingLocations"
0x18005e9f2  mov     rcx, rbx
0x18005e9f5  call    CMN_CompareStringNoCaseW
0x18005e9fa  test    eax, eax
0x18005e9fc  jz      loc_18005F236
0x18005ea02  lea     rdx, aFindinglocatio; "FindingLocations"
0x18005ea09  mov     rcx, rbx
0x18005ea0c  call    CMN_CompareStringNoCaseW
0x18005ea11  test    eax, eax
0x18005ea13  jz      loc_18005F236
0x18005ea19  lea     rdx, aLocations; "Locations"
0x18005ea20  mov     rcx, rbx
0x18005ea23  call    CMN_CompareStringNoCaseW
0x18005ea28  test    eax, eax
0x18005ea2a  jz      loc_18005F236
0x18005ea30  lea     rdx, aIsfindingorgan; "IsFindingOrganizations"
0x18005ea37  mov     rcx, rbx
0x18005ea3a  call    CMN_CompareStringNoCaseW
0x18005ea3f  test    eax, eax
0x18005ea41  jz      loc_18005F22E
0x18005ea47  lea     rdx, aFindingorganiz; "FindingOrganizations"
0x18005ea4e  mov     rcx, rbx
0x18005ea51  call    CMN_CompareStringNoCaseW
0x18005ea56  test    eax, eax
0x18005ea58  jz      loc_18005F22E
0x18005ea5e  lea     rdx, aOrganizations; "Organizations"
0x18005ea65  mov     rcx, rbx
0x18005ea68  call    CMN_CompareStringNoCaseW
  ... truncated ...
```
