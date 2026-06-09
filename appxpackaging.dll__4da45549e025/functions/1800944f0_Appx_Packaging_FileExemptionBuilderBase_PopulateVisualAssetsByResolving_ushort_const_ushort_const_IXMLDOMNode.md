# Appx::Packaging::FileExemptionBuilderBase::PopulateVisualAssetsByResolving(ushort const *,ushort const *,IXMLDOMNode *)

- ea: `0x1800944f0`
- end: `0x180094a2f`
- name: `?PopulateVisualAssetsByResolving@FileExemptionBuilderBase@Packaging@Appx@@AEAAJPEBG0PEAUIXMLDOMNode@@@Z`
- size: `1343`
- prototype: `int(Appx::Packaging::FileExemptionBuilderBase *__hidden this, const unsigned __int16 *, const unsigned __int16 *, struct IXMLDOMNode *)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800fe974`

## callees

- `0x1800059f0`
- `0x180005eb8`
- `0x18002cf44`
- `0x180039ef0`
- `0x1800424a0`
- `0x180082468`
- `0x180094044`
- `0x180094280`
- `0x1800944f0`
- `0x180094a38`
- `0x180094a70`
- `0x1800992c4`
- `0x1800fb888`
- `0x1800febfc`
- `0x180106010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180094903`
- `OLEAUT32!__imp_SysFreeString` at `0x18009493c`
- `OLEAUT32!__imp_SysFreeString` at `0x180094983`
- `OLEAUT32!__imp_SysFreeString` at `0x180094903`
- `OLEAUT32!__imp_SysFreeString` at `0x18009493c`
- `OLEAUT32!__imp_SysFreeString` at `0x180094983`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180094527`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180094527`

## string_xrefs

