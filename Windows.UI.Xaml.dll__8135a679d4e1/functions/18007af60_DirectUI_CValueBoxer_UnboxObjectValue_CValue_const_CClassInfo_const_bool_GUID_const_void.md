# DirectUI::CValueBoxer::UnboxObjectValue(CValue const *,CClassInfo const *,bool,_GUID const &,void * *)

- ea: `0x18007af60`
- end: `0x18007cea4`
- name: `?UnboxObjectValue@CValueBoxer@DirectUI@@SAJPEBVCValue@@PEBVCClassInfo@@_NAEBU_GUID@@PEAPEAX@Z`
- size: `8004`
- prototype: `HRESULT __fastcall(const CValue *box, const CClassInfo *pTargetType, bool targetTypeIsNullable, const _GUID *riid, void **value)`
- caller_count: `5`
- callee_count: `103`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18007af1c`
- `0x1800cd080`
- `0x1804df3ac`
- `0x18068a0b8`
- `0x1806abaac`

## callees

- `0x180004bc0`
- `0x180005374`
- `0x1800053b0`
- `0x180021840`
- `0x180040ce8`
- `0x18004bfd0`
- `0x180064694`
- `0x180065258`
- `0x18007a328`
- `0x18007a580`
- `0x18007af60`
- `0x18007d630`
- `0x1800ab600`
- `0x1800af8e0`
- `0x1800d4ad8`
- `0x1800d4ca4`
- `0x1800d5330`
- `0x1800e2378`
- `0x1800e252c`
- `0x1800fe130`
- `0x180100978`
- `0x18018fa14`
- `0x18018fa9c`
- `0x1801d6730`
- `0x1801e8e80`
- `0x1801e8efc`
- `0x1801e9130`
- `0x18024bdc0`
- `0x18024be20`
- `0x180253b04`
- `0x180254ef4`
- `0x1802a9250`
- `0x18031a1b4`
- `0x18037adfc`
- `0x18038f2f8`
- `0x180390304`
- `0x180421044`
- `0x1804210e4`
- `0x18045f190`
- `0x180460d90`
- `0x180460f68`
- `0x180461060`
- `0x1804613d0`
- `0x18046168c`
- `0x18046187c`
- `0x180461934`
- `0x18046d9c4`
- `0x18046fb8c`
- `0x1804732d8`
- `0x18047d504`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007b180`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007b180`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007b19e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007b19e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007bc3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007bc3a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18007b3de`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18007b3de`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x18007bcbf`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x18007bec1`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x18007bcbf`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x18007bec1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007ba25`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007c446`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007ba25`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007c446`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18007b652`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18007b652`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007c387`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007c387`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18007b580`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18007b580`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
__int64 __fastcall DirectUI::CValueBoxer::UnboxObjectValue(
        CValue *box,
        const CClassInfo *pTargetType,
        bool targetTypeIsNullable,
        const _GUID *riid,
        void **value)
{
  const _GUID *v5; // rsi
  unsigned int v8; // eax
  unsigned int v9; // r13d
  unsigned int v10; // eax
  MetaDataTypeInfoFlags *p_m_flags; // rcx
  const CClassInfo *BoxedType; // r15
  HRESULT KnownWinRTBoxFromEnumValue; // eax
  HRESULT v14; // r15d
  DirectUI::ValueTypeView<double> *v15; // r15
  KnownTypeIndex m_nIndex; // r15
  __int16 v17; // cx
  HSTRING__ *v18; // rsi
  unsigned __int16 v19; // ax
  int v20; // ebx
  CCustomClassInfo *Myval2; // rbx
  __int64 m_value; // rcx
  bool IsNull; // si
  DirectUI::ValueTypeView<double> *v24; // rcx
  HRESULT v26; // eax
  unsigned int v27; // ebx
  HRESULT v28; // ecx
  unsigned int v29; // eax
  Windows::Foundation::IPropertyValueStatics *PropertyValueStaticsNoRef; // rax
  HRESULT v31; // eax
  HRESULT v32; // eax
  char v33; // al
  DirectUI::DXamlCore *v34; // rbx
  HRESULT PeerPrivate; // eax
  DirectUI::ValueTypeView<double> *v36; // rcx
  long double M11; // rdi
  DirectUI::ValueTypeView<double> *v38; // rbx
  long double v39; // rsi
  DirectUI::DependencyObject *v40; // rdx
  DirectUI::ValueTypeView<double> *v41; // rcx
  unsigned int v42; // eax
  KnownTypeIndex v43; // cx
  unsigned int v44; // eax
  __int64 v45; // rcx
  int v46; // edx
  HSTRING StringRawBuffer; // rax
  UINT32 v48; // edx
  int String; // eax
  DirectUI::ValueTypeView<double> *v50; // rcx
  bool v51; // zf
  HRESULT v52; // eax
  HRESULT v53; // ecx
  HRESULT v54; // ecx
  unsigned int v55; // eax
  unsigned int v56; // ecx
  unsigned int v57; // ecx
  HRESULT v58; // eax
  const CClassInfo *v59; // rax
  unsigned int v60; // eax
  HRESULT v61; // eax
  DirectUI::ValueTypeViewBase<double> *v62; // rbx
  const long double *v63; // rax
  unsigned int v64; // r8d
  HRESULT v65; // eax
  DirectUI::ValueTypeView<double> *v66; // rbx
  const xstring_ptr_storage *v67; // rax
  DirectUI::ValueTypeView<double> *v68; // rcx
  HRESULT v69; // eax
  const xstring_ptr_storage **v70; // rbx
  HSTRING v71; // rbx
  Windows::Foundation::IPropertyValueStatics *v72; // rax
  HRESULT v73; // eax
  unsigned int v74; // edi
  Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo> *m_ptr; // rbx
  DirectUI::ValueTypeView<double> *v76; // rax
  HRESULT v77; // eax
  long double v78; // rbx
  DirectUI::ValueTypeView<double> *v79; // rcx
  unsigned int Storage; // r15d
  DirectUI::ValueTypeView<double> *v81; // rcx
  DirectUI::ValueTypeView<double> *v82; // rcx
  HRESULT v83; // ecx
  DirectUI::ValueTypeView<double> *v84; // rcx
  HRESULT v85; // eax
  __int64 v86; // rcx
  DirectUI::ValueTypeView<double> *v87; // rcx
  HRESULT v88; // eax
  DirectUI::ValueTypeView<double> *v89; // rcx
  char *v90; // rcx
  unsigned __int64 v91; // rcx
  HRESULT v92; // eax
  DirectUI::ValueTypeView<double> *ptr; // rcx
  CDependencyObject *v94; // rax
  CString *v95; // rax
  HRESULT v96; // eax
  HRESULT v97; // eax
  unsigned int v98; // eax
  unsigned int v99; // eax
  unsigned int v100; // eax
  DirectUI::ValueTypeView<double> *v101; // rcx
  DirectUI::ValueTypeView<double> *v102; // rcx
  xencoded_string_ptr v103; // rax
  const wchar_t *BufferAndCount; // rax
  HRESULT v105; // eax
  HRESULT v106; // r15d
  HRESULT v107; // ecx
  const xstring_ptr_storage *v108; // rbx
  HRESULT v109; // eax
  DirectUI::ValueTypeViewBase<int> *v110; // rbx
  const int *v111; // rax
  unsigned int v112; // r8d
  Windows::UI::Xaml::Input::IPointerEventHandler *v113; // rdx
  const CDependencyObject *v114; // rax
  CDependencyObject *v115; // rax
  CDependencyObject *v116; // rbx
  Windows::UI::Xaml::Documents::TextRange v117; // rcx
  const CClassInfo *ClassInfoByIndex; // rax
  HRESULT v119; // eax
  CThemeResource *v120; // rax
  KnownTypeIndex v121; // [rsp+28h] [rbp-E0h]
  unsigned int v122; // [rsp+38h] [rbp-D0h]
  ctl::ComPtr<DirectUI::ValueTypeView<double> > spDoubleVTV; // [rsp+58h] [rbp-B0h] BYREF
  xruntime_string_ptr pstrPromoted; // [rsp+60h] [rbp-A8h] BYREF
  Windows::UI::Color v125[2]; // [rsp+68h] [rbp-A0h] BYREF
  Windows::UI::Xaml::Documents::TextRange rawValue; // [rsp+70h] [rbp-98h]
  Windows::UI::Xaml::Interop::TypeName v127; // [rsp+78h] [rbp-90h] BYREF
  __int128 v128; // [rsp+88h] [rbp-80h]
  __int128 v129; // [rsp+98h] [rbp-70h] OVERLAPPED
  Windows::UI::Xaml::Media::Matrix v130; // [rsp+A8h] [rbp-60h] BYREF
  Windows::UI::Xaml::Media::Media3D::Matrix3D v131; // [rsp+D8h] [rbp-30h] BYREF
  Windows::UI::Xaml::Media::Media3D::Matrix3D v132; // [rsp+158h] [rbp+50h] BYREF

  rawValue = (Windows::UI::Xaml::Documents::TextRange)riid;
  v5 = riid;
  if ( !box )
  {
    OnNewFailure_1172_(0);
    return 2147500035LL;
  }
  if ( !value )
  {
    OnNewFailure_1172_((HRESULT)box);
    return 2147500035LL;
  }
  spDoubleVTV.ptr_ = 0;
  if ( targetTypeIsNullable )
  {
    v8 = box->m_flags.m_state.m_asOne & 0x3F;
    if ( v8 )
    {
      if ( v8 != 1 )
      {
        v9 = -2147418113;
        switch ( v8 )
        {
          case 2u:
          case 3u:
          case 4u:
          case 5u:
          case 6u:
          case 7u:
          case 8u:
          case 9u:
          case 0xFu:
          case 0x16u:
          case 0x17u:
          case 0x20u:
          case 0x21u:
            goto $LN1988;
          case 0xAu:
          case 0xBu:
          case 0xCu:
          case 0xDu:
          case 0x10u:
          case 0x11u:
          case 0x12u:
          case 0x13u:
          case 0x14u:
          case 0x15u:
          case 0x18u:
          case 0x19u:
          case 0x1Au:
          case 0x1Bu:
          case 0x1Du:
          case 0x1Eu:
          case 0x1Fu:
            v51 = *(_QWORD *)&box->m_value == 0;
            goto LABEL_115;
          case 0xEu:
            m_value = (__int64)box->m_value;
            if ( (m_value & 1) != 0 )
            {
              if ( WindowsDuplicateString((HSTRING)(m_value & 0xFFFFFFFFFFFFFFFEuLL), &v127.Name) < 0 )
              {
                v130.M11 = 0.0;
                v125[0] = 0;
                TraceForFailFast(-2147418113);
                OnNewFailureEncountered(-2147418113, 0, 0);
                GetStowedExceptionsForFailFast((_STOWED_EXCEPTION_INFORMATION_V2 ***)&v130, (unsigned int *)&v125[0].A);
                RoFailFastWithErrorContextInternal2(
                  -2147418113,
                  *(_DWORD *)v125,
                  *(struct _STOWED_EXCEPTION_INFORMATION_V2 **const *)&v130.M11);
              }
              m_value = (__int64)v127.Name | 1;
            }
            *(_QWORD *)&v130.M11 = m_value;
            IsNull = xencoded_string_ptr::IsNull((xencoded_string_ptr *)&v130);
            xstring_ptr::~xstring_ptr((xstring_ptr *)&v130);
            goto LABEL_42;
          case 0x1Cu:
            v51 = box->m_value.m_typeHandle == UnknownType;
LABEL_115:
            IsNull = v51;
LABEL_42:
            v51 = !IsNull;
            v5 = (const _GUID *)rawValue;
            if ( !v51 )
              goto LABEL_43;
            goto $LN1988;
          default:
            v130.M11 = 0.0;
            v125[0] = 0;
            TraceForFailFast(-2147418113);
            OnNewFailureEncountered(-2147418113, 0, 0);
            GetStowedExceptionsForFailFast((_STOWED_EXCEPTION_INFORMATION_V2 ***)&v130, (unsigned int *)&v125[0].A);
            RoFailFastWithErrorContextInternal2(
              -2147418113,
              *(_DWORD *)v125,
              *(struct _STOWED_EXCEPTION_INFORMATION_V2 **const *)&v130.M11);
            goto $LN1988;
        }
      }
      goto LABEL_44;
    }
  }
  v9 = -2147418113;
$LN1988:
  v10 = box->m_flags.m_state.m_asOne & 0x3F;
  if ( v10 == 27 )
  {
    v15 = (DirectUI::ValueTypeView<double> *)box->m_value;
    if ( spDoubleVTV.ptr_ != *(DirectUI::ValueTypeView<double> **)&box->m_value )
    {
      if ( v15 )
        v15->AddRef(*(IUnknown **)&box->m_value);
      spDoubleVTV.ptr_ = v15;
    }
    goto LABEL_20;
  }
  if ( !pTargetType )
    goto LABEL_20;
  p_m_flags = &pTargetType->m_flags;
  if ( (pTargetType->m_nIndex == Enumerated || (*p_m_flags & 0x800) != 0) && (v10 == 33 || v10 == 14 || v10 == 3) )
  {
    Storage = 0;
    LODWORD(pstrPromoted.m_encodedStorage.Storage) = 0;
    if ( v10 == 33 )
    {
      Storage = box->m_value.m_enum8.m_value;
      HIWORD(v127.Name) = 0;
      goto LABEL_173;
    }
    v98 = v10 - 1;
    if ( v98 )
    {
      v99 = v98 - 2;
      if ( v99 )
      {
        v100 = v99 - 1;
        if ( v100 )
        {
          if ( v100 != 10 )
          {
            OnFailure_3652_((HRESULT)p_m_flags);
LABEL_268:
            OnFailure_2990_(v9);
LABEL_226:
            ptr = spDoubleVTV.ptr_;
            if ( spDoubleVTV.ptr_ )
            {
LABEL_227:
              spDoubleVTV.ptr_ = 0;
              ptr->Release(ptr);
              return v9;
            }
            return v9;
          }
          v125[0] = 0;
          v103.Storage = CValue::AsEncodedString(box).Storage;
          BufferAndCount = xencoded_string_ptr::GetBufferAndCount(
                             (xencoded_string_ptr *)v103.Storage,
                             (unsigned int *)&v125[0].A);
          v105 = DirectUI::CValueBoxer::ResolveEnumValueFromString(
                   BufferAndCount,
                   *(_DWORD *)v125,
                   pTargetType,
                   (unsigned int *)&pstrPromoted);
          v106 = v105;
          if ( v105 < 0 )
          {
            OnFailure_2990_(v105);
            v9 = v106;
            goto LABEL_268;
          }
          Storage = (unsigned int)pstrPromoted.m_encodedStorage.Storage;
        }
        else
        {
          Storage = box->m_value.m_any[0];
        }
      }
      else
      {
        Storage = box->m_value.m_any[0];
      }
    }
LABEL_173:
    ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spDoubleVTV);
    KnownWinRTBoxFromEnumValue = GetKnownWinRTBoxFromEnumValue(Storage, pTargetType, &spDoubleVTV.ptr_);
    v14 = KnownWinRTBoxFromEnumValue;
    if ( KnownWinRTBoxFromEnumValue < 0 )
    {
LABEL_174:
      OnFailure_2990_(KnownWinRTBoxFromEnumValue);
LABEL_175:
      v81 = spDoubleVTV.ptr_;
      if ( spDoubleVTV.ptr_ )
      {
        spDoubleVTV.ptr_ = 0;
        v81->Release(v81);
      }
      return (unsigned int)v14;
    }
    goto LABEL_20;
  }
  if ( (*p_m_flags & 0x1000) != 0 )
  {
    if ( (*p_m_flags & 0x100) != 0 && v10 == 14 )
    {
      ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spDoubleVTV);
      CValue::As<14>(box, (xstring_ptr *)&v130);
      v14 = DirectUI::ActivationAPI::ActivateInstanceFromString(
              pTargetType,
              (const xstring_ptr_view *)&v130,
              &spDoubleVTV.ptr_);
      xstring_ptr::~xstring_ptr((xstring_ptr *)&v130);
      if ( v14 < 0 )
      {
        OnFailure_2990_(v14);
        goto LABEL_175;
      }
    }
    else
    {
      BoxedType = DirectUI::MetadataAPI::TryGetBoxedType(pTargetType);
      if ( BoxedType )
      {
        ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spDoubleVTV);
        KnownWinRTBoxFromEnumValue = DirectUI::CValueBoxer::UnboxObjectValue(box, BoxedType, &spDoubleVTV.ptr_);
        v14 = KnownWinRTBoxFromEnumValue;
        if ( KnownWinRTBoxFromEnumValue < 0 )
          goto LABEL_174;
      }
    }
  }
