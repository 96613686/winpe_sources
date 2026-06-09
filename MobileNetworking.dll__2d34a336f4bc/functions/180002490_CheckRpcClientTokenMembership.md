# CheckRpcClientTokenMembership

- ea: `0x180002490`
- end: `0x180002649`
- name: `CheckRpcClientTokenMembership`
- size: `441`
- prototype: `__int64 __fastcall(unsigned int, WINBOOL *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180002490`
- `0x180002a40`
- `0x180002b20`
- `0x180002bc0`
- `0x180008ff0`
- `0x180009130`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002584`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002584`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18000257a`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18000257a`
- `RPCRT4!RpcRevertToSelf` at `0x18000256a`
- `RPCRT4!RpcRevertToSelf` at `0x18000256a`

## pseudocode

```c
__int64 __fastcall CheckRpcClientTokenMembership(unsigned int a1, WINBOOL *a2)
{
  __int64 v2; // rsi
  PVOID *v4; // rcx
  unsigned int v5; // ebx
  unsigned int v7; // eax
  DWORD LastError; // eax
  void *v9; // rdx
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 v13; // r9
  int v14; // [rsp+48h] [rbp+10h] BYREF
  int v15; // [rsp+50h] [rbp+18h] BYREF

  v2 = a1;
  v14 = 0;
  v15 = 0;
  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 124, WPP_fd6184a389643c6486807174a58ed414_Traceguids);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !a2 || (unsigned int)v2 >= 0xA )
  {
    v5 = 87;
    if ( v4 == &WPP_GLOBAL_Control || (*((_BYTE *)v4 + 28) & 4) == 0 )
      goto LABEL_6;
    v12 = 125;
    v13 = 87;
    goto LABEL_30;
  }
  *a2 = 0;
  v7 = AcquireLockSecurityObject(&v15);
  v5 = v7;
  if ( v7 )
  {
    v4 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_6;
    v12 = 126;
    v13 = v7;
LABEL_30:
    WPP_SF_L(v4[2], v12, WPP_fd6184a389643c6486807174a58ed414_Traceguids, v13);
    goto LABEL_6;
  }
  LastError = ImpersonateRPCClientIfRequired(&v14);
  v5 = LastError;
  if ( LastError )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v11 = 127;
      goto LABEL_21;
    }
  }
  else
  {
    v9 = *(void **)(*(_QWORD *)&g_pSecurity + 8 * v2);
    if ( v9 )
    {
      if ( !CheckTokenMembership(0, v9, a2) )
      {
        LastError = GetLastError();
        v5 = LastError;
        if ( LastError )
        {
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            v11 = 128;
LABEL_21:
            WPP_SF_L(v10[2], v11, WPP_fd6184a389643c6486807174a58ed414_Traceguids, LastError);
          }
        }
      }
    }
  }
  if ( v14 )
    RpcRevertToSelf();
LABEL_6:
  ReleaseLockSecurityObject(&v15);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_L(*((_QWORD *)WPP_GLOBAL_Control + 2), 129, WPP_fd6184a389643c6486807174a58ed414_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x180002490  mov     [rsp+arg_0], rbx
0x180002495  push    rbp
0x180002496  push    rsi
0x180002497  push    rdi
0x180002498  sub     rsp, 20h
0x18000249c  xor     ebx, ebx
0x18000249e  mov     esi, ecx
0x1800024a0  mov     [rsp+38h+arg_8], ebx
0x1800024a4  mov     rdi, rdx
0x1800024a7  mov     [rsp+38h+arg_10], ebx
0x1800024ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800024b2  lea     rbp, WPP_GLOBAL_Control
0x1800024b9  cmp     rcx, rbp
0x1800024bc  jz      short loc_1800024C8
0x1800024be  test    byte ptr [rcx+1Ch], 8
0x1800024c2  jnz     loc_1800025BC
0x1800024c8  test    rdi, rdi
0x1800024cb  jnz     short loc_180002520
0x1800024cd  mov     ebx, 57h ; 'W'
0x1800024d2  cmp     rcx, rbp
0x1800024d5  jnz     loc_180002622
0x1800024db  lea     rcx, [rsp+38h+arg_10]
0x1800024e0  call    ReleaseLockSecurityObject
0x1800024e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800024ec  cmp     rcx, rbp
0x1800024ef  jnz     short loc_180002500
0x1800024f1  mov     eax, ebx
0x1800024f3  mov     rbx, [rsp+38h+arg_0]
0x1800024f8  add     rsp, 20h
0x1800024fc  pop     rdi
0x1800024fd  pop     rsi
0x1800024fe  pop     rbp
0x1800024ff  retn
0x180002500  test    byte ptr [rcx+1Ch], 8
0x180002504  jz      short loc_1800024F1
0x180002506  mov     rcx, [rcx+10h]
0x18000250a  lea     r8, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x180002511  mov     edx, 81h
0x180002516  mov     r9d, ebx
0x180002519  call    WPP_SF_L
0x18000251e  jmp     short loc_1800024F1
0x180002520  cmp     esi, 0Ah
0x180002523  jnb     short loc_1800024CD
0x180002525  lea     rcx, [rsp+38h+arg_10]
0x18000252a  mov     [rdi], ebx
0x18000252c  call    AcquireLockSecurityObject
0x180002531  mov     ebx, eax
0x180002533  test    eax, eax
0x180002535  jnz     loc_1800025DD
0x18000253b  lea     rcx, [rsp+38h+arg_8]
0x180002540  call    ImpersonateRPCClientIfRequired
0x180002545  mov     ebx, eax
0x180002547  test    eax, eax
0x180002549  jnz     loc_180002601
0x18000254f  mov     rax, cs:g_pSecurity
0x180002556  mov     rdx, [rax+rsi*8]; SidToCheck
0x18000255a  test    rdx, rdx
0x18000255d  jnz     short loc_180002575
0x18000255f  cmp     [rsp+38h+arg_8], 0
0x180002564  jz      loc_1800024DB
0x18000256a  call    cs:__imp_RpcRevertToSelf
0x180002570  jmp     loc_1800024DB
0x180002575  mov     r8, rdi; IsMember
0x180002578  xor     ecx, ecx; TokenHandle
0x18000257a  call    cs:__imp_CheckTokenMembership
0x180002580  test    eax, eax
0x180002582  jnz     short loc_18000255F
0x180002584  call    cs:__imp_GetLastError
0x18000258a  mov     ebx, eax
0x18000258c  test    eax, eax
0x18000258e  jz      short loc_18000255F
0x180002590  mov     rcx, cs:WPP_GLOBAL_Control
0x180002597  cmp     rcx, rbp
0x18000259a  jz      short loc_18000255F
0x18000259c  test    byte ptr [rcx+1Ch], 4
0x1800025a0  jz      short loc_18000255F
0x1800025a2  mov     edx, 80h
0x1800025a7  mov     rcx, [rcx+10h]
0x1800025ab  lea     r8, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x1800025b2  mov     r9d, eax
0x1800025b5  call    WPP_SF_L
0x1800025ba  jmp     short loc_18000255F
0x1800025bc  mov     rcx, [rcx+10h]
0x1800025c0  lea     r8, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x1800025c7  mov     edx, 7Ch ; '|'
0x1800025cc  call    WPP_SF_
0x1800025d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800025d8  jmp     loc_1800024C8
0x1800025dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800025e4  cmp     rcx, rbp
0x1800025e7  jz      loc_1800024DB
0x1800025ed  test    byte ptr [rcx+1Ch], 4
0x1800025f1  jz      loc_1800024DB
0x1800025f7  mov     edx, 7Eh ; '~'
0x1800025fc  mov     r9d, eax
0x1800025ff  jmp     short loc_180002634
0x180002601  mov     rcx, cs:WPP_GLOBAL_Control
0x180002608  cmp     rcx, rbp
0x18000260b  jz      loc_18000255F
0x180002611  test    byte ptr [rcx+1Ch], 4
0x180002615  jz      loc_18000255F
0x18000261b  mov     edx, 7Fh
0x180002620  jmp     short loc_1800025A7
0x180002622  test    byte ptr [rcx+1Ch], 4
0x180002626  jz      loc_1800024DB
0x18000262c  mov     edx, 7Dh ; '}'
0x180002631  mov     r9d, ebx
0x180002634  mov     rcx, [rcx+10h]
0x180002638  lea     r8, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x18000263f  call    WPP_SF_L
0x180002644  jmp     loc_1800024DB
```
