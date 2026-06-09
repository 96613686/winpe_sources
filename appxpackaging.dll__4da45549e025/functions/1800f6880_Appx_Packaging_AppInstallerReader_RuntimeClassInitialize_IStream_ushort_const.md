# Appx::Packaging::AppInstallerReader::RuntimeClassInitialize(IStream *,ushort const *)

- ea: `0x1800f6880`
- end: `0x1800f6b19`
- name: `?RuntimeClassInitialize@AppInstallerReader@Packaging@Appx@@QEAAJPEAUIStream@@PEBG@Z`
- size: `665`
- prototype: `int(Appx::Packaging::AppInstallerReader *__hidden this, struct IStream *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800f62ec`
- `0x1800f63cc`

## callees

- `0x180005eb8`
- `0x180007a28`
- `0x1800093b4`
- `0x180009eb8`
- `0x1800133fc`
- `0x180050b50`
- `0x18005dbd8`
- `0x1800992a0`
- `0x1800f6578`
- `0x1800f6880`

## import_xrefs

- `OpcServices!__imp_GetCloneableStream` at `0x1800f696e`
- `OpcServices!__imp_GetCloneableStream` at `0x1800f696e`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800f68f0`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800f68f0`

## string_xrefs

- `0x1800f6a75`: `AppxPackaging.dll`
- `0x1800f68b8`: `onecore\printscan\appxpackaging\appinstaller\src\appinstallerreader.cpp`
- `0x1800f6928`: `onecore\printscan\appxpackaging\appinstaller\src\appinstallerreader.cpp`
- `0x1800f6989`: `onecore\printscan\appxpackaging\appinstaller\src\appinstallerreader.cpp`
- `0x1800f6ab4`: `onecore\printscan\appxpackaging\appinstaller\src\appinstallerreader.cpp`
- `0x1800f69e3`: `http://schemas.microsoft.com/appx/appinstaller/2017/2`
- `0x1800f69cd`: `http://schemas.microsoft.com/appx/appinstaller/2017`
- `0x1800f6a0f`: `http://schemas.microsoft.com/appx/appinstaller/2021`
- `0x1800f69f9`: `http://schemas.microsoft.com/appx/appinstaller/2018`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::AppInstallerReader::RuntimeClassInitialize(
        Appx::Packaging::AppInstallerReader *this,
        struct IStream *a2,
        Appx::Packaging *a3)
{
  unsigned int v6; // ebx
  HRESULT v7; // eax
  __int64 v8; // rdx
  const unsigned __int16 *v9; // r8
  int CloneableStream; // eax
  unsigned __int64 v11; // r8
  __int64 v12; // rdx
  int v13; // eax
  int v15; // [rsp+20h] [rbp-99h]
  int v16; // [rsp+20h] [rbp-99h]
  struct IStream *v17; // [rsp+40h] [rbp-79h] BYREF
  LPSTREAM ppstm; // [rsp+48h] [rbp-71h] BYREF
  void **v19; // [rsp+50h] [rbp-69h] BYREF
  _QWORD v20[3]; // [rsp+58h] [rbp-61h] BYREF
  __int128 v21; // [rsp+70h] [rbp-49h]
  __int64 v22; // [rsp+80h] [rbp-39h]
  char v23; // [rsp+88h] [rbp-31h]
  __int16 v24; // [rsp+90h] [rbp-29h]
  _QWORD v25[8]; // [rsp+A0h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  if ( a2 )
  {
    ppstm = 0;
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&ppstm);
    v7 = CreateStreamOnHGlobal(0, 1, &ppstm);
    v6 = v7;
    if ( v7 < 0 )
    {
      v8 = 82;
LABEL_7:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"onecore\\printscan\\appxpackaging\\appinstaller\\src\\appinstallerreader.cpp",
        (const char *)(unsigned int)v7,
        v15);
LABEL_19:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&ppstm);
      return v6;
    }
    v7 = Appx::Packaging::CopyStreamAndCalculateDigest(a2, ppstm);
    v6 = v7;
    if ( v7 < 0 )
    {
      v8 = 84;
      goto LABEL_7;
    }
    v7 = Appx::Packaging::VerifyDigest(a3, *((const unsigned __int16 **)this + 5), v9);
    v6 = v7;
    if ( v7 < 0 )
    {
      v8 = 85;
      goto LABEL_7;
    }
    v17 = 0;
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v17);
    CloneableStream = GetCloneableStream(ppstm, &v17);
    v6 = CloneableStream;
    if ( CloneableStream >= 0 )
    {
      CloneableStream = Appx::Packaging::SetStreamPosition(v17, 0, v11);
      v6 = CloneableStream;
      if ( CloneableStream >= 0 )
      {
        v25[0] = L"s";
        v25[1] = L"http://schemas.microsoft.com/appx/appinstaller/2017";
        v25[2] = L"s2";
        v25[3] = L"http://schemas.microsoft.com/appx/appinstaller/2017/2";
        v25[4] = L"s3";
        v25[5] = L"http://schemas.microsoft.com/appx/appinstaller/2018";
        v25[6] = L"s4";
        v25[7] = L"http://schemas.microsoft.com/appx/appinstaller/2021";
        v19 = &Appx::Packaging::IXmlSchemaProvider::`vftable';
        Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ISAXContentHandler,ISAXErrorHandler>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ISAXContentHandler,ISAXErrorHandler>(v20);
        v22 = 0;
        v19 = &Appx::Packaging::AppInstallerSchemaProvider::`vftable';
        v23 = 1;
        v20[0] = &Appx::Packaging::AppInstallerSchemaProvider::`vftable'{for `ISAXContentHandler'};
        v21 = 0;
        v20[1] = &Appx::Packaging::AppInstallerSchemaProvider::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ISAXErrorHandler>'};
        v24 = 0;
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease((char *)this + 32);
        v13 = Appx::Packaging::XmlValidationHelper::ValidateXml(
                v17,
                (struct Appx::Packaging::IXmlSchemaProvider *)&v19,
                (struct XmlNamespaceAlias *)v25,
                4u,
                0x8008020C,
                L"AppxPackaging.dll",
                (struct IXMLDOMDocument **)this + 4,
                0);
        v6 = v13;
        if ( v13 >= 0 )
        {
          Appx::Packaging::EncryptionExclusionFileListSchemaProvider::~EncryptionExclusionFileListSchemaProvider((Appx::Packaging::EncryptionExclusionFileListSchemaProvider *)&v19);
          Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v17);
          v6 = 0;
          goto LABEL_19;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x6A,
          (unsigned int)"onecore\\printscan\\appxpackaging\\appinstaller\\src\\appinstallerreader.cpp",
          (const char *)(unsigned int)v13,
          v16);
        Appx::Packaging::EncryptionExclusionFileListSchemaProvider::~EncryptionExclusionFileListSchemaProvider((Appx::Packaging::EncryptionExclusionFileListSchemaProvider *)&v19);
        goto LABEL_13;
      }
      v12 = 90;
    }
    else
    {
      v12 = 89;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\printscan\\appxpackaging\\appinstaller\\src\\appinstallerreader.cpp",
      (const char *)(unsigned int)CloneableStream,
      v15);
