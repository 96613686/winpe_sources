# DatabaseTQMAdaptor::RetrieveAumIdsForPackage(ushort const *,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &)

- ea: `0x1800449e0`
- end: `0x180044d55`
- name: `?RetrieveAumIdsForPackage@DatabaseTQMAdaptor@@UEAAJPEBGAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z`
- size: `885`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180004e38`
- `0x18000e5f4`
- `0x1800117c0`
- `0x180014120`
- `0x180014220`
- `0x1800449e0`
- `0x180045ab4`
- `0x1800b99f0`
- `0x180100354`
- `0x180118010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180044bd7`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180044bd7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044b4a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044bf0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044c76`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044b4a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044bf0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044c76`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall DatabaseTQMAdaptor::RetrieveAumIdsForPackage(__int64 a1, __int64 a2, _QWORD *a3)
{
  int v5; // eax
  __int64 v6; // rsi
  WCHAR *v7; // r14
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, wil **); // rbx
  int v10; // eax
  int v11; // eax
  unsigned int i; // r12d
  wil *v13; // rdi
  __int64 (__fastcall *v14)(wil *, _QWORD, __int64 *); // rbx
  int v15; // eax
  __int64 v16; // rbx
  __int64 (__fastcall *v17)(__int64, LPVOID *); // rdi
  int v18; // eax
  const WCHAR *v19; // r8
  __int64 v20; // rdx
  const WCHAR *v21; // rcx
  __int64 v22; // rcx
  wil *v23; // rcx
  __int64 result; // rax
  __int64 v25; // rcx
  _QWORD *v26; // rbx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-C8h]
  BOOL bIgnoreCasea; // [rsp+20h] [rbp-C8h]
  unsigned int v29; // [rsp+30h] [rbp-B8h] BYREF
  wil *v30; // [rsp+38h] [rbp-B0h] BYREF
  __int64 v31; // [rsp+40h] [rbp-A8h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-A0h] BYREF
  __int64 v33; // [rsp+50h] [rbp-98h]
  __int64 v34; // [rsp+58h] [rbp-90h]
  LPCWCH lpString1; // [rsp+60h] [rbp-88h] BYREF
  __int64 v36; // [rsp+68h] [rbp-80h]
  __int64 v37; // [rsp+70h] [rbp-78h]
  _QWORD *v38; // [rsp+78h] [rbp-70h]
  _BYTE v39[32]; // [rsp+80h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  v38 = a3;
  lpString1 = 0;
  v36 = 0;
  v37 = 0;
  v5 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
         &lpString1,
         L"%s!",
         a2);
  try
  {
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x336,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\databasetqmadaptor.cpp",
        (const char *)(unsigned int)v5,
        bIgnoreCasea);
    v6 = v36;
    v7 = (WCHAR *)lpString1;
    if ( v36 == -1 )
    {
      if ( lpString1 )
      {
        do
          ++v6;
        while ( lpString1[v6] );
        v36 = v6;
      }
      else
      {
        v6 = 0;
        v36 = 0;
      }
    }
    v30 = 0;
    v8 = *(_QWORD *)(a1 + 40);
    v9 = *(__int64 (__fastcall **)(__int64, wil **))(*(_QWORD *)v8 + 232LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
    v10 = v9(v8, &v30);
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x33A,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\databasetqmadaptor.cpp",
        (const char *)(unsigned int)v10,
        bIgnoreCasea);
    v29 = 0;
    v11 = (*(__int64 (__fastcall **)(wil *, unsigned int *))(*(_QWORD *)v30 + 32LL))(v30, &v29);
    if ( v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x33D,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\databasetqmadaptor.cpp",
        (const char *)(unsigned int)v11,
        bIgnoreCasea);
    for ( i = 0; i < v29; ++i )
    {
      v31 = 0;
      pv = 0;
      v33 = 0;
      v34 = 0;
      v13 = v30;
      v14 = *(__int64 (__fastcall **)(wil *, _QWORD, __int64 *))(*(_QWORD *)v30 + 24LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
      v15 = v14(v13, i, &v31);
      if ( v15 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x343,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\databasetqmadaptor.cpp",
          (const char *)(unsigned int)v15,
          bIgnoreCasea);
      v16 = v31;
      v17 = *(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v31 + 24LL);
      if ( pv )
      {
        CoTaskMemFree(pv);
        pv = 0;
      }
      v33 = -1;
      v34 = -1;
      v18 = v17(v16, &pv);
      if ( v18 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x344,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\databasetqmadaptor.cpp",
          (const char *)(unsigned int)v18,
          bIgnoreCasea);
      v19 = &word_180124798;
      if ( pv )
        v19 = (const WCHAR *)pv;
      LODWORD(v20) = v6;
      if ( v6 == -1 )
      {
        if ( v7 )
        {
          v20 = -1;
          do
            ++v20;
          while ( v7[v20] );
        }
        else
        {
          LODWORD(v20) = 0;
        }
      }
      v21 = &word_180124798;
      if ( v7 )
        v21 = v7;
      if ( CompareStringOrdinal(v21, v20, v19, pv != 0 ? v6 : 0, 1) == 2 )
      {
        std::wstring::wstring(v39, pv);
        v25 = a3[1];
        if ( v25 == a3[2] )
        {
          std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(a3, a3[1], v39);
        }
        else
        {
          std::wstring::wstring(v25, v39);
          a3[1] += 32LL;
        }
        std::pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>::~pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>(v39);
      }
      if ( pv )
      {
        CoTaskMemFree(pv);
        pv = 0;
      }
      v33 = 0;
      v34 = 0;
      v22 = v31;
      if ( v31 )
      {
        v31 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
      }
    }
    v23 = v30;
    if ( v30 )
    {
      v30 = 0;
      (*(void (__fastcall **)(wil *))(*(_QWORD *)v23 + 16LL))(v23);
    }
    if ( v7 )
      CoTaskMemFree(v7);
    result = 0;
  }
  catch ( ... )
  {
    v26 = v38;
    if ( *v38 != v38[1] )
    {
      std::_Destroy_range<std::allocator<std::wstring>>((void *)*v38);
      v26[1] = *v26;
    }
    v29 = wil::ResultFromCaughtException(v23);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x34F,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\databasetqmadaptor.cpp",
      (const char *)v29,
      bIgnoreCase);
    return v29;
  }
  return result;
}

```

