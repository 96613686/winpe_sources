# WaasMedic::RegKeyExists(HKEY__ *,ushort const *,WaasMedic::RegistryHiveType)

- ea: `0x180028894`
- end: `0x18002895c`
- name: `?RegKeyExists@WaasMedic@@YAJPEAUHKEY__@@PEBGW4RegistryHiveType@1@@Z`
- size: `200`
- prototype: `int __high(HKEY, const unsigned __int16 *, enum WaasMedic::RegistryHiveType)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callers

- `0x18000c228`
- `0x18000d750`
- `0x180026424`

## callees

- `0x180028894`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x1800288da`
- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x1800288da`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180028929`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180028929`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028949`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028949`

## pseudocode

```c
__int64 __fastcall WaasMedic::RegKeyExists(__int64 a1, const WCHAR *a2)
{
  REGSAM v3; // ebx
  LSTATUS v4; // eax
  unsigned int v5; // ebx
  struct _SYSTEM_INFO v7; // [rsp+30h] [rbp-38h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+8h] BYREF

  hKey = 0;
  v3 = 1;
  if ( !dword_180098D58 )
  {
    dword_180098D54 = 0;
    memset(&v7, 0, sizeof(v7));
    GetNativeSystemInfo(&v7);
    if ( v7.wProcessorArchitecture == 6 || v7.wProcessorArchitecture == 9 )
      dword_180098D54 = 1;
    dword_180098D58 = 1;
  }
  if ( dword_180098D54 )
    v3 = 257;
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, v3, &hKey);
  v5 = v4;
  if ( v4 )
  {
    if ( v4 > 0 )
      return (unsigned __int16)v4 | 0x80070000;
  }
  else
  {
    v5 = 0;
    RegCloseKey(hKey);
  }
  return v5;
}

```

## disassembly

```asm
0x180028894  mov     rax, rsp
0x180028897  mov     [rax+10h], rbx
0x18002889b  mov     [rax+8], rcx
0x18002889f  push    rdi
0x1800288a0  sub     rsp, 60h
0x1800288a4  cmp     cs:dword_180098D58, 0
0x1800288ab  mov     rdi, rdx
0x1800288ae  mov     qword ptr [rax+8], 0
0x1800288b6  mov     ebx, 1
0x1800288bb  jnz     short loc_180028900
0x1800288bd  xorps   xmm0, xmm0
0x1800288c0  mov     cs:dword_180098D54, 0
0x1800288ca  lea     rcx, [rax-38h]; lpSystemInfo
0x1800288ce  movups  xmmword ptr [rax-38h], xmm0
0x1800288d2  movups  xmmword ptr [rax-28h], xmm0
0x1800288d6  movups  xmmword ptr [rax-18h], xmm0
0x1800288da  call    cs:__imp_GetNativeSystemInfo
0x1800288e0  lea     eax, [rbx+5]
0x1800288e3  cmp     ax, word ptr [rsp+68h+var_38]
0x1800288e8  jz      short loc_1800288F4
0x1800288ea  lea     eax, [rbx+8]
0x1800288ed  cmp     ax, word ptr [rsp+68h+var_38]
0x1800288f2  jnz     short loc_1800288FA
0x1800288f4  mov     cs:dword_180098D54, ebx
0x1800288fa  mov     cs:dword_180098D58, ebx
0x180028900  cmp     cs:dword_180098D54, 0
0x180028907  mov     eax, 101h
0x18002890c  cmovnz  ebx, eax
0x18002890f  lea     rax, [rsp+68h+hKey]
0x180028914  mov     r9d, ebx; samDesired
0x180028917  xor     r8d, r8d; ulOptions
0x18002891a  mov     [rsp+68h+phkResult], rax; phkResult
0x18002891f  mov     rdx, rdi; lpSubKey
0x180028922  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180028929  call    cs:__imp_RegOpenKeyExW
0x18002892f  mov     ebx, eax
0x180028931  test    eax, eax
0x180028933  jz      short loc_180028942
0x180028935  jle     short loc_18002894F
0x180028937  movzx   ebx, ax
0x18002893a  or      ebx, 80070000h
0x180028940  jmp     short loc_18002894F
0x180028942  mov     rcx, [rsp+68h+hKey]; hKey
0x180028947  xor     ebx, ebx
0x180028949  call    cs:__imp_RegCloseKey
0x18002894f  mov     eax, ebx
0x180028951  mov     rbx, [rsp+68h+arg_8]
0x180028956  add     rsp, 60h
0x18002895a  pop     rdi
0x18002895b  retn
```
