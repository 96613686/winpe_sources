# Int_FwRegistrationCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)

- ea: `0x180049930`
- end: `0x180049ba7`
- name: `?Int_FwRegistrationCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z`
- size: `631`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WAIT Wait, TP_WAIT_RESULT WaitResult)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180005954`
- `0x18002514c`
- `0x1800277b0`
- `0x18003104c`
- `0x180049930`
- `0x180049bb0`
- `0x18005e010`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x1800499b0`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800499b0`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180049b2c`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180049b2c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180049acc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180049acc`
- `FWPolicyIOMgr!FwAppContainerChangeFree` at `0x180049a3b`
- `FWPolicyIOMgr!FwAppContainerChangeFree` at `0x180049a3b`

## pseudocode

```c
void __fastcall Int_FwRegistrationCallback(
        PTP_CALLBACK_INSTANCE Instance,
        char *Context,
        PTP_WAIT Wait,
        TP_WAIT_RESULT WaitResult)
{
  __int64 v5; // r9
  FwPolicy2 *v6; // rcx
  __int64 v7; // rdx
  RPC_STATUS v8; // eax
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r8
  unsigned int inited; // eax
  unsigned int Reply; // [rsp+48h] [rbp-20h] BYREF

  Reply = 0;
  if ( Context )
  {
    v8 = RpcAsyncCompleteCall((PRPC_ASYNC_STATE)(Context + 8), &Reply);
    *((_DWORD *)Context + 30) = v8;
    if ( v8 == 997 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v10, v9, v11);
    _InterlockedExchange((volatile __int32 *)Context + 46, 0);
    if ( _InterlockedCompareExchange((volatile signed __int32 *)Context + 45, 0, 0) != 1 )
    {
      v5 = *((unsigned int *)Context + 30);
      Reply = v5;
      if ( (_DWORD)v5 )
      {
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v7 = 478;
          goto LABEL_5;
        }
      }
      else
      {
        (*((void (__fastcall **)(_QWORD, _QWORD))Context + 16))(*((_QWORD *)Context + 17), *((_QWORD *)Context + 21));
        FwAppContainerChangeFree(*((_QWORD *)Context + 21));
        *((_QWORD *)Context + 21) = 0;
        v5 = Reply;
        if ( Reply )
        {
          v6 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v7 = 479;
            goto LABEL_5;
          }
        }
        else
        {
          inited = Int_NetworkIsolationInitRegistrationRpcAsync((struct FW_INTCLIENT_REG_HANDLE_ *)Context);
          v5 = inited;
          Reply = inited;
          if ( inited )
          {
            v6 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v7 = 480;
              goto LABEL_5;
            }
          }
          else
          {
            SetThreadpoolWait(*((PTP_WAIT *)Context + 19), *((HANDLE *)Context + 18), 0);
            if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 481, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids);
            }
            Ndr64AsyncClientCall(
              (MIDL_STUBLESS_PROXY_INFO *)&FW_RESOURCE_INDICATION_ProxyInfo,
              9u,
              0,
              Context + 8,
              *(_QWORD *)Context,
              *((_QWORD *)Context + 20),
              Context + 168);
            *((_DWORD *)Context + 46) = 1;
          }
        }
      }
    }
  }
  else
  {
    v5 = 87;
    Reply = 87;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v7 = 477;
LABEL_5:
      WPP_SF_d(*((_QWORD *)v6 + 2), v7, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, v5);
    }
  }
}

