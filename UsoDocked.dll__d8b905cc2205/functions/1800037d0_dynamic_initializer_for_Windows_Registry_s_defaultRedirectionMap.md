# _dynamic_initializer_for__Windows::Registry::s_defaultRedirectionMap__

- ea: `0x1800037d0`
- end: `0x180003fd9`
- name: `_dynamic_initializer_for__Windows::Registry::s_defaultRedirectionMap__`
- size: `2057`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x1800037d0`
- `0x180007660`
- `0x180007944`
- `0x180007da0`
- `0x180007dfc`
- `0x18001ba70`
- `0x18002778c`
- `0x18003ea84`
- `0x18003ecb4`
- `0x1800401b4`

## string_xrefs

- `0x18000384e`: `Software\Microsoft\WindowsUpdate\Orchestrator`
- `0x1800038f5`: `Software\Microsoft\WindowsUpdate\UX`
- `0x1800038a2`: `Software\Microsoft\Windows\CurrentVersion\WindowsUpdate\Orchestrator`
- `0x1800039a1`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Update\TargetingInfo\DynamicInstalled`
- `0x180003948`: `Software\Microsoft\Windows\CurrentVersion\WindowsUpdate`
- `0x180003a74`: `SOFTWARE\Microsoft\Windows\CurrentVersion\Component Based Servicing\Interface`
- `0x180003a09`: `Software\Microsoft\WindowsUpdate\Orchestrator\Configurations`
- `0x180003b4a`: `Software\Microsoft\WindowsUpdate`
- `0x180003adf`: `SOFTWARE\Microsoft\Windows\CurrentVersion\DeviceAccess`
- `0x180003bb5`: `Software\Microsoft\Windows\CurrentVersion\UpdatePlatform\UX\Configurations`
- `0x180003cf6`: `Software\Microsoft\Windows\CurrentVersion\SystemProtectedUserData`

## pseudocode

