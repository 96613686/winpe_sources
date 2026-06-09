# GetWindowsInstallerStatus(bool &)

- ea: `0x140016ff0`
- end: `0x14001716e`
- name: `?GetWindowsInstallerStatus@@YAJAEA_N@Z`
- size: `382`
- prototype: `__int64 __fastcall(bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update`

## callers

- `0x14000e6cc`

## callees

- `0x14000740c`
- `0x1400074d4`
- `0x140016ff0`
- `0x14001a8d0`

## import_xrefs

- `ADVAPI32!CloseServiceHandle` at `0x1400170e7`
- `ADVAPI32!CloseServiceHandle` at `0x140017115`
- `ADVAPI32!CloseServiceHandle` at `0x1400170e7`
- `ADVAPI32!CloseServiceHandle` at `0x140017115`
- `ADVAPI32!OpenSCManagerW` at `0x140017047`
- `ADVAPI32!OpenSCManagerW` at `0x140017047`
- `ADVAPI32!QueryServiceStatusEx` at `0x14001708f`
- `ADVAPI32!QueryServiceStatusEx` at `0x14001708f`
- `ADVAPI32!OpenServiceW` at `0x140017067`
- `ADVAPI32!OpenServiceW` at `0x140017067`
- `KERNEL32!GetLastError` at `0x1400170c1`
- `KERNEL32!GetLastError` at `0x1400170ef`
- `KERNEL32!GetLastError` at `0x14001711d`
- `KERNEL32!GetLastError` at `0x1400170c1`
- `KERNEL32!GetLastError` at `0x1400170ef`
- `KERNEL32!GetLastError` at `0x14001711d`

## string_xrefs

- `0x140017036`: `msiserver`
- `0x1400170b3`: `Windows Installer service is busy.  dwCurrentState = %1!d!. dwControlsAccepted = %2!d!.`
- `0x1400170d8`: `QueryServiceStatusEx failed with error 0x%1!x!.`
- `0x140017106`: `OpenService failed with error 0x%1!x!.`
- `0x140017134`: `OpenSCManager failed with error 0x%1!x!.`
- `0x140017146`: `GetWindowsInstallerStatus failed with error = 0x%1!x!.`

## pseudocode

```c
__int64 __fastcall GetWindowsInstallerStatus(bool *a1)
{
  SC_HANDLE v2; // rax
  SC_HANDLE v3; // rsi
  SC_HANDLE v4; // rdi
  unsigned int v5; // ebx
  signed int LastError; // eax
  signed int v7; // eax
  signed int v8; // eax
  DWORD pcbBytesNeeded; // [rsp+30h] [rbp-78h] BYREF
  BYTE Buffer[16]; // [rsp+38h] [rbp-70h] BYREF
  __int128 v12; // [rsp+48h] [rbp-60h]
  int v13; // [rsp+58h] [rbp-50h]
  WCHAR ServiceName[8]; // [rsp+60h] [rbp-48h] BYREF
  int v15; // [rsp+70h] [rbp-38h]

  v13 = 0;
  *(_OWORD *)Buffer = 0;
  pcbBytesNeeded = 0;
  v12 = 0;
  v15 = *(_DWORD *)L"r";
  *a1 = 1;
  *(_OWORD *)ServiceName = *(_OWORD *)L"msiserver";
  v2 = OpenSCManagerW(0, 0, 1u);
  v3 = v2;
  if ( v2 )
  {
    v4 = OpenServiceW(v2, ServiceName, 4u);
    if ( v4 )
    {
      if ( QueryServiceStatusEx(v4, SC_STATUS_PROCESS_INFO, Buffer, 0x24u, &pcbBytesNeeded) )
      {
        v5 = 0;
        if ( *(_DWORD *)&Buffer[4] == 4 && (Buffer[8] & 4) == 0 )
        {
          *a1 = 0;
          LogInfo(L"Windows Installer service is busy.  dwCurrentState = %1!d!. dwControlsAccepted = %2!d!.", 4);
        }
      }
      else
      {
        LastError = GetLastError();
        v5 = LastError;
        if ( LastError > 0 )
          v5 = (unsigned __int16)LastError | 0x80070000;
        LogError(L"QueryServiceStatusEx failed with error 0x%1!x!.", v5);
      }
      CloseServiceHandle(v4);
    }
    else
    {
      v7 = GetLastError();
      v5 = v7;
      if ( v7 > 0 )
        v5 = (unsigned __int16)v7 | 0x80070000;
      LogError(L"OpenService failed with error 0x%1!x!.", v5);
    }
    CloseServiceHandle(v3);
  }
  else
  {
    v8 = GetLastError();
    v5 = v8;
    if ( v8 > 0 )
      v5 = (unsigned __int16)v8 | 0x80070000;
    LogError(L"OpenSCManager failed with error 0x%1!x!.", v5);
  }
  if ( (v5 & 0x80000000) != 0 )
    LogError(L"GetWindowsInstallerStatus failed with error = 0x%1!x!.", v5);
  return v5;
}

```

## disassembly

