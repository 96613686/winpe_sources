# CUIElement::GetValue(CDependencyProperty const *,CValue *)

- ea: `0x180032390`
- end: `0x180033a1c`
- name: `?GetValue@CUIElement@@UEAAJPEBVCDependencyProperty@@PEAVCValue@@@Z`
- size: `5772`
- prototype: `HRESULT __fastcall(CUIElement *this, const CDependencyProperty *dp, CValue *value)`
- caller_count: `8`
- callee_count: `41`
- tags: `file_ops, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180032190`
- `0x1804d5e30`
- `0x1804e681c`
- `0x180517640`
- `0x180534eb0`
- `0x180537230`
- `0x1805e56dc`
- `0x18080aa18`

## callees

- `0x180004bc0`
- `0x180021840`
- `0x180021960`
- `0x180021970`
- `0x18002c780`
- `0x18002cf20`
- `0x18002d990`
- `0x1800301a0`
- `0x1800313dc`
- `0x180032390`
- `0x1800344f8`
- `0x18003f058`
- `0x18003fcfc`
- `0x18004486c`
- `0x180044944`
- `0x180044968`
- `0x180044a14`
- `0x18006cfd0`
- `0x1800710d0`
- `0x18007433c`
- `0x1800ab600`
- `0x1800c4060`
- `0x1800c8bf4`
- `0x1800fe130`
- `0x180100978`
- `0x180131190`
- `0x1802a9b64`
- `0x1802a9eb8`
- `0x1802aa7fc`
- `0x1802aaeb8`
- `0x1802aaf24`
- `0x1802bc7d0`
- `0x1804894e0`
- `0x18054204c`
- `0x1806877a8`
- `0x180687890`
- `0x180688828`
- `0x1806e0934`
- `0x1806e0a18`
- `0x18076e110`
- `0x180c0e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800328d7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180032d83`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800328d7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180032d83`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800328f8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180032da7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800328f8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180032da7`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x180032992`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x180033001`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x180033679`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x18003377b`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x180032992`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x180033001`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x180033679`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x18003377b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180032941`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180032fb0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180032941`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180032fb0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800337d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800337ec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800337d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800337ec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180033247`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180033284`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800332aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180033247`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180033284`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800332aa`

## pseudocode

