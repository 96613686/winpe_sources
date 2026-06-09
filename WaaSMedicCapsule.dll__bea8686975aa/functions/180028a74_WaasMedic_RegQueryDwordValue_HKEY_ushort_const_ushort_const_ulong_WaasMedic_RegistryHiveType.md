# WaasMedic::RegQueryDwordValue(HKEY__ *,ushort const *,ushort const *,ulong *,WaasMedic::RegistryHiveType)

- ea: `0x180028a74`
- end: `0x180028b6f`
- name: `?RegQueryDwordValue@WaasMedic@@YAJPEAUHKEY__@@PEBG1PEAKW4RegistryHiveType@1@@Z`
- size: `251`
- prototype: `int __high(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned int *, enum WaasMedic::RegistryHiveType)`
- caller_count: `14`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x18001c8ec`
- `0x1800232b0`
- `0x1800233d0`
- `0x180023b50`
- `0x180023cd0`
- `0x180024080`
- `0x1800275dc`
- `0x1800387e0`
- `0x18004fa50`
- `0x180050120`
- `0x180051c80`
- `0x180056a90`
- `0x18005718c`
- `0x1800572c4`

## callees

- `0x180028a74`
- `0x180028b78`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x180028ad9`
- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x180028ad9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180028b2b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180028b2b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028b5e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028b5e`

## pseudocode

```c
LSTATUS __fastcall WaasMedic::RegQueryDwordValue(__int64 a1, const WCHAR *a2, HKEY a3, const unsigned __int16 *a4)
{
  LSTATUS result; // eax
  bool v8; // zf
  REGSAM v9; // ebx
  unsigned int *v10; // r9
  int DwordValue; // ebx
  struct _SYSTEM_INFO SystemInfo; // [rsp+30h] [rbp-58h] BYREF
  HKEY hKey; // [rsp+90h] [rbp+8h] BYREF

  hKey = 0;
  if ( !a4 )
    return -2147467261;
  v8 = dword_180098D58 == 0;
  v9 = 1;
  *(_DWORD *)a4 = 0;
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
  result = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, v9, &hKey);
  if ( result )
  {
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  else
  {
    DwordValue = WaasMedic::RegQueryDwordValue((WaasMedic *)hKey, a3, a4, v10);
    RegCloseKey(hKey);
    return DwordValue;
  }
  return result;
}

```

## disassembly

```asm
0x180028a74  mov     rax, rsp
0x180028a77  mov     [rax+8], rcx
0x180028a7b  push    rbx
0x180028a7c  push    rbp
0x180028a7d  push    rsi
0x180028a7e  push    rdi
0x180028a7f  sub     rsp, 68h
0x180028a83  mov     qword ptr [rax+8], 0
0x180028a8b  mov     rdi, r9
0x180028a8e  mov     rsi, r8
0x180028a91  mov     rbp, rdx
0x180028a94  test    r9, r9
0x180028a97  jnz     short loc_180028AA3
0x180028a99  mov     eax, 80004003h
0x180028a9e  jmp     loc_180028B66
0x180028aa3  cmp     cs:dword_180098D58, 0
0x180028aaa  mov     ebx, 1
0x180028aaf  mov     dword ptr [r9], 0
0x180028ab6  jnz     short loc_180028AFF
0x180028ab8  xorps   xmm0, xmm0
0x180028abb  mov     cs:dword_180098D54, 0
0x180028ac5  lea     rcx, [rsp+88h+SystemInfo]; lpSystemInfo
0x180028aca  movups  xmmword ptr [rsp+88h+SystemInfo], xmm0
0x180028acf  movups  xmmword ptr [rsp+88h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x180028ad4  movups  xmmword ptr [rsp+88h+SystemInfo.dwNumberOfProcessors], xmm0
0x180028ad9  call    cs:__imp_GetNativeSystemInfo
0x180028adf  lea     eax, [rbx+5]
0x180028ae2  cmp     ax, word ptr [rsp+88h+SystemInfo]
0x180028ae7  jz      short loc_180028AF3
0x180028ae9  lea     eax, [rbx+8]
0x180028aec  cmp     ax, word ptr [rsp+88h+SystemInfo]
0x180028af1  jnz     short loc_180028AF9
0x180028af3  mov     cs:dword_180098D54, ebx
0x180028af9  mov     cs:dword_180098D58, ebx
0x180028aff  cmp     cs:dword_180098D54, 0
0x180028b06  mov     eax, 101h
0x180028b0b  cmovnz  ebx, eax
0x180028b0e  lea     rax, [rsp+88h+hKey]
0x180028b16  mov     r9d, ebx; samDesired
0x180028b19  xor     r8d, r8d; ulOptions
0x180028b1c  mov     [rsp+88h+phkResult], rax; phkResult
0x180028b21  mov     rdx, rbp; lpSubKey
0x180028b24  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180028b2b  call    cs:__imp_RegOpenKeyExW
0x180028b31  test    eax, eax
0x180028b33  jz      short loc_180028B41
0x180028b35  jle     short loc_180028B66
0x180028b37  movzx   eax, ax
0x180028b3a  or      eax, 80070000h
0x180028b3f  jmp     short loc_180028B66
0x180028b41  mov     rcx, [rsp+88h+hKey]; this
0x180028b49  mov     r8, rdi; unsigned __int16 *
0x180028b4c  mov     rdx, rsi; HKEY
0x180028b4f  call    ?RegQueryDwordValue@WaasMedic@@YAJPEAUHKEY__@@PEBGPEAK@Z; WaasMedic::RegQueryDwordValue(HKEY__ *,ushort const *,ulong *)
0x180028b54  mov     rcx, [rsp+88h+hKey]; hKey
0x180028b5c  mov     ebx, eax
0x180028b5e  call    cs:__imp_RegCloseKey
0x180028b64  mov     eax, ebx
0x180028b66  add     rsp, 68h
0x180028b6a  pop     rdi
0x180028b6b  pop     rsi
0x180028b6c  pop     rbp
0x180028b6d  pop     rbx
0x180028b6e  retn
```
