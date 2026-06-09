# Appx::Packaging::Manifest::AppxManifestReaderImpl::ValidateUniqueWebAccountProviderURLs(void)

- ea: `0x1800554a8`
- end: `0x180055c09`
- name: `?ValidateUniqueWebAccountProviderURLs@AppxManifestReaderImpl@Manifest@Packaging@Appx@@AEAAJXZ`
- size: `1889`
- prototype: `__int64 __fastcall(Appx::Packaging::Manifest::AppxManifestReaderImpl *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180022400`

## callees

- `0x1800029e4`
- `0x180005eb8`
- `0x180010f40`
- `0x1800133fc`
- `0x18001b270`
- `0x18001c77c`
- `0x180033b64`
- `0x1800554a8`
- `0x1800992d0`
- `0x1800d68a8`
- `0x180106010`

## import_xrefs

- `ntdll!RtlInitializeGenericTableAvl` at `0x18005551b`
- `ntdll!RtlInitializeGenericTableAvl` at `0x18005551b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800555af`
- `OLEAUT32!__imp_SysFreeString` at `0x180055792`
- `OLEAUT32!__imp_SysFreeString` at `0x1800557a2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800557b1`
- `OLEAUT32!__imp_SysFreeString` at `0x180055894`
- `OLEAUT32!__imp_SysFreeString` at `0x1800558db`
- `OLEAUT32!__imp_SysFreeString` at `0x18005591a`
- `OLEAUT32!__imp_SysFreeString` at `0x180055929`
- `OLEAUT32!__imp_SysFreeString` at `0x180055990`
- `OLEAUT32!__imp_SysFreeString` at `0x1800559a0`
- `OLEAUT32!__imp_SysFreeString` at `0x180055a14`
- `OLEAUT32!__imp_SysFreeString` at `0x180055a2c`
- `OLEAUT32!__imp_SysFreeString` at `0x180055a3c`
- `OLEAUT32!__imp_SysFreeString` at `0x180055a4b`
- `OLEAUT32!__imp_SysFreeString` at `0x180055b0b`
- `OLEAUT32!__imp_SysFreeString` at `0x180055b4d`
- `OLEAUT32!__imp_SysFreeString` at `0x180055b88`
- `OLEAUT32!__imp_SysFreeString` at `0x180055ba0`
- `OLEAUT32!__imp_SysFreeString` at `0x180055bb0`
- `OLEAUT32!__imp_SysFreeString` at `0x180055bbf`
- `OLEAUT32!__imp_SysFreeString` at `0x180055bf1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800555af`
- `OLEAUT32!__imp_SysFreeString` at `0x180055792`
- `OLEAUT32!__imp_SysFreeString` at `0x1800557a2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800557b1`
- `OLEAUT32!__imp_SysFreeString` at `0x180055894`
- `OLEAUT32!__imp_SysFreeString` at `0x1800558db`
- `OLEAUT32!__imp_SysFreeString` at `0x18005591a`
- `OLEAUT32!__imp_SysFreeString` at `0x180055929`
- `OLEAUT32!__imp_SysFreeString` at `0x180055990`
- `OLEAUT32!__imp_SysFreeString` at `0x1800559a0`
- `OLEAUT32!__imp_SysFreeString` at `0x180055a14`
- `OLEAUT32!__imp_SysFreeString` at `0x180055a2c`
- `OLEAUT32!__imp_SysFreeString` at `0x180055a3c`
- `OLEAUT32!__imp_SysFreeString` at `0x180055a4b`
- `OLEAUT32!__imp_SysFreeString` at `0x180055b0b`
- `OLEAUT32!__imp_SysFreeString` at `0x180055b4d`
- `OLEAUT32!__imp_SysFreeString` at `0x180055b88`
- `OLEAUT32!__imp_SysFreeString` at `0x180055ba0`
- `OLEAUT32!__imp_SysFreeString` at `0x180055bb0`
- `OLEAUT32!__imp_SysFreeString` at `0x180055bbf`
- `OLEAUT32!__imp_SysFreeString` at `0x180055bf1`

## string_xrefs

