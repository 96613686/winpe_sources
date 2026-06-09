# FuseOperation::RuntimeClassInitialize(IHdrFusion *,uint,Microsoft::WRL::ComPtr<ExposureCompensatedFrame> const *)

- ea: `0x18002f56c`
- end: `0x18002f8de`
- name: `?RuntimeClassInitialize@FuseOperation@@QEAAJPEAUIHdrFusion@@IPEBV?$ComPtr@VExposureCompensatedFrame@@@WRL@Microsoft@@@Z`
- size: `882`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002accc`

## callees

- `0x180002420`
- `0x18000b490`
- `0x18000c0f8`
- `0x18001171c`
- `0x18002a9bc`
- `0x18002ae0c`
- `0x18002afd0`
- `0x18002bb50`
- `0x18002bb98`
- `0x18002bbc4`
- `0x18002cc6c`
- `0x18002f56c`
- `0x18002f8f0`
- `0x18012f850`
- `0x180142010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002f669`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002f739`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002f805`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002f669`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002f739`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002f805`

## string_xrefs

- `0x18002f6fa`: `Windows.System.Threading.ThreadPool`

## pseudocode

```c
__int64 __fastcall FuseOperation::RuntimeClassInitialize(__int64 a1, __int64 a2, int a3, __int64 a4)
{
  __int64 v8; // rbx
  __int64 v9; // rdi
  int v10; // ebx
  __int64 *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *v13; // rax
  __int64 v14; // rdx
  __int64 *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, __int64, __int64 *); // rbx
  __int64 *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  _BYTE v24[8]; // [rsp+30h] [rbp-50h] BYREF
  __int64 v25; // [rsp+38h] [rbp-48h] BYREF
  __int64 v26; // [rsp+40h] [rbp-40h] BYREF
  __int64 v27; // [rsp+48h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-30h] BYREF
  __int64 v29; // [rsp+68h] [rbp-18h]

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v24, "FuseOperation::RuntimeClassInitialize", 45);
  v27 = 0;
  v26 = 0;
  if ( *(_QWORD *)(a1 + 216) != a2 )
  {
    if ( a2 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 8LL))(a2);
    v25 = *(_QWORD *)(a1 + 216);
    *(_QWORD *)(a1 + 216) = a2;
    Microsoft::WRL::ComPtr<IMFVideoProcessorControl>::InternalRelease(&v25);
  }
  v8 = 0;
  for ( *(_DWORD *)(a1 + 248) = a3; (unsigned int)v8 < *(_DWORD *)(a1 + 248); v8 = (unsigned int)(v8 + 1) )
  {
    v9 = *(_QWORD *)(a4 + 8 * v8);
    if ( *(_QWORD *)(a1 + 8 * v8 + 224) != v9 )
    {
      v25 = *(_QWORD *)(a4 + 8 * v8);
      Microsoft::WRL::ComPtr<ExposureCompensatedFrame>::InternalAddRef(&v25);
      v25 = *(_QWORD *)(a1 + 8 * v8 + 224);
      *(_QWORD *)(a1 + 8 * v8 + 224) = v9;
      Microsoft::WRL::ComPtr<ExposureCompensatedFrame>::InternalRelease(&v25);
    }
  }
  v10 = Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Graphics::Imaging::Internal::HighDynamicRangeResult *,double>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::Start(a1 + 24);
  if ( v10 >= 0 )
  {
    v29 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.System.Threading.ThreadPool",
      0x24u,
      0x23u);
    v10 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::System::Threading::IThreadPoolStatics>>(
            v29,
            &v26);
    if ( v10 >= 0 )
    {
      v18 = v26;
      v19 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v26 + 48LL);
      Microsoft::WRL::ComPtr<IMFVideoProcessorControl>::InternalRelease(&v27);
      v10 = v19(v18, (a1 + 16) & -(__int64)(a1 != 0), &v27);
      if ( v10 < 0 )
      {
        v20 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
          CallStackTracing::s_wpInstance = v21;
          if ( v21 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
          {
            v20 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v20 = &qword_18015FF10;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18015FF10;
          }
        }
        if ( *((_BYTE *)v20 + 8) )
        {
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
          if ( *((_DWORD *)ThreadRelativeContext + 499) != v10 )
            CallStackContext::TraceFailure(ThreadRelativeContext, "FuseOperation::RuntimeClassInitialize", 70, v10);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v14 = 13;
          goto LABEL_42;
        }
      }
    }
    else
    {
      v15 = (__int64 *)CallStackTracing::s_wpInstance;
      v29 = 0;
      if ( !CallStackTracing::s_wpInstance )
      {
        v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v16;
        if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
        {
          v15 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v15 = &qword_18015FF10;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18015FF10;
        }
      }
      if ( *((_BYTE *)v15 + 8) )
      {
        v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
        if ( *((_DWORD *)v17 + 499) != v10 )
          CallStackContext::TraceFailure(v17, "FuseOperation::RuntimeClassInitialize", 69, v10);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v14 = 12;
        goto LABEL_42;
      }
    }
  }
  else
  {
    v11 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v12;
      if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
      {
        v11 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v11 = &qword_18015FF10;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18015FF10;
      }
    }
    if ( *((_BYTE *)v11 + 8) )
    {
      v13 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
      if ( *((_DWORD *)v13 + 499) != v10 )
        CallStackContext::TraceFailure(v13, "FuseOperation::RuntimeClassInitialize", 67, v10);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v14 = 11;
LABEL_42:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, &WPP_2a0cc8ddad0832ea6177204d38491785_Traceguids, a1, v10);
    }
  }
  Microsoft::WRL::ComPtr<IMFVideoProcessorControl>::InternalRelease(&v26);
  Microsoft::WRL::ComPtr<IMFVideoProcessorControl>::InternalRelease(&v27);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v24);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18002f56c  mov     [rsp-18h+arg_8], rbx
0x18002f571  mov     [rsp-18h+arg_10], rsi
0x18002f576  push    rbp
0x18002f577  push    rdi
0x18002f578  push    r14
0x18002f57a  mov     rbp, rsp
0x18002f57d  sub     rsp, 80h
0x18002f584  mov     rax, cs:__security_cookie
0x18002f58b  xor     rax, rsp
0x18002f58e  mov     [rbp+var_10], rax
0x18002f592  mov     edi, r8d
0x18002f595  mov     rbx, rdx
0x18002f598  mov     rsi, rcx
0x18002f59b  lea     rdx, aFuseoperationR; "FuseOperation::RuntimeClassInitialize"
0x18002f5a2  mov     r8d, 2Dh ; '-'; int
0x18002f5a8  lea     rcx, [rbp+var_50]; this
0x18002f5ac  mov     r14, r9
0x18002f5af  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18002f5b4  mov     [rbp+var_38], 0
0x18002f5bc  mov     [rbp+var_40], 0
0x18002f5c4  cmp     [rsi+0D8h], rbx
0x18002f5cb  jz      short loc_18002F5FC
0x18002f5cd  test    rbx, rbx
0x18002f5d0  jz      short loc_18002F5E1
0x18002f5d2  mov     rax, [rbx]
0x18002f5d5  mov     rcx, rbx
0x18002f5d8  mov     rax, [rax+8]
0x18002f5dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f5e1  mov     rax, [rsi+0D8h]
0x18002f5e8  lea     rcx, [rbp+var_48]
0x18002f5ec  mov     [rbp+var_48], rax
0x18002f5f0  mov     [rsi+0D8h], rbx
0x18002f5f7  call    ?InternalRelease@?$ComPtr@UIMFVideoProcessorControl@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFVideoProcessorControl>::InternalRelease(void)
0x18002f5fc  xor     ebx, ebx
0x18002f5fe  mov     [rsi+0F8h], edi
0x18002f604  test    edi, edi
0x18002f606  jz      short loc_18002F64A
0x18002f608  mov     rdi, [r14+rbx*8]
0x18002f60c  cmp     [rsi+rbx*8+0E0h], rdi
0x18002f614  jz      short loc_18002F640
0x18002f616  lea     rcx, [rbp+var_48]
0x18002f61a  mov     [rbp+var_48], rdi
0x18002f61e  call    ?InternalAddRef@?$ComPtr@VExposureCompensatedFrame@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<ExposureCompensatedFrame>::InternalAddRef(void)
0x18002f623  mov     r10, [rsi+rbx*8+0E0h]
0x18002f62b  lea     rcx, [rbp+var_48]
0x18002f62f  mov     [rbp+var_48], r10
0x18002f633  mov     [rsi+rbx*8+0E0h], rdi
0x18002f63b  call    ?InternalRelease@?$ComPtr@VExposureCompensatedFrame@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ExposureCompensatedFrame>::InternalRelease(void)
0x18002f640  inc     ebx
0x18002f642  cmp     ebx, [rsi+0F8h]
0x18002f648  jb      short loc_18002F608
0x18002f64a  lea     rcx, [rsi+18h]
0x18002f64e  call    ?Start@?$AsyncBase@U?$IAsyncOperationWithProgressCompletedHandler@PEAVHighDynamicRangeResult@Internal@Imaging@Graphics@Windows@@N@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@MEAAJXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Graphics::Imaging::Internal::HighDynamicRangeResult *,double>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::Start(void)
0x18002f653  mov     ebx, eax
0x18002f655  test    eax, eax
0x18002f657  jns     loc_18002F6EC
0x18002f65d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002f664  test    rcx, rcx
0x18002f667  jnz     short loc_18002F6AA
0x18002f669  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002f66f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002f676  mov     rcx, rax
0x18002f679  test    rax, rax
0x18002f67c  jz      short loc_18002F69C
0x18002f67e  mov     rax, [rax]
0x18002f681  mov     edx, 7F0h
0x18002f686  mov     rax, [rax+8]
0x18002f68a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f68f  test    eax, eax
0x18002f691  jz      short loc_18002F69C
0x18002f693  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002f69a  jmp     short loc_18002F6AA
0x18002f69c  lea     rcx, qword_18015FF10; this
0x18002f6a3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002f6aa  cmp     byte ptr [rcx+8], 0
0x18002f6ae  jz      short loc_18002F6D5
0x18002f6b0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002f6b5  cmp     [rax+7CCh], ebx
0x18002f6bb  jz      short loc_18002F6D5
0x18002f6bd  mov     r9d, ebx; int
0x18002f6c0  lea     rdx, aFuseoperationR; "FuseOperation::RuntimeClassInitialize"
0x18002f6c7  mov     r8d, 43h ; 'C'; int
0x18002f6cd  mov     rcx, rax; this
0x18002f6d0  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002f6d5  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002f6da  cmp     al, 1
0x18002f6dc  jb      loc_18002F89D
0x18002f6e2  mov     edx, 0Bh
0x18002f6e7  jmp     loc_18002F87F
0x18002f6ec  mov     r9d, 23h ; '#'; unsigned int
0x18002f6f2  mov     [rbp+var_18], 0
0x18002f6fa  lea     rdx, ?RuntimeClass_Windows_System_Threading_ThreadPool@@3QBGB; "Windows.System.Threading.ThreadPool"
0x18002f701  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x18002f705  lea     r8d, [r9+1]; unsigned int
0x18002f709  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18002f70e  mov     rcx, [rbp+var_18]
0x18002f712  lea     rdx, [rbp+var_40]
0x18002f716  call    ??$GetActivationFactory@V?$ComPtr@UIThreadPoolStatics@Threading@System@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIThreadPoolStatics@Threading@System@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::System::Threading::IThreadPoolStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Threading::IThreadPoolStatics>>)
0x18002f71b  mov     ebx, eax
0x18002f71d  test    eax, eax
0x18002f71f  jns     loc_18002F7BC
0x18002f725  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002f72c  mov     [rbp+var_18], 0
0x18002f734  test    rcx, rcx
0x18002f737  jnz     short loc_18002F77A
0x18002f739  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002f73f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002f746  mov     rcx, rax
0x18002f749  test    rax, rax
0x18002f74c  jz      short loc_18002F76C
0x18002f74e  mov     rax, [rax]
0x18002f751  mov     edx, 7F0h
0x18002f756  mov     rax, [rax+8]
0x18002f75a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f75f  test    eax, eax
0x18002f761  jz      short loc_18002F76C
0x18002f763  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002f76a  jmp     short loc_18002F77A
0x18002f76c  lea     rcx, qword_18015FF10; this
0x18002f773  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002f77a  cmp     byte ptr [rcx+8], 0
0x18002f77e  jz      short loc_18002F7A5
0x18002f780  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002f785  cmp     [rax+7CCh], ebx
0x18002f78b  jz      short loc_18002F7A5
0x18002f78d  mov     r9d, ebx; int
0x18002f790  lea     rdx, aFuseoperationR; "FuseOperation::RuntimeClassInitialize"
0x18002f797  mov     r8d, 45h ; 'E'; int
0x18002f79d  mov     rcx, rax; this
0x18002f7a0  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002f7a5  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002f7aa  cmp     al, 1
0x18002f7ac  jb      loc_18002F89D
0x18002f7b2  mov     edx, 0Ch
0x18002f7b7  jmp     loc_18002F87F
0x18002f7bc  mov     rdi, [rbp+var_40]
0x18002f7c0  lea     rcx, [rbp+var_38]
0x18002f7c4  mov     rax, [rdi]
0x18002f7c7  mov     rbx, [rax+30h]
0x18002f7cb  call    ?InternalRelease@?$ComPtr@UIMFVideoProcessorControl@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFVideoProcessorControl>::InternalRelease(void)
0x18002f7d0  lea     r8, [rsi+10h]
0x18002f7d4  mov     rdx, rsi
0x18002f7d7  neg     rdx
0x18002f7da  mov     rcx, rdi
0x18002f7dd  mov     rax, rbx
0x18002f7e0  sbb     rdx, rdx
0x18002f7e3  and     rdx, r8
0x18002f7e6  lea     r8, [rbp+var_38]
0x18002f7ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f7ef  mov     ebx, eax
0x18002f7f1  test    eax, eax
0x18002f7f3  jns     loc_18002F89D
0x18002f7f9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002f800  test    rcx, rcx
0x18002f803  jnz     short loc_18002F846
0x18002f805  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002f80b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002f812  mov     rcx, rax
0x18002f815  test    rax, rax
0x18002f818  jz      short loc_18002F838
0x18002f81a  mov     rax, [rax]
0x18002f81d  mov     edx, 7F0h
0x18002f822  mov     rax, [rax+8]
0x18002f826  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f82b  test    eax, eax
0x18002f82d  jz      short loc_18002F838
0x18002f82f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002f836  jmp     short loc_18002F846
0x18002f838  lea     rcx, qword_18015FF10; this
0x18002f83f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002f846  cmp     byte ptr [rcx+8], 0
0x18002f84a  jz      short loc_18002F871
0x18002f84c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002f851  cmp     [rax+7CCh], ebx
0x18002f857  jz      short loc_18002F871
0x18002f859  mov     r9d, ebx; int
0x18002f85c  lea     rdx, aFuseoperationR; "FuseOperation::RuntimeClassInitialize"
0x18002f863  mov     r8d, 46h ; 'F'; int
0x18002f869  mov     rcx, rax; this
0x18002f86c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002f871  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002f876  cmp     al, 1
0x18002f878  jb      short loc_18002F89D
0x18002f87a  mov     edx, 0Dh
0x18002f87f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f886  lea     r8, WPP_2a0cc8ddad0832ea6177204d38491785_Traceguids
0x18002f88d  mov     r9, rsi
0x18002f890  mov     [rsp+80h+var_60], ebx
0x18002f894  mov     rcx, [rcx+10h]
0x18002f898  call    WPP_SF_qD
0x18002f89d  lea     rcx, [rbp+var_40]
0x18002f8a1  call    ?InternalRelease@?$ComPtr@UIMFVideoProcessorControl@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFVideoProcessorControl>::InternalRelease(void)
0x18002f8a6  lea     rcx, [rbp+var_38]
0x18002f8aa  call    ?InternalRelease@?$ComPtr@UIMFVideoProcessorControl@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFVideoProcessorControl>::InternalRelease(void)
0x18002f8af  lea     rcx, [rbp+var_50]; this
0x18002f8b3  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18002f8b8  mov     eax, ebx
0x18002f8ba  mov     rcx, [rbp+var_10]
0x18002f8be  xor     rcx, rsp; StackCookie
0x18002f8c1  call    __security_check_cookie
0x18002f8c6  lea     r11, [rsp+80h+var_s0]
0x18002f8ce  mov     rbx, [r11+28h]
0x18002f8d2  mov     rsi, [r11+30h]
0x18002f8d6  mov     rsp, r11
0x18002f8d9  pop     r14
0x18002f8db  pop     rdi
0x18002f8dc  pop     rbp
0x18002f8dd  retn
```
