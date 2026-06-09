# COpenSearchRowset::_OpenSearchQuery(__int64,__int64,IStream * *)

- ea: `0x180044d50`
- end: `0x1800451a9`
- name: `?_OpenSearchQuery@COpenSearchRowset@@AEAAJ_J0PEAPEAUIStream@@@Z`
- size: `1113`
- prototype: `__int64 __fastcall(COpenSearchRowset *__hidden this, __int64, __int64, struct IStream **)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180043938`

## callees

- `0x1800054b0`
- `0x180005c74`
- `0x180005c88`
- `0x1800064d4`
- `0x180006900`
- `0x1800129f8`
- `0x180021e64`
- `0x18002eff0`
- `0x18002fa14`
- `0x18003d428`
- `0x180041c40`
- `0x180043304`
- `0x1800442f4`
- `0x180044360`
- `0x180044d50`
- `0x1800451b0`
- `0x180047888`
- `0x18004faa0`
- `0x180051010`

## import_xrefs

- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180045076`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180045076`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x180045092`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x180045092`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileEx` at `0x180045135`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileEx` at `0x180045135`
- `SHLWAPI!UrlIsW` at `0x1800450d8`
- `SHLWAPI!UrlIsW` at `0x1800450d8`
- `SHLWAPI!PathCreateFromUrlW` at `0x1800450fa`
- `SHLWAPI!PathCreateFromUrlW` at `0x1800450fa`
- `SHLWAPI!PathFileExistsW` at `0x180045116`
- `SHLWAPI!PathFileExistsW` at `0x180045116`
- `SHLWAPI!StrStrIW` at `0x180044ed7`
- `SHLWAPI!StrStrIW` at `0x180044eec`
- `SHLWAPI!StrStrIW` at `0x180044f07`
- `SHLWAPI!StrStrIW` at `0x180044f1c`
- `SHLWAPI!StrStrIW` at `0x180044ed7`
- `SHLWAPI!StrStrIW` at `0x180044eec`
- `SHLWAPI!StrStrIW` at `0x180044f07`
- `SHLWAPI!StrStrIW` at `0x180044f1c`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180045015`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180045015`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044dff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044ead`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044dff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044ead`
- `WININET!InternetReadFile` at `0x180045051`
- `WININET!InternetReadFile` at `0x180045051`
- `WININET!InternetCloseHandle` at `0x1800450b8`
- `WININET!InternetCloseHandle` at `0x1800450b8`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall COpenSearchRowset::_OpenSearchQuery(
        COpenSearchRowset *this,
        __int64 a2,
        __int64 a3,
        struct IStream **a4)
{
  int v4; // r14d
  __int64 v6; // r12
  const wchar_t *v9; // rax
  __int64 v10; // r8
  const wchar_t *v11; // r14
  const wchar_t *v12; // r9
  HRESULT appended; // ebx
  void *v14; // rcx
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, HWND, const wchar_t *, _QWORD, _DWORD, GUID *, struct IStream **); // rbx
  HWND ParentWindowFromSite; // rax
  PCWSTR *v18; // rdi
  void *v19; // rcx
  const WCHAR **v20; // rbx
  const WCHAR *v21; // rbx
  PWSTR v22; // rax
  BOOL v23; // eax
  int v24; // ecx
  int v25; // r8d
  int v26; // r9d
  __int64 v27; // rcx
  PCWSTR v28; // rdx
  bool v29; // cf
  int v30; // eax
  void *v31; // r14
  LPSTREAM *v32; // rax
  bool v33; // sf
  const WCHAR *v34; // rcx
  const WCHAR *v35; // rcx
  DWORD dwNumberOfBytesRead; // [rsp+40h] [rbp-C0h] BYREF
  HINTERNET hFile[3]; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR Buffer[2048]; // [rsp+60h] [rbp-A0h] BYREF

  v4 = 0;
  v6 = a3;
  if ( *((_QWORD *)this + 101) )
  {
    v9 = (const wchar_t *)*((_QWORD *)this + 96);
    v10 = *((_QWORD *)this + 100);
    memset(hFile, 0, sizeof(hFile));
    v11 = &psz;
    v12 = &psz;
    if ( v9 )
      v12 = v9;
    appended = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::AppendFormat(
                 hFile,
                 L"%s://%s/%u/%u",
                 v10,
                 v12,
                 a2,
                 v6);
    if ( appended >= 0 )
    {
      v14 = (void *)*((_QWORD *)this + 98);
      *((_QWORD *)this + 98) = 0;
      CoTaskMemFree(v14);
      appended = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::DetachInitializeIfEmpty(
                   hFile,
                   (char *)this + 784);
      if ( appended >= 0 )
      {
        v15 = *((_QWORD *)this + 101);
        v16 = *(__int64 (__fastcall **)(__int64, HWND, const wchar_t *, _QWORD, _DWORD, GUID *, struct IStream **))(*(_QWORD *)v15 + 24LL);
        if ( *((_QWORD *)this + 96) )
          v11 = (const wchar_t *)*((_QWORD *)this + 96);
        ParentWindowFromSite = COpenSearchRowset::_GetParentWindowFromSite(this);
        appended = v16(
                     v15,
                     ParentWindowFromSite,
                     v11,
                     (unsigned int)a2,
                     v6,
                     &GUID_0000000c_0000_0000_c000_000000000046,
                     a4);
      }
    }
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(hFile);
    v18 = (PCWSTR *)((char *)this + 776);
    goto LABEL_57;
  }
  if ( (byte_180069A01 & 4) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(
      (_DWORD)this,
      (unsigned int)PerfTrack_OpenSearch_QueryServer_Start,
      a3,
      (_DWORD)a4,
      (__int64)hFile);
  *a4 = 0;
  v18 = (PCWSTR *)((char *)this + 776);
  v19 = (void *)*((_QWORD *)this + 97);
  *((_QWORD *)this + 97) = 0;
  CoTaskMemFree(v19);
  v20 = (const WCHAR **)((char *)this + 760);
  if ( *((_QWORD *)this + 96) )
    v20 = (const WCHAR **)((char *)this + 752);
  v21 = *v20;
  if ( StrStrIW(v21, L"{startIndex}") || StrStrIW(v21, L"{startIndex?}") )
    v4 = 1;
  if ( StrStrIW(v21, L"{startPage}") || (v22 = StrStrIW(v21, L"{startPage?}")) != 0 )
    LODWORD(v22) = 1;
  v23 = !v4 && !(_DWORD)v22;
  *((_DWORD *)this + 18) = v23;
  if ( !v4 )
    v6 = *((unsigned int *)this + 13);
  appended = COpenSearchRowset::_BuildQueryUrl(this, a2, v6, v21, (unsigned __int16 **)this + 97);
  if ( appended >= 0 )
  {
    v27 = *((_QWORD *)this + 107);
    if ( !v27
      || (appended = (*(__int64 (__fastcall **)(__int64, PCWSTR, char *, _QWORD))(*(_QWORD *)v27 + 40LL))(
                       v27,
                       *v18,
                       (char *)this + 792,
                       0),
          appended >= 0) )
    {
      v28 = *v18;
      v29 = *((_QWORD *)this + 96) != 0;
      hFile[0] = 0;
      v30 = COpenSearchRowset::_OpenUrlRequest((__int64)this, (__int64)v28, v29 ? 71829504 : 4720640, 0, hFile);
      appended = v30;
      if ( v30 >= 0 )
      {
        v31 = hFile[0];
        appended = COpenSearchRowset::_HttpSendRequest(this, hFile[0]);
        if ( appended >= 0 )
        {
          ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(hFile);
          v32 = (LPSTREAM *)ATL::CComPtrBase<IXMLDOMDocument>::operator&(hFile);
          appended = CreateStreamOnHGlobal(0, 1, v32);
          if ( appended >= 0 )
          {
            dwNumberOfBytesRead = 0;
            while ( 1 )
            {
              appended = QueryContinueOnSite(*((struct IUnknown **)this + 4));
              if ( appended >= 0 )
              {
                dwNumberOfBytesRead = 0;
                if ( InternetReadFile(v31, Buffer, 0x1000u, &dwNumberOfBytesRead)
                  || (appended = ResultFromKnownLastError(), appended >= 0) )
                {
                  appended = IStream_Write((IStream *)hFile[0], Buffer, dwNumberOfBytesRead);
                }
              }
              v33 = appended < 0;
              if ( appended )
                break;
              if ( !dwNumberOfBytesRead )
              {
                v33 = 0;
                break;
              }
            }
            if ( !v33 )
            {
              appended = IStream_Reset((IStream *)hFile[0]);
              if ( appended >= 0 )
                *a4 = (struct IStream *)ATL::CComPtrBase<IScope>::Detach(hFile);
            }
          }
          ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(hFile);
        }
        InternetCloseHandle(v31);
        goto LABEL_55;
      }
      if ( v30 == -2147024846 )
      {
        if ( *((_DWORD *)this + 20) )
        {
          if ( UrlIsW(*v18, URLIS_FILEURL) )
          {
            v34 = *v18;
            dwNumberOfBytesRead = 260;
            appended = PathCreateFromUrlW(v34, Buffer, &dwNumberOfBytesRead, 0);
            if ( appended < 0 )
              goto LABEL_55;
            v35 = Buffer;
            goto LABEL_53;
          }
          if ( *((_DWORD *)this + 20) && PathFileExistsW(*v18) )
          {
            v35 = *v18;
LABEL_53:
            appended = SHCreateStreamOnFileEx(v35, 0, 0, 0, 0, a4);
            goto LABEL_55;
          }
        }
        appended = -2147467259;
      }
    }
  }
LABEL_55:
  if ( (byte_180069A01 & 4) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(
      v24,
      (unsigned int)PerfTrack_OpenSearch_QueryServer_Stop,
      v25,
      v26,
      (__int64)hFile);
LABEL_57:
  if ( appended < 0 && appended != -2147023673 && appended != -2144927744 )
    COpenSearchRowset::_ShowInfoBarErrorMessage(this, appended, *v18);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x180044d50  push    rbp
0x180044d52  push    rbx
0x180044d53  push    rsi
0x180044d54  push    rdi
0x180044d55  push    r12
0x180044d57  push    r13
0x180044d59  push    r14
0x180044d5b  push    r15
0x180044d5d  lea     rbp, [rsp-0F78h]
0x180044d65  mov     eax, 1078h
0x180044d6a  call    _alloca_probe
0x180044d6f  sub     rsp, rax
0x180044d72  mov     rax, cs:__security_cookie
0x180044d79  xor     rax, rsp
0x180044d7c  mov     [rbp+0FB0h+var_50], rax
0x180044d83  xor     r14d, r14d
0x180044d86  mov     r15, r9
0x180044d89  mov     r12, r8
0x180044d8c  mov     r13, rdx
0x180044d8f  mov     rsi, rcx
0x180044d92  cmp     [rcx+328h], r14
0x180044d99  jz      loc_180044E7E
0x180044d9f  mov     rax, [rcx+300h]
0x180044da6  lea     rdx, aSSUU; "%s://%s/%u/%u"
0x180044dad  mov     r8, [rcx+320h]
0x180044db4  test    rax, rax
0x180044db7  mov     [rsp+10B0h+hFile], r14
0x180044dbc  lea     rcx, [rsp+10B0h+hFile]
0x180044dc1  mov     [rsp+10B0h+var_1060], r14
0x180044dc6  mov     [rsp+10B0h+var_1058], r14
0x180044dcb  lea     r14, psz
0x180044dd2  mov     r9, r14
0x180044dd5  mov     dword ptr [rsp+10B0h+ppstm], r12d
0x180044dda  cmovnz  r9, rax
0x180044dde  mov     dword ptr [rsp+10B0h+pstmTemplate], r13d
0x180044de3  call    ?AppendFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::AppendFormat(ushort const *,...)
0x180044de8  mov     ebx, eax
0x180044dea  test    eax, eax
0x180044dec  js      short loc_180044E68
0x180044dee  lea     rbx, [rsi+310h]
0x180044df5  mov     rcx, [rbx]; pv
0x180044df8  mov     qword ptr [rbx], 0
0x180044dff  call    cs:__imp_CoTaskMemFree
0x180044e05  mov     rdx, rbx
0x180044e08  lea     rcx, [rsp+10B0h+hFile]
0x180044e0d  call    ?DetachInitializeIfEmpty@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAPEAG@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::DetachInitializeIfEmpty(ushort * *)
0x180044e12  mov     ebx, eax
0x180044e14  test    eax, eax
0x180044e16  js      short loc_180044E68
0x180044e18  mov     rdi, [rsi+328h]
0x180044e1f  mov     rcx, rsi; this
0x180044e22  mov     rax, [rdi]
0x180044e25  mov     rbx, [rax+18h]
0x180044e29  mov     rax, [rsi+300h]
0x180044e30  test    rax, rax
0x180044e33  cmovnz  r14, rax
0x180044e37  call    ?_GetParentWindowFromSite@COpenSearchRowset@@AEAAPEAUHWND__@@XZ; COpenSearchRowset::_GetParentWindowFromSite(void)
0x180044e3c  lea     rcx, _GUID_0000000c_0000_0000_c000_000000000046
0x180044e43  mov     [rsp+10B0h+var_1080], r15
0x180044e48  mov     [rsp+10B0h+ppstm], rcx
0x180044e4d  mov     rdx, rax
0x180044e50  mov     rcx, rdi
0x180044e53  mov     dword ptr [rsp+10B0h+pstmTemplate], r12d
0x180044e58  mov     r9d, r13d
0x180044e5b  mov     r8, r14
0x180044e5e  mov     rax, rbx
0x180044e61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044e66  mov     ebx, eax
0x180044e68  lea     rcx, [rsp+10B0h+hFile]
0x180044e6d  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180044e72  lea     rdi, [rsi+308h]
0x180044e79  jmp     loc_180045163
0x180044e7e  test    cs:byte_180069A01, 4
0x180044e85  jz      short loc_180044E9D
0x180044e87  lea     rax, [rsp+10B0h+hFile]
0x180044e8c  lea     rdx, PerfTrack_OpenSearch_QueryServer_Start
0x180044e93  mov     [rsp+10B0h+pstmTemplate], rax
0x180044e98  call    McGenEventWrite_EtwEventWriteTransfer
0x180044e9d  mov     [r15], r14
0x180044ea0  lea     rdi, [rsi+308h]
0x180044ea7  mov     rcx, [rdi]; pv
0x180044eaa  mov     [rdi], r14
0x180044ead  call    cs:__imp_CoTaskMemFree
0x180044eb3  lea     rbx, [rsi+2F8h]
0x180044eba  cmp     [rsi+300h], r14
0x180044ec1  jz      short loc_180044ECA
0x180044ec3  lea     rbx, [rsi+2F0h]
0x180044eca  mov     rbx, [rbx]
0x180044ecd  lea     rdx, aStartindex_1; "{startIndex}"
0x180044ed4  mov     rcx, rbx; pszFirst
0x180044ed7  call    cs:__imp_StrStrIW
0x180044edd  test    rax, rax
0x180044ee0  jnz     short loc_180044EF7
0x180044ee2  lea     rdx, aStartindex_0; "{startIndex?}"
0x180044ee9  mov     rcx, rbx; pszFirst
0x180044eec  call    cs:__imp_StrStrIW
0x180044ef2  test    rax, rax
0x180044ef5  jz      short loc_180044EFD
0x180044ef7  mov     r14d, 1
0x180044efd  lea     rdx, aStartpage; "{startPage}"
0x180044f04  mov     rcx, rbx; pszFirst
0x180044f07  call    cs:__imp_StrStrIW
0x180044f0d  test    rax, rax
0x180044f10  jnz     short loc_180044F27
0x180044f12  lea     rdx, aStartpage_1; "{startPage?}"
0x180044f19  mov     rcx, rbx; pszFirst
0x180044f1c  call    cs:__imp_StrStrIW
0x180044f22  test    rax, rax
0x180044f25  jz      short loc_180044F2C
0x180044f27  mov     eax, 1
0x180044f2c  test    r14d, r14d
0x180044f2f  jnz     short loc_180044F3B
0x180044f31  test    eax, eax
0x180044f33  jnz     short loc_180044F3B
0x180044f35  lea     eax, [r14+1]
0x180044f39  jmp     short loc_180044F3D
0x180044f3b  xor     eax, eax
0x180044f3d  mov     [rsi+48h], eax
0x180044f40  test    r14d, r14d
0x180044f43  jnz     short loc_180044F49
0x180044f45  mov     r12d, [rsi+34h]
0x180044f49  mov     r9, rbx; unsigned __int16 *
0x180044f4c  mov     [rsp+10B0h+pstmTemplate], rdi; unsigned __int16 **
0x180044f51  mov     r8, r12; __int64
0x180044f54  mov     rdx, r13; __int64
0x180044f57  mov     rcx, rsi; this
0x180044f5a  call    ?_BuildQueryUrl@COpenSearchRowset@@AEAAJ_J0PEBGPEAPEAG@Z; COpenSearchRowset::_BuildQueryUrl(__int64,__int64,ushort const *,ushort * *)
0x180044f5f  xor     r12d, r12d
0x180044f62  mov     ebx, eax
0x180044f64  test    eax, eax
0x180044f66  js      loc_180045144
0x180044f6c  mov     rcx, [rsi+358h]
0x180044f73  test    rcx, rcx
0x180044f76  jz      short loc_180044F9B
0x180044f78  mov     rax, [rcx]
0x180044f7b  lea     r8, [rsi+318h]
0x180044f82  mov     rdx, [rdi]
0x180044f85  xor     r9d, r9d
0x180044f88  mov     rax, [rax+28h]
0x180044f8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044f91  mov     ebx, eax
0x180044f93  test    eax, eax
0x180044f95  js      loc_180045144
0x180044f9b  mov     rax, [rsi+300h]
0x180044fa2  mov     rcx, rsi
0x180044fa5  mov     rdx, [rdi]
0x180044fa8  neg     rax
0x180044fab  lea     rax, [rsp+10B0h+hFile]
0x180044fb0  mov     [rsp+10B0h+hFile], r12
0x180044fb5  sbb     r8d, r8d
0x180044fb8  mov     [rsp+10B0h+pstmTemplate], rax
0x180044fbd  and     r8d, 4000000h
0x180044fc4  xor     r9d, r9d
0x180044fc7  add     r8d, 480800h
0x180044fce  call    ?_OpenUrlRequest@COpenSearchRowset@@AEAAJPEBGKW4OPENSEARCH_REQUEST_TYPE@@PEAPEAX@Z; COpenSearchRowset::_OpenUrlRequest(ushort const *,ulong,OPENSEARCH_REQUEST_TYPE,void * *)
0x180044fd3  mov     ebx, eax
0x180044fd5  test    eax, eax
0x180044fd7  js      loc_1800450C3
0x180044fdd  mov     r14, [rsp+10B0h+hFile]
0x180044fe2  mov     rcx, rsi; this
0x180044fe5  mov     rdx, r14; hRequest
0x180044fe8  call    ?_HttpSendRequest@COpenSearchRowset@@AEAAJPEAX@Z; COpenSearchRowset::_HttpSendRequest(void *)
0x180044fed  mov     ebx, eax
0x180044fef  test    eax, eax
0x180044ff1  js      loc_1800450B5
0x180044ff7  lea     rcx, [rsp+10B0h+hFile]; void *
0x180044ffc  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x180045001  lea     rcx, [rsp+10B0h+hFile]
0x180045006  call    ??I?$CComPtrBase@UIXMLDOMDocument@@@ATL@@QEAAPEAPEAUIXMLDOMDocument@@XZ; ATL::CComPtrBase<IXMLDOMDocument>::operator&(void)
0x18004500b  mov     r8, rax; ppstm
0x18004500e  mov     edx, 1; fDeleteOnRelease
0x180045013  xor     ecx, ecx; hGlobal
0x180045015  call    cs:__imp_CreateStreamOnHGlobal
0x18004501b  mov     ebx, eax
0x18004501d  test    eax, eax
0x18004501f  js      loc_1800450AB
0x180045025  mov     [rsp+10B0h+dwNumberOfBytesRead], r12d
0x18004502a  mov     rcx, [rsi+20h]; struct IUnknown *
0x18004502e  call    ?QueryContinueOnSite@@YAJPEAUIUnknown@@@Z; QueryContinueOnSite(IUnknown *)
0x180045033  mov     ebx, eax
0x180045035  test    eax, eax
0x180045037  js      short loc_18004507E
0x180045039  lea     r9, [rsp+10B0h+dwNumberOfBytesRead]; lpdwNumberOfBytesRead
0x18004503e  mov     [rsp+10B0h+dwNumberOfBytesRead], r12d
0x180045043  mov     r8d, 1000h; dwNumberOfBytesToRead
0x180045049  lea     rdx, [rsp+10B0h+Buffer]; lpBuffer
0x18004504e  mov     rcx, r14; hFile
0x180045051  call    cs:__imp_InternetReadFile
0x180045057  cmp     eax, 1
0x18004505a  jz      short loc_180045067
0x18004505c  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180045061  mov     ebx, eax
0x180045063  test    eax, eax
0x180045065  js      short loc_18004507E
0x180045067  mov     r8d, [rsp+10B0h+dwNumberOfBytesRead]; cb
0x18004506c  lea     rdx, [rsp+10B0h+Buffer]; pv
0x180045071  mov     rcx, [rsp+10B0h+hFile]; pstm
0x180045076  call    cs:__imp_IStream_Write
0x18004507c  mov     ebx, eax
0x18004507e  test    ebx, ebx
0x180045080  jnz     short loc_18004508B
0x180045082  cmp     [rsp+10B0h+dwNumberOfBytesRead], r12d
0x180045087  ja      short loc_18004502A
0x180045089  test    ebx, ebx
0x18004508b  js      short loc_1800450AB
0x18004508d  mov     rcx, [rsp+10B0h+hFile]; pstm
0x180045092  call    cs:__imp_IStream_Reset
0x180045098  mov     ebx, eax
0x18004509a  test    eax, eax
0x18004509c  js      short loc_1800450AB
0x18004509e  lea     rcx, [rsp+10B0h+hFile]
0x1800450a3  call    ?Detach@?$CComPtrBase@UIScope@@@ATL@@QEAAPEAUIScope@@XZ; ATL::CComPtrBase<IScope>::Detach(void)
0x1800450a8  mov     [r15], rax
0x1800450ab  lea     rcx, [rsp+10B0h+hFile]
0x1800450b0  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x1800450b5  mov     rcx, r14; hInternet
0x1800450b8  call    cs:__imp_InternetCloseHandle
0x1800450be  jmp     loc_180045144
0x1800450c3  cmp     eax, 80070032h
0x1800450c8  jnz     short loc_180045144
0x1800450ca  cmp     [rsi+50h], r12d
0x1800450ce  jz      short loc_18004513F
0x1800450d0  mov     rcx, [rdi]; pszUrl
0x1800450d3  mov     edx, 3; UrlIs
0x1800450d8  call    cs:__imp_UrlIsW
0x1800450de  test    eax, eax
0x1800450e0  jz      short loc_18004510D
0x1800450e2  mov     rcx, [rdi]; pszUrl
0x1800450e5  lea     r8, [rsp+10B0h+dwNumberOfBytesRead]; pcchPath
0x1800450ea  xor     r9d, r9d; dwFlags
0x1800450ed  mov     [rsp+10B0h+dwNumberOfBytesRead], 104h
0x1800450f5  lea     rdx, [rsp+10B0h+Buffer]; pszPath
0x1800450fa  call    cs:__imp_PathCreateFromUrlW
0x180045100  mov     ebx, eax
0x180045102  test    eax, eax
0x180045104  js      short loc_180045144
0x180045106  lea     rcx, [rsp+10B0h+Buffer]
0x18004510b  jmp     short loc_180045123
0x18004510d  cmp     [rsi+50h], r12d
0x180045111  jz      short loc_18004513F
0x180045113  mov     rcx, [rdi]; pszPath
0x180045116  call    cs:__imp_PathFileExistsW
0x18004511c  test    eax, eax
0x18004511e  jz      short loc_18004513F
0x180045120  mov     rcx, [rdi]; pszFile
0x180045123  xor     r9d, r9d; fCreate
0x180045126  mov     [rsp+10B0h+ppstm], r15; ppstm
0x18004512b  xor     r8d, r8d; dwAttributes
0x18004512e  mov     [rsp+10B0h+pstmTemplate], r12; pstmTemplate
0x180045133  xor     edx, edx; grfMode
0x180045135  call    cs:__imp_SHCreateStreamOnFileEx
0x18004513b  mov     ebx, eax
0x18004513d  jmp     short loc_180045144
0x18004513f  mov     ebx, 80004005h
0x180045144  test    cs:byte_180069A01, 4
0x18004514b  jz      short loc_180045163
0x18004514d  lea     rax, [rsp+10B0h+hFile]
0x180045152  lea     rdx, PerfTrack_OpenSearch_QueryServer_Stop
0x180045159  mov     [rsp+10B0h+pstmTemplate], rax
0x18004515e  call    McGenEventWrite_EtwEventWriteTransfer
0x180045163  test    ebx, ebx
0x180045165  jns     short loc_180045184
0x180045167  cmp     ebx, 800704C7h
0x18004516d  jz      short loc_180045184
0x18004516f  cmp     ebx, 80270000h
0x180045175  jz      short loc_180045184
0x180045177  mov     r8, [rdi]; unsigned __int16 *
0x18004517a  mov     edx, ebx; int
0x18004517c  mov     rcx, rsi; this
0x18004517f  call    ?_ShowInfoBarErrorMessage@COpenSearchRowset@@AEAAJJPEBG@Z; COpenSearchRowset::_ShowInfoBarErrorMessage(long,ushort const *)
0x180045184  mov     eax, ebx
0x180045186  mov     rcx, [rbp+0FB0h+var_50]
0x18004518d  xor     rcx, rsp; StackCookie
0x180045190  call    __security_check_cookie
0x180045195  add     rsp, 1078h
0x18004519c  pop     r15
0x18004519e  pop     r14
0x1800451a0  pop     r13
0x1800451a2  pop     r12
0x1800451a4  pop     rdi
0x1800451a5  pop     rsi
0x1800451a6  pop     rbx
0x1800451a7  pop     rbp
0x1800451a8  retn
```
