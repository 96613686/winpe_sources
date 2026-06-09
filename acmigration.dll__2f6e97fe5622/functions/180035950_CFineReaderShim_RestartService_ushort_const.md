# CFineReaderShim::RestartService(ushort const *)

- ea: `0x180035950`
- end: `0x180035b34`
- name: `?RestartService@CFineReaderShim@@AEAAKPEBG@Z`
- size: `484`
- prototype: `unsigned int(CFineReaderShim *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180035818`

## callees

- `0x180001cf0`
- `0x180035950`
- `0x1800543c0`

## import_xrefs

- `KERNEL32!Sleep` at `0x180035a93`
- `KERNEL32!Sleep` at `0x180035a93`
- `KERNEL32!GetLastError` at `0x1800359b1`
- `KERNEL32!GetLastError` at `0x1800359f8`
- `KERNEL32!GetLastError` at `0x180035ab2`
- `KERNEL32!GetLastError` at `0x1800359b1`
- `KERNEL32!GetLastError` at `0x1800359f8`
- `KERNEL32!GetLastError` at `0x180035ab2`
- `ADVAPI32!OpenSCManagerW` at `0x1800359a3`
- `ADVAPI32!OpenSCManagerW` at `0x1800359a3`
- `ADVAPI32!OpenServiceW` at `0x1800359ea`
- `ADVAPI32!OpenServiceW` at `0x1800359ea`
- `ADVAPI32!QueryServiceStatusEx` at `0x180035a5e`
- `ADVAPI32!QueryServiceStatusEx` at `0x180035a5e`
- `ADVAPI32!CloseServiceHandle` at `0x180035aff`
- `ADVAPI32!CloseServiceHandle` at `0x180035b08`
- `ADVAPI32!CloseServiceHandle` at `0x180035aff`
- `ADVAPI32!CloseServiceHandle` at `0x180035b08`
- `ADVAPI32!ControlService` at `0x180035a31`
- `ADVAPI32!ControlService` at `0x180035a31`
- `ADVAPI32!StartServiceW` at `0x180035aa8`
- `ADVAPI32!StartServiceW` at `0x180035aa8`

## string_xrefs

- `0x1800359b7`: `OpenSCManager failed (%d)\n`
- `0x1800359c4`: `CFineReaderShim::RestartService`
- `0x180035a0b`: `CFineReaderShim::RestartService`
- `0x180035ac5`: `CFineReaderShim::RestartService`
- `0x180035aed`: `CFineReaderShim::RestartService`
- `0x1800359fe`: `OpenService failed (%d)\n`
- `0x180035ab8`: `StartService failed (%d)\n`
- `0x180035ae0`: `Service start pending...\n`

## pseudocode

```c
__int64 __fastcall CFineReaderShim::RestartService(CFineReaderShim *this, const unsigned __int16 *a2)
{
  SC_HANDLE v3; // rax
  SC_HANDLE v4; // rsi
  DWORD LastError; // ebx
  SC_HANDLE v6; // rax
  SC_HANDLE v7; // rdi
  unsigned int i; // ebx
  DWORD v9; // edx
  DWORD pcbBytesNeeded; // [rsp+30h] [rbp-19h] BYREF
  BYTE Buffer[16]; // [rsp+38h] [rbp-11h] BYREF
  __int128 v13; // [rsp+48h] [rbp-1h]
  int v14; // [rsp+58h] [rbp+Fh]
  _SERVICE_STATUS ServiceStatus; // [rsp+60h] [rbp+17h] BYREF

  v14 = 0;
  pcbBytesNeeded = 0;
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  *(_OWORD *)Buffer = 0;
  v13 = 0;
  v3 = OpenSCManagerW(0, 0, 0xF003Fu);
  v4 = v3;
  if ( v3 )
  {
    v6 = OpenServiceW(v3, a2, 0xF01FFu);
    v7 = v6;
    if ( v6 )
    {
      ControlService(v6, 1u, &ServiceStatus);
      for ( i = 0; i < 2; ++i )
      {
        *(_DWORD *)&Buffer[4] = 4;
        QueryServiceStatusEx(v7, SC_STATUS_PROCESS_INFO, Buffer, 0x24u, &pcbBytesNeeded);
        if ( *(_DWORD *)&Buffer[4] == 1 )
          break;
        if ( *(_DWORD *)&Buffer[4] == 3 )
        {
          v9 = DWORD2(v13) / 0xA;
          if ( DWORD2(v13) / 0xA >= 0x3E8 )
          {
            if ( v9 > 0x2710 )
              v9 = 10000;
          }
          else
          {
            v9 = 1000;
          }
          Sleep(v9);
        }
      }
      if ( StartServiceW(v7, 0, 0) )
      {
        LastError = 0;
        AslLogCallPrintf(3, "CFineReaderShim::RestartService", 237, "Service start pending...\n");
      }
      else
      {
        LastError = GetLastError();
        AslLogCallPrintf(1, "CFineReaderShim::RestartService", 231, "StartService failed (%d)\n", LastError);
      }
      CloseServiceHandle(v7);
    }
    else
    {
      LastError = GetLastError();
      AslLogCallPrintf(1, "CFineReaderShim::RestartService", 185, "OpenService failed (%d)\n", LastError);
    }
    CloseServiceHandle(v4);
  }
  else
  {
    LastError = GetLastError();
    AslLogCallPrintf(1, "CFineReaderShim::RestartService", 173, "OpenSCManager failed (%d)\n", LastError);
  }
  return LastError;
}

```

