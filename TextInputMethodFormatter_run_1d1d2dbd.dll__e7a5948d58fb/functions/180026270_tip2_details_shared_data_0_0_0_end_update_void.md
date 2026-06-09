# tip2::details::shared_data<0,0,0>::end_update(void)

- ea: `0x180026270`
- end: `0x18002640c`
- name: `?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ`
- size: `412`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18001a138`
- `0x18001dd10`

## callees

- `0x180002240`
- `0x180026270`
- `0x180027e30`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180026368`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180026368`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180026351`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180026351`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800263ea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800263ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800263cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800263d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800263cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800263d7`

## string_xrefs

- `0x18002634a`: `kernelbase.dll`

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
0x180026270  push    rbp
0x180026272  push    rbx
0x180026273  push    rsi
0x180026274  push    rdi
0x180026275  lea     rbp, [rsp-7A8h]
0x18002627d  sub     rsp, 8A8h
0x180026284  mov     rax, cs:__security_cookie
0x18002628b  xor     rax, rsp
0x18002628e  mov     [rbp+7C0h+var_30], rax
0x180026295  mov     rbx, rcx
0x180026298  bts     dword ptr [rcx+40h], 0Bh
0x18002629d  cmp     qword ptr [rcx+0F0h], 0
0x1800262a5  jz      loc_1800263DD
0x1800262ab  test    dword ptr [rcx+40h], 100h
0x1800262b2  jnz     loc_1800263DD
0x1800262b8  test    dword ptr [rcx+14h], 8000h
0x1800262bf  jnz     loc_1800263DD
0x1800262c5  xorps   xmm0, xmm0
0x1800262c8  movups  [rsp+8C0h+var_890], xmm0
0x1800262cd  movups  xmmword ptr [rsp+8C0h+var_880], xmm0
0x1800262d2  movups  [rsp+8C0h+var_870], xmm0
0x1800262d7  mov     [rsp+8C0h+pv], 0
0x1800262e0  mov     [rsp+8C0h+var_858], 0
0x1800262e5  lea     rax, [rsp+8C0h+var_857]
0x1800262ea  mov     [rbp+7C0h+var_50], rax
0x1800262f1  lea     rax, [rbp+7C0h+var_57]
0x1800262f8  mov     [rbp+7C0h+var_40], rax
0x1800262ff  mov     [rsp+8C0h+var_857], 80408040h
0x180026307  mov     [rsp+8C0h+var_853], 0
0x18002630c  lea     rax, [rsp+8C0h+var_852]
0x180026311  mov     [rbp+7C0h+var_48], rax
0x180026318  mov     r8d, 1
0x18002631e  lea     rdx, [rsp+8C0h+pv]
0x180026323  call    ?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x180026328  mov     rdi, rax
0x18002632b  mov     rsi, [rbx+0F0h]
0x180026332  mov     rax, cs:?s_pfnTestUnlockData@?1??TestUnlockData@@9@4P6AXPEAUHTIPTEST__@@W4TestUnlockOptions@@PEBDPEAUTestInfo@TestInfo_ODR_guard@@@ZEA; void (*`TestUnlockData'::`2'::s_pfnTestUnlockData)(HTIPTEST__ *,TestUnlockOptions,char const *,TestInfo_ODR_guard::TestInfo *)
0x180026339  test    rax, rax
0x18002633c  jnz     short loc_18002638E
0x18002633e  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x180026345  test    rax, rax
0x180026348  jnz     short loc_18002635E
0x18002634a  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180026351  call    cs:__imp_GetModuleHandleW
0x180026357  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x18002635e  lea     rdx, aTestunlockdata; "TestUnlockData"
0x180026365  mov     rcx, rax; hModule
0x180026368  call    cs:__imp_GetProcAddress
0x18002636e  mov     cs:?s_pfnTestUnlockData@?1??TestUnlockData@@9@4P6AXPEAUHTIPTEST__@@W4TestUnlockOptions@@PEBDPEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; void (*`TestUnlockData'::`2'::s_pfnTestUnlockData)(HTIPTEST__ *,TestUnlockOptions,char const *,TestInfo_ODR_guard::TestInfo *)
0x180026375  test    rax, rax
0x180026378  jnz     short loc_18002638E
0x18002637a  xorps   xmm0, xmm0
0x18002637d  movups  [rsp+8C0h+var_890], xmm0
0x180026382  movups  xmmword ptr [rsp+8C0h+var_880], xmm0
0x180026387  movups  [rsp+8C0h+var_870], xmm0
0x18002638c  jmp     short loc_1800263A0
0x18002638e  lea     r9, [rsp+8C0h+var_890]
0x180026393  mov     r8, rdi
0x180026396  xor     edx, edx
0x180026398  mov     rcx, rsi
0x18002639b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800263a0  mov     rdx, [rsp+8C0h+var_880]
0x1800263a5  mov     rax, rdx
0x1800263a8  shr     rax, 20h
0x1800263ac  or      [rbx+40h], eax
0x1800263af  mov     rcx, [rsp+8C0h+var_880+8]
0x1800263b4  test    rcx, rcx
0x1800263b7  jnz     short loc_1800263BF
0x1800263b9  mov     [rbx+0B8h], edx
0x1800263bf  mov     rax, [rsp+8C0h+pv]
0x1800263c4  test    rax, rax
0x1800263c7  jz      short loc_1800263D7
0x1800263c9  mov     rcx, rax; pv
0x1800263cc  call    cs:__imp_CoTaskMemFree
0x1800263d2  mov     rcx, [rsp+8C0h+var_880+8]; pv
0x1800263d7  call    cs:__imp_CoTaskMemFree
0x1800263dd  dec     dword ptr [rbx+0E8h]
0x1800263e3  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x1800263ea  call    cs:__imp_LeaveCriticalSection
0x1800263f0  nop
0x1800263f1  mov     rcx, [rbp+7C0h+var_30]
0x1800263f8  xor     rcx, rsp; StackCookie
0x1800263fb  call    __security_check_cookie
0x180026400  add     rsp, 8A8h
0x180026407  pop     rdi
0x180026408  pop     rsi
0x180026409  pop     rbx
0x18002640a  pop     rbp
0x18002640b  retn
```
