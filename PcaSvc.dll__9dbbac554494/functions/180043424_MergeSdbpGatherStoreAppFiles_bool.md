# MergeSdbpGatherStoreAppFiles(bool)

- ea: `0x180043424`
- end: `0x180045135`
- name: `?MergeSdbpGatherStoreAppFiles@@YAK_N@Z`
- size: `7441`
- prototype: `__int64 __fastcall(char)`
- caller_count: `1`
- callee_count: `39`
- tags: `file_ops, reparse_path, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180042fa0`

## callees

- `0x1800055b8`
- `0x180007020`
- `0x18000a750`
- `0x18000b6f0`
- `0x18000c560`
- `0x18000dc08`
- `0x180012920`
- `0x1800139b4`
- `0x180020cd0`
- `0x1800211f8`
- `0x1800212b0`
- `0x1800310a8`
- `0x1800312d0`
- `0x18003530c`
- `0x18003c26c`
- `0x18003ccf8`
- `0x18003d910`
- `0x18003d988`
- `0x18003de84`
- `0x18003e1ac`
- `0x180043424`
- `0x18004513c`
- `0x18004cfa4`
- `0x18004d0f0`
- `0x18004d110`
- `0x1800538d0`
- `0x18007aa17`
- `0x180080038`
- `0x180096d58`
- `0x18009729c`
- `0x1800976c4`
- `0x180097a30`
- `0x180097e24`
- `0x1800e3f84`
- `0x1800e40b0`
- `0x1800e4254`
- `0x1800ee04c`
- `0x1800f1f10`
- `0x1800f1fd0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180043828`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180043828`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180044433`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004447a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180044d7f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180044dc6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180044e67`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180044433`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004447a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180044d7f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180044dc6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180044e67`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800444ab`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800444db`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180044df3`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180044e20`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800444ab`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800444db`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180044df3`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180044e20`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800441c9`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800442fd`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800445d9`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180044a31`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800441c9`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800442fd`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800445d9`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180044a31`
- `api-ms-win-core-processthreads-l1-1-7!GetMachineTypeAttributes` at `0x180043790`
- `api-ms-win-core-processthreads-l1-1-7!GetMachineTypeAttributes` at `0x180043790`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x1800439b0`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x180043a09`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x180043a99`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x1800439b0`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x180043a09`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x180043a99`

## string_xrefs

- `0x1800441df`: `Failed to create and expand sdbinst.exe path (%d)`
- `0x180044313`: `Failed to create and expand sdbinst.exe path (%d)`
- `0x1800445ef`: `Failed to create and expand sdbinst.exe path (%d)`
- `0x180044a47`: `Failed to create and expand sdbinst.exe path (%d)`
- `0x180044443`: `RegSetValueExW failed (%d)`
- `0x18004448e`: `RegSetValueExW failed (%d)`
- `0x180044d8f`: `RegSetValueExW failed (%d)`
- `0x180044dd6`: `RegSetValueExW failed (%d)`
- `0x180044e77`: `RegSetValueExW failed (%d)`
- `0x180043838`: `RegOpenKeyExW failed (%d)`
- `0x180043873`: `MergeSdbpGetStoreAppInstallDirectory failed (%d)`
- `0x180043ac9`: `Failed to extract sys update sdb data (%d)`
- `0x180043b20`: `MergeSdbpGetStoreAppDllsForArch failed (%d)`
- `0x180043939`: `MergeSdbpGetSdbGuidAndTimestampFromRegistry failed (%d)`
- `0x180043bac`: `MergeSdbpGetSdbGuidAndTimestampFromRegistry failed (%d)`
- `0x180043965`: `ApplicationCompatibilityEnhancements.cat`
- `0x1800439be`: `msiMergeInboxStoreApp.sdb`
- `0x180043a38`: `Failed to extract msi update sdb data (%d)`
- `0x180044170`: `%ls\system32\sdbinst.exe%ls -u -g %ls`
- `0x180044593`: `%ls\system32\sdbinst.exe%ls -u -g %ls`
- `0x18004420e`: `Failed to remove installed merge db (%d)`
- `0x18004461f`: `Failed to remove installed merge db (%d)`
- `0x180043ea3`: `SdbGetPluginDll failed (%d)`
- `0x1800440b6`: `MergeSdbpCompareDlls failed (%d)`
- `0x1800449e9`: `MergeSdbpCompareDlls failed (%d)`
- `0x180044343`: `Failed to install merge db (%d)`
- `0x180044a77`: `Failed to install merge db (%d)`
- `0x18004438d`: `SdbInst.exe ran successfully for msi update/add: %d`
- `0x1800444be`: `RegDeleteValueW failed (%d)`
- `0x1800444ef`: `RegDeleteValueW failed (%d)`
- `0x180044e03`: `RegDeleteValueW failed (%d)`
- `0x180044e30`: `RegDeleteValueW failed (%d)`
- `0x180044254`: `SdbInst.exe ran successfully for msi removal: %d`
- `0x1800442b7`: `%ls\system32\sdbinst.exe%ls%ls "%ls"`
- `0x18004493f`: `%ls\system32\sdbinst.exe%ls%ls "%ls"`
- `0x180044ced`: `SdbInst.exe ran successfully for sys update/add: %d`
- `0x180044bc7`: `SdbRemovePluginDll failed, swallowing (%d)`
- `0x18004497c`: `MergeSdbpSetInstalledShimDlls failed (%d)`
- `0x180044d2a`: `MergeSdbpSetInstalledShimDlls failed (%d)`
- `0x1800448c4`: `SdbAddPluginDll failed, swallowing (%d)`
- `0x1800438ee`: `SAIDMSI`
- `0x180044428`: `SAIDMSI`
- `0x1800444a0`: `SAIDMSI`
- `0x18004381a`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags`
- `0x1800438e2`: `SATMSI`
- `0x18004446f`: `SATMSI`
- `0x1800444d0`: `SATMSI`

## pseudocode

