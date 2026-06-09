# CTranscodeDestination::HandleMetadata(IMFMediaSource *,CTBucketHash<ulong,StreamSinkInfo> &)

- ea: `0x180043670`
- end: `0x180043a8f`
- name: `?HandleMetadata@CTranscodeDestination@@UEAAJPEAUIMFMediaSource@@AEAV?$CTBucketHash@KUStreamSinkInfo@@@@@Z`
- size: `1055`
- prototype: `__int64 __fastcall(CTranscodeDestination *this)`
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x18000a3f4`
- `0x18001a330`
- `0x18001c280`
- `0x180038368`
- `0x180043670`
- `0x180044094`
- `0x1800497a4`
- `0x18004f410`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800436ec`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004378f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180043908`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800439aa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800436ec`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004378f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180043908`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800439aa`

## pseudocode

```c
__int64 __fastcall CTranscodeDestination::HandleMetadata(
        CTranscodeDestination *this,
        int (__fastcall ***a2)(_QWORD, GUID *, __int64 *),
        __int64 a3)
{
  __int64 v6; // rdx
  int IsTransferMetadataNeeded; // ebx
  __int64 *v8; // rcx
  CallStackTracing *v9; // rax
  struct CallStackContext *v10; // rax
  __int64 v11; // rdx
  __int64 *v12; // rcx
  CallStackTracing *v13; // rax
  struct CallStackContext *v14; // rax
  __int64 *v15; // rcx
  __int64 v16; // rdx
  __int64 *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v20; // rdx
  __int64 *v21; // rcx
  CallStackTracing *v22; // rax
  struct CallStackContext *v23; // rax
  __int64 v25; // [rsp+30h] [rbp-20h] BYREF
  __int64 v26; // [rsp+38h] [rbp-18h] BYREF
  __int64 v27; // [rsp+40h] [rbp-10h] BYREF
  __int64 v28; // [rsp+48h] [rbp-8h] BYREF
  int v29; // [rsp+80h] [rbp+30h] BYREF
  struct IPropertyStore *v30; // [rsp+98h] [rbp+48h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v29, "CTranscodeDestination::HandleMetadata", 401);
  v28 = 0;
  v26 = 0;
  v25 = 0;
  v30 = 0;
  v27 = 0;
  v29 = 0;
  IsTransferMetadataNeeded = CTranscodeDestination::IsTransferMetadataNeeded(this, &v29, &v30);
  if ( IsTransferMetadataNeeded >= 0 )
  {
    if ( !v29 )
      goto LABEL_55;
    if ( a2 )
    {
      if ( (***((int (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 7))(
             *((_QWORD *)this + 7),
             &IID_IMFGetService,
             &v28) < 0
        || !v30 && (**a2)(a2, &IID_IMFGetService, &v26) < 0
        || (*(int (__fastcall **)(__int64, const IID *, GUID *, __int64 *))(*(_QWORD *)v28 + 24LL))(
             v28,
             &MF_PROPERTY_HANDLER_SERVICE,
             &IID_IPropertyStore,
             &v25) < 0 )
      {
        goto LABEL_55;
      }
      v15 = (__int64 *)v30;
      if ( !v30 )
      {
        if ( (*(int (__fastcall **)(__int64, const IID *, GUID *, struct IPropertyStore **))(*(_QWORD *)v26 + 24LL))(
               v26,
               &MF_PROPERTY_HANDLER_SERVICE,
               &IID_IPropertyStore,
               &v30) < 0 )
        {
          if ( (*(int (__fastcall **)(__int64, const IID *, GUID *, __int64 *))(*(_QWORD *)v26 + 24LL))(
                 v26,
                 &MF_METADATA_PROVIDER_SERVICE,
                 &IID_IMFMetadataProvider,
                 &v27) >= 0 )
          {
            IsTransferMetadataNeeded = CTranscodeMetadataHelper::TransferFromMetadataProviderToPropertyStore(
                                         v27,
                                         v25,
                                         a3);
            if ( IsTransferMetadataNeeded < 0 )
            {
              v17 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v16);
                CallStackTracing::s_wpInstance = v18;
                if ( v18
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
                {
                  v17 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v17 = &qword_180069A90;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
                }
              }
              if ( *((_BYTE *)v17 + 8) )
              {
                ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v17);
                if ( *((_DWORD *)ThreadRelativeContext + 499) != IsTransferMetadataNeeded )
                  CallStackContext::TraceFailure(
                    ThreadRelativeContext,
                    "CTranscodeDestination::HandleMetadata",
                    451,
                    IsTransferMetadataNeeded);
              }
              if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
              {
                v11 = 72;
                goto LABEL_54;
              }
            }
          }
          goto LABEL_55;
        }
        v15 = (__int64 *)v30;
      }
      IsTransferMetadataNeeded = MFCopyPropertyStore(v15, v25);
      if ( IsTransferMetadataNeeded < 0 )
      {
        v21 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v20);
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
          if ( *((_DWORD *)v23 + 499) != IsTransferMetadataNeeded )
            CallStackContext::TraceFailure(v23, "CTranscodeDestination::HandleMetadata", 443, IsTransferMetadataNeeded);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v11 = 71;
          goto LABEL_54;
        }
      }
      goto LABEL_55;
    }
    v12 = (__int64 *)CallStackTracing::s_wpInstance;
    IsTransferMetadataNeeded = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6);
      CallStackTracing::s_wpInstance = v13;
      if ( v13 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
      {
        v12 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v12 = &qword_180069A90;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
      }
    }
    if ( *((_BYTE *)v12 + 8) )
    {
      v14 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
      if ( *((_DWORD *)v14 + 499) != -2147467261 )
        CallStackContext::TraceFailure(v14, "CTranscodeDestination::HandleMetadata", 419, -2147467261);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v11 = 70;
      goto LABEL_54;
    }
  }
  else
  {
    v8 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v9 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6);
      CallStackTracing::s_wpInstance = v9;
      if ( v9 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v9 + 8LL))(v9, 2032) )
      {
        v8 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v8 = &qword_180069A90;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
      }
    }
    if ( *((_BYTE *)v8 + 8) )
    {
      v10 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v8);
      if ( *((_DWORD *)v10 + 499) != IsTransferMetadataNeeded )
        CallStackContext::TraceFailure(v10, "CTranscodeDestination::HandleMetadata", 411, IsTransferMetadataNeeded);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v11 = 69;
LABEL_54:
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v11,
        WPP_82ede244afe43de52d63f347cb6083ad_Traceguids,
        this,
        IsTransferMetadataNeeded);
    }
  }
LABEL_55:
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v27);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>((__int64 *)&v30);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v25);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v26);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v28);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v29);
  return (unsigned int)IsTransferMetadataNeeded;
}

```