LABEL_20:
  if ( spDoubleVTV.ptr_ )
    goto LABEL_43;
  if ( (box->m_flags.m_state.m_asOne & 0x3F) == 0 )
    goto LABEL_44;
  m_nIndex = ThemeResource;
  v17 = 40;
  if ( (box->m_flags.m_state.m_asOne & 0x3F) == 0x18 )
  {
    v18 = (HSTRING__ *)box->m_value;
    if ( box->m_value )
    {
      v17 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v18 + 600LL))(*(_QWORD *)&box->m_value);
      if ( v17 == 152 || v17 == 528 )
      {
        m_nIndex = v17;
        goto LABEL_27;
      }
      if ( v17 == 149 )
      {
        m_nIndex = *((_WORD *)v18 + 50);
        goto LABEL_27;
      }
    }
  }
  else
  {
    v18 = 0;
  }
  if ( (*(_BYTE *)&box->m_flags.m_state.0 & 0x3F) == 0x1D )
    goto LABEL_28;
  m_nIndex = Object;
  if ( !pTargetType )
    goto LABEL_84;
  m_nIndex = pTargetType->m_nIndex;
LABEL_27:
  if ( m_nIndex != Object )
    goto LABEL_28;
LABEL_84:
  if ( v18 )
  {
    m_nIndex = v17;
    goto LABEL_28;
  }
  if ( !CValue::IsNull(box) )
  {
    v42 = box->m_flags.m_state.m_asOne & 0x3F;
    switch ( v42 )
    {
      case 0xEu:
        v43 = String;
        break;
      case 9u:
LABEL_100:
        v43 = Double;
        break;
      case 0x13u:
        v43 = Thickness;
        break;
      default:
        switch ( v42 )
        {
          case 2u:
            v43 = Boolean;
            goto LABEL_135;
          case 3u:
          case 0x21u:
            *(_WORD *)&v125[0].A = 0;
            CValue::GetEnum(box, (unsigned int *)&pstrPromoted, (KnownTypeIndex *)v125);
            v43 = *(_WORD *)&v125[0].A;
            if ( !*(_WORD *)&v125[0].A )
              goto LABEL_307;
            goto LABEL_135;
          case 4u:
LABEL_307:
            v43 = Int32;
            goto LABEL_135;
          case 6u:
            v43 = Int64;
            goto LABEL_135;
          case 8u:
            goto LABEL_100;
          case 0xBu:
            if ( CValue::GetArrayElementCount(box) == 6 )
            {
              v43 = Matrix;
            }
            else
            {
              if ( CValue::GetArrayElementCount(box) != 16 )
              {
                OnFailure_977_(v107);
                OnFailure_2990_(-2147467259);
                v101 = spDoubleVTV.ptr_;
                if ( spDoubleVTV.ptr_ )
                {
                  spDoubleVTV.ptr_ = 0;
                  v101->Release(v101);
                }
                return 2147500037LL;
              }
              v43 = Matrix3D;
            }
            break;
          case 0xFu:
            v43 = Color;
            goto LABEL_135;
          case 0x10u:
            v43 = Point;
            goto LABEL_135;
          case 0x11u:
            v43 = Size;
            goto LABEL_135;
          case 0x12u:
            v43 = Rect;
            goto LABEL_135;
          case 0x14u:
            v43 = GridLength;
            goto LABEL_135;
          case 0x15u:
            v43 = CornerRadius;
            goto LABEL_135;
          case 0x16u:
            v43 = DateTime;
            goto LABEL_135;
          case 0x17u:
            v43 = TimeSpan;
            goto LABEL_135;
          default:
            *(double *)&pstrPromoted.m_encodedStorage.Storage = 0.0;
            goto LABEL_137;
        }
        break;
    }
LABEL_135:
    *(double *)&v59 = COERCE_DOUBLE(DirectUI::MetadataAPI::GetClassInfoByIndex(v43));
    pstrPromoted.m_encodedStorage.Storage = (const xstring_ptr_storage *)v59;
    if ( *(double *)&v59 != 0.0 )
      m_nIndex = v59->m_nIndex;
LABEL_137:
    v60 = box->m_flags.m_state.m_asOne & 0x3F;
    if ( (v60 == 33 || v60 == 3) && (m_nIndex != FontWeight || !pTargetType || pTargetType->m_nIndex != FontWeight) )
    {
      v108 = pstrPromoted.m_encodedStorage.Storage;
      v125[0] = 0;
      v109 = DirectUI::CValueBoxer::UnboxEnumValue(
               box,
               (const CClassInfo *)pstrPromoted.m_encodedStorage.Storage,
               (unsigned int *)&v125[0].A);
      LODWORD(pstrPromoted.m_encodedStorage.Storage) = v109;
      if ( v109 < 0 )
      {
        OnFailure_2990_(v109);
        ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spDoubleVTV);
        return LODWORD(pstrPromoted.m_encodedStorage.RuntimeStringHandleMarker);
      }
      if ( LOWORD(v108->Buffer) == 187 || LOWORD(v108->Buffer) == 159 )
      {
        ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spDoubleVTV);
        v26 = DirectUI::PropertyValue::CreateFromInt32(*(_DWORD *)v125, &spDoubleVTV.ptr_);
        v27 = v26;
        if ( v26 < 0 )
          goto LABEL_48;
      }
      else
      {
        ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spDoubleVTV);
        v26 = GetKnownWinRTBoxFromEnumValue(*(_DWORD *)v125, (const CClassInfo *)v108, &spDoubleVTV.ptr_);
        v27 = v26;
        if ( v26 < 0 )
          goto LABEL_48;
      }
      goto LABEL_28;
    }
    if ( v60 == 10 )
    {
      *(double *)&pstrPromoted.m_encodedStorage.Storage = 0.0;
      v61 = ctl::make<DirectUI::ValueTypeView<int>>((ctl::Internal::ComPtrRef<ctl::ComPtr<DirectUI::ValueTypeView<int> > >)&pstrPromoted);
      v27 = v61;
      if ( v61 >= 0 )
      {
        v110 = (DirectUI::ValueTypeViewBase<int> *)pstrPromoted.m_encodedStorage.Storage;
        CValue::GetArrayElementCount(box);
        v111 = CValue::As<10>(box);
        v65 = DirectUI::ValueTypeViewBase<int>::SetView(v110, v111, v112);
        v27 = v65;
        if ( v65 >= 0 )
        {
          v113 = (Windows::UI::Xaml::Input::IPointerEventHandler *)pstrPromoted.m_encodedStorage.Storage;
          *(double *)&pstrPromoted.m_encodedStorage.Storage = 0.0;
          ctl::ComPtr<Windows::UI::Xaml::Input::IPointerEventHandler>::Attach(
            (ctl::ComPtr<Windows::UI::Xaml::Input::IPointerEventHandler> *)&spDoubleVTV,
            v113);
          ctl::ComPtr<DirectUI::WebViewUnviewableContentIdentifiedEventArgs>::InternalRelease((ctl::ComPtr<DirectUI::CEventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Xaml::Hosting::DesktopWindowXamlSource *,Windows::UI::Xaml::Hosting::DesktopWindowXamlSourceTakeFocusRequestedEventArgs *>,Windows::UI::Xaml::Hosting::IDesktopWindowXamlSource,Windows::UI::Xaml::Hosting::IDesktopWindowXamlSourceTakeFocusRequestedEventArgs> > *)&pstrPromoted);
          goto LABEL_28;
        }
        goto LABEL_329;
      }
    }
    else
    {
      if ( v60 != 12 )
        goto LABEL_28;
      *(double *)&pstrPromoted.m_encodedStorage.Storage = 0.0;
      v61 = ctl::make<DirectUI::ValueTypeView<double>>((ctl::Internal::ComPtrRef<ctl::ComPtr<DirectUI::ValueTypeView<double> > >)&pstrPromoted);
      v27 = v61;
      if ( v61 >= 0 )
      {
        v62 = (DirectUI::ValueTypeViewBase<double> *)pstrPromoted.m_encodedStorage.Storage;
        CValue::GetArrayElementCount(box);
        v63 = CValue::As<12>(box);
        v65 = DirectUI::ValueTypeViewBase<double>::SetView(v62, v63, v64);
        v27 = v65;
        if ( v65 >= 0 )
        {
          v66 = (DirectUI::ValueTypeView<double> *)pstrPromoted.m_encodedStorage.Storage;
          v67 = 0;
          v68 = spDoubleVTV.ptr_;
          *(double *)&pstrPromoted.m_encodedStorage.Storage = 0.0;
          if ( spDoubleVTV.ptr_ != v66 )
          {
            if ( spDoubleVTV.ptr_ )
            {
              spDoubleVTV.ptr_ = 0;
              v68->Release(v68);
              v67 = pstrPromoted.m_encodedStorage.Storage;
            }
            spDoubleVTV.ptr_ = v66;
          }
          if ( v67 )
          {
            *(double *)&pstrPromoted.m_encodedStorage.Storage = 0.0;
            (*(void (__fastcall ***)(__int64))((char *)&v67[1].Handle + 4))[2]((__int64)&v67[1].Handle + 4);
          }
          goto LABEL_28;
        }
LABEL_329:
        OnFailure_2990_(v65);
        ctl::ComPtr<DirectUI::WebViewUnviewableContentIdentifiedEventArgs>::InternalRelease((ctl::ComPtr<DirectUI::CEventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Xaml::Hosting::DesktopWindowXamlSource *,Windows::UI::Xaml::Hosting::DesktopWindowXamlSourceTakeFocusRequestedEventArgs *>,Windows::UI::Xaml::Hosting::IDesktopWindowXamlSource,Windows::UI::Xaml::Hosting::IDesktopWindowXamlSourceTakeFocusRequestedEventArgs> > *)&pstrPromoted);
        goto LABEL_49;
      }
    }
    OnFailure_2990_(v61);
    if ( *(double *)&pstrPromoted.m_encodedStorage.Storage != 0.0 )
    {
      v90 = (char *)&pstrPromoted.m_encodedStorage.Storage[1].Handle + 4;
      *(double *)&pstrPromoted.m_encodedStorage.Storage = 0.0;
      (*(void (__fastcall **)(char *))(*(_QWORD *)v90 + 16LL))(v90);
    }
    goto LABEL_195;
  }
