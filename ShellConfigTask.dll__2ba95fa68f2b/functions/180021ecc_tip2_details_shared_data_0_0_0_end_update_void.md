# tip2::details::shared_data<0,0,0>::end_update(void)

- ea: `0x180021ecc`
- end: `0x180022068`
- name: `?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ`
- size: `412`
- prototype: ``
- caller_count: `8`
- callee_count: `4`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180013bf8`
- `0x180013c80`
- `0x180013d08`
- `0x180013d90`
- `0x180027e78`
- `0x180027f00`
- `0x180027f88`
- `0x180028010`

## callees

- `0x180002590`
- `0x180021ecc`
- `0x1800245dc`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180021fad`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180021fad`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180021fc4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180021fc4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180022046`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180022046`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022028`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022033`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022028`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022033`

## string_xrefs

- `0x180021fa6`: `kernelbase.dll`

## pseudocode

```c
void __fastcall tip2::details::shared_data<0,0,0>::end_update(__int64 a1)
{
  __int64 v2; // rdi
  __int64 v3; // rsi
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  int v6; // edx
  void *v7; // rcx
  __int128 v8; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID v9[2]; // [rsp+40h] [rbp-C0h]
  __int128 v10; // [rsp+50h] [rbp-B0h]
  LPVOID pv; // [rsp+60h] [rbp-A0h] BYREF
  char v12; // [rsp+68h] [rbp-98h]
  int v13; // [rsp+69h] [rbp-97h] BYREF
  char v14; // [rsp+6Dh] [rbp-93h]
  char v15; // [rsp+6Eh] [rbp-92h] BYREF
  char v16; // [rsp+869h] [rbp+769h] BYREF
  int *v17; // [rsp+870h] [rbp+770h]
  char *v18; // [rsp+878h] [rbp+778h]
  char *v19; // [rsp+880h] [rbp+780h]

  *(_DWORD *)(a1 + 64) |= 0x800u;
  if ( *(_QWORD *)(a1 + 240) && (*(_DWORD *)(a1 + 64) & 0x100) == 0 && (*(_DWORD *)(a1 + 20) & 0x8000) == 0 )
  {
    v8 = 0;
    *(_OWORD *)v9 = 0;
    v10 = 0;
    pv = 0;
    v12 = 0;
    v17 = &v13;
    v19 = &v16;
    v13 = -2143256512;
    v14 = 0;
    v18 = &v15;
    v2 = tip2::details::shared_data<0,0,0>::serialize_data(a1, &pv, 1);
    v3 = *(_QWORD *)(a1 + 240);
    ProcAddress = (FARPROC)`TestUnlockData'::`2'::s_pfnTestUnlockData;
    if ( `TestUnlockData'::`2'::s_pfnTestUnlockData )
      goto LABEL_9;
    ModuleHandleW = g_tip_details_kernelbaseModuleHandle;
    if ( !g_tip_details_kernelbaseModuleHandle )
    {
      ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
      g_tip_details_kernelbaseModuleHandle = ModuleHandleW;
    }
    ProcAddress = GetProcAddress(ModuleHandleW, "TestUnlockData");
    `TestUnlockData'::`2'::s_pfnTestUnlockData = (__int64)ProcAddress;
    if ( ProcAddress )
    {
LABEL_9:
      ((void (__fastcall *)(__int64, _QWORD, __int64, __int128 *))ProcAddress)(v3, 0, v2, &v8);
    }
    else
    {
      v8 = 0;
      *(_OWORD *)v9 = 0;
      v10 = 0;
    }
    v6 = (int)v9[0];
    *(_DWORD *)(a1 + 64) |= HIDWORD(v9[0]);
    v7 = v9[1];
    if ( !v9[1] )
      *(_DWORD *)(a1 + 184) = v6;
    if ( pv )
    {
      CoTaskMemFree(pv);
      v7 = v9[1];
    }
    CoTaskMemFree(v7);
  }
  --*(_DWORD *)(a1 + 232);
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 192));
}

