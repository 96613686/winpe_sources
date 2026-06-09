# LicenseManagerCore::ConnectRunningKey(ContentIdString const &,Microsoft::WRL::ComPtr<ILicenseIdentityContext> const &,Microsoft::WRL::ComPtr<IKeyLicenseCallback> const &)

- ea: `0x18003f240`
- end: `0x18003f511`
- name: `?ConnectRunningKey@LicenseManagerCore@@UEAA?AV?$ComPtr@UIKeyStateMachine@@@WRL@Microsoft@@AEBVContentIdString@@AEBV?$ComPtr@UILicenseIdentityContext@@@34@AEBV?$ComPtr@UIKeyLicenseCallback@@@34@@Z`
- size: `721`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180004738`
- `0x18001eac8`
- `0x18003f240`
- `0x1800593bc`
- `0x180076e64`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003f2c7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003f2c7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003f3c1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003f49a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003f3c1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003f49a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003f34f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003f34f`
- `ext-ms-win-core-licensemanager-l1-1-0!CompareContentId` at `0x18003f326`
- `ext-ms-win-core-licensemanager-l1-1-0!CompareContentId` at `0x18003f326`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 *__fastcall LicenseManagerCore::ConnectRunningKey(
        __int64 a1,
        __int64 *a2,
        __int64 a3,
        __int64 a4,
        __int64 **a5)
{
  __int64 v8; // rbx
  __int64 (__fastcall *v9)(__int64, GUID *, __int64 *); // rdi
  int v10; // eax
  __int64 v11; // rdi
  struct _RTL_CRITICAL_SECTION *v12; // r14
  __int64 v13; // rcx
  const WCHAR *i; // rbx
  const WCHAR *v15; // r13
  const WCHAR *v16; // rcx
  int v17; // eax
  const WCHAR *v18; // rcx
  __int64 *v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rcx
  __int64 v22; // rsi
  __int64 v23; // r15
  __int64 v24; // rsi
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rcx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-58h]
  __int64 v31; // [rsp+38h] [rbp-40h] BYREF
  __int64 v32; // [rsp+40h] [rbp-38h] BYREF
  int cchCount2[2]; // [rsp+48h] [rbp-30h] BYREF
  int cchCount1[2]; // [rsp+50h] [rbp-28h] BYREF
  __int64 v35; // [rsp+58h] [rbp-20h]
  __int64 v36; // [rsp+60h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+40h]

  MakeCom<LicenseManagerCore::KeyCoreWrapper,>(&v32);
  v31 = 0;
  v8 = v32;
  v9 = **(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v32;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v31);
  v10 = v9(v8, &GUID_cff16f1d_392c_47fa_95f4_c9d037df050c, &v31);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x470,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\managercore.cpp",
      (const char *)(unsigned int)v10,
      bIgnoreCase);
  v11 = 0;
  v35 = 0;
  v12 = (struct _RTL_CRITICAL_SECTION *)(a1 + 48);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 48));
  v36 = a1 + 48;
  for ( i = *(const WCHAR **)(a1 + 120); i != *(const WCHAR **)(a1 + 128); i += 24 )
  {
    if ( *(_QWORD *)(a3 + 24) <= 7u )
      v15 = (const WCHAR *)a3;
    else
      v15 = *(const WCHAR **)a3;
    *(_QWORD *)cchCount2 = *(_QWORD *)(a3 + 16);
    *(_QWORD *)cchCount1 = *((_QWORD *)i + 2);
    if ( (unsigned __int8)IsCompareContentIdPresent(v13) )
    {
      if ( *((_QWORD *)i + 3) <= 7u )
        v16 = i;
      else
        v16 = *(const WCHAR **)i;
      v17 = CompareContentId(v16, (unsigned int)cchCount1[0], v15, (unsigned int)cchCount2[0]);
    }
    else
    {
      if ( *((_QWORD *)i + 3) <= 7u )
        v18 = i;
      else
        v18 = *(const WCHAR **)i;
      v17 = CompareStringOrdinal(v18, cchCount1[0], v15, cchCount2[0], 1) - 2;
    }
    if ( !v17 )
      goto LABEL_20;
  }
  i = *(const WCHAR **)(a1 + 128);
