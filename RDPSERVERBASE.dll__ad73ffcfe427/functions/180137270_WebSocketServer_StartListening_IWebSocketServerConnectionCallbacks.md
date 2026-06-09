# WebSocketServer::StartListening(IWebSocketServerConnectionCallbacks *)

- ea: `0x180137270`
- end: `0x180137637`
- name: `?StartListening@WebSocketServer@@UEAAJPEAUIWebSocketServerConnectionCallbacks@@@Z`
- size: `967`
- prototype: `__int64 __fastcall(PVOID pv, struct IWebSocketServerConnectionCallbacks *)`
- caller_count: `0`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000f660`
- `0x18003ab0c`
- `0x180076090`
- `0x180077aa0`
- `0x180079724`
- `0x18007a404`
- `0x18007f42c`
- `0x18007f6b0`
- `0x180136d90`
- `0x180137270`
- `0x18019c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013749b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013749b`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1801372c9`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18013733b`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180137393`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1801373df`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180137454`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1801374ce`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1801372c9`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18013733b`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180137393`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1801373df`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180137454`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1801374ce`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18013729f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18013729f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18013760a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18013760a`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x1801375e9`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x1801375e9`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18013759b`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18013759b`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180137491`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180137491`
- `HTTPAPI!HttpReceiveHttpRequest` at `0x1801375d1`
- `HTTPAPI!HttpReceiveHttpRequest` at `0x1801375d1`

## pseudocode

```c
__int64 __fastcall WebSocketServer::StartListening(char *pv, struct IWebSocketServerConnectionCallbacks *a2)
{
  int ActivityIdPrefix; // eax
  int v5; // ebx
  _DWORD *v6; // rsi
  unsigned int v7; // eax
  __int64 v8; // rdx
  int v9; // eax
  DWORD LastError; // ebp
  unsigned int v11; // eax
  unsigned int v12; // r14d
  size_t v13; // rbp
  void *v14; // rax
  void *v15; // rbx
  unsigned int i; // ebp
  __int64 v17; // rbx
  ULONG v18; // eax

  AcquireSRWLockExclusive((PSRWLOCK)pv + 8);
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      ActivityIdPrefix = RdpX_GetActivityIdPrefix();
      WPP_SF_Ds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        (unsigned int)&WPP_b1a8cc76119c395613772ef098e23945_Traceguids,
        ActivityIdPrefix,
        (__int64)"pConnectionCallbacks");
    }
    v5 = -2147467261;
    v6 = pv + 72;
    goto LABEL_43;
  }
  v5 = 0;
  v6 = pv + 72;
  if ( !*((_DWORD *)pv + 18) )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_43;
    }
    v7 = RdpX_GetActivityIdPrefix();
    v8 = 15;
    goto LABEL_12;
  }
  if ( *v6 != 1 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_43;
    }
    v7 = RdpX_GetActivityIdPrefix();
    v8 = 16;
    goto LABEL_12;
  }
  *v6 = 2;
  v5 = WebSocketServer::SetupHttpApi(pv);
  if ( v5 >= 0 )
  {
    if ( !(unsigned int)CTSCriticalSection::Initialize((CTSCriticalSection *)(pv + 376)) )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_43;
      }
      v7 = RdpX_GetActivityIdPrefix();
      v8 = 18;
LABEL_12:
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, &WPP_b1a8cc76119c395613772ef098e23945_Traceguids, v7);
      goto LABEL_43;
    }
    if ( CreateTimerQueueTimer(
           (PHANDLE)pv + 27,
           0,
           WebSocketServer::SecurityMonitoringTimer,
           pv,
           1000 * *((_DWORD *)pv + 33),
           1000 * *((_DWORD *)pv + 33),
           0) )
    {
      v12 = *((_DWORD *)pv + 32);
      *((_QWORD *)pv + 10) = a2;
      v13 = saturated_mul(v12, 0x6038u);
      v14 = operator new(v13);
      v15 = v14;
      if ( v14 )
      {
        memset_0(v14, 0, v13);
        `vector constructor iterator'(
          v15,
          0x6038u,
          v12,
          (void *(*)(void *))WebSocketServer::RECEIVE_REQUEST_OVERLAPPED::RECEIVE_REQUEST_OVERLAPPED);
      }
      else
      {
        v15 = 0;
      }
      *((_QWORD *)pv + 25) = v15;
      for ( i = 0; i < *((_DWORD *)pv + 32); ++i )
      {
        v17 = 24632LL * i;
        *(_DWORD *)(v17 + *((_QWORD *)pv + 25) + 32) = 0;
        *(_OWORD *)(v17 + *((_QWORD *)pv + 25) + 36) = 0xF4A10000;
        StartThreadpoolIo(*((PTP_IO *)pv + 20));
        v18 = HttpReceiveHttpRequest(
                *((HANDLE *)pv + 19),
                0,
                0,
                (PHTTP_REQUEST)(v17 + *((_QWORD *)pv + 25) + 56),
                0x6000u,
                0,
                (LPOVERLAPPED)(v17 + *((_QWORD *)pv + 25)));
        if ( v18 && v18 != 997 )
          CancelThreadpoolIo(*((PTP_IO *)pv + 20));
      }
      v5 = 0;
    }
    else
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v11 = RdpX_GetActivityIdPrefix();
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          19,
          &WPP_b1a8cc76119c395613772ef098e23945_Traceguids,
          v11,
          LastError);
      }
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v9 = RdpX_GetActivityIdPrefix();
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      17,
      (unsigned int)&WPP_b1a8cc76119c395613772ef098e23945_Traceguids,
      v9,
      (__int64)"Failed to setup HTTP listener",
      v5);
  }
