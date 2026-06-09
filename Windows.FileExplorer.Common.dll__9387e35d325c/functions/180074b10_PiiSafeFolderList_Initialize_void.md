# PiiSafeFolderList::Initialize(void)

- ea: `0x180074b10`
- end: `0x1800751ca`
- name: `?Initialize@PiiSafeFolderList@@QEAAXXZ`
- size: `1722`
- prototype: `void __fastcall(PiiSafeFolderList *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180071a9c`

## callees

- `0x18001d320`
- `0x1800309ec`
- `0x180030a20`
- `0x180037780`
- `0x180038708`
- `0x180074b10`
- `0x180077ee8`

## import_xrefs

- `Windows.Storage!SHGetKnownFolderPath` at `0x180074d50`
- `Windows.Storage!SHGetKnownFolderPath` at `0x18007517f`
- `Windows.Storage!SHGetKnownFolderPath` at `0x180074d50`
- `Windows.Storage!SHGetKnownFolderPath` at `0x18007517f`
- `Windows.Storage!SHParseDisplayName` at `0x180074f2f`
- `Windows.Storage!SHParseDisplayName` at `0x180074f2f`

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
  __int64 v8; // rdx
  char *v9; // r13
  signed int v10; // r15d
  __int64 v11; // r14
  _QWORD v12[2]; // [rsp+30h] [rbp-D0h] BYREF
  PCWSTR pszName; // [rsp+40h] [rbp-C0h]
  char v14; // [rsp+48h] [rbp-B8h]
  int v15; // [rsp+49h] [rbp-B7h]
  __int16 v16; // [rsp+4Dh] [rbp-B3h]
  char v17; // [rsp+4Fh] [rbp-B1h]
  const wchar_t *v18; // [rsp+50h] [rbp-B0h]
  char v19; // [rsp+58h] [rbp-A8h]
  int v20; // [rsp+59h] [rbp-A7h]
  __int16 v21; // [rsp+5Dh] [rbp-A3h]
  char v22; // [rsp+5Fh] [rbp-A1h]
  const wchar_t *v23; // [rsp+60h] [rbp-A0h]
  char v24; // [rsp+68h] [rbp-98h]
  int v25; // [rsp+69h] [rbp-97h]
  __int16 v26; // [rsp+6Dh] [rbp-93h]
  char v27; // [rsp+6Fh] [rbp-91h]
  const WCHAR *v28; // [rsp+70h] [rbp-90h]
  char v29; // [rsp+78h] [rbp-88h]
  int v30; // [rsp+79h] [rbp-87h]
  __int16 v31; // [rsp+7Dh] [rbp-83h]
  char v32; // [rsp+7Fh] [rbp-81h]
  const wchar_t *v33; // [rsp+80h] [rbp-80h]
  char v34; // [rsp+88h] [rbp-78h]
  int v35; // [rsp+89h] [rbp-77h]
  __int16 v36; // [rsp+8Dh] [rbp-73h]
  char v37; // [rsp+8Fh] [rbp-71h]
  const wchar_t *v38; // [rsp+90h] [rbp-70h]
  char v39; // [rsp+98h] [rbp-68h]
  int v40; // [rsp+99h] [rbp-67h]
  __int16 v41; // [rsp+9Dh] [rbp-63h]
  char v42; // [rsp+9Fh] [rbp-61h]
  const wchar_t *v43; // [rsp+A0h] [rbp-60h]
  char v44; // [rsp+A8h] [rbp-58h]
  int v45; // [rsp+A9h] [rbp-57h]
  __int16 v46; // [rsp+ADh] [rbp-53h]
  char v47; // [rsp+AFh] [rbp-51h]
  const wchar_t *v48; // [rsp+B0h] [rbp-50h]
  char v49; // [rsp+B8h] [rbp-48h]
  int v50; // [rsp+B9h] [rbp-47h]
  __int16 v51; // [rsp+BDh] [rbp-43h]
  char v52; // [rsp+BFh] [rbp-41h]
  const wchar_t *v53; // [rsp+C0h] [rbp-40h]
  char v54; // [rsp+C8h] [rbp-38h]
  int v55; // [rsp+C9h] [rbp-37h]
  __int16 v56; // [rsp+CDh] [rbp-33h]
  char v57; // [rsp+CFh] [rbp-31h]
  const wchar_t *v58; // [rsp+D0h] [rbp-30h]
  char v59; // [rsp+D8h] [rbp-28h]
  int v60; // [rsp+D9h] [rbp-27h]
  __int16 v61; // [rsp+DDh] [rbp-23h]
  char v62; // [rsp+DFh] [rbp-21h]
  const wchar_t *v63; // [rsp+E0h] [rbp-20h]
  char v64; // [rsp+E8h] [rbp-18h]
  int v65; // [rsp+E9h] [rbp-17h]
  __int16 v66; // [rsp+EDh] [rbp-13h]
  char v67; // [rsp+EFh] [rbp-11h]
  const wchar_t *v68; // [rsp+F0h] [rbp-10h]
  char v69; // [rsp+F8h] [rbp-8h]
  int v70; // [rsp+F9h] [rbp-7h]
  __int16 v71; // [rsp+FDh] [rbp-3h]
  char v72; // [rsp+FFh] [rbp-1h]
  const wchar_t *v73; // [rsp+100h] [rbp+0h]
  char v74; // [rsp+108h] [rbp+8h]
  int v75; // [rsp+109h] [rbp+9h]
  __int16 v76; // [rsp+10Dh] [rbp+Dh]
  char v77; // [rsp+10Fh] [rbp+Fh]
  _QWORD *v78; // [rsp+110h] [rbp+10h] BYREF
  LPITEMIDLIST ppidl; // [rsp+118h] [rbp+18h] BYREF
  char v80; // [rsp+120h] [rbp+20h]
  GUID v81; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v82[4]; // [rsp+140h] [rbp+40h]
  GUID v83; // [rsp+144h] [rbp+44h]
  char v84; // [rsp+154h] [rbp+54h]
  GUID v85; // [rsp+158h] [rbp+58h]
  char v86; // [rsp+168h] [rbp+68h]
  GUID v87; // [rsp+16Ch] [rbp+6Ch]
  char v88; // [rsp+17Ch] [rbp+7Ch]
  GUID v89; // [rsp+180h] [rbp+80h]
  char v90; // [rsp+190h] [rbp+90h]
  GUID v91; // [rsp+194h] [rbp+94h]
  char v92; // [rsp+1A4h] [rbp+A4h]
  GUID v93; // [rsp+1A8h] [rbp+A8h]
  char v94; // [rsp+1B8h] [rbp+B8h]
  GUID v95; // [rsp+1BCh] [rbp+BCh]
  char v96; // [rsp+1CCh] [rbp+CCh]
  GUID v97; // [rsp+1D0h] [rbp+D0h]
  char v98; // [rsp+1E0h] [rbp+E0h]
  GUID v99; // [rsp+1E4h] [rbp+E4h]
  char v100; // [rsp+1F4h] [rbp+F4h]
  GUID v101; // [rsp+1F8h] [rbp+F8h]
  char v102; // [rsp+208h] [rbp+108h]
  GUID v103; // [rsp+20Ch] [rbp+10Ch]
  char v104; // [rsp+21Ch] [rbp+11Ch]
  GUID v105; // [rsp+220h] [rbp+120h]
  char v106; // [rsp+230h] [rbp+130h]
  GUID v107; // [rsp+234h] [rbp+134h]
  char v108; // [rsp+244h] [rbp+144h]
  GUID v109; // [rsp+248h] [rbp+148h]
  char v110; // [rsp+258h] [rbp+158h]
  GUID v111; // [rsp+25Ch] [rbp+15Ch]
  char v112; // [rsp+26Ch] [rbp+16Ch]
  GUID v113; // [rsp+270h] [rbp+170h]
  char v114; // [rsp+280h] [rbp+180h]
  GUID v115; // [rsp+284h] [rbp+184h]
  char v116; // [rsp+294h] [rbp+194h]
  GUID v117; // [rsp+298h] [rbp+198h]
  char v118; // [rsp+2A8h] [rbp+1A8h]
  GUID v119; // [rsp+2ACh] [rbp+1ACh]
  char v120; // [rsp+2BCh] [rbp+1BCh]
  GUID v121; // [rsp+2C0h] [rbp+1C0h]
  char v122; // [rsp+2D0h] [rbp+1D0h]
  GUID v123; // [rsp+2D4h] [rbp+1D4h]
  char v124; // [rsp+2E4h] [rbp+1E4h]
  GUID v125; // [rsp+2E8h] [rbp+1E8h]
  char v126; // [rsp+2F8h] [rbp+1F8h]
  GUID v127; // [rsp+2FCh] [rbp+1FCh]
  char v128; // [rsp+30Ch] [rbp+20Ch]

  v82[0] = 51;
  v84 = 52;
  v86 = 53;
  v88 = 54;
  v90 = 50;
  v92 = 11;
  v81 = FOLDERID_SkyDriveDocuments;
  v83 = FOLDERID_SkyDriveCameraRoll;
  v85 = FOLDERID_SkyDrivePictures;
  v87 = FOLDERID_SkyDriveMusic;
  v89 = FOLDERID_OneDrive;
  v91 = FOLDERID_Profile;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56275225>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56275225>::GetImpl'::`2'::impl) )
  {
    v94 = 113;
    v2 = 0;
    v96 = 114;
    v93 = FOLDERID_Fonts;
    v98 = 115;
    v100 = 116;
    v102 = 117;
    v95 = FOLDERID_ProgramFilesX86;
    v104 = 118;
    v106 = 22;
    v108 = 23;
    v97 = FOLDERID_ProgramFilesX64;
    v110 = 24;
    v112 = 25;
    v114 = 26;
    v99 = FOLDERID_ProgramFiles;
    v116 = 27;
    v118 = 28;
    v120 = 29;
    v101 = FOLDERID_Windows;
    v122 = 30;
    *((_DWORD *)this + 360) = 21;
    v103 = FOLDERID_HomeGroup;
    v105 = FOLDERID_Desktop;
    v107 = FOLDERID_Documents;
    v109 = FOLDERID_Downloads;
    v111 = FOLDERID_CameraRoll;
    v113 = FOLDERID_Pictures;
    v115 = FOLDERID_Music;
    v117 = FOLDERID_Videos;
    v119 = FOLDERID_Objects3D;
    v121 = FOLDERID_Screenshots;
    do
    {
      v3 = (int)v2;
      v4 = (PWSTR *)((char *)this + 8 * (int)v2);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        v4 + 130,
        0);
      if ( SHGetKnownFolderPath((GUID *)((char *)&v81 + 20 * (int)v2), 0x4100u, 0, v4 + 130) >= 0 )
        *((_QWORD *)this + 2 * (int)v2) = *((_QWORD *)this + (int)v2 + 130);
      ++v2;
      *((_BYTE *)this + 16 * v3 + 8) = v82[20 * v3];
    }
    while ( v2 < 0x15 );
    v14 = 120;
    pszName = L"shell:::{f874310e-b6b7-47dc-bc84-b9e6b38f5903}";
    v15 = 0;
    v16 = 0;
    v17 = 0;
    v18 = L"shell:::{20D04FE0-3AEA-1069-A2D8-08002B30309D}";
    v20 = 0;
    v21 = 0;
    v22 = 0;
    v23 = L"shell:::{645FF040-5081-101B-9F08-00AA002F954E}";
    v25 = 0;
    v26 = 0;
    v27 = 0;
    v28 = L"shell:::{e88865ea-0e1c-4e20-9aa6-edcd0212c87c}";
    v30 = 0;
    v31 = 0;
    v32 = 0;
    v33 = L"shell:::{1B3EA5DC-B587-4786-B4EF-BD1DC332AEAE}";
    v35 = 0;
    v36 = 0;
    v37 = 0;
    v38 = L"shell:::{031e4825-7b94-4dc3-b131-e946b44c8dd5}";
    v40 = 0;
    v41 = 0;
    v42 = 0;
    v43 = L"shell:::{26EE0668-A00A-44D7-9371-BEB064C98683}";
    v45 = 0;
    v46 = 0;
    v47 = 0;
    v48 = L"shell:::{031E4825-7B94-4DC3-B131-E946B44C8DD5}\\CameraRoll.library-ms";
    v50 = 0;
    v51 = 0;
    v52 = 0;
    v53 = L"shell:::{031E4825-7B94-4DC3-B131-E946B44C8DD5}\\Documents.library-ms";
    v55 = 0;
    v56 = 0;
    v57 = 0;
    v58 = L"shell:::{031E4825-7B94-4DC3-B131-E946B44C8DD5}\\Music.library-ms";
    v60 = 0;
    v61 = 0;
    v62 = 0;
    v63 = L"shell:::{031E4825-7B94-4DC3-B131-E946B44C8DD5}\\Pictures.library-ms";
    v65 = 0;
    v66 = 0;
    v67 = 0;
    v68 = L"shell:::{031E4825-7B94-4DC3-B131-E946B44C8DD5}\\SavedPictures.library-ms";
    v19 = 110;
    v24 = 112;
    v29 = 121;
    v34 = 123;
    v39 = 122;
    v44 = 111;
    v49 = 124;
    v54 = 125;
    v59 = 126;
    v64 = 127;
    v69 = 0x80;
    v70 = 0;
    v5 = 0;
    v71 = 0;
    v72 = 0;
    v73 = L"shell:::{031E4825-7B94-4DC3-B131-E946B44C8DD5}\\Videos.library-ms";
    v75 = 0;
    v76 = 0;
    v77 = 0;
    v74 = -127;
    do
    {
      v12[0] = 0;
      ppidl = 0;
      v80 = 1;
      *((_BYTE *)this + 16 * (int)v5 + 800) = *(&v14 + 16 * (int)v5);
      v6 = (&pszName)[2 * (int)v5];
      v78 = v12;
      v7 = (unsigned int)SHParseDisplayName(v6, 0, &ppidl, 0, 0) >> 31;
      wil::details::out_param_t<wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&v78);
      if ( (_BYTE)v7 )
        wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
          v12,
          0);
      v8 = v12[0];
      v12[0] = 0;
      wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
        (char *)this + 16 * (int)v5 + 808,
        v8);
      wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
        v12,
        0);
      ++v5;
    }
    while ( v5 < 0xD );
  }
  else
  {
    v94 = 110;
    v96 = 111;
    v93 = FOLDERID_ComputerFolder;
    v98 = 112;
    v100 = 113;
    v102 = 114;
    v95 = FOLDERID_ControlPanelFolder;
    v104 = 115;
    v106 = 116;
    v108 = 117;
    v97 = FOLDERID_RecycleBinFolder;
    v110 = 118;
    v112 = 22;
    v114 = 23;
    v99 = FOLDERID_Fonts;
    v116 = 24;
    v118 = 25;
    v120 = 26;
    v101 = FOLDERID_ProgramFilesX86;
    v122 = 27;
    v124 = 28;
    v126 = 29;
    v103 = FOLDERID_ProgramFilesX64;
    v128 = 30;
    v105 = FOLDERID_ProgramFiles;
    v107 = FOLDERID_Windows;
    v109 = FOLDERID_HomeGroup;
    v111 = FOLDERID_Desktop;
    v113 = FOLDERID_Documents;
    v115 = FOLDERID_Downloads;
    v117 = FOLDERID_CameraRoll;
    v119 = FOLDERID_Pictures;
    v121 = FOLDERID_Music;
    v123 = FOLDERID_Videos;
    v125 = FOLDERID_Objects3D;
    v127 = FOLDERID_Screenshots;
    memset_0(this, 0, 0x320u);
    v9 = (char *)this + 1040;
    memset_0((char *)this + 1040, 0, 0x190u);
    v10 = 0;
    *((_DWORD *)this + 360) = 24;
    do
    {
      v11 = v10;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v9[8 * v10],
        0);
      if ( SHGetKnownFolderPath((GUID *)((char *)&v81 + 20 * v10), 0x4100u, 0, (PWSTR *)&v9[8 * v10]) >= 0 )
        *((_QWORD *)this + 2 * v10) = *((_QWORD *)this + v10 + 130);
      ++v10;
      *((_BYTE *)this + 16 * v11 + 8) = v82[20 * v11];
    }
    while ( (unsigned int)v10 < 0x18 );
  }
}

