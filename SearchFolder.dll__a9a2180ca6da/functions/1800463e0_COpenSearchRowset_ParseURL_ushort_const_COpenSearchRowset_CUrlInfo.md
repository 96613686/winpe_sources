# COpenSearchRowset::_ParseURL(ushort const *,COpenSearchRowset::CUrlInfo *)

- ea: `0x1800463e0`
- end: `0x180046a02`
- name: `?_ParseURL@COpenSearchRowset@@AEAAJPEBGPEAUCUrlInfo@1@@Z`
- size: `1570`
- prototype: `__int64 __fastcall(COpenSearchRowset *__hidden this, const unsigned __int16 *, struct COpenSearchRowset::CUrlInfo *)`
- caller_count: `4`
- callee_count: `15`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180043830`
- `0x180043b28`
- `0x180043dd4`
- `0x180047a8c`

## callees

- `0x1800054b0`
- `0x180005c88`
- `0x180006900`
- `0x180006e10`
- `0x1800076dc`
- `0x18000ecc4`
- `0x1800120a4`
- `0x1800129f8`
- `0x18002409c`
- `0x180041da4`
- `0x1800463e0`
- `0x180046cf4`
- `0x180046d84`
- `0x18004faa0`
- `0x180051010`

## import_xrefs

- `SHLWAPI!PathFindExtensionW` at `0x18004658f`
- `SHLWAPI!PathFindExtensionW` at `0x18004658f`
- `SHLWAPI!UrlIsW` at `0x180046441`
- `SHLWAPI!UrlIsW` at `0x1800464fc`
- `SHLWAPI!UrlIsW` at `0x180046441`
- `SHLWAPI!UrlIsW` at `0x1800464fc`
- `SHLWAPI!PathFindFileNameW` at `0x18004656e`
- `SHLWAPI!PathFindFileNameW` at `0x1800465f2`
- `SHLWAPI!PathFindFileNameW` at `0x18004664f`
- `SHLWAPI!PathFindFileNameW` at `0x18004656e`
- `SHLWAPI!PathFindFileNameW` at `0x1800465f2`
- `SHLWAPI!PathFindFileNameW` at `0x18004664f`
- `SHLWAPI!UrlEscapeW` at `0x180046464`
- `SHLWAPI!UrlEscapeW` at `0x180046464`
- `SHLWAPI!PathCreateFromUrlW` at `0x180046519`
- `SHLWAPI!PathCreateFromUrlW` at `0x180046519`
- `SHLWAPI!PathIsRootW` at `0x1800465b0`
- `SHLWAPI!PathIsRootW` at `0x1800465b0`
- `SHLWAPI!PathRemoveBackslashW` at `0x1800465c2`
- `SHLWAPI!PathRemoveBackslashW` at `0x1800465c2`
- `SHLWAPI!PathRemoveFileSpecW` at `0x1800465cc`
- `SHLWAPI!PathRemoveFileSpecW` at `0x180046613`
- `SHLWAPI!PathRemoveFileSpecW` at `0x1800465cc`
- `SHLWAPI!PathRemoveFileSpecW` at `0x180046613`
- `SHLWAPI!StrRChrW` at `0x18004675b`
- `SHLWAPI!StrRChrW` at `0x1800467b8`
- `SHLWAPI!StrRChrW` at `0x18004684f`
- `SHLWAPI!StrRChrW` at `0x18004687a`
- `SHLWAPI!StrRChrW` at `0x18004675b`
- `SHLWAPI!StrRChrW` at `0x1800467b8`
- `SHLWAPI!StrRChrW` at `0x18004684f`
- `SHLWAPI!StrRChrW` at `0x18004687a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800468f7`
- `OLEAUT32!__imp_SysFreeString` at `0x18004697c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800468f7`
- `OLEAUT32!__imp_SysFreeString` at `0x18004697c`
- `OLEAUT32!__imp_SysStringLen` at `0x18004672e`
- `OLEAUT32!__imp_SysStringLen` at `0x180046745`
- `OLEAUT32!__imp_SysStringLen` at `0x18004672e`
- `OLEAUT32!__imp_SysStringLen` at `0x180046745`
- `ext-ms-win-core-iuri-l1-1-0!CreateUri` at `0x1800464ad`
- `ext-ms-win-core-iuri-l1-1-0!CreateUri` at `0x1800464ad`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall COpenSearchRowset::_ParseURL(
        COpenSearchRowset *this,
        const unsigned __int16 *a2,
        struct COpenSearchRowset::CUrlInfo *a3)
{
  HRESULT v5; // eax
  HRESULT Uri; // ebx
  IUri **v7; // rax
  HRESULT v8; // eax
  LPWSTR FileNameW; // rax
  __int64 v10; // rdx
  __int64 v11; // rcx
  const unsigned __int16 *ExtensionW; // rax
  __int64 v13; // rdx
  __int64 v14; // rcx
  const unsigned __int16 *v15; // rax
  __int64 v16; // rdx
  __int64 v17; // rcx
  unsigned __int16 **v18; // rdx
  WCHAR *v19; // rcx
  const wchar_t *v20; // r8
  UINT v21; // r12d
  UINT v22; // r15d
  PWSTR v23; // rax
  unsigned __int64 v24; // rdi
  __int64 v25; // rax
  unsigned __int64 v26; // rcx
  unsigned __int64 v27; // rdx
  unsigned __int64 v28; // rcx
  PWSTR v29; // rsi
  const WCHAR *v30; // rax
  const WCHAR *v31; // rsi
  PWSTR v32; // rax
  const unsigned __int16 *v33; // rsi
  COpenSearchRowset *v34; // rcx
  COpenSearchRowset *v35; // rcx
  __int128 v36; // xmm1
  __int128 v37; // xmm0
  __int128 v38; // xmm1
  __int64 v40; // [rsp+20h] [rbp-E0h] BYREF
  DWORD pcchPath[2]; // [rsp+28h] [rbp-D8h] BYREF
  unsigned __int16 *v42[2]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 *v43[2]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v44[2]; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR v45[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v46; // [rsp+70h] [rbp-90h] BYREF
  DWORD pcchEscaped; // [rsp+80h] [rbp-80h] BYREF
  BSTR pbstr; // [rsp+88h] [rbp-78h] BYREF
  WCHAR pszPath[264]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR pszEscaped[2088]; // [rsp+2A0h] [rbp+1A0h] BYREF

  COpenSearchRowset::CUrlInfo::Clear(a3);
  memset_0(v42, 0, 0x48u);
  pcchEscaped = 2084;
  if ( UrlIsW(a2, URLIS_URL) )
    v5 = UrlEscapeW(a2, pszEscaped, &pcchEscaped, 0x40000u);
  else
    v5 = StringCchCopyW(pszEscaped, 0x824u, a2);
  Uri = v5;
  if ( v5 < 0 )
    goto LABEL_79;
  ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v40);
  v7 = (IUri **)ATL::CComPtrBase<IXMLDOMDocument>::operator&(&v40);
  Uri = CreateUri(pszEscaped, 4u, 0, v7);
  if ( Uri < 0 )
    goto LABEL_76;
  Uri = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v40 + 192LL))(v40, &v46);
  if ( Uri < 0 )
    goto LABEL_76;
  if ( (_DWORD)v46 == 9 )
  {
    pcchPath[0] = 260;
    if ( UrlIsW(a2, URLIS_FILEURL) )
      v8 = PathCreateFromUrlW(pszEscaped, pszPath, pcchPath, 0x40000u);
    else
      v8 = StringCchCopyW(pszPath, 0x104u, a2);
    Uri = v8;
    if ( v8 >= 0 )
    {
      Uri = SHSysAllocString(pszPath, v43);
      if ( Uri >= 0 )
      {
        Uri = SHSysAllocString(pszPath, v42);
        if ( Uri >= 0 )
        {
          FileNameW = PathFindFileNameW(pszPath);
          Uri = _AllocString<CTCoAllocPolicy>(v11, v10, FileNameW, &v44[1]);
          if ( Uri >= 0 )
          {
            ExtensionW = PathFindExtensionW(pszPath);
            Uri = SHSysAllocString(ExtensionW, &v42[1]);
            if ( Uri >= 0 && !PathIsRootW(pszPath) )
            {
              PathRemoveBackslashW(pszPath);
              if ( PathRemoveFileSpecW(pszPath) )
              {
                Uri = _AllocString<CTCoAllocPolicy>(v14, v13, pszPath, v45);
                if ( Uri >= 0 )
                {
                  v15 = PathFindFileNameW(pszPath);
                  Uri = SHSysAllocString(v15, &v43[1]);
                  if ( Uri >= 0 )
                  {
                    if ( !PathRemoveFileSpecW(pszPath) )
                    {
LABEL_27:
                      Uri = _AllocString<CTCoAllocPolicy>(v17, v16, v45[0], &v45[1]);
                      goto LABEL_76;
                    }
                    v18 = v44;
                    v19 = pszPath;
LABEL_26:
                    Uri = SHSysAllocString(v19, v18);
                    if ( Uri < 0 )
                      goto LABEL_76;
                    goto LABEL_27;
                  }
                }
              }
              else
              {
                v20 = &psz;
                if ( v42[0] )
                  v20 = v42[0];
                Uri = _AllocString<CTCoAllocPolicy>(v14, v13, v20, v45);
                if ( Uri >= 0 )
                {
                  v19 = PathFindFileNameW(v45[0]);
                  v18 = &v43[1];
                  goto LABEL_26;
                }
              }
            }
          }
        }
      }
    }
  }
  else
  {
    Uri = (*(__int64 (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v40 + 56LL))(v40, v42);
    if ( Uri >= 0 )
    {
      Uri = StringCchCopyW(pszEscaped, 0x824u, a2);
      if ( Uri >= 0 )
      {
        (*(void (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v40 + 88LL))(v40, &v42[1]);
        pbstr = 0;
        Uri = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v40 + 64LL))(v40, &pbstr);
        if ( Uri >= 0 )
        {
          *(_QWORD *)pcchPath = 0;
          Uri = (*(__int64 (__fastcall **)(__int64, DWORD *))(*(_QWORD *)v40 + 152LL))(v40, pcchPath);
          if ( Uri >= 0 )
          {
            if ( *(_QWORD *)pcchPath )
              v21 = SysStringLen(*(BSTR *)pcchPath);
            else
              v21 = 0;
            if ( pbstr )
              v22 = SysStringLen(pbstr);
            else
              v22 = 0;
            v23 = StrRChrW(pszEscaped, 0, 0x3Fu);
            if ( v23 )
              *v23 = 0;
            v24 = -1;
            v25 = -1;
            do
              ++v25;
            while ( pszEscaped[v25] );
            if ( pszPath[v25 + 263] == 47 )
            {
              v26 = 2 * v25 - 2;
              if ( v26 >= 0x1048 )
                _report_rangecheckfailure();
              *(WCHAR *)((char *)pszEscaped + v26) = 0;
            }
            v29 = StrRChrW(pszEscaped, 0, 0x2Fu);
            if ( v29 )
            {
              v28 = -1;
              do
                ++v28;
              while ( v29[v28] );
              if ( v28 > 1 )
              {
                v27 = -1;
                do
                  ++v27;
                while ( pszEscaped[v27] );
                v28 = v22 + v21 + 3;
                if ( v27 > v28 )
                {
                  Uri = _AllocString<CTCoAllocPolicy>(v28, v27, v29 + 1, &v44[1]);
                  if ( Uri >= 0 )
                  {
                    v29[1] = 0;
                    Uri = _AllocString<CTCoAllocPolicy>(v28, v27, pszEscaped, v45);
                    if ( Uri >= 0 )
                    {
                      v30 = StrRChrW(pszEscaped, v29, 0x2Fu);
                      v31 = v30;
                      if ( v30 )
                      {
                        do
                          ++v24;
                        while ( v30[v24] );
                        if ( v24 > 1 )
                        {
                          v32 = StrRChrW(pszEscaped, v30, 0x2Fu);
                          v28 = (unsigned __int64)(v31 - 1);
                          if ( v32 != v31 - 1 )
                          {
                            v33 = v31 + 1;
                            Uri = SHSysAllocString(v33, &v43[1]);
                            if ( Uri >= 0 )
                            {
                              *v33 = 0;
                              if ( a2 != v33 )
                                Uri = SHSysAllocString(pszEscaped, v44);
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
            if ( !v44[0] )
              Uri = SHSysAllocString(pszEscaped, v44);
            if ( !v45[0] )
              Uri = _AllocString<CTCoAllocPolicy>(v28, v27, pszEscaped, v45);
          }
          SysFreeString(*(BSTR *)pcchPath);
          if ( Uri >= 0 )
          {
            Uri = COpenSearchRowset::_PreparePathForDisplayBSTR(v34, a2, v43);
            if ( Uri >= 0 )
            {
              if ( !v43[1] || (Uri = COpenSearchRowset::_PreparePathForDisplayBSTR(v35, v43[1], &v43[1]), Uri >= 0) )
              {
                if ( !v44[0] || (Uri = COpenSearchRowset::_PreparePathForDisplayBSTR(v35, v44[0], v44), Uri >= 0) )
                {
                  if ( !v45[0]
                    || (Uri = COpenSearchRowset::_PreparePathForDisplayCoAlloc(
                                v35,
                                v45[0],
                                (unsigned __int16 **)&v45[1]),
                        Uri >= 0) )
                  {
                    if ( v44[1] )
                      Uri = COpenSearchRowset::_PreparePathForDisplayCoAlloc(v35, v44[1], &v44[1]);
                  }
                }
              }
            }
          }
        }
        SysFreeString(pbstr);
      }
    }
  }
LABEL_76:
  ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(&v40);
  if ( Uri < 0 )
  {
LABEL_79:
    COpenSearchRowset::CUrlInfo::Clear((COpenSearchRowset::CUrlInfo *)v42);
    return (unsigned int)Uri;
  }
  v36 = *(_OWORD *)v43;
  *(_OWORD *)a3 = *(_OWORD *)v42;
  v37 = *(_OWORD *)v44;
  *((_OWORD *)a3 + 1) = v36;
  v38 = *(_OWORD *)v45;
  *((_OWORD *)a3 + 2) = v37;
  *(_QWORD *)&v37 = v46;
  *((_OWORD *)a3 + 3) = v38;
  *((_QWORD *)a3 + 8) = v37;
  return (unsigned int)Uri;
}

```

