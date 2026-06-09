# WaasMedic::RegQueryDwordValueWithDefault(HKEY__ *,ushort const *,ushort const *,ulong,WaasMedic::RegistryHiveType)

- ea: `0x140010554`
- end: `0x140010634`
- name: `?RegQueryDwordValueWithDefault@WaasMedic@@YAKPEAUHKEY__@@PEBG1KW4RegistryHiveType@1@@Z`
- size: `224`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, HKEY, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x14000a8f0`

## callees

- `0x1400104c0`
- `0x140010554`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001061c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001061c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400105f2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400105f2`
- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x14001059e`
- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x14001059e`

## pseudocode

```c
__int64 __fastcall WaasMedic::RegQueryDwordValueWithDefault(__int64 a1, const WCHAR *a2, HKEY a3, int a4)
{
  unsigned int v4; // ebx
  REGSAM v6; // edi
  HKEY v7; // rdx
  unsigned int *v8; // r9
  _SYSTEM_INFO SystemInfo; // [rsp+30h] [rbp-30h] BYREF
  HKEY hKey; // [rsp+90h] [rbp+30h] BYREF
  int v12; // [rsp+98h] [rbp+38h] BYREF

  v12 = a4;
  hKey = a3;
  v4 = 30;
  v6 = 1;
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
    v6 = 257;
  hKey = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, v6, &hKey) )
  {
    v12 = 30;
    if ( hKey && WaasMedic::RegQueryDwordValue((WaasMedic *)hKey, v7, (const unsigned __int16 *)&v12, v8) >= 0 )
      v4 = v12;
    RegCloseKey(hKey);
  }
  return v4;
}

```

## disassembly

```asm
0x140010554  mov     [rsp-18h+arg_0], rbx
0x140010559  mov     [rsp-18h+arg_18], r9d
0x14001055e  mov     [rsp-18h+hKey], r8
0x140010563  push    rbp
0x140010564  push    rsi
0x140010565  push    rdi
0x140010566  mov     rbp, rsp
0x140010569  sub     rsp, 60h
0x14001056d  cmp     cs:dword_1400207FC, 0
0x140010574  mov     ebx, 1Eh
0x140010579  mov     rsi, rdx
0x14001057c  lea     edi, [rbx-1Dh]
0x14001057f  jnz     short loc_1400105C2
0x140010581  xorps   xmm0, xmm0
0x140010584  mov     cs:dword_1400207F8, 0
0x14001058e  lea     rcx, [rbp+SystemInfo]; lpSystemInfo
0x140010592  movups  xmmword ptr [rbp+SystemInfo], xmm0
0x140010596  movups  xmmword ptr [rbp+SystemInfo.lpMaximumApplicationAddress], xmm0
0x14001059a  movups  xmmword ptr [rbp+SystemInfo.dwNumberOfProcessors], xmm0
0x14001059e  call    cs:__imp_GetNativeSystemInfo
0x1400105a4  lea     eax, [rbx-18h]
0x1400105a7  cmp     ax, word ptr [rbp+SystemInfo]
0x1400105ab  jz      short loc_1400105B6
0x1400105ad  lea     eax, [rbx-15h]
0x1400105b0  cmp     ax, word ptr [rbp+SystemInfo]
0x1400105b4  jnz     short loc_1400105BC
0x1400105b6  mov     cs:dword_1400207F8, edi
0x1400105bc  mov     cs:dword_1400207FC, edi
0x1400105c2  cmp     cs:dword_1400207F8, 0
0x1400105c9  mov     eax, 101h
0x1400105ce  cmovnz  edi, eax
0x1400105d1  lea     rax, [rbp+hKey]
0x1400105d5  mov     [rbp+hKey], 0
0x1400105dd  mov     r9d, edi; samDesired
0x1400105e0  mov     [rsp+60h+phkResult], rax; phkResult
0x1400105e5  xor     r8d, r8d; ulOptions
0x1400105e8  mov     rdx, rsi; lpSubKey
0x1400105eb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400105f2  call    cs:__imp_RegOpenKeyExW
0x1400105f8  test    eax, eax
0x1400105fa  jnz     short loc_140010622
0x1400105fc  mov     rcx, [rbp+hKey]; this
0x140010600  mov     [rbp+arg_18], ebx
0x140010603  test    rcx, rcx
0x140010606  jz      short loc_140010618
0x140010608  lea     r8, [rbp+arg_18]; unsigned __int16 *
0x14001060c  call    ?RegQueryDwordValue@WaasMedic@@YAJPEAUHKEY__@@PEBGPEAK@Z; WaasMedic::RegQueryDwordValue(HKEY__ *,ushort const *,ulong *)
0x140010611  test    eax, eax
0x140010613  js      short loc_140010618
0x140010615  mov     ebx, [rbp+arg_18]
0x140010618  mov     rcx, [rbp+hKey]; hKey
0x14001061c  call    cs:__imp_RegCloseKey
0x140010622  mov     eax, ebx
0x140010624  mov     rbx, [rsp+60h+arg_0]
0x14001062c  add     rsp, 60h
0x140010630  pop     rdi
0x140010631  pop     rsi
0x140010632  pop     rbp
0x140010633  retn
```
