# RtlCreateFilteringMicrodomWriter

- ea: `0x180053880`
- end: `0x18005398d`
- name: `RtlCreateFilteringMicrodomWriter`
- size: `269`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18001f4ac`
- `0x1800293a0`
- `0x180052dc8`
- `0x180053880`

## string_xrefs

- `0x1800538a2`: `onecore\base\xml\udom_editor.cpp`
- `0x1800538e2`: `onecore\base\xml\udom_editor.cpp`
- `0x180053927`: `onecore\base\xml\udom_editor.cpp`
- `0x1800538b5`: `RtlCreateFilteringMicrodomWriter`
- `0x1800538f9`: `RtlCreateFilteringMicrodomWriter`
- `0x18005393a`: `RtlCreateFilteringMicrodomWriter`
- `0x180053908`: `Not-null check failed: LowerWriter`

## pseudocode

```c
__int64 __fastcall RtlCreateFilteringMicrodomWriter(__int64 a1, const char *a2, _QWORD *a3, _QWORD *a4)
{
  const char *v4; // rax
  __int128 v6; // xmm0
  int v7; // eax
  unsigned int v8; // ecx
  struct Parameters v9; // [rsp+20h] [rbp-30h] BYREF
  const char *v10; // [rsp+28h] [rbp-28h]
  __int128 v11; // [rsp+30h] [rbp-20h]
  int v12; // [rsp+40h] [rbp-10h] BYREF

  v12 = 0;
  if ( (_DWORD)a1 )
  {
    *(_QWORD *)&v11 = 423;
    v9.lpVtbl = (struct ParametersVtbl *)"onecore\\base\\xml\\udom_editor.cpp";
    v10 = "RtlCreateFilteringMicrodomWriter";
    v4 = "Valid flags check failed: Flags";
LABEL_3:
    *((_QWORD *)&v11 + 1) = v4;
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
             &v12,
             &v9);
  }
  if ( a2 )
  {
    if ( a3[1] && !*a3 )
    {
      *(_QWORD *)&v11 = 425;
      v9.lpVtbl = (struct ParametersVtbl *)"onecore\\base\\xml\\udom_editor.cpp";
      v10 = "RtlCreateFilteringMicrodomWriter";
      v4 = "(NodesToIgnore.Length == 0) || (NodesToIgnore.Elements != 0)";
      goto LABEL_3;
    }
    v6 = *(_OWORD *)a3;
    v10 = a2;
    LODWORD(v9.lpVtbl) = 0;
    v11 = v6;
    v7 = Windows::Rtl::CRtlOneShotTypeDescriptionInit<MicrodomImplementation::CEditingDocumentFilter>::CreateInstance<MicrodomImplementation::CEditingDocumentFilter_IRtlMicrodomXmlWriter,MicrodomImplementation::CEditingDocumentFilter::Parameters,Windows::Microdom::Rtl::IRtlMicrodomXmlWriter>(
           a1,
           &v9,
           a4);
    v8 = 0;
    if ( v7 < 0 )
      return (unsigned int)v7;
    return v8;
  }
  else
  {
    *(_QWORD *)&v11 = 424;
    v9.lpVtbl = (struct ParametersVtbl *)"onecore\\base\\xml\\udom_editor.cpp";
    v10 = "RtlCreateFilteringMicrodomWriter";
    *((_QWORD *)&v11 + 1) = "Not-null check failed: LowerWriter";
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
             &v12,
             &v9);
  }
}