```c
__int64 __fastcall CUIElement::GetValue(CUIElement *this, const CDependencyProperty *dp, CValue *value)
{
  __int64 v3; // r12
  CValue *v5; // rsi
  CUIElement *v6; // r13
  MetaDataPropertyInfoFlags m_flags; // r10d
  __int64 m_nIndex; // r9
  const CValue *v9; // rbx
  __int64 m_nPropertyTypeIndex; // r15
  HRESULT v11; // edi
  containers::vector_map<enum KnownPropertyIndex,EffectiveValue,std::less<void>,std::allocator<std::pair<enum KnownPropertyIndex,EffectiveValue> > > *v12; // rax
  std::pair<enum KnownPropertyIndex,EffectiveValue> *v13; // rcx
  KnownPropertyIndex v14; // r11
  unsigned __int64 v15; // r8
  const CValue *p_value; // rbx
  int v17; // eax
  bool v18; // al
  HRESULT DefaultValue; // eax
  unsigned int v20; // r15d
  bool v21; // zf
  CDependencyObject *v22; // rdi
  HRESULT v23; // eax
  HRESULT v24; // r14d
  unsigned int v25; // r14d
  unsigned int v26; // ecx
  CValueDetails::CValueState v27; // ecx
  Flyweight::ValueObjectWrapper<CDOSharedState> *m_ptr; // rax
  CCoreServices *m_coreServices; // rbx
  HRESULT DefaultValueObject; // eax
  unsigned int v32; // ebx
  CUIElement_vtbl *v33; // rax
  HRESULT (__fastcall *SetValue)(CDependencyObject *, const SetValueParams *); // rax
  HRESULT v35; // eax
  HRESULT v36; // ebx
  CCustomClassInfo *v37; // r15
  CValueDetails::Value v38; // rbx
  __int64 v39; // r15
  unsigned int Storage; // xmm6_4
  unsigned int RuntimeStringHandleMarker_high; // eax
  unsigned __int64 m_value; // rbx
  int v43; // edx
  const wchar_t *v44; // rax
  UINT32 v45; // edx
  int v46; // eax
  int v47; // edx
  unsigned __int8 m_nPropertySlotCount; // cl
  unsigned int v49; // edx
  CDependencyObject::BitField v50; // r8
  unsigned int v51; // eax
  unsigned __int8 v52; // cf
  unsigned int v53; // xmm6_4
  unsigned int v54; // eax
  CDependencyObject *v55; // rbx
  __int64 v56; // rdi
  KnownTypeIndex v57; // ax
  unsigned __int64 m_handle; // rdx
  int v59; // r15d
  CCustomClassInfo *ClassInfoByIndex; // r15
  unsigned __int64 m_handleMask; // rcx
  bool v62; // al
  unsigned __int8 v63; // cl
  unsigned int v64; // r8d
  CDependencyObject::BitField v65; // rcx
  unsigned int v66; // eax
  unsigned __int8 v67; // cf
  HRESULT v68; // eax
  unsigned int v69; // edi
  containers::vector_map<enum KnownPropertyIndex,EffectiveValue,std::less<void>,std::allocator<std::pair<enum KnownPropertyIndex,EffectiveValue> > > *v70; // rax
  std::pair<enum KnownPropertyIndex,EffectiveValue> *v71; // rcx
  KnownPropertyIndex v72; // r10
  bool m_bool; // bl
  CCoreServices **p_m_coreServices; // rax
  bool IsPropertyDefault; // al
  CUIElement_vtbl *v76; // rcx
  bool v77; // bl
  HRESULT (__fastcall *v78)(CDependencyObject *, const SetValueParams *); // rax
  containers::vector_map<enum KnownPropertyIndex,EffectiveValue,std::less<void>,std::allocator<std::pair<enum KnownPropertyIndex,EffectiveValue> > > *Myval2; // rax
  unsigned __int64 v80; // rcx
  _OWORD *v81; // rcx
  _OWORD *v82; // rdi
  _OWORD *v83; // rax
  HSTRING StringRawBuffer; // rax
  UINT32 v85; // edx
  int v86; // eax
  __int64 v87; // rdx
  unsigned int v88; // eax
  CValueDetails::Value v89; // rbx
  unsigned int v90; // ebx
  std::pair<enum KnownPropertyIndex,EffectiveValue> *Myfirst; // rcx
  KnownPropertyIndex v92; // r10
  unsigned __int64 v93; // r8
  _OWORD *v94; // rcx
  _OWORD *v95; // rdi
  _OWORD *v96; // rax
  unsigned int v97; // ebx
  unsigned int v98; // eax
  HRESULT DefaultInheritedPropertyValue; // eax
  unsigned int v100; // edi
  __int64 v101; // rcx
  unsigned int v102; // eax
  int v103; // eax
  unsigned int v104; // eax
  _QWORD *FailFast; // rcx
  _QWORD *v106; // rdi
  unsigned int v107; // eax
  KnownTypeIndex m_typeHandle; // bx
  HRESULT ValueInternal; // eax
  unsigned int v110; // edi
  unsigned int bits; // eax
  unsigned int v112; // ebx
  KnownTypeIndex v113; // ax
  unsigned int v114; // eax
  HRESULT v115; // eax
  InheritedProperties *v116; // r8
  char v117; // al
  __int64 v118; // r8
  InheritedProperties *m_pInheritedProperties; // r8
  char v120; // al
  __int64 v121; // r8
  KnownTypeIndex v122; // cx
  unsigned int v123; // eax
  unsigned int pcStowedExceptions[2]; // [rsp+30h] [rbp-89h] BYREF
  bool success; // [rsp+38h] [rbp-81h] BYREF
  HSTRING string; // [rsp+40h] [rbp-79h] BYREF
  _STOWED_EXCEPTION_INFORMATION_V2 **pppStowedExceptions; // [rsp+48h] [rbp-71h] BYREF
  xstring_ptr v128[2]; // [rsp+50h] [rbp-69h] BYREF
  CREATEPARAMETERS v129; // [rsp+60h] [rbp-59h] BYREF
  _QWORD v130[3]; // [rsp+88h] [rbp-31h] BYREF
  int v131; // [rsp+A0h] [rbp-19h]
  __int64 v132; // [rsp+A8h] [rbp-11h]
  CValue outValue; // [rsp+B0h] [rbp-9h] BYREF
  __int64 v134; // [rsp+E8h] [rbp+2Fh]

  v5 = value;
  v6 = this;
  if ( dp->m_nIndex == UIElement_TransitionTarget )
  {
    m_ptr = this->m_sharedState.m_ptr;
    m_coreServices = m_ptr->m_value.m_coreServices;
    if ( m_ptr->m_value.m_coreServices->m_allowTransitionTargetsToBeCreated )
    {
      if ( CDependencyObject::IsPropertyDefaultByIndex(this, UIElement_TransitionTarget) )
      {
        DefaultValueObject = CDependencyProperty::CreateDefaultValueObject(dp, m_coreServices, v5);
        v32 = DefaultValueObject;
        if ( DefaultValueObject < 0 )
        {
          OnFailure_2990_(DefaultValueObject);
          return v32;
        }
        v129.m_value.m_value = (CValueDetails::Value)dp;
        v129.m_pCore = (CCoreServices *)v128;
        v33 = v6->__vftable;
        v129.m_value.m_flags = (CValueDetails::Flags)v5;
        *(_OWORD *)&v128[0].m_encodedStorage.Storage = 0;
        LODWORD(v129.m_spServiceProviderContext._Ptr) = 0;
        SetValue = v33->SetValue;
        v129.m_spServiceProviderContext._Rep = 0;
        v35 = SetValue(v6, (const SetValueParams *)&v129);
        LODWORD(this) = v128[1].m_encodedStorage.Storage;
        v36 = v35;
        if ( v128[1].m_encodedStorage.RuntimeStringHandleMarker )
          std::_Ref_count_base::_Decref((std::_Ref_count_base *)v128[1].m_encodedStorage.Storage);
        if ( v36 < 0 )
        {
          OnFailure_2990_(v36);
          return (unsigned int)v36;
        }
      }
    }
  }
  m_flags = dp->m_flags;
  v134 = v3;
  if ( (m_flags & 0x288) == 0x288 )
  {
    ValueInternal = CDependencyObject::GetValueInternal(v6, dp, v5);
    v110 = ValueInternal;
    if ( ValueInternal < 0 )
    {
      OnFailure_2990_(ValueInternal);
      OnFailure_2990_(v110);
      return v110;
    }
    return 0;
  }
  if ( (m_flags & 0x80u) == 0 || (m_flags & 0x200) != 0 )
  {
    if ( (m_flags & 1) == 0 )
    {
      if ( (m_flags & 0x100) != 0 )
      {
        DefaultValue = c_aDependencyPropertyRuntimeData[(unsigned __int16)dp->m_nIndex].m_pfn(v6, 0, 0, 0, v5);
        v11 = DefaultValue;
        if ( DefaultValue >= 0 )
          goto LABEL_44;
        goto LABEL_91;
      }
      m_nIndex = (unsigned __int16)dp->m_nIndex;
      if ( (m_flags & 0x200) != 0 )
      {
        LOBYTE(value) = 1;
        if ( c_aDependencyPropertyRuntimeData[m_nIndex].m_cgpfn(v6, dp, (bool)value) < 0 )
          goto LABEL_233;
        m_flags = dp->m_flags;
        if ( (m_flags & 0x100) != 0 )
          LODWORD(this) = 0;
        else
          LODWORD(this) = c_aDependencyPropertyRuntimeData[(unsigned __int16)dp->m_nIndex].m_nOffset;
        v9 = (const CValue *)(*(char **)((char *)&v6->__vftable + (unsigned __int16)this)
                            + c_aDependencyPropertyRuntimeData[(unsigned __int16)dp->m_nIndex].m_nGroupOffset);
      }
      else
      {
        v9 = (const CValue *)((char *)v6 + c_aDependencyPropertyRuntimeData[m_nIndex].m_nOffset);
      }
      *(_QWORD *)pcStowedExceptions = v9;
      if ( v9 )
      {
        m_nPropertyTypeIndex = (unsigned __int16)dp->m_nPropertyTypeIndex;
        v11 = 0;
        if ( (_DWORD)m_nPropertyTypeIndex == 140 )
        {
          if ( (m_flags & 0x10000) != 0 )
          {
LABEL_92:
            v53 = v9->m_value.m_any[0];
            CValue::ReleaseAndReset(v5);
            v5->m_flags.m_state.m_asOne &= 0xFFFFFFC8;
            v5->m_flags.m_state.m_asOne |= 0x48u;
            v5->m_value.m_any[0] = v53;
          }
          else
          {
            v128[0] = (xstring_ptr)v9->m_value;
            Storage = (unsigned int)v128[0].m_encodedStorage.Storage;
            CValue::ReleaseAndReset(v5);
            v5->m_flags.m_state.m_asOne &= 0xFFFFFFC9;
            v5->m_flags.m_state.m_asOne |= 0x49u;
            RuntimeStringHandleMarker_high = HIDWORD(v128[0].m_encodedStorage.RuntimeStringHandleMarker);
            v5->m_value.m_any[0] = Storage;
            v5->m_value.m_any[1] = RuntimeStringHandleMarker_high;
          }
        }
        else
        {
          if ( (_DWORD)m_nPropertyTypeIndex == 71 )
            goto LABEL_70;
          if ( (unsigned int)m_nPropertyTypeIndex <= 0x10D )
          {
            if ( (_DWORD)m_nPropertyTypeIndex != 269 )
            {
              switch ( dp->m_nPropertyTypeIndex )
              {
                case DateTime:
                  goto LABEL_44;
                case Object:
                  if ( (dp->m_flags & 1) != 0 )
                  {
                    Myval2 = v6->m_pValueTable._Mypair._Myval2;
                    if ( !Myval2 )
                      goto LABEL_155;
                    Myfirst = Myval2->m_data.m_vector._Mypair._Myval2._Myfirst;
                    v92 = dp->m_nIndex;
                    v93 = Myval2->m_data.m_vector._Mypair._Myval2._Mylast
                        - Myval2->m_data.m_vector._Mypair._Myval2._Myfirst;
                    while ( (__int64)v93 > 0 )
                    {
                      if ( (unsigned int)Myfirst[v93 >> 1].first < (unsigned __int16)v92 )
                      {
                        Myfirst += (v93 >> 1) + 1;
                        v93 += -1LL - (v93 >> 1);
                      }
                      else
                      {
                        v93 >>= 1;
                      }
                    }
                    if ( Myfirst == Myval2->m_data.m_vector._Mypair._Myval2._Mylast
                      || (unsigned __int16)v92 < (unsigned int)Myfirst->first
                      || (Myfirst->second.value.m_flags.m_state.m_asOne & 0x100) == 0 )
                    {
                      goto LABEL_155;
                    }
                  }
                  else
                  {
                    if ( (dp->m_flags & 0x288) != 0x288 )
                    {
                      m_nPropertySlotCount = c_aTypeProperties[(unsigned __int16)v6->GetTypeIndex(v6)].m_nPropertySlotCount;
                      v49 = c_aPropertySlot[(unsigned __int16)dp->m_nIndex];
                      if ( (unsigned __int8)v49 >= m_nPropertySlotCount )
                        goto LABEL_90;
                      if ( m_nPropertySlotCount <= 0x20u )
                      {
                        bits = v6->m_valid.bits;
                        v52 = _bittest((const int *)&bits, v49);
                      }
                      else
                      {
                        v50.pointer = (unsigned int *)v6->m_valid;
                        if ( !v50.pointer )
                          goto LABEL_155;
                        v51 = v50.pointer[(unsigned __int64)c_aPropertySlot[(unsigned __int16)dp->m_nIndex] >> 5];
                        v52 = _bittest((const int *)&v51, v49 & 0x1F);
                      }
                      if ( v52 )
                        goto LABEL_90;
LABEL_155:
                      CValue::ReleaseAndReset(v5);
                      v5->m_flags.m_state.m_asOne &= 0xFFFFFFD8;
                      v5->m_flags.m_state.m_asOne |= 0x58u;
                      v5->m_value = 0;
                      goto LABEL_44;
                    }
                    m_pInheritedProperties = v6->m_pInheritedProperties;
                    if ( !m_pInheritedProperties )
                      goto LABEL_155;
                    if ( m_pInheritedProperties->m_pWriter != v6 )
                      goto LABEL_155;
                    v120 = ToPropertyNumber(dp->m_nIndex);
                    if ( ((1LL << v120) & *(_QWORD *)(v121 + 104)) == 0 )
                      goto LABEL_155;
                  }
LABEL_90:
                  DefaultValue = CValue::CopyConverted(v5, v9);
                  v11 = DefaultValue;
                  if ( DefaultValue >= 0 )
                    goto LABEL_44;
                  goto LABEL_91;
                case Float:
                  goto LABEL_92;
                case TypeName:
                  m_typeHandle = v9->m_value.m_typeHandle;
                  CValue::ReleaseAndReset(v5);
                  v5->m_flags.m_state.m_asOne &= 0xFFFFFFDC;
                  v5->m_flags.m_state.m_asOne |= 0x5Cu;
                  v5->m_value.m_typeHandle = m_typeHandle;
                  goto LABEL_44;
                case Boolean:
                  m_bool = v9->m_value.m_bool;
                  CValue::ReleaseAndReset(v5);
                  v5->m_flags.m_state.m_asOne &= 0xFFFFFFC2;
                  v5->m_flags.m_state.m_asOne |= 0x42u;
                  v5->m_value.m_bool = m_bool;
                  goto LABEL_44;
                case Color:
                  v97 = v9->m_value.m_any[0];
                  CValue::ReleaseAndReset(v5);
                  v5->m_flags.m_state.m_asOne &= 0xFFFFFFCF;
                  v5->m_flags.m_state.m_asOne |= 0x4Fu;
                  v5->m_value.m_any[0] = v97;
                  goto LABEL_44;
                case CornerRadius:
                  CValue::ReleaseAndReset(v5);
                  v5->m_flags.m_state.m_asOne = v5->m_flags.m_state.m_asOne & 0xFFFFFF80 | 0x15;
                  v5->m_value.m_any[1] = pcStowedExceptions[1];
                  v5->m_value.m_any[0] = (unsigned int)v9;
                  goto LABEL_44;
                case FontWeight:
                  goto LABEL_228;
                case GridLength:
                  CValue::ReleaseAndReset(v5);
                  v5->m_flags.m_state.m_asOne = v5->m_flags.m_state.m_asOne & 0xFFFFFF80 | 0x14;
                  v5->m_value.m_any[1] = pcStowedExceptions[1];
                  v5->m_value.m_any[0] = (unsigned int)v9;
                  goto LABEL_44;
                case Int32:
                  v90 = v9->m_value.m_any[0];
                  CValue::ReleaseAndReset(v5);
                  v5->m_flags.m_state.m_asOne &= 0xFFFFFFC4;
                  v5->m_flags.m_state.m_asOne |= 0x44u;
                  v5->m_value.m_any[0] = v90;
                  goto LABEL_44;
                case Point:
                  CValue::ReleaseAndReset(v5);
                  v5->m_flags.m_state.m_asOne = v5->m_flags.m_state.m_asOne & 0xFFFFFF80 | 0x10;
                  v5->m_value.m_any[1] = pcStowedExceptions[1];
                  v5->m_value.m_any[0] = (unsigned int)v9;
                  goto LABEL_44;
                case Rect:
                  CValue::ReleaseAndReset(v5);
                  v5->m_flags.m_state.m_asOne = v5->m_flags.m_state.m_asOne & 0xFFFFFF80 | 0x12;
                  v5->m_value.m_any[1] = pcStowedExceptions[1];
                  v5->m_value.m_any[0] = (unsigned int)v9;
                  goto LABEL_44;
                case Size:
                  CValue::ReleaseAndReset(v5);
                  v5->m_flags.m_state.m_asOne = v5->m_flags.m_state.m_asOne & 0xFFFFFF80 | 0x11;
                  v5->m_value.m_any[1] = pcStowedExceptions[1];
                  v5->m_value.m_any[0] = (unsigned int)v9;
                  goto LABEL_44;
                default:
                  goto LABEL_58;
              }
            }
LABEL_70:
            m_value = (unsigned __int64)v9->m_value;
            if ( (m_value & 1) != 0 )
            {
              v103 = WindowsDuplicateString((HSTRING)(m_value & 0xFFFFFFFFFFFFFFFEuLL), &string);
              if ( v103 < 0 )
              {
                OnFailure_2990_(v103);
                goto LABEL_77;
              }
            }
            else
            {
              if ( !m_value || (v43 = *(_DWORD *)(m_value + 8), (v43 & 0x40000000) == 0) )
              {
LABEL_78:
                v128[0].m_encodedStorage.RuntimeStringHandleMarker = m_value;
                CValue::ReleaseAndReset(v5);
                v5->m_flags.m_state.m_asOne &= 0xFFFFFFCE;
                v5->m_flags.m_state.m_asOne |= 0x4Eu;
                if ( (m_value & 1) != 0 )
                {
                  v86 = WindowsDuplicateString((HSTRING)(m_value & 0xFFFFFFFFFFFFFFFEuLL), &string);
                  if ( v86 < 0 )
                    goto LABEL_168;
                }
                else
                {
                  if ( !m_value )
                    goto LABEL_81;
                  v47 = *(_DWORD *)(m_value + 8);
                  if ( (v47 & 0x40000000) == 0 )
                    goto LABEL_81;
                  pcStowedExceptions[0] = 0;
                  StringRawBuffer = *(HSTRING *)m_value;
                  if ( v47 < 0 )
                  {
                    StringRawBuffer = (HSTRING)WindowsGetStringRawBuffer(*(HSTRING *)m_value, pcStowedExceptions);
                    v85 = pcStowedExceptions[0];
                  }
                  else
                  {
                    v85 = v47 & 0x3FFFFFFF;
                    pcStowedExceptions[0] = v85;
                  }
                  v86 = WindowsCreateString((PCNZWCH)StringRawBuffer, v85, &string);
                  if ( v86 < 0 )
                  {
LABEL_168:
                    OnFailure_2990_(v86);
                    pppStowedExceptions = 0;
                    pcStowedExceptions[0] = 0;
                    TraceForFailFast(-2147418113);
                    OnNewFailureEncountered(-2147418113, 0, 0);
                    GetStowedExceptionsForFailFast(&pppStowedExceptions, pcStowedExceptions);
                    RoFailFastWithErrorContextInternal2(-2147418113, pcStowedExceptions[0], pppStowedExceptions);
                    LODWORD(m_value) = (_DWORD)string;
                    goto LABEL_82;
                  }
                }
                m_value = (unsigned __int64)string | 1;
LABEL_81:
                string = (HSTRING)m_value;
LABEL_82:
                v5->m_value.m_any[1] = HIDWORD(string);
                v5->m_value.m_any[0] = m_value;
                xstring_ptr::~xstring_ptr(v128);
                goto LABEL_44;
              }
              pcStowedExceptions[0] = 0;
              v44 = *(const wchar_t **)m_value;
              if ( v43 < 0 )
              {
                v44 = WindowsGetStringRawBuffer(*(HSTRING *)m_value, pcStowedExceptions);
                v45 = pcStowedExceptions[0];
              }
              else
              {
                v45 = v43 & 0x3FFFFFFF;
                pcStowedExceptions[0] = v45;
              }
              v46 = WindowsCreateString(v44, v45, &string);
              if ( v46 < 0 )
              {
                OnFailure_2990_(v46);
LABEL_77:
                pppStowedExceptions = 0;
                pcStowedExceptions[0] = 0;
                TraceForFailFast(-2147418113);
                OnNewFailureEncountered(-2147418113, 0, 0);
                GetStowedExceptionsForFailFast(&pppStowedExceptions, pcStowedExceptions);
                RoFailFastWithErrorContextInternal2(-2147418113, pcStowedExceptions[0], pppStowedExceptions);
                m_value = (unsigned __int64)string;
                goto LABEL_78;
              }
            }
            m_value = (unsigned __int64)string | 1;
            goto LABEL_78;
          }
          if ( (_DWORD)m_nPropertyTypeIndex == 292 )
          {
            CValue::ReleaseAndReset(v5);
            v5->m_flags.m_state.m_asOne = v5->m_flags.m_state.m_asOne & 0xFFFFFF80 | 0x13;
            v5->m_value.m_any[1] = pcStowedExceptions[1];
            v5->m_value.m_any[0] = (unsigned int)v9;
          }
          else if ( (_DWORD)m_nPropertyTypeIndex == 418
                 || (_DWORD)m_nPropertyTypeIndex == 454
                 || (_DWORD)m_nPropertyTypeIndex == 649 )
          {
            v89 = v9->m_value;
            CValue::ReleaseAndReset(v5);
            v5->m_flags.m_state.m_asOne &= ~0x20u;
            v5->m_flags.m_state.m_asOne |= 0x5Fu;
            v5->m_value = v89;
            CValueDetails::ValueStores::RefCounted<31,Flyweight::PropertyValueObjectBase>::AddRef(v5);
          }
          else
          {
LABEL_58:
            if ( (unsigned __int16)m_nPropertyTypeIndex >= 0x43Cu )
            {
              EnterCriticalSection(&g_csStatic);
              v37 = DirectUI::DynamicMetadataStorage::GetInstance()->m_customTypesCache._Mypair._Myval2._Myfirst[(unsigned int)(m_nPropertyTypeIndex - 1084)]._Mypair._Myval2;
              LeaveCriticalSection(&g_csStatic);
            }
            else
            {
              v37 = (CCustomClassInfo *)(&std::nothrow + 8 * m_nPropertyTypeIndex + 15053904);
            }
            if ( v37->m_nIndex == Enumerated || (v37->m_flags & 0x800) != 0 )
            {
              if ( (DirectUI::MetadataAPI::GetClassInfoByIndex(dp->m_nPropertyTypeIndex)->m_flags & 0x20000) != 0 )
              {
                v122 = dp->m_nPropertyTypeIndex;
                LOWORD(pcStowedExceptions[0]) = v9->m_value.m_enum8.m_value;
                HIWORD(pcStowedExceptions[0]) = DirectUI::MetadataAPI::GetClassInfoByIndex(v122)->m_nIndex;
                CValue::ReleaseAndReset(v5);
                v5->m_flags.m_state.m_asOne &= 0xFFFFFFE1;
                v123 = pcStowedExceptions[0];
                v5->m_flags.m_state.m_asOne |= 0x61u;
                v5->m_value.m_any[0] = v123;
              }
              else
              {
LABEL_228:
                v112 = v9->m_value.m_any[0];
                LODWORD(string) = v112;
                HIDWORD(string) = (unsigned __int16)CPropertyBase::GetPropertyType(&dp->CPropertyBase)->m_nIndex;
                CValue::ReleaseAndReset(v5);
                v5->m_flags.m_state.m_asOne &= 0xFFFFFFC3;
                v5->m_flags.m_state.m_asOne |= 0x43u;
                v5->m_value.m_any[1] = HIDWORD(string);
                v5->m_value.m_any[0] = v112;
              }
            }
            else
            {
              v38 = v9->m_value;
              v39 = HIDWORD(*(_QWORD *)&v38);
              if ( *(_QWORD *)&v38 || !CDependencyProperty::IsOnDemandProperty(dp) )
              {
                CValue::ReleaseAndReset(v5);
                v5->m_flags.m_state.m_asOne &= 0xFFFFFFD8;
                v5->m_flags.m_state.m_asOne |= 0x58u;
                v5->m_value = v38;
                if ( v38.m_any[0] | (unsigned __int64)(v39 << 32) )
                {
                  CDependencyObject::AddRef((CDependencyObject *)(v38.m_any[0] | (unsigned __int64)(v39 << 32)));
                  goto LABEL_44;
                }
              }
              else
              {
                p_m_coreServices = &v6->m_sharedState.m_ptr->m_value.m_coreServices;
                v129.m_value.m_value = 0;
                v129.m_value.m_flags = 0;
                v129.m_spServiceProviderContext = 0;
                v129.m_pCore = *p_m_coreServices;
                v11 = CDependencyProperty::CreateDefaultValueObject(dp, v129.m_pCore, v5);
                if ( v11 >= 0 )
                {
                  IsPropertyDefault = CDependencyObject::IsPropertyDefault(v6, dp);
                  v76 = v6->__vftable;
                  v77 = IsPropertyDefault;
                  v130[0] = dp;
                  v130[1] = v5;
                  v130[2] = v128;
                  v78 = v76->SetValue;
                  *(_OWORD *)&v128[0].m_encodedStorage.Storage = 0;
                  v131 = 0;
                  v132 = 0;
                  v11 = v78(v6, (const SetValueParams *)v130);
                  if ( v128[1].m_encodedStorage.RuntimeStringHandleMarker )
                    std::_Ref_count_base::_Decref((std::_Ref_count_base *)v128[1].m_encodedStorage.Storage);
                  if ( v77 )
                  {
                    if ( CQuirksMode2::QuirkPreRS2GetEffectiveValueField_ObjectIgnoreFailedLookup() )
                      v11 = 0;
                    CDependencyObject::SetPropertyIsDefault(v6, dp);
                  }
                  if ( v11 < 0 )
                  {
                    CValue::ReleaseAndReset(v5);
                    v5->m_flags.m_state.m_asOne &= 0xFFFFFFD8;
                    v5->m_flags.m_state.m_asOne |= 0x58u;
                    v5->m_value = 0;
                  }
                }
                CREATEPARAMETERS::~CREATEPARAMETERS(&v129);
              }
              if ( v11 < 0 )
                OnFailure_2990_(v11);
            }
          }
        }
LABEL_44:
        if ( v11 < 0 )
        {
          OnFailure_2990_(v11);
          OnFailure_2990_(v11);
          return (unsigned int)v11;
        }
        return 0;
      }
LABEL_233:
      v11 = -2147467261;
      OnNewFailure_1172_((HRESULT)this);
      goto LABEL_44;
    }
    v12 = v6->m_pValueTable._Mypair._Myval2;
    if ( !v12 )
      goto LABEL_271;
    v13 = v12->m_data.m_vector._Mypair._Myval2._Myfirst;
    v14 = dp->m_nIndex;
    v15 = v12->m_data.m_vector._Mypair._Myval2._Mylast - v12->m_data.m_vector._Mypair._Myval2._Myfirst;
    while ( (__int64)v15 > 0 )
    {
      if ( (unsigned int)v13[v15 >> 1].first < (unsigned __int16)v14 )
      {
        v13 += (v15 >> 1) + 1;
        v15 += -1LL - (v15 >> 1);
      }
      else
      {
        v15 >>= 1;
      }
    }
    if ( v13 == v12->m_data.m_vector._Mypair._Myval2._Mylast || (unsigned __int16)v14 < (unsigned int)v13->first )
    {
LABEL_271:
      if ( (m_flags & 0x40) == 0 || CDependencyProperty::IsCreateOnDemandDisabledByQuirk(dp->m_nIndex) )
      {
        DefaultValue = CDependencyObject::GetDefaultValue(v6, dp, v5);
        v11 = DefaultValue;
        if ( DefaultValue >= 0 )
        {
          v11 = 0;
          goto LABEL_44;
        }
      }
      else
      {
        DefaultValue = CDependencyProperty::CreateDefaultValueObject(
                         dp,
                         v6->m_sharedState.m_ptr->m_value.m_coreServices,
                         v5);
        v11 = DefaultValue;
        if ( DefaultValue >= 0 )
        {
          DefaultValue = CDependencyObject::SetValue(v6, dp, v5);
          v11 = DefaultValue;
          if ( DefaultValue >= 0 )
          {
            CDependencyObject::SetPropertyIsDefault(v6, dp);
            goto LABEL_43;
          }
        }
      }
LABEL_91:
      OnFailure_2990_(DefaultValue);
      goto LABEL_44;
    }
    p_value = &v13->second.value;
    if ( v5 == (CValue *)&v13->second )
    {
LABEL_43:
      v11 = 0;
      goto LABEL_44;
    }
    CValue::ReleaseAndReset(v5);
    v17 = p_value->m_flags.m_state.m_asOne & 0x3F;
    if ( !v17 )
      goto LABEL_42;
    if ( v17 != 24 )
    {
      if ( v17 == 8 )
      {
        v5->m_value.m_any[0] = p_value->m_value.m_any[0];
        v5->m_flags.m_state.m_asOne &= 0xFFFFFFC8;
        v5->m_flags.m_state.m_asOne |= 0x48u;
      }
      else
      {
        if ( v17 != 33 )
        {
          switch ( v17 )
          {
            case 1:
              v5->m_flags.m_state.m_asOne &= 0xFFFFFFC1;
              v5->m_flags.m_state.m_asOne |= 0x41u;
              goto LABEL_42;
            case 2:
              v18 = p_value->m_value.m_bool;
              v5->m_flags.m_state.m_asOne &= 0xFFFFFFC2;
              v5->m_flags.m_state.m_asOne |= 0x42u;
              v5->m_value.m_bool = v18;
              goto LABEL_42;
            case 3:
              v5->m_value.m_any[0] = p_value->m_value.m_any[0];
              v5->m_value.m_any[1] = p_value->m_value.m_any[1];
              v5->m_flags.m_state.m_asOne &= 0xFFFFFFC3;
              v5->m_flags.m_state.m_asOne |= 0x43u;
              goto LABEL_42;
            case 4:
              v98 = p_value->m_value.m_any[0];
              v5->m_flags.m_state.m_asOne &= 0xFFFFFFC4;
              v5->m_flags.m_state.m_asOne |= 0x44u;
              v5->m_value.m_any[0] = v98;
              goto LABEL_42;
            case 5:
              v114 = p_value->m_value.m_any[0];
              v5->m_flags.m_state.m_asOne &= 0xFFFFFFC5;
              v5->m_flags.m_state.m_asOne |= 0x45u;
              v5->m_value.m_any[0] = v114;
              goto LABEL_42;
            case 6:
              v5->m_value.m_any[0] = p_value->m_value.m_any[0];
              v5->m_value.m_any[1] = p_value->m_value.m_any[1];
              v5->m_flags.m_state.m_asOne &= 0xFFFFFFC6;
              v5->m_flags.m_state.m_asOne |= 0x46u;
              goto LABEL_42;
            case 7:
              v5->m_value.m_any[0] = p_value->m_value.m_any[0];
              v5->m_value.m_any[1] = p_value->m_value.m_any[1];
              v5->m_flags.m_state.m_asOne &= 0xFFFFFFC7;
              v5->m_flags.m_state.m_asOne |= 0x47u;
              goto LABEL_42;
            case 9:
              v5->m_value.m_any[0] = p_value->m_value.m_any[0];
              v5->m_value.m_any[1] = p_value->m_value.m_any[1];
              v5->m_flags.m_state.m_asOne &= 0xFFFFFFC9;
              v5->m_flags.m_state.m_asOne |= 0x49u;
              goto LABEL_42;
            case 10:
              CValueDetails::ValueStores::Array<11,float>::Copy(v5, p_value);
              v5->m_flags.m_state.m_asOne &= 0xFFFFFFCA;
              v5->m_flags.m_state.m_asOne |= 0x4Au;
              v5->m_flags.m_count = p_value->m_flags.m_count;
              goto LABEL_42;
            case 11:
              CValueDetails::ValueStores::Array<11,float>::Copy(v5, p_value);
              v5->m_flags.m_state.m_asOne &= 0xFFFFFFCB;
              v5->m_flags.m_state.m_asOne |= 0x4Bu;
              v5->m_flags.m_count = p_value->m_flags.m_count;
              goto LABEL_42;
            case 12:
              CValueDetails::ValueStores::Array<12,double>::Copy(v5, p_value);
              v5->m_flags.m_state.m_asOne &= 0xFFFFFFCC;
              v5->m_flags.m_state.m_asOne |= 0x4Cu;
              v5->m_flags.m_count = p_value->m_flags.m_count;
              goto LABEL_42;
            case 13:
              CValueDetails::ValueStores::Array<12,double>::Copy(v5, p_value);
              v5->m_flags.m_state.m_asOne &= 0xFFFFFFCD;
              v5->m_flags.m_state.m_asOne |= 0x4Du;
              v5->m_flags.m_count = p_value->m_flags.m_count;
              goto LABEL_42;
            case 14:
              v80 = (unsigned __int64)p_value->m_value;
              if ( (*(_QWORD *)&p_value->m_value & 1) != 0 )
              {
                if ( WindowsDuplicateString((HSTRING)(v80 & 0xFFFFFFFFFFFFFFFEuLL), (HSTRING *)&pppStowedExceptions) < 0 )
                {
                  string = 0;
                  pcStowedExceptions[0] = 0;
                  TraceForFailFast(-2147418113);
                  OnNewFailureEncountered(-2147418113, 0, 0);
                  GetStowedExceptionsForFailFast((_STOWED_EXCEPTION_INFORMATION_V2 ***)&string, pcStowedExceptions);
                  RoFailFastWithErrorContextInternal2(
                    -2147418113,
                    pcStowedExceptions[0],
                    (struct _STOWED_EXCEPTION_INFORMATION_V2 **const)string);
                }
                v80 = (unsigned __int64)pppStowedExceptions | 1;
              }
              v5->m_value = (CValueDetails::Value)v80;
              v5->m_flags.m_state.m_asOne &= 0xFFFFFFCE;
              v5->m_flags.m_state.m_asOne |= 0x4Eu;
              goto LABEL_42;
            case 15:
              v107 = p_value->m_value.m_any[0];
              v5->m_flags.m_state.m_asOne &= 0xFFFFFFCF;
              v5->m_flags.m_state.m_asOne |= 0x4Fu;
              v5->m_value.m_any[0] = v107;
              goto LABEL_42;
            case 16:
              FailFast = 0;
              v106 = (_QWORD *)p_value->m_value;
              if ( p_value->m_value )
              {
                FailFast = XcpAllocation::OSMemoryAllocateFailFast(8u);
                if ( FailFast )
                  *FailFast = 0;
                else
                  FailFast = 0;
                *FailFast = *v106;
              }
              v5->m_value = (CValueDetails::Value)FailFast;
              v5->m_flags.m_state.m_asOne &= 0xFFFFFFD0;
              v5->m_flags.m_state.m_asOne |= 0x50u;
              goto LABEL_42;
            case 17:
              CValueDetails::ValueStores::Reference<17,XSIZEF>::Copy(v5, p_value);
              v5->m_flags.m_state.m_asOne &= 0xFFFFFFD1;
              v5->m_flags.m_state.m_asOne |= 0x51u;
              goto LABEL_42;
            case 18:
              v24 = CValueDetails::Handlers::ConvertAndCopy::Copy<18>(v5, p_value);
              goto LABEL_41;
            case 19:
              v81 = 0;
              v82 = (_OWORD *)p_value->m_value;
              if ( p_value->m_value )
              {
                v83 = XcpAllocation::OSMemoryAllocateFailFast(0x10u);
                v81 = v83;
                if ( v83 )
                  *v83 = 0;
                else
                  v81 = 0;
                *v81 = *v82;
              }
              v5->m_value = (CValueDetails::Value)v81;
              v5->m_flags.m_state.m_asOne &= 0xFFFFFFD3;
              v5->m_flags.m_state.m_asOne |= 0x53u;
              goto LABEL_42;
            case 20:
              v24 = CValueDetails::Handlers::ConvertAndCopy::Copy<20>(v5, p_value);
              goto LABEL_41;
            case 21:
              v94 = 0;
              v95 = (_OWORD *)p_value->m_value;
              if ( p_value->m_value )
              {
                v96 = XcpAllocation::OSMemoryAllocateFailFast(0x10u);
                v94 = v96;
                if ( v96 )
                  *v96 = 0;
                else
                  v94 = 0;
                *v94 = *v95;
              }
              v5->m_value = (CValueDetails::Value)v94;
              v5->m_flags.m_state.m_asOne &= 0xFFFFFFD5;
              v5->m_flags.m_state.m_asOne |= 0x55u;
              goto LABEL_42;
            case 22:
              v5->m_value.m_any[0] = p_value->m_value.m_any[0];
              v5->m_value.m_any[1] = p_value->m_value.m_any[1];
              v5->m_flags.m_state.m_asOne &= 0xFFFFFFD6;
              v5->m_flags.m_state.m_asOne |= 0x56u;
              goto LABEL_42;
            case 23:
              v5->m_value.m_any[0] = p_value->m_value.m_any[0];
              v5->m_value.m_any[1] = p_value->m_value.m_any[1];
              v5->m_flags.m_state.m_asOne &= 0xFFFFFFD7;
              v5->m_flags.m_state.m_asOne |= 0x57u;
              goto LABEL_42;
            case 25:
              v5->m_value.m_any[0] = p_value->m_value.m_any[0];
              v5->m_value.m_any[1] = p_value->m_value.m_any[1];
              v5->m_flags.m_state.m_asOne &= 0xFFFFFFD9;
              v5->m_flags.m_state.m_asOne |= 0x59u;
              goto LABEL_42;
            case 26:
              v5->m_value.m_any[0] = p_value->m_value.m_any[0];
              v5->m_value.m_any[1] = p_value->m_value.m_any[1];
              CValueDetails::ValueStores::RefCounted<27,IInspectable>::AddRef(v5);
              v5->m_flags.m_state.m_asOne &= 0xFFFFFFDA;
              v5->m_flags.m_state.m_asOne |= 0x5Au;
              goto LABEL_42;
            case 27:
              v87 = p_value->m_value.m_any[0];
              v5->m_value.m_any[0] = v87;
              v88 = p_value->m_value.m_any[1];
              v5->m_value.m_any[1] = v88;
              if ( v87 | ((unsigned __int64)v88 << 32) )
                (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)(v87 | ((unsigned __int64)v88 << 32)) + 8LL))(v87 | ((unsigned __int64)v88 << 32));
              v5->m_flags.m_state.m_asOne &= 0xFFFFFFDB;
              v5->m_flags.m_state.m_asOne |= 0x5Bu;
              goto LABEL_42;
            case 28:
              v113 = p_value->m_value.m_typeHandle;
              v5->m_flags.m_state.m_asOne &= 0xFFFFFFDC;
              v5->m_flags.m_state.m_asOne |= 0x5Cu;
              v5->m_value.m_typeHandle = v113;
              goto LABEL_42;
            case 29:
              v101 = p_value->m_value.m_any[0];
              v5->m_value.m_any[0] = v101;
              v102 = p_value->m_value.m_any[1];
              v5->m_value.m_any[1] = v102;
              if ( v101 | ((unsigned __int64)v102 << 32) )
                ++*(_DWORD *)(v101 | ((unsigned __int64)v102 << 32));
              v5->m_flags.m_state.m_asOne &= 0xFFFFFFDD;
              v5->m_flags.m_state.m_asOne |= 0x5Du;
              goto LABEL_42;
            case 30:
              v5->m_value.m_any[0] = p_value->m_value.m_any[0];
              v5->m_value.m_any[1] = p_value->m_value.m_any[1];
              v5->m_flags.m_state.m_asOne &= 0xFFFFFFDE;
              v5->m_flags.m_state.m_asOne |= 0x5Eu;
              goto LABEL_42;
            case 31:
              v115 = CValueConvert::EnsureValueObjectUnboxed<CValue>(p_value, v5);
              v24 = v115;
              if ( v115 >= 0 )
                goto LABEL_40;
              OnFailure_2990_(v115);
              break;
            case 32:
              v5->m_value.m_any[0] = p_value->m_value.m_any[0];
              v5->m_value.m_any[1] = p_value->m_value.m_any[1];
              v5->m_flags.m_state.m_asOne &= 0xFFFFFFE0;
              v5->m_flags.m_state.m_asOne |= 0x60u;
              goto LABEL_42;
            default:
              string = 0;
              pcStowedExceptions[0] = 0;
              TraceForFailFast(-2147418113);
              OnNewFailureEncountered(-2147418113, 0, 0);
              GetStowedExceptionsForFailFast((_STOWED_EXCEPTION_INFORMATION_V2 ***)&string, pcStowedExceptions);
              RoFailFastWithErrorContextInternal2(
                -2147418113,
                pcStowedExceptions[0],
                (struct _STOWED_EXCEPTION_INFORMATION_V2 **const)string);
              goto LABEL_42;
          }
          goto LABEL_41;
        }
        v54 = p_value->m_value.m_any[0];
        v5->m_flags.m_state.m_asOne &= 0xFFFFFFE1;
        v5->m_flags.m_state.m_asOne |= 0x61u;
        v5->m_value.m_any[0] = v54;
      }
LABEL_42:
      v27.0 = ($AE0720DD29EBB950835C0AB6A5612248)v5->m_flags.m_state;
      v5->m_flags.m_state.m_asOne = *(_BYTE *)&v27.0 & 0x7F;
      v5->m_flags.m_state.m_asOne = p_value->m_flags.m_state.m_asOne
                                  ^ (p_value->m_flags.m_state.m_asOne
                                   ^ v27.m_asOne)
                                  & 0x7F;
      goto LABEL_43;
    }
    v20 = p_value->m_value.m_any[1];
    v22 = (CDependencyObject *)p_value->m_value;
    v21 = *(_QWORD *)&p_value->m_value == 0;
    outValue.m_value = 0;
    outValue.m_flags = 0;
    success = 0;
    if ( v21 )
    {
      v25 = (unsigned int)v22;
    }
    else
    {
      v23 = CValueConvert::TryUnboxCDependencyObjectValue<CValue>(v22, &outValue, &success);
      v24 = v23;
      if ( v23 < 0 )
      {
        OnFailure_2990_(v23);
        CValue::~CValue(&outValue);
        OnFailure_2990_(v24);
        goto LABEL_41;
      }
      v25 = (unsigned int)v22;
      if ( success )
        goto LABEL_37;
    }
    CValue::ReleaseAndReset(&outValue);
    outValue.m_value = (CValueDetails::Value)__PAIR64__(v20, v25);
    outValue.m_flags.m_state.m_asOne = outValue.m_flags.m_state.m_asOne & 0xFFFFFF80 | 0x58;
    if ( v22 )
      CDependencyObject::AddRef(v22);
LABEL_37:
    if ( v5 != &outValue )
    {
      CValue::ReleaseAndReset(v5);
      CValue::Dispatch<CValueDetails::Handlers::Transfer<CValueDetails::tag_move>,void,CValue>(
        v5,
        (ValueType)(*(_BYTE *)&outValue.m_flags.m_state.0 & 0x3F),
        &outValue);
      v26 = (v5->m_flags.m_state.m_asOne ^ outValue.m_flags.m_state.m_asOne) & 0x7F;
      outValue.m_value = 0;
      v5->m_flags.m_state.m_asOne = outValue.m_flags.m_state.m_asOne ^ v26;
      outValue.m_flags = 0;
    }
    CValue::~CValue(&outValue);
LABEL_40:
    v24 = 0;
LABEL_41:
    if ( v24 < 0 )
    {
      OnFailure_2990_(v24);
      goto LABEL_43;
    }
    goto LABEL_42;
  }
  v55 = v6;
  v56 = (unsigned __int16)DirectUI::MetadataAPI::GetClassInfoByIndex(dp->m_nDeclaringTypeIndex)->m_nIndex;
  while ( v55 )
  {
    v57 = v55->GetTypeIndex(v55);
    v59 = (unsigned __int16)v57;
    if ( (_WORD)v56 == v57 || (_DWORD)v56 == 40 )
      goto LABEL_117;
    if ( (unsigned __int16)v56 >= 0x43Cu )
    {
      if ( (unsigned __int16)v57 < (XYFocusNavigationStrategy|IVectorOfUri) )
      {
        ClassInfoByIndex = (CCustomClassInfo *)&c_aTypes[(unsigned __int16)v57];
        goto LABEL_107;
      }
LABEL_137:
      EnterCriticalSection(&g_csStatic);
      ClassInfoByIndex = DirectUI::DynamicMetadataStorage::GetInstance()->m_customTypesCache._Mypair._Myval2._Myfirst[v59 - 1084]._Mypair._Myval2;
      LeaveCriticalSection(&g_csStatic);
LABEL_107:
      while ( ClassInfoByIndex->m_nIndex )
      {
        if ( ClassInfoByIndex->m_nIndex == (_WORD)v56 )
        {
          v62 = 1;
          goto LABEL_114;
        }
        ClassInfoByIndex = (CCustomClassInfo *)DirectUI::MetadataAPI::GetClassInfoByIndex(ClassInfoByIndex->m_nBaseTypeIndex);
      }
LABEL_113:
      v62 = 0;
      goto LABEL_114;
    }
    if ( (unsigned __int16)v57 >= (XYFocusNavigationStrategy|IVectorOfUri) )
      goto LABEL_137;
    m_handle = c_aTypeCheckData[v56].m_handle;
    if ( !m_handle )
      goto LABEL_113;
    m_handleMask = c_aTypeCheckData[v56].m_handleMask;
    if ( (m_handleMask & 0x800000000000LL) != 0 )
      goto LABEL_113;
    v62 = (m_handleMask & c_aTypeCheckData[(unsigned __int16)v57].m_handle) == m_handle;
LABEL_114:
    if ( !v62 )
      goto LABEL_115;
LABEL_117:
    if ( (dp->m_flags & 1) != 0 )
    {
      v70 = v55->m_pValueTable._Mypair._Myval2;
      if ( v70 )
      {
        v71 = v70->m_data.m_vector._Mypair._Myval2._Myfirst;
        v72 = dp->m_nIndex;
        m_handle = v70->m_data.m_vector._Mypair._Myval2._Mylast - v70->m_data.m_vector._Mypair._Myval2._Myfirst;
        while ( (__int64)m_handle > 0 )
        {
          if ( (unsigned int)v71[m_handle >> 1].first < (unsigned __int16)v72 )
          {
            v71 += (m_handle >> 1) + 1;
            m_handle += -1LL - (m_handle >> 1);
          }
          else
          {
            m_handle >>= 1;
          }
        }
        if ( v71 != v70->m_data.m_vector._Mypair._Myval2._Mylast
          && (unsigned __int16)v72 >= (unsigned int)v71->first
          && (v71->second.value.m_flags.m_state.m_asOne & 0x100) != 0 )
        {
LABEL_124:
          v68 = CDependencyObject::GetValueInternal(v55, dp, v5);
          v69 = v68;
          if ( v68 >= 0 )
            return 0;
          OnFailure_2990_(v68);
          OnFailure_2990_(v69);
          OnFailure_2990_(v69);
          return v69;
        }
      }
    }
    else if ( (dp->m_flags & 0x288) == 0x288 )
    {
      v116 = v55->m_pInheritedProperties;
      if ( v116 )
      {
        if ( v116->m_pWriter == v55 )
        {
          v117 = ToPropertyNumber(dp->m_nIndex);
          if ( ((1LL << v117) & *(_QWORD *)(v118 + 104)) != 0 )
            goto LABEL_124;
        }
      }
    }
    else
    {
      v63 = c_aTypeProperties[(unsigned __int16)v55->GetTypeIndex(v55)].m_nPropertySlotCount;
      v64 = c_aPropertySlot[(unsigned __int16)dp->m_nIndex];
      if ( (unsigned __int8)v64 >= v63 )
        goto LABEL_124;
      if ( v63 <= 0x20u )
      {
        v104 = v55->m_valid.bits;
        v67 = _bittest((const int *)&v104, v64);
      }
      else
      {
        v65.pointer = (unsigned int *)v55->m_valid;
        if ( !v65.pointer )
          goto LABEL_115;
        m_handle = v64 & 0x1F;
        v66 = v65.pointer[(unsigned __int64)c_aPropertySlot[(unsigned __int16)dp->m_nIndex] >> 5];
        v67 = _bittest((const int *)&v66, m_handle);
      }
      if ( v67 )
        goto LABEL_124;
    }
LABEL_115:
    LOBYTE(m_handle) = dp->m_nIndex == FrameworkElement_DataContext;
    v55 = v55->GetInheritanceParentInternal(v55, m_handle);
  }
  DefaultInheritedPropertyValue = CCoreServices::GetDefaultInheritedPropertyValue(
                                    v6->m_sharedState.m_ptr->m_value.m_coreServices,
                                    dp->m_nIndex,
                                    v5);
  v100 = DefaultInheritedPropertyValue;
  if ( DefaultInheritedPropertyValue >= 0 )
    return 0;
  OnFailure_2990_(DefaultInheritedPropertyValue);
  OnFailure_2990_(v100);
  OnFailure_2990_(v100);
  OnFailure_2990_(v100);
  return v100;
}

```

