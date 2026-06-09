# AdjustPrivilege(ushort const *,EPrivilegeStatus)

- ea: `0x1400651a0`
- end: `0x140065361`
- name: `?AdjustPrivilege@@YAJPEBGW4EPrivilegeStatus@@@Z`
- size: `449`
- prototype: `__int64 __fastcall(const WCHAR *, int)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14000ce14`
- `0x140068594`
- `0x1400692bc`

## callees

- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x1400651a0`
- `0x14007cbd0`

## import_xrefs

- `ADVAPI32!OpenProcessToken` at `0x1400651e5`
- `ADVAPI32!OpenProcessToken` at `0x1400651e5`
- `ADVAPI32!AdjustTokenPrivileges` at `0x14006526e`
- `ADVAPI32!AdjustTokenPrivileges` at `0x14006526e`
- `ADVAPI32!LookupPrivilegeValueW` at `0x140065219`
- `ADVAPI32!LookupPrivilegeValueW` at `0x140065219`
- `KERNEL32!CloseHandle` at `0x14006533f`
- `KERNEL32!CloseHandle` at `0x14006533f`
- `KERNEL32!GetLastError` at `0x1400651ef`
- `KERNEL32!GetLastError` at `0x140065223`
- `KERNEL32!GetLastError` at `0x14006527c`
- `KERNEL32!GetLastError` at `0x1400651ef`
- `KERNEL32!GetLastError` at `0x140065223`
- `KERNEL32!GetLastError` at `0x14006527c`
- `KERNEL32!IsDebuggerPresent` at `0x1400652d7`
- `KERNEL32!IsDebuggerPresent` at `0x1400652d7`
- `KERNEL32!GetCurrentProcess` at `0x1400651d2`
- `KERNEL32!GetCurrentProcess` at `0x1400651d2`

## string_xrefs

- `0x1400652ac`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x1400652a5`: `AdjustPrivilege`

## pseudocode

