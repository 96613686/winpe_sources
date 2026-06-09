# Appx::Packaging::ContentGroupMap::ContentGroupMapReaderBase::ValidateAndInitializeSchema(IStream *,uint,XmlNamespaceAlias *)

- ea: `0x18006b8a4`
- end: `0x18006bc9f`
- name: `?ValidateAndInitializeSchema@ContentGroupMapReaderBase@ContentGroupMap@Packaging@Appx@@IEAAJPEAUIStream@@IPEAUXmlNamespaceAlias@@@Z`
- size: `1019`
- prototype: `int(Appx::Packaging::ContentGroupMap::ContentGroupMapReaderBase *__hidden this, struct IStream *, unsigned int, struct XmlNamespaceAlias *)`
- caller_count: `2`
- callee_count: `16`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800eb11c`
- `0x1800eb64c`

## callees

- `0x1800029e4`
- `0x180005eb8`
- `0x180009224`
- `0x180009eb8`
- `0x18000b254`
- `0x1800133fc`
- `0x180022b50`
- `0x180024c74`
- `0x180028dd0`
- `0x18004d290`
- `0x18006b8a4`
- `0x18006bca8`
- `0x18006bee8`
- `0x180071f50`
- `0x1800e56cc`
- `0x180106010`

## import_xrefs

- `OpcServices!__imp_AppxPreprocessXml` at `0x18006b9b7`
- `OpcServices!__imp_AppxPreprocessXml` at `0x18006b9b7`
- `OpcServices!__imp_GetCloneableStream` at `0x18006b8f8`
- `OpcServices!__imp_GetCloneableStream` at `0x18006b8f8`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18006b95e`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18006b95e`

## string_xrefs

- `0x18006b913`: `onecore\printscan\appxpackaging\streammap\src\contentgroupmapreaderbase.cpp`
- `0x18006b9d1`: `onecore\printscan\appxpackaging\streammap\src\contentgroupmapreaderbase.cpp`
- `0x18006ba1c`: `onecore\printscan\appxpackaging\streammap\src\contentgroupmapreaderbase.cpp`
- `0x18006bae6`: `onecore\printscan\appxpackaging\streammap\src\contentgroupmapreaderbase.cpp`
- `0x18006bb94`: `onecore\printscan\appxpackaging\streammap\src\contentgroupmapreaderbase.cpp`
- `0x18006bc33`: `onecore\printscan\appxpackaging\streammap\src\contentgroupmapreaderbase.cpp`
- `0x18006bc58`: `onecore\printscan\appxpackaging\streammap\src\contentgroupmapreaderbase.cpp`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::ContentGroupMap::ContentGroupMapReaderBase::ValidateAndInitializeSchema(
        struct IXMLDOMDocument2 **this,
        struct IStream *a2,
        unsigned __int64 a3,
        struct XmlNamespaceAlias *a4)
{
  int CloneableStream; // eax
  unsigned int v8; // ebx
  __int64 v9; // rdx
  HRESULT v10; // eax
  unsigned __int64 v11; // r9
  __int64 v12; // rdx
  int v13; // eax
  unsigned __int64 v14; // r8
  unsigned int v15; // edi
  int v16; // edx
  int v17; // eax
  unsigned __int64 v18; // r8
  int v19; // eax
  int XmlDocument; // eax
  __int64 v21; // rdx
  __int64 v22; // rax
  int v23; // eax
  struct IXMLDOMDocument2 *v24; // rbx
  int v25; // r15d
  __int64 v26; // rdx
  int *v27; // r8
  int *v28; // r9
  int v30; // eax
  int *v31; // [rsp+20h] [rbp-69h]
  LPSTREAM ppstm; // [rsp+40h] [rbp-49h] BYREF
  struct IXMLDOMDocument2 *v33; // [rsp+48h] [rbp-41h] BYREF
  int v34[2]; // [rsp+50h] [rbp-39h] BYREF
  __int64 v35; // [rsp+58h] [rbp-31h] BYREF
  int v36; // [rsp+60h] [rbp-29h]
  int v37; // [rsp+64h] [rbp-25h]
  struct IXMLDOMDocument2 *v38; // [rsp+68h] [rbp-21h] BYREF
  _QWORD v39[4]; // [rsp+70h] [rbp-19h] BYREF
  __int64 v40[10]; // [rsp+90h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]
  int v42; // [rsp+100h] [rbp+77h] BYREF

  v42 = a3;
  v35 = 0;
  CloneableStream = Appx::Packaging::SetStreamPosition(a2, 0, a3);
  v8 = CloneableStream;
  if ( CloneableStream >= 0 )
  {
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v35);
    CloneableStream = GetCloneableStream(a2, &v35);
    v8 = CloneableStream;
    if ( CloneableStream < 0 )
    {
      v9 = 99;
      goto LABEL_5;
    }
    Microsoft::WRL::ComPtr<Appx::Packaging::Consumption::AppxEncryptedFile>::operator=(this + 1, &v35);
    ppstm = 0;
    v33 = 0;
    *(_QWORD *)v34 = 0;
    v37 = 0;
    v36 = 0;
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&ppstm);
    v10 = CreateStreamOnHGlobal(0, 1, &ppstm);
    v8 = v10;
    if ( v10 < 0 )
    {
      v11 = (unsigned int)v10;
      v12 = 107;
LABEL_40:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v12,
        (unsigned int)"onecore\\printscan\\appxpackaging\\streammap\\src\\contentgroupmapreaderbase.cpp",
        (const char *)v11,
        (int)v31);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v34);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v33);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&ppstm);
      goto LABEL_41;
    }
    v40[0] = *((_QWORD *)a4 + 1);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      v34,
      0);
    v31 = v34;
    v13 = AppxPreprocessXml(a2, ppstm, v40, 1);
    v15 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x7B,
        (unsigned int)"onecore\\printscan\\appxpackaging\\streammap\\src\\contentgroupmapreaderbase.cpp",
        (const char *)(unsigned int)v13,
        (int)v34);
      if ( v15 == -2142175166 )
      {
        v12 = 127;
      }
      else
      {
        if ( !Appx::Packaging::Xml::IsIXmlParseError((Appx::Packaging::Xml *)v15, v16)
          && (v15 & 0x1FFF0000) != 0x510000
          && v15 != -2147467259 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x87,
            (unsigned int)"onecore\\printscan\\appxpackaging\\streammap\\src\\contentgroupmapreaderbase.cpp",
            (const char *)v15,
            (int)v31);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v34);
          Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v33);
          Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&ppstm);
          v8 = v15;
          goto LABEL_41;
        }
        v12 = 131;
      }
      goto LABEL_38;
    }
    v17 = Appx::Packaging::SetStreamPosition(a2, 0, v14);
    v8 = v17;
    if ( v17 < 0 )
    {
      v11 = (unsigned int)v17;
      v12 = 139;
      goto LABEL_40;
    }
    v19 = Appx::Packaging::SetStreamPosition(ppstm, 0, v18);
    v8 = v19;
    if ( v19 < 0 )
    {
      v11 = (unsigned int)v19;
      v12 = 140;
      goto LABEL_40;
    }
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v33);
    XmlDocument = Appx::Packaging::XmlValidationHelper::CreateXmlDocument((LPVOID *)&v33);
    v8 = XmlDocument;
    if ( XmlDocument < 0 )
    {
      v11 = (unsigned int)XmlDocument;
      v12 = 143;
      goto LABEL_40;
    }
    if ( !this[7] )
    {
      v22 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 **))(*this)->lpVtbl)(this);
      v23 = Common::Array<XmlSchemaInfo const,Common::ContainerOperations<XmlSchemaInfo const,XmlSchemaInfo const>,Common::NoKey,Common::ContainerOperations<Common::NoKey,XmlSchemaInfo const>,Common::ArrayOperations<XmlSchemaInfo const,Common::NoKey>>::Add(
              this + 5,
              v22);
      v8 = v23;
      if ( v23 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xBB,
          (unsigned int)"onecore\\printscan\\appxpackaging\\streammap\\src\\contentgroupmapreaderbase.cpp",
          (const char *)(unsigned int)v23,
          (int)v34);
        v12 = 145;
LABEL_39:
        v11 = v8;
        goto LABEL_40;
      }
    }
    v24 = v33;
    v25 = Appx::Packaging::XmlValidationHelper::SetSchemas(this + 5, v21, v33);
    if ( v25 >= 0 )
    {
      v25 = Appx::Packaging::XmlValidationHelper::SetSelectionNamespaces(v24, a4, 1u);
      if ( v25 >= 0 )
      {
        LOWORD(v42) = 0;
        v39[2] = 0;
        v39[0] = 13;
        v39[1] = ppstm;
        v25 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, _QWORD *, int *))v24->lpVtbl->load)(v24, v39, &v42);
        if ( v25 >= 0 )
        {
          if ( v15 != 1 && (_WORD)v42 )
          {
            v33 = 0;
            v38 = v24;
            Microsoft::WRL::ComPtr<IXMLDOMNodeList>::InternalAddRef(&v38);
            v38 = this[2];
            this[2] = v24;
            Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v38);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v34);
            Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v33);
            Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&ppstm);
            Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v35);
            return 0;
          }
          v30 = Appx::Packaging::XmlValidationHelper::LogCGMParseError(a2, v24, v27, v28);
          if ( v30 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0xA5,
              (unsigned int)"onecore\\printscan\\appxpackaging\\streammap\\src\\contentgroupmapreaderbase.cpp",
              (const char *)(unsigned int)v30,
              (int)v34);
          v12 = 168;
LABEL_38:
          v8 = -2146958837;
          goto LABEL_39;
        }
        v26 = 159;
      }
      else
      {
        v26 = 150;
      }
    }
    else
    {
      v26 = 146;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v26,
      (unsigned int)"onecore\\printscan\\appxpackaging\\streammap\\src\\contentgroupmapreaderbase.cpp",
      (const char *)(unsigned int)v25,
      (int)v34);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v34);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v33);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&ppstm);
    v8 = v25;
    goto LABEL_41;
  }
  v9 = 98;
LABEL_5:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v9,
    (unsigned int)"onecore\\printscan\\appxpackaging\\streammap\\src\\contentgroupmapreaderbase.cpp",
    (const char *)(unsigned int)CloneableStream,
    (int)v31);
LABEL_41:
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v35);
  return v8;
}

```

