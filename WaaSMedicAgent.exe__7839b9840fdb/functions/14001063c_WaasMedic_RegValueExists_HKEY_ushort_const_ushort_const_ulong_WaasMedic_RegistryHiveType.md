# WaasMedic::RegValueExists(HKEY__ *,ushort const *,ushort const *,ulong,WaasMedic::RegistryHiveType)

- ea: `0x14001063c`
- end: `0x140010756`
- name: `?RegValueExists@WaasMedic@@YAJPEAUHKEY__@@PEBG1KW4RegistryHiveType@1@@Z`
- size: `282`
- prototype: `__int64 __fastcall(__int64, const WCHAR *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callers

- `0x14000ffa4`

## callees

- `0x14001063c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001073e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001073e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14001071d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14001071d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400106e0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400106e0`
- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x140010694`
- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x140010694`

## pseudocode

```c
__int64 __fastcall WaasMedic::RegValueExists(__int64 a1, const WCHAR *a2)
{
  REGSAM v3; // ebx
  LSTATUS v4; // eax
  unsigned int v5; // ebx
  bool v6; // cc
  struct _SYSTEM_INFO SystemInfo; // [rsp+30h] [rbp-30h] BYREF
  HKEY hKey; // [rsp+80h] [rbp+20h] BYREF
  DWORD Type; // [rsp+88h] [rbp+28h] BYREF

  hKey = 0;
  v3 = 1;
  Type = 0;
  if ( !dword_1400207FC )
  {
    dword_1400207F8 = 0;
    memset(&SystemInfo, 0, sizeof(SystemInfo));
    GetNativeSystemInfo(&SystemInfo);
    if ( SystemInfo.wProcessorArchitecture == 6 || SystemInfo.wProcessorArchitecture == 9 )
      dword_1400207F8 = 1;
    dword_1400207FC = 1;
  }
  if ( dword_1400207F8 )
    v3 = 257;
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, v3, &hKey);
  v5 = v4;
  v6 = v4 <= 0;
  if ( v4 || (v4 = RegQueryValueExW(hKey, L"WorkerDelay", 0, &Type, 0, 0), v5 = v4, v6 = v4 <= 0, v4) )
  {
    if ( !v6 )
      v5 = (unsigned __int16)v4 | 0x80070000;
  }
  else if ( Type != 4 )
  {
    v5 = -2147024883;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v5;
}

```

## disassembly

```asm
0x14001063c  mov     rax, rsp
0x14001063f  mov     [rax+8], rbx
0x140010643  mov     [rax+10h], rdi
0x140010647  mov     [rax+20h], r9d
0x14001064b  mov     [rax+18h], r8
0x14001064f  push    rbp
0x140010650  mov     rbp, rsp
0x140010653  sub     rsp, 60h
0x140010657  cmp     cs:dword_1400207FC, 0
0x14001065e  mov     rdi, rdx
0x140010661  mov     [rbp+hKey], 0
0x140010669  mov     ebx, 1
0x14001066e  mov     [rbp+Type], 0
0x140010675  jnz     short loc_1400106B8
0x140010677  xorps   xmm0, xmm0
0x14001067a  mov     cs:dword_1400207F8, 0
0x140010684  lea     rcx, [rbp+SystemInfo]; lpSystemInfo
0x140010688  movups  xmmword ptr [rbp+SystemInfo], xmm0
0x14001068c  movups  xmmword ptr [rbp+SystemInfo.lpMaximumApplicationAddress], xmm0
0x140010690  movups  xmmword ptr [rbp+SystemInfo.dwNumberOfProcessors], xmm0
0x140010694  call    cs:__imp_GetNativeSystemInfo
0x14001069a  lea     eax, [rbx+5]
0x14001069d  cmp     ax, word ptr [rbp+SystemInfo]
0x1400106a1  jz      short loc_1400106AC
0x1400106a3  lea     eax, [rbx+8]
0x1400106a6  cmp     ax, word ptr [rbp+SystemInfo]
0x1400106aa  jnz     short loc_1400106B2
0x1400106ac  mov     cs:dword_1400207F8, ebx
0x1400106b2  mov     cs:dword_1400207FC, ebx
0x1400106b8  cmp     cs:dword_1400207F8, 0
0x1400106bf  mov     eax, 101h
0x1400106c4  cmovnz  ebx, eax
0x1400106c7  lea     rax, [rbp+hKey]
0x1400106cb  mov     r9d, ebx; samDesired
0x1400106ce  xor     r8d, r8d; ulOptions
0x1400106d1  mov     [rsp+60h+phkResult], rax; phkResult
0x1400106d6  mov     rdx, rdi; lpSubKey
0x1400106d9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400106e0  call    cs:__imp_RegOpenKeyExW
0x1400106e6  mov     ebx, eax
0x1400106e8  test    eax, eax
0x1400106ea  jz      short loc_1400106F9
0x1400106ec  jle     short loc_140010735
0x1400106ee  movzx   ebx, ax
0x1400106f1  or      ebx, 80070000h
0x1400106f7  jmp     short loc_140010735
0x1400106f9  mov     rcx, [rbp+hKey]; hKey
0x1400106fd  lea     r9, [rbp+Type]; lpType
0x140010701  mov     [rsp+60h+lpcbData], 0; lpcbData
0x14001070a  lea     rdx, ValueName; "WorkerDelay"
0x140010711  xor     r8d, r8d; lpReserved
0x140010714  mov     [rsp+60h+phkResult], 0; lpData
0x14001071d  call    cs:__imp_RegQueryValueExW
0x140010723  mov     ebx, eax
0x140010725  test    eax, eax
0x140010727  jnz     short loc_1400106EC
0x140010729  cmp     [rbp+Type], 4
0x14001072d  mov     eax, 8007000Dh
0x140010732  cmovnz  ebx, eax
0x140010735  mov     rcx, [rbp+hKey]; hKey
0x140010739  test    rcx, rcx
0x14001073c  jz      short loc_140010744
0x14001073e  call    cs:__imp_RegCloseKey
0x140010744  mov     rdi, [rsp+60h+arg_8]
0x140010749  mov     eax, ebx
0x14001074b  mov     rbx, [rsp+60h+arg_0]
0x140010750  add     rsp, 60h
0x140010754  pop     rbp
0x140010755  retn
```