LABEL_28:
  if ( spDoubleVTV.ptr_ )
    goto LABEL_55;
  if ( (unsigned __int16)m_nIndex > String )
  {
    if ( (unsigned __int16)m_nIndex <= Duration )
    {
      switch ( m_nIndex )
      {
        case Duration:
          v127 = 0;
          v26 = DirectUI::CValueBoxer::UnboxValue(box, (Windows::UI::Xaml::Duration *)&v127);
          v27 = v26;
          if ( v26 < 0 )
            goto LABEL_48;
          ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spDoubleVTV);
          v97 = DirectUI::PropertyValue::CreateReference<Windows::UI::Xaml::Duration>(
                  (Windows::UI::Xaml::Duration *)&v127,
                  &spDoubleVTV.ptr_);
          v27 = v97;
          if ( v97 < 0 )
          {
            OnFailure_2990_(v97);
            v89 = spDoubleVTV.ptr_;
            if ( spDoubleVTV.ptr_ )
              goto LABEL_211;
            return v27;
          }
          goto LABEL_55;
        case TextRange:
          v26 = DirectUI::CValueBoxer::UnboxValue(box, (Windows::UI::Xaml::Documents::TextRange *)&v127);
          v27 = v26;
          if ( v26 < 0 )
            goto LABEL_48;
          ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spDoubleVTV);
          v26 = DirectUI::PropertyValue::CreateFromTextRange(v117, &spDoubleVTV.ptr_);
          v27 = v26;
          if ( v26 < 0 )
            goto LABEL_48;
          goto LABEL_55;
        case Thickness:
          v127 = 0;
          v128 = 0;
          v32 = DirectUI::CValueBoxer::UnboxValue(box, (Windows::UI::Xaml::Thickness *)&v127);
          v27 = v32;
          if ( v32 >= 0 )
          {
            ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spDoubleVTV);
            v130.M11 = 0.0;
            v52 = DirectUI::PropertyValue::CreateTypedReference<Windows::UI::Xaml::Thickness>(
                    (Windows::UI::Xaml::Thickness *)&v127,
                    (Windows::Foundation::IReference<Windows::UI::Xaml::Thickness> **)&v130);
            v27 = v52;
            if ( v52 >= 0 )
            {
              v5 = (const _GUID *)rawValue;
              spDoubleVTV.ptr_ = *(DirectUI::ValueTypeView<double> **)&v130.M11;
              goto LABEL_43;
            }
            OnFailure_2990_(v52);
            if ( *(_QWORD *)&v130.M11 )
              (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v130.M11 + 16LL))(*(_QWORD *)&v130.M11);
LABEL_256:
            OnFailure_2990_(v27);
LABEL_198:
            v84 = spDoubleVTV.ptr_;
            if ( !spDoubleVTV.ptr_ )
              return v27;
            spDoubleVTV.ptr_ = 0;