## disassembly

```asm
0x180032390  push    rbp
0x180032392  push    rbx
0x180032393  push    rsi
0x180032394  push    r13
0x180032396  push    r14
0x180032398  lea     rbp, [rsp-37h]
0x18003239d  sub     rsp, 0F0h
0x1800323a4  mov     rax, cs:__security_cookie
0x1800323ab  xor     rax, rsp
0x1800323ae  mov     [rbp+57h+var_50], rax
0x1800323b2  mov     r14, dp
0x1800323b5  mov     rsi, value
0x1800323b8  mov     edx, 1D4h; nIndex
0x1800323bd  mov     r13, this
0x1800323c0  cmp     [r14], dx
0x1800323c4  jz      loc_18003270D
0x1800323ca  mov     r10d, [r14+8]
0x1800323ce  mov     eax, r10d
0x1800323d1  mov     [rsp+110h+arg_18], rdi
0x1800323d9  and     eax, 288h
0x1800323de  mov     [rsp+110h+var_28], r12
0x1800323e6  mov     [rsp+110h+var_30], r15
0x1800323ee  cmp     eax, 288h
0x1800323f3  jz      loc_180033429
0x1800323f9  mov     eax, r10d
0x1800323fc  and     eax, 200h
0x180032401  test    r10b, r10b
0x180032404  js      loc_180032B23
0x18003240a  movaps  [rsp+110h+var_40], xmm6
0x180032412  test    r10b, 1
0x180032416  jnz     loc_1800324B0
0x18003241c  lea     r12, std__nothrow
0x180032423  bt      r10d, 8
0x180032428  jb      loc_180032895
0x18003242e  movzx   r9d, word ptr [r14]
0x180032432  shl     r9, 5
0x180032436  test    eax, eax
0x180032438  jnz     loc_180032AA6
0x18003243e  movzx   ebx, word ptr [r9+r12+0C565E0h]
0x180032447  add     rbx, r13
0x18003244a  mov     qword ptr [rsp+110h+pcStowedExceptions], rbx
0x18003244f  test    rbx, rbx
0x180032452  jz      loc_1800334E8
0x180032458  movzx   r15d, word ptr [r14+2]
0x18003245d  xor     edi, edi
0x18003245f  cmp     r15d, 8Ch
0x180032466  jz      loc_180032862
0x18003246c  cmp     r15d, 47h ; 'G'
0x180032470  jz      loc_180032903
0x180032476  cmp     r15d, 10Dh
0x18003247d  ja      loc_1800327B9
0x180032483  jz      loc_180032903
0x180032489  lea     eax, [r15-0Ah]; switch 254 cases
0x18003248d  cmp     eax, 0FDh
0x180032492  ja      def_1800324AE; jumptable 00000001800324AE default case, cases 11-39,41,44-98,100-111,113-128,130-158,160-164,166-186,188-229,231-242,244-262
0x180032498  cdqe
0x18003249a  movzx   eax, ds:(byte_18003389C - 180000000h)[r12+rax]
0x1800324a3  mov     ecx, ds:(jpt_1800324AE - 180000000h)[r12+rax*4]
0x1800324ab  add     this, r12
0x1800324ae  jmp     this; switch jump
0x1800324b0  mov     rax, [r13+28h]
0x1800324b4  test    rax, rax
0x1800324b7  jz      loc_18003258A
0x1800324bd  mov     rbx, [rax+8]
0x1800324c1  mov     this, [rax]
0x1800324c4  mov     dp, rbx
0x1800324c7  movzx   r11d, word ptr [r14]
0x1800324cb  sub     dp, this
0x1800324ce  mov     rax, 6666666666666667h
0x1800324d8  imul    dp
0x1800324db  mov     value, dp
0x1800324de  sar     value, 3
0x1800324e2  mov     rax, value
0x1800324e5  shr     rax, 3Fh
0x1800324e9  add     value, rax
0x1800324ec  test    value, value
0x1800324ef  jle     short loc_180032512
0x1800324f1  mov     dp, value
0x1800324f4  shr     dp, 1
0x1800324f7  lea     rax, [dp+dp*4]
0x1800324fb  cmp     [this+rax*4], r11w
0x180032500  lea     r9, [this+rax*4]
0x180032504  jb      loc_1800325B8
0x18003250a  mov     value, dp
0x18003250d  test    value, value
0x180032510  jg      short loc_1800324F1
0x180032512  cmp     this, rbx
0x180032515  jz      short loc_18003258A
0x180032517  cmp     r11w, [this]
0x18003251b  jb      short loc_18003258A
0x18003251d  lea     rbx, [this+4]
0x180032521  cmp     rsi, rbx
0x180032524  jz      loc_1800326C6
0x18003252a  mov     this, rsi; this
0x18003252d  call    ?ReleaseAndReset@CValue@@QEAAXXZ; CValue::ReleaseAndReset(void)
0x180032532  mov     eax, [rbx+8]
0x180032535  and     eax, 3Fh
0x180032538  jz      loc_1800326AF
0x18003253e  cmp     eax, 18h
0x180032541  jz      loc_1800325CE
0x180032547  cmp     eax, 8
0x18003254a  jz      loc_180032B01
0x180032550  cmp     eax, 21h ; '!'
0x180032553  jz      loc_180032B12
0x180032559  dec     eax; switch 32 cases
0x18003255b  cmp     eax, 1Fh
0x18003255e  ja      def_180032576; jumptable 0000000180032576 default case, cases 8,24
0x180032564  lea     r12, std__nothrow
0x18003256b  mov     eax, ds:(jpt_180032576 - 180000000h)[r12+rax*4]
0x180032573  add     rax, r12
0x180032576  jmp     rax; switch jump
0x180032578  movzx   eax, byte ptr [rbx]; jumptable 0000000180032576 case 2
0x18003257b  and     dword ptr [rsi+8], 0FFFFFFC2h
0x18003257f  or      dword ptr [rsi+8], 42h
0x180032583  mov     [rsi], al
0x180032585  jmp     loc_1800326AF
0x18003258a  test    r10b, 40h
0x18003258e  jnz     loc_1800331E3
0x180032594  mov     value, rsi; pDefaultValue
0x180032597  mov     dp, r14; pDP
0x18003259a  mov     this, r13; this
0x18003259d  call    ?GetDefaultValue@CDependencyObject@@QEAAJPEBVCDependencyProperty@@PEAVCValue@@@Z; CDependencyObject::GetDefaultValue(CDependencyProperty const *,CValue *)
0x1800325a2  mov     edi, eax
0x1800325a4  test    eax, eax
0x1800325a6  jns     loc_180032DB2
0x1800325ac  mov     ecx, eax; failedFrameHR
0x1800325ae  call    OnFailure_2990_
0x1800325b3  jmp     loc_1800326C8; jumptable 00000001800324AE case 10
0x1800325b8  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800325bf  lea     this, [r9+14h]
0x1800325c3  sub     rax, dp
0x1800325c6  add     value, rax
0x1800325c9  jmp     loc_18003250D
0x1800325ce  mov     r15d, [rbx+4]
0x1800325d2  mov     eax, [rbx]
0x1800325d4  mov     edi, r15d
0x1800325d7  shl     rdi, 20h
0x1800325db  or      rdi, rax
0x1800325de  mov     qword ptr [rbp+57h+outValue.m_value], 0
0x1800325e6  mov     qword ptr [rbp+57h+outValue.m_flags], 0
0x1800325ee  mov     [rsp+110h+success], 0
0x1800325f3  jz      loc_1800333A9
0x1800325f9  lea     value, [rsp+110h+success]; success
0x1800325fe  mov     this, rdi; inValue
0x180032601  lea     dp, [rbp+57h+outValue]; outValue
0x180032605  call    ??$TryUnboxCDependencyObjectValue@VCValue@@@CValueConvert@@YAJPEAVCDependencyObject@@AEAVCValue@@AEA_N@Z; CValueConvert::TryUnboxCDependencyObjectValue<CValue>(CDependencyObject *,CValue &,bool &)
0x18003260a  mov     r14d, eax
0x18003260d  test    eax, eax
0x18003260f  js      loc_1800336D4
0x180032615  cmp     [rsp+110h+success], 0
0x18003261a  mov     r14d, edi
0x18003261d  jnz     short loc_180032658
0x18003261f  lea     this, [rbp+57h+outValue]; this
0x180032623  call    ?ReleaseAndReset@CValue@@QEAAXXZ; CValue::ReleaseAndReset(void)
0x180032628  mov     eax, dword ptr [rbp+57h+outValue.m_flags]
0x18003262b  mov     this, rdi
0x18003262e  and     eax, 0FFFFFFD8h
0x180032631  mov     dword ptr [rbp+57h+outValue.m_value], r14d
0x180032635  or      eax, 58h
0x180032638  mov     dword ptr [rbp+57h+outValue.m_value+4], r15d
0x18003263c  mov     dword ptr [rbp+57h+outValue.m_flags], eax
0x18003263f  mov     rax, 0FFFFFFFF00000000h
0x180032649  and     this, rax
0x18003264c  mov     eax, edi
0x18003264e  or      this, rax; this
0x180032651  jz      short loc_180032658
0x180032653  call    ?AddRef@CDependencyObject@@QEAAXXZ; CDependencyObject::AddRef(void)
0x180032658  lea     rax, [rbp+57h+outValue]
0x18003265c  cmp     rsi, rax
0x18003265f  jz      short loc_18003269A
0x180032661  mov     this, rsi; this
0x180032664  call    ?ReleaseAndReset@CValue@@QEAAXXZ; CValue::ReleaseAndReset(void)
0x180032669  mov     edx, dword ptr [rbp+57h+outValue.m_flags]
0x18003266c  lea     value, [rbp+57h+outValue]; arg
0x180032670  and     edx, 3Fh; valueType
0x180032673  mov     this, rsi; this
0x180032676  call    ??$Dispatch@U?$Transfer@Utag_move@CValueDetails@@@Handlers@CValueDetails@@XVCValue@@@CValue@@AEAAXW4ValueType@@$$QEAV0@@Z; CValue::Dispatch<CValueDetails::Handlers::Transfer<CValueDetails::tag_move>,void,CValue>(ValueType,CValue &&)
0x18003267b  mov     ecx, dword ptr [rbp+57h+outValue.m_flags]
0x18003267e  xor     ecx, [rsi+8]
0x180032681  and     ecx, 7Fh
0x180032684  mov     qword ptr [rbp+57h+outValue.m_value], 0
0x18003268c  xor     ecx, dword ptr [rbp+57h+outValue.m_flags]
0x18003268f  mov     [rsi+8], ecx
0x180032692  mov     qword ptr [rbp+57h+outValue.m_flags], 0
0x18003269a  lea     this, [rbp+57h+outValue]; this
0x18003269e  call    ??1CValue@@QEAA@XZ; CValue::~CValue(void)
0x1800326a3  xor     r14d, r14d
0x1800326a6  test    r14d, r14d
0x1800326a9  js      loc_18003349E
0x1800326af  mov     ecx, [rsi+8]
0x1800326b2  mov     eax, ecx
0x1800326b4  and     eax, 7Fh
0x1800326b7  mov     [rsi+8], eax
0x1800326ba  xor     ecx, [rbx+8]
0x1800326bd  and     ecx, 7Fh
0x1800326c0  xor     ecx, [rbx+8]
0x1800326c3  mov     [rsi+8], ecx
0x1800326c6  xor     edi, edi
0x1800326c8  movaps  xmm6, [rsp+110h+var_40]; jumptable 00000001800324AE case 10
0x1800326d0  test    edi, edi
0x1800326d2  js      loc_1800327A4
0x1800326d8  xor     eax, eax
0x1800326da  mov     r12, [rsp+110h+var_28]
0x1800326e2  mov     rdi, [rsp+110h+arg_18]
0x1800326ea  mov     r15, [rsp+110h+var_30]
0x1800326f2  mov     this, [rbp+57h+var_50]
0x1800326f6  xor     this, rsp; StackCookie
0x1800326f9  call    __security_check_cookie
0x1800326fe  add     rsp, 0F0h
0x180032705  pop     r14
0x180032707  pop     r13
0x180032709  pop     rsi
0x18003270a  pop     rbx
0x18003270b  pop     rbp
0x18003270c  retn
0x18003270d  mov     rax, [this+10h]
0x180032711  mov     rbx, [rax]
0x180032714  cmp     dword ptr [rbx+70h], 0
0x180032718  jz      loc_1800323CA
0x18003271e  call    ?IsPropertyDefaultByIndex@CDependencyObject@@QEBA_NW4KnownPropertyIndex@@@Z; CDependencyObject::IsPropertyDefaultByIndex(KnownPropertyIndex)
0x180032723  test    al, al
0x180032725  jz      loc_1800323CA
0x18003272b  mov     value, rsi; pDefaultValue
0x18003272e  mov     dp, rbx; pCore
0x180032731  mov     this, r14; this
0x180032734  call    ?CreateDefaultValueObject@CDependencyProperty@@QEBAJPEAVCCoreServices@@PEAVCValue@@@Z; CDependencyProperty::CreateDefaultValueObject(CCoreServices *,CValue *)
0x180032739  mov     ebx, eax
0x18003273b  test    eax, eax
0x18003273d  js      loc_180033786
0x180032743  lea     rax, [rbp+57h+var_C0]
0x180032747  mov     qword ptr [rbp+57h+var_B0.m_value.m_value], r14
0x18003274b  mov     [rbp+57h+var_B0.m_pCore], rax
0x18003274f  lea     dp, [rbp+57h+var_B0]
0x180032753  mov     rax, [r13+0]
0x180032757  xorps   xmm0, xmm0
0x18003275a  mov     this, r13
0x18003275d  mov     qword ptr [rbp+57h+var_B0.m_value.m_flags], rsi
0x180032761  movdqu  xmmword ptr [rbp+57h+var_C0.m_encodedStorage.___u0], xmm0
0x180032766  mov     dword ptr [rbp+57h+var_B0.m_spServiceProviderContext._Ptr], 0
0x18003276d  mov     rax, [rax+28h]
0x180032771  mov     [rbp+57h+var_B0.m_spServiceProviderContext._Rep], 0
0x180032779  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003277e  mov     this, qword ptr [rbp+57h+var_C0.m_encodedStorage.___u0+8]; this
0x180032782  mov     ebx, eax
0x180032784  test    this, this
0x180032787  jz      short loc_18003278E
0x180032789  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003278e  test    ebx, ebx
0x180032790  jns     loc_1800323CA
0x180032796  mov     ecx, ebx; failedFrameHR
0x180032798  call    OnFailure_2990_
0x18003279d  mov     eax, ebx
0x18003279f  jmp     loc_1800326F2
0x1800327a4  mov     ecx, edi; failedFrameHR
0x1800327a6  call    OnFailure_2990_
0x1800327ab  mov     ecx, edi; failedFrameHR
0x1800327ad  call    OnFailure_2990_
0x1800327b2  mov     eax, edi
0x1800327b4  jmp     loc_1800326DA
0x1800327b9  mov     ecx, r15d
0x1800327bc  sub     ecx, 124h
0x1800327c2  jz      loc_180032EDE
0x1800327c8  sub     ecx, 7Eh ; '~'
0x1800327cb  jz      loc_18003303E
0x1800327d1  sub     ecx, 24h ; '$'
0x1800327d4  jz      loc_18003303E
0x1800327da  cmp     ecx, 0C3h
0x1800327e0  jz      loc_18003303E
0x1800327e6  mov     eax, 43Ch; jumptable 00000001800324AE default case, cases 11-39,41,44-98,100-111,113-128,130-158,160-164,166-186,188-229,231-242,244-262
0x1800327eb  cmp     r15w, ax
0x1800327ef  jnb     loc_1800328D0
0x1800327f5  lea     r15, ds:0E5B450h[r15*8]
0x1800327fd  add     r15, r12
0x180032800  mov     eax, 95h
0x180032805  cmp     [r15], ax
0x180032809  jz      loc_180033813
0x18003280f  test    dword ptr [r15+4], 800h
0x180032817  jnz     loc_180033813
0x18003281d  mov     rbx, [rbx]
0x180032820  mov     r15, rbx
0x180032823  shr     r15, 20h
0x180032827  test    rbx, rbx
0x18003282a  jz      loc_180032DE0
0x180032830  mov     this, rsi; this
0x180032833  call    ?ReleaseAndReset@CValue@@QEAAXXZ; CValue::ReleaseAndReset(void)
0x180032838  and     dword ptr [rsi+8], 0FFFFFFD8h
0x18003283c  mov     this, r15
0x18003283f  or      dword ptr [rsi+8], 58h
0x180032843  shl     this, 20h
0x180032847  mov     eax, ebx
0x180032849  or      this, rax; this
0x18003284c  mov     [rsi], ebx
0x18003284e  mov     [rsi+4], r15d
0x180032852  jz      loc_180032EA5
0x180032858  call    ?AddRef@CDependencyObject@@QEAAXXZ; CDependencyObject::AddRef(void)
0x18003285d  jmp     loc_1800326C8; jumptable 00000001800324AE case 10
0x180032862  bt      r10d, 10h
0x180032867  jb      loc_180032A89; jumptable 00000001800324AE case 42
0x18003286d  movsd   xmm6, qword ptr [rbx]
0x180032871  mov     this, rsi; this
  ... truncated ...
```
