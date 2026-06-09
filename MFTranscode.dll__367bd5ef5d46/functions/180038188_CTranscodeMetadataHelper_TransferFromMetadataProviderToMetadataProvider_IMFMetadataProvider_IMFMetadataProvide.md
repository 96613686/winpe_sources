# CTranscodeMetadataHelper::TransferFromMetadataProviderToMetadataProvider(IMFMetadataProvider *,IMFMetadataProvider *,CTBucketHash<ulong,StreamSinkInfo> &)

- ea: `0x180038188`
- end: `0x180038361`
- name: `?TransferFromMetadataProviderToMetadataProvider@CTranscodeMetadataHelper@@SAJPEAUIMFMetadataProvider@@0AEAV?$CTBucketHash@KUStreamSinkInfo@@@@@Z`
- size: `473`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update`

## callers

- `0x1800451f0`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x180015e7c`
- `0x1800174c0`
- `0x18001a330`
- `0x18001c280`
- `0x180038188`
- `0x1800494cc`
- `0x18004f410`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800381fa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800382a8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800381fa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800382a8`

## pseudocode

```c
__int64 __fastcall CTranscodeMetadataHelper::TransferFromMetadataProviderToMetadataProvider(
        __int64 a1,
        __int64 a2,
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
  struct CallStackContext *ThreadRelativeContext; // rax
  _BYTE v18[4]; // [rsp+30h] [rbp-48h] BYREF
  unsigned int v19; // [rsp+34h] [rbp-44h] BYREF
  __int128 v20; // [rsp+38h] [rbp-40h] BYREF
  __int64 v21; // [rsp+48h] [rbp-30h]

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v18,
    "CTranscodeMetadataHelper::TransferFromMetadataProviderToMetadataProvider",
    22);
  v21 = 0;
  v19 = 0;
  v20 = 0;
  v8 = CTranscodeMetadataHelper::FillMetadataStreamIDMap(a3, &v20, v6, &v19);
  if ( v8 >= 0 )
  {
    v8 = MFCopyMFMetadata(a1, a2, (__int64)&v20, v19);
    if ( v8 < 0 )
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
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v14);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != v8 )
          CallStackContext::TraceFailure(
            ThreadRelativeContext,
            "CTranscodeMetadataHelper::TransferFromMetadataProviderToMetadataProvider",
            30,
            v8);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v12 = 12;
        goto LABEL_23;
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
          "CTranscodeMetadataHelper::TransferFromMetadataProviderToMetadataProvider",
          29,
          v8);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v12 = 11;
