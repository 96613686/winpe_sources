# BdeSvcApipAddRecoveryPassword

- ea: `0x18004c630`
- end: `0x18004c827`
- name: `BdeSvcApipAddRecoveryPassword`
- size: `503`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180009f30`
- `0x180009f60`
- `0x180034070`
- `0x18004c630`
- `0x1800716f4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c6c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c6c3`
- `RPCRT4!RpcImpersonateClient` at `0x18004c68d`
- `RPCRT4!RpcImpersonateClient` at `0x18004c68d`
- `RPCRT4!RpcRevertToSelf` at `0x18004c7b2`
- `RPCRT4!RpcRevertToSelf` at `0x18004c7b2`
- `FVEAPI!FveCommitChanges` at `0x18004c77a`
- `FVEAPI!FveCommitChanges` at `0x18004c77a`
- `FVEAPI!FveOpenVolumeW` at `0x18004c71e`
- `FVEAPI!FveOpenVolumeW` at `0x18004c71e`
- `FVEAPI!FveCloseVolume` at `0x18004c7d2`
- `FVEAPI!FveCloseVolume` at `0x18004c7d2`

## pseudocode

```c
__int64 __fastcall BdeSvcApipAddRecoveryPassword(__int64 a1, __int64 a2, struct _GUID *a3)
{
  unsigned int v5; // eax
  signed int LastError; // eax
  unsigned int v7; // ebx
  PVOID *v8; // rcx
  int v9; // eax
  unsigned __int16 *v10; // rdx
  unsigned __int16 *v11; // r8
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  void *v15; // [rsp+20h] [rbp-28h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids);
  v15 = (void *)-1LL;
  v5 = RpcImpersonateClient(0);
  if ( !v5 )
  {
    v9 = FveOpenVolumeW(a2, 1, &v15);
    v7 = v9;
    if ( v9 >= 0 )
    {
      v9 = CFveApiWrapper::AddRecoveryPassword(v15, v10, v11, a3);
      v7 = v9;
      if ( v9 >= 0 )
      {
        v9 = FveCommitChanges(v15);
        v7 = v9;
        if ( v9 >= 0 )
          goto LABEL_26;
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_26;
        v13 = 36;
      }
      else
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_26;
        v13 = 35;
      }
    }
    else
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_26;
      v13 = 34;
    }
    WPP_SF_d(v12[2], v13, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids, (unsigned int)v9);
LABEL_26:
    RpcRevertToSelf();
    goto LABEL_27;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids, v5);
  LastError = GetLastError();
  v7 = LastError;
  if ( LastError > 0 )
    v7 = (unsigned __int16)LastError | 0x80070000;
  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids, v7);
LABEL_27:
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v15 != (void *)-1LL )
  {
    FveCloseVolume(v15);
    v8 = (PVOID *)WPP_GLOBAL_Control;
    v15 = (void *)-1LL;
  }
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 0x20) != 0 )
    WPP_SF_(v8[2], 37, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids);
  return v7;
}

