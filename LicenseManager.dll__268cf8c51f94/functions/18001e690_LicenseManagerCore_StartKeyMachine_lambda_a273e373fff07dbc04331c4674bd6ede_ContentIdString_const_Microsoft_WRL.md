# LicenseManagerCore::StartKeyMachine<_lambda_a273e373fff07dbc04331c4674bd6ede_>(ContentIdString const &,Microsoft::WRL::ComPtr<ILicenseIdentityContext> const &,_lambda_a273e373fff07dbc04331c4674bd6ede_ &&)

- ea: `0x18001e690`
- end: `0x18001eac1`
- name: `??$StartKeyMachine@V_lambda_a273e373fff07dbc04331c4674bd6ede_@@@LicenseManagerCore@@QEAA?AV?$ComPtr@UIKeyStateMachine@@@WRL@Microsoft@@AEBVContentIdString@@AEBV?$ComPtr@UILicenseIdentityContext@@@23@$$QEAV_lambda_a273e373fff07dbc04331c4674bd6ede_@@@Z`
- size: `1073`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x18001e640`

## callees

- `0x180004738`
- `0x180012dc0`
- `0x18001e690`
- `0x18001eac8`
- `0x18001ec28`
- `0x18001f2d4`
- `0x18001f5ac`
- `0x18001fd40`
- `0x18004301c`
- `0x180044054`
- `0x1800445b4`
- `0x1800593bc`
- `0x180075e60`
- `0x180076e64`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e770`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e770`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e947`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e947`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001e7d5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001e7d5`
- `ext-ms-win-core-licensemanager-l1-1-0!CompareContentId` at `0x18001ea65`
- `ext-ms-win-core-licensemanager-l1-1-0!CompareContentId` at `0x18001ea65`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
_QWORD *__fastcall LicenseManagerCore::StartKeyMachine<_lambda_a273e373fff07dbc04331c4674bd6ede_>(
        __int64 a1,
        _QWORD *a2,
        const WCHAR *a3,
        __int64 a4,
        unsigned int **a5)
{
  __int64 *v8; // rcx
  __int64 v9; // rax
  __int64 v10; // rcx
  __int64 v11; // rbx
  __int64 (__fastcall *v12)(__int64, GUID *, _QWORD *); // rdi
  int v13; // eax
  __int64 v14; // rsi
  __int64 v15; // rcx
  __int64 i; // rbx
  const WCHAR *v17; // rdi
  __int64 v18; // r15
  const WCHAR *v19; // rcx
  int v20; // eax
  char *v21; // rcx
  __int64 v22; // rax
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rdi
  __int64 v26; // rdi
  __int64 v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rcx
  __int64 v31; // rdi
  __int64 v32; // r15
  const WCHAR *v33; // rcx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-E0h]
  int cchCount1[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v36; // [rsp+38h] [rbp-C8h] BYREF
  int v37; // [rsp+40h] [rbp-C0h]
  __int64 v38; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v39; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v40; // [rsp+58h] [rbp-A8h]
  unsigned int **v41; // [rsp+60h] [rbp-A0h]
  _QWORD *v42; // [rsp+68h] [rbp-98h]
  _QWORD *v43; // [rsp+70h] [rbp-90h]
  __int64 v44; // [rsp+78h] [rbp-88h]
  char v45; // [rsp+80h] [rbp-80h] BYREF
  __int64 v46; // [rsp+88h] [rbp-78h]
  _BYTE v47[48]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v48[32]; // [rsp+C0h] [rbp-40h] BYREF
  int v49; // [rsp+E0h] [rbp-20h]
  __int64 v50; // [rsp+E8h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  v42 = a2;
  v41 = a5;
  v43 = a2;
  v37 = 0;
  v8 = *(__int64 **)(a1 + 104);
  v9 = *v8;
  *(_QWORD *)cchCount1 = 0;
  (*(void (__fastcall **)(__int64 *, __int64, int *))(v9 + 32))(v8, a4, cchCount1);
  v10 = *(_QWORD *)cchCount1;
  if ( *(_QWORD *)cchCount1 )
  {
    *(_QWORD *)cchCount1 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  }
  MakeCom<LicenseManagerCore::KeyCoreWrapper,>(&v36);
  *a2 = 0;
  v37 = 1;
  v11 = v36;
  v12 = **(__int64 (__fastcall ***)(__int64, GUID *, _QWORD *))v36;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(a2);
  v13 = v12(v11, &GUID_cff16f1d_392c_47fa_95f4_c9d037df050c, a2);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x30D,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\managercore.cpp",
      (const char *)(unsigned int)v13,
      bIgnoreCase);
  v14 = 0;
  v40 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 64));
  v44 = a1 + 64;
  for ( i = *(_QWORD *)(a1 + 136); i != *(_QWORD *)(a1 + 144); i += 48 )
  {
    if ( *((_QWORD *)a3 + 3) <= 7u )
      v17 = a3;
    else
      v17 = *(const WCHAR **)a3;
    v18 = *((_QWORD *)a3 + 2);
    *(_QWORD *)cchCount1 = *(_QWORD *)(i + 16);
    if ( (unsigned __int8)IsCompareContentIdPresent(v15) )
    {
      if ( *(_QWORD *)(i + 24) <= 7u )
        v33 = (const WCHAR *)i;
      else
        v33 = *(const WCHAR **)i;
      v20 = CompareContentId(v33, (unsigned int)cchCount1[0], v17, (unsigned int)v18);
    }
    else
    {
      if ( *(_QWORD *)(i + 24) <= 7u )
        v19 = (const WCHAR *)i;
      else
        v19 = *(const WCHAR **)i;
      v20 = CompareStringOrdinal(v19, cchCount1[0], v17, v18, 1) - 2;
    }
    if ( !v20 )
      goto LABEL_15;
  }
  i = *(_QWORD *)(a1 + 144);
