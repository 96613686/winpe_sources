# tip2::details::shared_data<0,0,0>::start(void)

- ea: `0x18002d810`
- end: `0x18002d9c4`
- name: `?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ`
- size: `436`
- prototype: ``
- caller_count: `3`
- callee_count: `12`
- tags: `registry_config, service_task`

## callers

- `0x18002d9cc`
- `0x18002da60`
- `0x18004c13c`

## callees

- `0x180002b20`
- `0x180003cf6`
- `0x18000d84c`
- `0x18000e1c8`
- `0x18000e280`
- `0x18000e9e4`
- `0x180010374`
- `0x18001be70`
- `0x18001d050`
- `0x18001d36c`
- `0x18002d810`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002d906`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002d906`

## string_xrefs

- `0x18002d8ff`: `TestCreate`

## pseudocode

```c
_OWORD *__fastcall tip2::details::shared_data<0,0,0>::start(__int64 a1, _OWORD *a2)
{
  __int64 v4; // rdi
  __int64 v5; // r8
  _OWORD *v6; // r14
  unsigned int v7; // esi
  char v8; // r12
  unsigned int v9; // r13d
  FARPROC ProcAddress; // rax
  HMODULE KernelBaseModuleHandle; // rax
  __int64 v12; // rsi
  __int64 v13; // rdi
  __int64 v15; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v16[8]; // [rsp+48h] [rbp-B8h] BYREF
  void *v17; // [rsp+50h] [rbp-B0h] BYREF
  char v18; // [rsp+58h] [rbp-A8h]
  int v19; // [rsp+59h] [rbp-A7h] BYREF
  char v20; // [rsp+5Dh] [rbp-A3h]
  _BYTE v21[2043]; // [rsp+5Eh] [rbp-A2h] BYREF
  char v22; // [rsp+859h] [rbp+759h] BYREF
  int *v23; // [rsp+860h] [rbp+760h]
  _BYTE *v24; // [rsp+868h] [rbp+768h]
  char *v25; // [rsp+870h] [rbp+770h]

  v4 = 0;
  v15 = 0;
  wil::EnterCriticalSection(&v15, a1 + 192);
  memset_0(v21, 0, 0x802u);
  v17 = 0;
  v18 = 0;
  v23 = &v19;
  v25 = &v22;
  v19 = -2143256512;
  v20 = 0;
  v24 = v21;
  v6 = (_OWORD *)(a1 + 144);
  if ( (*(_DWORD *)(a1 + 64) & 0x800) != 0 && (*(_DWORD *)(a1 + 20) & 0x8000) == 0 )
    v4 = tip2::details::shared_data<0,0,0>::serialize_data(a1, &v17, 1);
  v7 = *(_DWORD *)(a1 + 20);
  v8 = *(_BYTE *)(a1 + 32);
  v9 = *(_DWORD *)(a1 + 16);
  ProcAddress = (FARPROC)`TestCreate'::`2'::s_pfnTestCreate;
  if ( `TestCreate'::`2'::s_pfnTestCreate
    || (KernelBaseModuleHandle = (HMODULE)tip_details_GetKernelBaseModuleHandle(),
        ProcAddress = GetProcAddress(KernelBaseModuleHandle, "TestCreate"),
        (`TestCreate'::`2'::s_pfnTestCreate = (__int64)ProcAddress) != 0) )
  {
    LOBYTE(v5) = v8;
    v12 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64, _QWORD, __int64, __int64))ProcAddress)(
            v9,
            0,
            v5,
            v7,
            v4,
            a1 + 144);
  }
  else
  {
    *v6 = 0;
    v12 = 0;
  }
  v13 = *(_QWORD *)(a1 + 240);
  if ( v13 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)v16);
    TestClose(v13);
    wil::last_error_context::~last_error_context((wil::last_error_context *)v16);
  }
  *(_QWORD *)(a1 + 240) = v12;
  *(_DWORD *)(a1 + 184) = 1;
  *a2 = *v6;
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v17);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v15);
  return a2;
}

