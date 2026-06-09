# AiSvcpRootStoreChangedCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)

- ea: `0x1800039e0`
- end: `0x180003a86`
- name: `?AiSvcpRootStoreChangedCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z`
- size: `166`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WAIT Wait, TP_WAIT_RESULT WaitResult)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800039e0`
- `0x1800049a8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003a4a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003a4a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180003a61`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180003a61`
- `CRYPT32!CertControlStore` at `0x180003a7a`
- `CRYPT32!CertControlStore` at `0x180003a7a`

## pseudocode

```c
void __fastcall AiSvcpRootStoreChangedCallback(
        PTP_CALLBACK_INSTANCE Instance,
        PVOID Context,
        PTP_WAIT Wait,
        TP_WAIT_RESULT WaitResult)
{
  struct _FILETIME pftDueTime; // [rsp+20h] [rbp-18h] BYREF

  pftDueTime = (struct _FILETIME)-100000000LL;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      39,
      WPP_c500ddf3cb7e33b2855b0d42471a40ca_Traceguids,
      "AiSvcpRootStoreChangedCallback");
  if ( !_InterlockedCompareExchange(&AiSvcpRootStoreChangeScheduled, 1, 0) )
    SetThreadpoolTimer(AiSvcpRootStoreTimer, &pftDueTime, 0, 0);
  SetThreadpoolWait(AiSvcpRootStoreWaitObject, AiSvcpRootStoreChangeEvent, 0);
  CertControlStore(AiSvcpRootCertStore, 0, 1u, &AiSvcpRootStoreChangeEvent);
}

```

## disassembly

```asm
0x1800039e0  push    rbx
0x1800039e2  sub     rsp, 30h
0x1800039e6  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], 0FFFFFFFFFA0A1F00h
0x1800039ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800039f6  lea     rax, WPP_GLOBAL_Control
0x1800039fd  cmp     rcx, rax
0x180003a00  jz      short loc_180003A27
0x180003a02  test    dword ptr [rcx+1Ch], 400h
0x180003a09  jz      short loc_180003A27
0x180003a0b  mov     rcx, [rcx+10h]
0x180003a0f  lea     r9, aAisvcprootstor; "AiSvcpRootStoreChangedCallback"
0x180003a16  mov     edx, 27h ; '''
0x180003a1b  lea     r8, WPP_c500ddf3cb7e33b2855b0d42471a40ca_Traceguids
0x180003a22  call    WPP_SF_s
0x180003a27  mov     ebx, 1
0x180003a2c  xor     eax, eax
0x180003a2e  lock cmpxchg cs:?AiSvcpRootStoreChangeScheduled@@3JC, ebx; long volatile AiSvcpRootStoreChangeScheduled
0x180003a36  jnz     short loc_180003A50
0x180003a38  mov     rcx, cs:?AiSvcpRootStoreTimer@@3PEAU_TP_TIMER@@EA; pti
0x180003a3f  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x180003a44  xor     r9d, r9d; msWindowLength
0x180003a47  xor     r8d, r8d; msPeriod
0x180003a4a  call    cs:__imp_SetThreadpoolTimer
0x180003a50  mov     rdx, cs:?AiSvcpRootStoreChangeEvent@@3PEAXEA; h
0x180003a57  xor     r8d, r8d; pftTimeout
0x180003a5a  mov     rcx, cs:?AiSvcpRootStoreWaitObject@@3PEAU_TP_WAIT@@EA; pwa
0x180003a61  call    cs:__imp_SetThreadpoolWait
0x180003a67  mov     rcx, cs:?AiSvcpRootCertStore@@3PEAXEA; hCertStore
0x180003a6e  lea     r9, ?AiSvcpRootStoreChangeEvent@@3PEAXEA; pvCtrlPara
0x180003a75  mov     r8d, ebx; dwCtrlType
0x180003a78  xor     edx, edx; dwFlags
0x180003a7a  call    cs:__imp_CertControlStore
0x180003a80  add     rsp, 30h
0x180003a84  pop     rbx
0x180003a85  retn
```