- `0x180094925`: `AddExemptedFilePathIfNotExists(sourcePackageName, valueBstr.Value())`
- `0x180094691`: `xpathFormatBuilder.AppendString( L"/*[local-name()='NamedResource' and translate(@name,'ABCDEFGHIJKLMNOPQRSTUVWXYZ','abcdefghijklmnopqrstuvwxyz')='%s']/*[local-name()='Candidate' and @type='Path']/*[local-name()='Value']")`
- `0x180094577`: `xpathFormat.SetValueFromString(L"*[local-name()='ResourceMap']/*[local-name()='ResourceMapSubtree' and @name='Files']")`
- `0x18009484d`: `AddExemptedFilePathIfNotExists( sourcePackageName, resourcePath)`
- `0x1800945cb`: `StringHelper::AllocAndCopyString(resourcePath, &resourcePathLocal, nullptr)`
- `0x180094742`: `xpathFormatBuilder.AppendString(parts[i])`
- `0x180094619`: `StringHelper::SplitString(resourcePathLocal, L'\\', parts)`
- `0x180094767`: `xpathFormatBuilder.AppendString( L"/*[local-name()='ResourceMapSubtree' and translate(@name,'ABCDEFGHIJKLMNOPQRSTUVWXYZ','abcdefghijklmnopqrstuvwxyz')='")`
- `0x18009471d`: `xpathFormatBuilder.AppendString(L"']")`
- `0x1800947b7`: `RetrieveCandidateNodeByXPath( xpathFormat.GetChars(), resourceFileName, resourcesPriDumpNode, &resolvedValues)`
- `0x180094678`: `/*[local-name()='NamedResource' and translate(@name,'ABCDEFGHIJKLMNOPQRSTUVWXYZ','abcdefghijklmnopqrstuvwxyz')='%s']/*[local-name()='Candidate' and @type='Path']/*[local-name()='Value']`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Appx::Packaging::FileExemptionBuilderBase::PopulateVisualAssetsByResolving(
        Appx::Packaging::FileExemptionBuilderBase *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct IXMLDOMNode *a4)
{
  int v5; // eax
  bool v6; // cl
  unsigned int v7; // ebx
  unsigned __int64 v8; // rdx
  int v10; // eax
  unsigned __int16 v11; // dx
  bool v12; // cl
  unsigned __int16 v13; // r8
  unsigned __int64 v14; // rdx
  BSTR v15; // rbx
  __int64 v16; // rdx
  int v17; // eax
  bool v18; // cl
  int v19; // edi
  unsigned __int64 v20; // rdx
  unsigned __int64 v21; // rdx
  unsigned int v22; // r14d
  unsigned __int64 v23; // r15
  __int64 v24; // r12
  int appended; // eax
  bool v26; // cl
  unsigned __int64 v27; // rdx
  bool v28; // cl
  unsigned __int16 *v29; // rcx
  __int64 v30; // rdx
  const unsigned __int16 *v31; // rdx
  int v32; // eax
  bool v33; // cl
  int v34; // eax
  bool v35; // cl
  unsigned __int64 v36; // rdx
  unsigned __int64 v37; // rdx
  unsigned __int64 v38; // rdx
  int v39; // eax
  bool v40; // cl
  unsigned __int64 v41; // rdx
  struct IXMLDOMNodeList *v42; // r14
  int v43; // eax
  const unsigned __int16 *v44; // rdx
  bool v45; // cl
  unsigned __int64 v46; // rdx
  int v47; // eax
  int v48; // eax
  bool v49; // cl
  unsigned __int64 v50; // rdx
  int i; // esi
  HRESULT (__stdcall *nextNode)(IXMLDOMNodeList *, IXMLDOMNode **); // rdi
  int v53; // eax
  bool v54; // cl
  int v55; // eax
  const unsigned __int16 *v56; // rdx
  bool v57; // cl
  int v58; // eax
  bool v59; // cl
  unsigned __int64 v60; // rdx
  unsigned __int64 v61; // rdx
  unsigned __int64 v62; // rdx
  unsigned __int64 v63; // rdx
  unsigned __int64 v64; // rdx
  struct IXMLDOMNodeList *v65; // [rsp+28h] [rbp-49h] BYREF
  unsigned __int16 *FileNameW; // [rsp+30h] [rbp-41h] BYREF
  BSTR bstrString; // [rsp+38h] [rbp-39h] BYREF
  unsigned __int16 *v68[2]; // [rsp+40h] [rbp-31h] BYREF
  int v69; // [rsp+50h] [rbp-21h]
  _QWORD v70[2]; // [rsp+58h] [rbp-19h] BYREF
  unsigned __int64 v71; // [rsp+68h] [rbp-9h]
  char v72; // [rsp+70h] [rbp-1h]
  _QWORD v73[10]; // [rsp+78h] [rbp+7h] BYREF
  const unsigned __int16 *v75; // [rsp+E8h] [rbp+77h] BYREF
  struct IXMLDOMNode *v76; // [rsp+F0h] [rbp+7Fh]

  v76 = a4;
  v75 = a3;
  v73[3] = -2;
  FileNameW = PathFindFileNameW(a2);
  *(_OWORD *)v68 = 0;
  v69 = 0;
  v73[1] = v68;
  v73[0] = &Common::StringBufferBuilder::`vftable';
  v73[2] = v68;
  v5 = Common::StringBuffer::SetValueFromString(
         (Common::StringBuffer *)v68,
         L"*[local-name()='ResourceMap']/*[local-name()='ResourceMapSubtree' and @name='Files']");
  v7 = v5;
  if ( v5 < 0 )
  {
    Appx::Packaging::SharedWithTools::Logging::WriteFailure(
      v6,
      v5,
      "xpathFormat.SetValueFromString(L\"*[local-name()='ResourceMap']/*[local-name()='ResourceMapSubtree' and @name='Files']\")",
      0);
    Appx::Packaging::SharedWithTools::Logging::WriteLastErrorInfo();
LABEL_3:
    if ( v68[1] )
      operator delete(v68[1], v8);
    return v7;
  }
  v70[0] = 0;
  v70[1] = 0;
  v71 = 0;
  v72 = 1;
  bstrString = 0;
  v10 = Appx::Packaging::StringHelper::AllocAndCopyString(a2, &bstrString, 0);
  v7 = v10;
  if ( v10 < 0 )
  {
    Appx::Packaging::SharedWithTools::Logging::WriteFailure(
      v12,
      v10,
      "StringHelper::AllocAndCopyString(resourcePath, &resourcePathLocal, nullptr)",
      0);
    Appx::Packaging::SharedWithTools::Logging::WriteLastErrorInfo();
    operator delete(bstrString, v14);
    Common::Array<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::ContainerOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::NoKey,Common::ContainerOperations<Common::NoKey,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::ArrayOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::NoKey>>::~Array<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::ContainerOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::NoKey,Common::ContainerOperations<Common::NoKey,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::ArrayOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::NoKey>>(v70);
    goto LABEL_3;
  }
  v15 = bstrString;
  Appx::Packaging::StringHelper::ReplaceAll(bstrString, v11, v13);
  v72 = 0;
  v17 = Appx::Packaging::StringHelper::SplitString(v15, v16, v70);
  v19 = v17;
  if ( v17 < 0 )
  {
    Appx::Packaging::SharedWithTools::Logging::WriteFailure(
      v18,
      v17,
      "StringHelper::SplitString(resourcePathLocal, L'\\\\', parts)",
      0);
    Appx::Packaging::SharedWithTools::Logging::WriteLastErrorInfo();
    operator delete(v15, v20);
LABEL_10:
    Common::Array<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::ContainerOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::NoKey,Common::ContainerOperations<Common::NoKey,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::ArrayOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::NoKey>>::~Array<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::ContainerOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::NoKey,Common::ContainerOperations<Common::NoKey,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::ArrayOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::NoKey>>(v70);
    if ( v68[1] )
      operator delete(v68[1], v21);
    return (unsigned int)v19;
  }
  v22 = 0;
  v23 = v71;
  v24 = v70[0];
  while ( v22 < v23 )
  {
    if ( v22 == v23 - 1 )
    {
      appended = Common::StringBuilder::AppendString(
                   (Common::StringBuilder *)v73,
                   L"/*[local-name()='NamedResource' and translate(@name,'ABCDEFGHIJKLMNOPQRSTUVWXYZ','abcdefghijklmnopqrs"
                    "tuvwxyz')='%s']/*[local-name()='Candidate' and @type='Path']/*[local-name()='Value']");
      v19 = appended;
      if ( appended < 0 )
      {
        Appx::Packaging::SharedWithTools::Logging::WriteFailure(
          v26,
          appended,
          "xpathFormatBuilder.AppendString( L\"/*[local-name()='NamedResource' and translate(@name,'ABCDEFGHIJKLMNOPQRSTU"
          "VWXYZ','abcdefghijklmnopqrstuvwxyz')='%s']/*[local-name()='Candidate' and @type='Path']/*[local-name()='Value']\")",
          0);
        Appx::Packaging::SharedWithTools::Logging::WriteLastErrorInfo();
        operator delete(v15, v27);
        goto LABEL_10;
      }
    }
    else
    {
      v19 = Common::StringBuilder::AppendString(
              (Common::StringBuilder *)v73,
              L"/*[local-name()='ResourceMapSubtree' and translate(@name,'ABCDEFGHIJKLMNOPQRSTUVWXYZ','abcdefghijklmnopqrstuvwxyz')='");
      if ( v19 < 0 )
      {
        Appx::Packaging::SharedWithTools::Logging::WriteFailure(
          v28,
          v19,
          "xpathFormatBuilder.AppendString( L\"/*[local-name()='ResourceMapSubtree' and translate(@name,'ABCDEFGHIJKLMNOP"
          "QRSTUVWXYZ','abcdefghijklmnopqrstuvwxyz')='\")",
          0);
        Appx::Packaging::SharedWithTools::Logging::WriteLastErrorInfo();
        operator delete(v15, v38);
        goto LABEL_10;
      }
      v29 = *(unsigned __int16 **)(v24 + 8LL * v22);
      v30 = -1;
      do
        ++v30;
      while ( v29[v30] );
      Common::String::ToLowerAscii(v29, v30);
      if ( v22 < v23 )
        v31 = *(const unsigned __int16 **)(v24 + 8LL * v22);
      else
        v31 = 0;
      v32 = Common::StringBuilder::AppendString((Common::StringBuilder *)v73, v31);
      v19 = v32;
      if ( v32 < 0 )
      {
        Appx::Packaging::SharedWithTools::Logging::WriteFailure(
          v33,
          v32,
          "xpathFormatBuilder.AppendString(parts[i])",
          0);
        Appx::Packaging::SharedWithTools::Logging::WriteLastErrorInfo();
        operator delete(v15, v37);
        goto LABEL_10;
      }
      v34 = Common::StringBuilder::AppendString((Common::StringBuilder *)v73, L"']");
      v19 = v34;
      if ( v34 < 0 )
      {
        Appx::Packaging::SharedWithTools::Logging::WriteFailure(v35, v34, "xpathFormatBuilder.AppendString(L\"']\")", 0);
        Appx::Packaging::SharedWithTools::Logging::WriteLastErrorInfo();
        operator delete(v15, v36);
        goto LABEL_10;
      }
    }
    ++v22;
  }
  v65 = 0;
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v65);
  v39 = Appx::Packaging::FileExemptionBuilderBase::RetrieveCandidateNodeByXPath(v68[1], FileNameW, v76, &v65);
  v19 = v39;
  if ( v39 < 0 )
  {
    Appx::Packaging::SharedWithTools::Logging::WriteFailure(
      v40,
      v39,
      "RetrieveCandidateNodeByXPath( xpathFormat.GetChars(), resourceFileName, resourcesPriDumpNode, &resolvedValues)",
      0);
    Appx::Packaging::SharedWithTools::Logging::WriteLastErrorInfo();
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v65);
    operator delete(v15, v41);
    goto LABEL_10;
  }
  LODWORD(v75) = 0;
  v42 = v65;
  v43 = ((__int64 (__fastcall *)(struct IXMLDOMNodeList *, const unsigned __int16 **))v65->lpVtbl->get_length)(
          v65,
          &v75);
  v19 = v43;
  if ( v43 < 0 )
  {
    Appx::Packaging::SharedWithTools::Logging::WriteFailure(
      v45,
      v43,
      "resolvedValues->get_length(&resolvedValuesLen)",
      0);
    Appx::Packaging::SharedWithTools::Logging::WriteLastErrorInfo();
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v65);
    operator delete(v15, v46);
    goto LABEL_10;
  }
  v47 = (int)v75;
  if ( (_DWORD)v75 )
  {
    for ( i = 0; i < v47; ++i )
    {
      FileNameW = 0;
      nextNode = v42->lpVtbl->nextNode;
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&FileNameW);
      v53 = ((__int64 (__fastcall *)(struct IXMLDOMNodeList *, unsigned __int16 **))nextNode)(v42, &FileNameW);
      v19 = v53;
      if ( v53 < 0 )
      {
        Appx::Packaging::SharedWithTools::Logging::WriteFailure(
          v54,
          v53,
          "resolvedValues->nextNode(&currentValNode)",
          0);
        Appx::Packaging::SharedWithTools::Logging::WriteLastErrorInfo();
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&FileNameW);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v65);
        operator delete(v15, v62);
        goto LABEL_10;
      }
      bstrString = 0;
      v55 = (*(__int64 (__fastcall **)(unsigned __int16 *, BSTR *))(*(_QWORD *)FileNameW + 208LL))(
              FileNameW,
              &bstrString);
      v19 = v55;
      if ( v55 < 0 )
      {
        Appx::Packaging::SharedWithTools::Logging::WriteFailure(v57, v55, "currentValNode->get_text(&valueBstr)", 0);
        Appx::Packaging::SharedWithTools::Logging::WriteLastErrorInfo();
        SysFreeString(bstrString);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&FileNameW);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v65);
        operator delete(v15, v61);
        goto LABEL_10;
      }
      v58 = Appx::Packaging::FileExemptionBuilderBase::AddExemptedFilePathIfNotExists(this, v56, bstrString);
      v19 = v58;
      if ( v58 < 0 )
      {
        Appx::Packaging::SharedWithTools::Logging::WriteFailure(
          v59,
          v58,
          "AddExemptedFilePathIfNotExists(sourcePackageName, valueBstr.Value())",
          0);
        Appx::Packaging::SharedWithTools::Logging::WriteLastErrorInfo();
        SysFreeString(bstrString);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&FileNameW);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v65);
        operator delete(v15, v60);
        goto LABEL_10;
      }
      SysFreeString(bstrString);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&FileNameW);
      v47 = (int)v75;
    }
  }
  else
  {
    v48 = Appx::Packaging::FileExemptionBuilderBase::AddExemptedFilePathIfNotExists(this, v44, a2);
    v19 = v48;
    if ( v48 < 0 )
    {
      Appx::Packaging::SharedWithTools::Logging::WriteFailure(
        v49,
        v48,
        "AddExemptedFilePathIfNotExists( sourcePackageName, resourcePath)",
        0);
      Appx::Packaging::SharedWithTools::Logging::WriteLastErrorInfo();
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v65);
      operator delete(v15, v50);
      goto LABEL_10;
    }
  }
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v65);
  operator delete(v15, v63);
  Common::Array<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::ContainerOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::NoKey,Common::ContainerOperations<Common::NoKey,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::ArrayOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::NoKey>>::~Array<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::ContainerOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::NoKey,Common::ContainerOperations<Common::NoKey,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::ArrayOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::NoKey>>(v70);
  if ( v68[1] )
    operator delete(v68[1], v64);
  return 0;
}

```

## disassembly

```asm
0x1800944f0  mov     rax, rsp
0x1800944f3  mov     [rax+20h], r9
0x1800944f7  mov     [rax+18h], r8
0x1800944fb  mov     [rax+8], rcx
0x1800944ff  push    rbp
0x180094500  push    rsi
0x180094501  push    rdi
0x180094502  push    r12
0x180094504  push    r13
0x180094506  push    r14
0x180094508  push    r15
0x18009450a  lea     rbp, [rax-5Fh]
0x18009450e  sub     rsp, 90h
0x180094515  mov     [rbp+57h+var_38], 0FFFFFFFFFFFFFFFEh
0x18009451d  mov     [rax+10h], rbx
0x180094521  mov     r13, rdx
0x180094524  mov     rcx, rdx; pszPath
0x180094527  call    cs:__imp_PathFindFileNameW
0x18009452e  nop     dword ptr [rax+rax+00h]
0x180094533  mov     [rbp+57h+var_98], rax
0x180094537  xorps   xmm0, xmm0
0x18009453a  movups  xmmword ptr [rbp+57h+var_88], xmm0
0x18009453e  xor     esi, esi
0x180094540  mov     [rbp+57h+var_78], esi
0x180094543  lea     rax, [rbp+57h+var_88]
0x180094547  mov     [rbp+57h+var_48], rax
0x18009454b  lea     rax, ??_7StringBufferBuilder@Common@@6B@; const Common::StringBufferBuilder::`vftable'
0x180094552  mov     [rbp+57h+var_50], rax
0x180094556  lea     rax, [rbp+57h+var_88]
0x18009455a  mov     [rbp+57h+var_40], rax
0x18009455e  lea     rdx, aLocalNameResou; "*[local-name()='ResourceMap']/*[local-n"...
0x180094565  lea     rcx, [rbp+57h+var_88]; this
0x180094569  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x18009456e  mov     ebx, eax
0x180094570  test    eax, eax
0x180094572  jns     short loc_18009459F
0x180094574  xor     r9d, r9d; unsigned __int16 *
0x180094577  lea     r8, aXpathformatSet; "xpathFormat.SetValueFromString(L\"*[loc"...
0x18009457e  mov     edx, eax; int
0x180094580  call    ?WriteFailure@Logging@SharedWithTools@Packaging@Appx@@SAX_NJPEBDPEBG@Z; Appx::Packaging::SharedWithTools::Logging::WriteFailure(bool,long,char const *,ushort const *)
0x180094585  call    ?WriteLastErrorInfo@Logging@SharedWithTools@Packaging@Appx@@SAXXZ; Appx::Packaging::SharedWithTools::Logging::WriteLastErrorInfo(void)
0x18009458a  mov     rcx, [rbp+57h+var_88+8]; void *
0x18009458e  test    rcx, rcx
0x180094591  jz      short loc_180094598
0x180094593  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180094598  mov     eax, ebx
0x18009459a  jmp     loc_180094A13
0x18009459f  mov     [rbp+57h+var_70], rsi
0x1800945a3  mov     [rbp+57h+var_68], rsi
0x1800945a7  mov     [rbp+57h+var_60], rsi
0x1800945ab  mov     [rbp+57h+var_58], 1
0x1800945af  mov     [rbp+57h+bstrString], rsi
0x1800945b3  xor     r8d, r8d; unsigned int *
0x1800945b6  lea     rdx, [rbp+57h+bstrString]; unsigned __int16 **
0x1800945ba  mov     rcx, r13; unsigned __int16 *
0x1800945bd  call    ?AllocAndCopyString@StringHelper@Packaging@Appx@@SAJPEBGPEAPEAGPEAI@Z; Appx::Packaging::StringHelper::AllocAndCopyString(ushort const *,ushort * *,uint *)
0x1800945c2  mov     ebx, eax
0x1800945c4  test    eax, eax
0x1800945c6  jns     short loc_1800945F4
0x1800945c8  xor     r9d, r9d; unsigned __int16 *
0x1800945cb  lea     r8, aStringhelperAl_0; "StringHelper::AllocAndCopyString(resour"...
0x1800945d2  mov     edx, eax; int
0x1800945d4  call    ?WriteFailure@Logging@SharedWithTools@Packaging@Appx@@SAX_NJPEBDPEBG@Z; Appx::Packaging::SharedWithTools::Logging::WriteFailure(bool,long,char const *,ushort const *)
0x1800945d9  call    ?WriteLastErrorInfo@Logging@SharedWithTools@Packaging@Appx@@SAXXZ; Appx::Packaging::SharedWithTools::Logging::WriteLastErrorInfo(void)
0x1800945de  nop
0x1800945df  mov     rcx, [rbp+57h+bstrString]; void *
0x1800945e3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800945e8  nop
0x1800945e9  lea     rcx, [rbp+57h+var_70]
0x1800945ed  call    ??1?$Array@U__MIDL___MIDL_itf_appxdatasource_0000_0000_0003@@V?$ContainerOperations@U__MIDL___MIDL_itf_appxdatasource_0000_0000_0003@@U1@@Common@@VNoKey@3@V?$ContainerOperations@VNoKey@Common@@U__MIDL___MIDL_itf_appxdatasource_0000_0000_0003@@@3@V?$ArrayOperations@U__MIDL___MIDL_itf_appxdatasource_0000_0000_0003@@VNoKey@Common@@@3@@Common@@QEAA@XZ; Common::Array<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::ContainerOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::NoKey,Common::ContainerOperations<Common::NoKey,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::ArrayOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::NoKey>>::~Array<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::ContainerOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::NoKey,Common::ContainerOperations<Common::NoKey,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::ArrayOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::NoKey>>(void)
0x1800945f2  jmp     short loc_18009458A
0x1800945f4  mov     rbx, [rbp+57h+bstrString]
0x1800945f8  mov     rcx, rbx; unsigned __int16 *
0x1800945fb  call    ?ReplaceAll@StringHelper@Packaging@Appx@@SAXPEAGGG@Z; Appx::Packaging::StringHelper::ReplaceAll(ushort *,ushort,ushort)
0x180094600  mov     [rbp+57h+var_58], sil
0x180094604  lea     r8, [rbp+57h+var_70]
0x180094608  mov     rcx, rbx
0x18009460b  call    ?SplitString@StringHelper@Packaging@Appx@@SAJPEAGGAEAV?$Array@GV?$ContainerOperations@GG@Common@@VNoKey@2@V?$ContainerOperations@VNoKey@Common@@G@2@V?$ArrayOperations@GVNoKey@Common@@@2@@Common@@@Z; Appx::Packaging::StringHelper::SplitString(ushort *,ushort,Common::Array<ushort,Common::ContainerOperations<ushort,ushort>,Common::NoKey,Common::ContainerOperations<Common::NoKey,ushort>,Common::ArrayOperations<ushort,Common::NoKey>> &)
0x180094610  mov     edi, eax
0x180094612  test    eax, eax
0x180094614  jns     short loc_180094654
0x180094616  xor     r9d, r9d; unsigned __int16 *
0x180094619  lea     r8, aStringhelperSp; "StringHelper::SplitString(resourcePathL"...
0x180094620  mov     edx, eax; int
0x180094622  call    ?WriteFailure@Logging@SharedWithTools@Packaging@Appx@@SAX_NJPEBDPEBG@Z; Appx::Packaging::SharedWithTools::Logging::WriteFailure(bool,long,char const *,ushort const *)
0x180094627  call    ?WriteLastErrorInfo@Logging@SharedWithTools@Packaging@Appx@@SAXXZ; Appx::Packaging::SharedWithTools::Logging::WriteLastErrorInfo(void)
0x18009462c  nop
0x18009462d  mov     rcx, rbx; void *
0x180094630  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180094635  nop
0x180094636  lea     rcx, [rbp+57h+var_70]
0x18009463a  call    ??1?$Array@U__MIDL___MIDL_itf_appxdatasource_0000_0000_0003@@V?$ContainerOperations@U__MIDL___MIDL_itf_appxdatasource_0000_0000_0003@@U1@@Common@@VNoKey@3@V?$ContainerOperations@VNoKey@Common@@U__MIDL___MIDL_itf_appxdatasource_0000_0000_0003@@@3@V?$ArrayOperations@U__MIDL___MIDL_itf_appxdatasource_0000_0000_0003@@VNoKey@Common@@@3@@Common@@QEAA@XZ; Common::Array<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::ContainerOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::NoKey,Common::ContainerOperations<Common::NoKey,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::ArrayOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::NoKey>>::~Array<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::ContainerOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::NoKey,Common::ContainerOperations<Common::NoKey,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::ArrayOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::NoKey>>(void)
0x18009463f  mov     rcx, [rbp+57h+var_88+8]; void *
0x180094643  test    rcx, rcx
0x180094646  jz      short loc_18009464D
0x180094648  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18009464d  mov     eax, edi
0x18009464f  jmp     loc_180094A13
0x180094654  mov     r14d, esi
0x180094657  mov     r15, [rbp+57h+var_60]
0x18009465b  mov     r12, [rbp+57h+var_70]
0x18009465f  mov     esi, r14d
0x180094662  cmp     rsi, r15
0x180094665  jnb     loc_180094789
0x18009466b  lea     rax, [r15-1]
0x18009466f  lea     rcx, [rbp+57h+var_50]; this
0x180094673  cmp     rsi, rax
0x180094676  jnz     short loc_1800946B0
0x180094678  lea     rdx, aLocalNameNamed; "/*[local-name()='NamedResource' and tra"...
0x18009467f  call    ?AppendString@StringBuilder@Common@@QEAAJPEBG@Z; Common::StringBuilder::AppendString(ushort const *)
0x180094684  mov     edi, eax
0x180094686  test    eax, eax
0x180094688  jns     loc_180094712
0x18009468e  xor     r9d, r9d; unsigned __int16 *
0x180094691  lea     r8, aXpathformatbui_0; "xpathFormatBuilder.AppendString( L\"/*["...
0x180094698  mov     edx, eax; int
0x18009469a  call    ?WriteFailure@Logging@SharedWithTools@Packaging@Appx@@SAX_NJPEBDPEBG@Z; Appx::Packaging::SharedWithTools::Logging::WriteFailure(bool,long,char const *,ushort const *)
0x18009469f  call    ?WriteLastErrorInfo@Logging@SharedWithTools@Packaging@Appx@@SAXXZ; Appx::Packaging::SharedWithTools::Logging::WriteLastErrorInfo(void)
0x1800946a4  nop
0x1800946a5  mov     rcx, rbx; void *
0x1800946a8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800946ad  nop
0x1800946ae  jmp     short loc_180094636
0x1800946b0  lea     rdx, aLocalNameResou_1; "/*[local-name()='ResourceMapSubtree' an"...
0x1800946b7  call    ?AppendString@StringBuilder@Common@@QEAAJPEBG@Z; Common::StringBuilder::AppendString(ushort const *)
0x1800946bc  mov     edi, eax
0x1800946be  xor     eax, eax
0x1800946c0  test    edi, edi
0x1800946c2  js      loc_180094764
0x1800946c8  mov     rcx, [r12+rsi*8]; unsigned __int16 *
0x1800946cc  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800946d0  inc     rdx; unsigned int
0x1800946d3  cmp     [rcx+rdx*2], ax
0x1800946d7  jnz     short loc_1800946D0
0x1800946d9  call    ?ToLowerAscii@String@Common@@SAXPEAGK@Z; Common::String::ToLowerAscii(ushort *,ulong)
0x1800946de  cmp     rsi, r15
0x1800946e1  jb      short loc_1800946E9
0x1800946e3  xor     esi, esi
0x1800946e5  mov     edx, esi
0x1800946e7  jmp     short loc_1800946ED
0x1800946e9  mov     rdx, [r12+rsi*8]; unsigned __int16 *
0x1800946ed  lea     rcx, [rbp+57h+var_50]; this
0x1800946f1  call    ?AppendString@StringBuilder@Common@@QEAAJPEBG@Z; Common::StringBuilder::AppendString(ushort const *)
0x1800946f6  mov     edi, eax
0x1800946f8  test    eax, eax
0x1800946fa  js      short loc_18009473F
0x1800946fc  lea     rdx, asc_18014C3BC; "']"
0x180094703  lea     rcx, [rbp+57h+var_50]; this
0x180094707  call    ?AppendString@StringBuilder@Common@@QEAAJPEBG@Z; Common::StringBuilder::AppendString(ushort const *)
0x18009470c  mov     edi, eax
0x18009470e  test    eax, eax
0x180094710  js      short loc_18009471A
0x180094712  inc     r14d
0x180094715  jmp     loc_18009465F
0x18009471a  xor     r9d, r9d; unsigned __int16 *
0x18009471d  lea     r8, aXpathformatbui_1; "xpathFormatBuilder.AppendString(L\"']\""...
0x180094724  mov     edx, edi; int
0x180094726  call    ?WriteFailure@Logging@SharedWithTools@Packaging@Appx@@SAX_NJPEBDPEBG@Z; Appx::Packaging::SharedWithTools::Logging::WriteFailure(bool,long,char const *,ushort const *)
0x18009472b  call    ?WriteLastErrorInfo@Logging@SharedWithTools@Packaging@Appx@@SAXXZ; Appx::Packaging::SharedWithTools::Logging::WriteLastErrorInfo(void)
0x180094730  nop
0x180094731  mov     rcx, rbx; void *
0x180094734  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180094739  nop
0x18009473a  jmp     loc_180094636
0x18009473f  xor     r9d, r9d; unsigned __int16 *
0x180094742  lea     r8, aXpathformatbui_2; "xpathFormatBuilder.AppendString(parts[i"...
0x180094749  mov     edx, edi; int
0x18009474b  call    ?WriteFailure@Logging@SharedWithTools@Packaging@Appx@@SAX_NJPEBDPEBG@Z; Appx::Packaging::SharedWithTools::Logging::WriteFailure(bool,long,char const *,ushort const *)
0x180094750  call    ?WriteLastErrorInfo@Logging@SharedWithTools@Packaging@Appx@@SAXXZ; Appx::Packaging::SharedWithTools::Logging::WriteLastErrorInfo(void)
0x180094755  nop
0x180094756  mov     rcx, rbx; void *
0x180094759  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18009475e  nop
0x18009475f  jmp     loc_180094636
0x180094764  xor     r9d, r9d; unsigned __int16 *
0x180094767  lea     r8, aXpathformatbui; "xpathFormatBuilder.AppendString( L\"/*["...
0x18009476e  mov     edx, edi; int
0x180094770  call    ?WriteFailure@Logging@SharedWithTools@Packaging@Appx@@SAX_NJPEBDPEBG@Z; Appx::Packaging::SharedWithTools::Logging::WriteFailure(bool,long,char const *,ushort const *)
0x180094775  call    ?WriteLastErrorInfo@Logging@SharedWithTools@Packaging@Appx@@SAXXZ; Appx::Packaging::SharedWithTools::Logging::WriteLastErrorInfo(void)
0x18009477a  nop
0x18009477b  mov     rcx, rbx; void *
0x18009477e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180094783  nop
0x180094784  jmp     loc_180094636
0x180094789  xor     r12d, r12d
0x18009478c  mov     [rbp+57h+var_A0], r12
0x180094790  lea     rcx, [rbp+57h+var_A0]
0x180094794  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180094799  lea     r9, [rbp+57h+var_A0]; struct IXMLDOMNodeList **
0x18009479d  mov     r8, [rbp+57h+arg_18]; struct IXMLDOMNode *
0x1800947a1  mov     rdx, [rbp+57h+var_98]; unsigned __int16 *
0x1800947a5  mov     rcx, [rbp+57h+var_88+8]; unsigned __int16 *
0x1800947a9  call    ?RetrieveCandidateNodeByXPath@FileExemptionBuilderBase@Packaging@Appx@@CAJPEBG0PEAUIXMLDOMNode@@PEAPEAUIXMLDOMNodeList@@@Z; Appx::Packaging::FileExemptionBuilderBase::RetrieveCandidateNodeByXPath(ushort const *,ushort const *,IXMLDOMNode *,IXMLDOMNodeList * *)
0x1800947ae  mov     edi, eax
0x1800947b0  test    eax, eax
0x1800947b2  jns     short loc_1800947E2
0x1800947b4  xor     r9d, r9d; unsigned __int16 *
0x1800947b7  lea     r8, aRetrievecandid; "RetrieveCandidateNodeByXPath( xpathForm"...
0x1800947be  mov     edx, eax; int
0x1800947c0  call    ?WriteFailure@Logging@SharedWithTools@Packaging@Appx@@SAX_NJPEBDPEBG@Z; Appx::Packaging::SharedWithTools::Logging::WriteFailure(bool,long,char const *,ushort const *)
0x1800947c5  call    ?WriteLastErrorInfo@Logging@SharedWithTools@Packaging@Appx@@SAXXZ; Appx::Packaging::SharedWithTools::Logging::WriteLastErrorInfo(void)
0x1800947ca  lea     rcx, [rbp+57h+var_A0]
0x1800947ce  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800947d3  nop
0x1800947d4  mov     rcx, rbx; void *
0x1800947d7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800947dc  nop
0x1800947dd  jmp     loc_180094636
0x1800947e2  mov     dword ptr [rbp+57h+arg_10], r12d
0x1800947e6  mov     r14, [rbp+57h+var_A0]
0x1800947ea  mov     rax, [r14]
0x1800947ed  lea     rdx, [rbp+57h+arg_10]
0x1800947f1  mov     rcx, r14
0x1800947f4  mov     rax, [rax+40h]
0x1800947f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800947fd  mov     edi, eax
0x1800947ff  test    eax, eax
0x180094801  jns     short loc_180094831
0x180094803  xor     r9d, r9d; unsigned __int16 *
0x180094806  lea     r8, aResolvedvalues_0; "resolvedValues->get_length(&resolvedVal"...
0x18009480d  mov     edx, eax; int
0x18009480f  call    ?WriteFailure@Logging@SharedWithTools@Packaging@Appx@@SAX_NJPEBDPEBG@Z; Appx::Packaging::SharedWithTools::Logging::WriteFailure(bool,long,char const *,ushort const *)
0x180094814  call    ?WriteLastErrorInfo@Logging@SharedWithTools@Packaging@Appx@@SAXXZ; Appx::Packaging::SharedWithTools::Logging::WriteLastErrorInfo(void)
0x180094819  lea     rcx, [rbp+57h+var_A0]
0x18009481d  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180094822  nop
0x180094823  mov     rcx, rbx; void *
0x180094826  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18009482b  nop
0x18009482c  jmp     loc_180094636
0x180094831  mov     eax, dword ptr [rbp+57h+arg_10]
0x180094834  test    eax, eax
0x180094836  jnz     short loc_180094890
0x180094838  mov     r8, r13; unsigned __int16 *
0x18009483b  mov     rcx, [rbp+57h+arg_0]; this
0x18009483f  call    ?AddExemptedFilePathIfNotExists@FileExemptionBuilderBase@Packaging@Appx@@AEAAJPEBG0@Z; Appx::Packaging::FileExemptionBuilderBase::AddExemptedFilePathIfNotExists(ushort const *,ushort const *)
0x180094844  mov     edi, eax
0x180094846  test    eax, eax
0x180094848  jns     short loc_180094878
0x18009484a  xor     r9d, r9d; unsigned __int16 *
0x18009484d  lea     r8, aAddexemptedfil_0; "AddExemptedFilePathIfNotExists( sourceP"...
0x180094854  mov     edx, eax; int
0x180094856  call    ?WriteFailure@Logging@SharedWithTools@Packaging@Appx@@SAX_NJPEBDPEBG@Z; Appx::Packaging::SharedWithTools::Logging::WriteFailure(bool,long,char const *,ushort const *)
0x18009485b  call    ?WriteLastErrorInfo@Logging@SharedWithTools@Packaging@Appx@@SAXXZ; Appx::Packaging::SharedWithTools::Logging::WriteLastErrorInfo(void)
0x180094860  lea     rcx, [rbp+57h+var_A0]
0x180094864  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180094869  nop
0x18009486a  mov     rcx, rbx; void *
0x18009486d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180094872  nop
0x180094873  jmp     loc_180094636
0x180094878  lea     rcx, [rbp+57h+var_A0]
0x18009487c  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180094881  nop
0x180094882  mov     rcx, rbx; void *
0x180094885  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18009488a  nop
0x18009488b  jmp     loc_1800949FA
0x180094890  mov     esi, r12d
0x180094893  mov     r15, [rbp+57h+arg_0]
0x180094897  cmp     esi, eax
0x180094899  jge     loc_1800949E7
0x18009489f  mov     [rbp+57h+var_98], r12
0x1800948a3  mov     rax, [r14]
0x1800948a6  mov     rdi, [rax+48h]
0x1800948aa  lea     rcx, [rbp+57h+var_98]
0x1800948ae  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800948b3  lea     rdx, [rbp+57h+var_98]
0x1800948b7  mov     rcx, r14
0x1800948ba  mov     rax, rdi
0x1800948bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800948c2  mov     edi, eax
0x1800948c4  test    eax, eax
0x1800948c6  js      loc_1800949B0
0x1800948cc  mov     [rbp+57h+bstrString], r12
0x1800948d0  mov     rcx, [rbp+57h+var_98]
0x1800948d4  mov     rax, [rcx]
0x1800948d7  lea     rdx, [rbp+57h+bstrString]
0x1800948db  mov     rax, [rax+0D0h]
0x1800948e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800948e7  mov     edi, eax
0x1800948e9  test    eax, eax
0x1800948eb  js      short loc_180094969
0x1800948ed  mov     r8, [rbp+57h+bstrString]; unsigned __int16 *
0x1800948f1  mov     rcx, r15; this
0x1800948f4  call    ?AddExemptedFilePathIfNotExists@FileExemptionBuilderBase@Packaging@Appx@@AEAAJPEBG0@Z; Appx::Packaging::FileExemptionBuilderBase::AddExemptedFilePathIfNotExists(ushort const *,ushort const *)
0x1800948f9  mov     edi, eax
0x1800948fb  test    eax, eax
0x1800948fd  js      short loc_180094922
0x1800948ff  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180094903  call    cs:__imp_SysFreeString
0x18009490a  nop     dword ptr [rax+rax+00h]
0x18009490f  lea     rcx, [rbp+57h+var_98]
0x180094913  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180094918  inc     esi
0x18009491a  mov     eax, dword ptr [rbp+57h+arg_10]
0x18009491d  jmp     loc_180094897
0x180094922  xor     r9d, r9d; unsigned __int16 *
0x180094925  lea     r8, aAddexemptedfil_1; "AddExemptedFilePathIfNotExists(sourcePa"...
0x18009492c  mov     edx, edi; int
  ... truncated ...
```
