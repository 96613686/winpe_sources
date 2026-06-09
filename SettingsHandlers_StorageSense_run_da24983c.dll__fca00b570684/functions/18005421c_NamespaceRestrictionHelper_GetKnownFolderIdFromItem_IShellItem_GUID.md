# NamespaceRestrictionHelper::GetKnownFolderIdFromItem(IShellItem *,_GUID *)

- ea: `0x18005421c`
- end: `0x180054583`
- name: `?GetKnownFolderIdFromItem@NamespaceRestrictionHelper@@AEAAJPEAUIShellItem@@PEAU_GUID@@@Z`
- size: `871`
- prototype: `int(NamespaceRestrictionHelper *__hidden this, struct IShellItem *, struct _GUID *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800586f4`

## callees

- `0x18000e6cc`
- `0x180018244`
- `0x18004f990`
- `0x180050d34`
- `0x18005292c`
- `0x18005421c`
- `0x180057018`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800542c3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005448c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054501`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005452d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054543`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054564`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800542c3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005448c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054501`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005452d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054543`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054564`
- `api-ms-win-shell-namespace-l1-1-0!ILIsEqual` at `0x1800544e8`
- `api-ms-win-shell-namespace-l1-1-0!ILIsEqual` at `0x1800544e8`
- `api-ms-win-shell-namespace-l1-1-0!SHGetIDListFromObject` at `0x1800542e9`
- `api-ms-win-shell-namespace-l1-1-0!SHGetIDListFromObject` at `0x1800542e9`
- `api-ms-win-storage-exports-internal-l1-1-0!SHGetKnownFolderIDList` at `0x1800544c8`
- `api-ms-win-storage-exports-internal-l1-1-0!SHGetKnownFolderIDList` at `0x1800544c8`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall NamespaceRestrictionHelper::GetKnownFolderIdFromItem(
        NamespaceRestrictionHelper *this,
        struct IShellItem *a2,
        struct _GUID *a3)
{
  int v5; // eax
  struct IBindCtx *v6; // rdx
  const struct _GUID *v7; // r8
  HRESULT UnaliasedItem; // ebx
  __int64 v10; // rdx
  void *v11; // rcx
  enum FOLDER_ENUM_MODE v12; // ecx
  ITEMIDLIST *v13; // rcx
  const KNOWNFOLDERID *const *v14; // rdi
  struct _GUID *v15; // rsi
  HRESULT v16; // ebx
  ITEMIDLIST *v17; // rcx
  ITEMIDLIST *v18; // rcx
  ITEMIDLIST *v19; // rcx
  bool v20; // zf
  void *v21; // rcx
  LPVOID pv; // [rsp+20h] [rbp-E0h] BYREF
  LPCITEMIDLIST pidl1; // [rsp+28h] [rbp-D8h] BYREF
  IUnknown *punk; // [rsp+30h] [rbp-D0h] BYREF
  LPCITEMIDLIST pidl2; // [rsp+38h] [rbp-C8h] BYREF
  void *p_pv; // [rsp+40h] [rbp-C0h] BYREF
  LPITEMIDLIST ppidl; // [rsp+48h] [rbp-B8h] BYREF
  char v28; // [rsp+50h] [rbp-B0h]
  _QWORD v29[26]; // [rsp+60h] [rbp-A0h] BYREF
  char v30; // [rsp+130h] [rbp+30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  *a3 = GUID_NULL;
  v5 = NamespaceRestrictionHelper::EnsureManager(this);
  UnaliasedItem = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x20B,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\NamespaceRestrictionHelper.h",
      (const char *)(unsigned int)v5,
      (int)pv);
    return (unsigned int)UnaliasedItem;
  }
  pv = 0;
  punk = 0;
  UnaliasedItem = GetUnaliasedItem(a2, v6, v7, (void **)&punk);
  if ( UnaliasedItem < 0 )
  {
    v10 = 529;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\NamespaceRestrictionHelper.h",
      (const char *)(unsigned int)UnaliasedItem,
      (int)pv);
