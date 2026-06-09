# NamespaceRestrictionHelper::KeyShouldAllowAccessToFolder(IShellItem *,HKEY__ *,HKEY__ *,NamespaceRestrictionAccessOptions *)

- ea: `0x1800586f4`
- end: `0x180058b76`
- name: `?KeyShouldAllowAccessToFolder@NamespaceRestrictionHelper@@AEAAJPEAUIShellItem@@PEAUHKEY__@@1PEAW4NamespaceRestrictionAccessOptions@@@Z`
- size: `1154`
- prototype: `__int64 __fastcall(NamespaceRestrictionHelper *__hidden this, struct IShellItem *, HKEY, HKEY, enum NamespaceRestrictionAccessOptions *)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18005af60`

## callees

- `0x180006e50`
- `0x180009b17`
- `0x18000e6cc`
- `0x180018244`
- `0x1800292a8`
- `0x18004f948`
- `0x18004f990`
- `0x180050904`
- `0x180053c48`
- `0x180053e70`
- `0x18005421c`
- `0x18005458c`
- `0x180057828`
- `0x1800585f4`
- `0x1800586f4`
- `0x180058b7c`
- `0x180058cf0`
- `0x18005a1ec`
- `0x18005ab78`
- `0x1800e3010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180058ac8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180058b46`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180058ac8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180058b46`
- `api-ms-win-shell-namespace-l1-1-0!ILIsEqual` at `0x180058adf`
- `api-ms-win-shell-namespace-l1-1-0!ILIsEqual` at `0x180058adf`
- `api-ms-win-shell-namespace-l1-1-0!SHGetIDListFromObject` at `0x180058a89`
- `api-ms-win-shell-namespace-l1-1-0!SHGetIDListFromObject` at `0x180058a89`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall NamespaceRestrictionHelper::KeyShouldAllowAccessToFolder(
        NamespaceRestrictionHelper *this,
        struct IShellItem *a2,
        HKEY a3,
        HKEY a4,
        enum NamespaceRestrictionAccessOptions *a5)
{
  NamespaceRestrictionHelper *v9; // rcx
  bool v10; // r14
  NamespaceRestrictionHelper *v11; // rcx
  HRESULT ShouldAllowAccessToKnownFolder; // ebx
  __int64 v13; // rdx
  char v15; // r14
  char v16; // r13
  struct IShellItem *v17; // rbx
  struct IShellItem *i; // rax
  int v19; // eax
  unsigned int v20; // r14d
  struct IShellItem *v21; // r14
  struct IShellItem v22; // rax
  NamespaceRestrictionHelper *v23; // rcx
  __int64 v24; // rdx
  bool v25; // dl
  NamespaceRestrictionHelper *v26; // rcx
  int DriveLetterForFolder; // ebx
  NamespaceRestrictionHelper *v28; // rcx
  int ShouldAllowAccessToDrive; // eax
  __int64 v30; // rdx
  void *v31; // rcx
  const ITEMIDLIST *GalleryPidl; // rax
  NamespaceRestrictionHelper *v33; // rcx
  void *v34; // rcx
  bool v35; // zf
  int v36; // [rsp+20h] [rbp-51h]
  bool v37; // [rsp+30h] [rbp-41h] BYREF
  bool v38; // [rsp+31h] [rbp-40h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-39h] BYREF
  unsigned __int16 *v40; // [rsp+40h] [rbp-31h] BYREF
  NamespaceRestrictionHelper *v41; // [rsp+48h] [rbp-29h]
  LPITEMIDLIST ppidl[2]; // [rsp+50h] [rbp-21h] BYREF
  char v43; // [rsp+60h] [rbp-11h]
  struct _GUID Buf1; // [rsp+68h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+57h]

  v41 = this;
  *(_DWORD *)a5 = 0;
  if ( !(unsigned int)IShellItem_IsFolder(a2) )
    goto LABEL_59;
  v37 = 0;
  v10 = 0;
  v38 = 0;
  ShouldAllowAccessToKnownFolder = NamespaceRestrictionHelper::RestrictionAppliesToStorageProvider(v9, a2, a3, &v37);
  if ( ShouldAllowAccessToKnownFolder < 0 )
  {
    v13 = 932;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\NamespaceRestrictionHelper.h",
      (const char *)(unsigned int)ShouldAllowAccessToKnownFolder,
      v36);
    return (unsigned int)ShouldAllowAccessToKnownFolder;
  }
  if ( a4 )
  {
    ShouldAllowAccessToKnownFolder = NamespaceRestrictionHelper::RestrictionAppliesToStorageProvider(v11, a2, a4, &v38);
    if ( ShouldAllowAccessToKnownFolder < 0 )
    {
      v13 = 935;
      goto LABEL_4;
    }
    v10 = v38;
  }
  if ( !v37 || v10 )
  {
    Buf1 = 0;
    NamespaceRestrictionHelper::GetKnownFolderIdNearestMatch(this, a2, &Buf1);
    v15 = 1;
    if ( !memcmp_0(&Buf1, &GUID_NULL, 0x10u) )
    {
      v37 = 0;
    }
    else
    {
      ShouldAllowAccessToKnownFolder = NamespaceRestrictionHelper::KeyShouldAllowAccessToKnownFolder(
                                         this,
                                         &Buf1,
                                         a3,
                                         a4,
                                         a5);
      if ( ShouldAllowAccessToKnownFolder < 0 )
      {
        v13 = 953;
        goto LABEL_4;
      }
      v37 = 1;
    }
    if ( !*(_DWORD *)a5 )
    {
      v16 = 0;
      v17 = a2;
      v40 = (unsigned __int16 *)a2;
      if ( a2 )
        ((void (__fastcall *)(struct IShellItem *))a2->lpVtbl->AddRef)(a2);
      for ( i = a2; i; i = v17 )
      {
        *(_OWORD *)ppidl = 0;
        NamespaceRestrictionHelper::GetKnownFolderIdFromItem(v41, v17, (struct _GUID *)ppidl);
        if ( memcmp_0(ppidl, &GUID_NULL, 0x10u) )
        {
          if ( memcmp_0(ppidl, &FOLDERID_Desktop, 0x10u) || v15 )
          {
            if ( v15 )
              v16 = 1;
            v19 = NamespaceRestrictionHelper::KeyShouldAllowAccessToKnownFolder(
                    v41,
                    (const struct _GUID *)ppidl,
                    a3,
                    a4,
                    a5);
            v20 = v19;
            if ( v19 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x3D7,
                (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\NamespaceRestrictionHelper.h",
                (const char *)(unsigned int)v19,
                v36);
              wil::com_ptr_t<Windows::Internal::StateRepository::IApplicationStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::StateRepository::IApplicationStatics,wil::err_exception_policy>(&v40);
              return v20;
            }
            if ( *(_DWORD *)a5 )
              break;
          }
        }
        pv = 0;
        v21 = v17;
        v22.lpVtbl = v17->lpVtbl;
        pv = 0;
        ((void (__fastcall *)(struct IShellItem *, LPVOID *))v22.lpVtbl->GetParent)(v17, &pv);
        v17 = (struct IShellItem *)pv;
        v40 = (unsigned __int16 *)pv;
        if ( pv )
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 8LL))(pv);
        if ( v21 )
          ((void (__fastcall *)(struct IShellItem *))v21->lpVtbl->Release)(v21);
        v15 = 0;
        wil::com_ptr_t<Windows::Internal::StateRepository::IApplicationStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::StateRepository::IApplicationStatics,wil::err_exception_policy>(&pv);
      }
      wil::com_ptr_t<Windows::Internal::StateRepository::IApplicationStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::StateRepository::IApplicationStatics,wil::err_exception_policy>(&v40);
      if ( !*(_DWORD *)a5 && !v37 && !v16 )
      {
        v37 = 0;
        ShouldAllowAccessToKnownFolder = NamespaceRestrictionHelper::AreAllStorageLocationsAllowed(v23, a3, &v37);
        if ( ShouldAllowAccessToKnownFolder < 0 )
        {
          v13 = 1000;
          goto LABEL_4;
        }
        v25 = v37;
        *(_DWORD *)a5 = v37 + 1;
        if ( !v25 )
        {
          LOBYTE(v24) = 1;
          wil::details::FeatureImpl<__WilFeatureTraits_Feature_DriveBasedNamespaceRestrictions>::ReportUsage(
            &`wil::Feature<__WilFeatureTraits_Feature_DriveBasedNamespaceRestrictions>::GetImpl'::`2'::impl,
            v24);
          v40 = 0;
          ppidl[0] = (LPITEMIDLIST)&v40;
          ppidl[1] = 0;
          v43 = 1;
          DriveLetterForFolder = NamespaceRestrictionHelper::GetDriveLetterForFolder(
                                   v26,
                                   a2,
                                   (unsigned __int16 **)&ppidl[1]);
          wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(ppidl);
          if ( DriveLetterForFolder >= 0 )
          {
            ShouldAllowAccessToDrive = NamespaceRestrictionHelper::KeyShouldAllowAccessToDrive(v28, v40, a3, a4, a5);
            ShouldAllowAccessToKnownFolder = ShouldAllowAccessToDrive;
            if ( ShouldAllowAccessToDrive < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x3F5,
                (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\NamespaceRestrictionHelper.h",
                (const char *)(unsigned int)ShouldAllowAccessToDrive,
                v36);
LABEL_46:
              wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v40);
              return (unsigned int)ShouldAllowAccessToKnownFolder;
            }
            if ( *(_DWORD *)a5 )
            {
              ShouldAllowAccessToKnownFolder = 0;
              goto LABEL_46;
            }
          }
          wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v40);
          pv = 0;
          ppidl[0] = (LPITEMIDLIST)&pv;
          ppidl[1] = 0;
          v43 = 1;
          ShouldAllowAccessToKnownFolder = SHGetIDListFromObject((IUnknown *)a2, &ppidl[1]);
          wil::details::out_param_t<wistd::unique_ptr<_ITEMIDLIST,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMIDLIST,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(ppidl);
          if ( ShouldAllowAccessToKnownFolder < 0 )
          {
            v30 = 1022;
            goto LABEL_49;
          }
          GalleryPidl = (const ITEMIDLIST *)GetGalleryPidl();
          if ( !ILIsEqual((LPCITEMIDLIST)pv, GalleryPidl) )
            goto LABEL_55;
          ShouldAllowAccessToKnownFolder = NamespaceRestrictionHelper::KeyShouldAllowAccessToKnownFolder(
                                             v41,
                                             &FOLDERID_Pictures,
                                             a3,
                                             a4,
                                             a5);
          if ( ShouldAllowAccessToKnownFolder < 0 )
          {
            v30 = 1025;
            goto LABEL_49;
          }
          if ( !*(_DWORD *)a5 )
          {
LABEL_55:
            ShouldAllowAccessToKnownFolder = NamespaceRestrictionHelper::KeyShouldAllowAccessToStorageLocation(
                                               v33,
                                               a2,
                                               a3,
                                               a4,
                                               a5);
            if ( ShouldAllowAccessToKnownFolder < 0 )
            {
              v30 = 1032;
LABEL_49:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v30,
                (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\NamespaceRestrictionHelper.h",
                (const char *)(unsigned int)ShouldAllowAccessToKnownFolder,
                v36);
              v31 = pv;
              pv = 0;
              if ( v31 )
                CoTaskMemFree(v31);
              return (unsigned int)ShouldAllowAccessToKnownFolder;
            }
          }
          v34 = pv;
          v35 = pv == 0;
          pv = 0;
          if ( !v35 )
            CoTaskMemFree(v34);
        }
      }
    }
  }
  else
  {
LABEL_59:
    *(_DWORD *)a5 = 2;
  }
  return 0;
}

