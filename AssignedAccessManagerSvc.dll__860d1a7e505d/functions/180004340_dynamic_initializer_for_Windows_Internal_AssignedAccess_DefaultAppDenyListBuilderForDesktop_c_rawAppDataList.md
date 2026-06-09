# _dynamic_initializer_for__Windows::Internal::AssignedAccess::DefaultAppDenyListBuilderForDesktop::c_rawAppDataList__

- ea: `0x180004340`
- end: `0x18000495f`
- name: `_dynamic_initializer_for__Windows::Internal::AssignedAccess::DefaultAppDenyListBuilderForDesktop::c_rawAppDataList__`
- size: `1567`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180006640`
- `0x1800069f0`
- `0x1800088ec`
- `0x180014a5c`
- `0x18004a020`

## string_xrefs

- `0x18000436e`: `%systemroot%\system32\bcdboot.exe`
- `0x1800043a9`: `%systemroot%\system32\bcdedit.exe`
- `0x1800043fa`: `%systemroot%\system32\changepk.exe`
- `0x1800043d2`: `%systemroot%\system32\change.exe`
- `0x1800044b5`: `%systemroot%\system32\klist.exe`
- `0x180004523`: `%systemroot%\system32\mdsched.exe`
- `0x1800044ec`: `%systemroot%\system32\logoff.exe`
- `0x180004591`: `%systemroot%\system32\msconfig.exe`
- `0x18000455a`: `%CommonProgramFiles%\Microsoft Shared\Ink\mip.exe`
- `0x1800045c8`: `%systemroot%\system32\msinfo.exe`
- `0x18000466d`: `%systemroot%\system32\recdisc.exe`
- `0x180004636`: `%systemroot%\system32\recoverydrive.exe`
- `0x1800046db`: `%systemroot%\Speech\Common\sapisvr.exe`
- `0x180004749`: `%systemroot%\system32\wfs.exe`
- `0x180004712`: `%systemroot%\system32\snippingtool.exe`
- `0x180004780`: `%systemroot%\write.exe`
- `0x180004825`: `%ProgramFiles%\Windows NT\Accessories\wordpad.exe`
- `0x180004893`: `%ProgramFiles(Arm)%\Windows NT\Accessories\wordpad.exe`
- `0x18000485c`: `%ProgramFiles(x86)%\Windows NT\Accessories\wordpad.exe`
- `0x1800048ca`: `%systemroot%\system32\xpsrchvw.exe`

## pseudocode

```c
// Hidden C++ exception states: #wind=27
int dynamic_initializer_for__Windows::Internal::AssignedAccess::DefaultAppDenyListBuilderForDesktop::c_rawAppDataList__()
{
  _QWORD v1[2]; // [rsp+20h] [rbp-E0h] BYREF
  _QWORD v2[4]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v3[32]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v4; // [rsp+70h] [rbp-90h]
  const wchar_t *v5; // [rsp+78h] [rbp-88h]
  const wchar_t *v6; // [rsp+80h] [rbp-80h]
  const wchar_t *v7; // [rsp+88h] [rbp-78h]
  _BYTE v8[32]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v9; // [rsp+B0h] [rbp-50h]
  const wchar_t *v10; // [rsp+B8h] [rbp-48h]
  const wchar_t *v11; // [rsp+C0h] [rbp-40h]
  const wchar_t *v12; // [rsp+C8h] [rbp-38h]
  _BYTE v13[32]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v14; // [rsp+F0h] [rbp-10h]
  const wchar_t *v15; // [rsp+F8h] [rbp-8h]
  const wchar_t *v16; // [rsp+100h] [rbp+0h]
  const wchar_t *v17; // [rsp+108h] [rbp+8h]
  _BYTE v18[32]; // [rsp+110h] [rbp+10h] BYREF
  __int64 v19; // [rsp+130h] [rbp+30h]
  const wchar_t *v20; // [rsp+138h] [rbp+38h]
  const wchar_t *v21; // [rsp+140h] [rbp+40h]
  const wchar_t *v22; // [rsp+148h] [rbp+48h]
  _BYTE v23[32]; // [rsp+150h] [rbp+50h] BYREF
  __int64 v24; // [rsp+170h] [rbp+70h]
  const wchar_t *v25; // [rsp+178h] [rbp+78h]
  const wchar_t *v26; // [rsp+180h] [rbp+80h]
  const wchar_t *v27; // [rsp+188h] [rbp+88h]
  _BYTE v28[32]; // [rsp+190h] [rbp+90h] BYREF
  __int64 v29; // [rsp+1B0h] [rbp+B0h]
  const wchar_t *v30; // [rsp+1B8h] [rbp+B8h]
  const wchar_t *v31; // [rsp+1C0h] [rbp+C0h]
  const wchar_t *v32; // [rsp+1C8h] [rbp+C8h]
  _BYTE v33[32]; // [rsp+1D0h] [rbp+D0h] BYREF
  __int64 v34; // [rsp+1F0h] [rbp+F0h]
  const wchar_t *v35; // [rsp+1F8h] [rbp+F8h]
  const wchar_t *v36; // [rsp+200h] [rbp+100h]
  const wchar_t *v37; // [rsp+208h] [rbp+108h]
  _BYTE v38[32]; // [rsp+210h] [rbp+110h] BYREF
  __int64 v39; // [rsp+230h] [rbp+130h]
  const wchar_t *v40; // [rsp+238h] [rbp+138h]
  const wchar_t *v41; // [rsp+240h] [rbp+140h]
  const wchar_t *v42; // [rsp+248h] [rbp+148h]
  _BYTE v43[32]; // [rsp+250h] [rbp+150h] BYREF
  __int64 v44; // [rsp+270h] [rbp+170h]
  const wchar_t *v45; // [rsp+278h] [rbp+178h]
  const wchar_t *v46; // [rsp+280h] [rbp+180h]
  const wchar_t *v47; // [rsp+288h] [rbp+188h]
  _BYTE v48[32]; // [rsp+290h] [rbp+190h] BYREF
  __int64 v49; // [rsp+2B0h] [rbp+1B0h]
  const wchar_t *v50; // [rsp+2B8h] [rbp+1B8h]
  const wchar_t *v51; // [rsp+2C0h] [rbp+1C0h]
  const wchar_t *v52; // [rsp+2C8h] [rbp+1C8h]
  _BYTE v53[32]; // [rsp+2D0h] [rbp+1D0h] BYREF
  __int64 v54; // [rsp+2F0h] [rbp+1F0h]
  const wchar_t *v55; // [rsp+2F8h] [rbp+1F8h]
  const wchar_t *v56; // [rsp+300h] [rbp+200h]
  const wchar_t *v57; // [rsp+308h] [rbp+208h]
  _BYTE v58[32]; // [rsp+310h] [rbp+210h] BYREF
  __int64 v59; // [rsp+330h] [rbp+230h]
  const wchar_t *v60; // [rsp+338h] [rbp+238h]
  const wchar_t *v61; // [rsp+340h] [rbp+240h]
  const wchar_t *v62; // [rsp+348h] [rbp+248h]
  _BYTE v63[32]; // [rsp+350h] [rbp+250h] BYREF
  __int64 v64; // [rsp+370h] [rbp+270h]
  const wchar_t *v65; // [rsp+378h] [rbp+278h]
  const wchar_t *v66; // [rsp+380h] [rbp+280h]
  const wchar_t *v67; // [rsp+388h] [rbp+288h]
  _BYTE v68[32]; // [rsp+390h] [rbp+290h] BYREF
  __int64 v69; // [rsp+3B0h] [rbp+2B0h]
  const wchar_t *v70; // [rsp+3B8h] [rbp+2B8h]
  const wchar_t *v71; // [rsp+3C0h] [rbp+2C0h]
  const wchar_t *v72; // [rsp+3C8h] [rbp+2C8h]
  _BYTE v73[32]; // [rsp+3D0h] [rbp+2D0h] BYREF
  __int64 v74; // [rsp+3F0h] [rbp+2F0h]
  const wchar_t *v75; // [rsp+3F8h] [rbp+2F8h]
  const wchar_t *v76; // [rsp+400h] [rbp+300h]
  const wchar_t *v77; // [rsp+408h] [rbp+308h]
  _BYTE v78[32]; // [rsp+410h] [rbp+310h] BYREF
  __int64 v79; // [rsp+430h] [rbp+330h]
  const wchar_t *v80; // [rsp+438h] [rbp+338h]
  const wchar_t *v81; // [rsp+440h] [rbp+340h]
  const wchar_t *v82; // [rsp+448h] [rbp+348h]
  _BYTE v83[32]; // [rsp+450h] [rbp+350h] BYREF
  __int64 v84; // [rsp+470h] [rbp+370h]
  const wchar_t *v85; // [rsp+478h] [rbp+378h]
  const wchar_t *v86; // [rsp+480h] [rbp+380h]
  const wchar_t *v87; // [rsp+488h] [rbp+388h]
  _BYTE v88[32]; // [rsp+490h] [rbp+390h] BYREF
  __int64 v89; // [rsp+4B0h] [rbp+3B0h]
  const wchar_t *v90; // [rsp+4B8h] [rbp+3B8h]
  const wchar_t *v91; // [rsp+4C0h] [rbp+3C0h]
  const wchar_t *v92; // [rsp+4C8h] [rbp+3C8h]
  _BYTE v93[32]; // [rsp+4D0h] [rbp+3D0h] BYREF
  __int64 v94; // [rsp+4F0h] [rbp+3F0h]
  const wchar_t *v95; // [rsp+4F8h] [rbp+3F8h]
  const wchar_t *v96; // [rsp+500h] [rbp+400h]
  const wchar_t *v97; // [rsp+508h] [rbp+408h]
  _BYTE v98[32]; // [rsp+510h] [rbp+410h] BYREF
  __int64 v99; // [rsp+530h] [rbp+430h]
  const wchar_t *v100; // [rsp+538h] [rbp+438h]
  const wchar_t *v101; // [rsp+540h] [rbp+440h]
  const wchar_t *v102; // [rsp+548h] [rbp+448h]
  _BYTE v103[32]; // [rsp+550h] [rbp+450h] BYREF
  __int64 v104; // [rsp+570h] [rbp+470h]
  const wchar_t *v105; // [rsp+578h] [rbp+478h]
  const wchar_t *v106; // [rsp+580h] [rbp+480h]
  const wchar_t *v107; // [rsp+588h] [rbp+488h]
  _BYTE v108[32]; // [rsp+590h] [rbp+490h] BYREF
  __int64 v109; // [rsp+5B0h] [rbp+4B0h]
  const wchar_t *v110; // [rsp+5B8h] [rbp+4B8h]
  const wchar_t *v111; // [rsp+5C0h] [rbp+4C0h]
  const wchar_t *v112; // [rsp+5C8h] [rbp+4C8h]
  _BYTE v113[32]; // [rsp+5D0h] [rbp+4D0h] BYREF
  __int64 v114; // [rsp+5F0h] [rbp+4F0h]
  const wchar_t *v115; // [rsp+5F8h] [rbp+4F8h]
  const wchar_t *v116; // [rsp+600h] [rbp+500h]
  const wchar_t *v117; // [rsp+608h] [rbp+508h]
  _BYTE v118[32]; // [rsp+610h] [rbp+510h] BYREF
  __int64 v119; // [rsp+630h] [rbp+530h]
  const wchar_t *v120; // [rsp+638h] [rbp+538h]
  const wchar_t *v121; // [rsp+640h] [rbp+540h]
  const wchar_t *v122; // [rsp+648h] [rbp+548h]
  _BYTE v123[32]; // [rsp+650h] [rbp+550h] BYREF
  __int64 v124; // [rsp+670h] [rbp+570h]
  const wchar_t *v125; // [rsp+678h] [rbp+578h]
  const wchar_t *v126; // [rsp+680h] [rbp+580h]
  const wchar_t *v127; // [rsp+688h] [rbp+588h]
  _BYTE v128[32]; // [rsp+690h] [rbp+590h] BYREF
  __int64 v129; // [rsp+6B0h] [rbp+5B0h]
  const wchar_t *v130; // [rsp+6B8h] [rbp+5B8h]
  const wchar_t *v131; // [rsp+6C0h] [rbp+5C0h]
  const wchar_t *v132; // [rsp+6C8h] [rbp+5C8h]
  _BYTE v133[32]; // [rsp+6D0h] [rbp+5D0h] BYREF
  __int64 v134; // [rsp+6F0h] [rbp+5F0h] BYREF

  v2[0] = 3;
  v2[1] = L"%systemroot%\\system32\\bcdboot.exe";
  v2[2] = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v2[3] = L"*";
  std::wstring::wstring(v3, L"*");
  v4 = 3;
  v5 = L"%systemroot%\\system32\\bcdedit.exe";
  v6 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v7 = L"*";
  std::wstring::wstring(v8, L"*");
  v9 = 3;
  v10 = L"%systemroot%\\system32\\change.exe";
  v11 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v12 = L"*";
  std::wstring::wstring(v13, L"*");
  v14 = 3;
  v15 = L"%systemroot%\\system32\\changepk.exe";
  v16 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v17 = L"*";
  std::wstring::wstring(v18, L"*");
  v19 = 3;
  v20 = L"%ProgramFiles%\\internet explorer\\iexplore.exe";
  v21 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v22 = L"*";
  std::wstring::wstring(v23, L"*");
  v24 = 3;
  v25 = L"%ProgramFiles(x86)%\\internet explorer\\iexplore.exe";
  v26 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v27 = L"*";
  std::wstring::wstring(v28, L"*");
  v29 = 3;
  v30 = L"%systemroot%\\helppane.exe";
  v31 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v32 = L"*";
  std::wstring::wstring(v33, L"*");
  v34 = 3;
  v35 = L"%systemroot%\\system32\\klist.exe";
  v36 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v37 = L"*";
  std::wstring::wstring(v38, L"*");
  v39 = 3;
  v40 = L"%systemroot%\\system32\\logoff.exe";
  v41 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v42 = L"*";
  std::wstring::wstring(v43, L"*");
  v44 = 3;
  v45 = L"%systemroot%\\system32\\mdsched.exe";
  v46 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v47 = L"*";
  std::wstring::wstring(v48, L"*");
  v49 = 3;
  v50 = L"%CommonProgramFiles%\\Microsoft Shared\\Ink\\mip.exe";
  v51 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v52 = L"*";
  std::wstring::wstring(v53, L"*");
  v54 = 3;
  v55 = L"%systemroot%\\system32\\msconfig.exe";
  v56 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v57 = L"*";
  std::wstring::wstring(v58, L"*");
  v59 = 3;
  v60 = L"%systemroot%\\system32\\msinfo.exe";
  v61 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v62 = L"*";
  std::wstring::wstring(v63, L"*");
  v64 = 3;
  v65 = L"%systemroot%\\notepad.exe";
  v66 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v67 = L"*";
  std::wstring::wstring(v68, L"*");
  v69 = 3;
  v70 = L"%systemroot%\\system32\\recoverydrive.exe";
  v71 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v72 = L"*";
  std::wstring::wstring(v73, L"*");
  v74 = 3;
  v75 = L"%systemroot%\\system32\\recdisc.exe";
  v76 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v77 = L"*";
  std::wstring::wstring(v78, L"*");
  v79 = 3;
  v80 = L"%systemroot%\\regedit.exe";
  v81 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v82 = L"*";
  std::wstring::wstring(v83, L"*");
  v84 = 3;
  v85 = L"%systemroot%\\Speech\\Common\\sapisvr.exe";
  v86 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v87 = L"*";
  std::wstring::wstring(v88, L"*");
  v89 = 3;
  v90 = L"%systemroot%\\system32\\snippingtool.exe";
  v91 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v92 = L"*";
  std::wstring::wstring(v93, L"*");
  v94 = 3;
  v95 = L"%systemroot%\\system32\\wfs.exe";
  v96 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v97 = L"*";
  std::wstring::wstring(v98, L"*");
  v99 = 3;
  v100 = L"%systemroot%\\write.exe";
  v101 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v102 = L"*";
  std::wstring::wstring(v103, L"*");
  v104 = 3;
  v105 = L"%ProgramFiles%\\Windows Media Player\\wmplayer.exe";
  v106 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v107 = L"*";
  std::wstring::wstring(v108, L"*");
  v109 = 3;
  v110 = L"%ProgramFiles(x86)%\\Windows Media Player\\wmplayer.exe";
  v111 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v112 = L"*";
  std::wstring::wstring(v113, L"*");
  v114 = 3;
  v115 = L"%ProgramFiles%\\Windows NT\\Accessories\\wordpad.exe";
  v116 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v117 = L"*";
  std::wstring::wstring(v118, L"*");
  v119 = 3;
  v120 = L"%ProgramFiles(x86)%\\Windows NT\\Accessories\\wordpad.exe";
  v121 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v122 = L"*";
  std::wstring::wstring(v123, L"*");
  v124 = 3;
  v125 = L"%ProgramFiles(Arm)%\\Windows NT\\Accessories\\wordpad.exe";
  v126 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v127 = L"*";
  std::wstring::wstring(v128, L"*");
  v129 = 3;
  v130 = L"%systemroot%\\system32\\xpsrchvw.exe";
  v131 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v132 = L"*";
  std::wstring::wstring(v133, L"*");
  v1[0] = v2;
  v1[1] = &v134;
  std::vector<Windows::Internal::AssignedAccess::RawAppData>::vector<Windows::Internal::AssignedAccess::RawAppData>(
    &Windows::Internal::AssignedAccess::DefaultAppDenyListBuilderForDesktop::c_rawAppDataList,
    v1);
  `eh vector destructor iterator'(
    v2,
    0x40u,
    0x1Bu,
    (void (*)(void *))Windows::Internal::AssignedAccess::RawAppData::~RawAppData);
  return atexit(dynamic_atexit_destructor_for__Windows::Internal::AssignedAccess::DefaultAppDenyListBuilderForDesktop::c_rawAppDataList__);
}

```

## disassembly

```asm
0x180004340  push    rbp
0x180004342  push    rbx
0x180004343  push    rsi
0x180004344  push    rdi
0x180004345  lea     rbp, [rsp-608h]
0x18000434d  sub     rsp, 708h
0x180004354  mov     rax, cs:__security_cookie
0x18000435b  xor     rax, rsp
0x18000435e  mov     [rbp+620h+var_30], rax
0x180004365  mov     [rsp+720h+var_6F0], 3
0x18000436e  lea     rax, aSystemrootSyst_14; "%systemroot%\\system32\\bcdboot.exe"
0x180004375  mov     [rsp+720h+var_6E8], rax
0x18000437a  lea     rbx, aOMicrosoftCorp; "O=MICROSOFT CORPORATION, L=REDMOND, S=W"...
0x180004381  mov     [rsp+720h+var_6E0], rbx
0x180004386  lea     rdi, asc_1800A7204; "*"
0x18000438d  mov     [rsp+720h+var_6D8], rdi
0x180004392  mov     rdx, rdi
0x180004395  lea     rcx, [rsp+720h+var_6D0]
0x18000439a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000439f  nop
0x1800043a0  mov     [rsp+720h+var_6B0], 3
0x1800043a9  lea     rax, aSystemrootSyst_5; "%systemroot%\\system32\\bcdedit.exe"
0x1800043b0  mov     [rsp+720h+var_6A8], rax
0x1800043b5  mov     [rbp+620h+var_6A0], rbx
0x1800043b9  mov     [rbp+620h+var_698], rdi
0x1800043bd  mov     rdx, rdi
0x1800043c0  lea     rcx, [rbp+620h+var_690]
0x1800043c4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800043c9  nop
0x1800043ca  mov     [rbp+620h+var_670], 3
0x1800043d2  lea     rax, aSystemrootSyst_11; "%systemroot%\\system32\\change.exe"
0x1800043d9  mov     [rbp+620h+var_668], rax
0x1800043dd  mov     [rbp+620h+var_660], rbx
0x1800043e1  mov     [rbp+620h+var_658], rdi
0x1800043e5  mov     rdx, rdi
0x1800043e8  lea     rcx, [rbp+620h+var_650]
0x1800043ec  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800043f1  nop
0x1800043f2  mov     [rbp+620h+var_630], 3
0x1800043fa  lea     rax, aSystemrootSyst_8; "%systemroot%\\system32\\changepk.exe"
0x180004401  mov     [rbp+620h+var_628], rax
0x180004405  mov     [rbp+620h+var_620], rbx
0x180004409  mov     [rbp+620h+var_618], rdi
0x18000440d  mov     rdx, rdi
0x180004410  lea     rcx, [rbp+620h+var_610]
0x180004414  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180004419  nop
0x18000441a  mov     [rbp+620h+var_5F0], 3
0x180004422  lea     rax, aProgramfilesIn; "%ProgramFiles%\\internet explorer\\iexp"...
0x180004429  mov     [rbp+620h+var_5E8], rax
0x18000442d  mov     [rbp+620h+var_5E0], rbx
0x180004431  mov     [rbp+620h+var_5D8], rdi
0x180004435  mov     rdx, rdi
0x180004438  lea     rcx, [rbp+620h+var_5D0]
0x18000443c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180004441  nop
0x180004442  mov     [rbp+620h+var_5B0], 3
0x18000444a  lea     rax, aProgramfilesX8_1; "%ProgramFiles(x86)%\\internet explorer"...
0x180004451  mov     [rbp+620h+var_5A8], rax
0x180004455  mov     [rbp+620h+var_5A0], rbx
0x18000445c  mov     [rbp+620h+var_598], rdi
0x180004463  mov     rdx, rdi
0x180004466  lea     rcx, [rbp+620h+var_590]
0x18000446d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180004472  nop
0x180004473  mov     [rbp+620h+var_570], 3
0x18000447e  lea     rax, aSystemrootHelp; "%systemroot%\\helppane.exe"
0x180004485  mov     [rbp+620h+var_568], rax
0x18000448c  mov     [rbp+620h+var_560], rbx
0x180004493  mov     [rbp+620h+var_558], rdi
0x18000449a  mov     rdx, rdi
0x18000449d  lea     rcx, [rbp+620h+var_550]
0x1800044a4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800044a9  nop
0x1800044aa  mov     [rbp+620h+var_530], 3
0x1800044b5  lea     rax, aSystemrootSyst_6; "%systemroot%\\system32\\klist.exe"
0x1800044bc  mov     [rbp+620h+var_528], rax
0x1800044c3  mov     [rbp+620h+var_520], rbx
0x1800044ca  mov     [rbp+620h+var_518], rdi
0x1800044d1  mov     rdx, rdi
0x1800044d4  lea     rcx, [rbp+620h+var_510]
0x1800044db  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800044e0  nop
0x1800044e1  mov     [rbp+620h+var_4F0], 3
0x1800044ec  lea     rax, aSystemrootSyst_9; "%systemroot%\\system32\\logoff.exe"
0x1800044f3  mov     [rbp+620h+var_4E8], rax
0x1800044fa  mov     [rbp+620h+var_4E0], rbx
0x180004501  mov     [rbp+620h+var_4D8], rdi
0x180004508  mov     rdx, rdi
0x18000450b  lea     rcx, [rbp+620h+var_4D0]
0x180004512  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180004517  nop
0x180004518  mov     [rbp+620h+var_4B0], 3
0x180004523  lea     rax, aSystemrootSyst_3; "%systemroot%\\system32\\mdsched.exe"
0x18000452a  mov     [rbp+620h+var_4A8], rax
0x180004531  mov     [rbp+620h+var_4A0], rbx
0x180004538  mov     [rbp+620h+var_498], rdi
0x18000453f  mov     rdx, rdi
0x180004542  lea     rcx, [rbp+620h+var_490]
0x180004549  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000454e  nop
0x18000454f  mov     [rbp+620h+var_470], 3
0x18000455a  lea     rax, aCommonprogramf; "%CommonProgramFiles%\\Microsoft Shared"...
0x180004561  mov     [rbp+620h+var_468], rax
0x180004568  mov     [rbp+620h+var_460], rbx
0x18000456f  mov     [rbp+620h+var_458], rdi
0x180004576  mov     rdx, rdi
0x180004579  lea     rcx, [rbp+620h+var_450]
0x180004580  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180004585  nop
0x180004586  mov     [rbp+620h+var_430], 3
0x180004591  lea     rax, aSystemrootSyst_4; "%systemroot%\\system32\\msconfig.exe"
0x180004598  mov     [rbp+620h+var_428], rax
0x18000459f  mov     [rbp+620h+var_420], rbx
0x1800045a6  mov     [rbp+620h+var_418], rdi
0x1800045ad  mov     rdx, rdi
0x1800045b0  lea     rcx, [rbp+620h+var_410]
0x1800045b7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800045bc  nop
0x1800045bd  mov     [rbp+620h+var_3F0], 3
0x1800045c8  lea     rax, aSystemrootSyst; "%systemroot%\\system32\\msinfo.exe"
0x1800045cf  mov     [rbp+620h+var_3E8], rax
0x1800045d6  mov     [rbp+620h+var_3E0], rbx
0x1800045dd  mov     [rbp+620h+var_3D8], rdi
0x1800045e4  mov     rdx, rdi
0x1800045e7  lea     rcx, [rbp+620h+var_3D0]
0x1800045ee  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800045f3  nop
0x1800045f4  mov     [rbp+620h+var_3B0], 3
0x1800045ff  lea     rax, aSystemrootNote; "%systemroot%\\notepad.exe"
0x180004606  mov     [rbp+620h+var_3A8], rax
0x18000460d  mov     [rbp+620h+var_3A0], rbx
0x180004614  mov     [rbp+620h+var_398], rdi
0x18000461b  mov     rdx, rdi
0x18000461e  lea     rcx, [rbp+620h+var_390]
0x180004625  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000462a  nop
0x18000462b  mov     [rbp+620h+var_370], 3
0x180004636  lea     rax, aSystemrootSyst_12; "%systemroot%\\system32\\recoverydrive.e"...
0x18000463d  mov     [rbp+620h+var_368], rax
0x180004644  mov     [rbp+620h+var_360], rbx
0x18000464b  mov     [rbp+620h+var_358], rdi
0x180004652  mov     rdx, rdi
0x180004655  lea     rcx, [rbp+620h+var_350]
0x18000465c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180004661  nop
0x180004662  mov     [rbp+620h+var_330], 3
0x18000466d  lea     rax, aSystemrootSyst_13; "%systemroot%\\system32\\recdisc.exe"
0x180004674  mov     [rbp+620h+var_328], rax
0x18000467b  mov     [rbp+620h+var_320], rbx
0x180004682  mov     [rbp+620h+var_318], rdi
0x180004689  mov     rdx, rdi
0x18000468c  lea     rcx, [rbp+620h+var_310]
0x180004693  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180004698  nop
0x180004699  mov     [rbp+620h+var_2F0], 3
0x1800046a4  lea     rax, aSystemrootRege; "%systemroot%\\regedit.exe"
0x1800046ab  mov     [rbp+620h+var_2E8], rax
0x1800046b2  mov     [rbp+620h+var_2E0], rbx
0x1800046b9  mov     [rbp+620h+var_2D8], rdi
0x1800046c0  mov     rdx, rdi
0x1800046c3  lea     rcx, [rbp+620h+var_2D0]
0x1800046ca  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800046cf  nop
0x1800046d0  mov     [rbp+620h+var_2B0], 3
0x1800046db  lea     rax, aSystemrootSpee; "%systemroot%\\Speech\\Common\\sapisvr.e"...
0x1800046e2  mov     [rbp+620h+var_2A8], rax
0x1800046e9  mov     [rbp+620h+var_2A0], rbx
0x1800046f0  mov     [rbp+620h+var_298], rdi
0x1800046f7  mov     rdx, rdi
0x1800046fa  lea     rcx, [rbp+620h+var_290]
0x180004701  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180004706  nop
0x180004707  mov     [rbp+620h+var_270], 3
0x180004712  lea     rax, aSystemrootSyst_0; "%systemroot%\\system32\\snippingtool.ex"...
0x180004719  mov     [rbp+620h+var_268], rax
0x180004720  mov     [rbp+620h+var_260], rbx
0x180004727  mov     [rbp+620h+var_258], rdi
0x18000472e  mov     rdx, rdi
0x180004731  lea     rcx, [rbp+620h+var_250]
0x180004738  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000473d  nop
0x18000473e  mov     [rbp+620h+var_230], 3
0x180004749  lea     rax, aSystemrootSyst_10; "%systemroot%\\system32\\wfs.exe"
0x180004750  mov     [rbp+620h+var_228], rax
0x180004757  mov     [rbp+620h+var_220], rbx
0x18000475e  mov     [rbp+620h+var_218], rdi
0x180004765  mov     rdx, rdi
0x180004768  lea     rcx, [rbp+620h+var_210]
0x18000476f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180004774  nop
0x180004775  mov     [rbp+620h+var_1F0], 3
0x180004780  lea     rax, aSystemrootWrit_0; "%systemroot%\\write.exe"
0x180004787  mov     [rbp+620h+var_1E8], rax
0x18000478e  mov     [rbp+620h+var_1E0], rbx
0x180004795  mov     [rbp+620h+var_1D8], rdi
0x18000479c  mov     rdx, rdi
0x18000479f  lea     rcx, [rbp+620h+var_1D0]
0x1800047a6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800047ab  nop
0x1800047ac  mov     [rbp+620h+var_1B0], 3
0x1800047b7  lea     rax, aProgramfilesWi_0; "%ProgramFiles%\\Windows Media Player\\w"...
0x1800047be  mov     [rbp+620h+var_1A8], rax
0x1800047c5  mov     [rbp+620h+var_1A0], rbx
0x1800047cc  mov     [rbp+620h+var_198], rdi
0x1800047d3  mov     rdx, rdi
0x1800047d6  lea     rcx, [rbp+620h+var_190]
0x1800047dd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800047e2  nop
0x1800047e3  mov     [rbp+620h+var_170], 3
0x1800047ee  lea     rax, aProgramfilesX8_0; "%ProgramFiles(x86)%\\Windows Media Play"...
0x1800047f5  mov     [rbp+620h+var_168], rax
0x1800047fc  mov     [rbp+620h+var_160], rbx
0x180004803  mov     [rbp+620h+var_158], rdi
0x18000480a  mov     rdx, rdi
0x18000480d  lea     rcx, [rbp+620h+var_150]
0x180004814  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180004819  nop
0x18000481a  mov     [rbp+620h+var_130], 3
0x180004825  lea     rax, aProgramfilesWi; "%ProgramFiles%\\Windows NT\\Accessories"...
0x18000482c  mov     [rbp+620h+var_128], rax
0x180004833  mov     [rbp+620h+var_120], rbx
0x18000483a  mov     [rbp+620h+var_118], rdi
0x180004841  mov     rdx, rdi
0x180004844  lea     rcx, [rbp+620h+var_110]
0x18000484b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180004850  nop
0x180004851  mov     [rbp+620h+var_F0], 3
0x18000485c  lea     rax, aProgramfilesX8_2; "%ProgramFiles(x86)%\\Windows NT\\Access"...
0x180004863  mov     [rbp+620h+var_E8], rax
0x18000486a  mov     [rbp+620h+var_E0], rbx
0x180004871  mov     [rbp+620h+var_D8], rdi
0x180004878  mov     rdx, rdi
0x18000487b  lea     rcx, [rbp+620h+var_D0]
0x180004882  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180004887  nop
0x180004888  mov     [rbp+620h+var_B0], 3
0x180004893  lea     rax, aProgramfilesAr; "%ProgramFiles(Arm)%\\Windows NT\\Access"...
0x18000489a  mov     [rbp+620h+var_A8], rax
0x1800048a1  mov     [rbp+620h+var_A0], rbx
0x1800048a8  mov     [rbp+620h+var_98], rdi
0x1800048af  mov     rdx, rdi
0x1800048b2  lea     rcx, [rbp+620h+var_90]
0x1800048b9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800048be  nop
0x1800048bf  mov     [rbp+620h+var_70], 3
0x1800048ca  lea     rax, aSystemrootSyst_7; "%systemroot%\\system32\\xpsrchvw.exe"
0x1800048d1  mov     [rbp+620h+var_68], rax
0x1800048d8  mov     [rbp+620h+var_60], rbx
0x1800048df  mov     [rbp+620h+var_58], rdi
0x1800048e6  mov     rdx, rdi
0x1800048e9  lea     rcx, [rbp+620h+var_50]
0x1800048f0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800048f5  nop
0x1800048f6  lea     rax, [rsp+720h+var_6F0]
0x1800048fb  mov     [rsp+720h+var_700], rax
0x180004900  lea     rax, [rbp+620h+var_30]
0x180004907  mov     [rsp+720h+var_6F8], rax
0x18000490c  lea     rdx, [rsp+720h+var_700]
0x180004911  lea     rcx, ?c_rawAppDataList@DefaultAppDenyListBuilderForDesktop@AssignedAccess@Internal@Windows@@0V?$vector@URawAppData@AssignedAccess@Internal@Windows@@V?$allocator@URawAppData@AssignedAccess@Internal@Windows@@@std@@@std@@A; std::vector<Windows::Internal::AssignedAccess::RawAppData> Windows::Internal::AssignedAccess::DefaultAppDenyListBuilderForDesktop::c_rawAppDataList
0x180004918  call    ??0?$vector@URawAppData@AssignedAccess@Internal@Windows@@V?$allocator@URawAppData@AssignedAccess@Internal@Windows@@@std@@@std@@QEAA@V?$initializer_list@URawAppData@AssignedAccess@Internal@Windows@@@1@AEBV?$allocator@URawAppData@AssignedAccess@Internal@Windows@@@1@@Z; std::vector<Windows::Internal::AssignedAccess::RawAppData>::vector<Windows::Internal::AssignedAccess::RawAppData>(std::initializer_list<Windows::Internal::AssignedAccess::RawAppData>,std::allocator<Windows::Internal::AssignedAccess::RawAppData> const &)
0x18000491d  nop
0x18000491e  lea     r9, ??1RawAppData@AssignedAccess@Internal@Windows@@QEAA@XZ; void (*)(void *)
0x180004925  mov     edx, 40h ; '@'; unsigned __int64
0x18000492a  lea     r8d, [rdx-25h]; unsigned __int64
0x18000492e  lea     rcx, [rsp+720h+var_6F0]; void *
0x180004933  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180004938  lea     rcx, _dynamic_atexit_destructor_for__Windows__Internal__AssignedAccess__DefaultAppDenyListBuilderForDesktop__c_rawAppDataList__; void (__cdecl *)()
0x18000493f  call    atexit
0x180004944  mov     rcx, [rbp+620h+var_30]
0x18000494b  xor     rcx, rsp; StackCookie
0x18000494e  call    __security_check_cookie
0x180004953  add     rsp, 708h
0x18000495a  pop     rdi
0x18000495b  pop     rsi
0x18000495c  pop     rbx
0x18000495d  pop     rbp
0x18000495e  retn
```
