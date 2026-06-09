# TsiCheckCallerCapabilities(ushort const *)

- ea: `0x18001ffc0`
- end: `0x180020055`
- name: `?TsiCheckCallerCapabilities@@YAJPEBG@Z`
- size: `149`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `5`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180001bd0`
- `0x180001dd0`
- `0x180002c80`
- `0x180018dac`
- `0x18001910c`

## callees

- `0x18000dac0`
- `0x18001ffc0`

## import_xrefs

- `RPCRT4!RpcRevertToSelfEx` at `0x180020033`
- `RPCRT4!RpcRevertToSelfEx` at `0x180020033`
- `RPCRT4!RpcImpersonateClient` at `0x18001ffe5`
- `RPCRT4!RpcImpersonateClient` at `0x18001ffe5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002001c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002001c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180020012`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180020012`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001fffb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001fffb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020047`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020047`

## pseudocode

```c
RPC_STATUS __fastcall TsiCheckCallerCapabilities(const unsigned __int16 *a1)
{
  int RPCClientToken; // ebx
  RPC_STATUS result; // eax
  bool v3; // cc
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  void *TokenHandle; // [rsp+30h] [rbp+8h] BYREF

  TokenHandle = 0;
  RPCClientToken = TsiGetRPCClientToken(&TokenHandle);
  if ( RPCClientToken < 0 )
    goto LABEL_9;
  result = RpcImpersonateClient(0);
  v3 = result <= 0;
  if ( result )
    goto LABEL_3;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    LastError = GetLastError();
    RPCClientToken = LastError;
    if ( LastError > 0 )
      RPCClientToken = (unsigned __int16)LastError | 0x80070000;
  }
  result = RpcRevertToSelfEx(0);
  v3 = result <= 0;
  if ( result )
  {
LABEL_3:
    if ( !v3 )
      return (unsigned __int16)result | 0x80070000;
  }
  else
  {
LABEL_9:
    if ( TokenHandle )
      CloseHandle(TokenHandle);
    return RPCClientToken;
  }
  return result;
}

```

## disassembly

```asm
0x18001ffc0  mov     [rsp+TokenHandle], rcx
0x18001ffc5  push    rbx
0x18001ffc6  sub     rsp, 20h
0x18001ffca  lea     rcx, [rsp+28h+TokenHandle]
0x18001ffcf  mov     [rsp+28h+TokenHandle], 0
0x18001ffd8  call    TsiGetRPCClientToken
0x18001ffdd  mov     ebx, eax
0x18001ffdf  test    eax, eax
0x18001ffe1  js      short loc_18002003D
0x18001ffe3  xor     ecx, ecx; BindingHandle
0x18001ffe5  call    cs:__imp_RpcImpersonateClient
0x18001ffeb  test    eax, eax
0x18001ffed  jz      short loc_18001FFFB
0x18001ffef  jle     short loc_18002004F
0x18001fff1  movzx   eax, ax
0x18001fff4  or      eax, 80070000h
0x18001fff9  jmp     short loc_18002004F
0x18001fffb  call    cs:__imp_GetCurrentThread
0x180020001  mov     edx, 8; DesiredAccess
0x180020006  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x18002000b  mov     rcx, rax; ThreadHandle
0x18002000e  lea     r8d, [rdx-7]; OpenAsSelf
0x180020012  call    cs:__imp_OpenThreadToken
0x180020018  test    eax, eax
0x18002001a  jnz     short loc_180020031
0x18002001c  call    cs:__imp_GetLastError
0x180020022  mov     ebx, eax
0x180020024  test    eax, eax
0x180020026  jle     short loc_180020031
0x180020028  movzx   ebx, ax
0x18002002b  or      ebx, 80070000h
0x180020031  xor     ecx, ecx; BindingHandle
0x180020033  call    cs:__imp_RpcRevertToSelfEx
0x180020039  test    eax, eax
0x18002003b  jnz     short loc_18001FFEF
0x18002003d  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x180020042  test    rcx, rcx
0x180020045  jz      short loc_18002004D
0x180020047  call    cs:__imp_CloseHandle
0x18002004d  mov     eax, ebx
0x18002004f  add     rsp, 20h
0x180020053  pop     rbx
0x180020054  retn
```
