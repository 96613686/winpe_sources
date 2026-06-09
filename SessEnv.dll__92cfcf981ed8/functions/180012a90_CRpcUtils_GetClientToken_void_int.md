# CRpcUtils::GetClientToken(void * *,int)

- ea: `0x180012a90`
- end: `0x180012b80`
- name: `?GetClientToken@CRpcUtils@@SAJPEAPEAXH@Z`
- size: `240`
- prototype: `__int64 __fastcall(void **, int)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180002730`
- `0x180031f00`
- `0x180039bb0`

## callees

- `0x180003f30`
- `0x180012a90`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012aed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012aed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012b63`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012b63`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180012ae3`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180012ae3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180012aca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180012aca`
- `RPCRT4!RpcImpersonateClient` at `0x180012aa8`
- `RPCRT4!RpcImpersonateClient` at `0x180012aa8`
- `RPCRT4!RpcRevertToSelf` at `0x180012b06`
- `RPCRT4!RpcRevertToSelf` at `0x180012b06`

## string_xrefs

- `0x180012ac1`: `RpcImpersonateClient failed: 0x%x in %s`
- `0x180012b42`: `CRpcUtils::GetClientToken`
- `0x180012b3b`: `OpenThreadToken failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CRpcUtils::GetClientToken(void **a1)
{
  RPC_STATUS v2; // eax
  unsigned int v3; // ebx
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  int v6; // eax
  bool v7; // sf
  void *v8; // rax
  void *TokenHandle; // [rsp+40h] [rbp+18h] BYREF

  TokenHandle = 0;
  v2 = RpcImpersonateClient(0);
  v3 = v2;
  if ( v2 > 0 )
    v3 = (unsigned __int16)v2 | 0x80070000;
  if ( (v3 & 0x80000000) == 0 )
  {
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 0xEu, 1, &TokenHandle) )
    {
      v3 = 0;
    }
    else
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
    }
    v6 = RpcRevertToSelf();
    v7 = v6 < 0;
    if ( v6 > 0 )
    {
      v6 = (unsigned __int16)v6 | 0x80070000;
      v7 = v6 < 0;
    }
    if ( v7 )
    {
      _DbgPrintMessage(8, "RpcRevertToSelf failed: 0x%x", v6);
      v3 = -2147024891;
    }
    else
    {
      if ( (v3 & 0x80000000) == 0 )
      {
        v8 = TokenHandle;
        goto LABEL_18;
      }
      _DbgPrintMessage(8, "OpenThreadToken failed: 0x%x in %s", v3, "CRpcUtils::GetClientToken");
    }
  }
  else
  {
    _DbgPrintMessage(8, "RpcImpersonateClient failed: 0x%x in %s", v3, "CRpcUtils::GetClientToken");
  }
  v8 = TokenHandle;
  if ( !TokenHandle )
  {
LABEL_18:
    *a1 = v8;
    return v3;
  }
  CloseHandle(TokenHandle);
  return v3;
}

```

## disassembly

```asm
0x180012a90  mov     [rsp+arg_0], rbx
0x180012a95  push    rdi
0x180012a96  sub     rsp, 20h
0x180012a9a  mov     rdi, rcx
0x180012a9d  mov     [rsp+28h+TokenHandle], 0
0x180012aa6  xor     ecx, ecx; BindingHandle
0x180012aa8  call    cs:__imp_RpcImpersonateClient
0x180012aae  mov     ebx, eax
0x180012ab0  test    eax, eax
0x180012ab2  jle     short loc_180012ABD
0x180012ab4  movzx   ebx, ax
0x180012ab7  or      ebx, 80070000h
0x180012abd  test    ebx, ebx
0x180012abf  jns     short loc_180012ACA
0x180012ac1  lea     rdx, aRpcimpersonate_0; "RpcImpersonateClient failed: 0x%x in %s"
0x180012ac8  jmp     short loc_180012B42
0x180012aca  call    cs:__imp_GetCurrentThread
0x180012ad0  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x180012ad5  mov     edx, 0Eh; DesiredAccess
0x180012ada  mov     rcx, rax; ThreadHandle
0x180012add  mov     r8d, 1; OpenAsSelf
0x180012ae3  call    cs:__imp_OpenThreadToken
0x180012ae9  test    eax, eax
0x180012aeb  jnz     short loc_180012B04
0x180012aed  call    cs:__imp_GetLastError
0x180012af3  mov     ebx, eax
0x180012af5  test    eax, eax
0x180012af7  jle     short loc_180012B06
0x180012af9  movzx   ebx, ax
0x180012afc  or      ebx, 80070000h
0x180012b02  jmp     short loc_180012B06
0x180012b04  xor     ebx, ebx
0x180012b06  call    cs:__imp_RpcRevertToSelf
0x180012b0c  test    eax, eax
0x180012b0e  jle     short loc_180012B1A
0x180012b10  movzx   eax, ax
0x180012b13  or      eax, 80070000h
0x180012b18  test    eax, eax
0x180012b1a  jns     short loc_180012B37
0x180012b1c  mov     r8d, eax
0x180012b1f  lea     rdx, aRpcreverttosel_1; "RpcRevertToSelf failed: 0x%x"
0x180012b26  mov     ecx, 8; int
0x180012b2b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180012b30  mov     ebx, 80070005h
0x180012b35  jmp     short loc_180012B56
0x180012b37  test    ebx, ebx
0x180012b39  jns     short loc_180012B6B
0x180012b3b  lea     rdx, aOpenthreadtoke; "OpenThreadToken failed: 0x%x in %s"
0x180012b42  lea     r9, aCrpcutilsGetcl_0; "CRpcUtils::GetClientToken"
0x180012b49  mov     r8d, ebx
0x180012b4c  mov     ecx, 8; int
0x180012b51  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180012b56  mov     rax, [rsp+28h+TokenHandle]
0x180012b5b  test    rax, rax
0x180012b5e  jz      short loc_180012B70
0x180012b60  mov     rcx, rax; hObject
0x180012b63  call    cs:__imp_CloseHandle
0x180012b69  jmp     short loc_180012B73
0x180012b6b  mov     rax, [rsp+28h+TokenHandle]
0x180012b70  mov     [rdi], rax
0x180012b73  mov     eax, ebx
0x180012b75  mov     rbx, [rsp+28h+arg_0]
0x180012b7a  add     rsp, 20h
0x180012b7e  pop     rdi
0x180012b7f  retn
```
