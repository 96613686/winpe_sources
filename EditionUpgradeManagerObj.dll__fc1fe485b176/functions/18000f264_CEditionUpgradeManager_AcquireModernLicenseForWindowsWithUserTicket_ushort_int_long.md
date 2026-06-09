# CEditionUpgradeManager::AcquireModernLicenseForWindowsWithUserTicket(ushort *,int,long *)

- ea: `0x18000f264`
- end: `0x1800117a0`
- name: `?AcquireModernLicenseForWindowsWithUserTicket@CEditionUpgradeManager@@AEAAJPEAGHPEAJ@Z`
- size: `9532`
- prototype: `__int64 __fastcall(CEditionUpgradeManager *this, unsigned __int16 *, int, int *)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x18000f220`
- `0x1800117b0`

## callees

- `0x180001ac0`
- `0x1800090dc`
- `0x180009480`
- `0x18000f264`
- `0x1800131a4`
- `0x180013674`
- `0x180022088`
- `0x18002295c`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800106a3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800106a3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800106dc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800106dc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f56b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f584`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f6c4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f6e5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010068`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800101e4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010215`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010246`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010269`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800102ba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800102ec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001031b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001034a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001036d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001053f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010a3a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010a66`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010a92`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010ab3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010b62`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010b8f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010bbc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010bdd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800111a9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011474`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001149d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800114c1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800114e5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011501`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011522`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011543`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011570`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011594`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800115b8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800115d4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800115f4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f56b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f584`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f6c4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f6e5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010068`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800101e4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010215`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010246`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010269`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800102ba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800102ec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001031b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001034a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001036d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001053f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010a3a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010a66`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010a92`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010ab3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010b62`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010b8f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010bbc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010bdd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800111a9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011474`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001149d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800114c1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800114e5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011501`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011522`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011543`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011570`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011594`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800115b8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800115d4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800115f4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f30c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f3b0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f533`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000fba5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000fc43`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001002f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001009e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800100f3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001019b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800103e5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180010623`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800108af`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001090c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180010968`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800109bd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180010c36`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001137e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f30c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f3b0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f533`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000fba5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000fc43`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001002f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001009e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800100f3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001019b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800103e5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180010623`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800108af`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001090c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180010968`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800109bd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180010c36`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001137e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f2f4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f3a1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f522`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f55d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f576`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f6b6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f6d7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fb94`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fc34`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001001d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001005a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001008d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800100df`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010188`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800101d4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010205`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010236`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010259`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800102ab`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800102dc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001030b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001033a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001035d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800103d4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001052f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010612`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010899`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800108f9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010955`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800109ae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010a2b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010a57`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010a83`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010aa4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010b53`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010b80`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010bad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010bce`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010c27`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011199`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001136c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011466`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001148f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800114b3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800114d7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800114f3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011514`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011535`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011562`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011586`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800115aa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800115c6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800115e6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f2f4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f3a1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f522`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f55d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f576`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f6b6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f6d7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fb94`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fc34`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001001d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001005a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001008d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800100df`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010188`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800101d4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010205`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010236`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010259`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800102ab`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800102dc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001030b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001033a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001035d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800103d4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001052f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010612`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010899`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800108f9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010955`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800109ae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010a2b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010a57`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010a83`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010aa4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010b53`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010b80`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010bad`

## string_xrefs

- `0x180010695`: `ntdll.dll`

## pseudocode

```c
__int64 __fastcall CEditionUpgradeManager::AcquireModernLicenseForWindowsWithUserTicket(
        CEditionUpgradeManager *this,
        unsigned __int16 *a2,
        int a3,
        int *a4)
{
  int *v4; // rdi
  int v5; // esi
  unsigned __int16 *v6; // rbx
  unsigned int v7; // ebx
  __int64 v8; // rcx
  int v9; // eax
  unsigned int v10; // ecx
  HANDLE ProcessHeap; // rax
  _OWORD *v12; // rax
  unsigned __int64 v13; // rcx
  void *v14; // r12
  void *v15; // r13
  int v16; // r14d
  HANDLE v17; // rax
  _QWORD *v18; // rax
  unsigned __int64 v19; // rdi
  _WORD *v20; // rax
  __int64 v21; // r8
  __int64 v22; // r9
  unsigned int v23; // eax
  unsigned int v24; // r8d
  unsigned __int64 v25; // r15
  int v26; // r9d
  __int64 v27; // r9
  const WCHAR *v28; // rax
  unsigned int v29; // edx
  unsigned int v30; // eax
  unsigned int v31; // edx
  unsigned int v32; // eax
  unsigned int v33; // eax
  __int64 v34; // rsi
  HANDLE v35; // rax
  char *v36; // rax
  HANDLE v37; // rax
  HANDLE v38; // rax
  int v39; // eax
  CEditionUpgradeManager *v40; // rcx
  char *v41; // rdx
  unsigned int v42; // eax
  char *v43; // r9
  char *v44; // r9
  HANDLE v45; // rax
  HANDLE v46; // rax
  _DWORD *v47; // rdx
  unsigned int v48; // eax
  unsigned __int64 v49; // rdx
  unsigned int v50; // eax
  unsigned int v51; // edx
  _DWORD *v52; // r8
  unsigned int v53; // eax
  _WORD *v54; // rax
  __int64 v55; // r9
  unsigned int v56; // esi
  unsigned __int64 v57; // r10
  int v58; // eax
  unsigned int v59; // r10d
  unsigned int v60; // r10d
  unsigned int *v61; // r9
  unsigned int i; // ecx
  unsigned int v63; // eax
  __int64 v64; // rdx
  const WCHAR *v65; // rax
  unsigned __int64 v66; // r9
  __int64 v67; // r8
  unsigned int v68; // r8d
  unsigned int v69; // eax
  _DWORD *v70; // rdx
  unsigned int v71; // r9d
  unsigned int v72; // eax
  unsigned int v73; // esi
  _DWORD *v74; // rdx
  unsigned int n; // r8d
  unsigned int v76; // eax
  unsigned int ii; // r14d
  _DWORD *v78; // rdx
  unsigned int v79; // r8d
  unsigned int v80; // eax
  unsigned int v81; // eax
  HANDLE v82; // rax
  _DWORD *v83; // rax
  unsigned __int64 v84; // rsi
  unsigned int *v85; // rax
  __int64 v86; // r14
  const void **v87; // rbx
  HANDLE v88; // rax
  _BYTE *v89; // rdx
  unsigned __int8 v90; // al
  unsigned __int64 j; // rcx
  unsigned __int8 *v92; // r15
  _BYTE *v93; // r13
  unsigned int v94; // r10d
  int v95; // edx
  int v96; // edi
  int v97; // ebx
  int v98; // edi
  int v99; // ebx
  int v100; // r8d
  unsigned int v101; // r10d
  int v102; // r11d
  int v103; // r9d
  int v104; // r10d
  unsigned int v105; // r8d
  int v106; // edx
  int v107; // r8d
  int v108; // r9d
  int v109; // r10d
  int v110; // r8d
  unsigned int v111; // r9d
  unsigned int v112; // r10d
  int v113; // r8d
  int v114; // r9d
  int v115; // r10d
  int v116; // r8d
  int v117; // r9d
  int v118; // r11d
  int v119; // r8d
  int v120; // r10d
  unsigned int v121; // r9d
  int v122; // r8d
  HANDLE v123; // rax
  _DWORD *v124; // rax
  int v125; // r14d
  HANDLE v126; // rax
  HANDLE v127; // rax
  void *v128; // rcx
  _QWORD *v129; // rax
  HANDLE v130; // rax
  _OWORD *v131; // rcx
  HANDLE v132; // rax
  _QWORD *v133; // rax
  HANDLE v134; // rax
  HANDLE v135; // rax
  HANDLE v136; // rax
  HANDLE v137; // rax
  HANDLE v138; // rax
  int v139; // eax
  unsigned int v140; // edx
  unsigned int v141; // ebx
  HANDLE v142; // rax
  char *v143; // rax
  char *v144; // rcx
  char *v145; // rcx
  _DWORD *v146; // r8
  int v147; // r10d
  _DWORD *v148; // r9
  HANDLE v149; // rax
  _DWORD *v150; // rax
  _DWORD *v151; // rdx
  unsigned int v152; // eax
  unsigned int v153; // ebx
  HANDLE v154; // rax
  unsigned int *v155; // rax
  bool v156; // zf
  __int128 v157; // rax
  int LastError; // eax
  bool v159; // sf
  FARPROC ProcAddress; // rax
  unsigned int v161; // r8d
  char *v162; // rax
  __int64 v163; // r9
  char *v164; // rax
  unsigned int v165; // r10d
  unsigned int *v166; // rax
  unsigned int v167; // r11d
  HANDLE v168; // rax
  _QWORD *v169; // rax
  _QWORD *v170; // rbx
  HANDLE v171; // rax
  void *v172; // rax
  HANDLE v173; // rax
  void *v174; // rax
  HANDLE v175; // rax
  void *v176; // rax
  _QWORD *v177; // rax
  HANDLE v178; // rax
  HANDLE v179; // rax
  HANDLE v180; // rax
  HANDLE v181; // rax
  unsigned int *v182; // rdx
  int v183; // ecx
  unsigned int *v184; // rax
  HANDLE v185; // rax
  HANDLE v186; // rax
  HANDLE v187; // rax
  HANDLE v188; // rax
  HANDLE v189; // rax
  _DWORD *v190; // r10
  unsigned __int8 v191; // dl
  unsigned __int64 v192; // r11
  unsigned int v193; // edx
  int v194; // r11d
  unsigned __int8 *v195; // r8
  int v196; // r10d
  int v197; // ecx
  int v198; // ecx
  unsigned int v199; // r9d
  _BYTE *v200; // r10
  int v201; // r8d
  unsigned int v202; // edx
  char v203; // r11
  unsigned int v204; // eax
  int v205; // r10d
  unsigned __int8 *v206; // rdx
  _BYTE *v207; // r14
  int v208; // r15d
  int v209; // r13d
  int v210; // eax
  int v211; // esi
  int v212; // edi
  int v213; // esi
  int v214; // ecx
  int v215; // edi
  unsigned int v216; // r9d
  int v217; // r10d
  unsigned int v218; // ecx
  int v219; // r9d
  int v220; // r10d
  unsigned int v221; // ecx
  int v222; // r9d
  int v223; // r11d
  int v224; // ebx
  unsigned int v225; // r10d
  int v226; // ecx
  int v227; // r9d
  unsigned int v228; // r10d
  int v229; // ecx
  int v230; // r9d
  int v231; // r10d
  int v232; // ecx
  unsigned int v233; // r9d
  int v234; // r10d
  int v235; // ecx
  int v236; // r9d
  unsigned int v237; // r10d
  int v238; // ecx
  int v239; // r9d
  unsigned __int64 m; // rax
  HANDLE v241; // rax
  unsigned int *v242; // rdx
  _DWORD *v243; // r9
  const void *v244; // r11
  unsigned __int64 v245; // rax
  _DWORD *v246; // r9
  HANDLE v247; // rax
  _DWORD *v248; // rax
  HANDLE v249; // rax
  void *v250; // rsi
  HANDLE v251; // rax
  void *v252; // rsi
  HANDLE v253; // rax
  void *v254; // rsi
  HANDLE v255; // rax
  HANDLE v256; // rax
  HANDLE v257; // rax
  HANDLE v258; // rax
  void *v259; // rsi
  HANDLE v260; // rax
  void *v261; // rsi
  HANDLE v262; // rax
  void *v263; // rsi
  HANDLE v264; // rax
  HANDLE v265; // rax
  HANDLE v266; // rax
  int *v267; // r14
  _DWORD *v268; // rax
  int v269; // r8d
  _DWORD *v270; // rdx
  _QWORD *v271; // rdx
  _DWORD *v272; // rax
  int v273; // edx
  int v275; // [rsp+30h] [rbp-D0h]
  int v276; // [rsp+30h] [rbp-D0h]
  int v277; // [rsp+30h] [rbp-D0h]
  _QWORD *v278; // [rsp+38h] [rbp-C8h]
  char *v279; // [rsp+38h] [rbp-C8h]
  unsigned int v280; // [rsp+40h] [rbp-C0h]
  unsigned int v281; // [rsp+40h] [rbp-C0h]
  unsigned int v282; // [rsp+40h] [rbp-C0h]
  unsigned int v283; // [rsp+40h] [rbp-C0h]
  void *v284; // [rsp+48h] [rbp-B8h]
  int v285; // [rsp+50h] [rbp-B0h]
  unsigned int v286; // [rsp+50h] [rbp-B0h]
  unsigned int k; // [rsp+50h] [rbp-B0h]
  unsigned int v288; // [rsp+50h] [rbp-B0h]
  unsigned int v289; // [rsp+50h] [rbp-B0h]
  int v290; // [rsp+50h] [rbp-B0h]
  int v291; // [rsp+50h] [rbp-B0h]
  unsigned int *v292; // [rsp+58h] [rbp-A8h]
  LPVOID v293; // [rsp+60h] [rbp-A0h]
  void *v294; // [rsp+60h] [rbp-A0h]
  void *v295; // [rsp+60h] [rbp-A0h]
  void *v296; // [rsp+60h] [rbp-A0h]
  char *v297; // [rsp+60h] [rbp-A0h]
  char *v298; // [rsp+60h] [rbp-A0h]
  char *v299; // [rsp+60h] [rbp-A0h]
  _DWORD *v300; // [rsp+60h] [rbp-A0h]
  unsigned int *v301; // [rsp+60h] [rbp-A0h]
  unsigned int *v302; // [rsp+60h] [rbp-A0h]
  unsigned __int8 *v303; // [rsp+60h] [rbp-A0h]
  LPVOID v304; // [rsp+60h] [rbp-A0h]
  _DWORD *v305; // [rsp+68h] [rbp-98h]
  const void **v306; // [rsp+70h] [rbp-90h]
  unsigned __int64 v307; // [rsp+78h] [rbp-88h]
  unsigned __int64 v308; // [rsp+78h] [rbp-88h]
  void *v309; // [rsp+80h] [rbp-80h]
  void *v310; // [rsp+80h] [rbp-80h]
  int v311; // [rsp+88h] [rbp-78h]
  unsigned int v312; // [rsp+88h] [rbp-78h]
  unsigned int v313; // [rsp+88h] [rbp-78h]
  _QWORD *v314; // [rsp+88h] [rbp-78h]
  char v315; // [rsp+88h] [rbp-78h]
  void *v316; // [rsp+90h] [rbp-70h]
  unsigned __int64 v317; // [rsp+98h] [rbp-68h]
  unsigned __int64 v318; // [rsp+98h] [rbp-68h]
  unsigned int v319; // [rsp+A0h] [rbp-60h]
  unsigned int *v320; // [rsp+A0h] [rbp-60h]
  __int64 v321; // [rsp+A0h] [rbp-60h]
  SIZE_T v322; // [rsp+A0h] [rbp-60h]
  SIZE_T dwBytes; // [rsp+A8h] [rbp-58h]
  unsigned int dwBytesa; // [rsp+A8h] [rbp-58h]
  _DWORD *dwBytesb; // [rsp+A8h] [rbp-58h]
  SIZE_T dwBytesc; // [rsp+A8h] [rbp-58h]
  unsigned int dwBytesd; // [rsp+A8h] [rbp-58h]
  SIZE_T dwBytese; // [rsp+A8h] [rbp-58h]
  SIZE_T dwBytesf; // [rsp+A8h] [rbp-58h]
  unsigned int *v330; // [rsp+B0h] [rbp-50h]
  SIZE_T v331; // [rsp+B8h] [rbp-48h]
  void *v332; // [rsp+B8h] [rbp-48h]
  void *v333; // [rsp+B8h] [rbp-48h]
  void *v334; // [rsp+B8h] [rbp-48h]
  void *v335; // [rsp+B8h] [rbp-48h]
  void *v336; // [rsp+B8h] [rbp-48h]
  void *v337; // [rsp+B8h] [rbp-48h]
  SIZE_T v338; // [rsp+B8h] [rbp-48h]
  SIZE_T v339; // [rsp+B8h] [rbp-48h]
  SIZE_T v340; // [rsp+B8h] [rbp-48h]
  __int64 v341; // [rsp+C0h] [rbp-40h]
  unsigned __int8 *v342; // [rsp+C0h] [rbp-40h]
  int v343; // [rsp+C8h] [rbp-38h]
  int v344; // [rsp+CCh] [rbp-34h]
  _BYTE *v345; // [rsp+D0h] [rbp-30h]
  unsigned int v346; // [rsp+D0h] [rbp-30h]
  int v347; // [rsp+D0h] [rbp-30h]
  char *v348; // [rsp+D8h] [rbp-28h]
  _BYTE *v349; // [rsp+D8h] [rbp-28h]
  _DWORD *lpMem; // [rsp+E8h] [rbp-18h]
  SIZE_T Size; // [rsp+F0h] [rbp-10h]
  SIZE_T Sizea; // [rsp+F0h] [rbp-10h]
  int v353; // [rsp+F8h] [rbp-8h] BYREF
  int v354; // [rsp+FCh] [rbp-4h]
  int *v355; // [rsp+100h] [rbp+0h]
  unsigned __int16 *v356; // [rsp+108h] [rbp+8h]
  HMODULE phModule; // [rsp+110h] [rbp+10h] BYREF
  __int128 v358; // [rsp+118h] [rbp+18h] BYREF
  __int128 v359; // [rsp+128h] [rbp+28h]
  __int128 v360; // [rsp+148h] [rbp+48h]
  _BYTE Src[144]; // [rsp+160h] [rbp+60h] BYREF

  v355 = a4;
  v354 = a3;
  v4 = a4;
  v356 = a2;
  v5 = a3;
  v6 = a2;
  v360 = 0;
  if ( !a4 )
  {
    v7 = -2147024809;
    v8 = 2147942487LL;
LABEL_3:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v8);
    goto LABEL_449;
  }
  v353 = 65;
  v9 = ConvertPartNumberToPfn(this, a2, &v353, Src);
  v353 = v9;
  if ( v9 < 0 )
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v9);
    v7 = v10;
    goto LABEL_449;
  }
  ProcessHeap = GetProcessHeap();
  v12 = HeapAlloc(ProcessHeap, 8u, 0xA0u);
  v14 = v12;
  if ( !v12 )
  {
    v15 = 0;
    v16 = -1073741801;
    v14 = 0;
    goto LABEL_39;
  }
  *v12 = `WarbirdUmGetDecryptionCipher'::`2'::DecryptionCipher;
  v12[1] = xmmword_18002F600;
  v12[2] = xmmword_18002F610;
  v12[3] = xmmword_18002F620;
  v12[4] = xmmword_18002F630;
  v12[5] = xmmword_18002F640;
  v12[6] = xmmword_18002F650;
  v12[7] = xmmword_18002F660;
  v12[8] = xmmword_18002F670;
  v12[9] = xmmword_18002F680;
  v17 = GetProcessHeap();
  v18 = HeapAlloc(v17, 8u, 8u);
  v15 = v18;
  if ( !v18 )
  {
    v16 = -1073741801;
    v15 = 0;
    goto LABEL_39;
  }
  *v18 = `WarbirdUmGetDecryptionKey'::`2'::nDecryptionKey;
  v19 = __rdtsc();
  v20 = Src;
  v21 = 0x7FFFFFFF;
  do
  {
    if ( !*v20 )
      break;
    ++v20;
    --v21;
  }
  while ( v21 );
  LODWORD(v13) = 0x7FFFFFFF - v21;
  v22 = (0x7FFFFFFF - v21) & -(__int64)(v21 != 0);
  if ( v21 )
  {
    if ( (unsigned int)(2 * v22 + 6) < 4 )
    {
      v16 = -1073741675;
      goto LABEL_38;
    }
    lpMem = 0;
    v23 = 2 * v22 + 210;
    LODWORD(v13) = 204;
    v344 = -1;
    v24 = -1;
    v25 = 0;
    if ( v23 >= 0xCC )
      v24 = 2 * v22 + 210;
    v26 = 0;
    v16 = v23 < 0xCC ? -805306219 : 0x10000000;
    if ( v23 < 0xCC )
      goto LABEL_59;
    v27 = 0x7FFFFFFF;
    v28 = &LocaleName;
    do
    {
      if ( !*v28 )
        break;
      ++v28;
      --v27;
    }
    while ( v27 );
    LODWORD(v13) = 0x7FFFFFFF - v27;
    if ( !v27 )
    {
      v16 = -1073741762;
LABEL_37:
      v6 = v356;
      goto LABEL_38;
    }
    v29 = 2 * ((0x7FFFFFFF - v27) & ((unsigned __int128)-(__int128)(unsigned __int64)v27 >> 64)) + 6;
    if ( v29 < 4 )
    {
      v16 = -1073741675;
      goto LABEL_37;
    }
    v30 = v24 + v29;
    v31 = -1;
    if ( v30 >= v24 )
      v31 = v30;
    v16 = v30 < v24 ? -805306219 : 0x10000000;
    if ( v30 < v24 )
      goto LABEL_442;
    v32 = v31 + 4;
    LODWORD(v13) = -1;
    if ( v31 + 4 >= v31 )
      LODWORD(v13) = v31 + 4;
    v16 = v32 < v31 ? -805306219 : 0x10000000;
    if ( v32 < v31 )
      goto LABEL_442;
    v33 = v13 + 8;
    v34 = 0xFFFFFFFFLL;
    if ( (int)v13 + 8 >= (unsigned int)v13 )
      v34 = v33;
    v16 = v33 < (unsigned int)v13 ? -805306219 : 0x10000000;
    if ( v33 < (unsigned int)v13 )
      goto LABEL_442;
    v35 = GetProcessHeap();
    v36 = (char *)HeapAlloc(v35, 8u, (unsigned int)v34);
    v25 = (unsigned __int64)v36;
    if ( !v36 )
    {
      v16 = -1073741801;
LABEL_36:
      v5 = v354;
      goto LABEL_37;
    }
    if ( v36 + 4 < v36 )
      goto LABEL_441;
    LODWORD(v13) = v34 + (_DWORD)v36;
    if ( v36 + 8 > &v36[v34] )
    {
LABEL_48:
      v16 = -1073741789;
LABEL_442:
      v26 = 0;
LABEL_59:
      if ( v16 >= 0 )
      {
LABEL_60:
        if ( v26 )
          v16 = v26;
      }
      goto LABEL_62;
    }
    *(_DWORD *)v36 = 4;
    *((_DWORD *)v36 + 1) = 109;
    if ( !v14 )
    {
      v16 = -1073741811;
      goto LABEL_442;
    }
    v41 = v36;
    LODWORD(v13) = 0;
    do
    {
      v42 = *(_DWORD *)v41 + 4;
      if ( *(_DWORD *)v41 >= 0xFFFFFFFC )
        goto LABEL_441;
      v43 = &v41[v42];
      if ( v43 < v41 )
        goto LABEL_441;
      LODWORD(v13) = v13 + 1;
      v41 += v42;
    }
    while ( !(_DWORD)v13 );
    v44 = v43 + 4;
    if ( v44 < v41 )
    {
LABEL_441:
      v16 = -1073741675;
      goto LABEL_442;
    }
    LODWORD(v13) = v25 + v34;
    if ( (unsigned __int64)(v41 + 164) > v25 + v34 )
      goto LABEL_48;
    *(_DWORD *)v41 = 160;
    memcpy_0(v44, v14, 0xA0u);
    if ( !v15 )
    {
      v16 = -1073741811;
LABEL_58:
      v26 = 0;
      goto LABEL_59;
    }
    if ( v25 )
    {
      v47 = (_DWORD *)v25;
      LODWORD(v13) = 0;
      do
      {
        v48 = *v47 + 4;
        if ( *v47 >= 0xFFFFFFFC || (_DWORD *)((char *)v47 + v48) < v47 )
          goto LABEL_86;
        LODWORD(v13) = v13 + 1;
        v47 = (_DWORD *)((char *)v47 + v48);
      }
      while ( (unsigned int)v13 < 2 );
      if ( v47 + 1 < v47 )
        goto LABEL_86;
      v13 = v25 + (unsigned int)v34;
      if ( (unsigned __int64)(v47 + 3) > v13 )
        goto LABEL_75;
      *v47 = 8;
      memcpy_0(v47 + 1, v15, 8u);
      v49 = v25;
      LODWORD(v13) = 0;
      do
      {
        v50 = *(_DWORD *)v49 + 4;
        if ( *(_DWORD *)v49 >= 0xFFFFFFFC || v49 + v50 < v49 )
          goto LABEL_86;
        LODWORD(v13) = v13 + 1;
        v49 += v50;
      }
      while ( (unsigned int)v13 < 3 );
      if ( v49 + 4 < v49 )
        goto LABEL_86;
      v13 = v25 + (unsigned int)v34;
      if ( v49 + 12 > v13 )
        goto LABEL_75;
      *(_DWORD *)v49 = 8;
      *(_QWORD *)(v49 + 4) = v19;
      v51 = v34;
      v52 = (_DWORD *)v25;
      v280 = v34;
      LODWORD(v13) = 0;
      do
      {
        v53 = *v52 + 4;
        if ( *v52 >= 0xFFFFFFFC || (_DWORD *)((char *)v52 + v53) < v52 )
          goto LABEL_86;
        LODWORD(v13) = v13 + 1;
        v52 = (_DWORD *)((char *)v52 + v53);
      }
      while ( (unsigned int)v13 < 4 );
      if ( v52 + 1 < v52 )
        goto LABEL_86;
      v13 = v25 + (unsigned int)v34;
      if ( (unsigned __int64)(v52 + 2) > v13 )
        goto LABEL_75;
      *v52 = 4;
      v52[1] = 3;
    }
    else
    {
      if ( (int)v34 + 12 < (unsigned int)v34 )
        goto LABEL_86;
      if ( (int)v34 + 24 < (unsigned int)(v34 + 12) )
        goto LABEL_86;
      v51 = v34 + 32;
      v280 = v34 + 32;
      if ( (int)v34 + 32 < (unsigned int)(v34 + 24) )
        goto LABEL_86;
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
    LODWORD(v13) = 0x7FFFFFFF - v55;
    v57 = (0x7FFFFFFF - v55) & -(__int64)(v55 != 0);
    if ( !v55 )
      goto LABEL_121;
    v58 = v57 + 1;
    if ( v57 + 1 < v57 )
      goto LABEL_439;
    v59 = 2 * v58;
    if ( 2 * v58 )
    {
      if ( v25 )
      {
        v61 = (unsigned int *)v25;
        for ( i = 0; i < 5; ++i )
        {
          v63 = *v61 + 4;
          if ( *v61 >= 0xFFFFFFFC || (unsigned int *)((char *)v61 + v63) < v61 )
            goto LABEL_112;
          v61 = (unsigned int *)((char *)v61 + v63);
        }
        if ( v61 + 1 < v61 )
        {
LABEL_112:
          v16 = -1073741675;
          goto LABEL_115;
        }
        if ( (unsigned __int64)v61 + v59 + 4 <= v25 + v51 )
        {
          *v61 = v59;
          v16 = 0;
          memcpy_0(v61 + 1, Src, v59);
          v56 = 6;
        }
        else
        {
          v16 = -1073741789;
        }
      }
      else
      {
        v60 = v59 + 4;
        if ( v60 >= 4 )
        {
          v13 = v51 + v60;
          if ( (unsigned int)v13 < v51 )
          {
            v13 = 0xFFFFFFFFLL;
            v16 = -1073741675;
            v280 = -1;
          }
          else
          {
            v280 = v51 + v60;
            v56 = 6;
            v16 = 0;
          }
LABEL_116:
          if ( v16 < 0 )
            goto LABEL_62;
          v64 = 0x7FFFFFFF;
          v65 = &LocaleName;
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
            v16 = -1073741762;
            goto LABEL_62;
          }
          if ( v66 + 1 < v66 )
          {
LABEL_439:
            v16 = -1073741675;
            goto LABEL_62;
          }
          v67 = (unsigned int)(2 * (v66 + 1));
          if ( (_DWORD)v67 )
          {
            if ( v25 )
            {
              v70 = (_DWORD *)v25;
              v71 = 0;
              while ( 1 )
              {
                v72 = *v70 + 4;
                if ( *v70 >= 0xFFFFFFFC || (_DWORD *)((char *)v70 + v72) < v70 )
                  break;
                ++v71;
                v70 = (_DWORD *)((char *)v70 + v72);
                if ( v71 >= v56 )
                {
                  if ( v70 + 1 < v70 )
                    break;
                  v13 += v25;
                  if ( (unsigned __int64)v70 + v67 + 4 <= v13 )
                  {
                    *v70 = v67;
                    v16 = 0;
                    memcpy_0(v70 + 1, &LocaleName, (unsigned int)v67);
                    ++v56;
                  }
                  else
                  {
                    v16 = -1073741789;
                  }
                  goto LABEL_139;
                }
              }
            }
            else
            {
              v68 = v67 + 4;
              if ( v68 >= 4 )
              {
                v69 = v13 + v68;
                if ( (unsigned int)v13 + v68 < (unsigned int)v13 )
                {
                  v69 = -1;
                  v16 = -1073741675;
                }
                else
                {
                  ++v56;
                  v16 = 0;
                }
LABEL_140:
                if ( v16 < 0 )
                  goto LABEL_62;
                if ( !v25 )
                {
                  LODWORD(v13) = v69 + 4;
                  if ( v69 + 4 < v69 )
                    goto LABEL_86;
                  v73 = v56 + 1;
                  ii = v69 + 12;
                  if ( v69 + 12 < v69 + 4 )
                    goto LABEL_86;
LABEL_160:
                  v281 = v73 + 1;
                  v293 = (LPVOID)__rdtsc();
                  LODWORD(v13) = ii + 8;
                  if ( ii >= 0xFFFFFFF8 || (v81 = (ii + 15) & 0xFFFFFFF8, v319 = v81, v81 < (unsigned int)v13) )
                  {
                    v16 = -805306219;
                    goto LABEL_62;
                  }
                  v343 = 0;
                  dwBytes = v81;
                  v82 = GetProcessHeap();
                  v83 = HeapAlloc(v82, 8u, (ii + 15) & 0xFFFFFFF8);
                  v84 = (unsigned __int64)v83;
                  if ( !v83 )
                  {
                    v16 = -805306345;
                    goto LABEL_408;
                  }
                  *v83 = v281;
                  v85 = v83 + 1;
                  if ( v84 + 4 < v84 || (*v85 = ii, v84 + 8 < v84 + 4) )
                  {
                    v126 = GetProcessHeap();
                    HeapFree(v126, 0, (LPVOID)v84);
                    v16 = -805306219;
                    goto LABEL_408;
                  }
                  *(_QWORD *)(v84 + dwBytes - 8) = v293;
                  memcpy_0((void *)(v84 + 8), (const void *)v25, ii);
                  v86 = v319;
                  v87 = 0;
                  v284 = 0;
                  v292 = 0;
                  v330 = 0;
                  v341 = 0;
                  if ( !v319
                    || (dwBytesa = v319 + 8,
                        v88 = GetProcessHeap(),
                        v345 = HeapAlloc(v88, 0, v319 + 8LL),
                        (v89 = v345) == 0) )
                  {
                    v16 = -805306367;
                    goto LABEL_385;
                  }
                  v90 = 0;
                  for ( j = 0; j < v319; v90 ^= *(_BYTE *)(v84 + j++) )
                    ;
                  v309 = v15;
                  v307 = v19;
                  v317 = v25;
                  if ( (unsigned __int64)v319 >> 3 )
                  {
                    v92 = (unsigned __int8 *)v84;
                    v93 = v345;
                    v94 = -1;
                    v348 = 0;
                    v275 = 0;
                    v311 = 0;
                    v285 = 0;
                    do
                    {
                      v95 = v92[1];
                      v96 = *v92;
                      v97 = v92[4];
                      v92 += 8;
                      v98 = *(v92 - 5) | ((*(v92 - 6) | ((v95 | (v96 << 8)) << 8)) << 8);
                      v99 = *(v92 - 1) | ((*(v92 - 2) | ((*(v92 - 3) | (v97 << 8)) << 8)) << 8);
                      v100 = v94 ^ v99;
                      v101 = v285 ^ v98 ^ ((v94 ^ v99) - 19032) ^ 0xC81ECB17;
                      v102 = v100 ^ (__ROR4__(v101, 7) + 45493 * __ROR4__(v101 ^ 0xC81ECB17, 15));
                      v103 = v101 ^ (51991 * __ROR4__(v102 - 1313519016, 9) - __ROR4__(v102, 10));
                      v104 = v102 ^ (__ROR4__(v103, 27) + 51230 * __ROR4__(v103 ^ 0xCB17, 28));
                      v105 = v103 ^ (-937506025 - (v104 ^ 0xB1B54A58));
                      v106 = v105 ^ (19032 * (__ROR4__(v104 ^ (45493 * (v105 - 19032) - (v105 >> 6)), 15) ^ 0xCB17));
                      v107 = v104 ^ (45493 * (v105 - 19032) - (v105 >> 6)) ^ (51991 * (__ROR4__(~v106, 3) + 51230));
                      v108 = v106 ^ (v107 - 19032 + 937506025);
                      v109 = v107 ^ (45493 * (v108 ^ 0xC81E)) ^ __ROR4__(v108, 10);
                      v110 = v108 ^ __ROR4__(v109, 3) ^ (51991 * __ROR4__(v109 ^ 0x4A58, 26));
                      v111 = v109 ^ (19032 * (__ROR4__(v110, 15) - 51230));
                      v112 = v110
                           ^ (19032 * (v111 ^ 0xC81E))
                           ^ ((v111 ^ (v111 >> 14)) >> 1)
                           ^ (19032 * ((8 * (v111 - 51991)) | ((v111 - 51991) >> 29)));
                      v113 = v111 ^ (45493 * (v112 - 51991) - (v112 >> 13));
                      v114 = v112 ^ __ROR4__(v113, 11) ^ (51991 * __ROR4__(-1313519016 - v113, 9));
                      v115 = v113 ^ (v114 + 1313467786);
                      v116 = v114 ^ (19032 * (v115 ^ 0xB1B5) - __ROR4__(v115, 7));
                      v117 = v115 ^ (45493 * __ROR4__(v116 ^ 0xC81E, 28) - __ROR4__(v116, 16));
                      v118 = v116 ^ (__ROR4__(v117, 4) + 51991 * __ROR4__(-1313519016 - v117, 10));
                      v119 = v117 ^ __ROR4__(v118, 9) ^ (51230 * __ROR4__(v118 + 1313519016, 4));
                      v120 = v118 ^ (19032 * __ROR4__(v119 ^ 0xC81ECB17, 24) - __ROR4__(v119, 30));
                      v121 = v119 ^ (45493 * __ROR4__(-937506025 - v120, 11) - __ROR4__(v120, 12));
                      v122 = v120 ^ (v121 >> 8) ^ (51991 * (v121 ^ 0xB1B5));
                      v94 = v311 ^ v122 ^ v121 ^ 0xC81ECB17 ^ 0xB1B54A58;
                      v93[3] = v275 ^ v122;
                      v285 = v275 ^ v122;
                      v93[7] = v94;
                      v93[2] = __ROR4__(v275 ^ v122, 8);
                      v93[6] = __ROR4__(v94, 8);
                      v93[1] = __ROR4__(v275 ^ v122, 16);
                      v93[5] = __ROR4__(v94, 16);
                      *v93 = __ROR4__(v275 ^ v122, 24);
                      v93[4] = __ROR4__(v94, 24);
                      v93 += 8;
                      v275 = v98;
                      v311 = v99;
                      ++v348;
                    }
                    while ( (unsigned __int64)v348 < (unsigned __int64)v319 >> 3 );
                    v25 = v317;
                    v15 = v309;
                    v19 = v307;
                    v87 = 0;
                    v86 = v319;
                    v89 = v345;
                  }
                  *(_QWORD *)&v89[v86] = v90;
                  v123 = GetProcessHeap();
                  v124 = HeapAlloc(v123, 8u, 0x30u);
                  v278 = v124;
                  if ( !v124 )
                  {
                    v125 = -1073741801;
                    v276 = -1073741801;
                    goto LABEL_190;
                  }
                  *v124 = dwBytesa;
                  v127 = GetProcessHeap();
                  v125 = -1073741801;
                  v128 = HeapAlloc(v127, 8u, dwBytesa);
                  v129 = v278;
                  if ( v128 )
                  {
                    v278[1] = v128;
                    memcpy_0(v128, v345, dwBytesa);
                    *((_DWORD *)v278 + 4) = 160;
                    v130 = GetProcessHeap();
                    v131 = HeapAlloc(v130, 8u, 0xA0u);
                    v129 = v278;
                    if ( v131 )
                    {
                      v278[3] = v131;
                      *v131 = `WarbirdUmGetEncryptionCipher'::`2'::EncryptionCipher;
                      v131[1] = xmmword_18002F550;
                      v131[2] = xmmword_18002F560;
                      v131[3] = xmmword_18002F570;
                      v131[4] = xmmword_18002F580;
                      v131[5] = xmmword_18002F590;
                      v131[6] = xmmword_18002F5A0;
                      v131[7] = xmmword_18002F5B0;
                      v131[8] = xmmword_18002F5C0;
                      v131[9] = xmmword_18002F5D0;
                      *((_DWORD *)v278 + 8) = 8;
                      v132 = GetProcessHeap();
                      v133 = HeapAlloc(v132, 8u, 8u);
                      if ( v133 )
                      {
                        v278[5] = v133;
                        *v133 = `WarbirdUmGetEncryptionKey'::`2'::nEncryptionKey;
                        v276 = 0;
                        v87 = (const void **)v278;
                        goto LABEL_190;
                      }
                      v129 = v278;
                    }
                    v278 = v129;
                  }
                  v276 = -1073741801;
                  v294 = (void *)v129[1];
                  if ( v294 )
                  {
                    v134 = GetProcessHeap();
                    HeapFree(v134, 0, v294);
                    v129 = v278;
                    v278[1] = 0;
                  }
                  v295 = (void *)v129[3];
                  if ( v295 )
                  {
                    v135 = GetProcessHeap();
                    HeapFree(v135, 0, v295);
                    v129 = v278;
                    v278[3] = 0;
                  }
                  v296 = (void *)v129[5];
                  if ( v296 )
                  {
                    v136 = GetProcessHeap();
                    HeapFree(v136, 0, v296);
                    v278[5] = 0;
                  }
                  v137 = GetProcessHeap();
                  HeapFree(v137, 0, v278);
LABEL_190:
                  v138 = GetProcessHeap();
                  HeapFree(v138, 0, v345);
                  v306 = v87;
                  v139 = v276 | 0x10000000;
                  if ( v276 >= 0 )
                  {
                    if ( *(_DWORD *)v87 < 0xFFFFFFFC )
                    {
                      LODWORD(v13) = *(_DWORD *)v87 + 8;
                      if ( (unsigned int)v13 >= *(_DWORD *)v87 + 4 )
                      {
                        v140 = v13 + *((_DWORD *)v87 + 4);
                        dwBytesb = v87 + 2;
                        if ( v140 >= (unsigned int)v13 )
                        {
                          LODWORD(v13) = v140 + 4;
                          if ( v140 + 4 >= v140 )
                          {
                            v286 = v13 + *((_DWORD *)v87 + 8);
                            if ( v286 >= (unsigned int)v13 )
                            {
                              v141 = v13 + *((_DWORD *)v87 + 8);
                              v142 = GetProcessHeap();
                              v143 = (char *)HeapAlloc(v142, 8u, v141);
                              v87 = v306;
                              v279 = v143;
                              LODWORD(v13) = (_DWORD)v143;
                              if ( !v143 )
                              {
LABEL_197:
                                v16 = -805306345;
                                goto LABEL_218;
                              }
                              *(_DWORD *)v143 = *(_DWORD *)v306;
                              v297 = v143 + 4;
                              if ( v143 + 4 < v143 )
                              {
                                v279 = v143;
                              }
                              else
                              {
                                memcpy_0(v143 + 4, v306[1], *(unsigned int *)v306);
                                v144 = &v297[*(unsigned int *)v306];
                                if ( v144 >= v297 )
                                {
                                  *(_DWORD *)v144 = *dwBytesb;
                                  v298 = v144 + 4;
                                  if ( v144 + 4 >= v144 )
                                  {
                                    memcpy_0(v144 + 4, v306[3], (unsigned int)*dwBytesb);
                                    v145 = &v298[*dwBytesb];
                                    if ( v145 >= v298 )
                                    {
                                      *(_DWORD *)v145 = *((_DWORD *)v306 + 8);
                                      v299 = v145 + 4;
                                      if ( v145 + 4 >= v145 )
                                      {
                                        memcpy_0(v145 + 4, v306[5], *((unsigned int *)v306 + 8));
                                        if ( &v299[*((unsigned int *)v306 + 8)] >= v299 )
                                        {
                                          LODWORD(v13) = (_DWORD)v279;
                                          v284 = v279;
                                          v312 = v286;
                                          if ( !v25 || v281 <= 1 )
                                            goto LABEL_212;
                                          v146 = (_DWORD *)v25;
                                          v147 = 0;
                                          do
                                          {
                                            v148 = v146 + 1;
                                            if ( v146 + 1 < v146 )
                                              goto LABEL_383;
                                            v146 = (_DWORD *)((char *)v148 + (unsigned int)*v146);
                                            if ( v146 < v148 )
                                              goto LABEL_383;
                                            ++v147;
                                          }
                                          while ( !v147 );
                                          if ( v146 + 1 < v146 )
                                            goto LABEL_383;
                                          if ( v281 <= 2 )
                                          {
LABEL_212:
                                            v16 = -1073741811;
                                            goto LABEL_218;
                                          }
                                          v150 = (_DWORD *)v25;
                                          for ( k = 0; k < 2; ++k )
                                          {
                                            v151 = v150 + 1;
                                            if ( v150 + 1 < v150 )
                                              goto LABEL_383;
                                            v150 = (_DWORD *)((char *)v151 + (unsigned int)*v150);
                                            v300 = v150;
                                            if ( v150 < v151 )
                                              goto LABEL_383;
                                            v318 = v25;
                                          }
                                          LODWORD(v13) = (_DWORD)v150;
                                          if ( v150 + 1 < v150
                                            || *v146 >= 0xFFFFFFC0
                                            || *v146 + 68 < (unsigned int)(*v146 + 64)
                                            || (LODWORD(v13) = *v146 + 68,
                                                v152 = v13 + *v150,
                                                v288 = v152,
                                                v152 < (unsigned int)v13) )
                                          {
LABEL_383:
                                            v16 = -1073741675;
LABEL_218:
                                            if ( !v84 )
                                            {
LABEL_386:
                                              if ( v87 )
                                              {
                                                v250 = (void *)v87[1];
                                                if ( v250 )
                                                {
                                                  v251 = GetProcessHeap();
                                                  HeapFree(v251, 0, v250);
                                                  v87[1] = 0;
                                                }
                                                v252 = (void *)v87[3];
                                                if ( v252 )
                                                {
                                                  v253 = GetProcessHeap();
                                                  HeapFree(v253, 0, v252);
                                                  v87[3] = 0;
                                                }
                                                v254 = (void *)v87[5];
                                                if ( v254 )
                                                {
                                                  v255 = GetProcessHeap();
                                                  HeapFree(v255, 0, v254);
                                                  v87[5] = 0;
                                                }
                                                v256 = GetProcessHeap();
                                                HeapFree(v256, 0, v87);
                                              }
                                              if ( v284 )
                                              {
                                                v257 = GetProcessHeap();
                                                HeapFree(v257, 0, v284);
                                              }
                                              if ( v292 )
                                              {
                                                v258 = GetProcessHeap();
                                                HeapFree(v258, 0, v292);
                                              }
                                              if ( v330 )
                                              {
                                                v259 = (void *)*((_QWORD *)v330 + 1);
                                                if ( v259 )
                                                {
                                                  v260 = GetProcessHeap();
                                                  HeapFree(v260, 0, v259);
                                                  *((_QWORD *)v330 + 1) = 0;
                                                }
                                                v261 = (void *)*((_QWORD *)v330 + 3);
                                                if ( v261 )
                                                {
                                                  v262 = GetProcessHeap();
                                                  HeapFree(v262, 0, v261);
                                                  *((_QWORD *)v330 + 3) = 0;
                                                }
                                                v263 = (void *)*((_QWORD *)v330 + 5);
                                                if ( v263 )
                                                {
                                                  v264 = GetProcessHeap();
                                                  HeapFree(v264, 0, v263);
                                                  *((_QWORD *)v330 + 5) = 0;
                                                }
                                                v265 = GetProcessHeap();
                                                HeapFree(v265, 0, v330);
                                              }
                                              if ( v341 )
                                              {
                                                v266 = GetProcessHeap();
                                                HeapFree(v266, 0, (LPVOID)v341);
                                              }
LABEL_408:
                                              if ( v16 < 0 )
                                                goto LABEL_62;
                                              if ( v343 != 3 )
                                              {
LABEL_410:
                                                v16 = -1073425151;
                                                goto LABEL_62;
                                              }
                                              LODWORD(v13) = (_DWORD)lpMem;
                                              if ( !lpMem )
                                              {
                                                v16 = -1073741811;
                                                goto LABEL_62;
                                              }
                                              if ( lpMem + 1 >= lpMem )
                                              {
                                                v267 = 0;
                                                if ( *lpMem )
                                                  v267 = lpMem + 1;
                                                if ( *lpMem != 4 )
                                                {
LABEL_425:
                                                  v16 = -1073741789;
                                                  goto LABEL_62;
                                                }
                                                v16 = *v267;
                                                if ( v16 >= 0 )
                                                {
                                                  v268 = lpMem;
                                                  v269 = 0;
                                                  v26 = v16;
                                                  while ( 1 )
                                                  {
                                                    v270 = v268 + 1;
                                                    if ( v268 + 1 < v268 )
                                                      goto LABEL_439;
                                                    v268 = (_DWORD *)((char *)v270 + (unsigned int)*v268);
                                                    if ( v268 < v270 )
                                                      goto LABEL_439;
                                                    if ( ++v269 )
                                                    {
                                                      if ( v268 + 1 < v268 )
                                                        goto LABEL_439;
                                                      v271 = 0;
                                                      if ( *v268 )
                                                        v271 = v268 + 1;
                                                      if ( *v268 != 8 )
                                                        goto LABEL_425;
                                                      if ( v19 != *v271 )
                                                        goto LABEL_410;
                                                      v272 = lpMem;
                                                      v273 = 0;
                                                      while ( 1 )
                                                      {
                                                        v13 = (unsigned __int64)(v272 + 1);
                                                        if ( v272 + 1 < v272 )
                                                          goto LABEL_439;
                                                        v272 = (_DWORD *)(v13 + (unsigned int)*v272);
                                                        if ( (unsigned __int64)v272 < v13 )
                                                          goto LABEL_439;
                                                        if ( (unsigned int)++v273 >= 2 )
                                                        {
                                                          if ( v272 + 1 < v272 )
                                                            goto LABEL_439;
                                                          v13 = 0;
                                                          if ( *v272 )
                                                            v13 = (unsigned __int64)(v272 + 1);
                                                          if ( *v272 != 16 )
                                                          {
                                                            v16 = -2147024883;
                                                            goto LABEL_62;
                                                          }
                                                          v16 = 0;
                                                          v360 = *(_OWORD *)v13;
                                                          goto LABEL_60;
                                                        }
                                                      }
                                                    }
                                                  }
                                                }
LABEL_62:
                                                if ( v25 )
                                                {
                                                  v45 = GetProcessHeap();
                                                  HeapFree(v45, 0, (LPVOID)v25);
                                                }
                                                if ( lpMem )
                                                {
                                                  v46 = GetProcessHeap();
                                                  HeapFree(v46, 0, lpMem);
                                                }
                                                goto LABEL_36;
                                              }
                                              goto LABEL_439;
                                            }
LABEL_385:
                                            v249 = GetProcessHeap();
                                            HeapFree(v249, 0, (LPVOID)v84);
                                            goto LABEL_386;
                                          }
                                          if ( v152 > 0x400000 )
                                          {
                                            v16 = -2147418113;
                                            v284 = v279;
                                            goto LABEL_218;
                                          }
                                          v153 = *v146 + 68 + *v300;
                                          v154 = GetProcessHeap();
                                          v155 = (unsigned int *)HeapAlloc(v154, 8u, v153);
                                          v87 = v306;
                                          v156 = v155 == 0;
                                          v292 = v155;
                                          *((_QWORD *)&v157 + 1) = v155;
                                          *(_QWORD *)&v157 = v279;
                                          v284 = v279;
                                          if ( v156 )
                                          {
                                            v16 = -805306345;
                                            v292 = 0;
                                            goto LABEL_218;
                                          }
                                          v13 = (unsigned __int64)v279;
                                          phModule = 0;
                                          v358 = 0;
                                          v359 = 0;
                                          if ( !v279 )
                                          {
                                            v16 = -2147024809;
LABEL_382:
                                            v292 = (unsigned int *)*((_QWORD *)&v157 + 1);
                                            v284 = (void *)v13;
                                            goto LABEL_218;
                                          }
                                          v358 = v157;
                                          LODWORD(v359) = v312;
                                          *(_QWORD *)((char *)&v359 + 4) = v288;
                                          if ( GetModuleHandleExW(1u, L"ntdll.dll", &phModule)
                                            && (ProcAddress = GetProcAddress(phModule, "NtQuerySystemInformation")) != 0 )
                                          {
                                            LastError = ((__int64 (__fastcall *)(__int64, __int128 *))ProcAddress)(
                                                          134,
                                                          &v358)
                                                      | 0x10000000;
                                            if ( LastError >= 0 )
                                            {
                                              v161 = DWORD1(v359);
LABEL_247:
                                              if ( v161 < 4 )
                                              {
                                                v16 = -805306306;
                                                goto LABEL_244;
                                              }
                                              v163 = *v292;
                                              v13 = (unsigned __int64)(v292 + 1);
                                              v289 = *v292;
                                              if ( v292 + 1 < v292 )
                                                goto LABEL_379;
                                              if ( v161 - 4 < (unsigned int)v163 )
                                              {
                                                v16 = -805306306;
                                                goto LABEL_244;
                                              }
                                              Size = *v292;
                                              dwBytesc = v163 + v13;
                                              if ( v163 + v13 < v13 )
                                              {
LABEL_379:
                                                v162 = v279;
                                                v16 = -805306219;
                                                goto LABEL_245;
                                              }
                                              if ( (unsigned int)v163 >= 0xFFFFFFFC )
                                                goto LABEL_378;
                                              if ( v161 - ((_DWORD)v163 + 4) < 4 )
                                              {
LABEL_255:
                                                v164 = v279;
                                                v16 = -805306306;
LABEL_256:
                                                v284 = v164;
                                                goto LABEL_218;
                                              }
                                              v165 = *(_DWORD *)(v163 + v13);
                                              v282 = v165;
                                              v13 = dwBytesc + 4;
                                              if ( dwBytesc + 4 < dwBytesc )
                                                goto LABEL_378;
                                              v313 = v163 + 8;
                                              if ( (int)v163 + 8 < (unsigned int)(v163 + 4) )
                                                goto LABEL_378;
                                              if ( v161 - v313 < v165 )
                                                goto LABEL_255;
                                              v331 = v165;
                                              v301 = (unsigned int *)(v13 + v165);
                                              if ( (unsigned __int64)v301 < v13 )
                                                goto LABEL_378;
                                              LODWORD(v13) = v313 + v165;
                                              if ( v313 + v165 < v313 )
                                                goto LABEL_378;
                                              if ( v161 - (unsigned int)v13 < 4 )
                                                goto LABEL_255;
                                              v166 = v301;
                                              v302 = v301 + 1;
                                              if ( v302 < v166 || (v167 = v13 + 4, (int)v13 + 4 < (unsigned int)v13) )
                                              {
LABEL_378:
                                                v164 = v279;
                                                v16 = -805306219;
                                                goto LABEL_256;
                                              }
                                              LODWORD(v13) = *v166;
                                              v346 = *v166;
                                              if ( v161 - v167 < *v166 )
                                                goto LABEL_255;
                                              if ( v167 + (unsigned int)v13 < v167 )
                                              {
                                                v16 = -805306219;
                                                goto LABEL_218;
                                              }
                                              if ( v161 != v167 + (_DWORD)v13 )
                                                goto LABEL_255;
                                              v13 = v165 + (unsigned int)v163 + (unsigned int)v13 + 12LL;
                                              if ( v13 != v161 )
                                                goto LABEL_255;
                                              v168 = GetProcessHeap();
                                              v169 = HeapAlloc(v168, 8u, 0x30u);
                                              v314 = v169;
                                              v170 = v169;
                                              if ( !v169 )
                                              {
                                                v87 = v306;
                                                v284 = v279;
                                                goto LABEL_197;
                                              }
                                              v320 = 0;
                                              if ( v292 == (unsigned int *)-4LL )
                                              {
                                                *(_DWORD *)v169 = 0;
                                                v169[1] = 0;
                                                v277 = 0;
                                              }
                                              else
                                              {
                                                *(_DWORD *)v169 = v289;
                                                v171 = GetProcessHeap();
                                                v172 = HeapAlloc(v171, 8u, Size);
                                                if ( !v172 )
                                                {
LABEL_282:
                                                  v87 = v306;
                                                  v284 = v279;
                                                  v177 = v314;
                                                  v277 = -1073741801;
                                                  Sizea = v84;
                                                  v308 = v19;
                                                  v310 = v15;
                                                  v316 = v14;
                                                  v332 = (void *)v314[1];
                                                  if ( v332 )
                                                  {
                                                    v178 = GetProcessHeap();
                                                    HeapFree(v178, 0, v332);
                                                    v177 = v314;
                                                    v314[1] = 0;
                                                  }
                                                  v333 = (void *)v177[3];
                                                  if ( v333 )
                                                  {
                                                    v179 = GetProcessHeap();
                                                    HeapFree(v179, 0, v333);
                                                    v177 = v314;
                                                    v314[3] = 0;
                                                  }
                                                  v334 = (void *)v177[5];
                                                  if ( v334 )
                                                  {
                                                    v180 = GetProcessHeap();
                                                    HeapFree(v180, 0, v334);
                                                    v314[5] = 0;
                                                  }
                                                  v181 = GetProcessHeap();
                                                  HeapFree(v181, 0, v314);
                                                  v182 = 0;
LABEL_292:
                                                  v183 = v277;
                                                  if ( v277 < 0 )
                                                  {
                                                    if ( v182 )
                                                    {
                                                      v335 = (void *)*((_QWORD *)v182 + 1);
                                                      if ( v335 )
                                                      {
                                                        v185 = GetProcessHeap();
                                                        HeapFree(v185, 0, v335);
                                                        v182 = v320;
                                                        *((_QWORD *)v320 + 1) = 0;
                                                      }
                                                      v336 = (void *)*((_QWORD *)v182 + 3);
                                                      if ( v336 )
                                                      {
                                                        v186 = GetProcessHeap();
                                                        HeapFree(v186, 0, v336);
                                                        v182 = v320;
                                                        *((_QWORD *)v320 + 3) = 0;
                                                      }
                                                      v337 = (void *)*((_QWORD *)v182 + 5);
                                                      if ( v337 )
                                                      {
                                                        v187 = GetProcessHeap();
                                                        HeapFree(v187, 0, v337);
                                                        *((_QWORD *)v320 + 5) = 0;
                                                      }
                                                      v188 = GetProcessHeap();
                                                      HeapFree(v188, 0, v320);
                                                      v183 = v277;
                                                    }
                                                    v184 = 0;
                                                  }
                                                  else
                                                  {
                                                    v184 = v182;
                                                    v330 = v182;
                                                  }
                                                  LODWORD(v13) = v183 | 0x10000000;
                                                  if ( (v13 & 0x80000000) != 0LL )
                                                  {
                                                    v16 = v13;
                                                    goto LABEL_218;
                                                  }
                                                  if ( !v184
                                                    || (v13 = *((_QWORD *)v184 + 1), (v303 = (unsigned __int8 *)v13) == 0)
                                                    || !*v184 )
                                                  {
                                                    v16 = -805306355;
                                                    goto LABEL_218;
                                                  }
                                                  v321 = *v184 - 8LL;
                                                  v189 = GetProcessHeap();
                                                  v305 = HeapAlloc(v189, 0, v321);
                                                  v190 = v305;
                                                  if ( !v305 )
                                                  {
LABEL_336:
                                                    v341 = 0;
                                                    v16 = -805306367;
                                                    goto LABEL_218;
                                                  }
                                                  v191 = 0;
                                                  v192 = v321;
                                                  v342 = v303;
                                                  dwBytesd = v321 & 7;
                                                  v349 = v305;
                                                  if ( (v321 & 7) != 0 )
                                                  {
                                                    v193 = 0;
                                                    v194 = 0;
                                                    v195 = v303;
                                                    v196 = 0;
                                                    do
                                                    {
                                                      v197 = *v195++;
                                                      v315 = 8 * v193;
                                                      if ( v193 >= 4 )
                                                        v194 |= v197 << (56 - v315);
                                                      else
                                                        v196 |= v197 << (24 - v315);
                                                      ++v193;
                                                    }
                                                    while ( (int)v193 < (int)dwBytesd );
                                                    v191 = 0;
                                                    v290 = v196;
                                                    v190 = v305;
                                                    v344 = v194;
                                                    v192 = v321;
                                                    v342 = v195;
                                                    v306 = v87;
                                                    Sizea = v84;
                                                    v318 = v25;
                                                    v308 = v19;
                                                    v310 = v15;
                                                    v316 = v14;
                                                    v198 = v344 ^ 0x699A899C;
                                                    v199 = v290 ^ 0x92F65A5;
                                                    if ( (v321 & 7) != 0 )
                                                    {
                                                      v200 = v305;
                                                      v201 = v290 ^ 0x92F65A5;
                                                      v202 = 0;
                                                      do
                                                      {
                                                        v338 = (SIZE_T)(v200 + 1);
                                                        if ( v202 >= 4 )
                                                        {
                                                          v198 = __ROR4__(v198, 24);
                                                          v203 = v198;
                                                        }
                                                        else
                                                        {
                                                          v201 = __ROR4__(v201, 24);
                                                          v203 = v201;
                                                        }
                                                        *v200 = v203;
                                                        ++v202;
                                                        ++v200;
                                                      }
                                                      while ( (int)v202 < (int)dwBytesd );
                                                      v191 = 0;
                                                      v190 = v305;
                                                      v349 = (_BYTE *)v338;
                                                      v192 = v321;
                                                    }
                                                    if ( dwBytesd <= 4 )
                                                    {
                                                      v283 = 0;
                                                      if ( dwBytesd < 4 )
                                                        v199 = v199 >> (8 * (4 - dwBytesd)) << (8 * (4 - dwBytesd));
                                                      goto LABEL_328;
                                                    }
                                                    v204 = (v344 ^ 0x699A899Cu) >> (8 * (8 - dwBytesd)) << (8 * (8 - dwBytesd));
                                                  }
                                                  else
                                                  {
                                                    v204 = 0;
                                                    v290 = 0;
                                                    v199 = 0;
                                                  }
                                                  v283 = v204;
LABEL_328:
                                                  v339 = v192 >> 3;
                                                  if ( v192 >> 3 )
                                                  {
                                                    v205 = v283;
                                                    v206 = v342;
                                                    v207 = v349;
                                                    v208 = v344;
                                                    v209 = v290;
                                                    dwBytese = 0;
                                                    do
                                                    {
                                                      v210 = *v206;
                                                      v211 = v206[1];
                                                      v212 = v206[4];
                                                      v206 += 8;
                                                      v213 = *(v206 - 5)
                                                           | ((*(v206 - 6) | (((v210 << 8) | v211) << 8)) << 8);
                                                      v214 = v199 ^ v213;
                                                      v215 = *(v206 - 1)
                                                           | ((*(v206 - 2) | ((*(v206 - 3) | (v212 << 8)) << 8)) << 8);
                                                      v216 = v199 ^ v213 ^ v205 ^ v215 ^ 0xAB69605E ^ 0x7F1137F;
                                                      v217 = v214
                                                           ^ (__ROR4__(v216, 22) + 4991
                                                                                 * __ROR4__(v216 + 1419157410, 27));
                                                      v218 = v216
                                                           ^ (43881 * __ROR4__(v217 + 133239679, 9) - __ROR4__(v217, 30));
                                                      v219 = v217 ^ (24670 * (v218 - 4991) - (v218 >> 13));
                                                      v220 = v218
                                                           ^ (2033 * __ROR4__(v219 ^ 0xAB69, 26) - __ROR4__(v219, 30));
                                                      v221 = v219 ^ (133239679 - (v220 ^ 0xAB69605E));
                                                      v222 = v220 ^ (43881 * (v221 ^ 0x137F)) ^ __ROR4__(v221, 6);
                                                      v223 = v221
                                                           ^ (__ROR4__(v222, 30) + 24670
                                                                                 * __ROR4__(v222 + 133239679, 15));
                                                      v224 = v222
                                                           ^ (2033 * __ROR4__(v223 + 1419157410, 14) - __ROR4__(v223, 24));
                                                      v225 = v223
                                                           ^ __ROR4__(v224, 10)
                                                           ^ (4991 * __ROR4__(v224 ^ 0xAB69605E, 12));
                                                      v226 = v224 ^ (v225 >> 10) ^ (43881 * (v225 ^ 0x7F1));
                                                      v227 = v225 ^ (2033 * (__ROR4__(~v226, 5) + 24670));
                                                      v228 = v226 ^ (v227 - 2033) ^ 0xAB69605E;
                                                      v229 = v227
                                                           ^ ((v228 >> 2)
                                                            + 4991 * __ROR4__(v226 ^ (v227 - 2033) ^ 0xAB6967AF, 30));
                                                      v230 = v228
                                                           ^ (__ROR4__(v229, 25) + 43881 * __ROR4__(v229 - 133239679, 6));
                                                      v231 = v229 ^ (24670 * (v230 ^ 0x137F) + __ROR4__(v230, 9));
                                                      v232 = v230
                                                           ^ (__ROR4__(v231, 25) + 2033 * __ROR4__(v231 ^ 0xAB69, 27));
                                                      v233 = v231 ^ v232 ^ 0xAC987321;
                                                      v234 = v232 ^ (4991 * (__ROR4__(v233, 3) - 43881));
                                                      v235 = v233
                                                           ^ (24670 * __ROR4__(v234 - 133239679, 1) - __ROR4__(v234, 6));
                                                      v236 = v234
                                                           ^ (__ROR4__(v235, 18) + 2033
                                                                                 * __ROR4__(v235 - 1419157410, 29));
                                                      v237 = v235
                                                           ^ (4991 * __ROR4__(v236 - 1419157410, 17) - __ROR4__(v236, 14));
                                                      v238 = v236 ^ (v237 >> 3) ^ (43881 * (v237 ^ 0x605E));
                                                      v239 = v209
                                                           ^ __ROR4__(v238, 30)
                                                           ^ (24670 * __ROR4__(v238 ^ 0x7F1137F, 28));
                                                      v209 = v213;
                                                      v199 = v237 ^ v239;
                                                      v207[3] = v199;
                                                      v205 = v238 ^ v208;
                                                      v207[7] = v238 ^ v208;
                                                      v208 = v215;
                                                      v207[2] = __ROR4__(v199, 8);
                                                      v207[6] = __ROR4__(v205, 8);
                                                      v207[1] = __ROR4__(v199, 16);
                                                      v207[5] = __ROR4__(v205, 16);
                                                      *v207 = __ROR4__(v199, 24);
                                                      v207[4] = __ROR4__(v205, 24);
                                                      v207 += 8;
                                                      ++dwBytese;
                                                    }
                                                    while ( dwBytese < v339 );
                                                    v191 = 0;
                                                    v125 = -1073741801;
                                                    v25 = v318;
                                                    v14 = v316;
                                                    v15 = v310;
                                                    v19 = v308;
                                                    v84 = Sizea;
                                                    v87 = v306;
                                                    v190 = v305;
                                                    v192 = v321;
                                                  }
                                                  for ( m = 0; m < v192; ++m )
                                                    v191 ^= *((_BYTE *)v190 + m);
                                                  if ( v191 != *(_QWORD *)&v303[v192] )
                                                  {
                                                    v241 = GetProcessHeap();
                                                    HeapFree(v241, 0, v305);
                                                    goto LABEL_336;
                                                  }
                                                  v13 = (unsigned __int64)v284;
                                                  v242 = v292;
                                                  if ( (unsigned int)v192 < 4 )
                                                  {
                                                    v125 = -1073741762;
                                                    v341 = (__int64)v190;
LABEL_375:
                                                    v16 = v125 | 0x10000000;
                                                    goto LABEL_218;
                                                  }
                                                  v341 = (__int64)v190;
                                                  v304 = v190 + 1;
                                                  v243 = v190;
                                                  if ( v190 + 1 < v190 )
                                                    goto LABEL_372;
                                                  if ( (unsigned int)(v192 - 4) < 4 )
                                                  {
LABEL_341:
                                                    v125 = -1073741762;
                                                    v341 = (__int64)v190;
LABEL_374:
                                                    v284 = (void *)v13;
                                                    v292 = v242;
                                                    goto LABEL_375;
                                                  }
                                                  dwBytesf = (SIZE_T)(v190 + 2);
                                                  v13 = (unsigned __int64)v284;
                                                  if ( v190 + 2 < v190 + 1 )
                                                    goto LABEL_372;
                                                  if ( (unsigned int)(v192 - 8) < v190[1] )
                                                    goto LABEL_341;
                                                  if ( v190[1] >= 0xFFFFFFF8 )
                                                  {
LABEL_372:
                                                    v125 = -1073741675;
                                                  }
                                                  else
                                                  {
                                                    v340 = (unsigned int)v192;
                                                    v322 = (unsigned int)v190[1];
                                                    v13 = (unsigned __int64)v284;
                                                    v242 = v292;
                                                    if ( (char *)v190 + (unsigned int)v192 >= (char *)v190 + v322 + 8 )
                                                    {
                                                      v244 = v190 + 2;
                                                      if ( v340 + -(__int64)v322 - 8 < 8 )
                                                      {
                                                        v291 = 0;
                                                        if ( v190 == (_DWORD *)-8LL )
                                                        {
                                                          v341 = -8;
                                                        }
                                                        else
                                                        {
                                                          v190 = v305;
                                                          v245 = (unsigned __int64)v304 + v322 + 4;
                                                          if ( v245 < dwBytesf )
                                                          {
                                                            v125 = -1073741675;
                                                            v341 = (__int64)v243;
                                                            goto LABEL_375;
                                                          }
                                                          v246 = (_DWORD *)dwBytesf;
                                                          if ( v245 > dwBytesf )
                                                          {
                                                            while ( 1 )
                                                            {
                                                              v13 = (unsigned __int64)(v246 + 1);
                                                              if ( v246 + 1 < v246 )
                                                                break;
                                                              if ( v13 > v245 )
                                                                goto LABEL_360;
                                                              if ( *v246 >= 0xFFFFFFFC )
                                                                break;
                                                              v13 = (unsigned __int64)v246 + (unsigned int)(*v246 + 4);
                                                              if ( v13 < (unsigned __int64)v246 )
                                                                break;
                                                              v245 = (unsigned __int64)v305 + v322 + 8;
                                                              if ( v13 > v245 )
                                                                goto LABEL_360;
                                                              ++v291;
                                                              v246 = (_DWORD *)((char *)v246 + (unsigned int)(*v246 + 4));
                                                              if ( v13 >= v245 )
                                                                goto LABEL_359;
                                                            }
                                                            v125 = -1073741675;
                                                            goto LABEL_375;
                                                          }
                                                          v341 = (__int64)v305;
LABEL_359:
                                                          if ( v246 != (_DWORD *)v245 )
                                                          {
LABEL_360:
                                                            v125 = -1073741811;
                                                            goto LABEL_375;
                                                          }
                                                        }
                                                        LODWORD(v13) = 0;
                                                        v347 = *v190;
                                                        if ( v190[1] )
                                                        {
                                                          v247 = GetProcessHeap();
                                                          v248 = HeapAlloc(v247, 8u, v322);
                                                          if ( !v248 )
                                                            goto LABEL_375;
                                                          v125 = 0;
                                                          v244 = (const void *)dwBytesf;
                                                        }
                                                        else
                                                        {
                                                          v248 = 0;
                                                          v125 = 0;
                                                        }
                                                        lpMem = v248;
                                                        if ( v244 )
                                                          memcpy_0(v248, v244, v322);
                                                        v343 = v291;
                                                        if ( v347 != v291 )
                                                          v125 = -1073741762;
                                                        goto LABEL_375;
                                                      }
                                                    }
                                                    v125 = -1073741762;
                                                  }
                                                  v341 = (__int64)v190;
                                                  goto LABEL_374;
                                                }
                                                v170[1] = v172;
                                                v277 = 0;
                                                memcpy_0(v172, v292 + 1, Size);
                                              }
                                              if ( dwBytesc == -4 )
                                              {
                                                *((_DWORD *)v170 + 4) = 0;
                                                v170[3] = 0;
                                              }
                                              else
                                              {
                                                *((_DWORD *)v170 + 4) = v282;
                                                v173 = GetProcessHeap();
                                                v174 = HeapAlloc(v173, 8u, v331);
                                                if ( !v174 )
                                                {
LABEL_281:
                                                  v314 = v170;
                                                  goto LABEL_282;
                                                }
                                                v170[3] = v174;
                                                v277 = 0;
                                                memcpy_0(v174, (const void *)(dwBytesc + 4), v331);
                                              }
                                              if ( v302 )
                                              {
                                                *((_DWORD *)v170 + 8) = v346;
                                                v175 = GetProcessHeap();
                                                v176 = HeapAlloc(v175, 8u, v346);
                                                if ( !v176 )
                                                  goto LABEL_281;
                                                v170[5] = v176;
                                                v277 = 0;
                                                memcpy_0(v176, v302, v346);
                                              }
                                              else
                                              {
                                                *((_DWORD *)v170 + 8) = 0;
                                                v170[5] = 0;
                                              }
                                              v182 = (unsigned int *)v170;
                                              v320 = (unsigned int *)v170;
                                              v87 = v306;
                                              v284 = v279;
                                              Sizea = v84;
                                              v308 = v19;
                                              v310 = v15;
                                              v316 = v14;
                                              goto LABEL_292;
                                            }
                                          }
                                          else
                                          {
                                            LastError = GetLastError();
                                            v159 = LastError < 0;
                                            if ( LastError > 0 )
                                            {
                                              LastError = (unsigned __int16)LastError | 0x80070000;
                                              v159 = LastError < 0;
                                            }
                                            if ( !v159 )
                                            {
                                              v16 = -2147467259;
                                              goto LABEL_381;
                                            }
                                          }
                                          v161 = v288;
                                          if ( LastError == -805306333 )
                                          {
                                            v16 = -2147024774;
LABEL_244:
                                            v162 = v279;
LABEL_245:
                                            v284 = v162;
                                            goto LABEL_218;
                                          }
                                          if ( LastError >= 0 )
                                            goto LABEL_247;
                                          v16 = LastError;
LABEL_381:
                                          *((_QWORD *)&v157 + 1) = v292;
                                          v13 = (unsigned __int64)v279;
                                          goto LABEL_382;
                                        }
                                      }
                                    }
                                  }
                                }
                              }
                              v149 = GetProcessHeap();
                              HeapFree(v149, 0, v279);
                            }
                          }
                        }
                      }
                    }
                    v139 = -805306219;
                  }
                  v16 = v139;
                  goto LABEL_218;
                }
                v13 = v69;
                v74 = (_DWORD *)v25;
                for ( n = 0; n < v56; v74 = (_DWORD *)((char *)v74 + v76) )
                {
                  v76 = *v74 + 4;
                  if ( *v74 >= 0xFFFFFFFC || (_DWORD *)((char *)v74 + v76) < v74 )
                    goto LABEL_86;
                  ++n;
                }
                if ( v74 + 1 < v74 )
                  goto LABEL_86;
                if ( (unsigned __int64)(v74 + 1) > v25 + v13 )
                  goto LABEL_75;
                v73 = v56 + 1;
                *v74 = 0;
                v78 = (_DWORD *)v25;
                v79 = 0;
                for ( ii = v13; v79 < v73; v78 = (_DWORD *)((char *)v78 + v80) )
                {
                  v80 = *v78 + 4;
                  if ( *v78 >= 0xFFFFFFFC )
                    goto LABEL_86;
                  v13 = (unsigned __int64)v78 + v80;
                  if ( v13 < (unsigned __int64)v78 )
                    goto LABEL_86;
                  ++v79;
                }
                if ( v78 + 1 < v78 )
                {
LABEL_86:
                  v16 = -1073741675;
                  goto LABEL_58;
                }
                v13 = v25 + ii;
                if ( (unsigned __int64)(v78 + 2) <= v13 )
                {
                  *v78 = 4;
                  v78[1] = 2;
                  goto LABEL_160;
                }
LABEL_75:
                v16 = -1073741789;
                goto LABEL_58;
              }
            }
            v16 = -1073741675;
          }
          else
          {
            v16 = -1073741811;
          }
LABEL_139:
          v69 = v280;
          goto LABEL_140;
        }
        v16 = -1073741675;
      }
    }
    else
    {
      v16 = -1073741811;
    }
LABEL_115:
    v13 = v280;
    goto LABEL_116;
  }
  v16 = -1073741762;
