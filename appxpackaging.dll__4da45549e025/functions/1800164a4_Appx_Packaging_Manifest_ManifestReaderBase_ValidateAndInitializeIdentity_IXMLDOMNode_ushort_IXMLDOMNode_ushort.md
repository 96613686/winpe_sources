# Appx::Packaging::Manifest::ManifestReaderBase::ValidateAndInitializeIdentity(IXMLDOMNode *,ushort *,IXMLDOMNode * *,ushort * *,ushort * *)

- ea: `0x1800164a4`
- end: `0x180016ac1`
- name: `?ValidateAndInitializeIdentity@ManifestReaderBase@Manifest@Packaging@Appx@@QEAAJPEAUIXMLDOMNode@@PEAGPEAPEAU5@PEAPEAG3@Z`
- size: `1565`
- prototype: `__int64 __fastcall(Appx::Packaging::Manifest::ManifestReaderBase *__hidden this, struct IXMLDOMNode *, unsigned __int16 *, struct IXMLDOMNode **, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800160e8`
- `0x1800199a4`
- `0x18002179c`

## callees

- `0x180005eb8`
- `0x180010f40`
- `0x1800133fc`
- `0x1800164a4`
- `0x18001711c`
- `0x18001733c`
- `0x180071f50`
- `0x180106010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016839`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800168d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016a61`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016a8e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016839`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800168d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016a61`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016a8e`
- `OLEAUT32!__imp_SysFreeString` at `0x18001665d`
- `OLEAUT32!__imp_SysFreeString` at `0x18001666c`
- `OLEAUT32!__imp_SysFreeString` at `0x18001667c`
- `OLEAUT32!__imp_SysFreeString` at `0x18001668b`
- `OLEAUT32!__imp_SysFreeString` at `0x180016854`
- `OLEAUT32!__imp_SysFreeString` at `0x180016863`
- `OLEAUT32!__imp_SysFreeString` at `0x180016873`
- `OLEAUT32!__imp_SysFreeString` at `0x180016882`
- `OLEAUT32!__imp_SysFreeString` at `0x180016980`
- `OLEAUT32!__imp_SysFreeString` at `0x18001698f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800169d7`
- `OLEAUT32!__imp_SysFreeString` at `0x18001665d`
- `OLEAUT32!__imp_SysFreeString` at `0x18001666c`
- `OLEAUT32!__imp_SysFreeString` at `0x18001667c`
- `OLEAUT32!__imp_SysFreeString` at `0x18001668b`
- `OLEAUT32!__imp_SysFreeString` at `0x180016854`
- `OLEAUT32!__imp_SysFreeString` at `0x180016863`
- `OLEAUT32!__imp_SysFreeString` at `0x180016873`
- `OLEAUT32!__imp_SysFreeString` at `0x180016882`
- `OLEAUT32!__imp_SysFreeString` at `0x180016980`
- `OLEAUT32!__imp_SysFreeString` at `0x18001698f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800169d7`
- `OLEAUT32!__imp_SysStringLen` at `0x1800165ba`
- `OLEAUT32!__imp_SysStringLen` at `0x1800167ce`
- `OLEAUT32!__imp_SysStringLen` at `0x1800165ba`
- `OLEAUT32!__imp_SysStringLen` at `0x1800167ce`

## string_xrefs

