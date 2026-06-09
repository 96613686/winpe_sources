# LicenseManagerCore::Refresh(ContentIdString const &,Microsoft::WRL::ComPtr<ILicenseIdentityContext> const &,Microsoft::WRL::ComPtr<IKeyLicenseCallback> const &)

- ea: `0x180035c70`
- end: `0x180035f28`
- name: `?Refresh@LicenseManagerCore@@UEAAXAEBVContentIdString@@AEBV?$ComPtr@UILicenseIdentityContext@@@WRL@Microsoft@@AEBV?$ComPtr@UIKeyLicenseCallback@@@45@@Z`
- size: `696`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180096310`

## callees

- `0x180004738`
- `0x180013b50`
- `0x180035c70`
- `0x180035f30`
- `0x1800360f8`
- `0x180076e64`
- `0x18008a400`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180035d2f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180035e5f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180035d2f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180035e5f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180035d09`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180035d09`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180035df1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180035eeb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180035df1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180035eeb`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180035da1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180035da1`
- `ext-ms-win-core-licensemanager-l1-1-0!CompareContentId` at `0x180035d7e`
- `ext-ms-win-core-licensemanager-l1-1-0!CompareContentId` at `0x180035d7e`

## string_xrefs

- `0x180035e12`: `Refreshing content %s outside of KeyMachine`
- `0x180035e94`: `Found content %s running after updating outside of KeyMachine`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall LicenseManagerCore::Refresh(__int64 a1, __int64 *a2, __int64 a3, __int64 a4)
{
  __int64 v7; // rbx
  void (__fastcall *v8)(__int64, __int64, _QWORD *); // rdi
  __int64 v9; // rcx
  const char *v10; // r9
  __int64 v11; // rcx
  __int64 v12; // r12
  __int64 i; // rbx
  const WCHAR *v14; // r15
  __int64 v15; // r12
  __int64 v16; // r13
  char v17; // al
  const WCHAR *v18; // rcx
  int v19; // eax
  char v20; // r15
  __int64 v21; // rcx
  __int64 v22; // rbx
  __int64 *v23; // rax
  __int64 v24; // rbx
  __int64 *v25; // rcx
  __int64 v26; // rax
  HANDLE *v27; // rcx
  _QWORD v28[2]; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+38h]
  HANDLE *v30; // [rsp+80h] [rbp+40h] BYREF
  __int64 v31; // [rsp+90h] [rbp+50h]
  __int64 v32; // [rsp+98h] [rbp+58h]

  v32 = a4;
  v31 = a3;
  MakeCom<RootsCallback,>(&v30);
  v7 = *(_QWORD *)(a1 + 88);
  v8 = *(void (__fastcall **)(__int64, __int64, _QWORD *))(*(_QWORD *)v7 + 32LL);
  v28[0] = v30;
  if ( v30 )
    (*((void (__fastcall **)(HANDLE *))*v30 + 1))(v30);
  v8(v7, a3, v28);
  v9 = v28[0];
  if ( v28[0] )
  {
    v28[0] = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  }
  if ( WaitForSingleObject(v30[3], 0xFFFFFFFF) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0xC6,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\managercore.cpp",
      v10);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 48));
  v28[0] = a1 + 48;
  v12 = a1 + 120;
  for ( i = *(_QWORD *)(a1 + 120); i != *(_QWORD *)(v12 + 8); i += 48 )
  {
    if ( (unsigned __int64)a2[3] <= 7 )
      v14 = (const WCHAR *)a2;
    else
      v14 = (const WCHAR *)*a2;
    v15 = a2[2];
    v16 = *(_QWORD *)(i + 16);
    v17 = IsCompareContentIdPresent(v11);
    v18 = (const WCHAR *)i;
    if ( v17 )
    {
      if ( *(_QWORD *)(i + 24) > 7u )
        v18 = *(const WCHAR **)i;
      v19 = CompareContentId(v18, (unsigned int)v16, v14, (unsigned int)v15);
    }
    else
    {
      if ( *(_QWORD *)(i + 24) > 7u )
        v18 = *(const WCHAR **)i;
      v19 = CompareStringOrdinal(v18, v16, v14, v15, 1) - 2;
    }
    v12 = a1 + 120;
    if ( !v19 )
      goto LABEL_22;
  }
  i = *(_QWORD *)(v12 + 8);
LABEL_22:
  v20 = 0;
  if ( i == *(_QWORD *)(a1 + 128) )
  {
    v22 = v32;
  }
  else
  {
    v20 = 1;
    v21 = *(_QWORD *)(i + 40);
    v22 = v32;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v21 + 64LL))(v21, v32);
  }
  if ( a1 != -48 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 48));
  if ( !v20 )
  {
    v23 = a2;
    if ( (unsigned __int64)a2[3] > 7 )
      v23 = (__int64 *)*a2;
    LogMessage(
      3u,
      "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\managercore.cpp",
      0x343u,
      "LicenseManagerCore::Refresh",
      (wchar_t *)L"Refreshing content %s outside of KeyMachine",
      v23);
    (*(void (__fastcall **)(__int64, __int64 *, __int64, __int64))(*(_QWORD *)a1 + 184LL))(a1, a2, v31, v22);
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 48));
    v28[1] = a1 + 48;
    LicenseManagerCore::ContentIdMap<KeyEntry>::find(v12, v28, a2);
    v24 = v28[0];
    if ( v28[0] != *(_QWORD *)(a1 + 128) )
    {
      if ( (unsigned __int64)a2[3] > 7 )
        a2 = (__int64 *)*a2;
      LogMessage(
        3u,
        "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\managercore.cpp",
        0x34Fu,
        "LicenseManagerCore::Refresh",
        (wchar_t *)L"Found content %s running after updating outside of KeyMachine",
        a2);
      v25 = *(__int64 **)(v24 + 40);
      v26 = *v25;
      v28[0] = 0;
      (*(void (__fastcall **)(__int64 *, _QWORD *))(v26 + 64))(v25, v28);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v28);
    }
    if ( a1 != -48 )
      LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 48));
  }
  v27 = v30;
  if ( v30 )
  {
    v30 = 0;
    (*((void (__fastcall **)(HANDLE *))*v27 + 2))(v27);
  }
}

```

