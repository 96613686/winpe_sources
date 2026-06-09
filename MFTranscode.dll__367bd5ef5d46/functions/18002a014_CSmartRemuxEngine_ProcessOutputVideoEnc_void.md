# CSmartRemuxEngine::_ProcessOutputVideoEnc(void)

- ea: `0x18002a014`
- end: `0x18002a50f`
- name: `?_ProcessOutputVideoEnc@CSmartRemuxEngine@@IEAAJXZ`
- size: `1275`
- prototype: `__int64 __fastcall(CSmartRemuxEngine *__hidden this)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800275d8`
- `0x180029548`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x18000a3f4`
- `0x18001a330`
- `0x18001c280`
- `0x18002a014`
- `0x18002ad4c`
- `0x18004f410`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002a172`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002a1fd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002a288`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002a31a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002a3a5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002a430`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002a172`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002a1fd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002a288`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002a31a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002a3a5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002a430`
- `MFPlat!MFCreateAlignedMemoryBuffer` at `0x18002a082`
- `MFPlat!MFCreateAlignedMemoryBuffer` at `0x18002a082`
- `MFPlat!MFCreateSample` at `0x18002a066`
- `MFPlat!MFCreateSample` at `0x18002a066`

## pseudocode

```c
__int64 __fastcall CSmartRemuxEngine::_ProcessOutputVideoEnc(CSmartRemuxEngine *this)
{
  __int64 v2; // rdx
  HRESULT v3; // ebx
  __int64 v4; // rdx
  __int64 v5; // rdx
  __int64 v6; // rcx
  int v7; // eax
  __int64 v8; // rdx
  __int64 v9; // rdx
  __int64 v10; // rdx
  __int64 *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *v13; // rax
  __int64 v14; // rdx
  __int64 *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  __int64 *v18; // rcx
  CallStackTracing *v19; // rax
  struct CallStackContext *v20; // rax
  __int64 *v21; // rcx
  CallStackTracing *v22; // rax
  struct CallStackContext *v23; // rax
  __int64 *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *v26; // rax
  __int64 *v27; // rcx
  CallStackTracing *v28; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  struct IMFSample *v31[2]; // [rsp+30h] [rbp-20h] BYREF
  __int128 v32; // [rsp+40h] [rbp-10h]
  IMFSample *ppIMFSample; // [rsp+70h] [rbp+20h] BYREF
  int v34; // [rsp+78h] [rbp+28h] BYREF
  IMFMediaBuffer *ppBuffer; // [rsp+80h] [rbp+30h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&ppIMFSample,
    "CSmartRemuxEngine::_ProcessOutputVideoEnc",
    2277);
  v34 = 0;
  *(_OWORD *)v31 = 0;
  v32 = 0;
  while ( 1 )
  {
    ppIMFSample = 0;
    ppBuffer = 0;
    v3 = MFCreateSample(&ppIMFSample);
    if ( v3 < 0 )
    {
      v27 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v2);
        CallStackTracing::s_wpInstance = v28;
        if ( v28 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
        {
          v27 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v27 = &qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      if ( *((_BYTE *)v27 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v27);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != v3 )
          CallStackContext::TraceFailure(ThreadRelativeContext, "CSmartRemuxEngine::_ProcessOutputVideoEnc", 2286, v3);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v14 = 294;
        goto LABEL_73;
      }
      goto LABEL_74;
    }
    v3 = MFCreateAlignedMemoryBuffer(*((_DWORD *)this + 21), 0xFu, &ppBuffer);
    if ( v3 < 0 )
    {
      v24 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4);
        CallStackTracing::s_wpInstance = v25;
        if ( v25 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
        {
          v24 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v24 = &qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      if ( *((_BYTE *)v24 + 8) )
      {
        v26 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v24);
        if ( *((_DWORD *)v26 + 499) != v3 )
          CallStackContext::TraceFailure(v26, "CSmartRemuxEngine::_ProcessOutputVideoEnc", 2287, v3);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v14 = 295;
        goto LABEL_73;
      }
      goto LABEL_74;
    }
    v3 = ((__int64 (__fastcall *)(IMFSample *, IMFMediaBuffer *))ppIMFSample->lpVtbl->AddBuffer)(ppIMFSample, ppBuffer);
    if ( v3 < 0 )
    {
      v21 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v5);
        CallStackTracing::s_wpInstance = v22;
        if ( v22 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
        {
          v21 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v21 = &qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      if ( *((_BYTE *)v21 + 8) )
      {
        v23 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v21);
        if ( *((_DWORD *)v23 + 499) != v3 )
          CallStackContext::TraceFailure(v23, "CSmartRemuxEngine::_ProcessOutputVideoEnc", 2288, v3);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v14 = 296;
        goto LABEL_73;
      }
      goto LABEL_74;
    }
    v6 = *((_QWORD *)this + 8);
    v31[1] = ppIMFSample;
    v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, struct IMFSample **, int *))(*(_QWORD *)v6 + 200LL))(
           v6,
           0,
           1,
           v31,
           &v34);
    v3 = v7;
    if ( v7 == -1072861838 )
    {
      v3 = 0;
      goto LABEL_74;
    }
    if ( v7 < 0 )
      break;
    v3 = CSmartRemuxEngine::_SetEncodedSampleDTS(this, v31[1]);
    if ( v3 < 0 )
    {
      v15 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v9);
        CallStackTracing::s_wpInstance = v16;
        if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
        {
          v15 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v15 = &qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      if ( *((_BYTE *)v15 + 8) )
      {
        v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
        if ( *((_DWORD *)v17 + 499) != v3 )
          CallStackContext::TraceFailure(v17, "CSmartRemuxEngine::_ProcessOutputVideoEnc", 2298, v3);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_74;
      v14 = 298;
LABEL_73:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, &WPP_14b006652b8137ad6e40de3d71db1d47_Traceguids, this, v3);
      goto LABEL_74;
    }
    v3 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, struct IMFSample *))(**((_QWORD **)this + 5) + 48LL))(
           *((_QWORD *)this + 5),
           *((unsigned int *)this + 33),
           v31[1]);
    if ( v3 < 0 )
    {
      v11 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10);
        CallStackTracing::s_wpInstance = v12;
        if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
        {
          v11 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v11 = &qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      if ( *((_BYTE *)v11 + 8) )
      {
        v13 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
        if ( *((_DWORD *)v13 + 499) != v3 )
          CallStackContext::TraceFailure(v13, "CSmartRemuxEngine::_ProcessOutputVideoEnc", 2300, v3);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_74;
      v14 = 299;
      goto LABEL_73;
    }
    ++*((_DWORD *)this + 36);
    if ( *((_QWORD *)&v32 + 1) )
    {
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v32 + 1) + 16LL))(*((_QWORD *)&v32 + 1));
      *((_QWORD *)&v32 + 1) = 0;
    }
    ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&ppBuffer);
    ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&ppIMFSample);
  }
  v18 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8);
    CallStackTracing::s_wpInstance = v19;
    if ( v19 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v19 + 8LL))(v19, 2032) )
    {
      v18 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v18 = &qword_180069A90;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
    }
  }
  if ( *((_BYTE *)v18 + 8) )
  {
    v20 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v18);
    if ( *((_DWORD *)v20 + 499) != v3 )
      CallStackContext::TraceFailure(v20, "CSmartRemuxEngine::_ProcessOutputVideoEnc", 2297, v3);
  }
  if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
  {
    v14 = 297;
    goto LABEL_73;
  }