- `0x180016601`: `onecore\printscan\appxpackaging\manifest\src\manifestreaderbase.cpp`
- `0x180016645`: `onecore\printscan\appxpackaging\manifest\src\manifestreaderbase.cpp`
- `0x1800168e9`: `onecore\printscan\appxpackaging\manifest\src\manifestreaderbase.cpp`
- `0x180016921`: `onecore\printscan\appxpackaging\manifest\src\manifestreaderbase.cpp`
- `0x180016968`: `onecore\printscan\appxpackaging\manifest\src\manifestreaderbase.cpp`
- `0x1800169bf`: `onecore\printscan\appxpackaging\manifest\src\manifestreaderbase.cpp`
- `0x180016a49`: `onecore\printscan\appxpackaging\manifest\src\manifestreaderbase.cpp`
- `0x180016a76`: `onecore\printscan\appxpackaging\manifest\src\manifestreaderbase.cpp`
- `0x180016aa3`: `onecore\printscan\appxpackaging\manifest\src\manifestreaderbase.cpp`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::Manifest::ManifestReaderBase::ValidateAndInitializeIdentity(
        Appx::Packaging::Manifest::ManifestReaderBase *this,
        struct IXMLDOMNode *a2,
        unsigned __int16 *a3,
        struct IXMLDOMNode **a4,
        unsigned __int16 **a5,
        unsigned __int16 **a6)
{
  struct IXMLDOMNodeVtbl *lpVtbl; // rax
  HRESULT (__stdcall *selectSingleNode)(IXMLDOMNode *, BSTR, IXMLDOMNode **); // rbx
  int v12; // eax
  struct Common::AutoBStr *v13; // r9
  unsigned int v14; // ebx
  int v15; // eax
  unsigned int v16; // esi
  struct IXMLDOMNode *v17; // rsi
  HRESULT (__stdcall *v18)(IXMLDOMNode *, BSTR, IXMLDOMNode **); // rdi
  OLECHAR *v19; // rbx
  int v20; // eax
  int v21; // eax
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // rcx
  OLECHAR *v26; // rcx
  __int64 v28; // rcx
  int v29; // eax
  struct Common::AutoBStr *v30; // r9
  unsigned int v31; // edi
  int v32; // eax
  struct IXMLDOMNode *v33; // r14
  HRESULT (__stdcall *v34)(IXMLDOMNode *, BSTR, IXMLDOMNode **); // rsi
  OLECHAR *v35; // rdi
  int v36; // eax
  int v37; // eax
  __int64 v38; // rcx
  unsigned __int16 **v39; // r14
  unsigned __int16 **v40; // r14
  int v41; // eax
  struct IXMLDOMNode *v42; // rcx
  int v43; // eax
  struct IXMLDOMNode *v44; // rcx
  struct IXMLDOMNode *v45; // rcx
  __int64 v46; // [rsp+20h] [rbp-50h] BYREF
  BSTR pbstr; // [rsp+28h] [rbp-48h] BYREF
  BSTR bstrString; // [rsp+30h] [rbp-40h] BYREF
  BSTR v49; // [rsp+38h] [rbp-38h] BYREF
  int v50; // [rsp+40h] [rbp-30h] BYREF
  const unsigned __int16 *v51; // [rsp+48h] [rbp-28h]
  int v52; // [rsp+50h] [rbp-20h]
  const wchar_t *v53; // [rsp+58h] [rbp-18h]
  int v54; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]
  struct IXMLDOMNode *v56; // [rsp+A8h] [rbp+38h] BYREF

  lpVtbl = a2->lpVtbl;
  v56 = 0;
  selectSingleNode = lpVtbl->selectSingleNode;
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v56);
  v12 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, unsigned __int16 *, struct IXMLDOMNode **))selectSingleNode)(
          a2,
          a3,
          &v56);
  v14 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x7A,
      (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\manifestreaderbase.cpp",
      (const char *)(unsigned int)v12,
      v46);
    v44 = v56;
    if ( v56 )
    {
      v56 = 0;
      ((void (__fastcall *)(struct IXMLDOMNode *))v44->lpVtbl->Release)(v44);
    }
    return v14;
  }
  else
  {
    if ( !v56 )
    {
      v16 = -2147418113;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7B,
        (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\manifestreaderbase.cpp",
        (const char *)0x8000FFFFLL,
        v46);
      goto LABEL_22;
    }
    v49 = 0;
    v51 = L"Publisher";
    v50 = 5;
    v53 = L"']";
    v52 = 9;
    v54 = 0;
    v15 = Appx::Packaging::BuildXPath(
            (Appx::Packaging *)&v50,
            (const struct Appx::Packaging::XPathComponent *)1,
            (unsigned int)&v49,
            v13);
    v16 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x7E,
        (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\manifestreaderbase.cpp",
        (const char *)(unsigned int)v15,
        v46);
      v26 = v49;
      goto LABEL_21;
    }
    v17 = v56;
    v46 = 0;
    pbstr = 0;
    v18 = v56->lpVtbl->selectSingleNode;
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v46);
    v19 = v49;
    v20 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, BSTR, __int64 *))v18)(v17, v49, &v46);
    v16 = v20;
    if ( v20 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x4D,
        (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\valuehelper.cpp",
        (const char *)(unsigned int)v20,
        v46);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v46);
