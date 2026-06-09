# tip2::details::shared_data<0,0,0>::start(void)

- ea: `0x14001b938`
- end: `0x14001bae1`
- name: `?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ`
- size: `425`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task`

## callers

- `0x14001bb28`

## callees

- `0x140003620`
- `0x1400085ac`
- `0x140009088`
- `0x140009138`
- `0x1400097ec`
- `0x14000bb60`
- `0x14001b764`
- `0x14001b938`
- `0x14001c1a4`
- `0x14001c3a4`
- `0x14001f010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14001ba24`
- `KERNEL32!GetProcAddress` at `0x14001ba24`

## string_xrefs

- `0x14001ba1d`: `TestCreate`

## pseudocode

```c
_OWORD *__fastcall tip2::details::shared_data<0,0,0>::start(__int64 a1, _OWORD *a2)
{
  __int64 v4; // r8
  bool v5; // zf
  bool v6; // al
  __int128 *v7; // rsi
  __int64 v8; // r14
  FARPROC ProcAddress; // rax
  unsigned int v10; // edi
  char v11; // r12
  unsigned int v12; // r13d
  HMODULE KernelBaseModuleHandle; // rax
  __int64 v14; // r14
  __int64 v15; // rdi
  __int128 v16; // xmm0
  _BYTE v18[8]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v19[8]; // [rsp+48h] [rbp-B8h] BYREF
  void *v20; // [rsp+50h] [rbp-B0h] BYREF
  char v21; // [rsp+58h] [rbp-A8h]
  int v22; // [rsp+59h] [rbp-A7h] BYREF
  char v23; // [rsp+5Dh] [rbp-A3h]
  char v24; // [rsp+5Eh] [rbp-A2h] BYREF
  char v25; // [rsp+859h] [rbp+759h] BYREF
  int *v26; // [rsp+860h] [rbp+760h]
  char *v27; // [rsp+868h] [rbp+768h]
  char *v28; // [rsp+870h] [rbp+770h]

  wil::EnterCriticalSection(v19, a1 + 192);
  v5 = (*(_DWORD *)(a1 + 64) & 0x800) == 0;
  v26 = &v22;
  v28 = &v25;
  v27 = &v24;
  v20 = 0;
  v21 = 0;
  v22 = -2143256512;
  v23 = 0;
  v6 = !v5 && (*(_DWORD *)(a1 + 20) & 0x8000) == 0;
  v7 = (__int128 *)(a1 + 144);
  if ( v6 )
    v8 = tip2::details::shared_data<0,0,0>::serialize_data(a1, &v20, 1);
  else
    v8 = 0;
  ProcAddress = (FARPROC)`TestCreate'::`2'::s_pfnTestCreate;
  v10 = *(_DWORD *)(a1 + 20);
  v11 = *(_BYTE *)(a1 + 32);
  v12 = *(_DWORD *)(a1 + 16);
  if ( `TestCreate'::`2'::s_pfnTestCreate
    || (KernelBaseModuleHandle = (HMODULE)tip_details_GetKernelBaseModuleHandle(),
        ProcAddress = GetProcAddress(KernelBaseModuleHandle, "TestCreate"),
        (`TestCreate'::`2'::s_pfnTestCreate = (__int64)ProcAddress) != 0) )
  {
    LOBYTE(v4) = v11;
    v14 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64, _QWORD, __int64, __int64))ProcAddress)(
            v12,
            0,
            v4,
            v10,
            v8,
            a1 + 144);
  }
  else
  {
    v14 = 0;
    *v7 = 0;
  }
  v15 = *(_QWORD *)(a1 + 240);
  if ( v15 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)v18);
    TestClose(v15);
    wil::last_error_context::~last_error_context((wil::last_error_context *)v18);
  }
  *(_QWORD *)(a1 + 240) = v14;
  v16 = *v7;
  *(_DWORD *)(a1 + 184) = 1;
  *a2 = v16;
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v20);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(v19);
  return a2;
}

