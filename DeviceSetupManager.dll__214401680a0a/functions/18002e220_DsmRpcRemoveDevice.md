# DsmRpcRemoveDevice

- ea: `0x18002e220`
- end: `0x18002e3c8`
- name: `DsmRpcRemoveDevice`
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
- `0x18002e220`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e391`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e391`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002e2b5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002e2b5`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002e2c9`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002e2c9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e34d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e34d`
- `RPCRT4!I_RpcMapWin32Status` at `0x18002e290`
- `RPCRT4!I_RpcMapWin32Status` at `0x18002e309`
- `RPCRT4!I_RpcMapWin32Status` at `0x18002e290`
- `RPCRT4!I_RpcMapWin32Status` at `0x18002e309`
- `RPCRT4!RpcImpersonateClient` at `0x18002e284`
- `RPCRT4!RpcImpersonateClient` at `0x18002e284`
- `RPCRT4!RpcRevertToSelf` at `0x18002e353`
- `RPCRT4!RpcRevertToSelf` at `0x18002e397`
- `RPCRT4!RpcRevertToSelf` at `0x18002e353`
- `RPCRT4!RpcRevertToSelf` at `0x18002e397`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18002e2fd`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18002e2fd`

## pseudocode

```c
__int64 __fastcall DsmRpcRemoveDevice(RPC_BINDING_HANDLE ClientBinding, struct _GUID *a2)
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
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_5382ed2977f13c9d8b4aa53ff18b2f0c_Traceguids);
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
          v8 = (v15 & 2) != 0;
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
0x18002e220  mov     [rsp-8+arg_10], rbx
0x18002e225  mov     [rsp-8+arg_18], rsi
0x18002e22a  push    rbp
0x18002e22b  push    rdi
0x18002e22c  push    r15
0x18002e22e  lea     rbp, [rsp-47h]
0x18002e233  sub     rsp, 0D0h
0x18002e23a  mov     rax, cs:__security_cookie
0x18002e241  xor     rax, rsp
0x18002e244  mov     [rbp+57h+var_20], rax
0x18002e248  mov     rsi, rdx
0x18002e24b  mov     rdi, rcx
0x18002e24e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e255  lea     rax, WPP_GLOBAL_Control
0x18002e25c  mov     r15d, 1
0x18002e262  cmp     rcx, rax
0x18002e265  jz      short loc_18002E281
0x18002e267  test    [rcx+1Ch], r15b
0x18002e26b  jz      short loc_18002E281
0x18002e26d  mov     rcx, [rcx+10h]
0x18002e271  lea     edx, [r15+1Ah]
0x18002e275  lea     r8, WPP_5382ed2977f13c9d8b4aa53ff18b2f0c_Traceguids
0x18002e27c  call    WPP_SF_
0x18002e281  mov     rcx, rdi; BindingHandle
0x18002e284  call    cs:__imp_RpcImpersonateClient
0x18002e28a  test    eax, eax
0x18002e28c  jz      short loc_18002E2AD
0x18002e28e  mov     ecx, eax; Status
0x18002e290  call    cs:__imp_I_RpcMapWin32Status
0x18002e296  mov     ebx, eax
0x18002e298  test    eax, eax
0x18002e29a  jle     short loc_18002E2A5
0x18002e29c  movzx   ebx, ax
0x18002e29f  or      ebx, 80070000h
0x18002e2a5  test    ebx, ebx
0x18002e2a7  js      loc_18002E3A2
0x18002e2ad  mov     [rbp+57h+TokenHandle], 0
0x18002e2b5  call    cs:__imp_GetCurrentThread
0x18002e2bb  xor     r8d, r8d; OpenAsSelf
0x18002e2be  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18002e2c2  mov     rcx, rax; ThreadHandle
0x18002e2c5  lea     edx, [r8+2]; DesiredAccess
0x18002e2c9  call    cs:__imp_OpenThreadToken
0x18002e2cf  test    eax, eax
0x18002e2d1  jz      loc_18002E391
0x18002e2d7  xor     edx, edx; Val
0x18002e2d9  lea     rcx, [rbp+57h+var_88]; void *
0x18002e2dd  xor     bl, bl
0x18002e2df  lea     r8d, [rdx+68h]; Size
0x18002e2e3  call    memset_0
0x18002e2e8  lea     rdx, [rbp+57h+RpcCallAttributes]; RpcCallAttributes
0x18002e2ec  mov     [rbp+57h+RpcCallAttributes], 3
0x18002e2f3  mov     rcx, rdi; ClientBinding
0x18002e2f6  mov     [rbp+57h+var_8C], 10h
0x18002e2fd  call    cs:__imp_RpcServerInqCallAttributesW
0x18002e303  test    eax, eax
0x18002e305  jz      short loc_18002E31F
0x18002e307  mov     ecx, eax; Status
0x18002e309  call    cs:__imp_I_RpcMapWin32Status
0x18002e30f  test    eax, eax
0x18002e311  jle     short loc_18002E31D
0x18002e313  movzx   eax, ax
0x18002e316  or      eax, 80070000h
0x18002e31b  test    eax, eax
0x18002e31d  js      short loc_18002E349
0x18002e31f  mov     r8d, [rbp+57h+dwProcessId]; dwProcessId
0x18002e323  lea     r9, [rbp+57h+var_B0]; enum DSM_REMOVABLE_FLAGS *
0x18002e327  mov     rdx, [rbp+57h+TokenHandle]; void *
0x18002e32b  mov     rcx, rsi; struct _GUID *
0x18002e32e  mov     [rbp+57h+var_B0], 0
0x18002e335  call    ?IsUserAllowedToRemove@CDsmAccessCheck@@SAJAEBU_GUID@@PEAXKPEAW4DSM_REMOVABLE_FLAGS@@@Z; CDsmAccessCheck::IsUserAllowedToRemove(_GUID const &,void *,ulong,DSM_REMOVABLE_FLAGS *)
0x18002e33a  test    eax, eax
0x18002e33c  js      short loc_18002E349
0x18002e33e  test    byte ptr [rbp+57h+var_B0], 2
0x18002e342  movzx   ebx, bl
0x18002e345  cmovnz  ebx, r15d
0x18002e349  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x18002e34d  call    cs:__imp_CloseHandle
0x18002e353  call    cs:__imp_RpcRevertToSelf
0x18002e359  test    bl, bl
0x18002e35b  jz      short loc_18002E39D
0x18002e35d  lea     rdx, [rbp+57h+var_A0]
0x18002e361  call    ?GetContainerManager@CDsmCore@@QEAA?AV?$shared_ptr@VContainerManager@@@std@@XZ; CDsmCore::GetContainerManager(void)
0x18002e366  mov     rbx, [rbp+57h+var_A0]
0x18002e36a  test    rbx, rbx
0x18002e36d  jnz     short loc_18002E374
0x18002e36f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002e374  mov     rdx, rsi
0x18002e377  mov     rcx, rbx
0x18002e37a  call    ?PostJob@ContainerManager@@QEAAJAEBU_GUID@@W4JobType@@W4JobAttributes@@PEBG@Z; ContainerManager::PostJob(_GUID const &,JobType,JobAttributes,ushort const *)
0x18002e37f  mov     rcx, [rbp+57h+var_98]; this
0x18002e383  mov     ebx, eax
0x18002e385  test    rcx, rcx
0x18002e388  jz      short loc_18002E3A2
0x18002e38a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002e38f  jmp     short loc_18002E3A2
0x18002e391  call    cs:__imp_GetLastError
0x18002e397  call    cs:__imp_RpcRevertToSelf
0x18002e39d  mov     ebx, 80070005h
0x18002e3a2  mov     eax, ebx
0x18002e3a4  mov     rcx, [rbp+57h+var_20]
0x18002e3a8  xor     rcx, rsp; StackCookie
0x18002e3ab  call    __security_check_cookie
0x18002e3b0  lea     r11, [rsp+0E0h+var_10]
0x18002e3b8  mov     rbx, [r11+30h]
0x18002e3bc  mov     rsi, [r11+38h]
0x18002e3c0  mov     rsp, r11
0x18002e3c3  pop     r15
0x18002e3c5  pop     rdi
0x18002e3c6  pop     rbp
0x18002e3c7  retn
```
