# ActivateClassicITA(IMFPMPHost *,ushort const *,IStream *,_GUID const &,void * *)

- ea: `0x18019f258`
- end: `0x1801a04b6`
- name: `?ActivateClassicITA@@YAJPEAUIMFPMPHost@@PEBGPEAUIStream@@AEBU_GUID@@PEAPEAX@Z`
- size: `4702`
- prototype: `__int64 __fastcall(struct IMFPMPHost *, const unsigned __int16 *, struct IStream *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180292434`

## callees

- `0x18000320c`
- `0x18000329c`
- `0x1800053d0`
- `0x180006c50`
- `0x18001e590`
- `0x18019f258`
- `0x1802a0040`
- `0x1802a0058`
- `0x1802a04a0`
- `0x1802a0ef4`
- `0x1802ea010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019f3c6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019f51d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019f67b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019f7c1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019f92c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019fa84`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019fbcd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019fd15`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019fe80`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019ffd8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a016c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a02b9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a0413`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019f3c6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019f51d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019f67b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019f7c1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019f92c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019fa84`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019fbcd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019fd15`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019fe80`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019ffd8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a016c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a02b9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a0413`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019f341`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019f35d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019f498`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019f4b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019f5f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019f612`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019f73c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019f758`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019f8a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019f8c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019f9ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019fa1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019fb48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019fb64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019fc90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019fcac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019fdfb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019fe17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019ff53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019ff6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a00e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a0103`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a0234`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a0250`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a038e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a03aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019f341`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019f35d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019f498`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019f4b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019f5f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019f612`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019f73c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019f758`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019f8a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019f8c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019f9ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019fa1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019fb48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019fb64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019fc90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019fcac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019fdfb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019fe17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019ff53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019ff6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a00e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a0103`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a0234`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a0250`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a038e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a03aa`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18019f34d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18019f4a4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18019f602`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18019f748`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18019f8b3`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18019fa0b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18019fb54`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18019fc9c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18019fe07`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18019ff5f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1801a00f3`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1801a0240`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1801a039a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18019f34d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18019f4a4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18019f602`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18019f748`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18019f8b3`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18019fa0b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18019fb54`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18019fc9c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18019fe07`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18019ff5f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1801a00f3`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1801a0240`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1801a039a`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18019face`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18019face`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18019fed9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18019fed9`
- `MFPlat!MFSerializeAttributesToStream` at `0x18019fc16`
- `MFPlat!MFSerializeAttributesToStream` at `0x18019fc16`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019f2f2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019f373`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019f43f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019f4ca`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019f59d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019f628`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019f6e3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019f76e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019f84e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019f8d9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019f9a6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019fa31`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019faef`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019fb7a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019fc37`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019fcc2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019fda2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019fe2d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019fefa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019ff85`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801a008e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801a0119`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801a01db`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801a0266`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801a0335`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801a03c0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019f2f2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019f373`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019f43f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019f4ca`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019f59d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019f628`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019f6e3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019f76e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019f84e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019f8d9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019f9a6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019fa31`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019faef`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019fb7a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019fc37`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019fcc2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019fda2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019fe2d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019fefa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019ff85`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801a008e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801a0119`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801a01db`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801a0266`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801a0335`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801a03c0`
- `MFPlat!MFCreateAttributes` at `0x18019f2d1`
- `MFPlat!MFCreateAttributes` at `0x18019f2d1`

## pseudocode

```c
__int64 __fastcall ActivateClassicITA(
        struct IMFPMPHost *a1,
        const unsigned __int16 *a2,
        struct IStream *a3,
        const struct _GUID *a4,
        void **a5)
{
  void *v9; // r13
  __int64 v10; // rdx
  __int64 v11; // rcx
  HRESULT Instance; // ebx
  __int64 v13; // r8
  __int64 v14; // r9
  CallStackTracing *v15; // rsi
  CallStackTracing *v16; // rax
  CallStackContext *v17; // r14
  DWORD LastError; // r15d
  CallStackContext *Value; // rax
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // r9
  CallStackTracing *v23; // rcx
  CallStackTracing *v24; // rax
  __int64 v25; // rax
  __int64 v26; // rdx
  __int64 v27; // rdx
  __int64 v28; // rcx
  __int64 v29; // r8
  __int64 v30; // r9
  CallStackTracing *v31; // rsi
  CallStackTracing *v32; // rax
  CallStackContext *v33; // r14
  DWORD v34; // r15d
  CallStackContext *v35; // rax
  __int64 v36; // rdx
  __int64 v37; // r8
  __int64 v38; // r9
  CallStackTracing *v39; // rcx
  CallStackTracing *v40; // rax
  __int64 v41; // rax
  struct IStreamVtbl *lpVtbl; // rax
  __int64 v43; // rdx
  __int64 v44; // rcx
  __int64 v45; // r8
  __int64 v46; // r9
  CallStackTracing *v47; // rsi
  CallStackTracing *v48; // rax
  CallStackContext *v49; // r14
  DWORD v50; // r15d
  CallStackContext *v51; // rax
  __int64 v52; // rdx
  __int64 v53; // r8
  __int64 v54; // r9
  CallStackTracing *v55; // rcx
  CallStackTracing *v56; // rax
  __int64 v57; // rax
  __int64 v58; // rdx
  __int64 v59; // rcx
  __int64 v60; // r8
  __int64 v61; // r9
  CallStackTracing *v62; // rsi
  CallStackTracing *v63; // rax
  CallStackContext *v64; // r14
  DWORD v65; // r15d
  CallStackContext *v66; // rax
  __int64 v67; // rdx
  __int64 v68; // r8
  __int64 v69; // r9
  CallStackTracing *v70; // rcx
  CallStackTracing *v71; // rax
  __int64 v72; // rax
  __int64 v73; // rdx
  __int64 v74; // rcx
  __int64 v75; // r8
  __int64 v76; // r9
  CallStackTracing *v77; // rsi
  CallStackTracing *v78; // rax
  CallStackContext *v79; // r14
  DWORD v80; // r15d
  CallStackContext *v81; // rax
  __int64 v82; // rdx
  __int64 v83; // r8
  __int64 v84; // r9
  CallStackTracing *v85; // rcx
  CallStackTracing *v86; // rax
  __int64 v87; // rax
  __int64 v88; // rdx
  __int64 v89; // rcx
  __int64 v90; // r8
  __int64 v91; // r9
  CallStackTracing *v92; // rsi
  CallStackTracing *v93; // rax
  CallStackContext *v94; // r14
  DWORD v95; // r15d
  CallStackContext *v96; // rax
  __int64 v97; // rdx
  __int64 v98; // r8
  __int64 v99; // r9
  CallStackTracing *v100; // rcx
  CallStackTracing *v101; // rax
  __int64 v102; // rax
  __int64 v103; // rdx
  __int64 v104; // rcx
  __int64 v105; // r8
  __int64 v106; // r9
  CallStackTracing *v107; // rsi
  CallStackTracing *v108; // rax
  CallStackContext *v109; // r14
  DWORD v110; // r15d
  CallStackContext *v111; // rax
  __int64 v112; // rdx
  __int64 v113; // r8
  __int64 v114; // r9
  CallStackTracing *v115; // rcx
  CallStackTracing *v116; // rax
  __int64 v117; // rax
  __int64 v118; // rdx
  __int64 v119; // rcx
  __int64 v120; // r8
  __int64 v121; // r9
  CallStackTracing *v122; // rsi
  CallStackTracing *v123; // rax
  CallStackContext *v124; // r14
  DWORD v125; // r15d
  CallStackContext *v126; // rax
  __int64 v127; // rdx
  __int64 v128; // r8
  __int64 v129; // r9
  CallStackTracing *v130; // rcx
  CallStackTracing *v131; // rax
  __int64 v132; // rax
  __int64 v133; // rdx
  __int64 v134; // rcx
  __int64 v135; // r8
  __int64 v136; // r9
  CallStackTracing *v137; // rsi
  CallStackTracing *v138; // rax
  CallStackContext *v139; // r14
  DWORD v140; // r15d
  CallStackContext *v141; // rax
  __int64 v142; // rdx
  __int64 v143; // r8
  __int64 v144; // r9
  CallStackTracing *v145; // rcx
  CallStackTracing *v146; // rax
  __int64 v147; // rax
  __int64 v148; // rdx
  __int64 v149; // rcx
  __int64 v150; // r8
  __int64 v151; // r9
  CallStackTracing *v152; // rsi
  CallStackTracing *v153; // rax
  CallStackContext *v154; // r14
  DWORD v155; // r15d
  CallStackContext *v156; // rax
  __int64 v157; // rdx
  __int64 v158; // r8
  __int64 v159; // r9
  CallStackTracing *v160; // rcx
  CallStackTracing *v161; // rax
  __int64 v162; // rax
  __int64 v163; // rdx
  __int64 v164; // rdx
  __int64 v165; // rcx
  __int64 v166; // r8
  __int64 v167; // r9
  CallStackTracing *v168; // rsi
  CallStackTracing *v169; // rax
  CallStackContext *v170; // r14
  DWORD v171; // r15d
  CallStackContext *v172; // rax
  __int64 v173; // rdx
  __int64 v174; // r8
  __int64 v175; // r9
  CallStackTracing *v176; // rcx
  CallStackTracing *v177; // rax
  __int64 v178; // rax
  __int64 v179; // rdx
  __int64 v180; // rcx
  __int64 v181; // r8
  __int64 v182; // r9
  CallStackTracing *v183; // rsi
  CallStackTracing *v184; // rax
  CallStackContext *v185; // r14
  DWORD v186; // r15d
  CallStackContext *v187; // rax
  __int64 v188; // rdx
  __int64 v189; // r8
  __int64 v190; // r9
  CallStackTracing *v191; // rcx
  CallStackTracing *v192; // rax
  __int64 v193; // rax
  __int64 v194; // rdx
  __int64 v195; // rcx
  __int64 v196; // r8
  __int64 v197; // r9
  CallStackTracing *v198; // rsi
  CallStackTracing *v199; // rax
  CallStackContext *v200; // r14
  DWORD v201; // r15d
  CallStackContext *v202; // rax
  __int64 v203; // rdx
  __int64 v204; // r8
  __int64 v205; // r9
  CallStackTracing *v206; // rcx
  CallStackTracing *v207; // rax
  __int64 v208; // rax
  char v210[8]; // [rsp+30h] [rbp-91h] BYREF
  __int64 v211; // [rsp+38h] [rbp-89h] BYREF
  LPSTREAM ppstm; // [rsp+40h] [rbp-81h] BYREF
  unsigned int v213; // [rsp+48h] [rbp-79h] BYREF
  IMFAttributes *ppMFAttributes; // [rsp+50h] [rbp-71h] BYREF
  LPVOID ppv[3]; // [rsp+58h] [rbp-69h] BYREF
  _BYTE v216[16]; // [rsp+70h] [rbp-51h] BYREF
  size_t Size; // [rsp+80h] [rbp-41h]

  v213 = 0;
  v9 = 0;
  memset_0(v216, 0, 0x50u);
  ppv[0] = 0;
  ppMFAttributes = 0;
  ppstm = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v210, "ActivateClassicITA", 5337);
  Instance = MFCreateAttributes(&ppMFAttributes, 3u);
  if ( Instance < 0 )
  {
    v15 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v11, v10, v13, v14);
      CallStackTracing::s_wpInstance = v16;
      if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
      {
        v15 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v15 = (CallStackTracing *)&qword_18033DBA0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18033DBA0;
      }
    }
    if ( *((_BYTE *)v15 + 8) )
    {
      v17 = (CallStackTracing *)((char *)v15 + 208);
      LastError = GetLastError();
      Value = (CallStackContext *)TlsGetValue(*((_DWORD *)v15 + 3));
      if ( Value )
      {
        v17 = Value;
      }
      else if ( !GetLastError() )
      {
        v23 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v20, v21, v22);
          CallStackTracing::s_wpInstance = v24;
          if ( v24 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
          {
            v23 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v23 = (CallStackTracing *)&qword_18033DBA0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18033DBA0;
          }
        }
        v25 = (**(__int64 (__fastcall ***)(CallStackTracing *))v23)(v23);
        if ( v25 )
          v17 = (CallStackContext *)v25;
      }
      SetLastError(LastError);
      if ( *((_DWORD *)v17 + 499) != Instance )
        CallStackContext::TraceFailure(v17, "ActivateClassicITA", 5337, Instance);
    }
    if ( g_wppLevels )
    {
      v26 = 518;
LABEL_279:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v26, &WPP_5e453b2cf4a23e6c31bab848ed53fc63_Traceguids, 0, Instance);
      goto LABEL_280;
    }
    goto LABEL_280;
  }
  Instance = ((__int64 (__fastcall *)(IMFAttributes *, __int64 *, const unsigned __int16 *))ppMFAttributes->lpVtbl->SetString)(
               ppMFAttributes,
               MF_ENCRYPTEDMEDIAEXTENSIONS_ACTIVATABLE_CLASS_ID,
               a2);
  if ( Instance >= 0 )
  {
    if ( a3 )
    {
      lpVtbl = a3->lpVtbl;
      v211 = 0;
      Instance = ((__int64 (__fastcall *)(struct IStream *, _BYTE *, __int64))lpVtbl->Stat)(a3, v216, 3);
      if ( Instance < 0 )
      {
        v47 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v48 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v44, v43, v45, v46);
          CallStackTracing::s_wpInstance = v48;
          if ( v48 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v48 + 8LL))(v48, 2032) )
          {
            v47 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v47 = (CallStackTracing *)&qword_18033DBA0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18033DBA0;
          }
        }
        if ( *((_BYTE *)v47 + 8) )
        {
          v49 = (CallStackTracing *)((char *)v47 + 208);
          v50 = GetLastError();
          v51 = (CallStackContext *)TlsGetValue(*((_DWORD *)v47 + 3));
          if ( v51 )
          {
            v49 = v51;
          }
          else if ( !GetLastError() )
          {
            v55 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v56 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v52, v53, v54);
              CallStackTracing::s_wpInstance = v56;
              if ( v56
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v56 + 8LL))(v56, 2032) )
              {
                v55 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v55 = (CallStackTracing *)&qword_18033DBA0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18033DBA0;
              }
            }
            v57 = (**(__int64 (__fastcall ***)(CallStackTracing *))v55)(v55);
            if ( v57 )
              v49 = (CallStackContext *)v57;
          }
          SetLastError(v50);
          if ( *((_DWORD *)v49 + 499) != Instance )
            CallStackContext::TraceFailure(v49, "ActivateClassicITA", 5344, Instance);
        }
        if ( g_wppLevels )
        {
          v26 = 520;
          goto LABEL_279;
        }
        goto LABEL_280;
      }
      v9 = operator new((unsigned int)Size);
      if ( !v9 )
      {
        v62 = CallStackTracing::s_wpInstance;
        Instance = -2147024882;
        if ( !CallStackTracing::s_wpInstance )
        {
          v63 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v59, v58, v60, v61);
          CallStackTracing::s_wpInstance = v63;
          if ( v63 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v63 + 8LL))(v63, 2032) )
          {
            v62 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v62 = (CallStackTracing *)&qword_18033DBA0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18033DBA0;
          }
        }
        if ( *((_BYTE *)v62 + 8) )
        {
          v64 = (CallStackTracing *)((char *)v62 + 208);
          v65 = GetLastError();
          v66 = (CallStackContext *)TlsGetValue(*((_DWORD *)v62 + 3));
          if ( v66 )
          {
            v64 = v66;
          }
          else if ( !GetLastError() )
          {
            v70 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v71 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v67, v68, v69);
              CallStackTracing::s_wpInstance = v71;
              if ( v71
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v71 + 8LL))(v71, 2032) )
              {
                v70 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v70 = (CallStackTracing *)&qword_18033DBA0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18033DBA0;
              }
            }
            v72 = (**(__int64 (__fastcall ***)(CallStackTracing *))v70)(v70);
            if ( v72 )
              v64 = (CallStackContext *)v72;
          }
          SetLastError(v65);
          if ( *((_DWORD *)v64 + 499) != -2147024882 )
            CallStackContext::TraceFailure(v64, "ActivateClassicITA", 5348, -2147024882);
        }
        if ( g_wppLevels )
        {
          v26 = 521;
          goto LABEL_279;
        }
        goto LABEL_280;
      }
      ((void (__fastcall *)(struct IStream *, __int64, _QWORD, _QWORD))a3->lpVtbl->Seek)(a3, v211, 0, 0);
      Instance = ((__int64 (__fastcall *)(struct IStream *, void *, _QWORD, unsigned int *))a3->lpVtbl->Read)(
                   a3,
                   v9,
                   (unsigned int)Size,
                   &v213);
      if ( Instance < 0 )
      {
        v77 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v78 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v74, v73, v75, v76);
          CallStackTracing::s_wpInstance = v78;
          if ( v78 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v78 + 8LL))(v78, 2032) )
          {
            v77 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v77 = (CallStackTracing *)&qword_18033DBA0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18033DBA0;
          }
        }
        if ( *((_BYTE *)v77 + 8) )
        {
          v79 = (CallStackTracing *)((char *)v77 + 208);
          v80 = GetLastError();
          v81 = (CallStackContext *)TlsGetValue(*((_DWORD *)v77 + 3));
          if ( v81 )
          {
            v79 = v81;
          }
          else if ( !GetLastError() )
          {
            v85 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v86 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v82, v83, v84);
              CallStackTracing::s_wpInstance = v86;
              if ( v86
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v86 + 8LL))(v86, 2032) )
              {
                v85 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v85 = (CallStackTracing *)&qword_18033DBA0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18033DBA0;
              }
            }
            v87 = (**(__int64 (__fastcall ***)(CallStackTracing *))v85)(v85);
            if ( v87 )
              v79 = (CallStackContext *)v87;
          }
          SetLastError(v80);
          if ( *((_DWORD *)v79 + 499) != Instance )
            CallStackContext::TraceFailure(v79, "ActivateClassicITA", 5351, Instance);
        }
        if ( g_wppLevels )
        {
          v26 = 522;
          goto LABEL_279;
        }
        goto LABEL_280;
      }
      Instance = ((__int64 (__fastcall *)(IMFAttributes *, __int64 *, void *, _QWORD))ppMFAttributes->lpVtbl->SetBlob)(
                   ppMFAttributes,
                   MF_ENCRYPTEDMEDIAEXTENSIONS_INITIALIZATION_DATA,
                   v9,
                   v213);
      if ( Instance < 0 )
      {
        v92 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v93 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v89, v88, v90, v91);
          CallStackTracing::s_wpInstance = v93;
          if ( v93 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v93 + 8LL))(v93, 2032) )
          {
            v92 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v92 = (CallStackTracing *)&qword_18033DBA0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18033DBA0;
          }
        }
        if ( *((_BYTE *)v92 + 8) )
        {
          v94 = (CallStackTracing *)((char *)v92 + 208);
          v95 = GetLastError();
          v96 = (CallStackContext *)TlsGetValue(*((_DWORD *)v92 + 3));
          if ( v96 )
          {
            v94 = v96;
          }
          else if ( !GetLastError() )
          {
            v100 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v101 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v97, v98, v99);
              CallStackTracing::s_wpInstance = v101;
              if ( v101
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v101 + 8LL))(v101, 2032) )
              {
                v100 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v100 = (CallStackTracing *)&qword_18033DBA0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18033DBA0;
              }
            }
            v102 = (**(__int64 (__fastcall ***)(CallStackTracing *))v100)(v100);
            if ( v102 )
              v94 = (CallStackContext *)v102;
          }
          SetLastError(v95);
          if ( *((_DWORD *)v94 + 499) != Instance )
            CallStackContext::TraceFailure(v94, "ActivateClassicITA", 5352, Instance);
        }
        if ( g_wppLevels )
        {
          v26 = 523;
          goto LABEL_279;
        }
        goto LABEL_280;
      }
    }
    Instance = CreateStreamOnHGlobal(0, 1, &ppstm);
    if ( Instance < 0 )
    {
      v107 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v108 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v104, v103, v105, v106);
        CallStackTracing::s_wpInstance = v108;
        if ( v108 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v108 + 8LL))(v108, 2032) )
        {
          v107 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v107 = (CallStackTracing *)&qword_18033DBA0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18033DBA0;
        }
      }
      if ( *((_BYTE *)v107 + 8) )
      {
        v109 = (CallStackTracing *)((char *)v107 + 208);
        v110 = GetLastError();
        v111 = (CallStackContext *)TlsGetValue(*((_DWORD *)v107 + 3));
        if ( v111 )
        {
          v109 = v111;
        }
        else if ( !GetLastError() )
        {
          v115 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v116 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v112, v113, v114);
            CallStackTracing::s_wpInstance = v116;
            if ( v116
              && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v116 + 8LL))(v116, 2032) )
            {
              v115 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v115 = (CallStackTracing *)&qword_18033DBA0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18033DBA0;
            }
          }
          v117 = (**(__int64 (__fastcall ***)(CallStackTracing *))v115)(v115);
          if ( v117 )
            v109 = (CallStackContext *)v117;
        }
        SetLastError(v110);
        if ( *((_DWORD *)v109 + 499) != Instance )
          CallStackContext::TraceFailure(v109, "ActivateClassicITA", 5356, Instance);
      }
      if ( g_wppLevels )
      {
        v26 = 524;
        goto LABEL_279;
      }
      goto LABEL_280;
    }
    Instance = MFSerializeAttributesToStream(ppMFAttributes, 0, ppstm);
    if ( Instance < 0 )
    {
      v122 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v123 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v119, v118, v120, v121);
        CallStackTracing::s_wpInstance = v123;
        if ( v123 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v123 + 8LL))(v123, 2032) )
        {
          v122 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v122 = (CallStackTracing *)&qword_18033DBA0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18033DBA0;
        }
      }
      if ( *((_BYTE *)v122 + 8) )
      {
        v124 = (CallStackTracing *)((char *)v122 + 208);
        v125 = GetLastError();
        v126 = (CallStackContext *)TlsGetValue(*((_DWORD *)v122 + 3));
        if ( v126 )
        {
          v124 = v126;
        }
        else if ( !GetLastError() )
        {
          v130 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v131 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v127, v128, v129);
            CallStackTracing::s_wpInstance = v131;
            if ( v131
              && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v131 + 8LL))(v131, 2032) )
            {
              v130 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v130 = (CallStackTracing *)&qword_18033DBA0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18033DBA0;
            }
          }
          v132 = (**(__int64 (__fastcall ***)(CallStackTracing *))v130)(v130);
          if ( v132 )
            v124 = (CallStackContext *)v132;
        }
        SetLastError(v125);
        if ( *((_DWORD *)v124 + 499) != Instance )
          CallStackContext::TraceFailure(v124, "ActivateClassicITA", 5357, Instance);
      }
      if ( g_wppLevels )
      {
        v26 = 525;
        goto LABEL_279;
      }
      goto LABEL_280;
    }
    if ( a1 )
    {
      Instance = ((__int64 (__fastcall *)(struct IMFPMPHost *, const IID *, LPSTREAM, GUID *, LPVOID *))a1->lpVtbl->CreateObjectByCLSID)(
                   a1,
                   &MF_ENCRYPTEDMEDIAEXTENSIONS_ACTIVATE,
                   ppstm,
                   &GUID_7fee9e9a_4a89_47a6_899c_b6a53a70fb67,
                   ppv);
      if ( Instance < 0 )
      {
        v137 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v138 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v134, v133, v135, v136);
          CallStackTracing::s_wpInstance = v138;
          if ( v138 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v138 + 8LL))(v138, 2032) )
          {
            v137 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v137 = (CallStackTracing *)&qword_18033DBA0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18033DBA0;
          }
        }
        if ( *((_BYTE *)v137 + 8) )
        {
          v139 = (CallStackTracing *)((char *)v137 + 208);
          v140 = GetLastError();
          v141 = (CallStackContext *)TlsGetValue(*((_DWORD *)v137 + 3));
          if ( v141 )
          {
            v139 = v141;
          }
          else if ( !GetLastError() )
          {
            v145 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v146 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v142, v143, v144);
              CallStackTracing::s_wpInstance = v146;
              if ( v146
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v146 + 8LL))(v146, 2032) )
              {
                v145 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v145 = (CallStackTracing *)&qword_18033DBA0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18033DBA0;
              }
            }
            v147 = (**(__int64 (__fastcall ***)(CallStackTracing *))v145)(v145);
            if ( v147 )
              v139 = (CallStackContext *)v147;
          }
          SetLastError(v140);
          if ( *((_DWORD *)v139 + 499) != Instance )
            CallStackContext::TraceFailure(v139, "ActivateClassicITA", 5363, Instance);
        }
        if ( g_wppLevels )
        {
          v26 = 526;
          goto LABEL_279;
        }
        goto LABEL_280;
      }
