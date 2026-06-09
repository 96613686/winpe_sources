# BuildSecurityDescriptor(ulong,ulong)

- ea: `0x180113118`
- end: `0x180113584`
- name: `?BuildSecurityDescriptor@@YAPEAXKK@Z`
- size: `1132`
- prototype: `void *__fastcall(unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18011361c`

## callees

- `0x180072450`
- `0x1800cf8c0`
- `0x1800e5ab0`
- `0x180113118`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180113163`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801132bf`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180113472`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180113163`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801132bf`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180113472`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180113524`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18011353b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180113557`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180113524`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18011353b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180113557`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801131f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180113269`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180113341`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011339f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801133f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180113445`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801134df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801131f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180113269`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180113341`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011339f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801133f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180113445`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801134df`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18011329a`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1801132a6`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18011329a`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1801132a6`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1801131bc`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1801131bc`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1801134b1`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1801134b1`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180113410`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180113410`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180113234`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180113234`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18011345c`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18011345c`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18011336a`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1801133be`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18011336a`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1801133be`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18011350d`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18011350d`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18011330c`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18011330c`

## pseudocode

```c
__int64 __fastcall BuildSecurityDescriptor()
{
  unsigned __int64 v0; // rsi
  struct _ACL *v1; // rbx
  char v2; // r15
  void *v3; // rax
  void *v4; // rdi
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  DWORD LastError; // eax
  __int64 v8; // rdx
  DWORD v9; // eax
  __int64 v10; // rdx
  DWORD LengthSid; // ebx
  SIZE_T v12; // r14
  struct _ACL *v13; // rax
  void *v14; // rax
  DWORD dwBufferLength; // [rsp+60h] [rbp-20h] BYREF
  PSID pSid; // [rsp+68h] [rbp-18h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+70h] [rbp-10h] BYREF

  pSid = 0;
  v0 = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  v1 = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 256;
  v2 = 0;
  v3 = HeapAlloc(g_hHeap, 0, 0x28u);
  v4 = v3;
  if ( !v3 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v6 = 10;
LABEL_6:
      WPP_SF_(v5[2], v6, &WPP_62e65b1aa5e43d79debbf88575ed7e0c_Traceguids);
      goto LABEL_55;
    }
    goto LABEL_55;
  }
  if ( !InitializeSecurityDescriptor(v3, 1u) )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      goto LABEL_55;
    }
    LastError = GetLastError();
    v8 = 11;
    goto LABEL_54;
  }
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0, 0, 0, 0, 0, 0, 0, 0, &pSid) )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      goto LABEL_55;
    }
    v9 = GetLastError();
    v10 = 12;
    goto LABEL_17;
  }
  LengthSid = GetLengthSid(AudiosrvSid);
  v12 = LengthSid + GetLengthSid(pSid) + 24;
  v13 = (struct _ACL *)HeapAlloc(g_hHeap, 0, v12);
  v1 = v13;
  if ( !v13 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v6 = 13;
      goto LABEL_6;
    }
    goto LABEL_55;
  }
  if ( !InitializeAcl(v13, v12, 2u) )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      goto LABEL_55;
    }
    v9 = GetLastError();
    v10 = 14;
LABEL_17:
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, &WPP_62e65b1aa5e43d79debbf88575ed7e0c_Traceguids, v9);
    goto LABEL_55;
  }
  if ( !AddAccessAllowedAce(v1, 2u, 0xF001Fu, AudiosrvSid) )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      goto LABEL_55;
    }
    LastError = GetLastError();
    v8 = 15;
    goto LABEL_54;
  }
  if ( !AddAccessAllowedAce(v1, 2u, 4u, pSid) )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      goto LABEL_55;
    }
    LastError = GetLastError();
    v8 = 16;
    goto LABEL_54;
  }
  if ( !SetSecurityDescriptorDacl(v4, 1, v1, 0) )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      goto LABEL_55;
    }
    LastError = GetLastError();
    v8 = 17;
