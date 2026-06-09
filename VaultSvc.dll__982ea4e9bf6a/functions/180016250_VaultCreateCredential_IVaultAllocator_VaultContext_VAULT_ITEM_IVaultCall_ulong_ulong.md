# VaultCreateCredential(IVaultAllocator *,VaultContext *,_VAULT_ITEM *,IVaultCall *,ulong,ulong)

- ea: `0x180016250`
- end: `0x180019d14`
- name: `?VaultCreateCredential@@YAKPEAUIVaultAllocator@@PEAUVaultContext@@PEAU_VAULT_ITEM@@PEAUIVaultCall@@KK@Z`
- size: `15044`
- prototype: `__int64 __fastcall(struct IVaultAllocator *, CUserVault **, struct _VAULT_ITEM *, struct IVaultCall *, __int16)`
- caller_count: `1`
- callee_count: `31`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180015e30`

## callees

- `0x1800010b4`
- `0x180003140`
- `0x180009020`
- `0x1800091d0`
- `0x18000aac0`
- `0x180012210`
- `0x180016250`
- `0x180020c80`
- `0x180021b70`
- `0x180027340`
- `0x180028760`
- `0x18002a4a0`
- `0x18002b890`
- `0x18002c2c0`
- `0x18002d410`
- `0x18002d724`
- `0x18002e710`
- `0x18002ea00`
- `0x1800303fc`
- `0x180032558`
- `0x180033d1c`
- `0x18003a580`
- `0x18003b4bc`
- `0x18003b7b0`
- `0x18003b7d8`
- `0x18003be38`
- `0x18003cb08`
- `0x18003d780`
- `0x1800493d4`
- `0x18004ac48`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800163ce`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800164e0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016560`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800165f0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016740`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800167c0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016850`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800169a0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016a20`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016ab0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016b20`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016ba0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016c70`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016cf0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016d80`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016df0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016e70`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800164e0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016560`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800165f0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016740`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800167c0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016850`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800169a0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016a20`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016ab0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016b20`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016ba0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016c70`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016cf0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016d80`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016df0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016e70`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180017585`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180017585`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x1800164bf`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18001653d`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x1800165ce`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18001665b`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18001671f`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18001679d`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18001682e`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x1800168bb`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180016982`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x1800169fc`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180016a89`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180016b01`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180016b7d`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180016c52`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180016ccc`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180016d59`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180016dd1`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180016e4d`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x1800164bf`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18001653d`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x1800165ce`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18001665b`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18001671f`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18001679d`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18001682e`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x1800168bb`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180016982`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x1800169fc`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180016a89`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180016b01`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180016b7d`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180016c52`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180016ccc`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180016d59`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180016dd1`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180016e4d`
- `LSASRV!LsaILookupUserAccountType` at `0x1800196cf`
- `LSASRV!LsaILookupUserAccountType` at `0x1800196cf`
- `ntdll!RtlPublishWnfStateData` at `0x180019b4f`
- `ntdll!RtlPublishWnfStateData` at `0x180019b4f`
- `ntdll!NtClose` at `0x18001970e`
- `ntdll!NtClose` at `0x18001970e`
- `ntdll!NtQueryInformationToken` at `0x18001782e`
- `ntdll!NtQueryInformationToken` at `0x180019698`
- `ntdll!NtQueryInformationToken` at `0x18001782e`
- `ntdll!NtQueryInformationToken` at `0x180019698`
- `ntdll!NtOpenThreadToken` at `0x1800176f1`
- `ntdll!NtOpenThreadToken` at `0x18001962f`
- `ntdll!NtOpenThreadToken` at `0x1800176f1`
- `ntdll!NtOpenThreadToken` at `0x18001962f`
- `ntdll!RtlNtStatusToDosError` at `0x180017731`
- `ntdll!RtlNtStatusToDosError` at `0x180017871`
- `ntdll!RtlNtStatusToDosError` at `0x18001971e`
- `ntdll!RtlNtStatusToDosError` at `0x180017731`
- `ntdll!RtlNtStatusToDosError` at `0x180017871`
- `ntdll!RtlNtStatusToDosError` at `0x18001971e`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall VaultCreateCredential(
        struct IVaultAllocator *a1,
        CUserVault **a2,
        struct _VAULT_ITEM *a3,
        struct IVaultCall *a4,
        __int16 a5)
{
  unsigned int v7; // r12d
  unsigned int v8; // ecx
  unsigned int v9; // esi
  _QWORD *v10; // rax
  CUserVault *v11; // r14
  _BYTE *v12; // r15
  void (__fastcall *v13)(HLOCAL); // r13
  _BYTE *v14; // rbx
  __int64 v15; // rax
  SIZE_T v16; // rax
  _BYTE *v17; // rcx
  _BYTE *v18; // rbx
  __int64 v19; // rax
  __int64 (__fastcall *v20)(); // rax
  SIZE_T v21; // rax
  _BYTE *v22; // rcx
  unsigned int v23; // eax
  _BYTE *v24; // rbx
  __int64 v25; // rax
  SIZE_T v26; // rax
  _BYTE *v27; // rcx
  __int64 v28; // rax
  SIZE_T v29; // rax
  _BYTE *v30; // rcx
  unsigned int VaultStore; // eax
  struct _GUID *v32; // rdx
  _BYTE *v33; // rbx
  __int64 v34; // rax
  SIZE_T v35; // rax
  _BYTE *v36; // rcx
  _BYTE *v37; // rbx
  __int64 v38; // rax
  SIZE_T v39; // rax
  _BYTE *v40; // rcx
  HLOCAL v41; // rbx
  __int64 v42; // rcx
  _BYTE *v43; // rax
  SIZE_T v44; // rax
  _BYTE *v45; // rdx
  _BYTE *v46; // rbx
  __int64 v47; // rax
  SIZE_T v48; // rax
  _BYTE *v49; // rcx
  _BYTE *v50; // rbx
  __int64 v51; // rax
  SIZE_T v52; // rax
  _BYTE *v53; // rcx
  _BYTE *v55; // rbx
  __int64 v56; // rax
  SIZE_T v57; // rax
  _BYTE *v58; // rcx
  _BYTE *v59; // rbx
  __int64 v60; // rax
  SIZE_T v61; // rax
  _BYTE *v62; // rcx
  HLOCAL v63; // rbx
  __int64 v64; // rcx
  _BYTE *v65; // rax
  SIZE_T v66; // rax
  _BYTE *v67; // rdx
  _BYTE *v68; // rbx
  __int64 v69; // rax
  SIZE_T v70; // rax
  _BYTE *v71; // rcx
  __int64 v72; // rax
  SIZE_T v73; // rax
  _BYTE *v74; // rcx
  _BYTE *v75; // r14
  __int64 v76; // rcx
  _BYTE *v77; // rax
  _BYTE *v78; // rcx
  __int64 v79; // rax
  unsigned int v80; // ebx
  __int64 v81; // rcx
  _BYTE *v82; // rax
  _BYTE *v83; // rcx
  __int64 v84; // rax
  ULONG Schema; // ebx
  __int64 v86; // rcx
  _BYTE *v87; // rax
  _BYTE *v88; // rcx
  __int64 v89; // rax
  __int64 v90; // rax
  __int64 v91; // rcx
  _BYTE *v92; // rax
  _BYTE *v93; // rcx
  __int64 v94; // rax
  ULONG v95; // eax
  __int64 v96; // rcx
  _BYTE *v97; // rax
  _BYTE *v98; // rcx
  __int64 v99; // rax
  ULONG v100; // eax
  __int64 v101; // rcx
  _BYTE *v102; // rax
  _BYTE *v103; // rcx
  __int64 v104; // rax
  struct _VAULT_ITEM_ELEMENT *v105; // rcx
  __int64 v106; // rcx
  _BYTE *v107; // rax
  _BYTE *v108; // rcx
  __int64 v109; // rax
  __int64 v110; // rax
  void (__fastcall ***v111)(_QWORD); // rbx
  int v112; // ebx
  __int64 v113; // rcx
  _BYTE *v114; // rax
  _BYTE *v115; // rcx
  __int64 v116; // rax
  NTSTATUS v117; // eax
  unsigned int v118; // r9d
  NTSTATUS v119; // ebx
  __int64 v120; // rcx
  _BYTE *v121; // rax
  _BYTE *v122; // rcx
  __int64 v123; // rax
  __int64 v124; // rcx
  _BYTE *v125; // rax
  _BYTE *v126; // rcx
  __int64 v127; // rax
  unsigned int v128; // ebx
  __int64 v129; // rcx
  _BYTE *v130; // rax
  _BYTE *v131; // rcx
  __int64 v132; // rax
  __int64 v133; // rcx
  _BYTE *v134; // rax
  _BYTE *v135; // rcx
  __int64 v136; // rax
  CUserVault *v137; // rsi
  unsigned int v138; // ebx
  __int64 v139; // rcx
  _BYTE *v140; // rax
  _BYTE *v141; // rcx
  __int64 v142; // rax
  unsigned int v143; // eax
  __int64 v144; // rcx
  _BYTE *v145; // rax
  _BYTE *v146; // rcx
  __int64 v147; // rax
  __int64 v148; // rax
  struct _VAULT_ITEM_ELEMENT *v149; // rbx
  __int64 v150; // rcx
  _BYTE *v151; // rax
  __int64 v152; // rdx
  __int64 v153; // rcx
  _BYTE *v154; // rax
  _BYTE *v155; // rcx
  __int64 v156; // rax
  __int64 v157; // rcx
  _BYTE *v158; // rax
  _BYTE *v159; // rcx
  __int64 v160; // rax
  unsigned int v161; // eax
  __int64 v162; // rcx
  _BYTE *v163; // rax
  _BYTE *v164; // rcx
  __int64 v165; // rax
  _BYTE *v166; // rcx
  __int64 v167; // rax
  __int64 v168; // rcx
  _BYTE *v169; // rax
  _BYTE *v170; // rcx
  __int64 v171; // rax
  __int64 v172; // rax
  __int64 v173; // rdx
  HLOCAL v174; // rcx
  _BYTE *v175; // rax
  __int64 v176; // rcx
  _BYTE *v177; // rax
  _BYTE *v178; // rcx
  __int64 v179; // rax
  struct _GUID *v180; // rdx
  __int64 v181; // rcx
  _BYTE *v182; // rax
  __int64 v183; // rcx
  _BYTE *v184; // rax
  _BYTE *v185; // rcx
  __int64 v186; // rax
  unsigned int v187; // eax
  __int64 v188; // rcx
  _BYTE *v189; // rax
  __int64 v190; // rcx
  _BYTE *v191; // rax
  _BYTE *v192; // rcx
  __int64 v193; // rax
  __int64 v194; // rcx
  _BYTE *v195; // rax
  __int64 v196; // rcx
  _BYTE *v197; // rax
  _BYTE *v198; // rcx
  __int64 v199; // rax
  unsigned int v200; // esi
  __int64 v201; // rbx
  unsigned int v202; // eax
  int v203; // r8d
  struct _GUID *v204; // rdx
  unsigned int v205; // eax
  int v206; // ebx
  unsigned int v207; // ebx
  CUserVault *v208; // rsi
  unsigned int v209; // eax
  struct _GUID *v210; // rdx
  __int64 v211; // rcx
  _BYTE *v212; // rax
  __int64 v213; // rcx
  _BYTE *v214; // rax
  __int64 v215; // rcx
  _BYTE *v216; // rax
  _BYTE *v217; // rcx
  __int64 v218; // rax
  __int64 v219; // rcx
  _BYTE *v220; // rax
  __int64 v221; // rcx
  _BYTE *v222; // rax
  _BYTE *v223; // rcx
  __int64 v224; // rax
  __int64 v225; // rcx
  _BYTE *v226; // rax
  _BYTE *v227; // rcx
  __int64 v228; // rax
  unsigned int v229; // ebx
  __int64 v230; // rcx
  _BYTE *v231; // rax
  __int64 v232; // rdx
  HLOCAL v233; // rcx
  _BYTE *v234; // rax
  ULONG v235; // ebx
  __int64 v236; // rcx
  _BYTE *v237; // rax
  HLOCAL v238; // rcx
  __int64 v239; // rcx
  _BYTE *v240; // rax
  CVaultPackageId *v241; // rax
  CVaultPackageId *v242; // rsi
  __int64 v243; // rbx
  __int64 v244; // rdi
  __int64 v245; // rax
  __int64 v246; // rcx
  _BYTE *v247; // rax
  __int64 v248; // rcx
  _BYTE *v249; // rax
  NTSTATUS v250; // eax
  struct _GUID *v251; // rdx
  NTSTATUS v252; // ebx
  _QWORD *v253; // rcx
  __int64 v254; // rdx
  ULONG v255; // eax
  __int64 v256; // rcx
  _BYTE *v257; // rax
  __int64 v258; // rcx
  _BYTE *v259; // rax
  __int64 v260; // rcx
  _BYTE *v261; // rax
  ULONG v262; // eax
  unsigned int v263; // r8d
  __int64 v264; // rcx
  _BYTE *v265; // rax
  int v266; // ecx
  int v267; // r8d
  int v268; // r9d
  int v269; // r8d
  int v270; // r9d
  unsigned __int16 *v271; // rax
  __int64 v272; // rcx
  _BYTE *v273; // rax
  int ReturnLength; // [rsp+20h] [rbp-E0h]
  char v275[8]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 (__fastcall *v276)(); // [rsp+48h] [rbp-B8h] BYREF
  HLOCAL v277; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v278; // [rsp+58h] [rbp-A8h]
  __int64 (__fastcall *v279)(); // [rsp+60h] [rbp-A0h] BYREF
  HLOCAL v280; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v281; // [rsp+70h] [rbp-90h]
  __int64 (__fastcall *v282)(); // [rsp+78h] [rbp-88h] BYREF
  HLOCAL v283; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v284; // [rsp+88h] [rbp-78h]
  __int64 (__fastcall *v285)(); // [rsp+90h] [rbp-70h] BYREF
  HLOCAL hMem; // [rsp+98h] [rbp-68h] BYREF
  unsigned int v287; // [rsp+A0h] [rbp-60h]
  BOOL (__stdcall *v288)(HANDLE); // [rsp+A8h] [rbp-58h] BYREF
  HLOCAL TokenHandle; // [rsp+B0h] [rbp-50h] BYREF
  unsigned int v290; // [rsp+B8h] [rbp-48h]
  unsigned int v291; // [rsp+C0h] [rbp-40h] BYREF
  unsigned int v292; // [rsp+C4h] [rbp-3Ch]
  unsigned int v293; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v294; // [rsp+D0h] [rbp-30h]
  _DWORD v295[2]; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v296; // [rsp+E0h] [rbp-20h]
  int v297; // [rsp+E8h] [rbp-18h]
  int v298; // [rsp+ECh] [rbp-14h]
  int v299; // [rsp+F0h] [rbp-10h]
  __int128 v300; // [rsp+F8h] [rbp-8h]
  int v301; // [rsp+108h] [rbp+8h] BYREF
  CUserVault *v302; // [rsp+110h] [rbp+10h]
  ULONG v303; // [rsp+118h] [rbp+18h] BYREF
  int TokenInformation; // [rsp+11Ch] [rbp+1Ch] BYREF
  unsigned int v305; // [rsp+120h] [rbp+20h] BYREF
  unsigned int v306; // [rsp+124h] [rbp+24h] BYREF
  void (__fastcall *v307)(HLOCAL, __int64); // [rsp+128h] [rbp+28h] BYREF
  HLOCAL v308; // [rsp+130h] [rbp+30h] BYREF
  unsigned int v309; // [rsp+138h] [rbp+38h]
  ULONG v310; // [rsp+140h] [rbp+40h] BYREF
  HANDLE Handle; // [rsp+148h] [rbp+48h] BYREF
  struct _VAULT_ITEM *AccountTypeString; // [rsp+150h] [rbp+50h] BYREF
  _QWORD v313[2]; // [rsp+158h] [rbp+58h] BYREF
  int v314; // [rsp+168h] [rbp+68h]
  __int128 v315; // [rsp+170h] [rbp+70h] BYREF
  CVaultPackageId *v316; // [rsp+180h] [rbp+80h]
  void (__fastcall *v317)(HLOCAL); // [rsp+190h] [rbp+90h]
  HLOCAL v318; // [rsp+198h] [rbp+98h] BYREF
  unsigned int v319; // [rsp+1A0h] [rbp+A0h]
  __int64 v320; // [rsp+1A8h] [rbp+A8h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+1B0h] [rbp+B0h] BYREF
  __int64 v322; // [rsp+1B8h] [rbp+B8h] BYREF
  __int64 (__fastcall *v323)(); // [rsp+1C0h] [rbp+C0h] BYREF
  __int64 v324; // [rsp+1C8h] [rbp+C8h] BYREF
  int v325; // [rsp+1D0h] [rbp+D0h]
  __int128 v326; // [rsp+1D8h] [rbp+D8h] BYREF
  __int64 v327; // [rsp+1E8h] [rbp+E8h] BYREF
  unsigned __int16 *v328; // [rsp+1F0h] [rbp+F0h] BYREF
  wchar_t *v329; // [rsp+1F8h] [rbp+F8h] BYREF
  __int128 v330; // [rsp+200h] [rbp+100h] BYREF
  _OWORD v331[5]; // [rsp+210h] [rbp+110h] BYREF
  __int64 v332; // [rsp+260h] [rbp+160h]
  __int128 v333; // [rsp+270h] [rbp+170h] BYREF
  char v334[48]; // [rsp+280h] [rbp+180h] BYREF
  _BYTE v335[96]; // [rsp+2B0h] [rbp+1B0h] BYREF
  unsigned __int16 v336[256]; // [rsp+310h] [rbp+210h] BYREF
  wchar_t Filename[256]; // [rsp+510h] [rbp+410h] BYREF

  AccountTypeString = a3;
  v7 = 0;
  v8 = (*((_QWORD *)a3 + 3) != 0) + 2;
  v9 = v8 + *((_DWORD *)a3 + 17);
  if ( v9 < v8 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids);
    v9 = 2;
  }
  v282 = AutoDereference<IVaultKeyManager>;
  v283 = 0;
  v284 = 0;
  v276 = AutoDereference<IVaultKeyManager>;
  v277 = 0;
  v278 = 0;
  v279 = AutoDereference<IVaultKeyManager>;
  v280 = 0;
  v281 = 0;
  v308 = 0;
  v309 = 0;
  v307 = 0;
  v322 = 0;
  v305 = 0;
  v306 = 0;
  v300 = 0;
  v10 = operator new(0x38u);
  *v10 = v10;
  v10[1] = v10;
  v10[2] = v10;
  *((_WORD *)v10 + 12) = 257;
  *(_QWORD *)&v300 = v10;
  v295[0] = v9;
  v295[1] = 0;
  v296 = 0;
  v297 = 0;
  v298 = 1;
  v299 = 1;
  v320 = 0;
  v275[0] = 0;
  v326 = 0;
  v330 = 0;
  v315 = 0;
  v11 = *a2;
  v302 = *a2;
  v313[1] = 0;
  v314 = 0;
  v313[0] = 0;
  SystemTimeAsFileTime = 0;
  hMem = 0;
  v287 = 0;
  v285 = AutoDereference<IVaultKeyManager>;
  v293 = *((unsigned __int8 *)a2 + 85);
  v288 = CloseHandle;
  TokenHandle = 0;
  v290 = 0;
  TokenInformation = 0;
  v301 = 0;
  v303 = 0;
  v12 = 0;
  v318 = 0;
  v319 = 0;
  v13 = DeleteCredentialElement;
  v317 = DeleteCredentialElement;
  v291 = 0;
  Filename[0] = 0;
  v336[0] = 0;
  if ( !*((_QWORD *)a3 + 4) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids);
    v290 = 0;
    v287 = 0;
    CVaultCredDataMap::~CVaultCredDataMap((CVaultCredDataMap *)v295);
    v14 = v277;
    if ( v277 )
    {
      v15 = v278;
      if ( v278 )
      {
        do
        {
          *v14++ = 0;
          --v15;
        }
        while ( v15 );
        v14 = v277;
      }
      if ( v276 )
      {
        ((void (__fastcall *)(_BYTE *))v276)(v14);
      }
      else if ( v14 )
      {
        v16 = LocalSize(v14);
        if ( v16 )
        {
          v17 = v14;
          do
          {
            *v17++ = 0;
            --v16;
          }
          while ( v16 );
        }
        LocalFree(v14);
      }
      v277 = 0;
    }
    v278 = 0;
    v18 = v283;
    if ( !v283 )
      return 87;
    v19 = v284;
    if ( v284 )
    {
      do
      {
        *v18++ = 0;
        --v19;
      }
      while ( v19 );
      v18 = v283;
    }
    v20 = v282;
    if ( !v282 )
    {
      if ( v18 )
      {
        v21 = LocalSize(v18);
        if ( v21 )
        {
          v22 = v18;
          do
          {
            *v22++ = 0;
            --v21;
          }
          while ( v21 );
        }
LABEL_183:
        LocalFree(v18);
        return 87;
      }
      return 87;
    }
    goto LABEL_178;
  }
  v23 = *((_DWORD *)a3 + 16);
  if ( (v23 & 0xFFFF0300) != 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids, v23, 64767);
    v290 = 0;
    v287 = 0;
    CVaultCredDataMap::~CVaultCredDataMap((CVaultCredDataMap *)v295);
    v24 = v277;
    if ( v277 )
    {
      v25 = v278;
      if ( v278 )
      {
        do
        {
          *v24++ = 0;
          --v25;
        }
        while ( v25 );
        v24 = v277;
      }
      if ( v276 )
      {
        ((void (__fastcall *)(_BYTE *))v276)(v24);
      }
      else if ( v24 )
      {
        v26 = LocalSize(v24);
        if ( v26 )
        {
          v27 = v24;
          do
          {
            *v27++ = 0;
            --v26;
          }
          while ( v26 );
        }
        LocalFree(v24);
      }
      v277 = 0;
    }
    v278 = 0;
    v18 = v283;
    if ( !v283 )
      return 87;
    v28 = v284;
    if ( v284 )
    {
      do
      {
        *v18++ = 0;
        --v28;
      }
      while ( v28 );
      v18 = v283;
    }
    v20 = v282;
    if ( !v282 )
    {
      if ( v18 )
      {
        v29 = LocalSize(v18);
        if ( v29 )
        {
          v30 = v18;
          do
          {
            *v30++ = 0;
            --v29;
          }
          while ( v29 );
        }
        goto LABEL_183;
      }
      return 87;
    }
