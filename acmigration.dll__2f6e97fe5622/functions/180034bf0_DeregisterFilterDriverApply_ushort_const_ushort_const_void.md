# DeregisterFilterDriverApply(ushort const *,ushort const *,void *)

- ea: `0x180034bf0`
- end: `0x180034dcf`
- name: `?DeregisterFilterDriverApply@@YAJPEBG0PEAX@Z`
- size: `479`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *, void *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001cf0`
- `0x180002874`
- `0x18000a51c`
- `0x180034bf0`
- `0x1800543c0`

## import_xrefs

- `KERNEL32!CreateProcessW` at `0x180034d1f`
- `KERNEL32!CreateProcessW` at `0x180034d1f`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180034c62`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180034c62`
- `KERNEL32!CloseHandle` at `0x180034d97`
- `KERNEL32!CloseHandle` at `0x180034da7`
- `KERNEL32!CloseHandle` at `0x180034d97`
- `KERNEL32!CloseHandle` at `0x180034da7`
- `KERNEL32!GetLastError` at `0x180034c6c`
- `KERNEL32!GetLastError` at `0x180034cb9`
- `KERNEL32!GetLastError` at `0x180034d29`
- `KERNEL32!GetLastError` at `0x180034d64`
- `KERNEL32!GetLastError` at `0x180034c6c`
- `KERNEL32!GetLastError` at `0x180034cb9`
- `KERNEL32!GetLastError` at `0x180034d29`
- `KERNEL32!GetLastError` at `0x180034d64`
- `KERNEL32!WaitForSingleObject` at `0x180034d5a`
- `KERNEL32!WaitForSingleObject` at `0x180034d5a`

## string_xrefs

- `0x180034c56`: `%windir%\system32\netcfg.exe -u `
- `0x180034c81`: `DeRegisterFilterDriver: Unable to expand windows directory.`
- `0x180034cce`: `DeRegisterFilterDriver: Concatenating CommandLine failed.`
- `0x180034d3e`: `DeRegisterFilterDriver: CreateProcess Failed.`
- `0x180034d79`: `DeRegisterFilterDriver: Waiting on CreateProcess failed.`

## pseudocode

```c
__int64 __fastcall DeregisterFilterDriverApply(const unsigned __int16 *a1, const unsigned __int16 *a2, void *a3)
{
  signed int v4; // eax
  unsigned int v5; // ebx
  signed int LastError; // eax
  signed int v7; // eax
  signed int v8; // eax
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+50h] [rbp-B0h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Dst[256]; // [rsp+E0h] [rbp-20h] BYREF

  memset_0(Dst, 0, sizeof(Dst));
  memset_0(&StartupInfo.cb + 1, 0, 0x64u);
  StartupInfo.cb = 104;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  if ( ExpandEnvironmentStringsW(L"%windir%\\system32\\netcfg.exe -u ", Dst, 0x100u) )
  {
    if ( StringCchCatW(Dst, 0x100u, a2) )
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      AslLogCallPrintf(
        1,
        "DeregisterFilterDriverApply",
        149,
        "DeRegisterFilterDriver: Concatenating CommandLine failed.");
    }
    else if ( CreateProcessW(0, Dst, 0, 0, 0, 0, 0, 0, &StartupInfo, &ProcessInformation) )
    {
      if ( WaitForSingleObject(ProcessInformation.hProcess, 0xFFFFFFFF) == -1 )
      {
        v8 = GetLastError();
        v5 = v8;
        if ( v8 > 0 )
          v5 = (unsigned __int16)v8 | 0x80070000;
        AslLogCallPrintf(
          1,
          "DeregisterFilterDriverApply",
          174,
          "DeRegisterFilterDriver: Waiting on CreateProcess failed.");
      }
      else
      {
        v5 = 0;
      }
    }
    else
    {
      v7 = GetLastError();
      v5 = v7;
      if ( v7 > 0 )
        v5 = (unsigned __int16)v7 | 0x80070000;
      AslLogCallPrintf(1, "DeregisterFilterDriverApply", 164, "DeRegisterFilterDriver: CreateProcess Failed.");
    }
  }
  else
  {
    v4 = GetLastError();
    v5 = v4;
    if ( v4 > 0 )
      v5 = (unsigned __int16)v4 | 0x80070000;
    AslLogCallPrintf(
      1,
      "DeregisterFilterDriverApply",
      143,
      "DeRegisterFilterDriver: Unable to expand windows directory.");
  }
  if ( ProcessInformation.hProcess )
    CloseHandle(ProcessInformation.hProcess);
  if ( ProcessInformation.hThread )
    CloseHandle(ProcessInformation.hThread);
  return v5;
}

