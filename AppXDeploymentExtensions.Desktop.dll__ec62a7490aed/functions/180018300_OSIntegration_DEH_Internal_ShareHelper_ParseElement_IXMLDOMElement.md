# OSIntegration::DEH::Internal::ShareHelper::ParseElement(IXMLDOMElement *)

- ea: `0x180018300`
- end: `0x180018c48`
- name: `?ParseElement@ShareHelper@Internal@DEH@OSIntegration@@UEAAJPEAUIXMLDOMElement@@@Z`
- size: `2376`
- prototype: `__int64 __fastcall(OSIntegration::DEH::Internal::ShareHelper *__hidden this, struct IXMLDOMElement *)`
- caller_count: `0`
- callee_count: `16`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x180006970`
- `0x180010890`
- `0x180012fc8`
- `0x1800178a0`
- `0x180017ba0`
- `0x180018300`
- `0x180018f88`
- `0x18001adb4`
- `0x180025270`
- `0x18003e690`
- `0x180069eb4`
- `0x1800aed10`
- `0x1800af1bc`
- `0x1800ba45d`
- `0x1800e00d0`
- `0x1801ac010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001865d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001877b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001865d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001877b`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180018406`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180018406`
- `OLEAUT32!__imp_SysFreeString` at `0x18001839a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800184e4`
- `OLEAUT32!__imp_SysFreeString` at `0x18001839a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800184e4`

## string_xrefs

- `0x180018387`: `onecore\admin\appmodel\common\xmltools.cpp`
- `0x18001887f`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x180018941`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x1800189b8`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x1800189d3`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x1800187ae`: `onecore\base\appmodel\common\widestring.cpp`
- `0x1800189ec`: `onecore\admin\appmodel\osim\src\deh\appx\common\tools.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall OSIntegration::DEH::Internal::ShareHelper::ParseElement(
        OSIntegration::DEH::Internal::ShareHelper *this,
        struct IXMLDOMElement *a2)
{
  unsigned int v4; // r12d
  OLECHAR *v5; // rbx
  signed int v6; // esi
  wil::details::in1diag3 *v7; // rcx
  __int64 v8; // r9
  __int64 v9; // rdx
  __int64 v10; // rcx
  const OLECHAR *v11; // rax
  __int64 v12; // rdx
  HRESULT (__stdcall *selectSingleNode)(IXMLDOMElement *, BSTR, IXMLDOMNode **); // rdi
  int v14; // eax
  const unsigned __int16 *v15; // rdi
  __int64 (__fastcall *v16)(const unsigned __int16 *, GUID *, char **); // rsi
  int v17; // eax
  char *v18; // rax
  char *v19; // rcx
  const unsigned __int16 *v20; // rcx
  int v21; // eax
  const struct std::nothrow_t *v22; // rdx
  signed int v23; // ebx
  char *v24; // rcx
  int v25; // eax
  __int64 v26; // rdx
  int v27; // eax
  _QWORD *v28; // r13
  unsigned __int64 v29; // r15
  wchar_t **v30; // r10
  unsigned __int64 v31; // rdi
  unsigned __int64 v32; // r12
  const WCHAR *v33; // rax
  unsigned int v34; // esi
  int v35; // eax
  unsigned __int64 v36; // r9
  __int64 v37; // rdx
  unsigned __int64 v38; // r12
  __int64 v39; // rbx
  Common::StringBuffer *v40; // r11
  __int64 v41; // r10
  WCHAR *v42; // rax
  int v43; // eax
  unsigned __int64 v44; // r9
  _DWORD *v45; // rsi
  _WORD *v46; // rcx
  unsigned int *v47; // rcx
  __int64 v48; // rdi
  __int64 v49; // r12
  const unsigned __int16 *v50; // r9
  wil::details::in1diag3 *v51; // rcx
  unsigned __int64 v52; // r9
  __int64 v53; // rdx
  int v54; // eax
  __int64 v55; // rdi
  const unsigned __int16 *v56; // r8
  wil::details::in1diag3 *v57; // rcx
  unsigned __int64 v58; // r9
  __int64 v59; // rdx
  int v60; // eax
  __int64 v61; // rdx
  char *v62; // rcx
  _DWORD *v63; // rbx
  int v64; // edi
  __int64 v65; // rdx
  char *v67; // rcx
  unsigned __int64 i; // rbx
  _QWORD *v69; // rdi
  void *v70; // rcx
  _QWORD *v71; // rax
  unsigned __int64 v72; // rbx
  unsigned __int64 j; // rsi
  _QWORD *v74; // rdi
  void *v75; // rcx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-E0h]
  BOOL bIgnoreCasea; // [rsp+20h] [rbp-E0h]
  BOOL bIgnoreCaseb; // [rsp+20h] [rbp-E0h]
  char v79; // [rsp+30h] [rbp-D0h]
  char v80; // [rsp+31h] [rbp-CFh]
  const unsigned __int16 *v81; // [rsp+38h] [rbp-C8h] BYREF
  char *v82; // [rsp+40h] [rbp-C0h] BYREF
  char *v83; // [rsp+48h] [rbp-B8h] BYREF
  OLECHAR *v84; // [rsp+50h] [rbp-B0h]
  void **v85; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int *v86; // [rsp+60h] [rbp-A0h]
  char *v87; // [rsp+68h] [rbp-98h]
  void *v88[2]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int64 v89; // [rsp+80h] [rbp-80h]
  char v90; // [rsp+88h] [rbp-78h]
  void *v91[2]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int64 v92; // [rsp+A0h] [rbp-60h]
  char v93; // [rsp+A8h] [rbp-58h]
  const WCHAR *v94; // [rsp+B0h] [rbp-50h]
  WCHAR String1[256]; // [rsp+C0h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+308h] [rbp+208h]

