# WitnessUpcallServerSecurityCallback

- ea: `0x180031dc0`
- end: `0x180031f50`
- name: `WitnessUpcallServerSecurityCallback`
- size: `400`
- prototype: `RPC_IF_CALLBACK_FN`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180022b54`
- `0x180022b7c`
- `0x180031dc0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031e88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031ead`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031e88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031ead`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180031ea3`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180031ea3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031f08`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031f08`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180031e32`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180031e32`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180031e49`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180031e49`
- `RPCRT4!RpcImpersonateClient` at `0x180031de1`
- `RPCRT4!RpcImpersonateClient` at `0x180031de1`
- `RPCRT4!RpcRevertToSelf` at `0x180031e51`
- `RPCRT4!RpcRevertToSelf` at `0x180031e51`

## pseudocode

```c
__int64 __fastcall WitnessUpcallServerSecurityCallback(RPC_IF_HANDLE InterfaceUuid, void *Context)
{
  unsigned int LastError; // ebx
  PVOID *v3; // rcx
  __int64 v4; // rdx
  HANDLE CurrentThread; // rax
  BOOL v6; // edi
  DWORD v7; // eax
  WINBOOL IsMember; // [rsp+40h] [rbp+18h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp+20h] BYREF

  TokenHandle = 0;
  IsMember = 1;
  LastError = RpcImpersonateClient(0);
  if ( LastError )
  {
    v3 = (PVOID *)WPP_witness_GLOBAL_Control;
    if ( WPP_witness_GLOBAL_Control != &WPP_witness_GLOBAL_Control
      && (*((_BYTE *)WPP_witness_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_witness_GLOBAL_Control + 25) )
    {
      v4 = 10;
LABEL_6:
      WPP_SF_(v3[2], v4, WPP_25b73f0a37193b70b6a932c4d871ce72_Traceguids);
LABEL_20:
      v3 = (PVOID *)WPP_witness_GLOBAL_Control;
    }
  }
  else
  {
    CurrentThread = GetCurrentThread();
    v6 = OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle);
    LastError = RpcRevertToSelf();
    if ( LastError )
    {
      v3 = (PVOID *)WPP_witness_GLOBAL_Control;
      if ( WPP_witness_GLOBAL_Control != &WPP_witness_GLOBAL_Control
        && (*((_BYTE *)WPP_witness_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_witness_GLOBAL_Control + 25) )
      {
        v4 = 11;
        goto LABEL_6;
      }
    }
    else
    {
      if ( !v6 )
      {
        LastError = GetLastError();
        goto LABEL_20;
      }
      if ( CheckTokenMembership(TokenHandle, LocalSystem, &IsMember) )
      {
        LastError = IsMember != 1 ? 5 : 0;
        goto LABEL_20;
      }
      v7 = GetLastError();
      LastError = v7;
      v3 = (PVOID *)WPP_witness_GLOBAL_Control;
      if ( WPP_witness_GLOBAL_Control != &WPP_witness_GLOBAL_Control
        && (*((_BYTE *)WPP_witness_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_witness_GLOBAL_Control + 25) )
      {
        WPP_SF_d(*((_QWORD *)WPP_witness_GLOBAL_Control + 2), 12, WPP_25b73f0a37193b70b6a932c4d871ce72_Traceguids, v7);
        goto LABEL_20;
      }
    }
  }
  if ( TokenHandle )
  {
    CloseHandle(TokenHandle);
    v3 = (PVOID *)WPP_witness_GLOBAL_Control;
  }
  if ( v3 != &WPP_witness_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 1) != 0 && *((_BYTE *)v3 + 25) >= 3u )
    WPP_SF_d(v3[2], 13, WPP_25b73f0a37193b70b6a932c4d871ce72_Traceguids, LastError);
  return LastError;
}

```

## disassembly

```asm
0x180031dc0  mov     rax, rsp
0x180031dc3  mov     [rax+8], rbx
0x180031dc7  mov     [rax+10h], rbp
0x180031dcb  push    rdi
0x180031dcc  sub     rsp, 20h
0x180031dd0  xor     ecx, ecx; BindingHandle
0x180031dd2  mov     qword ptr [rax+20h], 0
0x180031dda  mov     dword ptr [rax+18h], 1
0x180031de1  call    cs:__imp_RpcImpersonateClient
0x180031de7  lea     rbp, WPP_witness_GLOBAL_Control
0x180031dee  mov     ebx, eax
0x180031df0  test    eax, eax
0x180031df2  jz      short loc_180031E32
0x180031df4  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x180031dfb  cmp     rcx, rbp
0x180031dfe  jz      loc_180031EFB
0x180031e04  test    byte ptr [rcx+1Ch], 1
0x180031e08  jz      loc_180031EFB
0x180031e0e  cmp     byte ptr [rcx+19h], 1
0x180031e12  jb      loc_180031EFB
0x180031e18  mov     edx, 0Ah
0x180031e1d  mov     rcx, [rcx+10h]
0x180031e21  lea     r8, WPP_25b73f0a37193b70b6a932c4d871ce72_Traceguids
0x180031e28  call    WPP_SF_
0x180031e2d  jmp     loc_180031EF4
0x180031e32  call    cs:__imp_GetCurrentThread
0x180031e38  mov     edx, 8; DesiredAccess
0x180031e3d  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x180031e42  mov     rcx, rax; ThreadHandle
0x180031e45  lea     r8d, [rdx-7]; OpenAsSelf
0x180031e49  call    cs:__imp_OpenThreadToken
0x180031e4f  mov     edi, eax
0x180031e51  call    cs:__imp_RpcRevertToSelf
0x180031e57  mov     ebx, eax
0x180031e59  test    eax, eax
0x180031e5b  jz      short loc_180031E84
0x180031e5d  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x180031e64  cmp     rcx, rbp
0x180031e67  jz      loc_180031EFB
0x180031e6d  test    byte ptr [rcx+1Ch], 1
0x180031e71  jz      loc_180031EFB
0x180031e77  cmp     byte ptr [rcx+19h], 1
0x180031e7b  jb      short loc_180031EFB
0x180031e7d  mov     edx, 0Bh
0x180031e82  jmp     short loc_180031E1D
0x180031e84  test    edi, edi
0x180031e86  jnz     short loc_180031E92
0x180031e88  call    cs:__imp_GetLastError
0x180031e8e  mov     ebx, eax
0x180031e90  jmp     short loc_180031EF4
0x180031e92  mov     rcx, [rsp+28h+TokenHandle]; TokenHandle
0x180031e97  lea     r8, [rsp+28h+IsMember]; IsMember
0x180031e9c  lea     rdx, LocalSystem; SidToCheck
0x180031ea3  call    cs:__imp_CheckTokenMembership
0x180031ea9  test    eax, eax
0x180031eab  jnz     short loc_180031EE7
0x180031ead  call    cs:__imp_GetLastError
0x180031eb3  mov     ebx, eax
0x180031eb5  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x180031ebc  cmp     rcx, rbp
0x180031ebf  jz      short loc_180031EFB
0x180031ec1  test    byte ptr [rcx+1Ch], 1
0x180031ec5  jz      short loc_180031EFB
0x180031ec7  cmp     byte ptr [rcx+19h], 1
0x180031ecb  jb      short loc_180031EFB
0x180031ecd  mov     rcx, [rcx+10h]
0x180031ed1  lea     r8, WPP_25b73f0a37193b70b6a932c4d871ce72_Traceguids
0x180031ed8  mov     edx, 0Ch
0x180031edd  mov     r9d, eax
0x180031ee0  call    WPP_SF_d
0x180031ee5  jmp     short loc_180031EF4
0x180031ee7  mov     eax, [rsp+28h+IsMember]
0x180031eeb  dec     eax
0x180031eed  neg     eax
0x180031eef  sbb     ebx, ebx
0x180031ef1  and     ebx, 5
0x180031ef4  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x180031efb  mov     rax, [rsp+28h+TokenHandle]
0x180031f00  test    rax, rax
0x180031f03  jz      short loc_180031F15
0x180031f05  mov     rcx, rax; hObject
0x180031f08  call    cs:__imp_CloseHandle
0x180031f0e  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x180031f15  cmp     rcx, rbp
0x180031f18  jz      short loc_180031F3E
0x180031f1a  test    byte ptr [rcx+1Ch], 1
0x180031f1e  jz      short loc_180031F3E
0x180031f20  cmp     byte ptr [rcx+19h], 3
0x180031f24  jb      short loc_180031F3E
0x180031f26  mov     rcx, [rcx+10h]
0x180031f2a  lea     r8, WPP_25b73f0a37193b70b6a932c4d871ce72_Traceguids
0x180031f31  mov     edx, 0Dh
0x180031f36  mov     r9d, ebx
0x180031f39  call    WPP_SF_d
0x180031f3e  mov     rbp, [rsp+28h+arg_8]
0x180031f43  mov     eax, ebx
0x180031f45  mov     rbx, [rsp+28h+arg_0]
0x180031f4a  add     rsp, 20h
0x180031f4e  pop     rdi
0x180031f4f  retn
```
