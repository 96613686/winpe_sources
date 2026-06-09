# DeclaredConfigurationStore_ParseDeclaredConfigurationXml(ushort const *,DeclaredConfigurationScopeData *,ushort const *,DCDocument &)

- ea: `0x180033230`
- end: `0x180033879`
- name: `?DeclaredConfigurationStore_ParseDeclaredConfigurationXml@@YAJPEBGPEAUDeclaredConfigurationScopeData@@0AEAVDCDocument@@@Z`
- size: `1609`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct DeclaredConfigurationScopeData *, const unsigned __int16 *, struct DCDocument *)`
- caller_count: `0`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800117dc`
- `0x180019d38`
- `0x18001c704`
- `0x18001cd00`
- `0x18001e190`
- `0x18001f7e8`
- `0x180033230`
- `0x1800370d4`
- `0x180048cd8`
- `0x18004a5d4`
- `0x18004a630`
- `0x18004a660`
- `0x18004a76c`
- `0x1800f5c8c`
- `0x1800f63e4`
- `0x18012d59c`
- `0x180139010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180033602`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180033602`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x180033341`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x180033341`
- `XmlLite!CreateXmlReader` at `0x180033418`
- `XmlLite!CreateXmlReader` at `0x180033418`
- `XmlLite!CreateXmlReaderInputWithEncodingName` at `0x1800333a1`
- `XmlLite!CreateXmlReaderInputWithEncodingName` at `0x1800333a1`

## string_xrefs

- `0x1800332d1`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcparse.cpp`
- `0x180033315`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcparse.cpp`
- `0x1800333b7`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcparse.cpp`
- `0x18003342e`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcparse.cpp`
- `0x1800334a3`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcparse.cpp`
- `0x180033515`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcparse.cpp`
- `0x18003358d`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcparse.cpp`
- `0x18003361b`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcparse.cpp`
- `0x18003369a`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcparse.cpp`
- `0x180033715`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcparse.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall DeclaredConfigurationStore_ParseDeclaredConfigurationXml(
        const unsigned __int16 *a1,
        struct DeclaredConfigurationScopeData *a2,
        const unsigned __int16 *a3,
        struct DCDocument *a4)
{
  CDeclaredConfigurationLogger *Logger; // rax
  int v8; // eax
  unsigned __int64 v9; // rdx
  unsigned int v10; // ebx
  int v12; // eax
  IStream *v13; // rax
  IUnknown *v14; // rbx
  HRESULT v15; // eax
  unsigned int v16; // esi
  HRESULT v17; // eax
  int v18; // eax
  int v19; // eax
  int v20; // eax
  struct DCDocument *v21; // rcx
  unsigned int v22; // edi
  int IsAllowed; // eax
  struct DeclaredConfigurationScopeData *v24; // rcx
  int v25; // eax
  __int64 v26; // rsi
  __int64 i; // r14
  const unsigned __int16 *v28; // rdx
  __int64 v29; // r8
  _QWORD *v30; // rcx
  __int64 v31; // rax
  int pwszBaseUri; // [rsp+20h] [rbp-79h]
  int pwszBaseUria; // [rsp+20h] [rbp-79h]
  void *ppvObject; // [rsp+30h] [rbp-69h] BYREF
  IXmlReaderInput *ppInput; // [rsp+38h] [rbp-61h] BYREF
  IUnknown *pInputStream; // [rsp+40h] [rbp-59h] BYREF
  _QWORD v37[4]; // [rsp+48h] [rbp-51h] BYREF
  char v38; // [rsp+68h] [rbp-31h]
  UINT cbInit[2]; // [rsp+70h] [rbp-29h] BYREF
  _QWORD v40[3]; // [rsp+80h] [rbp-19h] BYREF
  _BYTE v41[88]; // [rsp+98h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]
  struct DeclaredConfigurationScopeData *v43; // [rsp+108h] [rbp+6Fh] BYREF
  int v44; // [rsp+118h] [rbp+7Fh] BYREF

