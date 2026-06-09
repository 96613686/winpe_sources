# VaultDeleteCredential(VaultContext *,_GUID *,_VAULT_ITEM_ELEMENT *,_VAULT_ITEM_ELEMENT *,_VAULT_ITEM_ELEMENT *)

- ea: `0x1800358a0`
- end: `0x180037636`
- name: `?VaultDeleteCredential@@YAKPEAUVaultContext@@PEAU_GUID@@PEAU_VAULT_ITEM_ELEMENT@@22@Z`
- size: `7574`
- prototype: `__int64 __fastcall(CUserVault **, struct _GUID *, wchar_t *, struct _VAULT_ITEM_ELEMENT *, struct _VAULT_ITEM_ELEMENT *)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180012470`

## callees

- `0x180003140`
- `0x180004110`
- `0x1800091d0`
- `0x18000aac0`
- `0x180012210`
- `0x180020c80`
- `0x180021b70`
- `0x180027340`
- `0x18002d724`
- `0x18002ea00`
- `0x1800303fc`
- `0x180033d1c`
- `0x1800358a0`
- `0x180038d84`
- `0x18003a580`
- `0x18003b7b0`
- `0x18003b7d8`
- `0x18003b8a8`
- `0x18003d780`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035945`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035a10`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035aa0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035b20`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035b91`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035cb0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035d40`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035dc0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035e31`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035f20`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035fb0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036030`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800360a1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036170`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036200`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036280`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036390`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036420`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800364a0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036511`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800365d0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036660`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800366e0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036751`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036800`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036890`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036910`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036981`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036a30`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036ac0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036b32`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036bb0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036c21`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036d70`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036df0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036e60`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036ee0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036f50`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180037030`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035a10`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035aa0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035b20`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035b91`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035cb0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035d40`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035dc0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035e31`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035f20`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035fb0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036030`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800360a1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036170`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036200`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036280`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036390`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036420`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800364a0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036511`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800365d0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036660`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800366e0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036751`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036800`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036890`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036910`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036981`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036a30`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036ac0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036b32`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036bb0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036c21`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036d70`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036df0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036e60`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036ee0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036f50`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180037030`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x1800359e6`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180035a7e`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180035af8`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180035b70`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180035c86`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180035d1e`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180035d98`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180035e10`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180035ef7`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180035f8e`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180036008`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180036080`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180036146`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x1800361de`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180036258`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x1800362dc`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180036366`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x1800363fe`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180036478`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x1800364f0`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x1800365a6`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18003663e`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x1800366b8`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180036730`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x1800367d6`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18003686e`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x1800368e8`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180036960`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180036a06`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180036a98`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180036b11`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180036b88`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180036c00`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180036d4e`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180036dc7`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180036e41`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180036eb8`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180036f30`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18003700e`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x1800359e6`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180035a7e`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180035af8`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180035b70`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180035c86`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180035d1e`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180035d98`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180035e10`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180035ef7`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180035f8e`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180036008`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180036080`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180036146`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x1800361de`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180036258`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x1800362dc`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180036366`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x1800363fe`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180036478`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x1800364f0`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x1800365a6`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18003663e`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x1800366b8`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180036730`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x1800367d6`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18003686e`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x1800368e8`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180036960`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180036a06`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180036a98`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180036b11`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180036b88`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180036c00`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180036d4e`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180036dc7`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180036e41`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180036eb8`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180036f30`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18003700e`
- `ntdll!NtQueryInformationToken` at `0x18003748e`
- `ntdll!NtQueryInformationToken` at `0x18003748e`
- `ntdll!NtOpenThreadToken` at `0x18003745c`
- `ntdll!NtOpenThreadToken` at `0x18003745c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall VaultDeleteCredential(
        CUserVault **a1,
        struct _GUID *a2,
        wchar_t *a3,
        struct _VAULT_ITEM_ELEMENT *a4,
        struct _VAULT_ITEM_ELEMENT *a5)
{
  _BYTE *v8; // rsi
  unsigned int v9; // r12d
  __int64 (__fastcall *v10)(); // r13
  HLOCAL v11; // rbx
  __int64 v12; // rcx
  _BYTE *v13; // rax
  SIZE_T v14; // rdx
  _BYTE *v15; // rax
  _BYTE *v16; // rbx
  __int64 v17; // rax
  SIZE_T v18; // rcx
  _BYTE *v19; // rax
  unsigned int Schema; // edi
  _BYTE *v22; // rbx
  __int64 v23; // rax
  SIZE_T v24; // rcx
  _BYTE *v25; // rax
  _BYTE *v26; // rbx
  __int64 v27; // rax
  SIZE_T v28; // rcx
  _BYTE *v29; // rax
  HLOCAL v30; // rbx
  __int64 v31; // rcx
  _BYTE *v32; // rax
  SIZE_T v33; // rdx
  _BYTE *v34; // rax
  _BYTE *v35; // rbx
  __int64 v36; // rax
  SIZE_T v37; // rcx
  _BYTE *v38; // rax
  __int64 v39; // rax
  _BYTE *v40; // rbx
  __int64 v41; // rax
  SIZE_T v42; // rcx
  _BYTE *v43; // rax
  _BYTE *v44; // rbx
  __int64 v45; // rax
  SIZE_T v46; // rcx
  _BYTE *v47; // rax
  HLOCAL v48; // rbx
  __int64 v49; // rcx
  _BYTE *v50; // rax
  SIZE_T v51; // rdx
  _BYTE *v52; // rax
  _BYTE *v53; // rbx
  __int64 v54; // rax
  SIZE_T v55; // rcx
  _BYTE *v56; // rax
  struct _GUID *v57; // rdx
  _BYTE *v58; // rbx
  __int64 v59; // rax
  SIZE_T v60; // rcx
  _BYTE *v61; // rax
  _BYTE *v62; // rbx
  __int64 v63; // rax
  SIZE_T v64; // rcx
  _BYTE *v65; // rax
  HLOCAL v66; // rbx
  __int64 v67; // rcx
  _BYTE *v68; // rax
  SIZE_T v69; // rdx
  _BYTE *v70; // rax
  _BYTE *v71; // rbx
  __int64 v72; // rax
  __int64 (__fastcall *v73)(); // rax
  SIZE_T v74; // rcx
  _BYTE *v75; // rax
  _BYTE *v76; // rbx
  __int64 v77; // rax
  SIZE_T v78; // rcx
  _BYTE *v79; // rax
  _BYTE *v80; // rbx
  __int64 v81; // rax
  SIZE_T v82; // rcx
  _BYTE *v83; // rax
  HLOCAL v84; // rbx
  __int64 v85; // rcx
  _BYTE *v86; // rax
  SIZE_T v87; // rdx
  _BYTE *v88; // rax
  __int64 v89; // rax
  SIZE_T v90; // rcx
  _BYTE *v91; // rax
  _BYTE *v92; // rdi
  unsigned int v93; // esi
  _BYTE *v94; // rbx
  __int64 v95; // rax
  SIZE_T v96; // rcx
  _BYTE *v97; // rax
  _BYTE *v98; // rbx
  __int64 v99; // rax
  SIZE_T v100; // rcx
  _BYTE *v101; // rax
  __int64 v102; // rcx
  _BYTE *v103; // rax
  SIZE_T v104; // rdx
  _BYTE *v105; // rax
  _BYTE *v106; // rbx
  __int64 v107; // rax
  SIZE_T v108; // rcx
  _BYTE *v109; // rax
  unsigned int v110; // edi
  _BYTE *v111; // rbx
  __int64 v112; // rax
  SIZE_T v113; // rcx
  _BYTE *v114; // rax
  _BYTE *v115; // rbx
  __int64 v116; // rax
  SIZE_T v117; // rcx
  _BYTE *v118; // rax
  HLOCAL v119; // rbx
  __int64 v120; // rcx
  _BYTE *v121; // rax
  SIZE_T v122; // rdx
  _BYTE *v123; // rax
  _BYTE *v124; // rbx
  __int64 v125; // rax
  SIZE_T v126; // rcx
  _BYTE *v127; // rax
  void *v128; // rdx
  unsigned int CallerPackageSid; // edi
  _BYTE *v130; // rbx
  __int64 v131; // rax
  SIZE_T v132; // rcx
  _BYTE *v133; // rax
  HLOCAL v134; // rbx
  __int64 v135; // rcx
  _BYTE *v136; // rax
  SIZE_T v137; // rdx
  _BYTE *v138; // rax
  _BYTE *v139; // rbx
  __int64 v140; // rax
  SIZE_T v141; // rcx
  _BYTE *v142; // rax
  HLOCAL v143; // rbx
  __int64 v144; // rcx
  _BYTE *v145; // rax
  SIZE_T v146; // rdx
  _BYTE *v147; // rax
  _BYTE *v148; // rbx
  __int64 v149; // rax
  SIZE_T v150; // rcx
  _BYTE *v151; // rax
  CVaultPackageId *v152; // rcx
  CVaultPackageId *v153; // rdi
  __int64 v154; // rbx
  __int64 v155; // rax
  __int64 v156; // rdx
  unsigned int v157; // edi
  _BYTE *v158; // rbx
  __int64 v159; // rax
  SIZE_T v160; // rcx
  _BYTE *v161; // rax
  _BYTE *v162; // rcx
  SIZE_T v163; // rax
  _BYTE *v164; // rdx
  _BYTE *v165; // rbx
  __int64 v166; // rax
  SIZE_T v167; // rax
  _BYTE *v168; // rcx
  HLOCAL v169; // rbx
  __int64 v170; // rcx
  _BYTE *v171; // rax
  SIZE_T v172; // rax
  _BYTE *v173; // rdx
  _BYTE *v174; // rbx
  __int64 v175; // rax
  SIZE_T v176; // rax
  _BYTE *v177; // rcx
  _BYTE *v178; // rbx
  unsigned int v179; // esi
  _BYTE *v180; // rdi
  __int64 v181; // rax
  SIZE_T v182; // rax
  _BYTE *v183; // rcx
  _BYTE *v184; // rcx
  __int64 v185; // rax
  __int64 v186; // rcx
  _BYTE *v187; // rax
  __int64 v188; // rax
  _BYTE *v189; // rcx
  __int64 v190; // rax
  __int64 v191; // rcx
  _BYTE *v192; // rax
  unsigned int v193; // edi
  _BYTE *v194; // rcx
  __int64 v195; // rax
  __int64 v196; // rcx
  _BYTE *v197; // rax
  _BYTE *v198; // rcx
  _BYTE *v199; // rcx
  __int64 v200; // rax
  __int64 v201; // rcx
  _BYTE *v202; // rax
  unsigned int v203; // r8d
  int v204; // r9d
  unsigned __int16 *v205; // rax
  _BYTE *v206; // rcx
  __int64 v207; // rax
  __int64 v208; // rcx
  _BYTE *v209; // rax
  HLOCAL v210; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v211; // [rsp+50h] [rbp-B0h]
  BOOL (__stdcall *v212)(HANDLE); // [rsp+58h] [rbp-A8h] BYREF
  HLOCAL hMem; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v214; // [rsp+68h] [rbp-98h]
  __int64 (__fastcall *v215)(); // [rsp+70h] [rbp-90h] BYREF
  HLOCAL v216; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v217; // [rsp+80h] [rbp-80h]
  __int64 (__fastcall *v218)(); // [rsp+88h] [rbp-78h]
  HLOCAL v219; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v220; // [rsp+98h] [rbp-68h]
  int v221; // [rsp+A0h] [rbp-60h] BYREF
  ULONG ReturnLength; // [rsp+A4h] [rbp-5Ch] BYREF
  int TokenInformation; // [rsp+A8h] [rbp-58h] BYREF
  wchar_t *v224; // [rsp+B0h] [rbp-50h] BYREF
  __int64 (__fastcall *v225)(); // [rsp+B8h] [rbp-48h] BYREF
  HLOCAL v226; // [rsp+C0h] [rbp-40h] BYREF
  unsigned int v227; // [rsp+C8h] [rbp-38h]
  int v228; // [rsp+D0h] [rbp-30h] BYREF
  CUserVault *v229; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v230; // [rsp+E0h] [rbp-20h] BYREF
  int v231; // [rsp+E8h] [rbp-18h]
  int v232; // [rsp+ECh] [rbp-14h]
  CVaultPackageId *v233; // [rsp+F0h] [rbp-10h]
  __int128 v234; // [rsp+100h] [rbp+0h] BYREF
  char v235[48]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v236[96]; // [rsp+140h] [rbp+40h] BYREF
  unsigned __int16 v237[256]; // [rsp+1A0h] [rbp+A0h] BYREF
  wchar_t Filename[256]; // [rsp+3A0h] [rbp+2A0h] BYREF