LABEL_7:
    wil::com_ptr_t<Windows::Internal::StateRepository::IApplicationStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::StateRepository::IApplicationStatics,wil::err_exception_policy>(&punk);
    v11 = pv;
    pv = 0;
    if ( v11 )
      CoTaskMemFree(v11);
    return (unsigned int)UnaliasedItem;
  }
  p_pv = &pv;
  ppidl = 0;
  v28 = 1;
  UnaliasedItem = SHGetIDListFromObject(punk, &ppidl);
  wil::details::out_param_t<wistd::unique_ptr<_ITEMIDLIST,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMIDLIST,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
  if ( UnaliasedItem < 0 )
  {
    v10 = 530;
    goto LABEL_6;
  }
  v29[0] = &FOLDERID_Downloads;
  v29[1] = &FOLDERID_Desktop;
  v29[2] = &unk_18010C3E8;
  v29[3] = &FOLDERID_Documents;
  v29[4] = &FOLDERID_Pictures;
  v29[5] = &FOLDERID_SavedPictures;
  v29[6] = &FOLDERID_CameraRoll;
  v29[7] = &FOLDERID_NetworkFolder;
  v29[8] = &FOLDERID_Windows;
  v29[9] = &FOLDERID_ComputerFolder;
  v29[10] = &FOLDERID_RecycleBinFolder;
  v29[11] = &FOLDERID_SearchHistory;
  v29[12] = &FOLDERID_SearchHome;
  v29[13] = &FOLDERID_PrintersFolder;
  v29[14] = &FOLDERID_Music;
  v29[15] = &FOLDERID_Videos;
  v29[16] = &FOLDERID_Device;
  v29[17] = &FOLDERID_RecordedCalls;
  v29[18] = &FOLDERID_Objects3D;
  v29[19] = &FOLDERID_OneDrive;
  v29[20] = &FOLDERID_Public;
  v29[21] = &FOLDERID_Profile;
  v29[22] = &FOLDERID_UsersLibraries;
  v29[23] = &FOLDERID_LocalAppData;
  v29[24] = &FOLDERID_AppsFolder;
  v29[25] = &FOLDERID_RoamingAppData;
  pidl1 = 0;
  p_pv = &pidl1;
  ppidl = 0;
  v28 = 1;
  UnaliasedItem = ConvertIDListEnumMode(v12, (const struct _ITEMIDLIST *)pv, &ppidl);
  wil::details::out_param_t<wistd::unique_ptr<_ITEMIDLIST,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMIDLIST,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
  if ( UnaliasedItem < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x236,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\NamespaceRestrictionHelper.h",
      (const char *)(unsigned int)UnaliasedItem,
      (int)pv);
    v13 = (ITEMIDLIST *)pidl1;
    pidl1 = 0;
    if ( v13 )
      CoTaskMemFree(v13);
    goto LABEL_7;
  }
  v14 = (const KNOWNFOLDERID *const *)v29;
  while ( 1 )
  {
    pidl2 = 0;
    p_pv = &pidl2;
    ppidl = 0;
    v28 = 1;
    v15 = (struct _GUID *)*v14;
    v16 = SHGetKnownFolderIDList(*v14, 0x5000u, 0, &ppidl);
    wil::details::out_param_t<wistd::unique_ptr<_ITEMIDLIST,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMIDLIST,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
    if ( v16 >= 0 )
    {
      if ( ILIsEqual(pidl1, pidl2) )
        break;
    }
    v17 = (ITEMIDLIST *)pidl2;
    pidl2 = 0;
    if ( v17 )
      CoTaskMemFree(v17);
    if ( ++v14 == (const KNOWNFOLDERID *const *)&v30 )
      goto LABEL_23;
  }
  *a3 = *v15;
  v18 = (ITEMIDLIST *)pidl2;
  pidl2 = 0;
  if ( v18 )
    CoTaskMemFree(v18);
LABEL_23:
  v19 = (ITEMIDLIST *)pidl1;
  v20 = pidl1 == 0;
  pidl1 = 0;
  if ( !v20 )
    CoTaskMemFree(v19);
  wil::com_ptr_t<Windows::Internal::StateRepository::IApplicationStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::StateRepository::IApplicationStatics,wil::err_exception_policy>(&punk);
  v21 = pv;
  v20 = pv == 0;
  pv = 0;
  if ( !v20 )
    CoTaskMemFree(v21);
  return 0;
}