```

## disassembly

```asm
0x180053880  push    rbp
0x180053882  mov     rbp, rsp
0x180053885  sub     rsp, 50h
0x180053889  mov     rax, cs:__security_cookie
0x180053890  xor     rax, rsp
0x180053893  mov     [rbp+var_8], rax
0x180053897  mov     [rbp+var_10], 0
0x18005389e  test    ecx, ecx
0x1800538a0  jz      short loc_1800538DD
0x1800538a2  lea     rax, aOnecoreBaseXml_8; "onecore\\base\\xml\\udom_editor.cpp"
0x1800538a9  mov     qword ptr [rbp+var_20], 1A7h
0x1800538b1  mov     [rbp+var_30], rax
0x1800538b5  lea     rax, aRtlcreatefilte_0; "RtlCreateFilteringMicrodomWriter"
0x1800538bc  mov     [rbp+var_28], rax
0x1800538c0  lea     rax, aValidFlagsChec; "Valid flags check failed: Flags"
0x1800538c7  lea     rdx, [rbp+var_30]
0x1800538cb  mov     qword ptr [rbp+var_20+8], rax
0x1800538cf  lea     rcx, [rbp+var_10]
0x1800538d3  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x1800538d8  jmp     loc_18005397A
0x1800538dd  test    rdx, rdx
0x1800538e0  jnz     short loc_18005391A
0x1800538e2  lea     rax, aOnecoreBaseXml_8; "onecore\\base\\xml\\udom_editor.cpp"
0x1800538e9  mov     qword ptr [rbp+var_20], 1A8h
0x1800538f1  mov     [rbp+var_30], rax
0x1800538f5  lea     rdx, [rbp+var_30]
0x1800538f9  lea     rax, aRtlcreatefilte_0; "RtlCreateFilteringMicrodomWriter"
0x180053900  mov     [rbp+var_28], rax
0x180053904  lea     rcx, [rbp+var_10]
0x180053908  lea     rax, aNotNullCheckFa_4; "Not-null check failed: LowerWriter"
0x18005390f  mov     qword ptr [rbp+var_20+8], rax
0x180053913  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x180053918  jmp     short loc_18005397A
0x18005391a  cmp     qword ptr [r8+8], 0
0x18005391f  jz      short loc_180053951
0x180053921  cmp     qword ptr [r8], 0
0x180053925  jnz     short loc_180053951
0x180053927  lea     rax, aOnecoreBaseXml_8; "onecore\\base\\xml\\udom_editor.cpp"
0x18005392e  mov     qword ptr [rbp+var_20], 1A9h
0x180053936  mov     [rbp+var_30], rax
0x18005393a  lea     rax, aRtlcreatefilte_0; "RtlCreateFilteringMicrodomWriter"
0x180053941  mov     [rbp+var_28], rax
0x180053945  lea     rax, aNodestoignoreL; "(NodesToIgnore.Length == 0) || (NodesTo"...
0x18005394c  jmp     loc_1800538C7
0x180053951  movups  xmm0, xmmword ptr [r8]
0x180053955  mov     [rbp+var_28], rdx
0x180053959  mov     r8, r9
0x18005395c  lea     rdx, [rbp+var_30]
0x180053960  mov     dword ptr [rbp+var_30], 0
0x180053967  movdqu  [rbp+var_20], xmm0
0x18005396c  call    ??$CreateInstance@VCEditingDocumentFilter_IRtlMicrodomXmlWriter@MicrodomImplementation@@UParameters@CEditingDocumentFilter@2@UIRtlMicrodomXmlWriter@Rtl@Microdom@Windows@@@?$CRtlOneShotTypeDescriptionInit@VCEditingDocumentFilter@MicrodomImplementation@@@Rtl@Windows@@QEAAJAEBUParameters@CEditingDocumentFilter@MicrodomImplementation@@PEAV?$Auto@PEAUIRtlMicrodomXmlWriter@Rtl@Microdom@Windows@@@2@@Z; Windows::Rtl::CRtlOneShotTypeDescriptionInit<MicrodomImplementation::CEditingDocumentFilter>::CreateInstance<MicrodomImplementation::CEditingDocumentFilter_IRtlMicrodomXmlWriter,MicrodomImplementation::CEditingDocumentFilter::Parameters,Windows::Microdom::Rtl::IRtlMicrodomXmlWriter>(MicrodomImplementation::CEditingDocumentFilter::Parameters const &,Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodomXmlWriter *> *)
0x180053971  xor     ecx, ecx
0x180053973  test    eax, eax
0x180053975  cmovs   ecx, eax
0x180053978  mov     eax, ecx
0x18005397a  mov     rcx, [rbp+var_8]
0x18005397e  xor     rcx, rsp; StackCookie
0x180053981  call    __security_check_cookie
0x180053986  add     rsp, 50h
0x18005398a  pop     rbp
0x18005398b  retn
```
