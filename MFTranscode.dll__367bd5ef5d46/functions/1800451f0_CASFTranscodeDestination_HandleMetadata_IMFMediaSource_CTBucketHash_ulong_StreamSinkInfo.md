# CASFTranscodeDestination::HandleMetadata(IMFMediaSource *,CTBucketHash<ulong,StreamSinkInfo> &)

- ea: `0x1800451f0`
- end: `0x180045708`
- name: `?HandleMetadata@CASFTranscodeDestination@@UEAAJPEAUIMFMediaSource@@AEAV?$CTBucketHash@KUStreamSinkInfo@@@@@Z`
- size: `1304`
- prototype: `__int64 __fastcall(CTranscodeDestination *this)`
- caller_count: `0`
- callee_count: `13`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x18000a3f4`
- `0x18001a330`
- `0x18001c280`
- `0x180038188`
- `0x180038604`
- `0x180044094`
- `0x1800451f0`
- `0x1800458d0`
- `0x18004f410`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180045272`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180045317`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800453cc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800454bc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180045588`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004562c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180045272`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180045317`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800453cc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800454bc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180045588`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004562c`

## pseudocode

```c
__int64 __fastcall CASFTranscodeDestination::HandleMetadata(
        CTranscodeDestination *this,
        int (__fastcall ***a2)(_QWORD, GUID *, __int64 *),
        __int64 a3)
{
  __int64 (__fastcall ***v6)(_QWORD, GUID *, struct IMFMetadataProvider **); // rcx
  __int64 (__fastcall **v7)(_QWORD, GUID *, struct IMFMetadataProvider **); // rax
  __int64 v8; // rdx
  int IsTransferMetadataNeeded; // ebx
  __int64 *v10; // rcx
  CallStackTracing *v11; // rax
  struct CallStackContext *v12; // rax
  __int64 v13; // rdx
  __int64 v14; // rdx
  __int64 *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  __int64 v18; // rdx
  __int64 *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v22; // rdx
  __int64 *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *v25; // rax
  __int64 v26; // rdx
  __int64 *v27; // rcx
  CallStackTracing *v28; // rax
  struct CallStackContext *v29; // rax
  __int64 v30; // rdx
  __int64 *v31; // rcx
  CallStackTracing *v32; // rax
  struct CallStackContext *v33; // rax
  struct IPropertyStore *v35; // [rsp+30h] [rbp-20h] BYREF
  __int64 v36; // [rsp+38h] [rbp-18h] BYREF
  __int64 v37[2]; // [rsp+40h] [rbp-10h] BYREF
  int v38; // [rsp+80h] [rbp+30h] BYREF
  struct IMFMetadataProvider *v39; // [rsp+98h] [rbp+48h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v38, "CASFTranscodeDestination::HandleMetadata", 210);
  v6 = (__int64 (__fastcall ***)(_QWORD, GUID *, struct IMFMetadataProvider **))*((_QWORD *)this + 9);
  v39 = 0;
  v36 = 0;
  v37[0] = 0;
  v35 = 0;
  v7 = *v6;
  v38 = 0;
  IsTransferMetadataNeeded = (*v7)(v6, &IID_IMFMetadataProvider, &v39);
  if ( IsTransferMetadataNeeded >= 0 )
  {
    IsTransferMetadataNeeded = CTranscodeDestination::IsTransferMetadataNeeded(this, &v38, &v35);
    if ( IsTransferMetadataNeeded >= 0 )
    {
      if ( v38 )
      {
        if ( v35 )
        {
          IsTransferMetadataNeeded = CTranscodeMetadataHelper::TransferFromPropertyStoreToMetadataProvider(v35, v39);
          if ( IsTransferMetadataNeeded < 0 )
          {
            v19 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18);
              CallStackTracing::s_wpInstance = v20;
              if ( v20
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2032) )
              {
                v19 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v19 = &qword_180069A90;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
              }
            }
            if ( *((_BYTE *)v19 + 8) )
            {
              ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
              if ( *((_DWORD *)ThreadRelativeContext + 499) != IsTransferMetadataNeeded )
                CallStackContext::TraceFailure(
                  ThreadRelativeContext,
                  "CASFTranscodeDestination::HandleMetadata",
                  235,
                  IsTransferMetadataNeeded);
            }
            if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            {
              v13 = 23;
              goto LABEL_72;
            }
            goto LABEL_73;
          }
        }
        else if ( (**a2)(a2, &IID_IMFGetService, &v36) >= 0 )
        {
          if ( (*(int (__fastcall **)(__int64, const IID *, GUID *, __int64 *))(*(_QWORD *)v36 + 24LL))(
                 v36,
                 &MF_METADATA_PROVIDER_SERVICE,
                 &IID_IMFMetadataProvider,
                 v37) < 0 )
          {
            if ( (*(int (__fastcall **)(__int64, const IID *, GUID *, struct IPropertyStore **))(*(_QWORD *)v36 + 24LL))(
                   v36,
                   &MF_PROPERTY_HANDLER_SERVICE,
                   &IID_IPropertyStore,
                   &v35) >= 0 )
            {
              IsTransferMetadataNeeded = CTranscodeMetadataHelper::TransferFromPropertyStoreToMetadataProvider(v35, v39);
              if ( IsTransferMetadataNeeded < 0 )
              {
                v27 = (__int64 *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v26);
                  CallStackTracing::s_wpInstance = v28;
                  if ( v28
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
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
                  v29 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v27);
                  if ( *((_DWORD *)v29 + 499) != IsTransferMetadataNeeded )
                    CallStackContext::TraceFailure(
                      v29,
                      "CASFTranscodeDestination::HandleMetadata",
                      258,
                      IsTransferMetadataNeeded);
                }
                if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                {
                  v13 = 25;
                  goto LABEL_72;
                }
                goto LABEL_73;
              }
            }
          }
          else
          {
            IsTransferMetadataNeeded = CTranscodeMetadataHelper::TransferFromMetadataProviderToMetadataProvider(
                                         v37[0],
                                         v39,
                                         a3);
            if ( IsTransferMetadataNeeded < 0 )
            {
              v23 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22);
                CallStackTracing::s_wpInstance = v24;
                if ( v24
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
                {
                  v23 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v23 = &qword_180069A90;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
                }
              }
              if ( *((_BYTE *)v23 + 8) )
              {
                v25 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
                if ( *((_DWORD *)v25 + 499) != IsTransferMetadataNeeded )
                  CallStackContext::TraceFailure(
                    v25,
                    "CASFTranscodeDestination::HandleMetadata",
                    248,
                    IsTransferMetadataNeeded);
              }
              if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
              {
                v13 = 24;
                goto LABEL_72;
              }
              goto LABEL_73;
            }
          }
        }
      }
      IsTransferMetadataNeeded = CASFTranscodeDestination::SetDeviceNeededMetadata(this, a3, v39);
      if ( IsTransferMetadataNeeded < 0 )
      {
        v31 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v30);
          CallStackTracing::s_wpInstance = v32;
          if ( v32 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v32 + 8LL))(v32, 2032) )
          {
            v31 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v31 = &qword_180069A90;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
          }
        }
        if ( *((_BYTE *)v31 + 8) )
        {
          v33 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v31);
          if ( *((_DWORD *)v33 + 499) != IsTransferMetadataNeeded )
            CallStackContext::TraceFailure(
              v33,
              "CASFTranscodeDestination::HandleMetadata",
              266,
              IsTransferMetadataNeeded);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v13 = 26;
          goto LABEL_72;
        }
      }
      goto LABEL_73;
    }
    v15 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v14);
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
      if ( *((_DWORD *)v17 + 499) != IsTransferMetadataNeeded )
        CallStackContext::TraceFailure(v17, "CASFTranscodeDestination::HandleMetadata", 228, IsTransferMetadataNeeded);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v13 = 22;
      goto LABEL_72;
    }
  }
  else
  {
    v10 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v11 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8);
      CallStackTracing::s_wpInstance = v11;
      if ( v11 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v11 + 8LL))(v11, 2032) )
      {
        v10 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v10 = &qword_180069A90;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
      }
    }
    if ( *((_BYTE *)v10 + 8) )
    {
      v12 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v10);
      if ( *((_DWORD *)v12 + 499) != IsTransferMetadataNeeded )
        CallStackContext::TraceFailure(v12, "CASFTranscodeDestination::HandleMetadata", 223, IsTransferMetadataNeeded);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v13 = 21;
LABEL_72:
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v13,
        &WPP_0a758c1def7e3974366218a1d0d46647_Traceguids,
        this,
        IsTransferMetadataNeeded);
    }
  }
LABEL_73:
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>((__int64 *)&v35);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(v37);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v36);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>((__int64 *)&v39);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v38);
  return (unsigned int)IsTransferMetadataNeeded;
}

```