LABEL_74:
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&ppBuffer);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&ppIMFSample);
  if ( *((_QWORD *)&v32 + 1) )
  {
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v32 + 1) + 16LL))(*((_QWORD *)&v32 + 1));
    *((_QWORD *)&v32 + 1) = 0;
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&ppIMFSample);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18002a014  mov     [rsp-18h+arg_18], rbx
0x18002a019  push    rbp
0x18002a01a  push    rdi
0x18002a01b  push    r15
0x18002a01d  mov     rbp, rsp
0x18002a020  sub     rsp, 50h
0x18002a024  mov     rdi, rcx
0x18002a027  lea     r15, aCsmartremuxeng_1; "CSmartRemuxEngine::_ProcessOutputVideoE"...
0x18002a02e  mov     rdx, r15; char *
0x18002a031  lea     rcx, [rbp+ppIMFSample]; this
0x18002a035  mov     r8d, 8E5h; int
0x18002a03b  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18002a040  xorps   xmm0, xmm0
0x18002a043  mov     [rbp+arg_8], 0
0x18002a04a  movups  xmmword ptr [rbp+var_20], xmm0
0x18002a04e  movups  [rbp+var_10], xmm0
0x18002a052  lea     rcx, [rbp+ppIMFSample]; ppIMFSample
0x18002a056  mov     [rbp+ppIMFSample], 0
0x18002a05e  mov     [rbp+ppBuffer], 0
0x18002a066  call    cs:__imp_MFCreateSample
0x18002a06c  mov     ebx, eax
0x18002a06e  test    eax, eax
0x18002a070  js      loc_18002A424
0x18002a076  mov     ecx, [rdi+54h]; cbMaxLength
0x18002a079  lea     r8, [rbp+ppBuffer]; ppBuffer
0x18002a07d  mov     edx, 0Fh; cbAligment
0x18002a082  call    cs:__imp_MFCreateAlignedMemoryBuffer
0x18002a088  mov     ebx, eax
0x18002a08a  test    eax, eax
0x18002a08c  js      loc_18002A399
0x18002a092  mov     rcx, [rbp+ppIMFSample]
0x18002a096  mov     rdx, [rbp+ppBuffer]
0x18002a09a  mov     rax, [rcx]
0x18002a09d  mov     rax, [rax+150h]
0x18002a0a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a0a9  mov     ebx, eax
0x18002a0ab  test    eax, eax
0x18002a0ad  js      loc_18002A30E
0x18002a0b3  mov     rax, [rbp+ppIMFSample]
0x18002a0b7  lea     rdx, [rbp+arg_8]
0x18002a0bb  mov     rcx, [rdi+40h]
0x18002a0bf  lea     r9, [rbp+var_20]
0x18002a0c3  mov     [rbp+var_20+8], rax
0x18002a0c7  mov     [rsp+50h+var_30], rdx
0x18002a0cc  xor     edx, edx
0x18002a0ce  mov     rax, [rcx]
0x18002a0d1  lea     r8d, [rdx+1]
0x18002a0d5  mov     rax, [rax+0C8h]
0x18002a0dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a0e1  mov     ebx, eax
0x18002a0e3  cmp     eax, 0C00D6D72h
0x18002a0e8  jz      loc_18002A307
0x18002a0ee  test    eax, eax
0x18002a0f0  js      loc_18002A27C
0x18002a0f6  mov     rdx, [rbp+var_20+8]; struct IMFSample *
0x18002a0fa  mov     rcx, rdi; this
0x18002a0fd  call    ?_SetEncodedSampleDTS@CSmartRemuxEngine@@IEAAJPEAUIMFSample@@@Z; CSmartRemuxEngine::_SetEncodedSampleDTS(IMFSample *)
0x18002a102  mov     ebx, eax
0x18002a104  test    eax, eax
0x18002a106  js      loc_18002A1F1
0x18002a10c  mov     rcx, [rdi+28h]
0x18002a110  mov     r8, [rbp+var_20+8]
0x18002a114  mov     edx, [rdi+84h]
0x18002a11a  mov     rax, [rcx]
0x18002a11d  mov     rax, [rax+30h]
0x18002a121  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a126  mov     ebx, eax
0x18002a128  test    eax, eax
0x18002a12a  js      short loc_18002A166
0x18002a12c  inc     dword ptr [rdi+90h]
0x18002a132  mov     rcx, qword ptr [rbp+var_10+8]
0x18002a136  test    rcx, rcx
0x18002a139  jz      short loc_18002A14F
0x18002a13b  mov     rax, [rcx]
0x18002a13e  mov     rax, [rax+10h]
0x18002a142  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a147  mov     qword ptr [rbp+var_10+8], 0
0x18002a14f  lea     rcx, [rbp+ppBuffer]
0x18002a153  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x18002a158  lea     rcx, [rbp+ppIMFSample]
0x18002a15c  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x18002a161  jmp     loc_18002A052
0x18002a166  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a16d  test    rcx, rcx
0x18002a170  jnz     short loc_18002A1B3
0x18002a172  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002a178  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a17f  mov     rcx, rax
0x18002a182  test    rax, rax
0x18002a185  jz      short loc_18002A1A5
0x18002a187  mov     rax, [rax]
0x18002a18a  mov     edx, 7F0h
0x18002a18f  mov     rax, [rax+8]
0x18002a193  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a198  test    eax, eax
0x18002a19a  jz      short loc_18002A1A5
0x18002a19c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a1a3  jmp     short loc_18002A1B3
0x18002a1a5  lea     rcx, qword_180069A90; this
0x18002a1ac  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a1b3  cmp     byte ptr [rcx+8], 0
0x18002a1b7  jz      short loc_18002A1DA
0x18002a1b9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002a1be  cmp     [rax+7CCh], ebx
0x18002a1c4  jz      short loc_18002A1DA
0x18002a1c6  mov     r9d, ebx; int
0x18002a1c9  mov     r8d, 8FCh; int
0x18002a1cf  mov     rdx, r15; char *
0x18002a1d2  mov     rcx, rax; this
0x18002a1d5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002a1da  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002a1df  cmp     al, 1
0x18002a1e1  jb      loc_18002A4C4
0x18002a1e7  mov     edx, 12Bh
0x18002a1ec  jmp     loc_18002A4A6
0x18002a1f1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a1f8  test    rcx, rcx
0x18002a1fb  jnz     short loc_18002A23E
0x18002a1fd  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002a203  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a20a  mov     rcx, rax
0x18002a20d  test    rax, rax
0x18002a210  jz      short loc_18002A230
0x18002a212  mov     rax, [rax]
0x18002a215  mov     edx, 7F0h
0x18002a21a  mov     rax, [rax+8]
0x18002a21e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a223  test    eax, eax
0x18002a225  jz      short loc_18002A230
0x18002a227  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a22e  jmp     short loc_18002A23E
0x18002a230  lea     rcx, qword_180069A90; this
0x18002a237  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a23e  cmp     byte ptr [rcx+8], 0
0x18002a242  jz      short loc_18002A265
0x18002a244  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002a249  cmp     [rax+7CCh], ebx
0x18002a24f  jz      short loc_18002A265
0x18002a251  mov     r9d, ebx; int
0x18002a254  mov     r8d, 8FAh; int
0x18002a25a  mov     rdx, r15; char *
0x18002a25d  mov     rcx, rax; this
0x18002a260  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002a265  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002a26a  cmp     al, 1
0x18002a26c  jb      loc_18002A4C4
0x18002a272  mov     edx, 12Ah
0x18002a277  jmp     loc_18002A4A6
0x18002a27c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a283  test    rcx, rcx
0x18002a286  jnz     short loc_18002A2C9
0x18002a288  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002a28e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a295  mov     rcx, rax
0x18002a298  test    rax, rax
0x18002a29b  jz      short loc_18002A2BB
0x18002a29d  mov     rax, [rax]
0x18002a2a0  mov     edx, 7F0h
0x18002a2a5  mov     rax, [rax+8]
0x18002a2a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a2ae  test    eax, eax
0x18002a2b0  jz      short loc_18002A2BB
0x18002a2b2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a2b9  jmp     short loc_18002A2C9
0x18002a2bb  lea     rcx, qword_180069A90; this
0x18002a2c2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a2c9  cmp     byte ptr [rcx+8], 0
0x18002a2cd  jz      short loc_18002A2F0
0x18002a2cf  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002a2d4  cmp     [rax+7CCh], ebx
0x18002a2da  jz      short loc_18002A2F0
0x18002a2dc  mov     r9d, ebx; int
0x18002a2df  mov     r8d, 8F9h; int
0x18002a2e5  mov     rdx, r15; char *
0x18002a2e8  mov     rcx, rax; this
0x18002a2eb  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002a2f0  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002a2f5  cmp     al, 1
0x18002a2f7  jb      loc_18002A4C4
0x18002a2fd  mov     edx, 129h
0x18002a302  jmp     loc_18002A4A6
0x18002a307  xor     ebx, ebx
0x18002a309  jmp     loc_18002A4C4
0x18002a30e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a315  test    rcx, rcx
0x18002a318  jnz     short loc_18002A35B
0x18002a31a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002a320  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a327  mov     rcx, rax
0x18002a32a  test    rax, rax
0x18002a32d  jz      short loc_18002A34D
0x18002a32f  mov     rax, [rax]
0x18002a332  mov     edx, 7F0h
0x18002a337  mov     rax, [rax+8]
0x18002a33b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a340  test    eax, eax
0x18002a342  jz      short loc_18002A34D
0x18002a344  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a34b  jmp     short loc_18002A35B
0x18002a34d  lea     rcx, qword_180069A90; this
0x18002a354  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a35b  cmp     byte ptr [rcx+8], 0
0x18002a35f  jz      short loc_18002A382
0x18002a361  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002a366  cmp     [rax+7CCh], ebx
0x18002a36c  jz      short loc_18002A382
0x18002a36e  mov     r9d, ebx; int
0x18002a371  mov     r8d, 8F0h; int
0x18002a377  mov     rdx, r15; char *
0x18002a37a  mov     rcx, rax; this
0x18002a37d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002a382  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002a387  cmp     al, 1
0x18002a389  jb      loc_18002A4C4
0x18002a38f  mov     edx, 128h
0x18002a394  jmp     loc_18002A4A6
0x18002a399  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a3a0  test    rcx, rcx
0x18002a3a3  jnz     short loc_18002A3E6
0x18002a3a5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002a3ab  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a3b2  mov     rcx, rax
0x18002a3b5  test    rax, rax
0x18002a3b8  jz      short loc_18002A3D8
0x18002a3ba  mov     rax, [rax]
0x18002a3bd  mov     edx, 7F0h
0x18002a3c2  mov     rax, [rax+8]
0x18002a3c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a3cb  test    eax, eax
0x18002a3cd  jz      short loc_18002A3D8
0x18002a3cf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a3d6  jmp     short loc_18002A3E6
0x18002a3d8  lea     rcx, qword_180069A90; this
0x18002a3df  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a3e6  cmp     byte ptr [rcx+8], 0
0x18002a3ea  jz      short loc_18002A40D
0x18002a3ec  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002a3f1  cmp     [rax+7CCh], ebx
0x18002a3f7  jz      short loc_18002A40D
0x18002a3f9  mov     r9d, ebx; int
0x18002a3fc  mov     r8d, 8EFh; int
0x18002a402  mov     rdx, r15; char *
0x18002a405  mov     rcx, rax; this
0x18002a408  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002a40d  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002a412  cmp     al, 1
0x18002a414  jb      loc_18002A4C4
0x18002a41a  mov     edx, 127h
0x18002a41f  jmp     loc_18002A4A6
0x18002a424  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a42b  test    rcx, rcx
0x18002a42e  jnz     short loc_18002A471
0x18002a430  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002a436  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a43d  mov     rcx, rax
0x18002a440  test    rax, rax
0x18002a443  jz      short loc_18002A463
0x18002a445  mov     rax, [rax]
0x18002a448  mov     edx, 7F0h
0x18002a44d  mov     rax, [rax+8]
0x18002a451  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a456  test    eax, eax
0x18002a458  jz      short loc_18002A463
0x18002a45a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a461  jmp     short loc_18002A471
0x18002a463  lea     rcx, qword_180069A90; this
0x18002a46a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a471  cmp     byte ptr [rcx+8], 0
0x18002a475  jz      short loc_18002A498
0x18002a477  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002a47c  cmp     [rax+7CCh], ebx
0x18002a482  jz      short loc_18002A498
0x18002a484  mov     r9d, ebx; int
0x18002a487  mov     r8d, 8EEh; int
0x18002a48d  mov     rdx, r15; char *
0x18002a490  mov     rcx, rax; this
0x18002a493  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002a498  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002a49d  cmp     al, 1
0x18002a49f  jb      short loc_18002A4C4
0x18002a4a1  mov     edx, 126h
0x18002a4a6  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a4ad  lea     r8, WPP_14b006652b8137ad6e40de3d71db1d47_Traceguids
0x18002a4b4  mov     r9, rdi
0x18002a4b7  mov     dword ptr [rsp+50h+var_30], ebx
0x18002a4bb  mov     rcx, [rcx+10h]
0x18002a4bf  call    WPP_SF_qd
0x18002a4c4  lea     rcx, [rbp+ppBuffer]
0x18002a4c8  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x18002a4cd  lea     rcx, [rbp+ppIMFSample]
0x18002a4d1  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x18002a4d6  mov     rcx, qword ptr [rbp+var_10+8]
0x18002a4da  test    rcx, rcx
0x18002a4dd  jz      short loc_18002A4F3
0x18002a4df  mov     rdx, [rcx]
0x18002a4e2  mov     rax, [rdx+10h]
0x18002a4e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a4eb  mov     qword ptr [rbp+var_10+8], 0
0x18002a4f3  lea     rcx, [rbp+ppIMFSample]; this
0x18002a4f7  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
  ... truncated ...
```
