# tip2::details::shared_data<0,0,0>::start(void)

- ea: `0x18000ed24`
- end: `0x18000eec9`
- name: `?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ`
- size: `421`
- prototype: `_OWORD *__fastcall(__int64, _OWORD *)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, service_task`

## callers

- `0x18000b6f0`
- `0x18000b820`

## callees

- `0x18000371c`
- `0x1800037a0`
- `0x180004c70`
- `0x18000a068`
- `0x18000a17c`
- `0x18000b370`
- `0x18000b3ac`
- `0x18000bc18`
- `0x18000eb08`
- `0x18000ed24`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ee0c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ee0c`

## string_xrefs

- `0x18000ee05`: `TestCreate`

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
0x18000ed24  mov     [rsp-8+arg_10], rbx
0x18000ed29  push    rbp
0x18000ed2a  push    rsi
0x18000ed2b  push    rdi
0x18000ed2c  push    r12
0x18000ed2e  push    r13
0x18000ed30  push    r14
0x18000ed32  push    r15
0x18000ed34  lea     rbp, [rsp-790h]
0x18000ed3c  sub     rsp, 890h
0x18000ed43  mov     rax, cs:__security_cookie
0x18000ed4a  xor     rax, rsp
0x18000ed4d  mov     [rbp+7C0h+var_40], rax
0x18000ed54  mov     r15, rdx
0x18000ed57  mov     rbx, rcx
0x18000ed5a  lea     rdx, [rcx+0C0h]
0x18000ed61  lea     rcx, [rsp+8C0h+var_878]
0x18000ed66  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x18000ed6b  mov     [rsp+8C0h+var_870], 0
0x18000ed74  mov     [rsp+8C0h+var_868], 0
0x18000ed79  lea     rax, [rsp+8C0h+var_867]
0x18000ed7e  mov     [rbp+7C0h+var_60], rax
0x18000ed85  lea     rax, [rbp+7C0h+var_67]
0x18000ed8c  mov     [rbp+7C0h+var_50], rax
0x18000ed93  mov     [rsp+8C0h+var_867], 80408040h
0x18000ed9b  mov     [rsp+8C0h+var_863], 0
0x18000eda0  lea     rax, [rsp+8C0h+var_862]
0x18000eda5  mov     [rbp+7C0h+var_58], rax
0x18000edac  lea     rsi, [rbx+90h]
0x18000edb3  test    dword ptr [rbx+40h], 800h
0x18000edba  setnz   cl
0x18000edbd  test    dword ptr [rbx+14h], 8000h
0x18000edc4  setz    al
0x18000edc7  test    al, cl
0x18000edc9  jz      short loc_18000EDE3
0x18000edcb  mov     r8d, 1
0x18000edd1  lea     rdx, [rsp+8C0h+var_870]
0x18000edd6  mov     rcx, rbx
0x18000edd9  call    ?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x18000edde  mov     rdi, rax
0x18000ede1  jmp     short loc_18000EDE5
0x18000ede3  xor     edi, edi
0x18000ede5  mov     r14d, [rbx+14h]
0x18000ede9  mov     r12b, [rbx+20h]
0x18000eded  mov     r13d, [rbx+10h]
0x18000edf1  mov     rax, cs:?s_pfnTestCreate@?1??TestCreate@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@W4TestProperties@@PEBDPEAU_GUID@@@ZEA; HTIPTEST__ * (*`TestCreate'::`2'::s_pfnTestCreate)(uint,TestRetrievalOptions,TestStorage,TestProperties,char const *,_GUID *)
0x18000edf8  test    rax, rax
0x18000edfb  jnz     short loc_18000EE2A
0x18000edfd  call    tip_details_GetKernelBaseModuleHandle
0x18000ee02  mov     rcx, rax; hModule
0x18000ee05  lea     rdx, aTestcreate; "TestCreate"
0x18000ee0c  call    cs:__imp_GetProcAddress
0x18000ee12  mov     cs:?s_pfnTestCreate@?1??TestCreate@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@W4TestProperties@@PEBDPEAU_GUID@@@ZEA, rax; HTIPTEST__ * (*`TestCreate'::`2'::s_pfnTestCreate)(uint,TestRetrievalOptions,TestStorage,TestProperties,char const *,_GUID *)
0x18000ee19  test    rax, rax
0x18000ee1c  jnz     short loc_18000EE2A
0x18000ee1e  xorps   xmm0, xmm0
0x18000ee21  movdqu  xmmword ptr [rsi], xmm0
0x18000ee25  xor     r14d, r14d
0x18000ee28  jmp     short loc_18000EE47
0x18000ee2a  mov     [rsp+8C0h+var_898], rsi
0x18000ee2f  mov     [rsp+8C0h+var_8A0], rdi
0x18000ee34  mov     r9d, r14d
0x18000ee37  mov     r8b, r12b
0x18000ee3a  xor     edx, edx
0x18000ee3c  mov     ecx, r13d
0x18000ee3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee44  mov     r14, rax
0x18000ee47  mov     rdi, [rbx+0F0h]
0x18000ee4e  test    rdi, rdi
0x18000ee51  jz      short loc_18000EE6F
0x18000ee53  lea     rcx, [rsp+8C0h+var_880]; this
0x18000ee58  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000ee5d  mov     rcx, rdi
0x18000ee60  call    TestClose
0x18000ee65  lea     rcx, [rsp+8C0h+var_880]; this
0x18000ee6a  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000ee6f  mov     [rbx+0F0h], r14
0x18000ee76  mov     dword ptr [rbx+0B8h], 1
0x18000ee80  movups  xmm0, xmmword ptr [rsi]
0x18000ee83  movdqu  xmmword ptr [r15], xmm0
0x18000ee88  lea     rcx, [rsp+8C0h+var_870]
0x18000ee8d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18000ee92  lea     rcx, [rsp+8C0h+var_878]
0x18000ee97  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18000ee9c  mov     rax, r15
0x18000ee9f  mov     rcx, [rbp+7C0h+var_40]
0x18000eea6  xor     rcx, rsp; StackCookie
0x18000eea9  call    __security_check_cookie
0x18000eeae  mov     rbx, [rsp+8C0h+arg_10]
0x18000eeb6  add     rsp, 890h
0x18000eebd  pop     r15
0x18000eebf  pop     r14
0x18000eec1  pop     r13
0x18000eec3  pop     r12
0x18000eec5  pop     rdi
0x18000eec6  pop     rsi
0x18000eec7  pop     rbp
0x18000eec8  retn
```
