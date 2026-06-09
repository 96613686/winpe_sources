# tip2::details::shared_data<1,0,0>::start(void)

- ea: `0x18003a350`
- end: `0x18003a4e6`
- name: `?start@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ`
- size: `406`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, service_task`

## callers

- `0x18003a4ec`
- `0x180045124`

## callees

- `0x180009190`
- `0x18000b198`
- `0x18000b4e8`
- `0x18000b85c`
- `0x18000c150`
- `0x18002c8ac`
- `0x18002ca8c`
- `0x18003457c`
- `0x18003a17c`
- `0x18003a350`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003a429`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003a429`

## string_xrefs

- `0x18003a422`: `TestCreate`

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
0x18003a350  mov     [rsp-8+arg_10], rbx
0x18003a355  push    rbp
0x18003a356  push    rsi
0x18003a357  push    rdi
0x18003a358  push    r12
0x18003a35a  push    r13
0x18003a35c  push    r14
0x18003a35e  push    r15
0x18003a360  lea     rbp, [rsp-790h]
0x18003a368  sub     rsp, 890h
0x18003a36f  mov     rax, cs:__security_cookie
0x18003a376  xor     rax, rsp
0x18003a379  mov     [rbp+7C0h+var_40], rax
0x18003a380  mov     r15, rdx
0x18003a383  mov     rbx, rcx
0x18003a386  lea     rdx, [rcx+0C0h]
0x18003a38d  lea     rcx, [rsp+8C0h+var_878]
0x18003a392  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x18003a397  mov     [rsp+8C0h+var_870], 0
0x18003a3a0  mov     [rsp+8C0h+var_868], 0
0x18003a3a5  lea     rax, [rsp+8C0h+var_867]
0x18003a3aa  mov     [rbp+7C0h+var_60], rax
0x18003a3b1  lea     rax, [rbp+7C0h+var_67]
0x18003a3b8  mov     [rbp+7C0h+var_50], rax
0x18003a3bf  mov     [rsp+8C0h+var_867], 80408040h
0x18003a3c7  mov     [rsp+8C0h+var_863], 0
0x18003a3cc  lea     rax, [rsp+8C0h+var_862]
0x18003a3d1  mov     [rbp+7C0h+var_58], rax
0x18003a3d8  lea     rsi, [rbx+90h]
0x18003a3df  test    dword ptr [rbx+40h], 800h
0x18003a3e6  jz      short loc_18003A400
0x18003a3e8  mov     r8d, 1
0x18003a3ee  lea     rdx, [rsp+8C0h+var_870]
0x18003a3f3  mov     rcx, rbx
0x18003a3f6  call    ?serialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<1,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x18003a3fb  mov     rdi, rax
0x18003a3fe  jmp     short loc_18003A402
0x18003a400  xor     edi, edi
0x18003a402  mov     r14d, [rbx+14h]
0x18003a406  mov     r12b, [rbx+20h]
0x18003a40a  mov     r13d, [rbx+10h]
0x18003a40e  mov     rax, cs:?s_pfnTestCreate@?1??TestCreate@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@W4TestProperties@@PEBDPEAU_GUID@@@ZEA; HTIPTEST__ * (*`TestCreate'::`2'::s_pfnTestCreate)(uint,TestRetrievalOptions,TestStorage,TestProperties,char const *,_GUID *)
0x18003a415  test    rax, rax
0x18003a418  jnz     short loc_18003A447
0x18003a41a  call    tip_details_GetKernelBaseModuleHandle
0x18003a41f  mov     rcx, rax; hModule
0x18003a422  lea     rdx, aTestcreate; "TestCreate"
0x18003a429  call    cs:__imp_GetProcAddress
0x18003a42f  mov     cs:?s_pfnTestCreate@?1??TestCreate@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@W4TestProperties@@PEBDPEAU_GUID@@@ZEA, rax; HTIPTEST__ * (*`TestCreate'::`2'::s_pfnTestCreate)(uint,TestRetrievalOptions,TestStorage,TestProperties,char const *,_GUID *)
0x18003a436  test    rax, rax
0x18003a439  jnz     short loc_18003A447
0x18003a43b  xorps   xmm0, xmm0
0x18003a43e  movdqu  xmmword ptr [rsi], xmm0
0x18003a442  xor     r14d, r14d
0x18003a445  jmp     short loc_18003A464
0x18003a447  mov     [rsp+8C0h+var_898], rsi
0x18003a44c  mov     [rsp+8C0h+var_8A0], rdi
0x18003a451  mov     r9d, r14d
0x18003a454  mov     r8b, r12b
0x18003a457  xor     edx, edx
0x18003a459  mov     ecx, r13d
0x18003a45c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a461  mov     r14, rax
0x18003a464  mov     rdi, [rbx+0F0h]
0x18003a46b  test    rdi, rdi
0x18003a46e  jz      short loc_18003A48C
0x18003a470  lea     rcx, [rsp+8C0h+var_880]; this
0x18003a475  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18003a47a  mov     rcx, rdi
0x18003a47d  call    TestClose
0x18003a482  lea     rcx, [rsp+8C0h+var_880]; this
0x18003a487  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18003a48c  mov     [rbx+0F0h], r14
0x18003a493  mov     dword ptr [rbx+0B8h], 1
0x18003a49d  movups  xmm0, xmmword ptr [rsi]
0x18003a4a0  movdqu  xmmword ptr [r15], xmm0
0x18003a4a5  lea     rcx, [rsp+8C0h+var_870]
0x18003a4aa  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18003a4af  lea     rcx, [rsp+8C0h+var_878]
0x18003a4b4  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18003a4b9  mov     rax, r15
0x18003a4bc  mov     rcx, [rbp+7C0h+var_40]
0x18003a4c3  xor     rcx, rsp; StackCookie
0x18003a4c6  call    __security_check_cookie
0x18003a4cb  mov     rbx, [rsp+8C0h+arg_10]
0x18003a4d3  add     rsp, 890h
0x18003a4da  pop     r15
0x18003a4dc  pop     r14
0x18003a4de  pop     r13
0x18003a4e0  pop     r12
0x18003a4e2  pop     rdi
0x18003a4e3  pop     rsi
0x18003a4e4  pop     rbp
0x18003a4e5  retn
```
