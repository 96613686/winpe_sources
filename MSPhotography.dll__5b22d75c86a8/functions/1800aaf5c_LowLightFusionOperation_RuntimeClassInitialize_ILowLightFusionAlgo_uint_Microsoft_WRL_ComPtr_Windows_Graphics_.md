# LowLightFusionOperation::RuntimeClassInitialize(ILowLightFusionAlgo *,uint,Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap> const *,Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap> const *)

- ea: `0x1800aaf5c`
- end: `0x1800ab3c5`
- name: `?RuntimeClassInitialize@LowLightFusionOperation@@QEAAJPEAUILowLightFusionAlgo@@IPEBV?$ComPtr@UISoftwareBitmap@Imaging@Graphics@Windows@@@WRL@Microsoft@@1@Z`
- size: `1129`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800a49e0`

## callees

- `0x180002420`
- `0x180005660`
- `0x18000b490`
- `0x18000c0f8`
- `0x18001171c`
- `0x18002a9bc`
- `0x18002ae0c`
- `0x18002afd0`
- `0x18002bb98`
- `0x18002cc6c`
- `0x1800a9158`
- `0x1800aaf5c`
- `0x1800ab3d0`
- `0x18012f850`
- `0x180142010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ab095`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ab16d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ab241`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ab2de`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ab095`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ab16d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ab241`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ab2de`

## string_xrefs

- `0x1800ab131`: `Windows.System.Threading.ThreadPool`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall LowLightFusionOperation::RuntimeClassInitialize(
        __int64 a1,
        __int64 a2,
        int a3,
        __int64 a4,
        __int64 a5)
{
  int v9; // edi
  __int64 v10; // rcx
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
  struct CallStackContext *v22; // rax
  __int64 *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  unsigned int v26; // ebx
  int v28; // [rsp+30h] [rbp-31h] BYREF
  _BYTE v29[4]; // [rsp+34h] [rbp-2Dh] BYREF
  __int64 v30; // [rsp+38h] [rbp-29h] BYREF
  __int64 v31; // [rsp+40h] [rbp-21h] BYREF
  _QWORD v32[3]; // [rsp+48h] [rbp-19h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp-1h] BYREF
  __int64 v34; // [rsp+78h] [rbp+17h]

  v28 = 0;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v29,
    "LowLightFusionOperation::RuntimeClassInitialize",
    48);
  v32[1] = a1;
  v32[2] = &v28;
  v31 = 0;
  v30 = 0;
  if ( *(_QWORD *)(a1 + 216) != a2 )
  {
    if ( a2 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 8LL))(a2);
    v32[0] = *(_QWORD *)(a1 + 216);
    *(_QWORD *)(a1 + 216) = a2;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v32);
  }
  *(_DWORD *)(a1 + 256) = a3;
  if ( a3 == 1 )
  {
    v9 = 0;
    v10 = a1 + 224;
  }
  else
  {
    if ( a3 != 2 )
    {
      v28 = -2147418113;
      v23 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v24;
        if ( v24 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
        {
          v23 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v23 = &qword_18015FF10;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18015FF10;
        }
      }
      if ( *((_BYTE *)v23 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
        if ( v28 < 0 && *((_DWORD *)ThreadRelativeContext + 499) != v28 )
          CallStackContext::TraceFailure(
            ThreadRelativeContext,
            "LowLightFusionOperation::RuntimeClassInitialize",
            77,
            v28);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v14 = 11;
        goto LABEL_56;
      }
      goto LABEL_57;
    }
    Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>::operator=(a1 + 224, a4);
    Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>::operator=(a1 + 232, a4 + 8);
    Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>::operator=(a1 + 240, a5);
    v9 = 1;
    v10 = a1 + 248;
    a4 = a5 + 8;
  }
  Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>::operator=(v10, a4);
  *(_DWORD *)(a1 + 260) = v9;
  v28 = Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Media::Core::LowLightFusionResult *,double>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::Start(a1 + 24);
  if ( v28 >= 0 )
  {
    v34 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.System.Threading.ThreadPool",
      0x24u,
      0x23u);
    v28 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::System::Threading::IThreadPoolStatics>>(
            v34,
            &v30);
    if ( v28 >= 0 )
    {
      v18 = v30;
      v19 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v30 + 48LL);
      Microsoft::WRL::ComPtr<IMFVideoProcessorControl>::InternalRelease(&v31);
      v28 = v19(v18, (a1 + 16) & -(__int64)(a1 != 0), &v31);
      if ( v28 < 0 )
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
          v22 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
          if ( v28 < 0 && *((_DWORD *)v22 + 499) != v28 )
            CallStackContext::TraceFailure(v22, "LowLightFusionOperation::RuntimeClassInitialize", 87, v28);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v14 = 14;
          goto LABEL_56;
        }
      }
    }
    else
    {
      v34 = 0;
      v15 = (__int64 *)CallStackTracing::s_wpInstance;
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
        if ( v28 < 0 && *((_DWORD *)v17 + 499) != v28 )
          CallStackContext::TraceFailure(v17, "LowLightFusionOperation::RuntimeClassInitialize", 86, v28);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v14 = 13;
        goto LABEL_56;
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
      if ( v28 < 0 && *((_DWORD *)v13 + 499) != v28 )
        CallStackContext::TraceFailure(v13, "LowLightFusionOperation::RuntimeClassInitialize", 84, v28);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v14 = 12;
LABEL_56:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, &WPP_0acac61da4473a1de7b74d610951a400_Traceguids, a1, v28);
    }
  }