## disassembly

```asm
0x180035c70  mov     [rsp-38h+arg_8], rbx
0x180035c75  mov     [rsp-38h+arg_18], r9
0x180035c7a  mov     [rsp-38h+arg_10], r8
0x180035c7f  push    rbp
0x180035c80  push    rsi
0x180035c81  push    rdi
0x180035c82  push    r12
0x180035c84  push    r13
0x180035c86  push    r14
0x180035c88  push    r15
0x180035c8a  mov     rbp, rsp
0x180035c8d  sub     rsp, 40h
0x180035c91  mov     r13, r8
0x180035c94  mov     rsi, rdx
0x180035c97  mov     r14, rcx
0x180035c9a  lea     rcx, [rbp+arg_0]
0x180035c9e  call    ??$MakeCom@VRootsCallback@@$$V@@YA?AV?$ComPtr@VRootsCallback@@@WRL@Microsoft@@XZ; MakeCom<RootsCallback,>(void)
0x180035ca3  nop
0x180035ca4  mov     rbx, [r14+58h]
0x180035ca8  mov     rax, [rbx]
0x180035cab  mov     rdi, [rax+20h]
0x180035caf  mov     rcx, [rbp+arg_0]
0x180035cb3  mov     [rbp+var_10], rcx
0x180035cb7  test    rcx, rcx
0x180035cba  jz      short loc_180035CC9
0x180035cbc  mov     rax, [rcx]
0x180035cbf  mov     rax, [rax+8]
0x180035cc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035cc8  nop
0x180035cc9  lea     r8, [rbp+var_10]
0x180035ccd  mov     rdx, r13
0x180035cd0  mov     rcx, rbx
0x180035cd3  mov     rax, rdi
0x180035cd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035cdb  nop
0x180035cdc  mov     rcx, [rbp+var_10]
0x180035ce0  test    rcx, rcx
0x180035ce3  jz      short loc_180035CFA
0x180035ce5  mov     [rbp+var_10], 0
0x180035ced  mov     rax, [rcx]
0x180035cf0  mov     rax, [rax+10h]
0x180035cf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035cf9  nop
0x180035cfa  mov     rcx, [rbp+arg_0]
0x180035cfe  mov     rbx, [rbp+38h]
0x180035d02  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180035d05  mov     rcx, [rcx+18h]; hHandle
0x180035d09  call    cs:__imp_WaitForSingleObject
0x180035d0f  test    eax, eax
0x180035d11  jz      short loc_180035D28
0x180035d13  lea     r8, aOnecoreuapEndu_17; "onecoreuap\\enduser\\winstore\\licensem"...
0x180035d1a  mov     edx, 0C6h; void *
0x180035d1f  mov     rcx, rbx; this
0x180035d22  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180035d28  lea     rdi, [r14+30h]
0x180035d2c  mov     rcx, rdi; lpCriticalSection
0x180035d2f  call    cs:__imp_EnterCriticalSection
0x180035d35  mov     [rbp+var_10], rdi
0x180035d39  lea     r12, [r14+78h]
0x180035d3d  mov     rbx, [r12]
0x180035d41  cmp     rbx, [r12+8]
0x180035d46  jz      short loc_180035DB8
0x180035d48  cmp     qword ptr [rsi+18h], 7
0x180035d4d  jbe     short loc_180035D54
0x180035d4f  mov     r15, [rsi]
0x180035d52  jmp     short loc_180035D57
0x180035d54  mov     r15, rsi
0x180035d57  mov     r12, [rsi+10h]
0x180035d5b  mov     r13, [rbx+10h]
0x180035d5f  call    IsCompareContentIdPresent
0x180035d64  mov     rcx, rbx
0x180035d67  test    al, al
0x180035d69  jz      short loc_180035D86
0x180035d6b  cmp     qword ptr [rbx+18h], 7
0x180035d70  jbe     short loc_180035D75
0x180035d72  mov     rcx, [rbx]
0x180035d75  mov     r9d, r12d
0x180035d78  mov     edx, r13d
0x180035d7b  mov     r8, r15
0x180035d7e  call    cs:__imp_CompareContentId
0x180035d84  jmp     short loc_180035DAA
0x180035d86  cmp     qword ptr [rbx+18h], 7
0x180035d8b  jbe     short loc_180035D90
0x180035d8d  mov     rcx, [rbx]; lpString1
0x180035d90  mov     r9d, r12d; cchCount2
0x180035d93  mov     edx, r13d; cchCount1
0x180035d96  mov     [rsp+40h+bIgnoreCase], 1; bIgnoreCase
0x180035d9e  mov     r8, r15; lpString2
0x180035da1  call    cs:__imp_CompareStringOrdinal
0x180035da7  sub     eax, 2
0x180035daa  lea     r12, [r14+78h]
0x180035dae  test    eax, eax
0x180035db0  jz      short loc_180035DBD
0x180035db2  add     rbx, 30h ; '0'
0x180035db6  jmp     short loc_180035D41
0x180035db8  mov     rbx, [r12+8]
0x180035dbd  xor     r15b, r15b
0x180035dc0  cmp     rbx, [r14+80h]
0x180035dc7  jz      short loc_180035DE5
0x180035dc9  mov     r15b, 1
0x180035dcc  mov     rcx, [rbx+28h]
0x180035dd0  mov     rax, [rcx]
0x180035dd3  mov     rbx, [rbp+arg_18]
0x180035dd7  mov     rdx, rbx
0x180035dda  mov     rax, [rax+40h]
0x180035dde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035de3  jmp     short loc_180035DE9
0x180035de5  mov     rbx, [rbp+arg_18]
0x180035de9  test    rdi, rdi
0x180035dec  jz      short loc_180035DF7
0x180035dee  mov     rcx, rdi; lpCriticalSection
0x180035df1  call    cs:__imp_LeaveCriticalSection
0x180035df7  test    r15b, r15b
0x180035dfa  jnz     loc_180035EF2
0x180035e00  mov     rax, rsi
0x180035e03  cmp     qword ptr [rsi+18h], 7
0x180035e08  jbe     short loc_180035E0D
0x180035e0a  mov     rax, [rsi]
0x180035e0d  mov     [rsp+40h+var_18], rax
0x180035e12  lea     rax, aRefreshingCont; "Refreshing content %s outside of KeyMac"...
0x180035e19  mov     qword ptr [rsp+40h+bIgnoreCase], rax; Format
0x180035e1e  lea     r9, aLicensemanager_20; "LicenseManagerCore::Refresh"
0x180035e25  mov     r8d, 343h; unsigned int
0x180035e2b  lea     rdx, aOnecoreuapEndu_17; "onecoreuap\\enduser\\winstore\\licensem"...
0x180035e32  mov     r15d, 3
0x180035e38  mov     ecx, r15d; unsigned int
0x180035e3b  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x180035e40  mov     rax, [r14]
0x180035e43  mov     r9, rbx
0x180035e46  mov     r8, [rbp+arg_10]
0x180035e4a  mov     rdx, rsi
0x180035e4d  mov     rcx, r14
0x180035e50  mov     rax, [rax+0B8h]
0x180035e57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035e5c  mov     rcx, rdi; lpCriticalSection
0x180035e5f  call    cs:__imp_EnterCriticalSection
0x180035e65  mov     [rbp+var_8], rdi
0x180035e69  mov     r8, rsi
0x180035e6c  lea     rdx, [rbp+var_10]
0x180035e70  mov     rcx, r12
0x180035e73  call    ?find@?$ContentIdMap@UKeyEntry@@@LicenseManagerCore@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@U?$pair@VContentIdString@@UKeyEntry@@@std@@@std@@@std@@@std@@AEBVContentIdString@@@Z; LicenseManagerCore::ContentIdMap<KeyEntry>::find(ContentIdString const &)
0x180035e78  mov     rbx, [rbp+var_10]
0x180035e7c  cmp     rbx, [r14+80h]
0x180035e83  jz      short loc_180035EE3
0x180035e85  cmp     qword ptr [rsi+18h], 7
0x180035e8a  jbe     short loc_180035E8F
0x180035e8c  mov     rsi, [rsi]
0x180035e8f  mov     [rsp+40h+var_18], rsi
0x180035e94  lea     rax, aFoundContentSR; "Found content %s running after updating"...
0x180035e9b  mov     qword ptr [rsp+40h+bIgnoreCase], rax; Format
0x180035ea0  lea     r9, aLicensemanager_20; "LicenseManagerCore::Refresh"
0x180035ea7  mov     r8d, 34Fh; unsigned int
0x180035ead  lea     rdx, aOnecoreuapEndu_17; "onecoreuap\\enduser\\winstore\\licensem"...
0x180035eb4  mov     ecx, r15d; unsigned int
0x180035eb7  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x180035ebc  mov     rcx, [rbx+28h]
0x180035ec0  mov     rax, [rcx]
0x180035ec3  mov     [rbp+var_10], 0
0x180035ecb  lea     rdx, [rbp+var_10]
0x180035ecf  mov     rax, [rax+40h]
0x180035ed3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035ed8  nop
0x180035ed9  lea     rcx, [rbp+var_10]
0x180035edd  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180035ee2  nop
0x180035ee3  test    rdi, rdi
0x180035ee6  jz      short loc_180035EF2
0x180035ee8  mov     rcx, rdi; lpCriticalSection
0x180035eeb  call    cs:__imp_LeaveCriticalSection
0x180035ef1  nop
0x180035ef2  mov     rcx, [rbp+arg_0]
0x180035ef6  test    rcx, rcx
0x180035ef9  jz      short loc_180035F10
0x180035efb  mov     [rbp+arg_0], 0
0x180035f03  mov     rax, [rcx]
0x180035f06  mov     rax, [rax+10h]
0x180035f0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035f0f  nop
0x180035f10  mov     rbx, [rsp+40h+arg_8]
0x180035f18  add     rsp, 40h
0x180035f1c  pop     r15
0x180035f1e  pop     r14
0x180035f20  pop     r13
0x180035f22  pop     r12
0x180035f24  pop     rdi
0x180035f25  pop     rsi
0x180035f26  pop     rbp
0x180035f27  retn
```
