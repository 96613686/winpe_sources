# GetRpcClientThreadToken(ulong,void * *)

- ea: `0x180005170`
- end: `0x180005204`
- name: `?GetRpcClientThreadToken@@YAJKPEAPEAX@Z`
- size: `148`
- prototype: `RPC_STATUS __fastcall(DWORD DesiredAccess, PHANDLE TokenHandle)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x180005170`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x180005186`
- `RPCRT4!RpcImpersonateClient` at `0x180005186`
- `RPCRT4!RpcRevertToSelf` at `0x1800051de`
- `RPCRT4!RpcRevertToSelf` at `0x1800051ec`
- `RPCRT4!RpcRevertToSelf` at `0x1800051de`
- `RPCRT4!RpcRevertToSelf` at `0x1800051ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800051c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800051c5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800051a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800051a7`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800051bb`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800051bb`

## pseudocode

```c
RPC_STATUS __fastcall GetRpcClientThreadToken(DWORD DesiredAccess, PHANDLE TokenHandle)
{
  RPC_STATUS result; // eax
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  unsigned int v7; // edi

  result = RpcImpersonateClient(0);
  if ( result )
  {
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  else
  {
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, DesiredAccess, 1, TokenHandle) )
    {
      RpcRevertToSelf();
      return 0;
    }
    else
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      RpcRevertToSelf();
      return v7;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180005170  mov     [rsp+arg_0], rbx
0x180005175  mov     [rsp+arg_8], rsi
0x18000517a  push    rdi
0x18000517b  sub     rsp, 20h
0x18000517f  mov     esi, ecx
0x180005181  mov     rdi, rdx
0x180005184  xor     ecx, ecx; BindingHandle
0x180005186  call    cs:__imp_RpcImpersonateClient
0x18000518c  test    eax, eax
0x18000518e  jz      short loc_1800051A2
0x180005190  jle     short loc_18000519A
0x180005192  movzx   eax, ax
0x180005195  or      eax, 80070000h
0x18000519a  xor     ebx, ebx
0x18000519c  test    eax, eax
0x18000519e  jns     short loc_1800051A7
0x1800051a0  jmp     short loc_1800051F4
0x1800051a2  mov     ebx, 1
0x1800051a7  call    cs:__imp_GetCurrentThread
0x1800051ad  mov     r9, rdi; TokenHandle
0x1800051b0  mov     r8d, 1; OpenAsSelf
0x1800051b6  mov     rcx, rax; ThreadHandle
0x1800051b9  mov     edx, esi; DesiredAccess
0x1800051bb  call    cs:__imp_OpenThreadToken
0x1800051c1  test    eax, eax
0x1800051c3  jnz     short loc_1800051E8
0x1800051c5  call    cs:__imp_GetLastError
0x1800051cb  mov     edi, eax
0x1800051cd  test    eax, eax
0x1800051cf  jle     short loc_1800051DA
0x1800051d1  movzx   edi, ax
0x1800051d4  or      edi, 80070000h
0x1800051da  test    ebx, ebx
0x1800051dc  jz      short loc_1800051E4
0x1800051de  call    cs:__imp_RpcRevertToSelf
0x1800051e4  mov     eax, edi
0x1800051e6  jmp     short loc_1800051F4
0x1800051e8  test    ebx, ebx
0x1800051ea  jz      short loc_1800051F2
0x1800051ec  call    cs:__imp_RpcRevertToSelf
0x1800051f2  xor     eax, eax
0x1800051f4  mov     rbx, [rsp+28h+arg_0]
0x1800051f9  mov     rsi, [rsp+28h+arg_8]
0x1800051fe  add     rsp, 20h
0x180005202  pop     rdi
0x180005203  retn
```