  v4 = 0;
  v91[0] = 0;
  v91[1] = 0;
  v92 = 0;
  v93 = 1;
  v88[0] = 0;
  v88[1] = 0;
  v89 = 0;
  v90 = 1;
  v82 = 0;
  v81 = 0;
  v83 = 0;
  v5 = 0;
  if ( !a2 )
  {
    v6 = -2147024809;
    v7 = retaddr;
    v8 = 2147942487LL;
    v9 = 124;
LABEL_3:
    wil::details::in1diag3::_Log_Hr(
      v7,
      (void *)v9,
      (unsigned int)"onecore\\admin\\appmodel\\common\\xmltools.cpp",
      (const char *)v8,
      bIgnoreCase);
    goto LABEL_20;
  }
  SysFreeString(0);
  v5 = 0;
  v84 = 0;
  v10 = 0x7FFFFFFF;
  v11 = L"*[local-name()='ShareTarget']/*[local-name()='SupportedFileTypes']/*[local-name()='SupportsAnyFileType']";
  do
  {
    if ( !*v11 )
      break;
    ++v11;
    --v10;
  }
  while ( v10 );
  v6 = v10 == 0 ? 0x80070057 : 0;
  v12 = (0x7FFFFFFF - v10) & ((unsigned __int128)-(__int128)(unsigned __int64)v10 >> 64);
  if ( v10 )
  {
    if ( (unsigned int)v12 <= 0x3FFFFFFF )
    {
      v5 = SysAllocStringLen(
             L"*[local-name()='ShareTarget']/*[local-name()='SupportedFileTypes']/*[local-name()='SupportsAnyFileType']",
             v12);
      v84 = v5;
      v6 = v5 == 0 ? 0x8007000E : 0;
    }
    else
    {
      v6 = -2147024809;
    }
  }
  v7 = retaddr;
  if ( v6 < 0 )
  {
    v8 = (unsigned int)v6;
    v9 = 127;
    goto LABEL_3;
  }
  selectSingleNode = a2->lpVtbl->selectSingleNode;
  Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v81);
  v14 = ((__int64 (__fastcall *)(struct IXMLDOMElement *, OLECHAR *, const unsigned __int16 **))selectSingleNode)(
          a2,
          v5,
          &v81);
  v6 = v14;
  v7 = retaddr;
  if ( v14 < 0 )
  {
    v8 = (unsigned int)v14;
    v9 = 131;
    goto LABEL_3;
  }
  v15 = v81;
  if ( v81 )
  {
    v16 = **(__int64 (__fastcall ***)(const unsigned __int16 *, GUID *, char **))v81;
    Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v83);
    v17 = v16(v15, &GUID_2933bf86_7b36_11d2_b20e_00c04f983e60, &v83);
    v6 = v17;
    v7 = retaddr;
    if ( v17 < 0 )
    {
      v8 = (unsigned int)v17;
      v9 = 137;
      goto LABEL_3;
    }
    v18 = v83;
    v83 = 0;
    v82 = v18;
  }
  else
  {
    v82 = 0;
  }