LABEL_13:
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v17);
    goto LABEL_19;
  }
  v6 = -2147467261;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x4A,
    (unsigned int)"onecore\\printscan\\appxpackaging\\appinstaller\\src\\appinstallerreader.cpp",
    (const char *)0x80004003LL,
    v15);
  return v6;
}

```

## disassembly

```asm
0x1800f6880  mov     [rsp-8+arg_18], rbx
0x1800f6885  push    rbp
0x1800f6886  push    rsi
0x1800f6887  push    rdi
0x1800f6888  push    r14
0x1800f688a  push    r15
0x1800f688c  lea     rbp, [rsp-37h]
0x1800f6891  sub     rsp, 0F0h
0x1800f6898  mov     rax, cs:__security_cookie
0x1800f689f  xor     rax, rsp
0x1800f68a2  mov     [rbp+57h+var_30], rax
0x1800f68a6  mov     r15, r8
0x1800f68a9  mov     rsi, rdx
0x1800f68ac  mov     r14, rcx
0x1800f68af  test    rdx, rdx
0x1800f68b2  jnz     short loc_1800F68D4
0x1800f68b4  mov     rcx, [rbp+5Fh]; this
0x1800f68b8  lea     r8, aOnecorePrintsc_137; "onecore\\printscan\\appxpackaging\\appi"...
0x1800f68bf  mov     ebx, 80004003h
0x1800f68c4  lea     edx, [rsi+4Ah]; void *
0x1800f68c7  mov     r9d, ebx; char *
0x1800f68ca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f68cf  jmp     loc_1800F6AF3
0x1800f68d4  lea     rcx, [rbp+57h+ppstm]
0x1800f68d8  mov     [rbp+57h+ppstm], 0
0x1800f68e0  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800f68e5  lea     r8, [rbp+57h+ppstm]; ppstm
0x1800f68e9  mov     edx, 1; fDeleteOnRelease
0x1800f68ee  xor     ecx, ecx; hGlobal
0x1800f68f0  call    cs:__imp_CreateStreamOnHGlobal
0x1800f68f7  nop     dword ptr [rax+rax+00h]
0x1800f68fc  mov     ebx, eax
0x1800f68fe  test    eax, eax
0x1800f6900  jns     short loc_1800F6909
0x1800f6902  mov     edx, 52h ; 'R'
0x1800f6907  jmp     short loc_1800F6924
0x1800f6909  mov     rdx, [rbp+57h+ppstm]
0x1800f690d  lea     r8, [r14+28h]
0x1800f6911  mov     rcx, rsi
0x1800f6914  call    ?CopyStreamAndCalculateDigest@Packaging@Appx@@YAJPEAUIStream@@0AEAV?$AutoArray@G$1??$AutoArrayDeallocate@G@Common@@YAXPEAG@Z@Common@@@Z; Appx::Packaging::CopyStreamAndCalculateDigest(IStream *,IStream *,Common::AutoArray<ushort,&Common::AutoArrayDeallocate<ushort>(ushort *)> &)
0x1800f6919  mov     ebx, eax
0x1800f691b  test    eax, eax
0x1800f691d  jns     short loc_1800F693C
0x1800f691f  mov     edx, 54h ; 'T'; void *
0x1800f6924  mov     rcx, [rbp+5Fh]; this
0x1800f6928  lea     r8, aOnecorePrintsc_137; "onecore\\printscan\\appxpackaging\\appi"...
0x1800f692f  mov     r9d, eax; char *
0x1800f6932  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f6937  jmp     loc_1800F6AEA
0x1800f693c  mov     rdx, [r14+28h]; unsigned __int16 *
0x1800f6940  mov     rcx, r15; this
0x1800f6943  call    ?VerifyDigest@Packaging@Appx@@YAJPEBG0@Z; Appx::Packaging::VerifyDigest(ushort const *,ushort const *)
0x1800f6948  mov     ebx, eax
0x1800f694a  test    eax, eax
0x1800f694c  jns     short loc_1800F6955
0x1800f694e  mov     edx, 55h ; 'U'
0x1800f6953  jmp     short loc_1800F6924
0x1800f6955  lea     rcx, [rbp+57h+var_D0]
0x1800f6959  mov     [rbp+57h+var_D0], 0
0x1800f6961  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800f6966  mov     rcx, [rbp+57h+ppstm]
0x1800f696a  lea     rdx, [rbp+57h+var_D0]
0x1800f696e  call    cs:__imp_GetCloneableStream
0x1800f6975  nop     dword ptr [rax+rax+00h]
0x1800f697a  mov     ebx, eax
0x1800f697c  test    eax, eax
0x1800f697e  jns     short loc_1800F69A6
0x1800f6980  mov     edx, 59h ; 'Y'; void *
0x1800f6985  mov     rcx, [rbp+5Fh]; this
0x1800f6989  lea     r8, aOnecorePrintsc_137; "onecore\\printscan\\appxpackaging\\appi"...
0x1800f6990  mov     r9d, eax; char *
0x1800f6993  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f6998  lea     rcx, [rbp+57h+var_D0]
0x1800f699c  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800f69a1  jmp     loc_1800F6AEA
0x1800f69a6  mov     rcx, [rbp+57h+var_D0]; this
0x1800f69aa  xor     edx, edx; struct IStream *
0x1800f69ac  call    ?SetStreamPosition@Packaging@Appx@@YAJPEAUIStream@@_K@Z; Appx::Packaging::SetStreamPosition(IStream *,unsigned __int64)
0x1800f69b1  mov     ebx, eax
0x1800f69b3  test    eax, eax
0x1800f69b5  jns     short loc_1800F69BE
0x1800f69b7  mov     edx, 5Ah ; 'Z'
0x1800f69bc  jmp     short loc_1800F6985
0x1800f69be  lea     rax, ?Namespace2017Alias@AppInstaller@Packaging@Appx@@3QBGB; "s"
0x1800f69c5  mov     [rbp+57h+var_70], rax
0x1800f69c9  lea     rcx, [rbp+57h+var_B8]
0x1800f69cd  lea     rax, ?Namespace2017@AppInstaller@Packaging@Appx@@3QBGB; "http://schemas.microsoft.com/appx/appin"...
0x1800f69d4  mov     [rbp+57h+var_68], rax
0x1800f69d8  lea     rax, ?Namespace2017Alias_v2@AppInstaller@Packaging@Appx@@3QBGB; "s2"
0x1800f69df  mov     [rbp+57h+var_60], rax
0x1800f69e3  lea     rax, ?Namespace2017_v2@AppInstaller@Packaging@Appx@@3QBGB; "http://schemas.microsoft.com/appx/appin"...
0x1800f69ea  mov     [rbp+57h+var_58], rax
0x1800f69ee  lea     rax, ?Namespace2018Alias@AppInstaller@Packaging@Appx@@3QBGB; "s3"
0x1800f69f5  mov     [rbp+57h+var_50], rax
0x1800f69f9  lea     rax, ?Namespace2018@AppInstaller@Packaging@Appx@@3QBGB; "http://schemas.microsoft.com/appx/appin"...
0x1800f6a00  mov     [rbp+57h+var_48], rax
0x1800f6a04  lea     rax, ?Namespace2021Alias@AppInstaller@Packaging@Appx@@3QBGB; "s4"
0x1800f6a0b  mov     [rbp+57h+var_40], rax
0x1800f6a0f  lea     rax, ?Namespace2021@AppInstaller@Packaging@Appx@@3QBGB; "http://schemas.microsoft.com/appx/appin"...
0x1800f6a16  mov     [rbp+57h+var_38], rax
0x1800f6a1a  lea     rax, ??_7IXmlSchemaProvider@Packaging@Appx@@6B@; const Appx::Packaging::IXmlSchemaProvider::`vftable'
0x1800f6a21  mov     [rbp+57h+var_C0], rax
0x1800f6a25  call    ??0?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UISAXContentHandler@@UISAXErrorHandler@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ISAXContentHandler,ISAXErrorHandler>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ISAXContentHandler,ISAXErrorHandler>(void)
0x1800f6a2a  lea     rax, ??_7AppInstallerSchemaProvider@Packaging@Appx@@6B@; const Appx::Packaging::AppInstallerSchemaProvider::`vftable'
0x1800f6a31  mov     [rbp+57h+var_90], 0
0x1800f6a39  mov     [rbp+57h+var_C0], rax
0x1800f6a3d  lea     rbx, [r14+20h]
0x1800f6a41  lea     rax, ??_7AppInstallerSchemaProvider@Packaging@Appx@@6BISAXContentHandler@@@; const Appx::Packaging::AppInstallerSchemaProvider::`vftable'{for `ISAXContentHandler'}
0x1800f6a48  mov     [rbp+57h+var_88], 1
0x1800f6a4c  mov     [rbp+57h+var_B8], rax
0x1800f6a50  xorps   xmm0, xmm0
0x1800f6a53  lea     rax, ??_7AppInstallerSchemaProvider@Packaging@Appx@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UISAXErrorHandler@@@Details@WRL@Microsoft@@@; const Appx::Packaging::AppInstallerSchemaProvider::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ISAXErrorHandler>'}
0x1800f6a5a  movdqa  [rbp+57h+var_A0], xmm0
0x1800f6a5f  mov     rcx, rbx
0x1800f6a62  mov     [rbp+57h+var_B0], rax
0x1800f6a66  mov     [rbp+57h+var_80], 0
0x1800f6a6c  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800f6a71  mov     rcx, [rbp+57h+var_D0]; struct IStream *
0x1800f6a75  lea     rax, LibFileName; "AppxPackaging.dll"
0x1800f6a7c  mov     [rsp+110h+var_D8], 0; struct IXMLDOMDocument **
0x1800f6a85  lea     r8, [rbp+57h+var_70]; struct XmlNamespaceAlias *
0x1800f6a89  mov     [rsp+110h+var_E0], rbx; struct IXMLDOMDocument **
0x1800f6a8e  lea     rdx, [rbp+57h+var_C0]; struct Appx::Packaging::IXmlSchemaProvider *
0x1800f6a92  mov     [rsp+110h+var_E8], rax; unsigned __int16 *
0x1800f6a97  mov     r9d, 4; unsigned int
0x1800f6a9d  mov     [rsp+110h+var_F0], 8008020Ch; int
0x1800f6aa5  call    ?ValidateXml@XmlValidationHelper@Packaging@Appx@@SAJPEAUIStream@@PEAUIXmlSchemaProvider@23@PEAUXmlNamespaceAlias@@KJPEBGPEAPEAUIXMLDOMDocument@@4@Z; Appx::Packaging::XmlValidationHelper::ValidateXml(IStream *,Appx::Packaging::IXmlSchemaProvider *,XmlNamespaceAlias *,ulong,long,ushort const *,IXMLDOMDocument * *,IXMLDOMDocument * *)
0x1800f6aaa  mov     ebx, eax
0x1800f6aac  test    eax, eax
0x1800f6aae  jns     short loc_1800F6AD6
0x1800f6ab0  mov     rcx, [rbp+5Fh]; this
0x1800f6ab4  lea     r8, aOnecorePrintsc_137; "onecore\\printscan\\appxpackaging\\appi"...
0x1800f6abb  mov     r9d, eax; char *
0x1800f6abe  mov     edx, 6Ah ; 'j'; void *
0x1800f6ac3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f6ac8  lea     rcx, [rbp+57h+var_C0]; this
0x1800f6acc  call    ??1EncryptionExclusionFileListSchemaProvider@Packaging@Appx@@UEAA@XZ; Appx::Packaging::EncryptionExclusionFileListSchemaProvider::~EncryptionExclusionFileListSchemaProvider(void)
0x1800f6ad1  jmp     loc_1800F6998
0x1800f6ad6  lea     rcx, [rbp+57h+var_C0]; this
0x1800f6ada  call    ??1EncryptionExclusionFileListSchemaProvider@Packaging@Appx@@UEAA@XZ; Appx::Packaging::EncryptionExclusionFileListSchemaProvider::~EncryptionExclusionFileListSchemaProvider(void)
0x1800f6adf  lea     rcx, [rbp+57h+var_D0]
0x1800f6ae3  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800f6ae8  xor     ebx, ebx
0x1800f6aea  lea     rcx, [rbp+57h+ppstm]
0x1800f6aee  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800f6af3  mov     eax, ebx
0x1800f6af5  mov     rcx, [rbp+57h+var_30]
0x1800f6af9  xor     rcx, rsp; StackCookie
0x1800f6afc  call    __security_check_cookie
0x1800f6b01  mov     rbx, [rsp+110h+arg_18]
0x1800f6b09  add     rsp, 0F0h
0x1800f6b10  pop     r15
0x1800f6b12  pop     r14
0x1800f6b14  pop     rdi
0x1800f6b15  pop     rsi
0x1800f6b16  pop     rbp
0x1800f6b17  retn
```