LABEL_57:
  v26 = v28;
  Microsoft::WRL::ComPtr<IMFVideoProcessorControl>::InternalRelease(&v30);
  Microsoft::WRL::ComPtr<IMFVideoProcessorControl>::InternalRelease(&v31);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v29);
  return v26;
}

```

## disassembly

```asm
0x1800aaf5c  mov     [rsp-8+arg_8], rbx
0x1800aaf61  push    rbp
0x1800aaf62  push    rsi
0x1800aaf63  push    rdi
0x1800aaf64  push    r14
0x1800aaf66  push    r15
0x1800aaf68  lea     rbp, [rsp-2Fh]
0x1800aaf6d  sub     rsp, 90h
0x1800aaf74  mov     rax, cs:__security_cookie
0x1800aaf7b  xor     rax, rsp
0x1800aaf7e  mov     [rbp+4Fh+var_30], rax
0x1800aaf82  mov     r15, r9
0x1800aaf85  mov     edi, r8d
0x1800aaf88  mov     rbx, rdx
0x1800aaf8b  mov     rsi, rcx
0x1800aaf8e  mov     r14, [rbp+4Fh+arg_20]
0x1800aaf92  mov     [rbp+4Fh+var_80], 0
0x1800aaf99  mov     r8d, 30h ; '0'; int
0x1800aaf9f  lea     rdx, aLowlightfusion_0; "LowLightFusionOperation::RuntimeClassIn"...
0x1800aafa6  lea     rcx, [rbp+4Fh+var_7C]; this
0x1800aafaa  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800aafaf  nop
0x1800aafb0  mov     [rbp+4Fh+var_60], rsi
0x1800aafb4  lea     rax, [rbp+4Fh+var_80]
0x1800aafb8  mov     [rbp+4Fh+var_58], rax
0x1800aafbc  mov     [rbp+4Fh+var_70], 0
0x1800aafc4  mov     [rbp+4Fh+var_78], 0
0x1800aafcc  cmp     [rsi+0D8h], rbx
0x1800aafd3  jz      short loc_1800AB005
0x1800aafd5  test    rbx, rbx
0x1800aafd8  jz      short loc_1800AAFEA
0x1800aafda  mov     rax, [rbx]
0x1800aafdd  mov     rcx, rbx
0x1800aafe0  mov     rax, [rax+8]
0x1800aafe4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aafe9  nop
0x1800aafea  mov     rax, [rsi+0D8h]
0x1800aaff1  mov     [rbp+4Fh+var_68], rax
0x1800aaff5  mov     [rsi+0D8h], rbx
0x1800aaffc  lea     rcx, [rbp+4Fh+var_68]
0x1800ab000  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800ab005  mov     [rsi+100h], edi
0x1800ab00b  cmp     edi, 1
0x1800ab00e  jnz     short loc_1800AB01B
0x1800ab010  xor     edi, edi
0x1800ab012  lea     rcx, [rsi+0E0h]
0x1800ab019  jmp     short loc_1800AB062
0x1800ab01b  cmp     edi, 2
0x1800ab01e  jnz     loc_1800AB2CB
0x1800ab024  lea     rbx, [rsi+0E0h]
0x1800ab02b  mov     rdx, r15
0x1800ab02e  mov     rcx, rbx
0x1800ab031  call    ??4?$ComPtr@UISoftwareBitmap@Imaging@Graphics@Windows@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>::operator=(Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap> const &)
0x1800ab036  lea     rdx, [r15+8]
0x1800ab03a  lea     rcx, [rbx+8]
0x1800ab03e  call    ??4?$ComPtr@UISoftwareBitmap@Imaging@Graphics@Windows@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>::operator=(Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap> const &)
0x1800ab043  lea     rbx, [rsi+0F0h]
0x1800ab04a  mov     rdx, r14
0x1800ab04d  mov     rcx, rbx
0x1800ab050  call    ??4?$ComPtr@UISoftwareBitmap@Imaging@Graphics@Windows@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>::operator=(Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap> const &)
0x1800ab055  mov     edi, 1
0x1800ab05a  lea     rcx, [rbx+8]
0x1800ab05e  lea     r15, [r14+8]
0x1800ab062  mov     ebx, 104h
0x1800ab067  mov     r14, rsi
0x1800ab06a  mov     rdx, r15
0x1800ab06d  call    ??4?$ComPtr@UISoftwareBitmap@Imaging@Graphics@Windows@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>::operator=(Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap> const &)
0x1800ab072  mov     [rsi+rbx], edi
0x1800ab075  lea     rcx, [rsi+18h]
0x1800ab079  call    ?Start@?$AsyncBase@U?$IAsyncOperationWithProgressCompletedHandler@PEAVLowLightFusionResult@Core@Media@Windows@@N@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@MEAAJXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Media::Core::LowLightFusionResult *,double>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::Start(void)
0x1800ab07e  mov     [rbp+4Fh+var_80], eax
0x1800ab081  test    eax, eax
0x1800ab083  jns     loc_1800AB11F
0x1800ab089  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ab090  test    rcx, rcx
0x1800ab093  jnz     short loc_1800AB0D6
0x1800ab095  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800ab09b  mov     rcx, rax
0x1800ab09e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ab0a5  test    rax, rax
0x1800ab0a8  jz      short loc_1800AB0C8
0x1800ab0aa  mov     rax, [rax]
0x1800ab0ad  mov     edx, 7F0h
0x1800ab0b2  mov     rax, [rax+8]
0x1800ab0b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab0bb  test    eax, eax
0x1800ab0bd  jz      short loc_1800AB0C8
0x1800ab0bf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ab0c6  jmp     short loc_1800AB0D6
0x1800ab0c8  lea     rcx, qword_18015FF10; this
0x1800ab0cf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ab0d6  cmp     byte ptr [rcx+8], 0
0x1800ab0da  jz      short loc_1800AB108
0x1800ab0dc  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ab0e1  mov     r9d, [rbp+4Fh+var_80]; int
0x1800ab0e5  test    r9d, r9d
0x1800ab0e8  jns     short loc_1800AB108
0x1800ab0ea  cmp     [rax+7CCh], r9d
0x1800ab0f1  jz      short loc_1800AB108
0x1800ab0f3  mov     r8d, 54h ; 'T'; int
0x1800ab0f9  lea     rdx, aLowlightfusion_0; "LowLightFusionOperation::RuntimeClassIn"...
0x1800ab100  mov     rcx, rax; this
0x1800ab103  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ab108  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800ab10d  cmp     al, 1
0x1800ab10f  jb      loc_1800AB380
0x1800ab115  mov     edx, 0Ch
0x1800ab11a  jmp     loc_1800AB35F
0x1800ab11f  mov     [rbp+4Fh+var_38], 0
0x1800ab127  mov     r9d, 23h ; '#'; unsigned int
0x1800ab12d  lea     r8d, [r9+1]; unsigned int
0x1800ab131  lea     rdx, ?RuntimeClass_Windows_System_Threading_ThreadPool@@3QBGB; "Windows.System.Threading.ThreadPool"
0x1800ab138  lea     rcx, [rbp+4Fh+hstringHeader]; hstringHeader
0x1800ab13c  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800ab141  lea     rdx, [rbp+4Fh+var_78]
0x1800ab145  mov     rcx, [rbp+4Fh+var_38]
0x1800ab149  call    ??$GetActivationFactory@V?$ComPtr@UIThreadPoolStatics@Threading@System@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIThreadPoolStatics@Threading@System@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::System::Threading::IThreadPoolStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Threading::IThreadPoolStatics>>)
0x1800ab14e  mov     [rbp+4Fh+var_80], eax
0x1800ab151  test    eax, eax
0x1800ab153  jns     loc_1800AB1F7
0x1800ab159  mov     [rbp+4Fh+var_38], 0
0x1800ab161  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ab168  test    rcx, rcx
0x1800ab16b  jnz     short loc_1800AB1AE
0x1800ab16d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800ab173  mov     rcx, rax
0x1800ab176  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ab17d  test    rax, rax
0x1800ab180  jz      short loc_1800AB1A0
0x1800ab182  mov     rax, [rax]
0x1800ab185  mov     edx, 7F0h
0x1800ab18a  mov     rax, [rax+8]
0x1800ab18e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab193  test    eax, eax
0x1800ab195  jz      short loc_1800AB1A0
0x1800ab197  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ab19e  jmp     short loc_1800AB1AE
0x1800ab1a0  lea     rcx, qword_18015FF10; this
0x1800ab1a7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ab1ae  cmp     byte ptr [rcx+8], 0
0x1800ab1b2  jz      short loc_1800AB1E0
0x1800ab1b4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ab1b9  mov     r9d, [rbp+4Fh+var_80]; int
0x1800ab1bd  test    r9d, r9d
0x1800ab1c0  jns     short loc_1800AB1E0
0x1800ab1c2  cmp     [rax+7CCh], r9d
0x1800ab1c9  jz      short loc_1800AB1E0
0x1800ab1cb  mov     r8d, 56h ; 'V'; int
0x1800ab1d1  lea     rdx, aLowlightfusion_0; "LowLightFusionOperation::RuntimeClassIn"...
0x1800ab1d8  mov     rcx, rax; this
0x1800ab1db  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ab1e0  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800ab1e5  cmp     al, 1
0x1800ab1e7  jb      loc_1800AB380
0x1800ab1ed  mov     edx, 0Dh
0x1800ab1f2  jmp     loc_1800AB35F
0x1800ab1f7  mov     rdi, [rbp+4Fh+var_78]
0x1800ab1fb  mov     rax, [rdi]
0x1800ab1fe  mov     rbx, [rax+30h]
0x1800ab202  lea     rcx, [rbp+4Fh+var_70]
0x1800ab206  call    ?InternalRelease@?$ComPtr@UIMFVideoProcessorControl@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFVideoProcessorControl>::InternalRelease(void)
0x1800ab20b  mov     rdx, rsi
0x1800ab20e  lea     r8, [rsi+10h]
0x1800ab212  neg     rdx
0x1800ab215  sbb     rdx, rdx
0x1800ab218  and     rdx, r8
0x1800ab21b  lea     r8, [rbp+4Fh+var_70]
0x1800ab21f  mov     rcx, rdi
0x1800ab222  mov     rax, rbx
0x1800ab225  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab22a  mov     [rbp+4Fh+var_80], eax
0x1800ab22d  test    eax, eax
0x1800ab22f  jns     loc_1800AB380
0x1800ab235  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ab23c  test    rcx, rcx
0x1800ab23f  jnz     short loc_1800AB282
0x1800ab241  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800ab247  mov     rcx, rax
0x1800ab24a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ab251  test    rax, rax
0x1800ab254  jz      short loc_1800AB274
0x1800ab256  mov     rax, [rax]
0x1800ab259  mov     edx, 7F0h
0x1800ab25e  mov     rax, [rax+8]
0x1800ab262  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab267  test    eax, eax
0x1800ab269  jz      short loc_1800AB274
0x1800ab26b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ab272  jmp     short loc_1800AB282
0x1800ab274  lea     rcx, qword_18015FF10; this
0x1800ab27b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ab282  cmp     byte ptr [rcx+8], 0
0x1800ab286  jz      short loc_1800AB2B4
0x1800ab288  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ab28d  mov     r9d, [rbp+4Fh+var_80]; int
0x1800ab291  test    r9d, r9d
0x1800ab294  jns     short loc_1800AB2B4
0x1800ab296  cmp     [rax+7CCh], r9d
0x1800ab29d  jz      short loc_1800AB2B4
0x1800ab29f  mov     r8d, 57h ; 'W'; int
0x1800ab2a5  lea     rdx, aLowlightfusion_0; "LowLightFusionOperation::RuntimeClassIn"...
0x1800ab2ac  mov     rcx, rax; this
0x1800ab2af  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ab2b4  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800ab2b9  cmp     al, 1
0x1800ab2bb  jb      loc_1800AB380
0x1800ab2c1  mov     edx, 0Eh
0x1800ab2c6  jmp     loc_1800AB35F
0x1800ab2cb  mov     [rbp+4Fh+var_80], 8000FFFFh
0x1800ab2d2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ab2d9  test    rcx, rcx
0x1800ab2dc  jnz     short loc_1800AB31F
0x1800ab2de  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800ab2e4  mov     rcx, rax
0x1800ab2e7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ab2ee  test    rax, rax
0x1800ab2f1  jz      short loc_1800AB311
0x1800ab2f3  mov     rax, [rax]
0x1800ab2f6  mov     edx, 7F0h
0x1800ab2fb  mov     rax, [rax+8]
0x1800ab2ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab304  test    eax, eax
0x1800ab306  jz      short loc_1800AB311
0x1800ab308  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ab30f  jmp     short loc_1800AB31F
0x1800ab311  lea     rcx, qword_18015FF10; this
0x1800ab318  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ab31f  cmp     byte ptr [rcx+8], 0
0x1800ab323  jz      short loc_1800AB351
0x1800ab325  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ab32a  mov     r9d, [rbp+4Fh+var_80]; int
0x1800ab32e  test    r9d, r9d
0x1800ab331  jns     short loc_1800AB351
0x1800ab333  cmp     [rax+7CCh], r9d
0x1800ab33a  jz      short loc_1800AB351
0x1800ab33c  mov     r8d, 4Dh ; 'M'; int
0x1800ab342  lea     rdx, aLowlightfusion_0; "LowLightFusionOperation::RuntimeClassIn"...
0x1800ab349  mov     rcx, rax; this
0x1800ab34c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ab351  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800ab356  cmp     al, 1
0x1800ab358  jb      short loc_1800AB380
0x1800ab35a  mov     edx, 0Bh
0x1800ab35f  mov     eax, [rbp+4Fh+var_80]
0x1800ab362  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ab369  mov     [rsp+0B0h+var_90], eax
0x1800ab36d  mov     r9, rsi
0x1800ab370  lea     r8, WPP_0acac61da4473a1de7b74d610951a400_Traceguids
0x1800ab377  mov     rcx, [rcx+10h]
0x1800ab37b  call    WPP_SF_qD
0x1800ab380  mov     ebx, [rbp+4Fh+var_80]
0x1800ab383  lea     rcx, [rbp+4Fh+var_78]
0x1800ab387  call    ?InternalRelease@?$ComPtr@UIMFVideoProcessorControl@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFVideoProcessorControl>::InternalRelease(void)
0x1800ab38c  nop
0x1800ab38d  lea     rcx, [rbp+4Fh+var_70]
0x1800ab391  call    ?InternalRelease@?$ComPtr@UIMFVideoProcessorControl@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFVideoProcessorControl>::InternalRelease(void)
0x1800ab396  nop
0x1800ab397  lea     rcx, [rbp+4Fh+var_7C]; this
0x1800ab39b  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800ab3a0  mov     eax, ebx
0x1800ab3a2  mov     rcx, [rbp+4Fh+var_30]
0x1800ab3a6  xor     rcx, rsp; StackCookie
0x1800ab3a9  call    __security_check_cookie
0x1800ab3ae  mov     rbx, [rsp+0B0h+arg_8]
0x1800ab3b6  add     rsp, 90h
0x1800ab3bd  pop     r15
0x1800ab3bf  pop     r14
0x1800ab3c1  pop     rdi
0x1800ab3c2  pop     rsi
0x1800ab3c3  pop     rbp
0x1800ab3c4  retn
```
