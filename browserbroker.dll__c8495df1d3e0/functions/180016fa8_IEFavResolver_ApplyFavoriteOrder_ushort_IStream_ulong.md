# IEFavResolver::ApplyFavoriteOrder(ushort *,IStream *,ulong)

- ea: `0x180016fa8`
- end: `0x1800173a1`
- name: `?ApplyFavoriteOrder@IEFavResolver@@AEAAJPEAGPEAUIStream@@K@Z`
- size: `1017`
- prototype: `__int64 __fastcall(IEFavResolver *__hidden this, unsigned __int16 *, struct IStream *, unsigned int)`
- caller_count: `2`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180017508`
- `0x180019b8c`

## callees

- `0x180001e20`
- `0x180002ce0`
- `0x180006cc4`
- `0x18000d17c`
- `0x18000d1c0`
- `0x1800154ac`
- `0x18001550c`
- `0x180015774`
- `0x1800160d0`
- `0x1800162fc`
- `0x180016428`
- `0x180016898`
- `0x180016fa8`
- `0x180017de4`
- `0x180017e50`
- `0x180024f94`
- `0x18002d010`

## import_xrefs

- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x180017037`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x1800171ab`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x180017037`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x1800171ab`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1800171f9`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18001720f`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1800171f9`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18001720f`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Reset` at `0x180017113`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Reset` at `0x180017113`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Read` at `0x18001716d`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Read` at `0x18001716d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800172c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800172d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800172c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800172d7`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180017027`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18001719b`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180017027`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18001719b`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x18001734e`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x18001734e`
- `api-ms-win-shell-namespace-l1-1-0!SHBindToObject` at `0x1800170b7`
- `api-ms-win-shell-namespace-l1-1-0!SHBindToObject` at `0x1800170b7`

## string_xrefs

- `0x180017219`: `Links`

## pseudocode

```c
__int64 __fastcall IEFavResolver::ApplyFavoriteOrder(
        IEFavResolver *this,
        unsigned __int16 *a2,
        struct IStream *a3,
        unsigned int a4)
{
  HRESULT FullPathFromUnifiedPath; // ebx
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  struct _ITEMIDLIST *FullAliasPidlFromFullPath; // rsi
  struct IStream *FavoritesOrderStream; // r14
  unsigned int v12; // r12d
  const WCHAR *v13; // r15
  unsigned int v14; // esi
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // r9
  const unsigned __int16 *v18; // r8
  int v19; // eax
  __int64 v20; // rdx
  __int64 v21; // r8
  char v23[8]; // [rsp+40h] [rbp-C0h] BYREF
  struct IE_GLOBAL_THREAD_STATE *v24; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int pv; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR pszStr1; // [rsp+58h] [rbp-A8h] BYREF
  struct _ITEMIDLIST *v27; // [rsp+60h] [rbp-A0h] BYREF
  HDPA hdpa; // [rsp+68h] [rbp-98h] BYREF
  struct IShellFolder *ppv; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v30; // [rsp+78h] [rbp-88h]
  __int64 CLSID; // [rsp+80h] [rbp-80h] BYREF
  struct _ITEMIDLIST *v32; // [rsp+88h] [rbp-78h]
  IEFavResolver *v33; // [rsp+90h] [rbp-70h]
  unsigned __int16 *v34; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 v35[264]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v36[264]; // [rsp+2B0h] [rbp+1B0h] BYREF

  pv = a4;
  pszStr1 = a2;
  v33 = this;
  v34 = a2;
  v30 = a4;
  FullPathFromUnifiedPath = IEFavResolver::GetFullPathFromUnifiedPath(this, a2, v36, a4);
  LODWORD(v24) = FullPathFromUnifiedPath;
  if ( FullPathFromUnifiedPath >= 0 )
  {
    if ( (unsigned int)dword_18003F000 > 5 )
    {
      v27 = (struct _ITEMIDLIST *)v36;
      v23[0] = 1;
      ppv = (struct IShellFolder *)GlobalThreadState();
      hdpa = (HDPA)IEConfiguration_GetCLSID(268435459);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>>(
        v7,
        (__int64)byte_180035ED9,
        v8,
        v9,
        (__int64 *)&hdpa,
        (__int64 *)&ppv,
        (__int64)v23,
        (const WCHAR **)&v27);
    }
    FullAliasPidlFromFullPath = IEFavResolver::GetFullAliasPidlFromFullPath(this, v36);
    v32 = FullAliasPidlFromFullPath;
    if ( FullAliasPidlFromFullPath )
    {
      ppv = 0;
      FullPathFromUnifiedPath = SHBindToObject(
                                  0,
                                  FullAliasPidlFromFullPath,
                                  0,
                                  &GUID_000214e6_0000_0000_c000_000000000046,
                                  (void **)&ppv);
      LODWORD(v24) = FullPathFromUnifiedPath;
      if ( FullPathFromUnifiedPath >= 0 )
      {
        hdpa = 0;
        if ( (unsigned int)CDPA_Base<__MIDL___MIDL_itf_inetpriv_shared_0000_0014_0001>::Create(&hdpa, 2) )
        {
          FavoritesOrderStream = GetFavoritesOrderStream(
                                   FullAliasPidlFromFullPath,
                                   0x1001u,
                                   (const unsigned __int16 *)this + 24);
          if ( FavoritesOrderStream )
          {
            LODWORD(v24) = 0;
            IStream_Reset(a3);
            v12 = 0;
            FullPathFromUnifiedPath = 0;
            v13 = pszStr1;
            v14 = pv;
            do
            {
              if ( v12 >= v14 )
                break;
              ++v12;
              pszStr1 = 0;
              pv = 0;
              FullPathFromUnifiedPath = IStream_ReadStrIE(a3, &pszStr1);
              LODWORD(v24) = FullPathFromUnifiedPath;
              if ( FullPathFromUnifiedPath >= 0 )
              {
                FullPathFromUnifiedPath = IStream_Read(a3, &pv, 4u);
                LODWORD(v24) = FullPathFromUnifiedPath;
                if ( FullPathFromUnifiedPath >= 0 )
                {
                  if ( (unsigned int)dword_18003F000 > 5 )
                  {
                    v27 = (struct _ITEMIDLIST *)pszStr1;
                    v23[0] = 1;
                    v24 = GlobalThreadState();
                    CLSID = IEConfiguration_GetCLSID(268435459);
                    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>>(
                      v15,
                      (__int64)&byte_180035E5F,
                      v16,
                      v17,
                      &CLSID,
                      (__int64 *)&v24,
                      (__int64)v23,
                      (const WCHAR **)&v27);
                  }
                  if ( pv )
                  {
                    if ( StrCmpICW(v13, L"ROOT") || StrCmpICW(pszStr1, L"_Favorites_Bar_") )
                      v18 = pszStr1;
                    else
                      v18 = L"Links";
                    v19 = StringCchCopyW(v35, 0x104u, v18);
                  }
                  else
                  {
                    v19 = StringCchPrintfW(v35, 0x104u, L"%s%s", pszStr1, L".url");
                  }
                  FullPathFromUnifiedPath = v19;
                  LODWORD(v24) = v19;
                  if ( v19 >= 0 )
                  {
                    v27 = 0;
                    FullPathFromUnifiedPath = ((__int64 (__fastcall *)(struct IShellFolder *, _QWORD, _QWORD, unsigned __int16 *, _QWORD, struct _ITEMIDLIST **, _QWORD))ppv->lpVtbl->ParseDisplayName)(
                                                ppv,
                                                0,
                                                0,
                                                v35,
                                                0,
                                                &v27,
                                                0);
                    LODWORD(v24) = FullPathFromUnifiedPath;
                    if ( FullPathFromUnifiedPath >= 0 && !(unsigned int)OrderList_Append(hdpa, v27, v12) )
                    {
                      LODWORD(v24) = -2147467259;
                      CoTaskMemFree(v27);
                      FullPathFromUnifiedPath = -2147467259;
                    }
                  }
                }
              }
              CoTaskMemFree((LPVOID)pszStr1);
            }
            while ( FullPathFromUnifiedPath >= 0 );
            if ( FullPathFromUnifiedPath >= 0 )
            {
              FullPathFromUnifiedPath = OrderList_SaveToStream(FavoritesOrderStream, hdpa, ppv);
              LODWORD(v24) = FullPathFromUnifiedPath;
            }
            (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)FavoritesOrderStream + 16LL))(FavoritesOrderStream);
            FullAliasPidlFromFullPath = v32;
            if ( FullPathFromUnifiedPath >= 0 )
              SHSendChangeMenuNotify(v33, v20, v21, v32);
          }
          else
          {
            LODWORD(v24) = -2147467259;
            FullPathFromUnifiedPath = -2147467259;
          }
          CDPA<__MIDL___MIDL_itf_inetpriv_shared_0000_0014_0001>::DestroyCallback(&hdpa);
        }
        else
        {
          FullPathFromUnifiedPath = -2147024882;
          LODWORD(v24) = -2147024882;
        }
      }
      ILFree(FullAliasPidlFromFullPath);
      ATL::CComPtrBase<IExtractIconW>::~CComPtrBase<IExtractIconW>((__int64 *)&ppv);
    }
    else
    {
      FullPathFromUnifiedPath = -2147024882;
      LODWORD(v24) = -2147024882;
    }
  }
  BrowserTelemetry::HandleOrderChangedFromEdge<unsigned short * &,unsigned long &,long &>((__int64)&v34);
  return (unsigned int)FullPathFromUnifiedPath;
}

