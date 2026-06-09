# InkManagerTelemetry::RecognitionActivity::StartActivity(IInkRecognizerContext *,HSTRING__ *,Windows::UI::Input::Internal::Inking::IInputGuide *)

- ea: `0x18003c4c8`
- end: `0x18003c800`
- name: `?StartActivity@RecognitionActivity@InkManagerTelemetry@@QEAAXPEAUIInkRecognizerContext@@PEAUHSTRING__@@PEAUIInputGuide@Inking@Internal@Input@UI@Windows@@@Z`
- size: `824`
- prototype: `void(InkManagerTelemetry::RecognitionActivity *__hidden this, struct IInkRecognizerContext *, HSTRING, struct Windows::UI::Input::Internal::Inking::IInputGuide *)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003bb90`

## callees

- `0x180001b9c`
- `0x1800025e4`
- `0x1800062a0`
- `0x18000bed8`
- `0x1800101bc`
- `0x1800101e8`
- `0x180038f48`
- `0x18003add0`
- `0x18003b49c`
- `0x18003c4c8`
- `0x18003c808`
- `0x18003cfc4`
- `0x18003cfe4`
- `0x18003d354`
- `0x18005a698`
- `0x1800fb010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18003c636`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18003c636`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003c6ea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003c6ea`
- `OLEAUT32!__imp_SysAllocString` at `0x18003c552`
- `OLEAUT32!__imp_SysAllocString` at `0x18003c552`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003c6d8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003c6d8`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall InkManagerTelemetry::RecognitionActivity::StartActivity(
        InkManagerTelemetry::RecognitionActivity *this,
        struct IInkRecognizerContext *a2,
        HSTRING a3,
        struct Windows::UI::Input::Internal::Inking::IInputGuide *a4)
{
  wil::TraceLoggingProvider *v8; // rax
  unsigned __int8 v9; // dl
  unsigned __int64 v10; // r8
  BSTR v11; // rax
  HRESULT (__stdcall *get_Recognizer)(IInkRecognizerContext *, IInkRecognizer **); // rbx
  __int64 v13; // rdi
  int (__fastcall *v14)(__int64, __int64 *); // rbx
  __int64 v15; // rbx
  const struct _tlgProvider_t *v16; // rax
  __int64 v17; // r8
  const struct _tlgProvider_t *v18; // rax
  __int64 v19; // rdx
  __int64 v20; // r8
  int v21; // ebx
  __int64 v22; // r8
  int v23; // ecx
  int v24; // [rsp+A0h] [rbp-80h] BYREF
  int v25; // [rsp+A4h] [rbp-7Ch] BYREF
  int v26; // [rsp+A8h] [rbp-78h] BYREF
  __int64 v27; // [rsp+B0h] [rbp-70h] BYREF
  __int64 v28; // [rsp+B8h] [rbp-68h] BYREF
  __int64 v29; // [rsp+C0h] [rbp-60h] BYREF
  int v30; // [rsp+C8h] [rbp-58h] BYREF
  int v31; // [rsp+CCh] [rbp-54h] BYREF
  int v32; // [rsp+D0h] [rbp-50h] BYREF
  int v33; // [rsp+D4h] [rbp-4Ch] BYREF
  int v34; // [rsp+D8h] [rbp-48h] BYREF
  int v35; // [rsp+DCh] [rbp-44h] BYREF
  int v36; // [rsp+E0h] [rbp-40h] BYREF
  int v37; // [rsp+E4h] [rbp-3Ch] BYREF
  int v38; // [rsp+E8h] [rbp-38h] BYREF
  int v39; // [rsp+ECh] [rbp-34h] BYREF
  int v40; // [rsp+F0h] [rbp-30h] BYREF
  PCWSTR StringRawBuffer; // [rsp+F8h] [rbp-28h] BYREF
  __int64 v42; // [rsp+100h] [rbp-20h] BYREF
  __int64 v43; // [rsp+108h] [rbp-18h] BYREF
  __int128 v44; // [rsp+110h] [rbp-10h] BYREF
  __int128 v45; // [rsp+120h] [rbp+0h] BYREF

  v8 = (wil::TraceLoggingProvider *)wil::details::static_lazy<InkManagerLogging>::get(
                                      this,
                                      _lambda_b9a08c5dbc2c400edd7d652b44696801_::_lambda_invoker_cdecl_);
  if ( wil::TraceLoggingProvider::IsEnabled_(v8, v9, v10) )
  {
    v28 = 0;
    v29 = 0;
    v45 = 0;
    v44 = 0;
    v26 = 0;
    v25 = 0;
    v24 = 0;
    if ( a2 )
    {
      get_Recognizer = a2->lpVtbl->get_Recognizer;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
      if ( ((int (__fastcall *)(struct IInkRecognizerContext *, __int64 *))get_Recognizer)(a2, &v29) < 0
        || (v13 = v29,
            v14 = *(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v29 + 56LL),
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
              &v28,
              0),
            v14(v13, &v28) < 0) )
      {
LABEL_19:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v28);
        return;
      }
    }
    else
    {
      v11 = SysAllocString(L"None");
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v28,
        v11);
      v27 = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v27);
    }
    if ( (int)Windows::UI::Input::Internal::Inking::CInputGuide::GetData(
                a4,
                (struct Windows::Foundation::Rect *)&v45,
                (struct Windows::Foundation::Rect *)&v44,
                &v26,
                &v25,
                &v24) >= 0 )
    {
      wil::ActivityBase<InkFeedbackManagerLogging,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
        this,
        &v27);
      v15 = *((_QWORD *)this + 34);
      v16 = InkManagerLogging::Provider();
      if ( *(_DWORD *)v16 > 5u && (unsigned __int8)tlgKeywordOn(v16, 0x200000000000LL, v17) )
        EventActivityIdControl(3u, (LPGUID)(v15 + 8));
      else
        *(_OWORD *)(v15 + 8) = 0;
      *(_DWORD *)v15 = 1;
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v27);
      v18 = InkManagerLogging::Provider();
      v21 = (int)v18;
      if ( *(_DWORD *)v18 > 5u && (unsigned __int8)tlgKeywordOn(v18, 0x200000000000LL, v20) )
      {
        v30 = v24;
        v31 = v25;
        v32 = v26;
        v33 = (int)*((float *)&v44 + 3);
        v34 = (int)*((float *)&v44 + 2);
        v35 = (int)*((float *)&v44 + 1);
        v36 = (int)*(float *)&v44;
        v37 = (int)*((float *)&v45 + 3);
        v38 = (int)*((float *)&v45 + 2);
        v39 = (int)*((float *)&v45 + 1);
        v40 = (int)*(float *)&v45;
        StringRawBuffer = WindowsGetStringRawBuffer(a3, 0);
        v42 = v28;
        LODWORD(v27) = GetCurrentThreadId();
        v43 = 0;
        v22 = *((_QWORD *)this + 34);
        if ( !*(_BYTE *)(v22 + 4) || _tlgGuidIsZero((const struct _GUID *)(v22 + 24)) )
          v23 = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v21,
          (unsigned int)&word_180133DC6,
          v22 + 8,
          v23,
          (__int64)&v43,
          (__int64)&v27,
          (__int64)&v42,
          (__int64)&StringRawBuffer,
          (__int64)&v40,
          (__int64)&v39,
          (__int64)&v38,
          (__int64)&v37,
          (__int64)&v36,
          (__int64)&v35,
          (__int64)&v34,
          (__int64)&v33,
          (__int64)&v32,
          (__int64)&v31,
          (__int64)&v30);
      }
      if ( !*((_DWORD *)this + 78) )
        wil::details::ThreadFailureCallbackHolder::StartWatching(
          (InkManagerTelemetry::RecognitionActivity *)((char *)this + 288),
          v19);
    }
    goto LABEL_19;
  }
}

```

