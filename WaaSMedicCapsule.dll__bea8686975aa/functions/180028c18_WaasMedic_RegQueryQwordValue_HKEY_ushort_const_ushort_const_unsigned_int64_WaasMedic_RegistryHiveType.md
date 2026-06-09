# WaasMedic::RegQueryQwordValue(HKEY__ *,ushort const *,ushort const *,unsigned __int64 *,WaasMedic::RegistryHiveType)

- ea: `0x180028c18`
- end: `0x180028d1b`
- name: `?RegQueryQwordValue@WaasMedic@@YAJPEAUHKEY__@@PEBG1PEA_KW4RegistryHiveType@1@@Z`
- size: `259`
- prototype: `int __high(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned __int64 *, enum WaasMedic::RegistryHiveType)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x180025d18`

## callees

- `0x180028c18`
- `0x180028d24`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x180028c7d`
- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x180028c7d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180028ccf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180028ccf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028d0a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028d0a`

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
    v8 = dword_180098D58 == 0;
    v9 = 1;
    *(_QWORD *)a4 = 0;
    if ( v8 )
    {
      dword_180098D54 = 0;
      memset(&SystemInfo, 0, sizeof(SystemInfo));
      GetNativeSystemInfo(&SystemInfo);
      if ( SystemInfo.wProcessorArchitecture == 6 || SystemInfo.wProcessorArchitecture == 9 )
        dword_180098D54 = 1;
      dword_180098D58 = 1;
    }
    if ( dword_180098D54 )
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
0x180028c18  mov     rax, rsp
0x180028c1b  mov     [rax+8], rcx
0x180028c1f  push    rbx
0x180028c20  push    rbp
0x180028c21  push    rsi
0x180028c22  push    rdi
0x180028c23  sub     rsp, 68h
0x180028c27  mov     qword ptr [rax+8], 0
0x180028c2f  mov     rdi, r9
0x180028c32  mov     rsi, r8
0x180028c35  mov     rbp, rdx
0x180028c38  test    r9, r9
0x180028c3b  jnz     short loc_180028C47
0x180028c3d  mov     ebx, 80004003h
0x180028c42  jmp     loc_180028D10
0x180028c47  cmp     cs:dword_180098D58, 0
0x180028c4e  mov     ebx, 1
0x180028c53  mov     qword ptr [r9], 0
0x180028c5a  jnz     short loc_180028CA3
0x180028c5c  xorps   xmm0, xmm0
0x180028c5f  mov     cs:dword_180098D54, 0
0x180028c69  lea     rcx, [rsp+88h+SystemInfo]; lpSystemInfo
0x180028c6e  movups  xmmword ptr [rsp+88h+SystemInfo], xmm0
0x180028c73  movups  xmmword ptr [rsp+88h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x180028c78  movups  xmmword ptr [rsp+88h+SystemInfo.dwNumberOfProcessors], xmm0
0x180028c7d  call    cs:__imp_GetNativeSystemInfo
0x180028c83  lea     eax, [rbx+5]
0x180028c86  cmp     ax, word ptr [rsp+88h+SystemInfo]
0x180028c8b  jz      short loc_180028C97
0x180028c8d  lea     eax, [rbx+8]
0x180028c90  cmp     ax, word ptr [rsp+88h+SystemInfo]
0x180028c95  jnz     short loc_180028C9D
0x180028c97  mov     cs:dword_180098D54, ebx
0x180028c9d  mov     cs:dword_180098D58, ebx
0x180028ca3  cmp     cs:dword_180098D54, 0
0x180028caa  mov     eax, 101h
0x180028caf  cmovnz  ebx, eax
0x180028cb2  lea     rax, [rsp+88h+hKey]
0x180028cba  mov     r9d, ebx; samDesired
0x180028cbd  xor     r8d, r8d; ulOptions
0x180028cc0  mov     [rsp+88h+phkResult], rax; phkResult
0x180028cc5  mov     rdx, rbp; lpSubKey
0x180028cc8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180028ccf  call    cs:__imp_RegOpenKeyExW
0x180028cd5  mov     ebx, eax
0x180028cd7  test    eax, eax
0x180028cd9  jz      short loc_180028CE8
0x180028cdb  jle     short loc_180028CFD
0x180028cdd  movzx   ebx, ax
0x180028ce0  or      ebx, 80070000h
0x180028ce6  jmp     short loc_180028CFD
0x180028ce8  mov     rcx, [rsp+88h+hKey]; this
0x180028cf0  mov     r8, rdi; unsigned __int16 *
0x180028cf3  mov     rdx, rsi; HKEY
0x180028cf6  call    ?RegQueryQwordValue@WaasMedic@@YAJPEAUHKEY__@@PEBGPEA_K@Z; WaasMedic::RegQueryQwordValue(HKEY__ *,ushort const *,unsigned __int64 *)
0x180028cfb  mov     ebx, eax
0x180028cfd  mov     rcx, [rsp+88h+hKey]; hKey
0x180028d05  test    rcx, rcx
0x180028d08  jz      short loc_180028D10
0x180028d0a  call    cs:__imp_RegCloseKey
0x180028d10  mov     eax, ebx
0x180028d12  add     rsp, 68h
0x180028d16  pop     rdi
0x180028d17  pop     rsi
0x180028d18  pop     rbp
0x180028d19  pop     rbx
0x180028d1a  retn
```