LABEL_178:
    ((void (__fastcall *)(_BYTE *))v20)(v18);
    return 87;
  }
  *((_DWORD *)a3 + 16) = v23 & 0xFFFFFBFF;
  VaultStore = CUserVault::GetVaultStore(v11, (struct IVaultStore **)&v280, 0);
  v292 = VaultStore;
  if ( VaultStore )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids, VaultStore);
    v33 = TokenHandle;
    if ( TokenHandle )
    {
      v34 = v290;
      if ( v290 )
      {
        do
        {
          *v33++ = 0;
          --v34;
        }
        while ( v34 );
        v33 = TokenHandle;
      }
      if ( v288 )
      {
        ((void (__fastcall *)(_BYTE *))v288)(v33);
        TokenHandle = 0;
      }
      else
      {
        if ( v33 )
        {
          v35 = LocalSize(v33);
          if ( v35 )
          {
            v36 = v33;
            do
            {
              *v36++ = 0;
              --v35;
            }
            while ( v35 );
          }
          LocalFree(v33);
        }
        TokenHandle = 0;
      }
    }
    v290 = 0;
    v37 = hMem;
    if ( hMem )
    {
      v38 = v287;
      if ( v287 )
      {
        do
        {
          *v37++ = 0;
          --v38;
        }
        while ( v38 );
        v37 = hMem;
      }
      if ( v285 )
      {
        ((void (__fastcall *)(_BYTE *))v285)(v37);
      }
      else if ( v37 )
      {
        v39 = LocalSize(v37);
        if ( v39 )
        {
          v40 = v37;
          do
          {
            *v40++ = 0;
            --v39;
          }
          while ( v39 );
        }
        LocalFree(v37);
      }
      hMem = 0;
    }
    v287 = 0;
    CVaultCredDataMap::~CVaultCredDataMap((CVaultCredDataMap *)v295);
    v41 = v280;
    if ( v280 )
    {
      if ( v281 )
      {
        v42 = v281;
        v43 = v280;
        do
        {
          *v43++ = 0;
          --v42;
        }
        while ( v42 );
      }
      if ( v279 )
      {
        ((void (__fastcall *)(HLOCAL))v279)(v41);
      }
      else if ( v41 )
      {
        v44 = LocalSize(v41);
        if ( v44 )
        {
          v45 = v41;
          do
          {
            *v45++ = 0;
            --v44;
          }
          while ( v44 );
        }
        LocalFree(v41);
      }
    }
    v46 = v277;
    if ( v277 )
    {
      v47 = v278;
      if ( v278 )
      {
        do
        {
          *v46++ = 0;
          --v47;
        }
        while ( v47 );
        v46 = v277;
      }
      if ( v276 )
      {
        ((void (__fastcall *)(_BYTE *))v276)(v46);
      }
      else if ( v46 )
      {
        v48 = LocalSize(v46);
        if ( v48 )
        {
          v49 = v46;
          do
          {
            *v49++ = 0;
            --v48;
          }
          while ( v48 );
        }
        LocalFree(v46);
      }
      v277 = 0;
    }
    v278 = 0;
    v50 = v283;
    if ( v283 )
    {
      v51 = v284;
      if ( v284 )
      {
        do
        {
          *v50++ = 0;
          --v51;
        }
        while ( v51 );
        v50 = v283;
      }
      if ( v282 )
      {
        ((void (__fastcall *)(_BYTE *))v282)(v50);
      }
      else if ( v50 )
      {
        v52 = LocalSize(v50);
        if ( v52 )
        {
          v53 = v50;
          do
          {
            *v53++ = 0;
            --v52;
          }
          while ( v52 );
        }
        LocalFree(v50);
      }
    }
    return v292;
  }
  if ( CUserVault::IsCredmanVault(v11, v32) && *((_QWORD *)a3 + 6) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids, 87);
    v55 = TokenHandle;
    if ( TokenHandle )
    {
      v56 = v290;
      if ( v290 )
      {
        do
        {
          *v55++ = 0;
          --v56;
        }
        while ( v56 );
        v55 = TokenHandle;
      }
      if ( v288 )
      {
        ((void (__fastcall *)(_BYTE *))v288)(v55);
        TokenHandle = 0;
      }
      else
      {
        if ( v55 )
        {
          v57 = LocalSize(v55);
          if ( v57 )
          {
            v58 = v55;
            do
            {
              *v58++ = 0;
              --v57;
            }
            while ( v57 );
          }
          LocalFree(v55);
        }
        TokenHandle = 0;
      }
    }
    v290 = 0;
    v59 = hMem;
    if ( hMem )
    {
      v60 = v287;
      if ( v287 )
      {
        do
        {
          *v59++ = 0;
          --v60;
        }
        while ( v60 );
        v59 = hMem;
      }
      if ( v285 )
      {
        ((void (__fastcall *)(_BYTE *))v285)(v59);
      }
      else if ( v59 )
      {
        v61 = LocalSize(v59);
        if ( v61 )
        {
          v62 = v59;
          do
          {
            *v62++ = 0;
            --v61;
          }
          while ( v61 );
        }
        LocalFree(v59);
      }
      hMem = 0;
    }
    v287 = 0;
    CVaultCredDataMap::~CVaultCredDataMap((CVaultCredDataMap *)v295);
    v63 = v280;
    if ( v280 )
    {
      if ( v281 )
      {
        v64 = v281;
        v65 = v280;
        do
        {
          *v65++ = 0;
          --v64;
        }
        while ( v64 );
      }
      if ( v279 )
      {
        ((void (__fastcall *)(HLOCAL))v279)(v63);
      }
      else if ( v63 )
      {
        v66 = LocalSize(v63);
        if ( v66 )
        {
          v67 = v63;
          do
          {
            *v67++ = 0;
            --v66;
          }
          while ( v66 );
        }
        LocalFree(v63);
      }
    }
    v68 = v277;
    if ( v277 )
    {
      v69 = v278;
      if ( v278 )
      {
        do
        {
          *v68++ = 0;
          --v69;
        }
        while ( v69 );
        v68 = v277;
      }
      if ( v276 )
      {
        ((void (__fastcall *)(_BYTE *))v276)(v68);
      }
      else if ( v68 )
      {
        v70 = LocalSize(v68);
        if ( v70 )
        {
          v71 = v68;
          do
          {
            *v71++ = 0;
            --v70;
          }
          while ( v70 );
        }
        LocalFree(v68);
      }
      v277 = 0;
    }
    v278 = 0;
    v18 = v283;
    if ( !v283 )
      return 87;
    v72 = v284;
    if ( v284 )
    {
      do
      {
        *v18++ = 0;
        --v72;
      }
      while ( v72 );
      v18 = v283;
    }
    v20 = v282;
    if ( !v282 )
    {
      if ( v18 )
      {
        v73 = LocalSize(v18);
        if ( v73 )
        {
          v74 = v18;
          do
          {
            *v74++ = 0;
            --v73;
          }
          while ( v73 );
        }
        goto LABEL_183;
      }
      return 87;
    }
    goto LABEL_178;
  }
  v75 = v280;
  if ( (*((_BYTE *)a3 + 64) & 0x40) != 0 )
  {
    if ( (*(unsigned int (__fastcall **)(HLOCAL, __int64))(*(_QWORD *)v280 + 136LL))(v280, 1) + 1 > 0x2000 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids, 0x2000);
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v288);
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v285);
      CVaultCredDataMap::~CVaultCredDataMap((CVaultCredDataMap *)v295);
      if ( v75 )
      {
        v76 = v281;
        if ( v281 )
        {
          v77 = v75;
          do
          {
            *v77++ = 0;
            --v76;
          }
          while ( v76 );
        }
        if ( v279 )
          ((void (__fastcall *)(_BYTE *))v279)(v75);
        else
          VaultFreeInternal(v75);
      }
      v78 = v277;
      if ( v277 )
      {
        v79 = v278;
        if ( v278 )
        {
          do
          {
            *v78++ = 0;
            --v79;
          }
          while ( v79 );
          v78 = v277;
        }
        if ( v276 )
          v276();
        else
          VaultFreeInternal(v78);
        v277 = 0;
      }