LABEL_54:
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, &WPP_62e65b1aa5e43d79debbf88575ed7e0c_Traceguids, LastError);
    goto LABEL_55;
  }
  dwBufferLength = GetSecurityDescriptorLength(v4);
  v14 = HeapAlloc(g_hHeap, 0, dwBufferLength);
  v0 = (unsigned __int64)v14;
  if ( !v14 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v6 = 18;
      goto LABEL_6;
    }
    goto LABEL_55;
  }
  if ( MakeSelfRelativeSD(v4, v14, &dwBufferLength) )
  {
    v2 = 1;
    goto LABEL_55;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    LastError = GetLastError();
    v8 = 19;
    goto LABEL_54;
  }
LABEL_55:
  if ( pSid )
    FreeSid(pSid);
  if ( v1 )
    HeapFree(g_hHeap, 0, v1);
  if ( v4 )
    HeapFree(g_hHeap, 0, v4);
  if ( !v2 && v0 )
    HeapFree(g_hHeap, 0, (LPVOID)v0);
  return v0 & -(__int64)(v2 != 0);
}

```

## disassembly

```asm
0x180113118  push    rbp
0x18011311a  push    rbx
0x18011311b  push    rsi
0x18011311c  push    rdi
0x18011311d  push    r12
0x18011311f  push    r14
0x180113121  push    r15
0x180113123  mov     rbp, rsp
0x180113126  sub     rsp, 80h
0x18011312d  mov     rax, cs:__security_cookie
0x180113134  xor     rax, rsp
0x180113137  mov     [rbp+var_8], rax
0x18011313b  mov     rcx, cs:g_hHeap; hHeap
0x180113142  xor     r12d, r12d
0x180113145  xor     edx, edx; dwFlags
0x180113147  mov     [rbp+var_18], r12
0x18011314b  mov     esi, r12d
0x18011314e  mov     dword ptr [rbp+pIdentifierAuthority.Value], r12d
0x180113152  mov     ebx, r12d
0x180113155  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 100h
0x18011315b  lea     r8d, [r12+28h]; dwBytes
0x180113160  mov     r15b, r12b
0x180113163  call    cs:__imp_HeapAlloc
0x180113169  mov     rdi, rax
0x18011316c  test    rax, rax
0x18011316f  jnz     short loc_1801131B4
0x180113171  mov     rcx, cs:WPP_GLOBAL_Control
0x180113178  lea     rax, WPP_GLOBAL_Control
0x18011317f  cmp     rcx, rax
0x180113182  jz      loc_180113504
0x180113188  test    byte ptr [rcx+1Ch], 10h
0x18011318c  jz      loc_180113504
0x180113192  cmp     byte ptr [rcx+19h], 4
0x180113196  jb      loc_180113504
0x18011319c  lea     edx, [rdi+0Ah]
0x18011319f  mov     rcx, [rcx+10h]
0x1801131a3  lea     r8, WPP_62e65b1aa5e43d79debbf88575ed7e0c_Traceguids
0x1801131aa  call    WPP_SF_
0x1801131af  jmp     loc_180113504
0x1801131b4  mov     edx, 1; dwRevision
0x1801131b9  mov     rcx, rdi; pSecurityDescriptor
0x1801131bc  call    cs:__imp_InitializeSecurityDescriptor
0x1801131c2  test    eax, eax
0x1801131c4  jnz     short loc_180113201
0x1801131c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1801131cd  lea     rax, WPP_GLOBAL_Control
0x1801131d4  cmp     rcx, rax
0x1801131d7  jz      loc_180113504
0x1801131dd  test    byte ptr [rcx+1Ch], 10h
0x1801131e1  jz      loc_180113504
0x1801131e7  cmp     byte ptr [rcx+19h], 4
0x1801131eb  jb      loc_180113504
0x1801131f1  call    cs:__imp_GetLastError
0x1801131f7  mov     edx, 0Bh
0x1801131fc  jmp     loc_1801134EA
0x180113201  lea     rax, [rbp+var_18]
0x180113205  xor     r9d, r9d; nSubAuthority1
0x180113208  mov     [rsp+80h+pSid], rax; pSid
0x18011320d  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x180113211  mov     [rsp+80h+nSubAuthority7], r12d; nSubAuthority7
0x180113216  xor     r8d, r8d; nSubAuthority0
0x180113219  mov     [rsp+80h+nSubAuthority6], r12d; nSubAuthority6
0x18011321e  mov     dl, 1; nSubAuthorityCount
0x180113220  mov     [rsp+80h+nSubAuthority5], r12d; nSubAuthority5
0x180113225  mov     [rsp+80h+nSubAuthority4], r12d; nSubAuthority4
0x18011322a  mov     [rsp+80h+nSubAuthority3], r12d; nSubAuthority3
0x18011322f  mov     [rsp+80h+nSubAuthority2], r12d; nSubAuthority2
0x180113234  call    cs:__imp_AllocateAndInitializeSid
0x18011323a  test    eax, eax
0x18011323c  jnz     short loc_180113293
0x18011323e  mov     rcx, cs:WPP_GLOBAL_Control
0x180113245  lea     rax, WPP_GLOBAL_Control
0x18011324c  cmp     rcx, rax
0x18011324f  jz      loc_180113504
0x180113255  test    byte ptr [rcx+1Ch], 10h
0x180113259  jz      loc_180113504
0x18011325f  cmp     byte ptr [rcx+19h], 4
0x180113263  jb      loc_180113504
0x180113269  call    cs:__imp_GetLastError
0x18011326f  mov     edx, 0Ch
0x180113274  mov     rcx, cs:WPP_GLOBAL_Control
0x18011327b  lea     r8, WPP_62e65b1aa5e43d79debbf88575ed7e0c_Traceguids
0x180113282  mov     r9d, eax
0x180113285  mov     rcx, [rcx+10h]
0x180113289  call    WPP_SF_d
0x18011328e  jmp     loc_180113504
0x180113293  mov     rcx, cs:?AudiosrvSid@@3PEAXEA; pSid
0x18011329a  call    cs:__imp_GetLengthSid
0x1801132a0  mov     rcx, [rbp+var_18]; pSid
0x1801132a4  mov     ebx, eax
0x1801132a6  call    cs:__imp_GetLengthSid
0x1801132ac  mov     rcx, cs:g_hHeap; hHeap
0x1801132b3  xor     edx, edx; dwFlags
0x1801132b5  lea     r14d, [rax+18h]
0x1801132b9  add     r14d, ebx
0x1801132bc  mov     r8d, r14d; dwBytes
0x1801132bf  call    cs:__imp_HeapAlloc
0x1801132c5  mov     rbx, rax
0x1801132c8  test    rax, rax
0x1801132cb  jnz     short loc_180113300
0x1801132cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1801132d4  lea     rax, WPP_GLOBAL_Control
0x1801132db  cmp     rcx, rax
0x1801132de  jz      loc_180113504
0x1801132e4  test    byte ptr [rcx+1Ch], 10h
0x1801132e8  jz      loc_180113504
0x1801132ee  cmp     byte ptr [rcx+19h], 4
0x1801132f2  jb      loc_180113504
0x1801132f8  lea     edx, [rbx+0Dh]
0x1801132fb  jmp     loc_18011319F
0x180113300  mov     r8d, 2; dwAclRevision
0x180113306  mov     edx, r14d; nAclLength
0x180113309  mov     rcx, rbx; pAcl
0x18011330c  call    cs:__imp_InitializeAcl
0x180113312  test    eax, eax
0x180113314  jnz     short loc_180113351
0x180113316  mov     rcx, cs:WPP_GLOBAL_Control
0x18011331d  lea     rax, WPP_GLOBAL_Control
0x180113324  cmp     rcx, rax
0x180113327  jz      loc_180113504
0x18011332d  test    byte ptr [rcx+1Ch], 10h
0x180113331  jz      loc_180113504
0x180113337  cmp     byte ptr [rcx+19h], 4
0x18011333b  jb      loc_180113504
0x180113341  call    cs:__imp_GetLastError
0x180113347  mov     edx, 0Eh
0x18011334c  jmp     loc_180113274
0x180113351  mov     r9, cs:?AudiosrvSid@@3PEAXEA; pSid
0x180113358  mov     r14d, 2
0x18011335e  mov     edx, r14d; dwAceRevision
0x180113361  mov     r8d, 0F001Fh; AccessMask
0x180113367  mov     rcx, rbx; pAcl
0x18011336a  call    cs:__imp_AddAccessAllowedAce
0x180113370  test    eax, eax
0x180113372  jnz     short loc_1801133AE
0x180113374  mov     rcx, cs:WPP_GLOBAL_Control
0x18011337b  lea     rax, WPP_GLOBAL_Control
0x180113382  cmp     rcx, rax
0x180113385  jz      loc_180113504
0x18011338b  test    byte ptr [rcx+1Ch], 10h
0x18011338f  jz      loc_180113504
0x180113395  cmp     byte ptr [rcx+19h], 4
0x180113399  jb      loc_180113504
0x18011339f  call    cs:__imp_GetLastError
0x1801133a5  lea     edx, [r14+0Dh]
0x1801133a9  jmp     loc_1801134EA
0x1801133ae  mov     r9, [rbp+var_18]; pSid
0x1801133b2  mov     r8d, 4; AccessMask
0x1801133b8  mov     edx, r14d; dwAceRevision
0x1801133bb  mov     rcx, rbx; pAcl
0x1801133be  call    cs:__imp_AddAccessAllowedAce
0x1801133c4  test    eax, eax
0x1801133c6  jnz     short loc_180113403
0x1801133c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1801133cf  lea     rax, WPP_GLOBAL_Control
0x1801133d6  cmp     rcx, rax
0x1801133d9  jz      loc_180113504
0x1801133df  test    byte ptr [rcx+1Ch], 10h
0x1801133e3  jz      loc_180113504
0x1801133e9  cmp     byte ptr [rcx+19h], 4
0x1801133ed  jb      loc_180113504
0x1801133f3  call    cs:__imp_GetLastError
0x1801133f9  mov     edx, 10h
0x1801133fe  jmp     loc_1801134EA
0x180113403  xor     r9d, r9d; bDaclDefaulted
0x180113406  mov     r8, rbx; pDacl
0x180113409  mov     rcx, rdi; pSecurityDescriptor
0x18011340c  lea     edx, [r9+1]; bDaclPresent
0x180113410  call    cs:__imp_SetSecurityDescriptorDacl
0x180113416  test    eax, eax
0x180113418  jnz     short loc_180113455
0x18011341a  mov     rcx, cs:WPP_GLOBAL_Control
0x180113421  lea     rax, WPP_GLOBAL_Control
0x180113428  cmp     rcx, rax
0x18011342b  jz      loc_180113504
0x180113431  test    byte ptr [rcx+1Ch], 10h
0x180113435  jz      loc_180113504
0x18011343b  cmp     byte ptr [rcx+19h], 4
0x18011343f  jb      loc_180113504
0x180113445  call    cs:__imp_GetLastError
0x18011344b  mov     edx, 11h
0x180113450  jmp     loc_1801134EA
0x180113455  mov     rcx, rdi; pSecurityDescriptor
0x180113458  mov     [rbp+dwBufferLength], r12d
0x18011345c  call    cs:__imp_GetSecurityDescriptorLength
0x180113462  mov     rcx, cs:g_hHeap; hHeap
0x180113469  xor     edx, edx; dwFlags
0x18011346b  mov     r8d, eax; dwBytes
0x18011346e  mov     [rbp+dwBufferLength], r8d
0x180113472  call    cs:__imp_HeapAlloc
0x180113478  mov     rsi, rax
0x18011347b  test    rax, rax
0x18011347e  jnz     short loc_1801134A7
0x180113480  mov     rcx, cs:WPP_GLOBAL_Control
0x180113487  lea     rax, WPP_GLOBAL_Control
0x18011348e  cmp     rcx, rax
0x180113491  jz      short loc_180113504
0x180113493  test    byte ptr [rcx+1Ch], 10h
0x180113497  jz      short loc_180113504
0x180113499  cmp     byte ptr [rcx+19h], 4
0x18011349d  jb      short loc_180113504
0x18011349f  lea     edx, [rsi+12h]
0x1801134a2  jmp     loc_18011319F
0x1801134a7  lea     r8, [rbp+dwBufferLength]; lpdwBufferLength
0x1801134ab  mov     rdx, rax; pSelfRelativeSecurityDescriptor
0x1801134ae  mov     rcx, rdi; pAbsoluteSecurityDescriptor
0x1801134b1  call    cs:__imp_MakeSelfRelativeSD
0x1801134b7  test    eax, eax
0x1801134b9  jz      short loc_1801134C0
0x1801134bb  mov     r15b, 1
0x1801134be  jmp     short loc_180113504
0x1801134c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1801134c7  lea     rax, WPP_GLOBAL_Control
0x1801134ce  cmp     rcx, rax
0x1801134d1  jz      short loc_180113504
0x1801134d3  test    byte ptr [rcx+1Ch], 10h
0x1801134d7  jz      short loc_180113504
0x1801134d9  cmp     byte ptr [rcx+19h], 4
0x1801134dd  jb      short loc_180113504
0x1801134df  call    cs:__imp_GetLastError
0x1801134e5  mov     edx, 13h
0x1801134ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1801134f1  lea     r8, WPP_62e65b1aa5e43d79debbf88575ed7e0c_Traceguids
0x1801134f8  mov     r9d, eax
0x1801134fb  mov     rcx, [rcx+10h]
0x1801134ff  call    WPP_SF_d
0x180113504  mov     rcx, [rbp+var_18]; pSid
0x180113508  test    rcx, rcx
0x18011350b  jz      short loc_180113513
0x18011350d  call    cs:__imp_FreeSid
0x180113513  test    rbx, rbx
0x180113516  jz      short loc_18011352A
0x180113518  mov     rcx, cs:g_hHeap; hHeap
0x18011351f  mov     r8, rbx; lpMem
0x180113522  xor     edx, edx; dwFlags
0x180113524  call    cs:__imp_HeapFree
0x18011352a  test    rdi, rdi
0x18011352d  jz      short loc_180113541
0x18011352f  mov     rcx, cs:g_hHeap; hHeap
0x180113536  mov     r8, rdi; lpMem
0x180113539  xor     edx, edx; dwFlags
0x18011353b  call    cs:__imp_HeapFree
0x180113541  test    r15b, r15b
0x180113544  jnz     short loc_18011355D
0x180113546  test    rsi, rsi
0x180113549  jz      short loc_18011355D
0x18011354b  mov     rcx, cs:g_hHeap; hHeap
0x180113552  mov     r8, rsi; lpMem
0x180113555  xor     edx, edx; dwFlags
0x180113557  call    cs:__imp_HeapFree
0x18011355d  neg     r15b
0x180113560  sbb     rax, rax
0x180113563  and     rax, rsi
0x180113566  mov     rcx, [rbp+var_8]
0x18011356a  xor     rcx, rsp; StackCookie
0x18011356d  call    __security_check_cookie
0x180113572  add     rsp, 80h
0x180113579  pop     r15
0x18011357b  pop     r14
0x18011357d  pop     r12
0x18011357f  pop     rdi
0x180113580  pop     rsi
0x180113581  pop     rbx
0x180113582  pop     rbp
0x180113583  retn
```
