# SecurityValidator<1>::CheckPermissionForOperation(ushort const *)

- ea: `0x180003608`
- end: `0x180003720`
- name: `?CheckPermissionForOperation@?$SecurityValidator@$00@@CAJPEBG@Z`
- size: `280`
- prototype: `__int64()`
- caller_count: `21`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800038d0`
- `0x180003da0`
- `0x180004250`
- `0x180004860`
- `0x180004ec0`
- `0x180006e70`
- `0x180007190`
- `0x180007280`
- `0x1800073d0`
- `0x1800074b0`
- `0x180007640`
- `0x180007780`
- `0x180007a80`
- `0x180007c40`
- `0x180007e40`
- `0x1800081c0`
- `0x180008440`
- `0x180008520`
- `0x180008880`
- `0x180008970`
- `0x180008a60`

## callees

- `0x180003608`
- `0x1800126a0`
- `0x180066db2`
- `0x180066df0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003664`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003664`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000369a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000369a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180003683`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180003683`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800036ca`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800036ca`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180003670`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180003670`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800036a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800036a4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800036ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800036ff`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x180003653`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x180003653`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 SecurityValidator<1>::CheckPermissionForOperation()
{
  RPC_STATUS v0; // eax
  HRESULT v1; // eax
  signed int v2; // ebx
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  SecurityFuncHelper *v5; // rcx
  int v6; // eax
  unsigned int v7; // eax
  void *TokenHandle; // [rsp+20h] [rbp-A8h] BYREF
  _DWORD RpcCallAttributes[2]; // [rsp+30h] [rbp-98h] BYREF
  _BYTE v11[56]; // [rsp+38h] [rbp-90h] BYREF
  int v12; // [rsp+70h] [rbp-58h]

  TokenHandle = 0;
  memset_0(v11, 0, 0x70u);
  RpcCallAttributes[0] = 3;
  RpcCallAttributes[1] = 16;
  v0 = RpcServerInqCallAttributesW(0, RpcCallAttributes);
  if ( v0 != 1725 && (v0 || v12 != GetCurrentProcessId()) )
  {
    v1 = CoImpersonateClient();
    v2 = v1;
    if ( v1 == -2147417833 )
      goto LABEL_19;
    if ( v1 < 0 )
      goto LABEL_20;
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    {
      LastError = GetLastError();
      if ( LastError )
      {
        if ( LastError > 0 )
          v2 = (unsigned __int16)LastError | 0x80070000;
        else
          v2 = LastError;
        goto LABEL_20;
      }
    }
    if ( v2 < 0 )
      goto LABEL_20;
    if ( v2 == 1 )
      goto LABEL_19;
  }
  CoRevertToSelf();
  v6 = SecurityFuncHelper::CheckAndInit(v5);
  if ( v6 >= 0 )
  {
LABEL_19:
    v2 = 0;
    goto LABEL_20;
  }
  v2 = (unsigned __int16)v6;
  v7 = (unsigned __int16)v6 | 0xC0070000;
  if ( v2 )
    v2 = v7;
  if ( v2 >= 0 )
    v2 = -2147024891;
LABEL_20:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180003608  push    rbx
0x18000360a  sub     rsp, 0C0h
0x180003611  mov     rax, cs:__security_cookie
0x180003618  xor     rax, rsp
0x18000361b  mov     [rsp+0C8h+var_18], rax
0x180003623  mov     [rsp+0C8h+TokenHandle], 0
0x18000362c  xor     edx, edx; Val
0x18000362e  lea     r8d, [rdx+70h]; Size
0x180003632  lea     rcx, [rsp+0C8h+var_90]; void *
0x180003637  call    memset_0
0x18000363c  mov     [rsp+0C8h+RpcCallAttributes], 3
0x180003644  mov     [rsp+0C8h+var_94], 10h
0x18000364c  lea     rdx, [rsp+0C8h+RpcCallAttributes]; RpcCallAttributes
0x180003651  xor     ecx, ecx; ClientBinding
0x180003653  call    cs:__imp_RpcServerInqCallAttributesW
0x180003659  cmp     eax, 6BDh
0x18000365e  jz      short loc_1800036CA
0x180003660  test    eax, eax
0x180003662  jnz     short loc_180003670
0x180003664  call    cs:__imp_GetCurrentProcessId
0x18000366a  cmp     [rsp+0C8h+var_58], eax
0x18000366e  jz      short loc_1800036CA
0x180003670  call    cs:__imp_CoImpersonateClient
0x180003676  mov     ebx, eax
0x180003678  cmp     eax, 80010117h
0x18000367d  jz      short loc_1800036F3
0x18000367f  test    eax, eax
0x180003681  js      short loc_1800036F5
0x180003683  call    cs:__imp_GetCurrentThread
0x180003689  lea     r9, [rsp+0C8h+TokenHandle]; TokenHandle
0x18000368e  mov     edx, 8; DesiredAccess
0x180003693  lea     r8d, [rdx-7]; OpenAsSelf
0x180003697  mov     rcx, rax; ThreadHandle
0x18000369a  call    cs:__imp_OpenThreadToken
0x1800036a0  test    eax, eax
0x1800036a2  jnz     short loc_1800036C1
0x1800036a4  call    cs:__imp_GetLastError
0x1800036aa  test    eax, eax
0x1800036ac  jz      short loc_1800036C1
0x1800036ae  jg      short loc_1800036B4
0x1800036b0  mov     ebx, eax
0x1800036b2  jmp     short loc_1800036BD
0x1800036b4  movzx   ebx, ax
0x1800036b7  or      ebx, 80070000h
0x1800036bd  test    ebx, ebx
0x1800036bf  js      short loc_1800036F5
0x1800036c1  test    ebx, ebx
0x1800036c3  js      short loc_1800036F5
0x1800036c5  cmp     ebx, 1
0x1800036c8  jz      short loc_1800036F3
0x1800036ca  call    cs:__imp_CoRevertToSelf
0x1800036d0  call    ?CheckAndInit@SecurityFuncHelper@@AEAAJXZ; SecurityFuncHelper::CheckAndInit(void)
0x1800036d5  test    eax, eax
0x1800036d7  jns     short loc_1800036F3
0x1800036d9  movzx   ebx, ax
0x1800036dc  mov     eax, ebx
0x1800036de  or      eax, 0C0070000h
0x1800036e3  test    ebx, ebx
0x1800036e5  cmovnz  ebx, eax
0x1800036e8  test    ebx, ebx
0x1800036ea  js      short loc_1800036F5
0x1800036ec  mov     ebx, 80070005h
0x1800036f1  jmp     short loc_1800036F5
0x1800036f3  xor     ebx, ebx
0x1800036f5  mov     rcx, [rsp+0C8h+TokenHandle]; hObject
0x1800036fa  test    rcx, rcx
0x1800036fd  jz      short loc_180003705
0x1800036ff  call    cs:__imp_CloseHandle
0x180003705  mov     eax, ebx
0x180003707  mov     rcx, [rsp+0C8h+var_18]
0x18000370f  xor     rcx, rsp; StackCookie
0x180003712  call    __security_check_cookie
0x180003717  add     rsp, 0C0h
0x18000371e  pop     rbx
0x18000371f  retn
```
