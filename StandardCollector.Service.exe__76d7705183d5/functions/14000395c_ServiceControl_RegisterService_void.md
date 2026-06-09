# ServiceControl::RegisterService(void)

- ea: `0x14000395c`
- end: `0x140003b4d`
- name: `?RegisterService@ServiceControl@@CAJXZ`
- size: `497`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x14000356c`

## callees

- `0x14000395c`
- `0x140003b50`
- `0x140003c40`
- `0x1400043a0`
- `0x1400108a8`
- `0x1400137e0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400039a4`
- `KERNEL32!GetLastError` at `0x140003ae2`
- `KERNEL32!GetLastError` at `0x1400039a4`
- `KERNEL32!GetLastError` at `0x140003ae2`
- `ADVAPI32!ChangeServiceConfig2W` at `0x140003a9b`
- `ADVAPI32!ChangeServiceConfig2W` at `0x140003aba`
- `ADVAPI32!ChangeServiceConfig2W` at `0x140003ad8`
- `ADVAPI32!ChangeServiceConfig2W` at `0x140003a9b`
- `ADVAPI32!ChangeServiceConfig2W` at `0x140003aba`
- `ADVAPI32!ChangeServiceConfig2W` at `0x140003ad8`
- `ADVAPI32!QueryServiceConfig2W` at `0x140003a7f`
- `ADVAPI32!QueryServiceConfig2W` at `0x140003a7f`
- `ADVAPI32!CreateServiceW` at `0x140003a45`
- `ADVAPI32!CreateServiceW` at `0x140003a45`
- `ADVAPI32!OpenSCManagerW` at `0x140003992`
- `ADVAPI32!OpenSCManagerW` at `0x140003992`
- `ADVAPI32!CloseServiceHandle` at `0x140003b07`
- `ADVAPI32!CloseServiceHandle` at `0x140003b20`
- `ADVAPI32!CloseServiceHandle` at `0x140003b07`
- `ADVAPI32!CloseServiceHandle` at `0x140003b20`

## string_xrefs

- `0x140003aa5`: `SeImpersonatePrivilege`
- `0x140003ac4`: `Visual Studio Data Collection Service. When running, this service collects real-time ETW events and processes them.`
- `0x140003a34`: `Visual Studio Standard Collector Service`
- `0x140003a3b`: `VsStandardCollectorService170`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 ServiceControl::RegisterService(void)
{
  SC_HANDLE v0; // rdi
  signed int v1; // eax
  signed int ModulePath; // esi
  SC_HANDLE ServiceW; // rbx
  signed int LastError; // eax
  const wchar_t *Info; // [rsp+80h] [rbp+1Fh] BYREF
  const wchar_t *v7; // [rsp+88h] [rbp+27h] BYREF
  BYTE Buffer[4]; // [rsp+90h] [rbp+2Fh] BYREF
  DWORD pcbBytesNeeded; // [rsp+94h] [rbp+33h] BYREF
  LPCWSTR lpBinaryPathName[2]; // [rsp+98h] [rbp+37h] BYREF
  __int64 v11; // [rsp+A8h] [rbp+47h]

  ServiceControl::UnregisterService();
  v0 = OpenSCManagerW(0, 0, 2u);
  if ( v0 )
  {
    *(_OWORD *)lpBinaryPathName = 0;
    v11 = 0;
    ModulePath = DiagHubCommon::ModulePath::GetModulePath(0);
    if ( ModulePath >= 0 )
    {
      ServiceW = CreateServiceW(
                   v0,
                   L"VsStandardCollectorService170",
                   L"Visual Studio Standard Collector Service",
                   0xF01FFu,
                   0x10u,
                   3u,
                   0,
                   lpBinaryPathName[0],
                   0,
                   0,
                   0,
                   0,
                   0);
      if ( ServiceW
        && (*(_DWORD *)Buffer = 0, pcbBytesNeeded = 0, QueryServiceConfig2W(ServiceW, 5u, Buffer, 4u, &pcbBytesNeeded))
        && (*(_DWORD *)Buffer = 1, ChangeServiceConfig2W(ServiceW, 5u, Buffer))
        && (Info = L"SeImpersonatePrivilege", ChangeServiceConfig2W(ServiceW, 6u, &Info))
        && (v7 = L"Visual Studio Data Collection Service. When running, this service collects real-time ETW events and processes them.",
            ChangeServiceConfig2W(ServiceW, 1u, &v7)) )
      {
        ServiceControl::OnRegister();
        ModulePath = 0;
      }
      else
      {
        LastError = GetLastError();
        ModulePath = (unsigned __int16)LastError | 0x80070000;
        if ( LastError <= 0 )
          ModulePath = LastError;
        if ( !ServiceW )
          goto LABEL_17;
      }
      CloseServiceHandle(ServiceW);
    }
LABEL_17:
    std::vector<unsigned short>::~vector<unsigned short>(lpBinaryPathName);
    goto LABEL_18;
  }
  v1 = GetLastError();
  ModulePath = (unsigned __int16)v1 | 0x80070000;
  if ( v1 <= 0 )
    ModulePath = v1;
LABEL_18:
  if ( v0 )
    CloseServiceHandle(v0);
  return (unsigned int)ModulePath;
}

```

