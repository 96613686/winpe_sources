# WaasMedic::CTimeSyncPlugin::IsTimeSyncDisabledByUser(void)

- ea: `0x18004ec2c`
- end: `0x18004eda5`
- name: `?IsTimeSyncDisabledByUser@CTimeSyncPlugin@WaasMedic@@CA_NXZ`
- size: `377`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callers

- `0x18004e660`

## callees

- `0x1800017ac`
- `0x180003bb0`
- `0x180016c9c`
- `0x180028b78`
- `0x18004ec2c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x18004ec70`
- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x18004ec70`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004ecd8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004ecd8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004ed0b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004ed0b`

## string_xrefs

- `0x18004ecca`: `SYSTEM\CurrentControlSet\Services\W32Time\TimeProviders\NtpClient`

## pseudocode

```c
char WaasMedic::CTimeSyncPlugin::IsTimeSyncDisabledByUser(void)
{
  REGSAM v0; // r9d
  unsigned int *v1; // r9
  int v2; // ebx
  const struct _tlgProvider_t *v4; // rax
  unsigned __int16 v5[4]; // [rsp+30h] [rbp-50h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-48h] BYREF
  struct _SYSTEM_INFO SystemInfo; // [rsp+40h] [rbp-40h] BYREF

  if ( !dword_180098D58 )
  {
    dword_180098D54 = 0;
    memset(&SystemInfo, 0, sizeof(SystemInfo));
    GetNativeSystemInfo(&SystemInfo);
    if ( SystemInfo.wProcessorArchitecture == 6 || SystemInfo.wProcessorArchitecture == 9 )
      dword_180098D54 = 1;
    dword_180098D58 = 1;
  }
  v0 = 1;
  if ( dword_180098D54 )
    v0 = 257;
  hKey = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SYSTEM\\CurrentControlSet\\Services\\W32Time\\TimeProviders\\NtpClient",
          0,
          v0,
          &hKey) )
  {
    v2 = 0;
    *(_DWORD *)v5 = 0;
    if ( hKey && WaasMedic::RegQueryDwordValue((WaasMedic *)hKey, (HKEY)&stru_1800819D8, v5, v1) >= 0 )
      v2 = *(_DWORD *)v5;
    RegCloseKey(hKey);
    if ( v2 == 1 )
      return 0;
  }
  v4 = WaasMedic::TelemetryProvider::Provider();
  if ( *(_DWORD *)v4 > 5u
    && (*((_QWORD *)v4 + 2) & 0x400000000000LL) != 0
    && (*((_QWORD *)v4 + 3) & 0x400000000000LL) == *((_QWORD *)v4 + 3) )
  {
    hKey = (HKEY)0x2000000;
    *(_QWORD *)&SystemInfo.dwNumberOfProcessors = &hKey;
    *(_QWORD *)&SystemInfo.dwAllocationGranularity = 8;
    tlgWriteTransfer_EventWriteTransfer(v4, &word_18008A1E6, 0, 0, 3, &SystemInfo);
  }
  return 1;
}

```

## disassembly

