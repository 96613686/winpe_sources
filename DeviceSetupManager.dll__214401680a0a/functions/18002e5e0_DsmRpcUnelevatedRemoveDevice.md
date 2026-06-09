# DsmRpcUnelevatedRemoveDevice

- ea: `0x18002e5e0`
- end: `0x18002e788`
- name: `DsmRpcUnelevatedRemoveDevice`
- size: `424`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE ClientBinding, struct _GUID *)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180012910`
- `0x18001370c`
- `0x180014908`
- `0x180019794`
- `0x18001af70`
- `0x18001ba48`
- `0x180021790`
- `0x18002d790`
- `0x18002e5e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e751`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e751`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002e675`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002e675`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002e689`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002e689`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e70d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e70d`
- `RPCRT4!I_RpcMapWin32Status` at `0x18002e650`
- `RPCRT4!I_RpcMapWin32Status` at `0x18002e6c9`
- `RPCRT4!I_RpcMapWin32Status` at `0x18002e650`
- `RPCRT4!I_RpcMapWin32Status` at `0x18002e6c9`
- `RPCRT4!RpcImpersonateClient` at `0x18002e644`
- `RPCRT4!RpcImpersonateClient` at `0x18002e644`
- `RPCRT4!RpcRevertToSelf` at `0x18002e713`
- `RPCRT4!RpcRevertToSelf` at `0x18002e757`
- `RPCRT4!RpcRevertToSelf` at `0x18002e713`
- `RPCRT4!RpcRevertToSelf` at `0x18002e757`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18002e6bd`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18002e6bd`

## pseudocode

```c
__int64 __fastcall DsmRpcUnelevatedRemoveDevice(RPC_BINDING_HANDLE ClientBinding, struct _GUID *a2)
{
  RPC_STATUS v4; // eax
  int v5; // eax
  unsigned int v6; // ebx
  HANDLE CurrentThread; // rax
  bool v8; // bl
  RPC_STATUS v9; // eax
  int v10; // eax
  bool v11; // sf
  __int64 v12; // rcx
  __int64 v13; // rbx
  int v15; // [rsp+30h] [rbp-59h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-51h] BYREF
  __int64 v17; // [rsp+40h] [rbp-49h] BYREF
  std::_Ref_count_base *v18; // [rsp+48h] [rbp-41h]
  _DWORD RpcCallAttributes[2]; // [rsp+50h] [rbp-39h] BYREF
  _BYTE v20[56]; // [rsp+58h] [rbp-31h] BYREF
  DWORD dwProcessId; // [rsp+90h] [rbp+7h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_5382ed2977f13c9d8b4aa53ff18b2f0c_Traceguids);
  v4 = RpcImpersonateClient(ClientBinding);
  if ( !v4 )
    goto LABEL_8;
  v5 = I_RpcMapWin32Status(v4);
  v6 = v5;
  if ( v5 > 0 )
    v6 = (unsigned __int16)v5 | 0x80070000;
  if ( (v6 & 0x80000000) == 0 )
  {
LABEL_8:
    TokenHandle = 0;
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 2u, 0, &TokenHandle) )
    {
      v8 = 0;
      memset_0(v20, 0, 0x68u);
      RpcCallAttributes[0] = 3;
      RpcCallAttributes[1] = 16;
      v9 = RpcServerInqCallAttributesW(ClientBinding, RpcCallAttributes);
      if ( !v9 )
        goto LABEL_13;
      v10 = I_RpcMapWin32Status(v9);
      v11 = v10 < 0;
      if ( v10 > 0 )
        v11 = 1;
      if ( !v11 )
      {
LABEL_13:
        v15 = 0;
        if ( (int)CDsmAccessCheck::IsUserAllowedToRemove(a2, TokenHandle, dwProcessId, (enum DSM_REMOVABLE_FLAGS *)&v15) >= 0 )
          v8 = (v15 & 1) != 0;
      }
      CloseHandle(TokenHandle);
      RpcRevertToSelf();
      if ( v8 )
      {
        CDsmCore::GetContainerManager(v12, &v17);
        v13 = v17;
        if ( !v17 )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        v6 = ContainerManager::PostJob(v13, a2);
        if ( v18 )
          std::_Ref_count_base::_Decref(v18);
        return v6;
      }
    }
    else
    {
      GetLastError();
      RpcRevertToSelf();
    }
    return (unsigned int)-2147024891;
  }
  return v6;
}