```c
// Hidden C++ exception states: #wind=36
int dynamic_initializer_for__Windows::Registry::s_defaultRedirectionMap__()
{
  __int64 v0; // rbx
  __int64 v1; // r8
  __int64 v2; // r8
  __int64 v3; // r8
  __int64 v4; // r8
  __int64 v5; // r8
  __int64 v6; // r8
  __int64 v7; // r8
  __int64 v8; // r8
  __int64 v9; // r8
  __int64 v10; // r8
  __int64 v11; // r8
  __int64 v12; // r8
  __int64 v13; // r8
  __int64 v14; // r8
  __int64 v15; // r8
  __int64 v16; // rcx
  _QWORD *v17; // r14
  __int64 *v18; // rbx
  __int64 v19; // rax
  __int128 v20; // xmm6
  __int64 v21; // r15
  _OWORD *v22; // rax
  _OWORD *v23; // rsi
  char *v24; // rdi
  _QWORD *v25; // rdx
  _QWORD *v26; // rdx
  __int64 *v28; // [rsp+28h] [rbp-E0h]
  __int64 v29; // [rsp+30h] [rbp-D8h]
  __int128 v30; // [rsp+38h] [rbp-D0h] BYREF
  __int128 v31; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v32; // [rsp+68h] [rbp-A0h]
  _BYTE v33[40]; // [rsp+70h] [rbp-98h] BYREF
  __int128 v34; // [rsp+98h] [rbp-70h] BYREF
  __int64 v35; // [rsp+A8h] [rbp-60h]
  __int64 v36; // [rsp+B0h] [rbp-58h]
  __int128 v37; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v38; // [rsp+C8h] [rbp-40h]
  __int64 v39; // [rsp+D0h] [rbp-38h]
  __int128 v40; // [rsp+D8h] [rbp-30h] BYREF
  __int64 v41; // [rsp+E8h] [rbp-20h]
  __int64 v42; // [rsp+F0h] [rbp-18h]
  __int128 v43; // [rsp+F8h] [rbp-10h] BYREF
  __int64 v44; // [rsp+108h] [rbp+0h]
  __int64 v45; // [rsp+110h] [rbp+8h]
  __int128 v46; // [rsp+118h] [rbp+10h] BYREF
  __int64 v47; // [rsp+128h] [rbp+20h]
  __int64 v48; // [rsp+130h] [rbp+28h]
  __int128 v49; // [rsp+138h] [rbp+30h] BYREF
  __int64 v50; // [rsp+148h] [rbp+40h]
  __int64 v51; // [rsp+150h] [rbp+48h]
  __int128 v52; // [rsp+158h] [rbp+50h] BYREF
  __int64 v53; // [rsp+168h] [rbp+60h]
  __int64 v54; // [rsp+170h] [rbp+68h]
  __int128 v55; // [rsp+178h] [rbp+70h] BYREF
  __int64 v56; // [rsp+188h] [rbp+80h]
  __int64 v57; // [rsp+190h] [rbp+88h]
  __int128 v58; // [rsp+198h] [rbp+90h] BYREF
  __int64 v59; // [rsp+1A8h] [rbp+A0h]
  __int64 v60; // [rsp+1B0h] [rbp+A8h]
  __int128 v61; // [rsp+1B8h] [rbp+B0h] BYREF
  __int64 v62; // [rsp+1C8h] [rbp+C0h]
  __int64 v63; // [rsp+1D0h] [rbp+C8h]
  __int128 v64; // [rsp+1D8h] [rbp+D0h] BYREF
  __int64 v65; // [rsp+1E8h] [rbp+E0h]
  __int64 v66; // [rsp+1F0h] [rbp+E8h]
  __int128 v67; // [rsp+1F8h] [rbp+F0h] BYREF
  __int64 v68; // [rsp+208h] [rbp+100h]
  __int64 v69; // [rsp+210h] [rbp+108h]
  __int128 v70; // [rsp+218h] [rbp+110h] BYREF
  __int64 v71; // [rsp+228h] [rbp+120h]
  __int64 v72; // [rsp+230h] [rbp+128h]
  __int128 v73; // [rsp+238h] [rbp+130h] BYREF
  __int64 v74; // [rsp+248h] [rbp+140h]
  __int64 v75; // [rsp+250h] [rbp+148h]
  __int128 v76; // [rsp+258h] [rbp+150h] BYREF
  __int64 v77; // [rsp+268h] [rbp+160h]
  __int64 v78; // [rsp+270h] [rbp+168h]
  __int128 v79; // [rsp+278h] [rbp+170h] BYREF
  __int64 v80; // [rsp+288h] [rbp+180h]
  __int64 v81; // [rsp+290h] [rbp+188h]
  __int128 v82; // [rsp+298h] [rbp+190h] BYREF
  __int64 v83; // [rsp+2A8h] [rbp+1A0h]
  __int64 v84; // [rsp+2B0h] [rbp+1A8h]
  __int128 v85; // [rsp+2B8h] [rbp+1B0h] BYREF
  __int64 v86; // [rsp+2C8h] [rbp+1C0h]
  __int64 v87; // [rsp+2D0h] [rbp+1C8h]
  __int128 v88; // [rsp+2D8h] [rbp+1D0h] BYREF
  __int64 v89; // [rsp+2E8h] [rbp+1E0h]
  __int64 v90; // [rsp+2F0h] [rbp+1E8h]
  __int128 v91; // [rsp+2F8h] [rbp+1F0h] BYREF
  __int64 v92; // [rsp+308h] [rbp+200h]
  __int64 v93; // [rsp+310h] [rbp+208h]
  __int128 v94; // [rsp+318h] [rbp+210h] BYREF
  __int64 v95; // [rsp+328h] [rbp+220h]
  __int64 v96; // [rsp+330h] [rbp+228h]
  __int128 v97; // [rsp+338h] [rbp+230h] BYREF
  __int64 v98; // [rsp+348h] [rbp+240h]
  __int64 v99; // [rsp+350h] [rbp+248h]
  __int128 v100; // [rsp+358h] [rbp+250h] BYREF
  __int64 v101; // [rsp+368h] [rbp+260h]
  __int64 v102; // [rsp+370h] [rbp+268h]
  __int128 v103; // [rsp+378h] [rbp+270h] BYREF
  __int64 v104; // [rsp+388h] [rbp+280h]
  __int64 v105; // [rsp+390h] [rbp+288h]
  __int128 v106; // [rsp+398h] [rbp+290h] BYREF
  __int64 v107; // [rsp+3A8h] [rbp+2A0h]
  __int64 v108; // [rsp+3B0h] [rbp+2A8h]
  __int128 v109; // [rsp+3B8h] [rbp+2B0h] BYREF
  __int64 v110; // [rsp+3C8h] [rbp+2C0h]
  __int64 v111; // [rsp+3D0h] [rbp+2C8h]
  __int128 v112; // [rsp+3D8h] [rbp+2D0h] BYREF
  __int64 v113; // [rsp+3E8h] [rbp+2E0h]
  __int64 v114; // [rsp+3F0h] [rbp+2E8h]
  __int128 v115; // [rsp+3F8h] [rbp+2F0h] BYREF
  __int64 v116; // [rsp+408h] [rbp+300h]
  __int64 v117; // [rsp+410h] [rbp+308h]
  __int128 v118; // [rsp+418h] [rbp+310h] BYREF
  __int64 v119; // [rsp+428h] [rbp+320h]
  __int64 v120; // [rsp+430h] [rbp+328h]
  __int128 v121; // [rsp+438h] [rbp+330h] BYREF
  __int64 v122; // [rsp+448h] [rbp+340h]
  __int64 v123; // [rsp+450h] [rbp+348h]
  __int64 v124; // [rsp+458h] [rbp+350h] BYREF

  v31 = 0;
  v32 = 0;
  *(_QWORD *)v33 = 0;
  v0 = -1;
  v1 = -1;
  do
    ++v1;
  while ( SystemInterface::Registry::USOROOT_REDIRECTION_ID[v1] );
  std::wstring::_Construct<1,unsigned short const *>(&v31, SystemInterface::Registry::USOROOT_REDIRECTION_ID);
  memset(&v33[8], 0, 32);
  std::wstring::_Construct<1,unsigned short const *>(&v33[8], L"Software\\Microsoft\\WindowsUpdate\\Orchestrator");
  v34 = 0;
  v35 = 0;
  v36 = 0;
  v2 = -1;
  do
    ++v2;
  while ( SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID[v2] );
  std::wstring::_Construct<1,unsigned short const *>(
    &v34,
    SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID);
  v37 = 0;
  v38 = 0;
  v39 = 0;
  std::wstring::_Construct<1,unsigned short const *>(
    &v37,
    L"Software\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate\\Orchestrator");
  v40 = 0;
  v41 = 0;
  v42 = 0;
  v3 = -1;
  do
    ++v3;
  while ( SystemInterface::Registry::UPDATEUXROOT_REDIRECTION_ID[v3] );
  std::wstring::_Construct<1,unsigned short const *>(&v40, SystemInterface::Registry::UPDATEUXROOT_REDIRECTION_ID);
  v43 = 0;
  v44 = 0;
  v45 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v43, L"Software\\Microsoft\\WindowsUpdate\\UX");
  v46 = 0;
  v47 = 0;
  v48 = 0;
  v4 = -1;
  do
    ++v4;
  while ( SystemInterface::Registry::CURRENTVERSIONWU_REDIRECTION_ID[v4] );
  std::wstring::_Construct<1,unsigned short const *>(&v46, SystemInterface::Registry::CURRENTVERSIONWU_REDIRECTION_ID);
  v49 = 0;
  v50 = 0;
  v51 = 0;
  std::wstring::_Construct<1,unsigned short const *>(
    &v49,
    L"Software\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate");
  v52 = 0;
  v53 = 0;
  v54 = 0;
  v5 = -1;
  do
    ++v5;
  while ( SystemInterface::Registry::UUP_DYN_INSTALLED_PROD_REDIRECTION_ID[v5] );
  std::wstring::_Construct<1,unsigned short const *>(
    &v52,
    SystemInterface::Registry::UUP_DYN_INSTALLED_PROD_REDIRECTION_ID);
  v55 = 0;
  v56 = 0;
  v57 = 0;
  std::wstring::_Construct<1,unsigned short const *>(
    &v55,
    L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Update\\TargetingInfo\\DynamicInstalled");
  v58 = 0;
  v59 = 0;
  v60 = 0;
  v6 = -1;
  do
    ++v6;
  while ( SystemInterface::Registry::USOCONFIGURATIONROOT_REDIRECTION_ID[v6] );
  std::wstring::_Construct<1,unsigned short const *>(
    &v58,
    SystemInterface::Registry::USOCONFIGURATIONROOT_REDIRECTION_ID);
  v61 = 0;
  v62 = 0;
  v63 = 0;
  std::wstring::_Construct<1,unsigned short const *>(
    &v61,
    L"Software\\Microsoft\\WindowsUpdate\\Orchestrator\\Configurations");
  v64 = 0;
  v65 = 0;
  v66 = 0;
  v7 = -1;
  do
    ++v7;
  while ( SystemInterface::Registry::CBSINTERFACE_REDIRECTION_ID[v7] );
  std::wstring::_Construct<1,unsigned short const *>(&v64, SystemInterface::Registry::CBSINTERFACE_REDIRECTION_ID);
  v67 = 0;
  v68 = 0;
  v69 = 0;
  std::wstring::_Construct<1,unsigned short const *>(
    &v67,
    L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Component Based Servicing\\Interface");
  v70 = 0;
  v71 = 0;
  v72 = 0;
  v8 = -1;
  do
    ++v8;
  while ( SystemInterface::Registry::DEVICEACCESS_REDIRECTION_ID[v8] );
  std::wstring::_Construct<1,unsigned short const *>(&v70, SystemInterface::Registry::DEVICEACCESS_REDIRECTION_ID);
  v73 = 0;
  v74 = 0;
  v75 = 0;
  std::wstring::_Construct<1,unsigned short const *>(
    &v73,
    L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\DeviceAccess");
  v76 = 0;
  v77 = 0;
  v78 = 0;
  v9 = -1;
  do
    ++v9;
  while ( SystemInterface::Registry::WU_REDIRECTION_ID[v9] );
  std::wstring::_Construct<1,unsigned short const *>(&v76, SystemInterface::Registry::WU_REDIRECTION_ID);
  v79 = 0;
  v80 = 0;
  v81 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v79, L"Software\\Microsoft\\WindowsUpdate");
  v82 = 0;
  v83 = 0;
  v84 = 0;
  v10 = -1;
  do
    ++v10;
  while ( SystemInterface::Registry::UXCONFIGURATIONROOT_REDIRECTION_ID[v10] );
  std::wstring::_Construct<1,unsigned short const *>(
    &v82,
    SystemInterface::Registry::UXCONFIGURATIONROOT_REDIRECTION_ID);
  v85 = 0;
  v86 = 0;
  v87 = 0;
  std::wstring::_Construct<1,unsigned short const *>(
    &v85,
    L"Software\\Microsoft\\Windows\\CurrentVersion\\UpdatePlatform\\UX\\Configurations");
  v88 = 0;
  v89 = 0;
  v90 = 0;
  v11 = -1;
  do
    ++v11;
  while ( SystemInterface::Registry::RESERVEMANAGER_REDIRECTION_ID[v11] );
  std::wstring::_Construct<1,unsigned short const *>(&v88, SystemInterface::Registry::RESERVEMANAGER_REDIRECTION_ID);
  v91 = 0;
  v92 = 0;
  v93 = 0;
  std::wstring::_Construct<1,unsigned short const *>(
    &v91,
    L"Software\\Microsoft\\Windows\\CurrentVersion\\ReserveManager");
  v94 = 0;
  v95 = 0;
  v96 = 0;
  v12 = -1;
  do
    ++v12;
  while ( SystemInterface::Registry::LOGONUI_REDIRECTION_ID[v12] );
  std::wstring::_Construct<1,unsigned short const *>(&v94, SystemInterface::Registry::LOGONUI_REDIRECTION_ID);
  v97 = 0;
  v98 = 0;
  v99 = 0;
  std::wstring::_Construct<1,unsigned short const *>(
    &v97,
    L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI");
  v100 = 0;
  v101 = 0;
  v102 = 0;
  v13 = -1;
  do
    ++v13;
  while ( SystemInterface::Registry::SYSTEMPROTECTEDUSERDATA_REDIRECTION_ID[v13] );
  std::wstring::_Construct<1,unsigned short const *>(
    &v100,
    SystemInterface::Registry::SYSTEMPROTECTEDUSERDATA_REDIRECTION_ID);
  v103 = 0;
  v104 = 0;
  v105 = 0;
  std::wstring::_Construct<1,unsigned short const *>(
    &v103,
    L"Software\\Microsoft\\Windows\\CurrentVersion\\SystemProtectedUserData");
  v106 = 0;
  v107 = 0;
  v108 = 0;
  v14 = -1;
  do
    ++v14;
  while ( SystemInterface::Registry::SETUP_OOBE_REDIRECTION_ID[v14] );
  std::wstring::_Construct<1,unsigned short const *>(&v106, SystemInterface::Registry::SETUP_OOBE_REDIRECTION_ID);
  v109 = 0;
  v110 = 0;
  v111 = 0;
  std::wstring::_Construct<1,unsigned short const *>(
    &v109,
    L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Setup\\OOBE");
  v112 = 0;
  v113 = 0;
  v114 = 0;
  v15 = -1;
  do
    ++v15;
  while ( SystemInterface::Registry::WINNTCURRENTVERSIONROOT_REDIRECTION_ID[v15] );
  std::wstring::_Construct<1,unsigned short const *>(
    &v112,
    SystemInterface::Registry::WINNTCURRENTVERSIONROOT_REDIRECTION_ID);
  v115 = 0;
  v116 = 0;
  v117 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v115, L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion");
  v118 = 0;
  v119 = 0;
  v120 = 0;
  do
    ++v0;
  while ( SystemInterface::Registry::CURRENTVERSIONAPPX_REDIRECTION_ID[v0] );
  std::wstring::_Construct<1,unsigned short const *>(
    &v118,
    SystemInterface::Registry::CURRENTVERSIONAPPX_REDIRECTION_ID);
  v121 = 0;
  v122 = 0;
  v123 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v121, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Appx");
  Windows::Registry::s_defaultRedirectionMap = 0;
  qword_180096480 = 0;
  v17 = operator new(0x60u);
  *v17 = v17;
  v17[1] = v17;
  v17[2] = v17;
  *((_WORD *)v17 + 12) = 257;
  Windows::Registry::s_defaultRedirectionMap = (__int64)v17;
  v18 = (__int64 *)&v31;
  do
  {
    v19 = std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Find_hint<std::wstring>(
            v16,
            &v30,
            v17,
            v18,
            v28,
            v29);
    v20 = *(_OWORD *)v19;
    if ( !*(_BYTE *)(v19 + 16) )
    {
      if ( qword_180096480 == 0x2AAAAAAAAAAAAAALL )
        std::_Throw_tree_length_error();
      v21 = Windows::Registry::s_defaultRedirectionMap;
      v28 = &Windows::Registry::s_defaultRedirectionMap;
      v22 = operator new(0x60u);
      v23 = v22;
      v24 = (char *)(v22 + 2);
      *(_QWORD *)&v30 = v22 + 2;
      v22[2] = 0;
      *((_QWORD *)v22 + 6) = 0;
      *((_QWORD *)v22 + 7) = 0;
      if ( (unsigned __int64)v18[3] <= 7 )
        v25 = v18;
      else
        v25 = (_QWORD *)*v18;
      std::wstring::_Construct<2,unsigned short const *>(v22 + 2, v25, v18[2]);
      v26 = v18 + 4;
      *((_OWORD *)v24 + 2) = 0;
      *((_QWORD *)v24 + 6) = 0;
      *((_QWORD *)v24 + 7) = 0;
      if ( (unsigned __int64)v18[7] > 7 )
        v26 = (_QWORD *)*v26;
      std::wstring::_Construct<2,unsigned short const *>(v24 + 32, v26, v18[6]);
      *(_QWORD *)v23 = v21;
      *((_QWORD *)v23 + 1) = v21;
      *((_QWORD *)v23 + 2) = v21;
      *((_WORD *)v23 + 12) = 0;
      v29 = 0;
      v30 = v20;
      std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,unsigned int>>>::_Insert_node(
        &Windows::Registry::s_defaultRedirectionMap,
        &v30,
        v23);
    }
    v18 += 8;
  }
  while ( v18 != &v124 );
  `eh vector destructor iterator'(
    &v31,
    0x40u,
    0x10u,
    std::pair<std::wstring const,std::wstring>::~pair<std::wstring const,std::wstring>);
  return atexit(dynamic_atexit_destructor_for__Windows::Registry::s_defaultRedirectionMap__);
}

