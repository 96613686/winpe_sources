# Appx::Packaging::Manifest::AppxManifestReaderImpl::ValidateOutOfProcessServerExtension(IXMLDOMNode *,bool,ushort const *,ushort const *)

- ea: `0x1800605ec`
- end: `0x180060cf3`
- name: `?ValidateOutOfProcessServerExtension@AppxManifestReaderImpl@Manifest@Packaging@Appx@@AEAAJPEAUIXMLDOMNode@@_NPEBG2@Z`
- size: `1799`
- prototype: `__int64 __fastcall(Appx::Packaging::XmlLineInformation **this, OLECHAR *, char, struct Common::AutoBStr *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `18`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001c8a8`
- `0x1800d757c`

## callees

- `0x180005eb8`
- `0x180010f40`
- `0x180011a70`
- `0x1800133fc`
- `0x18002e7e0`
- `0x180030958`
- `0x180039590`
- `0x18003a344`
- `0x18003a4a0`
- `0x18003adec`
- `0x18003c7c8`
- `0x1800605ec`
- `0x18006bf44`
- `0x18007b024`
- `0x1800992c4`
- `0x1800e0c4c`
- `0x1801051c0`
- `0x180106010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180060736`
- `OLEAUT32!__imp_SysFreeString` at `0x180060781`
- `OLEAUT32!__imp_SysFreeString` at `0x180060791`
- `OLEAUT32!__imp_SysFreeString` at `0x1800607fd`
- `OLEAUT32!__imp_SysFreeString` at `0x1800608e2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800608f2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800609e6`
- `OLEAUT32!__imp_SysFreeString` at `0x180060a4e`
- `OLEAUT32!__imp_SysFreeString` at `0x180060b1b`
- `OLEAUT32!__imp_SysFreeString` at `0x180060b2a`
- `OLEAUT32!__imp_SysFreeString` at `0x180060be0`
- `OLEAUT32!__imp_SysFreeString` at `0x180060bef`
- `OLEAUT32!__imp_SysFreeString` at `0x180060ca6`
- `OLEAUT32!__imp_SysFreeString` at `0x180060cb6`
- `OLEAUT32!__imp_SysFreeString` at `0x180060cd2`
- `OLEAUT32!__imp_SysFreeString` at `0x180060736`
- `OLEAUT32!__imp_SysFreeString` at `0x180060781`
- `OLEAUT32!__imp_SysFreeString` at `0x180060791`
- `OLEAUT32!__imp_SysFreeString` at `0x1800607fd`
- `OLEAUT32!__imp_SysFreeString` at `0x1800608e2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800608f2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800609e6`
- `OLEAUT32!__imp_SysFreeString` at `0x180060a4e`
- `OLEAUT32!__imp_SysFreeString` at `0x180060b1b`
- `OLEAUT32!__imp_SysFreeString` at `0x180060b2a`
- `OLEAUT32!__imp_SysFreeString` at `0x180060be0`
- `OLEAUT32!__imp_SysFreeString` at `0x180060bef`
- `OLEAUT32!__imp_SysFreeString` at `0x180060ca6`
- `OLEAUT32!__imp_SysFreeString` at `0x180060cb6`
- `OLEAUT32!__imp_SysFreeString` at `0x180060cd2`

## string_xrefs