## disassembly

```asm
0x1800449e0  push    rbx
0x1800449e2  push    rsi
0x1800449e3  push    rdi
0x1800449e4  push    r12
0x1800449e6  push    r13
0x1800449e8  push    r14
0x1800449ea  push    r15
0x1800449ec  sub     rsp, 0B0h
0x1800449f3  mov     rax, cs:__security_cookie
0x1800449fa  xor     rax, rsp
0x1800449fd  mov     [rsp+0E8h+var_48], rax
0x180044a05  mov     r15, r8
0x180044a08  mov     rdi, rcx
0x180044a0b  mov     [rsp+0E8h+var_70], r8
0x180044a10  xor     r13d, r13d
0x180044a13  mov     [rsp+0E8h+lpString1], r13
0x180044a18  mov     [rsp+0E8h+var_80], r13
0x180044a1d  mov     [rsp+0E8h+var_78], r13
0x180044a22  mov     r8, rdx
0x180044a25  lea     rdx, aS; "%s!"
0x180044a2c  lea     rcx, [rsp+0E8h+lpString1]
0x180044a31  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x180044a36  mov     rcx, [rsp+0E8h]; this
0x180044a3e  test    eax, eax
0x180044a40  js      loc_180044CA2
0x180044a46  mov     rsi, [rsp+0E8h+var_80]
0x180044a4b  mov     r14, [rsp+0E8h+lpString1]
0x180044a50  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180044a54  jnz     short loc_180044A71
0x180044a56  test    r14, r14
0x180044a59  jz      loc_180044CE0
0x180044a5f  or      rsi, rsi
0x180044a62  inc     rsi
0x180044a65  cmp     [r14+rsi*2], r13w
0x180044a6a  jnz     short loc_180044A62
0x180044a6c  mov     [rsp+0E8h+var_80], rsi
0x180044a71  mov     [rsp+0E8h+var_B0], r13
0x180044a76  mov     rdi, [rdi+28h]
0x180044a7a  mov     rax, [rdi]
0x180044a7d  mov     rbx, [rax+0E8h]
0x180044a84  lea     rcx, [rsp+0E8h+var_B0]
0x180044a89  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180044a8e  lea     rdx, [rsp+0E8h+var_B0]
0x180044a93  mov     rcx, rdi
0x180044a96  mov     rax, rbx
0x180044a99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044a9e  mov     rcx, [rsp+0E8h]; this
0x180044aa6  test    eax, eax
0x180044aa8  js      loc_180044CB7
0x180044aae  mov     [rsp+0E8h+var_B8], r13d
0x180044ab3  mov     rcx, [rsp+0E8h+var_B0]
0x180044ab8  mov     rax, [rcx]
0x180044abb  lea     rdx, [rsp+0E8h+var_B8]
0x180044ac0  mov     rax, [rax+20h]
0x180044ac4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044ac9  mov     rcx, [rsp+0E8h]; this
0x180044ad1  test    eax, eax
0x180044ad3  js      loc_180044CCB
0x180044ad9  mov     r12d, r13d
0x180044adc  cmp     r12d, [rsp+0E8h+var_B8]
0x180044ae1  jnb     loc_180044C52
0x180044ae7  mov     [rsp+0E8h+var_A8], r13
0x180044aec  mov     [rsp+0E8h+pv], r13
0x180044af1  mov     [rsp+0E8h+var_98], r13
0x180044af6  mov     [rsp+0E8h+var_90], r13
0x180044afb  mov     rdi, [rsp+0E8h+var_B0]
0x180044b00  mov     rax, [rdi]
0x180044b03  mov     rbx, [rax+18h]
0x180044b07  lea     rcx, [rsp+0E8h+var_A8]
0x180044b0c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180044b11  lea     r8, [rsp+0E8h+var_A8]
0x180044b16  mov     edx, r12d
0x180044b19  mov     rcx, rdi
0x180044b1c  mov     rax, rbx
0x180044b1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044b24  mov     rcx, [rsp+0E8h]; this
0x180044b2c  test    eax, eax
0x180044b2e  js      loc_180044C29
0x180044b34  mov     rbx, [rsp+0E8h+var_A8]
0x180044b39  mov     rax, [rbx]
0x180044b3c  mov     rdi, [rax+18h]
0x180044b40  mov     rcx, [rsp+0E8h+pv]; pv
0x180044b45  test    rcx, rcx
0x180044b48  jz      short loc_180044B55
0x180044b4a  call    cs:__imp_CoTaskMemFree
0x180044b50  mov     [rsp+0E8h+pv], r13
0x180044b55  or      rax, 0FFFFFFFFFFFFFFFFh
0x180044b59  mov     [rsp+0E8h+var_98], rax
0x180044b5e  mov     [rsp+0E8h+var_90], rax
0x180044b63  lea     rdx, [rsp+0E8h+pv]
0x180044b68  mov     rcx, rbx
0x180044b6b  mov     rax, rdi
0x180044b6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044b73  mov     rcx, [rsp+0E8h]; this
0x180044b7b  test    eax, eax
0x180044b7d  js      loc_180044C3D
0x180044b83  mov     rcx, [rsp+0E8h+pv]
0x180044b88  mov     rax, rcx
0x180044b8b  neg     rax
0x180044b8e  sbb     r9d, r9d
0x180044b91  and     r9d, esi; cchCount2
0x180044b94  lea     r8, word_180124798
0x180044b9b  test    rcx, rcx
0x180044b9e  cmovnz  r8, rcx; lpString2
0x180044ba2  mov     rdx, rsi
0x180044ba5  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180044ba9  jnz     short loc_180044BC1
0x180044bab  test    r14, r14
0x180044bae  jz      loc_180044CED
0x180044bb4  or      rdx, rsi
0x180044bb7  inc     rdx; cchCount1
0x180044bba  cmp     [r14+rdx*2], r13w
0x180044bbf  jnz     short loc_180044BB7
0x180044bc1  lea     rcx, word_180124798
0x180044bc8  test    r14, r14
0x180044bcb  cmovnz  rcx, r14; lpString1
0x180044bcf  mov     [rsp+0E8h+bIgnoreCase], 1; bIgnoreCase
0x180044bd7  call    cs:__imp_CompareStringOrdinal
0x180044bdd  cmp     eax, 2
0x180044be0  jz      loc_180044CF5
0x180044be6  mov     rcx, [rsp+0E8h+pv]; pv
0x180044beb  test    rcx, rcx
0x180044bee  jz      short loc_180044BFB
0x180044bf0  call    cs:__imp_CoTaskMemFree
0x180044bf6  mov     [rsp+0E8h+pv], r13
0x180044bfb  mov     [rsp+0E8h+var_98], r13
0x180044c00  mov     [rsp+0E8h+var_90], r13
0x180044c05  mov     rcx, [rsp+0E8h+var_A8]
0x180044c0a  test    rcx, rcx
0x180044c0d  jz      short loc_180044C21
0x180044c0f  mov     [rsp+0E8h+var_A8], r13
0x180044c14  mov     rax, [rcx]
0x180044c17  mov     rax, [rax+10h]
0x180044c1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044c20  nop
0x180044c21  inc     r12d
0x180044c24  jmp     loc_180044ADC
0x180044c29  mov     r9d, eax; char *
0x180044c2c  lea     r8, aOnecoreuapBase_29; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180044c33  mov     edx, 343h; void *
0x180044c38  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180044c3d  mov     r9d, eax; char *
0x180044c40  lea     r8, aOnecoreuapBase_29; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180044c47  mov     edx, 344h; void *
0x180044c4c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180044c52  mov     rcx, [rsp+0E8h+var_B0]
0x180044c57  test    rcx, rcx
0x180044c5a  jz      short loc_180044C6E
0x180044c5c  mov     [rsp+0E8h+var_B0], r13
0x180044c61  mov     rax, [rcx]
0x180044c64  mov     rax, [rax+10h]
0x180044c68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044c6d  nop
0x180044c6e  test    r14, r14
0x180044c71  jz      short loc_180044C7D
0x180044c73  mov     rcx, r14; pv
0x180044c76  call    cs:__imp_CoTaskMemFree
0x180044c7c  nop
0x180044c7d  xor     eax, eax
0x180044c7f  mov     rcx, [rsp+0E8h+var_48]
0x180044c87  xor     rcx, rsp; StackCookie
0x180044c8a  call    __security_check_cookie
0x180044c8f  add     rsp, 0B0h
0x180044c96  pop     r15
0x180044c98  pop     r14
0x180044c9a  pop     r13
0x180044c9c  pop     r12
0x180044c9e  pop     rdi
0x180044c9f  pop     rsi
0x180044ca0  pop     rbx
0x180044ca1  retn
0x180044ca2  mov     r9d, eax; char *
0x180044ca5  lea     r8, aOnecoreuapBase_29; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180044cac  mov     edx, 336h; void *
0x180044cb1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180044cb7  mov     r9d, eax; char *
0x180044cba  lea     r8, aOnecoreuapBase_29; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180044cc1  mov     edx, 33Ah; void *
0x180044cc6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180044ccb  mov     r9d, eax; char *
0x180044cce  lea     r8, aOnecoreuapBase_29; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180044cd5  mov     edx, 33Dh; void *
0x180044cda  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180044ce0  mov     rsi, r13
0x180044ce3  mov     [rsp+0E8h+var_80], r13
0x180044ce8  jmp     loc_180044A71
0x180044ced  mov     rdx, r13
0x180044cf0  jmp     loc_180044BC1
0x180044cf5  mov     rdx, [rsp+0E8h+pv]
0x180044cfa  lea     rcx, [rsp+0E8h+var_68]
0x180044d02  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180044d07  nop
0x180044d08  mov     rcx, [r15+8]
0x180044d0c  cmp     rcx, [r15+10h]
0x180044d10  jz      short loc_180044D26
0x180044d12  lea     rdx, [rsp+0E8h+var_68]
0x180044d1a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x180044d1f  add     qword ptr [r15+8], 20h ; ' '
0x180044d24  jmp     short loc_180044D3A
0x180044d26  lea     r8, [rsp+0E8h+var_68]
0x180044d2e  mov     rdx, rcx
0x180044d31  mov     rcx, r15
0x180044d34  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x180044d39  nop
0x180044d3a  lea     rcx, [rsp+0E8h+var_68]; void *
0x180044d42  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4__MIDL___MIDL_itf_wpntypes_0000_0000_0005@@@std@@QEAA@XZ; std::pair<std::wstring const,__MIDL___MIDL_itf_wpntypes_0000_0000_0005>::~pair<std::wstring const,__MIDL___MIDL_itf_wpntypes_0000_0000_0005>(void)
0x180044d47  jmp     loc_180044BE6
0x180044d4c  mov     eax, [rsp+0E8h+var_B8]
0x180044d50  jmp     loc_180044C7F
```
