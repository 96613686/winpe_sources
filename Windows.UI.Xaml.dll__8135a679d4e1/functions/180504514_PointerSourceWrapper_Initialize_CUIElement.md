# PointerSourceWrapper::Initialize(CUIElement *)

- ea: `0x180504514`
- end: `0x180504a71`
- name: `?Initialize@PointerSourceWrapper@@QEAAJPEAVCUIElement@@@Z`
- size: `1373`
- prototype: `HRESULT __fastcall(PointerSourceWrapper *this, CUIElement *hoverPointerSourceElement)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18043cce0`

## callees

- `0x180004bc0`
- `0x180008428`
- `0x1801292ec`
- `0x180197558`
- `0x180393c34`
- `0x180504514`
- `0x18076e110`
- `0x180c0e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180504982`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180504995`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1805049a8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1805049bb`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180504982`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180504995`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1805049a8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1805049bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180504770`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1805047f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1805048da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18050492f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180504770`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1805047f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1805048da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18050492f`

## pseudocode

```c
__int64 __fastcall PointerSourceWrapper::Initialize(PointerSourceWrapper *this, CUIElement *hoverPointerSourceElement)
{
  HRESULT v4; // eax
  unsigned int v5; // ebx
  IUnknown *ptr; // rbx
  HRESULT (__fastcall *QueryInterface)(IUnknown *, const _GUID *, void **); // rdi
  HRESULT v8; // eax
  Windows::UI::Composition::IVisual *v9; // rcx
  Windows::UI::Composition::IVisual *v11; // rbx
  HRESULT (__fastcall *v12)(IUnknown *, const _GUID *, void **); // rdi
  HRESULT v13; // eax
  Windows::UI::Composition::ICompositionObject *v14; // rdi
  HRESULT (__fastcall *get_Compositor)(Windows::UI::Composition::ICompositionObject *, Windows::UI::Composition::ICompositor **); // rbx
  Windows::UI::Composition::ICompositionObject *v16; // rcx
  Windows::UI::Composition::ICompositor *v17; // rbx
  HRESULT (__fastcall *v18)(IUnknown *, const _GUID *, void **); // rdi
  HRESULT v19; // eax
  Windows::UI::Composition::ICompositorRestricted *v20; // rdi
  HRESULT (__fastcall *CreateHoverPointerSource)(Windows::UI::Composition::ICompositorRestricted *, Windows::UI::Composition::IVisual *, Windows::UI::Composition::IHoverPointerSourcePartner **); // rbx
  HRESULT v22; // eax
  Windows::UI::Composition::IHoverPointerSourcePartner *v23; // rbx
  HRESULT (__fastcall *v24)(IUnknown *, const _GUID *, void **); // rdi
  Windows::UI::Composition::IHoverPointerSourcePartner *v25; // rcx
  Windows::UI::Composition::ICompositorRestricted *v26; // rcx
  Windows::UI::Composition::ICompositor *v27; // rbx
  Windows::UI::Composition::ICompositor_vtbl *v28; // rdi
  signed int v29; // eax
  HRESULT v30; // eax
  Windows::UI::Composition::IExpressionAnimation *v31; // rbx
  Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionAnimation> *p_m_realPointerPointAnimation; // r14
  HRESULT (__fastcall *v33)(IUnknown *, const _GUID *, void **); // rdi
  HRESULT v34; // eax
  Windows::UI::Composition::ICompositionAnimation *v35; // rbx
  Windows::UI::Composition::ICompositionObject *v36; // rsi
  Windows::UI::Composition::ICompositionAnimation_vtbl *v37; // rdi
  signed int v38; // eax
  Windows::UI::Composition::IExpressionAnimation *v39; // rcx
  Windows::UI::Composition::ICompositor *v40; // rcx
  Windows::UI::Composition::IExpressionAnimation *v41; // rcx
  Windows::UI::Composition::ICompositor *v42; // rdi
  Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionPropertySet> *p_m_pointerSourceProxy; // rsi
  HRESULT (__fastcall *CreatePropertySet)(Windows::UI::Composition::ICompositor *, Windows::UI::Composition::ICompositionPropertySet **); // rbx
  HRESULT v45; // eax
  HRESULT v46; // eax
  _QWORD *v47; // rbx
  Windows::UI::Composition::ICompositionPropertySet_vtbl *v48; // rsi
  signed int v49; // eax
  Windows::UI::Composition::ICompositionObject *v50; // rbx
  Windows::UI::Composition::ICompositionAnimation *v51; // rsi
  Windows::UI::Composition::ICompositionObject_vtbl *v52; // rdi
  signed int v53; // eax
  Microsoft::WRL::ComPtr<Windows::UI::Composition::IVisual> visual; // [rsp+20h] [rbp-60h] BYREF
  Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositor> compositor; // [rsp+28h] [rbp-58h] BYREF
  Microsoft::WRL::ComPtr<Windows::UI::Composition::IExpressionAnimation> expressionAnimation; // [rsp+30h] [rbp-50h] BYREF
  Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositorRestricted> compositorRestricted; // [rsp+38h] [rbp-48h] BYREF
  Microsoft::WRL::ComPtr<Windows::UI::Composition::IHoverPointerSourcePartner> hoverPointerSourcePartner; // [rsp+40h] [rbp-40h] BYREF
  Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionObject> visualAsCO; // [rsp+48h] [rbp-38h] BYREF
  Microsoft::WRL::ComPtr<IUnknown> handOffVisual; // [rsp+50h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-28h] BYREF
  HSTRING string; // [rsp+70h] [rbp-10h] BYREF

  handOffVisual.ptr_ = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionObjectStatics> *)&handOffVisual);
  v4 = CUIElement::GetHandOffVisual(hoverPointerSourceElement, &handOffVisual.ptr_);
  v5 = v4;
  if ( v4 < 0 )
  {
    OnFailure_2990_(v4);
    goto LABEL_6;
  }
  ptr = handOffVisual.ptr_;
  visual.ptr_ = 0;
  QueryInterface = handOffVisual.ptr_->QueryInterface;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics> *)&visual);
  v8 = QueryInterface(ptr, &GUID_117e202d_a859_4c89_873b_c2aa566788e3, (void **)&visual.ptr_);
  v5 = v8;
  if ( v8 < 0 )
  {
    OnFailure_2990_(v8);
LABEL_4:
    v9 = visual.ptr_;
    if ( visual.ptr_ )
    {
      visual.ptr_ = 0;
      v9->Release(v9);
    }
    goto LABEL_6;
  }
  v11 = visual.ptr_;
  compositor.ptr_ = 0;
  visualAsCO.ptr_ = 0;
  v12 = visual.ptr_->QueryInterface;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics> *)&visualAsCO);
  v13 = v12(v11, &GUID_bcb4ad45_7609_4550_934f_16002a68fded, (void **)&visualAsCO.ptr_);
  v5 = v13;
  if ( v13 < 0
    || (v14 = visualAsCO.ptr_,
        get_Compositor = visualAsCO.ptr_->get_Compositor,
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics> *)&compositor),
        v13 = get_Compositor(v14, &compositor.ptr_),
        v5 = v13,
        v13 < 0) )
  {
    OnFailure_2990_(v13);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics> *)&visualAsCO);
    goto LABEL_50;
  }
  v16 = visualAsCO.ptr_;
  if ( visualAsCO.ptr_ )
  {
    visualAsCO.ptr_ = 0;
    v16->Release(v16);
  }
  v17 = compositor.ptr_;
  compositorRestricted.ptr_ = 0;
  v18 = compositor.ptr_->QueryInterface;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics> *)&compositorRestricted);
  v19 = v18(v17, &GUID_36af3eb2_0371_49d7_9bb8_9c9414a9229c, (void **)&compositorRestricted.ptr_);
  v5 = v19;
  if ( v19 < 0 )
  {
    OnFailure_2990_(v19);
    goto LABEL_48;
  }
  v20 = compositorRestricted.ptr_;
  hoverPointerSourcePartner.ptr_ = 0;
  CreateHoverPointerSource = compositorRestricted.ptr_->CreateHoverPointerSource;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics> *)&hoverPointerSourcePartner);
  v22 = CreateHoverPointerSource(v20, visual.ptr_, &hoverPointerSourcePartner.ptr_);
  v5 = v22;
  if ( v22 < 0
    || (v23 = hoverPointerSourcePartner.ptr_,
        v24 = hoverPointerSourcePartner.ptr_->QueryInterface,
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics> *)&this->m_realPointerSourceCO),
        v22 = v24(v23, &GUID_bcb4ad45_7609_4550_934f_16002a68fded, (void **)&this->m_realPointerSourceCO.ptr_),
        v5 = v22,
        v22 < 0) )
  {
    OnFailure_2990_(v22);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics> *)&hoverPointerSourcePartner);
