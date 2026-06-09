# FacadeAnimationHelper::StartSingleAnimation(Windows::UI::Composition::ICompositionAnimationBase *,bool)

- ea: `0x18010bbc4`
- end: `0x18010c2e4`
- name: `?StartSingleAnimation@FacadeAnimationHelper@@AEAAJPEAUICompositionAnimationBase@Composition@UI@Windows@@_N@Z`
- size: `1824`
- prototype: `HRESULT __fastcall(FacadeAnimationHelper *this, Windows::UI::Composition::ICompositionAnimationBase *animation, bool isImplicitAnimation)`
- caller_count: `4`
- callee_count: `25`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18010a8e4`
- `0x18010c3c8`
- `0x18056c2ac`
- `0x1809f0e2c`

## callees

- `0x180004bc0`
- `0x180008428`
- `0x180020740`
- `0x180100a40`
- `0x18010b250`
- `0x18010bbc4`
- `0x18010d38c`
- `0x18011c2fc`
- `0x1801292ec`
- `0x1801eb330`
- `0x180283830`
- `0x180390114`
- `0x1803909f8`
- `0x180390aa0`
- `0x180390cc0`
- `0x18051e624`
- `0x18051e758`
- `0x1805b4428`
- `0x1805c30ec`
- `0x1806877a8`
- `0x180687890`
- `0x180689db0`
- `0x1806c84ac`
- `0x18076e110`
- `0x180c0e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18010c259`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18010c259`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x18010c292`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x18010c2cc`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x18010c292`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x18010c2cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010bc09`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010be11`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010c006`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010c074`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010c09d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010c11e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010bc09`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010be11`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010c006`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010c074`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010c09d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010c11e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18010bda1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18010bda1`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18010bdca`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18010bdca`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
__int64 __fastcall FacadeAnimationHelper::StartSingleAnimation(
        FacadeAnimationHelper *this,
        Windows::UI::Composition::ICompositionAnimationBase *animation,
        bool isImplicitAnimation)
{
  bool v3; // r13
  bool v6; // r8
  HRESULT v7; // eax
  HRESULT v8; // ebx
  CDependencyObject *m_object; // rbx
  KnownPropertyIndex v10; // r15
  const CPropertyBase *PropertyBaseByIndex; // rax
  DOFacadeAnimationInfo *FacadeAnimationInfo; // rbx
  Windows::UI::Composition::ICompositor *ptr; // rdi
  HRESULT (__fastcall *CreateScopedBatch)(Windows::UI::Composition::ICompositor *, Windows::UI::Composition::CompositionBatchTypes, Windows::UI::Composition::ICompositionScopedBatch **); // rbx
  HRESULT v15; // eax
  HRESULT (__fastcall *QueryInterface)(IUnknown *, const _GUID *, void **); // rbx
  HRESULT v17; // eax
  CDependencyObject *v18; // r13
  void (__fastcall ***v19)(_QWORD, GUID *, Microsoft::WRL::ComPtr<Windows::UI::Composition::IAnimationObject> *); // rdi
  void (__fastcall *v20)(_QWORD, GUID *, Microsoft::WRL::ComPtr<Windows::UI::Composition::IAnimationObject> *); // rbx
  HSTRING v21; // rbx
  HRESULT ActivationFactory; // eax
  HRESULT v23; // ebx
  Windows::UI::Composition::ICompositionObjectStatics *v24; // rsi
  HRESULT (__fastcall *StartAnimationWithIAnimationObject)(Windows::UI::Composition::ICompositionObjectStatics *, Windows::UI::Composition::IAnimationObject *, HSTRING__ *, Windows::UI::Composition::ICompositionAnimation *); // rdi
  Windows::UI::Composition::ICompositionAnimation *v26; // rbx
  Microsoft::WRL::Wrappers::HString *v27; // rax
  Windows::UI::Composition::ICompositionObjectStatics *v28; // rcx
  Windows::UI::Composition::IAnimationObject *v29; // rcx
  CCoreServices *m_context; // rcx
  IFacadePropertyListener *v31; // rbx
  DOFacadeAnimationInfo *v32; // rsi
  Windows::UI::Composition::ICompositionScopedBatch *v33; // rbx
  Windows::UI::Composition::ICompositionScopedBatch *v34; // rcx
  Windows::UI::Composition::ICompositionScopedBatch *v35; // rdi
  HRESULT (__fastcall *add_Completed)(Windows::UI::Composition::ICompositionScopedBatch *, Windows::Foundation::ITypedEventHandler<IInspectable *,Windows::UI::Composition::CompositionBatchCompletedEventArgs *> *, EventRegistrationToken *); // rbx
  Microsoft::WRL::ComPtr<Windows::Foundation::ITypedEventHandler<IInspectable *,Windows::UI::Composition::CompositionBatchCompletedEventArgs *> > *v37; // rax
  HRESULT v38; // ebx
  IFacadePropertyListener *v39; // rcx
  Windows::UI::Composition::ICompositionAnimation *v40; // rcx
  Windows::UI::Composition::ICompositionScopedBatch *v41; // rcx
  Windows::UI::Composition::ICompositionObject *v42; // rcx
  IPALEvent *m_hasFacadeAnimationsEvent; // rcx
  Microsoft::WRL::Wrappers::HString *AnimationTarget; // rax
  Microsoft::WRL::Wrappers::HString *v46; // rax
  Windows::UI::Composition::ICompositionScopedBatch *v47; // rcx
  Windows::UI::Composition::ICompositionObject *v48; // rcx
  HRESULT v49; // eax
  Windows::UI::Composition::ICompositionObjectStatics *v50; // rcx
  Windows::UI::Composition::IAnimationObject *v51; // rcx
  Windows::UI::Composition::ICompositionAnimation *v52; // rcx
  HRESULT v53; // eax
  KnownPropertyIndex facadeID[2]; // [rsp+30h] [rbp-99h] BYREF
  bool v55; // [rsp+34h] [rbp-95h]
  Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionScopedBatch> scopedBatch; // [rsp+38h] [rbp-91h] BYREF
  Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionObject> backingCO; // [rsp+40h] [rbp-89h] BYREF
  unsigned int cStowedExceptions; // [rsp+48h] [rbp-81h] BYREF
  Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionAnimation> ca; // [rsp+50h] [rbp-79h] BYREF
  Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionObjectStatics> compFactory; // [rsp+58h] [rbp-71h] BYREF
  Microsoft::WRL::ComPtr<Windows::UI::Composition::IAnimationObject> animationObject; // [rsp+60h] [rbp-69h] BYREF
  Microsoft::WRL::ComPtr<IFacadePropertyListener> listener; // [rsp+68h] [rbp-61h] BYREF
  Microsoft::WRL::Wrappers::HString targetProperty; // [rsp+70h] [rbp-59h] BYREF
  _STOWED_EXCEPTION_INFORMATION_V2 **ppStowedExceptions; // [rsp+78h] [rbp-51h] BYREF
  xephemeral_string_ptr currentTarget; // [rsp+80h] [rbp-49h] BYREF
  xephemeral_string_ptr newTarget; // [rsp+98h] [rbp-31h] BYREF
  DeferReferenceGuard guard; // [rsp+B0h] [rbp-19h]
  HSTRING string; // [rsp+C0h] [rbp-9h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+C8h] [rbp-1h] BYREF

  v3 = isImplicitAnimation;
  v55 = isImplicitAnimation;
  facadeID[0] = UnknownType_UnknownProperty;
  WindowsDeleteString(0);
  targetProperty.hstr_ = 0;
  v7 = FacadeAnimationHelper::ValidateTargetProperty(this, animation, v6, facadeID, &targetProperty.hstr_);
  v8 = v7;
  if ( v7 < 0
    || (m_object = this->m_object,
        v10 = facadeID[0],
        PropertyBaseByIndex = DirectUI::MetadataAPI::GetPropertyBaseByIndex(facadeID[0]),
        v7 = CDependencyObject::ValidateStrictnessOnProperty(m_object, PropertyBaseByIndex),
        v8 = v7,
        v7 < 0) )
  {
    OnFailure_2990_(v7);
    goto LABEL_51;
  }
  FacadeAnimationHelper::EnsureBackingCompositionObjectForFacade(this, &backingCO);
  LOBYTE(facadeID[0]) = 0;
  FacadeAnimationInfo = FacadeStorage::TryGetFacadeAnimationInfo(this->m_storage, this->m_object, v10);
  if ( FacadeAnimationInfo )
  {
    AnimationTarget = FacadeAnimationHelper::GetAnimationTarget(
                        (Microsoft::WRL::Wrappers::HString *)&animationObject,
                        animation);
    xephemeral_string_ptr::xephemeral_string_ptr(&newTarget, AnimationTarget->hstr_);
    WindowsDeleteString((HSTRING)animationObject.ptr_);
    animationObject.ptr_ = 0;
    v46 = FacadeAnimationHelper::GetAnimationTarget(
            (Microsoft::WRL::Wrappers::HString *)&compFactory,
            FacadeAnimationInfo->m_animation.ptr_);
    xephemeral_string_ptr::xephemeral_string_ptr(&currentTarget, v46->hstr_);
    WindowsDeleteString((HSTRING)compFactory.ptr_);
    compFactory.ptr_ = 0;
    if ( xstring_ptr_view::Equals(&newTarget.xstring_ptr_view, &currentTarget, xstrCompareCaseInsensitive) )
    {
      LOBYTE(facadeID[0]) = 1;
    }
    else
    {
      v53 = DirectUI::ErrorHelper::OriginateErrorUsingResourceID(-2147024809, 0x101Eu);
      v8 = v53;
      if ( v53 < 0 )
      {
        OnFailure_2990_(v53);
        currentTarget.m_encodedStorage.RuntimeStringHandleMarker = (unsigned __int64)&xstring_ptr_constants::c_xstring_ptr_storage_null;
        currentTarget.m_ephemeralStorage = xstring_ptr_constants::c_xstring_ptr_storage_null;
        newTarget.m_encodedStorage.RuntimeStringHandleMarker = (unsigned __int64)&xstring_ptr_constants::c_xstring_ptr_storage_null;
        newTarget.m_ephemeralStorage = xstring_ptr_constants::c_xstring_ptr_storage_null;
        goto LABEL_54;
      }
    }
  }
  else
  {
    FacadeAnimationHelper::PopulateBackingCompositionObjectWithFacade(this, v10);
  }
  scopedBatch.ptr_ = 0;
  ptr = this->m_context->m_pNWWindowRenderTarget->m_graphicsDeviceManager.m_ptr->m_pDCompTreeHost->m_spCompositor.ptr_;
  CreateScopedBatch = ptr->CreateScopedBatch;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics> *)&scopedBatch);
  v15 = CreateScopedBatch(ptr, CompositionBatchTypes_AllAnimations, &scopedBatch.ptr_);
  v8 = v15;
  if ( v15 < 0 )
  {
    OnFailure_2990_(v15);
LABEL_47:
    v47 = scopedBatch.ptr_;
    if ( scopedBatch.ptr_ )
    {
      scopedBatch.ptr_ = 0;
      v47->Release(v47);
    }
    v48 = backingCO.ptr_;
    if ( backingCO.ptr_ )
    {
      backingCO.ptr_ = 0;
      v48->Release(v48);
    }
    goto LABEL_51;
  }
  ca.ptr_ = 0;
  QueryInterface = animation->QueryInterface;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics> *)&ca);
  v17 = QueryInterface(animation, &GUID_464c4c2c_1caa_4061_9b40_e13fde1503ca, (void **)&ca.ptr_);
  v8 = v17;
  if ( v17 < 0 )
  {
    OnFailure_2990_(v17);
LABEL_61:
    v52 = ca.ptr_;
    if ( ca.ptr_ )
    {
      ca.ptr_ = 0;
      v52->Release(v52);
    }
    goto LABEL_47;
  }
  if ( CDependencyObject::OfTypeByIndex<305>(this->m_object) )
  {
    v18 = this->m_object;
    listener.ptr_ = (IFacadePropertyListener *)this->m_storage;
    guard.m_storage = (FacadeStorage *)listener.ptr_;
    guard.m_object = v18;
    FacadeStorage::EnsureDOFacadeStorage((FacadeStorage *)listener.ptr_, v18)->m_isDeferringReferences = 1;
    animationObject.ptr_ = 0;
    v19 = (void (__fastcall ***)(_QWORD, GUID *, Microsoft::WRL::ComPtr<Windows::UI::Composition::IAnimationObject> *))(this->m_object->m_hasEverHadManagedPeer & 0xFFFFFFFFFFFFFFFEuLL);
    v20 = **v19;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionObjectStatics> *)&animationObject);
    v20(v19, &GUID_e7141e0a_04b8_4fc5_a4dc_195392e57807, &animationObject);
    compFactory.ptr_ = 0;
    if ( WindowsCreateStringReference(
           RuntimeClass_Windows_UI_Composition_CompositionObject,
           0x28u,
           &hstringHeader,
           &string) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    v21 = string;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&compFactory);
    ActivationFactory = RoGetActivationFactory(v21, &GUID_c1ed052f_1ba2_44ba_a904_6a882a0a5adb, &compFactory);
    v23 = ActivationFactory;
    if ( ActivationFactory < 0 )
    {
      OnFailure_2990_(ActivationFactory);
      ppStowedExceptions = 0;
      cStowedExceptions = 0;
      TraceForFailFast(v23);
      GetStowedExceptionsForFailFast(&ppStowedExceptions, &cStowedExceptions);
      RoFailFastWithErrorContextInternal2(v23, cStowedExceptions, ppStowedExceptions);
    }
    v24 = compFactory.ptr_;
    StartAnimationWithIAnimationObject = compFactory.ptr_->StartAnimationWithIAnimationObject;
    v26 = ca.ptr_;
    v27 = FacadeAnimationHelper::GetAnimationTarget((Microsoft::WRL::Wrappers::HString *)&ppStowedExceptions, animation);
    v8 = StartAnimationWithIAnimationObject(v24, animationObject.ptr_, v27->hstr_, v26);
    WindowsDeleteString((HSTRING)ppStowedExceptions);
    if ( v8 >= 0 )
    {
      v28 = compFactory.ptr_;
      if ( compFactory.ptr_ )
      {
        compFactory.ptr_ = 0;
        v28->Release(v28);
      }
      v29 = animationObject.ptr_;
      if ( animationObject.ptr_ )
      {
        animationObject.ptr_ = 0;
        v29->Release(v29);
      }
      FacadeStorage::EnsureDOFacadeStorage((FacadeStorage *)listener.ptr_, v18)->m_isDeferringReferences = 0;
      v3 = v55;
      goto LABEL_18;
    }
    OnFailure_2990_(v8);
    v50 = compFactory.ptr_;
    if ( compFactory.ptr_ )
    {
      compFactory.ptr_ = 0;
      v50->Release(v50);
    }
    v51 = animationObject.ptr_;
    if ( animationObject.ptr_ )
    {
      animationObject.ptr_ = 0;
      v51->Release(v51);
    }
    FacadeStorage::EnsureDOFacadeStorage((FacadeStorage *)listener.ptr_, v18)->m_isDeferringReferences = 0;
    goto LABEL_61;
  }
  v49 = backingCO.ptr_->StartAnimation(backingCO.ptr_, targetProperty.hstr_, ca.ptr_);
  v8 = v49;
  if ( v49 < 0 )
  {
    OnFailure_2990_(v49);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics> *)&ca);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics> *)&scopedBatch);
