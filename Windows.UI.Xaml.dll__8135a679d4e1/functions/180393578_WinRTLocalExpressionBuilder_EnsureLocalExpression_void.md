# WinRTLocalExpressionBuilder::EnsureLocalExpression(void)

- ea: `0x180393578`
- end: `0x180393a7a`
- name: `?EnsureLocalExpression@WinRTLocalExpressionBuilder@@QEAAXXZ`
- size: `1282`
- prototype: `void __fastcall(WinRTLocalExpressionBuilder *this)`
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x180105dfc`

## callees

- `0x180004bc0`
- `0x180008428`
- `0x18019385c`
- `0x180216640`
- `0x180392ac4`
- `0x18039332c`
- `0x180393578`
- `0x180393a80`
- `0x180393be4`
- `0x180393c34`
- `0x180393c94`
- `0x1806861f4`
- `0x1806877a8`
- `0x180687890`
- `0x18076e110`
- `0x180c0e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180393887`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18039389d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1803938b3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180393939`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1803939f1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180393a3b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180393887`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18039389d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1803938b3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180393939`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1803939f1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180393a3b`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x180393922`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x18039396c`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1803939a3`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1803939da`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x180393a24`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x180393a6e`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x180393922`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x18039396c`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1803939a3`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1803939da`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x180393a24`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x180393a6e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180393642`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1803936f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18039379b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180393642`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1803936f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18039379b`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall WinRTLocalExpressionBuilder::EnsureLocalExpression(WinRTLocalExpressionBuilder *this)
{
  WinRTLocalExpressionCache *m_cache; // rcx
  Windows::UI::Composition::ICompositor *ptr; // rsi
  Windows::UI::Composition::ICompositor_vtbl *v4; // r13
  HSTRING__ *v5; // r12
  std::wstring *p_strExpression; // rdi
  unsigned __int64 v7; // r15
  unsigned __int64 v8; // rbx
  unsigned int v9; // eax
  UINT32 v10; // edx
  signed int StringReference; // eax
  HRESULT v12; // eax
  HRESULT v13; // ebx
  HRESULT v14; // eax
  HRESULT v15; // ebx
  HRESULT v16; // eax
  HRESULT v17; // ebx
  Windows::UI::Composition::ICompositionAnimation *v18; // rdi
  Windows::UI::Composition::ICompositionAnimation_vtbl *v19; // r13
  unsigned __int64 v20; // rbx
  Windows::UI::Composition::ICompositionObject *v21; // r12
  unsigned int v22; // eax
  UINT32 v23; // edx
  signed int v24; // eax
  HRESULT v25; // eax
  HRESULT v26; // ebx
  Microsoft::WRL::Details::Dummy v27; // r8
  Windows::UI::Composition::ICompositionObject *v28; // rbx
  Windows::UI::Composition::ICompositionObject_vtbl *v29; // r13
  Windows::UI::Composition::ICompositionAnimation *v30; // rsi
  unsigned int v31; // eax
  UINT32 v32; // edx
  signed int v33; // eax
  HRESULT v34; // eax
  HRESULT v35; // ebx
  Windows::UI::Composition::ICompositionAnimation *v36; // rcx
  Windows::UI::Composition::ICompositionObject *v37; // rcx
  Windows::UI::Composition::ICompositionObject *v38; // rcx
  Windows::UI::Composition::ICompositionAnimation *v39; // rcx
  Windows::UI::Composition::ICompositionAnimation *v40; // rsi
  HRESULT (__fastcall *SetReferenceParameter)(Windows::UI::Composition::ICompositionAnimation *, HSTRING__ *, Windows::UI::Composition::ICompositionObject *); // rdi
  Windows::UI::Composition::ICompositionObject *v42; // rbx
  __int64 v43; // rax
  HRESULT v44; // eax
  HRESULT v45; // ebx
  unsigned int cStowedExceptions; // [rsp+20h] [rbp-69h] BYREF
  _STOWED_EXCEPTION_INFORMATION_V2 **ppStowedExceptions; // [rsp+28h] [rbp-61h] BYREF
  Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionAnimation> animation; // [rsp+30h] [rbp-59h] BYREF
  Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionObject> visualCO; // [rsp+38h] [rbp-51h] BYREF
  Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionAnimation> spExpressionAsCompositionAnimation; // [rsp+40h] [rbp-49h] BYREF
  Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionObject> spPropertySetAsCO; // [rsp+48h] [rbp-41h] BYREF
  Microsoft::WRL::Wrappers::HStringReference hstringHeader; // [rsp+50h] [rbp-39h] BYREF
  std::wstring strExpression; // [rsp+70h] [rbp-19h] BYREF

  m_cache = this->m_cache;
  if ( !m_cache->m_localExpression.ptr_ || m_cache->m_transformFlags != this->m_transformFlags )
  {
    WinRTLocalExpressionBuilder::GetExpressionString(this, &strExpression);
    ptr = this->m_winrtContext.m_spCompositor.ptr_;
    v4 = ptr->__vftable;
    v5 = (HSTRING__ *)this->m_cache;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics> *)v5);
    p_strExpression = &strExpression;
    if ( strExpression._Mypair._Myval2._Myres > 7 )
      p_strExpression = (std::wstring *)strExpression._Mypair._Myval2._Bx._Ptr;
    hstringHeader.hstr_ = 0;
    v7 = -1;
    v8 = -1;
    do
      ++v8;
    while ( p_strExpression->_Mypair._Myval2._Bx._Buf[v8] );
    if ( v8 > 0xFFFFFFFF )
      goto LABEL_47;
    v9 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v8);
    v10 = v9 - 1;
    if ( (unsigned int)v8 < v9 )
      v10 = v8;
    StringReference = WindowsCreateStringReference(
                        p_strExpression->_Mypair._Myval2._Bx._Buf,
                        v10,
                        &hstringHeader.header_,
                        &hstringHeader.hstr_);
    if ( StringReference < 0 )
    {
      RaiseException(StringReference, 1u, 0, 0);
      __debugbreak();
    }
    v12 = v4->CreateExpressionAnimationWithExpression(
            ptr,
            hstringHeader.hstr_,
            (Windows::UI::Composition::IExpressionAnimation **)v5);
    v13 = v12;
    v5 = 0;
    if ( v12 < 0 )
    {
      OnFailure_2990_(v12);
      ppStowedExceptions = 0;
      cStowedExceptions = 0;
      TraceForFailFast(v13);
      GetStowedExceptionsForFailFast(&ppStowedExceptions, &cStowedExceptions);
      RoFailFastWithErrorContextInternal2(v13, cStowedExceptions, ppStowedExceptions);
    }
    spExpressionAsCompositionAnimation.ptr_ = 0;
    v14 = Microsoft::WRL::ComPtr<Windows::UI::Composition::IScalarKeyFrameAnimation>::As<Windows::UI::Composition::ICompositionAnimation>(
            &this->m_cache->m_localExpression,
            (Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionAnimation> >)&spExpressionAsCompositionAnimation);
    v15 = v14;
    if ( v14 < 0 )
    {
      OnFailure_2990_(v14);
      ppStowedExceptions = 0;
      cStowedExceptions = 0;
      TraceForFailFast(v15);
      GetStowedExceptionsForFailFast(&ppStowedExceptions, &cStowedExceptions);
      RoFailFastWithErrorContextInternal2(v15, cStowedExceptions, ppStowedExceptions);
    }
    spPropertySetAsCO.ptr_ = 0;
    v16 = Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionPropertySet>::As<Windows::UI::Composition::ICompositionObject>(
            &this->m_cache->m_localExpressionComponentsPS,
            (Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionObject> >)&spPropertySetAsCO);
    v17 = v16;
    if ( v16 < 0 )
    {
      OnFailure_2990_(v16);
      ppStowedExceptions = 0;
      cStowedExceptions = 0;
      TraceForFailFast(v17);
      GetStowedExceptionsForFailFast(&ppStowedExceptions, &cStowedExceptions);
      RoFailFastWithErrorContextInternal2(v17, cStowedExceptions, ppStowedExceptions);
    }
    v18 = spExpressionAsCompositionAnimation.ptr_;
    v19 = spExpressionAsCompositionAnimation.ptr_->__vftable;
    hstringHeader.hstr_ = 0;
    v20 = -1;
    do
      ++v20;
    while ( ExpressionHelper::sc_LocalTransformPropertySetName[v20] );
    if ( v20 > 0xFFFFFFFF )
      goto LABEL_46;
    v21 = spPropertySetAsCO.ptr_;
    v22 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v20);
    v23 = v22 - 1;
    if ( (unsigned int)v20 < v22 )
      v23 = v20;
    v24 = WindowsCreateStringReference(
            ExpressionHelper::sc_LocalTransformPropertySetName,
            v23,
            &hstringHeader.header_,
            &hstringHeader.hstr_);
    if ( v24 < 0 )
    {
      RaiseException(v24, 1u, 0, 0);
      __debugbreak();
    }
    v25 = v19->SetReferenceParameter(v18, hstringHeader.hstr_, v21);
    v26 = v25;
    v5 = 0;
    if ( v25 < 0 )
    {
      OnFailure_2990_(v25);
      ppStowedExceptions = 0;
      cStowedExceptions = 0;
      TraceForFailFast(v26);
      GetStowedExceptionsForFailFast(&ppStowedExceptions, &cStowedExceptions);
      RoFailFastWithErrorContextInternal2(v26, cStowedExceptions, ppStowedExceptions);
    }
    visualCO.ptr_ = 0;
    Microsoft::WRL::ComPtr<Windows::UI::Composition::IAmbientLight>::As<Windows::UI::Composition::ICompositionObject>(
      (Microsoft::WRL::ComPtr<Windows::UI::Composition::ILayerVisual> *)&this->m_visual,
      (Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionObject> >)&visualCO);
    if ( (this->m_transformFlags & 0x20) != 0 )
      goto LABEL_48;
    while ( 1 )
    {
      animation.ptr_ = (Windows::UI::Composition::ICompositionAnimation *)v5;
      Microsoft::WRL::ComPtr<Windows::UI::Composition::IScalarKeyFrameAnimation>::As<Windows::UI::Composition::ICompositionAnimation>(
        &this->m_cache->m_localExpression,
        (Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionAnimation> >)&animation);
      v28 = visualCO.ptr_;
      v29 = visualCO.ptr_->__vftable;
      hstringHeader.hstr_ = v5;
      do
        ++v7;
      while ( ExpressionHelper::sc_propertyName_TransformMatrix[v7] != (_WORD)v5 );
      if ( v7 <= 0xFFFFFFFF )
        break;
      RaiseException(0x80070216, 1u, 0, 0);
LABEL_46:
      RaiseException(0x80070216, 1u, 0, 0);
LABEL_47:
      RaiseException(0x80070216, 1u, 0, 0);
LABEL_48:
      v40 = spExpressionAsCompositionAnimation.ptr_;
      SetReferenceParameter = spExpressionAsCompositionAnimation.ptr_->SetReferenceParameter;
      v42 = visualCO.ptr_;
      Microsoft::WRL::Wrappers::HStringReference::HStringReference(
        &hstringHeader,
        &ExpressionHelper::sc_paramName_Visual,
        v27);
      v44 = SetReferenceParameter(v40, *(HSTRING__ **)(v43 + 24), v42);
      v45 = v44;
      if ( v44 < 0 )
      {
        OnFailure_2990_(v44);
        ppStowedExceptions = (_STOWED_EXCEPTION_INFORMATION_V2 **)v5;
        cStowedExceptions = (unsigned int)v5;
        TraceForFailFast(v45);
        GetStowedExceptionsForFailFast(&ppStowedExceptions, &cStowedExceptions);
        RoFailFastWithErrorContextInternal2(v45, cStowedExceptions, ppStowedExceptions);
      }
    }
    v30 = animation.ptr_;
    v31 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v7);
    v32 = v31 - 1;
    if ( (unsigned int)v7 < v31 )
      v32 = v7;
    v33 = WindowsCreateStringReference(
            ExpressionHelper::sc_propertyName_TransformMatrix,
            v32,
            &hstringHeader.header_,
            &hstringHeader.hstr_);
    if ( v33 < 0 )
    {
      RaiseException(v33, 1u, 0, 0);
      __debugbreak();
    }
    v34 = v29->StartAnimation(v28, hstringHeader.hstr_, v30);
    v35 = v34;
    if ( v34 < 0 )
    {
      OnFailure_2990_(v34);
      ppStowedExceptions = (_STOWED_EXCEPTION_INFORMATION_V2 **)v5;
      cStowedExceptions = (unsigned int)v5;
      TraceForFailFast(v35);
      GetStowedExceptionsForFailFast(&ppStowedExceptions, &cStowedExceptions);
      RoFailFastWithErrorContextInternal2(v35, cStowedExceptions, ppStowedExceptions);
    }
    this->m_cache->m_primaryVisualTransformCookie = DCompTreeHost::SetTracingCookie(
                                                      animation.ptr_,
                                                      PrimaryVisualTransform);
    this->m_cache->m_transformFlags = this->m_transformFlags;
    WinRTLocalExpressionBuilder::ReleaseUnnecessarySubParts(this);
    v36 = animation.ptr_;
    if ( animation.ptr_ )
    {
      animation.ptr_ = (Windows::UI::Composition::ICompositionAnimation *)v5;
      v36->Release(v36);
    }
    v37 = visualCO.ptr_;
    if ( visualCO.ptr_ )
    {
      visualCO.ptr_ = (Windows::UI::Composition::ICompositionObject *)v5;
      v37->Release(v37);
    }
    v38 = spPropertySetAsCO.ptr_;
    if ( spPropertySetAsCO.ptr_ )
    {
      spPropertySetAsCO.ptr_ = (Windows::UI::Composition::ICompositionObject *)v5;
      v38->Release(v38);
    }
    v39 = spExpressionAsCompositionAnimation.ptr_;
    if ( spExpressionAsCompositionAnimation.ptr_ )
    {
      spExpressionAsCompositionAnimation.ptr_ = (Windows::UI::Composition::ICompositionAnimation *)v5;
      v39->Release(v39);
    }
    if ( strExpression._Mypair._Myval2._Myres > 7 )
      std::_Deallocate<16>(strExpression._Mypair._Myval2._Bx._Ptr, 2 * strExpression._Mypair._Myval2._Myres + 2);
  }
}

```