LABEL_43:
  *v6 = v5 != 0 ? 5 : 3;
  ReleaseSRWLockExclusive((PSRWLOCK)pv + 8);
  if ( v5 < 0 )
    (*(void (__fastcall **)(char *))(*(_QWORD *)pv + 40LL))(pv);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180137270  push    rbx
0x180137272  push    rbp
0x180137273  push    rsi
0x180137274  push    rdi
0x180137275  push    r14
0x180137277  push    r15
0x180137279  sub     rsp, 68h
0x18013727d  xor     eax, eax
0x18013727f  movaps  [rsp+98h+var_48], xmm6
0x180137284  mov     rdi, rcx
0x180137287  mov     qword ptr [rsp+98h+var_58+4], rax
0x18013728c  add     rcx, 40h ; '@'; SRWLock
0x180137290  mov     dword ptr [rsp+98h+var_58+0Ch], eax
0x180137294  mov     rbp, rdx
0x180137297  mov     dword ptr [rsp+98h+var_58], 0F4A10000h
0x18013729f  call    cs:__imp_AcquireSRWLockExclusive
0x1801372a5  test    rbp, rbp
0x1801372a8  jnz     short loc_180137306
0x1801372aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1801372b1  lea     rax, WPP_GLOBAL_Control
0x1801372b8  cmp     rcx, rax
0x1801372bb  jz      short loc_1801372F8
0x1801372bd  test    byte ptr [rcx+1Ch], 8
0x1801372c1  jz      short loc_1801372F8
0x1801372c3  cmp     byte ptr [rcx+19h], 2
0x1801372c7  jb      short loc_1801372F8
0x1801372c9  call    cs:__imp_RdpX_GetActivityIdPrefix
0x1801372cf  lea     rcx, aPconnectioncal; "pConnectionCallbacks"
0x1801372d6  mov     r9d, eax
0x1801372d9  mov     qword ptr [rsp+98h+DueTime], rcx
0x1801372de  lea     edx, [rbp+0Eh]
0x1801372e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1801372e8  lea     r8, WPP_b1a8cc76119c395613772ef098e23945_Traceguids
0x1801372ef  mov     rcx, [rcx+10h]
0x1801372f3  call    WPP_SF_Ds
0x1801372f8  mov     ebx, 80004003h
0x1801372fd  lea     rsi, [rdi+48h]
0x180137301  jmp     loc_1801375F8
0x180137306  xor     ebx, ebx
0x180137308  lea     rsi, [rdi+48h]
0x18013730c  cmp     [rsi], ebx
0x18013730e  jnz     short loc_180137363
0x180137310  mov     rcx, cs:WPP_GLOBAL_Control
0x180137317  lea     rax, WPP_GLOBAL_Control
0x18013731e  cmp     rcx, rax
0x180137321  jz      loc_1801375F8
0x180137327  test    byte ptr [rcx+1Ch], 8
0x18013732b  jz      loc_1801375F8
0x180137331  cmp     byte ptr [rcx+19h], 2
0x180137335  jb      loc_1801375F8
0x18013733b  call    cs:__imp_RdpX_GetActivityIdPrefix
0x180137341  lea     edx, [rbx+0Fh]
0x180137344  mov     rcx, cs:WPP_GLOBAL_Control
0x18013734b  lea     r8, WPP_b1a8cc76119c395613772ef098e23945_Traceguids
0x180137352  mov     r9d, eax
0x180137355  mov     rcx, [rcx+10h]
0x180137359  call    WPP_SF_d
0x18013735e  jmp     loc_1801375F8
0x180137363  cmp     dword ptr [rsi], 1
0x180137366  jz      short loc_1801373A0
0x180137368  mov     rcx, cs:WPP_GLOBAL_Control
0x18013736f  lea     rax, WPP_GLOBAL_Control
0x180137376  cmp     rcx, rax
0x180137379  jz      loc_1801375F8
0x18013737f  test    byte ptr [rcx+1Ch], 8
0x180137383  jz      loc_1801375F8
0x180137389  cmp     byte ptr [rcx+19h], 2
0x18013738d  jb      loc_1801375F8
0x180137393  call    cs:__imp_RdpX_GetActivityIdPrefix
0x180137399  mov     edx, 10h
0x18013739e  jmp     short loc_180137344
0x1801373a0  mov     rcx, rdi; pv
0x1801373a3  mov     dword ptr [rsi], 2
0x1801373a9  call    ?SetupHttpApi@WebSocketServer@@AEAAJXZ; WebSocketServer::SetupHttpApi(void)
0x1801373ae  mov     ebx, eax
0x1801373b0  test    eax, eax
0x1801373b2  jns     short loc_180137419
0x1801373b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1801373bb  lea     rax, WPP_GLOBAL_Control
0x1801373c2  cmp     rcx, rax
0x1801373c5  jz      loc_1801375F8
0x1801373cb  test    byte ptr [rcx+1Ch], 8
0x1801373cf  jz      loc_1801375F8
0x1801373d5  cmp     byte ptr [rcx+19h], 2
0x1801373d9  jb      loc_1801375F8
0x1801373df  call    cs:__imp_RdpX_GetActivityIdPrefix
0x1801373e5  lea     rcx, aFailedToSetupH; "Failed to setup HTTP listener"
0x1801373ec  mov     [rsp+98h+Period], ebx
0x1801373f0  mov     qword ptr [rsp+98h+DueTime], rcx
0x1801373f5  lea     r8, WPP_b1a8cc76119c395613772ef098e23945_Traceguids
0x1801373fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180137403  mov     edx, 11h
0x180137408  mov     r9d, eax
0x18013740b  mov     rcx, [rcx+10h]
0x18013740f  call    WPP_SF_DsD
0x180137414  jmp     loc_1801375F8
0x180137419  lea     rcx, [rdi+178h]; this
0x180137420  call    ?Initialize@CTSCriticalSection@@QEAAHXZ; CTSCriticalSection::Initialize(void)
0x180137425  test    eax, eax
0x180137427  jnz     short loc_180137464
0x180137429  mov     rcx, cs:WPP_GLOBAL_Control
0x180137430  lea     rax, WPP_GLOBAL_Control
0x180137437  cmp     rcx, rax
0x18013743a  jz      loc_1801375F8
0x180137440  test    byte ptr [rcx+1Ch], 8
0x180137444  jz      loc_1801375F8
0x18013744a  cmp     byte ptr [rcx+19h], 2
0x18013744e  jb      loc_1801375F8
0x180137454  call    cs:__imp_RdpX_GetActivityIdPrefix
0x18013745a  mov     edx, 12h
0x18013745f  jmp     loc_180137344
0x180137464  imul    eax, [rdi+84h], 3E8h
0x18013746e  lea     rcx, [rdi+0D8h]; phNewTimer
0x180137475  mov     [rsp+98h+Flags], 0; Flags
0x18013747d  lea     r8, ?SecurityMonitoringTimer@WebSocketServer@@CAXPEAXE@Z; Callback
0x180137484  mov     r9, rdi; Parameter
0x180137487  xor     edx, edx; TimerQueue
0x180137489  mov     [rsp+98h+Period], eax; Period
0x18013748d  mov     [rsp+98h+DueTime], eax; DueTime
0x180137491  call    cs:__imp_CreateTimerQueueTimer
0x180137497  test    eax, eax
0x180137499  jnz     short loc_1801374FC
0x18013749b  call    cs:__imp_GetLastError
0x1801374a1  mov     ebp, eax
0x1801374a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1801374aa  lea     rax, WPP_GLOBAL_Control
0x1801374b1  cmp     rcx, rax
0x1801374b4  jz      loc_1801375F8
0x1801374ba  test    byte ptr [rcx+1Ch], 8
0x1801374be  jz      loc_1801375F8
0x1801374c4  cmp     byte ptr [rcx+19h], 2
0x1801374c8  jb      loc_1801375F8
0x1801374ce  call    cs:__imp_RdpX_GetActivityIdPrefix
0x1801374d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1801374db  lea     r8, WPP_b1a8cc76119c395613772ef098e23945_Traceguids
0x1801374e2  mov     edx, 13h
0x1801374e7  mov     [rsp+98h+DueTime], ebp
0x1801374eb  mov     r9d, eax
0x1801374ee  mov     rcx, [rcx+10h]
0x1801374f2  call    WPP_SF_Dd
0x1801374f7  jmp     loc_1801375F8
0x1801374fc  mov     r14d, [rdi+80h]
0x180137503  mov     eax, 6038h
0x180137508  mul     r14
0x18013750b  mov     [rdi+50h], rbp
0x18013750f  mov     rbp, rax
0x180137512  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180137519  cmovb   rbp, rax
0x18013751d  mov     rcx, rbp; Size
0x180137520  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180137525  mov     rbx, rax
0x180137528  test    rax, rax
0x18013752b  jz      short loc_180137553
0x18013752d  mov     r8, rbp; Size
0x180137530  xor     edx, edx; Val
0x180137532  mov     rcx, rax; void *
0x180137535  call    memset_0
0x18013753a  lea     r9, ??0RECEIVE_REQUEST_OVERLAPPED@WebSocketServer@@QEAA@XZ; void *(*)(void *)
0x180137541  mov     r8d, r14d; unsigned __int64
0x180137544  mov     edx, 6038h; unsigned __int64
0x180137549  mov     rcx, rbx; void *
0x18013754c  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x180137551  jmp     short loc_180137555
0x180137553  xor     ebx, ebx
0x180137555  movups  xmm6, [rsp+98h+var_58]
0x18013755a  mov     [rdi+0C8h], rbx
0x180137561  xor     ebp, ebp
0x180137563  cmp     ebp, [rdi+80h]
0x180137569  jnb     loc_1801375F6
0x18013756f  mov     eax, ebp
0x180137571  imul    rbx, rax, 6038h
0x180137578  mov     rax, [rdi+0C8h]
0x18013757f  mov     dword ptr [rbx+rax+20h], 0
0x180137587  mov     rax, [rdi+0C8h]
0x18013758e  movdqu  xmmword ptr [rbx+rax+24h], xmm6
0x180137594  mov     rcx, [rdi+0A0h]; pio
0x18013759b  call    cs:__imp_StartThreadpoolIo
0x1801375a1  mov     rcx, [rdi+0C8h]
0x1801375a8  xor     r8d, r8d; Flags
0x1801375ab  add     rcx, rbx
0x1801375ae  xor     edx, edx; RequestId
0x1801375b0  mov     qword ptr [rsp+98h+Flags], rcx; Overlapped
0x1801375b5  mov     qword ptr [rsp+98h+Period], 0; BytesReturned
0x1801375be  mov     [rsp+98h+DueTime], 6000h; RequestBufferLength
0x1801375c6  lea     r9, [rcx+38h]; RequestBuffer
0x1801375ca  mov     rcx, [rdi+98h]; RequestQueueHandle
0x1801375d1  call    cs:__imp_HttpReceiveHttpRequest
0x1801375d7  test    eax, eax
0x1801375d9  jz      short loc_1801375EF
0x1801375db  cmp     eax, 3E5h
0x1801375e0  jz      short loc_1801375EF
0x1801375e2  mov     rcx, [rdi+0A0h]; pio
0x1801375e9  call    cs:__imp_CancelThreadpoolIo
0x1801375ef  inc     ebp
0x1801375f1  jmp     loc_180137563
0x1801375f6  xor     ebx, ebx
0x1801375f8  mov     eax, ebx
0x1801375fa  lea     rcx, [rdi+40h]; SRWLock
0x1801375fe  neg     eax
0x180137600  sbb     edx, edx
0x180137602  and     edx, 2
0x180137605  add     edx, 3
0x180137608  mov     [rsi], edx
0x18013760a  call    cs:__imp_ReleaseSRWLockExclusive
0x180137610  test    ebx, ebx
0x180137612  jns     short loc_180137623
0x180137614  mov     rax, [rdi]
0x180137617  mov     rcx, rdi
0x18013761a  mov     rax, [rax+28h]
0x18013761e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180137623  movaps  xmm6, [rsp+98h+var_48]
0x180137628  mov     eax, ebx
0x18013762a  add     rsp, 68h
0x18013762e  pop     r15
0x180137630  pop     r14
0x180137632  pop     rdi
0x180137633  pop     rsi
0x180137634  pop     rbp
0x180137635  pop     rbx
0x180137636  retn
```