LABEL_48:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics> *)&compositorRestricted);
    goto LABEL_50;
  }
  v25 = hoverPointerSourcePartner.ptr_;
  if ( hoverPointerSourcePartner.ptr_ )
  {
    hoverPointerSourcePartner.ptr_ = 0;
    v25->Release(v25);
  }
  v26 = compositorRestricted.ptr_;
  if ( compositorRestricted.ptr_ )
  {
    compositorRestricted.ptr_ = 0;
    v26->Release(v26);
  }
  v27 = compositor.ptr_;
  expressionAnimation.ptr_ = 0;
  v28 = compositor.ptr_->__vftable;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics> *)&expressionAnimation);
  string = 0;
  v29 = WindowsCreateStringReference(L"hover.Point", 0xBu, &hstringHeader, &string);
  if ( v29 < 0 )
  {
    RaiseException(v29, 1u, 0, 0);
    __debugbreak();
  }
  v30 = v28->CreateExpressionAnimationWithExpression(v27, string, &expressionAnimation.ptr_);
  v5 = v30;
  if ( v30 < 0 )
    goto LABEL_23;
  v31 = expressionAnimation.ptr_;
  p_m_realPointerPointAnimation = &this->m_realPointerPointAnimation;
  v33 = expressionAnimation.ptr_->QueryInterface;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics> *)&this->m_realPointerPointAnimation);
  v34 = v33(v31, &GUID_464c4c2c_1caa_4061_9b40_e13fde1503ca, (void **)&this->m_realPointerPointAnimation.ptr_);
  v5 = v34;
  if ( v34 < 0 )
  {
    OnFailure_2990_(v34);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics> *)&expressionAnimation);
    goto LABEL_50;
  }
  v35 = p_m_realPointerPointAnimation->ptr_;
  v36 = this->m_realPointerSourceCO.ptr_;
  v37 = p_m_realPointerPointAnimation->ptr_->__vftable;
  string = 0;
  v38 = WindowsCreateStringReference(L"hover", 5u, &hstringHeader, &string);
  if ( v38 < 0 )
  {
    RaiseException(v38, 1u, 0, 0);
    __debugbreak();
  }
  v30 = v37->SetReferenceParameter(v35, string, v36);
  v5 = v30;
  if ( v30 < 0 )
  {
LABEL_23:
    OnFailure_2990_(v30);
    v39 = expressionAnimation.ptr_;
    if ( expressionAnimation.ptr_ )
    {
      expressionAnimation.ptr_ = 0;
      v39->Release(v39);
    }
    goto LABEL_25;
  }
  v41 = expressionAnimation.ptr_;
  if ( expressionAnimation.ptr_ )
  {
    expressionAnimation.ptr_ = 0;
    v41->Release(v41);
  }
  v42 = compositor.ptr_;
  p_m_pointerSourceProxy = &this->m_pointerSourceProxy;
  CreatePropertySet = compositor.ptr_->CreatePropertySet;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics> *)&this->m_pointerSourceProxy);
  v45 = CreatePropertySet(v42, &this->m_pointerSourceProxy.ptr_);
  v5 = v45;
  if ( v45 < 0 )
  {
LABEL_35:
    OnFailure_2990_(v45);
LABEL_25:
    v40 = compositor.ptr_;
    if ( compositor.ptr_ )
    {
      compositor.ptr_ = 0;
      v40->Release(v40);
    }
    goto LABEL_4;
  }
  v46 = Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionPropertySet>::As<Windows::UI::Composition::ICompositionObject>(
          &this->m_pointerSourceProxy,
          (Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionObject> >)&this->m_pointerSourceProxyCO);
  v5 = v46;
  if ( v46 < 0 )
    goto LABEL_43;
  v47 = &p_m_pointerSourceProxy->ptr_->__vftable;
  v48 = p_m_pointerSourceProxy->ptr_->__vftable;
  string = 0;
  v49 = WindowsCreateStringReference(L"Point", 5u, &hstringHeader, &string);
  if ( v49 < 0 )
  {
    RaiseException(v49, 1u, 0, 0);
    __debugbreak();
  }
  v46 = ((__int64 (__fastcall *)(_QWORD *, HSTRING, unsigned __int64))v48->InsertVector2)(
          v47,
          string,
          _mm_unpacklo_ps((__m128)0LL, (__m128)0LL).m128_u64[0]);
  v5 = v46;
  if ( v46 < 0 )
  {
LABEL_43:
    OnFailure_2990_(v46);
LABEL_50:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics> *)&compositor);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics> *)&visual);
LABEL_6:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionObjectStatics> *)&handOffVisual);
    return v5;
  }
  v50 = this->m_pointerSourceProxyCO.ptr_;
  v51 = p_m_realPointerPointAnimation->ptr_;
  v52 = v50->__vftable;
  string = 0;
  v53 = WindowsCreateStringReference(L"Point", 5u, &hstringHeader, &string);
  if ( v53 < 0 )
  {
    RaiseException(v53, 1u, 0, 0);
    __debugbreak();
  }
  v45 = v52->StartAnimation(v50, string, v51);
  v5 = v45;
  if ( v45 < 0 )
    goto LABEL_35;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics> *)&compositor);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics> *)&visual);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionObjectStatics> *)&handOffVisual);
  return 0;
}

