# tip2::details::shared_data<0,0,0>::end_update(void)

- ea: `0x180019c90`
- end: `0x180019e45`
- name: `?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ`
- size: `437`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `6`
- callee_count: `5`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800190e0`
- `0x180019c40`
- `0x180052c90`
- `0x180053610`
- `0x1800583b0`
- `0x18005bc90`

## callees

- `0x180010a20`
- `0x180019c90`
- `0x18004c070`
- `0x18005e260`
- `0x18005e2c0`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180019d9c`
- `KERNEL32!GetProcAddress` at `0x180019d9c`
- `KERNEL32!GetModuleHandleW` at `0x180019d85`
- `KERNEL32!GetModuleHandleW` at `0x180019d85`
- `KERNEL32!LeaveCriticalSection` at `0x180019e19`
- `KERNEL32!LeaveCriticalSection` at `0x180019e19`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019e01`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019e0c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019e01`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019e0c`

## string_xrefs

- `0x180019d7e`: `kernelbase.dll`

## pseudocode

```c
void __fastcall tip2::details::shared_data<0,0,0>::end_update(__int64 a1)
{
  int v2; // eax
  __int64 v3; // rdi
  __int64 v4; // rsi
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  int v7; // edx
  void *v8; // rcx
  __int128 v9; // [rsp+30h] [rbp-878h] BYREF
  LPVOID v10[2]; // [rsp+40h] [rbp-868h]
  __int128 v11; // [rsp+50h] [rbp-858h]
  LPVOID pv; // [rsp+60h] [rbp-848h] BYREF
  char v13; // [rsp+68h] [rbp-840h]
  int v14; // [rsp+69h] [rbp-83Fh] BYREF
  char v15; // [rsp+6Dh] [rbp-83Bh]
  _BYTE v16[2050]; // [rsp+6Eh] [rbp-83Ah] BYREF
  int *v17; // [rsp+870h] [rbp-38h]
  _BYTE *v18; // [rsp+878h] [rbp-30h]
  _BYTE *v19; // [rsp+880h] [rbp-28h]

  v2 = *(_DWORD *)(a1 + 64) | 0x800;
  *(_DWORD *)(a1 + 64) = v2;
  if ( *(_QWORD *)(a1 + 232) && (v2 & 0x100) == 0 )
  {
    v9 = 0;
    *(_OWORD *)v10 = 0;
    v11 = 0;
    memset(v16, 0, sizeof(v16));
    v3 = 0;
    pv = 0;
    v13 = 0;
    v17 = &v14;
    v19 = &v16[2043];
    v14 = -2143256512;
    v15 = 0;
    v18 = v16;
    if ( (*(_DWORD *)(a1 + 20) & 0x8000) == 0 )
      v3 = tip2::details::shared_data<0,0,0>::serialize_data(a1, &pv, 1);
    v4 = *(_QWORD *)(a1 + 232);
    ProcAddress = (FARPROC)`TestUnlockData'::`2'::s_pfnTestUnlockData;
    if ( `TestUnlockData'::`2'::s_pfnTestUnlockData )
      goto LABEL_10;
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
LABEL_10:
      ((void (__fastcall *)(__int64, _QWORD, __int64, __int128 *))ProcAddress)(v4, 0, v3, &v9);
    }
    else
    {
      v9 = 0;
      *(_OWORD *)v10 = 0;
      v11 = 0;
    }
    v7 = (int)v10[0];
    *(_DWORD *)(a1 + 64) |= HIDWORD(v10[0]);
    v8 = v10[1];
    if ( !v10[1] )
      *(_DWORD *)(a1 + 184) = v7;
    if ( pv )
    {
      CoTaskMemFree(pv);
      v8 = v10[1];
    }
    CoTaskMemFree(v8);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 192));
}

