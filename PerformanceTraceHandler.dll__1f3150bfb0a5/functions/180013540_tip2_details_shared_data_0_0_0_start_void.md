# tip2::details::shared_data<0,0,0>::start(void)

- ea: `0x180013540`
- end: `0x1800136e5`
- name: `?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ`
- size: `421`
- prototype: `_OWORD *__fastcall(__int64, _OWORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task`

## callers

- `0x180012890`

## callees

- `0x180002c00`
- `0x1800045b8`
- `0x1800048ec`
- `0x180004c88`
- `0x180005500`
- `0x18000b524`
- `0x18000e47c`
- `0x18000ea90`
- `0x18000eb28`
- `0x180013540`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013628`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013628`

## string_xrefs

- `0x180013621`: `TestCreate`

## pseudocode

```c
_OWORD *__fastcall tip2::details::shared_data<0,0,0>::start(__int64 a1, _OWORD *a2)
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
  if ( (*(_DWORD *)(a1 + 64) & 0x800) != 0 && (*(_DWORD *)(a1 + 20) & 0x8000) == 0 )
    v6 = tip2::details::shared_data<0,0,0>::serialize_data((__int64 *)a1, (struct tson::write_buffer *)&v17, 1u);
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
0x180013540  mov     [rsp-8+arg_10], rbx
0x180013545  push    rbp
0x180013546  push    rsi
0x180013547  push    rdi
0x180013548  push    r12
0x18001354a  push    r13
0x18001354c  push    r14
0x18001354e  push    r15
0x180013550  lea     rbp, [rsp-790h]
0x180013558  sub     rsp, 890h
0x18001355f  mov     rax, cs:__security_cookie
0x180013566  xor     rax, rsp
0x180013569  mov     [rbp+7C0h+var_40], rax
0x180013570  mov     r15, rdx
0x180013573  mov     rbx, rcx
0x180013576  lea     rdx, [rcx+0C0h]
0x18001357d  lea     rcx, [rsp+8C0h+var_878]
0x180013582  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x180013587  mov     [rsp+8C0h+var_870], 0
0x180013590  mov     [rsp+8C0h+var_868], 0
0x180013595  lea     rax, [rsp+8C0h+var_867]
0x18001359a  mov     [rbp+7C0h+var_60], rax
0x1800135a1  lea     rax, [rbp+7C0h+var_67]
0x1800135a8  mov     [rbp+7C0h+var_50], rax
0x1800135af  mov     [rsp+8C0h+var_867], 80408040h
0x1800135b7  mov     [rsp+8C0h+var_863], 0
0x1800135bc  lea     rax, [rsp+8C0h+var_862]
0x1800135c1  mov     [rbp+7C0h+var_58], rax
0x1800135c8  lea     rsi, [rbx+90h]
0x1800135cf  test    dword ptr [rbx+40h], 800h
0x1800135d6  setnz   cl
0x1800135d9  test    dword ptr [rbx+14h], 8000h
0x1800135e0  setz    al
0x1800135e3  test    al, cl
0x1800135e5  jz      short loc_1800135FF
0x1800135e7  mov     r8d, 1
0x1800135ed  lea     rdx, [rsp+8C0h+var_870]
0x1800135f2  mov     rcx, rbx
0x1800135f5  call    ?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x1800135fa  mov     rdi, rax
0x1800135fd  jmp     short loc_180013601
0x1800135ff  xor     edi, edi
0x180013601  mov     r14d, [rbx+14h]
0x180013605  mov     r12b, [rbx+20h]
0x180013609  mov     r13d, [rbx+10h]
0x18001360d  mov     rax, cs:?s_pfnTestCreate@?1??TestCreate@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@W4TestProperties@@PEBDPEAU_GUID@@@ZEA; HTIPTEST__ * (*`TestCreate'::`2'::s_pfnTestCreate)(uint,TestRetrievalOptions,TestStorage,TestProperties,char const *,_GUID *)
0x180013614  test    rax, rax
0x180013617  jnz     short loc_180013646
0x180013619  call    tip_details_GetKernelBaseModuleHandle
0x18001361e  mov     rcx, rax; hModule
0x180013621  lea     rdx, aTestcreate; "TestCreate"
0x180013628  call    cs:__imp_GetProcAddress
0x18001362e  mov     cs:?s_pfnTestCreate@?1??TestCreate@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@W4TestProperties@@PEBDPEAU_GUID@@@ZEA, rax; HTIPTEST__ * (*`TestCreate'::`2'::s_pfnTestCreate)(uint,TestRetrievalOptions,TestStorage,TestProperties,char const *,_GUID *)
0x180013635  test    rax, rax
0x180013638  jnz     short loc_180013646
0x18001363a  xorps   xmm0, xmm0
0x18001363d  movdqu  xmmword ptr [rsi], xmm0
0x180013641  xor     r14d, r14d
0x180013644  jmp     short loc_180013663
0x180013646  mov     [rsp+8C0h+var_898], rsi
0x18001364b  mov     [rsp+8C0h+var_8A0], rdi
0x180013650  mov     r9d, r14d
0x180013653  mov     r8b, r12b
0x180013656  xor     edx, edx
0x180013658  mov     ecx, r13d
0x18001365b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013660  mov     r14, rax
0x180013663  mov     rdi, [rbx+0F0h]
0x18001366a  test    rdi, rdi
0x18001366d  jz      short loc_18001368B
0x18001366f  lea     rcx, [rsp+8C0h+var_880]; this
0x180013674  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180013679  mov     rcx, rdi
0x18001367c  call    TestClose
0x180013681  lea     rcx, [rsp+8C0h+var_880]; this
0x180013686  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001368b  mov     [rbx+0F0h], r14
0x180013692  mov     dword ptr [rbx+0B8h], 1
0x18001369c  movups  xmm0, xmmword ptr [rsi]
0x18001369f  movdqu  xmmword ptr [r15], xmm0
0x1800136a4  lea     rcx, [rsp+8C0h+var_870]
0x1800136a9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800136ae  lea     rcx, [rsp+8C0h+var_878]
0x1800136b3  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x1800136b8  mov     rax, r15
0x1800136bb  mov     rcx, [rbp+7C0h+var_40]
0x1800136c2  xor     rcx, rsp; StackCookie
0x1800136c5  call    __security_check_cookie
0x1800136ca  mov     rbx, [rsp+8C0h+arg_10]
0x1800136d2  add     rsp, 890h
0x1800136d9  pop     r15
0x1800136db  pop     r14
0x1800136dd  pop     r13
0x1800136df  pop     r12
0x1800136e1  pop     rdi
0x1800136e2  pop     rsi
0x1800136e3  pop     rbp
0x1800136e4  retn
```
