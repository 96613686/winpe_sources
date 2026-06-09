# WaasMedic::RegKeyExists(HKEY__ *,ushort const *,WaasMedic::RegistryHiveType)

- ea: `0x180026714`
- end: `0x1800267dc`
- name: `?RegKeyExists@WaasMedic@@YAJPEAUHKEY__@@PEBGW4RegistryHiveType@1@@Z`
- size: `200`
- prototype: `int __high(HKEY, const unsigned __int16 *, enum WaasMedic::RegistryHiveType)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callers

- `0x18002a87c`

## callees

- `0x180026714`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x18002675a`
- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x18002675a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800267a9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800267a9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800267c9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800267c9`

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
  if ( !dword_1800A55AC )
  {
    dword_1800A55B0 = 0;
    memset(&v7, 0, sizeof(v7));
    GetNativeSystemInfo(&v7);
    if ( v7.wProcessorArchitecture == 6 || v7.wProcessorArchitecture == 9 )
      dword_1800A55B0 = 1;
    dword_1800A55AC = 1;
  }
  if ( dword_1800A55B0 )
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
0x180026714  mov     rax, rsp
0x180026717  mov     [rax+10h], rbx
0x18002671b  mov     [rax+8], rcx
0x18002671f  push    rdi
0x180026720  sub     rsp, 60h
0x180026724  cmp     cs:dword_1800A55AC, 0
0x18002672b  mov     rdi, rdx
0x18002672e  mov     qword ptr [rax+8], 0
0x180026736  mov     ebx, 1
0x18002673b  jnz     short loc_180026780
0x18002673d  xorps   xmm0, xmm0
0x180026740  mov     cs:dword_1800A55B0, 0
0x18002674a  lea     rcx, [rax-38h]; lpSystemInfo
0x18002674e  movups  xmmword ptr [rax-38h], xmm0
0x180026752  movups  xmmword ptr [rax-28h], xmm0
0x180026756  movups  xmmword ptr [rax-18h], xmm0
0x18002675a  call    cs:__imp_GetNativeSystemInfo
0x180026760  lea     eax, [rbx+5]
0x180026763  cmp     ax, word ptr [rsp+68h+var_38]
0x180026768  jz      short loc_180026774
0x18002676a  lea     eax, [rbx+8]
0x18002676d  cmp     ax, word ptr [rsp+68h+var_38]
0x180026772  jnz     short loc_18002677A
0x180026774  mov     cs:dword_1800A55B0, ebx
0x18002677a  mov     cs:dword_1800A55AC, ebx
0x180026780  cmp     cs:dword_1800A55B0, 0
0x180026787  mov     eax, 101h
0x18002678c  cmovnz  ebx, eax
0x18002678f  lea     rax, [rsp+68h+hKey]
0x180026794  mov     r9d, ebx; samDesired
0x180026797  xor     r8d, r8d; ulOptions
0x18002679a  mov     [rsp+68h+phkResult], rax; phkResult
0x18002679f  mov     rdx, rdi; lpSubKey
0x1800267a2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800267a9  call    cs:__imp_RegOpenKeyExW
0x1800267af  mov     ebx, eax
0x1800267b1  test    eax, eax
0x1800267b3  jz      short loc_1800267C2
0x1800267b5  jle     short loc_1800267CF
0x1800267b7  movzx   ebx, ax
0x1800267ba  or      ebx, 80070000h
0x1800267c0  jmp     short loc_1800267CF
0x1800267c2  mov     rcx, [rsp+68h+hKey]; hKey
0x1800267c7  xor     ebx, ebx
0x1800267c9  call    cs:__imp_RegCloseKey
0x1800267cf  mov     eax, ebx
0x1800267d1  mov     rbx, [rsp+68h+arg_8]
0x1800267d6  add     rsp, 60h
0x1800267da  pop     rdi
0x1800267db  retn
```
