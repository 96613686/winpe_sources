# WaasMedic::RegValueExists(HKEY__ *,ushort const *,ushort const *,ulong,WaasMedic::RegistryHiveType)

- ea: `0x180029780`
- end: `0x180029897`
- name: `?RegValueExists@WaasMedic@@YAJPEAUHKEY__@@PEBG1KW4RegistryHiveType@1@@Z`
- size: `279`
- prototype: `int __high(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned int, enum WaasMedic::RegistryHiveType)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callers

- `0x180026424`

## callees

- `0x180029780`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x1800297d9`
- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x1800297d9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002985e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002985e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180029825`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180029825`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002987f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002987f`

## pseudocode

```c
__int64 __fastcall WaasMedic::RegValueExists(__int64 a1, const WCHAR *a2, const WCHAR *a3)
{
  REGSAM v5; // ebx
  LSTATUS v6; // eax
  unsigned int v7; // ebx
  bool v8; // cc
  struct _SYSTEM_INFO SystemInfo; // [rsp+30h] [rbp-30h] BYREF
  HKEY hKey; // [rsp+80h] [rbp+20h] BYREF
  DWORD Type; // [rsp+98h] [rbp+38h] BYREF

  hKey = 0;
  Type = 0;
  v5 = 1;
  if ( !dword_180098D58 )
  {
    dword_180098D54 = 0;
    memset(&SystemInfo, 0, sizeof(SystemInfo));
    GetNativeSystemInfo(&SystemInfo);
    if ( SystemInfo.wProcessorArchitecture == 6 || SystemInfo.wProcessorArchitecture == 9 )
      dword_180098D54 = 1;
    dword_180098D58 = 1;
  }
  if ( dword_180098D54 )
    v5 = 257;
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, v5, &hKey);
  v7 = v6;
  v8 = v6 <= 0;
  if ( v6 || (v6 = RegQueryValueExW(hKey, a3, 0, &Type, 0, 0), v7 = v6, v8 = v6 <= 0, v6) )
  {
    if ( !v8 )
      v7 = (unsigned __int16)v6 | 0x80070000;
  }
  else if ( Type != 4 )
  {
    v7 = -2147024883;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v7;
}

```

## disassembly

```asm
0x180029780  mov     [rsp-18h+arg_8], rbx
0x180029785  mov     [rsp-18h+Type], r9d
0x18002978a  mov     [rsp-18h+hKey], rcx
0x18002978f  push    rbp
0x180029790  push    rsi
0x180029791  push    rdi
0x180029792  mov     rbp, rsp
0x180029795  sub     rsp, 60h
0x180029799  cmp     cs:dword_180098D58, 0
0x1800297a0  mov     rdi, r8
0x1800297a3  mov     rsi, rdx
0x1800297a6  mov     [rbp+hKey], 0
0x1800297ae  mov     [rbp+Type], 0
0x1800297b5  mov     ebx, 1
0x1800297ba  jnz     short loc_1800297FD
0x1800297bc  xorps   xmm0, xmm0
0x1800297bf  mov     cs:dword_180098D54, 0
0x1800297c9  lea     rcx, [rbp+SystemInfo]; lpSystemInfo
0x1800297cd  movups  xmmword ptr [rbp+SystemInfo], xmm0
0x1800297d1  movups  xmmword ptr [rbp+SystemInfo.lpMaximumApplicationAddress], xmm0
0x1800297d5  movups  xmmword ptr [rbp+SystemInfo.dwNumberOfProcessors], xmm0
0x1800297d9  call    cs:__imp_GetNativeSystemInfo
0x1800297df  lea     eax, [rbx+5]
0x1800297e2  cmp     ax, word ptr [rbp+SystemInfo]
0x1800297e6  jz      short loc_1800297F1
0x1800297e8  lea     eax, [rbx+8]
0x1800297eb  cmp     ax, word ptr [rbp+SystemInfo]
0x1800297ef  jnz     short loc_1800297F7
0x1800297f1  mov     cs:dword_180098D54, ebx
0x1800297f7  mov     cs:dword_180098D58, ebx
0x1800297fd  cmp     cs:dword_180098D54, 0
0x180029804  mov     eax, 101h
0x180029809  cmovnz  ebx, eax
0x18002980c  lea     rax, [rbp+hKey]
0x180029810  mov     r9d, ebx; samDesired
0x180029813  xor     r8d, r8d; ulOptions
0x180029816  mov     [rsp+60h+phkResult], rax; phkResult
0x18002981b  mov     rdx, rsi; lpSubKey
0x18002981e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180029825  call    cs:__imp_RegOpenKeyExW
0x18002982b  mov     ebx, eax
0x18002982d  test    eax, eax
0x18002982f  jz      short loc_18002983E
0x180029831  jle     short loc_180029876
0x180029833  movzx   ebx, ax
0x180029836  or      ebx, 80070000h
0x18002983c  jmp     short loc_180029876
0x18002983e  mov     rcx, [rbp+hKey]; hKey
0x180029842  lea     r9, [rbp+Type]; lpType
0x180029846  mov     [rsp+60h+lpcbData], 0; lpcbData
0x18002984f  xor     r8d, r8d; lpReserved
0x180029852  mov     rdx, rdi; lpValueName
0x180029855  mov     [rsp+60h+phkResult], 0; lpData
0x18002985e  call    cs:__imp_RegQueryValueExW
0x180029864  mov     ebx, eax
0x180029866  test    eax, eax
0x180029868  jnz     short loc_180029831
0x18002986a  cmp     [rbp+Type], 4
0x18002986e  mov     eax, 8007000Dh
0x180029873  cmovnz  ebx, eax
0x180029876  mov     rcx, [rbp+hKey]; hKey
0x18002987a  test    rcx, rcx
0x18002987d  jz      short loc_180029885
0x18002987f  call    cs:__imp_RegCloseKey
0x180029885  mov     eax, ebx
0x180029887  mov     rbx, [rsp+60h+arg_8]
0x18002988f  add     rsp, 60h
0x180029893  pop     rdi
0x180029894  pop     rsi
0x180029895  pop     rbp
0x180029896  retn
```