```

## disassembly

```asm
0x1800037d0  mov     rax, rsp
0x1800037d3  push    rbp
0x1800037d4  push    rbx
0x1800037d5  push    rsi
0x1800037d6  push    rdi
0x1800037d7  push    r12
0x1800037d9  push    r14
0x1800037db  push    r15
0x1800037dd  lea     rbp, [rax-3A8h]
0x1800037e4  sub     rsp, 470h
0x1800037eb  movaps  xmmword ptr [rax-48h], xmm6
0x1800037ef  mov     rax, cs:__security_cookie
0x1800037f6  xor     rax, rsp
0x1800037f9  mov     [rbp+3A0h+var_50], rax
0x180003800  mov     rdx, cs:?USOROOT_REDIRECTION_ID@Registry@SystemInterface@@2QEBGEB; ushort const * const SystemInterface::Registry::USOROOT_REDIRECTION_ID
0x180003807  xorps   xmm0, xmm0
0x18000380a  movups  [rsp+4A0h+var_458+8], xmm0
0x18000380f  xor     r12d, r12d
0x180003812  mov     [rsp+4A0h+var_440], r12
0x180003817  mov     qword ptr [rsp+4A0h+var_438], r12
0x18000381c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180003820  mov     r8, rbx
0x180003823  inc     r8
0x180003826  cmp     [rdx+r8*2], r12w
0x18000382b  jnz     short loc_180003823
0x18000382d  lea     rcx, [rsp+4A0h+var_458+8]
0x180003832  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180003837  nop
0x180003838  xorps   xmm0, xmm0
0x18000383b  movups  xmmword ptr [rsp+4A0h+var_438+8], xmm0
0x180003840  mov     [rbp+3A0h+var_420], r12
0x180003844  mov     [rbp+3A0h+var_418], r12
0x180003848  mov     r8d, 2Dh ; '-'
0x18000384e  lea     rdx, aSoftwareMicros_7; "Software\\Microsoft\\WindowsUpdate\\Orc"...
0x180003855  lea     rcx, [rsp+4A0h+var_438+8]
0x18000385a  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000385f  nop
0x180003860  mov     rdx, cs:?USOCURRENTVERSIONROOT_REDIRECTION_ID@Registry@SystemInterface@@2QEBGEB; ushort const * const SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID
0x180003867  xorps   xmm0, xmm0
0x18000386a  movups  [rbp+3A0h+var_410], xmm0
0x18000386e  mov     [rbp+3A0h+var_400], r12
0x180003872  mov     [rbp+3A0h+var_3F8], r12
0x180003876  mov     r8, rbx
0x180003879  inc     r8
0x18000387c  cmp     [rdx+r8*2], r12w
0x180003881  jnz     short loc_180003879
0x180003883  lea     rcx, [rbp+3A0h+var_410]
0x180003887  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000388c  nop
0x18000388d  xorps   xmm0, xmm0
0x180003890  movups  [rbp+3A0h+var_3F0], xmm0
0x180003894  mov     [rbp+3A0h+var_3E0], r12
0x180003898  mov     [rbp+3A0h+var_3D8], r12
0x18000389c  mov     r8d, 44h ; 'D'
0x1800038a2  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800038a9  lea     rcx, [rbp+3A0h+var_3F0]
0x1800038ad  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800038b2  nop
0x1800038b3  mov     rdx, cs:?UPDATEUXROOT_REDIRECTION_ID@Registry@SystemInterface@@2QEBGEB; ushort const * const SystemInterface::Registry::UPDATEUXROOT_REDIRECTION_ID
0x1800038ba  xorps   xmm0, xmm0
0x1800038bd  movups  [rbp+3A0h+var_3D0], xmm0
0x1800038c1  mov     [rbp+3A0h+var_3C0], r12
0x1800038c5  mov     [rbp+3A0h+var_3B8], r12
0x1800038c9  mov     r8, rbx
0x1800038cc  inc     r8
0x1800038cf  cmp     [rdx+r8*2], r12w
0x1800038d4  jnz     short loc_1800038CC
0x1800038d6  lea     rcx, [rbp+3A0h+var_3D0]
0x1800038da  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800038df  nop
0x1800038e0  xorps   xmm0, xmm0
0x1800038e3  movups  [rbp+3A0h+var_3B0], xmm0
0x1800038e7  mov     [rbp+3A0h+var_3A0], r12
0x1800038eb  mov     [rbp+3A0h+var_398], r12
0x1800038ef  mov     r8d, 23h ; '#'
0x1800038f5  lea     rdx, aSoftwareMicros_16; "Software\\Microsoft\\WindowsUpdate\\UX"
0x1800038fc  lea     rcx, [rbp+3A0h+var_3B0]
0x180003900  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180003905  nop
0x180003906  mov     rdx, cs:?CURRENTVERSIONWU_REDIRECTION_ID@Registry@SystemInterface@@2QEBGEB; ushort const * const SystemInterface::Registry::CURRENTVERSIONWU_REDIRECTION_ID
0x18000390d  xorps   xmm0, xmm0
0x180003910  movups  [rbp+3A0h+var_390], xmm0
0x180003914  mov     [rbp+3A0h+var_380], r12
0x180003918  mov     [rbp+3A0h+var_378], r12
0x18000391c  mov     r8, rbx
0x18000391f  inc     r8
0x180003922  cmp     [rdx+r8*2], r12w
0x180003927  jnz     short loc_18000391F
0x180003929  lea     rcx, [rbp+3A0h+var_390]
0x18000392d  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180003932  nop
0x180003933  xorps   xmm0, xmm0
0x180003936  movups  [rbp+3A0h+var_370], xmm0
0x18000393a  mov     [rbp+3A0h+var_360], r12
0x18000393e  mov     [rbp+3A0h+var_358], r12
0x180003942  mov     r8d, 37h ; '7'
0x180003948  lea     rdx, aSoftwareMicros_11; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000394f  lea     rcx, [rbp+3A0h+var_370]
0x180003953  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180003958  nop
0x180003959  mov     rdx, cs:?UUP_DYN_INSTALLED_PROD_REDIRECTION_ID@Registry@SystemInterface@@2QEBGEB; ushort const * const SystemInterface::Registry::UUP_DYN_INSTALLED_PROD_REDIRECTION_ID
0x180003960  xorps   xmm0, xmm0
0x180003963  movups  [rbp+3A0h+var_350], xmm0
0x180003967  mov     [rbp+3A0h+var_340], r12
0x18000396b  mov     [rbp+3A0h+var_338], r12
0x18000396f  mov     r8, rbx
0x180003972  inc     r8
0x180003975  cmp     [rdx+r8*2], r12w
0x18000397a  jnz     short loc_180003972
0x18000397c  lea     rcx, [rbp+3A0h+var_350]
0x180003980  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180003985  nop
0x180003986  xorps   xmm0, xmm0
0x180003989  movups  [rbp+3A0h+var_330], xmm0
0x18000398d  mov     [rbp+3A0h+var_320], r12
0x180003994  mov     [rbp+3A0h+var_318], r12
0x18000399b  mov     r8d, 52h ; 'R'
0x1800039a1  lea     rdx, aSoftwareMicros_17; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800039a8  lea     rcx, [rbp+3A0h+var_330]
0x1800039ac  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800039b1  nop
0x1800039b2  mov     rdx, cs:?USOCONFIGURATIONROOT_REDIRECTION_ID@Registry@SystemInterface@@2QEBGEB; ushort const * const SystemInterface::Registry::USOCONFIGURATIONROOT_REDIRECTION_ID
0x1800039b9  xorps   xmm0, xmm0
0x1800039bc  movups  [rbp+3A0h+var_310], xmm0
0x1800039c3  mov     [rbp+3A0h+var_300], r12
0x1800039ca  mov     [rbp+3A0h+var_2F8], r12
0x1800039d1  mov     r8, rbx
0x1800039d4  inc     r8
0x1800039d7  cmp     [rdx+r8*2], r12w
0x1800039dc  jnz     short loc_1800039D4
0x1800039de  lea     rcx, [rbp+3A0h+var_310]
0x1800039e5  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800039ea  nop
0x1800039eb  xorps   xmm0, xmm0
0x1800039ee  movups  [rbp+3A0h+var_2F0], xmm0
0x1800039f5  mov     [rbp+3A0h+var_2E0], r12
0x1800039fc  mov     [rbp+3A0h+var_2D8], r12
0x180003a03  mov     r8d, 3Ch ; '<'
0x180003a09  lea     rdx, aSoftwareMicros_13; "Software\\Microsoft\\WindowsUpdate\\Orc"...
0x180003a10  lea     rcx, [rbp+3A0h+var_2F0]
0x180003a17  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180003a1c  nop
0x180003a1d  mov     rdx, cs:?CBSINTERFACE_REDIRECTION_ID@Registry@SystemInterface@@2QEBGEB; ushort const * const SystemInterface::Registry::CBSINTERFACE_REDIRECTION_ID
0x180003a24  xorps   xmm0, xmm0
0x180003a27  movups  [rbp+3A0h+var_2D0], xmm0
0x180003a2e  mov     [rbp+3A0h+var_2C0], r12
0x180003a35  mov     [rbp+3A0h+var_2B8], r12
0x180003a3c  mov     r8, rbx
0x180003a3f  inc     r8
0x180003a42  cmp     [rdx+r8*2], r12w
0x180003a47  jnz     short loc_180003A3F
0x180003a49  lea     rcx, [rbp+3A0h+var_2D0]
0x180003a50  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180003a55  nop
0x180003a56  xorps   xmm0, xmm0
0x180003a59  movups  [rbp+3A0h+var_2B0], xmm0
0x180003a60  mov     [rbp+3A0h+var_2A0], r12
0x180003a67  mov     [rbp+3A0h+var_298], r12
0x180003a6e  mov     r8d, 4Dh ; 'M'
0x180003a74  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180003a7b  lea     rcx, [rbp+3A0h+var_2B0]
0x180003a82  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180003a87  nop
0x180003a88  mov     rdx, cs:?DEVICEACCESS_REDIRECTION_ID@Registry@SystemInterface@@2QEBGEB; ushort const * const SystemInterface::Registry::DEVICEACCESS_REDIRECTION_ID
0x180003a8f  xorps   xmm0, xmm0
0x180003a92  movups  [rbp+3A0h+var_290], xmm0
0x180003a99  mov     [rbp+3A0h+var_280], r12
0x180003aa0  mov     [rbp+3A0h+var_278], r12
0x180003aa7  mov     r8, rbx
0x180003aaa  inc     r8
0x180003aad  cmp     [rdx+r8*2], r12w
0x180003ab2  jnz     short loc_180003AAA
0x180003ab4  lea     rcx, [rbp+3A0h+var_290]
0x180003abb  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180003ac0  nop
0x180003ac1  xorps   xmm0, xmm0
0x180003ac4  movups  [rbp+3A0h+var_270], xmm0
0x180003acb  mov     [rbp+3A0h+var_260], r12
0x180003ad2  mov     [rbp+3A0h+var_258], r12
0x180003ad9  mov     r8d, 36h ; '6'
0x180003adf  lea     rdx, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180003ae6  lea     rcx, [rbp+3A0h+var_270]
0x180003aed  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180003af2  nop
0x180003af3  mov     rdx, cs:?WU_REDIRECTION_ID@Registry@SystemInterface@@2QEBGEB; ushort const * const SystemInterface::Registry::WU_REDIRECTION_ID
0x180003afa  xorps   xmm0, xmm0
0x180003afd  movups  [rbp+3A0h+var_250], xmm0
0x180003b04  mov     [rbp+3A0h+var_240], r12
0x180003b0b  mov     [rbp+3A0h+var_238], r12
0x180003b12  mov     r8, rbx
0x180003b15  inc     r8
0x180003b18  cmp     [rdx+r8*2], r12w
0x180003b1d  jnz     short loc_180003B15
0x180003b1f  lea     rcx, [rbp+3A0h+var_250]
0x180003b26  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180003b2b  nop
0x180003b2c  xorps   xmm0, xmm0
0x180003b2f  movups  [rbp+3A0h+var_230], xmm0
0x180003b36  mov     [rbp+3A0h+var_220], r12
0x180003b3d  mov     [rbp+3A0h+var_218], r12
0x180003b44  mov     r8d, 20h ; ' '
0x180003b4a  lea     rdx, aSoftwareMicros_12; "Software\\Microsoft\\WindowsUpdate"
0x180003b51  lea     rcx, [rbp+3A0h+var_230]
0x180003b58  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180003b5d  nop
0x180003b5e  mov     rdx, cs:?UXCONFIGURATIONROOT_REDIRECTION_ID@Registry@SystemInterface@@2QEBGEB; ushort const * const SystemInterface::Registry::UXCONFIGURATIONROOT_REDIRECTION_ID
0x180003b65  xorps   xmm0, xmm0
0x180003b68  movups  [rbp+3A0h+var_210], xmm0
0x180003b6f  mov     [rbp+3A0h+var_200], r12
0x180003b76  mov     [rbp+3A0h+var_1F8], r12
0x180003b7d  mov     r8, rbx
0x180003b80  inc     r8
0x180003b83  cmp     [rdx+r8*2], r12w
0x180003b88  jnz     short loc_180003B80
0x180003b8a  lea     rcx, [rbp+3A0h+var_210]
0x180003b91  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180003b96  nop
0x180003b97  xorps   xmm0, xmm0
0x180003b9a  movups  [rbp+3A0h+var_1F0], xmm0
0x180003ba1  mov     [rbp+3A0h+var_1E0], r12
0x180003ba8  mov     [rbp+3A0h+var_1D8], r12
0x180003baf  mov     r8d, 4Ah ; 'J'
0x180003bb5  lea     rdx, aSoftwareMicros_18; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180003bbc  lea     rcx, [rbp+3A0h+var_1F0]
0x180003bc3  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180003bc8  nop
0x180003bc9  mov     rdx, cs:?RESERVEMANAGER_REDIRECTION_ID@Registry@SystemInterface@@2QEBGEB; ushort const * const SystemInterface::Registry::RESERVEMANAGER_REDIRECTION_ID
0x180003bd0  xorps   xmm0, xmm0
0x180003bd3  movups  [rbp+3A0h+var_1D0], xmm0
0x180003bda  mov     [rbp+3A0h+var_1C0], r12
0x180003be1  mov     [rbp+3A0h+var_1B8], r12
0x180003be8  mov     r8, rbx
0x180003beb  inc     r8
0x180003bee  cmp     [rdx+r8*2], r12w
0x180003bf3  jnz     short loc_180003BEB
0x180003bf5  lea     rcx, [rbp+3A0h+var_1D0]
0x180003bfc  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180003c01  nop
0x180003c02  xorps   xmm0, xmm0
0x180003c05  movups  [rbp+3A0h+var_1B0], xmm0
0x180003c0c  mov     [rbp+3A0h+var_1A0], r12
0x180003c13  mov     [rbp+3A0h+var_198], r12
0x180003c1a  mov     r8d, 38h ; '8'
0x180003c20  lea     rdx, aSoftwareMicros_19; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180003c27  lea     rcx, [rbp+3A0h+var_1B0]
0x180003c2e  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180003c33  nop
0x180003c34  mov     rdx, cs:?LOGONUI_REDIRECTION_ID@Registry@SystemInterface@@2QEBGEB; ushort const * const SystemInterface::Registry::LOGONUI_REDIRECTION_ID
0x180003c3b  xorps   xmm0, xmm0
0x180003c3e  movups  [rbp+3A0h+var_190], xmm0
0x180003c45  mov     [rbp+3A0h+var_180], r12
0x180003c4c  mov     [rbp+3A0h+var_178], r12
0x180003c53  mov     r8, rbx
0x180003c56  inc     r8
0x180003c59  cmp     [rdx+r8*2], r12w
0x180003c5e  jnz     short loc_180003C56
0x180003c60  lea     rcx, [rbp+3A0h+var_190]
0x180003c67  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180003c6c  nop
0x180003c6d  xorps   xmm0, xmm0
0x180003c70  movups  [rbp+3A0h+var_170], xmm0
0x180003c77  mov     [rbp+3A0h+var_160], r12
0x180003c7e  mov     [rbp+3A0h+var_158], r12
0x180003c85  mov     r8d, 40h ; '@'
0x180003c8b  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180003c92  lea     rcx, [rbp+3A0h+var_170]
0x180003c99  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180003c9e  nop
0x180003c9f  mov     rdx, cs:?SYSTEMPROTECTEDUSERDATA_REDIRECTION_ID@Registry@SystemInterface@@2QEBGEB; ushort const * const SystemInterface::Registry::SYSTEMPROTECTEDUSERDATA_REDIRECTION_ID
0x180003ca6  xorps   xmm0, xmm0
0x180003ca9  movups  [rbp+3A0h+var_150], xmm0
0x180003cb0  mov     [rbp+3A0h+var_140], r12
0x180003cb7  mov     [rbp+3A0h+var_138], r12
0x180003cbe  mov     r8, rbx
0x180003cc1  inc     r8
0x180003cc4  cmp     [rdx+r8*2], r12w
0x180003cc9  jnz     short loc_180003CC1
0x180003ccb  lea     rcx, [rbp+3A0h+var_150]
0x180003cd2  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180003cd7  nop
0x180003cd8  xorps   xmm0, xmm0
0x180003cdb  movups  [rbp+3A0h+var_130], xmm0
0x180003ce2  mov     [rbp+3A0h+var_120], r12
0x180003ce9  mov     [rbp+3A0h+var_118], r12
0x180003cf0  mov     r8d, 41h ; 'A'
0x180003cf6  lea     rdx, aSoftwareMicros_9; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180003cfd  lea     rcx, [rbp+3A0h+var_130]
0x180003d04  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180003d09  nop
0x180003d0a  mov     rdx, cs:?SETUP_OOBE_REDIRECTION_ID@Registry@SystemInterface@@2QEBGEB; ushort const * const SystemInterface::Registry::SETUP_OOBE_REDIRECTION_ID
0x180003d11  xorps   xmm0, xmm0
0x180003d14  movups  [rbp+3A0h+var_110], xmm0
0x180003d1b  mov     [rbp+3A0h+var_100], r12
0x180003d22  mov     [rbp+3A0h+var_F8], r12
0x180003d29  mov     r8, rbx
0x180003d2c  inc     r8
0x180003d2f  cmp     [rdx+r8*2], r12w
0x180003d34  jnz     short loc_180003D2C
0x180003d36  lea     rcx, [rbp+3A0h+var_110]
0x180003d3d  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
  ... truncated ...
```