LABEL_13:
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x80,
        (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\manifestreaderbase.cpp",
        (const char *)v16,
        v46);
LABEL_20:
      SysFreeString(pbstr);
      v26 = v19;
LABEL_21:
      SysFreeString(v26);
LABEL_22:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v56);
      return v16;
    }
    if ( !v46 )
    {
      v22 = 79;
      goto LABEL_10;
    }
    v21 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v46 + 208LL))(v46, &pbstr);
    v16 = v21;
    if ( v21 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x51,
        (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\valuehelper.cpp",
        (const char *)(unsigned int)v21,
        v46);
LABEL_11:
      v23 = v46;
      if ( v46 )
      {
        v46 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
      }
      goto LABEL_13;
    }
    if ( !SysStringLen(pbstr) )
    {
      v22 = 84;
LABEL_10:
      v16 = -2147418113;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v22,
        (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\valuehelper.cpp",
        (const char *)0x8000FFFFLL,
        v46);
      goto LABEL_11;
    }
    v28 = v46;
    if ( v46 )
    {
      v46 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
    }
    v29 = Appx::Packaging::Manifest::ManifestReaderBase::ValidatePublisherAttribute(this, v56, pbstr);
    v31 = v29;
    if ( v29 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x81,
        (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\manifestreaderbase.cpp",
        (const char *)(unsigned int)v29,
        v46);
    }
    else
    {
      v49 = 0;
      v51 = L"Name";
      v50 = 5;
      v53 = L"']";
      v52 = 4;
      v54 = 0;
      v32 = Appx::Packaging::BuildXPath(
              (Appx::Packaging *)&v50,
              (const struct Appx::Packaging::XPathComponent *)1,
              (unsigned int)&v49,
              v30);
      v31 = v32;
      if ( v32 >= 0 )
      {
        v33 = v56;
        v46 = 0;
        bstrString = 0;
        v34 = v56->lpVtbl->selectSingleNode;
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v46);
        v35 = v49;
        v36 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, BSTR, __int64 *))v34)(v33, v49, &v46);
        v16 = v36;
        if ( v36 < 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x4D,
            (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\valuehelper.cpp",
            (const char *)(unsigned int)v36,
            v46);
          Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v46);
LABEL_18:
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x86,
            (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\manifestreaderbase.cpp",
            (const char *)v16,
            v46);
