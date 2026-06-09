# RetailDemoUtil::IsUserInGroup(ushort const *,ulong)

- ea: `0x180031284`
- end: `0x1800314d5`
- name: `?IsUserInGroup@RetailDemoUtil@@YA_NPEBGK@Z`
- size: `593`
- prototype: `bool __fastcall(LPCWCH lpString1, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180021830`

## callees

- `0x180008bbc`
- `0x18000e3bc`
- `0x18001094c`
- `0x180010a60`
- `0x18002ed74`
- `0x180031284`
- `0x180050010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180031407`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180031407`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800312cc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800312cc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180031438`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180031438`

## string_xrefs

- `0x18003146f`: `shellcommon\shell\retaildemo\util\retaildemoutil.cpp`
- `0x180031484`: `shellcommon\shell\retaildemo\util\retaildemoutil.cpp`
- `0x180031499`: `shellcommon\shell\retaildemo\util\retaildemoutil.cpp`
- `0x1800314ae`: `shellcommon\shell\retaildemo\util\retaildemoutil.cpp`
- `0x1800314c3`: `shellcommon\shell\retaildemo\util\retaildemoutil.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
bool __fastcall RetailDemoUtil::IsUserInGroup(LPCWCH lpString1, const unsigned __int16 *a2, __int64 a3)
{
  unsigned int v3; // esi
  HRESULT v5; // eax
  __int64 v6; // rdx
  __int64 v7; // r8
  LPVOID v8; // rdi
  __int64 (__fastcall *v9)(LPVOID, _QWORD, __int64 *); // rbx
  int v10; // eax
  int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // r8
  bool v14; // di
  unsigned int v15; // esi
  int v16; // eax
  __int64 (__fastcall ***v17)(_QWORD, GUID *, __int64 *); // rcx
  int v18; // eax
  int v19; // ebx
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // rdx
  __int64 v25; // r8
  int ppv; // [rsp+20h] [rbp-60h]
  __int64 v28; // [rsp+30h] [rbp-50h] BYREF
  LPVOID v29; // [rsp+38h] [rbp-48h] BYREF
  __int128 v30; // [rsp+40h] [rbp-40h] BYREF
  int v31; // [rsp+50h] [rbp-30h]
  PROPVARIANT pvar; // [rsp+60h] [rbp-20h] BYREF
  unsigned int v33; // [rsp+68h] [rbp-18h]
  __int64 v34; // [rsp+70h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]
  __int64 v36; // [rsp+C0h] [rbp+40h] BYREF
  LPCWCH lpString2; // [rsp+C8h] [rbp+48h] BYREF

  v3 = (unsigned int)a2;
  v29 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29, a2, a3);
  v5 = CoCreateInstance(&CLSID_LocalGroups, 0, 3u, &GUID_3c708557_c99d_4fa3_9231_56518418b4e4, &v29);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x284,
      (unsigned int)"shellcommon\\shell\\retaildemo\\util\\retaildemoutil.cpp",
      (const char *)(unsigned int)v5,
      ppv);
  v28 = 0;
  v8 = v29;
  v9 = *(__int64 (__fastcall **)(LPVOID, _QWORD, __int64 *))(*(_QWORD *)v29 + 80LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28, v6, v7);
  v10 = v9(v8, v3, &v28);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x287,
      (unsigned int)"shellcommon\\shell\\retaildemo\\util\\retaildemoutil.cpp",
      (const char *)(unsigned int)v10,
      ppv);
  LOWORD(pvar) = 0;
  v11 = (*(__int64 (__fastcall **)(__int64, __int64 *, PROPVARIANT *))(*(_QWORD *)v28 + 40LL))(
          v28,
          PKEY_SAM_GroupMembers,
          &pvar);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x28A,
      (unsigned int)"shellcommon\\shell\\retaildemo\\util\\retaildemoutil.cpp",
      (const char *)(unsigned int)v11,
      ppv);
  v14 = 0;
  if ( (_WORD)pvar )
  {
    v15 = 0;
    do
    {
      if ( v15 >= v33 )
        break;
      v36 = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v36, v12, v13);
      v36 = 0;
      if ( *(_WORD *)(v34 + 24LL * v15) != 13 )
      {
        v16 = -2147467262;
        if ( *(_WORD *)(v34 + 24LL * v15) != 66 )
          continue;
      }
      v17 = *(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))(v34 + 24LL * v15 + 8);
      v16 = (**v17)(v17, &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, &v36);
      if ( v16 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x290,
          (unsigned int)"shellcommon\\shell\\retaildemo\\util\\retaildemoutil.cpp",
          (const char *)(unsigned int)v16,
          ppv);
      lpString2 = 0;
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
        &lpString2,
        0);
      v30 = PKEY_SAM_SecurityID;
      v31 = 18;
      v18 = wil::PropertyStoreHelperBase<IPropertyStore>::GetSIDString<_tagpropertykey>((__int64)&v36, &v30, &lpString2);
      if ( v18 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x293,
          (unsigned int)"shellcommon\\shell\\retaildemo\\util\\retaildemoutil.cpp",
          (const char *)(unsigned int)v18,
          ppv);
      v19 = CompareStringOrdinal(lpString1, -1, lpString2, -1, 0);
      v14 = v19 == 2;
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpString2);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v36, v20, v21);
      ++v15;
    }
    while ( v19 != 2 );
  }
  PropVariantClear(&pvar);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28, v22, v23);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29, v24, v25);
  return v14;
}