- `0x18006066d`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestreader.cpp`
- `0x1800606da`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestreader.cpp`
- `0x180060721`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestreader.cpp`
- `0x18006076c`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestreader.cpp`
- `0x1800607e6`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestreader.cpp`
- `0x1800608d2`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestreader.cpp`
- `0x1800609cf`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestreader.cpp`
- `0x180060a37`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestreader.cpp`
- `0x180060afc`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestreader.cpp`
- `0x180060bbd`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestreader.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Appx::Packaging::Manifest::AppxManifestReaderImpl::ValidateOutOfProcessServerExtension(
        Appx::Packaging::XmlLineInformation **this,
        OLECHAR *a2,
        char a3,
        struct Common::AutoBStr *a4,
        const unsigned __int16 *a5)
{
  int v9; // eax
  int Node; // ebx
  int AttributeValue; // eax
  int v12; // eax
  int *v13; // r9
  struct IStream *v14; // rcx
  int v15; // eax
  __int64 v16; // rdx
  int v17; // ecx
  int v18; // r14d
  __int64 v19; // rdx
  int v20; // ecx
  int v21; // eax
  __int64 v22; // rdx
  int v23; // eax
  __int64 v24; // rdx
  OLECHAR *v25; // rdi
  OLECHAR *v26; // rbx
  BSTR v27; // rax
  int v28; // edx
  int v29; // ecx
  BSTR v30; // rax
  int v31; // ecx
  int v32; // edx
  int v33; // eax
  unsigned __int64 v34; // rdx
  int v35; // ecx
  unsigned __int16 *v36; // rsi
  unsigned __int64 v37; // rdx
  OLECHAR *v38; // rbx
  int v39; // ecx
  unsigned __int16 *v41; // [rsp+20h] [rbp-61h]
  int v42; // [rsp+20h] [rbp-61h]
  int v43; // [rsp+20h] [rbp-61h]
  int v44; // [rsp+20h] [rbp-61h]
  unsigned int *v45; // [rsp+30h] [rbp-51h] BYREF
  struct IStream *v46; // [rsp+38h] [rbp-49h] BYREF
  bool v47; // [rsp+40h] [rbp-41h] BYREF
  BSTR bstrString; // [rsp+48h] [rbp-39h] BYREF
  BSTR String1; // [rsp+50h] [rbp-31h] BYREF
  BSTR v50; // [rsp+58h] [rbp-29h] BYREF
  BSTR v51; // [rsp+60h] [rbp-21h] BYREF
  BSTR v52; // [rsp+68h] [rbp-19h] BYREF
  int v53; // [rsp+70h] [rbp-11h] BYREF
  const unsigned __int16 *v54; // [rsp+78h] [rbp-9h]
  int v55; // [rsp+80h] [rbp-1h]
  const wchar_t *v56; // [rsp+88h] [rbp+7h]
  int v57; // [rsp+90h] [rbp+Fh]
  __int64 v58; // [rsp+98h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+57h]

  v58 = -2;
  v45 = 0;
  v52 = 0;
  v53 = 3;
  v54 = L"OutOfProcessServer";
  v55 = 18;
  v56 = L"']";
  v57 = 0;
  v9 = Appx::Packaging::BuildXPath(
         (Appx::Packaging *)&v53,
         (const struct Appx::Packaging::XPathComponent *)1,
         (unsigned int)&v52,
         a4);
  Node = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC04,
      (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestreader.cpp",
      (const char *)(unsigned int)v9,
      (int)v41);
    goto LABEL_72;
  }
  v46 = 0;
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v46);
  v50 = a2;
  if ( a2 )
    (*(void (__fastcall **)(OLECHAR *))(*(_QWORD *)a2 + 8LL))(a2);
  Node = Appx::Packaging::TryGetNode(&v50, v52, &v46);
  if ( a2 )
    (*(void (__fastcall **)(OLECHAR *))(*(_QWORD *)a2 + 16LL))(a2);
  if ( Node < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC06,
      (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestreader.cpp",
      (const char *)(unsigned int)Node,
      (int)v41);
LABEL_9:
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v46);
    goto LABEL_72;
  }
  bstrString = 0;
  AttributeValue = Appx::Packaging::GetAttributeValue(&v46, L"RunFullTrust", 0, &bstrString);
  Node = AttributeValue;
  if ( AttributeValue < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC09,
      (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestreader.cpp",
      (const char *)(unsigned int)AttributeValue,
      (int)v41);
LABEL_12:
    SysFreeString(bstrString);
    goto LABEL_9;
  }
  String1 = 0;
  v12 = Appx::Packaging::GetAttributeValue(&v46, L"IdentityType", 0, &String1);
  Node = v12;
  if ( v12 >= 0 )
  {
    if ( bstrString )
    {
      LODWORD(v51) = 0;
      v15 = Appx::Packaging::ConvertToBool((Appx::Packaging *)bstrString, 0, (int)&v51, v13);
      Node = v15;
      if ( v15 < 0 )
      {
        v16 = 3089;
LABEL_19:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v16,
          (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestreader.cpp",
          (const char *)(unsigned int)v15,
          (int)v41);
LABEL_20:
        SysFreeString(String1);
        goto LABEL_12;
      }
      if ( (_DWORD)v51 )
      {
        v47 = 0;
        v15 = Appx::Packaging::Manifest::AppxManifestReaderImpl::ValidateCapability(
                (Appx::Packaging::Manifest::AppxManifestReaderImpl *)this,
                L"runFullTrust",
                APPX_CAPABILITY_CLASS_RESTRICTED,
                &v47);
        Node = v15;
        if ( v15 < 0 )
        {
          v16 = 3094;
          goto LABEL_19;
        }
        if ( !v47 )
        {
          Appx::Packaging::XmlLineInformation::GetXmlLineInformation(
            this[13],
            v46,
            0,
            0,
            (const unsigned __int16 *)&v45 + 2,
            (unsigned int *)&v45,
            v45);
          v18 = -2146958844;
          if ( (Microsoft_Windows_AppxPackagingOMEnableBits & 1) != 0 )
            McTemplateU0dqqz_EventWriteTransfer(
              v17,
              (unsigned int)&EVENT_MANIFEST_MISSING_CAPABILITY,
              -2146958844,
              HIDWORD(v45),
              (char)v45,
              (__int64)L"runFullTrust");
          AppxPackagingLog(
            &EVENT_MANIFEST_MISSING_CAPABILITY,
            0xB00000BF,
            -2146958844,
            HIDWORD(v45),
            (unsigned int)v45,
            L"runFullTrust");
          v19 = 3099;
LABEL_28:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v19,
            (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestreader.cpp",
            (const char *)0x80080204LL,
            v42);
LABEL_29:
          SysFreeString(String1);
          SysFreeString(bstrString);
          Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v46);
          Node = v18;
          goto LABEL_72;
        }
        if ( a3 && (!String1 || wcscmp_0(String1, L"activateAsPackage")) )
        {
          Appx::Packaging::XmlLineInformation::GetXmlLineInformation(
            this[13],
            v46,
            0,
            0,
            (const unsigned __int16 *)&v45 + 2,
            (unsigned int *)&v45,
            v45);
          v18 = -2146958844;
          if ( (Microsoft_Windows_AppxPackagingOMEnableBits & 1) != 0 )
            McTemplateU0dqq_EventWriteTransfer(
              v20,
              (unsigned int)&EVENT_MANIFEST_INCORRECT_IDENTITYTYPE_FOR_RUNFULLTRUST,
              -2146958844,
              HIDWORD(v45),
              (char)v45);
          AppxPackagingLog(
            &EVENT_MANIFEST_INCORRECT_IDENTITYTYPE_FOR_RUNFULLTRUST,
            0xB00000EC,
            -2146958844,
            HIDWORD(v45),
            (unsigned int)v45);
          v19 = 3108;
          goto LABEL_28;
        }
        v51 = 0;
        if ( a4 )
        {
          v21 = Common::AutoStringWithAllocator<unsigned short,&unsigned short * Common::AutoBStrAllocateAndCopy(unsigned short const *,unsigned int),&void Common::AutoBStrDeallocate(unsigned short *)>::CopyFromString(
                  &v51,
                  a4);
          Node = v21;
          if ( v21 < 0 )
          {
            v22 = 3122;
            goto LABEL_39;
          }
        }
        else
        {
          v21 = Common::AutoStringWithAllocator<unsigned short,&unsigned short * Common::AutoBStrAllocateAndCopy(unsigned short const *,unsigned int),&void Common::AutoBStrDeallocate(unsigned short *)>::CopyFromString(
                  &v51,
                  L"mediumIL");
          Node = v21;
          if ( v21 < 0 )
          {
            v22 = 3118;
LABEL_39:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v22,
              (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestreader.cpp",
              (const char *)(unsigned int)v21,
              (int)v41);
LABEL_40:
            SysFreeString(v51);
            goto LABEL_20;
          }
        }
        v50 = 0;
        if ( a5 )
        {
          v23 = Common::AutoStringWithAllocator<unsigned short,&unsigned short * Common::AutoBStrAllocateAndCopy(unsigned short const *,unsigned int),&void Common::AutoBStrDeallocate(unsigned short *)>::CopyFromString(
                  &v50,
                  a5);
          Node = v23;
          if ( v23 < 0 )
          {
            v24 = 3133;
            goto LABEL_46;
          }
        }
        else
        {
          v23 = Common::AutoStringWithAllocator<unsigned short,&unsigned short * Common::AutoBStrAllocateAndCopy(unsigned short const *,unsigned int),&void Common::AutoBStrDeallocate(unsigned short *)>::CopyFromString(
                  &v50,
                  L"packagedClassicApp");
          Node = v23;
          if ( v23 < 0 )
          {
            v24 = 3129;
LABEL_46:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v24,
              (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestreader.cpp",
              (const char *)(unsigned int)v23,
              (int)v41);
            SysFreeString(v50);
            goto LABEL_40;
          }
        }
        v25 = v51;
        v26 = v50;
        if ( ((unsigned __int64)this[33] & 0xFFFFFFFFFFFF0000uLL) >= 0xA000047BA0000LL )
        {
          v27 = v51;
          do
          {
            v28 = *(BSTR)((char *)v27 + (char *)L"mediumIL" - (char *)v51);
            v29 = *v27 - v28;
            if ( v29 )
              break;
            ++v27;
          }
          while ( v28 );
          if ( v29 )
            goto LABEL_58;
          v30 = v50;
          do
          {
            v31 = *(BSTR)((char *)v30 + (char *)L"packagedClassicApp" - (char *)v50);
            v32 = *v30 - v31;
            if ( v32 )
              break;
            ++v30;
          }
          while ( v31 );
          if ( v32 )
          {
LABEL_58:
            v50 = 0;
            v33 = Appx::Packaging::ConvertVersionToString(
                    (Appx::Packaging *)0xA000047BA0000LL,
                    4u,
                    4u,
                    (unsigned int)&v50,
                    (unsigned __int16 **)v41);
            v18 = v33;
            if ( v33 >= 0 )
            {
              Appx::Packaging::XmlLineInformation::GetXmlLineInformation(
                this[13],
                v46,
                0,
                0,
                (const unsigned __int16 *)&v45 + 2,
                (unsigned int *)&v45,
                v45);
              v18 = -2146958844;
              v36 = v50;
              if ( (Microsoft_Windows_AppxPackagingOMEnableBits & 1) != 0 )
                McTemplateU0dqqz_EventWriteTransfer(
                  v35,
                  (unsigned int)&EVENT_MANIFEST_OUTOFPROCESSSERVER_NEED_TRUSTLEVEL_EQUALS_MEDIUMIL,
                  -2146958844,
                  HIDWORD(v45),
                  (char)v45,
                  (__int64)v50);
              AppxPackagingLog(
                &EVENT_MANIFEST_OUTOFPROCESSSERVER_NEED_TRUSTLEVEL_EQUALS_MEDIUMIL,
                0xB000010B,
                -2146958844,
                HIDWORD(v45),
                (unsigned int)v45,
                v36);
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xC48,
                (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestreader.cpp",
                (const char *)0x80080204LL,
                v44);
              operator delete(v36, v37);
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xC45,
                (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestreader.cpp",
                (const char *)(unsigned int)v33,
                v43);
              operator delete(v50, v34);
            }
            SysFreeString(v26);
            SysFreeString(v25);
            goto LABEL_29;
          }
        }
        SysFreeString(v50);
        SysFreeString(v25);
      }
    }
    v38 = String1;
    if ( !*((_BYTE *)this + 417) || !String1 || wcscmp_0(String1, L"activateAsPackage") )
    {
      SysFreeString(v38);
      SysFreeString(bstrString);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v46);
      Node = 0;
      goto LABEL_72;
    }
    Appx::Packaging::XmlLineInformation::GetXmlLineInformation(
      this[13],
      v46,
      0,
      L"IdentityType",
      (const unsigned __int16 *)&v45 + 2,
      (unsigned int *)&v45,
      v45);
    v18 = -2146958844;
    if ( (Microsoft_Windows_AppxPackagingOMEnableBits & 1) != 0 )
      McTemplateU0dqq_EventWriteTransfer(
        v39,
        (unsigned int)&EVENT_MANIFEST_OUTPROCESSSERVER_IDENTITYTYPE_ON_FRAMEWORK_PACKAGE,
        -2146958844,
        HIDWORD(v45),
        (char)v45);
    AppxPackagingLog(
      &EVENT_MANIFEST_OUTPROCESSSERVER_IDENTITYTYPE_ON_FRAMEWORK_PACKAGE,
      0xB0000127,
      -2146958844,
      HIDWORD(v45),
      (unsigned int)v45);
    v19 = 3153;
    goto LABEL_28;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xC0C,
    (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestreader.cpp",
    (const char *)(unsigned int)v12,
    (int)v41);
  SysFreeString(String1);
  SysFreeString(bstrString);
  v14 = v46;
  if ( v46 )
  {
    v46 = 0;
    (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v14 + 16LL))(v14);
  }
LABEL_72:
  SysFreeString(v52);
  return (unsigned int)Node;
}

```