```

## disassembly

```asm
0x14001b938  mov     [rsp-8+arg_10], rbx
0x14001b93d  push    rbp
0x14001b93e  push    rsi
0x14001b93f  push    rdi
0x14001b940  push    r12
0x14001b942  push    r13
0x14001b944  push    r14
0x14001b946  push    r15
0x14001b948  lea     rbp, [rsp-790h]
0x14001b950  sub     rsp, 890h
0x14001b957  mov     rax, cs:__security_cookie
0x14001b95e  xor     rax, rsp
0x14001b961  mov     [rbp+7C0h+var_40], rax
0x14001b968  mov     r15, rdx
0x14001b96b  mov     rbx, rcx
0x14001b96e  lea     rdx, [rcx+0C0h]
0x14001b975  lea     rcx, [rsp+8C0h+var_878]
0x14001b97a  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x14001b97f  test    dword ptr [rbx+40h], 800h
0x14001b986  lea     rax, [rsp+8C0h+var_867]
0x14001b98b  mov     [rbp+7C0h+var_60], rax
0x14001b992  lea     rax, [rbp+7C0h+var_67]
0x14001b999  mov     [rbp+7C0h+var_50], rax
0x14001b9a0  lea     rax, [rsp+8C0h+var_862]
0x14001b9a5  mov     [rbp+7C0h+var_58], rax
0x14001b9ac  mov     [rsp+8C0h+var_870], 0
0x14001b9b5  mov     [rsp+8C0h+var_868], 0
0x14001b9ba  mov     [rsp+8C0h+var_867], 80408040h
0x14001b9c2  mov     [rsp+8C0h+var_863], 0
0x14001b9c7  jz      short loc_14001B9D6
0x14001b9c9  test    dword ptr [rbx+14h], 8000h
0x14001b9d0  jnz     short loc_14001B9D6
0x14001b9d2  mov     al, 1
0x14001b9d4  jmp     short loc_14001B9D8
0x14001b9d6  xor     al, al
0x14001b9d8  lea     rsi, [rbx+90h]
0x14001b9df  test    al, al
0x14001b9e1  jz      short loc_14001B9FB
0x14001b9e3  mov     r8d, 1
0x14001b9e9  lea     rdx, [rsp+8C0h+var_870]
0x14001b9ee  mov     rcx, rbx
0x14001b9f1  call    ?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x14001b9f6  mov     r14, rax
0x14001b9f9  jmp     short loc_14001B9FE
0x14001b9fb  xor     r14d, r14d
0x14001b9fe  mov     rax, cs:?s_pfnTestCreate@?1??TestCreate@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@W4TestProperties@@PEBDPEAU_GUID@@@ZEA; HTIPTEST__ * (*`TestCreate'::`2'::s_pfnTestCreate)(uint,TestRetrievalOptions,TestStorage,TestProperties,char const *,_GUID *)
0x14001ba05  mov     edi, [rbx+14h]
0x14001ba08  mov     r12b, [rbx+20h]
0x14001ba0c  mov     r13d, [rbx+10h]
0x14001ba10  test    rax, rax
0x14001ba13  jnz     short loc_14001BA42
0x14001ba15  call    tip_details_GetKernelBaseModuleHandle
0x14001ba1a  mov     rcx, rax; hModule
0x14001ba1d  lea     rdx, aTestcreate; "TestCreate"
0x14001ba24  call    cs:__imp_GetProcAddress
0x14001ba2a  mov     cs:?s_pfnTestCreate@?1??TestCreate@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@W4TestProperties@@PEBDPEAU_GUID@@@ZEA, rax; HTIPTEST__ * (*`TestCreate'::`2'::s_pfnTestCreate)(uint,TestRetrievalOptions,TestStorage,TestProperties,char const *,_GUID *)
0x14001ba31  test    rax, rax
0x14001ba34  jnz     short loc_14001BA42
0x14001ba36  xorps   xmm0, xmm0
0x14001ba39  xor     r14d, r14d
0x14001ba3c  movdqu  xmmword ptr [rsi], xmm0
0x14001ba40  jmp     short loc_14001BA5F
0x14001ba42  mov     [rsp+8C0h+var_898], rsi
0x14001ba47  mov     r9d, edi
0x14001ba4a  mov     r8b, r12b
0x14001ba4d  mov     [rsp+8C0h+var_8A0], r14
0x14001ba52  xor     edx, edx
0x14001ba54  mov     ecx, r13d
0x14001ba57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001ba5c  mov     r14, rax
0x14001ba5f  mov     rdi, [rbx+0F0h]
0x14001ba66  test    rdi, rdi
0x14001ba69  jz      short loc_14001BA87
0x14001ba6b  lea     rcx, [rsp+8C0h+var_880]; this
0x14001ba70  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x14001ba75  mov     rcx, rdi
0x14001ba78  call    TestClose
0x14001ba7d  lea     rcx, [rsp+8C0h+var_880]; this
0x14001ba82  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x14001ba87  mov     [rbx+0F0h], r14
0x14001ba8e  lea     rcx, [rsp+8C0h+var_870]
0x14001ba93  movups  xmm0, xmmword ptr [rsi]
0x14001ba96  mov     dword ptr [rbx+0B8h], 1
0x14001baa0  movdqu  xmmword ptr [r15], xmm0
0x14001baa5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x14001baaa  lea     rcx, [rsp+8C0h+var_878]
0x14001baaf  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x14001bab4  mov     rax, r15
0x14001bab7  mov     rcx, [rbp+7C0h+var_40]
0x14001babe  xor     rcx, rsp; StackCookie
0x14001bac1  call    __security_check_cookie
0x14001bac6  mov     rbx, [rsp+8C0h+arg_10]
0x14001bace  add     rsp, 890h
0x14001bad5  pop     r15
0x14001bad7  pop     r14
0x14001bad9  pop     r13
0x14001badb  pop     r12
0x14001badd  pop     rdi
0x14001bade  pop     rsi
0x14001badf  pop     rbp
0x14001bae0  retn
```
