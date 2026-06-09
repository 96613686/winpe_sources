# PiiSafeShellitemParsingNameProperties::FindLocalDiskLocation(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> const &,uchar &)

- ea: `0x180014328`
- end: `0x18001476a`
- name: `?FindLocalDiskLocation@PiiSafeShellitemParsingNameProperties@@AEAA?AW4ShellitemParsingNameRootLoc@@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@AEAE@Z`
- size: `1090`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001b1f8`

## callees

- `0x1800061e8`
- `0x180006900`
- `0x1800133ec`
- `0x180014328`
- `0x180018370`
- `0x180018c64`
- `0x18001cf80`
- `0x180021424`
- `0x1800214d8`
- `0x1800219dc`
- `0x18004fb0c`

## import_xrefs

- `SHELL32!__imp_PathComparePaths` at `0x1800145db`
- `SHELL32!__imp_PathComparePaths` at `0x180014706`
- `SHELL32!__imp_PathComparePaths` at `0x1800145db`
- `SHELL32!__imp_PathComparePaths` at `0x180014706`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x1800145c0`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x1800145c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001460d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014730`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001460d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014730`

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
  unsigned __int8 v9; // di
  char IsEnabled; // al
  char v11; // r12
  __int64 v12; // rdx
  struct _GUID *v13; // r8
  char v14; // r15
  bool v15; // r12
  const wchar_t **v16; // rsi
  const wchar_t **v17; // rsi
  char v19; // [rsp+30h] [rbp-D0h]
  LPCWSTR lpStringSource; // [rsp+38h] [rbp-C8h] BYREF
  const wchar_t *v21; // [rsp+40h] [rbp-C0h] BYREF
  __int16 v22; // [rsp+48h] [rbp-B8h]
  const wchar_t *v23; // [rsp+50h] [rbp-B0h]
  __int16 v24; // [rsp+58h] [rbp-A8h]
  const wchar_t *v25; // [rsp+60h] [rbp-A0h]
  __int16 v26; // [rsp+68h] [rbp-98h]
  const wchar_t *v27; // [rsp+70h] [rbp-90h]
  __int16 v28; // [rsp+78h] [rbp-88h]
  const wchar_t *v29; // [rsp+80h] [rbp-80h]
  __int16 v30; // [rsp+88h] [rbp-78h]
  const wchar_t *v31; // [rsp+90h] [rbp-70h]
  __int16 v32; // [rsp+98h] [rbp-68h]
  const wchar_t *v33; // [rsp+A0h] [rbp-60h]
  __int16 v34; // [rsp+A8h] [rbp-58h]
  const wchar_t *v35; // [rsp+B0h] [rbp-50h]
  __int16 v36; // [rsp+B8h] [rbp-48h]
  const wchar_t *v37; // [rsp+C0h] [rbp-40h]
  __int16 v38; // [rsp+C8h] [rbp-38h]
  const wchar_t *v39; // [rsp+D0h] [rbp-30h]
  __int16 v40; // [rsp+D8h] [rbp-28h]
  const wchar_t *v41; // [rsp+E0h] [rbp-20h]
  __int16 v42; // [rsp+E8h] [rbp-18h]
  const wchar_t *v43; // [rsp+F0h] [rbp-10h]
  __int16 v44; // [rsp+F8h] [rbp-8h]
  const wchar_t *v45; // [rsp+100h] [rbp+0h]
  __int16 v46; // [rsp+108h] [rbp+8h]
  const wchar_t *v47; // [rsp+110h] [rbp+10h] BYREF
  __int16 v48; // [rsp+118h] [rbp+18h]
  const wchar_t *v49; // [rsp+120h] [rbp+20h]
  __int16 v50; // [rsp+128h] [rbp+28h]
  const wchar_t *v51; // [rsp+130h] [rbp+30h]
  __int16 v52; // [rsp+138h] [rbp+38h]
  const wchar_t *v53; // [rsp+140h] [rbp+40h]
  __int16 v54; // [rsp+148h] [rbp+48h]
  const wchar_t *v55; // [rsp+150h] [rbp+50h]
  __int16 v56; // [rsp+158h] [rbp+58h]
  const wchar_t *v57; // [rsp+160h] [rbp+60h]
  __int16 v58; // [rsp+168h] [rbp+68h]
  const wchar_t *v59; // [rsp+170h] [rbp+70h]
  __int16 v60; // [rsp+178h] [rbp+78h]
  const wchar_t *v61; // [rsp+180h] [rbp+80h]
  __int16 v62; // [rsp+188h] [rbp+88h]
  const wchar_t *v63; // [rsp+190h] [rbp+90h]
  __int16 v64; // [rsp+198h] [rbp+98h]
  const wchar_t *v65; // [rsp+1A0h] [rbp+A0h]
  __int16 v66; // [rsp+1A8h] [rbp+A8h]
  const wchar_t *v67; // [rsp+1B0h] [rbp+B0h]
  __int16 v68; // [rsp+1B8h] [rbp+B8h]
  const wchar_t *v69; // [rsp+1C0h] [rbp+C0h]
  __int16 v70; // [rsp+1C8h] [rbp+C8h]
  const wchar_t *v71; // [rsp+1D0h] [rbp+D0h]
  __int16 v72; // [rsp+1D8h] [rbp+D8h]
  const wchar_t *v73; // [rsp+1E0h] [rbp+E0h]
  __int16 v74; // [rsp+1E8h] [rbp+E8h]
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
      LOBYTE(v5) = PiiSafeShellitemParsingNameHelpers::GetDriveOrUncRootLocation(*a2);
    else
      LOBYTE(v5) = 1;
    return (char)v5;
  }
  v9 = PiiSafeShellitemParsingNameProperties::CalculatePathDepth(v7, *v6, 0);
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_56275225>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56275225>::GetImpl'::`2'::impl);
  v11 = 11;
  if ( *((_BYTE *)v8 + 8) != 11 && (!IsEnabled || *((_BYTE *)v8 + 8) != 16) )
  {
    *a3 = v9;
    LOBYTE(v5) = *((_BYTE *)v8 + 8);
    return (char)v5;
  }
  v12 = -1;
  do
    ++v12;
  while ( (*v8)[v12] );
  details::safemake_cotaskmem_string_nothrow(&lpStringSource, &(*a2)[v12]);
  if ( !lpStringSource )
  {
    *a3 = v9;
    goto LABEL_36;
  }
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56275225>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56275225>::GetImpl'::`2'::impl) )
  {
    v21 = L"\\Desktop";
    v22 = 3073;
    v23 = L"\\Downloads";
    v24 = 3585;
    v25 = L"\\Documents";
    v26 = 3329;
    v27 = L"\\Pictures\\Camera Roll";
    v28 = 3842;
    v29 = L"\\Pictures\\Screenshots";
    v30 = 5122;
    v31 = L"\\Pictures";
    v32 = 4097;
    v33 = L"\\Videos";
    v34 = 4609;
    v35 = L"\\Music";
    v36 = 4353;
    v37 = L"\\3D Objects";
    v38 = 4865;
    v39 = L"\\Onedrive -";
    v40 = 17921;
    v41 = L"\\Google Drive";
    v42 = 23041;
    v43 = L"\\Dropbox";
    v44 = 20481;
    v45 = L"\\Sharepoint";
    v46 = 25601;
    v17 = &v21;
    while ( (unsigned int)PathComparePaths(*v17, lpStringSource) == 1 )
    {
      v17 += 2;
      if ( v17 == &v47 )
        goto LABEL_34;
    }
    v9 += *((_BYTE *)v17 + 8);
    v11 = *((_BYTE *)v17 + 9);
LABEL_34:
    *a3 = v9;
    CoTaskMemFree((LPVOID)lpStringSource);
LABEL_36:
    LOBYTE(v5) = v11;
    return (char)v5;
  }
  v47 = L"\\Desktop";
  v48 = 3073;
  v49 = L"\\Downloads";
  v50 = 3585;
  v51 = L"\\Documents";
  v52 = 3329;
  v53 = L"\\Pictures\\Camera Roll";
  v54 = 3842;
  v55 = L"\\Pictures\\Screenshots";
  v56 = 5122;
  v57 = L"\\Pictures\\iCloud Photos\\Photos";
  v58 = 26115;
  v59 = L"\\Pictures";
  v60 = 4097;
  v61 = L"\\Videos";
  v62 = 4609;
  v63 = L"\\Music";
  v64 = 4353;
  v65 = L"\\3D Objects";
  v66 = 4865;
  v67 = L"\\OneDrive -";
  v68 = 17921;
  v14 = 70;
  v69 = L"\\Dropbox";
  v70 = 20481;
  v71 = L"\\Sharepoint";
  v72 = 25601;
  v73 = L"\\iCloudDrive";
  v74 = 25857;
  v19 = *((_BYTE *)v8 + 8);
  Buf1 = 0;
  v15 = (int)PiiSafeShellitemParsingNameHelpers::GetKnownFolderIdFromPath(
               *(PiiSafeShellitemParsingNameHelpers **)a2,
               (const unsigned __int16 *)&Buf1,
               v13) >= 0
     && memcmp_0(&Buf1, &GUID_NULL, 0x10u);
  v16 = &v47;
  while ( *((_BYTE *)v16 + 9) != 70 )
  {
    if ( (unsigned int)PathComparePaths(*v16, lpStringSource) != 1 )
    {
      v14 = *((_BYTE *)v16 + 9);
      goto LABEL_27;
    }
LABEL_24:
    v16 += 2;
    if ( v16 == (const wchar_t **)&Buf1 )
    {
      v14 = v19;
      goto LABEL_28;
    }
  }
  if ( FindStringOrdinal(0x100000u, lpStringSource, -1, *v16, -1, 1) )
    goto LABEL_24;
  if ( v15 )
  {
    v9 += 2;
    v14 = 71;
    goto LABEL_28;
  }
