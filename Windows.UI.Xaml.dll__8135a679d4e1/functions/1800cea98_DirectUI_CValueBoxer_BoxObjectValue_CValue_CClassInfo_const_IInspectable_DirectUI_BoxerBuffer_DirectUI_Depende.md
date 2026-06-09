# DirectUI::CValueBoxer::BoxObjectValue(CValue *,CClassInfo const *,IInspectable *,DirectUI::BoxerBuffer *,DirectUI::DependencyObject * *,uchar)

- ea: `0x1800cea98`
- end: `0x1800cffea`
- name: `?BoxObjectValue@CValueBoxer@DirectUI@@SAJPEAVCValue@@PEBVCClassInfo@@PEAUIInspectable@@PEAVBoxerBuffer@2@PEAPEAVDependencyObject@2@E@Z`
- size: `5458`
- prototype: `HRESULT __fastcall(CValue *box, const CClassInfo *pSourceType, IInspectable *value, DirectUI::BoxerBuffer *buffer, DirectUI::DependencyObject **ppMOR, unsigned __int8 bPreserveObjectIdentity)`
- caller_count: `41`
- callee_count: `52`
- tags: `broker_com_uri`

## callers

- `0x1800cdbe4`
- `0x1800d0100`
- `0x1800d0280`
- `0x1800d0540`
- `0x1800f6348`
- `0x1802095cc`
- `0x18022b030`
- `0x18022b260`
- `0x18022b3ac`
- `0x18022b6d0`
- `0x18022b820`
- `0x18022b970`
- `0x18022bac0`
- `0x18022bc10`
- `0x18022c0a0`
- `0x18022c9c4`
- `0x18022cbc0`
- `0x18022e1e0`
- `0x180435828`
- `0x1804af9e0`
- `0x1804afca0`
- `0x1804aff30`
- `0x1804b01d0`
- `0x18052a7a0`
- `0x18054cf10`
- `0x1805e3618`
- `0x1805ee480`
- `0x1805f2380`
- `0x180629cb0`
- `0x180631bd0`
- `0x18068a0b8`
- `0x1806ab044`
- `0x1806abaac`
- `0x1808703cc`
- `0x180871e8c`
- `0x1808cec20`
- `0x1808e9bc0`
- `0x180927390`
- `0x180b9e3e4`
- `0x180b9f5e4`
- `0x180bb4194`

## callees

- `0x180004bc0`
- `0x1800053b0`
- `0x18000616c`
- `0x180021840`
- `0x180021970`
- `0x18006cfd0`
- `0x18008cf34`
- `0x1800cea98`
- `0x1800d03f4`
- `0x1800d0c0c`
- `0x1800e8b00`
- `0x1800efd20`
- `0x1800f1470`
- `0x1800f3fb4`
- `0x1800fe130`
- `0x1801e5458`
- `0x1801e67c4`
- `0x1803d3480`
- `0x1804960a0`
- `0x180496148`
- `0x1804d89dc`
- `0x1804e487c`
- `0x1804e7254`
- `0x180519624`
- `0x1805288c0`
- `0x180537abc`
- `0x18053849c`
- `0x18053ab60`
- `0x18056adb8`
- `0x18056c41c`
- `0x18056cb00`
- `0x180647668`
- `0x180679548`
- `0x1806877a8`
- `0x180687890`
- `0x180687a78`
- `0x180688828`
- `0x18069f6ac`
- `0x1806b2e84`
- `0x1806e018c`
- `0x1806eb1b0`
- `0x180704fa4`
- `0x18076e110`
- `0x1809a3104`
- `0x1809a3154`
- `0x1809a3218`
- `0x1809a32e4`
- `0x1809a3434`
- `0x1809a3544`
- `0x1809a3610`

## import_xrefs

- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1800cf899`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1800cf899`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cee06`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cf041`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cf0c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cf0dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cee06`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cf041`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cf0c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cf0dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800ced83`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800ced83`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x1800ced97`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x1800ced97`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
__int64 __fastcall DirectUI::CValueBoxer::BoxObjectValue(
        CValue *box,
        const xstring_ptr_storage *pSourceType,
        DirectUI::DependencyObject *value,
        HSTRING__ *buffer,
        DirectUI::DependencyObject **ppMOR,
        unsigned __int8 bPreserveObjectIdentity)
{
  HSTRING__ *v6; // r13
  DirectUI::DependencyObject *v7; // r9
  const xstring_ptr_storage *ClassInfoByIndex; // rdi
  HSTRING__ *v10; // rbx
  Windows::Foundation::IPropertyValue *UniversalTime; // rsi
  __int64 v12; // r12
  IInspectable *v13; // r14
  DirectUI::DependencyObject *ptr; // r12
  DirectUI::BoxerBuffer *v15; // r8
  unsigned int Buffer_low; // ecx
  unsigned int v17; // ecx
  unsigned int v18; // ecx
  HRESULT v20; // eax
  unsigned int v21; // r13d
  unsigned int v22; // ecx
  unsigned int v23; // ecx
  unsigned int v24; // ecx
  unsigned int v25; // ecx
  unsigned int v26; // ecx
  HRESULT v27; // eax
  unsigned int v28; // ebx
  int v29; // eax
  HRESULT v30; // edi
  UINT32 StringLen; // eax
  int v32; // edi
  unsigned int v33; // ebx
  xstring_ptr *p_bValue; // rcx
  unsigned int v35; // ecx
  unsigned int v36; // ecx
  unsigned int v37; // ecx
  unsigned int v38; // ecx
  unsigned int v39; // ecx
  HRESULT v40; // eax
  DirectUI::BoxerBuffer *v41; // r8
  HRESULT v42; // ebx
  HRESULT v43; // eax
  unsigned int v44; // ecx
  unsigned int v45; // ecx
  unsigned int v46; // ecx
  unsigned int v47; // ecx
  bool v48; // r12
  const xstring_ptr_storage *v49; // rcx
  __int64 v50; // rdi
  unsigned int v51; // eax
  CDependencyObject *v52; // rcx
  KnownTypeIndex v53; // cx
  unsigned int Storage; // ebx
  HRESULT v55; // eax
  HSTRING__ *v56; // rcx
  unsigned int v57; // ecx
  HRESULT v58; // eax
  CDependencyObject *Handle; // rax
  HRESULT ClassInfoFromOtherTypeBox; // eax
  unsigned int v61; // edi
  HRESULT ClassInfoFromObject_Helper; // eax
  DirectUI::BoxerBuffer *v63; // r8
  HRESULT v64; // eax
  HSTRING__ *v65; // rcx
  unsigned int v66; // ecx
  unsigned int v67; // ecx
  HRESULT v68; // eax
  DirectUI::BoxerBuffer *v69; // r8
  DirectUI::BoxerBuffer *v70; // r8
  HRESULT v71; // eax
  HSTRING__ *hstring; // rcx
  DirectUI::BoxerBuffer *v73; // r8
  unsigned int v74; // xmm6_4
  HRESULT v75; // ecx
  DirectUI::BoxerBuffer *v76; // r8
  DirectUI::BoxerBuffer *v77; // r8
  DirectUI::BoxerBuffer *v78; // r8
  DirectUI::BoxerBuffer *v79; // r8
  DirectUI::BoxerBuffer *v80; // r8
  DirectUI::BoxerBuffer *v81; // r8
  DirectUI::BoxerBuffer *v82; // r8
  DirectUI::BoxerBuffer *v83; // r8
  DirectUI::BoxerBuffer *v84; // r8
  DirectUI::BoxerBuffer *v85; // r8
  HRESULT v86; // eax
  DirectUI::BoxerBuffer *v87; // r8
  DirectUI::BoxerBuffer *v88; // r8
  DirectUI::BoxerBuffer *v89; // r8
  DirectUI::BoxerBuffer *v90; // r8
  unsigned int v91; // ebx
  unsigned int UniversalTime_high; // edi
  DirectUI::BoxerBuffer *v93; // r8
  Windows::Internal::String cStowedExceptions; // [rsp+28h] [rbp-79h] BYREF
  xstring_ptr bValue; // [rsp+30h] [rbp-71h] BYREF
  ctl::ComPtr<IInspectable> spValueAsInsp; // [rsp+38h] [rbp-69h] BYREF
  Windows::Foundation::DateTime dateTimeValue; // [rsp+40h] [rbp-61h] BYREF
  Windows::Foundation::Rect newString; // [rsp+48h] [rbp-59h] OVERLAPPED BYREF
  int v99; // [rsp+58h] [rbp-49h] BYREF
  unsigned __int16 v100; // [rsp+5Ch] [rbp-45h] BYREF
  __int16 nValue[2]; // [rsp+60h] [rbp-41h] BYREF
  unsigned __int16 v102; // [rsp+64h] [rbp-3Dh] BYREF
  ctl::ComPtr<DirectUI::DependencyObject> spMOR; // [rsp+68h] [rbp-39h] BYREF
  _BYTE rectValue[24]; // [rsp+70h] [rbp-31h] OVERLAPPED BYREF

  v6 = buffer;
  cStowedExceptions._hstring = buffer;
  v7 = value;
  *(_QWORD *)&newString.X = ppMOR;
  ClassInfoByIndex = pSourceType;
  spMOR.ptr_ = value;
  bValue.m_encodedStorage.Storage = pSourceType;
  if ( !box )
  {
    OnNewFailure_1172_(0);
    return 2147500035LL;
  }
  if ( !v6 || !ppMOR )
  {
    OnNewFailure_1172_((HRESULT)box);
    return 2147500035LL;
  }
  v10 = 0;
  v99 = 0;
  UniversalTime = 0;
  *(_QWORD *)rectValue = 0;
  v12 = 0;
  dateTimeValue.UniversalTime = 0;
  *(_QWORD *)&rectValue[8] = 0;
  if ( value
    && value->QueryInterface(value, &GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62, (void **)&dateTimeValue) >= 0
    && dateTimeValue.UniversalTime )
  {
    UniversalTime = (Windows::Foundation::IPropertyValue *)dateTimeValue.UniversalTime;
    *(Windows::Foundation::DateTime *)&rectValue[8] = dateTimeValue;
    v12 = dateTimeValue.UniversalTime;
  }
  v13 = 0;
  dateTimeValue.UniversalTime = 0;
  **(_QWORD **)&newString.X = 0;
  if ( !v12 )
  {
    ptr = spMOR.ptr_;
    if ( !spMOR.ptr_ )
      goto LABEL_33;
    ((void (__fastcall *)(DirectUI::DependencyObject *, const xstring_ptr_storage *, DirectUI::DependencyObject *, DirectUI::DependencyObject *))spMOR.ptr_->AddRef)(
      spMOR.ptr_,
      pSourceType,
      value,
      v7);
    v13 = ptr;
    dateTimeValue.UniversalTime = (__int64)ptr;
LABEL_11:
    if ( v13 )
    {
      if ( ClassInfoByIndex && (bPreserveObjectIdentity || LOWORD(ClassInfoByIndex->Buffer) != 40) )
      {
LABEL_15:
        if ( LOWORD(ClassInfoByIndex->Buffer) == 149 || (HIDWORD(ClassInfoByIndex->Handle) & 0x800) != 0 )
        {
          switch ( v99 )
          {
            case 4:
              LODWORD(spMOR.ptr_) = 0;
              v43 = UniversalTime->GetInt32(UniversalTime, (int *)&spMOR);
              v28 = v43;
              if ( v43 >= 0 )
              {
                v43 = DirectUI::CValueBoxer::BoxEnumValue(box, (unsigned int)spMOR.ptr_);
                v28 = v43;
                if ( v43 >= 0 )
                  goto LABEL_55;
              }
              goto LABEL_106;
            case 5:
              LODWORD(bValue.m_encodedStorage.Storage) = 0;
              v58 = UniversalTime->GetUInt32(UniversalTime, (unsigned int *)&bValue);
              v28 = v58;
              if ( v58 >= 0 )
              {
                v58 = DirectUI::CValueBoxer::BoxEnumValue(box, bValue.m_encodedStorage.RuntimeStringHandleMarker);
                v28 = v58;
                if ( v58 >= 0 )
                {
                  v28 = 0;
                  goto LABEL_187;
                }
              }
              goto LABEL_328;
            case 20:
              LODWORD(bValue.m_encodedStorage.Storage) = 0;
              if ( GetEnumValueFromKnownWinRTBox(ptr, (const CClassInfo *)ClassInfoByIndex, (unsigned int *)&bValue) >= 0 )
              {
                Storage = (unsigned int)bValue.m_encodedStorage.Storage;
                HIDWORD(dateTimeValue.UniversalTime) = LOWORD(ClassInfoByIndex->Buffer);
                LODWORD(dateTimeValue.UniversalTime) = bValue.m_encodedStorage.Storage;
                CValue::ReleaseAndReset(box);
                box->m_flags.m_state.m_asOne &= 0xFFFFFFC3;
                box->m_flags.m_state.m_asOne |= 0x43u;
                box->m_value.m_any[1] = HIDWORD(dateTimeValue.UniversalTime);
                box->m_value.m_any[0] = Storage;
                goto LABEL_55;
              }
              break;
          }
        }
        Buffer_low = LOWORD(ClassInfoByIndex->Buffer);
        if ( Buffer_low <= 0xD1 )
        {
          if ( Buffer_low == 209 )
          {
            v58 = DirectUI::CValueBoxer::BoxValue<Windows::UI::Xaml::Media::Matrix>(
                    box,
                    v13,
                    (DirectUI::BoxerBuffer *)v6);
            v28 = v58;
            if ( v58 >= 0 )
              goto LABEL_55;
            goto LABEL_328;
          }
          if ( Buffer_low > 0x70 )
          {
            v17 = Buffer_low - 129;
            if ( v17 )
            {
              v18 = v17 - 11;
              if ( !v18 )
              {
                dateTimeValue.UniversalTime = 0;
                if ( !UniversalTime )
                {
LABEL_23:
                  OnNewFailure_1208_(0);
LABEL_24:
                  v13->Release(v13);
                  return 2147500037LL;
                }
                v43 = UniversalTime->GetDouble(UniversalTime, (long double *)&dateTimeValue.UniversalTime);
                v28 = v43;
                if ( v43 < 0 )
                  goto LABEL_106;
                v91 = dateTimeValue.UniversalTime;
                UniversalTime_high = HIDWORD(dateTimeValue.UniversalTime);
                CValue::ReleaseAndReset(box);
                box->m_flags.m_state.m_asOne &= 0xFFFFFFC9;
                box->m_flags.m_state.m_asOne |= 0x49u;
                box->m_value.m_any[0] = v91;
                box->m_value.m_any[1] = UniversalTime_high;
                goto LABEL_55;
              }
              v57 = v18 - 18;
              if ( !v57 )
              {
                if ( !CQuirksMode2::QuirkBoxDataContextPropertyValues() )
                {
                  ctl::ComPtr<DirectUI::Storyboard>::InternalRelease((ctl::ComPtr<DirectUI::SoftwareBitmapSource> *)rectValue);
                  v58 = DirectUI::ExternalObjectReference::ConditionalWrap(
                          v13,
                          (DirectUI::DependencyObject **)rectValue,
                          0);
                  v28 = v58;
                  if ( v58 >= 0 )
                  {
                    v10 = *(HSTRING__ **)rectValue;
                    Handle = DirectUI::DependencyObject::GetHandle(*(DirectUI::DependencyObject **)rectValue);
                    CValue::SetAddRef<24>(box, Handle);
LABEL_88:
                    **(_QWORD **)&newString.X = v10;
LABEL_55:
                    v13->Release(v13);
                    goto LABEL_34;
                  }
                  goto LABEL_328;
                }
                cStowedExceptions._hstring = 0;
                ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&cStowedExceptions);
                v13->QueryInterface(
                  v13,
                  &GUID_92467e64_d66a_4cf4_9322_3d23b3c0c361,
                  (void **)&cStowedExceptions._hstring);
                v71 = DirectUI::CValueBoxer::BoxValue(
                        box,
                        (Windows::UI::Xaml::Media::IFontFamily *)cStowedExceptions._hstring,
                        v70);
                v28 = v71;
                if ( v71 < 0 )
                {
                  OnFailure_2990_(v71);
                  hstring = cStowedExceptions._hstring;
                  if ( cStowedExceptions._hstring )
                  {
                    cStowedExceptions._hstring = 0;
                    (*(void (__fastcall **)(HSTRING__ *))(*(_QWORD *)hstring + 16LL))(hstring);
                  }
                  goto LABEL_107;
                }
LABEL_314:
                ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&cStowedExceptions);
                goto LABEL_55;
              }
              v66 = v57 - 1;
              if ( !v66 )
              {
                v58 = DirectUI::CValueBoxer::BoxValue<Windows::UI::Text::FontWeight>(box, v13, v15);
                v28 = v58;
                if ( v58 >= 0 )
                  goto LABEL_55;
                goto LABEL_328;
              }
              v67 = v66 - 6;
              if ( !v67 )
              {
                v58 = DirectUI::CValueBoxer::BoxValue<Windows::UI::Xaml::GridLength>(
                        box,
                        v13,
                        (DirectUI::BoxerBuffer *)v6);
                v28 = v58;
                if ( v58 >= 0 )
                  goto LABEL_55;
                goto LABEL_328;
              }
              if ( v67 == 22 )
              {
                switch ( v99 )
                {
                  case 1:
                    BYTE1(spValueAsInsp.ptr_) = 0;
                    v58 = UniversalTime->GetUInt8(UniversalTime, (unsigned __int8 *)&spValueAsInsp.ptr_ + 1);
                    v28 = v58;
                    if ( v58 >= 0 )
                    {
                      v58 = DirectUI::CValueBoxer::BoxValue(box, BYTE1(spValueAsInsp.ptr_), v90);
                      v28 = v58;
                      if ( v58 >= 0 )
                        goto LABEL_55;
                    }
                    break;
                  case 2:
                    LOWORD(spMOR.ptr_) = 0;
                    v58 = UniversalTime->GetInt16(UniversalTime, (__int16 *)&spMOR);
                    v28 = v58;
                    if ( v58 >= 0 )
                    {
                      v58 = DirectUI::CValueBoxer::BoxValue(box, SLOWORD(spMOR.ptr_), v89);
                      v28 = v58;
                      if ( v58 >= 0 )
                        goto LABEL_55;
                    }
                    break;
                  case 3:
                    v102 = 0;
                    v58 = UniversalTime->GetUInt16(UniversalTime, &v102);
                    v28 = v58;
                    if ( v58 >= 0 )
                    {
                      v58 = DirectUI::CValueBoxer::BoxValue(box, v102, v88);
                      v28 = v58;
                      if ( v58 >= 0 )
                        goto LABEL_55;
                    }
                    break;
                  case 4:
                    LODWORD(cStowedExceptions._hstring) = 0;
                    v68 = UniversalTime->GetInt32(UniversalTime, (int *)&cStowedExceptions);
                    v28 = v68;
                    if ( v68 < 0
                      || (v68 = DirectUI::CValueBoxer::BoxValue(box, (int)cStowedExceptions._hstring, v69),
                          v28 = v68,
                          v68 < 0) )
                    {
                      OnFailure_2990_(v68);
LABEL_107:
                      v13->Release(v13);
                      if ( UniversalTime )
                        UniversalTime->Release(UniversalTime);
                      return v28;
                    }
                    goto LABEL_55;
                  default:
                    v75 = v99 - 5;
                    if ( v99 != 5 )
                    {
                      if ( v99 == 9 )
                      {
                        *(_QWORD *)&newString.X = 0;
                        v58 = UniversalTime->GetDouble(UniversalTime, (long double *)&newString.X);
                        v28 = v58;
                        if ( v58 >= 0 )
                        {
                          v58 = DirectUI::CValueBoxer::BoxValue(box, *(long double *)&newString.X, v85);
                          v28 = v58;
                          if ( v58 >= 0 )
                            goto LABEL_55;
                        }
                        break;
                      }
                      goto LABEL_240;
                    }
                    LODWORD(cStowedExceptions._hstring) = 0;
                    v86 = UniversalTime->GetUInt32(UniversalTime, (unsigned int *)&cStowedExceptions);
                    v28 = v86;
                    if ( v86 >= 0 )
                    {
                      v86 = DirectUI::CValueBoxer::BoxValue(box, (int)cStowedExceptions._hstring, v87);
                      v28 = v86;
                      if ( v86 >= 0 )
                        goto LABEL_55;
                    }
                    OnFailure_2990_(v86);
LABEL_187:
                    ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&dateTimeValue);
                    ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&rectValue[8]);
                    ctl::ComPtr<DirectUI::Storyboard>::InternalRelease((ctl::ComPtr<DirectUI::SoftwareBitmapSource> *)rectValue);
                    return v28;
                }
LABEL_328:
                OnFailure_2990_(v58);
                goto LABEL_187;
              }
LABEL_73:
              bValue.m_encodedStorage.Storage = 0;
              cStowedExceptions._hstring = 0;
              v48 = 1;
              if ( v13->QueryInterface(
                     v13,
                     &GUID_5c526665_f60e_4912_af59_5fe0680f089d,
                     (void **)&cStowedExceptions._hstring) >= 0
                && (*((_BYTE *)cStowedExceptions._hstring + 70) & 2) == 0 )
              {
                v48 = *((_QWORD *)cStowedExceptions._hstring + 18) == 0;
              }
              if ( cStowedExceptions._hstring )
                (*(void (__fastcall **)(HSTRING__ *))(*(_QWORD *)cStowedExceptions._hstring + 16LL))(cStowedExceptions._hstring);
              if ( v48 )
              {
                cStowedExceptions._hstring = 0;
                v55 = ctl::make<DirectUI::ExternalObjectReference>((ctl::Internal::ComPtrRef<ctl::ComPtr<DirectUI::ExternalObjectReference> >)&cStowedExceptions);
                v30 = v55;
                if ( v55 < 0 )
                {
                  OnFailure_2990_(v55);
                }
                else if ( *((_QWORD *)cStowedExceptions._hstring + 24) )
                {
                  OnNewFailure_2955_((HRESULT)cStowedExceptions._hstring);
                  v30 = -2147418113;
                  OnFailure_2990_(-2147418113);
                }
                else
                {
                  ctl::WeakReferenceSourceNoThreadId::SetPtrValue<IInspectable,IInspectable>(
                    (ctl::WeakReferenceSourceNoThreadId *)(cStowedExceptions._hstring + 2),
                    (DirectUI::TrackerPtr<IInspectable,1,0> *)cStowedExceptions._hstring + 8,
                    v13);
                  v10 = cStowedExceptions._hstring;
                  v30 = 0;
                  *(Windows::Internal::String *)rectValue = cStowedExceptions;
                  cStowedExceptions._hstring = 0;
                }
                if ( cStowedExceptions._hstring )
                {
                  v56 = cStowedExceptions._hstring + 2;
                  cStowedExceptions._hstring = 0;
                  (*(void (__fastcall **)(HSTRING__ *))(*(_QWORD *)v56 + 16LL))(v56);
                }
                if ( v30 >= 0 )
                  goto LABEL_101;
              }
              else
              {
                v30 = v13->QueryInterface(v13, &GUID_5c526665_f60e_4912_af59_5fe0680f089d, (void **)&bValue);
                if ( v30 >= 0 )
                {
                  v10 = bValue.m_encodedStorage.Handle;
                  v49 = 0;
                  *(xstring_ptr *)rectValue = bValue;
                  bValue.m_encodedStorage.Storage = 0;
LABEL_81:
                  if ( v49 )
                    (*((void (__fastcall **)(const xstring_ptr_storage *))v49->Buffer + 2))(v49);
                  if ( v30 >= 0 )
                  {
                    if ( (*((_BYTE *)v10 + 70) & 2) != 0 )
                    {
                      LODWORD(v50) = 0;
                      dateTimeValue.UniversalTime = 0;
                    }
                    else
                    {
                      v50 = *((_QWORD *)v10 + 18);
                      dateTimeValue.UniversalTime = v50;
                    }
                    CValue::ReleaseAndReset(box);
                    box->m_flags.m_state.m_asOne &= 0xFFFFFFD8;
                    box->m_flags.m_state.m_asOne |= 0x58u;
                    v51 = HIDWORD(dateTimeValue.UniversalTime);
                    LODWORD(dateTimeValue.UniversalTime) = v50;
                    v52 = (CDependencyObject *)dateTimeValue.UniversalTime;
                    box->m_value.m_any[0] = v50;
                    box->m_value.m_any[1] = v51;
                    if ( v52 )
                      CDependencyObject::AddRef(v52);
                    goto LABEL_88;
                  }
                  OnFailure_2990_(v30);
                  goto LABEL_186;
                }
              }
              OnFailure_2990_(v30);
LABEL_101:
              v49 = bValue.m_encodedStorage.Storage;
              goto LABEL_81;
            }
            v43 = DirectUI::CValueBoxer::BoxValue<Windows::UI::Xaml::CornerRadius>(
                    box,
                    v13,
                    (DirectUI::BoxerBuffer *)v6);
            v28 = v43;
            if ( v43 >= 0 )
              goto LABEL_55;
LABEL_106:
            OnFailure_2990_(v43);
            goto LABEL_107;
          }
          if ( Buffer_low == 112 )
          {
            v58 = DirectUI::CValueBoxer::BoxValue<Windows::UI::Color>(box, v13, v15);
            v28 = v58;
            if ( v58 >= 0 )
              goto LABEL_55;
            goto LABEL_328;
          }
          v35 = Buffer_low - 10;
          if ( v35 )
          {
            v36 = v35 - 16;
            if ( !v36 )
            {
              switch ( v99 )
              {
                case 1:
                  LOBYTE(spValueAsInsp.ptr_) = 0;
                  v58 = UniversalTime->GetUInt8(UniversalTime, (unsigned __int8 *)&spValueAsInsp);
                  v28 = v58;
                  if ( v58 >= 0 )
                  {
                    v58 = DirectUI::CValueBoxer::BoxValue(box, LOBYTE(spValueAsInsp.ptr_), v83);
                    v28 = v58;
                    if ( v58 >= 0 )
                      goto LABEL_55;
                  }
                  break;
                case 2:
                  nValue[0] = 0;
                  v58 = UniversalTime->GetInt16(UniversalTime, nValue);
                  v28 = v58;
                  if ( v58 >= 0 )
                  {
                    v58 = DirectUI::CValueBoxer::BoxValue(box, nValue[0], v82);
                    v28 = v58;
                    if ( v58 >= 0 )
                      goto LABEL_55;
                  }
                  break;
                case 3:
                  v100 = 0;
                  v58 = UniversalTime->GetUInt16(UniversalTime, &v100);
                  v28 = v58;
                  if ( v58 >= 0 )
                  {
                    v58 = DirectUI::CValueBoxer::BoxValue(box, v100, v81);
                    v28 = v58;
                    if ( v58 >= 0 )
                      goto LABEL_55;
                  }
                  break;
                case 4:
                  LODWORD(bValue.m_encodedStorage.Storage) = 0;
                  v58 = UniversalTime->GetInt32(UniversalTime, (int *)&bValue);
                  v28 = v58;
                  if ( v58 >= 0 )
                  {
                    v58 = DirectUI::CValueBoxer::BoxValue(box, SLODWORD(bValue.m_encodedStorage.Storage), v80);
                    v28 = v58;
                    if ( v58 >= 0 )
                      goto LABEL_55;
                  }
                  break;
                case 5:
                  LODWORD(bValue.m_encodedStorage.Storage) = 0;
                  v58 = UniversalTime->GetUInt32(UniversalTime, (unsigned int *)&bValue);
                  v28 = v58;
                  if ( v58 >= 0 )
                  {
                    v58 = DirectUI::CValueBoxer::BoxValue(
                            box,
                            LODWORD(bValue.m_encodedStorage.RuntimeStringHandleMarker),
                            v79);
                    v28 = v58;
                    if ( v58 >= 0 )
                      goto LABEL_55;
                  }
                  break;
                case 6:
                  *(_QWORD *)&newString.X = 0;
                  v58 = UniversalTime->GetInt64(UniversalTime, (__int64 *)&newString);
                  v28 = v58;
                  if ( v58 >= 0 )
                  {
                    v58 = DirectUI::CValueBoxer::BoxValue(box, *(__int64 *)&newString.X, v78);
                    v28 = v58;
                    if ( v58 >= 0 )
                      goto LABEL_55;
                  }
                  break;
                default:
                  v75 = v99 - 7;
                  if ( v99 == 7 )
                  {
                    *(_QWORD *)&newString.X = 0;
                    v58 = UniversalTime->GetUInt64(UniversalTime, (unsigned __int64 *)&newString);
                    v28 = v58;
                    if ( v58 >= 0 )
                    {
                      v58 = DirectUI::CValueBoxer::BoxValue(box, *(__int64 *)&newString.X, v77);
                      v28 = v58;
                      if ( v58 >= 0 )
                        goto LABEL_55;
                    }
                  }
                  else
                  {
                    if ( v99 != 9 )
                    {
LABEL_240:
                      OnFailure_977_(v75);
                      goto LABEL_189;
                    }
                    *(_QWORD *)&newString.X = 0;
                    v58 = UniversalTime->GetDouble(UniversalTime, (long double *)&newString.X);
                    v28 = v58;
                    if ( v58 >= 0 )
                    {
                      v58 = DirectUI::CValueBoxer::BoxValue(box, *(long double *)&newString.X, v76);
                      v28 = v58;
                      if ( v58 >= 0 )
                        goto LABEL_55;
                    }
                  }
                  break;
              }
              goto LABEL_328;
            }
            v37 = v36 - 16;
            if ( v37 )
            {
              v38 = v37 - 1;
              if ( !v38 )
              {
                v58 = DirectUI::CValueBoxer::BoxValue<Windows::UI::Xaml::Interop::TypeName>(
                        box,
                        v13,
                        (DirectUI::BoxerBuffer *)v6);
                v28 = v58;
                if ( v58 >= 0 )
                  goto LABEL_55;
                goto LABEL_328;
              }
              v39 = v38 - 28;
              if ( v39 )
              {
                if ( v39 != 28 )
                  goto LABEL_73;
                LOBYTE(spValueAsInsp.ptr_) = 0;
                if ( !UniversalTime )
                {
                  OnNewFailure_1208_(28);
                  goto LABEL_24;
                }
                v40 = UniversalTime->GetBoolean(UniversalTime, (unsigned __int8 *)&spValueAsInsp);
                v42 = v40;
                if ( v40 < 0 )
                {
                  OnFailure_2990_(v40);
                  *(_QWORD *)&newString.X = 0;
                  LODWORD(bValue.m_encodedStorage.Storage) = 0;
                  TraceForFailFast(v42);
                  GetStowedExceptionsForFailFast(
                    (_STOWED_EXCEPTION_INFORMATION_V2 ***)&newString,
                    (unsigned int *)&bValue);
                  RoFailFastWithErrorContextInternal2(
                    v42,
                    bValue.m_encodedStorage.RuntimeStringHandleMarker,
                    *(struct _STOWED_EXCEPTION_INFORMATION_V2 **const *)&newString.X);
                }
                v43 = DirectUI::CValueBoxer::BoxValue(box, (unsigned __int8)spValueAsInsp.ptr_, v41);
                v28 = v43;
                if ( v43 >= 0 )
                  goto LABEL_55;
                goto LABEL_106;
              }
              cStowedExceptions._hstring = 0;
              ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&cStowedExceptions);
              v13->QueryInterface(v13, &GUID_9e365e57_48b2_4160_956f_c7385120bbfc, (void **)&cStowedExceptions._hstring);
              v64 = DirectUI::CValueBoxer::BoxValue(
                      box,
                      (Windows::Foundation::IUriRuntimeClass *)cStowedExceptions._hstring,
                      v63);
              v28 = v64;
              if ( v64 >= 0 )
              {
                v65 = cStowedExceptions._hstring;
                if ( cStowedExceptions._hstring )
                {
                  cStowedExceptions._hstring = 0;
                  (*(void (__fastcall **)(HSTRING__ *))(*(_QWORD *)v65 + 16LL))(v65);
                }
                goto LABEL_55;
              }
LABEL_226:
              OnFailure_2990_(v64);
              ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&cStowedExceptions);
              goto LABEL_187;
            }
            LODWORD(bValue.m_encodedStorage.Storage) = 0;
            if ( UniversalTime )
            {
              v58 = UniversalTime->GetSingle(UniversalTime, (float *)&bValue);
              v28 = v58;
              if ( v58 >= 0 )
              {
                v74 = (unsigned int)bValue.m_encodedStorage.Storage;
                CValue::ReleaseAndReset(box);
                box->m_flags.m_state.m_asOne &= 0xFFFFFFC8;
                box->m_flags.m_state.m_asOne |= 0x48u;
                box->m_value.m_any[0] = v74;
                goto LABEL_55;
              }
              goto LABEL_328;
            }
          }
          else
          {
            *(_QWORD *)&newString.X = 0;
            if ( UniversalTime )
            {
              v58 = UniversalTime->GetDateTime(UniversalTime, (Windows::Foundation::DateTime *)&newString);
              v28 = v58;
              if ( v58 >= 0 )
              {
                v58 = DirectUI::CValueBoxer::BoxValue(box, *(Windows::Foundation::DateTime *)&newString.X, v84);
                v28 = v58;
                if ( v58 >= 0 )
                  goto LABEL_55;
              }
              goto LABEL_328;
            }
          }