```asm
0x140016ff0  push    rbx
0x140016ff2  push    rsi
0x140016ff3  push    rdi
0x140016ff4  push    r14
0x140016ff6  sub     rsp, 88h
0x140016ffd  mov     rax, cs:__security_cookie
0x140017004  xor     rax, rsp
0x140017007  mov     [rsp+0A8h+var_30], rax
0x14001700c  xorps   xmm0, xmm0
0x14001700f  xor     eax, eax
0x140017011  xor     edx, edx; lpDatabaseName
0x140017013  mov     [rsp+0A8h+var_50], eax
0x140017017  movups  xmmword ptr [rsp+0A8h+Buffer], xmm0
0x14001701c  mov     [rsp+0A8h+var_78], eax
0x140017020  mov     r14, rcx
0x140017023  mov     eax, dword ptr cs:aMsiserver+10h; "r"
0x140017029  movups  [rsp+0A8h+var_60], xmm0
0x14001702e  lea     r8d, [rdx+1]; dwDesiredAccess
0x140017032  mov     [rsp+0A8h+var_38], eax
0x140017036  movups  xmm0, xmmword ptr cs:aMsiserver; "msiserver"
0x14001703d  mov     byte ptr [rcx], 1
0x140017040  xor     ecx, ecx; lpMachineName
0x140017042  movups  xmmword ptr [rsp+0A8h+ServiceName], xmm0
0x140017047  call    cs:__imp_OpenSCManagerW
0x14001704d  mov     rsi, rax
0x140017050  test    rax, rax
0x140017053  jz      loc_14001711D
0x140017059  mov     r8d, 4; dwDesiredAccess
0x14001705f  lea     rdx, [rsp+0A8h+ServiceName]; lpServiceName
0x140017064  mov     rcx, rax; hSCManager
0x140017067  call    cs:__imp_OpenServiceW
0x14001706d  mov     rdi, rax
0x140017070  test    rax, rax
0x140017073  jz      short loc_1400170EF
0x140017075  lea     rax, [rsp+0A8h+var_78]
0x14001707a  mov     r9d, 24h ; '$'; cbBufSize
0x140017080  lea     r8, [rsp+0A8h+Buffer]; lpBuffer
0x140017085  mov     [rsp+0A8h+pcbBytesNeeded], rax; pcbBytesNeeded
0x14001708a  xor     edx, edx; InfoLevel
0x14001708c  mov     rcx, rdi; hService
0x14001708f  call    cs:__imp_QueryServiceStatusEx
0x140017095  test    eax, eax
0x140017097  jz      short loc_1400170C1
0x140017099  xor     ebx, ebx
0x14001709b  cmp     dword ptr [rsp+0A8h+Buffer+4], 4
0x1400170a0  jnz     short loc_1400170E4
0x1400170a2  mov     r8d, dword ptr [rsp+0A8h+Buffer+8]
0x1400170a7  test    r8b, 4
0x1400170ab  jnz     short loc_1400170E4
0x1400170ad  lea     edx, [rbx+4]
0x1400170b0  mov     [r14], bl
0x1400170b3  lea     rcx, aWindowsInstall; "Windows Installer service is busy.  dwC"...
0x1400170ba  call    ?LogInfo@@YAXPEBGZZ; LogInfo(ushort const *,...)
0x1400170bf  jmp     short loc_1400170E4
0x1400170c1  call    cs:__imp_GetLastError
0x1400170c7  mov     ebx, eax
0x1400170c9  test    eax, eax
0x1400170cb  jle     short loc_1400170D6
0x1400170cd  movzx   ebx, ax
0x1400170d0  or      ebx, 80070000h
0x1400170d6  mov     edx, ebx
0x1400170d8  lea     rcx, aQueryservicest; "QueryServiceStatusEx failed with error "...
0x1400170df  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x1400170e4  mov     rcx, rdi; hSCObject
0x1400170e7  call    cs:__imp_CloseServiceHandle
0x1400170ed  jmp     short loc_140017112
0x1400170ef  call    cs:__imp_GetLastError
0x1400170f5  mov     ebx, eax
0x1400170f7  test    eax, eax
0x1400170f9  jle     short loc_140017104
0x1400170fb  movzx   ebx, ax
0x1400170fe  or      ebx, 80070000h
0x140017104  mov     edx, ebx
0x140017106  lea     rcx, aOpenserviceFai; "OpenService failed with error 0x%1!x!."
0x14001710d  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x140017112  mov     rcx, rsi; hSCObject
0x140017115  call    cs:__imp_CloseServiceHandle
0x14001711b  jmp     short loc_140017140
0x14001711d  call    cs:__imp_GetLastError
0x140017123  mov     ebx, eax
0x140017125  test    eax, eax
0x140017127  jle     short loc_140017132
0x140017129  movzx   ebx, ax
0x14001712c  or      ebx, 80070000h
0x140017132  mov     edx, ebx
0x140017134  lea     rcx, aOpenscmanagerF; "OpenSCManager failed with error 0x%1!x!"...
0x14001713b  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x140017140  test    ebx, ebx
0x140017142  jns     short loc_140017152
0x140017144  mov     edx, ebx
0x140017146  lea     rcx, aGetwindowsinst; "GetWindowsInstallerStatus failed with e"...
0x14001714d  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x140017152  mov     eax, ebx
0x140017154  mov     rcx, [rsp+0A8h+var_30]
0x140017159  xor     rcx, rsp; StackCookie
0x14001715c  call    __security_check_cookie
0x140017161  add     rsp, 88h
0x140017168  pop     r14
0x14001716a  pop     rdi
0x14001716b  pop     rsi
0x14001716c  pop     rbx
0x14001716d  retn
```
