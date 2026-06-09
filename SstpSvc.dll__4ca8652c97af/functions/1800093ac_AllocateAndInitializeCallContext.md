# AllocateAndInitializeCallContext

- ea: `0x1800093ac`
- end: `0x1800099eb`
- name: `AllocateAndInitializeCallContext`
- size: `1599`
- prototype: `__int64 __fastcall(char, __int64 *)`
- caller_count: `3`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180004ef4`
- `0x180009dd8`
- `0x18000bc78`

## callees

- `0x180002d70`
- `0x180004530`
- `0x18000827c`
- `0x180008360`
- `0x1800093ac`
- `0x180014ac0`
- `0x180014af0`
- `0x18001bcba`
- `0x18001bcf0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800097e5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009885`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000994b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800097e5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009885`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000994b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000982a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800098a2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800099a4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800099b8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000982a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800098a2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800099a4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800099b8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180009919`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180009919`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180009524`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180009524`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009530`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800095f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000967b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800096ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009530`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800095f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000967b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800096ee`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800095e0`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800095e0`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180009669`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800096da`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180009669`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800096da`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180009905`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180009905`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800098ce`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800098e6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800098ce`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800098e6`

## pseudocode

```c
__int64 __fastcall AllocateAndInitializeCallContext(char a1, __int64 *a2)
{
  char *v4; // rcx
  __int64 BufferFromPool; // rax
  __int64 v6; // rbx
  DWORD v7; // esi
  _QWORD *v8; // r12
  DWORD LastError; // eax
  __int64 v10; // r8
  _QWORD *v11; // rax
  PTP_TIMER ThreadpoolTimer; // rax
  PTP_WORK ThreadpoolWork; // rax
  PTP_WORK v14; // rax
  struct _RTL_CRITICAL_SECTION *v15; // rcx
  char *v16; // rcx
  int v17; // eax
  char *v18; // rcx
  _QWORD *v19; // rax
  int v23; // [rsp+30h] [rbp-D0h] BYREF
  char v24[2044]; // [rsp+34h] [rbp-CCh] BYREF

  v23 = 0;
  memset_0(v24, 0, sizeof(v24));
  v4 = (char *)SstpSvcGlobals + 536;
  *a2 = 0;
  BufferFromPool = GetBufferFromPool(v4);
  v6 = BufferFromPool;
  if ( !BufferFromPool )
  {
    if ( (byte_18002D803 & 8) != 0 )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasSSTPSvcTraceError,
        L"TpCallCtxPool: Alloc failed for initrequest fails");
    return 8;
  }
  if ( (byte_18002D803 & 8) != 0 )
  {
    LOWORD(v23) = 0;
    FormatRRASErrorString(&v23, L"Allocating Call context 0x%p", BufferFromPool);
    if ( (byte_18002D803 & 8) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v23);
  }
  memset_0((void *)v6, 0, 0x278u);
  *(_DWORD *)(v6 + 32) = 17767;
  *(_QWORD *)(v6 + 216) = CleanupCallCtx;
  v8 = (_QWORD *)(v6 + 224);
  *(_QWORD *)(v6 + 240) = 0;
  *(_QWORD *)(v6 + 272) = 0;
  *(_QWORD *)(v6 + 280) = 0;
  *(_BYTE *)(v6 + 432) = 0;
  *(_QWORD *)(v6 + 624) = 0;
  *(_QWORD *)(v6 + 232) = v6 + 224;
  *(_QWORD *)(v6 + 224) = v6 + 224;
  *(_QWORD *)(v6 + 424) = v6 + 416;
  *(_QWORD *)(v6 + 416) = v6 + 416;
  *(_BYTE *)(v6 + 248) = a1;
  *(_QWORD *)(v6 + 612) = 1;
  if ( !InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)(v6 + 288), 0xFA0u) )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( (byte_18002D803 & 8) != 0 )
    {
      LOWORD(v23) = 0;
      FormatRRASErrorString(&v23, L"Error initializing callctx critsec [%d]", LastError);
      if ( (byte_18002D803 & 8) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v23);
    }
    goto LABEL_42;
  }
  v11 = SstpSvcGlobals;
  *(_DWORD *)(v6 + 344) = 3;
  *(_QWORD *)(v6 + 352) = 0;
  *(_QWORD *)(v6 + 360) = 0;
  *(_QWORD *)(v6 + 368) = 0;
  *(_QWORD *)(v6 + 376) = 0;
  *(_QWORD *)(v6 + 384) = 0;
  *(_QWORD *)(v6 + 392) = 0;
  *(_DWORD *)(v6 + 400) = 0;
  *(_DWORD *)(v6 + 404) = 1;
  *(_DWORD *)(v6 + 408) = 72;
  *(_QWORD *)(v6 + 352) = v11[20];
  if ( a1 )
  {
    ThreadpoolTimer = CreateThreadpoolTimer(ResponseWaitTimeout, (PVOID)v6, (PTP_CALLBACK_ENVIRON)(v6 + 344));
    *(_QWORD *)(v6 + 456) = ThreadpoolTimer;
    if ( !ThreadpoolTimer )
    {
      v7 = GetLastError();
      if ( (byte_18002D803 & 8) != 0 )
      {
        LOWORD(v23) = 0;
        FormatRRASErrorString(&v23, L"Error allocating response wait timeout [%d]", v7);
        if ( (byte_18002D803 & 8) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v23);
      }
LABEL_41:
      DeleteCriticalSection((LPCRITICAL_SECTION)(v6 + 288));
LABEL_42:
      LOBYTE(v10) = 1;
      FreeBufferToPool((char *)SstpSvcGlobals + 536, v6, v10);
      return v7;
    }
  }
  *(_OWORD *)(v6 + 40) = 0;
  *(_OWORD *)(v6 + 56) = 0;
  *(_QWORD *)(v6 + 72) = 0;
  *(_DWORD *)(v6 + 72) = 17770;
  ThreadpoolWork = CreateThreadpoolWork(SendToNetworkWorker, (PVOID)v6, (PTP_CALLBACK_ENVIRON)(v6 + 344));
  *(_QWORD *)(v6 + 328) = ThreadpoolWork;
  if ( !ThreadpoolWork )
  {
    v7 = GetLastError();
    if ( (byte_18002D803 & 8) != 0 )
    {
      LOWORD(v23) = 0;
      FormatRRASErrorString(&v23, L"Unable to allocate send work item: %d", v7);
      if ( (byte_18002D803 & 8) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v23);
    }
    goto LABEL_39;
  }
  v14 = CreateThreadpoolWork(ProcessReceivedBytesWorker, (PVOID)v6, (PTP_CALLBACK_ENVIRON)(v6 + 344));
  *(_QWORD *)(v6 + 336) = v14;
  if ( !v14 )
  {
    v7 = GetLastError();
    if ( (byte_18002D803 & 8) != 0 )
    {
      LOWORD(v23) = 0;
      FormatRRASErrorString(&v23, L"Unable to allocate process received bytes work item: %d", v7);
      if ( (byte_18002D803 & 8) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v23);
    }
    goto LABEL_38;
  }
  *(_DWORD *)(v6 + 160) = 17771;
  *(_OWORD *)(v6 + 128) = 0;
  *(_OWORD *)(v6 + 144) = 0;
  *(_DWORD *)(v6 + 112) = 17777;
  *(_OWORD *)(v6 + 80) = 0;
  *(_OWORD *)(v6 + 96) = 0;
  *(_DWORD *)(v6 + 72) = 17770;
  *(_OWORD *)(v6 + 40) = 0;
  *(_OWORD *)(v6 + 56) = 0;
  if ( (byte_18002D803 & 0x10) != 0 )
  {
    LOWORD(v23) = 0;
    FormatRRASErrorString(&v23, L"Setting %p callcontext->SendOverlapPosted to %ws", v6, L"FALSE");
    if ( (byte_18002D803 & 0x10) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceInfo, &v23);
  }
  v15 = (struct _RTL_CRITICAL_SECTION *)((char *)SstpSvcGlobals + 184);
  *(_QWORD *)(v6 + 256) = 0;
  *(_WORD *)(v6 + 264) = 0;
  *(_BYTE *)(v6 + 434) = 0;
  EnterCriticalSection(v15);
  v16 = (char *)SstpSvcGlobals;
  if ( *((_QWORD *)SstpSvcGlobals + 22) )
  {
    v17 = assign_HF_handle(*((_QWORD *)SstpSvcGlobals + 22), v6);
    v16 = (char *)SstpSvcGlobals;
    *(_DWORD *)(v6 + 244) = v17;
    v7 = v17 == 0 ? 8 : 0;
  }
  else
  {
    v7 = 87;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(v16 + 184));
  if ( v7 )
  {
    if ( (byte_18002D803 & 8) != 0 )
    {
      LOWORD(v23) = 0;
      FormatRRASErrorString(&v23, L"Unable to get the handle32 for the request: %d", v7);
      if ( (byte_18002D803 & 8) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v23);
    }
    goto LABEL_37;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)SstpSvcGlobals + 224));
  if ( *(_DWORD *)SstpSvcGlobals == 3 )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)SstpSvcGlobals + 224));
    v7 = 995;
    HfFreeHandle32(*((_QWORD *)SstpSvcGlobals + 22), v6 + 244);
LABEL_37:
    CloseThreadpoolWork(*(PTP_WORK *)(v6 + 336));
    *(_QWORD *)(v6 + 336) = 0;
LABEL_38:
    CloseThreadpoolWork(*(PTP_WORK *)(v6 + 328));
    *(_QWORD *)(v6 + 328) = 0;
LABEL_39:
    if ( a1 )
    {
      CloseThreadpoolTimer(*(PTP_TIMER *)(v6 + 456));
      *(_QWORD *)(v6 + 456) = 0;
    }
    goto LABEL_41;
  }
  *(_QWORD *)(v6 + 232) = v8;
  *v8 = v8;
  EnterCriticalSection((LPCRITICAL_SECTION)(v6 + 288));
  *(_DWORD *)(v6 + 252) = 1;
  if ( *(_BYTE *)(v6 + 248) )
  {
    *(_QWORD *)(v6 + 440) = 0;
    *(_QWORD *)(v6 + 448) = 0;
    *(_DWORD *)(v6 + 252) = 65537;
  }
  v18 = (char *)SstpSvcGlobals + 264;
  v19 = (_QWORD *)*((_QWORD *)SstpSvcGlobals + 34);
  *v8 = (char *)SstpSvcGlobals + 264;
  *(_QWORD *)(v6 + 232) = v19;
  *v19 = v8;
  *((_QWORD *)v18 + 1) = v8;
  LeaveCriticalSection((LPCRITICAL_SECTION)(v6 + 288));
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)SstpSvcGlobals + 224));
  *a2 = v6;
  return v7;
}

```

