# SRUpdatePackageStatusForUserSid

- ea: `0x1800169e0`
- end: `0x180016b35`
- name: `SRUpdatePackageStatusForUserSid`
- size: `341`
- prototype: `__int64 __fastcall(PSID pSid)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180016920`

## callees

- `0x180002980`
- `0x1800075e4`
- `0x180008b4c`
- `0x18000956c`
- `0x180009cb0`
- `0x18000b30c`
- `0x18000b348`
- `0x180014c9c`
- `0x180016920`
- `0x1800169e0`
- `0x180027010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180016ad1`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180016ad1`

## pseudocode

```c
__int64 __fastcall SRUpdatePackageStatusForUserSid(PSID pSid, __int64 a2, int a3)
{
  int v6; // eax
  unsigned int v7; // ebx
  int v8; // eax
  __int64 v9; // rdx
  __int64 v10; // rsi
  __int64 (__fastcall *v11)(__int64, _QWORD, PSID, __int64); // rdi
  __int64 v12; // rbx
  DWORD LengthSid; // eax
  int v14; // [rsp+20h] [rbp-60h]
  int v15; // [rsp+40h] [rbp-40h] BYREF
  __int64 v16; // [rsp+48h] [rbp-38h] BYREF
  __int64 v17; // [rsp+50h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-28h] BYREF
  __int64 v19; // [rsp+70h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]

  v17 = a2;
  if ( !pSid )
    return SRUpdatePackageStatusForUserFromToken();
  v15 = -2147221008;
  v6 = Common::AutoWinRTInitialize::Initialize(&v15);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v16 = 0;
    v19 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Internal.StateRepository.PackageUserStatus",
      0x33u,
      0x32u);
    v8 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageUserStatusStatics>>(
           v19,
           (__int64)&v16);
    v7 = v8;
    if ( v8 >= 0 )
    {
      v10 = v16;
      v11 = *(__int64 (__fastcall **)(__int64, _QWORD, PSID, __int64))(*(_QWORD *)v16 + 112LL);
      v12 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v17) + 24);
      LengthSid = GetLengthSid(pSid);
      v14 = a3;
      v8 = v11(v10, LengthSid, pSid, v12);
      v7 = v8;
      if ( v8 >= 0 )
      {
        Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v16);
        v7 = 0;
        goto LABEL_11;
      }
      v9 = 201;
    }
    else
    {
      v9 = 198;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\apiset_status.cpp",
      (const char *)(unsigned int)v8,
      v14);
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v16);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC1,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\apiset_status.cpp",
      (const char *)(unsigned int)v6,
      v14);
  }
LABEL_11:
  Common::AutoWinRTInitialize::~AutoWinRTInitialize((Common::AutoWinRTInitialize *)&v15);
  return v7;
}

