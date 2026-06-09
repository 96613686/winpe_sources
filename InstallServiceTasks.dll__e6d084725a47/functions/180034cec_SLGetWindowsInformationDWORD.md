# SLGetWindowsInformationDWORD

- ea: `0x180034cec`
- end: `0x18003a562`
- name: `SLGetWindowsInformationDWORD`
- size: `22646`
- prototype: `HRESULT __stdcall(PCWSTR pwszValueName, DWORD *pdwValue)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x1800211d8`
- `0x180026dc0`

## callees

- `0x1800047ad`
- `0x180006a0c`
- `0x180034c68`
- `0x180034c94`
- `0x180034cc0`
- `0x180034cec`
- `0x18003a568`
- `0x18003a584`
- `0x18003a5a4`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180036f27`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180039465`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180036f27`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180039465`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180036ede`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18003942d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180036ede`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18003942d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003527c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003529d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800352b6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800352cf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180035ea7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800365f8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180036626`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180036654`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180036675`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800366c7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800366f7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180036726`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180036755`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180036778`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180036895`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800368c0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800368ea`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180036914`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180036930`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003694d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180036966`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180036990`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800369b5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800369da`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800369f6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180036a13`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180036ba5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180037311`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180037340`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003736f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180037392`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180037428`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180037457`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180037486`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800374a9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180038636`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180038d78`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180038da7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180038dd6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180038df9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180038e53`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180038e83`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180038eb2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180038ee1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180038f04`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003914f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039830`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003985e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003988c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800398ad`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039943`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039972`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800399a1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800399c4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a20a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a230`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a255`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a27a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a296`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a2b3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a2cc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a2f6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a31b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a340`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a35c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a375`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a44e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a46f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a488`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a4a1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003527c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003529d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800352b6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800352cf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180035ea7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800365f8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180036626`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180036654`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180036675`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800366c7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800366f7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180036726`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180036755`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180036778`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180036895`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800368c0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800368ea`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180036914`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180036930`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003694d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180036966`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180036990`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800369b5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800369da`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800369f6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180036a13`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180036ba5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180037311`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180037340`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003736f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180037392`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180037428`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180037457`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180037486`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800374a9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180038636`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180038d78`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180038da7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180038dd6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180038df9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180038e53`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180038e83`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180038eb2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180038ee1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180038f04`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003914f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039830`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003985e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003988c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800398ad`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039943`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039972`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800399a1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800399c4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a20a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a230`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a255`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a27a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a296`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a2b3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a2cc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a2f6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a31b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a340`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a35c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a375`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a44e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a46f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a488`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a4a1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180034d94`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180034e5d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800350d5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003530f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800353a2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800354d4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180035df1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003643e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800364a8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800364fb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003659c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180036855`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180036d0a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003717e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800371ea`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003724c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800372b3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180037c7d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180038585`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180038be4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180038c1c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180038c74`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180038d1c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180038fde`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180039206`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800396ac`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180039710`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180039776`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800397dd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003a157`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180034d94`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180034e5d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800350d5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003530f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800353a2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800354d4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180035df1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003643e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800364a8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800364fb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003659c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180036855`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180036d0a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003717e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800371ea`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003724c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800372b3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180037c7d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180038585`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180038be4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180038c1c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180038c74`

## string_xrefs

- `0x180036ec0`: `ntdll.dll`
- `0x18003940f`: `ntdll.dll`

## pseudocode

