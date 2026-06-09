# ScoobeEligibility::Details::TryGetScoobeIntentPropertyValue(ushort const *,ushort const *,ulong *)

- ea: `0x180016500`
- end: `0x1800166cf`
- name: `?TryGetScoobeIntentPropertyValue@Details@ScoobeEligibility@@YA_NPEBG0PEAK@Z`
- size: `463`
- prototype: `bool __fastcall(ScoobeEligibility::Details *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011538`

## callees

- `0x1800032b0`
- `0x18000e2bc`
- `0x18000ee5c`
- `0x180010958`
- `0x18001136c`
- `0x180012328`
- `0x180016500`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001657f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001657f`

## string_xrefs

- `0x180016590`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\scoobe\ScoobeEligibilityWithML.h`
- `0x180016646`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\scoobe\ScoobeEligibilityWithML.h`
- `0x18001667b`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\scoobe\ScoobeEligibilityWithML.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
char __fastcall ScoobeEligibility::Details::TryGetScoobeIntentPropertyValue(
        ScoobeEligibility::Details *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int *a4)
{
  int ActivationFactory; // eax
  int v6; // r8d
  const unsigned __int16 **v7; // rax
  const unsigned __int16 *v8; // rbx
  __int64 v9; // rcx
  int v10; // eax
  int v11; // eax
  char v12; // bl
  int v14; // [rsp+20h] [rbp-29h]
  int v15; // [rsp+20h] [rbp-29h]
  _BYTE v16[8]; // [rsp+30h] [rbp-19h] BYREF
  const unsigned __int16 *v17; // [rsp+38h] [rbp-11h] BYREF
  __int64 v18; // [rsp+40h] [rbp-9h] BYREF
  int v19[2]; // [rsp+48h] [rbp-1h] BYREF
  __int64 v20; // [rsp+50h] [rbp+7h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp+Fh] BYREF
  __int64 v22; // [rsp+70h] [rbp+27h]
  _BYTE v23[24]; // [rsp+78h] [rbp+2Fh] BYREF
  __int64 v24; // [rsp+90h] [rbp+47h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  *(_QWORD *)v19 = L"NumberOfConsecutivePostpones";
  v17 = L"IntroPostponed";
  *(_DWORD *)a3 = 0;
  v18 = 0;
  v22 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"CloudExperienceHostAPI.UserIntentRecordCore",
    0x2Cu,
    0x2Bu);
  ActivationFactory = RoGetActivationFactory(v22, &GUID_296a1a91_f065_4c6f_8b38_ae3a3a32fb0e, &v18);
  if ( ActivationFactory < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x26,
      (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\scoobe\\ScoobeEligibilityWithML.h",
      (const char *)(unsigned int)ActivationFactory,
      v14);
  *(_QWORD *)v19 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(v23, v19) + 24);
  v17 = *(const unsigned __int16 **)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v17)
                                   + 24);
  v7 = (const unsigned __int16 **)___call_and_wait_for_completion_UIUserIntentRecord_CloudExperienceHostAPI__PEAUHSTRING____PEAU3_PEAPEAU__IAsyncOperation_PEAVUserIntentRecordResult_CloudExperienceHostAPI___Foundation_Windows____ZPEAU3_PEAU3__wil__YA_A_PPEAUIUserIntentRecord_CloudExperienceHostAPI__P812_EAAJPEAUHSTRING____1PEAPEAU__IAsyncOperation_PEAVUserIntentRecordResult_CloudExperienceHostAPI___Foundation_Windows___Z__QEAPEAU3_4_Z(
                                    (unsigned int)&v20,
                                    v18,
                                    v6,
                                    (unsigned int)&v17,
                                    (__int64)v19);
  v8 = *v7;
  *v7 = 0;
  v17 = v8;
  v9 = v20;
  if ( v20 )
  {
    v20 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  }
  v22 = 0;
  v24 = 0;
  v16[0] = 0;
  v10 = (*(__int64 (__fastcall **)(const unsigned __int16 *, _BYTE *))(*(_QWORD *)v8 + 56LL))(v8, v16);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2D,
      (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\scoobe\\ScoobeEligibilityWithML.h",
      (const char *)(unsigned int)v10,
      v15);
  if ( !v16[0] )
    goto LABEL_12;
  v11 = (*(__int64 (__fastcall **)(const unsigned __int16 *, const unsigned __int16 *))(*(_QWORD *)v8 + 48LL))(v8, a3);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x30,
      (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\scoobe\\ScoobeEligibilityWithML.h",
      (const char *)(unsigned int)v11,
      v15);
  if ( v16[0] )
    v12 = 1;
  else
LABEL_12:
    v12 = 0;
  wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v17);
  wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v18);
  return v12;
}

```

## disassembly

