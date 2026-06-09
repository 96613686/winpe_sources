# tip2::details::shared_data<1,0,0>::end_update(void)

- ea: `0x18004a394`
- end: `0x18004a50c`
- name: `?end_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXXZ`
- size: `376`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800493e0`
- `0x18004a364`

## callees

- `0x18001f8c8`
- `0x1800275e8`
- `0x180027bc8`
- `0x18002cd20`
- `0x180038560`
- `0x18004a394`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004a464`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004a464`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004a4ea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004a4ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a4d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a4d7`

## pseudocode

```c
void __fastcall tip2::details::shared_data<1,0,0>::end_update(__int64 a1)
{
  __int64 v2; // rdi
  __int64 v3; // rsi
  FARPROC ProcAddress; // rax
  HMODULE KernelBaseModuleHandle; // rax
  int v6; // ecx
  __int128 v7; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID pv[2]; // [rsp+40h] [rbp-C0h]
  __int128 v9; // [rsp+50h] [rbp-B0h]
  void *v10; // [rsp+60h] [rbp-A0h] BYREF
  char v11; // [rsp+68h] [rbp-98h]
  int v12; // [rsp+69h] [rbp-97h] BYREF
  char v13; // [rsp+6Dh] [rbp-93h]
  char v14; // [rsp+6Eh] [rbp-92h] BYREF
  char v15; // [rsp+869h] [rbp+769h] BYREF
  int *v16; // [rsp+870h] [rbp+770h]
  char *v17; // [rsp+878h] [rbp+778h]
  char *v18; // [rsp+880h] [rbp+780h]

  *(_DWORD *)(a1 + 64) |= 0x800u;
  if ( *(_QWORD *)(a1 + 240) && (*(_DWORD *)(a1 + 64) & 0x100) == 0 )
  {
    v7 = 0;
    *(_OWORD *)pv = 0;
    v9 = 0;
    v10 = 0;
    v11 = 0;
    v16 = &v12;
    v18 = &v15;
    v12 = -2143256512;
    v13 = 0;
    v17 = &v14;
    v2 = tip2::details::shared_data<1,0,0>::serialize_data(a1, &v10, 1);
    v3 = *(_QWORD *)(a1 + 240);
    ProcAddress = (FARPROC)`TestUnlockData'::`2'::s_pfnTestUnlockData;
    if ( `TestUnlockData'::`2'::s_pfnTestUnlockData
      || (KernelBaseModuleHandle = (HMODULE)tip_details_GetKernelBaseModuleHandle(),
          ProcAddress = GetProcAddress(KernelBaseModuleHandle, "TestUnlockData"),
          (`TestUnlockData'::`2'::s_pfnTestUnlockData = (__int64)ProcAddress) != 0) )
    {
      ((void (__fastcall *)(__int64, _QWORD, __int64, __int128 *))ProcAddress)(v3, 0, v2, &v7);
    }
    else
    {
      v7 = 0;
      *(_OWORD *)pv = 0;
      v9 = 0;
    }
    v6 = (int)pv[0];
    *(_DWORD *)(a1 + 64) |= HIDWORD(pv[0]);
    if ( pv[1] )
      tip2::details::shared_data<1,0,0>::deserialize_data(a1, &v7);
    else
      *(_DWORD *)(a1 + 184) = v6;
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v10);
    CoTaskMemFree(pv[1]);
  }
  --*(_DWORD *)(a1 + 232);
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 192));
}