LABEL_54:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics> *)&backingCO);
LABEL_51:
    WindowsDeleteString(targetProperty.hstr_);
    return (unsigned int)v8;
  }
LABEL_18:
  scopedBatch.ptr_->End(scopedBatch.ptr_);
  m_context = this->m_context;
  if ( _InterlockedIncrement(&m_context->m_facadeAnimationCount) == 1 )
  {
    m_hasFacadeAnimationsEvent = m_context->m_hasFacadeAnimationsEvent;
    if ( m_hasFacadeAnimationsEvent )
      m_hasFacadeAnimationsEvent->Set(m_hasFacadeAnimationsEvent);
  }
  if ( LOBYTE(facadeID[0]) )
  {
    CCoreServices::DecrementActiveFacadeAnimationCount(this->m_context);
  }
  else
  {
    FacadeStorage::GetBackingListener(this->m_storage, &listener, this->m_object);
    v31 = listener.ptr_;
    if ( listener.ptr_ )
      listener.ptr_->OnAnimationStarted(listener.ptr_, backingCO.ptr_, v10);
    if ( v31 )
      v31->Release(v31);
  }
  v32 = FacadeStorage::EnsureFacadeAnimationInfo(this->m_storage, this->m_object, v10);
  v32->m_facadeID = v10;
  Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionAnimationBase>::operator=(&v32->m_animation, animation);
  v33 = scopedBatch.ptr_;
  if ( v32->m_scopedBatch.ptr_ != scopedBatch.ptr_ )
  {
    if ( scopedBatch.ptr_ )
      scopedBatch.ptr_->AddRef(scopedBatch.ptr_);
    v34 = v32->m_scopedBatch.ptr_;
    v32->m_scopedBatch.ptr_ = v33;
    if ( v34 )
      v34->Release(v34);
  }
  v32->m_animationRunning = 1;
  v32->m_isImplicitAnimation = v3;
  v35 = scopedBatch.ptr_;
  add_Completed = scopedBatch.ptr_->add_Completed;
  v37 = this->m_callbacks->CreateCompletedCallback(this->m_callbacks, &listener);
  v38 = add_Completed(v35, v37->ptr_, &v32->m_token);
  v39 = listener.ptr_;
  if ( listener.ptr_ )
  {
    listener.ptr_ = 0;
    v39->Release(v39);
  }
  if ( v38 < 0 )
  {
    OnFailure_2990_(v38);
    listener.ptr_ = 0;
    cStowedExceptions = 0;
    TraceForFailFast(v38);
    GetStowedExceptionsForFailFast((_STOWED_EXCEPTION_INFORMATION_V2 ***)&listener, &cStowedExceptions);
    RoFailFastWithErrorContextInternal2(
      v38,
      cStowedExceptions,
      (struct _STOWED_EXCEPTION_INFORMATION_V2 **const)listener.ptr_);
  }
  FacadeAnimationHelper::InstrumentStartSingleAnimation(v10);
  v40 = ca.ptr_;
  if ( ca.ptr_ )
  {
    ca.ptr_ = 0;
    v40->Release(v40);
  }
  v41 = scopedBatch.ptr_;
  if ( scopedBatch.ptr_ )
  {
    scopedBatch.ptr_ = 0;
    v41->Release(v41);
  }
  v42 = backingCO.ptr_;
  if ( backingCO.ptr_ )
  {
    backingCO.ptr_ = 0;
    v42->Release(v42);
  }
  WindowsDeleteString(targetProperty.hstr_);
  return 0;
}

