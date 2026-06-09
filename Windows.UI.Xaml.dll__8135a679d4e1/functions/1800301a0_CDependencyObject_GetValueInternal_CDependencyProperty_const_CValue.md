# CDependencyObject::GetValueInternal(CDependencyProperty const *,CValue *)

- ea: `0x1800301a0`
- end: `0x1800313d6`
- name: `?GetValueInternal@CDependencyObject@@QEAAJPEBVCDependencyProperty@@PEAVCValue@@@Z`
- size: `4662`
- prototype: `HRESULT __fastcall(CDependencyObject *this, const CDependencyProperty *pDP, CValue *pValue)`
- caller_count: `5`
- callee_count: `38`
- tags: `file_ops, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18002ebc0`
- `0x180032390`
- `0x180272994`
- `0x180379d1c`
- `0x1809fc32c`

## callees

- `0x180004bc0`
- `0x180021840`
- `0x180021960`
- `0x180021970`
- `0x18002c780`
- `0x18002cf20`
- `0x18002d990`
- `0x1800301a0`
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

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180030279`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180030279`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030299`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030299`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1800306a2`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x180030ac6`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x18003107c`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x18003113e`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1800306a2`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x180030ac6`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x18003107c`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x18003113e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180030651`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180030a75`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180030651`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180030a75`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003118d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800311a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003118d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800311a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180030c6f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180030cac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180030cd2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180030c6f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180030cac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180030cd2`

## pseudocode

