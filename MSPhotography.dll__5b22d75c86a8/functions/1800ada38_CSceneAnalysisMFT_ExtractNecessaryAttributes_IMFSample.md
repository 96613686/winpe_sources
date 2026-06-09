# CSceneAnalysisMFT::ExtractNecessaryAttributes(IMFSample *)

- ea: `0x1800ada38`
- end: `0x1800addbf`
- name: `?ExtractNecessaryAttributes@CSceneAnalysisMFT@@AEAAJPEAUIMFSample@@@Z`
- size: `903`
- prototype: `__int64 __fastcall(CSceneAnalysisMFT *__hidden this, struct IMFSample *)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800b00f0`

## callees

- `0x180002420`
- `0x180005660`
- `0x18000b490`
- `0x18000c0f8`
- `0x18002a9bc`
- `0x18002ae0c`
- `0x18002afd0`
- `0x18002bb98`
- `0x1800ada38`
- `0x18012f850`
- `0x180142010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800adaed`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800adaed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800adad4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800adad4`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800adb02`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800adb02`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800adb1e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800adc01`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800adcb3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800adb1e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800adc01`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800adcb3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSceneAnalysisMFT::ExtractNecessaryAttributes(CSceneAnalysisMFT *this, struct IMFSample *a2)
{
  struct IMFSampleVtbl *lpVtbl; // rax
  HRESULT (__stdcall *GetUnknown)(IMFSample *, const GUID *const, const IID *const, LPVOID *); // rbx
  int ActivationFactory; // ebx
  __int64 *v7; // rcx
  CallStackTracing *v8; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v10; // rdx
  __int64 v11; // rsi
  __int64 (__fastcall *v12)(__int64, __int64, char *); // rdi
  __int64 *v13; // rcx
  CallStackTracing *v14; // rax
  struct CallStackContext *v15; // rax
  __int64 *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *v18; // rax
  struct IMFSampleVtbl *v19; // rax
  __int64 v20; // rcx
  _BYTE v22[8]; // [rsp+30h] [rbp-50h] BYREF
  __int64 v23; // [rsp+38h] [rbp-48h] BYREF
  __int64 v24; // [rsp+40h] [rbp-40h] BYREF
  __int64 v25; // [rsp+48h] [rbp-38h] BYREF
  HSTRING string; // [rsp+50h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-28h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v22,
    "CSceneAnalysisMFT::ExtractNecessaryAttributes",
    355);
  lpVtbl = a2->lpVtbl;
  v24 = 0;
  v23 = 0;
  GetUnknown = lpVtbl->GetUnknown;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
  if ( ((int (__fastcall *)(struct IMFSample *, const GUID *, GUID *, __int64 *))GetUnknown)(
         a2,
         &MFSampleExtension_CaptureMetadata,
         &GUID_2cd2d921_c447_44a7_a13c_4adabfc247e3,
         &v24) < 0 )
    goto LABEL_27;
  if ( WindowsCreateStringReference(L"Windows.Media.Capture.CapturedFrameControlValues", 0x30u, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  ActivationFactory = RoGetActivationFactory(string, &GUID_651dde8e_fa01_475c_9c0d_64cf6f70cf8f, &v23);
  if ( ActivationFactory < 0 )
  {
    v7 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v8 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v8;
      if ( v8 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v8 + 8LL))(v8, 2032) )
      {
        v7 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v7 = &qword_18015FF10;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18015FF10;
      }
    }
    if ( *((_BYTE *)v7 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v7);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != ActivationFactory )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CSceneAnalysisMFT::ExtractNecessaryAttributes",
          366,
          ActivationFactory);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v10 = 53;
LABEL_15:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v10,
        &WPP_a042ef2f2a7a38ff6a18b622801eb737_Traceguids,
        this,
        ActivationFactory);
      goto LABEL_40;
    }
    goto LABEL_40;
  }
  v11 = v23;
  v12 = *(__int64 (__fastcall **)(__int64, __int64, char *))(*(_QWORD *)v23 + 48LL);
  Microsoft::WRL::ComPtr<IMFVideoProcessorControl>::InternalRelease((char *)this + 448);
  ActivationFactory = v12(v11, v24, (char *)this + 448);
  if ( ActivationFactory >= 0 )
  {
LABEL_27:
    ActivationFactory = ((__int64 (__fastcall *)(struct IMFSample *, char *))a2->lpVtbl->GetSampleTime)(
                          a2,
                          (char *)this + 456);
    if ( ActivationFactory >= 0 )
    {
      v19 = a2->lpVtbl;
      v25 = 0;
      if ( ((int (__fastcall *)(struct IMFSample *, const IID *, __int64 *))v19->GetUINT64)(
             a2,
             &MFSampleExtension_DeviceTimestamp,
             &v25) >= 0 )
      {
        *((_QWORD *)this + 58) = v25;
        *((_BYTE *)this + 472) = 1;
      }
    }
    else
    {
      v16 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v17;
        if ( v17 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
        {
          v16 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v16 = &qword_18015FF10;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18015FF10;
        }
      }
      if ( *((_BYTE *)v16 + 8) )
      {
        v18 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v16);
        if ( *((_DWORD *)v18 + 499) != ActivationFactory )
          CallStackContext::TraceFailure(v18, "CSceneAnalysisMFT::ExtractNecessaryAttributes", 376, ActivationFactory);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v10 = 55;
        goto LABEL_15;
      }
    }
    goto LABEL_40;
  }
  v13 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
    CallStackTracing::s_wpInstance = v14;
    if ( v14 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
    {
      v13 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v13 = &qword_18015FF10;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18015FF10;
    }
  }
  if ( *((_BYTE *)v13 + 8) )
  {
    v15 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v13);
    if ( *((_DWORD *)v15 + 499) != ActivationFactory )
      CallStackContext::TraceFailure(v15, "CSceneAnalysisMFT::ExtractNecessaryAttributes", 371, ActivationFactory);
  }
  if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
  {
    v10 = 54;
    goto LABEL_15;
  }
LABEL_40:
  v20 = v23;
  if ( v23 )
  {
    v23 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v22);
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x1800ada38  mov     [rsp-28h+arg_10], rbx
0x1800ada3d  push    rbp
0x1800ada3e  push    rsi
0x1800ada3f  push    rdi
0x1800ada40  push    r14
0x1800ada42  push    r15
0x1800ada44  mov     rbp, rsp
0x1800ada47  sub     rsp, 80h
0x1800ada4e  mov     rax, cs:__security_cookie
0x1800ada55  xor     rax, rsp
0x1800ada58  mov     [rbp+var_10], rax
0x1800ada5c  mov     r15, rdx
0x1800ada5f  mov     r14, rcx
0x1800ada62  lea     rdx, aCsceneanalysis_30; "CSceneAnalysisMFT::ExtractNecessaryAttr"...
0x1800ada69  mov     r8d, 163h; int
0x1800ada6f  lea     rcx, [rbp+var_50]; this
0x1800ada73  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800ada78  mov     rax, [r15]
0x1800ada7b  lea     rcx, [rbp+var_40]
0x1800ada7f  mov     [rbp+var_40], 0
0x1800ada87  mov     [rbp+var_48], 0
0x1800ada8f  mov     rbx, [rax+88h]
0x1800ada96  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800ada9b  lea     r9, [rbp+var_40]
0x1800ada9f  mov     rcx, r15
0x1800adaa2  lea     r8, _GUID_2cd2d921_c447_44a7_a13c_4adabfc247e3
0x1800adaa9  mov     rax, rbx
0x1800adaac  lea     rdx, MFSampleExtension_CaptureMetadata
0x1800adab3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800adab8  test    eax, eax
0x1800adaba  js      loc_1800ADC84
0x1800adac0  lea     r9, [rbp+string]; string
0x1800adac4  mov     edx, 30h ; '0'; length
0x1800adac9  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800adacd  lea     rcx, ?RuntimeClass_Windows_Media_Capture_CapturedFrameControlValues@@3QBGB; "Windows.Media.Capture.CapturedFrameCont"...
0x1800adad4  call    cs:__imp_WindowsCreateStringReference
0x1800adada  test    eax, eax
0x1800adadc  jns     short loc_1800ADAF3
0x1800adade  xor     r9d, r9d; lpArguments
0x1800adae1  xor     r8d, r8d; nNumberOfArguments
0x1800adae4  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800adae9  lea     edx, [r9+1]; dwExceptionFlags
0x1800adaed  call    cs:__imp_RaiseException
0x1800adaf3  mov     rcx, [rbp+string]
0x1800adaf7  lea     r8, [rbp+var_48]
0x1800adafb  lea     rdx, _GUID_651dde8e_fa01_475c_9c0d_64cf6f70cf8f
0x1800adb02  call    cs:__imp_RoGetActivationFactory
0x1800adb08  mov     ebx, eax
0x1800adb0a  test    eax, eax
0x1800adb0c  jns     loc_1800ADBBF
0x1800adb12  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800adb19  test    rcx, rcx
0x1800adb1c  jnz     short loc_1800ADB5F
0x1800adb1e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800adb24  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800adb2b  mov     rcx, rax
0x1800adb2e  test    rax, rax
0x1800adb31  jz      short loc_1800ADB51
0x1800adb33  mov     rax, [rax]
0x1800adb36  mov     edx, 7F0h
0x1800adb3b  mov     rax, [rax+8]
0x1800adb3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800adb44  test    eax, eax
0x1800adb46  jz      short loc_1800ADB51
0x1800adb48  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800adb4f  jmp     short loc_1800ADB5F
0x1800adb51  lea     rcx, qword_18015FF10; this
0x1800adb58  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800adb5f  cmp     byte ptr [rcx+8], 0
0x1800adb63  jz      short loc_1800ADB8A
0x1800adb65  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800adb6a  cmp     [rax+7CCh], ebx
0x1800adb70  jz      short loc_1800ADB8A
0x1800adb72  mov     r9d, ebx; int
0x1800adb75  lea     rdx, aCsceneanalysis_30; "CSceneAnalysisMFT::ExtractNecessaryAttr"...
0x1800adb7c  mov     r8d, 16Eh; int
0x1800adb82  mov     rcx, rax; this
0x1800adb85  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800adb8a  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800adb8f  cmp     al, 1
0x1800adb91  jb      loc_1800ADD6B
0x1800adb97  mov     edx, 35h ; '5'
0x1800adb9c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800adba3  lea     r8, WPP_a042ef2f2a7a38ff6a18b622801eb737_Traceguids
0x1800adbaa  mov     r9, r14
0x1800adbad  mov     [rsp+80h+var_60], ebx
0x1800adbb1  mov     rcx, [rcx+10h]
0x1800adbb5  call    WPP_SF_qD
0x1800adbba  jmp     loc_1800ADD6B
0x1800adbbf  mov     rsi, [rbp+var_48]
0x1800adbc3  lea     rbx, [r14+1C0h]
0x1800adbca  mov     rcx, rbx
0x1800adbcd  mov     rax, [rsi]
0x1800adbd0  mov     rdi, [rax+30h]
0x1800adbd4  call    ?InternalRelease@?$ComPtr@UIMFVideoProcessorControl@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFVideoProcessorControl>::InternalRelease(void)
0x1800adbd9  mov     rdx, [rbp+var_40]
0x1800adbdd  mov     r8, rbx
0x1800adbe0  mov     rcx, rsi
0x1800adbe3  mov     rax, rdi
0x1800adbe6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800adbeb  mov     ebx, eax
0x1800adbed  test    eax, eax
0x1800adbef  jns     loc_1800ADC84
0x1800adbf5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800adbfc  test    rcx, rcx
0x1800adbff  jnz     short loc_1800ADC42
0x1800adc01  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800adc07  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800adc0e  mov     rcx, rax
0x1800adc11  test    rax, rax
0x1800adc14  jz      short loc_1800ADC34
0x1800adc16  mov     rax, [rax]
0x1800adc19  mov     edx, 7F0h
0x1800adc1e  mov     rax, [rax+8]
0x1800adc22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800adc27  test    eax, eax
0x1800adc29  jz      short loc_1800ADC34
0x1800adc2b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800adc32  jmp     short loc_1800ADC42
0x1800adc34  lea     rcx, qword_18015FF10; this
0x1800adc3b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800adc42  cmp     byte ptr [rcx+8], 0
0x1800adc46  jz      short loc_1800ADC6D
0x1800adc48  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800adc4d  cmp     [rax+7CCh], ebx
0x1800adc53  jz      short loc_1800ADC6D
0x1800adc55  mov     r9d, ebx; int
0x1800adc58  lea     rdx, aCsceneanalysis_30; "CSceneAnalysisMFT::ExtractNecessaryAttr"...
0x1800adc5f  mov     r8d, 173h; int
0x1800adc65  mov     rcx, rax; this
0x1800adc68  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800adc6d  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800adc72  cmp     al, 1
0x1800adc74  jb      loc_1800ADD6B
0x1800adc7a  mov     edx, 36h ; '6'
0x1800adc7f  jmp     loc_1800ADB9C
0x1800adc84  mov     rax, [r15]
0x1800adc87  lea     rdx, [r14+1C8h]
0x1800adc8e  mov     rcx, r15
0x1800adc91  mov     rax, [rax+118h]
0x1800adc98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800adc9d  mov     ebx, eax
0x1800adc9f  test    eax, eax
0x1800adca1  jns     loc_1800ADD32
0x1800adca7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800adcae  test    rcx, rcx
0x1800adcb1  jnz     short loc_1800ADCF4
0x1800adcb3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800adcb9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800adcc0  mov     rcx, rax
0x1800adcc3  test    rax, rax
0x1800adcc6  jz      short loc_1800ADCE6
0x1800adcc8  mov     rax, [rax]
0x1800adccb  mov     edx, 7F0h
0x1800adcd0  mov     rax, [rax+8]
0x1800adcd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800adcd9  test    eax, eax
0x1800adcdb  jz      short loc_1800ADCE6
0x1800adcdd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800adce4  jmp     short loc_1800ADCF4
0x1800adce6  lea     rcx, qword_18015FF10; this
0x1800adced  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800adcf4  cmp     byte ptr [rcx+8], 0
0x1800adcf8  jz      short loc_1800ADD1F
0x1800adcfa  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800adcff  cmp     [rax+7CCh], ebx
0x1800add05  jz      short loc_1800ADD1F
0x1800add07  mov     r9d, ebx; int
0x1800add0a  lea     rdx, aCsceneanalysis_30; "CSceneAnalysisMFT::ExtractNecessaryAttr"...
0x1800add11  mov     r8d, 178h; int
0x1800add17  mov     rcx, rax; this
0x1800add1a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800add1f  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800add24  cmp     al, 1
0x1800add26  jb      short loc_1800ADD6B
0x1800add28  mov     edx, 37h ; '7'
0x1800add2d  jmp     loc_1800ADB9C
0x1800add32  mov     rax, [r15]
0x1800add35  lea     r8, [rbp+var_38]
0x1800add39  lea     rdx, MFSampleExtension_DeviceTimestamp
0x1800add40  mov     [rbp+var_38], 0
0x1800add48  mov     rcx, r15
0x1800add4b  mov     rax, [rax+40h]
0x1800add4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800add54  test    eax, eax
0x1800add56  js      short loc_1800ADD6B
0x1800add58  mov     rax, [rbp+var_38]
0x1800add5c  mov     [r14+1D0h], rax
0x1800add63  mov     byte ptr [r14+1D8h], 1
0x1800add6b  mov     rcx, [rbp+var_48]
0x1800add6f  test    rcx, rcx
0x1800add72  jz      short loc_1800ADD88
0x1800add74  mov     [rbp+var_48], 0
0x1800add7c  mov     rdx, [rcx]
0x1800add7f  mov     rax, [rdx+10h]
0x1800add83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800add88  lea     rcx, [rbp+var_40]
0x1800add8c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800add91  lea     rcx, [rbp+var_50]; this
0x1800add95  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800add9a  mov     eax, ebx
0x1800add9c  mov     rcx, [rbp+var_10]
0x1800adda0  xor     rcx, rsp; StackCookie
0x1800adda3  call    __security_check_cookie
0x1800adda8  mov     rbx, [rsp+80h+arg_10]
0x1800addb0  add     rsp, 80h
0x1800addb7  pop     r15
0x1800addb9  pop     r14
0x1800addbb  pop     rdi
0x1800addbc  pop     rsi
0x1800addbd  pop     rbp
0x1800addbe  retn
```
