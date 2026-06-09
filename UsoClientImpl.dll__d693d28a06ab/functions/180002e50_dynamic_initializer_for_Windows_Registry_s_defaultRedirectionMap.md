# _dynamic_initializer_for__Windows::Registry::s_defaultRedirectionMap__

- ea: `0x180002e50`
- end: `0x180003a91`
- name: `_dynamic_initializer_for__Windows::Registry::s_defaultRedirectionMap__`
- size: `3137`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180002e50`
- `0x1800338a4`
- `0x180033b00`
- `0x18003b68c`
- `0x18003b8e0`
- `0x18003d710`
- `0x180056524`
- `0x180056568`
- `0x1800569e8`

## string_xrefs

- `0x180002f1b`: `Software\Microsoft\Windows\CurrentVersion\WindowsUpdate\Orchestrator`
- `0x180002ec7`: `Software\Microsoft\WindowsUpdate\Orchestrator`
- `0x180002f71`: `Software\Microsoft\WindowsUpdate\UX`
- `0x18000307c`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Update\TargetingInfo\DynamicInstalled`
- `0x18000301a`: `Software\Microsoft\Windows\CurrentVersion\WindowsUpdate`
- `0x180003146`: `SOFTWARE\Microsoft\Windows\CurrentVersion\Component Based Servicing\Interface`
- `0x1800030e1`: `Software\Microsoft\WindowsUpdate\Orchestrator\Configurations`
- `0x180003215`: `Software\Microsoft\WindowsUpdate`
- `0x1800031ae`: `SOFTWARE\Microsoft\Windows\CurrentVersion\DeviceAccess`
- `0x18000327a`: `Software\Microsoft\Windows\CurrentVersion\UpdatePlatform\UX\Configurations`
- `0x1800033ab`: `Software\Microsoft\Windows\CurrentVersion\SystemProtectedUserData`
- `0x18000353f`: `Software\Microsoft\Windows\CurrentVersion\Uninstall`
- `0x180003606`: `Software\Microsoft\Windows\CurrentVersion\InstallService`
- `0x1800035a4`: `Software\Wow6432Node\Microsoft\Windows\CurrentVersion\Uninstall`

## pseudocode

