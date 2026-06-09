# CUIElement::PopulateBackingCompositionObjectWithFacade(Windows::UI::Composition::ICompositionObject *,KnownPropertyIndex)

- ea: `0x180393d34`
- end: `0x18039435b`
- name: `?PopulateBackingCompositionObjectWithFacade@CUIElement@@QEAAXPEAUICompositionObject@Composition@UI@Windows@@W4KnownPropertyIndex@@@Z`
- size: `1575`
- prototype: `void __fastcall(CUIElement *this, Windows::UI::Composition::ICompositionObject *backingCO, KnownPropertyIndex facadeID)`
- caller_count: `1`
- callee_count: `17`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180649cb0`

## callees

- `0x180004bc0`
- `0x180008428`
- `0x180103860`
- `0x180104f10`
- `0x180105d8c`
- `0x180393d34`
- `0x18044bcbc`
- `0x1804c1824`
- `0x1804c1c9c`
- `0x1804d9700`
- `0x1804da4a8`
- `0x1804dea40`
- `0x1805ce86c`
- `0x1806877a8`
- `0x180687890`
- `0x18076e110`
- `0x180c0e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180394158`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18039416b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18039426a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18039427d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180394290`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1803942af`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180394158`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18039416b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18039426a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18039427d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180394290`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1803942af`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x18039434f`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x18039434f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180393e35`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180393e9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180393f64`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180393fcd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180394042`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1803940c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180393e35`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180393e9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180393f64`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180393fcd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180394042`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1803940c9`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CUIElement::PopulateBackingCompositionObjectWithFacade(
        CUIElement *this,
        Windows::UI::Composition::ICompositionObject *backingCO,
        unsigned __int16 facadeID)
{
  __m128 v3; // xmm0
  int v4; // esi
  HRESULT (__fastcall *QueryInterface)(IUnknown *, const _GUID *, void **); // rbx
  Windows::System::Internal::IUserManagerStatics *v8; // rbx
  Windows::System::Internal::IUserManagerStatics_vtbl *v9; // rdi
  Windows::Foundation::Numerics::Vector3 *Translation; // rax
  _STOWED_EXCEPTION_INFORMATION_V2 **v11; // xmm6_8
  float v12; // esi
  signed int v13; // eax
  HRESULT v14; // eax
  HRESULT v15; // ebx
  Windows::System::Internal::IUserManagerStatics *v16; // rbx
  Windows::System::Internal::IUserManagerStatics_vtbl *v17; // rdi
  signed int v18; // eax
  HRESULT v19; // eax
  Windows::System::Internal::IUserManagerStatics *v20; // rcx
  Windows::System::Internal::IUserManagerStatics *ptr; // rbx
  Windows::System::Internal::IUserManagerStatics_vtbl *v22; // rdi
  __m128 v23; // xmm6
  signed int StringReference; // eax
  Windows::System::Internal::IUserManagerStatics *v25; // rbx
  Windows::System::Internal::IUserManagerStatics_vtbl *v26; // rdi
  signed int v27; // eax
  Windows::System::Internal::IUserManagerStatics *v28; // rbx
  Windows::System::Internal::IUserManagerStatics_vtbl *v29; // rdi
  const Windows::Foundation::Numerics::Vector3 *ImplSparse_48; // rax
  _STOWED_EXCEPTION_INFORMATION_V2 **v31; // xmm6_8
  float v32; // esi
  signed int v33; // eax
  Windows::System::Internal::IUserManagerStatics *v34; // rbx
  Windows::System::Internal::IUserManagerStatics_vtbl *v35; // rdi
  const Windows::Foundation::Numerics::Matrix4x4 *ImplSparse_39; // rax
  __int128 v37; // xmm6
  __int128 v38; // xmm7
  __int128 v39; // xmm8
  __int128 v40; // xmm9
  signed int v41; // eax
  Windows::System::Internal::IUserManagerStatics *v42; // rsi
  HRESULT (__fastcall *v43)(Windows::System::Internal::IUserManagerStatics *, unsigned int, Windows::System::Internal::IUserProfile **); // rdi
  Windows::Foundation::Numerics::Vector3 *Scale; // rax
  _STOWED_EXCEPTION_INFORMATION_V2 **v45; // xmm6_8
  float v46; // ebx
  Windows::System::Internal::IUserManagerStatics *v47; // rsi
  HRESULT (__fastcall *v48)(Windows::System::Internal::IUserManagerStatics *, unsigned int, Windows::System::Internal::IUserProfile **); // rdi
  Windows::Foundation::Numerics::Vector3 *RotationAxis; // rax
  _STOWED_EXCEPTION_INFORMATION_V2 **v50; // xmm6_8
  float v51; // ebx
  Windows::System::Internal::IUserManagerStatics *v52; // rsi
  HRESULT (__fastcall *GetUser)(Windows::System::Internal::IUserManagerStatics *, unsigned int, Windows::System::Internal::IUserProfile **); // rdi
  Windows::Foundation::Numerics::Vector3 *ActualOffset; // rax
  _STOWED_EXCEPTION_INFORMATION_V2 **v55; // xmm6_8
  float Z; // ebx
  unsigned int pcStowedExceptions; // [rsp+28h] [rbp-E0h] BYREF
  _STOWED_EXCEPTION_INFORMATION_V2 **pppStowedExceptions; // [rsp+38h] [rbp-D0h] BYREF
  Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionPropertySet> backingPS; // [rsp+40h] [rbp-C8h]
  Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics> v60; // [rsp+48h] [rbp-C0h] BYREF
  Windows::Foundation::Numerics::Vector3 result; // [rsp+50h] [rbp-B8h] BYREF
  _OWORD v62[4]; // [rsp+68h] [rbp-A0h] BYREF
  Microsoft::WRL::Wrappers::HStringReference hstringHeader; // [rsp+A8h] [rbp-60h] BYREF

  v4 = facadeID;
  v60.ptr_ = 0;
  QueryInterface = backingCO->QueryInterface;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v60);
  QueryInterface(backingCO, &GUID_c9d6d202_5f67_4453_9117_9eadd430d3c2, (void **)&v60.ptr_);
  switch ( v4 )
  {
    case 417:
      goto LABEL_47;
    case 418:
      ptr = v60.ptr_;
      v22 = v60.ptr_->__vftable;
      *(double *)v3.m128_u64 = ((double (__fastcall *)(CUIElement *))this->GetActualWidth)(this);
      v23 = v3;
      *(double *)v3.m128_u64 = ((double (__fastcall *)(CUIElement *))this->GetActualHeight)(this);
      hstringHeader.hstr_ = 0;
      StringReference = WindowsCreateStringReference(
                          FacadeProperty_ActualSize,
                          0xAu,
                          &hstringHeader.header_,
                          &hstringHeader.hstr_);
      if ( StringReference >= 0 )
      {
        v19 = ((__int64 (__fastcall *)(Windows::System::Internal::IUserManagerStatics *, HSTRING__ *, unsigned __int64))v22->get_Profiles)(
                ptr,
                hstringHeader.hstr_,
                _mm_unpacklo_ps(v23, v3).m128_u64[0]);
        v15 = v19;
        if ( v19 >= 0 )
          break;
        goto LABEL_33;
      }
      RaiseException(StringReference, 1u, 0, 0);
LABEL_47:
      v52 = v60.ptr_;
      GetUser = v60.ptr_->GetUser;
      ActualOffset = CUIElement::GetActualOffset(this, &result);
      v55 = *(_STOWED_EXCEPTION_INFORMATION_V2 ***)&ActualOffset->X;
      Z = ActualOffset->Z;
      hstringHeader.hstr_ = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        FacadeProperty_ActualOffset,
        0xDu,
        0xCu);
      pppStowedExceptions = v55;
      *(float *)&backingPS.ptr_ = Z;
      v14 = GetUser(
              v52,
              (unsigned int)hstringHeader.hstr_,
              (Windows::System::Internal::IUserProfile **)&pppStowedExceptions);
      v15 = v14;
      if ( v14 >= 0 )
        break;
      goto LABEL_48;
    case 453:
      v16 = v60.ptr_;
      v17 = v60.ptr_->__vftable;
      hstringHeader.hstr_ = 0;
      v18 = WindowsCreateStringReference(FacadeProperty_Opacity, 7u, &hstringHeader.header_, &hstringHeader.hstr_);
      if ( v18 < 0 )
      {
        RaiseException(v18, 1u, 0, 0);
        __debugbreak();
      }
      v19 = ((__int64 (__fastcall *)(Windows::System::Internal::IUserManagerStatics *, HSTRING__ *))v17->Update)(
              v16,
              hstringHeader.hstr_);
      v15 = v19;
      if ( v19 < 0 )
        goto LABEL_33;
      break;
    case 2074:
      v28 = v60.ptr_;
      v29 = v60.ptr_->__vftable;
      if ( SimpleProperty::Property::id<2074>::IsSet(this) )
        ImplSparse_48 = SimpleProperty::details::GetImplSparse_48_(
                          &this->m_sharedState.m_ptr->m_value.m_coreServices->m_sparseTables.m_UIElement_CenterPoint,
                          this);
      else
        ImplSparse_48 = &value;
      v31 = *(_STOWED_EXCEPTION_INFORMATION_V2 ***)&ImplSparse_48->X;
      v32 = ImplSparse_48->Z;
      hstringHeader.hstr_ = 0;
      v33 = WindowsCreateStringReference(FacadeProperty_CenterPoint, 0xBu, &hstringHeader.header_, &hstringHeader.hstr_);
      if ( v33 < 0 )
      {
        RaiseException(v33, 1u, 0, 0);
        __debugbreak();
      }
      pppStowedExceptions = v31;
      *(float *)&backingPS.ptr_ = v32;
      v14 = v29->GetUser(
              v28,
              (unsigned int)hstringHeader.hstr_,
              (Windows::System::Internal::IUserProfile **)&pppStowedExceptions);
      v15 = v14;
      if ( v14 < 0 )
      {
LABEL_48:
        OnFailure_2990_(v14);
        goto LABEL_49;
      }
      break;
    case 2077:
      v25 = v60.ptr_;
      v26 = v60.ptr_->__vftable;
      CUIElement::GetRotation(this, 0);
      hstringHeader.hstr_ = 0;
      v27 = WindowsCreateStringReference(FacadeProperty_Rotation, 8u, &hstringHeader.header_, &hstringHeader.hstr_);
      if ( v27 < 0 )
      {
        RaiseException(v27, 1u, 0, 0);
        __debugbreak();
      }
      v19 = ((__int64 (__fastcall *)(Windows::System::Internal::IUserManagerStatics *, HSTRING__ *))v26->Update)(
              v25,
              hstringHeader.hstr_);
      v15 = v19;
      if ( v19 < 0 )
        goto LABEL_33;
      break;
    case 2078:
      v47 = v60.ptr_;
      v48 = v60.ptr_->GetUser;
      RotationAxis = CUIElement::GetRotationAxis(this, &result, 0);
      v50 = *(_STOWED_EXCEPTION_INFORMATION_V2 ***)&RotationAxis->X;
      v51 = RotationAxis->Z;
      hstringHeader.hstr_ = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        FacadeProperty_RotationAxis,
        0xDu,
        0xCu);
      pppStowedExceptions = v50;
      *(float *)&backingPS.ptr_ = v51;
      v14 = v48(
              v47,
              (unsigned int)hstringHeader.hstr_,
              (Windows::System::Internal::IUserProfile **)&pppStowedExceptions);
      v15 = v14;
      if ( v14 >= 0 )
        break;
      goto LABEL_48;
    case 2079:
      goto LABEL_38;
    case 2081:
      v34 = v60.ptr_;
      v35 = v60.ptr_->__vftable;
      if ( SimpleProperty::Property::id<2081>::IsSet(this) )
        ImplSparse_39 = SimpleProperty::details::GetImplSparse_39_(
                          &this->m_sharedState.m_ptr->m_value.m_coreServices->m_sparseTables.m_UIElement_TransformMatrix,
                          this);
      else
        ImplSparse_39 = &`SimpleProperty::Type::Default<39>'::`2'::s_default;
      v37 = *(_OWORD *)&ImplSparse_39->M11;
      v38 = *(_OWORD *)&ImplSparse_39->M21;
      v39 = *(_OWORD *)&ImplSparse_39->M31;
      v40 = *(_OWORD *)&ImplSparse_39->M41;
      hstringHeader.hstr_ = 0;
      v41 = WindowsCreateStringReference(
              FacadeProperty_TransformMatrix,
              0xFu,
              &hstringHeader.header_,
              &hstringHeader.hstr_);
      if ( v41 < 0 )
      {
LABEL_37:
        RaiseException(v41, 1u, 0, 0);
LABEL_38:
        v42 = v60.ptr_;
        v43 = v60.ptr_->GetUser;
        Scale = CUIElement::GetScale(this, &result, 0);
        v45 = *(_STOWED_EXCEPTION_INFORMATION_V2 ***)&Scale->X;
        v46 = Scale->Z;
        hstringHeader.hstr_ = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, FacadeProperty_Scale, 6u, 5u);
        pppStowedExceptions = v45;
        *(float *)&backingPS.ptr_ = v46;
        v14 = v43(
                v42,
                (unsigned int)hstringHeader.hstr_,
                (Windows::System::Internal::IUserProfile **)&pppStowedExceptions);
        v15 = v14;
        if ( v14 >= 0 )
          break;
        goto LABEL_48;
      }
      v62[0] = v37;
      v62[1] = v38;
      v62[2] = v39;
      v62[3] = v40;
      v19 = ((__int64 (__fastcall *)(Windows::System::Internal::IUserManagerStatics *, HSTRING__ *, _OWORD *))v35->CreateSponsoredProfile)(
              v34,
              hstringHeader.hstr_,
              v62);
      v15 = v19;
      if ( v19 >= 0 )
        break;