```

## disassembly

```asm
0x180049930  mov     [rsp+arg_0], rbx
0x180049935  mov     [rsp+arg_10], rsi
0x18004993a  push    rdi
0x18004993b  sub     rsp, 60h
0x18004993f  mov     rax, cs:__security_cookie
0x180049946  xor     rax, rsp
0x180049949  mov     [rsp+68h+var_18], rax
0x18004994e  mov     rbx, rdx
0x180049951  mov     [rsp+68h+var_28], rdx
0x180049956  mov     [rsp+68h+Reply], 0
0x18004995e  test    rdx, rdx
0x180049961  jnz     short loc_1800499A7
0x180049963  lea     r9d, [rdx+57h]
0x180049967  mov     [rsp+68h+Reply], r9d
0x18004996c  lea     rax, WPP_GLOBAL_Control
0x180049973  mov     rcx, cs:WPP_GLOBAL_Control
0x18004997a  cmp     rcx, rax
0x18004997d  jz      loc_180049B88
0x180049983  test    byte ptr [rcx+1Ch], 1
0x180049987  jz      loc_180049B88
0x18004998d  mov     edx, 1DDh
0x180049992  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x180049999  mov     rcx, [rcx+10h]
0x18004999d  call    WPP_SF_d
0x1800499a2  jmp     loc_180049B88
0x1800499a7  lea     rdx, [rsp+68h+Reply]; Reply
0x1800499ac  lea     rcx, [rbx+8]; pAsync
0x1800499b0  call    cs:__imp_RpcAsyncCompleteCall
0x1800499b6  mov     [rbx+78h], eax
0x1800499b9  cmp     eax, 3E5h
0x1800499be  jnz     short loc_1800499C5
0x1800499c0  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800499c5  xor     eax, eax
0x1800499c7  xchg    eax, [rbx+0B8h]
0x1800499cd  xor     ecx, ecx
0x1800499cf  xor     eax, eax
0x1800499d1  lock cmpxchg [rbx+0B4h], ecx
0x1800499d9  cmp     eax, 1
0x1800499dc  jz      loc_180049B88
0x1800499e2  mov     r9d, [rbx+78h]
0x1800499e6  mov     [rsp+68h+Reply], r9d
0x1800499eb  test    r9d, r9d
0x1800499ee  jz      short loc_180049A1B
0x1800499f0  lea     rax, WPP_GLOBAL_Control
0x1800499f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800499fe  cmp     rcx, rax
0x180049a01  jz      loc_180049B88
0x180049a07  test    byte ptr [rcx+1Ch], 1
0x180049a0b  jz      loc_180049B88
0x180049a11  mov     edx, 1DEh
0x180049a16  jmp     loc_180049992
0x180049a1b  lea     rdi, [rbx+0A8h]
0x180049a22  mov     rdx, [rdi]
0x180049a25  mov     rcx, [rbx+88h]
0x180049a2c  mov     rax, [rbx+80h]
0x180049a33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049a38  mov     rcx, [rdi]
0x180049a3b  call    cs:__imp_FwAppContainerChangeFree
0x180049a41  mov     qword ptr [rdi], 0
0x180049a48  mov     r9d, [rsp+68h+Reply]
0x180049a4d  test    r9d, r9d
0x180049a50  jz      short loc_180049A7D
0x180049a52  lea     rax, WPP_GLOBAL_Control
0x180049a59  mov     rcx, cs:WPP_GLOBAL_Control
0x180049a60  cmp     rcx, rax
0x180049a63  jz      loc_180049B88
0x180049a69  test    byte ptr [rcx+1Ch], 1
0x180049a6d  jz      loc_180049B88
0x180049a73  mov     edx, 1DFh
0x180049a78  jmp     loc_180049992
0x180049a7d  mov     rcx, rbx; struct FW_INTCLIENT_REG_HANDLE_ *
0x180049a80  call    ?Int_NetworkIsolationInitRegistrationRpcAsync@@YAKPEAUFW_INTCLIENT_REG_HANDLE_@@@Z; Int_NetworkIsolationInitRegistrationRpcAsync(FW_INTCLIENT_REG_HANDLE_ *)
0x180049a85  mov     r9d, eax
0x180049a88  mov     [rsp+68h+Reply], eax
0x180049a8c  test    eax, eax
0x180049a8e  jz      short loc_180049ABB
0x180049a90  lea     rax, WPP_GLOBAL_Control
0x180049a97  mov     rcx, cs:WPP_GLOBAL_Control
0x180049a9e  cmp     rcx, rax
0x180049aa1  jz      loc_180049B88
0x180049aa7  test    byte ptr [rcx+1Ch], 1
0x180049aab  jz      loc_180049B88
0x180049ab1  mov     edx, 1E0h
0x180049ab6  jmp     loc_180049992
0x180049abb  xor     r8d, r8d; pftTimeout
0x180049abe  mov     rdx, [rbx+90h]; h
0x180049ac5  mov     rcx, [rbx+98h]; pwa
0x180049acc  call    cs:__imp_SetThreadpoolWait
0x180049ad2  nop
0x180049ad3  lea     rax, WPP_GLOBAL_Control
0x180049ada  mov     rcx, cs:WPP_GLOBAL_Control
0x180049ae1  cmp     rcx, rax
0x180049ae4  jz      short loc_180049B01
0x180049ae6  test    byte ptr [rcx+1Ch], 4
0x180049aea  jz      short loc_180049B01
0x180049aec  mov     edx, 1E1h
0x180049af1  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x180049af8  mov     rcx, [rcx+10h]
0x180049afc  call    WPP_SF_
0x180049b01  mov     [rsp+68h+var_38], rdi
0x180049b06  mov     rax, [rbx+0A0h]
0x180049b0d  mov     [rsp+68h+var_40], rax
0x180049b12  mov     rax, [rbx]
0x180049b15  mov     [rsp+68h+var_48], rax
0x180049b1a  lea     r9, [rbx+8]
0x180049b1e  xor     r8d, r8d; pReturnValue
0x180049b21  lea     edx, [r8+9]; nProcNum
0x180049b25  lea     rcx, ?FW_RESOURCE_INDICATION_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180049b2c  call    cs:__imp_Ndr64AsyncClientCall
0x180049b32  jmp     short loc_180049B7E
0x180049b34  mov     rbx, [rsp+68h+var_28]
0x180049b39  mov     dword ptr [rbx+0B8h], 0
0x180049b43  mov     [rsp+68h+Reply], eax
0x180049b47  test    eax, eax
0x180049b49  jz      short loc_180049B7E
0x180049b4b  lea     rdx, WPP_GLOBAL_Control
0x180049b52  mov     rcx, cs:WPP_GLOBAL_Control
0x180049b59  cmp     rcx, rdx
0x180049b5c  jz      short loc_180049B7C
0x180049b5e  test    byte ptr [rcx+1Ch], 1
0x180049b62  jz      short loc_180049B7C
0x180049b64  mov     edx, 1E2h
0x180049b69  mov     r9d, eax
0x180049b6c  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x180049b73  mov     rcx, [rcx+10h]
0x180049b77  call    WPP_SF_d
0x180049b7c  jmp     short loc_180049B88
0x180049b7e  mov     dword ptr [rbx+0B8h], 1
0x180049b88  mov     rcx, [rsp+68h+var_18]
0x180049b8d  xor     rcx, rsp; StackCookie
0x180049b90  call    __security_check_cookie
0x180049b95  lea     r11, [rsp+68h+var_8]
0x180049b9a  mov     rbx, [r11+10h]
0x180049b9e  mov     rsi, [r11+20h]
0x180049ba2  mov     rsp, r11
0x180049ba5  pop     rdi
0x180049ba6  retn
0x18005bb34  push    rbp
0x18005bb36  sub     rsp, 40h
0x18005bb3a  mov     rbp, rdx
0x18005bb3d  mov     rcx, [rcx]
0x18005bb40  mov     ecx, [rcx]; ExceptionCode
0x18005bb42  call    cs:__imp_RpcExceptionFilter
0x18005bb48  nop
0x18005bb49  add     rsp, 40h
0x18005bb4d  pop     rbp
0x18005bb4e  retn
```
