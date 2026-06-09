# CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::EnablePrivilege(void *,ushort const *,int,int *)

- ea: `0x180027bfc`
- end: `0x180027cfd`
- name: `?EnablePrivilege@?$CFastDeleteImplT@V?$CDirectoryProviderT@VCWindowsOldAdaptor@@@@$00@@CAJPEAXPEBGHPEAH@Z`
- size: `257`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, const WCHAR *, int, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180029550`

## callees

- `0x180027008`
- `0x180027bfc`
- `0x1800293a4`
- `0x180032310`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180027c6a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180027c6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027c9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027c9b`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180027c91`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180027c91`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x180027c45`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x180027c45`

## pseudocode

```c
__int64 __fastcall CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::EnablePrivilege(
        HANDLE TokenHandle,
        const WCHAR *a2,
        int a3,
        int *a4)
{
  signed int LastError; // eax
  unsigned int v8; // ebx
  char Attributes; // cl
  DWORD ReturnLength; // [rsp+30h] [rbp-40h] BYREF
  _LUID Luid; // [rsp+38h] [rbp-38h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+40h] [rbp-30h] BYREF
  struct _TOKEN_PRIVILEGES PreviousState; // [rsp+50h] [rbp-20h] BYREF

  Luid = 0;
  ReturnLength = 0;
  NewState = 0;
  PreviousState = 0;
  if ( LookupPrivilegeValueW(0, a2, &Luid)
    && (NewState.Privileges[0].Luid = Luid,
        NewState.PrivilegeCount = 1,
        NewState.Privileges[0].Attributes = a3 != 0 ? 2 : 0,
        SetLastError(0),
        AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0x10u, &PreviousState, &ReturnLength)) )
  {
    v8 = 0;
    if ( a4 )
    {
      Attributes = PreviousState.Privileges[0].Attributes;
      if ( !PreviousState.PrivilegeCount )
        Attributes = NewState.Privileges[0].Attributes;
      *a4 = Attributes & 2;
    }
  }
  else
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v8 = -2147467259;
    }
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v8);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v8);
  return v8;
}

```

## disassembly

```asm
0x180027bfc  mov     [rsp-18h+arg_10], rbx
0x180027c01  push    rbp
0x180027c02  push    rsi
0x180027c03  push    rdi
0x180027c04  mov     rbp, rsp
0x180027c07  sub     rsp, 70h
0x180027c0b  mov     rax, cs:__security_cookie
0x180027c12  xor     rax, rsp
0x180027c15  mov     [rbp+var_10], rax
0x180027c19  mov     ebx, r8d
0x180027c1c  mov     qword ptr [rbp+Luid.LowPart], 0
0x180027c24  mov     rsi, rcx
0x180027c27  mov     [rbp+var_40], 0
0x180027c2e  xorps   xmm0, xmm0
0x180027c31  lea     r8, [rbp+Luid]; lpLuid
0x180027c35  xorps   xmm1, xmm1
0x180027c38  xor     ecx, ecx; lpSystemName
0x180027c3a  movups  xmmword ptr [rbp+NewState.PrivilegeCount], xmm0
0x180027c3e  mov     rdi, r9
0x180027c41  movups  xmmword ptr [rbp+var_20.PrivilegeCount], xmm1
0x180027c45  call    cs:__imp_LookupPrivilegeValueW
0x180027c4b  test    eax, eax
0x180027c4d  jz      short loc_180027C9B
0x180027c4f  mov     rax, qword ptr [rbp+Luid.LowPart]
0x180027c53  neg     ebx
0x180027c55  mov     qword ptr [rbp+NewState.Privileges.Luid.LowPart], rax
0x180027c59  sbb     eax, eax
0x180027c5b  mov     [rbp+NewState.PrivilegeCount], 1
0x180027c62  and     eax, 2
0x180027c65  xor     ecx, ecx; dwErrCode
0x180027c67  mov     [rbp+NewState.Privileges.Attributes], eax
0x180027c6a  call    cs:__imp_SetLastError
0x180027c70  lea     rax, [rbp+var_40]
0x180027c74  mov     r9d, 10h; BufferLength
0x180027c7a  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x180027c7f  lea     r8, [rbp+NewState]; NewState
0x180027c83  lea     rax, [rbp+var_20]
0x180027c87  xor     edx, edx; DisableAllPrivileges
0x180027c89  mov     rcx, rsi; TokenHandle
0x180027c8c  mov     [rsp+70h+PreviousState], rax; PreviousState
0x180027c91  call    cs:__imp_AdjustTokenPrivileges
0x180027c97  test    eax, eax
0x180027c99  jnz     short loc_180027CC2
0x180027c9b  call    cs:__imp_GetLastError
0x180027ca1  mov     ebx, eax
0x180027ca3  test    eax, eax
0x180027ca5  jz      short loc_180027CBB
0x180027ca7  jle     short loc_180027CB2
0x180027ca9  movzx   ebx, ax
0x180027cac  or      ebx, 80070000h
0x180027cb2  mov     ecx, ebx
0x180027cb4  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180027cb9  jmp     short loc_180027CD8
0x180027cbb  mov     ebx, 80004005h
0x180027cc0  jmp     short loc_180027CB2
0x180027cc2  xor     ebx, ebx
0x180027cc4  test    rdi, rdi
0x180027cc7  jz      short loc_180027CD8
0x180027cc9  cmp     [rbp+var_20.PrivilegeCount], ebx
0x180027ccc  mov     ecx, [rbp+var_20.Privileges.Attributes]
0x180027ccf  cmovz   ecx, [rbp+NewState.Privileges.Attributes]
0x180027cd3  and     ecx, 2
0x180027cd6  mov     [rdi], ecx
0x180027cd8  mov     ecx, ebx
0x180027cda  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180027cdf  mov     eax, ebx
0x180027ce1  mov     rcx, [rbp+var_10]
0x180027ce5  xor     rcx, rsp; StackCookie
0x180027ce8  call    __security_check_cookie
0x180027ced  mov     rbx, [rsp+70h+arg_10]
0x180027cf5  add     rsp, 70h
0x180027cf9  pop     rdi
0x180027cfa  pop     rsi
0x180027cfb  pop     rbp
0x180027cfc  retn
```