## disassembly

```asm
0x1800451f0  mov     [rsp-28h+arg_8], rbx
0x1800451f5  mov     [rsp-28h+arg_10], rsi
0x1800451fa  push    rbp
0x1800451fb  push    rdi
0x1800451fc  push    r12
0x1800451fe  push    r14
0x180045200  push    r15
0x180045202  mov     rbp, rsp
0x180045205  sub     rsp, 50h
0x180045209  mov     rsi, r8
0x18004520c  lea     r12, aCasftranscoded_8; "CASFTranscodeDestination::HandleMetadat"...
0x180045213  mov     r14, rdx
0x180045216  mov     rdi, rcx
0x180045219  mov     rdx, r12; char *
0x18004521c  lea     rcx, [rbp+arg_0]; this
0x180045220  mov     r8d, 0D2h; int
0x180045226  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18004522b  mov     rcx, [rdi+48h]
0x18004522f  lea     r8, [rbp+arg_18]
0x180045233  xor     r15d, r15d
0x180045236  lea     rdx, IID_IMFMetadataProvider
0x18004523d  mov     [rbp+arg_18], r15
0x180045241  mov     [rbp+var_18], r15
0x180045245  mov     [rbp+var_10], r15
0x180045249  mov     [rbp+var_20], r15
0x18004524d  mov     rax, [rcx]
0x180045250  mov     [rbp+arg_0], r15d
0x180045254  mov     rax, [rax]
0x180045257  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004525c  mov     ebx, eax
0x18004525e  test    eax, eax
0x180045260  jns     loc_1800452F1
0x180045266  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004526d  test    rcx, rcx
0x180045270  jnz     short loc_1800452B3
0x180045272  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180045278  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004527f  mov     rcx, rax
0x180045282  test    rax, rax
0x180045285  jz      short loc_1800452A5
0x180045287  mov     rax, [rax]
0x18004528a  mov     edx, 7F0h
0x18004528f  mov     rax, [rax+8]
0x180045293  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045298  test    eax, eax
0x18004529a  jz      short loc_1800452A5
0x18004529c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800452a3  jmp     short loc_1800452B3
0x1800452a5  lea     rcx, qword_180069A90; this
0x1800452ac  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800452b3  cmp     [rcx+8], r15b
0x1800452b7  jz      short loc_1800452DA
0x1800452b9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800452be  cmp     [rax+7CCh], ebx
0x1800452c4  jz      short loc_1800452DA
0x1800452c6  mov     r9d, ebx; int
0x1800452c9  mov     r8d, 0DFh; int
0x1800452cf  mov     rdx, r12; char *
0x1800452d2  mov     rcx, rax; this
0x1800452d5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800452da  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800452df  cmp     al, 1
0x1800452e1  jb      loc_1800456C0
0x1800452e7  mov     edx, 15h
0x1800452ec  jmp     loc_1800456A2
0x1800452f1  lea     r8, [rbp+var_20]; struct IPropertyStore **
0x1800452f5  mov     rcx, rdi; this
0x1800452f8  lea     rdx, [rbp+arg_0]; int *
0x1800452fc  call    ?IsTransferMetadataNeeded@CTranscodeDestination@@IEAAJPEAHPEAPEAUIPropertyStore@@@Z; CTranscodeDestination::IsTransferMetadataNeeded(int *,IPropertyStore * *)
0x180045301  mov     ebx, eax
0x180045303  test    eax, eax
0x180045305  jns     loc_180045396
0x18004530b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180045312  test    rcx, rcx
0x180045315  jnz     short loc_180045358
0x180045317  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004531d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180045324  mov     rcx, rax
0x180045327  test    rax, rax
0x18004532a  jz      short loc_18004534A
0x18004532c  mov     rax, [rax]
0x18004532f  mov     edx, 7F0h
0x180045334  mov     rax, [rax+8]
0x180045338  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004533d  test    eax, eax
0x18004533f  jz      short loc_18004534A
0x180045341  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180045348  jmp     short loc_180045358
0x18004534a  lea     rcx, qword_180069A90; this
0x180045351  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180045358  cmp     [rcx+8], r15b
0x18004535c  jz      short loc_18004537F
0x18004535e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180045363  cmp     [rax+7CCh], ebx
0x180045369  jz      short loc_18004537F
0x18004536b  mov     r9d, ebx; int
0x18004536e  mov     r8d, 0E4h; int
0x180045374  mov     rdx, r12; char *
0x180045377  mov     rcx, rax; this
0x18004537a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004537f  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180045384  cmp     al, 1
0x180045386  jb      loc_1800456C0
0x18004538c  mov     edx, 16h
0x180045391  jmp     loc_1800456A2
0x180045396  cmp     [rbp+arg_0], r15d
0x18004539a  jz      loc_180045607
0x1800453a0  mov     rcx, [rbp+var_20]; struct IPropertyStore *
0x1800453a4  test    rcx, rcx
0x1800453a7  jz      loc_18004544B
0x1800453ad  mov     rdx, [rbp+arg_18]; struct IMFMetadataProvider *
0x1800453b1  call    ?TransferFromPropertyStoreToMetadataProvider@CTranscodeMetadataHelper@@SAJPEAUIPropertyStore@@PEAUIMFMetadataProvider@@@Z; CTranscodeMetadataHelper::TransferFromPropertyStoreToMetadataProvider(IPropertyStore *,IMFMetadataProvider *)
0x1800453b6  mov     ebx, eax
0x1800453b8  test    eax, eax
0x1800453ba  jns     loc_180045607
0x1800453c0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800453c7  test    rcx, rcx
0x1800453ca  jnz     short loc_18004540D
0x1800453cc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800453d2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800453d9  mov     rcx, rax
0x1800453dc  test    rax, rax
0x1800453df  jz      short loc_1800453FF
0x1800453e1  mov     rax, [rax]
0x1800453e4  mov     edx, 7F0h
0x1800453e9  mov     rax, [rax+8]
0x1800453ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800453f2  test    eax, eax
0x1800453f4  jz      short loc_1800453FF
0x1800453f6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800453fd  jmp     short loc_18004540D
0x1800453ff  lea     rcx, qword_180069A90; this
0x180045406  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004540d  cmp     [rcx+8], r15b
0x180045411  jz      short loc_180045434
0x180045413  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180045418  cmp     [rax+7CCh], ebx
0x18004541e  jz      short loc_180045434
0x180045420  mov     r9d, ebx; int
0x180045423  mov     r8d, 0EBh; int
0x180045429  mov     rdx, r12; char *
0x18004542c  mov     rcx, rax; this
0x18004542f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180045434  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180045439  cmp     al, 1
0x18004543b  jb      loc_1800456C0
0x180045441  mov     edx, 17h
0x180045446  jmp     loc_1800456A2
0x18004544b  mov     rax, [r14]
0x18004544e  lea     r8, [rbp+var_18]
0x180045452  lea     rdx, IID_IMFGetService
0x180045459  mov     rcx, r14
0x18004545c  mov     rax, [rax]
0x18004545f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045464  test    eax, eax
0x180045466  js      loc_180045607
0x18004546c  mov     rcx, [rbp+var_18]
0x180045470  lea     r9, [rbp+var_10]
0x180045474  lea     r8, IID_IMFMetadataProvider
0x18004547b  lea     rdx, MF_METADATA_PROVIDER_SERVICE
0x180045482  mov     rax, [rcx]
0x180045485  mov     rax, [rax+18h]
0x180045489  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004548e  test    eax, eax
0x180045490  js      loc_18004553B
0x180045496  mov     rdx, [rbp+arg_18]
0x18004549a  mov     r8, rsi
0x18004549d  mov     rcx, [rbp+var_10]
0x1800454a1  call    ?TransferFromMetadataProviderToMetadataProvider@CTranscodeMetadataHelper@@SAJPEAUIMFMetadataProvider@@0AEAV?$CTBucketHash@KUStreamSinkInfo@@@@@Z; CTranscodeMetadataHelper::TransferFromMetadataProviderToMetadataProvider(IMFMetadataProvider *,IMFMetadataProvider *,CTBucketHash<ulong,StreamSinkInfo> &)
0x1800454a6  mov     ebx, eax
0x1800454a8  test    eax, eax
0x1800454aa  jns     loc_180045607
0x1800454b0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800454b7  test    rcx, rcx
0x1800454ba  jnz     short loc_1800454FD
0x1800454bc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800454c2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800454c9  mov     rcx, rax
0x1800454cc  test    rax, rax
0x1800454cf  jz      short loc_1800454EF
0x1800454d1  mov     rax, [rax]
0x1800454d4  mov     edx, 7F0h
0x1800454d9  mov     rax, [rax+8]
0x1800454dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800454e2  test    eax, eax
0x1800454e4  jz      short loc_1800454EF
0x1800454e6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800454ed  jmp     short loc_1800454FD
0x1800454ef  lea     rcx, qword_180069A90; this
0x1800454f6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800454fd  cmp     [rcx+8], r15b
0x180045501  jz      short loc_180045524
0x180045503  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180045508  cmp     [rax+7CCh], ebx
0x18004550e  jz      short loc_180045524
0x180045510  mov     r9d, ebx; int
0x180045513  mov     r8d, 0F8h; int
0x180045519  mov     rdx, r12; char *
0x18004551c  mov     rcx, rax; this
0x18004551f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180045524  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180045529  cmp     al, 1
0x18004552b  jb      loc_1800456C0
0x180045531  mov     edx, 18h
0x180045536  jmp     loc_1800456A2
0x18004553b  mov     rcx, [rbp+var_18]
0x18004553f  lea     r9, [rbp+var_20]
0x180045543  lea     r8, IID_IPropertyStore
0x18004554a  lea     rdx, MF_PROPERTY_HANDLER_SERVICE
0x180045551  mov     rax, [rcx]
0x180045554  mov     rax, [rax+18h]
0x180045558  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004555d  test    eax, eax
0x18004555f  js      loc_180045607
0x180045565  mov     rdx, [rbp+arg_18]; struct IMFMetadataProvider *
0x180045569  mov     rcx, [rbp+var_20]; struct IPropertyStore *
0x18004556d  call    ?TransferFromPropertyStoreToMetadataProvider@CTranscodeMetadataHelper@@SAJPEAUIPropertyStore@@PEAUIMFMetadataProvider@@@Z; CTranscodeMetadataHelper::TransferFromPropertyStoreToMetadataProvider(IPropertyStore *,IMFMetadataProvider *)
0x180045572  mov     ebx, eax
0x180045574  test    eax, eax
0x180045576  jns     loc_180045607
0x18004557c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180045583  test    rcx, rcx
0x180045586  jnz     short loc_1800455C9
0x180045588  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004558e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180045595  mov     rcx, rax
0x180045598  test    rax, rax
0x18004559b  jz      short loc_1800455BB
0x18004559d  mov     rax, [rax]
0x1800455a0  mov     edx, 7F0h
0x1800455a5  mov     rax, [rax+8]
0x1800455a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800455ae  test    eax, eax
0x1800455b0  jz      short loc_1800455BB
0x1800455b2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800455b9  jmp     short loc_1800455C9
0x1800455bb  lea     rcx, qword_180069A90; this
0x1800455c2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800455c9  cmp     [rcx+8], r15b
0x1800455cd  jz      short loc_1800455F0
0x1800455cf  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800455d4  cmp     [rax+7CCh], ebx
0x1800455da  jz      short loc_1800455F0
0x1800455dc  mov     r9d, ebx; int
0x1800455df  mov     r8d, 102h; int
0x1800455e5  mov     rdx, r12; char *
0x1800455e8  mov     rcx, rax; this
0x1800455eb  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800455f0  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800455f5  cmp     al, 1
0x1800455f7  jb      loc_1800456C0
0x1800455fd  mov     edx, 19h
0x180045602  jmp     loc_1800456A2
0x180045607  mov     r8, [rbp+arg_18]
0x18004560b  mov     rdx, rsi
0x18004560e  mov     rcx, rdi
0x180045611  call    ?SetDeviceNeededMetadata@CASFTranscodeDestination@@IEAAJAEAV?$CTBucketHash@KUStreamSinkInfo@@@@PEAUIMFMetadataProvider@@@Z; CASFTranscodeDestination::SetDeviceNeededMetadata(CTBucketHash<ulong,StreamSinkInfo> &,IMFMetadataProvider *)
0x180045616  mov     ebx, eax
0x180045618  test    eax, eax
0x18004561a  jns     loc_1800456C0
0x180045620  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180045627  test    rcx, rcx
0x18004562a  jnz     short loc_18004566D
0x18004562c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180045632  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180045639  mov     rcx, rax
0x18004563c  test    rax, rax
0x18004563f  jz      short loc_18004565F
0x180045641  mov     rax, [rax]
0x180045644  mov     edx, 7F0h
0x180045649  mov     rax, [rax+8]
0x18004564d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045652  test    eax, eax
0x180045654  jz      short loc_18004565F
0x180045656  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004565d  jmp     short loc_18004566D
0x18004565f  lea     rcx, qword_180069A90; this
0x180045666  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004566d  cmp     [rcx+8], r15b
0x180045671  jz      short loc_180045694
0x180045673  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180045678  cmp     [rax+7CCh], ebx
0x18004567e  jz      short loc_180045694
0x180045680  mov     r9d, ebx; int
0x180045683  mov     r8d, 10Ah; int
0x180045689  mov     rdx, r12; char *
0x18004568c  mov     rcx, rax; this
0x18004568f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180045694  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180045699  cmp     al, 1
0x18004569b  jb      short loc_1800456C0
0x18004569d  mov     edx, 1Ah
0x1800456a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800456a9  lea     r8, WPP_0a758c1def7e3974366218a1d0d46647_Traceguids
0x1800456b0  mov     r9, rdi
0x1800456b3  mov     [rsp+50h+var_30], ebx
0x1800456b7  mov     rcx, [rcx+10h]
0x1800456bb  call    WPP_SF_qd
0x1800456c0  lea     rcx, [rbp+var_20]
0x1800456c4  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
  ... truncated ...
```
