# tip2::details::shared_data<1,0,0>::end_update(void)

- ea: `0x180028f78`
- end: `0x1800290f0`
- name: `?end_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXXZ`
- size: `376`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18001f1b0`
- `0x180023ac0`

## callees

- `0x180018fc4`
- `0x18001aa64`
- `0x18001af84`
- `0x18001bbe0`
- `0x180028f78`
- `0x18002b88c`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800290bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800290bb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180029048`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180029048`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800290ce`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800290ce`

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
      tip2::details::shared_data<1,0,0>::deserialize_data((__int64 *)a1, (__int64)&v7);
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
0x180028f78  push    rbp
0x180028f7a  push    rbx
0x180028f7b  push    rsi
0x180028f7c  push    rdi
0x180028f7d  lea     rbp, [rsp-7A8h]
0x180028f85  sub     rsp, 8A8h
0x180028f8c  mov     rax, cs:__security_cookie
0x180028f93  xor     rax, rsp
0x180028f96  mov     [rbp+7C0h+var_30], rax
0x180028f9d  mov     rbx, rcx
0x180028fa0  bts     dword ptr [rcx+40h], 0Bh
0x180028fa5  cmp     qword ptr [rcx+0F0h], 0
0x180028fad  jz      loc_1800290C1
0x180028fb3  test    dword ptr [rcx+40h], 100h
0x180028fba  jnz     loc_1800290C1
0x180028fc0  xorps   xmm0, xmm0
0x180028fc3  movups  [rsp+8C0h+var_890], xmm0
0x180028fc8  movups  xmmword ptr [rsp+8C0h+pv], xmm0
0x180028fcd  movups  [rsp+8C0h+var_870], xmm0
0x180028fd2  mov     [rsp+8C0h+var_860], 0
0x180028fdb  mov     [rsp+8C0h+var_858], 0
0x180028fe0  lea     rax, [rsp+8C0h+var_857]
0x180028fe5  mov     [rbp+7C0h+var_50], rax
0x180028fec  lea     rax, [rbp+7C0h+var_57]
0x180028ff3  mov     [rbp+7C0h+var_40], rax
0x180028ffa  mov     [rsp+8C0h+var_857], 80408040h
0x180029002  mov     [rsp+8C0h+var_853], 0
0x180029007  lea     rax, [rsp+8C0h+var_852]
0x18002900c  mov     [rbp+7C0h+var_48], rax
0x180029013  mov     r8d, 1
0x180029019  lea     rdx, [rsp+8C0h+var_860]
0x18002901e  call    ?serialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<1,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x180029023  mov     rdi, rax
0x180029026  mov     rsi, [rbx+0F0h]
0x18002902d  mov     rax, cs:?s_pfnTestUnlockData@?1??TestUnlockData@@9@4P6AXPEAUHTIPTEST__@@W4TestUnlockOptions@@PEBDPEAUTestInfo@TestInfo_ODR_guard@@@ZEA; void (*`TestUnlockData'::`2'::s_pfnTestUnlockData)(HTIPTEST__ *,TestUnlockOptions,char const *,TestInfo_ODR_guard::TestInfo *)
0x180029034  test    rax, rax
0x180029037  jnz     short loc_18002906E
0x180029039  call    tip_details_GetKernelBaseModuleHandle
0x18002903e  mov     rcx, rax; hModule
0x180029041  lea     rdx, aTestunlockdata; "TestUnlockData"
0x180029048  call    cs:__imp_GetProcAddress
0x18002904e  mov     cs:?s_pfnTestUnlockData@?1??TestUnlockData@@9@4P6AXPEAUHTIPTEST__@@W4TestUnlockOptions@@PEBDPEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; void (*`TestUnlockData'::`2'::s_pfnTestUnlockData)(HTIPTEST__ *,TestUnlockOptions,char const *,TestInfo_ODR_guard::TestInfo *)
0x180029055  test    rax, rax
0x180029058  jnz     short loc_18002906E
0x18002905a  xorps   xmm0, xmm0
0x18002905d  movups  [rsp+8C0h+var_890], xmm0
0x180029062  movups  xmmword ptr [rsp+8C0h+pv], xmm0
0x180029067  movups  [rsp+8C0h+var_870], xmm0
0x18002906c  jmp     short loc_180029080
0x18002906e  lea     r9, [rsp+8C0h+var_890]
0x180029073  mov     r8, rdi
0x180029076  xor     edx, edx
0x180029078  mov     rcx, rsi
0x18002907b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029080  mov     rcx, [rsp+8C0h+pv]
0x180029085  mov     rax, rcx
0x180029088  shr     rax, 20h
0x18002908c  or      [rbx+40h], eax
0x18002908f  cmp     [rsp+8C0h+pv+8], 0
0x180029095  jz      short loc_1800290A6
0x180029097  lea     rdx, [rsp+8C0h+var_890]
0x18002909c  mov     rcx, rbx
0x18002909f  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x1800290a4  jmp     short loc_1800290AC
0x1800290a6  mov     [rbx+0B8h], ecx
0x1800290ac  lea     rcx, [rsp+8C0h+var_860]
0x1800290b1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800290b6  mov     rcx, [rsp+8C0h+pv+8]; pv
0x1800290bb  call    cs:__imp_CoTaskMemFree
0x1800290c1  dec     dword ptr [rbx+0E8h]
0x1800290c7  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x1800290ce  call    cs:__imp_LeaveCriticalSection
0x1800290d4  nop
0x1800290d5  mov     rcx, [rbp+7C0h+var_30]
0x1800290dc  xor     rcx, rsp; StackCookie
0x1800290df  call    __security_check_cookie
0x1800290e4  add     rsp, 8A8h
0x1800290eb  pop     rdi
0x1800290ec  pop     rsi
0x1800290ed  pop     rbx
0x1800290ee  pop     rbp
0x1800290ef  retn
```
