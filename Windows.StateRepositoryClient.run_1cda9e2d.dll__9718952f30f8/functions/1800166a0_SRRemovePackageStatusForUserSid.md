# SRRemovePackageStatusForUserSid

- ea: `0x1800166a0`
- end: `0x1800167e8`
- name: `SRRemovePackageStatusForUserSid`
- size: `328`
- prototype: `__int64 __fastcall(PSID pSid)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800165e0`

## callees

- `0x180002980`
- `0x1800075e4`
- `0x180008b4c`
- `0x18000956c`
- `0x180009cb0`
- `0x18000b30c`
- `0x18000b348`
- `0x180014c9c`
- `0x1800165e0`
- `0x1800166a0`
- `0x180027010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001678b`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001678b`

## pseudocode

```c
__int64 __fastcall SRRemovePackageStatusForUserSid(PSID pSid, __int64 a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  int v6; // eax
  __int64 v7; // rdx
  __int64 v8; // rsi
  __int64 (__fastcall *v9)(__int64, _QWORD, PSID, __int64); // rdi
  __int64 v10; // rbx
  DWORD LengthSid; // eax
  int v12; // [rsp+20h] [rbp-50h]
  int v13; // [rsp+30h] [rbp-40h] BYREF
  __int64 v14; // [rsp+38h] [rbp-38h] BYREF
  __int64 v15; // [rsp+40h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-28h] BYREF
  __int64 v17; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  v15 = a2;
  if ( !pSid )
    return SRRemovePackageStatusForUserFromToken();
  v13 = -2147221008;
  v4 = Common::AutoWinRTInitialize::Initialize(&v13);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v14 = 0;
    v17 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Internal.StateRepository.PackageUserStatus",
      0x33u,
      0x32u);
    v6 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageUserStatusStatics>>(
           v17,
           &v14);
    v5 = v6;
    if ( v6 >= 0 )
    {
      v8 = v14;
      v9 = *(__int64 (__fastcall **)(__int64, _QWORD, PSID, __int64))(*(_QWORD *)v14 + 104LL);
      v10 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v15) + 24);
      LengthSid = GetLengthSid(pSid);
      v6 = v9(v8, LengthSid, pSid, v10);
      v5 = v6;
      if ( v6 >= 0 )
      {
        Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v14);
        v5 = 0;
        goto LABEL_11;
      }
      v7 = 148;
    }
    else
    {
      v7 = 145;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\apiset_status.cpp",
      (const char *)(unsigned int)v6,
      v12);
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v14);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8C,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\apiset_status.cpp",
      (const char *)(unsigned int)v4,
      v12);
  }
LABEL_11:
  Common::AutoWinRTInitialize::~AutoWinRTInitialize((Common::AutoWinRTInitialize *)&v13);
  return v5;
}

```

## disassembly

```asm
0x1800166a0  mov     [rsp-18h+arg_10], rbx
0x1800166a5  mov     [rsp-18h+arg_18], rsi
0x1800166aa  push    rbp
0x1800166ab  push    rdi
0x1800166ac  push    r14
0x1800166ae  mov     rbp, rsp
0x1800166b1  sub     rsp, 70h
0x1800166b5  mov     rax, cs:__security_cookie
0x1800166bc  xor     rax, rsp
0x1800166bf  mov     [rbp+var_8], rax
0x1800166c3  mov     [rbp+var_30], rdx
0x1800166c7  mov     r14, rcx
0x1800166ca  test    rcx, rcx
0x1800166cd  jnz     short loc_1800166D9
0x1800166cf  call    SRRemovePackageStatusForUserFromToken
0x1800166d4  jmp     loc_1800167C7
0x1800166d9  lea     rcx, [rbp+var_40]
0x1800166dd  mov     [rbp+var_40], 800401F0h
0x1800166e4  call    ?Initialize@AutoWinRTInitialize@Common@@QEAAJW4RO_INIT_TYPE@@@Z; Common::AutoWinRTInitialize::Initialize(RO_INIT_TYPE)
0x1800166e9  mov     ebx, eax
0x1800166eb  test    eax, eax
0x1800166ed  jns     short loc_18001670C
0x1800166ef  mov     rcx, [rbp+18h]; this
0x1800166f3  lea     r8, aOnecoreBaseApp_32; "onecore\\base\\appmodel\\staterepositor"...
0x1800166fa  mov     r9d, eax; char *
0x1800166fd  mov     edx, 8Ch; void *
0x180016702  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016707  jmp     loc_1800167BC
0x18001670c  mov     r9d, 32h ; '2'; unsigned int
0x180016712  mov     [rbp+var_38], 0
0x18001671a  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_PackageUserStatus@@3QBGB; "Windows.Internal.StateRepository.Packag"...
0x180016721  mov     [rbp+var_10], 0
0x180016729  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x18001672d  lea     r8d, [r9+1]; unsigned int
0x180016731  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180016736  mov     rcx, [rbp+var_10]
0x18001673a  lea     rdx, [rbp+var_38]
0x18001673e  call    ??$GetActivationFactory@V?$ComPtr@UIPackageUserStatusStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPackageUserStatusStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageUserStatusStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageUserStatusStatics>>)
0x180016743  mov     ebx, eax
0x180016745  test    eax, eax
0x180016747  jns     short loc_18001676C
0x180016749  mov     edx, 91h; void *
0x18001674e  mov     rcx, [rbp+18h]; this
0x180016752  lea     r8, aOnecoreBaseApp_32; "onecore\\base\\appmodel\\staterepositor"...
0x180016759  mov     r9d, eax; char *
0x18001675c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016761  lea     rcx, [rbp+var_38]
0x180016765  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x18001676a  jmp     short loc_1800167BC
0x18001676c  mov     rsi, [rbp+var_38]
0x180016770  lea     rdx, [rbp+var_30]
0x180016774  lea     rcx, [rbp+hstringHeader]
0x180016778  mov     rax, [rsi]
0x18001677b  mov     rdi, [rax+68h]
0x18001677f  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180016784  mov     rcx, r14; pSid
0x180016787  mov     rbx, [rax+18h]
0x18001678b  call    cs:__imp_GetLengthSid
0x180016791  mov     r9, rbx
0x180016794  mov     r8, r14
0x180016797  mov     edx, eax
0x180016799  mov     rcx, rsi
0x18001679c  mov     rax, rdi
0x18001679f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800167a4  mov     ebx, eax
0x1800167a6  test    eax, eax
0x1800167a8  jns     short loc_1800167B1
0x1800167aa  mov     edx, 94h
0x1800167af  jmp     short loc_18001674E
0x1800167b1  lea     rcx, [rbp+var_38]
0x1800167b5  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x1800167ba  xor     ebx, ebx
0x1800167bc  lea     rcx, [rbp+var_40]; this
0x1800167c0  call    ??1AutoWinRTInitialize@Common@@QEAA@XZ; Common::AutoWinRTInitialize::~AutoWinRTInitialize(void)
0x1800167c5  mov     eax, ebx
0x1800167c7  mov     rcx, [rbp+var_8]
0x1800167cb  xor     rcx, rsp; StackCookie
0x1800167ce  call    __security_check_cookie
0x1800167d3  lea     r11, [rsp+70h+var_s0]
0x1800167d8  mov     rbx, [r11+30h]
0x1800167dc  mov     rsi, [r11+38h]
0x1800167e0  mov     rsp, r11
0x1800167e3  pop     r14
0x1800167e5  pop     rdi
0x1800167e6  pop     rbp
0x1800167e7  retn
```
