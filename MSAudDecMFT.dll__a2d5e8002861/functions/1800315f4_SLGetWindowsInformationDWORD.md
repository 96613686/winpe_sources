# SLGetWindowsInformationDWORD

- ea: `0x1800315f4`
- end: `0x180036d67`
- name: `SLGetWindowsInformationDWORD`
- size: `22387`
- prototype: `HRESULT __stdcall(PCWSTR pwszValueName, DWORD *pdwValue)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18003156c`

## callees

- `0x1800315f4`
- `0x180036e40`
- `0x18003f414`
- `0x18003f558`
- `0x18004292c`
- `0x18004bf38`
- `0x18009606c`
- `0x1800960c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033e91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035ec1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033e91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035ec1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180033223`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180033813`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180033223`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180033813`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180033204`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800337f4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180033204`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800337f4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180031691`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003175b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180031de0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180031e22`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180031e70`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180031f1d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180032193`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003247c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800324cb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180032526`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180032580`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180032b0b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180032d5b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003300e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003317f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180033780`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180033898`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800338cf`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180033932`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800339e6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800343c3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180034463`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800345b6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800348b0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180035211`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800354ac`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180035516`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003557a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800355e3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003620d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180031691`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003175b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180031de0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180031e22`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180031e70`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180031f1d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180032193`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003247c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800324cb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180032526`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180032580`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180032b0b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180032d5b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003300e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003317f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180033780`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180033898`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800338cf`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180033932`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800339e6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800343c3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180034463`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800345b6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800348b0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180035211`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800354ac`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180035516`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003557a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800355e3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003620d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031675`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031746`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800317dd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003182c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003185d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800318eb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003195d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031dc8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031e07`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031e56`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031f04`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031f50`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031f8d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003201f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003217c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180032232`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180032280`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800322b8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800322e2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180032327`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003235f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180032389`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800323c1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800323f0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180032464`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800324b1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003250b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180032569`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180032af4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180032d44`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180032ff5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180033168`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180033567`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180033769`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180033880`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800338b8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180033918`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800339cd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180033a38`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180033cff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180033d3b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180033d7b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180033dbc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180033df9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180033e36`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180033e65`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180033f28`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180033f64`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180033fa0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180033fce`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034007`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034044`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034081`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800340b0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800343a7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003444e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003459f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034899`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034f93`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034fee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180035024`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003505a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180035083`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800350c5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800350ff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180035139`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180035166`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800351fa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180035494`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800354fd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180035562`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800355ca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180035669`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800356a4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800356df`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003570d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180035b88`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180035bbe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180035bf4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180035c1d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180035c6a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180035c9b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180035ccc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180035cf4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180035d19`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180035d8c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180035db9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180035dde`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180035e07`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180035f10`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180035f4b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180035f86`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180035fb4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800361f2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003665d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180036682`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800366a7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180036cbc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180036cea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180036d0f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031675`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031746`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800317dd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003182c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003185d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800318eb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003195d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031dc8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031e07`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031e56`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031f04`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031f50`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031f8d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003201f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003217c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180032232`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180032280`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800322b8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800322e2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180032327`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003235f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180032389`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800323c1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800323f0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180032464`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800324b1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003250b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180032569`

## string_xrefs

- `0x1800331e6`: `ntdll.dll`
- `0x1800337d6`: `ntdll.dll`

## pseudocode

```c
HRESULT __stdcall SLGetWindowsInformationDWORD(PCWSTR pwszValueName, DWORD *pdwValue)
{
  DWORD *v2; // rdi
  DWORD *v4; // rbx
  HLOCAL v5; // rax
  void *v6; // rsi
  HANDLE ProcessHeap; // rax
  _OWORD *v8; // rax
  void *v9; // r12
  HANDLE v10; // rax
  _QWORD *v11; // rax
  void *v12; // r13
  int v13; // r15d
  HANDLE v14; // rax
  void *v15; // r14
  HANDLE v16; // rax
  void *v17; // r14
  HANDLE v18; // rax
  HRESULT v19; // ecx
  HANDLE v20; // rax
  HANDLE v22; // rax
  unsigned __int64 v23; // r15
  char *v24; // rdx
  unsigned __int8 v25; // al
  unsigned __int64 v26; // rcx
  int v27; // r10d
  unsigned __int8 *v28; // rax
  int v29; // r8d
  _BYTE *v30; // r12
  int v31; // r13d
  int v32; // r9d
  int v33; // esi
  int v34; // ecx
  int v35; // r14d
  int v36; // r11d
  int v37; // r14d
  int v38; // r11d
  int v39; // edx
  int v40; // r9d
  int v41; // r10d
  int v42; // r8d
  int v43; // r9d
  unsigned int v44; // edx
  int v45; // ecx
  int v46; // edx
  int v47; // r8d
  int v48; // r9d
  int v49; // edx
  unsigned int v50; // r8d
  unsigned int v51; // r9d
  int v52; // edx
  int v53; // r8d
  int v54; // r9d
  int v55; // edx
  int v56; // r8d
  int v57; // r10d
  int v58; // edx
  int v59; // r9d
  unsigned int v60; // r8d
  int v61; // edx
  int v62; // ecx
  unsigned int v63; // r9d
  _DWORD *v64; // r14
  HANDLE v65; // rax
  _QWORD *v66; // r15
  HANDLE v67; // rax
  void *v68; // rax
  HANDLE v69; // rax
  _OWORD *v70; // rax
  HANDLE v71; // rax
  _QWORD *v72; // rax
  _QWORD *v73; // rax
  int v74; // r15d
  HANDLE v75; // rax
  HANDLE v76; // rax
  LPVOID v77; // rax
  _DWORD *v78; // r9
  STRSAFE_PCNZWCH *v79; // r14
  void *v80; // r14
  void *v81; // r14
  LPVOID v82; // r14
  void *v83; // r14
  HANDLE v84; // rax
  int *v85; // r15
  unsigned int v86; // eax
  int v87; // r15d
  SIZE_T v88; // r9
  unsigned int *v89; // rax
  int jj; // edx
  __int64 v91; // r8
  unsigned int *v92; // rcx
  unsigned int v93; // ecx
  unsigned int v94; // edx
  unsigned int v95; // ecx
  unsigned int v96; // eax
  unsigned int v97; // r14d
  HANDLE v98; // rax
  _DWORD *v99; // rax
  const void **v100; // r14
  _DWORD *v101; // r15
  _DWORD *v102; // rcx
  unsigned int *v103; // rdx
  _DWORD *v104; // r15
  _DWORD *v105; // rcx
  HANDLE v106; // rax
  HANDLE v107; // rax
  HANDLE v108; // rax
  HANDLE v109; // rax
  HANDLE v110; // rax
  HANDLE v111; // rax
  HANDLE v112; // rax
  HANDLE v113; // rax
  HANDLE v114; // rax
  HANDLE v115; // rax
  _QWORD *v116; // rax
  _QWORD *v117; // r14
  void *v118; // r12
  HANDLE v119; // rax
  size_t v120; // r13
  void *v121; // rax
  int v122; // r15d
  char *v123; // r12
  HANDLE v124; // rax
  SIZE_T v125; // r13
  void *v126; // rax
  void *v127; // r12
  unsigned int v128; // eax
  unsigned int v129; // r13d
  HANDLE v130; // rax
  void *v131; // rax
  STRSAFE_PCNZWCH *v132; // rcx
  void *v133; // r15
  wchar_t *v134; // r10
  unsigned __int64 v135; // r11
  unsigned __int8 v136; // al
  int v137; // r9d
  unsigned int v138; // r8d
  SIZE_T v139; // rcx
  int v140; // r10d
  unsigned __int8 *v141; // rbx
  unsigned int v142; // r11d
  _BYTE *v143; // rsi
  SIZE_T v144; // r12
  int v145; // r13d
  int v146; // eax
  int v147; // ecx
  int v148; // r15d
  int v149; // r14d
  int v150; // r15d
  int v151; // edx
  int v152; // r14d
  int v153; // r8d
  int v154; // r9d
  unsigned int v155; // edx
  int v156; // r8d
  int v157; // r9d
  unsigned int v158; // edx
  int v159; // r8d
  int v160; // r10d
  int v161; // r11d
  unsigned int v162; // r9d
  int v163; // edx
  int v164; // r8d
  unsigned int v165; // r9d
  int v166; // edx
  int v167; // r8d
  int v168; // r9d
  int v169; // edx
  int v170; // r8d
  int v171; // r9d
  int v172; // edx
  int v173; // r8d
  unsigned int v174; // r9d
  int v175; // edx
  int v176; // r8d
  unsigned __int64 mm; // rcx
  SIZE_T v178; // rax
  unsigned int v179; // eax
  unsigned int v180; // ecx
  unsigned int v181; // eax
  unsigned int v182; // edx
  unsigned int v183; // eax
  int v184; // ecx
  unsigned int v185; // r14d
  HANDLE v186; // rax
  _DWORD *v187; // rax
  unsigned int v188; // ecx
  _DWORD *v189; // rdx
  unsigned int m; // ecx
  unsigned int v191; // eax
  _DWORD *v192; // rdx
  unsigned int n; // ecx
  unsigned int v194; // eax
  int v195; // eax
  _DWORD *v196; // rdx
  unsigned int v197; // ecx
  unsigned int ii; // r8d
  unsigned int v199; // eax
  void *v200; // rax
  __int64 v201; // r15
  HANDLE v202; // rax
  int v203; // r9d
  unsigned int v204; // r10d
  unsigned __int64 v205; // r15
  _DWORD *v206; // rdx
  unsigned int i; // r8d
  unsigned int v208; // eax
  unsigned int v209; // ecx
  unsigned int *v210; // rdx
  unsigned int j; // r8d
  unsigned int v212; // eax
  char *v213; // rdx
  unsigned int v214; // ecx
  unsigned int k; // r8d
  unsigned int v216; // eax
  SIZE_T v217; // rax
  const void *v218; // r11
  int v219; // r9d
  __int64 v220; // r9
  _DWORD *v221; // r11
  void *v222; // rax
  HANDLE v223; // rax
  _DWORD *v224; // rax
  unsigned int *v225; // rax
  unsigned int kk; // r15d
  SIZE_T v227; // r10
  unsigned int *v228; // r11
  unsigned int v229; // r11d
  unsigned int v230; // r9d
  unsigned int v231; // eax
  unsigned int v232; // r15d
  HANDLE v233; // rax
  SIZE_T v234; // rcx
  __int128 v235; // rax
  FARPROC ProcAddress; // rax
  int v237; // eax
  unsigned int v238; // r8d
  SIZE_T v239; // r15
  char *v240; // rcx
  unsigned int *v241; // r11
  SIZE_T v242; // r9
  unsigned int *v243; // rcx
  unsigned int v244; // r11d
  unsigned __int64 v245; // r10
  unsigned int v246; // ecx
  unsigned int v247; // r10d
  unsigned int v248; // ecx
  __int64 v249; // rcx
  void *v250; // rdx
  void *v251; // r8
  _DWORD *v252; // rbx
  HANDLE v253; // rax
  int v254; // eax
  int v255; // eax
  __int64 v256; // rcx
  __int64 v257; // r9
  unsigned int *v258; // rcx
  int i2; // r11d
  unsigned int v260; // ebx
  void *v261; // rcx
  unsigned int i3; // r9d
  unsigned int v263; // r10d
  unsigned int v264; // r11d
  unsigned int v265; // r11d
  unsigned int v266; // r11d
  unsigned int v267; // r9d
  unsigned int v268; // ebx
  HANDLE v269; // rax
  _DWORD *v270; // r14
  FARPROC v271; // rax
  HANDLE v272; // rax
  _DWORD *v273; // rax
  unsigned int v274; // ebx
  HANDLE v275; // rax
  LPVOID v276; // rax
  __int64 v277; // rbx
  void *v278; // rcx
  bool v279; // zf
  int v280; // eax
  HANDLE v281; // rax
  _OWORD *v282; // rcx
  _DWORD *v283; // rax
  HANDLE v284; // rax
  _QWORD *v285; // rax
  void *v286; // rcx
  unsigned int *v287; // rbx
  HANDLE v288; // rax
  _QWORD *v289; // rax
  __int64 v290; // rdx
  unsigned int v291; // r9d
  HANDLE v292; // rax
  STRSAFE_PCNZWCH *v293; // rax
  HANDLE v294; // rax
  HANDLE v295; // rax
  HANDLE v296; // rax
  HANDLE v297; // rax
  HANDLE v298; // rax
  HANDLE v299; // rax
  signed int LastError; // eax
  LPVOID v301; // rax
  HANDLE v302; // rax
  HANDLE v303; // rax
  HANDLE v304; // rax
  HANDLE v305; // rax
  HANDLE v306; // rax
  HANDLE v307; // rax
  HANDLE v308; // rax
  HANDLE v309; // rax
  unsigned int v310; // r14d
  int v311; // r11d
  unsigned int *v312; // rcx
  int v313; // r11d
  void *v314; // r9
  int v315; // r10d
  int v316; // r11d
  const wchar_t **v317; // rdx
  const wchar_t *v318; // rax
  unsigned int *v319; // rcx
  unsigned int v320; // r11d
  unsigned int v321; // r14d
  int v322; // r11d
  unsigned int *v323; // r9
  int v324; // r10d
  int v325; // r11d
  unsigned int *v326; // rdx
  unsigned int v327; // eax
  unsigned int *v328; // rcx
  size_t v329; // r14
  int v330; // eax
  unsigned int *v331; // r9
  unsigned int v332; // r11d
  int v333; // r11d
  unsigned int *v334; // rcx
  unsigned int v335; // r11d
  void *v336; // r9
  int v337; // r10d
  int v338; // r11d
  unsigned int *v339; // rdx
  unsigned int v340; // eax
  unsigned int v341; // r11d
  void *v342; // rcx
  __int64 v343; // r10
  unsigned int v344; // r9d
  int v345; // r11d
  void *v346; // r13
  HANDLE v347; // rax
  _OWORD *v348; // rax
  void *v349; // r12
  HANDLE v350; // rax
  unsigned int v351; // ecx
  unsigned int v352; // r11d
  int v353; // eax
  unsigned int v354; // r11d
  int v355; // r9d
  int v356; // eax
  unsigned int v357; // r11d
  int v358; // r9d
  int v359; // eax
  int v360; // r9d
  unsigned int v361; // r14d
  HANDLE v362; // rax
  _DWORD *v363; // rax
  _DWORD *v364; // r14
  unsigned int v365; // r11d
  _DWORD *v366; // rax
  unsigned int v367; // r14d
  unsigned int v368; // eax
  unsigned int v369; // r10d
  unsigned int *v370; // r9
  unsigned int *v371; // r9
  unsigned int v372; // r11d
  unsigned int v373; // r11d
  unsigned int v374; // r10d
  unsigned int *v375; // r9
  unsigned int nn; // r11d
  unsigned int *v377; // r9
  unsigned int *v378; // r10
  unsigned int v379; // r9d
  unsigned int i1; // r11d
  _DWORD *v381; // r10
  unsigned int v382; // r11d
  STRSAFE_PCNZWCH *v383; // rax
  STRSAFE_PCNZWCH v384; // rcx
  __int64 v385; // rcx
  unsigned int v386; // r9d
  int v387; // eax
  char *v388; // r9
  unsigned int v389; // r10d
  unsigned int v390; // eax
  unsigned int v391; // r14d
  HANDLE v392; // rax
  char *v393; // rax
  char *v394; // r14
  int v395; // r9d
  unsigned int v396; // r10d
  void *v397; // rcx
  unsigned int *v398; // rcx
  int v399; // eax
  unsigned __int64 v400; // r11
  unsigned __int8 v401; // al
  unsigned __int64 v402; // r8
  int v403; // r8d
  unsigned int v404; // r9d
  int v405; // r10d
  SIZE_T v406; // r12
  unsigned __int8 *v407; // rdi
  _BYTE *v408; // rsi
  int v409; // r13d
  int v410; // r8d
  unsigned int v411; // eax
  unsigned int v412; // r15d
  int v413; // ecx
  int v414; // r14d
  int v415; // r11d
  int v416; // r14d
  int v417; // r11d
  int v418; // edx
  int v419; // r8d
  int v420; // r10d
  int v421; // r8d
  int v422; // r10d
  int v423; // r9d
  int v424; // r8d
  unsigned int v425; // edx
  int v426; // r9d
  int v427; // ecx
  int v428; // edx
  int v429; // r8d
  int v430; // r9d
  int v431; // edx
  unsigned int v432; // r8d
  unsigned int v433; // r9d
  int v434; // edx
  int v435; // r8d
  int v436; // r9d
  int v437; // edx
  int v438; // r8d
  int v439; // r10d
  int v440; // edx
  int v441; // r9d
  unsigned int v442; // r8d
  int v443; // edx
  __int64 v444; // rdx
  __int64 v445; // r9
  __int64 v446; // rdx
  __int64 v447; // r9
  int v448; // r11d
  __int64 v449; // rdx
  __int64 v450; // r10
  int v451; // r11d
  HANDLE v452; // rax
  _QWORD *v453; // rbx
  HANDLE v454; // rax
  HANDLE v455; // rax
  HANDLE v456; // rax
  HANDLE v457; // rax
  HANDLE v458; // rax
  HANDLE v459; // rax
  HANDLE v460; // rax
  HANDLE v461; // rax
  __int64 v462; // rdx
  unsigned int v463; // r9d
  __int64 v464; // rdx
  unsigned int v465; // ebx
  HANDLE v466; // rax
  _DWORD *v467; // rax
  __int64 v468; // r9
  int v469; // r10d
  void *v470; // rcx
  __int64 v471; // r9
  int v472; // r10d
  LPVOID v473; // rcx
  unsigned int *v474; // r9
  unsigned int v475; // r9d
  const wchar_t *v476; // rbx
  int v477; // eax
  unsigned int v478; // r10d
  int v479; // r9d
  int v480; // r9d
  unsigned int v481; // r10d
  unsigned int v482; // r10d
  int v483; // r9d
  SIZE_T v484; // r11
  unsigned int v485; // r11d
  int v486; // r9d
  unsigned int v487; // r10d
  int v488; // r9d
  unsigned int v489; // r10d
  int v490; // r9d
  int v491; // r10d
  int v492; // r11d
  HANDLE v493; // rax
  _QWORD *v494; // rcx
  void *v495; // rbx
  HANDLE v496; // rax
  void *v497; // rax
  HANDLE v498; // rax
  void *v499; // rcx
  SIZE_T v500; // rax
  const wchar_t *v501; // rax
  HANDLE v502; // rax
  void *v503; // rcx
  unsigned int *v504; // rdx
  HANDLE v505; // rax
  HANDLE v506; // rax
  HANDLE v507; // rax
  HANDLE v508; // rax
  unsigned __int8 v509; // al
  unsigned __int8 *v510; // r11
  int v511; // r10d
  int v512; // r9d
  unsigned int v513; // r8d
  LPVOID v514; // rbx
  int v515; // r12d
  unsigned __int64 v516; // r13
  _BYTE *v517; // rsi
  int v518; // r10d
  unsigned int v519; // r15d
  unsigned int v520; // eax
  int v521; // r14d
  int v522; // edx
  int v523; // ebx
  unsigned int v524; // r8d
  int v525; // r9d
  unsigned int v526; // edx
  int v527; // r8d
  int v528; // r9d
  unsigned int v529; // edx
  int v530; // r8d
  int v531; // r10d
  int v532; // r11d
  unsigned int v533; // r9d
  int v534; // r8d
  unsigned int v535; // r9d
  int v536; // r10d
  int v537; // r11d
  unsigned int v538; // edx
  int v539; // r8d
  int v540; // r9d
  int v541; // edx
  int v542; // r10d
  int v543; // r8d
  unsigned int v544; // edx
  int v545; // ecx
  _DWORD *v546; // rdi
  unsigned __int64 v547; // rcx
  void *v548; // rdi
  void *v549; // rbx
  _QWORD *v550; // rbx
  HANDLE v551; // rax
  HANDLE v552; // rax
  HANDLE v553; // rax
  HANDLE v554; // rax
  void *v555; // rbx
  _QWORD *v556; // rbx
  void *v557; // r14
  HANDLE v558; // rax
  void *v559; // r14
  HANDLE v560; // rax
  void *v561; // r14
  HANDLE v562; // rax
  HANDLE v563; // rax
  HANDLE v564; // rax
  unsigned int v565; // r9d
  __int64 v566; // r11
  void *v567; // r14
  HANDLE v568; // rax
  HANDLE v569; // rax
  HANDLE v570; // rax
  HANDLE v571; // rax
  unsigned int v572; // r9d
  int v573; // r11d
  unsigned int v574; // r11d
  int v575; // r9d
  bool v576; // sf
  SIZE_T v577; // rax
  HANDLE v578; // rax
  HANDLE v579; // rax
  HANDLE v580; // rax
  HANDLE v581; // rax
  int v582; // eax
  void *v583; // r9
  __int64 v584; // r10
  void *v585; // r11
  __int64 v586; // rdx
  unsigned int *v587; // rbx
  void *v588; // r11
  void *v589; // r9
  __int64 v590; // r10
  STRSAFE_PCNZWCH v591; // r9
  __int64 v592; // r10
  unsigned __int64 v593; // r9
  unsigned int v594; // r10d
  __int64 v595; // rdx
  wchar_t *v596; // rcx
  HANDLE v597; // rax
  SIZE_T v598; // rdi
  void *v599; // rcx
  int i4; // r9d
  unsigned int v601; // r10d
  int v602; // r9d
  STRSAFE_PCNZWCH v603; // rcx
  unsigned int v604; // r14d
  unsigned int v605; // edi
  unsigned __int8 *v606; // rbx
  int v607; // esi
  int v608; // eax
  int v609; // r8d
  int v610; // r8d
  unsigned int v611; // ecx
  unsigned int v612; // edx
  unsigned int v613; // edi
  char *v614; // r15
  char v615; // bl
  HANDLE v616; // rax
  HANDLE v617; // rax
  HANDLE v618; // rax
  int *v619; // rcx
  int v620; // eax
  unsigned int v621; // r11d
  unsigned int v622; // r10d
  unsigned __int8 *v623; // rdi
  unsigned int v624; // ebx
  int v625; // esi
  int v626; // r9d
  int v627; // r9d
  unsigned int v628; // r10d
  unsigned int v629; // ecx
  int v630; // edx
  _BYTE *v631; // rbx
  char v632; // di
  LPVOID v633; // rcx
  unsigned int *v634; // r9
  unsigned int v635; // r9d
  unsigned int v636; // edi
  int v637; // r15d
  int v638; // r8d
  _BYTE *v639; // rcx
  unsigned int v640; // r9d
  int v641; // edx
  int v642; // ebx
  unsigned int v643; // edi
  char v644; // si
  unsigned int v645; // ecx
  HANDLE v646; // rax
  HANDLE v647; // rax
  HANDLE v648; // rax
  int v649; // [rsp+30h] [rbp-D0h]
  int v650; // [rsp+30h] [rbp-D0h]
  _DWORD v651[3]; // [rsp+34h] [rbp-CCh] BYREF
  unsigned int v652; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v653; // [rsp+44h] [rbp-BCh] BYREF
  int v654; // [rsp+48h] [rbp-B8h]
  unsigned int v655; // [rsp+4Ch] [rbp-B4h] BYREF
  SIZE_T v656; // [rsp+50h] [rbp-B0h]
  unsigned __int8 v657; // [rsp+58h] [rbp-A8h]
  STRSAFE_PCNZWCH psz; // [rsp+60h] [rbp-A0h] BYREF
  void *v659; // [rsp+68h] [rbp-98h] BYREF
  LPVOID v660; // [rsp+70h] [rbp-90h]
  LPVOID v661; // [rsp+78h] [rbp-88h]
  SIZE_T dwBytes; // [rsp+80h] [rbp-80h]
  LPVOID v663; // [rsp+88h] [rbp-78h]
  void *v664; // [rsp+90h] [rbp-70h] BYREF
  void *v665; // [rsp+98h] [rbp-68h]
  LPVOID v666; // [rsp+A0h] [rbp-60h]
  LPVOID v667; // [rsp+A8h] [rbp-58h] BYREF
  LPVOID v668; // [rsp+B0h] [rbp-50h] BYREF
  LPVOID Src[2]; // [rsp+B8h] [rbp-48h] BYREF
  LPVOID v670; // [rsp+C8h] [rbp-38h]
  LPVOID v671; // [rsp+D0h] [rbp-30h]
  _DWORD *v672; // [rsp+D8h] [rbp-28h] BYREF
  size_t v673[2]; // [rsp+E0h] [rbp-20h] BYREF
  SIZE_T v674; // [rsp+F0h] [rbp-10h] BYREF
  LPVOID lpMem; // [rsp+F8h] [rbp-8h]
  int v676; // [rsp+100h] [rbp+0h]
  void *v677; // [rsp+108h] [rbp+8h] BYREF
  SIZE_T Size; // [rsp+110h] [rbp+10h]
  void *v679; // [rsp+118h] [rbp+18h] BYREF
  unsigned int v680; // [rsp+120h] [rbp+20h] BYREF
  LPVOID v681; // [rsp+128h] [rbp+28h]
  unsigned int v682; // [rsp+130h] [rbp+30h] BYREF
  unsigned int v683; // [rsp+134h] [rbp+34h] BYREF
  int v684; // [rsp+138h] [rbp+38h]
  unsigned int v685; // [rsp+13Ch] [rbp+3Ch] BYREF
  unsigned int v686; // [rsp+140h] [rbp+40h]
  size_t v687; // [rsp+148h] [rbp+48h] BYREF
  size_t pcchLength[2]; // [rsp+150h] [rbp+50h] BYREF
  HMODULE hModule; // [rsp+160h] [rbp+60h] BYREF
  HMODULE phModule; // [rsp+170h] [rbp+70h] BYREF
  __int128 v691; // [rsp+178h] [rbp+78h] BYREF
  __int128 v692; // [rsp+188h] [rbp+88h]
  __int128 v693; // [rsp+198h] [rbp+98h] BYREF
  __int128 v694; // [rsp+1A8h] [rbp+A8h]
  DWORD *v695; // [rsp+1C0h] [rbp+C0h]
  HLOCAL hMem; // [rsp+1C8h] [rbp+C8h]

  v695 = pdwValue;
  v2 = pdwValue;
  psz = pwszValueName;
  if ( !pwszValueName || !pdwValue )
    return -2147024809;
  v4 = 0;
  hMem = 0;
  v5 = LocalAlloc(0x40u, 4u);
  v677 = v5;
  v6 = v5;
  if ( !v5 )
  {
    v13 = -2147024882;
    goto LABEL_26;
  }
  v684 = 0;
  v686 = 0;
  *(_OWORD *)Src = 0;
  v668 = 0;
  ProcessHeap = GetProcessHeap();
  v8 = HeapAlloc(ProcessHeap, 8u, 0xA0u);
  v654 = -805306345;
  v676 = -1;
  v9 = v8;
  if ( !v8 )
  {
    v12 = 0;
    v13 = -1073741801;
    v649 = -1073741801;
    v9 = 0;
    goto LABEL_11;
  }
  *v8 = `WarbirdUmGetDecryptionCipher'::`2'::DecryptionCipher;
  v8[1] = xmmword_1800E5580;
  v8[2] = xmmword_1800E5590;
  v8[3] = xmmword_1800E55A0;
  v8[4] = xmmword_1800E55B0;
  v8[5] = xmmword_1800E55C0;
  v8[6] = xmmword_1800E55D0;
  v8[7] = xmmword_1800E55E0;
  v8[8] = xmmword_1800E55F0;
  v8[9] = xmmword_1800E5600;
  v10 = GetProcessHeap();
  v11 = HeapAlloc(v10, 8u, 8u);
  v12 = v11;
  if ( !v11 )
  {
    v13 = -1073741801;
    v12 = 0;
    v649 = -1073741801;
    goto LABEL_11;
  }
  *v11 = `WarbirdUmGetDecryptionKey'::`2'::nDecryptionKey;
  v674 = __rdtsc();
  pcchLength[0] = 0;
  if ( StringLengthWorkerW(pwszValueName, (unsigned __int64)HIDWORD(v674) << 32, pcchLength) < 0 )
  {
    pcchLength[0] = 0;
LABEL_722:
    v13 = -1073741762;
    goto LABEL_10;
  }
  ++pcchLength[0];
  if ( (unsigned int)(2 * LODWORD(pcchLength[0])) >= 0xFFFFFFFC )
  {
    v13 = -1073741675;
    v649 = -1073741675;
    goto LABEL_11;
  }
  v179 = 2 * LODWORD(pcchLength[0]) + 200;
  v651[0] = 0;
  v180 = -1;
  if ( v179 >= 0xC4 )
    v180 = 2 * LODWORD(pcchLength[0]) + 200;
  v13 = v179 < 0xC4 ? -805306219 : 0x10000000;
  v649 = v13;
  if ( v179 < 0xC4 )
    goto LABEL_179;
  v181 = v180 + 8;
  v182 = -1;
  if ( v180 + 8 >= v180 )
    v182 = v180 + 8;
  v13 = v181 < v180 ? -805306219 : 0x10000000;
  v649 = v13;
  if ( v181 < v180 )
    goto LABEL_179;
  v183 = v182 + 8;
  v184 = -1;
  if ( v182 + 8 >= v182 )
    v184 = v182 + 8;
  v13 = v183 < v182 ? -805306219 : 0x10000000;
  v649 = v13;
  if ( v183 < v182 )
    goto LABEL_179;
  HIDWORD(Src[0]) = v184;
  v185 = v184;
  v186 = GetProcessHeap();
  v187 = HeapAlloc(v186, 8u, v185);
  if ( !v187 )
  {
    v13 = -1073741801;
    goto LABEL_10;
  }
  Src[1] = v187;
  LODWORD(Src[0]) = 0;
  v652 = 8;
  if ( v187 + 1 < v187 )
    goto LABEL_162;
  if ( v187 + 2 > (_DWORD *)((char *)Src[1] + HIDWORD(Src[0])) )
    goto LABEL_427;
  *v187 = 4;
  v187[1] = 0;
  v188 = ++LODWORD(Src[0]);
  if ( !v9 )
  {
LABEL_167:
    v13 = -1073741811;
    goto LABEL_163;
  }
  v604 = v652;
  v206 = Src[1];
  if ( Src[1] )
  {
    for ( i = 0; i < v188; ++i )
    {
      v208 = *v206 + 4;
      if ( *v206 >= 0xFFFFFFFC || (_DWORD *)((char *)v206 + v208) < v206 )
        goto LABEL_162;
      v206 = (_DWORD *)((char *)v206 + v208);
    }
    if ( v206 + 1 < v206 )
      goto LABEL_162;
    if ( v206 + 41 > (_DWORD *)((char *)Src[1] + HIDWORD(Src[0])) )
      goto LABEL_427;
    *v206 = 160;
    memcpy_0(v206 + 1, v9, 0xA0u);
  }
  else
  {
    v652 = 0;
    v649 = RtlUIntAdd(4, 160, &v652);
    v13 = v649;
    if ( v649 < 0 )
      goto LABEL_179;
    v649 = RtlUIntAdd(HIDWORD(Src[0]), v652, (char *)Src + 4);
    v13 = v649;
    if ( v649 < 0 )
      goto LABEL_179;
  }
  v209 = ++LODWORD(Src[0]);
  if ( v12 )
  {
    if ( !v604 )
      goto LABEL_167;
  }
  else if ( v604 )
  {
    goto LABEL_167;
  }
  v210 = (unsigned int *)Src[1];
  if ( Src[1] )
  {
    for ( j = 0; j < v209; ++j )
    {
      v212 = *v210 + 4;
      if ( *v210 >= 0xFFFFFFFC || (unsigned int *)((char *)v210 + v212) < v210 )
        goto LABEL_162;
      v210 = (unsigned int *)((char *)v210 + v212);
    }
    if ( v210 + 1 < v210 )
      goto LABEL_162;
    if ( (char *)v210 + v604 + 4 > (char *)Src[1] + HIDWORD(Src[0]) )
      goto LABEL_427;
    *v210 = v604;
    if ( v12 )
      memcpy_0(v210 + 1, v12, v604);
  }
  else
  {
    v652 = 0;
    v649 = RtlUIntAdd(4, v604, &v652);
    v13 = v649;
    if ( v649 < 0 )
      goto LABEL_179;
    v649 = RtlUIntAdd(HIDWORD(Src[0]), v652, (char *)Src + 4);
    v13 = v649;
    if ( v649 < 0 )
      goto LABEL_179;
  }
  v213 = (char *)Src[1];
  v214 = ++LODWORD(Src[0]);
  if ( Src[1] )
  {
    for ( k = 0; k < v214; ++k )
    {
      v216 = *(_DWORD *)v213 + 4;
      if ( *(_DWORD *)v213 >= 0xFFFFFFFC || &v213[v216] < v213 )
        goto LABEL_162;
      v213 += v216;
    }
    if ( v213 + 4 >= v213 )
    {
      if ( v213 + 12 > (char *)Src[1] + HIDWORD(Src[0]) )
        goto LABEL_427;
      v217 = v674;
      *(_DWORD *)v213 = 8;
      *(_QWORD *)(v213 + 4) = v217;
      goto LABEL_243;
    }
LABEL_162:
    v13 = -1073741675;
LABEL_163:
    v649 = v13;
    goto LABEL_179;
  }
  v652 = 0;
  v649 = RtlUIntAdd(4, 8, &v652);
  v13 = v649;
  if ( v649 < 0 )
    goto LABEL_179;
  v649 = RtlUIntAdd(HIDWORD(Src[0]), v652, (char *)Src + 4);
  v13 = v649;
  if ( v649 < 0 )
    goto LABEL_179;
LABEL_243:
  ++LODWORD(Src[0]);
  v687 = 0;
  if ( StringLengthWorkerW(psz, (size_t)v213, &v687) < 0 )
  {
    v687 = 0;
    goto LABEL_722;
  }
  v219 = v687 + 1;
  if ( v687 + 1 < v687 )
  {
    v687 = -1;
    goto LABEL_111;
  }
  ++v687;
  v220 = (unsigned int)(2 * v219);
  if ( !(_DWORD)v220 )
  {
    v13 = -1073741811;
LABEL_724:
    v649 = v13;
    goto LABEL_173;
  }
  v189 = Src[1];
  if ( Src[1] )
  {
    for ( m = 0; m < LODWORD(Src[0]); ++m )
    {
      v191 = *v189 + 4;
      if ( *v189 >= 0xFFFFFFFC || (_DWORD *)((char *)v189 + v191) < v189 )
        goto LABEL_172;
      v189 = (_DWORD *)((char *)v189 + v191);
    }
    if ( v189 + 1 < v189 )
    {
LABEL_172:
      v13 = -1073741675;
      v649 = -1073741675;
      goto LABEL_173;
    }
    if ( (char *)v189 + v220 + 4 > (char *)Src[1] + HIDWORD(Src[0]) )
    {
      v13 = -1073741789;
      goto LABEL_724;
    }
    *v189 = v220;
    v13 = 0;
    v649 = 0;
    memcpy_0(v189 + 1, v218, (unsigned int)v220);
    ++LODWORD(Src[0]);
  }
  else
  {
    v652 = 0;
    v649 = RtlUIntAdd(4, (unsigned int)v220, &v652);
    v13 = v649;
    if ( v649 >= 0 )
    {
      v649 = RtlUIntAdd(HIDWORD(Src[0]), v652, (char *)Src + 4);
      v13 = v649;
      if ( v649 >= 0 )
      {
        ++LODWORD(Src[0]);
        v13 = 0;
        goto LABEL_724;
      }
    }
  }
LABEL_173:
  if ( v13 < 0 )
    goto LABEL_11;
  v192 = Src[1];
  if ( Src[1] )
  {
    for ( n = 0; n < LODWORD(Src[0]); ++n )
    {
      v194 = *v192 + 4;
      if ( *v192 >= 0xFFFFFFFC || (_DWORD *)((char *)v192 + v194) < v192 )
        goto LABEL_178;
      v192 = (_DWORD *)((char *)v192 + v194);
    }
    if ( v192 + 1 < v192 )
      goto LABEL_178;
    if ( v192 + 2 > (_DWORD *)((char *)Src[1] + HIDWORD(Src[0])) )
      goto LABEL_427;
    *v192 = 4;
    v192[1] = 0;
  }
  else
  {
    v652 = 0;
    v649 = RtlUIntAdd(4, 4, &v652);
    v13 = v649;
    if ( v649 < 0 )
      goto LABEL_179;
    v649 = RtlUIntAdd(HIDWORD(Src[0]), v652, (char *)Src + 4);
    v13 = v649;
    if ( v649 < 0 )
      goto LABEL_179;
  }
  v196 = Src[1];
  v197 = ++LODWORD(Src[0]);
  if ( Src[1] )
  {
    for ( ii = 0; ii < v197; ++ii )
    {
      v199 = *v196 + 4;
      if ( *v196 >= 0xFFFFFFFC || (_DWORD *)((char *)v196 + v199) < v196 )
        goto LABEL_178;
      v196 = (_DWORD *)((char *)v196 + v199);
    }
    if ( v196 + 1 >= v196 )
    {
      if ( v196 + 2 > (_DWORD *)((char *)Src[1] + HIDWORD(Src[0])) )
        goto LABEL_427;
      *v196 = 4;
      v196[1] = 4;
      goto LABEL_198;
    }
LABEL_178:
    v13 = -1073741675;
    v649 = -1073741675;
    goto LABEL_179;
  }
  v652 = 0;
  v649 = RtlUIntAdd(4, 4, &v652);
  v13 = v649;
  if ( v649 < 0 )
    goto LABEL_179;
  v649 = RtlUIntAdd(HIDWORD(Src[0]), v652, (char *)Src + 4);
  v13 = v649;
  if ( v649 < 0 )
    goto LABEL_179;
LABEL_198:
  ++LODWORD(Src[0]);
  psz = (STRSAFE_PCNZWCH)__rdtsc();
  if ( HIDWORD(Src[0]) >= 0xFFFFFFF8
    || (v200 = (void *)((HIDWORD(Src[0]) + 15) & 0xFFFFFFF8), v670 = v200, (unsigned int)v200 < HIDWORD(Src[0]) + 8) )
  {
    v13 = -805306219;
    goto LABEL_10;
  }
  v653 = 0;
  v201 = (unsigned int)v200;
  v202 = GetProcessHeap();
  v64 = HeapAlloc(v202, 8u, (unsigned int)v201);
  if ( !v64 )
  {
    v13 = -805306345;
    v649 = -805306345;
    goto LABEL_64;
  }
  *v64 = Src[0];
  if ( v64 + 1 < v64 || (v64[1] = HIDWORD(Src[0]), v64 + 2 < v64 + 1) )
  {
    lpMem = v64;
    LODWORD(v670) = 0;
    v14 = GetProcessHeap();
    HeapFree(v14, 0, lpMem);
    v13 = -805306219;
    v649 = -805306219;
    goto LABEL_64;
  }
  *(_QWORD *)((char *)v64 + v201 - 8) = psz;
  memcpy_0(v64 + 2, Src[1], HIDWORD(Src[0]));
  v23 = (unsigned int)v670;
  v660 = 0;
  *(_QWORD *)&v651[1] = 0;
  v681 = 0;
  v663 = 0;
  v667 = 0;
  v666 = 0;
  if ( !(_DWORD)v670 || (dwBytes = (unsigned int)v670 + 8LL, v664 = MemoryAlloc(dwBytes), (v24 = (char *)v664) == 0) )
  {
    v13 = -805306367;
    v649 = -805306367;
    goto LABEL_766;
  }
  v25 = 0;
  v26 = 0;
  v657 = 0;
  if ( v23 )
  {
    do
      v25 ^= *((_BYTE *)v64 + v26++);
    while ( v26 < v23 );
    v657 = v25;
  }
  v665 = v9;
  v659 = v12;
  v661 = (LPVOID)0xC81ECB17B1B54A58LL;
  v656 = (SIZE_T)v64;
  if ( v23 >> 3 )
  {
    v27 = HIDWORD(v661);
    v28 = (unsigned __int8 *)v64;
    v29 = WORD1(v661);
    v30 = v664;
    v31 = HIWORD(v661);
    v32 = -1;
    v33 = WORD2(v661);
    lpMem = 0;
    v655 = 0;
    v651[0] = 0;
    v652 = 0;
    do
    {
      v34 = v28[1];
      v35 = *v28;
      v36 = v28[4];
      v28 += 8;
      v37 = *(v28 - 5) | ((*(v28 - 6) | ((v34 | (v35 << 8)) << 8)) << 8);
      v38 = *(v28 - 1) | ((*(v28 - 2) | ((*(v28 - 3) | (v36 << 8)) << 8)) << 8);
      v39 = v32 ^ v38;
      v40 = v652 ^ v37 ^ v27 ^ ((v32 ^ v38) - 19032);
      v41 = v39 ^ (__ROR4__(v40, 7) + v29 * __ROR4__(v40 ^ v27, 15));
      v42 = v40 ^ (v33 * __ROR4__(v41 - 1313519016, 9) - __ROR4__(v41, 10));
      v43 = v41 ^ (__ROR4__(v42, 27) + v31 * __ROR4__(v42 ^ v33, 28));
      v44 = v42 ^ (HIDWORD(v661) - (v43 ^ 0xB1B54A58));
      v45 = v44 ^ (19032 * (v33 ^ __ROR4__(v43 ^ (WORD1(v661) * (v44 - 19032) - (v44 >> 6)), 15)));
      v46 = v43 ^ (WORD1(v661) * (v44 - 19032) - (v44 >> 6)) ^ (v33 * (v31 + __ROR4__(~v45, 3)));
      v47 = v45 ^ (v46 - HIDWORD(v661) - 19032);
      v48 = v46 ^ (WORD1(v661) * (v31 ^ v47)) ^ __ROR4__(v47, 10);
      v49 = v47 ^ __ROR4__(v48, 3) ^ (v33 * __ROR4__(v48 ^ 0x4A58, 26));
      v50 = v48 ^ (19032 * (__ROR4__(v49, 15) - v31));
      v51 = v49
          ^ (19032 * (v31 ^ v50))
          ^ ((v50 ^ (v50 >> 14)) >> 1)
          ^ (19032 * ((8 * (v50 - v33)) | ((v50 - v33) >> 29)));
      v52 = v50 ^ (WORD1(v661) * (v51 - v33) - (v51 >> 13));
      v53 = v51 ^ __ROR4__(v52, 11) ^ (v33 * __ROR4__(-1313519016 - v52, 9));
      v54 = v52 ^ (v53 + 1313519016 - v31);
      v55 = v53 ^ (19032 * (v54 ^ WORD1(v661)) - __ROR4__(v54, 7));
      v56 = v54 ^ (WORD1(v661) * __ROR4__(v31 ^ v55, 28) - __ROR4__(v55, 16));
      v57 = v55 ^ (__ROR4__(v56, 4) + v33 * __ROR4__(-1313519016 - v56, 10));
      v58 = v56 ^ __ROR4__(v57, 9) ^ (v31 * __ROR4__(v57 + 1313519016, 4));
      v59 = v57 ^ (19032 * __ROR4__(v58 ^ HIDWORD(v661), 24) - __ROR4__(v58, 30));
      v27 = HIDWORD(v661);
      v60 = v58 ^ (WORD1(v661) * __ROR4__(HIDWORD(v661) - v59, 11) - __ROR4__(v59, 12));
      v61 = v59 ^ (v60 >> 8) ^ (v33 * (v60 ^ WORD1(v661)));
      v62 = v655 ^ v61;
      v63 = v651[0] ^ v61 ^ HIDWORD(v661) ^ 0xB1B54A58;
      v30[3] = v655 ^ v61;
      v32 = v60 ^ v63;
      v29 = WORD1(v661);
      v652 = v62;
      v30[7] = v32;
      v30[2] = __ROR4__(v62, 8);
      v30[6] = __ROR4__(v32, 8);
      v30[1] = __ROR4__(v652, 16);
      v30[5] = __ROR4__(v32, 16);
      *v30 = __ROR4__(v652, 24);
      v30[4] = __ROR4__(v32, 24);
      v30 += 8;
      v655 = v37;
      v651[0] = v38;
      lpMem = (char *)lpMem + 1;
    }
    while ( (unsigned __int64)lpMem < v23 >> 3 );
    v25 = v657;
    v6 = v677;
    v9 = v665;
    v12 = v659;
    v64 = (_DWORD *)v656;
    v23 = (unsigned int)v670;
    v24 = (char *)v664;
  }
  *(_QWORD *)&v24[v23] = v25;
  v65 = GetProcessHeap();
  v670 = HeapAlloc(v65, 8u, 0x30u);
  v66 = v670;
  if ( v670 )
  {
    *(_DWORD *)v670 = dwBytes;
    v656 = (SIZE_T)v64;
    v67 = GetProcessHeap();
    v68 = HeapAlloc(v67, 8u, (unsigned int)dwBytes);
    if ( v68 )
    {
      v66[1] = v68;
      memcpy_0(v68, v664, (unsigned int)dwBytes);
      *((_DWORD *)v66 + 4) = 160;
      v69 = GetProcessHeap();
      v70 = HeapAlloc(v69, 8u, 0xA0u);
      if ( v70 )
      {
        v66[3] = v70;
        *v70 = `WarbirdUmGetEncryptionCipher'::`2'::EncryptionCipher;
        v70[1] = xmmword_1800E54D0;
        v70[2] = xmmword_1800E54E0;
        v70[3] = xmmword_1800E54F0;
        v70[4] = xmmword_1800E5500;
        v70[5] = xmmword_1800E5510;
        v70[6] = xmmword_1800E5520;
        v70[7] = xmmword_1800E5530;
        v70[8] = xmmword_1800E5540;
        v70[9] = xmmword_1800E5550;
        *((_DWORD *)v66 + 8) = 8;
        v71 = GetProcessHeap();
        v72 = HeapAlloc(v71, 8u, 8u);
        if ( v72 )
        {
          v66[5] = v72;
          *v72 = `WarbirdUmGetEncryptionKey'::`2'::nEncryptionKey;
          v73 = v66;
          v74 = 0;
          v656 = (SIZE_T)v64;
          v660 = 0;
          goto LABEL_52;
        }
      }
      v293 = (STRSAFE_PCNZWCH *)v670;
      v656 = (SIZE_T)v64;
    }
    else
    {
      v293 = (STRSAFE_PCNZWCH *)v670;
    }
    v74 = -1073741801;
    psz = v293[1];
    if ( psz )
    {
      v292 = GetProcessHeap();
      HeapFree(v292, 0, (LPVOID)psz);
      v293 = (STRSAFE_PCNZWCH *)v670;
      *((_QWORD *)v670 + 1) = 0;
    }
    psz = v293[3];
    if ( psz )
    {
      v294 = GetProcessHeap();
      HeapFree(v294, 0, (LPVOID)psz);
      v293 = (STRSAFE_PCNZWCH *)v670;
      *((_QWORD *)v670 + 3) = 0;
    }
    psz = v293[5];
    if ( psz )
    {
      v295 = GetProcessHeap();
      HeapFree(v295, 0, (LPVOID)psz);
      *((_QWORD *)v670 + 5) = 0;
    }
    v75 = GetProcessHeap();
    HeapFree(v75, 0, v670);
  }
  else
  {
    v74 = -1073741801;
  }
  v73 = *(_QWORD **)&v651[1];
LABEL_52:
  *(_QWORD *)&v651[1] = v73;
  v76 = GetProcessHeap();
  HeapFree(v76, 0, v664);
  v77 = v660;
  if ( v660 )
  {
    psz = (STRSAFE_PCNZWCH)*((_QWORD *)v660 + 1);
    if ( psz )
    {
      v296 = GetProcessHeap();
      HeapFree(v296, 0, (LPVOID)psz);
      v77 = v660;
      *((_QWORD *)v660 + 1) = 0;
    }
    psz = (STRSAFE_PCNZWCH)*((_QWORD *)v77 + 3);
    if ( psz )
    {
      v297 = GetProcessHeap();
      HeapFree(v297, 0, (LPVOID)psz);
      v77 = v660;
      *((_QWORD *)v660 + 3) = 0;
    }
    psz = (STRSAFE_PCNZWCH)*((_QWORD *)v77 + 5);
    if ( psz )
    {
      v298 = GetProcessHeap();
      HeapFree(v298, 0, (LPVOID)psz);
      *((_QWORD *)v660 + 5) = 0;
    }
    v299 = GetProcessHeap();
    HeapFree(v299, 0, v660);
    v78 = *(_DWORD **)&v651[1];
  }
  else
  {
    v78 = *(_DWORD **)&v651[1];
  }
  v13 = v74 | 0x10000000;
  v649 = v13;
  if ( v13 >= 0 )
  {
    v86 = *v78 + 4;
    v655 = 0;
    if ( v86 < 4
      || (v93 = v86 + 4, v86 + 4 < v86)
      || (v94 = v93 + v78[4], lpMem = v78 + 4, v94 < v93)
      || (v95 = v94 + 4, v94 + 4 < v94)
      || (v96 = v95 + v78[8], v652 = v96, v96 < v95) )
    {
      v87 = -1073741675;
      goto LABEL_75;
    }
    v97 = v96;
    v98 = GetProcessHeap();
    v99 = HeapAlloc(v98, 8u, v97);
    v661 = v99;
    if ( !v99 )
    {
      v64 = (_DWORD *)v656;
      v13 = -805306345;
LABEL_115:
      v649 = v13;
      goto LABEL_55;
    }
    v100 = *(const void ***)&v651[1];
    v101 = v99 + 1;
    *v99 = **(_DWORD **)&v651[1];
    if ( v99 + 1 < v99 )
    {
      v661 = v99;
    }
    else
    {
      memcpy_0(v99 + 1, v100[1], *(unsigned int *)v100);
      v102 = (_DWORD *)((char *)v101 + *(unsigned int *)v100);
      if ( v102 >= v101 )
      {
        v103 = (unsigned int *)lpMem;
        v104 = v102 + 1;
        *v102 = *(_DWORD *)lpMem;
        if ( v102 + 1 >= v102 )
        {
          memcpy_0(v102 + 1, v100[3], *v103);
          v105 = (_DWORD *)((char *)v104 + *(unsigned int *)lpMem);
          if ( v105 >= v104 )
          {
            *v105 = *((_DWORD *)v100 + 8);
            v659 = v105;
            v87 = RtlULongLongAdd(v105, 4, &v659);
            if ( v87 >= 0 )
            {
              memcpy_0(v659, v100[5], *((unsigned int *)v100 + 8));
              v87 = RtlULongLongAdd(v659, *((unsigned int *)v100 + 8), &v659);
              if ( v87 >= 0 )
              {
                v64 = (_DWORD *)v656;
                v681 = v661;
                v655 = v652;
LABEL_75:
                v13 = v87 | 0x10000000;
                v649 = v13;
                if ( v13 < 0 )
                  goto LABEL_55;
                v683 = 64;
                v649 = RtlUIntAdd(64, 8, &v683);
                v13 = v649;
                if ( v649 < 0 )
                  goto LABEL_55;
                v89 = (unsigned int *)Src[1];
                if ( !Src[1] || LODWORD(Src[0]) <= 1 )
                  goto LABEL_733;
                for ( jj = 0; ; jj = 1 )
                {
                  v91 = *v89;
                  v92 = v89 + 1;
                  if ( jj )
                    break;
                  if ( v92 < v89 )
                    goto LABEL_114;
                  v89 = (unsigned int *)((char *)v92 + v91);
                  if ( (unsigned int *)((char *)v92 + v91) < v92 )
                    goto LABEL_114;
                }
                if ( v92 < v89 )
                {
LABEL_114:
                  v13 = -1073741675;
                  goto LABEL_115;
                }
                if ( LODWORD(Src[0]) <= 2 )
                {
LABEL_733:
                  v13 = -1073741811;
                  goto LABEL_115;
                }
                v225 = (unsigned int *)Src[1];
                for ( kk = 0; ; ++kk )
                {
                  v227 = v88;
                  v652 = *v225;
                  v228 = v225 + 1;
                  dwBytes = (SIZE_T)v9;
                  v665 = v12;
                  v660 = v64;
                  v656 = v88;
                  if ( kk >= 2 )
                    break;
                  if ( v228 < v225 )
                    goto LABEL_114;
                  v225 = (unsigned int *)((char *)v228 + v652);
                  if ( v225 < v228 )
                    goto LABEL_114;
                }
                if ( v228 < v225 )
                  goto LABEL_114;
                if ( v683 >= 0xFFFFFFFC )
                  goto LABEL_114;
                v229 = v683 + 8;
                if ( v683 + 8 < v683 + 4 )
                  goto LABEL_114;
                v230 = v229 + v91;
                if ( v229 + (unsigned int)v91 < v229 )
                  goto LABEL_114;
                v231 = v230 + 4;
                if ( v230 + 4 < v230 )
                  goto LABEL_114;
                v232 = v231 + v652;
                v652 = v232;
                if ( v232 < v231 )
                  goto LABEL_114;
                if ( v232 > 0x400000 )
                {
                  v13 = -2147418113;
                  *(_QWORD *)&v651[1] = v227;
                  goto LABEL_115;
                }
                v233 = GetProcessHeap();
                *(_QWORD *)&v235 = HeapAlloc(v233, 8u, v232);
                v234 = v656;
                *((_QWORD *)&v235 + 1) = v235;
                *(_QWORD *)&v651[1] = v656;
                v663 = (LPVOID)v235;
                if ( !(_QWORD)v235 )
                {
                  v13 = -805306345;
                  v663 = 0;
                  goto LABEL_115;
                }
                *(_QWORD *)&v235 = v681;
                phModule = 0;
                v693 = 0;
                v694 = 0;
                if ( !v681 )
                {
                  v13 = -2147024809;
                  v649 = -2147024809;
                  goto LABEL_404;
                }
                v693 = v235;
                LODWORD(v694) = v655;
                *(_QWORD *)((char *)&v694 + 4) = v232;
                if ( GetModuleHandleExW(1u, L"ntdll.dll", &phModule)
                  && (ProcAddress = GetProcAddress(phModule, "NtQuerySystemInformation")) != 0 )
                {
                  v237 = ((__int64 (__fastcall *)(__int64, __int128 *))ProcAddress)(134, &v693);
                  v13 = v237 | 0x10000000;
                  v649 = v237 | 0x10000000;
                  if ( v237 >= 0 )
                  {
                    v238 = DWORD1(v694);
                    goto LABEL_291;
                  }
                }
                else
                {
                  LastError = GetLastError();
                  v649 = LastError;
                  v13 = LastError;
                  if ( LastError > 0 )
                  {
                    v13 = (unsigned __int16)LastError | 0x80070000;
                    v649 = v13;
                  }
                  if ( v13 >= 0 )
                  {
                    v13 = -2147467259;
                    v649 = -2147467259;
LABEL_403:
                    v234 = *(_QWORD *)&v651[1];
                    *((_QWORD *)&v235 + 1) = v663;
LABEL_404:
                    v663 = (LPVOID)*((_QWORD *)&v235 + 1);
                    *(_QWORD *)&v651[1] = v234;
                    goto LABEL_55;
                  }
                }
                v238 = v652;
                if ( v13 == -805306333 )
                {
                  v13 = -2147024774;
                  goto LABEL_148;
                }
                if ( v13 >= 0 )
                {
LABEL_291:
                  if ( v238 < 4 )
                  {
                    v13 = -805306306;
                    goto LABEL_148;
                  }
                  v239 = *(unsigned int *)v663;
                  v240 = (char *)v663 + 4;
                  v679 = (char *)v663 + 4;
                  if ( (char *)v663 + 4 >= v663 )
                  {
                    if ( v238 - 4 < (unsigned int)v239 )
                      goto LABEL_147;
                    v241 = (unsigned int *)&v240[v239];
                    lpMem = &v240[v239];
                    if ( &v240[v239] < v240 || (unsigned int)v239 >= 0xFFFFFFFC )
                      goto LABEL_149;
                    if ( v238 - ((_DWORD)v239 + 4) < 4 )
                      goto LABEL_147;
                    v242 = *v241;
                    v243 = v241 + 1;
                    v652 = *v241;
                    if ( v241 + 1 < v241 )
                      goto LABEL_149;
                    v244 = v239 + 8;
                    if ( (int)v239 + 8 < (unsigned int)(v239 + 4) )
                      goto LABEL_149;
                    if ( v238 - v244 < (unsigned int)v242 )
                      goto LABEL_147;
                    v245 = (unsigned __int64)v243 + v242;
                    Size = v242;
                    psz = (STRSAFE_PCNZWCH)((char *)v243 + v242);
                    if ( (unsigned int *)((char *)v243 + v242) < v243 )
                      goto LABEL_149;
                    v246 = v244 + v242;
                    if ( v244 + (unsigned int)v242 < v244 )
                      goto LABEL_149;
                    if ( v238 - v246 < 4 )
                    {
LABEL_147:
                      v13 = -805306306;
LABEL_148:
                      v178 = v656;
LABEL_150:
                      *(_QWORD *)&v651[1] = v178;
                      goto LABEL_115;
                    }
                    v659 = (void *)(v245 + 4);
                    if ( v245 + 4 >= v245 )
                    {
                      v247 = v246 + 4;
                      if ( v246 + 4 >= v246 )
                      {
                        v248 = *(_DWORD *)psz;
                        v655 = v248;
                        if ( v238 - v247 >= v248 )
                        {
                          if ( v247 + v248 < v247 )
                          {
                            v13 = -805306219;
                            goto LABEL_115;
                          }
                          if ( v238 == v247 + v248 && (unsigned int)v242 + (_DWORD)v239 + v248 + 12LL == v238 )
                          {
                            v115 = GetProcessHeap();
                            v116 = HeapAlloc(v115, 8u, 0x30u);
                            v670 = v116;
                            v117 = v116;
                            if ( !v116 )
                            {
                              v13 = -805306345;
                              v64 = v660;
                              *(_QWORD *)&v651[1] = v656;
                              goto LABEL_115;
                            }
                            v118 = v679;
                            v661 = 0;
                            if ( v679 )
                            {
                              *(_DWORD *)v116 = v239;
                              v119 = GetProcessHeap();
                              v120 = v239;
                              v121 = HeapAlloc(v119, 8u, v239);
                              if ( !v121 )
                              {
LABEL_405:
                                v122 = -1073741801;
                                v12 = v665;
                                v64 = v660;
                                v9 = (void *)dwBytes;
                                *(_QWORD *)&v651[1] = v656;
                                v301 = v670;
                                v656 = (SIZE_T)v660;
                                v659 = v665;
                                v665 = (void *)dwBytes;
                                psz = (STRSAFE_PCNZWCH)*((_QWORD *)v670 + 1);
                                if ( psz )
                                {
                                  v302 = GetProcessHeap();
                                  HeapFree(v302, 0, (LPVOID)psz);
                                  v301 = v670;
                                  *((_QWORD *)v670 + 1) = 0;
                                }
                                psz = (STRSAFE_PCNZWCH)*((_QWORD *)v301 + 3);
                                if ( psz )
                                {
                                  v303 = GetProcessHeap();
                                  HeapFree(v303, 0, (LPVOID)psz);
                                  v301 = v670;
                                  *((_QWORD *)v670 + 3) = 0;
                                }
                                psz = (STRSAFE_PCNZWCH)*((_QWORD *)v301 + 5);
                                if ( psz )
                                {
                                  v304 = GetProcessHeap();
                                  HeapFree(v304, 0, (LPVOID)psz);
                                  *((_QWORD *)v670 + 5) = 0;
                                }
                                v305 = GetProcessHeap();
                                HeapFree(v305, 0, v670);
                                v132 = (STRSAFE_PCNZWCH *)v661;
LABEL_129:
                                if ( v122 >= 0 )
                                {
                                  v667 = v132;
                                }
                                else if ( v132 )
                                {
                                  psz = v132[1];
                                  if ( psz )
                                  {
                                    v306 = GetProcessHeap();
                                    HeapFree(v306, 0, (LPVOID)psz);
                                    v132 = (STRSAFE_PCNZWCH *)v661;
                                    *((_QWORD *)v661 + 1) = 0;
                                  }
                                  psz = v132[3];
                                  if ( psz )
                                  {
                                    v307 = GetProcessHeap();
                                    HeapFree(v307, 0, (LPVOID)psz);
                                    v132 = (STRSAFE_PCNZWCH *)v661;
                                    *((_QWORD *)v661 + 3) = 0;
                                  }
                                  psz = v132[5];
                                  if ( psz )
                                  {
                                    v308 = GetProcessHeap();
                                    HeapFree(v308, 0, (LPVOID)psz);
                                    *((_QWORD *)v661 + 5) = 0;
                                  }
                                  v309 = GetProcessHeap();
                                  HeapFree(v309, 0, v661);
                                }
                                v13 = v122 | 0x10000000;
                                v649 = v13;
                                if ( v13 < 0 )
                                  goto LABEL_55;
                                v133 = v667;
                                if ( !v667 || (dwBytes = *((_QWORD *)v667 + 1)) == 0 || !*(_DWORD *)v667 )
                                {
                                  v13 = -805306355;
                                  goto LABEL_115;
                                }
                                v661 = (LPVOID)(*(unsigned int *)v667 - 8LL);
                                v679 = MemoryAlloc((unsigned __int64)v661);
                                v134 = (wchar_t *)v679;
                                if ( !v679 )
                                  goto LABEL_146;
                                v135 = (unsigned __int64)v661;
                                v136 = 0;
                                v657 = 0;
                                v660 = (LPVOID)0x7F1137FAB69605ELL;
                                v670 = (LPVOID)dwBytes;
                                lpMem = v679;
                                v137 = (unsigned __int8)v661 & 7;
                                if ( ((unsigned __int8)v661 & 7) != 0 )
                                {
                                  LODWORD(v664) = 0;
                                  v605 = 0;
                                  v606 = (unsigned __int8 *)v670;
                                  v607 = 0;
                                  v608 = 0;
                                  do
                                  {
                                    v609 = *v606++;
                                    v652 = 8 * v605;
                                    if ( v605 >= 4 )
                                      v607 |= v609 << (56 - v652);
                                    else
                                      v608 |= v609 << (24 - v652);
                                    ++v605;
                                  }
                                  while ( (int)v605 < v137 );
                                  v650 = v608;
                                  v610 = v608;
                                  v136 = v657;
                                  LODWORD(v664) = v607;
                                  v6 = v677;
                                  v670 = v606;
                                  v667 = v133;
                                  v656 = (SIZE_T)v64;
                                  v659 = v12;
                                  v665 = v9;
                                  v138 = v610 ^ 0x92F65A5;
                                  v655 = 0;
                                  v611 = (unsigned int)v664 ^ 0x699A899C;
                                  v612 = v138;
                                  v652 = (unsigned int)v664 ^ 0x699A899C;
                                  if ( ((unsigned __int8)v661 & 7) != 0 )
                                  {
                                    v613 = v655;
                                    v614 = (char *)v679;
                                    do
                                    {
                                      psz = (STRSAFE_PCNZWCH)(v614 + 1);
                                      if ( v613 >= 4 )
                                      {
                                        v611 = __ROR4__(v611, 24);
                                        v615 = v611;
                                      }
                                      else
                                      {
                                        v612 = __ROR4__(v612, 24);
                                        v615 = v612;
                                      }
                                      *v614 = v615;
                                      ++v613;
                                      v614 = (char *)psz;
                                    }
                                    while ( (int)v613 < v137 );
                                    lpMem = (LPVOID)psz;
                                  }
                                  if ( (unsigned int)v137 <= 4 )
                                  {
                                    v652 = 0;
                                    if ( (unsigned int)v137 < 4 )
                                      v138 = v138 >> (8 * (4 - v137)) << (8 * (4 - v137));
                                    v137 = v652;
                                  }
                                  else
                                  {
                                    v137 = v652 >> (8 * (8 - v137)) << (8 * (8 - v137));
                                  }
                                }
                                else
                                {
                                  v650 = (unsigned __int8)v661 & 7;
                                  v138 = 0;
                                  LODWORD(v664) = -1;
                                }
                                v139 = v135 >> 3;
                                if ( v135 >> 3 )
                                {
                                  v140 = HIDWORD(v660);
                                  v141 = (unsigned __int8 *)v670;
                                  v142 = HIDWORD(v660) ^ 0xAB69605E;
                                  v143 = lpMem;
                                  v144 = v139;
                                  v145 = v650;
                                  v655 = WORD2(v660);
                                  v651[0] = 24670;
                                  v146 = (int)v664;
                                  Size = 0;
                                  v652 = HIDWORD(v660) ^ 0xAB69605E;
                                  do
                                  {
                                    v147 = *v141;
                                    v148 = v141[1];
                                    v149 = v141[4];
                                    v141 += 8;
                                    v150 = *(v141 - 5) | ((*(v141 - 6) | (((v147 << 8) | v148) << 8)) << 8);
                                    v151 = v138 ^ v150;
                                    v152 = *(v141 - 1) | ((*(v141 - 2) | ((*(v141 - 3) | (v149 << 8)) << 8)) << 8);
                                    v153 = v137 ^ v152 ^ v142 ^ v138 ^ v150;
                                    v154 = v151 ^ (__ROR4__(v153, 22) + v655 * __ROR4__(v153 + 1419157410, 27));
                                    v155 = v153 ^ (WORD1(v660) * __ROR4__(v154 + v140, 9) - __ROR4__(v154, 30));
                                    v156 = v154 ^ (v651[0] * (v155 - v655) - (v155 >> 13));
                                    v157 = v155 ^ (HIWORD(v660) * __ROR4__(WORD1(v660) ^ v156, 26) - __ROR4__(v156, 30));
                                    v158 = v156 ^ (v140 - (v157 ^ 0xAB69605E));
                                    v159 = v157 ^ (WORD1(v660) * (v655 ^ v158)) ^ __ROR4__(v158, 6);
                                    v160 = v158 ^ (__ROR4__(v159, 30) + v651[0] * __ROR4__(v159 + v140, 15));
                                    v161 = v159 ^ (HIWORD(v660) * __ROR4__(v160 + 1419157410, 14) - __ROR4__(v160, 24));
                                    v162 = v160 ^ __ROR4__(v161, 10) ^ (v655 * __ROR4__(v161 ^ 0xAB69605E, 12));
                                    v163 = v161 ^ (v162 >> 10) ^ (WORD1(v660) * (v162 ^ HIWORD(v660)));
                                    v142 = v652;
                                    v164 = v162 ^ (HIWORD(v660) * (v651[0] + __ROR4__(~v163, 5)));
                                    v140 = HIDWORD(v660);
                                    v165 = v163 ^ (v164 - HIWORD(v660)) ^ 0xAB69605E;
                                    v166 = v164 ^ ((v165 >> 2) + v655 * __ROR4__(v165 ^ HIWORD(v660), 30));
                                    v167 = v165 ^ (__ROR4__(v166, 25) + WORD1(v660) * __ROR4__(v166 - HIDWORD(v660), 6));
                                    v168 = v166 ^ (v651[0] * (v167 ^ v655) + __ROR4__(v167, 9));
                                    v169 = v167 ^ (__ROR4__(v168, 25) + HIWORD(v660) * __ROR4__(v168 ^ WORD1(v660), 27));
                                    v170 = v168 ^ v169 ^ v652;
                                    v171 = v169 ^ (v655 * (__ROR4__(v170, 3) - WORD1(v660)));
                                    v172 = v170 ^ (v651[0] * __ROR4__(v171 - HIDWORD(v660), 1) - __ROR4__(v171, 6));
                                    v173 = v171 ^ (__ROR4__(v172, 18) + HIWORD(v660) * __ROR4__(v172 - 1419157410, 29));
                                    v174 = v172 ^ (v655 * __ROR4__(v173 - 1419157410, 17) - __ROR4__(v173, 14));
                                    v175 = v173 ^ (v174 >> 3) ^ (WORD1(v660) * (v174 ^ v651[0]));
                                    v176 = v145 ^ __ROR4__(v175, 30) ^ (v651[0] * __ROR4__(v175 ^ HIDWORD(v660), 28));
                                    v145 = v150;
                                    v138 = v174 ^ v176;
                                    v143[3] = v138;
                                    v137 = v175 ^ v146;
                                    v143[7] = v175 ^ v146;
                                    v146 = v152;
                                    v143[2] = __ROR4__(v138, 8);
                                    v143[6] = __ROR4__(v137, 8);
                                    v143[1] = __ROR4__(v138, 16);
                                    v143[5] = __ROR4__(v137, 16);
                                    *v143 = __ROR4__(v138, 24);
                                    v143[4] = __ROR4__(v137, 24);
                                    v143 += 8;
                                    ++Size;
                                  }
                                  while ( Size < v144 );
                                  v136 = v657;
                                  v6 = v677;
                                  v9 = v665;
                                  v12 = v659;
                                  v64 = (_DWORD *)v656;
                                  v134 = (wchar_t *)v679;
                                  v135 = (unsigned __int64)v661;
                                }
                                for ( mm = 0; mm < v135; ++mm )
                                  v136 ^= *((_BYTE *)v134 + mm);
                                if ( v136 != *(_QWORD *)(v135 + dwBytes) )
                                {
                                  MemoryFree(v134);
LABEL_146:
                                  v13 = -805306367;
                                  v666 = 0;
                                  goto LABEL_115;
                                }
                                v249 = *(_QWORD *)&v651[1];
                                v250 = v663;
                                v251 = v667;
                                v666 = v134;
                                if ( (unsigned int)v135 < 4 )
                                  goto LABEL_257;
                                psz = v134 + 2;
                                if ( v134 + 2 < v134 )
                                  goto LABEL_286;
                                if ( (unsigned int)(v135 - 4) >= 4 )
                                {
                                  v205 = (unsigned __int64)(v134 + 4);
                                  if ( v134 + 4 < v134 + 2 )
                                    goto LABEL_286;
                                  v651[0] = *((_DWORD *)v134 + 1);
                                  if ( (unsigned int)(v135 - 8) >= v651[0] )
                                  {
                                    if ( v651[0] < 0xFFFFFFF8 )
                                    {
                                      v659 = (void *)(v205 + v651[0]);
                                      if ( (char *)v134 + (unsigned int)v135 >= v659
                                        && (unsigned int)v135 - (unsigned __int64)v651[0] - 8 < 8 )
                                      {
                                        v652 = 0;
                                        if ( v134 != (wchar_t *)-8LL )
                                        {
                                          v224 = v659;
                                          if ( (unsigned __int64)v659 < v205 )
                                          {
LABEL_211:
                                            LODWORD(v205) = -1073741675;
                                          }
                                          else
                                          {
                                            v666 = v134;
                                            while ( 1 )
                                            {
                                              v221 = (_DWORD *)v205;
                                              LODWORD(v205) = 0;
                                              if ( v221 >= v224 )
                                                break;
                                              if ( v221 + 1 < v221 )
                                                goto LABEL_211;
                                              if ( v221 + 1 > v224 )
                                                goto LABEL_764;
                                              if ( *v221 >= 0xFFFFFFFC )
                                                goto LABEL_211;
                                              v205 = (unsigned __int64)v221 + (unsigned int)(*v221 + 4);
                                              if ( v205 < (unsigned __int64)v221 )
                                                goto LABEL_211;
                                              v224 = v659;
                                              *(_QWORD *)&v651[1] = v249;
                                              v663 = v250;
                                              v667 = v251;
                                              v666 = v134;
                                              if ( v205 > (unsigned __int64)v659 )
                                              {
                                                LODWORD(v205) = -1073741811;
                                                v666 = v134;
                                                goto LABEL_288;
                                              }
                                              ++v652;
                                            }
                                            if ( v221 == v224 )
                                              goto LABEL_251;
LABEL_764:
                                            LODWORD(v205) = -1073741811;
                                          }
                                          goto LABEL_212;
                                        }
                                        v666 = (LPVOID)-8LL;
LABEL_251:
                                        v655 = *(_DWORD *)v134;
                                        v222 = 0;
                                        lpMem = 0;
                                        if ( v651[0] )
                                        {
                                          v223 = GetProcessHeap();
                                          v222 = HeapAlloc(v223, 8u, v651[0]);
                                          lpMem = v222;
                                          if ( !v222 )
                                          {
                                            LODWORD(v205) = -1073741801;
                                            goto LABEL_212;
                                          }
                                          LODWORD(v205) = 0;
                                        }
                                        if ( psz != (STRSAFE_PCNZWCH)-4LL )
                                          memcpy_0(v222, psz + 2, v651[0]);
                                        v668 = lpMem;
                                        v653 = v652;
                                        if ( v655 == v652 )
                                          goto LABEL_212;
LABEL_257:
                                        LODWORD(v205) = -1073741762;
LABEL_212:
                                        v13 = v205 | 0x10000000;
                                        goto LABEL_115;
                                      }
                                      goto LABEL_762;
                                    }
LABEL_286:
                                    LODWORD(v205) = -1073741675;
                                    goto LABEL_287;
                                  }
                                }
LABEL_762:
                                LODWORD(v205) = -1073741762;
LABEL_287:
                                v666 = v134;
LABEL_288:
                                v667 = v251;
                                v663 = v250;
                                *(_QWORD *)&v651[1] = v249;
                                goto LABEL_212;
                              }
                              v117[1] = v121;
                              v122 = 0;
                              memcpy_0(v121, v118, v120);
                            }
                            else
                            {
                              *(_DWORD *)v116 = 0;
                              v122 = 0;
                              v116[1] = 0;
                            }
                            v123 = (char *)lpMem + 4;
                            if ( lpMem == (LPVOID)-4LL )
                            {
                              *((_DWORD *)v117 + 4) = 0;
                              v117[3] = 0;
                            }
                            else
                            {
                              *((_DWORD *)v117 + 4) = v652;
                              v124 = GetProcessHeap();
                              v125 = Size;
                              v126 = HeapAlloc(v124, 8u, Size);
                              if ( !v126 )
                              {
LABEL_741:
                                v670 = v117;
                                goto LABEL_405;
                              }
                              v117[3] = v126;
                              v122 = 0;
                              memcpy_0(v126, v123, v125);
                            }
                            v127 = v659;
                            if ( !v659 )
                            {
                              *((_DWORD *)v117 + 8) = 0;
                              v117[5] = 0;
                              goto LABEL_128;
                            }
                            v128 = v655;
                            *((_DWORD *)v117 + 8) = v655;
                            v129 = v128;
                            v130 = GetProcessHeap();
                            v131 = HeapAlloc(v130, 8u, v129);
                            if ( v131 )
                            {
                              v117[5] = v131;
                              v122 = 0;
                              memcpy_0(v131, v127, v129);
LABEL_128:
                              v132 = (STRSAFE_PCNZWCH *)v117;
                              v12 = v665;
                              v64 = v660;
                              v9 = (void *)dwBytes;
                              *(_QWORD *)&v651[1] = v656;
                              v661 = v132;
                              v656 = (SIZE_T)v660;
                              v659 = v665;
                              v665 = (void *)dwBytes;
                              goto LABEL_129;
                            }
                            goto LABEL_741;
                          }
                        }
                        goto LABEL_147;
                      }
                    }
                  }
LABEL_149:
                  v178 = *(_QWORD *)&v651[1];
                  v13 = -805306219;
                  goto LABEL_150;
                }
                goto LABEL_403;
              }
            }
LABEL_94:
            *(_QWORD *)&v651[1] = v100;
            v64 = (_DWORD *)v656;
            v106 = GetProcessHeap();
            HeapFree(v106, 0, v661);
            goto LABEL_75;
          }
        }
      }
    }
    v87 = -1073741675;
    goto LABEL_94;
  }
LABEL_55:
  if ( v64 )
  {
LABEL_766:
    v616 = GetProcessHeap();
    HeapFree(v616, 0, v64);
  }
  v79 = *(STRSAFE_PCNZWCH **)&v651[1];
  if ( *(_QWORD *)&v651[1] )
  {
    psz = *(STRSAFE_PCNZWCH *)(*(_QWORD *)&v651[1] + 8LL);
    if ( psz )
    {
      v113 = GetProcessHeap();
      HeapFree(v113, 0, (LPVOID)psz);
      *(_QWORD *)(*(_QWORD *)&v651[1] + 8LL) = 0;
    }
    psz = v79[3];
    if ( psz )
    {
      v107 = GetProcessHeap();
      HeapFree(v107, 0, (LPVOID)psz);
      v79[3] = 0;
    }
    psz = v79[5];
    if ( psz )
    {
      v108 = GetProcessHeap();
      HeapFree(v108, 0, (LPVOID)psz);
      v79[5] = 0;
    }
    v109 = GetProcessHeap();
    HeapFree(v109, 0, v79);
  }
  v80 = v681;
  if ( v681 )
  {
    v617 = GetProcessHeap();
    HeapFree(v617, 0, v80);
  }
  v81 = v663;
  if ( v663 )
  {
    v618 = GetProcessHeap();
    HeapFree(v618, 0, v81);
  }
  v82 = v667;
  if ( v667 )
  {
    psz = (STRSAFE_PCNZWCH)*((_QWORD *)v667 + 1);
    if ( psz )
    {
      v114 = GetProcessHeap();
      HeapFree(v114, 0, (LPVOID)psz);
      *((_QWORD *)v82 + 1) = 0;
    }
    psz = (STRSAFE_PCNZWCH)*((_QWORD *)v82 + 3);
    if ( psz )
    {
      v110 = GetProcessHeap();
      HeapFree(v110, 0, (LPVOID)psz);
      *((_QWORD *)v82 + 3) = 0;
    }
    psz = (STRSAFE_PCNZWCH)*((_QWORD *)v82 + 5);
    if ( psz )
    {
      v111 = GetProcessHeap();
      HeapFree(v111, 0, (LPVOID)psz);
      *((_QWORD *)v82 + 5) = 0;
    }
    v112 = GetProcessHeap();
    HeapFree(v112, 0, v82);
  }
  v83 = v666;
  if ( v666 )
  {
    v84 = GetProcessHeap();
    HeapFree(v84, 0, v83);
  }
LABEL_64:
  if ( v13 < 0 )
    goto LABEL_11;
  if ( !v653 )
    goto LABEL_767;
  if ( !v668 )
    goto LABEL_774;
  if ( (char *)v668 + 4 < v668 )
  {
LABEL_111:
    v13 = -1073741675;
    goto LABEL_10;
  }
  v85 = 0;
  if ( *(_DWORD *)v668 )
    v85 = (int *)((char *)v668 + 4);
  if ( *(_DWORD *)v668 != 4 )
    goto LABEL_782;
  v13 = *v85;
  v649 = v13;
  if ( v13 == -805306333 )
  {
    v651[0] = -2147024774;
LABEL_770:
    if ( v653 != 6 )
      goto LABEL_767;
    v312 = (unsigned int *)v668;
    v313 = 0;
    v659 = v668;
    while ( !v313 )
    {
      v310 = *v312;
      v649 = RtlULongLongAdd(v312, 4, &v659);
      v13 = v649;
      if ( v649 < 0 )
        goto LABEL_179;
      v649 = RtlULongLongAdd(v659, v310, &v659);
      v13 = v649;
      if ( v649 < 0 )
        goto LABEL_179;
      v312 = (unsigned int *)v659;
      v313 = v311 + 1;
    }
    v649 = RtlULongLongAdd(v312, 4, &v659);
    v13 = v649;
    if ( v649 >= 0 )
    {
      v317 = (const wchar_t **)v659;
      if ( !v316 )
        v317 = 0;
      if ( v316 != 8 )
        goto LABEL_427;
      v651[0] = v315;
      v668 = v314;
      if ( !v314 )
        goto LABEL_167;
      v318 = *v317;
      v319 = (unsigned int *)v314;
      v659 = v314;
      v320 = 0;
      psz = v318;
      while ( v320 < 2 )
      {
        v321 = *v319;
        v649 = RtlULongLongAdd(v319, 4, &v659);
        v13 = v649;
        if ( v649 < 0 )
          goto LABEL_179;
        v649 = RtlULongLongAdd(v659, v321, &v659);
        v13 = v649;
        if ( v649 < 0 )
          goto LABEL_179;
        v319 = (unsigned int *)v659;
        v320 = v322 + 1;
      }
      v649 = RtlULongLongAdd(v319, 4, &v659);
      v13 = v649;
      if ( v649 >= 0 )
      {
        v326 = (unsigned int *)v659;
        if ( !v325 )
          v326 = 0;
        if ( v325 != 4 )
          goto LABEL_427;
        v651[0] = v324;
        v668 = v323;
        if ( !v323 )
          goto LABEL_167;
        v327 = *v326;
        v328 = v323;
        v659 = v323;
        v652 = v327;
        while ( 1 )
        {
          v329 = *v328;
          v330 = RtlULongLongAdd(v328, 4, &v659);
          v649 = v330;
          v13 = v330;
          if ( v332 >= 3 )
            break;
          if ( v330 < 0 )
            goto LABEL_179;
          v649 = RtlULongLongAdd(v659, v329, &v659);
          v13 = v649;
          if ( v649 < 0 )
            goto LABEL_179;
          v328 = (unsigned int *)v659;
        }
        if ( v330 >= 0 )
        {
          lpMem = (_DWORD)v329 ? v659 : 0LL;
          v334 = v331;
          v335 = 0;
          v659 = v331;
          while ( v335 < 4 )
          {
            v653 = *v334;
            v649 = RtlULongLongAdd(v334, 4, &v659);
            v13 = v649;
            if ( v649 < 0 )
              goto LABEL_179;
            v649 = RtlULongLongAdd(v659, v653, &v659);
            v13 = v649;
            if ( v649 < 0 )
              goto LABEL_179;
            v334 = (unsigned int *)v659;
            v335 = v333 + 1;
          }
          v649 = RtlULongLongAdd(v334, 4, &v659);
          v13 = v649;
          if ( v649 >= 0 )
          {
            v339 = (unsigned int *)v659;
            if ( !v338 )
              v339 = 0;
            if ( v338 == 4 )
            {
              v668 = v336;
              if ( v336 )
              {
                v340 = *v339;
                v341 = 0;
                v342 = v336;
                v651[0] = v337;
                v659 = v336;
                v653 = v340;
                v343 = 4;
                while ( v341 < 5 )
                {
                  v649 = RtlULongLongAdd(v342, v343, &v659);
                  v13 = v649;
                  if ( v649 < 0 )
                    goto LABEL_11;
                  v649 = RtlULongLongAdd(v659, v344, &v659);
                  v13 = v649;
                  if ( v649 < 0 )
                    goto LABEL_11;
                  v342 = v659;
                  v341 = v345 + 1;
                }
                v195 = RtlULongLongAdd(v342, v343, &v659);
                v649 = v195;
                v13 = v195;
                if ( v195 < 0 )
                {
LABEL_208:
                  v649 = v195;
                  goto LABEL_11;
                }
                v619 = (int *)v659;
                if ( !v203 )
                  v619 = 0;
                if ( v203 == v204 )
                {
                  if ( (STRSAFE_PCNZWCH)v674 == psz )
                  {
                    v620 = *v619;
                    v686 = v652;
                    v684 = v620;
                    if ( v653 <= v204 && (unsigned int)v329 <= v204 )
                    {
                      memcpy_0(v6, lpMem, v329);
LABEL_180:
                      v195 = v651[0];
                      if ( !v651[0] )
                        goto LABEL_11;
                      v13 = v651[0];
                      goto LABEL_208;
                    }
                    v13 = -2147024774;
LABEL_10:
                    v649 = v13;
                    goto LABEL_11;
                  }
LABEL_767:
                  v13 = -1073425151;
                  goto LABEL_10;
                }
LABEL_782:
                v13 = -1073741789;
                goto LABEL_10;
              }
LABEL_774:
              v13 = -1073741811;
              goto LABEL_10;
            }
LABEL_427:
            v13 = -1073741789;
            goto LABEL_163;
          }
        }
      }
    }
LABEL_179:
    if ( v13 < 0 )
      goto LABEL_11;
    goto LABEL_180;
  }
  v651[0] = v13;
  if ( v13 == -2147024774 || v13 >= 0 )
    goto LABEL_770;
LABEL_11:
  v15 = Src[1];
  Src[0] = 0;
  if ( Src[1] )
  {
    v16 = GetProcessHeap();
    HeapFree(v16, 0, v15);
    Src[1] = 0;
  }
  v17 = v668;
  if ( v668 )
  {
    v18 = GetProcessHeap();
    HeapFree(v18, 0, v17);
  }
  if ( v9 )
  {
    v20 = GetProcessHeap();
    HeapFree(v20, 0, v9);
  }
  if ( v12 )
  {
    v22 = GetProcessHeap();
    HeapFree(v22, 0, v12);
  }
  if ( v13 < 0 )
  {
    LocalFree(v6);
    v4 = (DWORD *)hMem;
    goto LABEL_21;
  }
  if ( !v684 )
    goto LABEL_25;
  v346 = 0;
  dwBytes = 0;
  *(_OWORD *)v673 = 0;
  v347 = GetProcessHeap();
  v348 = HeapAlloc(v347, 8u, 0xA0u);
  v349 = v348;
  if ( !v348 )
  {
    v349 = 0;
    goto LABEL_321;
  }
  *v348 = `WarbirdUmGetDecryptionCipher'::`2'::DecryptionCipher;
  v348[1] = xmmword_1800E5580;
  v348[2] = xmmword_1800E5590;
  v348[3] = xmmword_1800E55A0;
  v348[4] = xmmword_1800E55B0;
  v348[5] = xmmword_1800E55C0;
  v348[6] = xmmword_1800E55D0;
  v348[7] = xmmword_1800E55E0;
  v348[8] = xmmword_1800E55F0;
  v348[9] = xmmword_1800E5600;
  v350 = GetProcessHeap();
  psz = (STRSAFE_PCNZWCH)HeapAlloc(v350, 8u, 8u);
  if ( !psz )
    goto LABEL_321;
  v346 = (void *)psz;
  *(_QWORD *)psz = `WarbirdUmGetDecryptionKey'::`2'::nDecryptionKey;
  psz = (STRSAFE_PCNZWCH)__rdtsc();
  v651[0] = 0;
  v653 = 0;
  if ( (int)RtlUIntAdd(4, 4, &v653) < 0 )
    goto LABEL_321;
  if ( (int)RtlUIntAdd(0, v653, v651) < 0 )
    goto LABEL_321;
  v653 = v351;
  if ( (int)RtlUIntAdd(v352, 160, &v653) < 0 )
    goto LABEL_321;
  v353 = RtlUIntAdd(v651[0], v653, v651);
  if ( (v355 | v353) < 0 )
    goto LABEL_321;
  v653 = 0;
  if ( (int)RtlUIntAdd(v354, 8, &v653) < 0 )
    goto LABEL_321;
  v356 = RtlUIntAdd(v651[0], v653, v651);
  if ( (v358 | v356) < 0 )
    goto LABEL_321;
  v653 = 0;
  if ( (int)RtlUIntAdd(v357, 8, &v653) < 0 )
    goto LABEL_321;
  v359 = RtlUIntAdd(v651[0], v653, v651);
  if ( (v360 | v359) < 0 )
    goto LABEL_321;
  HIDWORD(v673[0]) = v651[0];
  v361 = v651[0];
  v362 = GetProcessHeap();
  v363 = HeapAlloc(v362, 8u, v361);
  v364 = v363;
  if ( !v363 )
    goto LABEL_321;
  v673[1] = (size_t)v363;
  LODWORD(v673[0]) = 0;
  LODWORD(v672) = 0;
  v671 = 0;
  v674 = (SIZE_T)v363;
  v652 = 8;
  if ( (int)RtlULongLongAdd(v363, 4, &v672) < 0 || (unsigned __int64)(v364 + 2) > v673[1] + HIDWORD(v673[0]) )
    goto LABEL_321;
  v366 = v672;
  *v364 = 4;
  v367 = v652;
  *v366 = 4;
  v368 = 0;
  v369 = LODWORD(v673[0]) + 1;
  LODWORD(v672) = 0;
  ++LODWORD(v673[0]);
  v671 = 0;
  if ( v349 )
  {
    if ( !v365 )
      goto LABEL_321;
  }
  else if ( v365 )
  {
    goto LABEL_321;
  }
  v370 = (unsigned int *)v673[1];
  if ( v673[1] )
  {
    v674 = v673[1];
    while ( 1 )
    {
      v652 = v368;
      if ( v368 >= v369 )
        break;
      v444 = *v370;
      v653 = 0;
      if ( (int)RtlUIntAdd(4, v444, &v653) < 0 || (int)RtlULongLongAdd(v445, v653, &v674) < 0 )
        goto LABEL_321;
      v370 = (unsigned int *)v674;
      v368 = v652 + 1;
    }
    if ( (int)RtlULongLongAdd(v370, 4, &v672) < 0 || (unsigned __int64)v371 + v372 + 4 > v673[1] + HIDWORD(v673[0]) )
      goto LABEL_321;
    *v371 = v372;
    if ( v349 )
      memcpy_0(v672, v349, v372);
    v373 = 4;
  }
  else
  {
    v653 = 0;
    if ( (int)RtlUIntAdd(4, v365, &v653) < 0 || (int)RtlUIntAdd(HIDWORD(v673[0]), v653, (char *)v673 + 4) < 0 )
      goto LABEL_321;
  }
  v374 = LODWORD(v673[0]) + 1;
  LODWORD(v672) = 0;
  ++LODWORD(v673[0]);
  v671 = 0;
  if ( v367 )
  {
    v375 = (unsigned int *)v673[1];
    if ( v673[1] )
    {
      v674 = v673[1];
      for ( nn = 0; nn < v374; nn = v448 + 1 )
      {
        v446 = *v375;
        v653 = 0;
        if ( (int)RtlUIntAdd(4, v446, &v653) < 0 || (int)RtlULongLongAdd(v447, v653, &v674) < 0 )
          goto LABEL_321;
        v375 = (unsigned int *)v674;
      }
      if ( (int)RtlULongLongAdd(v375, 4, &v672) < 0 || (unsigned __int64)v377 + v367 + 4 > v673[1] + HIDWORD(v673[0]) )
        goto LABEL_321;
      *v377 = v367;
      memcpy_0(v672, v346, v367);
      v621 = 4;
    }
    else
    {
      v653 = 0;
      if ( (int)RtlUIntAdd(v373, v367, &v653) < 0 || (int)RtlUIntAdd(HIDWORD(v673[0]), v653, (char *)v673 + 4) < 0 )
        goto LABEL_321;
    }
    v378 = (unsigned int *)v673[1];
    v379 = LODWORD(v673[0]) + 1;
    LODWORD(v672) = 0;
    ++LODWORD(v673[0]);
    v671 = 0;
    if ( v673[1] )
    {
      v674 = v673[1];
      for ( i1 = 0; i1 < v379; i1 = v451 + 1 )
      {
        v449 = *v378;
        v653 = 0;
        if ( (int)RtlUIntAdd(4, v449, &v653) < 0 || (int)RtlULongLongAdd(v450, v653, &v674) < 0 )
          goto LABEL_321;
        v378 = (unsigned int *)v674;
      }
      if ( (int)RtlULongLongAdd(v378, 4, &v672) < 0 || (unsigned __int64)(v381 + 3) > v673[1] + HIDWORD(v673[0]) )
        goto LABEL_321;
      v383 = (STRSAFE_PCNZWCH *)v672;
      v384 = psz;
      *v381 = 8;
      *v383 = v384;
    }
    else
    {
      v653 = 0;
      if ( (int)RtlUIntAdd(v621, 8, &v653) < 0 || (int)RtlUIntAdd(HIDWORD(v673[0]), v653, (char *)v673 + 4) < 0 )
        goto LABEL_321;
    }
    ++LODWORD(v673[0]);
    v653 = 0;
    if ( (int)RtlUIntAdd(v382, v382, &v653) >= 0 )
    {
      v655 = v653;
      v653 = 0;
      if ( (int)RtlUIntAdd(v385, 8, &v653) >= 0 && (int)RtlUIntAdd(v386, v653, &v655) >= 0 )
      {
        *(_QWORD *)&v651[1] = 0;
        v652 = 0;
        LODWORD(v664) = v655;
        psz = (STRSAFE_PCNZWCH)__rdtsc();
        v680 = 8;
        v387 = RtlUIntAdd(8, HIDWORD(v673[0]), &v680);
        if ( v387 < 0 )
        {
          v661 = v346;
          v668 = v349;
        }
        else
        {
          v390 = (v680 + 7) & 0xFFFFFFF8;
          if ( v390 < v680 )
            goto LABEL_321;
          v680 = (v680 + 7) & 0xFFFFFFF8;
          v391 = v390;
          v392 = GetProcessHeap();
          v393 = (char *)HeapAlloc(v392, 8u, v391);
          v394 = v393;
          if ( !v393 )
            goto LABEL_643;
          v659 = v393;
          v668 = v349;
          v661 = v346;
          *(_DWORD *)v393 = v673[0];
          v655 = RtlULongLongAdd(v393, 4, &v659);
          if ( (v655 & 0x80000000) != 0
            || (v397 = v659,
                *(_DWORD *)v659 = HIDWORD(v673[0]),
                v655 = RtlULongLongAdd(v397, v396, &v659),
                (v655 & 0x80000000) != 0) )
          {
            v668 = v349;
            v661 = v346;
            LODWORD(v664) = v395;
            v452 = GetProcessHeap();
            HeapFree(v452, 0, v394);
            v388 = *(char **)&v651[1];
            v387 = v655;
            v389 = v651[1];
          }
          else
          {
            *(_QWORD *)&v394[v680 - 8] = psz;
            memcpy_0(v659, (const void *)v673[1], HIDWORD(v673[0]));
            v389 = v680;
            v388 = v394;
            v387 = v655;
            *(_QWORD *)&v651[1] = v394;
          }
        }
        v398 = 0;
        v666 = 0;
        v660 = 0;
        v270 = 0;
        lpMem = 0;
        v399 = v387 | 0x10000000;
        v667 = 0;
        v665 = 0;
        if ( v399 < 0 )
        {
          v654 = v399;
          goto LABEL_664;
        }
        if ( !v388 )
          goto LABEL_321;
        v679 = (void *)v389;
        if ( !v389 || (psz = (STRSAFE_PCNZWCH)(v389 + 8LL), (Size = (SIZE_T)MemoryAlloc((unsigned __int64)psz)) == 0) )
        {
          v549 = *(void **)&v651[1];
          v548 = 0;
          v654 = -805306367;
          goto LABEL_854;
        }
        v400 = (unsigned __int64)v679;
        v401 = 0;
        v402 = 0;
        v670 = 0;
        v657 = 0;
        if ( v679 )
        {
          do
            v401 ^= *(_BYTE *)(*(_QWORD *)&v651[1] + v402++);
          while ( v402 < (unsigned __int64)v679 );
          v657 = v401;
        }
        v656 = 0xC81ECB17B1B54A58uLL;
        v681 = *(LPVOID *)&v651[1];
        v659 = (void *)Size;
        v403 = (unsigned __int8)v679 & 7;
        if ( ((unsigned __int8)v679 & 7) != 0 )
        {
          v622 = 0;
          v655 = 0;
          v654 = 0;
          v623 = *(unsigned __int8 **)&v651[1];
          v624 = 0;
          v625 = 0;
          do
          {
            v626 = *v623++;
            v653 = 8 * v622;
            if ( v622 >= 4 )
              v624 |= v626 << (56 - v653);
            else
              v625 |= v626 << (24 - v653);
            ++v622;
          }
          while ( (int)v622 < v403 );
          v654 = v625;
          v627 = v625;
          v6 = v677;
          v655 = v624;
          v681 = v623;
          v661 = v346;
          v668 = v349;
          v651[0] = 0;
          v628 = v624 ^ 0x42F6B18D;
          v404 = v627 ^ 0xB17A307A;
          v629 = v404;
          v630 = v624 ^ 0x42F6B18D;
          if ( ((unsigned __int8)v679 & 7) != 0 )
          {
            v631 = v659;
            do
            {
              v674 = (SIZE_T)(v631 + 1);
              if ( v651[0] >= 4u )
              {
                v630 = __ROR4__(v630, 24);
                v632 = v630;
              }
              else
              {
                v629 = __ROR4__(v629, 24);
                v632 = v629;
              }
              *v631 = v632;
              ++v651[0];
              v631 = (_BYTE *)v674;
            }
            while ( v651[0] < v403 );
            v659 = (void *)v674;
          }
          if ( (unsigned int)v403 <= 4 )
          {
            v405 = 0;
            if ( (unsigned int)v403 < 4 )
              v404 = v404 >> (8 * (4 - v403)) << (8 * (4 - v403));
          }
          else
          {
            v405 = v628 >> (8 * (8 - v403)) << (8 * (8 - v403));
          }
        }
        else
        {
          v404 = 0;
          v405 = -1;
          v654 = 0;
          v655 = 0;
        }
        if ( v400 >> 3 )
        {
          v406 = v400 >> 3;
          v407 = (unsigned __int8 *)v681;
          v408 = v659;
          v409 = v654;
          LODWORD(v663) = WORD1(v656);
          v410 = 19032;
          v653 = HIDWORD(v656) ^ 0xB1B54A58;
          v411 = v655;
          v412 = HIDWORD(v656) ^ 0xB1B54A58;
          v674 = 0;
          v651[0] = 19032;
          do
          {
            v413 = *v407;
            v414 = v407[1];
            v415 = v407[4];
            v407 += 8;
            v416 = *(v407 - 5) | ((*(v407 - 6) | (((v413 << 8) | v414) << 8)) << 8);
            v417 = *(v407 - 1) | ((*(v407 - 2) | ((*(v407 - 3) | (v415 << 8)) << 8)) << 8);
            v418 = v405 ^ v417;
            v419 = v404 ^ v416 ^ ((v405 ^ v417) - v410);
            v420 = __ROR4__(v419, 15);
            v421 = HIDWORD(v656) ^ v419;
            v422 = v418 ^ (__ROR4__(v421, 7) + WORD1(v656) * v420);
            v423 = v421 ^ (WORD2(v656) * __ROR4__(v422 - 1313519016, 9) - __ROR4__(v422, 10));
            v424 = v422 ^ (__ROR4__(v423, 27) + HIWORD(v656) * __ROR4__(WORD2(v656) ^ v423, 28));
            v425 = v423 ^ (HIDWORD(v656) - (v424 ^ 0xB1B54A58));
            v426 = v424 ^ (WORD1(v656) * (v425 - v651[0]) - (v425 >> 6));
            v427 = v425 ^ (v651[0] * (WORD2(v656) ^ __ROR4__(v426, 15)));
            v428 = v426 ^ (WORD2(v656) * (HIWORD(v656) + __ROR4__(~v427, 3)));
            v429 = v427 ^ (v428 - v651[0] - HIDWORD(v656));
            v430 = v428 ^ ((_DWORD)v663 * (v429 ^ HIWORD(v656))) ^ __ROR4__(v429, 10);
            v431 = v429 ^ __ROR4__(v430, 3) ^ (WORD2(v656) * __ROR4__(v430 ^ v651[0], 26));
            v432 = v430 ^ (v651[0] * (__ROR4__(v431, 15) - HIWORD(v656)));
            v433 = v431
                 ^ (v651[0] * (v432 ^ HIWORD(v656)))
                 ^ ((v432 ^ (v432 >> 14)) >> 1)
                 ^ (v651[0] * ((8 * (v432 - WORD2(v656))) | ((v432 - WORD2(v656)) >> 29)));
            v434 = v432 ^ (WORD1(v656) * (v433 - WORD2(v656)) - (v433 >> 13));
            v435 = v433 ^ __ROR4__(v434, 11) ^ (WORD2(v656) * __ROR4__(-1313519016 - v434, 9));
            v436 = v434 ^ (v435 - HIWORD(v656) + 1313519016);
            v437 = v435 ^ (v651[0] * (v436 ^ WORD1(v656)) - __ROR4__(v436, 7));
            v438 = v436 ^ (WORD1(v656) * __ROR4__(v437 ^ HIWORD(v656), 28) - __ROR4__(v437, 16));
            v439 = v437 ^ (__ROR4__(v438, 4) + WORD2(v656) * __ROR4__(-1313519016 - v438, 10));
            v440 = v438 ^ __ROR4__(v439, 9) ^ (HIWORD(v656) * __ROR4__(v439 + 1313519016, 4));
            v441 = v439 ^ (v651[0] * __ROR4__(HIDWORD(v656) ^ v440, 24) - __ROR4__(v440, 30));
            v442 = v440 ^ (WORD1(v656) * __ROR4__(HIDWORD(v656) - v441, 11) - __ROR4__(v441, 12));
            v443 = v441 ^ (v442 >> 8) ^ (WORD2(v656) * (v442 ^ WORD1(v656)));
            v404 = v409 ^ v443;
            v408[3] = v409 ^ v443;
            v405 = v442 ^ v411 ^ v443 ^ v412;
            v410 = v651[0];
            v409 = v416;
            v408[7] = v405;
            v411 = v417;
            v408[2] = __ROR4__(v404, 8);
            v408[6] = __ROR4__(v405, 8);
            v408[1] = __ROR4__(v404, 16);
            v408[5] = __ROR4__(v405, 16);
            *v408 = __ROR4__(v404, 24);
            v408[4] = __ROR4__(v405, 24);
            v408 += 8;
            ++v674;
          }
          while ( v674 < v406 );
          v401 = v657;
          v6 = v677;
          v13 = v649;
          v349 = v668;
          v346 = v661;
          v270 = v667;
          v400 = (unsigned __int64)v679;
        }
        *(_QWORD *)(Size + v400) = v401;
        v272 = GetProcessHeap();
        v273 = HeapAlloc(v272, 8u, 0x30u);
        v661 = v273;
        if ( v273 )
        {
          v274 = (unsigned int)psz;
          *v273 = (_DWORD)psz;
          v275 = GetProcessHeap();
          v276 = HeapAlloc(v275, 8u, v274);
          v277 = *(_QWORD *)&v651[1];
          v278 = v276;
          v279 = v276 == 0;
          v280 = (int)v664;
          if ( !v279 )
          {
            *((_QWORD *)v661 + 1) = v278;
            memcpy_0(v278, (const void *)Size, (unsigned int)psz);
            *((_DWORD *)v661 + 4) = 160;
            v281 = GetProcessHeap();
            v282 = HeapAlloc(v281, 8u, 0xA0u);
            v283 = v661;
            if ( v282 )
            {
              *((_QWORD *)v661 + 3) = v282;
              *v282 = `WarbirdUmGetEncryptionCipher'::`2'::EncryptionCipher;
              v282[1] = xmmword_1800E54D0;
              v282[2] = xmmword_1800E54E0;
              v282[3] = xmmword_1800E54F0;
              v282[4] = xmmword_1800E5500;
              v282[5] = xmmword_1800E5510;
              v282[6] = xmmword_1800E5520;
              v282[7] = xmmword_1800E5530;
              v282[8] = xmmword_1800E5540;
              v282[9] = xmmword_1800E5550;
              v283[8] = 8;
              v284 = GetProcessHeap();
              v285 = HeapAlloc(v284, 8u, 8u);
              if ( v285 )
              {
                v286 = v661;
                *((_QWORD *)v661 + 5) = v285;
                *v285 = `WarbirdUmGetEncryptionKey'::`2'::nEncryptionKey;
                v670 = v286;
                v651[0] = 0;
                *(_QWORD *)&v651[1] = v277;
LABEL_362:
                v287 = (unsigned int *)v670;
                v670 = 0;
                goto LABEL_363;
              }
              v283 = v661;
            }
            v661 = v283;
            v280 = (int)v664;
          }
          LODWORD(v664) = v280;
          *(_QWORD *)&v651[1] = v277;
          v453 = v661;
          v651[0] = -1073741801;
          v671 = (LPVOID)*((_QWORD *)v661 + 1);
          if ( v671 )
          {
            v454 = GetProcessHeap();
            HeapFree(v454, 0, v671);
            v453[1] = 0;
          }
          v671 = (LPVOID)v453[3];
          if ( v671 )
          {
            v455 = GetProcessHeap();
            HeapFree(v455, 0, v671);
            v453[3] = 0;
          }
          v671 = (LPVOID)v453[5];
          if ( v671 )
          {
            v456 = GetProcessHeap();
            HeapFree(v456, 0, v671);
            v453[5] = 0;
          }
          v457 = GetProcessHeap();
          HeapFree(v457, 0, v453);
          if ( v651[0] >= 0 )
            goto LABEL_362;
        }
        else
        {
          v651[0] = -1073741801;
        }
        v287 = (unsigned int *)v666;
LABEL_363:
        v666 = v287;
        v288 = GetProcessHeap();
        HeapFree(v288, 0, (LPVOID)Size);
        v289 = v670;
        if ( v670 )
        {
          v671 = (LPVOID)*((_QWORD *)v670 + 1);
          if ( v671 )
          {
            v458 = GetProcessHeap();
            HeapFree(v458, 0, v671);
            v289 = v670;
            *((_QWORD *)v670 + 1) = 0;
          }
          v671 = (LPVOID)v289[3];
          if ( v671 )
          {
            v459 = GetProcessHeap();
            HeapFree(v459, 0, v671);
            v289 = v670;
            *((_QWORD *)v670 + 3) = 0;
          }
          v671 = (LPVOID)v289[5];
          if ( v671 )
          {
            v460 = GetProcessHeap();
            HeapFree(v460, 0, v671);
            *((_QWORD *)v670 + 5) = 0;
          }
          v461 = GetProcessHeap();
          HeapFree(v461, 0, v670);
        }
        else
        {
          v666 = v287;
        }
        v255 = v651[0] | 0x10000000;
        if ( v651[0] < 0 )
          goto LABEL_356;
        v290 = *v287;
        v653 = 0;
        v651[0] = 4;
        v654 = RtlUIntAdd(4, v290, v651);
        if ( v654 < 0 )
          goto LABEL_326;
        v654 = RtlUIntAdd(v651[0], v291, v651);
        if ( v654 < 0 )
          goto LABEL_326;
        v462 = v287[4];
        psz = (STRSAFE_PCNZWCH)(v287 + 4);
        v654 = RtlUIntAdd(v651[0], v462, v651);
        if ( v654 < 0 )
          goto LABEL_326;
        v654 = RtlUIntAdd(v651[0], v463, v651);
        if ( v654 < 0 )
          goto LABEL_326;
        v464 = v287[8];
        v679 = v287 + 8;
        v654 = RtlUIntAdd(v651[0], v464, v651);
        if ( v654 < 0 )
          goto LABEL_326;
        v666 = v287;
        v465 = v651[0];
        v466 = GetProcessHeap();
        v467 = HeapAlloc(v466, 8u, v465);
        v661 = v467;
        if ( !v467 )
        {
          v654 = -805306345;
          goto LABEL_669;
        }
        v287 = (unsigned int *)v666;
        v468 = *(_QWORD *)&v651[1];
        v469 = (int)v664;
        v668 = v467;
        *v467 = *(_DWORD *)v666;
        LODWORD(v664) = v469;
        *(_QWORD *)&v651[1] = v468;
        v654 = RtlULongLongAdd(v467, 4, &v668);
        if ( v654 < 0 )
        {
          *(_QWORD *)&v651[1] = v471;
          LODWORD(v664) = v472;
          v661 = v470;
        }
        else
        {
          memcpy_0(v668, *((const void **)v287 + 1), *v287);
          v654 = RtlULongLongAdd(v668, *v287, &v668);
          if ( v654 >= 0 )
          {
            v473 = v668;
            *(_DWORD *)v668 = *(_DWORD *)psz;
            v654 = RtlULongLongAdd(v473, 4, &v668);
            if ( v654 >= 0 )
            {
              memcpy_0(v668, *((const void **)v287 + 3), *v474);
              v654 = RtlULongLongAdd(v668, *(unsigned int *)psz, &v668);
              if ( v654 >= 0 )
              {
                v633 = v668;
                *(_DWORD *)v668 = *(_DWORD *)v679;
                v654 = RtlULongLongAdd(v633, 4, &v668);
                if ( v654 >= 0 )
                {
                  memcpy_0(v668, *((const void **)v287 + 5), *v634);
                  v254 = RtlULongLongAdd(v668, *(unsigned int *)v679, &v668);
                  v654 = v254;
                  v666 = v287;
                  if ( v254 >= 0 )
                  {
                    lpMem = v661;
                    v653 = v651[0];
                    goto LABEL_327;
                  }
                  goto LABEL_324;
                }
              }
            }
          }
        }
        v666 = v287;
LABEL_324:
        v253 = GetProcessHeap();
        HeapFree(v253, 0, v661);
LABEL_326:
        v254 = v654;
LABEL_327:
        v255 = v254 | 0x10000000;
        if ( v255 < 0 )
          goto LABEL_356;
        v682 = 8;
        v255 = RtlUIntAdd(8, (unsigned int)v664, &v682) | 0x10000000;
        if ( v255 < 0 )
          goto LABEL_356;
        v256 = (v682 + 7) & 0xFFFFFFF8;
        if ( (unsigned int)v256 < v682 )
        {
          v255 = -1073741675;
          goto LABEL_356;
        }
        v685 = (v682 + 7) & 0xFFFFFFF8;
        v255 = RtlUIntAdd(v256, 8, &v685);
        if ( v255 >= 0 )
        {
          v258 = (unsigned int *)v673[1];
          v668 = v349;
          v661 = v346;
          *(_QWORD *)&v651[1] = v257;
          v666 = v287;
          v655 = 0;
          if ( !v673[1] )
            goto LABEL_813;
          v666 = v287;
          *(_QWORD *)&v651[1] = v257;
          v661 = v346;
          v668 = v349;
          if ( LODWORD(v673[0]) <= 1 )
            goto LABEL_813;
          v659 = (void *)v673[1];
          for ( i2 = 0; !i2; i2 = v573 + 1 )
          {
            v255 = RtlULongLongAdd(v258, 4, &v659);
            if ( v255 < 0 )
              goto LABEL_356;
            v255 = RtlULongLongAdd(v659, v572, &v659);
            if ( v255 < 0 )
              goto LABEL_356;
            v258 = (unsigned int *)v659;
          }
          v260 = *v258;
          v255 = RtlULongLongAdd(v258, 4, &v659);
          if ( v255 < 0 )
            goto LABEL_356;
          v261 = (void *)v673[1];
          if ( !v673[1] || LODWORD(v673[0]) <= 2 )
          {
LABEL_813:
            v255 = -1073741811;
            goto LABEL_356;
          }
          v659 = (void *)v673[1];
          for ( i3 = 0; i3 < 2; i3 = v575 + 1 )
          {
            v255 = RtlULongLongAdd(v261, 4, &v659);
            if ( v255 < 0 )
              goto LABEL_356;
            v255 = RtlULongLongAdd(v659, v574, &v659);
            if ( v255 < 0 )
              goto LABEL_356;
            v261 = v659;
          }
          v255 = RtlULongLongAdd(v261, 4, &v659);
          if ( v255 < 0 )
            goto LABEL_356;
          v655 = v263;
          v651[0] = v264;
          v255 = RtlUIntAdd(v264, v685, v651);
          if ( v255 < 0 )
            goto LABEL_356;
          v255 = RtlUIntAdd(v651[0], v265, v651);
          if ( v255 < 0 )
            goto LABEL_356;
          v255 = RtlUIntAdd(v651[0], v260, v651);
          if ( v255 < 0 )
            goto LABEL_356;
          v255 = RtlUIntAdd(v651[0], v266, v651);
          if ( v255 < 0 )
            goto LABEL_356;
          v255 = RtlUIntAdd(v651[0], v267, v651);
          if ( v255 < 0 )
            goto LABEL_356;
          v655 = v651[0];
          if ( v651[0] > 0x400000u )
          {
            v255 = -2147418113;
            goto LABEL_356;
          }
          v268 = v651[0];
          v269 = GetProcessHeap();
          v270 = HeapAlloc(v269, 8u, v268);
          if ( !v270 )
          {
            v270 = 0;
            v654 = -805306345;
            v548 = 0;
            goto LABEL_620;
          }
          hModule = 0;
          v691 = 0;
          v692 = 0;
          if ( !lpMem )
          {
            v654 = -2147024809;
            goto LABEL_669;
          }
          LODWORD(v692) = v653;
          *(_QWORD *)&v691 = lpMem;
          *(_QWORD *)((char *)&v692 + 4) = v655;
          *((_QWORD *)&v691 + 1) = v270;
          if ( GetModuleHandleExW(1u, L"ntdll.dll", &hModule)
            && (v271 = GetProcAddress(hModule, "NtQuerySystemInformation")) != 0 )
          {
            v255 = ((__int64 (__fastcall *)(__int64, __int128 *))v271)(134, &v691) | 0x10000000;
            if ( v255 >= 0 )
            {
              v475 = DWORD1(v692);
LABEL_565:
              LODWORD(v664) = 0;
              v667 = v270;
              if ( v475 < 4 )
                goto LABEL_817;
              v476 = (const wchar_t *)(unsigned int)*v270;
              LODWORD(v663) = *v270;
              v477 = RtlULongLongAdd(v270, 4, &v667);
              if ( v477 < 0 )
                goto LABEL_824;
              v477 = RtlUIntAdd(0, v478, &v664);
              if ( v477 < 0 )
              {
LABEL_825:
                v495 = v666;
                v667 = v270;
                goto LABEL_604;
              }
              if ( v479 - (int)v664 >= (unsigned int)v476 )
              {
                v679 = v667;
                psz = v476;
                v477 = RtlULongLongAdd(v667, (unsigned int)v476, &v667);
                if ( v477 >= 0 )
                {
                  v477 = RtlUIntAdd((unsigned int)v664, (unsigned int)v476, &v664);
                  if ( v477 >= 0 )
                  {
                    if ( v480 - (int)v664 < v481 )
                      goto LABEL_817;
                    v653 = *(_DWORD *)v667;
                    v477 = RtlULongLongAdd(v667, v481, &v667);
                    if ( v477 >= 0 )
                    {
                      v477 = RtlUIntAdd((unsigned int)v664, v482, &v664);
                      if ( v477 >= 0 )
                      {
                        if ( v483 - (int)v664 < (unsigned int)v484 )
                          goto LABEL_817;
                        Size = (SIZE_T)v667;
                        v674 = v484;
                        v477 = RtlULongLongAdd(v667, (unsigned int)v484, &v667);
                        if ( v477 >= 0 )
                        {
                          v477 = RtlUIntAdd((unsigned int)v664, v485, &v664);
                          if ( v477 >= 0 )
                          {
                            if ( v486 - (int)v664 < v487 )
                              goto LABEL_817;
                            v655 = *(_DWORD *)v667;
                            v477 = RtlULongLongAdd(v667, 4, &v667);
                            if ( v477 >= 0 )
                            {
                              v477 = RtlUIntAdd((unsigned int)v664, 4, &v664);
                              if ( v477 >= 0 )
                              {
                                if ( v488 - (int)v664 < v489 )
                                  goto LABEL_817;
                                v477 = RtlUIntAdd((unsigned int)v664, v489, &v664);
                                if ( v477 >= 0 )
                                {
                                  if ( v490 == (_DWORD)v664 && (unsigned int)(v491 + v492 + (_DWORD)v476) + 12LL == v490 )
                                  {
                                    v493 = GetProcessHeap();
                                    v656 = (SIZE_T)HeapAlloc(v493, 8u, 0x30u);
                                    v494 = (_QWORD *)v656;
                                    if ( v656 )
                                    {
                                      v495 = v666;
                                      v668 = v349;
                                      v661 = v346;
                                      v659 = 0;
                                      if ( v679 )
                                      {
                                        *(_DWORD *)v656 = (_DWORD)v663;
                                        v496 = GetProcessHeap();
                                        v497 = HeapAlloc(v496, 8u, (SIZE_T)psz);
                                        if ( !v497 )
                                        {
LABEL_670:
                                          v577 = v656;
                                          v651[0] = -1073741801;
                                          v667 = v270;
                                          v671 = *(LPVOID *)(v656 + 8);
                                          if ( v671 )
                                          {
                                            v578 = GetProcessHeap();
                                            HeapFree(v578, 0, v671);
                                            v577 = v656;
                                            *(_QWORD *)(v656 + 8) = 0;
                                          }
                                          v671 = *(LPVOID *)(v577 + 24);
                                          if ( v671 )
                                          {
                                            v579 = GetProcessHeap();
                                            HeapFree(v579, 0, v671);
                                            v577 = v656;
                                            *(_QWORD *)(v656 + 24) = 0;
                                          }
                                          v671 = *(LPVOID *)(v577 + 40);
                                          if ( v671 )
                                          {
                                            v580 = GetProcessHeap();
                                            HeapFree(v580, 0, v671);
                                            *(_QWORD *)(v656 + 40) = 0;
                                          }
                                          v581 = GetProcessHeap();
                                          HeapFree(v581, 0, (LPVOID)v656);
                                          v504 = (unsigned int *)v659;
                                          goto LABEL_595;
                                        }
                                        *(_QWORD *)(v656 + 8) = v497;
                                        v651[0] = 0;
                                        memcpy_0(v497, v679, (size_t)psz);
                                        v494 = (_QWORD *)v656;
                                      }
                                      else
                                      {
                                        *(_DWORD *)v656 = 0;
                                        v651[0] = 0;
                                        v494[1] = 0;
                                      }
                                      if ( Size )
                                      {
                                        *((_DWORD *)v494 + 4) = v653;
                                        v498 = GetProcessHeap();
                                        v499 = HeapAlloc(v498, 8u, v674);
                                        v500 = v656;
                                        if ( !v499 )
                                        {
LABEL_821:
                                          v656 = v500;
                                          v668 = v349;
                                          v661 = v346;
                                          v666 = v495;
                                          goto LABEL_670;
                                        }
                                        *(_QWORD *)(v656 + 24) = v499;
                                        v651[0] = 0;
                                        memcpy_0(v499, (const void *)Size, v674);
                                        v494 = (_QWORD *)v656;
                                      }
                                      else
                                      {
                                        *((_DWORD *)v494 + 4) = 0;
                                        v494[3] = 0;
                                      }
                                      if ( !v667 )
                                      {
                                        *((_DWORD *)v494 + 8) = 0;
                                        v494[5] = 0;
                                        goto LABEL_594;
                                      }
                                      v501 = (const wchar_t *)v655;
                                      *((_DWORD *)v494 + 8) = v655;
                                      psz = v501;
                                      v502 = GetProcessHeap();
                                      v503 = HeapAlloc(v502, 8u, (SIZE_T)psz);
                                      v500 = v656;
                                      if ( v503 )
                                      {
                                        *(_QWORD *)(v656 + 40) = v503;
                                        v651[0] = 0;
                                        memcpy_0(v503, v667, (size_t)psz);
                                        v494 = (_QWORD *)v656;
LABEL_594:
                                        v504 = (unsigned int *)v494;
                                        v659 = v494;
                                        v667 = v270;
                                        v666 = v495;
                                        v661 = v346;
                                        v668 = v349;
LABEL_595:
                                        v477 = v651[0];
                                        if ( v651[0] >= 0 )
                                        {
                                          v398 = v504;
                                          v660 = v504;
                                        }
                                        else
                                        {
                                          v398 = 0;
                                          v660 = 0;
                                          if ( v504 )
                                          {
                                            v671 = (LPVOID)*((_QWORD *)v504 + 1);
                                            if ( v671 )
                                            {
                                              v505 = GetProcessHeap();
                                              HeapFree(v505, 0, v671);
                                              v504 = (unsigned int *)v659;
                                              *((_QWORD *)v659 + 1) = 0;
                                            }
                                            v671 = (LPVOID)*((_QWORD *)v504 + 3);
                                            if ( v671 )
                                            {
                                              v506 = GetProcessHeap();
                                              HeapFree(v506, 0, v671);
                                              v504 = (unsigned int *)v659;
                                              *((_QWORD *)v659 + 3) = 0;
                                            }
                                            v671 = (LPVOID)*((_QWORD *)v504 + 5);
                                            if ( v671 )
                                            {
                                              v507 = GetProcessHeap();
                                              HeapFree(v507, 0, v671);
                                              *((_QWORD *)v659 + 5) = 0;
                                            }
                                            v508 = GetProcessHeap();
                                            HeapFree(v508, 0, v659);
                                            v477 = v651[0];
                                            v398 = 0;
                                            v660 = 0;
                                          }
                                        }
LABEL_604:
                                        v654 = v477 | 0x10000000;
                                        if ( v477 < 0 )
                                          goto LABEL_669;
                                        if ( !v398 || (v679 = (void *)*((_QWORD *)v398 + 1)) == 0 || !*v398 )
                                        {
                                          v654 = -805306355;
                                          goto LABEL_669;
                                        }
                                        v681 = (LPVOID)(*v398 - 8LL);
                                        v665 = MemoryAlloc((unsigned __int64)v681);
                                        if ( !v665 )
                                        {
LABEL_619:
                                          v654 = -805306367;
                                          v548 = 0;
                                          goto LABEL_620;
                                        }
                                        v509 = 0;
                                        v510 = (unsigned __int8 *)v679;
                                        v657 = 0;
                                        v656 = 0x7F1137FAB69605ELL;
                                        Size = (SIZE_T)v665;
                                        v511 = (unsigned __int8)v681 & 7;
                                        if ( ((unsigned __int8)v681 & 7) != 0 )
                                        {
                                          v635 = 0;
                                          v676 = 0;
                                          v655 = 0;
                                          v636 = 0;
                                          v637 = 0;
                                          do
                                          {
                                            v638 = *v510++;
                                            v653 = 8 * v635;
                                            if ( v635 >= 4 )
                                              v637 |= v638 << (56 - v653);
                                            else
                                              v636 |= v638 << (24 - v653);
                                            ++v635;
                                          }
                                          while ( (int)v635 < v511 );
                                          v676 = v637;
                                          v13 = v649;
                                          v655 = v636;
                                          v639 = (_BYTE *)Size;
                                          v667 = v270;
                                          v666 = v495;
                                          v661 = v346;
                                          v668 = v349;
                                          LODWORD(v663) = 0;
                                          v640 = v676 ^ 0x699A899C;
                                          v513 = v636 ^ 0x92F65A5;
                                          v641 = v636 ^ 0x92F65A5;
                                          v642 = v676 ^ 0x699A899C;
                                          if ( ((unsigned __int8)v681 & 7) != 0 )
                                          {
                                            v643 = (unsigned int)v663;
                                            do
                                            {
                                              v671 = v639 + 1;
                                              if ( v643 >= 4 )
                                              {
                                                v642 = __ROR4__(v642, 24);
                                                v644 = v642;
                                              }
                                              else
                                              {
                                                v641 = __ROR4__(v641, 24);
                                                v644 = v641;
                                              }
                                              *v639 = v644;
                                              ++v643;
                                              v639 = v671;
                                            }
                                            while ( (int)v643 < v511 );
                                            Size = (SIZE_T)v671;
                                            v6 = v677;
                                          }
                                          if ( (unsigned int)v511 <= 4 )
                                          {
                                            v512 = 0;
                                            if ( (unsigned int)v511 < 4 )
                                              v513 = v513 >> (8 * (4 - v511)) << (8 * (4 - v511));
                                          }
                                          else
                                          {
                                            v512 = v640 >> (8 * (8 - v511)) << (8 * (8 - v511));
                                          }
                                        }
                                        else
                                        {
                                          v512 = 0;
                                          v655 = (unsigned __int8)v681 & 7;
                                          v513 = 0;
                                        }
                                        v514 = v681;
                                        if ( (unsigned __int64)v681 >> 3 )
                                        {
                                          v515 = HIDWORD(v656);
                                          v516 = (unsigned __int64)v681 >> 3;
                                          v517 = (_BYTE *)Size;
                                          v651[0] = 24670;
                                          v518 = WORD2(v656);
                                          LODWORD(v663) = HIDWORD(v656) ^ 0xAB69605E;
                                          v519 = HIDWORD(v656) ^ 0xAB69605E;
                                          v520 = v655;
                                          psz = 0;
                                          LODWORD(v664) = WORD2(v656);
                                          do
                                          {
                                            v521 = v510[3] | ((v510[2] | ((v510[1] | (*v510 << 8)) << 8)) << 8);
                                            v522 = v513 ^ v521;
                                            v523 = v510[7] | ((v510[6] | ((v510[5] | (v510[4] << 8)) << 8)) << 8);
                                            v671 = v510 + 8;
                                            v524 = v512 ^ v523 ^ v515 ^ v513 ^ v521 ^ 0xAB69605E;
                                            v525 = v522 ^ (__ROR4__(v524, 22) + v518 * __ROR4__(v524 + 1419157410, 27));
                                            v526 = v524 ^ (WORD1(v656) * __ROR4__(v525 + v515, 9) - __ROR4__(v525, 30));
                                            v527 = v525 ^ (v651[0] * (v526 - v518) - (v526 >> 13));
                                            v528 = v526
                                                 ^ (HIWORD(v656) * __ROR4__(v527 ^ WORD1(v656), 26) - __ROR4__(v527, 30));
                                            v529 = v527 ^ (v515 - (v528 ^ 0xAB69605E));
                                            v530 = v528 ^ (WORD1(v656) * (v518 ^ v529)) ^ __ROR4__(v529, 6);
                                            v531 = v529 ^ (__ROR4__(v530, 30) + v651[0] * __ROR4__(v530 + v515, 15));
                                            v532 = v530
                                                 ^ (HIWORD(v656) * __ROR4__(v531 + 1419157410, 14) - __ROR4__(v531, 24));
                                            v533 = v531
                                                 ^ __ROR4__(v532, 10)
                                                 ^ ((_DWORD)v664 * __ROR4__(v532 ^ 0xAB69605E, 12));
                                            v534 = v533
                                                 ^ (HIWORD(v656)
                                                  * (v651[0]
                                                   + __ROR4__(
                                                       ~(v532 ^ (v533 >> 10) ^ (WORD1(v656) * (v533 ^ HIWORD(v656)))),
                                                       5)));
                                            v535 = v532
                                                 ^ (v533 >> 10)
                                                 ^ (WORD1(v656) * (v533 ^ HIWORD(v656)))
                                                 ^ (v534 - HIWORD(v656))
                                                 ^ 0xAB69605E;
                                            v536 = v534
                                                 ^ ((v535 >> 2) + (_DWORD)v664 * __ROR4__(v535 ^ HIWORD(v656), 30));
                                            v537 = v535 ^ (__ROR4__(v536, 25) + WORD1(v656) * __ROR4__(v536 - v515, 6));
                                            v538 = v536 ^ (v651[0] * ((unsigned int)v664 ^ v537) + __ROR4__(v537, 9));
                                            v539 = v537
                                                 ^ (__ROR4__(v538, 25) + HIWORD(v656) * __ROR4__(WORD1(v656) ^ v538, 27));
                                            v540 = v519 ^ v538 ^ v539;
                                            v541 = v539 ^ ((_DWORD)v664 * (__ROR4__(v540, 3) - WORD1(v656)));
                                            v510 = (unsigned __int8 *)v671;
                                            v542 = v540 ^ (v651[0] * __ROR4__(v541 - v515, 1) - __ROR4__(v541, 6));
                                            v543 = v541
                                                 ^ (__ROR4__(v542, 18) + HIWORD(v656) * __ROR4__(v542 - 1419157410, 29));
                                            v544 = v542
                                                 ^ ((_DWORD)v664 * __ROR4__(v543 - 1419157410, 17) - __ROR4__(v543, 14));
                                            v518 = (int)v664;
                                            v545 = v543 ^ (v544 >> 3) ^ (WORD1(v656) * (v651[0] ^ v544));
                                            v512 = v676 ^ v545;
                                            v676 = v523;
                                            v513 = v520
                                                 ^ v544
                                                 ^ __ROR4__(v545, 30)
                                                 ^ (v651[0] * __ROR4__(v515 ^ v545, 28));
                                            v520 = v521;
                                            v517[3] = v513;
                                            v517[7] = v512;
                                            v517[2] = __ROR4__(v513, 8);
                                            v517[6] = __ROR4__(v512, 8);
                                            v517[1] = __ROR4__(v513, 16);
                                            v517[5] = __ROR4__(v512, 16);
                                            *v517 = __ROR4__(v513, 24);
                                            v517[4] = __ROR4__(v512, 24);
                                            v517 += 8;
                                            psz = (STRSAFE_PCNZWCH)((char *)psz + 1);
                                          }
                                          while ( (unsigned __int64)psz < v516 );
                                          v509 = v657;
                                          v6 = v677;
                                          v13 = v649;
                                          v349 = v668;
                                          v346 = v661;
                                          v270 = v667;
                                          v514 = v681;
                                        }
                                        v546 = v665;
                                        v547 = 0;
                                        if ( v514 )
                                        {
                                          do
                                            v509 ^= *((_BYTE *)v665 + v547++);
                                          while ( v547 < (unsigned __int64)v514 );
                                        }
                                        if ( v509 != *(_QWORD *)((char *)v679 + (_QWORD)v514) )
                                        {
                                          MemoryFree(v665);
                                          goto LABEL_619;
                                        }
                                        v651[0] = 0;
                                        v677 = v665;
                                        if ( (unsigned int)v514 < 4 )
                                          goto LABEL_850;
                                        v582 = RtlULongLongAdd(v665, 4, &v677);
                                        if ( v582 >= 0 )
                                        {
                                          v582 = RtlUIntAdd(0, 4, v651);
                                          if ( v582 >= 0 )
                                          {
                                            if ( (unsigned int)((_DWORD)v514 - v651[0]) < 4 )
                                              goto LABEL_851;
                                            v655 = *(_DWORD *)v677;
                                            v582 = RtlULongLongAdd(v677, 4, &v677);
                                            if ( v582 < 0 )
                                              goto LABEL_852;
                                            v582 = RtlUIntAdd(v651[0], 4, v651);
                                            if ( v582 < 0 )
                                              goto LABEL_852;
                                            if ( (int)v514 - v651[0] < v655 )
                                              goto LABEL_851;
                                            v582 = RtlUIntAdd(v651[0], v655, v651);
                                            if ( v582 >= 0 )
                                            {
                                              v586 = (unsigned int)v514;
                                              v587 = (unsigned int *)v677;
                                              Size = v655;
                                              if ( (char *)v546 + v586 >= (char *)v677 + v655
                                                && (unsigned __int64)v546 + v586 - v655 - (_QWORD)v677 < 8 )
                                              {
                                                LODWORD(v663) = *v546;
                                                psz = 0;
                                                v679 = 0;
                                                v674 = 0;
                                                v676 = 0;
                                                if ( v677 )
                                                {
                                                  v582 = RtlULongLongAdd(v677, Size, &psz);
                                                  v654 = v582;
                                                  v665 = v546;
                                                  v660 = v588;
                                                  v666 = v589;
                                                  *(_QWORD *)&v651[1] = v590;
                                                  if ( v582 >= 0 )
                                                  {
                                                    v591 = psz;
                                                    v592 = 4;
                                                    while ( v587 < (unsigned int *)v591 )
                                                    {
                                                      v582 = RtlULongLongAdd(v587, v592, &v679);
                                                      if ( v582 < 0 )
                                                        goto LABEL_848;
                                                      if ( (unsigned __int64)v679 > v593 )
                                                        goto LABEL_843;
                                                      v595 = *v587;
                                                      v653 = 0;
                                                      v582 = RtlUIntAdd(v594, v595, &v653);
                                                      if ( v582 < 0 )
                                                        goto LABEL_355;
                                                      v582 = RtlULongLongAdd(v587, v653, &v674);
                                                      v654 = v582;
                                                      if ( v582 < 0 )
                                                        goto LABEL_848;
                                                      v587 = (unsigned int *)v674;
                                                      if ( v674 > (unsigned __int64)v591 )
                                                        goto LABEL_843;
                                                      ++v676;
                                                    }
                                                    if ( v587 == (unsigned int *)v591 )
                                                    {
                                                      v587 = (unsigned int *)v677;
                                                      goto LABEL_698;
                                                    }
LABEL_843:
                                                    v582 = -1073741811;
                                                    goto LABEL_355;
                                                  }
LABEL_848:
                                                  v645 = v652;
                                                }
                                                else
                                                {
                                                  v582 = 0;
                                                  v665 = v546;
                                                  v654 = 0;
                                                  v660 = v585;
                                                  v666 = v583;
                                                  *(_QWORD *)&v651[1] = v584;
LABEL_698:
                                                  v596 = 0;
                                                  psz = 0;
                                                  if ( v655 )
                                                  {
                                                    v597 = GetProcessHeap();
                                                    v598 = Size;
                                                    psz = (STRSAFE_PCNZWCH)HeapAlloc(v597, 8u, Size);
                                                    v596 = (wchar_t *)psz;
                                                    if ( !psz )
                                                    {
                                                      v582 = -1073741801;
LABEL_355:
                                                      v255 = v582 | 0x10000000;
                                                      goto LABEL_356;
                                                    }
                                                    v582 = 0;
                                                    v654 = 0;
                                                  }
                                                  else
                                                  {
                                                    v598 = Size;
                                                  }
                                                  if ( v587 )
                                                  {
                                                    memcpy_0(v596, v587, v598);
                                                    v582 = v654;
                                                  }
                                                  dwBytes = (SIZE_T)psz;
                                                  v645 = v676;
                                                  v652 = v676;
                                                }
                                                if ( v582 < 0 || (_DWORD)v663 == v645 )
                                                  goto LABEL_355;
LABEL_850:
                                                v582 = -1073741762;
                                                goto LABEL_355;
                                              }
LABEL_851:
                                              v582 = -1073741762;
                                            }
                                          }
                                        }
LABEL_852:
                                        v665 = v546;
                                        *(_QWORD *)&v651[1] = v584;
                                        v666 = v583;
                                        v660 = v585;
                                        goto LABEL_355;
                                      }
                                      goto LABEL_821;
                                    }
                                    v654 = -805306345;
                                    v660 = 0;
                                    v548 = 0;
LABEL_620:
                                    v549 = *(void **)&v651[1];
                                    if ( !*(_QWORD *)&v651[1] )
                                    {
LABEL_621:
                                      v550 = v666;
                                      if ( v666 )
                                      {
                                        v671 = (LPVOID)*((_QWORD *)v666 + 1);
                                        if ( v671 )
                                        {
                                          v551 = GetProcessHeap();
                                          HeapFree(v551, 0, v671);
                                          v550[1] = 0;
                                        }
                                        v671 = (LPVOID)v550[3];
                                        if ( v671 )
                                        {
                                          v552 = GetProcessHeap();
                                          HeapFree(v552, 0, v671);
                                          v550[3] = 0;
                                        }
                                        v671 = (LPVOID)v550[5];
                                        if ( v671 )
                                        {
                                          v553 = GetProcessHeap();
                                          HeapFree(v553, 0, v671);
                                          v550[5] = 0;
                                        }
                                        v554 = GetProcessHeap();
                                        HeapFree(v554, 0, v550);
                                      }
                                      v555 = lpMem;
                                      if ( lpMem )
                                      {
                                        v647 = GetProcessHeap();
                                        HeapFree(v647, 0, v555);
                                      }
                                      if ( v270 )
                                      {
                                        v648 = GetProcessHeap();
                                        HeapFree(v648, 0, v270);
                                      }
                                      v556 = v660;
                                      if ( v660 )
                                      {
                                        v557 = (void *)*((_QWORD *)v660 + 1);
                                        if ( v557 )
                                        {
                                          v558 = GetProcessHeap();
                                          HeapFree(v558, 0, v557);
                                          v556[1] = 0;
                                        }
                                        v559 = (void *)v556[3];
                                        if ( v559 )
                                        {
                                          v560 = GetProcessHeap();
                                          HeapFree(v560, 0, v559);
                                          v556[3] = 0;
                                        }
                                        v561 = (void *)v556[5];
                                        if ( v561 )
                                        {
                                          v562 = GetProcessHeap();
                                          HeapFree(v562, 0, v561);
                                          v556[5] = 0;
                                        }
                                        v563 = GetProcessHeap();
                                        HeapFree(v563, 0, v556);
                                      }
                                      if ( v548 )
                                      {
                                        v564 = GetProcessHeap();
                                        HeapFree(v564, 0, v548);
                                      }
LABEL_643:
                                      if ( v654 >= 0 )
                                      {
                                        v252 = (_DWORD *)dwBytes;
                                        if ( v652 )
                                        {
                                          if ( dwBytes )
                                          {
                                            psz = (STRSAFE_PCNZWCH)dwBytes;
                                            if ( (int)RtlULongLongAdd(dwBytes, 4, &psz) >= 0 )
                                            {
                                              v603 = psz;
                                              if ( !*v252 )
                                                v603 = 0;
                                              if ( *v252 == (_DWORD)v566 && *(int *)v603 >= 0 && v565 > 1 )
                                              {
                                                v599 = v252;
                                                v677 = v252;
                                                for ( i4 = 0; !i4; i4 = v602 + 1 )
                                                {
                                                  if ( (int)RtlULongLongAdd(v599, v566, &v677) < 0
                                                    || (int)RtlULongLongAdd(v677, v601, &v677) < 0 )
                                                  {
                                                    goto LABEL_647;
                                                  }
                                                  v599 = v677;
                                                }
                                                RtlULongLongAdd(v599, v566, &v677);
                                              }
                                            }
                                          }
                                        }
                                        goto LABEL_647;
                                      }
                                      goto LABEL_321;
                                    }
LABEL_854:
                                    v646 = GetProcessHeap();
                                    HeapFree(v646, 0, v549);
                                    goto LABEL_621;
                                  }
LABEL_817:
                                  v654 = -805306306;
                                  goto LABEL_669;
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
LABEL_824:
                v398 = (unsigned int *)v660;
                goto LABEL_825;
              }
              v654 = -805306306;
LABEL_664:
              v548 = v398;
              goto LABEL_620;
            }
          }
          else
          {
            v255 = GetLastError();
            v576 = v255 < 0;
            if ( v255 > 0 )
            {
              v255 = (unsigned __int16)v255 | 0x80070000;
              v576 = v255 < 0;
            }
            if ( !v576 )
            {
              v654 = -2147467259;
              goto LABEL_669;
            }
          }
          if ( v255 == -805306333 )
          {
            v654 = -2147024774;
LABEL_669:
            v548 = v665;
            goto LABEL_620;
          }
          if ( v255 >= 0 )
          {
            v475 = v655;
            goto LABEL_565;
          }
        }
LABEL_356:
        v654 = v255;
        goto LABEL_669;
      }
    }
  }
LABEL_321:
  v252 = (_DWORD *)dwBytes;
LABEL_647:
  v567 = (void *)v673[1];
  v673[0] = 0;
  if ( v673[1] )
  {
    v568 = GetProcessHeap();
    HeapFree(v568, 0, v567);
    v673[1] = 0;
  }
  if ( v252 )
  {
    v569 = GetProcessHeap();
    HeapFree(v569, 0, v252);
  }
  if ( v349 )
  {
    v570 = GetProcessHeap();
    HeapFree(v570, 0, v349);
  }
  if ( v346 )
  {
    v571 = GetProcessHeap();
    HeapFree(v571, 0, v346);
  }
LABEL_25:
  LODWORD(v5) = v686;
  v4 = (DWORD *)v6;
  v2 = v695;
LABEL_26:
  if ( v13 >= 0 )
  {
    if ( (_DWORD)v5 == 4 )
    {
      v19 = 0;
      *v2 = *v4;
      goto LABEL_31;
    }
    goto LABEL_34;
  }
LABEL_21:
  if ( v13 == -805306316 )
  {
    v19 = -1073418222;
    goto LABEL_31;
  }
  if ( v13 != -805306139 && v13 != -1073425151 )
  {
    if ( v13 == -805306306 )
    {
      v19 = -1073418200;
      goto LABEL_31;
    }
    if ( v13 != -2147024774 )
    {
      v19 = v13;
      goto LABEL_31;
    }
LABEL_34:
    v19 = -1073418210;
    goto LABEL_31;
  }
  v19 = -1073418201;
LABEL_31:
  v651[0] = v19;
  if ( v4 )
  {
    LocalFree(v4);
    return v651[0];
  }
  return v19;
}

```

## disassembly

```asm
0x1800315f4  mov     [rsp-8+arg_10], rbx
0x1800315f9  push    rbp
0x1800315fa  push    rsi
0x1800315fb  push    rdi
0x1800315fc  push    r12
0x1800315fe  push    r13
0x180031600  push    r14
0x180031602  push    r15
0x180031604  lea     rbp, [rsp-110h]
0x18003160c  sub     rsp, 210h
0x180031613  mov     [rbp+140h+var_80], rdx
0x18003161a  mov     rdi, rdx
0x18003161d  mov     [rsp+240h+psz], rcx
0x180031622  mov     r15, rcx
0x180031625  test    rcx, rcx
0x180031628  jz      loc_1800362D3
0x18003162e  test    rdx, rdx
0x180031631  jz      loc_1800362D3
0x180031637  xor     ebx, ebx
0x180031639  mov     [rbp+140h+hMem], rbx
0x180031640  lea     edx, [rbx+4]; uBytes
0x180031643  lea     ecx, [rbx+40h]; uFlags
0x180031646  call    cs:__imp_LocalAlloc
0x18003164d  nop     dword ptr [rax+rax+00h]
0x180031652  mov     [rbp+140h+var_138], rax
0x180031656  mov     rsi, rax
0x180031659  test    rax, rax
0x18003165c  jz      loc_1800318BA
0x180031662  xor     eax, eax
0x180031664  mov     [rbp+140h+var_108], ebx
0x180031667  xorps   xmm0, xmm0
0x18003166a  mov     [rbp+140h+var_100], eax
0x18003166d  movups  xmmword ptr [rbp+140h+Src], xmm0
0x180031671  mov     [rbp+140h+var_190], rax
0x180031675  call    cs:__imp_GetProcessHeap
0x18003167c  nop     dword ptr [rax+rax+00h]
0x180031681  lea     r13d, [rbx+8]
0x180031685  mov     r8d, 0A0h; dwBytes
0x18003168b  mov     rcx, rax; hHeap
0x18003168e  mov     edx, r13d; dwFlags
0x180031691  call    cs:__imp_HeapAlloc
0x180031698  nop     dword ptr [rax+rax+00h]
0x18003169d  or      r8d, 0FFFFFFFFh
0x1800316a1  mov     [rsp+240h+var_1F8], 0D0000017h
0x1800316a9  mov     [rbp+140h+var_140], r8d
0x1800316ad  mov     r12, rax
0x1800316b0  mov     r14d, 0C0000095h
0x1800316b6  mov     rbx, 0C81ECB17B1B54A58h
0x1800316c0  mov     rdi, 7F1137FAB69605Eh
0x1800316ca  test    rax, rax
0x1800316cd  jz      loc_180031982
0x1800316d3  movups  xmm0, cs:?DecryptionCipher@?1??WarbirdUmGetDecryptionCipher@@9@4PAEA; uchar near * `WarbirdUmGetDecryptionCipher'::`2'::DecryptionCipher
0x1800316da  movups  xmmword ptr [rax], xmm0
0x1800316dd  movups  xmm1, cs:xmmword_1800E5580
0x1800316e4  movups  xmmword ptr [rax+10h], xmm1
0x1800316e8  movups  xmm0, cs:xmmword_1800E5590
0x1800316ef  movups  xmmword ptr [rax+20h], xmm0
0x1800316f3  movups  xmm1, cs:xmmword_1800E55A0
0x1800316fa  movups  xmmword ptr [rax+30h], xmm1
0x1800316fe  movups  xmm0, cs:xmmword_1800E55B0
0x180031705  movups  xmmword ptr [rax+40h], xmm0
0x180031709  movups  xmm1, cs:xmmword_1800E55C0
0x180031710  movups  xmmword ptr [rax+50h], xmm1
0x180031714  movups  xmm0, cs:xmmword_1800E55D0
0x18003171b  movups  xmmword ptr [rax+60h], xmm0
0x18003171f  movups  xmm1, cs:xmmword_1800E55E0
0x180031726  movups  xmmword ptr [rax+70h], xmm1
0x18003172a  movups  xmm0, cs:xmmword_1800E55F0
0x180031731  movups  xmmword ptr [rax+80h], xmm0
0x180031738  movups  xmm1, cs:xmmword_1800E5600
0x18003173f  movups  xmmword ptr [rax+90h], xmm1
0x180031746  call    cs:__imp_GetProcessHeap
0x18003174d  nop     dword ptr [rax+rax+00h]
0x180031752  mov     r8d, r13d; dwBytes
0x180031755  mov     edx, r13d; dwFlags
0x180031758  mov     rcx, rax; hHeap
0x18003175b  call    cs:__imp_HeapAlloc
0x180031762  nop     dword ptr [rax+rax+00h]
0x180031767  mov     r13, rax
0x18003176a  test    rax, rax
0x18003176d  jz      loc_180031998
0x180031773  mov     rax, cs:?nDecryptionKey@?1??WarbirdUmGetDecryptionKey@@9@4_KA; unsigned __int64 `WarbirdUmGetDecryptionKey'::`2'::nDecryptionKey
0x18003177a  mov     [r13+0], rax
0x18003177e  rdtsc
0x180031780  shl     rdx, 20h; cchMax
0x180031784  or      rax, rdx
0x180031787  mov     [rbp+140h+var_150], rax
0x18003178b  lea     r8, [rbp+140h+pcchLength]; pcchLength
0x18003178f  mov     [rbp+140h+pcchLength], 0
0x180031797  mov     rcx, r15; psz
0x18003179a  call    StringLengthWorkerW
0x18003179f  test    eax, eax
0x1800317a1  js      loc_1800362DD
0x1800317a7  mov     rax, [rbp+140h+pcchLength]
0x1800317ab  inc     rax
0x1800317ae  mov     [rbp+140h+pcchLength], rax
0x1800317b2  lea     eax, ds:4[rax*2]
0x1800317b9  cmp     eax, 4
0x1800317bc  jnb     loc_180032A72
0x1800317c2  mov     r15d, r14d
0x1800317c5  mov     [rsp+240h+var_210], r14d
0x1800317ca  jmp     short loc_18003181B
0x1800317cc  mov     [rbp+140h+lpMem], r14
0x1800317d0  mov     r15d, 0C0000095h
0x1800317d6  xor     r14d, r14d
0x1800317d9  mov     dword ptr [rbp+140h+var_178], r14d
0x1800317dd  call    cs:__imp_GetProcessHeap
0x1800317e4  nop     dword ptr [rax+rax+00h]
0x1800317e9  mov     r8, [rbp+140h+lpMem]; lpMem
0x1800317ed  xor     edx, edx; dwFlags
0x1800317ef  mov     rcx, rax; hHeap
0x1800317f2  call    cs:__imp_HeapFree
0x1800317f9  nop     dword ptr [rax+rax+00h]
0x1800317fe  or      r15d, 10000000h
0x180031805  mov     [rsp+240h+var_210], r15d
0x18003180a  jl      loc_18003203F
0x180031810  mov     r15d, 0D000000Dh
0x180031816  mov     [rsp+240h+var_210], r15d
0x18003181b  mov     r14, [rbp+140h+Src+8]
0x18003181f  mov     [rbp+140h+Src], 0
0x180031827  test    r14, r14
0x18003182a  jz      short loc_180031854
0x18003182c  call    cs:__imp_GetProcessHeap
0x180031833  nop     dword ptr [rax+rax+00h]
0x180031838  mov     r8, r14; lpMem
0x18003183b  xor     edx, edx; dwFlags
0x18003183d  mov     rcx, rax; hHeap
0x180031840  call    cs:__imp_HeapFree
0x180031847  nop     dword ptr [rax+rax+00h]
0x18003184c  mov     [rbp+140h+Src+8], 0
0x180031854  mov     r14, [rbp+140h+var_190]
0x180031858  test    r14, r14
0x18003185b  jz      short loc_18003187D
0x18003185d  call    cs:__imp_GetProcessHeap
0x180031864  nop     dword ptr [rax+rax+00h]
0x180031869  mov     r8, r14; lpMem
0x18003186c  xor     edx, edx; dwFlags
0x18003186e  mov     rcx, rax; hHeap
0x180031871  call    cs:__imp_HeapFree
0x180031878  nop     dword ptr [rax+rax+00h]
0x18003187d  test    r12, r12
0x180031880  jnz     short loc_1800318EB
0x180031882  test    r13, r13
0x180031885  jnz     loc_18003195D
0x18003188b  test    r15d, r15d
0x18003188e  jns     short loc_1800318C2
0x180031890  mov     rcx, rsi; hMem
0x180031893  call    cs:__imp_LocalFree
0x18003189a  nop     dword ptr [rax+rax+00h]
0x18003189f  mov     rbx, [rbp+140h+hMem]
0x1800318a6  cmp     r15d, 0D0000034h
0x1800318ad  jnz     loc_180036D34
0x1800318b3  mov     ecx, 0C004F012h
0x1800318b8  jmp     short loc_18003191C
0x1800318ba  mov     r15d, 8007000Eh
0x1800318c0  jmp     short loc_1800318D9
0x1800318c2  cmp     [rbp+140h+var_108], 0
0x1800318c6  jnz     loc_180034397
0x1800318cc  mov     eax, [rbp+140h+var_100]
0x1800318cf  mov     rbx, rsi
0x1800318d2  mov     rdi, [rbp+140h+var_80]
0x1800318d9  test    r15d, r15d
0x1800318dc  js      short loc_1800318A6
0x1800318de  cmp     eax, 4
0x1800318e1  jnz     short loc_180031956
0x1800318e3  mov     eax, [rbx]
0x1800318e5  xor     ecx, ecx
0x1800318e7  mov     [rdi], eax
0x1800318e9  jmp     short loc_18003191C
0x1800318eb  call    cs:__imp_GetProcessHeap
0x1800318f2  nop     dword ptr [rax+rax+00h]
0x1800318f7  mov     r8, r12; lpMem
0x1800318fa  xor     edx, edx; dwFlags
0x1800318fc  mov     rcx, rax; hHeap
0x1800318ff  call    cs:__imp_HeapFree
0x180031906  nop     dword ptr [rax+rax+00h]
0x18003190b  jmp     loc_180031882
0x180031910  cmp     r15d, 8007007Ah
0x180031917  jz      short loc_180031956
0x180031919  mov     ecx, r15d
0x18003191c  mov     dword ptr [rsp+240h+var_20C], ecx
0x180031920  test    rbx, rbx
0x180031923  jz      short loc_180031938
0x180031925  mov     rcx, rbx; hMem
0x180031928  call    cs:__imp_LocalFree
0x18003192f  nop     dword ptr [rax+rax+00h]
0x180031934  mov     ecx, dword ptr [rsp+240h+var_20C]
0x180031938  mov     rbx, [rsp+240h+arg_10]
0x180031940  mov     eax, ecx
0x180031942  add     rsp, 210h
0x180031949  pop     r15
0x18003194b  pop     r14
0x18003194d  pop     r13
0x18003194f  pop     r12
0x180031951  pop     rdi
0x180031952  pop     rsi
0x180031953  pop     rbp
0x180031954  retn
0x180031956  mov     ecx, 0C004F01Eh
0x18003195b  jmp     short loc_18003191C
0x18003195d  call    cs:__imp_GetProcessHeap
0x180031964  nop     dword ptr [rax+rax+00h]
0x180031969  mov     r8, r13; lpMem
0x18003196c  xor     edx, edx; dwFlags
0x18003196e  mov     rcx, rax; hHeap
0x180031971  call    cs:__imp_HeapFree
0x180031978  nop     dword ptr [rax+rax+00h]
0x18003197d  jmp     loc_18003188B
0x180031982  xor     r13d, r13d
0x180031985  mov     r15d, 0C0000017h
0x18003198b  mov     [rsp+240h+var_210], r15d
0x180031990  xor     r12d, r12d
0x180031993  jmp     loc_18003181B
0x180031998  mov     r15d, 0C0000017h
0x18003199e  xor     r13d, r13d
0x1800319a1  mov     [rsp+240h+var_210], r15d
0x1800319a6  jmp     loc_18003181B
0x1800319ab  mov     rcx, [rsp+240h+psz]
0x1800319b0  mov     [r14+r15-8], rcx
0x1800319b5  mov     rcx, rax; void *
0x1800319b8  mov     r8d, dword ptr [rbp+140h+Src+4]; Size
0x1800319bc  mov     rdx, [rbp+140h+Src+8]; Src
0x1800319c0  call    memcpy_0
0x1800319c5  mov     r15d, dword ptr [rbp+140h+var_178]
0x1800319c9  xor     eax, eax
0x1800319cb  mov     [rsp+240h+var_1D0], 0
0x1800319d4  mov     qword ptr [rsp+240h+var_20C+4], 0
0x1800319dd  mov     [rbp+140h+var_118], 0
0x1800319e5  mov     [rbp+140h+var_1B8], 0
0x1800319ed  mov     [rbp+140h+var_198], rax
0x1800319f1  mov     [rbp+140h+var_1A0], rax
0x1800319f5  test    r15, r15
0x1800319f8  jz      loc_180036652
0x1800319fe  lea     rax, [r15+8]
0x180031a02  mov     rcx, rax; unsigned __int64
0x180031a05  mov     [rbp+140h+dwBytes], rax
0x180031a09  call    ?MemoryAlloc@@YAPEAX_K@Z; MemoryAlloc(unsigned __int64)
0x180031a0e  mov     [rbp+140h+var_1B0], rax
0x180031a12  mov     rdx, rax
0x180031a15  test    rax, rax
0x180031a18  jz      loc_180036652
0x180031a1e  xor     al, al
0x180031a20  xor     ecx, ecx
0x180031a22  mov     [rsp+240h+var_1E8], al
0x180031a26  test    r15, r15
0x180031a29  jz      short loc_180031A3B
0x180031a2b  xor     al, [r14+rcx]
0x180031a2f  inc     rcx
0x180031a32  cmp     rcx, r15
0x180031a35  jb      short loc_180031A2B
0x180031a37  mov     [rsp+240h+var_1E8], al
0x180031a3b  mov     rcx, r15
0x180031a3e  mov     [rbp+140h+var_1A8], r12
0x180031a42  shr     rcx, 3
0x180031a46  mov     [rsp+240h+var_1D8], r13
0x180031a4b  mov     [rsp+240h+var_1C8], rbx
0x180031a50  mov     [rsp+240h+var_1F4+4], r14
0x180031a55  test    rcx, rcx
0x180031a58  jz      loc_180031DC1
0x180031a5e  mov     r10d, dword ptr [rsp+240h+var_1C8+4]
0x180031a63  mov     rax, r14
0x180031a66  movzx   r8d, word ptr [rsp+240h+var_1C8+2]
0x180031a6c  mov     r12, rdx
0x180031a6f  movzx   r13d, word ptr [rsp+240h+var_1C8+6]
0x180031a75  or      r9d, 0FFFFFFFFh
0x180031a79  movzx   esi, r10w
0x180031a7d  mov     rdi, rcx
0x180031a80  mov     [rbp+140h+lpMem], 0
0x180031a88  movzx   r15d, bx
0x180031a8c  mov     dword ptr [rsp+240h+var_1F4], 0
0x180031a94  mov     dword ptr [rsp+240h+var_20C], 0
0x180031a9c  mov     dword ptr [rsp+240h+var_200], 0
0x180031aa4  movzx   ecx, byte ptr [rax+1]
0x180031aa8  movzx   r14d, byte ptr [rax]
0x180031aac  movzx   r11d, byte ptr [rax+4]
0x180031ab1  lea     rax, [rax+8]
0x180031ab5  shl     r14d, 8
0x180031ab9  or      r14d, ecx
0x180031abc  shl     r11d, 8
0x180031ac0  movzx   ecx, byte ptr [rax-6]
0x180031ac4  shl     r14d, 8
0x180031ac8  or      r14d, ecx
0x180031acb  movzx   ecx, byte ptr [rax-5]
0x180031acf  shl     r14d, 8
0x180031ad3  or      r14d, ecx
0x180031ad6  movzx   ecx, byte ptr [rax-3]
0x180031ada  or      r11d, ecx
0x180031add  movzx   ecx, byte ptr [rax-2]
0x180031ae1  shl     r11d, 8
0x180031ae5  or      r11d, ecx
0x180031ae8  movzx   ecx, byte ptr [rax-1]
0x180031aec  shl     r11d, 8
0x180031af0  or      r11d, ecx
0x180031af3  mov     edx, r11d
0x180031af6  xor     edx, r9d
0x180031af9  mov     r9d, edx
0x180031afc  sub     r9d, r15d
0x180031aff  xor     r9d, r10d
0x180031b02  xor     r9d, r14d
0x180031b05  xor     r9d, dword ptr [rsp+240h+var_200]
  ... truncated ...
```