## disassembly

```asm
0x14000395c  mov     rax, rsp
0x14000395f  mov     [rax+8], rbx
0x140003963  mov     [rax+10h], rsi
0x140003967  mov     [rax+18h], rdi
0x14000396b  push    rbp
0x14000396c  lea     rbp, [rax-5Fh]
0x140003970  sub     rsp, 0B0h
0x140003977  mov     rax, cs:__security_cookie
0x14000397e  xor     rax, rsp
0x140003981  mov     [rbp+57h+var_8], rax
0x140003985  call    ?UnregisterService@ServiceControl@@CAJXZ; ServiceControl::UnregisterService(void)
0x14000398a  xor     edx, edx; lpDatabaseName
0x14000398c  xor     ecx, ecx; lpMachineName
0x14000398e  lea     r8d, [rdx+2]; dwDesiredAccess
0x140003992  call    cs:__imp_OpenSCManagerW
0x140003998  mov     rdi, rax
0x14000399b  mov     [rbp+57h+var_40], rax
0x14000399f  test    rax, rax
0x1400039a2  jnz     short loc_1400039BD
0x1400039a4  call    cs:__imp_GetLastError
0x1400039aa  movzx   esi, ax
0x1400039ad  or      esi, 80070000h
0x1400039b3  test    eax, eax
0x1400039b5  cmovle  esi, eax
0x1400039b8  jmp     loc_140003B18
0x1400039bd  xor     eax, eax
0x1400039bf  xorps   xmm1, xmm1
0x1400039c2  movdqu  xmmword ptr [rbp+57h+var_20], xmm1
0x1400039c7  mov     [rbp+57h+var_10], rax
0x1400039cb  lea     rdx, [rbp+57h+var_20]
0x1400039cf  xor     ecx, ecx; hModule
0x1400039d1  call    ?GetModulePath@ModulePath@DiagHubCommon@@SAJPEAUHINSTANCE__@@AEAV?$vector@GV?$allocator@G@std@@@std@@@Z; DiagHubCommon::ModulePath::GetModulePath(HINSTANCE__ *,std::vector<ushort> &)
0x1400039d6  mov     esi, eax
0x1400039d8  test    eax, eax
0x1400039da  js      loc_140003B0E
0x1400039e0  mov     rax, [rbp+57h+var_20]
0x1400039e4  mov     [rsp+0B0h+lpPassword], 0; lpPassword
0x1400039ed  mov     [rsp+0B0h+lpServiceStartName], 0; lpServiceStartName
0x1400039f6  mov     [rsp+0B0h+lpDependencies], 0; lpDependencies
0x1400039ff  mov     [rsp+0B0h+lpdwTagId], 0; lpdwTagId
0x140003a08  mov     [rsp+0B0h+lpLoadOrderGroup], 0; lpLoadOrderGroup
0x140003a11  mov     [rsp+0B0h+lpBinaryPathName], rax; lpBinaryPathName
0x140003a16  mov     [rsp+0B0h+dwErrorControl], 0; dwErrorControl
0x140003a1e  mov     [rsp+0B0h+dwStartType], 3; dwStartType
0x140003a26  mov     [rsp+0B0h+dwServiceType], 10h; dwServiceType
0x140003a2e  mov     r9d, 0F01FFh; dwDesiredAccess
0x140003a34  lea     r8, Data; "Visual Studio Standard Collector Servic"...
0x140003a3b  lea     rdx, ?WZ_SERVICENAME@@3QBGB; "VsStandardCollectorService170"
0x140003a42  mov     rcx, rdi; hSCManager
0x140003a45  call    cs:__imp_CreateServiceW
0x140003a4b  mov     rbx, rax
0x140003a4e  test    rax, rax
0x140003a51  jz      loc_140003AE2
0x140003a57  mov     dword ptr [rbp+57h+Buffer], 0
0x140003a5e  mov     [rbp+57h+pcbBytesNeeded], 0
0x140003a65  lea     rax, [rbp+57h+pcbBytesNeeded]
0x140003a69  mov     qword ptr [rsp+0B0h+dwServiceType], rax; pcbBytesNeeded
0x140003a6e  mov     r9d, 4; cbBufSize
0x140003a74  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x140003a78  lea     edx, [r9+1]; dwInfoLevel
0x140003a7c  mov     rcx, rbx; hService
0x140003a7f  call    cs:__imp_QueryServiceConfig2W
0x140003a85  test    eax, eax
0x140003a87  jz      short loc_140003AE2
0x140003a89  mov     esi, 1
0x140003a8e  mov     dword ptr [rbp+57h+Buffer], esi
0x140003a91  lea     r8, [rbp+57h+Buffer]; lpInfo
0x140003a95  lea     edx, [rsi+4]; dwInfoLevel
0x140003a98  mov     rcx, rbx; hService
0x140003a9b  call    cs:__imp_ChangeServiceConfig2W
0x140003aa1  test    eax, eax
0x140003aa3  jz      short loc_140003AE2
0x140003aa5  lea     rax, aSeimpersonatep; "SeImpersonatePrivilege"
0x140003aac  mov     [rbp+57h+Info], rax
0x140003ab0  lea     r8, [rbp+57h+Info]; lpInfo
0x140003ab4  lea     edx, [rsi+5]; dwInfoLevel
0x140003ab7  mov     rcx, rbx; hService
0x140003aba  call    cs:__imp_ChangeServiceConfig2W
0x140003ac0  test    eax, eax
0x140003ac2  jz      short loc_140003AE2
0x140003ac4  lea     rax, aVisualStudioDa; "Visual Studio Data Collection Service. "...
0x140003acb  mov     [rbp+57h+var_30], rax
0x140003acf  lea     r8, [rbp+57h+var_30]; lpInfo
0x140003ad3  mov     edx, esi; dwInfoLevel
0x140003ad5  mov     rcx, rbx; hService
0x140003ad8  call    cs:__imp_ChangeServiceConfig2W
0x140003ade  test    eax, eax
0x140003ae0  jnz     short loc_140003AFD
0x140003ae2  call    cs:__imp_GetLastError
0x140003ae8  movzx   esi, ax
0x140003aeb  or      esi, 80070000h
0x140003af1  test    eax, eax
0x140003af3  cmovle  esi, eax
0x140003af6  test    rbx, rbx
0x140003af9  jz      short loc_140003B0E
0x140003afb  jmp     short loc_140003B04
0x140003afd  call    ?OnRegister@ServiceControl@@CAXXZ; ServiceControl::OnRegister(void)
0x140003b02  xor     esi, esi
0x140003b04  mov     rcx, rbx; hSCObject
0x140003b07  call    cs:__imp_CloseServiceHandle
0x140003b0d  nop
0x140003b0e  lea     rcx, [rbp+57h+var_20]
0x140003b12  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x140003b17  nop
0x140003b18  test    rdi, rdi
0x140003b1b  jz      short loc_140003B26
0x140003b1d  mov     rcx, rdi; hSCObject
0x140003b20  call    cs:__imp_CloseServiceHandle
0x140003b26  mov     eax, esi
0x140003b28  mov     rcx, [rbp+57h+var_8]
0x140003b2c  xor     rcx, rsp; StackCookie
0x140003b2f  call    __security_check_cookie
0x140003b34  lea     r11, [rsp+0B0h+var_s0]
0x140003b3c  mov     rbx, [r11+10h]
0x140003b40  mov     rsi, [r11+18h]
0x140003b44  mov     rdi, [r11+20h]
0x140003b48  mov     rsp, r11
0x140003b4b  pop     rbp
0x140003b4c  retn
```
