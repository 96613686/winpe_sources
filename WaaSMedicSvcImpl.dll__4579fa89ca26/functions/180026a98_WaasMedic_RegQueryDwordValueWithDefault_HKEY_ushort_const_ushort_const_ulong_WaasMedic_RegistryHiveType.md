# WaasMedic::RegQueryDwordValueWithDefault(HKEY__ *,ushort const *,ushort const *,ulong,WaasMedic::RegistryHiveType)

- ea: `0x180026a98`
- end: `0x180026b7f`
- name: `?RegQueryDwordValueWithDefault@WaasMedic@@YAKPEAUHKEY__@@PEBG1KW4RegistryHiveType@1@@Z`
- size: `231`
- prototype: `unsigned int __high(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned int, enum WaasMedic::RegistryHiveType)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x18001e83c`

## callees

- `0x1800269f8`
- `0x180026a98`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x180026ae2`
- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x180026ae2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180026b36`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180026b36`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026b67`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026b67`

## pseudocode

```c
__int64 __fastcall WaasMedic::RegQueryDwordValueWithDefault(__int64 a1, const WCHAR *a2, HKEY a3, int a4)
{
  unsigned int v4; // ebx
  REGSAM v6; // edi
  unsigned int *v7; // r9
  struct _SYSTEM_INFO SystemInfo; // [rsp+30h] [rbp-30h] BYREF
  HKEY hKey; // [rsp+90h] [rbp+30h] BYREF
  int v11; // [rsp+98h] [rbp+38h] BYREF

  v11 = a4;
  hKey = a3;
  v4 = 30;
  v6 = 1;
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
    v6 = 257;
  hKey = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, v6, &hKey) )
  {
    v11 = 30;
    if ( hKey
      && WaasMedic::RegQueryDwordValue((WaasMedic *)hKey, (HKEY)&stru_1800787F8, (const unsigned __int16 *)&v11, v7) >= 0 )
    {
      v4 = v11;
    }
    RegCloseKey(hKey);
  }
  return v4;
}

```

## disassembly

```asm
0x180026a98  mov     [rsp-18h+arg_0], rbx
0x180026a9d  mov     [rsp-18h+arg_18], r9d
0x180026aa2  mov     [rsp-18h+hKey], r8
0x180026aa7  push    rbp
0x180026aa8  push    rsi
0x180026aa9  push    rdi
0x180026aaa  mov     rbp, rsp
0x180026aad  sub     rsp, 60h
0x180026ab1  cmp     cs:dword_1800A55AC, 0
0x180026ab8  mov     ebx, 1Eh
0x180026abd  mov     rsi, rdx
0x180026ac0  lea     edi, [rbx-1Dh]
0x180026ac3  jnz     short loc_180026B06
0x180026ac5  xorps   xmm0, xmm0
0x180026ac8  mov     cs:dword_1800A55B0, 0
0x180026ad2  lea     rcx, [rbp+SystemInfo]; lpSystemInfo
0x180026ad6  movups  xmmword ptr [rbp+SystemInfo], xmm0
0x180026ada  movups  xmmword ptr [rbp+SystemInfo.lpMaximumApplicationAddress], xmm0
0x180026ade  movups  xmmword ptr [rbp+SystemInfo.dwNumberOfProcessors], xmm0
0x180026ae2  call    cs:__imp_GetNativeSystemInfo
0x180026ae8  lea     eax, [rbx-18h]
0x180026aeb  cmp     ax, word ptr [rbp+SystemInfo]
0x180026aef  jz      short loc_180026AFA
0x180026af1  lea     eax, [rbx-15h]
0x180026af4  cmp     ax, word ptr [rbp+SystemInfo]
0x180026af8  jnz     short loc_180026B00
0x180026afa  mov     cs:dword_1800A55B0, edi
0x180026b00  mov     cs:dword_1800A55AC, edi
0x180026b06  cmp     cs:dword_1800A55B0, 0
0x180026b0d  mov     eax, 101h
0x180026b12  cmovnz  edi, eax
0x180026b15  lea     rax, [rbp+hKey]
0x180026b19  mov     [rbp+hKey], 0
0x180026b21  mov     r9d, edi; samDesired
0x180026b24  mov     [rsp+60h+phkResult], rax; phkResult
0x180026b29  xor     r8d, r8d; ulOptions
0x180026b2c  mov     rdx, rsi; lpSubKey
0x180026b2f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180026b36  call    cs:__imp_RegOpenKeyExW
0x180026b3c  test    eax, eax
0x180026b3e  jnz     short loc_180026B6D
0x180026b40  mov     rcx, [rbp+hKey]; this
0x180026b44  mov     [rbp+arg_18], ebx
0x180026b47  test    rcx, rcx
0x180026b4a  jz      short loc_180026B63
0x180026b4c  lea     r8, [rbp+arg_18]; unsigned __int16 *
0x180026b50  lea     rdx, stru_1800787F8; HKEY
0x180026b57  call    ?RegQueryDwordValue@WaasMedic@@YAJPEAUHKEY__@@PEBGPEAK@Z; WaasMedic::RegQueryDwordValue(HKEY__ *,ushort const *,ulong *)
0x180026b5c  test    eax, eax
0x180026b5e  js      short loc_180026B63
0x180026b60  mov     ebx, [rbp+arg_18]
0x180026b63  mov     rcx, [rbp+hKey]; hKey
0x180026b67  call    cs:__imp_RegCloseKey
0x180026b6d  mov     eax, ebx
0x180026b6f  mov     rbx, [rsp+60h+arg_0]
0x180026b77  add     rsp, 60h
0x180026b7b  pop     rdi
0x180026b7c  pop     rsi
0x180026b7d  pop     rbp
0x180026b7e  retn
```