LABEL_20:
  if ( i == *(const WCHAR **)(a1 + 128) )
  {
    v19 = *a5;
    if ( *a5 )
    {
      v20 = *v19;
      *(_QWORD *)cchCount2 = 0;
      *(_QWORD *)cchCount1 = 0;
      (*(void (__fastcall **)(__int64 *, __int64, int *, int *))(v20 + 24))(v19, 1, cchCount1, cchCount2);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(cchCount1);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(cchCount2);
    }
    *a2 = 0;
    if ( a1 != -48 )
      LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 48));
    v21 = v31;
    if ( v31 )
    {
      v31 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    }
  }
  else
  {
    v22 = *((_QWORD *)i + 5);
    if ( v22 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 8LL))(*((_QWORD *)i + 5));
      v11 = v22;
      v35 = v22;
    }
    (*(void (__fastcall **)(__int64, __int64, __int64 **))(*(_QWORD *)v11 + 48LL))(v11, a4, a5);
    v23 = a1 - 16;
    v24 = v32;
    if ( *(_QWORD *)(v32 + 24) != v23 )
    {
      if ( v23 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 8LL))(v23);
      v25 = *(_QWORD *)(v24 + 24);
      *(_QWORD *)(v24 + 24) = v23;
      if ( v25 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
      v24 = v32;
    }
    if ( *(_QWORD *)(v24 + 16) != v11 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
      v26 = *(_QWORD *)(v24 + 16);
      *(_QWORD *)(v24 + 16) = v11;
      if ( v26 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    }
    ++*((_DWORD *)i + 8);
    if ( v12 )
      LeaveCriticalSection(v12);
    *a2 = 0;
    if ( a2 != &v31 )
    {
      *a2 = v31;
      v31 = 0;
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    v27 = v31;
    if ( v31 )
    {
      v31 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    }
  }
  v28 = v32;
  if ( v32 )
  {
    v32 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
  }
  return a2;
}