LABEL_33:
      OnFailure_2990_(v19);
LABEL_49:
      pppStowedExceptions = 0;
      pcStowedExceptions = 0;
      TraceForFailFast(v15);
      GetStowedExceptionsForFailFast(&pppStowedExceptions, &pcStowedExceptions);
      RoFailFastWithErrorContextInternal2(v15, pcStowedExceptions, pppStowedExceptions);
      break;
    case 2082:
      v8 = v60.ptr_;
      v9 = v60.ptr_->__vftable;
      Translation = CUIElement::GetTranslation(this, &result, 0);
      v11 = *(_STOWED_EXCEPTION_INFORMATION_V2 ***)&Translation->X;
      v12 = Translation->Z;
      hstringHeader.hstr_ = 0;
      v13 = WindowsCreateStringReference(
              FacadeProperty_Translation_0,
              0xBu,
              &hstringHeader.header_,
              &hstringHeader.hstr_);
      if ( v13 >= 0 )
      {
        pppStowedExceptions = v11;
        *(float *)&backingPS.ptr_ = v12;
        v14 = v9->GetUser(
                v8,
                (unsigned int)hstringHeader.hstr_,
                (Windows::System::Internal::IUserProfile **)&pppStowedExceptions);
        v15 = v14;
        if ( v14 >= 0 )
          break;
        goto LABEL_48;
      }
      RaiseException(v13, 1u, 0, 0);
      goto LABEL_37;
    default:
      break;
  }
  v20 = v60.ptr_;
  if ( v60.ptr_ )
  {
    v60.ptr_ = 0;
    v20->Release(v20);
  }
}

