# D3DCommon::DX10Framework::RunMainLoop(void)

- ea: `0x14008064c`
- end: `0x140080886`
- name: `?RunMainLoop@DX10Framework@D3DCommon@@QEAAJXZ`
- size: `570`
- prototype: `__int64 __fastcall(D3DCommon::DX10Framework *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140086a74`

## callees

- `0x14008064c`
- `0x140080a04`
- `0x140081584`
- `0x14008a958`
- `0x14011a010`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x1400806ca`
- `KERNEL32!GetTickCount` at `0x1400806ca`
- `KERNEL32!SetWaitableTimer` at `0x140080746`
- `KERNEL32!SetWaitableTimer` at `0x140080746`
- `KERNEL32!CreateWaitableTimerW` at `0x1400806e4`
- `KERNEL32!CreateWaitableTimerW` at `0x1400806e4`
- `KERNEL32!CancelWaitableTimer` at `0x14008085d`
- `KERNEL32!CancelWaitableTimer` at `0x14008085d`
- `KERNEL32!CloseHandle` at `0x140080867`
- `KERNEL32!CloseHandle` at `0x140080867`
- `KERNEL32!GetLastError` at `0x1400806f6`
- `KERNEL32!GetLastError` at `0x1400806f6`
- `USER32!TranslateMessage` at `0x1400807b3`
- `USER32!TranslateMessage` at `0x1400807b3`
- `USER32!PeekMessageW` at `0x14008069f`
- `USER32!PeekMessageW` at `0x1400807a5`
- `USER32!PeekMessageW` at `0x14008069f`
- `USER32!PeekMessageW` at `0x1400807a5`
- `USER32!MsgWaitForMultipleObjects` at `0x140080847`
- `USER32!MsgWaitForMultipleObjects` at `0x140080847`
- `USER32!PostMessageW` at `0x14008078b`
- `USER32!PostMessageW` at `0x14008081f`
- `USER32!PostMessageW` at `0x14008078b`
- `USER32!PostMessageW` at `0x14008081f`
- `USER32!DispatchMessageW` at `0x1400807bd`
- `USER32!DispatchMessageW` at `0x1400807bd`

## pseudocode

```c
__int64 __fastcall D3DCommon::DX10Framework::RunMainLoop(D3DCommon::DX10Framework *this)
{
  __int64 v2; // rbx
  HANDLE WaitableTimerW; // rcx
  signed int LastError; // eax
  signed int v5; // ebx
  char v6; // si
  bool v7; // sf
  unsigned int *v8; // r9
  struct tagMSG Msg; // [rsp+30h] [rbp-30h] BYREF
  HANDLE pHandles; // [rsp+80h] [rbp+20h] BYREF
  LARGE_INTEGER DueTime; // [rsp+88h] [rbp+28h] BYREF

  memset(&Msg, 0, sizeof(Msg));
  pHandles = 0;
  if ( !*((_QWORD *)this + 5) || !*((_QWORD *)this + 1) )
    return 2147500035LL;
  PeekMessageW(&Msg, 0, 0, 0, 0);
  *((_DWORD *)this + 20) = 0;
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 8LL))(*((_QWORD *)this + 1));
  D3DCommon::DX10Framework::p_RenderFrame(this, 0);
  v2 = *((_QWORD *)this + 1);
  *(_DWORD *)(v2 + 8) = GetTickCount();
  if ( !*(_DWORD *)(*((_QWORD *)this + 1) + 56LL) )
  {
    pHandles = 0;
LABEL_10:
    v6 = 0;
    while ( 1 )
    {
      if ( Msg.message == 18 )
      {
        v5 = 0;
        goto LABEL_26;
      }
      if ( dword_1401CBAC0 && !v6 )
      {
        v6 = 1;
        PostMessageW(hWnd, 0x8000u, 0, 0);
      }
      if ( PeekMessageW(&Msg, 0, 0, 0, 1u) )
        break;
      if ( !D3DCommon::TickTimer::TimeExpired((D3DCommon::TickTimer *)(*((_QWORD *)this + 1) + 8LL)) )
      {
        v5 = D3DCommon::DX10Framework::p_RenderFrame(this, 0);
        v7 = v5 < 0;
LABEL_19:
        if ( v7 )
          goto LABEL_26;
        goto LABEL_23;
      }
      v5 = D3DCommon::DX10Framework::p_RenderFrame(this, 1);
      if ( v5 < 0 )
        goto LABEL_26;
      D3DCommon::LogMessage((D3DCommon *)0x50, *((_DWORD *)this + 4), 0, v8);
      PostMessageW(hWnd, 0x8000u, 0, 0);
LABEL_23:
      if ( pHandles )
        MsgWaitForMultipleObjects(1u, &pHandles, 0, 0xFFFFFFFF, 0x1CBFu);
    }
    TranslateMessage(&Msg);
    DispatchMessageW(&Msg);
    v5 = D3DCommon::DX10Framework::sm_hrWndProcResult;
    v7 = D3DCommon::DX10Framework::sm_hrWndProcResult < 0;
    goto LABEL_19;
  }
  WaitableTimerW = CreateWaitableTimerW(0, 0, 0);
  pHandles = WaitableTimerW;
  if ( WaitableTimerW )
  {
    DueTime.QuadPart = 0;
    if ( SetWaitableTimer(WaitableTimerW, &DueTime, 0x3E8u / *(_DWORD *)(*((_QWORD *)this + 1) + 56LL), 0, 0, 0) )
      goto LABEL_10;
  }
  LastError = GetLastError();
  v5 = LastError;
  if ( LastError > 0 )
    v5 = (unsigned __int16)LastError | 0x80070000;