LABEL_258:
      Instance = (*(__int64 (__fastcall **)(LPVOID, const struct _GUID *, void **))(*(_QWORD *)ppv[0] + 264LL))(
                   ppv[0],
                   a4,
                   a5);
      if ( Instance < 0 )
      {
        v198 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v199 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v195, v194, v196, v197);
          CallStackTracing::s_wpInstance = v199;
          if ( v199 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v199 + 8LL))(v199, 2032) )
          {
            v198 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v198 = (CallStackTracing *)&qword_18033DBA0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18033DBA0;
          }
        }
        if ( *((_BYTE *)v198 + 8) )
        {
          v200 = (CallStackTracing *)((char *)v198 + 208);
          v201 = GetLastError();
          v202 = (CallStackContext *)TlsGetValue(*((_DWORD *)v198 + 3));
          if ( v202 )
          {
            v200 = v202;
          }
          else if ( !GetLastError() )
          {
            v206 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v207 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v203, v204, v205);
              CallStackTracing::s_wpInstance = v207;
              if ( v207
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v207 + 8LL))(v207, 2032) )
              {
                v206 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v206 = (CallStackTracing *)&qword_18033DBA0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18033DBA0;
              }
            }
            v208 = (**(__int64 (__fastcall ***)(CallStackTracing *))v206)(v206);
            if ( v208 )
              v200 = (CallStackContext *)v208;
          }
          SetLastError(v201);
          if ( *((_DWORD *)v200 + 499) != Instance )
            CallStackContext::TraceFailure(v200, "ActivateClassicITA", 5381, Instance);
        }
        if ( g_wppLevels )
        {
          v26 = 530;
          goto LABEL_279;
        }
      }
      goto LABEL_280;
    }
    v211 = 0;
    Instance = CoCreateInstance(
                 &MF_ENCRYPTEDMEDIAEXTENSIONS_ACTIVATE,
                 0,
                 1u,
                 &GUID_7fee9e9a_4a89_47a6_899c_b6a53a70fb67,
                 ppv);
    if ( Instance >= 0 )
    {
      ppv[1] = 0;
      ((void (__fastcall *)(LPSTREAM, _QWORD, _QWORD, _QWORD))ppstm->lpVtbl->Seek)(ppstm, 0, 0, 0);
      Instance = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv[0])(ppv[0], &IID_IPersistStream, &v211);
      if ( Instance >= 0 )
      {
        Instance = (*(__int64 (__fastcall **)(__int64, LPSTREAM))(*(_QWORD *)v211 + 40LL))(v211, ppstm);
        if ( Instance >= 0 )
        {
          ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v211);
          goto LABEL_258;
        }
        v183 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v184 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v180, v179, v181, v182);
          CallStackTracing::s_wpInstance = v184;
          if ( v184 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v184 + 8LL))(v184, 2032) )
          {
            v183 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v183 = (CallStackTracing *)&qword_18033DBA0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18033DBA0;
          }
        }
        if ( *((_BYTE *)v183 + 8) )
        {
          v185 = (CallStackTracing *)((char *)v183 + 208);
          v186 = GetLastError();
          v187 = (CallStackContext *)TlsGetValue(*((_DWORD *)v183 + 3));
          if ( v187 )
          {
            v185 = v187;
          }
          else if ( !GetLastError() )
          {
            v191 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v192 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v188, v189, v190);
              CallStackTracing::s_wpInstance = v192;
              if ( v192
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v192 + 8LL))(v192, 2032) )
              {
                v191 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v191 = (CallStackTracing *)&qword_18033DBA0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18033DBA0;
              }
            }
            v193 = (**(__int64 (__fastcall ***)(CallStackTracing *))v191)(v191);
            if ( v193 )
              v185 = (CallStackContext *)v193;
          }
          SetLastError(v186);
          if ( *((_DWORD *)v185 + 499) != Instance )
            CallStackContext::TraceFailure(v185, "ActivateClassicITA", 5377, Instance);
        }
        if ( !g_wppLevels )
        {
LABEL_214:
          ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v211);
          goto LABEL_280;
        }
        v163 = 529;
      }
      else
      {
        v168 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v169 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v165, v164, v166, v167);
          CallStackTracing::s_wpInstance = v169;
          if ( v169 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v169 + 8LL))(v169, 2032) )
          {
            v168 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v168 = (CallStackTracing *)&qword_18033DBA0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18033DBA0;
          }
        }
        if ( *((_BYTE *)v168 + 8) )
        {
          v170 = (CallStackTracing *)((char *)v168 + 208);
          v171 = GetLastError();
          v172 = (CallStackContext *)TlsGetValue(*((_DWORD *)v168 + 3));
          if ( v172 )
          {
            v170 = v172;
          }
          else if ( !GetLastError() )
          {
            v176 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v177 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v173, v174, v175);
              CallStackTracing::s_wpInstance = v177;
              if ( v177
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v177 + 8LL))(v177, 2032) )
              {
                v176 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v176 = (CallStackTracing *)&qword_18033DBA0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18033DBA0;
              }
            }
            v178 = (**(__int64 (__fastcall ***)(CallStackTracing *))v176)(v176);
            if ( v178 )
              v170 = (CallStackContext *)v178;
          }
          SetLastError(v171);
          if ( *((_DWORD *)v170 + 499) != Instance )
            CallStackContext::TraceFailure(v170, "ActivateClassicITA", 5376, Instance);
        }
        if ( !g_wppLevels )
          goto LABEL_214;
        v163 = 528;
      }
    }
    else
    {
      v152 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v153 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v149, v148, v150, v151);
        CallStackTracing::s_wpInstance = v153;
        if ( v153 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v153 + 8LL))(v153, 2032) )
        {
          v152 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v152 = (CallStackTracing *)&qword_18033DBA0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18033DBA0;
        }
      }
      if ( *((_BYTE *)v152 + 8) )
      {
        v154 = (CallStackTracing *)((char *)v152 + 208);
        v155 = GetLastError();
        v156 = (CallStackContext *)TlsGetValue(*((_DWORD *)v152 + 3));
        if ( v156 )
        {
          v154 = v156;
        }
        else if ( !GetLastError() )
        {
          v160 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v161 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v157, v158, v159);
            CallStackTracing::s_wpInstance = v161;
            if ( v161
              && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v161 + 8LL))(v161, 2032) )
            {
              v160 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v160 = (CallStackTracing *)&qword_18033DBA0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18033DBA0;
            }
          }
          v162 = (**(__int64 (__fastcall ***)(CallStackTracing *))v160)(v160);
          if ( v162 )
            v154 = (CallStackContext *)v162;
        }
        SetLastError(v155);
        if ( *((_DWORD *)v154 + 499) != Instance )
          CallStackContext::TraceFailure(v154, "ActivateClassicITA", 5369, Instance);
      }
      if ( !g_wppLevels )
        goto LABEL_214;
      v163 = 527;
    }
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v163, &WPP_5e453b2cf4a23e6c31bab848ed53fc63_Traceguids, 0, Instance);
    goto LABEL_214;
  }
  v31 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v28, v27, v29, v30);
    CallStackTracing::s_wpInstance = v32;
    if ( v32 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v32 + 8LL))(v32, 2032) )
    {
      v31 = CallStackTracing::s_wpInstance;
    }
    else
    {
      v31 = (CallStackTracing *)&qword_18033DBA0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18033DBA0;
    }
  }
  if ( *((_BYTE *)v31 + 8) )
  {
    v33 = (CallStackTracing *)((char *)v31 + 208);
    v34 = GetLastError();
    v35 = (CallStackContext *)TlsGetValue(*((_DWORD *)v31 + 3));
    if ( v35 )
    {
      v33 = v35;
    }
    else if ( !GetLastError() )
    {
      v39 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v40 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v36, v37, v38);
        CallStackTracing::s_wpInstance = v40;
        if ( v40 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v40 + 8LL))(v40, 2032) )
        {
          v39 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v39 = (CallStackTracing *)&qword_18033DBA0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18033DBA0;
        }
      }
      v41 = (**(__int64 (__fastcall ***)(CallStackTracing *))v39)(v39);
      if ( v41 )
        v33 = (CallStackContext *)v41;
    }
    SetLastError(v34);
    if ( *((_DWORD *)v33 + 499) != Instance )
      CallStackContext::TraceFailure(v33, "ActivateClassicITA", 5338, Instance);
  }
  if ( g_wppLevels )
  {
    v26 = 519;
    goto LABEL_279;
  }
