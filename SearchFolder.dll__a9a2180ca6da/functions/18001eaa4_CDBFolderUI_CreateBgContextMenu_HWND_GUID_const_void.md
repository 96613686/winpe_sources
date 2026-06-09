# CDBFolderUI::_CreateBgContextMenu(HWND__ *,_GUID const &,void * *)

- ea: `0x18001eaa4`
- end: `0x18001ee14`
- name: `?_CreateBgContextMenu@CDBFolderUI@@AEAAJPEAUHWND__@@AEBU_GUID@@PEAPEAX@Z`
- size: `880`
- prototype: `__int64 __fastcall(CDBFolderUI *this, HWND, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180003090`

## callees

- `0x1800033d0`
- `0x1800045d0`
- `0x180004640`
- `0x180004a10`
- `0x180005460`
- `0x1800054b0`
- `0x180005c88`
- `0x180006900`
- `0x180006924`
- `0x1800123b8`
- `0x18001eaa4`
- `0x180051010`

## import_xrefs

- `SHELL32!AssocCreateForClasses` at `0x18001ec64`
- `SHELL32!AssocCreateForClasses` at `0x18001ec64`
- `SHELL32!SHCreateDefaultContextMenu` at `0x18001ed11`
- `SHELL32!SHCreateDefaultContextMenu` at `0x18001ed11`
- `SHELL32!__imp_ILFindLastID` at `0x18001eb94`
- `SHELL32!__imp_ILFindLastID` at `0x18001eb94`

## pseudocode