LABEL_38:
  v4 = v355;
LABEL_39:
  if ( v14 )
  {
    v37 = GetProcessHeap();
    HeapFree(v37, 0, v14);
  }
  if ( v15 )
  {
    v38 = GetProcessHeap();
    HeapFree(v38, 0, v15);
  }
  if ( v16 >= 0 )
  {
    v7 = v353;
    *v4 = v16;
    goto LABEL_449;
  }
  v39 = CClipLicense::EnsureModernLicenseForCurrentOsProductWithUserTicket(v13, v5, v6, v4);
  v7 = v39;
  if ( v39 < 0 )
  {
    v8 = (unsigned int)v39;
    goto LABEL_3;
  }
  if ( !v5 && !*v4 )
    CEditionUpgradeManager::FireModernLicenseConsumption(v40);
LABEL_449:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v7);
  return v7;
}

```

## disassembly

```asm
0x18000f264  mov     [rsp-8+arg_0], rbx
0x18000f269  push    rbp
0x18000f26a  push    rsi
0x18000f26b  push    rdi
0x18000f26c  push    r12
0x18000f26e  push    r13
0x18000f270  push    r14
0x18000f272  push    r15
0x18000f274  lea     rbp, [rsp-100h]
0x18000f27c  sub     rsp, 200h
0x18000f283  mov     rax, cs:__security_cookie
0x18000f28a  xor     rax, rsp
0x18000f28d  mov     [rbp+130h+var_40], rax
0x18000f294  mov     [rbp+130h+var_130], r9
0x18000f298  xorps   xmm0, xmm0
0x18000f29b  mov     [rbp+130h+var_134], r8d
0x18000f29f  mov     rdi, r9
0x18000f2a2  mov     [rbp+130h+var_128], rdx
0x18000f2a6  mov     esi, r8d
0x18000f2a9  mov     rbx, rdx
0x18000f2ac  movups  [rbp+130h+var_E8], xmm0
0x18000f2b0  test    r9, r9
0x18000f2b3  jnz     short loc_18000F2CB
0x18000f2b5  mov     r14d, 80070057h
0x18000f2bb  mov     ebx, r14d
0x18000f2be  mov     ecx, r14d
0x18000f2c1  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000f2c6  jmp     loc_18001176D
0x18000f2cb  lea     r9, [rbp+130h+Src]
0x18000f2cf  mov     [rbp+130h+var_138], 41h ; 'A'
0x18000f2d6  lea     r8, [rbp+130h+var_138]
0x18000f2da  call    ConvertPartNumberToPfn
0x18000f2df  mov     [rbp+130h+var_138], eax
0x18000f2e2  test    eax, eax
0x18000f2e4  jns     short loc_18000F2F4
0x18000f2e6  mov     ecx, eax
0x18000f2e8  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000f2ed  mov     ebx, ecx
0x18000f2ef  jmp     loc_18001176D
0x18000f2f4  call    cs:__imp_GetProcessHeap
0x18000f2fa  mov     r14d, 8
0x18000f300  mov     r8d, 0A0h; dwBytes
0x18000f306  mov     rcx, rax; hHeap
0x18000f309  mov     edx, r14d; dwFlags
0x18000f30c  call    cs:__imp_HeapAlloc
0x18000f312  xor     r11d, r11d
0x18000f315  mov     r12, rax
0x18000f318  test    rax, rax
0x18000f31b  jnz     short loc_18000F32E
0x18000f31d  mov     r13d, r11d
0x18000f320  mov     r14d, 0C0000017h
0x18000f326  mov     r12d, r11d
0x18000f329  jmp     loc_18000F555
0x18000f32e  movups  xmm0, cs:?DecryptionCipher@?1??WarbirdUmGetDecryptionCipher@@9@4PAEA; uchar near * `WarbirdUmGetDecryptionCipher'::`2'::DecryptionCipher
0x18000f335  movups  xmmword ptr [rax], xmm0
0x18000f338  movups  xmm1, cs:xmmword_18002F600
0x18000f33f  movups  xmmword ptr [rax+10h], xmm1
0x18000f343  movups  xmm0, cs:xmmword_18002F610
0x18000f34a  movups  xmmword ptr [rax+20h], xmm0
0x18000f34e  movups  xmm1, cs:xmmword_18002F620
0x18000f355  movups  xmmword ptr [rax+30h], xmm1
0x18000f359  movups  xmm0, cs:xmmword_18002F630
0x18000f360  movups  xmmword ptr [rax+40h], xmm0
0x18000f364  movups  xmm1, cs:xmmword_18002F640
0x18000f36b  movups  xmmword ptr [rax+50h], xmm1
0x18000f36f  movups  xmm0, cs:xmmword_18002F650
0x18000f376  movups  xmmword ptr [rax+60h], xmm0
0x18000f37a  movups  xmm1, cs:xmmword_18002F660
0x18000f381  movups  xmmword ptr [rax+70h], xmm1
0x18000f385  movups  xmm0, cs:xmmword_18002F670
0x18000f38c  movups  xmmword ptr [rax+80h], xmm0
0x18000f393  movups  xmm1, cs:xmmword_18002F680
0x18000f39a  movups  xmmword ptr [rax+90h], xmm1
0x18000f3a1  call    cs:__imp_GetProcessHeap
0x18000f3a7  mov     r8, r14; dwBytes
0x18000f3aa  mov     edx, r14d; dwFlags
0x18000f3ad  mov     rcx, rax; hHeap
0x18000f3b0  call    cs:__imp_HeapAlloc
0x18000f3b6  xor     r11d, r11d
0x18000f3b9  mov     r13, rax
0x18000f3bc  test    rax, rax
0x18000f3bf  jnz     short loc_18000F3CF
0x18000f3c1  mov     r14d, 0C0000017h
0x18000f3c7  mov     r13d, r11d
0x18000f3ca  jmp     loc_18000F555
0x18000f3cf  mov     rax, cs:?nDecryptionKey@?1??WarbirdUmGetDecryptionKey@@9@4_KA; unsigned __int64 `WarbirdUmGetDecryptionKey'::`2'::nDecryptionKey
0x18000f3d6  mov     [r13+0], rax
0x18000f3da  rdtsc
0x18000f3dc  shl     rdx, 20h
0x18000f3e0  or      rax, rdx
0x18000f3e3  mov     rdi, rax
0x18000f3e6  mov     edx, 7FFFFFFFh
0x18000f3eb  lea     rax, [rbp+130h+Src]
0x18000f3ef  mov     r8d, edx
0x18000f3f2  cmp     [rax], r11w
0x18000f3f6  jz      short loc_18000F402
0x18000f3f8  add     rax, 2
0x18000f3fc  sub     r8, 1
0x18000f400  jnz     short loc_18000F3F2
0x18000f402  mov     rcx, rdx
0x18000f405  mov     rax, r8
0x18000f408  sub     rcx, r8
0x18000f40b  neg     rax
0x18000f40e  sbb     r9, r9
0x18000f411  and     r9, rcx
0x18000f414  test    r8, r8
0x18000f417  jnz     short loc_18000F424
0x18000f419  mov     r14d, 0C000003Eh
0x18000f41f  jmp     loc_18000F551
0x18000f424  lea     eax, ds:6[r9*2]
0x18000f42c  cmp     eax, 4
0x18000f42f  jb      loc_18001174C
0x18000f435  or      r10d, 0FFFFFFFFh
0x18000f439  mov     [rbp+130h+lpMem], r11
0x18000f43d  add     eax, 0CCh
0x18000f442  mov     [rsp+230h+var_200], r11d
0x18000f447  mov     ecx, 0CCh
0x18000f44c  mov     [rbp+130h+var_164], r10d
0x18000f450  cmp     eax, ecx
0x18000f452  mov     r8d, r10d
0x18000f455  mov     ebx, 0C0000095h
0x18000f45a  mov     r15, r11
0x18000f45d  cmovnb  r8d, eax
0x18000f461  mov     r9d, r11d
0x18000f464  sbb     r14d, r14d
0x18000f467  and     r14d, ebx
0x18000f46a  add     r14d, 10000000h
0x18000f471  cmp     eax, ecx
0x18000f473  jb      loc_18000F6A5
0x18000f479  mov     r9, rdx
0x18000f47c  lea     rax, LocaleName
0x18000f483  cmp     [rax], r11w
0x18000f487  jz      short loc_18000F493
0x18000f489  add     rax, 2
0x18000f48d  sub     r9, 1
0x18000f491  jnz     short loc_18000F483
0x18000f493  mov     rcx, rdx
0x18000f496  mov     rax, r9
0x18000f499  sub     rcx, r9
0x18000f49c  neg     rax
0x18000f49f  sbb     rdx, rdx
0x18000f4a2  and     rdx, rcx
0x18000f4a5  test    r9, r9
0x18000f4a8  jnz     short loc_18000F4B5
0x18000f4aa  mov     r14d, 0C000003Eh
0x18000f4b0  jmp     loc_18000F54D
0x18000f4b5  lea     edx, ds:6[rdx*2]
0x18000f4bc  cmp     edx, 4
0x18000f4bf  jb      loc_180011744
0x18000f4c5  lea     eax, [r8+rdx]
0x18000f4c9  mov     r9d, 10000000h
0x18000f4cf  cmp     eax, r8d
0x18000f4d2  mov     edx, r10d
0x18000f4d5  cmovnb  edx, eax
0x18000f4d8  sbb     r14d, r14d
0x18000f4db  and     r14d, ebx
0x18000f4de  add     r14d, r9d
0x18000f4e1  cmp     eax, r8d
0x18000f4e4  jb      loc_18001173C
0x18000f4ea  lea     eax, [rdx+4]
0x18000f4ed  mov     ecx, r10d
0x18000f4f0  cmp     eax, edx
0x18000f4f2  cmovnb  ecx, eax
0x18000f4f5  sbb     r14d, r14d
0x18000f4f8  and     r14d, ebx
0x18000f4fb  add     r14d, r9d
0x18000f4fe  cmp     eax, edx
0x18000f500  jb      loc_18001173C
0x18000f506  lea     eax, [rcx+8]
0x18000f509  mov     esi, r10d
0x18000f50c  cmp     eax, ecx
0x18000f50e  cmovnb  esi, eax
0x18000f511  sbb     r14d, r14d
0x18000f514  and     r14d, ebx
0x18000f517  add     r14d, r9d
0x18000f51a  cmp     eax, ecx
0x18000f51c  jb      loc_18001173C
0x18000f522  call    cs:__imp_GetProcessHeap
0x18000f528  mov     r8d, esi; dwBytes
0x18000f52b  mov     edx, 8; dwFlags
0x18000f530  mov     rcx, rax; hHeap
0x18000f533  call    cs:__imp_HeapAlloc
0x18000f539  xor     r11d, r11d
0x18000f53c  mov     r15, rax
0x18000f53f  test    rax, rax
0x18000f542  jnz     short loc_18000F5B1
0x18000f544  mov     r14d, 0C0000017h
0x18000f54a  mov     esi, [rbp+130h+var_134]
0x18000f54d  mov     rbx, [rbp+130h+var_128]
0x18000f551  mov     rdi, [rbp+130h+var_130]
0x18000f555  xor     r15d, r15d
0x18000f558  test    r12, r12
0x18000f55b  jz      short loc_18000F571
0x18000f55d  call    cs:__imp_GetProcessHeap
0x18000f563  mov     r8, r12; lpMem
0x18000f566  xor     edx, edx; dwFlags
0x18000f568  mov     rcx, rax; hHeap
0x18000f56b  call    cs:__imp_HeapFree
0x18000f571  test    r13, r13
0x18000f574  jz      short loc_18000F58A
0x18000f576  call    cs:__imp_GetProcessHeap
0x18000f57c  mov     r8, r13; lpMem
0x18000f57f  xor     edx, edx; dwFlags
0x18000f581  mov     rcx, rax; hHeap
0x18000f584  call    cs:__imp_HeapFree
0x18000f58a  test    r14d, r14d
0x18000f58d  jns     loc_180011767
0x18000f593  mov     r9, rdi; int *
0x18000f596  mov     r8, rbx; unsigned __int16 *
0x18000f599  mov     edx, esi; int
0x18000f59b  call    ?EnsureModernLicenseForCurrentOsProductWithUserTicket@CClipLicense@@SAJHHPEAGPEAJ@Z; CClipLicense::EnsureModernLicenseForCurrentOsProductWithUserTicket(int,int,ushort *,long *)
0x18000f5a0  mov     ebx, eax
0x18000f5a2  test    eax, eax
0x18000f5a4  jns     loc_180011757
0x18000f5aa  mov     ecx, eax
0x18000f5ac  jmp     loc_18000F2C1
0x18000f5b1  lea     rdx, [rax+4]
0x18000f5b5  cmp     rdx, r15
0x18000f5b8  jb      loc_180011739
0x18000f5be  lea     rcx, [rsi+rax]
0x18000f5c2  add     rax, 8
0x18000f5c6  cmp     rax, rcx
0x18000f5c9  jbe     short loc_18000F5D6
0x18000f5cb  mov     r14d, 0C0000023h
0x18000f5d1  jmp     loc_18001173C
0x18000f5d6  mov     dword ptr [r15], 4
0x18000f5dd  mov     dword ptr [rdx], 6Dh ; 'm'
0x18000f5e3  test    r12, r12
0x18000f5e6  jz      loc_180011731
0x18000f5ec  mov     r10d, 0A0h
0x18000f5f2  test    r15, r15
0x18000f5f5  jnz     short loc_18000F60D
0x18000f5f7  lea     r14d, [r10+4]
0x18000f5fb  add     r14d, esi
0x18000f5fe  cmp     r14d, esi
0x18000f601  jb      loc_180011739
0x18000f607  lea     r8d, [r15+8]
0x18000f60b  jmp     short loc_18000F68B
0x18000f60d  mov     r8d, 8
0x18000f613  mov     rdx, r15
0x18000f616  mov     [rbp+130h+var_168], r8d
0x18000f61a  mov     ecx, r11d
0x18000f61d  mov     eax, [rdx]
0x18000f61f  add     eax, 4
0x18000f622  cmp     eax, 4
0x18000f625  jb      loc_180011739
0x18000f62b  mov     r9d, eax
0x18000f62e  add     r9, rdx
0x18000f631  cmp     r9, rdx
0x18000f634  jb      loc_180011739
0x18000f63a  inc     ecx
0x18000f63c  mov     rdx, r9
0x18000f63f  cmp     ecx, 1
0x18000f642  jb      short loc_18000F61D
0x18000f644  add     r9, 4
0x18000f648  cmp     r9, rdx
0x18000f64b  jb      loc_180011739
0x18000f651  mov     r10d, r10d
0x18000f654  lea     rcx, [r15+rsi]
0x18000f658  mov     r14d, esi
0x18000f65b  lea     rax, [r10+4]
0x18000f65f  add     rax, rdx
0x18000f662  cmp     rax, rcx
0x18000f665  ja      loc_18000F5CB
0x18000f66b  mov     dword ptr [rdx], 0A0h
0x18000f671  test    r12, r12
0x18000f674  jz      short loc_18000F68B
0x18000f676  mov     r8d, r10d; Size
0x18000f679  mov     rdx, r12; Src
0x18000f67c  mov     rcx, r9; void *
0x18000f67f  call    memcpy_0
0x18000f684  mov     r8d, [rbp+130h+var_168]
0x18000f688  xor     r11d, r11d
0x18000f68b  mov     esi, 2
0x18000f690  test    r13, r13
0x18000f693  jnz     short loc_18000F6F0
0x18000f695  test    r8d, r8d
0x18000f698  jz      short loc_18000F6F5
0x18000f69a  mov     r14d, 0C000000Dh
0x18000f6a0  mov     r9d, [rsp+230h+var_200]
0x18000f6a5  test    r14d, r14d
0x18000f6a8  js      short loc_18000F6B1
0x18000f6aa  test    r9d, r9d
0x18000f6ad  cmovnz  r14d, r9d
0x18000f6b1  test    r15, r15
0x18000f6b4  jz      short loc_18000F6CA
0x18000f6b6  call    cs:__imp_GetProcessHeap
0x18000f6bc  mov     r8, r15; lpMem
0x18000f6bf  xor     edx, edx; dwFlags
0x18000f6c1  mov     rcx, rax; hHeap
0x18000f6c4  call    cs:__imp_HeapFree
0x18000f6ca  mov     rbx, [rbp+130h+lpMem]
0x18000f6ce  test    rbx, rbx
0x18000f6d1  jz      loc_18000F54A
0x18000f6d7  call    cs:__imp_GetProcessHeap
0x18000f6dd  mov     r8, rbx; lpMem
0x18000f6e0  xor     edx, edx; dwFlags
0x18000f6e2  mov     rcx, rax; hHeap
0x18000f6e5  call    cs:__imp_HeapFree
0x18000f6eb  jmp     loc_18000F54A
  ... truncated ...
```
