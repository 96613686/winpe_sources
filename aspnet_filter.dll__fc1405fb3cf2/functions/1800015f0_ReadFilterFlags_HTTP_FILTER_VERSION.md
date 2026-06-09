# ReadFilterFlags(_HTTP_FILTER_VERSION *)

- ea: `0x1800015f0`
- end: `0x1800016f3`
- name: `?ReadFilterFlags@@YAXPEAU_HTTP_FILTER_VERSION@@@Z`
- size: `259`
- prototype: `void __fastcall(struct _HTTP_FILTER_VERSION *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180001ad0`

## callees

- `0x1800015f0`
- `0x1800016f4`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x18000168f`
- `ADVAPI32!RegQueryValueExW` at `0x1800016c8`
- `ADVAPI32!RegQueryValueExW` at `0x18000168f`
- `ADVAPI32!RegQueryValueExW` at `0x1800016c8`
- `ADVAPI32!RegOpenKeyExW` at `0x18000164e`
- `ADVAPI32!RegOpenKeyExW` at `0x18000164e`
- `ADVAPI32!RegCloseKey` at `0x1800016e7`
- `ADVAPI32!RegCloseKey` at `0x1800016e7`

## string_xrefs

- `0x1800016b2`: `StopProtectedDirectoryFiltering`

## pseudocode

```c
void __fastcall ReadFilterFlags(struct _HTTP_FILTER_VERSION *a1)
{
  unsigned int dwServerFilterVersion_high; // eax
  int Data; // [rsp+40h] [rbp+10h] BYREF
  unsigned int v3; // [rsp+48h] [rbp+18h] BYREF
  DWORD cbData; // [rsp+50h] [rbp+20h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+28h] BYREF

  hKey = 0;
  v3 = 0;
  dwServerFilterVersion_high = HIWORD(a1->dwServerFilterVersion);
  if ( dwServerFilterVersion_high <= 6 )
  {
    if ( dwServerFilterVersion_high < 6 )
      g_FilterFlags &= ~1u;
  }
  else if ( (int)ReadIisRequestFilteringSection(&v3) >= 0 )
  {
    g_FilterFlags &= ~v3;
  }
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\ASP.NET", 0, 0x20019u, &hKey) )
  {
    cbData = 4;
    if ( (g_FilterFlags & 1) != 0 && !RegQueryValueExW(hKey, L"StopBinFiltering", 0, 0, (LPBYTE)&Data, &cbData) && Data )
      g_FilterFlags &= ~1u;
    if ( !RegQueryValueExW(hKey, L"StopProtectedDirectoryFiltering", 0, 0, (LPBYTE)&Data, &cbData) && Data )
      g_FilterFlags &= ~2u;
  }
  if ( hKey )
    RegCloseKey(hKey);
}

```

## disassembly

```asm
0x1800015f0  push    rbp
0x1800015f2  mov     rbp, rsp
0x1800015f5  sub     rsp, 30h
0x1800015f9  and     [rbp+hKey], 0
0x1800015fe  and     [rbp+arg_8], 0
0x180001602  movzx   eax, word ptr [rcx+2]
0x180001606  cmp     eax, 6
0x180001609  jbe     short loc_180001625
0x18000160b  lea     rcx, [rbp+arg_8]; unsigned int *
0x18000160f  call    ?ReadIisRequestFilteringSection@@YAJPEAK@Z; ReadIisRequestFilteringSection(ulong *)
0x180001614  test    eax, eax
0x180001616  js      short loc_18000162E
0x180001618  mov     eax, [rbp+arg_8]
0x18000161b  not     eax
0x18000161d  and     cs:?g_FilterFlags@@3HA, eax; int g_FilterFlags
0x180001623  jmp     short loc_18000162E
0x180001625  jnb     short loc_18000162E
0x180001627  and     cs:?g_FilterFlags@@3HA, 0FFFFFFFEh; int g_FilterFlags
0x18000162e  lea     rax, [rbp+hKey]
0x180001632  mov     r9d, 20019h; samDesired
0x180001638  xor     r8d, r8d; ulOptions
0x18000163b  mov     [rsp+30h+phkResult], rax; phkResult
0x180001640  lea     rdx, SubKey; "Software\\Microsoft\\ASP.NET"
0x180001647  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000164e  call    cs:__imp_RegOpenKeyExW
0x180001654  test    eax, eax
0x180001656  jnz     loc_1800016DE
0x18000165c  test    byte ptr cs:?g_FilterFlags@@3HA, 1; int g_FilterFlags
0x180001663  mov     [rbp+cbData], 4
0x18000166a  jz      short loc_1800016A5
0x18000166c  mov     rcx, [rbp+hKey]; hKey
0x180001670  lea     rax, [rbp+cbData]
0x180001674  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180001679  lea     rdx, ValueName; "StopBinFiltering"
0x180001680  lea     rax, [rbp+Data]
0x180001684  xor     r9d, r9d; lpType
0x180001687  xor     r8d, r8d; lpReserved
0x18000168a  mov     [rsp+30h+phkResult], rax; lpData
0x18000168f  call    cs:__imp_RegQueryValueExW
0x180001695  test    eax, eax
0x180001697  jnz     short loc_1800016A5
0x180001699  cmp     [rbp+Data], eax
0x18000169c  jz      short loc_1800016A5
0x18000169e  and     cs:?g_FilterFlags@@3HA, 0FFFFFFFEh; int g_FilterFlags
0x1800016a5  mov     rcx, [rbp+hKey]; hKey
0x1800016a9  lea     rax, [rbp+cbData]
0x1800016ad  mov     [rsp+30h+lpcbData], rax; lpcbData
0x1800016b2  lea     rdx, aStopprotectedd; "StopProtectedDirectoryFiltering"
0x1800016b9  lea     rax, [rbp+Data]
0x1800016bd  xor     r9d, r9d; lpType
0x1800016c0  xor     r8d, r8d; lpReserved
0x1800016c3  mov     [rsp+30h+phkResult], rax; lpData
0x1800016c8  call    cs:__imp_RegQueryValueExW
0x1800016ce  test    eax, eax
0x1800016d0  jnz     short loc_1800016DE
0x1800016d2  cmp     [rbp+Data], eax
0x1800016d5  jz      short loc_1800016DE
0x1800016d7  and     cs:?g_FilterFlags@@3HA, 0FFFFFFFDh; int g_FilterFlags
0x1800016de  mov     rcx, [rbp+hKey]; hKey
0x1800016e2  test    rcx, rcx
0x1800016e5  jz      short loc_1800016ED
0x1800016e7  call    cs:__imp_RegCloseKey
0x1800016ed  add     rsp, 30h
0x1800016f1  pop     rbp
0x1800016f2  retn
```
