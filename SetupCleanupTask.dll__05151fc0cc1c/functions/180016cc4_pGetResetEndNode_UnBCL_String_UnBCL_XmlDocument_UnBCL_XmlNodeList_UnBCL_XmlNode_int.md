# pGetResetEndNode(UnBCL::String *,UnBCL::XmlDocument * *,UnBCL::XmlNodeList * *,UnBCL::XmlNode * *,int *)

- ea: `0x180016cc4`
- end: `0x180017194`
- name: `?pGetResetEndNode@@YAJPEAVString@UnBCL@@PEAPEAVXmlDocument@2@PEAPEAVXmlNodeList@2@PEAPEAVXmlNode@2@PEAH@Z`
- size: `1232`
- prototype: `__int64 __fastcall(struct UnBCL::String *, struct UnBCL::XmlDocument **, struct UnBCL::XmlNodeList **, struct UnBCL::XmlNode **, int *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180015278`
- `0x18001577c`

## callees

- `0x180005e98`
- `0x18000638c`
- `0x180014f54`
- `0x180014fa8`
- `0x180014ffc`
- `0x180015050`
- `0x1800150a4`
- `0x180016cc4`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180016fcd`
- `msvcrt!_wcsicmp` at `0x180016fcd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016e59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016f3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016e59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016f3b`
- `unbcl!??0XmlDocument@UnBCL@@QEAA@XZ` at `0x180016d3d`
- `unbcl!??0XmlDocument@UnBCL@@QEAA@XZ` at `0x180016d3d`
- `unbcl!?AddRef@Object@UnBCL@@QEAAXXZ` at `0x180016e46`
- `unbcl!?AddRef@Object@UnBCL@@QEAAXXZ` at `0x180016f1a`
- `unbcl!?AddRef@Object@UnBCL@@QEAAXXZ` at `0x180016e46`
- `unbcl!?AddRef@Object@UnBCL@@QEAAXXZ` at `0x180016f1a`
- `unbcl!?DecRef@Object@UnBCL@@QEAAHXZ` at `0x18001710c`
- `unbcl!?DecRef@Object@UnBCL@@QEAAHXZ` at `0x180017128`
- `unbcl!?DecRef@Object@UnBCL@@QEAAHXZ` at `0x18001710c`
- `unbcl!?DecRef@Object@UnBCL@@QEAAHXZ` at `0x180017128`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180016fbd`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180016fbd`
- `unbcl!?Load@XmlDocument@UnBCL@@QEAAXPEAVString@2@@Z` at `0x180016d7c`
- `unbcl!?Load@XmlDocument@UnBCL@@QEAAXPEAVString@2@@Z` at `0x180016d7c`
- `unbcl!?SelectNodes@XmlNode@UnBCL@@QEAAPEAVXmlNodeList@2@PEAVString@2@@Z` at `0x180016d9f`
- `unbcl!?SelectNodes@XmlNode@UnBCL@@QEAAPEAVXmlNodeList@2@PEAVString@2@@Z` at `0x180016d9f`
- `unbcl!?get_Count@XmlNodeList@UnBCL@@QEAAHXZ` at `0x180016dfa`
- `unbcl!?get_Count@XmlNodeList@UnBCL@@QEAAHXZ` at `0x180016ff8`
- `unbcl!?get_Count@XmlNodeList@UnBCL@@QEAAHXZ` at `0x1800170d6`
- `unbcl!?get_Count@XmlNodeList@UnBCL@@QEAAHXZ` at `0x180016dfa`
- `unbcl!?get_Count@XmlNodeList@UnBCL@@QEAAHXZ` at `0x180016ff8`
- `unbcl!?get_Count@XmlNodeList@UnBCL@@QEAAHXZ` at `0x1800170d6`
- `unbcl!?get_Item@XmlNodeList@UnBCL@@QEAAPEAVXmlNode@2@H@Z` at `0x180016e0e`
- `unbcl!?get_Item@XmlNodeList@UnBCL@@QEAAPEAVXmlNode@2@H@Z` at `0x180016e0e`
- `unbcl!?get_Attributes@XmlNode@UnBCL@@QEAAPEAVXmlAttributeCollection@2@XZ` at `0x180016e1a`
- `unbcl!?get_Attributes@XmlNode@UnBCL@@QEAAPEAVXmlAttributeCollection@2@XZ` at `0x180016e1a`
- `unbcl!?get_Item@XmlAttributeCollection@UnBCL@@QEAAPEAVXmlAttribute@2@PEAVString@2@@Z` at `0x180016eee`
- `unbcl!?get_Item@XmlAttributeCollection@UnBCL@@QEAAPEAVXmlAttribute@2@PEAVString@2@@Z` at `0x180016eee`
- `unbcl!?get_Value@XmlNode@UnBCL@@QEAAPEAVString@2@XZ` at `0x180016fb4`
- `unbcl!?get_Value@XmlNode@UnBCL@@QEAAPEAVString@2@XZ` at `0x180016fb4`
- `unbcl!?SelectSingleNode@XmlNode@UnBCL@@QEAAPEAV12@PEAVString@2@@Z` at `0x180017068`
- `unbcl!?SelectSingleNode@XmlNode@UnBCL@@QEAAPEAV12@PEAVString@2@@Z` at `0x180017068`
- `unbcl!?get_ChildNodes@XmlNode@UnBCL@@QEAAPEAVXmlNodeList@2@XZ` at `0x1800170ac`
- `unbcl!?get_ChildNodes@XmlNode@UnBCL@@QEAAPEAVXmlNodeList@2@XZ` at `0x1800170ac`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180016d27`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180016d27`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180016dd5`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180016f30`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18001709e`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180016dd5`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180016f30`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18001709e`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180016d92`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180016ee1`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18001705b`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180016d92`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180016ee1`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18001705b`
- `WDSCORE!CurrentIP` at `0x180016e61`
- `WDSCORE!CurrentIP` at `0x180016f43`
- `WDSCORE!CurrentIP` at `0x180016e61`
- `WDSCORE!CurrentIP` at `0x180016f43`
- `WDSCORE!WdsSetupLogMessageW` at `0x180016ec7`
- `WDSCORE!WdsSetupLogMessageW` at `0x180016fa9`
- `WDSCORE!WdsSetupLogMessageW` at `0x180016ec7`
- `WDSCORE!WdsSetupLogMessageW` at `0x180016fa9`

## string_xrefs

- `0x180016ea4`: `base\ntsetup\setup\tools\setupcleanuptask\lib\src\setupcleanuptaskcleanupremediation.cpp`
- `0x180016f86`: `base\ntsetup\setup\tools\setupcleanuptask\lib\src\setupcleanuptaskcleanupremediation.cpp`

## pseudocode

```c
__int64 __fastcall pGetResetEndNode(
        struct UnBCL::String *a1,
        struct UnBCL::XmlDocument **a2,
        struct UnBCL::XmlNodeList **a3,
        struct UnBCL::XmlNode **a4,
        int *a5)
{
  int v8; // r15d
  UnBCL::XmlDocument *v9; // rax
  UnBCL::Object *v10; // rbx
  struct UnBCL::String *v11; // rax
  UnBCL::Object *v12; // rax
  UnBCL::XmlNode *Item; // rdi
  UnBCL::XmlNodeList *v14; // rsi
  UnBCL::Object *Attributes; // rbx
  DWORD v16; // edi
  __int64 v17; // rbx
  struct tagLOG_PARTIAL_MSG *v18; // rax
  struct UnBCL::String *v19; // rax
  UnBCL::Object *v20; // rbx
  DWORD v21; // edi
  __int64 v22; // rbx
  struct tagLOG_PARTIAL_MSG *v23; // rax
  UnBCL::String *Value; // rax
  const wchar_t *v25; // rax
  struct UnBCL::String *v26; // rax
  UnBCL::Object *v27; // rax
  UnBCL::Object *ChildNodes; // rax
  UnBCL::XmlNode *v29; // r14
  DWORD LastError; // esi
  __int64 v32; // r14
  __int64 v33; // rbx
  const wchar_t *CString; // rdi
  UnBCL::String *v35; // rax
  const char *v36; // rax
  struct tagLOG_PARTIAL_MSG *v37; // rax
  DWORD v38; // esi
  __int64 v39; // r14
  __int64 v40; // rbx
  const wchar_t *v41; // rdi
  UnBCL::String *v42; // rax
  const char *v43; // rax
  struct tagLOG_PARTIAL_MSG *v44; // rax
  void **v45; // [rsp+60h] [rbp-E8h] BYREF
  UnBCL::XmlDocument *v46; // [rsp+68h] [rbp-E0h]
  void **v47; // [rsp+70h] [rbp-D8h] BYREF
  UnBCL::XmlNodeList *v48; // [rsp+78h] [rbp-D0h]
  void **v49; // [rsp+80h] [rbp-C8h] BYREF
  UnBCL::Object *v50; // [rsp+88h] [rbp-C0h]
  void **v51; // [rsp+90h] [rbp-B8h] BYREF
  UnBCL::XmlNodeList *v52; // [rsp+98h] [rbp-B0h]
  void **v53; // [rsp+A0h] [rbp-A8h] BYREF
  UnBCL::Object *v54; // [rsp+A8h] [rbp-A0h]
  void **v55; // [rsp+B0h] [rbp-98h] BYREF
  UnBCL::XmlNode *v56; // [rsp+B8h] [rbp-90h]
  __int64 v57; // [rsp+C0h] [rbp-88h] BYREF
  __int64 v58; // [rsp+C8h] [rbp-80h] BYREF
  _BYTE v59[24]; // [rsp+D0h] [rbp-78h] BYREF
  _BYTE v60[24]; // [rsp+E8h] [rbp-60h] BYREF
  _BYTE v61[32]; // [rsp+100h] [rbp-48h] BYREF

  v8 = 0;
  if ( !a1 || !a2 || !a3 || !a4 )
    return 2147942487LL;
  *a2 = 0;
  *a3 = 0;
  *a4 = 0;
  v9 = (UnBCL::XmlDocument *)UnBCL::Object::operator new(0x28u);
  v10 = v9;
  v47 = (void **)v9;
  if ( v9 )
  {
    UnBCL::XmlDocument::XmlDocument(v9);
    *(_QWORD *)v10 = &UnBCL::XmlDocument::`local vftable';
  }
  else
  {
    v10 = 0;
  }
  v45 = &UnBCL::SmartPtr<UnBCL::XmlDocument>::`vftable';
  v46 = 0;
  UnBCL::SmartPtr<UnBCL::XmlNodeList>::Assign((__int64)&v45, v10);
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    v29 = v46;
    UnBCL::XmlDocument::Load(v46, a1);
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &UnBCL::XmlException * `RTTI Type Descriptor', (UnBCL::XmlException **)&v57) )
    {
      LastError = GetLastError();
      v32 = CurrentIP();
      v33 = v57;
      if ( (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v33 + 72LL))(v33) )
      {
        v35 = (UnBCL::String *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v33 + 72LL))(v33);
        CString = UnBCL::String::get_CString(v35);
      }
      else
      {
        CString = L"(NULL)";
      }
      v36 = (const char *)UnBCL::String::get_CString(a1);
      v37 = ConstructPartialMsgW(0x2000000, "XML parse error while loading %s. Message: %s", v36, (const char *)CString);
      WdsSetupLogMessageW(
        v37,
        0,
        L"D",
        0,
        103,
        L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanuptaskcleanupremediation.cpp",
        L"pGetResetEndNode",
        v32,
        LastError,
        0,
        0);
      (**(void (__fastcall ***)(__int64, __int64))v33)(v33, 1);
      __eh34_try_continuation(0, &UnBCL::XmlException * `RTTI Type Descriptor', &loc_180017161);
LABEL_34:
      UnBCL::SmartPtr<UnBCL::XmlDocument>::~SmartPtr<UnBCL::XmlDocument>(&v45);
      return 2147500037LL;
    }
    if ( __eh34_catch_type(0, &UnBCL::Exception * `RTTI Type Descriptor', (UnBCL::Exception **)&v58) )
    {
      v38 = GetLastError();
      v39 = CurrentIP();
      v40 = v58;
      if ( (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v40 + 72LL))(v40) )
      {
        v42 = (UnBCL::String *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v40 + 72LL))(v40);
        v41 = UnBCL::String::get_CString(v42);
      }
      else
      {
        v41 = L"(NULL)";
      }
      v43 = (const char *)UnBCL::String::get_CString(a1);
      v44 = ConstructPartialMsgW(0x2000000, "IO error while loading %s. Message: %s", v43, (const char *)v41);
      WdsSetupLogMessageW(
        v44,
        0,
        L"D",
        0,
        115,
        L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanuptaskcleanupremediation.cpp",
        L"pGetResetEndNode",
        v39,
        v38,
        0,
        0);
      (**(void (__fastcall ***)(__int64, __int64))v40)(v40, 1);
      __eh34_try_continuation(0, &UnBCL::Exception * `RTTI Type Descriptor', &loc_180017161);
      goto LABEL_34;
    }
  }
  v11 = (struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v59, L"/Reset/Run");
  v12 = UnBCL::XmlNode::SelectNodes(v29, v11);
  v51 = &UnBCL::SmartPtr<UnBCL::XmlNodeList>::`vftable';
  v52 = 0;
  UnBCL::SmartPtr<UnBCL::XmlNodeList>::Assign((__int64)&v51, v12);
  UnBCL::String::~String((UnBCL::String *)v59);
  Item = 0;
  v14 = v52;
  if ( v52 && (int)UnBCL::XmlNodeList::get_Count(v52) > 0 )
  {
    while ( 1 )
    {
      Item = UnBCL::XmlNodeList::get_Item(v14, v8);
      Attributes = UnBCL::XmlNode::get_Attributes(Item);
      v53 = &UnBCL::SmartPtr<UnBCL::XmlAttributeCollection>::`vftable';
      v54 = 0;
      if ( Attributes )
        UnBCL::Object::AddRef(Attributes);
      v54 = Attributes;
      if ( Attributes )
      {
        v19 = (struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v60, L"Phase");
        v20 = UnBCL::XmlAttributeCollection::get_Item(Attributes, v19);
        v49 = &UnBCL::SmartPtr<UnBCL::XmlAttribute>::`vftable';
        v50 = 0;
        if ( v20 )
          UnBCL::Object::AddRef(v20);
        v50 = v20;
        UnBCL::String::~String((UnBCL::String *)v60);
        if ( v20 )
        {
          Value = UnBCL::XmlNode::get_Value(v20);
          v25 = UnBCL::String::get_CString(Value);
          if ( !_wcsicmp(v25, L"FactoryReset_AfterImageApply") )
          {
            UnBCL::SmartPtr<UnBCL::XmlAttribute>::~SmartPtr<UnBCL::XmlAttribute>(&v49);
            UnBCL::SmartPtr<UnBCL::XmlAttributeCollection>::~SmartPtr<UnBCL::XmlAttributeCollection>(&v53);
            break;
          }
        }
        else
        {
          v21 = GetLastError();
          v22 = CurrentIP();
          v23 = ConstructPartialMsgW(50331648, "<Run> node %d has no Phase attribute", v8);
          WdsSetupLogMessageW(
            v23,
            0,
            L"D",
            0,
            142,
            L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanuptaskcleanupremediation.cpp",
            L"pGetResetEndNode",
            v22,
            v21,
            0,
            0);
        }
        UnBCL::SmartPtr<UnBCL::XmlAttribute>::~SmartPtr<UnBCL::XmlAttribute>(&v49);
      }
      else
      {
        v16 = GetLastError();
        v17 = CurrentIP();
        v18 = ConstructPartialMsgW(50331648, "<Run> node %d has no attributes", v8);
        WdsSetupLogMessageW(
          v18,
          0,
          L"D",
          0,
          135,
          L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanuptaskcleanupremediation.cpp",
          L"pGetResetEndNode",
          v17,
          v16,
          0,
          0);
      }
      UnBCL::SmartPtr<UnBCL::XmlAttributeCollection>::~SmartPtr<UnBCL::XmlAttributeCollection>(&v53);
      if ( ++v8 >= UnBCL::XmlNodeList::get_Count(v14) )
      {
        Item = 0;
        break;
      }
    }
  }
  if ( a5 )
  {
    *a5 = 0;
    if ( Item )
    {
      v26 = (struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v61, L"/Reset");
      v27 = UnBCL::XmlNode::SelectSingleNode(v29, v26);
      v55 = &UnBCL::SmartPtr<UnBCL::XmlNode>::`vftable';
      v56 = 0;
      UnBCL::SmartPtr<UnBCL::XmlNodeList>::Assign((__int64)&v55, v27);
      UnBCL::String::~String((UnBCL::String *)v61);
      ChildNodes = UnBCL::XmlNode::get_ChildNodes(v56);
      v47 = &UnBCL::SmartPtr<UnBCL::XmlNodeList>::`vftable';
      v48 = 0;
      UnBCL::SmartPtr<UnBCL::XmlNodeList>::Assign((__int64)&v47, ChildNodes);
      *a5 = UnBCL::XmlNodeList::get_Count(v48) == 1;
      UnBCL::SmartPtr<UnBCL::XmlNodeList>::~SmartPtr<UnBCL::XmlNodeList>(&v47);
      UnBCL::SmartPtr<UnBCL::XmlNode>::~SmartPtr<UnBCL::XmlNode>(&v55);
    }
  }
  if ( v29 )
  {
    UnBCL::Object::DecRef(v29);
    v46 = 0;
  }
  else
  {
    v29 = 0;
  }
  *a2 = v29;
  if ( v14 )
  {
    UnBCL::Object::DecRef(v14);
    v52 = 0;
  }
  else
  {
    v14 = 0;
  }
  *a3 = v14;
  *a4 = Item;
  UnBCL::SmartPtr<UnBCL::XmlNodeList>::~SmartPtr<UnBCL::XmlNodeList>(&v51);
  UnBCL::SmartPtr<UnBCL::XmlDocument>::~SmartPtr<UnBCL::XmlDocument>(&v45);
  return 0;
}

```

## disassembly

```asm
0x180016cc4  mov     rax, rsp
0x180016cc7  mov     [rax+10h], rbx
0x180016ccb  mov     [rax+20h], rsi
0x180016ccf  mov     [rax+18h], r8
0x180016cd3  mov     [rax+8], rcx
0x180016cd7  push    rdi
0x180016cd8  push    r12
0x180016cda  push    r13
0x180016cdc  push    r14
0x180016cde  push    r15
0x180016ce0  sub     rsp, 120h
0x180016ce7  mov     r13, r9
0x180016cea  mov     rax, r8
0x180016ced  mov     r12, rdx
0x180016cf0  mov     rdi, rcx
0x180016cf3  xor     r15d, r15d
0x180016cf6  test    rcx, rcx
0x180016cf9  jz      loc_180017172
0x180016cff  test    rdx, rdx
0x180016d02  jz      loc_180017172
0x180016d08  test    rax, rax
0x180016d0b  jz      loc_180017172
0x180016d11  test    r9, r9
0x180016d14  jz      loc_180017172
0x180016d1a  mov     [rdx], r15
0x180016d1d  mov     [r8], r15
0x180016d20  mov     [r9], r15
0x180016d23  lea     ecx, [r15+28h]
0x180016d27  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180016d2d  mov     rbx, rax
0x180016d30  mov     [rsp+148h+var_D8], rax
0x180016d35  test    rax, rax
0x180016d38  jz      short loc_180016D4F
0x180016d3a  mov     rcx, rax
0x180016d3d  call    cs:__imp_??0XmlDocument@UnBCL@@QEAA@XZ; UnBCL::XmlDocument::XmlDocument(void)
0x180016d43  lea     rax, ??_SXmlDocument@UnBCL@@6B@; const UnBCL::XmlDocument::`local vftable'
0x180016d4a  mov     [rbx], rax
0x180016d4d  jmp     short loc_180016D52
0x180016d4f  mov     rbx, r15
0x180016d52  lea     rax, ??_7?$SmartPtr@VXmlDocument@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::XmlDocument>::`vftable'
0x180016d59  mov     [rsp+148h+var_E8], rax
0x180016d5e  mov     [rsp+148h+var_E0], r15
0x180016d63  mov     rdx, rbx
0x180016d66  lea     rcx, [rsp+148h+var_E8]
0x180016d6b  call    ?Assign@?$SmartPtr@VXmlNodeList@UnBCL@@@UnBCL@@AEAAXPEAVXmlNodeList@2@@Z; UnBCL::SmartPtr<UnBCL::XmlNodeList>::Assign(UnBCL::XmlNodeList *)
0x180016d70  nop
0x180016d71  mov     r14, [rsp+148h+var_E0]
0x180016d76  mov     rdx, rdi
0x180016d79  mov     rcx, r14
0x180016d7c  call    cs:__imp_?Load@XmlDocument@UnBCL@@QEAAXPEAVString@2@@Z; UnBCL::XmlDocument::Load(UnBCL::String *)
0x180016d82  nop
0x180016d83  lea     rdx, aResetRun; "/Reset/Run"
0x180016d8a  lea     rcx, [rsp+148h+var_78]
0x180016d92  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180016d98  nop
0x180016d99  mov     rdx, rax
0x180016d9c  mov     rcx, r14
0x180016d9f  call    cs:__imp_?SelectNodes@XmlNode@UnBCL@@QEAAPEAVXmlNodeList@2@PEAVString@2@@Z; UnBCL::XmlNode::SelectNodes(UnBCL::String *)
0x180016da5  lea     rcx, ??_7?$SmartPtr@VXmlNodeList@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::XmlNodeList>::`vftable'
0x180016dac  mov     [rsp+148h+var_B8], rcx
0x180016db4  mov     [rsp+148h+var_B0], r15
0x180016dbc  mov     rdx, rax
0x180016dbf  lea     rcx, [rsp+148h+var_B8]
0x180016dc7  call    ?Assign@?$SmartPtr@VXmlNodeList@UnBCL@@@UnBCL@@AEAAXPEAVXmlNodeList@2@@Z; UnBCL::SmartPtr<UnBCL::XmlNodeList>::Assign(UnBCL::XmlNodeList *)
0x180016dcc  nop
0x180016dcd  lea     rcx, [rsp+148h+var_78]
0x180016dd5  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x180016ddb  mov     rdi, r15
0x180016dde  mov     [rsp+148h+arg_0], r15
0x180016de6  mov     rsi, [rsp+148h+var_B0]
0x180016dee  test    rsi, rsi
0x180016df1  jz      loc_18001702C
0x180016df7  mov     rcx, rsi
0x180016dfa  call    cs:__imp_?get_Count@XmlNodeList@UnBCL@@QEAAHXZ; UnBCL::XmlNodeList::get_Count(void)
0x180016e00  test    eax, eax
0x180016e02  jle     loc_18001702C
0x180016e08  mov     edx, r15d
0x180016e0b  mov     rcx, rsi
0x180016e0e  call    cs:__imp_?get_Item@XmlNodeList@UnBCL@@QEAAPEAVXmlNode@2@H@Z; UnBCL::XmlNodeList::get_Item(int)
0x180016e14  mov     rdi, rax
0x180016e17  mov     rcx, rax
0x180016e1a  call    cs:__imp_?get_Attributes@XmlNode@UnBCL@@QEAAPEAVXmlAttributeCollection@2@XZ; UnBCL::XmlNode::get_Attributes(void)
0x180016e20  mov     rbx, rax
0x180016e23  lea     rax, ??_7?$SmartPtr@VXmlAttributeCollection@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::XmlAttributeCollection>::`vftable'
0x180016e2a  mov     [rsp+148h+var_A8], rax
0x180016e32  mov     [rsp+148h+var_A0], 0
0x180016e3e  test    rbx, rbx
0x180016e41  jz      short loc_180016E4C
0x180016e43  mov     rcx, rbx
0x180016e46  call    cs:__imp_?AddRef@Object@UnBCL@@QEAAXXZ; UnBCL::Object::AddRef(void)
0x180016e4c  mov     [rsp+148h+var_A0], rbx
0x180016e54  test    rbx, rbx
0x180016e57  jnz     short loc_180016ED2
0x180016e59  call    cs:__imp_GetLastError
0x180016e5f  mov     edi, eax
0x180016e61  call    cs:__imp_CurrentIP
0x180016e67  mov     rbx, rax
0x180016e6a  mov     r8d, r15d
0x180016e6d  lea     rdx, aRunNodeDHasNoA; "<Run> node %d has no attributes"
0x180016e74  mov     ecx, 3000000h; unsigned int
0x180016e79  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180016e7e  mov     [rsp+148h+var_F8], 0
0x180016e86  mov     [rsp+148h+var_100], 0
0x180016e8f  mov     [rsp+148h+var_108], edi
0x180016e93  mov     [rsp+148h+var_110], rbx
0x180016e98  lea     rcx, aPgetresetendno; "pGetResetEndNode"
0x180016e9f  mov     [rsp+148h+var_118], rcx
0x180016ea4  lea     rcx, aBaseNtsetupSet_2; "base\\ntsetup\\setup\\tools\\setupclean"...
0x180016eab  mov     [rsp+148h+var_120], rcx
0x180016eb0  mov     [rsp+148h+var_128], 87h
0x180016eb8  xor     r9d, r9d
0x180016ebb  lea     r8, aD_0; "D"
0x180016ec2  xor     edx, edx
0x180016ec4  mov     rcx, rax
0x180016ec7  call    cs:__imp_WdsSetupLogMessageW
0x180016ecd  jmp     loc_180016FE5
0x180016ed2  lea     rdx, aPhase; "Phase"
0x180016ed9  lea     rcx, [rsp+148h+var_60]
0x180016ee1  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180016ee7  nop
0x180016ee8  mov     rdx, rax
0x180016eeb  mov     rcx, rbx
0x180016eee  call    cs:__imp_?get_Item@XmlAttributeCollection@UnBCL@@QEAAPEAVXmlAttribute@2@PEAVString@2@@Z; UnBCL::XmlAttributeCollection::get_Item(UnBCL::String *)
0x180016ef4  mov     rbx, rax
0x180016ef7  lea     rax, ??_7?$SmartPtr@VXmlAttribute@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::XmlAttribute>::`vftable'
0x180016efe  mov     [rsp+148h+var_C8], rax
0x180016f06  mov     [rsp+148h+var_C0], 0
0x180016f12  test    rbx, rbx
0x180016f15  jz      short loc_180016F20
0x180016f17  mov     rcx, rbx
0x180016f1a  call    cs:__imp_?AddRef@Object@UnBCL@@QEAAXXZ; UnBCL::Object::AddRef(void)
0x180016f20  mov     [rsp+148h+var_C0], rbx
0x180016f28  lea     rcx, [rsp+148h+var_60]
0x180016f30  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x180016f36  test    rbx, rbx
0x180016f39  jnz     short loc_180016FB1
0x180016f3b  call    cs:__imp_GetLastError
0x180016f41  mov     edi, eax
0x180016f43  call    cs:__imp_CurrentIP
0x180016f49  mov     rbx, rax
0x180016f4c  mov     r8d, r15d
0x180016f4f  lea     rdx, aRunNodeDHasNoP; "<Run> node %d has no Phase attribute"
0x180016f56  mov     ecx, 3000000h; unsigned int
0x180016f5b  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180016f60  mov     [rsp+148h+var_F8], 0
0x180016f68  mov     [rsp+148h+var_100], 0
0x180016f71  mov     [rsp+148h+var_108], edi
0x180016f75  mov     [rsp+148h+var_110], rbx
0x180016f7a  lea     rcx, aPgetresetendno; "pGetResetEndNode"
0x180016f81  mov     [rsp+148h+var_118], rcx
0x180016f86  lea     rcx, aBaseNtsetupSet_2; "base\\ntsetup\\setup\\tools\\setupclean"...
0x180016f8d  mov     [rsp+148h+var_120], rcx
0x180016f92  mov     [rsp+148h+var_128], 8Eh
0x180016f9a  xor     r9d, r9d
0x180016f9d  lea     r8, aD_0; "D"
0x180016fa4  xor     edx, edx
0x180016fa6  mov     rcx, rax
0x180016fa9  call    cs:__imp_WdsSetupLogMessageW
0x180016faf  jmp     short loc_180016FD7
0x180016fb1  mov     rcx, rbx
0x180016fb4  call    cs:__imp_?get_Value@XmlNode@UnBCL@@QEAAPEAVString@2@XZ; UnBCL::XmlNode::get_Value(void)
0x180016fba  mov     rcx, rax
0x180016fbd  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180016fc3  mov     rcx, rax; String1
0x180016fc6  lea     rdx, aFactoryresetAf; "FactoryReset_AfterImageApply"
0x180016fcd  call    cs:__imp__wcsicmp
0x180016fd3  test    eax, eax
0x180016fd5  jz      short loc_180017011
0x180016fd7  lea     rcx, [rsp+148h+var_C8]
0x180016fdf  call    ??1?$SmartPtr@VXmlAttribute@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::XmlAttribute>::~SmartPtr<UnBCL::XmlAttribute>(void)
0x180016fe4  nop
0x180016fe5  lea     rcx, [rsp+148h+var_A8]
0x180016fed  call    ??1?$SmartPtr@VXmlAttributeCollection@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::XmlAttributeCollection>::~SmartPtr<UnBCL::XmlAttributeCollection>(void)
0x180016ff2  inc     r15d
0x180016ff5  mov     rcx, rsi
0x180016ff8  call    cs:__imp_?get_Count@XmlNodeList@UnBCL@@QEAAHXZ; UnBCL::XmlNodeList::get_Count(void)
0x180016ffe  cmp     r15d, eax
0x180017001  jl      loc_180016E08
0x180017007  mov     rdi, [rsp+148h+arg_0]
0x18001700f  jmp     short loc_18001702C
0x180017011  lea     rcx, [rsp+148h+var_C8]
0x180017019  call    ??1?$SmartPtr@VXmlAttribute@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::XmlAttribute>::~SmartPtr<UnBCL::XmlAttribute>(void)
0x18001701e  nop
0x18001701f  lea     rcx, [rsp+148h+var_A8]
0x180017027  call    ??1?$SmartPtr@VXmlAttributeCollection@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::XmlAttributeCollection>::~SmartPtr<UnBCL::XmlAttributeCollection>(void)
0x18001702c  mov     rbx, [rsp+148h+arg_20]
0x180017034  xor     r15d, r15d
0x180017037  test    rbx, rbx
0x18001703a  jz      loc_1800170FF
0x180017040  mov     [rbx], r15d
0x180017043  test    rdi, rdi
0x180017046  jz      loc_1800170FF
0x18001704c  lea     rdx, aReset; "/Reset"
0x180017053  lea     rcx, [rsp+148h+var_48]
0x18001705b  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180017061  nop
0x180017062  mov     rdx, rax
0x180017065  mov     rcx, r14
0x180017068  call    cs:__imp_?SelectSingleNode@XmlNode@UnBCL@@QEAAPEAV12@PEAVString@2@@Z; UnBCL::XmlNode::SelectSingleNode(UnBCL::String *)
0x18001706e  lea     rcx, ??_7?$SmartPtr@VXmlNode@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::XmlNode>::`vftable'
0x180017075  mov     [rsp+148h+var_98], rcx
0x18001707d  mov     [rsp+148h+var_90], r15
0x180017085  mov     rdx, rax
0x180017088  lea     rcx, [rsp+148h+var_98]
0x180017090  call    ?Assign@?$SmartPtr@VXmlNodeList@UnBCL@@@UnBCL@@AEAAXPEAVXmlNodeList@2@@Z; UnBCL::SmartPtr<UnBCL::XmlNodeList>::Assign(UnBCL::XmlNodeList *)
0x180017095  nop
0x180017096  lea     rcx, [rsp+148h+var_48]
0x18001709e  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x1800170a4  mov     rcx, [rsp+148h+var_90]
0x1800170ac  call    cs:__imp_?get_ChildNodes@XmlNode@UnBCL@@QEAAPEAVXmlNodeList@2@XZ; UnBCL::XmlNode::get_ChildNodes(void)
0x1800170b2  lea     rcx, ??_7?$SmartPtr@VXmlNodeList@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::XmlNodeList>::`vftable'
0x1800170b9  mov     [rsp+148h+var_D8], rcx
0x1800170be  mov     [rsp+148h+var_D0], r15
0x1800170c3  mov     rdx, rax
0x1800170c6  lea     rcx, [rsp+148h+var_D8]
0x1800170cb  call    ?Assign@?$SmartPtr@VXmlNodeList@UnBCL@@@UnBCL@@AEAAXPEAVXmlNodeList@2@@Z; UnBCL::SmartPtr<UnBCL::XmlNodeList>::Assign(UnBCL::XmlNodeList *)
0x1800170d0  nop
0x1800170d1  mov     rcx, [rsp+148h+var_D0]
0x1800170d6  call    cs:__imp_?get_Count@XmlNodeList@UnBCL@@QEAAHXZ; UnBCL::XmlNodeList::get_Count(void)
0x1800170dc  mov     ecx, r15d
0x1800170df  cmp     eax, 1
0x1800170e2  setz    cl
0x1800170e5  mov     [rbx], ecx
0x1800170e7  lea     rcx, [rsp+148h+var_D8]
0x1800170ec  call    ??1?$SmartPtr@VXmlNodeList@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::XmlNodeList>::~SmartPtr<UnBCL::XmlNodeList>(void)
0x1800170f1  nop
0x1800170f2  lea     rcx, [rsp+148h+var_98]
0x1800170fa  call    ??1?$SmartPtr@VXmlNode@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::XmlNode>::~SmartPtr<UnBCL::XmlNode>(void)
0x1800170ff  test    r14, r14
0x180017102  jnz     short loc_180017109
0x180017104  mov     r14, r15
0x180017107  jmp     short loc_180017117
0x180017109  mov     rcx, r14
0x18001710c  call    cs:__imp_?DecRef@Object@UnBCL@@QEAAHXZ; UnBCL::Object::DecRef(void)
0x180017112  mov     [rsp+148h+var_E0], r15
0x180017117  mov     [r12], r14
0x18001711b  test    rsi, rsi
0x18001711e  jnz     short loc_180017125
0x180017120  mov     rsi, r15
0x180017123  jmp     short loc_180017136
0x180017125  mov     rcx, rsi
0x180017128  call    cs:__imp_?DecRef@Object@UnBCL@@QEAAHXZ; UnBCL::Object::DecRef(void)
0x18001712e  mov     [rsp+148h+var_B0], r15
0x180017136  mov     rax, [rsp+148h+arg_10]
0x18001713e  mov     [rax], rsi
0x180017141  mov     [r13+0], rdi
0x180017145  lea     rcx, [rsp+148h+var_B8]
0x18001714d  call    ??1?$SmartPtr@VXmlNodeList@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::XmlNodeList>::~SmartPtr<UnBCL::XmlNodeList>(void)
0x180017152  nop
0x180017153  lea     rcx, [rsp+148h+var_E8]
0x180017158  call    ??1?$SmartPtr@VXmlDocument@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::XmlDocument>::~SmartPtr<UnBCL::XmlDocument>(void)
0x18001715d  xor     eax, eax
0x18001715f  jmp     short loc_180017177
0x180017161  lea     rcx, [rsp+148h+var_E8]
0x180017166  call    ??1?$SmartPtr@VXmlDocument@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::XmlDocument>::~SmartPtr<UnBCL::XmlDocument>(void)
0x18001716b  mov     eax, 80004005h
0x180017170  jmp     short loc_180017177
0x180017172  mov     eax, 80070057h
0x180017177  lea     r11, [rsp+148h+var_28]
0x18001717f  mov     rbx, [r11+38h]
0x180017183  mov     rsi, [r11+48h]
0x180017187  mov     rsp, r11
0x18001718a  pop     r15
0x18001718c  pop     r14
0x18001718e  pop     r13
0x180017190  pop     r12
0x180017192  pop     rdi
0x180017193  retn
```
