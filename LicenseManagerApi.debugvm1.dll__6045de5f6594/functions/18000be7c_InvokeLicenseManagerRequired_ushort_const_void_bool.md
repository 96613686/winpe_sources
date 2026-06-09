# InvokeLicenseManagerRequired(ushort const *,void *,bool)

- ea: `0x18000be7c`
- end: `0x18000e52d`
- name: `?InvokeLicenseManagerRequired@@YA_NPEBGPEAX_N@Z`
- size: `9905`
- prototype: `char __fastcall(const unsigned __int16 *, PSID pSid, unsigned __int8)`
- caller_count: `6`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000f060`
- `0x18000fdd0`
- `0x180010420`
- `0x180010710`
- `0x1800109a0`
- `0x180010cc0`

## callees

- `0x180001960`
- `0x1800029d3`
- `0x18000be7c`
- `0x18000e534`
- `0x180011470`
- `0x180013010`

## import_xrefs

- `api-ms-win-crt-time-l1-1-0!_time64` at `0x18000c20b`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x18000c20b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000d350`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000d350`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d389`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d389`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c19a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c1b7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c1e1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c1fa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cd26`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cea0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ced1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cf02`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cf25`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cf73`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cfa4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cfd4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d004`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d025`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d1f7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d6d8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d706`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d734`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d755`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d801`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d82e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d85b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d87c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000de34`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e104`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e12d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e151`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e175`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e191`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e1b2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e1d3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e200`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e224`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e248`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e264`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e285`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c19a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c1b7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c1e1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c1fa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cd26`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cea0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ced1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cf02`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cf25`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cf73`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cfa4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cfd4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d004`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d025`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d1f7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d6d8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d706`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d734`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d755`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d801`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d82e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d85b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d87c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000de34`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e104`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e12d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e151`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e175`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e191`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e1b2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e1d3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e200`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e224`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e248`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e264`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e285`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bedb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bf8c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c12a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c18c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c1a9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c1d3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c1ec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c857`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c8f5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ccdb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cd18`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cd4b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cd9d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ce46`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ce90`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cec1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cef2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cf15`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cf64`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cf94`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cfc4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cff4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d016`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d08b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d1e7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d2c1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d540`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d59e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d5fa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d653`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d6c9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d6f7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d725`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d746`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d7f2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d81f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d84c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d86d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d8c6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000de24`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000dffd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e0f6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e11f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e143`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e167`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e183`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e1a4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e1c5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e1f2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e216`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e23a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e256`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e277`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bedb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bf8c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c12a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c18c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c1a9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c1d3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c1ec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c857`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c8f5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ccdb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cd18`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cd4b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cd9d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ce46`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ce90`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cec1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cef2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cf15`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cf64`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cf94`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cfc4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cff4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d016`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d08b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d1e7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d2c1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d540`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d59e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d5fa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d653`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d6c9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d6f7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d725`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d746`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d7f2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d81f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d84c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d86d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d8c6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000de24`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000dffd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e0f6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e11f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e143`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e167`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e183`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e1a4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e1c5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e1f2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e216`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e23a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e256`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e277`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000bef3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000bf9b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000c13b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000c868`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000c904`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000cced`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000cd5c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000cdb1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ce59`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000d09c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000d2d2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000d556`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000d5b1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000d60d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000d662`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000d8d5`

## string_xrefs

- `0x18000d342`: `ntdll.dll`

## pseudocode