LABEL_205:
      v278 = 0;
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v282);
      return 1381;
    }
  }
  else
  {
    v80 = dword_18005F628;
    if ( dword_18005F628
      && (*(unsigned int (__fastcall **)(HLOCAL, _QWORD))(*(_QWORD *)v280 + 136LL))(v280, 0) + 1 > v80 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          38,
          WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids,
          (unsigned int)dword_18005F628);
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v288);
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v285);
      CVaultCredDataMap::~CVaultCredDataMap((CVaultCredDataMap *)v295);
      if ( v75 )
      {
        v81 = v281;
        if ( v281 )
        {
          v82 = v75;
          do
          {
            *v82++ = 0;
            --v81;
          }
          while ( v81 );
        }
        if ( v279 )
          ((void (__fastcall *)(_BYTE *))v279)(v75);
        else
          VaultFreeInternal(v75);
      }
      v83 = v277;
      if ( v277 )
      {
        v84 = v278;
        if ( v278 )
        {
          do
          {
            *v83++ = 0;
            --v84;
          }
          while ( v84 );
          v83 = v277;
        }
        if ( v276 )
          v276();
        else
          VaultFreeInternal(v83);
        v277 = 0;
      }
      goto LABEL_205;
    }
  }
  (*(void (__fastcall **)(_BYTE *, __int64 *))(*(_QWORD *)v75 + 72LL))(v75, &v320);
  Schema = VaultGetSchema(v302, (const struct _GUID *)a3, (struct IVaultSchema **)&v277, 1u);
  if ( Schema )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF__guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids, a3);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v288);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v285);
    CVaultCredDataMap::~CVaultCredDataMap((CVaultCredDataMap *)v295);
    if ( v75 )
    {
      v86 = v281;
      if ( v281 )
      {
        v87 = v75;
        do
        {
          *v87++ = 0;
          --v86;
        }
        while ( v86 );
      }
      if ( v279 )
        ((void (__fastcall *)(_BYTE *))v279)(v75);
      else
        VaultFreeInternal(v75);
    }
    v88 = v277;
    if ( v277 )
    {
      v89 = v278;
      if ( v278 )
      {
        do
        {
          *v88++ = 0;
          --v89;
        }
        while ( v89 );
        v88 = v277;
      }
      if ( v276 )
        v276();
      else
        VaultFreeInternal(v88);
      v277 = 0;
    }