```c
__int64 __fastcall CDBFolderUI::_CreateBgContextMenu(CDBFolderUI *this, HWND a2, const struct _GUID *a3, void **a4)
{
  IShellFolder **v7; // rdi
  int v8; // eax
  unsigned int v9; // ebx
  int v10; // eax
  int v11; // eax
  LPITEMIDLIST ID; // rsi
  int v13; // ebx
  __int64 v14; // r8
  HRESULT v15; // eax
  char *v16; // rax
  __int64 v17; // rdx
  _QWORD *v18; // rcx
  HRESULT v19; // eax
  __int64 v20; // r9
  __int64 v21; // rdx
  int *v23; // [rsp+20h] [rbp-E0h]
  LPCITEMIDLIST pidl; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v25; // [rsp+48h] [rbp-B8h] BYREF
  void *ppv; // [rsp+50h] [rbp-B0h] BYREF
  void *v27; // [rsp+58h] [rbp-A8h] BYREF
  int v28[2]; // [rsp+60h] [rbp-A0h] BYREF
  const WCHAR *v29; // [rsp+68h] [rbp-98h] BYREF
  __int64 v30; // [rsp+70h] [rbp-90h] BYREF
  __int64 v31; // [rsp+78h] [rbp-88h] BYREF
  DEFCONTEXTMENU pdcm; // [rsp+80h] [rbp-80h] BYREF
  ASSOCIATIONELEMENT rgClasses; // [rsp+D0h] [rbp-30h] BYREF
  int v34; // [rsp+E8h] [rbp-18h]
  __int64 v35; // [rsp+F0h] [rbp-10h]
  __int64 v36; // [rsp+F8h] [rbp-8h]
  int v37; // [rsp+100h] [rbp+0h]
  __int64 v38; // [rsp+108h] [rbp+8h]
  void *v39; // [rsp+110h] [rbp+10h]
  int v40; // [rsp+118h] [rbp+18h]
  __int64 v41; // [rsp+120h] [rbp+20h]
  unsigned __int64 v42; // [rsp+128h] [rbp+28h]
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  *a4 = 0;
  v31 = 0;
  v7 = (IShellFolder **)((char *)this + 24);
  v8 = Microsoft::WRL::ComPtr<IShellFolder3>::As<IPersistFolder2>(
         (__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 3,
         &v31);
  v9 = v8;
  if ( v8 >= 0 )
  {
    pidl = 0;
    v10 = (*(__int64 (__fastcall **)(__int64, LPCITEMIDLIST *))(*(_QWORD *)v31 + 40LL))(v31, &pidl);
    v9 = v10;
    if ( v10 >= 0 )
    {
      v25 = 0;
      v11 = Microsoft::WRL::ComPtr<IShellFolder3>::As<IDBFolderForUIPriv>(
              (__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))v7,
              &v25);
      v9 = v11;
      if ( v11 >= 0 )
      {
        ID = ILFindLastID(pidl);
        v29 = 0;
        *(_QWORD *)v28 = 0;
        v27 = 0;
        v13 = (*(__int64 (__fastcall **)(__int64, LPITEMIDLIST))(*(_QWORD *)v25 + 32LL))(v25, ID);
        if ( v13 )
        {
          v23 = v28;
          LOBYTE(v14) = 1;
          (*(void (__fastcall **)(__int64, LPITEMIDLIST, __int64, const WCHAR **))(*(_QWORD *)v25 + 24LL))(
            v25,
            ID,
            v14,
            &v29);
        }
        rgClasses.ac = ASSOCCLASS_PROGID_STR;
        rgClasses.hkClass = 0;
        rgClasses.pszClass = v29;
        v34 = 2;
        v35 = 0;
        v36 = *(_QWORD *)v28;
        v37 = 2;
        v38 = 0;
        v39 = v27;
        v40 = 2;
        v41 = 0;
        v42 = (unsigned __int64)L"Stack\\Background" & -(__int64)(v13 != 0);
        ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&ppv);
        v15 = AssocCreateForClasses(&rgClasses, 4u, &GUID_c46ca590_3c3f_11d2_bee6_0000f805ca57, &ppv);
        v9 = v15;
        if ( v15 >= 0 )
        {
          v16 = (char *)operator new(0x20u, (const struct std::nothrow_t *)std::nothrow);
          if ( v16 )
          {
            CObjectWithSite::CObjectWithSite((CObjectWithSite *)(v16 + 8));
            *(_QWORD *)v17 = &CDBFolderBgMenuCB::`vftable'{for `IContextMenuCB'};
            *v18 = &CDBFolderBgMenuCB::`vftable'{for `CObjectWithSite'};
            *(_DWORD *)(v17 + 24) = 1;
            v30 = v17;
            pdcm.hwnd = a2;
            pdcm.pcmcb = (IContextMenuCB *)v17;
            pdcm.pidlFolder = pidl;
            pdcm.psf = *v7;
            *(_QWORD *)&pdcm.cidl = 0;
            pdcm.apidl = 0;
            pdcm.punkAssociationInfo = (IUnknown *)ppv;
            *(_QWORD *)&pdcm.cKeys = 0;
            pdcm.aKeys = 0;
            v19 = SHCreateDefaultContextMenu(&pdcm, a3, a4);
            v9 = v19;
            if ( v19 >= 0 )
            {
              ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v30);
              ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&ppv);
              CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&v27);
              CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>((void **)v28);
              CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>((void **)&v29);
              Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v25);
              CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>((void **)&pidl);
              v9 = 0;
              goto LABEL_20;
            }
            v20 = (unsigned int)v19;
            v21 = 1396;
          }
          else
          {
            v30 = 0;
            v9 = -2147024882;
            v20 = 2147942414LL;
            v21 = 1393;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v21,
            (unsigned int)"shell\\searchfolder\\dbfolder_ui.cpp",
            (const char *)v20,
            (int)v23);
          ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v30);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x56E,
            (unsigned int)"shell\\searchfolder\\dbfolder_ui.cpp",
            (const char *)(unsigned int)v15,
            (int)v23);
        }
        ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&ppv);
        CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&v27);
        CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>((void **)v28);
        CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>((void **)&v29);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x559,
          (unsigned int)"shell\\searchfolder\\dbfolder_ui.cpp",
          (const char *)(unsigned int)v11,
          (int)v23);
      }
      Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v25);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x556,
        (unsigned int)"shell\\searchfolder\\dbfolder_ui.cpp",
        (const char *)(unsigned int)v10,
        (int)v23);
    }
    CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>((void **)&pidl);
    goto LABEL_20;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x554,
    (unsigned int)"shell\\searchfolder\\dbfolder_ui.cpp",
    (const char *)(unsigned int)v8,
    (int)v23);
LABEL_20:
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v31);
  return v9;
}

