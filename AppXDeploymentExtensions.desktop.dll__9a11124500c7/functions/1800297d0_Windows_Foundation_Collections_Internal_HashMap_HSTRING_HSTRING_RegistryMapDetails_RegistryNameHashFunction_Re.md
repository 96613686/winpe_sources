# Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,RegistryMapDetails::RegistryNameHashFunction,RegistryMapDetails::RegistryNameEqualityPredicate,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::Insert(HSTRING__ *,HSTRING__ *,uchar *)

- ea: `0x1800297d0`
- end: `0x180029c67`
- name: `?Insert@?$HashMap@PEAUHSTRING__@@PEAU1@URegistryNameHashFunction@RegistryMapDetails@@URegistryNameEqualityPredicate@3@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U56789@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@6789@@Internal@Collections@Foundation@Windows@@UEAAJPEAUHSTRING__@@0PEAE@Z`
- size: `1175`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callees

- `0x180024444`
- `0x180028c1c`
- `0x1800297d0`
- `0x180029d10`
- `0x180029d8c`
- `0x180029da8`
- `0x18007e974`
- `0x1800830fc`
- `0x1800af1bc`
- `0x1800af1fc`
- `0x1800af918`
- `0x1800ba02c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180029b63`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180029b63`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180029878`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180029878`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002996c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002996c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18002982c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180029849`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18002982c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180029849`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029909`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002997f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002998f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800299cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029909`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002997f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002998f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800299cc`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180029811`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180029811`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,RegistryMapDetails::RegistryNameHashFunction,RegistryMapDetails::RegistryNameEqualityPredicate,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::Insert(
        __int64 a1,
        HSTRING a2,
        HSTRING a3,
        _BYTE *a4)
{
  _BYTE *v4; // r14
  HSTRING v6; // r15
  HRESULT v8; // edi
  HRESULT v9; // eax
  HSTRING v10; // rbx
  _DWORD *v11; // r13
  unsigned int v12; // eax
  __int64 v13; // r14
  _DWORD *v14; // r12
  unsigned int v15; // r15d
  __int64 i; // r14
  _DWORD *v18; // rax
  _DWORD *v19; // rdi
  void *v20; // rcx
  unsigned int v21; // eax
  unsigned int v22; // ecx
  __int64 v23; // r14
  __int64 j; // r14
  unsigned __int64 v25; // r14
  unsigned __int64 v26; // rax
  void *v27; // rax
  unsigned __int64 v28; // rax
  unsigned __int64 v29; // kr00_8
  _QWORD *v30; // rax
  __int64 v31; // rcx
  int v32; // r8d
  _QWORD *k; // rdx
  __int64 v34; // r14
  unsigned int v35; // eax
  unsigned int v36; // [rsp+30h] [rbp-20h]
  HSTRING newString; // [rsp+38h] [rbp-18h] BYREF
  HSTRING string[2]; // [rsp+40h] [rbp-10h] BYREF
  unsigned int v39; // [rsp+90h] [rbp+40h] BYREF
  HSTRING v40; // [rsp+98h] [rbp+48h]
  _BYTE *v41; // [rsp+A8h] [rbp+58h]

  v41 = a4;
  v40 = a2;
  *a4 = 0;
  v4 = a4;
  v6 = a2;
  if ( !*(_BYTE *)(a1 + 152) )
    RoOriginateError(2147549183LL, 0);
  newString = 0;
  v8 = WindowsDuplicateString(v6, &newString);
  if ( v8 >= 0 )
  {
    v9 = WindowsDuplicateString(a3, string);
    v10 = 0;
    v8 = v9;
    if ( v9 < 0 )
    {
      string[0] = 0;
LABEL_20:
      WindowsDeleteString(v10);
      WindowsDeleteString(string[0]);
      if ( v8 >= 0 )
        v8 = Windows::Foundation::Collections::Internal::HashMapOptions<_GUID,OSIntegration::DEH::ComProxyStubRegistration *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<_GUID>,0,0,0>::RaiseEvent(
               (unsigned __int8)v41,
               *(unsigned __int8 *)(a1 + 153),
               a1,
               *v4 != 0 ? 3 : 1,
               v6);
      goto LABEL_22;
    }
    v11 = (_DWORD *)(a1 + 136);
    if ( *(_DWORD *)(a1 + 128) == 1 )
    {
      if ( !*v11 )
        *v11 = -268435456;
    }
    else
    {
      AcquireSRWLockExclusive((PSRWLOCK)(a1 + 136));
    }
    XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(&v39, *(unsigned __int8 *)(a1 + 154), a1 + 156);
    if ( **(int **)(a1 + 144) > 1 )
    {
      v18 = operator new(4u, (const struct std::nothrow_t *)&std::nothrow);
      v19 = v18;
      if ( v18 )
      {
        *v18 = 1;
        v20 = *(void **)(a1 + 144);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v20, 0xFFFFFFFF) == 1 )
          operator delete(v20, (const struct std::nothrow_t *)4);
        *(_QWORD *)(a1 + 144) = v19;
      }
    }
    v12 = HashRegistryName(newString);
    v13 = *(_QWORD *)(a1 + 48);
    v14 = (_DWORD *)(a1 + 64);
    v15 = v12;
    if ( v13 )
    {
      for ( i = *(_QWORD *)(v13 + 8LL * (v12 % *v14)); i; i = *(_QWORD *)(i + 16) )
      {
        if ( *(_DWORD *)(i + 24) == v15 && RegistryNamesAreEqual(*(HSTRING *)i, newString) )
        {
          v10 = *(HSTRING *)(i + 8);
          WindowsDeleteString(0);
          v8 = 0;
          *(HSTRING *)(i + 8) = string[0];
          v4 = v41;
          string[0] = 0;
          *v41 = 1;
          goto LABEL_17;
        }
      }
    }
    if ( *(_QWORD *)(a1 + 56) == 0x7FFFFFFF )
    {
      v8 = -2147024882;
      goto LABEL_16;
    }
    v21 = HashRegistryName(newString);
    v39 = v21;
    v22 = v21;
    v23 = *(_QWORD *)(a1 + 48);
    v36 = v21 % *v14;
    if ( v23 )
    {
      for ( j = *(_QWORD *)(v23 + 8LL * (v21 % *v14)); j; j = *(_QWORD *)(j + 16) )
      {
        if ( *(_DWORD *)(j + 24) == v22 )
        {
          if ( RegistryNamesAreEqual(*(HSTRING *)j, newString) )
          {
            *(HSTRING *)(j + 8) = string[0];
            goto LABEL_15;
          }
          v22 = v39;
        }
      }
    }
    if ( !*(_QWORD *)(a1 + 48) )
    {
      v25 = (unsigned int)*v14;
      v26 = 8 * v25;
      if ( !is_mul_ok(v25, 8u) )
        v26 = -1;
      v27 = operator new[](v26, (const struct std::nothrow_t *)&std::nothrow);
      *(_QWORD *)(a1 + 48) = v27;
      if ( !v27 )
      {
        v8 = -2147024882;
        goto LABEL_16;
      }
      if ( (unsigned int)v25 > 0x1FFFFFFF )
      {
        v8 = -2147418113;
        goto LABEL_16;
      }
      memset_0(v27, 0, 8 * v25);
      *v14 = v25;
      XWinRT::XHashMap<HSTRING__ *,OSIntegration::DEH::IComTypeLibRegistration *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,OSIntegration::DEH::ComTypeLibRegistration *,RegistryMapDetails::RegistryNameHashFunction,RegistryMapDetails::RegistryNameEqualityPredicate,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<OSIntegration::DEH::ComTypeLibRegistration *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,OSIntegration::DEH::ComTypeLibRegistration *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<OSIntegration::DEH::IComTypeLibRegistration *>>::UpdateRehashThresholds(a1 + 40);
    }
    if ( !*(_QWORD *)(a1 + 112) )
    {
      v29 = *(unsigned int *)(a1 + 100);
      v28 = 32 * v29;
      string[1] = 0;
      if ( !is_mul_ok(v29, 0x20u) || v28 + 8 < v28 || (v30 = malloc(v28 + 8)) == 0 )
      {
        v8 = -2147024882;
        goto LABEL_16;
      }
      v31 = *(_QWORD *)(a1 + 104);
      *(_QWORD *)(a1 + 104) = v30;
      v32 = *(_DWORD *)(a1 + 100) - 1;
      *v30 = v31;
      for ( k = &v30[4 * (unsigned int)v32 + 1]; v32 >= 0; --v32 )
      {
        k[2] = *(_QWORD *)(a1 + 112);
        *(_QWORD *)(a1 + 112) = k;
        k -= 4;
      }
    }
    v34 = *(_QWORD *)(a1 + 112);
    if ( v34 )
    {
      *(_QWORD *)(a1 + 112) = *(_QWORD *)(v34 + 16);
      *(_QWORD *)v34 = newString;
      *(_DWORD *)(v34 + 24) = v39;
      ++*(_QWORD *)(a1 + 56);
      *(_QWORD *)(v34 + 16) = *(_QWORD *)(*(_QWORD *)(a1 + 48) + 8LL * v36);
      *(_QWORD *)(*(_QWORD *)(a1 + 48) + 8LL * v36) = v34;
      if ( *(_QWORD *)(a1 + 56) <= *(_QWORD *)(a1 + 80)
        || *(_DWORD *)(a1 + 96)
        || (v35 = XWinRT::XHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<IInspectable *>>::PickSize(a1 + 40),
            v8 = XWinRT::XHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,RegistryMapDetails::RegistryNameHashFunction,RegistryMapDetails::RegistryNameEqualityPredicate,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<HSTRING__ *>>::Rehash(
                   a1 + 40,
                   v35),
            v8 >= 0) )
      {
        *(HSTRING *)(v34 + 8) = string[0];
LABEL_15:
        v8 = 0;
        newString = 0;
        string[0] = 0;
      }
    }
    else
    {
      v8 = -2147418113;
    }