## disassembly

```asm
0x18003c4c8  push    rbp
0x18003c4ca  push    rbx
0x18003c4cb  push    rsi
0x18003c4cc  push    rdi
0x18003c4cd  push    r14
0x18003c4cf  push    r15
0x18003c4d1  lea     rbp, [rsp-28h]
0x18003c4d6  sub     rsp, 148h
0x18003c4dd  mov     rax, cs:__security_cookie
0x18003c4e4  xor     rax, rsp
0x18003c4e7  mov     [rbp+50h+var_40], rax
0x18003c4eb  mov     r14, r9
0x18003c4ee  mov     r15, r8
0x18003c4f1  mov     rdi, rdx
0x18003c4f4  mov     rsi, rcx
0x18003c4f7  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_b9a08c5dbc2c400edd7d652b44696801_@@CA@XZ; _lambda_b9a08c5dbc2c400edd7d652b44696801_::_lambda_invoker_cdecl_(void)
0x18003c4fe  call    ?get@?$static_lazy@VInkManagerLogging@@@details@wil@@QEAAPEAVInkManagerLogging@@P6AXXZ@Z; wil::details::static_lazy<InkManagerLogging>::get(void (*)(void))
0x18003c503  mov     rcx, rax; this
0x18003c506  call    ?IsEnabled_@TraceLoggingProvider@wil@@IEBA_NE_K@Z; wil::TraceLoggingProvider::IsEnabled_(uchar,unsigned __int64)
0x18003c50b  test    al, al
0x18003c50d  jz      loc_18003C7E4
0x18003c513  mov     [rbp+50h+var_B8], 0
0x18003c51b  mov     [rbp+50h+var_B0], 0
0x18003c523  xorps   xmm0, xmm0
0x18003c526  movups  [rbp+50h+var_50], xmm0
0x18003c52a  xorps   xmm1, xmm1
0x18003c52d  movups  [rbp+50h+var_60], xmm1
0x18003c531  mov     [rbp+50h+var_C8], 0
0x18003c538  mov     [rbp+50h+var_CC], 0
0x18003c53f  mov     [rbp+50h+var_D0], 0
0x18003c546  test    rdi, rdi
0x18003c549  jnz     short loc_18003C573
0x18003c54b  lea     rcx, aNone; "None"
0x18003c552  call    cs:__imp_SysAllocString
0x18003c558  mov     rdx, rax
0x18003c55b  lea     rcx, [rbp+50h+var_B8]
0x18003c55f  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18003c564  mov     [rbp+50h+var_C0], rdi
0x18003c568  lea     rcx, [rbp+50h+var_C0]
0x18003c56c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003c571  jmp     short loc_18003C5CA
0x18003c573  mov     rax, [rdi]
0x18003c576  mov     rbx, [rax+0B8h]
0x18003c57d  lea     rcx, [rbp+50h+var_B0]
0x18003c581  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003c586  lea     rdx, [rbp+50h+var_B0]
0x18003c58a  mov     rcx, rdi
0x18003c58d  mov     rax, rbx
0x18003c590  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c595  test    eax, eax
0x18003c597  js      loc_18003C7D1
0x18003c59d  mov     rdi, [rbp+50h+var_B0]
0x18003c5a1  mov     rax, [rdi]
0x18003c5a4  mov     rbx, [rax+38h]
0x18003c5a8  xor     edx, edx
0x18003c5aa  lea     rcx, [rbp+50h+var_B8]
0x18003c5ae  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18003c5b3  lea     rdx, [rbp+50h+var_B8]
0x18003c5b7  mov     rcx, rdi
0x18003c5ba  mov     rax, rbx
0x18003c5bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c5c2  test    eax, eax
0x18003c5c4  js      loc_18003C7D1
0x18003c5ca  lea     rax, [rbp+50h+var_D0]
0x18003c5ce  mov     [rsp+170h+var_148], rax; int *
0x18003c5d3  lea     rax, [rbp+50h+var_CC]
0x18003c5d7  mov     [rsp+170h+var_150], rax; int *
0x18003c5dc  lea     r9, [rbp+50h+var_C8]; int *
0x18003c5e0  lea     r8, [rbp+50h+var_60]; struct Windows::Foundation::Rect *
0x18003c5e4  lea     rdx, [rbp+50h+var_50]; struct Windows::Foundation::Rect *
0x18003c5e8  mov     rcx, r14; struct Windows::UI::Input::Internal::Inking::IInputGuide *
0x18003c5eb  call    ?GetData@CInputGuide@Inking@Internal@Input@UI@Windows@@SAJPEAUIInputGuide@23456@PEAURect@Foundation@6@1PEAH22@Z; Windows::UI::Input::Internal::Inking::CInputGuide::GetData(Windows::UI::Input::Internal::Inking::IInputGuide *,Windows::Foundation::Rect *,Windows::Foundation::Rect *,int *,int *,int *)
0x18003c5f0  test    eax, eax
0x18003c5f2  js      loc_18003C7D1
0x18003c5f8  lea     rdx, [rbp+50h+var_C0]
0x18003c5fc  mov     rcx, rsi
0x18003c5ff  call    ?LockExclusive@?$ActivityBase@VInkFeedbackManagerLogging@@$00$0EAAAAAAAAAAA@$04$0CAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<InkFeedbackManagerLogging,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18003c604  mov     rbx, [rsi+110h]
0x18003c60b  call    ?Provider@InkManagerLogging@@SAPEBU_tlgProvider_t@@XZ; InkManagerLogging::Provider(void)
0x18003c610  mov     ecx, [rax]
0x18003c612  cmp     ecx, 5
0x18003c615  jbe     short loc_18003C63E
0x18003c617  mov     rdx, 200000000000h
0x18003c621  mov     rcx, rax
0x18003c624  call    _tlgKeywordOn
0x18003c629  test    al, al
0x18003c62b  jz      short loc_18003C63E
0x18003c62d  lea     rdx, [rbx+8]; ActivityId
0x18003c631  mov     ecx, 3; ControlCode
0x18003c636  call    cs:__imp_EventActivityIdControl
0x18003c63c  jmp     short loc_18003C645
0x18003c63e  xorps   xmm0, xmm0
0x18003c641  movups  xmmword ptr [rbx+8], xmm0
0x18003c645  mov     dword ptr [rbx], 1
0x18003c64b  lea     rcx, [rbp+50h+var_C0]
0x18003c64f  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18003c654  call    ?Provider@InkManagerLogging@@SAPEBU_tlgProvider_t@@XZ; InkManagerLogging::Provider(void)
0x18003c659  mov     rbx, rax
0x18003c65c  mov     ecx, [rax]
0x18003c65e  cmp     ecx, 5
0x18003c661  jbe     loc_18003C7BE
0x18003c667  mov     rdx, 200000000000h
0x18003c671  mov     rcx, rax
0x18003c674  call    _tlgKeywordOn
0x18003c679  test    al, al
0x18003c67b  jz      loc_18003C7BE
0x18003c681  mov     ecx, [rbp+50h+var_D0]
0x18003c684  mov     [rbp+50h+var_A8], ecx
0x18003c687  mov     eax, [rbp+50h+var_CC]
0x18003c68a  mov     [rbp+50h+var_A4], eax
0x18003c68d  mov     eax, [rbp+50h+var_C8]
0x18003c690  mov     [rbp+50h+var_A0], eax
0x18003c693  cvttss2si eax, dword ptr [rbp+50h+var_60+0Ch]
0x18003c698  mov     [rbp+50h+var_9C], eax
0x18003c69b  cvttss2si eax, dword ptr [rbp+50h+var_60+8]
0x18003c6a0  mov     [rbp+50h+var_98], eax
0x18003c6a3  cvttss2si eax, dword ptr [rbp+50h+var_60+4]
0x18003c6a8  mov     [rbp+50h+var_94], eax
0x18003c6ab  cvttss2si eax, dword ptr [rbp+50h+var_60]
0x18003c6b0  mov     [rbp+50h+var_90], eax
0x18003c6b3  cvttss2si eax, dword ptr [rbp+50h+var_50+0Ch]
0x18003c6b8  mov     [rbp+50h+var_8C], eax
0x18003c6bb  cvttss2si eax, dword ptr [rbp+50h+var_50+8]
0x18003c6c0  mov     [rbp+50h+var_88], eax
0x18003c6c3  cvttss2si eax, dword ptr [rbp+50h+var_50+4]
0x18003c6c8  mov     [rbp+50h+var_84], eax
0x18003c6cb  cvttss2si eax, dword ptr [rbp+50h+var_50]
0x18003c6d0  mov     [rbp+50h+var_80], eax
0x18003c6d3  xor     edx, edx; length
0x18003c6d5  mov     rcx, r15; string
0x18003c6d8  call    cs:__imp_WindowsGetStringRawBuffer
0x18003c6de  mov     [rbp+50h+var_78], rax
0x18003c6e2  mov     rax, [rbp+50h+var_B8]
0x18003c6e6  mov     [rbp+50h+var_70], rax
0x18003c6ea  call    cs:__imp_GetCurrentThreadId
0x18003c6f0  mov     dword ptr [rbp+50h+var_C0], eax
0x18003c6f3  mov     [rbp+50h+var_68], 0
0x18003c6fb  mov     r8, [rsi+110h]
0x18003c702  cmp     byte ptr [r8+4], 0
0x18003c707  jz      short loc_18003C716
0x18003c709  lea     rcx, [r8+18h]; struct _GUID *
0x18003c70d  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x18003c712  test    al, al
0x18003c714  jz      short loc_18003C718
0x18003c716  xor     ecx, ecx
0x18003c718  add     r8, 8
0x18003c71c  lea     rax, [rbp+50h+var_A8]
0x18003c720  mov     [rsp+170h+var_E0], rax
0x18003c728  lea     rax, [rbp+50h+var_A4]
0x18003c72c  mov     [rsp+170h+var_E8], rax
0x18003c734  lea     rax, [rbp+50h+var_A0]
0x18003c738  mov     [rsp+170h+var_F0], rax
0x18003c740  lea     rax, [rbp+50h+var_9C]
0x18003c744  mov     [rsp+170h+var_F8], rax
0x18003c749  lea     rax, [rbp+50h+var_98]
0x18003c74d  mov     [rsp+170h+var_100], rax
0x18003c752  lea     rax, [rbp+50h+var_94]
0x18003c756  mov     [rsp+170h+var_108], rax
0x18003c75b  lea     rax, [rbp+50h+var_90]
0x18003c75f  mov     [rsp+170h+var_110], rax
0x18003c764  lea     rax, [rbp+50h+var_8C]
0x18003c768  mov     [rsp+170h+var_118], rax
0x18003c76d  lea     rax, [rbp+50h+var_88]
0x18003c771  mov     [rsp+170h+var_120], rax
0x18003c776  lea     rax, [rbp+50h+var_84]
0x18003c77a  mov     [rsp+170h+var_128], rax
0x18003c77f  lea     rax, [rbp+50h+var_80]
0x18003c783  mov     [rsp+170h+var_130], rax
0x18003c788  lea     rax, [rbp+50h+var_78]
0x18003c78c  mov     [rsp+170h+var_138], rax
0x18003c791  lea     rax, [rbp+50h+var_70]
0x18003c795  mov     [rsp+170h+var_140], rax
0x18003c79a  lea     rax, [rbp+50h+var_C0]
0x18003c79e  mov     [rsp+170h+var_148], rax
0x18003c7a3  lea     rax, [rbp+50h+var_68]
0x18003c7a7  mov     [rsp+170h+var_150], rax
0x18003c7ac  mov     r9, rcx
0x18003c7af  lea     rdx, word_180133DC6
0x18003c7b6  mov     rcx, rbx
0x18003c7b9  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U3@U2@U2@U2@U2@U2@U2@U2@U2@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@544444444444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18003c7be  lea     rcx, [rsi+120h]; this
0x18003c7c5  cmp     dword ptr [rcx+18h], 0
0x18003c7c9  jnz     short loc_18003C7D1
0x18003c7cb  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x18003c7d0  nop
0x18003c7d1  lea     rcx, [rbp+50h+var_B0]
0x18003c7d5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003c7da  nop
0x18003c7db  lea     rcx, [rbp+50h+var_B8]
0x18003c7df  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003c7e4  mov     rcx, [rbp+50h+var_40]
0x18003c7e8  xor     rcx, rsp; StackCookie
0x18003c7eb  call    __security_check_cookie
0x18003c7f0  add     rsp, 148h
0x18003c7f7  pop     r15
0x18003c7f9  pop     r14
0x18003c7fb  pop     rdi
0x18003c7fc  pop     rsi
0x18003c7fd  pop     rbx
0x18003c7fe  pop     rbp
0x18003c7ff  retn
```