```c
// Hidden C++ exception states: #wind=60
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
  __int64 v16; // r8
  __int64 v17; // r8
  __int64 v18; // r8
  __int64 v19; // r8
  __int64 v20; // r8
  __int64 v21; // r8
  __int64 v22; // r8
  __int64 v23; // r8
  __int64 v24; // r8
  __int64 v25; // r8
  __int64 v26; // r8
  __int64 v27; // r8
  __int64 v28; // rcx
  _QWORD *v29; // r14
  _BYTE *v30; // rsi
  __int64 v31; // rax
  __int128 v32; // xmm6
  __int64 v33; // rbx
  __int64 *v34; // rdi
  __int64 *v36; // [rsp+28h] [rbp-E0h]
  _QWORD v37[3]; // [rsp+30h] [rbp-D8h] BYREF
  __int64 v38; // [rsp+48h] [rbp-C0h]
  _BYTE v39[40]; // [rsp+50h] [rbp-B8h] BYREF
  _OWORD v40[2]; // [rsp+78h] [rbp-90h] BYREF
  _OWORD v41[2]; // [rsp+98h] [rbp-70h] BYREF
  _OWORD v42[2]; // [rsp+B8h] [rbp-50h] BYREF
  _OWORD v43[2]; // [rsp+D8h] [rbp-30h] BYREF
  _OWORD v44[2]; // [rsp+F8h] [rbp-10h] BYREF
  _OWORD v45[2]; // [rsp+118h] [rbp+10h] BYREF
  _OWORD v46[2]; // [rsp+138h] [rbp+30h] BYREF
  _OWORD v47[2]; // [rsp+158h] [rbp+50h] BYREF
  _OWORD v48[2]; // [rsp+178h] [rbp+70h] BYREF
  _OWORD v49[2]; // [rsp+198h] [rbp+90h] BYREF
  _OWORD v50[2]; // [rsp+1B8h] [rbp+B0h] BYREF
  _OWORD v51[2]; // [rsp+1D8h] [rbp+D0h] BYREF
  _OWORD v52[2]; // [rsp+1F8h] [rbp+F0h] BYREF
  _OWORD v53[2]; // [rsp+218h] [rbp+110h] BYREF
  _OWORD v54[2]; // [rsp+238h] [rbp+130h] BYREF
  _OWORD v55[2]; // [rsp+258h] [rbp+150h] BYREF
  _OWORD v56[2]; // [rsp+278h] [rbp+170h] BYREF
  _OWORD v57[2]; // [rsp+298h] [rbp+190h] BYREF
  _OWORD v58[2]; // [rsp+2B8h] [rbp+1B0h] BYREF
  _OWORD v59[2]; // [rsp+2D8h] [rbp+1D0h] BYREF
  _OWORD v60[2]; // [rsp+2F8h] [rbp+1F0h] BYREF
  _OWORD v61[2]; // [rsp+318h] [rbp+210h] BYREF
  _OWORD v62[2]; // [rsp+338h] [rbp+230h] BYREF
  _OWORD v63[2]; // [rsp+358h] [rbp+250h] BYREF
  _OWORD v64[2]; // [rsp+378h] [rbp+270h] BYREF
  _OWORD v65[2]; // [rsp+398h] [rbp+290h] BYREF
  _OWORD v66[2]; // [rsp+3B8h] [rbp+2B0h] BYREF
  _OWORD v67[2]; // [rsp+3D8h] [rbp+2D0h] BYREF
  _OWORD v68[2]; // [rsp+3F8h] [rbp+2F0h] BYREF
  _OWORD v69[2]; // [rsp+418h] [rbp+310h] BYREF
  _OWORD v70[2]; // [rsp+438h] [rbp+330h] BYREF
  _OWORD v71[2]; // [rsp+458h] [rbp+350h] BYREF
  _OWORD v72[2]; // [rsp+478h] [rbp+370h] BYREF
  _OWORD v73[2]; // [rsp+498h] [rbp+390h] BYREF
  _OWORD v74[2]; // [rsp+4B8h] [rbp+3B0h] BYREF
  _OWORD v75[2]; // [rsp+4D8h] [rbp+3D0h] BYREF
  _OWORD v76[2]; // [rsp+4F8h] [rbp+3F0h] BYREF
  _OWORD v77[2]; // [rsp+518h] [rbp+410h] BYREF
  _OWORD v78[2]; // [rsp+538h] [rbp+430h] BYREF
  _OWORD v79[2]; // [rsp+558h] [rbp+450h] BYREF
  _OWORD v80[2]; // [rsp+578h] [rbp+470h] BYREF
  _OWORD v81[2]; // [rsp+598h] [rbp+490h] BYREF
  _OWORD v82[2]; // [rsp+5B8h] [rbp+4B0h] BYREF
  _OWORD v83[2]; // [rsp+5D8h] [rbp+4D0h] BYREF
  _OWORD v84[2]; // [rsp+5F8h] [rbp+4F0h] BYREF
  _OWORD v85[2]; // [rsp+618h] [rbp+510h] BYREF
  _OWORD v86[2]; // [rsp+638h] [rbp+530h] BYREF
  _OWORD v87[2]; // [rsp+658h] [rbp+550h] BYREF
  _OWORD v88[2]; // [rsp+678h] [rbp+570h] BYREF
  _OWORD v89[2]; // [rsp+698h] [rbp+590h] BYREF
  _OWORD v90[2]; // [rsp+6B8h] [rbp+5B0h] BYREF
  _OWORD v91[2]; // [rsp+6D8h] [rbp+5D0h] BYREF
  _OWORD v92[2]; // [rsp+6F8h] [rbp+5F0h] BYREF
  _OWORD v93[2]; // [rsp+718h] [rbp+610h] BYREF
  _OWORD v94[2]; // [rsp+738h] [rbp+630h] BYREF
  _BYTE v95[48]; // [rsp+758h] [rbp+650h] BYREF

  memset(&v39[8], 0, 32);
  v0 = -1;
  v1 = -1;
  do
    ++v1;
  while ( SystemInterface::Registry::USOROOT_REDIRECTION_ID[v1] );
  std::wstring::_Construct<1,wchar_t const *>(&v39[8]);
  memset(v40, 0, sizeof(v40));
  std::wstring::_Construct<1,wchar_t const *>(v40);
  memset(v41, 0, sizeof(v41));
  v2 = -1;
  do
    ++v2;
  while ( SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID[v2] );
  std::wstring::_Construct<1,wchar_t const *>(v41);
  memset(v42, 0, sizeof(v42));
  std::wstring::_Construct<1,wchar_t const *>(v42);
  memset(v43, 0, sizeof(v43));
  v3 = -1;
  do
    ++v3;
  while ( SystemInterface::Registry::UPDATEUXROOT_REDIRECTION_ID[v3] );
  std::wstring::_Construct<1,wchar_t const *>(v43);
  memset(v44, 0, sizeof(v44));
  std::wstring::_Construct<1,wchar_t const *>(v44);
  memset(v45, 0, sizeof(v45));
  v4 = -1;
  do
    ++v4;
  while ( SystemInterface::Registry::CURRENTVERSION_REDIRECTION_ID[v4] );
  std::wstring::_Construct<1,wchar_t const *>(v45);
  memset(v46, 0, sizeof(v46));
  std::wstring::_Construct<1,wchar_t const *>(v46);
  memset(v47, 0, sizeof(v47));
  v5 = -1;
  do
    ++v5;
  while ( SystemInterface::Registry::CURRENTVERSIONWU_REDIRECTION_ID[v5] );
  std::wstring::_Construct<1,wchar_t const *>(v47);
  memset(v48, 0, sizeof(v48));
  std::wstring::_Construct<1,wchar_t const *>(v48);
  memset(v49, 0, sizeof(v49));
  v6 = -1;
  do
    ++v6;
  while ( SystemInterface::Registry::UUP_DYN_INSTALLED_PROD_REDIRECTION_ID[v6] );
  std::wstring::_Construct<1,wchar_t const *>(v49);
  memset(v50, 0, sizeof(v50));
  std::wstring::_Construct<1,wchar_t const *>(v50);
  memset(v51, 0, sizeof(v51));
  v7 = -1;
  do
    ++v7;
  while ( SystemInterface::Registry::USOCONFIGURATIONROOT_REDIRECTION_ID[v7] );
  std::wstring::_Construct<1,wchar_t const *>(v51);
  memset(v52, 0, sizeof(v52));
  std::wstring::_Construct<1,wchar_t const *>(v52);
  memset(v53, 0, sizeof(v53));
  v8 = -1;
  do
    ++v8;
  while ( SystemInterface::Registry::CBSINTERFACE_REDIRECTION_ID[v8] );
  std::wstring::_Construct<1,wchar_t const *>(v53);
  memset(v54, 0, sizeof(v54));
  std::wstring::_Construct<1,wchar_t const *>(v54);
  memset(v55, 0, sizeof(v55));
  v9 = -1;
  do
    ++v9;
  while ( SystemInterface::Registry::DEVICEACCESS_REDIRECTION_ID[v9] );
  std::wstring::_Construct<1,wchar_t const *>(v55);
  memset(v56, 0, sizeof(v56));
  std::wstring::_Construct<1,wchar_t const *>(v56);
  memset(v57, 0, sizeof(v57));
  v10 = -1;
  do
    ++v10;
  while ( SystemInterface::Registry::WU_REDIRECTION_ID[v10] );
  std::wstring::_Construct<1,wchar_t const *>(v57);
  memset(v58, 0, sizeof(v58));
  std::wstring::_Construct<1,wchar_t const *>(v58);
  memset(v59, 0, sizeof(v59));
  v11 = -1;
  do
    ++v11;
  while ( SystemInterface::Registry::UXCONFIGURATIONROOT_REDIRECTION_ID[v11] );
  std::wstring::_Construct<1,wchar_t const *>(v59);
  memset(v60, 0, sizeof(v60));
  std::wstring::_Construct<1,wchar_t const *>(v60);
  memset(v61, 0, sizeof(v61));
  v12 = -1;
  do
    ++v12;
  while ( SystemInterface::Registry::RESERVEMANAGER_REDIRECTION_ID[v12] );
  std::wstring::_Construct<1,wchar_t const *>(v61);
  memset(v62, 0, sizeof(v62));
  std::wstring::_Construct<1,wchar_t const *>(v62);
  memset(v63, 0, sizeof(v63));
  v13 = -1;
  do
    ++v13;
  while ( SystemInterface::Registry::LOGONUI_REDIRECTION_ID[v13] );
  std::wstring::_Construct<1,wchar_t const *>(v63);
  memset(v64, 0, sizeof(v64));
  std::wstring::_Construct<1,wchar_t const *>(v64);
  memset(v65, 0, sizeof(v65));
  v14 = -1;
  do
    ++v14;
  while ( SystemInterface::Registry::SYSTEMPROTECTEDUSERDATA_REDIRECTION_ID[v14] );
  std::wstring::_Construct<1,wchar_t const *>(v65);
  memset(v66, 0, sizeof(v66));
  std::wstring::_Construct<1,wchar_t const *>(v66);
  memset(v67, 0, sizeof(v67));
  v15 = -1;
  do
    ++v15;
  while ( SystemInterface::Registry::SETUP_OOBE_REDIRECTION_ID[v15] );
  std::wstring::_Construct<1,wchar_t const *>(v67);
  memset(v68, 0, sizeof(v68));
  std::wstring::_Construct<1,wchar_t const *>(v68);
  memset(v69, 0, sizeof(v69));
  v16 = -1;
  do
    ++v16;
  while ( SystemInterface::Registry::WINNTCURRENTVERSIONROOT_REDIRECTION_ID[v16] );
  std::wstring::_Construct<1,wchar_t const *>(v69);
  memset(v70, 0, sizeof(v70));
  std::wstring::_Construct<1,wchar_t const *>(v70);
  memset(v71, 0, sizeof(v71));
  v17 = -1;
  do
    ++v17;
  while ( SystemInterface::Registry::SYSTEM_SETUP_REDIRECTIONID[v17] );
  std::wstring::_Construct<1,wchar_t const *>(v71);
  memset(v72, 0, sizeof(v72));
  std::wstring::_Construct<1,wchar_t const *>(v72);
  memset(v73, 0, sizeof(v73));
  v18 = -1;
  do
    ++v18;
  while ( SystemInterface::Registry::WIN32_UNINSTALL_REDIRECTIONID[v18] );
  std::wstring::_Construct<1,wchar_t const *>(v73);
  memset(v74, 0, sizeof(v74));
  std::wstring::_Construct<1,wchar_t const *>(v74);
  memset(v75, 0, sizeof(v75));
  v19 = -1;
  do
    ++v19;
  while ( SystemInterface::Registry::WIN32_UNINSTALL_ALT_REDIRECTIONID[v19] );
  std::wstring::_Construct<1,wchar_t const *>(v75);
  memset(v76, 0, sizeof(v76));
  std::wstring::_Construct<1,wchar_t const *>(v76);
  memset(v77, 0, sizeof(v77));
  v20 = -1;
  do
    ++v20;
  while ( SystemInterface::Registry::INSTALLSERVICECURRENTVERSIONROOT_REDIRECTION_ID[v20] );
  std::wstring::_Construct<1,wchar_t const *>(v77);
  memset(v78, 0, sizeof(v78));
  std::wstring::_Construct<1,wchar_t const *>(v78);
  memset(v79, 0, sizeof(v79));
  v21 = -1;
  do
    ++v21;
  while ( SystemInterface::Registry::POLICIES_MICROSOFT_WINDOWS_REDIRECTION_ID[v21] );
  std::wstring::_Construct<1,wchar_t const *>(v79);
  memset(v80, 0, sizeof(v80));
  std::wstring::_Construct<1,wchar_t const *>(v80);
  memset(v81, 0, sizeof(v81));
  v22 = -1;
  do
    ++v22;
  while ( SystemInterface::Registry::CURRENTCONTROLSETCONTROL_REDIRECTION_ID[v22] );
  std::wstring::_Construct<1,wchar_t const *>(v81);
  memset(v82, 0, sizeof(v82));
  std::wstring::_Construct<1,wchar_t const *>(v82);
  memset(v83, 0, sizeof(v83));
  v23 = -1;
  do
    ++v23;
  while ( SystemInterface::Registry::POLICYMANAGER_CURRENT_DHM_ID[v23] );
  std::wstring::_Construct<1,wchar_t const *>(v83);
  memset(v84, 0, sizeof(v84));
  std::wstring::_Construct<1,wchar_t const *>(v84);
  memset(v85, 0, sizeof(v85));
  v24 = -1;
  do
    ++v24;
  while ( SystemInterface::Registry::CURRENTVERSIONAPPX_REDIRECTION_ID[v24] );
  std::wstring::_Construct<1,wchar_t const *>(v85);
  memset(v86, 0, sizeof(v86));
  std::wstring::_Construct<1,wchar_t const *>(v86);
  memset(v87, 0, sizeof(v87));
  v25 = -1;
  do
    ++v25;
  while ( SystemInterface::Registry::POLICYMANAGER_CURRENT_ROOT_ID[v25] );
  std::wstring::_Construct<1,wchar_t const *>(v87);
  memset(v88, 0, sizeof(v88));
  std::wstring::_Construct<1,wchar_t const *>(v88);
  memset(v89, 0, sizeof(v89));
  v26 = -1;
  do
    ++v26;
  while ( SystemInterface::Registry::POLICIES_MICROSOFT_WINDOWSSTORE_REDIRECTION_ID[v26] );
  std::wstring::_Construct<1,wchar_t const *>(v89);
  memset(v90, 0, sizeof(v90));
  std::wstring::_Construct<1,wchar_t const *>(v90);
  memset(v91, 0, sizeof(v91));
  v27 = -1;
  do
    ++v27;
  while ( SystemInterface::Registry::CURRENTVERSION_WINDOWSSTORE_REDIRECTION_ID[v27] );
  std::wstring::_Construct<1,wchar_t const *>(v91);
  memset(v92, 0, sizeof(v92));
  std::wstring::_Construct<1,wchar_t const *>(v92);
  memset(v93, 0, sizeof(v93));
  do
    ++v0;
  while ( SystemInterface::Registry::SOFTWARE_MICROSOFT_REDIRECTION_ID[v0] );
  std::wstring::_Construct<1,wchar_t const *>(v93);
  memset(v94, 0, sizeof(v94));
  std::wstring::_Construct<1,wchar_t const *>(v94);
  Windows::Registry::s_defaultRedirectionMap = 0;
  qword_18009FC38 = 0;
  v29 = operator new(0x60u);
  *v29 = v29;
  v29[1] = v29;
  v29[2] = v29;
  *((_WORD *)v29 + 12) = 257;
  Windows::Registry::s_defaultRedirectionMap = (__int64)v29;
  v30 = &v39[8];
  do
  {
    v31 = std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Find_hint<std::wstring>(
            v28,
            v95,
            v29,
            v30,
            v36);
    v32 = *(_OWORD *)v31;
    v38 = *(_QWORD *)(v31 + 16);
    if ( !(_BYTE)v38 )
    {
      if ( qword_18009FC38 == 0x2AAAAAAAAAAAAAALL )
        std::_Throw_tree_length_error();
      v33 = Windows::Registry::s_defaultRedirectionMap;
      v36 = &Windows::Registry::s_defaultRedirectionMap;
      v34 = (__int64 *)operator new(0x60u);
      std::wstring::wstring(v34 + 4, v30);
      std::wstring::wstring(v34 + 8, v30 + 32);
      *v34 = v33;
      v34[1] = v33;
      v34[2] = v33;
      *((_WORD *)v34 + 12) = 0;
      *(_OWORD *)&v37[1] = v32;
      std::_Tree_val<std::_Tree_simple_types<std::pair<winrt::hstring const,winrt::hstring>>>::_Insert_node(
        &Windows::Registry::s_defaultRedirectionMap,
        &v37[1],
        v34);
    }
    v30 += 64;
  }
  while ( v30 != v95 );
  `eh vector destructor iterator'(
    &v39[8],
    0x40u,
    0x1Cu,
    std::pair<std::wstring,std::wstring>::~pair<std::wstring,std::wstring>);
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__Windows::Registry::s_defaultRedirectionMap__);
}

