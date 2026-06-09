# tip2::details::shared_data<1,0,0>::start(void)

- ea: `0x18001b2b8`
- end: `0x18001b44e`
- name: `?start@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ`
- size: `406`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task`

## callers

- `0x18001b4bc`

## callees

- `0x180008274`
- `0x1800084c8`
- `0x180009f30`
- `0x18000c8a4`
- `0x18000cb20`
- `0x180012408`
- `0x18001b0e4`
- `0x18001b2b8`
- `0x18001ba9c`
- `0x18001bc7c`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001b391`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001b391`

## string_xrefs

- `0x18001b38a`: `TestCreate`

## pseudocode

```c
_OWORD *__fastcall tip2::details::shared_data<1,0,0>::start(__int64 a1, _OWORD *a2)
{
  __int64 v4; // r8
  _OWORD *v5; // rsi
  __int64 v6; // rdi
  unsigned int v7; // r14d
  char v8; // r12
  unsigned int v9; // r13d
  FARPROC ProcAddress; // rax
  HMODULE KernelBaseModuleHandle; // rax
  __int64 v12; // r14
  __int64 v13; // rdi
  _BYTE v15[8]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v16[8]; // [rsp+48h] [rbp-B8h] BYREF
  void *v17; // [rsp+50h] [rbp-B0h] BYREF
  char v18; // [rsp+58h] [rbp-A8h]
  int v19; // [rsp+59h] [rbp-A7h] BYREF
  char v20; // [rsp+5Dh] [rbp-A3h]
  char v21; // [rsp+5Eh] [rbp-A2h] BYREF
  char v22; // [rsp+859h] [rbp+759h] BYREF
  int *v23; // [rsp+860h] [rbp+760h]
  char *v24; // [rsp+868h] [rbp+768h]
  char *v25; // [rsp+870h] [rbp+770h]

  wil::EnterCriticalSection(v16, a1 + 192);
  v17 = 0;
  v18 = 0;
  v23 = &v19;
  v25 = &v22;
  v19 = -2143256512;
  v20 = 0;
  v24 = &v21;
  v5 = (_OWORD *)(a1 + 144);
  if ( (*(_DWORD *)(a1 + 64) & 0x800) != 0 )
    v6 = tip2::details::shared_data<1,0,0>::serialize_data(a1, &v17, 1);
  else
    v6 = 0;
  v7 = *(_DWORD *)(a1 + 20);
  v8 = *(_BYTE *)(a1 + 32);
  v9 = *(_DWORD *)(a1 + 16);
  ProcAddress = (FARPROC)`TestCreate'::`2'::s_pfnTestCreate;
  if ( `TestCreate'::`2'::s_pfnTestCreate
    || (KernelBaseModuleHandle = (HMODULE)tip_details_GetKernelBaseModuleHandle(),
        ProcAddress = GetProcAddress(KernelBaseModuleHandle, "TestCreate"),
        (`TestCreate'::`2'::s_pfnTestCreate = (__int64)ProcAddress) != 0) )
  {
    LOBYTE(v4) = v8;
    v12 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64, _QWORD, __int64, __int64))ProcAddress)(
            v9,
            0,
            v4,
            v7,
            v6,
            a1 + 144);
  }
  else
  {
    *v5 = 0;
    v12 = 0;
  }
  v13 = *(_QWORD *)(a1 + 240);
  if ( v13 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)v15);
    TestClose(v13);
    wil::last_error_context::~last_error_context((wil::last_error_context *)v15);
  }
  *(_QWORD *)(a1 + 240) = v12;
  *(_DWORD *)(a1 + 184) = 1;
  *a2 = *v5;
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v17);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(v16);
  return a2;
}

