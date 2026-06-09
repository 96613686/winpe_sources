# CallAudioRouting::_StartRecordingWithHresult(uint,CallAudioRouting::StartRecordingAction)

- ea: `0x18006b2c0`
- end: `0x18006ba68`
- name: `?_StartRecordingWithHresult@CallAudioRouting@@AEAAJIW4StartRecordingAction@1@@Z`
- size: `1960`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180069e40`

## callees

- `0x1800056a0`
- `0x180006e94`
- `0x1800091a8`
- `0x180010664`
- `0x1800107d8`
- `0x18005f9b4`
- `0x18005f9c0`
- `0x180064dac`
- `0x180069efc`
- `0x18006a3d4`
- `0x18006aa0c`
- `0x18006ae0c`
- `0x18006b0b8`
- `0x18006b2c0`
- `0x18007f9ec`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006b3bc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006b3bc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b403`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b5c8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b67d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b403`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b5c8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b67d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006b2f9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006b31e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006b2f9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006b31e`

## string_xrefs

- `0x18006b312`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x18006b3ef`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x18006b5b3`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x18006b6ec`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x18006b88a`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x18006b989`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x18006ba54`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`

## pseudocode

```c
__int64 __fastcall CallAudioRouting::_StartRecordingWithHresult(__int64 a1, unsigned int a2, char a3)
{
  __int64 v5; // rcx
  _QWORD *v6; // rdi
  __int64 v7; // rsi
  __int64 v8; // r14
  _QWORD *v9; // r12
  unsigned int v10; // r15d
  struct CallAudioRouting::CellularAudioState *v11; // rbx
  _QWORD *v12; // r15
  __int64 v13; // r15
  __int64 v14; // r15
  _QWORD *v15; // r15
  __int64 v16; // r15
  __int64 v17; // r8
  __int64 v18; // r9
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // rdx
  __int64 v22; // rax
  _QWORD *v23; // rcx
  __int64 v24; // rax
  _QWORD *v25; // rcx
  __int64 v26; // rax
  _QWORD *v27; // rcx
  __int64 v28; // r9
  __int64 v29; // rdx
  int v30; // eax
  BackTraceCollection *v31; // rcx
  __int64 v32; // r9
  int v33; // eax
  BackTraceCollection *v34; // rcx
  int v36; // eax
  BackTraceCollection *v37; // rcx
  int AudioFile; // eax
  BackTraceCollection *v39; // rcx
  int started; // eax
  BackTraceCollection *v41; // rcx
  _QWORD *v44; // [rsp+48h] [rbp-81h] BYREF
  _QWORD *v45; // [rsp+50h] [rbp-79h] BYREF
  __int64 v46; // [rsp+58h] [rbp-71h] BYREF
  _QWORD *v47; // [rsp+60h] [rbp-69h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+68h] [rbp-61h]
  struct CallAudioRouting::CellularAudioState *v49; // [rsp+70h] [rbp-59h] BYREF
  volatile __int32 *v50; // [rsp+78h] [rbp-51h] BYREF
  void *Block[2]; // [rsp+80h] [rbp-49h] BYREF
  __int16 v52; // [rsp+90h] [rbp-39h] BYREF
  __int64 v53; // [rsp+92h] [rbp-37h]
  int v54; // [rsp+9Ah] [rbp-2Fh]
  __int16 v55; // [rsp+9Eh] [rbp-2Bh]
  void *v56[2]; // [rsp+A0h] [rbp-29h] BYREF
  __int16 v57; // [rsp+B0h] [rbp-19h] BYREF
  __int64 v58; // [rsp+B2h] [rbp-17h]
  int v59; // [rsp+BAh] [rbp-Fh]
  __int16 v60; // [rsp+BEh] [rbp-Bh]
  void *v61[2]; // [rsp+C0h] [rbp-9h] BYREF
  __int16 v62; // [rsp+D0h] [rbp+7h] BYREF
  __int64 v63; // [rsp+D2h] [rbp+9h]
  int v64; // [rsp+DAh] [rbp+11h]
  __int16 v65; // [rsp+DEh] [rbp+15h]

  lpCriticalSection = (LPCRITICAL_SECTION)(a1 + 88);
  if ( *(_DWORD *)(a1 + 104) == GetCurrentThreadId() )
  {
    Log_AssertionEvent_9(v5, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 2168);
    if ( *(_DWORD *)(a1 + 104) == GetCurrentThreadId() )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  utl::lock_guard<ThreadCheck>::lock_guard<ThreadCheck>(&v50, a1 + 128);
  v61[0] = &v62;
  v6 = 0;
  v45 = 0;
  v61[1] = &v62;
  v7 = 0;
  v47 = 0;
  v56[0] = &v57;
  v8 = 0;
  v46 = 0;
  v56[1] = &v57;
  v9 = 0;
  v44 = 0;
  Block[0] = &v52;
  v63 = 0;
  v64 = 0;
  v65 = 0;
  v62 = 0;
  v58 = 0;
  v59 = 0;
  v60 = 0;
  v57 = 0;
  v53 = 0;
  v54 = 0;
  v55 = 0;
  v52 = 0;
  Block[1] = &v52;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 88));
  v49 = 0;
  if ( !(unsigned int)CallAudioRouting::_FindCellularState((CallAudioRouting *)a1, a2, &v49) )
  {
    v10 = -2147023728;
    BackTraceCollection::Capture(0, -2147023728);
    Log_HREvent_17(2147943568LL, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 2191);
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 88));
    if ( Block[0] != &v52 )
      operator delete(Block[0]);
    if ( v56[0] != &v57 )
      operator delete(v56[0]);
    if ( v61[0] != &v62 )
      operator delete(v61[0]);
    goto LABEL_85;
  }
  v11 = v49;
  v12 = (_QWORD *)*((_QWORD *)v49 + 5);
  if ( v12 )
  {
    (*(void (__fastcall **)(_QWORD))(*v12 + 8LL))(*((_QWORD *)v49 + 5));
    v45 = v12;
    v6 = v12;
  }
  v13 = *((_QWORD *)v11 + 6);
  if ( v13 )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v13 + 8LL))(*((_QWORD *)v11 + 6));
    v47 = (_QWORD *)v13;
    v7 = v13;
  }
  v14 = *((_QWORD *)v11 + 7);
  if ( v14 )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v14 + 8LL))(*((_QWORD *)v11 + 7));
    v46 = v14;
    v8 = v14;
  }
  v15 = (_QWORD *)*((_QWORD *)v11 + 8);
  if ( v15 )
  {
    (*(void (__fastcall **)(_QWORD))(*v15 + 8LL))(*((_QWORD *)v11 + 8));
    v44 = v15;
    v9 = v15;
  }
  v16 = -1;
  if ( v11 != (struct CallAudioRouting::CellularAudioState *)-144LL )
  {
    v17 = -1;
    do
      ++v17;
    while ( *((_WORD *)v11 + v17 + 72) );
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(v61) )
  {
    v10 = -2147024882;
    BackTraceCollection::Capture(0, -2147024882);
    v18 = 2198;
LABEL_33:
    Log_HREvent_17(2147942414LL, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", v18);
    LeaveCriticalSection(lpCriticalSection);
LABEL_34:
    if ( Block[0] != &v52 )
      operator delete(Block[0]);
    if ( v56[0] != &v57 )
      operator delete(v56[0]);
    if ( v61[0] != &v62 )
      operator delete(v61[0]);
    if ( !v9 )
      goto LABEL_43;
    v22 = *v9;
    v23 = v9;
LABEL_42:
    (*(void (__fastcall **)(_QWORD *))(v22 + 16))(v23);
LABEL_43:
    if ( v8 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    if ( !v7 )
      goto LABEL_48;
    v24 = *(_QWORD *)v7;
    v25 = (_QWORD *)v7;
LABEL_47:
    (*(void (__fastcall **)(_QWORD *))(v24 + 16))(v25);
LABEL_48:
    if ( !v6 )
      goto LABEL_85;
    v26 = *v6;
    v27 = v6;
LABEL_50:
    (*(void (__fastcall **)(_QWORD *))(v26 + 16))(v27);
    goto LABEL_85;
  }
  v19 = **((_QWORD **)v11 + 15);
  if ( v19 )
  {
    v20 = -1;
    do
      ++v20;
    while ( *(_WORD *)(v19 + 2 * v20) );
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(v56) )
  {
    v10 = -2147024882;
    BackTraceCollection::Capture(0, -2147024882);
    v18 = 2199;
    goto LABEL_33;
  }
  v21 = **((_QWORD **)v11 + 12);
  if ( v21 )
  {
    do
      ++v16;
    while ( *(_WORD *)(v21 + 2 * v16) );
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(Block) )
  {
    v10 = -2147024882;
    BackTraceCollection::Capture(0, -2147024882);
    v18 = 2200;
    goto LABEL_33;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 88));
  if ( !a3 )
  {
    started = CallAudioRouting::_StartRecordingInitialize((CallAudioRouting *)a1, a2);
    v10 = started;
    if ( started < 0 )
    {
      BackTraceCollection::Capture(v41, started);
      v28 = 2208;
      v29 = 1;
      goto LABEL_118;
    }
    goto LABEL_70;
  }
  if ( a3 == 1 )
  {
    AudioFile = CallAudioRouting::_StartRecordingCreateAudioFile(
                  (CallAudioRouting *)a1,
                  a2,
                  (unsigned __int16 **)v61,
                  (__int64 *)&v47);
    v10 = AudioFile;
    if ( AudioFile < 0 )
    {
      BackTraceCollection::Capture(v39, AudioFile);
      Log_HREvent_17(v10, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 2212);
      if ( Block[0] != &v52 )
        operator delete(Block[0]);
      if ( v56[0] != &v57 )
        operator delete(v56[0]);
      if ( v61[0] != &v62 )
        operator delete(v61[0]);
      if ( v9 )
        (*(void (__fastcall **)(_QWORD *))(*v9 + 16LL))(v9);
      if ( v8 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
      v25 = v47;
      if ( !v47 )
        goto LABEL_48;
      v24 = *v47;
      goto LABEL_47;
    }
    v7 = (__int64)v47;
    goto LABEL_70;
  }
  if ( a3 != 2 )
  {
    if ( a3 == 3 )
    {
      v33 = CallAudioRouting::_StartRecordingStart(a1, a2, &v44);
      v10 = v33;
      if ( v33 < 0 )
      {
        BackTraceCollection::Capture(v34, v33);
        v32 = 2220;
        goto LABEL_59;
      }
    }
    else
    {
      if ( a3 != 4 )
      {
        v28 = 2228;
        v29 = 0;
        v10 = -2147024809;
LABEL_118:
        Log_HREvent_17(v10, v29, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", v28);
        goto LABEL_34;
      }
      v30 = CallAudioRouting::_StartRecordingResume(a1, a2, &v44);
      v10 = v30;
      if ( v30 < 0 )
      {
        BackTraceCollection::Capture(v31, v30);
        v32 = 2224;
LABEL_59:
        Log_HREvent_17(v10, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", v32);
        if ( Block[0] != &v52 )
          operator delete(Block[0]);
        if ( v56[0] != &v57 )
          operator delete(v56[0]);
        if ( v61[0] != &v62 )
          operator delete(v61[0]);
        v23 = v44;
        if ( !v44 )
          goto LABEL_43;
        v22 = *v44;
        goto LABEL_42;
      }
    }
    v9 = v44;
    goto LABEL_70;
  }
  v36 = CallAudioRouting::_StartRecordingPrepare(a1, a2, &v45, &v46);
  v10 = v36;
  if ( v36 >= 0 )
  {
    v6 = v45;
    v8 = v46;
LABEL_70:
    if ( Block[0] != &v52 )
      operator delete(Block[0]);
    if ( v56[0] != &v57 )
      operator delete(v56[0]);
    if ( v61[0] != &v62 )
      operator delete(v61[0]);
    if ( v9 )
      (*(void (__fastcall **)(_QWORD *))(*v9 + 16LL))(v9);
    if ( v8 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    if ( v7 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    if ( v6 )
      (*(void (__fastcall **)(_QWORD *))(*v6 + 16LL))(v6);
    v10 = 0;
    goto LABEL_85;
  }
  BackTraceCollection::Capture(v37, v36);
  Log_HREvent_17(v10, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 2216);
  if ( Block[0] != &v52 )
    operator delete(Block[0]);
  if ( v56[0] != &v57 )
    operator delete(v56[0]);
  if ( v61[0] != &v62 )
    operator delete(v61[0]);
  if ( v9 )
    (*(void (__fastcall **)(_QWORD *))(*v9 + 16LL))(v9);
  if ( v46 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  v27 = v45;
  if ( v45 )
  {
    v26 = *v45;
    goto LABEL_50;
  }
LABEL_85:
  utl::lock_guard<ThreadCheck>::~lock_guard<ThreadCheck>(&v50);
  return v10;
}

```

## disassembly

```asm
0x18006b2c0  mov     [rsp-8+arg_10], rbx
0x18006b2c5  push    rbp
0x18006b2c6  push    rsi
0x18006b2c7  push    rdi
0x18006b2c8  push    r12
0x18006b2ca  push    r13
0x18006b2cc  push    r14
0x18006b2ce  push    r15
0x18006b2d0  lea     rbp, [rsp-27h]
0x18006b2d5  sub     rsp, 0F0h
0x18006b2dc  mov     rax, cs:__security_cookie
0x18006b2e3  xor     rax, rsp
0x18006b2e6  mov     [rbp+57h+var_40], rax
0x18006b2ea  mov     [rsp+120h+var_E0], r8b
0x18006b2ef  mov     r15d, edx
0x18006b2f2  mov     [rsp+120h+var_DC], edx
0x18006b2f6  mov     r13, rcx
0x18006b2f9  call    cs:__imp_GetCurrentThreadId
0x18006b2ff  lea     rbx, [r13+58h]
0x18006b303  mov     [rbp+57h+lpCriticalSection], rbx
0x18006b307  cmp     [rbx+10h], eax
0x18006b30a  jnz     short loc_18006B32F
0x18006b30c  mov     r8d, 878h
0x18006b312  lea     rdx, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18006b319  call    Log_AssertionEvent_9
0x18006b31e  call    cs:__imp_GetCurrentThreadId
0x18006b324  cmp     [r13+68h], eax
0x18006b328  jnz     short loc_18006B32F
0x18006b32a  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18006b32f  lea     rdx, [r13+80h]
0x18006b336  lea     rcx, [rbp+57h+var_A8]
0x18006b33a  call    ??0?$lock_guard@VThreadCheck@@@utl@@QEAA@AEAVThreadCheck@@@Z; utl::lock_guard<ThreadCheck>::lock_guard<ThreadCheck>(ThreadCheck &)
0x18006b33f  xor     ecx, ecx
0x18006b341  lea     rax, [rbp+57h+var_50]
0x18006b345  mov     [rbp+57h+var_60], rax
0x18006b349  mov     edi, ecx
0x18006b34b  lea     rax, [rbp+57h+var_50]
0x18006b34f  mov     [rbp+57h+var_D0], rcx
0x18006b353  mov     [rbp+57h+var_58], rax
0x18006b357  mov     esi, ecx
0x18006b359  lea     rax, [rbp+57h+var_70]
0x18006b35d  mov     [rbp+57h+var_C0], rcx
0x18006b361  mov     [rbp+57h+var_80], rax
0x18006b365  mov     r14d, ecx
0x18006b368  lea     rax, [rbp+57h+var_70]
0x18006b36c  mov     [rbp+57h+var_C8], rcx
0x18006b370  mov     [rbp+57h+var_78], rax
0x18006b374  mov     r12d, ecx
0x18006b377  lea     rax, [rbp+57h+var_90]
0x18006b37b  mov     [rsp+120h+var_D8], rcx
0x18006b380  mov     [rbp+57h+Block], rax
0x18006b384  lea     rax, [rbp+57h+var_90]
0x18006b388  mov     [rbp+57h+var_4E], rcx
0x18006b38c  mov     [rbp+57h+var_46], ecx
0x18006b38f  mov     [rbp+57h+var_42], cx
0x18006b393  mov     [rbp+57h+var_50], cx
0x18006b397  mov     [rbp+57h+var_6E], rcx
0x18006b39b  mov     [rbp+57h+var_66], ecx
0x18006b39e  mov     [rbp+57h+var_62], cx
0x18006b3a2  mov     [rbp+57h+var_70], cx
0x18006b3a6  mov     [rbp+57h+var_8E], rcx
0x18006b3aa  mov     [rbp+57h+var_86], ecx
0x18006b3ad  mov     [rbp+57h+var_82], cx
0x18006b3b1  mov     [rbp+57h+var_90], cx
0x18006b3b5  mov     rcx, rbx; lpCriticalSection
0x18006b3b8  mov     [rbp+57h+var_98], rax
0x18006b3bc  call    cs:__imp_EnterCriticalSection
0x18006b3c2  lea     r8, [rbp+57h+var_B0]; struct CallAudioRouting::CellularAudioState **
0x18006b3c6  mov     [rbp+57h+var_B0], r12
0x18006b3ca  mov     edx, r15d; unsigned int
0x18006b3cd  mov     rcx, r13; this
0x18006b3d0  call    ?_FindCellularState@CallAudioRouting@@AEAAHIPEAPEAUCellularAudioState@1@@Z; CallAudioRouting::_FindCellularState(uint,CallAudioRouting::CellularAudioState * *)
0x18006b3d5  xor     ecx, ecx; this
0x18006b3d7  test    eax, eax
0x18006b3d9  jnz     short loc_18006B458
0x18006b3db  mov     r15d, 80070490h
0x18006b3e1  mov     edx, r15d; int
0x18006b3e4  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18006b3e9  mov     r9d, 88Fh
0x18006b3ef  lea     r8, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18006b3f6  xor     edx, edx
0x18006b3f8  mov     ecx, r15d
0x18006b3fb  call    Log_HREvent_17
0x18006b400  mov     rcx, rbx; lpCriticalSection
0x18006b403  call    cs:__imp_LeaveCriticalSection
0x18006b409  mov     rcx, [rbp+57h+Block]; Block
0x18006b40d  lea     rax, [rbp+57h+var_90]
0x18006b411  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18006b418  cmp     rcx, rax
0x18006b41b  jz      short loc_18006B425
0x18006b41d  mov     rdx, rbx
0x18006b420  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006b425  mov     rcx, [rbp+57h+var_80]; Block
0x18006b429  lea     rax, [rbp+57h+var_70]
0x18006b42d  cmp     rcx, rax
0x18006b430  jz      short loc_18006B43A
0x18006b432  mov     rdx, rbx
0x18006b435  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006b43a  mov     rcx, [rbp+57h+var_60]; Block
0x18006b43e  lea     rax, [rbp+57h+var_50]
0x18006b442  cmp     rcx, rax
0x18006b445  jz      loc_18006B828
0x18006b44b  mov     rdx, rbx
0x18006b44e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006b453  jmp     loc_18006B828
0x18006b458  mov     rbx, [rbp+57h+var_B0]
0x18006b45c  mov     r15, [rbx+28h]
0x18006b460  test    r15, r15
0x18006b463  jz      short loc_18006B47D
0x18006b465  mov     rax, [r15]
0x18006b468  mov     rcx, r15
0x18006b46b  mov     rax, [rax+8]
0x18006b46f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b474  xor     ecx, ecx
0x18006b476  mov     [rbp+57h+var_D0], r15
0x18006b47a  mov     rdi, r15
0x18006b47d  mov     r15, [rbx+30h]
0x18006b481  test    r15, r15
0x18006b484  jz      short loc_18006B49E
0x18006b486  mov     rax, [r15]
0x18006b489  mov     rcx, r15
0x18006b48c  mov     rax, [rax+8]
0x18006b490  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b495  xor     ecx, ecx
0x18006b497  mov     [rbp+57h+var_C0], r15
0x18006b49b  mov     rsi, r15
0x18006b49e  mov     r15, [rbx+38h]
0x18006b4a2  test    r15, r15
0x18006b4a5  jz      short loc_18006B4BF
0x18006b4a7  mov     rax, [r15]
0x18006b4aa  mov     rcx, r15
0x18006b4ad  mov     rax, [rax+8]
0x18006b4b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b4b6  xor     ecx, ecx
0x18006b4b8  mov     [rbp+57h+var_C8], r15
0x18006b4bc  mov     r14, r15
0x18006b4bf  mov     r15, [rbx+40h]
0x18006b4c3  test    r15, r15
0x18006b4c6  jz      short loc_18006B4E1
0x18006b4c8  mov     rax, [r15]
0x18006b4cb  mov     rcx, r15
0x18006b4ce  mov     rax, [rax+8]
0x18006b4d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b4d7  xor     ecx, ecx
0x18006b4d9  mov     [rsp+120h+var_D8], r15
0x18006b4de  mov     r12, r15
0x18006b4e1  lea     rdx, [rbx+90h]
0x18006b4e8  or      r15, 0FFFFFFFFFFFFFFFFh
0x18006b4ec  test    rdx, rdx
0x18006b4ef  jz      short loc_18006B500
0x18006b4f1  mov     r8, r15
0x18006b4f4  inc     r8
0x18006b4f7  cmp     [rdx+r8*2], cx
0x18006b4fc  jnz     short loc_18006B4F4
0x18006b4fe  jmp     short loc_18006B503
0x18006b500  mov     r8, rcx
0x18006b503  lea     rcx, [rbp+57h+var_60]
0x18006b507  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18006b50c  xor     ecx, ecx; this
0x18006b50e  test    al, al
0x18006b510  jnz     short loc_18006B52B
0x18006b512  mov     r15d, 8007000Eh
0x18006b518  mov     edx, r15d; int
0x18006b51b  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18006b520  mov     r9d, 896h
0x18006b526  jmp     loc_18006B5B3
0x18006b52b  mov     rax, [rbx+78h]
0x18006b52f  mov     rdx, [rax]
0x18006b532  test    rdx, rdx
0x18006b535  jz      short loc_18006B546
0x18006b537  mov     r8, r15
0x18006b53a  inc     r8
0x18006b53d  cmp     [rdx+r8*2], cx
0x18006b542  jnz     short loc_18006B53A
0x18006b544  jmp     short loc_18006B549
0x18006b546  mov     r8, rcx
0x18006b549  lea     rcx, [rbp+57h+var_80]
0x18006b54d  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18006b552  xor     ecx, ecx; this
0x18006b554  test    al, al
0x18006b556  jnz     short loc_18006B56E
0x18006b558  mov     r15d, 8007000Eh
0x18006b55e  mov     edx, r15d; int
0x18006b561  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18006b566  mov     r9d, 897h
0x18006b56c  jmp     short loc_18006B5B3
0x18006b56e  mov     rax, [rbx+60h]
0x18006b572  mov     rdx, [rax]
0x18006b575  test    rdx, rdx
0x18006b578  jz      short loc_18006B586
0x18006b57a  inc     r15
0x18006b57d  cmp     [rdx+r15*2], cx
0x18006b582  jnz     short loc_18006B57A
0x18006b584  jmp     short loc_18006B589
0x18006b586  mov     r15, rcx
0x18006b589  mov     r8, r15
0x18006b58c  lea     rcx, [rbp+57h+Block]
0x18006b590  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18006b595  xor     ecx, ecx; this
0x18006b597  test    al, al
0x18006b599  jnz     loc_18006B66E
0x18006b59f  mov     r15d, 8007000Eh
0x18006b5a5  mov     edx, r15d; int
0x18006b5a8  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18006b5ad  mov     r9d, 898h
0x18006b5b3  lea     r8, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18006b5ba  xor     edx, edx
0x18006b5bc  mov     ecx, r15d
0x18006b5bf  call    Log_HREvent_17
0x18006b5c4  mov     rcx, [rbp+57h+lpCriticalSection]; lpCriticalSection
0x18006b5c8  call    cs:__imp_LeaveCriticalSection
0x18006b5ce  mov     rcx, [rbp+57h+Block]; Block
0x18006b5d2  lea     rax, [rbp+57h+var_90]
0x18006b5d6  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18006b5dd  cmp     rcx, rax
0x18006b5e0  jz      short loc_18006B5EA
0x18006b5e2  mov     rdx, rbx
0x18006b5e5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006b5ea  mov     rcx, [rbp+57h+var_80]; Block
0x18006b5ee  lea     rax, [rbp+57h+var_70]
0x18006b5f2  cmp     rcx, rax
0x18006b5f5  jz      short loc_18006B5FF
0x18006b5f7  mov     rdx, rbx
0x18006b5fa  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006b5ff  mov     rcx, [rbp+57h+var_60]; Block
0x18006b603  lea     rax, [rbp+57h+var_50]
0x18006b607  cmp     rcx, rax
0x18006b60a  jz      short loc_18006B614
0x18006b60c  mov     rdx, rbx
0x18006b60f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006b614  test    r12, r12
0x18006b617  jz      short loc_18006B629
0x18006b619  mov     rax, [r12]
0x18006b61d  mov     rcx, r12
0x18006b620  mov     rax, [rax+10h]
0x18006b624  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b629  test    r14, r14
0x18006b62c  jz      short loc_18006B63D
0x18006b62e  mov     rax, [r14]
0x18006b631  mov     rcx, r14
0x18006b634  mov     rax, [rax+10h]
0x18006b638  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b63d  test    rsi, rsi
0x18006b640  jz      short loc_18006B651
0x18006b642  mov     rax, [rsi]
0x18006b645  mov     rcx, rsi
0x18006b648  mov     rax, [rax+10h]
0x18006b64c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b651  test    rdi, rdi
0x18006b654  jz      loc_18006B828
0x18006b65a  mov     rax, [rdi]
0x18006b65d  mov     rcx, rdi
0x18006b660  mov     rax, [rax+10h]
0x18006b664  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b669  jmp     loc_18006B828
0x18006b66e  cmp     dword ptr [rbx+5Ch], 1
0x18006b672  mov     r15d, ecx
0x18006b675  lea     rcx, [r13+58h]; lpCriticalSection
0x18006b679  setnbe  r15b
0x18006b67d  call    cs:__imp_LeaveCriticalSection
0x18006b683  movsx   ecx, [rsp+120h+var_E0]
0x18006b688  test    ecx, ecx
0x18006b68a  jz      loc_18006BA29
0x18006b690  sub     ecx, 1
0x18006b693  jz      loc_18006B943
0x18006b699  sub     ecx, 1
0x18006b69c  jz      loc_18006B85B
0x18006b6a2  sub     ecx, 1
0x18006b6a5  jz      loc_18006B75C
0x18006b6ab  cmp     ecx, 1
0x18006b6ae  jz      short loc_18006B6C3
0x18006b6b0  mov     r9d, 8B4h
0x18006b6b6  xor     edx, edx
0x18006b6b8  mov     r15d, 80070057h
0x18006b6be  jmp     loc_18006BA54
0x18006b6c3  mov     edx, [rsp+120h+var_DC]
0x18006b6c7  lea     r8, [rsp+120h+var_D8]
0x18006b6cc  mov     rcx, r13
0x18006b6cf  call    ?_StartRecordingResume@CallAudioRouting@@AEAAJIAEBV?$ComPtr@UILowLagMediaRecording@Capture@Media@Windows@@@WRL@Microsoft@@@Z; CallAudioRouting::_StartRecordingResume(uint,Microsoft::WRL::ComPtr<Windows::Media::Capture::ILowLagMediaRecording> const &)
0x18006b6d4  mov     r15d, eax
0x18006b6d7  test    eax, eax
0x18006b6d9  jns     loc_18006B786
0x18006b6df  mov     edx, eax; int
0x18006b6e1  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18006b6e6  mov     r9d, 8B0h
0x18006b6ec  lea     r8, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18006b6f3  mov     edx, 1
0x18006b6f8  mov     ecx, r15d
0x18006b6fb  call    Log_HREvent_17
0x18006b700  mov     rcx, [rbp+57h+Block]; Block
0x18006b704  lea     rax, [rbp+57h+var_90]
0x18006b708  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18006b70f  cmp     rcx, rax
0x18006b712  jz      short loc_18006B71C
0x18006b714  mov     rdx, rbx
0x18006b717  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006b71c  mov     rcx, [rbp+57h+var_80]; Block
0x18006b720  lea     rax, [rbp+57h+var_70]
0x18006b724  cmp     rcx, rax
0x18006b727  jz      short loc_18006B731
  ... truncated ...
```