```

## disassembly

```asm
0x180504514  mov     [rsp-28h+arg_10], rbx
0x180504519  mov     [rsp-28h+arg_18], rsi
0x18050451e  push    rbp
0x18050451f  push    rdi
0x180504520  push    r12
0x180504522  push    r14
0x180504524  push    r15
0x180504526  mov     rbp, rsp
0x180504529  sub     rsp, 80h
0x180504530  mov     rax, cs:__security_cookie
0x180504537  xor     rax, rsp
0x18050453a  mov     [rbp+var_8], rax
0x18050453e  mov     r15, this
0x180504541  xor     r12d, r12d
0x180504544  lea     this, [rbp+handOffVisual]; this
0x180504548  mov     [rbp+handOffVisual.ptr_], r12
0x18050454c  mov     rbx, hoverPointerSourceElement
0x18050454f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180504554  lea     hoverPointerSourceElement, [rbp+handOffVisual]; ppUnkHandOffVisual
0x180504558  mov     this, rbx; this
0x18050455b  call    ?GetHandOffVisual@CUIElement@@QEAAJPEAPEAUIUnknown@@@Z; CUIElement::GetHandOffVisual(IUnknown * *)
0x180504560  mov     ebx, eax
0x180504562  test    eax, eax
0x180504564  js      loc_180504A65
0x18050456a  mov     rbx, [rbp+handOffVisual.ptr_]
0x18050456e  lea     this, [rbp+visual]; this
0x180504572  mov     [rbp+visual.ptr_], r12
0x180504576  mov     rax, [rbx]
0x180504579  mov     rdi, [rax]
0x18050457c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180504581  lea     r8, [rbp+visual]
0x180504585  mov     this, rbx
0x180504588  lea     hoverPointerSourceElement, _GUID_117e202d_a859_4c89_873b_c2aa566788e3
0x18050458f  mov     rax, rdi
0x180504592  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180504597  mov     ebx, eax
0x180504599  test    eax, eax
0x18050459b  jns     short loc_1805045F0
0x18050459d  mov     ecx, eax; failedFrameHR
0x18050459f  call    OnFailure_2990_
0x1805045a4  mov     this, [rbp+visual.ptr_]
0x1805045a8  test    this, this
0x1805045ab  jz      short loc_1805045BD
0x1805045ad  mov     [rbp+visual.ptr_], r12
0x1805045b1  mov     rax, [this]
0x1805045b4  mov     rax, [rax+10h]
0x1805045b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1805045bd  lea     this, [rbp+handOffVisual]; this
0x1805045c1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1805045c6  mov     eax, ebx
0x1805045c8  mov     this, [rbp+var_8]
0x1805045cc  xor     this, rsp; StackCookie
0x1805045cf  call    __security_check_cookie
0x1805045d4  lea     r11, [rsp+80h+var_s0]
0x1805045dc  mov     rbx, [r11+40h]
0x1805045e0  mov     rsi, [r11+48h]
0x1805045e4  mov     rsp, r11
0x1805045e7  pop     r15
0x1805045e9  pop     r14
0x1805045eb  pop     r12
0x1805045ed  pop     rdi
0x1805045ee  pop     rbp
0x1805045ef  retn
0x1805045f0  mov     rbx, [rbp+visual.ptr_]
0x1805045f4  lea     this, [rbp+visualAsCO]; this
0x1805045f8  mov     [rbp+compositor.ptr_], r12
0x1805045fc  mov     [rbp+visualAsCO.ptr_], r12
0x180504600  mov     rax, [rbx]
0x180504603  mov     rdi, [rax]
0x180504606  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18050460b  lea     r8, [rbp+visualAsCO]
0x18050460f  mov     this, rbx
0x180504612  lea     hoverPointerSourceElement, _GUID_bcb4ad45_7609_4550_934f_16002a68fded
0x180504619  mov     rax, rdi
0x18050461c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180504621  mov     ebx, eax
0x180504623  test    eax, eax
0x180504625  js      loc_180504A3E
0x18050462b  mov     rdi, [rbp+visualAsCO.ptr_]
0x18050462f  lea     this, [rbp+compositor]; this
0x180504633  mov     rax, [rdi]
0x180504636  mov     rbx, [rax+30h]
0x18050463a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18050463f  lea     hoverPointerSourceElement, [rbp+compositor]
0x180504643  mov     this, rdi
0x180504646  mov     rax, rbx
0x180504649  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18050464e  mov     ebx, eax
0x180504650  test    eax, eax
0x180504652  js      loc_180504A35
0x180504658  mov     this, [rbp+visualAsCO.ptr_]
0x18050465c  test    this, this
0x18050465f  jz      short loc_180504671
0x180504661  mov     [rbp+visualAsCO.ptr_], r12
0x180504665  mov     rax, [this]
0x180504668  mov     rax, [rax+10h]
0x18050466c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180504671  mov     rbx, [rbp+compositor.ptr_]
0x180504675  lea     this, [rbp+compositorRestricted]; this
0x180504679  mov     [rbp+compositorRestricted.ptr_], r12
0x18050467d  mov     rax, [rbx]
0x180504680  mov     rdi, [rax]
0x180504683  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180504688  lea     r8, [rbp+compositorRestricted]
0x18050468c  mov     this, rbx
0x18050468f  lea     hoverPointerSourceElement, _GUID_36af3eb2_0371_49d7_9bb8_9c9414a9229c
0x180504696  mov     rax, rdi
0x180504699  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18050469e  mov     ebx, eax
0x1805046a0  test    eax, eax
0x1805046a2  js      loc_180504A23
0x1805046a8  mov     rdi, [rbp+compositorRestricted.ptr_]
0x1805046ac  lea     this, [rbp+hoverPointerSourcePartner]; this
0x1805046b0  mov     [rbp+hoverPointerSourcePartner.ptr_], r12
0x1805046b4  mov     rax, [rdi]
0x1805046b7  mov     rbx, [rax+18h]
0x1805046bb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1805046c0  mov     hoverPointerSourceElement, [rbp+visual.ptr_]
0x1805046c4  lea     r8, [rbp+hoverPointerSourcePartner]
0x1805046c8  mov     this, rdi
0x1805046cb  mov     rax, rbx
0x1805046ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1805046d3  mov     ebx, eax
0x1805046d5  test    eax, eax
0x1805046d7  js      loc_180504A11
0x1805046dd  mov     rbx, [rbp+hoverPointerSourcePartner.ptr_]
0x1805046e1  lea     rsi, [r15+20h]
0x1805046e5  mov     this, rsi; this
0x1805046e8  mov     rax, [rbx]
0x1805046eb  mov     rdi, [rax]
0x1805046ee  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1805046f3  mov     r8, rsi
0x1805046f6  lea     hoverPointerSourceElement, _GUID_bcb4ad45_7609_4550_934f_16002a68fded
0x1805046fd  mov     this, rbx
0x180504700  mov     rax, rdi
0x180504703  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180504708  mov     ebx, eax
0x18050470a  test    eax, eax
0x18050470c  js      loc_180504A08
0x180504712  mov     this, [rbp+hoverPointerSourcePartner.ptr_]
0x180504716  test    this, this
0x180504719  jz      short loc_18050472B
0x18050471b  mov     [rbp+hoverPointerSourcePartner.ptr_], r12
0x18050471f  mov     rax, [this]
0x180504722  mov     rax, [rax+10h]
0x180504726  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18050472b  mov     this, [rbp+compositorRestricted.ptr_]
0x18050472f  test    this, this
0x180504732  jz      short loc_180504744
0x180504734  mov     [rbp+compositorRestricted.ptr_], r12
0x180504738  mov     rax, [this]
0x18050473b  mov     rax, [rax+10h]
0x18050473f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180504744  mov     rbx, [rbp+compositor.ptr_]
0x180504748  lea     this, [rbp+expressionAnimation]; this
0x18050474c  mov     [rbp+expressionAnimation.ptr_], r12
0x180504750  mov     rdi, [rbx]
0x180504753  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180504758  lea     r9, [rbp+string]; string
0x18050475c  mov     [rbp+string], r12
0x180504760  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180504764  mov     edx, 0Bh; length
0x180504769  lea     this, aHoverPoint; "hover.Point"
0x180504770  call    cs:__imp_WindowsCreateStringReference
0x180504776  test    eax, eax
0x180504778  js      loc_180504976
0x18050477e  mov     hoverPointerSourceElement, [rbp+string]
0x180504782  lea     r8, [rbp+expressionAnimation]
0x180504786  mov     rax, [rdi+70h]
0x18050478a  mov     this, rbx
0x18050478d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180504792  mov     ebx, eax
0x180504794  test    eax, eax
0x180504796  js      loc_18050495E
0x18050479c  mov     rbx, [rbp+expressionAnimation.ptr_]
0x1805047a0  lea     r14, [r15+28h]
0x1805047a4  mov     this, r14; this
0x1805047a7  mov     rax, [rbx]
0x1805047aa  mov     rdi, [rax]
0x1805047ad  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1805047b2  mov     r8, r14
0x1805047b5  lea     hoverPointerSourceElement, _GUID_464c4c2c_1caa_4061_9b40_e13fde1503ca
0x1805047bc  mov     this, rbx
0x1805047bf  mov     rax, rdi
0x1805047c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1805047c7  mov     ebx, eax
0x1805047c9  test    eax, eax
0x1805047cb  js      loc_1805049F6
0x1805047d1  mov     rbx, [r14]
0x1805047d4  lea     r9, [rbp+string]; string
0x1805047d8  mov     rsi, [rsi]
0x1805047db  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1805047df  mov     edx, 5; length
0x1805047e4  lea     this, aHover_0; "hover"
0x1805047eb  mov     rdi, [rbx]
0x1805047ee  mov     [rbp+string], r12
0x1805047f2  call    cs:__imp_WindowsCreateStringReference
0x1805047f8  test    eax, eax
0x1805047fa  js      loc_180504989
0x180504800  mov     hoverPointerSourceElement, [rbp+string]
0x180504804  mov     r8, rsi
0x180504807  mov     rax, [rdi+60h]
0x18050480b  mov     this, rbx
0x18050480e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180504813  mov     ebx, eax
0x180504815  test    eax, eax
0x180504817  jns     short loc_18050485B
0x180504819  mov     ecx, eax; failedFrameHR
0x18050481b  call    OnFailure_2990_
0x180504820  mov     this, [rbp+expressionAnimation.ptr_]
0x180504824  test    this, this
0x180504827  jz      short loc_180504839
0x180504829  mov     [rbp+expressionAnimation.ptr_], r12
0x18050482d  mov     rax, [this]
0x180504830  mov     rax, [rax+10h]
0x180504834  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180504839  mov     this, [rbp+compositor.ptr_]
0x18050483d  test    this, this
0x180504840  jz      loc_1805045A4
0x180504846  mov     [rbp+compositor.ptr_], r12
0x18050484a  mov     rax, [this]
0x18050484d  mov     rax, [rax+10h]
0x180504851  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180504856  jmp     loc_1805045A4
0x18050485b  mov     this, [rbp+expressionAnimation.ptr_]
0x18050485f  test    this, this
0x180504862  jz      short loc_180504874
0x180504864  mov     [rbp+expressionAnimation.ptr_], r12
0x180504868  mov     rax, [this]
0x18050486b  mov     rax, [rax+10h]
0x18050486f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180504874  mov     rdi, [rbp+compositor.ptr_]
0x180504878  lea     rsi, [r15+10h]
0x18050487c  mov     this, rsi; this
0x18050487f  mov     rax, [rdi]
0x180504882  mov     rbx, [rax+90h]
0x180504889  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18050488e  mov     hoverPointerSourceElement, rsi
0x180504891  mov     this, rdi
0x180504894  mov     rax, rbx
0x180504897  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18050489c  mov     ebx, eax
0x18050489e  test    eax, eax
0x1805048a0  js      loc_18050496A
0x1805048a6  lea     hoverPointerSourceElement, [r15+18h]; p
0x1805048aa  mov     this, rsi; this
0x1805048ad  call    ??$As@UICompositionObject@Composition@UI@Windows@@@?$ComPtr@UICompositionPropertySet@Composition@UI@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UICompositionObject@Composition@UI@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionPropertySet>::As<Windows::UI::Composition::ICompositionObject>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionObject>>)
0x1805048b2  mov     ebx, eax
0x1805048b4  test    eax, eax
0x1805048b6  js      loc_1805049ED
0x1805048bc  mov     rbx, [rsi]
0x1805048bf  lea     r9, [rbp+string]; string
0x1805048c3  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1805048c7  mov     edx, 5; length
0x1805048cc  lea     this, aPoint; "Point"
0x1805048d3  mov     rsi, [rbx]
0x1805048d6  mov     [rbp+string], r12
0x1805048da  call    cs:__imp_WindowsCreateStringReference
0x1805048e0  test    eax, eax
0x1805048e2  js      loc_18050499C
0x1805048e8  mov     hoverPointerSourceElement, [rbp+string]
0x1805048ec  xorps   xmm0, xmm0
0x1805048ef  mov     rax, [rsi+58h]
0x1805048f3  mov     this, rbx
0x1805048f6  unpcklps xmm0, xmm0
0x1805048f9  movq    r8, xmm0
0x1805048fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180504903  mov     ebx, eax
0x180504905  test    eax, eax
0x180504907  js      loc_1805049E4
0x18050490d  mov     rbx, [r15+18h]
0x180504911  lea     r9, [rbp+string]; string
0x180504915  mov     rsi, [r14]
0x180504918  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18050491c  mov     edx, 5; length
0x180504921  lea     this, aPoint; "Point"
0x180504928  mov     rdi, [rbx]
0x18050492b  mov     [rbp+string], r12
0x18050492f  call    cs:__imp_WindowsCreateStringReference
0x180504935  test    eax, eax
0x180504937  js      short loc_1805049AF
0x180504939  mov     hoverPointerSourceElement, [rbp+string]
0x18050493d  mov     r8, rsi
0x180504940  mov     rax, [rdi+48h]
0x180504944  mov     this, rbx
0x180504947  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18050494c  mov     ebx, eax
0x18050494e  test    eax, eax
0x180504950  jns     short loc_1805049C2
0x180504952  mov     ecx, eax; failedFrameHR
0x180504954  call    OnFailure_2990_
0x180504959  jmp     loc_180504839
0x18050495e  mov     ecx, eax; failedFrameHR
0x180504960  call    OnFailure_2990_
0x180504965  jmp     loc_180504820
0x18050496a  mov     ecx, eax; failedFrameHR
0x18050496c  call    OnFailure_2990_
0x180504971  jmp     loc_180504839
0x180504976  xor     r9d, r9d; lpArguments
0x180504979  xor     r8d, r8d; nNumberOfArguments
  ... truncated ...
```