LABEL_188:
          OnNewFailure_1208_(0);
LABEL_189:
          v28 = -2147467259;
          goto LABEL_187;
        }
        if ( Buffer_low > 0x121 )
        {
          v44 = Buffer_low - 292;
          if ( !v44 )
          {
            v43 = DirectUI::CValueBoxer::BoxValue<Windows::UI::Xaml::Thickness>(box, v13, (DirectUI::BoxerBuffer *)v6);
            v28 = v43;
            if ( v43 >= 0 )
              goto LABEL_55;
            goto LABEL_106;
          }
          v45 = v44 - 5;
          if ( v45 )
          {
            v46 = v45 - 121;
            if ( !v46 )
            {
              v58 = DirectUI::CValueBoxer::BoxValue<Windows::UI::Xaml::Duration>(box, v13, v15);
              v28 = v58;
              if ( v58 >= 0 )
                goto LABEL_55;
              goto LABEL_328;
            }
            v47 = v46 - 36;
            if ( !v47 )
            {
              v58 = DirectUI::CValueBoxer::BoxValue<Windows::UI::Xaml::Media::Animation::KeyTime>(box, v13, v15);
              v28 = v58;
              if ( v58 >= 0 )
                goto LABEL_55;
              goto LABEL_328;
            }
            if ( v47 != 195 )
              goto LABEL_73;
            v43 = DirectUI::CValueBoxer::BoxValue<Windows::UI::Xaml::Media::Animation::RepeatBehavior>(box, v13, v15);
            v28 = v43;
            if ( v43 >= 0 )
              goto LABEL_55;
            goto LABEL_106;
          }
          *(_QWORD *)&newString.X = 0;
          if ( UniversalTime )
          {
            v43 = UniversalTime->GetTimeSpan(UniversalTime, (Windows::Foundation::TimeSpan *)&newString);
            v28 = v43;
            if ( v43 >= 0 )
            {
              v43 = DirectUI::CValueBoxer::BoxValue(box, *(Windows::Foundation::TimeSpan *)&newString.X, v73);
              v28 = v43;
              if ( v43 >= 0 )
                goto LABEL_55;
            }
            goto LABEL_106;
          }
          goto LABEL_188;
        }
        if ( Buffer_low == 289 )
        {
          v58 = DirectUI::CValueBoxer::BoxValue<Windows::UI::Xaml::Documents::TextRange>(box, v13, v15);
          v28 = v58;
          if ( v58 >= 0 )
            goto LABEL_55;
          goto LABEL_328;
        }
        v22 = Buffer_low - 210;
        if ( !v22 )
        {
          v58 = DirectUI::CValueBoxer::BoxValue<Windows::UI::Xaml::Media::Media3D::Matrix3D>(
                  box,
                  v13,
                  (DirectUI::BoxerBuffer *)v6);
          v28 = v58;
          if ( v58 >= 0 )
            goto LABEL_55;
          goto LABEL_328;
        }
        v23 = v22 - 20;
        if ( !v23 )
        {
          *(_QWORD *)&newString.X = 0;
          if ( UniversalTime )
          {
            v58 = UniversalTime->GetPoint(UniversalTime, (Windows::Foundation::Point *)&newString);
            v28 = v58;
            if ( v58 >= 0 )
            {
              v58 = DirectUI::CValueBoxer::BoxValue(
                      box,
                      *(Windows::Foundation::Point *)&newString.X,
                      (DirectUI::BoxerBuffer *)v6);
              v28 = v58;
              if ( v58 >= 0 )
                goto LABEL_55;
            }
            goto LABEL_328;
          }
          goto LABEL_188;
        }
        v24 = v23 - 12;
        if ( !v24 )
        {
          ctl::ComPtr<IInspectable>::AsOrNull<Windows::UI::Xaml::IPropertyPath>(
            (ctl::ComPtr<IInspectable> *)&dateTimeValue,
            (ctl::ComPtr<Windows::UI::Xaml::IPropertyPath> *)&cStowedExceptions);
          v64 = DirectUI::CValueBoxer::BoxValue(
                  box,
                  (Windows::UI::Xaml::IPropertyPath *)cStowedExceptions._hstring,
                  v93);
          v28 = v64;
          if ( v64 >= 0 )
            goto LABEL_314;
          goto LABEL_226;
        }
        v25 = v24 - 1;
        if ( !v25 )
        {
          *(_OWORD *)&rectValue[8] = 0;
          if ( !UniversalTime )
            goto LABEL_23;
          v43 = UniversalTime->GetRect(UniversalTime, (Windows::Foundation::Rect *)&rectValue[8]);
          v28 = v43;
          if ( v43 >= 0 )
          {
            newString = *(Windows::Foundation::Rect *)&rectValue[8];
            v43 = DirectUI::CValueBoxer::BoxValue(box, &newString, (DirectUI::BoxerBuffer *)v6);
            v28 = v43;
            if ( v43 >= 0 )
              goto LABEL_55;
          }
          goto LABEL_106;
        }
        v26 = v25 - 20;
        if ( !v26 )
        {
          *(_QWORD *)&newString.X = 0;
          if ( UniversalTime )
          {
            v58 = UniversalTime->GetSize(UniversalTime, (Windows::Foundation::Size *)&newString);
            v28 = v58;
            if ( v58 >= 0 )
            {
              v58 = DirectUI::CValueBoxer::BoxValue(
                      box,
                      *(Windows::Foundation::Size *)&newString.X,
                      (DirectUI::BoxerBuffer *)v6);
              v28 = v58;
              if ( v58 >= 0 )
                goto LABEL_55;
            }
            goto LABEL_328;
          }
          goto LABEL_188;
        }
        if ( v26 != 6 )
          goto LABEL_73;
        cStowedExceptions._hstring = 0;
        if ( !UniversalTime )
        {
          OnNewFailure_1208_(6);
          goto LABEL_24;
        }
        v27 = UniversalTime->GetString(UniversalTime, &cStowedExceptions._hstring);
        v28 = v27;
        if ( v27 < 0 )
        {
          OnFailure_2990_(v27);
          if ( cStowedExceptions._hstring )
            WindowsDeleteString(cStowedExceptions._hstring);
          goto LABEL_107;
        }
        if ( cStowedExceptions._hstring )
        {
          bValue.m_encodedStorage.Storage = xstring_ptr_constants::c_xencoded_string_ptr_null.Storage;
          *(_QWORD *)&newString.X = 0;
          newString.Width = 0.0;
          v29 = WindowsDuplicateString(cStowedExceptions._hstring, (HSTRING *)&newString);
          v30 = v29;
          if ( v29 < 0 )
          {
            OnFailure_2990_(v29);
          }
          else
          {
            StringLen = WindowsGetStringLen(*(HSTRING *)&newString.X);
            if ( StringLen <= 0x3FFFFFFF )
            {
              v32 = LODWORD(newString.X) | 1;
              LODWORD(newString.Width) = StringLen & 0x3FFFFFFF | 0x80000000;
              *(_QWORD *)&rectValue[8] = *(_QWORD *)&newString.X | 1LL;
              if ( ((__int64)xstring_ptr_constants::c_xencoded_string_ptr_null.Storage & 1) != 0 )
                WindowsDeleteString((HSTRING)(xstring_ptr_constants::c_xencoded_string_ptr_null.RuntimeStringHandleMarker
                                            & 0xFFFFFFFFFFFFFFFEuLL));
              v33 = *(_DWORD *)&rectValue[12];
              CValue::ReleaseAndReset(box);
              box->m_flags.m_state.m_asOne &= 0xFFFFFFCE;
              p_bValue = &bValue;
              box->m_flags.m_state.m_asOne |= 0x4Eu;
              bValue.m_encodedStorage.Storage = xstring_ptr_constants::c_xencoded_string_ptr_null.Storage;
              box->m_value.m_any[0] = v32;
              box->m_value.m_any[1] = v33;
              goto LABEL_53;
            }
            v30 = -2147467259;
            OnNewFailure_1208_(0x3FFFFFFF);
          }
          OnFailure_2990_(v30);
          xstring_ptr::~xstring_ptr(&bValue);
          OnFailure_2990_(v30);
          Windows::Internal::String::~String(&cStowedExceptions);
LABEL_186:
          v28 = v30;
          goto LABEL_187;
        }
        CValue::ReleaseAndReset(box);
        box->m_flags.m_state.m_asOne &= 0xFFFFFFCE;
        p_bValue = (xstring_ptr *)&rectValue[8];
        box->m_flags.m_state.m_asOne |= 0x4Eu;
        *(xencoded_string_ptr *)&rectValue[8] = xstring_ptr_constants::c_xencoded_string_ptr_null;
        box->m_value = (CValueDetails::Value)xstring_ptr_constants::c_xencoded_string_ptr_null.Storage;
