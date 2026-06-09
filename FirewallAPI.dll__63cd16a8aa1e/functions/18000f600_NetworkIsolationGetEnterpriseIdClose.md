# NetworkIsolationGetEnterpriseIdClose

- ea: `0x18000f600`
- end: `0x18000f87b`
- name: `NetworkIsolationGetEnterpriseIdClose`
- size: `635`
- prototype: `DWORD __stdcall(HANDLE hOperation, BOOL bWaitForOperation)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f110`
- `0x18000f1a0`

## callees

- `0x180005954`
- `0x18000f600`
- `0x180024c3c`
- `0x1800277b0`
- `0x1800284c4`
- `0x18003104c`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x18000f838`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18000f838`
- `RPCRT4!RpcAsyncCancelCall` at `0x18000f80f`
- `RPCRT4!RpcAsyncCancelCall` at `0x18000f80f`
- `RPCRT4!RpcBindingFree` at `0x18000f766`
- `RPCRT4!RpcBindingFree` at `0x18000f766`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000f7c6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000f829`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000f7c6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000f829`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWaitEx` at `0x18000f666`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWaitEx` at `0x18000f666`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18000f685`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18000f74d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18000f685`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18000f74d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18000f678`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18000f740`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18000f678`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18000f740`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000f63d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000f63d`
- `fwbase!FwBaseFree` at `0x18000f704`
- `fwbase!FwBaseFree` at `0x18000f704`
- `fwbase!FwCloseHandle` at `0x18000f6c2`
- `fwbase!FwCloseHandle` at `0x18000f6da`
- `fwbase!FwCloseHandle` at `0x18000f6c2`
- `fwbase!FwCloseHandle` at `0x18000f6da`

## pseudocode

```c
DWORD __stdcall NetworkIsolationGetEnterpriseIdClose(HANDLE hOperation, BOOL bWaitForOperation)
{
  BOOL v4; // ebp
  struct _TP_WAIT *v5; // rcx
  struct _TP_WAIT *v6; // rcx
  __int64 v7; // rcx
  bool v8; // zf
  FwPolicy2 *v9; // rcx
  unsigned int v11; // eax
  __int64 v12; // rcx
  unsigned int v13; // eax
  __int64 v14; // rcx
  __int64 v15; // rcx
  DWORD Reply; // [rsp+20h] [rbp-38h] BYREF

  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 548, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids);
  Reply = 0;
  GetTickCount64();
  if ( hOperation )
  {
    v4 = 0;
    if ( !bWaitForOperation )
    {
      v5 = (struct _TP_WAIT *)*((_QWORD *)hOperation + 19);
      if ( v5 )
      {
        v4 = SetThreadpoolWaitEx(v5, 0, 0, 0);
        WaitForThreadpoolWaitCallbacks(*((PTP_WAIT *)hOperation + 19), 1);
        CloseThreadpoolWait(*((PTP_WAIT *)hOperation + 19));
        *((_QWORD *)hOperation + 19) = 0;
      }
    }
    if ( _InterlockedCompareExchange((volatile signed __int32 *)hOperation + 45, 0, 0) != 1 )
      goto LABEL_7;
    if ( bWaitForOperation )
    {
      WaitForSingleObject(*((HANDLE *)hOperation + 23), 0xFFFFFFFF);
    }
    else
    {
      if ( v4 )
      {
        v13 = RpcAsyncCancelCall((PRPC_ASYNC_STATE)((char *)hOperation + 8), 1);
        if ( v13 )
          MicrosoftTelemetryAssertTriggeredArgs(v14, v13);
        else
          WaitForSingleObject(*((HANDLE *)hOperation + 7), 0xFFFFFFFF);
      }
      if ( RpcAsyncCompleteCall((PRPC_ASYNC_STATE)((char *)hOperation + 8), &Reply) == 997 )
        MicrosoftTelemetryAssertTriggeredArgs(v15, 997);
      if ( Reply )
        goto LABEL_7;
    }
    if ( *((_DWORD *)hOperation + 30) )
      Reply = *((_DWORD *)hOperation + 30);
LABEL_7:
    v6 = (struct _TP_WAIT *)*((_QWORD *)hOperation + 19);
    if ( v6 )
    {
      WaitForThreadpoolWaitCallbacks(v6, 1);
      CloseThreadpoolWait(*((PTP_WAIT *)hOperation + 19));
      *((_QWORD *)hOperation + 19) = 0;
    }
    FwCloseHandle(*((_QWORD *)hOperation + 18));
    v7 = *((_QWORD *)hOperation + 23);
    *((_QWORD *)hOperation + 18) = 0;
    FwCloseHandle(v7);
    v8 = *(_QWORD *)hOperation == 0;
    *((_QWORD *)hOperation + 23) = 0;
    if ( !v8 )
    {
      v11 = RpcBindingFree((RPC_BINDING_HANDLE *)hOperation);
      if ( v11 )
        MicrosoftTelemetryAssertTriggeredArgs(v12, v11);
    }
    memset_0(hOperation, 0, 0xC0u);
    FwBaseFree(hOperation);
    goto LABEL_11;
  }
  Reply = 87;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control )
    return Reply;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 549, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, 87);
