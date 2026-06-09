# NetworkIsolationGetEnterpriseIdAsync

- ea: `0x18000f1a0`
- end: `0x18000f5f0`
- name: `NetworkIsolationGetEnterpriseIdAsync`
- size: `1104`
- prototype: `DWORD __stdcall(LPCWSTR wszServerName, DWORD dwFlags, void *context, PNETISO_EDP_ID_CALLBACK_FN callback, HANDLE *hOperation)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f110`

## callees

- `0x180005954`
- `0x18000e960`
- `0x18000f1a0`
- `0x18000f600`
- `0x18000f884`
- `0x180024c3c`
- `0x1800277b0`
- `0x1800284c4`
- `0x18003104c`
- `0x1800486d0`

## import_xrefs

- `RPCRT4!RpcExceptionFilter` at `0x18005b8f0`
- `RPCRT4!RpcExceptionFilter` at `0x18005b8f0`
- `RPCRT4!RpcBindingSetOption` at `0x18000f2b4`
- `RPCRT4!RpcBindingSetOption` at `0x18000f2b4`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18000f3fd`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18000f3fd`
- `RPCRT4!RpcBindingFree` at `0x18000f592`
- `RPCRT4!RpcBindingFree` at `0x18000f592`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000f305`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000f326`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000f305`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000f326`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18000f35b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18000f35b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000f3b2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000f3b2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000f20c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000f20c`
- `fwbase!FwBaseAlloc` at `0x18000f21d`
- `fwbase!FwBaseAlloc` at `0x18000f21d`

## pseudocode

```c
DWORD __stdcall NetworkIsolationGetEnterpriseIdAsync(
        LPCWSTR wszServerName,
        DWORD dwFlags,
        void *context,
        PNETISO_EDP_ID_CALLBACK_FN callback,
        HANDLE *hOperation)
{
  RPC_BINDING_HANDLE *v7; // rax
  RPC_BINDING_HANDLE *v8; // rsi
  __int64 v9; // r9
  unsigned int v10; // ebx
  FwPolicy2 *v11; // rcx
  unsigned int inited; // eax
  HANDLE EventW; // rax
  HANDLE v15; // rax
  struct _TP_WAIT *ThreadpoolWait; // rax
  __int64 v17; // rdx
  unsigned int v18; // eax
  __int64 v19; // rcx
  RPC_BINDING_HANDLE hBinding; // [rsp+78h] [rbp-40h] BYREF

  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 538, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids);
  hBinding = 0;
  GetTickCount64();
  *hOperation = 0;
  v7 = (RPC_BINDING_HANDLE *)FwBaseAlloc(192);
  v8 = v7;
  if ( !v7 )
  {
    v9 = 14;
    v10 = 14;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v17 = 539;
      goto LABEL_18;
    }
    goto LABEL_6;
  }
  memset_0(v7, 0, 0xC0u);
  inited = Int_FWLocalRpcBindingCreate(&hBinding);
  v10 = inited;
  if ( inited )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_6;
    v17 = 540;