## disassembly

```asm
0x180043670  mov     [rsp-28h+arg_8], rbx
0x180043675  mov     [rsp-28h+arg_10], rsi
0x18004367a  push    rbp
0x18004367b  push    rdi
0x18004367c  push    r12
0x18004367e  push    r14
0x180043680  push    r15
0x180043682  mov     rbp, rsp
0x180043685  sub     rsp, 50h
0x180043689  mov     r14, r8
0x18004368c  lea     r12, aCtranscodedest_2; "CTranscodeDestination::HandleMetadata"
0x180043693  mov     rdi, rdx
0x180043696  mov     rsi, rcx
0x180043699  mov     rdx, r12; char *
0x18004369c  lea     rcx, [rbp+arg_0]; this
0x1800436a0  mov     r8d, 191h; int
0x1800436a6  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800436ab  xor     r15d, r15d
0x1800436ae  lea     r8, [rbp+arg_18]; struct IPropertyStore **
0x1800436b2  lea     rdx, [rbp+arg_0]; int *
0x1800436b6  mov     [rbp+var_8], r15
0x1800436ba  mov     rcx, rsi; this
0x1800436bd  mov     [rbp+var_18], r15
0x1800436c1  mov     [rbp+var_20], r15
0x1800436c5  mov     [rbp+arg_18], r15
0x1800436c9  mov     [rbp+var_10], r15
0x1800436cd  mov     [rbp+arg_0], r15d
0x1800436d1  call    ?IsTransferMetadataNeeded@CTranscodeDestination@@IEAAJPEAHPEAPEAUIPropertyStore@@@Z; CTranscodeDestination::IsTransferMetadataNeeded(int *,IPropertyStore * *)
0x1800436d6  mov     ebx, eax
0x1800436d8  test    eax, eax
0x1800436da  jns     loc_18004376B
0x1800436e0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800436e7  test    rcx, rcx
0x1800436ea  jnz     short loc_18004372D
0x1800436ec  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800436f2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800436f9  mov     rcx, rax
0x1800436fc  test    rax, rax
0x1800436ff  jz      short loc_18004371F
0x180043701  mov     rax, [rax]
0x180043704  mov     edx, 7F0h
0x180043709  mov     rax, [rax+8]
0x18004370d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043712  test    eax, eax
0x180043714  jz      short loc_18004371F
0x180043716  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004371d  jmp     short loc_18004372D
0x18004371f  lea     rcx, qword_180069A90; this
0x180043726  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004372d  cmp     [rcx+8], r15b
0x180043731  jz      short loc_180043754
0x180043733  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180043738  cmp     [rax+7CCh], ebx
0x18004373e  jz      short loc_180043754
0x180043740  mov     r9d, ebx; int
0x180043743  mov     r8d, 19Bh; int
0x180043749  mov     rdx, r12; char *
0x18004374c  mov     rcx, rax; this
0x18004374f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180043754  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180043759  cmp     al, 1
0x18004375b  jb      loc_180043A3E
0x180043761  mov     edx, 45h ; 'E'
0x180043766  jmp     loc_180043A20
0x18004376b  cmp     [rbp+arg_0], r15d
0x18004376f  jz      loc_180043A3E
0x180043775  test    rdi, rdi
0x180043778  jnz     loc_18004380E
0x18004377e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180043785  mov     ebx, 80004003h
0x18004378a  test    rcx, rcx
0x18004378d  jnz     short loc_1800437D0
0x18004378f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180043795  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004379c  mov     rcx, rax
0x18004379f  test    rax, rax
0x1800437a2  jz      short loc_1800437C2
0x1800437a4  mov     rax, [rax]
0x1800437a7  mov     edx, 7F0h
0x1800437ac  mov     rax, [rax+8]
0x1800437b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800437b5  test    eax, eax
0x1800437b7  jz      short loc_1800437C2
0x1800437b9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800437c0  jmp     short loc_1800437D0
0x1800437c2  lea     rcx, qword_180069A90; this
0x1800437c9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800437d0  cmp     [rcx+8], r15b
0x1800437d4  jz      short loc_1800437F7
0x1800437d6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800437db  cmp     [rax+7CCh], ebx
0x1800437e1  jz      short loc_1800437F7
0x1800437e3  mov     r9d, ebx; int
0x1800437e6  mov     r8d, 1A3h; int
0x1800437ec  mov     rdx, r12; char *
0x1800437ef  mov     rcx, rax; this
0x1800437f2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800437f7  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800437fc  cmp     al, 1
0x1800437fe  jb      loc_180043A3E
0x180043804  mov     edx, 46h ; 'F'
0x180043809  jmp     loc_180043A20
0x18004380e  mov     rcx, [rsi+38h]
0x180043812  lea     r8, [rbp+var_8]
0x180043816  lea     rdx, IID_IMFGetService
0x18004381d  mov     rax, [rcx]
0x180043820  mov     rax, [rax]
0x180043823  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043828  test    eax, eax
0x18004382a  js      loc_180043A3E
0x180043830  cmp     [rbp+arg_18], r15
0x180043834  jnz     short loc_180043857
0x180043836  mov     rax, [rdi]
0x180043839  lea     r8, [rbp+var_18]
0x18004383d  lea     rdx, IID_IMFGetService
0x180043844  mov     rcx, rdi
0x180043847  mov     rax, [rax]
0x18004384a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004384f  test    eax, eax
0x180043851  js      loc_180043A3E
0x180043857  mov     rcx, [rbp+var_8]
0x18004385b  lea     r9, [rbp+var_20]
0x18004385f  lea     r8, IID_IPropertyStore
0x180043866  lea     rdx, MF_PROPERTY_HANDLER_SERVICE
0x18004386d  mov     rax, [rcx]
0x180043870  mov     rax, [rax+18h]
0x180043874  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043879  test    eax, eax
0x18004387b  js      loc_180043A3E
0x180043881  mov     rcx, [rbp+arg_18]
0x180043885  test    rcx, rcx
0x180043888  jnz     loc_18004398B
0x18004388e  mov     rcx, [rbp+var_18]
0x180043892  lea     r9, [rbp+arg_18]
0x180043896  lea     r8, IID_IPropertyStore
0x18004389d  lea     rdx, MF_PROPERTY_HANDLER_SERVICE
0x1800438a4  mov     rax, [rcx]
0x1800438a7  mov     rax, [rax+18h]
0x1800438ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800438b0  test    eax, eax
0x1800438b2  jns     loc_180043987
0x1800438b8  mov     rcx, [rbp+var_18]
0x1800438bc  lea     r9, [rbp+var_10]
0x1800438c0  lea     r8, IID_IMFMetadataProvider
0x1800438c7  lea     rdx, MF_METADATA_PROVIDER_SERVICE
0x1800438ce  mov     rax, [rcx]
0x1800438d1  mov     rax, [rax+18h]
0x1800438d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800438da  test    eax, eax
0x1800438dc  js      loc_180043A3E
0x1800438e2  mov     rdx, [rbp+var_20]
0x1800438e6  mov     r8, r14
0x1800438e9  mov     rcx, [rbp+var_10]
0x1800438ed  call    ?TransferFromMetadataProviderToPropertyStore@CTranscodeMetadataHelper@@SAJPEAUIMFMetadataProvider@@PEAUIPropertyStore@@AEAV?$CTBucketHash@KUStreamSinkInfo@@@@@Z; CTranscodeMetadataHelper::TransferFromMetadataProviderToPropertyStore(IMFMetadataProvider *,IPropertyStore *,CTBucketHash<ulong,StreamSinkInfo> &)
0x1800438f2  mov     ebx, eax
0x1800438f4  test    eax, eax
0x1800438f6  jns     loc_180043A3E
0x1800438fc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180043903  test    rcx, rcx
0x180043906  jnz     short loc_180043949
0x180043908  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004390e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180043915  mov     rcx, rax
0x180043918  test    rax, rax
0x18004391b  jz      short loc_18004393B
0x18004391d  mov     rax, [rax]
0x180043920  mov     edx, 7F0h
0x180043925  mov     rax, [rax+8]
0x180043929  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004392e  test    eax, eax
0x180043930  jz      short loc_18004393B
0x180043932  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180043939  jmp     short loc_180043949
0x18004393b  lea     rcx, qword_180069A90; this
0x180043942  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180043949  cmp     [rcx+8], r15b
0x18004394d  jz      short loc_180043970
0x18004394f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180043954  cmp     [rax+7CCh], ebx
0x18004395a  jz      short loc_180043970
0x18004395c  mov     r9d, ebx; int
0x18004395f  mov     r8d, 1C3h; int
0x180043965  mov     rdx, r12; char *
0x180043968  mov     rcx, rax; this
0x18004396b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180043970  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180043975  cmp     al, 1
0x180043977  jb      loc_180043A3E
0x18004397d  mov     edx, 48h ; 'H'
0x180043982  jmp     loc_180043A20
0x180043987  mov     rcx, [rbp+arg_18]
0x18004398b  mov     rdx, [rbp+var_20]
0x18004398f  call    MFCopyPropertyStore
0x180043994  mov     ebx, eax
0x180043996  test    eax, eax
0x180043998  jns     loc_180043A3E
0x18004399e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800439a5  test    rcx, rcx
0x1800439a8  jnz     short loc_1800439EB
0x1800439aa  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800439b0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800439b7  mov     rcx, rax
0x1800439ba  test    rax, rax
0x1800439bd  jz      short loc_1800439DD
0x1800439bf  mov     rax, [rax]
0x1800439c2  mov     edx, 7F0h
0x1800439c7  mov     rax, [rax+8]
0x1800439cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800439d0  test    eax, eax
0x1800439d2  jz      short loc_1800439DD
0x1800439d4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800439db  jmp     short loc_1800439EB
0x1800439dd  lea     rcx, qword_180069A90; this
0x1800439e4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800439eb  cmp     [rcx+8], r15b
0x1800439ef  jz      short loc_180043A12
0x1800439f1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800439f6  cmp     [rax+7CCh], ebx
0x1800439fc  jz      short loc_180043A12
0x1800439fe  mov     r9d, ebx; int
0x180043a01  mov     r8d, 1BBh; int
0x180043a07  mov     rdx, r12; char *
0x180043a0a  mov     rcx, rax; this
0x180043a0d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180043a12  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180043a17  cmp     al, 1
0x180043a19  jb      short loc_180043A3E
0x180043a1b  mov     edx, 47h ; 'G'
0x180043a20  mov     rcx, cs:WPP_GLOBAL_Control
0x180043a27  lea     r8, WPP_82ede244afe43de52d63f347cb6083ad_Traceguids
0x180043a2e  mov     r9, rsi
0x180043a31  mov     [rsp+50h+var_30], ebx
0x180043a35  mov     rcx, [rcx+10h]
0x180043a39  call    WPP_SF_qd
0x180043a3e  lea     rcx, [rbp+var_10]
0x180043a42  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x180043a47  lea     rcx, [rbp+arg_18]
0x180043a4b  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x180043a50  lea     rcx, [rbp+var_20]
0x180043a54  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x180043a59  lea     rcx, [rbp+var_18]
0x180043a5d  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x180043a62  lea     rcx, [rbp+var_8]
0x180043a66  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x180043a6b  lea     rcx, [rbp+arg_0]; this
0x180043a6f  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180043a74  lea     r11, [rsp+50h+var_s0]
0x180043a79  mov     eax, ebx
0x180043a7b  mov     rbx, [r11+38h]
0x180043a7f  mov     rsi, [r11+40h]
0x180043a83  mov     rsp, r11
0x180043a86  pop     r15
0x180043a88  pop     r14
0x180043a8a  pop     r12
0x180043a8c  pop     rdi
0x180043a8d  pop     rbp
0x180043a8e  retn
```
