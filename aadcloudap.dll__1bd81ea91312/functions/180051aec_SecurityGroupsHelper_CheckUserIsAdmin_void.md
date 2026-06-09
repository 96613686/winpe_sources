# SecurityGroupsHelper::CheckUserIsAdmin(void *)

- ea: `0x180051aec`
- end: `0x180051cee`
- name: `?CheckUserIsAdmin@SecurityGroupsHelper@@SAJPEAX@Z`
- size: `514`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180049394`

## callees

- `0x180003c20`
- `0x1800069c0`
- `0x180006ac4`
- `0x180051aec`
- `0x180071e14`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051bba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051bc4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051bcc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051c1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051c25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051c2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051bba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051bc4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051bcc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051c1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051c25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051c2d`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180051bb0`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180051bb0`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180051cb6`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180051cb6`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180051c11`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180051c11`

## string_xrefs

- `0x180051b30`: `SecurityGroupsHelper::CheckUserIsAdmin`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SecurityGroupsHelper::CheckUserIsAdmin(HANDLE TokenHandle)
{
  signed int LastError; // eax
  unsigned int v3; // ebx
  __int64 nSubAuthority2; // [rsp+20h] [rbp-49h]
  __int64 nSubAuthority4; // [rsp+30h] [rbp-39h]
  signed int v7; // [rsp+60h] [rbp-9h] BYREF
  WINBOOL IsMember; // [rsp+64h] [rbp-5h] BYREF
  PSID SidToCheck; // [rsp+68h] [rbp-1h] BYREF
  _BYTE v10[48]; // [rsp+70h] [rbp+7h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+A0h] [rbp+37h] BYREF

  v7 = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  SidToCheck = 0;
  IsMember = 0;
  DbgTracePrintHelper<unsigned long>::DbgTracePrintHelper<unsigned long>(
    v10,
    "securitygroupshelper.cpp",
    "SecurityGroupsHelper::CheckUserIsAdmin",
    &v7);
  if ( !TokenHandle )
  {
    LastError = -1073741811;
    LODWORD(nSubAuthority4) = 80;
LABEL_17:
    v7 = LastError;
    goto LABEL_18;
  }
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &SidToCheck)
    || ((int)GetLastError() > 0
      ? (LastError = (unsigned __int16)GetLastError() | 0xC0070000)
      : (LastError = GetLastError()),
        v7 = LastError,
        LastError >= 0) )
  {
    if ( CheckTokenMembership(TokenHandle, SidToCheck, &IsMember)
      || ((int)GetLastError() > 0
        ? (LastError = (unsigned __int16)GetLastError() | 0xC0070000)
        : (LastError = GetLastError()),
          v7 = LastError,
          LastError >= 0) )
    {
      if ( IsMember )
        goto LABEL_19;
      LastError = -1073741790;
      LODWORD(nSubAuthority4) = 99;
      goto LABEL_17;
    }
    LODWORD(nSubAuthority4) = 94;
  }
  else
  {
    LODWORD(nSubAuthority4) = 89;
  }
LABEL_18:
  LODWORD(nSubAuthority2) = LastError;
  WPPTraceLogA(
    2,
    0,
    "%x 0x%08x %s:%u : %s:%ws",
    2,
    nSubAuthority2,
    "securitygroupshelper.cpp",
    nSubAuthority4,
    "NTSTATUS",
    &base);
LABEL_19:
  if ( SidToCheck )
    FreeSid(SidToCheck);
  v3 = v7;
  DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(v10);
  return v3;
}