LABEL_200:
            v84->Release(v84);
            return v27;
          }
          goto LABEL_194;
        case TimeSpan:
          v127.Name = 0;
          v32 = DirectUI::CValueBoxer::UnboxValue(box, (Windows::Foundation::TimeSpan *)&v127);
          v27 = v32;
          if ( v32 < 0 )
            goto LABEL_194;
          ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spDoubleVTV);
          v88 = DirectUI::PropertyValue::CreateFromTimeSpan((Windows::Foundation::TimeSpan)v127.Name, &spDoubleVTV.ptr_);
          v27 = v88;
          if ( v88 < 0 )
          {
LABEL_209:
            OnFailure_2990_(v88);
            goto LABEL_210;
          }
          goto LABEL_55;
      }
    }
    else
    {
      switch ( m_nIndex )
      {
        case KeyTime:
          v127.Name = 0;
          v26 = DirectUI::CValueBoxer::UnboxValue(box, (Windows::UI::Xaml::Media::Animation::KeyTime *)&v127);
          v27 = v26;
          if ( v26 < 0 )
            goto LABEL_48;
          ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spDoubleVTV);
          v26 = DirectUI::PropertyValue::CreateReference<Windows::UI::Xaml::Media::Animation::KeyTime>(
                  (Windows::UI::Xaml::Media::Animation::KeyTime)v127.Name,
                  &spDoubleVTV.ptr_);
          v27 = v26;
          if ( v26 < 0 )
            goto LABEL_48;
          goto LABEL_55;
        case ThemeResource:
          *(double *)&pstrPromoted.m_encodedStorage.Storage = 0.0;
          if ( v18 )
          {
            v127.Name = v18;
            make_xref<CThemeResource,CThemeResourceExtension *>(
              (xref_ptr<CThemeResource> *)&v130,
              (CThemeResourceExtension **)&v127);
            v119 = DirectUI::ThemeResourceExpression::Create(
                     *(CThemeResource **)&v130.M11,
                     (DirectUI::ThemeResourceExpression **)&pstrPromoted);
            v27 = v119;
            if ( v119 < 0 )
            {
              OnFailure_2990_(v119);
              xref_ptr<CThemeResource>::DecrementRefCount((xref_ptr<CThemeResource> *)&v130);
              goto LABEL_49;
            }
            xref_ptr<CThemeResource>::DecrementRefCount((xref_ptr<CThemeResource> *)&v130);
          }
          else
          {
            v120 = CValue::As<29>(box);
            v26 = DirectUI::ThemeResourceExpression::Create(v120, (DirectUI::ThemeResourceExpression **)&pstrPromoted);
            v27 = v26;
            if ( v26 < 0 )
              goto LABEL_48;
          }
          ctl::ComPtr<Windows::UI::Xaml::Input::IPointerEventHandler>::Attach(
            (ctl::ComPtr<Windows::UI::Xaml::Input::IPointerEventHandler> *)&spDoubleVTV,
            (Windows::UI::Xaml::Input::IPointerEventHandler *)pstrPromoted.m_encodedStorage.Storage);
          v5 = (const _GUID *)rawValue;
          goto LABEL_43;
        case RepeatBehavior:
          v127 = 0;
          *(_QWORD *)&v128 = 0;
          v32 = DirectUI::CValueBoxer::UnboxValue(box, (Windows::UI::Xaml::Media::Animation::RepeatBehavior *)&v127);
          v27 = v32;
          if ( v32 < 0 )
          {
LABEL_194:
            OnFailure_2990_(v32);
LABEL_195:
            v84 = spDoubleVTV.ptr_;
            if ( !spDoubleVTV.ptr_ )
              return v27;
            spDoubleVTV.ptr_ = 0;
            goto LABEL_200;
          }
          ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spDoubleVTV);
          *(Windows::UI::Xaml::Interop::TypeName *)&v130.M11 = v127;
          *(_QWORD *)&v130.M21 = v128;
          v26 = DirectUI::PropertyValue::CreateReference<Windows::UI::Xaml::Media::Animation::RepeatBehavior>(
                  (Windows::UI::Xaml::Media::Animation::RepeatBehavior *)&v130,
                  &spDoubleVTV.ptr_);
          v27 = v26;
          if ( v26 < 0 )
          {
LABEL_48:
            OnFailure_2990_(v26);
LABEL_49:
            ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spDoubleVTV);
            return v27;
          }
LABEL_55:
          v5 = (const _GUID *)rawValue;
          goto LABEL_43;
      }
    }
LABEL_32:
    if ( v18 )
    {
      v19 = (*(__int64 (__fastcall **)(HSTRING__ *))(*(_QWORD *)v18 + 600LL))(v18);
      v20 = v19;
      if ( v19 == 149 )
        goto LABEL_378;
      if ( v19 >= 0x43Cu )
      {
        EnterCriticalSection(&g_csStatic);
        Myval2 = DirectUI::DynamicMetadataStorage::GetInstance()->m_customTypesCache._Mypair._Myval2._Myfirst[v20 - 1084]._Mypair._Myval2;
        LeaveCriticalSection(&g_csStatic);
        while ( Myval2->m_nIndex )
        {
          if ( Myval2->m_nIndex == Enumerated )
          {
            v33 = 1;
            goto LABEL_65;
          }
          Myval2 = (CCustomClassInfo *)DirectUI::MetadataAPI::GetClassInfoByIndex(Myval2->m_nBaseTypeIndex);
        }
        v33 = 0;
LABEL_65:
        if ( v33 )
        {
LABEL_378:
          ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spDoubleVTV);
          ClassInfoByIndex = DirectUI::MetadataAPI::GetClassInfoByIndex((KnownTypeIndex)*((_WORD *)v18 + 50));
          v26 = GetKnownWinRTBoxFromEnumValue(*((_DWORD *)v18 + 24), ClassInfoByIndex, &spDoubleVTV.ptr_);
          v27 = v26;
          if ( v26 < 0 )
            goto LABEL_48;
          goto LABEL_55;
        }
      }
      v130.M11 = 0.0;
      if ( DXamlInstanceStorage::g_dwTlsIndex == -1 )
      {
        v34 = 0;
        OnNewFailure_2955_(-1);
      }
      else
      {
        v34 = (DirectUI::DXamlCore *)TlsGetValue(DXamlInstanceStorage::g_dwTlsIndex);
        if ( !v34 && GetLastError() )
          OnFailure_977_(v83);
      }
      (*(void (__fastcall **)(HSTRING__ *))(*(_QWORD *)v18 + 600LL))(v18);
      PeerPrivate = DirectUI::DXamlCore::GetPeerPrivate(
                      v34,
                      0,
                      (CDependencyObject *)v18,
                      CreateIfNecessary,
                      v121,
                      0,
                      v122,
                      0,
                      (DirectUI::DependencyObject **)&v130);
      v27 = PeerPrivate;
      if ( PeerPrivate >= 0 )
      {
        v36 = spDoubleVTV.ptr_;
        if ( spDoubleVTV.ptr_ )
        {
          spDoubleVTV.ptr_ = 0;
          v36->Release(v36);
        }
        M11 = v130.M11;
        if ( *(_QWORD *)&v130.M11 )
        {
          v38 = (DirectUI::ValueTypeView<double> *)(*(_QWORD *)&v130.M11 + 8LL);
          v130.M11 = 0.0;
          if ( M11 != NAN
            && v38->QueryInterface(
                 (IUnknown *)(*(_QWORD *)&M11 + 8LL),
                 &GUID_7906a7a5_3434_4475_9d64_cd8acec0e3ea,
                 (void **)&v130) >= 0 )
          {
            v39 = v130.M11;
            if ( *(_QWORD *)&v130.M11 )
            {
              v40 = *(DirectUI::DependencyObject **)(*(_QWORD *)&v130.M11 + 32LL);
              if ( !v40 )
              {
                v41 = *(DirectUI::ValueTypeView<double> **)(*(_QWORD *)&v130.M11 + 8LL);
                spDoubleVTV.ptr_ = v41;
                if ( v41 )
                  v41->AddRef(v41);
                goto LABEL_78;
              }
              v85 = ctl::do_query_interface<IInspectable,DirectUI::DependencyObject>(&spDoubleVTV.ptr_, v40);
              v27 = v85;
              if ( v85 >= 0 )
              {
LABEL_78:
                (*(void (__fastcall **)(long double))(**(_QWORD **)&v39 + 16LL))(COERCE_LONG_DOUBLE(*(_QWORD *)&v39));
                goto LABEL_82;
              }
              OnFailure_2990_(v85);
              (*(void (__fastcall **)(long double))(**(_QWORD **)&v39 + 16LL))(COERCE_LONG_DOUBLE(*(_QWORD *)&v39));
              OnFailure_2990_(v27);
              v86 = *(_QWORD *)&M11 + 8LL;
              goto LABEL_203;
            }
          }
        }
        else
        {
          v38 = 0;
        }
        spDoubleVTV.ptr_ = v38;
        if ( v38 )
          v38->AddRef(v38);
LABEL_82:
        if ( M11 == 0.0 )
        {
LABEL_188:
          v5 = (const _GUID *)rawValue;
        }
        else
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)&M11 + 8LL) + 16LL))(*(_QWORD *)&M11 + 8LL);
          v5 = (const _GUID *)rawValue;
        }
LABEL_43:
        if ( spDoubleVTV.ptr_ )
        {
          v26 = spDoubleVTV.ptr_->QueryInterface(spDoubleVTV.ptr_, v5, value);
          v27 = v26;
          if ( v26 < 0 )
            goto LABEL_48;
        }
        goto LABEL_44;
      }
      OnFailure_2990_(PeerPrivate);
      if ( !*(_QWORD *)&v130.M11 )
      {
LABEL_204:
        v87 = spDoubleVTV.ptr_;
        if ( spDoubleVTV.ptr_ )
        {
          spDoubleVTV.ptr_ = 0;
          v87->Release(v87);
        }
        return v27;
      }
      v86 = *(_QWORD *)&v130.M11 + 8LL;
LABEL_203:
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v86 + 16LL))(v86);
      goto LABEL_204;
    }
