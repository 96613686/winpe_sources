# XamlBinaryFormatSubReader2::TryRead(ObjectWriterNode &)

- ea: `0x1800fb480`
- end: `0x1800fd747`
- name: `?TryRead@XamlBinaryFormatSubReader2@@QEAA_NAEAVObjectWriterNode@@@Z`
- size: `8903`
- prototype: `bool __fastcall(XamlBinaryFormatSubReader2 *this, ObjectWriterNode *currentXamlNode)`
- caller_count: `9`
- callee_count: `38`
- tags: `loader_planting`

## callers

- `0x1800a487c`
- `0x1800acfd0`
- `0x1800adcd0`
- `0x1800af040`
- `0x1800fad58`
- `0x1800fb158`
- `0x1800fb180`
- `0x180251acc`
- `0x1809cd8bc`

## callees

- `0x180004bc0`
- `0x180004d2c`
- `0x1800710d0`
- `0x180073394`
- `0x1800743a0`
- `0x180091480`
- `0x1800915c4`
- `0x180096e7c`
- `0x180097b70`
- `0x18009860c`
- `0x1800ab600`
- `0x1800fb480`
- `0x1800fd750`
- `0x1800fdd4c`
- `0x1800fde74`
- `0x1800fe130`
- `0x180167664`
- `0x180174b40`
- `0x180174fd0`
- `0x180175184`
- `0x1801752c4`
- `0x180176008`
- `0x1803d69c0`
- `0x18041740c`
- `0x1804174e4`
- `0x180417598`
- `0x180498384`
- `0x1804a895c`
- `0x1804b8650`
- `0x18055c4bc`
- `0x180577a40`
- `0x1806877a8`
- `0x180687890`
- `0x1806d21d0`
- `0x1806d3fcc`
- `0x180741320`
- `0x18075a184`
- `0x180c0e010`

## import_xrefs

- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1800fc98c`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1800fca16`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1800fcaa6`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1800fc98c`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1800fca16`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1800fcaa6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fb9f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fc8b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fc8c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fb9f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fc8b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fc8c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800fc935`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800fc9bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800fca49`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800fc935`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800fc9bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800fca49`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800fd41c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800fd443`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800fd46a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800fd41c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800fd443`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800fd46a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800fcfbb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800fd0b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800fd1a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800fcfbb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800fd0b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800fd1a9`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
char __fastcall XamlBinaryFormatSubReader2::TryRead(
        XamlBinaryFormatSubReader2 *this,
        ObjectWriterNode *currentXamlNode)
{
  XamlBinaryFormatSubReader2 *v3; // rbx
  __int64 m_currentNodeStreamOffset; // rdx
  unsigned int v5; // r8d
  std::_Ref_count_base *v6; // rsi
  XamlType *v7; // rax
  volatile signed __int32 *v8; // rdx
  std::_Ref_count_base *v9; // rsi
  std::_Ref_count_base *v10; // rcx
  std::_Ref_count_base *v11; // rsi
  std::_Ref_count_base *v12; // rcx
  std::_Ref_count_base *v13; // rsi
  std::_Ref_count_base *v14; // rcx
  std::_Ref_count_base *v15; // rsi
  std::_Ref_count_base *v16; // rcx
  std::_Ref_count_base *v17; // rsi
  std::_Ref_count_base *v18; // rcx
  std::_Ref_count_base *v19; // rsi
  std::_Ref_count_base *v20; // rcx
  std::_Ref_count_base *v21; // rsi
  std::_Ref_count_base *v22; // rcx
  std::_Ref_count_base *v23; // rsi
  std::_Ref_count_base *v24; // rcx
  std::_Ref_count_base *v25; // rsi
  xstring_ptr *p_m_strValue; // rsi
  HSTRING v27; // rax
  int v28; // edx
  std::vector<std::pair<bool,xstring_ptr>> *p_m_vecResourceList; // rdi
  std::pair<bool,xstring_ptr> *Myfirst; // r14
  unsigned __int64 v31; // rbx
  std::pair<bool,xstring_ptr> *v32; // rsi
  std::pair<bool,xstring_ptr> *Mylast; // r10
  unsigned __int64 v34; // r15
  std::pair<bool,xstring_ptr> *i; // r15
  std::pair<bool,xstring_ptr> *v36; // rsi
  std::pair<bool,xstring_ptr> *j; // rbx
  ObjectWriterNode *p_that; // rcx
  std::_Ref_count_base *v39; // rsi
  XamlType *v40; // rax
  std::_Ref_count_base *v41; // rcx
  volatile signed __int32 *v42; // rdx
  volatile signed __int32 *v43; // rsi
  std::_Ref_count_base *v44; // rsi
  std::_Ref_count_base *v45; // rcx
  std::_Ref_count_base *v46; // rsi
  std::_Ref_count_base *v47; // rcx
  std::_Ref_count_base *v48; // rsi
  std::_Ref_count_base *v49; // rcx
  std::_Ref_count_base *v50; // rsi
  std::_Ref_count_base *v51; // rcx
  std::_Ref_count_base *v52; // rsi
  std::_Ref_count_base *v53; // rcx
  std::_Ref_count_base *v54; // rsi
  std::_Ref_count_base *v55; // rcx
  std::_Ref_count_base *v56; // rsi
  std::_Ref_count_base *v57; // rcx
  std::_Ref_count_base *v58; // rsi
  std::_Ref_count_base *v59; // rcx
  std::_Ref_count_base *v60; // rsi
  xstring_ptr *v61; // rsi
  HSTRING v62; // rax
  int v63; // edx
  std::vector<std::pair<bool,xstring_ptr>> *v64; // rdi
  std::pair<bool,xstring_ptr> *v65; // r14
  unsigned __int64 v66; // rbx
  std::pair<bool,xstring_ptr> *v67; // rsi
  std::pair<bool,xstring_ptr> *v68; // r10
  unsigned __int64 v69; // r15
  std::pair<bool,xstring_ptr> *k; // r15
  std::pair<bool,xstring_ptr> *v71; // rsi
  std::pair<bool,xstring_ptr> *m; // rbx
  std::_Ref_count_base *v74; // rcx
  std::_Ref_count_base *v75; // rsi
  std::_Ref_count_base *v76; // rcx
  std::_Ref_count_base *v77; // rsi
  std::_Ref_count_base *v78; // rcx
  std::_Ref_count_base *v79; // rsi
  std::_Ref_count_base *v80; // rcx
  std::_Ref_count_base *v81; // rsi
  std::_Ref_count_base *v82; // rcx
  std::_Ref_count_base *v83; // rsi
  std::_Ref_count_base *v84; // rcx
  std::_Ref_count_base *v85; // rsi
  std::_Ref_count_base *v86; // rcx
  std::_Ref_count_base *v87; // rsi
  std::_Ref_count_base *v88; // rcx
  std::_Ref_count_base *v89; // rsi
  xstring_ptr *v90; // rsi
  HSTRING v91; // rax
  int v92; // edx
  std::vector<std::pair<bool,xstring_ptr>> *v93; // rdi
  std::pair<bool,xstring_ptr> *v94; // r14
  unsigned __int64 v95; // rbx
  std::pair<bool,xstring_ptr> *v96; // rsi
  std::pair<bool,xstring_ptr> *v97; // r10
  unsigned __int64 v98; // r15
  std::pair<bool,xstring_ptr> *n; // r15
  std::pair<bool,xstring_ptr> *v100; // rsi
  std::pair<bool,xstring_ptr> *ii; // rbx
  const ObjectWriterNode *v102; // rax
  std::_Ref_count_base *v103; // rdx
  XamlType *v104; // rax
  std::_Ref_count_base *v105; // rcx
  std::_Ref_count_base *v106; // rdx
  volatile signed __int32 *v107; // rsi
  std::_Ref_count_base *v108; // rsi
  const ObjectWriterNode *v109; // rax
  HSTRING Buffer; // rax
  unsigned int v111; // edx
  int v112; // eax
  HSTRING StringRawBuffer; // rax
  unsigned int v114; // edx
  int v115; // eax
  wchar_t *v116; // rax
  unsigned int v117; // edx
  int v118; // eax
  std::_Ref_count_base *v119; // rdx
  XamlType *v120; // rax
  std::_Ref_count_base *v121; // rdx
  std::_Ref_count_base *v122; // rdx
  IXamlSchemaObject *v123; // rax
  std::_Ref_count_base *v124; // rcx
  std::_Ref_count_base *v125; // rdx
  std::_Ref_count_base *v126; // rdx
  XamlQualifiedObject *v127; // rax
  std::_Ref_count_base *v128; // rdx
  const ObjectWriterNode *v129; // rax
  std::_Ref_count_base *Rep; // rdx
  XamlQualifiedObject *Ptr; // rax
  std::_Ref_count_base *v132; // rdx
  std::_Ref_count_base *v133; // rdx
  XamlQualifiedObject *v134; // rax
  std::_Ref_count_base *v135; // rdx
  std::_Ref_count_base *v136; // rdx
  XamlType *v137; // rax
  std::_Ref_count_base *v138; // rdx
  std::_Ref_count_base *v139; // rdx
  IXamlSchemaObject *v140; // rax
  std::_Ref_count_base *v141; // rdx
  const ObjectWriterNode *v142; // rax
  const ObjectWriterNode *v143; // rax
  const ObjectWriterNode *v144; // rax
  const ObjectWriterNode *v145; // rax
  const ObjectWriterNode *v146; // rax
  const ObjectWriterNode *v147; // rax
  const ObjectWriterNode *v148; // rax
  const ObjectWriterNode *v149; // rax
  const ObjectWriterNode *ResourcePropertyBagNode; // rax
  std::pair<bool,xstring_ptr> *v151; // r8
  std::pair<bool,xstring_ptr> *v152; // r8
  std::pair<bool,xstring_ptr> *v153; // r8
  const ObjectWriterNode *inited; // rax
  const ObjectWriterNode *v155; // rax
  const ObjectWriterNode *v156; // rax
  const XamlLineInfo *v157; // rax
  ObjectWriterNodeType v158; // edx
  const ObjectWriterNode *v159; // rax
  const ObjectWriterNode *v160; // rax
  const ObjectWriterNode *v161; // rax
  const XamlLineInfo *v162; // rax
  ObjectWriterNodeType v163; // edx
  const ObjectWriterNode *v164; // rax
  const XamlLineInfo *LineInfo; // rax
  char v166; // r9
  ObjectWriterNodeType v167; // edx
  XamlLineInfo v168; // [rsp+20h] [rbp-E0h] BYREF
  std::shared_ptr<XamlType> result; // [rsp+38h] [rbp-C8h] BYREF
  XamlLineInfo v170; // [rsp+48h] [rbp-B8h] BYREF
  ObjectWriterNode __that; // [rsp+60h] [rbp-A0h] BYREF
  char v172; // [rsp+128h] [rbp+28h] BYREF
  __int128 v173; // [rsp+130h] [rbp+30h]
  XamlBinaryFormatSubReader2 *v174; // [rsp+140h] [rbp+40h]
  __int128 v175; // [rsp+148h] [rbp+48h]
  __int128 v176; // [rsp+158h] [rbp+58h]
  __int128 v177; // [rsp+168h] [rbp+68h]
  IXamlSchemaObject *v178; // [rsp+178h] [rbp+78h]
  std::_Ref_count_base *v179; // [rsp+180h] [rbp+80h]
  __int128 v180; // [rsp+188h] [rbp+88h]
  XamlQualifiedObject *v181; // [rsp+198h] [rbp+98h]
  std::_Ref_count_base *v182; // [rsp+1A0h] [rbp+A0h]
  __int128 v183; // [rsp+1A8h] [rbp+A8h]
  __int128 v184; // [rsp+1B8h] [rbp+B8h]
  const xstring_ptr_storage *v185; // [rsp+1C8h] [rbp+C8h] BYREF
  unsigned int v186; // [rsp+1D0h] [rbp+D0h]
  std::vector<DirectUI::TrackerPtr<Windows::Foundation::ITypedEventHandler<IInspectable *,IInspectable *>,1,0>> v187; // [rsp+1D8h] [rbp+D8h] BYREF
  char v188; // [rsp+1F0h] [rbp+F0h] BYREF
  __int128 v189; // [rsp+1F8h] [rbp+F8h]
  XamlBinaryFormatSubReader2 *v190; // [rsp+208h] [rbp+108h]
  __int128 v191; // [rsp+210h] [rbp+110h]
  __int128 v192; // [rsp+220h] [rbp+120h]
  __int128 v193; // [rsp+230h] [rbp+130h]
  IXamlSchemaObject *v194; // [rsp+240h] [rbp+140h]
  std::_Ref_count_base *v195; // [rsp+248h] [rbp+148h]
  __int128 v196; // [rsp+250h] [rbp+150h]
  __int128 v197; // [rsp+260h] [rbp+160h]
  __int128 v198; // [rsp+270h] [rbp+170h]
  __int128 v199; // [rsp+280h] [rbp+180h]
  const xstring_ptr_storage *Storage; // [rsp+290h] [rbp+190h] BYREF
  unsigned int v201; // [rsp+298h] [rbp+198h]
  std::vector<DirectUI::TrackerPtr<Windows::Foundation::ITypedEventHandler<IInspectable *,IInspectable *>,1,0>> v202; // [rsp+2A0h] [rbp+1A0h] BYREF
  char v203; // [rsp+2B8h] [rbp+1B8h] BYREF
  __int128 v204; // [rsp+2C0h] [rbp+1C0h]
  XamlBinaryFormatSubReader2 *v205; // [rsp+2D0h] [rbp+1D0h]
  __int128 v206; // [rsp+2D8h] [rbp+1D8h]
  __int128 v207; // [rsp+2E8h] [rbp+1E8h]
  __int128 v208; // [rsp+2F8h] [rbp+1F8h]
  __int128 v209; // [rsp+308h] [rbp+208h]
  __int128 v210; // [rsp+318h] [rbp+218h]
  __int128 v211; // [rsp+328h] [rbp+228h]
  __int128 v212; // [rsp+338h] [rbp+238h]
  __int128 v213; // [rsp+348h] [rbp+248h]
  const xstring_ptr_storage *v214; // [rsp+358h] [rbp+258h] BYREF
  unsigned int v215; // [rsp+360h] [rbp+260h]
  std::vector<DirectUI::TrackerPtr<Windows::Foundation::ITypedEventHandler<IInspectable *,IInspectable *>,1,0>> v216; // [rsp+368h] [rbp+268h] BYREF
  unsigned int pcStowedExceptions; // [rsp+3C0h] [rbp+2C0h] BYREF
  HSTRING newString; // [rsp+3D0h] [rbp+2D0h] BYREF
  HSTRING string; // [rsp+3D8h] [rbp+2D8h] BYREF

  v3 = this;
  LODWORD(newString) = 0;
  m_currentNodeStreamOffset = this->m_currentNodeStreamOffset;
  this->m_lastNodeStreamOffset = m_currentNodeStreamOffset;
  if ( (unsigned int)(m_currentNodeStreamOffset + 1) <= this->m_nodeStreamLength )
  {
    v5 = this->m_nodeStream[m_currentNodeStreamOffset];
    this->m_currentNodeStreamOffset = m_currentNodeStreamOffset + 1;
    if ( v5 > 0x8B )
      return 1;
    if ( v5 == 139 )
    {
      LineInfo = XamlBinaryFormatSubReader2::GetLineInfo(this, &v170);
      LOBYTE(v167) = v166;
      ObjectWriterNode::ObjectWriterNode(&__that, v167, LineInfo);
      ObjectWriterNode::operator=(currentXamlNode, &__that);
      goto LABEL_194;
    }
    if ( v5 <= 0x16 )
    {
      if ( v5 == 22 )
      {
        inited = XamlBinaryFormatSubReader2::ReadPushScopeCreateTypeWithTypeConvertedConstantBeginInitNode(
                   this,
                   &__that);
        ObjectWriterNode::operator=(currentXamlNode, inited);
        goto LABEL_194;
      }
      if ( v5 <= 0xC )
      {
        if ( v5 == 12 )
        {
          XamlBinaryFormatSubReader2::ReadConstantAsQO(this, (std::shared_ptr<XamlQualifiedObject> *)&result);
          *(_QWORD *)&v168.m_uiLineNumber = 0;
          if ( v3->m_lineStream )
          {
            v168.m_uiStreamOffset = v3->m_lastNodeStreamOffset;
          }
          else
          {
            v168.m_uiStreamOffset = 0;
            v3 = 0;
          }
          Rep = result._Rep;
          if ( result._Rep )
          {
            _InterlockedAdd((volatile signed __int32 *)&result._Rep->_Uses, 1u);
            Rep = result._Rep;
          }
          Ptr = (XamlQualifiedObject *)result._Ptr;
          __that.m_NodeType[0] = 12;
          *(_OWORD *)&__that.m_LineInfo.m_uiLineNumber = *(_OWORD *)&v168.m_uiLineNumber;
          __that.m_LineInfo.m_pSubReader = v3;
          memset(&__that.m_CustomWriterData, 0, 80);
          if ( Rep )
            _InterlockedAdd((volatile signed __int32 *)&Rep->_Uses, 1u);
          __that.m_spValue._Ptr = Ptr;
          __that.m_spValue._Rep = Rep;
          memset(&__that.m_spTextSyntaxConverter, 0, 32);
          __that.m_strValue.m_encodedStorage = xstring_ptr_constants::c_xencoded_string_ptr_null;
          std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CDependencyObject * const,CDeferredMapping::DeferredInfo>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CDependencyObject * const,CDeferredMapping::DeferredInfo>>>>>>((std::vector<DirectUI::TrackerPtr<Windows::Foundation::ITypedEventHandler<IInspectable *,IInspectable *>,1,0>> *)&__that.m_vecResourceList);
          if ( v132 )
            std::_Ref_count_base::_Decref(v132);
          if ( result._Rep )
            std::_Ref_count_base::_Decref(result._Rep);
        }
        else
        {
          switch ( v5 )
          {
            case 1u:
              v157 = XamlBinaryFormatSubReader2::GetLineInfo(this, &v170);
              LOBYTE(v158) = 1;
              ObjectWriterNode::ObjectWriterNode(&__that, v158, v157);
              ObjectWriterNode::operator=(currentXamlNode, &__that);
              goto LABEL_194;
            case 2u:
              *(_QWORD *)&v168.m_uiLineNumber = 0;
              if ( this->m_lineStream )
              {
                v168.m_uiStreamOffset = m_currentNodeStreamOffset;
              }
              else
              {
                v168.m_uiStreamOffset = 0;
                v3 = 0;
              }
              __that.m_NodeType[0] = 2;
              *(_OWORD *)&__that.m_LineInfo.m_uiLineNumber = *(_OWORD *)&v168.m_uiLineNumber;
              __that.m_LineInfo.m_pSubReader = v3;
              memset(&__that.m_CustomWriterData, 0, 128);
              __that.m_strValue.m_encodedStorage = xstring_ptr_constants::c_xencoded_string_ptr_null;
              std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CDependencyObject * const,CDeferredMapping::DeferredInfo>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CDependencyObject * const,CDeferredMapping::DeferredInfo>>>>>>((std::vector<DirectUI::TrackerPtr<Windows::Foundation::ITypedEventHandler<IInspectable *,IInspectable *>,1,0>> *)&__that.m_vecResourceList);
              ObjectWriterNode::operator=(currentXamlNode, &__that);
              goto LABEL_194;
            case 3u:
              v144 = XamlBinaryFormatSubReader2::ReadAddNamespaceNode(this, &__that);
              ObjectWriterNode::operator=(currentXamlNode, v144);
              goto LABEL_194;
            case 4u:
              v156 = XamlBinaryFormatSubReader2::ReadPushConstantNode(this, &__that);
              ObjectWriterNode::operator=(currentXamlNode, v156);
              goto LABEL_194;
          }
          if ( v5 != 7 )
          {
            switch ( v5 )
            {
              case 8u:
                *(_QWORD *)&v168.m_uiLineNumber = 0;
                if ( this->m_lineStream )
                {
                  v168.m_uiStreamOffset = m_currentNodeStreamOffset;
                }
                else
                {
                  v168.m_uiStreamOffset = 0;
                  v3 = 0;
                }
                __that.m_NodeType[0] = 8;
                *(_OWORD *)&__that.m_LineInfo.m_uiLineNumber = *(_OWORD *)&v168.m_uiLineNumber;
                __that.m_LineInfo.m_pSubReader = v3;
                memset(&__that.m_CustomWriterData, 0, 128);
                __that.m_strValue.m_encodedStorage = xstring_ptr_constants::c_xencoded_string_ptr_null;
                std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CDependencyObject * const,CDeferredMapping::DeferredInfo>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CDependencyObject * const,CDeferredMapping::DeferredInfo>>>>>>((std::vector<DirectUI::TrackerPtr<Windows::Foundation::ITypedEventHandler<IInspectable *,IInspectable *>,1,0>> *)&__that.m_vecResourceList);
                ObjectWriterNode::operator=(currentXamlNode, &__that);
                break;
              case 9u:
                *(_QWORD *)&v168.m_uiLineNumber = 0;
                if ( this->m_lineStream )
                {
                  v168.m_uiStreamOffset = m_currentNodeStreamOffset;
                  v168.m_pSubReader = this;
                }
                else
                {
                  v168.m_uiStreamOffset = 0;
                  v168.m_pSubReader = 0;
                }
                LOBYTE(m_currentNodeStreamOffset) = 9;
                ObjectWriterNode::ObjectWriterNode(
                  &__that,
                  (const ObjectWriterNodeType)m_currentNodeStreamOffset,
                  &v168);
                ObjectWriterNode::operator=(currentXamlNode, &__that);
                break;
              case 0xAu:
                v149 = XamlBinaryFormatSubReader2::ReadAddToDictionaryWithKeyNode(this, &__that);
                ObjectWriterNode::operator=(currentXamlNode, v149);
                break;
              case 0xBu:
                v109 = XamlBinaryFormatSubReader2::ReadMakeCheckPeerTypeNode(this, &__that);
                ObjectWriterNode::operator=(currentXamlNode, v109);
                break;
              default:
                return 1;
            }
            goto LABEL_194;
          }
          XamlBinaryFormatSubReader2::ReadXamlProperty(this, (std::shared_ptr<XamlProperty> *)&result);
          *(_QWORD *)&v168.m_uiLineNumber = 0;
          if ( v3->m_lineStream )
          {
            v168.m_uiStreamOffset = v3->m_lastNodeStreamOffset;
          }
          else
          {
            v168.m_uiStreamOffset = 0;
            v3 = 0;
          }
          v136 = result._Rep;
          if ( result._Rep )
          {
            _InterlockedAdd((volatile signed __int32 *)&result._Rep->_Uses, 1u);
            v136 = result._Rep;
          }
          v137 = result._Ptr;
          __that.m_NodeType[0] = 7;
          *(_OWORD *)&__that.m_LineInfo.m_uiLineNumber = *(_OWORD *)&v168.m_uiLineNumber;
          __that.m_LineInfo.m_pSubReader = v3;
          memset(&__that.m_CustomWriterData, 0, 48);
          if ( v136 )
            _InterlockedAdd((volatile signed __int32 *)&v136->_Uses, 1u);
          __that.m_spShared._Ptr = v137;
          __that.m_spShared._Rep = v136;
          memset(&__that.m_spShared2, 0, 64);
          __that.m_strValue.m_encodedStorage = xstring_ptr_constants::c_xencoded_string_ptr_null;
          std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CDependencyObject * const,CDeferredMapping::DeferredInfo>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CDependencyObject * const,CDeferredMapping::DeferredInfo>>>>>>((std::vector<DirectUI::TrackerPtr<Windows::Foundation::ITypedEventHandler<IInspectable *,IInspectable *>,1,0>> *)&__that.m_vecResourceList);
          if ( v138 )
            std::_Ref_count_base::_Decref(v138);
          if ( result._Rep )
            std::_Ref_count_base::_Decref(result._Rep);
        }
      }
      else
      {
        switch ( v5 )
        {
          case 0xDu:
            XamlBinaryFormatSubReader2::ReadConstantAsQO(this, (std::shared_ptr<XamlQualifiedObject> *)&result);
            *(_QWORD *)&v168.m_uiLineNumber = 0;
            if ( v3->m_lineStream )
            {
              v168.m_uiStreamOffset = v3->m_lastNodeStreamOffset;
            }
            else
            {
              v168.m_uiStreamOffset = 0;
              v3 = 0;
            }
            v126 = result._Rep;
            if ( result._Rep )
            {
              _InterlockedAdd((volatile signed __int32 *)&result._Rep->_Uses, 1u);
              v126 = result._Rep;
            }
            v127 = (XamlQualifiedObject *)result._Ptr;
            __that.m_NodeType[0] = 13;
            *(_OWORD *)&__that.m_LineInfo.m_uiLineNumber = *(_OWORD *)&v168.m_uiLineNumber;
            __that.m_LineInfo.m_pSubReader = v3;
            memset(&__that.m_CustomWriterData, 0, 80);
            if ( v126 )
              _InterlockedAdd((volatile signed __int32 *)&v126->_Uses, 1u);
            __that.m_spValue._Ptr = v127;
            __that.m_spValue._Rep = v126;
            memset(&__that.m_spTextSyntaxConverter, 0, 32);
            __that.m_strValue.m_encodedStorage = xstring_ptr_constants::c_xencoded_string_ptr_null;
            std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CDependencyObject * const,CDeferredMapping::DeferredInfo>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CDependencyObject * const,CDeferredMapping::DeferredInfo>>>>>>((std::vector<DirectUI::TrackerPtr<Windows::Foundation::ITypedEventHandler<IInspectable *,IInspectable *>,1,0>> *)&__that.m_vecResourceList);
            if ( v128 )
              std::_Ref_count_base::_Decref(v128);
            if ( result._Rep )
              std::_Ref_count_base::_Decref(result._Rep);
            break;
          case 0xEu:
            ResourcePropertyBagNode = XamlBinaryFormatSubReader2::ReadGetResourcePropertyBagNode(this, &__that);
            ObjectWriterNode::operator=(currentXamlNode, ResourcePropertyBagNode);
            goto LABEL_194;
          case 0xFu:
            v142 = XamlBinaryFormatSubReader2::ReadSetCustomRuntimeDataNode(this, &__that);
            ObjectWriterNode::operator=(currentXamlNode, v142);
            goto LABEL_194;
          case 0x11u:
            v147 = XamlBinaryFormatSubReader2::ReadSetDeferredPropertyNode(this, &__that);
            ObjectWriterNode::operator=(currentXamlNode, v147);
            goto LABEL_194;
          case 0x12u:
            v148 = XamlBinaryFormatSubReader2::ReadPushScopeAddNamespaceNode(this, &__that);
            ObjectWriterNode::operator=(currentXamlNode, v148);
            goto LABEL_194;
          case 0x13u:
            XamlBinaryFormatSubReader2::ReadXamlProperty(this, (std::shared_ptr<XamlProperty> *)&result);
            *(_QWORD *)&v168.m_uiLineNumber = 0;
            if ( v3->m_lineStream )
            {
              v168.m_uiStreamOffset = v3->m_lastNodeStreamOffset;
            }
            else
            {
              v168.m_uiStreamOffset = 0;
              v3 = 0;
            }
            v119 = result._Rep;
            if ( result._Rep )
            {
              _InterlockedAdd((volatile signed __int32 *)&result._Rep->_Uses, 1u);
              v119 = result._Rep;
            }
            v120 = result._Ptr;
            __that.m_NodeType[0] = 19;
            *(_OWORD *)&__that.m_LineInfo.m_uiLineNumber = *(_OWORD *)&v168.m_uiLineNumber;
            __that.m_LineInfo.m_pSubReader = v3;
            memset(&__that.m_CustomWriterData, 0, 48);
            if ( v119 )
              _InterlockedAdd((volatile signed __int32 *)&v119->_Uses, 1u);
            __that.m_spShared._Ptr = v120;
            __that.m_spShared._Rep = v119;
            memset(&__that.m_spShared2, 0, 64);
            __that.m_strValue.m_encodedStorage = xstring_ptr_constants::c_xencoded_string_ptr_null;
            std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CDependencyObject * const,CDeferredMapping::DeferredInfo>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CDependencyObject * const,CDeferredMapping::DeferredInfo>>>>>>((std::vector<DirectUI::TrackerPtr<Windows::Foundation::ITypedEventHandler<IInspectable *,IInspectable *>,1,0>> *)&__that.m_vecResourceList);
            if ( v121 )
              std::_Ref_count_base::_Decref(v121);
            if ( result._Rep )
              std::_Ref_count_base::_Decref(result._Rep);
            break;
          case 0x14u:
            XamlBinaryFormatSubReader2::ReadXamlType(this, &result);
            *(_QWORD *)&v168.m_uiLineNumber = 0;
            if ( v3->m_lineStream )
            {
              v168.m_uiStreamOffset = v3->m_lastNodeStreamOffset;
            }
            else
            {
              v168.m_uiStreamOffset = 0;
              v3 = 0;
            }
            v6 = result._Rep;
            if ( result._Rep )
            {
              _InterlockedAdd((volatile signed __int32 *)&result._Rep->_Uses, 1u);
              v6 = result._Rep;
            }
            v7 = result._Ptr;
            v188 = 20;
            v189 = *(_OWORD *)&v168.m_uiLineNumber;
            v190 = v3;
            v191 = 0;
            v192 = 0;
            v193 = 0;
            if ( v6 )
              _InterlockedAdd((volatile signed __int32 *)&v6->_Uses, 1u);
            v194 = v7;
            v195 = v6;
            v196 = 0;
            v197 = 0;
            v198 = 0;
            v199 = 0;
            Storage = xstring_ptr_constants::c_xencoded_string_ptr_null.Storage;
            std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CDependencyObject * const,CDeferredMapping::DeferredInfo>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CDependencyObject * const,CDeferredMapping::DeferredInfo>>>>>>(&v202);
            if ( v6 )
            {
              if ( _InterlockedExchangeAdd(v8, 0xFFFFFFFF) == 1 )
              {
                v6->_Destroy(v6);
                if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v6->_Weaks, 0xFFFFFFFF) == 1 )
                  v6->_Delete_this(v6);
              }
            }
            LODWORD(newString) = 32;
            v9 = result._Rep;
            if ( result._Rep )
            {
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)&result._Rep->_Uses, 0xFFFFFFFF) == 1 )
              {
                v9->_Destroy(v9);
                if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v9->_Weaks, 0xFFFFFFFF) == 1 )
                  v9->_Delete_this(v9);
              }
            }
            currentXamlNode->m_NodeType[0] = v188;
            *(_OWORD *)&currentXamlNode->m_LineInfo.m_uiLineNumber = v189;
            currentXamlNode->m_LineInfo.m_pSubReader = v190;
            v10 = (std::_Ref_count_base *)*((_QWORD *)&v191 + 1);
            if ( *((_QWORD *)&v191 + 1) )
              _InterlockedAdd((volatile signed __int32 *)(*((_QWORD *)&v191 + 1) + 8LL), 1u);
            currentXamlNode->m_CustomWriterData._Ptr = (CustomWriterRuntimeData *)v191;
            v11 = currentXamlNode->m_CustomWriterData._Rep;
            currentXamlNode->m_CustomWriterData._Rep = v10;
            if ( v11 )
            {
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v11->_Uses, 0xFFFFFFFF) == 1 )
              {
                v11->_Destroy(v11);
                if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v11->_Weaks, 0xFFFFFFFF) == 1 )
                  v11->_Delete_this(v11);
              }
            }
            v12 = (std::_Ref_count_base *)*((_QWORD *)&v192 + 1);
            if ( *((_QWORD *)&v192 + 1) )
              _InterlockedAdd((volatile signed __int32 *)(*((_QWORD *)&v192 + 1) + 8LL), 1u);
            currentXamlNode->m_CustomWriterNodeStream._Ptr = (SubObjectWriterResult *)v192;
            v13 = currentXamlNode->m_CustomWriterNodeStream._Rep;
            currentXamlNode->m_CustomWriterNodeStream._Rep = v12;
            if ( v13 )
            {
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v13->_Uses, 0xFFFFFFFF) == 1 )
              {
                v13->_Destroy(v13);
                if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v13->_Weaks, 0xFFFFFFFF) == 1 )
                  v13->_Delete_this(v13);
              }
            }
            v14 = (std::_Ref_count_base *)*((_QWORD *)&v193 + 1);
            if ( *((_QWORD *)&v193 + 1) )
              _InterlockedAdd((volatile signed __int32 *)(*((_QWORD *)&v193 + 1) + 8LL), 1u);
            currentXamlNode->m_spNodeList._Ptr = (ObjectWriterNodeList *)v193;
            v15 = currentXamlNode->m_spNodeList._Rep;
            currentXamlNode->m_spNodeList._Rep = v14;
            if ( v15 )
            {
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v15->_Uses, 0xFFFFFFFF) == 1 )
              {
                v15->_Destroy(v15);
                if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v15->_Weaks, 0xFFFFFFFF) == 1 )
                  v15->_Delete_this(v15);
              }
            }
            v16 = v195;
            if ( v195 )
              _InterlockedAdd((volatile signed __int32 *)&v195->_Uses, 1u);
            currentXamlNode->m_spShared._Ptr = v194;
            v17 = currentXamlNode->m_spShared._Rep;
            currentXamlNode->m_spShared._Rep = v16;
            if ( v17 )
            {
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v17->_Uses, 0xFFFFFFFF) == 1 )
              {
                v17->_Destroy(v17);
                if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v17->_Weaks, 0xFFFFFFFF) == 1 )
                  v17->_Delete_this(v17);
              }
            }
            v18 = (std::_Ref_count_base *)*((_QWORD *)&v196 + 1);
            if ( *((_QWORD *)&v196 + 1) )
              _InterlockedAdd((volatile signed __int32 *)(*((_QWORD *)&v196 + 1) + 8LL), 1u);
            currentXamlNode->m_spShared2._Ptr = (IXamlSchemaObject *)v196;
            v19 = currentXamlNode->m_spShared2._Rep;
            currentXamlNode->m_spShared2._Rep = v18;
            if ( v19 )
            {
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v19->_Uses, 0xFFFFFFFF) == 1 )
              {
                v19->_Destroy(v19);
                if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v19->_Weaks, 0xFFFFFFFF) == 1 )
                  v19->_Delete_this(v19);
              }
            }
            v20 = (std::_Ref_count_base *)*((_QWORD *)&v197 + 1);
            if ( *((_QWORD *)&v197 + 1) )
              _InterlockedAdd((volatile signed __int32 *)(*((_QWORD *)&v197 + 1) + 8LL), 1u);
            currentXamlNode->m_spValue._Ptr = (XamlQualifiedObject *)v197;
            v21 = currentXamlNode->m_spValue._Rep;
            currentXamlNode->m_spValue._Rep = v20;
            if ( v21 )
            {
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v21->_Uses, 0xFFFFFFFF) == 1 )
              {
                v21->_Destroy(v21);
                if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v21->_Weaks, 0xFFFFFFFF) == 1 )
                  v21->_Delete_this(v21);
              }
            }
            v22 = (std::_Ref_count_base *)*((_QWORD *)&v198 + 1);
            if ( *((_QWORD *)&v198 + 1) )
              _InterlockedAdd((volatile signed __int32 *)(*((_QWORD *)&v198 + 1) + 8LL), 1u);
            currentXamlNode->m_spTextSyntaxConverter._Ptr = (XamlTextSyntax *)v198;
            v23 = currentXamlNode->m_spTextSyntaxConverter._Rep;
            currentXamlNode->m_spTextSyntaxConverter._Rep = v22;
            if ( v23 )
            {
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v23->_Uses, 0xFFFFFFFF) == 1 )
              {
                v23->_Destroy(v23);
                if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v23->_Weaks, 0xFFFFFFFF) == 1 )
                  v23->_Delete_this(v23);
              }
            }
            v24 = (std::_Ref_count_base *)*((_QWORD *)&v199 + 1);
            if ( *((_QWORD *)&v199 + 1) )
              _InterlockedAdd((volatile signed __int32 *)(*((_QWORD *)&v199 + 1) + 8LL), 1u);
            currentXamlNode->m_spSubReader._Ptr = (XamlBinaryFormatSubReader2 *)v199;
            v25 = currentXamlNode->m_spSubReader._Rep;
            currentXamlNode->m_spSubReader._Rep = v24;
            if ( v25 )
            {
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v25->_Uses, 0xFFFFFFFF) == 1 )
              {
                v25->_Destroy(v25);
                if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v25->_Weaks, 0xFFFFFFFF) == 1 )
                  v25->_Delete_this(v25);
              }
            }
            p_m_strValue = &currentXamlNode->m_strValue;
            if ( &currentXamlNode->m_strValue == (xstring_ptr *)&Storage )
            {
LABEL_84:
              currentXamlNode->m_intValue = v201;
              p_m_vecResourceList = &currentXamlNode->m_vecResourceList;
              if ( p_m_vecResourceList != (std::vector<std::pair<bool,xstring_ptr>> *)&v202 )
              {
                Myfirst = (std::pair<bool,xstring_ptr> *)v202._Mypair._Myval2._Myfirst;
                v31 = ((char *)v202._Mypair._Myval2._Mylast - (char *)v202._Mypair._Myval2._Myfirst) / 12;
                v32 = p_m_vecResourceList->_Mypair._Myval2._Myfirst;
                if ( v31 > p_m_vecResourceList->_Mypair._Myval2._Myend - p_m_vecResourceList->_Mypair._Myval2._Myfirst )
                {
                  std::vector<std::pair<bool,xstring_ptr>>::_Clear_and_reserve_geometric(
                    p_m_vecResourceList,
                    ((char *)v202._Mypair._Myval2._Mylast - (char *)v202._Mypair._Myval2._Myfirst) / 12);
                  v151 = p_m_vecResourceList->_Mypair._Myval2._Myfirst;
                }
                else
                {
                  Mylast = p_m_vecResourceList->_Mypair._Myval2._Mylast;
                  v34 = Mylast - v32;
                  if ( v31 <= v34 )
                  {
                    for ( i = &v32[v31]; v31; --v31 )
                    {
                      v32->first = Myfirst->first;
                      xstring_ptr::operator=(&v32->second, &Myfirst->second);
                      ++v32;
                      ++Myfirst;
                    }
                    v36 = p_m_vecResourceList->_Mypair._Myval2._Mylast;
                    for ( j = i; j != v36; ++j )
                      xstring_ptr::~xstring_ptr(&j->second);
                    p_m_vecResourceList->_Mypair._Myval2._Mylast = i;
                    goto LABEL_92;
                  }
                  while ( v32 != Mylast )
                  {
                    v32->first = Myfirst->first;
                    xstring_ptr::operator=(&v32->second, &Myfirst->second);
                    ++v32;
                    ++Myfirst;
                    Mylast = p_m_vecResourceList->_Mypair._Myval2._Mylast;
                  }
                  v31 -= v34;
                  v151 = Mylast;
                }
                p_m_vecResourceList->_Mypair._Myval2._Mylast = std::_Uninitialized_copy_n<std::pair<bool,xstring_ptr> *,std::allocator<std::pair<bool,xstring_ptr>>>(
                                                                 Myfirst,
                                                                 v31,
                                                                 v151,
                                                                 (std::allocator<std::pair<bool,xstring_ptr> > *)p_m_vecResourceList);
              }
LABEL_92:
              p_that = (ObjectWriterNode *)&v188;
LABEL_195:
              ObjectWriterNode::~ObjectWriterNode(p_that);
              return 1;
            }
            v27 = (HSTRING)Storage;
            if ( ((unsigned __int8)Storage & 1) != 0 )
            {
              v112 = WindowsDuplicateString((HSTRING)((unsigned __int64)Storage & 0xFFFFFFFFFFFFFFFEuLL), &string);
              if ( v112 < 0 )
                goto LABEL_297;
            }
            else
            {
              if ( !Storage )
              {
                v27 = 0;
                goto LABEL_80;
              }
              v28 = *((_DWORD *)Storage + 2);
              if ( (v28 & 0x40000000) == 0 )
              {
LABEL_80:
                string = v27;
LABEL_81:
                if ( (p_m_strValue->m_encodedStorage.RuntimeStringHandleMarker & 1) != 0 )
                  WindowsDeleteString((HSTRING)(p_m_strValue->m_encodedStorage.RuntimeStringHandleMarker
                                              & 0xFFFFFFFFFFFFFFFEuLL));
                p_m_strValue->m_encodedStorage.RuntimeStringHandleMarker = (unsigned __int64)string;
                goto LABEL_84;
              }
              pcStowedExceptions = 0;
              Buffer = (HSTRING)Storage->Buffer;
              if ( v28 < 0 )
              {
                Buffer = (HSTRING)WindowsGetStringRawBuffer(Storage->Handle, &pcStowedExceptions);
                v111 = pcStowedExceptions;
              }
              else
              {
                v111 = v28 & 0x3FFFFFFF;
                pcStowedExceptions = v111;
              }
              v112 = WindowsCreateString((PCNZWCH)Buffer, v111, &string);
              if ( v112 < 0 )
              {
LABEL_297:
                OnFailure_2990_(v112);
                result._Ptr = 0;
                pcStowedExceptions = 0;
                TraceForFailFast(-2147418113);
                OnNewFailureEncountered(-2147418113, 0, 0);
                GetStowedExceptionsForFailFast((_STOWED_EXCEPTION_INFORMATION_V2 ***)&result, &pcStowedExceptions);
                RoFailFastWithErrorContextInternal2(
                  -2147418113,
                  pcStowedExceptions,
                  (struct _STOWED_EXCEPTION_INFORMATION_V2 **const)result._Ptr);
                goto LABEL_81;
              }
            }
            string = (HSTRING)((unsigned __int64)string | 1);
            goto LABEL_81;
          case 0x15u:
            v143 = XamlBinaryFormatSubReader2::ReadPushScopeCreateTypeWithConstantBeginInitNode(this, &__that);
            ObjectWriterNode::operator=(currentXamlNode, v143);
