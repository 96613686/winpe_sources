# FWClosePolicyStore

- ea: `0x18000c130`
- end: `0x18000c55a`
- name: `FWClosePolicyStore`
- size: `1066`
- prototype: ``
- caller_count: `33`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180002390`
- `0x180003520`
- `0x180005a50`
- `0x180006394`
- `0x18000b390`
- `0x18000bcd0`
- `0x18000bea0`
- `0x180011120`
- `0x180018230`
- `0x180018ef0`
- `0x18001c344`
- `0x18001cb8c`
- `0x18001dd10`
- `0x18001f8f4`
- `0x180020370`
- `0x180025744`
- `0x180026de8`
- `0x180026f50`
- `0x18002e484`
- `0x180030ab8`
- `0x180032ac0`
- `0x180032de0`
- `0x180032f90`
- `0x1800332c0`
- `0x180033630`
- `0x180045f54`
- `0x1800474dc`
- `0x18004ae10`
- `0x18004c230`
- `0x18004cb70`
- `0x18004f6e0`
- `0x180050f10`
- `0x1800587a0`

## callees

- `0x180005954`
- `0x18000c130`
- `0x180024c3c`
- `0x18002514c`
- `0x18003104c`
- `0x1800516bc`

## import_xrefs

- `RPCRT4!RpcExceptionFilter` at `0x18005b81e`
- `RPCRT4!RpcExceptionFilter` at `0x18005b83a`
- `RPCRT4!RpcExceptionFilter` at `0x18005b81e`
- `RPCRT4!RpcExceptionFilter` at `0x18005b83a`
- `RPCRT4!NdrClientCall3` at `0x18000c1d8`
- `RPCRT4!NdrClientCall3` at `0x18000c40f`
- `RPCRT4!NdrClientCall3` at `0x18000c1d8`
- `RPCRT4!NdrClientCall3` at `0x18000c40f`
- `RPCRT4!RpcBindingFree` at `0x18000c2c1`
- `RPCRT4!RpcBindingFree` at `0x18000c2c1`
- `ntdll!EtwEventWrite` at `0x18000c15f`
- `ntdll!EtwEventWrite` at `0x18000c30f`
- `ntdll!EtwEventWrite` at `0x18000c15f`
- `ntdll!EtwEventWrite` at `0x18000c30f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000c182`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000c182`
- `fwbase!FwBaseFree` at `0x18000c2d7`
- `fwbase!FwBaseFree` at `0x18000c2e4`
- `fwbase!FwBaseFree` at `0x18000c2d7`
- `fwbase!FwBaseFree` at `0x18000c2e4`

## pseudocode