LABEL_44:
    v24 = spDoubleVTV.ptr_;
    if ( spDoubleVTV.ptr_ )
    {
      spDoubleVTV.ptr_ = 0;
      v24->Release(v24);
    }
    return 0;
  }
  if ( m_nIndex != String )
  {
    switch ( m_nIndex )
    {
      case DateTime:
        v130.M11 = 0.0;
        v26 = DirectUI::CValueBoxer::UnboxValue(box, (Windows::Foundation::DateTime *)&v130);
        v27 = v26;
        if ( v26 < 0 )
          goto LABEL_48;
        ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spDoubleVTV);
        v26 = DirectUI::PropertyValue::CreateFromDateTime(
                *(Windows::Foundation::DateTime *)&v130.M11,
                &spDoubleVTV.ptr_);
        v27 = v26;
        if ( v26 < 0 )
          goto LABEL_48;
        goto LABEL_55;
      case Int64:
        v130.M11 = 0.0;
        v32 = DirectUI::CValueBoxer::UnboxValueHelper<__int64>(
                box,
                lambda_5235ceedeaf41f5407e50c2f3d7dddfe_::_lambda_invoker_cdecl_,
                (HRESULT (__fastcall *)(const CDependencyObject *, __int64 *))DirectUI::Selection::InternalSelectedItemsStorage::SetAt,
                (__int64 *)&v130);
        v27 = v32;
        if ( v32 < 0 )
          goto LABEL_194;
        ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spDoubleVTV);
        v88 = DirectUI::PropertyValue::CreateFromInt64(*(__int64 *)&v130.M11, &spDoubleVTV.ptr_);
        v27 = v88;
        if ( v88 < 0 )
          goto LABEL_209;
        goto LABEL_55;
      case Float:
        LODWORD(pstrPromoted.m_encodedStorage.Storage) = 0;
        v26 = DirectUI::CValueBoxer::UnboxValue(box, (float *)&pstrPromoted);
        v27 = v26;
        if ( v26 < 0 )
          goto LABEL_48;
        ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spDoubleVTV);
        v26 = DirectUI::PropertyValue::CreateFromSingle(
                *(float *)&pstrPromoted.m_encodedStorage.Storage,
                &spDoubleVTV.ptr_);
        v27 = v26;
        if ( v26 < 0 )
          goto LABEL_48;
        goto LABEL_55;
      case TypeName:
        v127 = 0;
        v26 = DirectUI::CValueBoxer::UnboxValue(box, &v127);
        v27 = v26;
        if ( v26 < 0 )
          goto LABEL_48;
        ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spDoubleVTV);
        *(Windows::UI::Xaml::Interop::TypeName *)&v130.M11 = v127;
        v26 = DirectUI::PropertyValue::CreateReference<Windows::UI::Xaml::Interop::TypeName>(
                (Windows::UI::Xaml::Interop::TypeName *)&v130,
                &spDoubleVTV.ptr_);
        v27 = v26;
        if ( v26 < 0 )
          goto LABEL_48;
        goto LABEL_55;
      case Uri:
        v130.M11 = 0.0;
        v77 = DirectUI::CValueBoxer::UnboxValue(box, (Windows::Foundation::IUriRuntimeClass **)&v130);
        v27 = v77;
        if ( v77 < 0 )
          goto LABEL_197;
        v78 = v130.M11;
        v79 = spDoubleVTV.ptr_;
        if ( spDoubleVTV.ptr_ == *(DirectUI::ValueTypeView<double> **)&v130.M11 )
          goto LABEL_188;
        if ( !spDoubleVTV.ptr_ )
          goto LABEL_187;
        spDoubleVTV.ptr_ = 0;
        v79->Release(v79);
        v5 = (const _GUID *)rawValue;
        spDoubleVTV.ptr_ = *(DirectUI::ValueTypeView<double> **)&v78;
        goto LABEL_43;
      case Boolean:
        v125[0].A = 0;
        v32 = DirectUI::CValueBoxer::UnboxValue(box, &v125[0].A);
        v27 = v32;
        if ( v32 < 0 )
          goto LABEL_194;
        ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spDoubleVTV);
        m_ptr = (Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo> *)DirectUI::StaticStore::GetInstance((xref_ptr<DirectUI::StaticStore> *)&v127)->m_ptr;
        if ( v125[0].A )
        {
          Microsoft::WRL::ComPtr<ICastingEventHandler>::InternalAddRef(m_ptr + 2);
          v76 = (DirectUI::ValueTypeView<double> *)m_ptr[2].ptr_;
        }
        else
        {
          Microsoft::WRL::ComPtr<ICastingEventHandler>::InternalAddRef(m_ptr + 3);
          v76 = (DirectUI::ValueTypeView<double> *)m_ptr[3].ptr_;
        }
        spDoubleVTV.ptr_ = v76;
        xref_ptr<DirectUI::StaticStore>::DecrementRefCount((xref_ptr<DirectUI::StaticStore> *)&v127);
        v5 = (const _GUID *)rawValue;
        goto LABEL_43;
      case Color:
        if ( CValue::IsNull(box) )
        {
          v125[0] = 0;
          goto LABEL_132;
        }
        v55 = box->m_flags.m_state.m_asOne & 0x3F;
        LODWORD(pstrPromoted.m_encodedStorage.Storage) = 0;
        if ( v55 == 15 )
        {
          v56 = box->m_value.m_any[0];
LABEL_131:
          v125[0].B = v56;
          v57 = v56 >> 8;
          v125[0].G = v57;
          v125[0].A = BYTE2(v57);
          v125[0].R = BYTE1(v57);
LABEL_132:
          ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spDoubleVTV);
          *(double *)&pstrPromoted.m_encodedStorage.Storage = 0.0;
          v58 = DirectUI::PropertyValue::CreateTypedReference<Windows::UI::Color>(
                  v125[0],
                  (Windows::Foundation::IReference<Windows::UI::Color> **)&pstrPromoted);
          v27 = v58;
          if ( v58 >= 0 )
          {
            v5 = (const _GUID *)rawValue;
            spDoubleVTV.ptr_ = (DirectUI::ValueTypeView<double> *)pstrPromoted.m_encodedStorage.Storage;
            goto LABEL_43;
          }
          OnFailure_2990_(v58);
          if ( *(double *)&pstrPromoted.m_encodedStorage.Storage != 0.0 )
            (*(void (__fastcall **)(const xstring_ptr_storage *))(*(_QWORD *)pstrPromoted.m_encodedStorage.RuntimeStringHandleMarker
                                                                + 16LL))(pstrPromoted.m_encodedStorage.Storage);
          goto LABEL_256;
        }
        if ( v55 == 14 )
        {
          CValue::As<14>(box, (xstring_ptr *)&v130);
          v9 = CColor::ColorFromString((const xstring_ptr_view *)&v130, (unsigned int *)&pstrPromoted);
          xstring_ptr::~xstring_ptr((xstring_ptr *)&v130);
          if ( (v9 & 0x80000000) == 0 )
          {
            v56 = (unsigned int)pstrPromoted.m_encodedStorage.Storage;
            goto LABEL_131;
          }
          OnFailure_2990_(v9);
        }
        else
        {
          if ( v55 == 24 )
          {
            v115 = CValue::As<24>(box);
            v116 = v115;
            if ( v115 )
            {
              if ( CDependencyObject::OfTypeByIndex<112>(v115) )
              {
                v56 = (unsigned int)v116[1].__vftable;
                goto LABEL_131;
              }
            }
          }
          OnFailure_3652_(v54);
        }
        OnFailure_2990_(v9);
        ptr = spDoubleVTV.ptr_;
        if ( !spDoubleVTV.ptr_ )
          return v9;
        goto LABEL_227;
      case CornerRadius:
        v127 = 0;
        v128 = 0;
        v32 = DirectUI::CValueBoxer::UnboxValue(box, (Windows::UI::Xaml::CornerRadius *)&v127);
        v27 = v32;
        if ( v32 < 0 )
          goto LABEL_194;
        ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spDoubleVTV);
        *(double *)&pstrPromoted.m_encodedStorage.Storage = 0.0;
        v69 = DirectUI::PropertyValue::CreateTypedReference<Windows::UI::Xaml::CornerRadius>(
                (Windows::UI::Xaml::CornerRadius *)&v127,
                (Windows::Foundation::IReference<Windows::UI::Xaml::CornerRadius> **)&pstrPromoted);
        v27 = v69;
        if ( v69 >= 0 )
        {
          v5 = (const _GUID *)rawValue;
          spDoubleVTV.ptr_ = (DirectUI::ValueTypeView<double> *)pstrPromoted.m_encodedStorage.Storage;
          goto LABEL_43;
        }
        OnFailure_2990_(v69);
        if ( *(double *)&pstrPromoted.m_encodedStorage.Storage != 0.0 )
          (*(void (__fastcall **)(const xstring_ptr_storage *))(*(_QWORD *)pstrPromoted.m_encodedStorage.RuntimeStringHandleMarker
                                                              + 16LL))(pstrPromoted.m_encodedStorage.Storage);
        goto LABEL_256;
      case Double:
        *(double *)&pstrPromoted.m_encodedStorage.Storage = 0.0;
        if ( CValue::IsNull(box) )
        {
          *(double *)&pstrPromoted.m_encodedStorage.Storage = 0.0;
          goto LABEL_54;
        }
        v29 = box->m_flags.m_state.m_asOne & 0x3F;
        switch ( v29 )
        {
          case 8u:
            *(double *)&pstrPromoted.m_encodedStorage.Storage = box->m_value.m_float;
LABEL_54:
            ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spDoubleVTV);
            PropertyValueStaticsNoRef = DirectUI::StaticStore::GetPropertyValueStaticsNoRef();
            v31 = ((__int64 (__fastcall *)(Windows::Foundation::IPropertyValueStatics *, Windows::Foundation::IPropertyValueStatics *, ctl::ComPtr<DirectUI::ValueTypeView<double> > *))PropertyValueStaticsNoRef->CreateDouble)(
                    PropertyValueStaticsNoRef,
                    PropertyValueStaticsNoRef,
                    &spDoubleVTV);
            v27 = v31;
            if ( v31 >= 0 )
              goto LABEL_55;
            OnFailure_2990_(v31);
            OnFailure_2990_(v27);
LABEL_210:
            v89 = spDoubleVTV.ptr_;
            if ( spDoubleVTV.ptr_ )
            {
LABEL_211:
              spDoubleVTV.ptr_ = 0;
              v89->Release(v89);
              return v27;
            }
            return v27;
          case 9u:
            *(double *)&pstrPromoted.m_encodedStorage.Storage = CValue::As<9>(box);
            goto LABEL_54;
          case 0xEu:
            v91 = (unsigned __int64)box->m_value.m_any[1] << 32;
            *(_QWORD *)&v130.M11 = &xstring_ptr_constants::c_xstring_ptr_storage_null;
            v127.Name = (HSTRING__ *)(box->m_value.m_any[0] | v91);
            xephemeral_string_ptr::Decode((const xencoded_string_ptr *)&v127, (xephemeral_string_ptr *)&v130);
            v92 = lambda_bc04cb400b0a1bb49a71564b8916f1b7_::_lambda_invoker_cdecl_(
                    (const xstring_ptr_view *)&v130,
                    (long double *)&pstrPromoted);
            v9 = v92;
            if ( v92 >= 0 )
              goto LABEL_54;
            break;
          case 4u:
            *(double *)&pstrPromoted.m_encodedStorage.Storage = (double)box->m_value.m_signed;
            goto LABEL_54;
          case 6u:
            *(double *)&pstrPromoted.m_encodedStorage.Storage = (double)(int)CValue::As<6>(box);
            goto LABEL_54;
          case 0x18u:
            v114 = CValue::As<24>(box);
            v92 = lambda_ceaa395dd0caf639184d8357031ac9c0_::_lambda_invoker_cdecl_(v114, (long double *)&pstrPromoted);
            v9 = v92;
            if ( v92 >= 0 )
              goto LABEL_54;
            break;
          default:
            OnFailure_3652_(v28);
            goto LABEL_225;
        }
        OnFailure_2990_(v92);