```

## disassembly

```asm
0x18001eaa4  push    rbp
0x18001eaa6  push    rbx
0x18001eaa7  push    rsi
0x18001eaa8  push    rdi
0x18001eaa9  push    r12
0x18001eaab  push    r13
0x18001eaad  push    r14
0x18001eaaf  push    r15
0x18001eab1  lea     rbp, [rsp-48h]
0x18001eab6  sub     rsp, 148h
0x18001eabd  mov     rax, cs:__security_cookie
0x18001eac4  xor     rax, rsp
0x18001eac7  mov     [rbp+80h+var_50], rax
0x18001eacb  mov     r14, r9
0x18001eace  mov     r12, r8
0x18001ead1  mov     r15, rdx
0x18001ead4  xor     r13d, r13d
0x18001ead7  mov     [r9], r13
0x18001eada  mov     [rsp+180h+var_108], r13
0x18001eadf  lea     rdi, [rcx+18h]
0x18001eae3  lea     rdx, [rsp+180h+var_108]
0x18001eae8  mov     rcx, rdi
0x18001eaeb  call    ??$As@UIPersistFolder2@@@?$ComPtr@UIShellFolder3@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIPersistFolder2@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IShellFolder3>::As<IPersistFolder2>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IPersistFolder2>>)
0x18001eaf0  mov     ebx, eax
0x18001eaf2  test    eax, eax
0x18001eaf4  jns     short loc_18001EB16
0x18001eaf6  mov     rcx, [rbp+88h]; this
0x18001eafd  mov     r9d, eax; char *
0x18001eb00  lea     r8, aShellSearchfol_0; "shell\\searchfolder\\dbfolder_ui.cpp"
0x18001eb07  mov     edx, 554h; void *
0x18001eb0c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001eb11  jmp     loc_18001EDE8
0x18001eb16  mov     [rsp+180h+pidl], r13
0x18001eb1b  mov     rcx, [rsp+180h+var_108]
0x18001eb20  mov     rax, [rcx]
0x18001eb23  lea     rdx, [rsp+180h+pidl]
0x18001eb28  mov     rax, [rax+28h]
0x18001eb2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eb31  mov     ebx, eax
0x18001eb33  test    eax, eax
0x18001eb35  jns     short loc_18001EB57
0x18001eb37  mov     rcx, [rbp+88h]; this
0x18001eb3e  mov     r9d, eax; char *
0x18001eb41  lea     r8, aShellSearchfol_0; "shell\\searchfolder\\dbfolder_ui.cpp"
0x18001eb48  mov     edx, 556h; void *
0x18001eb4d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001eb52  jmp     loc_18001EDDD
0x18001eb57  mov     [rsp+180h+var_138], r13
0x18001eb5c  lea     rdx, [rsp+180h+var_138]
0x18001eb61  mov     rcx, rdi
0x18001eb64  call    ??$As@UIDBFolderForUIPriv@@@?$ComPtr@UIShellFolder3@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIDBFolderForUIPriv@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IShellFolder3>::As<IDBFolderForUIPriv>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IDBFolderForUIPriv>>)
0x18001eb69  mov     ebx, eax
0x18001eb6b  test    eax, eax
0x18001eb6d  jns     short loc_18001EB8F
0x18001eb6f  mov     rcx, [rbp+88h]; this
0x18001eb76  mov     r9d, eax; char *
0x18001eb79  lea     r8, aShellSearchfol_0; "shell\\searchfolder\\dbfolder_ui.cpp"
0x18001eb80  mov     edx, 559h; void *
0x18001eb85  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001eb8a  jmp     loc_18001EDD2
0x18001eb8f  mov     rcx, [rsp+180h+pidl]; pidl
0x18001eb94  call    cs:__imp_ILFindLastID
0x18001eb9a  mov     rsi, rax
0x18001eb9d  mov     [rsp+180h+var_118], r13
0x18001eba2  mov     qword ptr [rsp+180h+var_120], r13
0x18001eba7  mov     [rsp+180h+var_128], r13
0x18001ebac  mov     rcx, [rsp+180h+var_138]
0x18001ebb1  mov     rdx, [rcx]
0x18001ebb4  mov     rax, [rdx+20h]
0x18001ebb8  mov     rdx, rsi
0x18001ebbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ebc0  mov     ebx, eax
0x18001ebc2  test    eax, eax
0x18001ebc4  jz      short loc_18001EBF6
0x18001ebc6  mov     rcx, [rsp+180h+var_138]
0x18001ebcb  mov     rdx, [rcx]
0x18001ebce  mov     rax, [rdx+18h]
0x18001ebd2  lea     rdx, [rsp+180h+var_128]
0x18001ebd7  mov     [rsp+180h+var_158], rdx
0x18001ebdc  lea     rdx, [rsp+180h+var_120]
0x18001ebe1  mov     qword ptr [rsp+180h+var_160], rdx; int
0x18001ebe6  lea     r9, [rsp+180h+var_118]
0x18001ebeb  mov     r8b, 1
0x18001ebee  mov     rdx, rsi
0x18001ebf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ebf6  mov     ecx, 2
0x18001ebfb  mov     [rbp+80h+rgClasses.ac], ecx
0x18001ebfe  mov     [rbp+80h+rgClasses.hkClass], r13
0x18001ec02  mov     rax, [rsp+180h+var_118]
0x18001ec07  mov     [rbp+80h+rgClasses.pszClass], rax
0x18001ec0b  mov     [rbp+80h+var_98], ecx
0x18001ec0e  mov     [rbp+80h+var_90], r13
0x18001ec12  mov     rax, qword ptr [rsp+180h+var_120]
0x18001ec17  mov     [rbp+80h+var_88], rax
0x18001ec1b  mov     [rbp+80h+var_80], ecx
0x18001ec1e  mov     [rbp+80h+var_78], r13
0x18001ec22  mov     rax, [rsp+180h+var_128]
0x18001ec27  mov     [rbp+80h+var_70], rax
0x18001ec2b  mov     [rbp+80h+var_68], ecx
0x18001ec2e  mov     [rbp+80h+var_60], r13
0x18001ec32  neg     ebx
0x18001ec34  sbb     rax, rax
0x18001ec37  lea     rcx, aStackBackgroun; "Stack\\Background"
0x18001ec3e  and     rax, rcx
0x18001ec41  mov     [rbp+80h+var_58], rax
0x18001ec45  lea     rcx, [rsp+180h+ppv]; void *
0x18001ec4a  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x18001ec4f  lea     r9, [rsp+180h+ppv]; ppv
0x18001ec54  lea     r8, _GUID_c46ca590_3c3f_11d2_bee6_0000f805ca57; riid
0x18001ec5b  mov     edx, 4; cClasses
0x18001ec60  lea     rcx, [rbp+80h+rgClasses]; rgClasses
0x18001ec64  call    cs:__imp_AssocCreateForClasses
0x18001ec6a  mov     ebx, eax
0x18001ec6c  test    eax, eax
0x18001ec6e  jns     short loc_18001EC90
0x18001ec70  mov     rcx, [rbp+88h]; this
0x18001ec77  mov     r9d, eax; char *
0x18001ec7a  lea     r8, aShellSearchfol_0; "shell\\searchfolder\\dbfolder_ui.cpp"
0x18001ec81  mov     edx, 56Eh; void *
0x18001ec86  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ec8b  jmp     loc_18001EDA6
0x18001ec90  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001ec97  mov     ecx, 20h ; ' '; unsigned __int64
0x18001ec9c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001eca1  mov     rdx, rax
0x18001eca4  test    rax, rax
0x18001eca7  jz      loc_18001ED77
0x18001ecad  lea     rcx, [rax+8]; this
0x18001ecb1  call    ??0CObjectWithSite@@QEAA@XZ; CObjectWithSite::CObjectWithSite(void)
0x18001ecb6  lea     r8, ??_7CDBFolderBgMenuCB@@6BIContextMenuCB@@@; const CDBFolderBgMenuCB::`vftable'{for `IContextMenuCB'}
0x18001ecbd  mov     [rdx], r8
0x18001ecc0  lea     rax, ??_7CDBFolderBgMenuCB@@6BCObjectWithSite@@@; const CDBFolderBgMenuCB::`vftable'{for `CObjectWithSite'}
0x18001ecc7  mov     [rcx], rax
0x18001ecca  mov     dword ptr [rdx+18h], 1
0x18001ecd1  mov     [rsp+180h+var_110], rdx
0x18001ecd6  mov     [rbp+80h+pdcm.hwnd], r15
0x18001ecda  mov     [rbp+80h+pdcm.pcmcb], rdx
0x18001ecde  mov     rax, [rsp+180h+pidl]
0x18001ece3  mov     [rbp+80h+pdcm.pidlFolder], rax
0x18001ece7  mov     rax, [rdi]
0x18001ecea  mov     [rbp+80h+pdcm.psf], rax
0x18001ecee  mov     qword ptr [rbp+80h+pdcm.cidl], r13
0x18001ecf2  mov     [rbp+80h+pdcm.apidl], r13
0x18001ecf6  mov     rax, [rsp+180h+ppv]
0x18001ecfb  mov     [rbp+80h+pdcm.punkAssociationInfo], rax
0x18001ecff  mov     qword ptr [rbp+80h+pdcm.cKeys], r13
0x18001ed03  mov     [rbp+80h+pdcm.aKeys], r13
0x18001ed07  mov     r8, r14; ppv
0x18001ed0a  mov     rdx, r12; riid
0x18001ed0d  lea     rcx, [rbp+80h+pdcm]; pdcm
0x18001ed11  call    cs:__imp_SHCreateDefaultContextMenu
0x18001ed17  mov     ebx, eax
0x18001ed19  test    eax, eax
0x18001ed1b  jns     short loc_18001ED27
0x18001ed1d  mov     r9d, eax
0x18001ed20  mov     edx, 574h
0x18001ed25  jmp     short loc_18001ED89
0x18001ed27  lea     rcx, [rsp+180h+var_110]
0x18001ed2c  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x18001ed31  lea     rcx, [rsp+180h+ppv]
0x18001ed36  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x18001ed3b  nop
0x18001ed3c  lea     rcx, [rsp+180h+var_128]; void *
0x18001ed41  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x18001ed46  nop
0x18001ed47  lea     rcx, [rsp+180h+var_120]; void *
0x18001ed4c  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x18001ed51  nop
0x18001ed52  lea     rcx, [rsp+180h+var_118]; void *
0x18001ed57  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x18001ed5c  nop
0x18001ed5d  lea     rcx, [rsp+180h+var_138]
0x18001ed62  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18001ed67  nop
0x18001ed68  lea     rcx, [rsp+180h+pidl]; void *
0x18001ed6d  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x18001ed72  mov     ebx, r13d
0x18001ed75  jmp     short loc_18001EDE8
0x18001ed77  mov     [rsp+180h+var_110], r13
0x18001ed7c  mov     ebx, 8007000Eh
0x18001ed81  mov     r9d, ebx; char *
0x18001ed84  mov     edx, 571h; void *
0x18001ed89  lea     r8, aShellSearchfol_0; "shell\\searchfolder\\dbfolder_ui.cpp"
0x18001ed90  mov     rcx, [rbp+88h]; this
0x18001ed97  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ed9c  lea     rcx, [rsp+180h+var_110]
0x18001eda1  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x18001eda6  lea     rcx, [rsp+180h+ppv]
0x18001edab  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x18001edb0  nop
0x18001edb1  lea     rcx, [rsp+180h+var_128]; void *
0x18001edb6  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x18001edbb  nop
0x18001edbc  lea     rcx, [rsp+180h+var_120]; void *
0x18001edc1  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x18001edc6  nop
0x18001edc7  lea     rcx, [rsp+180h+var_118]; void *
0x18001edcc  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x18001edd1  nop
0x18001edd2  lea     rcx, [rsp+180h+var_138]
0x18001edd7  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18001eddc  nop
0x18001eddd  lea     rcx, [rsp+180h+pidl]; void *
0x18001ede2  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x18001ede7  nop
0x18001ede8  lea     rcx, [rsp+180h+var_108]
0x18001eded  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18001edf2  mov     eax, ebx
0x18001edf4  mov     rcx, [rbp+80h+var_50]
0x18001edf8  xor     rcx, rsp; StackCookie
0x18001edfb  call    __security_check_cookie
0x18001ee00  add     rsp, 148h
0x18001ee07  pop     r15
0x18001ee09  pop     r14
0x18001ee0b  pop     r13
0x18001ee0d  pop     r12
0x18001ee0f  pop     rdi
0x18001ee10  pop     rsi
0x18001ee11  pop     rbx
0x18001ee12  pop     rbp
0x18001ee13  retn
```