LABEL_194:
            p_that = &__that;
            goto LABEL_195;
          default:
            return 1;
        }
      }
      ObjectWriterNode::operator=(currentXamlNode, &__that);
      goto LABEL_194;
    }
    if ( (unsigned __int8)v5 <= 0x1Fu )
    {
      if ( (_BYTE)v5 == 31 )
      {
        v129 = XamlBinaryFormatSubReader2::ReadSetValueFromTemplateBindingNode(this, &__that);
        ObjectWriterNode::operator=(currentXamlNode, v129);
        goto LABEL_194;
      }
      switch ( v5 )
      {
        case 0x17u:
          v146 = XamlBinaryFormatSubReader2::ReadCreateTypeBeginInitNode(this, &__that);
          ObjectWriterNode::operator=(currentXamlNode, v146);
          goto LABEL_194;
        case 0x18u:
          v161 = XamlBinaryFormatSubReader2::ReadCreateTypeWithConstantBeginInitNode(this, &__that);
          ObjectWriterNode::operator=(currentXamlNode, v161);
          goto LABEL_194;
        case 0x19u:
          v160 = XamlBinaryFormatSubReader2::ReadCreateTypeWithTypeConvertedConstantBeginInitNode(this, &__that);
          ObjectWriterNode::operator=(currentXamlNode, v160);
          goto LABEL_194;
        case 0x1Au:
          XamlBinaryFormatSubReader2::ReadXamlProperty(this, (std::shared_ptr<XamlProperty> *)&result);
          XamlBinaryFormatSubReader2::ReadConstantAsQO(v3, (std::shared_ptr<XamlQualifiedObject> *)&v168);
          *(_QWORD *)&v170.m_uiLineNumber = 0;
          if ( v3->m_lineStream )
          {
            v170.m_uiStreamOffset = v3->m_lastNodeStreamOffset;
          }
          else
          {
            v170.m_uiStreamOffset = 0;
            v3 = 0;
          }
          v39 = result._Rep;
          if ( result._Rep )
          {
            _InterlockedAdd((volatile signed __int32 *)&result._Rep->_Uses, 1u);
            v39 = result._Rep;
          }
          v40 = result._Ptr;
          v172 = 26;
          v173 = *(_OWORD *)&v170.m_uiLineNumber;
          v174 = v3;
          v175 = 0;
          v176 = 0;
          v177 = 0;
          if ( v39 )
            _InterlockedAdd((volatile signed __int32 *)&v39->_Uses, 1u);
          v178 = v40;
          v179 = v39;
          v180 = 0;
          v41 = *(std::_Ref_count_base **)&v168.m_uiStreamOffset;
          if ( *(_QWORD *)&v168.m_uiStreamOffset )
          {
            _InterlockedAdd((volatile signed __int32 *)(*(_QWORD *)&v168.m_uiStreamOffset + 8LL), 1u);
            v41 = *(std::_Ref_count_base **)&v168.m_uiStreamOffset;
          }
          v181 = *(XamlQualifiedObject **)&v168.m_uiLineNumber;
          v182 = v41;
          v183 = 0;
          v184 = 0;
          v185 = xstring_ptr_constants::c_xencoded_string_ptr_null.Storage;
          std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CDependencyObject * const,CDeferredMapping::DeferredInfo>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CDependencyObject * const,CDeferredMapping::DeferredInfo>>>>>>(&v187);
          if ( v39 )
          {
            if ( _InterlockedExchangeAdd(v42, 0xFFFFFFFF) == 1 )
            {
              v39->_Destroy(v39);
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v39->_Weaks, 0xFFFFFFFF) == 1 )
                v39->_Delete_this(v39);
            }
          }
          LODWORD(newString) = 256;
          v43 = *(volatile signed __int32 **)&v168.m_uiStreamOffset;
          if ( *(_QWORD *)&v168.m_uiStreamOffset )
          {
            if ( _InterlockedExchangeAdd(
                   (volatile signed __int32 *)(*(_QWORD *)&v168.m_uiStreamOffset + 8LL),
                   0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v43)(v43);
              if ( _InterlockedExchangeAdd(v43 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v43 + 8LL))(v43);
            }
          }
          v44 = result._Rep;
          if ( result._Rep )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)&result._Rep->_Uses, 0xFFFFFFFF) == 1 )
            {
              v44->_Destroy(v44);
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v44->_Weaks, 0xFFFFFFFF) == 1 )
                v44->_Delete_this(v44);
            }
          }
          currentXamlNode->m_NodeType[0] = v172;
          *(_OWORD *)&currentXamlNode->m_LineInfo.m_uiLineNumber = v173;
          currentXamlNode->m_LineInfo.m_pSubReader = v174;
          v45 = (std::_Ref_count_base *)*((_QWORD *)&v175 + 1);
          if ( *((_QWORD *)&v175 + 1) )
            _InterlockedAdd((volatile signed __int32 *)(*((_QWORD *)&v175 + 1) + 8LL), 1u);
          currentXamlNode->m_CustomWriterData._Ptr = (CustomWriterRuntimeData *)v175;
          v46 = currentXamlNode->m_CustomWriterData._Rep;
          currentXamlNode->m_CustomWriterData._Rep = v45;
          if ( v46 )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v46->_Uses, 0xFFFFFFFF) == 1 )
            {
              v46->_Destroy(v46);
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v46->_Weaks, 0xFFFFFFFF) == 1 )
                v46->_Delete_this(v46);
            }
          }
          v47 = (std::_Ref_count_base *)*((_QWORD *)&v176 + 1);
          if ( *((_QWORD *)&v176 + 1) )
            _InterlockedAdd((volatile signed __int32 *)(*((_QWORD *)&v176 + 1) + 8LL), 1u);
          currentXamlNode->m_CustomWriterNodeStream._Ptr = (SubObjectWriterResult *)v176;
          v48 = currentXamlNode->m_CustomWriterNodeStream._Rep;
          currentXamlNode->m_CustomWriterNodeStream._Rep = v47;
          if ( v48 )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v48->_Uses, 0xFFFFFFFF) == 1 )
            {
              v48->_Destroy(v48);
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v48->_Weaks, 0xFFFFFFFF) == 1 )
                v48->_Delete_this(v48);
            }
          }
          v49 = (std::_Ref_count_base *)*((_QWORD *)&v177 + 1);
          if ( *((_QWORD *)&v177 + 1) )
            _InterlockedAdd((volatile signed __int32 *)(*((_QWORD *)&v177 + 1) + 8LL), 1u);
          currentXamlNode->m_spNodeList._Ptr = (ObjectWriterNodeList *)v177;
          v50 = currentXamlNode->m_spNodeList._Rep;
          currentXamlNode->m_spNodeList._Rep = v49;
          if ( v50 )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v50->_Uses, 0xFFFFFFFF) == 1 )
            {
              v50->_Destroy(v50);
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v50->_Weaks, 0xFFFFFFFF) == 1 )
                v50->_Delete_this(v50);
            }
          }
          v51 = v179;
          if ( v179 )
            _InterlockedAdd((volatile signed __int32 *)&v179->_Uses, 1u);
          currentXamlNode->m_spShared._Ptr = v178;
          v52 = currentXamlNode->m_spShared._Rep;
          currentXamlNode->m_spShared._Rep = v51;
          if ( v52 )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v52->_Uses, 0xFFFFFFFF) == 1 )
            {
              v52->_Destroy(v52);
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v52->_Weaks, 0xFFFFFFFF) == 1 )
                v52->_Delete_this(v52);
            }
          }
          v53 = (std::_Ref_count_base *)*((_QWORD *)&v180 + 1);
          if ( *((_QWORD *)&v180 + 1) )
            _InterlockedAdd((volatile signed __int32 *)(*((_QWORD *)&v180 + 1) + 8LL), 1u);
          currentXamlNode->m_spShared2._Ptr = (IXamlSchemaObject *)v180;
          v54 = currentXamlNode->m_spShared2._Rep;
          currentXamlNode->m_spShared2._Rep = v53;
          if ( v54 )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v54->_Uses, 0xFFFFFFFF) == 1 )
            {
              v54->_Destroy(v54);
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v54->_Weaks, 0xFFFFFFFF) == 1 )
                v54->_Delete_this(v54);
            }
          }
          v55 = v182;
          if ( v182 )
            _InterlockedAdd((volatile signed __int32 *)&v182->_Uses, 1u);
          currentXamlNode->m_spValue._Ptr = v181;
          v56 = currentXamlNode->m_spValue._Rep;
          currentXamlNode->m_spValue._Rep = v55;
          if ( v56 )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v56->_Uses, 0xFFFFFFFF) == 1 )
            {
              v56->_Destroy(v56);
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v56->_Weaks, 0xFFFFFFFF) == 1 )
                v56->_Delete_this(v56);
            }
          }
          v57 = (std::_Ref_count_base *)*((_QWORD *)&v183 + 1);
          if ( *((_QWORD *)&v183 + 1) )
            _InterlockedAdd((volatile signed __int32 *)(*((_QWORD *)&v183 + 1) + 8LL), 1u);
          currentXamlNode->m_spTextSyntaxConverter._Ptr = (XamlTextSyntax *)v183;
          v58 = currentXamlNode->m_spTextSyntaxConverter._Rep;
          currentXamlNode->m_spTextSyntaxConverter._Rep = v57;
          if ( v58 )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v58->_Uses, 0xFFFFFFFF) == 1 )
            {
              v58->_Destroy(v58);
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v58->_Weaks, 0xFFFFFFFF) == 1 )
                v58->_Delete_this(v58);
            }
          }
          v59 = (std::_Ref_count_base *)*((_QWORD *)&v184 + 1);
          if ( *((_QWORD *)&v184 + 1) )
            _InterlockedAdd((volatile signed __int32 *)(*((_QWORD *)&v184 + 1) + 8LL), 1u);
          currentXamlNode->m_spSubReader._Ptr = (XamlBinaryFormatSubReader2 *)v184;
          v60 = currentXamlNode->m_spSubReader._Rep;
          currentXamlNode->m_spSubReader._Rep = v59;
          if ( v60 )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v60->_Uses, 0xFFFFFFFF) == 1 )
            {
              v60->_Destroy(v60);
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v60->_Weaks, 0xFFFFFFFF) == 1 )
                v60->_Delete_this(v60);
            }
          }
          v61 = &currentXamlNode->m_strValue;
          if ( &currentXamlNode->m_strValue == (xstring_ptr *)&v185 )
          {
LABEL_175:
            currentXamlNode->m_intValue = v186;
            v64 = &currentXamlNode->m_vecResourceList;
            if ( v64 != (std::vector<std::pair<bool,xstring_ptr>> *)&v187 )
            {
              v65 = (std::pair<bool,xstring_ptr> *)v187._Mypair._Myval2._Myfirst;
              v66 = ((char *)v187._Mypair._Myval2._Mylast - (char *)v187._Mypair._Myval2._Myfirst) / 12;
              v67 = v64->_Mypair._Myval2._Myfirst;
              if ( v66 > v64->_Mypair._Myval2._Myend - v64->_Mypair._Myval2._Myfirst )
              {
                std::vector<std::pair<bool,xstring_ptr>>::_Clear_and_reserve_geometric(
                  v64,
                  ((char *)v187._Mypair._Myval2._Mylast - (char *)v187._Mypair._Myval2._Myfirst) / 12);
                v152 = v64->_Mypair._Myval2._Myfirst;
              }
              else
              {
                v68 = v64->_Mypair._Myval2._Mylast;
                v69 = v68 - v67;
                if ( v66 <= v69 )
                {
                  for ( k = &v67[v66]; v66; --v66 )
                  {
                    v67->first = v65->first;
                    xstring_ptr::operator=(&v67->second, &v65->second);
                    ++v67;
                    ++v65;
                  }
                  v71 = v64->_Mypair._Myval2._Mylast;
                  for ( m = k; m != v71; ++m )
                    xstring_ptr::~xstring_ptr(&m->second);
                  v64->_Mypair._Myval2._Mylast = k;
                  goto LABEL_183;
                }
                while ( v67 != v68 )
                {
                  v67->first = v65->first;
                  xstring_ptr::operator=(&v67->second, &v65->second);
                  ++v67;
                  ++v65;
                  v68 = v64->_Mypair._Myval2._Mylast;
                }
                v66 -= v69;
                v152 = v68;
              }
              v64->_Mypair._Myval2._Mylast = std::_Uninitialized_copy_n<std::pair<bool,xstring_ptr> *,std::allocator<std::pair<bool,xstring_ptr>>>(
                                               v65,
                                               v66,
                                               v152,
                                               (std::allocator<std::pair<bool,xstring_ptr> > *)v64);
            }
LABEL_183:
            p_that = (ObjectWriterNode *)&v172;
            goto LABEL_195;
          }
          v62 = (HSTRING)v185;
          if ( ((unsigned __int8)v185 & 1) != 0 )
          {
            v115 = WindowsDuplicateString((HSTRING)((unsigned __int64)v185 & 0xFFFFFFFFFFFFFFFEuLL), &string);
            if ( v115 < 0 )
              goto LABEL_301;
          }
          else
          {
            if ( !v185 )
            {
              v62 = 0;
              goto LABEL_171;
            }
            v63 = *((_DWORD *)v185 + 2);
            if ( (v63 & 0x40000000) == 0 )
            {
LABEL_171:
              string = v62;
LABEL_172:
              if ( (v61->m_encodedStorage.RuntimeStringHandleMarker & 1) != 0 )
                WindowsDeleteString((HSTRING)(v61->m_encodedStorage.RuntimeStringHandleMarker & 0xFFFFFFFFFFFFFFFEuLL));
              v61->m_encodedStorage.RuntimeStringHandleMarker = (unsigned __int64)string;
              goto LABEL_175;
            }
            pcStowedExceptions = 0;
            StringRawBuffer = (HSTRING)v185->Buffer;
            if ( v63 < 0 )
            {
              StringRawBuffer = (HSTRING)WindowsGetStringRawBuffer(v185->Handle, &pcStowedExceptions);
              v114 = pcStowedExceptions;
            }
            else
            {
              v114 = v63 & 0x3FFFFFFF;
              pcStowedExceptions = v114;
            }
            v115 = WindowsCreateString((PCNZWCH)StringRawBuffer, v114, &string);
            if ( v115 < 0 )
            {
LABEL_301:
              OnFailure_2990_(v115);
              result._Ptr = 0;
              pcStowedExceptions = 0;
              TraceForFailFast(-2147418113);
              OnNewFailureEncountered(-2147418113, 0, 0);
              GetStowedExceptionsForFailFast((_STOWED_EXCEPTION_INFORMATION_V2 ***)&result, &pcStowedExceptions);
              RoFailFastWithErrorContextInternal2(
                -2147418113,
                pcStowedExceptions,
                (struct _STOWED_EXCEPTION_INFORMATION_V2 **const)result._Ptr);
              goto LABEL_172;
            }
          }
          string = (HSTRING)((unsigned __int64)string | 1);
          goto LABEL_172;
        case 0x1Bu:
          v102 = XamlBinaryFormatSubReader2::ReadSetValueTypeConvertedConstantNode(this, &__that);
          ObjectWriterNode::operator=(currentXamlNode, v102);
          goto LABEL_194;
        case 0x1Cu:
          v159 = XamlBinaryFormatSubReader2::ReadSetValueTypeConvertedResolvedPropertyNode(this, &__that);
          ObjectWriterNode::operator=(currentXamlNode, v159);
          goto LABEL_194;
        case 0x1Du:
          v145 = XamlBinaryFormatSubReader2::ReadSetValueTypeConvertedResolvedTypeNode(this, &__that);
          ObjectWriterNode::operator=(currentXamlNode, v145);
          goto LABEL_194;
      }
      XamlBinaryFormatSubReader2::ReadXamlProperty(this, (std::shared_ptr<XamlProperty> *)&v168);
      XamlBinaryFormatSubReader2::ReadConstantAsQO(v3, (std::shared_ptr<XamlQualifiedObject> *)&result);
      *(_QWORD *)&v170.m_uiLineNumber = 0;
      if ( v3->m_lineStream )
      {
        v170.m_uiStreamOffset = v3->m_lastNodeStreamOffset;
      }
      else
      {
        v170.m_uiStreamOffset = 0;
        v3 = 0;
      }
      v122 = *(std::_Ref_count_base **)&v168.m_uiStreamOffset;
      if ( *(_QWORD *)&v168.m_uiStreamOffset )
      {
        _InterlockedAdd((volatile signed __int32 *)(*(_QWORD *)&v168.m_uiStreamOffset + 8LL), 1u);
        v122 = *(std::_Ref_count_base **)&v168.m_uiStreamOffset;
      }
      v123 = *(IXamlSchemaObject **)&v168.m_uiLineNumber;
      __that.m_NodeType[0] = 30;
      *(_OWORD *)&__that.m_LineInfo.m_uiLineNumber = *(_OWORD *)&v170.m_uiLineNumber;
      __that.m_LineInfo.m_pSubReader = v3;
      memset(&__that.m_CustomWriterData, 0, 48);
      if ( v122 )
        _InterlockedAdd((volatile signed __int32 *)&v122->_Uses, 1u);
      __that.m_spShared._Ptr = v123;
      __that.m_spShared._Rep = v122;
      __that.m_spShared2 = 0;
      v124 = result._Rep;
      if ( result._Rep )
      {
        _InterlockedAdd((volatile signed __int32 *)&result._Rep->_Uses, 1u);
        v124 = result._Rep;
      }
      __that.m_spValue._Ptr = (XamlQualifiedObject *)result._Ptr;
      __that.m_spValue._Rep = v124;
      memset(&__that.m_spTextSyntaxConverter, 0, 32);
      __that.m_strValue.m_encodedStorage = xstring_ptr_constants::c_xencoded_string_ptr_null;
      std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CDependencyObject * const,CDeferredMapping::DeferredInfo>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CDependencyObject * const,CDeferredMapping::DeferredInfo>>>>>>((std::vector<DirectUI::TrackerPtr<Windows::Foundation::ITypedEventHandler<IInspectable *,IInspectable *>,1,0>> *)&__that.m_vecResourceList);
      if ( v125 )
        std::_Ref_count_base::_Decref(v125);
      if ( result._Rep )
        std::_Ref_count_base::_Decref(result._Rep);
      if ( *(_QWORD *)&v168.m_uiStreamOffset )
        std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)&v168.m_uiStreamOffset);
