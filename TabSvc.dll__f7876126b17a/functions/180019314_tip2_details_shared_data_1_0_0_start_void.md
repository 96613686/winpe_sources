# tip2::details::shared_data<1,0,0>::start(void)

- ea: `0x180019314`
- end: `0x1800194aa`
- name: `?start@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ`
- size: `406`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task`

## callers

- `0x18002ab14`

## callees

- `0x1800186a0`
- `0x1800186c0`
- `0x180018fc4`
- `0x180019314`
- `0x180019764`
- `0x180019784`
- `0x18001aa64`
- `0x18001bbe0`
- `0x18002b2bc`
- `0x18002b88c`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800193ed`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800193ed`

## string_xrefs

- `0x1800193e6`: `TestCreate`

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
0x180019314  mov     [rsp-8+arg_10], rbx
0x180019319  push    rbp
0x18001931a  push    rsi
0x18001931b  push    rdi
0x18001931c  push    r12
0x18001931e  push    r13
0x180019320  push    r14
0x180019322  push    r15
0x180019324  lea     rbp, [rsp-790h]
0x18001932c  sub     rsp, 890h
0x180019333  mov     rax, cs:__security_cookie
0x18001933a  xor     rax, rsp
0x18001933d  mov     [rbp+7C0h+var_40], rax
0x180019344  mov     r15, rdx
0x180019347  mov     rbx, rcx
0x18001934a  lea     rdx, [rcx+0C0h]
0x180019351  lea     rcx, [rsp+8C0h+var_878]
0x180019356  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x18001935b  mov     [rsp+8C0h+var_870], 0
0x180019364  mov     [rsp+8C0h+var_868], 0
0x180019369  lea     rax, [rsp+8C0h+var_867]
0x18001936e  mov     [rbp+7C0h+var_60], rax
0x180019375  lea     rax, [rbp+7C0h+var_67]
0x18001937c  mov     [rbp+7C0h+var_50], rax
0x180019383  mov     [rsp+8C0h+var_867], 80408040h
0x18001938b  mov     [rsp+8C0h+var_863], 0
0x180019390  lea     rax, [rsp+8C0h+var_862]
0x180019395  mov     [rbp+7C0h+var_58], rax
0x18001939c  lea     rsi, [rbx+90h]
0x1800193a3  test    dword ptr [rbx+40h], 800h
0x1800193aa  jz      short loc_1800193C4
0x1800193ac  mov     r8d, 1
0x1800193b2  lea     rdx, [rsp+8C0h+var_870]
0x1800193b7  mov     rcx, rbx
0x1800193ba  call    ?serialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<1,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x1800193bf  mov     rdi, rax
0x1800193c2  jmp     short loc_1800193C6
0x1800193c4  xor     edi, edi
0x1800193c6  mov     r14d, [rbx+14h]
0x1800193ca  mov     r12b, [rbx+20h]
0x1800193ce  mov     r13d, [rbx+10h]
0x1800193d2  mov     rax, cs:?s_pfnTestCreate@?1??TestCreate@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@W4TestProperties@@PEBDPEAU_GUID@@@ZEA; HTIPTEST__ * (*`TestCreate'::`2'::s_pfnTestCreate)(uint,TestRetrievalOptions,TestStorage,TestProperties,char const *,_GUID *)
0x1800193d9  test    rax, rax
0x1800193dc  jnz     short loc_18001940B
0x1800193de  call    tip_details_GetKernelBaseModuleHandle
0x1800193e3  mov     rcx, rax; hModule
0x1800193e6  lea     rdx, aTestcreate; "TestCreate"
0x1800193ed  call    cs:__imp_GetProcAddress
0x1800193f3  mov     cs:?s_pfnTestCreate@?1??TestCreate@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@W4TestProperties@@PEBDPEAU_GUID@@@ZEA, rax; HTIPTEST__ * (*`TestCreate'::`2'::s_pfnTestCreate)(uint,TestRetrievalOptions,TestStorage,TestProperties,char const *,_GUID *)
0x1800193fa  test    rax, rax
0x1800193fd  jnz     short loc_18001940B
0x1800193ff  xorps   xmm0, xmm0
0x180019402  movdqu  xmmword ptr [rsi], xmm0
0x180019406  xor     r14d, r14d
0x180019409  jmp     short loc_180019428
0x18001940b  mov     [rsp+8C0h+var_898], rsi
0x180019410  mov     [rsp+8C0h+var_8A0], rdi
0x180019415  mov     r9d, r14d
0x180019418  mov     r8b, r12b
0x18001941b  xor     edx, edx
0x18001941d  mov     ecx, r13d
0x180019420  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019425  mov     r14, rax
0x180019428  mov     rdi, [rbx+0F0h]
0x18001942f  test    rdi, rdi
0x180019432  jz      short loc_180019450
0x180019434  lea     rcx, [rsp+8C0h+var_880]; this
0x180019439  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001943e  mov     rcx, rdi
0x180019441  call    TestClose
0x180019446  lea     rcx, [rsp+8C0h+var_880]; this
0x18001944b  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180019450  mov     [rbx+0F0h], r14
0x180019457  mov     dword ptr [rbx+0B8h], 1
0x180019461  movups  xmm0, xmmword ptr [rsi]
0x180019464  movdqu  xmmword ptr [r15], xmm0
0x180019469  lea     rcx, [rsp+8C0h+var_870]
0x18001946e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180019473  lea     rcx, [rsp+8C0h+var_878]
0x180019478  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18001947d  mov     rax, r15
0x180019480  mov     rcx, [rbp+7C0h+var_40]
0x180019487  xor     rcx, rsp; StackCookie
0x18001948a  call    __security_check_cookie
0x18001948f  mov     rbx, [rsp+8C0h+arg_10]
0x180019497  add     rsp, 890h
0x18001949e  pop     r15
0x1800194a0  pop     r14
0x1800194a2  pop     r13
0x1800194a4  pop     r12
0x1800194a6  pop     rdi
0x1800194a7  pop     rsi
0x1800194a8  pop     rbp
0x1800194a9  retn
```
