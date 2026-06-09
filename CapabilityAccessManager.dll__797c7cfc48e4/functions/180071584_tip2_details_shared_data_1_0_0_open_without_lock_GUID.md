# tip2::details::shared_data<1,0,0>::open_without_lock(_GUID *)

- ea: `0x180071584`
- end: `0x1800716a7`
- name: `?open_without_lock@?$shared_data@$00$0A@$0A@@details@tip2@@IEAAXPEAU_GUID@@@Z`
- size: `291`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800669a8`
- `0x180071508`

## callees

- `0x1800094c0`
- `0x18002f2a0`
- `0x18003b828`
- `0x18003ce88`
- `0x18003e34c`
- `0x180071584`
- `0x1800c7010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800715df`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800715df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007167f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007167f`

## string_xrefs

- `0x1800715d8`: `TestOpen`

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
0x180071584  mov     [rsp-18h+arg_10], rbx
0x180071589  mov     [rsp-18h+arg_18], rsi
0x18007158e  push    rbp
0x18007158f  push    rdi
0x180071590  push    r14
0x180071592  mov     rbp, rsp
0x180071595  sub     rsp, 70h
0x180071599  mov     rax, cs:__security_cookie
0x1800715a0  xor     rax, rsp
0x1800715a3  mov     [rbp+var_8], rax
0x1800715a7  mov     rdi, rdx
0x1800715aa  mov     rbx, rcx
0x1800715ad  xorps   xmm0, xmm0
0x1800715b0  movups  [rbp+var_38], xmm0
0x1800715b4  movups  xmmword ptr [rbp+pv], xmm0
0x1800715b8  movups  [rbp+var_18], xmm0
0x1800715bc  mov     sil, [rcx+20h]
0x1800715c0  mov     r14d, [rcx+10h]
0x1800715c4  mov     rax, cs:?s_pfnTestOpen@?1??TestOpen@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@PEAU_GUID@@PEAUTestInfo@TestInfo_ODR_guard@@@ZEA; HTIPTEST__ * (*`TestOpen'::`2'::s_pfnTestOpen)(uint,TestRetrievalOptions,TestStorage,_GUID *,TestInfo_ODR_guard::TestInfo *)
0x1800715cb  test    rax, rax
0x1800715ce  jnz     short loc_180071606
0x1800715d0  call    tip_details_GetKernelBaseModuleHandle
0x1800715d5  mov     rcx, rax; hModule
0x1800715d8  lea     rdx, aTestopen; "TestOpen"
0x1800715df  call    cs:__imp_GetProcAddress
0x1800715e5  mov     cs:?s_pfnTestOpen@?1??TestOpen@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@PEAU_GUID@@PEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; HTIPTEST__ * (*`TestOpen'::`2'::s_pfnTestOpen)(uint,TestRetrievalOptions,TestStorage,_GUID *,TestInfo_ODR_guard::TestInfo *)
0x1800715ec  test    rax, rax
0x1800715ef  jnz     short loc_180071606
0x1800715f1  xorps   xmm0, xmm0
0x1800715f4  movups  [rbp+var_38], xmm0
0x1800715f8  movups  xmmword ptr [rbp+pv], xmm0
0x1800715fc  movups  [rbp+var_18], xmm0
0x180071600  mov     [rbp+var_40], rax
0x180071604  jmp     short loc_180071672
0x180071606  lea     rcx, [rbp+var_38]
0x18007160a  mov     [rsp+70h+var_50], rcx
0x18007160f  mov     r9, rdi
0x180071612  mov     r8b, sil
0x180071615  mov     edx, 200002h
0x18007161a  mov     ecx, r14d
0x18007161d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071622  mov     [rbp+var_40], rax
0x180071626  test    rax, rax
0x180071629  jz      short loc_180071672
0x18007162b  movups  xmm0, [rbp+var_38]
0x18007162f  movdqu  xmmword ptr [rbx+90h], xmm0
0x180071637  mov     [rbp+var_40], 0
0x18007163f  lea     rcx, [rbx+0F0h]
0x180071646  mov     rdx, rax
0x180071649  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHTIPTEST__@@P6AXPEAU1@@Z$1?TestClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHTIPTEST__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::reset(HTIPTEST__ *)
0x18007164e  mov     eax, dword ptr [rbp+pv+4]
0x180071651  or      [rbx+40h], eax
0x180071654  cmp     [rbp+pv+8], 0
0x180071659  jz      short loc_180071669
0x18007165b  lea     rdx, [rbp+var_38]
0x18007165f  mov     rcx, rbx
0x180071662  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x180071667  jmp     short loc_180071672
0x180071669  mov     eax, dword ptr [rbp+pv]
0x18007166c  mov     [rbx+0B8h], eax
0x180071672  lea     rcx, [rbp+var_40]
0x180071676  call    ??1?$unique_storage@U?$resource_policy@PEAUHTIPTEST__@@P6AXPEAU1@@Z$1?TestClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>(void)
0x18007167b  mov     rcx, [rbp+pv+8]; pv
0x18007167f  call    cs:__imp_CoTaskMemFree
0x180071685  nop
0x180071686  mov     rcx, [rbp+var_8]
0x18007168a  xor     rcx, rsp; StackCookie
0x18007168d  call    __security_check_cookie
0x180071692  lea     r11, [rsp+70h+var_s0]
0x180071697  mov     rbx, [r11+30h]
0x18007169b  mov     rsi, [r11+38h]
0x18007169f  mov     rsp, r11
0x1800716a2  pop     r14
0x1800716a4  pop     rdi
0x1800716a5  pop     rbp
0x1800716a6  retn
```