LABEL_396:
      ObjectWriterNode::operator=(currentXamlNode, &__that);
      goto LABEL_194;
    }
    if ( v5 == 32 )
    {
      XamlBinaryFormatSubReader2::ReadXamlProperty(this, (std::shared_ptr<XamlProperty> *)&v168);
      *(_QWORD *)&v170.m_uiLineNumber = 0;
      if ( v3->m_lineStream )
      {
        v170.m_uiStreamOffset = v3->m_lastNodeStreamOffset;
      }
      else
      {
        v170.m_uiStreamOffset = 0;
        v3 = 0;
      }
      v139 = *(std::_Ref_count_base **)&v168.m_uiStreamOffset;
      if ( *(_QWORD *)&v168.m_uiStreamOffset )
      {
        _InterlockedAdd((volatile signed __int32 *)(*(_QWORD *)&v168.m_uiStreamOffset + 8LL), 1u);
        v139 = *(std::_Ref_count_base **)&v168.m_uiStreamOffset;
      }
      v140 = *(IXamlSchemaObject **)&v168.m_uiLineNumber;
      __that.m_NodeType[0] = 32;
      *(_OWORD *)&__that.m_LineInfo.m_uiLineNumber = *(_OWORD *)&v170.m_uiLineNumber;
      __that.m_LineInfo.m_pSubReader = v3;
      memset(&__that.m_CustomWriterData, 0, 48);
      if ( v139 )
        _InterlockedAdd((volatile signed __int32 *)&v139->_Uses, 1u);
      __that.m_spShared._Ptr = v140;
      __that.m_spShared._Rep = v139;
      memset(&__that.m_spShared2, 0, 64);
      __that.m_strValue.m_encodedStorage = xstring_ptr_constants::c_xencoded_string_ptr_null;
      std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CDependencyObject * const,CDeferredMapping::DeferredInfo>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CDependencyObject * const,CDeferredMapping::DeferredInfo>>>>>>((std::vector<DirectUI::TrackerPtr<Windows::Foundation::ITypedEventHandler<IInspectable *,IInspectable *>,1,0>> *)&__that.m_vecResourceList);
      if ( v141 )
        std::_Ref_count_base::_Decref(v141);
      if ( *(_QWORD *)&v168.m_uiStreamOffset )
        std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)&v168.m_uiStreamOffset);
      goto LABEL_396;
    }
    if ( v5 != 33 )
    {
      switch ( v5 )
      {
        case '"':
          XamlBinaryFormatSubReader2::ReadConstantAsQO(this, (std::shared_ptr<XamlQualifiedObject> *)&v168);
          *(_QWORD *)&v170.m_uiLineNumber = 0;
          if ( v3->m_lineStream )
          {
            v170.m_uiStreamOffset = v3->m_lastNodeStreamOffset;
          }
          else
          {
            v170.m_uiStreamOffset = 0;
            v3 = 0;
          }
          v133 = *(std::_Ref_count_base **)&v168.m_uiStreamOffset;
          if ( *(_QWORD *)&v168.m_uiStreamOffset )
          {
            _InterlockedAdd((volatile signed __int32 *)(*(_QWORD *)&v168.m_uiStreamOffset + 8LL), 1u);
            v133 = *(std::_Ref_count_base **)&v168.m_uiStreamOffset;
          }
          v134 = *(XamlQualifiedObject **)&v168.m_uiLineNumber;
          __that.m_NodeType[0] = 34;
          *(_OWORD *)&__that.m_LineInfo.m_uiLineNumber = *(_OWORD *)&v170.m_uiLineNumber;
          __that.m_LineInfo.m_pSubReader = v3;
          memset(&__that.m_CustomWriterData, 0, 80);
          if ( v133 )
            _InterlockedAdd((volatile signed __int32 *)&v133->_Uses, 1u);
          __that.m_spValue._Ptr = v134;
          __that.m_spValue._Rep = v133;
          memset(&__that.m_spTextSyntaxConverter, 0, 32);
          __that.m_strValue.m_encodedStorage = xstring_ptr_constants::c_xencoded_string_ptr_null;
          std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CDependencyObject * const,CDeferredMapping::DeferredInfo>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CDependencyObject * const,CDeferredMapping::DeferredInfo>>>>>>((std::vector<DirectUI::TrackerPtr<Windows::Foundation::ITypedEventHandler<IInspectable *,IInspectable *>,1,0>> *)&__that.m_vecResourceList);
          if ( v135 )
            std::_Ref_count_base::_Decref(v135);
          if ( *(_QWORD *)&v168.m_uiStreamOffset )
            std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)&v168.m_uiStreamOffset);
          break;
        case '#':
          v164 = XamlBinaryFormatSubReader2::ReadProvideThemeResourceValueNode(this, &__that);
          ObjectWriterNode::operator=(currentXamlNode, v164);
          goto LABEL_194;
        case '$':
          XamlBinaryFormatSubReader2::ReadXamlProperty(this, (std::shared_ptr<XamlProperty> *)&result);
          XamlBinaryFormatSubReader2::ReadConstantAsQO(v3, (std::shared_ptr<XamlQualifiedObject> *)&v168);
          *(_QWORD *)&v170.m_uiLineNumber = 0;
          if ( v3->m_lineStream )
          {
            v170.m_uiStreamOffset = v3->m_lastNodeStreamOffset;
          }
          else
          {
            v170.m_uiStreamOffset = 0;
            v3 = 0;
          }
          v103 = result._Rep;
          if ( result._Rep )
          {
            _InterlockedAdd((volatile signed __int32 *)&result._Rep->_Uses, 1u);
            v103 = result._Rep;
          }
          v104 = result._Ptr;
          __that.m_NodeType[0] = 36;
          *(_OWORD *)&__that.m_LineInfo.m_uiLineNumber = *(_OWORD *)&v170.m_uiLineNumber;
          __that.m_LineInfo.m_pSubReader = v3;
          memset(&__that.m_CustomWriterData, 0, 48);
          if ( v103 )
            _InterlockedAdd((volatile signed __int32 *)&v103->_Uses, 1u);
          __that.m_spShared._Ptr = v104;
          __that.m_spShared._Rep = v103;
          __that.m_spShared2 = 0;
          v105 = *(std::_Ref_count_base **)&v168.m_uiStreamOffset;
          if ( *(_QWORD *)&v168.m_uiStreamOffset )
          {
            _InterlockedAdd((volatile signed __int32 *)(*(_QWORD *)&v168.m_uiStreamOffset + 8LL), 1u);
            v105 = *(std::_Ref_count_base **)&v168.m_uiStreamOffset;
          }
          __that.m_spValue._Ptr = *(XamlQualifiedObject **)&v168.m_uiLineNumber;
          __that.m_spValue._Rep = v105;
          memset(&__that.m_spTextSyntaxConverter, 0, 32);
          __that.m_strValue.m_encodedStorage = xstring_ptr_constants::c_xencoded_string_ptr_null;
          std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CDependencyObject * const,CDeferredMapping::DeferredInfo>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CDependencyObject * const,CDeferredMapping::DeferredInfo>>>>>>((std::vector<DirectUI::TrackerPtr<Windows::Foundation::ITypedEventHandler<IInspectable *,IInspectable *>,1,0>> *)&__that.m_vecResourceList);
          if ( v106 )
            std::_Ref_count_base::_Decref(v106);
          LODWORD(newString) = 0x8000;
          v107 = *(volatile signed __int32 **)&v168.m_uiStreamOffset;
          if ( *(_QWORD *)&v168.m_uiStreamOffset )
          {
            if ( _InterlockedExchangeAdd(
                   (volatile signed __int32 *)(*(_QWORD *)&v168.m_uiStreamOffset + 8LL),
                   0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v107)(v107);
              if ( _InterlockedExchangeAdd(v107 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v107 + 8LL))(v107);
            }
          }
          v108 = result._Rep;
          if ( result._Rep )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)&result._Rep->_Uses, 0xFFFFFFFF) == 1 )
            {
              v108->_Destroy(v108);
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v108->_Weaks, 0xFFFFFFFF) == 1 )
                v108->_Delete_this(v108);
            }
          }
          break;
        default:
          switch ( v5 )
          {
            case '&':
              v155 = XamlBinaryFormatSubReader2::ReadBeginConditionalScopeNode(this, &__that);
              ObjectWriterNode::operator=(currentXamlNode, v155);
              break;
            case '\'':
              *(_QWORD *)&v168.m_uiLineNumber = 0;
              if ( this->m_lineStream )
              {
                v168.m_uiStreamOffset = m_currentNodeStreamOffset;
                v168.m_pSubReader = this;
              }
              else
              {
                v168.m_uiStreamOffset = 0;
                v168.m_pSubReader = 0;
              }
              LOBYTE(m_currentNodeStreamOffset) = 39;
              ObjectWriterNode::ObjectWriterNode(&__that, (const ObjectWriterNodeType)m_currentNodeStreamOffset, &v168);
              ObjectWriterNode::operator=(currentXamlNode, &__that);
              break;
            case '(':
              v162 = XamlBinaryFormatSubReader2::GetLineInfo(this, &v170);
              LOBYTE(v163) = 40;
              ObjectWriterNode::ObjectWriterNode(&__that, v163, v162);
              ObjectWriterNode::operator=(currentXamlNode, &__that);
              break;
            default:
              return 1;
          }
          goto LABEL_194;
      }
      goto LABEL_396;
    }
    *(_QWORD *)&v170.m_uiLineNumber = 0;
    if ( this->m_lineStream )
    {
      v170.m_uiStreamOffset = m_currentNodeStreamOffset;
    }
    else
    {
      v170.m_uiStreamOffset = 0;
      v3 = 0;
    }
    v203 = 33;
    v204 = *(_OWORD *)&v170.m_uiLineNumber;
    v205 = v3;
    v206 = 0;
    v207 = 0;
    v208 = 0;
    v209 = 0;
    v210 = 0;
    v211 = 0;
    v212 = 0;
    v213 = 0;
    v214 = xstring_ptr_constants::c_xencoded_string_ptr_null.Storage;
    std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CDependencyObject * const,CDeferredMapping::DeferredInfo>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CDependencyObject * const,CDeferredMapping::DeferredInfo>>>>>>(&v216);
    currentXamlNode->m_NodeType[0] = 33;
    *(_OWORD *)&currentXamlNode->m_LineInfo.m_uiLineNumber = v204;
    currentXamlNode->m_LineInfo.m_pSubReader = v205;
    v74 = (std::_Ref_count_base *)*((_QWORD *)&v206 + 1);
    if ( *((_QWORD *)&v206 + 1) )
      _InterlockedAdd((volatile signed __int32 *)(*((_QWORD *)&v206 + 1) + 8LL), 1u);
    currentXamlNode->m_CustomWriterData._Ptr = (CustomWriterRuntimeData *)v206;
    v75 = currentXamlNode->m_CustomWriterData._Rep;
    currentXamlNode->m_CustomWriterData._Rep = v74;
    if ( v75 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v75->_Uses, 0xFFFFFFFF) == 1 )
      {
        v75->_Destroy(v75);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v75->_Weaks, 0xFFFFFFFF) == 1 )
          v75->_Delete_this(v75);
      }
    }
    v76 = (std::_Ref_count_base *)*((_QWORD *)&v207 + 1);
    if ( *((_QWORD *)&v207 + 1) )
      _InterlockedAdd((volatile signed __int32 *)(*((_QWORD *)&v207 + 1) + 8LL), 1u);
    currentXamlNode->m_CustomWriterNodeStream._Ptr = (SubObjectWriterResult *)v207;
    v77 = currentXamlNode->m_CustomWriterNodeStream._Rep;
    currentXamlNode->m_CustomWriterNodeStream._Rep = v76;
    if ( v77 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v77->_Uses, 0xFFFFFFFF) == 1 )
      {
        v77->_Destroy(v77);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v77->_Weaks, 0xFFFFFFFF) == 1 )
          v77->_Delete_this(v77);
      }
    }
    v78 = (std::_Ref_count_base *)*((_QWORD *)&v208 + 1);
    if ( *((_QWORD *)&v208 + 1) )
      _InterlockedAdd((volatile signed __int32 *)(*((_QWORD *)&v208 + 1) + 8LL), 1u);
    currentXamlNode->m_spNodeList._Ptr = (ObjectWriterNodeList *)v208;
    v79 = currentXamlNode->m_spNodeList._Rep;
    currentXamlNode->m_spNodeList._Rep = v78;
    if ( v79 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v79->_Uses, 0xFFFFFFFF) == 1 )
      {
        v79->_Destroy(v79);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v79->_Weaks, 0xFFFFFFFF) == 1 )
          v79->_Delete_this(v79);
      }
    }
    v80 = (std::_Ref_count_base *)*((_QWORD *)&v209 + 1);
    if ( *((_QWORD *)&v209 + 1) )
      _InterlockedAdd((volatile signed __int32 *)(*((_QWORD *)&v209 + 1) + 8LL), 1u);
    currentXamlNode->m_spShared._Ptr = (IXamlSchemaObject *)v209;
    v81 = currentXamlNode->m_spShared._Rep;
    currentXamlNode->m_spShared._Rep = v80;
    if ( v81 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v81->_Uses, 0xFFFFFFFF) == 1 )
      {
        v81->_Destroy(v81);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v81->_Weaks, 0xFFFFFFFF) == 1 )
          v81->_Delete_this(v81);
      }
    }
    v82 = (std::_Ref_count_base *)*((_QWORD *)&v210 + 1);
    if ( *((_QWORD *)&v210 + 1) )
      _InterlockedAdd((volatile signed __int32 *)(*((_QWORD *)&v210 + 1) + 8LL), 1u);
    currentXamlNode->m_spShared2._Ptr = (IXamlSchemaObject *)v210;
    v83 = currentXamlNode->m_spShared2._Rep;
    currentXamlNode->m_spShared2._Rep = v82;
    if ( v83 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v83->_Uses, 0xFFFFFFFF) == 1 )
      {
        v83->_Destroy(v83);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v83->_Weaks, 0xFFFFFFFF) == 1 )
          v83->_Delete_this(v83);
      }
    }
    v84 = (std::_Ref_count_base *)*((_QWORD *)&v211 + 1);
    if ( *((_QWORD *)&v211 + 1) )
      _InterlockedAdd((volatile signed __int32 *)(*((_QWORD *)&v211 + 1) + 8LL), 1u);
    currentXamlNode->m_spValue._Ptr = (XamlQualifiedObject *)v211;
    v85 = currentXamlNode->m_spValue._Rep;
    currentXamlNode->m_spValue._Rep = v84;
    if ( v85 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v85->_Uses, 0xFFFFFFFF) == 1 )
      {
        v85->_Destroy(v85);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v85->_Weaks, 0xFFFFFFFF) == 1 )
          v85->_Delete_this(v85);
      }
    }
    v86 = (std::_Ref_count_base *)*((_QWORD *)&v212 + 1);
    if ( *((_QWORD *)&v212 + 1) )
      _InterlockedAdd((volatile signed __int32 *)(*((_QWORD *)&v212 + 1) + 8LL), 1u);
    currentXamlNode->m_spTextSyntaxConverter._Ptr = (XamlTextSyntax *)v212;
    v87 = currentXamlNode->m_spTextSyntaxConverter._Rep;
    currentXamlNode->m_spTextSyntaxConverter._Rep = v86;
    if ( v87 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v87->_Uses, 0xFFFFFFFF) == 1 )
      {
        v87->_Destroy(v87);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v87->_Weaks, 0xFFFFFFFF) == 1 )
          v87->_Delete_this(v87);
      }
    }
    v88 = (std::_Ref_count_base *)*((_QWORD *)&v213 + 1);
    if ( *((_QWORD *)&v213 + 1) )
      _InterlockedAdd((volatile signed __int32 *)(*((_QWORD *)&v213 + 1) + 8LL), 1u);
    currentXamlNode->m_spSubReader._Ptr = (XamlBinaryFormatSubReader2 *)v213;
    v89 = currentXamlNode->m_spSubReader._Rep;
    currentXamlNode->m_spSubReader._Rep = v88;
    if ( v89 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v89->_Uses, 0xFFFFFFFF) == 1 )
      {
        v89->_Destroy(v89);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v89->_Weaks, 0xFFFFFFFF) == 1 )
          v89->_Delete_this(v89);
      }
    }
    v90 = &currentXamlNode->m_strValue;
    if ( &currentXamlNode->m_strValue == (xstring_ptr *)&v214 )
    {
LABEL_257:
      currentXamlNode->m_intValue = v215;
      v93 = &currentXamlNode->m_vecResourceList;
      if ( v93 != (std::vector<std::pair<bool,xstring_ptr>> *)&v216 )
      {
        v94 = (std::pair<bool,xstring_ptr> *)v216._Mypair._Myval2._Myfirst;
        v95 = ((char *)v216._Mypair._Myval2._Mylast - (char *)v216._Mypair._Myval2._Myfirst) / 12;
        v96 = v93->_Mypair._Myval2._Myfirst;
        if ( v95 > v93->_Mypair._Myval2._Myend - v93->_Mypair._Myval2._Myfirst )
        {
          std::vector<std::pair<bool,xstring_ptr>>::_Clear_and_reserve_geometric(
            v93,
            ((char *)v216._Mypair._Myval2._Mylast - (char *)v216._Mypair._Myval2._Myfirst) / 12);
          v153 = v93->_Mypair._Myval2._Myfirst;
        }
        else
        {
          v97 = v93->_Mypair._Myval2._Mylast;
          v98 = v97 - v96;
          if ( v95 <= v98 )
          {
            for ( n = &v96[v95]; v95; --v95 )
            {
              v96->first = v94->first;
              xstring_ptr::operator=(&v96->second, &v94->second);
              ++v96;
              ++v94;
            }
            v100 = v93->_Mypair._Myval2._Mylast;
            for ( ii = n; ii != v100; ++ii )
              xstring_ptr::~xstring_ptr(&ii->second);
            v93->_Mypair._Myval2._Mylast = n;
            goto LABEL_265;
          }
          while ( v96 != v97 )
          {
            v96->first = v94->first;
            xstring_ptr::operator=(&v96->second, &v94->second);
            ++v96;
            ++v94;
            v97 = v93->_Mypair._Myval2._Mylast;
          }
          v95 -= v98;
          v153 = v97;
        }
        v93->_Mypair._Myval2._Mylast = std::_Uninitialized_copy_n<std::pair<bool,xstring_ptr> *,std::allocator<std::pair<bool,xstring_ptr>>>(
                                         v94,
                                         v95,
                                         v153,
                                         (std::allocator<std::pair<bool,xstring_ptr> > *)v93);
      }
LABEL_265:
      p_that = (ObjectWriterNode *)&v203;
      goto LABEL_195;
    }
    v91 = (HSTRING)v214;
    if ( ((unsigned __int8)v214 & 1) != 0 )
    {
      v118 = WindowsDuplicateString((HSTRING)((unsigned __int64)v214 & 0xFFFFFFFFFFFFFFFEuLL), &newString);
      if ( v118 < 0 )
        goto LABEL_305;
    }
    else
    {
      if ( !v214 )
      {
        v91 = 0;
        goto LABEL_253;
      }
      v92 = *((_DWORD *)v214 + 2);
      if ( (v92 & 0x40000000) == 0 )
      {
LABEL_253:
        newString = v91;
LABEL_254:
        if ( (v90->m_encodedStorage.RuntimeStringHandleMarker & 1) != 0 )
          WindowsDeleteString((HSTRING)(v90->m_encodedStorage.RuntimeStringHandleMarker & 0xFFFFFFFFFFFFFFFEuLL));
        v90->m_encodedStorage.RuntimeStringHandleMarker = (unsigned __int64)newString;
        goto LABEL_257;
      }
      pcStowedExceptions = 0;
      v116 = (wchar_t *)v214->Buffer;
      if ( v92 < 0 )
      {
        v116 = (wchar_t *)WindowsGetStringRawBuffer((HSTRING)v116, &pcStowedExceptions);
        v117 = pcStowedExceptions;
      }
      else
      {
        v117 = v92 & 0x3FFFFFFF;
        pcStowedExceptions = v117;
      }
      v118 = WindowsCreateString(v116, v117, &newString);
      if ( v118 < 0 )
      {
LABEL_305:
        OnFailure_2990_(v118);
        string = 0;
        pcStowedExceptions = 0;
        TraceForFailFast(-2147418113);
        OnNewFailureEncountered(-2147418113, 0, 0);
        GetStowedExceptionsForFailFast((_STOWED_EXCEPTION_INFORMATION_V2 ***)&string, &pcStowedExceptions);
        RoFailFastWithErrorContextInternal2(
          -2147418113,
          pcStowedExceptions,
          (struct _STOWED_EXCEPTION_INFORMATION_V2 **const)string);
        goto LABEL_254;
      }
    }
    newString = (HSTRING)((unsigned __int64)newString | 1);
    goto LABEL_254;
  }
  return 0;
}