```c
__int64 __fastcall CDependencyObject::GetValueInternal(
        CDependencyObject *this,
        const CDependencyProperty *pDP,
        CValue *pValue)
{
  MetaDataPropertyInfoFlags m_flags; // r11d
  CValue *v4; // rsi
  CDependencyObject *v6; // r13
  __int64 v7; // rax
  unsigned int v8; // edi
  const CValue *v9; // r14
  __int64 m_nPropertyTypeIndex; // rbx
  CCustomClassInfo *v11; // rbx
  containers::vector_map<enum KnownPropertyIndex,EffectiveValue,std::less<void>,std::allocator<std::pair<enum KnownPropertyIndex,EffectiveValue> > > *Myval2; // rax
  std::pair<enum KnownPropertyIndex,EffectiveValue> *Mylast; // rbx
  std::pair<enum KnownPropertyIndex,EffectiveValue> *Myfirst; // rcx
  KnownPropertyIndex m_nIndex; // r10
  unsigned __int64 v16; // r8
  const CValue *p_value; // rbx
  int v18; // eax
  bool m_bool; // al
  HRESULT DefaultValue; // eax
  unsigned int v21; // xmm6_4
  unsigned int v23; // r12d
  CDependencyObject *v24; // r14
  HRESULT v25; // eax
  HRESULT v26; // r15d
  unsigned int v27; // r15d
  unsigned int v28; // ecx
  CValueDetails::CValueState v29; // ecx
  unsigned int Storage; // xmm6_4
  unsigned int RuntimeStringHandleMarker_high; // eax
  HRESULT v32; // eax
  unsigned int v33; // ebx
  CValueDetails::Value v34; // rbx
  CValueDetails::Value v35; // rbx
  __int64 v36; // r14
  HRESULT DefaultValueObject; // r15d
  unsigned __int64 v38; // rbx
  int v39; // edx
  const wchar_t *v40; // rax
  UINT32 v41; // edx
  int v42; // eax
  int v43; // edx
  unsigned __int8 m_nPropertySlotCount; // cl
  unsigned int v45; // edx
  CDependencyObject::BitField v46; // r8
  unsigned int v47; // eax
  unsigned __int8 v48; // cf
  unsigned int v49; // eax
  bool v50; // bl
  CCoreServices **p_m_coreServices; // rax
  bool IsPropertyDefault; // al
  CDependencyObject_vtbl *v53; // rcx
  bool v54; // bl
  HRESULT (__fastcall *SetValue)(CDependencyObject *, const SetValueParams *); // rax
  HRESULT v56; // r14d
  containers::vector_map<enum KnownPropertyIndex,EffectiveValue,std::less<void>,std::allocator<std::pair<enum KnownPropertyIndex,EffectiveValue> > > *v57; // rax
  unsigned __int64 m_value; // rcx
  _OWORD *v59; // rcx
  _OWORD *v60; // r14
  _OWORD *v61; // rax
  HSTRING StringRawBuffer; // rax
  UINT32 v63; // edx
  int v64; // eax
  __int64 v65; // rcx
  unsigned int v66; // eax
  unsigned int v67; // ebx
  std::pair<enum KnownPropertyIndex,EffectiveValue> *v68; // rcx
  KnownPropertyIndex v69; // r10
  unsigned __int64 v70; // r8
  bool v71; // zf
  _OWORD *v72; // rcx
  _OWORD *v73; // r14
  _OWORD *v74; // rax
  unsigned int v75; // ebx
  unsigned int v76; // eax
  __int64 v77; // rcx
  unsigned int v78; // eax
  int v79; // eax
  _QWORD *FailFast; // rcx
  _QWORD *v81; // r14
  unsigned int v82; // eax
  KnownTypeIndex v83; // bx
  unsigned int bits; // eax
  unsigned int v85; // ebx
  KnownTypeIndex m_typeHandle; // ax
  unsigned int v87; // eax
  HRESULT v88; // eax
  InheritedProperties *m_pInheritedProperties; // r8
  char v90; // al
  __int64 v91; // r8
  KnownTypeIndex v92; // cx
  unsigned int v93; // eax
  unsigned int pcStowedExceptions[2]; // [rsp+30h] [rbp-89h] BYREF
  bool success; // [rsp+38h] [rbp-81h] BYREF
  HSTRING string; // [rsp+40h] [rbp-79h] BYREF
  _STOWED_EXCEPTION_INFORMATION_V2 **pppStowedExceptions; // [rsp+48h] [rbp-71h] BYREF
  xstring_ptr v98[2]; // [rsp+50h] [rbp-69h] BYREF
  CREATEPARAMETERS v99; // [rsp+60h] [rbp-59h] BYREF
  _QWORD v100[3]; // [rsp+88h] [rbp-31h] BYREF
  int v101; // [rsp+A0h] [rbp-19h]
  __int64 v102; // [rsp+A8h] [rbp-11h]
  CValue outValue; // [rsp+B0h] [rbp-9h] BYREF

  m_flags = pDP->m_flags;
  v4 = pValue;
  v6 = this;
  if ( (m_flags & 1) != 0 )
  {
    Myval2 = this->m_pValueTable._Mypair._Myval2;
    if ( Myval2 )
    {
      Mylast = Myval2->m_data.m_vector._Mypair._Myval2._Mylast;
      Myfirst = Myval2->m_data.m_vector._Mypair._Myval2._Myfirst;
      m_nIndex = pDP->m_nIndex;
      v16 = Mylast - Myval2->m_data.m_vector._Mypair._Myval2._Myfirst;
      while ( (__int64)v16 > 0 )
      {
        if ( (unsigned int)Myfirst[v16 >> 1].first < (unsigned __int16)m_nIndex )
        {
          Myfirst += (v16 >> 1) + 1;
          v16 += -1LL - (v16 >> 1);
        }
        else
        {
          v16 >>= 1;
        }
      }
      if ( Myfirst != Mylast && (unsigned __int16)m_nIndex >= (unsigned int)Myfirst->first )
      {
        p_value = &Myfirst->second.value;
        v8 = 0;
        if ( v4 == (CValue *)&Myfirst->second )
          return v8;
        CValue::ReleaseAndReset(v4);
        v18 = p_value->m_flags.m_state.m_asOne & 0x3F;
        if ( !v18 )
          goto LABEL_43;
        if ( v18 != 24 )
        {
          if ( v18 == 8 )
          {
            v4->m_value.m_any[0] = p_value->m_value.m_any[0];
            v4->m_flags.m_state.m_asOne &= 0xFFFFFFC8;
            v4->m_flags.m_state.m_asOne |= 0x48u;
          }
          else
          {
            if ( v18 != 33 )
            {
              switch ( v18 )
              {
                case 1:
                  v4->m_flags.m_state.m_asOne &= 0xFFFFFFC1;
                  v4->m_flags.m_state.m_asOne |= 0x41u;
                  goto LABEL_43;
                case 2:
                  m_bool = p_value->m_value.m_bool;
                  v4->m_flags.m_state.m_asOne &= 0xFFFFFFC2;
                  v4->m_flags.m_state.m_asOne |= 0x42u;
                  v4->m_value.m_bool = m_bool;
                  goto LABEL_43;
                case 3:
                  v4->m_value.m_any[0] = p_value->m_value.m_any[0];
                  v4->m_value.m_any[1] = p_value->m_value.m_any[1];
                  v4->m_flags.m_state.m_asOne &= 0xFFFFFFC3;
                  v4->m_flags.m_state.m_asOne |= 0x43u;
                  goto LABEL_43;
                case 4:
                  v76 = p_value->m_value.m_any[0];
                  v4->m_flags.m_state.m_asOne &= 0xFFFFFFC4;
                  v4->m_flags.m_state.m_asOne |= 0x44u;
                  v4->m_value.m_any[0] = v76;
                  goto LABEL_43;
                case 5:
                  v87 = p_value->m_value.m_any[0];
                  v4->m_flags.m_state.m_asOne &= 0xFFFFFFC5;
                  v4->m_flags.m_state.m_asOne |= 0x45u;
                  v4->m_value.m_any[0] = v87;
                  goto LABEL_43;
                case 6:
                  v4->m_value.m_any[0] = p_value->m_value.m_any[0];
                  v4->m_value.m_any[1] = p_value->m_value.m_any[1];
                  v4->m_flags.m_state.m_asOne &= 0xFFFFFFC6;
                  v4->m_flags.m_state.m_asOne |= 0x46u;
                  goto LABEL_43;
                case 7:
                  v4->m_value.m_any[0] = p_value->m_value.m_any[0];
                  v4->m_value.m_any[1] = p_value->m_value.m_any[1];
                  v4->m_flags.m_state.m_asOne &= 0xFFFFFFC7;
                  v4->m_flags.m_state.m_asOne |= 0x47u;
                  goto LABEL_43;
                case 9:
                  v4->m_value.m_any[0] = p_value->m_value.m_any[0];
                  v4->m_value.m_any[1] = p_value->m_value.m_any[1];
                  v4->m_flags.m_state.m_asOne &= 0xFFFFFFC9;
                  v4->m_flags.m_state.m_asOne |= 0x49u;
                  goto LABEL_43;
                case 10:
                  CValueDetails::ValueStores::Array<11,float>::Copy(v4, p_value);
                  v4->m_flags.m_state.m_asOne &= 0xFFFFFFCA;
                  v4->m_flags.m_state.m_asOne |= 0x4Au;
                  v4->m_flags.m_count = p_value->m_flags.m_count;
                  goto LABEL_43;
                case 11:
                  CValueDetails::ValueStores::Array<11,float>::Copy(v4, p_value);
                  v4->m_flags.m_state.m_asOne &= 0xFFFFFFCB;
                  v4->m_flags.m_state.m_asOne |= 0x4Bu;
                  v4->m_flags.m_count = p_value->m_flags.m_count;
                  goto LABEL_43;
                case 12:
                  CValueDetails::ValueStores::Array<12,double>::Copy(v4, p_value);
                  v4->m_flags.m_state.m_asOne &= 0xFFFFFFCC;
                  v4->m_flags.m_state.m_asOne |= 0x4Cu;
                  v4->m_flags.m_count = p_value->m_flags.m_count;
                  goto LABEL_43;
                case 13:
                  CValueDetails::ValueStores::Array<12,double>::Copy(v4, p_value);
                  v4->m_flags.m_state.m_asOne &= 0xFFFFFFCD;
                  v4->m_flags.m_state.m_asOne |= 0x4Du;
                  v4->m_flags.m_count = p_value->m_flags.m_count;
                  goto LABEL_43;
                case 14:
                  m_value = (unsigned __int64)p_value->m_value;
                  if ( (*(_QWORD *)&p_value->m_value & 1) != 0 )
                  {
                    if ( WindowsDuplicateString(
                           (HSTRING)(m_value & 0xFFFFFFFFFFFFFFFEuLL),
                           (HSTRING *)&pppStowedExceptions) < 0 )
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
                    m_value = (unsigned __int64)pppStowedExceptions | 1;
                  }
                  v4->m_value = (CValueDetails::Value)m_value;
                  v4->m_flags.m_state.m_asOne &= 0xFFFFFFCE;
                  v4->m_flags.m_state.m_asOne |= 0x4Eu;
                  goto LABEL_43;
                case 15:
                  v82 = p_value->m_value.m_any[0];
                  v4->m_flags.m_state.m_asOne &= 0xFFFFFFCF;
                  v4->m_flags.m_state.m_asOne |= 0x4Fu;
                  v4->m_value.m_any[0] = v82;
                  goto LABEL_43;
                case 16:
                  FailFast = 0;
                  v81 = (_QWORD *)p_value->m_value;
                  if ( p_value->m_value )
                  {
                    FailFast = XcpAllocation::OSMemoryAllocateFailFast(8u);
                    if ( FailFast )
                      *FailFast = 0;
                    else
                      FailFast = 0;
                    *FailFast = *v81;
                  }
                  v4->m_value = (CValueDetails::Value)FailFast;
                  v4->m_flags.m_state.m_asOne &= 0xFFFFFFD0;
                  v4->m_flags.m_state.m_asOne |= 0x50u;
                  goto LABEL_43;
                case 17:
                  CValueDetails::ValueStores::Reference<17,XSIZEF>::Copy(v4, p_value);
                  v4->m_flags.m_state.m_asOne &= 0xFFFFFFD1;
                  v4->m_flags.m_state.m_asOne |= 0x51u;
                  goto LABEL_43;
                case 18:
                  v26 = CValueDetails::Handlers::ConvertAndCopy::Copy<18>(v4, p_value);
                  goto LABEL_42;
                case 19:
                  v59 = 0;
                  v60 = (_OWORD *)p_value->m_value;
                  if ( p_value->m_value )
                  {
                    v61 = XcpAllocation::OSMemoryAllocateFailFast(0x10u);
                    v59 = v61;
                    if ( v61 )
                      *v61 = 0;
                    else
                      v59 = 0;
                    *v59 = *v60;
                  }
                  v4->m_value = (CValueDetails::Value)v59;
                  v4->m_flags.m_state.m_asOne &= 0xFFFFFFD3;
                  v4->m_flags.m_state.m_asOne |= 0x53u;
                  goto LABEL_43;
                case 20:
                  v26 = CValueDetails::Handlers::ConvertAndCopy::Copy<20>(v4, p_value);
                  goto LABEL_42;
                case 21:
                  v72 = 0;
                  v73 = (_OWORD *)p_value->m_value;
                  if ( p_value->m_value )
                  {
                    v74 = XcpAllocation::OSMemoryAllocateFailFast(0x10u);
                    v72 = v74;
                    if ( v74 )
                      *v74 = 0;
                    else
                      v72 = 0;
                    *v72 = *v73;
                  }
                  v4->m_value = (CValueDetails::Value)v72;
                  v4->m_flags.m_state.m_asOne &= 0xFFFFFFD5;
                  v4->m_flags.m_state.m_asOne |= 0x55u;
                  goto LABEL_43;
                case 22:
                  v4->m_value.m_any[0] = p_value->m_value.m_any[0];
                  v4->m_value.m_any[1] = p_value->m_value.m_any[1];
                  v4->m_flags.m_state.m_asOne &= 0xFFFFFFD6;
                  v4->m_flags.m_state.m_asOne |= 0x56u;
                  goto LABEL_43;
                case 23:
                  v4->m_value.m_any[0] = p_value->m_value.m_any[0];
                  v4->m_value.m_any[1] = p_value->m_value.m_any[1];
                  v4->m_flags.m_state.m_asOne &= 0xFFFFFFD7;
                  v4->m_flags.m_state.m_asOne |= 0x57u;
                  goto LABEL_43;
                case 25:
                  v4->m_value.m_any[0] = p_value->m_value.m_any[0];
                  v4->m_value.m_any[1] = p_value->m_value.m_any[1];
                  v4->m_flags.m_state.m_asOne &= 0xFFFFFFD9;
                  v4->m_flags.m_state.m_asOne |= 0x59u;
                  goto LABEL_43;
                case 26:
                  v4->m_value.m_any[0] = p_value->m_value.m_any[0];
                  v4->m_value.m_any[1] = p_value->m_value.m_any[1];
                  CValueDetails::ValueStores::RefCounted<27,IInspectable>::AddRef(v4);
                  v4->m_flags.m_state.m_asOne &= 0xFFFFFFDA;
                  v4->m_flags.m_state.m_asOne |= 0x5Au;
                  goto LABEL_43;
                case 27:
                  v65 = p_value->m_value.m_any[0];
                  v4->m_value.m_any[0] = v65;
                  v66 = p_value->m_value.m_any[1];
                  v4->m_value.m_any[1] = v66;
                  if ( v65 | ((unsigned __int64)v66 << 32) )
                    (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)(v65 | ((unsigned __int64)v66 << 32)) + 8LL))(v65 | ((unsigned __int64)v66 << 32));
                  v4->m_flags.m_state.m_asOne &= 0xFFFFFFDB;
                  v4->m_flags.m_state.m_asOne |= 0x5Bu;
                  goto LABEL_43;
                case 28:
                  m_typeHandle = p_value->m_value.m_typeHandle;
                  v4->m_flags.m_state.m_asOne &= 0xFFFFFFDC;
                  v4->m_flags.m_state.m_asOne |= 0x5Cu;
                  v4->m_value.m_typeHandle = m_typeHandle;
                  goto LABEL_43;
                case 29:
                  v77 = p_value->m_value.m_any[0];
                  v4->m_value.m_any[0] = v77;
                  v78 = p_value->m_value.m_any[1];
                  v4->m_value.m_any[1] = v78;
                  if ( v77 | ((unsigned __int64)v78 << 32) )
                    ++*(_DWORD *)(v77 | ((unsigned __int64)v78 << 32));
                  v4->m_flags.m_state.m_asOne &= 0xFFFFFFDD;
                  v4->m_flags.m_state.m_asOne |= 0x5Du;
                  goto LABEL_43;
                case 30:
                  v4->m_value.m_any[0] = p_value->m_value.m_any[0];
                  v4->m_value.m_any[1] = p_value->m_value.m_any[1];
                  v4->m_flags.m_state.m_asOne &= 0xFFFFFFDE;
                  v4->m_flags.m_state.m_asOne |= 0x5Eu;
                  goto LABEL_43;
                case 31:
                  v88 = CValueConvert::EnsureValueObjectUnboxed<CValue>(p_value, v4);
                  v26 = v88;
                  if ( v88 >= 0 )
                    goto LABEL_41;
                  OnFailure_2990_(v88);
                  break;
                case 32:
                  v4->m_value.m_any[0] = p_value->m_value.m_any[0];
                  v4->m_value.m_any[1] = p_value->m_value.m_any[1];
                  v4->m_flags.m_state.m_asOne &= 0xFFFFFFE0;
                  v4->m_flags.m_state.m_asOne |= 0x60u;
                  goto LABEL_43;
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
                  goto LABEL_43;
              }
              goto LABEL_42;
            }
            v49 = p_value->m_value.m_any[0];
            v4->m_flags.m_state.m_asOne &= 0xFFFFFFE1;
            v4->m_flags.m_state.m_asOne |= 0x61u;
            v4->m_value.m_any[0] = v49;
          }
LABEL_43:
          v29.0 = ($AE0720DD29EBB950835C0AB6A5612248)v4->m_flags.m_state;
          v4->m_flags.m_state.m_asOne = *(_BYTE *)&v29.0 & 0x7F;
          v4->m_flags.m_state.m_asOne = p_value->m_flags.m_state.m_asOne
                                      ^ (p_value->m_flags.m_state.m_asOne
                                       ^ v29.m_asOne)
                                      & 0x7F;
          return v8;
        }
        v23 = p_value->m_value.m_any[1];
        v24 = (CDependencyObject *)p_value->m_value;
        v71 = *(_QWORD *)&p_value->m_value == 0;
        outValue.m_value = 0;
        outValue.m_flags = 0;
        success = 0;
        if ( v71 )
        {
          v27 = (unsigned int)v24;
        }
        else
        {
          v25 = CValueConvert::TryUnboxCDependencyObjectValue<CValue>(v24, &outValue, &success);
          v26 = v25;
          if ( v25 < 0 )
          {
            OnFailure_2990_(v25);
            CValue::~CValue(&outValue);
            OnFailure_2990_(v26);
            goto LABEL_42;
          }
          v27 = (unsigned int)v24;
          if ( success )
            goto LABEL_38;
        }
        CValue::ReleaseAndReset(&outValue);
        outValue.m_value = (CValueDetails::Value)__PAIR64__(v23, v27);
        outValue.m_flags.m_state.m_asOne = outValue.m_flags.m_state.m_asOne & 0xFFFFFF80 | 0x58;
        if ( v24 )
          CDependencyObject::AddRef(v24);
LABEL_38:
        if ( v4 != &outValue )
        {
          CValue::ReleaseAndReset(v4);
          CValue::Dispatch<CValueDetails::Handlers::Transfer<CValueDetails::tag_move>,void,CValue>(
            v4,
            (ValueType)(*(_BYTE *)&outValue.m_flags.m_state.0 & 0x3F),
            &outValue);
          v28 = (v4->m_flags.m_state.m_asOne ^ outValue.m_flags.m_state.m_asOne) & 0x7F;
          outValue.m_value = 0;
          v4->m_flags.m_state.m_asOne = outValue.m_flags.m_state.m_asOne ^ v28;
          outValue.m_flags = 0;
        }
        CValue::~CValue(&outValue);
LABEL_41:
        v26 = 0;
LABEL_42:
        if ( v26 < 0 )
        {
          OnFailure_2990_(v26);
          return v8;
        }
        goto LABEL_43;
      }
    }
    if ( (m_flags & 0x40) == 0 || CDependencyProperty::IsCreateOnDemandDisabledByQuirk(pDP->m_nIndex) )
    {
      DefaultValue = CDependencyObject::GetDefaultValue(v6, pDP, v4);
      v8 = DefaultValue;
      if ( DefaultValue >= 0 )
        return 0;
    }
    else
    {
      DefaultValue = CDependencyProperty::CreateDefaultValueObject(
                       pDP,
                       v6->m_sharedState.m_ptr->m_value.m_coreServices,
                       v4);
      v8 = DefaultValue;
      if ( DefaultValue >= 0 )
      {
        DefaultValue = CDependencyObject::SetValue(v6, pDP, v4);
        v8 = DefaultValue;
        if ( DefaultValue >= 0 )
        {
          CDependencyObject::SetPropertyIsDefault(v6, pDP);
          return 0;
        }
      }
    }
LABEL_82:
    OnFailure_2990_(DefaultValue);
    return v8;
  }
  v7 = (unsigned __int16)pDP->m_nIndex;
  if ( (m_flags & 0x100) == 0 )
  {
    v8 = 0;
    if ( (m_flags & 0x200) != 0 )
    {
      LOBYTE(pValue) = 1;
      if ( c_aDependencyPropertyRuntimeData[v7].m_cgpfn(this, pDP, (bool)pValue) < 0 )
        goto LABEL_181;
      m_flags = pDP->m_flags;
      if ( (m_flags & 0x100) != 0 )
        LODWORD(this) = 0;
      else
        LODWORD(this) = c_aDependencyPropertyRuntimeData[(unsigned __int16)pDP->m_nIndex].m_nOffset;
      v9 = (const CValue *)(*(char **)((char *)&v6->__vftable + (unsigned __int16)this)
                          + c_aDependencyPropertyRuntimeData[(unsigned __int16)pDP->m_nIndex].m_nGroupOffset);
    }
    else
    {
      v9 = (const CValue *)((char *)this + c_aDependencyPropertyRuntimeData[v7].m_nOffset);
    }
    *(_QWORD *)pcStowedExceptions = v9;
    if ( v9 )
    {
      m_nPropertyTypeIndex = (unsigned __int16)pDP->m_nPropertyTypeIndex;
      if ( (_DWORD)m_nPropertyTypeIndex == 140 )
      {
        if ( (m_flags & 0x10000) != 0 )
        {
LABEL_31:
          v21 = v9->m_value.m_any[0];
          CValue::ReleaseAndReset(v4);
          v4->m_flags.m_state.m_asOne &= 0xFFFFFFC8;
          v4->m_flags.m_state.m_asOne |= 0x48u;
          v4->m_value.m_any[0] = v21;
        }
        else
        {
          v98[0] = (xstring_ptr)v9->m_value;
          Storage = (unsigned int)v98[0].m_encodedStorage.Storage;
          CValue::ReleaseAndReset(v4);
          v4->m_flags.m_state.m_asOne &= 0xFFFFFFC9;
          v4->m_flags.m_state.m_asOne |= 0x49u;
          RuntimeStringHandleMarker_high = HIDWORD(v98[0].m_encodedStorage.RuntimeStringHandleMarker);
          v4->m_value.m_any[0] = Storage;
          v4->m_value.m_any[1] = RuntimeStringHandleMarker_high;
        }
        return v8;
      }
      if ( (_DWORD)m_nPropertyTypeIndex == 71 )
        goto LABEL_60;
      if ( (unsigned int)m_nPropertyTypeIndex <= 0x10D )
      {
        if ( (_DWORD)m_nPropertyTypeIndex != 269 )
        {
          switch ( pDP->m_nPropertyTypeIndex )
          {
            case DateTime:
              return v8;
            case Object:
              if ( (pDP->m_flags & 1) != 0 )
              {
                v57 = v6->m_pValueTable._Mypair._Myval2;
                if ( !v57 )
                  goto LABEL_109;
                v68 = v57->m_data.m_vector._Mypair._Myval2._Myfirst;
                v69 = pDP->m_nIndex;
                v70 = v57->m_data.m_vector._Mypair._Myval2._Mylast - v57->m_data.m_vector._Mypair._Myval2._Myfirst;
                while ( (__int64)v70 > 0 )
                {
                  if ( (unsigned int)v68[v70 >> 1].first < (unsigned __int16)v69 )
                  {
                    v68 += (v70 >> 1) + 1;
                    v70 += -1LL - (v70 >> 1);
                  }
                  else
                  {
                    v70 >>= 1;
                  }
                }
                if ( v68 == v57->m_data.m_vector._Mypair._Myval2._Mylast
                  || (unsigned __int16)v69 < (unsigned int)v68->first )
                {
                  goto LABEL_109;
                }
                v71 = (v68->second.value.m_flags.m_state.m_asOne & 0x100) == 0;
              }
              else
              {
                if ( (pDP->m_flags & 0x288) != 0x288 )
                {
                  m_nPropertySlotCount = c_aTypeProperties[(unsigned __int16)v6->GetTypeIndex(v6)].m_nPropertySlotCount;
                  v45 = c_aPropertySlot[(unsigned __int16)pDP->m_nIndex];
                  if ( (unsigned __int8)v45 >= m_nPropertySlotCount )
                    goto LABEL_81;
                  if ( m_nPropertySlotCount <= 0x20u )
                  {
                    bits = v6->m_valid.bits;
                    v48 = _bittest((const int *)&bits, v45);
                  }
                  else
                  {
                    v46.pointer = (unsigned int *)v6->m_valid;
                    if ( !v46.pointer )
                      goto LABEL_109;
                    v47 = v46.pointer[(unsigned __int64)c_aPropertySlot[(unsigned __int16)pDP->m_nIndex] >> 5];
                    v48 = _bittest((const int *)&v47, v45 & 0x1F);
                  }
                  if ( v48 )
                    goto LABEL_81;
LABEL_109:
                  CValue::ReleaseAndReset(v4);
                  v4->m_flags.m_state.m_asOne &= 0xFFFFFFD8;
                  v4->m_flags.m_state.m_asOne |= 0x58u;
                  v4->m_value = 0;
                  return v8;
                }
                m_pInheritedProperties = v6->m_pInheritedProperties;
                if ( !m_pInheritedProperties || m_pInheritedProperties->m_pWriter != v6 )
                  goto LABEL_109;
                v90 = ToPropertyNumber(pDP->m_nIndex);
                v71 = ((1LL << v90) & *(_QWORD *)(v91 + 104)) == 0;
              }
              if ( !v71 )
              {
LABEL_81:
                DefaultValue = CValue::CopyConverted(v4, v9);
                v8 = DefaultValue;
                if ( DefaultValue >= 0 )
                  return v8;
                goto LABEL_82;
              }
              goto LABEL_109;
            case Float:
              goto LABEL_31;
            case TypeName:
              v83 = v9->m_value.m_typeHandle;
              CValue::ReleaseAndReset(v4);
              v4->m_flags.m_state.m_asOne &= 0xFFFFFFDC;
              v4->m_flags.m_state.m_asOne |= 0x5Cu;
              v4->m_value.m_typeHandle = v83;
              return v8;
            case Boolean:
              v50 = v9->m_value.m_bool;
              CValue::ReleaseAndReset(v4);
              v4->m_flags.m_state.m_asOne &= 0xFFFFFFC2;
              v4->m_flags.m_state.m_asOne |= 0x42u;
              v4->m_value.m_bool = v50;
              return v8;
            case Color:
              v75 = v9->m_value.m_any[0];
              CValue::ReleaseAndReset(v4);
              v4->m_flags.m_state.m_asOne &= 0xFFFFFFCF;
              v4->m_flags.m_state.m_asOne |= 0x4Fu;
              v4->m_value.m_any[0] = v75;
              return v8;
            case CornerRadius:
              CValue::ReleaseAndReset(v4);
              v4->m_flags.m_state.m_asOne = v4->m_flags.m_state.m_asOne & 0xFFFFFF80 | 0x15;
              v4->m_value.m_any[1] = pcStowedExceptions[1];
              v4->m_value.m_any[0] = (unsigned int)v9;
              return v8;
            case FontWeight:
              goto LABEL_175;
            case GridLength:
              CValue::ReleaseAndReset(v4);
              v4->m_flags.m_state.m_asOne = v4->m_flags.m_state.m_asOne & 0xFFFFFF80 | 0x14;
              v4->m_value.m_any[1] = pcStowedExceptions[1];
              v4->m_value.m_any[0] = (unsigned int)v9;
              return v8;
            case Int32:
              v67 = v9->m_value.m_any[0];
              CValue::ReleaseAndReset(v4);
              v4->m_flags.m_state.m_asOne &= 0xFFFFFFC4;
              v4->m_flags.m_state.m_asOne |= 0x44u;
              v4->m_value.m_any[0] = v67;
              return v8;
            case Point:
              CValue::ReleaseAndReset(v4);
              v4->m_flags.m_state.m_asOne = v4->m_flags.m_state.m_asOne & 0xFFFFFF80 | 0x10;
              v4->m_value.m_any[1] = pcStowedExceptions[1];
              v4->m_value.m_any[0] = (unsigned int)v9;
              return v8;
            case Rect:
              CValue::ReleaseAndReset(v4);
              v4->m_flags.m_state.m_asOne = v4->m_flags.m_state.m_asOne & 0xFFFFFF80 | 0x12;
              v4->m_value.m_any[1] = pcStowedExceptions[1];
              v4->m_value.m_any[0] = (unsigned int)v9;
              return v8;
            case Size:
              CValue::ReleaseAndReset(v4);
              v4->m_flags.m_state.m_asOne = v4->m_flags.m_state.m_asOne & 0xFFFFFF80 | 0x11;
              v4->m_value.m_any[1] = pcStowedExceptions[1];
              v4->m_value.m_any[0] = (unsigned int)v9;
              return v8;
            default:
              goto LABEL_11;
          }
        }
LABEL_60:
        v38 = (unsigned __int64)v9->m_value;
        if ( (*(_QWORD *)&v9->m_value & 1) != 0 )
        {
          v79 = WindowsDuplicateString((HSTRING)(v38 & 0xFFFFFFFFFFFFFFFEuLL), &string);
          if ( v79 < 0 )
          {
            OnFailure_2990_(v79);
            goto LABEL_67;
          }
        }
        else
        {
          if ( !v38 || (v39 = *(_DWORD *)(v38 + 8), (v39 & 0x40000000) == 0) )
          {
LABEL_68:
            v98[0].m_encodedStorage.RuntimeStringHandleMarker = v38;
            CValue::ReleaseAndReset(v4);
            v4->m_flags.m_state.m_asOne &= 0xFFFFFFCE;
            v4->m_flags.m_state.m_asOne |= 0x4Eu;
            if ( (v38 & 1) != 0 )
            {
              v64 = WindowsDuplicateString((HSTRING)(v38 & 0xFFFFFFFFFFFFFFFEuLL), &string);
              if ( v64 < 0 )
                goto LABEL_122;
            }
            else
            {
              if ( !v38 )
              {
                v38 = 0;
                goto LABEL_71;
              }
              v43 = *(_DWORD *)(v38 + 8);
              if ( (v43 & 0x40000000) == 0 )
              {
LABEL_71:
                string = (HSTRING)v38;
LABEL_72:
                v4->m_value.m_any[1] = HIDWORD(string);
                v4->m_value.m_any[0] = v38;
                xstring_ptr::~xstring_ptr(v98);
                return v8;
              }
              pcStowedExceptions[0] = 0;
              StringRawBuffer = *(HSTRING *)v38;
              if ( v43 < 0 )
              {
                StringRawBuffer = (HSTRING)WindowsGetStringRawBuffer(*(HSTRING *)v38, pcStowedExceptions);
                v63 = pcStowedExceptions[0];
              }
              else
              {
                v63 = v43 & 0x3FFFFFFF;
                pcStowedExceptions[0] = v63;
              }
              v64 = WindowsCreateString((PCNZWCH)StringRawBuffer, v63, &string);
              if ( v64 < 0 )
              {
LABEL_122:
                OnFailure_2990_(v64);
                pppStowedExceptions = 0;
                pcStowedExceptions[0] = 0;
                TraceForFailFast(-2147418113);
                OnNewFailureEncountered(-2147418113, 0, 0);
                GetStowedExceptionsForFailFast(&pppStowedExceptions, pcStowedExceptions);
                RoFailFastWithErrorContextInternal2(-2147418113, pcStowedExceptions[0], pppStowedExceptions);
                LODWORD(v38) = (_DWORD)string;
                goto LABEL_72;
              }
            }
            v38 = (unsigned __int64)string | 1;
            goto LABEL_71;
          }
          pcStowedExceptions[0] = 0;
          v40 = *(const wchar_t **)v38;
          if ( v39 < 0 )
          {
            v40 = WindowsGetStringRawBuffer(*(HSTRING *)v38, pcStowedExceptions);
            v41 = pcStowedExceptions[0];
          }
          else
          {
            v41 = v39 & 0x3FFFFFFF;
            pcStowedExceptions[0] = v41;
          }
          v42 = WindowsCreateString(v40, v41, &string);
          if ( v42 < 0 )
          {
            OnFailure_2990_(v42);
LABEL_67:
            pppStowedExceptions = 0;
            pcStowedExceptions[0] = 0;
            TraceForFailFast(-2147418113);
            OnNewFailureEncountered(-2147418113, 0, 0);
            GetStowedExceptionsForFailFast(&pppStowedExceptions, pcStowedExceptions);
            RoFailFastWithErrorContextInternal2(-2147418113, pcStowedExceptions[0], pppStowedExceptions);
            v38 = (unsigned __int64)string;
            goto LABEL_68;
          }
        }
        v38 = (unsigned __int64)string | 1;
        goto LABEL_68;
      }
      if ( (_DWORD)m_nPropertyTypeIndex == 292 )
      {
        CValue::ReleaseAndReset(v4);
        v4->m_flags.m_state.m_asOne = v4->m_flags.m_state.m_asOne & 0xFFFFFF80 | 0x13;
        v4->m_value.m_any[1] = pcStowedExceptions[1];
        v4->m_value.m_any[0] = (unsigned int)v9;
        return v8;
      }
      if ( (_DWORD)m_nPropertyTypeIndex != 418
        && (_DWORD)m_nPropertyTypeIndex != 454
        && (_DWORD)m_nPropertyTypeIndex != 649 )
      {
LABEL_11:
        if ( (unsigned __int16)m_nPropertyTypeIndex < 0x43Cu )
        {
          v11 = (CCustomClassInfo *)(&std::nothrow + 8 * m_nPropertyTypeIndex + 15053904);
        }
        else
        {
          EnterCriticalSection(&g_csStatic);
          v11 = DirectUI::DynamicMetadataStorage::GetInstance()->m_customTypesCache._Mypair._Myval2._Myfirst[(unsigned int)(m_nPropertyTypeIndex - 1084)]._Mypair._Myval2;
          LeaveCriticalSection(&g_csStatic);
        }
        if ( v11->m_nIndex == Enumerated || (v11->m_flags & 0x800) != 0 )
        {
          if ( (DirectUI::MetadataAPI::GetClassInfoByIndex(pDP->m_nPropertyTypeIndex)->m_flags & 0x20000) != 0 )
          {
            v92 = pDP->m_nPropertyTypeIndex;
            LOWORD(pcStowedExceptions[0]) = v9->m_value.m_enum8.m_value;
            HIWORD(pcStowedExceptions[0]) = DirectUI::MetadataAPI::GetClassInfoByIndex(v92)->m_nIndex;
            CValue::ReleaseAndReset(v4);
            v4->m_flags.m_state.m_asOne &= 0xFFFFFFE1;
            v93 = pcStowedExceptions[0];
            v4->m_flags.m_state.m_asOne |= 0x61u;
            v4->m_value.m_any[0] = v93;
          }
          else
          {
LABEL_175:
            LODWORD(string) = v9->m_value.m_any[0];
            v85 = (unsigned int)string;
            HIDWORD(string) = (unsigned __int16)CPropertyBase::GetPropertyType(&pDP->CPropertyBase)->m_nIndex;
            CValue::ReleaseAndReset(v4);
            v4->m_flags.m_state.m_asOne &= 0xFFFFFFC3;
            v4->m_flags.m_state.m_asOne |= 0x43u;
            v4->m_value.m_any[1] = HIDWORD(string);
            v4->m_value.m_any[0] = v85;
          }
          return v8;
        }
        v35 = v9->m_value;
        v36 = HIDWORD(*(_QWORD *)&v9->m_value);
        if ( *(_QWORD *)&v35 || !CDependencyProperty::IsOnDemandProperty(pDP) )
        {
          DefaultValueObject = 0;
          CValue::ReleaseAndReset(v4);
          v4->m_flags.m_state.m_asOne &= 0xFFFFFFD8;
          v4->m_flags.m_state.m_asOne |= 0x58u;
          v4->m_value.m_any[0] = v35.m_any[0];
          v4->m_value.m_any[1] = v36;
          if ( v35.m_any[0] | (unsigned __int64)(v36 << 32) )
          {
            CDependencyObject::AddRef((CDependencyObject *)(v35.m_any[0] | (unsigned __int64)(v36 << 32)));
            return v8;
          }
        }
        else
        {
          p_m_coreServices = &v6->m_sharedState.m_ptr->m_value.m_coreServices;
          v99.m_value.m_value = 0;
          v99.m_value.m_flags = 0;
          v99.m_spServiceProviderContext = 0;
          v99.m_pCore = *p_m_coreServices;
          DefaultValueObject = CDependencyProperty::CreateDefaultValueObject(pDP, v99.m_pCore, v4);
          if ( DefaultValueObject >= 0 )
          {
            IsPropertyDefault = CDependencyObject::IsPropertyDefault(v6, pDP);
            v53 = v6->__vftable;
            v54 = IsPropertyDefault;
            v100[0] = pDP;
            v100[1] = v4;
            v100[2] = v98;
            SetValue = v53->SetValue;
            *(_OWORD *)&v98[0].m_encodedStorage.Storage = 0;
            v101 = 0;
            v102 = 0;
            v56 = SetValue(v6, (const SetValueParams *)v100);
            if ( v98[1].m_encodedStorage.RuntimeStringHandleMarker )
              std::_Ref_count_base::_Decref((std::_Ref_count_base *)v98[1].m_encodedStorage.Storage);
            if ( v54 )
            {
              DefaultValueObject = 0;
              if ( !CQuirksMode2::QuirkPreRS2GetEffectiveValueField_ObjectIgnoreFailedLookup() )
                DefaultValueObject = v56;
              CDependencyObject::SetPropertyIsDefault(v6, pDP);
            }
            else
            {
              DefaultValueObject = v56;
            }
            if ( DefaultValueObject < 0 )
            {
              CValue::ReleaseAndReset(v4);
              v4->m_flags.m_state.m_asOne &= 0xFFFFFFD8;
              v4->m_flags.m_state.m_asOne |= 0x58u;
              v4->m_value = 0;
            }
          }
          CREATEPARAMETERS::~CREATEPARAMETERS(&v99);
        }
        v8 = DefaultValueObject;
        if ( DefaultValueObject < 0 )
          OnFailure_2990_(DefaultValueObject);
        return v8;
      }
      v34 = v9->m_value;
      CValue::ReleaseAndReset(v4);
      v4->m_flags.m_state.m_asOne &= ~0x20u;
      v4->m_flags.m_state.m_asOne |= 0x5Fu;
      v4->m_value = v34;
      CValueDetails::ValueStores::RefCounted<31,Flyweight::PropertyValueObjectBase>::AddRef(v4);
      return v8;
    }
LABEL_181:
    v8 = -2147467261;
    OnNewFailure_1172_((HRESULT)this);
    return v8;
  }
  v32 = c_aDependencyPropertyRuntimeData[v7].m_pfn(this, 0, 0, 0, pValue);
  v33 = v32;
  if ( v32 < 0 )
    OnFailure_2990_(v32);
  return v33;
}

```