```

## disassembly

```asm
0x180034bf0  mov     [rsp-8+arg_0], rbx
0x180034bf5  push    rbp
0x180034bf6  lea     rbp, [rsp-1F0h]
0x180034bfe  sub     rsp, 2F0h
0x180034c05  mov     rax, cs:__security_cookie
0x180034c0c  xor     rax, rsp
0x180034c0f  mov     [rbp+1F0h+var_10], rax
0x180034c16  mov     rbx, rdx
0x180034c19  lea     rcx, [rbp+1F0h+Dst]; void *
0x180034c1d  xor     edx, edx; Val
0x180034c1f  mov     r8d, 200h; Size
0x180034c25  call    memset_0
0x180034c2a  xor     edx, edx; Val
0x180034c2c  lea     rcx, [rsp+2F0h+StartupInfo+4]; void *
0x180034c31  lea     r8d, [rdx+64h]; Size
0x180034c35  call    memset_0
0x180034c3a  xorps   xmm0, xmm0
0x180034c3d  mov     [rsp+2F0h+StartupInfo.cb], 68h ; 'h'
0x180034c45  xor     eax, eax
0x180034c47  lea     rdx, [rbp+1F0h+Dst]; lpDst
0x180034c4b  mov     r8d, 100h; nSize
0x180034c51  mov     qword ptr [rsp+2F0h+ProcessInformation.dwProcessId], rax
0x180034c56  lea     rcx, aWindirSystem32_0; "%windir%\\system32\\netcfg.exe -u "
0x180034c5d  movups  xmmword ptr [rsp+2F0h+ProcessInformation.hProcess], xmm0
0x180034c62  call    cs:__imp_ExpandEnvironmentStringsW
0x180034c68  test    eax, eax
0x180034c6a  jnz     short loc_180034CA4
0x180034c6c  call    cs:__imp_GetLastError
0x180034c72  mov     ebx, eax
0x180034c74  test    eax, eax
0x180034c76  jle     short loc_180034C81
0x180034c78  movzx   ebx, ax
0x180034c7b  or      ebx, 80070000h
0x180034c81  lea     r9, aDeregisterfilt; "DeRegisterFilterDriver: Unable to expan"...
0x180034c88  mov     r8d, 8Fh
0x180034c8e  lea     rdx, aDeregisterfilt_2; "DeregisterFilterDriverApply"
0x180034c95  mov     ecx, 1
0x180034c9a  call    AslLogCallPrintf
0x180034c9f  jmp     loc_180034D8D
0x180034ca4  mov     r8, rbx; pszSrc
0x180034ca7  lea     rcx, [rbp+1F0h+Dst]; pszDest
0x180034cab  mov     edx, 100h; cchDest
0x180034cb0  call    StringCchCatW
0x180034cb5  test    eax, eax
0x180034cb7  jz      short loc_180034CDD
0x180034cb9  call    cs:__imp_GetLastError
0x180034cbf  mov     ebx, eax
0x180034cc1  test    eax, eax
0x180034cc3  jle     short loc_180034CCE
0x180034cc5  movzx   ebx, ax
0x180034cc8  or      ebx, 80070000h
0x180034cce  lea     r9, aDeregisterfilt_4; "DeRegisterFilterDriver: Concatenating C"...
0x180034cd5  mov     r8d, 95h
0x180034cdb  jmp     short loc_180034C8E
0x180034cdd  lea     rax, [rsp+2F0h+ProcessInformation]
0x180034ce2  xor     r9d, r9d; lpThreadAttributes
0x180034ce5  mov     [rsp+2F0h+lpProcessInformation], rax; lpProcessInformation
0x180034cea  lea     rdx, [rbp+1F0h+Dst]; lpCommandLine
0x180034cee  lea     rax, [rsp+2F0h+StartupInfo]
0x180034cf3  xor     r8d, r8d; lpProcessAttributes
0x180034cf6  mov     [rsp+2F0h+lpStartupInfo], rax; lpStartupInfo
0x180034cfb  xor     ecx, ecx; lpApplicationName
0x180034cfd  mov     [rsp+2F0h+lpCurrentDirectory], 0; lpCurrentDirectory
0x180034d06  mov     [rsp+2F0h+lpEnvironment], 0; lpEnvironment
0x180034d0f  mov     [rsp+2F0h+dwCreationFlags], 0; dwCreationFlags
0x180034d17  mov     [rsp+2F0h+bInheritHandles], 0; bInheritHandles
0x180034d1f  call    cs:__imp_CreateProcessW
0x180034d25  test    eax, eax
0x180034d27  jnz     short loc_180034D50
0x180034d29  call    cs:__imp_GetLastError
0x180034d2f  mov     ebx, eax
0x180034d31  test    eax, eax
0x180034d33  jle     short loc_180034D3E
0x180034d35  movzx   ebx, ax
0x180034d38  or      ebx, 80070000h
0x180034d3e  lea     r9, aDeregisterfilt_1; "DeRegisterFilterDriver: CreateProcess F"...
0x180034d45  mov     r8d, 0A4h
0x180034d4b  jmp     loc_180034C8E
0x180034d50  mov     rcx, [rsp+2F0h+ProcessInformation.hProcess]; hHandle
0x180034d55  or      ebx, 0FFFFFFFFh
0x180034d58  mov     edx, ebx; dwMilliseconds
0x180034d5a  call    cs:__imp_WaitForSingleObject
0x180034d60  cmp     eax, ebx
0x180034d62  jnz     short loc_180034D8B
0x180034d64  call    cs:__imp_GetLastError
0x180034d6a  mov     ebx, eax
0x180034d6c  test    eax, eax
0x180034d6e  jle     short loc_180034D79
0x180034d70  movzx   ebx, ax
0x180034d73  or      ebx, 80070000h
0x180034d79  lea     r9, aDeregisterfilt_3; "DeRegisterFilterDriver: Waiting on Crea"...
0x180034d80  mov     r8d, 0AEh
0x180034d86  jmp     loc_180034C8E
0x180034d8b  xor     ebx, ebx
0x180034d8d  mov     rcx, [rsp+2F0h+ProcessInformation.hProcess]; hObject
0x180034d92  test    rcx, rcx
0x180034d95  jz      short loc_180034D9D
0x180034d97  call    cs:__imp_CloseHandle
0x180034d9d  mov     rcx, [rsp+2F0h+ProcessInformation.hThread]; hObject
0x180034da2  test    rcx, rcx
0x180034da5  jz      short loc_180034DAD
0x180034da7  call    cs:__imp_CloseHandle
0x180034dad  mov     eax, ebx
0x180034daf  mov     rcx, [rbp+1F0h+var_10]
0x180034db6  xor     rcx, rsp; StackCookie
0x180034db9  call    __security_check_cookie
0x180034dbe  mov     rbx, [rsp+2F0h+arg_0]
0x180034dc6  add     rsp, 2F0h
0x180034dcd  pop     rbp
0x180034dce  retn
```