```

## disassembly

```asm
0x18004c630  mov     [rsp+arg_0], rbx
0x18004c635  push    rbp
0x18004c636  push    rsi
0x18004c637  push    rdi
0x18004c638  sub     rsp, 30h
0x18004c63c  mov     rax, cs:__security_cookie
0x18004c643  xor     rax, rsp
0x18004c646  mov     [rsp+48h+var_20], rax
0x18004c64b  mov     rdi, r8
0x18004c64e  mov     rbx, rdx
0x18004c651  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c658  lea     rsi, WPP_GLOBAL_Control
0x18004c65f  lea     rbp, WPP_951aaf4f82a831773594a9234edf98f2_Traceguids
0x18004c666  cmp     rcx, rsi
0x18004c669  jz      short loc_18004C682
0x18004c66b  test    byte ptr [rcx+1Ch], 20h
0x18004c66f  jz      short loc_18004C682
0x18004c671  mov     rcx, [rcx+10h]
0x18004c675  mov     edx, 1Fh
0x18004c67a  mov     r8, rbp
0x18004c67d  call    WPP_SF_
0x18004c682  xor     ecx, ecx; BindingHandle
0x18004c684  mov     [rsp+48h+var_28], 0FFFFFFFFFFFFFFFFh
0x18004c68d  call    cs:__imp_RpcImpersonateClient
0x18004c694  nop     dword ptr [rax+rax+00h]
0x18004c699  test    eax, eax
0x18004c69b  jz      short loc_18004C711
0x18004c69d  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c6a4  cmp     rcx, rsi
0x18004c6a7  jz      short loc_18004C6C3
0x18004c6a9  test    byte ptr [rcx+1Ch], 2
0x18004c6ad  jz      short loc_18004C6C3
0x18004c6af  mov     rcx, [rcx+10h]
0x18004c6b3  mov     edx, 20h ; ' '
0x18004c6b8  mov     r9d, eax
0x18004c6bb  mov     r8, rbp
0x18004c6be  call    WPP_SF_d
0x18004c6c3  call    cs:__imp_GetLastError
0x18004c6ca  nop     dword ptr [rax+rax+00h]
0x18004c6cf  mov     ebx, eax
0x18004c6d1  test    eax, eax
0x18004c6d3  jle     short loc_18004C6DE
0x18004c6d5  movzx   ebx, ax
0x18004c6d8  or      ebx, 80070000h
0x18004c6de  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c6e5  cmp     rcx, rsi
0x18004c6e8  jz      loc_18004C7C5
0x18004c6ee  test    byte ptr [rcx+1Ch], 40h
0x18004c6f2  jz      loc_18004C7C5
0x18004c6f8  mov     rcx, [rcx+10h]
0x18004c6fc  mov     edx, 21h ; '!'
0x18004c701  mov     r9d, ebx
0x18004c704  mov     r8, rbp
0x18004c707  call    WPP_SF_d
0x18004c70c  jmp     loc_18004C7BE
0x18004c711  lea     r8, [rsp+48h+var_28]
0x18004c716  mov     edx, 1
0x18004c71b  mov     rcx, rbx
0x18004c71e  call    cs:__imp_FveOpenVolumeW
0x18004c725  nop     dword ptr [rax+rax+00h]
0x18004c72a  mov     ebx, eax
0x18004c72c  test    eax, eax
0x18004c72e  jns     short loc_18004C749
0x18004c730  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c737  cmp     rcx, rsi
0x18004c73a  jz      short loc_18004C7B2
0x18004c73c  test    byte ptr [rcx+1Ch], 2
0x18004c740  jz      short loc_18004C7B2
0x18004c742  mov     edx, 22h ; '"'
0x18004c747  jmp     short loc_18004C7A3
0x18004c749  mov     rcx, [rsp+48h+var_28]; void *
0x18004c74e  mov     r9, rdi; struct _GUID *
0x18004c751  call    ?AddRecoveryPassword@CFveApiWrapper@@SAJPEAXPEAG1PEAU_GUID@@@Z; CFveApiWrapper::AddRecoveryPassword(void *,ushort *,ushort *,_GUID *)
0x18004c756  mov     ebx, eax
0x18004c758  test    eax, eax
0x18004c75a  jns     short loc_18004C775
0x18004c75c  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c763  cmp     rcx, rsi
0x18004c766  jz      short loc_18004C7B2
0x18004c768  test    byte ptr [rcx+1Ch], 2
0x18004c76c  jz      short loc_18004C7B2
0x18004c76e  mov     edx, 23h ; '#'
0x18004c773  jmp     short loc_18004C7A3
0x18004c775  mov     rcx, [rsp+48h+var_28]
0x18004c77a  call    cs:__imp_FveCommitChanges
0x18004c781  nop     dword ptr [rax+rax+00h]
0x18004c786  mov     ebx, eax
0x18004c788  test    eax, eax
0x18004c78a  jns     short loc_18004C7B2
0x18004c78c  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c793  cmp     rcx, rsi
0x18004c796  jz      short loc_18004C7B2
0x18004c798  test    byte ptr [rcx+1Ch], 2
0x18004c79c  jz      short loc_18004C7B2
0x18004c79e  mov     edx, 24h ; '$'
0x18004c7a3  mov     rcx, [rcx+10h]
0x18004c7a7  mov     r9d, eax
0x18004c7aa  mov     r8, rbp
0x18004c7ad  call    WPP_SF_d
0x18004c7b2  call    cs:__imp_RpcRevertToSelf
0x18004c7b9  nop     dword ptr [rax+rax+00h]
0x18004c7be  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c7c5  cmp     [rsp+48h+var_28], 0FFFFFFFFFFFFFFFFh
0x18004c7cb  jz      short loc_18004C7EE
0x18004c7cd  mov     rcx, [rsp+48h+var_28]
0x18004c7d2  call    cs:__imp_FveCloseVolume
0x18004c7d9  nop     dword ptr [rax+rax+00h]
0x18004c7de  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c7e5  mov     [rsp+48h+var_28], 0FFFFFFFFFFFFFFFFh
0x18004c7ee  cmp     rcx, rsi
0x18004c7f1  jz      short loc_18004C80A
0x18004c7f3  test    byte ptr [rcx+1Ch], 20h
0x18004c7f7  jz      short loc_18004C80A
0x18004c7f9  mov     rcx, [rcx+10h]
0x18004c7fd  mov     edx, 25h ; '%'
0x18004c802  mov     r8, rbp
0x18004c805  call    WPP_SF_
0x18004c80a  mov     eax, ebx
0x18004c80c  mov     rcx, [rsp+48h+var_20]
0x18004c811  xor     rcx, rsp; StackCookie
0x18004c814  call    __security_check_cookie
0x18004c819  mov     rbx, [rsp+48h+arg_0]
0x18004c81e  add     rsp, 30h
0x18004c822  pop     rdi
0x18004c823  pop     rsi
0x18004c824  pop     rbp
0x18004c825  retn
```
