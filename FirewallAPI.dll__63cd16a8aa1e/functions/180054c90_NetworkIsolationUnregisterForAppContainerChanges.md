# NetworkIsolationUnregisterForAppContainerChanges

- ea: `0x180054c90`
- end: `0x180054f17`
- name: `NetworkIsolationUnregisterForAppContainerChanges`
- size: `647`
- prototype: `DWORD __stdcall(HANDLE registrationObject)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800546e0`

## callees

- `0x180005954`
- `0x180024c3c`
- `0x18002514c`
- `0x1800277b0`
- `0x1800284c4`
- `0x18003104c`
- `0x180054c90`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x180054e71`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180054e71`
- `RPCRT4!RpcExceptionFilter` at `0x18005c12e`
- `RPCRT4!RpcExceptionFilter` at `0x18005c12e`
- `RPCRT4!RpcAsyncCancelCall` at `0x180054e3b`
- `RPCRT4!RpcAsyncCancelCall` at `0x180054e3b`
- `RPCRT4!NdrClientCall3` at `0x180054deb`
- `RPCRT4!NdrClientCall3` at `0x180054deb`
- `RPCRT4!RpcBindingFree` at `0x180054ea2`
- `RPCRT4!RpcBindingFree` at `0x180054ea2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180054e62`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180054e62`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWaitEx` at `0x180054d8c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWaitEx` at `0x180054d8c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180054db2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180054db2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180054da5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180054da5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180054cec`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180054cec`
- `fwbase!FwBaseFree` at `0x180054ec6`
- `fwbase!FwBaseFree` at `0x180054ec6`
- `fwbase!FwCloseHandle` at `0x180054e8d`
- `fwbase!FwCloseHandle` at `0x180054e8d`

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
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 493, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids);
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
    v4 = 495;
LABEL_8:
    WPP_SF_d(*((_QWORD *)v3 + 2), v4, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, 87);
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
    v4 = 494;
    goto LABEL_8;
  }
LABEL_31:
  if ( v3 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)v3 + 2), 496, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, Reply);
  return Reply;
}

```

## disassembly