LABEL_431:
    v278 = 0;
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v282);
    return Schema;
  }
  v90 = (*(__int64 (__fastcall **)(HLOCAL))(*(_QWORD *)v277 + 160LL))(v277);
  if ( !(unsigned int)VaultAccessCheck(1, v90, &v293) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids, 1168);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v288);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v285);
    CVaultCredDataMap::~CVaultCredDataMap((CVaultCredDataMap *)v295);
    if ( v75 )
    {
      v91 = v281;
      if ( v281 )
      {
        v92 = v75;
        do
        {
          *v92++ = 0;
          --v91;
        }
        while ( v91 );
      }
      if ( v279 )
        ((void (__fastcall *)(_BYTE *))v279)(v75);
      else
        VaultFreeInternal(v75);
    }
    v93 = v277;
    if ( v277 )
    {
      v94 = v278;
      if ( v278 )
      {
        do
        {
          *v93++ = 0;
          --v94;
        }
        while ( v94 );
        v93 = v277;
      }
      if ( v276 )
        v276();
      else
        VaultFreeInternal(v93);
      v277 = 0;
    }
    v278 = 0;
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v282);
    return 1168;
  }
  v95 = (*(__int64 (__fastcall **)(__int64, HLOCAL, _QWORD, _QWORD, HLOCAL *))(*(_QWORD *)v320 + 16LL))(
          v320,
          v277,
          v9,
          0,
          &v283);
  Schema = v95;
  if ( v95 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids, v95);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v288);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v285);
    CVaultCredDataMap::~CVaultCredDataMap((CVaultCredDataMap *)v295);
    if ( v75 )
    {
      if ( v281 )
      {
        v96 = v281;
        v97 = v75;
        do
        {
          *v97++ = 0;
          --v96;
        }
        while ( v96 );
      }
      if ( v279 )
        ((void (__fastcall *)(_BYTE *))v279)(v75);
      else
        VaultFreeInternal(v75);
    }
    v98 = v277;
    if ( v277 )
    {
      v99 = v278;
      if ( v278 )
      {
        do
        {
          *v98++ = 0;
          --v99;
        }
        while ( v99 );
        v98 = v277;
      }
      if ( v276 )
        v276();
      else
        VaultFreeInternal(v98);
      v277 = 0;
    }
    goto LABEL_431;
  }
  v100 = (*(__int64 (__fastcall **)(HLOCAL, _QWORD))(*(_QWORD *)v283 + 32LL))(v283, *((_QWORD *)a3 + 2));
  Schema = v100;
  if ( v100 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids, v100);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v288);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v285);
    CVaultCredDataMap::~CVaultCredDataMap((CVaultCredDataMap *)v295);
    if ( v75 )
    {
      if ( v281 )
      {
        v101 = v281;
        v102 = v75;
        do
        {
          *v102++ = 0;
          --v101;
        }
        while ( v101 );
      }
      if ( v279 )
        ((void (__fastcall *)(_BYTE *))v279)(v75);
      else
        VaultFreeInternal(v75);
    }
    v103 = v277;
    if ( v277 )
    {
      v104 = v278;
      if ( v278 )
      {
        do
        {
          *v103++ = 0;
          --v104;
        }
        while ( v104 );
        v103 = v277;
      }
      if ( v276 )
        v276();
      else
        VaultFreeInternal(v103);
      v277 = 0;
    }
    goto LABEL_431;
  }
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  (*(void (__fastcall **)(HLOCAL, struct _FILETIME))(*(_QWORD *)v283 + 200LL))(v283, SystemTimeAsFileTime);
  v105 = (struct _VAULT_ITEM_ELEMENT *)*((_QWORD *)a3 + 6);
  if ( v105 )
  {
    Schema = ValidateAndGetItemPackageSid(v105, (struct IVaultCredential *)v283, (struct CVaultSid **)&hMem);
    if ( Schema )
    {
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v288);
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v285);
      CVaultCredDataMap::~CVaultCredDataMap((CVaultCredDataMap *)v295);
      if ( v75 )
      {
        if ( v281 )
        {
          v106 = v281;
          v107 = v75;
          do
          {
            *v107++ = 0;
            --v106;
          }
          while ( v106 );
        }
        if ( v279 )
          ((void (__fastcall *)(_BYTE *))v279)(v75);
        else
          VaultFreeInternal(v75);
      }
      v108 = v277;
      if ( v277 )
      {
        v109 = v278;
        if ( v278 )
        {
          do
          {
            *v108++ = 0;
            --v109;
          }
          while ( v109 );
          v108 = v277;
        }
        if ( v276 )
          v276();
        else
          VaultFreeInternal(v108);
        v277 = 0;
      }
      goto LABEL_431;
    }
  }
  else
  {
    v110 = (*(__int64 (__fastcall **)(HLOCAL))(*(_QWORD *)v283 + 208LL))(v283);
    v111 = (void (__fastcall ***)(_QWORD))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v110 + 32LL))(v110);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v285);
    hMem = v111;
    (**v111)(v111);
  }
  v112 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 1u, &TokenHandle);
  if ( v112 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids);
    Schema = RtlNtStatusToDosError(v112);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v288);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v285);
    CVaultCredDataMap::~CVaultCredDataMap((CVaultCredDataMap *)v295);
    if ( v75 )
    {
      if ( v281 )
      {
        v113 = v281;
        v114 = v75;
        do
        {
          *v114++ = 0;
          --v113;
        }
        while ( v113 );
      }
      if ( v279 )
        ((void (__fastcall *)(_BYTE *))v279)(v75);
      else
        VaultFreeInternal(v75);
    }
    v115 = v277;
    if ( v277 )
    {
      v116 = v278;
      if ( v278 )
      {
        do
        {
          *v115++ = 0;
          --v116;
        }
        while ( v116 );
        v115 = v277;
      }
      if ( v276 )
        v276();
      else
        VaultFreeInternal(v115);
      v277 = 0;
    }
    goto LABEL_431;
  }
  v303 = 4;
  v117 = NtQueryInformationToken(TokenHandle, TokenIsAppContainer, &TokenInformation, 4u, &v303);
  v119 = v117;
  if ( v117 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        45,
        WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids,
        (unsigned int)v117);
    Schema = RtlNtStatusToDosError(v119);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v288);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v285);
    CVaultCredDataMap::~CVaultCredDataMap((CVaultCredDataMap *)v295);
    if ( v75 )
    {
      if ( v281 )
      {
        v120 = v281;
        v121 = v75;
        do
        {
          *v121++ = 0;
          --v120;
        }
        while ( v120 );
      }
      if ( v279 )
        ((void (__fastcall *)(_BYTE *))v279)(v75);
      else
        VaultFreeInternal(v75);
    }
    v122 = v277;
    if ( v277 )
    {
      v123 = v278;
      if ( v278 )
      {
        do
        {
          *v122++ = 0;
          --v123;
        }
        while ( v123 );
        v122 = v277;
      }
      if ( v276 )
        v276();
      else
        VaultFreeInternal(v122);
      v277 = 0;
    }
    goto LABEL_431;
  }
  if ( !TokenInformation )
    goto LABEL_432;
  if ( (*((_BYTE *)a3 + 64) & 0x40) != 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids, 5);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v288);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v285);
    CVaultCredDataMap::~CVaultCredDataMap((CVaultCredDataMap *)v295);
    if ( v75 )
    {
      if ( v281 )
      {
        v124 = v281;
        v125 = v75;
        do
        {
          *v125++ = 0;
          --v124;
        }
        while ( v124 );
      }
      if ( v279 )
        ((void (__fastcall *)(_BYTE *))v279)(v75);
      else
        VaultFreeInternal(v75);
    }
    v126 = v277;
    if ( v277 )
    {
      v127 = v278;
      if ( v278 )
      {
        do
        {
          *v126++ = 0;
          --v127;
        }
        while ( v127 );
        v126 = v277;
      }
      if ( v276 )
        v276();
      else
        VaultFreeInternal(v126);
      v277 = 0;
    }
    v278 = 0;
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v282);
    return 5;
  }
  v128 = dword_18005F63C;
  if ( dword_18005F63C
    && (*(unsigned int (__fastcall **)(_BYTE *, _QWORD))(*(_QWORD *)v75 + 224LL))(v75, *((_QWORD *)hMem + 2)) + 1 > v128 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        47,
        WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids,
        (unsigned int)dword_18005F63C);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v288);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v285);
    CVaultCredDataMap::~CVaultCredDataMap((CVaultCredDataMap *)v295);
    if ( v75 )
    {
      v129 = v281;
      if ( v281 )
      {
        v130 = v75;
        do
        {
          *v130++ = 0;
          --v129;
        }
        while ( v129 );
      }
      if ( v279 )
        ((void (__fastcall *)(_BYTE *))v279)(v75);
      else
        VaultFreeInternal(v75);
    }
    v131 = v277;
    if ( v277 )
    {
      v132 = v278;
      if ( v278 )
      {
        do
        {
          *v131++ = 0;
          --v132;
        }
        while ( v132 );
        v131 = v277;
      }
      if ( v276 )
        v276();
      else
        VaultFreeInternal(v131);
      v277 = 0;
    }
    v278 = 0;
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v282);
    return 1381;
  }
  v292 = 0;
  Schema = PopulateCallerAccountInfo(TokenHandle, (struct IVaultCredential *)v283, Filename, v118);
  if ( Schema )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids, Schema);
    if ( Schema != 15700 && Schema != 120 && Schema - 2 > 1 && Schema != 1168 )
    {
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v288);
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v285);
      CVaultCredDataMap::~CVaultCredDataMap((CVaultCredDataMap *)v295);
      if ( v75 )
      {
        if ( v281 )
        {
          v133 = v281;
          v134 = v75;
          do
          {
            *v134++ = 0;
            --v133;
          }
          while ( v133 );
        }
        if ( v279 )
          ((void (__fastcall *)(_BYTE *))v279)(v75);
        else
          VaultFreeInternal(v75);
      }
      v135 = v277;
      if ( v277 )
      {
        v136 = v278;
        if ( v278 )
        {
          do
          {
            *v135++ = 0;
            --v136;
          }
          while ( v136 );
          v135 = v277;
        }
        if ( v276 )
          v276();
        else
          VaultFreeInternal(v135);
        v277 = 0;
      }
      goto LABEL_431;
    }