## disassembly

```asm
0x1800301a0  mov     [rsp-8+arg_18], rbx
0x1800301a5  push    rbp
0x1800301a6  push    rsi
0x1800301a7  push    rdi
0x1800301a8  push    r12
0x1800301aa  push    r13
0x1800301ac  push    r14
0x1800301ae  push    r15
0x1800301b0  lea     rbp, [rsp-27h]
0x1800301b5  sub     rsp, 0E0h
0x1800301bc  mov     rax, cs:__security_cookie
0x1800301c3  xor     rax, rsp
0x1800301c6  mov     [rbp+57h+var_50], rax
0x1800301ca  mov     r11d, [pDP+8]
0x1800301ce  mov     rsi, pValue
0x1800301d1  mov     r12, pDP
0x1800301d4  mov     r13, this
0x1800301d7  test    r11b, 1
0x1800301db  jnz     loc_1800302A4
0x1800301e1  movzx   eax, word ptr [pDP]
0x1800301e4  lea     r15, std__nothrow
0x1800301eb  shl     rax, 5
0x1800301ef  bt      r11d, 8
0x1800301f4  jb      loc_18003052D
0x1800301fa  xor     edi, edi
0x1800301fc  movaps  [rsp+110h+var_40], xmm6
0x180030204  bt      r11d, 9
0x180030209  jb      loc_1800307B7
0x18003020f  movzx   r14d, word ptr [rax+r15+0C565E0h]
0x180030218  add     r14, this
0x18003021b  mov     qword ptr [rsp+110h+pcStowedExceptions], r14
0x180030220  test    r14, r14
0x180030223  jz      loc_180030EF3
0x180030229  movzx   ebx, word ptr [r12+2]
0x18003022f  cmp     ebx, 8Ch
0x180030235  jz      loc_1800304F9
0x18003023b  cmp     ebx, 47h ; 'G'
0x18003023e  jz      loc_180030613
0x180030244  cmp     ebx, 10Dh
0x18003024a  ja      loc_180030558
0x180030250  jz      loc_180030613
0x180030256  lea     eax, [rbx-0Ah]; switch 254 cases
0x180030259  cmp     eax, 0FDh
0x18003025e  jbe     loc_1800306F9
0x180030264  mov     eax, 43Ch; jumptable 000000018003070F default case, cases 11-39,41,44-98,100-111,113-128,130-158,160-164,166-186,188-229,231-242,244-262
0x180030269  cmp     bx, ax
0x18003026c  jb      loc_1800305A5
0x180030272  lea     this, ?g_csStatic@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180030279  call    cs:__imp_EnterCriticalSection
0x18003027f  call    ?GetInstance@DynamicMetadataStorage@DirectUI@@CAPEAV12@XZ; DirectUI::DynamicMetadataStorage::GetInstance(void)
0x180030284  lea     edx, [rbx-43Ch]
0x18003028a  lea     this, ?g_csStatic@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180030291  mov     rax, [rax+60h]
0x180030295  mov     rbx, [rax+pDP*8]
0x180030299  call    cs:__imp_LeaveCriticalSection
0x18003029f  jmp     loc_1800305B0
0x1800302a4  mov     rax, [this+28h]
0x1800302a8  test    rax, rax
0x1800302ab  jz      loc_180030380
0x1800302b1  mov     rbx, [rax+8]
0x1800302b5  mov     this, [rax]
0x1800302b8  mov     rax, 6666666666666667h
0x1800302c2  movzx   r10d, word ptr [pDP]
0x1800302c6  mov     pDP, rbx
0x1800302c9  sub     pDP, this
0x1800302cc  imul    pDP
0x1800302cf  mov     pValue, pDP
0x1800302d2  sar     pValue, 3
0x1800302d6  mov     rax, pValue
0x1800302d9  shr     rax, 3Fh
0x1800302dd  add     pValue, rax
0x1800302e0  test    pValue, pValue
0x1800302e3  jle     short loc_180030306
0x1800302e5  mov     pDP, pValue
0x1800302e8  shr     pDP, 1
0x1800302eb  lea     rax, [pDP+pDP*4]
0x1800302ef  cmp     [this+rax*4], r10w
0x1800302f4  lea     r9, [this+rax*4]
0x1800302f8  jb      loc_1800303AB
0x1800302fe  mov     pValue, pDP
0x180030301  test    pValue, pValue
0x180030304  jg      short loc_1800302E5
0x180030306  cmp     this, rbx
0x180030309  jz      short loc_180030380
0x18003030b  cmp     r10w, [this]
0x18003030f  jb      short loc_180030380
0x180030311  lea     rbx, [this+4]
0x180030315  xor     edi, edi
0x180030317  cmp     rsi, rbx
0x18003031a  jz      loc_1800303E2
0x180030320  mov     this, rsi; this
0x180030323  call    ?ReleaseAndReset@CValue@@QEAAXXZ; CValue::ReleaseAndReset(void)
0x180030328  mov     eax, [rbx+8]
0x18003032b  and     eax, 3Fh
0x18003032e  jz      loc_1800304DD
0x180030334  cmp     eax, 18h
0x180030337  jz      loc_18003040B
0x18003033d  cmp     eax, 8
0x180030340  jz      loc_18003080F
0x180030346  cmp     eax, 21h ; '!'
0x180030349  jz      loc_180030820
0x18003034f  dec     eax; switch 32 cases
0x180030351  cmp     eax, 1Fh
0x180030354  ja      def_18003036C; jumptable 000000018003036C default case, cases 8,24
0x18003035a  lea     r15, std__nothrow
0x180030361  mov     eax, ds:(jpt_18003036C - 180000000h)[r15+rax*4]
0x180030369  add     rax, r15
0x18003036c  jmp     rax; switch jump
0x18003036e  movzx   eax, byte ptr [rbx]; jumptable 000000018003036C case 2
0x180030371  and     dword ptr [rsi+8], 0FFFFFFC2h
0x180030375  or      dword ptr [rsi+8], 42h
0x180030379  mov     [rsi], al
0x18003037b  jmp     loc_1800304DD
0x180030380  test    r11b, 40h
0x180030384  jnz     loc_180030C48
0x18003038a  mov     pValue, rsi; pDefaultValue
0x18003038d  mov     pDP, r12; pDP
0x180030390  mov     this, r13; this
0x180030393  call    ?GetDefaultValue@CDependencyObject@@QEAAJPEBVCDependencyProperty@@PEAVCValue@@@Z; CDependencyObject::GetDefaultValue(CDependencyProperty const *,CValue *)
0x180030398  mov     edi, eax
0x18003039a  test    eax, eax
0x18003039c  jns     loc_180030870
0x1800303a2  mov     ecx, eax; failedFrameHR
0x1800303a4  call    OnFailure_2990_
0x1800303a9  jmp     short loc_1800303E2
0x1800303ab  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800303b2  lea     this, [r9+14h]
0x1800303b6  sub     rax, pDP
0x1800303b9  add     pValue, rax
0x1800303bc  jmp     loc_180030301
0x1800303c1  movss   xmm6, dword ptr [r14]; jumptable 000000018003070F case 42
0x1800303c6  mov     this, rsi; this
0x1800303c9  call    ?ReleaseAndReset@CValue@@QEAAXXZ; CValue::ReleaseAndReset(void)
0x1800303ce  and     dword ptr [rsi+8], 0FFFFFFC8h
0x1800303d2  or      dword ptr [rsi+8], 48h
0x1800303d6  movss   dword ptr [rsi], xmm6
0x1800303da  movaps  xmm6, [rsp+110h+var_40]; jumptable 000000018003070F case 10
0x1800303e2  mov     eax, edi
0x1800303e4  mov     this, [rbp+57h+var_50]
0x1800303e8  xor     this, rsp; StackCookie
0x1800303eb  call    __security_check_cookie
0x1800303f0  mov     rbx, [rsp+110h+arg_18]
0x1800303f8  add     rsp, 0E0h
0x1800303ff  pop     r15
0x180030401  pop     r14
0x180030403  pop     r13
0x180030405  pop     r12
0x180030407  pop     rdi
0x180030408  pop     rsi
0x180030409  pop     rbp
0x18003040a  retn
0x18003040b  mov     r12d, [rbx+4]
0x18003040f  mov     eax, [rbx]
0x180030411  mov     r14d, r12d
0x180030414  shl     r14, 20h
0x180030418  or      r14, rax
0x18003041b  mov     qword ptr [rbp+57h+outValue.m_value], rdi
0x18003041f  mov     qword ptr [rbp+57h+outValue.m_flags], rdi
0x180030423  mov     [rsp+110h+success], dil
0x180030428  jz      loc_180030DD8
0x18003042e  lea     pValue, [rsp+110h+success]; success
0x180030433  mov     this, r14; inValue
0x180030436  lea     pDP, [rbp+57h+outValue]; outValue
0x18003043a  call    ??$TryUnboxCDependencyObjectValue@VCValue@@@CValueConvert@@YAJPEAVCDependencyObject@@AEAVCValue@@AEA_N@Z; CValueConvert::TryUnboxCDependencyObjectValue<CValue>(CDependencyObject *,CValue &,bool &)
0x18003043f  mov     r15d, eax
0x180030442  test    eax, eax
0x180030444  js      loc_1800310D8
0x18003044a  mov     r15d, r14d
0x18003044d  cmp     [rsp+110h+success], dil
0x180030452  jnz     short loc_18003048E
0x180030454  lea     this, [rbp+57h+outValue]; this
0x180030458  call    ?ReleaseAndReset@CValue@@QEAAXXZ; CValue::ReleaseAndReset(void)
0x18003045d  mov     eax, dword ptr [rbp+57h+outValue.m_flags]
0x180030460  mov     this, r14
0x180030463  and     eax, 0FFFFFFD8h
0x180030466  mov     dword ptr [rbp+57h+outValue.m_value], r15d
0x18003046a  or      eax, 58h
0x18003046d  mov     dword ptr [rbp+57h+outValue.m_value+4], r12d
0x180030471  mov     dword ptr [rbp+57h+outValue.m_flags], eax
0x180030474  mov     rax, 0FFFFFFFF00000000h
0x18003047e  and     this, rax
0x180030481  mov     eax, r14d
0x180030484  or      this, rax; this
0x180030487  jz      short loc_18003048E
0x180030489  call    ?AddRef@CDependencyObject@@QEAAXXZ; CDependencyObject::AddRef(void)
0x18003048e  lea     rax, [rbp+57h+outValue]
0x180030492  cmp     rsi, rax
0x180030495  jz      short loc_1800304C8
0x180030497  mov     this, rsi; this
0x18003049a  call    ?ReleaseAndReset@CValue@@QEAAXXZ; CValue::ReleaseAndReset(void)
0x18003049f  mov     edx, dword ptr [rbp+57h+outValue.m_flags]
0x1800304a2  lea     pValue, [rbp+57h+outValue]; arg
0x1800304a6  and     edx, 3Fh; valueType
0x1800304a9  mov     this, rsi; this
0x1800304ac  call    ??$Dispatch@U?$Transfer@Utag_move@CValueDetails@@@Handlers@CValueDetails@@XVCValue@@@CValue@@AEAAXW4ValueType@@$$QEAV0@@Z; CValue::Dispatch<CValueDetails::Handlers::Transfer<CValueDetails::tag_move>,void,CValue>(ValueType,CValue &&)
0x1800304b1  mov     ecx, dword ptr [rbp+57h+outValue.m_flags]
0x1800304b4  xor     ecx, [rsi+8]
0x1800304b7  and     ecx, 7Fh
0x1800304ba  mov     qword ptr [rbp+57h+outValue.m_value], rdi
0x1800304be  xor     ecx, dword ptr [rbp+57h+outValue.m_flags]
0x1800304c1  mov     [rsi+8], ecx
0x1800304c4  mov     qword ptr [rbp+57h+outValue.m_flags], rdi
0x1800304c8  lea     this, [rbp+57h+outValue]; this
0x1800304cc  call    ??1CValue@@QEAA@XZ; CValue::~CValue(void)
0x1800304d1  mov     r15d, edi
0x1800304d4  test    r15d, r15d
0x1800304d7  js      loc_180030EA1
0x1800304dd  mov     ecx, [rsi+8]
0x1800304e0  mov     eax, ecx
0x1800304e2  and     eax, 7Fh
0x1800304e5  mov     [rsi+8], eax
0x1800304e8  xor     ecx, [rbx+8]
0x1800304eb  and     ecx, 7Fh
0x1800304ee  xor     ecx, [rbx+8]
0x1800304f1  mov     [rsi+8], ecx
0x1800304f4  jmp     loc_1800303E2
0x1800304f9  bt      r11d, 10h
0x1800304fe  jb      loc_1800303C1; jumptable 000000018003070F case 42
0x180030504  movsd   xmm6, qword ptr [r14]
0x180030509  mov     this, rsi; this
0x18003050c  movsd   qword ptr [rbp+57h+var_C0.m_encodedStorage.___u0], xmm6
0x180030511  call    ?ReleaseAndReset@CValue@@QEAAXXZ; CValue::ReleaseAndReset(void)
0x180030516  and     dword ptr [rsi+8], 0FFFFFFC9h
0x18003051a  or      dword ptr [rsi+8], 49h
0x18003051e  mov     eax, dword ptr [rbp+57h+var_C0.m_encodedStorage.___u0+4]
0x180030521  movss   dword ptr [rsi], xmm6
0x180030525  mov     [rsi+4], eax
0x180030528  jmp     loc_1800303DA; jumptable 000000018003070F case 10
0x18003052d  mov     rax, [rax+r15+0C565E0h]
0x180030535  xor     r9d, r9d
0x180030538  xor     r8d, r8d
0x18003053b  mov     [rsp+110h+var_F0], rsi
0x180030540  xor     edx, edx
0x180030542  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030547  mov     ebx, eax
0x180030549  test    eax, eax
0x18003054b  js      loc_180030D5A
0x180030551  mov     eax, ebx
0x180030553  jmp     loc_1800303E4
0x180030558  mov     ecx, ebx
0x18003055a  sub     ecx, 124h
0x180030560  jz      loc_18003099F
0x180030566  sub     ecx, 7Eh ; '~'
0x180030569  jz      short loc_18003057C
0x18003056b  sub     ecx, 24h ; '$'
0x18003056e  jz      short loc_18003057C
0x180030570  cmp     ecx, 0C3h
0x180030576  jnz     def_18003070F; jumptable 000000018003070F default case, cases 11-39,41,44-98,100-111,113-128,130-158,160-164,166-186,188-229,231-242,244-262
0x18003057c  mov     rbx, [r14]
0x18003057f  mov     this, rsi; this
0x180030582  call    ?ReleaseAndReset@CValue@@QEAAXXZ; CValue::ReleaseAndReset(void)
0x180030587  and     dword ptr [rsi+8], 0FFFFFFDFh
0x18003058b  mov     this, rsi; target
0x18003058e  or      dword ptr [rsi+8], 5Fh
0x180030592  mov     [rsi], ebx
0x180030594  shr     rbx, 20h
0x180030598  mov     [rsi+4], ebx
0x18003059b  call    ?AddRef@?$RefCounted@$0BP@VPropertyValueObjectBase@Flyweight@@@ValueStores@CValueDetails@@SAXAEAVCValue@@@Z; CValueDetails::ValueStores::RefCounted<31,Flyweight::PropertyValueObjectBase>::AddRef(CValue &)
0x1800305a0  jmp     loc_1800303DA; jumptable 000000018003070F case 10
0x1800305a5  lea     rbx, ds:0E5B450h[rbx*8]
0x1800305ad  add     rbx, r15
0x1800305b0  mov     eax, 95h
0x1800305b5  cmp     [rbx], ax
0x1800305b8  jz      loc_1800311CB
0x1800305be  test    dword ptr [rbx+4], 800h
0x1800305c5  jnz     loc_1800311CB
0x1800305cb  mov     rbx, [r14]
0x1800305ce  mov     r14, rbx
0x1800305d1  shr     r14, 20h
0x1800305d5  test    rbx, rbx
0x1800305d8  jz      loc_18003089F
0x1800305de  mov     this, rsi; this
0x1800305e1  mov     r15d, edi
0x1800305e4  call    ?ReleaseAndReset@CValue@@QEAAXXZ; CValue::ReleaseAndReset(void)
0x1800305e9  and     dword ptr [rsi+8], 0FFFFFFD8h
0x1800305ed  mov     this, r14
0x1800305f0  or      dword ptr [rsi+8], 58h
0x1800305f4  shl     this, 20h
0x1800305f8  mov     eax, ebx
0x1800305fa  or      this, rax; this
0x1800305fd  mov     [rsi], ebx
0x1800305ff  mov     [rsi+4], r14d
0x180030603  jz      loc_180030961
0x180030609  call    ?AddRef@CDependencyObject@@QEAAXXZ; CDependencyObject::AddRef(void)
0x18003060e  jmp     loc_1800303DA; jumptable 000000018003070F case 10
0x180030613  mov     rbx, [r14]
0x180030616  test    bl, 1
0x180030619  jnz     loc_180030CA1
0x18003061f  test    rbx, rbx
0x180030622  jz      loc_1800306AC
0x180030628  mov     edx, [rbx+8]
0x18003062b  bt      edx, 1Eh
0x18003062f  jnb     short loc_1800306AC
0x180030631  mov     [rsp+110h+pcStowedExceptions], edi
0x180030635  mov     rax, [rbx]
0x180030638  test    edx, edx
0x18003063a  js      loc_180031185
0x180030640  and     edx, 3FFFFFFFh; length
0x180030646  mov     [rsp+110h+pcStowedExceptions], edx
0x18003064a  lea     pValue, [rbp+57h+string]; string
  ... truncated ...
```