```

## disassembly

```asm
0x180051aec  mov     [rsp-8+arg_8], rbx
0x180051af1  mov     [rsp-8+arg_10], rsi
0x180051af6  push    rbp
0x180051af7  push    rdi
0x180051af8  push    r14
0x180051afa  lea     rbp, [rsp-47h]
0x180051aff  sub     rsp, 0B0h
0x180051b06  mov     rax, cs:__security_cookie
0x180051b0d  xor     rax, rsp
0x180051b10  mov     [rbp+57h+var_18], rax
0x180051b14  mov     rdi, rcx
0x180051b17  xor     esi, esi
0x180051b19  mov     [rbp+57h+var_60], esi
0x180051b1c  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], esi
0x180051b1f  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x180051b25  mov     [rbp+57h+SidToCheck], rsi
0x180051b29  mov     [rbp+57h+IsMember], esi
0x180051b2c  lea     r9, [rbp+57h+var_60]
0x180051b30  lea     r8, aSecuritygroups_3; "SecurityGroupsHelper::CheckUserIsAdmin"
0x180051b37  lea     r14, aOnecoreuapDsEx_37+21h; "securitygroupshelper.cpp"
0x180051b3e  mov     rdx, r14
0x180051b41  lea     rcx, [rbp+57h+var_50]
0x180051b45  call    ??0?$DbgTracePrintHelper@K@@QEAA@PEBD0AEAKW4AadTracingEventType@@@Z; DbgTracePrintHelper<ulong>::DbgTracePrintHelper<ulong>(char const *,char const *,ulong &,AadTracingEventType)
0x180051b4a  nop
0x180051b4b  lea     ebx, [rsi+2]
0x180051b4e  test    rdi, rdi
0x180051b51  jnz     short loc_180051B7D
0x180051b53  mov     eax, 0C000000Dh
0x180051b58  lea     rcx, base
0x180051b5f  mov     qword ptr [rsp+0C0h+nSubAuthority6], rcx
0x180051b64  lea     rcx, aNtstatus; "NTSTATUS"
0x180051b6b  mov     qword ptr [rsp+0C0h+nSubAuthority5], rcx
0x180051b70  mov     dword ptr [rsp+0C0h+nSubAuthority4], 50h ; 'P'
0x180051b78  jmp     loc_180051C8E
0x180051b7d  lea     rax, [rbp+57h+SidToCheck]
0x180051b81  mov     [rsp+0C0h+pSid], rax; pSid
0x180051b86  mov     [rsp+0C0h+nSubAuthority7], esi; nSubAuthority7
0x180051b8a  mov     [rsp+0C0h+nSubAuthority6], esi; nSubAuthority6
0x180051b8e  mov     [rsp+0C0h+nSubAuthority5], esi; nSubAuthority5
0x180051b92  mov     dword ptr [rsp+0C0h+nSubAuthority4], esi; nSubAuthority4
0x180051b96  mov     [rsp+0C0h+nSubAuthority3], esi; nSubAuthority3
0x180051b9a  mov     dword ptr [rsp+0C0h+nSubAuthority2], esi; nSubAuthority2
0x180051b9e  mov     r9d, 220h; nSubAuthority1
0x180051ba4  mov     r8d, 20h ; ' '; nSubAuthority0
0x180051baa  mov     dl, bl; nSubAuthorityCount
0x180051bac  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x180051bb0  call    cs:__imp_AllocateAndInitializeSid
0x180051bb6  test    eax, eax
0x180051bb8  jnz     short loc_180051C06
0x180051bba  call    cs:__imp_GetLastError
0x180051bc0  test    eax, eax
0x180051bc2  jg      short loc_180051BCC
0x180051bc4  call    cs:__imp_GetLastError
0x180051bca  jmp     short loc_180051BDA
0x180051bcc  call    cs:__imp_GetLastError
0x180051bd2  movzx   eax, ax
0x180051bd5  or      eax, 0C0070000h
0x180051bda  mov     [rbp+57h+var_60], eax
0x180051bdd  test    eax, eax
0x180051bdf  jns     short loc_180051C06
0x180051be1  lea     rcx, base
0x180051be8  mov     qword ptr [rsp+0C0h+nSubAuthority6], rcx
0x180051bed  lea     rcx, aNtstatus; "NTSTATUS"
0x180051bf4  mov     qword ptr [rsp+0C0h+nSubAuthority5], rcx
0x180051bf9  mov     dword ptr [rsp+0C0h+nSubAuthority4], 59h ; 'Y'
0x180051c01  jmp     loc_180051C91
0x180051c06  lea     r8, [rbp+57h+IsMember]; IsMember
0x180051c0a  mov     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x180051c0e  mov     rcx, rdi; TokenHandle
0x180051c11  call    cs:__imp_CheckTokenMembership
0x180051c17  test    eax, eax
0x180051c19  jnz     short loc_180051C64
0x180051c1b  call    cs:__imp_GetLastError
0x180051c21  test    eax, eax
0x180051c23  jg      short loc_180051C2D
0x180051c25  call    cs:__imp_GetLastError
0x180051c2b  jmp     short loc_180051C3B
0x180051c2d  call    cs:__imp_GetLastError
0x180051c33  movzx   eax, ax
0x180051c36  or      eax, 0C0070000h
0x180051c3b  mov     [rbp+57h+var_60], eax
0x180051c3e  test    eax, eax
0x180051c40  jns     short loc_180051C64
0x180051c42  lea     rcx, base
0x180051c49  mov     qword ptr [rsp+0C0h+nSubAuthority6], rcx
0x180051c4e  lea     rcx, aNtstatus; "NTSTATUS"
0x180051c55  mov     qword ptr [rsp+0C0h+nSubAuthority5], rcx
0x180051c5a  mov     dword ptr [rsp+0C0h+nSubAuthority4], 5Eh ; '^'
0x180051c62  jmp     short loc_180051C91
0x180051c64  cmp     [rbp+57h+IsMember], esi
0x180051c67  jnz     short loc_180051CAD
0x180051c69  mov     eax, 0C0000022h
0x180051c6e  lea     rcx, base
0x180051c75  mov     qword ptr [rsp+0C0h+nSubAuthority6], rcx
0x180051c7a  lea     rcx, aNtstatus; "NTSTATUS"
0x180051c81  mov     qword ptr [rsp+0C0h+nSubAuthority5], rcx
0x180051c86  mov     dword ptr [rsp+0C0h+nSubAuthority4], 63h ; 'c'
0x180051c8e  mov     [rbp+57h+var_60], eax
0x180051c91  mov     qword ptr [rsp+0C0h+nSubAuthority3], r14
0x180051c96  mov     dword ptr [rsp+0C0h+nSubAuthority2], eax
0x180051c9a  mov     r9d, ebx
0x180051c9d  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x180051ca4  xor     edx, edx
0x180051ca6  mov     ecx, ebx
0x180051ca8  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x180051cad  mov     rcx, [rbp+57h+SidToCheck]; pSid
0x180051cb1  test    rcx, rcx
0x180051cb4  jz      short loc_180051CBC
0x180051cb6  call    cs:__imp_FreeSid
0x180051cbc  mov     ebx, [rbp+57h+var_60]
0x180051cbf  lea     rcx, [rbp+57h+var_50]
0x180051cc3  call    ??1?$DbgTracePrintHelper@J@@QEAA@XZ; DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(void)
0x180051cc8  mov     eax, ebx
0x180051cca  mov     rcx, [rbp+57h+var_18]
0x180051cce  xor     rcx, rsp; StackCookie
0x180051cd1  call    __security_check_cookie
0x180051cd6  lea     r11, [rsp+0C0h+var_10]
0x180051cde  mov     rbx, [r11+28h]
0x180051ce2  mov     rsi, [r11+30h]
0x180051ce6  mov     rsp, r11
0x180051ce9  pop     r14
0x180051ceb  pop     rdi
0x180051cec  pop     rbp
0x180051ced  retn
```