LABEL_16:
    v4 = v41;
LABEL_17:
    if ( *(_DWORD *)(a1 + 128) == 1 )
      *v11 += 0x10000000;
    else
      ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 136));
    v6 = v40;
    goto LABEL_20;
  }
LABEL_22:
  WindowsDeleteString(newString);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800297d0  mov     [rsp-38h+arg_10], rbx
0x1800297d5  mov     [rsp-38h+arg_18], r9
0x1800297da  mov     [rsp-38h+arg_8], rdx
0x1800297df  push    rbp
0x1800297e0  push    rsi
0x1800297e1  push    rdi
0x1800297e2  push    r12
0x1800297e4  push    r13
0x1800297e6  push    r14
0x1800297e8  push    r15
0x1800297ea  mov     rbp, rsp
0x1800297ed  sub     rsp, 50h
0x1800297f1  mov     byte ptr [r9], 0
0x1800297f5  mov     r14, r9
0x1800297f8  cmp     byte ptr [rcx+98h], 0
0x1800297ff  mov     rbx, r8
0x180029802  mov     r15, rdx
0x180029805  mov     rsi, rcx
0x180029808  jnz     short loc_18002981D
0x18002980a  xor     edx, edx
0x18002980c  mov     ecx, 8000FFFFh
0x180029811  call    cs:__imp_RoOriginateError
0x180029818  nop     dword ptr [rax+rax+00h]
0x18002981d  lea     rdx, [rbp+newString]; newString
0x180029821  mov     [rbp+newString], 0
0x180029829  mov     rcx, r15; string
0x18002982c  call    cs:__imp_WindowsDuplicateString
0x180029833  nop     dword ptr [rax+rax+00h]
0x180029838  mov     edi, eax
0x18002983a  test    eax, eax
0x18002983c  js      loc_1800299C8
0x180029842  lea     rdx, [rbp+string]; newString
0x180029846  mov     rcx, rbx; string
0x180029849  call    cs:__imp_WindowsDuplicateString
0x180029850  nop     dword ptr [rax+rax+00h]
0x180029855  xor     ebx, ebx
0x180029857  mov     edi, eax
0x180029859  test    eax, eax
0x18002985b  js      loc_180029C44
0x180029861  cmp     dword ptr [rsi+80h], 1
0x180029868  lea     r13, [rsi+88h]
0x18002986f  jz      loc_180029C2D
0x180029875  mov     rcx, r13; SRWLock
0x180029878  call    cs:__imp_AcquireSRWLockExclusive
0x18002987f  nop     dword ptr [rax+rax+00h]
0x180029884  movzx   edx, byte ptr [rsi+9Ah]
0x18002988b  lea     r8, [rsi+9Ch]
0x180029892  lea     rcx, [rbp+arg_0]
0x180029896  call    ??0?$ReentrancyGuard@$0A@@detail@XWinRT@@QEAA@ZZ; XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(...)
0x18002989b  mov     rax, [rsi+90h]
0x1800298a2  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800298a6  mov     ecx, [rax]
0x1800298a8  cmp     ecx, 1
0x1800298ab  jg      loc_180029A20
0x1800298b1  mov     rcx, [rbp+newString]; HSTRING
0x1800298b5  lea     rdi, [rsi+28h]
0x1800298b9  call    ?HashRegistryName@@YAIPEAUHSTRING__@@@Z; HashRegistryName(HSTRING__ *)
0x1800298be  mov     r14, [rdi+8]
0x1800298c2  lea     r12, [rdi+18h]
0x1800298c6  mov     r15d, eax
0x1800298c9  test    r14, r14
0x1800298cc  jz      loc_1800299F3
0x1800298d2  xor     edx, edx
0x1800298d4  div     dword ptr [r12]
0x1800298d8  mov     r14, [r14+rdx*8]
0x1800298dc  test    r14, r14
0x1800298df  jz      loc_1800299F3
0x1800298e5  cmp     [r14+18h], r15d
0x1800298e9  jnz     loc_180029A0A
0x1800298ef  mov     rdx, [rbp+newString]; HSTRING
0x1800298f3  mov     rcx, [r14]; HSTRING
0x1800298f6  call    ?RegistryNamesAreEqual@@YA_NPEAUHSTRING__@@0@Z; RegistryNamesAreEqual(HSTRING__ *,HSTRING__ *)
0x1800298fb  test    al, al
0x1800298fd  jz      loc_180029A0A
0x180029903  mov     rbx, [r14+8]
0x180029907  xor     ecx, ecx; string
0x180029909  call    cs:__imp_WindowsDeleteString
0x180029910  nop     dword ptr [rax+rax+00h]
0x180029915  mov     rax, [rbp+string]
0x180029919  xor     edi, edi
0x18002991b  mov     [r14+8], rax
0x18002991f  mov     r14, [rbp+arg_18]
0x180029923  mov     [rbp+string], 0
0x18002992b  mov     byte ptr [r14], 1
0x18002992f  jmp     short loc_18002995C
0x180029931  mov     edi, 8007000Eh
0x180029936  test    edi, edi
0x180029938  js      loc_180029B08
0x18002993e  mov     rax, [rbp+string]
0x180029942  mov     [r15+8], rax
0x180029946  xor     edi, edi
0x180029948  mov     [rbp+newString], 0
0x180029950  mov     [rbp+string], 0
0x180029958  mov     r14, [rbp+arg_18]
0x18002995c  cmp     dword ptr [rsi+80h], 1
0x180029963  jz      loc_180029A13
0x180029969  mov     rcx, r13; SRWLock
0x18002996c  call    cs:__imp_ReleaseSRWLockExclusive
0x180029973  nop     dword ptr [rax+rax+00h]
0x180029978  mov     r15, [rbp+arg_8]
0x18002997c  mov     rcx, rbx; string
0x18002997f  call    cs:__imp_WindowsDeleteString
0x180029986  nop     dword ptr [rax+rax+00h]
0x18002998b  mov     rcx, [rbp+string]; string
0x18002998f  call    cs:__imp_WindowsDeleteString
0x180029996  nop     dword ptr [rax+rax+00h]
0x18002999b  test    edi, edi
0x18002999d  js      short loc_1800299C8
0x18002999f  mov     al, [r14]
0x1800299a2  mov     r8, rsi
0x1800299a5  movzx   edx, byte ptr [rsi+99h]
0x1800299ac  neg     al
0x1800299ae  movzx   ecx, byte ptr [rbp+arg_18]
0x1800299b2  sbb     r9d, r9d
0x1800299b5  mov     [rsp+50h+var_30], r15
0x1800299ba  and     r9d, 2
0x1800299be  inc     r9d
0x1800299c1  call    ?RaiseEvent@?$HashMapOptions@U_GUID@@PEAVComProxyStubRegistration@DEH@OSIntegration@@U?$DefaultLifetimeTraits@U_GUID@@@Internal@Collections@Foundation@Windows@@$0A@$0A@$0A@@Internal@Collections@Foundation@Windows@@SAJZZ; Windows::Foundation::Collections::Internal::HashMapOptions<_GUID,OSIntegration::DEH::ComProxyStubRegistration *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<_GUID>,0,0,0>::RaiseEvent(...)
0x1800299c6  mov     edi, eax
0x1800299c8  mov     rcx, [rbp+newString]; string
0x1800299cc  call    cs:__imp_WindowsDeleteString
0x1800299d3  nop     dword ptr [rax+rax+00h]
0x1800299d8  mov     rbx, [rsp+50h+arg_10]
0x1800299e0  mov     eax, edi
0x1800299e2  add     rsp, 50h
0x1800299e6  pop     r15
0x1800299e8  pop     r14
0x1800299ea  pop     r13
0x1800299ec  pop     r12
0x1800299ee  pop     rdi
0x1800299ef  pop     rsi
0x1800299f0  pop     rbp
0x1800299f1  retn
0x1800299f3  cmp     qword ptr [rsi+38h], 7FFFFFFFh
0x1800299fb  mov     r14, r12
0x1800299fe  jnz     short loc_180029A6F
0x180029a00  mov     edi, 8007000Eh
0x180029a05  jmp     loc_180029958
0x180029a0a  mov     r14, [r14+10h]
0x180029a0e  jmp     loc_1800298DC
0x180029a13  add     dword ptr [r13+0], 10000000h
0x180029a1b  jmp     loc_180029978
0x180029a20  mov     r14d, 4
0x180029a26  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180029a2d  mov     ecx, r14d; unsigned __int64
0x180029a30  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180029a35  mov     rdi, rax
0x180029a38  test    rax, rax
0x180029a3b  jz      loc_1800298B1
0x180029a41  mov     dword ptr [rax], 1
0x180029a47  mov     r8d, r15d
0x180029a4a  mov     rcx, [rsi+90h]; void *
0x180029a51  lock xadd [rcx], r8d
0x180029a56  add     r8d, r15d
0x180029a59  jnz     short loc_180029A63
0x180029a5b  mov     edx, r14d; struct std::nothrow_t *
0x180029a5e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180029a63  mov     [rsi+90h], rdi
0x180029a6a  jmp     loc_1800298B1
0x180029a6f  mov     rcx, [rbp+newString]; HSTRING
0x180029a73  call    ?HashRegistryName@@YAIPEAUHSTRING__@@@Z; HashRegistryName(HSTRING__ *)
0x180029a78  xor     edx, edx
0x180029a7a  mov     [rbp+arg_0], eax
0x180029a7d  mov     ecx, eax
0x180029a7f  div     dword ptr [r14]
0x180029a82  mov     r14, [rdi+8]
0x180029a86  mov     [rbp+var_20], edx
0x180029a89  test    r14, r14
0x180029a8c  jz      short loc_180029AC2
0x180029a8e  mov     r14, [r14+rdx*8]
0x180029a92  test    r14, r14
0x180029a95  jz      short loc_180029AC2
0x180029a97  cmp     [r14+18h], ecx
0x180029a9b  jnz     loc_180029C54
0x180029aa1  mov     rdx, [rbp+newString]; HSTRING
0x180029aa5  mov     rcx, [r14]; HSTRING
0x180029aa8  call    ?RegistryNamesAreEqual@@YA_NPEAUHSTRING__@@0@Z; RegistryNamesAreEqual(HSTRING__ *,HSTRING__ *)
0x180029aad  test    al, al
0x180029aaf  jz      loc_180029C51
0x180029ab5  mov     rax, [rbp+string]
0x180029ab9  mov     [r14+8], rax
0x180029abd  jmp     loc_180029946
0x180029ac2  xor     r15d, r15d
0x180029ac5  cmp     [rdi+8], r15
0x180029ac9  jnz     short loc_180029B33
0x180029acb  mov     r14d, [r12]
0x180029acf  lea     rcx, [r15-1]
0x180029ad3  lea     eax, [r15+8]
0x180029ad7  mul     r14
0x180029ada  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180029ae1  cmovb   rax, rcx
0x180029ae5  mov     rcx, rax; unsigned __int64
0x180029ae8  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180029aed  mov     [rdi+8], rax
0x180029af1  test    rax, rax
0x180029af4  jz      loc_180029C5D
0x180029afa  cmp     r14d, 1FFFFFFFh
0x180029b01  jbe     short loc_180029B15
0x180029b03  mov     edi, 8000FFFFh
0x180029b08  test    edi, edi
0x180029b0a  jns     loc_180029948
0x180029b10  jmp     loc_180029958
0x180029b15  lea     r8, ds:0[r14*8]; Size
0x180029b1d  xor     edx, edx; Val
0x180029b1f  mov     rcx, rax; void *
0x180029b22  call    memset_0
0x180029b27  mov     rcx, rdi
0x180029b2a  mov     [r12], r14d
0x180029b2e  call    ?UpdateRehashThresholds@?$XHashMap@PEAUHSTRING__@@PEAUIComTypeLibRegistration@DEH@OSIntegration@@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAVComTypeLibRegistration@DEH@OSIntegration@@URegistryNameHashFunction@RegistryMapDetails@@URegistryNameEqualityPredicate@6@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAVComTypeLibRegistration@DEH@OSIntegration@@@9Collections@Foundation@Windows@@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAVComTypeLibRegistration@DEH@OSIntegration@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@9Collections@Foundation@Windows@@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@PEAUIComTypeLibRegistration@DEH@OSIntegration@@@XWinRT@@@XWinRT@@AEAAXXZ; XWinRT::XHashMap<HSTRING__ *,OSIntegration::DEH::IComTypeLibRegistration *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,OSIntegration::DEH::ComTypeLibRegistration *,RegistryMapDetails::RegistryNameHashFunction,RegistryMapDetails::RegistryNameEqualityPredicate,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<OSIntegration::DEH::ComTypeLibRegistration *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,OSIntegration::DEH::ComTypeLibRegistration *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<OSIntegration::DEH::IComTypeLibRegistration *>>::UpdateRehashThresholds(void)
0x180029b33  cmp     qword ptr [rdi+48h], 0
0x180029b38  jnz     short loc_180029BB3
0x180029b3a  mov     ecx, [rdi+3Ch]
0x180029b3d  mov     eax, 20h ; ' '
0x180029b42  mul     rcx
0x180029b45  mov     [rbp+var_8], 0
0x180029b4d  test    rdx, rdx
0x180029b50  jnz     loc_180029931
0x180029b56  lea     rcx, [rax+8]; Size
0x180029b5a  cmp     rcx, rax
0x180029b5d  jb      loc_180029931
0x180029b63  call    cs:__imp_malloc
0x180029b6a  nop     dword ptr [rax+rax+00h]
0x180029b6f  test    rax, rax
0x180029b72  jz      loc_180029931
0x180029b78  mov     rcx, [rdi+40h]
0x180029b7c  mov     [rdi+40h], rax
0x180029b80  mov     r8d, [rdi+3Ch]
0x180029b84  dec     r8d
0x180029b87  mov     [rax], rcx
0x180029b8a  mov     edx, r8d
0x180029b8d  shl     rdx, 5
0x180029b91  add     rdx, 8
0x180029b95  add     rdx, rax
0x180029b98  test    r8d, r8d
0x180029b9b  js      short loc_180029BB3
0x180029b9d  mov     rax, [rdi+48h]
0x180029ba1  mov     [rdx+10h], rax
0x180029ba5  mov     [rdi+48h], rdx
0x180029ba9  sub     rdx, 20h ; ' '
0x180029bad  sub     r8d, 1
0x180029bb1  jns     short loc_180029B9D
0x180029bb3  mov     r14, [rdi+48h]
0x180029bb7  test    r14, r14
0x180029bba  jz      short loc_180029C00
0x180029bbc  mov     rax, [r14+10h]
0x180029bc0  mov     r8d, [rbp+var_20]
0x180029bc4  mov     [rdi+48h], rax
0x180029bc8  mov     rax, [rbp+newString]
0x180029bcc  mov     [r14], rax
0x180029bcf  mov     eax, [rbp+arg_0]
0x180029bd2  mov     [r14+18h], eax
0x180029bd6  inc     qword ptr [rdi+10h]
0x180029bda  mov     rax, [rdi+8]
0x180029bde  mov     rdx, [rax+r8*8]
0x180029be2  mov     [r14+10h], rdx
0x180029be6  mov     rax, [rdi+8]
0x180029bea  mov     [rax+r8*8], r14
0x180029bee  mov     rdx, [rdi+10h]
0x180029bf2  cmp     rdx, [rdi+28h]
0x180029bf6  ja      short loc_180029C0A
0x180029bf8  mov     r15, r14
0x180029bfb  jmp     loc_18002993E
0x180029c00  mov     edi, 8000FFFFh
0x180029c05  jmp     loc_180029936
0x180029c0a  cmp     dword ptr [rdi+38h], 0
0x180029c0e  jnz     short loc_180029BF8
0x180029c10  mov     rcx, rdi
0x180029c13  call    ?PickSize@?$XHashMap@PEAUHSTRING__@@PEAUIInspectable@@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@4567@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@PEAUIInspectable@@@XWinRT@@@XWinRT@@AEBAI_K@Z; XWinRT::XHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<IInspectable *>>::PickSize(unsigned __int64)
0x180029c18  mov     edx, eax
0x180029c1a  mov     rcx, rdi
0x180029c1d  call    ?Rehash@?$XHashMap@PEAUHSTRING__@@PEAU1@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAU1@URegistryNameHashFunction@RegistryMapDetails@@URegistryNameEqualityPredicate@3@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U56789@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@6789@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@PEAUHSTRING__@@@XWinRT@@@XWinRT@@QEAAJI@Z; XWinRT::XHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,RegistryMapDetails::RegistryNameHashFunction,RegistryMapDetails::RegistryNameEqualityPredicate,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<HSTRING__ *>>::Rehash(uint)
0x180029c22  mov     edi, eax
0x180029c24  test    eax, eax
0x180029c26  jns     short loc_180029BF8
0x180029c28  jmp     loc_180029936
0x180029c2d  cmp     [r13+0], ebx
0x180029c31  jnz     loc_180029884
0x180029c37  mov     dword ptr [r13+0], 0F0000000h
0x180029c3f  jmp     loc_180029884
0x180029c44  mov     [rbp+string], 0
0x180029c4c  jmp     loc_18002997C
0x180029c51  mov     ecx, [rbp+arg_0]
0x180029c54  mov     r14, [r14+10h]
0x180029c58  jmp     loc_180029A92
0x180029c5d  mov     edi, 8007000Eh
0x180029c62  jmp     loc_180029B08
```