## disassembly

```asm
0x18006b8a4  mov     [rsp-8+arg_10], r8d
0x18006b8a9  push    rbp
0x18006b8aa  push    rbx
0x18006b8ab  push    rsi
0x18006b8ac  push    rdi
0x18006b8ad  push    r12
0x18006b8af  push    r13
0x18006b8b1  push    r14
0x18006b8b3  push    r15
0x18006b8b5  lea     rbp, [rsp-1Fh]
0x18006b8ba  sub     rsp, 0A8h
0x18006b8c1  mov     r14, rdx
0x18006b8c4  mov     rsi, rcx
0x18006b8c7  xor     r12d, r12d
0x18006b8ca  mov     rcx, r14; this
0x18006b8cd  xor     edx, edx; struct IStream *
0x18006b8cf  mov     [rbp+57h+var_88], r12
0x18006b8d3  mov     r13, r9
0x18006b8d6  call    ?SetStreamPosition@Packaging@Appx@@YAJPEAUIStream@@_K@Z; Appx::Packaging::SetStreamPosition(IStream *,unsigned __int64)
0x18006b8db  mov     ebx, eax
0x18006b8dd  test    eax, eax
0x18006b8df  jns     short loc_18006B8E8
0x18006b8e1  lea     edx, [r12+62h]
0x18006b8e6  jmp     short loc_18006B90F
0x18006b8e8  lea     rcx, [rbp+57h+var_88]
0x18006b8ec  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18006b8f1  lea     rdx, [rbp+57h+var_88]
0x18006b8f5  mov     rcx, r14
0x18006b8f8  call    cs:__imp_GetCloneableStream
0x18006b8ff  nop     dword ptr [rax+rax+00h]
0x18006b904  mov     ebx, eax
0x18006b906  test    eax, eax
0x18006b908  jns     short loc_18006B927
0x18006b90a  mov     edx, 63h ; 'c'; void *
0x18006b90f  mov     rcx, [rbp+5Fh]; this
0x18006b913  lea     r8, aOnecorePrintsc_88; "onecore\\printscan\\appxpackaging\\stre"...
0x18006b91a  mov     r9d, eax; char *
0x18006b91d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006b922  jmp     loc_18006BC7F
0x18006b927  lea     rcx, [rsi+8]
0x18006b92b  lea     rdx, [rbp+57h+var_88]
0x18006b92f  call    ??4?$ComPtr@VAppxEncryptedFile@Consumption@Packaging@Appx@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<Appx::Packaging::Consumption::AppxEncryptedFile>::operator=(Microsoft::WRL::ComPtr<Appx::Packaging::Consumption::AppxEncryptedFile> const &)
0x18006b934  lea     rcx, [rbp+57h+ppstm]
0x18006b938  mov     [rbp+57h+ppstm], r12
0x18006b93c  mov     [rbp+57h+var_98], r12
0x18006b940  mov     qword ptr [rbp+57h+var_90], r12
0x18006b944  mov     [rbp+57h+var_7C], r12d
0x18006b948  mov     [rbp+57h+var_80], r12d
0x18006b94c  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18006b951  mov     edi, 1
0x18006b956  lea     r8, [rbp+57h+ppstm]; ppstm
0x18006b95a  mov     edx, edi; fDeleteOnRelease
0x18006b95c  xor     ecx, ecx; hGlobal
0x18006b95e  call    cs:__imp_CreateStreamOnHGlobal
0x18006b965  nop     dword ptr [rax+rax+00h]
0x18006b96a  mov     ebx, eax
0x18006b96c  test    eax, eax
0x18006b96e  jns     short loc_18006B97B
0x18006b970  mov     r9d, eax
0x18006b973  lea     edx, [rdi+6Ah]
0x18006b976  jmp     loc_18006BC54
0x18006b97b  mov     rax, [r13+8]
0x18006b97f  lea     rcx, [rbp+57h+var_90]
0x18006b983  xor     edx, edx
0x18006b985  mov     [rbp+57h+var_50], rax
0x18006b989  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18006b98e  mov     rdx, [rbp+57h+ppstm]
0x18006b992  lea     rax, [rbp+57h+var_80]
0x18006b996  mov     [rsp+0E0h+var_B0], rax
0x18006b99b  lea     r8, [rbp+57h+var_50]
0x18006b99f  lea     rax, [rbp+57h+var_7C]
0x18006b9a3  mov     r9d, edi
0x18006b9a6  mov     [rsp+0E0h+var_B8], rax
0x18006b9ab  mov     rcx, r14
0x18006b9ae  lea     rax, [rbp+57h+var_90]
0x18006b9b2  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x18006b9b7  call    cs:__imp_AppxPreprocessXml
0x18006b9be  nop     dword ptr [rax+rax+00h]
0x18006b9c3  mov     edi, eax
0x18006b9c5  test    eax, eax
0x18006b9c7  jns     loc_18006BA5C
0x18006b9cd  mov     rcx, [rbp+5Fh]; this
0x18006b9d1  lea     r8, aOnecorePrintsc_88; "onecore\\printscan\\appxpackaging\\stre"...
0x18006b9d8  mov     r9d, eax; char *
0x18006b9db  mov     edx, 7Bh ; '{'; void *
0x18006b9e0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006b9e5  cmp     edi, 80510042h
0x18006b9eb  jnz     short loc_18006B9F7
0x18006b9ed  mov     edx, 7Fh
0x18006b9f2  jmp     loc_18006BC4C
0x18006b9f7  mov     ecx, edi; this
0x18006b9f9  call    ?IsIXmlParseError@Xml@Packaging@Appx@@YA_NJ@Z; Appx::Packaging::Xml::IsIXmlParseError(long)
0x18006b9fe  test    al, al
0x18006ba00  jnz     short loc_18006BA52
0x18006ba02  mov     eax, edi
0x18006ba04  and     eax, 1FFF0000h
0x18006ba09  cmp     eax, 510000h
0x18006ba0e  jz      short loc_18006BA52
0x18006ba10  cmp     edi, 80004005h
0x18006ba16  jz      short loc_18006BA52
0x18006ba18  mov     rcx, [rbp+5Fh]; this
0x18006ba1c  lea     r8, aOnecorePrintsc_88; "onecore\\printscan\\appxpackaging\\stre"...
0x18006ba23  mov     r9d, edi; char *
0x18006ba26  mov     edx, 87h; void *
0x18006ba2b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006ba30  lea     rcx, [rbp+57h+var_90]
0x18006ba34  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18006ba39  lea     rcx, [rbp+57h+var_98]
0x18006ba3d  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18006ba42  lea     rcx, [rbp+57h+ppstm]
0x18006ba46  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18006ba4b  mov     ebx, edi
0x18006ba4d  jmp     loc_18006BC7F
0x18006ba52  mov     edx, 83h
0x18006ba57  jmp     loc_18006BC4C
0x18006ba5c  xor     edx, edx; struct IStream *
0x18006ba5e  mov     rcx, r14; this
0x18006ba61  call    ?SetStreamPosition@Packaging@Appx@@YAJPEAUIStream@@_K@Z; Appx::Packaging::SetStreamPosition(IStream *,unsigned __int64)
0x18006ba66  mov     ebx, eax
0x18006ba68  test    eax, eax
0x18006ba6a  jns     short loc_18006BA79
0x18006ba6c  mov     r9d, eax
0x18006ba6f  mov     edx, 8Bh
0x18006ba74  jmp     loc_18006BC54
0x18006ba79  mov     rcx, [rbp+57h+ppstm]; this
0x18006ba7d  xor     edx, edx; struct IStream *
0x18006ba7f  call    ?SetStreamPosition@Packaging@Appx@@YAJPEAUIStream@@_K@Z; Appx::Packaging::SetStreamPosition(IStream *,unsigned __int64)
0x18006ba84  mov     ebx, eax
0x18006ba86  test    eax, eax
0x18006ba88  jns     short loc_18006BA97
0x18006ba8a  mov     r9d, eax
0x18006ba8d  mov     edx, 8Ch
0x18006ba92  jmp     loc_18006BC54
0x18006ba97  lea     rcx, [rbp+57h+var_98]
0x18006ba9b  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18006baa0  lea     rcx, [rbp+57h+var_98]; struct IXMLDOMDocument2 **
0x18006baa4  call    ?CreateXmlDocument@XmlValidationHelper@Packaging@Appx@@SAJPEAPEAUIXMLDOMDocument2@@@Z; Appx::Packaging::XmlValidationHelper::CreateXmlDocument(IXMLDOMDocument2 * *)
0x18006baa9  mov     ebx, eax
0x18006baab  test    eax, eax
0x18006baad  jns     short loc_18006BABC
0x18006baaf  mov     r9d, eax
0x18006bab2  mov     edx, 8Fh
0x18006bab7  jmp     loc_18006BC54
0x18006babc  cmp     [rsi+38h], r12
0x18006bac0  jnz     short loc_18006BB04
0x18006bac2  mov     rax, [rsi]
0x18006bac5  mov     rcx, rsi
0x18006bac8  mov     rax, [rax]
0x18006bacb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bad0  mov     rdx, rax
0x18006bad3  lea     rcx, [rsi+28h]
0x18006bad7  call    ?Add@?$Array@$$CBUXmlSchemaInfo@@V?$ContainerOperations@$$CBUXmlSchemaInfo@@$$CBU1@@Common@@VNoKey@3@V?$ContainerOperations@VNoKey@Common@@$$CBUXmlSchemaInfo@@@3@V?$ArrayOperations@$$CBUXmlSchemaInfo@@VNoKey@Common@@@3@@Common@@QEAAJPEBUXmlSchemaInfo@@@Z; Common::Array<XmlSchemaInfo const,Common::ContainerOperations<XmlSchemaInfo const,XmlSchemaInfo const>,Common::NoKey,Common::ContainerOperations<Common::NoKey,XmlSchemaInfo const>,Common::ArrayOperations<XmlSchemaInfo const,Common::NoKey>>::Add(XmlSchemaInfo const *)
0x18006badc  mov     ebx, eax
0x18006bade  test    eax, eax
0x18006bae0  jns     short loc_18006BB04
0x18006bae2  mov     rcx, [rbp+5Fh]; this
0x18006bae6  lea     r8, aOnecorePrintsc_88; "onecore\\printscan\\appxpackaging\\stre"...
0x18006baed  mov     r9d, eax; char *
0x18006baf0  mov     edx, 0BBh; void *
0x18006baf5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006bafa  mov     edx, 91h
0x18006baff  jmp     loc_18006BC51
0x18006bb04  mov     rbx, [rbp+57h+var_98]
0x18006bb08  lea     rcx, [rsi+28h]
0x18006bb0c  mov     r8, rbx
0x18006bb0f  call    ?SetSchemas@XmlValidationHelper@Packaging@Appx@@SAJPEAV?$Array@$$CBUXmlSchemaInfo@@V?$ContainerOperations@$$CBUXmlSchemaInfo@@$$CBU1@@Common@@VNoKey@3@V?$ContainerOperations@VNoKey@Common@@$$CBUXmlSchemaInfo@@@3@V?$ArrayOperations@$$CBUXmlSchemaInfo@@VNoKey@Common@@@3@@Common@@PEBGPEAUIXMLDOMDocument2@@@Z; Appx::Packaging::XmlValidationHelper::SetSchemas(Common::Array<XmlSchemaInfo const,Common::ContainerOperations<XmlSchemaInfo const,XmlSchemaInfo const>,Common::NoKey,Common::ContainerOperations<Common::NoKey,XmlSchemaInfo const>,Common::ArrayOperations<XmlSchemaInfo const,Common::NoKey>> *,ushort const *,IXMLDOMDocument2 *)
0x18006bb14  mov     r15d, eax
0x18006bb17  test    eax, eax
0x18006bb19  jns     short loc_18006BB22
0x18006bb1b  mov     edx, 92h
0x18006bb20  jmp     short loc_18006BB90
0x18006bb22  mov     r8d, 1; unsigned int
0x18006bb28  mov     rdx, r13; struct XmlNamespaceAlias *
0x18006bb2b  mov     rcx, rbx; struct IXMLDOMDocument2 *
0x18006bb2e  call    ?SetSelectionNamespaces@XmlValidationHelper@Packaging@Appx@@SAJPEAUIXMLDOMDocument2@@PEAUXmlNamespaceAlias@@K@Z; Appx::Packaging::XmlValidationHelper::SetSelectionNamespaces(IXMLDOMDocument2 *,XmlNamespaceAlias *,ulong)
0x18006bb33  mov     r15d, eax
0x18006bb36  test    eax, eax
0x18006bb38  jns     short loc_18006BB41
0x18006bb3a  mov     edx, 96h
0x18006bb3f  jmp     short loc_18006BB90
0x18006bb41  xor     ecx, ecx
0x18006bb43  mov     word ptr [rbp+57h+arg_10], r12w
0x18006bb48  xorps   xmm0, xmm0
0x18006bb4b  mov     [rbp+57h+var_60], rcx
0x18006bb4f  movups  [rbp+57h+var_70], xmm0
0x18006bb53  lea     r8, [rbp+57h+arg_10]
0x18006bb57  lea     eax, [rcx+0Dh]
0x18006bb5a  mov     rcx, rbx
0x18006bb5d  mov     word ptr [rbp+57h+var_70], ax
0x18006bb61  lea     rdx, [rbp+57h+var_70]
0x18006bb65  mov     rax, [rbp+57h+ppstm]
0x18006bb69  mov     qword ptr [rbp+57h+var_70+8], rax
0x18006bb6d  mov     rax, [rbx]
0x18006bb70  movups  xmm0, [rbp+57h+var_70]
0x18006bb74  mov     rax, [rax+1D0h]
0x18006bb7b  movaps  [rbp+57h+var_70], xmm0
0x18006bb7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bb84  mov     r15d, eax
0x18006bb87  test    eax, eax
0x18006bb89  jns     short loc_18006BBC6
0x18006bb8b  mov     edx, 9Fh; void *
0x18006bb90  mov     rcx, [rbp+5Fh]; this
0x18006bb94  lea     r8, aOnecorePrintsc_88; "onecore\\printscan\\appxpackaging\\stre"...
0x18006bb9b  mov     r9d, r15d; char *
0x18006bb9e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006bba3  lea     rcx, [rbp+57h+var_90]
0x18006bba7  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18006bbac  lea     rcx, [rbp+57h+var_98]
0x18006bbb0  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18006bbb5  lea     rcx, [rbp+57h+ppstm]
0x18006bbb9  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18006bbbe  mov     ebx, r15d
0x18006bbc1  jmp     loc_18006BC7F
0x18006bbc6  cmp     edi, 1
0x18006bbc9  jz      short loc_18006BC20
0x18006bbcb  cmp     word ptr [rbp+57h+arg_10], r12w
0x18006bbd0  jz      short loc_18006BC20
0x18006bbd2  lea     rcx, [rbp+57h+var_78]
0x18006bbd6  mov     [rbp+57h+var_98], r12
0x18006bbda  mov     [rbp+57h+var_78], rbx
0x18006bbde  call    ?InternalAddRef@?$ComPtr@UIXMLDOMNodeList@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IXMLDOMNodeList>::InternalAddRef(void)
0x18006bbe3  mov     rax, [rsi+10h]
0x18006bbe7  lea     rcx, [rbp+57h+var_78]
0x18006bbeb  mov     [rbp+57h+var_78], rax
0x18006bbef  mov     [rsi+10h], rbx
0x18006bbf3  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18006bbf8  lea     rcx, [rbp+57h+var_90]
0x18006bbfc  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18006bc01  lea     rcx, [rbp+57h+var_98]
0x18006bc05  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18006bc0a  lea     rcx, [rbp+57h+ppstm]
0x18006bc0e  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18006bc13  lea     rcx, [rbp+57h+var_88]
0x18006bc17  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18006bc1c  xor     eax, eax
0x18006bc1e  jmp     short loc_18006BC8A
0x18006bc20  mov     rdx, rbx; struct IXMLDOMDocument2 *
0x18006bc23  mov     rcx, r14; struct IStream *
0x18006bc26  call    ?LogCGMParseError@XmlValidationHelper@Packaging@Appx@@SAJPEAUIStream@@PEAUIXMLDOMDocument2@@PEAJ2@Z; Appx::Packaging::XmlValidationHelper::LogCGMParseError(IStream *,IXMLDOMDocument2 *,long *,long *)
0x18006bc2b  test    eax, eax
0x18006bc2d  jns     short loc_18006BC47
0x18006bc2f  mov     rcx, [rbp+5Fh]; this
0x18006bc33  lea     r8, aOnecorePrintsc_88; "onecore\\printscan\\appxpackaging\\stre"...
0x18006bc3a  mov     r9d, eax; char *
0x18006bc3d  mov     edx, 0A5h; void *
0x18006bc42  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006bc47  mov     edx, 0A8h; void *
0x18006bc4c  mov     ebx, 8008020Bh
0x18006bc51  mov     r9d, ebx; char *
0x18006bc54  mov     rcx, [rbp+5Fh]; this
0x18006bc58  lea     r8, aOnecorePrintsc_88; "onecore\\printscan\\appxpackaging\\stre"...
0x18006bc5f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006bc64  lea     rcx, [rbp+57h+var_90]
0x18006bc68  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18006bc6d  lea     rcx, [rbp+57h+var_98]
0x18006bc71  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18006bc76  lea     rcx, [rbp+57h+ppstm]
0x18006bc7a  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18006bc7f  lea     rcx, [rbp+57h+var_88]
0x18006bc83  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18006bc88  mov     eax, ebx
0x18006bc8a  add     rsp, 0A8h
0x18006bc91  pop     r15
0x18006bc93  pop     r14
0x18006bc95  pop     r13
0x18006bc97  pop     r12
0x18006bc99  pop     rdi
0x18006bc9a  pop     rsi
0x18006bc9b  pop     rbx
0x18006bc9c  pop     rbp
0x18006bc9d  retn
```
