# HandlerAsset::RuntimeClassInitialize(IHandlerAsset *)

- ea: `0x180048d08`
- end: `0x180048f05`
- name: `?RuntimeClassInitialize@HandlerAsset@@QEAAJPEAUIHandlerAsset@@@Z`
- size: `509`
- prototype: `int(HandlerAsset *__hidden this, struct IHandlerAsset *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180048b6c`

## callees

- `0x18000de40`
- `0x180011618`
- `0x18001bf30`
- `0x180048d08`
- `0x180118010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048de2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048df2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048e02`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048e40`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048e4a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048e74`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048de2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048df2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048e02`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048e40`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048e4a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048e74`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall HandlerAsset::RuntimeClassInitialize(HandlerAsset *this, struct IHandlerAsset *a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  int v6; // eax
  int v7; // eax
  int v8; // eax
  int v9; // eax
  int v10; // eax
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+28h]
  LPVOID v14; // [rsp+58h] [rbp+38h] BYREF
  LPVOID v15; // [rsp+60h] [rbp+40h] BYREF
  LPVOID pv; // [rsp+68h] [rbp+48h] BYREF

  v15 = 0;
  v4 = (*(__int64 (__fastcall **)(struct IHandlerAsset *, LPVOID *))(*(_QWORD *)a2 + 40LL))(a2, &v15);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x21,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\handlerassets.cpp",
      (const char *)(unsigned int)v4,
      savedregs);
LABEL_17:
    if ( v15 )
      CoTaskMemFree(v15);
    return v5;
  }
  v6 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
         (char *)this + 48,
         v15,
         -1);
  v5 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x22,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\handlerassets.cpp",
      (const char *)(unsigned int)v6,
      savedregs);
LABEL_27:
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v15);
    return v5;
  }
  v14 = 0;
  v7 = (*(__int64 (__fastcall **)(struct IHandlerAsset *, LPVOID *))(*(_QWORD *)a2 + 24LL))(a2, &v14);
  v5 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x25,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\handlerassets.cpp",
      (const char *)(unsigned int)v7,
      savedregs);
LABEL_26:
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v14);
    goto LABEL_27;
  }
  v8 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
         (char *)this + 72,
         v14,
         -1);
  v5 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x26,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\handlerassets.cpp",
      (const char *)(unsigned int)v8,
      savedregs);
LABEL_15:
    if ( v14 )
      CoTaskMemFree(v14);
    goto LABEL_17;
  }
  pv = 0;
  v9 = (*(__int64 (__fastcall **)(struct IHandlerAsset *, LPVOID *))(*(_QWORD *)a2 + 32LL))(a2, &pv);
  v5 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x29,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\handlerassets.cpp",
      (const char *)(unsigned int)v9,
      savedregs);
    if ( pv )
      CoTaskMemFree(pv);
    goto LABEL_15;
  }
  v10 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
          (char *)this + 96,
          pv,
          -1);
  v5 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2A,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\handlerassets.cpp",
      (const char *)(unsigned int)v10,
      savedregs);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pv);
    goto LABEL_26;
  }
  if ( pv )
    CoTaskMemFree(pv);
  if ( v14 )
    CoTaskMemFree(v14);
  if ( v15 )
    CoTaskMemFree(v15);
  return 0;
}

```

## disassembly

