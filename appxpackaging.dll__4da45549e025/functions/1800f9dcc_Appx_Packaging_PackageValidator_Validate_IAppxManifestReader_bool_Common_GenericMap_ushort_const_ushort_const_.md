# Appx::Packaging::PackageValidator::Validate(IAppxManifestReader *,bool,Common::GenericMap<ushort const *,ushort const *> const &)

- ea: `0x1800f9dcc`
- end: `0x1800fa130`
- name: `?Validate@PackageValidator@Packaging@Appx@@SAJPEAUIAppxManifestReader@@_NAEBV?$GenericMap@PEBGPEBG@Common@@@Z`
- size: `868`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800c021c`
- `0x1800c0f54`

## callees

- `0x1800029e4`
- `0x180005eb8`
- `0x1800133fc`
- `0x180045334`
- `0x1800538c8`
- `0x180094a38`
- `0x1800f9dcc`
- `0x1800fa138`
- `0x1800fa538`
- `0x1800fa990`
- `0x1800fae7c`
- `0x180106010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800f9f01`
- `OLEAUT32!__imp_SysAllocString` at `0x1800f9f01`
- `OLEAUT32!__imp_SysFreeString` at `0x1800f9f2d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800f9f87`
- `OLEAUT32!__imp_SysFreeString` at `0x1800f9ff8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fa0de`
- `OLEAUT32!__imp_SysFreeString` at `0x1800f9f2d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800f9f87`
- `OLEAUT32!__imp_SysFreeString` at `0x1800f9ff8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fa0de`

## string_xrefs

- `0x1800f9e13`: `(manifestReader.As(&manifestReaderInternal))`
- `0x1800f9ed6`: `(manifestReaderInternal->GetXmlDom(&manifestDom))`
- `0x1800f9e99`: `(manifestReader6->GetIsNonQualifiedResourcePackage(&isNonQualifiedResourcePackage))`
- `0x1800f9e59`: `(manifestReader.As(&manifestReader6))`
- `0x1800fa06d`: `(ValidateProtocolsExtension(manifestReaderInternal.Get(), rootNode.Get()))`
- `0x1800fa04e`: `(ValidateComposedFilesInManifest( manifestReaderInternal.Get(), rootNode.Get(), payloadFiles, Manifest::ComposedFileNameXPaths, (sizeof(*RtlpNumberOf(Manifest::ComposedFileNameXPaths))), !localized && !isNonQualifiedResourcePackage))`
- `0x1800f9fe7`: `(ValidateFilesInManifest( manifestReaderInternal.Get(), rootNode.Get(), payloadFiles, Manifest::FileNameXPaths, (sizeof(*RtlpNumberOf(Manifest::FileNameXPaths))), !localized && !isNonQualifiedResourcePackage))`
- `0x1800f9f73`: `(manifestDom->selectSingleNode(packageRootQuery, &rootNode))`
- `0x1800fa08c`: `(ValidateFileTypeAssociationsExtension(manifestReaderInternal.Get(), rootNode.Get()))`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::PackageValidator::Validate(
        __int64 (__fastcall ***a1)(_QWORD, GUID *, __int64 *),
        __int64 a2,
        __int64 a3)
{
  int v5; // eax
  bool v6; // cl
  unsigned int v7; // ebx
  __int64 (__fastcall *v8)(_QWORD, GUID *, __int64 *); // rbx
  int v9; // eax
  bool v10; // cl
  const char *v11; // r8
  struct IAppxManifestReaderInternal *v12; // rdi
  __int64 (__fastcall *v13)(struct IAppxManifestReaderInternal *, __int64 *); // rbx
  int v14; // eax
  bool v15; // cl
  bool v16; // cl
  OLECHAR *v17; // rbx
  __int64 v18; // rsi
  __int64 (__fastcall *v19)(__int64, OLECHAR *, struct IXMLDOMNode **); // rdi
  bool v20; // cl
  int v21; // edi
  const char *v22; // r8
  int v23; // eax
  bool v24; // cl
  unsigned int v25; // esi
  int v27; // [rsp+20h] [rbp-30h]
  __int64 v28; // [rsp+30h] [rbp-20h] BYREF
  __int64 v29; // [rsp+38h] [rbp-18h] BYREF
  struct IAppxManifestReaderInternal *v30; // [rsp+40h] [rbp-10h] BYREF
  __int64 (__fastcall ***v31)(_QWORD, _QWORD, _QWORD); // [rsp+48h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  int v33; // [rsp+80h] [rbp+30h] BYREF
  struct IXMLDOMNode *v34; // [rsp+98h] [rbp+48h] BYREF

  v31 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))a1;
  Microsoft::WRL::ComPtr<IXMLDOMNodeList>::InternalAddRef(&v31);
  v30 = 0;
  v5 = Microsoft::WRL::ComPtr<IAppxManifestReader>::As<IAppxManifestReaderInternal>(&v31, &v30);
  v7 = v5;
  if ( v5 < 0 )
  {
    Appx::Packaging::SharedWithTools::Logging::WriteFailure(v6, v5, "(manifestReader.As(&manifestReaderInternal))", 0);
    goto LABEL_29;
  }
  v28 = 0;
  v8 = **a1;
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v28);
  v9 = v8(a1, &GUID_34deaca4_d3c0_4e3e_b312_e42625e3807e, &v28);
  v7 = v9;
  if ( v9 < 0 )
  {
    v11 = "(manifestReader.As(&manifestReader6))";
LABEL_5:
    Appx::Packaging::SharedWithTools::Logging::WriteFailure(v10, v9, v11, 0);
LABEL_6:
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v28);
    goto LABEL_29;
  }
  v33 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v28 + 24LL))(v28, &v33);
  v7 = v9;
  if ( v9 < 0 )
  {
    v11 = "(manifestReader6->GetIsNonQualifiedResourcePackage(&isNonQualifiedResourcePackage))";
    goto LABEL_5;
  }
  v12 = v30;
  v29 = 0;
  v13 = *(__int64 (__fastcall **)(struct IAppxManifestReaderInternal *, __int64 *))(*(_QWORD *)v30 + 24LL);
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v29);
  v14 = v13(v12, &v29);
  v7 = v14;
  if ( v14 < 0 )
  {
    Appx::Packaging::SharedWithTools::Logging::WriteFailure(
      v15,
      v14,
      "(manifestReaderInternal->GetXmlDom(&manifestDom))",
      0);
LABEL_11:
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v29);
    goto LABEL_6;
  }
  v34 = 0;
  v17 = SysAllocString(L"m:Package | win10foundation:Package");
  if ( !v17 )
  {
    v7 = -2147024882;
    Appx::Packaging::SharedWithTools::Logging::WriteFailure(v16, -2147024882, "(packageRootQuery) == NULL", 0);
    SysFreeString(0);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v34);
    goto LABEL_11;
  }
  v18 = v29;
  v19 = *(__int64 (__fastcall **)(__int64, OLECHAR *, struct IXMLDOMNode **))(*(_QWORD *)v29 + 296LL);
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v34);
  v21 = v19(v18, v17, &v34);
  if ( v21 >= 0 )
  {
    v23 = Appx::Packaging::PackageValidator::ValidateFilesInManifest(v30, v34, a3);
    v25 = v23;
    if ( v23 < 0 )
    {
      Appx::Packaging::SharedWithTools::Logging::WriteFailure(
        v24,
        v23,
        "(ValidateFilesInManifest( manifestReaderInternal.Get(), rootNode.Get(), payloadFiles, Manifest::FileNameXPaths, "
        "(sizeof(*RtlpNumberOf(Manifest::FileNameXPaths))), !localized && !isNonQualifiedResourcePackage))",
        0);
      SysFreeString(v17);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v34);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v29);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v28);
      v7 = v25;
      goto LABEL_29;
    }
    v21 = Appx::Packaging::PackageValidator::ValidateComposedFilesInManifest(v30, v34, a3);
    if ( v21 >= 0 )
    {
      v21 = Appx::Packaging::PackageValidator::ValidateProtocolsExtension(v30, v34);
      if ( v21 >= 0 )
      {
        v21 = Appx::Packaging::PackageValidator::ValidateFileTypeAssociationsExtension(v30, v34);
        if ( v21 >= 0 )
        {
          if ( !v33 || !Common::GenericMap<unsigned short const *,IAppxFile *>::Find(a3, L"resources.pri") )
          {
            SysFreeString(v17);
            Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v34);
            Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v29);
            Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v28);
            v7 = 0;
            goto LABEL_29;
          }
          v21 = -2146958829;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1BC,
            (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\packagevalidator.cpp",
            (const char *)0x80080213LL,
            v27);
          v22 = "(ValidateNonQualifiedResourcePackage(isNonQualifiedResourcePackage, payloadFiles))";
        }
        else
        {
          v22 = "(ValidateFileTypeAssociationsExtension(manifestReaderInternal.Get(), rootNode.Get()))";
        }
      }
      else
      {
        v22 = "(ValidateProtocolsExtension(manifestReaderInternal.Get(), rootNode.Get()))";
      }
    }
    else
    {
      v22 = "(ValidateComposedFilesInManifest( manifestReaderInternal.Get(), rootNode.Get(), payloadFiles, Manifest::Comp"
            "osedFileNameXPaths, (sizeof(*RtlpNumberOf(Manifest::ComposedFileNameXPaths))), !localized && !isNonQualified"
            "ResourcePackage))";
    }
  }
  else
  {
    v22 = "(manifestDom->selectSingleNode(packageRootQuery, &rootNode))";
  }
  Appx::Packaging::SharedWithTools::Logging::WriteFailure(v20, v21, v22, 0);
  SysFreeString(v17);
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v34);
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v29);
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v28);
  v7 = v21;
LABEL_29:
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v30);
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v31);
  return v7;
}

```

