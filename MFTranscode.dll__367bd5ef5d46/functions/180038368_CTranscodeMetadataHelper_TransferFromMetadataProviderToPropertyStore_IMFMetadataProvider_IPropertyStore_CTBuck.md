# CTranscodeMetadataHelper::TransferFromMetadataProviderToPropertyStore(IMFMetadataProvider *,IPropertyStore *,CTBucketHash<ulong,StreamSinkInfo> &)

- ea: `0x180038368`
- end: `0x1800385fc`
- name: `?TransferFromMetadataProviderToPropertyStore@CTranscodeMetadataHelper@@SAJPEAUIMFMetadataProvider@@PEAUIPropertyStore@@AEAV?$CTBucketHash@KUStreamSinkInfo@@@@@Z`
- size: `660`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180043670`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x18000a3f4`
- `0x180015e7c`
- `0x1800174c0`
- `0x18001a330`
- `0x18001c280`
- `0x180038368`
- `0x1800494cc`
- `0x180049f6c`
- `0x18004f410`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800383e2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180038487`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180038534`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800383e2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180038487`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180038534`

## pseudocode

```c
__int64 __fastcall CTranscodeMetadataHelper::TransferFromMetadataProviderToPropertyStore(
        __int64 a1,
        struct IPropertyStore *a2,
        __int64 a3)
{
  __int64 v6; // r8
  __int64 v7; // rdx
  int v8; // ebx
  __int64 *v9; // rcx
  CallStackTracing *v10; // rax
  struct CallStackContext *v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rdx
  __int64 *v14; // rcx
  CallStackTracing *v15; // rax
  struct CallStackContext *v16; // rax
  __int64 v17; // rdx
  __int64 *v18; // rcx
  CallStackTracing *v19; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  _BYTE v22[4]; // [rsp+30h] [rbp-30h] BYREF
  unsigned int v23; // [rsp+34h] [rbp-2Ch] BYREF
  void *v24; // [rsp+38h] [rbp-28h] BYREF
  __int128 v25; // [rsp+40h] [rbp-20h] BYREF
  __int64 v26; // [rsp+50h] [rbp-10h]

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v22,
    "CTranscodeMetadataHelper::TransferFromMetadataProviderToPropertyStore",
    59);
  v24 = 0;
  v26 = 0;
  v23 = 0;
  v25 = 0;
  v8 = CTranscodeMetadataHelper::FillMetadataStreamIDMap(a3, &v25, v6, &v23);
  if ( v8 >= 0 )
  {
    v8 = MFCreateMFMetadataOnPropertyStore(a2, &v24);
    if ( v8 >= 0 )
    {
      v8 = MFCopyMFMetadata(a1, (__int64)v24, (__int64)&v25, v23);
      if ( v8 < 0 )
      {
        v18 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v17);
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
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v18);
          if ( *((_DWORD *)ThreadRelativeContext + 499) != v8 )
            CallStackContext::TraceFailure(
              ThreadRelativeContext,
              "CTranscodeMetadataHelper::TransferFromMetadataProviderToPropertyStore",
              69,
              v8);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v12 = 19;
          goto LABEL_34;
        }
      }
    }
    else
    {
      v14 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v13);
        CallStackTracing::s_wpInstance = v15;
        if ( v15 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v15 + 8LL))(v15, 2032) )
        {
          v14 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v14 = &qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      if ( *((_BYTE *)v14 + 8) )
      {
        v16 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v14);
        if ( *((_DWORD *)v16 + 499) != v8 )
          CallStackContext::TraceFailure(
            v16,
            "CTranscodeMetadataHelper::TransferFromMetadataProviderToPropertyStore",
            68,
            v8);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v12 = 18;
        goto LABEL_34;
      }
    }
  }
  else
  {
    v9 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v7);
      CallStackTracing::s_wpInstance = v10;
      if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
      {
        v9 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v9 = &qword_180069A90;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
      }
    }
    if ( *((_BYTE *)v9 + 8) )
    {
      v11 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v9);
      if ( *((_DWORD *)v11 + 499) != v8 )
        CallStackContext::TraceFailure(
          v11,
          "CTranscodeMetadataHelper::TransferFromMetadataProviderToPropertyStore",
          67,
          v8);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v12 = 17;
LABEL_34:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, WPP_418792fad9ae30642cdb8466b2eec0c4_Traceguids, 0, v8);
    }
  }
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>((__int64 *)&v24);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v22);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180038368  mov     [rsp-18h+arg_18], rbx
0x18003836d  push    rbp
0x18003836e  push    rsi
0x18003836f  push    rdi
0x180038370  mov     rbp, rsp
0x180038373  sub     rsp, 60h
0x180038377  mov     rax, cs:__security_cookie
0x18003837e  xor     rax, rsp
0x180038381  mov     [rbp+var_8], rax
0x180038385  mov     rbx, r8
0x180038388  mov     rdi, rdx
0x18003838b  mov     rsi, rcx
0x18003838e  lea     rdx, aCtranscodemeta_2; "CTranscodeMetadataHelper::TransferFromM"...
0x180038395  mov     r8d, 3Bh ; ';'; int
0x18003839b  lea     rcx, [rbp+var_30]; this
0x18003839f  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800383a4  xor     eax, eax
0x1800383a6  mov     [rbp+var_28], 0
0x1800383ae  xorps   xmm0, xmm0
0x1800383b1  mov     [rbp+var_10], rax
0x1800383b5  lea     r9, [rbp+var_2C]
0x1800383b9  mov     [rbp+var_2C], eax
0x1800383bc  lea     rdx, [rbp+var_20]
0x1800383c0  mov     rcx, rbx
0x1800383c3  movups  [rbp+var_20], xmm0
0x1800383c7  call    ?FillMetadataStreamIDMap@CTranscodeMetadataHelper@@CAJAEAV?$CTBucketHash@KUStreamSinkInfo@@@@PEAUSTREAMID_MAP@@KPEAK@Z; CTranscodeMetadataHelper::FillMetadataStreamIDMap(CTBucketHash<ulong,StreamSinkInfo> &,STREAMID_MAP *,ulong,ulong *)
0x1800383cc  mov     ebx, eax
0x1800383ce  test    eax, eax
0x1800383d0  jns     loc_180038465
0x1800383d6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800383dd  test    rcx, rcx
0x1800383e0  jnz     short loc_180038423
0x1800383e2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800383e8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800383ef  mov     rcx, rax
0x1800383f2  test    rax, rax
0x1800383f5  jz      short loc_180038415
0x1800383f7  mov     rax, [rax]
0x1800383fa  mov     edx, 7F0h
0x1800383ff  mov     rax, [rax+8]
0x180038403  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038408  test    eax, eax
0x18003840a  jz      short loc_180038415
0x18003840c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180038413  jmp     short loc_180038423
0x180038415  lea     rcx, qword_180069A90; this
0x18003841c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180038423  cmp     byte ptr [rcx+8], 0
0x180038427  jz      short loc_18003844E
0x180038429  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003842e  cmp     [rax+7CCh], ebx
0x180038434  jz      short loc_18003844E
0x180038436  mov     r9d, ebx; int
0x180038439  lea     rdx, aCtranscodemeta_2; "CTranscodeMetadataHelper::TransferFromM"...
0x180038440  mov     r8d, 43h ; 'C'; int
0x180038446  mov     rcx, rax; this
0x180038449  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003844e  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180038453  cmp     al, 1
0x180038455  jb      loc_1800385CC
0x18003845b  mov     edx, 11h
0x180038460  jmp     loc_1800385AE
0x180038465  lea     rdx, [rbp+var_28]; void **
0x180038469  mov     rcx, rdi; struct IPropertyStore *
0x18003846c  call    MFCreateMFMetadataOnPropertyStore
0x180038471  mov     ebx, eax
0x180038473  test    eax, eax
0x180038475  jns     loc_18003850A
0x18003847b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180038482  test    rcx, rcx
0x180038485  jnz     short loc_1800384C8
0x180038487  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003848d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180038494  mov     rcx, rax
0x180038497  test    rax, rax
0x18003849a  jz      short loc_1800384BA
0x18003849c  mov     rax, [rax]
0x18003849f  mov     edx, 7F0h
0x1800384a4  mov     rax, [rax+8]
0x1800384a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800384ad  test    eax, eax
0x1800384af  jz      short loc_1800384BA
0x1800384b1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800384b8  jmp     short loc_1800384C8
0x1800384ba  lea     rcx, qword_180069A90; this
0x1800384c1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800384c8  cmp     byte ptr [rcx+8], 0
0x1800384cc  jz      short loc_1800384F3
0x1800384ce  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800384d3  cmp     [rax+7CCh], ebx
0x1800384d9  jz      short loc_1800384F3
0x1800384db  mov     r9d, ebx; int
0x1800384de  lea     rdx, aCtranscodemeta_2; "CTranscodeMetadataHelper::TransferFromM"...
0x1800384e5  mov     r8d, 44h ; 'D'; int
0x1800384eb  mov     rcx, rax; this
0x1800384ee  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800384f3  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800384f8  cmp     al, 1
0x1800384fa  jb      loc_1800385CC
0x180038500  mov     edx, 12h
0x180038505  jmp     loc_1800385AE
0x18003850a  mov     r9d, [rbp+var_2C]
0x18003850e  lea     r8, [rbp+var_20]
0x180038512  mov     rdx, [rbp+var_28]
0x180038516  mov     rcx, rsi
0x180038519  call    MFCopyMFMetadata
0x18003851e  mov     ebx, eax
0x180038520  test    eax, eax
0x180038522  jns     loc_1800385CC
0x180038528  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003852f  test    rcx, rcx
0x180038532  jnz     short loc_180038575
0x180038534  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003853a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180038541  mov     rcx, rax
0x180038544  test    rax, rax
0x180038547  jz      short loc_180038567
0x180038549  mov     rax, [rax]
0x18003854c  mov     edx, 7F0h
0x180038551  mov     rax, [rax+8]
0x180038555  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003855a  test    eax, eax
0x18003855c  jz      short loc_180038567
0x18003855e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180038565  jmp     short loc_180038575
0x180038567  lea     rcx, qword_180069A90; this
0x18003856e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180038575  cmp     byte ptr [rcx+8], 0
0x180038579  jz      short loc_1800385A0
0x18003857b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180038580  cmp     [rax+7CCh], ebx
0x180038586  jz      short loc_1800385A0
0x180038588  mov     r9d, ebx; int
0x18003858b  lea     rdx, aCtranscodemeta_2; "CTranscodeMetadataHelper::TransferFromM"...
0x180038592  mov     r8d, 45h ; 'E'; int
0x180038598  mov     rcx, rax; this
0x18003859b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800385a0  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800385a5  cmp     al, 1
0x1800385a7  jb      short loc_1800385CC
0x1800385a9  mov     edx, 13h
0x1800385ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800385b5  lea     r8, WPP_418792fad9ae30642cdb8466b2eec0c4_Traceguids
0x1800385bc  xor     r9d, r9d
0x1800385bf  mov     [rsp+60h+var_40], ebx
0x1800385c3  mov     rcx, [rcx+10h]
0x1800385c7  call    WPP_SF_qd
0x1800385cc  lea     rcx, [rbp+var_28]
0x1800385d0  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x1800385d5  lea     rcx, [rbp+var_30]; this
0x1800385d9  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800385de  mov     eax, ebx
0x1800385e0  mov     rcx, [rbp+var_8]
0x1800385e4  xor     rcx, rsp; StackCookie
0x1800385e7  call    __security_check_cookie
0x1800385ec  mov     rbx, [rsp+60h+arg_18]
0x1800385f4  add     rsp, 60h
0x1800385f8  pop     rdi
0x1800385f9  pop     rsi
0x1800385fa  pop     rbp
0x1800385fb  retn
```