```

## disassembly

```asm
0x18010bbc4  mov     [rsp-8+arg_10], rbx
0x18010bbc9  push    rbp
0x18010bbca  push    rsi
0x18010bbcb  push    rdi
0x18010bbcc  push    r12
0x18010bbce  push    r13
0x18010bbd0  push    r14
0x18010bbd2  push    r15
0x18010bbd4  lea     rbp, [rsp-27h]
0x18010bbd9  sub     rsp, 0F0h
0x18010bbe0  mov     rax, cs:__security_cookie
0x18010bbe7  xor     rax, rsp
0x18010bbea  mov     [rbp+57h+var_40], rax
0x18010bbee  mov     r13b, isImplicitAnimation
0x18010bbf1  mov     [rsp+120h+var_EC], isImplicitAnimation
0x18010bbf6  mov     r12, animation
0x18010bbf9  mov     r14, this
0x18010bbfc  xor     esi, esi
0x18010bbfe  mov     [rsp+120h+facadeID], si
0x18010bc03  mov     [rbp+57h+targetProperty.hstr_], rsi
0x18010bc07  xor     ecx, ecx; string
0x18010bc09  call    cs:__imp_WindowsDeleteString
0x18010bc0f  mov     [rbp+57h+targetProperty.hstr_], rsi
0x18010bc13  lea     rax, [rbp+57h+targetProperty]
0x18010bc17  mov     [rsp+120h+var_100], rax; animation
0x18010bc1c  lea     r9, [rsp+120h+facadeID]; compositionTarget
0x18010bc21  mov     animation, r12; animation
0x18010bc24  mov     this, r14; this
0x18010bc27  call    ?ValidateTargetProperty@FacadeAnimationHelper@@AEAAJPEAUICompositionAnimationBase@Composition@UI@Windows@@_NPEAW4KnownPropertyIndex@@PEAPEAUHSTRING__@@@Z; FacadeAnimationHelper::ValidateTargetProperty(Windows::UI::Composition::ICompositionAnimationBase *,bool,KnownPropertyIndex *,HSTRING__ * *)
0x18010bc2c  mov     ebx, eax
0x18010bc2e  test    eax, eax
0x18010bc30  js      loc_18010C177
0x18010bc36  mov     rbx, [r14+8]
0x18010bc3a  movzx   r15d, [rsp+120h+facadeID]
0x18010bc40  movzx   ecx, r15w; ePropertyIndex
0x18010bc44  call    ?GetPropertyBaseByIndex@MetadataAPI@DirectUI@@SAPEBVCPropertyBase@@W4KnownPropertyIndex@@@Z; DirectUI::MetadataAPI::GetPropertyBaseByIndex(KnownPropertyIndex)
0x18010bc49  mov     animation, rax; prop
0x18010bc4c  mov     this, rbx; this
0x18010bc4f  call    ?ValidateStrictnessOnProperty@CDependencyObject@@QEAAJPEBVCPropertyBase@@@Z; CDependencyObject::ValidateStrictnessOnProperty(CPropertyBase const *)
0x18010bc54  mov     ebx, eax
0x18010bc56  test    eax, eax
0x18010bc58  js      loc_18010C2D7
0x18010bc5e  lea     animation, [rsp+120h+backingCO]; result
0x18010bc63  mov     this, r14; this
0x18010bc66  call    ?EnsureBackingCompositionObjectForFacade@FacadeAnimationHelper@@AEAA?AV?$ComPtr@UICompositionObject@Composition@UI@Windows@@@WRL@Microsoft@@XZ; FacadeAnimationHelper::EnsureBackingCompositionObjectForFacade(void)
0x18010bc6b  nop
0x18010bc6c  mov     byte ptr [rsp+120h+facadeID], sil
0x18010bc71  movzx   r8d, r15w; facadeID
0x18010bc75  mov     animation, [r14+8]; object
0x18010bc79  mov     this, [r14+18h]; this
0x18010bc7d  call    ?TryGetFacadeAnimationInfo@FacadeStorage@@QEBAPEAVDOFacadeAnimationInfo@@PEBVCDependencyObject@@W4KnownPropertyIndex@@@Z; FacadeStorage::TryGetFacadeAnimationInfo(CDependencyObject const *,KnownPropertyIndex)
0x18010bc82  mov     rbx, rax
0x18010bc85  test    rax, rax
0x18010bc88  jnz     loc_18010C056
0x18010bc8e  movzx   edx, r15w; facadeID
0x18010bc92  mov     this, r14; this
0x18010bc95  call    ?PopulateBackingCompositionObjectWithFacade@FacadeAnimationHelper@@AEAAXW4KnownPropertyIndex@@@Z; FacadeAnimationHelper::PopulateBackingCompositionObjectWithFacade(KnownPropertyIndex)
0x18010bc9a  mov     [rsp+120h+scopedBatch.ptr_], rsi
0x18010bc9f  mov     rax, [r14+10h]
0x18010bca3  mov     this, [rax+660h]
0x18010bcaa  mov     rax, [this+20h]
0x18010bcae  mov     this, [rax+58h]
0x18010bcb2  mov     rdi, [this+1C8h]
0x18010bcb9  mov     rax, [rdi]
0x18010bcbc  mov     rbx, [rax+0A8h]
0x18010bcc3  lea     this, [rsp+120h+scopedBatch]; this
0x18010bcc8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18010bccd  lea     r8, [rsp+120h+scopedBatch]
0x18010bcd2  mov     edx, 5
0x18010bcd7  mov     this, rdi
0x18010bcda  mov     rax, rbx
0x18010bcdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010bce2  mov     ebx, eax
0x18010bce4  test    eax, eax
0x18010bce6  js      loc_18010C0DA
0x18010bcec  mov     [rbp+57h+ca.ptr_], rsi
0x18010bcf0  mov     rax, [r12]
0x18010bcf4  mov     rbx, [rax]
0x18010bcf7  lea     this, [rbp+57h+ca]; this
0x18010bcfb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18010bd00  lea     r8, [rbp+57h+ca]
0x18010bd04  lea     animation, _GUID_464c4c2c_1caa_4061_9b40_e13fde1503ca
0x18010bd0b  mov     this, r12
0x18010bd0e  mov     rax, rbx
0x18010bd11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010bd16  mov     ebx, eax
0x18010bd18  test    eax, eax
0x18010bd1a  js      loc_18010C1EE
0x18010bd20  mov     this, [r14+8]; this
0x18010bd24  call    ??$OfTypeByIndex@$0BDB@@CDependencyObject@@QEBA_NXZ; CDependencyObject::OfTypeByIndex<305>(void)
0x18010bd29  test    al, al
0x18010bd2b  jz      loc_18010C12B
0x18010bd31  mov     r13, [r14+8]
0x18010bd35  mov     rax, [r14+18h]
0x18010bd39  mov     [rbp+57h+listener.ptr_], rax
0x18010bd3d  mov     [rbp+57h+guard.m_storage], rax
0x18010bd41  mov     [rbp+57h+guard.m_object], r13
0x18010bd45  mov     animation, r13; object
0x18010bd48  mov     this, rax; this
0x18010bd4b  call    ?EnsureDOFacadeStorage@FacadeStorage@@AEAAAEAUDOFacadeStorage@@PEBVCDependencyObject@@@Z; FacadeStorage::EnsureDOFacadeStorage(CDependencyObject const *)
0x18010bd50  mov     byte ptr [rax+30h], 1
0x18010bd54  mov     [rbp+57h+animationObject.ptr_], rsi
0x18010bd58  mov     rax, [r14+8]
0x18010bd5c  mov     rdi, [rax+30h]
0x18010bd60  and     rdi, 0FFFFFFFFFFFFFFFEh
0x18010bd64  mov     rax, [rdi]
0x18010bd67  mov     rbx, [rax]
0x18010bd6a  lea     this, [rbp+57h+animationObject]; this
0x18010bd6e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18010bd73  lea     r8, [rbp+57h+animationObject]
0x18010bd77  lea     animation, _GUID_e7141e0a_04b8_4fc5_a4dc_195392e57807
0x18010bd7e  mov     this, rdi
0x18010bd81  mov     rax, rbx
0x18010bd84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010bd89  mov     [rbp+57h+compFactory.ptr_], rsi
0x18010bd8d  lea     r9, [rbp+57h+string]; string
0x18010bd91  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18010bd95  mov     edx, 28h ; '('; length
0x18010bd9a  lea     this, ?RuntimeClass_Windows_UI_Composition_CompositionObject@@3QBGB; sourceString
0x18010bda1  call    cs:__imp_WindowsCreateStringReference
0x18010bda7  test    eax, eax
0x18010bda9  js      loc_18010C24A
0x18010bdaf  mov     rbx, [rbp+57h+string]
0x18010bdb3  lea     this, [rbp+57h+compFactory]; this
0x18010bdb7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18010bdbc  lea     r8, [rbp+57h+compFactory]
0x18010bdc0  lea     animation, _GUID_c1ed052f_1ba2_44ba_a904_6a882a0a5adb
0x18010bdc7  mov     this, rbx
0x18010bdca  call    cs:__imp_RoGetActivationFactory
0x18010bdd0  mov     ebx, eax
0x18010bdd2  test    eax, eax
0x18010bdd4  js      loc_18010C264
0x18010bdda  mov     rsi, [rbp+57h+compFactory.ptr_]
0x18010bdde  mov     rax, [rsi]
0x18010bde1  mov     rdi, [rax+30h]
0x18010bde5  mov     rbx, [rbp+57h+ca.ptr_]
0x18010bde9  mov     animation, r12; animation
0x18010bdec  lea     this, [rbp+57h+ppStowedExceptions]; result
0x18010bdf0  call    ?GetAnimationTarget@FacadeAnimationHelper@@CA?AVHString@Wrappers@WRL@Microsoft@@PEAUICompositionAnimationBase@Composition@UI@Windows@@@Z; FacadeAnimationHelper::GetAnimationTarget(Windows::UI::Composition::ICompositionAnimationBase *)
0x18010bdf5  nop
0x18010bdf6  mov     r9, rbx
0x18010bdf9  mov     r8, [rax]
0x18010bdfc  mov     animation, [rbp+57h+animationObject.ptr_]
0x18010be00  mov     this, rsi
0x18010be03  mov     rax, rdi
0x18010be06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010be0b  mov     ebx, eax
0x18010be0d  mov     this, [rbp+57h+ppStowedExceptions]; string
0x18010be11  call    cs:__imp_WindowsDeleteString
0x18010be17  xor     esi, esi
0x18010be19  test    ebx, ebx
0x18010be1b  js      loc_18010C180
0x18010be21  mov     this, [rbp+57h+compFactory.ptr_]
0x18010be25  test    this, this
0x18010be28  jz      short loc_18010BE3B
0x18010be2a  mov     [rbp+57h+compFactory.ptr_], rsi
0x18010be2e  mov     rax, [this]
0x18010be31  mov     rax, [rax+10h]
0x18010be35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010be3a  nop
0x18010be3b  mov     this, [rbp+57h+animationObject.ptr_]
0x18010be3f  test    this, this
0x18010be42  jz      short loc_18010BE55
0x18010be44  mov     [rbp+57h+animationObject.ptr_], rsi
0x18010be48  mov     rax, [this]
0x18010be4b  mov     rax, [rax+10h]
0x18010be4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010be54  nop
0x18010be55  mov     animation, r13; object
0x18010be58  mov     this, [rbp+57h+listener.ptr_]; this
0x18010be5c  call    ?EnsureDOFacadeStorage@FacadeStorage@@AEAAAEAUDOFacadeStorage@@PEBVCDependencyObject@@@Z; FacadeStorage::EnsureDOFacadeStorage(CDependencyObject const *)
0x18010be61  mov     [rax+30h], sil
0x18010be65  mov     r13b, [rsp+120h+var_EC]
0x18010be6a  mov     this, [rsp+120h+scopedBatch.ptr_]
0x18010be6f  mov     rax, [this]
0x18010be72  mov     rax, [rax+40h]
0x18010be76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010be7b  mov     this, [r14+10h]
0x18010be7f  mov     eax, 1
0x18010be84  lock xadd [this+77Ch], eax
0x18010be8c  inc     eax
0x18010be8e  cmp     eax, 1
0x18010be91  jz      loc_18010C035
0x18010be97  cmp     byte ptr [rsp+120h+facadeID], sil
0x18010be9c  jnz     loc_18010C0CC
0x18010bea2  mov     r8, [r14+8]; object
0x18010bea6  lea     animation, [rbp+57h+listener]; result
0x18010beaa  mov     this, [r14+18h]; this
0x18010beae  call    ?GetBackingListener@FacadeStorage@@QEBA?AV?$ComPtr@UIFacadePropertyListener@@@WRL@Microsoft@@PEBVCDependencyObject@@@Z; FacadeStorage::GetBackingListener(CDependencyObject const *)
0x18010beb3  nop
0x18010beb4  mov     rbx, [rbp+57h+listener.ptr_]
0x18010beb8  test    rbx, rbx
0x18010bebb  jz      short loc_18010BED6
0x18010bebd  mov     rax, [rbx]
0x18010bec0  movzx   r8d, r15w
0x18010bec4  mov     animation, [rsp+120h+backingCO.ptr_]
0x18010bec9  mov     this, rbx
0x18010becc  mov     rax, [rax+68h]
0x18010bed0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010bed5  nop
0x18010bed6  test    rbx, rbx
0x18010bed9  jz      short loc_18010BEEA
0x18010bedb  mov     rax, [rbx]
0x18010bede  mov     this, rbx
0x18010bee1  mov     rax, [rax+10h]
0x18010bee5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010beea  movzx   r8d, r15w; facadeID
0x18010beee  mov     animation, [r14+8]; object
0x18010bef2  mov     this, [r14+18h]; this
0x18010bef6  call    ?EnsureFacadeAnimationInfo@FacadeStorage@@QEAAAEAVDOFacadeAnimationInfo@@PEBVCDependencyObject@@W4KnownPropertyIndex@@@Z; FacadeStorage::EnsureFacadeAnimationInfo(CDependencyObject const *,KnownPropertyIndex)
0x18010befb  mov     rsi, rax
0x18010befe  mov     [rax], r15w
0x18010bf02  lea     this, [rax+8]; this
0x18010bf06  mov     animation, r12; other
0x18010bf09  call    ??4?$ComPtr@UICompositionAnimationBase@Composition@UI@Windows@@@WRL@Microsoft@@QEAAAEAV012@PEAUICompositionAnimationBase@Composition@UI@Windows@@@Z; Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionAnimationBase>::operator=(Windows::UI::Composition::ICompositionAnimationBase *)
0x18010bf0e  mov     rbx, [rsp+120h+scopedBatch.ptr_]
0x18010bf13  xor     r12d, r12d
0x18010bf16  cmp     [rsi+10h], rbx
0x18010bf1a  jz      short loc_18010BF49
0x18010bf1c  test    rbx, rbx
0x18010bf1f  jz      short loc_18010BF30
0x18010bf21  mov     this, [rbx]
0x18010bf24  mov     rax, [this+8]
0x18010bf28  mov     this, rbx
0x18010bf2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010bf30  mov     this, [rsi+10h]
0x18010bf34  mov     [rsi+10h], rbx
0x18010bf38  test    this, this
0x18010bf3b  jz      short loc_18010BF49
0x18010bf3d  mov     rax, [this]
0x18010bf40  mov     rax, [rax+10h]
0x18010bf44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010bf49  mov     byte ptr [rsi+20h], 1
0x18010bf4d  mov     [rsi+21h], r13b
0x18010bf51  mov     rdi, [rsp+120h+scopedBatch.ptr_]
0x18010bf56  mov     rax, [rdi]
0x18010bf59  mov     rbx, [rax+58h]
0x18010bf5d  mov     this, [r14]
0x18010bf60  mov     animation, [this]
0x18010bf63  mov     rax, [animation+30h]
0x18010bf67  lea     animation, [rbp+57h+listener]
0x18010bf6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010bf70  nop
0x18010bf71  lea     r8, [rsi+18h]
0x18010bf75  mov     animation, [rax]
0x18010bf78  mov     this, rdi
0x18010bf7b  mov     rax, rbx
0x18010bf7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010bf83  mov     ebx, eax
0x18010bf85  mov     this, [rbp+57h+listener.ptr_]
0x18010bf89  test    this, this
0x18010bf8c  jz      short loc_18010BF9E
0x18010bf8e  mov     [rbp+57h+listener.ptr_], r12
0x18010bf92  mov     animation, [this]
0x18010bf95  mov     rax, [animation+10h]
0x18010bf99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010bf9e  test    ebx, ebx
0x18010bfa0  js      loc_18010C29D
0x18010bfa6  movzx   ecx, r15w; facadeID
0x18010bfaa  call    ?InstrumentStartSingleAnimation@FacadeAnimationHelper@@CAXW4KnownPropertyIndex@@@Z; FacadeAnimationHelper::InstrumentStartSingleAnimation(KnownPropertyIndex)
0x18010bfaf  nop
0x18010bfb0  mov     this, [rbp+57h+ca.ptr_]
0x18010bfb4  test    this, this
0x18010bfb7  jz      short loc_18010BFCA
0x18010bfb9  mov     [rbp+57h+ca.ptr_], r12
0x18010bfbd  mov     rax, [this]
0x18010bfc0  mov     rax, [rax+10h]
0x18010bfc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010bfc9  nop
0x18010bfca  mov     this, [rsp+120h+scopedBatch.ptr_]
0x18010bfcf  test    this, this
0x18010bfd2  jz      short loc_18010BFE6
0x18010bfd4  mov     [rsp+120h+scopedBatch.ptr_], r12
0x18010bfd9  mov     rax, [this]
0x18010bfdc  mov     rax, [rax+10h]
0x18010bfe0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010bfe5  nop
0x18010bfe6  mov     this, [rsp+120h+backingCO.ptr_]
0x18010bfeb  test    this, this
0x18010bfee  jz      short loc_18010C002
0x18010bff0  mov     [rsp+120h+backingCO.ptr_], r12
0x18010bff5  mov     rax, [this]
0x18010bff8  mov     rax, [rax+10h]
0x18010bffc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010c001  nop
0x18010c002  mov     this, [rbp+57h+targetProperty.hstr_]; string
0x18010c006  call    cs:__imp_WindowsDeleteString
0x18010c00c  xor     eax, eax
0x18010c00e  mov     this, [rbp+57h+var_40]
0x18010c012  xor     this, rsp; StackCookie
0x18010c015  call    __security_check_cookie
0x18010c01a  mov     rbx, [rsp+120h+arg_10]
0x18010c022  add     rsp, 0F0h
0x18010c029  pop     r15
0x18010c02b  pop     r14
0x18010c02d  pop     r13
0x18010c02f  pop     r12
0x18010c031  pop     rdi
0x18010c032  pop     rsi
0x18010c033  pop     rbp
  ... truncated ...
```