- `0x1800555de`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestreader.cpp`
- `0x18005560d`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestreader.cpp`
- `0x1800557e3`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestreader.cpp`
- `0x18005587c`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestreader.cpp`
- `0x1800558a9`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestreader.cpp`
- `0x1800558c3`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestreader.cpp`
- `0x180055902`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestreader.cpp`
- `0x180055952`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestreader.cpp`
- `0x180055970`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestreader.cpp`
- `0x1800559f4`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestreader.cpp`
- `0x180055b3a`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestreader.cpp`
- `0x180055b5f`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestreader.cpp`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::Manifest::AppxManifestReaderImpl::ValidateUniqueWebAccountProviderURLs(
        Appx::Packaging::Manifest::AppxManifestReaderImpl *this)
{
  struct _RTL_AVL_TABLE *v2; // rax
  struct Common::AutoBStr *v3; // r9
  struct _RTL_AVL_TABLE *v4; // r13
  int v5; // eax
  unsigned int v6; // ebx
  int NodesList; // eax
  int v8; // r12d
  __int64 v9; // r15
  __int64 (__fastcall *v11)(__int64, OLECHAR **); // rbx
  int v12; // eax
  struct Common::AutoBStr *v13; // r9
  int v14; // eax
  OLECHAR *v15; // rbx
  OLECHAR *v16; // rdi
  int RequiredNodeValue; // esi
  struct Common::AutoBStr *v18; // r9
  int v19; // eax
  OLECHAR *v20; // r14
  __int64 (__fastcall *v21)(OLECHAR *, BSTR, __int64 *); // rbx
  OLECHAR *v22; // rsi
  __int64 v23; // rcx
  OLECHAR *v24; // rcx
  int v25; // eax
  struct Common::AutoBStr *v26; // r9
  int v27; // eax
  OLECHAR *v28; // rcx
  OLECHAR *v29; // rcx
  OLECHAR *v30; // rbx
  int v31; // eax
  int v32; // r14d
  __int64 v33; // r14
  int i; // eax
  __int64 (__fastcall *v35)(__int64, __int64 *); // r15
  int v36; // eax
  int v37; // r15d
  __int64 v38; // rdx
  int TableContext; // [rsp+20h] [rbp-69h]
  PVOID TableContexta; // [rsp+20h] [rbp-69h]
  OLECHAR *v41; // [rsp+30h] [rbp-59h] BYREF
  __int64 v42; // [rsp+38h] [rbp-51h] BYREF
  __int64 v43; // [rsp+40h] [rbp-49h] BYREF
  BSTR v44; // [rsp+48h] [rbp-41h] BYREF
  __int64 v45; // [rsp+50h] [rbp-39h] BYREF
  __int64 v46; // [rsp+58h] [rbp-31h] BYREF
  BSTR v47; // [rsp+60h] [rbp-29h] BYREF
  BSTR bstrString; // [rsp+68h] [rbp-21h] BYREF
  int v49; // [rsp+70h] [rbp-19h] BYREF
  const unsigned __int16 *v50; // [rsp+78h] [rbp-11h]
  int v51; // [rsp+80h] [rbp-9h]
  const wchar_t *v52; // [rsp+88h] [rbp-1h]
  int v53; // [rsp+90h] [rbp+7h]
  _QWORD v54[9]; // [rsp+98h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]
  int v57; // [rsp+F8h] [rbp+6Fh] BYREF
  BSTR v58; // [rsp+100h] [rbp+77h] BYREF
  BSTR v59; // [rsp+108h] [rbp+7Fh] BYREF

  v2 = (struct _RTL_AVL_TABLE *)operator new(0x78u, (const struct std::nothrow_t *)&std::nothrow);
  v4 = v2;
  if ( v2 )
  {
    v2[1].BalancedRoot.Parent = (struct _RTL_BALANCED_LINKS *)Common::AutoBStrDeallocate;
    v2[1].BalancedRoot.LeftChild = (struct _RTL_BALANCED_LINKS *)Common::DeallocateCom<IAppxFile *>;
    RtlInitializeGenericTableAvl(
      v2,
      Common::GenericMapCaseInsensitiveCompare,
      Common::GenericMap<unsigned short *,void *>::GenericMapAllocate,
      Common::GenericMap<unsigned short const *,Appx::Packaging::Bitmap *>::GenericMapFree,
      0);
  }
  else
  {
    v4 = 0;
  }
  bstrString = 0;
  v5 = Appx::Packaging::BuildXPath(
         (Appx::Packaging *)&qword_18010B920,
         (const struct Appx::Packaging::XPathComponent *)5,
         &bstrString,
         v3);
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A9C,
      (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestreader.cpp",
      (const char *)(unsigned int)v5,
      TableContext);
    goto LABEL_9;
  }
  v42 = 0;
  v57 = 0;
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v42);
  TableContexta = &v57;
  NodesList = Appx::Packaging::GetNodesList((char *)this + 128, bstrString, 0, &v42);
  v6 = NodesList;
  if ( NodesList >= 0 )
  {
    v8 = 0;
    v9 = v42;
    if ( v57 <= 0 )
    {
LABEL_6:
      if ( v9 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      v6 = v8;
      goto LABEL_9;
    }
    v41 = 0;
    v11 = *(__int64 (__fastcall **)(__int64, OLECHAR **))(*(_QWORD *)v42 + 72LL);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v41);
    v12 = v11(v9, &v41);
    v6 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1AA7,
        (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestreader.cpp",
        (const char *)(unsigned int)v12,
        (int)&v57);
LABEL_36:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v41);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v42);
      goto LABEL_9;
    }
    v58 = 0;
    v49 = 5;
    v50 = L"Url";
    v51 = 3;
    v52 = L"']";
    v53 = 0;
    v14 = Appx::Packaging::BuildXPath(
            (Appx::Packaging *)&v49,
            (const struct Appx::Packaging::XPathComponent *)1,
            &v58,
            v13);
    v6 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1AAB,
        (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestreader.cpp",
        (const char *)(unsigned int)v14,
        (int)&v57);
      v28 = v58;
