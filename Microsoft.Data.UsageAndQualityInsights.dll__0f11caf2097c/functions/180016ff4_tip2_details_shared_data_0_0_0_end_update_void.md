# tip2::details::shared_data<0,0,0>::end_update(void)

- ea: `0x180016ff4`
- end: `0x180017190`
- name: `?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ`
- size: `412`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180013dbc`
- `0x180013e44`
- `0x180017a90`
- `0x180043764`

## callees

- `0x1800033d0`
- `0x180016ff4`
- `0x180018ba0`
- `0x180108010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800170d5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800170d5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800170ec`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800170ec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001716e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001716e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017150`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001715b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017150`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001715b`

## string_xrefs

- `0x1800170ce`: `kernelbase.dll`

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
0x180016ff4  push    rbp
0x180016ff6  push    rbx
0x180016ff7  push    rsi
0x180016ff8  push    rdi
0x180016ff9  lea     rbp, [rsp-7A8h]
0x180017001  sub     rsp, 8A8h
0x180017008  mov     rax, cs:__security_cookie
0x18001700f  xor     rax, rsp
0x180017012  mov     [rbp+7C0h+var_30], rax
0x180017019  mov     rbx, rcx
0x18001701c  bts     dword ptr [rcx+40h], 0Bh
0x180017021  cmp     qword ptr [rcx+0F0h], 0
0x180017029  jz      loc_180017161
0x18001702f  test    dword ptr [rcx+40h], 100h
0x180017036  jnz     loc_180017161
0x18001703c  test    dword ptr [rcx+14h], 8000h
0x180017043  jnz     loc_180017161
0x180017049  xorps   xmm0, xmm0
0x18001704c  movups  [rsp+8C0h+var_890], xmm0
0x180017051  movups  xmmword ptr [rsp+8C0h+var_880], xmm0
0x180017056  movups  [rsp+8C0h+var_870], xmm0
0x18001705b  mov     [rsp+8C0h+pv], 0
0x180017064  mov     [rsp+8C0h+var_858], 0
0x180017069  lea     rax, [rsp+8C0h+var_857]
0x18001706e  mov     [rbp+7C0h+var_50], rax
0x180017075  lea     rax, [rbp+7C0h+var_57]
0x18001707c  mov     [rbp+7C0h+var_40], rax
0x180017083  mov     [rsp+8C0h+var_857], 80408040h
0x18001708b  mov     [rsp+8C0h+var_853], 0
0x180017090  lea     rax, [rsp+8C0h+var_852]
0x180017095  mov     [rbp+7C0h+var_48], rax
0x18001709c  mov     r8d, 1
0x1800170a2  lea     rdx, [rsp+8C0h+pv]
0x1800170a7  call    ?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x1800170ac  mov     rdi, rax
0x1800170af  mov     rsi, [rbx+0F0h]
0x1800170b6  mov     rax, cs:?s_pfnTestUnlockData@?1??TestUnlockData@@9@4P6AXPEAUHTIPTEST__@@W4TestUnlockOptions@@PEBDPEAUTestInfo@TestInfo_ODR_guard@@@ZEA; void (*`TestUnlockData'::`2'::s_pfnTestUnlockData)(HTIPTEST__ *,TestUnlockOptions,char const *,TestInfo_ODR_guard::TestInfo *)
0x1800170bd  test    rax, rax
0x1800170c0  jnz     short loc_180017112
0x1800170c2  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x1800170c9  test    rax, rax
0x1800170cc  jnz     short loc_1800170E2
0x1800170ce  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800170d5  call    cs:__imp_GetModuleHandleW
0x1800170db  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x1800170e2  lea     rdx, aTestunlockdata; "TestUnlockData"
0x1800170e9  mov     rcx, rax; hModule
0x1800170ec  call    cs:__imp_GetProcAddress
0x1800170f2  mov     cs:?s_pfnTestUnlockData@?1??TestUnlockData@@9@4P6AXPEAUHTIPTEST__@@W4TestUnlockOptions@@PEBDPEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; void (*`TestUnlockData'::`2'::s_pfnTestUnlockData)(HTIPTEST__ *,TestUnlockOptions,char const *,TestInfo_ODR_guard::TestInfo *)
0x1800170f9  test    rax, rax
0x1800170fc  jnz     short loc_180017112
0x1800170fe  xorps   xmm0, xmm0
0x180017101  movups  [rsp+8C0h+var_890], xmm0
0x180017106  movups  xmmword ptr [rsp+8C0h+var_880], xmm0
0x18001710b  movups  [rsp+8C0h+var_870], xmm0
0x180017110  jmp     short loc_180017124
0x180017112  lea     r9, [rsp+8C0h+var_890]
0x180017117  mov     r8, rdi
0x18001711a  xor     edx, edx
0x18001711c  mov     rcx, rsi
0x18001711f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017124  mov     rdx, [rsp+8C0h+var_880]
0x180017129  mov     rax, rdx
0x18001712c  shr     rax, 20h
0x180017130  or      [rbx+40h], eax
0x180017133  mov     rcx, [rsp+8C0h+var_880+8]
0x180017138  test    rcx, rcx
0x18001713b  jnz     short loc_180017143
0x18001713d  mov     [rbx+0B8h], edx
0x180017143  mov     rax, [rsp+8C0h+pv]
0x180017148  test    rax, rax
0x18001714b  jz      short loc_18001715B
0x18001714d  mov     rcx, rax; pv
0x180017150  call    cs:__imp_CoTaskMemFree
0x180017156  mov     rcx, [rsp+8C0h+var_880+8]; pv
0x18001715b  call    cs:__imp_CoTaskMemFree
0x180017161  dec     dword ptr [rbx+0E8h]
0x180017167  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x18001716e  call    cs:__imp_LeaveCriticalSection
0x180017174  nop
0x180017175  mov     rcx, [rbp+7C0h+var_30]
0x18001717c  xor     rcx, rsp; StackCookie
0x18001717f  call    __security_check_cookie
0x180017184  add     rsp, 8A8h
0x18001718b  pop     rdi
0x18001718c  pop     rsi
0x18001718d  pop     rbx
0x18001718e  pop     rbp
0x18001718f  retn
```