LABEL_225:
        OnFailure_2990_(v9);
        goto LABEL_226;
      case FontFamily:
        v130.M11 = 0.0;
        v77 = DirectUI::CValueBoxer::UnboxValue(box, (Windows::UI::Xaml::Media::IFontFamily **)&v130);
        v27 = v77;
        if ( v77 < 0 )
        {
LABEL_197:
          OnFailure_2990_(v77);
          goto LABEL_198;
        }
        v78 = v130.M11;
        v82 = spDoubleVTV.ptr_;
        if ( spDoubleVTV.ptr_ != *(DirectUI::ValueTypeView<double> **)&v130.M11 )
        {
          if ( spDoubleVTV.ptr_ )
          {
            spDoubleVTV.ptr_ = 0;
            v82->Release(v82);
          }
LABEL_187:
          spDoubleVTV.ptr_ = *(DirectUI::ValueTypeView<double> **)&v78;
        }
        goto LABEL_188;
      case FontWeight:
        *(_WORD *)&v125[0].A = 0;
        v32 = DirectUI::CValueBoxer::UnboxValue(box, (Windows::UI::Text::FontWeight *)v125);
        v27 = v32;
        if ( v32 < 0 )
          goto LABEL_194;
        ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spDoubleVTV);
        v88 = DirectUI::PropertyValue::CreateReference<Windows::UI::Text::FontWeight>(
                *(Windows::UI::Text::FontWeight *)&v125[0].A,
                &spDoubleVTV.ptr_);
        v27 = v88;
        if ( v88 < 0 )
          goto LABEL_209;
        goto LABEL_55;
      case GridLength:
        v127 = 0;
        v32 = DirectUI::CValueBoxer::UnboxValue(box, (Windows::UI::Xaml::GridLength *)&v127);
        v27 = v32;
        if ( v32 < 0 )
          goto LABEL_194;
        ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spDoubleVTV);
        v26 = DirectUI::PropertyValue::CreateReference<Windows::UI::Xaml::GridLength>(
                (Windows::UI::Xaml::GridLength *)&v127,
                &spDoubleVTV.ptr_);
        v27 = v26;
        if ( v26 < 0 )
          goto LABEL_48;
        goto LABEL_55;
      case Int32:
        LODWORD(pstrPromoted.m_encodedStorage.Storage) = 0;
        v32 = DirectUI::CValueBoxer::UnboxValueHelper<int>(
                box,
                lambda_cf11065c9aaf4b35524004b6d4e50f11_::_lambda_invoker_cdecl_,
                (HRESULT (__fastcall *)(const CDependencyObject *, int *))lambda_e89a33f42b3224ae6f53928e8640cd84_::_lambda_invoker_cdecl_,
                (int *)&pstrPromoted);
        v27 = v32;
        if ( v32 < 0 )
          goto LABEL_194;
        ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spDoubleVTV);
        v88 = DirectUI::PropertyValue::CreateFromInt32((int)pstrPromoted.m_encodedStorage.Storage, &spDoubleVTV.ptr_);
        v27 = v88;
        if ( v88 < 0 )
          goto LABEL_209;
        goto LABEL_55;
      case Matrix:
        v127 = 0;
        v128 = 0;
        v129 = 0;
        v26 = DirectUI::CValueBoxer::UnboxValue(box, (Windows::UI::Xaml::Media::Matrix *)&v127);
        v27 = v26;
        if ( v26 < 0 )
          goto LABEL_48;
        ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spDoubleVTV);
        *(Windows::UI::Xaml::Interop::TypeName *)&v130.M11 = v127;
        *(_OWORD *)&v130.M21 = v128;
        *(_OWORD *)&v130.OffsetX = v129;
        v26 = DirectUI::PropertyValue::CreateReference<Windows::UI::Xaml::Media::Matrix>(&v130, &spDoubleVTV.ptr_);
        v27 = v26;
        if ( v26 < 0 )
          goto LABEL_48;
        goto LABEL_55;
      case Matrix3D:
        memset_0(&v131, 0, sizeof(v131));
        v26 = DirectUI::CValueBoxer::UnboxValue(box, &v131);
        v27 = v26;
        if ( v26 < 0 )
          goto LABEL_48;
        ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spDoubleVTV);
        v132 = v131;
        v26 = DirectUI::PropertyValue::CreateReference<Windows::UI::Xaml::Media::Media3D::Matrix3D>(
                &v132,
                &spDoubleVTV.ptr_);
        v27 = v26;
        if ( v26 < 0 )
          goto LABEL_48;
        goto LABEL_55;
      case Point:
        v130.M11 = 0.0;
        v26 = DirectUI::CValueBoxer::UnboxValue(box, (Windows::Foundation::Point *)&v130);
        v27 = v26;
        if ( v26 < 0 )
          goto LABEL_48;
        ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spDoubleVTV);
        v88 = DirectUI::PropertyValue::CreateFromPoint(*(Windows::Foundation::Point *)&v130.M11, &spDoubleVTV.ptr_);
        v27 = v88;
        if ( v88 < 0 )
          goto LABEL_209;
        goto LABEL_55;
      case PropertyPath:
        v130.M11 = 0.0;
        v26 = DirectUI::CValueBoxer::UnboxValue(box, (Windows::UI::Xaml::IPropertyPath **)&v130);
        v27 = v26;
        if ( v26 < 0 )
          goto LABEL_48;
        ctl::ComPtr<Windows::UI::Xaml::Input::IPointerEventHandler>::Attach(
          (ctl::ComPtr<Windows::UI::Xaml::Input::IPointerEventHandler> *)&spDoubleVTV,
          *(Windows::UI::Xaml::Input::IPointerEventHandler **)&v130.M11);
        v5 = (const _GUID *)rawValue;
        goto LABEL_43;
      case Rect:
        v127 = 0;
        v32 = DirectUI::CValueBoxer::UnboxValue(box, (Windows::Foundation::Rect *)&v127);
        v27 = v32;
        if ( v32 < 0 )
          goto LABEL_194;
        ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spDoubleVTV);
        v88 = DirectUI::PropertyValue::CreateFromRect((Windows::Foundation::Rect *)&v127, &spDoubleVTV.ptr_);
        v27 = v88;
        if ( v88 < 0 )
          goto LABEL_209;
        goto LABEL_55;
      case Size:
        v130.M11 = 0.0;
        v26 = DirectUI::CValueBoxer::UnboxValue(box, (Windows::Foundation::Size *)&v130);
        v27 = v26;
        if ( v26 < 0 )
          goto LABEL_48;
        ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spDoubleVTV);
        v88 = DirectUI::PropertyValue::CreateFromSize(*(Windows::Foundation::Size *)&v130.M11, &spDoubleVTV.ptr_);
        v27 = v88;
        if ( v88 < 0 )
          goto LABEL_209;
        goto LABEL_55;
      default:
        goto LABEL_32;
    }
  }
  if ( ((*(_BYTE *)&box->m_flags.m_state.0 & 0x3F) == 0 || CValue::IsNull(box))
    && (*(_BYTE *)&box->m_flags.m_state.0 & 0x3F) != 0xE )
  {
    goto LABEL_55;
  }
  *(double *)&pstrPromoted.m_encodedStorage.Storage = COERCE_DOUBLE(&xstring_ptr_constants::c_xstring_ptr_storage_null);
  v44 = box->m_flags.m_state.m_asOne & 0x3F;
  if ( v44 == 14 )
  {
    v45 = (__int64)box->m_value;
    v127.Name = (HSTRING__ *)v45;
    if ( (v45 & 1) != 0 )
    {
      v70 = (const xstring_ptr_storage **)xencoded_string_ptr::Clone((xencoded_string_ptr *)&v127).Storage;
      xencoded_string_ptr::Reset(&pstrPromoted);
      pstrPromoted.m_encodedStorage.Storage = *v70;
    }
    else
    {
      v127.Name = (HSTRING__ *)v45;
      if ( v45 )
      {
        v46 = *(_DWORD *)(v45 + 8);
        v125[0] = 0;
        StringRawBuffer = *(HSTRING *)v45;
        if ( v46 < 0 )
        {
          StringRawBuffer = (HSTRING)WindowsGetStringRawBuffer(*(HSTRING *)v45, (UINT32 *)&v125[0].A);
          v48 = (UINT32)v125[0];
        }
        else
        {
          v48 = v46 & 0x3FFFFFFF;
          v125[0] = (Windows::UI::Color)v48;
        }
        String = WindowsCreateString((PCNZWCH)StringRawBuffer, v48, (HSTRING *)&v130);
        v9 = String;
        if ( String < 0 )
        {
          OnFailure_2990_(String);
          OnFailure_2990_(v9);
          xstring_ptr::~xstring_ptr((xstring_ptr *)&v127);
          OnFailure_2990_(v9);
          OnFailure_2990_(v9);
LABEL_110:
          xencoded_string_ptr::Reset(&pstrPromoted);
          goto LABEL_111;
        }
        v45 = *(_QWORD *)&v130.M11 | 1LL;
      }
      *(_QWORD *)&v130.M11 = v45;
      xencoded_string_ptr::Reset(&pstrPromoted);
      pstrPromoted.m_encodedStorage.Storage = *(const xstring_ptr_storage **)&v130.M11;
      xstring_ptr::~xstring_ptr((xstring_ptr *)&v127);
    }
  }
  else if ( v44 == 24 )
  {
    v94 = CValue::As<24>(box);
    v95 = do_pointer_cast<CString>(v94);
    v96 = xstring_ptr_view::Promote(&v95->m_strString, &pstrPromoted);
    v9 = v96;
    if ( v96 < 0 )
    {
      OnFailure_2990_(v96);
      xencoded_string_ptr::Reset(&pstrPromoted);
LABEL_111:
      OnFailure_2990_(v9);
      v50 = spDoubleVTV.ptr_;
      if ( spDoubleVTV.ptr_ )
      {
        spDoubleVTV.ptr_ = 0;
        v50->Release(v50);
      }
      return v9;
    }
  }
  else if ( !CValue::IsNull(box) )
  {
    OnNewFailure_2955_(v53);
    goto LABEL_110;
  }
  v71 = xruntime_string_ptr::DetachHSTRING(&pstrPromoted);
  xencoded_string_ptr::Reset(&pstrPromoted);
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spDoubleVTV);
  v72 = DirectUI::StaticStore::GetPropertyValueStaticsNoRef();
  v73 = v72->CreateString(v72, v71, &spDoubleVTV.ptr_);
  v74 = v73;
  if ( v73 >= 0 )
  {
    if ( v71 )
    {
      WindowsDeleteString(v71);
      v5 = (const _GUID *)rawValue;
      goto LABEL_43;
    }
    goto LABEL_55;
  }
  OnFailure_2990_(v73);
  OnFailure_2990_(v74);
  if ( v71 )
    WindowsDeleteString(v71);
  v102 = spDoubleVTV.ptr_;
  if ( spDoubleVTV.ptr_ )
  {
    spDoubleVTV.ptr_ = 0;
    v102->Release(v102);
  }
  return v74;
}