## disassembly

```asm
0x1800605ec  push    rbp
0x1800605ee  push    rbx
0x1800605ef  push    rsi
0x1800605f0  push    rdi
0x1800605f1  push    r12
0x1800605f3  push    r14
0x1800605f5  push    r15
0x1800605f7  lea     rbp, [rsp-1Fh]
0x1800605fc  sub     rsp, 0A0h
0x180060603  mov     [rbp+4Fh+var_38], 0FFFFFFFFFFFFFFFEh
0x18006060b  mov     r15, r9
0x18006060e  mov     r14b, r8b
0x180060611  mov     rdi, rdx
0x180060614  mov     rsi, rcx
0x180060617  xor     r12d, r12d
0x18006061a  mov     [rbp+4Fh+var_9C], r12d
0x18006061e  mov     [rbp+4Fh+var_A0], r12d
0x180060622  mov     [rbp+4Fh+var_68], r12
0x180060626  mov     [rbp+4Fh+var_60], 3
0x18006062d  lea     rax, ?OutOfProcessServer@ElementNameWithoutPrefix@Manifest@Packaging@Appx@@3QBGB; "OutOfProcessServer"
0x180060634  mov     [rbp+4Fh+var_58], rax
0x180060638  mov     [rbp+4Fh+var_50], 12h
0x18006063f  lea     rax, asc_1801177B4; "']"
0x180060646  mov     [rbp+4Fh+var_48], rax
0x18006064a  mov     [rbp+4Fh+var_40], r12d
0x18006064e  lea     r8, [rbp+4Fh+var_68]; unsigned int
0x180060652  lea     edx, [r12+1]; struct Appx::Packaging::XPathComponent *
0x180060657  lea     rcx, [rbp+4Fh+var_60]; this
0x18006065b  call    ?BuildXPath@Packaging@Appx@@YAJPEBUXPathComponent@12@IAEAVAutoBStr@Common@@@Z; Appx::Packaging::BuildXPath(Appx::Packaging::XPathComponent const *,uint,Common::AutoBStr &)
0x180060660  mov     ebx, eax
0x180060662  test    eax, eax
0x180060664  jns     short loc_180060683
0x180060666  mov     rcx, [rbp+57h]; this
0x18006066a  mov     r9d, eax; char *
0x18006066d  lea     r8, aOnecorePrintsc_127; "onecore\\printscan\\appxpackaging\\mani"...
0x180060674  mov     edx, 0C04h; void *
0x180060679  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006067e  jmp     loc_180060CCE
0x180060683  mov     [rbp+4Fh+var_98], r12
0x180060687  lea     rcx, [rbp+4Fh+var_98]
0x18006068b  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180060690  mov     [rbp+4Fh+var_78], rdi
0x180060694  test    rdi, rdi
0x180060697  jz      short loc_1800606A8
0x180060699  mov     rax, [rdi]
0x18006069c  mov     rcx, rdi
0x18006069f  mov     rax, [rax+8]
0x1800606a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800606a8  lea     r8, [rbp+4Fh+var_98]
0x1800606ac  mov     rdx, [rbp+4Fh+var_68]
0x1800606b0  lea     rcx, [rbp+4Fh+var_78]
0x1800606b4  call    ?TryGetNode@Packaging@Appx@@YAJAEBV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@PEBGPEAPEAUIXMLDOMNode@@@Z; Appx::Packaging::TryGetNode(Microsoft::WRL::ComPtr<IXMLDOMNode> const &,ushort const *,IXMLDOMNode * *)
0x1800606b9  mov     ebx, eax
0x1800606bb  test    rdi, rdi
0x1800606be  jz      short loc_1800606CF
0x1800606c0  mov     rcx, [rdi]
0x1800606c3  mov     rax, [rcx+10h]
0x1800606c7  mov     rcx, rdi
0x1800606ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800606cf  test    ebx, ebx
0x1800606d1  jns     short loc_1800606F9
0x1800606d3  mov     rcx, [rbp+57h]; this
0x1800606d7  mov     r9d, ebx; char *
0x1800606da  lea     r8, aOnecorePrintsc_127; "onecore\\printscan\\appxpackaging\\mani"...
0x1800606e1  mov     edx, 0C06h; void *
0x1800606e6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800606eb  lea     rcx, [rbp+4Fh+var_98]
0x1800606ef  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800606f4  jmp     loc_180060CCE
0x1800606f9  mov     [rbp+4Fh+bstrString], r12
0x1800606fd  lea     r9, [rbp+4Fh+bstrString]
0x180060701  xor     r8d, r8d
0x180060704  lea     rdx, ?RunFullTrust@AttributeNameWithoutPrefix@Manifest@Packaging@Appx@@3QBGB; "RunFullTrust"
0x18006070b  lea     rcx, [rbp+4Fh+var_98]
0x18006070f  call    ?GetAttributeValue@Packaging@Appx@@YAJAEBV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@PEBGJPEAPEAG@Z; Appx::Packaging::GetAttributeValue(Microsoft::WRL::ComPtr<IXMLDOMNode> const &,ushort const *,long,ushort * *)
0x180060714  mov     ebx, eax
0x180060716  test    eax, eax
0x180060718  jns     short loc_180060744
0x18006071a  mov     rcx, [rbp+57h]; this
0x18006071e  mov     r9d, eax; char *
0x180060721  lea     r8, aOnecorePrintsc_127; "onecore\\printscan\\appxpackaging\\mani"...
0x180060728  mov     edx, 0C09h; void *
0x18006072d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180060732  mov     rcx, [rbp+4Fh+bstrString]; bstrString
0x180060736  call    cs:__imp_SysFreeString
0x18006073d  nop     dword ptr [rax+rax+00h]
0x180060742  jmp     short loc_1800606EB
0x180060744  mov     [rbp+4Fh+String1], r12
0x180060748  lea     r9, [rbp+4Fh+String1]
0x18006074c  xor     r8d, r8d
0x18006074f  lea     rdx, ?IdentityType@AttributeNameWithoutPrefix@Manifest@Packaging@Appx@@3QBGB; "IdentityType"
0x180060756  lea     rcx, [rbp+4Fh+var_98]
0x18006075a  call    ?GetAttributeValue@Packaging@Appx@@YAJAEBV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@PEBGJPEAPEAG@Z; Appx::Packaging::GetAttributeValue(Microsoft::WRL::ComPtr<IXMLDOMNode> const &,ushort const *,long,ushort * *)
0x18006075f  mov     ebx, eax
0x180060761  test    eax, eax
0x180060763  jns     short loc_1800607BF
0x180060765  mov     rcx, [rbp+57h]; this
0x180060769  mov     r9d, eax; char *
0x18006076c  lea     r8, aOnecorePrintsc_127; "onecore\\printscan\\appxpackaging\\mani"...
0x180060773  mov     edx, 0C0Ch; void *
0x180060778  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006077d  mov     rcx, [rbp+4Fh+String1]; bstrString
0x180060781  call    cs:__imp_SysFreeString
0x180060788  nop     dword ptr [rax+rax+00h]
0x18006078d  mov     rcx, [rbp+4Fh+bstrString]; bstrString
0x180060791  call    cs:__imp_SysFreeString
0x180060798  nop     dword ptr [rax+rax+00h]
0x18006079d  mov     rcx, [rbp+4Fh+var_98]
0x1800607a1  test    rcx, rcx
0x1800607a4  jz      loc_180060CCE
0x1800607aa  mov     [rbp+4Fh+var_98], r12
0x1800607ae  mov     rax, [rcx]
0x1800607b1  mov     rax, [rax+10h]
0x1800607b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800607ba  jmp     loc_180060CCE
0x1800607bf  mov     rcx, [rbp+4Fh+bstrString]; this
0x1800607c3  test    rcx, rcx
0x1800607c6  jz      loc_180060BFB
0x1800607cc  mov     dword ptr [rbp+4Fh+var_70], r12d
0x1800607d0  lea     r8, [rbp+4Fh+var_70]; int
0x1800607d4  xor     edx, edx; unsigned __int16 *
0x1800607d6  call    ?ConvertToBool@Packaging@Appx@@YAJPEAGHPEAH@Z; Appx::Packaging::ConvertToBool(ushort *,int,int *)
0x1800607db  mov     ebx, eax
0x1800607dd  test    eax, eax
0x1800607df  jns     short loc_18006080E
0x1800607e1  mov     edx, 0C11h; void *
0x1800607e6  lea     r8, aOnecorePrintsc_127; "onecore\\printscan\\appxpackaging\\mani"...
0x1800607ed  mov     r9d, eax; char *
0x1800607f0  mov     rcx, [rbp+57h]; this
0x1800607f4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800607f9  mov     rcx, [rbp+4Fh+String1]; bstrString
0x1800607fd  call    cs:__imp_SysFreeString
0x180060804  nop     dword ptr [rax+rax+00h]
0x180060809  jmp     loc_180060732
0x18006080e  cmp     dword ptr [rbp+4Fh+var_70], r12d
0x180060812  jz      loc_180060BFB
0x180060818  mov     [rbp+4Fh+var_90], r12b
0x18006081c  lea     r9, [rbp+4Fh+var_90]; bool *
0x180060820  mov     r8d, 2; enum APPX_CAPABILITY_CLASS_TYPE
0x180060826  lea     rdi, ?RestrictedCapabilityRunFullTrust@Value@Packaging@Appx@@3QBGB; "runFullTrust"
0x18006082d  mov     rdx, rdi; unsigned __int16 *
0x180060830  mov     rcx, rsi; this
0x180060833  call    ?ValidateCapability@AppxManifestReaderImpl@Manifest@Packaging@Appx@@AEAAJPEBGW4APPX_CAPABILITY_CLASS_TYPE@@PEA_N@Z; Appx::Packaging::Manifest::AppxManifestReaderImpl::ValidateCapability(ushort const *,APPX_CAPABILITY_CLASS_TYPE,bool *)
0x180060838  mov     ebx, eax
0x18006083a  test    eax, eax
0x18006083c  jns     short loc_180060845
0x18006083e  mov     edx, 0C16h
0x180060843  jmp     short loc_1800607E6
0x180060845  cmp     [rbp+4Fh+var_90], r12b
0x180060849  jnz     loc_18006090F
0x18006084f  lea     rax, [rbp+4Fh+var_A0]
0x180060853  mov     [rsp+0D0h+var_A8], rax; unsigned int *
0x180060858  lea     rax, [rbp+4Fh+var_9C]
0x18006085c  mov     [rsp+0D0h+var_B0], rax; unsigned __int16 *
0x180060861  xor     r9d, r9d; unsigned __int16 *
0x180060864  xor     r8d, r8d; struct IXMLDOMNode *
0x180060867  mov     rdx, [rbp+4Fh+var_98]; struct IStream *
0x18006086b  mov     rcx, [rsi+68h]; this
0x18006086f  call    ?GetXmlLineInformation@XmlLineInformation@Packaging@Appx@@YAJPEAUIStream@@PEAUIXMLDOMNode@@PEBG2PEAI3@Z; Appx::Packaging::XmlLineInformation::GetXmlLineInformation(IStream *,IXMLDOMNode *,ushort const *,ushort const *,uint *,uint *)
0x180060874  mov     r14d, 80080204h
0x18006087a  test    byte ptr cs:Microsoft_Windows_AppxPackagingOMEnableBits, 1
0x180060881  jz      short loc_1800608A2
0x180060883  mov     [rsp+0D0h+var_A8], rdi
0x180060888  mov     eax, [rbp+4Fh+var_A0]
0x18006088b  mov     dword ptr [rsp+0D0h+var_B0], eax
0x18006088f  mov     r9d, [rbp+4Fh+var_9C]
0x180060893  mov     r8d, r14d
0x180060896  lea     rdx, EVENT_MANIFEST_MISSING_CAPABILITY
0x18006089d  call    McTemplateU0dqqz_EventWriteTransfer
0x1800608a2  mov     [rsp+0D0h+var_A8], rdi; unsigned __int16 *
0x1800608a7  mov     eax, [rbp+4Fh+var_A0]
0x1800608aa  mov     dword ptr [rsp+0D0h+var_B0], eax; int
0x1800608ae  mov     r9d, [rbp+4Fh+var_9C]; unsigned int
0x1800608b2  mov     r8d, r14d; int
0x1800608b5  mov     edx, 0B00000BFh; unsigned int
0x1800608ba  lea     rcx, EVENT_MANIFEST_MISSING_CAPABILITY; struct _EVENT_DESCRIPTOR *
0x1800608c1  call    ?AppxPackagingLog@@YAJAEBU_EVENT_DESCRIPTOR@@KJIIPEBG@Z; AppxPackagingLog(_EVENT_DESCRIPTOR const &,ulong,long,uint,uint,ushort const *)
0x1800608c6  mov     edx, 0C1Bh; void *
0x1800608cb  mov     rcx, [rbp+57h]; this
0x1800608cf  mov     r9d, r14d; char *
0x1800608d2  lea     r8, aOnecorePrintsc_127; "onecore\\printscan\\appxpackaging\\mani"...
0x1800608d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800608de  mov     rcx, [rbp+4Fh+String1]; bstrString
0x1800608e2  call    cs:__imp_SysFreeString
0x1800608e9  nop     dword ptr [rax+rax+00h]
0x1800608ee  mov     rcx, [rbp+4Fh+bstrString]; bstrString
0x1800608f2  call    cs:__imp_SysFreeString
0x1800608f9  nop     dword ptr [rax+rax+00h]
0x1800608fe  lea     rcx, [rbp+4Fh+var_98]
0x180060902  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180060907  mov     ebx, r14d
0x18006090a  jmp     loc_180060CCE
0x18006090f  test    r14b, r14b
0x180060912  jz      loc_1800609A8
0x180060918  mov     rcx, [rbp+4Fh+String1]; String1
0x18006091c  test    rcx, rcx
0x18006091f  jz      short loc_180060931
0x180060921  lea     rdx, aActivateaspack; "activateAsPackage"
0x180060928  call    wcscmp_0
0x18006092d  test    eax, eax
0x18006092f  jz      short loc_1800609A8
0x180060931  lea     rax, [rbp+4Fh+var_A0]
0x180060935  mov     [rsp+0D0h+var_A8], rax; unsigned int *
0x18006093a  lea     rax, [rbp+4Fh+var_9C]
0x18006093e  mov     [rsp+0D0h+var_B0], rax; unsigned __int16 *
0x180060943  xor     r9d, r9d; unsigned __int16 *
0x180060946  xor     r8d, r8d; struct IXMLDOMNode *
0x180060949  mov     rdx, [rbp+4Fh+var_98]; struct IStream *
0x18006094d  mov     rcx, [rsi+68h]; this
0x180060951  call    ?GetXmlLineInformation@XmlLineInformation@Packaging@Appx@@YAJPEAUIStream@@PEAUIXMLDOMNode@@PEBG2PEAI3@Z; Appx::Packaging::XmlLineInformation::GetXmlLineInformation(IStream *,IXMLDOMNode *,ushort const *,ushort const *,uint *,uint *)
0x180060956  mov     r14d, 80080204h
0x18006095c  test    byte ptr cs:Microsoft_Windows_AppxPackagingOMEnableBits, 1
0x180060963  jz      short loc_18006097F
0x180060965  mov     eax, [rbp+4Fh+var_A0]
0x180060968  mov     dword ptr [rsp+0D0h+var_B0], eax
0x18006096c  mov     r9d, [rbp+4Fh+var_9C]
0x180060970  mov     r8d, r14d
0x180060973  lea     rdx, EVENT_MANIFEST_INCORRECT_IDENTITYTYPE_FOR_RUNFULLTRUST
0x18006097a  call    McTemplateU0dqq_EventWriteTransfer
0x18006097f  mov     eax, [rbp+4Fh+var_A0]
0x180060982  mov     dword ptr [rsp+0D0h+var_B0], eax; unsigned int
0x180060986  mov     r9d, [rbp+4Fh+var_9C]; unsigned int
0x18006098a  mov     r8d, r14d; int
0x18006098d  mov     edx, 0B00000ECh; unsigned int
0x180060992  lea     rcx, EVENT_MANIFEST_INCORRECT_IDENTITYTYPE_FOR_RUNFULLTRUST; struct _EVENT_DESCRIPTOR *
0x180060999  call    ?AppxPackagingLog@@YAJAEBU_EVENT_DESCRIPTOR@@KJII@Z; AppxPackagingLog(_EVENT_DESCRIPTOR const &,ulong,long,uint,uint)
0x18006099e  mov     edx, 0C24h
0x1800609a3  jmp     loc_1800608CB
0x1800609a8  mov     [rbp+4Fh+var_70], r12
0x1800609ac  lea     r14, ?TrustLevelMediumIL@Value@Packaging@Appx@@3QBGB; "mediumIL"
0x1800609b3  lea     rcx, [rbp+4Fh+var_70]
0x1800609b7  test    r15, r15
0x1800609ba  jnz     short loc_1800609F7
0x1800609bc  mov     rdx, r14
0x1800609bf  call    ?CopyFromString@?$AutoStringWithAllocator@G$1?AutoBStrAllocateAndCopy@Common@@YAPEAGPEBGI@Z$1?AutoBStrDeallocate@2@YAXPEAG@Z@Common@@QEAAJPEBG@Z; Common::AutoStringWithAllocator<ushort,&Common::AutoBStrAllocateAndCopy(ushort const *,uint),&Common::AutoBStrDeallocate(ushort *)>::CopyFromString(ushort const *)
0x1800609c4  mov     ebx, eax
0x1800609c6  test    eax, eax
0x1800609c8  jns     short loc_180060A0C
0x1800609ca  mov     edx, 0C2Eh; void *
0x1800609cf  lea     r8, aOnecorePrintsc_127; "onecore\\printscan\\appxpackaging\\mani"...
0x1800609d6  mov     r9d, eax; char *
0x1800609d9  mov     rcx, [rbp+57h]; this
0x1800609dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800609e2  mov     rcx, [rbp+4Fh+var_70]; bstrString
0x1800609e6  call    cs:__imp_SysFreeString
0x1800609ed  nop     dword ptr [rax+rax+00h]
0x1800609f2  jmp     loc_1800607F9
0x1800609f7  mov     rdx, r15
0x1800609fa  call    ?CopyFromString@?$AutoStringWithAllocator@G$1?AutoBStrAllocateAndCopy@Common@@YAPEAGPEBGI@Z$1?AutoBStrDeallocate@2@YAXPEAG@Z@Common@@QEAAJPEBG@Z; Common::AutoStringWithAllocator<ushort,&Common::AutoBStrAllocateAndCopy(ushort const *,uint),&Common::AutoBStrDeallocate(ushort *)>::CopyFromString(ushort const *)
0x1800609ff  mov     ebx, eax
0x180060a01  test    eax, eax
0x180060a03  jns     short loc_180060A0C
0x180060a05  mov     edx, 0C32h
0x180060a0a  jmp     short loc_1800609CF
0x180060a0c  mov     [rbp+4Fh+var_78], r12
0x180060a10  lea     r15, ?RuntimeBehaviorPackagedClassicApp@Value@Packaging@Appx@@3QBGB; "packagedClassicApp"
0x180060a17  mov     rdx, [rbp+4Fh+arg_20]
0x180060a1b  lea     rcx, [rbp+4Fh+var_78]
0x180060a1f  test    rdx, rdx
0x180060a22  jnz     short loc_180060A5C
0x180060a24  mov     rdx, r15
0x180060a27  call    ?CopyFromString@?$AutoStringWithAllocator@G$1?AutoBStrAllocateAndCopy@Common@@YAPEAGPEBGI@Z$1?AutoBStrDeallocate@2@YAXPEAG@Z@Common@@QEAAJPEBG@Z; Common::AutoStringWithAllocator<ushort,&Common::AutoBStrAllocateAndCopy(ushort const *,uint),&Common::AutoBStrDeallocate(ushort *)>::CopyFromString(ushort const *)
0x180060a2c  mov     ebx, eax
0x180060a2e  test    eax, eax
0x180060a30  jns     short loc_180060A6E
0x180060a32  mov     edx, 0C39h; void *
0x180060a37  lea     r8, aOnecorePrintsc_127; "onecore\\printscan\\appxpackaging\\mani"...
0x180060a3e  mov     r9d, eax; char *
0x180060a41  mov     rcx, [rbp+57h]; this
0x180060a45  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180060a4a  mov     rcx, [rbp+4Fh+var_78]; bstrString
0x180060a4e  call    cs:__imp_SysFreeString
0x180060a55  nop     dword ptr [rax+rax+00h]
0x180060a5a  jmp     short loc_1800609E2
0x180060a5c  call    ?CopyFromString@?$AutoStringWithAllocator@G$1?AutoBStrAllocateAndCopy@Common@@YAPEAGPEBGI@Z$1?AutoBStrDeallocate@2@YAXPEAG@Z@Common@@QEAAJPEBG@Z; Common::AutoStringWithAllocator<ushort,&Common::AutoBStrAllocateAndCopy(ushort const *,uint),&Common::AutoBStrDeallocate(ushort *)>::CopyFromString(ushort const *)
0x180060a61  mov     ebx, eax
0x180060a63  test    eax, eax
0x180060a65  jns     short loc_180060A6E
0x180060a67  mov     edx, 0C3Dh
0x180060a6c  jmp     short loc_180060A37
0x180060a6e  mov     rax, [rsi+108h]
0x180060a75  and     rax, 0FFFFFFFFFFFF0000h
0x180060a7b  mov     r10, 0A000047BA0000h
0x180060a85  mov     rdi, [rbp+4Fh+var_70]
0x180060a89  mov     rbx, [rbp+4Fh+var_78]
0x180060a8d  cmp     rax, r10
0x180060a90  jb      loc_180060BDD
0x180060a96  mov     rax, rdi
0x180060a99  sub     r14, rdi
0x180060a9c  movzx   ecx, word ptr [rax]
0x180060a9f  movzx   edx, word ptr [rax+r14]
0x180060aa4  sub     ecx, edx
0x180060aa6  jnz     short loc_180060AB0
0x180060aa8  add     rax, 2
0x180060aac  test    edx, edx
0x180060aae  jnz     short loc_180060A9C
0x180060ab0  test    ecx, ecx
0x180060ab2  jnz     short loc_180060AD6
0x180060ab4  mov     rax, rbx
0x180060ab7  sub     r15, rbx
  ... truncated ...
```