```asm
0x180016500  mov     [rsp-8+arg_0], rbx
0x180016505  mov     [rsp-8+arg_8], rdi
0x18001650a  push    rbp
0x18001650b  lea     rbp, [rsp-57h]
0x180016510  sub     rsp, 0A0h
0x180016517  mov     rax, cs:__security_cookie
0x18001651e  xor     rax, rsp
0x180016521  mov     [rbp+57h+var_8], rax
0x180016525  mov     rdi, r8
0x180016528  lea     rax, aNumberofconsec; "NumberOfConsecutivePostpones"
0x18001652f  mov     qword ptr [rbp+57h+var_58], rax
0x180016533  lea     rax, aIntropostponed; "IntroPostponed"
0x18001653a  mov     [rbp+57h+var_68], rax
0x18001653e  mov     dword ptr [r8], 0
0x180016545  mov     [rbp+57h+var_60], 0
0x18001654d  mov     [rbp+57h+var_30], 0
0x180016555  mov     r9d, 2Bh ; '+'; unsigned int
0x18001655b  lea     r8d, [r9+1]; unsigned int
0x18001655f  lea     rdx, ?RuntimeClass_CloudExperienceHostAPI_UserIntentRecordCore@@3QBGB; "CloudExperienceHostAPI.UserIntentRecord"...
0x180016566  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18001656a  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001656f  nop
0x180016570  lea     r8, [rbp+57h+var_60]
0x180016574  lea     rdx, _GUID_296a1a91_f065_4c6f_8b38_ae3a3a32fb0e
0x18001657b  mov     rcx, [rbp+57h+var_30]
0x18001657f  call    cs:__imp_RoGetActivationFactory
0x180016585  mov     rcx, [rbp+5Fh]; this
0x180016589  test    eax, eax
0x18001658b  jns     short loc_1800165A2
0x18001658d  mov     r9d, eax; char *
0x180016590  lea     r8, aShellcommondes_0; "ShellCommonDesktopBase\\Internal\\Shell"...
0x180016597  mov     edx, 26h ; '&'; void *
0x18001659c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800165a2  lea     rdx, [rbp+57h+var_58]
0x1800165a6  lea     rcx, [rbp+57h+var_28]
0x1800165aa  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800165af  nop
0x1800165b0  mov     rax, [rax+18h]
0x1800165b4  mov     qword ptr [rbp+57h+var_58], rax
0x1800165b8  lea     rdx, [rbp+57h+var_68]
0x1800165bc  lea     rcx, [rbp+57h+hstringHeader]
0x1800165c0  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800165c5  nop
0x1800165c6  mov     rax, [rax+18h]
0x1800165ca  mov     [rbp+57h+var_68], rax
0x1800165ce  lea     rax, [rbp+57h+var_58]
0x1800165d2  mov     qword ptr [rsp+0A0h+var_80], rax; int
0x1800165d7  lea     r9, [rbp+57h+var_68]
0x1800165db  mov     rdx, [rbp+57h+var_60]
0x1800165df  lea     rcx, [rbp+57h+var_50]
0x1800165e3  call    ??$call_and_wait_for_completion@UIUserIntentRecord@CloudExperienceHostAPI@@PEAUHSTRING__@@PEAU3@PEAPEAU?$IAsyncOperation@PEAVUserIntentRecordResult@CloudExperienceHostAPI@@@Foundation@Windows@@$$ZPEAU3@PEAU3@@wil@@YA?A_PPEAUIUserIntentRecord@CloudExperienceHostAPI@@P812@EAAJPEAUHSTRING__@@1PEAPEAU?$IAsyncOperation@PEAVUserIntentRecordResult@CloudExperienceHostAPI@@@Foundation@Windows@@@Z$$QEAPEAU3@4@Z
0x1800165e8  mov     rbx, [rax]
0x1800165eb  mov     qword ptr [rax], 0
0x1800165f2  mov     [rbp+57h+var_68], rbx
0x1800165f6  mov     rcx, [rbp+57h+var_50]
0x1800165fa  test    rcx, rcx
0x1800165fd  jz      short loc_180016614
0x1800165ff  mov     [rbp+57h+var_50], 0
0x180016607  mov     rax, [rcx]
0x18001660a  mov     rax, [rax+10h]
0x18001660e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016613  nop
0x180016614  mov     [rbp+57h+var_30], 0
0x18001661c  mov     [rbp+57h+var_10], 0
0x180016624  mov     [rbp+57h+var_70], 0
0x180016628  mov     rax, [rbx]
0x18001662b  lea     rdx, [rbp+57h+var_70]
0x18001662f  mov     rcx, rbx
0x180016632  mov     rax, [rax+38h]
0x180016636  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001663b  mov     rcx, [rbp+5Fh]; this
0x18001663f  test    eax, eax
0x180016641  jns     short loc_180016658
0x180016643  mov     r9d, eax; char *
0x180016646  lea     r8, aShellcommondes_0; "ShellCommonDesktopBase\\Internal\\Shell"...
0x18001664d  mov     edx, 2Dh ; '-'; void *
0x180016652  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180016658  cmp     [rbp+57h+var_70], 0
0x18001665c  jz      short loc_180016697
0x18001665e  mov     rax, [rbx]
0x180016661  mov     rdx, rdi
0x180016664  mov     rcx, rbx
0x180016667  mov     rax, [rax+30h]
0x18001666b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016670  mov     rcx, [rbp+5Fh]; this
0x180016674  test    eax, eax
0x180016676  jns     short loc_18001668D
0x180016678  mov     r9d, eax; char *
0x18001667b  lea     r8, aShellcommondes_0; "ShellCommonDesktopBase\\Internal\\Shell"...
0x180016682  mov     edx, 30h ; '0'; void *
0x180016687  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001668d  cmp     [rbp+57h+var_70], 0
0x180016691  jz      short loc_180016697
0x180016693  mov     bl, 1
0x180016695  jmp     short loc_180016699
0x180016697  xor     bl, bl
0x180016699  lea     rcx, [rbp+57h+var_68]
0x18001669d  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x1800166a2  nop
0x1800166a3  lea     rcx, [rbp+57h+var_60]
0x1800166a7  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x1800166ac  mov     al, bl
0x1800166ae  mov     rcx, [rbp+57h+var_8]
0x1800166b2  xor     rcx, rsp; StackCookie
0x1800166b5  call    __security_check_cookie
0x1800166ba  lea     r11, [rsp+0A0h+var_s0]
0x1800166c2  mov     rbx, [r11+10h]
0x1800166c6  mov     rdi, [r11+18h]
0x1800166ca  mov     rsp, r11
0x1800166cd  pop     rbp
0x1800166ce  retn
```
