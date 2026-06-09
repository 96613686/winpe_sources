# SimpleCheckMembership(ulong,int *)

- ea: `0x1800180c0`
- end: `0x1800181e2`
- name: `?SimpleCheckMembership@@YAKKPEAH@Z`
- size: `290`
- prototype: `__int64 __fastcall(DWORD nSubAuthority0, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000caa0`

## callees

- `0x1800180c0`
- `0x180018218`
- `0x18001a380`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018138`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018183`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018138`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018183`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001812e`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001812e`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800181bb`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800181bb`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180018179`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180018179`

## pseudocode

```c
__int64 __fastcall SimpleCheckMembership(DWORD nSubAuthority0, int *a2)
{
  DWORD LastError; // ebx
  __int64 v4; // r8
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  WINBOOL IsMember; // [rsp+60h] [rbp-20h] BYREF
  PSID SidToCheck; // [rsp+68h] [rbp-18h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+70h] [rbp-10h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  SidToCheck = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  if ( !a2 )
    return 87;
  *a2 = 0;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, nSubAuthority0, 0, 0, 0, 0, 0, 0, 0, &SidToCheck) )
  {
    IsMember = 0;
    if ( CheckTokenMembership(0, SidToCheck, &IsMember) )
    {
      LastError = 0;
      *a2 = IsMember;
    }
    else
    {
      LastError = GetLastError();
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v6 = 16;
        goto LABEL_7;
      }
    }
  }
  else
  {
    LastError = GetLastError();
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v6 = 15;
LABEL_7:
      WPP_SF_D(v5[2], v6, v4, LastError);
    }
  }
  if ( SidToCheck )
    FreeSid(SidToCheck);
  return LastError;
}

```

## disassembly

```asm
0x1800180c0  mov     [rsp-18h+arg_10], rbx
0x1800180c5  push    rbp
0x1800180c6  push    rsi
0x1800180c7  push    rdi
0x1800180c8  mov     rbp, rsp
0x1800180cb  sub     rsp, 80h
0x1800180d2  mov     rax, cs:__security_cookie
0x1800180d9  xor     rax, rsp
0x1800180dc  mov     [rbp+var_8], rax
0x1800180e0  xor     esi, esi
0x1800180e2  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 500h
0x1800180e8  mov     [rbp+SidToCheck], rsi
0x1800180ec  mov     rdi, rdx
0x1800180ef  mov     dword ptr [rbp+pIdentifierAuthority.Value], esi
0x1800180f2  test    rdx, rdx
0x1800180f5  jnz     short loc_1800180FF
0x1800180f7  lea     ebx, [rdx+57h]
0x1800180fa  jmp     loc_1800181C1
0x1800180ff  lea     rax, [rbp+SidToCheck]
0x180018103  mov     [rdx], esi
0x180018105  mov     [rsp+80h+pSid], rax; pSid
0x18001810a  mov     r8d, ecx; nSubAuthority0
0x18001810d  mov     [rsp+80h+nSubAuthority7], esi; nSubAuthority7
0x180018111  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x180018115  mov     [rsp+80h+nSubAuthority6], esi; nSubAuthority6
0x180018119  xor     r9d, r9d; nSubAuthority1
0x18001811c  mov     [rsp+80h+nSubAuthority5], esi; nSubAuthority5
0x180018120  mov     dl, 1; nSubAuthorityCount
0x180018122  mov     [rsp+80h+nSubAuthority4], esi; nSubAuthority4
0x180018126  mov     [rsp+80h+nSubAuthority3], esi; nSubAuthority3
0x18001812a  mov     [rsp+80h+nSubAuthority2], esi; nSubAuthority2
0x18001812e  call    cs:__imp_AllocateAndInitializeSid
0x180018134  test    eax, eax
0x180018136  jnz     short loc_18001816C
0x180018138  call    cs:__imp_GetLastError
0x18001813e  mov     ebx, eax
0x180018140  mov     rcx, cs:WPP_GLOBAL_Control
0x180018147  lea     rax, WPP_GLOBAL_Control
0x18001814e  cmp     rcx, rax
0x180018151  jz      short loc_1800181B2
0x180018153  test    byte ptr [rcx+1Ch], 4
0x180018157  jz      short loc_1800181B2
0x180018159  mov     edx, 0Fh
0x18001815e  mov     rcx, [rcx+10h]
0x180018162  mov     r9d, ebx
0x180018165  call    WPP_SF_D
0x18001816a  jmp     short loc_1800181B2
0x18001816c  mov     rdx, [rbp+SidToCheck]; SidToCheck
0x180018170  lea     r8, [rbp+IsMember]; IsMember
0x180018174  xor     ecx, ecx; TokenHandle
0x180018176  mov     [rbp+IsMember], esi
0x180018179  call    cs:__imp_CheckTokenMembership
0x18001817f  test    eax, eax
0x180018181  jnz     short loc_1800181AB
0x180018183  call    cs:__imp_GetLastError
0x180018189  mov     ebx, eax
0x18001818b  mov     rcx, cs:WPP_GLOBAL_Control
0x180018192  lea     rax, WPP_GLOBAL_Control
0x180018199  cmp     rcx, rax
0x18001819c  jz      short loc_1800181B2
0x18001819e  test    byte ptr [rcx+1Ch], 4
0x1800181a2  jz      short loc_1800181B2
0x1800181a4  mov     edx, 10h
0x1800181a9  jmp     short loc_18001815E
0x1800181ab  mov     eax, [rbp+IsMember]
0x1800181ae  mov     ebx, esi
0x1800181b0  mov     [rdi], eax
0x1800181b2  mov     rcx, [rbp+SidToCheck]; pSid
0x1800181b6  test    rcx, rcx
0x1800181b9  jz      short loc_1800181C1
0x1800181bb  call    cs:__imp_FreeSid
0x1800181c1  mov     eax, ebx
0x1800181c3  mov     rcx, [rbp+var_8]
0x1800181c7  xor     rcx, rsp; StackCookie
0x1800181ca  call    __security_check_cookie
0x1800181cf  mov     rbx, [rsp+80h+arg_10]
0x1800181d7  add     rsp, 80h
0x1800181de  pop     rdi
0x1800181df  pop     rsi
0x1800181e0  pop     rbp
0x1800181e1  retn
```