  v224 = a3;
  v215 = AutoDereference<IVaultKeyManager>;
  v216 = 0;
  v217 = 0;
  v218 = AutoDereference<IVaultKeyManager>;
  v219 = 0;
  v220 = 0;
  v210 = 0;
  v211 = 0;
  v8 = 0;
  v226 = 0;
  v9 = 0;
  v227 = 0;
  v10 = AutoDereference<IVaultKeyManager>;
  v225 = AutoDereference<IVaultKeyManager>;
  v221 = *((unsigned __int8 *)a1 + 85);
  v228 = 0;
  TokenInformation = 0;
  ReturnLength = 0;
  v212 = CloseHandle;
  hMem = 0;
  v214 = 0;
  Filename[0] = 0;
  v229 = *a1;
  v237[0] = 0;
  LODWORD(v234) = CUserVault::GetVaultStore(v229, (struct IVaultStore **)&v219, 0);
  if ( (_DWORD)v234 )
  {
    v214 = 0;
    v211 = 0;
    v11 = v219;
    if ( v219 )
    {
      if ( v220 )
      {
        v12 = v220;
        v13 = v219;
        do
        {
          *v13++ = 0;
          --v12;
        }
        while ( v12 );
      }
      if ( v218 )
      {
        ((void (__fastcall *)(HLOCAL))v218)(v11);
      }
      else if ( v11 )
      {
        v14 = LocalSize(v11);
        if ( v14 )
        {
          v15 = v11;
          do
          {
            *v15++ = 0;
            --v14;
          }
          while ( v14 );
        }
        LocalFree(v11);
      }
    }
    v16 = v216;
    if ( v216 )
    {
      v17 = v217;
      if ( v217 )
      {
        do
        {
          *v16++ = 0;
          --v17;
        }
        while ( v17 );
        v16 = v216;
      }
      if ( v215 )
      {
        ((void (__fastcall *)(_BYTE *))v215)(v16);
      }
      else if ( v16 )
      {
        v18 = LocalSize(v16);
        if ( v18 )
        {
          v19 = v16;
          do
          {
            *v19++ = 0;
            --v18;
          }
          while ( v18 );
        }
        LocalFree(v16);
      }
    }
    return (unsigned int)v234;
  }
  Schema = VaultGetSchema(*a1, a2, (struct IVaultSchema **)&v210, 1u);
  if ( Schema )
  {
    if ( a2 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF__guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids, a2);
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids);
    }
    v22 = hMem;
    if ( hMem )
    {
      v23 = v214;
      if ( v214 )
      {
        do
        {
          *v22++ = 0;
          --v23;
        }
        while ( v23 );
        v22 = hMem;
      }
      if ( v212 )
      {
        ((void (__fastcall *)(_BYTE *))v212)(v22);
        hMem = 0;
      }
      else
      {
        if ( v22 )
        {
          v24 = LocalSize(v22);
          if ( v24 )
          {
            v25 = v22;
            do
            {
              *v25++ = 0;
              --v24;
            }
            while ( v24 );
          }
          LocalFree(v22);
        }
        hMem = 0;
      }
    }
    v214 = 0;
    v26 = v210;
    if ( v210 )
    {
      v27 = v211;
      if ( v211 )
      {
        do
        {
          *v26++ = 0;
          --v27;
        }
        while ( v27 );
        v26 = v210;
      }
      if ( AutoDereference<IVaultKeyManager> )
      {
        ((void (__fastcall *)(_BYTE *))AutoDereference<IVaultKeyManager>)(v26);
      }
      else if ( v26 )
      {
        v28 = LocalSize(v26);
        if ( v28 )
        {
          v29 = v26;
          do
          {
            *v29++ = 0;
            --v28;
          }
          while ( v28 );
        }
        LocalFree(v26);
      }
      v210 = 0;
    }
    v211 = 0;
    v30 = v219;
    if ( v219 )
    {
      if ( v220 )
      {
        v31 = v220;
        v32 = v219;
        do
        {
          *v32++ = 0;
          --v31;
        }
        while ( v31 );
      }
      if ( v218 )
      {
        ((void (__fastcall *)(HLOCAL))v218)(v30);
      }
      else if ( v30 )
      {
        v33 = LocalSize(v30);
        if ( v33 )
        {
          v34 = v30;
          do
          {
            *v34++ = 0;
            --v33;
          }
          while ( v33 );
        }
        LocalFree(v30);
      }
    }
    v35 = v216;
    if ( v216 )
    {
      v36 = v217;
      if ( v217 )
      {
        do
        {
          *v35++ = 0;
          --v36;
        }
        while ( v36 );
        v35 = v216;
      }
      if ( v215 )
      {
        ((void (__fastcall *)(_BYTE *))v215)(v35);
      }
      else if ( v35 )
      {
        v37 = LocalSize(v35);
        if ( v37 )
        {
          v38 = v35;
          do
          {
            *v38++ = 0;
            --v37;
          }
          while ( v37 );
        }
        LocalFree(v35);
      }
    }
    return Schema;
  }
  v39 = (*(__int64 (__fastcall **)(HLOCAL))(*(_QWORD *)v210 + 160LL))(v210);
  if ( !(unsigned int)VaultAccessCheck(1, v39, &v221) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids, 1168);
    v40 = hMem;
    if ( hMem )
    {
      v41 = v214;
      if ( v214 )
      {
        do
        {
          *v40++ = 0;
          --v41;
        }
        while ( v41 );
        v40 = hMem;
      }
      if ( v212 )
      {
        ((void (__fastcall *)(_BYTE *))v212)(v40);
        hMem = 0;
      }
      else
      {
        if ( v40 )
        {
          v42 = LocalSize(v40);
          if ( v42 )
          {
            v43 = v40;
            do
            {
              *v43++ = 0;
              --v42;
            }
            while ( v42 );
          }
          LocalFree(v40);
        }
        hMem = 0;
      }
    }
    v214 = 0;
    v44 = v210;
    if ( v210 )
    {
      v45 = v211;
      if ( v211 )
      {
        do
        {
          *v44++ = 0;
          --v45;
        }
        while ( v45 );
        v44 = v210;
      }
      if ( AutoDereference<IVaultKeyManager> )
      {
        ((void (__fastcall *)(_BYTE *))AutoDereference<IVaultKeyManager>)(v44);
      }
      else if ( v44 )
      {
        v46 = LocalSize(v44);
        if ( v46 )
        {
          v47 = v44;
          do
          {
            *v47++ = 0;
            --v46;
          }
          while ( v46 );
        }
        LocalFree(v44);
      }
      v210 = 0;
    }
    v211 = 0;
    v48 = v219;
    if ( v219 )
    {
      if ( v220 )
      {
        v49 = v220;
        v50 = v219;
        do
        {
          *v50++ = 0;
          --v49;
        }
        while ( v49 );
      }
      if ( v218 )
      {
        ((void (__fastcall *)(HLOCAL))v218)(v48);
      }
      else if ( v48 )
      {
        v51 = LocalSize(v48);
        if ( v51 )
        {
          v52 = v48;
          do
          {
            *v52++ = 0;
            --v51;
          }
          while ( v51 );
        }
        LocalFree(v48);
      }
    }
    v53 = v216;
    if ( v216 )
    {
      v54 = v217;
      if ( v217 )
      {
        do
        {
          *v53++ = 0;
          --v54;
        }
        while ( v54 );
        v53 = v216;
      }
      if ( v215 )
      {
        ((void (__fastcall *)(_BYTE *))v215)(v53);
      }
      else if ( v53 )
      {
        v55 = LocalSize(v53);
        if ( v55 )
        {
          v56 = v53;
          do
          {
            *v56++ = 0;
            --v55;
          }
          while ( v55 );
        }
        LocalFree(v53);
      }
    }
    return 1168;
  }
  v234 = *(_OWORD *)(*(__int64 (__fastcall **)(HLOCAL, __int128 *))(*(_QWORD *)v210 + 24LL))(v210, &v234);
  if ( !CUserVault::IsCredmanVault(v229, v57) )
  {
    if ( a5 )
    {
      v110 = VaultValidatePackageSidElement(a5);
      if ( v110 )
      {
        v111 = hMem;
        if ( hMem )
        {
          v112 = v214;
          if ( v214 )
          {
            do
            {
              *v111++ = 0;
              --v112;
            }
            while ( v112 );
            v111 = hMem;
          }
          if ( v212 )
          {
            ((void (__fastcall *)(_BYTE *))v212)(v111);
            hMem = 0;
          }
          else
          {
            if ( v111 )
            {
              v113 = LocalSize(v111);
              if ( v113 )
              {
                v114 = v111;
                do
                {
                  *v114++ = 0;
                  --v113;
                }
                while ( v113 );
              }
              LocalFree(v111);
            }
            hMem = 0;
          }
        }
        v214 = 0;
        v115 = v210;
        if ( v210 )
        {
          v116 = v211;
          if ( v211 )
          {
            do
            {
              *v115++ = 0;
              --v116;
            }
            while ( v116 );
            v115 = v210;
          }
          if ( AutoDereference<IVaultKeyManager> )
          {
            ((void (__fastcall *)(_BYTE *))AutoDereference<IVaultKeyManager>)(v115);
          }
          else if ( v115 )
          {
            v117 = LocalSize(v115);
            if ( v117 )
            {
              v118 = v115;
              do
              {
                *v118++ = 0;
                --v117;
              }
              while ( v117 );
            }
            LocalFree(v115);
          }
          v210 = 0;
        }
        v211 = 0;
        v119 = v219;
        if ( v219 )
        {
          if ( v220 )
          {
            v120 = v220;
            v121 = v219;
            do
            {
              *v121++ = 0;
              --v120;
            }
            while ( v120 );
          }
          if ( v218 )
          {
            ((void (__fastcall *)(HLOCAL))v218)(v119);
          }
          else if ( v119 )
          {
            v122 = LocalSize(v119);
            if ( v122 )
            {
              v123 = v119;
              do
              {
                *v123++ = 0;
                --v122;
              }
              while ( v122 );
            }
            LocalFree(v119);
          }
        }
        v124 = v216;
        if ( v216 )
        {
          v125 = v217;
          if ( v217 )
          {
            do
            {
              *v124++ = 0;
              --v125;
            }
            while ( v125 );
            v124 = v216;
          }
          if ( v215 )
          {
            ((void (__fastcall *)(_BYTE *))v215)(v124);
          }
          else if ( v124 )
          {
            v126 = LocalSize(v124);
            if ( v126 )
            {
              v127 = v124;
              do
              {
                *v127++ = 0;
                --v126;
              }
              while ( v126 );
            }
            LocalFree(v124);
          }
        }
        return v110;
      }
      v128 = (void *)*((_QWORD *)a5 + 2);
    }
    else
    {
      CallerPackageSid = VaultGetCallerPackageSid((struct CVaultSid **)&v226);
      if ( CallerPackageSid )
      {
        v130 = hMem;
        if ( hMem )
        {
          v131 = v214;
          if ( v214 )
          {
            do
            {
              *v130++ = 0;
              --v131;
            }
            while ( v131 );
            v130 = hMem;
          }
          if ( v212 )
          {
            ((void (__fastcall *)(_BYTE *))v212)(v130);
            hMem = 0;
          }
          else
          {
            if ( v130 )
            {
              v132 = LocalSize(v130);
              if ( v132 )
              {
                v133 = v130;
                do
                {
                  *v133++ = 0;
                  --v132;
                }
                while ( v132 );
              }
              LocalFree(v130);
            }
            hMem = 0;
          }
        }
        v214 = 0;
        v134 = v226;
        if ( v226 )
        {
          if ( v227 )
          {
            v135 = v227;
            v136 = v226;
            do
            {
              *v136++ = 0;
              --v135;
            }
            while ( v135 );
          }
          if ( v225 )
          {
            ((void (__fastcall *)(HLOCAL))v225)(v134);
          }
          else if ( v134 )
          {
            v137 = LocalSize(v134);
            if ( v137 )
            {
              v138 = v134;
              do
              {
                *v138++ = 0;
                --v137;
              }
              while ( v137 );
            }
            LocalFree(v134);
          }
        }
        v139 = v210;
        if ( v210 )
        {
          v140 = v211;
          if ( v211 )
          {
            do
            {
              *v139++ = 0;
              --v140;
            }
            while ( v140 );
            v139 = v210;
          }
          if ( AutoDereference<IVaultKeyManager> )
          {
            ((void (__fastcall *)(_BYTE *))AutoDereference<IVaultKeyManager>)(v139);
          }
          else if ( v139 )
          {
            v141 = LocalSize(v139);
            if ( v141 )
            {
              v142 = v139;
              do
              {
                *v142++ = 0;
                --v141;
              }
              while ( v141 );
            }
            LocalFree(v139);
          }
          v210 = 0;
        }
        v211 = 0;
        v143 = v219;
        if ( v219 )
        {
          if ( v220 )
          {
            v144 = v220;
            v145 = v219;
            do
            {
              *v145++ = 0;
              --v144;
            }
            while ( v144 );
          }
          if ( v218 )
          {
            ((void (__fastcall *)(HLOCAL))v218)(v143);
          }
          else if ( v143 )
          {
            v146 = LocalSize(v143);
            if ( v146 )
            {
              v147 = v143;
              do
              {
                *v147++ = 0;
                --v146;
              }
              while ( v146 );
            }
            LocalFree(v143);
          }
        }
        v148 = v216;
        if ( v216 )
        {
          v149 = v217;
          if ( v217 )
          {
            do
            {
              *v148++ = 0;
              --v149;
            }
            while ( v149 );
            v148 = v216;
          }
          if ( v215 )
          {
            ((void (__fastcall *)(_BYTE *))v215)(v148);
          }
          else if ( v148 )
          {
            v150 = LocalSize(v148);
            if ( v150 )
            {
              v151 = v148;
              do
              {
                *v151++ = 0;
                --v150;
              }
              while ( v150 );
            }
            LocalFree(v148);
          }
        }
        return CallerPackageSid;
      }
      v8 = v226;
      v128 = (void *)*((_QWORD *)v226 + 2);
      v9 = v227;
      v10 = v225;
    }
    v152 = CVaultPackageId::CVaultPackageId((CVaultPackageId *)v235, v128);
    v230 = 8;
    v232 = 0;
    v153 = 0;
    if ( *((_DWORD *)v152 + 10) )
      v153 = v152;
    v231 = *((_DWORD *)v152 + 10);
    v154 = (*(__int64 (__fastcall **)(HLOCAL))(*(_QWORD *)v210 + 112LL))(v210);
    v155 = (*(__int64 (__fastcall **)(HLOCAL))(*(_QWORD *)v210 + 120LL))(v210);
    v233 = v153;
    v157 = ComputeItemDigest(&v234, (__int64)v224, v155, (__int64)a4, v154, (__int64)&v230, (__int64)v236);
    if ( v157 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids, v157);
      v158 = hMem;
      if ( hMem )
      {
        v159 = v214;
        if ( v214 )
        {
          do
          {
            *v158++ = 0;
            --v159;
          }
          while ( v159 );
          v158 = hMem;
        }
        if ( v212 )
        {
          ((void (__fastcall *)(_BYTE *))v212)(v158);
        }
        else if ( v158 )
        {
          v160 = LocalSize(v158);
          if ( v160 )
          {
            v161 = v158;
            do
            {
              *v161++ = 0;
              --v160;
            }
            while ( v160 );
          }
          LocalFree(v158);
        }
        hMem = 0;
      }
      v214 = 0;
      if ( v8 )
      {
        if ( v9 )
        {
          v156 = v9;
          v162 = v8;
          do
          {
            *v162++ = 0;
            --v156;
          }
          while ( v156 );
        }
        if ( v10 )
        {
          ((void (__fastcall *)(_BYTE *, __int64))v10)(v8, v156);
        }
        else
        {
          v163 = LocalSize(v8);
          if ( v163 )
          {
            v164 = v8;
            do
            {
              *v164++ = 0;
              --v163;
            }
            while ( v163 );
          }
          LocalFree(v8);
        }
      }
      v165 = v210;
      if ( v210 )
      {
        v166 = v211;
        if ( v211 )
        {
          do
          {
            *v165++ = 0;
            --v166;
          }
          while ( v166 );
          v165 = v210;
        }
        if ( AutoDereference<IVaultKeyManager> )
        {
          ((void (__fastcall *)(_BYTE *))AutoDereference<IVaultKeyManager>)(v165);
        }
        else if ( v165 )
        {
          v167 = LocalSize(v165);
          if ( v167 )
          {
            v168 = v165;
            do
            {
              *v168++ = 0;
              --v167;
            }
            while ( v167 );
          }
          LocalFree(v165);
        }
        v210 = 0;
      }
      v211 = 0;
      v169 = v219;
      if ( v219 )
      {
        if ( v220 )
        {
          v170 = v220;
          v171 = v219;
          do
          {
            *v171++ = 0;
            --v170;
          }
          while ( v170 );
        }
        if ( v218 )
        {
          ((void (__fastcall *)(HLOCAL))v218)(v169);
        }
        else if ( v169 )
        {
          v172 = LocalSize(v169);
          if ( v172 )
          {
            v173 = v169;
            do
            {
              *v173++ = 0;
              --v172;
            }
            while ( v172 );
          }
          LocalFree(v169);
        }
      }
      v174 = v216;
      if ( v216 )
      {
        v175 = v217;
        if ( v217 )
        {
          do
          {
            *v174++ = 0;
            --v175;
          }
          while ( v175 );
          v174 = v216;
        }
        if ( v215 )
        {
          ((void (__fastcall *)(_BYTE *))v215)(v174);
        }
        else if ( v174 )
        {
          v176 = LocalSize(v174);
          if ( v176 )
          {
            v177 = v174;
            do
            {
              *v177++ = 0;
              --v176;
            }
            while ( v176 );
          }
          LocalFree(v174);
        }
      }
      return v157;
    }
    v178 = v219;
    v179 = (*(__int64 (__fastcall **)(HLOCAL, _BYTE *, HLOCAL *))(*(_QWORD *)v219 + 168LL))(v219, v236, &v216);
    if ( v179 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          26,
          (unsigned int)WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids,
          (unsigned int)v236,
          v179);
      v180 = hMem;
      if ( hMem )
      {
        v181 = v214;
        if ( v214 )
        {
          do
          {
            *v180++ = 0;
            --v181;
          }
          while ( v181 );
          v180 = hMem;
        }
        if ( v212 )
        {
          ((void (__fastcall *)(_BYTE *))v212)(v180);
        }
        else if ( v180 )
        {
          v182 = LocalSize(v180);
          if ( v182 )
          {
            v183 = v180;
            do
            {
              *v183++ = 0;
              --v182;
            }
            while ( v182 );
          }
          LocalFree(v180);
        }
        hMem = 0;
      }
      v214 = 0;
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v225);
      v184 = v210;
      if ( v210 )
      {
        v185 = v211;
        if ( v211 )
        {
          do
          {
            *v184++ = 0;
            --v185;
          }
          while ( v185 );
          v184 = v210;
        }
        if ( AutoDereference<IVaultKeyManager> )
          AutoDereference<IVaultKeyManager>();
        else
          VaultFreeInternal(v184);
        v210 = 0;
      }
      v211 = 0;
      if ( v178 )
      {
        if ( v220 )
        {
          v186 = v220;
          v187 = v178;
          do
          {
            *v187++ = 0;
            --v186;
          }
          while ( v186 );
        }
        if ( v218 )
          ((void (__fastcall *)(_BYTE *))v218)(v178);
        else
          VaultFreeInternal(v178);
      }
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v215);
      return v179;
    }
    v188 = (*(__int64 (__fastcall **)(HLOCAL))(*(_QWORD *)v216 + 208LL))(v216);
    if ( !(unsigned int)VaultAccessCheck(0, v188, &v221) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          27,
          (unsigned int)WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids,
          (unsigned int)v236,
          144);
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v212);
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v225);
      v189 = v210;
      if ( v210 )
      {
        v190 = v211;
        if ( v211 )
        {
          do
          {
            *v189++ = 0;
            --v190;
          }
          while ( v190 );
          v189 = v210;
        }
        if ( AutoDereference<IVaultKeyManager> )
          AutoDereference<IVaultKeyManager>();
        else
          VaultFreeInternal(v189);
        v210 = 0;
      }
      v211 = 0;
      if ( v178 )
      {
        if ( v220 )
        {
          v191 = v220;
          v192 = v178;
          do
          {
            *v192++ = 0;
            --v191;
          }
          while ( v191 );
        }
        if ( v218 )
          ((void (__fastcall *)(_BYTE *))v218)(v178);
        else
          VaultFreeInternal(v178);
      }
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v215);
      return 1168;
    }
    v193 = (*(__int64 (__fastcall **)(HLOCAL, int *))(*(_QWORD *)v216 + 248LL))(v216, &v228);
    if ( v193 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          28,
          (unsigned int)WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids,
          (unsigned int)v236,
          v193);
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v212);
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v225);
      v194 = v210;
      if ( v210 )
      {
        v195 = v211;
        if ( v211 )
        {
          do
          {
            *v194++ = 0;
            --v195;
          }
          while ( v195 );
          v194 = v210;
        }
        if ( AutoDereference<IVaultKeyManager> )
          AutoDereference<IVaultKeyManager>();
        else
          VaultFreeInternal(v194);
        v210 = 0;
      }
      v211 = 0;
      if ( !v178 )
        goto LABEL_516;
      if ( v220 )
      {
        v196 = v220;
        v197 = v178;
        do
        {
          *v197++ = 0;
          --v196;
        }
        while ( v196 );
      }
      v198 = v178;
      if ( !v218 )
      {
        VaultFreeInternal(v178);
        goto LABEL_516;
      }
    }
    else
    {
      v193 = (*(__int64 (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v178 + 160LL))(v178, v236);
      if ( !v193 )
      {
        if ( NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 1u, &hMem) >= 0 )
        {
          ReturnLength = 4;
          if ( NtQueryInformationToken(hMem, TokenIsAppContainer, &TokenInformation, 4u, &ReturnLength) >= 0 )
          {
            if ( TokenInformation )
              PopulateCallerAccountInfo(hMem, 0, Filename);
            LogAppName(Filename, v237, v203);
          }
          if ( (unsigned int)dword_18005F0C0 > 5
            && (qword_18005F0D0 & 0x400000000000LL) != 0
            && (qword_18005F0D8 & 0x400000000000LL) == qword_18005F0D8 )
          {
            v205 = L"NULL";
            if ( v237[0] )
              v205 = v237;
            v229 = (CUserVault *)v205;
            v224 = Filename;
            *(_QWORD *)&v234 = v236;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
              (unsigned int)v237,
              (unsigned int)byte_180054D39,
              v203,
              v204,
              (__int64)&v234,
              (__int64)&v224,
              (__int64)&v229);
          }
        }
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v212);
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v225);
        v206 = v210;
        if ( v210 )
        {
          v207 = v211;
          if ( v211 )
          {
            do
            {
              *v206++ = 0;
              --v207;
            }
            while ( v207 );
            v206 = v210;
          }
          if ( AutoDereference<IVaultKeyManager> )
            AutoDereference<IVaultKeyManager>();
          else
            VaultFreeInternal(v206);
          v210 = 0;
        }
        v211 = 0;
        if ( v178 )
        {
          if ( v220 )
          {
            v208 = v220;
            v209 = v178;
            do
            {
              *v209++ = 0;
              --v208;
            }
            while ( v208 );
          }
          if ( v218 )
            ((void (__fastcall *)(_BYTE *))v218)(v178);
          else
            VaultFreeInternal(v178);
        }
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v215);
        return 0;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          29,
          (unsigned int)WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids,
          (unsigned int)v236,
          v193);
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v212);
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v225);
      v199 = v210;
      if ( v210 )
      {
        v200 = v211;
        if ( v211 )
        {
          do
          {
            *v199++ = 0;
            --v200;
          }
          while ( v200 );
          v199 = v210;
        }
        if ( AutoDereference<IVaultKeyManager> )
          AutoDereference<IVaultKeyManager>();
        else
          VaultFreeInternal(v199);
        v210 = 0;
      }
      v211 = 0;
      if ( !v178 )
      {
LABEL_516:
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v215);
        return v193;
      }
      if ( v220 )
      {
        v201 = v220;
        v202 = v178;
        do
        {
          *v202++ = 0;
          --v201;
        }
        while ( v201 );
      }
      v198 = v178;
      if ( !v218 )
      {
        VaultFreeInternal(v178);
        goto LABEL_516;
      }
    }
    ((void (__fastcall *)(_BYTE *))v218)(v198);
    goto LABEL_516;
  }
  if ( !a4 )
  {
    v58 = hMem;
    if ( hMem )
    {
      v59 = v214;
      if ( v214 )
      {
        do
        {
          *v58++ = 0;
          --v59;
        }
        while ( v59 );
        v58 = hMem;
      }
      if ( v212 )
      {
        ((void (__fastcall *)(_BYTE *))v212)(v58);
        hMem = 0;
      }
      else
      {
        if ( v58 )
        {
          v60 = LocalSize(v58);
          if ( v60 )
          {
            v61 = v58;
            do
            {
              *v61++ = 0;
              --v60;
            }
            while ( v60 );
          }
          LocalFree(v58);
        }
        hMem = 0;
      }
    }
    v214 = 0;
    v62 = v210;
    if ( v210 )
    {
      v63 = v211;
      if ( v211 )
      {
        do
        {
          *v62++ = 0;
          --v63;
        }
        while ( v63 );
        v62 = v210;
      }
      if ( AutoDereference<IVaultKeyManager> )
      {
        ((void (__fastcall *)(_BYTE *))AutoDereference<IVaultKeyManager>)(v62);
      }
      else if ( v62 )
      {
        v64 = LocalSize(v62);
        if ( v64 )
        {
          v65 = v62;
          do
          {
            *v65++ = 0;
            --v64;
          }
          while ( v64 );
        }
        LocalFree(v62);
      }
      v210 = 0;
    }
    v211 = 0;
    v66 = v219;
    if ( v219 )
    {
      if ( v220 )
      {
        v67 = v220;
        v68 = v219;
        do
        {
          *v68++ = 0;
          --v67;
        }
        while ( v67 );
      }
      if ( v218 )
      {
        ((void (__fastcall *)(HLOCAL))v218)(v66);
      }
      else if ( v66 )
      {
        v69 = LocalSize(v66);
        if ( v69 )
        {
          v70 = v66;
          do
          {
            *v70++ = 0;
            --v69;
          }
          while ( v69 );
        }
        LocalFree(v66);
      }
    }
    v71 = v216;
    if ( !v216 )
      return 87;
    v72 = v217;
    if ( v217 )
    {
      do
      {
        *v71++ = 0;
        --v72;
      }
      while ( v72 );
      v71 = v216;
    }
    v73 = v215;
    if ( !v215 )
    {
      if ( v71 )
      {
        v74 = LocalSize(v71);
        if ( v74 )
        {
          v75 = v71;
          do
          {
            *v75++ = 0;
            --v74;
          }
          while ( v74 );
        }
LABEL_224:
        LocalFree(v71);
        return 87;
      }
      return 87;
    }
    goto LABEL_219;
  }
  if ( *((_DWORD *)a4 + 2) != 7 )
  {
    v76 = hMem;
    if ( hMem )
    {
      v77 = v214;
      if ( v214 )
      {
        do
        {
          *v76++ = 0;
          --v77;
        }
        while ( v77 );
        v76 = hMem;
      }
      if ( v212 )
      {
        ((void (__fastcall *)(_BYTE *))v212)(v76);
        hMem = 0;
      }
      else
      {
        if ( v76 )
        {
          v78 = LocalSize(v76);
          if ( v78 )
          {
            v79 = v76;
            do
            {
              *v79++ = 0;
              --v78;
            }
            while ( v78 );
          }
          LocalFree(v76);
        }
        hMem = 0;
      }
    }
    v214 = 0;
    v80 = v210;
    if ( v210 )
    {
      v81 = v211;
      if ( v211 )
      {
        do
        {
          *v80++ = 0;
          --v81;
        }
        while ( v81 );
        v80 = v210;
      }
      if ( AutoDereference<IVaultKeyManager> )
      {
        ((void (__fastcall *)(_BYTE *))AutoDereference<IVaultKeyManager>)(v80);
      }
      else if ( v80 )
      {
        v82 = LocalSize(v80);
        if ( v82 )
        {
          v83 = v80;
          do
          {
            *v83++ = 0;
            --v82;
          }
          while ( v82 );
        }
        LocalFree(v80);
      }
      v210 = 0;
    }
    v211 = 0;
    v84 = v219;
    if ( v219 )
    {
      if ( v220 )
      {
        v85 = v220;
        v86 = v219;
        do
        {
          *v86++ = 0;
          --v85;
        }
        while ( v85 );
      }
      if ( v218 )
      {
        ((void (__fastcall *)(HLOCAL))v218)(v84);
      }
      else if ( v84 )
      {
        v87 = LocalSize(v84);
        if ( v87 )
        {
          v88 = v84;
          do
          {
            *v88++ = 0;
            --v87;
          }
          while ( v87 );
        }
        LocalFree(v84);
      }
    }
    v71 = v216;
    if ( !v216 )
      return 87;
    v89 = v217;
    if ( v217 )
    {
      do
      {
        *v71++ = 0;
        --v89;
      }
      while ( v89 );
      v71 = v216;
    }
    v73 = v215;
    if ( !v215 )
    {
      if ( v71 )
      {
        v90 = LocalSize(v71);
        if ( v90 )
        {
          v91 = v71;
          do
          {
            *v91++ = 0;
            --v90;
          }
          while ( v90 );
        }
        goto LABEL_224;
      }
      return 87;
    }
LABEL_219:
    ((void (__fastcall *)(_BYTE *))v73)(v71);
    return 87;
  }
  v92 = v219;
  v93 = (*(__int64 (__fastcall **)(HLOCAL, struct _GUID *, wchar_t *, struct _VAULT_ITEM_ELEMENT *, struct _VAULT_ITEM_ELEMENT *))(*(_QWORD *)v219 + 152LL))(
          v219,
          a2,
          v224,
          a4,
          a5);
  v94 = hMem;
  if ( hMem )
  {
    v95 = v214;
    if ( v214 )
    {
      do
      {
        *v94++ = 0;
        --v95;
      }
      while ( v95 );
      v94 = hMem;
    }
    if ( v212 )
    {
      ((void (__fastcall *)(_BYTE *))v212)(v94);
      hMem = 0;
    }
    else
    {
      if ( v94 )
      {
        v96 = LocalSize(v94);
        if ( v96 )
        {
          v97 = v94;
          do
          {
            *v97++ = 0;
            --v96;
          }
          while ( v96 );
        }
        LocalFree(v94);
      }
      hMem = 0;
    }
  }
  v214 = 0;
  v98 = v210;
  if ( v210 )
  {
    v99 = v211;
    if ( v211 )
    {
      do
      {
        *v98++ = 0;
        --v99;
      }
      while ( v99 );
      v98 = v210;
    }
    if ( AutoDereference<IVaultKeyManager> )
    {
      ((void (__fastcall *)(_BYTE *))AutoDereference<IVaultKeyManager>)(v98);
    }
    else if ( v98 )
    {
      v100 = LocalSize(v98);
      if ( v100 )
      {
        v101 = v98;
        do
        {
          *v101++ = 0;
          --v100;
        }
        while ( v100 );
      }
      LocalFree(v98);
    }
    v210 = 0;
  }
  v211 = 0;
  if ( v92 )
  {
    if ( v220 )
    {
      v102 = v220;
      v103 = v92;
      do
      {
        *v103++ = 0;
        --v102;
      }
      while ( v102 );
    }
    if ( v218 )
    {
      ((void (__fastcall *)(_BYTE *))v218)(v92);
    }
    else
    {
      v104 = LocalSize(v92);
      if ( v104 )
      {
        v105 = v92;
        do
        {
          *v105++ = 0;
          --v104;
        }
        while ( v104 );
      }
      LocalFree(v92);
    }
  }
  v106 = v216;
  if ( v216 )
  {
    v107 = v217;
    if ( v217 )
    {
      do
      {
        *v106++ = 0;
        --v107;
      }
      while ( v107 );
      v106 = v216;
    }
    if ( v215 )
    {
      ((void (__fastcall *)(_BYTE *))v215)(v106);
    }
    else if ( v106 )
    {
      v108 = LocalSize(v106);
      if ( v108 )
      {
        v109 = v106;
        do
        {
          *v109++ = 0;
          --v108;
        }
        while ( v108 );
      }
      LocalFree(v106);
    }
  }
  return v93;
}

