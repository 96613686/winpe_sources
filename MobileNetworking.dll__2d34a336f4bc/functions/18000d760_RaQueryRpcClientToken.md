# RaQueryRpcClientToken

- ea: `0x18000d760`
- end: `0x18000d858`
- name: `RaQueryRpcClientToken`
- size: `248`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18000cfe0`

## callees

- `0x18000d760`
- `0x18000d860`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000d7cd`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000d7cd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000d7b4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000d7b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d7de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d7de`
- `RPCRT4!RpcRevertToSelfEx` at `0x18000d819`
- `RPCRT4!RpcRevertToSelfEx` at `0x18000d819`
- `RPCRT4!RpcImpersonateClient` at `0x18000d77d`
- `RPCRT4!RpcImpersonateClient` at `0x18000d77d`

## pseudocode

```c
__int64 __fastcall RaQueryRpcClientToken(void **a1)
{
  unsigned int v2; // eax
  __int64 v3; // r8
  unsigned int v4; // ebx
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  __int64 v9; // r8
  void *TokenHandle; // [rsp+38h] [rbp+10h] BYREF

  TokenHandle = 0;
  v2 = RpcImpersonateClient(0);
  v4 = v2;
  if ( v2 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v6 = 16;
LABEL_15:
      WPP_SF_D(v5[2], v6, v3, v2);
    }
  }
  else
  {
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 0xF01FFu, 1, &TokenHandle)
      || (LastError = GetLastError(), (v4 = LastError) == 0) )
    {
      *a1 = TokenHandle;
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, v9, LastError);
    }
    v2 = RpcRevertToSelfEx(0);
    if ( v2 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v6 = 18;
        goto LABEL_15;
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18000d760  mov     [rsp+arg_0], rbx
0x18000d765  mov     [rsp+arg_10], rsi
0x18000d76a  push    rdi
0x18000d76b  sub     rsp, 20h
0x18000d76f  mov     rsi, rcx
0x18000d772  mov     [rsp+28h+TokenHandle], 0
0x18000d77b  xor     ecx, ecx; BindingHandle
0x18000d77d  call    cs:__imp_RpcImpersonateClient
0x18000d783  mov     ebx, eax
0x18000d785  test    eax, eax
0x18000d787  jz      short loc_18000D7B4
0x18000d789  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d790  lea     rdi, WPP_GLOBAL_Control
0x18000d797  cmp     rcx, rdi
0x18000d79a  jz      loc_18000D846
0x18000d7a0  test    byte ptr [rcx+1Ch], 4
0x18000d7a4  jz      loc_18000D846
0x18000d7aa  mov     edx, 10h
0x18000d7af  jmp     loc_18000D83A
0x18000d7b4  call    cs:__imp_GetCurrentThread
0x18000d7ba  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x18000d7bf  mov     edx, 0F01FFh; DesiredAccess
0x18000d7c4  mov     rcx, rax; ThreadHandle
0x18000d7c7  mov     r8d, 1; OpenAsSelf
0x18000d7cd  call    cs:__imp_OpenThreadToken
0x18000d7d3  lea     rdi, WPP_GLOBAL_Control
0x18000d7da  test    eax, eax
0x18000d7dc  jnz     short loc_18000D80F
0x18000d7de  call    cs:__imp_GetLastError
0x18000d7e4  mov     ebx, eax
0x18000d7e6  test    eax, eax
0x18000d7e8  jz      short loc_18000D80F
0x18000d7ea  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d7f1  cmp     rcx, rdi
0x18000d7f4  jz      short loc_18000D817
0x18000d7f6  test    byte ptr [rcx+1Ch], 4
0x18000d7fa  jz      short loc_18000D817
0x18000d7fc  mov     rcx, [rcx+10h]
0x18000d800  mov     edx, 11h
0x18000d805  mov     r9d, eax
0x18000d808  call    WPP_SF_D
0x18000d80d  jmp     short loc_18000D817
0x18000d80f  mov     rax, [rsp+28h+TokenHandle]
0x18000d814  mov     [rsi], rax
0x18000d817  xor     ecx, ecx; BindingHandle
0x18000d819  call    cs:__imp_RpcRevertToSelfEx
0x18000d81f  test    eax, eax
0x18000d821  jz      short loc_18000D846
0x18000d823  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d82a  cmp     rcx, rdi
0x18000d82d  jz      short loc_18000D846
0x18000d82f  test    byte ptr [rcx+1Ch], 4
0x18000d833  jz      short loc_18000D846
0x18000d835  mov     edx, 12h
0x18000d83a  mov     rcx, [rcx+10h]
0x18000d83e  mov     r9d, eax
0x18000d841  call    WPP_SF_D
0x18000d846  mov     rsi, [rsp+28h+arg_10]
0x18000d84b  mov     eax, ebx
0x18000d84d  mov     rbx, [rsp+28h+arg_0]
0x18000d852  add     rsp, 20h
0x18000d856  pop     rdi
0x18000d857  retn
```
