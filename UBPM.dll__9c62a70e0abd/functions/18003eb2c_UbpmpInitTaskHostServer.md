# UbpmpInitTaskHostServer

- ea: `0x18003eb2c`
- end: `0x18003ec63`
- name: `UbpmpInitTaskHostServer`
- size: `311`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x18002c420`

## callees

- `0x18001afe4`
- `0x1800351ec`
- `0x18003eb2c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ec2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ec2a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003eba6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003eba6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003eb72`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003eb72`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003ebc3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003ebc3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003ebf9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003ebf9`

## string_xrefs

- `0x18003eb9a`: `TaskhostTimeout`

## pseudocode

```c
PVOID UbpmpInitTaskHostServer()
{
  PVOID result; // rax
  DWORD LastError; // eax
  int Data; // [rsp+40h] [rbp+10h] BYREF
  DWORD Type; // [rsp+48h] [rbp+18h] BYREF
  DWORD cbData; // [rsp+50h] [rbp+20h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+28h] BYREF

  hKey = 0;
  Type = 0;
  cbData = 4;
  Data = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control", 0, 0x20019u, &hKey) )
  {
    if ( !RegQueryValueExW(hKey, L"TaskhostTimeout", 0, &Type, (LPBYTE)&Data, &cbData) && Type != 4 )
      Data = 0;
    RegCloseKey(hKey);
  }
  if ( Data )
  {
    g_dwTaskhostResponseTimeoutMsec = Data & 0x7FFFFFFF;
    g_fBreakOnTaskhostTimeout = Data < 0;
  }
  g_hLowPowerEpochExited = CreateEventW(0, 0, 1, 0);
  if ( g_hLowPowerEpochExited )
    return (PVOID)UbpmpSetInitialHostServerJobObjectRequests();
  result = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    LastError = GetLastError();
    return (PVOID)WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    211,
                    WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids,
                    LastError);
  }
  return result;
}

```

## disassembly

```asm
0x18003eb2c  push    rbp
0x18003eb2e  mov     rbp, rsp
0x18003eb31  sub     rsp, 30h
0x18003eb35  lea     rax, [rbp+hKey]
0x18003eb39  mov     [rbp+hKey], 0
0x18003eb41  mov     r9d, 20019h; samDesired
0x18003eb47  mov     [rsp+30h+phkResult], rax; phkResult
0x18003eb4c  xor     r8d, r8d; ulOptions
0x18003eb4f  mov     [rbp+Type], 0
0x18003eb56  lea     rdx, SubKey; "System\\CurrentControlSet\\Control"
0x18003eb5d  mov     [rbp+cbData], 4
0x18003eb64  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003eb6b  mov     [rbp+Data], 0
0x18003eb72  call    cs:__imp_RegOpenKeyExW
0x18003eb79  nop     dword ptr [rax+rax+00h]
0x18003eb7e  test    eax, eax
0x18003eb80  jnz     short loc_18003EBCF
0x18003eb82  mov     rcx, [rbp+hKey]; hKey
0x18003eb86  lea     rax, [rbp+cbData]
0x18003eb8a  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18003eb8f  lea     r9, [rbp+Type]; lpType
0x18003eb93  lea     rax, [rbp+Data]
0x18003eb97  xor     r8d, r8d; lpReserved
0x18003eb9a  lea     rdx, aTaskhosttimeou; "TaskhostTimeout"
0x18003eba1  mov     [rsp+30h+phkResult], rax; lpData
0x18003eba6  call    cs:__imp_RegQueryValueExW
0x18003ebad  nop     dword ptr [rax+rax+00h]
0x18003ebb2  test    eax, eax
0x18003ebb4  jnz     short loc_18003EBBF
0x18003ebb6  cmp     [rbp+Type], 4
0x18003ebba  jz      short loc_18003EBBF
0x18003ebbc  mov     [rbp+Data], eax
0x18003ebbf  mov     rcx, [rbp+hKey]; hKey
0x18003ebc3  call    cs:__imp_RegCloseKey
0x18003ebca  nop     dword ptr [rax+rax+00h]
0x18003ebcf  mov     ecx, [rbp+Data]
0x18003ebd2  test    ecx, ecx
0x18003ebd4  jz      short loc_18003EBEE
0x18003ebd6  mov     eax, ecx
0x18003ebd8  shr     ecx, 1Fh
0x18003ebdb  btr     eax, 1Fh
0x18003ebdf  and     cl, 1
0x18003ebe2  mov     cs:?g_dwTaskhostResponseTimeoutMsec@@3KA, eax; ulong g_dwTaskhostResponseTimeoutMsec
0x18003ebe8  mov     cs:?g_fBreakOnTaskhostTimeout@@3EA, cl; uchar g_fBreakOnTaskhostTimeout
0x18003ebee  xor     r9d, r9d; lpName
0x18003ebf1  xor     edx, edx; bManualReset
0x18003ebf3  xor     ecx, ecx; lpEventAttributes
0x18003ebf5  lea     r8d, [r9+1]; bInitialState
0x18003ebf9  call    cs:__imp_CreateEventW
0x18003ec00  nop     dword ptr [rax+rax+00h]
0x18003ec05  mov     cs:?g_hLowPowerEpochExited@@3PEAXEA, rax; void * g_hLowPowerEpochExited
0x18003ec0c  test    rax, rax
0x18003ec0f  jnz     short loc_18003EC57
0x18003ec11  mov     rax, cs:WPP_GLOBAL_Control
0x18003ec18  lea     rcx, WPP_GLOBAL_Control
0x18003ec1f  cmp     rax, rcx
0x18003ec22  jz      short loc_18003EC5C
0x18003ec24  test    byte ptr [rax+1Ch], 1
0x18003ec28  jz      short loc_18003EC5C
0x18003ec2a  call    cs:__imp_GetLastError
0x18003ec31  nop     dword ptr [rax+rax+00h]
0x18003ec36  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ec3d  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x18003ec44  mov     edx, 0D3h
0x18003ec49  mov     r9d, eax
0x18003ec4c  mov     rcx, [rcx+10h]
0x18003ec50  call    WPP_SF_d
0x18003ec55  jmp     short loc_18003EC5C
0x18003ec57  call    UbpmpSetInitialHostServerJobObjectRequests
0x18003ec5c  add     rsp, 30h
0x18003ec60  pop     rbp
0x18003ec61  retn
```
