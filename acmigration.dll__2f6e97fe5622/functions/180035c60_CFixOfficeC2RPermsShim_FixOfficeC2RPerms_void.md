# CFixOfficeC2RPermsShim::FixOfficeC2RPerms(void)

- ea: `0x180035c60`
- end: `0x180035ef9`
- name: `?FixOfficeC2RPerms@CFixOfficeC2RPermsShim@@QEAAKXZ`
- size: `665`
- prototype: `unsigned int __fastcall(CFixOfficeC2RPermsShim *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180035c40`

## callees

- `0x180001cf0`
- `0x180002874`
- `0x18000a51c`
- `0x180035c60`
- `0x1800543c0`

## import_xrefs

- `KERNEL32!CreateProcessW` at `0x180035e59`
- `KERNEL32!CreateProcessW` at `0x180035e59`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180035ccd`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180035d12`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180035ccd`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180035d12`
- `KERNEL32!CloseHandle` at `0x180035eb6`
- `KERNEL32!CloseHandle` at `0x180035ec6`
- `KERNEL32!CloseHandle` at `0x180035eb6`
- `KERNEL32!CloseHandle` at `0x180035ec6`
- `KERNEL32!GetLastError` at `0x180035cd7`
- `KERNEL32!GetLastError` at `0x180035d1c`
- `KERNEL32!GetLastError` at `0x180035d6f`
- `KERNEL32!GetLastError` at `0x180035da1`
- `KERNEL32!GetLastError` at `0x180035dd0`
- `KERNEL32!GetLastError` at `0x180035dff`
- `KERNEL32!GetLastError` at `0x180035e63`
- `KERNEL32!GetLastError` at `0x180035e8b`
- `KERNEL32!GetLastError` at `0x180035cd7`
- `KERNEL32!GetLastError` at `0x180035d1c`
- `KERNEL32!GetLastError` at `0x180035d6f`
- `KERNEL32!GetLastError` at `0x180035da1`
- `KERNEL32!GetLastError` at `0x180035dd0`
- `KERNEL32!GetLastError` at `0x180035dff`
- `KERNEL32!GetLastError` at `0x180035e63`
- `KERNEL32!GetLastError` at `0x180035e8b`
- `KERNEL32!WaitForSingleObject` at `0x180035e80`
- `KERNEL32!WaitForSingleObject` at `0x180035e80`

## string_xrefs

- `0x180035cc6`: `%windir%\system32\icacls.exe `
- `0x180035cdd`: `[FixOfficeC2RPermsShim] Error expanding icacls exe command line. [%d]`
- `0x180035d22`: `[FixOfficeC2RPermsShim] Error expanding Office C2R directory. [%d]`
- `0x180035d75`: `[FixOfficeC2RPermsShim] Concatenating Quote to dnd of ICACLSBuffer failed. [%d]`
- `0x180035da7`: `[FixOfficeC2RPermsShim] Concatenating Quote to end of PathBuffer failed. [%d]`
- `0x180035dd6`: `[FixOfficeC2RPermsShim] Concatenating CommandLine failed. [%d]`
- `0x180035e05`: `[FixOfficeC2RPermsShim] Concatenating CommandLine options failed. [%d]`
- `0x180035e69`: `[FixOfficeC2RPermsShim] CreateProcess Failed. [%d]`
- `0x180035e91`: `[FixOfficeC2RPermsShim] Waiting on CreateProcess failed. [%d]`

## pseudocode

