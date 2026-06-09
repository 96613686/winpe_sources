# WaasMedic::RegQueryQwordValue(HKEY__ *,ushort const *,ushort const *,unsigned __int64 *,WaasMedic::RegistryHiveType)

- ea: `0x180026b88`
- end: `0x180026c8b`
- name: `?RegQueryQwordValue@WaasMedic@@YAJPEAUHKEY__@@PEBG1PEA_KW4RegistryHiveType@1@@Z`
- size: `259`
- prototype: `int __high(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned __int64 *, enum WaasMedic::RegistryHiveType)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x180064d1c`
- `0x180065b50`

## callees

- `0x180026b88`
- `0x180026c94`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x180026bed`
- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x180026bed`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180026c3f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180026c3f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026c7a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026c7a`

## pseudocode

```c
__int64 __fastcall WaasMedic::RegQueryQwordValue(__int64 a1, const WCHAR *a2, HKEY a3, const unsigned __int16 *a4)
{
  unsigned int QwordValue; // ebx
  bool v8; // zf
  REGSAM v9; // ebx
  LSTATUS v10; // eax
  unsigned __int64 *v11; // r9
  struct _SYSTEM_INFO SystemInfo; // [rsp+30h] [rbp-58h] BYREF
  HKEY hKey; // [rsp+90h] [rbp+8h] BYREF

  hKey = 0;
  if ( a4 )
  {
    v8 = dword_1800A55AC == 0;
    v9 = 1;
    *(_QWORD *)a4 = 0;
    if ( v8 )
    {
      dword_1800A55B0 = 0;
      memset(&SystemInfo, 0, sizeof(SystemInfo));
      GetNativeSystemInfo(&SystemInfo);
      if ( SystemInfo.wProcessorArchitecture == 6 || SystemInfo.wProcessorArchitecture == 9 )
        dword_1800A55B0 = 1;
      dword_1800A55AC = 1;
    }
    if ( dword_1800A55B0 )
      v9 = 257;
    v10 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, v9, &hKey);
    QwordValue = v10;
    if ( v10 )
    {
      if ( v10 > 0 )
        QwordValue = (unsigned __int16)v10 | 0x80070000;
    }
    else
    {
      QwordValue = WaasMedic::RegQueryQwordValue((WaasMedic *)hKey, a3, a4, v11);
    }
    if ( hKey )
      RegCloseKey(hKey);
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return QwordValue;
}

```

## disassembly

```asm
0x180026b88  mov     rax, rsp
0x180026b8b  mov     [rax+8], rcx
0x180026b8f  push    rbx
0x180026b90  push    rbp
0x180026b91  push    rsi
0x180026b92  push    rdi
0x180026b93  sub     rsp, 68h
0x180026b97  mov     qword ptr [rax+8], 0
0x180026b9f  mov     rdi, r9
0x180026ba2  mov     rsi, r8
0x180026ba5  mov     rbp, rdx
0x180026ba8  test    r9, r9
0x180026bab  jnz     short loc_180026BB7
0x180026bad  mov     ebx, 80004003h
0x180026bb2  jmp     loc_180026C80
0x180026bb7  cmp     cs:dword_1800A55AC, 0
0x180026bbe  mov     ebx, 1
0x180026bc3  mov     qword ptr [r9], 0
0x180026bca  jnz     short loc_180026C13
0x180026bcc  xorps   xmm0, xmm0
0x180026bcf  mov     cs:dword_1800A55B0, 0
0x180026bd9  lea     rcx, [rsp+88h+SystemInfo]; lpSystemInfo
0x180026bde  movups  xmmword ptr [rsp+88h+SystemInfo], xmm0
0x180026be3  movups  xmmword ptr [rsp+88h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x180026be8  movups  xmmword ptr [rsp+88h+SystemInfo.dwNumberOfProcessors], xmm0
0x180026bed  call    cs:__imp_GetNativeSystemInfo
0x180026bf3  lea     eax, [rbx+5]
0x180026bf6  cmp     ax, word ptr [rsp+88h+SystemInfo]
0x180026bfb  jz      short loc_180026C07
0x180026bfd  lea     eax, [rbx+8]
0x180026c00  cmp     ax, word ptr [rsp+88h+SystemInfo]
0x180026c05  jnz     short loc_180026C0D
0x180026c07  mov     cs:dword_1800A55B0, ebx
0x180026c0d  mov     cs:dword_1800A55AC, ebx
0x180026c13  cmp     cs:dword_1800A55B0, 0
0x180026c1a  mov     eax, 101h
0x180026c1f  cmovnz  ebx, eax
0x180026c22  lea     rax, [rsp+88h+hKey]
0x180026c2a  mov     r9d, ebx; samDesired
0x180026c2d  xor     r8d, r8d; ulOptions
0x180026c30  mov     [rsp+88h+phkResult], rax; phkResult
0x180026c35  mov     rdx, rbp; lpSubKey
0x180026c38  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180026c3f  call    cs:__imp_RegOpenKeyExW
0x180026c45  mov     ebx, eax
0x180026c47  test    eax, eax
0x180026c49  jz      short loc_180026C58
0x180026c4b  jle     short loc_180026C6D
0x180026c4d  movzx   ebx, ax
0x180026c50  or      ebx, 80070000h
0x180026c56  jmp     short loc_180026C6D
0x180026c58  mov     rcx, [rsp+88h+hKey]; this
0x180026c60  mov     r8, rdi; unsigned __int16 *
0x180026c63  mov     rdx, rsi; HKEY
0x180026c66  call    ?RegQueryQwordValue@WaasMedic@@YAJPEAUHKEY__@@PEBGPEA_K@Z; WaasMedic::RegQueryQwordValue(HKEY__ *,ushort const *,unsigned __int64 *)
0x180026c6b  mov     ebx, eax
0x180026c6d  mov     rcx, [rsp+88h+hKey]; hKey
0x180026c75  test    rcx, rcx
0x180026c78  jz      short loc_180026C80
0x180026c7a  call    cs:__imp_RegCloseKey
0x180026c80  mov     eax, ebx
0x180026c82  add     rsp, 68h
0x180026c86  pop     rdi
0x180026c87  pop     rsi
0x180026c88  pop     rbp
0x180026c89  pop     rbx
0x180026c8a  retn
```
