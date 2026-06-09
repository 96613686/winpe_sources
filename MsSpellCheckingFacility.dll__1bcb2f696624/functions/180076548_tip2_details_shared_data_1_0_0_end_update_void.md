# tip2::details::shared_data<1,0,0>::end_update(void)

- ea: `0x180076548`
- end: `0x1800766c0`
- name: `?end_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXXZ`
- size: `376`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180076368`
- `0x180076398`
- `0x18007c97c`

## callees

- `0x180054bc0`
- `0x180057430`
- `0x180057ac4`
- `0x180061320`
- `0x180076548`
- `0x18007869c`
- `0x1800c0010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180076618`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180076618`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007669e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007669e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007668b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007668b`

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
0x180076548  push    rbp
0x18007654a  push    rbx
0x18007654b  push    rsi
0x18007654c  push    rdi
0x18007654d  lea     rbp, [rsp-7A8h]
0x180076555  sub     rsp, 8A8h
0x18007655c  mov     rax, cs:__security_cookie
0x180076563  xor     rax, rsp
0x180076566  mov     [rbp+7C0h+var_30], rax
0x18007656d  mov     rbx, rcx
0x180076570  bts     dword ptr [rcx+40h], 0Bh
0x180076575  cmp     qword ptr [rcx+0F0h], 0
0x18007657d  jz      loc_180076691
0x180076583  test    dword ptr [rcx+40h], 100h
0x18007658a  jnz     loc_180076691
0x180076590  xorps   xmm0, xmm0
0x180076593  movups  [rsp+8C0h+var_890], xmm0
0x180076598  movups  xmmword ptr [rsp+8C0h+pv], xmm0
0x18007659d  movups  [rsp+8C0h+var_870], xmm0
0x1800765a2  mov     [rsp+8C0h+var_860], 0
0x1800765ab  mov     [rsp+8C0h+var_858], 0
0x1800765b0  lea     rax, [rsp+8C0h+var_857]
0x1800765b5  mov     [rbp+7C0h+var_50], rax
0x1800765bc  lea     rax, [rbp+7C0h+var_57]
0x1800765c3  mov     [rbp+7C0h+var_40], rax
0x1800765ca  mov     [rsp+8C0h+var_857], 80408040h
0x1800765d2  mov     [rsp+8C0h+var_853], 0
0x1800765d7  lea     rax, [rsp+8C0h+var_852]
0x1800765dc  mov     [rbp+7C0h+var_48], rax
0x1800765e3  mov     r8d, 1
0x1800765e9  lea     rdx, [rsp+8C0h+var_860]
0x1800765ee  call    ?serialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<1,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x1800765f3  mov     rdi, rax
0x1800765f6  mov     rsi, [rbx+0F0h]
0x1800765fd  mov     rax, cs:?s_pfnTestUnlockData@?1??TestUnlockData@@9@4P6AXPEAUHTIPTEST__@@W4TestUnlockOptions@@PEBDPEAUTestInfo@TestInfo_ODR_guard@@@ZEA; void (*`TestUnlockData'::`2'::s_pfnTestUnlockData)(HTIPTEST__ *,TestUnlockOptions,char const *,TestInfo_ODR_guard::TestInfo *)
0x180076604  test    rax, rax
0x180076607  jnz     short loc_18007663E
0x180076609  call    tip_details_GetKernelBaseModuleHandle
0x18007660e  mov     rcx, rax; hModule
0x180076611  lea     rdx, aTestunlockdata; "TestUnlockData"
0x180076618  call    cs:__imp_GetProcAddress
0x18007661e  mov     cs:?s_pfnTestUnlockData@?1??TestUnlockData@@9@4P6AXPEAUHTIPTEST__@@W4TestUnlockOptions@@PEBDPEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; void (*`TestUnlockData'::`2'::s_pfnTestUnlockData)(HTIPTEST__ *,TestUnlockOptions,char const *,TestInfo_ODR_guard::TestInfo *)
0x180076625  test    rax, rax
0x180076628  jnz     short loc_18007663E
0x18007662a  xorps   xmm0, xmm0
0x18007662d  movups  [rsp+8C0h+var_890], xmm0
0x180076632  movups  xmmword ptr [rsp+8C0h+pv], xmm0
0x180076637  movups  [rsp+8C0h+var_870], xmm0
0x18007663c  jmp     short loc_180076650
0x18007663e  lea     r9, [rsp+8C0h+var_890]
0x180076643  mov     r8, rdi
0x180076646  xor     edx, edx
0x180076648  mov     rcx, rsi
0x18007664b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076650  mov     rcx, [rsp+8C0h+pv]
0x180076655  mov     rax, rcx
0x180076658  shr     rax, 20h
0x18007665c  or      [rbx+40h], eax
0x18007665f  cmp     [rsp+8C0h+pv+8], 0
0x180076665  jz      short loc_180076676
0x180076667  lea     rdx, [rsp+8C0h+var_890]
0x18007666c  mov     rcx, rbx
0x18007666f  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x180076674  jmp     short loc_18007667C
0x180076676  mov     [rbx+0B8h], ecx
0x18007667c  lea     rcx, [rsp+8C0h+var_860]
0x180076681  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180076686  mov     rcx, [rsp+8C0h+pv+8]; pv
0x18007668b  call    cs:__imp_CoTaskMemFree
0x180076691  dec     dword ptr [rbx+0E8h]
0x180076697  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x18007669e  call    cs:__imp_LeaveCriticalSection
0x1800766a4  nop
0x1800766a5  mov     rcx, [rbp+7C0h+var_30]
0x1800766ac  xor     rcx, rsp; StackCookie
0x1800766af  call    __security_check_cookie
0x1800766b4  add     rsp, 8A8h
0x1800766bb  pop     rdi
0x1800766bc  pop     rsi
0x1800766bd  pop     rbx
0x1800766be  pop     rbp
0x1800766bf  retn
```