LABEL_15:
  if ( i == *(_QWORD *)(a1 + 144) )
  {
    LODWORD(v38) = 0;
    v39 = 0;
    ContentIdString::ContentIdString((ContentIdString *)v48, (const struct ContentIdString *)a3);
    v49 = 0;
    v50 = 0;
    v39 = 0;
    v31 = *(_QWORD *)(a1 + 144);
    if ( v31 == *(_QWORD *)(a1 + 152) )
    {
      i = std::vector<std::pair<ContentIdString,KeyEntry>>::_Emplace_reallocate<std::pair<ContentIdString,KeyEntry>>(
            a1 + 136,
            i,
            v48);
    }
    else if ( i == v31 )
    {
      std::vector<std::pair<ContentIdString,KeyEntry>>::_Emplace_back_with_unused_capacity<std::pair<ContentIdString,KeyEntry>>(
        a1 + 136,
        v48);
    }
    else
    {
      v46 = a1 + 136;
      std::pair<ContentIdString,KeyEntry>::pair<ContentIdString,KeyEntry>(v47, v48);
      v32 = v31 - 48;
      std::pair<ContentIdString,KeyEntry>::pair<ContentIdString,KeyEntry>(v31, v31 - 48);
      *(_QWORD *)(a1 + 144) += 48LL;
      while ( v32 != i )
      {
        v32 -= 48;
        v31 -= 48;
        std::pair<ContentIdString,KeyEntry>::operator=<std::pair<ContentIdString,KeyEntry>,0>(v31, v32);
      }
      std::pair<ContentIdString,KeyEntry>::operator=<std::pair<ContentIdString,KeyEntry>,0>(i, v47);
      std::pair<ContentIdString,KeyEntry>::~pair<ContentIdString,KeyEntry>((ContentIdString *)v47);
    }
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v50);
    ContentIdString::~ContentIdString((ContentIdString *)v48);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v39);
  }
  if ( !*(_QWORD *)(i + 40) )
  {
    v38 = a1;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
    v21 = (char *)CreateKey(cchCount1, a3, &v38);
    v22 = 0;
    if ( &v45 != v21 )
    {
      v22 = *(_QWORD *)v21;
      *(_QWORD *)v21 = 0;
    }
    v23 = *(_QWORD *)(i + 40);
    *(_QWORD *)(i + 40) = v22;
    if ( v23 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    v24 = *(_QWORD *)cchCount1;
    if ( *(_QWORD *)cchCount1 )
    {
      *(_QWORD *)cchCount1 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    }
    if ( v38 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
  }
  v25 = *(_QWORD *)(i + 40);
  if ( v25 )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v25 + 8LL))(*(_QWORD *)(i + 40));
    v14 = v25;
    v40 = v25;
  }
  (*(void (__fastcall **)(__int64, _QWORD, unsigned int *, unsigned int *))(*(_QWORD *)v14 + 56LL))(
    v14,
    **v41,
    v41[1],
    v41[2]);
  v26 = v36;
  if ( *(_QWORD *)(v36 + 24) != a1 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
    v27 = *(_QWORD *)(v26 + 24);
    *(_QWORD *)(v26 + 24) = a1;
    if ( v27 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    v26 = v36;
  }
  if ( *(_QWORD *)(v26 + 16) != v14 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14);
    v28 = *(_QWORD *)(v26 + 16);
    *(_QWORD *)(v26 + 16) = v14;
    if ( v28 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
  }
  ++*(_DWORD *)(i + 32);
  if ( a1 != -64 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 64));
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  v29 = v36;
  if ( v36 )
  {
    v36 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
  }
  return v42;
}

