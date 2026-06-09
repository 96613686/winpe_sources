# tip2::details::shared_data<0,0,0>::end_update(void)

- ea: `0x180012ec0`
- end: `0x180013036`
- name: `?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ`
- size: `374`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180010a90`
- `0x1800125d0`

## callees

- `0x180002c00`
- `0x18000b524`
- `0x18000e47c`
- `0x18000eb28`
- `0x180012ec0`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012f9d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012f9d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013014`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013014`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013001`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013001`

## pseudocode

```c
void __fastcall tip2::details::shared_data<0,0,0>::end_update(__int64 a1)
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
  if ( *(_QWORD *)(a1 + 240) && (*(_DWORD *)(a1 + 64) & 0x100) == 0 && (*(_DWORD *)(a1 + 20) & 0x8000) == 0 )
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
    v2 = tip2::details::shared_data<0,0,0>::serialize_data(a1, &v10, 1);
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
    if ( !pv[1] )
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
0x180012ec0  push    rbp
0x180012ec2  push    rbx
0x180012ec3  push    rsi
0x180012ec4  push    rdi
0x180012ec5  lea     rbp, [rsp-7A8h]
0x180012ecd  sub     rsp, 8A8h
0x180012ed4  mov     rax, cs:__security_cookie
0x180012edb  xor     rax, rsp
0x180012ede  mov     [rbp+7C0h+var_30], rax
0x180012ee5  mov     rbx, rcx
0x180012ee8  bts     dword ptr [rcx+40h], 0Bh
0x180012eed  cmp     qword ptr [rcx+0F0h], 0
0x180012ef5  jz      loc_180013007
0x180012efb  test    dword ptr [rcx+40h], 100h
0x180012f02  jnz     loc_180013007
0x180012f08  test    dword ptr [rcx+14h], 8000h
0x180012f0f  jnz     loc_180013007
0x180012f15  xorps   xmm0, xmm0
0x180012f18  movups  [rsp+8C0h+var_890], xmm0
0x180012f1d  movups  xmmword ptr [rsp+8C0h+pv], xmm0
0x180012f22  movups  [rsp+8C0h+var_870], xmm0
0x180012f27  mov     [rsp+8C0h+var_860], 0
0x180012f30  mov     [rsp+8C0h+var_858], 0
0x180012f35  lea     rax, [rsp+8C0h+var_857]
0x180012f3a  mov     [rbp+7C0h+var_50], rax
0x180012f41  lea     rax, [rbp+7C0h+var_57]
0x180012f48  mov     [rbp+7C0h+var_40], rax
0x180012f4f  mov     [rsp+8C0h+var_857], 80408040h
0x180012f57  mov     [rsp+8C0h+var_853], 0
0x180012f5c  lea     rax, [rsp+8C0h+var_852]
0x180012f61  mov     [rbp+7C0h+var_48], rax
0x180012f68  mov     r8d, 1
0x180012f6e  lea     rdx, [rsp+8C0h+var_860]
0x180012f73  call    ?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x180012f78  mov     rdi, rax
0x180012f7b  mov     rsi, [rbx+0F0h]
0x180012f82  mov     rax, cs:?s_pfnTestUnlockData@?1??TestUnlockData@@9@4P6AXPEAUHTIPTEST__@@W4TestUnlockOptions@@PEBDPEAUTestInfo@TestInfo_ODR_guard@@@ZEA; void (*`TestUnlockData'::`2'::s_pfnTestUnlockData)(HTIPTEST__ *,TestUnlockOptions,char const *,TestInfo_ODR_guard::TestInfo *)
0x180012f89  test    rax, rax
0x180012f8c  jnz     short loc_180012FC3
0x180012f8e  call    tip_details_GetKernelBaseModuleHandle
0x180012f93  mov     rcx, rax; hModule
0x180012f96  lea     rdx, aTestunlockdata; "TestUnlockData"
0x180012f9d  call    cs:__imp_GetProcAddress
0x180012fa3  mov     cs:?s_pfnTestUnlockData@?1??TestUnlockData@@9@4P6AXPEAUHTIPTEST__@@W4TestUnlockOptions@@PEBDPEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; void (*`TestUnlockData'::`2'::s_pfnTestUnlockData)(HTIPTEST__ *,TestUnlockOptions,char const *,TestInfo_ODR_guard::TestInfo *)
0x180012faa  test    rax, rax
0x180012fad  jnz     short loc_180012FC3
0x180012faf  xorps   xmm0, xmm0
0x180012fb2  movups  [rsp+8C0h+var_890], xmm0
0x180012fb7  movups  xmmword ptr [rsp+8C0h+pv], xmm0
0x180012fbc  movups  [rsp+8C0h+var_870], xmm0
0x180012fc1  jmp     short loc_180012FD5
0x180012fc3  lea     r9, [rsp+8C0h+var_890]
0x180012fc8  mov     r8, rdi
0x180012fcb  xor     edx, edx
0x180012fcd  mov     rcx, rsi
0x180012fd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012fd5  mov     rcx, [rsp+8C0h+pv]
0x180012fda  mov     rax, rcx
0x180012fdd  shr     rax, 20h
0x180012fe1  or      [rbx+40h], eax
0x180012fe4  cmp     [rsp+8C0h+pv+8], 0
0x180012fea  jnz     short loc_180012FF2
0x180012fec  mov     [rbx+0B8h], ecx
0x180012ff2  lea     rcx, [rsp+8C0h+var_860]
0x180012ff7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180012ffc  mov     rcx, [rsp+8C0h+pv+8]; pv
0x180013001  call    cs:__imp_CoTaskMemFree
0x180013007  dec     dword ptr [rbx+0E8h]
0x18001300d  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x180013014  call    cs:__imp_LeaveCriticalSection
0x18001301a  nop
0x18001301b  mov     rcx, [rbp+7C0h+var_30]
0x180013022  xor     rcx, rsp; StackCookie
0x180013025  call    __security_check_cookie
0x18001302a  add     rsp, 8A8h
0x180013031  pop     rdi
0x180013032  pop     rsi
0x180013033  pop     rbx
0x180013034  pop     rbp
0x180013035  retn
```
