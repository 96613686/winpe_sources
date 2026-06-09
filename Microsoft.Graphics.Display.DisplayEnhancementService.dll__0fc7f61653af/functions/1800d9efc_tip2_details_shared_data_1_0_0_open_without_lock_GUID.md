# tip2::details::shared_data<1,0,0>::open_without_lock(_GUID *)

- ea: `0x1800d9efc`
- end: `0x1800da01f`
- name: `?open_without_lock@?$shared_data@$00$0A@$0A@@details@tip2@@IEAAXPEAU_GUID@@@Z`
- size: `291`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800d7fc4`
- `0x1800d9e38`

## callees

- `0x180005860`
- `0x18006ceec`
- `0x18007345c`
- `0x180074868`
- `0x1800ccf38`
- `0x1800d9efc`
- `0x1800ed010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800d9f57`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800d9f57`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d9ff7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d9ff7`

## string_xrefs

- `0x1800d9f50`: `TestOpen`

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
0x1800d9efc  mov     [rsp-18h+arg_10], rbx
0x1800d9f01  mov     [rsp-18h+arg_18], rsi
0x1800d9f06  push    rbp
0x1800d9f07  push    rdi
0x1800d9f08  push    r14
0x1800d9f0a  mov     rbp, rsp
0x1800d9f0d  sub     rsp, 70h
0x1800d9f11  mov     rax, cs:__security_cookie
0x1800d9f18  xor     rax, rsp
0x1800d9f1b  mov     [rbp+var_8], rax
0x1800d9f1f  mov     rdi, rdx
0x1800d9f22  mov     rbx, rcx
0x1800d9f25  xorps   xmm0, xmm0
0x1800d9f28  movups  [rbp+var_38], xmm0
0x1800d9f2c  movups  xmmword ptr [rbp+pv], xmm0
0x1800d9f30  movups  [rbp+var_18], xmm0
0x1800d9f34  mov     sil, [rcx+20h]
0x1800d9f38  mov     r14d, [rcx+10h]
0x1800d9f3c  mov     rax, cs:?s_pfnTestOpen@?1??TestOpen@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@PEAU_GUID@@PEAUTestInfo@TestInfo_ODR_guard@@@ZEA; HTIPTEST__ * (*`TestOpen'::`2'::s_pfnTestOpen)(uint,TestRetrievalOptions,TestStorage,_GUID *,TestInfo_ODR_guard::TestInfo *)
0x1800d9f43  test    rax, rax
0x1800d9f46  jnz     short loc_1800D9F7E
0x1800d9f48  call    tip_details_GetKernelBaseModuleHandle
0x1800d9f4d  mov     rcx, rax; hModule
0x1800d9f50  lea     rdx, aTestopen; "TestOpen"
0x1800d9f57  call    cs:__imp_GetProcAddress
0x1800d9f5d  mov     cs:?s_pfnTestOpen@?1??TestOpen@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@PEAU_GUID@@PEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; HTIPTEST__ * (*`TestOpen'::`2'::s_pfnTestOpen)(uint,TestRetrievalOptions,TestStorage,_GUID *,TestInfo_ODR_guard::TestInfo *)
0x1800d9f64  test    rax, rax
0x1800d9f67  jnz     short loc_1800D9F7E
0x1800d9f69  xorps   xmm0, xmm0
0x1800d9f6c  movups  [rbp+var_38], xmm0
0x1800d9f70  movups  xmmword ptr [rbp+pv], xmm0
0x1800d9f74  movups  [rbp+var_18], xmm0
0x1800d9f78  mov     [rbp+var_40], rax
0x1800d9f7c  jmp     short loc_1800D9FEA
0x1800d9f7e  lea     rcx, [rbp+var_38]
0x1800d9f82  mov     [rsp+70h+var_50], rcx
0x1800d9f87  mov     r9, rdi
0x1800d9f8a  mov     r8b, sil
0x1800d9f8d  mov     edx, 200002h
0x1800d9f92  mov     ecx, r14d
0x1800d9f95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9f9a  mov     [rbp+var_40], rax
0x1800d9f9e  test    rax, rax
0x1800d9fa1  jz      short loc_1800D9FEA
0x1800d9fa3  movups  xmm0, [rbp+var_38]
0x1800d9fa7  movdqu  xmmword ptr [rbx+90h], xmm0
0x1800d9faf  mov     [rbp+var_40], 0
0x1800d9fb7  lea     rcx, [rbx+0F0h]
0x1800d9fbe  mov     rdx, rax
0x1800d9fc1  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHTIPTEST__@@P6AXPEAU1@@Z$1?TestClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHTIPTEST__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::reset(HTIPTEST__ *)
0x1800d9fc6  mov     eax, dword ptr [rbp+pv+4]
0x1800d9fc9  or      [rbx+40h], eax
0x1800d9fcc  cmp     [rbp+pv+8], 0
0x1800d9fd1  jz      short loc_1800D9FE1
0x1800d9fd3  lea     rdx, [rbp+var_38]
0x1800d9fd7  mov     rcx, rbx
0x1800d9fda  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x1800d9fdf  jmp     short loc_1800D9FEA
0x1800d9fe1  mov     eax, dword ptr [rbp+pv]
0x1800d9fe4  mov     [rbx+0B8h], eax
0x1800d9fea  lea     rcx, [rbp+var_40]
0x1800d9fee  call    ??1?$unique_storage@U?$resource_policy@PEAUHTIPTEST__@@P6AXPEAU1@@Z$1?TestClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>(void)
0x1800d9ff3  mov     rcx, [rbp+pv+8]; pv
0x1800d9ff7  call    cs:__imp_CoTaskMemFree
0x1800d9ffd  nop
0x1800d9ffe  mov     rcx, [rbp+var_8]
0x1800da002  xor     rcx, rsp; StackCookie
0x1800da005  call    __security_check_cookie
0x1800da00a  lea     r11, [rsp+70h+var_s0]
0x1800da00f  mov     rbx, [r11+30h]
0x1800da013  mov     rsi, [r11+38h]
0x1800da017  mov     rsp, r11
0x1800da01a  pop     r14
0x1800da01c  pop     rdi
0x1800da01d  pop     rbp
0x1800da01e  retn
```
