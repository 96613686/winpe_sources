# tip2::details::shared_data<1,0,0>::open_without_lock(_GUID *)

- ea: `0x18003dbe0`
- end: `0x18003dd03`
- name: `?open_without_lock@?$shared_data@$00$0A@$0A@@details@tip2@@IEAAXPEAU_GUID@@@Z`
- size: `291`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180035d5c`

## callees

- `0x1800032b0`
- `0x1800370fc`
- `0x18003c738`
- `0x18003dbe0`
- `0x18003e544`
- `0x18003fcb4`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003dc3b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003dc3b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003dcdb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003dcdb`

## string_xrefs

- `0x18003dc34`: `TestOpen`

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
0x18003dbe0  mov     [rsp-18h+arg_10], rbx
0x18003dbe5  mov     [rsp-18h+arg_18], rsi
0x18003dbea  push    rbp
0x18003dbeb  push    rdi
0x18003dbec  push    r14
0x18003dbee  mov     rbp, rsp
0x18003dbf1  sub     rsp, 70h
0x18003dbf5  mov     rax, cs:__security_cookie
0x18003dbfc  xor     rax, rsp
0x18003dbff  mov     [rbp+var_8], rax
0x18003dc03  mov     rdi, rdx
0x18003dc06  mov     rbx, rcx
0x18003dc09  xorps   xmm0, xmm0
0x18003dc0c  movups  [rbp+var_38], xmm0
0x18003dc10  movups  xmmword ptr [rbp+pv], xmm0
0x18003dc14  movups  [rbp+var_18], xmm0
0x18003dc18  mov     sil, [rcx+20h]
0x18003dc1c  mov     r14d, [rcx+10h]
0x18003dc20  mov     rax, cs:?s_pfnTestOpen@?1??TestOpen@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@PEAU_GUID@@PEAUTestInfo@TestInfo_ODR_guard@@@ZEA; HTIPTEST__ * (*`TestOpen'::`2'::s_pfnTestOpen)(uint,TestRetrievalOptions,TestStorage,_GUID *,TestInfo_ODR_guard::TestInfo *)
0x18003dc27  test    rax, rax
0x18003dc2a  jnz     short loc_18003DC62
0x18003dc2c  call    tip_details_GetKernelBaseModuleHandle
0x18003dc31  mov     rcx, rax; hModule
0x18003dc34  lea     rdx, aTestopen; "TestOpen"
0x18003dc3b  call    cs:__imp_GetProcAddress
0x18003dc41  mov     cs:?s_pfnTestOpen@?1??TestOpen@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@PEAU_GUID@@PEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; HTIPTEST__ * (*`TestOpen'::`2'::s_pfnTestOpen)(uint,TestRetrievalOptions,TestStorage,_GUID *,TestInfo_ODR_guard::TestInfo *)
0x18003dc48  test    rax, rax
0x18003dc4b  jnz     short loc_18003DC62
0x18003dc4d  xorps   xmm0, xmm0
0x18003dc50  movups  [rbp+var_38], xmm0
0x18003dc54  movups  xmmword ptr [rbp+pv], xmm0
0x18003dc58  movups  [rbp+var_18], xmm0
0x18003dc5c  mov     [rbp+var_40], rax
0x18003dc60  jmp     short loc_18003DCCE
0x18003dc62  lea     rcx, [rbp+var_38]
0x18003dc66  mov     [rsp+70h+var_50], rcx
0x18003dc6b  mov     r9, rdi
0x18003dc6e  mov     r8b, sil
0x18003dc71  mov     edx, 200002h
0x18003dc76  mov     ecx, r14d
0x18003dc79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dc7e  mov     [rbp+var_40], rax
0x18003dc82  test    rax, rax
0x18003dc85  jz      short loc_18003DCCE
0x18003dc87  movups  xmm0, [rbp+var_38]
0x18003dc8b  movdqu  xmmword ptr [rbx+90h], xmm0
0x18003dc93  mov     [rbp+var_40], 0
0x18003dc9b  lea     rcx, [rbx+0F0h]
0x18003dca2  mov     rdx, rax
0x18003dca5  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHTIPTEST__@@P6AXPEAU1@@Z$1?TestClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHTIPTEST__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::reset(HTIPTEST__ *)
0x18003dcaa  mov     eax, dword ptr [rbp+pv+4]
0x18003dcad  or      [rbx+40h], eax
0x18003dcb0  cmp     [rbp+pv+8], 0
0x18003dcb5  jz      short loc_18003DCC5
0x18003dcb7  lea     rdx, [rbp+var_38]
0x18003dcbb  mov     rcx, rbx
0x18003dcbe  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x18003dcc3  jmp     short loc_18003DCCE
0x18003dcc5  mov     eax, dword ptr [rbp+pv]
0x18003dcc8  mov     [rbx+0B8h], eax
0x18003dcce  lea     rcx, [rbp+var_40]
0x18003dcd2  call    ??1?$unique_storage@U?$resource_policy@PEAUHTIPTEST__@@P6AXPEAU1@@Z$1?TestClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>(void)
0x18003dcd7  mov     rcx, [rbp+pv+8]; pv
0x18003dcdb  call    cs:__imp_CoTaskMemFree
0x18003dce1  nop
0x18003dce2  mov     rcx, [rbp+var_8]
0x18003dce6  xor     rcx, rsp; StackCookie
0x18003dce9  call    __security_check_cookie
0x18003dcee  lea     r11, [rsp+70h+var_s0]
0x18003dcf3  mov     rbx, [r11+30h]
0x18003dcf7  mov     rsi, [r11+38h]
0x18003dcfb  mov     rsp, r11
0x18003dcfe  pop     r14
0x18003dd00  pop     rdi
0x18003dd01  pop     rbp
0x18003dd02  retn
```