LABEL_432:
    v292 = 1;
  }
  v294 = (*(__int64 (__fastcall **)(HLOCAL))(*(_QWORD *)v277 + 120LL))(v277);
  v137 = v302;
  v138 = ValidateAndSetCredentialElement(
           (_DWORD)v302,
           *((_QWORD *)a3 + 4),
           v294,
           (_DWORD)v283,
           (__int64) IVaultCredential::`vcall'{40,{flat}},
           1,
           (__int64)v275,
           (__int64)&v330);
  if ( v138 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids, v138);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v288);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v285);
    CVaultCredDataMap::~CVaultCredDataMap((CVaultCredDataMap *)v295);
    if ( v75 )
    {
      if ( v281 )
      {
        v139 = v281;
        v140 = v75;
        do
        {
          *v140++ = 0;
          --v139;
        }
        while ( v139 );
      }
      if ( v279 )
        ((void (__fastcall *)(_BYTE *))v279)(v75);
      else
        VaultFreeInternal(v75);
    }
    v141 = v277;
    if ( v277 )
    {
      v142 = v278;
      if ( v278 )
      {
        do
        {
          *v141++ = 0;
          --v142;
        }
        while ( v142 );
        v141 = v277;
      }
      if ( v276 )
        v276();
      else
        VaultFreeInternal(v141);
      v277 = 0;
    }
LABEL_764:
    v278 = 0;
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v282);
    return v138;
  }
  if ( v275[0] )
  {
    v143 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v294 + 8LL))(v294);
    v138 = CVaultCredDataMap::SetCredData(v295, v143, &v330);
    if ( v138 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids, v138);
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v288);
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v285);
      CVaultCredDataMap::~CVaultCredDataMap((CVaultCredDataMap *)v295);
      if ( v75 )
      {
        if ( v281 )
        {
          v144 = v281;
          v145 = v75;
          do
          {
            *v145++ = 0;
            --v144;
          }
          while ( v144 );
        }
        if ( v279 )
          ((void (__fastcall *)(_BYTE *))v279)(v75);
        else
          VaultFreeInternal(v75);
      }
      v146 = v277;
      if ( v277 )
      {
        v147 = v278;
        if ( v278 )
        {
          do
          {
            *v146++ = 0;
            --v147;
          }
          while ( v147 );
          v146 = v277;
        }
        if ( v276 )
          v276();
        else
          VaultFreeInternal(v146);
        v277 = 0;
      }
      goto LABEL_764;
    }
  }
  v148 = (*(__int64 (__fastcall **)(HLOCAL))(*(_QWORD *)v277 + 112LL))(v277);
  v294 = v148;
  if ( v148 )
  {
    v152 = *((_QWORD *)a3 + 3);
    if ( v152 )
    {
      v138 = ValidateAndSetCredentialElement(
               (_DWORD)v137,
               v152,
               v148,
               (_DWORD)v283,
               (__int64) IVaultCredential::`vcall'{48,{flat}},
               1,
               (__int64)v275,
               (__int64)&v315);
      if ( v138 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids, v138);
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v288);
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v285);
        CVaultCredDataMap::~CVaultCredDataMap((CVaultCredDataMap *)v295);
        if ( v75 )
        {
          if ( v281 )
          {
            v157 = v281;
            v158 = v75;
            do
            {
              *v158++ = 0;
              --v157;
            }
            while ( v157 );
          }
          if ( v279 )
            ((void (__fastcall *)(_BYTE *))v279)(v75);
          else
            VaultFreeInternal(v75);
        }
        v159 = v277;
        if ( v277 )
        {
          v160 = v278;
          if ( v278 )
          {
            do
            {
              *v159++ = 0;
              --v160;
            }
            while ( v160 );
            v159 = v277;
          }
          if ( v276 )
            v276();
          else
            VaultFreeInternal(v159);
          v277 = 0;
        }
        goto LABEL_764;
      }
      if ( v275[0] )
      {
        v161 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v294 + 8LL))(v294);
        v138 = CVaultCredDataMap::SetCredData(v295, v161, &v315);
        if ( v138 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids, v138);
          CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v288);
          CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v285);
          CVaultCredDataMap::~CVaultCredDataMap((CVaultCredDataMap *)v295);
          if ( v75 )
          {
            if ( v281 )
            {
              v162 = v281;
              v163 = v75;
              do
              {
                *v163++ = 0;
                --v162;
              }
              while ( v162 );
            }
            if ( v279 )
              ((void (__fastcall *)(_BYTE *))v279)(v75);
            else
              VaultFreeInternal(v75);
          }
          v164 = v277;
          if ( v277 )
          {
            v165 = v278;
            if ( v278 )
            {
              do
              {
                *v164++ = 0;
                --v165;
              }
              while ( v165 );
              v164 = v277;
            }
            if ( v276 )
              v276();
            else
              VaultFreeInternal(v164);
            v277 = 0;
          }
          goto LABEL_764;
        }
      }
      goto LABEL_476;
    }
LABEL_488:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v288);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v285);
    CVaultCredDataMap::~CVaultCredDataMap((CVaultCredDataMap *)v295);
    if ( v75 )
    {
      if ( v281 )
      {
        v153 = v281;
        v154 = v75;
        do
        {
          *v154++ = 0;
          --v153;
        }
        while ( v153 );
      }
      if ( v279 )
        ((void (__fastcall *)(_BYTE *))v279)(v75);
      else
        VaultFreeInternal(v75);
    }
    v155 = v277;
    if ( v277 )
    {
      v156 = v278;
      if ( v278 )
      {
        do
        {
          *v155++ = 0;
          --v156;
        }
        while ( v156 );
        v155 = v277;
      }
      if ( v276 )
        v276();
      else
        VaultFreeInternal(v155);
      v277 = 0;
    }
    goto LABEL_688;
  }
  if ( *((_QWORD *)a3 + 3) )
    goto LABEL_488;
LABEL_476:
  v149 = (struct _VAULT_ITEM_ELEMENT *)*((_QWORD *)a3 + 5);
  v293 = a5 & 1;
  if ( v149 )
  {
    if ( (a5 & 1) != 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids);
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v288);
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v285);
      CVaultCredDataMap::~CVaultCredDataMap((CVaultCredDataMap *)v295);
      if ( v75 )
      {
        if ( v281 )
        {
          v168 = v281;
          v169 = v75;
          do
          {
            *v169++ = 0;
            --v168;
          }
          while ( v168 );
        }
        if ( v279 )
          ((void (__fastcall *)(_BYTE *))v279)(v75);
        else
          VaultFreeInternal(v75);
      }
      v170 = v277;
      if ( v277 )
      {
        v171 = v278;
        if ( v278 )
        {
          do
          {
            *v170++ = 0;
            --v171;
          }
          while ( v171 );
          v170 = v277;
        }
        if ( v276 )
          v276();
        else
          VaultFreeInternal(v170);
        v277 = 0;
      }
      goto LABEL_688;
    }
    v172 = (*(__int64 (__fastcall **)(HLOCAL))(*(_QWORD *)v277 + 128LL))(v277);
    v294 = v172;
    if ( (a5 & 0x20) != 0 )
    {
      v138 = VaultUnprotectAuthenticator(v149, (struct _VAULT_ITEM_ELEMENT **)&v318);
      if ( v138 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids, v138);
        v174 = v318;
        if ( v318 )
        {
          if ( v319 )
          {
            v173 = v319;
            v175 = v318;
            do
            {
              *v175++ = 0;
              --v173;
            }
            while ( v173 );
          }
          if ( v317 )
            ((void (__fastcall *)(HLOCAL, __int64))v317)(v174, v173);
          else
            VaultFreeInternal(v174);
        }
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v288);
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v285);
        CVaultCredDataMap::~CVaultCredDataMap((CVaultCredDataMap *)v295);
        if ( v75 )
        {
          if ( v281 )
          {
            v176 = v281;
            v177 = v75;
            do
            {
              *v177++ = 0;
              --v176;
            }
            while ( v176 );
          }
          if ( v279 )
            ((void (__fastcall *)(_BYTE *))v279)(v75);
          else
            VaultFreeInternal(v75);
        }
        v178 = v277;
        if ( v277 )
        {
          v179 = v278;
          if ( v278 )
          {
            do
            {
              *v178++ = 0;
              --v179;
            }
            while ( v179 );
            v178 = v277;
          }
          if ( v276 )
            v276();
          else
            VaultFreeInternal(v178);
          v277 = 0;
        }
        goto LABEL_764;
      }
      v12 = v318;
      LODWORD(v149) = (_DWORD)v318;
      v7 = v319;
      v13 = v317;
      LODWORD(v172) = v294;
    }
    v138 = ValidateAndSetCredentialElement(
             (_DWORD)v137,
             (_DWORD)v149,
             v172,
             (_DWORD)v283,
             (__int64) IVaultCredential::`vcall'{56,{flat}},
             1,
             (__int64)v275,
             (__int64)&v326);
    if ( v138 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids, v138);
      if ( v12 )
      {
        if ( v7 )
        {
          v181 = v7;
          v182 = v12;
          do
          {
            *v182++ = 0;
            --v181;
          }
          while ( v181 );
        }
        if ( v13 )
          v13(v12);
        else
          VaultFreeInternal(v12);
      }
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v288);
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v285);
      CVaultCredDataMap::~CVaultCredDataMap((CVaultCredDataMap *)v295);
      if ( v75 )
      {
        if ( v281 )
        {
          v183 = v281;
          v184 = v75;
          do
          {
            *v184++ = 0;
            --v183;
          }
          while ( v183 );
        }
        if ( v279 )
          ((void (__fastcall *)(_BYTE *))v279)(v75);
        else
          VaultFreeInternal(v75);
      }
      v185 = v277;
      if ( v277 )
      {
        v186 = v278;
        if ( v278 )
        {
          do
          {
            *v185++ = 0;
            --v186;
          }
          while ( v186 );
          v185 = v277;
        }
        if ( v276 )
          v276();
        else
          VaultFreeInternal(v185);
        v277 = 0;
      }
      goto LABEL_764;
    }
    if ( v275[0] )
    {
      v187 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v294 + 8LL))(v294);
      v138 = CVaultCredDataMap::SetCredData(v295, v187, &v326);
      if ( v138 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids, v138);
        if ( v12 )
        {
          if ( v7 )
          {
            v188 = v7;
            v189 = v12;
            do
            {
              *v189++ = 0;
              --v188;
            }
            while ( v188 );
          }
          if ( v13 )
            v13(v12);
          else
            VaultFreeInternal(v12);
        }
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v288);
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v285);
        CVaultCredDataMap::~CVaultCredDataMap((CVaultCredDataMap *)v295);
        if ( v75 )
        {
          if ( v281 )
          {
            v190 = v281;
            v191 = v75;
            do
            {
              *v191++ = 0;
              --v190;
            }
            while ( v190 );
          }
          if ( v279 )
            ((void (__fastcall *)(_BYTE *))v279)(v75);
          else
            VaultFreeInternal(v75);
        }
        v192 = v277;
        if ( v277 )
        {
          v193 = v278;
          if ( v278 )
          {
            do
            {
              *v192++ = 0;
              --v193;
            }
            while ( v193 );
            v192 = v277;
          }
          if ( v276 )
            v276();
          else
            VaultFreeInternal(v192);
          v277 = 0;
        }
        goto LABEL_764;
      }
    }
    else if ( !CUserVault::IsCredmanVault(v137, v180) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids);
      if ( v12 )
      {
        if ( v7 )
        {
          v194 = v7;
          v195 = v12;
          do
          {
            *v195++ = 0;
            --v194;
          }
          while ( v194 );
        }
        if ( v13 )
          v13(v12);
        else
          VaultFreeInternal(v12);
      }
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v288);
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v285);
      CVaultCredDataMap::~CVaultCredDataMap((CVaultCredDataMap *)v295);
      if ( v75 )
      {
        if ( v281 )
        {
          v196 = v281;
          v197 = v75;
          do
          {
            *v197++ = 0;
            --v196;
          }
          while ( v196 );
        }
        if ( v279 )
          ((void (__fastcall *)(_BYTE *))v279)(v75);
        else
          VaultFreeInternal(v75);
      }
      v198 = v277;
      if ( v277 )
      {
        v199 = v278;
        if ( v278 )
        {
          do
          {
            *v198++ = 0;
            --v199;
          }
          while ( v199 );
          v198 = v277;
        }
        if ( v276 )
          v276();
        else
          VaultFreeInternal(v198);
        v277 = 0;
      }
      goto LABEL_688;
    }
  }
  else if ( (a5 & 1) == 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v288);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v285);
    CVaultCredDataMap::~CVaultCredDataMap((CVaultCredDataMap *)v295);
    if ( v75 )
    {
      if ( v281 )
      {
        v150 = v281;
        v151 = v75;
        do
        {
          *v151++ = 0;
          --v150;
        }
        while ( v150 );
      }
      if ( v279 )
        ((void (__fastcall *)(_BYTE *))v279)(v75);
      else
        VaultFreeInternal(v75);
    }
    v166 = v277;
    if ( v277 )
    {
      v167 = v278;
      if ( v278 )
      {
        do
        {
          *v166++ = 0;
          --v167;
        }
        while ( v167 );
        v166 = v277;
      }
      if ( v276 )
        v276();
      else
        VaultFreeInternal(v166);
      v277 = 0;
    }
LABEL_688:
    v278 = 0;
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v282);
    return 87;
  }
  v200 = 0;
  if ( *((_DWORD *)a3 + 17) )
  {
    while ( 1 )
    {
      v201 = 32LL * v200;
      v294 = (*(__int64 (__fastcall **)(HLOCAL, _QWORD))(*(_QWORD *)v277 + 144LL))(
               v277,
               *(unsigned int *)(v201 + *((_QWORD *)a3 + 9)));
      v138 = ValidateAndSetCredentialElement(
               (_DWORD)v302,
               (unsigned int)v201 + (unsigned int)*((_QWORD *)a3 + 9),
               v294,
               (_DWORD)v283,
               (__int64) IVaultCredential::`vcall'{64,{flat}},
               0,
               (__int64)v275,
               (__int64)&v326);
      if ( v138 )
        break;
      if ( v275[0] )
      {
        v202 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v294 + 8LL))(v294);
        v138 = CVaultCredDataMap::SetCredData(v295, v202, &v326);
        if ( v138 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              61,
              WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids,
              v200,
              v138);
          if ( v12 )
          {
            if ( v7 )
            {
              v213 = v7;
              v214 = v12;
              do
              {
                *v214++ = 0;
                --v213;
              }
              while ( v213 );
            }
            if ( v13 )
              v13(v12);
            else
              VaultFreeInternal(v12);
          }
          CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v288);
          CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v285);
          CVaultCredDataMap::~CVaultCredDataMap((CVaultCredDataMap *)v295);
          if ( v75 )
          {
            if ( v281 )
            {
              v215 = v281;
              v216 = v75;
              do
              {
                *v216++ = 0;
                --v215;
              }
              while ( v215 );
            }
            if ( v279 )
              ((void (__fastcall *)(_BYTE *))v279)(v75);
            else
              VaultFreeInternal(v75);
          }
          v217 = v277;
          if ( v277 )
          {
            v218 = v278;
            if ( v278 )
            {
              do
              {
                *v217++ = 0;
                --v218;
              }
              while ( v218 );
              v217 = v277;
            }
            if ( v276 )
              v276();
            else
              VaultFreeInternal(v217);
            v277 = 0;
          }
          goto LABEL_764;
        }
      }
      if ( ++v200 >= *((_DWORD *)a3 + 17) )
        goto LABEL_694;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids, v200, v138);
    if ( v12 )
    {
      if ( v7 )
      {
        v219 = v7;
        v220 = v12;
        do
        {
          *v220++ = 0;
          --v219;
        }
        while ( v219 );
      }
      if ( v13 )
        v13(v12);
      else
        VaultFreeInternal(v12);
    }
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v288);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v285);
    CVaultCredDataMap::~CVaultCredDataMap((CVaultCredDataMap *)v295);
    if ( v75 )
    {
      if ( v281 )
      {
        v221 = v281;
        v222 = v75;
        do
        {
          *v222++ = 0;
          --v221;
        }
        while ( v221 );
      }
      if ( v279 )
        ((void (__fastcall *)(_BYTE *))v279)(v75);
      else
        VaultFreeInternal(v75);
    }
    v223 = v277;
    if ( v277 )
    {
      v224 = v278;
      if ( v278 )
      {
        do
        {
          *v223++ = 0;
          --v224;
        }
        while ( v224 );
        v223 = v277;
      }
      if ( v276 )
        v276();
      else
        VaultFreeInternal(v223);
      v277 = 0;
    }
    goto LABEL_764;
  }