```

## disassembly

```asm
0x18003f240  mov     [rsp-40h+arg_18], r9
0x18003f245  push    rbp
0x18003f246  push    rbx
0x18003f247  push    rsi
0x18003f248  push    rdi
0x18003f249  push    r12
0x18003f24b  push    r13
0x18003f24d  push    r14
0x18003f24f  push    r15
0x18003f251  mov     rbp, rsp
0x18003f254  sub     rsp, 78h
0x18003f258  mov     rsi, r8
0x18003f25b  mov     r12, rdx
0x18003f25e  mov     r15, rcx
0x18003f261  xor     r13d, r13d
0x18003f264  lea     rcx, [rbp+var_38]
0x18003f268  call    ??$MakeCom@VKeyCoreWrapper@LicenseManagerCore@@$$V@@YA?AV?$ComPtr@VKeyCoreWrapper@LicenseManagerCore@@@WRL@Microsoft@@XZ; MakeCom<LicenseManagerCore::KeyCoreWrapper,>(void)
0x18003f26d  nop
0x18003f26e  mov     [rbp+var_40], r13
0x18003f272  mov     rbx, [rbp+var_38]
0x18003f276  mov     rax, [rbx]
0x18003f279  mov     rdi, [rax]
0x18003f27c  lea     rcx, [rbp+var_40]
0x18003f280  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18003f285  lea     r8, [rbp+var_40]
0x18003f289  lea     rdx, _GUID_cff16f1d_392c_47fa_95f4_c9d037df050c
0x18003f290  mov     rcx, rbx
0x18003f293  mov     rax, rdi
0x18003f296  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f29b  nop
0x18003f29c  mov     rcx, [rbp+40h]; this
0x18003f2a0  test    eax, eax
0x18003f2a2  jns     short loc_18003F2B9
0x18003f2a4  mov     r9d, eax; char *
0x18003f2a7  lea     r8, aOnecoreuapEndu_17; "onecoreuap\\enduser\\winstore\\licensem"...
0x18003f2ae  mov     edx, 470h; void *
0x18003f2b3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003f2b9  mov     rdi, r13
0x18003f2bc  mov     [rbp+var_20], r13
0x18003f2c0  lea     r14, [r15+30h]
0x18003f2c4  mov     rcx, r14; lpCriticalSection
0x18003f2c7  call    cs:__imp_EnterCriticalSection
0x18003f2cd  mov     [rbp+var_18], r14
0x18003f2d1  mov     rbx, [r15+78h]
0x18003f2d5  mov     rax, [r15+80h]
0x18003f2dc  cmp     rbx, rax
0x18003f2df  jz      loc_18003F368
0x18003f2e5  cmp     qword ptr [rsi+18h], 7
0x18003f2ea  jbe     short loc_18003F2F1
0x18003f2ec  mov     r13, [rsi]
0x18003f2ef  jmp     short loc_18003F2F4
0x18003f2f1  mov     r13, rsi
0x18003f2f4  mov     rax, [rsi+10h]
0x18003f2f8  mov     qword ptr [rbp+cchCount2], rax
0x18003f2fc  mov     rax, [rbx+10h]
0x18003f300  mov     qword ptr [rbp+cchCount1], rax
0x18003f304  call    IsCompareContentIdPresent
0x18003f309  test    al, al
0x18003f30b  jz      short loc_18003F32E
0x18003f30d  cmp     qword ptr [rbx+18h], 7
0x18003f312  jbe     short loc_18003F319
0x18003f314  mov     rcx, [rbx]
0x18003f317  jmp     short loc_18003F31C
0x18003f319  mov     rcx, rbx
0x18003f31c  mov     r9d, [rbp+cchCount2]
0x18003f320  mov     edx, [rbp+cchCount1]
0x18003f323  mov     r8, r13
0x18003f326  call    cs:__imp_CompareContentId
0x18003f32c  jmp     short loc_18003F358
0x18003f32e  cmp     qword ptr [rbx+18h], 7
0x18003f333  jbe     short loc_18003F33A
0x18003f335  mov     rcx, [rbx]
0x18003f338  jmp     short loc_18003F33D
0x18003f33a  mov     rcx, rbx; lpString1
0x18003f33d  mov     r9d, [rbp+cchCount2]; cchCount2
0x18003f341  mov     edx, [rbp+cchCount1]; cchCount1
0x18003f344  mov     [rsp+78h+bIgnoreCase], 1; bIgnoreCase
0x18003f34c  mov     r8, r13; lpString2
0x18003f34f  call    cs:__imp_CompareStringOrdinal
0x18003f355  sub     eax, 2
0x18003f358  xor     r13d, r13d
0x18003f35b  test    eax, eax
0x18003f35d  jz      short loc_18003F36B
0x18003f35f  add     rbx, 30h ; '0'
0x18003f363  jmp     loc_18003F2D5
0x18003f368  mov     rbx, rax
0x18003f36b  cmp     rbx, [r15+80h]
0x18003f372  jnz     short loc_18003F3E7
0x18003f374  mov     rax, [rbp+arg_20]
0x18003f378  mov     rcx, [rax]
0x18003f37b  test    rcx, rcx
0x18003f37e  jz      short loc_18003F3B5
0x18003f380  mov     rax, [rcx]
0x18003f383  mov     qword ptr [rbp+cchCount2], r13
0x18003f387  mov     qword ptr [rbp+cchCount1], r13
0x18003f38b  lea     r9, [rbp+cchCount2]
0x18003f38f  lea     r8, [rbp+cchCount1]
0x18003f393  mov     edx, 1
0x18003f398  mov     rax, [rax+18h]
0x18003f39c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f3a1  nop
0x18003f3a2  lea     rcx, [rbp+cchCount1]
0x18003f3a6  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18003f3ab  nop
0x18003f3ac  lea     rcx, [rbp+cchCount2]
0x18003f3b0  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18003f3b5  mov     [r12], r13
0x18003f3b9  test    r14, r14
0x18003f3bc  jz      short loc_18003F3C8
0x18003f3be  mov     rcx, r14; lpCriticalSection
0x18003f3c1  call    cs:__imp_LeaveCriticalSection
0x18003f3c7  nop
0x18003f3c8  mov     rcx, [rbp+var_40]
0x18003f3cc  test    rcx, rcx
0x18003f3cf  jz      short loc_18003F3E2
0x18003f3d1  mov     [rbp+var_40], r13
0x18003f3d5  mov     rax, [rcx]
0x18003f3d8  mov     rax, [rax+10h]
0x18003f3dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f3e1  nop
0x18003f3e2  jmp     loc_18003F4E3
0x18003f3e7  mov     rsi, [rbx+28h]
0x18003f3eb  test    rsi, rsi
0x18003f3ee  jz      short loc_18003F407
0x18003f3f0  mov     rax, [rsi]
0x18003f3f3  mov     rcx, rsi
0x18003f3f6  mov     rax, [rax+8]
0x18003f3fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f3ff  nop
0x18003f400  mov     rdi, rsi
0x18003f403  mov     [rbp+var_20], rsi
0x18003f407  mov     rax, [rdi]
0x18003f40a  mov     r8, [rbp+arg_20]
0x18003f40e  mov     rdx, [rbp+arg_18]
0x18003f412  mov     rcx, rdi
0x18003f415  mov     rax, [rax+30h]
0x18003f419  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f41e  add     r15, 0FFFFFFFFFFFFFFF0h
0x18003f422  mov     rsi, [rbp+var_38]
0x18003f426  cmp     [rsi+18h], r15
0x18003f42a  jz      short loc_18003F45F
0x18003f42c  test    r15, r15
0x18003f42f  jz      short loc_18003F441
0x18003f431  mov     rax, [r15]
0x18003f434  mov     rcx, r15
0x18003f437  mov     rax, [rax+8]
0x18003f43b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f440  nop
0x18003f441  mov     rcx, [rsi+18h]
0x18003f445  mov     [rsi+18h], r15
0x18003f449  test    rcx, rcx
0x18003f44c  jz      short loc_18003F45B
0x18003f44e  mov     rax, [rcx]
0x18003f451  mov     rax, [rax+10h]
0x18003f455  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f45a  nop
0x18003f45b  mov     rsi, [rbp+var_38]
0x18003f45f  cmp     [rsi+10h], rdi
0x18003f463  jz      short loc_18003F48F
0x18003f465  mov     rax, [rdi]
0x18003f468  mov     rcx, rdi
0x18003f46b  mov     rax, [rax+8]
0x18003f46f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f474  nop
0x18003f475  mov     rcx, [rsi+10h]
0x18003f479  mov     [rsi+10h], rdi
0x18003f47d  test    rcx, rcx
0x18003f480  jz      short loc_18003F48F
0x18003f482  mov     rax, [rcx]
0x18003f485  mov     rax, [rax+10h]
0x18003f489  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f48e  nop
0x18003f48f  inc     dword ptr [rbx+20h]
0x18003f492  test    r14, r14
0x18003f495  jz      short loc_18003F4A0
0x18003f497  mov     rcx, r14; lpCriticalSection
0x18003f49a  call    cs:__imp_LeaveCriticalSection
0x18003f4a0  mov     [r12], r13
0x18003f4a4  lea     rax, [rbp+var_40]
0x18003f4a8  cmp     r12, rax
0x18003f4ab  jz      short loc_18003F4B9
0x18003f4ad  mov     rax, [rbp+var_40]
0x18003f4b1  mov     [r12], rax
0x18003f4b5  mov     [rbp+var_40], r13
0x18003f4b9  mov     rax, [rdi]
0x18003f4bc  mov     rcx, rdi
0x18003f4bf  mov     rax, [rax+10h]
0x18003f4c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f4c8  nop
0x18003f4c9  mov     rcx, [rbp+var_40]
0x18003f4cd  test    rcx, rcx
0x18003f4d0  jz      short loc_18003F4E3
0x18003f4d2  mov     [rbp+var_40], r13
0x18003f4d6  mov     rax, [rcx]
0x18003f4d9  mov     rax, [rax+10h]
0x18003f4dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f4e2  nop
0x18003f4e3  mov     rcx, [rbp+var_38]
0x18003f4e7  test    rcx, rcx
0x18003f4ea  jz      short loc_18003F4FD
0x18003f4ec  mov     [rbp+var_38], r13
0x18003f4f0  mov     rax, [rcx]
0x18003f4f3  mov     rax, [rax+10h]
0x18003f4f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f4fc  nop
0x18003f4fd  mov     rax, r12
0x18003f500  add     rsp, 78h
0x18003f504  pop     r15
0x18003f506  pop     r14
0x18003f508  pop     r13
0x18003f50a  pop     r12
0x18003f50c  pop     rdi
0x18003f50d  pop     rsi
0x18003f50e  pop     rbx
0x18003f50f  pop     rbp
0x18003f510  retn
```