```

## disassembly

```asm
0x180031284  mov     [rsp-28h+arg_0], rbx
0x180031289  push    rbp
0x18003128a  push    rsi
0x18003128b  push    rdi
0x18003128c  push    r14
0x18003128e  push    r15
0x180031290  mov     rbp, rsp
0x180031293  sub     rsp, 80h
0x18003129a  mov     esi, edx
0x18003129c  mov     r14, rcx
0x18003129f  xor     r15d, r15d
0x1800312a2  mov     [rbp+var_48], r15
0x1800312a6  lea     rcx, [rbp+var_48]
0x1800312aa  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800312af  lea     rax, [rbp+var_48]
0x1800312b3  mov     qword ptr [rsp+80h+ppv], rax; int
0x1800312b8  lea     r9, _GUID_3c708557_c99d_4fa3_9231_56518418b4e4; riid
0x1800312bf  xor     edx, edx; pUnkOuter
0x1800312c1  lea     r8d, [r15+3]; dwClsContext
0x1800312c5  lea     rcx, CLSID_LocalGroups; rclsid
0x1800312cc  call    cs:__imp_CoCreateInstance
0x1800312d2  mov     rcx, [rbp+28h]; this
0x1800312d6  test    eax, eax
0x1800312d8  js      loc_180031496
0x1800312de  mov     [rbp+var_50], r15
0x1800312e2  mov     rdi, [rbp+var_48]
0x1800312e6  mov     rax, [rdi]
0x1800312e9  mov     rbx, [rax+50h]
0x1800312ed  lea     rcx, [rbp+var_50]
0x1800312f1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800312f6  lea     r8, [rbp+var_50]
0x1800312fa  mov     edx, esi
0x1800312fc  mov     rcx, rdi
0x1800312ff  mov     rax, rbx
0x180031302  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031307  mov     rcx, [rbp+28h]; this
0x18003130b  test    eax, eax
0x18003130d  js      loc_1800314AB
0x180031313  mov     word ptr [rbp+pvar], r15w
0x180031318  mov     rcx, [rbp+var_50]
0x18003131c  mov     rax, [rcx]
0x18003131f  lea     r8, [rbp+pvar]
0x180031323  lea     rdx, PKEY_SAM_GroupMembers
0x18003132a  mov     rax, [rax+28h]
0x18003132e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031333  mov     rcx, [rbp+28h]; this
0x180031337  test    eax, eax
0x180031339  js      loc_1800314C0
0x18003133f  mov     dil, r15b
0x180031342  cmp     word ptr [rbp+pvar], r15w
0x180031347  jz      loc_180031434
0x18003134d  mov     esi, r15d
0x180031350  cmp     esi, [rbp+var_18]
0x180031353  jnb     loc_180031434
0x180031359  mov     [rbp+arg_10], r15
0x18003135d  lea     rcx, [rbp+arg_10]
0x180031361  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180031366  mov     eax, esi
0x180031368  lea     rcx, [rax+rax*2]
0x18003136c  mov     rdx, [rbp+var_10]
0x180031370  mov     [rbp+arg_10], r15
0x180031374  mov     eax, 0Dh
0x180031379  cmp     ax, [rdx+rcx*8]
0x18003137d  jz      short loc_180031391
0x18003137f  mov     eax, 80004002h
0x180031384  mov     r8d, 42h ; 'B'
0x18003138a  cmp     r8w, [rdx+rcx*8]
0x18003138f  jnz     short loc_1800313AC
0x180031391  mov     rcx, [rdx+rcx*8+8]
0x180031396  mov     rax, [rcx]
0x180031399  lea     r8, [rbp+arg_10]
0x18003139d  lea     rdx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x1800313a4  mov     rax, [rax]
0x1800313a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800313ac  mov     rcx, [rbp+28h]; this
0x1800313b0  test    eax, eax
0x1800313b2  js      loc_180031481
0x1800313b8  mov     [rbp+lpString2], r15
0x1800313bc  xor     edx, edx
0x1800313be  lea     rcx, [rbp+lpString2]
0x1800313c2  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x1800313c7  movups  xmm0, cs:PKEY_SAM_SecurityID
0x1800313ce  movaps  [rbp+var_40], xmm0
0x1800313d2  mov     eax, cs:dword_180059BF0
0x1800313d8  mov     [rbp+var_30], eax
0x1800313db  lea     r8, [rbp+lpString2]
0x1800313df  lea     rdx, [rbp+var_40]
0x1800313e3  lea     rcx, [rbp+arg_10]
0x1800313e7  call    ??$GetSIDString@U_tagpropertykey@@@?$PropertyStoreHelperBase@UIPropertyStore@@@wil@@QEBAJU_tagpropertykey@@PEAPEAG@Z; wil::PropertyStoreHelperBase<IPropertyStore>::GetSIDString<_tagpropertykey>(_tagpropertykey,ushort * *)
0x1800313ec  mov     rcx, [rbp+28h]; this
0x1800313f0  test    eax, eax
0x1800313f2  js      short loc_18003146C
0x1800313f4  mov     [rsp+80h+ppv], r15d; bIgnoreCase
0x1800313f9  or      r9d, 0FFFFFFFFh; cchCount2
0x1800313fd  mov     r8, [rbp+lpString2]; lpString2
0x180031401  or      edx, r9d; cchCount1
0x180031404  mov     rcx, r14; lpString1
0x180031407  call    cs:__imp_CompareStringOrdinal
0x18003140d  mov     ebx, eax
0x18003140f  cmp     eax, 2
0x180031412  setz    dil
0x180031416  lea     rcx, [rbp+lpString2]
0x18003141a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18003141f  nop
0x180031420  lea     rcx, [rbp+arg_10]
0x180031424  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180031429  inc     esi
0x18003142b  cmp     ebx, 2
0x18003142e  jnz     loc_180031350
0x180031434  lea     rcx, [rbp+pvar]; pvar
0x180031438  call    cs:__imp_PropVariantClear
0x18003143e  nop
0x18003143f  lea     rcx, [rbp+var_50]
0x180031443  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180031448  nop
0x180031449  lea     rcx, [rbp+var_48]
0x18003144d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180031452  mov     al, dil
0x180031455  mov     rbx, [rsp+80h+arg_0]
0x18003145d  add     rsp, 80h
0x180031464  pop     r15
0x180031466  pop     r14
0x180031468  pop     rdi
0x180031469  pop     rsi
0x18003146a  pop     rbp
0x18003146b  retn
0x18003146c  mov     r9d, eax; char *
0x18003146f  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\retaildemo\\util\\r"...
0x180031476  mov     edx, 293h; void *
0x18003147b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180031481  mov     r9d, eax; char *
0x180031484  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\retaildemo\\util\\r"...
0x18003148b  mov     edx, 290h; void *
0x180031490  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180031496  mov     r9d, eax; char *
0x180031499  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\retaildemo\\util\\r"...
0x1800314a0  mov     edx, 284h; void *
0x1800314a5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800314ab  mov     r9d, eax; char *
0x1800314ae  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\retaildemo\\util\\r"...
0x1800314b5  mov     edx, 287h; void *
0x1800314ba  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800314c0  mov     r9d, eax; char *
0x1800314c3  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\retaildemo\\util\\r"...
0x1800314ca  mov     edx, 28Ah; void *
0x1800314cf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