LABEL_694:
  v203 = *((_DWORD *)a3 + 16);
  v204 = (struct _GUID *)(v203 & 0x40);
  LODWORD(v204) = (unsigned int)v204 | 0x200;
  if ( (v203 & 0x800) == 0 )
    v204 = (struct _GUID *)(*((_DWORD *)a3 + 16) & 0x40);
  v205 = (unsigned int)v204 | 0x10000000;
  if ( !v293 )
    v205 = (unsigned int)v204;
  v206 = v205 | 0x20;
  if ( (a5 & 0x20) == 0 )
    v206 = v205;
  v207 = v203 & 0xF0FF | v206;
  v208 = v302;
  if ( (a5 & 0x1000) != 0 || !CUserVault::IsBuiltinVault(v302, v204) )
    v207 |= 0x400u;
  (*(void (__fastcall **)(HLOCAL, _QWORD))(*(_QWORD *)v283 + 168LL))(v283, v207);
  v209 = (*(__int64 (__fastcall **)(HLOCAL, int *))(*(_QWORD *)v283 + 248LL))(v283, &v301);
  v293 = v209;
  if ( v209 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids, v209);
    if ( v12 )
    {
      if ( v7 )
      {
        v211 = v7;
        v212 = v12;
        do
        {
          *v212++ = 0;
          --v211;
        }
        while ( v211 );
      }
      if ( v13 )
        v13(v12);
      else
        VaultFreeInternal(v12);
    }
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v288);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v285);
    CVaultCredDataMap::~CVaultCredDataMap((CVaultCredDataMap *)v295);
    if ( v75 )
    {
      if ( v281 )
      {
        v225 = v281;
        v226 = v75;
        do
        {
          *v226++ = 0;
          --v225;
        }
        while ( v225 );
      }
      if ( v279 )
        ((void (__fastcall *)(_BYTE *))v279)(v75);
      else
        VaultFreeInternal(v75);
    }
    v227 = v277;
    if ( v277 )
    {
      v228 = v278;
      if ( v278 )
      {
        do
        {
          *v227++ = 0;
          --v228;
        }
        while ( v228 );
        v227 = v277;
      }
      if ( v276 )
        v276();
      else
        VaultFreeInternal(v227);
      v277 = 0;
    }
    v278 = 0;
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v282);
    return v293;
  }
  if ( v301 )
    (*(void (__fastcall **)(HLOCAL, _QWORD))(*(_QWORD *)v283 + 168LL))(v283, v207 | 0x100);
  if ( !CUserVault::IsCredmanVault(v208, v210) )
  {
    v229 = CVaultCredDataMap::SerializeData((CVaultCredDataMap *)v295, (unsigned __int8 **)&v308, &v305);
    if ( v229 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids, v229);
      if ( v12 )
      {
        if ( v7 )
        {
          v230 = v7;
          v231 = v12;
          do
          {
            *v231++ = 0;
            --v230;
          }
          while ( v230 );
        }
        if ( v13 )
          v13(v12);
        else
          VaultFreeInternal(v12);
      }
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v288);
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v285);
      CVaultCredDataMap::~CVaultCredDataMap((CVaultCredDataMap *)v295);
      v233 = v308;
      if ( v308 )
      {
        if ( v309 )
        {
          v232 = v309;
          v234 = v308;
          do
          {
            *v234++ = 0;
            --v232;
          }
          while ( v232 );
        }
        if ( v307 )
          v307(v233, v232);
        else
          VaultFreeInternal(v233);
      }
      CVaultAutoPtr<IVaultStore *,void,IVaultStore *,0>::~CVaultAutoPtr<IVaultStore *,void,IVaultStore *,0>(&v279);
      CVaultAutoPtr<void *,int,void *,0>::~CVaultAutoPtr<void *,int,void *,0>(&v276);
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v282);
      return v229;
    }
    LOBYTE(ReturnLength) = 1;
    v235 = CUserVault::EncryptData(v208, 1, v308, v305, ReturnLength, &v322, &v306);
    if ( v235 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids, v235);
      if ( !v12 )
        goto LABEL_913;
      if ( v7 )
      {
        v236 = v7;
        v237 = v12;
        do
        {
          *v237++ = 0;
          --v236;
        }
        while ( v236 );
      }
      v238 = v12;
      if ( !v13 )
      {
        VaultFreeInternal(v12);
        goto LABEL_913;
      }
      goto LABEL_911;
    }
    v235 = (*(__int64 (__fastcall **)(HLOCAL, __int64, _QWORD))(*(_QWORD *)v283 + 80LL))(v283, v322, v306);
    if ( v235 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids, v235);
      if ( !v12 )
        goto LABEL_913;
      if ( v7 )
      {
        v239 = v7;
        v240 = v12;
        do
        {
          *v240++ = 0;
          --v239;
        }
        while ( v239 );
      }
      v238 = v12;
      if ( !v13 )
      {
        VaultFreeInternal(v12);
        goto LABEL_913;
      }
      goto LABEL_911;
    }
  }
  v241 = CVaultPackageId::CVaultPackageId((CVaultPackageId *)v334, *((void *const *)hMem + 2));
  *(_QWORD *)&v315 = 8;
  HIDWORD(v315) = 0;
  v242 = 0;
  if ( *((_DWORD *)v241 + 10) )
    v242 = v241;
  DWORD2(v315) = *((_DWORD *)v241 + 10);
  v243 = (*(__int64 (__fastcall **)(HLOCAL))(*(_QWORD *)v277 + 112LL))(v277);
  v244 = *((_QWORD *)a3 + 3);
  v245 = (*(__int64 (__fastcall **)(HLOCAL))(*(_QWORD *)v277 + 120LL))(v277);
  v316 = v242;
  v235 = ComputeItemDigest(AccountTypeString, *((_QWORD *)AccountTypeString + 4), v245, v244, v243, &v315, v335);
  if ( v235 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids, v235);
    if ( !v12 )
      goto LABEL_913;
    if ( v7 )
    {
      v246 = v7;
      v247 = v12;
      do
      {
        *v247++ = 0;
        --v246;
      }
      while ( v246 );
    }
    v238 = v12;
    if ( !v13 )
    {
      VaultFreeInternal(v12);
      goto LABEL_913;
    }
    goto LABEL_911;
  }
  v235 = (*(__int64 (__fastcall **)(HLOCAL, _BYTE *, __int64))(*(_QWORD *)v283 + 88LL))(v283, v335, 82);
  if ( v235 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids, v235);
    if ( !v12 )
      goto LABEL_913;
    if ( v7 )
    {
      v248 = v7;
      v249 = v12;
      do
      {
        *v249++ = 0;
        --v248;
      }
      while ( v248 );
    }
    v238 = v12;
    if ( !v13 )
    {
      VaultFreeInternal(v12);
      goto LABEL_913;
    }
    goto LABEL_911;
  }
  v310 = 0;
  memset(v331, 0, sizeof(v331));
  v332 = 0;
  Handle = 0;
  v291 = 0;
  v250 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 1u, &Handle);
  v252 = v250;
  if ( v250 >= 0 )
  {
    v250 = NtQueryInformationToken(Handle, TokenUser, v331, 0x58u, &v310);
    v252 = v250;
    if ( v250 >= 0 )
    {
      v250 = LsaILookupUserAccountType(*(_QWORD *)&v331[0], &v291);
      v252 = v250;
      if ( v250 < 0 )
      {
        v253 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          v254 = 32;
          goto LABEL_856;
        }
      }
    }
    else
    {
      v253 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v254 = 31;
        goto LABEL_856;
      }
    }
  }
  else
  {
    v253 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v254 = 30;
LABEL_856:
      WPP_SF_d(v253[2], v254, WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids, (unsigned int)v250);
    }
  }
  if ( Handle )
    NtClose(Handle);
  if ( v252 < 0 )
  {
    v255 = RtlNtStatusToDosError(v252);
    v235 = v255;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids, v255);
    if ( !v12 )
      goto LABEL_913;
    if ( v7 )
    {
      v256 = v7;
      v257 = v12;
      do
      {
        *v257++ = 0;
        --v256;
      }
      while ( v256 );
    }
    v238 = v12;
    if ( !v13 )
    {
      VaultFreeInternal(v12);
      goto LABEL_913;
    }
    goto LABEL_911;
  }
  if ( v292 && !CUserVault::IsCredmanVault(v302, v251) && ((v291 - 2) & 0xFFFFFFFC) == 0 && v291 != 4 )
  {
    v333 = 0;
    v323 = AutoDereference<IVaultKeyManager>;
    v324 = 0;
    v325 = 0;
    if ( (*(unsigned int (__fastcall **)(_BYTE *, _BYTE *, __int64 *))(*(_QWORD *)v75 + 168LL))(v75, v335, &v324) )
    {
      v333 = xmmword_180053830;
    }
    else
    {
      v235 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v324 + 280LL))(v324, &v333);
      if ( v235 )
      {
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v323);
        if ( !v12 )
          goto LABEL_913;
        if ( v7 )
        {
          v258 = v7;
          v259 = v12;
          do
          {
            *v259++ = 0;
            --v258;
          }
          while ( v258 );
        }
        v238 = v12;
        if ( !v13 )
        {
          VaultFreeInternal(v12);
          goto LABEL_913;
        }
        goto LABEL_911;
      }
    }
    v235 = (*(__int64 (__fastcall **)(HLOCAL, __int128 *))(*(_QWORD *)v283 + 312LL))(v283, &v333);
    if ( v235 )
    {
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v323);
      if ( !v12 )
        goto LABEL_913;
      if ( v7 )
      {
        v260 = v7;
        v261 = v12;
        do
        {
          *v261++ = 0;
          --v260;
        }
        while ( v260 );
      }
      v238 = v12;
      if ( !v13 )
      {
        VaultFreeInternal(v12);
        goto LABEL_913;
      }
      goto LABEL_911;
    }
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v323);
  }
  v262 = (*(__int64 (__fastcall **)(_BYTE *, HLOCAL, _BYTE *, _QWORD))(*(_QWORD *)v75 + 104LL))(v75, v283, v335, 0);
  v235 = v262;
  if ( v262 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids, v262);
    if ( !v12 )
      goto LABEL_913;
    if ( v7 )
    {
      v264 = v7;
      v265 = v12;
      do
      {
        *v265++ = 0;
        --v264;
      }
      while ( v264 );
    }
    v238 = v12;
    if ( !v13 )
    {
      VaultFreeInternal(v12);
      goto LABEL_913;
    }