```c
__int64 __fastcall MergeSdbpGatherStoreAppFiles(char a1)
{
  char v1; // r15
  struct _GUID v2; // xmm7
  struct _GUID v3; // xmm6
  unsigned __int64 i; // rbx
  int MachineTypeAttributes; // eax
  int v6; // eax
  LSTATUS v7; // eax
  unsigned int v8; // ebx
  unsigned int StoreAppInstallDirectory; // eax
  unsigned __int64 RegistryQWORD; // rax
  char v11; // r13
  char v12; // r12
  unsigned int SdbGuidAndTimestampFromRegistry; // eax
  int v14; // eax
  int v15; // r8d
  int v16; // eax
  unsigned int v17; // eax
  int v18; // eax
  unsigned int v19; // eax
  unsigned __int64 j; // rbx
  unsigned int StoreAppDllsForArch; // eax
  unsigned int v22; // esi
  unsigned int v23; // eax
  unsigned __int8 **v24; // r8
  unsigned int *v25; // r9
  const char *v26; // r9
  int v27; // r8d
  unsigned __int64 k; // rsi
  const unsigned __int16 *v29; // rdx
  unsigned int RegistryMULTISTRING; // eax
  ULONGLONG *v31; // r14
  int v32; // eax
  ULONGLONG v33; // rbx
  _QWORD *v34; // rax
  _QWORD *v35; // r9
  int PluginDll; // eax
  int v37; // eax
  __int64 v38; // rbx
  ULONGLONG *v39; // r14
  ULONGLONG v40; // rax
  ULONGLONG v41; // rdi
  const unsigned __int16 **v42; // r8
  const unsigned __int16 **v43; // r11
  unsigned int v44; // eax
  int v45; // r8d
  const char *v46; // r9
  int v47; // r8d
  const char *v48; // r9
  int v49; // r8d
  char v50; // si
  __int64 v51; // r14
  ULONGLONG *v52; // r12
  ULONGLONG v53; // rdi
  const unsigned __int16 **v54; // rdx
  const unsigned __int16 **v55; // r11
  ULONGLONG v56; // r10
  RtlStringArray *v57; // r9
  const unsigned __int16 **v58; // rdx
  __int64 v59; // r9
  const unsigned __int16 **v60; // r11
  const unsigned __int16 *v61; // r11
  __int64 v62; // r9
  const unsigned __int16 **v63; // rax
  __int64 v64; // r9
  unsigned int RegistryDWORD; // r14d
  const wchar_t *v66; // rcx
  int v67; // eax
  DWORD v68; // eax
  unsigned int v69; // eax
  const wchar_t *v70; // rcx
  const wchar_t *v71; // rax
  int v72; // eax
  DWORD v73; // eax
  unsigned int v74; // eax
  int v75; // eax
  __int64 v76; // rax
  LSTATUS v77; // eax
  LSTATUS v78; // eax
  LSTATUS v79; // eax
  LSTATUS v80; // eax
  const wchar_t *v81; // rcx
  int v82; // eax
  DWORD v83; // eax
  unsigned int v84; // eax
  __int64 v85; // rbx
  void *v86; // rdx
  int v87; // eax
  int v88; // eax
  unsigned int v89; // eax
  unsigned __int64 m; // r15
  ULONGLONG *v91; // r12
  ULONGLONG v92; // rbx
  const unsigned __int16 **v93; // rdx
  ULONGLONG v94; // r10
  RtlStringArray *v95; // r9
  const unsigned __int16 **v96; // rdx
  __int64 v97; // r9
  const unsigned __int16 *v98; // r11
  __int64 v99; // r9
  const unsigned __int16 **v100; // rax
  __int64 v101; // r9
  unsigned int v102; // eax
  unsigned int v103; // r14d
  RtlStringArray *v104; // r9
  LPCWSTR *v105; // rax
  __int64 v106; // r9
  int v107; // eax
  const wchar_t *v108; // rcx
  const wchar_t *v109; // rax
  int v110; // eax
  int v111; // r8d
  DWORD v112; // eax
  unsigned int v113; // eax
  char v114; // r14
  __int64 v115; // r15
  int v116; // eax
  ULONGLONG *v117; // r12
  ULONGLONG v118; // rsi
  const unsigned __int16 **v119; // rdx
  __int64 *v120; // rax
  int v121; // eax
  const unsigned __int16 **v122; // rdx
  int v123; // eax
  unsigned __int64 n; // rbx
  int v125; // eax
  __int64 v126; // rax
  LSTATUS v127; // eax
  LSTATUS v128; // eax
  LSTATUS v129; // eax
  LSTATUS v130; // eax
  LSTATUS v131; // eax
  const char *v133; // r9
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  PHKEY phkResulta; // [rsp+20h] [rbp-E0h]
  PHKEY phkResultb; // [rsp+20h] [rbp-E0h]
  WCHAR *phkResultc; // [rsp+20h] [rbp-E0h]
  PHKEY phkResultd; // [rsp+20h] [rbp-E0h]
  PHKEY phkResulte; // [rsp+20h] [rbp-E0h]
  PHKEY phkResultf; // [rsp+20h] [rbp-E0h]
  PHKEY phkResultg; // [rsp+20h] [rbp-E0h]
  DWORD cbData[2]; // [rsp+28h] [rbp-D8h]
  unsigned int v143; // [rsp+50h] [rbp-B0h] BYREF
  char v144; // [rsp+54h] [rbp-ACh]
  bool v145; // [rsp+55h] [rbp-ABh] BYREF
  unsigned __int16 *v146; // [rsp+58h] [rbp-A8h] BYREF
  char v147; // [rsp+60h] [rbp-A0h]
  char v148; // [rsp+61h] [rbp-9Fh]
  char v149; // [rsp+62h] [rbp-9Eh]
  _BYTE v150[13]; // [rsp+63h] [rbp-9Dh] BYREF
  bool v151; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v152[2]; // [rsp+80h] [rbp-80h] BYREF
  HKEY hKey[2]; // [rsp+90h] [rbp-70h] BYREF
  ULONGLONG v154[2]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int v155[2]; // [rsp+B0h] [rbp-50h] BYREF
  ULONGLONG pullResult; // [rsp+B8h] [rbp-48h] BYREF
  int v157; // [rsp+C0h] [rbp-40h] BYREF
  BYTE v158[8]; // [rsp+C8h] [rbp-38h] BYREF
  BYTE v159[8]; // [rsp+D0h] [rbp-30h] BYREF
  BYTE v160[8]; // [rsp+D8h] [rbp-28h] BYREF
  struct _GUID Buf2; // [rsp+E0h] [rbp-20h] BYREF
  struct _GUID v162; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int16 *v163; // [rsp+100h] [rbp+0h]
  _BYTE v164[8]; // [rsp+108h] [rbp+8h]
  unsigned __int16 *v165; // [rsp+110h] [rbp+10h]
  _WORD v166[4]; // [rsp+118h] [rbp+18h]
  RtlStringArray *v167; // [rsp+120h] [rbp+20h]
  RtlStringArray *v168; // [rsp+128h] [rbp+28h]
  RtlStringArray *v169; // [rsp+130h] [rbp+30h]
  struct RtlStringArray *v170; // [rsp+138h] [rbp+38h]
  RtlStringArray *v171[2]; // [rsp+140h] [rbp+40h]
  char v172; // [rsp+150h] [rbp+50h]
  char *v173; // [rsp+158h] [rbp+58h]
  __int16 v174; // [rsp+160h] [rbp+60h]
  _BYTE *v175; // [rsp+168h] [rbp+68h]
  _BYTE *v176; // [rsp+170h] [rbp+70h]
  _BYTE *v177; // [rsp+178h] [rbp+78h]
  _BYTE *v178; // [rsp+180h] [rbp+80h]
  _BYTE *v179; // [rsp+188h] [rbp+88h]
  const wchar_t *v180; // [rsp+190h] [rbp+90h]
  char v181; // [rsp+198h] [rbp+98h]
  char *v182; // [rsp+1A0h] [rbp+A0h]
  __int16 v183; // [rsp+1A8h] [rbp+A8h]
  _BYTE *v184; // [rsp+1B0h] [rbp+B0h]
  _BYTE *v185; // [rsp+1B8h] [rbp+B8h]
  _BYTE *v186; // [rsp+1C0h] [rbp+C0h]
  _BYTE *v187; // [rsp+1C8h] [rbp+C8h]
  _BYTE *v188; // [rsp+1D0h] [rbp+D0h]
  const wchar_t *v189; // [rsp+1D8h] [rbp+D8h]
  char v190; // [rsp+1E0h] [rbp+E0h]
  char *v191; // [rsp+1E8h] [rbp+E8h]
  __int16 v192; // [rsp+1F0h] [rbp+F0h]
  _BYTE *v193; // [rsp+1F8h] [rbp+F8h]
  _BYTE *v194; // [rsp+200h] [rbp+100h]
  _BYTE *v195; // [rsp+208h] [rbp+108h]
  _BYTE *v196; // [rsp+210h] [rbp+110h]
  _BYTE *v197; // [rsp+218h] [rbp+118h]
  _BYTE v198[56]; // [rsp+220h] [rbp+120h] BYREF
  _BYTE v199[56]; // [rsp+258h] [rbp+158h] BYREF
  _BYTE v200[56]; // [rsp+290h] [rbp+190h] BYREF
  _BYTE v201[56]; // [rsp+2C8h] [rbp+1C8h] BYREF
  _BYTE v202[56]; // [rsp+300h] [rbp+200h] BYREF
  _BYTE v203[56]; // [rsp+338h] [rbp+238h] BYREF
  _BYTE v204[56]; // [rsp+370h] [rbp+270h] BYREF
  _BYTE v205[56]; // [rsp+3A8h] [rbp+2A8h] BYREF
  _BYTE v206[56]; // [rsp+3E0h] [rbp+2E0h] BYREF
  _BYTE v207[56]; // [rsp+418h] [rbp+318h] BYREF
  _BYTE v208[56]; // [rsp+450h] [rbp+350h] BYREF
  _BYTE v209[56]; // [rsp+488h] [rbp+388h] BYREF
  _BYTE v210[56]; // [rsp+4C0h] [rbp+3C0h] BYREF
  _BYTE v211[56]; // [rsp+4F8h] [rbp+3F8h] BYREF
  _BYTE v212[56]; // [rsp+530h] [rbp+430h] BYREF
  _BYTE v213[56]; // [rsp+568h] [rbp+468h] BYREF
  _BYTE v214[56]; // [rsp+5A0h] [rbp+4A0h] BYREF
  _BYTE v215[56]; // [rsp+5D8h] [rbp+4D8h] BYREF
  _BYTE v216[56]; // [rsp+610h] [rbp+510h] BYREF
  _BYTE v217[56]; // [rsp+648h] [rbp+548h] BYREF
  _BYTE v218[56]; // [rsp+680h] [rbp+580h] BYREF
  GUID Buf1; // [rsp+6B8h] [rbp+5B8h] BYREF
  GUID Guid; // [rsp+6C8h] [rbp+5C8h] BYREF
  char v221; // [rsp+6D8h] [rbp+5D8h] BYREF
  char v222; // [rsp+6F0h] [rbp+5F0h] BYREF
  char v223; // [rsp+708h] [rbp+608h] BYREF
  char v224; // [rsp+720h] [rbp+620h] BYREF
  _WORD Data[40]; // [rsp+740h] [rbp+640h] BYREF
  _WORD v226[40]; // [rsp+790h] [rbp+690h] BYREF
  unsigned __int16 v227[264]; // [rsp+7E0h] [rbp+6E0h] BYREF
  WCHAR v228[264]; // [rsp+9F0h] [rbp+8F0h] BYREF
  WCHAR Dst[264]; // [rsp+C00h] [rbp+B00h] BYREF
  WCHAR v230[264]; // [rsp+E10h] [rbp+D10h] BYREF
  WCHAR v231[264]; // [rsp+1020h] [rbp+F20h] BYREF
  WCHAR pszPath[264]; // [rsp+1230h] [rbp+1130h] BYREF
  WCHAR Src[264]; // [rsp+1440h] [rbp+1340h] BYREF
  WCHAR v234[264]; // [rsp+1650h] [rbp+1550h] BYREF
  WCHAR FileName[264]; // [rsp+1860h] [rbp+1760h] BYREF

  v149 = a1;
  v1 = 0;
  v143 = 0;
  hKey[0] = 0;
  Guid = 0;
  Buf1 = 0;
  RtlStringArray::RtlStringArray((RtlStringArray *)v203);
  RtlStringArray::RtlStringArray((RtlStringArray *)v202);
  RtlStringArray::RtlStringArray((RtlStringArray *)v201);
  RtlStringArray::RtlStringArray((RtlStringArray *)v199);
  RtlStringArray::RtlStringArray((RtlStringArray *)v218);
  RtlStringArray::RtlStringArray((RtlStringArray *)v217);
  RtlStringArray::RtlStringArray((RtlStringArray *)v216);
  RtlStringArray::RtlStringArray((RtlStringArray *)v215);
  RtlStringArray::RtlStringArray((RtlStringArray *)v214);
  RtlStringArray::RtlStringArray((RtlStringArray *)v213);
  RtlStringArray::RtlStringArray((RtlStringArray *)v212);
  RtlStringArray::RtlStringArray((RtlStringArray *)v205);
  RtlStringArray::RtlStringArray((RtlStringArray *)v211);
  RtlStringArray::RtlStringArray((RtlStringArray *)v210);
  RtlStringArray::RtlStringArray((RtlStringArray *)v209);
  RtlStringArray::RtlStringArray((RtlStringArray *)v208);
  RtlStringArray::RtlStringArray((RtlStringArray *)v207);
  RtlStringArray::RtlStringArray((RtlStringArray *)v206);
  RtlStringArray::RtlStringArray((RtlStringArray *)v200);
  RtlStringArray::RtlStringArray((RtlStringArray *)v204);
  *(_WORD *)v150 = 0;
  *(_QWORD *)v158 = 0;
  *(_QWORD *)v159 = 0;
  *(_QWORD *)v155 = 0;
  *(_QWORD *)&v150[5] = 0;
  v2 = 0;
  v162 = 0;
  v3 = 0;
  Buf2 = 0;
  Guid = 0;
  Buf1 = 0;
  v163 = L"X86";
  v164[0] = 0;
  v165 = (unsigned __int16 *)&v221;
  v166[0] = 332;
  v167 = (RtlStringArray *)v203;
  v168 = (RtlStringArray *)v218;
  v169 = (RtlStringArray *)v214;
  v170 = (struct RtlStringArray *)v211;
  v171[0] = (RtlStringArray *)v207;
  v171[1] = (RtlStringArray *)L"AMD64";
  v172 = 0;
  v173 = &v222;
  v174 = -31132;
  v175 = v202;
  v176 = v217;
  v177 = v213;
  v178 = v210;
  v179 = v206;
  v180 = L"ARM";
  v181 = 0;
  v182 = &v223;
  v183 = 452;
  v184 = v201;
  v185 = v216;
  v186 = v212;
  v187 = v209;
  v188 = v200;
  v189 = L"ARM64";
  v190 = 0;
  v191 = &v224;
  v192 = -21916;
  v193 = v199;
  v194 = v215;
  v195 = v205;
  v196 = v208;
  v197 = v204;
  for ( i = 0; i < 4; ++i )
  {
    v157 = 0;
    MachineTypeAttributes = GetMachineTypeAttributes((unsigned __int16)v166[36 * i], &v157);
    if ( PcaFailedHr(&v143, MachineTypeAttributes) )
    {
      v133 = "GetMachineTypeAttributes failed (%d)";
      v15 = 1576;
      goto LABEL_296;
    }
    if ( (v157 & 1) != 0 )
      v164[72 * i] = 1;
    v6 = StringCchPrintfW(
           *(unsigned __int16 **)&v166[36 * i - 4],
           0xBu,
           L"%ls%ls",
           L"SACD_",
           *(_QWORD *)&v164[72 * i - 8]);
    if ( PcaFailedHr(&v143, v6) )
    {
      v15 = 1589;
LABEL_294:
      v133 = "StringCchPrintfW failed (%d)";
LABEL_296:
      v8 = v143;
      LODWORD(phkResult) = v143;
      AslLogCallPrintf(1, (unsigned int)"MergeSdbpGatherStoreAppFiles", v15, (_DWORD)v133, phkResult);
      goto LABEL_297;
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    hKey,
    0);
  v7 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags",
         0,
         0x2001Fu,
         hKey);
  v8 = v7;
  if ( v7 )
  {
    LODWORD(phkResulta) = v7;
    AslLogCallPrintf(
      1,
      (unsigned int)"MergeSdbpGatherStoreAppFiles",
      1595,
      (unsigned int)"RegOpenKeyExW failed (%d)",
      phkResulta);
    goto LABEL_297;
  }
  *(_QWORD *)v160 = 0;
  StoreAppInstallDirectory = MergeSdbpGetStoreAppInstallDirectory(v227, 0x104u, (unsigned __int64 *)v160);
  v8 = StoreAppInstallDirectory;
  v143 = StoreAppInstallDirectory;
  if ( StoreAppInstallDirectory )
  {
    LODWORD(phkResulta) = StoreAppInstallDirectory;
    AslLogCallPrintf(
      1,
      (unsigned int)"MergeSdbpGatherStoreAppFiles",
      1607,
      (unsigned int)"MergeSdbpGetStoreAppInstallDirectory failed (%d)",
      phkResulta);
    goto LABEL_297;
  }
  RegistryQWORD = PcaUtilityGetRegistryQWORD(hKey[0], 0, L"SAV", 0xFFFFFFFFFFFFFFFFuLL);
  if ( *(_QWORD *)v160 == RegistryQWORD )
    goto LABEL_292;
  v11 = 0;
  v12 = 0;
  v148 = 0;
  if ( v227[0] )
  {
    v14 = StringCchPrintfW(pszPath, 0x104u, L"%ls\\%ls", v227, L"ApplicationCompatibilityEnhancements.cat");
    if ( PcaFailedHr(&v143, v14) )
    {
      v15 = 1638;
      goto LABEL_294;
    }
    if ( PathFileExistsW(pszPath) )
    {
      v16 = StringCchPrintfW(v228, 0x104u, L"%ls\\sdb\\%ls", v227, L"msiMergeInboxStoreApp.sdb");
      if ( PcaFailedHr(&v143, v16) )
      {
        v15 = 1649;
        goto LABEL_294;
      }
      if ( PathFileExistsW(v228) )
      {
        v11 = 1;
        v17 = MergeSdbpExtractGuidAndTimestampFromSdb(v228, &Buf2, (unsigned __int64 *)v158);
        v8 = v17;
        v143 = v17;
        if ( v17 )
        {
          LODWORD(phkResult) = v17;
          AslLogCallPrintf(
            1,
            (unsigned int)"MergeSdbpGatherStoreAppFiles",
            1657,
            (unsigned int)"Failed to extract msi update sdb data (%d)",
            phkResult);
          goto LABEL_297;
        }
        v3 = Buf2;
      }
      v18 = StringCchPrintfW(v230, 0x104u, L"%ls\\sdb\\%ls", v227, L"sysMergeInboxStoreApp.sdb");
      if ( PcaFailedHr(&v143, v18) )
      {
        v15 = 1664;
        goto LABEL_294;
      }
      if ( PathFileExistsW(v230) )
      {
        v12 = 1;
        v148 = 1;
        v19 = MergeSdbpExtractGuidAndTimestampFromSdb(v230, &v162, (unsigned __int64 *)v159);
        v8 = v19;
        if ( v19 )
        {
          LODWORD(phkResult) = v19;
          AslLogCallPrintf(
            1,
            (unsigned int)"MergeSdbpGatherStoreAppFiles",
            1672,
            (unsigned int)"Failed to extract sys update sdb data (%d)",
            phkResult);
          goto LABEL_297;
        }
        v2 = v162;
      }
      for ( j = 0; j < 4; ++j )
      {
        if ( v164[72 * j] )
        {
          StoreAppDllsForArch = MergeSdbpGetStoreAppDllsForArch(
                                  *(const unsigned __int16 **)&v164[72 * j - 8],
                                  v227,
                                  *(&v168 + 9 * j),
                                  v171[9 * j - 1]);
          v22 = StoreAppDllsForArch;
          if ( StoreAppDllsForArch )
          {
            LODWORD(phkResult) = StoreAppDllsForArch;
            AslLogCallPrintf(
              1,
              (unsigned int)"MergeSdbpGatherStoreAppFiles",
              1686,
              (unsigned int)"MergeSdbpGetStoreAppDllsForArch failed (%d)",
              phkResult);
            goto LABEL_38;
          }
        }
      }
      goto LABEL_14;
    }
LABEL_292:
    v8 = 0;
    goto LABEL_297;
  }
  v228[0] = 0;
  v230[0] = 0;
LABEL_14:
  v146 = 0;
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(&v146);
  *(struct _GUID *)v152 = v3;
  SdbGuidAndTimestampFromRegistry = MergeSdbpGetSdbGuidAndTimestampFromRegistry(
                                      hKey[0],
                                      &v146,
                                      &Buf1,
                                      (__int64)v150,
                                      (__int64)v152,
                                      v11,
                                      L"SAIDMSI",
                                      L"SATMSI");
  v8 = SdbGuidAndTimestampFromRegistry;
  if ( SdbGuidAndTimestampFromRegistry )
  {
    LODWORD(phkResultb) = SdbGuidAndTimestampFromRegistry;
    AslLogCallPrintf(
      1,
      (unsigned int)"MergeSdbpGatherStoreAppFiles",
      1708,
      (unsigned int)"MergeSdbpGetSdbGuidAndTimestampFromRegistry failed (%d)",
      phkResultb);
    goto LABEL_16;
  }
  v152[0] = 0;
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(v152);
  *(struct _GUID *)v154 = v2;
  v23 = MergeSdbpGetSdbGuidAndTimestampFromRegistry(
          hKey[0],
          v152,
          &Guid,
          (__int64)&v150[1],
          (__int64)v154,
          v12,
          L"SAIDSYS",
          L"SATSYS");
  v8 = v23;
  v143 = v23;
  if ( v23 )
  {
    LODWORD(phkResultc) = v23;
    v26 = "MergeSdbpGetSdbGuidAndTimestampFromRegistry failed (%d)";
    v27 = 1724;
    goto LABEL_41;
  }
  for ( k = 0; k < 4; ++k )
  {
    if ( !v164[72 * k] )
      continue;
    v154[0] = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      v154,
      0);
    RegistryMULTISTRING = PcaUtilityGetRegistryMULTISTRING(
                            hKey[0],
                            v29,
                            *(const unsigned __int16 **)&v166[36 * k - 4],
                            (unsigned __int16 **)v154);
    v8 = RegistryMULTISTRING;
    v143 = RegistryMULTISTRING;
    if ( (RegistryMULTISTRING & 0xFFFFFFFC) != 0 || RegistryMULTISTRING == 1 )
    {
      LODWORD(phkResultc) = RegistryMULTISTRING;
      v46 = "Regkey lookup failed (%d)";
      v47 = 1740;
      goto LABEL_91;
    }
    if ( !v154[0] )
      goto LABEL_61;
    v31 = (ULONGLONG *)*(&v167 + 9 * k);
    v32 = RtlStringArray::FromMultiString((RtlStringArray *)v31, (const unsigned __int16 *)v154[0]);
    if ( PcaFailedHr(&v143, v32) )
    {
      v46 = "FromMultiString failed (%d)";
      v47 = 1747;
      goto LABEL_87;
    }
    RtlStringArray::Sort((RtlStringArray *)v31);
    if ( !v31[2] )
      goto LABEL_61;
    v33 = 0;
    do
    {
      v34 = 0;
      if ( v33 < v31[2] )
      {
        pullResult = 0;
        if ( ULongLongMult(v31[1], v33, &pullResult) < 0
          || (v34 = (_QWORD *)(v31[5] + pullResult), (unsigned __int64)v34 < v31[5]) )
        {
          v34 = v35;
        }
      }
      PluginDll = SdbGetPluginDll(*v34, (unsigned __int16)v166[36 * k], FileName);
      if ( PcaFailedNt(&v143, PluginDll) )
      {
        v46 = "SdbGetPluginDll failed (%d)";
        v47 = 1759;
LABEL_87:
        v8 = v143;
        LODWORD(phkResultc) = v143;
LABEL_91:
        AslLogCallPrintf(1, (unsigned int)"MergeSdbpGatherStoreAppFiles", v47, (_DWORD)v46, phkResultc);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v154);
        goto LABEL_42;
      }
      if ( !(unsigned int)AslDoesFileExistNtPath(FileName) )
      {
        RtlStringArray::Delete((RtlStringArray *)v31, v33--);
        goto LABEL_59;
      }
      v37 = RtlStringArray::Append(*(&v169 + 9 * k), FileName, 0);
      if ( PcaFailedHr(&v143, v37) )
      {
        v46 = "Append failed (%d)";
        v47 = 1770;
        goto LABEL_87;
      }
LABEL_59:
      ++v33;
    }
    while ( v33 < v31[2] );
    v1 = 0;
LABEL_61:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v154);
  }
  if ( v150[0] != v11 || memcmp_0(&Buf1, &Buf2, 0x10u) || (v145 = 0, *(_QWORD *)v155 != *(_QWORD *)v158) )
    v145 = 1;
  v144 = v150[1];
  if ( v150[1] != v12 || memcmp_0(&Guid, &v162, 0x10u) || *(_QWORD *)&v150[5] != *(_QWORD *)v159 )
    v1 = 1;
  v147 = v1;
  v38 = 0;
  while ( 2 )
  {
    if ( v164[72 * v38] )
    {
      v39 = (ULONGLONG *)v171[9 * v38 - 1];
      v40 = v39[2];
      if ( v40 )
      {
        v41 = 0;
        while ( 1 )
        {
          v42 = 0;
          if ( v41 < v40 )
          {
            v154[0] = 0;
            if ( ULongLongMult(v39[1], v41, v154) < 0
              || (v42 = (const unsigned __int16 **)(v39[5] + v154[0]), (unsigned __int64)v42 < v39[5]) )
            {
              v42 = v43;
            }
          }
          v22 = MergeSdbpVerifySignatureAgainstCatalog(*v42, pszPath, (unsigned __int8 **)v42, v25);
          v143 = v22;
          if ( v22 )
            break;
          ++v41;
          v40 = v39[2];
          if ( v41 >= v40 )
            goto LABEL_81;
        }
        v48 = "MergeSdbpVerifySignatureAgainstCatalog (%d)";
        v49 = 1798;
LABEL_93:
        LODWORD(phkResultc) = v22;
        AslLogCallPrintf(1, (unsigned int)"MergeSdbpGatherStoreAppFiles", v49, (_DWORD)v48, phkResultc);
        goto LABEL_94;
      }
    }
LABEL_81:
    if ( (unsigned __int64)++v38 < 4 )
      continue;
    break;
  }
  if ( v11 )
  {
    v44 = MergeSdbpVerifySignatureAgainstCatalog(v228, pszPath, v24, v25);
    v8 = v44;
    v143 = v44;
    if ( v44 )
    {
      v45 = 1806;
LABEL_85:
      LODWORD(phkResultc) = v44;
      AslLogCallPrintf(
        1,
        (unsigned int)"MergeSdbpGatherStoreAppFiles",
        v45,
        (unsigned int)"MergeSdbpVerifySignatureAgainstCatalog (%d)",
        phkResultc);
      goto LABEL_42;
    }
  }
  if ( v12 )
  {
    v44 = MergeSdbpVerifySignatureAgainstCatalog(v230, pszPath, v24, v25);
    v8 = v44;
    v143 = v44;
    if ( v44 )
    {
      v45 = 1813;
      goto LABEL_85;
    }
  }
  v50 = 0;
  if ( v1 )
    goto LABEL_126;
  v51 = 0;
  while ( 2 )
  {
    v50 = 0;
    if ( !v164[72 * v51] )
      goto LABEL_121;
    if ( *((_QWORD *)*(&v169 + 9 * v51) + 2) != *((_QWORD *)v171[9 * v51 - 1] + 2) )
    {
LABEL_124:
      v50 = 1;
      break;
    }
    v52 = (ULONGLONG *)*(&v168 + 9 * v51);
    if ( !v52[2] )
      goto LABEL_121;
    v53 = 0;
    while ( 2 )
    {
      v54 = 0;
      if ( v53 < v52[2] )
      {
        v154[0] = 0;
        if ( ULongLongMult(v52[1], v53, v154) < 0
          || (v54 = (const unsigned __int16 **)(v52[5] + v154[0]), (unsigned __int64)v54 < v52[5]) )
        {
          v54 = v55;
        }
      }
      v56 = RtlStringArray::Find(*(&v167 + 9 * v51), *v54);
      v151 = 0;
      if ( v56 == -1 )
        goto LABEL_124;
      v57 = v171[9 * v51 - 1];
      v58 = 0;
      if ( v53 < *((_QWORD *)v57 + 2) )
      {
        v154[0] = 0;
        if ( ULongLongMult(*((_QWORD *)v57 + 1), v53, v154) < 0
          || (v58 = (const unsigned __int16 **)(*(_QWORD *)(v59 + 40) + v154[0]),
              (unsigned __int64)v58 < *(_QWORD *)(v59 + 40)) )
        {
          v58 = v60;
        }
      }
      v61 = *v58;
      v62 = (__int64)*(&v169 + 9 * v51);
      v63 = 0;
      if ( v56 < *(_QWORD *)(v62 + 16) )
      {
        v154[0] = 0;
        if ( ULongLongMult(*(_QWORD *)(v62 + 8), v56, v154) < 0
          || (v63 = (const unsigned __int16 **)(*(_QWORD *)(v64 + 40) + v154[0]),
              (unsigned __int64)v63 < *(_QWORD *)(v64 + 40)) )
        {
          v63 = 0;
        }
      }
      v22 = MergeSdbpCompareDlls(*v63, v61, &v151);
      v143 = v22;
      if ( v22 )
      {
        v48 = "MergeSdbpCompareDlls failed (%d)";
        v49 = 1844;
        goto LABEL_93;
      }
      if ( !v151 )
        goto LABEL_124;
      if ( ++v53 < v52[2] )
        continue;
      break;
    }
    v50 = 0;
LABEL_121:
    if ( (unsigned __int64)++v51 < 4 )
      continue;
    break;
  }
  v1 = v147;
  v12 = v148;
LABEL_126:
  RegistryDWORD = PcaUtilityGetRegistryDWORD(hKey[0], 0, L"TestHookRapidMitigationsForceAddition", 0);
  LODWORD(v154[0]) = RegistryDWORD;
  if ( v145 )
  {
    LODWORD(pullResult) = -1;
    if ( !v150[0] )
      goto LABEL_144;
    if ( v11 && !memcmp_0(&Buf1, &Buf2, 0x10u) && *(_QWORD *)v155 < *(_QWORD *)v158 )
      goto LABEL_145;
    v66 = L" -mm";
    if ( !v149 )
      v66 = &sourceString;
    v67 = StringCchPrintfW(Src, 0x104u, L"%ls\\system32\\sdbinst.exe%ls -u -g %ls", L"%SYSTEMROOT%", v66, v146);
    if ( PcaFailedHr(&v143, v67) )
    {
      v27 = 1892;
LABEL_135:
      v26 = "StringCchPrintfW failed (%d)";
      goto LABEL_136;
    }
    v68 = ExpandEnvironmentStringsW(Src, Dst, 0x104u);
    if ( PcaFailedHr(&v143, v68) )
    {
      v26 = "Failed to create and expand sdbinst.exe path (%d)";
      v27 = 1899;
      goto LABEL_136;
    }
    v69 = MergeSdbpLaunchProcess(Dst, (unsigned int *)&pullResult);
    v8 = v69;
    v143 = v69;
    if ( v69 )
    {
      LODWORD(phkResultc) = v69;
      AslLogCallPrintf(
        1,
        (unsigned int)"MergeSdbpGatherStoreAppFiles",
        1904,
        (unsigned int)"Failed to remove installed merge db (%d)",
        phkResultc);
      goto LABEL_42;
    }
    if ( (_DWORD)pullResult )
    {
      phkResultc = Dst;
      AslLogCallPrintf(
        1,
        (unsigned int)"MergeSdbpGatherStoreAppFiles",
        1909,
        (unsigned int)"Sdbinst.exe (%ls) returned unexpected result (%d)");
    }
    else
    {
      LODWORD(phkResultc) = 0;
      AslLogCallPrintf(
        0,
        (unsigned int)"MergeSdbpGatherStoreAppFiles",
        1912,
        (unsigned int)"SdbInst.exe ran successfully for msi removal: %d");
    }
LABEL_144:
    if ( v11 )
    {
LABEL_145:
      v70 = L" -a";
      if ( !RegistryDWORD )
        v70 = &sourceString;
      v71 = L" -mm";
      if ( !v149 )
        v71 = &sourceString;
      v72 = StringCchPrintfW(Src, 0x104u, L"%ls\\system32\\sdbinst.exe%ls%ls \"%ls\"", L"%SYSTEMROOT%", v71, v70, v228);
      if ( PcaFailedHr(&v143, v72) )
      {
        v27 = 1924;
        goto LABEL_135;
      }
      v73 = ExpandEnvironmentStringsW(Src, Dst, 0x104u);
      if ( PcaFailedHr(&v143, v73) )
      {
        v26 = "Failed to create and expand sdbinst.exe path (%d)";
        v27 = 1931;
        goto LABEL_136;
      }
      v74 = MergeSdbpLaunchProcess(Dst, (unsigned int *)&pullResult);
      v8 = v74;
      v143 = v74;
      if ( v74 )
      {
        LODWORD(phkResultc) = v74;
        AslLogCallPrintf(
          1,
          (unsigned int)"MergeSdbpGatherStoreAppFiles",
          1936,
          (unsigned int)"Failed to install merge db (%d)",
          phkResultc);
        goto LABEL_42;
      }
      if ( (_DWORD)pullResult )
      {
        phkResultc = Dst;
        AslLogCallPrintf(
          1,
          (unsigned int)"MergeSdbpGatherStoreAppFiles",
          1941,
          (unsigned int)"Sdbinst.exe (%ls) returned unexpected result (%d)");
      }
      else
      {
        LODWORD(phkResultc) = 0;
        AslLogCallPrintf(
          0,
          (unsigned int)"MergeSdbpGatherStoreAppFiles",
          1944,
          (unsigned int)"SdbInst.exe ran successfully for msi update/add: %d");
      }
    }
    if ( !(_DWORD)pullResult )
    {
      if ( v11 )
      {
        v75 = AslGuidToString(Data, 40, &Buf2);
        if ( PcaFailedNt(&v143, v75) )
        {
          v26 = "AslGuidToString failed (%d)";
          v27 = 1953;
          goto LABEL_136;
        }
        v76 = -1;
        do
          ++v76;
        while ( Data[v76] );
        v77 = RegSetValueExW(hKey[0], L"SAIDMSI", 0, 1u, (const BYTE *)Data, 2 * v76 + 2);
        v8 = v77;
        if ( v77 )
        {
          LODWORD(phkResultd) = v77;
          AslLogCallPrintf(
            1,
            (unsigned int)"MergeSdbpGatherStoreAppFiles",
            1963,
            (unsigned int)"RegSetValueExW failed (%d)",
            phkResultd);
          goto LABEL_42;
        }
        v78 = RegSetValueExW(hKey[0], L"SATMSI", 0, 0xBu, v158, 8u);
        v8 = v78;
        v143 = v78;
        if ( v78 )
        {
          LODWORD(phkResultc) = v78;
          AslLogCallPrintf(
            1,
            (unsigned int)"MergeSdbpGatherStoreAppFiles",
            1973,
            (unsigned int)"RegSetValueExW failed (%d)",
            phkResultc);
          goto LABEL_42;
        }
      }
      else
      {
        v79 = RegDeleteValueW(hKey[0], L"SAIDMSI");
        v8 = v79;
        if ( v79 )
        {
          LODWORD(phkResultc) = v79;
          AslLogCallPrintf(
            1,
            (unsigned int)"MergeSdbpGatherStoreAppFiles",
            1979,
            (unsigned int)"RegDeleteValueW failed (%d)",
            phkResultc);
          goto LABEL_42;
        }
        v80 = RegDeleteValueW(hKey[0], L"SATMSI");
        v8 = v80;
        v143 = v80;
        if ( v80 )
        {
          LODWORD(phkResultc) = v80;
          AslLogCallPrintf(
            1,
            (unsigned int)"MergeSdbpGatherStoreAppFiles",
            1984,
            (unsigned int)"RegDeleteValueW failed (%d)",
            phkResultc);
          goto LABEL_42;
        }
      }
    }
  }
  if ( !v1 && !v50 )
  {
LABEL_289:
    v131 = RegSetValueExW(hKey[0], L"SAV", 0, 0xBu, v160, 8u);
    v8 = v131;
    if ( v131 )
    {
      LODWORD(phkResultg) = v131;
      AslLogCallPrintf(
        1,
        (unsigned int)"MergeSdbpGatherStoreAppFiles",
        2256,
        (unsigned int)"RegSetValueExW failed (%d)",
        phkResultg);
      goto LABEL_42;
    }
    g_TipTest_StoreAppStateWasModified = 1;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v152);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v146);
    RtlStringArray::~RtlStringArray((RtlStringArray *)v204);
    RtlStringArray::~RtlStringArray((RtlStringArray *)v200);
    RtlStringArray::~RtlStringArray((RtlStringArray *)v206);
    RtlStringArray::~RtlStringArray((RtlStringArray *)v207);
    RtlStringArray::~RtlStringArray((RtlStringArray *)v208);
    RtlStringArray::~RtlStringArray((RtlStringArray *)v209);
    RtlStringArray::~RtlStringArray((RtlStringArray *)v210);
    RtlStringArray::~RtlStringArray((RtlStringArray *)v211);
    RtlStringArray::~RtlStringArray((RtlStringArray *)v205);
    RtlStringArray::~RtlStringArray((RtlStringArray *)v212);
    RtlStringArray::~RtlStringArray((RtlStringArray *)v213);
    RtlStringArray::~RtlStringArray((RtlStringArray *)v214);
    RtlStringArray::~RtlStringArray((RtlStringArray *)v215);
    RtlStringArray::~RtlStringArray((RtlStringArray *)v216);
    RtlStringArray::~RtlStringArray((RtlStringArray *)v217);
    RtlStringArray::~RtlStringArray((RtlStringArray *)v218);
    RtlStringArray::~RtlStringArray((RtlStringArray *)v199);
    RtlStringArray::~RtlStringArray((RtlStringArray *)v201);
    RtlStringArray::~RtlStringArray((RtlStringArray *)v202);
    RtlStringArray::~RtlStringArray((RtlStringArray *)v203);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(hKey);
    return 0;
  }
  v155[0] = -1;
  if ( !v150[1] || v50 )
    goto LABEL_190;
  if ( !v12 || memcmp_0(&Guid, &v162, 0x10u) || *(_QWORD *)&v150[5] >= *(_QWORD *)v159 )
  {
    v81 = L" -mm";
    if ( !v149 )
      v81 = &sourceString;
    v82 = StringCchPrintfW(v234, 0x104u, L"%ls\\system32\\sdbinst.exe%ls -u -g %ls", L"%SYSTEMROOT%", v81, v152[0]);
    if ( PcaFailedHr(&v143, v82) )
    {
      v27 = 2024;
      goto LABEL_135;
    }
    v83 = ExpandEnvironmentStringsW(v234, v231, 0x104u);
    if ( PcaFailedHr(&v143, v83) )
    {
      v26 = "Failed to create and expand sdbinst.exe path (%d)";
      v27 = 2031;
      goto LABEL_136;
    }
    v84 = MergeSdbpLaunchProcess(v231, v155);
    v8 = v84;
    v143 = v84;
    if ( v84 )
    {
      LODWORD(phkResultc) = v84;
      AslLogCallPrintf(
        1,
        (unsigned int)"MergeSdbpGatherStoreAppFiles",
        2036,
        (unsigned int)"Failed to remove installed merge db (%d)",
        phkResultc);
      goto LABEL_42;
    }
    if ( v155[0] )
    {
      phkResultc = v231;
      AslLogCallPrintf(
        1,
        (unsigned int)"MergeSdbpGatherStoreAppFiles",
        2041,
        (unsigned int)"Sdbinst.exe (%ls) returned unexpected result (%d)");
    }
    else
    {
      v144 = 0;
      LODWORD(phkResultc) = 0;
      AslLogCallPrintf(
        0,
        (unsigned int)"MergeSdbpGatherStoreAppFiles",
        2045,
        (unsigned int)"SdbInst.exe ran successfully for sys removal: %d");
    }
LABEL_190:
    if ( !v12 )
      goto LABEL_242;
  }
  v85 = 0;
  while ( 2 )
  {
    if ( v164[72 * v85] )
    {
      RtlStringArray::RtlStringArray((RtlStringArray *)v198);
      RtlStringArray::Initialize((RtlStringArray *)v198, v86, 0, 0x10u, (int)phkResultc);
      v87 = RtlStringArray::AppendFrom((RtlStringArray *)v198, *(&v168 + 9 * v85));
      if ( PcaFailedHr(&v143, v87) )
      {
        v111 = 2065;
      }
      else
      {
        v88 = RtlStringArray::AppendFrom((RtlStringArray *)v198, *(&v167 + 9 * v85));
        if ( !PcaFailedHr(&v143, v88) )
        {
          v89 = MergeSdbpSetInstalledShimDlls(hKey, v198, *(_QWORD *)&v166[36 * v85 - 4]);
          v22 = v89;
          v143 = v89;
          if ( !v89 )
          {
            RtlStringArray::~RtlStringArray((RtlStringArray *)v198);
            goto LABEL_197;
          }
          LODWORD(phkResultc) = v89;
          AslLogCallPrintf(
            1,
            (unsigned int)"MergeSdbpGatherStoreAppFiles",
            2075,
            (unsigned int)"MergeSdbpSetInstalledShimDlls failed (%d)",
            phkResultc);
          RtlStringArray::~RtlStringArray((RtlStringArray *)v198);
LABEL_94:
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v152);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v146);
LABEL_38:
          v8 = v22;
          goto LABEL_297;
        }
        v111 = 2070;
      }
      v8 = v143;
      LODWORD(phkResultc) = v143;
      AslLogCallPrintf(
        1,
        (unsigned int)"MergeSdbpGatherStoreAppFiles",
        v111,
        (unsigned int)"AppendFrom failed (%d)",
        phkResultc);
      RtlStringArray::~RtlStringArray((RtlStringArray *)v198);
      goto LABEL_42;
    }
LABEL_197:
    if ( (unsigned __int64)++v85 < 4 )
      continue;
    break;
  }
  for ( m = 0; m < 4; ++m )
  {
    if ( v164[72 * m] )
    {
      v91 = (ULONGLONG *)*(&v168 + 9 * m);
      if ( v91[2] )
      {
        v92 = 0;
        do
        {
          v93 = 0;
          if ( v92 < v91[2] )
          {
            *(_QWORD *)&v150[5] = 0;
            if ( ULongLongMult(v91[1], v92, (ULONGLONG *)&v150[5]) < 0
              || (v93 = (const unsigned __int16 **)(v91[5] + *(_QWORD *)&v150[5]), (unsigned __int64)v93 < v91[5]) )
            {
              v93 = 0;
            }
          }
          v94 = RtlStringArray::Find(*(&v167 + 9 * m), *v93);
          v145 = 0;
          if ( v94 == -1 )
            goto LABEL_217;
          v95 = v171[9 * m - 1];
          v96 = 0;
          if ( v92 < *((_QWORD *)v95 + 2) )
          {
            *(_QWORD *)&v150[5] = 0;
            if ( ULongLongMult(*((_QWORD *)v95 + 1), v92, (ULONGLONG *)&v150[5]) < 0
              || (v96 = (const unsigned __int16 **)(*(_QWORD *)(v97 + 40) + *(_QWORD *)&v150[5]),
                  (unsigned __int64)v96 < *(_QWORD *)(v97 + 40)) )
            {
              v96 = 0;
            }
          }
          v98 = *v96;
          v99 = (__int64)*(&v169 + 9 * m);
          v100 = 0;
          if ( v94 < *(_QWORD *)(v99 + 16) )
          {
            *(_QWORD *)&v150[5] = 0;
            if ( ULongLongMult(*(_QWORD *)(v99 + 8), v94, (ULONGLONG *)&v150[5]) < 0
              || (v100 = (const unsigned __int16 **)(*(_QWORD *)(v101 + 40) + *(_QWORD *)&v150[5]),
                  (unsigned __int64)v100 < *(_QWORD *)(v101 + 40)) )
            {
              v100 = 0;
            }
          }
          v102 = MergeSdbpCompareDlls(*v100, v98, &v145);
          v103 = v102;
          v143 = v102;
          if ( v102 )
          {
            LODWORD(phkResultc) = v102;
            AslLogCallPrintf(
              1,
              (unsigned int)"MergeSdbpGatherStoreAppFiles",
              2098,
              (unsigned int)"MergeSdbpCompareDlls failed (%d)",
              phkResultc);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v152);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v146);
            v8 = v103;
            goto LABEL_297;
          }
          if ( !v145 )
          {
LABEL_217:
            v104 = v171[9 * m - 1];
            v105 = 0;
            if ( v92 < *((_QWORD *)v104 + 2) )
            {
              *(_QWORD *)&v150[5] = 0;
              if ( ULongLongMult(*((_QWORD *)v104 + 1), v92, (ULONGLONG *)&v150[5]) < 0
                || (v105 = (LPCWSTR *)(*(_QWORD *)(v106 + 40) + *(_QWORD *)&v150[5]),
                    (unsigned __int64)v105 < *(_QWORD *)(v106 + 40)) )
              {
                v105 = 0;
              }
            }
            v107 = SdbAddPluginDll(*v105, v166[36 * m]);
            if ( PcaFailedNt(&v143, v107) )
            {
              LODWORD(phkResultc) = v143;
              AslLogCallPrintf(
                1,
                (unsigned int)"MergeSdbpGatherStoreAppFiles",
                2108,
                (unsigned int)"SdbAddPluginDll failed, swallowing (%d)",
                phkResultc);
            }
          }
          ++v92;
        }
        while ( v92 < v91[2] );
      }
    }
  }
  v108 = L" -a";
  if ( !LODWORD(v154[0]) )
    v108 = &sourceString;
  v109 = L" -mm";
  if ( !v149 )
    v109 = &sourceString;
  v110 = StringCchPrintfW(v234, 0x104u, L"%ls\\system32\\sdbinst.exe%ls%ls \"%ls\"", L"%SYSTEMROOT%", v109, v108, v230);
  if ( PcaFailedHr(&v143, v110) )
  {
    v27 = 2118;
    goto LABEL_135;
  }
  v112 = ExpandEnvironmentStringsW(v234, v231, 0x104u);
  if ( PcaFailedHr(&v143, v112) )
  {
    v26 = "Failed to create and expand sdbinst.exe path (%d)";
    v27 = 2125;
    goto LABEL_136;
  }
  v113 = MergeSdbpLaunchProcess(v231, v155);
  v8 = v113;
  v143 = v113;
  if ( v113 )
  {
    LODWORD(phkResultc) = v113;
    AslLogCallPrintf(
      1,
      (unsigned int)"MergeSdbpGatherStoreAppFiles",
      2130,
      (unsigned int)"Failed to install merge db (%d)",
      phkResultc);
    goto LABEL_42;
  }
  if ( !v155[0] )
  {
    v114 = 1;
    v144 = 1;
    LODWORD(phkResultc) = 0;
    AslLogCallPrintf(
      0,
      (unsigned int)"MergeSdbpGatherStoreAppFiles",
      2140,
      (unsigned int)"SdbInst.exe ran successfully for sys update/add: %d",
      phkResultc);
    goto LABEL_243;
  }
  cbData[0] = v155[0];
  AslLogCallPrintf(
    1,
    (unsigned int)"MergeSdbpGatherStoreAppFiles",
    2135,
    (unsigned int)"Sdbinst.exe (%ls) returned unexpected result (%d)",
    v231,
    *(_QWORD *)cbData);
LABEL_242:
  v114 = v144;
  if ( v144 )
  {
LABEL_267:
    for ( n = 0; n < 4; ++n )
    {
      if ( v164[72 * n] )
      {
        v22 = MergeSdbpSetInstalledShimDlls(hKey, v171[9 * n], *(_QWORD *)&v166[36 * n - 4]);
        v143 = v22;
        if ( v22 )
        {
          v48 = "MergeSdbpSetInstalledShimDlls failed (%d)";
          v49 = 2192;
          goto LABEL_93;
        }
      }
    }
    if ( v155[0] )
      goto LABEL_289;
    if ( v114 )
    {
      v125 = AslGuidToString(v226, 40, &v162);
      if ( PcaFailedNt(&v143, v125) )
      {
        v26 = "AslGuidToString failed (%d)";
        v27 = 2206;
        goto LABEL_136;
      }
      v126 = -1;
      do
        ++v126;
      while ( v226[v126] );
      v127 = RegSetValueExW(hKey[0], L"SAIDSYS", 0, 1u, (const BYTE *)v226, 2 * v126 + 2);
      v8 = v127;
      if ( v127 )
      {
        LODWORD(phkResulte) = v127;
        AslLogCallPrintf(
          1,
          (unsigned int)"MergeSdbpGatherStoreAppFiles",
          2216,
          (unsigned int)"RegSetValueExW failed (%d)",
          phkResulte);
        goto LABEL_42;
      }
      v128 = RegSetValueExW(hKey[0], L"SATSYS", 0, 0xBu, v159, 8u);
      v8 = v128;
      if ( v128 )
      {
        LODWORD(phkResultf) = v128;
        AslLogCallPrintf(
          1,
          (unsigned int)"MergeSdbpGatherStoreAppFiles",
          2226,
          (unsigned int)"RegSetValueExW failed (%d)",
          phkResultf);
        goto LABEL_42;
      }
    }
    else
    {
      v129 = RegDeleteValueW(hKey[0], L"SAIDSYS");
      v8 = v129;
      if ( v129 )
      {
        LODWORD(phkResultc) = v129;
        AslLogCallPrintf(
          1,
          (unsigned int)"MergeSdbpGatherStoreAppFiles",
          2232,
          (unsigned int)"RegDeleteValueW failed (%d)",
          phkResultc);
        goto LABEL_42;
      }
      v130 = RegDeleteValueW(hKey[0], L"SATSYS");
      v8 = v130;
      if ( v130 )
      {
        LODWORD(phkResultc) = v130;
        AslLogCallPrintf(
          1,
          (unsigned int)"MergeSdbpGatherStoreAppFiles",
          2237,
          (unsigned int)"RegDeleteValueW failed (%d)",
          phkResultc);
        goto LABEL_42;
      }
    }
    goto LABEL_289;
  }
LABEL_243:
  v115 = 0;
  while ( !v164[72 * v115] )
  {
LABEL_266:
    if ( (unsigned __int64)++v115 >= 4 )
      goto LABEL_267;
  }
  v116 = RtlStringArray::AppendFrom(v171[9 * v115], *(&v168 + 9 * v115));
  if ( !PcaFailedHr(&v143, v116) )
  {
    v117 = (ULONGLONG *)*(&v167 + 9 * v115);
    if ( v117[2] )
    {
      v118 = 0;
      while ( 1 )
      {
        if ( !v114 )
          goto LABEL_254;
        v119 = 0;
        if ( v118 < v117[2] )
        {
          *(_QWORD *)&v150[5] = 0;
          if ( ULongLongMult(v117[1], v118, (ULONGLONG *)&v150[5]) < 0
            || (v119 = (const unsigned __int16 **)(v117[5] + *(_QWORD *)&v150[5]), (unsigned __int64)v119 < v117[5]) )
          {
            v119 = 0;
          }
        }
        if ( RtlStringArray::Find(*(&v168 + 9 * v115), *v119) == -1 )
        {
LABEL_254:
          v120 = 0;
          if ( v118 < v117[2] )
          {
            *(_QWORD *)&v150[5] = 0;
            if ( ULongLongMult(v117[1], v118, (ULONGLONG *)&v150[5]) < 0
              || (v120 = (__int64 *)(v117[5] + *(_QWORD *)&v150[5]), (unsigned __int64)v120 < v117[5]) )
            {
              v120 = 0;
            }
          }
          v121 = SdbRemovePluginDll(*v120, (unsigned __int16)v166[36 * v115]);
          if ( PcaFailedNt(&v143, v121) )
          {
            LODWORD(phkResultc) = v143;
            AslLogCallPrintf(
              1,
              (unsigned int)"MergeSdbpGatherStoreAppFiles",
              2171,
              (unsigned int)"SdbRemovePluginDll failed, swallowing (%d)",
              phkResultc);
            v122 = 0;
            if ( v118 < v117[2] )
            {
              *(_QWORD *)&v150[5] = 0;
              if ( ULongLongMult(v117[1], v118, (ULONGLONG *)&v150[5]) < 0
                || (v122 = (const unsigned __int16 **)(v117[5] + *(_QWORD *)&v150[5]), (unsigned __int64)v122 < v117[5]) )
              {
                v122 = 0;
              }
            }
            v123 = RtlStringArray::Append(v171[9 * v115], *v122, 0);
            if ( PcaFailedHr(&v143, v123) )
            {
              v26 = "Append failed (%d)";
              v27 = 2174;
              goto LABEL_136;
            }
          }
          v114 = v144;
        }
        if ( ++v118 >= v117[2] )
          goto LABEL_266;
      }
    }
    goto LABEL_266;
  }
  v26 = "AppendFrom failed (%d)";
  v27 = 2155;
LABEL_136:
  v8 = v143;
  LODWORD(phkResultc) = v143;
LABEL_41:
  AslLogCallPrintf(1, (unsigned int)"MergeSdbpGatherStoreAppFiles", v27, (_DWORD)v26, phkResultc);
LABEL_42:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v152);
LABEL_16:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v146);
LABEL_297:
  RtlStringArray::~RtlStringArray((RtlStringArray *)v204);
  RtlStringArray::~RtlStringArray((RtlStringArray *)v200);
  RtlStringArray::~RtlStringArray((RtlStringArray *)v206);
  RtlStringArray::~RtlStringArray((RtlStringArray *)v207);
  RtlStringArray::~RtlStringArray((RtlStringArray *)v208);
  RtlStringArray::~RtlStringArray((RtlStringArray *)v209);
  RtlStringArray::~RtlStringArray((RtlStringArray *)v210);
  RtlStringArray::~RtlStringArray((RtlStringArray *)v211);
  RtlStringArray::~RtlStringArray((RtlStringArray *)v205);
  RtlStringArray::~RtlStringArray((RtlStringArray *)v212);
  RtlStringArray::~RtlStringArray((RtlStringArray *)v213);
  RtlStringArray::~RtlStringArray((RtlStringArray *)v214);
  RtlStringArray::~RtlStringArray((RtlStringArray *)v215);
  RtlStringArray::~RtlStringArray((RtlStringArray *)v216);
  RtlStringArray::~RtlStringArray((RtlStringArray *)v217);
  RtlStringArray::~RtlStringArray((RtlStringArray *)v218);
  RtlStringArray::~RtlStringArray((RtlStringArray *)v199);
  RtlStringArray::~RtlStringArray((RtlStringArray *)v201);
  RtlStringArray::~RtlStringArray((RtlStringArray *)v202);
  RtlStringArray::~RtlStringArray((RtlStringArray *)v203);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(hKey);
  return v8;
}

```