## disassembly

```asm
0x1800f9dcc  mov     [rsp-28h+arg_8], rbx
0x1800f9dd1  push    rbp
0x1800f9dd2  push    rsi
0x1800f9dd3  push    rdi
0x1800f9dd4  push    r14
0x1800f9dd6  push    r15
0x1800f9dd8  mov     rbp, rsp
0x1800f9ddb  sub     rsp, 50h
0x1800f9ddf  mov     rdi, rcx
0x1800f9de2  mov     [rbp+var_8], rcx
0x1800f9de6  lea     rcx, [rbp+var_8]
0x1800f9dea  mov     r15, r8
0x1800f9ded  mov     r14b, dl
0x1800f9df0  call    ?InternalAddRef@?$ComPtr@UIXMLDOMNodeList@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IXMLDOMNodeList>::InternalAddRef(void)
0x1800f9df5  lea     rdx, [rbp+var_10]
0x1800f9df9  mov     [rbp+var_10], 0
0x1800f9e01  lea     rcx, [rbp+var_8]
0x1800f9e05  call    ??$As@UIAppxManifestReaderInternal@@@?$ComPtr@UIAppxManifestReader@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIAppxManifestReaderInternal@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IAppxManifestReader>::As<IAppxManifestReaderInternal>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAppxManifestReaderInternal>>)
0x1800f9e0a  mov     ebx, eax
0x1800f9e0c  test    eax, eax
0x1800f9e0e  jns     short loc_1800F9E26
0x1800f9e10  xor     r9d, r9d; unsigned __int16 *
0x1800f9e13  lea     r8, aManifestreader; "(manifestReader.As(&manifestReaderInter"...
0x1800f9e1a  mov     edx, eax; int
0x1800f9e1c  call    ?WriteFailure@Logging@SharedWithTools@Packaging@Appx@@SAX_NJPEBDPEBG@Z; Appx::Packaging::SharedWithTools::Logging::WriteFailure(bool,long,char const *,ushort const *)
0x1800f9e21  jmp     loc_1800FA107
0x1800f9e26  mov     [rbp+var_20], 0
0x1800f9e2e  lea     rcx, [rbp+var_20]
0x1800f9e32  mov     rax, [rdi]
0x1800f9e35  mov     rbx, [rax]
0x1800f9e38  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800f9e3d  lea     r8, [rbp+var_20]
0x1800f9e41  mov     rcx, rdi
0x1800f9e44  lea     rdx, _GUID_34deaca4_d3c0_4e3e_b312_e42625e3807e
0x1800f9e4b  mov     rax, rbx
0x1800f9e4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f9e53  mov     ebx, eax
0x1800f9e55  test    eax, eax
0x1800f9e57  jns     short loc_1800F9E78
0x1800f9e59  lea     r8, aManifestreader_3; "(manifestReader.As(&manifestReader6))"
0x1800f9e60  xor     r9d, r9d; unsigned __int16 *
0x1800f9e63  mov     edx, eax; int
0x1800f9e65  call    ?WriteFailure@Logging@SharedWithTools@Packaging@Appx@@SAX_NJPEBDPEBG@Z; Appx::Packaging::SharedWithTools::Logging::WriteFailure(bool,long,char const *,ushort const *)
0x1800f9e6a  lea     rcx, [rbp+var_20]
0x1800f9e6e  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800f9e73  jmp     loc_1800FA107
0x1800f9e78  mov     rcx, [rbp+var_20]
0x1800f9e7c  lea     rdx, [rbp+arg_0]
0x1800f9e80  mov     [rbp+arg_0], 0
0x1800f9e87  mov     rax, [rcx]
0x1800f9e8a  mov     rax, [rax+18h]
0x1800f9e8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f9e93  mov     ebx, eax
0x1800f9e95  test    eax, eax
0x1800f9e97  jns     short loc_1800F9EA2
0x1800f9e99  lea     r8, aManifestreader_0; "(manifestReader6->GetIsNonQualifiedReso"...
0x1800f9ea0  jmp     short loc_1800F9E60
0x1800f9ea2  mov     rdi, [rbp+var_10]
0x1800f9ea6  lea     rcx, [rbp+var_18]
0x1800f9eaa  mov     [rbp+var_18], 0
0x1800f9eb2  mov     rax, [rdi]
0x1800f9eb5  mov     rbx, [rax+18h]
0x1800f9eb9  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800f9ebe  lea     rdx, [rbp+var_18]
0x1800f9ec2  mov     rcx, rdi
0x1800f9ec5  mov     rax, rbx
0x1800f9ec8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f9ecd  mov     ebx, eax
0x1800f9ecf  test    eax, eax
0x1800f9ed1  jns     short loc_1800F9EF2
0x1800f9ed3  xor     r9d, r9d; unsigned __int16 *
0x1800f9ed6  lea     r8, aManifestreader_2; "(manifestReaderInternal->GetXmlDom(&man"...
0x1800f9edd  mov     edx, eax; int
0x1800f9edf  call    ?WriteFailure@Logging@SharedWithTools@Packaging@Appx@@SAX_NJPEBDPEBG@Z; Appx::Packaging::SharedWithTools::Logging::WriteFailure(bool,long,char const *,ushort const *)
0x1800f9ee4  lea     rcx, [rbp+var_18]
0x1800f9ee8  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800f9eed  jmp     loc_1800F9E6A
0x1800f9ef2  lea     rcx, ?PackageRootNodeXPath@Element@Manifest@Packaging@Appx@@3QBGB; "m:Package | win10foundation:Package"
0x1800f9ef9  mov     [rbp+arg_18], 0
0x1800f9f01  call    cs:__imp_SysAllocString
0x1800f9f08  nop     dword ptr [rax+rax+00h]
0x1800f9f0d  mov     rbx, rax
0x1800f9f10  test    rax, rax
0x1800f9f13  jnz     short loc_1800F9F44
0x1800f9f15  mov     ebx, 8007000Eh
0x1800f9f1a  lea     r8, aPackagerootque; "(packageRootQuery) == NULL"
0x1800f9f21  mov     edx, ebx; int
0x1800f9f23  xor     r9d, r9d; unsigned __int16 *
0x1800f9f26  call    ?WriteFailure@Logging@SharedWithTools@Packaging@Appx@@SAX_NJPEBDPEBG@Z; Appx::Packaging::SharedWithTools::Logging::WriteFailure(bool,long,char const *,ushort const *)
0x1800f9f2b  xor     ecx, ecx; bstrString
0x1800f9f2d  call    cs:__imp_SysFreeString
0x1800f9f34  nop     dword ptr [rax+rax+00h]
0x1800f9f39  lea     rcx, [rbp+arg_18]
0x1800f9f3d  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800f9f42  jmp     short loc_1800F9EE4
0x1800f9f44  mov     rsi, [rbp+var_18]
0x1800f9f48  lea     rcx, [rbp+arg_18]
0x1800f9f4c  mov     rax, [rsi]
0x1800f9f4f  mov     rdi, [rax+128h]
0x1800f9f56  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800f9f5b  lea     r8, [rbp+arg_18]
0x1800f9f5f  mov     rdx, rbx
0x1800f9f62  mov     rcx, rsi
0x1800f9f65  mov     rax, rdi
0x1800f9f68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f9f6d  mov     edi, eax
0x1800f9f6f  test    eax, eax
0x1800f9f71  jns     short loc_1800F9FB5
0x1800f9f73  lea     r8, aManifestdomSel; "(manifestDom->selectSingleNode(packageR"...
0x1800f9f7a  xor     r9d, r9d; unsigned __int16 *
0x1800f9f7d  mov     edx, edi; int
0x1800f9f7f  call    ?WriteFailure@Logging@SharedWithTools@Packaging@Appx@@SAX_NJPEBDPEBG@Z; Appx::Packaging::SharedWithTools::Logging::WriteFailure(bool,long,char const *,ushort const *)
0x1800f9f84  mov     rcx, rbx; bstrString
0x1800f9f87  call    cs:__imp_SysFreeString
0x1800f9f8e  nop     dword ptr [rax+rax+00h]
0x1800f9f93  lea     rcx, [rbp+arg_18]
0x1800f9f97  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800f9f9c  lea     rcx, [rbp+var_18]
0x1800f9fa0  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800f9fa5  lea     rcx, [rbp+var_20]
0x1800f9fa9  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800f9fae  mov     ebx, edi
0x1800f9fb0  jmp     loc_1800FA107
0x1800f9fb5  mov     dil, 1
0x1800f9fb8  test    r14b, r14b
0x1800f9fbb  jnz     short loc_1800F9FC8
0x1800f9fbd  cmp     [rbp+arg_0], 0
0x1800f9fc1  jnz     short loc_1800F9FC8
0x1800f9fc3  mov     al, dil
0x1800f9fc6  jmp     short loc_1800F9FCA
0x1800f9fc8  xor     eax, eax
0x1800f9fca  mov     rdx, [rbp+arg_18]
0x1800f9fce  mov     r8, r15
0x1800f9fd1  mov     rcx, [rbp+var_10]
0x1800f9fd5  mov     [rsp+50h+var_28], al
0x1800f9fd9  call    ?ValidateFilesInManifest@PackageValidator@Packaging@Appx@@CAJPEAUIAppxManifestReaderInternal@@PEAUIXMLDOMNode@@AEBV?$GenericMap@PEBGPEBG@Common@@PEBUFileNameTable@Manifest@23@K_N@Z; Appx::Packaging::PackageValidator::ValidateFilesInManifest(IAppxManifestReaderInternal *,IXMLDOMNode *,Common::GenericMap<ushort const *,ushort const *> const &,Appx::Packaging::Manifest::FileNameTable const *,ulong,bool)
0x1800f9fde  mov     esi, eax
0x1800f9fe0  test    eax, eax
0x1800f9fe2  jns     short loc_1800FA026
0x1800f9fe4  xor     r9d, r9d; unsigned __int16 *
0x1800f9fe7  lea     r8, aValidatefilesi; "(ValidateFilesInManifest( manifestReade"...
0x1800f9fee  mov     edx, eax; int
0x1800f9ff0  call    ?WriteFailure@Logging@SharedWithTools@Packaging@Appx@@SAX_NJPEBDPEBG@Z; Appx::Packaging::SharedWithTools::Logging::WriteFailure(bool,long,char const *,ushort const *)
0x1800f9ff5  mov     rcx, rbx; bstrString
0x1800f9ff8  call    cs:__imp_SysFreeString
0x1800f9fff  nop     dword ptr [rax+rax+00h]
0x1800fa004  lea     rcx, [rbp+arg_18]
0x1800fa008  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800fa00d  lea     rcx, [rbp+var_18]
0x1800fa011  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800fa016  lea     rcx, [rbp+var_20]
0x1800fa01a  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800fa01f  mov     ebx, esi
0x1800fa021  jmp     loc_1800FA107
0x1800fa026  test    r14b, r14b
0x1800fa029  jnz     short loc_1800FA031
0x1800fa02b  cmp     [rbp+arg_0], 0
0x1800fa02f  jz      short loc_1800FA033
0x1800fa031  xor     edi, edi
0x1800fa033  mov     rdx, [rbp+arg_18]
0x1800fa037  mov     r8, r15
0x1800fa03a  mov     rcx, [rbp+var_10]
0x1800fa03e  mov     [rsp+50h+var_28], dil
0x1800fa043  call    ?ValidateComposedFilesInManifest@PackageValidator@Packaging@Appx@@CAJPEAUIAppxManifestReaderInternal@@PEAUIXMLDOMNode@@AEBV?$GenericMap@PEBGPEBG@Common@@PEBUComposedFileNameTable@Manifest@23@K_N@Z; Appx::Packaging::PackageValidator::ValidateComposedFilesInManifest(IAppxManifestReaderInternal *,IXMLDOMNode *,Common::GenericMap<ushort const *,ushort const *> const &,Appx::Packaging::Manifest::ComposedFileNameTable const *,ulong,bool)
0x1800fa048  mov     edi, eax
0x1800fa04a  test    eax, eax
0x1800fa04c  jns     short loc_1800FA05A
0x1800fa04e  lea     r8, aValidatecompos; "(ValidateComposedFilesInManifest( manif"...
0x1800fa055  jmp     loc_1800F9F7A
0x1800fa05a  mov     rdx, [rbp+arg_18]; struct IXMLDOMNode *
0x1800fa05e  mov     rcx, [rbp+var_10]; struct IAppxManifestReaderInternal *
0x1800fa062  call    ?ValidateProtocolsExtension@PackageValidator@Packaging@Appx@@CAJPEAUIAppxManifestReaderInternal@@PEAUIXMLDOMNode@@@Z; Appx::Packaging::PackageValidator::ValidateProtocolsExtension(IAppxManifestReaderInternal *,IXMLDOMNode *)
0x1800fa067  mov     edi, eax
0x1800fa069  test    eax, eax
0x1800fa06b  jns     short loc_1800FA079
0x1800fa06d  lea     r8, aValidateprotoc; "(ValidateProtocolsExtension(manifestRea"...
0x1800fa074  jmp     loc_1800F9F7A
0x1800fa079  mov     rdx, [rbp+arg_18]; struct IXMLDOMNode *
0x1800fa07d  mov     rcx, [rbp+var_10]; struct IAppxManifestReaderInternal *
0x1800fa081  call    ?ValidateFileTypeAssociationsExtension@PackageValidator@Packaging@Appx@@CAJPEAUIAppxManifestReaderInternal@@PEAUIXMLDOMNode@@@Z; Appx::Packaging::PackageValidator::ValidateFileTypeAssociationsExtension(IAppxManifestReaderInternal *,IXMLDOMNode *)
0x1800fa086  mov     edi, eax
0x1800fa088  test    eax, eax
0x1800fa08a  jns     short loc_1800FA098
0x1800fa08c  lea     r8, aValidatefilety; "(ValidateFileTypeAssociationsExtension("...
0x1800fa093  jmp     loc_1800F9F7A
0x1800fa098  cmp     [rbp+arg_0], 0
0x1800fa09c  jz      short loc_1800FA0DB
0x1800fa09e  lea     rdx, aResourcesPri; "resources.pri"
0x1800fa0a5  mov     rcx, r15
0x1800fa0a8  call    ?Find@?$GenericMap@PEBGPEAUIAppxFile@@@Common@@QEAAPEAUIAppxFile@@PEBG@Z; Common::GenericMap<ushort const *,IAppxFile *>::Find(ushort const *)
0x1800fa0ad  test    rax, rax
0x1800fa0b0  jz      short loc_1800FA0DB
0x1800fa0b2  mov     rcx, [rbp+28h]; this
0x1800fa0b6  lea     r8, aOnecorePrintsc_158; "onecore\\printscan\\appxpackaging\\lib"...
0x1800fa0bd  mov     edi, 80080213h
0x1800fa0c2  mov     edx, 1BCh; void *
0x1800fa0c7  mov     r9d, edi; char *
0x1800fa0ca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800fa0cf  lea     r8, aValidatenonqua; "(ValidateNonQualifiedResourcePackage(is"...
0x1800fa0d6  jmp     loc_1800F9F7A
0x1800fa0db  mov     rcx, rbx; bstrString
0x1800fa0de  call    cs:__imp_SysFreeString
0x1800fa0e5  nop     dword ptr [rax+rax+00h]
0x1800fa0ea  lea     rcx, [rbp+arg_18]
0x1800fa0ee  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800fa0f3  lea     rcx, [rbp+var_18]
0x1800fa0f7  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800fa0fc  lea     rcx, [rbp+var_20]
0x1800fa100  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800fa105  xor     ebx, ebx
0x1800fa107  lea     rcx, [rbp+var_10]
0x1800fa10b  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800fa110  lea     rcx, [rbp+var_8]
0x1800fa114  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800fa119  mov     eax, ebx
0x1800fa11b  mov     rbx, [rsp+50h+arg_8]
0x1800fa123  add     rsp, 50h
0x1800fa127  pop     r15
0x1800fa129  pop     r14
0x1800fa12b  pop     rdi
0x1800fa12c  pop     rsi
0x1800fa12d  pop     rbp
0x1800fa12e  retn
```