LABEL_27:
  v9 += *((_BYTE *)v16 + 8);
LABEL_28:
  *a3 = v9;
  CoTaskMemFree((LPVOID)lpStringSource);
  LOBYTE(v5) = v14;
  return (char)v5;
}

```

## disassembly

```asm
0x180014328  mov     [rsp-8+arg_0], rsi
0x18001432d  mov     [rsp-8+arg_18], rdi
0x180014332  push    rbp
0x180014333  push    r12
0x180014335  push    r13
0x180014337  push    r14
0x180014339  push    r15
0x18001433b  lea     rbp, [rsp-110h]
0x180014343  sub     rsp, 210h
0x18001434a  mov     rax, cs:__security_cookie
0x180014351  xor     rax, rsp
0x180014354  mov     [rbp+130h+var_30], rax
0x18001435b  mov     r14, r8
0x18001435e  mov     r13, rdx
0x180014361  xor     r15d, r15d
0x180014364  mov     [r8], r15b
0x180014367  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_8a5fbf835690efcf02570e7e9326c5fe_@@CA@XZ; _lambda_8a5fbf835690efcf02570e7e9326c5fe_::_lambda_invoker_cdecl_(void)
0x18001436e  call    ?get@?$static_lazy@VPiiSafeFolderList@@@details@wil@@QEAAPEAVPiiSafeFolderList@@P6AXXZ@Z; wil::details::static_lazy<PiiSafeFolderList>::get(void (*)(void))
0x180014373  test    rax, rax
0x180014376  jz      loc_18001473E
0x18001437c  mov     rdx, [r13+0]; unsigned __int16 *
0x180014380  mov     rcx, rax; this
0x180014383  call    ?ReturnMatchingKnownFolder@PiiSafeFolderList@@QEAAPEBVPiiSafeKnownFolder@@QEBG@Z; PiiSafeFolderList::ReturnMatchingKnownFolder(ushort const * const)
0x180014388  mov     rsi, rax
0x18001438b  test    rax, rax
0x18001438e  jnz     short loc_1800143B5
0x180014390  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_58459845@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_58459845@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_58459845> `wil::Feature<__WilFeatureTraits_Feature_58459845>::GetImpl(void)'::`2'::impl
0x180014397  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_58459845@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_58459845>::__private_IsEnabled(void)
0x18001439c  test    al, al
0x18001439e  jz      short loc_1800143AE
0x1800143a0  mov     rcx, [r13+0]
0x1800143a4  call    ?GetDriveOrUncRootLocation@PiiSafeShellitemParsingNameHelpers@@YA?AW4ShellitemParsingNameRootLoc@@PEBG@Z; PiiSafeShellitemParsingNameHelpers::GetDriveOrUncRootLocation(ushort const *)
0x1800143a9  jmp     loc_18001473E
0x1800143ae  mov     al, 1
0x1800143b0  jmp     loc_18001473E
0x1800143b5  xor     r8d, r8d; bool
0x1800143b8  mov     rdx, [rax]; unsigned __int16 *
0x1800143bb  call    ?CalculatePathDepth@PiiSafeShellitemParsingNameProperties@@AEAAEPEBG_N@Z; PiiSafeShellitemParsingNameProperties::CalculatePathDepth(ushort const *,bool)
0x1800143c0  mov     dil, al
0x1800143c3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56275225@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56275225@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56275225> `wil::Feature<__WilFeatureTraits_Feature_56275225>::GetImpl(void)'::`2'::impl
0x1800143ca  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56275225@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56275225>::__private_IsEnabled(void)
0x1800143cf  mov     r12b, 0Bh
0x1800143d2  cmp     [rsi+8], r12b
0x1800143d6  jz      short loc_1800143ED
0x1800143d8  test    al, al
0x1800143da  jz      short loc_1800143E2
0x1800143dc  cmp     byte ptr [rsi+8], 10h
0x1800143e0  jz      short loc_1800143ED
0x1800143e2  mov     [r14], dil
0x1800143e5  mov     al, [rsi+8]
0x1800143e8  jmp     loc_18001473E
0x1800143ed  mov     rax, [rsi]
0x1800143f0  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800143f4  inc     rdx
0x1800143f7  cmp     [rax+rdx*2], r15w
0x1800143fc  jnz     short loc_1800143F4
0x1800143fe  mov     rax, [r13+0]
0x180014402  lea     rdx, [rax+rdx*2]
0x180014406  lea     rcx, [rsp+230h+lpStringSource]
0x18001440b  call    details__safemake_cotaskmem_string_nothrow
0x180014410  nop
0x180014411  cmp     [rsp+230h+lpStringSource], r15
0x180014416  jz      loc_180014738
0x18001441c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56275225@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56275225@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56275225> `wil::Feature<__WilFeatureTraits_Feature_56275225>::GetImpl(void)'::`2'::impl
0x180014423  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56275225@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56275225>::__private_IsEnabled(void)
0x180014428  test    al, al
0x18001442a  lea     rax, aDesktop; "\\Desktop"
0x180014431  jz      loc_18001461B
0x180014437  mov     [rbp+130h+var_120], rax
0x18001443b  mov     [rbp+130h+var_118], 0C01h
0x180014441  lea     rax, aDownloads; "\\Downloads"
0x180014448  mov     [rbp+130h+var_110], rax
0x18001444c  mov     [rbp+130h+var_108], 0E01h
0x180014452  lea     rax, aDocuments; "\\Documents"
0x180014459  mov     [rbp+130h+var_100], rax
0x18001445d  mov     [rbp+130h+var_F8], 0D01h
0x180014463  lea     rax, aPicturesCamera; "\\Pictures\\Camera Roll"
0x18001446a  mov     [rbp+130h+var_F0], rax
0x18001446e  mov     [rbp+130h+var_E8], 0F02h
0x180014474  lea     rax, aPicturesScreen; "\\Pictures\\Screenshots"
0x18001447b  mov     [rbp+130h+var_E0], rax
0x18001447f  mov     [rbp+130h+var_D8], 1402h
0x180014485  lea     rax, aPicturesIcloud; "\\Pictures\\iCloud Photos\\Photos"
0x18001448c  mov     [rbp+130h+var_D0], rax
0x180014490  mov     [rbp+130h+var_C8], 6603h
0x180014496  lea     rax, aPictures; "\\Pictures"
0x18001449d  mov     [rbp+130h+var_C0], rax
0x1800144a1  mov     [rbp+130h+var_B8], 1001h
0x1800144a7  lea     rax, aVideos; "\\Videos"
0x1800144ae  mov     [rbp+130h+var_B0], rax
0x1800144b5  mov     [rbp+130h+var_A8], 1201h
0x1800144be  lea     rax, aMusic; "\\Music"
0x1800144c5  mov     [rbp+130h+var_A0], rax
0x1800144cc  mov     [rbp+130h+var_98], 1101h
0x1800144d5  lea     rax, a3dObjects; "\\3D Objects"
0x1800144dc  mov     [rbp+130h+var_90], rax
0x1800144e3  mov     [rbp+130h+var_88], 1301h
0x1800144ec  lea     rax, aOnedrive_0; "\\OneDrive -"
0x1800144f3  mov     [rbp+130h+var_80], rax
0x1800144fa  mov     [rbp+130h+var_78], 4601h
0x180014503  mov     r15b, 46h ; 'F'
0x180014506  lea     rax, aDropbox; "\\Dropbox"
0x18001450d  mov     [rbp+130h+var_70], rax
0x180014514  mov     [rbp+130h+var_68], 5001h
0x18001451d  lea     rax, aSharepoint; "\\Sharepoint"
0x180014524  mov     [rbp+130h+var_60], rax
0x18001452b  mov     [rbp+130h+var_58], 6401h
0x180014534  lea     rax, aIclouddrive; "\\iCloudDrive"
0x18001453b  mov     [rbp+130h+var_50], rax
0x180014542  mov     [rbp+130h+var_48], 6501h
0x18001454b  mov     al, [rsi+8]
0x18001454e  mov     [rsp+230h+var_200], al
0x180014552  xorps   xmm0, xmm0
0x180014555  movups  [rbp+130h+Buf1], xmm0
0x18001455c  lea     rdx, [rbp+130h+Buf1]; unsigned __int16 *
0x180014563  mov     rcx, [r13+0]; this
0x180014567  call    ?GetKnownFolderIdFromPath@PiiSafeShellitemParsingNameHelpers@@YAJPEBGPEAU_GUID@@@Z; PiiSafeShellitemParsingNameHelpers::GetKnownFolderIdFromPath(ushort const *,_GUID *)
0x18001456c  test    eax, eax
0x18001456e  js      short loc_180014592
0x180014570  mov     r8d, 10h; Size
0x180014576  lea     rdx, GUID_NULL; Buf2
0x18001457d  lea     rcx, [rbp+130h+Buf1]; Buf1
0x180014584  call    memcmp_0
0x180014589  test    eax, eax
0x18001458b  jz      short loc_180014592
0x18001458d  mov     r12b, 1
0x180014590  jmp     short loc_180014595
0x180014592  xor     r12b, r12b
0x180014595  lea     rsi, [rbp+130h+var_120]
0x180014599  mov     rdx, [rsp+230h+lpStringSource]; lpStringSource
0x18001459e  cmp     [rsi+9], r15b
0x1800145a2  jnz     short loc_1800145D8
0x1800145a4  mov     [rsp+230h+bIgnoreCase], 1; bIgnoreCase
0x1800145ac  mov     [rsp+230h+cchValue], 0FFFFFFFFh; cchValue
0x1800145b4  mov     r9, [rsi]; lpStringValue
0x1800145b7  or      r8d, 0FFFFFFFFh; cchSource
0x1800145bb  mov     ecx, 100000h; dwFindStringOrdinalFlags
0x1800145c0  call    cs:__imp_FindStringOrdinal
0x1800145c6  test    eax, eax
0x1800145c8  jnz     short loc_1800145E6
0x1800145ca  test    r12b, r12b
0x1800145cd  jz      short loc_180014601
0x1800145cf  add     dil, 2
0x1800145d3  mov     r15b, 47h ; 'G'
0x1800145d6  jmp     short loc_180014605
0x1800145d8  mov     rcx, [rsi]
0x1800145db  call    cs:__imp_PathComparePaths
0x1800145e1  cmp     eax, 1
0x1800145e4  jnz     short loc_1800145FD
0x1800145e6  add     rsi, 10h
0x1800145ea  lea     rax, [rbp+130h+Buf1]
0x1800145f1  cmp     rsi, rax
0x1800145f4  jnz     short loc_180014599
0x1800145f6  mov     r15b, [rsp+230h+var_200]
0x1800145fb  jmp     short loc_180014605
0x1800145fd  mov     r15b, [rsi+9]
0x180014601  add     dil, [rsi+8]
0x180014605  mov     [r14], dil
0x180014608  mov     rcx, [rsp+230h+lpStringSource]; pv
0x18001460d  call    cs:__imp_CoTaskMemFree
0x180014613  mov     al, r15b
0x180014616  jmp     loc_18001473E
0x18001461b  mov     [rsp+230h+var_1F0], rax
0x180014620  mov     [rsp+230h+var_1E8], 0C01h
0x180014627  lea     rax, aDownloads; "\\Downloads"
0x18001462e  mov     [rsp+230h+var_1E0], rax
0x180014633  mov     [rsp+230h+var_1D8], 0E01h
0x18001463a  lea     rax, aDocuments; "\\Documents"
0x180014641  mov     [rsp+230h+var_1D0], rax
0x180014646  mov     [rsp+230h+var_1C8], 0D01h
0x18001464d  lea     rax, aPicturesCamera; "\\Pictures\\Camera Roll"
0x180014654  mov     [rsp+230h+var_1C0], rax
0x180014659  mov     [rsp+230h+var_1B8], 0F02h
0x180014660  lea     rax, aPicturesScreen; "\\Pictures\\Screenshots"
0x180014667  mov     [rbp+130h+var_1B0], rax
0x18001466b  mov     [rbp+130h+var_1A8], 1402h
0x180014671  lea     rax, aPictures; "\\Pictures"
0x180014678  mov     [rbp+130h+var_1A0], rax
0x18001467c  mov     [rbp+130h+var_198], 1001h
0x180014682  lea     rax, aVideos; "\\Videos"
0x180014689  mov     [rbp+130h+var_190], rax
0x18001468d  mov     [rbp+130h+var_188], 1201h
0x180014693  lea     rax, aMusic; "\\Music"
0x18001469a  mov     [rbp+130h+var_180], rax
0x18001469e  mov     [rbp+130h+var_178], 1101h
0x1800146a4  lea     rax, a3dObjects; "\\3D Objects"
0x1800146ab  mov     [rbp+130h+var_170], rax
0x1800146af  mov     [rbp+130h+var_168], 1301h
0x1800146b5  lea     rax, aOnedrive; "\\Onedrive -"
0x1800146bc  mov     [rbp+130h+var_160], rax
0x1800146c0  mov     [rbp+130h+var_158], 4601h
0x1800146c6  lea     rax, aGoogleDrive; "\\Google Drive"
0x1800146cd  mov     [rbp+130h+var_150], rax
0x1800146d1  mov     [rbp+130h+var_148], 5A01h
0x1800146d7  lea     rax, aDropbox; "\\Dropbox"
0x1800146de  mov     [rbp+130h+var_140], rax
0x1800146e2  mov     [rbp+130h+var_138], 5001h
0x1800146e8  lea     rax, aSharepoint; "\\Sharepoint"
0x1800146ef  mov     [rbp+130h+var_130], rax
0x1800146f3  mov     [rbp+130h+var_128], 6401h
0x1800146f9  lea     rsi, [rsp+230h+var_1F0]
0x1800146fe  mov     rdx, [rsp+230h+lpStringSource]
0x180014703  mov     rcx, [rsi]
0x180014706  call    cs:__imp_PathComparePaths
0x18001470c  cmp     eax, 1
0x18001470f  jnz     short loc_180014720
0x180014711  add     rsi, 10h
0x180014715  lea     rax, [rbp+130h+var_120]
0x180014719  cmp     rsi, rax
0x18001471c  jnz     short loc_1800146FE
0x18001471e  jmp     short loc_180014728
0x180014720  add     dil, [rsi+8]
0x180014724  mov     r12b, [rsi+9]
0x180014728  mov     [r14], dil
0x18001472b  mov     rcx, [rsp+230h+lpStringSource]; pv
0x180014730  call    cs:__imp_CoTaskMemFree
0x180014736  jmp     short loc_18001473B
0x180014738  mov     [r14], dil
0x18001473b  mov     al, r12b
0x18001473e  mov     rcx, [rbp+130h+var_30]
0x180014745  xor     rcx, rsp; StackCookie
0x180014748  call    __security_check_cookie
0x18001474d  lea     r11, [rsp+230h+var_20]
0x180014755  mov     rsi, [r11+30h]
0x180014759  mov     rdi, [r11+48h]
0x18001475d  mov     rsp, r11
0x180014760  pop     r15
0x180014762  pop     r14
0x180014764  pop     r13
0x180014766  pop     r12
0x180014768  pop     rbp
0x180014769  retn
```
