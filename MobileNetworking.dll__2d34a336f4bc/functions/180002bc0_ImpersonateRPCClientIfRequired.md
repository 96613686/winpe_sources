# ImpersonateRPCClientIfRequired

- ea: `0x180002bc0`
- end: `0x180002d02`
- name: `ImpersonateRPCClientIfRequired`
- size: `322`
- prototype: `DWORD __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180002490`

## callees

- `0x180002bc0`
- `0x180008ff0`
- `0x180009130`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180002c11`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180002c11`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180002bf8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180002bf8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002c1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002c1b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002c71`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002c71`
- `RPCRT4!RpcImpersonateClient` at `0x180002c2c`
- `RPCRT4!RpcImpersonateClient` at `0x180002c2c`

## pseudocode

```c
DWORD __fastcall ImpersonateRPCClientIfRequired(_DWORD *a1)
{
  HANDLE CurrentThread; // rax
  DWORD result; // eax
  DWORD v4; // ebx
  PVOID *v5; // rcx
  __int64 v6; // rdx
  void *TokenHandle; // [rsp+38h] [rbp+10h] BYREF

  TokenHandle = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 115, WPP_fd6184a389643c6486807174a58ed414_Traceguids);
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    v4 = 0;
    CloseHandle(TokenHandle);
    goto LABEL_8;
  }
  result = GetLastError();
  v4 = result;
  if ( result != 1008 && result )
  {
    v5 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return result;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_9;
    v6 = 116;
    goto LABEL_19;
  }
  result = RpcImpersonateClient(0);
  v4 = result;
  if ( !result )
  {
    *a1 = 1;
LABEL_8:
    v5 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_9;
  }
  v5 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return result;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v6 = 117;
LABEL_19:
    WPP_SF_L(v5[2], v6, WPP_fd6184a389643c6486807174a58ed414_Traceguids, result);
    goto LABEL_8;
  }
LABEL_9:
  if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 8) != 0 )
    WPP_SF_L(v5[2], 118, WPP_fd6184a389643c6486807174a58ed414_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x180002bc0  mov     [rsp+arg_10], rsi
0x180002bc5  push    rdi
0x180002bc6  sub     rsp, 20h
0x180002bca  mov     rdi, rcx
0x180002bcd  mov     [rsp+28h+TokenHandle], 0
0x180002bd6  mov     rcx, cs:WPP_GLOBAL_Control
0x180002bdd  lea     rsi, WPP_GLOBAL_Control
0x180002be4  cmp     rcx, rsi
0x180002be7  jz      short loc_180002BF3
0x180002be9  test    byte ptr [rcx+1Ch], 8
0x180002bed  jnz     loc_180002C79
0x180002bf3  mov     [rsp+28h+arg_0], rbx
0x180002bf8  call    cs:__imp_GetCurrentThread
0x180002bfe  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x180002c03  mov     edx, 8; DesiredAccess
0x180002c08  mov     rcx, rax; ThreadHandle
0x180002c0b  mov     r8d, 1; OpenAsSelf
0x180002c11  call    cs:__imp_OpenThreadToken
0x180002c17  test    eax, eax
0x180002c19  jnz     short loc_180002C6A
0x180002c1b  call    cs:__imp_GetLastError
0x180002c21  mov     ebx, eax
0x180002c23  cmp     eax, 3F0h
0x180002c28  jnz     short loc_180002C93
0x180002c2a  xor     ecx, ecx; BindingHandle
0x180002c2c  call    cs:__imp_RpcImpersonateClient
0x180002c32  mov     ebx, eax
0x180002c34  test    eax, eax
0x180002c36  jnz     loc_180002CCD
0x180002c3c  mov     dword ptr [rdi], 1
0x180002c42  mov     rcx, cs:WPP_GLOBAL_Control
0x180002c49  cmp     rcx, rsi
0x180002c4c  jz      short loc_180002C58
0x180002c4e  test    byte ptr [rcx+1Ch], 8
0x180002c52  jnz     loc_180002CE5
0x180002c58  mov     eax, ebx
0x180002c5a  mov     rbx, [rsp+28h+arg_0]
0x180002c5f  mov     rsi, [rsp+28h+arg_10]
0x180002c64  add     rsp, 20h
0x180002c68  pop     rdi
0x180002c69  retn
0x180002c6a  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x180002c6f  xor     ebx, ebx
0x180002c71  call    cs:__imp_CloseHandle
0x180002c77  jmp     short loc_180002C42
0x180002c79  mov     rcx, [rcx+10h]
0x180002c7d  lea     r8, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x180002c84  mov     edx, 73h ; 's'
0x180002c89  call    WPP_SF_
0x180002c8e  jmp     loc_180002BF3
0x180002c93  test    eax, eax
0x180002c95  jz      short loc_180002C2A
0x180002c97  mov     rcx, cs:WPP_GLOBAL_Control
0x180002c9e  cmp     rcx, rsi
0x180002ca1  jz      short loc_180002C5A
0x180002ca3  test    byte ptr [rcx+1Ch], 4
0x180002ca7  jz      short loc_180002C49
0x180002ca9  mov     edx, 74h ; 't'
0x180002cae  jmp     short loc_180002CB5
0x180002cb0  mov     edx, 75h ; 'u'
0x180002cb5  mov     rcx, [rcx+10h]
0x180002cb9  lea     r8, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x180002cc0  mov     r9d, eax
0x180002cc3  call    WPP_SF_L
0x180002cc8  jmp     loc_180002C42
0x180002ccd  mov     rcx, cs:WPP_GLOBAL_Control
0x180002cd4  cmp     rcx, rsi
0x180002cd7  jz      short loc_180002C5A
0x180002cd9  test    byte ptr [rcx+1Ch], 4
0x180002cdd  jz      loc_180002C49
0x180002ce3  jmp     short loc_180002CB0
0x180002ce5  mov     rcx, [rcx+10h]
0x180002ce9  lea     r8, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x180002cf0  mov     edx, 76h ; 'v'
0x180002cf5  mov     r9d, ebx
0x180002cf8  call    WPP_SF_L
0x180002cfd  jmp     loc_180002C58
```
