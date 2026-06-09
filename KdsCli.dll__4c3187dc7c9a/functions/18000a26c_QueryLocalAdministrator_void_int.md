# QueryLocalAdministrator(void *,int *)

- ea: `0x18000a26c`
- end: `0x18000a37c`
- name: `?QueryLocalAdministrator@@YAJPEAXPEAH@Z`
- size: `272`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180009408`

## callees

- `0x180001630`
- `0x18000a26c`
- `0x18001a450`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a2e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a328`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a2e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a328`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18000a31e`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18000a31e`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18000a2d7`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18000a2d7`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000a355`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000a355`

## string_xrefs

- `0x18000a2fc`: `onecore\ds\security\keyman\sidkeyprov\kdscli\sidkeyldap.cxx`

## pseudocode

```c
__int64 __fastcall QueryLocalAdministrator(HANDLE TokenHandle, int *a2)
{
  signed int LastError; // eax
  unsigned int v5; // ebx
  unsigned int v6; // r9d
  signed int v7; // eax
  WINBOOL IsMember; // [rsp+60h] [rbp-20h] BYREF
  PSID SidToCheck; // [rsp+68h] [rbp-18h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+70h] [rbp-10h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *a2 = 0;
  IsMember = 0;
  SidToCheck = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &SidToCheck) )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    v6 = 124;
LABEL_5:
    SidKeyDebugTraceError(v5, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\sidkeyldap.cxx", v6);
    goto LABEL_11;
  }
  if ( !CheckTokenMembership(TokenHandle, SidToCheck, &IsMember) )
  {
    v7 = GetLastError();
    v5 = v7;
    if ( v7 > 0 )
      v5 = (unsigned __int16)v7 | 0x80070000;
    v6 = 135;
    goto LABEL_5;
  }
  *a2 = IsMember;
  v5 = 0;
LABEL_11:
  if ( SidToCheck )
    FreeSid(SidToCheck);
  return v5;
}

```

## disassembly

```asm
0x18000a26c  mov     [rsp-18h+arg_10], rbx
0x18000a271  push    rbp
0x18000a272  push    rsi
0x18000a273  push    rdi
0x18000a274  mov     rbp, rsp
0x18000a277  sub     rsp, 80h
0x18000a27e  mov     rax, cs:__security_cookie
0x18000a285  xor     rax, rsp
0x18000a288  mov     [rbp+var_8], rax
0x18000a28c  xor     esi, esi
0x18000a28e  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 500h
0x18000a294  lea     rax, [rbp+SidToCheck]
0x18000a298  mov     [rdx], esi
0x18000a29a  mov     [rsp+80h+pSid], rax; pSid
0x18000a29f  mov     rbx, rdx
0x18000a2a2  mov     [rsp+80h+nSubAuthority7], esi; nSubAuthority7
0x18000a2a6  mov     rdi, rcx
0x18000a2a9  mov     [rsp+80h+nSubAuthority6], esi; nSubAuthority6
0x18000a2ad  lea     r8d, [rsi+20h]; nSubAuthority0
0x18000a2b1  mov     [rsp+80h+nSubAuthority5], esi; nSubAuthority5
0x18000a2b5  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x18000a2b9  mov     [rsp+80h+nSubAuthority4], esi; nSubAuthority4
0x18000a2bd  mov     r9d, 220h; nSubAuthority1
0x18000a2c3  mov     [rsp+80h+nSubAuthority3], esi; nSubAuthority3
0x18000a2c7  mov     dl, 2; nSubAuthorityCount
0x18000a2c9  mov     [rsp+80h+nSubAuthority2], esi; nSubAuthority2
0x18000a2cd  mov     [rbp+IsMember], esi
0x18000a2d0  mov     [rbp+SidToCheck], rsi
0x18000a2d4  mov     dword ptr [rbp+pIdentifierAuthority.Value], esi
0x18000a2d7  call    cs:__imp_AllocateAndInitializeSid
0x18000a2dd  test    eax, eax
0x18000a2df  jnz     short loc_18000A313
0x18000a2e1  call    cs:__imp_GetLastError
0x18000a2e7  mov     ebx, eax
0x18000a2e9  test    eax, eax
0x18000a2eb  jle     short loc_18000A2F6
0x18000a2ed  movzx   ebx, ax
0x18000a2f0  or      ebx, 80070000h
0x18000a2f6  mov     r9d, 7Ch ; '|'; unsigned int
0x18000a2fc  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18000a303  mov     ecx, ebx; unsigned int
0x18000a305  lea     rdx, aHr; "hr"
0x18000a30c  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000a311  jmp     short loc_18000A34C
0x18000a313  mov     rdx, [rbp+SidToCheck]; SidToCheck
0x18000a317  lea     r8, [rbp+IsMember]; IsMember
0x18000a31b  mov     rcx, rdi; TokenHandle
0x18000a31e  call    cs:__imp_CheckTokenMembership
0x18000a324  test    eax, eax
0x18000a326  jnz     short loc_18000A345
0x18000a328  call    cs:__imp_GetLastError
0x18000a32e  mov     ebx, eax
0x18000a330  test    eax, eax
0x18000a332  jle     short loc_18000A33D
0x18000a334  movzx   ebx, ax
0x18000a337  or      ebx, 80070000h
0x18000a33d  mov     r9d, 87h
0x18000a343  jmp     short loc_18000A2FC
0x18000a345  mov     eax, [rbp+IsMember]
0x18000a348  mov     [rbx], eax
0x18000a34a  mov     ebx, esi
0x18000a34c  mov     rcx, [rbp+SidToCheck]; pSid
0x18000a350  test    rcx, rcx
0x18000a353  jz      short loc_18000A35B
0x18000a355  call    cs:__imp_FreeSid
0x18000a35b  mov     eax, ebx
0x18000a35d  mov     rcx, [rbp+var_8]
0x18000a361  xor     rcx, rsp; StackCookie
0x18000a364  call    __security_check_cookie
0x18000a369  mov     rbx, [rsp+80h+arg_10]
0x18000a371  add     rsp, 80h
0x18000a378  pop     rdi
0x18000a379  pop     rsi
0x18000a37a  pop     rbp
0x18000a37b  retn
```