```c
HRESULT __stdcall SLGetWindowsInformationDWORD(PCWSTR pwszValueName, DWORD *pdwValue)
{
  DWORD *v2; // rdi
  HRESULT v3; // ebx
  int v4; // ebx
  HLOCAL v5; // rax
  _DWORD *v6; // rsi
  HANDLE ProcessHeap; // rax
  _OWORD *v8; // rax
  void *v9; // r15
  int v10; // r14d
  void *v11; // r12
  HANDLE v12; // rax
  _QWORD *v13; // rax
  int v14; // eax
  unsigned int v15; // ecx
  unsigned int v16; // r11d
  int v17; // eax
  unsigned int v18; // r11d
  int v19; // r9d
  int v20; // eax
  unsigned int v21; // r11d
  int v22; // r9d
  int v23; // eax
  size_t v24; // rdx
  int v25; // r9d
  unsigned int v26; // r11d
  int v27; // eax
  unsigned int v28; // r11d
  int v29; // eax
  unsigned int v30; // r11d
  int v31; // r9d
  int v32; // eax
  int v33; // r9d
  unsigned int v34; // esi
  HANDLE v35; // rax
  void *v36; // rax
  _DWORD *v37; // r9
  unsigned int v38; // r11d
  _DWORD *v39; // rax
  unsigned int v40; // eax
  unsigned int v41; // r10d
  void *v42; // r13
  HANDLE v43; // rax
  HANDLE v44; // rax
  HANDLE v45; // rax
  HANDLE v46; // rax
  void *v47; // r12
  _DWORD *v48; // r13
  HANDLE v49; // rax
  _OWORD *v50; // rax
  void *v51; // r15
  HANDLE v52; // rax
  _QWORD *v53; // rax
  void *v54; // r13
  int v55; // ecx
  unsigned int v56; // r11d
  int v57; // eax
  unsigned int v58; // r11d
  int v59; // r9d
  int v60; // eax
  unsigned int v61; // r11d
  int v62; // r9d
  int v63; // eax
  int v64; // r9d
  unsigned int v65; // esi
  HANDLE v66; // rax
  _DWORD *v67; // rax
  _DWORD *v68; // rsi
  unsigned int *v69; // r9
  __int64 v70; // rdx
  __int64 v71; // r9
  unsigned int *v72; // r9
  unsigned int v73; // r11d
  unsigned int v74; // r10d
  unsigned int *v75; // r9
  unsigned int jj; // r11d
  __int64 v77; // rdx
  __int64 v78; // r9
  int v79; // r11d
  _DWORD *v80; // r9
  unsigned int *v81; // r10
  unsigned int v82; // r9d
  size_t v83; // rdx
  unsigned int kk; // r11d
  __int64 v85; // rdx
  __int64 v86; // r10
  int v87; // r11d
  _DWORD *v88; // r10
  SIZE_T *v89; // rax
  SIZE_T v90; // rcx
  unsigned int v91; // r11d
  unsigned int *v92; // r9
  unsigned int mm; // esi
  __int64 v94; // rdx
  __int64 v95; // r9
  _DWORD *v96; // r9
  __int64 v97; // r10
  STRSAFE_PCNZWCH v98; // rdx
  void *v99; // rcx
  unsigned int *v100; // r9
  unsigned int v101; // r10d
  unsigned int nn; // r11d
  __int64 v103; // rdx
  __int64 v104; // r9
  int v105; // r11d
  _DWORD *v106; // r9
  _DWORD *v107; // rax
  unsigned int *v108; // r9
  unsigned int v109; // r10d
  unsigned int i5; // r11d
  __int64 v111; // rdx
  __int64 v112; // r9
  int v113; // r11d
  _DWORD *v114; // r9
  _DWORD *v115; // rax
  __int64 v116; // rcx
  unsigned int v117; // r9d
  unsigned int v118; // r9d
  int v119; // r14d
  unsigned int v120; // eax
  unsigned int v121; // esi
  HANDLE v122; // rax
  _DWORD *v123; // rsi
  int v124; // r9d
  unsigned int v125; // r10d
  size_t v126; // rcx
  HANDLE v127; // rax
  unsigned int *v128; // r13
  unsigned int *v129; // rsi
  wchar_t *v130; // r14
  unsigned __int64 v131; // r10
  unsigned __int8 v132; // al
  unsigned __int64 v133; // rcx
  STRSAFE_PCNZWCH v134; // r11
  int v135; // edx
  unsigned int v136; // r9d
  int v137; // edi
  int v138; // ebx
  int v139; // r8d
  unsigned int v140; // r9d
  unsigned int v141; // r8d
  unsigned int v142; // ecx
  int v143; // r11d
  _BYTE *v144; // rdi
  char v145; // bl
  int v146; // r9d
  int v147; // r15d
  SIZE_T v148; // r14
  _BYTE *v149; // rdi
  int v150; // r13d
  unsigned int v151; // r12d
  int v152; // eax
  int v153; // esi
  int v154; // r11d
  int v155; // edx
  int v156; // r9d
  int v157; // r10d
  int v158; // r8d
  int v159; // r9d
  unsigned int v160; // edx
  int v161; // r8d
  int v162; // ecx
  int v163; // edx
  int v164; // r8d
  int v165; // r9d
  int v166; // edx
  unsigned int v167; // r8d
  unsigned int v168; // r9d
  int v169; // edx
  int v170; // r8d
  int v171; // r9d
  int v172; // edx
  int v173; // r8d
  int v174; // r9d
  int v175; // r10d
  int v176; // r8d
  unsigned int v177; // edx
  int v178; // r8d
  int v179; // r9d
  HANDLE v180; // rax
  wchar_t *v181; // rax
  int v182; // r14d
  HANDLE v183; // rax
  void *v184; // rcx
  STRSAFE_PCNZWCH v185; // r14
  HANDLE v186; // rax
  _OWORD *v187; // rax
  HANDLE v188; // rax
  _QWORD *v189; // rax
  STRSAFE_PCNZWCH v190; // rax
  HANDLE v191; // rax
  HANDLE v192; // rax
  HANDLE v193; // rax
  HANDLE v194; // rax
  HANDLE v195; // rax
  size_t v196; // rax
  HANDLE v197; // rax
  HANDLE v198; // rax
  HANDLE v199; // rax
  HANDLE v200; // rax
  __int64 v201; // rdx
  unsigned int v202; // r9d
  int v203; // r14d
  __int64 v204; // rdx
  unsigned int v205; // r9d
  __int64 v206; // rdx
  unsigned int v207; // esi
  HANDLE v208; // rax
  unsigned int *v209; // rax
  unsigned int *v210; // rcx
  LPVOID v211; // rax
  HANDLE v212; // rax
  HANDLE v213; // rax
  HANDLE v214; // rax
  HANDLE v215; // rax
  HANDLE v216; // rax
  void *v217; // rsi
  HANDLE v218; // rax
  HANDLE v219; // rax
  _QWORD *v220; // rsi
  void *v221; // r13
  HANDLE v222; // rax
  void *v223; // r13
  HANDLE v224; // rax
  void *v225; // r13
  HANDLE v226; // rax
  HANDLE v227; // rax
  void *v228; // rsi
  HANDLE v229; // rax
  unsigned int v230; // eax
  void *v231; // rcx
  void *v232; // r9
  int v233; // r10d
  void *v234; // rcx
  unsigned int *v235; // r9
  void *v236; // rcx
  unsigned int *v237; // r9
  HANDLE v238; // rax
  int v239; // eax
  __int64 v240; // rcx
  void *v241; // r9
  unsigned int *v242; // rcx
  unsigned int v243; // r10d
  int i2; // r11d
  unsigned int v245; // r9d
  int v246; // r11d
  LPVOID v247; // rcx
  unsigned int v248; // esi
  HANDLE v249; // rax
  unsigned int i3; // r9d
  unsigned int v251; // r11d
  int v252; // r9d
  unsigned int v253; // r11d
  unsigned int v254; // r11d
  unsigned int v255; // r11d
  unsigned int v256; // r9d
  signed int v257; // eax
  FARPROC v258; // rax
  int v259; // eax
  unsigned int v260; // r9d
  void *v261; // rsi
  unsigned int v262; // r10d
  int v263; // r14d
  unsigned int *v264; // rcx
  int v265; // r9d
  int v266; // r9d
  __int64 v267; // r10
  unsigned int v268; // r10d
  int v269; // r9d
  void *v270; // r11
  unsigned int v271; // r11d
  int v272; // r9d
  unsigned int v273; // r10d
  int v274; // r9d
  unsigned int v275; // r10d
  int v276; // r9d
  int v277; // r10d
  int v278; // r11d
  HANDLE v279; // rax
  _QWORD *v280; // rax
  _QWORD *v281; // rcx
  bool v282; // zf
  HANDLE v283; // rax
  void *v284; // rcx
  HANDLE v285; // rax
  void *v286; // rcx
  void *v287; // rax
  void *v288; // rax
  unsigned int v289; // r14d
  HANDLE v290; // rax
  void *v291; // rcx
  _QWORD *v292; // rax
  HANDLE v293; // rax
  HANDLE v294; // rax
  HANDLE v295; // rax
  HANDLE v296; // rax
  unsigned int *v297; // rdx
  HANDLE v298; // rax
  HANDLE v299; // rax
  HANDLE v300; // rax
  HANDLE v301; // rax
  unsigned __int64 v302; // r14
  _BYTE *v303; // r11
  unsigned __int8 v304; // al
  unsigned int v305; // r9d
  unsigned int v306; // r10d
  int v307; // edi
  unsigned __int8 *v308; // rbx
  unsigned int v309; // eax
  int v310; // r8d
  unsigned int v311; // r8d
  unsigned int v312; // r8d
  unsigned int v313; // r10d
  unsigned int v314; // esi
  unsigned int v315; // ecx
  int v316; // edx
  _BYTE *v317; // rdi
  char v318; // bl
  int v319; // r10d
  int v320; // r11d
  SIZE_T v321; // r15
  unsigned __int8 *v322; // rbx
  int v323; // r13d
  unsigned int v324; // r9d
  unsigned int v325; // r12d
  _BYTE *v326; // rax
  int v327; // ecx
  int v328; // r14d
  int v329; // esi
  int v330; // r14d
  int v331; // edx
  int v332; // esi
  int v333; // r8d
  int v334; // r9d
  unsigned int v335; // edx
  int v336; // r8d
  int v337; // r9d
  unsigned int v338; // edx
  int v339; // r8d
  int v340; // r10d
  int v341; // r11d
  unsigned int v342; // r9d
  int v343; // r8d
  unsigned int v344; // r9d
  int v345; // r10d
  int v346; // r11d
  int v347; // edx
  int v348; // r8d
  int v349; // r9d
  int v350; // edx
  int v351; // r10d
  int v352; // r8d
  unsigned int v353; // edx
  int v354; // r8d
  unsigned __int64 i4; // rcx
  int v356; // r14d
  void *v357; // r9
  void *v358; // r10
  unsigned int *v359; // r11
  const void *v360; // rcx
  int v361; // eax
  void *v362; // rcx
  void *v363; // r11
  void *v364; // r10
  void *v365; // r9
  void *v366; // r10
  void *v367; // r9
  __int64 v368; // r11
  unsigned int *v369; // r9
  SIZE_T v370; // r10
  unsigned int v371; // r11d
  __int64 v372; // rdx
  __int64 v373; // r9
  unsigned int v374; // edx
  void *v375; // r9
  HANDLE v376; // rax
  unsigned int v377; // eax
  size_t v378; // rcx
  int v379; // r9d
  __int64 v380; // r11
  int *v381; // r14
  int i1; // r9d
  unsigned int v383; // r10d
  int v384; // r9d
  int v385; // r9d
  __int64 v386; // r11
  void **v387; // rdx
  void *v388; // rax
  size_t v389; // rcx
  unsigned int v390; // r9d
  unsigned int v391; // r10d
  int v392; // r9d
  int v393; // r9d
  __int64 v394; // r11
  unsigned int *v395; // rdx
  unsigned int v396; // eax
  size_t v397; // rcx
  int v398; // eax
  unsigned int v399; // r10d
  unsigned int v400; // r9d
  unsigned int *v401; // rcx
  unsigned int v402; // r9d
  unsigned int v403; // r13d
  int v404; // r9d
  int v405; // r9d
  unsigned int *v406; // rdx
  unsigned int *v407; // rcx
  unsigned int v408; // r9d
  unsigned int v409; // r13d
  int v410; // r9d
  int v411; // eax
  int v412; // r9d
  size_t v413; // r10
  const void *v414; // r11
  int *v415; // rcx
  unsigned int v416; // r11d
  _DWORD *v417; // rax
  unsigned int v418; // r10d
  unsigned int *v419; // r9
  unsigned int v420; // r11d
  unsigned int i; // esi
  __int64 v422; // rdx
  __int64 v423; // r9
  unsigned int *v424; // r9
  unsigned int v425; // r11d
  unsigned int v426; // r10d
  unsigned int *v427; // r9
  unsigned int v428; // r11d
  unsigned int j; // r11d
  __int64 v430; // rdx
  __int64 v431; // r9
  int v432; // r11d
  _DWORD *v433; // r9
  unsigned int *v434; // r10
  unsigned int v435; // r9d
  unsigned int v436; // r11d
  unsigned int k; // r11d
  __int64 v438; // rdx
  __int64 v439; // r10
  int v440; // r11d
  _DWORD *v441; // r10
  _QWORD *v442; // rax
  LPVOID v443; // rcx
  __int64 v444; // rcx
  unsigned int v445; // r9d
  unsigned int v446; // r13d
  int v447; // eax
  LPVOID v448; // r9
  unsigned int v449; // r10d
  unsigned int v450; // eax
  unsigned int v451; // esi
  HANDLE v452; // rax
  char *v453; // rax
  char *v454; // rsi
  unsigned int v455; // r9d
  size_t v456; // rcx
  HANDLE v457; // rax
  void **v458; // rcx
  unsigned int *v459; // r13
  const void **v460; // rsi
  int v461; // eax
  unsigned __int64 v462; // r11
  unsigned __int8 v463; // al
  unsigned __int64 v464; // r8
  int v465; // r8d
  unsigned int v466; // r10d
  unsigned __int8 *v467; // rdi
  unsigned int v468; // ebx
  unsigned int v469; // esi
  int v470; // r9d
  unsigned int v471; // r10d
  unsigned int v472; // r9d
  unsigned int v473; // ecx
  int v474; // edx
  _BYTE *v475; // rbx
  char v476; // di
  unsigned int v477; // r10d
  SIZE_T v478; // r15
  unsigned __int8 *v479; // rdi
  unsigned int v480; // r12d
  int v481; // r14d
  int v482; // r8d
  unsigned int v483; // eax
  _BYTE *v484; // r13
  int v485; // ecx
  int v486; // esi
  int v487; // r11d
  int v488; // esi
  int v489; // r11d
  int v490; // edx
  int v491; // r10d
  int v492; // r8d
  int v493; // r10d
  int v494; // r9d
  int v495; // r8d
  unsigned int v496; // edx
  int v497; // r9d
  int v498; // ecx
  int v499; // edx
  int v500; // r8d
  int v501; // r9d
  int v502; // edx
  unsigned int v503; // r8d
  unsigned int v504; // r9d
  int v505; // edx
  int v506; // r8d
  int v507; // r9d
  int v508; // edx
  int v509; // r8d
  int v510; // r9d
  int v511; // edx
  int v512; // r8d
  unsigned int v513; // ecx
  int v514; // edx
  int v515; // r10d
  HANDLE v516; // rax
  _DWORD *v517; // rax
  void *v518; // rbx
  unsigned int v519; // ebx
  HANDLE v520; // rax
  void *v521; // rax
  HANDLE v522; // rax
  _OWORD *v523; // rcx
  _DWORD *v524; // rax
  HANDLE v525; // rax
  _QWORD *v526; // rax
  _QWORD *v527; // rax
  HANDLE v528; // rax
  HANDLE v529; // rax
  HANDLE v530; // rax
  HANDLE v531; // rax
  LPVOID v532; // rcx
  HANDLE v533; // rax
  size_t v534; // rax
  HANDLE v535; // rax
  HANDLE v536; // rax
  HANDLE v537; // rax
  HANDLE v538; // rax
  int LastError; // eax
  __int64 v540; // rdx
  unsigned int v541; // r11d
  __int64 v542; // rdx
  unsigned int v543; // r11d
  __int64 v544; // rdx
  unsigned int v545; // ebx
  HANDLE v546; // rax
  LPVOID v547; // rcx
  int v548; // eax
  void *v549; // rcx
  int v550; // r9d
  LPVOID v551; // rcx
  unsigned int *v552; // r9
  LPVOID v553; // rcx
  unsigned int *v554; // r9
  int v555; // eax
  HANDLE v556; // rax
  int v557; // eax
  int v558; // r11d
  __int64 v559; // rcx
  unsigned int *v560; // rcx
  unsigned int v561; // ebx
  HANDLE v562; // rax
  void **v563; // rdi
  int m; // r10d
  unsigned int v565; // r11d
  int v566; // r10d
  unsigned int v567; // ebx
  size_t v568; // rcx
  unsigned int n; // r10d
  unsigned int v570; // r11d
  int v571; // r10d
  unsigned int v572; // r9d
  unsigned int v573; // r11d
  unsigned int v574; // r11d
  unsigned int v575; // r11d
  unsigned int v576; // r10d
  bool v577; // sf
  FARPROC ProcAddress; // rax
  unsigned int v579; // r9d
  SIZE_T v580; // rbx
  int v581; // eax
  unsigned int v582; // r10d
  int v583; // r9d
  int v584; // r9d
  __int64 v585; // r10
  unsigned int v586; // r10d
  int v587; // r9d
  SIZE_T v588; // r11
  unsigned int v589; // r11d
  int v590; // r9d
  unsigned int v591; // r10d
  int v592; // r9d
  unsigned int v593; // r10d
  int v594; // r9d
  int v595; // r10d
  int v596; // r11d
  HANDLE v597; // rax
  _QWORD *v598; // rax
  _DWORD *v599; // rcx
  void *v600; // rbx
  HANDLE v601; // rax
  void *v602; // rcx
  _QWORD *v603; // rax
  HANDLE v604; // rax
  void *v605; // rcx
  SIZE_T v606; // rax
  HANDLE v607; // rax
  void *v608; // rcx
  void *v609; // rcx
  HANDLE v610; // rax
  HANDLE v611; // rax
  HANDLE v612; // rax
  HANDLE v613; // rax
  void **v614; // rdx
  HANDLE v615; // rax
  HANDLE v616; // rax
  HANDLE v617; // rax
  HANDLE v618; // rax
  unsigned int *v619; // r11
  unsigned __int8 v620; // al
  unsigned __int8 *v621; // r8
  unsigned int v622; // r10d
  unsigned int v623; // ecx
  unsigned int v624; // edi
  unsigned int v625; // r11d
  int v626; // r9d
  char v627; // al
  unsigned int *v628; // rcx
  unsigned int v629; // r8d
  unsigned int v630; // r9d
  int v631; // edx
  int v632; // ebx
  unsigned int v633; // edi
  char v634; // al
  int v635; // r9d
  size_t v636; // rbx
  int v637; // r14d
  SIZE_T v638; // r15
  int v639; // r10d
  _BYTE *v640; // r13
  unsigned int v641; // r12d
  unsigned int v642; // r11d
  unsigned __int8 *v643; // rax
  int v644; // ecx
  int v645; // esi
  int v646; // ebx
  int v647; // esi
  int v648; // edx
  int v649; // ebx
  unsigned int v650; // r8d
  int v651; // r9d
  unsigned int v652; // edx
  int v653; // r8d
  int v654; // r9d
  unsigned int v655; // edx
  int v656; // r8d
  int v657; // r10d
  int v658; // r11d
  unsigned int v659; // r9d
  int v660; // r8d
  unsigned int v661; // r9d
  int v662; // r10d
  int v663; // r11d
  int v664; // edx
  int v665; // r8d
  unsigned int v666; // r9d
  int v667; // edx
  int v668; // r10d
  int v669; // r8d
  unsigned int v670; // r9d
  int v671; // edx
  int v672; // r8d
  unsigned int v673; // r9d
  size_t ii; // rcx
  int v675; // eax
  void *v676; // r9
  void *v677; // r10
  unsigned int *v678; // r11
  unsigned int v679; // edi
  const void *v680; // rdi
  unsigned int *v681; // rbx
  unsigned int *v682; // r11
  void *v683; // r10
  void *v684; // r9
  SIZE_T v685; // r9
  __int64 v686; // r10
  unsigned __int64 v687; // r9
  unsigned int v688; // r10d
  __int64 v689; // rdx
  void *v690; // rcx
  HANDLE v691; // rax
  size_t v692; // rbx
  unsigned int v693; // ecx
  void *v694; // rbx
  HANDLE v695; // rax
  void *v696; // rbx
  HANDLE v697; // rax
  void *v698; // rbx
  HANDLE v699; // rax
  void *v700; // rbx
  HANDLE v701; // rax
  HANDLE v702; // rax
  void *v703; // rbx
  HANDLE v704; // rax
  HANDLE v705; // rax
  _QWORD *v706; // rbx
  void *v707; // rsi
  HANDLE v708; // rax
  void *v709; // rsi
  HANDLE v710; // rax
  void *v711; // rsi
  HANDLE v712; // rax
  HANDLE v713; // rax
  HANDLE v714; // rax
  unsigned int v715; // r9d
  __int64 v716; // r11
  int *v717; // rcx
  size_t v718; // rcx
  int v719; // r9d
  unsigned int v720; // r10d
  int v721; // r9d
  void *v722; // rsi
  HANDLE v723; // rax
  HANDLE v724; // rax
  HANDLE v725; // rax
  HANDLE v726; // rax
  SIZE_T dwBytes; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v729; // [rsp+38h] [rbp-C8h] BYREF
  SIZE_T v730; // [rsp+3Ch] [rbp-C4h] BYREF
  LPVOID v731; // [rsp+48h] [rbp-B8h]
  size_t v732; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int8 v733; // [rsp+58h] [rbp-A8h]
  unsigned int v734; // [rsp+5Ch] [rbp-A4h]
  unsigned int v735; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int *v736; // [rsp+68h] [rbp-98h]
  LPVOID v737; // [rsp+70h] [rbp-90h]
  LPVOID v738; // [rsp+78h] [rbp-88h] BYREF
  void *v739; // [rsp+80h] [rbp-80h] BYREF
  LPVOID v740; // [rsp+88h] [rbp-78h]
  LPVOID v741; // [rsp+90h] [rbp-70h] BYREF
  LPVOID v742; // [rsp+98h] [rbp-68h]
  _DWORD *v743; // [rsp+A0h] [rbp-60h] BYREF
  int v744; // [rsp+A8h] [rbp-58h]
  size_t pcchLength; // [rsp+B0h] [rbp-50h] BYREF
  SIZE_T v746; // [rsp+B8h] [rbp-48h]
  unsigned int v747; // [rsp+C0h] [rbp-40h]
  LPVOID lpMem[2]; // [rsp+C8h] [rbp-38h] BYREF
  STRSAFE_PCNZWCH psz; // [rsp+D8h] [rbp-28h]
  SIZE_T v750; // [rsp+E0h] [rbp-20h] BYREF
  LPVOID v751; // [rsp+E8h] [rbp-18h]
  void *v752; // [rsp+F0h] [rbp-10h]
  SIZE_T v753; // [rsp+F8h] [rbp-8h] BYREF
  void *v754; // [rsp+100h] [rbp+0h] BYREF
  void *v755; // [rsp+108h] [rbp+8h] BYREF
  unsigned int v756; // [rsp+110h] [rbp+10h] BYREF
  size_t v757[2]; // [rsp+118h] [rbp+18h] BYREF
  void *Src; // [rsp+128h] [rbp+28h] BYREF
  unsigned int v759; // [rsp+130h] [rbp+30h]
  unsigned int v760; // [rsp+134h] [rbp+34h] BYREF
  unsigned int v761; // [rsp+138h] [rbp+38h] BYREF
  SIZE_T Size; // [rsp+140h] [rbp+40h]
  unsigned int v763; // [rsp+148h] [rbp+48h] BYREF
  unsigned int v764; // [rsp+14Ch] [rbp+4Ch] BYREF
  LPVOID v765; // [rsp+150h] [rbp+50h]
  int v766; // [rsp+158h] [rbp+58h]
  unsigned int v767; // [rsp+15Ch] [rbp+5Ch] BYREF
  unsigned int v768; // [rsp+160h] [rbp+60h]
  unsigned int v769; // [rsp+164h] [rbp+64h] BYREF
  void *v770; // [rsp+168h] [rbp+68h] BYREF
  DWORD *v771; // [rsp+170h] [rbp+70h] BYREF
  HMODULE phModule; // [rsp+180h] [rbp+80h] BYREF
  HMODULE hModule; // [rsp+190h] [rbp+90h] BYREF
  void *v774; // [rsp+198h] [rbp+98h]
  DWORD *v775; // [rsp+1A0h] [rbp+A0h]
  __int128 v776; // [rsp+1A8h] [rbp+A8h] BYREF
  __int128 v777; // [rsp+1B8h] [rbp+B8h]
  __int128 v778; // [rsp+1C8h] [rbp+C8h] BYREF
  __int128 v779; // [rsp+1D8h] [rbp+D8h]

  v775 = pdwValue;
  v2 = pdwValue;
  psz = pwszValueName;
  v771 = 0;
  if ( pwszValueName && pdwValue )
  {
    v4 = 0;
    LODWORD(v746) = 0;
    v770 = 0;
    v5 = LocalAlloc(0x40u, 4u);
    SP<unsigned char,SP_HLOCAL<unsigned char>>::operator=(&v770, v5);
    v774 = v770;
    if ( !v770 )
    {
      v10 = -2147024882;
      goto LABEL_868;
    }
    v766 = 0;
    v6 = 0;
    v768 = 0;
    *(_OWORD *)lpMem = 0;
    v738 = 0;
    ProcessHeap = GetProcessHeap();
    v8 = HeapAlloc(ProcessHeap, 8u, 0xA0u);
    v756 = -1;
    v735 = -805306345;
    v9 = v8;
    if ( !v8 )
    {
      v10 = -1073741801;
      v11 = 0;
      LODWORD(dwBytes) = -1073741801;
      goto LABEL_39;
    }
    *v8 = xmmword_180069D10;
    v8[1] = xmmword_180069D20;
    v8[2] = xmmword_180069D30;
    v8[3] = xmmword_180069D40;
    v8[4] = xmmword_180069D50;
    v8[5] = xmmword_180069D60;
    v8[6] = xmmword_180069D70;
    v8[7] = xmmword_180069D80;
    v8[8] = xmmword_180069D90;
    v8[9] = xmmword_180069DA0;
    v12 = GetProcessHeap();
    v13 = HeapAlloc(v12, 8u, 8u);
    v11 = v13;
    if ( !v13 )
    {
      v10 = -1073741801;
      LODWORD(dwBytes) = -1073741801;
      goto LABEL_39;
    }
    *v13 = qword_180069C50;
    v750 = __rdtsc();
    v729 = 0;
    dwBytes = (unsigned int)RtlUIntAdd(4, 4, &v729);
    v10 = dwBytes;
    if ( (dwBytes & 0x80000000) != 0LL )
      goto LABEL_39;
    v14 = RtlUIntAdd(0, v729, (char *)&dwBytes + 4);
    v10 = v14 | 0x10000000;
    LODWORD(dwBytes) = v14 | 0x10000000;
    if ( v14 < 0 )
      goto LABEL_39;
    v729 = v15;
    LODWORD(dwBytes) = RtlUIntAdd(v16, 160, &v729);
    v10 = dwBytes;
    if ( (dwBytes & 0x80000000) != 0LL )
      goto LABEL_39;
    v17 = RtlUIntAdd(HIDWORD(dwBytes), v729, (char *)&dwBytes + 4);
    v10 = v19 | v17;
    LODWORD(dwBytes) = v19 | v17;
    if ( (v19 | v17) < 0 )
      goto LABEL_39;
    v729 = 0;
    LODWORD(dwBytes) = RtlUIntAdd(v18, v18 + 4, &v729);
    v10 = dwBytes;
    if ( (dwBytes & 0x80000000) != 0LL )
      goto LABEL_39;
    v20 = RtlUIntAdd(HIDWORD(dwBytes), v729, (char *)&dwBytes + 4);
    v10 = v22 | v20;
    LODWORD(dwBytes) = v22 | v20;
    if ( (v22 | v20) < 0 )
      goto LABEL_39;
    v729 = 0;
    LODWORD(dwBytes) = RtlUIntAdd(v21, v21 + 4, &v729);
    v10 = dwBytes;
    if ( (dwBytes & 0x80000000) != 0LL )
      goto LABEL_39;
    v23 = RtlUIntAdd(HIDWORD(dwBytes), v729, (char *)&dwBytes + 4);
    v10 = v25 | v23;
    LODWORD(dwBytes) = v25 | v23;
    if ( (v25 | v23) < 0 )
      goto LABEL_39;
    pcchLength = 0;
    if ( StringCchLengthW(psz, v24, &pcchLength) < 0 )
    {
      v10 = -1073741762;
LABEL_251:
      LODWORD(dwBytes) = v10;
      goto LABEL_39;
    }
    v729 = 0;
    LODWORD(dwBytes) = RtlUIntAdd(v26, (unsigned int)(2 * (pcchLength + 1)), &v729);
    v10 = dwBytes;
    if ( (dwBytes & 0x80000000) != 0LL )
      goto LABEL_39;
    v27 = RtlUIntAdd(HIDWORD(dwBytes), v729, (char *)&dwBytes + 4);
    v10 = v27 | 0x10000000;
    LODWORD(dwBytes) = v27 | 0x10000000;
    if ( v27 < 0 )
      goto LABEL_39;
    v729 = 0;
    LODWORD(dwBytes) = RtlUIntAdd(v28, v28, &v729);
    v10 = dwBytes;
    if ( (dwBytes & 0x80000000) != 0LL )
      goto LABEL_39;
    v29 = RtlUIntAdd(HIDWORD(dwBytes), v729, (char *)&dwBytes + 4);
    v10 = v31 | v29;
    LODWORD(dwBytes) = v31 | v29;
    if ( (v31 | v29) < 0
      || (v729 = 0, LODWORD(dwBytes) = RtlUIntAdd(v30, v30, &v729), v10 = dwBytes, (dwBytes & 0x80000000) != 0LL)
      || (v32 = RtlUIntAdd(HIDWORD(dwBytes), v729, (char *)&dwBytes + 4),
          v10 = v33 | v32,
          LODWORD(dwBytes) = v33 | v32,
          (v33 | v32) < 0) )
    {
LABEL_39:
      v42 = lpMem[1];
      lpMem[0] = 0;
      if ( lpMem[1] )
      {
        v43 = GetProcessHeap();
        HeapFree(v43, 0, v42);
        lpMem[1] = 0;
      }
      if ( v6 )
      {
        v44 = GetProcessHeap();
        HeapFree(v44, 0, v6);
      }
      if ( v9 )
      {
        v45 = GetProcessHeap();
        HeapFree(v45, 0, v9);
      }
      if ( v11 )
      {
        v46 = GetProcessHeap();
        HeapFree(v46, 0, v11);
      }
      if ( v10 < 0 )
      {
        v4 = v746;
        goto LABEL_867;
      }
      if ( !v766 )
      {
LABEL_864:
        v4 = v768;
        v771 = (DWORD *)v774;
        v770 = 0;
LABEL_867:
        v2 = v775;
LABEL_868:
        SP<unsigned char,SP_HLOCAL<unsigned char>>::Reset(&v770);
        if ( v10 >= 0 )
        {
          if ( v4 == 4 )
          {
            v3 = 0;
            *v2 = *v771;
            goto LABEL_881;
          }
        }
        else
        {
          switch ( v10 )
          {
            case -805306316:
              v3 = -1073418222;
              goto LABEL_881;
            case -805306139:
            case -1073425151:
              v3 = -1073418201;
              goto LABEL_881;
            case -805306306:
              v3 = -1073418200;
              goto LABEL_881;
          }
          if ( v10 != -2147024774 )
          {
            v3 = v10;
            goto LABEL_881;
          }
        }
        v3 = -1073418210;
        goto LABEL_881;
      }
      v47 = 0;
      v48 = 0;
      v746 = 0;
      *(_OWORD *)v757 = 0;
      v49 = GetProcessHeap();
      v50 = HeapAlloc(v49, 8u, 0xA0u);
      v51 = v50;
      if ( !v50 )
      {
LABEL_856:
        v722 = (void *)v757[1];
        v757[0] = 0;
        if ( v757[1] )
        {
          v723 = GetProcessHeap();
          HeapFree(v723, 0, v722);
          v757[1] = 0;
        }
        if ( v48 )
        {
          v724 = GetProcessHeap();
          HeapFree(v724, 0, v48);
        }
        if ( v51 )
        {
          v725 = GetProcessHeap();
          HeapFree(v725, 0, v51);
        }
        if ( v47 )
        {
          v726 = GetProcessHeap();
          HeapFree(v726, 0, v47);
        }
        goto LABEL_864;
      }
      *v50 = xmmword_180069D10;
      v50[1] = xmmword_180069D20;
      v50[2] = xmmword_180069D30;
      v50[3] = xmmword_180069D40;
      v50[4] = xmmword_180069D50;
      v50[5] = xmmword_180069D60;
      v50[6] = xmmword_180069D70;
      v50[7] = xmmword_180069D80;
      v50[8] = xmmword_180069D90;
      v50[9] = xmmword_180069DA0;
      v52 = GetProcessHeap();
      v53 = HeapAlloc(v52, 8u, 8u);
      v54 = v53;
      if ( v53 )
      {
        *v53 = qword_180069C50;
        v742 = (LPVOID)__rdtsc();
        v730 = 0;
        if ( (int)RtlUIntAdd(4, 4, (char *)&v730 + 4) < 0 )
          goto LABEL_854;
        if ( (int)RtlUIntAdd(0, HIDWORD(v730), &v730) < 0 )
          goto LABEL_854;
        HIDWORD(v730) = v55;
        if ( (int)RtlUIntAdd(v56, 160, (char *)&v730 + 4) < 0 )
          goto LABEL_854;
        v57 = RtlUIntAdd((unsigned int)v730, HIDWORD(v730), &v730);
        if ( (v59 | v57) < 0 )
          goto LABEL_854;
        HIDWORD(v730) = 0;
        if ( (int)RtlUIntAdd(v58, 8, (char *)&v730 + 4) < 0 )
          goto LABEL_854;
        v60 = RtlUIntAdd((unsigned int)v730, HIDWORD(v730), &v730);
        if ( (v62 | v60) < 0
          || (HIDWORD(v730) = 0, (int)RtlUIntAdd(v61, 8, (char *)&v730 + 4) < 0)
          || (v63 = RtlUIntAdd((unsigned int)v730, HIDWORD(v730), &v730), (v64 | v63) < 0)
          || (HIDWORD(v757[0]) = v730,
              v65 = v730,
              v66 = GetProcessHeap(),
              v67 = HeapAlloc(v66, 8u, v65),
              (v68 = v67) == 0) )
        {
LABEL_854:
          v47 = v54;
          goto LABEL_855;
        }
        v757[1] = (size_t)v67;
        LODWORD(v757[0]) = 0;
        LODWORD(v755) = 0;
        v754 = 0;
        v750 = (SIZE_T)v67;
        v47 = v54;
        if ( (int)RtlULongLongAdd(v67, 4, &v755) < 0 || (unsigned __int64)(v68 + 2) > v757[1] + HIDWORD(v757[0]) )
          goto LABEL_855;
        v417 = v755;
        *v68 = 4;
        *v417 = 4;
        v418 = LODWORD(v757[0]) + 1;
        LODWORD(v755) = 0;
        ++LODWORD(v757[0]);
        v754 = 0;
        if ( v51 )
        {
          if ( !v416 )
            goto LABEL_855;
        }
        else if ( v416 )
        {
          goto LABEL_855;
        }
        v419 = (unsigned int *)v757[1];
        if ( v757[1] )
        {
          v750 = v757[1];
          for ( i = 0; i < v418; ++i )
          {
            v422 = *v419;
            HIDWORD(v730) = 0;
            if ( (int)RtlUIntAdd(4, v422, (char *)&v730 + 4) < 0 || (int)RtlULongLongAdd(v423, HIDWORD(v730), &v750) < 0 )
              goto LABEL_855;
            v419 = (unsigned int *)v750;
          }
          if ( (int)RtlULongLongAdd(v419, 4, &v755) < 0
            || (unsigned __int64)v424 + v425 + 4 > v757[1] + HIDWORD(v757[0]) )
          {
            goto LABEL_855;
          }
          *v424 = v425;
          if ( v51 )
            memcpy_0(v755, v51, v425);
          v420 = 4;
        }
        else
        {
          HIDWORD(v730) = 0;
          if ( (int)RtlUIntAdd(4, v416, (char *)&v730 + 4) < 0
            || (int)RtlUIntAdd(HIDWORD(v757[0]), HIDWORD(v730), (char *)v757 + 4) < 0 )
          {
            goto LABEL_855;
          }
        }
        v426 = LODWORD(v757[0]) + 1;
        LODWORD(v755) = 0;
        ++LODWORD(v757[0]);
        v754 = 0;
        if ( v54 )
        {
          v427 = (unsigned int *)v757[1];
          if ( v757[1] )
          {
            v750 = v757[1];
            for ( j = 0; j < v426; j = v432 + 1 )
            {
              v430 = *v427;
              HIDWORD(v730) = 0;
              if ( (int)RtlUIntAdd(4, v430, (char *)&v730 + 4) < 0
                || (int)RtlULongLongAdd(v431, HIDWORD(v730), &v750) < 0 )
              {
                goto LABEL_855;
              }
              v427 = (unsigned int *)v750;
            }
            if ( (int)RtlULongLongAdd(v427, 4, &v755) < 0 || (unsigned __int64)(v433 + 3) > v757[1] + HIDWORD(v757[0]) )
              goto LABEL_855;
            *v433 = 8;
            memcpy_0(v755, v54, 8u);
            v428 = 4;
          }
          else
          {
            HIDWORD(v730) = 0;
            if ( (int)RtlUIntAdd(v420, 8, (char *)&v730 + 4) < 0
              || (int)RtlUIntAdd(HIDWORD(v757[0]), HIDWORD(v730), (char *)v757 + 4) < 0 )
            {
              goto LABEL_855;
            }
          }
          v434 = (unsigned int *)v757[1];
          v435 = LODWORD(v757[0]) + 1;
          LODWORD(v755) = 0;
          ++LODWORD(v757[0]);
          v754 = 0;
          if ( v757[1] )
          {
            v750 = v757[1];
            for ( k = 0; k < v435; k = v440 + 1 )
            {
              v438 = *v434;
              HIDWORD(v730) = 0;
              if ( (int)RtlUIntAdd(4, v438, (char *)&v730 + 4) < 0
                || (int)RtlULongLongAdd(v439, HIDWORD(v730), &v750) < 0 )
              {
                goto LABEL_855;
              }
              v434 = (unsigned int *)v750;
            }
            if ( (int)RtlULongLongAdd(v434, 4, &v755) < 0 || (unsigned __int64)(v441 + 3) > v757[1] + HIDWORD(v757[0]) )
              goto LABEL_855;
            v442 = v755;
            v443 = v742;
            *v441 = 8;
            *v442 = v443;
          }
          else
          {
            HIDWORD(v730) = 0;
            if ( (int)RtlUIntAdd(v428, 8, (char *)&v730 + 4) < 0
              || (int)RtlUIntAdd(HIDWORD(v757[0]), HIDWORD(v730), (char *)v757 + 4) < 0 )
            {
              goto LABEL_855;
            }
          }
          ++LODWORD(v757[0]);
          HIDWORD(v730) = 0;
          if ( (int)RtlUIntAdd(v436, v436, (char *)&v730 + 4) >= 0 )
          {
            v729 = HIDWORD(v730);
            HIDWORD(v730) = 0;
            if ( (int)RtlUIntAdd(v444, 8, (char *)&v730 + 4) >= 0 && (int)RtlUIntAdd(v445, HIDWORD(v730), &v729) >= 0 )
            {
              v446 = v729;
              v731 = 0;
              v744 = 0;
              HIDWORD(dwBytes) = v729;
              v742 = (LPVOID)__rdtsc();
              v760 = 8;
              v447 = RtlUIntAdd(8, HIDWORD(v757[0]), &v760);
              if ( v447 < 0 )
              {
                v752 = v47;
                v741 = v51;
              }
              else
              {
                v450 = (v760 + 7) & 0xFFFFFFF8;
                if ( v450 < v760 )
                  goto LABEL_855;
                v760 = (v760 + 7) & 0xFFFFFFF8;
                v451 = v450;
                v452 = GetProcessHeap();
                v453 = (char *)HeapAlloc(v452, 8u, v451);
                v454 = v453;
                if ( !v453 )
                  goto LABEL_839;
                v732 = (size_t)v453;
                v741 = v51;
                v752 = v47;
                HIDWORD(dwBytes) = v446;
                *(_DWORD *)v453 = v757[0];
                v729 = RtlULongLongAdd(v453, 4, &v732);
                if ( (v729 & 0x80000000) != 0
                  || (v456 = v732,
                      *(_DWORD *)v732 = HIDWORD(v757[0]),
                      v729 = RtlULongLongAdd(v456, v455, &v732),
                      (v729 & 0x80000000) != 0) )
                {
                  v741 = v51;
                  v752 = v47;
                  HIDWORD(dwBytes) = v446;
                  v457 = GetProcessHeap();
                  HeapFree(v457, 0, v454);
                  v448 = v731;
                  v447 = v729;
                  v449 = (unsigned int)v731;
                }
                else
                {
                  *(_QWORD *)&v454[v760 - 8] = v742;
                  memcpy_0((void *)v732, (const void *)v757[1], HIDWORD(v757[0]));
                  v449 = v760;
                  v448 = v454;
                  v447 = v729;
                  v731 = v454;
                }
              }
              v458 = 0;
              v459 = 0;
              v765 = 0;
              v460 = 0;
              v739 = 0;
              v461 = v447 | 0x10000000;
              v740 = 0;
              v736 = 0;
              if ( v461 < 0 )
              {
                v735 = v461;
                goto LABEL_814;
              }
              if ( v448 )
              {
                v754 = (void *)v449;
                if ( !v449 || (v753 = v449 + 8LL, (Size = (SIZE_T)MemoryAlloc(v753)) == 0) )
                {
                  v694 = v731;
                  v563 = 0;
                  v735 = -805306367;
                  goto LABEL_816;
                }
                v462 = (unsigned __int64)v754;
                v463 = 0;
                v464 = 0;
                v732 = 0;
                v733 = 0;
                if ( v754 )
                {
                  do
                    v463 ^= *((_BYTE *)v731 + v464++);
                  while ( v464 < (unsigned __int64)v754 );
                  v733 = v463;
                }
                v737 = (LPVOID)0xC81ECB17B1B54A58LL;
                pcchLength = (size_t)v731;
                Src = (void *)Size;
                v465 = (unsigned __int8)v754 & 7;
                if ( ((unsigned __int8)v754 & 7) != 0 )
                {
                  v466 = 0;
                  v729 = 0;
                  v734 = 0;
                  v467 = (unsigned __int8 *)v731;
                  v468 = 0;
                  v469 = 0;
                  do
                  {
                    v470 = *v467++;
                    HIDWORD(v730) = 8 * v466;
                    if ( v466 >= 4 )
                      v468 |= v470 << (56 - BYTE4(v730));
                    else
                      v469 |= v470 << (24 - BYTE4(v730));
                    ++v466;
                  }
                  while ( (int)v466 < v465 );
                  v734 = v469;
                  v460 = 0;
                  v729 = v468;
                  pcchLength = (size_t)v467;
                  v752 = v47;
                  v741 = v51;
                  LODWORD(v730) = 0;
                  v471 = v468 ^ 0x42F6B18D;
                  v472 = v734 ^ 0xB17A307A;
                  v473 = v734 ^ 0xB17A307A;
                  v474 = v468 ^ 0x42F6B18D;
                  if ( ((unsigned __int8)v754 & 7) != 0 )
                  {
                    v475 = Src;
                    do
                    {
                      v742 = v475 + 1;
                      if ( (unsigned int)v730 >= 4 )
                      {
                        v474 = __ROR4__(v474, 24);
                        v476 = v474;
                      }
                      else
                      {
                        v473 = __ROR4__(v473, 24);
                        v476 = v473;
                      }
                      *v475 = v476;
                      LODWORD(v730) = v730 + 1;
                      v475 = v742;
                    }
                    while ( (int)v730 < v465 );
                    Src = v742;
                  }
                  if ( (unsigned int)v465 <= 4 )
                  {
                    v477 = 0;
                    if ( (unsigned int)v465 < 4 )
                      v472 = v472 >> (8 * (4 - v465)) << (8 * (4 - v465));
                  }
                  else
                  {
                    v477 = v471 >> (8 * (8 - v465)) << (8 * (8 - v465));
                  }
                }
                else
                {
                  v472 = 0;
                  v734 = 0;
                  v477 = -1;
                  v729 = 0;
                }
                if ( v462 >> 3 )
                {
                  v478 = v462 >> 3;
                  v479 = (unsigned __int8 *)pcchLength;
                  v480 = v734;
                  v481 = WORD2(v737);
                  v482 = 19032;
                  v747 = WORD1(v737);
                  v483 = v729;
                  v750 = 0;
                  v484 = Src;
                  LODWORD(v730) = 19032;
                  do
                  {
                    v485 = v479[1];
                    v486 = *v479;
                    v487 = v479[4];
                    v479 += 8;
                    v488 = *(v479 - 5) | ((*(v479 - 6) | ((v485 | (v486 << 8)) << 8)) << 8);
                    v489 = *(v479 - 1) | ((*(v479 - 2) | ((*(v479 - 3) | (v487 << 8)) << 8)) << 8);
                    v490 = v477 ^ v489;
                    v491 = v472 ^ v488 ^ ((v477 ^ v489) - v482);
                    v492 = v491 ^ HIDWORD(v737);
                    v493 = v490 ^ (__ROR4__(v491 ^ HIDWORD(v737), 7) + WORD1(v737) * __ROR4__(v491, 15));
                    v494 = v492 ^ (v481 * __ROR4__(v493 - 1313519016, 9) - __ROR4__(v493, 10));
                    v495 = v493 ^ (__ROR4__(v494, 27) + HIWORD(v737) * __ROR4__(v494 ^ v481, 28));
                    v496 = v494 ^ (HIDWORD(v737) - (v495 ^ 0xB1B54A58));
                    v497 = v495 ^ (WORD1(v737) * (v496 - v730) - (v496 >> 6));
                    v498 = v496 ^ (v730 * (v481 ^ __ROR4__(v497, 15)));
                    v499 = v497 ^ (v481 * (HIWORD(v737) + __ROR4__(~v498, 3)));
                    v500 = v498 ^ (v499 - HIDWORD(v737) - v730);
                    v501 = v499 ^ (v747 * (v500 ^ HIWORD(v737))) ^ __ROR4__(v500, 10);
                    v502 = v500 ^ __ROR4__(v501, 3) ^ (v481 * __ROR4__(v730 ^ v501, 26));
                    v503 = v501 ^ (v730 * (__ROR4__(v502, 15) - HIWORD(v737)));
                    v504 = v502
                         ^ ((v503 ^ (v503 >> 14)) >> 1)
                         ^ (v730 * (v503 ^ HIWORD(v737)))
                         ^ (v730 * (((unsigned __int64)(v503 - v481) >> 29) | (8 * (v503 - v481))));
                    v505 = v503 ^ (WORD1(v737) * (v504 - v481) - (v504 >> 13));
                    v506 = v504 ^ __ROR4__(v505, 11) ^ (v481 * __ROR4__(-1313519016 - v505, 9));
                    v507 = v505 ^ (v506 + 1313519016 - HIWORD(v737));
                    v508 = v506 ^ (v730 * (v507 ^ WORD1(v737)) - __ROR4__(v507, 7));
                    v509 = v507 ^ (WORD1(v737) * __ROR4__(v508 ^ HIWORD(v737), 28) - __ROR4__(v508, 16));
                    v510 = v508 ^ (__ROR4__(v509, 4) + v481 * __ROR4__(-1313519016 - v509, 10));
                    v511 = v509 ^ __ROR4__(v510, 9) ^ (HIWORD(v737) * __ROR4__(v510 + 1313519016, 4));
                    v512 = v510 ^ (v730 * __ROR4__(HIDWORD(v737) ^ v511, 24) - __ROR4__(v511, 30));
                    v513 = v511 ^ (WORD1(v737) * __ROR4__(HIDWORD(v737) - v512, 11) - __ROR4__(v512, 12));
                    v514 = v512 ^ (v513 >> 8) ^ (v481 * (WORD1(v737) ^ v513));
                    v482 = v730;
                    v472 = v480 ^ v514;
                    v515 = v483 ^ v514 ^ HIDWORD(v737) ^ v513;
                    v484[3] = v480 ^ v514;
                    v477 = v515 ^ 0xB1B54A58;
                    v484[7] = v477;
                    LOBYTE(v513) = __ROR4__(v480 ^ v514, 8);
                    v480 = v488;
                    v484[2] = v513;
                    v483 = v489;
                    v484[6] = __ROR4__(v477, 8);
                    v484[1] = __ROR4__(v472, 16);
                    v484[5] = __ROR4__(v477, 16);
                    *v484 = __ROR4__(v472, 24);
                    v484[4] = __ROR4__(v477, 24);
                    v484 += 8;
                    ++v750;
                  }
                  while ( v750 < v478 );
                  v459 = (unsigned int *)v739;
                  v463 = v733;
                  v460 = (const void **)v739;
                  v10 = dwBytes;
                  v51 = v741;
                  v47 = v752;
                  v462 = (unsigned __int64)v754;
                }
                *(_QWORD *)(Size + v462) = v463;
                v516 = GetProcessHeap();
                v517 = HeapAlloc(v516, 8u, 0x30u);
                v738 = v517;
                if ( !v517 )
                {
                  v518 = v731;
                  LODWORD(v730) = -1073741801;
                  goto LABEL_607;
                }
                v519 = v753;
                *v517 = v753;
                v520 = GetProcessHeap();
                v521 = HeapAlloc(v520, 8u, v519);
                v518 = v731;
                if ( v521 )
                {
                  *((_QWORD *)v738 + 1) = v521;
                  memcpy_0(v521, (const void *)Size, (unsigned int)v753);
                  *((_DWORD *)v738 + 4) = 160;
                  v522 = GetProcessHeap();
                  v523 = HeapAlloc(v522, 8u, 0xA0u);
                  v524 = v738;
                  if ( v523 )
                  {
                    *((_QWORD *)v738 + 3) = v523;
                    *v523 = xmmword_180069C60;
                    v523[1] = xmmword_180069C70;
                    v523[2] = xmmword_180069C80;
                    v523[3] = xmmword_180069C90;
                    v523[4] = xmmword_180069CA0;
                    v523[5] = xmmword_180069CB0;
                    v523[6] = xmmword_180069CC0;
                    v523[7] = xmmword_180069CD0;
                    v523[8] = xmmword_180069CE0;
                    v523[9] = xmmword_180069CF0;
                    v524[8] = 8;
                    v525 = GetProcessHeap();
                    v526 = HeapAlloc(v525, 8u, 8u);
                    if ( v526 )
                    {
                      v532 = v738;
                      *((_QWORD *)v738 + 5) = v526;
                      *v526 = qword_180069D00;
                      v732 = (size_t)v532;
                      LODWORD(v730) = 0;
                      v731 = v518;
                      goto LABEL_606;
                    }
                    v524 = v738;
                  }
                  v738 = v524;
                }
                v527 = v738;
                LODWORD(v730) = -1073741801;
                v731 = v518;
                v742 = (LPVOID)*((_QWORD *)v738 + 1);
                if ( v742 )
                {
                  v528 = GetProcessHeap();
                  HeapFree(v528, 0, v742);
                  v527 = v738;
                  *((_QWORD *)v738 + 1) = 0;
                }
                v742 = (LPVOID)v527[3];
                if ( v742 )
                {
                  v529 = GetProcessHeap();
                  HeapFree(v529, 0, v742);
                  v527 = v738;
                  *((_QWORD *)v738 + 3) = 0;
                }
                v742 = (LPVOID)v527[5];
                if ( v742 )
                {
                  v530 = GetProcessHeap();
                  HeapFree(v530, 0, v742);
                  *((_QWORD *)v738 + 5) = 0;
                }
                v531 = GetProcessHeap();
                HeapFree(v531, 0, v738);
                if ( (v730 & 0x80000000) != 0LL )
                {
LABEL_607:
                  v533 = GetProcessHeap();
                  HeapFree(v533, 0, (LPVOID)Size);
                  v534 = v732;
                  if ( v732 )
                  {
                    v742 = *(LPVOID *)(v732 + 8);
                    if ( v742 )
                    {
                      v535 = GetProcessHeap();
                      HeapFree(v535, 0, v742);
                      v534 = v732;
                      *(_QWORD *)(v732 + 8) = 0;
                    }
                    v742 = *(LPVOID *)(v534 + 24);
                    if ( v742 )
                    {
                      v536 = GetProcessHeap();
                      HeapFree(v536, 0, v742);
                      v534 = v732;
                      *(_QWORD *)(v732 + 24) = 0;
                    }
                    v742 = *(LPVOID *)(v534 + 40);
                    if ( v742 )
                    {
                      v537 = GetProcessHeap();
                      HeapFree(v537, 0, v742);
                      *(_QWORD *)(v732 + 40) = 0;
                    }
                    v538 = GetProcessHeap();
                    HeapFree(v538, 0, (LPVOID)v732);
                  }
                  LastError = v730 | 0x10000000;
                  if ( (v730 & 0x80000000) != 0LL )
                  {
                    v731 = v518;
                    goto LABEL_810;
                  }
                  v540 = *(unsigned int *)v460;
                  HIDWORD(v730) = 0;
                  v735 = 4;
                  LODWORD(v730) = RtlUIntAdd(4, v540, &v735);
                  if ( (v730 & 0x80000000) != 0LL )
                    goto LABEL_634;
                  LODWORD(v730) = RtlUIntAdd(v735, v541, &v735);
                  if ( (v730 & 0x80000000) != 0LL
                    || (v542 = *((unsigned int *)v460 + 4),
                        v750 = (SIZE_T)(v460 + 2),
                        LODWORD(v730) = RtlUIntAdd(v735, v542, &v735),
                        (v730 & 0x80000000) != 0LL)
                    || (LODWORD(v730) = RtlUIntAdd(v735, v543, &v735), (v730 & 0x80000000) != 0LL)
                    || (v544 = *((unsigned int *)v460 + 8),
                        v754 = v460 + 4,
                        LODWORD(v730) = RtlUIntAdd(v735, v544, &v735),
                        (v730 & 0x80000000) != 0LL) )
                  {
LABEL_634:
                    v731 = v518;
                  }
                  else
                  {
                    v545 = v735;
                    v546 = GetProcessHeap();
                    v738 = HeapAlloc(v546, 8u, v545);
                    v547 = v738;
                    if ( !v738 )
                    {
                      v735 = -805306345;
LABEL_679:
                      v563 = (void **)v736;
                      goto LABEL_815;
                    }
                    v548 = *(_DWORD *)v460;
                    v518 = v731;
                    v741 = v738;
                    *(_DWORD *)v738 = v548;
                    LODWORD(v730) = RtlULongLongAdd(v547, 4, &v741);
                    if ( (v730 & 0x80000000) != 0LL )
                    {
                      HIDWORD(dwBytes) = v550;
                      v738 = v549;
                    }
                    else
                    {
                      memcpy_0(v741, v460[1], *(unsigned int *)v460);
                      LODWORD(v730) = RtlULongLongAdd(v741, *(unsigned int *)v460, &v741);
                      if ( (v730 & 0x80000000) == 0LL )
                      {
                        v551 = v741;
                        *(_DWORD *)v741 = *(_DWORD *)v750;
                        LODWORD(v730) = RtlULongLongAdd(v551, 4, &v741);
                        if ( (v730 & 0x80000000) == 0LL )
                        {
                          memcpy_0(v741, v460[3], *v552);
                          LODWORD(v730) = RtlULongLongAdd(v741, *(unsigned int *)v750, &v741);
                          if ( (v730 & 0x80000000) == 0LL )
                          {
                            v553 = v741;
                            *(_DWORD *)v741 = *(_DWORD *)v754;
                            LODWORD(v730) = RtlULongLongAdd(v553, 4, &v741);
                            if ( (v730 & 0x80000000) == 0LL )
                            {
                              memcpy_0(v741, v460[5], *v554);
                              v555 = RtlULongLongAdd(v741, *(unsigned int *)v754, &v741);
                              LODWORD(v730) = v555;
                              if ( v555 >= 0 )
                              {
                                v765 = v738;
                                HIDWORD(v730) = v735;
LABEL_636:
                                LastError = v555 | 0x10000000;
                                if ( LastError < 0 )
                                  goto LABEL_810;
                                v764 = 8;
                                v557 = RtlUIntAdd(8, HIDWORD(dwBytes), &v764);
                                LastError = v558 | v557;
                                if ( LastError < 0 )
                                  goto LABEL_810;
                                v559 = (v764 + 7) & 0xFFFFFFF8;
                                if ( (unsigned int)v559 < v764 )
                                {
                                  LastError = -1073741675;
                                  goto LABEL_810;
                                }
                                v767 = (v764 + 7) & 0xFFFFFFF8;
                                LastError = RtlUIntAdd(v559, 8, &v767);
                                if ( LastError < 0 )
                                  goto LABEL_810;
                                v560 = (unsigned int *)v757[1];
                                v741 = v51;
                                v752 = v47;
                                v731 = v518;
                                psz = (STRSAFE_PCNZWCH)v460;
                                v729 = 0;
                                if ( !v757[1] )
                                  goto LABEL_642;
                                psz = (STRSAFE_PCNZWCH)v460;
                                v731 = v518;
                                v752 = v47;
                                v741 = v51;
                                if ( LODWORD(v757[0]) <= 1 )
                                  goto LABEL_642;
                                v732 = v757[1];
                                for ( m = 0; !m; m = v566 + 1 )
                                {
                                  LastError = RtlULongLongAdd(v560, 4, &v732);
                                  if ( LastError < 0 )
                                    goto LABEL_810;
                                  LastError = RtlULongLongAdd(v732, v565, &v732);
                                  if ( LastError < 0 )
                                    goto LABEL_810;
                                  v560 = (unsigned int *)v732;
                                }
                                v567 = *v560;
                                LastError = RtlULongLongAdd(v560, 4, &v732);
                                if ( LastError < 0 )
                                  goto LABEL_810;
                                v568 = v757[1];
                                if ( !v757[1] || LODWORD(v757[0]) <= 2 )
                                {
LABEL_642:
                                  LastError = -1073741811;
                                  goto LABEL_810;
                                }
                                v732 = v757[1];
                                for ( n = 0; n < 2; n = v571 + 1 )
                                {
                                  LastError = RtlULongLongAdd(v568, 4, &v732);
                                  if ( LastError < 0 )
                                    goto LABEL_810;
                                  LastError = RtlULongLongAdd(v732, v570, &v732);
                                  if ( LastError < 0 )
                                    goto LABEL_810;
                                  v568 = v732;
                                }
                                LastError = RtlULongLongAdd(v568, 4, &v732);
                                if ( LastError < 0 )
                                  goto LABEL_810;
                                v729 = v572;
                                LODWORD(v730) = v573;
                                LastError = RtlUIntAdd(v573, v767, &v730);
                                if ( LastError < 0 )
                                  goto LABEL_810;
                                LastError = RtlUIntAdd((unsigned int)v730, v574, &v730);
                                if ( LastError < 0 )
                                  goto LABEL_810;
                                LastError = RtlUIntAdd((unsigned int)v730, v567, &v730);
                                if ( LastError < 0 )
                                  goto LABEL_810;
                                LastError = RtlUIntAdd((unsigned int)v730, v575, &v730);
                                if ( LastError < 0 )
                                  goto LABEL_810;
                                LastError = RtlUIntAdd((unsigned int)v730, v576, &v730);
                                if ( LastError < 0 )
                                  goto LABEL_810;
                                v729 = v730;
                                if ( (unsigned int)v730 > 0x400000 )
                                {
                                  LastError = -2147418113;
                                  goto LABEL_810;
                                }
                                v561 = v730;
                                v562 = GetProcessHeap();
                                v459 = (unsigned int *)HeapAlloc(v562, 8u, v561);
                                if ( !v459 )
                                {
                                  v735 = -805306345;
                                  v563 = 0;
                                  goto LABEL_815;
                                }
                                hModule = 0;
                                v776 = 0;
                                v777 = 0;
                                if ( !v765 )
                                {
                                  v735 = -2147024809;
                                  goto LABEL_679;
                                }
                                LODWORD(v777) = HIDWORD(v730);
                                *(_QWORD *)&v776 = v765;
                                *(_QWORD *)((char *)&v777 + 4) = v729;
                                *((_QWORD *)&v776 + 1) = v459;
                                if ( GetModuleHandleExW(1u, L"ntdll.dll", &hModule)
                                  && (ProcAddress = GetProcAddress(hModule, "NtQuerySystemInformation")) != 0 )
                                {
                                  LastError = ((__int64 (__fastcall *)(__int64, __int128 *))ProcAddress)(134, &v776)
                                            | 0x10000000;
                                  if ( LastError >= 0 )
                                  {
                                    v579 = DWORD1(v777);
                                    goto LABEL_682;
                                  }
                                }
                                else
                                {
                                  LastError = GetLastError();
                                  v577 = LastError < 0;
                                  if ( LastError > 0 )
                                  {
                                    LastError = (unsigned __int16)LastError | 0x80070000;
                                    v577 = LastError < 0;
                                  }
                                  if ( !v577 )
                                  {
                                    v735 = -2147467259;
                                    goto LABEL_679;
                                  }
                                }
                                if ( LastError == -805306333 )
                                {
                                  v735 = -2147024774;
                                  goto LABEL_679;
                                }
                                if ( LastError < 0 )
                                {
LABEL_810:
                                  v735 = LastError;
                                  goto LABEL_679;
                                }
                                v579 = v729;
LABEL_682:
                                HIDWORD(dwBytes) = 0;
                                v738 = v459;
                                if ( v579 < 4 )
                                {
LABEL_683:
                                  v735 = -805306306;
                                  goto LABEL_679;
                                }
                                v580 = *v459;
                                v747 = *v459;
                                v581 = RtlULongLongAdd(v459, 4, &v738);
                                if ( v581 >= 0 )
                                {
                                  v581 = RtlUIntAdd(0, v582, (char *)&dwBytes + 4);
                                  if ( v581 < 0 )
                                  {
LABEL_737:
                                    v600 = v731;
                                    v739 = v459;
                                    goto LABEL_738;
                                  }
                                  if ( v583 - HIDWORD(dwBytes) < (unsigned int)v580 )
                                  {
                                    v735 = -805306306;
LABEL_814:
                                    v563 = v458;
LABEL_815:
                                    v694 = v731;
                                    if ( !v731 )
                                    {
LABEL_817:
                                      if ( v460 )
                                      {
                                        v696 = (void *)v460[1];
                                        if ( v696 )
                                        {
                                          v697 = GetProcessHeap();
                                          HeapFree(v697, 0, v696);
                                          v460[1] = 0;
                                        }
                                        v698 = (void *)v460[3];
                                        if ( v698 )
                                        {
                                          v699 = GetProcessHeap();
                                          HeapFree(v699, 0, v698);
                                          v460[3] = 0;
                                        }
                                        v700 = (void *)v460[5];
                                        if ( v700 )
                                        {
                                          v701 = GetProcessHeap();
                                          HeapFree(v701, 0, v700);
                                          v460[5] = 0;
                                        }
                                        v702 = GetProcessHeap();
                                        HeapFree(v702, 0, v460);
                                      }
                                      v703 = v765;
                                      if ( v765 )
                                      {
                                        v704 = GetProcessHeap();
                                        HeapFree(v704, 0, v703);
                                      }
                                      if ( v459 )
                                      {
                                        v705 = GetProcessHeap();
                                        HeapFree(v705, 0, v459);
                                      }
                                      v706 = v740;
                                      if ( v740 )
                                      {
                                        v707 = (void *)*((_QWORD *)v740 + 1);
                                        if ( v707 )
                                        {
                                          v708 = GetProcessHeap();
                                          HeapFree(v708, 0, v707);
                                          v706[1] = 0;
                                        }
                                        v709 = (void *)v706[3];
                                        if ( v709 )
                                        {
                                          v710 = GetProcessHeap();
                                          HeapFree(v710, 0, v709);
                                          v706[3] = 0;
                                        }
                                        v711 = (void *)v706[5];
                                        if ( v711 )
                                        {
                                          v712 = GetProcessHeap();
                                          HeapFree(v712, 0, v711);
                                          v706[5] = 0;
                                        }
                                        v713 = GetProcessHeap();
                                        HeapFree(v713, 0, v706);
                                      }
                                      if ( v563 )
                                      {
                                        v714 = GetProcessHeap();
                                        HeapFree(v714, 0, v563);
                                      }
LABEL_839:
                                      if ( (v735 & 0x80000000) == 0 )
                                      {
                                        v48 = (_DWORD *)v746;
                                        if ( v744 )
                                        {
                                          if ( v746 )
                                          {
                                            v750 = v746;
                                            if ( (int)RtlULongLongAdd(v746, 4, &v750) >= 0 )
                                            {
                                              v717 = (int *)v750;
                                              if ( !*v48 )
                                                v717 = 0;
                                              if ( *v48 == (_DWORD)v716 && *v717 >= 0 && v715 > 1 )
                                              {
                                                v718 = (size_t)v48;
                                                v719 = 0;
                                                v732 = (size_t)v48;
                                                while ( !v719 )
                                                {
                                                  if ( (int)RtlULongLongAdd(v718, v716, &v732) < 0
                                                    || (int)RtlULongLongAdd(v732, v720, &v732) < 0 )
                                                  {
                                                    goto LABEL_856;
                                                  }
                                                  v718 = v732;
                                                  v719 = v721 + 1;
                                                }
                                                RtlULongLongAdd(v718, v716, &v732);
                                              }
                                            }
                                          }
                                        }
                                        goto LABEL_856;
                                      }
                                      goto LABEL_855;
                                    }
LABEL_816:
                                    v695 = GetProcessHeap();
                                    HeapFree(v695, 0, v694);
                                    goto LABEL_817;
                                  }
                                  v754 = v738;
                                  v750 = v580;
                                  v581 = RtlULongLongAdd(v738, v580, &v738);
                                  if ( v581 >= 0 )
                                  {
                                    v581 = RtlUIntAdd(HIDWORD(dwBytes), (unsigned int)v580, (char *)&dwBytes + 4);
                                    if ( v581 >= 0 )
                                    {
                                      if ( v584 - HIDWORD(dwBytes) < (unsigned int)v585 )
                                        goto LABEL_683;
                                      v759 = *(_DWORD *)v738;
                                      v581 = RtlULongLongAdd(v738, v585, &v738);
                                      if ( v581 >= 0 )
                                      {
                                        v581 = RtlUIntAdd(HIDWORD(dwBytes), v586, (char *)&dwBytes + 4);
                                        if ( v581 >= 0 )
                                        {
                                          if ( v587 - HIDWORD(dwBytes) < (unsigned int)v588 )
                                            goto LABEL_683;
                                          pcchLength = (size_t)v738;
                                          v753 = v588;
                                          v581 = RtlULongLongAdd(v738, (unsigned int)v588, &v738);
                                          if ( v581 >= 0 )
                                          {
                                            v581 = RtlUIntAdd(HIDWORD(dwBytes), v589, (char *)&dwBytes + 4);
                                            if ( v581 >= 0 )
                                            {
                                              if ( v590 - HIDWORD(dwBytes) < v591 )
                                                goto LABEL_683;
                                              HIDWORD(v730) = *(_DWORD *)v738;
                                              v581 = RtlULongLongAdd(v738, 4, &v738);
                                              if ( v581 >= 0 )
                                              {
                                                v581 = RtlUIntAdd(HIDWORD(dwBytes), 4, (char *)&dwBytes + 4);
                                                if ( v581 >= 0 )
                                                {
                                                  if ( v592 - HIDWORD(dwBytes) < v593 )
                                                    goto LABEL_683;
                                                  v581 = RtlUIntAdd(HIDWORD(dwBytes), v593, (char *)&dwBytes + 4);
                                                  if ( v581 >= 0 )
                                                  {
                                                    if ( v594 != HIDWORD(dwBytes)
                                                      || (unsigned int)(v595 + v596 + v580) + 12LL != v594 )
                                                    {
                                                      goto LABEL_683;
                                                    }
                                                    v597 = GetProcessHeap();
                                                    v598 = HeapAlloc(v597, 8u, 0x30u);
                                                    v751 = v598;
                                                    v599 = v598;
                                                    if ( !v598 )
                                                    {
                                                      v735 = -805306345;
                                                      v740 = 0;
                                                      v563 = 0;
                                                      goto LABEL_815;
                                                    }
                                                    v600 = v731;
                                                    v741 = v51;
                                                    v752 = v47;
                                                    psz = (STRSAFE_PCNZWCH)v460;
                                                    v732 = 0;
                                                    if ( v754 )
                                                    {
                                                      *(_DWORD *)v598 = v747;
                                                      v601 = GetProcessHeap();
                                                      v602 = HeapAlloc(v601, 8u, v750);
                                                      v603 = v751;
                                                      if ( !v602 )
                                                      {
LABEL_716:
                                                        v609 = (void *)v603[1];
                                                        LODWORD(v730) = -1073741801;
                                                        v739 = v459;
                                                        v742 = v609;
                                                        if ( v609 )
                                                        {
                                                          v610 = GetProcessHeap();
                                                          HeapFree(v610, 0, v742);
                                                          v603 = v751;
                                                          *((_QWORD *)v751 + 1) = 0;
                                                        }
                                                        v742 = (LPVOID)v603[3];
                                                        if ( v742 )
                                                        {
                                                          v611 = GetProcessHeap();
                                                          HeapFree(v611, 0, v742);
                                                          v603 = v751;
                                                          *((_QWORD *)v751 + 3) = 0;
                                                        }
                                                        v742 = (LPVOID)v603[5];
                                                        if ( v742 )
                                                        {
                                                          v612 = GetProcessHeap();
                                                          HeapFree(v612, 0, v742);
                                                          *((_QWORD *)v751 + 5) = 0;
                                                        }
                                                        v613 = GetProcessHeap();
                                                        HeapFree(v613, 0, v751);
                                                        v614 = (void **)v732;
                                                        goto LABEL_726;
                                                      }
                                                      *((_QWORD *)v751 + 1) = v602;
                                                      LODWORD(v730) = 0;
                                                      memcpy_0(v602, v754, v750);
                                                      v599 = v751;
                                                    }
                                                    else
                                                    {
                                                      *(_DWORD *)v598 = 0;
                                                      v598[1] = 0;
                                                      LODWORD(v730) = 0;
                                                    }
                                                    if ( pcchLength )
                                                    {
                                                      v599[4] = v759;
                                                      v604 = GetProcessHeap();
                                                      v605 = HeapAlloc(v604, 8u, v753);
                                                      v603 = v751;
                                                      if ( !v605 )
                                                      {
LABEL_715:
                                                        v741 = v51;
                                                        v752 = v47;
                                                        v731 = v600;
                                                        psz = (STRSAFE_PCNZWCH)v460;
                                                        v751 = v603;
                                                        goto LABEL_716;
                                                      }
                                                      *((_QWORD *)v751 + 3) = v605;
                                                      LODWORD(v730) = 0;
                                                      memcpy_0(v605, (const void *)pcchLength, v753);
                                                      v599 = v751;
                                                    }
                                                    else
                                                    {
                                                      v599[4] = 0;
                                                      *((_QWORD *)v599 + 3) = 0;
                                                    }
                                                    if ( v738 )
                                                    {
                                                      v606 = HIDWORD(v730);
                                                      v599[8] = HIDWORD(v730);
                                                      v750 = v606;
                                                      v607 = GetProcessHeap();
                                                      v608 = HeapAlloc(v607, 8u, v750);
                                                      v603 = v751;
                                                      if ( !v608 )
                                                        goto LABEL_715;
                                                      *((_QWORD *)v751 + 5) = v608;
                                                      LODWORD(v730) = 0;
                                                      memcpy_0(v608, v738, v750);
                                                      v599 = v751;
                                                    }
                                                    else
                                                    {
                                                      v599[8] = 0;
                                                      *((_QWORD *)v599 + 5) = 0;
                                                    }
                                                    v614 = (void **)v599;
                                                    v732 = (size_t)v599;
                                                    v739 = v459;
                                                    psz = (STRSAFE_PCNZWCH)v460;
                                                    v731 = v600;
                                                    v752 = v47;
                                                    v741 = v51;
LABEL_726:
                                                    v581 = v730;
                                                    if ( (v730 & 0x80000000) != 0LL )
                                                    {
                                                      v458 = 0;
                                                      v740 = 0;
                                                      if ( v614 )
                                                      {
                                                        v742 = v614[1];
                                                        if ( v742 )
                                                        {
                                                          v615 = GetProcessHeap();
                                                          HeapFree(v615, 0, v742);
                                                          v614 = (void **)v732;
                                                          *(_QWORD *)(v732 + 8) = 0;
                                                        }
                                                        v742 = v614[3];
                                                        if ( v742 )
                                                        {
                                                          v616 = GetProcessHeap();
                                                          HeapFree(v616, 0, v742);
                                                          v614 = (void **)v732;
                                                          *(_QWORD *)(v732 + 24) = 0;
                                                        }
                                                        v742 = v614[5];
                                                        if ( v742 )
                                                        {
                                                          v617 = GetProcessHeap();
                                                          HeapFree(v617, 0, v742);
                                                          *(_QWORD *)(v732 + 40) = 0;
                                                        }
                                                        v618 = GetProcessHeap();
                                                        HeapFree(v618, 0, (LPVOID)v732);
                                                        v581 = v730;
                                                        v458 = 0;
                                                        v740 = 0;
                                                      }
                                                    }
                                                    else
                                                    {
                                                      v458 = v614;
                                                      v740 = v614;
                                                    }
LABEL_738:
                                                    v735 = v581 | 0x10000000;
                                                    if ( v581 < 0 )
                                                      goto LABEL_679;
                                                    if ( !v458 || (Src = v458[1]) == 0 || !*(_DWORD *)v458 )
                                                    {
                                                      v735 = -805306355;
                                                      goto LABEL_679;
                                                    }
                                                    pcchLength = *(unsigned int *)v458 - 8LL;
                                                    v736 = (unsigned int *)MemoryAlloc(pcchLength);
                                                    v619 = v736;
                                                    if ( !v736 )
                                                      goto LABEL_770;
                                                    v620 = 0;
                                                    v621 = (unsigned __int8 *)Src;
                                                    v733 = 0;
                                                    v738 = (LPVOID)0x7F1137FAB69605ELL;
                                                    v750 = (SIZE_T)Src;
                                                    v754 = v736;
                                                    v622 = pcchLength & 7;
                                                    if ( (pcchLength & 7) != 0 )
                                                    {
                                                      v756 = 0;
                                                      v729 = 0;
                                                      v734 = 0;
                                                      v623 = 0;
                                                      v624 = 0;
                                                      v625 = 0;
                                                      do
                                                      {
                                                        v626 = *v621;
                                                        v627 = 8 * v623;
                                                        ++v621;
                                                        if ( v623 >= 4 )
                                                          v625 |= v626 << (56 - v627);
                                                        else
                                                          v624 |= v626 << (24 - v627);
                                                        v623 = v734 + 1;
                                                        v734 = v623;
                                                      }
                                                      while ( (int)v623 < (int)v622 );
                                                      v620 = v733;
                                                      v729 = v624;
                                                      v756 = v625;
                                                      v619 = v736;
                                                      v628 = v736;
                                                      v750 = (SIZE_T)v621;
                                                      v739 = v459;
                                                      psz = (STRSAFE_PCNZWCH)v460;
                                                      v731 = v600;
                                                      v752 = v47;
                                                      v741 = v51;
                                                      v629 = v624 ^ 0x92F65A5;
                                                      v747 = 0;
                                                      v630 = v756 ^ 0x699A899C;
                                                      v631 = v624 ^ 0x92F65A5;
                                                      v632 = v756 ^ 0x699A899C;
                                                      if ( (pcchLength & 7) != 0 )
                                                      {
                                                        v633 = v747;
                                                        do
                                                        {
                                                          v742 = (char *)v628 + 1;
                                                          if ( v633 >= 4 )
                                                          {
                                                            v632 = __ROR4__(v632, 24);
                                                            v634 = v632;
                                                          }
                                                          else
                                                          {
                                                            v631 = __ROR4__(v631, 24);
                                                            v634 = v631;
                                                          }
                                                          *(_BYTE *)v628 = v634;
                                                          ++v633;
                                                          v628 = (unsigned int *)v742;
                                                        }
                                                        while ( (int)v633 < (int)v622 );
                                                        v754 = v742;
                                                        v620 = v733;
                                                      }
                                                      if ( v622 <= 4 )
                                                      {
                                                        v635 = 0;
                                                        if ( v622 < 4 )
                                                          v629 = v629 >> (8 * (4 - v622)) << (8 * (4 - v622));
                                                      }
                                                      else
                                                      {
                                                        v635 = v630 >> (8 * (8 - v622)) << (8 * (8 - v622));
                                                      }
                                                    }
                                                    else
                                                    {
                                                      v635 = 0;
                                                      v729 = 0;
                                                      v629 = 0;
                                                    }
                                                    v636 = pcchLength;
                                                    if ( pcchLength >> 3 )
                                                    {
                                                      v637 = HIDWORD(v738);
                                                      v638 = pcchLength >> 3;
                                                      v639 = WORD1(v738);
                                                      v640 = v754;
                                                      v641 = v729;
                                                      v642 = WORD2(v738);
                                                      LODWORD(v730) = 24670;
                                                      v643 = (unsigned __int8 *)v750;
                                                      v734 = WORD2(v738);
                                                      v753 = 0;
                                                      do
                                                      {
                                                        v644 = *v643;
                                                        v645 = v643[1];
                                                        v646 = v643[4];
                                                        v643 += 8;
                                                        v647 = *(v643 - 5)
                                                             | ((*(v643 - 6) | (((v644 << 8) | v645) << 8)) << 8);
                                                        v648 = v629 ^ v647;
                                                        v649 = *(v643 - 1)
                                                             | ((*(v643 - 2) | ((*(v643 - 3) | (v646 << 8)) << 8)) << 8);
                                                        v650 = v637 ^ v629 ^ v647 ^ v635 ^ v649 ^ 0xAB69605E;
                                                        v651 = v648
                                                             ^ (__ROR4__(v650, 22)
                                                              + v642 * __ROR4__(v650 + 1419157410, 27));
                                                        v652 = v650
                                                             ^ (v639 * __ROR4__(v651 + v637, 9) - __ROR4__(v651, 30));
                                                        v653 = v651 ^ (v730 * (v652 - v642) - (v652 >> 13));
                                                        v654 = v652
                                                             ^ (HIWORD(v738) * __ROR4__(v653 ^ v639, 26)
                                                              - __ROR4__(v653, 30));
                                                        v655 = v653 ^ (v637 - (v654 ^ 0xAB69605E));
                                                        v656 = v654 ^ (v639 * (v642 ^ v655)) ^ __ROR4__(v655, 6);
                                                        v657 = v655
                                                             ^ (__ROR4__(v656, 30) + v730 * __ROR4__(v656 + v637, 15));
                                                        v658 = v656
                                                             ^ (HIWORD(v738) * __ROR4__(v657 + 1419157410, 14)
                                                              - __ROR4__(v657, 24));
                                                        v659 = v657
                                                             ^ __ROR4__(v658, 10)
                                                             ^ (v734 * __ROR4__(v658 ^ 0xAB69605E, 12));
                                                        v660 = v659
                                                             ^ (HIWORD(v738)
                                                              * (v730
                                                               + __ROR4__(
                                                                   ~(v658
                                                                   ^ (v659 >> 10)
                                                                   ^ (WORD1(v738) * (HIWORD(v738) ^ v659))),
                                                                   5)));
                                                        v661 = v658
                                                             ^ (v659 >> 10)
                                                             ^ (WORD1(v738) * (HIWORD(v738) ^ v659))
                                                             ^ (v660 - HIWORD(v738))
                                                             ^ 0xAB69605E;
                                                        v662 = v660
                                                             ^ ((v661 >> 2) + v734 * __ROR4__(HIWORD(v738) ^ v661, 30));
                                                        v663 = v661
                                                             ^ (__ROR4__(v662, 25)
                                                              + WORD1(v738) * __ROR4__(v662 - v637, 6));
                                                        v664 = v662 ^ (v730 * (v734 ^ v663) + __ROR4__(v663, 9));
                                                        v665 = v663
                                                             ^ (__ROR4__(v664, 25)
                                                              + HIWORD(v738) * __ROR4__(v664 ^ WORD1(v738), 27));
                                                        v642 = v734;
                                                        v666 = v637 ^ v664 ^ v665 ^ 0xAB69605E;
                                                        v667 = v665 ^ (v734 * (__ROR4__(v666, 3) - WORD1(v738)));
                                                        v668 = v666
                                                             ^ (v730 * __ROR4__(v667 - v637, 1) - __ROR4__(v667, 6));
                                                        v669 = v667
                                                             ^ (__ROR4__(v668, 18)
                                                              + HIWORD(v738) * __ROR4__(v668 - 1419157410, 29));
                                                        v670 = v668
                                                             ^ (v734 * __ROR4__(v669 - 1419157410, 17)
                                                              - __ROR4__(v669, 14));
                                                        v639 = WORD1(v738);
                                                        v671 = v669 ^ (v670 >> 3) ^ (WORD1(v738) * (v730 ^ v670));
                                                        v672 = v641
                                                             ^ __ROR4__(v671, 30)
                                                             ^ (v730 * __ROR4__(v637 ^ v671, 28));
                                                        v641 = v647;
                                                        v629 = v670 ^ v672;
                                                        v673 = v756;
                                                        v640[3] = v629;
                                                        v635 = v671 ^ v673;
                                                        v640[7] = v635;
                                                        v640[2] = __ROR4__(v629, 8);
                                                        v640[6] = __ROR4__(v635, 8);
                                                        v640[1] = __ROR4__(v629, 16);
                                                        v640[5] = __ROR4__(v635, 16);
                                                        *v640 = __ROR4__(v629, 24);
                                                        v640[4] = __ROR4__(v635, 24);
                                                        v640 += 8;
                                                        v756 = v649;
                                                        ++v753;
                                                      }
                                                      while ( v753 < v638 );
                                                      v620 = v733;
                                                      v10 = dwBytes;
                                                      v51 = v741;
                                                      v47 = v752;
                                                      v459 = (unsigned int *)v739;
                                                      v460 = (const void **)psz;
                                                      v619 = v736;
                                                      v636 = pcchLength;
                                                    }
                                                    for ( ii = 0; ii < v636; ++ii )
                                                      v620 ^= *((_BYTE *)v619 + ii);
                                                    if ( v620 != *(_QWORD *)((char *)Src + v636) )
                                                    {
                                                      MemoryFree(v619);
LABEL_770:
                                                      v735 = -805306367;
                                                      v563 = 0;
                                                      goto LABEL_815;
                                                    }
                                                    v756 = 0;
                                                    v732 = (size_t)v619;
                                                    if ( (unsigned int)v636 < 4 )
                                                      goto LABEL_772;
                                                    v675 = RtlULongLongAdd(v619, 4, &v732);
                                                    if ( v675 >= 0 )
                                                    {
                                                      v675 = RtlUIntAdd(0, 4, &v756);
                                                      if ( v675 >= 0 )
                                                      {
                                                        if ( (unsigned int)v636 - v756 < 4 )
                                                          goto LABEL_807;
                                                        v679 = *(_DWORD *)v732;
                                                        v734 = *(_DWORD *)v732;
                                                        v675 = RtlULongLongAdd(v732, 4, &v732);
                                                        if ( v675 < 0 )
                                                          goto LABEL_808;
                                                        v675 = RtlUIntAdd(v756, 4, &v756);
                                                        if ( v675 < 0 )
                                                          goto LABEL_808;
                                                        if ( (unsigned int)v636 - v756 < v679 )
                                                          goto LABEL_807;
                                                        v675 = RtlUIntAdd(v756, v679, &v756);
                                                        if ( v675 >= 0 )
                                                        {
                                                          v680 = (const void *)v732;
                                                          pcchLength = v734;
                                                          if ( (unsigned __int64)v678 + (unsigned int)v636 >= v734 + v732
                                                            && (unsigned __int64)v678
                                                             + (unsigned int)v636
                                                             - (unsigned __int64)v734
                                                             - v732 < 8 )
                                                          {
                                                            v747 = *v678;
                                                            v750 = 0;
                                                            v754 = 0;
                                                            v753 = 0;
                                                            v729 = 0;
                                                            if ( v732 )
                                                            {
                                                              v681 = (unsigned int *)v732;
                                                              v675 = RtlULongLongAdd(v732, pcchLength, &v750);
                                                              v735 = v675;
                                                              v736 = v682;
                                                              v740 = v683;
                                                              v731 = v684;
                                                              if ( v675 >= 0 )
                                                              {
                                                                v685 = v750;
                                                                v686 = 4;
                                                                while ( (unsigned __int64)v681 < v685 )
                                                                {
                                                                  v675 = RtlULongLongAdd(v681, v686, &v754);
                                                                  if ( v675 < 0 )
                                                                    goto LABEL_803;
                                                                  if ( (unsigned __int64)v754 > v687 )
                                                                    goto LABEL_793;
                                                                  v689 = *v681;
                                                                  HIDWORD(v730) = 0;
                                                                  v675 = RtlUIntAdd(v688, v689, (char *)&v730 + 4);
                                                                  if ( v675 < 0 )
                                                                    goto LABEL_809;
                                                                  v675 = RtlULongLongAdd(v681, HIDWORD(v730), &v753);
                                                                  v735 = v675;
                                                                  if ( v675 < 0 )
                                                                    goto LABEL_803;
                                                                  v681 = (unsigned int *)v753;
                                                                  if ( v753 > v685 )
                                                                    goto LABEL_793;
                                                                  ++v729;
                                                                }
                                                                if ( v681 == (unsigned int *)v685 )
                                                                  goto LABEL_795;
LABEL_793:
                                                                v675 = -1073741811;
                                                                goto LABEL_809;
                                                              }
LABEL_803:
                                                              v693 = v744;
                                                            }
                                                            else
                                                            {
                                                              v675 = 0;
                                                              v736 = v678;
                                                              v735 = 0;
                                                              v740 = v677;
                                                              v731 = v676;
LABEL_795:
                                                              v690 = 0;
                                                              v750 = 0;
                                                              if ( v734 )
                                                              {
                                                                v691 = GetProcessHeap();
                                                                v692 = pcchLength;
                                                                v750 = (SIZE_T)HeapAlloc(v691, 8u, pcchLength);
                                                                v690 = (void *)v750;
                                                                if ( !v750 )
                                                                {
                                                                  v675 = -1073741801;
                                                                  goto LABEL_809;
                                                                }
                                                                v675 = 0;
                                                                v735 = 0;
                                                              }
                                                              else
                                                              {
                                                                v692 = pcchLength;
                                                              }
                                                              if ( v680 )
                                                              {
                                                                memcpy_0(v690, v680, v692);
                                                                v675 = v735;
                                                              }
                                                              v746 = v750;
                                                              v693 = v729;
                                                              v744 = v729;
                                                            }
                                                            if ( v675 < 0 || v747 == v693 )
                                                              goto LABEL_809;
LABEL_772:
                                                            v675 = -1073741762;
LABEL_809:
                                                            LastError = v675 | 0x10000000;
                                                            goto LABEL_810;
                                                          }
LABEL_807:
                                                          v675 = -1073741762;
                                                        }
                                                      }
                                                    }
LABEL_808:
                                                    v736 = v678;
                                                    v731 = v676;
                                                    v740 = v677;
                                                    goto LABEL_809;
                                                  }
                                                }
                                              }
                                            }
                                          }
                                        }
                                      }
                                    }
                                  }
                                }
                                v458 = (void **)v740;
                                goto LABEL_737;
                              }
                            }
                          }
                        }
                      }
                    }
                    v731 = v518;
                    v556 = GetProcessHeap();
                    HeapFree(v556, 0, v738);
                  }
                  v555 = v730;
                  goto LABEL_636;
                }
LABEL_606:
                v460 = (const void **)v732;
                v732 = 0;
                goto LABEL_607;
              }
            }
          }
        }
      }
LABEL_855:
      v48 = (_DWORD *)v746;
      goto LABEL_856;
    }
    HIDWORD(lpMem[0]) = HIDWORD(dwBytes);
    v34 = HIDWORD(dwBytes);
    v35 = GetProcessHeap();
    v36 = HeapAlloc(v35, 8u, v34);
    if ( !v36 )
    {
      v10 = -1073741801;
LABEL_27:
      LODWORD(dwBytes) = v10;
LABEL_28:
      v6 = v738;
      goto LABEL_39;
    }
    lpMem[1] = v36;
    LODWORD(v743) = 0;
    v742 = 0;
    LODWORD(v730) = 0;
    LODWORD(lpMem[0]) = 0;
    pcchLength = (size_t)v36;
    LODWORD(dwBytes) = RtlULongLongAdd(v36, 4, &v743);
    v10 = dwBytes;
    if ( (dwBytes & 0x80000000) != 0LL )
      goto LABEL_35;
    if ( v37 + 2 <= (_DWORD *)((char *)lpMem[1] + HIDWORD(lpMem[0])) )
    {
      v39 = v743;
      *v37 = 4;
      *v39 = 0;
      v40 = 0;
      v41 = LODWORD(lpMem[0]) + 1;
      LODWORD(v743) = 0;
      ++LODWORD(lpMem[0]);
      v742 = 0;
      if ( v9 )
      {
        if ( !v38 )
          goto LABEL_33;
      }
      else if ( v38 )
      {
LABEL_33:
        v10 = -1073741811;
LABEL_34:
        LODWORD(dwBytes) = v10;
LABEL_35:
        v6 = v738;
        goto LABEL_36;
      }
      v69 = (unsigned int *)lpMem[1];
      if ( lpMem[1] )
      {
        pcchLength = (size_t)lpMem[1];
        while ( 1 )
        {
          v734 = v40;
          if ( v40 >= v41 )
            break;
          v70 = *v69;
          v729 = 0;
          LODWORD(dwBytes) = RtlUIntAdd(4, v70, &v729);
          v10 = dwBytes;
          if ( (dwBytes & 0x80000000) != 0LL )
            goto LABEL_35;
          LODWORD(dwBytes) = RtlULongLongAdd(v71, v729, &pcchLength);
          v10 = dwBytes;
          if ( (dwBytes & 0x80000000) != 0LL )
            goto LABEL_35;
          v69 = (unsigned int *)pcchLength;
          v40 = v734 + 1;
        }
        LODWORD(dwBytes) = RtlULongLongAdd(v69, 4, &v743);
        v10 = dwBytes;
        if ( (dwBytes & 0x80000000) != 0LL )
          goto LABEL_35;
        if ( (char *)v72 + v73 + 4 > (char *)lpMem[1] + HIDWORD(lpMem[0]) )
          goto LABEL_73;
        *v72 = v73;
        if ( v9 )
          memcpy_0(v743, v9, v73);
      }
      else
      {
        v729 = 0;
        LODWORD(dwBytes) = RtlUIntAdd(4, v38, &v729);
        v10 = dwBytes;
        if ( (dwBytes & 0x80000000) != 0LL )
          goto LABEL_35;
        LODWORD(dwBytes) = RtlUIntAdd(HIDWORD(lpMem[0]), v729, (char *)lpMem + 4);
        v10 = dwBytes;
        if ( (dwBytes & 0x80000000) != 0LL )
          goto LABEL_35;
      }
      v74 = LODWORD(lpMem[0]) + 1;
      LODWORD(v743) = 0;
      ++LODWORD(lpMem[0]);
      v742 = 0;
      if ( !v11 )
        goto LABEL_33;
      v75 = (unsigned int *)lpMem[1];
      if ( lpMem[1] )
      {
        pcchLength = (size_t)lpMem[1];
        for ( jj = 0; jj < v74; jj = v79 + 1 )
        {
          v77 = *v75;
          v729 = 0;
          LODWORD(dwBytes) = RtlUIntAdd(4, v77, &v729);
          v10 = dwBytes;
          if ( (dwBytes & 0x80000000) != 0LL )
            goto LABEL_35;
          LODWORD(dwBytes) = RtlULongLongAdd(v78, v729, &pcchLength);
          v10 = dwBytes;
          if ( (dwBytes & 0x80000000) != 0LL )
            goto LABEL_35;
          v75 = (unsigned int *)pcchLength;
        }
        LODWORD(dwBytes) = RtlULongLongAdd(v75, 4, &v743);
        v10 = dwBytes;
        if ( (dwBytes & 0x80000000) != 0LL )
          goto LABEL_35;
        if ( v80 + 3 > (_DWORD *)((char *)lpMem[1] + HIDWORD(lpMem[0])) )
          goto LABEL_73;
        *v80 = 8;
        memcpy_0(v743, v11, 8u);
      }
      else
      {
        v729 = 0;
        LODWORD(dwBytes) = RtlUIntAdd(4, 8, &v729);
        v10 = dwBytes;
        if ( (dwBytes & 0x80000000) != 0LL )
          goto LABEL_35;
        LODWORD(dwBytes) = RtlUIntAdd(HIDWORD(lpMem[0]), v729, (char *)lpMem + 4);
        v10 = dwBytes;
        if ( (dwBytes & 0x80000000) != 0LL )
          goto LABEL_35;
      }
      v81 = (unsigned int *)lpMem[1];
      v82 = LODWORD(lpMem[0]) + 1;
      LODWORD(v743) = 0;
      ++LODWORD(lpMem[0]);
      v742 = 0;
      if ( lpMem[1] )
      {
        pcchLength = (size_t)lpMem[1];
        for ( kk = 0; kk < v82; kk = v87 + 1 )
        {
          v85 = *v81;
          v729 = 0;
          LODWORD(dwBytes) = RtlUIntAdd(4, v85, &v729);
          v10 = dwBytes;
          if ( (dwBytes & 0x80000000) != 0LL )
            goto LABEL_35;
          LODWORD(dwBytes) = RtlULongLongAdd(v86, v729, &pcchLength);
          v10 = dwBytes;
          if ( (dwBytes & 0x80000000) != 0LL )
            goto LABEL_35;
          v81 = (unsigned int *)pcchLength;
        }
        LODWORD(dwBytes) = RtlULongLongAdd(v81, 4, &v743);
        v10 = dwBytes;
        if ( (dwBytes & 0x80000000) != 0LL )
          goto LABEL_35;
        if ( v88 + 3 > (_DWORD *)((char *)lpMem[1] + HIDWORD(lpMem[0])) )
          goto LABEL_73;
        v89 = (SIZE_T *)v743;
        v90 = v750;
        *v88 = 8;
        *v89 = v90;
      }
      else
      {
        v729 = 0;
        LODWORD(dwBytes) = RtlUIntAdd(4, 8, &v729);
        v10 = dwBytes;
        if ( (dwBytes & 0x80000000) != 0LL )
          goto LABEL_35;
        LODWORD(dwBytes) = RtlUIntAdd(HIDWORD(lpMem[0]), v729, (char *)lpMem + 4);
        v10 = dwBytes;
        if ( (dwBytes & 0x80000000) != 0LL )
          goto LABEL_35;
      }
      ++LODWORD(lpMem[0]);
      v732 = 0;
      if ( StringCchLengthW(psz, v83, &v732) < 0 )
      {
        v10 = -1073741762;
        goto LABEL_34;
      }
      LODWORD(dwBytes) = RtlULongLongAdd(v732, 1, &v732);
      v10 = dwBytes;
      if ( (dwBytes & 0x80000000) != 0LL )
        goto LABEL_35;
      LODWORD(v743) = 0;
      v742 = 0;
      if ( !(2 * (_DWORD)v732) )
        goto LABEL_33;
      v92 = (unsigned int *)lpMem[1];
      if ( lpMem[1] )
      {
        pcchLength = (size_t)lpMem[1];
        for ( mm = 0; mm < v91; ++mm )
        {
          v94 = *v92;
          v729 = 0;
          LODWORD(dwBytes) = RtlUIntAdd(4, v94, &v729);
          v10 = dwBytes;
          if ( (dwBytes & 0x80000000) != 0LL )
            goto LABEL_35;
          LODWORD(dwBytes) = RtlULongLongAdd(v95, v729, &pcchLength);
          v10 = dwBytes;
          if ( (dwBytes & 0x80000000) != 0LL )
            goto LABEL_35;
          v92 = (unsigned int *)pcchLength;
        }
        LODWORD(dwBytes) = RtlULongLongAdd(v92, 4, &v743);
        v10 = dwBytes;
        if ( (dwBytes & 0x80000000) != 0LL )
          goto LABEL_35;
        if ( (char *)v96 + v97 + 4 > (char *)lpMem[1] + HIDWORD(lpMem[0]) )
          goto LABEL_73;
        v98 = psz;
        v99 = v743;
        *v96 = v97;
        memcpy_0(v99, v98, (unsigned int)v97);
      }
      else
      {
        v729 = 0;
        LODWORD(dwBytes) = RtlUIntAdd(4, (unsigned int)(2 * v732), &v729);
        v10 = dwBytes;
        if ( (dwBytes & 0x80000000) != 0LL )
          goto LABEL_35;
        LODWORD(dwBytes) = RtlUIntAdd(HIDWORD(lpMem[0]), v729, (char *)lpMem + 4);
        v10 = dwBytes;
        if ( (dwBytes & 0x80000000) != 0LL )
          goto LABEL_35;
      }
      v100 = (unsigned int *)lpMem[1];
      v101 = LODWORD(lpMem[0]) + 1;
      LODWORD(v743) = 0;
      ++LODWORD(lpMem[0]);
      v742 = 0;
      if ( lpMem[1] )
      {
        pcchLength = (size_t)lpMem[1];
        for ( nn = 0; nn < v101; nn = v105 + 1 )
        {
          v103 = *v100;
          v729 = 0;
          LODWORD(dwBytes) = RtlUIntAdd(4, v103, &v729);
          v10 = dwBytes;
          if ( (dwBytes & 0x80000000) != 0LL )
            goto LABEL_35;
          LODWORD(dwBytes) = RtlULongLongAdd(v104, v729, &pcchLength);
          v10 = dwBytes;
          if ( (dwBytes & 0x80000000) != 0LL )
            goto LABEL_35;
          v100 = (unsigned int *)pcchLength;
        }
        LODWORD(dwBytes) = RtlULongLongAdd(v100, 4, &v743);
        v10 = dwBytes;
        if ( (dwBytes & 0x80000000) != 0LL )
          goto LABEL_35;
        if ( v106 + 2 > (_DWORD *)((char *)lpMem[1] + HIDWORD(lpMem[0])) )
          goto LABEL_73;
        v107 = v743;
        *v106 = 4;
        *v107 = 0;
      }
      else
      {
        v729 = 0;
        LODWORD(dwBytes) = RtlUIntAdd(4, 4, &v729);
        v10 = dwBytes;
        if ( (dwBytes & 0x80000000) != 0LL )
          goto LABEL_35;
        LODWORD(dwBytes) = RtlUIntAdd(HIDWORD(lpMem[0]), v729, (char *)lpMem + 4);
        v10 = dwBytes;
        if ( (dwBytes & 0x80000000) != 0LL )
          goto LABEL_35;
      }
      v108 = (unsigned int *)lpMem[1];
      v109 = LODWORD(lpMem[0]) + 1;
      LODWORD(v743) = 0;
      ++LODWORD(lpMem[0]);
      v742 = 0;
      if ( !lpMem[1] )
      {
        v729 = 0;
        LODWORD(dwBytes) = RtlUIntAdd(4, 4, &v729);
        v10 = dwBytes;
        if ( (dwBytes & 0x80000000) != 0LL )
          goto LABEL_35;
        LODWORD(dwBytes) = RtlUIntAdd(HIDWORD(lpMem[0]), v729, (char *)lpMem + 4);
        v10 = dwBytes;
        if ( (dwBytes & 0x80000000) != 0LL )
          goto LABEL_35;
LABEL_141:
        ++LODWORD(lpMem[0]);
        v729 = 0;
        LODWORD(dwBytes) = RtlUIntAdd(4, 4, &v729);
        v10 = dwBytes;
        if ( (dwBytes & 0x80000000) != 0LL )
          goto LABEL_35;
        HIDWORD(dwBytes) = v729;
        v729 = 0;
        LODWORD(dwBytes) = RtlUIntAdd(v116, 8, &v729);
        v10 = dwBytes;
        if ( (dwBytes & 0x80000000) != 0LL )
          goto LABEL_35;
        LODWORD(dwBytes) = RtlUIntAdd(v117, v729, (char *)&dwBytes + 4);
        v10 = dwBytes;
        if ( (dwBytes & 0x80000000) != 0LL )
          goto LABEL_35;
        v729 = 0;
        LODWORD(dwBytes) = RtlUIntAdd(4, 4, &v729);
        v10 = dwBytes;
        if ( (dwBytes & 0x80000000) != 0LL )
          goto LABEL_35;
        LODWORD(dwBytes) = RtlUIntAdd(HIDWORD(dwBytes), v729, (char *)&dwBytes + 4);
        v10 = dwBytes;
        if ( (dwBytes & 0x80000000) != 0LL )
          goto LABEL_35;
        v729 = 0;
        LODWORD(dwBytes) = RtlUIntAdd(4, 4, &v729);
        v10 = dwBytes;
        if ( (dwBytes & 0x80000000) != 0LL )
          goto LABEL_35;
        LODWORD(dwBytes) = RtlUIntAdd(HIDWORD(dwBytes), v729, (char *)&dwBytes + 4);
        v10 = dwBytes;
        if ( (dwBytes & 0x80000000) != 0LL )
          goto LABEL_35;
        v729 = 0;
        LODWORD(dwBytes) = RtlUIntAdd(4, 4, &v729);
        v10 = dwBytes;
        if ( (dwBytes & 0x80000000) != 0LL )
          goto LABEL_35;
        LODWORD(dwBytes) = RtlUIntAdd(HIDWORD(dwBytes), v729, (char *)&dwBytes + 4);
        v10 = dwBytes;
        if ( (dwBytes & 0x80000000) != 0LL )
          goto LABEL_35;
        v729 = 0;
        LODWORD(dwBytes) = RtlUIntAdd(4, 4, &v729);
        v10 = dwBytes;
        if ( (dwBytes & 0x80000000) != 0LL )
          goto LABEL_35;
        LODWORD(dwBytes) = RtlUIntAdd(HIDWORD(dwBytes), v729, (char *)&dwBytes + 4);
        v10 = dwBytes;
        if ( (dwBytes & 0x80000000) != 0LL )
          goto LABEL_35;
        v729 = 0;
        v731 = 0;
        v754 = (void *)__rdtsc();
        v761 = 8;
        HIDWORD(v730) = 0;
        v119 = RtlUIntAdd(8, HIDWORD(lpMem[0]), &v761);
        if ( v119 < 0 )
        {
          v741 = v11;
          v752 = v9;
        }
        else
        {
          v120 = (v761 + 7) & 0xFFFFFFF8;
          if ( v120 < v761 )
          {
            v10 = -805306219;
            goto LABEL_27;
          }
          v761 = (v761 + 7) & 0xFFFFFFF8;
          v121 = v120;
          v122 = GetProcessHeap();
          v123 = HeapAlloc(v122, 8u, v121);
          if ( !v123 )
          {
            v10 = -805306345;
            LODWORD(dwBytes) = -805306345;
            goto LABEL_248;
          }
          v752 = v9;
          v741 = v11;
          v732 = (size_t)v123;
          *v123 = lpMem[0];
          v119 = RtlULongLongAdd(v123, 4, &v732);
          if ( v119 < 0
            || (v126 = v732, *(_DWORD *)v732 = HIDWORD(lpMem[0]), v119 = RtlULongLongAdd(v126, v125, &v732), v119 < 0) )
          {
            v752 = v9;
            v741 = v11;
            HIDWORD(dwBytes) = v124;
            v127 = GetProcessHeap();
            HeapFree(v127, 0, v123);
            v118 = HIDWORD(v730);
          }
          else
          {
            *(_QWORD *)((char *)v123 + v761 - 8) = v754;
            memcpy_0((void *)v732, lpMem[1], HIDWORD(lpMem[0]));
            v118 = v761;
            v731 = v123;
          }
        }
        v128 = 0;
        pcchLength = 0;
        v129 = 0;
        v739 = 0;
        v10 = v119 | 0x10000000;
        v740 = 0;
        LODWORD(dwBytes) = v10;
        v751 = 0;
        if ( v10 < 0 )
          goto LABEL_223;
        v130 = (wchar_t *)v731;
        if ( !v731 )
        {
          v10 = -805306355;
          goto LABEL_27;
        }
        v754 = (void *)v118;
        if ( !v118 || (Size = v118 + 8LL, (Src = MemoryAlloc(Size)) == 0) )
        {
          v10 = -805306367;
          LODWORD(dwBytes) = -805306367;
          goto LABEL_225;
        }
        v131 = (unsigned __int64)v754;
        v132 = 0;
        v133 = 0;
        v732 = 0;
        v733 = 0;
        if ( v754 )
        {
          do
            v132 ^= *((_BYTE *)v130 + v133++);
          while ( v133 < (unsigned __int64)v754 );
          v733 = v132;
        }
        v765 = Src;
        v134 = v130;
        v737 = (LPVOID)0xC81ECB17B1B54A58LL;
        psz = v130;
        v135 = (unsigned __int8)v754 & 7;
        if ( ((unsigned __int8)v754 & 7) != 0 )
        {
          v136 = 0;
          LODWORD(dwBytes) = 0;
          v744 = 0;
          v137 = 0;
          v138 = 0;
          do
          {
            v139 = *(unsigned __int8 *)v134;
            v134 = (STRSAFE_PCNZWCH)((char *)v134 + 1);
            v734 = 8 * v136;
            if ( v136 >= 4 )
              v137 |= v139 << (56 - v734);
            else
              v138 |= v139 << (24 - v734);
            ++v136;
          }
          while ( (int)v136 < v135 );
          v744 = v138;
          LODWORD(dwBytes) = v137;
          psz = v134;
          v731 = v130;
          v741 = v11;
          v752 = v9;
          v734 = 0;
          v140 = v137 ^ 0x42F6B18D;
          v141 = v138 ^ 0xB17A307A;
          v142 = v138 ^ 0xB17A307A;
          v143 = v137 ^ 0x42F6B18D;
          if ( ((unsigned __int8)v754 & 7) != 0 )
          {
            v144 = v765;
            do
            {
              v753 = (SIZE_T)(v144 + 1);
              if ( v734 >= 4 )
              {
                v143 = __ROR4__(v143, 24);
                v145 = v143;
              }
              else
              {
                v142 = __ROR4__(v142, 24);
                v145 = v142;
              }
              ++v734;
              *v144 = v145;
              v144 = (_BYTE *)v753;
            }
            while ( (int)v734 < v135 );
            v765 = (LPVOID)v753;
          }
          if ( (unsigned int)v135 <= 4 )
          {
            v146 = 0;
            if ( (unsigned int)v135 < 4 )
              v141 = v141 >> (8 * (4 - v135)) << (8 * (4 - v135));
          }
          else
          {
            v146 = v140 >> (8 * (8 - v135)) << (8 * (8 - v135));
          }
          v134 = psz;
        }
        else
        {
          v141 = 0;
          v744 = 0;
          v146 = -1;
          LODWORD(dwBytes) = 0;
        }
        if ( v131 >> 3 )
        {
          v147 = WORD2(v737);
          v148 = v131 >> 3;
          v149 = v765;
          v150 = dwBytes;
          v734 = 19032;
          v747 = WORD1(v737);
          HIDWORD(v730) = HIWORD(v737);
          v753 = 0;
          v759 = HIDWORD(v737) ^ 0xB1B54A58;
          v151 = HIDWORD(v737) ^ 0xB1B54A58;
          v152 = v744;
          do
          {
            v153 = *((unsigned __int8 *)v134 + 3)
                 | ((*((unsigned __int8 *)v134 + 2)
                   | (((*(unsigned __int8 *)v134 << 8) | *((unsigned __int8 *)v134 + 1)) << 8)) << 8);
            v154 = *((unsigned __int8 *)psz + 7)
                 | ((*((unsigned __int8 *)psz + 6)
                   | ((*((unsigned __int8 *)psz + 5) | (*((unsigned __int8 *)v134 + 4) << 8)) << 8)) << 8);
            psz += 4;
            v155 = v146 ^ v154;
            v156 = v141 ^ v153 ^ HIDWORD(v737) ^ ((v146 ^ v154) - v734);
            v157 = v155 ^ (__ROR4__(v156, 7) + WORD1(v737) * __ROR4__(v156 ^ HIDWORD(v737), 15));
            v158 = v156 ^ (v147 * __ROR4__(v157 - 1313519016, 9) - __ROR4__(v157, 10));
            v159 = v157 ^ (__ROR4__(v158, 27) + HIWORD(v737) * __ROR4__(v147 ^ v158, 28));
            v160 = v158 ^ (HIDWORD(v737) - (v159 ^ 0xB1B54A58));
            v161 = v159 ^ (WORD1(v737) * (v160 - v734) - (v160 >> 6));
            v162 = v160 ^ (v734 * (v147 ^ __ROR4__(v161, 15)));
            v163 = v161 ^ (v147 * (HIWORD(v737) + __ROR4__(~v162, 3)));
            v164 = v162 ^ (v163 - HIDWORD(v737) - v734);
            v165 = v163 ^ (v747 * (HIDWORD(v730) ^ v164)) ^ __ROR4__(v164, 10);
            v166 = v164 ^ __ROR4__(v165, 3) ^ (v147 * __ROR4__(v734 ^ v165, 26));
            v167 = v165 ^ (v734 * (__ROR4__(v166, 15) - HIWORD(v737)));
            v168 = v166
                 ^ (v734 * (HIDWORD(v730) ^ v167))
                 ^ ((v167 ^ (v167 >> 14)) >> 1)
                 ^ (v734 * ((8 * (v167 - v147)) | ((v167 - v147) >> 29)));
            v169 = v167 ^ (WORD1(v737) * (v168 - v147) - (v168 >> 13));
            v170 = v168 ^ __ROR4__(v169, 11) ^ (v147 * __ROR4__(-1313519016 - v169, 9));
            v171 = v169 ^ (v170 + 1313519016 - HIWORD(v737));
            v172 = v170 ^ (v734 * (v171 ^ WORD1(v737)) - __ROR4__(v171, 7));
            v173 = v171 ^ (WORD1(v737) * __ROR4__(HIWORD(v737) ^ v172, 28) - __ROR4__(v172, 16));
            v174 = v172 ^ (__ROR4__(v173, 4) + v147 * __ROR4__(-1313519016 - v173, 10));
            v175 = v173 ^ __ROR4__(v174, 9) ^ (HIWORD(v737) * __ROR4__(v174 + 1313519016, 4));
            v176 = v174 ^ (v734 * __ROR4__(v175 ^ HIDWORD(v737), 24) - __ROR4__(v175, 30));
            v177 = v175 ^ (WORD1(v737) * __ROR4__(HIDWORD(v737) - v176, 11) - __ROR4__(v176, 12));
            v178 = v176 ^ (v177 >> 8) ^ (v147 * (v177 ^ WORD1(v737)));
            v179 = v151 ^ v178;
            v141 = v152 ^ v178;
            v149[3] = v141;
            v146 = v177 ^ v150 ^ v179;
            v149[7] = v146;
            v150 = v154;
            v134 = psz;
            v152 = v153;
            v149[2] = __ROR4__(v141, 8);
            v149[6] = __ROR4__(v146, 8);
            v149[1] = __ROR4__(v141, 16);
            v149[5] = __ROR4__(v146, 16);
            *v149 = __ROR4__(v141, 24);
            v149[4] = __ROR4__(v146, 24);
            v149 += 8;
            ++v753;
          }
          while ( v753 < v148 );
          v128 = (unsigned int *)v739;
          v132 = v733;
          v129 = (unsigned int *)v739;
          v9 = v752;
          v11 = v741;
          v130 = (wchar_t *)v731;
          v131 = (unsigned __int64)v754;
        }
        *(_QWORD *)((char *)Src + v131) = v132;
        v180 = GetProcessHeap();
        v181 = (wchar_t *)HeapAlloc(v180, 8u, 0x30u);
        psz = v181;
        if ( v181 )
        {
          *(_DWORD *)v181 = Size;
          v183 = GetProcessHeap();
          v184 = HeapAlloc(v183, 8u, (unsigned int)Size);
          if ( !v184 )
            goto LABEL_198;
          v731 = v130;
          v185 = psz;
          *((_QWORD *)psz + 1) = v184;
          memcpy_0(v184, Src, (unsigned int)Size);
          *((_DWORD *)v185 + 4) = 160;
          v186 = GetProcessHeap();
          v187 = HeapAlloc(v186, 8u, 0xA0u);
          if ( !v187 )
            goto LABEL_198;
          *((_QWORD *)v185 + 3) = v187;
          *v187 = xmmword_180069C60;
          v187[1] = xmmword_180069C70;
          v187[2] = xmmword_180069C80;
          v187[3] = xmmword_180069C90;
          v187[4] = xmmword_180069CA0;
          v187[5] = xmmword_180069CB0;
          v187[6] = xmmword_180069CC0;
          v187[7] = xmmword_180069CD0;
          v187[8] = xmmword_180069CE0;
          v187[9] = xmmword_180069CF0;
          *((_DWORD *)v185 + 8) = 8;
          v188 = GetProcessHeap();
          v189 = HeapAlloc(v188, 8u, 8u);
          if ( v189 )
          {
            *((_QWORD *)v185 + 5) = v189;
            *v189 = qword_180069D00;
            v732 = (size_t)v185;
            v182 = 0;
            v129 = (unsigned int *)v732;
            v732 = 0;
          }
          else
          {
LABEL_198:
            v182 = -1073741801;
            v190 = psz;
            v742 = (LPVOID)*((_QWORD *)psz + 1);
            if ( v742 )
            {
              v191 = GetProcessHeap();
              HeapFree(v191, 0, v742);
              v190 = psz;
              *((_QWORD *)psz + 1) = 0;
            }
            v742 = (LPVOID)*((_QWORD *)v190 + 3);
            if ( v742 )
            {
              v192 = GetProcessHeap();
              HeapFree(v192, 0, v742);
              v190 = psz;
              *((_QWORD *)psz + 3) = 0;
            }
            v742 = (LPVOID)*((_QWORD *)v190 + 5);
            if ( v742 )
            {
              v193 = GetProcessHeap();
              HeapFree(v193, 0, v742);
              *((_QWORD *)psz + 5) = 0;
            }
            v194 = GetProcessHeap();
            HeapFree(v194, 0, (LPVOID)psz);
          }
        }
        else
        {
          v182 = -1073741801;
        }
        v195 = GetProcessHeap();
        HeapFree(v195, 0, Src);
        v196 = v732;
        if ( v732 )
        {
          v742 = *(LPVOID *)(v732 + 8);
          if ( v742 )
          {
            v197 = GetProcessHeap();
            HeapFree(v197, 0, v742);
            v196 = v732;
            *(_QWORD *)(v732 + 8) = 0;
          }
          v742 = *(LPVOID *)(v196 + 24);
          if ( v742 )
          {
            v198 = GetProcessHeap();
            HeapFree(v198, 0, v742);
            v196 = v732;
            *(_QWORD *)(v732 + 24) = 0;
          }
          v742 = *(LPVOID *)(v196 + 40);
          if ( v742 )
          {
            v199 = GetProcessHeap();
            HeapFree(v199, 0, v742);
            *(_QWORD *)(v732 + 40) = 0;
          }
          v200 = GetProcessHeap();
          HeapFree(v200, 0, (LPVOID)v732);
        }
        v10 = v182 | 0x10000000;
        LODWORD(dwBytes) = v10;
        if ( v10 < 0 )
        {
          v211 = v731;
LABEL_224:
          if ( !v211 )
          {
LABEL_226:
            if ( v129 )
            {
              v742 = (LPVOID)*((_QWORD *)v129 + 1);
              if ( v742 )
              {
                v213 = GetProcessHeap();
                HeapFree(v213, 0, v742);
                *((_QWORD *)v129 + 1) = 0;
              }
              v742 = (LPVOID)*((_QWORD *)v129 + 3);
              if ( v742 )
              {
                v214 = GetProcessHeap();
                HeapFree(v214, 0, v742);
                *((_QWORD *)v129 + 3) = 0;
              }
              v742 = (LPVOID)*((_QWORD *)v129 + 5);
              if ( v742 )
              {
                v215 = GetProcessHeap();
                HeapFree(v215, 0, v742);
                *((_QWORD *)v129 + 5) = 0;
              }
              v216 = GetProcessHeap();
              HeapFree(v216, 0, v129);
            }
            v217 = (void *)pcchLength;
            if ( pcchLength )
            {
              v218 = GetProcessHeap();
              HeapFree(v218, 0, v217);
            }
            if ( v128 )
            {
              v219 = GetProcessHeap();
              HeapFree(v219, 0, v128);
            }
            v220 = v740;
            if ( v740 )
            {
              v221 = (void *)*((_QWORD *)v740 + 1);
              if ( v221 )
              {
                v222 = GetProcessHeap();
                HeapFree(v222, 0, v221);
                v220[1] = 0;
              }
              v223 = (void *)v220[3];
              if ( v223 )
              {
                v224 = GetProcessHeap();
                HeapFree(v224, 0, v223);
                v220[3] = 0;
              }
              v225 = (void *)v220[5];
              if ( v225 )
              {
                v226 = GetProcessHeap();
                HeapFree(v226, 0, v225);
                v220[5] = 0;
              }
              v227 = GetProcessHeap();
              HeapFree(v227, 0, v220);
            }
            v228 = v751;
            if ( v751 )
            {
              v229 = GetProcessHeap();
              HeapFree(v229, 0, v228);
            }
LABEL_248:
            if ( v10 < 0 )
              goto LABEL_28;
            v6 = v738;
            if ( !v729 )
              goto LABEL_250;
            if ( !v738 )
              goto LABEL_462;
            v754 = v738;
            LODWORD(dwBytes) = RtlULongLongAdd(v738, 4, &v754);
            v10 = dwBytes;
            if ( (dwBytes & 0x80000000) != 0LL )
              goto LABEL_36;
            v381 = (int *)v754;
            if ( !*v6 )
              v381 = 0;
            if ( *v6 != (_DWORD)v380 )
              goto LABEL_487;
            v10 = *v381;
            LODWORD(dwBytes) = v10;
            if ( v10 == -805306333 )
            {
              LODWORD(v730) = -2147024774;
            }
            else
            {
              LODWORD(v730) = v10;
              if ( v10 != -2147024774 && v10 < 0 )
                goto LABEL_39;
            }
            if ( v379 == 6 )
            {
              v732 = v378;
              for ( i1 = 0; !i1; i1 = v384 + 1 )
              {
                LODWORD(dwBytes) = RtlULongLongAdd(v378, v380, &v732);
                v10 = dwBytes;
                if ( (dwBytes & 0x80000000) != 0LL )
                  goto LABEL_36;
                LODWORD(dwBytes) = RtlULongLongAdd(v732, v383, &v732);
                v10 = dwBytes;
                if ( (dwBytes & 0x80000000) != 0LL )
                  goto LABEL_36;
                v378 = v732;
              }
              LODWORD(dwBytes) = RtlULongLongAdd(v378, v380, &v732);
              v10 = dwBytes;
              if ( (dwBytes & 0x80000000) != 0LL )
                goto LABEL_36;
              v387 = (void **)v732;
              if ( !v385 )
                v387 = 0;
              if ( v385 != 8 )
                goto LABEL_487;
              if ( !v6 )
              {
LABEL_462:
                v10 = -1073741811;
LABEL_488:
                LODWORD(dwBytes) = v10;
                goto LABEL_36;
              }
              v388 = *v387;
              v389 = (size_t)v6;
              v732 = (size_t)v6;
              v390 = 0;
              v742 = v388;
              while ( v390 < 2 )
              {
                LODWORD(dwBytes) = RtlULongLongAdd(v389, v386, &v732);
                v10 = dwBytes;
                if ( (dwBytes & 0x80000000) != 0LL )
                  goto LABEL_36;
                LODWORD(dwBytes) = RtlULongLongAdd(v732, v391, &v732);
                v10 = dwBytes;
                if ( (dwBytes & 0x80000000) != 0LL )
                  goto LABEL_36;
                v389 = v732;
                v390 = v392 + 1;
              }
              LODWORD(dwBytes) = RtlULongLongAdd(v389, v386, &v732);
              v10 = dwBytes;
              if ( (dwBytes & 0x80000000) != 0LL )
                goto LABEL_36;
              v395 = (unsigned int *)v732;
              if ( !v393 )
                v395 = 0;
              if ( v393 != (_DWORD)v394 )
                goto LABEL_487;
              v396 = *v395;
              v397 = (size_t)v6;
              v732 = (size_t)v6;
              v747 = v396;
              while ( 1 )
              {
                v398 = RtlULongLongAdd(v397, v394, &v732);
                LODWORD(dwBytes) = v398;
                v10 = v398;
                if ( v400 >= 3 )
                  break;
                if ( v398 < 0 )
                  goto LABEL_36;
                LODWORD(dwBytes) = RtlULongLongAdd(v732, v399, &v732);
                v10 = dwBytes;
                if ( (dwBytes & 0x80000000) != 0LL )
                  goto LABEL_36;
                v397 = v732;
              }
              if ( v398 < 0 )
                goto LABEL_36;
              v401 = v6;
              v402 = 0;
              v732 = (size_t)v6;
              while ( v402 < 4 )
              {
                v403 = *v401;
                LODWORD(dwBytes) = RtlULongLongAdd(v401, 4, &v732);
                v10 = dwBytes;
                if ( (dwBytes & 0x80000000) != 0LL )
                  goto LABEL_36;
                LODWORD(dwBytes) = RtlULongLongAdd(v732, v403, &v732);
                v10 = dwBytes;
                if ( (dwBytes & 0x80000000) != 0LL )
                  goto LABEL_36;
                v401 = (unsigned int *)v732;
                v402 = v404 + 1;
              }
              LODWORD(dwBytes) = RtlULongLongAdd(v401, 4, &v732);
              v10 = dwBytes;
              if ( (dwBytes & 0x80000000) != 0LL )
              {
LABEL_36:
                if ( v10 < 0 )
                  goto LABEL_39;
LABEL_37:
                if ( (_DWORD)v730 )
                {
                  v10 = v730;
                  LODWORD(dwBytes) = v730;
                }
                goto LABEL_39;
              }
              v406 = (unsigned int *)v732;
              if ( !v405 )
                v406 = 0;
              if ( v405 != 4 )
              {
LABEL_487:
                v10 = -1073741789;
                goto LABEL_488;
              }
              v407 = v6;
              v759 = *v406;
              v408 = 0;
              v732 = (size_t)v6;
              while ( v408 < 5 )
              {
                v409 = *v407;
                LODWORD(dwBytes) = RtlULongLongAdd(v407, 4, &v732);
                v10 = dwBytes;
                if ( (dwBytes & 0x80000000) != 0LL )
                  goto LABEL_39;
                LODWORD(dwBytes) = RtlULongLongAdd(v732, v409, &v732);
                v10 = dwBytes;
                if ( (dwBytes & 0x80000000) != 0LL )
                  goto LABEL_39;
                v407 = (unsigned int *)v732;
                v408 = v410 + 1;
              }
              v411 = RtlULongLongAdd(v407, 4, &v732);
              LODWORD(dwBytes) = v411;
              v10 = v411;
              if ( v411 < 0 )
              {
                LODWORD(dwBytes) = v411;
                goto LABEL_39;
              }
              v415 = (int *)v732;
              if ( !v412 )
                v415 = 0;
              if ( v412 != 4 )
              {
                v10 = -1073741789;
                goto LABEL_251;
              }
              if ( (LPVOID)v750 == v742 )
              {
                v766 = *v415;
                v768 = v747;
                if ( v759 > 4 || (unsigned int)v413 > 4 )
                {
                  v10 = -2147024774;
                  goto LABEL_251;
                }
                memcpy_0(v774, v414, v413);
                goto LABEL_37;
              }
            }
LABEL_250:
            v10 = -1073425151;
            goto LABEL_251;
          }
LABEL_225:
          v212 = GetProcessHeap();
          HeapFree(v212, 0, v731);
          goto LABEL_226;
        }
        v201 = *v129;
        HIDWORD(v730) = 0;
        LODWORD(dwBytes) = 4;
        v203 = RtlUIntAdd(4, v201, &dwBytes);
        if ( v203 >= 0 )
        {
          v203 = RtlUIntAdd((unsigned int)dwBytes, v202, &dwBytes);
          if ( v203 >= 0 )
          {
            v204 = v129[4];
            v754 = v129 + 4;
            v203 = RtlUIntAdd((unsigned int)dwBytes, v204, &dwBytes);
            if ( v203 >= 0 )
            {
              v203 = RtlUIntAdd((unsigned int)dwBytes, v205, &dwBytes);
              if ( v203 >= 0 )
              {
                v206 = v129[8];
                v753 = (SIZE_T)(v129 + 8);
                v203 = RtlUIntAdd((unsigned int)dwBytes, v206, &dwBytes);
                if ( v203 >= 0 )
                {
                  v736 = v129;
                  v207 = dwBytes;
                  v208 = GetProcessHeap();
                  v209 = (unsigned int *)HeapAlloc(v208, 8u, v207);
                  v129 = v736;
                  v210 = v209;
                  v741 = v209;
                  if ( !v209 )
                  {
                    v10 = -805306345;
LABEL_222:
                    LODWORD(dwBytes) = v10;
LABEL_223:
                    v211 = v731;
                    goto LABEL_224;
                  }
                  v230 = *v736;
                  v739 = v210;
                  *v210 = v230;
                  v203 = RtlULongLongAdd(v210, 4, &v739);
                  if ( v203 < 0 )
                  {
                    v731 = v232;
                    HIDWORD(dwBytes) = v233;
                    v741 = v231;
                  }
                  else
                  {
                    memcpy_0(v739, *((const void **)v129 + 1), *v129);
                    v203 = RtlULongLongAdd(v739, *v129, &v739);
                    if ( v203 >= 0 )
                    {
                      v234 = v739;
                      *(_DWORD *)v739 = *(_DWORD *)v754;
                      v203 = RtlULongLongAdd(v234, 4, &v739);
                      if ( v203 >= 0 )
                      {
                        memcpy_0(v739, *((const void **)v129 + 3), *v235);
                        v203 = RtlULongLongAdd(v739, *(unsigned int *)v754, &v739);
                        if ( v203 >= 0 )
                        {
                          v236 = v739;
                          *(_DWORD *)v739 = *(_DWORD *)v753;
                          v203 = RtlULongLongAdd(v236, 4, &v739);
                          if ( v203 >= 0 )
                          {
                            memcpy_0(v739, *((const void **)v129 + 5), *v237);
                            v203 = RtlULongLongAdd(v739, *(unsigned int *)v753, &v739);
                            if ( v203 >= 0 )
                            {
                              pcchLength = (size_t)v741;
                              HIDWORD(v730) = dwBytes;
                              goto LABEL_263;
                            }
                          }
                        }
                      }
                    }
                  }
                  v238 = GetProcessHeap();
                  HeapFree(v238, 0, v741);
                }
              }
            }
          }
        }
LABEL_263:
        v10 = v203 | 0x10000000;
        LODWORD(dwBytes) = v10;
        if ( v10 < 0 )
          goto LABEL_223;
        v763 = 8;
        v239 = RtlUIntAdd(8, HIDWORD(dwBytes), &v763);
        v10 = v239 | 0x10000000;
        LODWORD(dwBytes) = v239 | 0x10000000;
        if ( v239 < 0 )
          goto LABEL_223;
        v240 = (v763 + 7) & 0xFFFFFFF8;
        if ( (unsigned int)v240 < v763 )
        {
          v10 = -1073741675;
          goto LABEL_222;
        }
        v769 = (v763 + 7) & 0xFFFFFFF8;
        LODWORD(dwBytes) = RtlUIntAdd(v240, 8, &v769);
        v10 = dwBytes;
        if ( (dwBytes & 0x80000000) != 0LL )
          goto LABEL_223;
        v242 = (unsigned int *)lpMem[1];
        v243 = 0;
        v752 = v9;
        v741 = v11;
        v731 = v241;
        v736 = v129;
        v734 = 0;
        if ( lpMem[1] )
        {
          v736 = v129;
          v731 = v241;
          v741 = v11;
          v752 = v9;
          if ( LODWORD(lpMem[0]) > 1 )
          {
            v732 = (size_t)lpMem[1];
            for ( i2 = 0; !i2; i2 = v246 + 1 )
            {
              LODWORD(dwBytes) = RtlULongLongAdd(v242, 4, &v732);
              v10 = dwBytes;
              if ( (dwBytes & 0x80000000) != 0LL )
                goto LABEL_278;
              LODWORD(dwBytes) = RtlULongLongAdd(v732, v245, &v732);
              v10 = dwBytes;
              if ( (dwBytes & 0x80000000) != 0LL )
                goto LABEL_278;
              v242 = (unsigned int *)v732;
            }
            v747 = *v242;
            LODWORD(dwBytes) = RtlULongLongAdd(v242, 4, &v732);
            v10 = dwBytes;
            if ( (dwBytes & 0x80000000) != 0LL )
              goto LABEL_278;
            v247 = lpMem[1];
            if ( lpMem[1] && LODWORD(lpMem[0]) > 2 )
            {
              v732 = (size_t)lpMem[1];
              for ( i3 = 0; i3 < 2; i3 = v252 + 1 )
              {
                LODWORD(dwBytes) = RtlULongLongAdd(v247, 4, &v732);
                v10 = dwBytes;
                if ( (dwBytes & 0x80000000) != 0LL )
                  goto LABEL_278;
                LODWORD(dwBytes) = RtlULongLongAdd(v732, v251, &v732);
                v10 = dwBytes;
                if ( (dwBytes & 0x80000000) != 0LL )
                  goto LABEL_278;
                v247 = (LPVOID)v732;
              }
              LODWORD(dwBytes) = RtlULongLongAdd(v247, 4, &v732);
              v10 = dwBytes;
              if ( (dwBytes & 0x80000000) == 0LL )
              {
                v734 = v243;
                HIDWORD(dwBytes) = v253;
                LODWORD(dwBytes) = RtlUIntAdd(v253, v769, (char *)&dwBytes + 4);
                v10 = dwBytes;
                if ( (dwBytes & 0x80000000) != 0LL )
                  goto LABEL_296;
                LODWORD(dwBytes) = RtlUIntAdd(HIDWORD(dwBytes), v254, (char *)&dwBytes + 4);
                v10 = dwBytes;
                if ( (dwBytes & 0x80000000) != 0LL
                  || (LODWORD(dwBytes) = RtlUIntAdd(HIDWORD(dwBytes), v747, (char *)&dwBytes + 4),
                      v10 = dwBytes,
                      (dwBytes & 0x80000000) != 0LL)
                  || (LODWORD(dwBytes) = RtlUIntAdd(HIDWORD(dwBytes), v255, (char *)&dwBytes + 4),
                      v10 = dwBytes,
                      (dwBytes & 0x80000000) != 0LL)
                  || (LODWORD(dwBytes) = RtlUIntAdd(HIDWORD(dwBytes), v256, (char *)&dwBytes + 4),
                      v10 = dwBytes,
                      (dwBytes & 0x80000000) != 0LL) )
                {
LABEL_296:
                  if ( v10 < 0 )
                    goto LABEL_223;
                }
                else
                {
                  v243 = HIDWORD(dwBytes);
                  v734 = HIDWORD(dwBytes);
                }
                if ( v243 > 0x400000 )
                {
                  v10 = -2147418113;
                  goto LABEL_222;
                }
LABEL_279:
                v248 = v243;
                v249 = GetProcessHeap();
                v128 = (unsigned int *)HeapAlloc(v249, 8u, v248);
                if ( !v128 )
                {
                  v10 = -805306345;
LABEL_281:
                  LODWORD(dwBytes) = v10;
LABEL_282:
                  v129 = v736;
                  goto LABEL_223;
                }
                phModule = 0;
                v778 = 0;
                v779 = 0;
                if ( !pcchLength )
                {
                  v10 = -2147024809;
                  goto LABEL_281;
                }
                LODWORD(v779) = HIDWORD(v730);
                *(_QWORD *)&v778 = pcchLength;
                *(_QWORD *)((char *)&v779 + 4) = v734;
                *((_QWORD *)&v778 + 1) = v128;
                if ( GetModuleHandleExW(1u, L"ntdll.dll", &phModule)
                  && (v258 = GetProcAddress(phModule, "NtQuerySystemInformation")) != 0 )
                {
                  v259 = ((__int64 (__fastcall *)(__int64, __int128 *))v258)(134, &v778);
                  v10 = v259 | 0x10000000;
                  LODWORD(dwBytes) = v259 | 0x10000000;
                  if ( v259 >= 0 )
                  {
                    v260 = DWORD1(v779);
                    goto LABEL_313;
                  }
                }
                else
                {
                  v257 = GetLastError();
                  LODWORD(dwBytes) = v257;
                  v10 = v257;
                  if ( v257 > 0 )
                  {
                    v10 = (unsigned __int16)v257 | 0x80070000;
                    LODWORD(dwBytes) = v10;
                  }
                  if ( v10 >= 0 )
                  {
                    v10 = -2147467259;
                    goto LABEL_281;
                  }
                }
                if ( v10 == -805306333 )
                {
                  v10 = -2147024774;
                  goto LABEL_281;
                }
                if ( v10 < 0 )
                  goto LABEL_282;
                v260 = v734;
LABEL_313:
                HIDWORD(dwBytes) = 0;
                v739 = v128;
                if ( v260 < 4 )
                {
LABEL_314:
                  v10 = -805306306;
                  goto LABEL_281;
                }
                v261 = (void *)*v128;
                v747 = *v128;
                v263 = RtlULongLongAdd(v128, 4, &v739);
                if ( v263 >= 0 )
                {
                  v263 = RtlUIntAdd(0, v262, (char *)&dwBytes + 4);
                  if ( v263 < 0 )
                  {
LABEL_367:
                    v129 = v736;
                    v739 = v128;
                    goto LABEL_368;
                  }
                  if ( v265 - HIDWORD(dwBytes) < (unsigned int)v261 )
                    goto LABEL_314;
                  v753 = (SIZE_T)v739;
                  v754 = v261;
                  v263 = RtlULongLongAdd(v739, (unsigned int)v261, &v739);
                  if ( v263 >= 0 )
                  {
                    v263 = RtlUIntAdd(HIDWORD(dwBytes), (unsigned int)v261, (char *)&dwBytes + 4);
                    if ( v263 >= 0 )
                    {
                      if ( v266 - HIDWORD(dwBytes) < (unsigned int)v267 )
                        goto LABEL_314;
                      v759 = *(_DWORD *)v739;
                      v263 = RtlULongLongAdd(v739, v267, &v739);
                      if ( v263 >= 0 )
                      {
                        v263 = RtlUIntAdd(HIDWORD(dwBytes), v268, (char *)&dwBytes + 4);
                        if ( v263 >= 0 )
                        {
                          if ( v269 - HIDWORD(dwBytes) < (unsigned int)v270 )
                            goto LABEL_314;
                          Size = (SIZE_T)v739;
                          Src = v270;
                          v263 = RtlULongLongAdd(v739, (unsigned int)v270, &v739);
                          if ( v263 >= 0 )
                          {
                            v263 = RtlUIntAdd(HIDWORD(dwBytes), v271, (char *)&dwBytes + 4);
                            if ( v263 >= 0 )
                            {
                              if ( v272 - HIDWORD(dwBytes) < v273 )
                                goto LABEL_314;
                              HIDWORD(v730) = *(_DWORD *)v739;
                              v263 = RtlULongLongAdd(v739, 4, &v739);
                              if ( v263 >= 0 )
                              {
                                v263 = RtlUIntAdd(HIDWORD(dwBytes), 4, (char *)&dwBytes + 4);
                                if ( v263 >= 0 )
                                {
                                  if ( v274 - HIDWORD(dwBytes) < v275 )
                                    goto LABEL_314;
                                  v263 = RtlUIntAdd(HIDWORD(dwBytes), v275, (char *)&dwBytes + 4);
                                  if ( v263 >= 0 )
                                  {
                                    if ( v276 != HIDWORD(dwBytes)
                                      || (unsigned int)(v277 + v278 + (_DWORD)v261) + 12LL != v276 )
                                    {
                                      goto LABEL_314;
                                    }
                                    v279 = GetProcessHeap();
                                    v280 = HeapAlloc(v279, 8u, 0x30u);
                                    v129 = v736;
                                    v281 = v280;
                                    v737 = v280;
                                    v282 = v280 == 0;
                                    v211 = v731;
                                    if ( v282 )
                                    {
                                      v10 = -805306345;
                                      v740 = 0;
                                      LODWORD(dwBytes) = -805306345;
                                      goto LABEL_224;
                                    }
                                    v752 = v9;
                                    v741 = v11;
                                    v732 = 0;
                                    if ( v753 )
                                    {
                                      *(_DWORD *)v281 = v747;
                                      v283 = GetProcessHeap();
                                      v284 = HeapAlloc(v283, 8u, (SIZE_T)v754);
                                      if ( !v284 )
                                      {
LABEL_346:
                                        v292 = v737;
                                        v263 = -1073741801;
                                        v739 = v128;
                                        v742 = (LPVOID)*((_QWORD *)v737 + 1);
                                        if ( v742 )
                                        {
                                          v293 = GetProcessHeap();
                                          HeapFree(v293, 0, v742);
                                          v292 = v737;
                                          *((_QWORD *)v737 + 1) = 0;
                                        }
                                        v742 = (LPVOID)v292[3];
                                        if ( v742 )
                                        {
                                          v294 = GetProcessHeap();
                                          HeapFree(v294, 0, v742);
                                          v292 = v737;
                                          *((_QWORD *)v737 + 3) = 0;
                                        }
                                        v742 = (LPVOID)v292[5];
                                        if ( v742 )
                                        {
                                          v295 = GetProcessHeap();
                                          HeapFree(v295, 0, v742);
                                          *((_QWORD *)v737 + 5) = 0;
                                        }
                                        v296 = GetProcessHeap();
                                        HeapFree(v296, 0, v737);
                                        v297 = (unsigned int *)v732;
                                        goto LABEL_356;
                                      }
                                      *((_QWORD *)v737 + 1) = v284;
                                      v263 = 0;
                                      memcpy_0(v284, (const void *)v753, (size_t)v754);
                                      v281 = v737;
                                    }
                                    else
                                    {
                                      *(_DWORD *)v281 = 0;
                                      v263 = 0;
                                      v281[1] = 0;
                                    }
                                    if ( Size )
                                    {
                                      *((_DWORD *)v281 + 4) = v759;
                                      v285 = GetProcessHeap();
                                      v286 = HeapAlloc(v285, 8u, (SIZE_T)Src);
                                      v287 = v737;
                                      if ( !v286 )
                                      {
LABEL_345:
                                        v737 = v287;
                                        v752 = v9;
                                        v741 = v11;
                                        v736 = v129;
                                        goto LABEL_346;
                                      }
                                      *((_QWORD *)v737 + 3) = v286;
                                      v263 = 0;
                                      memcpy_0(v286, (const void *)Size, (size_t)Src);
                                      v281 = v737;
                                    }
                                    else
                                    {
                                      *((_DWORD *)v281 + 4) = 0;
                                      v281[3] = 0;
                                    }
                                    if ( v739 )
                                    {
                                      v288 = (void *)HIDWORD(v730);
                                      *((_DWORD *)v281 + 8) = HIDWORD(v730);
                                      v289 = (unsigned int)v288;
                                      v742 = v288;
                                      v290 = GetProcessHeap();
                                      v291 = HeapAlloc(v290, 8u, v289);
                                      v287 = v737;
                                      if ( !v291 )
                                        goto LABEL_345;
                                      *((_QWORD *)v737 + 5) = v291;
                                      v263 = 0;
                                      memcpy_0(v291, v739, (size_t)v742);
                                      v281 = v737;
                                    }
                                    else
                                    {
                                      *((_DWORD *)v281 + 8) = 0;
                                      v281[5] = 0;
                                    }
                                    v297 = (unsigned int *)v281;
                                    v732 = (size_t)v281;
                                    v739 = v128;
                                    v736 = v129;
                                    v741 = v11;
                                    v752 = v9;
LABEL_356:
                                    if ( v263 < 0 )
                                    {
                                      v264 = 0;
                                      v740 = 0;
                                      if ( v297 )
                                      {
                                        v742 = (LPVOID)*((_QWORD *)v297 + 1);
                                        if ( v742 )
                                        {
                                          v298 = GetProcessHeap();
                                          HeapFree(v298, 0, v742);
                                          v297 = (unsigned int *)v732;
                                          *(_QWORD *)(v732 + 8) = 0;
                                        }
                                        v742 = (LPVOID)*((_QWORD *)v297 + 3);
                                        if ( v742 )
                                        {
                                          v299 = GetProcessHeap();
                                          HeapFree(v299, 0, v742);
                                          v297 = (unsigned int *)v732;
                                          *(_QWORD *)(v732 + 24) = 0;
                                        }
                                        v742 = (LPVOID)*((_QWORD *)v297 + 5);
                                        if ( v742 )
                                        {
                                          v300 = GetProcessHeap();
                                          HeapFree(v300, 0, v742);
                                          *(_QWORD *)(v732 + 40) = 0;
                                        }
                                        v301 = GetProcessHeap();
                                        HeapFree(v301, 0, (LPVOID)v732);
                                        v264 = 0;
                                        v740 = 0;
                                      }
                                    }
                                    else
                                    {
                                      v264 = v297;
                                      v740 = v297;
                                    }
LABEL_368:
                                    v10 = v263 | 0x10000000;
                                    LODWORD(dwBytes) = v10;
                                    if ( v10 < 0 )
                                      goto LABEL_223;
                                    if ( !v264 || (Size = *((_QWORD *)v264 + 1)) == 0 || !*v264 )
                                    {
                                      v10 = -805306355;
                                      goto LABEL_281;
                                    }
                                    v302 = *v264 - 8LL;
                                    psz = (STRSAFE_PCNZWCH)v302;
                                    v751 = MemoryAlloc(v302);
                                    v303 = v751;
                                    if ( !v751 )
                                    {
LABEL_400:
                                      v10 = -805306367;
                                      v751 = 0;
                                      goto LABEL_281;
                                    }
                                    v304 = 0;
                                    v733 = 0;
                                    v737 = (LPVOID)0x7F1137FAB69605ELL;
                                    Src = (void *)Size;
                                    v754 = v751;
                                    v305 = v302 & 7;
                                    if ( (v302 & 7) != 0 )
                                    {
                                      v306 = 0;
                                      v744 = 0;
                                      v734 = 0;
                                      v307 = 0;
                                      v308 = (unsigned __int8 *)Src;
                                      v309 = 0;
                                      do
                                      {
                                        v310 = *v308++;
                                        HIDWORD(v730) = 8 * v306;
                                        if ( v306 >= 4 )
                                          v307 |= v310 << (56 - BYTE4(v730));
                                        else
                                          v309 |= v310 << (24 - BYTE4(v730));
                                        ++v306;
                                      }
                                      while ( (int)v306 < (int)v305 );
                                      v734 = v309;
                                      v311 = v309;
                                      v304 = v733;
                                      v744 = v307;
                                      Src = v308;
                                      v739 = v128;
                                      v736 = v129;
                                      v741 = v11;
                                      v752 = v9;
                                      v312 = v311 ^ 0x92F65A5;
                                      v313 = v307 ^ 0x699A899C;
                                      v314 = 0;
                                      v315 = v312;
                                      v316 = v307 ^ 0x699A899C;
                                      if ( (v302 & 7) != 0 )
                                      {
                                        v317 = v751;
                                        do
                                        {
                                          v742 = v317 + 1;
                                          if ( v314 >= 4 )
                                          {
                                            v316 = __ROR4__(v316, 24);
                                            v318 = v316;
                                          }
                                          else
                                          {
                                            v315 = __ROR4__(v315, 24);
                                            v318 = v315;
                                          }
                                          *v317 = v318;
                                          ++v314;
                                          v317 = v742;
                                        }
                                        while ( (int)v314 < (int)v305 );
                                        v754 = v742;
                                      }
                                      if ( v305 <= 4 )
                                      {
                                        v319 = 0;
                                        if ( v305 < 4 )
                                          v312 = v312 >> (8 * (4 - v305)) << (8 * (4 - v305));
                                      }
                                      else
                                      {
                                        v319 = v313 >> (8 * (8 - v305)) << (8 * (8 - v305));
                                      }
                                    }
                                    else
                                    {
                                      v319 = 0;
                                      v734 = 0;
                                      v312 = 0;
                                      v744 = -1;
                                    }
                                    if ( v302 >> 3 )
                                    {
                                      v320 = HIDWORD(v737);
                                      v321 = v302 >> 3;
                                      v322 = (unsigned __int8 *)Src;
                                      v323 = v744;
                                      v324 = HIDWORD(v737) ^ 0xAB69605E;
                                      v325 = v734;
                                      HIDWORD(dwBytes) = WORD2(v737);
                                      LODWORD(dwBytes) = 24670;
                                      v326 = v754;
                                      v753 = 0;
                                      HIDWORD(v730) = HIDWORD(v737) ^ 0xAB69605E;
                                      do
                                      {
                                        v327 = v322[1];
                                        v328 = *v322;
                                        v329 = v322[4];
                                        v322 += 8;
                                        v330 = *(v322 - 5) | ((*(v322 - 6) | ((v327 | (v328 << 8)) << 8)) << 8);
                                        v331 = v312 ^ v330;
                                        v332 = *(v322 - 1) | ((*(v322 - 2) | ((*(v322 - 3) | (v329 << 8)) << 8)) << 8);
                                        v333 = v319 ^ v332 ^ v324 ^ v312 ^ v330;
                                        v334 = v331
                                             ^ (__ROR4__(v333, 22) + HIDWORD(dwBytes) * __ROR4__(v333 + 1419157410, 27));
                                        v335 = v333 ^ (WORD1(v737) * __ROR4__(v334 + v320, 9) - __ROR4__(v334, 30));
                                        v336 = v334 ^ (dwBytes * (v335 - HIDWORD(dwBytes)) - (v335 >> 13));
                                        v337 = v335
                                             ^ (HIWORD(v737) * __ROR4__(WORD1(v737) ^ v336, 26) - __ROR4__(v336, 30));
                                        v338 = v336 ^ (v320 - (v337 ^ 0xAB69605E));
                                        v339 = v337 ^ (WORD1(v737) * (HIDWORD(dwBytes) ^ v338)) ^ __ROR4__(v338, 6);
                                        v340 = v338 ^ (__ROR4__(v339, 30) + dwBytes * __ROR4__(v339 + v320, 15));
                                        v341 = v339
                                             ^ (HIWORD(v737) * __ROR4__(v340 + 1419157410, 14) - __ROR4__(v340, 24));
                                        v342 = v340
                                             ^ __ROR4__(v341, 10)
                                             ^ (HIDWORD(dwBytes) * __ROR4__(v341 ^ 0xAB69605E, 12));
                                        v343 = v342
                                             ^ (HIWORD(v737)
                                              * (dwBytes
                                               + __ROR4__(
                                                   ~(v341 ^ (v342 >> 10) ^ (WORD1(v737) * (v342 ^ HIWORD(v737)))),
                                                   5)));
                                        v344 = v341
                                             ^ (v342 >> 10)
                                             ^ (WORD1(v737) * (v342 ^ HIWORD(v737)))
                                             ^ (v343 - HIWORD(v737))
                                             ^ 0xAB69605E;
                                        v345 = v343
                                             ^ ((v344 >> 2) + HIDWORD(dwBytes) * __ROR4__(HIWORD(v737) ^ v344, 30));
                                        v346 = v344
                                             ^ (__ROR4__(v345, 25) + WORD1(v737) * __ROR4__(v345 - HIDWORD(v737), 6));
                                        v347 = v345 ^ (dwBytes * (HIDWORD(dwBytes) ^ v346) + __ROR4__(v346, 9));
                                        v348 = v346
                                             ^ (__ROR4__(v347, 25) + HIWORD(v737) * __ROR4__(WORD1(v737) ^ v347, 27));
                                        v320 = HIDWORD(v737);
                                        v349 = HIDWORD(v730) ^ v347 ^ v348;
                                        v350 = v348 ^ (HIDWORD(dwBytes) * (__ROR4__(v349, 3) - WORD1(v737)));
                                        v351 = v349 ^ (dwBytes * __ROR4__(v350 - HIDWORD(v737), 1) - __ROR4__(v350, 6));
                                        v324 = HIDWORD(v730);
                                        v352 = v350
                                             ^ (__ROR4__(v351, 18) + HIWORD(v737) * __ROR4__(v351 - 1419157410, 29));
                                        v353 = v351
                                             ^ (HIDWORD(dwBytes) * __ROR4__(v352 - 1419157410, 17) - __ROR4__(v352, 14));
                                        v354 = v352 ^ (v353 >> 3) ^ (WORD1(v737) * (dwBytes ^ v353));
                                        v319 = v323 ^ v354;
                                        v323 = v332;
                                        v312 = v325
                                             ^ v353
                                             ^ __ROR4__(v354, 30)
                                             ^ (dwBytes * __ROR4__(HIDWORD(v737) ^ v354, 28));
                                        v325 = v330;
                                        v326[3] = v312;
                                        v326[7] = v319;
                                        v326[2] = __ROR4__(v312, 8);
                                        v326[6] = __ROR4__(v319, 8);
                                        v326[1] = __ROR4__(v312, 16);
                                        v326[5] = __ROR4__(v319, 16);
                                        *v326 = __ROR4__(v312, 24);
                                        v326[4] = __ROR4__(v319, 24);
                                        v326 += 8;
                                        ++v753;
                                      }
                                      while ( v753 < v321 );
                                      v304 = v733;
                                      v9 = v752;
                                      v11 = v741;
                                      v128 = (unsigned int *)v739;
                                      v303 = v751;
                                      v302 = (unsigned __int64)psz;
                                    }
                                    for ( i4 = 0; i4 < v302; ++i4 )
                                      v304 ^= v303[i4];
                                    if ( v304 != *(_QWORD *)(Size + v302) )
                                    {
                                      MemoryFree(v303);
                                      goto LABEL_400;
                                    }
                                    v129 = v736;
                                    HIDWORD(dwBytes) = 0;
                                    v732 = (size_t)v303;
                                    if ( (unsigned int)v302 < 4 )
                                    {
LABEL_402:
                                      v356 = -1073741762;
LABEL_439:
                                      v10 = v356 | 0x10000000;
                                      goto LABEL_222;
                                    }
                                    v356 = RtlULongLongAdd(v303, 4, &v732);
                                    if ( v356 >= 0 )
                                    {
                                      v356 = RtlUIntAdd(0, 4, (char *)&dwBytes + 4);
                                      if ( v356 >= 0 )
                                      {
                                        if ( (unsigned int)((_DWORD)psz - HIDWORD(dwBytes)) < 4 )
                                          goto LABEL_437;
                                        v734 = *(_DWORD *)v732;
                                        v356 = RtlULongLongAdd(v732, 4, &v732);
                                        if ( v356 < 0 )
                                          goto LABEL_438;
                                        v356 = RtlUIntAdd(HIDWORD(dwBytes), 4, (char *)&dwBytes + 4);
                                        if ( v356 < 0 )
                                          goto LABEL_438;
                                        if ( (int)psz - HIDWORD(dwBytes) < v734 )
                                          goto LABEL_437;
                                        v356 = RtlUIntAdd(HIDWORD(dwBytes), v734, (char *)&dwBytes + 4);
                                        if ( v356 >= 0 )
                                        {
                                          if ( (unsigned __int64)v359 + (unsigned int)psz >= v734 + v732 )
                                          {
                                            v360 = (const void *)v732;
                                            if ( (unsigned __int64)v359 + (unsigned int)psz - v732 - v734 < 8 )
                                            {
                                              v747 = *v359;
                                              v754 = 0;
                                              v753 = 0;
                                              Src = 0;
                                              v744 = 0;
                                              if ( v732 )
                                              {
                                                v361 = RtlULongLongAdd(v732, v734, &v754);
                                                v751 = v363;
                                                v356 = v361;
                                                v740 = v364;
                                                v731 = v365;
                                                if ( v361 < 0 )
                                                {
LABEL_433:
                                                  v377 = v729;
LABEL_434:
                                                  if ( v356 < 0 || v747 == v377 )
                                                    goto LABEL_439;
                                                  goto LABEL_402;
                                                }
                                                v366 = v754;
                                                v367 = v362;
                                                v368 = 4;
                                                while ( v367 < v366 )
                                                {
                                                  v356 = RtlULongLongAdd(v367, v368, &v753);
                                                  if ( v356 < 0 )
                                                    goto LABEL_433;
                                                  if ( v753 > v370 )
                                                    goto LABEL_422;
                                                  v372 = *v369;
                                                  HIDWORD(v730) = 0;
                                                  v356 = RtlUIntAdd(v371, v372, (char *)&v730 + 4);
                                                  if ( v356 < 0 )
                                                    goto LABEL_439;
                                                  v356 = RtlULongLongAdd(v373, HIDWORD(v730), &Src);
                                                  if ( v356 < 0 )
                                                    goto LABEL_433;
                                                  v367 = Src;
                                                  if ( Src > v366 )
                                                    goto LABEL_422;
                                                  ++v744;
                                                }
                                                if ( v367 != v366 )
                                                {
LABEL_422:
                                                  v356 = -1073741811;
                                                  goto LABEL_439;
                                                }
                                                v360 = (const void *)v732;
                                              }
                                              else
                                              {
                                                v356 = 0;
                                                v751 = v359;
                                                v740 = v358;
                                                v731 = v357;
                                              }
                                              v374 = v734;
                                              v375 = 0;
                                              v754 = 0;
                                              if ( v734 )
                                              {
                                                v376 = GetProcessHeap();
                                                v754 = HeapAlloc(v376, 8u, v734);
                                                v375 = v754;
                                                if ( !v754 )
                                                {
                                                  v356 = -1073741801;
                                                  goto LABEL_439;
                                                }
                                                v360 = (const void *)v732;
                                                v356 = 0;
                                                v374 = v734;
                                              }
                                              if ( v360 )
                                                memcpy_0(v375, v360, v374);
                                              v738 = v754;
                                              v377 = v744;
                                              v729 = v744;
                                              goto LABEL_434;
                                            }
                                          }
LABEL_437:
                                          v356 = -1073741762;
                                        }
                                      }
                                    }
LABEL_438:
                                    v751 = v359;
                                    v731 = v357;
                                    v740 = v358;
                                    goto LABEL_439;
                                  }
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
                v264 = (unsigned int *)v740;
                goto LABEL_367;
              }
LABEL_278:
              if ( v10 < 0 )
                goto LABEL_223;
              goto LABEL_279;
            }
          }
        }
        v10 = -1073741811;
        LODWORD(dwBytes) = -1073741811;
        goto LABEL_278;
      }
      pcchLength = (size_t)lpMem[1];
      for ( i5 = 0; i5 < v109; i5 = v113 + 1 )
      {
        v111 = *v108;
        v729 = 0;
        LODWORD(dwBytes) = RtlUIntAdd(4, v111, &v729);
        v10 = dwBytes;
        if ( (dwBytes & 0x80000000) != 0LL )
          goto LABEL_35;
        LODWORD(dwBytes) = RtlULongLongAdd(v112, v729, &pcchLength);
        v10 = dwBytes;
        if ( (dwBytes & 0x80000000) != 0LL )
          goto LABEL_35;
        v108 = (unsigned int *)pcchLength;
      }
      LODWORD(dwBytes) = RtlULongLongAdd(v108, 4, &v743);
      v10 = dwBytes;
      if ( (dwBytes & 0x80000000) != 0LL )
        goto LABEL_35;
      if ( v114 + 2 <= (_DWORD *)((char *)lpMem[1] + HIDWORD(lpMem[0])) )
      {
        v115 = v743;
        *v114 = 4;
        *v115 = 4;
        goto LABEL_141;
      }
    }
LABEL_73:
    v10 = -1073741789;
    goto LABEL_34;
  }
  v3 = -2147024809;
LABEL_881:
  SP<unsigned char,SP_HLOCAL<unsigned char>>::Reset(&v771);
  return v3;
}

```

