# RtlCreateFilteringMicrodomWriter

- ea: `0x180056000`
- end: `0x18005613f`
- name: `RtlCreateFilteringMicrodomWriter`
- size: `319`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18001f1d8`
- `0x18002d2b0`
- `0x180055630`
- `0x180055ae0`
- `0x180056000`

## import_xrefs

- `ntdll!RtlRaiseStatus` at `0x180056105`
- `ntdll!RtlRaiseStatus` at `0x180056105`

## string_xrefs

- `0x180056026`: `onecore\base\xml\udom_editor.cpp`
- `0x180056066`: `onecore\base\xml\udom_editor.cpp`
- `0x1800560ae`: `onecore\base\xml\udom_editor.cpp`
- `0x180056039`: `RtlCreateFilteringMicrodomWriter`
- `0x18005607d`: `RtlCreateFilteringMicrodomWriter`
- `0x1800560c1`: `RtlCreateFilteringMicrodomWriter`
- `0x18005608c`: `Not-null check failed: LowerWriter`

## pseudocode

```c
__int64 __fastcall RtlCreateFilteringMicrodomWriter(__int64 a1, const char *a2, _QWORD *a3, __int64 a4)
{
  const char *v5; // rax
  __int64 result; // rax
  __int128 v7; // xmm0
  const char *v8; // [rsp+20h] [rbp-38h] BYREF
  const char *v9; // [rsp+28h] [rbp-30h]
  __int128 v10; // [rsp+30h] [rbp-28h]
  int v11; // [rsp+40h] [rbp-18h] BYREF

  v11 = 0;
  if ( (_DWORD)a1 )
  {
    *(_QWORD *)&v10 = 423;
    v8 = "onecore\\base\\xml\\udom_editor.cpp";
    v9 = "RtlCreateFilteringMicrodomWriter";
    v5 = "Valid flags check failed: Flags";
LABEL_3:
    *((_QWORD *)&v10 + 1) = v5;
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
             &v11,
             &v8);
  }
  if ( a2 )
  {
    if ( a3[1] && !*a3 )
    {
      *(_QWORD *)&v10 = 425;
      v8 = "onecore\\base\\xml\\udom_editor.cpp";
      v9 = "RtlCreateFilteringMicrodomWriter";
      v5 = "(NodesToIgnore.Length == 0) || (NodesToIgnore.Elements != 0)";
      goto LABEL_3;
    }
    v7 = *(_OWORD *)a3;
    v9 = a2;
    v10 = v7;
    result = Windows::Rtl::CRtlOneShotTypeDescriptionInit<MicrodomImplementation::CEditingDocumentFilter>::Initialize(
               a1,
               a2,
               a3,
               a4,
               0);
    if ( (int)result >= 0 )
    {
      if ( dword_1800D2AF8 != 2 )
        RtlRaiseStatus(-1073741595);
      result = Windows::Rtl::CRtlObjectTypeDescription<MicrodomImplementation::CEditingDocumentFilter>::CreateInstance<MicrodomImplementation::CEditingDocumentFilter_IRtlMicrodomXmlWriter,MicrodomImplementation::CEditingDocumentFilter::Parameters,Windows::Microdom::Rtl::IRtlMicrodomXmlWriter>(
                 MicrodomImplementation::g_OneShotFilterCreator,
                 &v8,
                 a4);
      if ( (int)result >= 0 )
        return 0;
    }
  }
  else
  {
    *(_QWORD *)&v10 = 424;
    v8 = "onecore\\base\\xml\\udom_editor.cpp";
    v9 = "RtlCreateFilteringMicrodomWriter";
    *((_QWORD *)&v10 + 1) = "Not-null check failed: LowerWriter";
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
             &v11,
             &v8);
  }
  return result;
}