LABEL_23:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, WPP_418792fad9ae30642cdb8466b2eec0c4_Traceguids, 0, v8);
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v18);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180038188  push    rbx
0x18003818a  push    rsi
0x18003818b  push    rdi
0x18003818c  sub     rsp, 60h
0x180038190  mov     rax, cs:__security_cookie
0x180038197  xor     rax, rsp
0x18003819a  mov     [rsp+78h+var_28], rax
0x18003819f  mov     rbx, r8
0x1800381a2  mov     rsi, rdx
0x1800381a5  mov     rdi, rcx
0x1800381a8  lea     rdx, aCtranscodemeta; "CTranscodeMetadataHelper::TransferFromM"...
0x1800381af  mov     r8d, 16h; int
0x1800381b5  lea     rcx, [rsp+78h+var_48]; this
0x1800381ba  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800381bf  xor     eax, eax
0x1800381c1  lea     r9, [rsp+78h+var_44]
0x1800381c6  xorps   xmm0, xmm0
0x1800381c9  mov     [rsp+78h+var_30], rax
0x1800381ce  lea     rdx, [rsp+78h+var_40]
0x1800381d3  mov     [rsp+78h+var_44], eax
0x1800381d7  mov     rcx, rbx
0x1800381da  movups  [rsp+78h+var_40], xmm0
0x1800381df  call    ?FillMetadataStreamIDMap@CTranscodeMetadataHelper@@CAJAEAV?$CTBucketHash@KUStreamSinkInfo@@@@PEAUSTREAMID_MAP@@KPEAK@Z; CTranscodeMetadataHelper::FillMetadataStreamIDMap(CTBucketHash<ulong,StreamSinkInfo> &,STREAMID_MAP *,ulong,ulong *)
0x1800381e4  mov     ebx, eax
0x1800381e6  test    eax, eax
0x1800381e8  jns     loc_18003827D
0x1800381ee  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800381f5  test    rcx, rcx
0x1800381f8  jnz     short loc_18003823B
0x1800381fa  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180038200  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180038207  mov     rcx, rax
0x18003820a  test    rax, rax
0x18003820d  jz      short loc_18003822D
0x18003820f  mov     rax, [rax]
0x180038212  mov     edx, 7F0h
0x180038217  mov     rax, [rax+8]
0x18003821b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038220  test    eax, eax
0x180038222  jz      short loc_18003822D
0x180038224  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003822b  jmp     short loc_18003823B
0x18003822d  lea     rcx, qword_180069A90; this
0x180038234  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003823b  cmp     byte ptr [rcx+8], 0
0x18003823f  jz      short loc_180038266
0x180038241  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180038246  cmp     [rax+7CCh], ebx
0x18003824c  jz      short loc_180038266
0x18003824e  mov     r9d, ebx; int
0x180038251  lea     rdx, aCtranscodemeta; "CTranscodeMetadataHelper::TransferFromM"...
0x180038258  mov     r8d, 1Dh; int
0x18003825e  mov     rcx, rax; this
0x180038261  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180038266  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18003826b  cmp     al, 1
0x18003826d  jb      loc_180038340
0x180038273  mov     edx, 0Bh
0x180038278  jmp     loc_180038322
0x18003827d  mov     r9d, [rsp+78h+var_44]
0x180038282  lea     r8, [rsp+78h+var_40]
0x180038287  mov     rdx, rsi
0x18003828a  mov     rcx, rdi
0x18003828d  call    MFCopyMFMetadata
0x180038292  mov     ebx, eax
0x180038294  test    eax, eax
0x180038296  jns     loc_180038340
0x18003829c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800382a3  test    rcx, rcx
0x1800382a6  jnz     short loc_1800382E9
0x1800382a8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800382ae  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800382b5  mov     rcx, rax
0x1800382b8  test    rax, rax
0x1800382bb  jz      short loc_1800382DB
0x1800382bd  mov     rax, [rax]
0x1800382c0  mov     edx, 7F0h
0x1800382c5  mov     rax, [rax+8]
0x1800382c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800382ce  test    eax, eax
0x1800382d0  jz      short loc_1800382DB
0x1800382d2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800382d9  jmp     short loc_1800382E9
0x1800382db  lea     rcx, qword_180069A90; this
0x1800382e2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800382e9  cmp     byte ptr [rcx+8], 0
0x1800382ed  jz      short loc_180038314
0x1800382ef  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800382f4  cmp     [rax+7CCh], ebx
0x1800382fa  jz      short loc_180038314
0x1800382fc  mov     r9d, ebx; int
0x1800382ff  lea     rdx, aCtranscodemeta; "CTranscodeMetadataHelper::TransferFromM"...
0x180038306  mov     r8d, 1Eh; int
0x18003830c  mov     rcx, rax; this
0x18003830f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180038314  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180038319  cmp     al, 1
0x18003831b  jb      short loc_180038340
0x18003831d  mov     edx, 0Ch
0x180038322  mov     rcx, cs:WPP_GLOBAL_Control
0x180038329  lea     r8, WPP_418792fad9ae30642cdb8466b2eec0c4_Traceguids
0x180038330  xor     r9d, r9d
0x180038333  mov     [rsp+78h+var_58], ebx
0x180038337  mov     rcx, [rcx+10h]
0x18003833b  call    WPP_SF_qd
0x180038340  lea     rcx, [rsp+78h+var_48]; this
0x180038345  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18003834a  mov     eax, ebx
0x18003834c  mov     rcx, [rsp+78h+var_28]
0x180038351  xor     rcx, rsp; StackCookie
0x180038354  call    __security_check_cookie
0x180038359  add     rsp, 60h
0x18003835d  pop     rdi
0x18003835e  pop     rsi
0x18003835f  pop     rbx
0x180038360  retn
```