LABEL_911:
    v13(v238);
LABEL_913:
    CVaultAutoPtr<void *,int,void *,0>::~CVaultAutoPtr<void *,int,void *,0>(&v288);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v285);
    CVaultAutoPtr<void *,int,void *,0>::~CVaultAutoPtr<void *,int,void *,0>(v313);
    CVaultCredDataMap::~CVaultCredDataMap((CVaultCredDataMap *)v295);
    CVaultAutoPtr<void *,int,void *,0>::~CVaultAutoPtr<void *,int,void *,0>(&v307);
    CVaultAutoPtr<IVaultStore *,void,IVaultStore *,0>::~CVaultAutoPtr<IVaultStore *,void,IVaultStore *,0>(&v279);
    CVaultAutoPtr<void *,int,void *,0>::~CVaultAutoPtr<void *,int,void *,0>(&v276);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v282);
    return v235;
  }
  if ( v301 )
  {
    if ( (a5 & 0x4000) != 0 )
    {
      RtlPublishWnfStateData(WNF_VTSV_ADD_CRED_NOTIFY, 0, 0, 0, 0);
      if ( (unsigned int)dword_18005F0C0 > 5
        && (qword_18005F0D0 & 0x400000000000LL) != 0
        && (qword_18005F0D8 & 0x400000000000LL) == qword_18005F0D8 )
      {
        AccountTypeString = (struct _VAULT_ITEM *)GetAccountTypeString(v291);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          v266,
          (unsigned int)byte_180054CF5,
          v267,
          v268,
          (__int64)&AccountTypeString);
      }
    }
  }
  LogAppName(Filename, v336, v263);
  if ( (unsigned int)dword_18005F0C0 > 5
    && (qword_18005F0D0 & 0x400000000000LL) != 0
    && (qword_18005F0D8 & 0x400000000000LL) == qword_18005F0D8 )
  {
    v327 = GetAccountTypeString(v291);
    v271 = L"NULL";
    if ( v336[0] )
      v271 = v336;
    v328 = v271;
    v329 = Filename;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (unsigned int)v336,
      (unsigned int)&dword_180054CAC,
      v269,
      v270,
      (__int64)&v329,
      (__int64)&v328,
      (__int64)&v327);
  }
  if ( v12 )
  {
    if ( v7 )
    {
      v272 = v7;
      v273 = v12;
      do
      {
        *v273++ = 0;
        --v272;
      }
      while ( v272 );
    }
    if ( v13 )
      v13(v12);
    else
      VaultFreeInternal(v12);
  }
  CVaultAutoPtr<void *,int,void *,0>::~CVaultAutoPtr<void *,int,void *,0>(&v288);
  CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v285);
  CVaultAutoPtr<void *,int,void *,0>::~CVaultAutoPtr<void *,int,void *,0>(v313);
  CVaultCredDataMap::~CVaultCredDataMap((CVaultCredDataMap *)v295);
  CVaultAutoPtr<void *,int,void *,0>::~CVaultAutoPtr<void *,int,void *,0>(&v307);
  CVaultAutoPtr<IVaultStore *,void,IVaultStore *,0>::~CVaultAutoPtr<IVaultStore *,void,IVaultStore *,0>(&v279);
  CVaultAutoPtr<void *,int,void *,0>::~CVaultAutoPtr<void *,int,void *,0>(&v276);
  CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v282);
  return 0;
}