```

## disassembly

```asm
0x1800fb480  mov     [rsp-8+arg_8], rbx
0x1800fb485  push    rbp
0x1800fb486  push    rsi
0x1800fb487  push    rdi
0x1800fb488  push    r12
0x1800fb48a  push    r13
0x1800fb48c  push    r14
0x1800fb48e  push    r15
0x1800fb490  lea     rbp, [rsp-280h]
0x1800fb498  sub     rsp, 380h
0x1800fb49f  mov     rdi, currentXamlNode
0x1800fb4a2  mov     rbx, this
0x1800fb4a5  xor     r12d, r12d
0x1800fb4a8  mov     dword ptr [rbp+2B0h+newString], r12d
0x1800fb4af  mov     edx, [this+14h]
0x1800fb4b2  mov     [this+18h], edx
0x1800fb4b5  lea     r9d, [currentXamlNode+1]
0x1800fb4b9  cmp     r9d, [this+1Ch]
0x1800fb4bd  ja      loc_1800FD740
0x1800fb4c3  mov     rax, [this+28h]
0x1800fb4c7  movzx   r8d, byte ptr [currentXamlNode+rax]
0x1800fb4cc  mov     [this+14h], r9d
0x1800fb4d0  mov     ecx, r8d
0x1800fb4d3  lea     r13d, [r12+1]
0x1800fb4d8  mov     r9d, 8Bh
0x1800fb4de  cmp     r8d, r9d
0x1800fb4e1  ja      loc_1800FC1DB
0x1800fb4e7  jz      loc_1800FD70F
0x1800fb4ed  cmp     ecx, 16h
0x1800fb4f0  ja      loc_1800FBAFD
0x1800fb4f6  jz      loc_1800FD352
0x1800fb4fc  cmp     ecx, 0Ch
0x1800fb4ff  jbe     loc_1800FC119
0x1800fb505  sub     ecx, 0Dh
0x1800fb508  jz      loc_1800FCCA4
0x1800fb50e  sub     ecx, r13d
0x1800fb511  jz      loc_1800FD2C4
0x1800fb517  sub     ecx, r13d
0x1800fb51a  jz      loc_1800FD1C3
0x1800fb520  sub     ecx, 2
0x1800fb523  jz      loc_1800FD267
0x1800fb529  sub     ecx, r13d
0x1800fb52c  jz      loc_1800FD286
0x1800fb532  sub     ecx, r13d
0x1800fb535  jz      loc_1800FCAB1
0x1800fb53b  sub     ecx, r13d
0x1800fb53e  jnz     loc_1800FD1E2
0x1800fb544  lea     currentXamlNode, [rsp+3B0h+result]; result
0x1800fb549  mov     this, rbx; this
0x1800fb54c  call    ?ReadXamlType@XamlBinaryFormatSubReader2@@QEAA?AV?$shared_ptr@VXamlType@@@std@@XZ; XamlBinaryFormatSubReader2::ReadXamlType(void)
0x1800fb551  mov     [rsp+3B0h+var_390._Ptr], r12
0x1800fb556  cmp     [rbx+30h], r12
0x1800fb55a  jz      loc_1800FD487
0x1800fb560  mov     eax, [rbx+18h]
0x1800fb563  mov     dword ptr [rsp+3B0h+var_390._Rep], eax
0x1800fb567  mov     rsi, [rsp+3B0h+result._Rep]
0x1800fb56c  test    rsi, rsi
0x1800fb56f  jz      short loc_1800FB57B
0x1800fb571  lock add [rsi+8], r13d
0x1800fb576  mov     rsi, [rsp+3B0h+result._Rep]
0x1800fb57b  mov     rax, [rsp+3B0h+result._Ptr]
0x1800fb580  mov     [rbp+2B0h+var_1C0], 14h
0x1800fb587  movups  xmm0, xmmword ptr [rsp+3B0h+var_390._Ptr]
0x1800fb58c  movups  [rbp+2B0h+var_1B8], xmm0
0x1800fb593  mov     [rbp+2B0h+var_1A8], rbx
0x1800fb59a  xorps   xmm0, xmm0
0x1800fb59d  movdqu  [rbp+2B0h+var_1A0], xmm0
0x1800fb5a5  xorps   xmm1, xmm1
0x1800fb5a8  movdqu  [rbp+2B0h+var_190], xmm1
0x1800fb5b0  movdqu  [rbp+2B0h+var_180], xmm0
0x1800fb5b8  test    rsi, rsi
0x1800fb5bb  jz      loc_1800FD5BC
0x1800fb5c1  lea     currentXamlNode, [rsi+8]
0x1800fb5c5  lock add [currentXamlNode], r13d
0x1800fb5c9  mov     [rbp+2B0h+var_170], rax
0x1800fb5d0  mov     [rbp+2B0h+var_168], rsi
0x1800fb5d7  movdqu  [rbp+2B0h+var_160], xmm0
0x1800fb5df  movdqu  [rbp+2B0h+var_150], xmm1
0x1800fb5e7  movdqu  [rbp+2B0h+var_140], xmm0
0x1800fb5ef  movdqu  [rbp+2B0h+var_130], xmm1
0x1800fb5f7  mov     rax, qword ptr cs:?c_xencoded_string_ptr_null@xstring_ptr_constants@@2Uxencoded_string_ptr@@B.___u0; xencoded_string_ptr const xstring_ptr_constants::c_xencoded_string_ptr_null ...
0x1800fb5fe  mov     [rbp+2B0h+var_120], rax
0x1800fb605  lea     this, [rbp+2B0h+var_110]; this
0x1800fb60c  call    ??$?0AEBV?$allocator@U?$pair@QEAVCDependencyObject@@UDeferredInfo@CDeferredMapping@@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAVCDependencyObject@@UDeferredInfo@CDeferredMapping@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@AEBV?$allocator@U?$pair@QEAVCDependencyObject@@UDeferredInfo@CDeferredMapping@@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CDependencyObject * const,CDeferredMapping::DeferredInfo>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CDependencyObject * const,CDeferredMapping::DeferredInfo>>>>>>(std::allocator<std::pair<CDependencyObject * const,CDeferredMapping::DeferredInfo>> const &)
0x1800fb611  or      ebx, 0FFFFFFFFh
0x1800fb614  test    rsi, rsi
0x1800fb617  jz      short loc_1800FB64B
0x1800fb619  mov     eax, ebx
0x1800fb61b  lock xadd [currentXamlNode], eax
0x1800fb61f  add     eax, ebx
0x1800fb621  jnz     short loc_1800FB64B
0x1800fb623  mov     rax, [rsi]
0x1800fb626  mov     this, rsi
0x1800fb629  mov     rax, [rax]
0x1800fb62c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb631  mov     eax, ebx
0x1800fb633  lock xadd [rsi+0Ch], eax
0x1800fb638  add     eax, ebx
0x1800fb63a  jnz     short loc_1800FB64B
0x1800fb63c  mov     rax, [rsi]
0x1800fb63f  mov     this, rsi
0x1800fb642  mov     rax, [rax+8]
0x1800fb646  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb64b  mov     dword ptr [rbp+2B0h+newString], 20h ; ' '
0x1800fb655  mov     rsi, [rsp+3B0h+result._Rep]
0x1800fb65a  test    rsi, rsi
0x1800fb65d  jz      short loc_1800FB692
0x1800fb65f  mov     eax, ebx
0x1800fb661  lock xadd [rsi+8], eax
0x1800fb666  add     eax, ebx
0x1800fb668  jnz     short loc_1800FB692
0x1800fb66a  mov     rax, [rsi]
0x1800fb66d  mov     this, rsi
0x1800fb670  mov     rax, [rax]
0x1800fb673  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb678  mov     eax, ebx
0x1800fb67a  lock xadd [rsi+0Ch], eax
0x1800fb67f  add     eax, ebx
0x1800fb681  jnz     short loc_1800FB692
0x1800fb683  mov     rax, [rsi]
0x1800fb686  mov     this, rsi
0x1800fb689  mov     rax, [rax+8]
0x1800fb68d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb692  mov     al, [rbp+2B0h+var_1C0]
0x1800fb698  mov     [rdi], al
0x1800fb69a  movups  xmm0, [rbp+2B0h+var_1B8]
0x1800fb6a1  movups  xmmword ptr [rdi+8], xmm0
0x1800fb6a5  movsd   xmm1, [rbp+2B0h+var_1A8]
0x1800fb6ad  movsd   qword ptr [rdi+18h], xmm1
0x1800fb6b2  mov     this, qword ptr [rbp+2B0h+var_1A0+8]
0x1800fb6b9  test    this, this
0x1800fb6bc  jz      short loc_1800FB6C3
0x1800fb6be  lock add [this+8], r13d
0x1800fb6c3  mov     rax, qword ptr [rbp+2B0h+var_1A0]
0x1800fb6ca  mov     [rdi+20h], rax
0x1800fb6ce  mov     rsi, [rdi+28h]
0x1800fb6d2  mov     [rdi+28h], this
0x1800fb6d6  test    rsi, rsi
0x1800fb6d9  jz      short loc_1800FB70E
0x1800fb6db  mov     eax, ebx
0x1800fb6dd  lock xadd [rsi+8], eax
0x1800fb6e2  add     eax, ebx
0x1800fb6e4  jnz     short loc_1800FB70E
0x1800fb6e6  mov     rax, [rsi]
0x1800fb6e9  mov     this, rsi
0x1800fb6ec  mov     rax, [rax]
0x1800fb6ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb6f4  mov     eax, ebx
0x1800fb6f6  lock xadd [rsi+0Ch], eax
0x1800fb6fb  add     eax, ebx
0x1800fb6fd  jnz     short loc_1800FB70E
0x1800fb6ff  mov     rax, [rsi]
0x1800fb702  mov     this, rsi
0x1800fb705  mov     rax, [rax+8]
0x1800fb709  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb70e  mov     this, qword ptr [rbp+2B0h+var_190+8]
0x1800fb715  test    this, this
0x1800fb718  jz      short loc_1800FB71F
0x1800fb71a  lock add [this+8], r13d
0x1800fb71f  mov     rax, qword ptr [rbp+2B0h+var_190]
0x1800fb726  mov     [rdi+30h], rax
0x1800fb72a  mov     rsi, [rdi+38h]
0x1800fb72e  mov     [rdi+38h], this
0x1800fb732  test    rsi, rsi
0x1800fb735  jz      short loc_1800FB76A
0x1800fb737  mov     eax, ebx
0x1800fb739  lock xadd [rsi+8], eax
0x1800fb73e  add     eax, ebx
0x1800fb740  jnz     short loc_1800FB76A
0x1800fb742  mov     rax, [rsi]
0x1800fb745  mov     this, rsi
0x1800fb748  mov     rax, [rax]
0x1800fb74b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb750  mov     eax, ebx
0x1800fb752  lock xadd [rsi+0Ch], eax
0x1800fb757  add     eax, ebx
0x1800fb759  jnz     short loc_1800FB76A
0x1800fb75b  mov     rax, [rsi]
0x1800fb75e  mov     this, rsi
0x1800fb761  mov     rax, [rax+8]
0x1800fb765  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb76a  mov     this, qword ptr [rbp+2B0h+var_180+8]
0x1800fb771  test    this, this
0x1800fb774  jz      short loc_1800FB77B
0x1800fb776  lock add [this+8], r13d
0x1800fb77b  mov     rax, qword ptr [rbp+2B0h+var_180]
0x1800fb782  mov     [rdi+40h], rax
0x1800fb786  mov     rsi, [rdi+48h]
0x1800fb78a  mov     [rdi+48h], this
0x1800fb78e  test    rsi, rsi
0x1800fb791  jz      short loc_1800FB7C6
0x1800fb793  mov     eax, ebx
0x1800fb795  lock xadd [rsi+8], eax
0x1800fb79a  add     eax, ebx
0x1800fb79c  jnz     short loc_1800FB7C6
0x1800fb79e  mov     rax, [rsi]
0x1800fb7a1  mov     this, rsi
0x1800fb7a4  mov     rax, [rax]
0x1800fb7a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb7ac  mov     eax, ebx
0x1800fb7ae  lock xadd [rsi+0Ch], eax
0x1800fb7b3  add     eax, ebx
0x1800fb7b5  jnz     short loc_1800FB7C6
0x1800fb7b7  mov     rax, [rsi]
0x1800fb7ba  mov     this, rsi
0x1800fb7bd  mov     rax, [rax+8]
0x1800fb7c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb7c6  mov     this, [rbp+2B0h+var_168]
0x1800fb7cd  test    this, this
0x1800fb7d0  jz      short loc_1800FB7D7
0x1800fb7d2  lock add [this+8], r13d
0x1800fb7d7  mov     rax, [rbp+2B0h+var_170]
0x1800fb7de  mov     [rdi+50h], rax
0x1800fb7e2  mov     rsi, [rdi+58h]
0x1800fb7e6  mov     [rdi+58h], this
0x1800fb7ea  test    rsi, rsi
0x1800fb7ed  jz      short loc_1800FB822
0x1800fb7ef  mov     eax, ebx
0x1800fb7f1  lock xadd [rsi+8], eax
0x1800fb7f6  add     eax, ebx
0x1800fb7f8  jnz     short loc_1800FB822
0x1800fb7fa  mov     rax, [rsi]
0x1800fb7fd  mov     this, rsi
0x1800fb800  mov     rax, [rax]
0x1800fb803  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb808  mov     eax, ebx
0x1800fb80a  lock xadd [rsi+0Ch], eax
0x1800fb80f  add     eax, ebx
0x1800fb811  jnz     short loc_1800FB822
0x1800fb813  mov     rax, [rsi]
0x1800fb816  mov     this, rsi
0x1800fb819  mov     rax, [rax+8]
0x1800fb81d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb822  mov     this, qword ptr [rbp+2B0h+var_160+8]
0x1800fb829  test    this, this
0x1800fb82c  jz      short loc_1800FB833
0x1800fb82e  lock add [this+8], r13d
0x1800fb833  mov     rax, qword ptr [rbp+2B0h+var_160]
0x1800fb83a  mov     [rdi+60h], rax
0x1800fb83e  mov     rsi, [rdi+68h]
0x1800fb842  mov     [rdi+68h], this
0x1800fb846  test    rsi, rsi
0x1800fb849  jz      short loc_1800FB87E
0x1800fb84b  mov     eax, ebx
0x1800fb84d  lock xadd [rsi+8], eax
0x1800fb852  add     eax, ebx
0x1800fb854  jnz     short loc_1800FB87E
0x1800fb856  mov     rax, [rsi]
0x1800fb859  mov     this, rsi
0x1800fb85c  mov     rax, [rax]
0x1800fb85f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb864  mov     eax, ebx
0x1800fb866  lock xadd [rsi+0Ch], eax
0x1800fb86b  add     eax, ebx
0x1800fb86d  jnz     short loc_1800FB87E
0x1800fb86f  mov     rax, [rsi]
0x1800fb872  mov     this, rsi
0x1800fb875  mov     rax, [rax+8]
0x1800fb879  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb87e  mov     this, qword ptr [rbp+2B0h+var_150+8]
0x1800fb885  test    this, this
0x1800fb888  jz      short loc_1800FB88F
0x1800fb88a  lock add [this+8], r13d
0x1800fb88f  mov     rax, qword ptr [rbp+2B0h+var_150]
0x1800fb896  mov     [rdi+70h], rax
0x1800fb89a  mov     rsi, [rdi+78h]
0x1800fb89e  mov     [rdi+78h], this
0x1800fb8a2  test    rsi, rsi
0x1800fb8a5  jz      short loc_1800FB8DA
0x1800fb8a7  mov     eax, ebx
0x1800fb8a9  lock xadd [rsi+8], eax
0x1800fb8ae  add     eax, ebx
0x1800fb8b0  jnz     short loc_1800FB8DA
0x1800fb8b2  mov     rax, [rsi]
0x1800fb8b5  mov     this, rsi
0x1800fb8b8  mov     rax, [rax]
0x1800fb8bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb8c0  mov     eax, ebx
0x1800fb8c2  lock xadd [rsi+0Ch], eax
0x1800fb8c7  add     eax, ebx
0x1800fb8c9  jnz     short loc_1800FB8DA
0x1800fb8cb  mov     rax, [rsi]
0x1800fb8ce  mov     this, rsi
0x1800fb8d1  mov     rax, [rax+8]
0x1800fb8d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb8da  mov     this, qword ptr [rbp+2B0h+var_140+8]
0x1800fb8e1  test    this, this
0x1800fb8e4  jz      short loc_1800FB8EB
0x1800fb8e6  lock add [this+8], r13d
0x1800fb8eb  mov     rax, qword ptr [rbp+2B0h+var_140]
0x1800fb8f2  mov     [rdi+80h], rax
0x1800fb8f9  mov     rsi, [rdi+88h]
0x1800fb900  mov     [rdi+88h], this
0x1800fb907  test    rsi, rsi
0x1800fb90a  jz      short loc_1800FB93F
0x1800fb90c  mov     eax, ebx
0x1800fb90e  lock xadd [rsi+8], eax
0x1800fb913  add     eax, ebx
0x1800fb915  jnz     short loc_1800FB93F
0x1800fb917  mov     rax, [rsi]
  ... truncated ...
```