```

## disassembly

```asm
0x18005421c  mov     [rsp-8+arg_18], rbx
0x180054221  push    rbp
0x180054222  push    rsi
0x180054223  push    rdi
0x180054224  push    r14
0x180054226  push    r15
0x180054228  lea     rbp, [rsp-30h]
0x18005422d  sub     rsp, 130h
0x180054234  mov     r14, r8
0x180054237  mov     rdi, rdx
0x18005423a  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180054241  movdqu  xmmword ptr [r8], xmm0
0x180054246  call    ?EnsureManager@NamespaceRestrictionHelper@@AEAAJXZ; NamespaceRestrictionHelper::EnsureManager(void)
0x18005424b  mov     ebx, eax
0x18005424d  xor     r15d, r15d
0x180054250  test    eax, eax
0x180054252  jns     short loc_180054273
0x180054254  mov     rcx, [rbp+58h]; this
0x180054258  mov     r9d, eax; char *
0x18005425b  lea     r8, aOnecoreuapInte_6; "onecoreuap\\internal\\shell\\inc\\priva"...
0x180054262  mov     edx, 20Bh; void *
0x180054267  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005426c  mov     eax, ebx
0x18005426e  jmp     loc_18005456C
0x180054273  mov     [rsp+150h+pv], r15; int
0x180054278  mov     [rsp+150h+punk], r15
0x18005427d  lea     r9, [rsp+150h+punk]; void **
0x180054282  mov     rcx, rdi; struct IShellItem *
0x180054285  call    ?GetUnaliasedItem@@YAJPEAUIShellItem@@PEAUIBindCtx@@AEBU_GUID@@PEAPEAX@Z; GetUnaliasedItem(IShellItem *,IBindCtx *,_GUID const &,void * *)
0x18005428a  mov     ebx, eax
0x18005428c  test    eax, eax
0x18005428e  jns     short loc_1800542CB
0x180054290  mov     edx, 211h; void *
0x180054295  lea     r8, aOnecoreuapInte_6; "onecoreuap\\internal\\shell\\inc\\priva"...
0x18005429c  mov     r9d, ebx; char *
0x18005429f  mov     rcx, [rbp+58h]; this
0x1800542a3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800542a8  nop
0x1800542a9  lea     rcx, [rsp+150h+punk]
0x1800542ae  call    ??1?$com_ptr_t@UIApplicationStatics@StateRepository@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::StateRepository::IApplicationStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::StateRepository::IApplicationStatics,wil::err_exception_policy>(void)
0x1800542b3  nop
0x1800542b4  mov     rcx, [rsp+150h+pv]; pv
0x1800542b9  mov     [rsp+150h+pv], r15
0x1800542be  test    rcx, rcx
0x1800542c1  jz      short loc_18005426C
0x1800542c3  call    cs:__imp_CoTaskMemFree
0x1800542c9  jmp     short loc_18005426C
0x1800542cb  lea     rax, [rsp+150h+pv]
0x1800542d0  mov     [rsp+150h+var_110], rax
0x1800542d5  mov     [rsp+150h+ppidl], r15
0x1800542da  mov     [rsp+150h+var_100], 1
0x1800542df  lea     rdx, [rsp+150h+ppidl]; ppidl
0x1800542e4  mov     rcx, [rsp+150h+punk]; punk
0x1800542e9  call    cs:__imp_SHGetIDListFromObject
0x1800542ef  mov     ebx, eax
0x1800542f1  lea     rcx, [rsp+150h+var_110]
0x1800542f6  call    ??1?$out_param_t@V?$unique_ptr@U_ITEMIDLIST@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_ITEMIDLIST,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMIDLIST,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x1800542fb  test    ebx, ebx
0x1800542fd  jns     short loc_180054306
0x1800542ff  mov     edx, 212h
0x180054304  jmp     short loc_180054295
0x180054306  lea     rax, FOLDERID_Downloads
0x18005430d  mov     [rsp+150h+var_F0], rax
0x180054312  lea     rax, FOLDERID_Desktop
0x180054319  mov     [rsp+150h+var_E8], rax
0x18005431e  lea     rax, unk_18010C3E8
0x180054325  mov     [rsp+150h+var_E0], rax
0x18005432a  lea     rax, FOLDERID_Documents
0x180054331  mov     [rsp+150h+var_D8], rax
0x180054336  lea     rax, FOLDERID_Pictures
0x18005433d  mov     [rbp+50h+var_D0], rax
0x180054341  lea     rax, FOLDERID_SavedPictures
0x180054348  mov     [rbp+50h+var_C8], rax
0x18005434c  lea     rax, FOLDERID_CameraRoll
0x180054353  mov     [rbp+50h+var_C0], rax
0x180054357  lea     rax, FOLDERID_NetworkFolder
0x18005435e  mov     [rbp+50h+var_B8], rax
0x180054362  lea     rax, FOLDERID_Windows
0x180054369  mov     [rbp+50h+var_B0], rax
0x18005436d  lea     rax, FOLDERID_ComputerFolder
0x180054374  mov     [rbp+50h+var_A8], rax
0x180054378  lea     rax, FOLDERID_RecycleBinFolder
0x18005437f  mov     [rbp+50h+var_A0], rax
0x180054383  lea     rax, FOLDERID_SearchHistory
0x18005438a  mov     [rbp+50h+var_98], rax
0x18005438e  lea     rax, FOLDERID_SearchHome
0x180054395  mov     [rbp+50h+var_90], rax
0x180054399  lea     rax, FOLDERID_PrintersFolder
0x1800543a0  mov     [rbp+50h+var_88], rax
0x1800543a4  lea     rax, FOLDERID_Music
0x1800543ab  mov     [rbp+50h+var_80], rax
0x1800543af  lea     rax, FOLDERID_Videos
0x1800543b6  mov     [rbp+50h+var_78], rax
0x1800543ba  lea     rax, FOLDERID_Device
0x1800543c1  mov     [rbp+50h+var_70], rax
0x1800543c5  lea     rax, FOLDERID_RecordedCalls
0x1800543cc  mov     [rbp+50h+var_68], rax
0x1800543d0  lea     rax, FOLDERID_Objects3D
0x1800543d7  mov     [rbp+50h+var_60], rax
0x1800543db  lea     rax, FOLDERID_OneDrive
0x1800543e2  mov     [rbp+50h+var_58], rax
0x1800543e6  lea     rax, FOLDERID_Public
0x1800543ed  mov     [rbp+50h+var_50], rax
0x1800543f1  lea     rax, FOLDERID_Profile
0x1800543f8  mov     [rbp+50h+var_48], rax
0x1800543fc  lea     rax, FOLDERID_UsersLibraries
0x180054403  mov     [rbp+50h+var_40], rax
0x180054407  lea     rax, FOLDERID_LocalAppData
0x18005440e  mov     [rbp+50h+var_38], rax
0x180054412  lea     rax, FOLDERID_AppsFolder
0x180054419  mov     [rbp+50h+var_30], rax
0x18005441d  lea     rax, FOLDERID_RoamingAppData
0x180054424  mov     [rbp+50h+var_28], rax
0x180054428  mov     [rsp+150h+pidl1], r15
0x18005442d  lea     rax, [rsp+150h+pidl1]
0x180054432  mov     [rsp+150h+var_110], rax
0x180054437  mov     [rsp+150h+ppidl], r15
0x18005443c  mov     [rsp+150h+var_100], 1
0x180054441  lea     r8, [rsp+150h+ppidl]; struct _ITEMIDLIST **
0x180054446  mov     rdx, [rsp+150h+pv]; struct _ITEMIDLIST *
0x18005444b  call    ?ConvertIDListEnumMode@@YAJW4FOLDER_ENUM_MODE@@PEFBU_ITEMIDLIST@@PEAPEFAU2@@Z; ConvertIDListEnumMode(FOLDER_ENUM_MODE,_ITEMIDLIST const *,_ITEMIDLIST * *)
0x180054450  mov     ebx, eax
0x180054452  lea     rcx, [rsp+150h+var_110]
0x180054457  call    ??1?$out_param_t@V?$unique_ptr@U_ITEMIDLIST@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_ITEMIDLIST,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMIDLIST,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18005445c  test    ebx, ebx
0x18005445e  jns     short loc_180054497
0x180054460  mov     rcx, [rbp+58h]; this
0x180054464  mov     r9d, ebx; char *
0x180054467  lea     r8, aOnecoreuapInte_6; "onecoreuap\\internal\\shell\\inc\\priva"...
0x18005446e  mov     edx, 236h; void *
0x180054473  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180054478  nop
0x180054479  mov     rcx, [rsp+150h+pidl1]; pv
0x18005447e  mov     [rsp+150h+pidl1], r15
0x180054483  test    rcx, rcx
0x180054486  jz      loc_1800542A9
0x18005448c  call    cs:__imp_CoTaskMemFree
0x180054492  jmp     loc_1800542A9
0x180054497  lea     rdi, [rsp+150h+var_F0]
0x18005449c  mov     [rsp+150h+pidl2], r15
0x1800544a1  lea     rax, [rsp+150h+pidl2]
0x1800544a6  mov     [rsp+150h+var_110], rax
0x1800544ab  mov     [rsp+150h+ppidl], r15
0x1800544b0  mov     [rsp+150h+var_100], 1
0x1800544b5  mov     rsi, [rdi]
0x1800544b8  lea     r9, [rsp+150h+ppidl]; ppidl
0x1800544bd  xor     r8d, r8d; hToken
0x1800544c0  mov     edx, 5000h; dwFlags
0x1800544c5  mov     rcx, rsi; rfid
0x1800544c8  call    cs:__imp_SHGetKnownFolderIDList
0x1800544ce  mov     ebx, eax
0x1800544d0  lea     rcx, [rsp+150h+var_110]
0x1800544d5  call    ??1?$out_param_t@V?$unique_ptr@U_ITEMIDLIST@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_ITEMIDLIST,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMIDLIST,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x1800544da  test    ebx, ebx
0x1800544dc  js      short loc_1800544F2
0x1800544de  mov     rdx, [rsp+150h+pidl2]; pidl2
0x1800544e3  mov     rcx, [rsp+150h+pidl1]; pidl1
0x1800544e8  call    cs:__imp_ILIsEqual
0x1800544ee  test    eax, eax
0x1800544f0  jnz     short loc_180054516
0x1800544f2  mov     rcx, [rsp+150h+pidl2]; pv
0x1800544f7  mov     [rsp+150h+pidl2], r15
0x1800544fc  test    rcx, rcx
0x1800544ff  jz      short loc_180054507
0x180054501  call    cs:__imp_CoTaskMemFree
0x180054507  add     rdi, 8
0x18005450b  lea     rax, [rbp+50h+var_20]
0x18005450f  cmp     rdi, rax
0x180054512  jnz     short loc_18005449C
0x180054514  jmp     short loc_180054534
0x180054516  movups  xmm0, xmmword ptr [rsi]
0x180054519  movdqu  xmmword ptr [r14], xmm0
0x18005451e  mov     rcx, [rsp+150h+pidl2]; pv
0x180054523  mov     [rsp+150h+pidl2], r15
0x180054528  test    rcx, rcx
0x18005452b  jz      short loc_180054534
0x18005452d  call    cs:__imp_CoTaskMemFree
0x180054533  nop
0x180054534  mov     rcx, [rsp+150h+pidl1]; pv
0x180054539  test    rcx, rcx
0x18005453c  mov     [rsp+150h+pidl1], r15
0x180054541  jz      short loc_18005454A
0x180054543  call    cs:__imp_CoTaskMemFree
0x180054549  nop
0x18005454a  lea     rcx, [rsp+150h+punk]
0x18005454f  call    ??1?$com_ptr_t@UIApplicationStatics@StateRepository@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::StateRepository::IApplicationStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::StateRepository::IApplicationStatics,wil::err_exception_policy>(void)
0x180054554  nop
0x180054555  mov     rcx, [rsp+150h+pv]; pv
0x18005455a  test    rcx, rcx
0x18005455d  mov     [rsp+150h+pv], r15
0x180054562  jz      short loc_18005456A
0x180054564  call    cs:__imp_CoTaskMemFree
0x18005456a  xor     eax, eax
0x18005456c  mov     rbx, [rsp+150h+arg_18]
0x180054574  add     rsp, 130h
0x18005457b  pop     r15
0x18005457d  pop     r14
0x18005457f  pop     rdi
0x180054580  pop     rsi
0x180054581  pop     rbp
0x180054582  retn
```
