# tip2::details::shared_data<1,0,0>::open_without_lock(_GUID *)

- ea: `0x1800830f8`
- end: `0x18008321b`
- name: `?open_without_lock@?$shared_data@$00$0A@$0A@@details@tip2@@IEAAXPEAU_GUID@@@Z`
- size: `291`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18007bcd0`
- `0x18007be20`
- `0x18007bee0`

## callees

- `0x180057ac4`
- `0x180061320`
- `0x180073f58`
- `0x180077978`
- `0x18007869c`
- `0x1800830f8`
- `0x1800c0010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180083153`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180083153`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800831f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800831f3`

## string_xrefs

- `0x18008314c`: `TestOpen`

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
0x1800830f8  mov     [rsp-18h+arg_10], rbx
0x1800830fd  mov     [rsp-18h+arg_18], rsi
0x180083102  push    rbp
0x180083103  push    rdi
0x180083104  push    r14
0x180083106  mov     rbp, rsp
0x180083109  sub     rsp, 70h
0x18008310d  mov     rax, cs:__security_cookie
0x180083114  xor     rax, rsp
0x180083117  mov     [rbp+var_8], rax
0x18008311b  mov     rdi, rdx
0x18008311e  mov     rbx, rcx
0x180083121  xorps   xmm0, xmm0
0x180083124  movups  [rbp+var_38], xmm0
0x180083128  movups  xmmword ptr [rbp+pv], xmm0
0x18008312c  movups  [rbp+var_18], xmm0
0x180083130  mov     sil, [rcx+20h]
0x180083134  mov     r14d, [rcx+10h]
0x180083138  mov     rax, cs:?s_pfnTestOpen@?1??TestOpen@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@PEAU_GUID@@PEAUTestInfo@TestInfo_ODR_guard@@@ZEA; HTIPTEST__ * (*`TestOpen'::`2'::s_pfnTestOpen)(uint,TestRetrievalOptions,TestStorage,_GUID *,TestInfo_ODR_guard::TestInfo *)
0x18008313f  test    rax, rax
0x180083142  jnz     short loc_18008317A
0x180083144  call    tip_details_GetKernelBaseModuleHandle
0x180083149  mov     rcx, rax; hModule
0x18008314c  lea     rdx, aTestopen; "TestOpen"
0x180083153  call    cs:__imp_GetProcAddress
0x180083159  mov     cs:?s_pfnTestOpen@?1??TestOpen@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@PEAU_GUID@@PEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; HTIPTEST__ * (*`TestOpen'::`2'::s_pfnTestOpen)(uint,TestRetrievalOptions,TestStorage,_GUID *,TestInfo_ODR_guard::TestInfo *)
0x180083160  test    rax, rax
0x180083163  jnz     short loc_18008317A
0x180083165  xorps   xmm0, xmm0
0x180083168  movups  [rbp+var_38], xmm0
0x18008316c  movups  xmmword ptr [rbp+pv], xmm0
0x180083170  movups  [rbp+var_18], xmm0
0x180083174  mov     [rbp+var_40], rax
0x180083178  jmp     short loc_1800831E6
0x18008317a  lea     rcx, [rbp+var_38]
0x18008317e  mov     [rsp+70h+var_50], rcx
0x180083183  mov     r9, rdi
0x180083186  mov     r8b, sil
0x180083189  mov     edx, 200002h
0x18008318e  mov     ecx, r14d
0x180083191  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083196  mov     [rbp+var_40], rax
0x18008319a  test    rax, rax
0x18008319d  jz      short loc_1800831E6
0x18008319f  movups  xmm0, [rbp+var_38]
0x1800831a3  movdqu  xmmword ptr [rbx+90h], xmm0
0x1800831ab  mov     [rbp+var_40], 0
0x1800831b3  lea     rcx, [rbx+0F0h]
0x1800831ba  mov     rdx, rax
0x1800831bd  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHTIPTEST__@@P6AXPEAU1@@Z$1?TestClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHTIPTEST__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::reset(HTIPTEST__ *)
0x1800831c2  mov     eax, dword ptr [rbp+pv+4]
0x1800831c5  or      [rbx+40h], eax
0x1800831c8  cmp     [rbp+pv+8], 0
0x1800831cd  jz      short loc_1800831DD
0x1800831cf  lea     rdx, [rbp+var_38]
0x1800831d3  mov     rcx, rbx
0x1800831d6  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x1800831db  jmp     short loc_1800831E6
0x1800831dd  mov     eax, dword ptr [rbp+pv]
0x1800831e0  mov     [rbx+0B8h], eax
0x1800831e6  lea     rcx, [rbp+var_40]
0x1800831ea  call    ??1?$unique_storage@U?$resource_policy@PEAUHTIPTEST__@@P6AXPEAU1@@Z$1?TestClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>(void)
0x1800831ef  mov     rcx, [rbp+pv+8]; pv
0x1800831f3  call    cs:__imp_CoTaskMemFree
0x1800831f9  nop
0x1800831fa  mov     rcx, [rbp+var_8]
0x1800831fe  xor     rcx, rsp; StackCookie
0x180083201  call    __security_check_cookie
0x180083206  lea     r11, [rsp+70h+var_s0]
0x18008320b  mov     rbx, [r11+30h]
0x18008320f  mov     rsi, [r11+38h]
0x180083213  mov     rsp, r11
0x180083216  pop     r14
0x180083218  pop     rdi
0x180083219  pop     rbp
0x18008321a  retn
```