## disassembly

```asm
0x1800093ac  push    rbp
0x1800093ae  push    rbx
0x1800093af  push    rsi
0x1800093b0  push    rdi
0x1800093b1  push    r12
0x1800093b3  push    r13
0x1800093b5  push    r14
0x1800093b7  push    r15
0x1800093b9  lea     rbp, [rsp-748h]
0x1800093c1  sub     rsp, 848h
0x1800093c8  mov     rax, cs:__security_cookie
0x1800093cf  xor     rax, rsp
0x1800093d2  mov     [rbp+780h+var_50], rax
0x1800093d9  mov     rbx, rdx
0x1800093dc  mov     [rsp+880h+var_858], rdx
0x1800093e1  mov     sil, cl
0x1800093e4  mov     [rsp+880h+var_860], cl
0x1800093e8  xor     r13d, r13d
0x1800093eb  lea     rcx, [rsp+880h+var_84C]; void *
0x1800093f0  xor     edx, edx; Val
0x1800093f2  mov     [rsp+880h+var_850], r13d
0x1800093f7  mov     r8d, 7FCh; Size
0x1800093fd  call    memset_0
0x180009402  mov     rcx, cs:SstpSvcGlobals
0x180009409  add     rcx, 218h
0x180009410  mov     [rbx], r13
0x180009413  call    GetBufferFromPool
0x180009418  lea     edi, [r13+8]
0x18000941c  mov     rbx, rax
0x18000941f  test    rax, rax
0x180009422  jnz     short loc_18000944E
0x180009424  test    cs:byte_18002D803, dil
0x18000942b  jz      short loc_180009447
0x18000942d  lea     r8, aTpcallctxpoolA; "TpCallCtxPool: Alloc failed for initreq"...
0x180009434  lea     rdx, RasSSTPSvcTraceError
0x18000943b  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180009442  call    McTemplateU0z_EventWriteTransfer
0x180009447  mov     esi, edi
0x180009449  jmp     loc_1800099C6
0x18000944e  test    cs:byte_18002D803, dil
0x180009455  lea     r15, RasSSTPSvcTraceError
0x18000945c  lea     r14, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180009463  jz      short loc_180009498
0x180009465  mov     r8, rbx
0x180009468  mov     word ptr [rsp+880h+var_850], r13w
0x18000946e  lea     rdx, aAllocatingCall; "Allocating Call context 0x%p"
0x180009475  lea     rcx, [rsp+880h+var_850]
0x18000947a  call    FormatRRASErrorString
0x18000947f  test    cs:byte_18002D803, dil
0x180009486  jz      short loc_180009498
0x180009488  lea     r8, [rsp+880h+var_850]
0x18000948d  mov     rdx, r15
0x180009490  mov     rcx, r14
0x180009493  call    McTemplateU0z_EventWriteTransfer
0x180009498  xor     edx, edx; Val
0x18000949a  mov     r8d, 278h; Size
0x1800094a0  mov     rcx, rbx; void *
0x1800094a3  call    memset_0
0x1800094a8  lea     rax, CleanupCallCtx
0x1800094af  mov     dword ptr [rbx+20h], 4567h
0x1800094b6  mov     [rbx+0D8h], rax
0x1800094bd  lea     r12, [rbx+0E0h]
0x1800094c4  lea     rax, [rbx+1A0h]
0x1800094cb  mov     [rbx+0F0h], r13
0x1800094d2  mov     [rbx+110h], r13
0x1800094d9  mov     edx, 0FA0h; dwSpinCount
0x1800094de  mov     [rbx+118h], r13
0x1800094e5  mov     [rbx+1B0h], r13b
0x1800094ec  mov     [rbx+270h], r13
0x1800094f3  lea     r13, [rbx+120h]
0x1800094fa  mov     rcx, r13; lpCriticalSection
0x1800094fd  mov     [rbx+0E8h], r12
0x180009504  mov     [r12], r12
0x180009508  mov     [rbx+1A8h], rax
0x18000950f  mov     [rax], rax
0x180009512  mov     [rbx+0F8h], sil
0x180009519  mov     qword ptr [rbx+264h], 1
0x180009524  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000952a  xor     edx, edx
0x18000952c  test    eax, eax
0x18000952e  jnz     short loc_180009582
0x180009530  call    cs:__imp_GetLastError
0x180009536  test    cs:byte_18002D803, dil
0x18000953d  mov     esi, eax
0x18000953f  jz      loc_18000991F
0x180009545  xor     ecx, ecx
0x180009547  lea     rdx, aErrorInitializ; "Error initializing callctx critsec [%d]"
0x18000954e  mov     word ptr [rsp+880h+var_850], cx
0x180009553  mov     r8d, eax
0x180009556  lea     rcx, [rsp+880h+var_850]
0x18000955b  call    FormatRRASErrorString
0x180009560  test    cs:byte_18002D803, dil
0x180009567  jz      loc_18000991F
0x18000956d  lea     r8, [rsp+880h+var_850]
0x180009572  mov     rdx, r15
0x180009575  mov     rcx, r14
0x180009578  call    McTemplateU0z_EventWriteTransfer
0x18000957d  jmp     loc_18000991F
0x180009582  lea     rsi, [rbx+158h]
0x180009589  mov     rax, cs:SstpSvcGlobals
0x180009590  mov     dword ptr [rsi], 3
0x180009596  mov     [rsi+8], rdx
0x18000959a  mov     [rsi+10h], rdx
0x18000959e  mov     [rsi+18h], rdx
0x1800095a2  mov     [rsi+20h], rdx
0x1800095a6  mov     [rsi+28h], rdx
0x1800095aa  mov     [rsi+30h], rdx
0x1800095ae  mov     [rsi+38h], edx
0x1800095b1  mov     dword ptr [rsi+3Ch], 1
0x1800095b8  mov     dword ptr [rsi+40h], 48h ; 'H'
0x1800095bf  mov     rcx, [rax+0A0h]
0x1800095c6  mov     [rbx+160h], rcx
0x1800095cd  cmp     [rsp+880h+var_860], dl
0x1800095d1  jz      short loc_180009644
0x1800095d3  mov     r8, rsi; pcbe
0x1800095d6  lea     rcx, ResponseWaitTimeout; pfnti
0x1800095dd  mov     rdx, rbx; pv
0x1800095e0  call    cs:__imp_CreateThreadpoolTimer
0x1800095e6  mov     [rbx+1C8h], rax
0x1800095ed  test    rax, rax
0x1800095f0  jnz     short loc_180009644
0x1800095f2  call    cs:__imp_GetLastError
0x1800095f8  test    cs:byte_18002D803, dil
0x1800095ff  mov     esi, eax
0x180009601  jz      loc_180009916
0x180009607  xor     eax, eax
0x180009609  lea     rdx, aErrorAllocatin; "Error allocating response wait timeout "...
0x180009610  mov     r8d, esi
0x180009613  mov     word ptr [rsp+880h+var_850], ax
0x180009618  lea     rcx, [rsp+880h+var_850]
0x18000961d  call    FormatRRASErrorString
0x180009622  test    cs:byte_18002D803, dil
0x180009629  jz      loc_180009916
0x18000962f  lea     r8, [rsp+880h+var_850]
0x180009634  mov     rdx, r15
0x180009637  mov     rcx, r14
0x18000963a  call    McTemplateU0z_EventWriteTransfer
0x18000963f  jmp     loc_180009916
0x180009644  xorps   xmm0, xmm0
0x180009647  lea     rcx, SendToNetworkWorker; pfnwk
0x18000964e  movups  xmmword ptr [rbx+28h], xmm0
0x180009652  xor     eax, eax
0x180009654  mov     r8, rsi; pcbe
0x180009657  movups  xmmword ptr [rbx+38h], xmm0
0x18000965b  mov     [rbx+48h], rax
0x18000965f  mov     rdx, rbx; pv
0x180009662  mov     dword ptr [rbx+48h], 456Ah
0x180009669  call    cs:__imp_CreateThreadpoolWork
0x18000966f  mov     [rbx+148h], rax
0x180009676  test    rax, rax
0x180009679  jnz     short loc_1800096CD
0x18000967b  call    cs:__imp_GetLastError
0x180009681  test    cs:byte_18002D803, dil
0x180009688  mov     esi, eax
0x18000968a  jz      loc_1800098F7
0x180009690  xor     eax, eax
0x180009692  lea     rdx, aUnableToAlloca; "Unable to allocate send work item: %d"
0x180009699  mov     r8d, esi
0x18000969c  mov     word ptr [rsp+880h+var_850], ax
0x1800096a1  lea     rcx, [rsp+880h+var_850]
0x1800096a6  call    FormatRRASErrorString
0x1800096ab  test    cs:byte_18002D803, dil
0x1800096b2  jz      loc_1800098F7
0x1800096b8  lea     r8, [rsp+880h+var_850]
0x1800096bd  mov     rdx, r15
0x1800096c0  mov     rcx, r14
0x1800096c3  call    McTemplateU0z_EventWriteTransfer
0x1800096c8  jmp     loc_1800098F7
0x1800096cd  mov     r8, rsi; pcbe
0x1800096d0  lea     rcx, ProcessReceivedBytesWorker; pfnwk
0x1800096d7  mov     rdx, rbx; pv
0x1800096da  call    cs:__imp_CreateThreadpoolWork
0x1800096e0  xor     esi, esi
0x1800096e2  mov     [rbx+150h], rax
0x1800096e9  test    rax, rax
0x1800096ec  jnz     short loc_180009740
0x1800096ee  call    cs:__imp_GetLastError
0x1800096f4  test    cs:byte_18002D803, dil
0x1800096fb  mov     esi, eax
0x1800096fd  jz      loc_1800098DF
0x180009703  xor     eax, eax
0x180009705  lea     rdx, aUnableToAlloca_0; "Unable to allocate process received byt"...
0x18000970c  mov     r8d, esi
0x18000970f  mov     word ptr [rsp+880h+var_850], ax
0x180009714  lea     rcx, [rsp+880h+var_850]
0x180009719  call    FormatRRASErrorString
0x18000971e  test    cs:byte_18002D803, dil
0x180009725  jz      loc_1800098DF
0x18000972b  lea     r8, [rsp+880h+var_850]
0x180009730  mov     rdx, r15
0x180009733  mov     rcx, r14
0x180009736  call    McTemplateU0z_EventWriteTransfer
0x18000973b  jmp     loc_1800098DF
0x180009740  mov     dword ptr [rbx+0A0h], 456Bh
0x18000974a  xorps   xmm0, xmm0
0x18000974d  movups  xmmword ptr [rbx+80h], xmm0
0x180009754  movups  xmmword ptr [rbx+90h], xmm0
0x18000975b  mov     dword ptr [rbx+70h], 4571h
0x180009762  xorps   xmm1, xmm1
0x180009765  movups  xmmword ptr [rbx+50h], xmm0
0x180009769  movups  xmmword ptr [rbx+60h], xmm0
0x18000976d  mov     dword ptr [rbx+48h], 456Ah
0x180009774  movups  xmmword ptr [rbx+28h], xmm1
0x180009778  movups  xmmword ptr [rbx+38h], xmm1
0x18000977c  test    cs:byte_18002D803, 10h
0x180009783  jz      short loc_1800097C2
0x180009785  lea     r9, aFalse; "FALSE"
0x18000978c  mov     word ptr [rsp+880h+var_850], si
0x180009791  mov     r8, rbx
0x180009794  lea     rdx, aSettingPCallco; "Setting %p callcontext->SendOverlapPost"...
0x18000979b  lea     rcx, [rsp+880h+var_850]
0x1800097a0  call    FormatRRASErrorString
0x1800097a5  test    cs:byte_18002D803, 10h
0x1800097ac  jz      short loc_1800097C2
0x1800097ae  lea     r8, [rsp+880h+var_850]
0x1800097b3  mov     rcx, r14
0x1800097b6  lea     rdx, RasSSTPSvcTraceInfo
0x1800097bd  call    McTemplateU0z_EventWriteTransfer
0x1800097c2  mov     rcx, cs:SstpSvcGlobals
0x1800097c9  add     rcx, 0B8h; lpCriticalSection
0x1800097d0  mov     [rbx+100h], rsi
0x1800097d7  mov     [rbx+108h], si
0x1800097de  mov     [rbx+1B2h], sil
0x1800097e5  call    cs:__imp_EnterCriticalSection
0x1800097eb  mov     rcx, cs:SstpSvcGlobals
0x1800097f2  mov     rax, [rcx+0B0h]
0x1800097f9  test    rax, rax
0x1800097fc  jnz     short loc_180009803
0x1800097fe  lea     esi, [rax+57h]
0x180009801  jmp     short loc_180009823
0x180009803  mov     rdx, rbx
0x180009806  mov     rcx, rax
0x180009809  call    assign_HF_handle
0x18000980e  mov     rcx, cs:SstpSvcGlobals
0x180009815  mov     [rbx+0F4h], eax
0x18000981b  neg     eax
0x18000981d  sbb     esi, esi
0x18000981f  not     esi
0x180009821  and     esi, edi
0x180009823  add     rcx, 0B8h; lpCriticalSection
0x18000982a  call    cs:__imp_LeaveCriticalSection
0x180009830  test    esi, esi
0x180009832  jz      short loc_180009877
0x180009834  test    cs:byte_18002D803, dil
0x18000983b  jz      loc_1800098C7
0x180009841  xor     eax, eax
0x180009843  lea     rdx, aUnableToGetThe; "Unable to get the handle32 for the requ"...
0x18000984a  mov     r8d, esi
0x18000984d  mov     word ptr [rsp+880h+var_850], ax
0x180009852  lea     rcx, [rsp+880h+var_850]
0x180009857  call    FormatRRASErrorString
0x18000985c  test    cs:byte_18002D803, dil
0x180009863  jz      short loc_1800098C7
0x180009865  lea     r8, [rsp+880h+var_850]
0x18000986a  mov     rdx, r15
0x18000986d  mov     rcx, r14
0x180009870  call    McTemplateU0z_EventWriteTransfer
0x180009875  jmp     short loc_1800098C7
0x180009877  mov     rcx, cs:SstpSvcGlobals
0x18000987e  add     rcx, 0E0h; lpCriticalSection
0x180009885  call    cs:__imp_EnterCriticalSection
0x18000988b  mov     rcx, cs:SstpSvcGlobals
0x180009892  cmp     dword ptr [rcx], 3
0x180009895  jnz     loc_18000993D
0x18000989b  add     rcx, 0E0h; lpCriticalSection
0x1800098a2  call    cs:__imp_LeaveCriticalSection
0x1800098a8  mov     esi, 3E3h
0x1800098ad  mov     rcx, cs:SstpSvcGlobals
0x1800098b4  lea     rdx, [rbx+0F4h]
0x1800098bb  mov     rcx, [rcx+0B0h]
0x1800098c2  call    HfFreeHandle32
0x1800098c7  mov     rcx, [rbx+150h]; pwk
0x1800098ce  call    cs:__imp_CloseThreadpoolWork
0x1800098d4  mov     qword ptr [rbx+150h], 0
0x1800098df  mov     rcx, [rbx+148h]; pwk
0x1800098e6  call    cs:__imp_CloseThreadpoolWork
0x1800098ec  mov     qword ptr [rbx+148h], 0
0x1800098f7  cmp     [rsp+880h+var_860], 0
0x1800098fc  jz      short loc_180009916
0x1800098fe  mov     rcx, [rbx+1C8h]; pti
0x180009905  call    cs:__imp_CloseThreadpoolTimer
0x18000990b  mov     qword ptr [rbx+1C8h], 0
0x180009916  mov     rcx, r13; lpCriticalSection
0x180009919  call    cs:__imp_DeleteCriticalSection
0x18000991f  mov     rcx, cs:SstpSvcGlobals
0x180009926  mov     r8b, 1
0x180009929  add     rcx, 218h
0x180009930  mov     rdx, rbx
0x180009933  call    FreeBufferToPool
0x180009938  jmp     loc_1800099C6
0x18000993d  mov     rcx, r13; lpCriticalSection
0x180009940  mov     [rbx+0E8h], r12
0x180009947  mov     [r12], r12
0x18000994b  call    cs:__imp_EnterCriticalSection
0x180009951  xor     eax, eax
0x180009953  mov     dword ptr [rbx+0FCh], 1
0x18000995d  cmp     [rbx+0F8h], al
0x180009963  jz      short loc_18000997D
0x180009965  mov     [rbx+1B8h], rax
0x18000996c  mov     [rbx+1C0h], rax
  ... truncated ...
```