  v43 = a2;
  *(_QWORD *)cbInit = 0;
  pInputStream = 0;
  v44 = 0;
  Logger = CDeclaredConfigurationLogger::GetLogger();
  CDeclaredConfigurationLogger::LogDeclaredConfigurationBeginDCParsingFromCSPEvent(
    Logger,
    a1,
    *(const unsigned __int16 **)v43,
    *((const unsigned __int16 **)v43 + 1),
    *((_DWORD *)v43 + 4),
    *((_DWORD *)v43 + 5));
  v37[0] = a4;
  v37[1] = &v43;
  v37[2] = cbInit;
  v37[3] = &v44;
  v38 = 1;
  v8 = StringCchLengthW(a3, 0x7FFFFFFFu, (unsigned __int64 *)&pInputStream);
  v10 = v8;
  v44 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x11C8,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcparse.cpp",
      (const char *)(unsigned int)v8,
      pwszBaseUri);
    v38 = 0;
    lambda_6a0e824aa1f74373265ae2075a41d9f0_::operator()(v37);
    return v10;
  }
  v12 = ULongLongMult((unsigned __int64)pInputStream, v9, (unsigned __int64 *)cbInit);
  v10 = v12;
  v44 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x11CA,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcparse.cpp",
      (const char *)(unsigned int)v12,
      pwszBaseUri);
    v38 = 0;
    lambda_6a0e824aa1f74373265ae2075a41d9f0_::operator()(v37);
    return v10;
  }
  pInputStream = 0;
  v13 = SHCreateMemStream((const BYTE *)a3, cbInit[0]);
  Microsoft::WRL::ComPtr<IStream>::Attach(&pInputStream, v13);
  v14 = pInputStream;
  if ( !pInputStream )
  {
    v10 = -2147467259;
    v44 = -2147467259;
    v38 = 0;
    lambda_6a0e824aa1f74373265ae2075a41d9f0_::operator()(v37);
    return v10;
  }
  ppInput = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppInput);
  v15 = CreateXmlReaderInputWithEncodingName(v14, 0, L"UTF-16", 0, 0, &ppInput);
  v16 = v15;
  v44 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x11D9,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcparse.cpp",
      (const char *)(unsigned int)v15,
      pwszBaseUria);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppInput);
    if ( v14 )
      ((void (__fastcall *)(IUnknown *))v14->lpVtbl->Release)(v14);
    v38 = 0;
    lambda_6a0e824aa1f74373265ae2075a41d9f0_::operator()(v37);
    return v16;
  }
  ppvObject = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppvObject);
  v17 = CreateXmlReader(&GUID_7279fc81_709d_4095_b63d_69fe4b0d9030, &ppvObject, 0);
  v16 = v17;
  v44 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x11DD,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcparse.cpp",
      (const char *)(unsigned int)v17,
      pwszBaseUria);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppvObject);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppInput);
    if ( v14 )
      ((void (__fastcall *)(IUnknown *))v14->lpVtbl->Release)(v14);
