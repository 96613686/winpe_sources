# tip2::details::shared_data<0,0,0>::end_update(void)

- ea: `0x1400565e0`
- end: `0x14005677c`
- name: `?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ`
- size: `412`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x140052d0c`

## callees

- `0x1400042f0`
- `0x1400565e0`
- `0x140057c30`
- `0x14005d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400566d8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400566d8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400566c1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400566c1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14005675a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14005675a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14005673c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140056747`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14005673c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140056747`

## string_xrefs

- `0x1400566ba`: `kernelbase.dll`

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
0x1400565e0  push    rbp
0x1400565e2  push    rbx
0x1400565e3  push    rsi
0x1400565e4  push    rdi
0x1400565e5  lea     rbp, [rsp-7A8h]
0x1400565ed  sub     rsp, 8A8h
0x1400565f4  mov     rax, cs:__security_cookie
0x1400565fb  xor     rax, rsp
0x1400565fe  mov     [rbp+7C0h+var_30], rax
0x140056605  mov     rbx, rcx
0x140056608  bts     dword ptr [rcx+40h], 0Bh
0x14005660d  cmp     qword ptr [rcx+0F0h], 0
0x140056615  jz      loc_14005674D
0x14005661b  test    dword ptr [rcx+40h], 100h
0x140056622  jnz     loc_14005674D
0x140056628  test    dword ptr [rcx+14h], 8000h
0x14005662f  jnz     loc_14005674D
0x140056635  xorps   xmm0, xmm0
0x140056638  movups  [rsp+8C0h+var_890], xmm0
0x14005663d  movups  xmmword ptr [rsp+8C0h+var_880], xmm0
0x140056642  movups  [rsp+8C0h+var_870], xmm0
0x140056647  mov     [rsp+8C0h+pv], 0
0x140056650  mov     [rsp+8C0h+var_858], 0
0x140056655  lea     rax, [rsp+8C0h+var_857]
0x14005665a  mov     [rbp+7C0h+var_50], rax
0x140056661  lea     rax, [rbp+7C0h+var_57]
0x140056668  mov     [rbp+7C0h+var_40], rax
0x14005666f  mov     [rsp+8C0h+var_857], 80408040h
0x140056677  mov     [rsp+8C0h+var_853], 0
0x14005667c  lea     rax, [rsp+8C0h+var_852]
0x140056681  mov     [rbp+7C0h+var_48], rax
0x140056688  mov     r8d, 1
0x14005668e  lea     rdx, [rsp+8C0h+pv]
0x140056693  call    ?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x140056698  mov     rdi, rax
0x14005669b  mov     rsi, [rbx+0F0h]
0x1400566a2  mov     rax, cs:?s_pfnTestUnlockData@?1??TestUnlockData@@9@4P6AXPEAUHTIPTEST__@@W4TestUnlockOptions@@PEBDPEAUTestInfo@TestInfo_ODR_guard@@@ZEA; void (*`TestUnlockData'::`2'::s_pfnTestUnlockData)(HTIPTEST__ *,TestUnlockOptions,char const *,TestInfo_ODR_guard::TestInfo *)
0x1400566a9  test    rax, rax
0x1400566ac  jnz     short loc_1400566FE
0x1400566ae  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x1400566b5  test    rax, rax
0x1400566b8  jnz     short loc_1400566CE
0x1400566ba  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1400566c1  call    cs:__imp_GetModuleHandleW
0x1400566c7  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x1400566ce  lea     rdx, aTestunlockdata; "TestUnlockData"
0x1400566d5  mov     rcx, rax; hModule
0x1400566d8  call    cs:__imp_GetProcAddress
0x1400566de  mov     cs:?s_pfnTestUnlockData@?1??TestUnlockData@@9@4P6AXPEAUHTIPTEST__@@W4TestUnlockOptions@@PEBDPEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; void (*`TestUnlockData'::`2'::s_pfnTestUnlockData)(HTIPTEST__ *,TestUnlockOptions,char const *,TestInfo_ODR_guard::TestInfo *)
0x1400566e5  test    rax, rax
0x1400566e8  jnz     short loc_1400566FE
0x1400566ea  xorps   xmm0, xmm0
0x1400566ed  movups  [rsp+8C0h+var_890], xmm0
0x1400566f2  movups  xmmword ptr [rsp+8C0h+var_880], xmm0
0x1400566f7  movups  [rsp+8C0h+var_870], xmm0
0x1400566fc  jmp     short loc_140056710
0x1400566fe  lea     r9, [rsp+8C0h+var_890]
0x140056703  mov     r8, rdi
0x140056706  xor     edx, edx
0x140056708  mov     rcx, rsi
0x14005670b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140056710  mov     rdx, [rsp+8C0h+var_880]
0x140056715  mov     rax, rdx
0x140056718  shr     rax, 20h
0x14005671c  or      [rbx+40h], eax
0x14005671f  mov     rcx, [rsp+8C0h+var_880+8]
0x140056724  test    rcx, rcx
0x140056727  jnz     short loc_14005672F
0x140056729  mov     [rbx+0B8h], edx
0x14005672f  mov     rax, [rsp+8C0h+pv]
0x140056734  test    rax, rax
0x140056737  jz      short loc_140056747
0x140056739  mov     rcx, rax; pv
0x14005673c  call    cs:__imp_CoTaskMemFree
0x140056742  mov     rcx, [rsp+8C0h+var_880+8]; pv
0x140056747  call    cs:__imp_CoTaskMemFree
0x14005674d  dec     dword ptr [rbx+0E8h]
0x140056753  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x14005675a  call    cs:__imp_LeaveCriticalSection
0x140056760  nop
0x140056761  mov     rcx, [rbp+7C0h+var_30]
0x140056768  xor     rcx, rsp; StackCookie
0x14005676b  call    __security_check_cookie
0x140056770  add     rsp, 8A8h
0x140056777  pop     rdi
0x140056778  pop     rsi
0x140056779  pop     rbx
0x14005677a  pop     rbp
0x14005677b  retn
```