LABEL_19:
          SysFreeString(bstrString);
          SysFreeString(v35);
          goto LABEL_20;
        }
        if ( !v46 )
        {
          v24 = 79;
LABEL_15:
          v16 = -2147418113;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v24,
            (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\valuehelper.cpp",
            (const char *)0x8000FFFFLL,
            v46);
          goto LABEL_16;
        }
        v37 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v46 + 208LL))(v46, &bstrString);
        v16 = v37;
        if ( v37 < 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x51,
            (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\valuehelper.cpp",
            (const char *)(unsigned int)v37,
            v46);
LABEL_16:
          v25 = v46;
          if ( v46 )
          {
            v46 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
          }
          goto LABEL_18;
        }
        if ( !SysStringLen(bstrString) )
        {
          v24 = 84;
          goto LABEL_15;
        }
        v38 = v46;
        if ( v46 )
        {
          v46 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
        }
        v39 = a5;
        if ( a5 )
        {
          v49 = 0;
          v43 = Common::AutoStringWithAllocator<unsigned short,&unsigned short * Common::AutoCoTaskMemStringAllocateAndCopy(unsigned short const *,unsigned int),&void Common::AutoCoTaskMemStringDeallocate(unsigned short *)>::CopyFromBStr(
                  &v49,
                  bstrString);
          v16 = v43;
          if ( v43 < 0 )
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x8C,
              (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\manifestreaderbase.cpp",
              (const char *)(unsigned int)v43,
              v46);
            CoTaskMemFree(v49);
            goto LABEL_40;
          }
          *v39 = v49;
          CoTaskMemFree(0);
        }
        v40 = a6;
        if ( a6 )
        {
          v49 = 0;
          v41 = Common::AutoStringWithAllocator<unsigned short,&unsigned short * Common::AutoCoTaskMemStringAllocateAndCopy(unsigned short const *,unsigned int),&void Common::AutoCoTaskMemStringDeallocate(unsigned short *)>::CopyFromBStr(
                  &v49,
                  pbstr);
          v16 = v41;
          if ( v41 < 0 )
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x93,
              (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\manifestreaderbase.cpp",
              (const char *)(unsigned int)v41,
              v46);
            CoTaskMemFree(v49);
            goto LABEL_19;
          }
          *v40 = v49;
          CoTaskMemFree(0);
        }
        *a4 = v56;
        v56 = 0;
LABEL_40:
        SysFreeString(bstrString);
        SysFreeString(v35);
        SysFreeString(pbstr);
        SysFreeString(v19);
        v42 = v56;
        if ( v56 )
        {
          v56 = 0;
          ((void (__fastcall *)(struct IXMLDOMNode *))v42->lpVtbl->Release)(v42);
        }
        return v16;
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x84,
        (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\manifestreaderbase.cpp",
        (const char *)(unsigned int)v32,
        v46);
      SysFreeString(v49);
    }
    SysFreeString(pbstr);
    SysFreeString(v19);
    v45 = v56;
    if ( v56 )
    {
      v56 = 0;
      ((void (__fastcall *)(struct IXMLDOMNode *))v45->lpVtbl->Release)(v45);
    }
    return v31;
  }
}