LABEL_43:
    v38 = 0;
    lambda_6a0e824aa1f74373265ae2075a41d9f0_::operator()(v37);
    return v16;
  }
  v18 = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)ppvObject + 40LL))(ppvObject, 4);
  v16 = v18;
  v44 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x11DF,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcparse.cpp",
      (const char *)(unsigned int)v18,
      pwszBaseUria);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppvObject);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppInput);
    if ( v14 )
      ((void (__fastcall *)(IUnknown *))v14->lpVtbl->Release)(v14);
    goto LABEL_43;
  }
  v19 = (*(__int64 (__fastcall **)(void *, IXmlReaderInput *))(*(_QWORD *)ppvObject + 24LL))(ppvObject, ppInput);
  v16 = v19;
  v44 = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x11E1,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcparse.cpp",
      (const char *)(unsigned int)v19,
      pwszBaseUria);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppvObject);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppInput);
    if ( v14 )
      ((void (__fastcall *)(IUnknown *))v14->lpVtbl->Release)(v14);
    goto LABEL_43;
  }
  ParseDCCSPPayload::ParseDCCSPPayload((ParseDCCSPPayload *)v40, (struct IXmlReader *)ppvObject, a4);
  v20 = XmlParseFactory::ParseXmlNodesTypes((XmlParseFactory *)v40);
  v16 = v20;
  v44 = v20;
  if ( v20 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x11E6,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcparse.cpp",
      (const char *)(unsigned int)v20,
      pwszBaseUria);
    v40[0] = &XmlParseFactory::`vftable';
    std::deque<std::wstring>::~deque<std::wstring>(v41);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppvObject);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppInput);
    if ( v14 )
      ((void (__fastcall *)(IUnknown *))v14->lpVtbl->Release)(v14);
    goto LABEL_43;
  }
  if ( *((_QWORD *)a4 + 3) <= 7u )
    v21 = a4;
  else
    v21 = *(struct DCDocument **)a4;
  if ( (unsigned int)_o__wcsicmp(v21, a1) )
  {
    v22 = -2147418113;
    v44 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x11EB,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcparse.cpp",
      (const char *)0x8000FFFFLL,
      pwszBaseUria);
    v40[0] = &XmlParseFactory::`vftable';
    std::deque<std::wstring>::~deque<std::wstring>(v41);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppvObject);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppInput);
    if ( v14 )
      ((void (__fastcall *)(IUnknown *))v14->lpVtbl->Release)(v14);
  }
  else
  {
    IsAllowed = ValidateConfigurationProviderIsAllowed(v43, a4);
    v16 = IsAllowed;
    v44 = IsAllowed;
    if ( IsAllowed < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x11F1,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcparse.cpp",
        (const char *)(unsigned int)IsAllowed,
        pwszBaseUria);
      v40[0] = &XmlParseFactory::`vftable';
      std::deque<std::wstring>::~deque<std::wstring>(v41);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppvObject);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppInput);
      if ( v14 )
        ((void (__fastcall *)(IUnknown *))v14->lpVtbl->Release)(v14);
      goto LABEL_43;
    }
    v25 = ValidateOSDefinedScenarioCapabilities(v24, a4);
    v16 = v25;
    v44 = v25;
    if ( v25 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x11F7,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcparse.cpp",
        (const char *)(unsigned int)v25,
        pwszBaseUria);
      v40[0] = &XmlParseFactory::`vftable';
      std::deque<std::wstring>::~deque<std::wstring>(v41);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppvObject);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppInput);
      if ( v14 )
        ((void (__fastcall *)(IUnknown *))v14->lpVtbl->Release)(v14);
      goto LABEL_43;
    }
    v26 = *((_QWORD *)a4 + 29);
    for ( i = *((_QWORD *)a4 + 30); v26 != i; v26 += 16 )
    {
      v28 = *(const unsigned __int16 **)v43;
      v29 = -1;
      do
        ++v29;
      while ( v28[v29] );
      std::wstring::_Assign<unsigned short>((char **)(*(_QWORD *)v26 + 8LL), v28, (char *)v29);
    }
    v30 = (_QWORD *)*((_QWORD *)a4 + 26);
    if ( (__int64)(*((_QWORD *)a4 + 27) - (_QWORD)v30) >> 4 )
    {
      v31 = _RTDynamicCast_0(
              *v30,
              0,
              &DCProviderOrchestration `RTTI Type Descriptor',
              &DCNativeProviderOrchestration `RTTI Type Descriptor',
              0);
      if ( v31 )
      {
        if ( (__int64)(*((_QWORD *)a4 + 21) - *((_QWORD *)a4 + 20)) >> 4 )
          *(_WORD *)(v31 + 176) = 1;
      }
    }
    v22 = v44;
    v40[0] = &XmlParseFactory::`vftable';
    std::deque<std::wstring>::~deque<std::wstring>(v41);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppvObject);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppInput);
    if ( v14 )
      ((void (__fastcall *)(IUnknown *))v14->lpVtbl->Release)(v14);
  }
  v38 = 0;
  lambda_6a0e824aa1f74373265ae2075a41d9f0_::operator()(v37);
  return v22;
}

```

