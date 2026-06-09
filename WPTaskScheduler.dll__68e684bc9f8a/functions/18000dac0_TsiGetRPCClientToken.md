# TsiGetRPCClientToken

- ea: `0x18000dac0`
- end: `0x18000db4c`
- name: `TsiGetRPCClientToken`
- size: `140`
- prototype: `RPC_STATUS __fastcall(void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18001ffc0`

## callees

- `0x18000dac0`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x18000dacb`
- `RPCRT4!RpcImpersonateClient` at `0x18000dacb`
- `RPCRT4!RpcRevertToSelf` at `0x18000db01`
- `RPCRT4!RpcRevertToSelf` at `0x18000db2f`
- `RPCRT4!RpcRevertToSelf` at `0x18000db01`
- `RPCRT4!RpcRevertToSelf` at `0x18000db2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000db27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000db27`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000daf7`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000daf7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000dade`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000dade`

## pseudocode

```c
RPC_STATUS __fastcall TsiGetRPCClientToken(void **a1)
{
  RPC_STATUS result; // eax
  bool v3; // cc
  HANDLE CurrentThread; // rax
  signed int LastError; // ebx
  void *TokenHandle; // [rsp+38h] [rbp+10h] BYREF

  result = RpcImpersonateClient(0);
  v3 = result <= 0;
  if ( result )
  {
LABEL_6:
    if ( !v3 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    result = RpcRevertToSelf();
    v3 = result <= 0;
    if ( !result )
    {
      *a1 = TokenHandle;
      return 0;
    }
    goto LABEL_6;
  }
  LastError = GetLastError();
  RpcRevertToSelf();
  if ( LastError > 0 )
    return (unsigned __int16)LastError | 0x80070000;
  return LastError;
}

```

## disassembly

```asm
0x18000dac0  push    rbx
0x18000dac2  sub     rsp, 20h
0x18000dac6  mov     rbx, rcx
0x18000dac9  xor     ecx, ecx; BindingHandle
0x18000dacb  call    cs:__imp_RpcImpersonateClient
0x18000dad1  test    eax, eax
0x18000dad3  jnz     short loc_18000DB1B
0x18000dad5  mov     [rsp+28h+TokenHandle], 0
0x18000dade  call    cs:__imp_GetCurrentThread
0x18000dae4  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x18000dae9  mov     edx, 8; DesiredAccess
0x18000daee  mov     rcx, rax; ThreadHandle
0x18000daf1  mov     r8d, 1; OpenAsSelf
0x18000daf7  call    cs:__imp_OpenThreadToken
0x18000dafd  test    eax, eax
0x18000daff  jz      short loc_18000DB27
0x18000db01  call    cs:__imp_RpcRevertToSelf
0x18000db07  test    eax, eax
0x18000db09  jnz     short loc_18000DB1B
0x18000db0b  mov     rax, [rsp+28h+TokenHandle]
0x18000db10  mov     [rbx], rax
0x18000db13  xor     eax, eax
0x18000db15  add     rsp, 20h
0x18000db19  pop     rbx
0x18000db1a  retn
0x18000db1b  jle     short loc_18000DB15
0x18000db1d  movzx   eax, ax
0x18000db20  or      eax, 80070000h
0x18000db25  jmp     short loc_18000DB15
0x18000db27  call    cs:__imp_GetLastError
0x18000db2d  mov     ebx, eax
0x18000db2f  call    cs:__imp_RpcRevertToSelf
0x18000db35  test    ebx, ebx
0x18000db37  jg      short loc_18000DB41
0x18000db39  mov     eax, ebx
0x18000db3b  add     rsp, 20h
0x18000db3f  pop     rbx
0x18000db40  retn
0x18000db41  movzx   ebx, bx
0x18000db44  or      ebx, 80070000h
0x18000db4a  jmp     short loc_18000DB39
```