LABEL_20:
  SysFreeString(v5);
  v19 = v83;
  if ( v83 )
  {
    v83 = 0;
    (*(void (__fastcall **)(char *))(*(_QWORD *)v19 + 16LL))(v19);
  }
  v20 = v81;
  if ( v81 )
  {
    v81 = 0;
    (*(void (__fastcall **)(const unsigned __int16 *))(*(_QWORD *)v20 + 16LL))(v20);
  }
  if ( v6 >= 0 && v82 )
  {
    LODWORD(v83) = 0;
    v80 = 1;
  }
  else
  {
    v80 = 0;
    LODWORD(v83) = OSIntegration::Tools::ConvertElementsIntoStringBufferArrayForQuery(
                     a2,
                     L"*[local-name()='ShareTarget']/*[local-name()='SupportedFileTypes']/*[local-name()='FileType']",
                     v91,
                     0);
    if ( (int)v83 >= 0 )
    {
      v25 = OSIntegration::Tools::FlattenStringBufferArrayToDeliminatedList(v91, &unk_1801AD130, (char *)this + 72);
      v23 = v25;
      if ( v25 < 0 )
      {
        v26 = 107;
        goto LABEL_117;
      }
    }
  }
  v21 = OSIntegration::Tools::ConvertElementsIntoStringBufferArrayForQuery(
          a2,
          L"*[local-name()='ShareTarget']/*[local-name()='DataFormat']",
          v88,
          0);
  v23 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x74,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\uex\\share\\sharehelper.cpp",
      (const char *)(unsigned int)v21,
      bIgnoreCase);
    v24 = v82;
    if ( v82 )
    {
      v82 = 0;
      (*(void (__fastcall **)(char *))(*(_QWORD *)v24 + 16LL))(v24);
    }
    goto LABEL_120;
  }
  v79 = 0;
  v27 = -1;
  LODWORD(v81) = -1;
  v28 = v88[0];
  v29 = 0;
  while ( 1 )
  {
    v30 = off_1801AD0E0;
    LODWORD(v84) = v4;
    v31 = v4;
    v32 = v89;
    if ( v31 >= v89 )
      break;
    _mm_lfence();
    v33 = *(const WCHAR **)(v28[v31] + 8LL);
    v94 = v33;
    v23 = 0;
    v34 = 0;
    do
    {
      if ( (_BYTE)v29 )
        goto LABEL_47;
      if ( v34 >= 5 )
        break;
      v35 = CompareStringOrdinal(v30[2 * (int)v34 + 1], -1, v33, -1, 1);
      v30 = off_1801AD0E0;
      if ( v35 == 2 )
      {
        v23 = StringCchCopyW(String1, 0xFFu, off_1801AD0E0[2 * (int)v34]);
        LOBYTE(v29) = 1;
      }
      ++v34;
      v33 = v94;
    }
    while ( v23 >= 0 );
    if ( v23 >= 0 )
    {
      if ( (_BYTE)v29 )
      {
LABEL_47:
        v29 = 0;
        goto LABEL_48;
      }
      v23 = StringCchCopyW(String1, 0xFFu, v33);
    }
    v29 = 0;
    if ( v23 < 0 )
    {
      v36 = (unsigned int)v23;
      v37 = 47;
      goto LABEL_66;
    }
LABEL_48:
    v38 = v89;
    v39 = 0;
    if ( v31 < v89 )
      v39 = v28[v31];
    operator delete(*(void **)(v39 + 8), v22);
    *(_QWORD *)(v39 + 8) = 0;
    *(_DWORD *)v39 = 0;
    *(_DWORD *)(v39 + 16) = 0;
    v40 = 0;
    if ( v31 < v38 )
      v40 = (Common::StringBuffer *)v28[v31];
    v41 = 1073741822;
    v42 = String1;
    do
    {
      if ( !*v42 )
        break;
      ++v42;
      --v41;
    }
    while ( v41 );
    v23 = v41 == 0 ? 0x80070057 : 0;
    if ( !v41 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x249,
        (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
        (const char *)(unsigned int)v23,
        bIgnoreCase);
LABEL_62:
      v36 = (unsigned int)v23;
      v37 = 52;
LABEL_66:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v37,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\uex\\share\\sharehelper.cpp",
        (const char *)v36,
        bIgnoreCase);
      v44 = (unsigned int)v23;
      v26 = 121;
LABEL_118:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v26,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\uex\\share\\sharehelper.cpp",
        (const char *)v44,
        bIgnoreCase);