## disassembly

```asm
0x180035950  mov     [rsp-8+arg_0], rbx
0x180035955  mov     [rsp-8+arg_10], rsi
0x18003595a  push    rbp
0x18003595b  push    rdi
0x18003595c  push    r15
0x18003595e  lea     rbp, [rsp-47h]
0x180035963  sub     rsp, 90h
0x18003596a  mov     rax, cs:__security_cookie
0x180035971  xor     rax, rsp
0x180035974  mov     [rbp+57h+var_20], rax
0x180035978  xorps   xmm0, xmm0
0x18003597b  xor     eax, eax
0x18003597d  xorps   xmm1, xmm1
0x180035980  mov     [rbp+57h+var_48], eax
0x180035983  mov     rbx, rdx
0x180035986  mov     [rbp+57h+var_70], eax
0x180035989  movups  xmmword ptr [rbp+57h+ServiceStatus.dwServiceType], xmm0
0x18003598d  xor     edx, edx; lpDatabaseName
0x18003598f  xor     ecx, ecx; lpMachineName
0x180035991  mov     r8d, 0F003Fh; dwDesiredAccess
0x180035997  movups  xmmword ptr [rbp+57h+ServiceStatus.dwWin32ExitCode], xmm0
0x18003599b  movups  xmmword ptr [rbp+57h+Buffer], xmm1
0x18003599f  movups  [rbp+57h+var_58], xmm1
0x1800359a3  call    cs:__imp_OpenSCManagerW
0x1800359a9  mov     rsi, rax
0x1800359ac  test    rax, rax
0x1800359af  jnz     short loc_1800359DE
0x1800359b1  call    cs:__imp_GetLastError
0x1800359b7  lea     r9, aOpenscmanagerF_0; "OpenSCManager failed (%d)\n"
0x1800359be  mov     r8d, 0ADh
0x1800359c4  lea     rdx, aCfinereadershi_1; "CFineReaderShim::RestartService"
0x1800359cb  mov     dword ptr [rsp+0A0h+pcbBytesNeeded], eax
0x1800359cf  lea     ecx, [rsi+1]
0x1800359d2  mov     ebx, eax
0x1800359d4  call    AslLogCallPrintf
0x1800359d9  jmp     loc_180035B0E
0x1800359de  mov     r8d, 0F01FFh; dwDesiredAccess
0x1800359e4  mov     rdx, rbx; lpServiceName
0x1800359e7  mov     rcx, rsi; hSCManager
0x1800359ea  call    cs:__imp_OpenServiceW
0x1800359f0  mov     rdi, rax
0x1800359f3  test    rax, rax
0x1800359f6  jnz     short loc_180035A25
0x1800359f8  call    cs:__imp_GetLastError
0x1800359fe  lea     r9, aOpenserviceFai_0; "OpenService failed (%d)\n"
0x180035a05  mov     r8d, 0B9h
0x180035a0b  lea     rdx, aCfinereadershi_1; "CFineReaderShim::RestartService"
0x180035a12  mov     dword ptr [rsp+0A0h+pcbBytesNeeded], eax
0x180035a16  lea     ecx, [rdi+1]
0x180035a19  mov     ebx, eax
0x180035a1b  call    AslLogCallPrintf
0x180035a20  jmp     loc_180035B05
0x180035a25  lea     r8, [rbp+57h+ServiceStatus]; lpServiceStatus
0x180035a29  mov     edx, 1; dwControl
0x180035a2e  mov     rcx, rdi; hService
0x180035a31  call    cs:__imp_ControlService
0x180035a37  xor     ebx, ebx
0x180035a39  mov     r15d, 2710h
0x180035a3f  lea     rax, [rbp+57h+var_70]
0x180035a43  mov     dword ptr [rbp+57h+Buffer+4], 4
0x180035a4a  mov     r9d, 24h ; '$'; cbBufSize
0x180035a50  mov     [rsp+0A0h+pcbBytesNeeded], rax; pcbBytesNeeded
0x180035a55  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x180035a59  xor     edx, edx; InfoLevel
0x180035a5b  mov     rcx, rdi; hService
0x180035a5e  call    cs:__imp_QueryServiceStatusEx
0x180035a64  cmp     dword ptr [rbp+57h+Buffer+4], 1
0x180035a68  jz      short loc_180035AA0
0x180035a6a  cmp     dword ptr [rbp+57h+Buffer+4], 3
0x180035a6e  jnz     short loc_180035A99
0x180035a70  mov     eax, 0CCCCCCCDh
0x180035a75  mul     dword ptr [rbp+57h+var_58+8]
0x180035a78  shr     edx, 3
0x180035a7b  cmp     edx, 3E8h
0x180035a81  jnb     short loc_180035A8A
0x180035a83  mov     edx, 3E8h
0x180035a88  jmp     short loc_180035A91
0x180035a8a  cmp     edx, r15d
0x180035a8d  cmova   edx, r15d
0x180035a91  mov     ecx, edx; dwMilliseconds
0x180035a93  call    cs:__imp_Sleep
0x180035a99  inc     ebx
0x180035a9b  cmp     ebx, 2
0x180035a9e  jb      short loc_180035A3F
0x180035aa0  xor     r8d, r8d; lpServiceArgVectors
0x180035aa3  xor     edx, edx; dwNumServiceArgs
0x180035aa5  mov     rcx, rdi; hService
0x180035aa8  call    cs:__imp_StartServiceW
0x180035aae  test    eax, eax
0x180035ab0  jnz     short loc_180035ADE
0x180035ab2  call    cs:__imp_GetLastError
0x180035ab8  lea     r9, aStartserviceFa; "StartService failed (%d)\n"
0x180035abf  mov     r8d, 0E7h
0x180035ac5  lea     rdx, aCfinereadershi_1; "CFineReaderShim::RestartService"
0x180035acc  mov     dword ptr [rsp+0A0h+pcbBytesNeeded], eax
0x180035ad0  mov     ecx, 1
0x180035ad5  mov     ebx, eax
0x180035ad7  call    AslLogCallPrintf
0x180035adc  jmp     short loc_180035AFC
0x180035ade  xor     ebx, ebx
0x180035ae0  lea     r9, aServiceStartPe; "Service start pending...\n"
0x180035ae7  mov     r8d, 0EDh
0x180035aed  lea     rdx, aCfinereadershi_1; "CFineReaderShim::RestartService"
0x180035af4  lea     ecx, [rbx+3]
0x180035af7  call    AslLogCallPrintf
0x180035afc  mov     rcx, rdi; hSCObject
0x180035aff  call    cs:__imp_CloseServiceHandle
0x180035b05  mov     rcx, rsi; hSCObject
0x180035b08  call    cs:__imp_CloseServiceHandle
0x180035b0e  mov     eax, ebx
0x180035b10  mov     rcx, [rbp+57h+var_20]
0x180035b14  xor     rcx, rsp; StackCookie
0x180035b17  call    __security_check_cookie
0x180035b1c  lea     r11, [rsp+0A0h+var_10]
0x180035b24  mov     rbx, [r11+20h]
0x180035b28  mov     rsi, [r11+30h]
0x180035b2c  mov     rsp, r11
0x180035b2f  pop     r15
0x180035b31  pop     rdi
0x180035b32  pop     rbp
0x180035b33  retn
```
