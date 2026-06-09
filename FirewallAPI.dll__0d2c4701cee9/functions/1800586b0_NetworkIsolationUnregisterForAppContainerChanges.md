# NetworkIsolationUnregisterForAppContainerChanges

- ea: `0x1800586b0`
- end: `0x18005897a`
- name: `NetworkIsolationUnregisterForAppContainerChanges`
- size: `714`
- prototype: `DWORD __stdcall(HANDLE registrationObject)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800580b0`

## callees

- `0x180005e0c`
- `0x180026798`
- `0x180026c9c`
- `0x1800294b0`
- `0x18002a1f4`
- `0x18003336c`
- `0x1800586b0`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x1800588bb`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800588bb`
- `RPCRT4!RpcExceptionFilter` at `0x18006039e`
- `RPCRT4!RpcExceptionFilter` at `0x18006039e`
- `RPCRT4!RpcAsyncCancelCall` at `0x180058879`
- `RPCRT4!RpcAsyncCancelCall` at `0x180058879`
- `RPCRT4!NdrClientCall3` at `0x180058823`
- `RPCRT4!NdrClientCall3` at `0x180058823`
- `RPCRT4!RpcBindingFree` at `0x1800588f8`
- `RPCRT4!RpcBindingFree` at `0x1800588f8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800588a6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800588a6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWaitEx` at `0x1800587b2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWaitEx` at `0x1800587b2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800587e4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800587e4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800587d1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800587d1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18005870c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18005870c`
- `fwbase!FwBaseFree` at `0x180058922`
- `fwbase!FwBaseFree` at `0x180058922`
- `fwbase!FwCloseHandle` at `0x1800588dd`
- `fwbase!FwCloseHandle` at `0x1800588dd`

## pseudocode

```c
DWORD __stdcall NetworkIsolationUnregisterForAppContainerChanges(HANDLE registrationObject)
{
  FwPolicy2 *v3; // rcx
  __int64 v4; // rdx
  _QWORD *v5; // rsi
  BOOL v6; // r12d
  struct _TP_WAIT *v7; // rcx
  unsigned int v8; // esi
  unsigned int v9; // eax
  __int64 v10; // rcx
  RPC_STATUS v11; // eax
  unsigned int v12; // eax
  __int64 v13; // rcx
  DWORD Reply; // [rsp+58h] [rbp-50h] BYREF

  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 492, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids);
  Reply = 0;
  GetTickCount64();
  if ( registrationObject )
  {
    v5 = (char *)registrationObject + 160;
    if ( *((_QWORD *)registrationObject + 20) )
    {
      v6 = 0;
      v7 = (struct _TP_WAIT *)*((_QWORD *)registrationObject + 19);
      if ( v7 )
      {
        v6 = SetThreadpoolWaitEx(v7, 0, 0, 0);
        WaitForThreadpoolWaitCallbacks(*((PTP_WAIT *)registrationObject + 19), 1);
        CloseThreadpoolWait(*((PTP_WAIT *)registrationObject + 19));
        *((_QWORD *)registrationObject + 19) = 0;
      }
      if ( *v5 )
      {
        _InterlockedExchange((volatile __int32 *)registrationObject + 45, 1);
        Reply = (unsigned int)NdrClientCall3(
                                (MIDL_STUBLESS_PROXY_INFO *)&FW_RESOURCE_INDICATION_ProxyInfo,
                                0xAu,
                                0,
                                *(_QWORD *)registrationObject,
                                (char *)registrationObject + 160).Pointer;
        *v5 = 0;
      }
      if ( _InterlockedCompareExchange((volatile signed __int32 *)registrationObject + 46, 0, 0) == 1 )
      {
        v8 = 0;
        if ( Reply )
        {
          v9 = RpcAsyncCancelCall((PRPC_ASYNC_STATE)((char *)registrationObject + 8), 1);
          v8 = v9;
          if ( v9 )
            MicrosoftTelemetryAssertTriggeredArgs(v10, v9);
        }
        if ( v6 && !v8 )
          WaitForSingleObject(*((HANDLE *)registrationObject + 18), 0xFFFFFFFF);
        v11 = RpcAsyncCompleteCall((PRPC_ASYNC_STATE)((char *)registrationObject + 8), &Reply);
        *((_DWORD *)registrationObject + 30) = v11;
        if ( v11 == 997 )
          MicrosoftTelemetryAssertTriggeredNoArgs();
      }
      FwCloseHandle(*((_QWORD *)registrationObject + 18));
      *((_QWORD *)registrationObject + 18) = 0;
      if ( *(_QWORD *)registrationObject )
      {
        v12 = RpcBindingFree((RPC_BINDING_HANDLE *)registrationObject);
        if ( v12 )
          MicrosoftTelemetryAssertTriggeredArgs(v13, v12);
      }
      memset_0(registrationObject, 0, 0xC0u);
      FwBaseFree(registrationObject);
      goto LABEL_30;
    }
    Reply = 87;
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control )
      return Reply;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_31;
    v4 = 494;
LABEL_8:
    WPP_SF_d(*((_QWORD *)v3 + 2), v4, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, 87);
LABEL_30:
    v3 = WPP_GLOBAL_Control;
    goto LABEL_31;
  }
  Reply = 87;
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control )
    return Reply;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v4 = 493;
    goto LABEL_8;
  }
LABEL_31:
  if ( v3 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)v3 + 2), 495, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, Reply);
  return Reply;
}

```

