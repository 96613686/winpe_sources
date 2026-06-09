# RemoteFileBrowseClient::ShowFileDialog(IFileDialog *,ushort const *,ushort const *,ushort const *)

- ea: `0x18000ba9c`
- end: `0x18000c40f`
- name: `?ShowFileDialog@RemoteFileBrowseClient@@AEAA_NPEAUIFileDialog@@PEBG11@Z`
- size: `2419`
- prototype: `bool __fastcall(RemoteFileBrowseClient *__hidden this, struct IFileDialog *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000b640`

## callees

- `0x180002030`
- `0x1800020d0`
- `0x180002db8`
- `0x1800054a4`
- `0x1800056e0`
- `0x18000591c`
- `0x180007150`
- `0x18000762c`
- `0x1800092f0`
- `0x18000b0ec`
- `0x18000b184`
- `0x18000b374`
- `0x18000b420`
- `0x18000b4a0`
- `0x18000ba9c`
- `0x18000d414`
- `0x18000d740`
- `0x180017434`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c19a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c19a`
- `SHELL32!SHCreateItemInKnownFolder` at `0x18000bde1`
- `SHELL32!SHCreateItemInKnownFolder` at `0x18000bf02`
- `SHELL32!SHCreateItemInKnownFolder` at `0x18000bde1`
- `SHELL32!SHCreateItemInKnownFolder` at `0x18000bf02`
- `SHELL32!SHCreateItemFromParsingName` at `0x18000bd16`
- `SHELL32!SHCreateItemFromParsingName` at `0x18000bed4`
- `SHELL32!SHCreateItemFromParsingName` at `0x18000bf25`
- `SHELL32!SHCreateItemFromParsingName` at `0x18000bd16`
- `SHELL32!SHCreateItemFromParsingName` at `0x18000bed4`
- `SHELL32!SHCreateItemFromParsingName` at `0x18000bf25`

## pseudocode

```c
bool __fastcall RemoteFileBrowseClient::ShowFileDialog(
        RemoteFileBrowseClient *this,
        struct IFileDialog *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5)
{
  int v7; // edx
  unsigned int v8; // edx
  int v9; // eax
  int v10; // eax
  int v11; // eax
  __int64 ServerRegistrar; // rax
  RTL_SRWLOCK *v13; // rcx
  RTL_SRWLOCK *v14; // rdx
  volatile signed __int32 *v15; // rbx
  volatile signed __int32 *v16; // rbx
  unsigned __int64 v17; // rdx
  PCWSTR *v18; // rcx
  void **v19; // rax
  const WCHAR *v20; // rcx
  HRESULT v21; // eax
  int v22; // eax
  int v23; // eax
  _QWORD *v24; // rcx
  void *v25; // rcx
  void **v26; // rax
  HRESULT v27; // eax
  int v28; // eax
  const wchar_t *v29; // rcx
  unsigned __int64 v30; // rdx
  PCWSTR *v31; // rcx
  void **v32; // rax
  const WCHAR *v33; // rcx
  void **v34; // rax
  void **v35; // rax
  const WCHAR *v36; // rcx
  int v37; // eax
  _QWORD *v38; // rax
  _QWORD *v39; // rax
  int v40; // eax
  int v41; // eax
  _QWORD *v42; // rax
  _QWORD *v43; // rbx
  int Interface; // eax
  int v45; // eax
  void *v46; // rcx
  unsigned int v47; // eax
  int v48; // eax
  __int64 v49; // rax
  int v50; // eax
  __int64 v51; // r8
  const void *v52; // r9
  char **v53; // rcx
  unsigned __int64 v54; // rdx
  char *v55; // r14
  __int64 v56; // rbx
  _QWORD *v57; // rcx
  _QWORD *v58; // rcx
  bool v59; // di
  __int64 v60; // rcx
  __int64 v61; // rcx
  volatile signed __int32 *v62; // rbx
  unsigned int v64; // eax
  int ppv; // [rsp+20h] [rbp-C1h]
  int ppva; // [rsp+20h] [rbp-C1h]
  int ppvb; // [rsp+20h] [rbp-C1h]
  char v68; // [rsp+30h] [rbp-B1h] BYREF
  unsigned int v69; // [rsp+34h] [rbp-ADh] BYREF
  _QWORD *v70; // [rsp+38h] [rbp-A9h] BYREF
  void *Src[2]; // [rsp+40h] [rbp-A1h] BYREF
  __int64 v72; // [rsp+50h] [rbp-91h] BYREF
  int v73; // [rsp+58h] [rbp-89h] BYREF
  __int64 v74; // [rsp+60h] [rbp-81h] BYREF
  PSRWLOCK SRWLock[2]; // [rsp+68h] [rbp-79h] BYREF
  _QWORD v76[3]; // [rsp+78h] [rbp-69h] BYREF
  __int16 v77; // [rsp+90h] [rbp-51h]
  char v78[8]; // [rsp+98h] [rbp-49h] BYREF
  volatile signed __int32 *v79; // [rsp+A0h] [rbp-41h]
  PCWSTR v80[2]; // [rsp+A8h] [rbp-39h] BYREF
  unsigned __int64 v81; // [rsp+B8h] [rbp-29h]
  unsigned __int64 v82; // [rsp+C0h] [rbp-21h]
  PCWSTR pszPath[2]; // [rsp+C8h] [rbp-19h] BYREF
  unsigned __int64 v84; // [rsp+D8h] [rbp-9h]
  unsigned __int64 v85; // [rsp+E0h] [rbp-1h]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+57h]