## disassembly

```asm
0x180393578  push    rbp
0x18039357a  push    rbx
0x18039357b  push    rsi
0x18039357c  push    rdi
0x18039357d  push    r12
0x18039357f  push    r13
0x180393581  push    r14
0x180393583  push    r15
0x180393585  lea     rbp, [rsp-1Fh]
0x18039358a  sub     rsp, 0A8h
0x180393591  mov     rax, cs:__security_cookie
0x180393598  xor     rax, rsp
0x18039359b  mov     [rbp+57h+var_50], rax
0x18039359f  mov     r14, this
0x1803935a2  mov     this, [this+30h]
0x1803935a6  xor     ebx, ebx
0x1803935a8  cmp     [this], rbx
0x1803935ab  jz      short loc_1803935D6
0x1803935ad  mov     eax, [r14+38h]
0x1803935b1  cmp     [this+3Ch], eax
0x1803935b4  jnz     short loc_1803935D6
0x1803935b6  mov     this, [rbp+57h+var_50]
0x1803935ba  xor     this, rsp; StackCookie
0x1803935bd  call    __security_check_cookie
0x1803935c2  add     rsp, 0A8h
0x1803935c9  pop     r15
0x1803935cb  pop     r14
0x1803935cd  pop     r13
0x1803935cf  pop     r12
0x1803935d1  pop     rdi
0x1803935d2  pop     rsi
0x1803935d3  pop     rbx
0x1803935d4  pop     rbp
0x1803935d5  retn
0x1803935d6  lea     rdx, [rbp+57h+strExpression]; result
0x1803935da  mov     this, r14; this
0x1803935dd  call    ?GetExpressionString@WinRTLocalExpressionBuilder@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; WinRTLocalExpressionBuilder::GetExpressionString(void)
0x1803935e2  nop
0x1803935e3  mov     rsi, [r14+18h]
0x1803935e7  mov     r13, [rsi]
0x1803935ea  mov     r12, [r14+30h]
0x1803935ee  mov     this, r12; this
0x1803935f1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1803935f6  lea     rdi, [rbp+57h+strExpression]
0x1803935fa  cmp     [rbp+57h+strExpression._Mypair._Myval2._Myres], 7
0x1803935ff  cmova   rdi, qword ptr [rbp+57h+strExpression._Mypair._Myval2._Bx]
0x180393604  mov     [rbp+57h+string], rbx
0x180393608  or      r15, 0FFFFFFFFFFFFFFFFh
0x18039360c  mov     rbx, r15
0x18039360f  xor     eax, eax
0x180393611  inc     rbx
0x180393614  cmp     [rdi+rbx*2], ax
0x180393618  jnz     short loc_180393611
0x18039361a  mov     eax, 0FFFFFFFFh
0x18039361f  cmp     rbx, rax
0x180393622  ja      loc_1803938A4
0x180393628  mov     ecx, ebx; augend
0x18039362a  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18039362f  lea     edx, [rax-1]
0x180393632  cmp     ebx, eax
0x180393634  cmovb   edx, ebx; length
0x180393637  lea     r9, [rbp+57h+string]; string
0x18039363b  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18039363f  mov     this, rdi; sourceString
0x180393642  call    cs:__imp_WindowsCreateStringReference
0x180393648  test    eax, eax
0x18039364a  js      loc_18039392D
0x180393650  mov     r8, r12
0x180393653  mov     rdx, [rbp+57h+string]
0x180393657  mov     this, rsi
0x18039365a  mov     rax, [r13+70h]
0x18039365e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180393663  mov     ebx, eax
0x180393665  xor     r12d, r12d
0x180393668  test    eax, eax
0x18039366a  js      loc_180393940
0x180393670  mov     [rbp+57h+spExpressionAsCompositionAnimation.ptr_], r12
0x180393674  lea     rdx, [rbp+57h+spExpressionAsCompositionAnimation]; p
0x180393678  mov     this, [r14+30h]; this
0x18039367c  call    ??$As@UICompositionAnimation@Composition@UI@Windows@@@?$ComPtr@UIScalarKeyFrameAnimation@Composition@UI@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UICompositionAnimation@Composition@UI@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::UI::Composition::IScalarKeyFrameAnimation>::As<Windows::UI::Composition::ICompositionAnimation>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionAnimation>>)
0x180393681  mov     ebx, eax
0x180393683  test    eax, eax
0x180393685  js      loc_180393977
0x18039368b  mov     [rbp+57h+spPropertySetAsCO.ptr_], r12
0x18039368f  mov     this, [r14+30h]
0x180393693  add     this, 8; this
0x180393697  lea     rdx, [rbp+57h+spPropertySetAsCO]; p
0x18039369b  call    ??$As@UICompositionObject@Composition@UI@Windows@@@?$ComPtr@UICompositionPropertySet@Composition@UI@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UICompositionObject@Composition@UI@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionPropertySet>::As<Windows::UI::Composition::ICompositionObject>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionObject>>)
0x1803936a0  mov     ebx, eax
0x1803936a2  test    eax, eax
0x1803936a4  js      loc_1803939AE
0x1803936aa  mov     rdi, [rbp+57h+spExpressionAsCompositionAnimation.ptr_]
0x1803936ae  mov     r13, [rdi]
0x1803936b1  mov     [rbp+57h+string], r12
0x1803936b5  mov     rsi, cs:?sc_LocalTransformPropertySetName@ExpressionHelper@@2QEBGEB; ushort const * const ExpressionHelper::sc_LocalTransformPropertySetName
0x1803936bc  mov     rbx, r15
0x1803936bf  inc     rbx
0x1803936c2  cmp     [rsi+rbx*2], r12w
0x1803936c7  jnz     short loc_1803936BF
0x1803936c9  mov     eax, 0FFFFFFFFh
0x1803936ce  cmp     rbx, rax
0x1803936d1  ja      loc_18039388E
0x1803936d7  mov     r12, [rbp+57h+spPropertySetAsCO.ptr_]
0x1803936db  mov     ecx, ebx; augend
0x1803936dd  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1803936e2  lea     edx, [rax-1]
0x1803936e5  cmp     ebx, eax
0x1803936e7  cmovb   edx, ebx; length
0x1803936ea  lea     r9, [rbp+57h+string]; string
0x1803936ee  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1803936f2  mov     this, rsi; sourceString
0x1803936f5  call    cs:__imp_WindowsCreateStringReference
0x1803936fb  test    eax, eax
0x1803936fd  js      loc_1803939E5
0x180393703  mov     r8, r12
0x180393706  mov     rdx, [rbp+57h+string]
0x18039370a  mov     this, rdi
0x18039370d  mov     rax, [r13+60h]
0x180393711  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180393716  mov     ebx, eax
0x180393718  xor     r12d, r12d
0x18039371b  test    eax, eax
0x18039371d  js      loc_1803939F8
0x180393723  mov     [rbp+57h+visualCO.ptr_], r12
0x180393727  lea     this, [r14+28h]; this
0x18039372b  lea     rdx, [rbp+57h+visualCO]; p
0x18039372f  call    ??$As@UICompositionObject@Composition@UI@Windows@@@?$ComPtr@UIAmbientLight@Composition@UI@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UICompositionObject@Composition@UI@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::UI::Composition::IAmbientLight>::As<Windows::UI::Composition::ICompositionObject>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionObject>>)
0x180393734  test    byte ptr [r14+38h], 20h
0x180393739  jnz     loc_1803938BA
0x18039373f  mov     [rbp+57h+animation.ptr_], r12
0x180393743  lea     rdx, [rbp+57h+animation]; p
0x180393747  mov     this, [r14+30h]; this
0x18039374b  call    ??$As@UICompositionAnimation@Composition@UI@Windows@@@?$ComPtr@UIScalarKeyFrameAnimation@Composition@UI@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UICompositionAnimation@Composition@UI@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::UI::Composition::IScalarKeyFrameAnimation>::As<Windows::UI::Composition::ICompositionAnimation>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionAnimation>>)
0x180393750  mov     rbx, [rbp+57h+visualCO.ptr_]
0x180393754  mov     r13, [rbx]
0x180393757  mov     [rbp+57h+string], r12
0x18039375b  mov     rdi, cs:?sc_propertyName_TransformMatrix@ExpressionHelper@@2QEBGEB; ushort const * const ExpressionHelper::sc_propertyName_TransformMatrix
0x180393762  inc     r15
0x180393765  cmp     [rdi+r15*2], r12w
0x18039376a  jnz     short loc_180393762
0x18039376c  mov     eax, 0FFFFFFFFh
0x180393771  cmp     r15, rax
0x180393774  ja      loc_180393878
0x18039377a  mov     rsi, [rbp+57h+animation.ptr_]
0x18039377e  mov     ecx, r15d; augend
0x180393781  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180393786  lea     edx, [rax-1]
0x180393789  cmp     r15d, eax
0x18039378c  cmovb   edx, r15d; length
0x180393790  lea     r9, [rbp+57h+string]; string
0x180393794  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180393798  mov     this, rdi; sourceString
0x18039379b  call    cs:__imp_WindowsCreateStringReference
0x1803937a1  test    eax, eax
0x1803937a3  js      loc_180393A2F
0x1803937a9  mov     r8, rsi
0x1803937ac  mov     rdx, [rbp+57h+string]
0x1803937b0  mov     this, rbx
0x1803937b3  mov     rax, [r13+48h]
0x1803937b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803937bc  mov     ebx, eax
0x1803937be  test    eax, eax
0x1803937c0  js      loc_180393A42
0x1803937c6  xor     edx, edx; category
0x1803937c8  mov     this, [rbp+57h+animation.ptr_]; compositionObject
0x1803937cc  call    ?SetTracingCookie@DCompTreeHost@@SAIPEAUIInspectable@@W4TracingCookieCategory@1@@Z; DCompTreeHost::SetTracingCookie(IInspectable *,DCompTreeHost::TracingCookieCategory)
0x1803937d1  mov     rdx, [r14+30h]
0x1803937d5  mov     [rdx+38h], eax
0x1803937d8  mov     rdx, [r14+30h]
0x1803937dc  mov     eax, [r14+38h]
0x1803937e0  mov     [rdx+3Ch], eax
0x1803937e3  mov     this, r14; this
0x1803937e6  call    ?ReleaseUnnecessarySubParts@WinRTLocalExpressionBuilder@@AEAAXXZ; WinRTLocalExpressionBuilder::ReleaseUnnecessarySubParts(void)
0x1803937eb  nop
0x1803937ec  mov     this, [rbp+57h+animation.ptr_]
0x1803937f0  test    this, this
0x1803937f3  jz      short loc_180393806
0x1803937f5  mov     [rbp+57h+animation.ptr_], r12
0x1803937f9  mov     rax, [this]
0x1803937fc  mov     rax, [rax+10h]
0x180393800  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180393805  nop
0x180393806  mov     this, [rbp+57h+visualCO.ptr_]
0x18039380a  test    this, this
0x18039380d  jz      short loc_180393820
0x18039380f  mov     [rbp+57h+visualCO.ptr_], r12
0x180393813  mov     rax, [this]
0x180393816  mov     rax, [rax+10h]
0x18039381a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18039381f  nop
0x180393820  mov     this, [rbp+57h+spPropertySetAsCO.ptr_]
0x180393824  test    this, this
0x180393827  jz      short loc_18039383A
0x180393829  mov     [rbp+57h+spPropertySetAsCO.ptr_], r12
0x18039382d  mov     rax, [this]
0x180393830  mov     rax, [rax+10h]
0x180393834  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180393839  nop
0x18039383a  mov     this, [rbp+57h+spExpressionAsCompositionAnimation.ptr_]
0x18039383e  test    this, this
0x180393841  jz      short loc_180393854
0x180393843  mov     [rbp+57h+spExpressionAsCompositionAnimation.ptr_], r12
0x180393847  mov     rax, [this]
0x18039384a  mov     rax, [rax+10h]
0x18039384e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180393853  nop
0x180393854  mov     rdx, [rbp+57h+strExpression._Mypair._Myval2._Myres]
0x180393858  cmp     rdx, 7
0x18039385c  jbe     loc_1803935B6
0x180393862  lea     rdx, ds:2[rdx*2]; _Bytes
0x18039386a  mov     this, qword ptr [rbp+57h+strExpression._Mypair._Myval2._Bx]; _Ptr
0x18039386e  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180393873  jmp     loc_1803935B6
0x180393878  xor     r9d, r9d; lpArguments
0x18039387b  xor     r8d, r8d; nNumberOfArguments
0x18039387e  lea     edx, [r9+1]; dwExceptionFlags
0x180393882  mov     ecx, 80070216h; dwExceptionCode
0x180393887  call    cs:__imp_RaiseException
0x18039388d  nop
0x18039388e  xor     r9d, r9d; lpArguments
0x180393891  xor     r8d, r8d; nNumberOfArguments
0x180393894  lea     edx, [r9+1]; dwExceptionFlags
0x180393898  mov     ecx, 80070216h; dwExceptionCode
0x18039389d  call    cs:__imp_RaiseException
0x1803938a3  nop
0x1803938a4  xor     r9d, r9d; lpArguments
0x1803938a7  xor     r8d, r8d; nNumberOfArguments
0x1803938aa  lea     edx, [r9+1]; dwExceptionFlags
0x1803938ae  mov     ecx, 80070216h; dwExceptionCode
0x1803938b3  call    cs:__imp_RaiseException
0x1803938b9  nop
0x1803938ba  mov     rsi, [rbp+57h+spExpressionAsCompositionAnimation.ptr_]
0x1803938be  mov     rax, [rsi]
0x1803938c1  mov     rdi, [rax+60h]
0x1803938c5  mov     rbx, [rbp+57h+visualCO.ptr_]
0x1803938c9  lea     rdx, ?sc_paramName_Visual@ExpressionHelper@@2QEBGEB; strRef
0x1803938d0  lea     this, [rbp+57h+hstringHeader]; this
0x1803938d4  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1803938d9  nop
0x1803938da  mov     r8, rbx
0x1803938dd  mov     rdx, [rax+18h]
0x1803938e1  mov     this, rsi
0x1803938e4  mov     rax, rdi
0x1803938e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803938ec  mov     ebx, eax
0x1803938ee  test    eax, eax
0x1803938f0  jns     loc_18039373F
0x1803938f6  mov     ecx, eax; failedFrameHR
0x1803938f8  call    OnFailure_2990_
0x1803938fd  mov     [rbp+57h+ppStowedExceptions], r12
0x180393901  mov     [rbp+57h+cStowedExceptions], r12d
0x180393905  mov     ecx, ebx; errorCode
0x180393907  call    TraceForFailFast
0x18039390c  lea     rdx, [rbp+57h+cStowedExceptions]; pcStowedExceptions
0x180393910  lea     this, [rbp+57h+ppStowedExceptions]; pppStowedExceptions
0x180393914  call    GetStowedExceptionsForFailFast
0x180393919  mov     r8, [rbp+57h+ppStowedExceptions]
0x18039391d  mov     edx, [rbp+57h+cStowedExceptions]
0x180393920  mov     ecx, ebx
0x180393922  call    cs:__imp_?RoFailFastWithErrorContextInternal2@@YAXJKQEAPEAU_STOWED_EXCEPTION_INFORMATION_V2@@@Z; RoFailFastWithErrorContextInternal2(long,ulong,_STOWED_EXCEPTION_INFORMATION_V2 * * const)
0x180393928  jmp     loc_18039373F
0x18039392d  xor     r9d, r9d; lpArguments
0x180393930  xor     r8d, r8d; nNumberOfArguments
0x180393933  lea     edx, [r9+1]; dwExceptionFlags
0x180393937  mov     ecx, eax; dwExceptionCode
0x180393939  call    cs:__imp_RaiseException
0x18039393f  int     3; Trap to Debugger
0x180393940  mov     ecx, ebx; failedFrameHR
0x180393942  call    OnFailure_2990_
0x180393947  mov     [rbp+57h+ppStowedExceptions], r12
0x18039394b  mov     [rbp+57h+cStowedExceptions], r12d
0x18039394f  mov     ecx, ebx; errorCode
0x180393951  call    TraceForFailFast
0x180393956  lea     rdx, [rbp+57h+cStowedExceptions]; pcStowedExceptions
0x18039395a  lea     this, [rbp+57h+ppStowedExceptions]; pppStowedExceptions
0x18039395e  call    GetStowedExceptionsForFailFast
0x180393963  mov     r8, [rbp+57h+ppStowedExceptions]
0x180393967  mov     edx, [rbp+57h+cStowedExceptions]
0x18039396a  mov     ecx, ebx
0x18039396c  call    cs:__imp_?RoFailFastWithErrorContextInternal2@@YAXJKQEAPEAU_STOWED_EXCEPTION_INFORMATION_V2@@@Z; RoFailFastWithErrorContextInternal2(long,ulong,_STOWED_EXCEPTION_INFORMATION_V2 * * const)
0x180393972  jmp     loc_180393670
0x180393977  mov     ecx, ebx; failedFrameHR
0x180393979  call    OnFailure_2990_
0x18039397e  mov     [rbp+57h+ppStowedExceptions], r12
0x180393982  mov     [rbp+57h+cStowedExceptions], r12d
0x180393986  mov     ecx, ebx; errorCode
0x180393988  call    TraceForFailFast
0x18039398d  lea     rdx, [rbp+57h+cStowedExceptions]; pcStowedExceptions
0x180393991  lea     this, [rbp+57h+ppStowedExceptions]; pppStowedExceptions
0x180393995  call    GetStowedExceptionsForFailFast
0x18039399a  mov     r8, [rbp+57h+ppStowedExceptions]
0x18039399e  mov     edx, [rbp+57h+cStowedExceptions]
0x1803939a1  mov     ecx, ebx
0x1803939a3  call    cs:__imp_?RoFailFastWithErrorContextInternal2@@YAXJKQEAPEAU_STOWED_EXCEPTION_INFORMATION_V2@@@Z; RoFailFastWithErrorContextInternal2(long,ulong,_STOWED_EXCEPTION_INFORMATION_V2 * * const)
0x1803939a9  jmp     loc_18039368B
0x1803939ae  mov     ecx, ebx; failedFrameHR
0x1803939b0  call    OnFailure_2990_
0x1803939b5  mov     [rbp+57h+ppStowedExceptions], r12
0x1803939b9  mov     [rbp+57h+cStowedExceptions], r12d
0x1803939bd  mov     ecx, ebx; errorCode
  ... truncated ...
```