LABEL_11:
    v9 = WPP_GLOBAL_Control;
  }
  if ( v9 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)v9 + 2), 550, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, Reply);
  return Reply;
}

```

## disassembly

```asm
0x18000f600  push    rbx
0x18000f602  push    rbp
0x18000f603  push    rsi
0x18000f604  push    r15
0x18000f606  sub     rsp, 38h
0x18000f60a  mov     rax, cs:__security_cookie
0x18000f611  xor     rax, rsp
0x18000f614  mov     [rsp+58h+var_30], rax
0x18000f619  mov     esi, edx
0x18000f61b  mov     rbx, rcx
0x18000f61e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f625  lea     r15, WPP_GLOBAL_Control
0x18000f62c  cmp     rcx, r15
0x18000f62f  jnz     loc_18000F7E0
0x18000f635  mov     [rsp+58h+Reply], 0
0x18000f63d  call    cs:__imp_GetTickCount64
0x18000f643  test    rbx, rbx
0x18000f646  jz      loc_18000F77C
0x18000f64c  xor     ebp, ebp
0x18000f64e  test    esi, esi
0x18000f650  jnz     short loc_18000F696
0x18000f652  mov     rcx, [rbx+98h]; pwa
0x18000f659  test    rcx, rcx
0x18000f65c  jz      short loc_18000F696
0x18000f65e  xor     r9d, r9d; Reserved
0x18000f661  xor     r8d, r8d; pftTimeout
0x18000f664  xor     edx, edx; h
0x18000f666  call    cs:__imp_SetThreadpoolWaitEx
0x18000f66c  mov     rcx, [rbx+98h]; pwa
0x18000f673  lea     edx, [rsi+1]; fCancelPendingCallbacks
0x18000f676  mov     ebp, eax
0x18000f678  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x18000f67e  mov     rcx, [rbx+98h]; pwa
0x18000f685  call    cs:__imp_CloseThreadpoolWait
0x18000f68b  mov     qword ptr [rbx+98h], 0
0x18000f696  xor     ecx, ecx
0x18000f698  xor     eax, eax
0x18000f69a  lock cmpxchg [rbx+0B4h], ecx
0x18000f6a2  cmp     eax, 1
0x18000f6a5  jz      loc_18000F7B7
0x18000f6ab  mov     rcx, [rbx+98h]; pwa
0x18000f6b2  test    rcx, rcx
0x18000f6b5  jnz     loc_18000F73B
0x18000f6bb  mov     rcx, [rbx+90h]
0x18000f6c2  call    cs:__imp_FwCloseHandle
0x18000f6c8  mov     rcx, [rbx+0B8h]
0x18000f6cf  mov     qword ptr [rbx+90h], 0
0x18000f6da  call    cs:__imp_FwCloseHandle
0x18000f6e0  cmp     qword ptr [rbx], 0
0x18000f6e4  mov     qword ptr [rbx+0B8h], 0
0x18000f6ef  jnz     short loc_18000F763
0x18000f6f1  xor     edx, edx; Val
0x18000f6f3  mov     r8d, 0C0h; Size
0x18000f6f9  mov     rcx, rbx; void *
0x18000f6fc  call    memset_0
0x18000f701  mov     rcx, rbx
0x18000f704  call    cs:__imp_FwBaseFree
0x18000f70a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f711  cmp     rcx, r15
0x18000f714  jz      short loc_18000F720
0x18000f716  test    byte ptr [rcx+1Ch], 8
0x18000f71a  jnz     loc_18000F85C
0x18000f720  mov     eax, [rsp+58h+Reply]
0x18000f724  mov     rcx, [rsp+58h+var_30]
0x18000f729  xor     rcx, rsp; StackCookie
0x18000f72c  call    __security_check_cookie
0x18000f731  add     rsp, 38h
0x18000f735  pop     r15
0x18000f737  pop     rsi
0x18000f738  pop     rbp
0x18000f739  pop     rbx
0x18000f73a  retn
0x18000f73b  mov     edx, 1; fCancelPendingCallbacks
0x18000f740  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x18000f746  mov     rcx, [rbx+98h]; pwa
0x18000f74d  call    cs:__imp_CloseThreadpoolWait
0x18000f753  mov     qword ptr [rbx+98h], 0
0x18000f75e  jmp     loc_18000F6BB
0x18000f763  mov     rcx, rbx; Binding
0x18000f766  call    cs:__imp_RpcBindingFree
0x18000f76c  test    eax, eax
0x18000f76e  jz      short loc_18000F6F1
0x18000f770  mov     edx, eax
0x18000f772  call    MicrosoftTelemetryAssertTriggeredArgs
0x18000f777  jmp     loc_18000F6F1
0x18000f77c  mov     r9d, 57h ; 'W'
0x18000f782  mov     [rsp+58h+Reply], r9d
0x18000f787  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f78e  cmp     rcx, r15
0x18000f791  jz      short loc_18000F720
0x18000f793  test    byte ptr [rcx+1Ch], 1
0x18000f797  jz      loc_18000F711
0x18000f79d  mov     rcx, [rcx+10h]
0x18000f7a1  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x18000f7a8  mov     edx, 225h
0x18000f7ad  call    WPP_SF_d
0x18000f7b2  jmp     loc_18000F70A
0x18000f7b7  cmp     esi, 1
0x18000f7ba  jnz     short loc_18000F804
0x18000f7bc  mov     rcx, [rbx+0B8h]; hHandle
0x18000f7c3  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000f7c6  call    cs:__imp_WaitForSingleObject
0x18000f7cc  mov     eax, [rbx+78h]
0x18000f7cf  test    eax, eax
0x18000f7d1  jz      loc_18000F6AB
0x18000f7d7  mov     [rsp+58h+Reply], eax
0x18000f7db  jmp     loc_18000F6AB
0x18000f7e0  test    byte ptr [rcx+1Ch], 8
0x18000f7e4  jz      loc_18000F635
0x18000f7ea  mov     rcx, [rcx+10h]
0x18000f7ee  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x18000f7f5  mov     edx, 224h
0x18000f7fa  call    WPP_SF_
0x18000f7ff  jmp     loc_18000F635
0x18000f804  cmp     ebp, 1
0x18000f807  jnz     short loc_18000F82F
0x18000f809  lea     rcx, [rbx+8]; pAsync
0x18000f80d  mov     edx, ebp; fAbort
0x18000f80f  call    cs:__imp_RpcAsyncCancelCall
0x18000f815  test    eax, eax
0x18000f817  jz      short loc_18000F822
0x18000f819  mov     edx, eax
0x18000f81b  call    MicrosoftTelemetryAssertTriggeredArgs
0x18000f820  jmp     short loc_18000F82F
0x18000f822  mov     rcx, [rbx+38h]; hHandle
0x18000f826  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000f829  call    cs:__imp_WaitForSingleObject
0x18000f82f  lea     rcx, [rbx+8]; pAsync
0x18000f833  lea     rdx, [rsp+58h+Reply]; Reply
0x18000f838  call    cs:__imp_RpcAsyncCompleteCall
0x18000f83e  mov     edx, 3E5h
0x18000f843  cmp     eax, edx
0x18000f845  jnz     short loc_18000F84C
0x18000f847  call    MicrosoftTelemetryAssertTriggeredArgs
0x18000f84c  cmp     [rsp+58h+Reply], 0
0x18000f851  jnz     loc_18000F6AB
0x18000f857  jmp     loc_18000F7CC
0x18000f85c  mov     r9d, [rsp+58h+Reply]
0x18000f861  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x18000f868  mov     rcx, [rcx+10h]
0x18000f86c  mov     edx, 226h
0x18000f871  call    WPP_SF_d
0x18000f876  jmp     loc_18000F720
```