LABEL_53:
        xstring_ptr::~xstring_ptr(p_bValue);
        if ( cStowedExceptions._hstring )
          WindowsDeleteString(cStowedExceptions._hstring);
        goto LABEL_55;
      }
      ClassInfoFromObject_Helper = DirectUI::MetadataAPI::GetClassInfoFromObject_Helper(
                                     ptr,
                                     (const CClassInfo **)&bValue,
                                     0);
      v61 = ClassInfoFromObject_Helper;
      if ( ClassInfoFromObject_Helper >= 0 )
      {
        ClassInfoByIndex = bValue.m_encodedStorage.Storage;
        goto LABEL_15;
      }
      OnFailure_2990_(ClassInfoFromObject_Helper);
      goto LABEL_138;
    }
LABEL_33:
    CValue::ReleaseAndReset(box);
    box->m_flags.m_state.m_asOne &= 0xFFFFFFC1;
    box->m_flags.m_state.m_asOne |= 0x41u;
LABEL_34:
    if ( UniversalTime )
      UniversalTime->Release(UniversalTime);
    return 0;
  }
  v20 = (*(__int64 (__fastcall **)(__int64, int *, DirectUI::DependencyObject *, DirectUI::DependencyObject *))(*(_QWORD *)v12 + 48LL))(
          v12,
          &v99,
          value,
          v7);
  v21 = v20;
  if ( v20 < 0 )
  {
    OnFailure_2990_(v20);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    return v21;
  }
  ptr = spMOR.ptr_;
  if ( v99 && spMOR.ptr_ )
  {
    spMOR.ptr_->AddRef(spMOR.ptr_);
    v13 = ptr;
    dateTimeValue.UniversalTime = (__int64)ptr;
  }
  if ( ClassInfoByIndex && (bPreserveObjectIdentity || LOWORD(ClassInfoByIndex->Buffer) != 40) )
  {
LABEL_32:
    v6 = cStowedExceptions._hstring;
    goto LABEL_11;
  }
  ClassInfoByIndex = 0;
  bValue.m_encodedStorage.Storage = 0;
  if ( v99 <= 10 )
  {
    if ( v99 == 10 )
    {
      v53 = Char16;
    }
    else
    {
      if ( v99 != 1 )
      {
        if ( v99 == 2 )
        {
          v53 = Int16;
          goto LABEL_97;
        }
        if ( v99 == 3 )
        {
          v53 = UInt16;
          goto LABEL_97;
        }
        if ( v99 != 4 && v99 != 5 )
        {
          switch ( v99 )
          {
            case 6:
            case 7:
              v53 = Int64;
              break;
            case 8:
              v53 = Float;
              break;
            case 9:
              v53 = Double;
              break;
            default:
              goto LABEL_32;
          }
          goto LABEL_97;
        }
      }
      v53 = Int32;
    }
LABEL_97:
    ClassInfoByIndex = (const xstring_ptr_storage *)DirectUI::MetadataAPI::GetClassInfoByIndex(v53);
    bValue.m_encodedStorage.Storage = ClassInfoByIndex;
    goto LABEL_32;
  }
  switch ( v99 )
  {
    case 11:
      v53 = Boolean;
      goto LABEL_97;
    case 12:
      v53 = String;
      goto LABEL_97;
    case 15:
      v53 = TimeSpan;
      goto LABEL_97;
    case 16:
      v53 = Guid;
      goto LABEL_97;
    case 17:
      v53 = Point;
      goto LABEL_97;
    case 18:
      v53 = Size;
      goto LABEL_97;
    case 19:
      v53 = Rect;
      goto LABEL_97;
  }
  if ( v99 != 20 )
    goto LABEL_32;
  ClassInfoFromOtherTypeBox = DirectUI::MetadataAPI::GetClassInfoFromOtherTypeBox(
                                UniversalTime,
                                (const CClassInfo **)&bValue);
  v61 = ClassInfoFromOtherTypeBox;
  if ( ClassInfoFromOtherTypeBox >= 0 )
  {
    ClassInfoByIndex = bValue.m_encodedStorage.Storage;
    goto LABEL_32;
  }
  OnFailure_2990_(ClassInfoFromOtherTypeBox);
  OnFailure_2990_(v61);
  if ( v13 )