LABEL_26:
  if ( pHandles )
  {
    CancelWaitableTimer(pHandles);
    CloseHandle(pHandles);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14008064c  mov     [rsp-18h+arg_10], rbx
0x140080651  push    rbp
0x140080652  push    rsi
0x140080653  push    rdi
0x140080654  mov     rbp, rsp
0x140080657  sub     rsp, 60h
0x14008065b  mov     rdi, rcx
0x14008065e  xorps   xmm0, xmm0
0x140080661  movups  xmmword ptr [rbp+Msg.hwnd], xmm0
0x140080665  movups  xmmword ptr [rbp+Msg.wParam], xmm0
0x140080669  movups  xmmword ptr [rbp+Msg.time], xmm0
0x14008066d  mov     [rbp+pHandles], 0
0x140080675  cmp     qword ptr [rcx+28h], 0
0x14008067a  jz      loc_140080871
0x140080680  cmp     qword ptr [rcx+8], 0
0x140080685  jz      loc_140080871
0x14008068b  mov     [rsp+60h+wRemoveMsg], 0; wRemoveMsg
0x140080693  xor     r9d, r9d; wMsgFilterMax
0x140080696  xor     r8d, r8d; wMsgFilterMin
0x140080699  xor     edx, edx; hWnd
0x14008069b  lea     rcx, [rbp+Msg]; lpMsg
0x14008069f  call    cs:__imp_PeekMessageW
0x1400806a5  mov     dword ptr [rdi+50h], 0
0x1400806ac  mov     rcx, [rdi+8]
0x1400806b0  mov     rax, [rcx]
0x1400806b3  mov     rax, [rax+8]
0x1400806b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400806bc  xor     edx, edx; bool
0x1400806be  mov     rcx, rdi; this
0x1400806c1  call    ?p_RenderFrame@DX10Framework@D3DCommon@@AEAAJ_N@Z; D3DCommon::DX10Framework::p_RenderFrame(bool)
0x1400806c6  mov     rbx, [rdi+8]
0x1400806ca  call    cs:__imp_GetTickCount
0x1400806d0  mov     [rbx+8], eax
0x1400806d3  mov     rax, [rdi+8]
0x1400806d7  cmp     dword ptr [rax+38h], 0
0x1400806db  jbe     short loc_140080752
0x1400806dd  xor     r8d, r8d; lpTimerName
0x1400806e0  xor     edx, edx; bManualReset
0x1400806e2  xor     ecx, ecx; lpTimerAttributes
0x1400806e4  call    cs:__imp_CreateWaitableTimerW
0x1400806ea  mov     rcx, rax; hTimer
0x1400806ed  mov     [rbp+pHandles], rax
0x1400806f1  test    rax, rax
0x1400806f4  jnz     short loc_140080714
0x1400806f6  call    cs:__imp_GetLastError
0x1400806fc  mov     ebx, eax
0x1400806fe  test    eax, eax
0x140080700  jle     loc_140080854
0x140080706  movzx   ebx, ax
0x140080709  or      ebx, 80070000h
0x14008070f  jmp     loc_140080854
0x140080714  mov     qword ptr [rbp+DueTime], 0
0x14008071c  mov     r8, [rdi+8]
0x140080720  xor     edx, edx
0x140080722  mov     eax, 3E8h
0x140080727  div     dword ptr [r8+38h]
0x14008072b  mov     r8d, eax; lPeriod
0x14008072e  mov     [rsp+60h+fResume], 0; fResume
0x140080736  mov     qword ptr [rsp+60h+wRemoveMsg], 0; lpArgToCompletionRoutine
0x14008073f  xor     r9d, r9d; pfnCompletionRoutine
0x140080742  lea     rdx, [rbp+DueTime]; lpDueTime
0x140080746  call    cs:__imp_SetWaitableTimer
0x14008074c  test    eax, eax
0x14008074e  jnz     short loc_14008075A
0x140080750  jmp     short loc_1400806F6
0x140080752  mov     [rbp+pHandles], 0
0x14008075a  xor     sil, sil
0x14008075d  cmp     [rbp+Msg.message], 12h
0x140080761  jz      loc_140080852
0x140080767  mov     eax, cs:dword_1401CBAC0
0x14008076d  test    eax, eax
0x14008076f  jz      short loc_140080791
0x140080771  test    sil, sil
0x140080774  jnz     short loc_140080791
0x140080776  mov     sil, 1
0x140080779  xor     r9d, r9d; lParam
0x14008077c  xor     r8d, r8d; wParam
0x14008077f  mov     edx, 8000h; Msg
0x140080784  mov     rcx, cs:hWnd; hWnd
0x14008078b  call    cs:__imp_PostMessageW
0x140080791  mov     [rsp+60h+wRemoveMsg], 1; wRemoveMsg
0x140080799  xor     r9d, r9d; wMsgFilterMax
0x14008079c  xor     r8d, r8d; wMsgFilterMin
0x14008079f  xor     edx, edx; hWnd
0x1400807a1  lea     rcx, [rbp+Msg]; lpMsg
0x1400807a5  call    cs:__imp_PeekMessageW
0x1400807ab  test    eax, eax
0x1400807ad  jz      short loc_1400807CD
0x1400807af  lea     rcx, [rbp+Msg]; lpMsg
0x1400807b3  call    cs:__imp_TranslateMessage
0x1400807b9  lea     rcx, [rbp+Msg]; lpMsg
0x1400807bd  call    cs:__imp_DispatchMessageW
0x1400807c3  mov     ebx, cs:?sm_hrWndProcResult@DX10Framework@D3DCommon@@0JA; long D3DCommon::DX10Framework::sm_hrWndProcResult
0x1400807c9  test    ebx, ebx
0x1400807cb  jmp     short loc_1400807EC
0x1400807cd  mov     rcx, [rdi+8]
0x1400807d1  add     rcx, 8; this
0x1400807d5  call    ?TimeExpired@TickTimer@D3DCommon@@QEAA_NXZ; D3DCommon::TickTimer::TimeExpired(void)
0x1400807da  mov     rcx, rdi; this
0x1400807dd  test    al, al
0x1400807df  jnz     short loc_1400807F0
0x1400807e1  xor     edx, edx; bool
0x1400807e3  call    ?p_RenderFrame@DX10Framework@D3DCommon@@AEAAJ_N@Z; D3DCommon::DX10Framework::p_RenderFrame(bool)
0x1400807e8  mov     ebx, eax
0x1400807ea  test    eax, eax
0x1400807ec  js      short loc_140080854
0x1400807ee  jmp     short loc_140080825
0x1400807f0  mov     dl, 1; bool
0x1400807f2  call    ?p_RenderFrame@DX10Framework@D3DCommon@@AEAAJ_N@Z; D3DCommon::DX10Framework::p_RenderFrame(bool)
0x1400807f7  mov     ebx, eax
0x1400807f9  test    eax, eax
0x1400807fb  js      short loc_140080854
0x1400807fd  mov     ecx, 50h ; 'P'; this
0x140080802  xor     r8d, r8d; unsigned int
0x140080805  mov     edx, [rdi+10h]; unsigned __int16
0x140080808  call    ?LogMessage@D3DCommon@@YAJGKPEAI@Z; D3DCommon::LogMessage(ushort,ulong,uint *)
0x14008080d  xor     r9d, r9d; lParam
0x140080810  xor     r8d, r8d; wParam
0x140080813  mov     edx, 8000h; Msg
0x140080818  mov     rcx, cs:hWnd; hWnd
0x14008081f  call    cs:__imp_PostMessageW
0x140080825  cmp     [rbp+pHandles], 0
0x14008082a  jz      loc_14008075D
0x140080830  mov     [rsp+60h+wRemoveMsg], 1CBFh; dwWakeMask
0x140080838  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x14008083c  xor     r8d, r8d; fWaitAll
0x14008083f  lea     rdx, [rbp+pHandles]; pHandles
0x140080843  lea     ecx, [r8+1]; nCount
0x140080847  call    cs:__imp_MsgWaitForMultipleObjects
0x14008084d  jmp     loc_14008075D
0x140080852  xor     ebx, ebx
0x140080854  mov     rcx, [rbp+pHandles]; hTimer
0x140080858  test    rcx, rcx
0x14008085b  jz      short loc_14008086D
0x14008085d  call    cs:__imp_CancelWaitableTimer
0x140080863  mov     rcx, [rbp+pHandles]; hObject
0x140080867  call    cs:__imp_CloseHandle
0x14008086d  mov     eax, ebx
0x14008086f  jmp     short loc_140080876
0x140080871  mov     eax, 80004003h
0x140080876  mov     rbx, [rsp+60h+arg_10]
0x14008087e  add     rsp, 60h
0x140080882  pop     rdi
0x140080883  pop     rsi
0x140080884  pop     rbp
0x140080885  retn
```
