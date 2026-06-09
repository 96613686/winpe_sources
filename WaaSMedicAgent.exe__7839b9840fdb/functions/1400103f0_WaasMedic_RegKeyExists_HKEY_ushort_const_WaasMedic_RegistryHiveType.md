# WaasMedic::RegKeyExists(HKEY__ *,ushort const *,WaasMedic::RegistryHiveType)

- ea: `0x1400103f0`
- end: `0x1400104b8`
- name: `?RegKeyExists@WaasMedic@@YAJPEAUHKEY__@@PEBGW4RegistryHiveType@1@@Z`
- size: `200`
- prototype: `__int64 __fastcall(__int64, const WCHAR *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callers

- `0x14000ffa4`

## callees

- `0x1400103f0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400104a5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400104a5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140010485`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140010485`
- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x140010436`
- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x140010436`

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
  if ( !dword_1400207FC )
  {
    dword_1400207F8 = 0;
    memset(&v7, 0, sizeof(v7));
    GetNativeSystemInfo(&v7);
    if ( v7.wProcessorArchitecture == 6 || v7.wProcessorArchitecture == 9 )
      dword_1400207F8 = 1;
    dword_1400207FC = 1;
  }
  if ( dword_1400207F8 )
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
0x1400103f0  mov     rax, rsp
0x1400103f3  mov     [rax+10h], rbx
0x1400103f7  mov     [rax+8], rcx
0x1400103fb  push    rdi
0x1400103fc  sub     rsp, 60h
0x140010400  cmp     cs:dword_1400207FC, 0
0x140010407  mov     rdi, rdx
0x14001040a  mov     qword ptr [rax+8], 0
0x140010412  mov     ebx, 1
0x140010417  jnz     short loc_14001045C
0x140010419  xorps   xmm0, xmm0
0x14001041c  mov     cs:dword_1400207F8, 0
0x140010426  lea     rcx, [rax-38h]; lpSystemInfo
0x14001042a  movups  xmmword ptr [rax-38h], xmm0
0x14001042e  movups  xmmword ptr [rax-28h], xmm0
0x140010432  movups  xmmword ptr [rax-18h], xmm0
0x140010436  call    cs:__imp_GetNativeSystemInfo
0x14001043c  lea     eax, [rbx+5]
0x14001043f  cmp     ax, word ptr [rsp+68h+var_38]
0x140010444  jz      short loc_140010450
0x140010446  lea     eax, [rbx+8]
0x140010449  cmp     ax, word ptr [rsp+68h+var_38]
0x14001044e  jnz     short loc_140010456
0x140010450  mov     cs:dword_1400207F8, ebx
0x140010456  mov     cs:dword_1400207FC, ebx
0x14001045c  cmp     cs:dword_1400207F8, 0
0x140010463  mov     eax, 101h
0x140010468  cmovnz  ebx, eax
0x14001046b  lea     rax, [rsp+68h+hKey]
0x140010470  mov     r9d, ebx; samDesired
0x140010473  xor     r8d, r8d; ulOptions
0x140010476  mov     [rsp+68h+phkResult], rax; phkResult
0x14001047b  mov     rdx, rdi; lpSubKey
0x14001047e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140010485  call    cs:__imp_RegOpenKeyExW
0x14001048b  mov     ebx, eax
0x14001048d  test    eax, eax
0x14001048f  jz      short loc_14001049E
0x140010491  jle     short loc_1400104AB
0x140010493  movzx   ebx, ax
0x140010496  or      ebx, 80070000h
0x14001049c  jmp     short loc_1400104AB
0x14001049e  mov     rcx, [rsp+68h+hKey]; hKey
0x1400104a3  xor     ebx, ebx
0x1400104a5  call    cs:__imp_RegCloseKey
0x1400104ab  mov     eax, ebx
0x1400104ad  mov     rbx, [rsp+68h+arg_8]
0x1400104b2  add     rsp, 60h
0x1400104b6  pop     rdi
0x1400104b7  retn
```
