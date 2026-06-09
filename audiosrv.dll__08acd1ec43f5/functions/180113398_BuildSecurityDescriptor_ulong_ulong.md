# BuildSecurityDescriptor(ulong,ulong)

- ea: `0x180113398`
- end: `0x180113804`
- name: `?BuildSecurityDescriptor@@YAPEAXKK@Z`
- size: `1132`
- prototype: `void *__fastcall(unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18011389c`

## callees

- `0x180071f50`
- `0x1800cd8d0`
- `0x1800e5330`
- `0x180113398`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801133e3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18011353f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801136f2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801133e3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18011353f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801136f2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801137a4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801137bb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801137d7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801137a4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801137bb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801137d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180113471`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801134e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801135c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011361f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180113673`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801136c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011375f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180113471`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801134e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801135c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011361f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180113673`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801136c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011375f`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18011351a`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180113526`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18011351a`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180113526`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18011343c`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18011343c`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180113731`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180113731`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180113690`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180113690`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1801134b4`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1801134b4`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1801135ea`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18011363e`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1801135ea`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18011363e`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18011378d`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18011378d`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1801136dc`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1801136dc`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18011358c`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18011358c`

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
      WPP_SF_(v5[2], v6, WPP_62e65b1aa5e43d79debbf88575ed7e0c_Traceguids);
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
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, WPP_62e65b1aa5e43d79debbf88575ed7e0c_Traceguids, v9);
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
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, WPP_62e65b1aa5e43d79debbf88575ed7e0c_Traceguids, LastError);
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
0x180113398  push    rbp
0x18011339a  push    rbx
0x18011339b  push    rsi
0x18011339c  push    rdi
0x18011339d  push    r12
0x18011339f  push    r14
0x1801133a1  push    r15
0x1801133a3  mov     rbp, rsp
0x1801133a6  sub     rsp, 80h
0x1801133ad  mov     rax, cs:__security_cookie
0x1801133b4  xor     rax, rsp
0x1801133b7  mov     [rbp+var_8], rax
0x1801133bb  mov     rcx, cs:g_hHeap; hHeap
0x1801133c2  xor     r12d, r12d
0x1801133c5  xor     edx, edx; dwFlags
0x1801133c7  mov     [rbp+var_18], r12
0x1801133cb  mov     esi, r12d
0x1801133ce  mov     dword ptr [rbp+pIdentifierAuthority.Value], r12d
0x1801133d2  mov     ebx, r12d
0x1801133d5  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 100h
0x1801133db  lea     r8d, [r12+28h]; dwBytes
0x1801133e0  mov     r15b, r12b
0x1801133e3  call    cs:__imp_HeapAlloc
0x1801133e9  mov     rdi, rax
0x1801133ec  test    rax, rax
0x1801133ef  jnz     short loc_180113434
0x1801133f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1801133f8  lea     rax, WPP_GLOBAL_Control
0x1801133ff  cmp     rcx, rax
0x180113402  jz      loc_180113784
0x180113408  test    byte ptr [rcx+1Ch], 10h
0x18011340c  jz      loc_180113784
0x180113412  cmp     byte ptr [rcx+19h], 4
0x180113416  jb      loc_180113784
0x18011341c  lea     edx, [rdi+0Ah]
0x18011341f  mov     rcx, [rcx+10h]
0x180113423  lea     r8, WPP_62e65b1aa5e43d79debbf88575ed7e0c_Traceguids
0x18011342a  call    WPP_SF_
0x18011342f  jmp     loc_180113784
0x180113434  mov     edx, 1; dwRevision
0x180113439  mov     rcx, rdi; pSecurityDescriptor
0x18011343c  call    cs:__imp_InitializeSecurityDescriptor
0x180113442  test    eax, eax
0x180113444  jnz     short loc_180113481
0x180113446  mov     rcx, cs:WPP_GLOBAL_Control
0x18011344d  lea     rax, WPP_GLOBAL_Control
0x180113454  cmp     rcx, rax
0x180113457  jz      loc_180113784
0x18011345d  test    byte ptr [rcx+1Ch], 10h
0x180113461  jz      loc_180113784
0x180113467  cmp     byte ptr [rcx+19h], 4
0x18011346b  jb      loc_180113784
0x180113471  call    cs:__imp_GetLastError
0x180113477  mov     edx, 0Bh
0x18011347c  jmp     loc_18011376A
0x180113481  lea     rax, [rbp+var_18]
0x180113485  xor     r9d, r9d; nSubAuthority1
0x180113488  mov     [rsp+80h+pSid], rax; pSid
0x18011348d  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x180113491  mov     [rsp+80h+nSubAuthority7], r12d; nSubAuthority7
0x180113496  xor     r8d, r8d; nSubAuthority0
0x180113499  mov     [rsp+80h+nSubAuthority6], r12d; nSubAuthority6
0x18011349e  mov     dl, 1; nSubAuthorityCount
0x1801134a0  mov     [rsp+80h+nSubAuthority5], r12d; nSubAuthority5
0x1801134a5  mov     [rsp+80h+nSubAuthority4], r12d; nSubAuthority4
0x1801134aa  mov     [rsp+80h+nSubAuthority3], r12d; nSubAuthority3
0x1801134af  mov     [rsp+80h+nSubAuthority2], r12d; nSubAuthority2
0x1801134b4  call    cs:__imp_AllocateAndInitializeSid
0x1801134ba  test    eax, eax
0x1801134bc  jnz     short loc_180113513
0x1801134be  mov     rcx, cs:WPP_GLOBAL_Control
0x1801134c5  lea     rax, WPP_GLOBAL_Control
0x1801134cc  cmp     rcx, rax
0x1801134cf  jz      loc_180113784
0x1801134d5  test    byte ptr [rcx+1Ch], 10h
0x1801134d9  jz      loc_180113784
0x1801134df  cmp     byte ptr [rcx+19h], 4
0x1801134e3  jb      loc_180113784
0x1801134e9  call    cs:__imp_GetLastError
0x1801134ef  mov     edx, 0Ch
0x1801134f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1801134fb  lea     r8, WPP_62e65b1aa5e43d79debbf88575ed7e0c_Traceguids
0x180113502  mov     r9d, eax
0x180113505  mov     rcx, [rcx+10h]
0x180113509  call    WPP_SF_d
0x18011350e  jmp     loc_180113784
0x180113513  mov     rcx, cs:?AudiosrvSid@@3PEAXEA; pSid
0x18011351a  call    cs:__imp_GetLengthSid
0x180113520  mov     rcx, [rbp+var_18]; pSid
0x180113524  mov     ebx, eax
0x180113526  call    cs:__imp_GetLengthSid
0x18011352c  mov     rcx, cs:g_hHeap; hHeap
0x180113533  xor     edx, edx; dwFlags
0x180113535  lea     r14d, [rax+18h]
0x180113539  add     r14d, ebx
0x18011353c  mov     r8d, r14d; dwBytes
0x18011353f  call    cs:__imp_HeapAlloc
0x180113545  mov     rbx, rax
0x180113548  test    rax, rax
0x18011354b  jnz     short loc_180113580
0x18011354d  mov     rcx, cs:WPP_GLOBAL_Control
0x180113554  lea     rax, WPP_GLOBAL_Control
0x18011355b  cmp     rcx, rax
0x18011355e  jz      loc_180113784
0x180113564  test    byte ptr [rcx+1Ch], 10h
0x180113568  jz      loc_180113784
0x18011356e  cmp     byte ptr [rcx+19h], 4
0x180113572  jb      loc_180113784
0x180113578  lea     edx, [rbx+0Dh]
0x18011357b  jmp     loc_18011341F
0x180113580  mov     r8d, 2; dwAclRevision
0x180113586  mov     edx, r14d; nAclLength
0x180113589  mov     rcx, rbx; pAcl
0x18011358c  call    cs:__imp_InitializeAcl
0x180113592  test    eax, eax
0x180113594  jnz     short loc_1801135D1
0x180113596  mov     rcx, cs:WPP_GLOBAL_Control
0x18011359d  lea     rax, WPP_GLOBAL_Control
0x1801135a4  cmp     rcx, rax
0x1801135a7  jz      loc_180113784
0x1801135ad  test    byte ptr [rcx+1Ch], 10h
0x1801135b1  jz      loc_180113784
0x1801135b7  cmp     byte ptr [rcx+19h], 4
0x1801135bb  jb      loc_180113784
0x1801135c1  call    cs:__imp_GetLastError
0x1801135c7  mov     edx, 0Eh
0x1801135cc  jmp     loc_1801134F4
0x1801135d1  mov     r9, cs:?AudiosrvSid@@3PEAXEA; pSid
0x1801135d8  mov     r14d, 2
0x1801135de  mov     edx, r14d; dwAceRevision
0x1801135e1  mov     r8d, 0F001Fh; AccessMask
0x1801135e7  mov     rcx, rbx; pAcl
0x1801135ea  call    cs:__imp_AddAccessAllowedAce
0x1801135f0  test    eax, eax
0x1801135f2  jnz     short loc_18011362E
0x1801135f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1801135fb  lea     rax, WPP_GLOBAL_Control
0x180113602  cmp     rcx, rax
0x180113605  jz      loc_180113784
0x18011360b  test    byte ptr [rcx+1Ch], 10h
0x18011360f  jz      loc_180113784
0x180113615  cmp     byte ptr [rcx+19h], 4
0x180113619  jb      loc_180113784
0x18011361f  call    cs:__imp_GetLastError
0x180113625  lea     edx, [r14+0Dh]
0x180113629  jmp     loc_18011376A
0x18011362e  mov     r9, [rbp+var_18]; pSid
0x180113632  mov     r8d, 4; AccessMask
0x180113638  mov     edx, r14d; dwAceRevision
0x18011363b  mov     rcx, rbx; pAcl
0x18011363e  call    cs:__imp_AddAccessAllowedAce
0x180113644  test    eax, eax
0x180113646  jnz     short loc_180113683
0x180113648  mov     rcx, cs:WPP_GLOBAL_Control
0x18011364f  lea     rax, WPP_GLOBAL_Control
0x180113656  cmp     rcx, rax
0x180113659  jz      loc_180113784
0x18011365f  test    byte ptr [rcx+1Ch], 10h
0x180113663  jz      loc_180113784
0x180113669  cmp     byte ptr [rcx+19h], 4
0x18011366d  jb      loc_180113784
0x180113673  call    cs:__imp_GetLastError
0x180113679  mov     edx, 10h
0x18011367e  jmp     loc_18011376A
0x180113683  xor     r9d, r9d; bDaclDefaulted
0x180113686  mov     r8, rbx; pDacl
0x180113689  mov     rcx, rdi; pSecurityDescriptor
0x18011368c  lea     edx, [r9+1]; bDaclPresent
0x180113690  call    cs:__imp_SetSecurityDescriptorDacl
0x180113696  test    eax, eax
0x180113698  jnz     short loc_1801136D5
0x18011369a  mov     rcx, cs:WPP_GLOBAL_Control
0x1801136a1  lea     rax, WPP_GLOBAL_Control
0x1801136a8  cmp     rcx, rax
0x1801136ab  jz      loc_180113784
0x1801136b1  test    byte ptr [rcx+1Ch], 10h
0x1801136b5  jz      loc_180113784
0x1801136bb  cmp     byte ptr [rcx+19h], 4
0x1801136bf  jb      loc_180113784
0x1801136c5  call    cs:__imp_GetLastError
0x1801136cb  mov     edx, 11h
0x1801136d0  jmp     loc_18011376A
0x1801136d5  mov     rcx, rdi; pSecurityDescriptor
0x1801136d8  mov     [rbp+dwBufferLength], r12d
0x1801136dc  call    cs:__imp_GetSecurityDescriptorLength
0x1801136e2  mov     rcx, cs:g_hHeap; hHeap
0x1801136e9  xor     edx, edx; dwFlags
0x1801136eb  mov     r8d, eax; dwBytes
0x1801136ee  mov     [rbp+dwBufferLength], r8d
0x1801136f2  call    cs:__imp_HeapAlloc
0x1801136f8  mov     rsi, rax
0x1801136fb  test    rax, rax
0x1801136fe  jnz     short loc_180113727
0x180113700  mov     rcx, cs:WPP_GLOBAL_Control
0x180113707  lea     rax, WPP_GLOBAL_Control
0x18011370e  cmp     rcx, rax
0x180113711  jz      short loc_180113784
0x180113713  test    byte ptr [rcx+1Ch], 10h
0x180113717  jz      short loc_180113784
0x180113719  cmp     byte ptr [rcx+19h], 4
0x18011371d  jb      short loc_180113784
0x18011371f  lea     edx, [rsi+12h]
0x180113722  jmp     loc_18011341F
0x180113727  lea     r8, [rbp+dwBufferLength]; lpdwBufferLength
0x18011372b  mov     rdx, rax; pSelfRelativeSecurityDescriptor
0x18011372e  mov     rcx, rdi; pAbsoluteSecurityDescriptor
0x180113731  call    cs:__imp_MakeSelfRelativeSD
0x180113737  test    eax, eax
0x180113739  jz      short loc_180113740
0x18011373b  mov     r15b, 1
0x18011373e  jmp     short loc_180113784
0x180113740  mov     rcx, cs:WPP_GLOBAL_Control
0x180113747  lea     rax, WPP_GLOBAL_Control
0x18011374e  cmp     rcx, rax
0x180113751  jz      short loc_180113784
0x180113753  test    byte ptr [rcx+1Ch], 10h
0x180113757  jz      short loc_180113784
0x180113759  cmp     byte ptr [rcx+19h], 4
0x18011375d  jb      short loc_180113784
0x18011375f  call    cs:__imp_GetLastError
0x180113765  mov     edx, 13h
0x18011376a  mov     rcx, cs:WPP_GLOBAL_Control
0x180113771  lea     r8, WPP_62e65b1aa5e43d79debbf88575ed7e0c_Traceguids
0x180113778  mov     r9d, eax
0x18011377b  mov     rcx, [rcx+10h]
0x18011377f  call    WPP_SF_d
0x180113784  mov     rcx, [rbp+var_18]; pSid
0x180113788  test    rcx, rcx
0x18011378b  jz      short loc_180113793
0x18011378d  call    cs:__imp_FreeSid
0x180113793  test    rbx, rbx
0x180113796  jz      short loc_1801137AA
0x180113798  mov     rcx, cs:g_hHeap; hHeap
0x18011379f  mov     r8, rbx; lpMem
0x1801137a2  xor     edx, edx; dwFlags
0x1801137a4  call    cs:__imp_HeapFree
0x1801137aa  test    rdi, rdi
0x1801137ad  jz      short loc_1801137C1
0x1801137af  mov     rcx, cs:g_hHeap; hHeap
0x1801137b6  mov     r8, rdi; lpMem
0x1801137b9  xor     edx, edx; dwFlags
0x1801137bb  call    cs:__imp_HeapFree
0x1801137c1  test    r15b, r15b
0x1801137c4  jnz     short loc_1801137DD
0x1801137c6  test    rsi, rsi
0x1801137c9  jz      short loc_1801137DD
0x1801137cb  mov     rcx, cs:g_hHeap; hHeap
0x1801137d2  mov     r8, rsi; lpMem
0x1801137d5  xor     edx, edx; dwFlags
0x1801137d7  call    cs:__imp_HeapFree
0x1801137dd  neg     r15b
0x1801137e0  sbb     rax, rax
0x1801137e3  and     rax, rsi
0x1801137e6  mov     rcx, [rbp+var_8]
0x1801137ea  xor     rcx, rsp; StackCookie
0x1801137ed  call    __security_check_cookie
0x1801137f2  add     rsp, 80h
0x1801137f9  pop     r15
0x1801137fb  pop     r14
0x1801137fd  pop     r12
0x1801137ff  pop     rdi
0x180113800  pop     rsi
0x180113801  pop     rbx
0x180113802  pop     rbp
0x180113803  retn
```
