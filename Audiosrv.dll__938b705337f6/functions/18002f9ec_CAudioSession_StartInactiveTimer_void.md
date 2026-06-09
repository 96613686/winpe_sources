# CAudioSession::StartInactiveTimer(void)

- ea: `0x18002f9ec`
- end: `0x18002fd2c`
- name: `?StartInactiveTimer@CAudioSession@@QEAAXXZ`
- size: `832`
- prototype: `void __fastcall(CAudioSession *__hidden this)`
- caller_count: `3`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x18000fe60`
- `0x1800329f0`
- `0x180034d70`

## callees

- `0x18002a04c`
- `0x18002f9ec`
- `0x18002fd34`
- `0x180030a64`
- `0x1800cdfbc`
- `0x1800cfd9c`
- `0x18016b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002fa12`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002fa12`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002fc9b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002fc9b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002fb2a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002fb2a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002fb39`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002fb39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fa8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fc1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fce1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fcf8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fa8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fc1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fce1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fcf8`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18002fa69`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18002fa69`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18002faa7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18002faa7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x18002fa80`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x18002fa80`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18002fc04`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18002fc04`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x18002fac2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x18002fac2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002fc57`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002fc57`

## string_xrefs

- `0x18002fd16`: `avcore\audiocore\server\audiosrv\dll\audiosession.cpp`

## pseudocode