```c
char __fastcall InvokeLicenseManagerRequired(const unsigned __int16 *a1, PSID pSid, unsigned __int8 a3)
{
  const unsigned __int16 *v3; // rbx
  unsigned __int8 v4; // di
  HANDLE ProcessHeap; // rax
  _OWORD *v6; // rax
  void *v7; // r12
  void *v8; // r13
  int v9; // r14d
  HANDLE v10; // rax
  _QWORD *v11; // rax
  unsigned __int64 v12; // rdi
  const unsigned __int16 *v13; // rax
  __int64 v14; // r8
  __int64 v15; // r9
  unsigned int v16; // eax
  unsigned int v17; // r8d
  char *v18; // r15
  int v19; // r9d
  __int64 v20; // r9
  _WORD *v21; // rax
  unsigned int v22; // edx
  unsigned int v23; // eax
  unsigned int v24; // edx
  unsigned int v25; // eax
  unsigned int v26; // ecx
  unsigned int v27; // eax
  unsigned int v28; // edx
  __int64 v29; // r14
  HANDLE v30; // rax
  char *v31; // rax
  HANDLE v32; // rax
  HANDLE v33; // rax
  HANDLE v34; // rax
  HANDLE v35; // rax
  int v36; // r8d
  char *v38; // rdx
  int v39; // ecx
  unsigned int v40; // eax
  char *v41; // r9
  char *v42; // r9
  unsigned int v43; // r14d
  _DWORD *v44; // rdx
  unsigned int i; // r9d
  unsigned int v46; // eax
  unsigned __int64 v47; // rdx
  unsigned int j; // ecx
  unsigned int v49; // eax
  unsigned int v50; // edx
  _DWORD *v51; // r9
  unsigned int k; // ecx
  unsigned int v53; // eax
  const unsigned __int16 *v54; // rax
  __int64 v55; // r10
  unsigned int v56; // esi
  unsigned __int64 v57; // r11
  int v58; // eax
  unsigned int v59; // r11d
  unsigned int v60; // r11d
  __int64 v61; // rcx
  unsigned int *v62; // r10
  unsigned int v63; // ecx
  __int64 v64; // rdx
  _WORD *v65; // rax
  unsigned __int64 v66; // r10
  __int64 v67; // r9
  unsigned int v68; // r9d
  unsigned int v69; // eax
  _DWORD *v70; // rdx
  unsigned int m; // r10d
  unsigned int v72; // eax
  unsigned int v73; // r14d
  unsigned int v74; // esi
  __int64 v75; // r14
  DWORD *v76; // rdx
  unsigned int jj; // ecx
  unsigned int v78; // eax
  unsigned int kk; // r9d
  _DWORD *v80; // rdx
  unsigned int v81; // ecx
  unsigned int v82; // eax
  unsigned int v83; // r9d
  unsigned int v84; // eax
  __int64 v85; // r14
  HANDLE v86; // rax
  unsigned __int8 *v87; // rax
  unsigned __int8 *v88; // rsi
  __int64 v89; // r14
  unsigned int *v90; // rbx
  HANDLE v91; // rax
  _BYTE *v92; // rdx
  unsigned __int8 v93; // al
  unsigned __int64 n; // rcx
  unsigned __int8 *v95; // r15
  _BYTE *v96; // r13
  unsigned int v97; // r10d
  int v98; // edx
  int v99; // edi
  int v100; // ebx
  int v101; // edi
  int v102; // ebx
  int v103; // r8d
  unsigned int v104; // r10d
  int v105; // r11d
  int v106; // r9d
  int v107; // r10d
  unsigned int v108; // r8d
  int v109; // edx
  int v110; // r8d
  int v111; // r9d
  int v112; // r10d
  int v113; // r8d
  unsigned int v114; // r9d
  unsigned int v115; // r10d
  int v116; // r8d
  int v117; // r9d
  int v118; // r10d
  int v119; // r8d
  int v120; // r9d
  int v121; // r11d
  int v122; // r8d
  int v123; // r10d
  unsigned int v124; // r9d
  int v125; // r8d
  HANDLE v126; // rax
  _DWORD *v127; // rax
  int v128; // r14d
  HANDLE v129; // rax
  HANDLE v130; // rax
  void *v131; // rcx
  _QWORD *v132; // rax
  HANDLE v133; // rax
  _OWORD *v134; // rcx
  HANDLE v135; // rax
  _QWORD *v136; // rax
  HANDLE v137; // rax
  HANDLE v138; // rax
  HANDLE v139; // rax
  HANDLE v140; // rax
  HANDLE v141; // rax
  int v142; // eax
  unsigned int v143; // ecx
  unsigned int v144; // edx
  unsigned int v145; // ecx
  unsigned int v146; // ebx
  HANDLE v147; // rax
  char *v148; // rax
  char *v149; // rcx
  char *v150; // rcx
  char *v151; // r9
  int v152; // r11d
  char *v153; // r10
  HANDLE v154; // rax
  char *v155; // rax
  char *v156; // rdx
  unsigned int v157; // r8d
  unsigned int v158; // eax
  unsigned int v159; // ebx
  HANDLE v160; // rax
  unsigned int *v161; // rax
  bool v162; // zf
  __int128 v163; // rax
  char *v164; // rcx
  int LastError; // eax
  bool v166; // sf
  FARPROC ProcAddress; // rax
  unsigned int v168; // r8d
  char *v169; // rax
  __int64 v170; // r9
  unsigned int *v171; // rcx
  char *v172; // rax
  unsigned int v173; // r10d
  SIZE_T v174; // rcx
  unsigned int v175; // ecx
  unsigned int *v176; // rax
  unsigned int v177; // r11d
  unsigned int v178; // ecx
  HANDLE v179; // rax
  _QWORD *v180; // rax
  _QWORD *v181; // rbx
  HANDLE v182; // rax
  void *v183; // rax
  HANDLE v184; // rax
  void *v185; // rax
  HANDLE v186; // rax
  void *v187; // rax
  _QWORD *v188; // rax
  HANDLE v189; // rax
  HANDLE v190; // rax
  HANDLE v191; // rax
  HANDLE v192; // rax
  unsigned int *v193; // rdx
  int v194; // ecx
  unsigned int *v195; // rax
  HANDLE v196; // rax
  HANDLE v197; // rax
  HANDLE v198; // rax
  HANDLE v199; // rax
  int v200; // ecx
  HANDLE v201; // rax
  _DWORD *v202; // r10
  unsigned __int8 v203; // dl
  unsigned __int64 v204; // r11
  unsigned int v205; // edx
  int v206; // r10d
  unsigned __int8 *v207; // r8
  int v208; // r11d
  int v209; // ecx
  int v210; // ecx
  unsigned int v211; // r9d
  _BYTE *v212; // r10
  int v213; // r8d
  unsigned int v214; // r11d
  char v215; // dl
  int v216; // edx
  unsigned __int8 *v217; // r14
  _BYTE *v218; // r15
  int v219; // r13d
  int v220; // r12d
  int v221; // eax
  int v222; // esi
  int v223; // edi
  int v224; // esi
  int v225; // ecx
  int v226; // edi
  unsigned int v227; // r9d
  int v228; // r10d
  unsigned int v229; // ecx
  int v230; // r9d
  int v231; // r10d
  unsigned int v232; // ecx
  int v233; // r9d
  int v234; // r11d
  int v235; // ebx
  unsigned int v236; // r10d
  int v237; // ecx
  int v238; // r9d
  unsigned int v239; // r10d
  int v240; // ecx
  int v241; // r9d
  int v242; // r10d
  int v243; // ecx
  unsigned int v244; // r9d
  int v245; // r10d
  int v246; // ecx
  int v247; // r9d
  unsigned int v248; // r10d
  int v249; // ecx
  int v250; // r9d
  unsigned __int64 ii; // rax
  HANDLE v252; // rax
  char *v253; // rcx
  unsigned int *v254; // rdx
  _DWORD *v255; // r9
  const void *v256; // r11
  unsigned __int64 v257; // rax
  char *v258; // r9
  char *v259; // rcx
  HANDLE v260; // rax
  _DWORD *v261; // rax
  HANDLE v262; // rax
  void *v263; // rsi
  HANDLE v264; // rax
  void *v265; // rsi
  HANDLE v266; // rax
  void *v267; // rsi
  HANDLE v268; // rax
  HANDLE v269; // rax
  HANDLE v270; // rax
  HANDLE v271; // rax
  void *v272; // rsi
  HANDLE v273; // rax
  void *v274; // rsi
  HANDLE v275; // rax
  void *v276; // rsi
  HANDLE v277; // rax
  HANDLE v278; // rax
  HANDLE v279; // rax
  int *v280; // r14
  _DWORD *v281; // rax
  int v282; // r8d
  _DWORD *v283; // rdx
  _QWORD *v284; // rdx
  _DWORD *v285; // rax
  int v286; // edx
  _DWORD *v287; // rcx
  __int128 *v288; // rcx
  const unsigned __int16 *v289; // rax
  unsigned int v290; // r8d
  const unsigned __int16 *v291; // rax
  unsigned int v292; // r8d
  int v294; // [rsp+30h] [rbp-D0h]
  int v295; // [rsp+40h] [rbp-C0h]
  int v296; // [rsp+40h] [rbp-C0h]
  int v297; // [rsp+40h] [rbp-C0h]
  unsigned int v298; // [rsp+44h] [rbp-BCh]
  unsigned int v299; // [rsp+44h] [rbp-BCh]
  unsigned int v300; // [rsp+44h] [rbp-BCh]
  unsigned int v301; // [rsp+44h] [rbp-BCh]
  DWORD Size; // [rsp+4Ch] [rbp-B4h]
  unsigned int Sizea; // [rsp+4Ch] [rbp-B4h]
  int Sizeb; // [rsp+4Ch] [rbp-B4h]
  unsigned int Sizec; // [rsp+4Ch] [rbp-B4h]
  unsigned int Sized; // [rsp+4Ch] [rbp-B4h]
  unsigned int Sizee; // [rsp+4Ch] [rbp-B4h]
  unsigned int Sizef; // [rsp+4Ch] [rbp-B4h]
  int Sizeg; // [rsp+4Ch] [rbp-B4h]
  size_t Size_4; // [rsp+50h] [rbp-B0h]
  char *Size_4a; // [rsp+50h] [rbp-B0h]
  _DWORD *Size_4b; // [rsp+50h] [rbp-B0h]
  char *v314; // [rsp+58h] [rbp-A8h]
  unsigned int *v315; // [rsp+68h] [rbp-98h]
  __int64 v316; // [rsp+70h] [rbp-90h]
  char v317; // [rsp+70h] [rbp-90h]
  void *v319; // [rsp+78h] [rbp-88h]
  void *v320; // [rsp+78h] [rbp-88h]
  void *v321; // [rsp+78h] [rbp-88h]
  void *v322; // [rsp+78h] [rbp-88h]
  char *v323; // [rsp+78h] [rbp-88h]
  char *v324; // [rsp+78h] [rbp-88h]
  char *v325; // [rsp+78h] [rbp-88h]
  char *v326; // [rsp+78h] [rbp-88h]
  unsigned int *v327; // [rsp+78h] [rbp-88h]
  unsigned int *v328; // [rsp+78h] [rbp-88h]
  unsigned __int8 *v329; // [rsp+78h] [rbp-88h]
  void *v330; // [rsp+78h] [rbp-88h]
  unsigned __int8 *v331; // [rsp+80h] [rbp-80h]
  const void **v332; // [rsp+88h] [rbp-78h]
  char *v333; // [rsp+90h] [rbp-70h]
  char *v334; // [rsp+90h] [rbp-70h]
  unsigned __int64 v335; // [rsp+98h] [rbp-68h]
  unsigned __int64 v336; // [rsp+98h] [rbp-68h]
  void *v337; // [rsp+A0h] [rbp-60h]
  void *v338; // [rsp+A0h] [rbp-60h]
  void *v339; // [rsp+A8h] [rbp-58h]
  unsigned int v340; // [rsp+B0h] [rbp-50h]
  unsigned int *v341; // [rsp+B0h] [rbp-50h]
  __int64 v342; // [rsp+B0h] [rbp-50h]
  SIZE_T v343; // [rsp+B0h] [rbp-50h]
  int v344; // [rsp+B8h] [rbp-48h]
  unsigned int v345; // [rsp+B8h] [rbp-48h]
  unsigned int v346; // [rsp+B8h] [rbp-48h]
  _QWORD *v347; // [rsp+B8h] [rbp-48h]
  char v348; // [rsp+B8h] [rbp-48h]
  int v349; // [rsp+C0h] [rbp-40h]
  int v350; // [rsp+C0h] [rbp-40h]
  unsigned int *v351; // [rsp+C8h] [rbp-38h]
  unsigned int dwBytes; // [rsp+D0h] [rbp-30h]
  _DWORD *dwBytesa; // [rsp+D0h] [rbp-30h]
  SIZE_T dwBytesb; // [rsp+D0h] [rbp-30h]
  unsigned int dwBytesc; // [rsp+D0h] [rbp-30h]
  SIZE_T dwBytesd; // [rsp+D0h] [rbp-30h]
  SIZE_T dwBytese; // [rsp+D0h] [rbp-30h]
  SIZE_T v358; // [rsp+D8h] [rbp-28h]
  void *v359; // [rsp+D8h] [rbp-28h]
  void *v360; // [rsp+D8h] [rbp-28h]
  void *v361; // [rsp+D8h] [rbp-28h]
  void *v362; // [rsp+D8h] [rbp-28h]
  void *v363; // [rsp+D8h] [rbp-28h]
  void *v364; // [rsp+D8h] [rbp-28h]
  SIZE_T v365; // [rsp+D8h] [rbp-28h]
  SIZE_T v366; // [rsp+D8h] [rbp-28h]
  SIZE_T v367; // [rsp+D8h] [rbp-28h]
  const unsigned __int16 *Src; // [rsp+E0h] [rbp-20h]
  char *Srca; // [rsp+E0h] [rbp-20h]
  _BYTE *Srcb; // [rsp+E0h] [rbp-20h]
  int v371; // [rsp+E8h] [rbp-18h]
  DWORD v372; // [rsp+ECh] [rbp-14h]
  _BYTE *v373; // [rsp+F0h] [rbp-10h]
  unsigned int v374; // [rsp+F0h] [rbp-10h]
  int v375; // [rsp+F0h] [rbp-10h]
  _DWORD *lpMem; // [rsp+F8h] [rbp-8h]
  SIZE_T v377; // [rsp+100h] [rbp+0h]
  SIZE_T v378; // [rsp+100h] [rbp+0h]
  HMODULE phModule; // [rsp+110h] [rbp+10h] BYREF
  __int128 v381; // [rsp+118h] [rbp+18h] BYREF
  __int128 v382; // [rsp+128h] [rbp+28h]
  __int128 v383; // [rsp+148h] [rbp+48h]

  v3 = a1;
  v4 = a3;
  v383 = 0;
  if ( pSid )
    Size = GetLengthSid(pSid);
  else
    Size = 0;
  ProcessHeap = GetProcessHeap();
  v6 = HeapAlloc(ProcessHeap, 8u, 0xA0u);
  v7 = v6;
  if ( !v6 )
  {
    v8 = 0;
    v9 = -1073741801;
    v7 = 0;
    goto LABEL_50;
  }
  *v6 = xmmword_18001A2C0;
  v6[1] = xmmword_18001A2D0;
  v6[2] = xmmword_18001A2E0;
  v6[3] = xmmword_18001A2F0;
  v6[4] = xmmword_18001A300;
  v6[5] = xmmword_18001A310;
  v6[6] = xmmword_18001A320;
  v6[7] = xmmword_18001A330;
  v6[8] = xmmword_18001A340;
  v6[9] = xmmword_18001A350;
  v10 = GetProcessHeap();
  v11 = HeapAlloc(v10, 8u, 8u);
  v8 = v11;
  if ( !v11 )
  {
    v9 = -1073741801;
    v8 = 0;
    goto LABEL_50;
  }
  *v11 = qword_18001A200;
  v12 = __rdtsc();
  v13 = (const unsigned __int16 *)&unk_180016038;
  if ( v3 )
    v13 = v3;
  v14 = 0x7FFFFFFF;
  Src = v13;
  do
  {
    if ( !*v13 )
      break;
    ++v13;
    --v14;
  }
  while ( v14 );
  v15 = (0x7FFFFFFF - v14) & -(__int64)(v14 != 0);
  if ( v14 )
  {
    if ( (unsigned int)(2 * v15 + 6) < 4 )
    {
      v9 = -1073741675;
      goto LABEL_49;
    }
    lpMem = 0;
    v16 = 2 * v15 + 210;
    v349 = -1;
    v17 = -1;
    v18 = 0;
    if ( v16 >= 0xCC )
      v17 = 2 * v15 + 210;
    v19 = 0;
    v9 = v16 < 0xCC ? -805306219 : 0x10000000;
    if ( v16 < 0xCC )
      goto LABEL_41;
    v20 = 0x7FFFFFFF;
    v21 = &unk_180016038;
    do
    {
      if ( !*v21 )
        break;
      ++v21;
      --v20;
    }
    while ( v20 );
    if ( !v20 )
    {
      v9 = -1073741762;
LABEL_48:
      v3 = a1;
      goto LABEL_49;
    }
    v22 = 2 * ((0x7FFFFFFF - v20) & ((unsigned __int128)-(__int128)(unsigned __int64)v20 >> 64)) + 6;
    if ( v22 < 4 )
      goto LABEL_448;
    v23 = v17 + v22;
    v24 = -1;
    if ( v23 >= v17 )
      v24 = v23;
    v9 = v23 < v17 ? -805306219 : 0x10000000;
    if ( v23 < v17 )
      goto LABEL_40;
    v372 = Size + 4;
    if ( Size >= 0xFFFFFFFC )
    {
LABEL_448:
      v9 = -1073741675;
      goto LABEL_48;
    }
    v25 = v24 + Size + 4;
    v26 = -1;
    if ( v25 >= v24 )
      v26 = v24 + Size + 4;
    v9 = v25 < v24 ? -805306219 : 0x10000000;
    if ( v25 < v24 )
      goto LABEL_40;
    v27 = v26 + 8;
    v28 = -1;
    if ( v26 + 8 >= v26 )
      v28 = v26 + 8;
    v298 = v28;
    v9 = v27 < v26 ? -805306219 : 0x10000000;
    if ( v27 < v26 )
    {
LABEL_40:
      v19 = 0;
      goto LABEL_41;
    }
    v29 = v28;
    v30 = GetProcessHeap();
    v31 = (char *)HeapAlloc(v30, 8u, (unsigned int)v29);
    v18 = v31;
    if ( !v31 )
    {
      v9 = -1073741801;
      goto LABEL_48;
    }
    if ( v31 + 4 < v31 )
      goto LABEL_447;
    if ( v31 + 8 > &v31[v29] )
    {
LABEL_39:
      v9 = -1073741789;
      goto LABEL_40;
    }
    *(_DWORD *)v31 = 4;
    *((_DWORD *)v31 + 1) = 109;
    if ( !v7 )
    {
      v9 = -1073741811;
      goto LABEL_40;
    }
    v38 = v31;
    v39 = 0;
    do
    {
      v40 = *(_DWORD *)v38 + 4;
      if ( *(_DWORD *)v38 >= 0xFFFFFFFC )
        goto LABEL_447;
      v41 = &v38[v40];
      if ( v41 < v38 )
        goto LABEL_447;
      ++v39;
      v38 += v40;
    }
    while ( !v39 );
    v42 = v41 + 4;
    if ( v42 < v38 )
    {
LABEL_447:
      v9 = -1073741675;
      goto LABEL_40;
    }
    v43 = v298;
    if ( v38 + 164 > &v18[v298] )
      goto LABEL_39;
    *(_DWORD *)v38 = 160;
    memcpy_0(v42, v7, 0xA0u);
    if ( !v8 )
      goto LABEL_65;
    if ( v18 )
    {
      v44 = v18;
      for ( i = 0; i < 2; ++i )
      {
        v46 = *v44 + 4;
        if ( *v44 >= 0xFFFFFFFC || (_DWORD *)((char *)v44 + v46) < v44 )
          goto LABEL_87;
        v44 = (_DWORD *)((char *)v44 + v46);
      }
      if ( v44 + 1 < v44 )
        goto LABEL_87;
      if ( v44 + 3 > (_DWORD *)&v18[v298] )
        goto LABEL_76;
      *v44 = 8;
      memcpy_0(v44 + 1, v8, 8u);
      v47 = (unsigned __int64)v18;
      for ( j = 0; j < 3; ++j )
      {
        v49 = *(_DWORD *)v47 + 4;
        if ( *(_DWORD *)v47 >= 0xFFFFFFFC || v47 + v49 < v47 )
          goto LABEL_87;
        v47 += v49;
      }
      if ( v47 + 4 < v47 )
        goto LABEL_87;
      if ( v47 + 12 > (unsigned __int64)&v18[v298] )
        goto LABEL_76;
      *(_DWORD *)v47 = 8;
      *(_QWORD *)(v47 + 4) = v12;
      v50 = v298;
      v51 = v18;
      for ( k = 0; k < 4; ++k )
      {
        v53 = *v51 + 4;
        if ( *v51 >= 0xFFFFFFFC || (_DWORD *)((char *)v51 + v53) < v51 )
          goto LABEL_87;
        v51 = (_DWORD *)((char *)v51 + v53);
      }
      if ( v51 + 1 < v51 )
        goto LABEL_87;
      if ( v51 + 2 > (_DWORD *)&v18[v298] )
        goto LABEL_76;
      *v51 = 4;
      v51[1] = 3;
    }
    else
    {
      if ( v298 + 12 < v298 )
        goto LABEL_87;
      if ( v298 + 24 < v298 + 12 )
        goto LABEL_87;
      v50 = v298 + 32;
      v298 += 32;
      if ( v43 + 32 < v43 + 24 )
        goto LABEL_87;
    }
    v54 = Src;
    v55 = 0x7FFFFFFF;
    v56 = 5;
    do
    {
      if ( !*v54 )
        break;
      ++v54;
      --v55;
    }
    while ( v55 );
    v9 = 0;
    v57 = (0x7FFFFFFF - v55) & -(__int64)(v55 != 0);
    if ( !v55 )
      goto LABEL_121;
    v58 = v57 + 1;
    if ( v57 + 1 < v57 )
      goto LABEL_445;
    v59 = 2 * v58;
    if ( 2 * v58 )
    {
      if ( v18 )
      {
        v62 = (unsigned int *)v18;
        v63 = 0;
        while ( *v62 < 0xFFFFFFFC && (unsigned int *)((char *)v62 + *v62 + 4) >= v62 )
        {
          ++v63;
          v62 = (unsigned int *)((char *)v62 + *v62 + 4);
          if ( v63 >= 5 )
          {
            if ( v62 + 1 < v62 )
              break;
            if ( (char *)v62 + v59 + 4 <= &v18[v50] )
            {
              *v62 = v59;
              memcpy_0(v62 + 1, Src, v59);
              v56 = 6;
            }
            else
            {
              v9 = -1073741789;
            }
            goto LABEL_115;
          }
        }
      }
      else
      {
        v60 = v59 + 4;
        if ( v60 >= 4 )
        {
          v61 = v60 + v50;
          if ( (unsigned int)v61 < v50 )
          {
            v61 = 0xFFFFFFFFLL;
            v9 = -1073741675;
            v298 = -1;
          }
          else
          {
            v298 = v60 + v50;
            v56 = 6;
          }
LABEL_116:
          if ( v9 < 0 )
            goto LABEL_44;
          v64 = 0x7FFFFFFF;
          v65 = &unk_180016038;
          do
          {
            if ( !*v65 )
              break;
            ++v65;
            --v64;
          }
          while ( v64 );
          v66 = (0x7FFFFFFF - v64) & -(__int64)(v64 != 0);
          if ( !v64 )
          {
LABEL_121:
            v9 = -1073741762;
            goto LABEL_44;
          }
          if ( v66 + 1 < v66 )
          {
LABEL_445:
            v9 = -1073741675;
            goto LABEL_44;
          }
          v67 = (unsigned int)(2 * (v66 + 1));
          if ( (_DWORD)v67 )
          {
            if ( v18 )
            {
              v70 = v18;
              for ( m = 0; m < v56; ++m )
              {
                v72 = *v70 + 4;
                if ( *v70 >= 0xFFFFFFFC || (_DWORD *)((char *)v70 + v72) < v70 )
                {
                  v9 = -1073741675;
                  goto LABEL_140;
                }
                v70 = (_DWORD *)((char *)v70 + v72);
              }
              if ( v70 + 1 < v70 )
                goto LABEL_129;
              if ( (char *)v70 + v67 + 4 <= &v18[v61] )
              {
                *v70 = v67;
                v9 = 0;
                memcpy_0(v70 + 1, &unk_180016038, (unsigned int)v67);
                ++v56;
              }
              else
              {
                v9 = -1073741789;
              }
            }
            else
            {
              v68 = v67 + 4;
              if ( v68 >= 4 )
              {
                v69 = v68 + v61;
                if ( v68 + (unsigned int)v61 < (unsigned int)v61 )
                {
                  v69 = -1;
                  v9 = -1073741675;
                }
                else
                {
                  ++v56;
                  v9 = 0;
                }
LABEL_141:
                if ( v9 < 0 )
                  goto LABEL_44;
                if ( pSid )
                {
                  if ( !Size )
                  {
LABEL_65:
                    v9 = -1073741811;
LABEL_66:
                    v19 = 0;
LABEL_41:
                    if ( v9 >= 0 )
                    {
LABEL_42:
                      if ( v19 )
                        v9 = v19;
                    }
                    goto LABEL_44;
                  }
                }
                else if ( Size )
                {
                  goto LABEL_65;
                }
                if ( !v18 )
                {
                  v73 = v69 + v372;
                  if ( v69 + v372 < v69 )
                    goto LABEL_87;
                  v74 = v56 + 1;
                  kk = v73 + 8;
                  Sizea = v73 + 8;
                  if ( v73 + 8 < v73 )
                    goto LABEL_87;
LABEL_167:
                  v299 = v74 + 1;
                  v319 = (void *)__rdtsc();
                  v83 = kk + 8;
                  if ( v83 < 8 || (v84 = (v83 + 7) & 0xFFFFFFF8, v340 = v84, v84 < v83) )
                  {
                    v9 = -805306219;
                    goto LABEL_44;
                  }
                  v371 = 0;
                  v85 = v84;
                  v86 = GetProcessHeap();
                  v87 = (unsigned __int8 *)HeapAlloc(v86, 8u, (unsigned int)v85);
                  v88 = v87;
                  if ( !v87 )
                  {
                    v9 = -805306345;
                    goto LABEL_414;
                  }
                  *(_DWORD *)v87 = v299;
                  if ( v87 + 4 < v87 || (*((_DWORD *)v87 + 1) = Sizea, v87 + 8 < v87 + 4) )
                  {
                    v129 = GetProcessHeap();
                    HeapFree(v129, 0, v88);
                    v9 = -805306219;
                    goto LABEL_414;
                  }
                  *(_QWORD *)&v87[v85 - 8] = v319;
                  memcpy_0(v87 + 8, v18, Sizea);
                  v89 = v340;
                  v90 = 0;
                  v314 = 0;
                  v315 = 0;
                  v351 = 0;
                  v316 = 0;
                  if ( !v340
                    || (dwBytes = v340 + 8,
                        v91 = GetProcessHeap(),
                        v373 = HeapAlloc(v91, 0, v340 + 8LL),
                        (v92 = v373) == 0) )
                  {
                    v9 = -805306367;
                    goto LABEL_391;
                  }
                  v93 = 0;
                  for ( n = 0; n < v340; ++n )
                    v93 ^= v88[n];
                  v337 = v8;
                  v335 = v12;
                  v333 = v18;
                  if ( (unsigned __int64)v340 >> 3 )
                  {
                    v95 = v88;
                    v96 = v373;
                    v97 = -1;
                    Srca = 0;
                    v295 = 0;
                    v344 = 0;
                    Sizeb = 0;
                    do
                    {
                      v98 = *v95;
                      v99 = v95[1];
                      v100 = v95[4];
                      v95 += 8;
                      v101 = *(v95 - 5) | ((*(v95 - 6) | (((v98 << 8) | v99) << 8)) << 8);
                      v102 = *(v95 - 1) | ((*(v95 - 2) | ((*(v95 - 3) | (v100 << 8)) << 8)) << 8);
                      v103 = v97 ^ v102;
                      v104 = Sizeb ^ v101 ^ ((v97 ^ v102) - 19032) ^ 0xC81ECB17;
                      v105 = v103 ^ (__ROR4__(v104, 7) + 45493 * __ROR4__(v104 ^ 0xC81ECB17, 15));
                      v106 = v104 ^ (51991 * __ROR4__(v105 - 1313519016, 9) - __ROR4__(v105, 10));
                      v107 = v105 ^ (__ROR4__(v106, 27) + 51230 * __ROR4__(v106 ^ 0xCB17, 28));
                      v108 = v106 ^ (-937506025 - (v107 ^ 0xB1B54A58));
                      v109 = v108 ^ (19032 * (__ROR4__(v107 ^ (45493 * (v108 - 19032) - (v108 >> 6)), 15) ^ 0xCB17));
                      v110 = v107 ^ (45493 * (v108 - 19032) - (v108 >> 6)) ^ (51991 * (__ROR4__(~v109, 3) + 51230));
                      v111 = v109 ^ (v110 + 937486993);
                      v112 = v110 ^ (45493 * (v111 ^ 0xC81E)) ^ __ROR4__(v111, 10);
                      v113 = v111 ^ __ROR4__(v112, 3) ^ (51991 * __ROR4__(v112 ^ 0x4A58, 26));
                      v114 = v112 ^ (19032 * (__ROR4__(v113, 15) - 51230));
                      v115 = v113
                           ^ (19032 * (v114 ^ 0xC81E))
                           ^ ((v114 ^ (v114 >> 14)) >> 1)
                           ^ (19032 * (((unsigned __int64)(v114 - 51991) >> 29) | (8 * (v114 - 51991))));
                      v116 = v114 ^ (45493 * (v115 - 51991) - (v115 >> 13));
                      v117 = v115 ^ __ROR4__(v116, 11) ^ (51991 * __ROR4__(-1313519016 - v116, 9));
                      v118 = v116 ^ (v117 + 1313467786);
                      v119 = v117 ^ (19032 * (v118 ^ 0xB1B5) - __ROR4__(v118, 7));
                      v120 = v118 ^ (45493 * __ROR4__(v119 ^ 0xC81E, 28) - __ROR4__(v119, 16));
                      v121 = v119 ^ (__ROR4__(v120, 4) + 51991 * __ROR4__(-1313519016 - v120, 10));
                      v122 = v120 ^ __ROR4__(v121, 9) ^ (51230 * __ROR4__(v121 + 1313519016, 4));
                      v123 = v121 ^ (19032 * __ROR4__(v122 ^ 0xC81ECB17, 24) - __ROR4__(v122, 30));
                      v124 = v122 ^ (45493 * __ROR4__(-937506025 - v123, 11) - __ROR4__(v123, 12));
                      v125 = v123 ^ (v124 >> 8) ^ (51991 * (v124 ^ 0xB1B5));
                      v97 = v344 ^ v125 ^ v124 ^ 0xC81ECB17 ^ 0xB1B54A58;
                      v96[3] = v295 ^ v125;
                      Sizeb = v295 ^ v125;
                      v96[7] = v97;
                      v96[2] = __ROR4__(v295 ^ v125, 8);
                      v96[6] = __ROR4__(v97, 8);
                      v96[1] = __ROR4__(v295 ^ v125, 16);
                      v96[5] = __ROR4__(v97, 16);
                      *v96 = __ROR4__(v295 ^ v125, 24);
                      v96[4] = __ROR4__(v97, 24);
                      v96 += 8;
                      v295 = v101;
                      v344 = v102;
                      ++Srca;
                    }
                    while ( (unsigned __int64)Srca < (unsigned __int64)v340 >> 3 );
                    v18 = v333;
                    v8 = v337;
                    v12 = v335;
                    v90 = 0;
                    v89 = v340;
                    v92 = v373;
                  }
                  *(_QWORD *)&v92[v89] = v93;
                  v126 = GetProcessHeap();
                  v127 = HeapAlloc(v126, 8u, 0x30u);
                  Size_4 = (size_t)v127;
                  if ( !v127 )
                  {
                    v128 = -1073741801;
                    v296 = -1073741801;
                    goto LABEL_197;
                  }
                  *v127 = dwBytes;
                  v130 = GetProcessHeap();
                  v128 = -1073741801;
                  v131 = HeapAlloc(v130, 8u, dwBytes);
                  v132 = (_QWORD *)Size_4;
                  if ( v131 )
                  {
                    *(_QWORD *)(Size_4 + 8) = v131;
                    memcpy_0(v131, v373, dwBytes);
                    *(_DWORD *)(Size_4 + 16) = 160;
                    v133 = GetProcessHeap();
                    v134 = HeapAlloc(v133, 8u, 0xA0u);
                    v132 = (_QWORD *)Size_4;
                    if ( v134 )
                    {
                      *(_QWORD *)(Size_4 + 24) = v134;
                      *v134 = xmmword_18001A210;
                      v134[1] = xmmword_18001A220;
                      v134[2] = xmmword_18001A230;
                      v134[3] = xmmword_18001A240;
                      v134[4] = xmmword_18001A250;
                      v134[5] = xmmword_18001A260;
                      v134[6] = xmmword_18001A270;
                      v134[7] = xmmword_18001A280;
                      v134[8] = xmmword_18001A290;
                      v134[9] = xmmword_18001A2A0;
                      *(_DWORD *)(Size_4 + 32) = 8;
                      v135 = GetProcessHeap();
                      v136 = HeapAlloc(v135, 8u, 8u);
                      if ( v136 )
                      {
                        *(_QWORD *)(Size_4 + 40) = v136;
                        *v136 = qword_18001A2B0;
                        v296 = 0;
                        v90 = (unsigned int *)Size_4;
                        goto LABEL_197;
                      }
                      v132 = (_QWORD *)Size_4;
                    }
                    Size_4 = (size_t)v132;
                  }
                  v296 = -1073741801;
                  v320 = (void *)v132[1];
                  if ( v320 )
                  {
                    v137 = GetProcessHeap();
                    HeapFree(v137, 0, v320);
                    v132 = (_QWORD *)Size_4;
                    *(_QWORD *)(Size_4 + 8) = 0;
                  }
                  v321 = (void *)v132[3];
                  if ( v321 )
                  {
                    v138 = GetProcessHeap();
                    HeapFree(v138, 0, v321);
                    v132 = (_QWORD *)Size_4;
                    *(_QWORD *)(Size_4 + 24) = 0;
                  }
                  v322 = (void *)v132[5];
                  if ( v322 )
                  {
                    v139 = GetProcessHeap();
                    HeapFree(v139, 0, v322);
                    *(_QWORD *)(Size_4 + 40) = 0;
                  }
                  v140 = GetProcessHeap();
                  HeapFree(v140, 0, (LPVOID)Size_4);
LABEL_197:
                  v141 = GetProcessHeap();
                  HeapFree(v141, 0, v373);
                  v332 = (const void **)v90;
                  v142 = v296 | 0x10000000;
                  if ( v296 >= 0 )
                  {
                    if ( *v90 < 0xFFFFFFFC )
                    {
                      v143 = *v90 + 8;
                      if ( v143 >= *v90 + 4 )
                      {
                        v144 = v143 + v90[4];
                        dwBytesa = v90 + 4;
                        if ( v144 >= v143 )
                        {
                          v145 = v144 + 4;
                          if ( v144 + 4 >= v144 )
                          {
                            Sizec = v145 + v90[8];
                            if ( Sizec >= v145 )
                            {
                              v146 = v145 + v90[8];
                              v147 = GetProcessHeap();
                              v148 = (char *)HeapAlloc(v147, 8u, v146);
                              v90 = (unsigned int *)v332;
                              Size_4a = v148;
                              if ( !v148 )
                              {
LABEL_204:
                                v9 = -805306345;
                                goto LABEL_225;
                              }
                              *(_DWORD *)v148 = *(_DWORD *)v332;
                              v323 = v148 + 4;
                              if ( v148 + 4 < v148 )
                              {
                                Size_4a = v148;
                              }
                              else
                              {
                                memcpy_0(v148 + 4, v332[1], *(unsigned int *)v332);
                                v149 = &v323[*(unsigned int *)v332];
                                if ( v149 >= v323 )
                                {
                                  *(_DWORD *)v149 = *dwBytesa;
                                  v324 = v149 + 4;
                                  if ( v149 + 4 >= v149 )
                                  {
                                    memcpy_0(v149 + 4, v332[3], (unsigned int)*dwBytesa);
                                    v150 = &v324[*dwBytesa];
                                    if ( v150 >= v324 )
                                    {
                                      *(_DWORD *)v150 = *((_DWORD *)v332 + 8);
                                      v325 = v150 + 4;
                                      if ( v150 + 4 >= v150 )
                                      {
                                        memcpy_0(v150 + 4, v332[5], *((unsigned int *)v332 + 8));
                                        if ( &v325[*((unsigned int *)v332 + 8)] >= v325 )
                                        {
                                          v314 = Size_4a;
                                          v345 = Sizec;
                                          if ( !v18 || v299 <= 1 )
                                            goto LABEL_219;
                                          v151 = v18;
                                          v152 = 0;
                                          do
                                          {
                                            v153 = v151 + 4;
                                            if ( v151 + 4 < v151 )
                                              goto LABEL_389;
                                            v151 = &v153[*(unsigned int *)v151];
                                            if ( v151 < v153 )
                                              goto LABEL_389;
                                            ++v152;
                                          }
                                          while ( !v152 );
                                          if ( v151 + 4 < v151 )
                                            goto LABEL_389;
                                          if ( v299 <= 2 )
                                          {
LABEL_219:
                                            v9 = -1073741811;
                                            goto LABEL_225;
                                          }
                                          v155 = v18;
                                          for ( Sized = 0; Sized < 2; ++Sized )
                                          {
                                            v156 = v155 + 4;
                                            if ( v155 + 4 < v155 )
                                              goto LABEL_389;
                                            v155 = &v156[*(unsigned int *)v155];
                                            v326 = v155;
                                            if ( v155 < v156 )
                                              goto LABEL_389;
                                            v334 = v18;
                                          }
                                          if ( v155 + 4 < v155
                                            || *(_DWORD *)v151 >= 0xFFFFFFC0
                                            || (v157 = *(_DWORD *)v151 + 68, v157 < *(_DWORD *)v151 + 64)
                                            || (v158 = v157 + *(_DWORD *)v155, Sizee = v158, v158 < v157) )
                                          {
LABEL_389:
                                            v9 = -1073741675;
LABEL_225:
                                            if ( !v88 )
                                            {
LABEL_392:
                                              if ( v90 )
                                              {
                                                v263 = (void *)*((_QWORD *)v90 + 1);
                                                if ( v263 )
                                                {
                                                  v264 = GetProcessHeap();
                                                  HeapFree(v264, 0, v263);
                                                  *((_QWORD *)v90 + 1) = 0;
                                                }
                                                v265 = (void *)*((_QWORD *)v90 + 3);
                                                if ( v265 )
                                                {
                                                  v266 = GetProcessHeap();
                                                  HeapFree(v266, 0, v265);
                                                  *((_QWORD *)v90 + 3) = 0;
                                                }
                                                v267 = (void *)*((_QWORD *)v90 + 5);
                                                if ( v267 )
                                                {
                                                  v268 = GetProcessHeap();
                                                  HeapFree(v268, 0, v267);
                                                  *((_QWORD *)v90 + 5) = 0;
                                                }
                                                v269 = GetProcessHeap();
                                                HeapFree(v269, 0, v90);
                                              }
                                              if ( v314 )
                                              {
                                                v270 = GetProcessHeap();
                                                HeapFree(v270, 0, v314);
                                              }
                                              if ( v315 )
                                              {
                                                v271 = GetProcessHeap();
                                                HeapFree(v271, 0, v315);
                                              }
                                              if ( v351 )
                                              {
                                                v272 = (void *)*((_QWORD *)v351 + 1);
                                                if ( v272 )
                                                {
                                                  v273 = GetProcessHeap();
                                                  HeapFree(v273, 0, v272);
                                                  *((_QWORD *)v351 + 1) = 0;
                                                }
                                                v274 = (void *)*((_QWORD *)v351 + 3);
                                                if ( v274 )
                                                {
                                                  v275 = GetProcessHeap();
                                                  HeapFree(v275, 0, v274);
                                                  *((_QWORD *)v351 + 3) = 0;
                                                }
                                                v276 = (void *)*((_QWORD *)v351 + 5);
                                                if ( v276 )
                                                {
                                                  v277 = GetProcessHeap();
                                                  HeapFree(v277, 0, v276);
                                                  *((_QWORD *)v351 + 5) = 0;
                                                }
                                                v278 = GetProcessHeap();
                                                HeapFree(v278, 0, v351);
                                              }
                                              if ( v316 )
                                              {
                                                v279 = GetProcessHeap();
                                                HeapFree(v279, 0, (LPVOID)v316);
                                              }
LABEL_414:
                                              if ( v9 < 0 )
                                                goto LABEL_44;
                                              if ( v371 != 3 )
                                              {
LABEL_416:
                                                v9 = -1073425151;
                                                goto LABEL_44;
                                              }
                                              if ( !lpMem )
                                              {
                                                v9 = -1073741811;
                                                goto LABEL_44;
                                              }
                                              if ( lpMem + 1 >= lpMem )
                                              {
                                                v280 = 0;
                                                if ( *lpMem )
                                                  v280 = lpMem + 1;
                                                if ( *lpMem != 4 )
                                                {
LABEL_431:
                                                  v9 = -1073741789;
                                                  goto LABEL_44;
                                                }
                                                v9 = *v280;
                                                if ( v9 >= 0 )
                                                {
                                                  v281 = lpMem;
                                                  v282 = 0;
                                                  v19 = v9;
                                                  while ( 1 )
                                                  {
                                                    v283 = v281 + 1;
                                                    if ( v281 + 1 < v281 )
                                                      goto LABEL_445;
                                                    v281 = (_DWORD *)((char *)v283 + (unsigned int)*v281);
                                                    if ( v281 < v283 )
                                                      goto LABEL_445;
                                                    if ( ++v282 )
                                                    {
                                                      if ( v281 + 1 < v281 )
                                                        goto LABEL_445;
                                                      v284 = 0;
                                                      if ( *v281 )
                                                        v284 = v281 + 1;
                                                      if ( *v281 != 8 )
                                                        goto LABEL_431;
                                                      if ( v12 != *v284 )
                                                        goto LABEL_416;
                                                      v285 = lpMem;
                                                      v286 = 0;
                                                      while ( 1 )
                                                      {
                                                        v287 = v285 + 1;
                                                        if ( v285 + 1 < v285 )
                                                          goto LABEL_445;
                                                        v285 = (_DWORD *)((char *)v287 + (unsigned int)*v285);
                                                        if ( v285 < v287 )
                                                          goto LABEL_445;
                                                        if ( (unsigned int)++v286 >= 2 )
                                                        {
                                                          if ( v285 + 1 < v285 )
                                                            goto LABEL_445;
                                                          v288 = 0;
                                                          if ( *v285 )
                                                            v288 = (__int128 *)(v285 + 1);
                                                          if ( *v285 != 16 )
                                                          {
                                                            v9 = -2147024883;
                                                            goto LABEL_44;
                                                          }
                                                          v9 = 0;
                                                          v383 = *v288;
                                                          goto LABEL_42;
                                                        }
                                                      }
                                                    }
                                                  }
                                                }
LABEL_44:
                                                if ( v18 )
                                                {
                                                  v32 = GetProcessHeap();
                                                  HeapFree(v32, 0, v18);
                                                }
                                                if ( lpMem )
                                                {
                                                  v33 = GetProcessHeap();
                                                  HeapFree(v33, 0, lpMem);
                                                }
                                                goto LABEL_48;
                                              }
                                              goto LABEL_445;
                                            }
LABEL_391:
                                            v262 = GetProcessHeap();
                                            HeapFree(v262, 0, v88);
                                            goto LABEL_392;
                                          }
                                          if ( v158 > 0x400000 )
                                          {
                                            v9 = -2147418113;
                                            v314 = Size_4a;
                                            goto LABEL_225;
                                          }
                                          v159 = v157 + *(_DWORD *)v326;
                                          v160 = GetProcessHeap();
                                          v161 = (unsigned int *)HeapAlloc(v160, 8u, v159);
                                          v90 = (unsigned int *)v332;
                                          v162 = v161 == 0;
                                          v315 = v161;
                                          *((_QWORD *)&v163 + 1) = v161;
                                          *(_QWORD *)&v163 = Size_4a;
                                          v314 = Size_4a;
                                          if ( v162 )
                                          {
                                            v9 = -805306345;
                                            v315 = 0;
                                            goto LABEL_225;
                                          }
                                          v164 = Size_4a;
                                          phModule = 0;
                                          v381 = 0;
                                          v382 = 0;
                                          if ( !Size_4a )
                                          {
                                            v9 = -2147024809;
LABEL_388:
                                            v315 = (unsigned int *)*((_QWORD *)&v163 + 1);
                                            v314 = v164;
                                            goto LABEL_225;
                                          }
                                          v381 = v163;
                                          LODWORD(v382) = v345;
                                          *(_QWORD *)((char *)&v382 + 4) = Sizee;
                                          if ( GetModuleHandleExW(1u, L"ntdll.dll", &phModule)
                                            && (ProcAddress = GetProcAddress(phModule, "NtQuerySystemInformation")) != 0 )
                                          {
                                            LastError = ((__int64 (__fastcall *)(__int64, __int128 *))ProcAddress)(
                                                          134,
                                                          &v381)
                                                      | 0x10000000;
                                            if ( LastError >= 0 )
                                            {
                                              v168 = DWORD1(v382);
LABEL_254:
                                              if ( v168 < 4 )
                                              {
                                                v9 = -805306306;
                                                goto LABEL_251;
                                              }
                                              v170 = *v315;
                                              v171 = v315 + 1;
                                              Sizef = *v315;
                                              if ( v315 + 1 < v315 )
                                                goto LABEL_385;
                                              if ( v168 - 4 < (unsigned int)v170 )
                                              {
                                                v9 = -805306306;
                                                goto LABEL_251;
                                              }
                                              v377 = *v315;
                                              dwBytesb = (SIZE_T)v171 + v170;
                                              if ( (unsigned int *)((char *)v171 + v170) < v171 )
                                              {
LABEL_385:
                                                v169 = Size_4a;
                                                v9 = -805306219;
                                                goto LABEL_252;
                                              }
                                              if ( (unsigned int)v170 >= 0xFFFFFFFC )
                                                goto LABEL_384;
                                              if ( v168 - ((_DWORD)v170 + 4) < 4 )
                                              {
LABEL_262:
                                                v172 = Size_4a;
                                                v9 = -805306306;
LABEL_263:
                                                v314 = v172;
                                                goto LABEL_225;
                                              }
                                              v173 = *(unsigned int *)((char *)v171 + v170);
                                              v300 = v173;
                                              v174 = dwBytesb + 4;
                                              if ( dwBytesb + 4 < dwBytesb )
                                                goto LABEL_384;
                                              v346 = v170 + 8;
                                              if ( (int)v170 + 8 < (unsigned int)(v170 + 4) )
                                                goto LABEL_384;
                                              if ( v168 - v346 < v173 )
                                                goto LABEL_262;
                                              v358 = v173;
                                              v327 = (unsigned int *)(v174 + v173);
                                              if ( (unsigned __int64)v327 < v174 )
                                                goto LABEL_384;
                                              v175 = v346 + v173;
                                              if ( v346 + v173 < v346 )
                                                goto LABEL_384;
                                              if ( v168 - v175 < 4 )
                                                goto LABEL_262;
                                              v176 = v327;
                                              v328 = v327 + 1;
                                              if ( v328 < v176 || (v177 = v175 + 4, v175 + 4 < v175) )
                                              {
LABEL_384:
                                                v172 = Size_4a;
                                                v9 = -805306219;
                                                goto LABEL_263;
                                              }
                                              v178 = *v176;
                                              v374 = *v176;
                                              if ( v168 - v177 < *v176 )
                                                goto LABEL_262;
                                              if ( v177 + v178 < v177 )
                                              {
                                                v9 = -805306219;
                                                goto LABEL_225;
                                              }
                                              if ( v168 != v177 + v178 || v173 + (_DWORD)v170 + v178 + 12LL != v168 )
                                                goto LABEL_262;
                                              v179 = GetProcessHeap();
                                              v180 = HeapAlloc(v179, 8u, 0x30u);
                                              v347 = v180;
                                              v181 = v180;
                                              if ( !v180 )
                                              {
                                                v90 = (unsigned int *)v332;
                                                v314 = Size_4a;
                                                goto LABEL_204;
                                              }
                                              v341 = 0;
                                              if ( v315 == (unsigned int *)-4LL )
                                              {
                                                *(_DWORD *)v180 = 0;
                                                v180[1] = 0;
                                                v297 = 0;
                                              }
                                              else
                                              {
                                                *(_DWORD *)v180 = Sizef;
                                                v182 = GetProcessHeap();
                                                v183 = HeapAlloc(v182, 8u, v377);
                                                if ( !v183 )
                                                {
LABEL_289:
                                                  v90 = (unsigned int *)v332;
                                                  v314 = Size_4a;
                                                  v188 = v347;
                                                  v297 = -1073741801;
                                                  v378 = (SIZE_T)v88;
                                                  v336 = v12;
                                                  v338 = v8;
                                                  v339 = v7;
                                                  v359 = (void *)v347[1];
                                                  if ( v359 )
                                                  {
                                                    v189 = GetProcessHeap();
                                                    HeapFree(v189, 0, v359);
                                                    v188 = v347;
                                                    v347[1] = 0;
                                                  }
                                                  v360 = (void *)v188[3];
                                                  if ( v360 )
                                                  {
                                                    v190 = GetProcessHeap();
                                                    HeapFree(v190, 0, v360);
                                                    v188 = v347;
                                                    v347[3] = 0;
                                                  }
                                                  v361 = (void *)v188[5];
                                                  if ( v361 )
                                                  {
                                                    v191 = GetProcessHeap();
                                                    HeapFree(v191, 0, v361);
                                                    v347[5] = 0;
                                                  }
                                                  v192 = GetProcessHeap();
                                                  HeapFree(v192, 0, v347);
                                                  v193 = 0;
                                                  goto LABEL_299;
                                                }
                                                v181[1] = v183;
                                                v297 = 0;
                                                memcpy_0(v183, v315 + 1, v377);
                                              }
                                              if ( dwBytesb == -4 )
                                              {
                                                *((_DWORD *)v181 + 4) = 0;
                                                v181[3] = 0;
                                              }
                                              else
                                              {
                                                *((_DWORD *)v181 + 4) = v300;
                                                v184 = GetProcessHeap();
                                                v185 = HeapAlloc(v184, 8u, v358);
                                                if ( !v185 )
                                                {
LABEL_288:
                                                  v347 = v181;
                                                  goto LABEL_289;
                                                }
                                                v181[3] = v185;
                                                v297 = 0;
                                                memcpy_0(v185, (const void *)(dwBytesb + 4), v358);
                                              }
                                              if ( v328 )
                                              {
                                                *((_DWORD *)v181 + 8) = v374;
                                                v186 = GetProcessHeap();
                                                v187 = HeapAlloc(v186, 8u, v374);
                                                if ( !v187 )
                                                  goto LABEL_288;
                                                v181[5] = v187;
                                                v297 = 0;
                                                memcpy_0(v187, v328, v374);
                                              }
                                              else
                                              {
                                                *((_DWORD *)v181 + 8) = 0;
                                                v181[5] = 0;
                                              }
                                              v193 = (unsigned int *)v181;
                                              v341 = (unsigned int *)v181;
                                              v90 = (unsigned int *)v332;
                                              v314 = Size_4a;
                                              v378 = (SIZE_T)v88;
                                              v336 = v12;
                                              v338 = v8;
                                              v339 = v7;
LABEL_299:
                                              v194 = v297;
                                              if ( v297 < 0 )
                                              {
                                                if ( v193 )
                                                {
                                                  v362 = (void *)*((_QWORD *)v193 + 1);
                                                  if ( v362 )
                                                  {
                                                    v196 = GetProcessHeap();
                                                    HeapFree(v196, 0, v362);
                                                    v193 = v341;
                                                    *((_QWORD *)v341 + 1) = 0;
                                                  }
                                                  v363 = (void *)*((_QWORD *)v193 + 3);
                                                  if ( v363 )
                                                  {
                                                    v197 = GetProcessHeap();
                                                    HeapFree(v197, 0, v363);
                                                    v193 = v341;
                                                    *((_QWORD *)v341 + 3) = 0;
                                                  }
                                                  v364 = (void *)*((_QWORD *)v193 + 5);
                                                  if ( v364 )
                                                  {
                                                    v198 = GetProcessHeap();
                                                    HeapFree(v198, 0, v364);
                                                    *((_QWORD *)v341 + 5) = 0;
                                                  }
                                                  v199 = GetProcessHeap();
                                                  HeapFree(v199, 0, v341);
                                                  v194 = v297;
                                                }
                                                v195 = 0;
                                              }
                                              else
                                              {
                                                v195 = v193;
                                                v351 = v193;
                                              }
                                              v200 = v194 | 0x10000000;
                                              if ( v200 < 0 )
                                              {
                                                v9 = v200;
                                                goto LABEL_225;
                                              }
                                              if ( !v195
                                                || (v329 = (unsigned __int8 *)*((_QWORD *)v195 + 1)) == 0
                                                || !*v195 )
                                              {
                                                v9 = -805306355;
                                                goto LABEL_225;
                                              }
                                              v342 = *v195 - 8LL;
                                              v201 = GetProcessHeap();
                                              Size_4b = HeapAlloc(v201, 0, v342);
                                              v202 = Size_4b;
                                              if ( !Size_4b )
                                              {
LABEL_342:
                                                v316 = 0;
                                                v9 = -805306367;
                                                goto LABEL_225;
                                              }
                                              v203 = 0;
                                              v204 = v342;
                                              v331 = v329;
                                              dwBytesc = v342 & 7;
                                              Srcb = Size_4b;
                                              if ( (v342 & 7) != 0 )
                                              {
                                                v205 = 0;
                                                v206 = 0;
                                                v207 = v329;
                                                v208 = 0;
                                                do
                                                {
                                                  v209 = *v207++;
                                                  v348 = 8 * v205;
                                                  if ( v205 >= 4 )
                                                    v208 |= v209 << (56 - v348);
                                                  else
                                                    v206 |= v209 << (24 - v348);
                                                  ++v205;
                                                }
                                                while ( (int)v205 < (int)dwBytesc );
                                                v203 = 0;
                                                v349 = v208;
                                                v204 = v342;
                                                Sizeg = v206;
                                                v202 = Size_4b;
                                                v331 = v207;
                                                v332 = (const void **)v90;
                                                v378 = (SIZE_T)v88;
                                                v334 = v18;
                                                v336 = v12;
                                                v338 = v8;
                                                v339 = v7;
                                                v210 = v349 ^ 0x699A899C;
                                                v211 = Sizeg ^ 0x92F65A5;
                                                if ( (v342 & 7) != 0 )
                                                {
                                                  v212 = Size_4b;
                                                  v213 = Sizeg ^ 0x92F65A5;
                                                  v214 = 0;
                                                  do
                                                  {
                                                    v365 = (SIZE_T)(v212 + 1);
                                                    if ( v214 >= 4 )
                                                    {
                                                      v210 = __ROR4__(v210, 24);
                                                      v215 = v210;
                                                    }
                                                    else
                                                    {
                                                      v213 = __ROR4__(v213, 24);
                                                      v215 = v213;
                                                    }
                                                    *v212 = v215;
                                                    ++v214;
                                                    ++v212;
                                                  }
                                                  while ( (int)v214 < (int)dwBytesc );
                                                  v202 = Size_4b;
                                                  v204 = v342;
                                                  Srcb = (_BYTE *)v365;
                                                  v203 = 0;
                                                }
                                                if ( dwBytesc <= 4 )
                                                {
                                                  v301 = 0;
                                                  if ( dwBytesc < 4 )
                                                    v211 = v211 >> (8 * (4 - dwBytesc)) << (8 * (4 - dwBytesc));
                                                }
                                                else
                                                {
                                                  v301 = (v349 ^ 0x699A899Cu) >> (8 * (8 - dwBytesc)) << (8 * (8 - dwBytesc));
                                                }
                                              }
                                              else
                                              {
                                                Sizeg = 0;
                                                v301 = 0;
                                                v211 = 0;
                                              }
                                              v366 = v204 >> 3;
                                              if ( v204 >> 3 )
                                              {
                                                v216 = v301;
                                                v217 = v331;
                                                v218 = Srcb;
                                                v219 = Sizeg;
                                                v220 = v349;
                                                dwBytesd = 0;
                                                do
                                                {
                                                  v221 = *v217;
                                                  v222 = v217[1];
                                                  v223 = v217[4];
                                                  v217 += 8;
                                                  v224 = *(v217 - 5)
                                                       | ((*(v217 - 6) | (((v221 << 8) | v222) << 8)) << 8);
                                                  v225 = v211 ^ v224;
                                                  v226 = *(v217 - 1)
                                                       | ((*(v217 - 2) | ((*(v217 - 3) | (v223 << 8)) << 8)) << 8);
                                                  v227 = v211 ^ v224 ^ v216 ^ v226 ^ 0xAB69605E ^ 0x7F1137F;
                                                  v228 = v225
                                                       ^ (__ROR4__(v227, 22) + 4991 * __ROR4__(v227 + 1419157410, 27));
                                                  v229 = v227
                                                       ^ (43881 * __ROR4__(v228 + 133239679, 9) - __ROR4__(v228, 30));
                                                  v230 = v228 ^ (24670 * (v229 - 4991) - (v229 >> 13));
                                                  v231 = v229
                                                       ^ (2033 * __ROR4__(v230 ^ 0xAB69, 26) - __ROR4__(v230, 30));
                                                  v232 = v230 ^ (133239679 - (v231 ^ 0xAB69605E));
                                                  v233 = v231 ^ (43881 * (v232 ^ 0x137F)) ^ __ROR4__(v232, 6);
                                                  v234 = v232
                                                       ^ (__ROR4__(v233, 30) + 24670 * __ROR4__(v233 + 133239679, 15));
                                                  v235 = v233
                                                       ^ (2033 * __ROR4__(v234 + 1419157410, 14) - __ROR4__(v234, 24));
                                                  v236 = v234
                                                       ^ __ROR4__(v235, 10)
                                                       ^ (4991 * __ROR4__(v235 ^ 0xAB69605E, 12));
                                                  v237 = v235 ^ (v236 >> 10) ^ (43881 * (v236 ^ 0x7F1));
                                                  v238 = v236 ^ (2033 * (__ROR4__(~v237, 5) + 24670));
                                                  v239 = v237 ^ (v238 - 2033) ^ 0xAB69605E;
                                                  v240 = v238 ^ ((v239 >> 2) + 4991 * __ROR4__(v239 ^ 0x7F1, 30));
                                                  v241 = v239
                                                       ^ (__ROR4__(v240, 25) + 43881 * __ROR4__(v240 - 133239679, 6));
                                                  v242 = v240 ^ (24670 * (v241 ^ 0x137F) + __ROR4__(v241, 9));
                                                  v243 = v241
                                                       ^ (__ROR4__(v242, 25) + 2033 * __ROR4__(v242 ^ 0xAB69, 27));
                                                  v244 = v242 ^ v243 ^ 0xAC987321;
                                                  v245 = v243 ^ (4991 * (__ROR4__(v244, 3) - 43881));
                                                  v246 = v244
                                                       ^ (24670 * __ROR4__(v245 - 133239679, 1) - __ROR4__(v245, 6));
                                                  v247 = v245
                                                       ^ (__ROR4__(v246, 18) + 2033 * __ROR4__(v246 - 1419157410, 29));
                                                  v248 = v246
                                                       ^ (4991 * __ROR4__(v247 - 1419157410, 17) - __ROR4__(v247, 14));
                                                  v249 = v247 ^ (v248 >> 3) ^ (43881 * (v248 ^ 0x605E));
                                                  v216 = v249 ^ v220;
                                                  v220 = v226;
                                                  v250 = v219
                                                       ^ __ROR4__(v249, 30)
                                                       ^ (24670 * __ROR4__(v249 ^ 0x7F1137F, 28));
                                                  v219 = v224;
                                                  v211 = v248 ^ v250;
                                                  v218[3] = v211;
                                                  v218[7] = v216;
                                                  v218[2] = __ROR4__(v211, 8);
                                                  v218[6] = __ROR4__(v216, 8);
                                                  v218[1] = __ROR4__(v211, 16);
                                                  v218[5] = __ROR4__(v216, 16);
                                                  *v218 = __ROR4__(v211, 24);
                                                  v218[4] = __ROR4__(v216, 24);
                                                  v218 += 8;
                                                  ++dwBytesd;
                                                }
                                                while ( dwBytesd < v366 );
                                                v203 = 0;
                                                v128 = -1073741801;
                                                v18 = v334;
                                                v7 = v339;
                                                v8 = v338;
                                                v12 = v336;
                                                v88 = (unsigned __int8 *)v378;
                                                v90 = (unsigned int *)v332;
                                                v202 = Size_4b;
                                                v204 = v342;
                                              }
                                              for ( ii = 0; ii < v204; ++ii )
                                                v203 ^= *((_BYTE *)v202 + ii);
                                              if ( v203 != *(_QWORD *)&v329[v204] )
                                              {
                                                v252 = GetProcessHeap();
                                                HeapFree(v252, 0, Size_4b);
                                                goto LABEL_342;
                                              }
                                              v253 = v314;
                                              v254 = v315;
                                              if ( (unsigned int)v204 < 4 )
                                              {
                                                v128 = -1073741762;
                                                v316 = (__int64)v202;
LABEL_381:
                                                v9 = v128 | 0x10000000;
                                                goto LABEL_225;
                                              }
                                              v316 = (__int64)v202;
                                              v330 = v202 + 1;
                                              v255 = v202;
                                              if ( v202 + 1 < v202 )
                                                goto LABEL_378;
                                              if ( (unsigned int)(v204 - 4) < 4 )
                                              {
LABEL_347:
                                                v128 = -1073741762;
                                                v316 = (__int64)v202;
LABEL_380:
                                                v314 = v253;
                                                v315 = v254;
                                                goto LABEL_381;
                                              }
                                              dwBytese = (SIZE_T)(v202 + 2);
                                              v253 = v314;
                                              if ( v202 + 2 < v202 + 1 )
                                                goto LABEL_378;
                                              if ( (unsigned int)(v204 - 8) < v202[1] )
                                                goto LABEL_347;
                                              if ( v202[1] >= 0xFFFFFFF8 )
                                              {
LABEL_378:
                                                v128 = -1073741675;
                                              }
                                              else
                                              {
                                                v367 = (unsigned int)v204;
                                                v343 = (unsigned int)v202[1];
                                                v253 = v314;
                                                v254 = v315;
                                                if ( (char *)v202 + (unsigned int)v204 >= (char *)v202 + v343 + 8 )
                                                {
                                                  v256 = v202 + 2;
                                                  if ( v367 - v343 - 8 < 8 )
                                                  {
                                                    v350 = 0;
                                                    if ( v202 == (_DWORD *)-8LL )
                                                    {
                                                      v316 = -8;
                                                    }
                                                    else
                                                    {
                                                      v202 = Size_4b;
                                                      v257 = (unsigned __int64)v330 + v343 + 4;
                                                      if ( v257 < dwBytese )
                                                      {
                                                        v128 = -1073741675;
                                                        v316 = (__int64)v255;
                                                        goto LABEL_381;
                                                      }
                                                      v258 = (char *)dwBytese;
                                                      if ( v257 > dwBytese )
                                                      {
                                                        while ( v258 + 4 >= v258 )
                                                        {
                                                          if ( (unsigned __int64)(v258 + 4) > v257 )
                                                            goto LABEL_366;
                                                          if ( *(_DWORD *)v258 >= 0xFFFFFFFC )
                                                            break;
                                                          v259 = &v258[*(_DWORD *)v258 + 4];
                                                          if ( v259 < v258 )
                                                            break;
                                                          v257 = (unsigned __int64)Size_4b + v343 + 8;
                                                          if ( (unsigned __int64)v259 > v257 )
                                                            goto LABEL_366;
                                                          ++v350;
                                                          v258 += (unsigned int)(*(_DWORD *)v258 + 4);
                                                          if ( (unsigned __int64)v259 >= v257 )
                                                            goto LABEL_365;
                                                        }
                                                        v128 = -1073741675;
                                                        goto LABEL_381;
                                                      }
                                                      v316 = (__int64)Size_4b;
LABEL_365:
                                                      if ( v258 != (char *)v257 )
                                                      {
LABEL_366:
                                                        v128 = -1073741811;
                                                        goto LABEL_381;
                                                      }
                                                    }
                                                    v375 = *v202;
                                                    if ( v202[1] )
                                                    {
                                                      v260 = GetProcessHeap();
                                                      v261 = HeapAlloc(v260, 8u, v343);
                                                      if ( !v261 )
                                                        goto LABEL_381;
                                                      v128 = 0;
                                                      v256 = (const void *)dwBytese;
                                                    }
                                                    else
                                                    {
                                                      v261 = 0;
                                                      v128 = 0;
                                                    }
                                                    lpMem = v261;
                                                    if ( v256 )
                                                      memcpy_0(v261, v256, v343);
                                                    v371 = v350;
                                                    if ( v375 != v350 )
                                                      v128 = -1073741762;
                                                    goto LABEL_381;
                                                  }
                                                }
                                                v128 = -1073741762;
                                              }
                                              v316 = (__int64)v202;
                                              goto LABEL_380;
                                            }
                                          }
                                          else
                                          {
                                            LastError = GetLastError();
                                            v166 = LastError < 0;
                                            if ( LastError > 0 )
                                            {
                                              LastError = (unsigned __int16)LastError | 0x80070000;
                                              v166 = LastError < 0;
                                            }
                                            if ( !v166 )
                                            {
                                              v9 = -2147467259;
                                              goto LABEL_387;
                                            }
                                          }
                                          v168 = Sizee;
                                          if ( LastError == -805306333 )
                                          {
                                            v9 = -2147024774;
LABEL_251:
                                            v169 = Size_4a;
LABEL_252:
                                            v314 = v169;
                                            goto LABEL_225;
                                          }
                                          if ( LastError >= 0 )
                                            goto LABEL_254;
                                          v9 = LastError;
LABEL_387:
                                          *((_QWORD *)&v163 + 1) = v315;
                                          v164 = Size_4a;
                                          goto LABEL_388;
                                        }
                                      }
                                    }
                                  }
                                }
                              }
                              v154 = GetProcessHeap();
                              HeapFree(v154, 0, Size_4a);
                            }
                          }
                        }
                      }
                    }
                    v142 = -805306219;
                  }
                  v9 = v142;
                  goto LABEL_225;
                }
                v75 = v69;
                v76 = (DWORD *)v18;
                for ( jj = 0; jj < v56; v76 = (DWORD *)((char *)v76 + v78) )
                {
                  v78 = *v76 + 4;
                  if ( *v76 >= 0xFFFFFFFC || (DWORD *)((char *)v76 + v78) < v76 )
                    goto LABEL_87;
                  ++jj;
                }
                if ( v76 + 1 < v76 )
                  goto LABEL_87;
                if ( (char *)v76 + Size + 4 > &v18[v75] )
                  goto LABEL_76;
                *v76 = Size;
                if ( pSid )
                  memcpy_0(v76 + 1, pSid, Size);
                v74 = v56 + 1;
                Sizea = v75;
                v80 = v18;
                v81 = 0;
                for ( kk = v75; v81 < v74; v80 = (_DWORD *)((char *)v80 + v82) )
                {
                  v82 = *v80 + 4;
                  if ( *v80 >= 0xFFFFFFFC || (_DWORD *)((char *)v80 + v82) < v80 )
                    goto LABEL_87;
                  ++v81;
                }
                if ( v80 + 1 < v80 )
                {
LABEL_87:
                  v9 = -1073741675;
                  goto LABEL_66;
                }
                if ( v80 + 2 <= (_DWORD *)&v18[(unsigned int)v75] )
                {
                  *v80 = 4;
                  v80[1] = 2 * a3;
                  goto LABEL_167;
                }
LABEL_76:
                v9 = -1073741789;
                goto LABEL_66;
              }
LABEL_129:
              v9 = -1073741675;
            }
          }
          else
          {
            v9 = -1073741811;
          }
LABEL_140:
          v69 = v298;
          goto LABEL_141;
        }
      }
      v9 = -1073741675;
    }
    else
    {
      v9 = -1073741811;
    }
LABEL_115:
    v61 = v298;
    goto LABEL_116;
  }
  v9 = -1073741762;
LABEL_49:
  v4 = a3;
LABEL_50:
  if ( v7 )
  {
    v34 = GetProcessHeap();
    HeapFree(v34, 0, v7);
  }
  if ( v8 )
  {
    v35 = GetProcessHeap();
    HeapFree(v35, 0, v8);
  }
  if ( v9 < 0 )
  {
    if ( v4 || !IsCapabilityLicensedApp(v3) )
    {
      v294 = v9;
      v289 = L"Invoking license manager because app not licensed: PFN %s, hr = 0x%X";
      v290 = 400;
      goto LABEL_468;
    }
    v317 = 0;
    LogMessage(
      3u,
      "onecoreuap\\enduser\\winstore\\licensemanager\\apisethost\\activationapis.cpp",
      0x184u,
      "InvokeLicenseManagerRequired",
      L"Skipping license manager because app has capability: PFN %s",
      v3);
    return v317;
  }
  v36 = _time64(0);
  if ( (BYTE4(v383) & 0x20) == 0 )
  {
    if ( (BYTE4(v383) & 0x40) != 0 && v4 )
    {
      v294 = DWORD1(v383);
      v289 = L"Invoking license manager because licenses/leases require online check: PFN %s, Basic Policy Flags 0x%X";
      v290 = 322;
LABEL_468:
      v317 = 1;
      LogMessage(
        3u,
        "onecoreuap\\enduser\\winstore\\licensemanager\\apisethost\\activationapis.cpp",
        v290,
        "InvokeLicenseManagerRequired",
        v289,
        v3,
        v294);
      return v317;
    }
    if ( DWORD2(v383) && DWORD2(v383) - v36 <= 300 )
    {
      v291 = L"Invoking license manager because license/lease about to expire: PFN %s";
      v292 = 336;
    }
    else
    {
      if ( !HIDWORD(v383) || SHIDWORD(v383) >= v36 || !v4 )
      {
        v317 = 0;
        LogMessage(
          3u,
          "onecoreuap\\enduser\\winstore\\licensemanager\\apisethost\\activationapis.cpp",
          0x175u,
          "InvokeLicenseManagerRequired",
          L"Skipping license manager: PFN %s",
          v3);
        return v317;
      }
      if ( IsCapabilityLicensedApp(v3) )
        return 0;
      v291 = L"Invoking license manager because license/lease polling time up: PFN %s";
      v292 = 361;
    }
    v317 = 1;
    LogMessage(
      3u,
      "onecoreuap\\enduser\\winstore\\licensemanager\\apisethost\\activationapis.cpp",
      v292,
      "InvokeLicenseManagerRequired",
      v291,
      v3);
    return v317;
  }
  LogMessage(
    3u,
    "onecoreuap\\enduser\\winstore\\licensemanager\\apisethost\\activationapis.cpp",
    0x138u,
    "InvokeLicenseManagerRequired",
    L"Invoking license manager because licenses/leases require online check: PFN %s, Basic Policy Flags 0x%X",
    v3,
    DWORD1(v383));
  return 1;
}

```