## disassembly

```asm
0x180043424  push    rbp
0x180043426  push    rbx
0x180043427  push    rsi
0x180043428  push    rdi
0x180043429  push    r12
0x18004342b  push    r13
0x18004342d  push    r14
0x18004342f  push    r15
0x180043431  lea     rbp, [rsp-19A8h]
0x180043439  mov     eax, 1AA8h
0x18004343e  call    _alloca_probe
0x180043443  sub     rsp, rax
0x180043446  movaps  [rsp+1AE0h+var_50], xmm6
0x18004344e  movaps  [rsp+1AE0h+var_60], xmm7
0x180043456  mov     rax, cs:__security_cookie
0x18004345d  xor     rax, rsp
0x180043460  mov     [rbp+19E0h+var_70], rax
0x180043467  mov     [rsp+1AE0h+var_1A7E], cl
0x18004346b  xor     r15d, r15d
0x18004346e  mov     [rsp+1AE0h+var_1A90], r15d
0x180043473  mov     [rbp+19E0h+hKey], r15
0x180043477  mov     qword ptr [rbp+19E0h+var_1A10], r15
0x18004347b  mov     qword ptr [rbp+19E0h+var_1A18], r15
0x18004347f  xorps   xmm0, xmm0
0x180043482  movups  xmmword ptr [rbp+19E0h+Guid.Data1], xmm0
0x180043489  xorps   xmm1, xmm1
0x18004348c  movups  [rbp+19E0h+Buf1], xmm1
0x180043493  lea     rcx, [rbp+19E0h+var_17A8]; this
0x18004349a  call    ??0RtlStringArray@@QEAA@XZ; RtlStringArray::RtlStringArray(void)
0x18004349f  nop
0x1800434a0  lea     rcx, [rbp+19E0h+var_17E0]; this
0x1800434a7  call    ??0RtlStringArray@@QEAA@XZ; RtlStringArray::RtlStringArray(void)
0x1800434ac  nop
0x1800434ad  lea     rcx, [rbp+19E0h+var_1818]; this
0x1800434b4  call    ??0RtlStringArray@@QEAA@XZ; RtlStringArray::RtlStringArray(void)
0x1800434b9  nop
0x1800434ba  lea     rcx, [rbp+19E0h+var_1888]; this
0x1800434c1  call    ??0RtlStringArray@@QEAA@XZ; RtlStringArray::RtlStringArray(void)
0x1800434c6  nop
0x1800434c7  lea     rcx, [rbp+19E0h+var_1460]; this
0x1800434ce  call    ??0RtlStringArray@@QEAA@XZ; RtlStringArray::RtlStringArray(void)
0x1800434d3  nop
0x1800434d4  lea     rcx, [rbp+19E0h+var_1498]; this
0x1800434db  call    ??0RtlStringArray@@QEAA@XZ; RtlStringArray::RtlStringArray(void)
0x1800434e0  nop
0x1800434e1  lea     rcx, [rbp+19E0h+var_14D0]; this
0x1800434e8  call    ??0RtlStringArray@@QEAA@XZ; RtlStringArray::RtlStringArray(void)
0x1800434ed  nop
0x1800434ee  lea     rcx, [rbp+19E0h+var_1508]; this
0x1800434f5  call    ??0RtlStringArray@@QEAA@XZ; RtlStringArray::RtlStringArray(void)
0x1800434fa  nop
0x1800434fb  lea     rcx, [rbp+19E0h+var_1540]; this
0x180043502  call    ??0RtlStringArray@@QEAA@XZ; RtlStringArray::RtlStringArray(void)
0x180043507  nop
0x180043508  lea     rcx, [rbp+19E0h+var_1578]; this
0x18004350f  call    ??0RtlStringArray@@QEAA@XZ; RtlStringArray::RtlStringArray(void)
0x180043514  nop
0x180043515  lea     rcx, [rbp+19E0h+var_15B0]; this
0x18004351c  call    ??0RtlStringArray@@QEAA@XZ; RtlStringArray::RtlStringArray(void)
0x180043521  nop
0x180043522  lea     rcx, [rbp+19E0h+var_1738]; this
0x180043529  call    ??0RtlStringArray@@QEAA@XZ; RtlStringArray::RtlStringArray(void)
0x18004352e  nop
0x18004352f  lea     rcx, [rbp+19E0h+var_15E8]; this
0x180043536  call    ??0RtlStringArray@@QEAA@XZ; RtlStringArray::RtlStringArray(void)
0x18004353b  nop
0x18004353c  lea     rcx, [rbp+19E0h+var_1620]; this
0x180043543  call    ??0RtlStringArray@@QEAA@XZ; RtlStringArray::RtlStringArray(void)
0x180043548  nop
0x180043549  lea     rcx, [rbp+19E0h+var_1658]; this
0x180043550  call    ??0RtlStringArray@@QEAA@XZ; RtlStringArray::RtlStringArray(void)
0x180043555  nop
0x180043556  lea     rcx, [rbp+19E0h+var_1690]; this
0x18004355d  call    ??0RtlStringArray@@QEAA@XZ; RtlStringArray::RtlStringArray(void)
0x180043562  nop
0x180043563  lea     rcx, [rbp+19E0h+var_16C8]; this
0x18004356a  call    ??0RtlStringArray@@QEAA@XZ; RtlStringArray::RtlStringArray(void)
0x18004356f  nop
0x180043570  lea     rcx, [rbp+19E0h+var_1700]; this
0x180043577  call    ??0RtlStringArray@@QEAA@XZ; RtlStringArray::RtlStringArray(void)
0x18004357c  nop
0x18004357d  lea     rcx, [rbp+19E0h+var_1850]; this
0x180043584  call    ??0RtlStringArray@@QEAA@XZ; RtlStringArray::RtlStringArray(void)
0x180043589  nop
0x18004358a  lea     rcx, [rbp+19E0h+var_1770]; this
0x180043591  call    ??0RtlStringArray@@QEAA@XZ; RtlStringArray::RtlStringArray(void)
0x180043596  nop
0x180043597  mov     [rsp+1AE0h+var_1A7D], r15b
0x18004359c  mov     [rsp+1AE0h+var_1A7D+1], r15b
0x1800435a1  mov     qword ptr [rbp+19E0h+var_1A18], r15
0x1800435a5  mov     qword ptr [rbp+19E0h+var_1A10], r15
0x1800435a9  mov     qword ptr [rbp+19E0h+var_1A30], r15
0x1800435ad  mov     qword ptr [rsp+1AE0h+var_1A7D+5], r15
0x1800435b2  xorps   xmm7, xmm7
0x1800435b5  movaps  xmmword ptr [rbp+19E0h+var_19F0.Data1], xmm7
0x1800435b9  xorps   xmm6, xmm6
0x1800435bc  movaps  [rbp+19E0h+Buf2], xmm6
0x1800435c0  xorps   xmm0, xmm0
0x1800435c3  movups  xmmword ptr [rbp+19E0h+Guid.Data1], xmm0
0x1800435ca  xorps   xmm1, xmm1
0x1800435cd  movups  [rbp+19E0h+Buf1], xmm1
0x1800435d4  lea     rax, aX86; "X86"
0x1800435db  mov     [rbp+19E0h+var_19E0], rax
0x1800435df  mov     [rbp+19E0h+var_19D8], r15b
0x1800435e3  lea     rax, [rbp+19E0h+var_1408]
0x1800435ea  mov     [rbp+19E0h+var_19D0], rax
0x1800435ee  mov     eax, 14Ch
0x1800435f3  mov     [rbp+19E0h+var_19C8], ax
0x1800435f7  lea     rax, [rbp+19E0h+var_17A8]
0x1800435fe  mov     [rbp+19E0h+var_19C0], rax
0x180043602  lea     rax, [rbp+19E0h+var_1460]
0x180043609  mov     [rbp+19E0h+var_19B8], rax
0x18004360d  lea     rax, [rbp+19E0h+var_1540]
0x180043614  mov     [rbp+19E0h+var_19B0], rax
0x180043618  lea     rax, [rbp+19E0h+var_15E8]
0x18004361f  mov     [rbp+19E0h+var_19A8], rax
0x180043623  lea     rax, [rbp+19E0h+var_16C8]
0x18004362a  mov     [rbp+19E0h+var_19A0], rax
0x18004362e  lea     rax, aAmd64; "AMD64"
0x180043635  mov     [rbp+19E0h+var_1998], rax
0x180043639  mov     [rbp+19E0h+var_1990], r15b
0x18004363d  lea     rax, [rbp+19E0h+var_13F0]
0x180043644  mov     [rbp+19E0h+var_1988], rax
0x180043648  mov     eax, 8664h
0x18004364d  mov     [rbp+19E0h+var_1980], ax
0x180043651  lea     rax, [rbp+19E0h+var_17E0]
0x180043658  mov     [rbp+19E0h+var_1978], rax
0x18004365c  lea     rax, [rbp+19E0h+var_1498]
0x180043663  mov     [rbp+19E0h+var_1970], rax
0x180043667  lea     rax, [rbp+19E0h+var_1578]
0x18004366e  mov     [rbp+19E0h+var_1968], rax
0x180043672  lea     rax, [rbp+19E0h+var_1620]
0x180043679  mov     [rbp+19E0h+var_1960], rax
0x180043680  lea     rax, [rbp+19E0h+var_1700]
0x180043687  mov     [rbp+19E0h+var_1958], rax
0x18004368e  lea     rax, aArm; "ARM"
0x180043695  mov     [rbp+19E0h+var_1950], rax
0x18004369c  mov     [rbp+19E0h+var_1948], r15b
0x1800436a3  lea     rax, [rbp+19E0h+var_13D8]
0x1800436aa  mov     [rbp+19E0h+var_1940], rax
0x1800436b1  mov     eax, 1C4h
0x1800436b6  mov     [rbp+19E0h+var_1938], ax
0x1800436bd  lea     rax, [rbp+19E0h+var_1818]
0x1800436c4  mov     [rbp+19E0h+var_1930], rax
0x1800436cb  lea     rax, [rbp+19E0h+var_14D0]
0x1800436d2  mov     [rbp+19E0h+var_1928], rax
0x1800436d9  lea     rax, [rbp+19E0h+var_15B0]
0x1800436e0  mov     [rbp+19E0h+var_1920], rax
0x1800436e7  lea     rax, [rbp+19E0h+var_1658]
0x1800436ee  mov     [rbp+19E0h+var_1918], rax
0x1800436f5  lea     rax, [rbp+19E0h+var_1850]
0x1800436fc  mov     [rbp+19E0h+var_1910], rax
0x180043703  lea     rax, aArm64; "ARM64"
0x18004370a  mov     [rbp+19E0h+var_1908], rax
0x180043711  mov     [rbp+19E0h+var_1900], r15b
0x180043718  lea     rax, [rbp+19E0h+var_13C0]
0x18004371f  mov     [rbp+19E0h+var_18F8], rax
0x180043726  mov     eax, 0AA64h
0x18004372b  mov     [rbp+19E0h+var_18F0], ax
0x180043732  lea     rax, [rbp+19E0h+var_1888]
0x180043739  mov     [rbp+19E0h+var_18E8], rax
0x180043740  lea     rax, [rbp+19E0h+var_1508]
0x180043747  mov     [rbp+19E0h+var_18E0], rax
0x18004374e  lea     rax, [rbp+19E0h+var_1738]
0x180043755  mov     [rbp+19E0h+var_18D8], rax
0x18004375c  lea     rax, [rbp+19E0h+var_1690]
0x180043763  mov     [rbp+19E0h+var_18D0], rax
0x18004376a  lea     rax, [rbp+19E0h+var_1770]
0x180043771  mov     [rbp+19E0h+var_18C8], rax
0x180043778  mov     ebx, r15d
0x18004377b  lea     r14d, [r15+1]
0x18004377f  mov     [rbp+19E0h+var_1A20], r15d
0x180043783  lea     rdi, [rbx+rbx*8]
0x180043787  lea     rdx, [rbp+19E0h+var_1A20]
0x18004378b  movzx   ecx, [rbp+rdi*8+19E0h+var_19C8]
0x180043790  call    cs:__imp_GetMachineTypeAttributes
0x180043796  mov     edx, eax; int
0x180043798  lea     rcx, [rsp+1AE0h+var_1A90]; unsigned int *
0x18004379d  call    ?PcaFailedHr@@YA_NAEAKJ@Z; PcaFailedHr(ulong &,long)
0x1800437a2  test    al, al
0x1800437a4  jnz     loc_180044FD0
0x1800437aa  mov     eax, [rbp+19E0h+var_1A20]
0x1800437ad  and     eax, r14d
0x1800437b0  test    al, al
0x1800437b2  jz      short loc_1800437B9
0x1800437b4  mov     [rbp+rdi*8+19E0h+var_19D8], r14b
0x1800437b9  mov     rax, [rbp+rdi*8+19E0h+var_19E0]
0x1800437be  mov     [rsp+1AE0h+phkResult], rax
0x1800437c3  lea     r9, aSacd; "SACD_"
0x1800437ca  lea     r8, aLsLs_0; "%ls%ls"
0x1800437d1  mov     edx, 0Bh; unsigned __int64
0x1800437d6  mov     rcx, [rbp+rdi*8+19E0h+var_19D0]; unsigned __int16 *
0x1800437db  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800437e0  mov     edx, eax; int
0x1800437e2  lea     rcx, [rsp+1AE0h+var_1A90]; unsigned int *
0x1800437e7  call    ?PcaFailedHr@@YA_NAEAKJ@Z; PcaFailedHr(ulong &,long)
0x1800437ec  test    al, al
0x1800437ee  jnz     loc_180044FC1
0x1800437f4  add     rbx, r14
0x1800437f7  cmp     rbx, 4
0x1800437fb  jb      short loc_18004377F
0x1800437fd  xor     edx, edx
0x1800437ff  lea     rcx, [rbp+19E0h+hKey]
0x180043803  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180043808  lea     rax, [rbp+19E0h+hKey]
0x18004380c  mov     [rsp+1AE0h+phkResult], rax; phkResult
0x180043811  mov     r9d, 2001Fh; samDesired
0x180043817  xor     r8d, r8d; ulOptions
0x18004381a  lea     rdx, aSoftwareMicros_23; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180043821  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180043828  call    cs:__imp_RegOpenKeyExW
0x18004382e  mov     ebx, eax
0x180043830  test    eax, eax
0x180043832  jz      short loc_18004384A
0x180043834  mov     dword ptr [rsp+1AE0h+phkResult], eax
0x180043838  lea     r9, aRegopenkeyexwF; "RegOpenKeyExW failed (%d)"
0x18004383f  mov     r8d, 63Bh
0x180043845  jmp     loc_180044FE5
0x18004384a  mov     qword ptr [rbp+19E0h+var_1A08], r15
0x18004384e  lea     r8, [rbp+19E0h+var_1A08]; unsigned __int64 *
0x180043852  mov     edi, 104h
0x180043857  mov     edx, edi; unsigned __int64
0x180043859  lea     rcx, [rbp+19E0h+var_1300]; unsigned __int16 *
0x180043860  call    ?MergeSdbpGetStoreAppInstallDirectory@@YAKPEAG_KPEA_K@Z; MergeSdbpGetStoreAppInstallDirectory(ushort *,unsigned __int64,unsigned __int64 *)
0x180043865  mov     ebx, eax
0x180043867  mov     [rsp+1AE0h+var_1A90], eax
0x18004386b  test    eax, eax
0x18004386d  jz      short loc_180043885
0x18004386f  mov     dword ptr [rsp+1AE0h+phkResult], eax
0x180043873  lea     r9, aMergesdbpgetst_2; "MergeSdbpGetStoreAppInstallDirectory fa"...
0x18004387a  mov     r8d, 647h
0x180043880  jmp     loc_180044FE5
0x180043885  or      r9, 0FFFFFFFFFFFFFFFFh; unsigned __int64
0x180043889  lea     r8, aSav; "SAV"
0x180043890  xor     edx, edx; unsigned __int16 *
0x180043892  mov     rcx, [rbp+19E0h+hKey]; HKEY
0x180043896  call    ?PcaUtilityGetRegistryQWORD@@YA_KPEAUHKEY__@@PEBG1_K@Z; PcaUtilityGetRegistryQWORD(HKEY__ *,ushort const *,ushort const *,unsigned __int64)
0x18004389b  cmp     qword ptr [rbp+19E0h+var_1A08], rax
0x18004389f  jz      loc_180044FBC
0x1800438a5  mov     r13b, r15b
0x1800438a8  mov     r12b, r15b
0x1800438ab  mov     [rsp+1AE0h+var_1A7F], r15b
0x1800438b0  cmp     [rbp+19E0h+var_1300], r15w
0x1800438b8  jnz     loc_180043965
0x1800438be  mov     [rbp+19E0h+var_10F0], r15w
0x1800438c6  mov     [rbp+19E0h+var_CD0], r15w
0x1800438ce  mov     [rsp+1AE0h+var_1A88], r15
0x1800438d3  lea     rcx, [rsp+1AE0h+var_1A88]
0x1800438d8  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$T@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(std::nullptr_t)
0x1800438dd  movdqa  xmmword ptr [rbp+19E0h+var_1A60], xmm6
0x1800438e2  lea     rax, aSatmsi; "SATMSI"
0x1800438e9  mov     [rsp+1AE0h+var_1AA0], rax; unsigned __int16 *
0x1800438ee  lea     rax, aSaidmsi; "SAIDMSI"
0x1800438f5  mov     [rsp+1AE0h+lpValue], rax; lpValue
0x1800438fa  mov     [rsp+1AE0h+var_1AB0], r13b; char
0x1800438ff  lea     rax, [rbp+19E0h+var_1A60]
0x180043903  mov     qword ptr [rsp+1AE0h+cbData], rax; __int64
0x180043908  lea     rax, [rsp+1AE0h+var_1A7D]
0x18004390d  mov     [rsp+1AE0h+phkResult], rax; __int64
0x180043912  lea     r9, [rbp+19E0h+var_1A30]
0x180043916  lea     r8, [rbp+19E0h+Buf1]; Guid
0x18004391d  lea     rdx, [rsp+1AE0h+var_1A88]; unsigned __int16 **
0x180043922  mov     rcx, [rbp+19E0h+hKey]; hkey
0x180043926  call    ?MergeSdbpGetSdbGuidAndTimestampFromRegistry@@YAKPEAUHKEY__@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@AEAU_GUID@@AEA_KAEA_NU4@_NPEBG7@Z; MergeSdbpGetSdbGuidAndTimestampFromRegistry(HKEY__ *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,_GUID &,unsigned __int64 &,bool &,_GUID,bool,ushort const *,ushort const *)
0x18004392b  mov     ebx, eax
0x18004392d  test    eax, eax
0x18004392f  jz      loc_180043B43
0x180043935  mov     dword ptr [rsp+1AE0h+phkResult], eax
0x180043939  lea     r9, aMergesdbpgetsd_0; "MergeSdbpGetSdbGuidAndTimestampFromRegi"...
0x180043940  mov     r8d, 6ACh
0x180043946  lea     rdx, aMergesdbpgathe; "MergeSdbpGatherStoreAppFiles"
0x18004394d  mov     ecx, r14d
0x180043950  call    AslLogCallPrintf
0x180043955  nop
0x180043956  lea     rcx, [rsp+1AE0h+var_1A88]
0x18004395b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180043960  jmp     loc_180044FF5
0x180043965  lea     rax, aApplicationcom; "ApplicationCompatibilityEnhancements.ca"...
0x18004396c  mov     [rsp+1AE0h+phkResult], rax
0x180043971  lea     r9, [rbp+19E0h+var_1300]
0x180043978  lea     r8, aLsLs; "%ls\\%ls"
0x18004397f  mov     rdx, rdi; unsigned __int64
0x180043982  lea     rcx, [rbp+19E0h+pszPath]; unsigned __int16 *
0x180043989  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004398e  mov     edx, eax; int
0x180043990  lea     rcx, [rsp+1AE0h+var_1A90]; unsigned int *
0x180043995  call    ?PcaFailedHr@@YA_NAEAKJ@Z; PcaFailedHr(ulong &,long)
0x18004399a  test    al, al
0x18004399c  jz      short loc_1800439A9
0x18004399e  mov     r8d, 666h
0x1800439a4  jmp     loc_180044FC7
0x1800439a9  lea     rcx, [rbp+19E0h+pszPath]; pszPath
0x1800439b0  call    cs:__imp_PathFileExistsW
0x1800439b6  test    eax, eax
0x1800439b8  jz      loc_180044FBC
0x1800439be  lea     rax, aMsimergeinboxs; "msiMergeInboxStoreApp.sdb"
0x1800439c5  mov     [rsp+1AE0h+phkResult], rax
0x1800439ca  lea     r9, [rbp+19E0h+var_1300]
0x1800439d1  lea     r8, aLsSdbLs; "%ls\\sdb\\%ls"
0x1800439d8  mov     rdx, rdi; unsigned __int64
  ... truncated ...
```
