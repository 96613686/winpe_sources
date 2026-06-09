# NetworkIsolationGetEnterpriseIdClose

- ea: `0x180010610`
- end: `0x1800108ec`
- name: `NetworkIsolationGetEnterpriseIdClose`
- size: `732`
- prototype: `DWORD __stdcall(HANDLE hOperation, BOOL bWaitForOperation)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800100f0`
- `0x180010180`

## callees

- `0x180005e0c`
- `0x180010610`
- `0x180026798`
- `0x1800294b0`
- `0x18002a1f4`
- `0x18003336c`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x1800108a3`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800108a3`
- `RPCRT4!RpcAsyncCancelCall` at `0x18001086e`
- `RPCRT4!RpcAsyncCancelCall` at `0x18001086e`
- `RPCRT4!RpcBindingFree` at `0x1800107b1`
- `RPCRT4!RpcBindingFree` at `0x1800107b1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001081f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001088e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001081f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001088e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWaitEx` at `0x18001067c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWaitEx` at `0x18001067c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800106a7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180010792`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800106a7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180010792`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180010694`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18001077f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180010694`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18001077f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001064d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001064d`
- `fwbase!FwBaseFree` at `0x18001073c`
- `fwbase!FwBaseFree` at `0x18001073c`
- `fwbase!FwCloseHandle` at `0x1800106ea`
- `fwbase!FwCloseHandle` at `0x180010708`
- `fwbase!FwCloseHandle` at `0x1800106ea`
- `fwbase!FwCloseHandle` at `0x180010708`

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
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 547, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids);
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
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 548, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, 87);
LABEL_11:
    v9 = WPP_GLOBAL_Control;
  }
  if ( v9 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)v9 + 2), 549, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, Reply);
  return Reply;
}