```asm
0x180048d08  push    rbp
0x180048d0a  push    rbx
0x180048d0b  push    rsi
0x180048d0c  push    rdi
0x180048d0d  push    r15; int
0x180048d0f  mov     rbp, rsp
0x180048d12  sub     rsp, 20h
0x180048d16  mov     rdi, rdx
0x180048d19  mov     rsi, rcx
0x180048d1c  mov     [rbp+arg_10], 0
0x180048d24  mov     rax, [rdx]
0x180048d27  lea     rdx, [rbp+arg_10]
0x180048d2b  mov     rcx, rdi
0x180048d2e  mov     rax, [rax+28h]
0x180048d32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048d37  mov     ebx, eax
0x180048d39  test    eax, eax
0x180048d3b  js      loc_180048E7C
0x180048d41  lea     rcx, [rsi+30h]
0x180048d45  or      r15, 0FFFFFFFFFFFFFFFFh
0x180048d49  mov     r8, r15
0x180048d4c  mov     rdx, [rbp+arg_10]
0x180048d50  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x180048d55  mov     ebx, eax
0x180048d57  test    eax, eax
0x180048d59  js      loc_180048E96
0x180048d5f  mov     [rbp+arg_8], 0
0x180048d67  mov     rax, [rdi]
0x180048d6a  lea     rdx, [rbp+arg_8]
0x180048d6e  mov     rcx, rdi
0x180048d71  mov     rax, [rax+18h]
0x180048d75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048d7a  mov     ebx, eax
0x180048d7c  test    eax, eax
0x180048d7e  js      loc_180048EB0
0x180048d84  lea     rcx, [rsi+48h]
0x180048d88  mov     r8, r15
0x180048d8b  mov     rdx, [rbp+arg_8]
0x180048d8f  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x180048d94  mov     ebx, eax
0x180048d96  test    eax, eax
0x180048d98  js      short loc_180048E15
0x180048d9a  mov     [rbp+pv], 0
0x180048da2  mov     rax, [rdi]
0x180048da5  lea     rdx, [rbp+pv]
0x180048da9  mov     rcx, rdi
0x180048dac  mov     rax, [rax+20h]
0x180048db0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048db5  mov     ebx, eax
0x180048db7  test    eax, eax
0x180048db9  js      loc_180048E52
0x180048dbf  lea     rcx, [rsi+60h]
0x180048dc3  mov     r8, r15
0x180048dc6  mov     rdx, [rbp+pv]
0x180048dca  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x180048dcf  mov     ebx, eax
0x180048dd1  test    eax, eax
0x180048dd3  js      loc_180048ECA
0x180048dd9  mov     rcx, [rbp+pv]; pv
0x180048ddd  test    rcx, rcx
0x180048de0  jz      short loc_180048DE9
0x180048de2  call    cs:__imp_CoTaskMemFree
0x180048de8  nop
0x180048de9  mov     rcx, [rbp+arg_8]; pv
0x180048ded  test    rcx, rcx
0x180048df0  jz      short loc_180048DF9
0x180048df2  call    cs:__imp_CoTaskMemFree
0x180048df8  nop
0x180048df9  mov     rcx, [rbp+arg_10]; pv
0x180048dfd  test    rcx, rcx
0x180048e00  jz      short loc_180048E08
0x180048e02  call    cs:__imp_CoTaskMemFree
0x180048e08  xor     eax, eax
0x180048e0a  add     rsp, 20h
0x180048e0e  pop     r15
0x180048e10  pop     rdi
0x180048e11  pop     rsi
0x180048e12  pop     rbx
0x180048e13  pop     rbp
0x180048e14  retn
0x180048e15  mov     rcx, [rbp+28h]; this
0x180048e19  mov     r9d, ebx; char *
0x180048e1c  lea     r8, aOnecoreuapBase_52; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180048e23  mov     edx, 26h ; '&'; void *
0x180048e28  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048e2d  nop
0x180048e2e  mov     rcx, [rbp+arg_8]; pv
0x180048e32  test    rcx, rcx
0x180048e35  jnz     short loc_180048E4A
0x180048e37  mov     rcx, [rbp+arg_10]; pv
0x180048e3b  test    rcx, rcx
0x180048e3e  jz      short loc_180048E46
0x180048e40  call    cs:__imp_CoTaskMemFree
0x180048e46  mov     eax, ebx
0x180048e48  jmp     short loc_180048E0A
0x180048e4a  call    cs:__imp_CoTaskMemFree
0x180048e50  jmp     short loc_180048E37
0x180048e52  mov     rcx, [rbp+28h]; this
0x180048e56  mov     r9d, ebx; char *
0x180048e59  lea     r8, aOnecoreuapBase_52; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180048e60  mov     edx, 29h ; ')'; void *
0x180048e65  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048e6a  nop
0x180048e6b  mov     rcx, [rbp+pv]; pv
0x180048e6f  test    rcx, rcx
0x180048e72  jz      short loc_180048E2E
0x180048e74  call    cs:__imp_CoTaskMemFree
0x180048e7a  jmp     short loc_180048E2E
0x180048e7c  mov     rcx, [rbp+28h]; this
0x180048e80  mov     r9d, ebx; char *
0x180048e83  lea     r8, aOnecoreuapBase_52; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180048e8a  mov     edx, 21h ; '!'; void *
0x180048e8f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048e94  jmp     short loc_180048E37
0x180048e96  mov     rcx, [rbp+28h]; this
0x180048e9a  mov     r9d, eax; char *
0x180048e9d  lea     r8, aOnecoreuapBase_52; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180048ea4  mov     edx, 22h ; '"'; void *
0x180048ea9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048eae  jmp     short loc_180048EF7
0x180048eb0  mov     rcx, [rbp+28h]; this
0x180048eb4  mov     r9d, eax; char *
0x180048eb7  lea     r8, aOnecoreuapBase_52; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180048ebe  mov     edx, 25h ; '%'; void *
0x180048ec3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048ec8  jmp     short loc_180048EED
0x180048eca  mov     rcx, [rbp+28h]; this
0x180048ece  mov     r9d, eax; char *
0x180048ed1  lea     r8, aOnecoreuapBase_52; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180048ed8  mov     edx, 2Ah ; '*'; void *
0x180048edd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048ee2  nop
0x180048ee3  lea     rcx, [rbp+pv]
0x180048ee7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180048eec  nop
0x180048eed  lea     rcx, [rbp+arg_8]
0x180048ef1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180048ef6  nop
0x180048ef7  lea     rcx, [rbp+arg_10]
0x180048efb  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180048f00  jmp     loc_180048E46
```