```c
__int64 __fastcall AdjustPrivilege(const WCHAR *a1, int a2)
{
  HANDLE CurrentProcess; // rax
  signed int v5; // eax
  signed int v6; // ebx
  unsigned int v7; // r12d
  signed int v8; // eax
  signed int LastError; // eax
  signed int v11; // [rsp+30h] [rbp-68h]
  signed int v12; // [rsp+38h] [rbp-60h]
  void *TokenHandle; // [rsp+40h] [rbp-58h] BYREF
  _LUID Luid[2]; // [rsp+48h] [rbp-50h] BYREF

  TokenHandle = 0;
  *(_OWORD *)&Luid[0].LowPart = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle) )
  {
    if ( LookupPrivilegeValueW(0, a1, (PLUID)&Luid[0].HighPart) )
    {
      v6 = 0;
      Luid[0].LowPart = 1;
      Luid[1].HighPart = a2 != 0 ? 2 : 0;
      if ( AdjustTokenPrivileges(TokenHandle, 0, (PTOKEN_PRIVILEGES)Luid, 0, 0, 0) )
        goto LABEL_18;
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      v7 = 1353;
    }
    else
    {
      v8 = GetLastError();
      v6 = v8;
      if ( v8 > 0 )
        v6 = (unsigned __int16)v8 | 0x80070000;
      v7 = 1347;
    }
  }
  else
  {
    v5 = GetLastError();
    v6 = v5;
    if ( v5 > 0 )
      v6 = (unsigned __int16)v5 | 0x80070000;
    v7 = 1340;
  }
  if ( v6 >= 0 )
    v6 = -2147467259;
  LOGASSERTHR(L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp", v7, L"AdjustPrivilege", L"CBRAEx", L"fSuccess", v6);
  if ( IsDebuggerPresent() )
  {
    v12 = v6;
    DEBUGMSGLEVEL(
      2u,
      L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
      L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
      v7,
      L"AdjustPrivilege",
      L"CBRAEx",
      L"fSuccess",
      v12);
  }
  else
  {
    v11 = v6;
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
      v7,
      L"AdjustPrivilege",
      L"CBRAEx",
      L"fSuccess",
      v11);
  }
LABEL_18:
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(TokenHandle);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1400651a0  push    rbx
0x1400651a2  push    rbp
0x1400651a3  push    rsi
0x1400651a4  push    rdi
0x1400651a5  push    r12
0x1400651a7  push    r14
0x1400651a9  sub     rsp, 68h
0x1400651ad  mov     rax, cs:__security_cookie
0x1400651b4  xor     rax, rsp
0x1400651b7  mov     [rsp+98h+var_40], rax
0x1400651bc  xorps   xmm0, xmm0
0x1400651bf  mov     [rsp+98h+TokenHandle], 0
0x1400651c8  movups  xmmword ptr [rsp+98h+Luid.LowPart], xmm0
0x1400651cd  mov     edi, edx
0x1400651cf  mov     rbx, rcx
0x1400651d2  call    cs:__imp_GetCurrentProcess
0x1400651d8  lea     r8, [rsp+98h+TokenHandle]; TokenHandle
0x1400651dd  mov     edx, 28h ; '('; DesiredAccess
0x1400651e2  mov     rcx, rax; ProcessHandle
0x1400651e5  call    cs:__imp_OpenProcessToken
0x1400651eb  test    eax, eax
0x1400651ed  jnz     short loc_14006520F
0x1400651ef  call    cs:__imp_GetLastError
0x1400651f5  mov     ebx, eax
0x1400651f7  test    eax, eax
0x1400651f9  jle     short loc_140065204
0x1400651fb  movzx   ebx, ax
0x1400651fe  or      ebx, 80070000h
0x140065204  mov     r12d, 53Ch
0x14006520a  jmp     loc_140065297
0x14006520f  lea     r8, [rsp+98h+Luid.HighPart]; lpLuid
0x140065214  mov     rdx, rbx; lpName
0x140065217  xor     ecx, ecx; lpSystemName
0x140065219  call    cs:__imp_LookupPrivilegeValueW
0x14006521f  test    eax, eax
0x140065221  jnz     short loc_140065240
0x140065223  call    cs:__imp_GetLastError
0x140065229  mov     ebx, eax
0x14006522b  test    eax, eax
0x14006522d  jle     short loc_140065238
0x14006522f  movzx   ebx, ax
0x140065232  or      ebx, 80070000h
0x140065238  mov     r12d, 543h
0x14006523e  jmp     short loc_140065297
0x140065240  mov     rcx, [rsp+98h+TokenHandle]; TokenHandle
0x140065245  lea     r8, [rsp+98h+Luid]; NewState
0x14006524a  xor     ebx, ebx
0x14006524c  mov     [rsp+98h+Luid.LowPart], 1
0x140065254  neg     edi
0x140065256  mov     [rsp+98h+ReturnLength], rbx; ReturnLength
0x14006525b  mov     [rsp+98h+PreviousState], rbx; PreviousState
0x140065260  sbb     eax, eax
0x140065262  xor     r9d, r9d; BufferLength
0x140065265  and     eax, 2
0x140065268  xor     edx, edx; DisableAllPrivileges
0x14006526a  mov     [rsp+98h+Luid.HighPart+8], eax
0x14006526e  call    cs:__imp_AdjustTokenPrivileges
0x140065274  test    eax, eax
0x140065276  jnz     loc_140065330
0x14006527c  call    cs:__imp_GetLastError
0x140065282  mov     ebx, eax
0x140065284  test    eax, eax
0x140065286  jle     short loc_140065291
0x140065288  movzx   ebx, ax
0x14006528b  or      ebx, 80070000h
0x140065291  mov     r12d, 549h
0x140065297  mov     eax, 80004005h
0x14006529c  lea     r14, aCbraex; "CBRAEx"
0x1400652a3  test    ebx, ebx
0x1400652a5  lea     rsi, aAdjustprivileg; "AdjustPrivilege"
0x1400652ac  lea     rdi, aTermsrvWmsSrcC_22; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x1400652b3  mov     r9, r14; unsigned __int16 *
0x1400652b6  cmovns  ebx, eax
0x1400652b9  lea     rbp, aFsuccess; "fSuccess"
0x1400652c0  mov     dword ptr [rsp+98h+ReturnLength], ebx; int
0x1400652c4  mov     r8, rsi; unsigned __int16 *
0x1400652c7  mov     edx, r12d; unsigned int
0x1400652ca  mov     [rsp+98h+PreviousState], rbp; unsigned __int16 *
0x1400652cf  mov     rcx, rdi; unsigned __int16 *
0x1400652d2  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400652d7  call    cs:__imp_IsDebuggerPresent
0x1400652dd  test    eax, eax
0x1400652df  jz      short loc_14006530D
0x1400652e1  mov     [rsp+98h+var_60], ebx
0x1400652e5  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x1400652ec  mov     [rsp+98h+var_68], rbp
0x1400652f1  mov     r9d, r12d
0x1400652f4  mov     [rsp+98h+ReturnLength], r14
0x1400652f9  mov     r8, rdi
0x1400652fc  mov     ecx, 2; unsigned __int8
0x140065301  mov     [rsp+98h+PreviousState], rsi
0x140065306  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14006530b  jmp     short loc_140065330
0x14006530d  mov     dword ptr [rsp+98h+var_68], ebx
0x140065311  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140065318  mov     [rsp+98h+ReturnLength], rbp
0x14006531d  mov     r9, rsi
0x140065320  mov     r8d, r12d
0x140065323  mov     [rsp+98h+PreviousState], r14
0x140065328  mov     rdx, rdi
0x14006532b  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140065330  mov     rcx, [rsp+98h+TokenHandle]; hObject
0x140065335  lea     rdx, [rcx-1]
0x140065339  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x14006533d  ja      short loc_140065345
0x14006533f  call    cs:__imp_CloseHandle
0x140065345  mov     eax, ebx
0x140065347  mov     rcx, [rsp+98h+var_40]
0x14006534c  xor     rcx, rsp; StackCookie
0x14006534f  call    __security_check_cookie
0x140065354  add     rsp, 68h
0x140065358  pop     r14
0x14006535a  pop     r12
0x14006535c  pop     rdi
0x14006535d  pop     rsi
0x14006535e  pop     rbp
0x14006535f  pop     rbx
0x140065360  retn
```