```

## disassembly

```asm
0x18001e690  push    rbp
0x18001e692  push    rbx
0x18001e693  push    rsi
0x18001e694  push    rdi
0x18001e695  push    r12
0x18001e697  push    r13
0x18001e699  push    r14
0x18001e69b  push    r15
0x18001e69d  lea     rbp, [rsp-8]
0x18001e6a2  sub     rsp, 108h
0x18001e6a9  mov     rax, cs:__security_cookie
0x18001e6b0  xor     rax, rsp
0x18001e6b3  mov     [rbp+40h+var_50], rax
0x18001e6b7  mov     r13, r8
0x18001e6ba  mov     rsi, rdx
0x18001e6bd  mov     [rsp+140h+var_D8], rdx
0x18001e6c2  mov     r12, rcx
0x18001e6c5  mov     rax, [rbp+40h+arg_20]
0x18001e6c9  mov     [rsp+140h+var_E0], rax
0x18001e6ce  mov     [rsp+140h+var_D0], rdx
0x18001e6d3  xor     r15d, r15d
0x18001e6d6  mov     [rsp+140h+var_100], r15d
0x18001e6db  mov     rcx, [rcx+68h]
0x18001e6df  mov     rax, [rcx]
0x18001e6e2  mov     qword ptr [rsp+140h+cchCount1], r15
0x18001e6e7  lea     r8, [rsp+140h+cchCount1]
0x18001e6ec  mov     rdx, r9
0x18001e6ef  mov     rax, [rax+20h]
0x18001e6f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e6f8  nop
0x18001e6f9  mov     rcx, qword ptr [rsp+140h+cchCount1]
0x18001e6fe  test    rcx, rcx
0x18001e701  jz      short loc_18001E715
0x18001e703  mov     qword ptr [rsp+140h+cchCount1], r15
0x18001e708  mov     rax, [rcx]
0x18001e70b  mov     rax, [rax+10h]
0x18001e70f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e714  nop
0x18001e715  lea     rcx, [rsp+140h+var_108]
0x18001e71a  call    ??$MakeCom@VKeyCoreWrapper@LicenseManagerCore@@$$V@@YA?AV?$ComPtr@VKeyCoreWrapper@LicenseManagerCore@@@WRL@Microsoft@@XZ; MakeCom<LicenseManagerCore::KeyCoreWrapper,>(void)
0x18001e71f  nop
0x18001e720  mov     [rsi], r15
0x18001e723  mov     [rsp+140h+var_100], 1
0x18001e72b  mov     rbx, [rsp+140h+var_108]
0x18001e730  mov     rax, [rbx]
0x18001e733  mov     rdi, [rax]
0x18001e736  mov     rcx, rsi
0x18001e739  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001e73e  mov     r8, rsi
0x18001e741  lea     rdx, _GUID_cff16f1d_392c_47fa_95f4_c9d037df050c
0x18001e748  mov     rcx, rbx
0x18001e74b  mov     rax, rdi
0x18001e74e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e753  nop
0x18001e754  mov     rcx, [rbp+48h]; this
0x18001e758  test    eax, eax
0x18001e75a  js      loc_18001EA93
0x18001e760  mov     rsi, r15
0x18001e763  mov     [rsp+140h+var_E8], r15
0x18001e768  lea     rbx, [r12+40h]
0x18001e76d  mov     rcx, rbx; lpCriticalSection
0x18001e770  call    cs:__imp_EnterCriticalSection
0x18001e776  mov     [rsp+140h+var_C8], rbx
0x18001e77b  lea     r14, [r12+88h]
0x18001e783  mov     rbx, [r14]
0x18001e786  cmp     rbx, [r14+8]
0x18001e78a  jz      short loc_18001E7EB
0x18001e78c  cmp     qword ptr [r13+18h], 7
0x18001e791  jbe     loc_18001E99F
0x18001e797  mov     rdi, [r13+0]
0x18001e79b  mov     r15, [r13+10h]
0x18001e79f  mov     rax, [rbx+10h]
0x18001e7a3  mov     qword ptr [rsp+140h+cchCount1], rax
0x18001e7a8  call    IsCompareContentIdPresent
0x18001e7ad  test    al, al
0x18001e7af  jnz     loc_18001EA51
0x18001e7b5  cmp     qword ptr [rbx+18h], 7
0x18001e7ba  jbe     loc_18001E9A7
0x18001e7c0  mov     rcx, [rbx]; lpString1
0x18001e7c3  mov     r9d, r15d; cchCount2
0x18001e7c6  mov     edx, [rsp+140h+cchCount1]; cchCount1
0x18001e7ca  mov     [rsp+140h+bIgnoreCase], 1; bIgnoreCase
0x18001e7d2  mov     r8, rdi; lpString2
0x18001e7d5  call    cs:__imp_CompareStringOrdinal
0x18001e7db  sub     eax, 2
0x18001e7de  xor     r15d, r15d
0x18001e7e1  test    eax, eax
0x18001e7e3  jz      short loc_18001E7EF
0x18001e7e5  add     rbx, 30h ; '0'
0x18001e7e9  jmp     short loc_18001E786
0x18001e7eb  mov     rbx, [r14+8]
0x18001e7ef  cmp     rbx, [r14+8]
0x18001e7f3  jz      loc_18001E9AF
0x18001e7f9  cmp     [rbx+28h], r15
0x18001e7fd  jnz     loc_18001E88D
0x18001e803  mov     [rsp+140h+var_F8], r12
0x18001e808  mov     rax, [r12]
0x18001e80c  mov     rcx, r12
0x18001e80f  mov     rax, [rax+8]
0x18001e813  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e818  nop
0x18001e819  lea     r8, [rsp+140h+var_F8]
0x18001e81e  mov     rdx, r13
0x18001e821  lea     rcx, [rsp+140h+cchCount1]
0x18001e826  call    ?CreateKey@@YA?AV?$ComPtr@UIKeyForCore@@@WRL@Microsoft@@AEBVContentIdString@@AEBV?$ComPtr@UICoreForKey@@@23@@Z; CreateKey(ContentIdString const &,Microsoft::WRL::ComPtr<ICoreForKey> const &)
0x18001e82b  mov     rcx, rax
0x18001e82e  mov     rax, r15
0x18001e831  lea     rdx, [rbp+40h+var_C0]
0x18001e835  cmp     rdx, rcx
0x18001e838  jz      short loc_18001E840
0x18001e83a  mov     rax, [rcx]
0x18001e83d  mov     [rcx], r15
0x18001e840  mov     rcx, [rbx+28h]
0x18001e844  mov     [rbx+28h], rax
0x18001e848  test    rcx, rcx
0x18001e84b  jz      short loc_18001E85A
0x18001e84d  mov     rax, [rcx]
0x18001e850  mov     rax, [rax+10h]
0x18001e854  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e859  nop
0x18001e85a  mov     rcx, qword ptr [rsp+140h+cchCount1]
0x18001e85f  test    rcx, rcx
0x18001e862  jz      short loc_18001E876
0x18001e864  mov     qword ptr [rsp+140h+cchCount1], r15
0x18001e869  mov     rax, [rcx]
0x18001e86c  mov     rax, [rax+10h]
0x18001e870  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e875  nop
0x18001e876  mov     rcx, [rsp+140h+var_F8]
0x18001e87b  test    rcx, rcx
0x18001e87e  jz      short loc_18001E88D
0x18001e880  mov     rax, [rcx]
0x18001e883  mov     rax, [rax+10h]
0x18001e887  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e88c  nop
0x18001e88d  mov     rdi, [rbx+28h]
0x18001e891  test    rdi, rdi
0x18001e894  jz      short loc_18001E8AE
0x18001e896  mov     rax, [rdi]
0x18001e899  mov     rcx, rdi
0x18001e89c  mov     rax, [rax+8]
0x18001e8a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e8a5  nop
0x18001e8a6  mov     rsi, rdi
0x18001e8a9  mov     [rsp+140h+var_E8], rdi
0x18001e8ae  mov     rax, [rsi]
0x18001e8b1  mov     rcx, [rsp+140h+var_E0]
0x18001e8b6  mov     rdx, [rcx]
0x18001e8b9  mov     r9, [rcx+10h]
0x18001e8bd  mov     r8, [rcx+8]
0x18001e8c1  mov     edx, [rdx]
0x18001e8c3  mov     rcx, rsi
0x18001e8c6  mov     rax, [rax+38h]
0x18001e8ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e8cf  mov     rdi, [rsp+140h+var_108]
0x18001e8d4  cmp     [rdi+18h], r12
0x18001e8d8  jz      short loc_18001E90A
0x18001e8da  mov     rax, [r12]
0x18001e8de  mov     rcx, r12
0x18001e8e1  mov     rax, [rax+8]
0x18001e8e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e8ea  nop
0x18001e8eb  mov     rcx, [rdi+18h]
0x18001e8ef  mov     [rdi+18h], r12
0x18001e8f3  test    rcx, rcx
0x18001e8f6  jz      short loc_18001E905
0x18001e8f8  mov     rax, [rcx]
0x18001e8fb  mov     rax, [rax+10h]
0x18001e8ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e904  nop
0x18001e905  mov     rdi, [rsp+140h+var_108]
0x18001e90a  cmp     [rdi+10h], rsi
0x18001e90e  jz      short loc_18001E93A
0x18001e910  mov     rax, [rsi]
0x18001e913  mov     rcx, rsi
0x18001e916  mov     rax, [rax+8]
0x18001e91a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e91f  nop
0x18001e920  mov     rcx, [rdi+10h]
0x18001e924  mov     [rdi+10h], rsi
0x18001e928  test    rcx, rcx
0x18001e92b  jz      short loc_18001E93A
0x18001e92d  mov     rax, [rcx]
0x18001e930  mov     rax, [rax+10h]
0x18001e934  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e939  nop
0x18001e93a  inc     dword ptr [rbx+20h]
0x18001e93d  lea     rcx, [r12+40h]; lpCriticalSection
0x18001e942  test    rcx, rcx
0x18001e945  jz      short loc_18001E94E
0x18001e947  call    cs:__imp_LeaveCriticalSection
0x18001e94d  nop
0x18001e94e  mov     rax, [rsi]
0x18001e951  mov     rcx, rsi
0x18001e954  mov     rax, [rax+10h]
0x18001e958  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e95d  nop
0x18001e95e  mov     rcx, [rsp+140h+var_108]
0x18001e963  test    rcx, rcx
0x18001e966  jz      short loc_18001E97A
0x18001e968  mov     [rsp+140h+var_108], r15
0x18001e96d  mov     rdx, [rcx]
0x18001e970  mov     rax, [rdx+10h]
0x18001e974  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e979  nop
0x18001e97a  mov     rax, [rsp+140h+var_D8]
0x18001e97f  mov     rcx, [rbp+40h+var_50]
0x18001e983  xor     rcx, rsp; StackCookie
0x18001e986  call    __security_check_cookie
0x18001e98b  add     rsp, 108h
0x18001e992  pop     r15
0x18001e994  pop     r14
0x18001e996  pop     r13
0x18001e998  pop     r12
0x18001e99a  pop     rdi
0x18001e99b  pop     rsi
0x18001e99c  pop     rbx
0x18001e99d  pop     rbp
0x18001e99e  retn
0x18001e99f  mov     rdi, r13
0x18001e9a2  jmp     loc_18001E79B
0x18001e9a7  mov     rcx, rbx
0x18001e9aa  jmp     loc_18001E7C3
0x18001e9af  mov     dword ptr [rsp+140h+var_F8], r15d
0x18001e9b4  mov     [rsp+140h+var_F0], r15
0x18001e9b9  mov     rdx, r13; struct ContentIdString *
0x18001e9bc  lea     rcx, [rbp+40h+var_80]; this
0x18001e9c0  call    ??0ContentIdString@@QEAA@AEBV0@@Z; ContentIdString::ContentIdString(ContentIdString const &)
0x18001e9c5  mov     [rbp+40h+var_60], r15d
0x18001e9c9  mov     [rbp+40h+var_58], r15
0x18001e9cd  mov     [rsp+140h+var_F0], r15
0x18001e9d2  mov     rdi, [r14+8]
0x18001e9d6  cmp     rdi, [r14+10h]
0x18001e9da  jz      loc_18001EA7F
0x18001e9e0  lea     rdx, [rbp+40h+var_80]
0x18001e9e4  cmp     rbx, rdi
0x18001e9e7  jz      loc_18001EA75
0x18001e9ed  mov     [rbp+40h+var_B8], r14
0x18001e9f1  lea     rcx, [rbp+40h+var_B0]
0x18001e9f5  call    ??0?$pair@VContentIdString@@UKeyEntry@@@std@@QEAA@$$QEAU01@@Z; std::pair<ContentIdString,KeyEntry>::pair<ContentIdString,KeyEntry>(std::pair<ContentIdString,KeyEntry> &&)
0x18001e9fa  lea     r15, [rdi-30h]
0x18001e9fe  mov     rdx, r15
0x18001ea01  mov     rcx, rdi
0x18001ea04  call    ??0?$pair@VContentIdString@@UKeyEntry@@@std@@QEAA@$$QEAU01@@Z; std::pair<ContentIdString,KeyEntry>::pair<ContentIdString,KeyEntry>(std::pair<ContentIdString,KeyEntry> &&)
0x18001ea09  add     qword ptr [r14+8], 30h ; '0'
0x18001ea0e  cmp     r15, rbx
0x18001ea11  jnz     loc_18001EAA8
0x18001ea17  lea     rdx, [rbp+40h+var_B0]
0x18001ea1b  mov     rcx, rbx
0x18001ea1e  call    ??$?4U?$pair@VContentIdString@@UKeyEntry@@@std@@$0A@@?$pair@VContentIdString@@UKeyEntry@@@std@@QEAAAEAU01@$$QEAU01@@Z; std::pair<ContentIdString,KeyEntry>::operator=<std::pair<ContentIdString,KeyEntry>,0>(std::pair<ContentIdString,KeyEntry> &&)
0x18001ea23  lea     rcx, [rbp+40h+var_B0]; this
0x18001ea27  call    ??1?$pair@VContentIdString@@UKeyEntry@@@std@@QEAA@XZ; std::pair<ContentIdString,KeyEntry>::~pair<ContentIdString,KeyEntry>(void)
0x18001ea2c  xor     r15d, r15d
0x18001ea2f  lea     rcx, [rbp+40h+var_58]
0x18001ea33  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001ea38  lea     rcx, [rbp+40h+var_80]; this
0x18001ea3c  call    ??1ContentIdString@@QEAA@XZ; ContentIdString::~ContentIdString(void)
0x18001ea41  nop
0x18001ea42  lea     rcx, [rsp+140h+var_F0]
0x18001ea47  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001ea4c  jmp     loc_18001E7F9
0x18001ea51  cmp     qword ptr [rbx+18h], 7
0x18001ea56  jbe     short loc_18001EA70
0x18001ea58  mov     rcx, [rbx]
0x18001ea5b  mov     r9d, r15d
0x18001ea5e  mov     edx, [rsp+140h+cchCount1]
0x18001ea62  mov     r8, rdi
0x18001ea65  call    cs:__imp_CompareContentId
0x18001ea6b  jmp     loc_18001E7DE
0x18001ea70  mov     rcx, rbx
0x18001ea73  jmp     short loc_18001EA5B
0x18001ea75  mov     rcx, r14
0x18001ea78  call    ??$_Emplace_back_with_unused_capacity@U?$pair@VContentIdString@@UKeyEntry@@@std@@@?$vector@U?$pair@VContentIdString@@UKeyEntry@@@std@@V?$allocator@U?$pair@VContentIdString@@UKeyEntry@@@std@@@2@@std@@AEAAAEAU?$pair@VContentIdString@@UKeyEntry@@@1@$$QEAU21@@Z; std::vector<std::pair<ContentIdString,KeyEntry>>::_Emplace_back_with_unused_capacity<std::pair<ContentIdString,KeyEntry>>(std::pair<ContentIdString,KeyEntry> &&)
0x18001ea7d  jmp     short loc_18001EA2F
0x18001ea7f  lea     r8, [rbp+40h+var_80]
0x18001ea83  mov     rdx, rbx
0x18001ea86  mov     rcx, r14
0x18001ea89  call    ??$_Emplace_reallocate@U?$pair@VContentIdString@@UKeyEntry@@@std@@@?$vector@U?$pair@VContentIdString@@UKeyEntry@@@std@@V?$allocator@U?$pair@VContentIdString@@UKeyEntry@@@std@@@2@@std@@AEAAPEAU?$pair@VContentIdString@@UKeyEntry@@@1@QEAU21@$$QEAU21@@Z; std::vector<std::pair<ContentIdString,KeyEntry>>::_Emplace_reallocate<std::pair<ContentIdString,KeyEntry>>(std::pair<ContentIdString,KeyEntry> * const,std::pair<ContentIdString,KeyEntry> &&)
0x18001ea8e  mov     rbx, rax
0x18001ea91  jmp     short loc_18001EA2F
0x18001ea93  mov     r9d, eax; char *
0x18001ea96  lea     r8, aOnecoreuapEndu_17; "onecoreuap\\enduser\\winstore\\licensem"...
0x18001ea9d  mov     edx, 30Dh; void *
0x18001eaa2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001eaa8  sub     r15, 30h ; '0'
0x18001eaac  sub     rdi, 30h ; '0'
0x18001eab0  mov     rdx, r15
0x18001eab3  mov     rcx, rdi
0x18001eab6  call    ??$?4U?$pair@VContentIdString@@UKeyEntry@@@std@@$0A@@?$pair@VContentIdString@@UKeyEntry@@@std@@QEAAAEAU01@$$QEAU01@@Z; std::pair<ContentIdString,KeyEntry>::operator=<std::pair<ContentIdString,KeyEntry>,0>(std::pair<ContentIdString,KeyEntry> &&)
0x18001eabb  jmp     loc_18001EA0E
```