LABEL_26:
    v9 = inited;
    goto LABEL_18;
  }
  inited = RpcBindingSetOption(hBinding, 9u, 1u);
  v10 = inited;
  if ( inited )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_6;
    v17 = 541;
    goto LABEL_26;
  }
  *v8 = hBinding;
  hBinding = 0;
  v8[16] = callback;
  v8[17] = context;
  *((_DWORD *)v8 + 44) = 1;
  _InterlockedExchange((volatile __int32 *)v8 + 45, 1);
  EventW = CreateEventW(0, 0, 0, 0);
  v8[18] = EventW;
  if ( !EventW )
  {
    v9 = 14;
    v10 = 14;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v17 = 542;
      goto LABEL_18;
    }
    goto LABEL_6;
  }
  v15 = CreateEventW(0, 1, 0, 0);
  v8[23] = v15;
  if ( !v15 )
  {
    v9 = 14;
    v10 = 14;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v17 = 543;
      goto LABEL_18;
    }
    goto LABEL_6;
  }
  inited = Int_NetworkIsolationInitOperationRpcAsync((struct FW_INTCLIENT_OP_HANDLE_ *)v8);
  v10 = inited;
  if ( inited )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_6;
    v17 = 544;
    goto LABEL_26;
  }
  ThreadpoolWait = CreateThreadpoolWait(Int_NetworkIsolationAsyncOpCallback, v8, 0);
  v8[19] = ThreadpoolWait;
  if ( ThreadpoolWait )
  {
    SetThreadpoolWait(ThreadpoolWait, v8[7], 0);
    Ndr64AsyncClientCall(
      (MIDL_STUBLESS_PROXY_INFO *)&FW_NET_ISO_DIAG_ProxyInfo,
      1u,
      0,
      v8 + 1,
      *v8,
      wszServerName,
      dwFlags,
      v8 + 20,
      v8 + 21);
    _InterlockedIncrement((volatile signed __int32 *)v8 + 44);
    *hOperation = v8;
    goto LABEL_20;
  }
  v9 = v10 + 14;
  v10 += 14;
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v17 = 545;
LABEL_18:
    WPP_SF_d(*((_QWORD *)v11 + 2), v17, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, v9);
LABEL_20:
    v11 = WPP_GLOBAL_Control;
  }
LABEL_6:
  if ( v10 )
  {
    FwTelemetryEventWriteError("NetworkIsolationGetEnterpriseIdAsync", v10);
    if ( hBinding )
    {
      v18 = RpcBindingFree(&hBinding);
      if ( v18 )
        MicrosoftTelemetryAssertTriggeredArgs(v19, v18);
      hBinding = 0;
    }
    if ( v8 )
    {
      _InterlockedExchange((volatile __int32 *)v8 + 45, 0);
      NetworkIsolationGetEnterpriseIdClose(v8, 0);
    }
    v11 = WPP_GLOBAL_Control;
  }
  if ( v11 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)v11 + 2), 547, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, v10);
  return v10;
}

