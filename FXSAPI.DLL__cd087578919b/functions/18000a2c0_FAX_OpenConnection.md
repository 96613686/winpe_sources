# FAX_OpenConnection

- ea: `0x18000a2c0`
- end: `0x18000a6f5`
- name: `FAX_OpenConnection`
- size: `1077`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE ClientBinding, struct _ASYNC_EVENT_INFO *, __int64 **)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation`

## callees

- `0x180004cb4`
- `0x180008fd0`
- `0x18000a2c0`
- `0x18000abe4`
- `0x18000ac14`
- `0x18003358c`

## import_xrefs

- `RPCRT4!RpcBindingInqAuthClientW` at `0x18000a512`
- `RPCRT4!RpcBindingInqAuthClientW` at `0x18000a512`
- `KERNEL32!GetVersion` at `0x18000a4b7`
- `KERNEL32!GetVersion` at `0x18000a4b7`
- `KERNEL32!EnterCriticalSection` at `0x18000a320`
- `KERNEL32!EnterCriticalSection` at `0x18000a320`
- `KERNEL32!LeaveCriticalSection` at `0x18000a6d9`
- `KERNEL32!LeaveCriticalSection` at `0x18000a6d9`

## pseudocode

```c
__int64 __fastcall FAX_OpenConnection(RPC_BINDING_HANDLE ClientBinding, struct _ASYNC_EVENT_INFO *a2, __int64 **a3)
{
  __int64 *v4; // r14
  unsigned int v6; // ebx
  struct _LIST_ENTRY *v7; // rcx
  __int64 v8; // r9
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  unsigned int v11; // eax
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r9
  struct _ASYNC_EVENT_INFO *AuthnLevel; // [rsp+78h] [rbp+10h] BYREF
  __int64 **v17; // [rsp+80h] [rbp+18h]
  RPC_AUTHZ_HANDLE Privs; // [rsp+88h] [rbp+20h] BYREF

  v17 = a3;
  AuthnLevel = a2;
  v4 = (__int64 *)a2;
  v6 = 5;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_152912f6797533292abcfca723f93957_Traceguids);
  }
  EnterCriticalSection(&g_CsFaxAssyncInfo);
  if ( !FindContextNode(v7, (struct _ASYNC_EVENT_INFO *)v4) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, &WPP_152912f6797533292abcfca723f93957_Traceguids);
    }
    v6 = 87;
    goto LABEL_67;
  }
  if ( v4[3] )
    goto LABEL_73;
  if ( !v4[5] )
  {
LABEL_15:
    v6 = 87;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_152912f6797533292abcfca723f93957_Traceguids);
    }
    goto LABEL_67;
  }
  if ( v4[3] )
  {
LABEL_73:
    if ( v4[5] )
      goto LABEL_15;
  }
  if ( !ValidAsyncInfoSignature((const wchar_t *)v4) )
  {
    v6 = 87;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_152912f6797533292abcfca723f93957_Traceguids);
    }
    goto LABEL_67;
  }
  v8 = *((unsigned int *)v4 + 20);
  if ( (unsigned int)v8 > 1 )
  {
    v6 = 87;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_152912f6797533292abcfca723f93957_Traceguids, v8);
    }
    goto LABEL_67;
  }
  if ( *((_DWORD *)v4 + 18) )
  {
    v6 = 87;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_67;
    }
    v10 = 40;
    goto LABEL_37;
  }
  *((_DWORD *)v4 + 18) = 1;
  if ( (unsigned __int8)GetVersion() < 5u || *((_DWORD *)v4 + 19) <= 0x10000u )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, &WPP_152912f6797533292abcfca723f93957_Traceguids);
    }
  }
  else
  {
    Privs = 0;
    LODWORD(AuthnLevel) = 0;
    v11 = RpcBindingInqAuthClientW(ClientBinding, &Privs, 0, (unsigned int *)&AuthnLevel, 0, 0);
    if ( v11 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_67;
      }
      v13 = 41;
      v14 = v11;
      goto LABEL_45;
    }
    v14 = (unsigned int)AuthnLevel;
    if ( (unsigned int)AuthnLevel < 6 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_67;
      }
      v13 = 42;