```

## disassembly

```asm
0x180002e50  mov     rax, rsp
0x180002e53  mov     [rax+10h], rbx
0x180002e57  mov     [rax+18h], rsi
0x180002e5b  mov     [rax+20h], rdi
0x180002e5f  push    rbp
0x180002e60  push    r12
0x180002e62  push    r13
0x180002e64  push    r14
0x180002e66  push    r15
0x180002e68  lea     rbp, [rax-6A8h]
0x180002e6f  sub     rsp, 780h
0x180002e76  movaps  xmmword ptr [rax-38h], xmm6
0x180002e7a  mov     rdx, cs:?USOROOT_REDIRECTION_ID@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::USOROOT_REDIRECTION_ID
0x180002e81  xorps   xmm0, xmm0
0x180002e84  movups  [rsp+7A0h+var_758+8], xmm0
0x180002e89  xorps   xmm1, xmm1
0x180002e8c  movdqa  [rsp+7A0h+var_748+8], xmm1
0x180002e92  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180002e96  mov     r8, rbx
0x180002e99  xor     r15d, r15d
0x180002e9c  inc     r8
0x180002e9f  cmp     [rdx+r8*2], r15w
0x180002ea4  jnz     short loc_180002E9C
0x180002ea6  lea     rcx, [rsp+7A0h+var_758+8]
0x180002eab  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180002eb0  nop
0x180002eb1  xorps   xmm0, xmm0
0x180002eb4  movups  [rsp+7A0h+var_738+8], xmm0
0x180002eb9  xorps   xmm1, xmm1
0x180002ebc  movdqa  [rbp+6A0h+var_720], xmm1
0x180002ec1  mov     r8d, 2Dh ; '-'
0x180002ec7  lea     rdx, aSoftwareMicros_9; "Software\\Microsoft\\WindowsUpdate\\Orc"...
0x180002ece  lea     rcx, [rsp+7A0h+var_738+8]
0x180002ed3  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180002ed8  nop
0x180002ed9  mov     rdx, cs:?USOCURRENTVERSIONROOT_REDIRECTION_ID@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID
0x180002ee0  xorps   xmm0, xmm0
0x180002ee3  movups  [rbp+6A0h+var_710], xmm0
0x180002ee7  xorps   xmm1, xmm1
0x180002eea  movdqa  [rbp+6A0h+var_700], xmm1
0x180002eef  mov     r8, rbx
0x180002ef2  inc     r8
0x180002ef5  cmp     [rdx+r8*2], r15w
0x180002efa  jnz     short loc_180002EF2
0x180002efc  lea     rcx, [rbp+6A0h+var_710]
0x180002f00  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180002f05  nop
0x180002f06  xorps   xmm0, xmm0
0x180002f09  movups  [rbp+6A0h+var_6F0], xmm0
0x180002f0d  xorps   xmm1, xmm1
0x180002f10  movdqa  [rbp+6A0h+var_6E0], xmm1
0x180002f15  mov     r8d, 44h ; 'D'
0x180002f1b  lea     rdx, aSoftwareMicros_5; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180002f22  lea     rcx, [rbp+6A0h+var_6F0]
0x180002f26  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180002f2b  nop
0x180002f2c  mov     rdx, cs:?UPDATEUXROOT_REDIRECTION_ID@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::UPDATEUXROOT_REDIRECTION_ID
0x180002f33  xorps   xmm0, xmm0
0x180002f36  movups  [rbp+6A0h+var_6D0], xmm0
0x180002f3a  xorps   xmm1, xmm1
0x180002f3d  movdqa  [rbp+6A0h+var_6C0], xmm1
0x180002f42  mov     r8, rbx
0x180002f45  inc     r8
0x180002f48  cmp     [rdx+r8*2], r15w
0x180002f4d  jnz     short loc_180002F45
0x180002f4f  lea     rcx, [rbp+6A0h+var_6D0]
0x180002f53  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180002f58  nop
0x180002f59  xorps   xmm0, xmm0
0x180002f5c  movups  [rbp+6A0h+var_6B0], xmm0
0x180002f60  xorps   xmm1, xmm1
0x180002f63  movdqa  [rbp+6A0h+var_6A0], xmm1
0x180002f68  mov     r14d, 23h ; '#'
0x180002f6e  mov     r8d, r14d
0x180002f71  lea     rdx, aSoftwareMicros_18; "Software\\Microsoft\\WindowsUpdate\\UX"
0x180002f78  lea     rcx, [rbp+6A0h+var_6B0]
0x180002f7c  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180002f81  nop
0x180002f82  mov     rdx, cs:?CURRENTVERSION_REDIRECTION_ID@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::CURRENTVERSION_REDIRECTION_ID
0x180002f89  xorps   xmm0, xmm0
0x180002f8c  movups  [rbp+6A0h+var_690], xmm0
0x180002f90  xorps   xmm1, xmm1
0x180002f93  movdqa  [rbp+6A0h+var_680], xmm1
0x180002f98  mov     r8, rbx
0x180002f9b  inc     r8
0x180002f9e  cmp     [rdx+r8*2], r15w
0x180002fa3  jnz     short loc_180002F9B
0x180002fa5  lea     rcx, [rbp+6A0h+var_690]
0x180002fa9  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180002fae  nop
0x180002faf  xorps   xmm0, xmm0
0x180002fb2  movups  [rbp+6A0h+var_670], xmm0
0x180002fb6  xorps   xmm1, xmm1
0x180002fb9  movdqa  [rbp+6A0h+var_660], xmm1
0x180002fbe  mov     r8d, 29h ; ')'
0x180002fc4  lea     rdx, aSoftwareMicros_13; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180002fcb  lea     rcx, [rbp+6A0h+var_670]
0x180002fcf  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180002fd4  nop
0x180002fd5  mov     rdx, cs:?CURRENTVERSIONWU_REDIRECTION_ID@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::CURRENTVERSIONWU_REDIRECTION_ID
0x180002fdc  xorps   xmm0, xmm0
0x180002fdf  movups  [rbp+6A0h+var_650], xmm0
0x180002fe3  xorps   xmm1, xmm1
0x180002fe6  movdqa  [rbp+6A0h+var_640], xmm1
0x180002feb  mov     r8, rbx
0x180002fee  inc     r8
0x180002ff1  cmp     [rdx+r8*2], r15w
0x180002ff6  jnz     short loc_180002FEE
0x180002ff8  lea     rcx, [rbp+6A0h+var_650]
0x180002ffc  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180003001  nop
0x180003002  xorps   xmm0, xmm0
0x180003005  movups  [rbp+6A0h+var_630], xmm0
0x180003009  xorps   xmm1, xmm1
0x18000300c  movdqa  [rbp+6A0h+var_620], xmm1
0x180003014  mov     r8d, 37h ; '7'
0x18000301a  lea     rdx, aSoftwareMicros_12; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180003021  lea     rcx, [rbp+6A0h+var_630]
0x180003025  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18000302a  nop
0x18000302b  mov     rdx, cs:?UUP_DYN_INSTALLED_PROD_REDIRECTION_ID@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::UUP_DYN_INSTALLED_PROD_REDIRECTION_ID
0x180003032  xorps   xmm0, xmm0
0x180003035  movups  [rbp+6A0h+var_610], xmm0
0x18000303c  xorps   xmm1, xmm1
0x18000303f  movdqa  [rbp+6A0h+var_600], xmm1
0x180003047  mov     r8, rbx
0x18000304a  inc     r8
0x18000304d  cmp     [rdx+r8*2], r15w
0x180003052  jnz     short loc_18000304A
0x180003054  lea     rcx, [rbp+6A0h+var_610]
0x18000305b  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180003060  nop
0x180003061  xorps   xmm0, xmm0
0x180003064  movups  [rbp+6A0h+var_5F0], xmm0
0x18000306b  xorps   xmm1, xmm1
0x18000306e  movdqa  [rbp+6A0h+var_5E0], xmm1
0x180003076  mov     r8d, 52h ; 'R'
0x18000307c  lea     rdx, aSoftwareMicros_19; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180003083  lea     rcx, [rbp+6A0h+var_5F0]
0x18000308a  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18000308f  nop
0x180003090  mov     rdx, cs:?USOCONFIGURATIONROOT_REDIRECTION_ID@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::USOCONFIGURATIONROOT_REDIRECTION_ID
0x180003097  xorps   xmm0, xmm0
0x18000309a  movups  [rbp+6A0h+var_5D0], xmm0
0x1800030a1  xorps   xmm1, xmm1
0x1800030a4  movdqa  [rbp+6A0h+var_5C0], xmm1
0x1800030ac  mov     r8, rbx
0x1800030af  inc     r8
0x1800030b2  cmp     [rdx+r8*2], r15w
0x1800030b7  jnz     short loc_1800030AF
0x1800030b9  lea     rcx, [rbp+6A0h+var_5D0]
0x1800030c0  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800030c5  nop
0x1800030c6  xorps   xmm0, xmm0
0x1800030c9  movups  [rbp+6A0h+var_5B0], xmm0
0x1800030d0  xorps   xmm1, xmm1
0x1800030d3  movdqa  [rbp+6A0h+var_5A0], xmm1
0x1800030db  mov     r8d, 3Ch ; '<'
0x1800030e1  lea     rdx, aSoftwareMicros_15; "Software\\Microsoft\\WindowsUpdate\\Orc"...
0x1800030e8  lea     rcx, [rbp+6A0h+var_5B0]
0x1800030ef  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800030f4  nop
0x1800030f5  mov     rdx, cs:?CBSINTERFACE_REDIRECTION_ID@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::CBSINTERFACE_REDIRECTION_ID
0x1800030fc  xorps   xmm0, xmm0
0x1800030ff  movups  [rbp+6A0h+var_590], xmm0
0x180003106  xorps   xmm1, xmm1
0x180003109  movdqa  [rbp+6A0h+var_580], xmm1
0x180003111  mov     r8, rbx
0x180003114  inc     r8
0x180003117  cmp     [rdx+r8*2], r15w
0x18000311c  jnz     short loc_180003114
0x18000311e  lea     rcx, [rbp+6A0h+var_590]
0x180003125  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18000312a  nop
0x18000312b  xorps   xmm0, xmm0
0x18000312e  movups  [rbp+6A0h+var_570], xmm0
0x180003135  xorps   xmm1, xmm1
0x180003138  movdqa  [rbp+6A0h+var_560], xmm1
0x180003140  mov     r8d, 4Dh ; 'M'
0x180003146  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18000314d  lea     rcx, [rbp+6A0h+var_570]
0x180003154  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180003159  nop
0x18000315a  mov     rdx, cs:?DEVICEACCESS_REDIRECTION_ID@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::DEVICEACCESS_REDIRECTION_ID
0x180003161  xorps   xmm0, xmm0
0x180003164  movups  [rbp+6A0h+var_550], xmm0
0x18000316b  xorps   xmm1, xmm1
0x18000316e  movdqa  [rbp+6A0h+var_540], xmm1
0x180003176  mov     r8, rbx
0x180003179  inc     r8
0x18000317c  cmp     [rdx+r8*2], r15w
0x180003181  jnz     short loc_180003179
0x180003183  lea     rcx, [rbp+6A0h+var_550]
0x18000318a  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18000318f  nop
0x180003190  xorps   xmm0, xmm0
0x180003193  movups  [rbp+6A0h+var_530], xmm0
0x18000319a  xorps   xmm1, xmm1
0x18000319d  movdqa  [rbp+6A0h+var_520], xmm1
0x1800031a5  mov     r12d, 36h ; '6'
0x1800031ab  mov     r8d, r12d
0x1800031ae  lea     rdx, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800031b5  lea     rcx, [rbp+6A0h+var_530]
0x1800031bc  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800031c1  nop
0x1800031c2  mov     rdx, cs:?WU_REDIRECTION_ID@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::WU_REDIRECTION_ID
0x1800031c9  xorps   xmm0, xmm0
0x1800031cc  movups  [rbp+6A0h+var_510], xmm0
0x1800031d3  xorps   xmm1, xmm1
0x1800031d6  movdqa  [rbp+6A0h+var_500], xmm1
0x1800031de  mov     r8, rbx
0x1800031e1  inc     r8
0x1800031e4  cmp     [rdx+r8*2], r15w
0x1800031e9  jnz     short loc_1800031E1
0x1800031eb  lea     rcx, [rbp+6A0h+var_510]
0x1800031f2  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800031f7  nop
0x1800031f8  xorps   xmm0, xmm0
0x1800031fb  movups  [rbp+6A0h+var_4F0], xmm0
0x180003202  xorps   xmm1, xmm1
0x180003205  movdqa  [rbp+6A0h+var_4E0], xmm1
0x18000320d  mov     esi, 20h ; ' '
0x180003212  mov     r8d, esi
0x180003215  lea     rdx, aSoftwareMicros_14; "Software\\Microsoft\\WindowsUpdate"
0x18000321c  lea     rcx, [rbp+6A0h+var_4F0]
0x180003223  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180003228  nop
0x180003229  mov     rdx, cs:?UXCONFIGURATIONROOT_REDIRECTION_ID@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::UXCONFIGURATIONROOT_REDIRECTION_ID
0x180003230  xorps   xmm0, xmm0
0x180003233  movups  [rbp+6A0h+var_4D0], xmm0
0x18000323a  xorps   xmm1, xmm1
0x18000323d  movdqa  [rbp+6A0h+var_4C0], xmm1
0x180003245  mov     r8, rbx
0x180003248  inc     r8
0x18000324b  cmp     [rdx+r8*2], r15w
0x180003250  jnz     short loc_180003248
0x180003252  lea     rcx, [rbp+6A0h+var_4D0]
0x180003259  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18000325e  nop
0x18000325f  xorps   xmm0, xmm0
0x180003262  movups  [rbp+6A0h+var_4B0], xmm0
0x180003269  xorps   xmm1, xmm1
0x18000326c  movdqa  [rbp+6A0h+var_4A0], xmm1
0x180003274  mov     r8d, 4Ah ; 'J'
0x18000327a  lea     rdx, aSoftwareMicros_20; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180003281  lea     rcx, [rbp+6A0h+var_4B0]
0x180003288  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18000328d  nop
0x18000328e  mov     rdx, cs:?RESERVEMANAGER_REDIRECTION_ID@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::RESERVEMANAGER_REDIRECTION_ID
0x180003295  xorps   xmm0, xmm0
0x180003298  movups  [rbp+6A0h+var_490], xmm0
0x18000329f  xorps   xmm1, xmm1
0x1800032a2  movdqa  [rbp+6A0h+var_480], xmm1
0x1800032aa  mov     r8, rbx
0x1800032ad  inc     r8
0x1800032b0  cmp     [rdx+r8*2], r15w
0x1800032b5  jnz     short loc_1800032AD
0x1800032b7  lea     rcx, [rbp+6A0h+var_490]
0x1800032be  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800032c3  nop
0x1800032c4  xorps   xmm0, xmm0
0x1800032c7  movups  [rbp+6A0h+var_470], xmm0
0x1800032ce  xorps   xmm1, xmm1
0x1800032d1  movdqa  [rbp+6A0h+var_460], xmm1
0x1800032d9  mov     edi, 38h ; '8'
0x1800032de  mov     r8d, edi
0x1800032e1  lea     rdx, aSoftwareMicros_21; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800032e8  lea     rcx, [rbp+6A0h+var_470]
0x1800032ef  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800032f4  nop
0x1800032f5  mov     rdx, cs:?LOGONUI_REDIRECTION_ID@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::LOGONUI_REDIRECTION_ID
0x1800032fc  xorps   xmm0, xmm0
0x1800032ff  movups  [rbp+6A0h+var_450], xmm0
0x180003306  xorps   xmm1, xmm1
0x180003309  movdqa  [rbp+6A0h+var_440], xmm1
0x180003311  mov     r8, rbx
0x180003314  inc     r8
0x180003317  cmp     [rdx+r8*2], r15w
0x18000331c  jnz     short loc_180003314
0x18000331e  lea     rcx, [rbp+6A0h+var_450]
0x180003325  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18000332a  nop
0x18000332b  xorps   xmm0, xmm0
0x18000332e  movups  [rbp+6A0h+var_430], xmm0
0x180003335  xorps   xmm1, xmm1
0x180003338  movdqa  [rbp+6A0h+var_420], xmm1
0x180003340  mov     r8d, 40h ; '@'
0x180003346  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000334d  lea     rcx, [rbp+6A0h+var_430]
0x180003354  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180003359  nop
0x18000335a  mov     rdx, cs:?SYSTEMPROTECTEDUSERDATA_REDIRECTION_ID@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::SYSTEMPROTECTEDUSERDATA_REDIRECTION_ID
0x180003361  xorps   xmm0, xmm0
0x180003364  movups  [rbp+6A0h+var_410], xmm0
0x18000336b  xorps   xmm1, xmm1
0x18000336e  movdqa  [rbp+6A0h+var_400], xmm1
0x180003376  mov     r8, rbx
0x180003379  inc     r8
0x18000337c  cmp     [rdx+r8*2], r15w
0x180003381  jnz     short loc_180003379
  ... truncated ...
```