```asm
0x18004ec2c  mov     [rsp-8+arg_0], rbx
0x18004ec31  push    rbp
0x18004ec32  mov     rbp, rsp
0x18004ec35  sub     rsp, 80h
0x18004ec3c  mov     rax, cs:__security_cookie
0x18004ec43  xor     rax, rsp
0x18004ec46  mov     [rbp+var_10], rax
0x18004ec4a  cmp     cs:dword_180098D58, 0
0x18004ec51  jnz     short loc_18004ECA0
0x18004ec53  xorps   xmm0, xmm0
0x18004ec56  mov     cs:dword_180098D54, 0
0x18004ec60  lea     rcx, [rbp+SystemInfo]; lpSystemInfo
0x18004ec64  movups  xmmword ptr [rbp+SystemInfo], xmm0
0x18004ec68  movups  xmmword ptr [rbp+SystemInfo.lpMaximumApplicationAddress], xmm0
0x18004ec6c  movups  xmmword ptr [rbp+SystemInfo.dwNumberOfProcessors], xmm0
0x18004ec70  call    cs:__imp_GetNativeSystemInfo
0x18004ec76  mov     eax, 6
0x18004ec7b  cmp     ax, word ptr [rbp+SystemInfo]
0x18004ec7f  jz      short loc_18004EC8C
0x18004ec81  mov     eax, 9
0x18004ec86  cmp     ax, word ptr [rbp+SystemInfo]
0x18004ec8a  jnz     short loc_18004EC96
0x18004ec8c  mov     cs:dword_180098D54, 1
0x18004ec96  mov     cs:dword_180098D58, 1
0x18004eca0  cmp     cs:dword_180098D54, 0
0x18004eca7  mov     eax, 101h
0x18004ecac  mov     r9d, 1
0x18004ecb2  cmovnz  r9d, eax; samDesired
0x18004ecb6  lea     rax, [rbp+hKey]
0x18004ecba  mov     [rbp+hKey], 0
0x18004ecc2  xor     r8d, r8d; ulOptions
0x18004ecc5  mov     [rsp+80h+phkResult], rax; phkResult
0x18004ecca  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services\\W3"...
0x18004ecd1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004ecd8  call    cs:__imp_RegOpenKeyExW
0x18004ecde  test    eax, eax
0x18004ece0  jnz     short loc_18004ED1A
0x18004ece2  mov     rcx, [rbp+hKey]; this
0x18004ece6  xor     ebx, ebx
0x18004ece8  mov     dword ptr [rbp+var_50], ebx
0x18004eceb  test    rcx, rcx
0x18004ecee  jz      short loc_18004ED07
0x18004ecf0  lea     r8, [rbp+var_50]; unsigned __int16 *
0x18004ecf4  lea     rdx, stru_1800819D8; HKEY
0x18004ecfb  call    ?RegQueryDwordValue@WaasMedic@@YAJPEAUHKEY__@@PEBGPEAK@Z; WaasMedic::RegQueryDwordValue(HKEY__ *,ushort const *,ulong *)
0x18004ed00  test    eax, eax
0x18004ed02  js      short loc_18004ED07
0x18004ed04  mov     ebx, dword ptr [rbp+var_50]
0x18004ed07  mov     rcx, [rbp+hKey]; hKey
0x18004ed0b  call    cs:__imp_RegCloseKey
0x18004ed11  cmp     ebx, 1
0x18004ed14  jnz     short loc_18004ED1A
0x18004ed16  xor     al, al
0x18004ed18  jmp     short loc_18004ED88
0x18004ed1a  call    ?Provider@TelemetryProvider@WaasMedic@@SAPEBU_tlgProvider_t@@XZ; WaasMedic::TelemetryProvider::Provider(void)
0x18004ed1f  mov     ecx, [rax]
0x18004ed21  cmp     ecx, 5
0x18004ed24  jbe     short loc_18004ED86
0x18004ed26  mov     rdx, [rax+18h]
0x18004ed2a  mov     r8, 400000000000h
0x18004ed34  mov     rcx, [rax+10h]
0x18004ed38  test    r8, rcx
0x18004ed3b  jz      short loc_18004ED86
0x18004ed3d  mov     rcx, rdx
0x18004ed40  and     rcx, r8
0x18004ed43  cmp     rcx, rdx
0x18004ed46  jnz     short loc_18004ED86
0x18004ed48  lea     rcx, [rbp+hKey]
0x18004ed4c  mov     [rbp+hKey], 2000000h
0x18004ed54  mov     qword ptr [rbp+SystemInfo.dwNumberOfProcessors], rcx
0x18004ed58  lea     rdx, word_18008A1E6
0x18004ed5f  lea     rcx, [rbp+SystemInfo]
0x18004ed63  mov     qword ptr [rbp+SystemInfo.dwAllocationGranularity], 8
0x18004ed6b  mov     [rsp+80h+var_58], rcx
0x18004ed70  xor     r9d, r9d
0x18004ed73  mov     rcx, rax
0x18004ed76  mov     dword ptr [rsp+80h+phkResult], 3
0x18004ed7e  xor     r8d, r8d
0x18004ed81  call    _tlgWriteTransfer_EventWriteTransfer
0x18004ed86  mov     al, 1
0x18004ed88  mov     rcx, [rbp+var_10]
0x18004ed8c  xor     rcx, rsp; StackCookie
0x18004ed8f  call    __security_check_cookie
0x18004ed94  mov     rbx, [rsp+80h+arg_0]
0x18004ed9c  add     rsp, 80h
0x18004eda3  pop     rbp
0x18004eda4  retn
```