## disassembly

```asm
0x1800463e0  mov     [rsp-8+arg_0], rbx
0x1800463e5  push    rbp
0x1800463e6  push    rsi
0x1800463e7  push    rdi
0x1800463e8  push    r12
0x1800463ea  push    r13
0x1800463ec  push    r14
0x1800463ee  push    r15
0x1800463f0  lea     rbp, [rsp-1200h]
0x1800463f8  mov     eax, 1300h
0x1800463fd  call    _alloca_probe
0x180046402  sub     rsp, rax
0x180046405  mov     rax, cs:__security_cookie
0x18004640c  xor     rax, rsp
0x18004640f  mov     [rbp+1230h+var_40], rax
0x180046416  mov     rcx, r8; this
0x180046419  mov     r13, r8
0x18004641c  mov     r14, rdx
0x18004641f  call    ?Clear@CUrlInfo@COpenSearchRowset@@QEAAXXZ; COpenSearchRowset::CUrlInfo::Clear(void)
0x180046424  xor     edx, edx; Val
0x180046426  lea     rcx, [rsp+1330h+var_1300]; void *
0x18004642b  lea     r8d, [rdx+48h]; Size
0x18004642f  call    memset_0
0x180046434  mov     edi, 824h
0x180046439  xor     edx, edx; UrlIs
0x18004643b  mov     rcx, r14; pszUrl
0x18004643e  mov     [rbp+1230h+pcchEscaped], edi
0x180046441  call    cs:__imp_UrlIsW
0x180046447  xor     esi, esi
0x180046449  mov     r15d, 40000h
0x18004644f  test    eax, eax
0x180046451  jz      short loc_18004646C
0x180046453  mov     r9d, r15d; dwFlags
0x180046456  lea     r8, [rbp+1230h+pcchEscaped]; pcchEscaped
0x18004645a  lea     rdx, [rbp+1230h+pszEscaped]; pszEscaped
0x180046461  mov     rcx, r14; pszUrl
0x180046464  call    cs:__imp_UrlEscapeW
0x18004646a  jmp     short loc_18004647E
0x18004646c  mov     r8, r14; unsigned __int16 *
0x18004646f  lea     rcx, [rbp+1230h+pszEscaped]; unsigned __int16 *
0x180046476  mov     rdx, rdi; unsigned __int64
0x180046479  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004647e  mov     ebx, eax
0x180046480  test    eax, eax
0x180046482  js      loc_1800469CC
0x180046488  lea     rcx, [rsp+1330h+var_1310]; void *
0x18004648d  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x180046492  lea     rcx, [rsp+1330h+var_1310]
0x180046497  call    ??I?$CComPtrBase@UIXMLDOMDocument@@@ATL@@QEAAPEAPEAUIXMLDOMDocument@@XZ; ATL::CComPtrBase<IXMLDOMDocument>::operator&(void)
0x18004649c  xor     r8d, r8d; dwReserved
0x18004649f  lea     rcx, [rbp+1230h+pszEscaped]; pwzURI
0x1800464a6  mov     r9, rax; ppURI
0x1800464a9  lea     edx, [r8+4]; dwFlags
0x1800464ad  call    cs:__imp_CreateUri
0x1800464b3  mov     ebx, eax
0x1800464b5  test    eax, eax
0x1800464b7  js      loc_180046982
0x1800464bd  mov     rcx, [rsp+1330h+var_1310]
0x1800464c2  lea     rdx, [rsp+1330h+var_12C0]
0x1800464c7  mov     rax, [rcx]
0x1800464ca  mov     rax, [rax+0C0h]
0x1800464d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800464d6  mov     ebx, eax
0x1800464d8  test    eax, eax
0x1800464da  js      loc_180046982
0x1800464e0  cmp     dword ptr [rsp+1330h+var_12C0], 9
0x1800464e5  jnz     loc_180046682
0x1800464eb  mov     ebx, 104h
0x1800464f0  mov     edx, 3; UrlIs
0x1800464f5  mov     rcx, r14; pszUrl
0x1800464f8  mov     [rsp+1330h+pcchPath], ebx
0x1800464fc  call    cs:__imp_UrlIsW
0x180046502  test    eax, eax
0x180046504  jz      short loc_180046521
0x180046506  mov     r9d, r15d; dwFlags
0x180046509  lea     r8, [rsp+1330h+pcchPath]; pcchPath
0x18004650e  lea     rdx, [rbp+1230h+pszPath]; pszPath
0x180046512  lea     rcx, [rbp+1230h+pszEscaped]; pszUrl
0x180046519  call    cs:__imp_PathCreateFromUrlW
0x18004651f  jmp     short loc_180046530
0x180046521  mov     r8, r14; unsigned __int16 *
0x180046524  lea     rcx, [rbp+1230h+pszPath]; unsigned __int16 *
0x180046528  mov     rdx, rbx; unsigned __int64
0x18004652b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180046530  mov     ebx, eax
0x180046532  test    eax, eax
0x180046534  js      loc_180046982
0x18004653a  lea     rdx, [rsp+1330h+var_12F0]; unsigned __int16 **
0x18004653f  lea     rcx, [rbp+1230h+pszPath]; unsigned __int16 *
0x180046543  call    ?SHSysAllocString@@YAJPEBGPEAPEAG@Z; SHSysAllocString(ushort const *,ushort * *)
0x180046548  mov     ebx, eax
0x18004654a  test    eax, eax
0x18004654c  js      loc_180046982
0x180046552  lea     rdx, [rsp+1330h+var_1300]; unsigned __int16 **
0x180046557  lea     rcx, [rbp+1230h+pszPath]; unsigned __int16 *
0x18004655b  call    ?SHSysAllocString@@YAJPEBGPEAPEAG@Z; SHSysAllocString(ushort const *,ushort * *)
0x180046560  mov     ebx, eax
0x180046562  test    eax, eax
0x180046564  js      loc_180046982
0x18004656a  lea     rcx, [rbp+1230h+pszPath]; pszPath
0x18004656e  call    cs:__imp_PathFindFileNameW
0x180046574  mov     r8, rax
0x180046577  lea     r9, [rsp+1330h+var_12E0+8]
0x18004657c  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x180046581  mov     ebx, eax
0x180046583  test    eax, eax
0x180046585  js      loc_180046982
0x18004658b  lea     rcx, [rbp+1230h+pszPath]; pszPath
0x18004658f  call    cs:__imp_PathFindExtensionW
0x180046595  mov     rcx, rax; unsigned __int16 *
0x180046598  lea     rdx, [rsp+1330h+var_1300+8]; unsigned __int16 **
0x18004659d  call    ?SHSysAllocString@@YAJPEBGPEAPEAG@Z; SHSysAllocString(ushort const *,ushort * *)
0x1800465a2  mov     ebx, eax
0x1800465a4  test    eax, eax
0x1800465a6  js      loc_180046982
0x1800465ac  lea     rcx, [rbp+1230h+pszPath]; pszPath
0x1800465b0  call    cs:__imp_PathIsRootW
0x1800465b6  test    eax, eax
0x1800465b8  jnz     loc_180046982
0x1800465be  lea     rcx, [rbp+1230h+pszPath]; pszPath
0x1800465c2  call    cs:__imp_PathRemoveBackslashW
0x1800465c8  lea     rcx, [rbp+1230h+pszPath]; pszPath
0x1800465cc  call    cs:__imp_PathRemoveFileSpecW
0x1800465d2  lea     r9, [rsp+1330h+var_12D0]
0x1800465d7  test    eax, eax
0x1800465d9  jz      short loc_180046628
0x1800465db  lea     r8, [rbp+1230h+pszPath]
0x1800465df  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x1800465e4  mov     ebx, eax
0x1800465e6  test    eax, eax
0x1800465e8  js      loc_180046982
0x1800465ee  lea     rcx, [rbp+1230h+pszPath]; pszPath
0x1800465f2  call    cs:__imp_PathFindFileNameW
0x1800465f8  mov     rcx, rax; unsigned __int16 *
0x1800465fb  lea     rdx, [rsp+1330h+var_12F0+8]; unsigned __int16 **
0x180046600  call    ?SHSysAllocString@@YAJPEBGPEAPEAG@Z; SHSysAllocString(ushort const *,ushort * *)
0x180046605  mov     ebx, eax
0x180046607  test    eax, eax
0x180046609  js      loc_180046982
0x18004660f  lea     rcx, [rbp+1230h+pszPath]; pszPath
0x180046613  call    cs:__imp_PathRemoveFileSpecW
0x180046619  test    eax, eax
0x18004661b  jz      short loc_18004666C
0x18004661d  lea     rdx, [rsp+1330h+var_12E0]
0x180046622  lea     rcx, [rbp+1230h+pszPath]
0x180046626  jmp     short loc_18004665D
0x180046628  mov     rax, [rsp+1330h+var_1300]
0x18004662d  lea     r8, psz
0x180046634  test    rax, rax
0x180046637  cmovnz  r8, rax
0x18004663b  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x180046640  mov     ebx, eax
0x180046642  test    eax, eax
0x180046644  js      loc_180046982
0x18004664a  mov     rcx, [rsp+1330h+var_12D0]; pszPath
0x18004664f  call    cs:__imp_PathFindFileNameW
0x180046655  mov     rcx, rax; unsigned __int16 *
0x180046658  lea     rdx, [rsp+1330h+var_12F0+8]; unsigned __int16 **
0x18004665d  call    ?SHSysAllocString@@YAJPEBGPEAPEAG@Z; SHSysAllocString(ushort const *,ushort * *)
0x180046662  mov     ebx, eax
0x180046664  test    eax, eax
0x180046666  js      loc_180046982
0x18004666c  mov     r8, [rsp+1330h+var_12D0]
0x180046671  lea     r9, [rsp+1330h+var_12D0+8]
0x180046676  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x18004667b  mov     ebx, eax
0x18004667d  jmp     loc_180046982
0x180046682  mov     rcx, [rsp+1330h+var_1310]
0x180046687  lea     rdx, [rsp+1330h+var_1300]
0x18004668c  mov     rax, [rcx]
0x18004668f  mov     rax, [rax+38h]
0x180046693  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046698  mov     ebx, eax
0x18004669a  test    eax, eax
0x18004669c  js      loc_180046982
0x1800466a2  mov     r8, r14; unsigned __int16 *
0x1800466a5  lea     rcx, [rbp+1230h+pszEscaped]; unsigned __int16 *
0x1800466ac  mov     rdx, rdi; unsigned __int64
0x1800466af  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800466b4  mov     ebx, eax
0x1800466b6  test    eax, eax
0x1800466b8  js      loc_180046982
0x1800466be  mov     rcx, [rsp+1330h+var_1310]
0x1800466c3  lea     rdx, [rsp+1330h+var_1300+8]
0x1800466c8  mov     rax, [rcx]
0x1800466cb  mov     rax, [rax+58h]
0x1800466cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800466d4  mov     rcx, [rsp+1330h+var_1310]
0x1800466d9  lea     rdx, [rbp+1230h+pbstr]
0x1800466dd  mov     [rbp+1230h+pbstr], rsi
0x1800466e1  mov     rax, [rcx]
0x1800466e4  mov     rax, [rax+40h]
0x1800466e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800466ed  mov     ebx, eax
0x1800466ef  test    eax, eax
0x1800466f1  js      loc_180046978
0x1800466f7  mov     rcx, [rsp+1330h+var_1310]
0x1800466fc  lea     rdx, [rsp+1330h+pcchPath]
0x180046701  mov     qword ptr [rsp+1330h+pcchPath], rsi
0x180046706  mov     rax, [rcx]
0x180046709  mov     rax, [rax+98h]
0x180046710  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046715  mov     ebx, eax
0x180046717  test    eax, eax
0x180046719  js      loc_1800468F2
0x18004671f  mov     rcx, qword ptr [rsp+1330h+pcchPath]; pbstr
0x180046724  test    rcx, rcx
0x180046727  jnz     short loc_18004672E
0x180046729  mov     r12d, esi
0x18004672c  jmp     short loc_180046737
0x18004672e  call    cs:__imp_SysStringLen
0x180046734  mov     r12d, eax
0x180046737  mov     rcx, [rbp+1230h+pbstr]; pbstr
0x18004673b  test    rcx, rcx
0x18004673e  jnz     short loc_180046745
0x180046740  mov     r15d, esi
0x180046743  jmp     short loc_18004674E
0x180046745  call    cs:__imp_SysStringLen
0x18004674b  mov     r15d, eax
0x18004674e  xor     edx, edx; pszEnd
0x180046750  lea     rcx, [rbp+1230h+pszEscaped]; pszStart
0x180046757  lea     r8d, [rdx+3Fh]; wMatch
0x18004675b  call    cs:__imp_StrRChrW
0x180046761  test    rax, rax
0x180046764  jz      short loc_180046769
0x180046766  mov     [rax], si
0x180046769  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18004676d  lea     rcx, [rbp+1230h+pszEscaped]
0x180046774  mov     rax, rdi
0x180046777  inc     rax
0x18004677a  cmp     [rcx+rax*2], si
0x18004677e  jnz     short loc_180046777
0x180046780  mov     edx, 2Fh ; '/'
0x180046785  cmp     [rbp+rax*2+1230h+var_1092], dx
0x18004678d  jnz     short loc_1800467AC
0x18004678f  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x180046797  cmp     rcx, 1048h
0x18004679e  jnb     loc_1800469C6
0x1800467a4  mov     [rbp+rcx+1230h+pszEscaped], si
0x1800467ac  mov     r8d, edx; wMatch
0x1800467af  lea     rcx, [rbp+1230h+pszEscaped]; pszStart
0x1800467b6  xor     edx, edx; pszEnd
0x1800467b8  call    cs:__imp_StrRChrW
0x1800467be  mov     rsi, rax
0x1800467c1  xor     eax, eax
0x1800467c3  test    rsi, rsi
0x1800467c6  jz      loc_1800468BC
0x1800467cc  mov     rcx, rdi
0x1800467cf  inc     rcx
0x1800467d2  cmp     [rsi+rcx*2], ax
0x1800467d6  jnz     short loc_1800467CF
0x1800467d8  cmp     rcx, 1
0x1800467dc  jbe     loc_1800468BC
0x1800467e2  lea     rcx, [rbp+1230h+pszEscaped]
0x1800467e9  mov     rdx, rdi
0x1800467ec  inc     rdx
0x1800467ef  cmp     [rcx+rdx*2], ax
0x1800467f3  jnz     short loc_1800467EC
0x1800467f5  lea     ecx, [r12+3]
0x1800467fa  add     ecx, r15d
0x1800467fd  cmp     rdx, rcx
0x180046800  jbe     loc_1800468BC
0x180046806  lea     r9, [rsp+1330h+var_12E0+8]
0x18004680b  lea     r8, [rsi+2]
0x18004680f  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x180046814  xor     r12d, r12d
0x180046817  mov     ebx, eax
0x180046819  test    eax, eax
0x18004681b  js      loc_1800468BC
0x180046821  lea     r9, [rsp+1330h+var_12D0]
0x180046826  mov     [rsi+2], r12w
0x18004682b  lea     r8, [rbp+1230h+pszEscaped]
0x180046832  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x180046837  mov     ebx, eax
0x180046839  test    eax, eax
0x18004683b  js      short loc_1800468BC
0x18004683d  lea     r15d, [r12+2Fh]
0x180046842  mov     rdx, rsi; pszEnd
0x180046845  mov     r8d, r15d; wMatch
0x180046848  lea     rcx, [rbp+1230h+pszEscaped]; pszStart
0x18004684f  call    cs:__imp_StrRChrW
0x180046855  mov     rsi, rax
0x180046858  test    rax, rax
0x18004685b  jz      short loc_1800468BC
0x18004685d  inc     rdi
0x180046860  cmp     [rax+rdi*2], r12w
0x180046865  jnz     short loc_18004685D
0x180046867  cmp     rdi, 1
0x18004686b  jbe     short loc_1800468BC
0x18004686d  mov     r8d, r15d; wMatch
0x180046870  lea     rcx, [rbp+1230h+pszEscaped]; pszStart
0x180046877  mov     rdx, rsi; pszEnd
0x18004687a  call    cs:__imp_StrRChrW
0x180046880  lea     rcx, [rsi-2]
0x180046884  cmp     rax, rcx
0x180046887  jz      short loc_1800468BC
0x180046889  add     rsi, 2
0x18004688d  lea     rdx, [rsp+1330h+var_12F0+8]; unsigned __int16 **
0x180046892  mov     rcx, rsi; unsigned __int16 *
0x180046895  call    ?SHSysAllocString@@YAJPEBGPEAPEAG@Z; SHSysAllocString(ushort const *,ushort * *)
  ... truncated ...
```
