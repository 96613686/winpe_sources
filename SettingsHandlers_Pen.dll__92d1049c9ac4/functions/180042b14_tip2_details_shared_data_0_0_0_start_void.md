# tip2::details::shared_data<0,0,0>::start(void)

- ea: `0x180042b14`
- end: `0x180042cbd`
- name: `?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ`
- size: `425`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task`

## callers

- `0x180042cc4`

## callees

- `0x1800030e0`
- `0x180005af0`
- `0x180005ecc`
- `0x180006240`
- `0x180006ec8`
- `0x180020740`
- `0x180042940`
- `0x180042b14`
- `0x180043108`
- `0x18004321c`
- `0x18005d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180042c00`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180042c00`

## string_xrefs

- `0x180042bf9`: `TestCreate`

## pseudocode

```c
_OWORD *__fastcall tip2::details::shared_data<0,0,0>::start(__int64 a1, _OWORD *a2)
{
  __int64 v4; // r8
  bool v5; // al
  _OWORD *v6; // rsi
  __int64 v7; // r14
  unsigned int v8; // edi
  char v9; // r12
  unsigned int v10; // r13d
  FARPROC ProcAddress; // rax
  HMODULE KernelBaseModuleHandle; // rax
  __int64 v13; // r14
  __int64 v14; // rdi
  _BYTE v16[8]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v17[8]; // [rsp+48h] [rbp-B8h] BYREF
  void *v18; // [rsp+50h] [rbp-B0h] BYREF
  char v19; // [rsp+58h] [rbp-A8h]
  int v20; // [rsp+59h] [rbp-A7h] BYREF
  char v21; // [rsp+5Dh] [rbp-A3h]
  char v22; // [rsp+5Eh] [rbp-A2h] BYREF
  char v23; // [rsp+859h] [rbp+759h] BYREF
  int *v24; // [rsp+860h] [rbp+760h]
  char *v25; // [rsp+868h] [rbp+768h]
  char *v26; // [rsp+870h] [rbp+770h]

  wil::EnterCriticalSection(v17, a1 + 192);
  v18 = 0;
  v19 = 0;
  v24 = &v20;
  v26 = &v23;
  v20 = -2143256512;
  v21 = 0;
  v25 = &v22;
  v5 = (*(_DWORD *)(a1 + 64) & 0x800) != 0 && (*(_DWORD *)(a1 + 20) & 0x8000) == 0;
  v6 = (_OWORD *)(a1 + 144);
  if ( v5 )
    v7 = tip2::details::shared_data<0,0,0>::serialize_data(a1, &v18, 1);
  else
    v7 = 0;
  v8 = *(_DWORD *)(a1 + 20);
  v9 = *(_BYTE *)(a1 + 32);
  v10 = *(_DWORD *)(a1 + 16);
  ProcAddress = (FARPROC)`TestCreate'::`2'::s_pfnTestCreate;
  if ( `TestCreate'::`2'::s_pfnTestCreate
    || (KernelBaseModuleHandle = (HMODULE)tip_details_GetKernelBaseModuleHandle(),
        ProcAddress = GetProcAddress(KernelBaseModuleHandle, "TestCreate"),
        (`TestCreate'::`2'::s_pfnTestCreate = (__int64)ProcAddress) != 0) )
  {
    LOBYTE(v4) = v9;
    v13 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64, _QWORD, __int64, __int64))ProcAddress)(
            v10,
            0,
            v4,
            v8,
            v7,
            a1 + 144);
  }
  else
  {
    *v6 = 0;
    v13 = 0;
  }
  v14 = *(_QWORD *)(a1 + 240);
  if ( v14 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)v16);
    TestClose(v14);
    wil::last_error_context::~last_error_context((wil::last_error_context *)v16);
  }
  *(_QWORD *)(a1 + 240) = v13;
  *(_DWORD *)(a1 + 184) = 1;
  *a2 = *v6;
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v18);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(v17);
  return a2;
}