```

## disassembly

```asm
0x1800586f4  push    rbp
0x1800586f6  push    rbx
0x1800586f7  push    rsi
0x1800586f8  push    rdi
0x1800586f9  push    r12
0x1800586fb  push    r13
0x1800586fd  push    r14
0x1800586ff  push    r15
0x180058701  lea     rbp, [rsp-17h]
0x180058706  sub     rsp, 88h
0x18005870d  mov     rax, cs:__security_cookie
0x180058714  xor     rax, rsp
0x180058717  mov     [rbp+4Fh+var_48], rax
0x18005871b  mov     r15, r9
0x18005871e  mov     r12, r8
0x180058721  mov     rsi, rdx
0x180058724  mov     r13, rcx
0x180058727  mov     [rbp+4Fh+var_78], rcx
0x18005872b  mov     rdi, [rbp+4Fh+arg_20]
0x18005872f  mov     dword ptr [rdi], 0
0x180058735  mov     rcx, rdx; struct IShellItem *
0x180058738  call    ?IShellItem_IsFolder@@YAHPEAUIShellItem@@@Z; IShellItem_IsFolder(IShellItem *)
0x18005873d  test    eax, eax
0x18005873f  jz      loc_180058B4E
0x180058745  mov     [rbp+4Fh+var_90], 0
0x180058749  xor     r14b, r14b
0x18005874c  mov     [rbp+4Fh+var_8F], r14b
0x180058750  lea     r9, [rbp+4Fh+var_90]; bool *
0x180058754  mov     r8, r12; HKEY
0x180058757  mov     rdx, rsi; struct IShellItem *
0x18005875a  call    ?RestrictionAppliesToStorageProvider@NamespaceRestrictionHelper@@AEAAJPEAUIShellItem@@PEAUHKEY__@@PEA_N@Z; NamespaceRestrictionHelper::RestrictionAppliesToStorageProvider(IShellItem *,HKEY__ *,bool *)
0x18005875f  mov     ebx, eax
0x180058761  test    eax, eax
0x180058763  jns     short loc_180058784
0x180058765  mov     edx, 3A4h; void *
0x18005876a  lea     r8, aOnecoreuapInte_6; "onecoreuap\\internal\\shell\\inc\\priva"...
0x180058771  mov     r9d, ebx; char *
0x180058774  mov     rcx, [rbp+57h]; this
0x180058778  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005877d  mov     eax, ebx
0x18005877f  jmp     loc_180058B56
0x180058784  test    r15, r15
0x180058787  jz      short loc_1800587A9
0x180058789  lea     r9, [rbp+4Fh+var_8F]; bool *
0x18005878d  mov     r8, r15; HKEY
0x180058790  mov     rdx, rsi; struct IShellItem *
0x180058793  call    ?RestrictionAppliesToStorageProvider@NamespaceRestrictionHelper@@AEAAJPEAUIShellItem@@PEAUHKEY__@@PEA_N@Z; NamespaceRestrictionHelper::RestrictionAppliesToStorageProvider(IShellItem *,HKEY__ *,bool *)
0x180058798  mov     ebx, eax
0x18005879a  test    eax, eax
0x18005879c  jns     short loc_1800587A5
0x18005879e  mov     edx, 3A7h
0x1800587a3  jmp     short loc_18005876A
0x1800587a5  mov     r14b, [rbp+4Fh+var_8F]
0x1800587a9  cmp     [rbp+4Fh+var_90], 0
0x1800587ad  jz      short loc_1800587B8
0x1800587af  test    r14b, r14b
0x1800587b2  jz      loc_180058B4E
0x1800587b8  xorps   xmm0, xmm0
0x1800587bb  movups  [rbp+4Fh+Buf1], xmm0
0x1800587bf  lea     r8, [rbp+4Fh+Buf1]; struct _GUID *
0x1800587c3  mov     rdx, rsi; struct IShellItem *
0x1800587c6  mov     rcx, r13; this
0x1800587c9  call    ?GetKnownFolderIdNearestMatch@NamespaceRestrictionHelper@@AEAAJPEAUIShellItem@@PEAU_GUID@@@Z; NamespaceRestrictionHelper::GetKnownFolderIdNearestMatch(IShellItem *,_GUID *)
0x1800587ce  mov     r8d, 10h; Size
0x1800587d4  lea     rdx, GUID_NULL; Buf2
0x1800587db  lea     rcx, [rbp+4Fh+Buf1]; Buf1
0x1800587df  call    memcmp_0
0x1800587e4  mov     r14d, 1
0x1800587ea  test    eax, eax
0x1800587ec  jnz     short loc_1800587F3
0x1800587ee  mov     [rbp+4Fh+var_90], al
0x1800587f1  jmp     short loc_18005881E
0x1800587f3  mov     qword ptr [rsp+0C0h+var_A0], rdi; int
0x1800587f8  mov     r9, r15; HKEY
0x1800587fb  mov     r8, r12; HKEY
0x1800587fe  lea     rdx, [rbp+4Fh+Buf1]; struct _GUID *
0x180058802  mov     rcx, r13; this
0x180058805  call    ?KeyShouldAllowAccessToKnownFolder@NamespaceRestrictionHelper@@AEAAJPEBU_GUID@@PEAUHKEY__@@1PEAW4NamespaceRestrictionAccessOptions@@@Z; NamespaceRestrictionHelper::KeyShouldAllowAccessToKnownFolder(_GUID const *,HKEY__ *,HKEY__ *,NamespaceRestrictionAccessOptions *)
0x18005880a  mov     ebx, eax
0x18005880c  test    eax, eax
0x18005880e  jns     short loc_18005881A
0x180058810  mov     edx, 3B9h
0x180058815  jmp     loc_18005876A
0x18005881a  mov     [rbp+4Fh+var_90], r14b
0x18005881e  cmp     dword ptr [rdi], 0
0x180058821  jnz     loc_180058B54
0x180058827  xor     r13b, r13b
0x18005882a  mov     rbx, rsi
0x18005882d  mov     [rbp+4Fh+var_80], rbx
0x180058831  test    rsi, rsi
0x180058834  jz      short loc_180058846
0x180058836  mov     rax, [rsi]
0x180058839  mov     rcx, rsi
0x18005883c  mov     rax, [rax+8]
0x180058840  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058845  nop
0x180058846  mov     rax, rsi
0x180058849  test    rax, rax
0x18005884c  jz      loc_180058973
0x180058852  xorps   xmm0, xmm0
0x180058855  movups  xmmword ptr [rbp+4Fh+ppidl], xmm0
0x180058859  lea     r8, [rbp+4Fh+ppidl]; struct _GUID *
0x18005885d  mov     rdx, rbx; struct IShellItem *
0x180058860  mov     rcx, [rbp+4Fh+var_78]; this
0x180058864  call    ?GetKnownFolderIdFromItem@NamespaceRestrictionHelper@@AEAAJPEAUIShellItem@@PEAU_GUID@@@Z; NamespaceRestrictionHelper::GetKnownFolderIdFromItem(IShellItem *,_GUID *)
0x180058869  mov     r8d, 10h; Size
0x18005886f  lea     rdx, GUID_NULL; Buf2
0x180058876  lea     rcx, [rbp+4Fh+ppidl]; Buf1
0x18005887a  call    memcmp_0
0x18005887f  test    eax, eax
0x180058881  jz      short loc_1800588DF
0x180058883  mov     r8d, 10h; Size
0x180058889  lea     rdx, FOLDERID_Desktop; Buf2
0x180058890  lea     rcx, [rbp+4Fh+ppidl]; Buf1
0x180058894  call    memcmp_0
0x180058899  test    eax, eax
0x18005889b  jnz     short loc_1800588A2
0x18005889d  test    r14b, r14b
0x1800588a0  jz      short loc_1800588DF
0x1800588a2  movzx   r13d, r13b
0x1800588a6  test    r14b, r14b
0x1800588a9  mov     eax, 1
0x1800588ae  cmovnz  r13d, eax
0x1800588b2  mov     qword ptr [rsp+0C0h+var_A0], rdi; int
0x1800588b7  mov     r9, r15; HKEY
0x1800588ba  mov     r8, r12; HKEY
0x1800588bd  lea     rdx, [rbp+4Fh+ppidl]; struct _GUID *
0x1800588c1  mov     rcx, [rbp+4Fh+var_78]; this
0x1800588c5  call    ?KeyShouldAllowAccessToKnownFolder@NamespaceRestrictionHelper@@AEAAJPEBU_GUID@@PEAUHKEY__@@1PEAW4NamespaceRestrictionAccessOptions@@@Z; NamespaceRestrictionHelper::KeyShouldAllowAccessToKnownFolder(_GUID const *,HKEY__ *,HKEY__ *,NamespaceRestrictionAccessOptions *)
0x1800588ca  mov     r14d, eax
0x1800588cd  test    eax, eax
0x1800588cf  js      short loc_180058949
0x1800588d1  xor     r14d, r14d
0x1800588d4  cmp     [rdi], r14d
0x1800588d7  jnz     loc_180058976
0x1800588dd  jmp     short loc_1800588E2
0x1800588df  xor     r14d, r14d
0x1800588e2  mov     [rbp+4Fh+pv], r14
0x1800588e6  mov     r14, rbx
0x1800588e9  mov     rax, [rbx]
0x1800588ec  mov     [rbp+4Fh+pv], 0
0x1800588f4  lea     rdx, [rbp+4Fh+pv]
0x1800588f8  mov     rcx, rbx
0x1800588fb  mov     rax, [rax+20h]
0x1800588ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058904  mov     rbx, [rbp+4Fh+pv]
0x180058908  mov     [rbp+4Fh+var_80], rbx
0x18005890c  test    rbx, rbx
0x18005890f  jz      short loc_180058920
0x180058911  mov     rax, [rbx]
0x180058914  mov     rcx, rbx
0x180058917  mov     rax, [rax+8]
0x18005891b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058920  test    r14, r14
0x180058923  jz      short loc_180058935
0x180058925  mov     rax, [r14]
0x180058928  mov     rcx, r14
0x18005892b  mov     rax, [rax+10h]
0x18005892f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058934  nop
0x180058935  xor     r14b, r14b
0x180058938  lea     rcx, [rbp+4Fh+pv]
0x18005893c  call    ??1?$com_ptr_t@UIApplicationStatics@StateRepository@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::StateRepository::IApplicationStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::StateRepository::IApplicationStatics,wil::err_exception_policy>(void)
0x180058941  mov     rax, rbx
0x180058944  jmp     loc_180058849
0x180058949  mov     rcx, [rbp+57h]; this
0x18005894d  mov     r9d, r14d; char *
0x180058950  lea     r8, aOnecoreuapInte_6; "onecoreuap\\internal\\shell\\inc\\priva"...
0x180058957  mov     edx, 3D7h; void *
0x18005895c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180058961  nop
0x180058962  lea     rcx, [rbp+4Fh+var_80]
0x180058966  call    ??1?$com_ptr_t@UIApplicationStatics@StateRepository@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::StateRepository::IApplicationStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::StateRepository::IApplicationStatics,wil::err_exception_policy>(void)
0x18005896b  mov     eax, r14d
0x18005896e  jmp     loc_180058B56
0x180058973  xor     r14d, r14d
0x180058976  lea     rcx, [rbp+4Fh+var_80]
0x18005897a  call    ??1?$com_ptr_t@UIApplicationStatics@StateRepository@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::StateRepository::IApplicationStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::StateRepository::IApplicationStatics,wil::err_exception_policy>(void)
0x18005897f  cmp     [rdi], r14d
0x180058982  jnz     loc_180058B54
0x180058988  cmp     [rbp+4Fh+var_90], r14b
0x18005898c  jnz     loc_180058B54
0x180058992  test    r13b, r13b
0x180058995  jnz     loc_180058B54
0x18005899b  mov     [rbp+4Fh+var_90], r14b
0x18005899f  lea     r8, [rbp+4Fh+var_90]; bool *
0x1800589a3  mov     rdx, r12; HKEY
0x1800589a6  call    ?AreAllStorageLocationsAllowed@NamespaceRestrictionHelper@@AEAAJPEAUHKEY__@@PEA_N@Z; NamespaceRestrictionHelper::AreAllStorageLocationsAllowed(HKEY__ *,bool *)
0x1800589ab  mov     ebx, eax
0x1800589ad  test    eax, eax
0x1800589af  jns     short loc_1800589BB
0x1800589b1  mov     edx, 3E8h
0x1800589b6  jmp     loc_18005876A
0x1800589bb  mov     dl, [rbp+4Fh+var_90]
0x1800589be  mov     al, dl
0x1800589c0  neg     al
0x1800589c2  sbb     ecx, ecx
0x1800589c4  neg     ecx
0x1800589c6  mov     r13d, 1
0x1800589cc  add     ecx, r13d
0x1800589cf  mov     [rdi], ecx
0x1800589d1  test    dl, dl
0x1800589d3  jnz     loc_180058B54
0x1800589d9  mov     dl, r13b
0x1800589dc  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DriveBasedNamespaceRestrictions@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DriveBasedNamespaceRestrictions@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DriveBasedNamespaceRestrictions> `wil::Feature<__WilFeatureTraits_Feature_DriveBasedNamespaceRestrictions>::GetImpl(void)'::`2'::impl
0x1800589e3  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_DriveBasedNamespaceRestrictions@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DriveBasedNamespaceRestrictions>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800589e8  mov     [rbp+4Fh+var_80], r14
0x1800589ec  lea     rax, [rbp+4Fh+var_80]
0x1800589f0  mov     [rbp+4Fh+ppidl], rax
0x1800589f4  mov     [rbp+4Fh+ppidl+8], r14
0x1800589f8  mov     [rbp+4Fh+var_60], r13b
0x1800589fc  lea     r8, [rbp+4Fh+ppidl+8]; unsigned __int16 **
0x180058a00  mov     rdx, rsi; struct IShellItem *
0x180058a03  call    ?GetDriveLetterForFolder@NamespaceRestrictionHelper@@AEAAJPEAUIShellItem@@PEAPEAG@Z; NamespaceRestrictionHelper::GetDriveLetterForFolder(IShellItem *,ushort * *)
0x180058a08  mov     ebx, eax
0x180058a0a  lea     rcx, [rbp+4Fh+ppidl]
0x180058a0e  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x180058a13  shr     ebx, 1Fh
0x180058a16  xor     bl, r13b
0x180058a19  jz      short loc_180058A65
0x180058a1b  mov     qword ptr [rsp+0C0h+var_A0], rdi; int
0x180058a20  mov     r9, r15; HKEY
0x180058a23  mov     r8, r12; HKEY
0x180058a26  mov     rdx, [rbp+4Fh+var_80]; unsigned __int16 *
0x180058a2a  call    ?KeyShouldAllowAccessToDrive@NamespaceRestrictionHelper@@AEAAJPEBGPEAUHKEY__@@1PEAW4NamespaceRestrictionAccessOptions@@@Z; NamespaceRestrictionHelper::KeyShouldAllowAccessToDrive(ushort const *,HKEY__ *,HKEY__ *,NamespaceRestrictionAccessOptions *)
0x180058a2f  mov     ebx, eax
0x180058a31  test    eax, eax
0x180058a33  jns     short loc_180058A4F
0x180058a35  mov     rcx, [rbp+57h]; this
0x180058a39  mov     r9d, eax; char *
0x180058a3c  lea     r8, aOnecoreuapInte_6; "onecoreuap\\internal\\shell\\inc\\priva"...
0x180058a43  mov     edx, 3F5h; void *
0x180058a48  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180058a4d  jmp     short loc_180058A57
0x180058a4f  cmp     [rdi], r14d
0x180058a52  jz      short loc_180058A65
0x180058a54  mov     ebx, r14d
0x180058a57  lea     rcx, [rbp+4Fh+var_80]
0x180058a5b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180058a60  jmp     loc_18005877D
0x180058a65  lea     rcx, [rbp+4Fh+var_80]
0x180058a69  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180058a6e  mov     [rbp+4Fh+pv], r14
0x180058a72  lea     rax, [rbp+4Fh+pv]
0x180058a76  mov     [rbp+4Fh+ppidl], rax
0x180058a7a  mov     [rbp+4Fh+ppidl+8], r14
0x180058a7e  mov     [rbp+4Fh+var_60], r13b
0x180058a82  lea     rdx, [rbp+4Fh+ppidl+8]; ppidl
0x180058a86  mov     rcx, rsi; punk
0x180058a89  call    cs:__imp_SHGetIDListFromObject
0x180058a8f  mov     ebx, eax
0x180058a91  lea     rcx, [rbp+4Fh+ppidl]
0x180058a95  call    ??1?$out_param_t@V?$unique_ptr@U_ITEMIDLIST@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_ITEMIDLIST,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMIDLIST,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180058a9a  test    ebx, ebx
0x180058a9c  jns     short loc_180058AD3
0x180058a9e  mov     edx, 3FEh; void *
0x180058aa3  mov     rcx, [rbp+57h]; this
0x180058aa7  mov     r9d, ebx; char *
0x180058aaa  lea     r8, aOnecoreuapInte_6; "onecoreuap\\internal\\shell\\inc\\priva"...
0x180058ab1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180058ab6  nop
0x180058ab7  mov     rcx, [rbp+4Fh+pv]; pv
0x180058abb  mov     [rbp+4Fh+pv], r14
0x180058abf  test    rcx, rcx
0x180058ac2  jz      loc_18005877D
0x180058ac8  call    cs:__imp_CoTaskMemFree
0x180058ace  jmp     loc_18005877D
0x180058ad3  call    GetGalleryPidl
0x180058ad8  mov     rdx, rax; pidl2
0x180058adb  mov     rcx, [rbp+4Fh+pv]; pidl1
0x180058adf  call    cs:__imp_ILIsEqual
0x180058ae5  test    eax, eax
0x180058ae7  jz      short loc_180058B16
0x180058ae9  mov     qword ptr [rsp+0C0h+var_A0], rdi; enum NamespaceRestrictionAccessOptions *
0x180058aee  mov     r9, r15; HKEY
0x180058af1  mov     r8, r12; HKEY
0x180058af4  lea     rdx, FOLDERID_Pictures; struct _GUID *
0x180058afb  mov     rcx, [rbp+4Fh+var_78]; this
0x180058aff  call    ?KeyShouldAllowAccessToKnownFolder@NamespaceRestrictionHelper@@AEAAJPEBU_GUID@@PEAUHKEY__@@1PEAW4NamespaceRestrictionAccessOptions@@@Z; NamespaceRestrictionHelper::KeyShouldAllowAccessToKnownFolder(_GUID const *,HKEY__ *,HKEY__ *,NamespaceRestrictionAccessOptions *)
0x180058b04  mov     ebx, eax
0x180058b06  test    eax, eax
0x180058b08  jns     short loc_180058B11
0x180058b0a  mov     edx, 401h
0x180058b0f  jmp     short loc_180058AA3
0x180058b11  cmp     [rdi], r14d
0x180058b14  jnz     short loc_180058B39
0x180058b16  mov     qword ptr [rsp+0C0h+var_A0], rdi; enum NamespaceRestrictionAccessOptions *
0x180058b1b  mov     r9, r15; HKEY
0x180058b1e  mov     r8, r12; HKEY
0x180058b21  mov     rdx, rsi; struct IShellItem *
0x180058b24  call    ?KeyShouldAllowAccessToStorageLocation@NamespaceRestrictionHelper@@AEAAJPEAUIShellItem@@PEAUHKEY__@@1PEAW4NamespaceRestrictionAccessOptions@@@Z; NamespaceRestrictionHelper::KeyShouldAllowAccessToStorageLocation(IShellItem *,HKEY__ *,HKEY__ *,NamespaceRestrictionAccessOptions *)
0x180058b29  mov     ebx, eax
0x180058b2b  test    eax, eax
0x180058b2d  jns     short loc_180058B39
0x180058b2f  mov     edx, 408h
0x180058b34  jmp     loc_180058AA3
0x180058b39  mov     rcx, [rbp+4Fh+pv]; pv
0x180058b3d  test    rcx, rcx
0x180058b40  mov     [rbp+4Fh+pv], r14
0x180058b44  jz      short loc_180058B54
  ... truncated ...
```