```

## disassembly

```asm
0x18001b2b8  mov     [rsp-8+arg_10], rbx
0x18001b2bd  push    rbp
0x18001b2be  push    rsi
0x18001b2bf  push    rdi
0x18001b2c0  push    r12
0x18001b2c2  push    r13
0x18001b2c4  push    r14
0x18001b2c6  push    r15
0x18001b2c8  lea     rbp, [rsp-790h]
0x18001b2d0  sub     rsp, 890h
0x18001b2d7  mov     rax, cs:__security_cookie
0x18001b2de  xor     rax, rsp
0x18001b2e1  mov     [rbp+7C0h+var_40], rax
0x18001b2e8  mov     r15, rdx
0x18001b2eb  mov     rbx, rcx
0x18001b2ee  lea     rdx, [rcx+0C0h]
0x18001b2f5  lea     rcx, [rsp+8C0h+var_878]
0x18001b2fa  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x18001b2ff  mov     [rsp+8C0h+var_870], 0
0x18001b308  mov     [rsp+8C0h+var_868], 0
0x18001b30d  lea     rax, [rsp+8C0h+var_867]
0x18001b312  mov     [rbp+7C0h+var_60], rax
0x18001b319  lea     rax, [rbp+7C0h+var_67]
0x18001b320  mov     [rbp+7C0h+var_50], rax
0x18001b327  mov     [rsp+8C0h+var_867], 80408040h
0x18001b32f  mov     [rsp+8C0h+var_863], 0
0x18001b334  lea     rax, [rsp+8C0h+var_862]
0x18001b339  mov     [rbp+7C0h+var_58], rax
0x18001b340  lea     rsi, [rbx+90h]
0x18001b347  test    dword ptr [rbx+40h], 800h
0x18001b34e  jz      short loc_18001B368
0x18001b350  mov     r8d, 1
0x18001b356  lea     rdx, [rsp+8C0h+var_870]
0x18001b35b  mov     rcx, rbx
0x18001b35e  call    ?serialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<1,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x18001b363  mov     rdi, rax
0x18001b366  jmp     short loc_18001B36A
0x18001b368  xor     edi, edi
0x18001b36a  mov     r14d, [rbx+14h]
0x18001b36e  mov     r12b, [rbx+20h]
0x18001b372  mov     r13d, [rbx+10h]
0x18001b376  mov     rax, cs:?s_pfnTestCreate@?1??TestCreate@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@W4TestProperties@@PEBDPEAU_GUID@@@ZEA; HTIPTEST__ * (*`TestCreate'::`2'::s_pfnTestCreate)(uint,TestRetrievalOptions,TestStorage,TestProperties,char const *,_GUID *)
0x18001b37d  test    rax, rax
0x18001b380  jnz     short loc_18001B3AF
0x18001b382  call    tip_details_GetKernelBaseModuleHandle
0x18001b387  mov     rcx, rax; hModule
0x18001b38a  lea     rdx, aTestcreate; "TestCreate"
0x18001b391  call    cs:__imp_GetProcAddress
0x18001b397  mov     cs:?s_pfnTestCreate@?1??TestCreate@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@W4TestProperties@@PEBDPEAU_GUID@@@ZEA, rax; HTIPTEST__ * (*`TestCreate'::`2'::s_pfnTestCreate)(uint,TestRetrievalOptions,TestStorage,TestProperties,char const *,_GUID *)
0x18001b39e  test    rax, rax
0x18001b3a1  jnz     short loc_18001B3AF
0x18001b3a3  xorps   xmm0, xmm0
0x18001b3a6  movdqu  xmmword ptr [rsi], xmm0
0x18001b3aa  xor     r14d, r14d
0x18001b3ad  jmp     short loc_18001B3CC
0x18001b3af  mov     [rsp+8C0h+var_898], rsi
0x18001b3b4  mov     [rsp+8C0h+var_8A0], rdi
0x18001b3b9  mov     r9d, r14d
0x18001b3bc  mov     r8b, r12b
0x18001b3bf  xor     edx, edx
0x18001b3c1  mov     ecx, r13d
0x18001b3c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b3c9  mov     r14, rax
0x18001b3cc  mov     rdi, [rbx+0F0h]
0x18001b3d3  test    rdi, rdi
0x18001b3d6  jz      short loc_18001B3F4
0x18001b3d8  lea     rcx, [rsp+8C0h+var_880]; this
0x18001b3dd  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001b3e2  mov     rcx, rdi
0x18001b3e5  call    TestClose
0x18001b3ea  lea     rcx, [rsp+8C0h+var_880]; this
0x18001b3ef  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001b3f4  mov     [rbx+0F0h], r14
0x18001b3fb  mov     dword ptr [rbx+0B8h], 1
0x18001b405  movups  xmm0, xmmword ptr [rsi]
0x18001b408  movdqu  xmmword ptr [r15], xmm0
0x18001b40d  lea     rcx, [rsp+8C0h+var_870]
0x18001b412  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001b417  lea     rcx, [rsp+8C0h+var_878]
0x18001b41c  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18001b421  mov     rax, r15
0x18001b424  mov     rcx, [rbp+7C0h+var_40]
0x18001b42b  xor     rcx, rsp; StackCookie
0x18001b42e  call    __security_check_cookie
0x18001b433  mov     rbx, [rsp+8C0h+arg_10]
0x18001b43b  add     rsp, 890h
0x18001b442  pop     r15
0x18001b444  pop     r14
0x18001b446  pop     r13
0x18001b448  pop     r12
0x18001b44a  pop     rdi
0x18001b44b  pop     rsi
0x18001b44c  pop     rbp
0x18001b44d  retn
```