```

## disassembly

```asm
0x180042b14  mov     [rsp-8+arg_10], rbx
0x180042b19  push    rbp
0x180042b1a  push    rsi
0x180042b1b  push    rdi
0x180042b1c  push    r12
0x180042b1e  push    r13
0x180042b20  push    r14
0x180042b22  push    r15
0x180042b24  lea     rbp, [rsp-790h]
0x180042b2c  sub     rsp, 890h
0x180042b33  mov     rax, cs:__security_cookie
0x180042b3a  xor     rax, rsp
0x180042b3d  mov     [rbp+7C0h+var_40], rax
0x180042b44  mov     r15, rdx
0x180042b47  mov     rbx, rcx
0x180042b4a  lea     rdx, [rcx+0C0h]
0x180042b51  lea     rcx, [rsp+8C0h+var_878]
0x180042b56  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x180042b5b  mov     [rsp+8C0h+var_870], 0
0x180042b64  mov     [rsp+8C0h+var_868], 0
0x180042b69  lea     rax, [rsp+8C0h+var_867]
0x180042b6e  mov     [rbp+7C0h+var_60], rax
0x180042b75  lea     rax, [rbp+7C0h+var_67]
0x180042b7c  mov     [rbp+7C0h+var_50], rax
0x180042b83  mov     [rsp+8C0h+var_867], 80408040h
0x180042b8b  mov     [rsp+8C0h+var_863], 0
0x180042b90  lea     rax, [rsp+8C0h+var_862]
0x180042b95  mov     [rbp+7C0h+var_58], rax
0x180042b9c  test    dword ptr [rbx+40h], 800h
0x180042ba3  jz      short loc_180042BB2
0x180042ba5  test    dword ptr [rbx+14h], 8000h
0x180042bac  jnz     short loc_180042BB2
0x180042bae  mov     al, 1
0x180042bb0  jmp     short loc_180042BB4
0x180042bb2  xor     al, al
0x180042bb4  lea     rsi, [rbx+90h]
0x180042bbb  test    al, al
0x180042bbd  jz      short loc_180042BD7
0x180042bbf  mov     r8d, 1
0x180042bc5  lea     rdx, [rsp+8C0h+var_870]
0x180042bca  mov     rcx, rbx
0x180042bcd  call    ?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x180042bd2  mov     r14, rax
0x180042bd5  jmp     short loc_180042BDA
0x180042bd7  xor     r14d, r14d
0x180042bda  mov     edi, [rbx+14h]
0x180042bdd  mov     r12b, [rbx+20h]
0x180042be1  mov     r13d, [rbx+10h]
0x180042be5  mov     rax, cs:?s_pfnTestCreate@?1??TestCreate@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@W4TestProperties@@PEBDPEAU_GUID@@@ZEA; HTIPTEST__ * (*`TestCreate'::`2'::s_pfnTestCreate)(uint,TestRetrievalOptions,TestStorage,TestProperties,char const *,_GUID *)
0x180042bec  test    rax, rax
0x180042bef  jnz     short loc_180042C1E
0x180042bf1  call    tip_details_GetKernelBaseModuleHandle
0x180042bf6  mov     rcx, rax; hModule
0x180042bf9  lea     rdx, aTestcreate; "TestCreate"
0x180042c00  call    cs:__imp_GetProcAddress
0x180042c06  mov     cs:?s_pfnTestCreate@?1??TestCreate@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@W4TestProperties@@PEBDPEAU_GUID@@@ZEA, rax; HTIPTEST__ * (*`TestCreate'::`2'::s_pfnTestCreate)(uint,TestRetrievalOptions,TestStorage,TestProperties,char const *,_GUID *)
0x180042c0d  test    rax, rax
0x180042c10  jnz     short loc_180042C1E
0x180042c12  xorps   xmm0, xmm0
0x180042c15  movdqu  xmmword ptr [rsi], xmm0
0x180042c19  xor     r14d, r14d
0x180042c1c  jmp     short loc_180042C3B
0x180042c1e  mov     [rsp+8C0h+var_898], rsi
0x180042c23  mov     [rsp+8C0h+var_8A0], r14
0x180042c28  mov     r9d, edi
0x180042c2b  mov     r8b, r12b
0x180042c2e  xor     edx, edx
0x180042c30  mov     ecx, r13d
0x180042c33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042c38  mov     r14, rax
0x180042c3b  mov     rdi, [rbx+0F0h]
0x180042c42  test    rdi, rdi
0x180042c45  jz      short loc_180042C63
0x180042c47  lea     rcx, [rsp+8C0h+var_880]; this
0x180042c4c  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180042c51  mov     rcx, rdi
0x180042c54  call    TestClose
0x180042c59  lea     rcx, [rsp+8C0h+var_880]; this
0x180042c5e  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180042c63  mov     [rbx+0F0h], r14
0x180042c6a  mov     dword ptr [rbx+0B8h], 1
0x180042c74  movups  xmm0, xmmword ptr [rsi]
0x180042c77  movdqu  xmmword ptr [r15], xmm0
0x180042c7c  lea     rcx, [rsp+8C0h+var_870]
0x180042c81  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180042c86  lea     rcx, [rsp+8C0h+var_878]
0x180042c8b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180042c90  mov     rax, r15
0x180042c93  mov     rcx, [rbp+7C0h+var_40]
0x180042c9a  xor     rcx, rsp; StackCookie
0x180042c9d  call    __security_check_cookie
0x180042ca2  mov     rbx, [rsp+8C0h+arg_10]
0x180042caa  add     rsp, 890h
0x180042cb1  pop     r15
0x180042cb3  pop     r14
0x180042cb5  pop     r13
0x180042cb7  pop     r12
0x180042cb9  pop     rdi
0x180042cba  pop     rsi
0x180042cbb  pop     rbp
0x180042cbc  retn
```