```

## disassembly

```asm
0x180074b10  push    rbp
0x180074b12  push    rbx
0x180074b13  push    rsi
0x180074b14  push    rdi
0x180074b15  push    r12
0x180074b17  push    r13
0x180074b19  push    r14
0x180074b1b  push    r15
0x180074b1d  lea     rbp, [rsp-228h]
0x180074b25  sub     rsp, 328h
0x180074b2c  mov     rax, cs:__security_cookie
0x180074b33  xor     rax, rsp
0x180074b36  mov     [rbp+260h+var_50], rax
0x180074b3d  mov     rdi, rcx
0x180074b40  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56275225@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56275225@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56275225> `wil::Feature<__WilFeatureTraits_Feature_56275225>::GetImpl(void)'::`2'::impl
0x180074b47  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56275225@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56275225>::__private_IsEnabled(void)
0x180074b4c  movups  xmm0, xmmword ptr cs:FOLDERID_SkyDriveDocuments.Data1
0x180074b53  xor     r13d, r13d
0x180074b56  mov     [rbp+260h+var_220], 33h ; '3'
0x180074b5a  mov     [rbp+260h+var_20C], 34h ; '4'
0x180074b5e  mov     [rbp+260h+var_1F8], 35h ; '5'
0x180074b62  mov     [rbp+260h+var_1E4], 36h ; '6'
0x180074b66  mov     [rbp+260h+var_1D0], 32h ; '2'
0x180074b6d  mov     [rbp+260h+var_1BC], 0Bh
0x180074b74  movdqu  [rbp+260h+var_230], xmm0
0x180074b79  movups  xmm0, xmmword ptr cs:FOLDERID_SkyDriveCameraRoll.Data1
0x180074b80  movdqu  [rbp+260h+var_21C], xmm0
0x180074b85  movups  xmm0, xmmword ptr cs:FOLDERID_SkyDrivePictures.Data1
0x180074b8c  movdqu  [rbp+260h+var_208], xmm0
0x180074b91  movups  xmm0, xmmword ptr cs:FOLDERID_SkyDriveMusic.Data1
0x180074b98  movdqu  [rbp+260h+var_1F4], xmm0
0x180074b9d  movups  xmm0, xmmword ptr cs:FOLDERID_OneDrive.Data1
0x180074ba4  movdqu  [rbp+260h+var_1E0], xmm0
0x180074bac  movups  xmm0, xmmword ptr cs:FOLDERID_Profile.Data1
0x180074bb3  movdqu  [rbp+260h+var_1CC], xmm0
0x180074bbb  test    al, al
0x180074bbd  jz      loc_180074F8A
0x180074bc3  movups  xmm0, xmmword ptr cs:FOLDERID_Fonts.Data1
0x180074bca  mov     [rbp+260h+var_1A8], 71h ; 'q'
0x180074bd1  mov     r15d, r13d
0x180074bd4  mov     [rbp+260h+var_194], 72h ; 'r'
0x180074bdb  movdqu  [rbp+260h+var_1B8], xmm0
0x180074be3  mov     [rbp+260h+var_180], 73h ; 's'
0x180074bea  movups  xmm0, xmmword ptr cs:FOLDERID_ProgramFilesX86.Data1
0x180074bf1  mov     [rbp+260h+var_16C], 74h ; 't'
0x180074bf8  mov     [rbp+260h+var_158], 75h ; 'u'
0x180074bff  movdqu  [rbp+260h+var_1A4], xmm0
0x180074c07  mov     [rbp+260h+var_144], 76h ; 'v'
0x180074c0e  movups  xmm0, xmmword ptr cs:FOLDERID_ProgramFilesX64.Data1
0x180074c15  mov     [rbp+260h+var_130], 16h
0x180074c1c  mov     [rbp+260h+var_11C], 17h
0x180074c23  movdqu  [rbp+260h+var_190], xmm0
0x180074c2b  mov     [rbp+260h+var_108], 18h
0x180074c32  movups  xmm0, xmmword ptr cs:FOLDERID_ProgramFiles.Data1
0x180074c39  mov     [rbp+260h+var_F4], 19h
0x180074c40  mov     [rbp+260h+var_E0], 1Ah
0x180074c47  movdqu  [rbp+260h+var_17C], xmm0
0x180074c4f  mov     [rbp+260h+var_CC], 1Bh
0x180074c56  movups  xmm0, xmmword ptr cs:FOLDERID_Windows.Data1
0x180074c5d  mov     [rbp+260h+var_B8], 1Ch
0x180074c64  mov     [rbp+260h+var_A4], 1Dh
0x180074c6b  movdqu  [rbp+260h+var_168], xmm0
0x180074c73  mov     [rbp+260h+var_90], 1Eh
0x180074c7a  movups  xmm0, xmmword ptr cs:FOLDERID_HomeGroup.Data1
0x180074c81  mov     dword ptr [rdi+5A0h], 15h
0x180074c8b  movdqu  [rbp+260h+var_154], xmm0
0x180074c93  movups  xmm0, xmmword ptr cs:FOLDERID_Desktop.Data1
0x180074c9a  movdqu  [rbp+260h+var_140], xmm0
0x180074ca2  movups  xmm0, xmmword ptr cs:FOLDERID_Documents.Data1
0x180074ca9  movdqu  [rbp+260h+var_12C], xmm0
0x180074cb1  movups  xmm0, xmmword ptr cs:FOLDERID_Downloads.Data1
0x180074cb8  movdqu  [rbp+260h+var_118], xmm0
0x180074cc0  movups  xmm0, xmmword ptr cs:FOLDERID_CameraRoll.Data1
0x180074cc7  movdqu  [rbp+260h+var_104], xmm0
0x180074ccf  movups  xmm0, xmmword ptr cs:FOLDERID_Pictures.Data1
0x180074cd6  movdqu  [rbp+260h+var_F0], xmm0
0x180074cde  movups  xmm0, xmmword ptr cs:FOLDERID_Music.Data1
0x180074ce5  movdqu  [rbp+260h+var_DC], xmm0
0x180074ced  movups  xmm0, xmmword ptr cs:FOLDERID_Videos.Data1
0x180074cf4  movdqu  [rbp+260h+var_C8], xmm0
0x180074cfc  movups  xmm0, xmmword ptr cs:FOLDERID_Objects3D.Data1
0x180074d03  movdqu  [rbp+260h+var_B4], xmm0
0x180074d0b  movups  xmm0, xmmword ptr cs:FOLDERID_Screenshots.Data1
0x180074d12  movdqu  [rbp+260h+var_A0], xmm0
0x180074d1a  movsxd  r14, r15d
0x180074d1d  xor     edx, edx
0x180074d1f  lea     rbx, [rdi+r14*8]
0x180074d23  lea     rcx, [rbx+410h]
0x180074d2a  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180074d2f  lea     rcx, [rbp+260h+var_230]
0x180074d33  mov     rsi, r14
0x180074d36  lea     r12, [r14+r14*4]
0x180074d3a  xor     r8d, r8d; hToken
0x180074d3d  lea     rcx, [rcx+r12*4]; rfid
0x180074d41  mov     edx, 4100h; dwFlags
0x180074d46  lea     r9, [rbx+410h]; ppszPath
0x180074d4d  add     rsi, rsi
0x180074d50  call    cs:__imp_SHGetKnownFolderPath
0x180074d56  test    eax, eax
0x180074d58  js      short loc_180074D66
0x180074d5a  mov     rax, [rdi+r14*8+410h]
0x180074d62  mov     [rdi+rsi*8], rax
0x180074d66  mov     al, [rbp+r12*4+260h+var_220]
0x180074d6b  inc     r15d
0x180074d6e  mov     [rdi+rsi*8+8], al
0x180074d72  cmp     r15d, 15h
0x180074d76  jb      short loc_180074D1A
0x180074d78  lea     rax, aShellF874310eB; "shell:::{f874310e-b6b7-47dc-bc84-b9e6b3"...
0x180074d7f  mov     [rsp+360h+var_318], 78h ; 'x'
0x180074d84  mov     [rsp+360h+pszName], rax
0x180074d89  xor     eax, eax
0x180074d8b  mov     [rsp+360h+var_317], eax
0x180074d8f  mov     [rsp+360h+var_313], ax
0x180074d94  mov     [rsp+360h+var_311], al
0x180074d98  lea     rax, aShell20d04fe03; "shell:::{20D04FE0-3AEA-1069-A2D8-08002B"...
0x180074d9f  mov     [rsp+360h+var_310], rax
0x180074da4  xor     eax, eax
0x180074da6  mov     [rsp+360h+var_307], eax
0x180074daa  mov     [rsp+360h+var_303], ax
0x180074daf  mov     [rsp+360h+var_301], al
0x180074db3  lea     rax, aShell645ff0405; "shell:::{645FF040-5081-101B-9F08-00AA00"...
0x180074dba  mov     [rsp+360h+var_300], rax
0x180074dbf  xor     eax, eax
0x180074dc1  mov     [rsp+360h+var_2F7], eax
0x180074dc5  mov     [rsp+360h+var_2F3], ax
0x180074dca  mov     [rsp+360h+var_2F1], al
0x180074dce  lea     rax, pszName; "shell:::{e88865ea-0e1c-4e20-9aa6-edcd02"...
0x180074dd5  mov     [rsp+360h+var_2F0], rax
0x180074dda  xor     eax, eax
0x180074ddc  mov     [rsp+360h+var_2E7], eax
0x180074de0  mov     [rsp+360h+var_2E3], ax
0x180074de5  mov     [rsp+360h+var_2E1], al
0x180074de9  lea     rax, aShell1b3ea5dcB; "shell:::{1B3EA5DC-B587-4786-B4EF-BD1DC3"...
0x180074df0  mov     [rbp+260h+var_2E0], rax
0x180074df4  xor     eax, eax
0x180074df6  mov     [rbp+260h+var_2D7], eax
0x180074df9  mov     [rbp+260h+var_2D3], ax
0x180074dfd  mov     [rbp+260h+var_2D1], al
0x180074e00  lea     rax, aShell031e48257_2; "shell:::{031e4825-7b94-4dc3-b131-e946b4"...
0x180074e07  mov     [rbp+260h+var_2D0], rax
0x180074e0b  xor     eax, eax
0x180074e0d  mov     [rbp+260h+var_2C7], eax
0x180074e10  mov     [rbp+260h+var_2C3], ax
0x180074e14  mov     [rbp+260h+var_2C1], al
0x180074e17  lea     rax, aShell26ee0668A; "shell:::{26EE0668-A00A-44D7-9371-BEB064"...
0x180074e1e  mov     [rbp+260h+var_2C0], rax
0x180074e22  xor     eax, eax
0x180074e24  mov     [rbp+260h+var_2B7], eax
0x180074e27  mov     [rbp+260h+var_2B3], ax
0x180074e2b  mov     [rbp+260h+var_2B1], al
0x180074e2e  lea     rax, aShell031e48257_4; "shell:::{031E4825-7B94-4DC3-B131-E946B4"...
0x180074e35  mov     [rbp+260h+var_2B0], rax
0x180074e39  xor     eax, eax
0x180074e3b  mov     [rbp+260h+var_2A7], eax
0x180074e3e  mov     [rbp+260h+var_2A3], ax
0x180074e42  mov     [rbp+260h+var_2A1], al
0x180074e45  lea     rax, aShell031e48257_3; "shell:::{031E4825-7B94-4DC3-B131-E946B4"...
0x180074e4c  mov     [rbp+260h+var_2A0], rax
0x180074e50  xor     eax, eax
0x180074e52  mov     [rbp+260h+var_297], eax
0x180074e55  mov     [rbp+260h+var_293], ax
0x180074e59  mov     [rbp+260h+var_291], al
0x180074e5c  lea     rax, aShell031e48257_5; "shell:::{031E4825-7B94-4DC3-B131-E946B4"...
0x180074e63  mov     [rbp+260h+var_290], rax
0x180074e67  xor     eax, eax
0x180074e69  mov     [rbp+260h+var_287], eax
0x180074e6c  mov     [rbp+260h+var_283], ax
0x180074e70  mov     [rbp+260h+var_281], al
0x180074e73  lea     rax, aShell031e48257; "shell:::{031E4825-7B94-4DC3-B131-E946B4"...
0x180074e7a  mov     [rbp+260h+var_280], rax
0x180074e7e  xor     eax, eax
0x180074e80  mov     [rbp+260h+var_277], eax
0x180074e83  mov     [rbp+260h+var_273], ax
0x180074e87  mov     [rbp+260h+var_271], al
0x180074e8a  lea     rax, aShell031e48257_1; "shell:::{031E4825-7B94-4DC3-B131-E946B4"...
0x180074e91  mov     [rbp+260h+var_270], rax
0x180074e95  xor     eax, eax
0x180074e97  mov     [rsp+360h+var_308], 6Eh ; 'n'
0x180074e9c  mov     [rsp+360h+var_2F8], 70h ; 'p'
0x180074ea1  mov     [rsp+360h+var_2E8], 79h ; 'y'
0x180074ea6  mov     [rbp+260h+var_2D8], 7Bh ; '{'
0x180074eaa  mov     [rbp+260h+var_2C8], 7Ah ; 'z'
0x180074eae  mov     [rbp+260h+var_2B8], 6Fh ; 'o'
0x180074eb2  mov     [rbp+260h+var_2A8], 7Ch ; '|'
0x180074eb6  mov     [rbp+260h+var_298], 7Dh ; '}'
0x180074eba  mov     [rbp+260h+var_288], 7Eh ; '~'
0x180074ebe  mov     [rbp+260h+var_278], 7Fh
0x180074ec2  mov     [rbp+260h+var_268], 80h
0x180074ec6  mov     [rbp+260h+var_267], eax
0x180074ec9  mov     r14d, r13d
0x180074ecc  mov     [rbp+260h+var_263], ax
0x180074ed0  mov     [rbp+260h+var_261], al
0x180074ed3  lea     rax, aShell031e48257_0; "shell:::{031E4825-7B94-4DC3-B131-E946B4"...
0x180074eda  mov     [rbp+260h+var_260], rax
0x180074ede  xor     eax, eax
0x180074ee0  mov     [rbp+260h+var_257], eax
0x180074ee3  mov     [rbp+260h+var_253], ax
0x180074ee7  mov     [rbp+260h+var_251], al
0x180074eea  mov     [rbp+260h+var_258], 81h
0x180074eee  movsxd  rcx, r14d
0x180074ef1  lea     r8, [rbp+260h+ppidl]; ppidl
0x180074ef5  mov     rsi, rcx
0x180074ef8  mov     [rsp+360h+var_330], r13
0x180074efd  add     rcx, 32h ; '2'
0x180074f01  shl     rsi, 4
0x180074f05  add     rcx, rcx
0x180074f08  mov     [rbp+260h+ppidl], r13
0x180074f0c  xor     r9d, r9d; sfgaoIn
0x180074f0f  mov     [rbp+260h+var_240], 1
0x180074f13  xor     edx, edx; pbc
0x180074f15  mov     [rsp+360h+psfgaoOut], r13; psfgaoOut
0x180074f1a  mov     al, [rsp+rsi+360h+var_318]
0x180074f1e  mov     [rdi+rcx*8], al
0x180074f21  lea     rax, [rsp+360h+var_330]
0x180074f26  mov     rcx, [rsp+rsi+360h+pszName]; pszName
0x180074f2b  mov     [rbp+260h+var_250], rax
0x180074f2f  call    cs:__imp_SHParseDisplayName
0x180074f35  mov     ebx, eax
0x180074f37  lea     rcx, [rbp+260h+var_250]
0x180074f3b  shr     ebx, 1Fh
0x180074f3e  call    ??1?$out_param_t@V?$unique_ptr@U_ITEMIDLIST_ABSOLUTE@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180074f43  test    bl, bl
0x180074f45  jz      short loc_180074F53
0x180074f47  xor     edx, edx
0x180074f49  lea     rcx, [rsp+360h+var_330]
0x180074f4e  call    ?reset@?$unique_ptr@U_ITEMIDLIST_ABSOLUTE@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAU_ITEMIDLIST_ABSOLUTE@@@Z; wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(_ITEMIDLIST_ABSOLUTE *)
0x180074f53  mov     rdx, [rsp+360h+var_330]
0x180074f58  lea     rcx, [rdi+328h]
0x180074f5f  add     rcx, rsi
0x180074f62  mov     [rsp+360h+var_330], r13
0x180074f67  call    ?reset@?$unique_ptr@U_ITEMIDLIST_ABSOLUTE@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAU_ITEMIDLIST_ABSOLUTE@@@Z; wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(_ITEMIDLIST_ABSOLUTE *)
0x180074f6c  xor     edx, edx
0x180074f6e  lea     rcx, [rsp+360h+var_330]
0x180074f73  call    ?reset@?$unique_ptr@U_ITEMIDLIST_ABSOLUTE@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAU_ITEMIDLIST_ABSOLUTE@@@Z; wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(_ITEMIDLIST_ABSOLUTE *)
0x180074f78  inc     r14d
0x180074f7b  cmp     r14d, 0Dh
0x180074f7f  jb      loc_180074EEE
0x180074f85  jmp     loc_1800751A7
0x180074f8a  movups  xmm0, xmmword ptr cs:FOLDERID_ComputerFolder.Data1
0x180074f91  xor     edx, edx; Val
0x180074f93  mov     [rbp+260h+var_1A8], 6Eh ; 'n'
0x180074f9a  mov     r8d, 320h; Size
0x180074fa0  mov     [rbp+260h+var_194], 6Fh ; 'o'
0x180074fa7  movdqu  [rbp+260h+var_1B8], xmm0
0x180074faf  mov     rcx, rdi; void *
0x180074fb2  mov     [rbp+260h+var_180], 70h ; 'p'
0x180074fb9  movups  xmm0, xmmword ptr cs:FOLDERID_ControlPanelFolder.Data1
0x180074fc0  mov     [rbp+260h+var_16C], 71h ; 'q'
0x180074fc7  mov     [rbp+260h+var_158], 72h ; 'r'
0x180074fce  movdqu  [rbp+260h+var_1A4], xmm0
0x180074fd6  mov     [rbp+260h+var_144], 73h ; 's'
0x180074fdd  movups  xmm0, xmmword ptr cs:FOLDERID_RecycleBinFolder.Data1
0x180074fe4  mov     [rbp+260h+var_130], 74h ; 't'
0x180074feb  mov     [rbp+260h+var_11C], 75h ; 'u'
0x180074ff2  movdqu  [rbp+260h+var_190], xmm0
0x180074ffa  mov     [rbp+260h+var_108], 76h ; 'v'
0x180075001  movups  xmm0, xmmword ptr cs:FOLDERID_Fonts.Data1
0x180075008  mov     [rbp+260h+var_F4], 16h
0x18007500f  mov     [rbp+260h+var_E0], 17h
0x180075016  movdqu  [rbp+260h+var_17C], xmm0
0x18007501e  mov     [rbp+260h+var_CC], 18h
0x180075025  movups  xmm0, xmmword ptr cs:FOLDERID_ProgramFilesX86.Data1
0x18007502c  mov     [rbp+260h+var_B8], 19h
0x180075033  mov     [rbp+260h+var_A4], 1Ah
0x18007503a  movdqu  [rbp+260h+var_168], xmm0
0x180075042  mov     [rbp+260h+var_90], 1Bh
0x180075049  movups  xmm0, xmmword ptr cs:FOLDERID_ProgramFilesX64.Data1
0x180075050  mov     [rbp+260h+var_7C], 1Ch
0x180075057  mov     [rbp+260h+var_68], 1Dh
0x18007505e  movdqu  [rbp+260h+var_154], xmm0
0x180075066  mov     [rbp+260h+var_54], 1Eh
0x18007506d  movups  xmm0, xmmword ptr cs:FOLDERID_ProgramFiles.Data1
0x180075074  movdqu  [rbp+260h+var_140], xmm0
0x18007507c  movups  xmm0, xmmword ptr cs:FOLDERID_Windows.Data1
0x180075083  movdqu  [rbp+260h+var_12C], xmm0
0x18007508b  movups  xmm0, xmmword ptr cs:FOLDERID_HomeGroup.Data1
0x180075092  movdqu  [rbp+260h+var_118], xmm0
0x18007509a  movups  xmm0, xmmword ptr cs:FOLDERID_Desktop.Data1
0x1800750a1  movdqu  [rbp+260h+var_104], xmm0
0x1800750a9  movups  xmm0, xmmword ptr cs:FOLDERID_Documents.Data1
0x1800750b0  movdqu  [rbp+260h+var_F0], xmm0
0x1800750b8  movups  xmm0, xmmword ptr cs:FOLDERID_Downloads.Data1
0x1800750bf  movdqu  [rbp+260h+var_DC], xmm0
0x1800750c7  movups  xmm0, xmmword ptr cs:FOLDERID_CameraRoll.Data1
0x1800750ce  movdqu  [rbp+260h+var_C8], xmm0
0x1800750d6  movups  xmm0, xmmword ptr cs:FOLDERID_Pictures.Data1
0x1800750dd  movdqu  [rbp+260h+var_B4], xmm0
0x1800750e5  movups  xmm0, xmmword ptr cs:FOLDERID_Music.Data1
0x1800750ec  movdqu  [rbp+260h+var_A0], xmm0
0x1800750f4  movups  xmm0, xmmword ptr cs:FOLDERID_Videos.Data1
0x1800750fb  movdqu  [rbp+260h+var_8C], xmm0
0x180075103  movups  xmm0, xmmword ptr cs:FOLDERID_Objects3D.Data1
0x18007510a  movdqu  [rbp+260h+var_78], xmm0
0x180075112  movups  xmm0, xmmword ptr cs:FOLDERID_Screenshots.Data1
0x180075119  movdqu  [rbp+260h+var_64], xmm0
0x180075121  call    memset_0
0x180075126  lea     r13, [rdi+410h]
0x18007512d  xor     edx, edx; Val
0x18007512f  mov     rcx, r13; void *
0x180075132  mov     r8d, 190h; Size
  ... truncated ...
```
