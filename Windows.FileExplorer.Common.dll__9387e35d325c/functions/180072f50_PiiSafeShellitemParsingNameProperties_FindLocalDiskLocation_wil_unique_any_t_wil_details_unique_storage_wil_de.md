# PiiSafeShellitemParsingNameProperties::FindLocalDiskLocation(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> const &,uchar &)

- ea: `0x180072f50`
- end: `0x18007338b`
- name: `?FindLocalDiskLocation@PiiSafeShellitemParsingNameProperties@@AEAA?AW4ShellitemParsingNameRootLoc@@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@AEAE@Z`
- size: `1083`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180075bec`

## callees

- `0x180007900`
- `0x180035f08`
- `0x180037780`
- `0x1800386e4`
- `0x180072350`
- `0x180072f50`
- `0x180073b94`
- `0x180074580`
- `0x180076920`
- `0x180077ee8`
- `0x180077f24`
- `0x1800781d0`

## import_xrefs

- `Windows.Storage!__imp_PathComparePaths` at `0x180073203`
- `Windows.Storage!__imp_PathComparePaths` at `0x18007332d`
- `Windows.Storage!__imp_PathComparePaths` at `0x180073203`
- `Windows.Storage!__imp_PathComparePaths` at `0x18007332d`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x1800731e8`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x1800731e8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall PiiSafeShellitemParsingNameProperties::FindLocalDiskLocation(
        __int64 a1,
        const unsigned __int16 *const *a2,
        unsigned __int8 *a3)
{
  PiiSafeFolderList *v5; // rax
  const unsigned __int16 **v6; // rax
  PiiSafeShellitemParsingNameProperties *v7; // rcx
  const unsigned __int16 **v8; // rsi
  const unsigned __int16 *v9; // rdx
  unsigned __int8 v10; // di
  char IsEnabled; // al
  char v12; // r12
  __int64 v13; // rdx
  struct _GUID *v14; // r8
  char v15; // r15
  bool v16; // r12
  const wchar_t **v17; // rsi
  const wchar_t **v18; // rsi
  char v20; // [rsp+30h] [rbp-D0h]
  LPCWSTR lpStringSource; // [rsp+38h] [rbp-C8h] BYREF
  const wchar_t *v22; // [rsp+40h] [rbp-C0h] BYREF
  __int16 v23; // [rsp+48h] [rbp-B8h]
  const wchar_t *v24; // [rsp+50h] [rbp-B0h]
  __int16 v25; // [rsp+58h] [rbp-A8h]
  const wchar_t *v26; // [rsp+60h] [rbp-A0h]
  __int16 v27; // [rsp+68h] [rbp-98h]
  const wchar_t *v28; // [rsp+70h] [rbp-90h]
  __int16 v29; // [rsp+78h] [rbp-88h]
  const wchar_t *v30; // [rsp+80h] [rbp-80h]
  __int16 v31; // [rsp+88h] [rbp-78h]
  const wchar_t *v32; // [rsp+90h] [rbp-70h]
  __int16 v33; // [rsp+98h] [rbp-68h]
  const wchar_t *v34; // [rsp+A0h] [rbp-60h]
  __int16 v35; // [rsp+A8h] [rbp-58h]
  const wchar_t *v36; // [rsp+B0h] [rbp-50h]
  __int16 v37; // [rsp+B8h] [rbp-48h]
  const wchar_t *v38; // [rsp+C0h] [rbp-40h]
  __int16 v39; // [rsp+C8h] [rbp-38h]
  const wchar_t *v40; // [rsp+D0h] [rbp-30h]
  __int16 v41; // [rsp+D8h] [rbp-28h]
  const wchar_t *v42; // [rsp+E0h] [rbp-20h]
  __int16 v43; // [rsp+E8h] [rbp-18h]
  const wchar_t *v44; // [rsp+F0h] [rbp-10h]
  __int16 v45; // [rsp+F8h] [rbp-8h]
  const wchar_t *v46; // [rsp+100h] [rbp+0h]
  __int16 v47; // [rsp+108h] [rbp+8h]
  const wchar_t *v48; // [rsp+110h] [rbp+10h] BYREF
  __int16 v49; // [rsp+118h] [rbp+18h]
  const wchar_t *v50; // [rsp+120h] [rbp+20h]
  __int16 v51; // [rsp+128h] [rbp+28h]
  const wchar_t *v52; // [rsp+130h] [rbp+30h]
  __int16 v53; // [rsp+138h] [rbp+38h]
  const wchar_t *v54; // [rsp+140h] [rbp+40h]
  __int16 v55; // [rsp+148h] [rbp+48h]
  const wchar_t *v56; // [rsp+150h] [rbp+50h]
  __int16 v57; // [rsp+158h] [rbp+58h]
  const wchar_t *v58; // [rsp+160h] [rbp+60h]
  __int16 v59; // [rsp+168h] [rbp+68h]
  const wchar_t *v60; // [rsp+170h] [rbp+70h]
  __int16 v61; // [rsp+178h] [rbp+78h]
  const wchar_t *v62; // [rsp+180h] [rbp+80h]
  __int16 v63; // [rsp+188h] [rbp+88h]
  const wchar_t *v64; // [rsp+190h] [rbp+90h]
  __int16 v65; // [rsp+198h] [rbp+98h]
  const wchar_t *v66; // [rsp+1A0h] [rbp+A0h]
  __int16 v67; // [rsp+1A8h] [rbp+A8h]
  const wchar_t *v68; // [rsp+1B0h] [rbp+B0h]
  __int16 v69; // [rsp+1B8h] [rbp+B8h]
  const wchar_t *v70; // [rsp+1C0h] [rbp+C0h]
  __int16 v71; // [rsp+1C8h] [rbp+C8h]
  const wchar_t *v72; // [rsp+1D0h] [rbp+D0h]
  __int16 v73; // [rsp+1D8h] [rbp+D8h]
  const wchar_t *v74; // [rsp+1E0h] [rbp+E0h]
  __int16 v75; // [rsp+1E8h] [rbp+E8h]
  __int128 Buf1; // [rsp+1F0h] [rbp+F0h] BYREF

  *a3 = 0;
  v5 = (PiiSafeFolderList *)wil::details::static_lazy<PiiSafeFolderList>::get(
                              a1,
                              _lambda_8a5fbf835690efcf02570e7e9326c5fe_::_lambda_invoker_cdecl_);
  if ( !v5 )
    return (char)v5;
  v6 = (const unsigned __int16 **)PiiSafeFolderList::ReturnMatchingKnownFolder(v5, *a2);
  v8 = v6;
  if ( !v6 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_58459845>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_58459845>::GetImpl'::`2'::impl) )
      LOBYTE(v5) = PiiSafeShellitemParsingNameHelpers::GetDriveOrUncRootLocation(
                     *(PiiSafeShellitemParsingNameHelpers **)a2,
                     v9);
    else
      LOBYTE(v5) = 1;
    return (char)v5;
  }
  v10 = PiiSafeShellitemParsingNameProperties::CalculatePathDepth(v7, *v6, 0);
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_56275225>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56275225>::GetImpl'::`2'::impl);
  v12 = 11;
  if ( *((_BYTE *)v8 + 8) != 11 && (!IsEnabled || *((_BYTE *)v8 + 8) != 16) )
  {
    *a3 = v10;
    LOBYTE(v5) = *((_BYTE *)v8 + 8);
    return (char)v5;
  }
  v13 = -1;
  do
    ++v13;
  while ( (*v8)[v13] );
  details::safemake_cotaskmem_string_nothrow(&lpStringSource, &(*a2)[v13]);
  if ( !lpStringSource )
    goto LABEL_34;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56275225>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56275225>::GetImpl'::`2'::impl) )
  {
    v22 = L"\\Desktop";
    v23 = 3073;
    v24 = L"\\Downloads";
    v25 = 3585;
    v26 = L"\\Documents";
    v27 = 3329;
    v28 = L"\\Pictures\\Camera Roll";
    v29 = 3842;
    v30 = L"\\Pictures\\Screenshots";
    v31 = 5122;
    v32 = L"\\Pictures";
    v33 = 4097;
    v34 = L"\\Videos";
    v35 = 4609;
    v36 = L"\\Music";
    v37 = 4353;
    v38 = L"\\3D Objects";
    v39 = 4865;
    v40 = L"\\Onedrive -";
    v41 = 17921;
    v42 = L"\\Google Drive";
    v43 = 23041;
    v44 = L"\\Dropbox";
    v45 = 20481;
    v46 = L"\\Sharepoint";
    v47 = 25601;
    v18 = &v22;
    while ( (unsigned int)PathComparePaths(*v18, lpStringSource) == 1 )
    {
      v18 += 2;
      if ( v18 == &v48 )
        goto LABEL_34;
    }
    v10 += *((_BYTE *)v18 + 8);
    v12 = *((_BYTE *)v18 + 9);
LABEL_34:
    *a3 = v10;
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&lpStringSource);
    LOBYTE(v5) = v12;
    return (char)v5;
  }
  v48 = L"\\Desktop";
  v49 = 3073;
  v50 = L"\\Downloads";
  v51 = 3585;
  v52 = L"\\Documents";
  v53 = 3329;
  v54 = L"\\Pictures\\Camera Roll";
  v55 = 3842;
  v56 = L"\\Pictures\\Screenshots";
  v57 = 5122;
  v58 = L"\\Pictures\\iCloud Photos\\Photos";
  v59 = 26115;
  v60 = L"\\Pictures";
  v61 = 4097;
  v62 = L"\\Videos";
  v63 = 4609;
  v64 = L"\\Music";
  v65 = 4353;
  v66 = L"\\3D Objects";
  v67 = 4865;
  v68 = L"\\OneDrive -";
  v69 = 17921;
  v15 = 70;
  v70 = L"\\Dropbox";
  v71 = 20481;
  v72 = L"\\Sharepoint";
  v73 = 25601;
  v74 = L"\\iCloudDrive";
  v75 = 25857;
  v20 = *((_BYTE *)v8 + 8);
  Buf1 = 0;
  v16 = (int)PiiSafeShellitemParsingNameHelpers::GetKnownFolderIdFromPath(
               *(PiiSafeShellitemParsingNameHelpers **)a2,
               (const unsigned __int16 *)&Buf1,
               v14) >= 0
     && memcmp_0(&Buf1, &GUID_NULL, 0x10u);
  v17 = &v48;
  while ( *((_BYTE *)v17 + 9) != 70 )
  {
    if ( (unsigned int)PathComparePaths(*v17, lpStringSource) != 1 )
    {
      v15 = *((_BYTE *)v17 + 9);
      goto LABEL_27;
    }
LABEL_24:
    v17 += 2;
    if ( v17 == (const wchar_t **)&Buf1 )
    {
      v15 = v20;
      goto LABEL_28;
    }
  }
  if ( FindStringOrdinal(0x100000u, lpStringSource, -1, *v17, -1, 1) )
    goto LABEL_24;
  if ( v16 )
  {
    v10 += 2;
    v15 = 71;
    goto LABEL_28;
  }