```

## disassembly

```asm
0x1800358a0  push    rbp
0x1800358a2  push    rbx
0x1800358a3  push    rsi
0x1800358a4  push    rdi
0x1800358a5  push    r12
0x1800358a7  push    r13
0x1800358a9  push    r14
0x1800358ab  push    r15
0x1800358ad  lea     rbp, [rsp-4B8h]
0x1800358b5  sub     rsp, 5B8h
0x1800358bc  mov     rax, cs:__security_cookie
0x1800358c3  xor     rax, rsp
0x1800358c6  mov     [rbp+4F0h+var_50], rax
0x1800358cd  mov     r15, r9
0x1800358d0  mov     [rbp+4F0h+var_540], r8
0x1800358d4  mov     r14, rdx
0x1800358d7  mov     rdi, rcx
0x1800358da  mov     rbx, [rbp+4F0h+arg_20]
0x1800358e1  lea     rax, ??$AutoDereference@UIVaultKeyManager@@@@YAXPEAUIVaultKeyManager@@@Z
0x1800358e8  mov     [rsp+5F0h+var_580], rax
0x1800358ed  xor     edx, edx
0x1800358ef  mov     [rsp+5F0h+var_578], rdx
0x1800358f4  mov     [rbp+4F0h+var_570], edx
0x1800358f7  lea     rax, ??$AutoDereference@UIVaultKeyManager@@@@YAXPEAUIVaultKeyManager@@@Z
0x1800358fe  mov     [rbp+4F0h+var_568], rax
0x180035902  mov     [rbp+4F0h+var_560], rdx
0x180035906  mov     [rbp+4F0h+var_558], edx
0x180035909  lea     rax, ??$AutoDereference@UIVaultKeyManager@@@@YAXPEAUIVaultKeyManager@@@Z
0x180035910  mov     [rsp+5F0h+var_5B0], rax
0x180035915  mov     [rsp+5F0h+var_5A8], rdx
0x18003591a  mov     [rsp+5F0h+var_5A0], edx
0x18003591e  mov     esi, edx
0x180035920  mov     [rbp+4F0h+var_530], rdx
0x180035924  mov     r12d, edx
0x180035927  mov     [rbp+4F0h+var_528], edx
0x18003592a  lea     r13, ??$AutoDereference@UIVaultKeyManager@@@@YAXPEAUIVaultKeyManager@@@Z
0x180035931  mov     [rbp+4F0h+var_538], r13
0x180035935  movzx   eax, byte ptr [rcx+55h]
0x180035939  mov     [rbp+4F0h+var_550], eax
0x18003593c  mov     [rbp+4F0h+var_520], edx
0x18003593f  mov     [rbp+4F0h+TokenInformation], edx
0x180035942  mov     [rbp+4F0h+var_54C], edx
0x180035945  mov     rax, cs:__imp_CloseHandle
0x18003594c  mov     [rsp+5F0h+var_598], rax
0x180035951  mov     [rsp+5F0h+hMem], rdx
0x180035956  mov     [rsp+5F0h+var_588], edx
0x18003595a  mov     [rbp+4F0h+Filename], dx
0x180035961  mov     rcx, [rcx]; this
0x180035964  mov     [rbp+4F0h+var_518], rcx
0x180035968  mov     [rbp+4F0h+var_450], dx
0x18003596f  xor     r8d, r8d; unsigned __int8
0x180035972  lea     rdx, [rbp+4F0h+var_560]; struct IVaultStore **
0x180035976  call    ?GetVaultStore@CUserVault@@QEAAKPEAPEAUIVaultStore@@E@Z
0x18003597b  mov     dword ptr [rbp+4F0h+var_4F0], eax
0x18003597e  test    eax, eax
0x180035980  jz      loc_180035BA0
0x180035986  mov     rbx, [rsp+5F0h+hMem]
0x18003598b  test    rbx, rbx
0x18003598e  jz      loc_180035A20
0x180035994  mov     eax, [rsp+5F0h+var_588]
0x180035998  test    eax, eax
0x18003599a  jz      short loc_1800359C2
0x18003599c  test    rbx, rbx
0x18003599f  jz      short loc_1800359C2
0x1800359a1  test    rax, rax
0x1800359a4  jz      short loc_1800359C2
0x1800359a6  nop     word ptr [rax+rax+00000000h]
0x1800359b0  mov     byte ptr [rbx], 0
0x1800359b3  lea     rbx, [rbx+1]
0x1800359b7  sub     rax, 1
0x1800359bb  jnz     short loc_1800359B0
0x1800359bd  mov     rbx, [rsp+5F0h+hMem]
0x1800359c2  mov     rax, [rsp+5F0h+var_598]
0x1800359c7  test    rax, rax
0x1800359ca  jz      short loc_1800359DE
0x1800359cc  mov     rcx, rbx
0x1800359cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800359d4  xor     r14d, r14d
0x1800359d7  mov     [rsp+5F0h+hMem], r14
0x1800359dc  jmp     short loc_180035A23
0x1800359de  test    rbx, rbx
0x1800359e1  jz      short loc_180035A16
0x1800359e3  mov     rcx, rbx; hMem
0x1800359e6  call    cs:__imp_LocalSize
0x1800359ec  mov     rcx, rax
0x1800359ef  test    rax, rax
0x1800359f2  jz      short loc_180035A0D
0x1800359f4  mov     rax, rbx
0x1800359f7  nop     word ptr [rax+rax+00000000h]
0x180035a00  mov     byte ptr [rax], 0
0x180035a03  lea     rax, [rax+1]
0x180035a07  sub     rcx, 1
0x180035a0b  jnz     short loc_180035A00
0x180035a0d  mov     rcx, rbx; hMem
0x180035a10  call    cs:__imp_LocalFree
0x180035a16  xor     r14d, r14d
0x180035a19  mov     [rsp+5F0h+hMem], r14
0x180035a1e  jmp     short loc_180035A23
0x180035a20  xor     r14d, r14d
0x180035a23  mov     [rsp+5F0h+var_588], r14d
0x180035a28  mov     rbx, [rsp+5F0h+var_5A8]
0x180035a2d  test    rbx, rbx
0x180035a30  jz      short loc_180035AAB
0x180035a32  mov     eax, [rsp+5F0h+var_5A0]
0x180035a36  test    eax, eax
0x180035a38  jz      short loc_180035A62
0x180035a3a  test    rbx, rbx
0x180035a3d  jz      short loc_180035A62
0x180035a3f  test    rax, rax
0x180035a42  jz      short loc_180035A62
0x180035a44  nop     dword ptr [rax+00h]
0x180035a48  nop     dword ptr [rax+rax+00000000h]
0x180035a50  mov     byte ptr [rbx], 0
0x180035a53  lea     rbx, [rbx+1]
0x180035a57  sub     rax, 1
0x180035a5b  jnz     short loc_180035A50
0x180035a5d  mov     rbx, [rsp+5F0h+var_5A8]
0x180035a62  mov     rax, [rsp+5F0h+var_5B0]
0x180035a67  test    rax, rax
0x180035a6a  jz      short loc_180035A76
0x180035a6c  mov     rcx, rbx
0x180035a6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035a74  jmp     short loc_180035AA6
0x180035a76  test    rbx, rbx
0x180035a79  jz      short loc_180035AA6
0x180035a7b  mov     rcx, rbx; hMem
0x180035a7e  call    cs:__imp_LocalSize
0x180035a84  mov     rcx, rax
0x180035a87  test    rax, rax
0x180035a8a  jz      short loc_180035A9D
0x180035a8c  mov     rax, rbx
0x180035a8f  nop
0x180035a90  mov     byte ptr [rax], 0
0x180035a93  lea     rax, [rax+1]
0x180035a97  sub     rcx, 1
0x180035a9b  jnz     short loc_180035A90
0x180035a9d  mov     rcx, rbx; hMem
0x180035aa0  call    cs:__imp_LocalFree
0x180035aa6  mov     [rsp+5F0h+var_5A8], r14
0x180035aab  mov     [rsp+5F0h+var_5A0], r14d
0x180035ab0  mov     rbx, [rbp+4F0h+var_560]
0x180035ab4  test    rbx, rbx
0x180035ab7  jz      short loc_180035B27
0x180035ab9  mov     eax, [rbp+4F0h+var_558]
0x180035abc  test    eax, eax
0x180035abe  jz      short loc_180035ADD
0x180035ac0  test    rbx, rbx
0x180035ac3  jz      short loc_180035ADD
0x180035ac5  mov     ecx, eax
0x180035ac7  test    eax, eax
0x180035ac9  jz      short loc_180035ADD
0x180035acb  mov     rax, rbx
0x180035ace  xchg    ax, ax
0x180035ad0  mov     byte ptr [rax], 0
0x180035ad3  lea     rax, [rax+1]
0x180035ad7  sub     rcx, 1
0x180035adb  jnz     short loc_180035AD0
0x180035add  mov     rax, [rbp+4F0h+var_568]
0x180035ae1  test    rax, rax
0x180035ae4  jz      short loc_180035AF0
0x180035ae6  mov     rcx, rbx
0x180035ae9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035aee  jmp     short loc_180035B27
0x180035af0  test    rbx, rbx
0x180035af3  jz      short loc_180035B27
0x180035af5  mov     rcx, rbx; hMem
0x180035af8  call    cs:__imp_LocalSize
0x180035afe  mov     rdx, rax
0x180035b01  test    rax, rax
0x180035b04  jz      short loc_180035B1D
0x180035b06  mov     rax, rbx
0x180035b09  nop     dword ptr [rax+00000000h]
0x180035b10  mov     byte ptr [rax], 0
0x180035b13  lea     rax, [rax+1]
0x180035b17  sub     rdx, 1
0x180035b1b  jnz     short loc_180035B10
0x180035b1d  mov     rcx, rbx; hMem
0x180035b20  call    cs:__imp_LocalFree
0x180035b26  nop
0x180035b27  mov     rbx, [rsp+5F0h+var_578]
0x180035b2c  test    rbx, rbx
0x180035b2f  jz      short loc_180035B98
0x180035b31  mov     eax, [rbp+4F0h+var_570]
0x180035b34  test    eax, eax
0x180035b36  jz      short loc_180035B54
0x180035b38  test    rbx, rbx
0x180035b3b  jz      short loc_180035B54
0x180035b3d  test    rax, rax
0x180035b40  jz      short loc_180035B54
0x180035b42  mov     byte ptr [rbx], 0
0x180035b45  lea     rbx, [rbx+1]
0x180035b49  sub     rax, 1
0x180035b4d  jnz     short loc_180035B42
0x180035b4f  mov     rbx, [rsp+5F0h+var_578]
0x180035b54  mov     rax, [rsp+5F0h+var_580]
0x180035b59  test    rax, rax
0x180035b5c  jz      short loc_180035B68
0x180035b5e  mov     rcx, rbx
0x180035b61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035b66  jmp     short loc_180035B98
0x180035b68  test    rbx, rbx
0x180035b6b  jz      short loc_180035B98
0x180035b6d  mov     rcx, rbx; hMem
0x180035b70  call    cs:__imp_LocalSize
0x180035b76  mov     rcx, rax
0x180035b79  test    rax, rax
0x180035b7c  jz      short loc_180035B8E
0x180035b7e  mov     rax, rbx
0x180035b81  mov     byte ptr [rax], 0
0x180035b84  lea     rax, [rax+1]
0x180035b88  sub     rcx, 1
0x180035b8c  jnz     short loc_180035B81
0x180035b8e  mov     rcx, rbx; hMem
0x180035b91  call    cs:__imp_LocalFree
0x180035b97  nop
0x180035b98  mov     eax, dword ptr [rbp+4F0h+var_4F0]
0x180035b9b  jmp     loc_180037613
0x180035ba0  mov     r9b, 1; unsigned __int8
0x180035ba3  lea     r8, [rsp+5F0h+var_5A8]; struct IVaultSchema **
0x180035ba8  mov     rdx, r14; struct _GUID *
0x180035bab  mov     rcx, [rdi]; this
0x180035bae  call    ?VaultGetSchema@@YAKPEAVCUserVault@@PEBU_GUID@@PEAPEAUIVaultSchema@@E@Z
0x180035bb3  mov     edi, eax
0x180035bb5  test    eax, eax
0x180035bb7  jz      loc_180035E3F
0x180035bbd  test    r14, r14
0x180035bc0  jz      short loc_180035BF5
0x180035bc2  lea     rax, WPP_GLOBAL_Control
0x180035bc9  mov     rcx, cs:WPP_GLOBAL_Control
0x180035bd0  cmp     rcx, rax
0x180035bd3  jz      short loc_180035C24
0x180035bd5  test    byte ptr [rcx+1Ch], 8
0x180035bd9  jz      short loc_180035C24
0x180035bdb  mov     edx, 16h
0x180035be0  mov     r9, r14
0x180035be3  lea     r8, WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids
0x180035bea  mov     rcx, [rcx+10h]
0x180035bee  call    WPP_SF__guid_
0x180035bf3  jmp     short loc_180035C24
0x180035bf5  lea     rax, WPP_GLOBAL_Control
0x180035bfc  mov     rcx, cs:WPP_GLOBAL_Control
0x180035c03  cmp     rcx, rax
0x180035c06  jz      short loc_180035C24
0x180035c08  test    byte ptr [rcx+1Ch], 8
0x180035c0c  jz      short loc_180035C24
0x180035c0e  mov     edx, 17h
0x180035c13  lea     r8, WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids
0x180035c1a  mov     rcx, [rcx+10h]
0x180035c1e  call    WPP_SF_
0x180035c23  nop
0x180035c24  mov     rbx, [rsp+5F0h+hMem]
0x180035c29  test    rbx, rbx
0x180035c2c  jz      loc_180035CC0
0x180035c32  mov     eax, [rsp+5F0h+var_588]
0x180035c36  test    eax, eax
0x180035c38  jz      short loc_180035C62
0x180035c3a  test    rbx, rbx
0x180035c3d  jz      short loc_180035C62
0x180035c3f  test    rax, rax
0x180035c42  jz      short loc_180035C62
0x180035c44  nop     dword ptr [rax+00h]
0x180035c48  nop     dword ptr [rax+rax+00000000h]
0x180035c50  mov     byte ptr [rbx], 0
0x180035c53  lea     rbx, [rbx+1]
0x180035c57  sub     rax, 1
0x180035c5b  jnz     short loc_180035C50
0x180035c5d  mov     rbx, [rsp+5F0h+hMem]
0x180035c62  mov     rax, [rsp+5F0h+var_598]
0x180035c67  test    rax, rax
0x180035c6a  jz      short loc_180035C7E
0x180035c6c  mov     rcx, rbx
0x180035c6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035c74  xor     r14d, r14d
0x180035c77  mov     [rsp+5F0h+hMem], r14
0x180035c7c  jmp     short loc_180035CC3
0x180035c7e  test    rbx, rbx
0x180035c81  jz      short loc_180035CB6
0x180035c83  mov     rcx, rbx; hMem
0x180035c86  call    cs:__imp_LocalSize
0x180035c8c  mov     rcx, rax
0x180035c8f  test    rax, rax
0x180035c92  jz      short loc_180035CAD
0x180035c94  mov     rax, rbx
0x180035c97  nop     word ptr [rax+rax+00000000h]
0x180035ca0  mov     byte ptr [rax], 0
0x180035ca3  lea     rax, [rax+1]
0x180035ca7  sub     rcx, 1
0x180035cab  jnz     short loc_180035CA0
0x180035cad  mov     rcx, rbx; hMem
0x180035cb0  call    cs:__imp_LocalFree
0x180035cb6  xor     r14d, r14d
0x180035cb9  mov     [rsp+5F0h+hMem], r14
0x180035cbe  jmp     short loc_180035CC3
0x180035cc0  xor     r14d, r14d
0x180035cc3  mov     [rsp+5F0h+var_588], r14d
0x180035cc8  mov     rbx, [rsp+5F0h+var_5A8]
0x180035ccd  test    rbx, rbx
0x180035cd0  jz      short loc_180035D4B
0x180035cd2  mov     eax, [rsp+5F0h+var_5A0]
0x180035cd6  test    eax, eax
  ... truncated ...
```