## disassembly

```asm
0x18000be7c  mov     [rsp-8+arg_10], rbx
0x18000be81  push    rbp
0x18000be82  push    rsi
0x18000be83  push    rdi
0x18000be84  push    r12
0x18000be86  push    r13
0x18000be88  push    r14
0x18000be8a  push    r15
0x18000be8c  lea     rbp, [rsp-60h]
0x18000be91  sub     rsp, 160h
0x18000be98  mov     rax, cs:__security_cookie
0x18000be9f  xor     rax, rsp
0x18000bea2  mov     [rbp+90h+var_38], rax
0x18000bea6  mov     rbx, rcx
0x18000bea9  mov     [rbp+90h+var_88], rcx
0x18000bead  xor     ecx, ecx
0x18000beaf  mov     [rsp+190h+var_148], r8b
0x18000beb4  mov     [rsp+190h+var_118], rdx
0x18000beb9  xorps   xmm0, xmm0
0x18000bebc  mov     dil, r8b
0x18000bebf  movups  [rbp+90h+var_48], xmm0
0x18000bec3  test    rdx, rdx
0x18000bec6  jz      short loc_18000BED7
0x18000bec8  mov     rcx, rdx; pSid
0x18000becb  call    cs:__imp_GetLengthSid
0x18000bed1  mov     dword ptr [rsp+190h+Size], eax
0x18000bed5  jmp     short loc_18000BEDB
0x18000bed7  mov     dword ptr [rsp+190h+Size], ecx
0x18000bedb  call    cs:__imp_GetProcessHeap
0x18000bee1  mov     r14d, 8
0x18000bee7  mov     r8d, 0A0h; dwBytes
0x18000beed  mov     rcx, rax; hHeap
0x18000bef0  mov     edx, r14d; dwFlags
0x18000bef3  call    cs:__imp_HeapAlloc
0x18000bef9  xor     r11d, r11d
0x18000befc  lea     esi, [r14-7]
0x18000bf00  mov     r12, rax
0x18000bf03  test    rax, rax
0x18000bf06  jnz     short loc_18000BF19
0x18000bf08  mov     r13d, r11d
0x18000bf0b  mov     r14d, 0C0000017h
0x18000bf11  mov     r12d, r11d
0x18000bf14  jmp     loc_18000C1CB
0x18000bf19  movups  xmm0, cs:xmmword_18001A2C0
0x18000bf20  movups  xmmword ptr [rax], xmm0
0x18000bf23  movups  xmm1, cs:xmmword_18001A2D0
0x18000bf2a  movups  xmmword ptr [rax+10h], xmm1
0x18000bf2e  movups  xmm0, cs:xmmword_18001A2E0
0x18000bf35  movups  xmmword ptr [rax+20h], xmm0
0x18000bf39  movups  xmm1, cs:xmmword_18001A2F0
0x18000bf40  movups  xmmword ptr [rax+30h], xmm1
0x18000bf44  movups  xmm0, cs:xmmword_18001A300
0x18000bf4b  movups  xmmword ptr [rax+40h], xmm0
0x18000bf4f  movups  xmm1, cs:xmmword_18001A310
0x18000bf56  movups  xmmword ptr [rax+50h], xmm1
0x18000bf5a  movups  xmm0, cs:xmmword_18001A320
0x18000bf61  movups  xmmword ptr [rax+60h], xmm0
0x18000bf65  movups  xmm1, cs:xmmword_18001A330
0x18000bf6c  movups  xmmword ptr [rax+70h], xmm1
0x18000bf70  movups  xmm0, cs:xmmword_18001A340
0x18000bf77  movups  xmmword ptr [rax+80h], xmm0
0x18000bf7e  movups  xmm1, cs:xmmword_18001A350
0x18000bf85  movups  xmmword ptr [rax+90h], xmm1
0x18000bf8c  call    cs:__imp_GetProcessHeap
0x18000bf92  mov     r8, r14; dwBytes
0x18000bf95  mov     edx, r14d; dwFlags
0x18000bf98  mov     rcx, rax; hHeap
0x18000bf9b  call    cs:__imp_HeapAlloc
0x18000bfa1  xor     r11d, r11d
0x18000bfa4  mov     r13, rax
0x18000bfa7  test    rax, rax
0x18000bfaa  jnz     short loc_18000BFBA
0x18000bfac  mov     r14d, 0C0000017h
0x18000bfb2  mov     r13d, r11d
0x18000bfb5  jmp     loc_18000C1CB
0x18000bfba  mov     rax, cs:qword_18001A200
0x18000bfc1  mov     [r13+0], rax
0x18000bfc5  rdtsc
0x18000bfc7  shl     rdx, 20h
0x18000bfcb  or      rax, rdx
0x18000bfce  mov     rdi, rax
0x18000bfd1  test    rbx, rbx
0x18000bfd4  lea     rax, unk_180016038
0x18000bfdb  mov     edx, 7FFFFFFFh
0x18000bfe0  cmovnz  rax, rbx
0x18000bfe4  mov     r8d, edx
0x18000bfe7  mov     [rbp+90h+Src], rax
0x18000bfeb  cmp     [rax], r11w
0x18000bfef  jz      short loc_18000BFFA
0x18000bff1  add     rax, 2
0x18000bff5  sub     r8, rsi
0x18000bff8  jnz     short loc_18000BFEB
0x18000bffa  mov     rcx, rdx
0x18000bffd  mov     rax, r8
0x18000c000  sub     rcx, r8
0x18000c003  neg     rax
0x18000c006  sbb     r9, r9
0x18000c009  and     r9, rcx
0x18000c00c  test    r8, r8
0x18000c00f  jnz     short loc_18000C01C
0x18000c011  mov     r14d, 0C000003Eh
0x18000c017  jmp     loc_18000C1C6
0x18000c01c  lea     eax, ds:6[r9*2]
0x18000c024  cmp     eax, 4
0x18000c027  jb      loc_18000E3E1
0x18000c02d  or      r10d, 0FFFFFFFFh
0x18000c031  mov     [rbp+90h+lpMem], r11
0x18000c035  add     eax, 0CCh
0x18000c03a  mov     [rsp+190h+var_150], r11d
0x18000c03f  mov     ecx, 0CCh
0x18000c044  mov     [rbp+90h+var_D0], r10d
0x18000c048  cmp     eax, ecx
0x18000c04a  mov     r8d, r10d
0x18000c04d  mov     ebx, 0C0000095h
0x18000c052  mov     r15, r11
0x18000c055  cmovnb  r8d, eax
0x18000c059  mov     r9d, r11d
0x18000c05c  sbb     r14d, r14d
0x18000c05f  and     r14d, ebx
0x18000c062  add     r14d, 10000000h
0x18000c069  cmp     eax, ecx
0x18000c06b  jb      loc_18000C17B
0x18000c071  mov     r9, rdx
0x18000c074  lea     rax, unk_180016038
0x18000c07b  cmp     [rax], r11w
0x18000c07f  jz      short loc_18000C08A
0x18000c081  add     rax, 2
0x18000c085  sub     r9, rsi
0x18000c088  jnz     short loc_18000C07B
0x18000c08a  mov     rcx, rdx
0x18000c08d  mov     rax, r9
0x18000c090  sub     rcx, r9
0x18000c093  neg     rax
0x18000c096  sbb     rdx, rdx
0x18000c099  and     rdx, rcx
0x18000c09c  test    r9, r9
0x18000c09f  jnz     short loc_18000C0AC
0x18000c0a1  mov     r14d, 0C000003Eh
0x18000c0a7  jmp     loc_18000C1C2
0x18000c0ac  lea     edx, ds:6[rdx*2]
0x18000c0b3  cmp     edx, 4
0x18000c0b6  jb      loc_18000E3D9
0x18000c0bc  lea     eax, [r8+rdx]
0x18000c0c0  mov     r9d, 10000000h
0x18000c0c6  cmp     eax, r8d
0x18000c0c9  mov     edx, r10d
0x18000c0cc  cmovnb  edx, eax
0x18000c0cf  sbb     r14d, r14d
0x18000c0d2  and     r14d, ebx
0x18000c0d5  add     r14d, r9d
0x18000c0d8  cmp     eax, r8d
0x18000c0db  jb      loc_18000C178
0x18000c0e1  mov     eax, dword ptr [rsp+190h+Size]
0x18000c0e5  add     eax, 4
0x18000c0e8  mov     [rbp+90h+var_A4], eax
0x18000c0eb  cmp     eax, 4
0x18000c0ee  jb      loc_18000E3D9
0x18000c0f4  add     eax, edx
0x18000c0f6  mov     ecx, r10d
0x18000c0f9  cmp     eax, edx
0x18000c0fb  cmovnb  ecx, eax
0x18000c0fe  sbb     r14d, r14d
0x18000c101  and     r14d, ebx
0x18000c104  add     r14d, r9d
0x18000c107  cmp     eax, edx
0x18000c109  jb      short loc_18000C178
0x18000c10b  lea     eax, [rcx+8]
0x18000c10e  mov     edx, r10d
0x18000c111  cmp     eax, ecx
0x18000c113  cmovnb  edx, eax
0x18000c116  sbb     r14d, r14d
0x18000c119  and     r14d, ebx
0x18000c11c  mov     [rsp+190h+var_14C], edx
0x18000c120  add     r14d, r9d
0x18000c123  cmp     eax, ecx
0x18000c125  jb      short loc_18000C178
0x18000c127  mov     r14d, edx
0x18000c12a  call    cs:__imp_GetProcessHeap
0x18000c130  mov     r8d, r14d; dwBytes
0x18000c133  mov     edx, 8; dwFlags
0x18000c138  mov     rcx, rax; hHeap
0x18000c13b  call    cs:__imp_HeapAlloc
0x18000c141  xor     r11d, r11d
0x18000c144  mov     r15, rax
0x18000c147  test    rax, rax
0x18000c14a  jnz     short loc_18000C154
0x18000c14c  mov     r14d, 0C0000017h
0x18000c152  jmp     short loc_18000C1C2
0x18000c154  lea     rdx, [rax+4]
0x18000c158  cmp     rdx, r15
0x18000c15b  jb      loc_18000E3D1
0x18000c161  lea     rcx, [r14+rax]
0x18000c165  add     rax, 8
0x18000c169  cmp     rax, rcx
0x18000c16c  jbe     loc_18000C25D
0x18000c172  mov     r14d, 0C0000023h
0x18000c178  mov     r9d, r11d
0x18000c17b  test    r14d, r14d
0x18000c17e  js      short loc_18000C187
0x18000c180  test    r9d, r9d
0x18000c183  cmovnz  r14d, r9d
0x18000c187  test    r15, r15
0x18000c18a  jz      short loc_18000C1A0
0x18000c18c  call    cs:__imp_GetProcessHeap
0x18000c192  mov     r8, r15; lpMem
0x18000c195  xor     edx, edx; dwFlags
0x18000c197  mov     rcx, rax; hHeap
0x18000c19a  call    cs:__imp_HeapFree
0x18000c1a0  mov     rbx, [rbp+90h+lpMem]
0x18000c1a4  test    rbx, rbx
0x18000c1a7  jz      short loc_18000C1BD
0x18000c1a9  call    cs:__imp_GetProcessHeap
0x18000c1af  mov     r8, rbx; lpMem
0x18000c1b2  xor     edx, edx; dwFlags
0x18000c1b4  mov     rcx, rax; hHeap
0x18000c1b7  call    cs:__imp_HeapFree
0x18000c1bd  mov     esi, 1
0x18000c1c2  mov     rbx, [rbp+90h+var_88]
0x18000c1c6  mov     dil, [rsp+190h+var_148]
0x18000c1cb  xor     r15d, r15d
0x18000c1ce  test    r12, r12
0x18000c1d1  jz      short loc_18000C1E7
0x18000c1d3  call    cs:__imp_GetProcessHeap
0x18000c1d9  mov     r8, r12; lpMem
0x18000c1dc  xor     edx, edx; dwFlags
0x18000c1de  mov     rcx, rax; hHeap
0x18000c1e1  call    cs:__imp_HeapFree
0x18000c1e7  test    r13, r13
0x18000c1ea  jz      short loc_18000C200
0x18000c1ec  call    cs:__imp_GetProcessHeap
0x18000c1f2  mov     r8, r13; lpMem
0x18000c1f5  xor     edx, edx; dwFlags
0x18000c1f7  mov     rcx, rax; hHeap
0x18000c1fa  call    cs:__imp_HeapFree
0x18000c200  test    r14d, r14d
0x18000c203  js      loc_18000E49E
0x18000c209  xor     ecx, ecx; Time
0x18000c20b  call    cs:__imp__time64
0x18000c211  mov     edx, dword ptr [rbp+90h+var_48+4]
0x18000c214  mov     r8, rax
0x18000c217  test    dl, 20h
0x18000c21a  jz      loc_18000E3EC
0x18000c220  mov     [rsp+190h+var_160], edx
0x18000c224  lea     rax, aInvokingLicens_2; "Invoking license manager because licens"...
0x18000c22b  mov     [rsp+190h+var_168], rbx
0x18000c230  lea     rdx, aOnecoreuapEndu; "onecoreuap\\enduser\\winstore\\licensem"...
0x18000c237  lea     r9, aInvokelicensem; "InvokeLicenseManagerRequired"
0x18000c23e  mov     [rsp+190h+var_170], rax; unsigned __int16 *
0x18000c243  mov     r8d, 138h; unsigned int
0x18000c249  mov     ecx, 3; unsigned int
0x18000c24e  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x18000c253  mov     ecx, 1
0x18000c258  jmp     loc_18000E504
0x18000c25d  mov     dword ptr [r15], 4
0x18000c264  mov     dword ptr [rdx], 6Dh ; 'm'
0x18000c26a  test    r12, r12
0x18000c26d  jz      loc_18000E3C6
0x18000c273  mov     r10d, 0A0h
0x18000c279  test    r15, r15
0x18000c27c  jnz     short loc_18000C29B
0x18000c27e  mov     eax, [rsp+190h+var_14C]
0x18000c282  lea     r14d, [rax+4]
0x18000c286  add     r14d, r10d
0x18000c289  cmp     r14d, eax
0x18000c28c  jb      loc_18000E3D1
0x18000c292  lea     r8d, [r15+8]
0x18000c296  jmp     loc_18000C31C
0x18000c29b  mov     r8d, 8
0x18000c2a1  mov     rdx, r15
0x18000c2a4  mov     [rbp+90h+var_A8], r8d
0x18000c2a8  mov     ecx, r11d
0x18000c2ab  mov     eax, [rdx]
0x18000c2ad  add     eax, 4
0x18000c2b0  cmp     eax, 4
0x18000c2b3  jb      loc_18000E3D1
0x18000c2b9  mov     r9d, eax
0x18000c2bc  add     r9, rdx
0x18000c2bf  cmp     r9, rdx
0x18000c2c2  jb      loc_18000E3D1
0x18000c2c8  add     ecx, esi
0x18000c2ca  mov     rdx, r9
0x18000c2cd  cmp     ecx, esi
0x18000c2cf  jb      short loc_18000C2AB
0x18000c2d1  add     r9, 4
0x18000c2d5  cmp     r9, rdx
0x18000c2d8  jb      loc_18000E3D1
0x18000c2de  mov     eax, [rsp+190h+var_14C]
0x18000c2e2  mov     r14d, eax
0x18000c2e5  mov     r10d, r10d
0x18000c2e8  lea     rcx, [r15+rax]
0x18000c2ec  lea     rax, [r10+4]
0x18000c2f0  add     rax, rdx
0x18000c2f3  cmp     rax, rcx
0x18000c2f6  ja      loc_18000C172
0x18000c2fc  mov     dword ptr [rdx], 0A0h
0x18000c302  test    r12, r12
0x18000c305  jz      short loc_18000C31C
0x18000c307  mov     r8d, r10d; Size
0x18000c30a  mov     rdx, r12; Src
0x18000c30d  mov     rcx, r9; void *
  ... truncated ...
```