LABEL_119:
      Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v82);
      goto LABEL_120;
    }
    v23 = Common::StringBuffer::SetValue(v40, String1, v41 != 0 ? 1073741822 - v41 : 0);
    if ( v23 < 0 )
      goto LABEL_62;
    if ( CompareStringOrdinal(String1, -1, L"Shell IDList Array", -1, 1) == 2 )
    {
      v79 = 1;
      v27 = (int)v84;
      LODWORD(v81) = (_DWORD)v84;
    }
    else
    {
      v27 = (int)v81;
    }
    v4 = (_DWORD)v84 + 1;
  }
  if ( v27 != -1 )
  {
    v43 = Common::Array<Common::StringBuffer,Common::ContainerOperations<Common::StringBuffer,Common::StringBuffer>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::StringBuffer>,Common::ArrayOperations<Common::StringBuffer,Common::NoKey>>::DeleteAt(
            v88,
            v27);
    v23 = v43;
    if ( v43 < 0 )
    {
      v36 = (unsigned int)v43;
      v37 = 68;
      goto LABEL_66;
    }
    v28 = v88[0];
    v32 = v89;
  }
  v45 = (_DWORD *)((char *)this + 96);
  v86 = (unsigned int *)((char *)this + 96);
  v85 = &Common::StringBufferBuilder::`vftable';
  v87 = (char *)this + 96;
  v46 = (_WORD *)*((_QWORD *)this + 13);
  if ( v46 )
    *v46 = 0;
  *v45 = 0;
  while ( 1 )
  {
    if ( v29 >= v32 )
    {
      v63 = (_DWORD *)((char *)this + 72);
      if ( v79 && !*v63 )
        goto LABEL_106;
      v64 = (int)v83;
      if ( (int)v83 < 0 )
      {
        v65 = 136;
LABEL_104:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v65,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\uex\\share\\sharehelper.cpp",
          (const char *)(unsigned int)v64,
          bIgnoreCase);
        v23 = v64;
        goto LABEL_119;
      }
      if ( v80 )
      {
LABEL_106:
        v63 = (_DWORD *)((char *)this + 72);
        v64 = Common::StringBuffer::SetValue((OSIntegration::DEH::Internal::ShareHelper *)((char *)this + 72), L"*", 1u);
        if ( v64 < 0 )
        {
          v65 = 143;
          goto LABEL_104;
        }
      }
      if ( !*((_DWORD *)this + 24) )
      {
        v63 = (_DWORD *)((char *)this + 72);
        if ( !*((_DWORD *)this + 18) )
        {
          v23 = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x96,
                  (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\uex\\share\\sharehelper.cpp",
                  (const char *)0x3CF2,
                  bIgnoreCase);
          goto LABEL_119;
        }
      }
      if ( *v63
        && (v25 = OSIntegration::Tools::AddStringPropertyToContainer(
                    L"SupportedFileTypes",
                    *((unsigned __int16 **)this + 10)),
            v23 = v25,
            v25 < 0) )
      {
        v26 = 158;
      }
      else
      {
        if ( !*v45
          || (v25 = OSIntegration::Tools::AddStringPropertyToContainer(
                      L"SupportedDataFormats",
                      *((unsigned __int16 **)this + 13)),
              v23 = v25,
              v25 >= 0) )
        {
          v67 = v82;
          if ( v82 )
          {
            v82 = 0;
            (*(void (__fastcall **)(char *))(*(_QWORD *)v67 + 16LL))(v67);
          }
          if ( v28 )
          {
            if ( v90 )
            {
              for ( i = 0; i < v32; ++i )
              {
                v69 = (_QWORD *)v28[i];
                if ( v69 )
                {
                  v70 = (void *)v69[1];
                  if ( v70 )
                    operator delete(v70, v22);
                  operator delete(v69, v22);
                }
              }
            }
            operator delete(v28, v22);
          }
          v71 = v91[0];
          if ( v91[0] )
          {
            if ( v93 )
            {
              v72 = 0;
              for ( j = v92; v72 < j; ++v72 )
              {
                v74 = (_QWORD *)v71[v72];
                if ( v74 )
                {
                  v75 = (void *)v74[1];
                  if ( v75 )
                    operator delete(v75, v22);
                  operator delete(v74, v22);
                  v71 = v91[0];
                }
              }
            }
            operator delete(v71, v22);
          }
          return 0;
        }
        v26 = 166;
      }
LABEL_117:
      v44 = (unsigned int)v25;
      goto LABEL_118;
    }
    v47 = (unsigned int *)v28[v29];
    v48 = *v86;
    v49 = *v47;
    v50 = (const unsigned __int16 *)*((_QWORD *)v47 + 1);
    v81 = v50;
    v23 = ~(_DWORD)v49 < (unsigned int)v48 ? 0x80070216 : 0;
    v51 = retaddr;
    if ( (unsigned int)v48 <= ~(_DWORD)v49 )
    {
      if ( (unsigned int)(v49 + v48) > 0x3FFFFFFF )
      {
        v23 = -2147023613;
        goto LABEL_81;
      }
      v54 = ((__int64 (__fastcall *)(void ***))*v85)(&v85);
      v23 = v54;
      v51 = retaddr;
      if ( v54 >= 0 )
      {
        v23 = 0;
        goto LABEL_80;
      }
      v52 = (unsigned int)v54;
      v53 = 269;
    }
    else
    {
      v52 = (unsigned int)v23;
      v53 = 263;
    }
    wil::details::in1diag3::_Log_Hr(
      v51,
      (void *)v53,
      (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
      (const char *)v52,
      bIgnoreCase);
LABEL_80:
    v50 = v81;
LABEL_81:
    if ( v23 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x79,
        (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
        (const char *)(unsigned int)v23,
        bIgnoreCase);
      v61 = 397;
      goto LABEL_97;
    }
    memcpy_0((void *)(*((_QWORD *)v86 + 1) + 2 * v48), v50, 2 * v49);
    v32 = v89;
    if ( v29 < v89 - 1 )
      break;
LABEL_94:
    ++v29;
  }
  v55 = *v86;
  v56 = L";";
  v81 = L";";
  v23 = (_DWORD)v55 == -1 ? 0x80070216 : 0;
  v57 = retaddr;
  if ( (_DWORD)v55 == -1 )
  {
    v58 = (unsigned int)v23;
    v59 = 263;
    goto LABEL_85;
  }
  v22 = (const struct std::nothrow_t *)(unsigned int)(v55 + 1);
  if ( (unsigned int)v22 <= 0x3FFFFFFF )
  {
    v60 = ((__int64 (__fastcall *)(void ***))*v85)(&v85);
    v23 = v60;
    v57 = retaddr;
    if ( v60 >= 0 )
    {
      v23 = 0;
    }
    else
    {
      v58 = (unsigned int)v60;
      v59 = 269;
LABEL_85:
      wil::details::in1diag3::_Log_Hr(
        v57,
        (void *)v59,
        (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
        (const char *)v58,
        bIgnoreCase);
    }
    v56 = v81;
  }
  else
  {
    v23 = -2147023613;
  }
  if ( v23 >= 0 )
  {
    *(_WORD *)(*((_QWORD *)v86 + 1) + 2 * v55) = *v56;
    goto LABEL_94;
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x79,
    (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
    (const char *)(unsigned int)v23,
    bIgnoreCase);
  v61 = 402;
LABEL_97:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v61,
    (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\tools.cpp",
    (const char *)(unsigned int)v23,
    bIgnoreCasea);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x7F,
    (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\uex\\share\\sharehelper.cpp",
    (const char *)(unsigned int)v23,
    bIgnoreCaseb);
  v62 = v82;
  if ( v82 )
  {
    v82 = 0;
    (*(void (__fastcall **)(char *))(*(_QWORD *)v62 + 16LL))(v62);
  }
LABEL_120:
  Common::Array<Common::StringBuffer,Common::ContainerOperations<Common::StringBuffer,Common::StringBuffer>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::StringBuffer>,Common::ArrayOperations<Common::StringBuffer,Common::NoKey>>::~Array<Common::StringBuffer,Common::ContainerOperations<Common::StringBuffer,Common::StringBuffer>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::StringBuffer>,Common::ArrayOperations<Common::StringBuffer,Common::NoKey>>(v88);
  Common::Array<Common::StringBuffer,Common::ContainerOperations<Common::StringBuffer,Common::StringBuffer>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::StringBuffer>,Common::ArrayOperations<Common::StringBuffer,Common::NoKey>>::~Array<Common::StringBuffer,Common::ContainerOperations<Common::StringBuffer,Common::StringBuffer>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::StringBuffer>,Common::ArrayOperations<Common::StringBuffer,Common::NoKey>>(v91);
  return (unsigned int)v23;
}

```

