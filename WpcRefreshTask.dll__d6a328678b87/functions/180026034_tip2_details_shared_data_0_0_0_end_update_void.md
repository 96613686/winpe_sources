# tip2::details::shared_data<0,0,0>::end_update(void)

- ea: `0x180026034`
- end: `0x1800261d0`
- name: `?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ`
- size: `412`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `5`
- callee_count: `4`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180020d1c`
- `0x180020da4`
- `0x180081a34`
- `0x180081abc`
- `0x180081b44`

## callees

- `0x1800060a0`
- `0x180026034`
- `0x180027c5c`
- `0x1800ae010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002612c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002612c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180026115`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180026115`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800261ae`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800261ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026190`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002619b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026190`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002619b`

## string_xrefs

- `0x18002610e`: `kernelbase.dll`

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
0x180026034  push    rbp
0x180026036  push    rbx
0x180026037  push    rsi
0x180026038  push    rdi
0x180026039  lea     rbp, [rsp-7A8h]
0x180026041  sub     rsp, 8A8h
0x180026048  mov     rax, cs:__security_cookie
0x18002604f  xor     rax, rsp
0x180026052  mov     [rbp+7C0h+var_30], rax
0x180026059  mov     rbx, rcx
0x18002605c  bts     dword ptr [rcx+40h], 0Bh
0x180026061  cmp     qword ptr [rcx+0F0h], 0
0x180026069  jz      loc_1800261A1
0x18002606f  test    dword ptr [rcx+40h], 100h
0x180026076  jnz     loc_1800261A1
0x18002607c  test    dword ptr [rcx+14h], 8000h
0x180026083  jnz     loc_1800261A1
0x180026089  xorps   xmm0, xmm0
0x18002608c  movups  [rsp+8C0h+var_890], xmm0
0x180026091  movups  xmmword ptr [rsp+8C0h+var_880], xmm0
0x180026096  movups  [rsp+8C0h+var_870], xmm0
0x18002609b  mov     [rsp+8C0h+pv], 0
0x1800260a4  mov     [rsp+8C0h+var_858], 0
0x1800260a9  lea     rax, [rsp+8C0h+var_857]
0x1800260ae  mov     [rbp+7C0h+var_50], rax
0x1800260b5  lea     rax, [rbp+7C0h+var_57]
0x1800260bc  mov     [rbp+7C0h+var_40], rax
0x1800260c3  mov     [rsp+8C0h+var_857], 80408040h
0x1800260cb  mov     [rsp+8C0h+var_853], 0
0x1800260d0  lea     rax, [rsp+8C0h+var_852]
0x1800260d5  mov     [rbp+7C0h+var_48], rax
0x1800260dc  mov     r8d, 1
0x1800260e2  lea     rdx, [rsp+8C0h+pv]
0x1800260e7  call    ?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x1800260ec  mov     rdi, rax
0x1800260ef  mov     rsi, [rbx+0F0h]
0x1800260f6  mov     rax, cs:?s_pfnTestUnlockData@?1??TestUnlockData@@9@4P6AXPEAUHTIPTEST__@@W4TestUnlockOptions@@PEBDPEAUTestInfo@TestInfo_ODR_guard@@@ZEA; void (*`TestUnlockData'::`2'::s_pfnTestUnlockData)(HTIPTEST__ *,TestUnlockOptions,char const *,TestInfo_ODR_guard::TestInfo *)
0x1800260fd  test    rax, rax
0x180026100  jnz     short loc_180026152
0x180026102  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x180026109  test    rax, rax
0x18002610c  jnz     short loc_180026122
0x18002610e  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180026115  call    cs:__imp_GetModuleHandleW
0x18002611b  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x180026122  lea     rdx, aTestunlockdata; "TestUnlockData"
0x180026129  mov     rcx, rax; hModule
0x18002612c  call    cs:__imp_GetProcAddress
0x180026132  mov     cs:?s_pfnTestUnlockData@?1??TestUnlockData@@9@4P6AXPEAUHTIPTEST__@@W4TestUnlockOptions@@PEBDPEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; void (*`TestUnlockData'::`2'::s_pfnTestUnlockData)(HTIPTEST__ *,TestUnlockOptions,char const *,TestInfo_ODR_guard::TestInfo *)
0x180026139  test    rax, rax
0x18002613c  jnz     short loc_180026152
0x18002613e  xorps   xmm0, xmm0
0x180026141  movups  [rsp+8C0h+var_890], xmm0
0x180026146  movups  xmmword ptr [rsp+8C0h+var_880], xmm0
0x18002614b  movups  [rsp+8C0h+var_870], xmm0
0x180026150  jmp     short loc_180026164
0x180026152  lea     r9, [rsp+8C0h+var_890]
0x180026157  mov     r8, rdi
0x18002615a  xor     edx, edx
0x18002615c  mov     rcx, rsi
0x18002615f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026164  mov     rdx, [rsp+8C0h+var_880]
0x180026169  mov     rax, rdx
0x18002616c  shr     rax, 20h
0x180026170  or      [rbx+40h], eax
0x180026173  mov     rcx, [rsp+8C0h+var_880+8]
0x180026178  test    rcx, rcx
0x18002617b  jnz     short loc_180026183
0x18002617d  mov     [rbx+0B8h], edx
0x180026183  mov     rax, [rsp+8C0h+pv]
0x180026188  test    rax, rax
0x18002618b  jz      short loc_18002619B
0x18002618d  mov     rcx, rax; pv
0x180026190  call    cs:__imp_CoTaskMemFree
0x180026196  mov     rcx, [rsp+8C0h+var_880+8]; pv
0x18002619b  call    cs:__imp_CoTaskMemFree
0x1800261a1  dec     dword ptr [rbx+0E8h]
0x1800261a7  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x1800261ae  call    cs:__imp_LeaveCriticalSection
0x1800261b4  nop
0x1800261b5  mov     rcx, [rbp+7C0h+var_30]
0x1800261bc  xor     rcx, rsp; StackCookie
0x1800261bf  call    __security_check_cookie
0x1800261c4  add     rsp, 8A8h
0x1800261cb  pop     rdi
0x1800261cc  pop     rsi
0x1800261cd  pop     rbx
0x1800261ce  pop     rbp
0x1800261cf  retn
```
