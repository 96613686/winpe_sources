# _dynamic_initializer_for__DialogEngine::RequestPreference::preferenceNames__

- ea: `0x180003840`
- end: `0x180003ad4`
- name: `_dynamic_initializer_for__DialogEngine::RequestPreference::preferenceNames__`
- size: `660`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `reparse_path, registry_config, broker_com_uri`

## callees

- `0x180004e14`
- `0x180009e14`

## string_xrefs

- `0x180003858`: `MaxInitialPaths`
- `0x18000386c`: `MaxSubsequentPaths`
- `0x18000395c`: `AllowQueryCompletions`
- `0x1800039d4`: `WordCompletionPenalty`
- `0x180003a4c`: `CompletionEntityCount`

## pseudocode

```c
// Hidden C++ exception states: #wind=31
int dynamic_initializer_for__DialogEngine::RequestPreference::preferenceNames__()
{
  std::string::string(DialogEngine::RequestPreference::preferenceNames, "Undefined");
  std::string::string(qword_18013E850, "MaxInitialPaths");
  std::string::string(qword_18013E870, "MaxSubsequentPaths");
  std::string::string(qword_18013E890, "MaxEntitiesToCheck");
  std::string::string(qword_18013E8B0, "LookupTimeout");
  std::string::string(qword_18013E8D0, "ForceStopAfterNSuggestions");
  std::string::string(qword_18013E8F0, "ReturnAttributes");
  std::string::string(qword_18013E910, "ReturnMetadata");
  std::string::string(qword_18013E930, "ReturnParsingInfo");
  std::string::string(qword_18013E950, "ReturnQuery");
  std::string::string(qword_18013E970, "MaxSuggestionsOverride");
  std::string::string(qword_18013E990, "GetNonQueryAttributes");
  std::string::string(qword_18013E9B0, "DedupOnEntityID");
  std::string::string(qword_18013E9D0, "DedupOnSemanticInterpretation");
  std::string::string(qword_18013E9F0, "AllowQueryCompletions");
  std::string::string(qword_18013EA10, "GetOnlyTargetAttributes");
  std::string::string(qword_18013EA30, "RetainQueryText");
  std::string::string(qword_18013EA50, "IncludeUnconstrainingInDedup");
  std::string::string(qword_18013EA70, "ReturnFilters");
  std::string::string(qword_18013EA90, "EnableSpellingCorrection");
  std::string::string(qword_18013EAB0, "WordCompletionPenalty");
  std::string::string(qword_18013EAD0, "MaxConvScore");
  std::string::string(qword_18013EAF0, "AbsolutePruningThreshold");
  std::string::string(qword_18013EB10, "RelativePruningThreshold");
  std::string::string(qword_18013EB30, "MaxMatchCount");
  std::string::string(qword_18013EB50, "SubExpressionExpansionCount");
  std::string::string(qword_18013EB70, "CompletionEntityCount");
  std::string::string(qword_18013EB90, "DefaultSelectManyCount");
  std::string::string(qword_18013EBB0, "MaxGrammarDepth");
  std::string::string(qword_18013EBD0, "Market");
  std::string::string(qword_18013EBF0, "IME");
  std::string::string(qword_18013EC10, "Segment");
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__DialogEngine::RequestPreference::preferenceNames__);
}

```

## disassembly

