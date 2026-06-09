# FWClosePolicyStore

- ea: `0x18000cc80`
- end: `0x18000d0db`
- name: `FWClosePolicyStore`
- size: `1115`
- prototype: ``
- caller_count: `33`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180002474`
- `0x1800037dc`
- `0x180005f10`
- `0x180006874`
- `0x18000b4b0`
- `0x18000bea0`
- `0x18000c810`
- `0x18000c9e0`
- `0x180018270`
- `0x1800191e0`
- `0x18001ae24`
- `0x18001cf1c`
- `0x18001f140`
- `0x180020f98`
- `0x180021b60`
- `0x180027370`
- `0x180028af4`
- `0x180028c60`
- `0x180030468`
- `0x180032d78`
- `0x180034fe0`
- `0x180035340`
- `0x180035500`
- `0x180035850`
- `0x180035c10`
- `0x180049680`
- `0x18004adac`
- `0x18004e080`
- `0x18004f530`
- `0x18004fed0`
- `0x180052c60`
- `0x180054570`
- `0x18005c844`

## callees

- `0x180005e0c`
- `0x18000cc80`
- `0x180026798`
- `0x180026c9c`
- `0x18003336c`
- `0x180054d58`

## import_xrefs

- `RPCRT4!RpcExceptionFilter` at `0x18005fa2e`
- `RPCRT4!RpcExceptionFilter` at `0x18005fa50`
- `RPCRT4!RpcExceptionFilter` at `0x18005fa2e`
- `RPCRT4!RpcExceptionFilter` at `0x18005fa50`
- `RPCRT4!NdrClientCall3` at `0x18000cd34`
- `RPCRT4!NdrClientCall3` at `0x18000cf8a`
- `RPCRT4!NdrClientCall3` at `0x18000cd34`
- `RPCRT4!NdrClientCall3` at `0x18000cf8a`
- `RPCRT4!RpcBindingFree` at `0x18000ce23`
- `RPCRT4!RpcBindingFree` at `0x18000ce23`
- `ntdll!EtwEventWrite` at `0x18000ccaf`
- `ntdll!EtwEventWrite` at `0x18000ce83`
- `ntdll!EtwEventWrite` at `0x18000ccaf`
- `ntdll!EtwEventWrite` at `0x18000ce83`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000ccd8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000ccd8`
- `fwbase!FwBaseFree` at `0x18000ce3f`
- `fwbase!FwBaseFree` at `0x18000ce52`
- `fwbase!FwBaseFree` at `0x18000ce3f`
- `fwbase!FwBaseFree` at `0x18000ce52`

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
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids);
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
    v12 = 38;
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
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, Pointer);
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
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, 87);
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
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, v13);
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
    v12 = 42;
LABEL_51:
    WPP_SF_d(*((_QWORD *)v7 + 2), v12, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, 87);
    goto LABEL_52;
  }
LABEL_16:
  if ( v7 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)v7 + 2), 377, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids);
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
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids);
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_CLNT_API_Exit_ClosePolicyStore, 0, 0);
  return v6;
}

