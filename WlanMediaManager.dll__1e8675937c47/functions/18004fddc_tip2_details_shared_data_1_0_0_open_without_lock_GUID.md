# tip2::details::shared_data<1,0,0>::open_without_lock(_GUID *)

- ea: `0x18004fddc`
- end: `0x18004feff`
- name: `?open_without_lock@?$shared_data@$00$0A@$0A@@details@tip2@@IEAAXPEAU_GUID@@@Z`
- size: `291`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180039314`

## callees

- `0x180003ed0`
- `0x18003a204`
- `0x18004df78`
- `0x18004fddc`
- `0x1800505d0`
- `0x18005227c`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004fe37`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004fe37`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004fed7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004fed7`

## string_xrefs

- `0x18004fe30`: `TestOpen`

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
0x18004fddc  mov     [rsp-18h+arg_10], rbx
0x18004fde1  mov     [rsp-18h+arg_18], rsi
0x18004fde6  push    rbp
0x18004fde7  push    rdi
0x18004fde8  push    r14
0x18004fdea  mov     rbp, rsp
0x18004fded  sub     rsp, 70h
0x18004fdf1  mov     rax, cs:__security_cookie
0x18004fdf8  xor     rax, rsp
0x18004fdfb  mov     [rbp+var_8], rax
0x18004fdff  mov     rdi, rdx
0x18004fe02  mov     rbx, rcx
0x18004fe05  xorps   xmm0, xmm0
0x18004fe08  movups  [rbp+var_38], xmm0
0x18004fe0c  movups  xmmword ptr [rbp+pv], xmm0
0x18004fe10  movups  [rbp+var_18], xmm0
0x18004fe14  mov     sil, [rcx+20h]
0x18004fe18  mov     r14d, [rcx+10h]
0x18004fe1c  mov     rax, cs:?s_pfnTestOpen@?1??TestOpen@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@PEAU_GUID@@PEAUTestInfo@TestInfo_ODR_guard@@@ZEA; HTIPTEST__ * (*`TestOpen'::`2'::s_pfnTestOpen)(uint,TestRetrievalOptions,TestStorage,_GUID *,TestInfo_ODR_guard::TestInfo *)
0x18004fe23  test    rax, rax
0x18004fe26  jnz     short loc_18004FE5E
0x18004fe28  call    tip_details_GetKernelBaseModuleHandle
0x18004fe2d  mov     rcx, rax; hModule
0x18004fe30  lea     rdx, ProcName; "TestOpen"
0x18004fe37  call    cs:__imp_GetProcAddress
0x18004fe3d  mov     cs:?s_pfnTestOpen@?1??TestOpen@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@PEAU_GUID@@PEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; HTIPTEST__ * (*`TestOpen'::`2'::s_pfnTestOpen)(uint,TestRetrievalOptions,TestStorage,_GUID *,TestInfo_ODR_guard::TestInfo *)
0x18004fe44  test    rax, rax
0x18004fe47  jnz     short loc_18004FE5E
0x18004fe49  xorps   xmm0, xmm0
0x18004fe4c  movups  [rbp+var_38], xmm0
0x18004fe50  movups  xmmword ptr [rbp+pv], xmm0
0x18004fe54  movups  [rbp+var_18], xmm0
0x18004fe58  mov     [rbp+var_40], rax
0x18004fe5c  jmp     short loc_18004FECA
0x18004fe5e  lea     rcx, [rbp+var_38]
0x18004fe62  mov     [rsp+70h+var_50], rcx
0x18004fe67  mov     r9, rdi
0x18004fe6a  mov     r8b, sil
0x18004fe6d  mov     edx, 200002h
0x18004fe72  mov     ecx, r14d
0x18004fe75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fe7a  mov     [rbp+var_40], rax
0x18004fe7e  test    rax, rax
0x18004fe81  jz      short loc_18004FECA
0x18004fe83  movups  xmm0, [rbp+var_38]
0x18004fe87  movdqu  xmmword ptr [rbx+90h], xmm0
0x18004fe8f  mov     [rbp+var_40], 0
0x18004fe97  lea     rcx, [rbx+0F0h]
0x18004fe9e  mov     rdx, rax
0x18004fea1  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHTIPTEST__@@P6AXPEAU1@@Z$1?TestClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHTIPTEST__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::reset(HTIPTEST__ *)
0x18004fea6  mov     eax, dword ptr [rbp+pv+4]
0x18004fea9  or      [rbx+40h], eax
0x18004feac  cmp     [rbp+pv+8], 0
0x18004feb1  jz      short loc_18004FEC1
0x18004feb3  lea     rdx, [rbp+var_38]
0x18004feb7  mov     rcx, rbx
0x18004feba  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x18004febf  jmp     short loc_18004FECA
0x18004fec1  mov     eax, dword ptr [rbp+pv]
0x18004fec4  mov     [rbx+0B8h], eax
0x18004feca  lea     rcx, [rbp+var_40]
0x18004fece  call    ??1?$unique_storage@U?$resource_policy@PEAUHTIPTEST__@@P6AXPEAU1@@Z$1?TestClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>(void)
0x18004fed3  mov     rcx, [rbp+pv+8]; pv
0x18004fed7  call    cs:__imp_CoTaskMemFree
0x18004fedd  nop
0x18004fede  mov     rcx, [rbp+var_8]
0x18004fee2  xor     rcx, rsp; StackCookie
0x18004fee5  call    __security_check_cookie
0x18004feea  lea     r11, [rsp+70h+var_s0]
0x18004feef  mov     rbx, [r11+30h]
0x18004fef3  mov     rsi, [r11+38h]
0x18004fef7  mov     rsp, r11
0x18004fefa  pop     r14
0x18004fefc  pop     rdi
0x18004fefd  pop     rbp
0x18004fefe  retn
```