```

## disassembly

```asm
0x180016fa8  push    rbp
0x180016faa  push    rbx
0x180016fab  push    rsi
0x180016fac  push    r12
0x180016fae  push    r13
0x180016fb0  push    r14
0x180016fb2  push    r15
0x180016fb4  lea     rbp, [rsp-3D0h]
0x180016fbc  sub     rsp, 4D0h
0x180016fc3  mov     rax, cs:__security_cookie
0x180016fca  xor     rax, rsp
0x180016fcd  mov     [rbp+400h+var_40], rax
0x180016fd4  mov     [rsp+500h+pv], r9d
0x180016fd9  mov     r13, r8
0x180016fdc  mov     [rsp+500h+pszStr1], rdx
0x180016fe1  mov     r15, rcx
0x180016fe4  mov     [rbp+400h+var_470], rcx
0x180016fe8  mov     [rbp+400h+var_468], rdx
0x180016fec  mov     [rsp+500h+var_488], r9d
0x180016ff1  lea     r8, [rbp+400h+var_250]; unsigned __int16 *
0x180016ff8  call    ?GetFullPathFromUnifiedPath@IEFavResolver@@AEAAJPEBGPEAGI@Z; IEFavResolver::GetFullPathFromUnifiedPath(ushort const *,ushort *,uint)
0x180016ffd  mov     ebx, eax
0x180016fff  mov     dword ptr [rsp+500h+var_4B8], eax
0x180017003  test    eax, eax
0x180017005  js      loc_18001736A
0x18001700b  mov     eax, cs:dword_18003F000
0x180017011  cmp     eax, 5
0x180017014  jbe     short loc_180017076
0x180017016  lea     rax, [rbp+400h+var_250]
0x18001701d  mov     [rsp+500h+var_4A0], rax
0x180017022  mov     [rsp+500h+var_4C0], 1
0x180017027  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x18001702d  mov     [rsp+500h+var_490], rax
0x180017032  mov     ecx, 10000003h
0x180017037  call    cs:__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z; IEConfiguration_GetCLSID(IEConfigurationID)
0x18001703d  mov     [rsp+500h+hdpa], rax
0x180017042  lea     rax, [rsp+500h+var_4A0]
0x180017047  mov     [rsp+500h+var_4C8], rax
0x18001704c  lea     rax, [rsp+500h+var_4C0]
0x180017051  mov     [rsp+500h+var_4D0], rax
0x180017056  lea     rax, [rsp+500h+var_490]
0x18001705b  mov     [rsp+500h+var_4D8], rax
0x180017060  lea     rax, [rsp+500h+hdpa]
0x180017065  mov     [rsp+500h+ppv], rax
0x18001706a  lea     rdx, byte_180035ED9
0x180017071  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_BrowserWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<ushort> const &)
0x180017076  lea     rdx, [rbp+400h+var_250]; unsigned __int16 *
0x18001707d  mov     rcx, r15; this
0x180017080  call    ?GetFullAliasPidlFromFullPath@IEFavResolver@@AEAAPEFAU_ITEMIDLIST@@PEBG@Z; IEFavResolver::GetFullAliasPidlFromFullPath(ushort const *)
0x180017085  mov     rsi, rax
0x180017088  mov     [rbp+400h+var_478], rax
0x18001708c  test    rax, rax
0x18001708f  jz      loc_180017361
0x180017095  mov     [rsp+500h+var_490], 0
0x18001709e  lea     rax, [rsp+500h+var_490]
0x1800170a3  mov     [rsp+500h+ppv], rax; ppv
0x1800170a8  lea     r9, _GUID_000214e6_0000_0000_c000_000000000046; riid
0x1800170af  xor     r8d, r8d; pbc
0x1800170b2  mov     rdx, rsi; pidl
0x1800170b5  xor     ecx, ecx; psf
0x1800170b7  call    cs:__imp_SHBindToObject
0x1800170bd  mov     ebx, eax
0x1800170bf  mov     dword ptr [rsp+500h+var_4B8], eax
0x1800170c3  test    eax, eax
0x1800170c5  js      loc_18001734B
0x1800170cb  mov     [rsp+500h+hdpa], 0
0x1800170d4  mov     edx, 2
0x1800170d9  lea     rcx, [rsp+500h+hdpa]
0x1800170de  call    ?Create@?$CDPA_Base@U__MIDL___MIDL_itf_inetpriv_shared_0000_0014_0001@@@@QEAAHH@Z; CDPA_Base<__MIDL___MIDL_itf_inetpriv_shared_0000_0014_0001>::Create(int)
0x1800170e3  test    eax, eax
0x1800170e5  jz      loc_180017342
0x1800170eb  lea     r8, [r15+30h]; unsigned __int16 *
0x1800170ef  mov     edx, 1001h; unsigned int
0x1800170f4  mov     rcx, rsi; struct _ITEMIDLIST *
0x1800170f7  call    ?GetFavoritesOrderStream@@YAPEAUIStream@@PEFBU_ITEMIDLIST@@KPEBG@Z; GetFavoritesOrderStream(_ITEMIDLIST const *,ulong,ushort const *)
0x1800170fc  mov     r14, rax
0x1800170ff  test    rax, rax
0x180017102  jz      loc_180017329
0x180017108  mov     dword ptr [rsp+500h+var_4B8], 0
0x180017110  mov     rcx, r13; pstm
0x180017113  call    cs:__imp_IStream_Reset
0x180017119  xor     r12d, r12d
0x18001711c  xor     ebx, ebx
0x18001711e  mov     r15, [rsp+500h+pszStr1]
0x180017123  mov     esi, [rsp+500h+pv]
0x180017127  cmp     r12d, esi
0x18001712a  jnb     loc_1800172E5
0x180017130  inc     r12d
0x180017133  mov     [rsp+500h+pszStr1], 0
0x18001713c  mov     [rsp+500h+pv], 0
0x180017144  lea     rdx, [rsp+500h+pszStr1]
0x180017149  mov     rcx, r13
0x18001714c  call    IStream_ReadStrIE
0x180017151  mov     ebx, eax
0x180017153  mov     dword ptr [rsp+500h+var_4B8], eax
0x180017157  test    eax, eax
0x180017159  js      loc_1800172D2
0x18001715f  mov     r8d, 4; cb
0x180017165  lea     rdx, [rsp+500h+pv]; pv
0x18001716a  mov     rcx, r13; pstm
0x18001716d  call    cs:__imp_IStream_Read
0x180017173  mov     ebx, eax
0x180017175  mov     dword ptr [rsp+500h+var_4B8], eax
0x180017179  test    eax, eax
0x18001717b  js      loc_1800172D2
0x180017181  mov     eax, cs:dword_18003F000
0x180017187  cmp     eax, 5
0x18001718a  jbe     short loc_1800171E8
0x18001718c  mov     rax, [rsp+500h+pszStr1]
0x180017191  mov     [rsp+500h+var_4A0], rax
0x180017196  mov     [rsp+500h+var_4C0], 1
0x18001719b  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1800171a1  mov     [rsp+500h+var_4B8], rax
0x1800171a6  mov     ecx, 10000003h
0x1800171ab  call    cs:__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z; IEConfiguration_GetCLSID(IEConfigurationID)
0x1800171b1  mov     [rbp+400h+var_480], rax
0x1800171b5  lea     rax, [rsp+500h+var_4A0]
0x1800171ba  mov     [rsp+500h+var_4C8], rax
0x1800171bf  lea     rax, [rsp+500h+var_4C0]
0x1800171c4  mov     [rsp+500h+var_4D0], rax
0x1800171c9  lea     rax, [rsp+500h+var_4B8]
0x1800171ce  mov     [rsp+500h+var_4D8], rax
0x1800171d3  lea     rax, [rbp+400h+var_480]
0x1800171d7  mov     [rsp+500h+ppv], rax
0x1800171dc  lea     rdx, byte_180035E5F
0x1800171e3  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_BrowserWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<ushort> const &)
0x1800171e8  cmp     [rsp+500h+pv], 0
0x1800171ed  jz      short loc_180017237
0x1800171ef  lea     rdx, aRoot_0; "ROOT"
0x1800171f6  mov     rcx, r15; pszStr1
0x1800171f9  call    cs:__imp_StrCmpICW
0x1800171ff  test    eax, eax
0x180017201  jnz     short loc_180017230
0x180017203  lea     rdx, aFavoritesBar_0; "_Favorites_Bar_"
0x18001720a  mov     rcx, [rsp+500h+pszStr1]; pszStr1
0x18001720f  call    cs:__imp_StrCmpICW
0x180017215  test    eax, eax
0x180017217  jnz     short loc_180017230
0x180017219  lea     r8, aLinks; "Links"
0x180017220  mov     edx, 104h; unsigned __int64
0x180017225  lea     rcx, [rbp+400h+var_460]; unsigned __int16 *
0x180017229  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001722e  jmp     short loc_18001725D
0x180017230  mov     r8, [rsp+500h+pszStr1]
0x180017235  jmp     short loc_180017220
0x180017237  lea     rax, aUrl; ".url"
0x18001723e  mov     [rsp+500h+ppv], rax
0x180017243  mov     r9, [rsp+500h+pszStr1]
0x180017248  lea     r8, aSS; "%s%s"
0x18001724f  mov     edx, 104h; unsigned __int64
0x180017254  lea     rcx, [rbp+400h+var_460]; unsigned __int16 *
0x180017258  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001725d  mov     ebx, eax
0x18001725f  mov     dword ptr [rsp+500h+var_4B8], eax
0x180017263  xor     r8d, r8d
0x180017266  test    eax, eax
0x180017268  js      short loc_1800172D2
0x18001726a  mov     [rsp+500h+var_4A0], r8
0x18001726f  mov     rcx, [rsp+500h+var_490]
0x180017274  mov     rax, [rcx]
0x180017277  mov     [rsp+500h+var_4D0], r8
0x18001727c  lea     rdx, [rsp+500h+var_4A0]
0x180017281  mov     [rsp+500h+var_4D8], rdx
0x180017286  mov     [rsp+500h+ppv], r8
0x18001728b  lea     r9, [rbp+400h+var_460]
0x18001728f  xor     edx, edx
0x180017291  mov     rax, [rax+18h]
0x180017295  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001729a  mov     ebx, eax
0x18001729c  mov     dword ptr [rsp+500h+var_4B8], eax
0x1800172a0  test    eax, eax
0x1800172a2  js      short loc_1800172D2
0x1800172a4  mov     r8d, r12d; int
0x1800172a7  mov     rdx, [rsp+500h+var_4A0]; struct _ITEMIDLIST *
0x1800172ac  mov     rcx, [rsp+500h+hdpa]; hdpa
0x1800172b1  call    ?OrderList_Append@@YAHPEAU_DPA@@PEFAU_ITEMIDLIST@@H@Z; OrderList_Append(_DPA *,_ITEMIDLIST *,int)
0x1800172b6  test    eax, eax
0x1800172b8  jnz     short loc_1800172D2
0x1800172ba  mov     dword ptr [rsp+500h+var_4B8], 80004005h
0x1800172c2  mov     rcx, [rsp+500h+var_4A0]; pv
0x1800172c7  call    cs:__imp_CoTaskMemFree
0x1800172cd  mov     ebx, 80004005h
0x1800172d2  mov     rcx, [rsp+500h+pszStr1]; pv
0x1800172d7  call    cs:__imp_CoTaskMemFree
0x1800172dd  test    ebx, ebx
0x1800172df  jns     loc_180017127
0x1800172e5  test    ebx, ebx
0x1800172e7  js      short loc_180017301
0x1800172e9  mov     r8, [rsp+500h+var_490]; struct IShellFolder *
0x1800172ee  mov     rdx, [rsp+500h+hdpa]; hdpa
0x1800172f3  mov     rcx, r14; pstream
0x1800172f6  call    ?OrderList_SaveToStream@@YAJPEAUIStream@@PEAU_DPA@@PEAUIShellFolder@@@Z; OrderList_SaveToStream(IStream *,_DPA *,IShellFolder *)
0x1800172fb  mov     ebx, eax
0x1800172fd  mov     dword ptr [rsp+500h+var_4B8], eax
0x180017301  mov     rax, [r14]
0x180017304  mov     rcx, r14
0x180017307  mov     rax, [rax+10h]
0x18001730b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017310  test    ebx, ebx
0x180017312  mov     rsi, [rbp+400h+var_478]
0x180017316  mov     r15, [rbp+400h+var_470]
0x18001731a  js      short loc_180017336
0x18001731c  mov     r9, rsi
0x18001731f  mov     rcx, r15
0x180017322  call    SHSendChangeMenuNotify
0x180017327  jmp     short loc_180017336
0x180017329  mov     dword ptr [rsp+500h+var_4B8], 80004005h
0x180017331  mov     ebx, 80004005h
0x180017336  lea     rcx, [rsp+500h+hdpa]
0x18001733b  call    ?DestroyCallback@?$CDPA@U__MIDL___MIDL_itf_inetpriv_shared_0000_0014_0001@@@@QEAAXP6AHPEAU__MIDL___MIDL_itf_inetpriv_shared_0000_0014_0001@@PEAX@Z1@Z; CDPA<__MIDL___MIDL_itf_inetpriv_shared_0000_0014_0001>::DestroyCallback(int (*)(__MIDL___MIDL_itf_inetpriv_shared_0000_0014_0001 *,void *),void *)
0x180017340  jmp     short loc_18001734B
0x180017342  mov     ebx, 8007000Eh
0x180017347  mov     dword ptr [rsp+500h+var_4B8], ebx
0x18001734b  mov     rcx, rsi; pidl
0x18001734e  call    cs:__imp_ILFree
0x180017354  nop
0x180017355  lea     rcx, [rsp+500h+var_490]
0x18001735a  call    ??1?$CComPtrBase@UIExtractIconW@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IExtractIconW>::~CComPtrBase<IExtractIconW>(void)
0x18001735f  jmp     short loc_18001736A
0x180017361  mov     ebx, 8007000Eh
0x180017366  mov     dword ptr [rsp+500h+var_4B8], ebx
0x18001736a  lea     r8, [rsp+500h+var_4B8]
0x18001736f  lea     rdx, [rsp+500h+var_488]
0x180017374  lea     rcx, [rbp+400h+var_468]
0x180017378  call    ??$HandleOrderChangedFromEdge@AEAPEAGAEAKAEAJ@BrowserTelemetry@@SAXAEAPEAGAEAKAEAJ@Z; BrowserTelemetry::HandleOrderChangedFromEdge<ushort * &,ulong &,long &>(ushort * &,ulong &,long &)
0x18001737d  mov     eax, ebx
0x18001737f  mov     rcx, [rbp+400h+var_40]
0x180017386  xor     rcx, rsp; StackCookie
0x180017389  call    __security_check_cookie
0x18001738e  add     rsp, 4D0h
0x180017395  pop     r15
0x180017397  pop     r14
0x180017399  pop     r13
0x18001739b  pop     r12
0x18001739d  pop     rsi
0x18001739e  pop     rbx
0x18001739f  pop     rbp
0x1800173a0  retn
```
