# CAudioSession::StartInactiveTimer(void)

- ea: `0x18002fb4c`
- end: `0x18002fe8c`
- name: `?StartInactiveTimer@CAudioSession@@QEAAXXZ`
- size: `832`
- prototype: `void __fastcall(CAudioSession *__hidden this)`
- caller_count: `3`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x18000ffb0`
- `0x180032b50`
- `0x180034ed0`

## callees

- `0x18002a1ac`
- `0x18002fb4c`
- `0x18002fe94`
- `0x180030bc4`
- `0x1800cbfcc`
- `0x1800cddac`
- `0x18016c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002fb72`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002fb72`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002fdfb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002fdfb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002fc8a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002fc8a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002fc99`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002fc99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fbea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fd7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fe41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fe58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fbea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fd7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fe41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fe58`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18002fbc9`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18002fbc9`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18002fc07`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18002fc07`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x18002fbe0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x18002fbe0`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18002fd64`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18002fd64`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x18002fc22`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x18002fc22`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002fdb7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002fdb7`

## string_xrefs

- `0x18002fe76`: `avcore\audiocore\server\audiosrv\dll\audiosession.cpp`

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
  v24[0] = off_18016FF18;
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
0x18002fb4c  push    rbp
0x18002fb4e  push    rbx
0x18002fb4f  push    rsi
0x18002fb50  push    rdi
0x18002fb51  push    r12
0x18002fb53  push    r13
0x18002fb55  push    r14
0x18002fb57  push    r15
0x18002fb59  lea     rbp, [rsp-1Fh]
0x18002fb5e  sub     rsp, 0A8h
0x18002fb65  mov     r13, rcx
0x18002fb68  lea     r15, [rcx+1F0h]
0x18002fb6f  mov     rcx, r15; lpCriticalSection
0x18002fb72  call    cs:__imp_EnterCriticalSection
0x18002fb78  mov     rcx, cs:?g_AudioService@@3PEAVIAudioService@@EA; IAudioService * g_AudioService
0x18002fb7f  mov     rax, [rcx]
0x18002fb82  mov     rax, [rax+78h]
0x18002fb86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fb8b  mov     rsi, rax
0x18002fb8e  lea     rax, off_18016FF18
0x18002fb95  mov     [rbp+57h+var_C0], rax
0x18002fb99  mov     [rbp+57h+var_B8], r13
0x18002fb9d  lea     rax, [rbp+57h+var_C0]
0x18002fba1  mov     [rbp+57h+var_88], rax
0x18002fba5  mov     r12d, [r13+0F0h]
0x18002fbac  xor     r14d, r14d
0x18002fbaf  mov     edi, r14d
0x18002fbb2  mov     cl, [rsi+50h]
0x18002fbb5  nop
0x18002fbb6  test    cl, cl
0x18002fbb8  jnz     loc_18002FDCC
0x18002fbbe  lea     ebx, [r14+1]
0x18002fbc2  cmp     [rsi], r14
0x18002fbc5  jnz     short loc_18002FC3E
0x18002fbc7  xor     ecx, ecx; reserved
0x18002fbc9  call    cs:__imp_CreateThreadpool
0x18002fbcf  mov     [rsi], rax
0x18002fbd2  test    rax, rax
0x18002fbd5  jz      loc_18002FE41
0x18002fbdb  mov     edx, ebx; cthrdMic
0x18002fbdd  mov     rcx, [rsi]; ptpp
0x18002fbe0  call    cs:__imp_SetThreadpoolThreadMinimum
0x18002fbe6  test    eax, eax
0x18002fbe8  jnz     short loc_18002FC07
0x18002fbea  call    cs:__imp_GetLastError
0x18002fbf0  mov     edi, eax
0x18002fbf2  test    eax, eax
0x18002fbf4  jle     short loc_18002FBFF
0x18002fbf6  movzx   edi, ax
0x18002fbf9  or      edi, 80070000h
0x18002fbff  test    edi, edi
0x18002fc01  js      loc_18002FDCC
0x18002fc07  call    cs:__imp_CreateThreadpoolCleanupGroup
0x18002fc0d  mov     [rsi+0A8h], rax
0x18002fc14  test    rax, rax
0x18002fc17  jz      loc_18002FE58
0x18002fc1d  mov     edx, ebx; cthrdMost
0x18002fc1f  mov     rcx, [rsi]; ptpp
0x18002fc22  call    cs:__imp_SetThreadpoolThreadMaximum
0x18002fc28  mov     rax, [rsi]
0x18002fc2b  mov     [rsi+10h], rax
0x18002fc2f  mov     rax, [rsi+0A8h]
0x18002fc36  mov     [rsi+18h], rax
0x18002fc3a  mov     [rsi+20h], r14
0x18002fc3e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002fc45  mov     ecx, 20h ; ' '; unsigned __int64
0x18002fc4a  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18002fc4f  mov     rbx, rax
0x18002fc52  test    rax, rax
0x18002fc55  jz      loc_18002FE20
0x18002fc5b  mov     [rax], r14
0x18002fc5e  mov     [rax+8], r14
0x18002fc62  mov     [rax+10h], r14
0x18002fc66  mov     [rbp+57h+var_48], r14
0x18002fc6a  mov     rcx, [rbp+57h+var_88]
0x18002fc6e  test    rcx, rcx
0x18002fc71  jz      short loc_18002FC86
0x18002fc73  mov     rax, [rcx]
0x18002fc76  lea     rdx, [rbp+57h+var_80]
0x18002fc7a  mov     rax, [rax]
0x18002fc7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fc82  mov     [rbp+57h+var_48], rax
0x18002fc86  mov     [rbx+18h], rsi
0x18002fc8a  call    cs:__imp_GetProcessHeap
0x18002fc90  mov     rcx, rax; hHeap
0x18002fc93  xor     edx, edx; dwFlags
0x18002fc95  lea     r8d, [rdx+50h]; dwBytes
0x18002fc99  call    cs:__imp_HeapAlloc
0x18002fc9f  mov     rdi, rax
0x18002fca2  test    rax, rax
0x18002fca5  jz      loc_18002FE27
0x18002fcab  mov     eax, 1
0x18002fcb0  mov     [rdi+8], eax
0x18002fcb3  mov     [rdi+0Ch], eax
0x18002fcb6  lea     rax, ??_7?$_Ref_count_obj2@V?$function@$$A6AJPEAVSystemEffectDescriptor@@PEAVSystemEffectChainDescriptor@@@Z@std@@@std@@6B@; const std::_Ref_count_obj2<std::function<long (SystemEffectDescriptor *,SystemEffectChainDescriptor *)>>::`vftable'
0x18002fcbd  mov     [rdi], rax
0x18002fcc0  lea     rcx, [rdi+10h]
0x18002fcc4  lea     rdx, [rbp+57h+var_80]
0x18002fcc8  call    ??0?$function@$$A6AXPEAUIAudioStreamInfo@@@Z@std@@QEAA@AEBV01@@Z; std::function<void (IAudioStreamInfo *)>::function<void (IAudioStreamInfo *)>(std::function<void (IAudioStreamInfo *)> const &)
0x18002fccd  lea     rax, [rdi+10h]
0x18002fcd1  mov     [rbx+8], rax
0x18002fcd5  mov     r14, [rbx+10h]
0x18002fcd9  mov     [rbx+10h], rdi
0x18002fcdd  test    r14, r14
0x18002fce0  jz      short loc_18002FD1A
0x18002fce2  or      edi, 0FFFFFFFFh
0x18002fce5  mov     eax, edi
0x18002fce7  lock xadd [r14+8], eax
0x18002fced  add     eax, edi
0x18002fcef  jnz     short loc_18002FD1A
0x18002fcf1  mov     rax, [r14]
0x18002fcf4  mov     rcx, r14
0x18002fcf7  mov     rax, [rax]
0x18002fcfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fcff  mov     eax, edi
0x18002fd01  lock xadd [r14+0Ch], eax
0x18002fd07  add     eax, edi
0x18002fd09  jnz     short loc_18002FD1A
0x18002fd0b  mov     rax, [r14]
0x18002fd0e  mov     rcx, r14
0x18002fd11  mov     rax, [rax+8]
0x18002fd15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fd1a  mov     r14, [rbx+8]
0x18002fd1e  mov     rax, r14
0x18002fd21  neg     rax
0x18002fd24  sbb     edi, edi
0x18002fd26  not     edi
0x18002fd28  and     edi, 8007000Eh
0x18002fd2e  mov     rcx, [rbp+57h+var_48]
0x18002fd32  test    rcx, rcx
0x18002fd35  jz      short loc_18002FD4D
0x18002fd37  mov     rax, [rcx]
0x18002fd3a  lea     rdx, [rbp+57h+var_80]
0x18002fd3e  cmp     rcx, rdx
0x18002fd41  setnz   dl
0x18002fd44  mov     rax, [rax+20h]
0x18002fd48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fd4d  test    r14, r14
0x18002fd50  jz      loc_18002FE16
0x18002fd56  lea     r8, [rsi+8]; pcbe
0x18002fd5a  mov     rdx, rbx; pv
0x18002fd5d  lea     rcx, ?TimerCallback@CSerialWorkQueue@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18002fd64  call    cs:__imp_CreateThreadpoolTimer
0x18002fd6a  mov     rsi, rax
0x18002fd6d  xor     r14d, r14d
0x18002fd70  test    rax, rax
0x18002fd73  jz      short loc_18002FD7D
0x18002fd75  mov     edi, r14d
0x18002fd78  mov     [rbx], rax
0x18002fd7b  jmp     short loc_18002FD99
0x18002fd7d  call    cs:__imp_GetLastError
0x18002fd83  mov     edi, eax
0x18002fd85  test    eax, eax
0x18002fd87  jle     short loc_18002FD92
0x18002fd89  movzx   edi, ax
0x18002fd8c  or      edi, 80070000h
0x18002fd92  mov     [rbx], rsi
0x18002fd95  test    edi, edi
0x18002fd97  js      short loc_18002FE16
0x18002fd99  imul    rax, r12, 0FFFFFFFFFFFFD8F0h
0x18002fda0  mov     [rbp+57h+pftDueTime.dwLowDateTime], eax
0x18002fda3  shr     rax, 20h
0x18002fda7  mov     [rbp+57h+pftDueTime.dwHighDateTime], eax
0x18002fdaa  xor     r9d, r9d; msWindowLength
0x18002fdad  xor     r8d, r8d; msPeriod
0x18002fdb0  lea     rdx, [rbp+57h+pftDueTime]; pftDueTime
0x18002fdb4  mov     rcx, rsi; pti
0x18002fdb7  call    cs:__imp_SetThreadpoolTimer
0x18002fdbd  lea     rcx, [r13+218h]
0x18002fdc4  mov     rdx, rbx
0x18002fdc7  call    ?reset@?$unique_ptr@U_RecurringTask@@U?$default_delete@U_RecurringTask@@@std@@@std@@QEAAXPEAU_RecurringTask@@@Z; std::unique_ptr<_RecurringTask>::reset(_RecurringTask *)
0x18002fdcc  mov     rcx, [rbp+57h+var_88]
0x18002fdd0  test    rcx, rcx
0x18002fdd3  jz      short loc_18002FDEF
0x18002fdd5  mov     rax, [rcx]
0x18002fdd8  lea     rdx, [rbp+57h+var_C0]
0x18002fddc  cmp     rcx, rdx
0x18002fddf  setnz   dl
0x18002fde2  mov     rax, [rax+20h]
0x18002fde6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fdeb  mov     [rbp+57h+var_88], r14
0x18002fdef  test    edi, edi
0x18002fdf1  js      short loc_18002FE6F
0x18002fdf3  test    r15, r15
0x18002fdf6  jz      short loc_18002FE02
0x18002fdf8  mov     rcx, r15; lpCriticalSection
0x18002fdfb  call    cs:__imp_LeaveCriticalSection
0x18002fe01  nop
0x18002fe02  add     rsp, 0A8h
0x18002fe09  pop     r15
0x18002fe0b  pop     r14
0x18002fe0d  pop     r13
0x18002fe0f  pop     r12
0x18002fe11  pop     rdi
0x18002fe12  pop     rsi
0x18002fe13  pop     rbx
0x18002fe14  pop     rbp
0x18002fe15  retn
0x18002fe16  mov     rdx, rbx
0x18002fe19  call    ??R?$default_delete@U_RecurringTask@@@std@@QEBAXPEAU_RecurringTask@@@Z; std::default_delete<_RecurringTask>::operator()(_RecurringTask *)
0x18002fe1e  jmp     short loc_18002FDCC
0x18002fe20  mov     edi, 8007000Eh
0x18002fe25  jmp     short loc_18002FDCC
0x18002fe27  mov     rdi, r14
0x18002fe2a  jmp     loc_18002FCCD
0x18002fe2f  test    edi, edi
0x18002fe31  js      short loc_18002FDCC
0x18002fe33  jmp     loc_18002FBDB
0x18002fe38  test    edi, edi
0x18002fe3a  js      short loc_18002FDCC
0x18002fe3c  jmp     loc_18002FC1D
0x18002fe41  call    cs:__imp_GetLastError
0x18002fe47  mov     edi, eax
0x18002fe49  test    eax, eax
0x18002fe4b  jle     short loc_18002FE2F
0x18002fe4d  movzx   edi, ax
0x18002fe50  or      edi, 80070000h
0x18002fe56  jmp     short loc_18002FE2F
0x18002fe58  call    cs:__imp_GetLastError
0x18002fe5e  mov     edi, eax
0x18002fe60  test    eax, eax
0x18002fe62  jle     short loc_18002FE38
0x18002fe64  movzx   edi, ax
0x18002fe67  or      edi, 80070000h
0x18002fe6d  jmp     short loc_18002FE38
0x18002fe6f  mov     rcx, [rbp+5Fh]; this
0x18002fe73  mov     r9d, edi; char *
0x18002fe76  lea     r8, aAvcoreAudiocor_18; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18002fe7d  mov     edx, 0DCDh; void *
0x18002fe82  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002fe87  jmp     loc_18002FDF3
```