## disassembly

```asm
0x180034cec  mov     [rsp-8+arg_10], rbx
0x180034cf1  push    rbp
0x180034cf2  push    rsi
0x180034cf3  push    rdi
0x180034cf4  push    r12
0x180034cf6  push    r13
0x180034cf8  push    r14
0x180034cfa  push    r15
0x180034cfc  lea     rbp, [rsp-140h]
0x180034d04  sub     rsp, 240h
0x180034d0b  mov     [rbp+170h+var_D0], rdx
0x180034d12  mov     rdi, rdx
0x180034d15  mov     [rbp+170h+psz], rcx
0x180034d19  mov     [rbp+170h+var_100], 0
0x180034d21  test    rcx, rcx
0x180034d24  jnz     short loc_180034D30
0x180034d26  mov     ebx, 80070057h
0x180034d2b  jmp     loc_18003A53C
0x180034d30  test    rdx, rdx
0x180034d33  jz      short loc_180034D26
0x180034d35  xor     ebx, ebx
0x180034d37  mov     dword ptr [rbp+170h+var_1B8], ebx
0x180034d3a  mov     [rbp+170h+var_108], rbx
0x180034d3e  lea     edx, [rbx+4]; uBytes
0x180034d41  lea     ecx, [rbx+40h]; uFlags
0x180034d44  call    cs:__imp_LocalAlloc
0x180034d4a  mov     rdx, rax
0x180034d4d  lea     rcx, [rbp+170h+var_108]
0x180034d51  call    ??4?$SP@EV?$SP_HLOCAL@E@@@@QEAAAEAV0@V?$CTypeWrapper@PEAE@@@Z; SP<uchar,SP_HLOCAL<uchar>>::operator=(CTypeWrapper<uchar *>)
0x180034d56  mov     rax, [rbp+170h+var_108]
0x180034d5a  mov     [rbp+170h+var_D8], rax
0x180034d61  test    rax, rax
0x180034d64  jz      loc_18003A4BF
0x180034d6a  xorps   xmm0, xmm0
0x180034d6d  mov     [rbp+170h+var_118], ebx
0x180034d70  xor     esi, esi
0x180034d72  mov     [rbp+170h+var_110], ebx
0x180034d75  movups  xmmword ptr [rbp+170h+lpMem], xmm0
0x180034d79  mov     [rsp+270h+var_1F8], rsi
0x180034d7e  call    cs:__imp_GetProcessHeap
0x180034d84  lea     r14d, [rbx+8]
0x180034d88  mov     r8d, 0A0h; dwBytes
0x180034d8e  mov     rcx, rax; hHeap
0x180034d91  mov     edx, r14d; dwFlags
0x180034d94  call    cs:__imp_HeapAlloc
0x180034d9a  mov     r13d, 0D0000017h
0x180034da0  mov     [rbp+170h+var_160], 0FFFFFFFFh
0x180034da7  mov     dword ptr [rsp+270h+var_214+4], r13d
0x180034dac  mov     r15, rax
0x180034daf  mov     rbx, 0C81ECB17B1B54A58h
0x180034db9  mov     rdi, 7F1137FAB69605Eh
0x180034dc3  test    rax, rax
0x180034dc6  jnz     short loc_180034DDB
0x180034dc8  mov     r14d, 0C0000017h
0x180034dce  xor     r12d, r12d
0x180034dd1  mov     dword ptr [rsp+270h+dwBytes], r14d
0x180034dd6  jmp     loc_18003525D
0x180034ddb  movups  xmm0, cs:xmmword_180069D10
0x180034de2  movups  xmmword ptr [rax], xmm0
0x180034de5  movups  xmm1, cs:xmmword_180069D20
0x180034dec  movups  xmmword ptr [rax+10h], xmm1
0x180034df0  movups  xmm0, cs:xmmword_180069D30
0x180034df7  movups  xmmword ptr [rax+20h], xmm0
0x180034dfb  movups  xmm1, cs:xmmword_180069D40
0x180034e02  movups  xmmword ptr [rax+30h], xmm1
0x180034e06  movups  xmm0, cs:xmmword_180069D50
0x180034e0d  movups  xmmword ptr [rax+40h], xmm0
0x180034e11  movups  xmm1, cs:xmmword_180069D60
0x180034e18  movups  xmmword ptr [rax+50h], xmm1
0x180034e1c  movups  xmm0, cs:xmmword_180069D70
0x180034e23  movups  xmmword ptr [rax+60h], xmm0
0x180034e27  movups  xmm1, cs:xmmword_180069D80
0x180034e2e  movups  xmmword ptr [rax+70h], xmm1
0x180034e32  movups  xmm0, cs:xmmword_180069D90
0x180034e39  movups  xmmword ptr [rax+80h], xmm0
0x180034e40  movups  xmm1, cs:xmmword_180069DA0
0x180034e47  movups  xmmword ptr [rax+90h], xmm1
0x180034e4e  call    cs:__imp_GetProcessHeap
0x180034e54  mov     r8, r14; dwBytes
0x180034e57  mov     edx, r14d; dwFlags
0x180034e5a  mov     rcx, rax; hHeap
0x180034e5d  call    cs:__imp_HeapAlloc
0x180034e63  mov     r12, rax
0x180034e66  test    rax, rax
0x180034e69  jnz     short loc_180034E7B
0x180034e6b  mov     r14d, 0C0000017h
0x180034e71  mov     dword ptr [rsp+270h+dwBytes], r14d
0x180034e76  jmp     loc_18003525D
0x180034e7b  mov     rax, cs:qword_180069C50
0x180034e82  mov     [r12], rax
0x180034e86  rdtsc
0x180034e88  shl     rdx, 20h
0x180034e8c  or      rax, rdx
0x180034e8f  mov     [rbp+170h+var_190], rax
0x180034e93  mov     r11d, 4
0x180034e99  mov     dword ptr [rsp+270h+dwBytes+4], esi
0x180034e9d  mov     edx, r11d
0x180034ea0  mov     [rsp+270h+var_238], esi
0x180034ea4  mov     ecx, r11d
0x180034ea7  lea     r8, [rsp+270h+var_238]
0x180034eac  call    RtlUIntAdd
0x180034eb1  mov     dword ptr [rsp+270h+dwBytes], eax
0x180034eb5  mov     r14d, eax
0x180034eb8  test    eax, eax
0x180034eba  js      loc_18003525D
0x180034ec0  mov     edx, [rsp+270h+var_238]
0x180034ec4  lea     r8, [rsp+270h+dwBytes+4]
0x180034ec9  xor     ecx, ecx
0x180034ecb  call    RtlUIntAdd
0x180034ed0  mov     r14d, eax
0x180034ed3  mov     r9d, 10000000h
0x180034ed9  or      r14d, r9d
0x180034edc  mov     dword ptr [rsp+270h+dwBytes], r14d
0x180034ee1  jl      loc_18003525D
0x180034ee7  mov     [rsp+270h+var_238], ecx
0x180034eeb  lea     r8, [rsp+270h+var_238]
0x180034ef0  mov     ecx, r11d
0x180034ef3  mov     edx, 0A0h
0x180034ef8  call    RtlUIntAdd
0x180034efd  mov     dword ptr [rsp+270h+dwBytes], eax
0x180034f01  mov     r14d, eax
0x180034f04  test    eax, eax
0x180034f06  js      loc_18003525D
0x180034f0c  mov     edx, [rsp+270h+var_238]
0x180034f10  lea     r8, [rsp+270h+dwBytes+4]
0x180034f15  mov     ecx, dword ptr [rsp+270h+dwBytes+4]
0x180034f19  call    RtlUIntAdd
0x180034f1e  mov     r14d, eax
0x180034f21  or      r14d, r9d
0x180034f24  mov     dword ptr [rsp+270h+dwBytes], r14d
0x180034f29  jl      loc_18003525D
0x180034f2f  lea     r8, [rsp+270h+var_238]
0x180034f34  mov     [rsp+270h+var_238], esi
0x180034f38  lea     edx, [r11+4]
0x180034f3c  mov     ecx, r11d
0x180034f3f  call    RtlUIntAdd
0x180034f44  mov     dword ptr [rsp+270h+dwBytes], eax
0x180034f48  mov     r14d, eax
0x180034f4b  test    eax, eax
0x180034f4d  js      loc_18003525D
0x180034f53  mov     edx, [rsp+270h+var_238]
0x180034f57  lea     r8, [rsp+270h+dwBytes+4]
0x180034f5c  mov     ecx, dword ptr [rsp+270h+dwBytes+4]
0x180034f60  call    RtlUIntAdd
0x180034f65  mov     r14d, eax
0x180034f68  or      r14d, r9d
0x180034f6b  mov     dword ptr [rsp+270h+dwBytes], r14d
0x180034f70  jl      loc_18003525D
0x180034f76  lea     r8, [rsp+270h+var_238]
0x180034f7b  mov     [rsp+270h+var_238], esi
0x180034f7f  lea     edx, [r11+4]
0x180034f83  mov     ecx, r11d
0x180034f86  call    RtlUIntAdd
0x180034f8b  mov     dword ptr [rsp+270h+dwBytes], eax
0x180034f8f  mov     r14d, eax
0x180034f92  test    eax, eax
0x180034f94  js      loc_18003525D
0x180034f9a  mov     edx, [rsp+270h+var_238]
0x180034f9e  lea     r8, [rsp+270h+dwBytes+4]
0x180034fa3  mov     ecx, dword ptr [rsp+270h+dwBytes+4]
0x180034fa7  call    RtlUIntAdd
0x180034fac  mov     r14d, eax
0x180034faf  or      r14d, r9d
0x180034fb2  mov     dword ptr [rsp+270h+dwBytes], r14d
0x180034fb7  jl      loc_18003525D
0x180034fbd  mov     rcx, [rbp+170h+psz]; psz
0x180034fc1  lea     r8, [rbp+170h+pcchLength]; pcchLength
0x180034fc5  mov     [rbp+170h+pcchLength], rsi
0x180034fc9  call    StringCchLengthW
0x180034fce  test    eax, eax
0x180034fd0  jns     short loc_180034FDD
0x180034fd2  mov     r14d, 0C000003Eh
0x180034fd8  jmp     loc_180036A3C
0x180034fdd  mov     rdx, [rbp+170h+pcchLength]
0x180034fe1  lea     r8, [rsp+270h+var_238]
0x180034fe6  inc     rdx
0x180034fe9  mov     [rsp+270h+var_238], esi
0x180034fed  add     edx, edx
0x180034fef  mov     ecx, r11d
0x180034ff2  call    RtlUIntAdd
0x180034ff7  mov     dword ptr [rsp+270h+dwBytes], eax
0x180034ffb  mov     r14d, eax
0x180034ffe  test    eax, eax
0x180035000  js      loc_18003525D
0x180035006  mov     edx, [rsp+270h+var_238]
0x18003500a  lea     r8, [rsp+270h+dwBytes+4]
0x18003500f  mov     ecx, dword ptr [rsp+270h+dwBytes+4]
0x180035013  call    RtlUIntAdd
0x180035018  mov     r14d, eax
0x18003501b  mov     r9d, 10000000h
0x180035021  or      r14d, r9d
0x180035024  mov     dword ptr [rsp+270h+dwBytes], r14d
0x180035029  jl      loc_18003525D
0x18003502f  lea     r8, [rsp+270h+var_238]
0x180035034  mov     [rsp+270h+var_238], esi
0x180035038  mov     edx, r11d
0x18003503b  mov     ecx, r11d
0x18003503e  call    RtlUIntAdd
0x180035043  mov     dword ptr [rsp+270h+dwBytes], eax
0x180035047  mov     r14d, eax
0x18003504a  test    eax, eax
0x18003504c  js      loc_18003525D
0x180035052  mov     edx, [rsp+270h+var_238]
0x180035056  lea     r8, [rsp+270h+dwBytes+4]
0x18003505b  mov     ecx, dword ptr [rsp+270h+dwBytes+4]
0x18003505f  call    RtlUIntAdd
0x180035064  mov     r14d, eax
0x180035067  or      r14d, r9d
0x18003506a  mov     dword ptr [rsp+270h+dwBytes], r14d
0x18003506f  jl      loc_18003525D
0x180035075  lea     r8, [rsp+270h+var_238]
0x18003507a  mov     [rsp+270h+var_238], esi
0x18003507e  mov     edx, r11d
0x180035081  mov     ecx, r11d
0x180035084  call    RtlUIntAdd
0x180035089  mov     dword ptr [rsp+270h+dwBytes], eax
0x18003508d  mov     r14d, eax
0x180035090  test    eax, eax
0x180035092  js      loc_18003525D
0x180035098  mov     edx, [rsp+270h+var_238]
0x18003509c  lea     r8, [rsp+270h+dwBytes+4]
0x1800350a1  mov     ecx, dword ptr [rsp+270h+dwBytes+4]
0x1800350a5  call    RtlUIntAdd
0x1800350aa  mov     r14d, eax
0x1800350ad  or      r14d, r9d
0x1800350b0  mov     dword ptr [rsp+270h+dwBytes], r14d
0x1800350b5  jl      loc_18003525D
0x1800350bb  mov     eax, dword ptr [rsp+270h+dwBytes+4]
0x1800350bf  mov     dword ptr [rbp+170h+lpMem+4], eax
0x1800350c2  mov     esi, eax
0x1800350c4  call    cs:__imp_GetProcessHeap
0x1800350ca  mov     r8d, esi; dwBytes
0x1800350cd  mov     edx, 8; dwFlags
0x1800350d2  mov     rcx, rax; hHeap
0x1800350d5  call    cs:__imp_HeapAlloc
0x1800350db  mov     r9, rax
0x1800350de  test    rax, rax
0x1800350e1  jnz     short loc_1800350F8
0x1800350e3  mov     r14d, 0C0000017h
0x1800350e9  mov     dword ptr [rsp+270h+dwBytes], r14d
0x1800350ee  mov     rsi, [rsp+270h+var_1F8]
0x1800350f3  jmp     loc_18003525D
0x1800350f8  xor     ecx, ecx
0x1800350fa  mov     [rbp+170h+lpMem+8], r9
0x1800350fe  xor     r14d, r14d
0x180035101  mov     qword ptr [rbp+170h+var_1D4], rcx
0x180035105  xor     eax, eax
0x180035107  mov     [rbp-68h], rcx
0x18003510b  mov     dword ptr [rsp+270h+var_234], r14d
0x180035110  mov     dword ptr [rbp+170h+lpMem], eax
0x180035113  test    r9, r9
0x180035116  jnz     short loc_180035168
0x180035118  lea     edx, [rax+4]
0x18003511b  mov     [rsp+270h+var_238], eax
0x18003511f  mov     ecx, edx
0x180035121  lea     r8, [rsp+270h+var_238]
0x180035126  call    RtlUIntAdd
0x18003512b  mov     dword ptr [rsp+270h+dwBytes], eax
0x18003512f  mov     r14d, eax
0x180035132  test    eax, eax
0x180035134  js      loc_180035241
0x18003513a  mov     edx, [rsp+270h+var_238]
0x18003513e  lea     r8, [rbp+170h+lpMem+4]
0x180035142  mov     ecx, dword ptr [rbp+170h+lpMem+4]
0x180035145  call    RtlUIntAdd
0x18003514a  mov     dword ptr [rsp+270h+dwBytes], eax
0x18003514e  mov     r14d, eax
0x180035151  test    eax, eax
0x180035153  js      loc_180035241
0x180035159  lea     esi, [r9+8]
0x18003515d  mov     r11d, 0A0h
0x180035163  jmp     loc_18003520F
0x180035168  xor     r10d, r10d
0x18003516b  mov     [rbp+170h+pcchLength], r9
0x18003516f  mov     r11d, 0A0h
0x180035175  lea     esi, [r10+8]
0x180035179  cmp     r10d, eax
0x18003517c  jnb     short loc_1800351CE
0x18003517e  mov     edx, [r9]
0x180035181  lea     r8, [rsp+270h+var_238]
0x180035186  mov     ecx, 4
0x18003518b  mov     [rsp+270h+var_238], 0
0x180035193  call    RtlUIntAdd
0x180035198  mov     dword ptr [rsp+270h+dwBytes], eax
0x18003519c  mov     r14d, eax
0x18003519f  test    eax, eax
0x1800351a1  js      loc_180035241
0x1800351a7  mov     edx, [rsp+270h+var_238]
0x1800351ab  lea     r8, [rbp+170h+pcchLength]
0x1800351af  mov     rcx, r9
0x1800351b2  call    RtlULongLongAdd
0x1800351b7  mov     dword ptr [rsp+270h+dwBytes], eax
0x1800351bb  mov     r14d, eax
0x1800351be  test    eax, eax
0x1800351c0  js      short loc_180035241
0x1800351c2  mov     r9, [rbp+170h+pcchLength]
0x1800351c6  inc     r10d
0x1800351c9  mov     eax, dword ptr [rbp+170h+lpMem]
0x1800351cc  jmp     short loc_180035179
0x1800351ce  lea     r8, [rbp+170h+var_1D4+4]
  ... truncated ...
```