LABEL_35:
      SysFreeString(v28);
      goto LABEL_36;
    }
    v15 = v41;
    v16 = v58;
    v44 = 0;
    v58 = v41;
    if ( v41 )
      (*(void (__fastcall **)(OLECHAR *))(*(_QWORD *)v41 + 8LL))(v41);
    RequiredNodeValue = Appx::Packaging::GetRequiredNodeValue(&v58, v16, &v44);
    if ( v15 )
      (*(void (__fastcall **)(OLECHAR *))(*(_QWORD *)v15 + 16LL))(v15);
    if ( RequiredNodeValue < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1AAE,
        (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestreader.cpp",
        (const char *)(unsigned int)RequiredNodeValue,
        (int)&v57);
      SysFreeString(v44);
      SysFreeString(v16);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v41);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v42);
      v6 = RequiredNodeValue;
      goto LABEL_9;
    }
    v58 = 0;
    v50 = L"ManagedUrls";
    v49 = 3;
    v52 = L"']";
    v51 = 11;
    v53 = 0;
    v19 = Appx::Packaging::BuildXPath(
            (Appx::Packaging *)&v49,
            (const struct Appx::Packaging::XPathComponent *)1,
            &v58,
            v18);
    v6 = v19;
    if ( v19 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1AB1,
        (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestreader.cpp",
        (const char *)(unsigned int)v19,
        (int)&v57);
      v29 = v58;
LABEL_41:
      SysFreeString(v29);
      SysFreeString(v44);
      v28 = v16;
      goto LABEL_35;
    }
    v43 = 0;
    v20 = v41;
    v21 = *(__int64 (__fastcall **)(OLECHAR *, BSTR, __int64 *))(*(_QWORD *)v41 + 296LL);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v43);
    v22 = v58;
    v8 = v21(v20, v58, &v43);
    if ( v8 != 1 && v43 )
    {
      v59 = v41;
      Microsoft::WRL::ComPtr<IXMLDOMNodeList>::InternalAddRef(&v59);
      v25 = Appx::Packaging::Manifest::AppxManifestReaderImpl::PopulateDictionaryWithNode(this, v4, v44, &v59);
      v6 = v25;
      if ( v25 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1AB9,
          (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestreader.cpp",
          (const char *)(unsigned int)v25,
          (int)&v57);
        goto LABEL_40;
      }
      v59 = 0;
      v49 = 3;
      v50 = L"Url";
      v51 = 3;
      v52 = L"']";
      v53 = 0;
      v27 = Appx::Packaging::BuildXPath(
              (Appx::Packaging *)&v49,
              (const struct Appx::Packaging::XPathComponent *)1,
              &v59,
              v26);
      v6 = v27;
      if ( v27 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1ABC,
          (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestreader.cpp",
          (const char *)(unsigned int)v27,
          (int)&v57);
        SysFreeString(v59);
LABEL_40:
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v43);
        v29 = v22;
        goto LABEL_41;
      }
      v46 = 0;
      LODWORD(v58) = 0;
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v46);
      v30 = v59;
      TableContexta = &v58;
      v31 = Appx::Packaging::GetNodesList(&v43, v59, 0, &v46);
      v32 = v31;
      if ( v31 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1AC1,
          (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestreader.cpp",
          (const char *)(unsigned int)v31,
          (int)&v58);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v46);
        SysFreeString(v30);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v43);
        SysFreeString(v22);
        SysFreeString(v44);
        SysFreeString(v16);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v41);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v42);
        v6 = v32;
        goto LABEL_9;
      }
      v33 = v46;
      for ( i = 0; ; i = (_DWORD)v59 + 1 )
      {
        LODWORD(v59) = i;
        if ( i >= (int)v58 )
          break;
        v45 = 0;
        v35 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v33 + 72LL);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v45);
        v36 = v35(v33, &v45);
        v37 = v36;
        if ( v36 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1AC7,
            (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestreader.cpp",
            (const char *)(unsigned int)v36,
            (int)&v58);
          goto LABEL_54;
        }
        v47 = 0;
        v37 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v45 + 208LL))(v45, &v47);
        if ( v37 < 0 )
        {
          v38 = 6858;
LABEL_52:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v38,
            (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestreader.cpp",
            (const char *)(unsigned int)v37,
            (int)&v58);
          SysFreeString(v47);
LABEL_54:
          Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v45);
          Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v46);
          SysFreeString(v30);
          Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v43);
          SysFreeString(v22);
          SysFreeString(v44);
          SysFreeString(v16);
          Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v41);
          Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v42);
          v6 = v37;
          goto LABEL_9;
        }
        v54[0] = v45;
        Microsoft::WRL::ComPtr<IXMLDOMNodeList>::InternalAddRef(v54);
        v37 = Appx::Packaging::Manifest::AppxManifestReaderImpl::PopulateDictionaryWithNode(this, v4, v47, v54);
        if ( v37 < 0 )
        {
          v38 = 6860;
          goto LABEL_52;
        }
        SysFreeString(v47);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v45);
      }
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v46);
      SysFreeString(v30);
      v9 = v42;
    }
    v23 = v43;
    if ( v43 )
    {
      v43 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    }
    SysFreeString(v22);
    SysFreeString(v44);
    SysFreeString(v16);
    v24 = v41;
    if ( v41 )
    {
      v41 = 0;
      (*(void (__fastcall **)(OLECHAR *))(*(_QWORD *)v24 + 16LL))(v24);
    }
    if ( v8 < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1AD1,
        (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestreader.cpp",
        (const char *)(unsigned int)v8,
        (int)TableContexta);
    goto LABEL_6;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1AA0,
    (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestreader.cpp",
    (const char *)(unsigned int)NodesList,
    (int)&v57);
  if ( v42 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
LABEL_9:
  SysFreeString(bstrString);
  Common::AutoPtrDeallocate<Common::GenericMap<unsigned short *,IXMLDOMNode *>>(v4);
  return v6;
}

```

## disassembly

```asm
0x1800554a8  mov     [rsp-8+arg_0], rcx
0x1800554ad  push    rbp
0x1800554ae  push    rbx
0x1800554af  push    rsi
0x1800554b0  push    rdi
0x1800554b1  push    r12
0x1800554b3  push    r13
0x1800554b5  push    r14
0x1800554b7  push    r15
0x1800554b9  lea     rbp, [rsp-1Fh]
0x1800554be  sub     rsp, 0A8h
0x1800554c5  mov     rdi, rcx
0x1800554c8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800554cf  mov     ecx, 78h ; 'x'; unsigned __int64
0x1800554d4  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800554d9  xor     r14d, r14d
0x1800554dc  mov     r13, rax
0x1800554df  test    rax, rax
0x1800554e2  jz      loc_180055623
0x1800554e8  lea     rax, ?AutoBStrDeallocate@Common@@YAXPEAG@Z; Common::AutoBStrDeallocate(ushort *)
0x1800554ef  mov     [rsp+0E0h+TableContext], r14; int
0x1800554f4  mov     [r13+68h], rax
0x1800554f8  lea     r9, ?GenericMapFree@?$GenericMap@PEBGPEAVBitmap@Packaging@Appx@@@Common@@CAXPEAU_RTL_AVL_TABLE@@PEAX@Z; FreeRoutine
0x1800554ff  lea     rax, ??$DeallocateCom@PEAUIAppxFile@@@Common@@YAXPEAUIAppxFile@@@Z; Common::DeallocateCom<IAppxFile *>(IAppxFile *)
0x180055506  mov     rcx, r13; Table
0x180055509  lea     r8, ?GenericMapAllocate@?$GenericMap@PEAGPEAX@Common@@CAPEAXPEAU_RTL_AVL_TABLE@@K@Z; AllocateRoutine
0x180055510  mov     [r13+70h], rax
0x180055514  lea     rdx, ?GenericMapCaseInsensitiveCompare@Common@@YA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@Z; CompareRoutine
0x18005551b  call    cs:__imp_RtlInitializeGenericTableAvl
0x180055522  nop     dword ptr [rax+rax+00h]
0x180055527  mov     esi, 5
0x18005552c  mov     [rbp+57h+bstrString], r14
0x180055530  mov     edx, esi; struct Appx::Packaging::XPathComponent *
0x180055532  lea     r8, [rbp+57h+bstrString]; unsigned int
0x180055536  lea     rcx, qword_18010B920; this
0x18005553d  call    ?BuildXPath@Packaging@Appx@@YAJPEBUXPathComponent@12@IAEAVAutoBStr@Common@@@Z; Appx::Packaging::BuildXPath(Appx::Packaging::XPathComponent const *,uint,Common::AutoBStr &)
0x180055542  mov     ebx, eax
0x180055544  test    eax, eax
0x180055546  js      loc_180055609
0x18005554c  lea     rcx, [rbp+57h+var_A8]
0x180055550  mov     [rbp+57h+var_A8], r14
0x180055554  mov     [rbp+57h+arg_8], r14d
0x180055558  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18005555d  mov     rdx, [rbp+57h+bstrString]
0x180055561  lea     rax, [rbp+57h+arg_8]
0x180055565  lea     rcx, [rdi+80h]
0x18005556c  mov     [rsp+0E0h+TableContext], rax; int
0x180055571  lea     r9, [rbp+57h+var_A8]
0x180055575  xor     r8d, r8d
0x180055578  call    ?GetNodesList@Packaging@Appx@@YAJAEBV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@PEAGJPEAPEAUIXMLDOMNodeList@@PEAJ@Z; Appx::Packaging::GetNodesList(Microsoft::WRL::ComPtr<IXMLDOMNode> const &,ushort *,long,IXMLDOMNodeList * *,long *)
0x18005557d  mov     ebx, eax
0x18005557f  test    eax, eax
0x180055581  js      short loc_1800555DA
0x180055583  mov     r12d, r14d
0x180055586  mov     r15, [rbp+57h+var_A8]
0x18005558a  cmp     [rbp+57h+arg_8], r14d
0x18005558e  jg      loc_18005562B
0x180055594  test    r15, r15
0x180055597  jz      short loc_1800555A8
0x180055599  mov     rax, [r15]
0x18005559c  mov     rcx, r15
0x18005559f  mov     rax, [rax+10h]
0x1800555a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800555a8  mov     ebx, r12d
0x1800555ab  mov     rcx, [rbp+57h+bstrString]; bstrString
0x1800555af  call    cs:__imp_SysFreeString
0x1800555b6  nop     dword ptr [rax+rax+00h]
0x1800555bb  mov     rcx, r13; void *
0x1800555be  call    ??$AutoPtrDeallocate@V?$GenericMap@PEAGPEAUIXMLDOMNode@@@Common@@@Common@@YAXPEAV?$GenericMap@PEAGPEAUIXMLDOMNode@@@0@@Z; Common::AutoPtrDeallocate<Common::GenericMap<ushort *,IXMLDOMNode *>>(Common::GenericMap<ushort *,IXMLDOMNode *> *)
0x1800555c3  mov     eax, ebx
0x1800555c5  add     rsp, 0A8h
0x1800555cc  pop     r15
0x1800555ce  pop     r14
0x1800555d0  pop     r13
0x1800555d2  pop     r12
0x1800555d4  pop     rdi
0x1800555d5  pop     rsi
0x1800555d6  pop     rbx
0x1800555d7  pop     rbp
0x1800555d8  retn
0x1800555da  mov     rcx, [rbp+5Fh]; this
0x1800555de  lea     r8, aOnecorePrintsc_127; "onecore\\printscan\\appxpackaging\\mani"...
0x1800555e5  mov     r9d, eax; char *
0x1800555e8  mov     edx, 1AA0h; void *
0x1800555ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800555f2  mov     rcx, [rbp+57h+var_A8]
0x1800555f6  test    rcx, rcx
0x1800555f9  jz      short loc_1800555AB
0x1800555fb  mov     rdx, [rcx]
0x1800555fe  mov     rax, [rdx+10h]
0x180055602  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055607  jmp     short loc_1800555AB
0x180055609  mov     rcx, [rbp+5Fh]; this
0x18005560d  lea     r8, aOnecorePrintsc_127; "onecore\\printscan\\appxpackaging\\mani"...
0x180055614  mov     r9d, eax; char *
0x180055617  mov     edx, 1A9Ch; void *
0x18005561c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180055621  jmp     short loc_1800555AB
0x180055623  mov     r13, r14
0x180055626  jmp     loc_180055527
0x18005562b  mov     [rbp+57h+var_B0], r14
0x18005562f  lea     rcx, [rbp+57h+var_B0]
0x180055633  mov     rax, [r15]
0x180055636  mov     rbx, [rax+48h]
0x18005563a  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18005563f  lea     rdx, [rbp+57h+var_B0]
0x180055643  mov     rcx, r15
0x180055646  mov     rax, rbx
0x180055649  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005564e  mov     ebx, eax
0x180055650  test    eax, eax
0x180055652  js      loc_1800558A5
0x180055658  mov     r12d, 3
0x18005565e  mov     [rbp+57h+arg_10], r14
0x180055662  lea     rax, ?Url@AttributeNameWithoutPrefix@Manifest@Packaging@Appx@@3QBGB; "Url"
0x180055669  mov     [rbp+57h+var_70], esi
0x18005566c  mov     [rbp+57h+var_68], rax
0x180055670  lea     r8, [rbp+57h+arg_10]; unsigned int
0x180055674  lea     rax, asc_1801177B4; "']"
0x18005567b  mov     [rbp+57h+var_60], r12d
0x18005567f  lea     edx, [r12-2]; struct Appx::Packaging::XPathComponent *
0x180055684  mov     [rbp+57h+var_58], rax
0x180055688  lea     rcx, [rbp+57h+var_70]; this
0x18005568c  mov     [rbp+57h+var_50], r14d
0x180055690  call    ?BuildXPath@Packaging@Appx@@YAJPEBUXPathComponent@12@IAEAVAutoBStr@Common@@@Z; Appx::Packaging::BuildXPath(Appx::Packaging::XPathComponent const *,uint,Common::AutoBStr &)
0x180055695  mov     ebx, eax
0x180055697  test    eax, eax
0x180055699  js      loc_1800558BF
0x18005569f  mov     rbx, [rbp+57h+var_B0]
0x1800556a3  mov     rdi, [rbp+57h+arg_10]
0x1800556a7  mov     [rbp+57h+var_98], r14
0x1800556ab  mov     [rbp+57h+arg_10], rbx
0x1800556af  test    rbx, rbx
0x1800556b2  jz      short loc_1800556C3
0x1800556b4  mov     rax, [rbx]
0x1800556b7  mov     rcx, rbx
0x1800556ba  mov     rax, [rax+8]
0x1800556be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800556c3  lea     r8, [rbp+57h+var_98]
0x1800556c7  mov     rdx, rdi
0x1800556ca  lea     rcx, [rbp+57h+arg_10]
0x1800556ce  call    ?GetRequiredNodeValue@Packaging@Appx@@YAJAEBV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@PEAGPEAPEAG@Z; Appx::Packaging::GetRequiredNodeValue(Microsoft::WRL::ComPtr<IXMLDOMNode> const &,ushort *,ushort * *)
0x1800556d3  mov     esi, eax
0x1800556d5  test    rbx, rbx
0x1800556d8  jz      short loc_1800556E9
0x1800556da  mov     rcx, [rbx]
0x1800556dd  mov     rax, [rcx+10h]
0x1800556e1  mov     rcx, rbx
0x1800556e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800556e9  test    esi, esi
0x1800556eb  js      loc_1800558FE
0x1800556f1  lea     rax, ?ManagedUrls@ElementNameWithoutPrefix@Manifest@Packaging@Appx@@3QBGB; "ManagedUrls"
0x1800556f8  mov     [rbp+57h+arg_10], r14
0x1800556fc  mov     [rbp+57h+var_68], rax
0x180055700  lea     r8, [rbp+57h+arg_10]; unsigned int
0x180055704  lea     rax, asc_1801177B4; "']"
0x18005570b  mov     [rbp+57h+var_70], r12d
0x18005570f  mov     edx, 1; struct Appx::Packaging::XPathComponent *
0x180055714  mov     [rbp+57h+var_58], rax
0x180055718  lea     rcx, [rbp+57h+var_70]; this
0x18005571c  mov     [rbp+57h+var_60], 0Bh
0x180055723  mov     [rbp+57h+var_50], r14d
0x180055727  call    ?BuildXPath@Packaging@Appx@@YAJPEBUXPathComponent@12@IAEAVAutoBStr@Common@@@Z; Appx::Packaging::BuildXPath(Appx::Packaging::XPathComponent const *,uint,Common::AutoBStr &)
0x18005572c  mov     ebx, eax
0x18005572e  test    eax, eax
0x180055730  js      loc_18005594E
0x180055736  mov     [rbp+57h+var_A0], r14
0x18005573a  lea     rcx, [rbp+57h+var_A0]
0x18005573e  mov     r14, [rbp+57h+var_B0]
0x180055742  mov     rax, [r14]
0x180055745  mov     rbx, [rax+128h]
0x18005574c  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180055751  mov     rsi, [rbp+57h+arg_10]
0x180055755  lea     r8, [rbp+57h+var_A0]
0x180055759  mov     rdx, rsi
0x18005575c  mov     rcx, r14
0x18005575f  mov     rax, rbx
0x180055762  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055767  xor     r14d, r14d
0x18005576a  mov     r12d, eax
0x18005576d  cmp     eax, 1
0x180055770  jnz     loc_1800557FC
0x180055776  mov     rcx, [rbp+57h+var_A0]
0x18005577a  test    rcx, rcx
0x18005577d  jz      short loc_18005578F
0x18005577f  mov     [rbp+57h+var_A0], r14
0x180055783  mov     rax, [rcx]
0x180055786  mov     rax, [rax+10h]
0x18005578a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005578f  mov     rcx, rsi; bstrString
0x180055792  call    cs:__imp_SysFreeString
0x180055799  nop     dword ptr [rax+rax+00h]
0x18005579e  mov     rcx, [rbp+57h+var_98]; bstrString
0x1800557a2  call    cs:__imp_SysFreeString
0x1800557a9  nop     dword ptr [rax+rax+00h]
0x1800557ae  mov     rcx, rdi; bstrString
0x1800557b1  call    cs:__imp_SysFreeString
0x1800557b8  nop     dword ptr [rax+rax+00h]
0x1800557bd  mov     rcx, [rbp+57h+var_B0]
0x1800557c1  test    rcx, rcx
0x1800557c4  jz      short loc_1800557D6
0x1800557c6  mov     [rbp+57h+var_B0], r14
0x1800557ca  mov     rax, [rcx]
0x1800557cd  mov     rax, [rax+10h]
0x1800557d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800557d6  test    r12d, r12d
0x1800557d9  jns     loc_180055594
0x1800557df  mov     rcx, [rbp+5Fh]; this
0x1800557e3  lea     r8, aOnecorePrintsc_127; "onecore\\printscan\\appxpackaging\\mani"...
0x1800557ea  mov     r9d, r12d; char *
0x1800557ed  mov     edx, 1AD1h; void *
0x1800557f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800557f7  jmp     loc_180055594
0x1800557fc  cmp     [rbp+57h+var_A0], r14
0x180055800  jz      loc_180055776
0x180055806  mov     rcx, [rbp+57h+var_B0]
0x18005580a  mov     [rbp+57h+arg_18], rcx
0x18005580e  lea     rcx, [rbp+57h+arg_18]
0x180055812  call    ?InternalAddRef@?$ComPtr@UIXMLDOMNodeList@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IXMLDOMNodeList>::InternalAddRef(void)
0x180055817  mov     r8, [rbp+57h+var_98]
0x18005581b  lea     r9, [rbp+57h+arg_18]
0x18005581f  mov     rcx, [rbp+57h+arg_0]
0x180055823  mov     rdx, r13
0x180055826  call    ?PopulateDictionaryWithNode@AppxManifestReaderImpl@Manifest@Packaging@Appx@@AEAAJPEAV?$GenericMap@PEAGPEAUIXMLDOMNode@@@Common@@PEAGV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@@Z; Appx::Packaging::Manifest::AppxManifestReaderImpl::PopulateDictionaryWithNode(Common::GenericMap<ushort *,IXMLDOMNode *> *,ushort *,Microsoft::WRL::ComPtr<IXMLDOMNode>)
0x18005582b  mov     ebx, eax
0x18005582d  test    eax, eax
0x18005582f  js      loc_18005596C
0x180055835  mov     ecx, 3
0x18005583a  mov     [rbp+57h+arg_18], r14
0x18005583e  lea     rax, ?Url@ElementNameWithoutPrefix@Manifest@Packaging@Appx@@3QBGB; "Url"
0x180055845  mov     [rbp+57h+var_70], ecx
0x180055848  mov     [rbp+57h+var_68], rax
0x18005584c  lea     r8, [rbp+57h+arg_18]; unsigned int
0x180055850  mov     [rbp+57h+var_60], ecx
0x180055853  lea     rax, asc_1801177B4; "']"
0x18005585a  lea     edx, [rcx-2]; struct Appx::Packaging::XPathComponent *
0x18005585d  mov     [rbp+57h+var_58], rax
0x180055861  lea     rcx, [rbp+57h+var_70]; this
0x180055865  mov     [rbp+57h+var_50], r14d
0x180055869  call    ?BuildXPath@Packaging@Appx@@YAJPEBUXPathComponent@12@IAEAVAutoBStr@Common@@@Z; Appx::Packaging::BuildXPath(Appx::Packaging::XPathComponent const *,uint,Common::AutoBStr &)
0x18005586e  mov     ebx, eax
0x180055870  test    eax, eax
0x180055872  jns     loc_1800559B4
0x180055878  mov     rcx, [rbp+5Fh]; this
0x18005587c  lea     r8, aOnecorePrintsc_127; "onecore\\printscan\\appxpackaging\\mani"...
0x180055883  mov     r9d, eax; char *
0x180055886  mov     edx, 1ABCh; void *
0x18005588b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180055890  mov     rcx, [rbp+57h+arg_18]; bstrString
0x180055894  call    cs:__imp_SysFreeString
0x18005589b  nop     dword ptr [rax+rax+00h]
0x1800558a0  jmp     loc_180055984
0x1800558a5  mov     rcx, [rbp+5Fh]; this
0x1800558a9  lea     r8, aOnecorePrintsc_127; "onecore\\printscan\\appxpackaging\\mani"...
0x1800558b0  mov     r9d, eax; char *
0x1800558b3  mov     edx, 1AA7h; void *
0x1800558b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800558bd  jmp     short loc_1800558E7
0x1800558bf  mov     rcx, [rbp+5Fh]; this
0x1800558c3  lea     r8, aOnecorePrintsc_127; "onecore\\printscan\\appxpackaging\\mani"...
0x1800558ca  mov     r9d, eax; char *
0x1800558cd  mov     edx, 1AABh; void *
0x1800558d2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800558d7  mov     rcx, [rbp+57h+arg_10]; bstrString
0x1800558db  call    cs:__imp_SysFreeString
0x1800558e2  nop     dword ptr [rax+rax+00h]
0x1800558e7  lea     rcx, [rbp+57h+var_B0]
0x1800558eb  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800558f0  lea     rcx, [rbp+57h+var_A8]
0x1800558f4  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800558f9  jmp     loc_1800555AB
0x1800558fe  mov     rcx, [rbp+5Fh]; this
0x180055902  lea     r8, aOnecorePrintsc_127; "onecore\\printscan\\appxpackaging\\mani"...
0x180055909  mov     r9d, esi; char *
0x18005590c  mov     edx, 1AAEh; void *
0x180055911  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180055916  mov     rcx, [rbp+57h+var_98]; bstrString
0x18005591a  call    cs:__imp_SysFreeString
0x180055921  nop     dword ptr [rax+rax+00h]
0x180055926  mov     rcx, rdi; bstrString
0x180055929  call    cs:__imp_SysFreeString
0x180055930  nop     dword ptr [rax+rax+00h]
0x180055935  lea     rcx, [rbp+57h+var_B0]
0x180055939  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18005593e  lea     rcx, [rbp+57h+var_A8]
0x180055942  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180055947  mov     ebx, esi
0x180055949  jmp     loc_1800555AB
0x18005594e  mov     rcx, [rbp+5Fh]; this
0x180055952  lea     r8, aOnecorePrintsc_127; "onecore\\printscan\\appxpackaging\\mani"...
0x180055959  mov     r9d, eax; char *
0x18005595c  mov     edx, 1AB1h; void *
0x180055961  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180055966  mov     rcx, [rbp+57h+arg_10]
0x18005596a  jmp     short loc_180055990
0x18005596c  mov     rcx, [rbp+5Fh]; this
0x180055970  lea     r8, aOnecorePrintsc_127; "onecore\\printscan\\appxpackaging\\mani"...
0x180055977  mov     r9d, eax; char *
0x18005597a  mov     edx, 1AB9h; void *
0x18005597f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
  ... truncated ...
```