```c
void __fastcall CAudioSession::StartInactiveTimer(CAudioSession *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // r15
  __int64 v3; // rsi
  __int64 v4; // r12
  _QWORD *v5; // r14
  signed int v6; // edi
  PTP_POOL Threadpool; // rax
  signed int v8; // eax
  PTP_CLEANUP_GROUP ThreadpoolCleanupGroup; // rax
  PTP_TIMER *v10; // rax
  PTP_TIMER *v11; // rbx
  HANDLE ProcessHeap; // rax
  _DWORD *v13; // rax
  _DWORD *v14; // rdi
  volatile signed __int32 *v15; // r14
  _BYTE *v16; // rcx
  _BYTE *v17; // rdx
  PTP_TIMER ThreadpoolTimer; // rax
  struct _TP_TIMER *v19; // rsi
  signed int v20; // eax
  _QWORD *v21; // rdx
  signed int LastError; // eax
  signed int v23; // eax
  _QWORD v24[7]; // [rsp+20h] [rbp-69h] BYREF
  _QWORD *v25; // [rsp+58h] [rbp-31h]
  _BYTE v26[56]; // [rsp+60h] [rbp-29h] BYREF
  _BYTE *v27; // [rsp+98h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]
  struct _FILETIME pftDueTime; // [rsp+F0h] [rbp+67h] BYREF

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 496);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 496));
  v3 = (*(__int64 (__fastcall **)(struct IAudioService *))(*(_QWORD *)g_AudioService + 120LL))(g_AudioService);
  v24[0] = off_18016EF18;
  v24[1] = this;
  v25 = v24;
  v4 = *((unsigned int *)this + 60);
  v5 = 0;
  v6 = 0;
  if ( *(_BYTE *)(v3 + 80) )
    goto LABEL_28;
  if ( !*(_QWORD *)v3 )
  {
    Threadpool = CreateThreadpool(0);
    *(_QWORD *)v3 = Threadpool;
    if ( !Threadpool )
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      if ( v6 < 0 )
        goto LABEL_28;
    }
    if ( !SetThreadpoolThreadMinimum(*(PTP_POOL *)v3, 1u) )
    {
      v8 = GetLastError();
      v6 = v8;
      if ( v8 > 0 )
        v6 = (unsigned __int16)v8 | 0x80070000;
      if ( v6 < 0 )
        goto LABEL_28;
    }
    ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
    *(_QWORD *)(v3 + 168) = ThreadpoolCleanupGroup;
    if ( !ThreadpoolCleanupGroup )
    {
      v23 = GetLastError();
      v6 = v23;
      if ( v23 > 0 )
        v6 = (unsigned __int16)v23 | 0x80070000;
      if ( v6 < 0 )
        goto LABEL_28;
    }
    SetThreadpoolThreadMaximum(*(PTP_POOL *)v3, 1u);
    *(_QWORD *)(v3 + 16) = *(_QWORD *)v3;
    *(_QWORD *)(v3 + 24) = *(_QWORD *)(v3 + 168);
    *(_QWORD *)(v3 + 32) = 0;
  }
  v10 = (PTP_TIMER *)operator new[](0x20u, (const struct std::nothrow_t *)&std::nothrow);
  v11 = v10;
  if ( v10 )
  {
    *v10 = 0;
    v10[1] = 0;
    v10[2] = 0;
    v27 = 0;
    if ( v25 )
      v27 = (_BYTE *)(*(__int64 (__fastcall **)(_QWORD *, _BYTE *))*v25)(v25, v26);
    v11[3] = (PTP_TIMER)v3;
    ProcessHeap = GetProcessHeap();
    v13 = HeapAlloc(ProcessHeap, 0, 0x50u);
    v14 = v13;
    if ( v13 )
    {
      v13[2] = 1;
      v13[3] = 1;
      *(_QWORD *)v13 = &std::_Ref_count_obj2<std::function<long (SystemEffectDescriptor *,SystemEffectChainDescriptor *)>>::`vftable';
      std::function<void (IAudioStreamInfo *)>::function<void (IAudioStreamInfo *)>(v13 + 4, v26);
    }
    else
    {
      v14 = 0;
    }
    v11[1] = (PTP_TIMER)(v14 + 4);
    v15 = (volatile signed __int32 *)v11[2];
    v11[2] = (PTP_TIMER)v14;
    if ( v15 )
    {
      if ( _InterlockedExchangeAdd(v15 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
        if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
      }
    }
    v5 = v11[1];
    v6 = v5 == 0 ? 0x8007000E : 0;
    v16 = v27;
    if ( v27 )
    {
      v17 = v26;
      LOBYTE(v17) = v27 != v26;
      (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v27 + 32LL))(v27, v17);
    }
    if ( v5 )
    {
      ThreadpoolTimer = CreateThreadpoolTimer(CSerialWorkQueue::TimerCallback, v11, (PTP_CALLBACK_ENVIRON)(v3 + 8));
      v19 = ThreadpoolTimer;
      v5 = 0;
      if ( ThreadpoolTimer )
      {
        v6 = 0;
        *v11 = ThreadpoolTimer;
LABEL_27:
        pftDueTime = (struct _FILETIME)(-10000 * v4);
        SetThreadpoolTimer(v19, &pftDueTime, 0, 0);
        std::unique_ptr<_RecurringTask>::reset((char *)this + 536, v11);
        goto LABEL_28;
      }
      v20 = GetLastError();
      v6 = v20;
      if ( v20 > 0 )
        v6 = (unsigned __int16)v20 | 0x80070000;
      *v11 = 0;
      if ( v6 >= 0 )
        goto LABEL_27;
    }
    std::default_delete<_RecurringTask>::operator()(v16, v11);
  }
  else
  {
    v6 = -2147024882;
  }
LABEL_28:
  if ( v25 )
  {
    v21 = v24;
    LOBYTE(v21) = v25 != v24;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v25 + 32LL))(v25, v21);
    v25 = v5;
  }
  if ( v6 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xDCD,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audiosession.cpp",
      (const char *)(unsigned int)v6,
      v24[0]);
  if ( v2 )
    LeaveCriticalSection(v2);
}

