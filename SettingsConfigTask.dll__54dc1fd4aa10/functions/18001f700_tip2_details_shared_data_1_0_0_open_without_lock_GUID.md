# tip2::details::shared_data<1,0,0>::open_without_lock(_GUID *)

- ea: `0x18001f700`
- end: `0x18001f823`
- name: `?open_without_lock@?$shared_data@$00$0A@$0A@@details@tip2@@IEAAXPEAU_GUID@@@Z`
- size: `291`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180011954`

## callees

- `0x1800021d0`
- `0x18001299c`
- `0x18001dcf4`
- `0x18001f700`
- `0x1800200b0`
- `0x180021ae0`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001f75b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001f75b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f7fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f7fb`

## string_xrefs

- `0x18001f754`: `TestOpen`

## pseudocode

```c
void __fastcall tip2::details::shared_data<1,0,0>::open_without_lock(__int64 a1, __int64 a2, __int64 a3)
{
  char v5; // si
  unsigned int v6; // r14d
  FARPROC ProcAddress; // rax
  HMODULE KernelBaseModuleHandle; // rax
  __int64 v9; // rax
  __int64 v10; // [rsp+30h] [rbp-40h] BYREF
  __int128 v11; // [rsp+38h] [rbp-38h] BYREF
  LPVOID pv[2]; // [rsp+48h] [rbp-28h]
  __int128 v13; // [rsp+58h] [rbp-18h]

  v11 = 0;
  *(_OWORD *)pv = 0;
  v13 = 0;
  v5 = *(_BYTE *)(a1 + 32);
  v6 = *(_DWORD *)(a1 + 16);
  ProcAddress = (FARPROC)`TestOpen'::`2'::s_pfnTestOpen;
  if ( `TestOpen'::`2'::s_pfnTestOpen
    || (KernelBaseModuleHandle = (HMODULE)tip_details_GetKernelBaseModuleHandle(),
        ProcAddress = GetProcAddress(KernelBaseModuleHandle, "TestOpen"),
        (`TestOpen'::`2'::s_pfnTestOpen = (__int64)ProcAddress) != 0) )
  {
    LOBYTE(a3) = v5;
    v9 = ((__int64 (__fastcall *)(_QWORD, __int64, __int64, __int64, __int128 *))ProcAddress)(v6, 2097154, a3, a2, &v11);
    v10 = v9;
    if ( v9 )
    {
      *(_OWORD *)(a1 + 144) = v11;
      v10 = 0;
      wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&void TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::reset(
        a1 + 240,
        v9);
      *(_DWORD *)(a1 + 64) |= HIDWORD(pv[0]);
      if ( pv[1] )
        tip2::details::shared_data<1,0,0>::deserialize_data(a1, &v11);
      else
        *(_DWORD *)(a1 + 184) = pv[0];
    }
  }
  else
  {
    v11 = 0;
    *(_OWORD *)pv = 0;
    v13 = 0;
    v10 = 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&void TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&void TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>(&v10);
  CoTaskMemFree(pv[1]);
}

```

## disassembly

```asm
0x18001f700  mov     [rsp-18h+arg_10], rbx
0x18001f705  mov     [rsp-18h+arg_18], rsi
0x18001f70a  push    rbp
0x18001f70b  push    rdi
0x18001f70c  push    r14
0x18001f70e  mov     rbp, rsp
0x18001f711  sub     rsp, 70h
0x18001f715  mov     rax, cs:__security_cookie
0x18001f71c  xor     rax, rsp
0x18001f71f  mov     [rbp+var_8], rax
0x18001f723  mov     rdi, rdx
0x18001f726  mov     rbx, rcx
0x18001f729  xorps   xmm0, xmm0
0x18001f72c  movups  [rbp+var_38], xmm0
0x18001f730  movups  xmmword ptr [rbp+pv], xmm0
0x18001f734  movups  [rbp+var_18], xmm0
0x18001f738  mov     sil, [rcx+20h]
0x18001f73c  mov     r14d, [rcx+10h]
0x18001f740  mov     rax, cs:?s_pfnTestOpen@?1??TestOpen@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@PEAU_GUID@@PEAUTestInfo@TestInfo_ODR_guard@@@ZEA; HTIPTEST__ * (*`TestOpen'::`2'::s_pfnTestOpen)(uint,TestRetrievalOptions,TestStorage,_GUID *,TestInfo_ODR_guard::TestInfo *)
0x18001f747  test    rax, rax
0x18001f74a  jnz     short loc_18001F782
0x18001f74c  call    tip_details_GetKernelBaseModuleHandle
0x18001f751  mov     rcx, rax; hModule
0x18001f754  lea     rdx, aTestopen; "TestOpen"
0x18001f75b  call    cs:__imp_GetProcAddress
0x18001f761  mov     cs:?s_pfnTestOpen@?1??TestOpen@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@PEAU_GUID@@PEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; HTIPTEST__ * (*`TestOpen'::`2'::s_pfnTestOpen)(uint,TestRetrievalOptions,TestStorage,_GUID *,TestInfo_ODR_guard::TestInfo *)
0x18001f768  test    rax, rax
0x18001f76b  jnz     short loc_18001F782
0x18001f76d  xorps   xmm0, xmm0
0x18001f770  movups  [rbp+var_38], xmm0
0x18001f774  movups  xmmword ptr [rbp+pv], xmm0
0x18001f778  movups  [rbp+var_18], xmm0
0x18001f77c  mov     [rbp+var_40], rax
0x18001f780  jmp     short loc_18001F7EE
0x18001f782  lea     rcx, [rbp+var_38]
0x18001f786  mov     [rsp+70h+var_50], rcx
0x18001f78b  mov     r9, rdi
0x18001f78e  mov     r8b, sil
0x18001f791  mov     edx, 200002h
0x18001f796  mov     ecx, r14d
0x18001f799  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f79e  mov     [rbp+var_40], rax
0x18001f7a2  test    rax, rax
0x18001f7a5  jz      short loc_18001F7EE
0x18001f7a7  movups  xmm0, [rbp+var_38]
0x18001f7ab  movdqu  xmmword ptr [rbx+90h], xmm0
0x18001f7b3  mov     [rbp+var_40], 0
0x18001f7bb  lea     rcx, [rbx+0F0h]
0x18001f7c2  mov     rdx, rax
0x18001f7c5  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHTIPTEST__@@P6AXPEAU1@@Z$1?TestClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHTIPTEST__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::reset(HTIPTEST__ *)
0x18001f7ca  mov     eax, dword ptr [rbp+pv+4]
0x18001f7cd  or      [rbx+40h], eax
0x18001f7d0  cmp     [rbp+pv+8], 0
0x18001f7d5  jz      short loc_18001F7E5
0x18001f7d7  lea     rdx, [rbp+var_38]
0x18001f7db  mov     rcx, rbx
0x18001f7de  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x18001f7e3  jmp     short loc_18001F7EE
0x18001f7e5  mov     eax, dword ptr [rbp+pv]
0x18001f7e8  mov     [rbx+0B8h], eax
0x18001f7ee  lea     rcx, [rbp+var_40]
0x18001f7f2  call    ??1?$unique_storage@U?$resource_policy@PEAUHTIPTEST__@@P6AXPEAU1@@Z$1?TestClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>(void)
0x18001f7f7  mov     rcx, [rbp+pv+8]; pv
0x18001f7fb  call    cs:__imp_CoTaskMemFree
0x18001f801  nop
0x18001f802  mov     rcx, [rbp+var_8]
0x18001f806  xor     rcx, rsp; StackCookie
0x18001f809  call    __security_check_cookie
0x18001f80e  lea     r11, [rsp+70h+var_s0]
0x18001f813  mov     rbx, [r11+30h]
0x18001f817  mov     rsi, [r11+38h]
0x18001f81b  mov     rsp, r11
0x18001f81e  pop     r14
0x18001f820  pop     rdi
0x18001f821  pop     rbp
0x18001f822  retn
```