```

## disassembly

```asm
0x18007af60  mov     r11, rsp
0x18007af63  push    rbp
0x18007af64  push    rbx
0x18007af65  push    rsi
0x18007af66  push    rdi
0x18007af67  lea     rbp, [r11-118h]
0x18007af6e  sub     rsp, 1F8h
0x18007af75  mov     rax, cs:__security_cookie
0x18007af7c  xor     rax, rsp
0x18007af7f  mov     [rbp+110h+var_40], rax
0x18007af86  mov     qword ptr [rsp+210h+rawValue.StartIndex], riid
0x18007af8b  mov     rsi, riid
0x18007af8e  mov     rbx, pTargetType
0x18007af91  mov     rdi, box
0x18007af94  test    box, box
0x18007af97  jz      loc_18007B55F
0x18007af9d  mov     [r11+18h], r14
0x18007afa1  mov     r14, [rbp+110h+arg_20]
0x18007afa8  test    r14, r14
0x18007afab  jz      loc_18007CC43
0x18007afb1  mov     [r11+8], r12
0x18007afb5  xor     r12d, r12d
0x18007afb8  mov     [r11+10h], r13
0x18007afbc  mov     [r11-28h], r15
0x18007afc0  movaps  xmmword ptr [r11-38h], xmm6
0x18007afc5  mov     [rsp+210h+spDoubleVTV.ptr_], r12
0x18007afca  test    targetTypeIsNullable, targetTypeIsNullable
0x18007afcd  jz      short loc_18007AFDB
0x18007afcf  mov     eax, [box+8]
0x18007afd2  and     eax, 3Fh
0x18007afd5  jnz     loc_18007B3B0
0x18007afdb  lea     r12, std__nothrow
0x18007afe2  mov     r13d, 8000FFFFh
0x18007afe8  mov     eax, [rdi+8]; jumptable 000000018007B1EC cases 2-9,15,22,23,32,33
0x18007afeb  mov     ecx, 95h
0x18007aff0  and     eax, 3Fh
0x18007aff3  cmp     eax, 1Bh
0x18007aff6  jz      short loc_18007B072
0x18007aff8  test    rbx, rbx
0x18007affb  jz      loc_18007B0B5
0x18007b001  cmp     [rbx], cx
0x18007b004  lea     box, [rbx+4]; failedFrameHR
0x18007b008  jz      loc_18007BB20
0x18007b00e  test    dword ptr [box], 800h
0x18007b014  jnz     loc_18007BB20
0x18007b01a  mov     edx, [box]
0x18007b01c  bt      edx, 0Ch
0x18007b020  jnb     loc_18007B0B5
0x18007b026  bt      edx, 8
0x18007b02a  jnb     short loc_18007B035
0x18007b02c  cmp     eax, 0Eh
0x18007b02f  jz      loc_18007BBA4
0x18007b035  mov     box, rbx; pType
0x18007b038  call    ?TryGetBoxedType@MetadataAPI@DirectUI@@SAPEBVCClassInfo@@PEBV3@@Z; DirectUI::MetadataAPI::TryGetBoxedType(CClassInfo const *)
0x18007b03d  mov     r15, rax
0x18007b040  test    rax, rax
0x18007b043  jz      short loc_18007B0B5
0x18007b045  lea     box, [rsp+210h+spDoubleVTV]; this
0x18007b04a  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x18007b04f  lea     r8, [rsp+210h+spDoubleVTV]; value
0x18007b054  mov     pTargetType, r15; pTargetType
0x18007b057  mov     box, rdi; box
0x18007b05a  call    ?UnboxObjectValue@CValueBoxer@DirectUI@@SAJPEBVCValue@@PEBVCClassInfo@@PEAPEAUIInspectable@@@Z; DirectUI::CValueBoxer::UnboxObjectValue(CValue const *,CClassInfo const *,IInspectable * *)
0x18007b05f  mov     r15d, eax
0x18007b062  test    eax, eax
0x18007b064  jns     short loc_18007B0B5
0x18007b066  mov     ecx, eax; failedFrameHR
0x18007b068  call    OnFailure_2990_
0x18007b06d  jmp     loc_18007BB6D
0x18007b072  mov     r15d, [rdi+4]
0x18007b076  mov     eax, [rdi]
0x18007b078  shl     r15, 20h
0x18007b07c  or      r15, rax
0x18007b07f  cmp     [rsp+210h+spDoubleVTV.ptr_], r15
0x18007b084  jz      short loc_18007B0B5
0x18007b086  test    r15, r15
0x18007b089  jz      short loc_18007B09A
0x18007b08b  mov     rax, [r15]
0x18007b08e  mov     box, r15
0x18007b091  mov     rax, [rax+8]
0x18007b095  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b09a  mov     box, [rsp+210h+spDoubleVTV.ptr_]
0x18007b09f  mov     [rsp+210h+spDoubleVTV.ptr_], r15
0x18007b0a4  test    box, box
0x18007b0a7  jz      short loc_18007B0B5
0x18007b0a9  mov     rax, [box]
0x18007b0ac  mov     rax, [rax+10h]
0x18007b0b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b0b5  cmp     [rsp+210h+spDoubleVTV.ptr_], 0
0x18007b0bb  jnz     loc_18007B22A
0x18007b0c1  mov     eax, [rdi+8]
0x18007b0c4  and     eax, 3Fh
0x18007b0c7  jz      loc_18007B4BD
0x18007b0cd  mov     edx, 28h ; '('
0x18007b0d2  mov     r15d, 210h
0x18007b0d8  movzx   ecx, dx
0x18007b0db  cmp     eax, 18h
0x18007b0de  jz      loc_18007B510
0x18007b0e4  xor     esi, esi
0x18007b0e6  mov     eax, [rdi+8]
0x18007b0e9  and     eax, 3Fh
0x18007b0ec  cmp     al, 1Dh
0x18007b0ee  jz      short loc_18007B10C
0x18007b0f0  movzx   r15d, dx
0x18007b0f4  test    rbx, rbx
0x18007b0f7  jz      loc_18007B4F7
0x18007b0fd  movzx   r15d, word ptr [rbx]
0x18007b101  cmp     r15w, 28h ; '('
0x18007b106  jz      loc_18007B4F7
0x18007b10c  cmp     [rsp+210h+spDoubleVTV.ptr_], 0
0x18007b112  jnz     loc_18007B34B
0x18007b118  movzx   ecx, r15w
0x18007b11c  cmp     ecx, 10Dh
0x18007b122  ja      loc_18007B355
0x18007b128  jz      loc_18007B5CE
0x18007b12e  add     ecx, 0FFFFFFF6h; switch 254 cases
0x18007b131  cmp     ecx, 0FDh
0x18007b137  jbe     loc_18007B2C4
0x18007b13d  test    rsi, rsi; jumptable 000000018007B2DB default case, cases 11-25,27-41,44-70,72-98,100-111,113-128,130-139,141-157,160-164,166-186,188-208,211-229,231-241,244-262
0x18007b140  jz      loc_18007B4BD
0x18007b146  mov     rax, [rsi]
0x18007b149  mov     box, rsi
0x18007b14c  mov     rax, [rax+258h]
0x18007b153  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b158  movzx   ebx, ax
0x18007b15b  mov     r15d, 95h
0x18007b161  cmp     r15w, bx
0x18007b165  jz      loc_18007CAE0
0x18007b16b  mov     edi, 43Ch
0x18007b170  cmp     bx, di
0x18007b173  jb      loc_18007B3C8
0x18007b179  lea     box, ?g_csStatic@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18007b180  call    cs:__imp_EnterCriticalSection
0x18007b186  call    ?GetInstance@DynamicMetadataStorage@DirectUI@@CAPEAV12@XZ; DirectUI::DynamicMetadataStorage::GetInstance(void)
0x18007b18b  mov     edx, ebx
0x18007b18d  lea     box, ?g_csStatic@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18007b194  sub     edx, edi
0x18007b196  mov     rax, [rax+60h]
0x18007b19a  mov     rbx, [rax+pTargetType*8]
0x18007b19e  call    cs:__imp_LeaveCriticalSection
0x18007b1a4  movzx   eax, word ptr [rbx]
0x18007b1a7  test    ax, ax
0x18007b1aa  jz      loc_18007B509
0x18007b1b0  cmp     ax, r15w
0x18007b1b4  jz      loc_18007B3BE
0x18007b1ba  movzx   ecx, word ptr [rbx+2]; eTypeIndex
0x18007b1be  call    ?GetClassInfoByIndex@MetadataAPI@DirectUI@@SAPEBVCClassInfo@@W4KnownTypeIndex@@@Z; DirectUI::MetadataAPI::GetClassInfoByIndex(KnownTypeIndex)
0x18007b1c3  mov     rbx, rax
0x18007b1c6  jmp     short loc_18007B1A4
0x18007b1c8  add     eax, 0FFFFFFFEh; switch 32 cases
0x18007b1cb  lea     r12, std__nothrow
0x18007b1d2  mov     r13d, 8000FFFFh
0x18007b1d8  cmp     eax, 1Fh
0x18007b1db  ja      def_18007B1EC; jumptable 000000018007B1EC default case
0x18007b1e1  mov     eax, ds:(jpt_18007B1EC - 180000000h)[r12+rax*4]
0x18007b1e9  add     rax, r12
0x18007b1ec  jmp     rax; switch jump
0x18007b1ee  mov     ecx, [box+4]; jumptable 000000018007B1EC case 14
0x18007b1f1  mov     eax, [rdi]
0x18007b1f3  shl     box, 20h
0x18007b1f7  or      box, rax
0x18007b1fa  test    cl, 1
0x18007b1fd  jnz     loc_18007B577
0x18007b203  mov     qword ptr [rbp+110h+var_170.___u0], box
0x18007b207  lea     box, [rbp+110h+var_170]; this
0x18007b20b  call    ?IsNull@xencoded_string_ptr@@QEBA_NXZ; xencoded_string_ptr::IsNull(void)
0x18007b210  lea     box, [rbp+110h+var_170]; this
0x18007b214  movzx   esi, al
0x18007b217  call    ??1xstring_ptr@@QEAA@XZ; xstring_ptr::~xstring_ptr(void)
0x18007b21c  test    sil, sil
0x18007b21f  mov     rsi, qword ptr [rsp+210h+rawValue.StartIndex]
0x18007b224  jz      $LN1988; jumptable 000000018007B1EC cases 2-9,15,22,23,32,33
0x18007b22a  xor     r12d, r12d
0x18007b22d  mov     box, [rsp+210h+spDoubleVTV.ptr_]
0x18007b232  test    box, box
0x18007b235  jnz     short loc_18007B297
0x18007b237  mov     box, [rsp+210h+spDoubleVTV.ptr_]
0x18007b23c  test    box, box
0x18007b23f  jz      short loc_18007B252
0x18007b241  mov     [rsp+210h+spDoubleVTV.ptr_], r12
0x18007b246  mov     rax, [box]
0x18007b249  mov     rax, [rax+10h]
0x18007b24d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b252  xor     eax, eax
0x18007b254  mov     r15, [rsp+1F0h]
0x18007b25c  mov     r13, [rsp+210h+arg_8]
0x18007b264  movaps  xmm6, [rsp+210h+var_38+8]
0x18007b26c  mov     r12, [rsp+210h+arg_0]
0x18007b274  mov     r14, [rsp+210h+arg_10]
0x18007b27c  mov     box, [rbp+110h+var_40]
0x18007b283  xor     box, rsp; StackCookie
0x18007b286  call    __security_check_cookie
0x18007b28b  add     rsp, 1F8h
0x18007b292  pop     rdi
0x18007b293  pop     rsi
0x18007b294  pop     rbx
0x18007b295  pop     rbp
0x18007b296  retn
0x18007b297  mov     rax, [box]
0x18007b29a  mov     r8, r14
0x18007b29d  mov     pTargetType, rsi
0x18007b2a0  mov     rax, [rax]
0x18007b2a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b2a8  mov     ebx, eax
0x18007b2aa  test    eax, eax
0x18007b2ac  jns     short loc_18007B237
0x18007b2ae  mov     ecx, eax; failedFrameHR
0x18007b2b0  call    OnFailure_2990_
0x18007b2b5  lea     box, [rsp+210h+spDoubleVTV]; this
0x18007b2ba  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x18007b2bf  jmp     loc_18007BD6F
0x18007b2c4  movsxd  rax, ecx
0x18007b2c7  movzx   eax, ds:(byte_18007CD24 - 180000000h)[r12+rax]
0x18007b2d0  mov     ecx, ds:(jpt_18007B2DB - 180000000h)[r12+rax*4]
0x18007b2d8  add     box, r12
0x18007b2db  jmp     box; switch jump
0x18007b2dd  xorps   xmm6, xmm6; jumptable 000000018007B2DB case 140
0x18007b2e0  mov     box, rdi; this
0x18007b2e3  movsd   qword ptr [rsp+210h+pstrPromoted.m_encodedStorage.___u0], xmm6
0x18007b2e9  call    ?IsNull@CValue@@QEBA_NXZ; CValue::IsNull(void)
0x18007b2ee  test    al, al
0x18007b2f0  jnz     loc_18007C80B
0x18007b2f6  mov     eax, [rdi+8]
0x18007b2f9  and     eax, 3Fh
0x18007b2fc  cmp     eax, 8
0x18007b2ff  jnz     loc_18007BA35
0x18007b305  movss   xmm0, dword ptr [rdi]
0x18007b309  cvtps2pd xmm0, xmm0
0x18007b30c  movsd   qword ptr [rsp+210h+pstrPromoted.m_encodedStorage.___u0], xmm0
0x18007b312  lea     box, [rsp+210h+spDoubleVTV]; this
0x18007b317  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x18007b31c  movsd   xmm6, qword ptr [rsp+210h+pstrPromoted.m_encodedStorage.___u0]
0x18007b322  call    ?GetPropertyValueStaticsNoRef@StaticStore@DirectUI@@SAPEAUIPropertyValueStatics@Foundation@Windows@@XZ; DirectUI::StaticStore::GetPropertyValueStaticsNoRef(void)
0x18007b327  mov     pTargetType, rax
0x18007b32a  lea     r8, [rsp+210h+spDoubleVTV]
0x18007b32f  movaps  xmm1, xmm6
0x18007b332  mov     box, [rax]
0x18007b335  mov     rax, [box+78h]
0x18007b339  mov     box, pTargetType
0x18007b33c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b341  mov     ebx, eax
0x18007b343  test    eax, eax
0x18007b345  js      loc_18007C816
0x18007b34b  mov     rsi, qword ptr [rsp+210h+rawValue.StartIndex]
0x18007b350  jmp     loc_18007B22A
0x18007b355  cmp     ecx, 1A2h
0x18007b35b  jbe     loc_18007B6F3
0x18007b361  sub     ecx, 1C6h
0x18007b367  jz      loc_18007CBEC
0x18007b36d  sub     ecx, 4Ah ; 'J'
0x18007b370  jz      loc_18007CB5A
0x18007b376  cmp     ecx, 79h ; 'y'
0x18007b379  jnz     def_18007B2DB; jumptable 000000018007B2DB default case, cases 11-25,27-41,44-70,72-98,100-111,113-128,130-139,141-157,160-164,166-186,188-208,211-229,231-241,244-262
0x18007b37f  xorps   xmm0, xmm0
0x18007b382  lea     pTargetType, [rsp+210h+var_1A0]; value
0x18007b387  xor     eax, eax
0x18007b389  mov     box, rdi; box
0x18007b38c  movups  xmmword ptr [rsp+210h+var_1A0], xmm0
0x18007b391  mov     qword ptr [rbp+110h+var_1A0+10h], rax
0x18007b395  call    ?UnboxValue@CValueBoxer@DirectUI@@SAJPEBVCValue@@PEAURepeatBehavior@Animation@Media@Xaml@UI@Windows@@@Z; DirectUI::CValueBoxer::UnboxValue(CValue const *,Windows::UI::Xaml::Media::Animation::RepeatBehavior *)
0x18007b39a  mov     ebx, eax
0x18007b39c  test    eax, eax
0x18007b39e  jns     loc_18007CB19
0x18007b3a4  mov     ecx, eax; failedFrameHR
0x18007b3a6  call    OnFailure_2990_
0x18007b3ab  jmp     loc_18007BCD1
0x18007b3b0  cmp     eax, 1
0x18007b3b3  jz      loc_18007B237
0x18007b3b9  jmp     loc_18007B1C8
0x18007b3be  mov     al, 1
0x18007b3c0  test    al, al
0x18007b3c2  jnz     loc_18007CAE0
0x18007b3c8  mov     ecx, cs:?g_dwTlsIndex@DXamlInstanceStorage@@3KA; failedFrameHR
0x18007b3ce  xor     r12d, r12d
0x18007b3d1  mov     qword ptr [rbp+110h+var_170.___u0], r12
0x18007b3d5  cmp     ecx, 0FFFFFFFFh
0x18007b3d8  jz      loc_18007BFA7
0x18007b3de  call    cs:__imp_TlsGetValue
0x18007b3e4  mov     rbx, rax
0x18007b3e7  test    rax, rax
0x18007b3ea  jz      loc_18007BC3A
0x18007b3f0  mov     rax, [rsi]
0x18007b3f3  mov     box, rsi
0x18007b3f6  mov     rax, [rax+258h]
0x18007b3fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b402  lea     rax, [rbp+110h+var_170]
0x18007b406  mov     r9d, 1; createMode
0x18007b40c  mov     [rsp+40h], rax; pCoreDO
0x18007b411  mov     r8, rsi; pCoreDO
0x18007b414  mov     [rsp+210h+pOuter], r12; pOuter
0x18007b419  xor     edx, edx; pOuter
0x18007b41b  mov     box, rbx; this
0x18007b41e  mov     dword ptr [rsp+210h+var_1F0+8], r12d; pIsPendingDelete
0x18007b423  call    ?GetPeerPrivate@DXamlCore@DirectUI@@AEAAJPEAUIInspectable@@PEAVCDependencyObject@@W4GetPeerPrivateCreateMode@12@W4KnownTypeIndex@@IIPEAIPEAPEAVDependencyObject@2@@Z; DirectUI::DXamlCore::GetPeerPrivate(IInspectable *,CDependencyObject *,DirectUI::DXamlCore::GetPeerPrivateCreateMode,KnownTypeIndex,uint,uint,uint *,DirectUI::DependencyObject * *)
0x18007b428  mov     ebx, eax
0x18007b42a  test    eax, eax
0x18007b42c  js      loc_18007C472
0x18007b432  mov     box, [rsp+210h+spDoubleVTV.ptr_]
0x18007b437  test    box, box
0x18007b43a  jz      short loc_18007B44D
  ... truncated ...
```
