# WaasMedic::RegValueExists(HKEY__ *,ushort const *,ushort const *,ulong,WaasMedic::RegistryHiveType)

- ea: `0x1800276d8`
- end: `0x1800277ef`
- name: `?RegValueExists@WaasMedic@@YAJPEAUHKEY__@@PEBG1KW4RegistryHiveType@1@@Z`
- size: `279`
- prototype: `int __high(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned int, enum WaasMedic::RegistryHiveType)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callers

- `0x18002a87c`

## callees

- `0x1800276d8`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x180027731`
- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x180027731`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002777d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002777d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800277b6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800277b6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800277d7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800277d7`

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
  if ( !dword_1800A55AC )
  {
    dword_1800A55B0 = 0;
    memset(&SystemInfo, 0, sizeof(SystemInfo));
    GetNativeSystemInfo(&SystemInfo);
    if ( SystemInfo.wProcessorArchitecture == 6 || SystemInfo.wProcessorArchitecture == 9 )
      dword_1800A55B0 = 1;
    dword_1800A55AC = 1;
  }
  if ( dword_1800A55B0 )
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
0x1800276d8  mov     [rsp-18h+arg_8], rbx
0x1800276dd  mov     [rsp-18h+Type], r9d
0x1800276e2  mov     [rsp-18h+hKey], rcx
0x1800276e7  push    rbp
0x1800276e8  push    rsi
0x1800276e9  push    rdi
0x1800276ea  mov     rbp, rsp
0x1800276ed  sub     rsp, 60h
0x1800276f1  cmp     cs:dword_1800A55AC, 0
0x1800276f8  mov     rdi, r8
0x1800276fb  mov     rsi, rdx
0x1800276fe  mov     [rbp+hKey], 0
0x180027706  mov     [rbp+Type], 0
0x18002770d  mov     ebx, 1
0x180027712  jnz     short loc_180027755
0x180027714  xorps   xmm0, xmm0
0x180027717  mov     cs:dword_1800A55B0, 0
0x180027721  lea     rcx, [rbp+SystemInfo]; lpSystemInfo
0x180027725  movups  xmmword ptr [rbp+SystemInfo], xmm0
0x180027729  movups  xmmword ptr [rbp+SystemInfo.lpMaximumApplicationAddress], xmm0
0x18002772d  movups  xmmword ptr [rbp+SystemInfo.dwNumberOfProcessors], xmm0
0x180027731  call    cs:__imp_GetNativeSystemInfo
0x180027737  lea     eax, [rbx+5]
0x18002773a  cmp     ax, word ptr [rbp+SystemInfo]
0x18002773e  jz      short loc_180027749
0x180027740  lea     eax, [rbx+8]
0x180027743  cmp     ax, word ptr [rbp+SystemInfo]
0x180027747  jnz     short loc_18002774F
0x180027749  mov     cs:dword_1800A55B0, ebx
0x18002774f  mov     cs:dword_1800A55AC, ebx
0x180027755  cmp     cs:dword_1800A55B0, 0
0x18002775c  mov     eax, 101h
0x180027761  cmovnz  ebx, eax
0x180027764  lea     rax, [rbp+hKey]
0x180027768  mov     r9d, ebx; samDesired
0x18002776b  xor     r8d, r8d; ulOptions
0x18002776e  mov     [rsp+60h+phkResult], rax; phkResult
0x180027773  mov     rdx, rsi; lpSubKey
0x180027776  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002777d  call    cs:__imp_RegOpenKeyExW
0x180027783  mov     ebx, eax
0x180027785  test    eax, eax
0x180027787  jz      short loc_180027796
0x180027789  jle     short loc_1800277CE
0x18002778b  movzx   ebx, ax
0x18002778e  or      ebx, 80070000h
0x180027794  jmp     short loc_1800277CE
0x180027796  mov     rcx, [rbp+hKey]; hKey
0x18002779a  lea     r9, [rbp+Type]; lpType
0x18002779e  mov     [rsp+60h+lpcbData], 0; lpcbData
0x1800277a7  xor     r8d, r8d; lpReserved
0x1800277aa  mov     rdx, rdi; lpValueName
0x1800277ad  mov     [rsp+60h+phkResult], 0; lpData
0x1800277b6  call    cs:__imp_RegQueryValueExW
0x1800277bc  mov     ebx, eax
0x1800277be  test    eax, eax
0x1800277c0  jnz     short loc_180027789
0x1800277c2  cmp     [rbp+Type], 4
0x1800277c6  mov     eax, 8007000Dh
0x1800277cb  cmovnz  ebx, eax
0x1800277ce  mov     rcx, [rbp+hKey]; hKey
0x1800277d2  test    rcx, rcx
0x1800277d5  jz      short loc_1800277DD
0x1800277d7  call    cs:__imp_RegCloseKey
0x1800277dd  mov     eax, ebx
0x1800277df  mov     rbx, [rsp+60h+arg_8]
0x1800277e7  add     rsp, 60h
0x1800277eb  pop     rdi
0x1800277ec  pop     rsi
0x1800277ed  pop     rbp
0x1800277ee  retn
```
