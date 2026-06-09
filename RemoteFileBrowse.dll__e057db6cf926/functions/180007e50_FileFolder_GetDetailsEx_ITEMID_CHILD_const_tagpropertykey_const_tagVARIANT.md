# FileFolder::GetDetailsEx(_ITEMID_CHILD const *,_tagpropertykey const *,tagVARIANT *)

- ea: `0x180007e50`
- end: `0x180008762`
- name: `?GetDetailsEx@FileFolder@@UEAAJPEFBU_ITEMID_CHILD@@PEBU_tagpropertykey@@PEAUtagVARIANT@@@Z`
- size: `2322`
- prototype: `__int64 __fastcall(FileFolder *this, const struct _ITEMID_CHILD *, const struct _tagpropertykey *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting`

## callees

- `0x180002030`
- `0x180002dc4`
- `0x1800056e0`
- `0x18000591c`
- `0x1800070cc`
- `0x1800070f0`
- `0x180007150`
- `0x18000762c`
- `0x18000798c`
- `0x180007e50`
- `0x1800088e4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000854b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180008569`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180008587`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000854b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180008569`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180008587`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180008184`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180008184`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180008480`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180008532`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180008480`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180008532`
- `OLEAUT32!__imp_SysAllocString` at `0x180008217`
- `OLEAUT32!__imp_SysAllocString` at `0x1800082a5`
- `OLEAUT32!__imp_SysAllocString` at `0x180008321`
- `OLEAUT32!__imp_SysAllocString` at `0x1800083ae`
- `OLEAUT32!__imp_SysAllocString` at `0x180008404`
- `OLEAUT32!__imp_SysAllocString` at `0x180008497`
- `OLEAUT32!__imp_SysAllocString` at `0x1800085d5`
- `OLEAUT32!__imp_SysAllocString` at `0x18000864f`
- `OLEAUT32!__imp_SysAllocString` at `0x180008217`
- `OLEAUT32!__imp_SysAllocString` at `0x1800082a5`
- `OLEAUT32!__imp_SysAllocString` at `0x180008321`
- `OLEAUT32!__imp_SysAllocString` at `0x1800083ae`
- `OLEAUT32!__imp_SysAllocString` at `0x180008404`
- `OLEAUT32!__imp_SysAllocString` at `0x180008497`
- `OLEAUT32!__imp_SysAllocString` at `0x1800085d5`
- `OLEAUT32!__imp_SysAllocString` at `0x18000864f`
- `OLEAUT32!__imp_VariantInit` at `0x180007ea2`
- `OLEAUT32!__imp_VariantInit` at `0x18000822d`
- `OLEAUT32!__imp_VariantInit` at `0x1800082bb`
- `OLEAUT32!__imp_VariantInit` at `0x180008337`
- `OLEAUT32!__imp_VariantInit` at `0x1800083c4`
- `OLEAUT32!__imp_VariantInit` at `0x18000841a`
- `OLEAUT32!__imp_VariantInit` at `0x1800084ad`
- `OLEAUT32!__imp_VariantInit` at `0x1800085ef`
- `OLEAUT32!__imp_VariantInit` at `0x180008669`
- `OLEAUT32!__imp_VariantInit` at `0x180007ea2`
- `OLEAUT32!__imp_VariantInit` at `0x18000822d`
- `OLEAUT32!__imp_VariantInit` at `0x1800082bb`
- `OLEAUT32!__imp_VariantInit` at `0x180008337`
- `OLEAUT32!__imp_VariantInit` at `0x1800083c4`
- `OLEAUT32!__imp_VariantInit` at `0x18000841a`
- `OLEAUT32!__imp_VariantInit` at `0x1800084ad`
- `OLEAUT32!__imp_VariantInit` at `0x1800085ef`
- `OLEAUT32!__imp_VariantInit` at `0x180008669`
- `PROPSYS!InitVariantFromBuffer` at `0x18000819a`
- `PROPSYS!InitVariantFromBuffer` at `0x18000819a`
- `PROPSYS!InitVariantFromFileTime` at `0x180007fa8`
- `PROPSYS!InitVariantFromFileTime` at `0x18000800f`
- `PROPSYS!InitVariantFromFileTime` at `0x180008076`
- `PROPSYS!InitVariantFromFileTime` at `0x180007fa8`
- `PROPSYS!InitVariantFromFileTime` at `0x18000800f`
- `PROPSYS!InitVariantFromFileTime` at `0x180008076`

## string_xrefs

- `0x180008202`: `prop:System.DateCreated;`
- `0x1800083a7`: `prop:System.Size;System.DateModified;System.DateCreated;System.DateAccessed;System.Attributes;`
- `0x1800083fd`: `prop:System.DateModified;System.DateCreated;System.DateAccessed;System.Attributes;`

## pseudocode

```c
__int64 __fastcall FileFolder::GetDetailsEx(
        FileFolder *this,
        const struct _ITEMID_CHILD *a2,
        const struct _tagpropertykey *a3,
        struct tagVARIANT *a4)
{
  __int64 v7; // rcx
  int v8; // esi
  const wchar_t *v9; // r14
  __int64 pid; // rcx
  HRESULT inited; // eax
  unsigned int v12; // ebx
  const char *v13; // r9
  __int64 result; // rax
  HRESULT v15; // eax
  unsigned int v16; // ebx
  HRESULT v17; // eax
  unsigned int v18; // ebx
  HRESULT v19; // eax
  unsigned int v20; // ebx
  const OLECHAR *v21; // rcx
  BSTR v22; // rax
  const OLECHAR *v23; // rcx
  BSTR v24; // rax
  BSTR v25; // rax
  BSTR v26; // rax
  BSTR v27; // rax
  wchar_t *v28; // rcx
  BSTR v29; // rax
  wchar_t *v30; // rax
  wchar_t *v31; // rbx
  __int64 v32; // rax
  const OLECHAR *v33; // rbx
  BSTR v34; // rax
  unsigned int v35; // ebx
  BSTR v36; // rax
  unsigned int v37; // ebx
  unsigned int v38; // eax
  int v39; // [rsp+20h] [rbp-308h]
  char *v40; // [rsp+28h] [rbp-300h]
  int v41; // [rsp+30h] [rbp-2F8h] BYREF
  wchar_t *Str[2]; // [rsp+38h] [rbp-2F0h] BYREF
  __m128i si128; // [rsp+48h] [rbp-2E0h]
  __int128 v44; // [rsp+58h] [rbp-2D0h]
  __m256i v45; // [rsp+68h] [rbp-2C0h] BYREF
  OLECHAR *psz[5]; // [rsp+88h] [rbp-2A0h] BYREF
  __int32 pv; // [rsp+B0h] [rbp-278h] BYREF
  __int64 v48; // [rsp+B4h] [rbp-274h]
  __int64 v49; // [rsp+BCh] [rbp-26Ch]
  __int64 v50; // [rsp+C4h] [rbp-264h]
  int v51; // [rsp+CCh] [rbp-25Ch]
  int v52; // [rsp+D0h] [rbp-258h]
  _BYTE v53[8]; // [rsp+D4h] [rbp-254h] BYREF
  _BYTE v54[548]; // [rsp+DCh] [rbp-24Ch] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+328h] [rbp+0h]