```

## disassembly

```asm
0x18000f1a0  mov     [rsp+arg_10], rbx
0x18000f1a5  mov     [rsp+arg_18], rsi
0x18000f1aa  push    rdi
0x18000f1ab  push    r12
0x18000f1ad  push    r13
0x18000f1af  push    r14
0x18000f1b1  push    r15
0x18000f1b3  sub     rsp, 90h
0x18000f1ba  mov     rax, cs:__security_cookie
0x18000f1c1  xor     rax, rsp
0x18000f1c4  mov     [rsp+0B8h+var_38], rax
0x18000f1cc  mov     r15, r9
0x18000f1cf  mov     r13, r8
0x18000f1d2  mov     [rsp+0B8h+var_68], edx
0x18000f1d6  mov     [rsp+0B8h+var_58], rcx
0x18000f1db  mov     r12, [rsp+0B8h+hOperation]
0x18000f1e3  mov     [rsp+0B8h+var_50], r12
0x18000f1e8  lea     r14, WPP_GLOBAL_Control
0x18000f1ef  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f1f6  cmp     rcx, r14
0x18000f1f9  jz      short loc_18000F205
0x18000f1fb  test    byte ptr [rcx+1Ch], 8
0x18000f1ff  jnz     loc_18000F482
0x18000f205  xor     edi, edi
0x18000f207  mov     [rsp+0B8h+hBinding], rdi
0x18000f20c  call    cs:__imp_GetTickCount64
0x18000f212  mov     [r12], rdi
0x18000f216  mov     ebx, 0C0h
0x18000f21b  mov     ecx, ebx
0x18000f21d  call    cs:__imp_FwBaseAlloc
0x18000f223  mov     rsi, rax
0x18000f226  mov     [rsp+0B8h+var_60], rax
0x18000f22b  test    rax, rax
0x18000f22e  jnz     short loc_18000F287
0x18000f230  lea     r9d, [rdi+0Eh]
0x18000f234  mov     ebx, r9d
0x18000f237  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f23e  cmp     rcx, r14
0x18000f241  jnz     loc_18000F49C
0x18000f247  test    ebx, ebx
0x18000f249  jnz     loc_18000F578
0x18000f24f  cmp     rcx, r14
0x18000f252  jnz     loc_18000F5C9
0x18000f258  mov     eax, ebx
0x18000f25a  mov     rcx, [rsp+0B8h+var_38]
0x18000f262  xor     rcx, rsp; StackCookie
0x18000f265  call    __security_check_cookie
0x18000f26a  lea     r11, [rsp+0B8h+var_28]
0x18000f272  mov     rbx, [r11+40h]
0x18000f276  mov     rsi, [r11+48h]
0x18000f27a  mov     rsp, r11
0x18000f27d  pop     r15
0x18000f27f  pop     r14
0x18000f281  pop     r13
0x18000f283  pop     r12
0x18000f285  pop     rdi
0x18000f286  retn
0x18000f287  mov     r8, rbx; Size
0x18000f28a  xor     edx, edx; Val
0x18000f28c  mov     rcx, rsi; void *
0x18000f28f  call    memset_0
0x18000f294  lea     rcx, [rsp+0B8h+hBinding]
0x18000f299  call    Int_FWLocalRpcBindingCreate
0x18000f29e  mov     ebx, eax
0x18000f2a0  test    eax, eax
0x18000f2a2  jnz     loc_18000F4B0
0x18000f2a8  lea     edx, [rax+9]; option
0x18000f2ab  lea     r8d, [rax+1]; optionValue
0x18000f2af  mov     rcx, [rsp+0B8h+hBinding]; hBinding
0x18000f2b4  call    cs:__imp_RpcBindingSetOption
0x18000f2ba  mov     ebx, eax
0x18000f2bc  test    eax, eax
0x18000f2be  jnz     loc_18000F4DE
0x18000f2c4  mov     rax, [rsp+0B8h+hBinding]
0x18000f2c9  mov     [rsi], rax
0x18000f2cc  mov     [rsp+0B8h+hBinding], rdi
0x18000f2d1  mov     [rsi+80h], r15
0x18000f2d8  mov     [rsi+88h], r13
0x18000f2df  lea     r15, [rsi+0B0h]
0x18000f2e6  mov     [rsp+0B8h+var_48], r15
0x18000f2eb  mov     dword ptr [r15], 1
0x18000f2f2  lea     eax, [rbx+1]
0x18000f2f5  xchg    eax, [rsi+0B4h]
0x18000f2fb  xor     r9d, r9d; lpName
0x18000f2fe  xor     r8d, r8d; bInitialState
0x18000f301  xor     edx, edx; bManualReset
0x18000f303  xor     ecx, ecx; lpEventAttributes
0x18000f305  call    cs:__imp_CreateEventW
0x18000f30b  mov     [rsi+90h], rax
0x18000f312  test    rax, rax
0x18000f315  jz      loc_18000F4FF
0x18000f31b  xor     r9d, r9d; lpName
0x18000f31e  xor     r8d, r8d; bInitialState
0x18000f321  lea     edx, [rbx+1]; bManualReset
0x18000f324  xor     ecx, ecx; lpEventAttributes
0x18000f326  call    cs:__imp_CreateEventW
0x18000f32c  mov     [rsi+0B8h], rax
0x18000f333  test    rax, rax
0x18000f336  jz      loc_18000F52C
0x18000f33c  mov     rcx, rsi; struct FW_INTCLIENT_OP_HANDLE_ *
0x18000f33f  call    ?Int_NetworkIsolationInitOperationRpcAsync@@YAKPEAUFW_INTCLIENT_OP_HANDLE_@@@Z; Int_NetworkIsolationInitOperationRpcAsync(FW_INTCLIENT_OP_HANDLE_ *)
0x18000f344  mov     ebx, eax
0x18000f346  test    eax, eax
0x18000f348  jnz     loc_18000F559
0x18000f34e  xor     r8d, r8d; pcbe
0x18000f351  mov     rdx, rsi; pv
0x18000f354  lea     rcx, ?Int_NetworkIsolationAsyncOpCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x18000f35b  call    cs:__imp_CreateThreadpoolWait
0x18000f361  mov     [rsi+98h], rax
0x18000f368  test    rax, rax
0x18000f36b  jnz     short loc_18000F3A8
0x18000f36d  lea     r9d, [rbx+0Eh]
0x18000f371  mov     ebx, r9d
0x18000f374  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f37b  cmp     rcx, r14
0x18000f37e  jz      loc_18000F247
0x18000f384  test    byte ptr [rcx+1Ch], 1
0x18000f388  jz      loc_18000F247
0x18000f38e  mov     edx, 221h
0x18000f393  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x18000f39a  mov     rcx, [rcx+10h]
0x18000f39e  call    WPP_SF_d
0x18000f3a3  jmp     loc_18000F476
0x18000f3a8  xor     r8d, r8d; pftTimeout
0x18000f3ab  mov     rdx, [rsi+38h]; h
0x18000f3af  mov     rcx, rax; pwa
0x18000f3b2  call    cs:__imp_SetThreadpoolWait
0x18000f3b8  nop
0x18000f3b9  lea     rax, [rsi+0A8h]
0x18000f3c0  lea     rcx, [rsi+0A0h]
0x18000f3c7  mov     [rsp+0B8h+var_78], rax
0x18000f3cc  mov     [rsp+0B8h+var_80], rcx
0x18000f3d1  mov     eax, [rsp+0B8h+var_68]
0x18000f3d5  mov     [rsp+0B8h+var_88], eax
0x18000f3d9  mov     rax, [rsp+0B8h+var_58]
0x18000f3de  mov     [rsp+0B8h+var_90], rax
0x18000f3e3  mov     rax, [rsi]
0x18000f3e6  mov     [rsp+0B8h+var_98], rax
0x18000f3eb  lea     r9, [rsi+8]
0x18000f3ef  xor     r8d, r8d; pReturnValue
0x18000f3f2  lea     edx, [r8+1]; nProcNum
0x18000f3f6  lea     rcx, ?FW_NET_ISO_DIAG_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18000f3fd  call    cs:__imp_Ndr64AsyncClientCall
0x18000f403  jmp     short loc_18000F46E
0x18000f405  mov     ebx, eax
0x18000f407  test    eax, eax
0x18000f409  jz      short loc_18000F456
0x18000f40b  lea     rax, WPP_GLOBAL_Control
0x18000f412  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f419  cmp     rcx, rax
0x18000f41c  jz      short loc_18000F443
0x18000f41e  test    byte ptr [rcx+1Ch], 1
0x18000f422  jz      short loc_18000F443
0x18000f424  mov     edx, 222h
0x18000f429  mov     r9d, ebx
0x18000f42c  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x18000f433  mov     rcx, [rcx+10h]
0x18000f437  call    WPP_SF_d
0x18000f43c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f443  lea     r14, WPP_GLOBAL_Control
0x18000f44a  xor     edi, edi
0x18000f44c  mov     rsi, [rsp+0B8h+var_60]
0x18000f451  jmp     loc_18000F247
0x18000f456  lea     r14, WPP_GLOBAL_Control
0x18000f45d  xor     edi, edi
0x18000f45f  mov     r12, [rsp+0B8h+var_50]
0x18000f464  mov     rsi, [rsp+0B8h+var_60]
0x18000f469  mov     r15, [rsp+0B8h+var_48]
0x18000f46e  lock inc dword ptr [r15]
0x18000f472  mov     [r12], rsi
0x18000f476  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f47d  jmp     loc_18000F247
0x18000f482  mov     edx, 21Ah
0x18000f487  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x18000f48e  mov     rcx, [rcx+10h]
0x18000f492  call    WPP_SF_
0x18000f497  jmp     loc_18000F205
0x18000f49c  test    byte ptr [rcx+1Ch], 1
0x18000f4a0  jz      loc_18000F247
0x18000f4a6  mov     edx, 21Bh
0x18000f4ab  jmp     loc_18000F393
0x18000f4b0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f4b7  cmp     rcx, r14
0x18000f4ba  jz      loc_18000F247
0x18000f4c0  test    byte ptr [rcx+1Ch], 1
0x18000f4c4  jz      loc_18000F247
0x18000f4ca  mov     edx, 21Ch
0x18000f4cf  jmp     short loc_18000F4D6
0x18000f4d1  mov     edx, 220h
0x18000f4d6  mov     r9d, eax
0x18000f4d9  jmp     loc_18000F393
0x18000f4de  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f4e5  cmp     rcx, r14
0x18000f4e8  jz      loc_18000F247
0x18000f4ee  test    byte ptr [rcx+1Ch], 1
0x18000f4f2  jz      loc_18000F247
0x18000f4f8  mov     edx, 21Dh
0x18000f4fd  jmp     short loc_18000F4D6
0x18000f4ff  mov     r9d, 0Eh
0x18000f505  mov     ebx, r9d
0x18000f508  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f50f  cmp     rcx, r14
0x18000f512  jz      loc_18000F247
0x18000f518  test    byte ptr [rcx+1Ch], 1
0x18000f51c  jz      loc_18000F247
0x18000f522  mov     edx, 21Eh
0x18000f527  jmp     loc_18000F393
0x18000f52c  mov     r9d, 0Eh
0x18000f532  mov     ebx, r9d
0x18000f535  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f53c  cmp     rcx, r14
0x18000f53f  jz      loc_18000F247
0x18000f545  test    byte ptr [rcx+1Ch], 1
0x18000f549  jz      loc_18000F247
0x18000f54f  mov     edx, 21Fh
0x18000f554  jmp     loc_18000F393
0x18000f559  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f560  cmp     rcx, r14
0x18000f563  jz      loc_18000F247
0x18000f569  test    byte ptr [rcx+1Ch], 1
0x18000f56d  jz      loc_18000F247
0x18000f573  jmp     loc_18000F4D1
0x18000f578  mov     edx, ebx; unsigned int
0x18000f57a  lea     rcx, aNetworkisolati_29; "NetworkIsolationGetEnterpriseIdAsync"
0x18000f581  call    ?FwTelemetryEventWriteError@@YAXQEADI@Z; FwTelemetryEventWriteError(char * const,uint)
0x18000f586  cmp     [rsp+0B8h+hBinding], rdi
0x18000f58b  jz      short loc_18000F5A8
0x18000f58d  lea     rcx, [rsp+0B8h+hBinding]; Binding
0x18000f592  call    cs:__imp_RpcBindingFree
0x18000f598  test    eax, eax
0x18000f59a  jz      short loc_18000F5A3
0x18000f59c  mov     edx, eax
0x18000f59e  call    MicrosoftTelemetryAssertTriggeredArgs
0x18000f5a3  mov     [rsp+0B8h+hBinding], rdi
0x18000f5a8  test    rsi, rsi
0x18000f5ab  jz      short loc_18000F5BD
0x18000f5ad  xchg    edi, [rsi+0B4h]
0x18000f5b3  xor     edx, edx; bWaitForOperation
0x18000f5b5  mov     rcx, rsi; hOperation
0x18000f5b8  call    NetworkIsolationGetEnterpriseIdClose
0x18000f5bd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f5c4  jmp     loc_18000F24F
0x18000f5c9  test    byte ptr [rcx+1Ch], 8
0x18000f5cd  jz      loc_18000F258
0x18000f5d3  mov     edx, 223h
0x18000f5d8  mov     r9d, ebx
0x18000f5db  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x18000f5e2  mov     rcx, [rcx+10h]
0x18000f5e6  call    WPP_SF_d
0x18000f5eb  jmp     loc_18000F258
0x18005b8e2  push    rbp
0x18005b8e4  sub     rsp, 50h
0x18005b8e8  mov     rbp, rdx
0x18005b8eb  mov     rcx, [rcx]
0x18005b8ee  mov     ecx, [rcx]; ExceptionCode
0x18005b8f0  call    cs:__imp_RpcExceptionFilter
0x18005b8f6  nop
0x18005b8f7  add     rsp, 50h
0x18005b8fb  pop     rbp
0x18005b8fc  retn
```