```

## disassembly

```asm
0x18002d810  mov     [rsp-8+arg_10], rbx
0x18002d815  push    rbp
0x18002d816  push    rsi
0x18002d817  push    rdi
0x18002d818  push    r12
0x18002d81a  push    r13
0x18002d81c  push    r14
0x18002d81e  push    r15
0x18002d820  lea     rbp, [rsp-790h]
0x18002d828  sub     rsp, 890h
0x18002d82f  mov     rax, cs:__security_cookie
0x18002d836  xor     rax, rsp
0x18002d839  mov     [rbp+7C0h+var_40], rax
0x18002d840  mov     r15, rdx
0x18002d843  mov     rbx, rcx
0x18002d846  xor     edi, edi
0x18002d848  mov     [rsp+8C0h+var_880], rdi
0x18002d84d  lea     rdx, [rcx+0C0h]
0x18002d854  lea     rcx, [rsp+8C0h+var_880]
0x18002d859  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x18002d85e  xor     edx, edx; Val
0x18002d860  mov     r8d, 802h; Size
0x18002d866  lea     rcx, [rsp+8C0h+var_862]; void *
0x18002d86b  call    memset_0
0x18002d870  mov     [rsp+8C0h+var_870], rdi
0x18002d875  mov     [rsp+8C0h+var_868], dil
0x18002d87a  lea     rax, [rsp+8C0h+var_867]
0x18002d87f  mov     [rbp+7C0h+var_60], rax
0x18002d886  lea     rax, [rbp+7C0h+var_67]
0x18002d88d  mov     [rbp+7C0h+var_50], rax
0x18002d894  mov     [rsp+8C0h+var_867], 80408040h
0x18002d89c  mov     [rsp+8C0h+var_863], dil
0x18002d8a1  lea     rax, [rsp+8C0h+var_862]
0x18002d8a6  mov     [rbp+7C0h+var_58], rax
0x18002d8ad  lea     r14, [rbx+90h]
0x18002d8b4  test    dword ptr [rbx+40h], 800h
0x18002d8bb  setnz   cl
0x18002d8be  test    dword ptr [rbx+14h], 8000h
0x18002d8c5  setz    al
0x18002d8c8  test    al, cl
0x18002d8ca  jz      short loc_18002D8E0
0x18002d8cc  lea     r8d, [rdi+1]
0x18002d8d0  lea     rdx, [rsp+8C0h+var_870]
0x18002d8d5  mov     rcx, rbx
0x18002d8d8  call    ?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x18002d8dd  mov     rdi, rax
0x18002d8e0  mov     esi, [rbx+14h]
0x18002d8e3  mov     r12b, [rbx+20h]
0x18002d8e7  mov     r13d, [rbx+10h]
0x18002d8eb  mov     rax, cs:?s_pfnTestCreate@?1??TestCreate@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@W4TestProperties@@PEBDPEAU_GUID@@@ZEA; HTIPTEST__ * (*`TestCreate'::`2'::s_pfnTestCreate)(uint,TestRetrievalOptions,TestStorage,TestProperties,char const *,_GUID *)
0x18002d8f2  test    rax, rax
0x18002d8f5  jnz     short loc_18002D924
0x18002d8f7  call    tip_details_GetKernelBaseModuleHandle
0x18002d8fc  mov     rcx, rax; hModule
0x18002d8ff  lea     rdx, aTestcreate; "TestCreate"
0x18002d906  call    cs:__imp_GetProcAddress
0x18002d90c  mov     cs:?s_pfnTestCreate@?1??TestCreate@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@W4TestProperties@@PEBDPEAU_GUID@@@ZEA, rax; HTIPTEST__ * (*`TestCreate'::`2'::s_pfnTestCreate)(uint,TestRetrievalOptions,TestStorage,TestProperties,char const *,_GUID *)
0x18002d913  test    rax, rax
0x18002d916  jnz     short loc_18002D924
0x18002d918  xorps   xmm0, xmm0
0x18002d91b  movdqu  xmmword ptr [r14], xmm0
0x18002d920  xor     esi, esi
0x18002d922  jmp     short loc_18002D941
0x18002d924  mov     [rsp+8C0h+var_898], r14
0x18002d929  mov     [rsp+8C0h+var_8A0], rdi
0x18002d92e  mov     r9d, esi
0x18002d931  mov     r8b, r12b
0x18002d934  xor     edx, edx
0x18002d936  mov     ecx, r13d
0x18002d939  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d93e  mov     rsi, rax
0x18002d941  mov     rdi, [rbx+0F0h]
0x18002d948  test    rdi, rdi
0x18002d94b  jz      short loc_18002D969
0x18002d94d  lea     rcx, [rsp+8C0h+var_878]; this
0x18002d952  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18002d957  mov     rcx, rdi
0x18002d95a  call    TestClose
0x18002d95f  lea     rcx, [rsp+8C0h+var_878]; this
0x18002d964  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18002d969  mov     [rbx+0F0h], rsi
0x18002d970  mov     dword ptr [rbx+0B8h], 1
0x18002d97a  movups  xmm0, xmmword ptr [r14]
0x18002d97e  movdqu  xmmword ptr [r15], xmm0
0x18002d983  lea     rcx, [rsp+8C0h+var_870]
0x18002d988  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18002d98d  lea     rcx, [rsp+8C0h+var_880]
0x18002d992  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18002d997  mov     rax, r15
0x18002d99a  mov     rcx, [rbp+7C0h+var_40]
0x18002d9a1  xor     rcx, rsp; StackCookie
0x18002d9a4  call    __security_check_cookie
0x18002d9a9  mov     rbx, [rsp+8C0h+arg_10]
0x18002d9b1  add     rsp, 890h
0x18002d9b8  pop     r15
0x18002d9ba  pop     r14
0x18002d9bc  pop     r13
0x18002d9be  pop     r12
0x18002d9c0  pop     rdi
0x18002d9c1  pop     rsi
0x18002d9c2  pop     rbp
0x18002d9c3  retn
```