## disassembly

```asm
0x180033230  mov     [rsp-8+arg_0], rbx
0x180033235  mov     [rsp-8+arg_8], rdx
0x18003323a  push    rbp
0x18003323b  push    rsi
0x18003323c  push    rdi
0x18003323d  push    r14
0x18003323f  push    r15
0x180033241  lea     rbp, [rsp-37h]
0x180033246  sub     rsp, 0D0h
0x18003324d  mov     rdi, r9
0x180033250  mov     rsi, r8
0x180033253  mov     r14, rcx
0x180033256  xor     r15d, r15d
0x180033259  mov     qword ptr [rbp+57h+cbInit], r15
0x18003325d  mov     [rbp+57h+pInputStream], r15
0x180033261  mov     [rbp+57h+arg_18], r15d
0x180033265  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x18003326a  mov     r8, [rbp+57h+arg_8]
0x18003326e  mov     edx, [r8+14h]
0x180033272  mov     dword ptr [rsp+0F0h+ppInput], edx; unsigned int
0x180033276  mov     edx, [r8+10h]
0x18003327a  mov     dword ptr [rsp+0F0h+pwszBaseUri], edx; int
0x18003327e  mov     r9, [r8+8]; unsigned __int16 *
0x180033282  mov     r8, [r8]; unsigned __int16 *
0x180033285  mov     rdx, r14; unsigned __int16 *
0x180033288  mov     rcx, rax; this
0x18003328b  call    ?LogDeclaredConfigurationBeginDCParsingFromCSPEvent@CDeclaredConfigurationLogger@@QEAAXPEBG00KK@Z; CDeclaredConfigurationLogger::LogDeclaredConfigurationBeginDCParsingFromCSPEvent(ushort const *,ushort const *,ushort const *,ulong,ulong)
0x180033290  mov     [rbp+57h+var_A8], rdi
0x180033294  lea     rax, [rbp+57h+arg_8]
0x180033298  mov     [rbp+57h+var_A0], rax
0x18003329c  lea     rax, [rbp+57h+cbInit]
0x1800332a0  mov     [rbp+57h+var_98], rax
0x1800332a4  lea     rax, [rbp+57h+arg_18]
0x1800332a8  mov     [rbp+57h+var_90], rax
0x1800332ac  mov     [rbp+57h+var_88], 1
0x1800332b0  lea     r8, [rbp+57h+pInputStream]; unsigned __int64 *
0x1800332b4  mov     edx, 7FFFFFFFh; unsigned __int64
0x1800332b9  mov     rcx, rsi; unsigned __int16 *
0x1800332bc  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800332c1  mov     ebx, eax
0x1800332c3  mov     [rbp+57h+arg_18], eax
0x1800332c6  test    eax, eax
0x1800332c8  jns     short loc_1800332F8
0x1800332ca  mov     rcx, [rbp+5Fh]; this
0x1800332ce  mov     r9d, eax; char *
0x1800332d1  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800332d8  mov     edx, 11C8h; void *
0x1800332dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800332e2  nop
0x1800332e3  mov     [rbp+57h+var_88], r15b
0x1800332e7  lea     rcx, [rbp+57h+var_A8]
0x1800332eb  call    _lambda_6a0e824aa1f74373265ae2075a41d9f0___operator__
0x1800332f0  nop
0x1800332f1  mov     eax, ebx
0x1800332f3  jmp     loc_180033862
0x1800332f8  lea     r8, [rbp+57h+cbInit]; unsigned __int64 *
0x1800332fc  mov     rcx, [rbp+57h+pInputStream]; unsigned __int64
0x180033300  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180033305  mov     ebx, eax
0x180033307  mov     [rbp+57h+arg_18], eax
0x18003330a  test    eax, eax
0x18003330c  jns     short loc_180033337
0x18003330e  mov     rcx, [rbp+5Fh]; this
0x180033312  mov     r9d, eax; char *
0x180033315  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x18003331c  mov     edx, 11CAh; void *
0x180033321  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033326  nop
0x180033327  mov     [rbp+57h+var_88], r15b
0x18003332b  lea     rcx, [rbp+57h+var_A8]
0x18003332f  call    _lambda_6a0e824aa1f74373265ae2075a41d9f0___operator__
0x180033334  nop
0x180033335  jmp     short loc_1800332F1
0x180033337  mov     [rbp+57h+pInputStream], r15
0x18003333b  mov     edx, [rbp+57h+cbInit]; cbInit
0x18003333e  mov     rcx, rsi; pInit
0x180033341  call    cs:__imp_SHCreateMemStream
0x180033347  mov     rdx, rax
0x18003334a  lea     rcx, [rbp+57h+pInputStream]
0x18003334e  call    ?Attach@?$ComPtr@UIStream@@@WRL@Microsoft@@QEAAXPEAUIStream@@@Z; Microsoft::WRL::ComPtr<IStream>::Attach(IStream *)
0x180033353  mov     rbx, [rbp+57h+pInputStream]
0x180033357  test    rbx, rbx
0x18003335a  jnz     short loc_180033377
0x18003335c  mov     ebx, 80004005h
0x180033361  mov     [rbp+57h+arg_18], ebx
0x180033364  mov     [rbp+57h+var_88], r15b
0x180033368  lea     rcx, [rbp+57h+var_A8]
0x18003336c  call    _lambda_6a0e824aa1f74373265ae2075a41d9f0___operator__
0x180033371  nop
0x180033372  jmp     loc_1800332F1
0x180033377  mov     [rbp+57h+var_B8], r15
0x18003337b  lea     rcx, [rbp+57h+var_B8]
0x18003337f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180033384  lea     rax, [rbp+57h+var_B8]
0x180033388  mov     [rsp+0F0h+ppInput], rax; ppInput
0x18003338d  mov     [rsp+0F0h+pwszBaseUri], r15; int
0x180033392  xor     r9d, r9d; fEncodingHint
0x180033395  lea     r8, pwszEncodingName; "UTF-16"
0x18003339c  xor     edx, edx; pMalloc
0x18003339e  mov     rcx, rbx; pInputStream
0x1800333a1  call    cs:__imp_CreateXmlReaderInputWithEncodingName
0x1800333a7  mov     esi, eax
0x1800333a9  mov     [rbp+57h+arg_18], eax
0x1800333ac  test    eax, eax
0x1800333ae  jns     short loc_1800333FD
0x1800333b0  mov     rcx, [rbp+5Fh]; this
0x1800333b4  mov     r9d, eax; char *
0x1800333b7  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800333be  mov     edx, 11D9h; void *
0x1800333c3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800333c8  nop
0x1800333c9  lea     rcx, [rbp+57h+var_B8]
0x1800333cd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800333d2  nop
0x1800333d3  test    rbx, rbx
0x1800333d6  jz      short loc_1800333E8
0x1800333d8  mov     rax, [rbx]
0x1800333db  mov     rcx, rbx
0x1800333de  mov     rax, [rax+10h]
0x1800333e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800333e7  nop
0x1800333e8  mov     [rbp+57h+var_88], r15b
0x1800333ec  lea     rcx, [rbp+57h+var_A8]
0x1800333f0  call    _lambda_6a0e824aa1f74373265ae2075a41d9f0___operator__
0x1800333f5  nop
0x1800333f6  mov     eax, esi
0x1800333f8  jmp     loc_180033862
0x1800333fd  mov     [rbp+57h+ppvObject], r15
0x180033401  lea     rcx, [rbp+57h+ppvObject]
0x180033405  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003340a  xor     r8d, r8d; pMalloc
0x18003340d  lea     rdx, [rbp+57h+ppvObject]; ppvObject
0x180033411  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030; riid
0x180033418  call    cs:__imp_CreateXmlReader
0x18003341e  mov     esi, eax
0x180033420  mov     [rbp+57h+arg_18], eax
0x180033423  test    eax, eax
0x180033425  jns     short loc_18003347C
0x180033427  mov     rcx, [rbp+5Fh]; this
0x18003342b  mov     r9d, eax; char *
0x18003342e  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x180033435  mov     edx, 11DDh; void *
0x18003343a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003343f  nop
0x180033440  lea     rcx, [rbp+57h+ppvObject]
0x180033444  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180033449  nop
0x18003344a  lea     rcx, [rbp+57h+var_B8]
0x18003344e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180033453  nop
0x180033454  test    rbx, rbx
0x180033457  jz      short loc_180033469
0x180033459  mov     rax, [rbx]
0x18003345c  mov     rcx, rbx
0x18003345f  mov     rax, [rax+10h]
0x180033463  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033468  nop
0x180033469  mov     [rbp+57h+var_88], r15b
0x18003346d  lea     rcx, [rbp+57h+var_A8]
0x180033471  call    _lambda_6a0e824aa1f74373265ae2075a41d9f0___operator__
0x180033476  nop
0x180033477  jmp     loc_1800333F6
0x18003347c  mov     rcx, [rbp+57h+ppvObject]
0x180033480  mov     rax, [rcx]
0x180033483  xor     r8d, r8d
0x180033486  lea     edx, [r8+4]
0x18003348a  mov     rax, [rax+28h]
0x18003348e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033493  mov     esi, eax
0x180033495  mov     [rbp+57h+arg_18], eax
0x180033498  test    eax, eax
0x18003349a  jns     short loc_1800334F1
0x18003349c  mov     rcx, [rbp+5Fh]; this
0x1800334a0  mov     r9d, eax; char *
0x1800334a3  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800334aa  mov     edx, 11DFh; void *
0x1800334af  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800334b4  nop
0x1800334b5  lea     rcx, [rbp+57h+ppvObject]
0x1800334b9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800334be  nop
0x1800334bf  lea     rcx, [rbp+57h+var_B8]
0x1800334c3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800334c8  nop
0x1800334c9  test    rbx, rbx
0x1800334cc  jz      short loc_1800334DE
0x1800334ce  mov     rax, [rbx]
0x1800334d1  mov     rcx, rbx
0x1800334d4  mov     rax, [rax+10h]
0x1800334d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800334dd  nop
0x1800334de  mov     [rbp+57h+var_88], r15b
0x1800334e2  lea     rcx, [rbp+57h+var_A8]
0x1800334e6  call    _lambda_6a0e824aa1f74373265ae2075a41d9f0___operator__
0x1800334eb  nop
0x1800334ec  jmp     loc_1800333F6
0x1800334f1  mov     rcx, [rbp+57h+ppvObject]
0x1800334f5  mov     rax, [rcx]
0x1800334f8  mov     rdx, [rbp+57h+var_B8]
0x1800334fc  mov     rax, [rax+18h]
0x180033500  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033505  mov     esi, eax
0x180033507  mov     [rbp+57h+arg_18], eax
0x18003350a  test    eax, eax
0x18003350c  jns     short loc_180033563
0x18003350e  mov     rcx, [rbp+5Fh]; this
0x180033512  mov     r9d, eax; char *
0x180033515  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x18003351c  mov     edx, 11E1h; void *
0x180033521  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033526  nop
0x180033527  lea     rcx, [rbp+57h+ppvObject]
0x18003352b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180033530  nop
0x180033531  lea     rcx, [rbp+57h+var_B8]
0x180033535  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003353a  nop
0x18003353b  test    rbx, rbx
0x18003353e  jz      short loc_180033550
0x180033540  mov     rax, [rbx]
0x180033543  mov     rcx, rbx
0x180033546  mov     rax, [rax+10h]
0x18003354a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003354f  nop
0x180033550  mov     [rbp+57h+var_88], r15b
0x180033554  lea     rcx, [rbp+57h+var_A8]
0x180033558  call    _lambda_6a0e824aa1f74373265ae2075a41d9f0___operator__
0x18003355d  nop
0x18003355e  jmp     loc_1800333F6
0x180033563  mov     r8, rdi; struct DCDocument *
0x180033566  mov     rdx, [rbp+57h+ppvObject]; struct IXmlReader *
0x18003356a  lea     rcx, [rbp+57h+var_70]; this
0x18003356e  call    ??0ParseDCCSPPayload@@QEAA@PEAUIXmlReader@@AEAVDCDocument@@@Z; ParseDCCSPPayload::ParseDCCSPPayload(IXmlReader *,DCDocument &)
0x180033573  nop
0x180033574  lea     rcx, [rbp+57h+var_70]; this
0x180033578  call    ?ParseXmlNodesTypes@XmlParseFactory@@QEAAJXZ; XmlParseFactory::ParseXmlNodesTypes(void)
0x18003357d  mov     esi, eax
0x18003357f  mov     [rbp+57h+arg_18], eax
0x180033582  test    eax, eax
0x180033584  jns     short loc_1800335F0
0x180033586  mov     rcx, [rbp+5Fh]; this
0x18003358a  mov     r9d, eax; char *
0x18003358d  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x180033594  mov     edx, 11E6h; void *
0x180033599  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003359e  nop
0x18003359f  lea     rcx, ??_7XmlParseFactory@@6B@; const XmlParseFactory::`vftable'
0x1800335a6  mov     [rbp+57h+var_70], rcx
0x1800335aa  lea     rcx, [rbp+57h+var_58]
0x1800335ae  call    ??1?$deque@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::deque<std::wstring>::~deque<std::wstring>(void)
0x1800335b3  nop
0x1800335b4  lea     rcx, [rbp+57h+ppvObject]
0x1800335b8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800335bd  nop
0x1800335be  lea     rcx, [rbp+57h+var_B8]
0x1800335c2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800335c7  nop
0x1800335c8  test    rbx, rbx
0x1800335cb  jz      short loc_1800335DD
0x1800335cd  mov     rax, [rbx]
0x1800335d0  mov     rcx, rbx
0x1800335d3  mov     rax, [rax+10h]
0x1800335d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800335dc  nop
0x1800335dd  mov     [rbp+57h+var_88], r15b
0x1800335e1  lea     rcx, [rbp+57h+var_A8]
0x1800335e5  call    _lambda_6a0e824aa1f74373265ae2075a41d9f0___operator__
0x1800335ea  nop
0x1800335eb  jmp     loc_1800333F6
0x1800335f0  cmp     qword ptr [rdi+18h], 7
0x1800335f5  jbe     short loc_1800335FC
0x1800335f7  mov     rcx, [rdi]
0x1800335fa  jmp     short loc_1800335FF
0x1800335fc  mov     rcx, rdi
0x1800335ff  mov     rdx, r14
0x180033602  call    cs:__imp__o__wcsicmp
0x180033608  test    eax, eax
0x18003360a  jz      short loc_18003367E
0x18003360c  mov     edi, 8000FFFFh
0x180033611  mov     [rbp+57h+arg_18], edi
0x180033614  mov     rcx, [rbp+5Fh]; this
0x180033618  mov     r9d, edi; char *
0x18003361b  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x180033622  mov     edx, 11EBh; void *
0x180033627  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003362c  nop
0x18003362d  lea     rcx, ??_7XmlParseFactory@@6B@; const XmlParseFactory::`vftable'
0x180033634  mov     [rbp+57h+var_70], rcx
0x180033638  lea     rcx, [rbp+57h+var_58]
0x18003363c  call    ??1?$deque@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::deque<std::wstring>::~deque<std::wstring>(void)
0x180033641  nop
0x180033642  lea     rcx, [rbp+57h+ppvObject]
0x180033646  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003364b  nop
0x18003364c  lea     rcx, [rbp+57h+var_B8]
0x180033650  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180033655  nop
0x180033656  test    rbx, rbx
0x180033659  jz      short loc_18003366B
0x18003365b  mov     rax, [rbx]
  ... truncated ...
```