```c
__int64 __fastcall FWClosePolicyStore(__int64 a1)
{
  __int64 v2; // rdx
  __int64 v3; // r8
  int v4; // eax
  unsigned int Pointer; // eax
  unsigned int v6; // ebx
  FwPolicy2 *v7; // rcx
  unsigned int v8; // eax
  unsigned int v9; // eax
  __int64 v10; // rcx
  __int64 v12; // rdx
  unsigned int v13; // eax

  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_CLNT_API_Enter_ClosePolicyStore, 0, 0);
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids);
  GetTickCount64();
  if ( !a1 )
  {
    a1 = 0;
    v6 = 87;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control )
      goto LABEL_19;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_16;
    v12 = 39;
    goto LABEL_51;
  }
  v4 = *(_DWORD *)(a1 + 4);
  if ( !v4 )
  {
    if ( *(_QWORD *)(a1 + 32) && *(_QWORD *)(a1 + 40) )
    {
      Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&FW_ProxyInfo, 1u, 0).Pointer;
      v6 = Pointer;
      if ( Pointer )
      {
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, Pointer);
          v7 = WPP_GLOBAL_Control;
        }
      }
      else
      {
        *(_QWORD *)(a1 + 40) = 0;
        v7 = WPP_GLOBAL_Control;
      }
      goto LABEL_16;
    }
    v6 = 87;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, 87);
LABEL_52:
      v7 = WPP_GLOBAL_Control;
      goto LABEL_16;
    }
    goto LABEL_16;
  }
  v6 = 0;
  if ( v4 != 1 )
    goto LABEL_52;
  if ( *(_QWORD *)(a1 + 32) && *(_QWORD *)(a1 + 40) )
  {
    v13 = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&RemoteFW_ProxyInfo, 1u, 0).Pointer;
    v6 = v13;
    if ( v13 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, v13);
        v7 = WPP_GLOBAL_Control;
      }
    }
    else
    {
      *(_QWORD *)(a1 + 40) = 0;
      v7 = WPP_GLOBAL_Control;
    }
    goto LABEL_16;
  }
  v6 = 87;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control )
    goto LABEL_19;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v12 = 43;
LABEL_51:
    WPP_SF_d(*((_QWORD *)v7 + 2), v12, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, 87);
    goto LABEL_52;
  }
LABEL_16:
  if ( v7 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)v7 + 2), 378, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids);
LABEL_19:
  if ( a1 )
  {
    v8 = *(_DWORD *)(a1 + 4);
    if ( v8 > 1 )
    {
      if ( v8 != 2 )
        MicrosoftTelemetryAssertTriggeredNoArgs(v7, v2, v3);
      Int_FWCleanupGPOPolicyStore(a1, v2, v3);
    }
    else if ( *(_QWORD *)(a1 + 32) )
    {
      v9 = RpcBindingFree((RPC_BINDING_HANDLE *)(a1 + 32));
      if ( v9 )
        MicrosoftTelemetryAssertTriggeredArgs(v10, v9);
      *(_QWORD *)(a1 + 32) = 0;
    }
    FwBaseFree(*(_QWORD *)(a1 + 8));
    *(_QWORD *)(a1 + 8) = 0;
  }
  FwBaseFree(a1);
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids);
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_CLNT_API_Exit_ClosePolicyStore, 0, 0);
  return v6;
}

```

## disassembly