```c
__int64 __fastcall CFixOfficeC2RPermsShim::FixOfficeC2RPerms(CFixOfficeC2RPermsShim *this)
{
  __int64 i; // rbx
  DWORD LastError; // eax
  const char *v3; // r9
  __int64 v4; // r8
  DWORD v5; // eax
  const char *v6; // r9
  __int64 v7; // r8
  __int64 bInheritHandles; // [rsp+20h] [rbp-E0h]
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+50h] [rbp-B0h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Dst[264]; // [rsp+E0h] [rbp-20h] BYREF
  WCHAR pszDest[264]; // [rsp+2F0h] [rbp+1F0h] BYREF

  for ( i = 0; i != 4; ++i )
  {
    memset_0(Dst, 0, 0x208u);
    memset_0(pszDest, 0, 0x208u);
    if ( !ExpandEnvironmentStringsW(L"%windir%\\system32\\icacls.exe ", Dst, 0x104u) )
    {
      LastError = GetLastError();
      v3 = "[FixOfficeC2RPermsShim] Error expanding icacls exe command line. [%d]";
      v4 = 172;
LABEL_4:
      LODWORD(bInheritHandles) = LastError;
      AslLogCallPrintf(1, "CFixOfficeC2RPermsShim::FixOfficeC2RPerms", v4, v3, bInheritHandles);
      continue;
    }
    if ( !ExpandEnvironmentStringsW(off_18006BDB0[i], pszDest, 0x104u) )
    {
      LastError = GetLastError();
      v3 = "[FixOfficeC2RPermsShim] Error expanding Office C2R directory. [%d]";
      v4 = 177;
      goto LABEL_4;
    }
    memset_0(&StartupInfo.cb + 1, 0, 0x64u);
    StartupInfo.cb = 104;
    memset(&ProcessInformation, 0, sizeof(ProcessInformation));
    if ( StringCchCatW(Dst, 0x104u, L"\"") )
    {
      v5 = GetLastError();
      v6 = "[FixOfficeC2RPermsShim] Concatenating Quote to dnd of ICACLSBuffer failed. [%d]";
      v7 = 193;
LABEL_19:
      LODWORD(bInheritHandles) = v5;
      AslLogCallPrintf(1, "CFixOfficeC2RPermsShim::FixOfficeC2RPerms", v7, v6, bInheritHandles);
      goto LABEL_20;
    }
    if ( StringCchCatW(pszDest, 0x104u, L"\"") )
    {
      v5 = GetLastError();
      v6 = "[FixOfficeC2RPermsShim] Concatenating Quote to end of PathBuffer failed. [%d]";
      v7 = 199;
      goto LABEL_19;
    }
    if ( StringCchCatW(Dst, 0x104u, pszDest) )
    {
      v5 = GetLastError();
      v6 = "[FixOfficeC2RPermsShim] Concatenating CommandLine failed. [%d]";
      v7 = 205;
      goto LABEL_19;
    }
    if ( StringCchCatW(Dst, 0x104u, L" /grant *S-1-15-2-1:(OI)(CI)RX") )
    {
      v5 = GetLastError();
      v6 = "[FixOfficeC2RPermsShim] Concatenating CommandLine options failed. [%d]";
      v7 = 211;
      goto LABEL_19;
    }
    if ( !CreateProcessW(0, Dst, 0, 0, 0, 0, 0, 0, &StartupInfo, &ProcessInformation) )
    {
      v5 = GetLastError();
      v6 = "[FixOfficeC2RPermsShim] CreateProcess Failed. [%d]";
      v7 = 227;
      goto LABEL_19;
    }
    if ( WaitForSingleObject(ProcessInformation.hProcess, 0xFFFFFFFF) == -1 )
    {
      v5 = GetLastError();
      v6 = "[FixOfficeC2RPermsShim] Waiting on CreateProcess failed. [%d]";
      v7 = 236;
      goto LABEL_19;
    }
LABEL_20:
    if ( ProcessInformation.hProcess )
      CloseHandle(ProcessInformation.hProcess);
    if ( ProcessInformation.hThread )
      CloseHandle(ProcessInformation.hThread);
  }
  return 0;
}

```

## disassembly

