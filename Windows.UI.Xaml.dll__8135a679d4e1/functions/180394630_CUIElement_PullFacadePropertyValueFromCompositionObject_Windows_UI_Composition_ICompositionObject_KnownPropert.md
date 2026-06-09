# CUIElement::PullFacadePropertyValueFromCompositionObject(Windows::UI::Composition::ICompositionObject *,KnownPropertyIndex)

- ea: `0x180394630`
- end: `0x180394ceb`
- name: `?PullFacadePropertyValueFromCompositionObject@CUIElement@@QEAAJPEAUICompositionObject@Composition@UI@Windows@@W4KnownPropertyIndex@@@Z`
- size: `1723`
- prototype: `HRESULT __fastcall(CUIElement *this, Windows::UI::Composition::ICompositionObject *backingCO, KnownPropertyIndex facadeID)`
- caller_count: `1`
- callee_count: `25`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1803960f0`

## callees

- `0x180004bc0`
- `0x180008428`
- `0x180108510`
- `0x180108d10`
- `0x18010b6c0`
- `0x180115f88`
- `0x180116238`
- `0x180119c64`
- `0x1802ed308`
- `0x180394630`
- `0x1804d99ec`
- `0x1804d9a8c`
- `0x1804d9fc0`
- `0x1804da0bc`
- `0x1804dea40`
- `0x1806196d8`
- `0x1806877a8`
- `0x180687890`
- `0x18076e110`
- `0x18076f0a4`
- `0x1809c8960`
- `0x1809c89f8`
- `0x1809e1ef4`
- `0x1809e1f40`
- `0x180c0e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18039487e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180394c69`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18039487e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180394c69`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1803948b7`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x180394966`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x180394a2c`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x180394ad9`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x180394b86`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x180394c3a`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x180394ca2`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x180394cdf`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1803948b7`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x180394966`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x180394a2c`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x180394ad9`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x180394b86`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x180394c3a`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x180394ca2`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x180394cdf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1803946d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1803947f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1803946d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1803947f1`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CUIElement::PullFacadePropertyValueFromCompositionObject(
        CUIElement *this,
        Windows::UI::Composition::ICompositionObject *backingCO,
        unsigned __int16 facadeID)
{
  int v3; // r14d
  HRESULT (__fastcall *QueryInterface)(IUnknown *, const _GUID *, void **); // rbx
  HRESULT v7; // eax
  unsigned int v8; // ebx
  Windows::UI::Composition::ICompositionPropertySet *ptr; // rbx
  Windows::UI::Composition::ICompositionPropertySet_vtbl *v10; // rdi
  signed int StringReference; // eax
  HRESULT v12; // eax
  HRESULT v13; // ebx
  HRESULT v14; // eax
  HRESULT v15; // ebx
  Windows::UI::Composition::ICompositionPropertySet *v16; // rcx
  Windows::UI::Composition::ICompositionPropertySet *v18; // rcx
  Windows::UI::Composition::ICompositionPropertySet *v19; // rbx
  Windows::UI::Composition::ICompositionPropertySet_vtbl *v20; // rdi
  signed int v21; // eax
  HRESULT v22; // eax
  SimpleProperty::details::tag_storage<1> v23; // r8
  HRESULT v24; // ebx
  Windows::UI::Composition::ICompositionPropertySet *v25; // rdi
  HRESULT (__fastcall *TryGetMatrix4x4)(Windows::UI::Composition::ICompositionPropertySet *, HSTRING__ *, Windows::Foundation::Numerics::Matrix4x4 *, Windows::UI::Composition::CompositionGetValueStatus *); // rbx
  HRESULT v27; // eax
  SimpleProperty::details::tag_storage<1> v28; // r8
  HRESULT v29; // ebx
  Windows::UI::Composition::ICompositionPropertySet *v30; // rdi
  HRESULT (__fastcall *v31)(Windows::UI::Composition::ICompositionPropertySet *, HSTRING__ *, Windows::Foundation::Numerics::Vector3 *, Windows::UI::Composition::CompositionGetValueStatus *); // rbx
  HRESULT v32; // eax
  SimpleProperty::details::tag_storage<1> v33; // r8
  HRESULT v34; // ebx
  Windows::UI::Composition::ICompositionPropertySet *v35; // rdi
  HRESULT (__fastcall *v36)(Windows::UI::Composition::ICompositionPropertySet *, HSTRING__ *, Windows::Foundation::Numerics::Vector3 *, Windows::UI::Composition::CompositionGetValueStatus *); // rbx
  HRESULT v37; // eax
  SimpleProperty::details::tag_storage<1> v38; // r8
  HRESULT v39; // ebx
  Windows::UI::Composition::ICompositionPropertySet *v40; // rdi
  HRESULT (__fastcall *TryGetScalar)(Windows::UI::Composition::ICompositionPropertySet *, HSTRING__ *, float *, Windows::UI::Composition::CompositionGetValueStatus *); // rbx
  HRESULT v42; // eax
  SimpleProperty::details::tag_storage<1> v43; // r8
  HRESULT v44; // ebx
  Windows::UI::Composition::ICompositionPropertySet *v45; // rdi
  HRESULT (__fastcall *TryGetVector3)(Windows::UI::Composition::ICompositionPropertySet *, HSTRING__ *, Windows::Foundation::Numerics::Vector3 *, Windows::UI::Composition::CompositionGetValueStatus *); // rbx
  HRESULT v47; // eax
  SimpleProperty::details::tag_storage<1> v48; // r8
  HRESULT v49; // ebx
  unsigned int cStowedExceptions; // [rsp+30h] [rbp-D0h] BYREF
  _STOWED_EXCEPTION_INFORMATION_V2 **ppStowedExceptions; // [rsp+38h] [rbp-C8h] BYREF
  Windows::UI::Composition::CompositionGetValueStatus status; // [rsp+40h] [rbp-C0h] BYREF
  Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionPropertySet> backingPS; // [rsp+48h] [rbp-B8h] BYREF
  float rotation; // [rsp+50h] [rbp-B0h] BYREF
  float opacity; // [rsp+54h] [rbp-ACh] BYREF
  Microsoft::WRL::Wrappers::HStringReference hstringHeader; // [rsp+58h] [rbp-A8h] BYREF
  Windows::Foundation::Numerics::Vector3 translation; // [rsp+78h] [rbp-88h] BYREF
  Windows::Foundation::Numerics::Vector3 scale; // [rsp+88h] [rbp-78h] BYREF
  Windows::Foundation::Numerics::Vector3 rotationAxis; // [rsp+98h] [rbp-68h] BYREF
  Windows::Foundation::Numerics::Vector3 centerPoint; // [rsp+A8h] [rbp-58h] BYREF
  Windows::Foundation::Numerics::Matrix4x4 transformMatrix; // [rsp+C0h] [rbp-40h] BYREF

  v3 = facadeID;
  backingPS.ptr_ = 0;
  QueryInterface = backingCO->QueryInterface;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics> *)&backingPS);
  v7 = QueryInterface(backingCO, &GUID_c9d6d202_5f67_4453_9117_9eadd430d3c2, (void **)&backingPS.ptr_);
  v8 = v7;
  if ( v7 >= 0 )
  {
    status = CompositionGetValueStatus_Succeeded;
    switch ( v3 )
    {
      case 453:
        opacity = 0.0;
        ptr = backingPS.ptr_;
        v10 = backingPS.ptr_->__vftable;
        hstringHeader.hstr_ = 0;
        StringReference = WindowsCreateStringReference(
                            FacadeProperty_Opacity,
                            7u,
                            &hstringHeader.header_,
                            &hstringHeader.hstr_);
        if ( StringReference < 0 )
        {
          RaiseException(StringReference, 1u, 0, 0);
          __debugbreak();
        }
        v12 = v10->TryGetScalar(ptr, hstringHeader.hstr_, &opacity, &status);
        v13 = v12;
        if ( v12 < 0 )
        {
          OnFailure_2990_(v12);
          ppStowedExceptions = 0;
          cStowedExceptions = 0;
          TraceForFailFast(v13);
          GetStowedExceptionsForFailFast(&ppStowedExceptions, &cStowedExceptions);
          RoFailFastWithErrorContextInternal2(v13, cStowedExceptions, ppStowedExceptions);
        }
        v14 = CDependencyObject::SetValueByKnownIndex(this, UIElement_Opacity, opacity);
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
        goto LABEL_8;
      case 2074:
        *(_QWORD *)&centerPoint.X = 0;
        centerPoint.Z = 0.0;
        v45 = backingPS.ptr_;
        TryGetVector3 = backingPS.ptr_->TryGetVector3;
        hstringHeader.hstr_ = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(
          &hstringHeader,
          FacadeProperty_CenterPoint,
          0xCu,
          0xBu);
        v47 = TryGetVector3(v45, hstringHeader.hstr_, &centerPoint, &status);
        v49 = v47;
        if ( v47 < 0 )
        {
          OnFailure_2990_(v47);
          ppStowedExceptions = 0;
          cStowedExceptions = 0;
          TraceForFailFast(v49);
          GetStowedExceptionsForFailFast(&ppStowedExceptions, &cStowedExceptions);
          RoFailFastWithErrorContextInternal2(v49, cStowedExceptions, ppStowedExceptions);
        }
        SimpleProperty::details::SetImpl_2074_(this, &centerPoint, v48);
        CUIElement::UpdateHasNonZeroCenterPoint(this, &centerPoint);
        break;
      case 2077:
        rotation = 0.0;
        v40 = backingPS.ptr_;
        TryGetScalar = backingPS.ptr_->TryGetScalar;
        hstringHeader.hstr_ = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, FacadeProperty_Rotation, 9u, 8u);
        v42 = TryGetScalar(v40, hstringHeader.hstr_, &rotation, &status);
        v44 = v42;
        if ( v42 < 0 )
        {
          OnFailure_2990_(v42);
          ppStowedExceptions = 0;
          cStowedExceptions = 0;
          TraceForFailFast(v44);
          GetStowedExceptionsForFailFast(&ppStowedExceptions, &cStowedExceptions);
          RoFailFastWithErrorContextInternal2(v44, cStowedExceptions, ppStowedExceptions);
        }
        SimpleProperty::details::SetImpl_2077_(this, rotation, v43);
        CUIElement::UpdateHasNonZeroRotation(this, rotation);
        break;
      case 2078:
        *(_QWORD *)&rotationAxis.X = 0;
        rotationAxis.Z = 0.0;
        v35 = backingPS.ptr_;
        v36 = backingPS.ptr_->TryGetVector3;
        hstringHeader.hstr_ = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(
          &hstringHeader,
          FacadeProperty_RotationAxis,
          0xDu,
          0xCu);
        v37 = v36(v35, hstringHeader.hstr_, &rotationAxis, &status);
        v39 = v37;
        if ( v37 < 0 )
        {
          OnFailure_2990_(v37);
          ppStowedExceptions = 0;
          cStowedExceptions = 0;
          TraceForFailFast(v39);
          GetStowedExceptionsForFailFast(&ppStowedExceptions, &cStowedExceptions);
          RoFailFastWithErrorContextInternal2(v39, cStowedExceptions, ppStowedExceptions);
        }
        SimpleProperty::details::SetImpl_2078_(this, &rotationAxis, v38);
        CUIElement::UpdateHasNonDefaultRotationAxis(this, &rotationAxis);
        break;
      case 2079:
        *(_QWORD *)&scale.X = 0;
        scale.Z = 0.0;
        v30 = backingPS.ptr_;
        v31 = backingPS.ptr_->TryGetVector3;
        hstringHeader.hstr_ = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, FacadeProperty_Scale, 6u, 5u);
        v32 = v31(v30, hstringHeader.hstr_, &scale, &status);
        v34 = v32;
        if ( v32 < 0 )
        {
          OnFailure_2990_(v32);
          ppStowedExceptions = 0;
          cStowedExceptions = 0;
          TraceForFailFast(v34);
          GetStowedExceptionsForFailFast(&ppStowedExceptions, &cStowedExceptions);
          RoFailFastWithErrorContextInternal2(v34, cStowedExceptions, ppStowedExceptions);
        }
        SimpleProperty::details::SetImpl_2079_(this, &scale, v33);
        CUIElement::UpdateHasScaleZ(this, &scale);
        break;
      case 2081:
        memset_0(&transformMatrix, 0, sizeof(transformMatrix));
        v25 = backingPS.ptr_;
        TryGetMatrix4x4 = backingPS.ptr_->TryGetMatrix4x4;
        hstringHeader.hstr_ = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(
          &hstringHeader,
          FacadeProperty_TransformMatrix,
          0x10u,
          0xFu);
        v27 = TryGetMatrix4x4(v25, hstringHeader.hstr_, &transformMatrix, &status);
        v29 = v27;
        if ( v27 < 0 )
        {
          OnFailure_2990_(v27);
          ppStowedExceptions = 0;
          cStowedExceptions = 0;
          TraceForFailFast(v29);
          GetStowedExceptionsForFailFast(&ppStowedExceptions, &cStowedExceptions);
          RoFailFastWithErrorContextInternal2(v29, cStowedExceptions, ppStowedExceptions);
        }
        SimpleProperty::details::SetImpl_2081_(this, &transformMatrix, v28);
        CUIElement::UpdateHasNonIdentityTransformMatrix(this, &transformMatrix);
        CUIElement::NWSetTransformDirty(this, PerThread);
        CUIElement::OnTransformMatrixForHitTestingChanged(this, &transformMatrix);
        goto LABEL_8;
      case 2082:
        *(_QWORD *)&translation.X = 0;
        translation.Z = 0.0;
        v19 = backingPS.ptr_;
        v20 = backingPS.ptr_->__vftable;
        hstringHeader.hstr_ = 0;
        v21 = WindowsCreateStringReference(
                FacadeProperty_Translation_0,
                0xBu,
                &hstringHeader.header_,
                &hstringHeader.hstr_);
        if ( v21 < 0 )
        {
          RaiseException(v21, 1u, 0, 0);
          __debugbreak();
        }
        v22 = v20->TryGetVector3(v19, hstringHeader.hstr_, &translation, &status);
        v24 = v22;
        if ( v22 < 0 )
        {
          OnFailure_2990_(v22);
          ppStowedExceptions = 0;
          cStowedExceptions = 0;
          TraceForFailFast(v24);
          GetStowedExceptionsForFailFast(&ppStowedExceptions, &cStowedExceptions);
          RoFailFastWithErrorContextInternal2(v24, cStowedExceptions, ppStowedExceptions);
        }
        SimpleProperty::details::SetImpl_2082_(this, &translation, v23);
        if ( translation.Z == 0.0 )
        {
          if ( (*((_DWORD *)this + 38) & 0x40) != 0 )
            CUIElement::UnsetRequiresComposition(this, IElementFactory, None);
        }
        else if ( (*((_DWORD *)this + 38) & 0x40) == 0 )
        {
          CUIElement::SetRequiresComposition(this, IElementFactory, None);
        }
        break;
      default:
LABEL_8:
        v16 = backingPS.ptr_;
        if ( backingPS.ptr_ )
        {
          backingPS.ptr_ = 0;
          v16->Release(v16);
        }
        return 0;
    }
    CUIElement::NWSetTransformDirty(this, PerThread);
    goto LABEL_8;
  }
  OnFailure_2990_(v7);
  v18 = backingPS.ptr_;
  if ( backingPS.ptr_ )
  {
    backingPS.ptr_ = 0;
    v18->Release(v18);
  }
  return v8;
}

```

## disassembly

```asm
0x180394630  mov     [rsp-8+arg_10], rbx
0x180394635  push    rbp
0x180394636  push    rsi
0x180394637  push    rdi
0x180394638  push    r14
0x18039463a  push    r15
0x18039463c  lea     rbp, [rsp-10h]
0x180394641  sub     rsp, 110h
0x180394648  mov     rax, cs:__security_cookie
0x18039464f  xor     rax, rsp
0x180394652  mov     [rbp+30h+var_30], rax
0x180394656  movzx   r14d, facadeID
0x18039465a  mov     rdi, backingCO
0x18039465d  mov     rsi, this
0x180394660  xor     r15d, r15d
0x180394663  mov     [rsp+130h+backingPS.ptr_], r15
0x180394668  mov     rax, [backingCO]
0x18039466b  mov     rbx, [rax]
0x18039466e  lea     this, [rsp+130h+backingPS]; this
0x180394673  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180394678  lea     r8, [rsp+130h+backingPS]
0x18039467d  lea     backingCO, _GUID_c9d6d202_5f67_4453_9117_9eadd430d3c2
0x180394684  mov     this, rdi
0x180394687  mov     rax, rbx
0x18039468a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18039468f  mov     ebx, eax
0x180394691  test    eax, eax
0x180394693  js      loc_180394766
0x180394699  mov     [rsp+130h+status], r15d
0x18039469e  mov     ecx, r14d
0x1803946a1  mov     r14d, 1C5h
0x1803946a7  sub     ecx, r14d
0x1803946aa  jnz     loc_18039478D
0x1803946b0  mov     [rsp+130h+opacity], ecx
0x1803946b4  mov     rbx, [rsp+130h+backingPS.ptr_]
0x1803946b9  mov     rdi, [rbx]
0x1803946bc  mov     [rsp+130h+string], r15
0x1803946c1  lea     r9, [rsp+130h+string]; string
0x1803946c6  lea     r8, [rsp+130h+hstringHeader]; hstringHeader
0x1803946cb  lea     edx, [this+7]; length
0x1803946ce  lea     this, FacadeProperty_Opacity; sourceString
0x1803946d5  call    cs:__imp_WindowsCreateStringReference
0x1803946db  test    eax, eax
0x1803946dd  js      loc_180394C5D
0x1803946e3  lea     r9, [rsp+130h+status]
0x1803946e8  lea     r8, [rsp+130h+opacity]
0x1803946ed  mov     backingCO, [rsp+130h+string]
0x1803946f2  mov     this, rbx
0x1803946f5  mov     rax, [rdi+90h]
0x1803946fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180394701  mov     ebx, eax
0x180394703  test    eax, eax
0x180394705  js      loc_180394C70
0x18039470b  mov     edx, r14d; index
0x18039470e  movss   xmm2, [rsp+130h+opacity]; value
0x180394714  mov     this, rsi; this
0x180394717  call    ?SetValueByKnownIndex@CDependencyObject@@QEAAJW4KnownPropertyIndex@@M@Z; CDependencyObject::SetValueByKnownIndex(KnownPropertyIndex,float)
0x18039471c  mov     ebx, eax
0x18039471e  test    eax, eax
0x180394720  js      loc_180394CAD
0x180394726  mov     this, [rsp+130h+backingPS.ptr_]
0x18039472b  test    this, this
0x18039472e  jz      short loc_180394741
0x180394730  mov     [rsp+130h+backingPS.ptr_], r15
0x180394735  mov     rax, [this]
0x180394738  mov     rax, [rax+10h]
0x18039473c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180394741  xor     eax, eax
0x180394743  mov     this, [rbp+30h+var_30]
0x180394747  xor     this, rsp; StackCookie
0x18039474a  call    __security_check_cookie
0x18039474f  mov     rbx, [rsp+130h+arg_10]
0x180394757  add     rsp, 110h
0x18039475e  pop     r15
0x180394760  pop     r14
0x180394762  pop     rdi
0x180394763  pop     rsi
0x180394764  pop     rbp
0x180394765  retn
0x180394766  mov     ecx, ebx; failedFrameHR
0x180394768  call    OnFailure_2990_
0x18039476d  nop
0x18039476e  mov     this, [rsp+130h+backingPS.ptr_]
0x180394773  test    this, this
0x180394776  jz      short loc_180394789
0x180394778  mov     [rsp+130h+backingPS.ptr_], r15
0x18039477d  mov     rax, [this]
0x180394780  mov     rax, [rax+10h]
0x180394784  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180394789  mov     eax, ebx
0x18039478b  jmp     short loc_180394743
0x18039478d  sub     ecx, 655h
0x180394793  jz      loc_180394BB0
0x180394799  sub     ecx, 3
0x18039479c  jz      loc_180394AFC
0x1803947a2  sub     ecx, 1
0x1803947a5  jz      loc_180394A4F
0x1803947ab  sub     ecx, 1
0x1803947ae  jz      loc_1803949A2
0x1803947b4  sub     ecx, 2
0x1803947b7  jz      loc_1803948D6
0x1803947bd  cmp     ecx, 1
0x1803947c0  jnz     loc_180394726
0x1803947c6  xor     eax, eax
0x1803947c8  mov     qword ptr [rsp+130h+translation.X], rax
0x1803947cd  mov     [rbp+30h+translation.Z], eax
0x1803947d0  mov     rbx, [rsp+130h+backingPS.ptr_]
0x1803947d5  mov     rdi, [rbx]
0x1803947d8  mov     [rsp+130h+string], r15
0x1803947dd  lea     r9, [rsp+130h+string]; string
0x1803947e2  lea     r8, [rsp+130h+hstringHeader]; hstringHeader
0x1803947e7  lea     edx, [this+0Ah]; length
0x1803947ea  lea     this, FacadeProperty_Translation_0; sourceString
0x1803947f1  call    cs:__imp_WindowsCreateStringReference
0x1803947f7  test    eax, eax
0x1803947f9  js      short loc_180394872
0x1803947fb  lea     r9, [rsp+130h+status]
0x180394800  lea     r8, [rsp+130h+translation]
0x180394805  mov     backingCO, [rsp+130h+string]
0x18039480a  mov     this, rbx
0x18039480d  mov     rax, [rdi+0A0h]
0x180394814  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180394819  mov     ebx, eax
0x18039481b  test    eax, eax
0x18039481d  js      short loc_180394885
0x18039481f  lea     backingCO, [rsp+130h+translation]; value
0x180394824  mov     this, rsi; obj
0x180394827  call    SimpleProperty__details__SetImpl_2082_
0x18039482c  mov     eax, [rsi+98h]
0x180394832  shr     eax, 6
0x180394835  and     al, 1
0x180394837  movss   xmm0, [rbp+30h+translation.Z]
0x18039483c  ucomiss xmm0, cs:__real@00000000
0x180394843  jp      short loc_18039485D
0x180394845  jnz     short loc_18039485D
0x180394847  test    al, al
0x180394849  jnz     short loc_1803948C2
0x18039484b  mov     edx, 1; flags
0x180394850  mov     this, rsi; pTarget
0x180394853  call    ?NWSetTransformDirty@CUIElement@@SAXPEAVCDependencyObject@@W4Value@DirtyFlags@@@Z; CUIElement::NWSetTransformDirty(CDependencyObject *,DirtyFlags::Value)
0x180394858  jmp     loc_180394726
0x18039485d  test    al, al
0x18039485f  jnz     short loc_18039484B
0x180394861  xor     r8d, r8d; detailedAnimationReason
0x180394864  lea     edx, [r8+17h]; compositionReason
0x180394868  mov     this, rsi; this
0x18039486b  call    ?SetRequiresComposition@CUIElement@@UEAAJW4Value@CompositionRequirement@@W42IndependentAnimationType@@@Z; CUIElement::SetRequiresComposition(CompositionRequirement::Value,IndependentAnimationType::Value)
0x180394870  jmp     short loc_18039484B
0x180394872  xor     r9d, r9d; lpArguments
0x180394875  xor     r8d, r8d; nNumberOfArguments
0x180394878  lea     edx, [r9+1]; dwExceptionFlags
0x18039487c  mov     ecx, eax; dwExceptionCode
0x18039487e  call    cs:__imp_RaiseException
0x180394884  int     3; Trap to Debugger
0x180394885  mov     ecx, ebx; failedFrameHR
0x180394887  call    OnFailure_2990_
0x18039488c  mov     [rsp+130h+ppStowedExceptions], r15
0x180394891  mov     [rsp+130h+cStowedExceptions], r15d
0x180394896  mov     ecx, ebx; errorCode
0x180394898  call    TraceForFailFast
0x18039489d  lea     backingCO, [rsp+130h+cStowedExceptions]; pcStowedExceptions
0x1803948a2  lea     this, [rsp+130h+ppStowedExceptions]; pppStowedExceptions
0x1803948a7  call    GetStowedExceptionsForFailFast
0x1803948ac  mov     r8, [rsp+130h+ppStowedExceptions]
0x1803948b1  mov     edx, [rsp+130h+cStowedExceptions]
0x1803948b5  mov     ecx, ebx
0x1803948b7  call    cs:__imp_?RoFailFastWithErrorContextInternal2@@YAXJKQEAPEAU_STOWED_EXCEPTION_INFORMATION_V2@@@Z; RoFailFastWithErrorContextInternal2(long,ulong,_STOWED_EXCEPTION_INFORMATION_V2 * * const)
0x1803948bd  jmp     loc_18039481F
0x1803948c2  xor     r8d, r8d; detailedAnimationReason
0x1803948c5  lea     edx, [r8+17h]; compositionReason
0x1803948c9  mov     this, rsi; this
0x1803948cc  call    ?UnsetRequiresComposition@CUIElement@@UEAAXW4Value@CompositionRequirement@@W42IndependentAnimationType@@@Z; CUIElement::UnsetRequiresComposition(CompositionRequirement::Value,IndependentAnimationType::Value)
0x1803948d1  jmp     loc_18039484B
0x1803948d6  xor     edx, edx; Val
0x1803948d8  lea     r8d, [backingCO+40h]; Size
0x1803948dc  lea     this, [rbp+30h+transformMatrix]; void *
0x1803948e0  call    memset_0
0x1803948e5  mov     rdi, [rsp+130h+backingPS.ptr_]
0x1803948ea  mov     rax, [rdi]
0x1803948ed  mov     rbx, [rax+80h]
0x1803948f4  mov     [rsp+130h+string], r15
0x1803948f9  mov     r9d, 0Fh; len
0x1803948ff  lea     r8d, [r9+1]; bufferLen
0x180394903  lea     backingCO, FacadeProperty_TransformMatrix; str
0x18039490a  lea     this, [rsp+130h+hstringHeader]; this
0x18039490f  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180394914  nop
0x180394915  lea     r9, [rsp+130h+status]
0x18039491a  lea     r8, [rbp+30h+transformMatrix]
0x18039491e  mov     backingCO, [rsp+130h+string]
0x180394923  mov     this, rdi
0x180394926  mov     rax, rbx
0x180394929  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18039492e  mov     ebx, eax
0x180394930  test    eax, eax
0x180394932  jns     short loc_18039496C
0x180394934  mov     ecx, eax; failedFrameHR
0x180394936  call    OnFailure_2990_
0x18039493b  mov     [rsp+130h+ppStowedExceptions], r15
0x180394940  mov     [rsp+130h+cStowedExceptions], r15d
0x180394945  mov     ecx, ebx; errorCode
0x180394947  call    TraceForFailFast
0x18039494c  lea     backingCO, [rsp+130h+cStowedExceptions]; pcStowedExceptions
0x180394951  lea     this, [rsp+130h+ppStowedExceptions]; pppStowedExceptions
0x180394956  call    GetStowedExceptionsForFailFast
0x18039495b  mov     r8, [rsp+130h+ppStowedExceptions]
0x180394960  mov     edx, [rsp+130h+cStowedExceptions]
0x180394964  mov     ecx, ebx
0x180394966  call    cs:__imp_?RoFailFastWithErrorContextInternal2@@YAXJKQEAPEAU_STOWED_EXCEPTION_INFORMATION_V2@@@Z; RoFailFastWithErrorContextInternal2(long,ulong,_STOWED_EXCEPTION_INFORMATION_V2 * * const)
0x18039496c  lea     backingCO, [rbp+30h+transformMatrix]; value
0x180394970  mov     this, rsi; obj
0x180394973  call    SimpleProperty__details__SetImpl_2081_
0x180394978  lea     backingCO, [rbp+30h+transformMatrix]; transformMatrix
0x18039497c  mov     this, rsi; this
0x18039497f  call    ?UpdateHasNonIdentityTransformMatrix@CUIElement@@QEAAXAEBUMatrix4x4@Numerics@Foundation@Windows@@@Z; CUIElement::UpdateHasNonIdentityTransformMatrix(Windows::Foundation::Numerics::Matrix4x4 const &)
0x180394984  mov     edx, 1; flags
0x180394989  mov     this, rsi; pTarget
0x18039498c  call    ?NWSetTransformDirty@CUIElement@@SAXPEAVCDependencyObject@@W4Value@DirtyFlags@@@Z; CUIElement::NWSetTransformDirty(CDependencyObject *,DirtyFlags::Value)
0x180394991  lea     backingCO, [rbp+30h+transformMatrix]; transformMatrix
0x180394995  mov     this, rsi; this
0x180394998  call    ?OnTransformMatrixForHitTestingChanged@CUIElement@@QEAAXAEBUMatrix4x4@Numerics@Foundation@Windows@@@Z; CUIElement::OnTransformMatrixForHitTestingChanged(Windows::Foundation::Numerics::Matrix4x4 const &)
0x18039499d  jmp     loc_180394726
0x1803949a2  xor     eax, eax
0x1803949a4  mov     qword ptr [rbp+30h+scale.X], rax
0x1803949a8  mov     [rbp+30h+scale.Z], eax
0x1803949ab  mov     rdi, [rsp+130h+backingPS.ptr_]
0x1803949b0  mov     rax, [rdi]
0x1803949b3  mov     rbx, [rax+0A0h]
0x1803949ba  mov     [rsp+130h+string], r15
0x1803949bf  mov     r9d, 5; len
0x1803949c5  lea     r8d, [r9+1]; bufferLen
0x1803949c9  lea     backingCO, FacadeProperty_Scale; str
0x1803949d0  lea     this, [rsp+130h+hstringHeader]; this
0x1803949d5  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1803949da  nop
0x1803949db  lea     r9, [rsp+130h+status]
0x1803949e0  lea     r8, [rbp+30h+scale]
0x1803949e4  mov     backingCO, [rsp+130h+string]
0x1803949e9  mov     this, rdi
0x1803949ec  mov     rax, rbx
0x1803949ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803949f4  mov     ebx, eax
0x1803949f6  test    eax, eax
0x1803949f8  jns     short loc_180394A32
0x1803949fa  mov     ecx, eax; failedFrameHR
0x1803949fc  call    OnFailure_2990_
0x180394a01  mov     [rsp+130h+ppStowedExceptions], r15
0x180394a06  mov     [rsp+130h+cStowedExceptions], r15d
0x180394a0b  mov     ecx, ebx; errorCode
0x180394a0d  call    TraceForFailFast
0x180394a12  lea     backingCO, [rsp+130h+cStowedExceptions]; pcStowedExceptions
0x180394a17  lea     this, [rsp+130h+ppStowedExceptions]; pppStowedExceptions
0x180394a1c  call    GetStowedExceptionsForFailFast
0x180394a21  mov     r8, [rsp+130h+ppStowedExceptions]
0x180394a26  mov     edx, [rsp+130h+cStowedExceptions]
0x180394a2a  mov     ecx, ebx
0x180394a2c  call    cs:__imp_?RoFailFastWithErrorContextInternal2@@YAXJKQEAPEAU_STOWED_EXCEPTION_INFORMATION_V2@@@Z; RoFailFastWithErrorContextInternal2(long,ulong,_STOWED_EXCEPTION_INFORMATION_V2 * * const)
0x180394a32  lea     backingCO, [rbp+30h+scale]; value
0x180394a36  mov     this, rsi; obj
0x180394a39  call    SimpleProperty__details__SetImpl_2079_
0x180394a3e  lea     backingCO, [rbp+30h+scale]; scale
0x180394a42  mov     this, rsi; this
0x180394a45  call    ?UpdateHasScaleZ@CUIElement@@QEAAXAEBUVector3@Numerics@Foundation@Windows@@@Z; CUIElement::UpdateHasScaleZ(Windows::Foundation::Numerics::Vector3 const &)
0x180394a4a  jmp     loc_18039484B
0x180394a4f  xor     eax, eax
0x180394a51  mov     qword ptr [rbp+30h+rotationAxis.X], rax
0x180394a55  mov     [rbp+30h+rotationAxis.Z], eax
0x180394a58  mov     rdi, [rsp+130h+backingPS.ptr_]
0x180394a5d  mov     rax, [rdi]
0x180394a60  mov     rbx, [rax+0A0h]
0x180394a67  mov     [rsp+130h+string], r15
0x180394a6c  mov     r9d, 0Ch; len
0x180394a72  lea     r8d, [r9+1]; bufferLen
0x180394a76  lea     backingCO, FacadeProperty_RotationAxis; str
0x180394a7d  lea     this, [rsp+130h+hstringHeader]; this
0x180394a82  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180394a87  nop
0x180394a88  lea     r9, [rsp+130h+status]
0x180394a8d  lea     r8, [rbp+30h+rotationAxis]
0x180394a91  mov     backingCO, [rsp+130h+string]
0x180394a96  mov     this, rdi
0x180394a99  mov     rax, rbx
0x180394a9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180394aa1  mov     ebx, eax
0x180394aa3  test    eax, eax
0x180394aa5  jns     short loc_180394ADF
0x180394aa7  mov     ecx, eax; failedFrameHR
0x180394aa9  call    OnFailure_2990_
0x180394aae  mov     [rsp+130h+ppStowedExceptions], r15
0x180394ab3  mov     [rsp+130h+cStowedExceptions], r15d
0x180394ab8  mov     ecx, ebx; errorCode
0x180394aba  call    TraceForFailFast
0x180394abf  lea     backingCO, [rsp+130h+cStowedExceptions]; pcStowedExceptions
0x180394ac4  lea     this, [rsp+130h+ppStowedExceptions]; pppStowedExceptions
0x180394ac9  call    GetStowedExceptionsForFailFast
0x180394ace  mov     r8, [rsp+130h+ppStowedExceptions]
0x180394ad3  mov     edx, [rsp+130h+cStowedExceptions]
0x180394ad7  mov     ecx, ebx
0x180394ad9  call    cs:__imp_?RoFailFastWithErrorContextInternal2@@YAXJKQEAPEAU_STOWED_EXCEPTION_INFORMATION_V2@@@Z; RoFailFastWithErrorContextInternal2(long,ulong,_STOWED_EXCEPTION_INFORMATION_V2 * * const)
0x180394adf  lea     backingCO, [rbp+30h+rotationAxis]; value
  ... truncated ...
```