  try
  {
    if ( a2 && a3 && a4 )
    {
      VariantInit(a4);
      v8 = 4;
      if ( *(_WORD *)a2 && ((v8 = *(_DWORD *)((char *)a2 + 2), v8 == 3) || v8 == 2) )
      {
        v44 = 0;
        memset(&v45, 0, sizeof(v45));
        if ( *(_WORD *)a2 < 0x32u )
        {
          v38 = wil::verify_hresult<long>(0x80070057);
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x118,
            (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\Utility.h",
            (const char *)v38,
            v39);
        }
        v44 = *(_OWORD *)((char *)a2 + 2);
        v45 = *(__m256i *)((char *)a2 + 18);
        *(_OWORD *)Str = 0;
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        LOWORD(Str[0]) = 0;
        FileFolder::GetFileFolderName(v7, a2, Str);
        v9 = (const wchar_t *)Str;
        if ( si128.m128i_i64[1] > 7uLL )
          v9 = Str[0];
        pid = a3->pid;
        if ( (_DWORD)pid == PKEY_Size.pid
          && *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_Size.fmtid.Data1
          && *(_QWORD *)a3->fmtid.Data4 == *(_QWORD *)PKEY_Size.fmtid.Data4 )
        {
          if ( (_DWORD)v44 == 3 )
          {
            a4->vt = 21;
            a4->llVal = *((_QWORD *)&v44 + 1);
          }
        }
        else if ( (_DWORD)pid == PKEY_DateModified.pid
               && *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_DateModified.fmtid.Data1
               && *(_QWORD *)a3->fmtid.Data4 == *(_QWORD *)PKEY_DateModified.fmtid.Data4 )
        {
          inited = InitVariantFromFileTime((const FILETIME *)((char *)&v45.m256i_u64[2] + 4), a4);
          v12 = inited;
          if ( inited < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x2C9,
              (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\filefolder.cpp",
              (const char *)(unsigned int)inited,
              v39);
            std::wstring::~wstring((char **)Str);
            return v12;
          }
        }
        else if ( (_DWORD)pid == PKEY_DateCreated.pid
               && *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_DateCreated.fmtid.Data1
               && *(_QWORD *)a3->fmtid.Data4 == *(_QWORD *)PKEY_DateCreated.fmtid.Data4 )
        {
          v15 = InitVariantFromFileTime((const FILETIME *)((char *)v45.m256i_i64 + 4), a4);
          v16 = v15;
          if ( v15 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x2CD,
              (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\filefolder.cpp",
              (const char *)(unsigned int)v15,
              v39);
            std::wstring::~wstring((char **)Str);
            return v16;
          }
        }
        else if ( (_DWORD)pid == PKEY_DateAccessed.pid
               && *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_DateAccessed.fmtid.Data1
               && *(_QWORD *)a3->fmtid.Data4 == *(_QWORD *)PKEY_DateAccessed.fmtid.Data4 )
        {
          v17 = InitVariantFromFileTime((const FILETIME *)((char *)&v45.m256i_u64[1] + 4), a4);
          v18 = v17;
          if ( v17 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x2D1,
              (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\filefolder.cpp",
              (const char *)(unsigned int)v17,
              v39);
            std::wstring::~wstring((char **)Str);
            return v18;
          }
        }
        else if ( (_DWORD)pid == PKEY_FileAttributes.pid
               && *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_FileAttributes.fmtid.Data1
               && *(_QWORD *)a3->fmtid.Data4 == *(_QWORD *)PKEY_FileAttributes.fmtid.Data4 )
        {
          a4->vt = 19;
          a4->lVal = v45.m256i_i32[0];
        }
        else if ( (_DWORD)pid == PKEY_FindData.pid
               && *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_FindData.fmtid.Data1
               && *(_QWORD *)a3->fmtid.Data4 == *(_QWORD *)PKEY_FindData.fmtid.Data4 )
        {
          memset_0(v53, 0, 0x22Cu);
          pv = v45.m256i_i32[0];
          v51 = HIDWORD(v44);
          v52 = DWORD2(v44);
          v48 = *(__int64 *)((char *)v45.m256i_i64 + 4);
          v49 = *(__int64 *)((char *)&v45.m256i_i64[1] + 4);
          v50 = *(__int64 *)((char *)&v45.m256i_i64[2] + 4);
          _o_wcscpy_s(v54, 260);
          v19 = InitVariantFromBuffer(&pv, 0x250u, a4);
          v20 = v19;
          if ( v19 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x2E2,
              (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\filefolder.cpp",
              (const char *)(unsigned int)v19,
              v39);
            std::wstring::~wstring((char **)Str);
            return v20;
          }
        }
        else if ( (_DWORD)pid == PKEY_PropList_InfoTip.pid
               && *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_PropList_InfoTip.fmtid.Data1
               && *(_QWORD *)a3->fmtid.Data4 == *(_QWORD *)PKEY_PropList_InfoTip.fmtid.Data4 )
        {
          a4->vt = 8;
          v21 = L"prop:System.DisplayType;System.Size;System.DateModified;";
          if ( v8 != 3 )
            v21 = L"prop:System.DateCreated;";
          v22 = SysAllocString(v21);
          a4->llVal = (LONGLONG)v22;
          if ( !v22 )
          {
            VariantInit(a4);
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x2F6,
              (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\filefolder.cpp",
              (const char *)0x8007000ELL,
              v39);
            std::wstring::~wstring((char **)Str);
            return 2147942414LL;
          }
        }
        else if ( (_DWORD)pid == PKEY_PropList_TileInfo.pid
               && *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_PropList_TileInfo.fmtid.Data1
               && *(_QWORD *)a3->fmtid.Data4 == *(_QWORD *)PKEY_PropList_TileInfo.fmtid.Data4 )
        {
          a4->vt = 8;
          v23 = L"prop:System.DisplayType;System.Size;";
          if ( v8 != 3 )
            v23 = L"prop:System.DisplayType;System.DateModified;";
          v24 = SysAllocString(v23);
          a4->llVal = (LONGLONG)v24;
          if ( !v24 )
          {
            VariantInit(a4);
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x30A,
              (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\filefolder.cpp",
              (const char *)0x8007000ELL,
              v39);
            std::wstring::~wstring((char **)Str);
            return 2147942414LL;
          }
        }
        else if ( (_DWORD)pid == PKEY_PropList_PreviewTitle.pid
               && *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_PropList_PreviewTitle.fmtid.Data1
               && *(_QWORD *)a3->fmtid.Data4 == *(_QWORD *)PKEY_PropList_PreviewTitle.fmtid.Data4 )
        {
          a4->vt = 8;
          v25 = SysAllocString(L"prop:System.DisplayName;System.DisplayType;");
          a4->llVal = (LONGLONG)v25;
          if ( !v25 )
          {
            VariantInit(a4);
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x312,
              (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\filefolder.cpp",
              (const char *)0x8007000ELL,
              v39);
            std::wstring::~wstring((char **)Str);
            return 2147942414LL;
          }
        }
        else if ( (_DWORD)pid == PKEY_PropList_PreviewDetails.pid
               && *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_PropList_PreviewDetails.fmtid.Data1
               && *(_QWORD *)a3->fmtid.Data4 == *(_QWORD *)PKEY_PropList_PreviewDetails.fmtid.Data4 )
        {
          a4->vt = 8;
          if ( v8 == 3 )
          {
            v26 = SysAllocString(L"prop:System.Size;System.DateModified;System.DateCreated;System.DateAccessed;System.Attributes;");
            a4->llVal = (LONGLONG)v26;
            if ( !v26 )
            {
              VariantInit(a4);
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x31F,
                (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\filefolder.cpp",
                (const char *)0x8007000ELL,
                v39);
              std::wstring::~wstring((char **)Str);
              return 2147942414LL;
            }
          }
          else
          {
            v27 = SysAllocString(L"prop:System.DateModified;System.DateCreated;System.DateAccessed;System.Attributes;");
            a4->llVal = (LONGLONG)v27;
            if ( !v27 )
            {
              VariantInit(a4);
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x329,
                (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\filefolder.cpp",
                (const char *)0x8007000ELL,
                v39);
              std::wstring::~wstring((char **)Str);
              return 2147942414LL;
            }
          }
        }
        else if ( (_DWORD)pid == PKEY_FileExtension.pid
               && *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_FileExtension.fmtid.Data1
               && *(_QWORD *)a3->fmtid.Data4 == *(_QWORD *)PKEY_FileExtension.fmtid.Data4 )
        {
          v28 = wcsrchr(v9, 0x2Eu);
          if ( v28 )
          {
            a4->vt = 8;
            v29 = SysAllocString(v28);
            a4->llVal = (LONGLONG)v29;
            if ( !v29 )
            {
              VariantInit(a4);
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x331,
                (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\filefolder.cpp",
                (const char *)0x8007000ELL,
                v39);
              std::wstring::~wstring((char **)Str);
              return 2147942414LL;
            }
          }
        }
        else if ( (_DWORD)pid == PKEY_ItemTypeText.pid
               && *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_ItemTypeText.fmtid.Data1
               && *(_QWORD *)a3->fmtid.Data4 == *(_QWORD *)PKEY_ItemTypeText.fmtid.Data4 )
        {
          v41 = 120;
          if ( v8 == 2 )
          {
            v41 = 119;
          }
          else
          {
            v30 = wcsrchr(v9, 0x2Eu);
            if ( v30 )
            {
              v31 = v30 + 1;
              if ( (unsigned int)_o__wcsicmp(v30 + 1, L"VHD") )
              {
                if ( (unsigned int)_o__wcsicmp(v31, L"VFD") )
                {
                  if ( !(unsigned int)_o__wcsicmp(v31, L"ISO") )
                    v41 = 118;
                }
                else
                {
                  v41 = 117;
                }
              }
              else
              {
                v41 = 116;
              }
            }
          }
          v32 = std::map<int,std::wstring>::operator[](pid, &v41);
          std::wstring::wstring((__int64)psz, v32);
          v33 = (const OLECHAR *)psz;
          if ( psz[3] > (OLECHAR *)7 )
            v33 = psz[0];
          a4->vt = 8;
          v34 = SysAllocString(v33);
          a4->llVal = (LONGLONG)v34;
          if ( !v34 )
          {
            v35 = v33 != 0 ? 0xFFFFFFB7 : 0;
            VariantInit(a4);
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x353,
              (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\filefolder.cpp",
              (const char *)(v35 - 2147024809),
              v39);
            std::wstring::~wstring((char **)psz);
            std::wstring::~wstring((char **)Str);
            return v35 - 2147024809;
          }
          std::wstring::~wstring((char **)psz);
        }
        else
        {
          a4->vt = 8;
          v36 = SysAllocString(v9);
          a4->llVal = (LONGLONG)v36;
          if ( !v36 )
          {
            v37 = v9 != 0 ? 0xFFFFFFB7 : 0;
            VariantInit(a4);
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x357,
              (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\filefolder.cpp",
              (const char *)(v37 - 2147024809),
              v39);
            std::wstring::~wstring((char **)Str);
            return v37 - 2147024809;
          }
        }
        std::wstring::~wstring((char **)Str);
        result = 0;
      }
      else
      {
        LODWORD(v40) = v8;
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x35C,
          (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\filefolder.cpp",
          (const char *)0x80070057LL,
          (int)"unknown PIDL type %u",
          v40);
        result = 2147942487LL;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2AE,
        (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\filefolder.cpp",
        (const char *)0x80070057LL,
        v39);
      result = 2147942487LL;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x35F,
                           (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\filefolder.cpp",
                           v13);
  }
  return result;
}

```

## disassembly

```asm
0x180007e50  mov     [rsp+arg_0], rbx
0x180007e55  mov     [rsp+arg_10], rsi
0x180007e5a  push    rdi
0x180007e5b  push    r14
0x180007e5d  push    r15
0x180007e5f  sub     rsp, 310h
0x180007e66  mov     rax, cs:__security_cookie
0x180007e6d  xor     rax, rsp
0x180007e70  mov     [rsp+328h+var_28], rax
0x180007e78  mov     rdi, r9
0x180007e7b  mov     rbx, r8
0x180007e7e  mov     r14, rdx
0x180007e81  xor     r15d, r15d
0x180007e84  test    rdx, rdx
0x180007e87  jz      loc_1800086ED
0x180007e8d  test    rbx, rbx
0x180007e90  jz      loc_1800086ED
0x180007e96  test    r9, r9
0x180007e99  jz      loc_1800086ED
0x180007e9f  mov     rcx, r9; pvarg
0x180007ea2  call    cs:__imp_VariantInit
0x180007ea8  lea     esi, [r15+4]
0x180007eac  cmp     [r14], r15w
0x180007eb0  jz      loc_1800086B1
0x180007eb6  mov     esi, [r14+2]
0x180007eba  cmp     esi, 3
0x180007ebd  jz      short loc_180007EC8
0x180007ebf  cmp     esi, 2
0x180007ec2  jnz     loc_1800086B1
0x180007ec8  xorps   xmm0, xmm0
0x180007ecb  movups  [rsp+328h+var_2D0], xmm0
0x180007ed0  movups  xmmword ptr [rsp+328h+var_2C0.dwLowDateTime], xmm0
0x180007ed5  movups  xmmword ptr [rsp+328h+pft.dwLowDateTime], xmm0
0x180007eda  cmp     word ptr [r14], 32h ; '2'
0x180007edf  jb      loc_18000873A
0x180007ee5  movups  xmm0, xmmword ptr [r14+2]
0x180007eea  movups  [rsp+328h+var_2D0], xmm0
0x180007eef  movups  xmm1, xmmword ptr [r14+12h]
0x180007ef4  movups  xmmword ptr [rsp+328h+var_2C0.dwLowDateTime], xmm1
0x180007ef9  movups  xmm0, xmmword ptr [r14+22h]
0x180007efe  movups  xmmword ptr [rsp+328h+pft.dwLowDateTime], xmm0
0x180007f03  xorps   xmm1, xmm1
0x180007f06  movups  xmmword ptr [rsp+328h+Str], xmm1
0x180007f0b  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x180007f13  movdqu  [rsp+328h+var_2E0], xmm0
0x180007f19  mov     word ptr [rsp+328h+Str], r15w
0x180007f1f  lea     r8, [rsp+328h+Str]
0x180007f24  mov     rdx, r14
0x180007f27  call    ?GetFileFolderName@FileFolder@@IEAAXPEFBU_ITEMIDLIST@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; FileFolder::GetFileFolderName(_ITEMIDLIST const *,std::wstring &)
0x180007f2c  lea     r14, [rsp+328h+Str]
0x180007f31  cmp     qword ptr [rsp+328h+var_2E0+8], 7
0x180007f37  cmova   r14, [rsp+328h+Str]
0x180007f3d  mov     ecx, [rbx+10h]
0x180007f40  cmp     ecx, cs:PKEY_Size.pid
0x180007f46  jnz     short loc_180007F7F
0x180007f48  mov     rax, [rbx]
0x180007f4b  cmp     rax, qword ptr cs:PKEY_Size.fmtid.Data1
0x180007f52  jnz     short loc_180007F7F
0x180007f54  mov     rax, [rbx+8]
0x180007f58  cmp     rax, qword ptr cs:PKEY_Size.fmtid.Data4
0x180007f5f  jnz     short loc_180007F7F
0x180007f61  cmp     dword ptr [rsp+328h+var_2D0], 3
0x180007f66  jnz     loc_1800086A2
0x180007f6c  mov     word ptr [rdi], 15h
0x180007f71  mov     rax, qword ptr [rsp+328h+var_2D0+8]
0x180007f76  mov     [rdi+8], rax
0x180007f7a  jmp     loc_1800086A2
0x180007f7f  cmp     ecx, cs:PKEY_DateModified.pid
0x180007f85  jnz     short loc_180007FE6
0x180007f87  mov     rax, [rbx]
0x180007f8a  cmp     rax, qword ptr cs:PKEY_DateModified.fmtid.Data1
0x180007f91  jnz     short loc_180007FE6
0x180007f93  mov     rax, [rbx+8]
0x180007f97  cmp     rax, qword ptr cs:PKEY_DateModified.fmtid.Data4
0x180007f9e  jnz     short loc_180007FE6
0x180007fa0  mov     rdx, rdi; pvar
0x180007fa3  lea     rcx, [rsp+328h+pft.dwHighDateTime]; pft
0x180007fa8  call    cs:__imp_InitVariantFromFileTime
0x180007fae  mov     ebx, eax
0x180007fb0  test    eax, eax
0x180007fb2  jns     loc_1800086A2
0x180007fb8  mov     rcx, [rsp+328h]; this
0x180007fc0  mov     r9d, eax; char *
0x180007fc3  lea     r8, aVmUxUiRemotefi_8; "vm\\ux\\ui\\remotefilebrowse\\filefolde"...
0x180007fca  mov     edx, 2C9h; void *
0x180007fcf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007fd4  nop
0x180007fd5  lea     rcx, [rsp+328h+Str]
0x180007fda  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180007fdf  mov     eax, ebx
0x180007fe1  jmp     loc_180008711
0x180007fe6  cmp     ecx, cs:PKEY_DateCreated.pid
0x180007fec  jnz     short loc_18000804D
0x180007fee  mov     rax, [rbx]
0x180007ff1  cmp     rax, qword ptr cs:PKEY_DateCreated.fmtid.Data1
0x180007ff8  jnz     short loc_18000804D
0x180007ffa  mov     rax, [rbx+8]
0x180007ffe  cmp     rax, qword ptr cs:PKEY_DateCreated.fmtid.Data4
0x180008005  jnz     short loc_18000804D
0x180008007  mov     rdx, rdi; pvar
0x18000800a  lea     rcx, [rsp+328h+var_2C0.dwHighDateTime]; pft
0x18000800f  call    cs:__imp_InitVariantFromFileTime
0x180008015  mov     ebx, eax
0x180008017  test    eax, eax
0x180008019  jns     loc_1800086A2
0x18000801f  mov     rcx, [rsp+328h]; this
0x180008027  mov     r9d, eax; char *
0x18000802a  lea     r8, aVmUxUiRemotefi_8; "vm\\ux\\ui\\remotefilebrowse\\filefolde"...
0x180008031  mov     edx, 2CDh; void *
0x180008036  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000803b  nop
0x18000803c  lea     rcx, [rsp+328h+Str]
0x180008041  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180008046  mov     eax, ebx
0x180008048  jmp     loc_180008711
0x18000804d  cmp     ecx, cs:PKEY_DateAccessed.pid
0x180008053  jnz     short loc_1800080B4
0x180008055  mov     rax, [rbx]
0x180008058  cmp     rax, qword ptr cs:PKEY_DateAccessed.fmtid.Data1
0x18000805f  jnz     short loc_1800080B4
0x180008061  mov     rax, [rbx+8]
0x180008065  cmp     rax, qword ptr cs:PKEY_DateAccessed.fmtid.Data4
0x18000806c  jnz     short loc_1800080B4
0x18000806e  mov     rdx, rdi; pvar
0x180008071  lea     rcx, [rsp+328h+var_2C0.dwHighDateTime+8]; pft
0x180008076  call    cs:__imp_InitVariantFromFileTime
0x18000807c  mov     ebx, eax
0x18000807e  test    eax, eax
0x180008080  jns     loc_1800086A2
0x180008086  mov     rcx, [rsp+328h]; this
0x18000808e  mov     r9d, eax; char *
0x180008091  lea     r8, aVmUxUiRemotefi_8; "vm\\ux\\ui\\remotefilebrowse\\filefolde"...
0x180008098  mov     edx, 2D1h; void *
0x18000809d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800080a2  nop
0x1800080a3  lea     rcx, [rsp+328h+Str]
0x1800080a8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800080ad  mov     eax, ebx
0x1800080af  jmp     loc_180008711
0x1800080b4  cmp     ecx, cs:PKEY_FileAttributes.pid
0x1800080ba  jnz     short loc_1800080E6
0x1800080bc  mov     rax, [rbx]
0x1800080bf  cmp     rax, qword ptr cs:PKEY_FileAttributes.fmtid.Data1
0x1800080c6  jnz     short loc_1800080E6
0x1800080c8  mov     rax, [rbx+8]
0x1800080cc  cmp     rax, qword ptr cs:PKEY_FileAttributes.fmtid.Data4
0x1800080d3  jnz     short loc_1800080E6
0x1800080d5  mov     word ptr [rdi], 13h
0x1800080da  mov     eax, [rsp+328h+var_2C0.dwLowDateTime]
0x1800080de  mov     [rdi+8], eax
0x1800080e1  jmp     loc_1800086A2
0x1800080e6  cmp     ecx, cs:PKEY_FindData.pid
0x1800080ec  jnz     loc_1800081D8
0x1800080f2  mov     rax, [rbx]
0x1800080f5  cmp     rax, qword ptr cs:PKEY_FindData.fmtid.Data1
0x1800080fc  jnz     loc_1800081D8
0x180008102  mov     rax, [rbx+8]
0x180008106  cmp     rax, qword ptr cs:PKEY_FindData.fmtid.Data4
0x18000810d  jnz     loc_1800081D8
0x180008113  xor     edx, edx; Val
0x180008115  mov     r8d, 22Ch; Size
0x18000811b  lea     rcx, [rsp+328h+var_254]; void *
0x180008123  call    memset_0
0x180008128  mov     eax, [rsp+328h+var_2C0.dwLowDateTime]
0x18000812c  mov     [rsp+328h+pv], eax
0x180008133  mov     rcx, qword ptr [rsp+328h+var_2D0+8]
0x180008138  mov     rax, rcx
0x18000813b  shr     rax, 20h
0x18000813f  mov     [rsp+328h+var_25C], eax
0x180008146  mov     [rsp+328h+var_258], ecx
0x18000814d  mov     rax, qword ptr [rsp+328h+var_2C0.dwHighDateTime]
0x180008152  mov     [rsp+328h+var_274], rax
0x18000815a  mov     rax, qword ptr [rsp+328h+var_2C0.dwHighDateTime+8]
0x18000815f  mov     [rsp+328h+var_26C], rax
0x180008167  mov     rax, qword ptr [rsp+328h+pft.dwHighDateTime]
0x18000816c  mov     [rsp+328h+var_264], rax
0x180008174  mov     r8, r14
0x180008177  mov     edx, 104h
0x18000817c  lea     rcx, [rsp+328h+var_24C]
0x180008184  call    cs:__imp__o_wcscpy_s
0x18000818a  mov     r8, rdi; pvar
0x18000818d  mov     edx, 250h; cb
0x180008192  lea     rcx, [rsp+328h+pv]; pv
0x18000819a  call    cs:__imp_InitVariantFromBuffer
0x1800081a0  mov     ebx, eax
0x1800081a2  test    eax, eax
0x1800081a4  jns     loc_1800086A2
0x1800081aa  mov     rcx, [rsp+328h]; this
0x1800081b2  mov     r9d, eax; char *
0x1800081b5  lea     r8, aVmUxUiRemotefi_8; "vm\\ux\\ui\\remotefilebrowse\\filefolde"...
0x1800081bc  mov     edx, 2E2h; void *
0x1800081c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800081c6  nop
0x1800081c7  lea     rcx, [rsp+328h+Str]
0x1800081cc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800081d1  mov     eax, ebx
0x1800081d3  jmp     loc_180008711
0x1800081d8  cmp     ecx, cs:PKEY_PropList_InfoTip.pid
0x1800081de  jnz     loc_180008266
0x1800081e4  mov     rax, [rbx]
0x1800081e7  cmp     rax, qword ptr cs:PKEY_PropList_InfoTip.fmtid.Data1
0x1800081ee  jnz     short loc_180008266
0x1800081f0  mov     rax, [rbx+8]
0x1800081f4  cmp     rax, qword ptr cs:PKEY_PropList_InfoTip.fmtid.Data4
0x1800081fb  jnz     short loc_180008266
0x1800081fd  mov     word ptr [rdi], 8
0x180008202  lea     rax, aPropSystemDate_0; "prop:System.DateCreated;"
0x180008209  lea     rcx, aPropSystemDisp_1; "prop:System.DisplayType;System.Size;Sys"...
0x180008210  cmp     esi, 3
0x180008213  cmovnz  rcx, rax; psz
0x180008217  call    cs:__imp_SysAllocString
0x18000821d  mov     [rdi+8], rax
0x180008221  test    rax, rax
0x180008224  jnz     loc_1800086A2
0x18000822a  mov     rcx, rdi; pvarg
0x18000822d  call    cs:__imp_VariantInit
0x180008233  mov     rcx, [rsp+328h]; this
0x18000823b  mov     ebx, 8007000Eh
0x180008240  mov     r9d, ebx; char *
0x180008243  lea     r8, aVmUxUiRemotefi_8; "vm\\ux\\ui\\remotefilebrowse\\filefolde"...
0x18000824a  mov     edx, 2F6h; void *
0x18000824f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008254  nop
0x180008255  lea     rcx, [rsp+328h+Str]
0x18000825a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000825f  mov     eax, ebx
0x180008261  jmp     loc_180008711
0x180008266  cmp     ecx, cs:PKEY_PropList_TileInfo.pid
0x18000826c  jnz     loc_1800082F4
0x180008272  mov     rax, [rbx]
0x180008275  cmp     rax, qword ptr cs:PKEY_PropList_TileInfo.fmtid.Data1
0x18000827c  jnz     short loc_1800082F4
0x18000827e  mov     rax, [rbx+8]
0x180008282  cmp     rax, qword ptr cs:PKEY_PropList_TileInfo.fmtid.Data4
0x180008289  jnz     short loc_1800082F4
0x18000828b  mov     word ptr [rdi], 8
0x180008290  lea     rax, aPropSystemDisp_0; "prop:System.DisplayType;System.DateModi"...
0x180008297  lea     rcx, aPropSystemDisp; "prop:System.DisplayType;System.Size;"
0x18000829e  cmp     esi, 3
0x1800082a1  cmovnz  rcx, rax; psz
0x1800082a5  call    cs:__imp_SysAllocString
0x1800082ab  mov     [rdi+8], rax
0x1800082af  test    rax, rax
0x1800082b2  jnz     loc_1800086A2
0x1800082b8  mov     rcx, rdi; pvarg
0x1800082bb  call    cs:__imp_VariantInit
0x1800082c1  mov     rcx, [rsp+328h]; this
0x1800082c9  mov     ebx, 8007000Eh
0x1800082ce  mov     r9d, ebx; char *
0x1800082d1  lea     r8, aVmUxUiRemotefi_8; "vm\\ux\\ui\\remotefilebrowse\\filefolde"...
0x1800082d8  mov     edx, 30Ah; void *
0x1800082dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800082e2  nop
0x1800082e3  lea     rcx, [rsp+328h+Str]
0x1800082e8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800082ed  mov     eax, ebx
0x1800082ef  jmp     loc_180008711
0x1800082f4  cmp     ecx, cs:PKEY_PropList_PreviewTitle.pid
0x1800082fa  jnz     short loc_180008370
0x1800082fc  mov     rax, [rbx]
0x1800082ff  cmp     rax, qword ptr cs:PKEY_PropList_PreviewTitle.fmtid.Data1
0x180008306  jnz     short loc_180008370
0x180008308  mov     rax, [rbx+8]
0x18000830c  cmp     rax, qword ptr cs:PKEY_PropList_PreviewTitle.fmtid.Data4
0x180008313  jnz     short loc_180008370
0x180008315  mov     word ptr [rdi], 8
0x18000831a  lea     rcx, aPropSystemDisp_3; "prop:System.DisplayName;System.DisplayT"...
0x180008321  call    cs:__imp_SysAllocString
0x180008327  mov     [rdi+8], rax
0x18000832b  test    rax, rax
0x18000832e  jnz     loc_1800086A2
0x180008334  mov     rcx, rdi; pvarg
0x180008337  call    cs:__imp_VariantInit
0x18000833d  mov     rcx, [rsp+328h]; this
0x180008345  mov     ebx, 8007000Eh
0x18000834a  mov     r9d, ebx; char *
0x18000834d  lea     r8, aVmUxUiRemotefi_8; "vm\\ux\\ui\\remotefilebrowse\\filefolde"...
0x180008354  mov     edx, 312h; void *
0x180008359  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000835e  nop
0x18000835f  lea     rcx, [rsp+328h+Str]
0x180008364  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180008369  mov     eax, ebx
0x18000836b  jmp     loc_180008711
0x180008370  cmp     ecx, cs:PKEY_PropList_PreviewDetails.pid
0x180008376  jnz     loc_180008453
0x18000837c  mov     rax, [rbx]
0x18000837f  cmp     rax, qword ptr cs:PKEY_PropList_PreviewDetails.fmtid.Data1
0x180008386  jnz     loc_180008453
0x18000838c  mov     rax, [rbx+8]
0x180008390  cmp     rax, qword ptr cs:PKEY_PropList_PreviewDetails.fmtid.Data4
0x180008397  jnz     loc_180008453
0x18000839d  mov     word ptr [rdi], 8
0x1800083a2  cmp     esi, 3
0x1800083a5  jnz     short loc_1800083FD
0x1800083a7  lea     rcx, aPropSystemSize; "prop:System.Size;System.DateModified;Sy"...
0x1800083ae  call    cs:__imp_SysAllocString
0x1800083b4  mov     [rdi+8], rax
0x1800083b8  test    rax, rax
0x1800083bb  jnz     loc_1800086A2
  ... truncated ...
```