```

## disassembly

```asm
0x180056000  push    rbp
0x180056002  push    rbx
0x180056003  mov     rbp, rsp
0x180056006  sub     rsp, 58h
0x18005600a  mov     rax, cs:__security_cookie
0x180056011  xor     rax, rsp
0x180056014  mov     [rbp+var_10], rax
0x180056018  mov     [rbp+var_18], 0
0x18005601f  mov     rbx, r9
0x180056022  test    ecx, ecx
0x180056024  jz      short loc_180056061
0x180056026  lea     rax, aOnecoreBaseXml_8; "onecore\\base\\xml\\udom_editor.cpp"
0x18005602d  mov     qword ptr [rbp+var_28], 1A7h
0x180056035  mov     [rbp+var_38], rax
0x180056039  lea     rax, aRtlcreatefilte_0; "RtlCreateFilteringMicrodomWriter"
0x180056040  mov     [rbp+var_30], rax
0x180056044  lea     rax, aValidFlagsChec; "Valid flags check failed: Flags"
0x18005604b  lea     rdx, [rbp+var_38]
0x18005604f  mov     qword ptr [rbp+var_28+8], rax
0x180056053  lea     rcx, [rbp+var_18]
0x180056057  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18005605c  jmp     loc_18005612B
0x180056061  test    rdx, rdx
0x180056064  jnz     short loc_1800560A1
0x180056066  lea     rax, aOnecoreBaseXml_8; "onecore\\base\\xml\\udom_editor.cpp"
0x18005606d  mov     qword ptr [rbp+var_28], 1A8h
0x180056075  mov     [rbp+var_38], rax
0x180056079  lea     rdx, [rbp+var_38]
0x18005607d  lea     rax, aRtlcreatefilte_0; "RtlCreateFilteringMicrodomWriter"
0x180056084  mov     [rbp+var_30], rax
0x180056088  lea     rcx, [rbp+var_18]
0x18005608c  lea     rax, aNotNullCheckFa_4; "Not-null check failed: LowerWriter"
0x180056093  mov     qword ptr [rbp+var_28+8], rax
0x180056097  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18005609c  jmp     loc_18005612B
0x1800560a1  cmp     qword ptr [r8+8], 0
0x1800560a6  jz      short loc_1800560D8
0x1800560a8  cmp     qword ptr [r8], 0
0x1800560ac  jnz     short loc_1800560D8
0x1800560ae  lea     rax, aOnecoreBaseXml_8; "onecore\\base\\xml\\udom_editor.cpp"
0x1800560b5  mov     qword ptr [rbp+var_28], 1A9h
0x1800560bd  mov     [rbp+var_38], rax
0x1800560c1  lea     rax, aRtlcreatefilte_0; "RtlCreateFilteringMicrodomWriter"
0x1800560c8  mov     [rbp+var_30], rax
0x1800560cc  lea     rax, aNodestoignoreL; "(NodesToIgnore.Length == 0) || (NodesTo"...
0x1800560d3  jmp     loc_18005604B
0x1800560d8  movups  xmm0, xmmword ptr [r8]
0x1800560dc  mov     dword ptr [rbp+var_38], 0
0x1800560e3  mov     [rbp+var_30], rdx
0x1800560e7  movdqu  [rbp+var_28], xmm0
0x1800560ec  call    ?Initialize@?$CRtlOneShotTypeDescriptionInit@VCEditingDocumentFilter@MicrodomImplementation@@@Rtl@Windows@@QEAAJXZ; Windows::Rtl::CRtlOneShotTypeDescriptionInit<MicrodomImplementation::CEditingDocumentFilter>::Initialize(void)
0x1800560f1  test    eax, eax
0x1800560f3  js      short loc_18005612B
0x1800560f5  mov     eax, cs:dword_1800D2AF8
0x1800560fb  cmp     eax, 2
0x1800560fe  jz      short loc_180056112
0x180056100  mov     ecx, 0C00000E5h; Status
0x180056105  call    cs:__imp_RtlRaiseStatus
0x18005610c  nop     dword ptr [rax+rax+00h]
0x180056111  int     3; Trap to Debugger
0x180056112  mov     rcx, cs:?g_OneShotFilterCreator@MicrodomImplementation@@3V?$CRtlOneShotTypeDescriptionInit@VCEditingDocumentFilter@MicrodomImplementation@@@Rtl@Windows@@A; Windows::Rtl::CRtlOneShotTypeDescriptionInit<MicrodomImplementation::CEditingDocumentFilter> MicrodomImplementation::g_OneShotFilterCreator
0x180056119  lea     rdx, [rbp+var_38]
0x18005611d  mov     r8, rbx
0x180056120  call    ??$CreateInstance@VCEditingDocumentFilter_IRtlMicrodomXmlWriter@MicrodomImplementation@@UParameters@CEditingDocumentFilter@2@UIRtlMicrodomXmlWriter@Rtl@Microdom@Windows@@@?$CRtlObjectTypeDescription@VCEditingDocumentFilter@MicrodomImplementation@@@Rtl@Windows@@QEAAJAEBUParameters@CEditingDocumentFilter@MicrodomImplementation@@PEAV?$Auto@PEAUIRtlMicrodomXmlWriter@Rtl@Microdom@Windows@@@2@@Z; Windows::Rtl::CRtlObjectTypeDescription<MicrodomImplementation::CEditingDocumentFilter>::CreateInstance<MicrodomImplementation::CEditingDocumentFilter_IRtlMicrodomXmlWriter,MicrodomImplementation::CEditingDocumentFilter::Parameters,Windows::Microdom::Rtl::IRtlMicrodomXmlWriter>(MicrodomImplementation::CEditingDocumentFilter::Parameters const &,Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodomXmlWriter *> *)
0x180056125  test    eax, eax
0x180056127  js      short loc_18005612B
0x180056129  xor     eax, eax
0x18005612b  mov     rcx, [rbp+var_10]
0x18005612f  xor     rcx, rsp; StackCookie
0x180056132  call    __security_check_cookie
0x180056137  add     rsp, 58h
0x18005613b  pop     rbx
0x18005613c  pop     rbp
0x18005613d  retn
```