## disassembly

```asm
0x1800586b0  push    rbx
0x1800586b2  push    rsi
0x1800586b3  push    rdi
0x1800586b4  push    r12
0x1800586b6  push    r14
0x1800586b8  push    r15
0x1800586ba  sub     rsp, 78h
0x1800586be  mov     rax, cs:__security_cookie
0x1800586c5  xor     rax, rsp
0x1800586c8  mov     [rsp+0A8h+var_48], rax
0x1800586cd  mov     r15, rcx
0x1800586d0  mov     rbx, rcx
0x1800586d3  mov     [rsp+0A8h+var_68], rcx
0x1800586d8  lea     r14, WPP_GLOBAL_Control
0x1800586df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800586e6  cmp     rcx, r14
0x1800586e9  jz      short loc_180058706
0x1800586eb  test    byte ptr [rcx+1Ch], 8
0x1800586ef  jz      short loc_180058706
0x1800586f1  mov     edx, 1ECh
0x1800586f6  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x1800586fd  mov     rcx, [rcx+10h]
0x180058701  call    WPP_SF_
0x180058706  xor     edi, edi
0x180058708  mov     [rsp+0A8h+Reply], edi
0x18005870c  call    cs:__imp_GetTickCount64
0x180058713  nop     dword ptr [rax+rax+00h]
0x180058718  test    rbx, rbx
0x18005871b  jnz     short loc_18005875A
0x18005871d  lea     r9d, [rdi+57h]
0x180058721  mov     [rsp+0A8h+Reply], r9d
0x180058726  mov     rcx, cs:WPP_GLOBAL_Control
0x18005872d  cmp     rcx, r14
0x180058730  jz      loc_18005895A
0x180058736  test    byte ptr [rcx+1Ch], 1
0x18005873a  jz      loc_180058935
0x180058740  mov     edx, 1EDh
0x180058745  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x18005874c  mov     rcx, [rcx+10h]
0x180058750  call    WPP_SF_d
0x180058755  jmp     loc_18005892E
0x18005875a  lea     rsi, [r15+0A0h]
0x180058761  mov     [rsp+0A8h+var_58], rsi
0x180058766  cmp     [rsi], rdi
0x180058769  jnz     short loc_180058797
0x18005876b  mov     r9d, 57h ; 'W'
0x180058771  mov     [rsp+0A8h+Reply], r9d
0x180058776  mov     rcx, cs:WPP_GLOBAL_Control
0x18005877d  cmp     rcx, r14
0x180058780  jz      loc_18005895A
0x180058786  test    byte ptr [rcx+1Ch], 1
0x18005878a  jz      loc_180058935
0x180058790  mov     edx, 1EEh
0x180058795  jmp     short loc_180058745
0x180058797  mov     r12d, edi
0x18005879a  mov     [rsp+0A8h+var_78], edi
0x18005879e  mov     rcx, [r15+98h]; pwa
0x1800587a5  test    rcx, rcx
0x1800587a8  jz      short loc_1800587F7
0x1800587aa  xor     r9d, r9d; Reserved
0x1800587ad  xor     r8d, r8d; pftTimeout
0x1800587b0  xor     edx, edx; h
0x1800587b2  call    cs:__imp_SetThreadpoolWaitEx
0x1800587b9  nop     dword ptr [rax+rax+00h]
0x1800587be  mov     r12d, eax
0x1800587c1  mov     [rsp+0A8h+var_78], eax
0x1800587c5  mov     edx, 1; fCancelPendingCallbacks
0x1800587ca  mov     rcx, [r15+98h]; pwa
0x1800587d1  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x1800587d8  nop     dword ptr [rax+rax+00h]
0x1800587dd  mov     rcx, [r15+98h]; pwa
0x1800587e4  call    cs:__imp_CloseThreadpoolWait
0x1800587eb  nop     dword ptr [rax+rax+00h]
0x1800587f0  mov     [r15+98h], rdi
0x1800587f7  cmp     [rsi], rdi
0x1800587fa  jz      short loc_18005885C
0x1800587fc  mov     eax, 1
0x180058801  xchg    eax, [r15+0B4h]
0x180058808  mov     [rsp+0A8h+var_70], rdi
0x18005880d  mov     [rsp+0A8h+var_88], rsi
0x180058812  mov     r9, [r15]
0x180058815  xor     r8d, r8d; pReturnValue
0x180058818  lea     edx, [r8+0Ah]; nProcNum
0x18005881c  lea     rcx, ?FW_RESOURCE_INDICATION_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180058823  call    cs:__imp_NdrClientCall3
0x18005882a  nop     dword ptr [rax+rax+00h]
0x18005882f  mov     [rsp+0A8h+var_70], rax
0x180058834  mov     [rsp+0A8h+Reply], eax
0x180058838  jmp     short loc_180058859
0x18005883a  mov     [rsp+0A8h+Reply], eax
0x18005883e  lea     r14, WPP_GLOBAL_Control
0x180058845  xor     edi, edi
0x180058847  mov     r12d, [rsp+0A8h+var_78]
0x18005884c  mov     rbx, [rsp+0A8h+var_68]
0x180058851  mov     r15, rbx
0x180058854  mov     rsi, [rsp+0A8h+var_58]
0x180058859  mov     [rsi], rdi
0x18005885c  xor     eax, eax
0x18005885e  lock cmpxchg [rbx+0B8h], edi
0x180058866  cmp     eax, 1
0x180058869  jnz     short loc_1800588D6
0x18005886b  mov     esi, edi
0x18005886d  cmp     [rsp+0A8h+Reply], edi
0x180058871  jz      short loc_180058892
0x180058873  lea     rcx, [rbx+8]; pAsync
0x180058877  mov     edx, eax; fAbort
0x180058879  call    cs:__imp_RpcAsyncCancelCall
0x180058880  nop     dword ptr [rax+rax+00h]
0x180058885  mov     esi, eax
0x180058887  test    eax, eax
0x180058889  jz      short loc_180058892
0x18005888b  mov     edx, eax; __annotation("Debug", "TelemetryAssert", "rpcStatus == RPC_S_OK", "RpcAsyncCancelCall")
0x18005888d  call    MicrosoftTelemetryAssertTriggeredArgs
0x180058892  cmp     r12d, 1
0x180058896  jnz     short loc_1800588B2
0x180058898  test    esi, esi
0x18005889a  jnz     short loc_1800588B2
0x18005889c  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18005889f  mov     rcx, [rbx+90h]; hHandle
0x1800588a6  call    cs:__imp_WaitForSingleObject
0x1800588ad  nop     dword ptr [rax+rax+00h]
0x1800588b2  lea     rcx, [rbx+8]; pAsync
0x1800588b6  lea     rdx, [rsp+0A8h+Reply]; Reply
0x1800588bb  call    cs:__imp_RpcAsyncCompleteCall
0x1800588c2  nop     dword ptr [rax+rax+00h]
0x1800588c7  mov     [rbx+78h], eax
0x1800588ca  cmp     eax, 3E5h
0x1800588cf  jnz     short loc_1800588D6
0x1800588d1  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "phClntSubscription->Status != RPC_S_ASYNC_CALL_PENDING")
0x1800588d6  mov     rcx, [rbx+90h]
0x1800588dd  call    cs:__imp_FwCloseHandle
0x1800588e4  nop     dword ptr [rax+rax+00h]
0x1800588e9  mov     [rbx+90h], rdi
0x1800588f0  cmp     [r15], rdi
0x1800588f3  jz      short loc_18005890F
0x1800588f5  mov     rcx, rbx; Binding
0x1800588f8  call    cs:__imp_RpcBindingFree
0x1800588ff  nop     dword ptr [rax+rax+00h]
0x180058904  test    eax, eax
0x180058906  jz      short loc_18005890F
0x180058908  mov     edx, eax; __annotation("Debug", "TelemetryAssert", "status == RPC_S_OK", "RpcBindingFree")
0x18005890a  call    MicrosoftTelemetryAssertTriggeredArgs
0x18005890f  xor     edx, edx; Val
0x180058911  mov     r8d, 0C0h; Size
0x180058917  mov     rcx, rbx; void *
0x18005891a  call    memset_0
0x18005891f  mov     rcx, rbx
0x180058922  call    cs:__imp_FwBaseFree
0x180058929  nop     dword ptr [rax+rax+00h]
0x18005892e  mov     rcx, cs:WPP_GLOBAL_Control
0x180058935  cmp     rcx, r14
0x180058938  jz      short loc_18005895A
0x18005893a  test    byte ptr [rcx+1Ch], 8
0x18005893e  jz      short loc_18005895A
0x180058940  mov     edx, 1EFh
0x180058945  mov     r9d, [rsp+0A8h+Reply]
0x18005894a  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x180058951  mov     rcx, [rcx+10h]
0x180058955  call    WPP_SF_d
0x18005895a  mov     eax, [rsp+0A8h+Reply]
0x18005895e  mov     rcx, [rsp+0A8h+var_48]
0x180058963  xor     rcx, rsp; StackCookie
0x180058966  call    __security_check_cookie
0x18005896b  add     rsp, 78h
0x18005896f  pop     r15
0x180058971  pop     r14
0x180058973  pop     r12
0x180058975  pop     rdi
0x180058976  pop     rsi
0x180058977  pop     rbx
0x180058978  retn
0x180060390  push    rbp
0x180060392  sub     rsp, 30h
0x180060396  mov     rbp, rdx
0x180060399  mov     rcx, [rcx]
0x18006039c  mov     ecx, [rcx]; ExceptionCode
0x18006039e  call    cs:__imp_RpcExceptionFilter
0x1800603a5  nop     dword ptr [rax+rax+00h]
0x1800603aa  nop
0x1800603ab  add     rsp, 30h
0x1800603af  pop     rbp
0x1800603b0  retn
```