```

## disassembly

```asm
0x180010610  push    rbx
0x180010612  push    rbp
0x180010613  push    rsi
0x180010614  push    r15
0x180010616  sub     rsp, 38h
0x18001061a  mov     rax, cs:__security_cookie
0x180010621  xor     rax, rsp
0x180010624  mov     [rsp+58h+var_30], rax
0x180010629  mov     esi, edx
0x18001062b  mov     rbx, rcx
0x18001062e  mov     rcx, cs:WPP_GLOBAL_Control
0x180010635  lea     r15, WPP_GLOBAL_Control
0x18001063c  cmp     rcx, r15
0x18001063f  jnz     loc_18001083F
0x180010645  mov     [rsp+58h+Reply], 0
0x18001064d  call    cs:__imp_GetTickCount64
0x180010654  nop     dword ptr [rax+rax+00h]
0x180010659  test    rbx, rbx
0x18001065c  jz      loc_1800107D1
0x180010662  xor     ebp, ebp
0x180010664  test    esi, esi
0x180010666  jnz     short loc_1800106BE
0x180010668  mov     rcx, [rbx+98h]; pwa
0x18001066f  test    rcx, rcx
0x180010672  jz      short loc_1800106BE
0x180010674  xor     r9d, r9d; Reserved
0x180010677  xor     r8d, r8d; pftTimeout
0x18001067a  xor     edx, edx; h
0x18001067c  call    cs:__imp_SetThreadpoolWaitEx
0x180010683  nop     dword ptr [rax+rax+00h]
0x180010688  mov     rcx, [rbx+98h]; pwa
0x18001068f  lea     edx, [rsi+1]; fCancelPendingCallbacks
0x180010692  mov     ebp, eax
0x180010694  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x18001069b  nop     dword ptr [rax+rax+00h]
0x1800106a0  mov     rcx, [rbx+98h]; pwa
0x1800106a7  call    cs:__imp_CloseThreadpoolWait
0x1800106ae  nop     dword ptr [rax+rax+00h]
0x1800106b3  mov     qword ptr [rbx+98h], 0
0x1800106be  xor     ecx, ecx
0x1800106c0  xor     eax, eax
0x1800106c2  lock cmpxchg [rbx+0B4h], ecx
0x1800106ca  cmp     eax, 1
0x1800106cd  jz      loc_180010810
0x1800106d3  mov     rcx, [rbx+98h]; pwa
0x1800106da  test    rcx, rcx
0x1800106dd  jnz     loc_18001077A
0x1800106e3  mov     rcx, [rbx+90h]
0x1800106ea  call    cs:__imp_FwCloseHandle
0x1800106f1  nop     dword ptr [rax+rax+00h]
0x1800106f6  mov     rcx, [rbx+0B8h]
0x1800106fd  mov     qword ptr [rbx+90h], 0
0x180010708  call    cs:__imp_FwCloseHandle
0x18001070f  nop     dword ptr [rax+rax+00h]
0x180010714  cmp     qword ptr [rbx], 0
0x180010718  mov     qword ptr [rbx+0B8h], 0
0x180010723  jnz     loc_1800107AE
0x180010729  xor     edx, edx; Val
0x18001072b  mov     r8d, 0C0h; Size
0x180010731  mov     rcx, rbx; void *
0x180010734  call    memset_0
0x180010739  mov     rcx, rbx
0x18001073c  call    cs:__imp_FwBaseFree
0x180010743  nop     dword ptr [rax+rax+00h]
0x180010748  mov     rcx, cs:WPP_GLOBAL_Control
0x18001074f  cmp     rcx, r15
0x180010752  jz      short loc_18001075E
0x180010754  test    byte ptr [rcx+1Ch], 8
0x180010758  jnz     loc_1800108CD
0x18001075e  mov     eax, [rsp+58h+Reply]
0x180010762  mov     rcx, [rsp+58h+var_30]
0x180010767  xor     rcx, rsp; StackCookie
0x18001076a  call    __security_check_cookie
0x18001076f  add     rsp, 38h
0x180010773  pop     r15
0x180010775  pop     rsi
0x180010776  pop     rbp
0x180010777  pop     rbx
0x180010778  retn
0x18001077a  mov     edx, 1; fCancelPendingCallbacks
0x18001077f  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x180010786  nop     dword ptr [rax+rax+00h]
0x18001078b  mov     rcx, [rbx+98h]; pwa
0x180010792  call    cs:__imp_CloseThreadpoolWait
0x180010799  nop     dword ptr [rax+rax+00h]
0x18001079e  mov     qword ptr [rbx+98h], 0
0x1800107a9  jmp     loc_1800106E3
0x1800107ae  mov     rcx, rbx; Binding
0x1800107b1  call    cs:__imp_RpcBindingFree
0x1800107b8  nop     dword ptr [rax+rax+00h]
0x1800107bd  test    eax, eax
0x1800107bf  jz      loc_180010729
0x1800107c5  mov     edx, eax; __annotation("Debug", "TelemetryAssert", "status == RPC_S_OK", "RpcBindingFree")
0x1800107c7  call    MicrosoftTelemetryAssertTriggeredArgs
0x1800107cc  jmp     loc_180010729
0x1800107d1  mov     r9d, 57h ; 'W'
0x1800107d7  mov     [rsp+58h+Reply], r9d
0x1800107dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800107e3  cmp     rcx, r15
0x1800107e6  jz      loc_18001075E
0x1800107ec  test    byte ptr [rcx+1Ch], 1
0x1800107f0  jz      loc_18001074F
0x1800107f6  mov     rcx, [rcx+10h]
0x1800107fa  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x180010801  mov     edx, 224h
0x180010806  call    WPP_SF_d
0x18001080b  jmp     loc_180010748
0x180010810  cmp     esi, 1
0x180010813  jnz     short loc_180010863
0x180010815  mov     rcx, [rbx+0B8h]; hHandle
0x18001081c  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001081f  call    cs:__imp_WaitForSingleObject
0x180010826  nop     dword ptr [rax+rax+00h]
0x18001082b  mov     eax, [rbx+78h]
0x18001082e  test    eax, eax
0x180010830  jz      loc_1800106D3
0x180010836  mov     [rsp+58h+Reply], eax
0x18001083a  jmp     loc_1800106D3
0x18001083f  test    byte ptr [rcx+1Ch], 8
0x180010843  jz      loc_180010645
0x180010849  mov     rcx, [rcx+10h]
0x18001084d  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x180010854  mov     edx, 223h
0x180010859  call    WPP_SF_
0x18001085e  jmp     loc_180010645
0x180010863  cmp     ebp, 1
0x180010866  jnz     short loc_18001089A
0x180010868  lea     rcx, [rbx+8]; pAsync
0x18001086c  mov     edx, ebp; fAbort
0x18001086e  call    cs:__imp_RpcAsyncCancelCall
0x180010875  nop     dword ptr [rax+rax+00h]
0x18001087a  test    eax, eax
0x18001087c  jz      short loc_180010887
0x18001087e  mov     edx, eax; __annotation("Debug", "TelemetryAssert", "Status == RPC_S_OK", "RpcAsyncCancelCall")
0x180010880  call    MicrosoftTelemetryAssertTriggeredArgs
0x180010885  jmp     short loc_18001089A
0x180010887  mov     rcx, [rbx+38h]; hHandle
0x18001088b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001088e  call    cs:__imp_WaitForSingleObject
0x180010895  nop     dword ptr [rax+rax+00h]
0x18001089a  lea     rcx, [rbx+8]; pAsync
0x18001089e  lea     rdx, [rsp+58h+Reply]; Reply
0x1800108a3  call    cs:__imp_RpcAsyncCompleteCall
0x1800108aa  nop     dword ptr [rax+rax+00h]
0x1800108af  mov     edx, 3E5h
0x1800108b4  cmp     eax, edx
0x1800108b6  jnz     short loc_1800108BD
0x1800108b8  call    MicrosoftTelemetryAssertTriggeredArgs; __annotation("Debug", "TelemetryAssert", "Status != RPC_S_ASYNC_CALL_PENDING", "RpcAsyncCompleteCall")
0x1800108bd  cmp     [rsp+58h+Reply], 0
0x1800108c2  jnz     loc_1800106D3
0x1800108c8  jmp     loc_18001082B
0x1800108cd  mov     r9d, [rsp+58h+Reply]
0x1800108d2  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x1800108d9  mov     rcx, [rcx+10h]
0x1800108dd  mov     edx, 225h
0x1800108e2  call    WPP_SF_d
0x1800108e7  jmp     loc_18001075E
```
