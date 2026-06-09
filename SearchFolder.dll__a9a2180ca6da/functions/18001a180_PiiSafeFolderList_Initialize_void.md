# PiiSafeFolderList::Initialize(void)

- ea: `0x18001a180`
- end: `0x18001a85d`
- name: `?Initialize@PiiSafeFolderList@@QEAAXXZ`
- size: `1757`
- prototype: `void __fastcall(PiiSafeFolderList *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180012864`

## callees

- `0x180006900`
- `0x1800076dc`
- `0x1800125f8`
- `0x18001a180`
- `0x180021424`
- `0x180021ad4`

## import_xrefs

- `SHELL32!SHGetKnownFolderPath` at `0x18001a3c0`
- `SHELL32!SHGetKnownFolderPath` at `0x18001a812`
- `SHELL32!SHGetKnownFolderPath` at `0x18001a3c0`
- `SHELL32!SHGetKnownFolderPath` at `0x18001a812`
- `SHELL32!SHParseDisplayName` at `0x18001a59e`
- `SHELL32!SHParseDisplayName` at `0x18001a59e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a5c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a5f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a605`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a5c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a5f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a605`

## pseudocode

```c
void __fastcall PiiSafeFolderList::Initialize(PiiSafeFolderList *this)
{
  unsigned int v2; // r15d
  __int64 v3; // r14
  PWSTR *v4; // rbx
  unsigned int v5; // r14d
  const WCHAR *v6; // rcx
  unsigned int v7; // ebx
  void *v8; // rcx
  void *v9; // rdx
  void *v10; // rcx
  LPVOID v11; // rax
  char *v12; // r13
  signed int v13; // r15d
  __int64 v14; // r14
  LPVOID pv; // [rsp+30h] [rbp-D0h] BYREF
  PCWSTR pszName; // [rsp+40h] [rbp-C0h]
  char v17; // [rsp+48h] [rbp-B8h]
  int v18; // [rsp+49h] [rbp-B7h]
  __int16 v19; // [rsp+4Dh] [rbp-B3h]
  char v20; // [rsp+4Fh] [rbp-B1h]
  const wchar_t *v21; // [rsp+50h] [rbp-B0h]
  char v22; // [rsp+58h] [rbp-A8h]
  int v23; // [rsp+59h] [rbp-A7h]
  __int16 v24; // [rsp+5Dh] [rbp-A3h]
  char v25; // [rsp+5Fh] [rbp-A1h]
  const wchar_t *v26; // [rsp+60h] [rbp-A0h]
  char v27; // [rsp+68h] [rbp-98h]
  int v28; // [rsp+69h] [rbp-97h]
  __int16 v29; // [rsp+6Dh] [rbp-93h]
  char v30; // [rsp+6Fh] [rbp-91h]
  const WCHAR *v31; // [rsp+70h] [rbp-90h]
  char v32; // [rsp+78h] [rbp-88h]
  int v33; // [rsp+79h] [rbp-87h]
  __int16 v34; // [rsp+7Dh] [rbp-83h]
  char v35; // [rsp+7Fh] [rbp-81h]
  const wchar_t *v36; // [rsp+80h] [rbp-80h]
  char v37; // [rsp+88h] [rbp-78h]
  int v38; // [rsp+89h] [rbp-77h]
  __int16 v39; // [rsp+8Dh] [rbp-73h]
  char v40; // [rsp+8Fh] [rbp-71h]
  const wchar_t *v41; // [rsp+90h] [rbp-70h]
  char v42; // [rsp+98h] [rbp-68h]
  int v43; // [rsp+99h] [rbp-67h]
  __int16 v44; // [rsp+9Dh] [rbp-63h]
  char v45; // [rsp+9Fh] [rbp-61h]
  const wchar_t *v46; // [rsp+A0h] [rbp-60h]
  char v47; // [rsp+A8h] [rbp-58h]
  int v48; // [rsp+A9h] [rbp-57h]
  __int16 v49; // [rsp+ADh] [rbp-53h]
  char v50; // [rsp+AFh] [rbp-51h]
  const wchar_t *v51; // [rsp+B0h] [rbp-50h]
  char v52; // [rsp+B8h] [rbp-48h]
  int v53; // [rsp+B9h] [rbp-47h]
  __int16 v54; // [rsp+BDh] [rbp-43h]
  char v55; // [rsp+BFh] [rbp-41h]
  const wchar_t *v56; // [rsp+C0h] [rbp-40h]
  char v57; // [rsp+C8h] [rbp-38h]
  int v58; // [rsp+C9h] [rbp-37h]
  __int16 v59; // [rsp+CDh] [rbp-33h]
  char v60; // [rsp+CFh] [rbp-31h]
  const wchar_t *v61; // [rsp+D0h] [rbp-30h]
  char v62; // [rsp+D8h] [rbp-28h]
  int v63; // [rsp+D9h] [rbp-27h]
  __int16 v64; // [rsp+DDh] [rbp-23h]
  char v65; // [rsp+DFh] [rbp-21h]
  const wchar_t *v66; // [rsp+E0h] [rbp-20h]
  char v67; // [rsp+E8h] [rbp-18h]
  int v68; // [rsp+E9h] [rbp-17h]
  __int16 v69; // [rsp+EDh] [rbp-13h]
  char v70; // [rsp+EFh] [rbp-11h]
  const wchar_t *v71; // [rsp+F0h] [rbp-10h]
  char v72; // [rsp+F8h] [rbp-8h]
  int v73; // [rsp+F9h] [rbp-7h]
  __int16 v74; // [rsp+FDh] [rbp-3h]
  char v75; // [rsp+FFh] [rbp-1h]
  const wchar_t *v76; // [rsp+100h] [rbp+0h]
  char v77; // [rsp+108h] [rbp+8h]
  int v78; // [rsp+109h] [rbp+9h]
  __int16 v79; // [rsp+10Dh] [rbp+Dh]
  char v80; // [rsp+10Fh] [rbp+Fh]
  LPVOID *p_pv; // [rsp+110h] [rbp+10h] BYREF
  LPITEMIDLIST ppidl; // [rsp+118h] [rbp+18h] BYREF
  char v83; // [rsp+120h] [rbp+20h]
  GUID v84; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v85[4]; // [rsp+140h] [rbp+40h]
  GUID v86; // [rsp+144h] [rbp+44h]
  char v87; // [rsp+154h] [rbp+54h]
  GUID v88; // [rsp+158h] [rbp+58h]
  char v89; // [rsp+168h] [rbp+68h]
  GUID v90; // [rsp+16Ch] [rbp+6Ch]
  char v91; // [rsp+17Ch] [rbp+7Ch]
  GUID v92; // [rsp+180h] [rbp+80h]
  char v93; // [rsp+190h] [rbp+90h]
  GUID v94; // [rsp+194h] [rbp+94h]
  char v95; // [rsp+1A4h] [rbp+A4h]
  GUID v96; // [rsp+1A8h] [rbp+A8h]
  char v97; // [rsp+1B8h] [rbp+B8h]
  GUID v98; // [rsp+1BCh] [rbp+BCh]
  char v99; // [rsp+1CCh] [rbp+CCh]
  GUID v100; // [rsp+1D0h] [rbp+D0h]
  char v101; // [rsp+1E0h] [rbp+E0h]
  GUID v102; // [rsp+1E4h] [rbp+E4h]
  char v103; // [rsp+1F4h] [rbp+F4h]
  GUID v104; // [rsp+1F8h] [rbp+F8h]
  char v105; // [rsp+208h] [rbp+108h]
  GUID v106; // [rsp+20Ch] [rbp+10Ch]
  char v107; // [rsp+21Ch] [rbp+11Ch]
  GUID v108; // [rsp+220h] [rbp+120h]
  char v109; // [rsp+230h] [rbp+130h]
  GUID v110; // [rsp+234h] [rbp+134h]
  char v111; // [rsp+244h] [rbp+144h]
  GUID v112; // [rsp+248h] [rbp+148h]
  char v113; // [rsp+258h] [rbp+158h]
  GUID v114; // [rsp+25Ch] [rbp+15Ch]
  char v115; // [rsp+26Ch] [rbp+16Ch]
  GUID v116; // [rsp+270h] [rbp+170h]
  char v117; // [rsp+280h] [rbp+180h]
  GUID v118; // [rsp+284h] [rbp+184h]
  char v119; // [rsp+294h] [rbp+194h]
  GUID v120; // [rsp+298h] [rbp+198h]
  char v121; // [rsp+2A8h] [rbp+1A8h]
  GUID v122; // [rsp+2ACh] [rbp+1ACh]
  char v123; // [rsp+2BCh] [rbp+1BCh]
  GUID v124; // [rsp+2C0h] [rbp+1C0h]
  char v125; // [rsp+2D0h] [rbp+1D0h]
  GUID v126; // [rsp+2D4h] [rbp+1D4h]
  char v127; // [rsp+2E4h] [rbp+1E4h]
  GUID v128; // [rsp+2E8h] [rbp+1E8h]
  char v129; // [rsp+2F8h] [rbp+1F8h]
  GUID v130; // [rsp+2FCh] [rbp+1FCh]
  char v131; // [rsp+30Ch] [rbp+20Ch]

  v85[0] = 51;
  v87 = 52;
  v89 = 53;
  v91 = 54;
  v93 = 50;
  v95 = 11;
  v84 = FOLDERID_SkyDriveDocuments;
  v86 = FOLDERID_SkyDriveCameraRoll;
  v88 = FOLDERID_SkyDrivePictures;
  v90 = FOLDERID_SkyDriveMusic;
  v92 = FOLDERID_OneDrive;
  v94 = FOLDERID_Profile;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56275225>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56275225>::GetImpl'::`2'::impl) )
  {
    v97 = 113;
    v2 = 0;
    v99 = 114;
    v96 = FOLDERID_Fonts;
    v101 = 115;
    v103 = 116;
    v105 = 117;
    v98 = FOLDERID_ProgramFilesX86;
    v107 = 118;
    v109 = 22;
    v111 = 23;
    v100 = FOLDERID_ProgramFilesX64;
    v113 = 24;
    v115 = 25;
    v117 = 26;
    v102 = FOLDERID_ProgramFiles;
    v119 = 27;
    v121 = 28;
    v123 = 29;
    v104 = FOLDERID_Windows;
    v125 = 30;
    v106 = FOLDERID_HomeGroup;
    v108 = FOLDERID_Desktop;
    v110 = FOLDERID_Documents;
    *((_DWORD *)this + 360) = 21;
    v112 = FOLDERID_Downloads;
    v114 = FOLDERID_CameraRoll;
    v116 = FOLDERID_Pictures;
    v118 = FOLDERID_Music;
    v120 = FOLDERID_Videos;
    v122 = FOLDERID_Objects3D;
    v124 = FOLDERID_Screenshots;
    do
    {
      v3 = (int)v2;
      v4 = (PWSTR *)((char *)this + 8 * (int)v2);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        v4 + 130,
        0);
      if ( SHGetKnownFolderPath((GUID *)((char *)&v84 + 20 * (int)v2), 0x4100u, 0, v4 + 130) >= 0 )
        *((_QWORD *)this + 2 * (int)v2) = *((_QWORD *)this + (int)v2 + 130);
      ++v2;
      *((_BYTE *)this + 16 * v3 + 8) = v85[20 * v3];
    }
    while ( v2 < 0x15 );
    v17 = 120;
    pszName = L"shell:::{f874310e-b6b7-47dc-bc84-b9e6b38f5903}";
    v18 = 0;
    v19 = 0;
    v20 = 0;
    v21 = L"shell:::{20D04FE0-3AEA-1069-A2D8-08002B30309D}";
    v23 = 0;
    v24 = 0;
    v25 = 0;
    v26 = L"shell:::{645FF040-5081-101B-9F08-00AA002F954E}";
    v28 = 0;
    v29 = 0;
    v30 = 0;
    v31 = L"shell:::{e88865ea-0e1c-4e20-9aa6-edcd0212c87c}";
    v33 = 0;
    v34 = 0;
    v35 = 0;
    v36 = L"shell:::{1B3EA5DC-B587-4786-B4EF-BD1DC332AEAE}";
    v38 = 0;
    v39 = 0;
    v40 = 0;
    v41 = L"shell:::{031e4825-7b94-4dc3-b131-e946b44c8dd5}";
    v43 = 0;
    v44 = 0;
    v45 = 0;
    v46 = L"shell:::{26EE0668-A00A-44D7-9371-BEB064C98683}";
    v48 = 0;
    v49 = 0;
    v50 = 0;
    v51 = L"shell:::{031E4825-7B94-4DC3-B131-E946B44C8DD5}\\CameraRoll.library-ms";
    v53 = 0;
    v54 = 0;
    v55 = 0;
    v56 = L"shell:::{031E4825-7B94-4DC3-B131-E946B44C8DD5}\\Documents.library-ms";
    v58 = 0;
    v59 = 0;
    v60 = 0;
    v61 = L"shell:::{031E4825-7B94-4DC3-B131-E946B44C8DD5}\\Music.library-ms";
    v63 = 0;
    v64 = 0;
    v65 = 0;
    v66 = L"shell:::{031E4825-7B94-4DC3-B131-E946B44C8DD5}\\Pictures.library-ms";
    v68 = 0;
    v69 = 0;
    v70 = 0;
    v71 = L"shell:::{031E4825-7B94-4DC3-B131-E946B44C8DD5}\\SavedPictures.library-ms";
    v22 = 110;
    v27 = 112;
    v32 = 121;
    v37 = 123;
    v42 = 122;
    v47 = 111;
    v52 = 124;
    v57 = 125;
    v62 = 126;
    v67 = 127;
    v72 = 0x80;
    v73 = 0;
    v5 = 0;
    v74 = 0;
    v75 = 0;
    v76 = L"shell:::{031E4825-7B94-4DC3-B131-E946B44C8DD5}\\Videos.library-ms";
    v78 = 0;
    v79 = 0;
    v80 = 0;
    v77 = -127;
    do
    {
      pv = 0;
      ppidl = 0;
      v83 = 1;
      *((_BYTE *)this + 16 * (int)v5 + 800) = *(&v17 + 16 * (int)v5);
      v6 = (&pszName)[2 * (int)v5];
      p_pv = &pv;
      v7 = (unsigned int)SHParseDisplayName(v6, 0, &ppidl, 0, 0) >> 31;
      wil::details::out_param_t<wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>((__int64)&p_pv);
      if ( (_BYTE)v7 )
      {
        v8 = pv;
        pv = 0;
        if ( v8 )
          CoTaskMemFree(v8);
      }
      v9 = (void *)*((_QWORD *)this + 2 * (int)v5 + 101);
      v10 = 0;
      v11 = pv;
      pv = 0;
      *((_QWORD *)this + 2 * (int)v5 + 101) = v11;
      if ( v9 )
      {
        CoTaskMemFree(v9);
        v10 = pv;
      }
      pv = 0;
      if ( v10 )
        CoTaskMemFree(v10);
      ++v5;
    }
    while ( v5 < 0xD );
  }
  else
  {
    v97 = 110;
    v99 = 111;
    v96 = FOLDERID_ComputerFolder;
    v101 = 112;
    v103 = 113;
    v105 = 114;
    v98 = FOLDERID_ControlPanelFolder;
    v107 = 115;
    v109 = 116;
    v111 = 117;
    v100 = FOLDERID_RecycleBinFolder;
    v113 = 118;
    v115 = 22;
    v117 = 23;
    v102 = FOLDERID_Fonts;
    v119 = 24;
    v121 = 25;
    v123 = 26;
    v104 = FOLDERID_ProgramFilesX86;
    v125 = 27;
    v127 = 28;
    v129 = 29;
    v106 = FOLDERID_ProgramFilesX64;
    v131 = 30;
    v108 = FOLDERID_ProgramFiles;
    v110 = FOLDERID_Windows;
    v112 = FOLDERID_HomeGroup;
    v114 = FOLDERID_Desktop;
    v116 = FOLDERID_Documents;
    v118 = FOLDERID_Downloads;
    v120 = FOLDERID_CameraRoll;
    v122 = FOLDERID_Pictures;
    v124 = FOLDERID_Music;
    v126 = FOLDERID_Videos;
    v128 = FOLDERID_Objects3D;
    v130 = FOLDERID_Screenshots;
    memset_0(this, 0, 0x320u);
    v12 = (char *)this + 1040;
    memset_0((char *)this + 1040, 0, 0x190u);
    v13 = 0;
    *((_DWORD *)this + 360) = 24;
    do
    {
      v14 = v13;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v12[8 * v13],
        0);
      if ( SHGetKnownFolderPath((GUID *)((char *)&v84 + 20 * v13), 0x4100u, 0, (PWSTR *)&v12[8 * v13]) >= 0 )
        *((_QWORD *)this + 2 * v13) = *((_QWORD *)this + v13 + 130);
      ++v13;
      *((_BYTE *)this + 16 * v14 + 8) = v85[20 * v14];
    }
    while ( (unsigned int)v13 < 0x18 );
  }
}