```

## disassembly

```asm
0x180016250  mov     [rsp-8+arg_0], rbx
0x180016255  push    rbp
0x180016256  push    rsi
0x180016257  push    rdi
0x180016258  push    r12
0x18001625a  push    r13
0x18001625c  push    r14
0x18001625e  push    r15
0x180016260  lea     rbp, [rsp-620h]
0x180016268  sub     rsp, 720h
0x18001626f  mov     rax, cs:__security_cookie
0x180016276  xor     rax, rsp
0x180016279  mov     [rbp+650h+var_40], rax
0x180016280  mov     rdi, r8
0x180016283  mov     [rbp+650h+var_600], r8
0x180016287  mov     rbx, rdx
0x18001628a  xor     r12d, r12d
0x18001628d  mov     ecx, r12d
0x180016290  cmp     [r8+18h], rcx
0x180016294  setnz   cl
0x180016297  add     ecx, 2
0x18001629a  mov     esi, [r8+44h]
0x18001629e  add     esi, ecx
0x1800162a0  lea     rax, WPP_GLOBAL_Control
0x1800162a7  cmp     esi, ecx
0x1800162a9  jnb     short loc_1800162D7
0x1800162ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800162b2  cmp     rcx, rax
0x1800162b5  jz      short loc_1800162D2
0x1800162b7  test    byte ptr [rcx+1Ch], 2
0x1800162bb  jz      short loc_1800162D2
0x1800162bd  mov     edx, 0Bh
0x1800162c2  lea     r8, WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids
0x1800162c9  mov     rcx, [rcx+10h]
0x1800162cd  call    WPP_SF_
0x1800162d2  mov     esi, 2
0x1800162d7  lea     rax, ??$AutoDereference@UIVaultKeyManager@@@@YAXPEAUIVaultKeyManager@@@Z; AutoDereference<IVaultKeyManager>(IVaultKeyManager *)
0x1800162de  mov     [rsp+750h+var_6D8], rax
0x1800162e3  mov     [rbp+650h+var_6D0], r12
0x1800162e7  mov     [rbp+650h+var_6C8], r12d
0x1800162eb  lea     rax, ??$AutoDereference@UIVaultKeyManager@@@@YAXPEAUIVaultKeyManager@@@Z; AutoDereference<IVaultKeyManager>(IVaultKeyManager *)
0x1800162f2  mov     [rsp+750h+var_708], rax
0x1800162f7  mov     [rsp+750h+var_700], r12
0x1800162fc  mov     [rsp+750h+var_6F8], r12d
0x180016301  lea     rax, ??$AutoDereference@UIVaultKeyManager@@@@YAXPEAUIVaultKeyManager@@@Z; AutoDereference<IVaultKeyManager>(IVaultKeyManager *)
0x180016308  mov     [rsp+750h+var_6F0], rax
0x18001630d  mov     [rsp+750h+var_6E8], r12
0x180016312  mov     [rsp+750h+var_6E0], r12d
0x180016317  mov     [rbp+650h+var_620], r12
0x18001631b  mov     [rbp+650h+var_618], r12d
0x18001631f  mov     [rbp+650h+var_628], r12
0x180016323  mov     [rbp+650h+var_598], r12
0x18001632a  mov     [rbp+650h+var_630], r12d
0x18001632e  mov     [rbp+650h+var_62C], r12d
0x180016332  xorps   xmm0, xmm0
0x180016335  movdqu  [rbp+650h+var_658], xmm0
0x18001633a  mov     ecx, 38h ; '8'; Size
0x18001633f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180016344  mov     [rax], rax
0x180016347  mov     [rax+8], rax
0x18001634b  mov     [rax+10h], rax
0x18001634f  mov     word ptr [rax+18h], 101h
0x180016355  mov     qword ptr [rbp+650h+var_658], rax
0x180016359  mov     [rbp+650h+var_678], esi
0x18001635c  mov     [rbp+650h+var_674], r12d
0x180016360  mov     [rbp+650h+var_670], r12
0x180016364  mov     [rbp+650h+var_668], r12d
0x180016368  mov     [rbp+650h+var_664], 1
0x18001636f  mov     [rbp+650h+var_660], 1
0x180016376  mov     [rbp+650h+var_5A8], r12
0x18001637d  mov     [rsp+750h+var_710], 0
0x180016382  xorps   xmm0, xmm0
0x180016385  movups  [rbp+650h+var_578], xmm0
0x18001638c  xorps   xmm1, xmm1
0x18001638f  movups  [rbp+650h+var_550], xmm1
0x180016396  movups  [rbp+650h+var_5E0], xmm0
0x18001639a  mov     r14, [rbx]
0x18001639d  mov     [rbp+650h+var_640], r14
0x1800163a1  mov     [rbp+650h+var_5F0], r12
0x1800163a5  mov     [rbp+650h+var_5E8], r12d
0x1800163a9  mov     [rbp+650h+var_5F8], r12
0x1800163ad  mov     qword ptr [rbp+650h+SystemTimeAsFileTime.dwLowDateTime], r12
0x1800163b4  mov     [rbp+650h+hMem], r12
0x1800163b8  mov     [rbp+650h+var_6B0], r12d
0x1800163bc  lea     rax, ??$AutoDereference@UIVaultKeyManager@@@@YAXPEAUIVaultKeyManager@@@Z; AutoDereference<IVaultKeyManager>(IVaultKeyManager *)
0x1800163c3  mov     [rbp+650h+var_6C0], rax
0x1800163c7  movzx   eax, byte ptr [rbx+55h]
0x1800163cb  mov     [rbp+650h+var_688], eax
0x1800163ce  mov     rdx, cs:__imp_CloseHandle
0x1800163d5  mov     [rbp+650h+var_6A8], rdx
0x1800163d9  mov     rbx, r12
0x1800163dc  mov     [rbp+650h+TokenHandle], rbx
0x1800163e0  mov     r9d, r12d
0x1800163e3  mov     [rbp+650h+var_698], r12d
0x1800163e7  mov     [rbp+650h+TokenInformation], r12d
0x1800163eb  mov     [rbp+650h+var_648], r12d
0x1800163ef  mov     [rbp+650h+var_638], r12d
0x1800163f3  mov     r15, r12
0x1800163f6  mov     [rbp+650h+var_5B8], r12
0x1800163fd  mov     [rbp+650h+var_5B0], r12d
0x180016404  lea     r13, ?DeleteCredentialElement@@YAXPEAU_VAULT_ITEM_ELEMENT@@@Z; DeleteCredentialElement(_VAULT_ITEM_ELEMENT *)
0x18001640b  mov     [rbp+650h+var_5C0], r13
0x180016412  mov     [rbp+650h+var_690], 0
0x180016419  xor     eax, eax
0x18001641b  mov     [rbp+650h+Filename], ax
0x180016422  mov     [rbp+650h+var_440], ax
0x180016429  cmp     [rdi+20h], rax
0x18001642d  jnz     loc_180016682
0x180016433  mov     rcx, cs:WPP_GLOBAL_Control
0x18001643a  lea     r10, WPP_GLOBAL_Control
0x180016441  cmp     rcx, r10
0x180016444  jz      short loc_18001646D
0x180016446  test    byte ptr [rcx+1Ch], 2
0x18001644a  jz      short loc_18001646D
0x18001644c  mov     edx, 21h ; '!'
0x180016451  lea     r8, WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids
0x180016458  mov     rcx, [rcx+10h]
0x18001645c  call    WPP_SF_
0x180016461  mov     r9d, [rbp+650h+var_698]
0x180016465  mov     rbx, [rbp+650h+TokenHandle]
0x180016469  mov     rdx, [rbp+650h+var_6A8]
0x18001646d  test    rbx, rbx
0x180016470  jz      short loc_1800164EE
0x180016472  test    r9d, r9d
0x180016475  jz      short loc_1800164A5
0x180016477  test    rbx, rbx
0x18001647a  jz      short loc_1800164A5
0x18001647c  mov     eax, r9d
0x18001647f  test    r9d, r9d
0x180016482  jz      short loc_1800164A5
0x180016484  nop     dword ptr [rax+00h]
0x180016488  nop     dword ptr [rax+rax+00000000h]
0x180016490  mov     byte ptr [rbx], 0
0x180016493  lea     rbx, [rbx+1]
0x180016497  sub     rax, 1
0x18001649b  jnz     short loc_180016490
0x18001649d  mov     rbx, [rbp+650h+TokenHandle]
0x1800164a1  mov     rdx, [rbp+650h+var_6A8]
0x1800164a5  test    rdx, rdx
0x1800164a8  jz      short loc_1800164B7
0x1800164aa  mov     rcx, rbx
0x1800164ad  mov     rax, rdx
0x1800164b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800164b5  jmp     short loc_1800164E6
0x1800164b7  test    rbx, rbx
0x1800164ba  jz      short loc_1800164E6
0x1800164bc  mov     rcx, rbx; hMem
0x1800164bf  call    cs:__imp_LocalSize
0x1800164c5  test    rax, rax
0x1800164c8  jz      short loc_1800164DD
0x1800164ca  mov     rcx, rbx
0x1800164cd  nop     dword ptr [rax]
0x1800164d0  mov     byte ptr [rcx], 0
0x1800164d3  lea     rcx, [rcx+1]
0x1800164d7  sub     rax, 1
0x1800164db  jnz     short loc_1800164D0
0x1800164dd  mov     rcx, rbx; hMem
0x1800164e0  call    cs:__imp_LocalFree
0x1800164e6  mov     [rbp+650h+TokenHandle], 0
0x1800164ee  mov     [rbp+650h+var_698], 0
0x1800164f5  mov     rax, [rbp+650h+hMem]
0x1800164f9  test    rax, rax
0x1800164fc  jz      short loc_18001656E
0x1800164fe  mov     ecx, [rbp+650h+var_6B0]
0x180016501  test    ecx, ecx
0x180016503  jz      short loc_18001651D
0x180016505  test    rax, rax
0x180016508  jz      short loc_18001651D
0x18001650a  test    rcx, rcx
0x18001650d  jz      short loc_18001651D
0x18001650f  nop
0x180016510  mov     byte ptr [rax], 0
0x180016513  lea     rax, [rax+1]
0x180016517  sub     rcx, 1
0x18001651b  jnz     short loc_180016510
0x18001651d  mov     rax, [rbp+650h+var_6C0]
0x180016521  test    rax, rax
0x180016524  jz      short loc_180016531
0x180016526  mov     rcx, [rbp+650h+hMem]
0x18001652a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001652f  jmp     short loc_180016566
0x180016531  mov     rbx, [rbp+650h+hMem]
0x180016535  test    rbx, rbx
0x180016538  jz      short loc_180016566
0x18001653a  mov     rcx, rbx; hMem
0x18001653d  call    cs:__imp_LocalSize
0x180016543  test    rax, rax
0x180016546  jz      short loc_18001655D
0x180016548  mov     rdx, rbx
0x18001654b  nop     dword ptr [rax+rax+00h]
0x180016550  mov     byte ptr [rdx], 0
0x180016553  lea     rdx, [rdx+1]
0x180016557  sub     rax, 1
0x18001655b  jnz     short loc_180016550
0x18001655d  mov     rcx, rbx; hMem
0x180016560  call    cs:__imp_LocalFree
0x180016566  mov     [rbp+650h+hMem], 0
0x18001656e  mov     [rbp+650h+var_6B0], 0
0x180016575  lea     rcx, [rbp+650h+var_678]; this
0x180016579  call    ??1CVaultCredDataMap@@QEAA@XZ; CVaultCredDataMap::~CVaultCredDataMap(void)
0x18001657e  nop
0x18001657f  mov     rbx, [rsp+750h+var_700]
0x180016584  test    rbx, rbx
0x180016587  jz      short loc_1800165FF
0x180016589  mov     eax, [rsp+750h+var_6F8]
0x18001658d  test    eax, eax
0x18001658f  jz      short loc_1800165B2
0x180016591  test    rbx, rbx
0x180016594  jz      short loc_1800165B2
0x180016596  test    rax, rax
0x180016599  jz      short loc_1800165B2
0x18001659b  nop     dword ptr [rax+rax+00h]
0x1800165a0  mov     byte ptr [rbx], 0
0x1800165a3  lea     rbx, [rbx+1]
0x1800165a7  sub     rax, 1
0x1800165ab  jnz     short loc_1800165A0
0x1800165ad  mov     rbx, [rsp+750h+var_700]
0x1800165b2  mov     rax, [rsp+750h+var_708]
0x1800165b7  test    rax, rax
0x1800165ba  jz      short loc_1800165C6
0x1800165bc  mov     rcx, rbx
0x1800165bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800165c4  jmp     short loc_1800165F6
0x1800165c6  test    rbx, rbx
0x1800165c9  jz      short loc_1800165F6
0x1800165cb  mov     rcx, rbx; hMem
0x1800165ce  call    cs:__imp_LocalSize
0x1800165d4  test    rax, rax
0x1800165d7  jz      short loc_1800165ED
0x1800165d9  mov     rcx, rbx
0x1800165dc  nop     dword ptr [rax+00h]
0x1800165e0  mov     byte ptr [rcx], 0
0x1800165e3  lea     rcx, [rcx+1]
0x1800165e7  sub     rax, 1
0x1800165eb  jnz     short loc_1800165E0
0x1800165ed  mov     rcx, rbx; hMem
0x1800165f0  call    cs:__imp_LocalFree
0x1800165f6  mov     [rsp+750h+var_700], 0
0x1800165ff  mov     [rsp+750h+var_6F8], 0
0x180016607  mov     rbx, [rbp+650h+var_6D0]
0x18001660b  test    rbx, rbx
0x18001660e  jz      loc_180016E77
0x180016614  mov     eax, [rbp+650h+var_6C8]
0x180016617  test    eax, eax
0x180016619  jz      short loc_180016641
0x18001661b  test    rbx, rbx
0x18001661e  jz      short loc_180016641
0x180016620  test    rax, rax
0x180016623  jz      short loc_180016641
0x180016625  nop     word ptr [rax+rax+00000000h]
0x180016630  mov     byte ptr [rbx], 0
0x180016633  lea     rbx, [rbx+1]
0x180016637  sub     rax, 1
0x18001663b  jnz     short loc_180016630
0x18001663d  mov     rbx, [rbp+650h+var_6D0]
0x180016641  mov     rax, [rsp+750h+var_6D8]
0x180016646  test    rax, rax
0x180016649  jnz     loc_180016E3B
0x18001664f  test    rbx, rbx
0x180016652  jz      loc_180016E77
0x180016658  mov     rcx, rbx; hMem
0x18001665b  call    cs:__imp_LocalSize
0x180016661  test    rax, rax
0x180016664  jz      loc_180016E6D
0x18001666a  mov     rcx, rbx
0x18001666d  nop     dword ptr [rax]
0x180016670  mov     byte ptr [rcx], 0
0x180016673  lea     rcx, [rcx+1]
0x180016677  sub     rax, 1
0x18001667b  jnz     short loc_180016670
0x18001667d  jmp     loc_180016E6D
0x180016682  mov     eax, [rdi+40h]
0x180016685  test    eax, 0FFFF0300h
0x18001668a  jz      loc_1800168E2
0x180016690  mov     rcx, cs:WPP_GLOBAL_Control
0x180016697  lea     r10, WPP_GLOBAL_Control
0x18001669e  cmp     rcx, r10
0x1800166a1  jz      short loc_1800166D5
0x1800166a3  test    byte ptr [rcx+1Ch], 2
0x1800166a7  jz      short loc_1800166D5
0x1800166a9  mov     edx, 22h ; '"'
0x1800166ae  mov     dword ptr [rsp+750h+ReturnLength], 0FCFFh
0x1800166b6  mov     r9d, eax
0x1800166b9  lea     r8, WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids
0x1800166c0  mov     rcx, [rcx+10h]
0x1800166c4  call    WPP_SF_dd
0x1800166c9  mov     r9d, [rbp+650h+var_698]
0x1800166cd  mov     rbx, [rbp+650h+TokenHandle]
0x1800166d1  mov     rdx, [rbp+650h+var_6A8]
0x1800166d5  test    rbx, rbx
0x1800166d8  jz      short loc_18001674E
0x1800166da  test    r9d, r9d
0x1800166dd  jz      short loc_180016705
0x1800166df  test    rbx, rbx
0x1800166e2  jz      short loc_180016705
0x1800166e4  mov     eax, r9d
0x1800166e7  test    r9d, r9d
0x1800166ea  jz      short loc_180016705
0x1800166ec  nop     dword ptr [rax+00h]
0x1800166f0  mov     byte ptr [rbx], 0
  ... truncated ...
```