## disassembly

```asm
0x180018300  mov     [rsp-8+arg_10], rbx
0x180018305  push    rbp
0x180018306  push    rsi
0x180018307  push    rdi
0x180018308  push    r12
0x18001830a  push    r13
0x18001830c  push    r14
0x18001830e  push    r15
0x180018310  lea     rbp, [rsp-1D0h]
0x180018318  sub     rsp, 2D0h
0x18001831f  mov     rax, cs:__security_cookie
0x180018326  xor     rax, rsp
0x180018329  mov     [rbp+200h+var_40], rax
0x180018330  mov     r15, rdx
0x180018333  mov     r14, rcx
0x180018336  xor     r12d, r12d
0x180018339  mov     [rbp+200h+var_270], r12
0x18001833d  mov     [rbp+200h+var_268], r12
0x180018341  mov     [rbp+200h+var_260], r12
0x180018345  mov     [rbp+200h+var_258], 1
0x180018349  mov     [rsp+300h+var_290], r12
0x18001834e  mov     [rsp+300h+var_288], r12
0x180018353  mov     [rbp+200h+var_280], r12
0x180018357  mov     [rbp+200h+var_278], 1
0x18001835b  mov     [rsp+300h+var_2C0], r12
0x180018360  mov     [rsp+300h+var_2C8], r12
0x180018365  mov     [rsp+300h+var_2B8], r12
0x18001836a  mov     ebx, r12d
0x18001836d  test    rdx, rdx
0x180018370  jnz     short loc_180018398
0x180018372  mov     edi, 80070057h
0x180018377  mov     esi, edi
0x180018379  mov     rcx, [rbp+208h]; this
0x180018380  mov     r9d, edi; char *
0x180018383  lea     edx, [r15+7Ch]; void *
0x180018387  lea     r8, aOnecoreAdminAp_120; "onecore\\admin\\appmodel\\common\\xmlto"...
0x18001838e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180018393  jmp     loc_1800184E1
0x180018398  xor     ecx, ecx; bstrString
0x18001839a  call    cs:__imp_SysFreeString
0x1800183a1  nop     dword ptr [rax+rax+00h]
0x1800183a6  mov     rbx, r12
0x1800183a9  mov     [rsp+300h+var_2B0], rbx
0x1800183ae  mov     r8d, 7FFFFFFFh
0x1800183b4  mov     ecx, r8d
0x1800183b7  lea     rax, aLocalNameShare_1; "*[local-name()='ShareTarget']/*[local-n"...
0x1800183be  cmp     [rax], r12w
0x1800183c2  jz      short loc_1800183CE
0x1800183c4  add     rax, 2
0x1800183c8  sub     rcx, 1
0x1800183cc  jnz     short loc_1800183BE
0x1800183ce  mov     rax, rcx
0x1800183d1  neg     rax
0x1800183d4  sbb     esi, esi
0x1800183d6  not     esi
0x1800183d8  mov     edi, 80070057h
0x1800183dd  and     esi, edi
0x1800183df  mov     rax, rcx
0x1800183e2  sub     r8, rcx
0x1800183e5  neg     rax
0x1800183e8  sbb     rdx, rdx
0x1800183eb  and     rdx, r8; ui
0x1800183ee  test    rcx, rcx
0x1800183f1  jz      short loc_180018427
0x1800183f3  cmp     edx, 3FFFFFFFh
0x1800183f9  jbe     short loc_1800183FF
0x1800183fb  mov     esi, edi
0x1800183fd  jmp     short loc_180018427
0x1800183ff  lea     rcx, aLocalNameShare_1; "*[local-name()='ShareTarget']/*[local-n"...
0x180018406  call    cs:__imp_SysAllocStringLen
0x18001840d  nop     dword ptr [rax+rax+00h]
0x180018412  mov     rbx, rax
0x180018415  mov     [rsp+300h+var_2B0], rax
0x18001841a  neg     rax
0x18001841d  sbb     esi, esi
0x18001841f  not     esi
0x180018421  and     esi, 8007000Eh
0x180018427  mov     rcx, [rbp+208h]
0x18001842e  test    esi, esi
0x180018430  jns     short loc_18001843F
0x180018432  mov     r9d, esi
0x180018435  mov     edx, 7Fh
0x18001843a  jmp     loc_180018387
0x18001843f  mov     rax, [r15]
0x180018442  mov     rdi, [rax+128h]
0x180018449  lea     rcx, [rsp+300h+var_2C8]
0x18001844e  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x180018453  lea     r8, [rsp+300h+var_2C8]
0x180018458  mov     rdx, rbx
0x18001845b  mov     rcx, r15
0x18001845e  mov     rax, rdi
0x180018461  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018466  mov     esi, eax
0x180018468  mov     rcx, [rbp+208h]
0x18001846f  test    eax, eax
0x180018471  jns     short loc_180018480
0x180018473  mov     r9d, eax
0x180018476  mov     edx, 83h
0x18001847b  jmp     loc_180018387
0x180018480  mov     rdi, [rsp+300h+var_2C8]
0x180018485  test    rdi, rdi
0x180018488  jz      short loc_1800184DC
0x18001848a  mov     rax, [rdi]
0x18001848d  mov     rsi, [rax]
0x180018490  lea     rcx, [rsp+300h+var_2B8]
0x180018495  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x18001849a  lea     r8, [rsp+300h+var_2B8]
0x18001849f  lea     rdx, _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60
0x1800184a6  mov     rcx, rdi
0x1800184a9  mov     rax, rsi
0x1800184ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800184b1  mov     esi, eax
0x1800184b3  mov     rcx, [rbp+208h]
0x1800184ba  test    eax, eax
0x1800184bc  jns     short loc_1800184CB
0x1800184be  mov     r9d, eax
0x1800184c1  mov     edx, 89h
0x1800184c6  jmp     loc_180018387
0x1800184cb  mov     rax, [rsp+300h+var_2B8]
0x1800184d0  mov     [rsp+300h+var_2B8], r12
0x1800184d5  mov     [rsp+300h+var_2C0], rax
0x1800184da  jmp     short loc_1800184E1
0x1800184dc  mov     [rsp+300h+var_2C0], r12
0x1800184e1  mov     rcx, rbx; bstrString
0x1800184e4  call    cs:__imp_SysFreeString
0x1800184eb  nop     dword ptr [rax+rax+00h]
0x1800184f0  nop
0x1800184f1  mov     rcx, [rsp+300h+var_2B8]
0x1800184f6  test    rcx, rcx
0x1800184f9  jz      short loc_18001850D
0x1800184fb  mov     [rsp+300h+var_2B8], r12
0x180018500  mov     rax, [rcx]
0x180018503  mov     rax, [rax+10h]
0x180018507  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001850c  nop
0x18001850d  mov     rcx, [rsp+300h+var_2C8]
0x180018512  test    rcx, rcx
0x180018515  jz      short loc_180018529
0x180018517  mov     [rsp+300h+var_2C8], r12
0x18001851c  mov     rax, [rcx]
0x18001851f  mov     rax, [rax+10h]
0x180018523  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018528  nop
0x180018529  test    esi, esi
0x18001852b  js      short loc_18001859C
0x18001852d  cmp     [rsp+300h+var_2C0], r12
0x180018532  jz      short loc_18001859C
0x180018534  mov     dword ptr [rsp+300h+var_2B8], r12d
0x180018539  mov     [rsp+300h+var_2CF], 1
0x18001853e  xor     r9d, r9d
0x180018541  lea     r8, [rsp+300h+var_290]
0x180018546  lea     rdx, aLocalNameShare_2; "*[local-name()='ShareTarget']/*[local-n"...
0x18001854d  mov     rcx, r15
0x180018550  call    ?ConvertElementsIntoStringBufferArrayForQuery@Tools@OSIntegration@@YAJPEAUIXMLDOMElement@@PEBGAEAV?$Array@VStringBuffer@Common@@V?$ContainerOperations@VStringBuffer@Common@@V12@@2@VNoKey@2@V?$ContainerOperations@VNoKey@Common@@VStringBuffer@2@@2@V?$ArrayOperations@VStringBuffer@Common@@VNoKey@2@@2@@Common@@PEAVItemVerifier@12@@Z; OSIntegration::Tools::ConvertElementsIntoStringBufferArrayForQuery(IXMLDOMElement *,ushort const *,Common::Array<Common::StringBuffer,Common::ContainerOperations<Common::StringBuffer,Common::StringBuffer>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::StringBuffer>,Common::ArrayOperations<Common::StringBuffer,Common::NoKey>> &,OSIntegration::Tools::ItemVerifier *)
0x180018555  mov     ebx, eax
0x180018557  test    eax, eax
0x180018559  jns     loc_1800185EB
0x18001855f  mov     rcx, [rbp+208h]; this
0x180018566  mov     r9d, eax; char *
0x180018569  lea     r8, aOnecoreAdminAp_75; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180018570  mov     edx, 74h ; 't'; void *
0x180018575  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001857a  nop
0x18001857b  mov     rcx, [rsp+300h+var_2C0]
0x180018580  test    rcx, rcx
0x180018583  jz      short loc_180018597
0x180018585  mov     [rsp+300h+var_2C0], r12
0x18001858a  mov     rax, [rcx]
0x18001858d  mov     rax, [rax+10h]
0x180018591  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018596  nop
0x180018597  jmp     loc_180018B52
0x18001859c  mov     [rsp+300h+var_2CF], r12b
0x1800185a1  xor     r9d, r9d
0x1800185a4  lea     r8, [rbp+200h+var_270]
0x1800185a8  lea     rdx, aLocalNameShare; "*[local-name()='ShareTarget']/*[local-n"...
0x1800185af  mov     rcx, r15
0x1800185b2  call    ?ConvertElementsIntoStringBufferArrayForQuery@Tools@OSIntegration@@YAJPEAUIXMLDOMElement@@PEBGAEAV?$Array@VStringBuffer@Common@@V?$ContainerOperations@VStringBuffer@Common@@V12@@2@VNoKey@2@V?$ContainerOperations@VNoKey@Common@@VStringBuffer@2@@2@V?$ArrayOperations@VStringBuffer@Common@@VNoKey@2@@2@@Common@@PEAVItemVerifier@12@@Z; OSIntegration::Tools::ConvertElementsIntoStringBufferArrayForQuery(IXMLDOMElement *,ushort const *,Common::Array<Common::StringBuffer,Common::ContainerOperations<Common::StringBuffer,Common::StringBuffer>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::StringBuffer>,Common::ArrayOperations<Common::StringBuffer,Common::NoKey>> &,OSIntegration::Tools::ItemVerifier *)
0x1800185b7  mov     dword ptr [rsp+300h+var_2B8], eax
0x1800185bb  test    eax, eax
0x1800185bd  js      loc_18001853E
0x1800185c3  lea     r8, [r14+48h]
0x1800185c7  lea     rdx, unk_1801AD130
0x1800185ce  lea     rcx, [rbp+200h+var_270]
0x1800185d2  call    ?FlattenStringBufferArrayToDeliminatedList@Tools@OSIntegration@@YAJAEAV?$Array@VStringBuffer@Common@@V?$ContainerOperations@VStringBuffer@Common@@V12@@2@VNoKey@2@V?$ContainerOperations@VNoKey@Common@@VStringBuffer@2@@2@V?$ArrayOperations@VStringBuffer@Common@@VNoKey@2@@2@@Common@@PEBUCOMMON_STRING@4@AEAVStringBuffer@4@@Z; OSIntegration::Tools::FlattenStringBufferArrayToDeliminatedList(Common::Array<Common::StringBuffer,Common::ContainerOperations<Common::StringBuffer,Common::StringBuffer>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::StringBuffer>,Common::ArrayOperations<Common::StringBuffer,Common::NoKey>> &,Common::COMMON_STRING const *,Common::StringBuffer &)
0x1800185d7  mov     ebx, eax
0x1800185d9  test    eax, eax
0x1800185db  jns     loc_18001853E
0x1800185e1  mov     edx, 6Bh ; 'k'
0x1800185e6  jmp     loc_180018B30
0x1800185eb  mov     [rsp+300h+var_2D0], r12b
0x1800185f0  or      eax, 0FFFFFFFFh
0x1800185f3  mov     dword ptr [rsp+300h+var_2C8], eax
0x1800185f7  mov     r13, [rsp+300h+var_290]
0x1800185fc  xor     r15d, r15d
0x1800185ff  lea     r10, off_1801AD0E0; "UniformResourceLocatorW"
0x180018606  mov     dword ptr [rsp+300h+var_2B0], r12d
0x18001860b  mov     edi, r12d
0x18001860e  mov     r12, [rbp+200h+var_280]
0x180018612  cmp     rdi, r12
0x180018615  jnb     loc_1800187C9
0x18001861b  lfence
0x18001861e  mov     rax, [r13+rdi*8+0]
0x180018623  mov     rax, [rax+8]
0x180018627  mov     [rbp+200h+var_250], rax
0x18001862b  mov     ebx, r15d
0x18001862e  xor     ecx, ecx
0x180018630  mov     esi, ecx
0x180018632  test    r15b, r15b
0x180018635  jnz     loc_1800186C5
0x18001863b  cmp     esi, 5
0x18001863e  jnb     short loc_180018696
0x180018640  movsxd  r12, esi
0x180018643  add     r12, r12
0x180018646  mov     [rsp+300h+bIgnoreCase], 1; bIgnoreCase
0x18001864e  or      r9d, 0FFFFFFFFh; cchCount2
0x180018652  mov     r8, rax; lpString2
0x180018655  or      edx, r9d; cchCount1
0x180018658  mov     rcx, [r10+r12*8+8]; lpString1
0x18001865d  call    cs:__imp_CompareStringOrdinal
0x180018664  nop     dword ptr [rax+rax+00h]
0x180018669  lea     r10, off_1801AD0E0; "UniformResourceLocatorW"
0x180018670  cmp     eax, 2
0x180018673  jnz     short loc_18001868C
0x180018675  mov     r8, [r10+r12*8]; unsigned __int16 *
0x180018679  mov     edx, 0FFh; unsigned __int64
0x18001867e  lea     rcx, [rbp+200h+String1]; unsigned __int16 *
0x180018682  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180018687  mov     ebx, eax
0x180018689  mov     r15b, 1
0x18001868c  inc     esi
0x18001868e  test    ebx, ebx
0x180018690  mov     rax, [rbp+200h+var_250]
0x180018694  jns     short loc_180018632
0x180018696  test    ebx, ebx
0x180018698  js      short loc_1800186B2
0x18001869a  test    r15b, r15b
0x18001869d  jnz     short loc_1800186C5
0x18001869f  mov     r8, rax; unsigned __int16 *
0x1800186a2  mov     edx, 0FFh; unsigned __int64
0x1800186a7  lea     rcx, [rbp+200h+String1]; unsigned __int16 *
0x1800186ab  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800186b0  mov     ebx, eax
0x1800186b2  xor     r15d, r15d
0x1800186b5  test    ebx, ebx
0x1800186b7  jns     short loc_1800186C8
0x1800186b9  mov     r9d, ebx
0x1800186bc  lea     edx, [r15+2Fh]
0x1800186c0  jmp     loc_1800187E9
0x1800186c5  xor     r15d, r15d
0x1800186c8  mov     r12, [rbp+200h+var_280]
0x1800186cc  cmp     rdi, r12
0x1800186cf  mov     rbx, r15
0x1800186d2  jnb     short loc_1800186D9
0x1800186d4  mov     rbx, [r13+rdi*8+0]
0x1800186d9  mov     rcx, [rbx+8]; void *
0x1800186dd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800186e2  mov     [rbx+8], r15
0x1800186e6  mov     [rbx], r15d
0x1800186e9  mov     [rbx+10h], r15d
0x1800186ed  cmp     rdi, r12
0x1800186f0  mov     r11, r15
0x1800186f3  jnb     short loc_1800186FA
0x1800186f5  mov     r11, [r13+rdi*8+0]
0x1800186fa  mov     r10d, 3FFFFFFEh
0x180018700  lea     rax, [rbp+200h+String1]
0x180018704  cmp     [rax], r15w
0x180018708  jz      short loc_180018714
0x18001870a  add     rax, 2
0x18001870e  sub     r10, 1
0x180018712  jnz     short loc_180018704
0x180018714  mov     rax, r10
0x180018717  neg     rax
0x18001871a  sbb     ebx, ebx
0x18001871c  not     ebx
0x18001871e  and     ebx, 80070057h
0x180018724  mov     r8, r10
0x180018727  mov     rax, r10
0x18001872a  mov     edx, 3FFFFFFEh
0x18001872f  sub     rdx, r10
0x180018732  neg     rax
0x180018735  sbb     r9, r9
0x180018738  and     r9, rdx
0x18001873b  neg     r8
0x18001873e  sbb     r8, r8
0x180018741  and     r8, r9; unsigned int
0x180018744  mov     rcx, [rbp+208h]; this
0x18001874b  test    r10, r10
0x18001874e  jz      short loc_1800187AB
0x180018750  lea     rdx, [rbp+200h+String1]; unsigned __int16 *
0x180018754  mov     rcx, r11; this
0x180018757  call    ?SetValue@StringBuffer@Common@@QEAAJPEBGK@Z; Common::StringBuffer::SetValue(ushort const *,ulong)
0x18001875c  mov     ebx, eax
0x18001875e  test    eax, eax
0x180018760  js      short loc_1800187BF
0x180018762  mov     [rsp+300h+bIgnoreCase], 1; bIgnoreCase
0x18001876a  or      edx, 0FFFFFFFFh; cchCount1
0x18001876d  mov     r9d, edx; cchCount2
0x180018770  lea     r8, aShellIdlistArr; "Shell IDList Array"
0x180018777  lea     rcx, [rbp+200h+String1]; lpString1
  ... truncated ...
```
