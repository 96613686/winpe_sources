# WaasMedic::RegQueryStringValue(HKEY__ *,ushort const *,ushort const *,ushort *,ulong,WaasMedic::RegistryHiveType)

- ea: `0x180026d34`
- end: `0x180026e2f`
- name: `?RegQueryStringValue@WaasMedic@@YAJPEAUHKEY__@@PEBG1PEAGKW4RegistryHiveType@1@@Z`
- size: `251`
- prototype: `int __high(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *, unsigned int, enum WaasMedic::RegistryHiveType)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x1800262dc`
- `0x18002d4c8`

## callees

- `0x180026d34`
- `0x18002799c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x180026d7f`
- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x180026d7f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180026dd1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180026dd1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026e1e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026e1e`

## pseudocode

```c
LSTATUS __fastcall WaasMedic::RegQueryStringValue(__int64 a1, const WCHAR *a2, __int64 a3, __int64 a4)
{
  REGSAM v7; // ebx
  LSTATUS result; // eax
  __int64 v9; // rcx
  int ValueCchHelper; // ebx
  struct _SYSTEM_INFO v11; // [rsp+40h] [rbp-58h] BYREF
  HKEY hKey; // [rsp+A0h] [rbp+8h] BYREF

  hKey = 0;
  v7 = 1;
  if ( !dword_1800A55AC )
  {
    dword_1800A55B0 = 0;
    memset(&v11, 0, sizeof(v11));
    GetNativeSystemInfo(&v11);
    if ( v11.wProcessorArchitecture == 6 || v11.wProcessorArchitecture == 9 )
      dword_1800A55B0 = 1;
    dword_1800A55AC = 1;
  }
  if ( dword_1800A55B0 )
    v7 = 257;
  result = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, v7, &hKey);
  if ( result )
  {
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  else
  {
    ValueCchHelper = WaasMedic::SafeRegQueryValueCchHelper(v9, hKey, a3, a4, 2085, 0, 0);
    RegCloseKey(hKey);
    return ValueCchHelper;
  }
  return result;
}

```

## disassembly

```asm
0x180026d34  mov     rax, rsp
0x180026d37  mov     [rax+8], rcx
0x180026d3b  push    rbx
0x180026d3c  push    rbp
0x180026d3d  push    rsi
0x180026d3e  push    rdi
0x180026d3f  sub     rsp, 78h
0x180026d43  cmp     cs:dword_1800A55AC, 0
0x180026d4a  mov     rdi, r9
0x180026d4d  mov     rsi, r8
0x180026d50  mov     qword ptr [rax+8], 0
0x180026d58  mov     rbp, rdx
0x180026d5b  mov     ebx, 1
0x180026d60  jnz     short loc_180026DA5
0x180026d62  xorps   xmm0, xmm0
0x180026d65  mov     cs:dword_1800A55B0, 0
0x180026d6f  lea     rcx, [rax-58h]; lpSystemInfo
0x180026d73  movups  xmmword ptr [rax-58h], xmm0
0x180026d77  movups  xmmword ptr [rax-48h], xmm0
0x180026d7b  movups  xmmword ptr [rax-38h], xmm0
0x180026d7f  call    cs:__imp_GetNativeSystemInfo
0x180026d85  lea     eax, [rbx+5]
0x180026d88  cmp     ax, word ptr [rsp+98h+var_58]
0x180026d8d  jz      short loc_180026D99
0x180026d8f  lea     eax, [rbx+8]
0x180026d92  cmp     ax, word ptr [rsp+98h+var_58]
0x180026d97  jnz     short loc_180026D9F
0x180026d99  mov     cs:dword_1800A55B0, ebx
0x180026d9f  mov     cs:dword_1800A55AC, ebx
0x180026da5  cmp     cs:dword_1800A55B0, 0
0x180026dac  mov     eax, 101h
0x180026db1  cmovnz  ebx, eax
0x180026db4  lea     rax, [rsp+98h+hKey]
0x180026dbc  mov     r9d, ebx; samDesired
0x180026dbf  xor     r8d, r8d; ulOptions
0x180026dc2  mov     [rsp+98h+phkResult], rax; phkResult
0x180026dc7  mov     rdx, rbp; lpSubKey
0x180026dca  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180026dd1  call    cs:__imp_RegOpenKeyExW
0x180026dd7  test    eax, eax
0x180026dd9  jz      short loc_180026DE7
0x180026ddb  jle     short loc_180026E26
0x180026ddd  movzx   eax, ax
0x180026de0  or      eax, 80070000h
0x180026de5  jmp     short loc_180026E26
0x180026de7  mov     rdx, [rsp+98h+hKey]
0x180026def  mov     r9, rdi
0x180026df2  mov     [rsp+98h+var_68], 0
0x180026dfb  mov     r8, rsi
0x180026dfe  mov     [rsp+98h+var_70], 0
0x180026e07  mov     dword ptr [rsp+98h+phkResult], 825h
0x180026e0f  call    WaasMedic__SafeRegQueryValueCchHelper
0x180026e14  mov     rcx, [rsp+98h+hKey]; hKey
0x180026e1c  mov     ebx, eax
0x180026e1e  call    cs:__imp_RegCloseKey
0x180026e24  mov     eax, ebx
0x180026e26  add     rsp, 78h
0x180026e2a  pop     rdi
0x180026e2b  pop     rsi
0x180026e2c  pop     rbp
0x180026e2d  pop     rbx
0x180026e2e  retn
```