```

## disassembly

```asm
0x180393d34  mov     rax, rsp
0x180393d37  mov     [rax+18h], rbx
0x180393d3b  push    rbp
0x180393d3c  push    rsi
0x180393d3d  push    rdi
0x180393d3e  push    r14
0x180393d40  push    r15
0x180393d42  lea     rbp, [rax-38h]
0x180393d46  sub     rsp, 110h
0x180393d4d  movaps  xmmword ptr [rax-38h], xmm6
0x180393d51  movaps  xmmword ptr [rax-48h], xmm7
0x180393d55  movaps  xmmword ptr [rax-58h], xmm8
0x180393d5a  movaps  xmmword ptr [rax-68h], xmm9
0x180393d5f  mov     rax, cs:__security_cookie
0x180393d66  xor     rax, rsp
0x180393d69  mov     [rbp+30h+var_70], rax
0x180393d6d  movzx   esi, facadeID
0x180393d71  mov     rdi, backingCO
0x180393d74  mov     r14, this
0x180393d77  xor     r15d, r15d
0x180393d7a  mov     [rsp+130h+var_F0.ptr_], r15
0x180393d7f  mov     rax, [backingCO]
0x180393d82  mov     rbx, [rax]
0x180393d85  lea     this, [rsp+130h+var_F0]; this
0x180393d8a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180393d8f  lea     r8, [rsp+130h+var_F0]
0x180393d94  lea     backingCO, _GUID_c9d6d202_5f67_4453_9117_9eadd430d3c2
0x180393d9b  mov     this, rdi
0x180393d9e  mov     rax, rbx
0x180393da1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180393da6  mov     edx, esi
0x180393da8  sub     edx, 1A1h
0x180393dae  jz      loc_1803942B6
0x180393db4  sub     edx, 1
0x180393db7  jz      loc_180393F1A
0x180393dbd  sub     edx, 23h ; '#'
0x180393dc0  jz      loc_180393E74
0x180393dc6  sub     edx, 655h
0x180393dcc  jz      loc_180394004
0x180393dd2  sub     edx, 3
0x180393dd5  jz      loc_180393FA0
0x180393ddb  sub     edx, 1
0x180393dde  jz      loc_1803941E8
0x180393de4  sub     edx, 1
0x180393de7  jz      loc_180394172
0x180393ded  sub     edx, 2
0x180393df0  jz      loc_180394085
0x180393df6  cmp     edx, 1
0x180393df9  jnz     loc_180393EC8
0x180393dff  mov     rbx, [rsp+130h+var_F0.ptr_]
0x180393e04  mov     rdi, [rbx]
0x180393e07  xor     r8d, r8d; preferAnimatingValue
0x180393e0a  lea     backingCO, [rsp+130h+result]; result
0x180393e0f  mov     this, r14; this
0x180393e12  call    ?GetTranslation@CUIElement@@QEBA?AUVector3@Numerics@Foundation@Windows@@_N@Z; CUIElement::GetTranslation(bool)
0x180393e17  movsd   xmm6, qword ptr [rax]
0x180393e1b  mov     esi, [rax+8]
0x180393e1e  mov     [rbp+30h+string], r15
0x180393e22  lea     r9, [rbp+30h+string]; string
0x180393e26  lea     r8, [rbp+30h+hstringHeader]; hstringHeader
0x180393e2a  lea     edx, [r15+0Bh]; length
0x180393e2e  lea     this, FacadeProperty_Translation_0; sourceString
0x180393e35  call    cs:__imp_WindowsCreateStringReference
0x180393e3b  test    eax, eax
0x180393e3d  js      loc_18039414C
0x180393e43  movsd   [rsp+130h+pppStowedExceptions], xmm6
0x180393e49  mov     dword ptr [rsp+130h+backingPS.ptr_], esi
0x180393e4d  lea     r8, [rsp+130h+pppStowedExceptions]
0x180393e52  mov     backingCO, [rbp+30h+string]
0x180393e56  mov     this, rbx
0x180393e59  mov     rax, [rdi+60h]
0x180393e5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180393e62  mov     ebx, eax
0x180393e64  test    eax, eax
0x180393e66  jns     short loc_180393EC8
0x180393e68  mov     ecx, eax; failedFrameHR
0x180393e6a  call    OnFailure_2990_
0x180393e6f  jmp     loc_180394324
0x180393e74  mov     rbx, [rsp+130h+var_F0.ptr_]
0x180393e79  mov     rdi, [rbx]
0x180393e7c  movss   xmm6, dword ptr [r14+9Ch]
0x180393e85  mov     [rbp+30h+string], r15
0x180393e89  lea     r9, [rbp+30h+string]; string
0x180393e8d  lea     r8, [rbp+30h+hstringHeader]; hstringHeader
0x180393e91  mov     edx, 7; length
0x180393e96  lea     this, FacadeProperty_Opacity; sourceString
0x180393e9d  call    cs:__imp_WindowsCreateStringReference
0x180393ea3  test    eax, eax
0x180393ea5  js      loc_180394284
0x180393eab  movaps  xmm2, xmm6
0x180393eae  mov     backingCO, [rbp+30h+string]
0x180393eb2  mov     this, rbx
0x180393eb5  mov     rax, [rdi+50h]
0x180393eb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180393ebe  mov     ebx, eax
0x180393ec0  test    eax, eax
0x180393ec2  js      loc_180394297
0x180393ec8  mov     this, [rsp+130h+var_F0.ptr_]
0x180393ecd  test    this, this
0x180393ed0  jz      short loc_180393EE3
0x180393ed2  mov     [rsp+130h+var_F0.ptr_], r15
0x180393ed7  mov     rax, [this]
0x180393eda  mov     rax, [rax+10h]
0x180393ede  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180393ee3  mov     this, [rbp+30h+var_70]
0x180393ee7  xor     this, rsp; StackCookie
0x180393eea  call    __security_check_cookie
0x180393eef  lea     r11, [rsp+130h+var_20]
0x180393ef7  mov     rbx, [r11+40h]
0x180393efb  movaps  xmm6, xmmword ptr [r11-10h]
0x180393f00  movaps  xmm7, xmmword ptr [r11-20h]
0x180393f05  movaps  xmm8, xmmword ptr [r11-30h]
0x180393f0a  movaps  xmm9, xmmword ptr [r11-40h]
0x180393f0f  mov     rsp, r11
0x180393f12  pop     r15
0x180393f14  pop     r14
0x180393f16  pop     rdi
0x180393f17  pop     rsi
0x180393f18  pop     rbp
0x180393f19  retn
0x180393f1a  mov     rbx, [rsp+130h+var_F0.ptr_]
0x180393f1f  mov     rdi, [rbx]
0x180393f22  mov     rax, [r14]
0x180393f25  mov     this, r14
0x180393f28  mov     rax, [rax+2E8h]
0x180393f2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180393f34  movaps  xmm6, xmm0
0x180393f37  mov     rax, [r14]
0x180393f3a  mov     this, r14
0x180393f3d  mov     rax, [rax+2F0h]
0x180393f44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180393f49  movaps  xmm7, xmm0
0x180393f4c  mov     [rbp+30h+string], r15
0x180393f50  lea     r9, [rbp+30h+string]; string
0x180393f54  lea     r8, [rbp+30h+hstringHeader]; hstringHeader
0x180393f58  mov     edx, 0Ah; length
0x180393f5d  lea     this, FacadeProperty_ActualSize; sourceString
0x180393f64  call    cs:__imp_WindowsCreateStringReference
0x180393f6a  test    eax, eax
0x180393f6c  js      loc_1803942A3
0x180393f72  unpcklps xmm6, xmm7
0x180393f75  movq    r8, xmm6
0x180393f7a  mov     backingCO, [rbp+30h+string]
0x180393f7e  mov     this, rbx
0x180393f81  mov     rax, [rdi+58h]
0x180393f85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180393f8a  mov     ebx, eax
0x180393f8c  test    eax, eax
0x180393f8e  jns     loc_180393EC8
0x180393f94  mov     ecx, eax; failedFrameHR
0x180393f96  call    OnFailure_2990_
0x180393f9b  jmp     loc_180394324
0x180393fa0  mov     rbx, [rsp+130h+var_F0.ptr_]
0x180393fa5  mov     rdi, [rbx]
0x180393fa8  xor     edx, edx; preferAnimatingValue
0x180393faa  mov     this, r14; this
0x180393fad  call    ?GetRotation@CUIElement@@QEBAM_N@Z; CUIElement::GetRotation(bool)
0x180393fb2  movaps  xmm6, xmm0
0x180393fb5  mov     [rbp+30h+string], r15
0x180393fb9  lea     r9, [rbp+30h+string]; string
0x180393fbd  lea     r8, [rbp+30h+hstringHeader]; hstringHeader
0x180393fc1  mov     edx, 8; length
0x180393fc6  lea     this, FacadeProperty_Rotation; sourceString
0x180393fcd  call    cs:__imp_WindowsCreateStringReference
0x180393fd3  test    eax, eax
0x180393fd5  js      loc_18039425E
0x180393fdb  movaps  xmm2, xmm6
0x180393fde  mov     backingCO, [rbp+30h+string]
0x180393fe2  mov     this, rbx
0x180393fe5  mov     rax, [rdi+50h]
0x180393fe9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180393fee  mov     ebx, eax
0x180393ff0  test    eax, eax
0x180393ff2  jns     loc_180393EC8
0x180393ff8  mov     ecx, eax; failedFrameHR
0x180393ffa  call    OnFailure_2990_
0x180393fff  jmp     loc_180394324
0x180394004  mov     rbx, [rsp+130h+var_F0.ptr_]
0x180394009  mov     rdi, [rbx]
0x18039400c  mov     this, r14; obj
0x18039400f  call    ?IsSet@?$id@$0IBK@@Property@SimpleProperty@@SA_NPEBX@Z; SimpleProperty::Property::id<2074>::IsSet(void const *)
0x180394014  test    al, al
0x180394016  jnz     loc_180394131
0x18039401c  lea     rax, value
0x180394023  movsd   xmm6, qword ptr [rax]
0x180394027  mov     esi, [rax+8]
0x18039402a  mov     [rbp+30h+string], r15
0x18039402e  lea     r9, [rbp+30h+string]; string
0x180394032  lea     r8, [rbp+30h+hstringHeader]; hstringHeader
0x180394036  mov     edx, 0Bh; length
0x18039403b  lea     this, FacadeProperty_CenterPoint; sourceString
0x180394042  call    cs:__imp_WindowsCreateStringReference
0x180394048  test    eax, eax
0x18039404a  js      loc_180394271
0x180394050  movsd   [rsp+130h+pppStowedExceptions], xmm6
0x180394056  mov     dword ptr [rsp+130h+backingPS.ptr_], esi
0x18039405a  lea     r8, [rsp+130h+pppStowedExceptions]
0x18039405f  mov     backingCO, [rbp+30h+string]
0x180394063  mov     this, rbx
0x180394066  mov     rax, [rdi+60h]
0x18039406a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18039406f  mov     ebx, eax
0x180394071  test    eax, eax
0x180394073  jns     loc_180393EC8
0x180394079  mov     ecx, eax; failedFrameHR
0x18039407b  call    OnFailure_2990_
0x180394080  jmp     loc_180394324
0x180394085  mov     rbx, [rsp+130h+var_F0.ptr_]
0x18039408a  mov     rdi, [rbx]
0x18039408d  mov     this, r14; obj
0x180394090  call    ?IsSet@?$id@$0ICB@@Property@SimpleProperty@@SA_NPEBX@Z; SimpleProperty::Property::id<2081>::IsSet(void const *)
0x180394095  test    al, al
0x180394097  jnz     short loc_180394116
0x180394099  lea     rax, ?s_default@?1???$Default@$0CH@@Type@SimpleProperty@@SAAEBUMatrix4x4@Numerics@Foundation@Windows@@XZ@4U3456@B; Windows::Foundation::Numerics::Matrix4x4 const `SimpleProperty::Type::Default<39>(void)'::`2'::s_default
0x1803940a0  movups  xmm6, xmmword ptr [rax]
0x1803940a3  movups  xmm7, xmmword ptr [rax+10h]
0x1803940a7  movups  xmm8, xmmword ptr [rax+20h]
0x1803940ac  movups  xmm9, xmmword ptr [rax+30h]
0x1803940b1  mov     [rbp+30h+string], r15
0x1803940b5  lea     r9, [rbp+30h+string]; string
0x1803940b9  lea     r8, [rbp+30h+hstringHeader]; hstringHeader
0x1803940bd  mov     edx, 0Fh; length
0x1803940c2  lea     this, FacadeProperty_TransformMatrix; sourceString
0x1803940c9  call    cs:__imp_WindowsCreateStringReference
0x1803940cf  test    eax, eax
0x1803940d1  js      loc_18039415F
0x1803940d7  movaps  [rsp+130h+var_D8+8], xmm6
0x1803940dc  movaps  [rsp+130h+var_C8+8], xmm7
0x1803940e1  movaps  [rbp+30h+var_B0], xmm8
0x1803940e6  movaps  [rbp+30h+var_A0], xmm9
0x1803940eb  lea     r8, [rsp+130h+var_D8+8]
0x1803940f0  mov     backingCO, [rbp+30h+string]
0x1803940f4  mov     this, rbx
0x1803940f7  mov     rax, [rdi+40h]
0x1803940fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180394100  mov     ebx, eax
0x180394102  test    eax, eax
0x180394104  jns     loc_180393EC8
0x18039410a  mov     ecx, eax; failedFrameHR
0x18039410c  call    OnFailure_2990_
0x180394111  jmp     loc_180394324
0x180394116  mov     rax, [r14+10h]
0x18039411a  mov     this, [rax]
0x18039411d  add     this, 0B18h; table
0x180394124  mov     backingCO, r14; obj
0x180394127  call    SimpleProperty__details__GetImplSparse_39_
0x18039412c  jmp     loc_1803940A0
0x180394131  mov     rax, [r14+10h]
0x180394135  mov     this, [rax]
0x180394138  add     this, 0A70h; table
0x18039413f  mov     backingCO, r14; obj
0x180394142  call    SimpleProperty__details__GetImplSparse_48_
0x180394147  jmp     loc_180394023
0x18039414c  xor     r9d, r9d; lpArguments
0x18039414f  xor     r8d, r8d; nNumberOfArguments
0x180394152  lea     edx, [r9+1]; dwExceptionFlags
0x180394156  mov     ecx, eax; dwExceptionCode
0x180394158  call    cs:__imp_RaiseException
0x18039415e  nop
0x18039415f  xor     r9d, r9d; lpArguments
0x180394162  xor     r8d, r8d; nNumberOfArguments
0x180394165  lea     edx, [r9+1]; dwExceptionFlags
0x180394169  mov     ecx, eax; dwExceptionCode
0x18039416b  call    cs:__imp_RaiseException
0x180394171  nop
0x180394172  mov     rsi, [rsp+130h+var_F0.ptr_]
0x180394177  mov     rax, [rsi]
0x18039417a  mov     rdi, [rax+60h]
0x18039417e  xor     r8d, r8d; preferAnimatingValue
0x180394181  lea     backingCO, [rsp+130h+result]; result
0x180394186  mov     this, r14; this
0x180394189  call    ?GetScale@CUIElement@@QEBA?AUVector3@Numerics@Foundation@Windows@@_N@Z; CUIElement::GetScale(bool)
0x18039418e  movsd   xmm6, qword ptr [rax]
0x180394192  mov     ebx, [rax+8]
0x180394195  mov     [rbp+30h+string], r15
0x180394199  mov     r9d, 5; len
0x18039419f  lea     r8d, [r9+1]; bufferLen
0x1803941a3  lea     backingCO, FacadeProperty_Scale; str
0x1803941aa  lea     this, [rbp+30h+hstringHeader]; this
0x1803941ae  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1803941b3  nop
0x1803941b4  movsd   [rsp+130h+pppStowedExceptions], xmm6
0x1803941ba  mov     dword ptr [rsp+130h+backingPS.ptr_], ebx
0x1803941be  lea     r8, [rsp+130h+pppStowedExceptions]
0x1803941c3  mov     backingCO, [rbp+30h+string]
0x1803941c7  mov     this, rsi
0x1803941ca  mov     rax, rdi
0x1803941cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803941d2  mov     ebx, eax
0x1803941d4  test    eax, eax
0x1803941d6  jns     loc_180393EC8
0x1803941dc  mov     ecx, eax; failedFrameHR
0x1803941de  call    OnFailure_2990_
0x1803941e3  jmp     loc_180394324
0x1803941e8  mov     rsi, [rsp+130h+var_F0.ptr_]
0x1803941ed  mov     rax, [rsi]
0x1803941f0  mov     rdi, [rax+60h]
0x1803941f4  xor     r8d, r8d; preferAnimatingValue
0x1803941f7  lea     backingCO, [rsp+130h+result]; result
0x1803941fc  mov     this, r14; this
  ... truncated ...
```