```

## disassembly

```asm
0x18001a180  push    rbp
0x18001a182  push    rbx
0x18001a183  push    rsi
0x18001a184  push    rdi
0x18001a185  push    r12
0x18001a187  push    r13
0x18001a189  push    r14
0x18001a18b  push    r15
0x18001a18d  lea     rbp, [rsp-228h]
0x18001a195  sub     rsp, 328h
0x18001a19c  mov     rax, cs:__security_cookie
0x18001a1a3  xor     rax, rsp
0x18001a1a6  mov     [rbp+260h+var_50], rax
0x18001a1ad  mov     rdi, rcx
0x18001a1b0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56275225@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56275225@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56275225> `wil::Feature<__WilFeatureTraits_Feature_56275225>::GetImpl(void)'::`2'::impl
0x18001a1b7  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56275225@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56275225>::__private_IsEnabled(void)
0x18001a1bc  movups  xmm0, xmmword ptr cs:FOLDERID_SkyDriveDocuments.Data1
0x18001a1c3  xor     r13d, r13d
0x18001a1c6  mov     [rbp+260h+var_220], 33h ; '3'
0x18001a1ca  mov     [rbp+260h+var_20C], 34h ; '4'
0x18001a1ce  mov     [rbp+260h+var_1F8], 35h ; '5'
0x18001a1d2  mov     [rbp+260h+var_1E4], 36h ; '6'
0x18001a1d6  mov     [rbp+260h+var_1D0], 32h ; '2'
0x18001a1dd  mov     [rbp+260h+var_1BC], 0Bh
0x18001a1e4  movdqu  [rbp+260h+var_230], xmm0
0x18001a1e9  movups  xmm0, xmmword ptr cs:FOLDERID_SkyDriveCameraRoll.Data1
0x18001a1f0  movdqu  [rbp+260h+var_21C], xmm0
0x18001a1f5  movups  xmm0, xmmword ptr cs:FOLDERID_SkyDrivePictures.Data1
0x18001a1fc  movdqu  [rbp+260h+var_208], xmm0
0x18001a201  movups  xmm0, xmmword ptr cs:FOLDERID_SkyDriveMusic.Data1
0x18001a208  movdqu  [rbp+260h+var_1F4], xmm0
0x18001a20d  movups  xmm0, xmmword ptr cs:FOLDERID_OneDrive.Data1
0x18001a214  movdqu  [rbp+260h+var_1E0], xmm0
0x18001a21c  movups  xmm0, xmmword ptr cs:FOLDERID_Profile.Data1
0x18001a223  movdqu  [rbp+260h+var_1CC], xmm0
0x18001a22b  test    al, al
0x18001a22d  jz      loc_18001A61D
0x18001a233  movups  xmm0, xmmword ptr cs:FOLDERID_Fonts.Data1
0x18001a23a  mov     [rbp+260h+var_1A8], 71h ; 'q'
0x18001a241  mov     r15d, r13d
0x18001a244  mov     [rbp+260h+var_194], 72h ; 'r'
0x18001a24b  movdqu  [rbp+260h+var_1B8], xmm0
0x18001a253  mov     [rbp+260h+var_180], 73h ; 's'
0x18001a25a  movups  xmm0, xmmword ptr cs:FOLDERID_ProgramFilesX86.Data1
0x18001a261  mov     [rbp+260h+var_16C], 74h ; 't'
0x18001a268  mov     [rbp+260h+var_158], 75h ; 'u'
0x18001a26f  movdqu  [rbp+260h+var_1A4], xmm0
0x18001a277  mov     [rbp+260h+var_144], 76h ; 'v'
0x18001a27e  movups  xmm0, xmmword ptr cs:FOLDERID_ProgramFilesX64.Data1
0x18001a285  mov     [rbp+260h+var_130], 16h
0x18001a28c  mov     [rbp+260h+var_11C], 17h
0x18001a293  movdqu  [rbp+260h+var_190], xmm0
0x18001a29b  mov     [rbp+260h+var_108], 18h
0x18001a2a2  movups  xmm0, xmmword ptr cs:FOLDERID_ProgramFiles.Data1
0x18001a2a9  mov     [rbp+260h+var_F4], 19h
0x18001a2b0  mov     [rbp+260h+var_E0], 1Ah
0x18001a2b7  movdqu  [rbp+260h+var_17C], xmm0
0x18001a2bf  mov     [rbp+260h+var_CC], 1Bh
0x18001a2c6  movups  xmm0, xmmword ptr cs:FOLDERID_Windows.Data1
0x18001a2cd  mov     [rbp+260h+var_B8], 1Ch
0x18001a2d4  mov     [rbp+260h+var_A4], 1Dh
0x18001a2db  movdqu  [rbp+260h+var_168], xmm0
0x18001a2e3  mov     [rbp+260h+var_90], 1Eh
0x18001a2ea  movups  xmm0, xmmword ptr cs:FOLDERID_HomeGroup.Data1
0x18001a2f1  movdqu  [rbp+260h+var_154], xmm0
0x18001a2f9  movups  xmm0, xmmword ptr cs:FOLDERID_Desktop.Data1
0x18001a300  movdqu  [rbp+260h+var_140], xmm0
0x18001a308  movups  xmm0, xmmword ptr cs:FOLDERID_Documents.Data1
0x18001a30f  movdqu  [rbp+260h+var_12C], xmm0
0x18001a317  movups  xmm0, xmmword ptr cs:FOLDERID_Downloads.Data1
0x18001a31e  mov     dword ptr [rdi+5A0h], 15h
0x18001a328  movdqu  [rbp+260h+var_118], xmm0
0x18001a330  movups  xmm0, xmmword ptr cs:FOLDERID_CameraRoll.Data1
0x18001a337  movdqu  [rbp+260h+var_104], xmm0
0x18001a33f  movups  xmm0, xmmword ptr cs:FOLDERID_Pictures.Data1
0x18001a346  movdqu  [rbp+260h+var_F0], xmm0
0x18001a34e  movups  xmm0, xmmword ptr cs:FOLDERID_Music.Data1
0x18001a355  movdqu  [rbp+260h+var_DC], xmm0
0x18001a35d  movups  xmm0, xmmword ptr cs:FOLDERID_Videos.Data1
0x18001a364  movdqu  [rbp+260h+var_C8], xmm0
0x18001a36c  movups  xmm0, xmmword ptr cs:FOLDERID_Objects3D.Data1
0x18001a373  movdqu  [rbp+260h+var_B4], xmm0
0x18001a37b  movups  xmm0, xmmword ptr cs:FOLDERID_Screenshots.Data1
0x18001a382  movdqu  [rbp+260h+var_A0], xmm0
0x18001a38a  movsxd  r14, r15d
0x18001a38d  xor     edx, edx
0x18001a38f  lea     rbx, [rdi+r14*8]
0x18001a393  lea     rcx, [rbx+410h]
0x18001a39a  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18001a39f  lea     rcx, [rbp+260h+var_230]
0x18001a3a3  mov     rsi, r14
0x18001a3a6  lea     r12, [r14+r14*4]
0x18001a3aa  xor     r8d, r8d; hToken
0x18001a3ad  lea     rcx, [rcx+r12*4]; rfid
0x18001a3b1  mov     edx, 4100h; dwFlags
0x18001a3b6  lea     r9, [rbx+410h]; ppszPath
0x18001a3bd  add     rsi, rsi
0x18001a3c0  call    cs:__imp_SHGetKnownFolderPath
0x18001a3c6  test    eax, eax
0x18001a3c8  js      short loc_18001A3D6
0x18001a3ca  mov     rax, [rdi+r14*8+410h]
0x18001a3d2  mov     [rdi+rsi*8], rax
0x18001a3d6  mov     al, [rbp+r12*4+260h+var_220]
0x18001a3db  inc     r15d
0x18001a3de  mov     [rdi+rsi*8+8], al
0x18001a3e2  cmp     r15d, 15h
0x18001a3e6  jb      short loc_18001A38A
0x18001a3e8  lea     rax, pszName; "shell:::{f874310e-b6b7-47dc-bc84-b9e6b3"...
0x18001a3ef  mov     [rsp+360h+var_318], 78h ; 'x'
0x18001a3f4  mov     [rsp+360h+pszName], rax
0x18001a3f9  xor     eax, eax
0x18001a3fb  mov     [rsp+360h+var_317], eax
0x18001a3ff  mov     [rsp+360h+var_313], ax
0x18001a404  mov     [rsp+360h+var_311], al
0x18001a408  lea     rax, aShell20d04fe03; "shell:::{20D04FE0-3AEA-1069-A2D8-08002B"...
0x18001a40f  mov     [rsp+360h+var_310], rax
0x18001a414  xor     eax, eax
0x18001a416  mov     [rsp+360h+var_307], eax
0x18001a41a  mov     [rsp+360h+var_303], ax
0x18001a41f  mov     [rsp+360h+var_301], al
0x18001a423  lea     rax, aShell645ff0405; "shell:::{645FF040-5081-101B-9F08-00AA00"...
0x18001a42a  mov     [rsp+360h+var_300], rax
0x18001a42f  xor     eax, eax
0x18001a431  mov     [rsp+360h+var_2F7], eax
0x18001a435  mov     [rsp+360h+var_2F3], ax
0x18001a43a  mov     [rsp+360h+var_2F1], al
0x18001a43e  lea     rax, aShellE88865ea0; "shell:::{e88865ea-0e1c-4e20-9aa6-edcd02"...
0x18001a445  mov     [rsp+360h+var_2F0], rax
0x18001a44a  xor     eax, eax
0x18001a44c  mov     [rsp+360h+var_2E7], eax
0x18001a450  mov     [rsp+360h+var_2E3], ax
0x18001a455  mov     [rsp+360h+var_2E1], al
0x18001a459  lea     rax, aShell1b3ea5dcB; "shell:::{1B3EA5DC-B587-4786-B4EF-BD1DC3"...
0x18001a460  mov     [rbp+260h+var_2E0], rax
0x18001a464  xor     eax, eax
0x18001a466  mov     [rbp+260h+var_2D7], eax
0x18001a469  mov     [rbp+260h+var_2D3], ax
0x18001a46d  mov     [rbp+260h+var_2D1], al
0x18001a470  lea     rax, aShell031e48257_2; "shell:::{031e4825-7b94-4dc3-b131-e946b4"...
0x18001a477  mov     [rbp+260h+var_2D0], rax
0x18001a47b  xor     eax, eax
0x18001a47d  mov     [rbp+260h+var_2C7], eax
0x18001a480  mov     [rbp+260h+var_2C3], ax
0x18001a484  mov     [rbp+260h+var_2C1], al
0x18001a487  lea     rax, aShell26ee0668A; "shell:::{26EE0668-A00A-44D7-9371-BEB064"...
0x18001a48e  mov     [rbp+260h+var_2C0], rax
0x18001a492  xor     eax, eax
0x18001a494  mov     [rbp+260h+var_2B7], eax
0x18001a497  mov     [rbp+260h+var_2B3], ax
0x18001a49b  mov     [rbp+260h+var_2B1], al
0x18001a49e  lea     rax, aShell031e48257_4; "shell:::{031E4825-7B94-4DC3-B131-E946B4"...
0x18001a4a5  mov     [rbp+260h+var_2B0], rax
0x18001a4a9  xor     eax, eax
0x18001a4ab  mov     [rbp+260h+var_2A7], eax
0x18001a4ae  mov     [rbp+260h+var_2A3], ax
0x18001a4b2  mov     [rbp+260h+var_2A1], al
0x18001a4b5  lea     rax, aShell031e48257_3; "shell:::{031E4825-7B94-4DC3-B131-E946B4"...
0x18001a4bc  mov     [rbp+260h+var_2A0], rax
0x18001a4c0  xor     eax, eax
0x18001a4c2  mov     [rbp+260h+var_297], eax
0x18001a4c5  mov     [rbp+260h+var_293], ax
0x18001a4c9  mov     [rbp+260h+var_291], al
0x18001a4cc  lea     rax, aShell031e48257_5; "shell:::{031E4825-7B94-4DC3-B131-E946B4"...
0x18001a4d3  mov     [rbp+260h+var_290], rax
0x18001a4d7  xor     eax, eax
0x18001a4d9  mov     [rbp+260h+var_287], eax
0x18001a4dc  mov     [rbp+260h+var_283], ax
0x18001a4e0  mov     [rbp+260h+var_281], al
0x18001a4e3  lea     rax, aShell031e48257; "shell:::{031E4825-7B94-4DC3-B131-E946B4"...
0x18001a4ea  mov     [rbp+260h+var_280], rax
0x18001a4ee  xor     eax, eax
0x18001a4f0  mov     [rbp+260h+var_277], eax
0x18001a4f3  mov     [rbp+260h+var_273], ax
0x18001a4f7  mov     [rbp+260h+var_271], al
0x18001a4fa  lea     rax, aShell031e48257_1; "shell:::{031E4825-7B94-4DC3-B131-E946B4"...
0x18001a501  mov     [rbp+260h+var_270], rax
0x18001a505  xor     eax, eax
0x18001a507  mov     [rsp+360h+var_308], 6Eh ; 'n'
0x18001a50c  mov     [rsp+360h+var_2F8], 70h ; 'p'
0x18001a511  mov     [rsp+360h+var_2E8], 79h ; 'y'
0x18001a516  mov     [rbp+260h+var_2D8], 7Bh ; '{'
0x18001a51a  mov     [rbp+260h+var_2C8], 7Ah ; 'z'
0x18001a51e  mov     [rbp+260h+var_2B8], 6Fh ; 'o'
0x18001a522  mov     [rbp+260h+var_2A8], 7Ch ; '|'
0x18001a526  mov     [rbp+260h+var_298], 7Dh ; '}'
0x18001a52a  mov     [rbp+260h+var_288], 7Eh ; '~'
0x18001a52e  mov     [rbp+260h+var_278], 7Fh
0x18001a532  mov     [rbp+260h+var_268], 80h
0x18001a536  mov     [rbp+260h+var_267], eax
0x18001a539  mov     r14d, r13d
0x18001a53c  mov     [rbp+260h+var_263], ax
0x18001a540  mov     [rbp+260h+var_261], al
0x18001a543  lea     rax, aShell031e48257_0; "shell:::{031E4825-7B94-4DC3-B131-E946B4"...
0x18001a54a  mov     [rbp+260h+var_260], rax
0x18001a54e  xor     eax, eax
0x18001a550  mov     [rbp+260h+var_257], eax
0x18001a553  mov     [rbp+260h+var_253], ax
0x18001a557  mov     [rbp+260h+var_251], al
0x18001a55a  mov     [rbp+260h+var_258], 81h
0x18001a55e  movsxd  rcx, r14d
0x18001a561  lea     r8, [rbp+260h+ppidl]; ppidl
0x18001a565  mov     rsi, rcx
0x18001a568  mov     [rsp+360h+pv], r13
0x18001a56d  add     rcx, 32h ; '2'
0x18001a571  mov     [rbp+260h+ppidl], r13
0x18001a575  add     rcx, rcx
0x18001a578  mov     [rbp+260h+var_240], 1
0x18001a57c  add     rsi, rsi
0x18001a57f  mov     [rsp+360h+psfgaoOut], r13; psfgaoOut
0x18001a584  xor     r9d, r9d; sfgaoIn
0x18001a587  xor     edx, edx; pbc
0x18001a589  mov     al, [rsp+rsi*8+360h+var_318]
0x18001a58d  mov     [rdi+rcx*8], al
0x18001a590  lea     rax, [rsp+360h+pv]
0x18001a595  mov     rcx, [rsp+rsi*8+360h+pszName]; pszName
0x18001a59a  mov     [rbp+260h+var_250], rax
0x18001a59e  call    cs:__imp_SHParseDisplayName
0x18001a5a4  mov     ebx, eax
0x18001a5a6  lea     rcx, [rbp+260h+var_250]
0x18001a5aa  shr     ebx, 1Fh
0x18001a5ad  call    ??1?$out_param_t@V?$unique_ptr@U_ITEMIDLIST_ABSOLUTE@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18001a5b2  test    bl, bl
0x18001a5b4  jz      short loc_18001A5CB
0x18001a5b6  mov     rcx, [rsp+360h+pv]; pv
0x18001a5bb  mov     [rsp+360h+pv], r13
0x18001a5c0  test    rcx, rcx
0x18001a5c3  jz      short loc_18001A5CB
0x18001a5c5  call    cs:__imp_CoTaskMemFree
0x18001a5cb  mov     rdx, [rdi+rsi*8+328h]
0x18001a5d3  mov     rcx, r13
0x18001a5d6  mov     rax, [rsp+360h+pv]
0x18001a5db  mov     [rsp+360h+pv], rcx
0x18001a5e0  mov     [rdi+rsi*8+328h], rax
0x18001a5e8  test    rdx, rdx
0x18001a5eb  jz      short loc_18001A5FB
0x18001a5ed  mov     rcx, rdx; pv
0x18001a5f0  call    cs:__imp_CoTaskMemFree
0x18001a5f6  mov     rcx, [rsp+360h+pv]; pv
0x18001a5fb  mov     [rsp+360h+pv], r13
0x18001a600  test    rcx, rcx
0x18001a603  jz      short loc_18001A60B
0x18001a605  call    cs:__imp_CoTaskMemFree
0x18001a60b  inc     r14d
0x18001a60e  cmp     r14d, 0Dh
0x18001a612  jb      loc_18001A55E
0x18001a618  jmp     loc_18001A83A
0x18001a61d  movups  xmm0, xmmword ptr cs:FOLDERID_ComputerFolder.Data1
0x18001a624  xor     edx, edx; Val
0x18001a626  mov     [rbp+260h+var_1A8], 6Eh ; 'n'
0x18001a62d  mov     r8d, 320h; Size
0x18001a633  mov     [rbp+260h+var_194], 6Fh ; 'o'
0x18001a63a  movdqu  [rbp+260h+var_1B8], xmm0
0x18001a642  mov     rcx, rdi; void *
0x18001a645  mov     [rbp+260h+var_180], 70h ; 'p'
0x18001a64c  movups  xmm0, xmmword ptr cs:FOLDERID_ControlPanelFolder.Data1
0x18001a653  mov     [rbp+260h+var_16C], 71h ; 'q'
0x18001a65a  mov     [rbp+260h+var_158], 72h ; 'r'
0x18001a661  movdqu  [rbp+260h+var_1A4], xmm0
0x18001a669  mov     [rbp+260h+var_144], 73h ; 's'
0x18001a670  movups  xmm0, xmmword ptr cs:FOLDERID_RecycleBinFolder.Data1
0x18001a677  mov     [rbp+260h+var_130], 74h ; 't'
0x18001a67e  mov     [rbp+260h+var_11C], 75h ; 'u'
0x18001a685  movdqu  [rbp+260h+var_190], xmm0
0x18001a68d  mov     [rbp+260h+var_108], 76h ; 'v'
0x18001a694  movups  xmm0, xmmword ptr cs:FOLDERID_Fonts.Data1
0x18001a69b  mov     [rbp+260h+var_F4], 16h
0x18001a6a2  mov     [rbp+260h+var_E0], 17h
0x18001a6a9  movdqu  [rbp+260h+var_17C], xmm0
0x18001a6b1  mov     [rbp+260h+var_CC], 18h
0x18001a6b8  movups  xmm0, xmmword ptr cs:FOLDERID_ProgramFilesX86.Data1
0x18001a6bf  mov     [rbp+260h+var_B8], 19h
0x18001a6c6  mov     [rbp+260h+var_A4], 1Ah
0x18001a6cd  movdqu  [rbp+260h+var_168], xmm0
0x18001a6d5  mov     [rbp+260h+var_90], 1Bh
0x18001a6dc  movups  xmm0, xmmword ptr cs:FOLDERID_ProgramFilesX64.Data1
0x18001a6e3  mov     [rbp+260h+var_7C], 1Ch
0x18001a6ea  mov     [rbp+260h+var_68], 1Dh
0x18001a6f1  movdqu  [rbp+260h+var_154], xmm0
0x18001a6f9  mov     [rbp+260h+var_54], 1Eh
0x18001a700  movups  xmm0, xmmword ptr cs:FOLDERID_ProgramFiles.Data1
0x18001a707  movdqu  [rbp+260h+var_140], xmm0
0x18001a70f  movups  xmm0, xmmword ptr cs:FOLDERID_Windows.Data1
0x18001a716  movdqu  [rbp+260h+var_12C], xmm0
0x18001a71e  movups  xmm0, xmmword ptr cs:FOLDERID_HomeGroup.Data1
0x18001a725  movdqu  [rbp+260h+var_118], xmm0
0x18001a72d  movups  xmm0, xmmword ptr cs:FOLDERID_Desktop.Data1
0x18001a734  movdqu  [rbp+260h+var_104], xmm0
0x18001a73c  movups  xmm0, xmmword ptr cs:FOLDERID_Documents.Data1
0x18001a743  movdqu  [rbp+260h+var_F0], xmm0
0x18001a74b  movups  xmm0, xmmword ptr cs:FOLDERID_Downloads.Data1
0x18001a752  movdqu  [rbp+260h+var_DC], xmm0
0x18001a75a  movups  xmm0, xmmword ptr cs:FOLDERID_CameraRoll.Data1
0x18001a761  movdqu  [rbp+260h+var_C8], xmm0
0x18001a769  movups  xmm0, xmmword ptr cs:FOLDERID_Pictures.Data1
0x18001a770  movdqu  [rbp+260h+var_B4], xmm0
0x18001a778  movups  xmm0, xmmword ptr cs:FOLDERID_Music.Data1
0x18001a77f  movdqu  [rbp+260h+var_A0], xmm0
0x18001a787  movups  xmm0, xmmword ptr cs:FOLDERID_Videos.Data1
0x18001a78e  movdqu  [rbp+260h+var_8C], xmm0
0x18001a796  movups  xmm0, xmmword ptr cs:FOLDERID_Objects3D.Data1
  ... truncated ...
```
