# tip2::details::shared_data<1,0,0>::start(void)

- ea: `0x180025af0`
- end: `0x180025c86`
- name: `?start@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ`
- size: `406`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, service_task`

## callers

- `0x180025c8c`
- `0x1800286b4`

## callees

- `0x180003560`
- `0x180004dc8`
- `0x180005094`
- `0x18001b360`
- `0x18001b3dc`
- `0x18001f52c`
- `0x180025900`
- `0x180025af0`
- `0x180026424`
- `0x1800265a8`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180025bc9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180025bc9`

## string_xrefs

- `0x180025bc2`: `TestCreate`

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
0x180025af0  mov     [rsp-8+arg_10], rbx
0x180025af5  push    rbp
0x180025af6  push    rsi
0x180025af7  push    rdi
0x180025af8  push    r12
0x180025afa  push    r13
0x180025afc  push    r14
0x180025afe  push    r15
0x180025b00  lea     rbp, [rsp-790h]
0x180025b08  sub     rsp, 890h
0x180025b0f  mov     rax, cs:__security_cookie
0x180025b16  xor     rax, rsp
0x180025b19  mov     [rbp+7C0h+var_40], rax
0x180025b20  mov     r15, rdx
0x180025b23  mov     rbx, rcx
0x180025b26  lea     rdx, [rcx+0C0h]
0x180025b2d  lea     rcx, [rsp+8C0h+var_878]
0x180025b32  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x180025b37  mov     [rsp+8C0h+var_870], 0
0x180025b40  mov     [rsp+8C0h+var_868], 0
0x180025b45  lea     rax, [rsp+8C0h+var_867]
0x180025b4a  mov     [rbp+7C0h+var_60], rax
0x180025b51  lea     rax, [rbp+7C0h+var_67]
0x180025b58  mov     [rbp+7C0h+var_50], rax
0x180025b5f  mov     [rsp+8C0h+var_867], 80408040h
0x180025b67  mov     [rsp+8C0h+var_863], 0
0x180025b6c  lea     rax, [rsp+8C0h+var_862]
0x180025b71  mov     [rbp+7C0h+var_58], rax
0x180025b78  lea     rsi, [rbx+90h]
0x180025b7f  test    dword ptr [rbx+40h], 800h
0x180025b86  jz      short loc_180025BA0
0x180025b88  mov     r8d, 1
0x180025b8e  lea     rdx, [rsp+8C0h+var_870]
0x180025b93  mov     rcx, rbx
0x180025b96  call    ?serialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<1,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x180025b9b  mov     rdi, rax
0x180025b9e  jmp     short loc_180025BA2
0x180025ba0  xor     edi, edi
0x180025ba2  mov     r14d, [rbx+14h]
0x180025ba6  mov     r12b, [rbx+20h]
0x180025baa  mov     r13d, [rbx+10h]
0x180025bae  mov     rax, cs:?s_pfnTestCreate@?1??TestCreate@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@W4TestProperties@@PEBDPEAU_GUID@@@ZEA; HTIPTEST__ * (*`TestCreate'::`2'::s_pfnTestCreate)(uint,TestRetrievalOptions,TestStorage,TestProperties,char const *,_GUID *)
0x180025bb5  test    rax, rax
0x180025bb8  jnz     short loc_180025BE7
0x180025bba  call    tip_details_GetKernelBaseModuleHandle
0x180025bbf  mov     rcx, rax; hModule
0x180025bc2  lea     rdx, aTestcreate; "TestCreate"
0x180025bc9  call    cs:__imp_GetProcAddress
0x180025bcf  mov     cs:?s_pfnTestCreate@?1??TestCreate@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@W4TestProperties@@PEBDPEAU_GUID@@@ZEA, rax; HTIPTEST__ * (*`TestCreate'::`2'::s_pfnTestCreate)(uint,TestRetrievalOptions,TestStorage,TestProperties,char const *,_GUID *)
0x180025bd6  test    rax, rax
0x180025bd9  jnz     short loc_180025BE7
0x180025bdb  xorps   xmm0, xmm0
0x180025bde  movdqu  xmmword ptr [rsi], xmm0
0x180025be2  xor     r14d, r14d
0x180025be5  jmp     short loc_180025C04
0x180025be7  mov     [rsp+8C0h+var_898], rsi
0x180025bec  mov     [rsp+8C0h+var_8A0], rdi
0x180025bf1  mov     r9d, r14d
0x180025bf4  mov     r8b, r12b
0x180025bf7  xor     edx, edx
0x180025bf9  mov     ecx, r13d
0x180025bfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025c01  mov     r14, rax
0x180025c04  mov     rdi, [rbx+0F0h]
0x180025c0b  test    rdi, rdi
0x180025c0e  jz      short loc_180025C2C
0x180025c10  lea     rcx, [rsp+8C0h+var_880]; this
0x180025c15  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180025c1a  mov     rcx, rdi
0x180025c1d  call    TestClose
0x180025c22  lea     rcx, [rsp+8C0h+var_880]; this
0x180025c27  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180025c2c  mov     [rbx+0F0h], r14
0x180025c33  mov     dword ptr [rbx+0B8h], 1
0x180025c3d  movups  xmm0, xmmword ptr [rsi]
0x180025c40  movdqu  xmmword ptr [r15], xmm0
0x180025c45  lea     rcx, [rsp+8C0h+var_870]
0x180025c4a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180025c4f  lea     rcx, [rsp+8C0h+var_878]
0x180025c54  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180025c59  mov     rax, r15
0x180025c5c  mov     rcx, [rbp+7C0h+var_40]
0x180025c63  xor     rcx, rsp; StackCookie
0x180025c66  call    __security_check_cookie
0x180025c6b  mov     rbx, [rsp+8C0h+arg_10]
0x180025c73  add     rsp, 890h
0x180025c7a  pop     r15
0x180025c7c  pop     r14
0x180025c7e  pop     r13
0x180025c80  pop     r12
0x180025c82  pop     rdi
0x180025c83  pop     rsi
0x180025c84  pop     rbp
0x180025c85  retn
```