LABEL_138:
    v13->Release(v13);
  if ( UniversalTime )
    UniversalTime->Release(UniversalTime);
  return v61;
}

```

## disassembly

```asm
0x1800cea98  mov     rax, rsp
0x1800cea9b  push    rbp
0x1800cea9c  push    rbx
0x1800cea9d  push    rsi
0x1800cea9e  push    rdi
0x1800cea9f  push    r12
0x1800ceaa1  push    r13
0x1800ceaa3  push    r14
0x1800ceaa5  push    r15
0x1800ceaa7  lea     rbp, [rax-4Fh]
0x1800ceaab  sub     rsp, 0A8h
0x1800ceab2  movaps  xmmword ptr [rax-58h], xmm6
0x1800ceab6  mov     rax, cs:__security_cookie
0x1800ceabd  xor     rax, rsp
0x1800ceac0  mov     [rbp+47h+var_60], rax
0x1800ceac4  mov     rbx, [rbp+47h+arg_20]
0x1800ceac8  mov     r13, buffer
0x1800ceacb  mov     [rbp+47h+cStowedExceptions], buffer
0x1800ceacf  mov     buffer, value
0x1800cead2  mov     [rbp+47h+newString], rbx
0x1800cead6  mov     rdi, pSourceType
0x1800cead9  mov     [rbp+47h+spMOR.ptr_], value
0x1800ceadd  mov     r15, box
0x1800ceae0  mov     [rbp+47h+bValue], pSourceType
0x1800ceae4  test    box, box
0x1800ceae7  jz      loc_1800CF000
0x1800ceaed  test    r13, r13
0x1800ceaf0  jz      loc_1800CFFE0
0x1800ceaf6  test    rbx, rbx
0x1800ceaf9  jz      loc_1800CFFD6
0x1800ceaff  xor     ebx, ebx
0x1800ceb01  mov     [rbp+47h+var_90], 0
0x1800ceb08  xor     esi, esi
0x1800ceb0a  mov     qword ptr [rbp+47h+rectValue.X], rbx
0x1800ceb0e  xor     r12d, r12d
0x1800ceb11  mov     [rbp+47h+dateTimeValue.UniversalTime], rbx
0x1800ceb15  mov     qword ptr [rbp+47h+rectValue.Width], rsi
0x1800ceb19  test    value, value
0x1800ceb1c  jz      short loc_1800CEB4E
0x1800ceb1e  mov     rax, [value]
0x1800ceb21  lea     pSourceType, _GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62
0x1800ceb28  lea     value, [rbp+47h+dateTimeValue]
0x1800ceb2c  mov     box, buffer
0x1800ceb2f  mov     rax, [rax]
0x1800ceb32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ceb37  test    eax, eax
0x1800ceb39  js      short loc_1800CEB4E
0x1800ceb3b  mov     rax, [rbp+47h+dateTimeValue.UniversalTime]
0x1800ceb3f  test    rax, rax
0x1800ceb42  jz      short loc_1800CEB4E
0x1800ceb44  mov     rsi, rax
0x1800ceb47  mov     qword ptr [rbp+47h+rectValue.Width], rax
0x1800ceb4b  mov     r12, rax
0x1800ceb4e  mov     rax, [rbp+47h+newString]
0x1800ceb52  xor     r14d, r14d
0x1800ceb55  mov     [rbp+47h+dateTimeValue.UniversalTime], r14
0x1800ceb59  mov     [rax], rbx
0x1800ceb5c  test    r12, r12
0x1800ceb5f  jnz     loc_1800CEC30
0x1800ceb65  mov     r12, [rbp+47h+spMOR.ptr_]
0x1800ceb69  test    r12, r12
0x1800ceb6c  jz      loc_1800CEC95
0x1800ceb72  mov     rax, [r12]
0x1800ceb76  mov     box, r12
0x1800ceb79  mov     rax, [rax+8]
0x1800ceb7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ceb82  mov     r14, r12
0x1800ceb85  mov     [rbp+47h+dateTimeValue.UniversalTime], r12
0x1800ceb89  test    r14, r14
0x1800ceb8c  jz      loc_1800CEC95
0x1800ceb92  test    rdi, rdi
0x1800ceb95  jz      loc_1800CF2FE
0x1800ceb9b  cmp     [rbp+47h+arg_28], bl
0x1800ceb9e  jnz     short loc_1800CEBAA
0x1800ceba0  cmp     word ptr [rdi], 28h ; '('
0x1800ceba4  jz      loc_1800CF2FE
0x1800cebaa  mov     eax, 95h
0x1800cebaf  cmp     [rdi], ax
0x1800cebb2  jz      loc_1800CF0E4
0x1800cebb8  test    dword ptr [rdi+4], 800h
0x1800cebbf  jnz     loc_1800CF0E4
0x1800cebc5  xor     r12d, r12d
0x1800cebc8  movzx   ecx, word ptr [rdi]
0x1800cebcb  mov     eax, 0D1h
0x1800cebd0  cmp     ecx, eax
0x1800cebd2  ja      loc_1800CECE5
0x1800cebd8  jz      loc_1800CFE33
0x1800cebde  cmp     ecx, 70h ; 'p'
0x1800cebe1  jbe     loc_1800CEE29
0x1800cebe7  sub     ecx, 81h
0x1800cebed  jz      loc_1800CF086
0x1800cebf3  sub     ecx, 0Bh; failedFrameHR
0x1800cebf6  jnz     loc_1800CF259
0x1800cebfc  xorps   xmm0, xmm0
0x1800cebff  movsd   [rbp+47h+dateTimeValue.UniversalTime], xmm0
0x1800cec04  test    rsi, rsi
0x1800cec07  jnz     loc_1800CF22D
0x1800cec0d  call    OnNewFailure_1208_
0x1800cec12  test    r14, r14
0x1800cec15  jz      short loc_1800CEC26
0x1800cec17  mov     rax, [r14]
0x1800cec1a  mov     box, r14
0x1800cec1d  mov     rax, [rax+10h]
0x1800cec21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cec26  mov     eax, 80004005h
0x1800cec2b  jmp     loc_1800CECBD
0x1800cec30  mov     rax, [r12]
0x1800cec34  lea     pSourceType, [rbp+47h+var_90]
0x1800cec38  mov     box, r12
0x1800cec3b  mov     rax, [rax+30h]
0x1800cec3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cec44  mov     r13d, eax
0x1800cec47  test    eax, eax
0x1800cec49  js      loc_1800CF00F
0x1800cec4f  mov     r12, [rbp+47h+spMOR.ptr_]
0x1800cec53  cmp     [rbp+47h+var_90], ebx
0x1800cec56  jz      short loc_1800CEC74
0x1800cec58  test    r12, r12
0x1800cec5b  jz      short loc_1800CEC74
0x1800cec5d  mov     rax, [r12]
0x1800cec61  mov     box, r12
0x1800cec64  mov     rax, [rax+8]
0x1800cec68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cec6d  mov     r14, r12
0x1800cec70  mov     [rbp+47h+dateTimeValue.UniversalTime], r12
0x1800cec74  test    rdi, rdi
0x1800cec77  jz      loc_1800CF04C
0x1800cec7d  cmp     [rbp+47h+arg_28], bl
0x1800cec80  jnz     short loc_1800CEC8C
0x1800cec82  cmp     word ptr [rdi], 28h ; '('
0x1800cec86  jz      loc_1800CF04C
0x1800cec8c  mov     r13, [rbp+47h+cStowedExceptions]
0x1800cec90  jmp     loc_1800CEB89
0x1800cec95  mov     box, r15; this
0x1800cec98  call    ?ReleaseAndReset@CValue@@QEAAXXZ; CValue::ReleaseAndReset(void)
0x1800cec9d  and     dword ptr [r15+8], 0FFFFFFC1h
0x1800ceca2  or      dword ptr [r15+8], 41h
0x1800ceca7  test    rsi, rsi
0x1800cecaa  jz      short loc_1800CECBB
0x1800cecac  mov     rax, [rsi]
0x1800cecaf  mov     box, rsi
0x1800cecb2  mov     rax, [rax+10h]
0x1800cecb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cecbb  xor     eax, eax
0x1800cecbd  mov     box, [rbp+47h+var_60]
0x1800cecc1  xor     box, rsp; StackCookie
0x1800cecc4  call    __security_check_cookie
0x1800cecc9  movaps  xmm6, [rsp+0E0h+var_58+8]
0x1800cecd1  add     rsp, 0A8h
0x1800cecd8  pop     r15
0x1800cecda  pop     r14
0x1800cecdc  pop     r13
0x1800cecde  pop     r12
0x1800cece0  pop     rdi
0x1800cece1  pop     rsi
0x1800cece2  pop     rbx
0x1800cece3  pop     rbp
0x1800cece4  retn
0x1800cece5  mov     eax, 121h
0x1800cecea  cmp     ecx, eax
0x1800cecec  ja      loc_1800CEEC3
0x1800cecf2  jz      loc_1800CFF66
0x1800cecf8  sub     ecx, 0D2h
0x1800cecfe  jz      loc_1800CFF42
0x1800ced04  sub     ecx, 14h; failedFrameHR
0x1800ced07  jz      loc_1800CF7B8
0x1800ced0d  sub     ecx, 0Ch
0x1800ced10  jz      loc_1800CFEB3
0x1800ced16  sub     ecx, 1; failedFrameHR
0x1800ced19  jz      loc_1800CF4CC
0x1800ced1f  sub     ecx, 14h; failedFrameHR
0x1800ced22  jz      loc_1800CF79F
0x1800ced28  cmp     ecx, 6
0x1800ced2b  jnz     loc_1800CEEF6
0x1800ced31  mov     [rbp+47h+cStowedExceptions], r12
0x1800ced35  test    rsi, rsi
0x1800ced38  jz      loc_1800CF02F
0x1800ced3e  mov     rax, [rsi]
0x1800ced41  lea     pSourceType, [rbp+47h+cStowedExceptions]
0x1800ced45  mov     box, rsi
0x1800ced48  mov     rax, [rax+98h]
0x1800ced4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ced54  mov     ebx, eax
0x1800ced56  test    eax, eax
0x1800ced58  js      loc_1800CF0CC
0x1800ced5e  mov     box, [rbp+47h+cStowedExceptions]; string
0x1800ced62  mov     rbx, qword ptr cs:?c_xencoded_string_ptr_null@xstring_ptr_constants@@2Uxencoded_string_ptr@@B.___u0; xencoded_string_ptr const xstring_ptr_constants::c_xencoded_string_ptr_null ...
0x1800ced69  test    box, box
0x1800ced6c  jz      loc_1800CF48F
0x1800ced72  xor     eax, eax
0x1800ced74  mov     [rbp+47h+bValue], rbx
0x1800ced78  lea     pSourceType, [rbp+47h+newString]; newString
0x1800ced7c  mov     [rbp+47h+newString], rax
0x1800ced80  mov     [rbp+47h+valueType], eax
0x1800ced83  call    cs:__imp_WindowsDuplicateString
0x1800ced89  mov     edi, eax
0x1800ced8b  test    eax, eax
0x1800ced8d  js      loc_1800CF688
0x1800ced93  mov     box, [rbp+47h+newString]; string
0x1800ced97  call    cs:__imp_WindowsGetStringLen
0x1800ced9d  mov     ecx, 3FFFFFFFh; failedFrameHR
0x1800ceda2  cmp     eax, ecx
0x1800ceda4  ja      loc_1800CFE57
0x1800cedaa  mov     rdi, [rbp+47h+newString]
0x1800cedae  and     eax, ecx
0x1800cedb0  mov     r12d, 1
0x1800cedb6  bts     eax, 1Fh
0x1800cedba  or      rdi, r12
0x1800cedbd  mov     [rbp+47h+valueType], eax
0x1800cedc0  mov     qword ptr [rbp+47h+rectValue.Width], rdi
0x1800cedc4  test    r12b, bl
0x1800cedc7  jnz     loc_1800CF0BA
0x1800cedcd  mov     ebx, [rbp+47h+rectValue.Height]
0x1800cedd0  mov     box, r15; this
0x1800cedd3  call    ?ReleaseAndReset@CValue@@QEAAXXZ; CValue::ReleaseAndReset(void)
0x1800cedd8  and     dword ptr [r15+8], 0FFFFFFCEh
0x1800ceddd  lea     box, [rbp+47h+bValue]; this
0x1800cede1  or      dword ptr [r15+8], 4Eh
0x1800cede6  mov     rax, qword ptr cs:?c_xencoded_string_ptr_null@xstring_ptr_constants@@2Uxencoded_string_ptr@@B.___u0; xencoded_string_ptr const xstring_ptr_constants::c_xencoded_string_ptr_null ...
0x1800ceded  mov     [rbp+47h+bValue], rax
0x1800cedf1  mov     [r15], edi
0x1800cedf4  mov     [r15+4], ebx
0x1800cedf8  call    ??1xstring_ptr@@QEAA@XZ; xstring_ptr::~xstring_ptr(void)
0x1800cedfd  mov     box, [rbp+47h+cStowedExceptions]; string
0x1800cee01  test    box, box
0x1800cee04  jz      short loc_1800CEE0C
0x1800cee06  call    cs:__imp_WindowsDeleteString
0x1800cee0c  test    r14, r14
0x1800cee0f  jz      loc_1800CECA7
0x1800cee15  mov     rax, [r14]
0x1800cee18  mov     box, r14
0x1800cee1b  mov     rax, [rax+10h]
0x1800cee1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cee24  jmp     loc_1800CECA7
0x1800cee29  jz      loc_1800CF6F3
0x1800cee2f  sub     ecx, 0Ah; failedFrameHR
0x1800cee32  jz      loc_1800CF788
0x1800cee38  sub     ecx, 10h
0x1800cee3b  jz      loc_1800CF923
0x1800cee41  sub     ecx, 10h; failedFrameHR
0x1800cee44  jz      loc_1800CF772
0x1800cee4a  sub     ecx, 1
0x1800cee4d  jz      loc_1800CF8B9
0x1800cee53  sub     ecx, 1Ch; failedFrameHR
0x1800cee56  jz      loc_1800CF399
0x1800cee5c  cmp     ecx, 1Ch
0x1800cee5f  jnz     loc_1800CEEF6
0x1800cee65  mov     byte ptr [rbp+47h+spValueAsInsp.ptr_], r12b
0x1800cee69  test    rsi, rsi
0x1800cee6c  jz      loc_1800CF4C2
0x1800cee72  mov     rax, [rsi]
0x1800cee75  lea     pSourceType, [rbp+47h+spValueAsInsp]
0x1800cee79  mov     box, rsi
0x1800cee7c  mov     rax, [rax+90h]
0x1800cee83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cee88  mov     ebx, eax
0x1800cee8a  test    eax, eax
0x1800cee8c  js      loc_1800CF86D
0x1800cee92  mov     dl, byte ptr [rbp+47h+spValueAsInsp.ptr_]; value
0x1800cee95  mov     box, r15; box
0x1800cee98  call    ?BoxValue@CValueBoxer@DirectUI@@SAJPEAVCValue@@EPEAVBoxerBuffer@2@@Z; DirectUI::CValueBoxer::BoxValue(CValue *,uchar,DirectUI::BoxerBuffer *)
0x1800cee9d  mov     ebx, eax
0x1800cee9f  test    eax, eax
0x1800ceea1  jns     loc_1800CEE0C
0x1800ceea7  mov     ecx, eax; failedFrameHR
0x1800ceea9  call    OnFailure_2990_
0x1800ceeae  test    r14, r14
0x1800ceeb1  jz      loc_1800CF125
0x1800ceeb7  mov     box, [r14]
0x1800ceeba  mov     rax, [box+10h]
0x1800ceebe  jmp     loc_1800CF11D
0x1800ceec3  sub     ecx, 124h
0x1800ceec9  jz      loc_1800CF375
0x1800ceecf  sub     ecx, 5; failedFrameHR
0x1800ceed2  jz      loc_1800CF5F3
0x1800ceed8  sub     ecx, 79h ; 'y'
0x1800ceedb  jz      loc_1800CF66A
0x1800ceee1  sub     ecx, 24h ; '$'
0x1800ceee4  jz      loc_1800CFFB5
0x1800ceeea  cmp     ecx, 0C3h
0x1800ceef0  jz      loc_1800CF5D2
0x1800ceef6  mov     [rbp+47h+bValue], r12
0x1800ceefa  mov     box, r12
0x1800ceefd  mov     [rbp+47h+cStowedExceptions], box
0x1800cef01  test    r14, r14
0x1800cef04  jz      short loc_1800CEF3F
0x1800cef06  mov     rax, [r14]
0x1800cef09  lea     value, [rbp+47h+cStowedExceptions]
0x1800cef0d  lea     pSourceType, _GUID_5c526665_f60e_4912_af59_5fe0680f089d
0x1800cef14  mov     box, r14
0x1800cef17  mov     r12d, 1
0x1800cef1d  mov     rax, [rax]
0x1800cef20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cef25  mov     box, [rbp+47h+cStowedExceptions]
0x1800cef29  test    eax, eax
0x1800cef2b  js      short loc_1800CEF3F
0x1800cef2d  test    byte ptr [box+46h], 2
0x1800cef31  jnz     short loc_1800CEF3F
0x1800cef33  cmp     [box+90h], rbx
0x1800cef3a  jz      short loc_1800CEF3F
  ... truncated ...
```