LABEL_280:
  operator delete(v9);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v210);
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&ppstm);
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&ppMFAttributes);
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(ppv);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18019f258  push    rbp
0x18019f25a  push    rbx
0x18019f25b  push    rsi
0x18019f25c  push    rdi
0x18019f25d  push    r12
0x18019f25f  push    r13
0x18019f261  push    r14
0x18019f263  push    r15
0x18019f265  lea     rbp, [rsp-17h]
0x18019f26a  sub     rsp, 0D8h
0x18019f271  mov     rax, cs:__security_cookie
0x18019f278  xor     rax, rsp
0x18019f27b  mov     [rbp+4Fh+var_50], rax
0x18019f27f  mov     r12, [rbp+4Fh+arg_20]
0x18019f283  xor     ebx, ebx
0x18019f285  mov     rdi, r8
0x18019f288  mov     [rbp+4Fh+var_C8], ebx
0x18019f28b  mov     r14, rdx
0x18019f28e  mov     rsi, rcx
0x18019f291  xor     edx, edx; Val
0x18019f293  lea     rcx, [rbp+4Fh+var_A0]; void *
0x18019f297  lea     r8d, [rbx+50h]; Size
0x18019f29b  mov     r15, r9
0x18019f29e  mov     r13d, ebx
0x18019f2a1  call    memset_0
0x18019f2a6  mov     r8d, 14D9h; int
0x18019f2ac  mov     [rbp+4Fh+var_B8], rbx
0x18019f2b0  lea     rdx, aActivateclassi; "ActivateClassicITA"
0x18019f2b7  mov     [rbp+4Fh+ppMFAttributes], rbx
0x18019f2bb  lea     rcx, [rsp+110h+var_E0]; this
0x18019f2c0  mov     [rsp+110h+ppstm], rbx
0x18019f2c5  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18019f2ca  lea     edx, [rbx+3]; cInitialSize
0x18019f2cd  lea     rcx, [rbp+4Fh+ppMFAttributes]; ppMFAttributes
0x18019f2d1  call    cs:__imp_MFCreateAttributes
0x18019f2d7  mov     ebx, eax
0x18019f2d9  test    eax, eax
0x18019f2db  jns     loc_18019F404
0x18019f2e1  mov     rsi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18019f2e8  mov     edi, 7F0h
0x18019f2ed  test    rsi, rsi
0x18019f2f0  jnz     short loc_18019F330
0x18019f2f2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18019f2f8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18019f2ff  mov     rcx, rax
0x18019f302  test    rax, rax
0x18019f305  jz      short loc_18019F322
0x18019f307  mov     rax, [rax]
0x18019f30a  mov     edx, edi
0x18019f30c  mov     rax, [rax+8]
0x18019f310  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019f315  test    eax, eax
0x18019f317  jz      short loc_18019F322
0x18019f319  mov     rsi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18019f320  jmp     short loc_18019F330
0x18019f322  lea     rsi, qword_18033DBA0
0x18019f329  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rsi; CallStackTracing * CallStackTracing::s_wpInstance
0x18019f330  cmp     [rsi+8], r13b
0x18019f334  jz      loc_18019F3ED
0x18019f33a  lea     r14, [rsi+0D0h]
0x18019f341  call    cs:__imp_GetLastError
0x18019f347  mov     ecx, [rsi+0Ch]; dwTlsIndex
0x18019f34a  mov     r15d, eax
0x18019f34d  call    cs:__imp_TlsGetValue
0x18019f353  test    rax, rax
0x18019f356  jz      short loc_18019F35D
0x18019f358  mov     r14, rax
0x18019f35b  jmp     short loc_18019F3C3
0x18019f35d  call    cs:__imp_GetLastError
0x18019f363  test    eax, eax
0x18019f365  jnz     short loc_18019F3C3
0x18019f367  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18019f36e  test    rcx, rcx
0x18019f371  jnz     short loc_18019F3B1
0x18019f373  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18019f379  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18019f380  mov     rcx, rax
0x18019f383  test    rax, rax
0x18019f386  jz      short loc_18019F3A3
0x18019f388  mov     rax, [rax]
0x18019f38b  mov     edx, edi
0x18019f38d  mov     rax, [rax+8]
0x18019f391  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019f396  test    eax, eax
0x18019f398  jz      short loc_18019F3A3
0x18019f39a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18019f3a1  jmp     short loc_18019F3B1
0x18019f3a3  lea     rcx, qword_18033DBA0
0x18019f3aa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18019f3b1  mov     rax, [rcx]
0x18019f3b4  mov     rax, [rax]
0x18019f3b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019f3bc  test    rax, rax
0x18019f3bf  cmovnz  r14, rax
0x18019f3c3  mov     ecx, r15d; dwErrCode
0x18019f3c6  call    cs:__imp_SetLastError
0x18019f3cc  cmp     [r14+7CCh], ebx
0x18019f3d3  jz      short loc_18019F3ED
0x18019f3d5  mov     r9d, ebx; int
0x18019f3d8  lea     rdx, aActivateclassi; "ActivateClassicITA"
0x18019f3df  mov     r8d, 14D9h; int
0x18019f3e5  mov     rcx, r14; this
0x18019f3e8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18019f3ed  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18019f3f4  jb      loc_1801A0466
0x18019f3fa  mov     edx, 206h
0x18019f3ff  jmp     loc_1801A0448
0x18019f404  mov     rcx, [rbp+4Fh+ppMFAttributes]
0x18019f408  lea     rdx, MF_ENCRYPTEDMEDIAEXTENSIONS_ACTIVATABLE_CLASS_ID
0x18019f40f  mov     r8, r14
0x18019f412  mov     rax, [rcx]
0x18019f415  mov     rax, [rax+0C8h]
0x18019f41c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019f421  xor     r14d, r14d
0x18019f424  mov     ebx, eax
0x18019f426  test    eax, eax
0x18019f428  jns     loc_18019F55B
0x18019f42e  mov     rsi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18019f435  mov     edi, 7F0h
0x18019f43a  test    rsi, rsi
0x18019f43d  jnz     short loc_18019F47D
0x18019f43f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18019f445  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18019f44c  mov     rcx, rax
0x18019f44f  test    rax, rax
0x18019f452  jz      short loc_18019F46F
0x18019f454  mov     rax, [rax]
0x18019f457  mov     edx, edi
0x18019f459  mov     rax, [rax+8]
0x18019f45d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019f462  test    eax, eax
0x18019f464  jz      short loc_18019F46F
0x18019f466  mov     rsi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18019f46d  jmp     short loc_18019F47D
0x18019f46f  lea     rsi, qword_18033DBA0
0x18019f476  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rsi; CallStackTracing * CallStackTracing::s_wpInstance
0x18019f47d  cmp     [rsi+8], r14b
0x18019f481  jz      loc_18019F544
0x18019f487  lea     r14, [rsi+0D0h]
0x18019f48e  cmp     [rsi+8], r13b
0x18019f492  jz      loc_18019F523
0x18019f498  call    cs:__imp_GetLastError
0x18019f49e  mov     ecx, [rsi+0Ch]; dwTlsIndex
0x18019f4a1  mov     r15d, eax
0x18019f4a4  call    cs:__imp_TlsGetValue
0x18019f4aa  test    rax, rax
0x18019f4ad  jz      short loc_18019F4B4
0x18019f4af  mov     r14, rax
0x18019f4b2  jmp     short loc_18019F51A
0x18019f4b4  call    cs:__imp_GetLastError
0x18019f4ba  test    eax, eax
0x18019f4bc  jnz     short loc_18019F51A
0x18019f4be  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18019f4c5  test    rcx, rcx
0x18019f4c8  jnz     short loc_18019F508
0x18019f4ca  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18019f4d0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18019f4d7  mov     rcx, rax
0x18019f4da  test    rax, rax
0x18019f4dd  jz      short loc_18019F4FA
0x18019f4df  mov     rax, [rax]
0x18019f4e2  mov     edx, edi
0x18019f4e4  mov     rax, [rax+8]
0x18019f4e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019f4ed  test    eax, eax
0x18019f4ef  jz      short loc_18019F4FA
0x18019f4f1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18019f4f8  jmp     short loc_18019F508
0x18019f4fa  lea     rcx, qword_18033DBA0
0x18019f501  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18019f508  mov     rax, [rcx]
0x18019f50b  mov     rax, [rax]
0x18019f50e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019f513  test    rax, rax
0x18019f516  cmovnz  r14, rax
0x18019f51a  mov     ecx, r15d; dwErrCode
0x18019f51d  call    cs:__imp_SetLastError
0x18019f523  cmp     [r14+7CCh], ebx
0x18019f52a  jz      short loc_18019F544
0x18019f52c  mov     r9d, ebx; int
0x18019f52f  lea     rdx, aActivateclassi; "ActivateClassicITA"
0x18019f536  mov     r8d, 14DAh; int
0x18019f53c  mov     rcx, r14; this
0x18019f53f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18019f544  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18019f54b  jb      loc_1801A0466
0x18019f551  mov     edx, 207h
0x18019f556  jmp     loc_1801A0448
0x18019f55b  test    rdi, rdi
0x18019f55e  jz      loc_18019FAC2
0x18019f564  mov     rax, [rdi]
0x18019f567  lea     rdx, [rbp+4Fh+var_A0]
0x18019f56b  mov     r8d, 3
0x18019f571  mov     [rsp+110h+var_D8], r14
0x18019f576  mov     rcx, rdi
0x18019f579  mov     rax, [rax+60h]
0x18019f57d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019f582  mov     ebx, eax
0x18019f584  test    eax, eax
0x18019f586  jns     loc_18019F6B9
0x18019f58c  mov     rsi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18019f593  mov     edi, 7F0h
0x18019f598  test    rsi, rsi
0x18019f59b  jnz     short loc_18019F5DB
0x18019f59d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18019f5a3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18019f5aa  mov     rcx, rax
0x18019f5ad  test    rax, rax
0x18019f5b0  jz      short loc_18019F5CD
0x18019f5b2  mov     rax, [rax]
0x18019f5b5  mov     edx, edi
0x18019f5b7  mov     rax, [rax+8]
0x18019f5bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019f5c0  test    eax, eax
0x18019f5c2  jz      short loc_18019F5CD
0x18019f5c4  mov     rsi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18019f5cb  jmp     short loc_18019F5DB
0x18019f5cd  lea     rsi, qword_18033DBA0
0x18019f5d4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rsi; CallStackTracing * CallStackTracing::s_wpInstance
0x18019f5db  cmp     [rsi+8], r14b
0x18019f5df  jz      loc_18019F6A2
0x18019f5e5  lea     r14, [rsi+0D0h]
0x18019f5ec  cmp     [rsi+8], r13b
0x18019f5f0  jz      loc_18019F681
0x18019f5f6  call    cs:__imp_GetLastError
0x18019f5fc  mov     ecx, [rsi+0Ch]; dwTlsIndex
0x18019f5ff  mov     r15d, eax
0x18019f602  call    cs:__imp_TlsGetValue
0x18019f608  test    rax, rax
0x18019f60b  jz      short loc_18019F612
0x18019f60d  mov     r14, rax
0x18019f610  jmp     short loc_18019F678
0x18019f612  call    cs:__imp_GetLastError
0x18019f618  test    eax, eax
0x18019f61a  jnz     short loc_18019F678
0x18019f61c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18019f623  test    rcx, rcx
0x18019f626  jnz     short loc_18019F666
0x18019f628  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18019f62e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18019f635  mov     rcx, rax
0x18019f638  test    rax, rax
0x18019f63b  jz      short loc_18019F658
0x18019f63d  mov     rax, [rax]
0x18019f640  mov     edx, edi
0x18019f642  mov     rax, [rax+8]
0x18019f646  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019f64b  test    eax, eax
0x18019f64d  jz      short loc_18019F658
0x18019f64f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18019f656  jmp     short loc_18019F666
0x18019f658  lea     rcx, qword_18033DBA0
0x18019f65f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18019f666  mov     rax, [rcx]
0x18019f669  mov     rax, [rax]
0x18019f66c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019f671  test    rax, rax
0x18019f674  cmovnz  r14, rax
0x18019f678  mov     ecx, r15d; dwErrCode
0x18019f67b  call    cs:__imp_SetLastError
0x18019f681  cmp     [r14+7CCh], ebx
0x18019f688  jz      short loc_18019F6A2
0x18019f68a  mov     r9d, ebx; int
0x18019f68d  lea     rdx, aActivateclassi; "ActivateClassicITA"
0x18019f694  mov     r8d, 14E0h; int
0x18019f69a  mov     rcx, r14; this
0x18019f69d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18019f6a2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18019f6a9  jb      loc_1801A0466
0x18019f6af  mov     edx, 208h
0x18019f6b4  jmp     loc_1801A0448
0x18019f6b9  mov     ecx, dword ptr [rbp+4Fh+Size]; Size
0x18019f6bc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18019f6c1  mov     r13, rax
0x18019f6c4  test    rax, rax
0x18019f6c7  jnz     loc_18019F7FF
0x18019f6cd  mov     rsi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18019f6d4  mov     ebx, 8007000Eh
0x18019f6d9  mov     edi, 7F0h
0x18019f6de  test    rsi, rsi
0x18019f6e1  jnz     short loc_18019F721
0x18019f6e3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18019f6e9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18019f6f0  mov     rcx, rax
0x18019f6f3  test    rax, rax
0x18019f6f6  jz      short loc_18019F713
0x18019f6f8  mov     rax, [rax]
0x18019f6fb  mov     edx, edi
0x18019f6fd  mov     rax, [rax+8]
0x18019f701  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019f706  test    eax, eax
0x18019f708  jz      short loc_18019F713
0x18019f70a  mov     rsi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18019f711  jmp     short loc_18019F721
0x18019f713  lea     rsi, qword_18033DBA0
0x18019f71a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rsi; CallStackTracing * CallStackTracing::s_wpInstance
0x18019f721  cmp     [rsi+8], r14b
0x18019f725  jz      loc_18019F7E8
0x18019f72b  cmp     byte ptr [rsi+8], 0
0x18019f72f  lea     r14, [rsi+0D0h]
  ... truncated ...
```