```

## disassembly

```asm
0x18000cc80  mov     [rsp+arg_10], rbx
0x18000cc85  mov     [rsp+arg_18], rsi
0x18000cc8a  push    rdi
0x18000cc8b  push    r14
0x18000cc8d  push    r15
0x18000cc8f  sub     rsp, 40h
0x18000cc93  mov     rdi, rcx
0x18000cc96  mov     rcx, cs:g_Provider
0x18000cc9d  test    rcx, rcx
0x18000cca0  jz      short loc_18000CCBB
0x18000cca2  xor     r9d, r9d
0x18000cca5  xor     r8d, r8d
0x18000cca8  lea     rdx, MPS_CLNT_API_Enter_ClosePolicyStore
0x18000ccaf  call    cs:__imp_EtwEventWrite
0x18000ccb6  nop     dword ptr [rax+rax+00h]
0x18000ccbb  lea     rsi, WPP_GLOBAL_Control
0x18000ccc2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ccc9  cmp     rcx, rsi
0x18000cccc  jz      short loc_18000CCD8
0x18000ccce  test    byte ptr [rcx+1Ch], 8
0x18000ccd2  jnz     loc_18000CEF2
0x18000ccd8  call    cs:__imp_GetTickCount64
0x18000ccdf  nop     dword ptr [rax+rax+00h]
0x18000cce4  test    rdi, rdi
0x18000cce7  jz      loc_18000CEC3
0x18000cced  mov     [rsp+58h+arg_0], rdi
0x18000ccf2  mov     eax, [rdi+4]
0x18000ccf5  test    eax, eax
0x18000ccf7  jnz     loc_18000CF4B
0x18000ccfd  mov     r9, [rdi+20h]
0x18000cd01  test    r9, r9
0x18000cd04  jz      loc_18000CF0C
0x18000cd0a  lea     r14, [rdi+28h]
0x18000cd0e  cmp     qword ptr [r14], 0
0x18000cd12  jz      loc_18000CF0C
0x18000cd18  xor     r15d, r15d
0x18000cd1b  mov     [rsp+58h+arg_8], r15
0x18000cd20  mov     [rsp+58h+var_38], r14
0x18000cd25  xor     r8d, r8d; pReturnValue
0x18000cd28  mov     edx, 1; nProcNum
0x18000cd2d  lea     rcx, ?FW_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18000cd34  call    cs:__imp_NdrClientCall3
0x18000cd3b  nop     dword ptr [rax+rax+00h]
0x18000cd40  mov     rbx, rax
0x18000cd43  mov     [rsp+58h+arg_8], rax
0x18000cd48  mov     [rsp+58h+var_28], eax
0x18000cd4c  test    eax, eax
0x18000cd4e  jz      short loc_18000CD83
0x18000cd50  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cd57  cmp     rcx, rsi
0x18000cd5a  jz      short loc_18000CD81
0x18000cd5c  test    byte ptr [rcx+1Ch], 1
0x18000cd60  jz      short loc_18000CD81
0x18000cd62  mov     edx, 28h ; '('
0x18000cd67  mov     r9d, eax
0x18000cd6a  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x18000cd71  mov     rcx, [rcx+10h]
0x18000cd75  call    WPP_SF_d
0x18000cd7a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cd81  jmp     short loc_18000CDF8
0x18000cd83  mov     [r14], r15
0x18000cd86  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cd8d  jmp     short loc_18000CDF8
0x18000cd8f  mov     ebx, eax
0x18000cd91  mov     [rsp+58h+var_28], eax
0x18000cd95  test    eax, eax
0x18000cd97  jz      short loc_18000CDE2
0x18000cd99  lea     rdx, WPP_GLOBAL_Control
0x18000cda0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cda7  cmp     rcx, rdx
0x18000cdaa  jz      short loc_18000CDD1
0x18000cdac  test    byte ptr [rcx+1Ch], 1
0x18000cdb0  jz      short loc_18000CDD1
0x18000cdb2  mov     edx, 29h ; ')'
0x18000cdb7  mov     r9d, eax
0x18000cdba  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x18000cdc1  mov     rcx, [rcx+10h]
0x18000cdc5  call    WPP_SF_d
0x18000cdca  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cdd1  lea     rsi, WPP_GLOBAL_Control
0x18000cdd8  xor     r15d, r15d
0x18000cddb  mov     rdi, [rsp+58h+arg_0]
0x18000cde0  jmp     short loc_18000CDF8
0x18000cde2  lea     rsi, WPP_GLOBAL_Control
0x18000cde9  xor     r15d, r15d
0x18000cdec  mov     rdi, [rsp+58h+arg_0]
0x18000cdf1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cdf8  cmp     rcx, rsi
0x18000cdfb  jz      short loc_18000CE07
0x18000cdfd  test    byte ptr [rcx+1Ch], 8
0x18000ce01  jnz     loc_18000D09E
0x18000ce07  test    rdi, rdi
0x18000ce0a  jz      short loc_18000CE4F
0x18000ce0c  mov     eax, [rdi+4]
0x18000ce0f  cmp     eax, 1
0x18000ce12  ja      loc_18000D0B8
0x18000ce18  cmp     qword ptr [rdi+20h], 0
0x18000ce1d  jz      short loc_18000CE3B
0x18000ce1f  lea     rcx, [rdi+20h]; Binding
0x18000ce23  call    cs:__imp_RpcBindingFree
0x18000ce2a  nop     dword ptr [rax+rax+00h]
0x18000ce2f  test    eax, eax
0x18000ce31  jnz     loc_18000D0CF
0x18000ce37  mov     [rdi+20h], r15
0x18000ce3b  mov     rcx, [rdi+8]
0x18000ce3f  call    cs:__imp_FwBaseFree
0x18000ce46  nop     dword ptr [rax+rax+00h]
0x18000ce4b  mov     [rdi+8], r15
0x18000ce4f  mov     rcx, rdi
0x18000ce52  call    cs:__imp_FwBaseFree
0x18000ce59  nop     dword ptr [rax+rax+00h]
0x18000ce5e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ce65  cmp     rcx, rsi
0x18000ce68  jnz     short loc_18000CEA6
0x18000ce6a  mov     rcx, cs:g_Provider
0x18000ce71  test    rcx, rcx
0x18000ce74  jz      short loc_18000CE8F
0x18000ce76  xor     r9d, r9d
0x18000ce79  xor     r8d, r8d
0x18000ce7c  lea     rdx, MPS_CLNT_API_Exit_ClosePolicyStore
0x18000ce83  call    cs:__imp_EtwEventWrite
0x18000ce8a  nop     dword ptr [rax+rax+00h]
0x18000ce8f  mov     eax, ebx
0x18000ce91  mov     rbx, [rsp+58h+arg_10]
0x18000ce96  mov     rsi, [rsp+58h+arg_18]
0x18000ce9b  add     rsp, 40h
0x18000ce9f  pop     r15
0x18000cea1  pop     r14
0x18000cea3  pop     rdi
0x18000cea4  retn
0x18000cea6  test    byte ptr [rcx+1Ch], 8
0x18000ceaa  jz      short loc_18000CE6A
0x18000ceac  mov     edx, 2Dh ; '-'
0x18000ceb1  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x18000ceb8  mov     rcx, [rcx+10h]
0x18000cebc  call    WPP_SF_
0x18000cec1  jmp     short loc_18000CE6A
0x18000cec3  xor     r15d, r15d
0x18000cec6  mov     edi, r15d
0x18000cec9  mov     ebx, 57h ; 'W'
0x18000cece  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ced5  cmp     rcx, rsi
0x18000ced8  jz      loc_18000CE07
0x18000cede  test    byte ptr [rcx+1Ch], 1
0x18000cee2  jz      loc_18000CDF8
0x18000cee8  mov     edx, 26h ; '&'
0x18000ceed  jmp     loc_18000D07F
0x18000cef2  mov     edx, 25h ; '%'
0x18000cef7  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x18000cefe  mov     rcx, [rcx+10h]
0x18000cf02  call    WPP_SF_
0x18000cf07  jmp     loc_18000CCD8
0x18000cf0c  mov     ebx, 57h ; 'W'
0x18000cf11  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cf18  cmp     rcx, rsi
0x18000cf1b  jz      short loc_18000CF43
0x18000cf1d  test    byte ptr [rcx+1Ch], 1
0x18000cf21  jz      short loc_18000CF43
0x18000cf23  mov     edx, 27h ; '''
0x18000cf28  mov     r9d, ebx
0x18000cf2b  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x18000cf32  mov     rcx, [rcx+10h]
0x18000cf36  call    WPP_SF_d
0x18000cf3b  xor     r15d, r15d
0x18000cf3e  jmp     loc_18000D092
0x18000cf43  xor     r15d, r15d
0x18000cf46  jmp     loc_18000CDF8
0x18000cf4b  xor     r15d, r15d
0x18000cf4e  mov     ebx, r15d
0x18000cf51  cmp     eax, 1
0x18000cf54  jnz     loc_18000D092
0x18000cf5a  mov     r9, [rdi+20h]
0x18000cf5e  test    r9, r9
0x18000cf61  jz      loc_18000D05B
0x18000cf67  lea     r14, [rdi+28h]
0x18000cf6b  cmp     [r14], rbx
0x18000cf6e  jz      loc_18000D05B
0x18000cf74  mov     [rsp+58h+arg_8], r15
0x18000cf79  mov     [rsp+58h+var_38], r14
0x18000cf7e  xor     r8d, r8d; pReturnValue
0x18000cf81  mov     edx, eax; nProcNum
0x18000cf83  lea     rcx, ?RemoteFW_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18000cf8a  call    cs:__imp_NdrClientCall3
0x18000cf91  nop     dword ptr [rax+rax+00h]
0x18000cf96  mov     [rsp+58h+arg_8], rax
0x18000cf9b  mov     ebx, eax
0x18000cf9d  mov     [rsp+58h+var_28], eax
0x18000cfa1  test    eax, eax
0x18000cfa3  jz      short loc_18000CFDB
0x18000cfa5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cfac  cmp     rcx, rsi
0x18000cfaf  jz      short loc_18000CFD6
0x18000cfb1  test    byte ptr [rcx+1Ch], 1
0x18000cfb5  jz      short loc_18000CFD6
0x18000cfb7  mov     edx, 2Bh ; '+'
0x18000cfbc  mov     r9d, eax
0x18000cfbf  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x18000cfc6  mov     rcx, [rcx+10h]
0x18000cfca  call    WPP_SF_d
0x18000cfcf  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cfd6  jmp     loc_18000CDF8
0x18000cfdb  mov     [r14], r15
0x18000cfde  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cfe5  jmp     loc_18000CDF8
0x18000cfea  mov     ebx, eax
0x18000cfec  mov     [rsp+58h+var_28], eax
0x18000cff0  test    eax, eax
0x18000cff2  jz      short loc_18000D040
0x18000cff4  lea     rdx, WPP_GLOBAL_Control
0x18000cffb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d002  cmp     rcx, rdx
0x18000d005  jz      short loc_18000D02C
0x18000d007  test    byte ptr [rcx+1Ch], 1
0x18000d00b  jz      short loc_18000D02C
0x18000d00d  mov     edx, 2Ch ; ','
0x18000d012  mov     r9d, eax
0x18000d015  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x18000d01c  mov     rcx, [rcx+10h]
0x18000d020  call    WPP_SF_d
0x18000d025  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d02c  lea     rsi, WPP_GLOBAL_Control
0x18000d033  xor     r15d, r15d
0x18000d036  mov     rdi, [rsp+58h+arg_0]
0x18000d03b  jmp     loc_18000CDF8
0x18000d040  lea     rsi, WPP_GLOBAL_Control
0x18000d047  xor     r15d, r15d
0x18000d04a  mov     rdi, [rsp+58h+arg_0]
0x18000d04f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d056  jmp     loc_18000CDF8
0x18000d05b  mov     ebx, 57h ; 'W'
0x18000d060  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d067  cmp     rcx, rsi
0x18000d06a  jz      loc_18000CE07
0x18000d070  test    byte ptr [rcx+1Ch], 1
0x18000d074  jz      loc_18000CDF8
0x18000d07a  mov     edx, 2Ah ; '*'
0x18000d07f  mov     r9d, ebx
0x18000d082  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x18000d089  mov     rcx, [rcx+10h]
0x18000d08d  call    WPP_SF_d
0x18000d092  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d099  jmp     loc_18000CDF8
0x18000d09e  mov     edx, 179h
0x18000d0a3  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x18000d0aa  mov     rcx, [rcx+10h]
0x18000d0ae  call    WPP_SF_
0x18000d0b3  jmp     loc_18000CE07
0x18000d0b8  cmp     eax, 2
0x18000d0bb  jz      short loc_18000D0C2
0x18000d0bd  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "phClient->HandleType == FWINT_CLIENT_HANDLE_GPO")
0x18000d0c2  mov     rcx, rdi
0x18000d0c5  call    Int_FWCleanupGPOPolicyStore
0x18000d0ca  jmp     loc_18000CE3B
0x18000d0cf  mov     edx, eax; __annotation("Debug", "TelemetryAssert", "status == RPC_S_OK", "RpcBindingFree")
0x18000d0d1  call    MicrosoftTelemetryAssertTriggeredArgs
0x18000d0d6  jmp     loc_18000CE37
0x18005fa20  push    rbp
0x18005fa22  sub     rsp, 30h
0x18005fa26  mov     rbp, rdx
0x18005fa29  mov     rcx, [rcx]
0x18005fa2c  mov     ecx, [rcx]; ExceptionCode
0x18005fa2e  call    cs:__imp_RpcExceptionFilter
0x18005fa35  nop     dword ptr [rax+rax+00h]
0x18005fa3a  nop
0x18005fa3b  add     rsp, 30h
0x18005fa3f  pop     rbp
0x18005fa40  retn
0x18005fa42  push    rbp
0x18005fa44  sub     rsp, 30h
0x18005fa48  mov     rbp, rdx
0x18005fa4b  mov     rcx, [rcx]
0x18005fa4e  mov     ecx, [rcx]; ExceptionCode
0x18005fa50  call    cs:__imp_RpcExceptionFilter
0x18005fa57  nop     dword ptr [rax+rax+00h]
0x18005fa5c  nop
0x18005fa5d  add     rsp, 30h
0x18005fa61  pop     rbp
0x18005fa62  retn
```
