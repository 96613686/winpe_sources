# SecurityValidator<1>::CheckPermissionForOperation(ushort const *)

- ea: `0x1800036b8`
- end: `0x18000380d`
- name: `?CheckPermissionForOperation@?$SecurityValidator@$00@@CAJPEBG@Z`
- size: `341`
- prototype: ``
- caller_count: `21`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800039e0`
- `0x180003ec0`
- `0x180004380`
- `0x1800049f0`
- `0x180005070`
- `0x1800070f0`
- `0x180007430`
- `0x180007520`
- `0x180007670`
- `0x180007760`
- `0x1800078f0`
- `0x180007a30`
- `0x180007d30`
- `0x180007f00`
- `0x180008100`
- `0x180008490`
- `0x180008720`
- `0x180008800`
- `0x180008b60`
- `0x180008c60`
- `0x180008d60`

## callees

- `0x1800036b8`
- `0x180012fbc`
- `0x18006c8d2`
- `0x18006c910`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000371e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000371e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000376e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000376e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180003751`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180003751`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800037aa`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800037aa`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180003730`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180003730`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000377e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000377e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800037e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800037e5`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x180003703`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x180003703`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x1800036b8  push    rbx
0x1800036ba  sub     rsp, 0C0h
0x1800036c1  mov     rax, cs:__security_cookie
0x1800036c8  xor     rax, rsp
0x1800036cb  mov     [rsp+0C8h+var_18], rax
0x1800036d3  mov     [rsp+0C8h+TokenHandle], 0
0x1800036dc  xor     edx, edx; Val
0x1800036de  lea     r8d, [rdx+70h]; Size
0x1800036e2  lea     rcx, [rsp+0C8h+var_90]; void *
0x1800036e7  call    memset_0
0x1800036ec  mov     [rsp+0C8h+RpcCallAttributes], 3
0x1800036f4  mov     [rsp+0C8h+var_94], 10h
0x1800036fc  lea     rdx, [rsp+0C8h+RpcCallAttributes]; RpcCallAttributes
0x180003701  xor     ecx, ecx; ClientBinding
0x180003703  call    cs:__imp_RpcServerInqCallAttributesW
0x18000370a  nop     dword ptr [rax+rax+00h]
0x18000370f  cmp     eax, 6BDh
0x180003714  jz      loc_1800037AA
0x18000371a  test    eax, eax
0x18000371c  jnz     short loc_180003730
0x18000371e  call    cs:__imp_GetCurrentProcessId
0x180003725  nop     dword ptr [rax+rax+00h]
0x18000372a  cmp     [rsp+0C8h+var_58], eax
0x18000372e  jz      short loc_1800037AA
0x180003730  call    cs:__imp_CoImpersonateClient
0x180003737  nop     dword ptr [rax+rax+00h]
0x18000373c  mov     ebx, eax
0x18000373e  cmp     eax, 80010117h
0x180003743  jz      loc_1800037D9
0x180003749  test    eax, eax
0x18000374b  js      loc_1800037DB
0x180003751  call    cs:__imp_GetCurrentThread
0x180003758  nop     dword ptr [rax+rax+00h]
0x18000375d  lea     r9, [rsp+0C8h+TokenHandle]; TokenHandle
0x180003762  mov     edx, 8; DesiredAccess
0x180003767  lea     r8d, [rdx-7]; OpenAsSelf
0x18000376b  mov     rcx, rax; ThreadHandle
0x18000376e  call    cs:__imp_OpenThreadToken
0x180003775  nop     dword ptr [rax+rax+00h]
0x18000377a  test    eax, eax
0x18000377c  jnz     short loc_1800037A1
0x18000377e  call    cs:__imp_GetLastError
0x180003785  nop     dword ptr [rax+rax+00h]
0x18000378a  test    eax, eax
0x18000378c  jz      short loc_1800037A1
0x18000378e  jg      short loc_180003794
0x180003790  mov     ebx, eax
0x180003792  jmp     short loc_18000379D
0x180003794  movzx   ebx, ax
0x180003797  or      ebx, 80070000h
0x18000379d  test    ebx, ebx
0x18000379f  js      short loc_1800037DB
0x1800037a1  test    ebx, ebx
0x1800037a3  js      short loc_1800037DB
0x1800037a5  cmp     ebx, 1
0x1800037a8  jz      short loc_1800037D9
0x1800037aa  call    cs:__imp_CoRevertToSelf
0x1800037b1  nop     dword ptr [rax+rax+00h]
0x1800037b6  call    ?CheckAndInit@SecurityFuncHelper@@AEAAJXZ; SecurityFuncHelper::CheckAndInit(void)
0x1800037bb  test    eax, eax
0x1800037bd  jns     short loc_1800037D9
0x1800037bf  movzx   ebx, ax
0x1800037c2  mov     eax, ebx
0x1800037c4  or      eax, 0C0070000h
0x1800037c9  test    ebx, ebx
0x1800037cb  cmovnz  ebx, eax
0x1800037ce  test    ebx, ebx
0x1800037d0  js      short loc_1800037DB
0x1800037d2  mov     ebx, 80070005h
0x1800037d7  jmp     short loc_1800037DB
0x1800037d9  xor     ebx, ebx
0x1800037db  mov     rcx, [rsp+0C8h+TokenHandle]; hObject
0x1800037e0  test    rcx, rcx
0x1800037e3  jz      short loc_1800037F1
0x1800037e5  call    cs:__imp_CloseHandle
0x1800037ec  nop     dword ptr [rax+rax+00h]
0x1800037f1  mov     eax, ebx
0x1800037f3  mov     rcx, [rsp+0C8h+var_18]
0x1800037fb  xor     rcx, rsp; StackCookie
0x1800037fe  call    __security_check_cookie
0x180003803  add     rsp, 0C0h
0x18000380a  pop     rbx
0x18000380b  retn
```