```

## disassembly

```asm
0x180019c90  mov     [rsp+arg_8], rbx
0x180019c95  mov     [rsp+arg_10], rsi
0x180019c9a  push    rdi
0x180019c9b  sub     rsp, 8A0h
0x180019ca2  mov     rax, cs:__security_cookie
0x180019ca9  xor     rax, rsp
0x180019cac  mov     [rsp+8A8h+var_18], rax
0x180019cb4  mov     rbx, rcx
0x180019cb7  mov     eax, [rcx+40h]
0x180019cba  bts     eax, 0Bh
0x180019cbe  mov     [rcx+40h], eax
0x180019cc1  cmp     qword ptr [rcx+0E8h], 0
0x180019cc9  jz      loc_180019E12
0x180019ccf  bt      eax, 8
0x180019cd3  jb      loc_180019E12
0x180019cd9  xorps   xmm0, xmm0
0x180019cdc  movups  [rsp+8A8h+var_878], xmm0
0x180019ce1  movups  xmmword ptr [rsp+8A8h+var_868], xmm0
0x180019ce6  movups  [rsp+8A8h+var_858], xmm0
0x180019ceb  xor     edx, edx; Val
0x180019ced  mov     r8d, 802h; Size
0x180019cf3  lea     rcx, [rsp+8A8h+var_83A]; void *
0x180019cf8  call    memset
0x180019cfd  xor     edi, edi
0x180019cff  mov     [rsp+8A8h+pv], rdi
0x180019d04  mov     [rsp+8A8h+var_840], dil
0x180019d09  lea     rax, [rsp+8A8h+var_83F]
0x180019d0e  mov     [rsp+8A8h+var_38], rax
0x180019d16  lea     rax, [rsp+8A8h+var_3F]
0x180019d1e  mov     [rsp+8A8h+var_28], rax
0x180019d26  mov     [rsp+8A8h+var_83F], 80408040h
0x180019d2e  mov     [rsp+8A8h+var_83B], dil
0x180019d33  lea     rax, [rsp+8A8h+var_83A]
0x180019d38  mov     [rsp+8A8h+var_30], rax
0x180019d40  test    dword ptr [rbx+14h], 8000h
0x180019d47  jnz     short loc_180019D5F
0x180019d49  mov     r8d, 1
0x180019d4f  lea     rdx, [rsp+8A8h+pv]
0x180019d54  mov     rcx, rbx
0x180019d57  call    ?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x180019d5c  mov     rdi, rax
0x180019d5f  mov     rsi, [rbx+0E8h]
0x180019d66  mov     rax, cs:?s_pfnTestUnlockData@?1??TestUnlockData@@9@4P6AXPEAUHTIPTEST__@@W4TestUnlockOptions@@PEBDPEAUTestInfo@TestInfo_ODR_guard@@@ZEA; void (*`TestUnlockData'::`2'::s_pfnTestUnlockData)(HTIPTEST__ *,TestUnlockOptions,char const *,TestInfo_ODR_guard::TestInfo *)
0x180019d6d  test    rax, rax
0x180019d70  jnz     short loc_180019DC2
0x180019d72  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x180019d79  test    rax, rax
0x180019d7c  jnz     short loc_180019D92
0x180019d7e  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180019d85  call    cs:__imp_GetModuleHandleW
0x180019d8b  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x180019d92  lea     rdx, aTestunlockdata; "TestUnlockData"
0x180019d99  mov     rcx, rax; hModule
0x180019d9c  call    cs:__imp_GetProcAddress
0x180019da2  mov     cs:?s_pfnTestUnlockData@?1??TestUnlockData@@9@4P6AXPEAUHTIPTEST__@@W4TestUnlockOptions@@PEBDPEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; void (*`TestUnlockData'::`2'::s_pfnTestUnlockData)(HTIPTEST__ *,TestUnlockOptions,char const *,TestInfo_ODR_guard::TestInfo *)
0x180019da9  test    rax, rax
0x180019dac  jnz     short loc_180019DC2
0x180019dae  xorps   xmm0, xmm0
0x180019db1  movups  [rsp+8A8h+var_878], xmm0
0x180019db6  movups  xmmword ptr [rsp+8A8h+var_868], xmm0
0x180019dbb  movups  [rsp+8A8h+var_858], xmm0
0x180019dc0  jmp     short loc_180019DD5
0x180019dc2  lea     r9, [rsp+8A8h+var_878]
0x180019dc7  mov     r8, rdi
0x180019dca  xor     edx, edx
0x180019dcc  mov     rcx, rsi
0x180019dcf  call    cs:__guard_dispatch_icall_fptr
0x180019dd5  mov     rdx, [rsp+8A8h+var_868]
0x180019dda  mov     rax, rdx
0x180019ddd  shr     rax, 20h
0x180019de1  or      [rbx+40h], eax
0x180019de4  mov     rcx, [rsp+8A8h+var_868+8]
0x180019de9  test    rcx, rcx
0x180019dec  jnz     short loc_180019DF4
0x180019dee  mov     [rbx+0B8h], edx
0x180019df4  mov     rax, [rsp+8A8h+pv]
0x180019df9  test    rax, rax
0x180019dfc  jz      short loc_180019E0C
0x180019dfe  mov     rcx, rax; pv
0x180019e01  call    cs:__imp_CoTaskMemFree
0x180019e07  mov     rcx, [rsp+8A8h+var_868+8]; pv
0x180019e0c  call    cs:__imp_CoTaskMemFree
0x180019e12  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x180019e19  call    cs:__imp_LeaveCriticalSection
0x180019e1f  nop
0x180019e20  mov     rcx, [rsp+8A8h+var_18]
0x180019e28  xor     rcx, rsp; StackCookie
0x180019e2b  call    __security_check_cookie
0x180019e30  lea     r11, [rsp+8A8h+var_8]
0x180019e38  mov     rbx, [r11+18h]
0x180019e3c  mov     rsi, [r11+20h]
0x180019e40  mov     rsp, r11
0x180019e43  pop     rdi
0x180019e44  retn
```