LABEL_45:
      WPP_SF_d(v12[2], v13, &WPP_152912f6797533292abcfca723f93957_Traceguids, v14);
      goto LABEL_67;
    }
  }
  v6 = 0;
  v4[8] = (__int64)ClientBinding;
  if ( !*((_DWORD *)v4 + 14) )
    goto LABEL_67;
  LODWORD(AuthnLevel) = 0;
  v6 = IsLocalRPCConnectionIpTcp(ClientBinding, &AuthnLevel);
  if ( !v6 )
  {
    if ( (_DWORD)AuthnLevel )
      goto LABEL_67;
    v6 = 87;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_67;
    }
    v10 = 45;
LABEL_37:
    WPP_SF_(v9[2], v10, &WPP_152912f6797533292abcfca723f93957_Traceguids);
LABEL_67:
    if ( v6 )
    {
      v6 = 0;
      v4 = qword_180043400;
    }
    *a3 = v4;
    goto LABEL_70;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_152912f6797533292abcfca723f93957_Traceguids, v6);
  }
  *a3 = 0;
LABEL_70:
  LeaveCriticalSection(&g_CsFaxAssyncInfo);
  return v6;
}

```

## disassembly

```asm
0x18000a2c0  mov     [rsp+arg_10], r8
0x18000a2c5  mov     [rsp+AuthnLevel], rdx
0x18000a2ca  push    rbx
0x18000a2cb  push    rsi
0x18000a2cc  push    r12
0x18000a2ce  push    r13
0x18000a2d0  push    r14
0x18000a2d2  sub     rsp, 40h
0x18000a2d6  mov     r13, r8
0x18000a2d9  mov     r14, rdx
0x18000a2dc  mov     r12, rcx
0x18000a2df  lea     rax, WPP_GLOBAL_Control
0x18000a2e6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a2ed  mov     esi, 1000h
0x18000a2f2  mov     ebx, 5
0x18000a2f7  cmp     rcx, rax
0x18000a2fa  jz      short loc_18000A319
0x18000a2fc  test    [rcx+1Ch], esi
0x18000a2ff  jz      short loc_18000A319
0x18000a301  cmp     [rcx+19h], bl
0x18000a304  jb      short loc_18000A319
0x18000a306  lea     edx, [rbx+1Ch]
0x18000a309  lea     r8, WPP_152912f6797533292abcfca723f93957_Traceguids
0x18000a310  mov     rcx, [rcx+10h]
0x18000a314  call    WPP_SF_
0x18000a319  lea     rcx, ?g_CsFaxAssyncInfo@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000a320  call    cs:__imp_EnterCriticalSection
0x18000a327  nop     dword ptr [rax+rax+00h]
0x18000a32c  mov     rdx, r14; struct _ASYNC_EVENT_INFO *
0x18000a32f  call    ?FindContextNode@@YAPEAU_CONTEXT_NODE@@PEAU_LIST_ENTRY@@PEAU_ASYNC_EVENT_INFO@@@Z; FindContextNode(_LIST_ENTRY *,_ASYNC_EVENT_INFO *)
0x18000a334  test    rax, rax
0x18000a337  jnz     short loc_18000A374
0x18000a339  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a340  lea     rdx, WPP_GLOBAL_Control
0x18000a347  cmp     rcx, rdx
0x18000a34a  jz      short loc_18000A36A
0x18000a34c  test    [rcx+1Ch], esi
0x18000a34f  jz      short loc_18000A36A
0x18000a351  cmp     byte ptr [rcx+19h], 2
0x18000a355  jb      short loc_18000A36A
0x18000a357  lea     edx, [rax+23h]
0x18000a35a  lea     r8, WPP_152912f6797533292abcfca723f93957_Traceguids
0x18000a361  mov     rcx, [rcx+10h]
0x18000a365  call    WPP_SF_
0x18000a36a  mov     ebx, 57h ; 'W'
0x18000a36f  jmp     loc_18000A6C1
0x18000a374  cmp     qword ptr [r14+18h], 0
0x18000a379  jnz     short loc_18000A389
0x18000a37b  cmp     qword ptr [r14+28h], 0
0x18000a380  jz      short loc_18000A390
0x18000a382  cmp     qword ptr [r14+18h], 0
0x18000a387  jz      short loc_18000A3CF
0x18000a389  cmp     qword ptr [r14+28h], 0
0x18000a38e  jz      short loc_18000A3CF
0x18000a390  mov     ebx, 57h ; 'W'
0x18000a395  mov     [rsp+68h+var_38], ebx
0x18000a399  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a3a0  lea     rdx, WPP_GLOBAL_Control
0x18000a3a7  cmp     rcx, rdx
0x18000a3aa  jz      short loc_18000A3CA
0x18000a3ac  test    [rcx+1Ch], esi
0x18000a3af  jz      short loc_18000A3CA
0x18000a3b1  cmp     byte ptr [rcx+19h], 2
0x18000a3b5  jb      short loc_18000A3CA
0x18000a3b7  lea     edx, [rbx-33h]
0x18000a3ba  lea     r8, WPP_152912f6797533292abcfca723f93957_Traceguids
0x18000a3c1  mov     rcx, [rcx+10h]
0x18000a3c5  call    WPP_SF_
0x18000a3ca  jmp     loc_18000A6C1
0x18000a3cf  mov     rcx, r14; struct _ASYNC_EVENT_INFO *
0x18000a3d2  call    ?ValidAsyncInfoSignature@@YAHPEAU_ASYNC_EVENT_INFO@@@Z; ValidAsyncInfoSignature(_ASYNC_EVENT_INFO *)
0x18000a3d7  test    eax, eax
0x18000a3d9  jnz     short loc_18000A418
0x18000a3db  lea     ebx, [rax+57h]
0x18000a3de  mov     [rsp+68h+var_38], ebx
0x18000a3e2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a3e9  lea     rdx, WPP_GLOBAL_Control
0x18000a3f0  cmp     rcx, rdx
0x18000a3f3  jz      short loc_18000A413
0x18000a3f5  test    [rcx+1Ch], esi
0x18000a3f8  jz      short loc_18000A413
0x18000a3fa  cmp     byte ptr [rcx+19h], 2
0x18000a3fe  jb      short loc_18000A413
0x18000a400  lea     edx, [rax+25h]
0x18000a403  lea     r8, WPP_152912f6797533292abcfca723f93957_Traceguids
0x18000a40a  mov     rcx, [rcx+10h]
0x18000a40e  call    WPP_SF_
0x18000a413  jmp     loc_18000A6C1
0x18000a418  mov     r9d, [r14+50h]
0x18000a41c  cmp     r9d, 1
0x18000a420  jbe     short loc_18000A461
0x18000a422  mov     ebx, 57h ; 'W'
0x18000a427  mov     [rsp+68h+var_38], ebx
0x18000a42b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a432  lea     rdx, WPP_GLOBAL_Control
0x18000a439  cmp     rcx, rdx
0x18000a43c  jz      short loc_18000A45C
0x18000a43e  test    [rcx+1Ch], esi
0x18000a441  jz      short loc_18000A45C
0x18000a443  cmp     byte ptr [rcx+19h], 2
0x18000a447  jb      short loc_18000A45C
0x18000a449  lea     edx, [rbx-31h]
0x18000a44c  lea     r8, WPP_152912f6797533292abcfca723f93957_Traceguids
0x18000a453  mov     rcx, [rcx+10h]
0x18000a457  call    WPP_SF_d
0x18000a45c  jmp     loc_18000A6C1
0x18000a461  cmp     dword ptr [r14+48h], 0
0x18000a466  jz      short loc_18000A4AF
0x18000a468  mov     ebx, 57h ; 'W'
0x18000a46d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a474  lea     rdx, WPP_GLOBAL_Control
0x18000a47b  cmp     rcx, rdx
0x18000a47e  jz      loc_18000A6C1
0x18000a484  test    [rcx+1Ch], esi
0x18000a487  jz      loc_18000A6C1
0x18000a48d  cmp     byte ptr [rcx+19h], 2
0x18000a491  jb      loc_18000A6C1
0x18000a497  lea     edx, [rbx-2Fh]
0x18000a49a  lea     r8, WPP_152912f6797533292abcfca723f93957_Traceguids
0x18000a4a1  mov     rcx, [rcx+10h]
0x18000a4a5  call    WPP_SF_
0x18000a4aa  jmp     loc_18000A6C1
0x18000a4af  mov     dword ptr [r14+48h], 1
0x18000a4b7  call    cs:__imp_GetVersion
0x18000a4be  nop     dword ptr [rax+rax+00h]
0x18000a4c3  cmp     al, bl
0x18000a4c5  jb      loc_18000A5A5
0x18000a4cb  cmp     dword ptr [r14+4Ch], 10000h
0x18000a4d3  jbe     loc_18000A5A5
0x18000a4d9  mov     [rsp+68h+Privs], 0
0x18000a4e5  mov     dword ptr [rsp+68h+AuthnLevel], 0
0x18000a4ed  mov     [rsp+68h+AuthzSvc], 0; AuthzSvc
0x18000a4f6  mov     [rsp+68h+AuthnSvc], 0; AuthnSvc
0x18000a4ff  lea     r9, [rsp+68h+AuthnLevel]; AuthnLevel
0x18000a504  xor     r8d, r8d; ServerPrincName
0x18000a507  lea     rdx, [rsp+68h+Privs]; Privs
0x18000a50f  mov     rcx, r12; ClientBinding
0x18000a512  call    cs:__imp_RpcBindingInqAuthClientW
0x18000a519  nop     dword ptr [rax+rax+00h]
0x18000a51e  test    eax, eax
0x18000a520  jz      short loc_18000A569
0x18000a522  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a529  lea     rdx, WPP_GLOBAL_Control
0x18000a530  cmp     rcx, rdx
0x18000a533  jz      loc_18000A6C1
0x18000a539  test    [rcx+1Ch], esi
0x18000a53c  jz      loc_18000A6C1
0x18000a542  cmp     byte ptr [rcx+19h], 2
0x18000a546  jb      loc_18000A6C1
0x18000a54c  mov     edx, 29h ; ')'
0x18000a551  mov     r9d, eax
0x18000a554  lea     r8, WPP_152912f6797533292abcfca723f93957_Traceguids
0x18000a55b  mov     rcx, [rcx+10h]
0x18000a55f  call    WPP_SF_d
0x18000a564  jmp     loc_18000A6C1
0x18000a569  mov     r9d, dword ptr [rsp+68h+AuthnLevel]
0x18000a56e  cmp     r9d, 6
0x18000a572  jnb     short loc_18000A5D8
0x18000a574  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a57b  lea     rdx, WPP_GLOBAL_Control
0x18000a582  cmp     rcx, rdx
0x18000a585  jz      loc_18000A6C1
0x18000a58b  test    [rcx+1Ch], esi
0x18000a58e  jz      loc_18000A6C1
0x18000a594  cmp     byte ptr [rcx+19h], 2
0x18000a598  jb      loc_18000A6C1
0x18000a59e  mov     edx, 2Ah ; '*'
0x18000a5a3  jmp     short loc_18000A554
0x18000a5a5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a5ac  lea     rdx, WPP_GLOBAL_Control
0x18000a5b3  cmp     rcx, rdx
0x18000a5b6  jz      short loc_18000A5D8
0x18000a5b8  test    [rcx+1Ch], esi
0x18000a5bb  jz      short loc_18000A5D8
0x18000a5bd  cmp     byte ptr [rcx+19h], 3
0x18000a5c1  jb      short loc_18000A5D8
0x18000a5c3  mov     edx, 2Bh ; '+'
0x18000a5c8  lea     r8, WPP_152912f6797533292abcfca723f93957_Traceguids
0x18000a5cf  mov     rcx, [rcx+10h]
0x18000a5d3  call    WPP_SF_
0x18000a5d8  xor     ebx, ebx
0x18000a5da  mov     [r14+40h], r12
0x18000a5de  cmp     [r14+38h], ebx
0x18000a5e2  jz      loc_18000A6C1
0x18000a5e8  mov     dword ptr [rsp+68h+AuthnLevel], ebx
0x18000a5ec  lea     rdx, [rsp+68h+AuthnLevel]
0x18000a5f1  mov     rcx, r12; ClientBinding
0x18000a5f4  call    IsLocalRPCConnectionIpTcp
0x18000a5f9  mov     ebx, eax
0x18000a5fb  test    eax, eax
0x18000a5fd  jz      short loc_18000A642
0x18000a5ff  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a606  lea     rax, WPP_GLOBAL_Control
0x18000a60d  cmp     rcx, rax
0x18000a610  jz      short loc_18000A635
0x18000a612  test    [rcx+1Ch], esi
0x18000a615  jz      short loc_18000A635
0x18000a617  cmp     byte ptr [rcx+19h], 2
0x18000a61b  jb      short loc_18000A635
0x18000a61d  mov     edx, 2Ch ; ','
0x18000a622  mov     r9d, ebx
0x18000a625  lea     r8, WPP_152912f6797533292abcfca723f93957_Traceguids
0x18000a62c  mov     rcx, [rcx+10h]
0x18000a630  call    WPP_SF_d
0x18000a635  mov     qword ptr [r13+0], 0
0x18000a63d  jmp     loc_18000A6D2
0x18000a642  cmp     dword ptr [rsp+68h+AuthnLevel], 0
0x18000a647  jnz     short loc_18000A6C1
0x18000a649  mov     ebx, 57h ; 'W'
0x18000a64e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a655  lea     rax, WPP_GLOBAL_Control
0x18000a65c  cmp     rcx, rax
0x18000a65f  jz      short loc_18000A6C1
0x18000a661  test    [rcx+1Ch], esi
0x18000a664  jz      short loc_18000A6C1
0x18000a666  cmp     byte ptr [rcx+19h], 2
0x18000a66a  jb      short loc_18000A6C1
0x18000a66c  lea     edx, [rbx-2Ah]
0x18000a66f  jmp     loc_18000A49A
0x18000a674  mov     ebx, eax
0x18000a676  mov     [rsp+68h+var_38], eax
0x18000a67a  lea     rax, WPP_GLOBAL_Control
0x18000a681  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a688  cmp     rcx, rax
0x18000a68b  jz      short loc_18000A6B4
0x18000a68d  test    dword ptr [rcx+1Ch], 1000h
0x18000a694  jz      short loc_18000A6B4
0x18000a696  cmp     byte ptr [rcx+19h], 2
0x18000a69a  jb      short loc_18000A6B4
0x18000a69c  mov     edx, 27h ; '''
0x18000a6a1  mov     r9d, ebx
0x18000a6a4  lea     r8, WPP_152912f6797533292abcfca723f93957_Traceguids
0x18000a6ab  mov     rcx, [rcx+10h]
0x18000a6af  call    WPP_SF_d
0x18000a6b4  mov     r13, [rsp+68h+arg_10]
0x18000a6bc  mov     r14, [rsp+68h+AuthnLevel]
0x18000a6c1  test    ebx, ebx
0x18000a6c3  jz      short loc_18000A6CE
0x18000a6c5  xor     ebx, ebx
0x18000a6c7  lea     r14, qword_180043400
0x18000a6ce  mov     [r13+0], r14
0x18000a6d2  lea     rcx, ?g_CsFaxAssyncInfo@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000a6d9  call    cs:__imp_LeaveCriticalSection
0x18000a6e0  nop     dword ptr [rax+rax+00h]
0x18000a6e5  mov     eax, ebx
0x18000a6e7  add     rsp, 40h
0x18000a6eb  pop     r14
0x18000a6ed  pop     r13
0x18000a6ef  pop     r12
0x18000a6f1  pop     rsi
0x18000a6f2  pop     rbx
0x18000a6f3  retn
```