```asm
0x180035c60  push    rbp
0x180035c62  push    rbx
0x180035c63  push    rsi
0x180035c64  push    r14
0x180035c66  push    r15
0x180035c68  lea     rbp, [rsp-410h]
0x180035c70  sub     rsp, 510h
0x180035c77  mov     rax, cs:__security_cookie
0x180035c7e  xor     rax, rsp
0x180035c81  mov     [rbp+430h+var_30], rax
0x180035c88  xor     ebx, ebx
0x180035c8a  lea     r14, aCfixofficec2rp; "CFixOfficeC2RPermsShim::FixOfficeC2RPer"...
0x180035c91  mov     r15d, 104h
0x180035c97  lea     esi, [rbx+1]
0x180035c9a  xor     edx, edx; Val
0x180035c9c  lea     rcx, [rbp+430h+Dst]; void *
0x180035ca0  mov     r8d, 208h; Size
0x180035ca6  call    memset_0
0x180035cab  xor     edx, edx; Val
0x180035cad  lea     rcx, [rbp+430h+pszDest]; void *
0x180035cb4  mov     r8d, 208h; Size
0x180035cba  call    memset_0
0x180035cbf  mov     r8d, r15d; nSize
0x180035cc2  lea     rdx, [rbp+430h+Dst]; lpDst
0x180035cc6  lea     rcx, aWindirSystem32_5; "%windir%\\system32\\icacls.exe "
0x180035ccd  call    cs:__imp_ExpandEnvironmentStringsW
0x180035cd3  test    eax, eax
0x180035cd5  jnz     short loc_180035CFD
0x180035cd7  call    cs:__imp_GetLastError
0x180035cdd  lea     r9, aFixofficec2rpe_0; "[FixOfficeC2RPermsShim] Error expanding"...
0x180035ce4  mov     r8d, 0ACh
0x180035cea  mov     rdx, r14
0x180035ced  mov     dword ptr [rsp+530h+bInheritHandles], eax
0x180035cf1  mov     ecx, esi
0x180035cf3  call    AslLogCallPrintf
0x180035cf8  jmp     loc_180035ECC
0x180035cfd  lea     rcx, off_18006BDB0; "%programfiles%\\Microsoft Office 15"
0x180035d04  mov     r8d, r15d; nSize
0x180035d07  mov     rcx, [rcx+rbx*8]; lpSrc
0x180035d0b  lea     rdx, [rbp+430h+pszDest]; lpDst
0x180035d12  call    cs:__imp_ExpandEnvironmentStringsW
0x180035d18  test    eax, eax
0x180035d1a  jnz     short loc_180035D31
0x180035d1c  call    cs:__imp_GetLastError
0x180035d22  lea     r9, aFixofficec2rpe_1; "[FixOfficeC2RPermsShim] Error expanding"...
0x180035d29  mov     r8d, 0B1h
0x180035d2f  jmp     short loc_180035CEA
0x180035d31  xor     edx, edx; Val
0x180035d33  lea     rcx, [rsp+530h+StartupInfo+4]; void *
0x180035d38  lea     r8d, [rdx+64h]; Size
0x180035d3c  call    memset_0
0x180035d41  xor     eax, eax
0x180035d43  mov     [rsp+530h+StartupInfo.cb], 68h ; 'h'
0x180035d4b  xorps   xmm0, xmm0
0x180035d4e  mov     qword ptr [rsp+530h+ProcessInformation.dwProcessId], rax
0x180035d53  lea     r8, asc_18006ECB4; "\""
0x180035d5a  mov     rdx, r15; cchDest
0x180035d5d  lea     rcx, [rbp+430h+Dst]; pszDest
0x180035d61  movups  xmmword ptr [rsp+530h+ProcessInformation.hProcess], xmm0
0x180035d66  call    StringCchCatW
0x180035d6b  test    eax, eax
0x180035d6d  jz      short loc_180035D87
0x180035d6f  call    cs:__imp_GetLastError
0x180035d75  lea     r9, aFixofficec2rpe_3; "[FixOfficeC2RPermsShim] Concatenating Q"...
0x180035d7c  mov     r8d, 0C1h
0x180035d82  jmp     loc_180035E9E
0x180035d87  lea     r8, asc_18006ECB4; "\""
0x180035d8e  mov     rdx, r15; cchDest
0x180035d91  lea     rcx, [rbp+430h+pszDest]; pszDest
0x180035d98  call    StringCchCatW
0x180035d9d  test    eax, eax
0x180035d9f  jz      short loc_180035DB9
0x180035da1  call    cs:__imp_GetLastError
0x180035da7  lea     r9, aFixofficec2rpe_7; "[FixOfficeC2RPermsShim] Concatenating Q"...
0x180035dae  mov     r8d, 0C7h
0x180035db4  jmp     loc_180035E9E
0x180035db9  lea     r8, [rbp+430h+pszDest]; pszSrc
0x180035dc0  mov     rdx, r15; cchDest
0x180035dc3  lea     rcx, [rbp+430h+Dst]; pszDest
0x180035dc7  call    StringCchCatW
0x180035dcc  test    eax, eax
0x180035dce  jz      short loc_180035DE8
0x180035dd0  call    cs:__imp_GetLastError
0x180035dd6  lea     r9, aFixofficec2rpe_2; "[FixOfficeC2RPermsShim] Concatenating C"...
0x180035ddd  mov     r8d, 0CDh
0x180035de3  jmp     loc_180035E9E
0x180035de8  lea     r8, aGrantS11521OiC; " /grant *S-1-15-2-1:(OI)(CI)RX"
0x180035def  mov     rdx, r15; cchDest
0x180035df2  lea     rcx, [rbp+430h+Dst]; pszDest
0x180035df6  call    StringCchCatW
0x180035dfb  test    eax, eax
0x180035dfd  jz      short loc_180035E17
0x180035dff  call    cs:__imp_GetLastError
0x180035e05  lea     r9, aFixofficec2rpe_4; "[FixOfficeC2RPermsShim] Concatenating C"...
0x180035e0c  mov     r8d, 0D3h
0x180035e12  jmp     loc_180035E9E
0x180035e17  lea     rax, [rsp+530h+ProcessInformation]
0x180035e1c  xor     r9d, r9d; lpThreadAttributes
0x180035e1f  mov     [rsp+530h+lpProcessInformation], rax; lpProcessInformation
0x180035e24  lea     rdx, [rbp+430h+Dst]; lpCommandLine
0x180035e28  lea     rax, [rsp+530h+StartupInfo]
0x180035e2d  xor     r8d, r8d; lpProcessAttributes
0x180035e30  mov     [rsp+530h+lpStartupInfo], rax; lpStartupInfo
0x180035e35  xor     ecx, ecx; lpApplicationName
0x180035e37  mov     [rsp+530h+lpCurrentDirectory], 0; lpCurrentDirectory
0x180035e40  mov     [rsp+530h+lpEnvironment], 0; lpEnvironment
0x180035e49  mov     [rsp+530h+dwCreationFlags], 0; dwCreationFlags
0x180035e51  mov     dword ptr [rsp+530h+bInheritHandles], 0; bInheritHandles
0x180035e59  call    cs:__imp_CreateProcessW
0x180035e5f  test    eax, eax
0x180035e61  jnz     short loc_180035E78
0x180035e63  call    cs:__imp_GetLastError
0x180035e69  lea     r9, aFixofficec2rpe; "[FixOfficeC2RPermsShim] CreateProcess F"...
0x180035e70  mov     r8d, 0E3h
0x180035e76  jmp     short loc_180035E9E
0x180035e78  mov     rcx, [rsp+530h+ProcessInformation.hProcess]; hHandle
0x180035e7d  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180035e80  call    cs:__imp_WaitForSingleObject
0x180035e86  cmp     eax, 0FFFFFFFFh
0x180035e89  jnz     short loc_180035EAC
0x180035e8b  call    cs:__imp_GetLastError
0x180035e91  lea     r9, aFixofficec2rpe_6; "[FixOfficeC2RPermsShim] Waiting on Crea"...
0x180035e98  mov     r8d, 0ECh
0x180035e9e  mov     rdx, r14
0x180035ea1  mov     dword ptr [rsp+530h+bInheritHandles], eax
0x180035ea5  mov     ecx, esi
0x180035ea7  call    AslLogCallPrintf
0x180035eac  mov     rcx, [rsp+530h+ProcessInformation.hProcess]; hObject
0x180035eb1  test    rcx, rcx
0x180035eb4  jz      short loc_180035EBC
0x180035eb6  call    cs:__imp_CloseHandle
0x180035ebc  mov     rcx, [rsp+530h+ProcessInformation.hThread]; hObject
0x180035ec1  test    rcx, rcx
0x180035ec4  jz      short loc_180035ECC
0x180035ec6  call    cs:__imp_CloseHandle
0x180035ecc  add     rbx, rsi
0x180035ecf  cmp     rbx, 4
0x180035ed3  jnz     loc_180035C9A
0x180035ed9  xor     eax, eax
0x180035edb  mov     rcx, [rbp+430h+var_30]
0x180035ee2  xor     rcx, rsp; StackCookie
0x180035ee5  call    __security_check_cookie
0x180035eea  add     rsp, 510h
0x180035ef1  pop     r15
0x180035ef3  pop     r14
0x180035ef5  pop     rsi
0x180035ef6  pop     rbx
0x180035ef7  pop     rbp
0x180035ef8  retn
```