```asm
0x180054c90  push    rbx
0x180054c92  push    rsi
0x180054c93  push    rdi
0x180054c94  push    r12
0x180054c96  push    r14
0x180054c98  push    r15
0x180054c9a  sub     rsp, 78h
0x180054c9e  mov     rax, cs:__security_cookie
0x180054ca5  xor     rax, rsp
0x180054ca8  mov     [rsp+0A8h+var_48], rax
0x180054cad  mov     r15, rcx
0x180054cb0  mov     rbx, rcx
0x180054cb3  mov     [rsp+0A8h+var_68], rcx
0x180054cb8  lea     r14, WPP_GLOBAL_Control
0x180054cbf  mov     rcx, cs:WPP_GLOBAL_Control
0x180054cc6  cmp     rcx, r14
0x180054cc9  jz      short loc_180054CE6
0x180054ccb  test    byte ptr [rcx+1Ch], 8
0x180054ccf  jz      short loc_180054CE6
0x180054cd1  mov     edx, 1EDh
0x180054cd6  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x180054cdd  mov     rcx, [rcx+10h]
0x180054ce1  call    WPP_SF_
0x180054ce6  xor     edi, edi
0x180054ce8  mov     [rsp+0A8h+Reply], edi
0x180054cec  call    cs:__imp_GetTickCount64
0x180054cf2  test    rbx, rbx
0x180054cf5  jnz     short loc_180054D34
0x180054cf7  lea     r9d, [rdi+57h]
0x180054cfb  mov     [rsp+0A8h+Reply], r9d
0x180054d00  mov     rcx, cs:WPP_GLOBAL_Control
0x180054d07  cmp     rcx, r14
0x180054d0a  jz      loc_180054EF8
0x180054d10  test    byte ptr [rcx+1Ch], 1
0x180054d14  jz      loc_180054ED3
0x180054d1a  mov     edx, 1EEh
0x180054d1f  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x180054d26  mov     rcx, [rcx+10h]
0x180054d2a  call    WPP_SF_d
0x180054d2f  jmp     loc_180054ECC
0x180054d34  lea     rsi, [r15+0A0h]
0x180054d3b  mov     [rsp+0A8h+var_58], rsi
0x180054d40  cmp     [rsi], rdi
0x180054d43  jnz     short loc_180054D71
0x180054d45  mov     r9d, 57h ; 'W'
0x180054d4b  mov     [rsp+0A8h+Reply], r9d
0x180054d50  mov     rcx, cs:WPP_GLOBAL_Control
0x180054d57  cmp     rcx, r14
0x180054d5a  jz      loc_180054EF8
0x180054d60  test    byte ptr [rcx+1Ch], 1
0x180054d64  jz      loc_180054ED3
0x180054d6a  mov     edx, 1EFh
0x180054d6f  jmp     short loc_180054D1F
0x180054d71  mov     r12d, edi
0x180054d74  mov     [rsp+0A8h+var_78], edi
0x180054d78  mov     rcx, [r15+98h]; pwa
0x180054d7f  test    rcx, rcx
0x180054d82  jz      short loc_180054DBF
0x180054d84  xor     r9d, r9d; Reserved
0x180054d87  xor     r8d, r8d; pftTimeout
0x180054d8a  xor     edx, edx; h
0x180054d8c  call    cs:__imp_SetThreadpoolWaitEx
0x180054d92  mov     r12d, eax
0x180054d95  mov     [rsp+0A8h+var_78], eax
0x180054d99  mov     edx, 1; fCancelPendingCallbacks
0x180054d9e  mov     rcx, [r15+98h]; pwa
0x180054da5  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x180054dab  mov     rcx, [r15+98h]; pwa
0x180054db2  call    cs:__imp_CloseThreadpoolWait
0x180054db8  mov     [r15+98h], rdi
0x180054dbf  cmp     [rsi], rdi
0x180054dc2  jz      short loc_180054E1E
0x180054dc4  mov     eax, 1
0x180054dc9  xchg    eax, [r15+0B4h]
0x180054dd0  mov     [rsp+0A8h+var_70], rdi
0x180054dd5  mov     [rsp+0A8h+var_88], rsi
0x180054dda  mov     r9, [r15]
0x180054ddd  xor     r8d, r8d; pReturnValue
0x180054de0  lea     edx, [r8+0Ah]; nProcNum
0x180054de4  lea     rcx, ?FW_RESOURCE_INDICATION_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180054deb  call    cs:__imp_NdrClientCall3
0x180054df1  mov     [rsp+0A8h+var_70], rax
0x180054df6  mov     [rsp+0A8h+Reply], eax
0x180054dfa  jmp     short loc_180054E1B
0x180054dfc  mov     [rsp+0A8h+Reply], eax
0x180054e00  lea     r14, WPP_GLOBAL_Control
0x180054e07  xor     edi, edi
0x180054e09  mov     r12d, [rsp+0A8h+var_78]
0x180054e0e  mov     rbx, [rsp+0A8h+var_68]
0x180054e13  mov     r15, rbx
0x180054e16  mov     rsi, [rsp+0A8h+var_58]
0x180054e1b  mov     [rsi], rdi
0x180054e1e  xor     eax, eax
0x180054e20  lock cmpxchg [rbx+0B8h], edi
0x180054e28  cmp     eax, 1
0x180054e2b  jnz     short loc_180054E86
0x180054e2d  mov     esi, edi
0x180054e2f  cmp     [rsp+0A8h+Reply], edi
0x180054e33  jz      short loc_180054E4E
0x180054e35  lea     rcx, [rbx+8]; pAsync
0x180054e39  mov     edx, eax; fAbort
0x180054e3b  call    cs:__imp_RpcAsyncCancelCall
0x180054e41  mov     esi, eax
0x180054e43  test    eax, eax
0x180054e45  jz      short loc_180054E4E
0x180054e47  mov     edx, eax
0x180054e49  call    MicrosoftTelemetryAssertTriggeredArgs
0x180054e4e  cmp     r12d, 1
0x180054e52  jnz     short loc_180054E68
0x180054e54  test    esi, esi
0x180054e56  jnz     short loc_180054E68
0x180054e58  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180054e5b  mov     rcx, [rbx+90h]; hHandle
0x180054e62  call    cs:__imp_WaitForSingleObject
0x180054e68  lea     rcx, [rbx+8]; pAsync
0x180054e6c  lea     rdx, [rsp+0A8h+Reply]; Reply
0x180054e71  call    cs:__imp_RpcAsyncCompleteCall
0x180054e77  mov     [rbx+78h], eax
0x180054e7a  cmp     eax, 3E5h
0x180054e7f  jnz     short loc_180054E86
0x180054e81  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180054e86  mov     rcx, [rbx+90h]
0x180054e8d  call    cs:__imp_FwCloseHandle
0x180054e93  mov     [rbx+90h], rdi
0x180054e9a  cmp     [r15], rdi
0x180054e9d  jz      short loc_180054EB3
0x180054e9f  mov     rcx, rbx; Binding
0x180054ea2  call    cs:__imp_RpcBindingFree
0x180054ea8  test    eax, eax
0x180054eaa  jz      short loc_180054EB3
0x180054eac  mov     edx, eax
0x180054eae  call    MicrosoftTelemetryAssertTriggeredArgs
0x180054eb3  xor     edx, edx; Val
0x180054eb5  mov     r8d, 0C0h; Size
0x180054ebb  mov     rcx, rbx; void *
0x180054ebe  call    memset_0
0x180054ec3  mov     rcx, rbx
0x180054ec6  call    cs:__imp_FwBaseFree
0x180054ecc  mov     rcx, cs:WPP_GLOBAL_Control
0x180054ed3  cmp     rcx, r14
0x180054ed6  jz      short loc_180054EF8
0x180054ed8  test    byte ptr [rcx+1Ch], 8
0x180054edc  jz      short loc_180054EF8
0x180054ede  mov     edx, 1F0h
0x180054ee3  mov     r9d, [rsp+0A8h+Reply]
0x180054ee8  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x180054eef  mov     rcx, [rcx+10h]
0x180054ef3  call    WPP_SF_d
0x180054ef8  mov     eax, [rsp+0A8h+Reply]
0x180054efc  mov     rcx, [rsp+0A8h+var_48]
0x180054f01  xor     rcx, rsp; StackCookie
0x180054f04  call    __security_check_cookie
0x180054f09  add     rsp, 78h
0x180054f0d  pop     r15
0x180054f0f  pop     r14
0x180054f11  pop     r12
0x180054f13  pop     rdi
0x180054f14  pop     rsi
0x180054f15  pop     rbx
0x180054f16  retn
0x18005c120  push    rbp
0x18005c122  sub     rsp, 30h
0x18005c126  mov     rbp, rdx
0x18005c129  mov     rcx, [rcx]
0x18005c12c  mov     ecx, [rcx]; ExceptionCode
0x18005c12e  call    cs:__imp_RpcExceptionFilter
0x18005c134  nop
0x18005c135  add     rsp, 30h
0x18005c139  pop     rbp
0x18005c13a  retn
```