```

## disassembly

```asm
0x1800164a4  mov     [rsp-28h+arg_0], rbx
0x1800164a9  mov     [rsp-28h+arg_10], rsi
0x1800164ae  push    rbp
0x1800164af  push    rdi
0x1800164b0  push    r12
0x1800164b2  push    r14
0x1800164b4  push    r15
0x1800164b6  mov     rbp, rsp
0x1800164b9  sub     rsp, 70h
0x1800164bd  mov     rax, [rdx]
0x1800164c0  mov     r14, rcx
0x1800164c3  xor     r12d, r12d
0x1800164c6  lea     rcx, [rbp+arg_8]
0x1800164ca  mov     r15, r9
0x1800164cd  mov     [rbp+arg_8], r12
0x1800164d1  mov     rdi, r8
0x1800164d4  mov     rsi, rdx
0x1800164d7  mov     rbx, [rax+128h]
0x1800164de  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800164e3  lea     r8, [rbp+arg_8]
0x1800164e7  mov     rdx, rdi
0x1800164ea  mov     rcx, rsi
0x1800164ed  mov     rax, rbx
0x1800164f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800164f5  mov     ebx, eax
0x1800164f7  test    eax, eax
0x1800164f9  js      loc_1800168E5
0x1800164ff  cmp     [rbp+arg_8], r12
0x180016503  jz      loc_180016A9F
0x180016509  lea     rax, ?Publisher@AttributeNameWithoutPrefix@Manifest@Packaging@Appx@@3QBGB; "Publisher"
0x180016510  mov     [rbp+var_38], r12
0x180016514  mov     [rbp+var_28], rax
0x180016518  lea     r8, [rbp+var_38]; unsigned int
0x18001651c  lea     rax, asc_1801177B4; "']"
0x180016523  mov     [rbp+var_30], 5
0x18001652a  lea     edx, [r12+1]; struct Appx::Packaging::XPathComponent *
0x18001652f  mov     [rbp+var_18], rax
0x180016533  lea     rcx, [rbp+var_30]; this
0x180016537  mov     [rbp+var_20], 9
0x18001653e  mov     [rbp+var_10], r12d
0x180016542  call    ?BuildXPath@Packaging@Appx@@YAJPEBUXPathComponent@12@IAEAVAutoBStr@Common@@@Z; Appx::Packaging::BuildXPath(Appx::Packaging::XPathComponent const *,uint,Common::AutoBStr &)
0x180016547  mov     esi, eax
0x180016549  test    eax, eax
0x18001654b  js      loc_18001691D
0x180016551  mov     rsi, [rbp+arg_8]
0x180016555  lea     rcx, [rbp+var_50]
0x180016559  mov     [rbp+var_50], r12
0x18001655d  mov     [rbp+pbstr], r12
0x180016561  mov     rax, [rsi]
0x180016564  mov     rdi, [rax+128h]
0x18001656b  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180016570  mov     rbx, [rbp+var_38]
0x180016574  lea     r8, [rbp+var_50]
0x180016578  mov     rdx, rbx
0x18001657b  mov     rcx, rsi
0x18001657e  mov     rax, rdi
0x180016581  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016586  mov     esi, eax
0x180016588  test    eax, eax
0x18001658a  js      loc_18001693E
0x180016590  mov     rcx, [rbp+var_50]
0x180016594  test    rcx, rcx
0x180016597  jz      short loc_1800165D3
0x180016599  mov     rax, [rcx]
0x18001659c  lea     rdx, [rbp+pbstr]
0x1800165a0  mov     rax, [rax+0D0h]
0x1800165a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800165ac  mov     esi, eax
0x1800165ae  test    eax, eax
0x1800165b0  js      loc_180016A0B
0x1800165b6  mov     rcx, [rbp+pbstr]; pbstr
0x1800165ba  call    cs:__imp_SysStringLen
0x1800165c1  nop     dword ptr [rax+rax+00h]
0x1800165c6  test    eax, eax
0x1800165c8  jnz     loc_1800166E6
0x1800165ce  lea     edx, [rax+54h]
0x1800165d1  jmp     short loc_1800165D8
0x1800165d3  mov     edx, 4Fh ; 'O'; void *
0x1800165d8  mov     rcx, [rbp+28h]; this
0x1800165dc  lea     r8, aOnecorePrintsc_100; "onecore\\printscan\\appxpackaging\\lib"...
0x1800165e3  mov     esi, 8000FFFFh
0x1800165e8  mov     r9d, esi; char *
0x1800165eb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800165f0  mov     rcx, [rbp+var_50]
0x1800165f4  test    rcx, rcx
0x1800165f7  jnz     loc_1800166BC
0x1800165fd  mov     rcx, [rbp+28h]; this
0x180016601  lea     r8, aOnecorePrintsc_124; "onecore\\printscan\\appxpackaging\\mani"...
0x180016608  mov     r9d, esi; char *
0x18001660b  mov     edx, 80h; void *
0x180016610  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180016615  jmp     short loc_180016678
0x180016617  mov     edx, 4Fh ; 'O'; void *
0x18001661c  mov     rcx, [rbp+28h]; this
0x180016620  lea     r8, aOnecorePrintsc_100; "onecore\\printscan\\appxpackaging\\lib"...
0x180016627  mov     esi, 8000FFFFh
0x18001662c  mov     r9d, esi; char *
0x18001662f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016634  mov     rcx, [rbp+var_50]
0x180016638  test    rcx, rcx
0x18001663b  jnz     loc_1800166D1
0x180016641  mov     rcx, [rbp+28h]; this
0x180016645  lea     r8, aOnecorePrintsc_124; "onecore\\printscan\\appxpackaging\\mani"...
0x18001664c  mov     r9d, esi; char *
0x18001664f  mov     edx, 86h; void *
0x180016654  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180016659  mov     rcx, [rbp+bstrString]; bstrString
0x18001665d  call    cs:__imp_SysFreeString
0x180016664  nop     dword ptr [rax+rax+00h]
0x180016669  mov     rcx, rdi; bstrString
0x18001666c  call    cs:__imp_SysFreeString
0x180016673  nop     dword ptr [rax+rax+00h]
0x180016678  mov     rcx, [rbp+pbstr]; bstrString
0x18001667c  call    cs:__imp_SysFreeString
0x180016683  nop     dword ptr [rax+rax+00h]
0x180016688  mov     rcx, rbx; bstrString
0x18001668b  call    cs:__imp_SysFreeString
0x180016692  nop     dword ptr [rax+rax+00h]
0x180016697  lea     rcx, [rbp+arg_8]
0x18001669b  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800166a0  mov     eax, esi
0x1800166a2  lea     r11, [rsp+70h+var_s0]
0x1800166a7  mov     rbx, [r11+30h]
0x1800166ab  mov     rsi, [r11+40h]
0x1800166af  mov     rsp, r11
0x1800166b2  pop     r15
0x1800166b4  pop     r14
0x1800166b6  pop     r12
0x1800166b8  pop     rdi
0x1800166b9  pop     rbp
0x1800166ba  retn
0x1800166bc  mov     [rbp+var_50], r12
0x1800166c0  mov     rax, [rcx]
0x1800166c3  mov     rax, [rax+10h]
0x1800166c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800166cc  jmp     loc_1800165FD
0x1800166d1  mov     [rbp+var_50], r12
0x1800166d5  mov     rax, [rcx]
0x1800166d8  mov     rax, [rax+10h]
0x1800166dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800166e1  jmp     loc_180016641
0x1800166e6  mov     rcx, [rbp+var_50]
0x1800166ea  test    rcx, rcx
0x1800166ed  jz      short loc_1800166FF
0x1800166ef  mov     [rbp+var_50], r12
0x1800166f3  mov     rax, [rcx]
0x1800166f6  mov     rax, [rax+10h]
0x1800166fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800166ff  mov     r8, [rbp+pbstr]; unsigned __int16 *
0x180016703  mov     rcx, r14; this
0x180016706  mov     rdx, [rbp+arg_8]; struct IXMLDOMNode *
0x18001670a  call    ?ValidatePublisherAttribute@ManifestReaderBase@Manifest@Packaging@Appx@@AEAAJPEAUIXMLDOMNode@@PEBG@Z; Appx::Packaging::Manifest::ManifestReaderBase::ValidatePublisherAttribute(IXMLDOMNode *,ushort const *)
0x18001670f  mov     edi, eax
0x180016711  test    eax, eax
0x180016713  js      loc_180016964
0x180016719  lea     rax, ?Name@AttributeNameWithoutPrefix@Manifest@Packaging@Appx@@3QBGB; "Name"
0x180016720  mov     [rbp+var_38], r12
0x180016724  mov     [rbp+var_28], rax
0x180016728  lea     r8, [rbp+var_38]; unsigned int
0x18001672c  lea     rax, asc_1801177B4; "']"
0x180016733  mov     [rbp+var_30], 5
0x18001673a  mov     edx, 1; struct Appx::Packaging::XPathComponent *
0x18001673f  mov     [rbp+var_18], rax
0x180016743  lea     rcx, [rbp+var_30]; this
0x180016747  mov     [rbp+var_20], 4
0x18001674e  mov     [rbp+var_10], r12d
0x180016752  call    ?BuildXPath@Packaging@Appx@@YAJPEBUXPathComponent@12@IAEAVAutoBStr@Common@@@Z; Appx::Packaging::BuildXPath(Appx::Packaging::XPathComponent const *,uint,Common::AutoBStr &)
0x180016757  mov     edi, eax
0x180016759  test    eax, eax
0x18001675b  js      loc_1800169BB
0x180016761  mov     r14, [rbp+arg_8]
0x180016765  lea     rcx, [rbp+var_50]
0x180016769  mov     [rbp+var_50], r12
0x18001676d  mov     [rbp+bstrString], r12
0x180016771  mov     rax, [r14]
0x180016774  mov     rsi, [rax+128h]
0x18001677b  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180016780  mov     rdi, [rbp+var_38]
0x180016784  lea     r8, [rbp+var_50]
0x180016788  mov     rdx, rdi
0x18001678b  mov     rcx, r14
0x18001678e  mov     rax, rsi
0x180016791  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016796  mov     esi, eax
0x180016798  test    eax, eax
0x18001679a  js      loc_1800169E5
0x1800167a0  mov     rcx, [rbp+var_50]
0x1800167a4  test    rcx, rcx
0x1800167a7  jz      loc_180016617
0x1800167ad  mov     rax, [rcx]
0x1800167b0  lea     rdx, [rbp+bstrString]
0x1800167b4  mov     rax, [rax+0D0h]
0x1800167bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800167c0  mov     esi, eax
0x1800167c2  test    eax, eax
0x1800167c4  js      loc_180016A28
0x1800167ca  mov     rcx, [rbp+bstrString]; pbstr
0x1800167ce  call    cs:__imp_SysStringLen
0x1800167d5  nop     dword ptr [rax+rax+00h]
0x1800167da  test    eax, eax
0x1800167dc  jnz     short loc_1800167E6
0x1800167de  lea     edx, [rax+54h]
0x1800167e1  jmp     loc_18001661C
0x1800167e6  mov     rcx, [rbp+var_50]
0x1800167ea  test    rcx, rcx
0x1800167ed  jz      short loc_1800167FF
0x1800167ef  mov     [rbp+var_50], r12
0x1800167f3  mov     rax, [rcx]
0x1800167f6  mov     rax, [rax+10h]
0x1800167fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800167ff  mov     r14, [rbp+arg_20]
0x180016803  test    r14, r14
0x180016806  jnz     loc_1800168B0
0x18001680c  mov     r14, [rbp+arg_28]
0x180016810  test    r14, r14
0x180016813  jz      short loc_180016845
0x180016815  mov     rdx, [rbp+pbstr]
0x180016819  lea     rcx, [rbp+var_38]
0x18001681d  mov     [rbp+var_38], r12
0x180016821  call    ?CopyFromBStr@?$AutoStringWithAllocator@G$1?AutoCoTaskMemStringAllocateAndCopy@Common@@YAPEAGPEBGI@Z$1?AutoCoTaskMemStringDeallocate@2@YAXPEAG@Z@Common@@QEAAJQEAG@Z; Common::AutoStringWithAllocator<ushort,&Common::AutoCoTaskMemStringAllocateAndCopy(ushort const *,uint),&Common::AutoCoTaskMemStringDeallocate(ushort *)>::CopyFromBStr(ushort * const)
0x180016826  mov     esi, eax
0x180016828  test    eax, eax
0x18001682a  js      loc_180016A45
0x180016830  mov     rax, [rbp+var_38]
0x180016834  xor     ecx, ecx; pv
0x180016836  mov     [r14], rax
0x180016839  call    cs:__imp_CoTaskMemFree
0x180016840  nop     dword ptr [rax+rax+00h]
0x180016845  mov     rax, [rbp+arg_8]
0x180016849  mov     [r15], rax
0x18001684c  mov     [rbp+arg_8], r12
0x180016850  mov     rcx, [rbp+bstrString]; bstrString
0x180016854  call    cs:__imp_SysFreeString
0x18001685b  nop     dword ptr [rax+rax+00h]
0x180016860  mov     rcx, rdi; bstrString
0x180016863  call    cs:__imp_SysFreeString
0x18001686a  nop     dword ptr [rax+rax+00h]
0x18001686f  mov     rcx, [rbp+pbstr]; bstrString
0x180016873  call    cs:__imp_SysFreeString
0x18001687a  nop     dword ptr [rax+rax+00h]
0x18001687f  mov     rcx, rbx; bstrString
0x180016882  call    cs:__imp_SysFreeString
0x180016889  nop     dword ptr [rax+rax+00h]
0x18001688e  mov     rcx, [rbp+arg_8]
0x180016892  test    rcx, rcx
0x180016895  jz      loc_1800166A0
0x18001689b  mov     [rbp+arg_8], r12
0x18001689f  mov     rax, [rcx]
0x1800168a2  mov     rax, [rax+10h]
0x1800168a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800168ab  jmp     loc_1800166A0
0x1800168b0  mov     rdx, [rbp+bstrString]
0x1800168b4  lea     rcx, [rbp+var_38]
0x1800168b8  mov     [rbp+var_38], r12
0x1800168bc  call    ?CopyFromBStr@?$AutoStringWithAllocator@G$1?AutoCoTaskMemStringAllocateAndCopy@Common@@YAPEAGPEBGI@Z$1?AutoCoTaskMemStringDeallocate@2@YAXPEAG@Z@Common@@QEAAJQEAG@Z; Common::AutoStringWithAllocator<ushort,&Common::AutoCoTaskMemStringAllocateAndCopy(ushort const *,uint),&Common::AutoCoTaskMemStringDeallocate(ushort *)>::CopyFromBStr(ushort * const)
0x1800168c1  mov     esi, eax
0x1800168c3  test    eax, eax
0x1800168c5  js      loc_180016A72
0x1800168cb  mov     rax, [rbp+var_38]
0x1800168cf  xor     ecx, ecx; pv
0x1800168d1  mov     [r14], rax
0x1800168d4  call    cs:__imp_CoTaskMemFree
0x1800168db  nop     dword ptr [rax+rax+00h]
0x1800168e0  jmp     loc_18001680C
0x1800168e5  mov     rcx, [rbp+28h]; this
0x1800168e9  lea     r8, aOnecorePrintsc_124; "onecore\\printscan\\appxpackaging\\mani"...
0x1800168f0  mov     r9d, ebx; char *
0x1800168f3  mov     edx, 7Ah ; 'z'; void *
0x1800168f8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800168fd  mov     rcx, [rbp+arg_8]
0x180016901  test    rcx, rcx
0x180016904  jz      short loc_180016916
0x180016906  mov     [rbp+arg_8], r12
0x18001690a  mov     rax, [rcx]
0x18001690d  mov     rax, [rax+10h]
0x180016911  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016916  mov     eax, ebx
0x180016918  jmp     loc_1800166A2
0x18001691d  mov     rcx, [rbp+28h]; this
0x180016921  lea     r8, aOnecorePrintsc_124; "onecore\\printscan\\appxpackaging\\mani"...
0x180016928  mov     r9d, eax; char *
0x18001692b  mov     edx, 7Eh ; '~'; void *
0x180016930  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180016935  mov     rcx, [rbp+var_38]
0x180016939  jmp     loc_18001668B
0x18001693e  mov     rcx, [rbp+28h]; this
0x180016942  lea     r8, aOnecorePrintsc_100; "onecore\\printscan\\appxpackaging\\lib"...
0x180016949  mov     r9d, eax; char *
0x18001694c  mov     edx, 4Dh ; 'M'; void *
0x180016951  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180016956  lea     rcx, [rbp+var_50]
0x18001695a  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18001695f  jmp     loc_1800165FD
0x180016964  mov     rcx, [rbp+28h]; this
0x180016968  lea     r8, aOnecorePrintsc_124; "onecore\\printscan\\appxpackaging\\mani"...
0x18001696f  mov     r9d, edi; char *
0x180016972  mov     edx, 81h; void *
0x180016977  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001697c  mov     rcx, [rbp+pbstr]; bstrString
0x180016980  call    cs:__imp_SysFreeString
  ... truncated ...
```
