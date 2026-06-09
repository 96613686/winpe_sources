# WaasMedic::RegQueryStringValue(HKEY__ *,ushort const *,ushort const *,ushort *,ulong,WaasMedic::RegistryHiveType)

- ea: `0x180028dc4`
- end: `0x180028ebf`
- name: `?RegQueryStringValue@WaasMedic@@YAJPEAUHKEY__@@PEBG1PEAGKW4RegistryHiveType@1@@Z`
- size: `251`
- prototype: `int __high(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *, unsigned int, enum WaasMedic::RegistryHiveType)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x18002845c`
- `0x180057324`

## callees

- `0x180028dc4`
- `0x180029a40`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x180028e0f`
- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x180028e0f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180028e61`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180028e61`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028eae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028eae`

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
  if ( !dword_180098D58 )
  {
    dword_180098D54 = 0;
    memset(&v11, 0, sizeof(v11));
    GetNativeSystemInfo(&v11);
    if ( v11.wProcessorArchitecture == 6 || v11.wProcessorArchitecture == 9 )
      dword_180098D54 = 1;
    dword_180098D58 = 1;
  }
  if ( dword_180098D54 )
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
0x180028dc4  mov     rax, rsp
0x180028dc7  mov     [rax+8], rcx
0x180028dcb  push    rbx
0x180028dcc  push    rbp
0x180028dcd  push    rsi
0x180028dce  push    rdi
0x180028dcf  sub     rsp, 78h
0x180028dd3  cmp     cs:dword_180098D58, 0
0x180028dda  mov     rdi, r9
0x180028ddd  mov     rsi, r8
0x180028de0  mov     qword ptr [rax+8], 0
0x180028de8  mov     rbp, rdx
0x180028deb  mov     ebx, 1
0x180028df0  jnz     short loc_180028E35
0x180028df2  xorps   xmm0, xmm0
0x180028df5  mov     cs:dword_180098D54, 0
0x180028dff  lea     rcx, [rax-58h]; lpSystemInfo
0x180028e03  movups  xmmword ptr [rax-58h], xmm0
0x180028e07  movups  xmmword ptr [rax-48h], xmm0
0x180028e0b  movups  xmmword ptr [rax-38h], xmm0
0x180028e0f  call    cs:__imp_GetNativeSystemInfo
0x180028e15  lea     eax, [rbx+5]
0x180028e18  cmp     ax, word ptr [rsp+98h+var_58]
0x180028e1d  jz      short loc_180028E29
0x180028e1f  lea     eax, [rbx+8]
0x180028e22  cmp     ax, word ptr [rsp+98h+var_58]
0x180028e27  jnz     short loc_180028E2F
0x180028e29  mov     cs:dword_180098D54, ebx
0x180028e2f  mov     cs:dword_180098D58, ebx
0x180028e35  cmp     cs:dword_180098D54, 0
0x180028e3c  mov     eax, 101h
0x180028e41  cmovnz  ebx, eax
0x180028e44  lea     rax, [rsp+98h+hKey]
0x180028e4c  mov     r9d, ebx; samDesired
0x180028e4f  xor     r8d, r8d; ulOptions
0x180028e52  mov     [rsp+98h+phkResult], rax; phkResult
0x180028e57  mov     rdx, rbp; lpSubKey
0x180028e5a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180028e61  call    cs:__imp_RegOpenKeyExW
0x180028e67  test    eax, eax
0x180028e69  jz      short loc_180028E77
0x180028e6b  jle     short loc_180028EB6
0x180028e6d  movzx   eax, ax
0x180028e70  or      eax, 80070000h
0x180028e75  jmp     short loc_180028EB6
0x180028e77  mov     rdx, [rsp+98h+hKey]
0x180028e7f  mov     r9, rdi
0x180028e82  mov     [rsp+98h+var_68], 0
0x180028e8b  mov     r8, rsi
0x180028e8e  mov     [rsp+98h+var_70], 0
0x180028e97  mov     dword ptr [rsp+98h+phkResult], 825h
0x180028e9f  call    WaasMedic__SafeRegQueryValueCchHelper
0x180028ea4  mov     rcx, [rsp+98h+hKey]; hKey
0x180028eac  mov     ebx, eax
0x180028eae  call    cs:__imp_RegCloseKey
0x180028eb4  mov     eax, ebx
0x180028eb6  add     rsp, 78h
0x180028eba  pop     rdi
0x180028ebb  pop     rsi
0x180028ebc  pop     rbp
0x180028ebd  pop     rbx
0x180028ebe  retn
```