```

## disassembly

```asm
0x180021ecc  push    rbp
0x180021ece  push    rbx
0x180021ecf  push    rsi
0x180021ed0  push    rdi
0x180021ed1  lea     rbp, [rsp-7A8h]
0x180021ed9  sub     rsp, 8A8h
0x180021ee0  mov     rax, cs:__security_cookie
0x180021ee7  xor     rax, rsp
0x180021eea  mov     [rbp+7C0h+var_30], rax
0x180021ef1  mov     rbx, rcx
0x180021ef4  bts     dword ptr [rcx+40h], 0Bh
0x180021ef9  cmp     qword ptr [rcx+0F0h], 0
0x180021f01  jz      loc_180022039
0x180021f07  test    dword ptr [rcx+40h], 100h
0x180021f0e  jnz     loc_180022039
0x180021f14  test    dword ptr [rcx+14h], 8000h
0x180021f1b  jnz     loc_180022039
0x180021f21  xorps   xmm0, xmm0
0x180021f24  movups  [rsp+8C0h+var_890], xmm0
0x180021f29  movups  xmmword ptr [rsp+8C0h+var_880], xmm0
0x180021f2e  movups  [rsp+8C0h+var_870], xmm0
0x180021f33  mov     [rsp+8C0h+pv], 0
0x180021f3c  mov     [rsp+8C0h+var_858], 0
0x180021f41  lea     rax, [rsp+8C0h+var_857]
0x180021f46  mov     [rbp+7C0h+var_50], rax
0x180021f4d  lea     rax, [rbp+7C0h+var_57]
0x180021f54  mov     [rbp+7C0h+var_40], rax
0x180021f5b  mov     [rsp+8C0h+var_857], 80408040h
0x180021f63  mov     [rsp+8C0h+var_853], 0
0x180021f68  lea     rax, [rsp+8C0h+var_852]
0x180021f6d  mov     [rbp+7C0h+var_48], rax
0x180021f74  mov     r8d, 1
0x180021f7a  lea     rdx, [rsp+8C0h+pv]
0x180021f7f  call    ?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x180021f84  mov     rdi, rax
0x180021f87  mov     rsi, [rbx+0F0h]
0x180021f8e  mov     rax, cs:?s_pfnTestUnlockData@?1??TestUnlockData@@9@4P6AXPEAUHTIPTEST__@@W4TestUnlockOptions@@PEBDPEAUTestInfo@TestInfo_ODR_guard@@@ZEA; void (*`TestUnlockData'::`2'::s_pfnTestUnlockData)(HTIPTEST__ *,TestUnlockOptions,char const *,TestInfo_ODR_guard::TestInfo *)
0x180021f95  test    rax, rax
0x180021f98  jnz     short loc_180021FEA
0x180021f9a  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x180021fa1  test    rax, rax
0x180021fa4  jnz     short loc_180021FBA
0x180021fa6  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180021fad  call    cs:__imp_GetModuleHandleW
0x180021fb3  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x180021fba  lea     rdx, aTestunlockdata; "TestUnlockData"
0x180021fc1  mov     rcx, rax; hModule
0x180021fc4  call    cs:__imp_GetProcAddress
0x180021fca  mov     cs:?s_pfnTestUnlockData@?1??TestUnlockData@@9@4P6AXPEAUHTIPTEST__@@W4TestUnlockOptions@@PEBDPEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; void (*`TestUnlockData'::`2'::s_pfnTestUnlockData)(HTIPTEST__ *,TestUnlockOptions,char const *,TestInfo_ODR_guard::TestInfo *)
0x180021fd1  test    rax, rax
0x180021fd4  jnz     short loc_180021FEA
0x180021fd6  xorps   xmm0, xmm0
0x180021fd9  movups  [rsp+8C0h+var_890], xmm0
0x180021fde  movups  xmmword ptr [rsp+8C0h+var_880], xmm0
0x180021fe3  movups  [rsp+8C0h+var_870], xmm0
0x180021fe8  jmp     short loc_180021FFC
0x180021fea  lea     r9, [rsp+8C0h+var_890]
0x180021fef  mov     r8, rdi
0x180021ff2  xor     edx, edx
0x180021ff4  mov     rcx, rsi
0x180021ff7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021ffc  mov     rdx, [rsp+8C0h+var_880]
0x180022001  mov     rax, rdx
0x180022004  shr     rax, 20h
0x180022008  or      [rbx+40h], eax
0x18002200b  mov     rcx, [rsp+8C0h+var_880+8]
0x180022010  test    rcx, rcx
0x180022013  jnz     short loc_18002201B
0x180022015  mov     [rbx+0B8h], edx
0x18002201b  mov     rax, [rsp+8C0h+pv]
0x180022020  test    rax, rax
0x180022023  jz      short loc_180022033
0x180022025  mov     rcx, rax; pv
0x180022028  call    cs:__imp_CoTaskMemFree
0x18002202e  mov     rcx, [rsp+8C0h+var_880+8]; pv
0x180022033  call    cs:__imp_CoTaskMemFree
0x180022039  dec     dword ptr [rbx+0E8h]
0x18002203f  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x180022046  call    cs:__imp_LeaveCriticalSection
0x18002204c  nop
0x18002204d  mov     rcx, [rbp+7C0h+var_30]
0x180022054  xor     rcx, rsp; StackCookie
0x180022057  call    __security_check_cookie
0x18002205c  add     rsp, 8A8h
0x180022063  pop     rdi
0x180022064  pop     rsi
0x180022065  pop     rbx
0x180022066  pop     rbp
0x180022067  retn
```