```

## disassembly

```asm
0x18002e5e0  mov     [rsp-8+arg_10], rbx
0x18002e5e5  mov     [rsp-8+arg_18], rsi
0x18002e5ea  push    rbp
0x18002e5eb  push    rdi
0x18002e5ec  push    r14
0x18002e5ee  lea     rbp, [rsp-47h]
0x18002e5f3  sub     rsp, 0D0h
0x18002e5fa  mov     rax, cs:__security_cookie
0x18002e601  xor     rax, rsp
0x18002e604  mov     [rbp+57h+var_20], rax
0x18002e608  mov     rsi, rdx
0x18002e60b  mov     rdi, rcx
0x18002e60e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e615  lea     rax, WPP_GLOBAL_Control
0x18002e61c  mov     r14d, 1
0x18002e622  cmp     rcx, rax
0x18002e625  jz      short loc_18002E641
0x18002e627  test    [rcx+1Ch], r14b
0x18002e62b  jz      short loc_18002E641
0x18002e62d  mov     rcx, [rcx+10h]
0x18002e631  lea     edx, [r14+1Bh]
0x18002e635  lea     r8, WPP_5382ed2977f13c9d8b4aa53ff18b2f0c_Traceguids
0x18002e63c  call    WPP_SF_
0x18002e641  mov     rcx, rdi; BindingHandle
0x18002e644  call    cs:__imp_RpcImpersonateClient
0x18002e64a  test    eax, eax
0x18002e64c  jz      short loc_18002E66D
0x18002e64e  mov     ecx, eax; Status
0x18002e650  call    cs:__imp_I_RpcMapWin32Status
0x18002e656  mov     ebx, eax
0x18002e658  test    eax, eax
0x18002e65a  jle     short loc_18002E665
0x18002e65c  movzx   ebx, ax
0x18002e65f  or      ebx, 80070000h
0x18002e665  test    ebx, ebx
0x18002e667  js      loc_18002E762
0x18002e66d  mov     [rbp+57h+TokenHandle], 0
0x18002e675  call    cs:__imp_GetCurrentThread
0x18002e67b  xor     r8d, r8d; OpenAsSelf
0x18002e67e  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18002e682  mov     rcx, rax; ThreadHandle
0x18002e685  lea     edx, [r8+2]; DesiredAccess
0x18002e689  call    cs:__imp_OpenThreadToken
0x18002e68f  test    eax, eax
0x18002e691  jz      loc_18002E751
0x18002e697  xor     edx, edx; Val
0x18002e699  lea     rcx, [rbp+57h+var_88]; void *
0x18002e69d  xor     bl, bl
0x18002e69f  lea     r8d, [rdx+68h]; Size
0x18002e6a3  call    memset_0
0x18002e6a8  lea     rdx, [rbp+57h+RpcCallAttributes]; RpcCallAttributes
0x18002e6ac  mov     [rbp+57h+RpcCallAttributes], 3
0x18002e6b3  mov     rcx, rdi; ClientBinding
0x18002e6b6  mov     [rbp+57h+var_8C], 10h
0x18002e6bd  call    cs:__imp_RpcServerInqCallAttributesW
0x18002e6c3  test    eax, eax
0x18002e6c5  jz      short loc_18002E6DF
0x18002e6c7  mov     ecx, eax; Status
0x18002e6c9  call    cs:__imp_I_RpcMapWin32Status
0x18002e6cf  test    eax, eax
0x18002e6d1  jle     short loc_18002E6DD
0x18002e6d3  movzx   eax, ax
0x18002e6d6  or      eax, 80070000h
0x18002e6db  test    eax, eax
0x18002e6dd  js      short loc_18002E709
0x18002e6df  mov     r8d, [rbp+57h+dwProcessId]; dwProcessId
0x18002e6e3  lea     r9, [rbp+57h+var_B0]; enum DSM_REMOVABLE_FLAGS *
0x18002e6e7  mov     rdx, [rbp+57h+TokenHandle]; void *
0x18002e6eb  mov     rcx, rsi; struct _GUID *
0x18002e6ee  mov     [rbp+57h+var_B0], 0
0x18002e6f5  call    ?IsUserAllowedToRemove@CDsmAccessCheck@@SAJAEBU_GUID@@PEAXKPEAW4DSM_REMOVABLE_FLAGS@@@Z; CDsmAccessCheck::IsUserAllowedToRemove(_GUID const &,void *,ulong,DSM_REMOVABLE_FLAGS *)
0x18002e6fa  test    eax, eax
0x18002e6fc  js      short loc_18002E709
0x18002e6fe  test    byte ptr [rbp+57h+var_B0], r14b
0x18002e702  movzx   ebx, bl
0x18002e705  cmovnz  ebx, r14d
0x18002e709  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x18002e70d  call    cs:__imp_CloseHandle
0x18002e713  call    cs:__imp_RpcRevertToSelf
0x18002e719  test    bl, bl
0x18002e71b  jz      short loc_18002E75D
0x18002e71d  lea     rdx, [rbp+57h+var_A0]
0x18002e721  call    ?GetContainerManager@CDsmCore@@QEAA?AV?$shared_ptr@VContainerManager@@@std@@XZ; CDsmCore::GetContainerManager(void)
0x18002e726  mov     rbx, [rbp+57h+var_A0]
0x18002e72a  test    rbx, rbx
0x18002e72d  jnz     short loc_18002E734
0x18002e72f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002e734  mov     rdx, rsi
0x18002e737  mov     rcx, rbx
0x18002e73a  call    ?PostJob@ContainerManager@@QEAAJAEBU_GUID@@W4JobType@@W4JobAttributes@@PEBG@Z; ContainerManager::PostJob(_GUID const &,JobType,JobAttributes,ushort const *)
0x18002e73f  mov     rcx, [rbp+57h+var_98]; this
0x18002e743  mov     ebx, eax
0x18002e745  test    rcx, rcx
0x18002e748  jz      short loc_18002E762
0x18002e74a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002e74f  jmp     short loc_18002E762
0x18002e751  call    cs:__imp_GetLastError
0x18002e757  call    cs:__imp_RpcRevertToSelf
0x18002e75d  mov     ebx, 80070005h
0x18002e762  mov     eax, ebx
0x18002e764  mov     rcx, [rbp+57h+var_20]
0x18002e768  xor     rcx, rsp; StackCookie
0x18002e76b  call    __security_check_cookie
0x18002e770  lea     r11, [rsp+0E0h+var_10]
0x18002e778  mov     rbx, [r11+30h]
0x18002e77c  mov     rsi, [r11+38h]
0x18002e780  mov     rsp, r11
0x18002e783  pop     r14
0x18002e785  pop     rdi
0x18002e786  pop     rbp
0x18002e787  retn
```