```

## disassembly

```asm
0x18004a394  push    rbp
0x18004a396  push    rbx
0x18004a397  push    rsi
0x18004a398  push    rdi
0x18004a399  lea     rbp, [rsp-7A8h]
0x18004a3a1  sub     rsp, 8A8h
0x18004a3a8  mov     rax, cs:__security_cookie
0x18004a3af  xor     rax, rsp
0x18004a3b2  mov     [rbp+7C0h+var_30], rax
0x18004a3b9  mov     rbx, rcx
0x18004a3bc  bts     dword ptr [rcx+40h], 0Bh
0x18004a3c1  cmp     qword ptr [rcx+0F0h], 0
0x18004a3c9  jz      loc_18004A4DD
0x18004a3cf  test    dword ptr [rcx+40h], 100h
0x18004a3d6  jnz     loc_18004A4DD
0x18004a3dc  xorps   xmm0, xmm0
0x18004a3df  movups  [rsp+8C0h+var_890], xmm0
0x18004a3e4  movups  xmmword ptr [rsp+8C0h+pv], xmm0
0x18004a3e9  movups  [rsp+8C0h+var_870], xmm0
0x18004a3ee  mov     [rsp+8C0h+var_860], 0
0x18004a3f7  mov     [rsp+8C0h+var_858], 0
0x18004a3fc  lea     rax, [rsp+8C0h+var_857]
0x18004a401  mov     [rbp+7C0h+var_50], rax
0x18004a408  lea     rax, [rbp+7C0h+var_57]
0x18004a40f  mov     [rbp+7C0h+var_40], rax
0x18004a416  mov     [rsp+8C0h+var_857], 80408040h
0x18004a41e  mov     [rsp+8C0h+var_853], 0
0x18004a423  lea     rax, [rsp+8C0h+var_852]
0x18004a428  mov     [rbp+7C0h+var_48], rax
0x18004a42f  mov     r8d, 1
0x18004a435  lea     rdx, [rsp+8C0h+var_860]
0x18004a43a  call    ?serialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<1,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x18004a43f  mov     rdi, rax
0x18004a442  mov     rsi, [rbx+0F0h]
0x18004a449  mov     rax, cs:?s_pfnTestUnlockData@?1??TestUnlockData@@9@4P6AXPEAUHTIPTEST__@@W4TestUnlockOptions@@PEBDPEAUTestInfo@TestInfo_ODR_guard@@@ZEA; void (*`TestUnlockData'::`2'::s_pfnTestUnlockData)(HTIPTEST__ *,TestUnlockOptions,char const *,TestInfo_ODR_guard::TestInfo *)
0x18004a450  test    rax, rax
0x18004a453  jnz     short loc_18004A48A
0x18004a455  call    tip_details_GetKernelBaseModuleHandle
0x18004a45a  mov     rcx, rax; hModule
0x18004a45d  lea     rdx, aTestunlockdata; "TestUnlockData"
0x18004a464  call    cs:__imp_GetProcAddress
0x18004a46a  mov     cs:?s_pfnTestUnlockData@?1??TestUnlockData@@9@4P6AXPEAUHTIPTEST__@@W4TestUnlockOptions@@PEBDPEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; void (*`TestUnlockData'::`2'::s_pfnTestUnlockData)(HTIPTEST__ *,TestUnlockOptions,char const *,TestInfo_ODR_guard::TestInfo *)
0x18004a471  test    rax, rax
0x18004a474  jnz     short loc_18004A48A
0x18004a476  xorps   xmm0, xmm0
0x18004a479  movups  [rsp+8C0h+var_890], xmm0
0x18004a47e  movups  xmmword ptr [rsp+8C0h+pv], xmm0
0x18004a483  movups  [rsp+8C0h+var_870], xmm0
0x18004a488  jmp     short loc_18004A49C
0x18004a48a  lea     r9, [rsp+8C0h+var_890]
0x18004a48f  mov     r8, rdi
0x18004a492  xor     edx, edx
0x18004a494  mov     rcx, rsi
0x18004a497  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a49c  mov     rcx, [rsp+8C0h+pv]
0x18004a4a1  mov     rax, rcx
0x18004a4a4  shr     rax, 20h
0x18004a4a8  or      [rbx+40h], eax
0x18004a4ab  cmp     [rsp+8C0h+pv+8], 0
0x18004a4b1  jz      short loc_18004A4C2
0x18004a4b3  lea     rdx, [rsp+8C0h+var_890]
0x18004a4b8  mov     rcx, rbx
0x18004a4bb  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x18004a4c0  jmp     short loc_18004A4C8
0x18004a4c2  mov     [rbx+0B8h], ecx
0x18004a4c8  lea     rcx, [rsp+8C0h+var_860]
0x18004a4cd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18004a4d2  mov     rcx, [rsp+8C0h+pv+8]; pv
0x18004a4d7  call    cs:__imp_CoTaskMemFree
0x18004a4dd  dec     dword ptr [rbx+0E8h]
0x18004a4e3  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x18004a4ea  call    cs:__imp_LeaveCriticalSection
0x18004a4f0  nop
0x18004a4f1  mov     rcx, [rbp+7C0h+var_30]
0x18004a4f8  xor     rcx, rsp; StackCookie
0x18004a4fb  call    __security_check_cookie
0x18004a500  add     rsp, 8A8h
0x18004a507  pop     rdi
0x18004a508  pop     rsi
0x18004a509  pop     rbx
0x18004a50a  pop     rbp
0x18004a50b  retn
```