```asm
0x18000c130  mov     [rsp+arg_10], rbx
0x18000c135  mov     [rsp+arg_18], rsi
0x18000c13a  push    rdi
0x18000c13b  push    r14
0x18000c13d  push    r15
0x18000c13f  sub     rsp, 40h
0x18000c143  mov     rdi, rcx
0x18000c146  mov     rcx, cs:g_Provider
0x18000c14d  test    rcx, rcx
0x18000c150  jz      short loc_18000C165
0x18000c152  xor     r9d, r9d
0x18000c155  xor     r8d, r8d
0x18000c158  lea     rdx, MPS_CLNT_API_Enter_ClosePolicyStore
0x18000c15f  call    cs:__imp_EtwEventWrite
0x18000c165  lea     rsi, WPP_GLOBAL_Control
0x18000c16c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c173  cmp     rcx, rsi
0x18000c176  jz      short loc_18000C182
0x18000c178  test    byte ptr [rcx+1Ch], 8
0x18000c17c  jnz     loc_18000C377
0x18000c182  call    cs:__imp_GetTickCount64
0x18000c188  test    rdi, rdi
0x18000c18b  jz      loc_18000C348
0x18000c191  mov     [rsp+58h+arg_0], rdi
0x18000c196  mov     eax, [rdi+4]
0x18000c199  test    eax, eax
0x18000c19b  jnz     loc_18000C3D0
0x18000c1a1  mov     r9, [rdi+20h]
0x18000c1a5  test    r9, r9
0x18000c1a8  jz      loc_18000C391
0x18000c1ae  lea     r14, [rdi+28h]
0x18000c1b2  cmp     qword ptr [r14], 0
0x18000c1b6  jz      loc_18000C391
0x18000c1bc  xor     r15d, r15d
0x18000c1bf  mov     [rsp+58h+arg_8], r15
0x18000c1c4  mov     [rsp+58h+var_38], r14
0x18000c1c9  xor     r8d, r8d; pReturnValue
0x18000c1cc  mov     edx, 1; nProcNum
0x18000c1d1  lea     rcx, ?FW_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18000c1d8  call    cs:__imp_NdrClientCall3
0x18000c1de  mov     rbx, rax
0x18000c1e1  mov     [rsp+58h+arg_8], rax
0x18000c1e6  mov     [rsp+58h+var_28], eax
0x18000c1ea  test    eax, eax
0x18000c1ec  jz      short loc_18000C221
0x18000c1ee  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c1f5  cmp     rcx, rsi
0x18000c1f8  jz      short loc_18000C21F
0x18000c1fa  test    byte ptr [rcx+1Ch], 1
0x18000c1fe  jz      short loc_18000C21F
0x18000c200  mov     edx, 29h ; ')'
0x18000c205  mov     r9d, eax
0x18000c208  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x18000c20f  mov     rcx, [rcx+10h]
0x18000c213  call    WPP_SF_d
0x18000c218  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c21f  jmp     short loc_18000C296
0x18000c221  mov     [r14], r15
0x18000c224  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c22b  jmp     short loc_18000C296
0x18000c22d  mov     ebx, eax
0x18000c22f  mov     [rsp+58h+var_28], eax
0x18000c233  test    eax, eax
0x18000c235  jz      short loc_18000C280
0x18000c237  lea     rdx, WPP_GLOBAL_Control
0x18000c23e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c245  cmp     rcx, rdx
0x18000c248  jz      short loc_18000C26F
0x18000c24a  test    byte ptr [rcx+1Ch], 1
0x18000c24e  jz      short loc_18000C26F
0x18000c250  mov     edx, 2Ah ; '*'
0x18000c255  mov     r9d, eax
0x18000c258  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x18000c25f  mov     rcx, [rcx+10h]
0x18000c263  call    WPP_SF_d
0x18000c268  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c26f  lea     rsi, WPP_GLOBAL_Control
0x18000c276  xor     r15d, r15d
0x18000c279  mov     rdi, [rsp+58h+arg_0]
0x18000c27e  jmp     short loc_18000C296
0x18000c280  lea     rsi, WPP_GLOBAL_Control
0x18000c287  xor     r15d, r15d
0x18000c28a  mov     rdi, [rsp+58h+arg_0]
0x18000c28f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c296  cmp     rcx, rsi
0x18000c299  jz      short loc_18000C2A5
0x18000c29b  test    byte ptr [rcx+1Ch], 8
0x18000c29f  jnz     loc_18000C51D
0x18000c2a5  test    rdi, rdi
0x18000c2a8  jz      short loc_18000C2E1
0x18000c2aa  mov     eax, [rdi+4]
0x18000c2ad  cmp     eax, 1
0x18000c2b0  ja      loc_18000C537
0x18000c2b6  cmp     qword ptr [rdi+20h], 0
0x18000c2bb  jz      short loc_18000C2D3
0x18000c2bd  lea     rcx, [rdi+20h]; Binding
0x18000c2c1  call    cs:__imp_RpcBindingFree
0x18000c2c7  test    eax, eax
0x18000c2c9  jnz     loc_18000C54E
0x18000c2cf  mov     [rdi+20h], r15
0x18000c2d3  mov     rcx, [rdi+8]
0x18000c2d7  call    cs:__imp_FwBaseFree
0x18000c2dd  mov     [rdi+8], r15
0x18000c2e1  mov     rcx, rdi
0x18000c2e4  call    cs:__imp_FwBaseFree
0x18000c2ea  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c2f1  cmp     rcx, rsi
0x18000c2f4  jnz     short loc_18000C32B
0x18000c2f6  mov     rcx, cs:g_Provider
0x18000c2fd  test    rcx, rcx
0x18000c300  jz      short loc_18000C315
0x18000c302  xor     r9d, r9d
0x18000c305  xor     r8d, r8d
0x18000c308  lea     rdx, MPS_CLNT_API_Exit_ClosePolicyStore
0x18000c30f  call    cs:__imp_EtwEventWrite
0x18000c315  mov     eax, ebx
0x18000c317  mov     rbx, [rsp+58h+arg_10]
0x18000c31c  mov     rsi, [rsp+58h+arg_18]
0x18000c321  add     rsp, 40h
0x18000c325  pop     r15
0x18000c327  pop     r14
0x18000c329  pop     rdi
0x18000c32a  retn
0x18000c32b  test    byte ptr [rcx+1Ch], 8
0x18000c32f  jz      short loc_18000C2F6
0x18000c331  mov     edx, 2Eh ; '.'
0x18000c336  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x18000c33d  mov     rcx, [rcx+10h]
0x18000c341  call    WPP_SF_
0x18000c346  jmp     short loc_18000C2F6
0x18000c348  xor     r15d, r15d
0x18000c34b  mov     edi, r15d
0x18000c34e  mov     ebx, 57h ; 'W'
0x18000c353  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c35a  cmp     rcx, rsi
0x18000c35d  jz      loc_18000C2A5
0x18000c363  test    byte ptr [rcx+1Ch], 1
0x18000c367  jz      loc_18000C296
0x18000c36d  mov     edx, 27h ; '''
0x18000c372  jmp     loc_18000C4FE
0x18000c377  mov     edx, 26h ; '&'
0x18000c37c  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x18000c383  mov     rcx, [rcx+10h]
0x18000c387  call    WPP_SF_
0x18000c38c  jmp     loc_18000C182
0x18000c391  mov     ebx, 57h ; 'W'
0x18000c396  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c39d  cmp     rcx, rsi
0x18000c3a0  jz      short loc_18000C3C8
0x18000c3a2  test    byte ptr [rcx+1Ch], 1
0x18000c3a6  jz      short loc_18000C3C8
0x18000c3a8  mov     edx, 28h ; '('
0x18000c3ad  mov     r9d, ebx
0x18000c3b0  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x18000c3b7  mov     rcx, [rcx+10h]
0x18000c3bb  call    WPP_SF_d
0x18000c3c0  xor     r15d, r15d
0x18000c3c3  jmp     loc_18000C511
0x18000c3c8  xor     r15d, r15d
0x18000c3cb  jmp     loc_18000C296
0x18000c3d0  xor     r15d, r15d
0x18000c3d3  mov     ebx, r15d
0x18000c3d6  cmp     eax, 1
0x18000c3d9  jnz     loc_18000C511
0x18000c3df  mov     r9, [rdi+20h]
0x18000c3e3  test    r9, r9
0x18000c3e6  jz      loc_18000C4DA
0x18000c3ec  lea     r14, [rdi+28h]
0x18000c3f0  cmp     [r14], rbx
0x18000c3f3  jz      loc_18000C4DA
0x18000c3f9  mov     [rsp+58h+arg_8], r15
0x18000c3fe  mov     [rsp+58h+var_38], r14
0x18000c403  xor     r8d, r8d; pReturnValue
0x18000c406  mov     edx, eax; nProcNum
0x18000c408  lea     rcx, ?RemoteFW_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18000c40f  call    cs:__imp_NdrClientCall3
0x18000c415  mov     [rsp+58h+arg_8], rax
0x18000c41a  mov     ebx, eax
0x18000c41c  mov     [rsp+58h+var_28], eax
0x18000c420  test    eax, eax
0x18000c422  jz      short loc_18000C45A
0x18000c424  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c42b  cmp     rcx, rsi
0x18000c42e  jz      short loc_18000C455
0x18000c430  test    byte ptr [rcx+1Ch], 1
0x18000c434  jz      short loc_18000C455
0x18000c436  mov     edx, 2Ch ; ','
0x18000c43b  mov     r9d, eax
0x18000c43e  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x18000c445  mov     rcx, [rcx+10h]
0x18000c449  call    WPP_SF_d
0x18000c44e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c455  jmp     loc_18000C296
0x18000c45a  mov     [r14], r15
0x18000c45d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c464  jmp     loc_18000C296
0x18000c469  mov     ebx, eax
0x18000c46b  mov     [rsp+58h+var_28], eax
0x18000c46f  test    eax, eax
0x18000c471  jz      short loc_18000C4BF
0x18000c473  lea     rdx, WPP_GLOBAL_Control
0x18000c47a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c481  cmp     rcx, rdx
0x18000c484  jz      short loc_18000C4AB
0x18000c486  test    byte ptr [rcx+1Ch], 1
0x18000c48a  jz      short loc_18000C4AB
0x18000c48c  mov     edx, 2Dh ; '-'
0x18000c491  mov     r9d, eax
0x18000c494  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x18000c49b  mov     rcx, [rcx+10h]
0x18000c49f  call    WPP_SF_d
0x18000c4a4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c4ab  lea     rsi, WPP_GLOBAL_Control
0x18000c4b2  xor     r15d, r15d
0x18000c4b5  mov     rdi, [rsp+58h+arg_0]
0x18000c4ba  jmp     loc_18000C296
0x18000c4bf  lea     rsi, WPP_GLOBAL_Control
0x18000c4c6  xor     r15d, r15d
0x18000c4c9  mov     rdi, [rsp+58h+arg_0]
0x18000c4ce  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c4d5  jmp     loc_18000C296
0x18000c4da  mov     ebx, 57h ; 'W'
0x18000c4df  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c4e6  cmp     rcx, rsi
0x18000c4e9  jz      loc_18000C2A5
0x18000c4ef  test    byte ptr [rcx+1Ch], 1
0x18000c4f3  jz      loc_18000C296
0x18000c4f9  mov     edx, 2Bh ; '+'
0x18000c4fe  mov     r9d, ebx
0x18000c501  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x18000c508  mov     rcx, [rcx+10h]
0x18000c50c  call    WPP_SF_d
0x18000c511  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c518  jmp     loc_18000C296
0x18000c51d  mov     edx, 17Ah
0x18000c522  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x18000c529  mov     rcx, [rcx+10h]
0x18000c52d  call    WPP_SF_
0x18000c532  jmp     loc_18000C2A5
0x18000c537  cmp     eax, 2
0x18000c53a  jz      short loc_18000C541
0x18000c53c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000c541  mov     rcx, rdi
0x18000c544  call    Int_FWCleanupGPOPolicyStore
0x18000c549  jmp     loc_18000C2D3
0x18000c54e  mov     edx, eax
0x18000c550  call    MicrosoftTelemetryAssertTriggeredArgs
0x18000c555  jmp     loc_18000C2CF
0x18005b810  push    rbp
0x18005b812  sub     rsp, 30h
0x18005b816  mov     rbp, rdx
0x18005b819  mov     rcx, [rcx]
0x18005b81c  mov     ecx, [rcx]; ExceptionCode
0x18005b81e  call    cs:__imp_RpcExceptionFilter
0x18005b824  nop
0x18005b825  add     rsp, 30h
0x18005b829  pop     rbp
0x18005b82a  retn
0x18005b82c  push    rbp
0x18005b82e  sub     rsp, 30h
0x18005b832  mov     rbp, rdx
0x18005b835  mov     rcx, [rcx]
0x18005b838  mov     ecx, [rcx]; ExceptionCode
0x18005b83a  call    cs:__imp_RpcExceptionFilter
0x18005b840  nop
0x18005b841  add     rsp, 30h
0x18005b845  pop     rbp
0x18005b846  retn
```