  v69 = 0;
  ((void (__fastcall *)(struct IFileDialog *, unsigned int *))a2->lpVtbl->GetOptions)(a2, &v69);
  v7 = v69 | 0x20180;
  v69 |= 0x20180u;
  if ( *(_DWORD *)this == 1 )
  {
    v8 = v7 | 0x20;
  }
  else
  {
    if ( *(_DWORD *)this != 2 )
      goto LABEL_6;
    v8 = v7 & 0xFFFECFFD | 0x10000;
  }
  v69 = v8;
LABEL_6:
  v9 = ((__int64 (__fastcall *)(struct IFileDialog *))a2->lpVtbl->SetOptions)(a2);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2F1,
      (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\remotefilebrowseclient.cpp",
      (const char *)(unsigned int)v9,
      ppv);
  if ( *((_QWORD *)this + 23) )
  {
    v10 = ((__int64 (__fastcall *)(struct IFileDialog *))a2->lpVtbl->SetTitle)(a2);
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2F5,
        (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\remotefilebrowseclient.cpp",
        (const char *)(unsigned int)v10,
        ppv);
  }
  if ( *((_QWORD *)this + 27) )
  {
    v11 = ((__int64 (__fastcall *)(struct IFileDialog *))a2->lpVtbl->SetOkButtonLabel)(a2);
    if ( v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2FA,
        (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\remotefilebrowseclient.cpp",
        (const char *)(unsigned int)v11,
        ppv);
  }
  std::wstring::wstring(pszPath, &RemoteFileBrowseClient::rfbRoot);
  *(_OWORD *)SRWLock = 0;
  v68 = 0;
  v76[0] = &v68;
  v76[1] = SRWLock;
  v76[2] = this;
  v77 = 257;
  if ( !*((_BYTE *)this + 4) )
  {
    ServerRegistrar = GetServerRegistrar(v78);
    v13 = *(RTL_SRWLOCK **)ServerRegistrar;
    v14 = *(RTL_SRWLOCK **)(ServerRegistrar + 8);
    *(_QWORD *)ServerRegistrar = 0;
    *(_QWORD *)(ServerRegistrar + 8) = 0;
    SRWLock[0] = v13;
    v15 = (volatile signed __int32 *)SRWLock[1];
    SRWLock[1] = v14;
    if ( v15 )
    {
      if ( _InterlockedExchangeAdd(v15 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
        if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
      }
    }
    v16 = v79;
    if ( v79 )
    {
      if ( _InterlockedExchangeAdd(v79 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v16)(v16);
        if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
      }
    }
    RfbServerRegistrar::RegisterServer(SRWLock[0], (__int64)a5);
    v68 = 1;
    Src[0] = 0;
    v17 = v84;
    v18 = pszPath;
    if ( v84 >= v85 )
    {
      std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(pszPath);
    }
    else
    {
      ++v84;
      if ( v85 > 7 )
        v18 = (PCWSTR *)pszPath[0];
      *(_DWORD *)((char *)v18 + 2 * v17) = 92;
    }
    std::wstring::append(pszPath);
    v19 = (void **)IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IShellItem>>(Src);
    v20 = (const WCHAR *)pszPath;
    if ( v85 > 7 )
      v20 = pszPath[0];
    v21 = SHCreateItemFromParsingName(v20, 0, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, v19);
    if ( v21 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x31B,
        (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\remotefilebrowseclient.cpp",
        (const char *)(unsigned int)v21,
        ppva);
    v70 = 0;
    v22 = ((__int64 (__fastcall *)(struct IFileDialog *, GUID *, _QWORD **))a2->lpVtbl->QueryInterface)(
            a2,
            &GUID_61744fc7_85b5_4791_a9b0_272276309b13,
            &v70);
    if ( v22 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x31F,
        (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\remotefilebrowseclient.cpp",
        (const char *)(unsigned int)v22,
        ppva);
    v23 = (*(__int64 (__fastcall **)(_QWORD *, void *))(*v70 + 224LL))(v70, Src[0]);
    if ( v23 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x320,
        (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\remotefilebrowseclient.cpp",
        (const char *)(unsigned int)v23,
        ppva);
    v24 = v70;
    if ( v70 )
    {
      v70 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v24 + 16LL))(v24);
    }
    v25 = Src[0];
    if ( Src[0] )
    {
      Src[0] = 0;
      (*(void (__fastcall **)(void *))(*(_QWORD *)v25 + 16LL))(v25);
    }
  }
  v74 = 0;
  v26 = (void **)IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IShellItem>>(&v74);
  v27 = SHCreateItemInKnownFolder(&FOLDERID_NetworkFolder, 0, 0, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, v26);
  if ( v27 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x329,
      (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\remotefilebrowseclient.cpp",
      (const char *)(unsigned int)v27,
      ppvb);
  v28 = ((__int64 (__fastcall *)(struct IFileDialog *, __int64, __int64))a2->lpVtbl->AddPlace)(a2, v74, 1);
  if ( v28 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x32B,
      (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\remotefilebrowseclient.cpp",
      (const char *)(unsigned int)v28,
      ppvb);
  *(_OWORD *)v80 = 0;
  v81 = 0;
  v82 = 7;
  LOWORD(v80[0]) = 0;
  if ( !*((_BYTE *)this + 4) )
  {
    v29 = (const wchar_t *)((char *)this + 40);
    if ( *((_QWORD *)this + 8) > 7u )
      v29 = *(const wchar_t **)v29;
    if ( wcsncmp_0(v29, L"\\\\", 2u) )
    {
      std::wstring::append(v80);
      v30 = v81;
      v31 = v80;
      if ( v81 >= v82 )
      {
        std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(v80);
      }
      else
      {
        ++v81;
        if ( v82 > 7 )
          v31 = (PCWSTR *)v80[0];
        *(_DWORD *)((char *)v31 + 2 * v30) = 92;
      }
    }
  }
  v72 = 0;
  std::wstring::append(v80);
  if ( !v81 )
    goto LABEL_126;
  v32 = (void **)IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IShellItem>>(&v72);
  v33 = (const WCHAR *)v80;
  if ( v82 > 7 )
    v33 = v80[0];
  if ( SHCreateItemFromParsingName(v33, 0, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, v32) < 0 )
  {
LABEL_126:
    if ( *((_BYTE *)this + 4) )
    {
      v34 = (void **)IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IShellItem>>(&v72);
      SHCreateItemInKnownFolder(&FOLDERID_ComputerFolder, 0, 0, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, v34);
    }
    else
    {
      v35 = (void **)IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IShellItem>>(&v72);
      v36 = (const WCHAR *)pszPath;
      if ( v85 > 7 )
        v36 = pszPath[0];
      SHCreateItemFromParsingName(v36, 0, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, v35);
    }
  }
  if ( v72 )
  {
    v37 = ((__int64 (__fastcall *)(struct IFileDialog *))a2->lpVtbl->SetFolder)(a2);
    if ( v37 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x35A,
        (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\remotefilebrowseclient.cpp",
        (const char *)(unsigned int)v37,
        ppvb);
  }
  if ( *((_QWORD *)this + 11) )
  {
    v38 = (_QWORD *)((char *)this + 104);
    if ( *((_QWORD *)this + 16) > 7u )
      v38 = (_QWORD *)*v38;
    Src[0] = v38;
    v39 = (_QWORD *)((char *)this + 72);
    if ( *((_QWORD *)this + 12) > 7u )
      v39 = (_QWORD *)*v39;
    Src[1] = v39;
    v40 = ((__int64 (__fastcall *)(struct IFileDialog *, __int64, void **))a2->lpVtbl->SetFileTypes)(a2, 1, Src);
    if ( v40 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x367,
        (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\remotefilebrowseclient.cpp",
        (const char *)(unsigned int)v40,
        ppvb);
  }
  if ( *(_DWORD *)this == 2 )
  {
    if ( *((_QWORD *)this + 11) )
    {
      v41 = ((__int64 (__fastcall *)(struct IFileDialog *))a2->lpVtbl->SetDefaultExtension)(a2);
      if ( v41 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x36F,
          (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\remotefilebrowseclient.cpp",
          (const char *)(unsigned int)v41,
          ppvb);
    }
  }
  v73 = 0;
  if ( !*((_BYTE *)this + 4) )
  {
    v70 = 0;
    v42 = operator new(0x10u, (const struct std::nothrow_t *)std::nothrow);
    v43 = v42;
    if ( v42 )
    {
      *(_OWORD *)v42 = 0;
      *((_DWORD *)v42 + 3) = 1;
      *v42 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IFileDialogEvents>::`vftable';
      if ( Microsoft::WRL::Details::ModuleBase::module_ )
        (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                             + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
      *v43 = &RfbFileDialogEvents::`vftable';
      v70 = v43;
    }
    else
    {
      v43 = 0;
    }
    Src[0] = 0;
    Interface = Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IFileDialogEvents>::QueryInterface(
                  v43,
                  &GUID_973510db_7d7f_452b_8975_74a85828d354,
                  Src);
    if ( Interface < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x37C,
        (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\remotefilebrowseclient.cpp",
        (const char *)(unsigned int)Interface,
        ppvb);
    v45 = ((__int64 (__fastcall *)(struct IFileDialog *, void *, int *))a2->lpVtbl->Advise)(a2, Src[0], &v73);
    if ( v45 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x37D,
        (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\remotefilebrowseclient.cpp",
        (const char *)(unsigned int)v45,
        ppvb);
    v46 = Src[0];
    if ( Src[0] )
    {
      Src[0] = 0;
      (*(void (__fastcall **)(void *))(*(_QWORD *)v46 + 16LL))(v46);
    }
    if ( v43 )
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IFileDialogEvents>::Release(v43);
  }
  v47 = ((__int64 (__fastcall *)(struct IFileDialog *, _QWORD))a2->lpVtbl->Show)(a2, *((_QWORD *)this + 29));
  if ( v47 == -2147023673 )
  {
    v58 = (_QWORD *)((char *)this + 136);
    *((_QWORD *)this + 19) = 0;
    if ( *((_QWORD *)this + 20) > 7u )
      v58 = (_QWORD *)*v58;
    *(_WORD *)v58 = 0;
  }
  else
  {
    if ( v47 )
    {
      v64 = wil::verify_hresult<long>(v47);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x394,
        (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\remotefilebrowseclient.cpp",
        (const char *)v64,
        ppvb);
    }
    v70 = 0;
    v48 = ((__int64 (__fastcall *)(struct IFileDialog *, _QWORD **))a2->lpVtbl->GetResult)(a2, &v70);
    if ( v48 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x387,
        (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\remotefilebrowseclient.cpp",
        (const char *)(unsigned int)v48,
        ppvb);
    Src[0] = 0;
    v49 = *v70;
    Src[0] = 0;
    v50 = (*(__int64 (__fastcall **)(_QWORD *, __int64, void **))(v49 + 40))(v70, 2147647488LL, Src);
    if ( v50 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x38A,
        (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\remotefilebrowseclient.cpp",
        (const char *)(unsigned int)v50,
        ppvb);
    v52 = Src[0];
    v53 = (char **)((char *)this + 136);
    v54 = -1;
    do
      ++v54;
    while ( *((_WORD *)Src[0] + v54) );
    if ( v54 > *((_QWORD *)this + 20) )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        v53,
        v54,
        v51,
        Src[0]);
    }
    else
    {
      if ( *((_QWORD *)this + 20) <= 7u )
        v55 = (char *)this + 136;
      else
        v55 = *v53;
      *((_QWORD *)this + 19) = v54;
      v56 = 2 * v54;
      memmove_0(v55, v52, 2 * v54);
      *(_WORD *)&v55[v56] = 0;
    }
    if ( Src[0] )
      CoTaskMemFree(Src[0]);
    v57 = v70;
    if ( v70 )
    {
      v70 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v57 + 16LL))(v57);
    }
  }
  if ( v73 )
    ((void (__fastcall *)(struct IFileDialog *))a2->lpVtbl->Unadvise)(a2);
  v59 = *((_QWORD *)this + 19) != 0;
  v60 = v72;
  if ( v72 )
  {
    v72 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
  }
  std::wstring::~wstring(v80);
  v61 = v74;
  if ( v74 )
  {
    v74 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
  }
  wil::details::ScopeExitFnGuard__lambda_8109012ef33c7ad204f13e59c49309d8___::operator()(v76);
  v62 = (volatile signed __int32 *)SRWLock[1];
  if ( SRWLock[1] )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)&SRWLock[1][1], 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v62)(v62);
      if ( _InterlockedExchangeAdd(v62 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v62 + 8LL))(v62);
    }
  }
  std::wstring::~wstring(pszPath);
  return v59;
}

```

## disassembly

```asm
0x18000ba9c  push    rbp
0x18000ba9e  push    rbx
0x18000ba9f  push    rsi
0x18000baa0  push    rdi
0x18000baa1  push    r12
0x18000baa3  push    r13
0x18000baa5  push    r14
0x18000baa7  push    r15
0x18000baa9  lea     rbp, [rsp-17h]
0x18000baae  sub     rsp, 0F8h
0x18000bab5  mov     rax, cs:__security_cookie
0x18000babc  xor     rax, rsp
0x18000babf  mov     [rbp+4Fh+var_48], rax
0x18000bac3  mov     r15, r9
0x18000bac6  mov     r14, r8
0x18000bac9  mov     rsi, rdx
0x18000bacc  mov     rdi, rcx
0x18000bacf  mov     r12, [rbp+4Fh+arg_20]
0x18000bad3  xor     r13d, r13d
0x18000bad6  mov     [rsp+130h+var_FC], r13d
0x18000badb  mov     rax, [rdx]
0x18000bade  lea     rdx, [rsp+130h+var_FC]
0x18000bae3  mov     rcx, rsi
0x18000bae6  mov     rax, [rax+50h]
0x18000baea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000baef  mov     edx, [rsp+130h+var_FC]
0x18000baf3  or      edx, 20180h
0x18000baf9  mov     [rsp+130h+var_FC], edx
0x18000bafd  cmp     dword ptr [rdi], 1
0x18000bb00  jnz     short loc_18000BB07
0x18000bb02  or      edx, 20h
0x18000bb05  jmp     short loc_18000BB16
0x18000bb07  cmp     dword ptr [rdi], 2
0x18000bb0a  jnz     short loc_18000BB1A
0x18000bb0c  and     edx, 0FFFFCFFDh
0x18000bb12  bts     edx, 10h
0x18000bb16  mov     [rsp+130h+var_FC], edx
0x18000bb1a  mov     rax, [rsi]
0x18000bb1d  mov     rcx, rsi
0x18000bb20  mov     rax, [rax+48h]
0x18000bb24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb29  mov     rcx, [rbp+57h]; this
0x18000bb2d  test    eax, eax
0x18000bb2f  js      loc_18000C2C9
0x18000bb35  cmp     [rdi+0B8h], r13
0x18000bb3c  jz      short loc_18000BB6D
0x18000bb3e  mov     rax, [rsi]
0x18000bb41  lea     rdx, [rdi+0A8h]
0x18000bb48  cmp     qword ptr [rdx+18h], 7
0x18000bb4d  jbe     short loc_18000BB52
0x18000bb4f  mov     rdx, [rdx]
0x18000bb52  mov     rcx, rsi
0x18000bb55  mov     rax, [rax+88h]
0x18000bb5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb61  mov     rcx, [rbp+57h]; this
0x18000bb65  test    eax, eax
0x18000bb67  js      loc_18000C2DE
0x18000bb6d  cmp     [rdi+0D8h], r13
0x18000bb74  jz      short loc_18000BBA5
0x18000bb76  mov     rax, [rsi]
0x18000bb79  lea     rdx, [rdi+0C8h]
0x18000bb80  cmp     qword ptr [rdx+18h], 7
0x18000bb85  jbe     short loc_18000BB8A
0x18000bb87  mov     rdx, [rdx]
0x18000bb8a  mov     rcx, rsi
0x18000bb8d  mov     rax, [rax+90h]
0x18000bb94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb99  mov     rcx, [rbp+57h]; this
0x18000bb9d  test    eax, eax
0x18000bb9f  js      loc_18000C2F3
0x18000bba5  lea     rdx, ?rfbRoot@RemoteFileBrowseClient@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const RemoteFileBrowseClient::rfbRoot
0x18000bbac  lea     rcx, [rbp+4Fh+pszPath]
0x18000bbb0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000bbb5  nop
0x18000bbb6  xorps   xmm0, xmm0
0x18000bbb9  movdqu  xmmword ptr [rbp+4Fh+SRWLock], xmm0
0x18000bbbe  mov     [rsp+130h+var_100], r13b
0x18000bbc3  lea     rax, [rsp+130h+var_100]
0x18000bbc8  mov     [rbp+4Fh+var_B8], rax
0x18000bbcc  lea     rax, [rbp+4Fh+SRWLock]
0x18000bbd0  mov     [rbp+4Fh+var_B0], rax
0x18000bbd4  mov     [rbp+4Fh+var_A8], rdi
0x18000bbd8  mov     [rbp+4Fh+var_A0], 101h
0x18000bbde  mov     ebx, 5Ch ; '\'
0x18000bbe3  cmp     [rdi+4], r13b
0x18000bbe7  jnz     loc_18000BDB7
0x18000bbed  lea     rcx, [rbp+4Fh+var_98]
0x18000bbf1  call    ?GetServerRegistrar@@YA?AV?$shared_ptr@VRfbServerRegistrar@@@std@@XZ; GetServerRegistrar(void)
0x18000bbf6  mov     rcx, [rax]
0x18000bbf9  mov     rdx, [rax+8]
0x18000bbfd  mov     [rax], r13
0x18000bc00  mov     [rax+8], r13
0x18000bc04  mov     [rbp+4Fh+SRWLock], rcx
0x18000bc08  mov     rbx, [rbp+4Fh+SRWLock+8]
0x18000bc0c  mov     [rbp+4Fh+SRWLock+8], rdx
0x18000bc10  test    rbx, rbx
0x18000bc13  jz      short loc_18000BC4C
0x18000bc15  or      eax, 0FFFFFFFFh
0x18000bc18  lock xadd [rbx+8], eax
0x18000bc1d  cmp     eax, 1
0x18000bc20  jnz     short loc_18000BC4C
0x18000bc22  mov     rax, [rbx]
0x18000bc25  mov     rcx, rbx
0x18000bc28  mov     rax, [rax]
0x18000bc2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc30  or      eax, 0FFFFFFFFh
0x18000bc33  lock xadd [rbx+0Ch], eax
0x18000bc38  cmp     eax, 1
0x18000bc3b  jnz     short loc_18000BC4C
0x18000bc3d  mov     rax, [rbx]
0x18000bc40  mov     rcx, rbx
0x18000bc43  mov     rax, [rax+8]
0x18000bc47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc4c  mov     rbx, [rbp+4Fh+var_90]
0x18000bc50  test    rbx, rbx
0x18000bc53  jz      short loc_18000BC8C
0x18000bc55  or      eax, 0FFFFFFFFh
0x18000bc58  lock xadd [rbx+8], eax
0x18000bc5d  cmp     eax, 1
0x18000bc60  jnz     short loc_18000BC8C
0x18000bc62  mov     rax, [rbx]
0x18000bc65  mov     rcx, rbx
0x18000bc68  mov     rax, [rax]
0x18000bc6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc70  or      eax, 0FFFFFFFFh
0x18000bc73  lock xadd [rbx+0Ch], eax
0x18000bc78  cmp     eax, 1
0x18000bc7b  jnz     short loc_18000BC8C
0x18000bc7d  mov     rax, [rbx]
0x18000bc80  mov     rcx, rbx
0x18000bc83  mov     rax, [rax+8]
0x18000bc87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc8c  mov     qword ptr [rsp+130h+ppv], r12; int
0x18000bc91  mov     r9, r15
0x18000bc94  mov     r8, r14
0x18000bc97  lea     rdx, [rdi+8]
0x18000bc9b  mov     rcx, [rbp+4Fh+SRWLock]; SRWLock
0x18000bc9f  call    ?RegisterServer@RfbServerRegistrar@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG11@Z; RfbServerRegistrar::RegisterServer(std::wstring const &,ushort const *,ushort const *,ushort const *)
0x18000bca4  mov     [rsp+130h+var_100], 1
0x18000bca9  mov     [rsp+130h+Src], r13
0x18000bcae  mov     rdx, [rbp+4Fh+var_58]
0x18000bcb2  lea     rcx, [rbp+4Fh+pszPath]; Src
0x18000bcb6  cmp     rdx, [rbp+4Fh+var_50]
0x18000bcba  jnb     short loc_18000BCD7
0x18000bcbc  lea     rax, [rdx+1]
0x18000bcc0  mov     [rbp+4Fh+var_58], rax
0x18000bcc4  cmp     [rbp+4Fh+var_50], 7
0x18000bcc9  cmova   rcx, [rbp+4Fh+pszPath]
0x18000bcce  mov     dword ptr [rcx+rdx*2], 5Ch ; '\'
0x18000bcd5  jmp     short loc_18000BCE2
0x18000bcd7  mov     r9d, 5Ch ; '\'
0x18000bcdd  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x18000bce2  lea     rdx, [rdi+8]
0x18000bce6  lea     rcx, [rbp+4Fh+pszPath]; Src
0x18000bcea  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18000bcef  lea     rcx, [rsp+130h+Src]
0x18000bcf4  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIShellItem@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIShellItem@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IShellItem>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IShellItem>>)
0x18000bcf9  lea     rcx, [rbp+4Fh+pszPath]
0x18000bcfd  cmp     [rbp+4Fh+var_50], 7
0x18000bd02  cmova   rcx, [rbp+4Fh+pszPath]; pszPath
0x18000bd07  mov     r9, rax; ppv
0x18000bd0a  lea     r14, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe
0x18000bd11  mov     r8, r14; riid
0x18000bd14  xor     edx, edx; pbc
0x18000bd16  call    cs:__imp_SHCreateItemFromParsingName
0x18000bd1c  mov     rcx, [rbp+57h]; this
0x18000bd20  test    eax, eax
0x18000bd22  js      loc_18000C308
0x18000bd28  mov     [rsp+130h+var_F8], r13
0x18000bd2d  mov     rax, [rsi]
0x18000bd30  lea     r8, [rsp+130h+var_F8]
0x18000bd35  lea     rdx, _GUID_61744fc7_85b5_4791_a9b0_272276309b13
0x18000bd3c  mov     rcx, rsi
0x18000bd3f  mov     rax, [rax]
0x18000bd42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd47  mov     rcx, [rbp+57h]; this
0x18000bd4b  test    eax, eax
0x18000bd4d  js      loc_18000C31D
0x18000bd53  mov     rcx, [rsp+130h+var_F8]
0x18000bd58  mov     rax, [rcx]
0x18000bd5b  mov     rdx, [rsp+130h+Src]
0x18000bd60  mov     rax, [rax+0E0h]
0x18000bd67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd6c  mov     rcx, [rbp+57h]; this
0x18000bd70  test    eax, eax
0x18000bd72  js      loc_18000C332
0x18000bd78  mov     rcx, [rsp+130h+var_F8]
0x18000bd7d  test    rcx, rcx
0x18000bd80  jz      short loc_18000BD94
0x18000bd82  mov     [rsp+130h+var_F8], r13
0x18000bd87  mov     rax, [rcx]
0x18000bd8a  mov     rax, [rax+10h]
0x18000bd8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd93  nop
0x18000bd94  mov     rcx, [rsp+130h+Src]
0x18000bd99  test    rcx, rcx
0x18000bd9c  jz      short loc_18000BDB0
0x18000bd9e  mov     [rsp+130h+Src], r13
0x18000bda3  mov     rax, [rcx]
0x18000bda6  mov     rax, [rax+10h]
0x18000bdaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bdaf  nop
0x18000bdb0  mov     ebx, 5Ch ; '\'
0x18000bdb5  jmp     short loc_18000BDBE
0x18000bdb7  lea     r14, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe
0x18000bdbe  mov     [rsp+130h+var_D0], r13
0x18000bdc3  lea     rcx, [rsp+130h+var_D0]
0x18000bdc8  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIShellItem@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIShellItem@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IShellItem>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IShellItem>>)
0x18000bdcd  mov     qword ptr [rsp+130h+ppv], rax; int
0x18000bdd2  mov     r9, r14; riid
0x18000bdd5  xor     r8d, r8d; pszItem
0x18000bdd8  xor     edx, edx; dwKFFlags
0x18000bdda  lea     rcx, FOLDERID_NetworkFolder; kfid
0x18000bde1  call    cs:__imp_SHCreateItemInKnownFolder
0x18000bde7  mov     rcx, [rbp+57h]; this
0x18000bdeb  test    eax, eax
0x18000bded  js      loc_18000C347
0x18000bdf3  mov     rax, [rsi]
0x18000bdf6  mov     r8d, 1
0x18000bdfc  mov     rdx, [rsp+130h+var_D0]
0x18000be01  mov     rcx, rsi
0x18000be04  mov     rax, [rax+0A8h]
0x18000be0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be10  mov     rcx, [rbp+57h]; this
0x18000be14  test    eax, eax
0x18000be16  js      loc_18000C35C
0x18000be1c  xorps   xmm0, xmm0
0x18000be1f  movups  xmmword ptr [rbp+4Fh+var_88], xmm0
0x18000be23  mov     [rbp+4Fh+var_78], r13
0x18000be27  mov     [rbp+4Fh+var_70], 7
0x18000be2f  mov     word ptr [rbp+4Fh+var_88], r13w
0x18000be34  cmp     [rdi+4], r13b
0x18000be38  jnz     short loc_18000BE9C
0x18000be3a  lea     rcx, [rdi+28h]
0x18000be3e  cmp     qword ptr [rcx+18h], 7
0x18000be43  jbe     short loc_18000BE48
0x18000be45  mov     rcx, [rcx]; String1
0x18000be48  mov     r8d, 2; MaxCount
0x18000be4e  lea     rdx, String2; "\\\\"
0x18000be55  call    wcsncmp_0
0x18000be5a  test    eax, eax
0x18000be5c  jz      short loc_18000BE9C
0x18000be5e  lea     rdx, [rbp+4Fh+pszPath]
0x18000be62  lea     rcx, [rbp+4Fh+var_88]; Src
0x18000be66  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18000be6b  mov     rdx, [rbp+4Fh+var_78]
0x18000be6f  lea     rcx, [rbp+4Fh+var_88]; Src
0x18000be73  cmp     rdx, [rbp+4Fh+var_70]
0x18000be77  jnb     short loc_18000BE94
0x18000be79  lea     rax, [rdx+1]
0x18000be7d  mov     [rbp+4Fh+var_78], rax
0x18000be81  cmp     [rbp+4Fh+var_70], 7
0x18000be86  cmova   rcx, [rbp+4Fh+var_88]
0x18000be8b  mov     dword ptr [rcx+rdx*2], 5Ch ; '\'
0x18000be92  jmp     short loc_18000BE9C
0x18000be94  mov     r9d, ebx
0x18000be97  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x18000be9c  mov     [rsp+130h+var_E0], r13
0x18000bea1  lea     rdx, [rdi+28h]
0x18000bea5  lea     rcx, [rbp+4Fh+var_88]; Src
0x18000bea9  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18000beae  cmp     [rbp+4Fh+var_78], r13
0x18000beb2  jz      short loc_18000BEDE
0x18000beb4  lea     rcx, [rsp+130h+var_E0]
0x18000beb9  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIShellItem@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIShellItem@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IShellItem>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IShellItem>>)
0x18000bebe  lea     rcx, [rbp+4Fh+var_88]
0x18000bec2  cmp     [rbp+4Fh+var_70], 7
0x18000bec7  cmova   rcx, [rbp+4Fh+var_88]; pszPath
0x18000becc  mov     r9, rax; ppv
0x18000becf  mov     r8, r14; riid
0x18000bed2  xor     edx, edx; pbc
0x18000bed4  call    cs:__imp_SHCreateItemFromParsingName
0x18000beda  test    eax, eax
0x18000bedc  jns     short loc_18000BF2B
0x18000bede  lea     rcx, [rsp+130h+var_E0]
0x18000bee3  cmp     [rdi+4], r13b
0x18000bee7  jz      short loc_18000BF0A
0x18000bee9  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIShellItem@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIShellItem@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IShellItem>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IShellItem>>)
0x18000beee  mov     qword ptr [rsp+130h+ppv], rax; ppv
0x18000bef3  mov     r9, r14; riid
0x18000bef6  xor     r8d, r8d; pszItem
0x18000bef9  xor     edx, edx; dwKFFlags
0x18000befb  lea     rcx, FOLDERID_ComputerFolder; kfid
0x18000bf02  call    cs:__imp_SHCreateItemInKnownFolder
0x18000bf08  jmp     short loc_18000BF2B
0x18000bf0a  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIShellItem@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIShellItem@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IShellItem>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IShellItem>>)
0x18000bf0f  lea     rcx, [rbp+4Fh+pszPath]
0x18000bf13  cmp     [rbp+4Fh+var_50], 7
0x18000bf18  cmova   rcx, [rbp+4Fh+pszPath]; pszPath
0x18000bf1d  mov     r9, rax; ppv
0x18000bf20  mov     r8, r14; riid
0x18000bf23  xor     edx, edx; pbc
0x18000bf25  call    cs:__imp_SHCreateItemFromParsingName
0x18000bf2b  mov     rdx, [rsp+130h+var_E0]
0x18000bf30  test    rdx, rdx
0x18000bf33  jz      short loc_18000BF50
0x18000bf35  mov     rax, [rsi]
0x18000bf38  mov     rcx, rsi
0x18000bf3b  mov     rax, [rax+60h]
0x18000bf3f  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