```asm
0x180003840  sub     rsp, 28h
0x180003844  lea     rdx, aUndefined; "Undefined"
0x18000384b  lea     rcx, ?preferenceNames@RequestPreference@DialogEngine@@0QBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@B; std::string const near * const DialogEngine::RequestPreference::preferenceNames
0x180003852  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180003857  nop
0x180003858  lea     rdx, aMaxinitialpath; "MaxInitialPaths"
0x18000385f  lea     rcx, qword_18013E850
0x180003866  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18000386b  nop
0x18000386c  lea     rdx, aMaxsubsequentp; "MaxSubsequentPaths"
0x180003873  lea     rcx, qword_18013E870
0x18000387a  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18000387f  nop
0x180003880  lea     rdx, aMaxentitiestoc; "MaxEntitiesToCheck"
0x180003887  lea     rcx, qword_18013E890
0x18000388e  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180003893  nop
0x180003894  lea     rdx, aLookuptimeout; "LookupTimeout"
0x18000389b  lea     rcx, qword_18013E8B0
0x1800038a2  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800038a7  nop
0x1800038a8  lea     rdx, aForcestopafter; "ForceStopAfterNSuggestions"
0x1800038af  lea     rcx, qword_18013E8D0
0x1800038b6  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800038bb  nop
0x1800038bc  lea     rdx, aReturnattribut; "ReturnAttributes"
0x1800038c3  lea     rcx, qword_18013E8F0
0x1800038ca  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800038cf  nop
0x1800038d0  lea     rdx, aReturnmetadata; "ReturnMetadata"
0x1800038d7  lea     rcx, qword_18013E910
0x1800038de  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800038e3  nop
0x1800038e4  lea     rdx, aReturnparsingi; "ReturnParsingInfo"
0x1800038eb  lea     rcx, qword_18013E930
0x1800038f2  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800038f7  nop
0x1800038f8  lea     rdx, aReturnquery; "ReturnQuery"
0x1800038ff  lea     rcx, qword_18013E950
0x180003906  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18000390b  nop
0x18000390c  lea     rdx, aMaxsuggestions; "MaxSuggestionsOverride"
0x180003913  lea     rcx, qword_18013E970
0x18000391a  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18000391f  nop
0x180003920  lea     rdx, aGetnonqueryatt; "GetNonQueryAttributes"
0x180003927  lea     rcx, qword_18013E990
0x18000392e  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180003933  nop
0x180003934  lea     rdx, aDeduponentityi; "DedupOnEntityID"
0x18000393b  lea     rcx, qword_18013E9B0
0x180003942  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180003947  nop
0x180003948  lea     rdx, aDeduponsemanti; "DedupOnSemanticInterpretation"
0x18000394f  lea     rcx, qword_18013E9D0
0x180003956  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18000395b  nop
0x18000395c  lea     rdx, aAllowquerycomp; "AllowQueryCompletions"
0x180003963  lea     rcx, qword_18013E9F0
0x18000396a  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18000396f  nop
0x180003970  lea     rdx, aGetonlytargeta; "GetOnlyTargetAttributes"
0x180003977  lea     rcx, qword_18013EA10
0x18000397e  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180003983  nop
0x180003984  lea     rdx, aRetainquerytex; "RetainQueryText"
0x18000398b  lea     rcx, qword_18013EA30
0x180003992  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180003997  nop
0x180003998  lea     rdx, aIncludeunconst; "IncludeUnconstrainingInDedup"
0x18000399f  lea     rcx, qword_18013EA50
0x1800039a6  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800039ab  nop
0x1800039ac  lea     rdx, aReturnfilters; "ReturnFilters"
0x1800039b3  lea     rcx, qword_18013EA70
0x1800039ba  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800039bf  nop
0x1800039c0  lea     rdx, aEnablespelling; "EnableSpellingCorrection"
0x1800039c7  lea     rcx, qword_18013EA90
0x1800039ce  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800039d3  nop
0x1800039d4  lea     rdx, aWordcompletion; "WordCompletionPenalty"
0x1800039db  lea     rcx, qword_18013EAB0
0x1800039e2  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800039e7  nop
0x1800039e8  lea     rdx, aMaxconvscore; "MaxConvScore"
0x1800039ef  lea     rcx, qword_18013EAD0
0x1800039f6  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800039fb  nop
0x1800039fc  lea     rdx, aAbsoluteprunin; "AbsolutePruningThreshold"
0x180003a03  lea     rcx, qword_18013EAF0
0x180003a0a  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180003a0f  nop
0x180003a10  lea     rdx, aRelativeprunin; "RelativePruningThreshold"
0x180003a17  lea     rcx, qword_18013EB10
0x180003a1e  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180003a23  nop
0x180003a24  lea     rdx, aMaxmatchcount; "MaxMatchCount"
0x180003a2b  lea     rcx, qword_18013EB30
0x180003a32  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180003a37  nop
0x180003a38  lea     rdx, aSubexpressione; "SubExpressionExpansionCount"
0x180003a3f  lea     rcx, qword_18013EB50
0x180003a46  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180003a4b  nop
0x180003a4c  lea     rdx, aCompletionenti; "CompletionEntityCount"
0x180003a53  lea     rcx, qword_18013EB70
0x180003a5a  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180003a5f  nop
0x180003a60  lea     rdx, aDefaultselectm; "DefaultSelectManyCount"
0x180003a67  lea     rcx, qword_18013EB90
0x180003a6e  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180003a73  nop
0x180003a74  lea     rdx, aMaxgrammardept; "MaxGrammarDepth"
0x180003a7b  lea     rcx, qword_18013EBB0
0x180003a82  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180003a87  nop
0x180003a88  lea     rdx, aMarket; "Market"
0x180003a8f  lea     rcx, qword_18013EBD0
0x180003a96  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180003a9b  nop
0x180003a9c  lea     rdx, aIme; "IME"
0x180003aa3  lea     rcx, qword_18013EBF0
0x180003aaa  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180003aaf  nop
0x180003ab0  lea     rdx, aSegment_0; "Segment"
0x180003ab7  lea     rcx, qword_18013EC10
0x180003abe  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180003ac3  nop
0x180003ac4  lea     rcx, _dynamic_atexit_destructor_for__DialogEngine__RequestPreference__preferenceNames__
0x180003acb  add     rsp, 28h
0x180003acf  jmp     atexit
```