```

## disassembly

```asm
0x18002f9ec  push    rbp
0x18002f9ee  push    rbx
0x18002f9ef  push    rsi
0x18002f9f0  push    rdi
0x18002f9f1  push    r12
0x18002f9f3  push    r13
0x18002f9f5  push    r14
0x18002f9f7  push    r15
0x18002f9f9  lea     rbp, [rsp-1Fh]
0x18002f9fe  sub     rsp, 0A8h
0x18002fa05  mov     r13, rcx
0x18002fa08  lea     r15, [rcx+1F0h]
0x18002fa0f  mov     rcx, r15; lpCriticalSection
0x18002fa12  call    cs:__imp_EnterCriticalSection
0x18002fa18  mov     rcx, cs:?g_AudioService@@3PEAVIAudioService@@EA; IAudioService * g_AudioService
0x18002fa1f  mov     rax, [rcx]
0x18002fa22  mov     rax, [rax+78h]
0x18002fa26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fa2b  mov     rsi, rax
0x18002fa2e  lea     rax, off_18016EF18
0x18002fa35  mov     [rbp+57h+var_C0], rax
0x18002fa39  mov     [rbp+57h+var_B8], r13
0x18002fa3d  lea     rax, [rbp+57h+var_C0]
0x18002fa41  mov     [rbp+57h+var_88], rax
0x18002fa45  mov     r12d, [r13+0F0h]
0x18002fa4c  xor     r14d, r14d
0x18002fa4f  mov     edi, r14d
0x18002fa52  mov     cl, [rsi+50h]
0x18002fa55  nop
0x18002fa56  test    cl, cl
0x18002fa58  jnz     loc_18002FC6C
0x18002fa5e  lea     ebx, [r14+1]
0x18002fa62  cmp     [rsi], r14
0x18002fa65  jnz     short loc_18002FADE
0x18002fa67  xor     ecx, ecx; reserved
0x18002fa69  call    cs:__imp_CreateThreadpool
0x18002fa6f  mov     [rsi], rax
0x18002fa72  test    rax, rax
0x18002fa75  jz      loc_18002FCE1
0x18002fa7b  mov     edx, ebx; cthrdMic
0x18002fa7d  mov     rcx, [rsi]; ptpp
0x18002fa80  call    cs:__imp_SetThreadpoolThreadMinimum
0x18002fa86  test    eax, eax
0x18002fa88  jnz     short loc_18002FAA7
0x18002fa8a  call    cs:__imp_GetLastError
0x18002fa90  mov     edi, eax
0x18002fa92  test    eax, eax
0x18002fa94  jle     short loc_18002FA9F
0x18002fa96  movzx   edi, ax
0x18002fa99  or      edi, 80070000h
0x18002fa9f  test    edi, edi
0x18002faa1  js      loc_18002FC6C
0x18002faa7  call    cs:__imp_CreateThreadpoolCleanupGroup
0x18002faad  mov     [rsi+0A8h], rax
0x18002fab4  test    rax, rax
0x18002fab7  jz      loc_18002FCF8
0x18002fabd  mov     edx, ebx; cthrdMost
0x18002fabf  mov     rcx, [rsi]; ptpp
0x18002fac2  call    cs:__imp_SetThreadpoolThreadMaximum
0x18002fac8  mov     rax, [rsi]
0x18002facb  mov     [rsi+10h], rax
0x18002facf  mov     rax, [rsi+0A8h]
0x18002fad6  mov     [rsi+18h], rax
0x18002fada  mov     [rsi+20h], r14
0x18002fade  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002fae5  mov     ecx, 20h ; ' '; unsigned __int64
0x18002faea  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18002faef  mov     rbx, rax
0x18002faf2  test    rax, rax
0x18002faf5  jz      loc_18002FCC0
0x18002fafb  mov     [rax], r14
0x18002fafe  mov     [rax+8], r14
0x18002fb02  mov     [rax+10h], r14
0x18002fb06  mov     [rbp+57h+var_48], r14
0x18002fb0a  mov     rcx, [rbp+57h+var_88]
0x18002fb0e  test    rcx, rcx
0x18002fb11  jz      short loc_18002FB26
0x18002fb13  mov     rax, [rcx]
0x18002fb16  lea     rdx, [rbp+57h+var_80]
0x18002fb1a  mov     rax, [rax]
0x18002fb1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fb22  mov     [rbp+57h+var_48], rax
0x18002fb26  mov     [rbx+18h], rsi
0x18002fb2a  call    cs:__imp_GetProcessHeap
0x18002fb30  mov     rcx, rax; hHeap
0x18002fb33  xor     edx, edx; dwFlags
0x18002fb35  lea     r8d, [rdx+50h]; dwBytes
0x18002fb39  call    cs:__imp_HeapAlloc
0x18002fb3f  mov     rdi, rax
0x18002fb42  test    rax, rax
0x18002fb45  jz      loc_18002FCC7
0x18002fb4b  mov     eax, 1
0x18002fb50  mov     [rdi+8], eax
0x18002fb53  mov     [rdi+0Ch], eax
0x18002fb56  lea     rax, ??_7?$_Ref_count_obj2@V?$function@$$A6AJPEAVSystemEffectDescriptor@@PEAVSystemEffectChainDescriptor@@@Z@std@@@std@@6B@; const std::_Ref_count_obj2<std::function<long (SystemEffectDescriptor *,SystemEffectChainDescriptor *)>>::`vftable'
0x18002fb5d  mov     [rdi], rax
0x18002fb60  lea     rcx, [rdi+10h]
0x18002fb64  lea     rdx, [rbp+57h+var_80]
0x18002fb68  call    ??0?$function@$$A6AXPEAUIAudioStreamInfo@@@Z@std@@QEAA@AEBV01@@Z; std::function<void (IAudioStreamInfo *)>::function<void (IAudioStreamInfo *)>(std::function<void (IAudioStreamInfo *)> const &)
0x18002fb6d  lea     rax, [rdi+10h]
0x18002fb71  mov     [rbx+8], rax
0x18002fb75  mov     r14, [rbx+10h]
0x18002fb79  mov     [rbx+10h], rdi
0x18002fb7d  test    r14, r14
0x18002fb80  jz      short loc_18002FBBA
0x18002fb82  or      edi, 0FFFFFFFFh
0x18002fb85  mov     eax, edi
0x18002fb87  lock xadd [r14+8], eax
0x18002fb8d  add     eax, edi
0x18002fb8f  jnz     short loc_18002FBBA
0x18002fb91  mov     rax, [r14]
0x18002fb94  mov     rcx, r14
0x18002fb97  mov     rax, [rax]
0x18002fb9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fb9f  mov     eax, edi
0x18002fba1  lock xadd [r14+0Ch], eax
0x18002fba7  add     eax, edi
0x18002fba9  jnz     short loc_18002FBBA
0x18002fbab  mov     rax, [r14]
0x18002fbae  mov     rcx, r14
0x18002fbb1  mov     rax, [rax+8]
0x18002fbb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fbba  mov     r14, [rbx+8]
0x18002fbbe  mov     rax, r14
0x18002fbc1  neg     rax
0x18002fbc4  sbb     edi, edi
0x18002fbc6  not     edi
0x18002fbc8  and     edi, 8007000Eh
0x18002fbce  mov     rcx, [rbp+57h+var_48]
0x18002fbd2  test    rcx, rcx
0x18002fbd5  jz      short loc_18002FBED
0x18002fbd7  mov     rax, [rcx]
0x18002fbda  lea     rdx, [rbp+57h+var_80]
0x18002fbde  cmp     rcx, rdx
0x18002fbe1  setnz   dl
0x18002fbe4  mov     rax, [rax+20h]
0x18002fbe8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fbed  test    r14, r14
0x18002fbf0  jz      loc_18002FCB6
0x18002fbf6  lea     r8, [rsi+8]; pcbe
0x18002fbfa  mov     rdx, rbx; pv
0x18002fbfd  lea     rcx, ?TimerCallback@CSerialWorkQueue@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18002fc04  call    cs:__imp_CreateThreadpoolTimer
0x18002fc0a  mov     rsi, rax
0x18002fc0d  xor     r14d, r14d
0x18002fc10  test    rax, rax
0x18002fc13  jz      short loc_18002FC1D
0x18002fc15  mov     edi, r14d
0x18002fc18  mov     [rbx], rax
0x18002fc1b  jmp     short loc_18002FC39
0x18002fc1d  call    cs:__imp_GetLastError
0x18002fc23  mov     edi, eax
0x18002fc25  test    eax, eax
0x18002fc27  jle     short loc_18002FC32
0x18002fc29  movzx   edi, ax
0x18002fc2c  or      edi, 80070000h
0x18002fc32  mov     [rbx], rsi
0x18002fc35  test    edi, edi
0x18002fc37  js      short loc_18002FCB6
0x18002fc39  imul    rax, r12, 0FFFFFFFFFFFFD8F0h
0x18002fc40  mov     [rbp+57h+pftDueTime.dwLowDateTime], eax
0x18002fc43  shr     rax, 20h
0x18002fc47  mov     [rbp+57h+pftDueTime.dwHighDateTime], eax
0x18002fc4a  xor     r9d, r9d; msWindowLength
0x18002fc4d  xor     r8d, r8d; msPeriod
0x18002fc50  lea     rdx, [rbp+57h+pftDueTime]; pftDueTime
0x18002fc54  mov     rcx, rsi; pti
0x18002fc57  call    cs:__imp_SetThreadpoolTimer
0x18002fc5d  lea     rcx, [r13+218h]
0x18002fc64  mov     rdx, rbx
0x18002fc67  call    ?reset@?$unique_ptr@U_RecurringTask@@U?$default_delete@U_RecurringTask@@@std@@@std@@QEAAXPEAU_RecurringTask@@@Z; std::unique_ptr<_RecurringTask>::reset(_RecurringTask *)
0x18002fc6c  mov     rcx, [rbp+57h+var_88]
0x18002fc70  test    rcx, rcx
0x18002fc73  jz      short loc_18002FC8F
0x18002fc75  mov     rax, [rcx]
0x18002fc78  lea     rdx, [rbp+57h+var_C0]
0x18002fc7c  cmp     rcx, rdx
0x18002fc7f  setnz   dl
0x18002fc82  mov     rax, [rax+20h]
0x18002fc86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fc8b  mov     [rbp+57h+var_88], r14
0x18002fc8f  test    edi, edi
0x18002fc91  js      short loc_18002FD0F
0x18002fc93  test    r15, r15
0x18002fc96  jz      short loc_18002FCA2
0x18002fc98  mov     rcx, r15; lpCriticalSection
0x18002fc9b  call    cs:__imp_LeaveCriticalSection
0x18002fca1  nop
0x18002fca2  add     rsp, 0A8h
0x18002fca9  pop     r15
0x18002fcab  pop     r14
0x18002fcad  pop     r13
0x18002fcaf  pop     r12
0x18002fcb1  pop     rdi
0x18002fcb2  pop     rsi
0x18002fcb3  pop     rbx
0x18002fcb4  pop     rbp
0x18002fcb5  retn
0x18002fcb6  mov     rdx, rbx
0x18002fcb9  call    ??R?$default_delete@U_RecurringTask@@@std@@QEBAXPEAU_RecurringTask@@@Z; std::default_delete<_RecurringTask>::operator()(_RecurringTask *)
0x18002fcbe  jmp     short loc_18002FC6C
0x18002fcc0  mov     edi, 8007000Eh
0x18002fcc5  jmp     short loc_18002FC6C
0x18002fcc7  mov     rdi, r14
0x18002fcca  jmp     loc_18002FB6D
0x18002fccf  test    edi, edi
0x18002fcd1  js      short loc_18002FC6C
0x18002fcd3  jmp     loc_18002FA7B
0x18002fcd8  test    edi, edi
0x18002fcda  js      short loc_18002FC6C
0x18002fcdc  jmp     loc_18002FABD
0x18002fce1  call    cs:__imp_GetLastError
0x18002fce7  mov     edi, eax
0x18002fce9  test    eax, eax
0x18002fceb  jle     short loc_18002FCCF
0x18002fced  movzx   edi, ax
0x18002fcf0  or      edi, 80070000h
0x18002fcf6  jmp     short loc_18002FCCF
0x18002fcf8  call    cs:__imp_GetLastError
0x18002fcfe  mov     edi, eax
0x18002fd00  test    eax, eax
0x18002fd02  jle     short loc_18002FCD8
0x18002fd04  movzx   edi, ax
0x18002fd07  or      edi, 80070000h
0x18002fd0d  jmp     short loc_18002FCD8
0x18002fd0f  mov     rcx, [rbp+5Fh]; this
0x18002fd13  mov     r9d, edi; char *
0x18002fd16  lea     r8, aAvcoreAudiocor_18; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18002fd1d  mov     edx, 0DCDh; void *
0x18002fd22  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002fd27  jmp     loc_18002FC93
```