```

## disassembly

```asm
0x1800169e0  push    rbp
0x1800169e2  push    rbx
0x1800169e3  push    rsi
0x1800169e4  push    rdi
0x1800169e5  push    r12
0x1800169e7  push    r14
0x1800169e9  push    r15
0x1800169eb  mov     rbp, rsp
0x1800169ee  sub     rsp, 80h
0x1800169f5  mov     rax, cs:__security_cookie
0x1800169fc  xor     rax, rsp
0x1800169ff  mov     [rbp+var_8], rax
0x180016a03  mov     [rbp+var_30], rdx
0x180016a07  mov     r12d, r9d
0x180016a0a  mov     r15d, r8d
0x180016a0d  mov     r14, rcx
0x180016a10  test    rcx, rcx
0x180016a13  jnz     short loc_180016A1F
0x180016a15  call    SRUpdatePackageStatusForUserFromToken
0x180016a1a  jmp     loc_180016B17
0x180016a1f  lea     rcx, [rbp+var_40]
0x180016a23  mov     [rbp+var_40], 800401F0h
0x180016a2a  call    ?Initialize@AutoWinRTInitialize@Common@@QEAAJW4RO_INIT_TYPE@@@Z; Common::AutoWinRTInitialize::Initialize(RO_INIT_TYPE)
0x180016a2f  mov     ebx, eax
0x180016a31  test    eax, eax
0x180016a33  jns     short loc_180016A52
0x180016a35  mov     rcx, [rbp+38h]; this
0x180016a39  lea     r8, aOnecoreBaseApp_32; "onecore\\base\\appmodel\\staterepositor"...
0x180016a40  mov     r9d, eax; char *
0x180016a43  mov     edx, 0C1h; void *
0x180016a48  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016a4d  jmp     loc_180016B0C
0x180016a52  mov     r9d, 32h ; '2'; unsigned int
0x180016a58  mov     [rbp+var_38], 0
0x180016a60  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_PackageUserStatus@@3QBGB; "Windows.Internal.StateRepository.Packag"...
0x180016a67  mov     [rbp+var_10], 0
0x180016a6f  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x180016a73  lea     r8d, [r9+1]; unsigned int
0x180016a77  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180016a7c  mov     rcx, [rbp+var_10]
0x180016a80  lea     rdx, [rbp+var_38]
0x180016a84  call    ??$GetActivationFactory@V?$ComPtr@UIPackageUserStatusStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPackageUserStatusStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageUserStatusStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageUserStatusStatics>>)
0x180016a89  mov     ebx, eax
0x180016a8b  test    eax, eax
0x180016a8d  jns     short loc_180016AB2
0x180016a8f  mov     edx, 0C6h; void *
0x180016a94  mov     rcx, [rbp+38h]; this
0x180016a98  lea     r8, aOnecoreBaseApp_32; "onecore\\base\\appmodel\\staterepositor"...
0x180016a9f  mov     r9d, eax; char *
0x180016aa2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016aa7  lea     rcx, [rbp+var_38]
0x180016aab  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x180016ab0  jmp     short loc_180016B0C
0x180016ab2  mov     rsi, [rbp+var_38]
0x180016ab6  lea     rdx, [rbp+var_30]
0x180016aba  lea     rcx, [rbp+hstringHeader]
0x180016abe  mov     rax, [rsi]
0x180016ac1  mov     rdi, [rax+70h]
0x180016ac5  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180016aca  mov     rcx, r14; pSid
0x180016acd  mov     rbx, [rax+18h]
0x180016ad1  call    cs:__imp_GetLengthSid
0x180016ad7  mov     [rsp+80h+var_58], r12d
0x180016adc  mov     r9, rbx
0x180016adf  mov     edx, eax
0x180016ae1  mov     [rsp+80h+var_60], r15d
0x180016ae6  mov     rax, rdi
0x180016ae9  mov     r8, r14
0x180016aec  mov     rcx, rsi
0x180016aef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016af4  mov     ebx, eax
0x180016af6  test    eax, eax
0x180016af8  jns     short loc_180016B01
0x180016afa  mov     edx, 0C9h
0x180016aff  jmp     short loc_180016A94
0x180016b01  lea     rcx, [rbp+var_38]
0x180016b05  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x180016b0a  xor     ebx, ebx
0x180016b0c  lea     rcx, [rbp+var_40]; this
0x180016b10  call    ??1AutoWinRTInitialize@Common@@QEAA@XZ; Common::AutoWinRTInitialize::~AutoWinRTInitialize(void)
0x180016b15  mov     eax, ebx
0x180016b17  mov     rcx, [rbp+var_8]
0x180016b1b  xor     rcx, rsp; StackCookie
0x180016b1e  call    __security_check_cookie
0x180016b23  add     rsp, 80h
0x180016b2a  pop     r15
0x180016b2c  pop     r14
0x180016b2e  pop     r12
0x180016b30  pop     rdi
0x180016b31  pop     rsi
0x180016b32  pop     rbx
0x180016b33  pop     rbp
0x180016b34  retn
```
