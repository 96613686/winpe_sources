# tip2::details::shared_data<0,0,0>::end_update(void)

- ea: `0x18000a770`
- end: `0x18000a925`
- name: `?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ`
- size: `437`
- prototype: `void __fastcall(__int64)`
- caller_count: `3`
- callee_count: `5`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180007410`
- `0x180008480`
- `0x1800084d0`

## callees

- `0x18000a770`
- `0x18000aec0`
- `0x1800181b0`
- `0x18001cdf0`
- `0x18001d600`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000a87c`
- `KERNEL32!GetProcAddress` at `0x18000a87c`
- `KERNEL32!GetModuleHandleW` at `0x18000a865`
- `KERNEL32!GetModuleHandleW` at `0x18000a865`
- `KERNEL32!LeaveCriticalSection` at `0x18000a8f9`
- `KERNEL32!LeaveCriticalSection` at `0x18000a8f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a8e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a8ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a8e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a8ec`

## string_xrefs

- `0x18000a85e`: `kernelbase.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x18000a770  mov     [rsp+arg_8], rbx
0x18000a775  mov     [rsp+arg_10], rsi
0x18000a77a  push    rdi
0x18000a77b  sub     rsp, 8A0h
0x18000a782  mov     rax, cs:__security_cookie
0x18000a789  xor     rax, rsp
0x18000a78c  mov     [rsp+8A8h+var_18], rax
0x18000a794  mov     rbx, rcx
0x18000a797  mov     eax, [rcx+40h]
0x18000a79a  bts     eax, 0Bh
0x18000a79e  mov     [rcx+40h], eax
0x18000a7a1  cmp     qword ptr [rcx+0E8h], 0
0x18000a7a9  jz      loc_18000A8F2
0x18000a7af  bt      eax, 8
0x18000a7b3  jb      loc_18000A8F2
0x18000a7b9  xorps   xmm0, xmm0
0x18000a7bc  movups  [rsp+8A8h+var_878], xmm0
0x18000a7c1  movups  xmmword ptr [rsp+8A8h+var_868], xmm0
0x18000a7c6  movups  [rsp+8A8h+var_858], xmm0
0x18000a7cb  xor     edx, edx; Val
0x18000a7cd  mov     r8d, 802h; Size
0x18000a7d3  lea     rcx, [rsp+8A8h+var_83A]; void *
0x18000a7d8  call    memset
0x18000a7dd  xor     edi, edi
0x18000a7df  mov     [rsp+8A8h+pv], rdi
0x18000a7e4  mov     [rsp+8A8h+var_840], dil
0x18000a7e9  lea     rax, [rsp+8A8h+var_83F]
0x18000a7ee  mov     [rsp+8A8h+var_38], rax
0x18000a7f6  lea     rax, [rsp+8A8h+var_3F]
0x18000a7fe  mov     [rsp+8A8h+var_28], rax
0x18000a806  mov     [rsp+8A8h+var_83F], 80408040h
0x18000a80e  mov     [rsp+8A8h+var_83B], dil
0x18000a813  lea     rax, [rsp+8A8h+var_83A]
0x18000a818  mov     [rsp+8A8h+var_30], rax
0x18000a820  test    dword ptr [rbx+14h], 8000h
0x18000a827  jnz     short loc_18000A83F
0x18000a829  mov     r8d, 1
0x18000a82f  lea     rdx, [rsp+8A8h+pv]
0x18000a834  mov     rcx, rbx
0x18000a837  call    ?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x18000a83c  mov     rdi, rax
0x18000a83f  mov     rsi, [rbx+0E8h]
0x18000a846  mov     rax, cs:?s_pfnTestUnlockData@?1??TestUnlockData@@9@4P6AXPEAUHTIPTEST__@@W4TestUnlockOptions@@PEBDPEAUTestInfo@TestInfo_ODR_guard@@@ZEA; void (*`TestUnlockData'::`2'::s_pfnTestUnlockData)(HTIPTEST__ *,TestUnlockOptions,char const *,TestInfo_ODR_guard::TestInfo *)
0x18000a84d  test    rax, rax
0x18000a850  jnz     short loc_18000A8A2
0x18000a852  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x18000a859  test    rax, rax
0x18000a85c  jnz     short loc_18000A872
0x18000a85e  lea     rcx, ModuleName; "kernelbase.dll"
0x18000a865  call    cs:__imp_GetModuleHandleW
0x18000a86b  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x18000a872  lea     rdx, ProcName; "TestUnlockData"
0x18000a879  mov     rcx, rax; hModule
0x18000a87c  call    cs:__imp_GetProcAddress
0x18000a882  mov     cs:?s_pfnTestUnlockData@?1??TestUnlockData@@9@4P6AXPEAUHTIPTEST__@@W4TestUnlockOptions@@PEBDPEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; void (*`TestUnlockData'::`2'::s_pfnTestUnlockData)(HTIPTEST__ *,TestUnlockOptions,char const *,TestInfo_ODR_guard::TestInfo *)
0x18000a889  test    rax, rax
0x18000a88c  jnz     short loc_18000A8A2
0x18000a88e  xorps   xmm0, xmm0
0x18000a891  movups  [rsp+8A8h+var_878], xmm0
0x18000a896  movups  xmmword ptr [rsp+8A8h+var_868], xmm0
0x18000a89b  movups  [rsp+8A8h+var_858], xmm0
0x18000a8a0  jmp     short loc_18000A8B5
0x18000a8a2  lea     r9, [rsp+8A8h+var_878]
0x18000a8a7  mov     r8, rdi
0x18000a8aa  xor     edx, edx
0x18000a8ac  mov     rcx, rsi
0x18000a8af  call    cs:__guard_dispatch_icall_fptr
0x18000a8b5  mov     rdx, [rsp+8A8h+var_868]
0x18000a8ba  mov     rax, rdx
0x18000a8bd  shr     rax, 20h
0x18000a8c1  or      [rbx+40h], eax
0x18000a8c4  mov     rcx, [rsp+8A8h+var_868+8]
0x18000a8c9  test    rcx, rcx
0x18000a8cc  jnz     short loc_18000A8D4
0x18000a8ce  mov     [rbx+0B8h], edx
0x18000a8d4  mov     rax, [rsp+8A8h+pv]
0x18000a8d9  test    rax, rax
0x18000a8dc  jz      short loc_18000A8EC
0x18000a8de  mov     rcx, rax; pv
0x18000a8e1  call    cs:__imp_CoTaskMemFree
0x18000a8e7  mov     rcx, [rsp+8A8h+var_868+8]; pv
0x18000a8ec  call    cs:__imp_CoTaskMemFree
0x18000a8f2  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x18000a8f9  call    cs:__imp_LeaveCriticalSection
0x18000a8ff  nop
0x18000a900  mov     rcx, [rsp+8A8h+var_18]
0x18000a908  xor     rcx, rsp; StackCookie
0x18000a90b  call    __security_check_cookie
0x18000a910  lea     r11, [rsp+8A8h+var_8]
0x18000a918  mov     rbx, [r11+18h]
0x18000a91c  mov     rsi, [r11+20h]
0x18000a920  mov     rsp, r11
0x18000a923  pop     rdi
0x18000a924  retn
```
