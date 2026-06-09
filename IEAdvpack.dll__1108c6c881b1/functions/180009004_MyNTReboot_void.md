# MyNTReboot(void)

- ea: `0x180009004`
- end: `0x18000910a`
- name: `?MyNTReboot@@YAHXZ`
- size: `262`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180004880`

## callees

- `0x180008a6c`
- `0x180009004`
- `0x18001b980`

## import_xrefs

- `USER32!ExitWindowsEx` at `0x1800090e1`
- `USER32!ExitWindowsEx` at `0x1800090e1`
- `KERNEL32!CloseHandle` at `0x1800090c0`
- `KERNEL32!CloseHandle` at `0x1800090c0`
- `KERNEL32!GetCurrentProcess` at `0x18000902a`
- `KERNEL32!GetCurrentProcess` at `0x18000902a`
- `ADVAPI32!OpenProcessToken` at `0x18000903d`
- `ADVAPI32!OpenProcessToken` at `0x18000903d`
- `ADVAPI32!LookupPrivilegeValueW` at `0x18000907c`
- `ADVAPI32!LookupPrivilegeValueW` at `0x18000907c`
- `ADVAPI32!AdjustTokenPrivileges` at `0x1800090b3`
- `ADVAPI32!AdjustTokenPrivileges` at `0x1800090b3`

## string_xrefs

- `0x180009075`: `SeShutdownPrivilege`

## pseudocode

```c
__int64 MyNTReboot(void)
{
  HANDLE CurrentProcess; // rax
  UINT v1; // edx
  BOOL v3; // ebx
  HANDLE TokenHandle; // [rsp+30h] [rbp-28h] BYREF
  _LUID Luid[2]; // [rsp+38h] [rbp-20h] BYREF

  TokenHandle = 0;
  *(_OWORD *)&Luid[0].LowPart = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle) )
  {
    v1 = 1134;
LABEL_3:
    MsgBox2Param(0, v1, 0, 0, 0x10u, 0);
    return 0;
  }
  LookupPrivilegeValueW(0, L"SeShutdownPrivilege", (PLUID)&Luid[0].HighPart);
  Luid[0].LowPart = 1;
  Luid[1].HighPart = 2;
  v3 = AdjustTokenPrivileges(TokenHandle, 0, (PTOKEN_PRIVILEGES)Luid, 0, 0, 0);
  CloseHandle(TokenHandle);
  if ( !v3 )
  {
    v1 = 1135;
    goto LABEL_3;
  }
  if ( !ExitWindowsEx(2u, 0) )
  {
    v1 = 1136;
    goto LABEL_3;
  }
  return 1;
}

```

## disassembly

```asm
0x180009004  push    rbx
0x180009006  sub     rsp, 50h
0x18000900a  mov     rax, cs:__security_cookie
0x180009011  xor     rax, rsp
0x180009014  mov     [rsp+58h+var_10], rax
0x180009019  xorps   xmm0, xmm0
0x18000901c  mov     [rsp+58h+TokenHandle], 0
0x180009025  movups  xmmword ptr [rsp+58h+Luid.LowPart], xmm0
0x18000902a  call    cs:__imp_GetCurrentProcess
0x180009030  lea     r8, [rsp+58h+TokenHandle]; TokenHandle
0x180009035  mov     edx, 28h ; '('; DesiredAccess
0x18000903a  mov     rcx, rax; ProcessHandle
0x18000903d  call    cs:__imp_OpenProcessToken
0x180009043  xor     ecx, ecx; hWnd
0x180009045  test    eax, eax
0x180009047  jnz     short loc_180009070
0x180009049  xor     r9d, r9d; unsigned __int16 *
0x18000904c  mov     edx, 46Eh; uID
0x180009051  xor     r8d, r8d; unsigned __int16 *
0x180009054  mov     dword ptr [rsp+58h+ReturnLength], 0; unsigned int
0x18000905c  mov     dword ptr [rsp+58h+PreviousState], 10h; unsigned int
0x180009064  call    ?MsgBox2Param@@YAHPEAUHWND__@@IPEBG1II@Z; MsgBox2Param(HWND__ *,uint,ushort const *,ushort const *,uint,uint)
0x180009069  xor     eax, eax
0x18000906b  jmp     loc_1800090F7
0x180009070  lea     r8, [rsp+58h+Luid.HighPart]; lpLuid
0x180009075  lea     rdx, aSeshutdownpriv; "SeShutdownPrivilege"
0x18000907c  call    cs:__imp_LookupPrivilegeValueW
0x180009082  mov     rcx, [rsp+58h+TokenHandle]; TokenHandle
0x180009087  lea     r8, [rsp+58h+Luid]; NewState
0x18000908c  xor     r9d, r9d; BufferLength
0x18000908f  mov     [rsp+58h+ReturnLength], 0; ReturnLength
0x180009098  xor     edx, edx; DisableAllPrivileges
0x18000909a  mov     [rsp+58h+Luid.LowPart], 1
0x1800090a2  mov     [rsp+58h+Luid.HighPart+8], 2
0x1800090aa  mov     [rsp+58h+PreviousState], 0; PreviousState
0x1800090b3  call    cs:__imp_AdjustTokenPrivileges
0x1800090b9  mov     rcx, [rsp+58h+TokenHandle]; hObject
0x1800090be  mov     ebx, eax
0x1800090c0  call    cs:__imp_CloseHandle
0x1800090c6  test    ebx, ebx
0x1800090c8  jnz     short loc_1800090DC
0x1800090ca  mov     edx, 46Fh
0x1800090cf  xor     r9d, r9d
0x1800090d2  xor     r8d, r8d
0x1800090d5  xor     ecx, ecx
0x1800090d7  jmp     loc_180009054
0x1800090dc  xor     edx, edx; dwReason
0x1800090de  lea     ecx, [rdx+2]; uFlags
0x1800090e1  call    cs:__imp_ExitWindowsEx
0x1800090e7  test    eax, eax
0x1800090e9  jnz     short loc_1800090F2
0x1800090eb  mov     edx, 470h
0x1800090f0  jmp     short loc_1800090CF
0x1800090f2  mov     eax, 1
0x1800090f7  mov     rcx, [rsp+58h+var_10]
0x1800090fc  xor     rcx, rsp; StackCookie
0x1800090ff  call    __security_check_cookie
0x180009104  add     rsp, 50h
0x180009108  pop     rbx
0x180009109  retn
```