LABEL_27:
  v10 += *((_BYTE *)v17 + 8);
LABEL_28:
  *a3 = v10;
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&lpStringSource);
  LOBYTE(v5) = v15;
  return (char)v5;
}

```

## disassembly

```asm
0x180072f50  mov     [rsp-8+arg_0], rsi
0x180072f55  mov     [rsp-8+arg_18], rdi
0x180072f5a  push    rbp
0x180072f5b  push    r12
0x180072f5d  push    r13
0x180072f5f  push    r14
0x180072f61  push    r15
0x180072f63  lea     rbp, [rsp-110h]
0x180072f6b  sub     rsp, 210h
0x180072f72  mov     rax, cs:__security_cookie
0x180072f79  xor     rax, rsp
0x180072f7c  mov     [rbp+130h+var_30], rax
0x180072f83  mov     r14, r8
0x180072f86  mov     r13, rdx
0x180072f89  xor     r15d, r15d
0x180072f8c  mov     [r8], r15b
0x180072f8f  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_8a5fbf835690efcf02570e7e9326c5fe_@@CA@XZ; _lambda_8a5fbf835690efcf02570e7e9326c5fe_::_lambda_invoker_cdecl_(void)
0x180072f96  call    ?get@?$static_lazy@VPiiSafeFolderList@@@details@wil@@QEAAPEAVPiiSafeFolderList@@P6AXXZ@Z; wil::details::static_lazy<PiiSafeFolderList>::get(void (*)(void))
0x180072f9b  test    rax, rax
0x180072f9e  jz      loc_18007335F
0x180072fa4  mov     rdx, [r13+0]; unsigned __int16 *
0x180072fa8  mov     rcx, rax; this
0x180072fab  call    ?ReturnMatchingKnownFolder@PiiSafeFolderList@@QEAAPEBVPiiSafeKnownFolder@@QEBG@Z; PiiSafeFolderList::ReturnMatchingKnownFolder(ushort const * const)
0x180072fb0  mov     rsi, rax
0x180072fb3  test    rax, rax
0x180072fb6  jnz     short loc_180072FDD
0x180072fb8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_58459845@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_58459845@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_58459845> `wil::Feature<__WilFeatureTraits_Feature_58459845>::GetImpl(void)'::`2'::impl
0x180072fbf  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_58459845@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_58459845>::__private_IsEnabled(void)
0x180072fc4  test    al, al
0x180072fc6  jz      short loc_180072FD6
0x180072fc8  mov     rcx, [r13+0]
0x180072fcc  call    ?GetDriveOrUncRootLocation@PiiSafeShellitemParsingNameHelpers@@YA?AW4ShellitemParsingNameRootLoc@@PEBG@Z; PiiSafeShellitemParsingNameHelpers::GetDriveOrUncRootLocation(ushort const *)
0x180072fd1  jmp     loc_18007335F
0x180072fd6  mov     al, 1
0x180072fd8  jmp     loc_18007335F
0x180072fdd  xor     r8d, r8d; bool
0x180072fe0  mov     rdx, [rax]; unsigned __int16 *
0x180072fe3  call    ?CalculatePathDepth@PiiSafeShellitemParsingNameProperties@@AEAAEPEBG_N@Z; PiiSafeShellitemParsingNameProperties::CalculatePathDepth(ushort const *,bool)
0x180072fe8  mov     dil, al
0x180072feb  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56275225@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56275225@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56275225> `wil::Feature<__WilFeatureTraits_Feature_56275225>::GetImpl(void)'::`2'::impl
0x180072ff2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56275225@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56275225>::__private_IsEnabled(void)
0x180072ff7  mov     r12b, 0Bh
0x180072ffa  cmp     [rsi+8], r12b
0x180072ffe  jz      short loc_180073015
0x180073000  test    al, al
0x180073002  jz      short loc_18007300A
0x180073004  cmp     byte ptr [rsi+8], 10h
0x180073008  jz      short loc_180073015
0x18007300a  mov     [r14], dil
0x18007300d  mov     al, [rsi+8]
0x180073010  jmp     loc_18007335F
0x180073015  mov     rax, [rsi]
0x180073018  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18007301c  inc     rdx
0x18007301f  cmp     [rax+rdx*2], r15w
0x180073024  jnz     short loc_18007301C
0x180073026  mov     rax, [r13+0]
0x18007302a  lea     rdx, [rax+rdx*2]
0x18007302e  lea     rcx, [rsp+230h+lpStringSource]
0x180073033  call    details__safemake_cotaskmem_string_nothrow
0x180073038  nop
0x180073039  cmp     [rsp+230h+lpStringSource], r15
0x18007303e  jz      loc_18007334F
0x180073044  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56275225@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56275225@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56275225> `wil::Feature<__WilFeatureTraits_Feature_56275225>::GetImpl(void)'::`2'::impl
0x18007304b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56275225@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56275225>::__private_IsEnabled(void)
0x180073050  test    al, al
0x180073052  lea     rax, aDesktop; "\\Desktop"
0x180073059  jz      loc_180073242
0x18007305f  mov     [rbp+130h+var_120], rax
0x180073063  mov     [rbp+130h+var_118], 0C01h
0x180073069  lea     rax, aDownloads; "\\Downloads"
0x180073070  mov     [rbp+130h+var_110], rax
0x180073074  mov     [rbp+130h+var_108], 0E01h
0x18007307a  lea     rax, aDocuments; "\\Documents"
0x180073081  mov     [rbp+130h+var_100], rax
0x180073085  mov     [rbp+130h+var_F8], 0D01h
0x18007308b  lea     rax, aPicturesCamera; "\\Pictures\\Camera Roll"
0x180073092  mov     [rbp+130h+var_F0], rax
0x180073096  mov     [rbp+130h+var_E8], 0F02h
0x18007309c  lea     rax, aPicturesScreen; "\\Pictures\\Screenshots"
0x1800730a3  mov     [rbp+130h+var_E0], rax
0x1800730a7  mov     [rbp+130h+var_D8], 1402h
0x1800730ad  lea     rax, aPicturesIcloud; "\\Pictures\\iCloud Photos\\Photos"
0x1800730b4  mov     [rbp+130h+var_D0], rax
0x1800730b8  mov     [rbp+130h+var_C8], 6603h
0x1800730be  lea     rax, aPictures; "\\Pictures"
0x1800730c5  mov     [rbp+130h+var_C0], rax
0x1800730c9  mov     [rbp+130h+var_B8], 1001h
0x1800730cf  lea     rax, aVideos; "\\Videos"
0x1800730d6  mov     [rbp+130h+var_B0], rax
0x1800730dd  mov     [rbp+130h+var_A8], 1201h
0x1800730e6  lea     rax, aMusic; "\\Music"
0x1800730ed  mov     [rbp+130h+var_A0], rax
0x1800730f4  mov     [rbp+130h+var_98], 1101h
0x1800730fd  lea     rax, a3dObjects; "\\3D Objects"
0x180073104  mov     [rbp+130h+var_90], rax
0x18007310b  mov     [rbp+130h+var_88], 1301h
0x180073114  lea     rax, aOnedrive_0; "\\OneDrive -"
0x18007311b  mov     [rbp+130h+var_80], rax
0x180073122  mov     [rbp+130h+var_78], 4601h
0x18007312b  mov     r15b, 46h ; 'F'
0x18007312e  lea     rax, aDropbox; "\\Dropbox"
0x180073135  mov     [rbp+130h+var_70], rax
0x18007313c  mov     [rbp+130h+var_68], 5001h
0x180073145  lea     rax, aSharepoint; "\\Sharepoint"
0x18007314c  mov     [rbp+130h+var_60], rax
0x180073153  mov     [rbp+130h+var_58], 6401h
0x18007315c  lea     rax, aIclouddrive; "\\iCloudDrive"
0x180073163  mov     [rbp+130h+var_50], rax
0x18007316a  mov     [rbp+130h+var_48], 6501h
0x180073173  mov     al, [rsi+8]
0x180073176  mov     [rsp+230h+var_200], al
0x18007317a  xorps   xmm0, xmm0
0x18007317d  movups  [rbp+130h+Buf1], xmm0
0x180073184  lea     rdx, [rbp+130h+Buf1]; unsigned __int16 *
0x18007318b  mov     rcx, [r13+0]; this
0x18007318f  call    ?GetKnownFolderIdFromPath@PiiSafeShellitemParsingNameHelpers@@YAJPEBGPEAU_GUID@@@Z; PiiSafeShellitemParsingNameHelpers::GetKnownFolderIdFromPath(ushort const *,_GUID *)
0x180073194  test    eax, eax
0x180073196  js      short loc_1800731BA
0x180073198  mov     r8d, 10h; Size
0x18007319e  lea     rdx, GUID_NULL; Buf2
0x1800731a5  lea     rcx, [rbp+130h+Buf1]; Buf1
0x1800731ac  call    memcmp_0
0x1800731b1  test    eax, eax
0x1800731b3  jz      short loc_1800731BA
0x1800731b5  mov     r12b, 1
0x1800731b8  jmp     short loc_1800731BD
0x1800731ba  xor     r12b, r12b
0x1800731bd  lea     rsi, [rbp+130h+var_120]
0x1800731c1  mov     rdx, [rsp+230h+lpStringSource]; lpStringSource
0x1800731c6  cmp     [rsi+9], r15b
0x1800731ca  jnz     short loc_180073200
0x1800731cc  mov     [rsp+230h+bIgnoreCase], 1; bIgnoreCase
0x1800731d4  mov     [rsp+230h+cchValue], 0FFFFFFFFh; cchValue
0x1800731dc  mov     r9, [rsi]; lpStringValue
0x1800731df  or      r8d, 0FFFFFFFFh; cchSource
0x1800731e3  mov     ecx, 100000h; dwFindStringOrdinalFlags
0x1800731e8  call    cs:__imp_FindStringOrdinal
0x1800731ee  test    eax, eax
0x1800731f0  jnz     short loc_18007320E
0x1800731f2  test    r12b, r12b
0x1800731f5  jz      short loc_180073229
0x1800731f7  add     dil, 2
0x1800731fb  mov     r15b, 47h ; 'G'
0x1800731fe  jmp     short loc_18007322D
0x180073200  mov     rcx, [rsi]
0x180073203  call    cs:__imp_PathComparePaths
0x180073209  cmp     eax, 1
0x18007320c  jnz     short loc_180073225
0x18007320e  add     rsi, 10h
0x180073212  lea     rax, [rbp+130h+Buf1]
0x180073219  cmp     rsi, rax
0x18007321c  jnz     short loc_1800731C1
0x18007321e  mov     r15b, [rsp+230h+var_200]
0x180073223  jmp     short loc_18007322D
0x180073225  mov     r15b, [rsi+9]
0x180073229  add     dil, [rsi+8]
0x18007322d  mov     [r14], dil
0x180073230  lea     rcx, [rsp+230h+lpStringSource]; void *
0x180073235  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x18007323a  mov     al, r15b
0x18007323d  jmp     loc_18007335F
0x180073242  mov     [rsp+230h+var_1F0], rax
0x180073247  mov     [rsp+230h+var_1E8], 0C01h
0x18007324e  lea     rax, aDownloads; "\\Downloads"
0x180073255  mov     [rsp+230h+var_1E0], rax
0x18007325a  mov     [rsp+230h+var_1D8], 0E01h
0x180073261  lea     rax, aDocuments; "\\Documents"
0x180073268  mov     [rsp+230h+var_1D0], rax
0x18007326d  mov     [rsp+230h+var_1C8], 0D01h
0x180073274  lea     rax, aPicturesCamera; "\\Pictures\\Camera Roll"
0x18007327b  mov     [rsp+230h+var_1C0], rax
0x180073280  mov     [rsp+230h+var_1B8], 0F02h
0x180073287  lea     rax, aPicturesScreen; "\\Pictures\\Screenshots"
0x18007328e  mov     [rbp+130h+var_1B0], rax
0x180073292  mov     [rbp+130h+var_1A8], 1402h
0x180073298  lea     rax, aPictures; "\\Pictures"
0x18007329f  mov     [rbp+130h+var_1A0], rax
0x1800732a3  mov     [rbp+130h+var_198], 1001h
0x1800732a9  lea     rax, aVideos; "\\Videos"
0x1800732b0  mov     [rbp+130h+var_190], rax
0x1800732b4  mov     [rbp+130h+var_188], 1201h
0x1800732ba  lea     rax, aMusic; "\\Music"
0x1800732c1  mov     [rbp+130h+var_180], rax
0x1800732c5  mov     [rbp+130h+var_178], 1101h
0x1800732cb  lea     rax, a3dObjects; "\\3D Objects"
0x1800732d2  mov     [rbp+130h+var_170], rax
0x1800732d6  mov     [rbp+130h+var_168], 1301h
0x1800732dc  lea     rax, aOnedrive; "\\Onedrive -"
0x1800732e3  mov     [rbp+130h+var_160], rax
0x1800732e7  mov     [rbp+130h+var_158], 4601h
0x1800732ed  lea     rax, aGoogleDrive; "\\Google Drive"
0x1800732f4  mov     [rbp+130h+var_150], rax
0x1800732f8  mov     [rbp+130h+var_148], 5A01h
0x1800732fe  lea     rax, aDropbox; "\\Dropbox"
0x180073305  mov     [rbp+130h+var_140], rax
0x180073309  mov     [rbp+130h+var_138], 5001h
0x18007330f  lea     rax, aSharepoint; "\\Sharepoint"
0x180073316  mov     [rbp+130h+var_130], rax
0x18007331a  mov     [rbp+130h+var_128], 6401h
0x180073320  lea     rsi, [rsp+230h+var_1F0]
0x180073325  mov     rdx, [rsp+230h+lpStringSource]
0x18007332a  mov     rcx, [rsi]
0x18007332d  call    cs:__imp_PathComparePaths
0x180073333  cmp     eax, 1
0x180073336  jnz     short loc_180073347
0x180073338  add     rsi, 10h
0x18007333c  lea     rax, [rbp+130h+var_120]
0x180073340  cmp     rsi, rax
0x180073343  jnz     short loc_180073325
0x180073345  jmp     short loc_18007334F
0x180073347  add     dil, [rsi+8]
0x18007334b  mov     r12b, [rsi+9]
0x18007334f  mov     [r14], dil
0x180073352  lea     rcx, [rsp+230h+lpStringSource]; void *
0x180073357  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x18007335c  mov     al, r12b
0x18007335f  mov     rcx, [rbp+130h+var_30]
0x180073366  xor     rcx, rsp; StackCookie
0x180073369  call    __security_check_cookie
0x18007336e  lea     r11, [rsp+230h+var_20]
0x180073376  mov     rsi, [r11+30h]
0x18007337a  mov     rdi, [r11+48h]
0x18007337e  mov     rsp, r11
0x180073381  pop     r15
0x180073383  pop     r14
0x180073385  pop     r13
0x180073387  pop     r12
0x180073389  pop     rbp
0x18007338a  retn
```
