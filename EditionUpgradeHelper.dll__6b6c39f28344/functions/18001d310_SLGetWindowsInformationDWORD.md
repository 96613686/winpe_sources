# SLGetWindowsInformationDWORD

- ea: `0x18001d310`
- end: `0x1800264de`
- name: `SLGetWindowsInformationDWORD`
- size: `37326`
- prototype: `HRESULT __stdcall(PCWSTR pwszValueName, DWORD *pdwValue)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180009320`

## callees

- `0x1800018e0`
- `0x1800024d4`
- `0x180006fac`
- `0x180008450`
- `0x180009a2c`
- `0x180009a58`
- `0x18000b35c`
- `0x18000b3a0`
- `0x18000b3cc`
- `0x18000b404`
- `0x18001d310`
- `0x1800264e4`
- `0x180026634`
- `0x18002664c`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18001d7d1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18001ee3e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18002066d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180020c49`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180024237`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18002531d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18001d7d1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18001ee3e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18002066d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180020c49`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180024237`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18002531d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d875`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001eeac`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180020728`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180020d04`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800242f8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002535b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d875`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001eeac`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180020728`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180020d04`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800242f8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002535b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001d39e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001d713`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001d8e4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001d9cd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001dac2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001dc10`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001dcbf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001dde5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001dfaf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001dfcf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e2c6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e738`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e77b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e7af`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e7e1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e80d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e839`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e85a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e88e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e8d2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e974`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e9d1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001ea00`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001ea2f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001ea51`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001eb12`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001ec1e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001ed79`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f06e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f0d5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f12e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f189`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f200`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f22c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f258`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f279`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f31e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f34b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f378`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f399`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001faf1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001fc09`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001fc3c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001fc69`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001fc96`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001fcb7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001fcd5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001fcf3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001fd25`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001fd52`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001fd7f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001fda0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001fdbe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800200f2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002010e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020798`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020d74`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024368`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002449a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002453a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024577`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800247b7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024c27`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024c65`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024c9a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024cc9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024cf5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024d21`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024d42`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024d70`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024dbc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024e65`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024eb8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024ee7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024f16`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024f38`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024ff5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025176`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002526a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002552b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025597`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800255f2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002564a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800256c7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800256f4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025721`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025743`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800257f6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025823`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025850`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025871`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025fe5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180026112`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002613f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180026163`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180026187`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800261a3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800261c3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800261e3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180026210`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180026234`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180026258`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180026274`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180026294`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002631f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002633f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002635b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180026377`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001d39e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001d713`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001d8e4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001d9cd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001dac2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001dc10`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001dcbf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001dde5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001dfaf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001dfcf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e2c6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e738`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e77b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e7af`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e7e1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e80d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e839`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e85a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e88e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e8d2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e974`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e9d1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001ea00`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001ea2f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001ea51`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001eb12`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001ec1e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001ed79`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f06e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f0d5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f12e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f189`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f200`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f22c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f258`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f279`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f31e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f34b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f378`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f399`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001faf1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001fc09`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001fc3c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001fc69`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001fc96`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001fcb7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001fcd5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001fcf3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001fd25`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001fd52`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001fd7f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001fda0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001fdbe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800200f2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002010e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020798`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020d74`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024368`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002449a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002453a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024577`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800247b7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024c27`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024c65`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024c9a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024cc9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024cf5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024d21`

## string_xrefs

- `0x18001ee07`: `ntdll.dll`
- `0x180025309`: `ntdll.dll`
- `0x18001dd27`: `Security-SPP-GenuineLocalStatus`
- `0x18001e069`: `Security-SPP-GenuineLocalStatus`
- `0x18001e143`: `Security-SPP-GenuineLocalStatus`

## pseudocode

```c
HRESULT __stdcall SLGetWindowsInformationDWORD(PCWSTR pwszValueName, DWORD *pdwValue)
{
  HRESULT v2; // ebx
  int v3; // eax
  HANDLE ProcessHeap; // rax
  _BYTE *v5; // rax
  _BYTE *v6; // rdi
  _BYTE *v7; // r14
  __int64 *v8; // rsi
  int v9; // r12d
  int v10; // r10d
  int v11; // r8d
  __int64 v12; // r15
  int v13; // r13d
  int v14; // ecx
  int v15; // ebx
  int v16; // r11d
  int v17; // ebx
  int v18; // edx
  int v19; // r11d
  unsigned int v20; // r8d
  int v21; // r9d
  unsigned int v22; // edx
  int v23; // r10d
  int v24; // r8d
  unsigned int v25; // r9d
  int v26; // r10d
  int v27; // edx
  int v28; // r8d
  unsigned int v29; // r9d
  int v30; // edx
  int v31; // r8d
  unsigned int v32; // r10d
  unsigned int v33; // r8d
  int v34; // r9d
  int v35; // edx
  unsigned int v36; // r8d
  int v37; // r9d
  int v38; // edx
  int v39; // r8d
  unsigned int v40; // r9d
  int v41; // r10d
  int v42; // ecx
  unsigned __int64 v43; // rcx
  char v44; // al
  HANDLE v45; // rax
  __int64 i; // rbx
  HMODULE v47; // rcx
  unsigned int v48; // r12d
  void *v49; // r13
  __int64 v50; // rbx
  HMODULE *v51; // r14
  _BYTE *v52; // rdi
  int v53; // ebx
  __int64 v54; // rax
  char *v55; // rdx
  unsigned int v56; // eax
  __int64 v57; // rsi
  __int64 (__fastcall *ProcAddress)(); // rax
  HANDLE v59; // rax
  const wchar_t *v60; // rsi
  const wchar_t *v61; // r14
  int v62; // r12d
  int v63; // r13d
  __int64 v64; // r15
  signed int v65; // eax
  signed int v66; // ebx
  __int64 v67; // r9
  SIZE_T v68; // rdi
  SIZE_T v69; // r8
  signed int LastError; // eax
  unsigned int v71; // ebx
  HANDLE v72; // rax
  LPVOID v73; // rax
  __int64 (__fastcall *v74)(); // rbx
  DWORD CurrentThreadId; // eax
  __int64 v76; // r15
  __int64 v77; // r9
  SIZE_T v78; // rdi
  SIZE_T v79; // r8
  signed int v80; // eax
  unsigned int v81; // ebx
  HANDLE v82; // rax
  LPVOID v83; // rax
  HANDLE CurrentProcess; // rax
  int v85; // r12d
  HLOCAL v86; // rax
  HANDLE v87; // rax
  _OWORD *v88; // rax
  void *v89; // rdi
  int v90; // r15d
  int v91; // edi
  int v92; // r13d
  HANDLE v93; // rax
  _QWORD *v94; // rax
  void *v95; // rbx
  unsigned int v96; // r11d
  unsigned int v97; // eax
  unsigned int v98; // eax
  unsigned int v99; // ecx
  _DWORD *v100; // r12
  unsigned int v101; // eax
  unsigned int v102; // edx
  unsigned int v103; // eax
  unsigned int v104; // ecx
  __int64 v105; // r15
  HANDLE v106; // rax
  _DWORD *v107; // rax
  int v108; // ecx
  size_t v109; // rdx
  unsigned int v110; // eax
  _DWORD *v111; // r8
  __int64 v112; // r15
  unsigned int v113; // r8d
  unsigned int v114; // r11d
  unsigned int v115; // ecx
  _DWORD *v116; // rdx
  unsigned int v117; // eax
  unsigned __int64 v118; // r10
  HANDLE v119; // rax
  void *v120; // r12
  HANDLE v121; // rax
  unsigned int v122; // ecx
  unsigned int v123; // eax
  SIZE_T v124; // rax
  unsigned int v125; // r11d
  __int64 v126; // r8
  unsigned int v127; // r8d
  unsigned int v128; // eax
  _DWORD *v129; // rdx
  unsigned int v130; // ecx
  unsigned int v131; // eax
  unsigned int v132; // r11d
  __int64 v133; // rdx
  _DWORD *v134; // r8
  unsigned int i7; // ecx
  unsigned int v136; // eax
  unsigned int i8; // r9d
  _DWORD *v138; // r8
  unsigned int v139; // ecx
  unsigned int v140; // eax
  unsigned int v141; // r9d
  size_t v142; // rax
  unsigned int v143; // r15d
  HANDLE v144; // rax
  _DWORD *v145; // rax
  const void *v146; // r10
  char *v147; // r15
  _DWORD *v148; // rdx
  unsigned int v149; // eax
  _BYTE *v150; // rdx
  unsigned __int8 v151; // al
  unsigned __int64 v152; // r8
  unsigned __int8 *v153; // rdi
  int v154; // r9d
  LPCWSTR v155; // r14
  int v156; // r8d
  int v157; // r15d
  unsigned int v158; // r13d
  _BYTE *v159; // r12
  int v160; // r10d
  int v161; // ecx
  int v162; // ebx
  int v163; // r11d
  int v164; // ebx
  int v165; // r11d
  int v166; // edx
  int v167; // r8d
  int v168; // r10d
  int v169; // r8d
  int v170; // r10d
  int v171; // r9d
  int v172; // r8d
  unsigned int v173; // edx
  int v174; // r9d
  int v175; // ecx
  int v176; // edx
  int v177; // r8d
  int v178; // r9d
  int v179; // edx
  unsigned int v180; // r8d
  unsigned int v181; // r9d
  int v182; // edx
  int v183; // r8d
  int v184; // r9d
  unsigned int v185; // edx
  int v186; // r8d
  int v187; // r10d
  int v188; // edx
  int v189; // r9d
  unsigned int v190; // r8d
  unsigned int v191; // r10d
  int v192; // edx
  unsigned int v193; // r9d
  HANDLE v194; // rax
  HANDLE v195; // rax
  int v196; // r15d
  void *v197; // rax
  HANDLE v198; // rax
  SIZE_T v199; // rax
  HANDLE v200; // rax
  HANDLE v201; // rax
  HANDLE v202; // rax
  HANDLE v203; // rax
  _DWORD *v204; // rcx
  SIZE_T v205; // r15
  HANDLE v206; // rax
  void *v207; // rax
  HANDLE v208; // rax
  _OWORD *v209; // rax
  HANDLE v210; // rax
  _QWORD *v211; // rax
  SIZE_T v212; // rax
  HANDLE v213; // rax
  HANDLE v214; // rax
  HANDLE v215; // rax
  HANDLE v216; // rax
  unsigned int v217; // eax
  unsigned int v218; // edx
  unsigned int v219; // r8d
  unsigned int v220; // edx
  unsigned int v221; // eax
  unsigned int v222; // ebx
  HANDLE v223; // rax
  _DWORD *v224; // rax
  void *v225; // rcx
  const void **v226; // rbx
  _DWORD *v227; // r15
  _DWORD *v228; // rcx
  unsigned int *v229; // rdx
  _DWORD *v230; // r15
  _DWORD *v231; // rcx
  _DWORD *v232; // r15
  HANDLE v233; // rax
  unsigned int *v234; // r8
  int v235; // r11d
  unsigned int *v236; // r10
  const WCHAR *v237; // rax
  const WCHAR *v238; // r8
  void *v239; // r15
  unsigned int v240; // r9d
  unsigned int v241; // eax
  unsigned int v242; // ebx
  HANDLE v243; // rax
  void *v244; // rax
  void *v245; // rdx
  void *v246; // r8
  void *v247; // r9
  signed int v248; // eax
  FARPROC v249; // rax
  int v250; // eax
  unsigned int v251; // edx
  SIZE_T v252; // r15
  char *v253; // rcx
  char *v254; // r11
  SIZE_T v255; // r9
  _DWORD *v256; // rcx
  unsigned int v257; // r11d
  unsigned __int64 v258; // r10
  unsigned int v259; // ecx
  unsigned int v260; // r10d
  unsigned int v261; // ecx
  HANDLE v262; // rax
  _QWORD *v263; // rax
  size_t v264; // rbx
  void *v265; // rdi
  HANDLE v266; // rax
  size_t v267; // r12
  void *v268; // rax
  int v269; // r15d
  const void *v270; // rdi
  HANDLE v271; // rax
  SIZE_T v272; // r12
  void *v273; // rax
  unsigned int v274; // eax
  size_t v275; // r12
  HANDLE v276; // rax
  void *v277; // rax
  size_t v278; // rax
  HANDLE v279; // rax
  HANDLE v280; // rax
  HANDLE v281; // rax
  HANDLE v282; // rax
  LPCWSTR *v283; // rcx
  HANDLE v284; // rax
  HANDLE v285; // rax
  HANDLE v286; // rax
  HANDLE v287; // rax
  void *v288; // r15
  _DWORD *v289; // rax
  _DWORD *v290; // r11
  unsigned __int8 v291; // al
  unsigned int v292; // r10d
  unsigned int v293; // esi
  int v294; // r13d
  int v295; // eax
  unsigned __int8 *v296; // r14
  int v297; // ecx
  unsigned int v298; // r8d
  unsigned int v299; // r9d
  unsigned int v300; // r15d
  int v301; // ecx
  unsigned int v302; // edx
  WCHAR *v303; // r14
  char v304; // si
  int v305; // r9d
  SIZE_T v306; // r15
  int v307; // r11d
  SIZE_T v308; // r13
  unsigned __int8 *v309; // rsi
  _BYTE *v310; // r15
  int v311; // r12d
  int v312; // r10d
  int v313; // eax
  int v314; // ecx
  int v315; // edi
  int v316; // ebx
  int v317; // edi
  int v318; // edx
  int v319; // ebx
  unsigned int v320; // r8d
  int v321; // r9d
  unsigned int v322; // edx
  int v323; // r8d
  int v324; // r9d
  unsigned int v325; // edx
  int v326; // r8d
  int v327; // r10d
  int v328; // r11d
  unsigned int v329; // r9d
  int v330; // r8d
  unsigned int v331; // r9d
  int v332; // r10d
  int v333; // r11d
  int v334; // edx
  int v335; // r8d
  unsigned int v336; // r9d
  int v337; // edx
  int v338; // r10d
  int v339; // r8d
  unsigned int v340; // r9d
  int v341; // edx
  int v342; // r8d
  SIZE_T j; // rcx
  int v344; // r15d
  size_t v345; // rax
  _DWORD *v346; // r15
  unsigned int v347; // eax
  size_t v348; // r8
  HANDLE v349; // rax
  void *v350; // rax
  HANDLE v351; // rax
  LPVOID v352; // rax
  HANDLE v353; // rax
  HANDLE v354; // rax
  HANDLE v355; // rax
  HANDLE v356; // rax
  HANDLE v357; // rax
  HANDLE v358; // rax
  LPVOID v359; // rax
  HANDLE v360; // rax
  HANDLE v361; // rax
  HANDLE v362; // rax
  HANDLE v363; // rax
  HANDLE v364; // rax
  int *v365; // r15
  int v366; // r9d
  _DWORD *v367; // rax
  int v368; // r8d
  _DWORD *v369; // rdx
  LPCWSTR *v370; // rdx
  _DWORD *v371; // rax
  int v372; // r8d
  _DWORD *v373; // rdx
  int *v374; // rdx
  int v375; // r15d
  unsigned int *v376; // rax
  int v377; // r8d
  unsigned int *v378; // rdx
  size_t v379; // r9
  _DWORD *v380; // rax
  int v381; // r8d
  _DWORD *v382; // rdx
  unsigned int *v383; // rdx
  int v384; // r8d
  _DWORD *v385; // rax
  unsigned int v386; // r11d
  _DWORD *v387; // rdx
  int *v388; // rdx
  HANDLE v389; // rax
  HANDLE v390; // rax
  DWORD ModuleFileNameW; // eax
  size_t v392; // r12
  __int64 v393; // rax
  unsigned int v394; // edi
  int v395; // eax
  _BYTE *v396; // rax
  _BYTE *v397; // r12
  _BYTE *v398; // rsi
  __int64 *v399; // r14
  __int64 v400; // r15
  int v401; // edi
  int v402; // r13d
  int v403; // r10d
  int v404; // r8d
  int v405; // ecx
  int v406; // ebx
  int v407; // r11d
  int v408; // ebx
  int v409; // edx
  int v410; // r11d
  unsigned int v411; // r8d
  int v412; // r9d
  unsigned int v413; // r10d
  int v414; // edx
  int v415; // r8d
  unsigned int v416; // r9d
  int v417; // r10d
  int v418; // edx
  int v419; // r8d
  unsigned int v420; // r9d
  int v421; // edx
  int v422; // r8d
  unsigned int v423; // r10d
  unsigned int v424; // r8d
  int v425; // r9d
  int v426; // edx
  unsigned int v427; // r8d
  int v428; // r9d
  int v429; // edx
  int v430; // r8d
  unsigned int v431; // r9d
  int v432; // r10d
  int v433; // ecx
  unsigned __int64 v434; // rcx
  char v435; // al
  __int64 m; // rbx
  HMODULE v437; // rcx
  __int64 v438; // rax
  __int64 v439; // rbx
  SIZE_T v440; // r8
  _BYTE *v441; // r12
  __int64 v442; // rax
  int v443; // ebx
  __int64 v444; // rax
  unsigned __int64 v445; // rdx
  int v446; // eax
  unsigned int v447; // ecx
  __int64 v448; // rax
  __int64 (__fastcall *v449)(); // rax
  HANDLE v450; // rax
  int v451; // eax
  const WCHAR *v452; // rax
  WCHAR *v453; // rsi
  __int64 *v454; // r14
  int v455; // eax
  __int64 v456; // r15
  int v457; // edi
  int v458; // r10d
  int v459; // r8d
  int v460; // ecx
  int v461; // ebx
  int v462; // r11d
  int v463; // ebx
  int v464; // edx
  int v465; // r11d
  unsigned int v466; // r8d
  int v467; // r9d
  unsigned int v468; // edx
  int v469; // r10d
  int v470; // r8d
  unsigned int v471; // r9d
  int v472; // r10d
  int v473; // edx
  int v474; // r8d
  unsigned int v475; // r9d
  int v476; // edx
  int v477; // r8d
  unsigned int v478; // r10d
  unsigned int v479; // r8d
  int v480; // r9d
  int v481; // edx
  unsigned int v482; // r8d
  int v483; // r9d
  int v484; // edx
  int v485; // r8d
  unsigned int v486; // r9d
  int v487; // r10d
  int v488; // ecx
  unsigned __int64 v489; // rcx
  WCHAR *v490; // r12
  char v491; // al
  __int64 n; // rbx
  HMODULE v493; // rcx
  __int64 v494; // rax
  __int64 v495; // rbx
  SIZE_T v496; // r8
  WCHAR *v497; // r12
  __int64 v498; // rax
  int v499; // ebx
  __int64 v500; // rax
  unsigned __int64 v501; // rdx
  int v502; // eax
  unsigned int v503; // ecx
  __int64 v504; // rax
  __int64 (__fastcall *v505)(); // rax
  HANDLE v506; // rax
  signed int v507; // eax
  signed int v508; // ebx
  bool v509; // sf
  void *v510; // rax
  char *v511; // r12
  void *v512; // rax
  bool v513; // sf
  WCHAR *v514; // rsi
  unsigned int i6; // r14d
  __int64 v516; // rax
  _DWORD *v517; // rax
  unsigned int v518; // r10d
  unsigned int v519; // edx
  unsigned int i1; // ecx
  __int64 v521; // r12
  __int64 v522; // rcx
  const wchar_t *v523; // rcx
  __int64 i2; // rdx
  __int64 v525; // rax
  _BYTE *v526; // rax
  _BYTE *v527; // r12
  __int64 v528; // rcx
  __int64 *v529; // rbx
  _BYTE *v530; // rsi
  int v531; // r15d
  int v532; // edi
  int v533; // r8d
  int v534; // edx
  __int64 v535; // r14
  int v536; // eax
  int v537; // r11d
  int v538; // r10d
  int v539; // r11d
  int v540; // ecx
  int v541; // r10d
  unsigned int v542; // edx
  int v543; // r8d
  unsigned int v544; // r9d
  int v545; // ecx
  int v546; // edx
  unsigned int v547; // r8d
  int v548; // r9d
  int v549; // ecx
  int v550; // edx
  unsigned int v551; // r8d
  int v552; // ecx
  int v553; // edx
  unsigned int v554; // r9d
  unsigned int v555; // edx
  int v556; // r8d
  int v557; // ecx
  unsigned int v558; // edx
  int v559; // r8d
  int v560; // ecx
  int v561; // edx
  unsigned int v562; // r8d
  int v563; // ecx
  int v564; // edx
  unsigned __int64 v565; // rax
  __m128 v566; // xmm1
  __m128 v567; // xmm0
  __m128 v568; // xmm0
  __m128 v569; // xmm1
  __m128 v570; // xmm1
  __m128 v571; // xmm1
  int v572; // r8d
  unsigned int v573; // edx
  unsigned int i3; // ecx
  __int64 v575; // rax
  void *v576; // rax
  void **v577; // r12
  unsigned int v578; // ecx
  unsigned int v579; // eax
  __int64 v580; // rdx
  __int64 v581; // rax
  __int64 v582; // r9
  int v583; // eax
  void *v584; // rax
  __int64 v585; // r9
  signed int v586; // eax
  __int64 i4; // r14
  _BYTE *v588; // rax
  __int64 v589; // rcx
  __int64 i5; // rcx
  _BYTE *v591; // rax
  signed int v592; // eax
  int v593; // r12d
  int v594; // eax
  int v595; // eax
  unsigned int v596; // ebx
  const WCHAR *v597; // rax
  int v598; // eax
  __int64 v599; // rax
  bool v600; // sf
  unsigned __int16 *v601; // rbx
  int v602; // eax
  __int64 v603; // rax
  bool v604; // sf
  unsigned int v605; // ecx
  unsigned int v606; // eax
  int v607; // eax
  void *v608; // rbx
  void *v609; // rbx
  unsigned int v610; // ebx
  __int64 v611; // rdx
  signed int v612; // eax
  int v613; // eax
  __int64 v614; // rax
  bool v615; // sf
  void *v616; // rbx
  unsigned int v617; // ebx
  int v618; // eax
  int v619; // ebx
  int v620; // r12d
  int v621; // r12d
  __int64 v622; // rax
  int v623; // r12d
  __int64 v624; // rax
  int v625; // edx
  int v626; // eax
  HMODULE v627; // rcx
  unsigned int v628; // ebx
  __int64 v629; // rax
  int v630; // eax
  int v631; // edi
  int v632; // r12d
  LPVOID v633; // rbx
  int v634; // eax
  __int64 v635; // rax
  size_t v636; // rbx
  SIZE_T v637; // rax
  signed int v638; // eax
  signed int v639; // edi
  int v640; // ebx
  int v641; // eax
  void *v642; // rax
  __int64 (__fastcall *v643)(); // rbx
  __int64 v644; // rax
  int v645; // r11d
  int v646; // eax
  int v647; // r10d
  int v648; // r8d
  int v649; // r9d
  int v650; // ecx
  int v651; // edi
  unsigned __int8 v652; // r14
  int v653; // esi
  char *v654; // r15
  char *v655; // rax
  int v656; // r10d
  int v657; // r9d
  char v658; // di
  unsigned __int8 *v659; // r8
  _BYTE *v660; // r11
  char v661; // r15
  unsigned __int8 v662; // dl
  int v663; // r8d
  int v664; // r9d
  int v665; // edx
  int v666; // r8d
  int v667; // ecx
  LPVOID v668; // rbx
  __int64 v669; // rax
  SIZE_T v670; // rax
  SIZE_T v671; // rbx
  SIZE_T v672; // rax
  bool v673; // sf
  void *v674; // rax
  __int64 (__fastcall *v675)(); // rbx
  __int64 v676; // rax
  int v677; // r12d
  int v678; // r10d
  int v679; // r8d
  int v680; // r9d
  int v681; // ecx
  int v682; // r11d
  int v683; // esi
  char *v684; // r14
  char *v685; // rax
  char v686; // bl
  int v687; // r9d
  char v688; // r15
  unsigned __int8 *v689; // r8
  unsigned __int8 v690; // r11
  _BYTE *v691; // r10
  unsigned __int8 v692; // dl
  int v693; // r8d
  int v694; // r9d
  int v695; // edx
  int v696; // r8d
  int v697; // ecx
  LPVOID v698; // r12
  SIZE_T v699; // rdi
  SIZE_T v700; // rbx
  char v701; // al
  int v702; // ebx
  int v703; // r9d
  int v704; // eax
  int v705; // r11d
  int v706; // r8d
  int v707; // edi
  SIZE_T v708; // rax
  __int64 v709; // rax
  size_t v710; // rcx
  int v711; // eax
  int v712; // ebx
  signed int v713; // edi
  const WCHAR *v714; // rax
  bool v715; // sf
  size_t v716; // rbx
  const WCHAR *v717; // rax
  __int64 (__fastcall *v718)(); // rbx
  __int64 v719; // rax
  size_t v720; // rbx
  int v721; // eax
  int v722; // edx
  int v723; // r9d
  int v724; // r11d
  int v725; // r10d
  int v726; // ecx
  int v727; // r8d
  __int64 v728; // r8
  unsigned __int8 v729; // si
  int v730; // r14d
  char *v731; // r15
  char *v732; // rax
  char v733; // bl
  int v734; // r9d
  unsigned __int8 *v735; // r8
  char v736; // r15
  _BYTE *v737; // r10
  unsigned __int8 v738; // dl
  int v739; // r8d
  int v740; // r9d
  int v741; // edx
  int v742; // r8d
  int v743; // ecx
  signed int v744; // edi
  __int64 v745; // rax
  int v746; // ebx
  void *v747; // rax
  bool v748; // sf
  size_t v749; // rbx
  unsigned int v750; // eax
  size_t v751; // rbx
  void *v752; // rax
  __int64 (__fastcall *v753)(); // rbx
  __int64 v754; // rax
  int v755; // r8d
  int v756; // edx
  int v757; // r10d
  int v758; // r9d
  int v759; // ecx
  int v760; // r11d
  int v761; // esi
  const WCHAR *v762; // r14
  _BYTE *v763; // rax
  char v764; // bl
  LPCWSTR v765; // r8
  char v766; // r15
  _BYTE *v767; // r10
  unsigned __int8 v768; // r11
  int v769; // r9d
  unsigned __int8 v770; // dl
  int v771; // r8d
  int v772; // r9d
  int v773; // edx
  int v774; // r8d
  int v775; // ecx
  bool v776; // zf
  _BYTE *v777; // rax
  __int64 v778; // rcx
  __int64 ii; // rcx
  _BYTE *v780; // rax
  __int64 v781; // rcx
  __int64 jj; // rcx
  _BYTE *v783; // rcx
  __int64 v784; // rax
  __int64 v785; // rax
  int v786; // eax
  __int64 kk; // rbx
  HMODULE v788; // rcx
  int v789; // ebx
  int v790; // eax
  int v791; // r12d
  int v792; // eax
  const WCHAR *v793; // rax
  WCHAR *v794; // r12
  __int64 *v795; // r15
  __int64 v796; // rax
  int v797; // esi
  int v798; // r14d
  int v799; // r10d
  int v800; // r8d
  int v801; // ecx
  int v802; // ebx
  int v803; // r11d
  int v804; // ebx
  int v805; // edx
  int v806; // r11d
  unsigned int v807; // r8d
  int v808; // r9d
  unsigned int v809; // r10d
  int v810; // edx
  int v811; // r8d
  unsigned int v812; // r9d
  int v813; // r10d
  int v814; // edx
  int v815; // r8d
  unsigned int v816; // r9d
  int v817; // edx
  int v818; // r8d
  unsigned int v819; // r10d
  unsigned int v820; // r8d
  int v821; // r9d
  int v822; // edx
  unsigned int v823; // r8d
  int v824; // r9d
  int v825; // edx
  int v826; // r8d
  unsigned int v827; // r9d
  int v828; // r10d
  int v829; // ecx
  WCHAR *v830; // rdi
  unsigned __int64 v831; // rcx
  char v832; // al
  __int64 mm; // rbx
  HMODULE v834; // rcx
  unsigned int v835; // r12d
  __int64 v836; // rbx
  size_t v837; // rax
  HMODULE *v838; // r12
  WCHAR *v839; // rdi
  size_t v840; // rcx
  int v841; // ebx
  __int64 v842; // rax
  char *v843; // rdx
  unsigned int v844; // edx
  unsigned int v845; // eax
  __int64 v846; // r12
  __int64 (__fastcall *v847)(); // rax
  int v848; // ecx
  HANDLE v849; // rax
  int v850; // eax
  __int64 nn; // rbx
  HMODULE v852; // rcx
  HANDLE v853; // rax
  _OWORD *v854; // rax
  void *v855; // rdi
  HANDLE v856; // rax
  _QWORD *v857; // rbx
  HANDLE v858; // rax
  unsigned int *v859; // rax
  unsigned int v860; // r10d
  unsigned int *v861; // r12
  int v862; // ecx
  unsigned int *v863; // rdx
  unsigned int v864; // eax
  unsigned int *v865; // r8
  unsigned int v866; // edx
  char *v867; // rcx
  unsigned int v868; // eax
  char *v869; // r11
  char *v870; // r11
  int v871; // r10d
  unsigned __int64 v872; // r8
  unsigned int v873; // ecx
  unsigned int v874; // eax
  LPVOID v875; // rax
  unsigned int v876; // r10d
  HANDLE v877; // rax
  _DWORD *v878; // rax
  int v879; // eax
  unsigned int v880; // edx
  char *v881; // rdx
  unsigned __int8 v882; // al
  unsigned __int64 v883; // r8
  _BYTE *v884; // r13
  LPVOID v885; // r14
  int v886; // r8d
  int v887; // r9d
  unsigned int v888; // r15d
  unsigned __int8 *v889; // rdi
  int v890; // eax
  int v891; // ecx
  int v892; // ebx
  int v893; // r11d
  int v894; // ebx
  int v895; // r11d
  int v896; // r8d
  int v897; // r10d
  int v898; // r8d
  int v899; // r10d
  int v900; // r9d
  int v901; // r8d
  unsigned int v902; // edx
  int v903; // r9d
  int v904; // ecx
  int v905; // edx
  int v906; // r8d
  int v907; // r9d
  int v908; // edx
  unsigned int v909; // r8d
  unsigned int v910; // r9d
  int v911; // edx
  int v912; // r8d
  int v913; // r9d
  int v914; // edx
  int v915; // r8d
  int v916; // r9d
  int v917; // edx
  int v918; // r8d
  unsigned int v919; // ecx
  int v920; // r9d
  int v921; // edx
  void *v922; // rsi
  HANDLE v923; // rax
  HANDLE v924; // rax
  _DWORD *v925; // rax
  void *v926; // rax
  HANDLE v927; // rax
  LPVOID v928; // rax
  HANDLE v929; // rax
  HANDLE v930; // rax
  HANDLE v931; // rax
  HANDLE v932; // rax
  _DWORD *v933; // rcx
  HANDLE v934; // rax
  void *v935; // rcx
  SIZE_T v936; // rax
  HANDLE v937; // rax
  _OWORD *v938; // rcx
  HANDLE v939; // rax
  _QWORD *v940; // rax
  void *v941; // rcx
  HANDLE v942; // rax
  HANDLE v943; // rax
  HANDLE v944; // rax
  HANDLE v945; // rax
  SIZE_T v946; // rcx
  int v947; // eax
  unsigned int v948; // edx
  unsigned int v949; // r8d
  unsigned int v950; // edx
  unsigned int v951; // eax
  unsigned int v952; // ebx
  HANDLE v953; // rax
  _DWORD *v954; // rax
  const void **v955; // rbx
  _DWORD *v956; // rcx
  unsigned int *v957; // rdx
  _DWORD *v958; // rcx
  char *v959; // rax
  SIZE_T v960; // r8
  const WCHAR *v961; // rdx
  int v962; // r10d
  const WCHAR *v963; // r9
  HANDLE v964; // rax
  unsigned int *v965; // rax
  unsigned int *v966; // rdx
  void *v967; // rdx
  unsigned int v968; // r8d
  unsigned int v969; // eax
  unsigned int v970; // ebx
  HANDLE v971; // rax
  void *v972; // rax
  __int128 v973; // rax
  void *v974; // r8
  int v975; // eax
  bool v976; // sf
  FARPROC v977; // rax
  unsigned int v978; // r8d
  SIZE_T v979; // r9
  char *v980; // rcx
  unsigned int v981; // r10d
  SIZE_T v982; // rcx
  unsigned int v983; // ecx
  unsigned int *v984; // rax
  unsigned int v985; // r11d
  unsigned int v986; // ecx
  HANDLE v987; // rax
  _QWORD *v988; // rax
  size_t v989; // rbx
  LPCWSTR v990; // rdi
  HANDLE v991; // rax
  SIZE_T v992; // rsi
  void *v993; // rax
  const void *v994; // rdi
  HANDLE v995; // rax
  LPCWSTR v996; // rsi
  void *v997; // rax
  const void *v998; // rdi
  unsigned int v999; // eax
  size_t v1000; // rsi
  HANDLE v1001; // rax
  void *v1002; // rax
  LPVOID v1003; // rax
  void *v1004; // rcx
  HANDLE v1005; // rax
  HANDLE v1006; // rax
  HANDLE v1007; // rax
  HANDLE v1008; // rax
  LPVOID *v1009; // rcx
  int v1010; // r9d
  unsigned int *v1011; // rax
  HANDLE v1012; // rax
  HANDLE v1013; // rax
  HANDLE v1014; // rax
  HANDLE v1015; // rax
  _DWORD *v1016; // r11
  unsigned __int8 v1017; // al
  unsigned __int64 v1018; // r10
  int v1019; // r10d
  int v1020; // eax
  int v1021; // r15d
  unsigned __int8 *v1022; // r14
  int v1023; // ecx
  unsigned int v1024; // edx
  _BYTE *v1025; // rcx
  unsigned int v1026; // r9d
  unsigned int v1027; // r8d
  unsigned int v1028; // r11d
  int v1029; // r14d
  int v1030; // eax
  char v1031; // r15
  int v1032; // r9d
  int v1033; // r13d
  SIZE_T v1034; // r15
  WCHAR *v1035; // rsi
  int v1036; // r12d
  unsigned int v1037; // r10d
  int v1038; // r11d
  unsigned __int8 *v1039; // rax
  int v1040; // ecx
  int v1041; // edi
  int v1042; // ebx
  int v1043; // edi
  int v1044; // edx
  int v1045; // ebx
  int v1046; // r8d
  int v1047; // r9d
  unsigned int v1048; // edx
  int v1049; // r8d
  int v1050; // r9d
  unsigned int v1051; // edx
  int v1052; // r8d
  int v1053; // r10d
  int v1054; // r11d
  unsigned int v1055; // r9d
  int v1056; // r8d
  unsigned int v1057; // r9d
  int v1058; // r10d
  int v1059; // r11d
  int v1060; // edx
  int v1061; // r8d
  int v1062; // r9d
  int v1063; // edx
  int v1064; // r10d
  int v1065; // r8d
  unsigned int v1066; // edx
  int v1067; // r9d
  int v1068; // r8d
  int v1069; // ecx
  unsigned __int64 v1070; // rcx
  void *v1071; // r14
  void *v1072; // r8
  int v1073; // r9d
  SIZE_T v1074; // r10
  SIZE_T v1075; // r14
  SIZE_T v1076; // r8
  char *v1077; // r9
  LPCWSTR v1078; // r9
  const WCHAR *v1079; // rax
  LPCWSTR v1080; // r10
  int v1081; // r14d
  char *v1082; // rcx
  HANDLE v1083; // rax
  SIZE_T v1084; // r14
  void *v1085; // rax
  HANDLE v1086; // rax
  _QWORD *v1087; // rsi
  void *v1088; // r14
  HANDLE v1089; // rax
  void *v1090; // r14
  HANDLE v1091; // rax
  void *v1092; // r14
  HANDLE v1093; // rax
  HANDLE v1094; // rax
  void *v1095; // rsi
  HANDLE v1096; // rax
  void *v1097; // rsi
  HANDLE v1098; // rax
  _QWORD *v1099; // rsi
  void *v1100; // r14
  HANDLE v1101; // rax
  void *v1102; // r14
  HANDLE v1103; // rax
  void *v1104; // r14
  HANDLE v1105; // rax
  HANDLE v1106; // rax
  void *v1107; // rsi
  HANDLE v1108; // rax
  unsigned int *v1109; // rdx
  int *v1110; // rax
  int v1111; // r8d
  unsigned int *v1112; // rcx
  HANDLE v1113; // rax
  void *v1114; // rsi
  HANDLE v1115; // rax
  HANDLE v1116; // rax
  HANDLE v1117; // rax
  int v1118; // eax
  __int64 k; // rbx
  HMODULE v1120; // rcx
  int v1122; // [rsp+60h] [rbp-A0h]
  unsigned int v1123; // [rsp+60h] [rbp-A0h]
  unsigned int v1124; // [rsp+60h] [rbp-A0h]
  int v1125; // [rsp+60h] [rbp-A0h]
  int v1126; // [rsp+60h] [rbp-A0h]
  int v1127; // [rsp+60h] [rbp-A0h]
  unsigned __int8 v1128; // [rsp+64h] [rbp-9Ch]
  unsigned __int8 v1129; // [rsp+64h] [rbp-9Ch]
  int Src; // [rsp+68h] [rbp-98h]
  _BYTE *Srca; // [rsp+68h] [rbp-98h]
  const void *Srcb; // [rsp+68h] [rbp-98h]
  int Srcc; // [rsp+68h] [rbp-98h]
  LPVOID v1134; // [rsp+70h] [rbp-90h]
  SIZE_T v1135; // [rsp+78h] [rbp-88h] BYREF
  LPVOID v1136; // [rsp+80h] [rbp-80h]
  SIZE_T v1137; // [rsp+88h] [rbp-78h] BYREF
  LPVOID v1138; // [rsp+90h] [rbp-70h]
  LPVOID v1139; // [rsp+98h] [rbp-68h] BYREF
  LPCWSTR lpModuleName; // [rsp+A0h] [rbp-60h]
  size_t pcchLength; // [rsp+A8h] [rbp-58h] BYREF
  LPVOID v1142; // [rsp+B0h] [rbp-50h]
  SIZE_T v1143; // [rsp+B8h] [rbp-48h]
  LPVOID v1144; // [rsp+C0h] [rbp-40h]
  size_t Size; // [rsp+C8h] [rbp-38h]
  SIZE_T v1146; // [rsp+D0h] [rbp-30h]
  LPVOID lpMem; // [rsp+D8h] [rbp-28h] BYREF
  size_t v1148; // [rsp+E0h] [rbp-20h]
  LPVOID v1149; // [rsp+E8h] [rbp-18h]
  LPVOID v1150; // [rsp+F0h] [rbp-10h]
  LPVOID v1151; // [rsp+F8h] [rbp-8h]
  LPVOID v1152; // [rsp+100h] [rbp+0h]
  _OWORD *v1153; // [rsp+108h] [rbp+8h] BYREF
  SIZE_T v1154; // [rsp+110h] [rbp+10h]
  SIZE_T v1155; // [rsp+118h] [rbp+18h] BYREF
  LPVOID v1156; // [rsp+120h] [rbp+20h] BYREF
  SIZE_T v1157; // [rsp+128h] [rbp+28h]
  SIZE_T v1158; // [rsp+130h] [rbp+30h] BYREF
  void *v1159; // [rsp+138h] [rbp+38h]
  int v1160; // [rsp+140h] [rbp+40h]
  SIZE_T v1161; // [rsp+148h] [rbp+48h]
  unsigned int v1162; // [rsp+150h] [rbp+50h] BYREF
  int v1163; // [rsp+154h] [rbp+54h]
  LPCWSTR v1164; // [rsp+158h] [rbp+58h]
  __int128 v1165; // [rsp+160h] [rbp+60h]
  SIZE_T v1166; // [rsp+170h] [rbp+70h]
  unsigned int dwBytes; // [rsp+178h] [rbp+78h] BYREF
  unsigned int dwBytes_4; // [rsp+17Ch] [rbp+7Ch] BYREF
  unsigned int v1169; // [rsp+180h] [rbp+80h] BYREF
  __int64 v1170; // [rsp+188h] [rbp+88h]
  int v1171; // [rsp+190h] [rbp+90h] BYREF
  _BYTE *v1172; // [rsp+198h] [rbp+98h] BYREF
  DWORD *v1173; // [rsp+1A0h] [rbp+A0h] BYREF
  HMODULE phModule; // [rsp+1A8h] [rbp+A8h] BYREF
  HMODULE hModule; // [rsp+1B0h] [rbp+B0h] BYREF
  void *v1176; // [rsp+1B8h] [rbp+B8h]
  __int128 v1177; // [rsp+1C0h] [rbp+C0h] BYREF
  __int128 v1178; // [rsp+1D0h] [rbp+D0h]
  __int128 v1179; // [rsp+1E0h] [rbp+E0h] BYREF
  __int128 v1180; // [rsp+1F0h] [rbp+F0h]
  __int64 v1181; // [rsp+208h] [rbp+108h] BYREF
  __int64 v1182; // [rsp+210h] [rbp+110h] BYREF
  __int64 v1183; // [rsp+218h] [rbp+118h] BYREF
  __int64 v1184; // [rsp+220h] [rbp+120h] BYREF
  __int64 v1185; // [rsp+228h] [rbp+128h] BYREF
  DWORD *v1186; // [rsp+230h] [rbp+130h]
  __int128 v1187; // [rsp+238h] [rbp+138h] BYREF
  _OWORD v1188[3]; // [rsp+288h] [rbp+188h] BYREF
  _QWORD v1189[20]; // [rsp+2C0h] [rbp+1C0h] BYREF
  int v1190; // [rsp+360h] [rbp+260h] BYREF
  int v1191; // [rsp+364h] [rbp+264h]
  void *v1192; // [rsp+368h] [rbp+268h]
  void *v1193; // [rsp+370h] [rbp+270h]
  void *v1194; // [rsp+378h] [rbp+278h]
  WCHAR *v1195; // [rsp+380h] [rbp+280h]
  const WCHAR *v1196; // [rsp+388h] [rbp+288h]
  __int64 v1197; // [rsp+390h] [rbp+290h]
  int v1198; // [rsp+398h] [rbp+298h]
  int v1199; // [rsp+39Ch] [rbp+29Ch] BYREF
  int v1200; // [rsp+3A0h] [rbp+2A0h]
  int v1201; // [rsp+3A4h] [rbp+2A4h]
  int v1202; // [rsp+3A8h] [rbp+2A8h]
  int v1203; // [rsp+3ACh] [rbp+2ACh] BYREF
  int v1204; // [rsp+3B0h] [rbp+2B0h]
  int v1205; // [rsp+3B4h] [rbp+2B4h]
  unsigned int v1206; // [rsp+3B8h] [rbp+2B8h]
  unsigned int v1207; // [rsp+3BCh] [rbp+2BCh] BYREF
  unsigned int v1208; // [rsp+3C0h] [rbp+2C0h]
  unsigned int v1209; // [rsp+3C4h] [rbp+2C4h]
  unsigned int v1210; // [rsp+3C8h] [rbp+2C8h]
  int v1211; // [rsp+3D0h] [rbp+2D0h] BYREF
  _DWORD v1212[3]; // [rsp+3D4h] [rbp+2D4h] BYREF
  __int16 v1213; // [rsp+3E2h] [rbp+2E2h]
  __int64 v1214; // [rsp+3E8h] [rbp+2E8h]
  int v1215; // [rsp+440h] [rbp+340h] BYREF
  _DWORD v1216[5]; // [rsp+444h] [rbp+344h] BYREF
  SIZE_T v1217; // [rsp+458h] [rbp+358h]
  int v1218; // [rsp+4B0h] [rbp+3B0h] BYREF
  _DWORD v1219[5]; // [rsp+4B4h] [rbp+3B4h] BYREF
  size_t v1220; // [rsp+4C8h] [rbp+3C8h]
  int v1221; // [rsp+520h] [rbp+420h] BYREF
  _DWORD v1222[5]; // [rsp+524h] [rbp+424h] BYREF
  SIZE_T v1223; // [rsp+538h] [rbp+438h]
  int v1224; // [rsp+590h] [rbp+490h] BYREF
  _DWORD v1225[5]; // [rsp+594h] [rbp+494h] BYREF
  SIZE_T v1226; // [rsp+5A8h] [rbp+4A8h]
  int v1227; // [rsp+600h] [rbp+500h] BYREF
  char v1228[20]; // [rsp+604h] [rbp+504h] BYREF
  SIZE_T v1229; // [rsp+618h] [rbp+518h]
  int v1230; // [rsp+670h] [rbp+570h] BYREF
  char v1231[20]; // [rsp+674h] [rbp+574h] BYREF
  SIZE_T v1232; // [rsp+688h] [rbp+588h]
  int v1233; // [rsp+6E0h] [rbp+5E0h] BYREF
  char v1234[20]; // [rsp+6E4h] [rbp+5E4h] BYREF
  SIZE_T v1235; // [rsp+6F8h] [rbp+5F8h]
  int v1236; // [rsp+750h] [rbp+650h] BYREF
  char v1237[20]; // [rsp+754h] [rbp+654h] BYREF
  const WCHAR *v1238; // [rsp+768h] [rbp+668h]
  __int128 v1239; // [rsp+7C0h] [rbp+6C0h] BYREF
  __int128 v1240; // [rsp+7D0h] [rbp+6D0h] BYREF
  __int128 v1241; // [rsp+7E0h] [rbp+6E0h] BYREF
  __int128 v1242; // [rsp+7F0h] [rbp+6F0h] BYREF
  __int64 v1243; // [rsp+800h] [rbp+700h] BYREF
  int v1244; // [rsp+808h] [rbp+708h]
  int v1245; // [rsp+80Ch] [rbp+70Ch]
  _DWORD v1246[12]; // [rsp+810h] [rbp+710h] BYREF
  __int128 v1247; // [rsp+840h] [rbp+740h] BYREF
  __int128 v1248; // [rsp+850h] [rbp+750h] BYREF
  __int64 v1249; // [rsp+860h] [rbp+760h]
  __int128 v1250; // [rsp+868h] [rbp+768h] BYREF
  _OWORD v1251[2]; // [rsp+878h] [rbp+778h] BYREF
  __int128 v1252; // [rsp+898h] [rbp+798h] BYREF
  _OWORD v1253[2]; // [rsp+8A8h] [rbp+7A8h] BYREF
  __int128 v1254; // [rsp+8C8h] [rbp+7C8h] BYREF
  _OWORD v1255[2]; // [rsp+8D8h] [rbp+7D8h] BYREF
  __int128 v1256; // [rsp+8F8h] [rbp+7F8h] BYREF
  _OWORD v1257[2]; // [rsp+908h] [rbp+808h] BYREF
  __int128 v1258; // [rsp+928h] [rbp+828h] BYREF
  __int128 v1259; // [rsp+938h] [rbp+838h] BYREF
  __int64 v1260; // [rsp+948h] [rbp+848h]
  _OWORD v1261[2]; // [rsp+950h] [rbp+850h] BYREF
  _DWORD v1262[6]; // [rsp+970h] [rbp+870h] BYREF
  char v1263; // [rsp+98Ah] [rbp+88Ah]
  unsigned __int16 v1264[34]; // [rsp+98Ch] [rbp+88Ch] BYREF
  _DWORD v1265[6]; // [rsp+9D0h] [rbp+8D0h] BYREF
  char v1266; // [rsp+9EAh] [rbp+8EAh]
  unsigned __int16 v1267[34]; // [rsp+9ECh] [rbp+8ECh] BYREF
  _DWORD v1268[6]; // [rsp+A30h] [rbp+930h] BYREF
  char v1269; // [rsp+A4Ah] [rbp+94Ah]
  unsigned __int16 v1270[34]; // [rsp+A4Ch] [rbp+94Ch] BYREF
  _BYTE v1271[68]; // [rsp+A90h] [rbp+990h] BYREF
  __int16 v1272; // [rsp+AD4h] [rbp+9D4h]
  unsigned __int16 v1273; // [rsp+B36h] [rbp+A36h]
  int v1274; // [rsp+B3Ch] [rbp+A3Ch]
  int v1275; // [rsp+B40h] [rbp+A40h]
  int v1276; // [rsp+B70h] [rbp+A70h] BYREF
  __int128 v1277; // [rsp+B78h] [rbp+A78h]
  __int128 v1278; // [rsp+B88h] [rbp+A88h]
  __int128 v1279; // [rsp+B98h] [rbp+A98h]
  __int64 v1280; // [rsp+BA8h] [rbp+AA8h]
  _BYTE v1281[176]; // [rsp+BB0h] [rbp+AB0h] BYREF
  WCHAR Filename[264]; // [rsp+C60h] [rbp+B60h] BYREF

  v1186 = pdwValue;
  v1173 = 0;
  if ( pdwValue )
  {
    LODWORD(v1148) = 0;
    v1155 = 0;
    while ( _InterlockedCompareExchange(&dword_18002F8EC, 1, 0) )
      ;
    v3 = dword_18002F8E8;
    v1163 = -1;
    if ( dword_18002F8E8 )
      goto LABEL_46;
    ProcessHeap = GetProcessHeap();
    v5 = HeapAlloc(ProcessHeap, 0, 0x338u);
    v6 = v5;
    if ( !v5 )
      goto LABEL_13;
    v7 = v5;
    v8 = qword_18002B6E0;
    v9 = 0;
    v10 = 0;
    v11 = 0;
    v12 = 103;
    v13 = -1;
    do
    {
      v14 = *(unsigned __int8 *)v8 << 8;
      v15 = *((unsigned __int8 *)v8 + 1);
      v16 = *((unsigned __int8 *)v8++ + 4);
      v17 = *((unsigned __int8 *)v8 - 5) | ((*((unsigned __int8 *)v8 - 6) | ((v14 | v15) << 8)) << 8);
      v18 = v11 ^ v17;
      v19 = *((unsigned __int8 *)v8 - 1)
          | ((*((unsigned __int8 *)v8 - 2) | ((*((unsigned __int8 *)v8 - 3) | (v16 << 8)) << 8)) << 8);
      v20 = v10 ^ v19 ^ v11 ^ v17 ^ 0xAC987321;
      v21 = v18 ^ (__ROR4__(v20, 22) + 4991 * __ROR4__(v20 + 1419157410, 27));
      v22 = v20 ^ (43881 * __ROR4__(v21 + 133239679, 9) - __ROR4__(v21, 30));
      v23 = v21 ^ (24670 * v22 - (v22 >> 13) - 123127970);
      v24 = v22 ^ (2033 * __ROR4__(v23 ^ 0xAB69, 26) - __ROR4__(v23, 30));
      v25 = v23 ^ (133239679 - (v24 ^ 0xAB69605E));
      v26 = v24 ^ (43881 * (v25 ^ 0x137F)) ^ __ROR4__(v25, 6);
      v27 = v25 ^ (__ROR4__(v26, 30) + 24670 * __ROR4__(v26 + 133239679, 15));
      v28 = v26 ^ (2033 * __ROR4__(v27 + 1419157410, 14) - __ROR4__(v27, 24));
      v29 = v27 ^ __ROR4__(v28, 10) ^ (4991 * __ROR4__(v28 ^ 0xAB69605E, 12));
      v30 = v28 ^ (v29 >> 10) ^ (43881 * (v29 ^ 0x7F1));
      v31 = v29 ^ (2033 * (__ROR4__(~v30, 5) + 24670));
      v32 = v31 ^ (((v30 ^ (v31 - 2033) ^ 0xAB69605E) >> 2) + 4991 * __ROR4__(v30 ^ (v31 - 2033) ^ 0xAB6967AF, 30));
      v33 = v30 ^ (v31 - 2033) ^ 0xAB69605E ^ (__ROR4__(v32, 25) + 43881 * __ROR4__(v32 - 133239679, 6));
      v34 = v32 ^ (24670 * (v33 ^ 0x137F) + __ROR4__(v33, 9));
      v35 = v33 ^ (__ROR4__(v34, 25) + 2033 * __ROR4__(v34 ^ 0xAB69, 27));
      v36 = v34 ^ v35 ^ 0xAC987321;
      v37 = v35 ^ (4991 * __ROR4__(v36, 3) - 219010071);
      v38 = v36 ^ (24670 * __ROR4__(v37 - 133239679, 1) - __ROR4__(v37, 6));
      v39 = v37 ^ (__ROR4__(v38, 18) + 2033 * __ROR4__(v38 - 1419157410, 29));
      v40 = v38 ^ (4991 * __ROR4__(v39 - 1419157410, 17) - __ROR4__(v39, 14));
      v41 = v39 ^ (v40 >> 3) ^ (43881 * (v40 ^ 0x605E));
      v42 = __ROR4__(v41, 30);
      v10 = v13 ^ v41;
      v13 = v19;
      v11 = v9 ^ v40 ^ v42 ^ (24670 * __ROR4__(v39 ^ (v40 >> 3) ^ (43881 * (v40 ^ 0x605E)) ^ 0x7F1137F, 28));
      v9 = v17;
      v7[3] = v11;
      v7[7] = v10;
      v7[2] = __ROR4__(v11, 8);
      v7[6] = __ROR4__(v10, 8);
      v7[1] = __ROR4__(v11, 16);
      v7[5] = __ROR4__(v10, 16);
      *v7 = __ROR4__(v11, 24);
      v7[4] = __ROR4__(v10, 24);
      v7 += 8;
      --v12;
    }
    while ( v12 );
    v43 = 0;
    v44 = 0;
    do
      v44 ^= v6[v43++];
    while ( v43 < 0x338 );
    if ( v44 != 64 )
    {
      v45 = GetProcessHeap();
      HeapFree(v45, 0, v6);
      goto LABEL_13;
    }
    LODWORD(Size) = 0;
    v6[823] = 0;
    v48 = 0;
    memset_0(qword_18002F860, 0, sizeof(qword_18002F860));
    v49 = v6;
    if ( *v6 )
    {
      while ( 1 )
      {
        v50 = -1;
        do
          ++v50;
        while ( *(_WORD *)&v6[2 * v50] );
        v51 = (HMODULE *)&qword_18002F860[3 * v48];
        if ( !GetModuleHandleExW(0, (LPCWSTR)v6, v51) )
          break;
        v52 = &v6[2 * v50];
        if ( *(_WORD *)*v51 == 23117
          && (v54 = *((int *)*v51 + 15), (unsigned int)v54 < 0x10000000)
          && (v55 = (char *)*v51 + v54, v55 >= (char *)*v51)
          && *(_DWORD *)v55 == 17744 )
        {
          if ( ((*((_WORD *)v55 + 12) - 267) & 0xFEFF) != 0 )
          {
            v53 = -1073741811;
          }
          else
          {
            *(__int64 *)((char *)&qword_18002F860[3 * v48 + 1] + 4) = *((_QWORD *)v55 + 17);
            v53 = 0;
            LODWORD(qword_18002F860[3 * v48 + 1]) = *((_DWORD *)v55 + 20);
          }
        }
        else
        {
          v53 = -1073741701;
        }
        v56 = *(_DWORD *)(v52 + 2);
        v6 = v52 + 6;
        LODWORD(v1146) = v56;
        if ( v56 )
        {
          do
          {
            v57 = -1;
            do
              ++v57;
            while ( v6[v57] );
            if ( v53 >= 0 )
            {
              ProcAddress = GetProcAddress(*v51, v6);
              if ( !ProcAddress )
                goto LABEL_40;
              off_18002F000[(unsigned int)Size] = ProcAddress;
              v56 = v1146;
            }
            v6 += v57 + 1;
            LODWORD(Size) = Size + 1;
            LODWORD(v12) = v12 + 1;
          }
          while ( (unsigned int)v12 < v56 );
        }
        ++v48;
        LODWORD(v12) = 0;
        if ( !*v6 )
          goto LABEL_40;
      }
      v53 = -1073741702;
LABEL_40:
      if ( !v49 )
        goto LABEL_44;
    }
    else
    {
      v53 = 0;
    }
    v59 = GetProcessHeap();
    HeapFree(v59, 0, v49);
LABEL_44:
    if ( v53 < 0 )
    {
LABEL_13:
      for ( i = 0; i != 4; ++i )
      {
        v47 = (HMODULE)qword_18002F860[3 * i];
        if ( v47 )
          FreeLibrary(v47);
      }
      memset_0(qword_18002F860, 0, sizeof(qword_18002F860));
      memcpy_0(off_18002F000, off_180028410, 0x170u);
LABEL_47:
      v1135 = 0;
      _InterlockedExchange(&dword_18002F8EC, 0);
      v60 = 0;
      v61 = 0;
      v1137 = 0;
      v62 = 0;
      if ( NtCurrentPeb()->SessionId )
      {
        v63 = 0;
        v64 = off_18002F110[0]();
        if ( !v64 )
          goto LABEL_49;
        dwBytes = 0;
        v67 = 0;
        pcchLength = 0;
        v68 = 0;
        while ( 1 )
        {
          v69 = 0;
          if ( v68 )
            v69 = v68;
          if ( ((unsigned int (__fastcall *)(__int64, __int64, SIZE_T, __int64, unsigned int *))off_18002F130[0])(
                 v64,
                 2,
                 v69,
                 v67,
                 &dwBytes) )
          {
            v1135 = v68;
            v66 = 0;
            v60 = (const wchar_t *)v68;
            goto LABEL_69;
          }
          LastError = GetLastError();
          v66 = LastError;
          if ( LastError != 122 )
            break;
          if ( v68 )
          {
            v66 = -2147467259;
            goto LABEL_70;
          }
          v71 = dwBytes;
          v72 = GetProcessHeap();
          v73 = HeapAlloc(v72, 0, v71);
          v68 = (SIZE_T)v73;
          if ( !v73 )
          {
            v66 = -2147024882;
LABEL_69:
            pcchLength = 0;
            goto LABEL_70;
          }
          v67 = dwBytes;
          pcchLength = (size_t)v73;
        }
        if ( LastError )
        {
          if ( LastError > 0 )
            v66 = (unsigned __int16)LastError | 0x80070000;
        }
        else
        {
          v66 = -2147467259;
        }
LABEL_70:
        SP<unsigned short *,SP_MEM<unsigned short *>>::Reset(&pcchLength);
        if ( v66 < 0 )
          goto LABEL_98;
        v74 = off_18002F128[0];
        CurrentThreadId = GetCurrentThreadId();
        v76 = ((__int64 (__fastcall *)(_QWORD))v74)(CurrentThreadId);
        if ( !v76 )
          goto LABEL_49;
        dwBytes_4 = 0;
        v77 = 0;
        pcchLength = 0;
        v78 = 0;
        while ( 1 )
        {
          v79 = 0;
          if ( v78 )
            v79 = v78;
          if ( ((unsigned int (__fastcall *)(__int64, __int64, SIZE_T, __int64, unsigned int *))off_18002F130[0])(
                 v76,
                 2,
                 v79,
                 v77,
                 &dwBytes_4) )
          {
            v1137 = v78;
            v66 = 0;
            v61 = (const wchar_t *)v78;
            goto LABEL_87;
          }
          v80 = GetLastError();
          v66 = v80;
          if ( v80 != 122 )
            break;
          if ( v78 )
          {
            v66 = -2147467259;
            goto LABEL_88;
          }
          v81 = dwBytes_4;
          v82 = GetProcessHeap();
          v83 = HeapAlloc(v82, 0, v81);
          v78 = (SIZE_T)v83;
          if ( !v83 )
          {
            v66 = -2147024882;
LABEL_87:
            pcchLength = 0;
            goto LABEL_88;
          }
          v77 = dwBytes_4;
          pcchLength = (size_t)v83;
        }
        if ( v80 )
        {
          if ( v80 > 0 )
            v66 = (unsigned __int16)v80 | 0x80070000;
        }
        else
        {
          v66 = -2147467259;
        }
LABEL_88:
        SP<unsigned short *,SP_MEM<unsigned short *>>::Reset(&pcchLength);
        if ( v66 < 0 )
          goto LABEL_98;
        if ( !v60 || wcscmp_0(v60, L"WinSta0") || !v61 || wcscmp_0(v61, L"Default") )
          goto LABEL_97;
        v1171 = 0;
        CurrentProcess = GetCurrentProcess();
        if ( !(unsigned int)GetProcessMitigationPolicy(CurrentProcess, 11, &v1171) )
        {
LABEL_49:
          v65 = GetLastError();
          v66 = v65;
          if ( v65 > 0 )
            v66 = (unsigned __int16)v65 | 0x80070000;
          if ( v66 >= 0 )
            v66 = -2147467259;
          goto LABEL_98;
        }
        if ( (v1171 & 0xF) == 0 )
          v62 = 1;
      }
      else
      {
        v66 = 0;
      }
LABEL_97:
      v63 = v62;
LABEL_98:
      SP<unsigned short *,SP_MEM<unsigned short *>>::Reset(&v1137);
      SP<unsigned short *,SP_MEM<unsigned short *>>::Reset(&v1135);
      v85 = 0;
      if ( v66 >= 0 )
        v85 = v63;
      v1122 = v85;
      v86 = LocalAlloc(0x40u, 4u);
      SP_HLOCAL<unsigned char>::operator=(&v1155, v86);
      v1176 = (void *)v1155;
      if ( !v1155 )
      {
        v90 = -2147024882;
        goto LABEL_103;
      }
      v87 = GetProcessHeap();
      v88 = HeapAlloc(v87, 8u, 0xA0u);
      v89 = v88;
      if ( !v88 )
      {
        v90 = -1073741801;
LABEL_103:
        v91 = 0;
        goto LABEL_1477;
      }
      v92 = 0;
      v1160 = 0;
      *v88 = xmmword_18002F4B0;
      v88[1] = xmmword_18002F4C0;
      v88[2] = xmmword_18002F4D0;
      v88[3] = xmmword_18002F4E0;
      v88[4] = xmmword_18002F4F0;
      v88[5] = xmmword_18002F500;
      v88[6] = xmmword_18002F510;
      v88[7] = xmmword_18002F520;
      v88[8] = xmmword_18002F530;
      v88[9] = xmmword_18002F540;
      v93 = GetProcessHeap();
      v94 = HeapAlloc(v93, 8u, 8u);
      v1161 = 196;
      v95 = v94;
      if ( !v94 )
      {
        v90 = -1073741801;
        v95 = 0;
LABEL_540:
        Src = v90;
        goto LABEL_541;
      }
      *v94 = qword_18002F3F8;
      v1158 = __rdtsc();
      pcchLength = 0;
      if ( StringCchLengthW(L"Security-SPP-GenuineLocalStatus", (unsigned __int64)HIDWORD(v1158) << 32, &pcchLength) < 0 )
      {
        v90 = -1073741762;
LABEL_539:
        v1122 = v85;
        goto LABEL_540;
      }
      v97 = 2 * pcchLength + 6;
      if ( v97 < 4 )
      {
        v90 = -1073741675;
        goto LABEL_539;
      }
      v98 = v96 + v97;
      lpMem = 0;
      LODWORD(v1143) = 0;
      v99 = -1;
      v100 = 0;
      if ( v98 >= v96 )
        v99 = v98;
      v90 = v98 < v96 ? -805306219 : 0x10000000;
      Src = v90;
      if ( v98 < v96 )
        goto LABEL_147;
      v101 = v99 + 8;
      v102 = -1;
      if ( v99 + 8 >= v99 )
        v102 = v99 + 8;
      v90 = v101 < v99 ? -805306219 : 0x10000000;
      Src = v90;
      if ( v101 < v99 )
        goto LABEL_147;
      v103 = v102 + 8;
      v104 = -1;
      if ( v102 + 8 >= v102 )
        v104 = v102 + 8;
      LODWORD(v1146) = v104;
      v90 = v103 < v102 ? -805306219 : 0x10000000;
      Src = v90;
      if ( v103 < v102 )
        goto LABEL_147;
      v105 = v104;
      v106 = GetProcessHeap();
      v107 = HeapAlloc(v106, 8u, (unsigned int)v105);
      v100 = v107;
      if ( !v107 )
      {
        v90 = -1073741801;
        goto LABEL_540;
      }
      if ( v107 + 1 < v107 )
        goto LABEL_145;
      if ( v107 + 2 > (_DWORD *)((char *)v107 + v105) )
      {
LABEL_122:
        v90 = -1073741789;
LABEL_146:
        Src = v90;
LABEL_147:
        if ( v90 < 0 )
          goto LABEL_151;
LABEL_148:
        if ( (_DWORD)v1143 )
          v90 = v1143;
        goto LABEL_150;
      }
      *v107 = 4;
      v108 = 0;
      v107[1] = 0;
      v109 = (size_t)v107;
      do
      {
        if ( *(_DWORD *)v109 >= 0xFFFFFFFC )
          goto LABEL_145;
        v110 = *(_DWORD *)v109 + 4;
        v111 = (_DWORD *)(v109 + v110);
        if ( (unsigned __int64)v111 < v109 )
          goto LABEL_145;
        v109 += v110;
        ++v108;
      }
      while ( !v108 );
      if ( v111 + 1 < v111 )
        goto LABEL_145;
      v112 = (unsigned int)v1146;
      if ( v111 + 41 > (_DWORD *)((char *)v100 + (unsigned int)v1146) )
        goto LABEL_122;
      *v111 = 160;
      if ( v89 )
        memcpy_0(v111 + 1, v89, 0xA0u);
      if ( !v95 )
      {
        v90 = -1073741811;
        goto LABEL_146;
      }
      if ( v100 )
      {
        v115 = 0;
        LODWORD(v1154) = 2;
        v116 = v100;
        do
        {
          v117 = *v116 + 4;
          if ( *v116 >= 0xFFFFFFFC )
            goto LABEL_135;
          v118 = (unsigned __int64)v116 + v117;
          if ( v118 < (unsigned __int64)v116 )
            goto LABEL_135;
          ++v115;
          v116 = (_DWORD *)((char *)v116 + v117);
        }
        while ( v115 < 2 );
        lpModuleName = (LPCWSTR)(v118 + 4);
        if ( v118 + 4 >= v118 )
        {
          if ( v116 + 3 > (_DWORD *)((char *)v100 + v112) )
          {
            v90 = -1073741789;
            goto LABEL_146;
          }
          *v116 = 8;
          memcpy_0((void *)lpModuleName, v95, 8u);
          v114 = v1154 + 1;
          LODWORD(v1150) = v112;
          v109 = (size_t)v100;
          v122 = 0;
          if ( (_DWORD)v1154 != -1 )
          {
            do
            {
              v123 = *(_DWORD *)v109 + 4;
              if ( *(_DWORD *)v109 >= 0xFFFFFFFC || v109 + v123 < v109 )
                goto LABEL_145;
              ++v122;
              v109 += v123;
            }
            while ( v122 < v114 );
          }
          if ( v109 + 4 < v109 )
            goto LABEL_145;
          if ( v109 + 12 > (unsigned __int64)v100 + (unsigned int)v112 )
            goto LABEL_122;
          v124 = v1158;
          *(_DWORD *)v109 = 8;
          *(_QWORD *)(v109 + 4) = v124;
LABEL_164:
          pcchLength = 0;
          LODWORD(v1154) = v114 + 1;
          if ( StringCchLengthW(L"Security-SPP-GenuineLocalStatus", v109, &pcchLength) < 0 )
          {
            v90 = -1073741762;
LABEL_535:
            Src = v90;
            goto LABEL_151;
          }
          if ( pcchLength + 1 < pcchLength )
          {
            v90 = -1073741675;
            goto LABEL_535;
          }
          v126 = (unsigned int)(2 * (pcchLength + 1));
          if ( (_DWORD)v126 )
          {
            if ( v100 )
            {
              v129 = v100;
              v130 = 0;
              if ( !v125 )
              {
LABEL_178:
                if ( v129 + 1 < v129 )
                {
                  v90 = -1073741675;
                }
                else
                {
                  if ( (char *)v129 + v126 + 4 <= (char *)v100 + (unsigned int)v112 )
                  {
                    *v129 = v126;
                    v90 = 0;
                    Src = 0;
                    memcpy_0(v129 + 1, L"Security-SPP-GenuineLocalStatus", (unsigned int)v126);
                    v128 = (unsigned int)v1150;
                    v125 = v1154 + 1;
                    goto LABEL_186;
                  }
                  v90 = -1073741789;
                }
                goto LABEL_184;
              }
              while ( 1 )
              {
                v131 = *v129 + 4;
                if ( *v129 >= 0xFFFFFFFC || (_DWORD *)((char *)v129 + v131) < v129 )
                  break;
                ++v130;
                v129 = (_DWORD *)((char *)v129 + v131);
                if ( v130 >= v125 )
                  goto LABEL_178;
              }
            }
            else
            {
              v127 = v126 + 4;
              if ( v127 >= 4 )
              {
                v128 = v112 + v127;
                if ( (unsigned int)v112 + v127 >= (unsigned int)v112 )
                {
                  ++v125;
                  Src = 0;
                  v90 = 0;
LABEL_186:
                  if ( v90 < 0 )
                    goto LABEL_151;
                  if ( !v100 )
                  {
                    if ( v128 + 8 < v128 )
                      goto LABEL_145;
                    v132 = v125 + 1;
                    i8 = v128 + 16;
                    LODWORD(Size) = v128 + 16;
                    if ( v128 + 16 < v128 + 8 )
                      goto LABEL_145;
LABEL_206:
                    LODWORD(v1154) = v132 + 1;
                    lpModuleName = (LPCWSTR)__rdtsc();
                    v141 = i8 + 8;
                    if ( v141 < 8 || (v142 = (v141 + 7) & 0xFFFFFFF8, pcchLength = v142, (unsigned int)v142 < v141) )
                    {
                      v90 = -805306219;
                      goto LABEL_535;
                    }
                    LODWORD(v1149) = 0;
                    v143 = (v141 + 7) & 0xFFFFFFF8;
                    v1137 = (unsigned int)v142;
                    v144 = GetProcessHeap();
                    v145 = HeapAlloc(v144, 8u, v143);
                    v146 = 0;
                    v1134 = v145;
                    v147 = (char *)v145;
                    if ( !v145 )
                    {
                      v90 = -805306345;
                      Src = -805306345;
                      goto LABEL_470;
                    }
                    v148 = v145 + 1;
                    *v145 = v1154;
                    if ( v145 + 1 < v145 || (v149 = Size, *v148 = Size, v147 + 8 < v147 + 4) )
                    {
                      v1137 = (SIZE_T)v1134;
                      LODWORD(pcchLength) = 0;
                      v194 = GetProcessHeap();
                      HeapFree(v194, 0, (LPVOID)v1137);
                      v90 = -805306219;
                      Src = -805306219;
                      goto LABEL_469;
                    }
                    *(_QWORD *)&v147[v1137 - 8] = lpModuleName;
                    memcpy_0(v147 + 8, v100, v149);
                    v1137 = 0;
                    v1139 = 0;
                    v1138 = 0;
                    v1144 = 0;
                    v1152 = 0;
                    v1150 = 0;
                    if ( !(_DWORD)pcchLength
                      || (v1143 = (unsigned int)pcchLength + 8LL, Srca = MemoryAlloc(v1143), (v150 = Srca) == 0) )
                    {
                      v90 = -805306367;
                      Src = -805306367;
                      goto LABEL_446;
                    }
                    v151 = 0;
                    v1128 = 0;
                    v152 = 0;
                    if ( (_DWORD)pcchLength )
                    {
                      do
                        v151 ^= v147[v152++];
                      while ( v152 < (unsigned int)pcchLength );
                      v1128 = v151;
                    }
                    v1151 = v89;
                    v1157 = (SIZE_T)v95;
                    v1153 = v100;
                    Size = 0xC81ECB17B1B54A58uLL;
                    lpModuleName = (LPCWSTR)((unsigned __int64)(unsigned int)pcchLength >> 3);
                    v1134 = v147;
                    if ( lpModuleName )
                    {
                      v153 = (unsigned __int8 *)v147;
                      v154 = WORD1(Size);
                      v155 = lpModuleName;
                      v156 = 0;
                      v157 = WORD2(Size);
                      v158 = HIDWORD(Size) ^ 0xB1B54A58;
                      v1135 = 0;
                      v159 = Srca;
                      LODWORD(v1136) = 0;
                      LODWORD(v1142) = 0;
                      v160 = -1;
                      LODWORD(v1159) = WORD1(Size);
                      do
                      {
                        v161 = *v153;
                        v162 = v153[1];
                        v163 = v153[4];
                        v153 += 8;
                        v164 = *(v153 - 5) | ((*(v153 - 6) | (((v161 << 8) | v162) << 8)) << 8);
                        v165 = *(v153 - 1) | ((*(v153 - 2) | ((*(v153 - 3) | (v163 << 8)) << 8)) << 8);
                        v166 = v160 ^ v165;
                        v167 = v156 ^ v164 ^ ((v160 ^ v165) - 19032);
                        v168 = __ROR4__(v167, 15);
                        v169 = HIDWORD(Size) ^ v167;
                        v170 = v166 ^ (__ROR4__(v169, 7) + v154 * v168);
                        v171 = v169 ^ (v157 * __ROR4__(v170 - 1313519016, 9) - __ROR4__(v170, 10));
                        v172 = v170 ^ (__ROR4__(v171, 27) + HIWORD(Size) * __ROR4__(v157 ^ v171, 28));
                        v173 = v171 ^ (HIDWORD(Size) - (v172 ^ 0xB1B54A58));
                        v174 = v172 ^ (WORD1(Size) * (v173 - 19032) - (v173 >> 6));
                        v175 = v173 ^ (19032 * (v157 ^ __ROR4__(v174, 15)));
                        v176 = v174 ^ (v157 * (HIWORD(Size) + __ROR4__(~v175, 3)));
                        v177 = v175 ^ (v176 - HIDWORD(Size) - 19032);
                        v178 = v176 ^ ((_DWORD)v1159 * (HIWORD(Size) ^ v177)) ^ __ROR4__(v177, 10);
                        v179 = v177 ^ __ROR4__(v178, 3) ^ (v157 * __ROR4__(v178 ^ 0x4A58, 26));
                        v180 = v178 ^ (19032 * (__ROR4__(v179, 15) - HIWORD(Size)));
                        v181 = v179
                             ^ (19032 * (HIWORD(Size) ^ v180))
                             ^ ((v180 ^ (v180 >> 14)) >> 1)
                             ^ (19032 * ((8 * (v180 - v157)) | ((v180 - v157) >> 29)));
                        v182 = v180 ^ (WORD1(Size) * (v181 - v157) - (v181 >> 13));
                        v183 = v181 ^ __ROR4__(v182, 11) ^ (v157 * __ROR4__(-1313519016 - v182, 9));
                        v184 = v182 ^ (v183 + 1313519016 - HIWORD(Size));
                        v185 = v183 ^ (19032 * ((unsigned int)v1159 ^ v184) - __ROR4__(v184, 7));
                        v186 = v184 ^ (WORD1(Size) * __ROR4__(HIWORD(Size) ^ v185, 28) - __ROR4__(v185, 16));
                        v187 = v185 ^ (__ROR4__(v186, 4) + v157 * __ROR4__(-1313519016 - v186, 10));
                        v188 = v186 ^ __ROR4__(v187, 9) ^ (HIWORD(Size) * __ROR4__(v187 + 1313519016, 4));
                        v189 = v187 ^ (19032 * __ROR4__(v188 ^ HIDWORD(Size), 24) - __ROR4__(v188, 30));
                        v190 = v188 ^ (WORD1(Size) * __ROR4__(HIDWORD(Size) - v189, 11) - __ROR4__(v189, 12));
                        v191 = v190 ^ v158 ^ (unsigned int)v1142;
                        LODWORD(v1142) = v165;
                        v192 = v189 ^ (v190 >> 8) ^ (v157 * (v190 ^ WORD1(Size)));
                        v193 = v192 ^ (unsigned int)v1136;
                        LODWORD(v1136) = v164;
                        v159[3] = v193;
                        v160 = v192 ^ v191;
                        v159[7] = v160;
                        v159[2] = __ROR4__(v193, 8);
                        v159[6] = __ROR4__(v160, 8);
                        v159[1] = __ROR4__(v193, 16);
                        v159[5] = __ROR4__(v160, 16);
                        *v159 = __ROR4__(v193, 24);
                        v159[4] = __ROR4__(v160, 24);
                        v159 += 8;
                        LODWORD(v1146) = v193;
                        v154 = WORD1(Size);
                        v156 = v1146;
                        ++v1135;
                      }
                      while ( v1135 < (unsigned __int64)v155 );
                      v151 = v1128;
                      v92 = v1160;
                      v100 = v1153;
                      v89 = v1151;
                      v95 = (void *)v1157;
                      v147 = (char *)v1134;
                      v150 = Srca;
                    }
                    else
                    {
                      v1157 = (SIZE_T)v95;
                    }
                    *(_QWORD *)&v150[(unsigned int)pcchLength] = v151;
                    v195 = GetProcessHeap();
                    v1135 = (SIZE_T)HeapAlloc(v195, 8u, 0x30u);
                    if ( v1135 )
                    {
                      v1134 = v147;
                      v205 = v1135;
                      v1157 = (SIZE_T)v95;
                      *(_DWORD *)v1135 = v1143;
                      v206 = GetProcessHeap();
                      v207 = HeapAlloc(v206, 8u, (unsigned int)v1143);
                      if ( v207 )
                      {
                        *(_QWORD *)(v205 + 8) = v207;
                        memcpy_0(v207, Srca, (unsigned int)v1143);
                        *(_DWORD *)(v205 + 16) = 160;
                        v208 = GetProcessHeap();
                        v209 = HeapAlloc(v208, 8u, 0xA0u);
                        if ( v209 )
                        {
                          *(_QWORD *)(v205 + 24) = v209;
                          *v209 = xmmword_18002F400;
                          v209[1] = xmmword_18002F410;
                          v209[2] = xmmword_18002F420;
                          v209[3] = xmmword_18002F430;
                          v209[4] = xmmword_18002F440;
                          v209[5] = xmmword_18002F450;
                          v209[6] = xmmword_18002F460;
                          v209[7] = xmmword_18002F470;
                          v209[8] = xmmword_18002F480;
                          v209[9] = xmmword_18002F490;
                          *(_DWORD *)(v205 + 32) = 8;
                          v210 = GetProcessHeap();
                          v211 = HeapAlloc(v210, 8u, 8u);
                          if ( v211 )
                          {
                            *(_QWORD *)(v205 + 40) = v211;
                            *v211 = qword_18002F4A0;
                            v1137 = v205;
                            v196 = 0;
                            v1157 = (SIZE_T)v95;
                            v197 = (void *)v1137;
                            v1137 = 0;
LABEL_226:
                            v1139 = v197;
                            v198 = GetProcessHeap();
                            HeapFree(v198, 0, Srca);
                            v199 = v1137;
                            if ( v1137 )
                            {
                              lpModuleName = *(LPCWSTR *)(v1137 + 8);
                              if ( lpModuleName )
                              {
                                v200 = GetProcessHeap();
                                HeapFree(v200, 0, (LPVOID)lpModuleName);
                                v199 = v1137;
                                *(_QWORD *)(v1137 + 8) = 0;
                              }
                              lpModuleName = *(LPCWSTR *)(v199 + 24);
                              if ( lpModuleName )
                              {
                                v201 = GetProcessHeap();
                                HeapFree(v201, 0, (LPVOID)lpModuleName);
                                v199 = v1137;
                                *(_QWORD *)(v1137 + 24) = 0;
                              }
                              lpModuleName = *(LPCWSTR *)(v199 + 40);
                              if ( lpModuleName )
                              {
                                v202 = GetProcessHeap();
                                HeapFree(v202, 0, (LPVOID)lpModuleName);
                                *(_QWORD *)(v1137 + 40) = 0;
                              }
                              v203 = GetProcessHeap();
                              HeapFree(v203, 0, (LPVOID)v1137);
                              v204 = v1139;
                            }
                            else
                            {
                              v204 = v1139;
                            }
                            v90 = v196 | 0x10000000;
                            Src = v90;
                            if ( v90 < 0 )
                              goto LABEL_436;
                            v217 = *v204 + 4;
                            LODWORD(v1159) = 0;
                            if ( v217 >= 4 )
                            {
                              v218 = v217 + 4;
                              if ( v217 + 4 >= v217 )
                              {
                                v219 = v218 + v204[4];
                                pcchLength = (size_t)(v204 + 4);
                                if ( v219 >= v218 )
                                {
                                  v220 = v219 + 4;
                                  if ( v219 + 4 >= v219 )
                                  {
                                    v221 = v220 + v204[8];
                                    LODWORD(v1146) = v221;
                                    if ( v221 >= v220 )
                                    {
                                      v222 = v221;
                                      v223 = GetProcessHeap();
                                      v224 = HeapAlloc(v223, 8u, v222);
                                      v146 = 0;
                                      v1137 = (SIZE_T)v224;
                                      if ( !v224 )
                                      {
                                        v95 = (void *)v1157;
                                        v90 = -805306345;
LABEL_255:
                                        Src = v90;
LABEL_256:
                                        v225 = v1134;
                                        goto LABEL_439;
                                      }
                                      v226 = (const void **)v1139;
                                      v227 = v224 + 1;
                                      *v224 = *(_DWORD *)v1139;
                                      if ( v224 + 1 < v224 )
                                      {
                                        v1137 = (SIZE_T)v224;
                                      }
                                      else
                                      {
                                        memcpy_0(v224 + 1, v226[1], *(unsigned int *)v226);
                                        v228 = (_DWORD *)((char *)v227 + *(unsigned int *)v226);
                                        if ( v228 >= v227 )
                                        {
                                          v229 = (unsigned int *)pcchLength;
                                          v230 = v228 + 1;
                                          *v228 = *(_DWORD *)pcchLength;
                                          if ( v228 + 1 >= v228 )
                                          {
                                            memcpy_0(v228 + 1, v226[3], *v229);
                                            v231 = (_DWORD *)((char *)v230 + *(unsigned int *)pcchLength);
                                            if ( v231 >= v230 )
                                            {
                                              v232 = v231 + 1;
                                              *v231 = *((_DWORD *)v226 + 8);
                                              if ( v231 + 1 >= v231 )
                                              {
                                                memcpy_0(v231 + 1, v226[5], *((unsigned int *)v226 + 8));
                                                if ( (_DWORD *)((char *)v232 + *((unsigned int *)v226 + 8)) >= v232 )
                                                {
                                                  v225 = v1134;
                                                  v95 = (void *)v1157;
                                                  v1138 = (LPVOID)v1137;
                                                  LODWORD(v1159) = v1146;
                                                  if ( v100 && (unsigned int)v1154 > 1 )
                                                  {
                                                    v234 = v100;
                                                    v235 = 0;
                                                    do
                                                    {
                                                      v236 = v234 + 1;
                                                      if ( v234 + 1 < v234 )
                                                        goto LABEL_442;
                                                      v234 = (unsigned int *)((char *)v236 + *v234);
                                                      pcchLength = (size_t)v234;
                                                      if ( v234 < v236 )
                                                        goto LABEL_442;
                                                      ++v235;
                                                    }
                                                    while ( !v235 );
                                                    if ( v234 + 1 < v234 )
                                                    {
LABEL_442:
                                                      v90 = -1073741675;
                                                      goto LABEL_443;
                                                    }
                                                    if ( (unsigned int)v1154 > 2 )
                                                    {
                                                      v237 = (const WCHAR *)v100;
                                                      LODWORD(Size) = 0;
                                                      do
                                                      {
                                                        v238 = v237 + 2;
                                                        if ( v237 + 2 < v237 )
                                                          goto LABEL_442;
                                                        v237 = (const WCHAR *)((char *)v238 + *(unsigned int *)v237);
                                                        lpModuleName = v237;
                                                        if ( v237 < v238 )
                                                          goto LABEL_442;
                                                        LODWORD(Size) = Size + 1;
                                                        v239 = (void *)v1137;
                                                        v1135 = (SIZE_T)v89;
                                                        v1151 = (LPVOID)v1157;
                                                        v1153 = v100;
                                                        v1142 = v1134;
                                                        v1136 = v1139;
                                                        v1154 = v1137;
                                                      }
                                                      while ( (unsigned int)Size < 2 );
                                                      if ( v237 + 2 >= lpModuleName
                                                        && *(_DWORD *)pcchLength < 0xFFFFFFB0 )
                                                      {
                                                        v240 = *(_DWORD *)pcchLength + 84;
                                                        if ( v240 >= *(_DWORD *)pcchLength + 80 )
                                                        {
                                                          v241 = v240 + *(_DWORD *)lpModuleName;
                                                          LODWORD(v1143) = v241;
                                                          if ( v241 >= v240 )
                                                          {
                                                            if ( v241 > 0x400000 )
                                                            {
                                                              v90 = -2147418113;
                                                              v1138 = (LPVOID)v1154;
                                                              v1139 = v1136;
                                                              goto LABEL_443;
                                                            }
                                                            v242 = v241;
                                                            v243 = GetProcessHeap();
                                                            v244 = HeapAlloc(v243, 8u, v242);
                                                            v245 = v1136;
                                                            v146 = 0;
                                                            v225 = v1142;
                                                            v246 = v244;
                                                            v95 = v1151;
                                                            v1144 = v244;
                                                            v1139 = v1136;
                                                            v1134 = v1142;
                                                            if ( !v244 )
                                                            {
                                                              v90 = -805306345;
                                                              Src = -805306345;
                                                              v1138 = (LPVOID)v1154;
                                                              v1144 = 0;
                                                              goto LABEL_439;
                                                            }
                                                            v247 = v239;
                                                            v1138 = v239;
                                                            phModule = 0;
                                                            v1177 = 0;
                                                            v1178 = 0;
                                                            if ( !v239 )
                                                            {
                                                              v90 = -2147024809;
                                                              Src = -2147024809;
LABEL_297:
                                                              v1144 = v246;
                                                              v1138 = v247;
                                                              v1139 = v245;
                                                              goto LABEL_438;
                                                            }
                                                            LODWORD(v1178) = (_DWORD)v1159;
                                                            *((_QWORD *)&v1177 + 1) = v244;
                                                            *(_QWORD *)((char *)&v1178 + 4) = (unsigned int)v1143;
                                                            *(_QWORD *)&v1177 = v239;
                                                            if ( GetModuleHandleExW(1u, L"ntdll.dll", &phModule)
                                                              && (v249 = GetProcAddress(
                                                                           phModule,
                                                                           "NtQuerySystemInformation")) != 0 )
                                                            {
                                                              v250 = ((__int64 (__fastcall *)(__int64, __int128 *))v249)(
                                                                       134,
                                                                       &v1177);
                                                              v90 = v250 | 0x10000000;
                                                              Src = v250 | 0x10000000;
                                                              if ( v250 >= 0 )
                                                              {
                                                                v251 = DWORD1(v1178);
                                                                v146 = 0;
                                                                goto LABEL_306;
                                                              }
                                                              v146 = 0;
                                                            }
                                                            else
                                                            {
                                                              v248 = GetLastError();
                                                              v146 = 0;
                                                              Src = v248;
                                                              v90 = v248;
                                                              if ( v248 > 0 )
                                                              {
                                                                v90 = (unsigned __int16)v248 | 0x80070000;
                                                                Src = v90;
                                                              }
                                                              if ( v90 >= 0 )
                                                              {
                                                                v90 = -2147467259;
                                                                Src = -2147467259;
                                                                goto LABEL_296;
                                                              }
                                                            }
                                                            v251 = v1143;
                                                            if ( v90 == -805306333 )
                                                            {
                                                              v90 = -2147024774;
LABEL_304:
                                                              v225 = v1142;
                                                              v1138 = (LPVOID)v1154;
                                                              v1139 = v1136;
                                                              Src = v90;
LABEL_438:
                                                              v1134 = v225;
                                                              goto LABEL_439;
                                                            }
                                                            if ( v90 >= 0 )
                                                            {
LABEL_306:
                                                              if ( v251 < 4 )
                                                              {
                                                                v90 = -805306306;
                                                                goto LABEL_304;
                                                              }
                                                              v252 = *(unsigned int *)v1144;
                                                              v253 = (char *)v1144 + 4;
                                                              v1159 = (char *)v1144 + 4;
                                                              if ( (char *)v1144 + 4 < v1144 )
                                                                goto LABEL_441;
                                                              if ( v251 - 4 < (unsigned int)v252 )
                                                              {
                                                                v90 = -805306306;
                                                                goto LABEL_304;
                                                              }
                                                              v254 = &v253[v252];
                                                              Size = (size_t)&v253[v252];
                                                              if ( &v253[v252] < v253 )
                                                              {
LABEL_441:
                                                                v90 = -805306219;
                                                                v225 = v1134;
                                                                Src = -805306219;
                                                                goto LABEL_438;
                                                              }
                                                              if ( (unsigned int)v252 < 0xFFFFFFFC )
                                                              {
                                                                if ( v251 - ((_DWORD)v252 + 4) < 4 )
                                                                {
LABEL_314:
                                                                  v90 = -805306306;
                                                                  v225 = v1142;
                                                                  v1138 = (LPVOID)v1154;
                                                                  v1139 = v1136;
                                                                  Src = -805306306;
LABEL_437:
                                                                  v146 = 0;
                                                                  goto LABEL_438;
                                                                }
                                                                v255 = *(unsigned int *)v254;
                                                                v256 = v254 + 4;
                                                                LODWORD(v1146) = *(_DWORD *)v254;
                                                                if ( v254 + 4 >= v254 )
                                                                {
                                                                  v257 = v252 + 8;
                                                                  if ( (int)v252 + 8 >= (unsigned int)(v252 + 4) )
                                                                  {
                                                                    if ( v251 - v257 < (unsigned int)v255 )
                                                                      goto LABEL_314;
                                                                    v258 = (unsigned __int64)v256 + v255;
                                                                    v1143 = v255;
                                                                    lpModuleName = (LPCWSTR)((char *)v256 + v255);
                                                                    if ( (_DWORD *)((char *)v256 + v255) >= v256 )
                                                                    {
                                                                      v259 = v257 + v255;
                                                                      if ( v257 + (unsigned int)v255 >= v257 )
                                                                      {
                                                                        if ( v251 - v259 < 4 )
                                                                          goto LABEL_314;
                                                                        Srcb = (const void *)(v258 + 4);
                                                                        if ( v258 + 4 >= v258 )
                                                                        {
                                                                          v260 = v259 + 4;
                                                                          if ( v259 + 4 >= v259 )
                                                                          {
                                                                            v261 = *(_DWORD *)lpModuleName;
                                                                            LODWORD(v1157) = v261;
                                                                            if ( v251 - v260 < v261 )
                                                                              goto LABEL_314;
                                                                            if ( v260 + v261 >= v260 )
                                                                            {
                                                                              if ( v251 != v260 + v261
                                                                                || (unsigned int)v252
                                                                                 + (_DWORD)v255
                                                                                 + v261
                                                                                 + 12LL != v251 )
                                                                              {
                                                                                goto LABEL_314;
                                                                              }
                                                                              v262 = GetProcessHeap();
                                                                              v263 = HeapAlloc(v262, 8u, 0x30u);
                                                                              v146 = 0;
                                                                              pcchLength = (size_t)v263;
                                                                              v264 = (size_t)v263;
                                                                              if ( !v263 )
                                                                              {
                                                                                v90 = -805306345;
                                                                                v225 = v1142;
                                                                                v95 = v1151;
                                                                                v1138 = (LPVOID)v1154;
                                                                                v1139 = v1136;
                                                                                Src = -805306345;
                                                                                goto LABEL_438;
                                                                              }
                                                                              v265 = v1159;
                                                                              v1137 = 0;
                                                                              if ( v1159 )
                                                                              {
                                                                                *(_DWORD *)v263 = v252;
                                                                                v266 = GetProcessHeap();
                                                                                v267 = v252;
                                                                                v268 = HeapAlloc(v266, 8u, v252);
                                                                                if ( !v268 )
                                                                                {
LABEL_340:
                                                                                  v269 = -1073741801;
                                                                                  v95 = v1151;
                                                                                  v100 = v1153;
                                                                                  v89 = (void *)v1135;
                                                                                  v1138 = (LPVOID)v1154;
                                                                                  v1139 = v1136;
                                                                                  v1134 = v1142;
                                                                                  v278 = pcchLength;
                                                                                  v1157 = (SIZE_T)v1151;
                                                                                  v1151 = (LPVOID)v1135;
                                                                                  lpModuleName = *(LPCWSTR *)(pcchLength + 8);
                                                                                  if ( lpModuleName )
                                                                                  {
                                                                                    v279 = GetProcessHeap();
                                                                                    HeapFree(
                                                                                      v279,
                                                                                      0,
                                                                                      (LPVOID)lpModuleName);
                                                                                    v278 = pcchLength;
                                                                                    *(_QWORD *)(pcchLength + 8) = 0;
                                                                                  }
                                                                                  lpModuleName = *(LPCWSTR *)(v278 + 24);
                                                                                  if ( lpModuleName )
                                                                                  {
                                                                                    v280 = GetProcessHeap();
                                                                                    HeapFree(
                                                                                      v280,
                                                                                      0,
                                                                                      (LPVOID)lpModuleName);
                                                                                    v278 = pcchLength;
                                                                                    *(_QWORD *)(pcchLength + 24) = 0;
                                                                                  }
                                                                                  lpModuleName = *(LPCWSTR *)(v278 + 40);
                                                                                  if ( lpModuleName )
                                                                                  {
                                                                                    v281 = GetProcessHeap();
                                                                                    HeapFree(
                                                                                      v281,
                                                                                      0,
                                                                                      (LPVOID)lpModuleName);
                                                                                    *(_QWORD *)(pcchLength + 40) = 0;
                                                                                  }
                                                                                  v282 = GetProcessHeap();
                                                                                  HeapFree(v282, 0, (LPVOID)pcchLength);
                                                                                  v283 = (LPCWSTR *)v1137;
                                                                                  v146 = 0;
LABEL_350:
                                                                                  if ( v269 < 0 )
                                                                                  {
                                                                                    if ( v283 )
                                                                                    {
                                                                                      lpModuleName = v283[1];
                                                                                      if ( lpModuleName )
                                                                                      {
                                                                                        v284 = GetProcessHeap();
                                                                                        HeapFree(
                                                                                          v284,
                                                                                          0,
                                                                                          (LPVOID)lpModuleName);
                                                                                        v283 = (LPCWSTR *)v1137;
                                                                                        *(_QWORD *)(v1137 + 8) = 0;
                                                                                      }
                                                                                      lpModuleName = v283[3];
                                                                                      if ( lpModuleName )
                                                                                      {
                                                                                        v285 = GetProcessHeap();
                                                                                        HeapFree(
                                                                                          v285,
                                                                                          0,
                                                                                          (LPVOID)lpModuleName);
                                                                                        v283 = (LPCWSTR *)v1137;
                                                                                        *(_QWORD *)(v1137 + 24) = 0;
                                                                                      }
                                                                                      lpModuleName = v283[5];
                                                                                      if ( lpModuleName )
                                                                                      {
                                                                                        v286 = GetProcessHeap();
                                                                                        HeapFree(
                                                                                          v286,
                                                                                          0,
                                                                                          (LPVOID)lpModuleName);
                                                                                        *(_QWORD *)(v1137 + 40) = 0;
                                                                                      }
                                                                                      v287 = GetProcessHeap();
                                                                                      HeapFree(v287, 0, (LPVOID)v1137);
                                                                                      v146 = 0;
                                                                                    }
                                                                                  }
                                                                                  else
                                                                                  {
                                                                                    v1152 = v283;
                                                                                  }
                                                                                  v90 = v269 | 0x10000000;
                                                                                  Src = v90;
                                                                                  if ( v90 < 0 )
                                                                                    goto LABEL_256;
                                                                                  v288 = v1152;
                                                                                  if ( !v1152
                                                                                    || (v1142 = (LPVOID)*((_QWORD *)v1152 + 1)) == 0
                                                                                    || !*(_DWORD *)v1152 )
                                                                                  {
                                                                                    v90 = -805306355;
                                                                                    goto LABEL_255;
                                                                                  }
                                                                                  v1137 = *(unsigned int *)v1152 - 8LL;
                                                                                  v289 = MemoryAlloc(v1137);
                                                                                  v146 = 0;
                                                                                  Size = (size_t)v289;
                                                                                  v290 = v289;
                                                                                  if ( !v289 )
                                                                                  {
LABEL_392:
                                                                                    v1150 = 0;
                                                                                    v90 = -805306367;
                                                                                    goto LABEL_255;
                                                                                  }
                                                                                  v291 = 0;
                                                                                  v1135 = 0x7F1137FAB69605ELL;
                                                                                  pcchLength = (size_t)v1142;
                                                                                  v1136 = v290;
                                                                                  v292 = v1137 & 7;
                                                                                  if ( (v1137 & 7) != 0 )
                                                                                  {
                                                                                    LODWORD(v1150) = 0;
                                                                                    v293 = 0;
                                                                                    v294 = 0;
                                                                                    v295 = 0;
                                                                                    v296 = (unsigned __int8 *)pcchLength;
                                                                                    do
                                                                                    {
                                                                                      v297 = *v296++;
                                                                                      LODWORD(v1143) = v297;
                                                                                      LODWORD(v1159) = 8 * v293;
                                                                                      if ( v293 >= 4 )
                                                                                      {
                                                                                        LODWORD(v1143) = (_DWORD)v1143 << (56 - (_BYTE)v1159);
                                                                                        v294 |= v1143;
                                                                                      }
                                                                                      else
                                                                                      {
                                                                                        LODWORD(v1143) = (_DWORD)v1143 << (24 - (_BYTE)v1159);
                                                                                        v295 |= v1143;
                                                                                      }
                                                                                      ++v293;
                                                                                    }
                                                                                    while ( (int)v293 < (int)v292 );
                                                                                    Srcc = v295;
                                                                                    v291 = 0;
                                                                                    LODWORD(v1150) = v294;
                                                                                    v92 = v1160;
                                                                                    pcchLength = (size_t)v296;
                                                                                    v1152 = v288;
                                                                                    v1153 = v100;
                                                                                    v1157 = (SIZE_T)v95;
                                                                                    v1151 = v89;
                                                                                    v298 = Srcc ^ 0x92F65A5;
                                                                                    v299 = (unsigned int)v1150
                                                                                         ^ 0x699A899C;
                                                                                    v300 = 0;
                                                                                    v301 = Srcc ^ 0x92F65A5;
                                                                                    v302 = (unsigned int)v1150
                                                                                         ^ 0x699A899C;
                                                                                    if ( (v1137 & 7) != 0 )
                                                                                    {
                                                                                      v303 = (WCHAR *)v290;
                                                                                      do
                                                                                      {
                                                                                        lpModuleName = (WCHAR *)((char *)v303 + 1);
                                                                                        if ( v300 >= 4 )
                                                                                        {
                                                                                          v302 = __ROR4__(v302, 24);
                                                                                          v304 = v302;
                                                                                        }
                                                                                        else
                                                                                        {
                                                                                          v301 = __ROR4__(v301, 24);
                                                                                          v304 = v301;
                                                                                        }
                                                                                        *(_BYTE *)v303 = v304;
                                                                                        ++v300;
                                                                                        v303 = (WCHAR *)lpModuleName;
                                                                                      }
                                                                                      while ( (int)v300 < (int)v292 );
                                                                                      v92 = v1160;
                                                                                      v1136 = (LPVOID)lpModuleName;
                                                                                    }
                                                                                    if ( v292 <= 4 )
                                                                                    {
                                                                                      v305 = 0;
                                                                                      if ( v292 < 4 )
                                                                                        v298 = v298 >> (8 * (4 - v292)) << (8 * (4 - v292));
                                                                                    }
                                                                                    else
                                                                                    {
                                                                                      v305 = v299 >> (8 * (8 - v292)) << (8 * (8 - v292));
                                                                                    }
                                                                                  }
                                                                                  else
                                                                                  {
                                                                                    LODWORD(v1150) = -1;
                                                                                    Srcc = 0;
                                                                                    v305 = 0;
                                                                                    v298 = 0;
                                                                                  }
                                                                                  v306 = v1137;
                                                                                  if ( v1137 >> 3 )
                                                                                  {
                                                                                    v307 = HIDWORD(v1135);
                                                                                    v308 = v1137 >> 3;
                                                                                    v309 = (unsigned __int8 *)pcchLength;
                                                                                    v310 = v1136;
                                                                                    v311 = Srcc;
                                                                                    v312 = WORD2(v1135);
                                                                                    LODWORD(v1143) = 24670;
                                                                                    v313 = (int)v1150;
                                                                                    LODWORD(v1154) = WORD2(v1135);
                                                                                    v1146 = 0;
                                                                                    do
                                                                                    {
                                                                                      v314 = v309[1];
                                                                                      v315 = *v309;
                                                                                      v316 = v309[4];
                                                                                      v309 += 8;
                                                                                      v317 = *(v309 - 5)
                                                                                           | ((*(v309 - 6)
                                                                                             | ((v314 | (v315 << 8)) << 8)) << 8);
                                                                                      v318 = v298 ^ v317;
                                                                                      v319 = *(v309 - 1)
                                                                                           | ((*(v309 - 2)
                                                                                             | ((*(v309 - 3)
                                                                                               | (v316 << 8)) << 8)) << 8);
                                                                                      v320 = v305
                                                                                           ^ v319
                                                                                           ^ v307
                                                                                           ^ v298
                                                                                           ^ v317
                                                                                           ^ 0xAB69605E;
                                                                                      v321 = v318
                                                                                           ^ (__ROR4__(v320, 22)
                                                                                            + v312
                                                                                            * __ROR4__(
                                                                                                v320 + 1419157410,
                                                                                                27));
                                                                                      v322 = v320
                                                                                           ^ (WORD1(v1135)
                                                                                            * __ROR4__(v321 + v307, 9)
                                                                                            - __ROR4__(v321, 30));
                                                                                      v323 = v321
                                                                                           ^ (v1143 * (v322 - v312)
                                                                                            - (v322 >> 13));
                                                                                      v324 = v322
                                                                                           ^ (HIWORD(v1135)
                                                                                            * __ROR4__(
                                                                                                v323 ^ WORD1(v1135),
                                                                                                26)
                                                                                            - __ROR4__(v323, 30));
                                                                                      v325 = v323
                                                                                           ^ (v307 - (v324 ^ 0xAB69605E));
                                                                                      v326 = v324
                                                                                           ^ (WORD1(v1135)
                                                                                            * (v312 ^ v325))
                                                                                           ^ __ROR4__(v325, 6);
                                                                                      v327 = v325
                                                                                           ^ (__ROR4__(v326, 30)
                                                                                            + v1143
                                                                                            * __ROR4__(v326 + v307, 15));
                                                                                      v328 = v326
                                                                                           ^ (HIWORD(v1135)
                                                                                            * __ROR4__(
                                                                                                v327 + 1419157410,
                                                                                                14)
                                                                                            - __ROR4__(v327, 24));
                                                                                      v329 = v327
                                                                                           ^ __ROR4__(v328, 10)
                                                                                           ^ (v1154
                                                                                            * __ROR4__(
                                                                                                v328 ^ 0xAB69605E,
                                                                                                12));
                                                                                      v330 = v329
                                                                                           ^ (HIWORD(v1135)
                                                                                            * (v1143
                                                                                             + __ROR4__(
                                                                                                 ~(v328
                                                                                                 ^ (v329 >> 10)
                                                                                                 ^ (WORD1(v1135)
                                                                                                  * (v329 ^ HIWORD(v1135)))),
                                                                                                 5)));
                                                                                      v331 = v328
                                                                                           ^ (v329 >> 10)
                                                                                           ^ (WORD1(v1135)
                                                                                            * (v329 ^ HIWORD(v1135)))
                                                                                           ^ (v330 - HIWORD(v1135))
                                                                                           ^ 0xAB69605E;
                                                                                      v332 = v330
                                                                                           ^ ((v331 >> 2)
                                                                                            + v1154
                                                                                            * __ROR4__(
                                                                                                HIWORD(v1135) ^ v331,
                                                                                                30));
                                                                                      v333 = v331
                                                                                           ^ (__ROR4__(v332, 25)
                                                                                            + WORD1(v1135)
                                                                                            * __ROR4__(
                                                                                                v332 - HIDWORD(v1135),
                                                                                                6));
                                                                                      v334 = v332
                                                                                           ^ (v1143 * (v1154 ^ v333)
                                                                                            + __ROR4__(v333, 9));
                                                                                      v335 = v333
                                                                                           ^ (__ROR4__(v334, 25)
                                                                                            + HIWORD(v1135)
                                                                                            * __ROR4__(
                                                                                                v334 ^ WORD1(v1135),
                                                                                                27));
                                                                                      v307 = HIDWORD(v1135);
                                                                                      v336 = HIDWORD(v1135)
                                                                                           ^ v334
                                                                                           ^ v335
                                                                                           ^ 0xAB69605E;
                                                                                      v337 = v335
                                                                                           ^ (v1154
                                                                                            * (__ROR4__(v336, 3)
                                                                                             - WORD1(v1135)));
                                                                                      v338 = v336
                                                                                           ^ (v1143
                                                                                            * __ROR4__(
                                                                                                v337 - HIDWORD(v1135),
                                                                                                1)
                                                                                            - __ROR4__(v337, 6));
                                                                                      v339 = v337
                                                                                           ^ (__ROR4__(v338, 18)
                                                                                            + HIWORD(v1135)
                                                                                            * __ROR4__(
                                                                                                v338 - 1419157410,
                                                                                                29));
                                                                                      v340 = v338
                                                                                           ^ (v1154
                                                                                            * __ROR4__(
                                                                                                v339 - 1419157410,
                                                                                                17)
                                                                                            - __ROR4__(v339, 14));
                                                                                      v312 = v1154;
                                                                                      v341 = v339
                                                                                           ^ (v340 >> 3)
                                                                                           ^ (WORD1(v1135)
                                                                                            * (v1143 ^ v340));
                                                                                      v342 = v311
                                                                                           ^ __ROR4__(v341, 30)
                                                                                           ^ (v1143
                                                                                            * __ROR4__(
                                                                                                HIDWORD(v1135) ^ v341,
                                                                                                28));
                                                                                      v311 = v317;
                                                                                      v298 = v340 ^ v342;
                                                                                      v310[3] = v298;
                                                                                      v305 = v341 ^ v313;
                                                                                      v310[7] = v341 ^ v313;
                                                                                      v313 = v319;
                                                                                      v310[2] = __ROR4__(v298, 8);
                                                                                      v310[6] = __ROR4__(v305, 8);
                                                                                      v310[1] = __ROR4__(v298, 16);
                                                                                      v310[5] = __ROR4__(v305, 16);
                                                                                      *v310 = __ROR4__(v298, 24);
                                                                                      v310[4] = __ROR4__(v305, 24);
                                                                                      v310 += 8;
                                                                                      ++v1146;
                                                                                    }
                                                                                    while ( v1146 < v308 );
                                                                                    v291 = 0;
                                                                                    v92 = v1160;
                                                                                    v100 = v1153;
                                                                                    v89 = v1151;
                                                                                    v95 = (void *)v1157;
                                                                                    v290 = (_DWORD *)Size;
                                                                                    v306 = v1137;
                                                                                  }
                                                                                  for ( j = 0; j < v306; ++j )
                                                                                    v291 ^= *((_BYTE *)v290 + j);
                                                                                  if ( v291 != *(_QWORD *)((char *)v1142 + v306) )
                                                                                  {
                                                                                    MemoryFree(v290);
                                                                                    v146 = 0;
                                                                                    goto LABEL_392;
                                                                                  }
                                                                                  v225 = v1134;
                                                                                  if ( (unsigned int)v306 < 4 )
                                                                                  {
                                                                                    v344 = -1073741762;
LABEL_395:
                                                                                    v1150 = v290;
LABEL_396:
                                                                                    v146 = 0;
LABEL_426:
                                                                                    v90 = v344 | 0x10000000;
                                                                                    Src = v90;
                                                                                    goto LABEL_439;
                                                                                  }
                                                                                  v1135 = (SIZE_T)(v290 + 1);
                                                                                  v1150 = v290;
                                                                                  if ( v290 + 1 < v290 )
                                                                                  {
                                                                                    v344 = -1073741675;
                                                                                    v1150 = v290;
                                                                                    goto LABEL_396;
                                                                                  }
                                                                                  if ( (unsigned int)(v306 - 4) < 4 )
                                                                                    goto LABEL_399;
                                                                                  if ( v1135 + 4 >= (unsigned __int64)(v290 + 1) )
                                                                                  {
                                                                                    if ( (unsigned int)(v306 - 8) < v290[1] )
                                                                                      goto LABEL_399;
                                                                                    if ( v290[1] < 0xFFFFFFF8 )
                                                                                    {
                                                                                      v1137 = (unsigned int)v290[1];
                                                                                      pcchLength = (size_t)v290
                                                                                                 + v1137
                                                                                                 + 8;
                                                                                      if ( (unsigned __int64)v290
                                                                                         + (unsigned int)v306 >= pcchLength )
                                                                                      {
                                                                                        v345 = (size_t)(v290 + 2);
                                                                                        if ( (unsigned int)v306
                                                                                           - v1137
                                                                                           - 8 < 8 )
                                                                                        {
                                                                                          LODWORD(Size) = 0;
                                                                                          if ( v290 == (_DWORD *)-8LL )
                                                                                          {
                                                                                            v1150 = (LPVOID)-8LL;
                                                                                          }
                                                                                          else
                                                                                          {
                                                                                            if ( pcchLength < v345 )
                                                                                            {
                                                                                              v344 = -1073741675;
                                                                                              goto LABEL_395;
                                                                                            }
                                                                                            v346 = v290 + 2;
                                                                                            if ( pcchLength > v345 )
                                                                                            {
                                                                                              while ( v346 + 1 >= v346 )
                                                                                              {
                                                                                                if ( (unsigned __int64)(v346 + 1) > pcchLength )
                                                                                                  goto LABEL_419;
                                                                                                v347 = *v346 + 4;
                                                                                                if ( *v346 >= 0xFFFFFFFC )
                                                                                                  break;
                                                                                                v348 = (size_t)v346 + v347;
                                                                                                if ( v348 < (unsigned __int64)v346 )
                                                                                                  break;
                                                                                                if ( v348 > pcchLength )
                                                                                                  goto LABEL_419;
                                                                                                LODWORD(Size) = Size + 1;
                                                                                                v346 = (_DWORD *)((char *)v346 + v347);
                                                                                                if ( v348 >= pcchLength )
                                                                                                  goto LABEL_418;
                                                                                              }
                                                                                              v344 = -1073741675;
                                                                                              goto LABEL_396;
                                                                                            }
                                                                                            v1150 = v290;
LABEL_418:
                                                                                            if ( v346 != (_DWORD *)pcchLength )
                                                                                            {
LABEL_419:
                                                                                              v344 = -1073741811;
                                                                                              goto LABEL_396;
                                                                                            }
                                                                                          }
                                                                                          v146 = 0;
                                                                                          LODWORD(v1146) = *v290;
                                                                                          if ( v290[1] )
                                                                                          {
                                                                                            v349 = GetProcessHeap();
                                                                                            v350 = HeapAlloc(
                                                                                                     v349,
                                                                                                     8u,
                                                                                                     v1137);
                                                                                            v146 = 0;
                                                                                            if ( !v350 )
                                                                                            {
                                                                                              v344 = -1073741801;
LABEL_425:
                                                                                              v225 = v1134;
                                                                                              goto LABEL_426;
                                                                                            }
                                                                                          }
                                                                                          else
                                                                                          {
                                                                                            v350 = 0;
                                                                                          }
                                                                                          v344 = 0;
                                                                                          lpMem = v350;
                                                                                          if ( v1135 != -4 )
                                                                                          {
                                                                                            memcpy_0(
                                                                                              v350,
                                                                                              (const void *)(v1135 + 4),
                                                                                              v1137);
                                                                                            v146 = 0;
                                                                                          }
                                                                                          LODWORD(v1149) = Size;
                                                                                          if ( (_DWORD)v1146 != (_DWORD)Size )
                                                                                            v344 = -1073741762;
                                                                                          goto LABEL_425;
                                                                                        }
                                                                                      }
LABEL_399:
                                                                                      v344 = -1073741762;
LABEL_400:
                                                                                      v1150 = v290;
                                                                                      goto LABEL_396;
                                                                                    }
                                                                                  }
                                                                                  v344 = -1073741675;
                                                                                  goto LABEL_400;
                                                                                }
                                                                                *(_QWORD *)(v264 + 8) = v268;
                                                                                v269 = 0;
                                                                                memcpy_0(v268, v265, v267);
                                                                                v146 = 0;
                                                                              }
                                                                              else
                                                                              {
                                                                                *(_DWORD *)v263 = 0;
                                                                                v269 = 0;
                                                                                v263[1] = 0;
                                                                              }
                                                                              v270 = (const void *)(Size + 4);
                                                                              if ( Size == -4 )
                                                                              {
                                                                                *(_DWORD *)(v264 + 16) = 0;
                                                                                *(_QWORD *)(v264 + 24) = 0;
                                                                              }
                                                                              else
                                                                              {
                                                                                *(_DWORD *)(v264 + 16) = v1146;
                                                                                v271 = GetProcessHeap();
                                                                                v272 = v1143;
                                                                                v273 = HeapAlloc(v271, 8u, v1143);
                                                                                if ( !v273 )
                                                                                {
LABEL_339:
                                                                                  pcchLength = v264;
                                                                                  goto LABEL_340;
                                                                                }
                                                                                *(_QWORD *)(v264 + 24) = v273;
                                                                                v269 = 0;
                                                                                memcpy_0(v273, v270, v272);
                                                                                v146 = 0;
                                                                              }
                                                                              if ( Srcb )
                                                                              {
                                                                                v274 = v1157;
                                                                                *(_DWORD *)(v264 + 32) = v1157;
                                                                                v275 = v274;
                                                                                v276 = GetProcessHeap();
                                                                                v277 = HeapAlloc(
                                                                                         v276,
                                                                                         8u,
                                                                                         (unsigned int)v275);
                                                                                if ( !v277 )
                                                                                  goto LABEL_339;
                                                                                *(_QWORD *)(v264 + 40) = v277;
                                                                                v269 = 0;
                                                                                memcpy_0(v277, Srcb, v275);
                                                                                v146 = 0;
                                                                              }
                                                                              else
                                                                              {
                                                                                *(_DWORD *)(v264 + 32) = 0;
                                                                                *(_QWORD *)(v264 + 40) = 0;
                                                                              }
                                                                              v283 = (LPCWSTR *)v264;
                                                                              v100 = v1153;
                                                                              v89 = (void *)v1135;
                                                                              v1138 = (LPVOID)v1154;
                                                                              v1139 = v1136;
                                                                              v1137 = v264;
                                                                              v95 = v1151;
                                                                              v1134 = v1142;
                                                                              v1157 = (SIZE_T)v1151;
                                                                              v1151 = (LPVOID)v1135;
                                                                              goto LABEL_350;
                                                                            }
                                                                            v225 = v1134;
                                                                            v90 = -805306219;
                                                                            goto LABEL_443;
                                                                          }
                                                                        }
                                                                      }
                                                                    }
                                                                  }
                                                                }
                                                              }
                                                              v90 = -805306219;
                                                              Src = -805306219;
LABEL_436:
                                                              v225 = v1134;
                                                              goto LABEL_437;
                                                            }
LABEL_296:
                                                            v225 = v1134;
                                                            v245 = v1139;
                                                            v246 = v1144;
                                                            v247 = v1138;
                                                            goto LABEL_297;
                                                          }
                                                        }
                                                      }
                                                      goto LABEL_442;
                                                    }
                                                  }
                                                  v90 = -1073741811;
LABEL_443:
                                                  Src = v90;
                                                  goto LABEL_444;
                                                }
                                              }
                                            }
                                          }
                                        }
                                      }
                                      v1139 = v226;
                                      v95 = (void *)v1157;
                                      v233 = GetProcessHeap();
                                      HeapFree(v233, 0, (LPVOID)v1137);
                                    }
                                  }
                                }
                              }
                            }
                            v225 = v1134;
                            v90 = -805306219;
                            Src = -805306219;
LABEL_444:
                            v146 = 0;
LABEL_439:
                            if ( !v225 )
                            {
LABEL_447:
                              v352 = v1139;
                              if ( v1139 )
                              {
                                lpModuleName = (LPCWSTR)*((_QWORD *)v1139 + 1);
                                if ( lpModuleName )
                                {
                                  v353 = GetProcessHeap();
                                  HeapFree(v353, 0, (LPVOID)lpModuleName);
                                  v352 = v1139;
                                  *((_QWORD *)v1139 + 1) = 0;
                                }
                                lpModuleName = (LPCWSTR)*((_QWORD *)v352 + 3);
                                if ( lpModuleName )
                                {
                                  v354 = GetProcessHeap();
                                  HeapFree(v354, 0, (LPVOID)lpModuleName);
                                  v352 = v1139;
                                  *((_QWORD *)v1139 + 3) = 0;
                                }
                                lpModuleName = (LPCWSTR)*((_QWORD *)v352 + 5);
                                if ( lpModuleName )
                                {
                                  v355 = GetProcessHeap();
                                  HeapFree(v355, 0, (LPVOID)lpModuleName);
                                  *((_QWORD *)v1139 + 5) = 0;
                                }
                                v356 = GetProcessHeap();
                                HeapFree(v356, 0, v1139);
                                v146 = 0;
                              }
                              if ( v1138 )
                              {
                                v357 = GetProcessHeap();
                                HeapFree(v357, 0, v1138);
                                v146 = 0;
                              }
                              if ( v1144 )
                              {
                                v358 = GetProcessHeap();
                                HeapFree(v358, 0, v1144);
                                v146 = 0;
                              }
                              v359 = v1152;
                              if ( v1152 )
                              {
                                lpModuleName = (LPCWSTR)*((_QWORD *)v1152 + 1);
                                if ( lpModuleName )
                                {
                                  v360 = GetProcessHeap();
                                  HeapFree(v360, 0, (LPVOID)lpModuleName);
                                  v359 = v1152;
                                  *((_QWORD *)v1152 + 1) = 0;
                                }
                                lpModuleName = (LPCWSTR)*((_QWORD *)v359 + 3);
                                if ( lpModuleName )
                                {
                                  v361 = GetProcessHeap();
                                  HeapFree(v361, 0, (LPVOID)lpModuleName);
                                  v359 = v1152;
                                  *((_QWORD *)v1152 + 3) = 0;
                                }
                                lpModuleName = (LPCWSTR)*((_QWORD *)v359 + 5);
                                if ( lpModuleName )
                                {
                                  v362 = GetProcessHeap();
                                  HeapFree(v362, 0, (LPVOID)lpModuleName);
                                  *((_QWORD *)v1152 + 5) = 0;
                                }
                                v363 = GetProcessHeap();
                                HeapFree(v363, 0, v1152);
                                v146 = 0;
                              }
                              if ( !v1150 )
                              {
LABEL_470:
                                if ( v90 < 0 )
                                  goto LABEL_151;
                                if ( !(_DWORD)v1149 )
                                {
LABEL_472:
                                  v90 = -1073425151;
LABEL_150:
                                  Src = v90;
                                  goto LABEL_151;
                                }
                                if ( !lpMem )
                                {
                                  v90 = -1073741811;
                                  goto LABEL_150;
                                }
                                if ( (char *)lpMem + 4 >= lpMem )
                                {
                                  v365 = 0;
                                  if ( *(_DWORD *)lpMem )
                                    v365 = (int *)((char *)lpMem + 4);
                                  if ( *(_DWORD *)lpMem != 4 )
                                  {
LABEL_500:
                                    v90 = -1073741789;
                                    goto LABEL_150;
                                  }
                                  v90 = *v365;
                                  Src = v90;
                                  if ( v90 == -805306333 )
                                  {
                                    v366 = -2147024774;
                                    LODWORD(v1143) = -2147024774;
                                  }
                                  else
                                  {
                                    LODWORD(v1143) = v90;
                                    v366 = v90;
                                    if ( v90 != -2147024774 && v90 < 0 )
                                    {
LABEL_151:
                                      if ( v100 )
                                      {
                                        v119 = GetProcessHeap();
                                        HeapFree(v119, 0, v100);
                                      }
                                      v120 = lpMem;
                                      if ( lpMem )
                                      {
                                        v121 = GetProcessHeap();
                                        HeapFree(v121, 0, v120);
                                      }
                                      if ( !v89 )
                                      {
LABEL_542:
                                        if ( v95 )
                                        {
                                          v390 = GetProcessHeap();
                                          HeapFree(v390, 0, v95);
                                        }
                                        if ( v90 < 0 )
                                        {
                                          v91 = v1148;
LABEL_1477:
                                          while ( _InterlockedCompareExchange(&dword_18002F8EC, 1, 0) )
                                            ;
                                          v1118 = dword_18002F8E8;
                                          if ( dword_18002F8E8 > 0 )
                                          {
                                            --dword_18002F8E8;
                                            if ( v1118 == 1 )
                                            {
                                              for ( k = 0; k != 4; ++k )
                                              {
                                                v1120 = (HMODULE)qword_18002F860[3 * k];
                                                if ( v1120 )
                                                  FreeLibrary(v1120);
                                              }
                                              memset_0(qword_18002F860, 0, sizeof(qword_18002F860));
                                              memcpy_0(off_18002F000, off_180028410, 0x170u);
                                            }
                                          }
                                          _InterlockedExchange(&dword_18002F8EC, 0);
                                          SP_HLOCAL<unsigned char>::~SP_HLOCAL<unsigned char>(&v1155);
                                          if ( v90 >= 0 )
                                          {
                                            if ( v91 == 4 )
                                            {
                                              v2 = 0;
                                              *v1186 = *v1173;
                                              goto LABEL_1497;
                                            }
                                          }
                                          else
                                          {
                                            switch ( v90 )
                                            {
                                              case -805306316:
                                                v2 = -1073418222;
                                                goto LABEL_1497;
                                              case -805306139:
                                              case -1073425151:
                                                v2 = -1073418201;
                                                goto LABEL_1497;
                                              case -805306306:
                                                v2 = -1073418200;
                                                goto LABEL_1497;
                                            }
                                            v2 = v90;
                                            if ( v90 != -2147024774 )
                                              goto LABEL_1497;
                                          }
                                          v2 = -1073418210;
                                          goto LABEL_1497;
                                        }
                                        if ( !v1122 )
                                          goto LABEL_1474;
                                        v1156 = 0;
                                        dword_18002F850 = v1122;
                                        ModuleFileNameW = GetModuleFileNameW((HMODULE)0x180000000LL, Filename, 0x104u);
                                        v392 = 0;
                                        if ( !ModuleFileNameW || ModuleFileNameW == 260 && GetLastError() == 122 )
                                        {
LABEL_1159:
                                          SH_HANDLE::~SH_HANDLE((SH_HANDLE *)&v1156);
                                          v853 = GetProcessHeap();
                                          v854 = HeapAlloc(v853, 8u, 0xA0u);
                                          v855 = v854;
                                          if ( v854 )
                                          {
                                            *v854 = xmmword_18002F4B0;
                                            v854[1] = xmmword_18002F4C0;
                                            v854[2] = xmmword_18002F4D0;
                                            v854[3] = xmmword_18002F4E0;
                                            v854[4] = xmmword_18002F4F0;
                                            v854[5] = xmmword_18002F500;
                                            v854[6] = xmmword_18002F510;
                                            v854[7] = xmmword_18002F520;
                                            v854[8] = xmmword_18002F530;
                                            v854[9] = xmmword_18002F540;
                                            v856 = GetProcessHeap();
                                            v857 = HeapAlloc(v856, 8u, 8u);
                                            if ( !v857 )
                                            {
                                              v857 = 0;
LABEL_1471:
                                              v1116 = GetProcessHeap();
                                              HeapFree(v1116, 0, v855);
LABEL_1472:
                                              if ( v857 )
                                              {
                                                v1117 = GetProcessHeap();
                                                HeapFree(v1117, 0, v857);
                                              }
                                              goto LABEL_1474;
                                            }
                                            *v857 = qword_18002F3F8;
                                            v1156 = (LPVOID)__rdtsc();
                                            v858 = GetProcessHeap();
                                            v859 = (unsigned int *)HeapAlloc(v858, 8u, 0xC4u);
                                            v860 = 0;
                                            v861 = v859;
                                            if ( !v859 )
                                              goto LABEL_1471;
                                            pcchLength = 0;
                                            if ( v859 + 1 >= v859 && v859 + 2 <= v859 + 49 )
                                            {
                                              *v859 = 4;
                                              v862 = 0;
                                              v859[1] = 4;
                                              v863 = v859;
                                              do
                                              {
                                                if ( *v863 >= 0xFFFFFFFC )
                                                  goto LABEL_1466;
                                                v864 = *v863 + 4;
                                                v865 = (unsigned int *)((char *)v863 + v864);
                                                if ( v865 < v863 )
                                                  goto LABEL_1467;
                                                v863 = (unsigned int *)((char *)v863 + v864);
                                                ++v862;
                                              }
                                              while ( !v862 );
                                              if ( v865 + 1 >= v865 && v865 + 41 <= v861 + 49 )
                                              {
                                                *v865 = 160;
                                                if ( v855 )
                                                {
                                                  memcpy_0(v865 + 1, v855, 0xA0u);
                                                  v860 = 0;
                                                }
                                                if ( !v861 )
                                                {
                                                  v866 = 3;
                                                  v871 = 220;
                                                  LODWORD(v1148) = 220;
LABEL_1188:
                                                  LODWORD(v1154) = v866 + 1;
                                                  v1156 = (LPVOID)__rdtsc();
                                                  v876 = v871 + 8;
                                                  if ( v876 < 8 )
                                                    goto LABEL_1466;
                                                  v1152 = (LPVOID)((v876 + 7) & 0xFFFFFFF8);
                                                  if ( (unsigned int)v1152 < v876 )
                                                    goto LABEL_1466;
                                                  LODWORD(v1159) = 0;
                                                  v1161 = (v876 + 7) & 0xFFFFFFF8;
                                                  v877 = GetProcessHeap();
                                                  v878 = HeapAlloc(v877, 8u, v1161);
                                                  v1138 = v878;
                                                  if ( !v878 )
                                                  {
                                                    v879 = -805306345;
LABEL_1453:
                                                    if ( v879 >= 0 )
                                                    {
                                                      if ( (_DWORD)v1159 )
                                                      {
                                                        v1109 = (unsigned int *)pcchLength;
                                                        if ( pcchLength )
                                                        {
                                                          if ( pcchLength + 4 >= pcchLength )
                                                          {
                                                            v1110 = 0;
                                                            if ( *(_DWORD *)pcchLength )
                                                              v1110 = (int *)(pcchLength + 4);
                                                            if ( *(_DWORD *)pcchLength == 4
                                                              && *v1110 >= 0
                                                              && (unsigned int)v1159 > 1 )
                                                            {
                                                              v1111 = 0;
                                                              do
                                                              {
                                                                v1112 = v1109 + 1;
                                                                if ( v1109 + 1 < v1109 )
                                                                  break;
                                                                v1109 = (unsigned int *)((char *)v1112 + *v1109);
                                                                if ( v1109 < v1112 )
                                                                  break;
                                                                ++v1111;
                                                              }
                                                              while ( !v1111 );
                                                            }
                                                          }
                                                        }
                                                      }
                                                    }
                                                    goto LABEL_1466;
                                                  }
                                                  *v878 = v1154;
                                                  if ( v878 + 1 < v878
                                                    || (v880 = v1148, v878[1] = v1148, v878 + 2 < v878 + 1) )
                                                  {
                                                    v1161 = (SIZE_T)v878;
                                                    v923 = GetProcessHeap();
                                                    HeapFree(v923, 0, (LPVOID)v1161);
                                                    v879 = -805306219;
                                                    goto LABEL_1453;
                                                  }
                                                  *(_QWORD *)((char *)v878 + v1161 - 8) = v1156;
                                                  memcpy_0(v878 + 2, v861, v880);
                                                  v1161 = (SIZE_T)v1138;
                                                  v1151 = 0;
                                                  v1136 = 0;
                                                  v1142 = 0;
                                                  v1149 = 0;
                                                  v1144 = 0;
                                                  v1137 = 0;
                                                  if ( !(_DWORD)v1152
                                                    || (v1155 = (unsigned int)v1152 + 8LL,
                                                        v1150 = MemoryAlloc(v1155),
                                                        (v881 = (char *)v1150) == 0) )
                                                  {
                                                    v922 = v1138;
                                                    v1126 = -805306367;
                                                    goto LABEL_1429;
                                                  }
                                                  v882 = 0;
                                                  v1129 = 0;
                                                  v883 = 0;
                                                  if ( (_DWORD)v1152 )
                                                  {
                                                    do
                                                    {
                                                      v882 ^= *(_BYTE *)(v883 + v1161);
                                                      ++v883;
                                                    }
                                                    while ( v883 < (unsigned int)v1152 );
                                                    v1129 = v882;
                                                  }
                                                  v1160 = v92;
                                                  v1153 = v855;
                                                  lpMem = v857;
                                                  v1135 = (SIZE_T)v861;
                                                  Size = 0xC81ECB17B1B54A58uLL;
                                                  v1156 = (LPVOID)((unsigned __int64)(unsigned int)v1152 >> 3);
                                                  if ( v1156 )
                                                  {
                                                    v884 = v1150;
                                                    v885 = v1156;
                                                    v886 = 0;
                                                    LODWORD(v1148) = WORD1(Size);
                                                    v887 = -1;
                                                    LODWORD(v1134) = HIDWORD(Size) ^ 0xB1B54A58;
                                                    v888 = HIDWORD(Size) ^ 0xB1B54A58;
                                                    v889 = (unsigned __int8 *)v1138;
                                                    LODWORD(v1139) = HIWORD(Size);
                                                    v890 = WORD2(Size);
                                                    v1161 = 0;
                                                    LODWORD(v1146) = 0;
                                                    LODWORD(v1157) = 0;
                                                    do
                                                    {
                                                      v891 = v889[1];
                                                      v892 = *v889;
                                                      v893 = v889[4];
                                                      v889 += 8;
                                                      v894 = *(v889 - 5)
                                                           | ((*(v889 - 6) | ((v891 | (v892 << 8)) << 8)) << 8);
                                                      v895 = *(v889 - 1)
                                                           | ((*(v889 - 2) | ((*(v889 - 3) | (v893 << 8)) << 8)) << 8);
                                                      v896 = v886 ^ v894 ^ ((v887 ^ v895) - 19032);
                                                      v897 = __ROR4__(v896, 15);
                                                      v898 = HIDWORD(Size) ^ v896;
                                                      v899 = v887 ^ v895 ^ (__ROR4__(v898, 7) + WORD1(Size) * v897);
                                                      v900 = v898
                                                           ^ (v890 * __ROR4__(v899 - 1313519016, 9) - __ROR4__(v899, 10));
                                                      v901 = v899
                                                           ^ (__ROR4__(v900, 27)
                                                            + HIWORD(Size) * __ROR4__(v890 ^ v900, 28));
                                                      v902 = v900 ^ (HIDWORD(Size) - (v901 ^ 0xB1B54A58));
                                                      v903 = v901 ^ (WORD1(Size) * (v902 - 19032) - (v902 >> 6));
                                                      v904 = v902 ^ (19032 * (v890 ^ __ROR4__(v903, 15)));
                                                      v905 = v903 ^ (v890 * (HIWORD(Size) + __ROR4__(~v904, 3)));
                                                      v906 = v904 ^ (v905 - HIDWORD(Size) - 19032);
                                                      v907 = v905
                                                           ^ (v1148 * ((unsigned int)v1139 ^ v906))
                                                           ^ __ROR4__(v906, 10);
                                                      v908 = v906
                                                           ^ __ROR4__(v907, 3)
                                                           ^ (v890 * __ROR4__(v907 ^ 0x4A58, 26));
                                                      v909 = v907 ^ (19032 * (__ROR4__(v908, 15) - HIWORD(Size)));
                                                      v910 = v908
                                                           ^ ((v909 ^ (v909 >> 14)) >> 1)
                                                           ^ (19032 * (v909 ^ HIWORD(Size)))
                                                           ^ (19032 * (((v909 - v890) >> 29) | (8 * (v909 - v890))));
                                                      v911 = v909 ^ (WORD1(Size) * (v910 - v890) - (v910 >> 13));
                                                      v912 = v910
                                                           ^ __ROR4__(v911, 11)
                                                           ^ (v890 * __ROR4__(-1313519016 - v911, 9));
                                                      v913 = v911 ^ (v912 + 1313519016 - HIWORD(Size));
                                                      v914 = v912 ^ (19032 * (v913 ^ WORD1(Size)) - __ROR4__(v913, 7));
                                                      v915 = v913
                                                           ^ (WORD1(Size) * __ROR4__(v914 ^ HIWORD(Size), 28)
                                                            - __ROR4__(v914, 16));
                                                      v916 = v914
                                                           ^ (__ROR4__(v915, 4) + v890
                                                                                * __ROR4__(-1313519016 - v915, 10));
                                                      v917 = v915
                                                           ^ __ROR4__(v916, 9)
                                                           ^ (HIWORD(Size) * __ROR4__(v916 + 1313519016, 4));
                                                      v918 = v916
                                                           ^ (19032 * __ROR4__(v917 ^ HIDWORD(Size), 24)
                                                            - __ROR4__(v917, 30));
                                                      v919 = v917
                                                           ^ (WORD1(Size) * __ROR4__(HIDWORD(Size) - v918, 11)
                                                            - __ROR4__(v918, 12));
                                                      v920 = v1157 ^ v919;
                                                      LODWORD(v1157) = v895;
                                                      v921 = v918 ^ (v919 >> 8) ^ (v890 * (WORD1(Size) ^ v919));
                                                      v886 = v921 ^ v1146;
                                                      LODWORD(v1146) = v894;
                                                      v884[3] = v886;
                                                      v887 = v921 ^ v888 ^ v920;
                                                      v884[7] = v887;
                                                      v884[2] = __ROR4__(v886, 8);
                                                      v884[6] = __ROR4__(v887, 8);
                                                      v884[1] = __ROR4__(v886, 16);
                                                      v884[5] = __ROR4__(v887, 16);
                                                      *v884 = __ROR4__(v886, 24);
                                                      v884[4] = __ROR4__(v887, 24);
                                                      v884 += 8;
                                                      ++v1161;
                                                    }
                                                    while ( v1161 < (unsigned __int64)v885 );
                                                    v882 = v1129;
                                                    v90 = Src;
                                                    v861 = (unsigned int *)v1135;
                                                    v92 = v1160;
                                                    v855 = v1153;
                                                    v857 = lpMem;
                                                    v922 = v1138;
                                                    v881 = (char *)v1150;
                                                  }
                                                  else
                                                  {
                                                    v922 = v1138;
                                                    lpMem = v857;
                                                  }
                                                  *(_QWORD *)&v881[(unsigned int)v1152] = v882;
                                                  v924 = GetProcessHeap();
                                                  v925 = HeapAlloc(v924, 8u, 0x30u);
                                                  v1135 = (SIZE_T)v925;
                                                  if ( !v925 )
                                                  {
                                                    LODWORD(v1143) = -1073741801;
LABEL_1207:
                                                    v926 = v1136;
                                                    goto LABEL_1208;
                                                  }
                                                  *v925 = v1155;
                                                  lpMem = v857;
                                                  v1138 = v922;
                                                  v934 = GetProcessHeap();
                                                  v935 = HeapAlloc(v934, 8u, (unsigned int)v1155);
                                                  v936 = v1135;
                                                  if ( v935 )
                                                  {
                                                    *(_QWORD *)(v1135 + 8) = v935;
                                                    memcpy_0(v935, v1150, (unsigned int)v1155);
                                                    *(_DWORD *)(v1135 + 16) = 160;
                                                    v937 = GetProcessHeap();
                                                    v938 = HeapAlloc(v937, 8u, 0xA0u);
                                                    v936 = v1135;
                                                    if ( v938 )
                                                    {
                                                      *(_QWORD *)(v1135 + 24) = v938;
                                                      *v938 = xmmword_18002F400;
                                                      v938[1] = xmmword_18002F410;
                                                      v938[2] = xmmword_18002F420;
                                                      v938[3] = xmmword_18002F430;
                                                      v938[4] = xmmword_18002F440;
                                                      v938[5] = xmmword_18002F450;
                                                      v938[6] = xmmword_18002F460;
                                                      v938[7] = xmmword_18002F470;
                                                      v938[8] = xmmword_18002F480;
                                                      v938[9] = xmmword_18002F490;
                                                      *(_DWORD *)(v936 + 32) = 8;
                                                      v939 = GetProcessHeap();
                                                      v940 = HeapAlloc(v939, 8u, 8u);
                                                      if ( v940 )
                                                      {
                                                        v946 = v1135;
                                                        *(_QWORD *)(v1135 + 40) = v940;
                                                        *v940 = qword_18002F4A0;
                                                        v926 = (void *)v946;
                                                        v1138 = v922;
                                                        LODWORD(v1143) = 0;
                                                        lpMem = v857;
                                                        goto LABEL_1230;
                                                      }
                                                      v936 = v1135;
                                                    }
                                                    lpMem = v857;
                                                    v1138 = v922;
                                                    v1135 = v936;
                                                  }
                                                  v941 = *(void **)(v936 + 8);
                                                  LODWORD(v1143) = -1073741801;
                                                  v1156 = v941;
                                                  if ( v941 )
                                                  {
                                                    v942 = GetProcessHeap();
                                                    HeapFree(v942, 0, v1156);
                                                    v936 = v1135;
                                                    *(_QWORD *)(v1135 + 8) = 0;
                                                  }
                                                  v1156 = *(LPVOID *)(v936 + 24);
                                                  if ( v1156 )
                                                  {
                                                    v943 = GetProcessHeap();
                                                    HeapFree(v943, 0, v1156);
                                                    v936 = v1135;
                                                    *(_QWORD *)(v1135 + 24) = 0;
                                                  }
                                                  v1156 = *(LPVOID *)(v936 + 40);
                                                  if ( v1156 )
                                                  {
                                                    v944 = GetProcessHeap();
                                                    HeapFree(v944, 0, v1156);
                                                    *(_QWORD *)(v1135 + 40) = 0;
                                                  }
                                                  v945 = GetProcessHeap();
                                                  HeapFree(v945, 0, (LPVOID)v1135);
                                                  if ( (v1143 & 0x80000000) != 0LL )
                                                    goto LABEL_1207;
                                                  v926 = v1151;
LABEL_1230:
                                                  v1151 = 0;
LABEL_1208:
                                                  v1136 = v926;
                                                  v927 = GetProcessHeap();
                                                  HeapFree(v927, 0, v1150);
                                                  v928 = v1151;
                                                  if ( v1151 )
                                                  {
                                                    v1156 = (LPVOID)*((_QWORD *)v1151 + 1);
                                                    if ( v1156 )
                                                    {
                                                      v929 = GetProcessHeap();
                                                      HeapFree(v929, 0, v1156);
                                                      v928 = v1151;
                                                      *((_QWORD *)v1151 + 1) = 0;
                                                    }
                                                    v1156 = (LPVOID)*((_QWORD *)v928 + 3);
                                                    if ( v1156 )
                                                    {
                                                      v930 = GetProcessHeap();
                                                      HeapFree(v930, 0, v1156);
                                                      v928 = v1151;
                                                      *((_QWORD *)v1151 + 3) = 0;
                                                    }
                                                    v1156 = (LPVOID)*((_QWORD *)v928 + 5);
                                                    if ( v1156 )
                                                    {
                                                      v931 = GetProcessHeap();
                                                      HeapFree(v931, 0, v1156);
                                                      *((_QWORD *)v1151 + 5) = 0;
                                                    }
                                                    v932 = GetProcessHeap();
                                                    HeapFree(v932, 0, v1151);
                                                    v933 = v1136;
                                                  }
                                                  else
                                                  {
                                                    v933 = v1136;
                                                  }
                                                  v947 = v1143 | 0x10000000;
                                                  if ( (v1143 & 0x80000000) != 0LL )
                                                    goto LABEL_1261;
                                                  if ( *v933 >= 0xFFFFFFFC
                                                    || (v948 = *v933 + 8, v948 < *v933 + 4)
                                                    || (v949 = v948 + v933[4], v1161 = (SIZE_T)(v933 + 4), v949 < v948)
                                                    || (v950 = v949 + 4, v949 + 4 < v949)
                                                    || (v951 = v950 + v933[8], LODWORD(v1134) = v951, v951 < v950) )
                                                  {
                                                    v1138 = v922;
                                                    goto LABEL_1260;
                                                  }
                                                  v952 = v951;
                                                  v953 = GetProcessHeap();
                                                  v954 = HeapAlloc(v953, 8u, v952);
                                                  v1135 = (SIZE_T)v954;
                                                  if ( !v954 )
                                                  {
                                                    v857 = lpMem;
                                                    v922 = v1138;
                                                    v1126 = -805306345;
                                                    goto LABEL_1262;
                                                  }
                                                  v955 = (const void **)v1136;
                                                  *v954 = *(_DWORD *)v1136;
                                                  v1156 = v954 + 1;
                                                  if ( v954 + 1 < v954 )
                                                  {
                                                    v1135 = (SIZE_T)v954;
                                                  }
                                                  else
                                                  {
                                                    memcpy_0(v954 + 1, v955[1], *(unsigned int *)v955);
                                                    v956 = (char *)v1156 + *(unsigned int *)v955;
                                                    if ( v956 >= v1156 )
                                                    {
                                                      v957 = (unsigned int *)v1161;
                                                      *v956 = *(_DWORD *)v1161;
                                                      v1156 = v956 + 1;
                                                      if ( v956 + 1 >= v956 )
                                                      {
                                                        memcpy_0(v956 + 1, v955[3], *v957);
                                                        v958 = (char *)v1156 + *(unsigned int *)v1161;
                                                        if ( v958 >= v1156 )
                                                        {
                                                          *v958 = *((_DWORD *)v955 + 8);
                                                          v1156 = v958 + 1;
                                                          if ( v958 + 1 >= v958 )
                                                          {
                                                            memcpy_0(v958 + 1, v955[5], *((unsigned int *)v955 + 8));
                                                            v959 = (char *)v1156 + *((unsigned int *)v955 + 8);
                                                            v1138 = v922;
                                                            if ( v959 >= v1156 )
                                                            {
                                                              v960 = v1135;
                                                              v857 = lpMem;
                                                              v1142 = (LPVOID)v1135;
                                                              LODWORD(v1146) = (_DWORD)v1134;
                                                              if ( !v861 || (unsigned int)v1154 <= 1 )
                                                                goto LABEL_1254;
                                                              v961 = (const WCHAR *)v861;
                                                              v962 = 0;
                                                              do
                                                              {
                                                                v963 = v961 + 2;
                                                                if ( v961 + 2 < v961 )
                                                                  goto LABEL_1426;
                                                                v961 = (const WCHAR *)((char *)v963
                                                                                     + *(unsigned int *)v961);
                                                                v1164 = v961;
                                                                if ( v961 < v963 )
                                                                  goto LABEL_1426;
                                                                ++v962;
                                                              }
                                                              while ( !v962 );
                                                              if ( v961 + 2 < v961 )
                                                                goto LABEL_1426;
                                                              if ( (unsigned int)v1154 <= 2 )
                                                              {
LABEL_1254:
                                                                v1126 = -1073741811;
LABEL_1427:
                                                                v922 = v1138;
                                                                goto LABEL_1262;
                                                              }
                                                              v965 = v861;
                                                              LODWORD(v1148) = 0;
                                                              do
                                                              {
                                                                v966 = v965 + 1;
                                                                if ( v965 + 1 < v965 )
                                                                  goto LABEL_1426;
                                                                v965 = (unsigned int *)((char *)v966 + *v965);
                                                                v1156 = v965;
                                                                if ( v965 < v966 )
                                                                  goto LABEL_1426;
                                                                LODWORD(v1148) = v1148 + 1;
                                                                v967 = (void *)v960;
                                                                v1153 = v855;
                                                                v1151 = v857;
                                                                v1143 = (SIZE_T)v861;
                                                                v1152 = v922;
                                                                lpMem = v1136;
                                                                v1135 = v960;
                                                              }
                                                              while ( (unsigned int)v1148 < 2 );
                                                              if ( v965 + 1 < v1156
                                                                || *(_DWORD *)v1164 >= 0xFFFFFFD0
                                                                || (v968 = *(_DWORD *)v1164 + 52,
                                                                    v968 < *(_DWORD *)v1164 + 48)
                                                                || (v969 = v968 + *(_DWORD *)v1156,
                                                                    LODWORD(Size) = v969,
                                                                    v969 < v968) )
                                                              {
LABEL_1426:
                                                                v1126 = -1073741675;
                                                                goto LABEL_1427;
                                                              }
                                                              if ( v969 > 0x400000 )
                                                              {
                                                                v1136 = lpMem;
                                                                v1126 = -2147418113;
                                                                v1142 = v967;
                                                                v1138 = v922;
                                                                goto LABEL_1427;
                                                              }
                                                              v970 = v969;
                                                              v971 = GetProcessHeap();
                                                              v972 = HeapAlloc(v971, 8u, v970);
                                                              v857 = v1151;
                                                              v776 = v972 == 0;
                                                              *((_QWORD *)&v973 + 1) = v972;
                                                              v1149 = v972;
                                                              *(_QWORD *)&v973 = v1135;
                                                              v1142 = (LPVOID)v1135;
                                                              v1136 = lpMem;
                                                              if ( v776 )
                                                              {
                                                                v1126 = -805306345;
                                                                v1149 = 0;
                                                                goto LABEL_1262;
                                                              }
                                                              v974 = (void *)v1135;
                                                              hModule = 0;
                                                              v1179 = 0;
                                                              v1180 = 0;
                                                              if ( !v1135 )
                                                              {
                                                                v1126 = -2147024809;
LABEL_1424:
                                                                v1142 = v974;
                                                                goto LABEL_1425;
                                                              }
                                                              v1179 = v973;
                                                              LODWORD(v1180) = v1146;
                                                              *(_QWORD *)((char *)&v1180 + 4) = (unsigned int)Size;
                                                              if ( GetModuleHandleExW(1u, L"ntdll.dll", &hModule)
                                                                && (v977 = GetProcAddress(
                                                                             hModule,
                                                                             "NtQuerySystemInformation")) != 0 )
                                                              {
                                                                v975 = ((__int64 (__fastcall *)(__int64, __int128 *))v977)(
                                                                         134,
                                                                         &v1179)
                                                                     | 0x10000000;
                                                                if ( v975 >= 0 )
                                                                {
                                                                  v978 = DWORD1(v1180);
LABEL_1290:
                                                                  if ( v978 < 4 )
                                                                  {
                                                                    v1126 = -805306306;
                                                                    goto LABEL_1288;
                                                                  }
                                                                  *((_QWORD *)&v973 + 1) = v1149;
                                                                  v979 = *(unsigned int *)v1149;
                                                                  v980 = (char *)v1149 + 4;
                                                                  LODWORD(v1139) = *(_DWORD *)v1149;
                                                                  v1164 = (LPCWSTR)((char *)v1149 + 4);
                                                                  if ( (char *)v1149 + 4 < v1149 )
                                                                  {
                                                                    v1126 = -805306219;
LABEL_1425:
                                                                    v1149 = (LPVOID)*((_QWORD *)&v973 + 1);
                                                                    goto LABEL_1262;
                                                                  }
                                                                  if ( v978 - 4 < (unsigned int)v979 )
                                                                  {
                                                                    v1126 = -805306306;
                                                                    goto LABEL_1288;
                                                                  }
                                                                  v1166 = v979;
                                                                  v1161 = (SIZE_T)&v980[v979];
                                                                  if ( &v980[v979] < v980
                                                                    || (unsigned int)v979 >= 0xFFFFFFFC )
                                                                  {
                                                                    goto LABEL_1420;
                                                                  }
                                                                  if ( v978 - ((_DWORD)v979 + 4) < 4 )
                                                                    goto LABEL_1298;
                                                                  v981 = *(_DWORD *)&v980[v979];
                                                                  LODWORD(v1146) = v981;
                                                                  v982 = v1161 + 4;
                                                                  if ( v1161 + 4 < v1161 )
                                                                    goto LABEL_1420;
                                                                  LODWORD(v1134) = v979 + 8;
                                                                  if ( (int)v979 + 8 < (unsigned int)(v979 + 4) )
                                                                    goto LABEL_1420;
                                                                  if ( v978 - (unsigned int)v1134 < v981 )
                                                                    goto LABEL_1298;
                                                                  lpModuleName = (LPCWSTR)v981;
                                                                  v1156 = (LPVOID)(v982 + v981);
                                                                  if ( (unsigned __int64)v1156 < v982 )
                                                                    goto LABEL_1420;
                                                                  v983 = (_DWORD)v1134 + v981;
                                                                  if ( (unsigned int)v1134 + v981 < (unsigned int)v1134 )
                                                                    goto LABEL_1420;
                                                                  if ( v978 - v983 < 4 )
                                                                    goto LABEL_1298;
                                                                  v984 = (unsigned int *)v1156;
                                                                  v1156 = (char *)v1156 + 4;
                                                                  if ( v1156 < v984
                                                                    || (v985 = v983 + 4, v983 + 4 < v983) )
                                                                  {
LABEL_1420:
                                                                    v1126 = -805306219;
                                                                    goto LABEL_1262;
                                                                  }
                                                                  v986 = *v984;
                                                                  LODWORD(v1157) = v986;
                                                                  if ( v978 - v985 < v986 )
                                                                    goto LABEL_1298;
                                                                  if ( v985 + v986 < v985 )
                                                                  {
                                                                    v1126 = -805306219;
                                                                    goto LABEL_1262;
                                                                  }
                                                                  if ( v978 != v985 + v986
                                                                    || (unsigned int)v979 + v981 + v986 + 12LL != v978 )
                                                                  {
LABEL_1298:
                                                                    v1142 = (LPVOID)v1135;
                                                                    v1136 = lpMem;
                                                                    v1126 = -805306306;
                                                                    goto LABEL_1262;
                                                                  }
                                                                  v987 = GetProcessHeap();
                                                                  v988 = HeapAlloc(v987, 8u, 0x30u);
                                                                  v1134 = v988;
                                                                  v989 = (size_t)v988;
                                                                  if ( !v988 )
                                                                  {
                                                                    v861 = (unsigned int *)v1143;
                                                                    v857 = v1151;
                                                                    v1142 = (LPVOID)v1135;
                                                                    v1136 = lpMem;
                                                                    v1126 = -805306345;
                                                                    goto LABEL_1262;
                                                                  }
                                                                  v990 = v1164;
                                                                  v1148 = 0;
                                                                  if ( v1164 )
                                                                  {
                                                                    *(_DWORD *)v988 = (_DWORD)v1139;
                                                                    v991 = GetProcessHeap();
                                                                    v992 = v1166;
                                                                    v993 = HeapAlloc(v991, 8u, v1166);
                                                                    if ( !v993 )
                                                                    {
LABEL_1324:
                                                                      v922 = v1152;
                                                                      v861 = (unsigned int *)v1143;
                                                                      v857 = v1151;
                                                                      v855 = v1153;
                                                                      v1142 = (LPVOID)v1135;
                                                                      v1136 = lpMem;
                                                                      v1003 = v1134;
                                                                      v1127 = -1073741801;
                                                                      v1138 = v1152;
                                                                      v1135 = v1143;
                                                                      v1004 = (void *)*((_QWORD *)v1134 + 1);
                                                                      lpMem = v1151;
                                                                      v1160 = v92;
                                                                      v1156 = v1004;
                                                                      if ( v1004 )
                                                                      {
                                                                        v1005 = GetProcessHeap();
                                                                        HeapFree(v1005, 0, v1156);
                                                                        v1003 = v1134;
                                                                        *((_QWORD *)v1134 + 1) = 0;
                                                                      }
                                                                      v1156 = (LPVOID)*((_QWORD *)v1003 + 3);
                                                                      if ( v1156 )
                                                                      {
                                                                        v1006 = GetProcessHeap();
                                                                        HeapFree(v1006, 0, v1156);
                                                                        v1003 = v1134;
                                                                        *((_QWORD *)v1134 + 3) = 0;
                                                                      }
                                                                      v1156 = (LPVOID)*((_QWORD *)v1003 + 5);
                                                                      if ( v1156 )
                                                                      {
                                                                        v1007 = GetProcessHeap();
                                                                        HeapFree(v1007, 0, v1156);
                                                                        *((_QWORD *)v1134 + 5) = 0;
                                                                      }
                                                                      v1008 = GetProcessHeap();
                                                                      HeapFree(v1008, 0, v1134);
                                                                      v1009 = (LPVOID *)v1148;
                                                                      goto LABEL_1334;
                                                                    }
                                                                    *(_QWORD *)(v989 + 8) = v993;
                                                                    v1127 = 0;
                                                                    memcpy_0(v993, v990, v992);
                                                                  }
                                                                  else
                                                                  {
                                                                    *(_DWORD *)v988 = 0;
                                                                    v988[1] = 0;
                                                                    v1127 = 0;
                                                                  }
                                                                  v994 = (const void *)(v1161 + 4);
                                                                  if ( v1161 == -4 )
                                                                  {
                                                                    *(_DWORD *)(v989 + 16) = 0;
                                                                    *(_QWORD *)(v989 + 24) = 0;
                                                                  }
                                                                  else
                                                                  {
                                                                    *(_DWORD *)(v989 + 16) = v1146;
                                                                    v995 = GetProcessHeap();
                                                                    v996 = lpModuleName;
                                                                    v997 = HeapAlloc(v995, 8u, (SIZE_T)lpModuleName);
                                                                    if ( !v997 )
                                                                    {
LABEL_1323:
                                                                      v1134 = (LPVOID)v989;
                                                                      goto LABEL_1324;
                                                                    }
                                                                    *(_QWORD *)(v989 + 24) = v997;
                                                                    v1127 = 0;
                                                                    memcpy_0(v997, v994, (size_t)v996);
                                                                  }
                                                                  v998 = v1156;
                                                                  if ( v1156 )
                                                                  {
                                                                    v999 = v1157;
                                                                    *(_DWORD *)(v989 + 32) = v1157;
                                                                    v1000 = v999;
                                                                    v1001 = GetProcessHeap();
                                                                    v1002 = HeapAlloc(v1001, 8u, (unsigned int)v1000);
                                                                    if ( !v1002 )
                                                                      goto LABEL_1323;
                                                                    *(_QWORD *)(v989 + 40) = v1002;
                                                                    v1127 = 0;
                                                                    memcpy_0(v1002, v998, v1000);
                                                                  }
                                                                  else
                                                                  {
                                                                    *(_DWORD *)(v989 + 32) = 0;
                                                                    *(_QWORD *)(v989 + 40) = 0;
                                                                  }
                                                                  v1009 = (LPVOID *)v989;
                                                                  v922 = v1152;
                                                                  v861 = (unsigned int *)v1143;
                                                                  v855 = v1153;
                                                                  v1142 = (LPVOID)v1135;
                                                                  v1148 = v989;
                                                                  v857 = v1151;
                                                                  v1136 = lpMem;
                                                                  v1138 = v1152;
                                                                  v1135 = v1143;
                                                                  lpMem = v1151;
                                                                  v1160 = v92;
LABEL_1334:
                                                                  v1010 = v1127;
                                                                  if ( v1127 < 0 )
                                                                  {
                                                                    if ( v1009 )
                                                                    {
                                                                      v1156 = v1009[1];
                                                                      if ( v1156 )
                                                                      {
                                                                        v1012 = GetProcessHeap();
                                                                        HeapFree(v1012, 0, v1156);
                                                                        v1009 = (LPVOID *)v1148;
                                                                        *(_QWORD *)(v1148 + 8) = 0;
                                                                      }
                                                                      v1156 = v1009[3];
                                                                      if ( v1156 )
                                                                      {
                                                                        v1013 = GetProcessHeap();
                                                                        HeapFree(v1013, 0, v1156);
                                                                        v1009 = (LPVOID *)v1148;
                                                                        *(_QWORD *)(v1148 + 24) = 0;
                                                                      }
                                                                      v1156 = v1009[5];
                                                                      if ( v1156 )
                                                                      {
                                                                        v1014 = GetProcessHeap();
                                                                        HeapFree(v1014, 0, v1156);
                                                                        *(_QWORD *)(v1148 + 40) = 0;
                                                                      }
                                                                      v1015 = GetProcessHeap();
                                                                      HeapFree(v1015, 0, (LPVOID)v1148);
                                                                      v1010 = v1127;
                                                                    }
                                                                    v1011 = (unsigned int *)v1144;
                                                                  }
                                                                  else
                                                                  {
                                                                    v1011 = (unsigned int *)v1009;
                                                                    v1144 = v1009;
                                                                  }
                                                                  v1126 = v1010 | 0x10000000;
                                                                  if ( v1010 < 0 )
                                                                  {
LABEL_1262:
                                                                    if ( !v922 )
                                                                    {
LABEL_1430:
                                                                      v1087 = v1136;
                                                                      if ( v1136 )
                                                                      {
                                                                        v1088 = (void *)*((_QWORD *)v1136 + 1);
                                                                        if ( v1088 )
                                                                        {
                                                                          v1089 = GetProcessHeap();
                                                                          HeapFree(v1089, 0, v1088);
                                                                          v1087[1] = 0;
                                                                        }
                                                                        v1090 = (void *)v1087[3];
                                                                        if ( v1090 )
                                                                        {
                                                                          v1091 = GetProcessHeap();
                                                                          HeapFree(v1091, 0, v1090);
                                                                          v1087[3] = 0;
                                                                        }
                                                                        v1092 = (void *)v1087[5];
                                                                        if ( v1092 )
                                                                        {
                                                                          v1093 = GetProcessHeap();
                                                                          HeapFree(v1093, 0, v1092);
                                                                          v1087[5] = 0;
                                                                        }
                                                                        v1094 = GetProcessHeap();
                                                                        HeapFree(v1094, 0, v1087);
                                                                      }
                                                                      v1095 = v1142;
                                                                      if ( v1142 )
                                                                      {
                                                                        v1096 = GetProcessHeap();
                                                                        HeapFree(v1096, 0, v1095);
                                                                      }
                                                                      v1097 = v1149;
                                                                      if ( v1149 )
                                                                      {
                                                                        v1098 = GetProcessHeap();
                                                                        HeapFree(v1098, 0, v1097);
                                                                      }
                                                                      v1099 = v1144;
                                                                      if ( v1144 )
                                                                      {
                                                                        v1100 = (void *)*((_QWORD *)v1144 + 1);
                                                                        if ( v1100 )
                                                                        {
                                                                          v1101 = GetProcessHeap();
                                                                          HeapFree(v1101, 0, v1100);
                                                                          v1099[1] = 0;
                                                                        }
                                                                        v1102 = (void *)v1099[3];
                                                                        if ( v1102 )
                                                                        {
                                                                          v1103 = GetProcessHeap();
                                                                          HeapFree(v1103, 0, v1102);
                                                                          v1099[3] = 0;
                                                                        }
                                                                        v1104 = (void *)v1099[5];
                                                                        if ( v1104 )
                                                                        {
                                                                          v1105 = GetProcessHeap();
                                                                          HeapFree(v1105, 0, v1104);
                                                                          v1099[5] = 0;
                                                                        }
                                                                        v1106 = GetProcessHeap();
                                                                        HeapFree(v1106, 0, v1099);
                                                                      }
                                                                      v1107 = (void *)v1137;
                                                                      if ( v1137 )
                                                                      {
                                                                        v1108 = GetProcessHeap();
                                                                        HeapFree(v1108, 0, v1107);
                                                                      }
                                                                      v879 = v1126;
                                                                      goto LABEL_1453;
                                                                    }
LABEL_1429:
                                                                    v1086 = GetProcessHeap();
                                                                    HeapFree(v1086, 0, v922);
                                                                    goto LABEL_1430;
                                                                  }
                                                                  if ( !v1011
                                                                    || (v1158 = *((_QWORD *)v1011 + 1)) == 0
                                                                    || !*v1011 )
                                                                  {
                                                                    v1126 = -805306355;
                                                                    goto LABEL_1262;
                                                                  }
                                                                  v1151 = (LPVOID)(*v1011 - 8LL);
                                                                  v1139 = MemoryAlloc((unsigned __int64)v1151);
                                                                  v1016 = v1139;
                                                                  if ( !v1139 )
                                                                  {
LABEL_1377:
                                                                    v1126 = -805306367;
                                                                    v1137 = 0;
                                                                    goto LABEL_1262;
                                                                  }
                                                                  v1017 = 0;
                                                                  v1018 = (unsigned __int64)v1151;
                                                                  v1155 = v1158;
                                                                  v1161 = (unsigned __int8)v1151 & 7;
                                                                  v1137 = 0x7F1137FAB69605ELL;
                                                                  lpModuleName = (LPCWSTR)v1139;
                                                                  if ( ((unsigned __int8)v1151 & 7) != 0 )
                                                                  {
                                                                    v1163 = 0;
                                                                    LODWORD(v1154) = 0;
                                                                    LODWORD(v1134) = 0;
                                                                    v1019 = 0;
                                                                    v1020 = 0;
                                                                    v1021 = 0;
                                                                    v1022 = (unsigned __int8 *)v1155;
                                                                    do
                                                                    {
                                                                      v1023 = *v1022++;
                                                                      LODWORD(v1143) = v1023;
                                                                      LODWORD(v1146) = 8 * v1019;
                                                                      if ( (unsigned int)v1019 >= 4 )
                                                                      {
                                                                        LODWORD(v1143) = (_DWORD)v1143 << (56 - v1146);
                                                                        v1021 |= v1143;
                                                                      }
                                                                      else
                                                                      {
                                                                        LODWORD(v1143) = (_DWORD)v1143 << (24 - v1146);
                                                                        v1020 |= v1143;
                                                                      }
                                                                      ++v1019;
                                                                    }
                                                                    while ( v1019 < (int)v1161 );
                                                                    v1018 = (unsigned __int64)v1151;
                                                                    LODWORD(v1154) = v1020;
                                                                    v1017 = 0;
                                                                    v1163 = v1021;
                                                                    v90 = Src;
                                                                    v1024 = v1161;
                                                                    v1025 = v1139;
                                                                    v1155 = (SIZE_T)v1022;
                                                                    v1138 = v922;
                                                                    v1135 = (SIZE_T)v861;
                                                                    lpMem = v857;
                                                                    v1153 = v855;
                                                                    v1160 = v92;
                                                                    v1026 = v1163 ^ 0x699A899C;
                                                                    LODWORD(v1134) = 0;
                                                                    v1027 = v1154 ^ 0x92F65A5;
                                                                    if ( (_DWORD)v1161 )
                                                                    {
                                                                      v1028 = (unsigned int)v1134;
                                                                      v1029 = v1154 ^ 0x92F65A5;
                                                                      v1030 = v1163 ^ 0x699A899C;
                                                                      do
                                                                      {
                                                                        v1156 = v1025 + 1;
                                                                        if ( v1028 >= 4 )
                                                                        {
                                                                          v1030 = __ROR4__(v1030, 24);
                                                                          v1031 = v1030;
                                                                        }
                                                                        else
                                                                        {
                                                                          v1029 = __ROR4__(v1029, 24);
                                                                          v1031 = v1029;
                                                                        }
                                                                        *v1025 = v1031;
                                                                        ++v1028;
                                                                        v1025 = v1156;
                                                                      }
                                                                      while ( (int)v1028 < (int)v1024 );
                                                                      v1017 = 0;
                                                                      v1016 = v1139;
                                                                      v1018 = (unsigned __int64)v1151;
                                                                      lpModuleName = (LPCWSTR)v1156;
                                                                      v90 = Src;
                                                                    }
                                                                    if ( v1024 <= 4 )
                                                                    {
                                                                      v1032 = 0;
                                                                      if ( v1024 < 4 )
                                                                        v1027 = v1027 >> (8 * (4 - v1024)) << (8 * (4 - v1024));
                                                                    }
                                                                    else
                                                                    {
                                                                      v1032 = v1026 >> (8 * (8 - v1024)) << (8 * (8 - v1024));
                                                                    }
                                                                  }
                                                                  else
                                                                  {
                                                                    LODWORD(v1154) = 0;
                                                                    v1032 = 0;
                                                                    v1027 = 0;
                                                                  }
                                                                  if ( v1018 >> 3 )
                                                                  {
                                                                    v1033 = HIDWORD(v1137);
                                                                    v1034 = v1018 >> 3;
                                                                    v1035 = (WCHAR *)lpModuleName;
                                                                    v1036 = v1154;
                                                                    v1161 = 0;
                                                                    v1037 = HIDWORD(v1137) ^ 0xAB69605E;
                                                                    v1038 = WORD2(v1137);
                                                                    LODWORD(v1143) = 24670;
                                                                    v1039 = (unsigned __int8 *)v1155;
                                                                    LODWORD(v1146) = HIDWORD(v1137) ^ 0xAB69605E;
                                                                    LODWORD(Size) = WORD2(v1137);
                                                                    do
                                                                    {
                                                                      v1040 = *v1039;
                                                                      v1041 = v1039[1];
                                                                      v1042 = v1039[4];
                                                                      v1039 += 8;
                                                                      v1043 = *(v1039 - 5)
                                                                            | ((*(v1039 - 6)
                                                                              | (((v1040 << 8) | v1041) << 8)) << 8);
                                                                      v1044 = v1027 ^ v1043;
                                                                      v1045 = *(v1039 - 1)
                                                                            | ((*(v1039 - 2)
                                                                              | ((*(v1039 - 3) | (v1042 << 8)) << 8)) << 8);
                                                                      v1046 = v1037 ^ v1032 ^ v1045 ^ v1027 ^ v1043;
                                                                      v1047 = v1044
                                                                            ^ (__ROR4__(v1046, 22)
                                                                             + v1038 * __ROR4__(v1046 + 1419157410, 27));
                                                                      v1048 = v1046
                                                                            ^ (WORD1(v1137) * __ROR4__(v1047 + v1033, 9)
                                                                             - __ROR4__(v1047, 30));
                                                                      v1049 = v1047
                                                                            ^ (v1143 * (v1048 - v1038) - (v1048 >> 13));
                                                                      v1050 = v1048
                                                                            ^ (HIWORD(v1137)
                                                                             * __ROR4__(WORD1(v1137) ^ v1049, 26)
                                                                             - __ROR4__(v1049, 30));
                                                                      v1051 = v1049 ^ (v1033 - (v1050 ^ 0xAB69605E));
                                                                      v1052 = v1050
                                                                            ^ (WORD1(v1137) * (v1038 ^ v1051))
                                                                            ^ __ROR4__(v1051, 6);
                                                                      v1053 = v1051
                                                                            ^ (__ROR4__(v1052, 30)
                                                                             + v1143 * __ROR4__(v1052 + v1033, 15));
                                                                      v1054 = v1052
                                                                            ^ (HIWORD(v1137)
                                                                             * __ROR4__(v1053 + 1419157410, 14)
                                                                             - __ROR4__(v1053, 24));
                                                                      v1055 = v1053
                                                                            ^ __ROR4__(v1054, 10)
                                                                            ^ (Size * __ROR4__(v1054 ^ 0xAB69605E, 12));
                                                                      v1056 = v1055
                                                                            ^ (HIWORD(v1137)
                                                                             * (v1143
                                                                              + __ROR4__(
                                                                                  ~(v1054
                                                                                  ^ (v1055 >> 10)
                                                                                  ^ (WORD1(v1137)
                                                                                   * (HIWORD(v1137) ^ v1055))),
                                                                                  5)));
                                                                      v1057 = v1054
                                                                            ^ (v1055 >> 10)
                                                                            ^ (WORD1(v1137) * (HIWORD(v1137) ^ v1055))
                                                                            ^ (v1056 - HIWORD(v1137))
                                                                            ^ 0xAB69605E;
                                                                      v1058 = v1056
                                                                            ^ ((v1057 >> 2)
                                                                             + Size
                                                                             * __ROR4__(HIWORD(v1137) ^ v1057, 30));
                                                                      v1059 = v1057
                                                                            ^ (__ROR4__(v1058, 25)
                                                                             + WORD1(v1137) * __ROR4__(v1058 - v1033, 6));
                                                                      v1060 = v1058
                                                                            ^ (v1143 * (Size ^ v1059)
                                                                             + __ROR4__(v1059, 9));
                                                                      v1061 = v1059
                                                                            ^ (__ROR4__(v1060, 25)
                                                                             + HIWORD(v1137)
                                                                             * __ROR4__(WORD1(v1137) ^ v1060, 27));
                                                                      v1038 = Size;
                                                                      v1062 = v1146 ^ v1060 ^ v1061;
                                                                      v1063 = v1061
                                                                            ^ (Size * (__ROR4__(v1062, 3) - WORD1(v1137)));
                                                                      v1064 = v1062
                                                                            ^ (v1143 * __ROR4__(v1063 - v1033, 1)
                                                                             - __ROR4__(v1063, 6));
                                                                      v1065 = v1063
                                                                            ^ (__ROR4__(v1064, 18)
                                                                             + HIWORD(v1137)
                                                                             * __ROR4__(v1064 - 1419157410, 29));
                                                                      v1066 = v1064
                                                                            ^ (Size * __ROR4__(v1065 - 1419157410, 17)
                                                                             - __ROR4__(v1065, 14));
                                                                      v1037 = v1146;
                                                                      v1067 = v1065
                                                                            ^ (v1066 >> 3)
                                                                            ^ (WORD1(v1137) * (v1143 ^ v1066));
                                                                      v1068 = v1067 ^ v1033;
                                                                      v1069 = v1067;
                                                                      v1032 = v1163 ^ v1067;
                                                                      v1163 = v1045;
                                                                      v1027 = v1036
                                                                            ^ v1066
                                                                            ^ __ROR4__(v1069, 30)
                                                                            ^ (v1143 * __ROR4__(v1068, 28));
                                                                      v1036 = v1043;
                                                                      *((_BYTE *)v1035 + 3) = v1027;
                                                                      *((_BYTE *)v1035 + 7) = v1032;
                                                                      *((_BYTE *)v1035 + 2) = __ROR4__(v1027, 8);
                                                                      *((_BYTE *)v1035 + 6) = __ROR4__(v1032, 8);
                                                                      *((_BYTE *)v1035 + 1) = __ROR4__(v1027, 16);
                                                                      *((_BYTE *)v1035 + 5) = __ROR4__(v1032, 16);
                                                                      *(_BYTE *)v1035 = __ROR4__(v1027, 24);
                                                                      *((_BYTE *)v1035 + 4) = __ROR4__(v1032, 24);
                                                                      v1035 += 4;
                                                                      ++v1161;
                                                                    }
                                                                    while ( v1161 < v1034 );
                                                                    v1017 = 0;
                                                                    v90 = Src;
                                                                    v861 = (unsigned int *)v1135;
                                                                    v92 = v1160;
                                                                    v855 = v1153;
                                                                    v857 = lpMem;
                                                                    v922 = v1138;
                                                                    v1016 = v1139;
                                                                  }
                                                                  v1070 = 0;
                                                                  if ( v1151 )
                                                                  {
                                                                    do
                                                                      v1017 ^= *((_BYTE *)v1016 + v1070++);
                                                                    while ( v1070 < (unsigned __int64)v1151 );
                                                                  }
                                                                  if ( v1017 != *(_QWORD *)((char *)v1151 + v1158) )
                                                                  {
                                                                    MemoryFree(v1016);
                                                                    goto LABEL_1377;
                                                                  }
                                                                  v1071 = v1136;
                                                                  v1072 = v1142;
                                                                  if ( (unsigned int)v1151 < 4 )
                                                                  {
                                                                    v1073 = -1073741762;
                                                                    v1137 = (SIZE_T)v1016;
LABEL_1418:
                                                                    v1126 = v1073 | 0x10000000;
                                                                    goto LABEL_1262;
                                                                  }
                                                                  v1137 = (SIZE_T)v1016;
                                                                  v1161 = (SIZE_T)(v1016 + 1);
                                                                  v1074 = (SIZE_T)v1016;
                                                                  if ( v1016 + 1 < v1016 )
                                                                    goto LABEL_1415;
                                                                  if ( (unsigned int)((_DWORD)v1151 - 4) < 4 )
                                                                  {
LABEL_1382:
                                                                    v1073 = -1073741762;
                                                                    v1137 = (SIZE_T)v1016;
LABEL_1417:
                                                                    v1136 = v1071;
                                                                    v1142 = v1072;
                                                                    goto LABEL_1418;
                                                                  }
                                                                  lpModuleName = (LPCWSTR)(v1016 + 2);
                                                                  v1071 = v1136;
                                                                  if ( v1016 + 2 < v1016 + 1 )
                                                                    goto LABEL_1415;
                                                                  if ( (unsigned int)((_DWORD)v1151 - 8) < v1016[1] )
                                                                    goto LABEL_1382;
                                                                  if ( v1016[1] >= 0xFFFFFFF8 )
                                                                  {
LABEL_1415:
                                                                    v1073 = -1073741675;
                                                                  }
                                                                  else
                                                                  {
                                                                    v1075 = (unsigned int)v1016[1];
                                                                    v1156 = (LPVOID)(unsigned int)v1151;
                                                                    v1135 = v1075;
                                                                    v1076 = v1075 + 4;
                                                                    v1071 = v1136;
                                                                    v1077 = (char *)v1016 + v1076 + 4;
                                                                    v1072 = v1142;
                                                                    if ( (char *)v1016 + (unsigned int)v1151 >= v1077 )
                                                                    {
                                                                      v1078 = lpModuleName;
                                                                      if ( (unsigned __int64)v1156
                                                                         + (char *)v1016
                                                                         - v1135
                                                                         - (char *)lpModuleName < 8 )
                                                                      {
                                                                        LODWORD(v1148) = 0;
                                                                        if ( lpModuleName )
                                                                        {
                                                                          v1016 = v1139;
                                                                          v1079 = (const WCHAR *)(v1135 + 4 + v1161);
                                                                          if ( v1079 < lpModuleName )
                                                                          {
                                                                            v1073 = -1073741675;
                                                                            v1137 = v1074;
                                                                            goto LABEL_1418;
                                                                          }
                                                                          v1080 = lpModuleName;
                                                                          if ( v1079 > lpModuleName )
                                                                          {
                                                                            v1081 = v1148;
                                                                            while ( v1080 + 2 >= v1080 )
                                                                            {
                                                                              if ( v1080 + 2 > v1079 )
                                                                                goto LABEL_1402;
                                                                              if ( *(_DWORD *)v1080 >= 0xFFFFFFFC )
                                                                                break;
                                                                              v1082 = (char *)v1080
                                                                                    + (unsigned int)(*(_DWORD *)v1080 + 4);
                                                                              if ( v1082 < (char *)v1080 )
                                                                                break;
                                                                              v1079 = (const WCHAR *)((char *)v1139 + v1135 + 8);
                                                                              if ( v1082 > (char *)v1079 )
                                                                                goto LABEL_1402;
                                                                              ++v1081;
                                                                              v1080 = (LPCWSTR)((char *)v1080
                                                                                              + (unsigned int)(*(_DWORD *)v1080 + 4));
                                                                              LODWORD(v1148) = v1081;
                                                                              if ( v1082 >= (char *)v1079 )
                                                                                goto LABEL_1401;
                                                                            }
                                                                            v1073 = -1073741675;
                                                                            goto LABEL_1418;
                                                                          }
                                                                          v1137 = (SIZE_T)v1139;
LABEL_1401:
                                                                          if ( v1080 != v1079 )
                                                                          {
LABEL_1402:
                                                                            v1073 = -1073741811;
                                                                            goto LABEL_1418;
                                                                          }
                                                                        }
                                                                        else
                                                                        {
                                                                          v1137 = (SIZE_T)v1016;
                                                                        }
                                                                        LODWORD(v1134) = *v1016;
                                                                        if ( v1016[1] )
                                                                        {
                                                                          v1083 = GetProcessHeap();
                                                                          v1084 = v1135;
                                                                          v1085 = HeapAlloc(v1083, 8u, v1135);
                                                                          if ( !v1085 )
                                                                          {
                                                                            v1073 = -1073741801;
                                                                            goto LABEL_1418;
                                                                          }
                                                                          v1078 = lpModuleName;
                                                                        }
                                                                        else
                                                                        {
                                                                          v1084 = v1135;
                                                                          v1085 = 0;
                                                                        }
                                                                        pcchLength = (size_t)v1085;
                                                                        if ( v1078 )
                                                                          memcpy_0(v1085, v1078, v1084);
                                                                        LODWORD(v1159) = v1148;
                                                                        v1073 = 0;
                                                                        if ( (_DWORD)v1134 != (_DWORD)v1148 )
                                                                          v1073 = -1073741762;
                                                                        goto LABEL_1418;
                                                                      }
                                                                    }
                                                                    v1073 = -1073741762;
                                                                  }
                                                                  v1137 = (SIZE_T)v1016;
                                                                  goto LABEL_1417;
                                                                }
                                                              }
                                                              else
                                                              {
                                                                v975 = GetLastError();
                                                                v976 = v975 < 0;
                                                                if ( v975 > 0 )
                                                                {
                                                                  v975 = (unsigned __int16)v975 | 0x80070000;
                                                                  v976 = v975 < 0;
                                                                }
                                                                if ( !v976 )
                                                                {
                                                                  v1126 = -2147467259;
                                                                  goto LABEL_1423;
                                                                }
                                                              }
                                                              v978 = Size;
                                                              if ( v975 == -805306333 )
                                                              {
                                                                v1126 = -2147024774;
LABEL_1288:
                                                                v1142 = (LPVOID)v1135;
                                                                v1136 = lpMem;
                                                                goto LABEL_1262;
                                                              }
                                                              if ( v975 >= 0 )
                                                                goto LABEL_1290;
                                                              v1126 = v975;
LABEL_1423:
                                                              *((_QWORD *)&v973 + 1) = v1149;
                                                              v974 = v1142;
                                                              goto LABEL_1424;
                                                            }
                                                            goto LABEL_1258;
                                                          }
                                                        }
                                                      }
                                                    }
                                                  }
                                                  v1138 = v922;
LABEL_1258:
                                                  v1136 = v955;
                                                  v857 = lpMem;
                                                  v964 = GetProcessHeap();
                                                  HeapFree(v964, 0, (LPVOID)v1135);
LABEL_1260:
                                                  v922 = v1138;
                                                  v947 = -805306219;
LABEL_1261:
                                                  v1126 = v947;
                                                  goto LABEL_1262;
                                                }
                                                v1161 = 196;
                                                v867 = (char *)v861;
                                                LODWORD(v1154) = 2;
                                                LODWORD(v1146) = 196;
                                                Src = v90;
                                                do
                                                {
                                                  v868 = *(_DWORD *)v867 + 4;
                                                  if ( *(_DWORD *)v867 >= 0xFFFFFFFC )
                                                    goto LABEL_1466;
                                                  v869 = &v867[v868];
                                                  if ( v869 < v867 )
                                                    goto LABEL_1467;
                                                  ++v860;
                                                  v867 += v868;
                                                }
                                                while ( v860 < 2 );
                                                v870 = v869 + 4;
                                                if ( v870 >= v867 && v867 + 12 <= (char *)v861 + (unsigned int)v1161 )
                                                {
                                                  *(_DWORD *)v867 = 8;
                                                  memcpy_0(v870, v857, 8u);
                                                  v866 = v1154 + 1;
                                                  LODWORD(v1148) = v1146;
                                                  v872 = (unsigned __int64)v861;
                                                  v873 = 0;
                                                  v871 = v1146;
                                                  if ( (_DWORD)v1154 != -1 )
                                                  {
                                                    while ( 1 )
                                                    {
                                                      v874 = *(_DWORD *)v872 + 4;
                                                      if ( *(_DWORD *)v872 >= 0xFFFFFFFC )
                                                        break;
                                                      if ( v872 + v874 < v872 )
                                                        goto LABEL_1467;
                                                      ++v873;
                                                      v872 += v874;
                                                      if ( v873 >= v866 )
                                                        goto LABEL_1185;
                                                    }
LABEL_1466:
                                                    if ( !v861 )
                                                      goto LABEL_1468;
                                                    goto LABEL_1467;
                                                  }
LABEL_1185:
                                                  if ( v872 + 4 >= v872
                                                    && v872 + 12 <= (unsigned __int64)v861 + (unsigned int)v1146 )
                                                  {
                                                    v875 = v1156;
                                                    *(_DWORD *)v872 = 8;
                                                    *(_QWORD *)(v872 + 4) = v875;
                                                    goto LABEL_1188;
                                                  }
                                                }
                                              }
                                            }
LABEL_1467:
                                            v1113 = GetProcessHeap();
                                            HeapFree(v1113, 0, v861);
LABEL_1468:
                                            v1114 = (void *)pcchLength;
                                            if ( pcchLength )
                                            {
                                              v1115 = GetProcessHeap();
                                              HeapFree(v1115, 0, v1114);
                                            }
                                            if ( !v855 )
                                              goto LABEL_1472;
                                            goto LABEL_1471;
                                          }
LABEL_1474:
                                          v91 = v92;
                                          v1173 = (DWORD *)v1176;
                                          v1155 = 0;
                                          goto LABEL_1477;
                                        }
                                        v1151 = (LPVOID)((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))off_18002F0F8[0])(
                                                          0,
                                                          0,
                                                          1027);
                                        if ( !v1151 )
                                        {
                                          GetLastError();
                                          goto LABEL_1159;
                                        }
                                        v393 = off_18002F098[0]();
                                        v394 = dword_18002F850;
                                        qword_18002F840 = v393;
                                        LODWORD(v1138) = dword_18002F850;
                                        memset_0(&v1190, 0, 0x70u);
                                        memset(v1246, 0, 44);
                                        v1165 = 0;
                                        while ( _InterlockedCompareExchange(&dword_18002F8EC, 1, 0) )
                                          ;
                                        v395 = dword_18002F8E8;
                                        if ( dword_18002F8E8 )
                                          goto LABEL_596;
                                        v396 = MemoryAlloc(0x338u);
                                        v397 = v396;
                                        if ( !v396 )
                                        {
LABEL_561:
                                          v392 = 0;
                                          goto LABEL_562;
                                        }
                                        v398 = v396;
                                        v399 = qword_18002B6E0;
                                        v400 = 103;
                                        v401 = 0;
                                        v402 = -1;
                                        v403 = 0;
                                        v404 = 0;
                                        do
                                        {
                                          v405 = *((unsigned __int8 *)v399 + 1);
                                          v406 = *(unsigned __int8 *)v399;
                                          v407 = *((unsigned __int8 *)v399++ + 4);
                                          v408 = *((unsigned __int8 *)v399 - 5)
                                               | ((*((unsigned __int8 *)v399 - 6) | ((v405 | (v406 << 8)) << 8)) << 8);
                                          v409 = v404 ^ v408;
                                          v410 = *((unsigned __int8 *)v399 - 1)
                                               | ((*((unsigned __int8 *)v399 - 2)
                                                 | ((*((unsigned __int8 *)v399 - 3) | (v407 << 8)) << 8)) << 8);
                                          v411 = v404 ^ v408 ^ v403 ^ v410 ^ 0xAC987321;
                                          v412 = v409 ^ (__ROR4__(v411, 22) + 4991 * __ROR4__(v411 + 1419157410, 27));
                                          v413 = v411 ^ (43881 * __ROR4__(v412 + 133239679, 9) - __ROR4__(v412, 30));
                                          v414 = v412 ^ (24670 * v413 - (v413 >> 13) - 123127970);
                                          v415 = v413 ^ (2033 * __ROR4__(v414 ^ 0xAB69, 26) - __ROR4__(v414, 30));
                                          v416 = v414 ^ (133239679 - (v415 ^ 0xAB69605E));
                                          v417 = v415 ^ (43881 * (v416 ^ 0x137F)) ^ __ROR4__(v416, 6);
                                          v418 = v416 ^ (__ROR4__(v417, 30) + 24670 * __ROR4__(v417 + 133239679, 15));
                                          v419 = v417 ^ (2033 * __ROR4__(v418 + 1419157410, 14) - __ROR4__(v418, 24));
                                          v420 = v418 ^ __ROR4__(v419, 10) ^ (4991 * __ROR4__(v419 ^ 0xAB69605E, 12));
                                          v421 = v419 ^ (v420 >> 10) ^ (43881 * (v420 ^ 0x7F1));
                                          v422 = v420 ^ (2033 * (__ROR4__(~v421, 5) + 24670));
                                          v423 = v422
                                               ^ (((v421 ^ (v422 - 2033) ^ 0xAB69605E) >> 2)
                                                + 4991 * __ROR4__(v421 ^ (v422 - 2033) ^ 0xAB6967AF, 30));
                                          v424 = v421
                                               ^ (v422 - 2033)
                                               ^ 0xAB69605E
                                               ^ (__ROR4__(v423, 25) + 43881 * __ROR4__(v423 - 133239679, 6));
                                          v425 = v423 ^ (24670 * (v424 ^ 0x137F) + __ROR4__(v424, 9));
                                          v426 = v424 ^ (__ROR4__(v425, 25) + 2033 * __ROR4__(v425 ^ 0xAB69, 27));
                                          v427 = v425 ^ v426 ^ 0xAC987321;
                                          v428 = v426 ^ (4991 * __ROR4__(v427, 3) - 219010071);
                                          v429 = v427 ^ (24670 * __ROR4__(v428 - 133239679, 1) - __ROR4__(v428, 6));
                                          v430 = v428 ^ (__ROR4__(v429, 18) + 2033 * __ROR4__(v429 - 1419157410, 29));
                                          v431 = v429 ^ (4991 * __ROR4__(v430 - 1419157410, 17) - __ROR4__(v430, 14));
                                          v432 = v430 ^ (v431 >> 3) ^ (43881 * (v431 ^ 0x605E));
                                          v433 = __ROR4__(v432, 30);
                                          v403 = v402 ^ v432;
                                          v402 = v410;
                                          v404 = v401
                                               ^ v431
                                               ^ v433
                                               ^ (24670
                                                * __ROR4__(
                                                    v430 ^ (v431 >> 3) ^ (43881 * (v431 ^ 0x605E)) ^ 0x7F1137F,
                                                    28));
                                          v401 = v408;
                                          v398[3] = v404;
                                          v398[7] = v403;
                                          v398[2] = __ROR4__(v404, 8);
                                          v398[6] = __ROR4__(v403, 8);
                                          v398[1] = __ROR4__(v404, 16);
                                          v398[5] = __ROR4__(v403, 16);
                                          *v398 = __ROR4__(v404, 24);
                                          v398[4] = __ROR4__(v403, 24);
                                          v398 += 8;
                                          --v400;
                                        }
                                        while ( v400 );
                                        v394 = (unsigned int)v1138;
                                        v90 = Src;
                                        v434 = 0;
                                        v92 = v1160;
                                        v435 = 0;
                                        do
                                          v435 ^= v397[v434++];
                                        while ( v434 < 0x338 );
                                        if ( v435 != 64 )
                                        {
                                          MemoryFree(v397);
                                          goto LABEL_561;
                                        }
                                        LODWORD(Size) = 0;
                                        LODWORD(v1149) = 0;
                                        v397[823] = 0;
                                        memset_0(qword_18002F860, 0, sizeof(qword_18002F860));
                                        if ( *v397 )
                                        {
                                          v438 = (unsigned int)v1149;
                                          v1155 = (SIZE_T)v397;
                                          while ( 1 )
                                          {
                                            v439 = -1;
                                            do
                                              ++v439;
                                            while ( *(_WORD *)&v397[2 * v439] );
                                            v1158 = 3 * v438;
                                            if ( !GetModuleHandleExW(
                                                    0,
                                                    (LPCWSTR)v397,
                                                    (HMODULE *)&qword_18002F860[3 * v438]) )
                                              break;
                                            v440 = v1158;
                                            v441 = &v397[2 * v439];
                                            v442 = qword_18002F860[v1158];
                                            if ( *(_WORD *)v442 == 23117
                                              && (v444 = *(int *)(v442 + 60), (unsigned int)v444 < 0x10000000)
                                              && (v445 = qword_18002F860[v1158] + v444, v445 >= qword_18002F860[v1158])
                                              && *(_DWORD *)v445 == 17744 )
                                            {
                                              if ( ((*(_WORD *)(v445 + 24) - 267) & 0xFEFF) != 0 )
                                              {
                                                v443 = -1073741811;
                                              }
                                              else
                                              {
                                                v443 = 0;
                                                *(__int64 *)((char *)&qword_18002F860[v1158 + 1] + 4) = *(_QWORD *)(v445 + 136);
                                                LODWORD(qword_18002F860[v440 + 1]) = *(_DWORD *)(v445 + 80);
                                              }
                                            }
                                            else
                                            {
                                              v443 = -1073741701;
                                            }
                                            v446 = *(_DWORD *)(v441 + 2);
                                            v447 = 0;
                                            v397 = v441 + 6;
                                            LODWORD(v1146) = v446;
                                            LODWORD(v1148) = 0;
                                            if ( v446 )
                                            {
                                              do
                                              {
                                                v448 = -1;
                                                do
                                                  ++v448;
                                                while ( v397[v448] );
                                                lpModuleName = (LPCWSTR)v448;
                                                if ( v443 >= 0 )
                                                {
                                                  v449 = GetProcAddress((HMODULE)qword_18002F860[v440], v397);
                                                  if ( !v449 )
                                                    goto LABEL_590;
                                                  v440 = v1158;
                                                  off_18002F000[(unsigned int)Size] = v449;
                                                  v448 = (__int64)lpModuleName;
                                                  v447 = v1148;
                                                }
                                                v397 += v448 + 1;
                                                LODWORD(Size) = Size + 1;
                                                LODWORD(v1148) = ++v447;
                                              }
                                              while ( v447 < (unsigned int)v1146 );
                                            }
                                            v438 = (unsigned int)((_DWORD)v1149 + 1);
                                            LODWORD(v1149) = (_DWORD)v1149 + 1;
                                            if ( !*v397 )
                                              goto LABEL_590;
                                          }
                                          v443 = -1073741702;
LABEL_590:
                                          v397 = (_BYTE *)v1155;
                                          if ( !v1155 )
                                            goto LABEL_594;
                                        }
                                        else
                                        {
                                          v443 = 0;
                                        }
                                        v450 = GetProcessHeap();
                                        HeapFree(v450, 0, v397);
LABEL_594:
                                        v392 = 0;
                                        if ( v443 < 0 )
                                        {
LABEL_562:
                                          for ( m = 0; m != 4; ++m )
                                          {
                                            v437 = (HMODULE)qword_18002F860[3 * m];
                                            if ( v437 )
                                              FreeLibrary(v437);
                                          }
                                          memset_0(qword_18002F860, 0, sizeof(qword_18002F860));
                                          memcpy_0(off_18002F000, off_180028410, 0x170u);
LABEL_597:
                                          _InterlockedExchange(&dword_18002F8EC, 0);
                                          v1135 = 0;
                                          v1139 = 0;
                                          while ( _InterlockedCompareExchange(&dword_18002F8EC, 1, 0) )
                                            ;
                                          v451 = dword_18002F8E8;
                                          if ( dword_18002F8E8 )
                                            goto LABEL_642;
                                          v452 = (const WCHAR *)MemoryAlloc(0x338u);
                                          lpModuleName = v452;
                                          if ( !v452 )
                                          {
LABEL_607:
                                            v392 = 0;
                                            goto LABEL_608;
                                          }
                                          v453 = (WCHAR *)v452;
                                          v454 = qword_18002B6E0;
                                          v455 = -1;
                                          v456 = 103;
                                          v457 = 0;
                                          v458 = 0;
                                          v459 = 0;
                                          do
                                          {
                                            v460 = *((unsigned __int8 *)v454 + 1);
                                            v461 = *(unsigned __int8 *)v454;
                                            v462 = *((unsigned __int8 *)v454++ + 4);
                                            v463 = *((unsigned __int8 *)v454 - 5)
                                                 | ((*((unsigned __int8 *)v454 - 6) | ((v460 | (v461 << 8)) << 8)) << 8);
                                            v464 = v459 ^ v463;
                                            v465 = *((unsigned __int8 *)v454 - 1)
                                                 | ((*((unsigned __int8 *)v454 - 2)
                                                   | ((*((unsigned __int8 *)v454 - 3) | (v462 << 8)) << 8)) << 8);
                                            v466 = v458 ^ v465 ^ v459 ^ v463 ^ 0xAC987321;
                                            v467 = v464 ^ (__ROR4__(v466, 22) + 4991 * __ROR4__(v466 + 1419157410, 27));
                                            v468 = v466 ^ (43881 * __ROR4__(v467 + 133239679, 9) - __ROR4__(v467, 30));
                                            v469 = v467 ^ (24670 * v468 - (v468 >> 13) - 123127970);
                                            v470 = v468 ^ (2033 * __ROR4__(v469 ^ 0xAB69, 26) - __ROR4__(v469, 30));
                                            v471 = v469 ^ (133239679 - (v470 ^ 0xAB69605E));
                                            v472 = v470 ^ (43881 * (v471 ^ 0x137F)) ^ __ROR4__(v471, 6);
                                            v473 = v471 ^ (__ROR4__(v472, 30) + 24670 * __ROR4__(v472 + 133239679, 15));
                                            v474 = v472 ^ (2033 * __ROR4__(v473 + 1419157410, 14) - __ROR4__(v473, 24));
                                            v475 = v473 ^ __ROR4__(v474, 10) ^ (4991 * __ROR4__(v474 ^ 0xAB69605E, 12));
                                            v476 = v474 ^ (v475 >> 10) ^ (43881 * (v475 ^ 0x7F1));
                                            v477 = v475 ^ (2033 * (__ROR4__(~v476, 5) + 24670));
                                            v478 = v477
                                                 ^ (((v476 ^ (v477 - 2033) ^ 0xAB69605E) >> 2)
                                                  + 4991 * __ROR4__(v476 ^ (v477 - 2033) ^ 0xAB6967AF, 30));
                                            v479 = v476
                                                 ^ (v477 - 2033)
                                                 ^ 0xAB69605E
                                                 ^ (__ROR4__(v478, 25) + 43881 * __ROR4__(v478 - 133239679, 6));
                                            v480 = v478 ^ (24670 * (v479 ^ 0x137F) + __ROR4__(v479, 9));
                                            v481 = v479 ^ (__ROR4__(v480, 25) + 2033 * __ROR4__(v480 ^ 0xAB69, 27));
                                            v482 = v480 ^ v481 ^ 0xAC987321;
                                            v483 = v481 ^ (4991 * __ROR4__(v482, 3) - 219010071);
                                            v484 = v482 ^ (24670 * __ROR4__(v483 - 133239679, 1) - __ROR4__(v483, 6));
                                            v485 = v483 ^ (__ROR4__(v484, 18) + 2033 * __ROR4__(v484 - 1419157410, 29));
                                            v486 = v484 ^ (4991 * __ROR4__(v485 - 1419157410, 17) - __ROR4__(v485, 14));
                                            v487 = v485 ^ (v486 >> 3) ^ (43881 * (v486 ^ 0x605E));
                                            v488 = __ROR4__(v487, 30);
                                            v458 = v455 ^ v487;
                                            v455 = v465;
                                            v459 = v457
                                                 ^ v486
                                                 ^ v488
                                                 ^ (24670
                                                  * __ROR4__(
                                                      v485 ^ (v486 >> 3) ^ (43881 * (v486 ^ 0x605E)) ^ 0x7F1137F,
                                                      28));
                                            v457 = v463;
                                            *((_BYTE *)v453 + 3) = v459;
                                            *((_BYTE *)v453 + 7) = v458;
                                            *((_BYTE *)v453 + 2) = __ROR4__(v459, 8);
                                            *((_BYTE *)v453 + 6) = __ROR4__(v458, 8);
                                            *((_BYTE *)v453 + 1) = __ROR4__(v459, 16);
                                            *((_BYTE *)v453 + 5) = __ROR4__(v458, 16);
                                            *(_BYTE *)v453 = __ROR4__(v459, 24);
                                            *((_BYTE *)v453 + 4) = __ROR4__(v458, 24);
                                            v453 += 4;
                                            --v456;
                                          }
                                          while ( v456 );
                                          v394 = (unsigned int)v1138;
                                          v90 = Src;
                                          v489 = 0;
                                          v490 = (WCHAR *)lpModuleName;
                                          v491 = 0;
                                          do
                                            v491 ^= *((_BYTE *)lpModuleName + v489++);
                                          while ( v489 < 0x338 );
                                          if ( v491 != 64 )
                                          {
                                            MemoryFree((void *)lpModuleName);
                                            goto LABEL_607;
                                          }
                                          LODWORD(Size) = 0;
                                          LODWORD(v1149) = 0;
                                          *((_BYTE *)lpModuleName + 823) = 0;
                                          memset_0(qword_18002F860, 0, sizeof(qword_18002F860));
                                          if ( *(_BYTE *)v490 )
                                          {
                                            v494 = (unsigned int)v1149;
                                            v1155 = (SIZE_T)v490;
                                            while ( 1 )
                                            {
                                              v495 = -1;
                                              do
                                                ++v495;
                                              while ( v490[v495] );
                                              v1158 = 3 * v494;
                                              if ( !GetModuleHandleExW(0, v490, (HMODULE *)&qword_18002F860[3 * v494]) )
                                                break;
                                              v496 = v1158;
                                              v497 = &v490[v495];
                                              v498 = qword_18002F860[v1158];
                                              if ( *(_WORD *)v498 == 23117
                                                && (v500 = *(int *)(v498 + 60), (unsigned int)v500 < 0x10000000)
                                                && (v501 = qword_18002F860[v1158] + v500, v501 >= qword_18002F860[v1158])
                                                && *(_DWORD *)v501 == 17744 )
                                              {
                                                if ( ((*(_WORD *)(v501 + 24) - 267) & 0xFEFF) != 0 )
                                                {
                                                  v499 = -1073741811;
                                                }
                                                else
                                                {
                                                  v499 = 0;
                                                  *(__int64 *)((char *)&qword_18002F860[v1158 + 1] + 4) = *(_QWORD *)(v501 + 136);
                                                  LODWORD(qword_18002F860[v496 + 1]) = *(_DWORD *)(v501 + 80);
                                                }
                                              }
                                              else
                                              {
                                                v499 = -1073741701;
                                              }
                                              v502 = *(_DWORD *)(v497 + 1);
                                              v503 = 0;
                                              v490 = v497 + 3;
                                              LODWORD(v1146) = v502;
                                              LODWORD(v1148) = 0;
                                              if ( v502 )
                                              {
                                                do
                                                {
                                                  v504 = -1;
                                                  do
                                                    ++v504;
                                                  while ( *((_BYTE *)v490 + v504) );
                                                  lpModuleName = (LPCWSTR)v504;
                                                  if ( v499 >= 0 )
                                                  {
                                                    v505 = GetProcAddress((HMODULE)qword_18002F860[v496], (LPCSTR)v490);
                                                    if ( !v505 )
                                                      goto LABEL_636;
                                                    v496 = v1158;
                                                    off_18002F000[(unsigned int)Size] = v505;
                                                    v504 = (__int64)lpModuleName;
                                                    v503 = v1148;
                                                  }
                                                  v490 = (WCHAR *)((char *)v490 + v504 + 1);
                                                  LODWORD(Size) = Size + 1;
                                                  LODWORD(v1148) = ++v503;
                                                }
                                                while ( v503 < (unsigned int)v1146 );
                                              }
                                              v494 = (unsigned int)((_DWORD)v1149 + 1);
                                              LODWORD(v1149) = (_DWORD)v1149 + 1;
                                              if ( !*(_BYTE *)v490 )
                                                goto LABEL_636;
                                            }
                                            v499 = -1073741702;
LABEL_636:
                                            v490 = (WCHAR *)v1155;
                                            if ( !v1155 )
                                              goto LABEL_640;
                                          }
                                          else
                                          {
                                            v499 = 0;
                                          }
                                          v506 = GetProcessHeap();
                                          HeapFree(v506, 0, v490);
LABEL_640:
                                          v392 = 0;
                                          if ( v499 < 0 )
                                          {
LABEL_608:
                                            for ( n = 0; n != 4; ++n )
                                            {
                                              v493 = (HMODULE)qword_18002F860[3 * n];
                                              if ( v493 )
                                                FreeLibrary(v493);
                                            }
                                            memset_0(qword_18002F860, 0, sizeof(qword_18002F860));
                                            memcpy_0(off_18002F000, off_180028410, 0x170u);
LABEL_643:
                                            _InterlockedExchange(&dword_18002F8EC, 0);
                                            memset_0(&v1190, 0, 0x70u);
                                            LOWORD(v1134) = (v394 >> 4) & 0xF;
                                            WORD1(v1134) = (v394 >> 8) & 0xF;
                                            WORD2(v1134) = (v394 >> 12) & 0xF;
                                            v1165 = 0;
                                            v1137 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))off_18002F0F8[0])(
                                                      0,
                                                      0,
                                                      1027);
                                            LODWORD(v1154) = 0xFFFFFF;
                                            if ( !v1137 )
                                            {
                                              v507 = GetLastError();
                                              v508 = v507;
                                              if ( v507 > 0 )
                                                v508 = (unsigned __int16)v507 | 0x80070000;
                                              if ( v508 >= 0 )
                                                v508 = -2147467259;
LABEL_849:
                                              while ( _InterlockedCompareExchange(&dword_18002F8EC, 1, 0) )
                                                ;
                                              v626 = dword_18002F8E8;
                                              if ( dword_18002F8E8 > 0 )
                                              {
                                                --dword_18002F8E8;
                                                if ( v626 == 1 )
                                                {
                                                  do
                                                  {
                                                    v627 = (HMODULE)qword_18002F860[3 * v392];
                                                    if ( v627 )
                                                      FreeLibrary(v627);
                                                    ++v392;
                                                  }
                                                  while ( v392 != 4 );
                                                  memset_0(qword_18002F860, 0, sizeof(qword_18002F860));
                                                  memcpy_0(off_18002F000, off_180028410, 0x170u);
                                                }
                                              }
                                              _InterlockedExchange(&dword_18002F8EC, 0);
                                              SP<unsigned short *,SP_MEM<unsigned short *>>::Reset(&v1139);
                                              if ( v508 < 0 )
                                              {
LABEL_1070:
                                                v777 = v1192;
                                                if ( v1192 )
                                                {
                                                  v778 = -1;
                                                  do
                                                    ++v778;
                                                  while ( *((_WORD *)v1192 + v778) );
                                                  for ( ii = 2 * v778 + 2; ii; --ii )
                                                    *v777++ = 0;
                                                  MemoryFree(v1192);
                                                  v1192 = 0;
                                                }
                                                v780 = v1193;
                                                if ( v1193 )
                                                {
                                                  v781 = -1;
                                                  do
                                                    ++v781;
                                                  while ( *((_WORD *)v1193 + v781) );
                                                  for ( jj = 2 * v781 + 2; jj; --jj )
                                                    *v780++ = 0;
                                                  MemoryFree(v1193);
                                                  v1193 = 0;
                                                }
                                                v783 = v1194;
                                                if ( v1194 )
                                                {
                                                  v784 = -1;
                                                  do
                                                    ++v784;
                                                  while ( *((_WORD *)v1194 + v784) );
                                                  v785 = 2 * v784 + 2;
                                                  if ( v785 )
                                                  {
                                                    do
                                                    {
                                                      *v783++ = 0;
                                                      --v785;
                                                    }
                                                    while ( v785 );
                                                    v783 = v1194;
                                                  }
                                                  MemoryFree(v783);
                                                  v1194 = 0;
                                                }
                                                if ( v1195 )
                                                {
                                                  off_18002F038[0]();
                                                  v1195 = 0;
                                                }
                                                if ( v1196 )
                                                {
                                                  off_18002F038[0]();
                                                  v1196 = 0;
                                                }
                                                if ( v1197 )
                                                {
                                                  off_18002F038[0]();
                                                  v1197 = 0;
                                                }
                                                while ( _InterlockedCompareExchange(&dword_18002F8EC, 1, 0) )
                                                  ;
                                                v786 = dword_18002F8E8;
                                                if ( dword_18002F8E8 > 0 )
                                                {
                                                  --dword_18002F8E8;
                                                  if ( v786 == 1 )
                                                  {
                                                    for ( kk = 0; kk != 4; ++kk )
                                                    {
                                                      v788 = (HMODULE)qword_18002F860[3 * kk];
                                                      if ( v788 )
                                                        FreeLibrary(v788);
                                                    }
                                                    memset_0(qword_18002F860, 0, sizeof(qword_18002F860));
                                                    memcpy_0(off_18002F000, off_180028410, 0x170u);
                                                  }
                                                }
                                                _InterlockedExchange(&dword_18002F8EC, 0);
                                                v789 = qword_18002F840;
                                                LODWORD(v1139) = dword_18002F850;
                                                v790 = off_18002F098[0]();
                                                v1276 = 0;
                                                v791 = v790 - v789;
                                                v1137 = (unsigned int)(v790 - v789);
                                                v1277 = 0;
                                                v1280 = 0;
                                                v1278 = 0;
                                                v1279 = 0;
                                                while ( _InterlockedCompareExchange(&dword_18002F8EC, 1, 0) )
                                                  ;
                                                v792 = dword_18002F8E8;
                                                if ( dword_18002F8E8 )
                                                  goto LABEL_1148;
                                                v793 = (const WCHAR *)MemoryAlloc(0x338u);
                                                v1164 = v793;
                                                if ( !v793 )
                                                  goto LABEL_1113;
                                                v794 = (WCHAR *)v793;
                                                v795 = qword_18002B6E0;
                                                v796 = 103;
                                                v797 = 0;
                                                v798 = -1;
                                                v799 = 0;
                                                v800 = 0;
                                                do
                                                {
                                                  v801 = *((unsigned __int8 *)v795 + 1);
                                                  v802 = *(unsigned __int8 *)v795;
                                                  v803 = *((unsigned __int8 *)v795++ + 4);
                                                  v804 = *((unsigned __int8 *)v795 - 5)
                                                       | ((*((unsigned __int8 *)v795 - 6) | ((v801 | (v802 << 8)) << 8)) << 8);
                                                  v805 = v800 ^ v804;
                                                  v806 = *((unsigned __int8 *)v795 - 1)
                                                       | ((*((unsigned __int8 *)v795 - 2)
                                                         | ((*((unsigned __int8 *)v795 - 3) | (v803 << 8)) << 8)) << 8);
                                                  v807 = v800 ^ v804 ^ v799 ^ v806 ^ 0xAC987321;
                                                  v808 = v805
                                                       ^ (__ROR4__(v807, 22) + 4991 * __ROR4__(v807 + 1419157410, 27));
                                                  v809 = v807
                                                       ^ (43881 * __ROR4__(v808 + 133239679, 9) - __ROR4__(v808, 30));
                                                  v810 = v808 ^ (24670 * v809 - (v809 >> 13) - 123127970);
                                                  v811 = v809
                                                       ^ (2033 * __ROR4__(v810 ^ 0xAB69, 26) - __ROR4__(v810, 30));
                                                  v812 = v810 ^ (133239679 - (v811 ^ 0xAB69605E));
                                                  v813 = v811 ^ (43881 * (v812 ^ 0x137F)) ^ __ROR4__(v812, 6);
                                                  v814 = v812
                                                       ^ (__ROR4__(v813, 30) + 24670 * __ROR4__(v813 + 133239679, 15));
                                                  v815 = v813
                                                       ^ (2033 * __ROR4__(v814 + 1419157410, 14) - __ROR4__(v814, 24));
                                                  v816 = v814
                                                       ^ __ROR4__(v815, 10)
                                                       ^ (4991 * __ROR4__(v815 ^ 0xAB69605E, 12));
                                                  v817 = v815 ^ (v816 >> 10) ^ (43881 * (v816 ^ 0x7F1));
                                                  v818 = v816 ^ (2033 * (__ROR4__(~v817, 5) + 24670));
                                                  v819 = v818
                                                       ^ (((v817 ^ (v818 - 2033) ^ 0xAB69605E) >> 2)
                                                        + 4991 * __ROR4__(v817 ^ (v818 - 2033) ^ 0xAB6967AF, 30));
                                                  v820 = v817
                                                       ^ (v818 - 2033)
                                                       ^ 0xAB69605E
                                                       ^ (__ROR4__(v819, 25) + 43881 * __ROR4__(v819 - 133239679, 6));
                                                  v821 = v819 ^ (24670 * (v820 ^ 0x137F) + __ROR4__(v820, 9));
                                                  v822 = v820
                                                       ^ (__ROR4__(v821, 25) + 2033 * __ROR4__(v821 ^ 0xAB69, 27));
                                                  v823 = v821 ^ v822 ^ 0xAC987321;
                                                  v824 = v822 ^ (4991 * __ROR4__(v823, 3) - 219010071);
                                                  v825 = v823
                                                       ^ (24670 * __ROR4__(v824 - 133239679, 1) - __ROR4__(v824, 6));
                                                  v826 = v824
                                                       ^ (__ROR4__(v825, 18) + 2033 * __ROR4__(v825 - 1419157410, 29));
                                                  v827 = v825
                                                       ^ (4991 * __ROR4__(v826 - 1419157410, 17) - __ROR4__(v826, 14));
                                                  v828 = v826 ^ (v827 >> 3) ^ (43881 * (v827 ^ 0x605E));
                                                  v829 = __ROR4__(v828, 30);
                                                  v799 = v798 ^ v828;
                                                  v798 = v806;
                                                  v800 = v797
                                                       ^ v827
                                                       ^ v829
                                                       ^ (24670
                                                        * __ROR4__(
                                                            v826 ^ (v827 >> 3) ^ (43881 * (v827 ^ 0x605E)) ^ 0x7F1137F,
                                                            28));
                                                  v797 = v804;
                                                  *((_BYTE *)v794 + 3) = v800;
                                                  *((_BYTE *)v794 + 7) = v799;
                                                  *((_BYTE *)v794 + 2) = __ROR4__(v800, 8);
                                                  *((_BYTE *)v794 + 6) = __ROR4__(v799, 8);
                                                  *((_BYTE *)v794 + 1) = __ROR4__(v800, 16);
                                                  *((_BYTE *)v794 + 5) = __ROR4__(v799, 16);
                                                  *(_BYTE *)v794 = __ROR4__(v800, 24);
                                                  *((_BYTE *)v794 + 4) = __ROR4__(v799, 24);
                                                  v794 += 4;
                                                  --v796;
                                                }
                                                while ( v796 );
                                                v90 = Src;
                                                v830 = (WCHAR *)v1164;
                                                v831 = 0;
                                                v832 = 0;
                                                do
                                                  v832 ^= *((_BYTE *)v1164 + v831++);
                                                while ( v831 < 0x338 );
                                                if ( v832 != 64 )
                                                {
                                                  MemoryFree((void *)v1164);
                                                  v791 = v1137;
                                                  goto LABEL_1113;
                                                }
                                                LODWORD(v1148) = 0;
                                                LODWORD(v1157) = 0;
                                                v835 = 0;
                                                *((_BYTE *)v1164 + 823) = 0;
                                                memset_0(qword_18002F860, 0, sizeof(qword_18002F860));
                                                if ( *(_BYTE *)v830 )
                                                {
                                                  v1155 = (SIZE_T)v830;
                                                  while ( 1 )
                                                  {
                                                    v836 = -1;
                                                    do
                                                      ++v836;
                                                    while ( v830[v836] );
                                                    v837 = 3LL * v835;
                                                    v838 = (HMODULE *)&qword_18002F860[3 * v835];
                                                    pcchLength = v837;
                                                    if ( !GetModuleHandleExW(0, v830, v838) )
                                                      break;
                                                    v839 = &v830[v836];
                                                    if ( *(_WORD *)*v838 == 23117
                                                      && (v842 = *((int *)*v838 + 15), (unsigned int)v842 < 0x10000000)
                                                      && (v843 = (char *)*v838 + v842, v843 >= (char *)*v838)
                                                      && *(_DWORD *)v843 == 17744 )
                                                    {
                                                      v840 = pcchLength;
                                                      if ( ((*((_WORD *)v843 + 12) - 267) & 0xFEFF) != 0 )
                                                      {
                                                        v841 = -1073741811;
                                                      }
                                                      else
                                                      {
                                                        v841 = 0;
                                                        *(__int64 *)((char *)&qword_18002F860[pcchLength + 1] + 4) = *((_QWORD *)v843 + 17);
                                                        LODWORD(qword_18002F860[v840 + 1]) = *((_DWORD *)v843 + 20);
                                                      }
                                                    }
                                                    else
                                                    {
                                                      v840 = pcchLength;
                                                      v841 = -1073741701;
                                                    }
                                                    v844 = *(_DWORD *)(v839 + 1);
                                                    v845 = 0;
                                                    v830 = v839 + 3;
                                                    LODWORD(v1134) = v844;
                                                    for ( LODWORD(v1146) = 0; v845 < v844; LODWORD(v1146) = v845 )
                                                    {
                                                      v846 = -1;
                                                      do
                                                        ++v846;
                                                      while ( *((_BYTE *)v830 + v846) );
                                                      if ( v841 < 0 )
                                                      {
                                                        v848 = v1148;
                                                      }
                                                      else
                                                      {
                                                        v847 = GetProcAddress(
                                                                 (HMODULE)qword_18002F860[v840],
                                                                 (LPCSTR)v830);
                                                        if ( !v847 )
                                                          goto LABEL_1142;
                                                        v848 = v1148;
                                                        v844 = (unsigned int)v1134;
                                                        off_18002F000[(unsigned int)v1148] = v847;
                                                        v845 = v1146;
                                                      }
                                                      LODWORD(v1148) = v848 + 1;
                                                      v840 = pcchLength;
                                                      ++v845;
                                                      v830 = (WCHAR *)((char *)v830 + v846 + 1);
                                                    }
                                                    v835 = v1157 + 1;
                                                    LODWORD(v1157) = v1157 + 1;
                                                    if ( !*(_BYTE *)v830 )
                                                      goto LABEL_1142;
                                                  }
                                                  v841 = -1073741702;
LABEL_1142:
                                                  v830 = (WCHAR *)v1155;
                                                  if ( !v1155 )
                                                    goto LABEL_1146;
                                                }
                                                else
                                                {
                                                  v841 = 0;
                                                }
                                                v849 = GetProcessHeap();
                                                HeapFree(v849, 0, v830);
LABEL_1146:
                                                v791 = v1137;
                                                if ( v841 < 0 )
                                                {
LABEL_1113:
                                                  for ( mm = 0; mm != 4; ++mm )
                                                  {
                                                    v834 = (HMODULE)qword_18002F860[3 * mm];
                                                    if ( v834 )
                                                      FreeLibrary(v834);
                                                  }
                                                  memset_0(qword_18002F860, 0, sizeof(qword_18002F860));
                                                  memcpy_0(off_18002F000, off_180028410, 0x170u);
                                                  goto LABEL_1149;
                                                }
                                                v792 = dword_18002F8E8;
LABEL_1148:
                                                dword_18002F8E8 = v792 + 1;
LABEL_1149:
                                                _InterlockedExchange(&dword_18002F8EC, 0);
                                                LODWORD(v1280) = (_DWORD)v1139;
                                                LODWORD(v1277) = v791;
                                                v1276 = 1;
                                                LODWORD(v1278) = -1721306479;
                                                DWORD2(v1277) = 1;
                                                LODWORD(v1279) = 1;
                                                DWORD2(v1278) = 1;
                                                DWORD2(v1279) = 1;
                                                ((void (__fastcall *)(_QWORD, __int64, __int64, int *))qword_18002F0D0)(
                                                  0,
                                                  8225,
                                                  4,
                                                  &v1276);
                                                while ( _InterlockedCompareExchange(&dword_18002F8EC, 1, 0) )
                                                  ;
                                                v850 = dword_18002F8E8;
                                                if ( dword_18002F8E8 > 0 )
                                                {
                                                  --dword_18002F8E8;
                                                  if ( v850 == 1 )
                                                  {
                                                    for ( nn = 0; nn != 4; ++nn )
                                                    {
                                                      v852 = (HMODULE)qword_18002F860[3 * nn];
                                                      if ( v852 )
                                                        FreeLibrary(v852);
                                                    }
                                                    memset_0(qword_18002F860, 0, sizeof(qword_18002F860));
                                                    memcpy_0(off_18002F000, off_180028410, 0x170u);
                                                  }
                                                }
                                                _InterlockedExchange(&dword_18002F8EC, 0);
                                                ((void (__fastcall *)(_QWORD, LPVOID))off_18002F160[0])(0, v1151);
                                                goto LABEL_1159;
                                              }
                                              v628 = v1165;
                                              v1153 = 0;
                                              v1158 = v1165;
                                              v1211 = 0;
                                              memset_0(v1212, 0, 0x64u);
                                              v629 = ((__int64 (__fastcall *)(LPVOID, __int64))off_18002F050[0])(
                                                       v1151,
                                                       7);
                                              if ( v629
                                                && ((unsigned int (__fastcall *)(__int64, __int64, int *))off_18002F068[0])(
                                                     v629,
                                                     104,
                                                     &v1211) )
                                              {
                                                if ( v1213 != 32
                                                  || !v1214
                                                  || v1212[0] <= 0
                                                  || (v630 = 1, LODWORD(Size) = 1, v1212[1] <= 0) )
                                                {
                                                  v630 = 0;
                                                  LODWORD(Size) = 0;
                                                }
                                                v631 = v394 & 0xF;
                                                v632 = v631;
                                                if ( v630 )
                                                {
LABEL_868:
                                                  ((void (__fastcall *)(int *, _QWORD, _QWORD))off_18002F150)(
                                                    &v1199,
                                                    v628,
                                                    HIDWORD(v1158));
                                                  ((void (__fastcall *)(int *, _QWORD, _QWORD))off_18002F150)(
                                                    &v1203,
                                                    v628,
                                                    HIDWORD(v1158));
                                                  if ( v631 == 1 )
                                                    v1153 = (_OWORD *)((__int64 (__fastcall *)(_QWORD))off_18002F028[0])(v1191 == 0 ? 0xB26720 : 0);
LABEL_870:
                                                  v633 = v1151;
                                                  LODWORD(v1134) = ((__int64 (__fastcall *)(LPVOID, __int64))off_18002F080[0])(
                                                                     v1151,
                                                                     1);
                                                  v634 = 2064;
                                                  if ( v1190 )
                                                    v634 = 133138;
                                                  v1125 = v634;
                                                  if ( (_DWORD)Size )
                                                  {
                                                    v1215 = 0;
                                                    memset_0(v1216, 0, 0x64u);
                                                    v1230 = 0;
                                                    memset_0(v1231, 0, 0x64u);
                                                    v1137 = (SIZE_T)v1192;
                                                    memset(v1251, 0, 28);
                                                    v1250 = 0;
                                                    v1242 = 0;
                                                    if ( !v1192 )
                                                      goto LABEL_876;
                                                    LODWORD(v1146) = v1191;
                                                    lpModuleName = v1195;
                                                    v635 = ((__int64 (__fastcall *)(LPVOID, __int64))off_18002F050[0])(
                                                             v633,
                                                             7);
                                                    if ( v635 )
                                                    {
                                                      if ( ((unsigned int (__fastcall *)(__int64, __int64, int *))off_18002F068[0])(
                                                             v635,
                                                             104,
                                                             &v1215) )
                                                      {
                                                        v1155 = v1217;
                                                        LODWORD(v1148) = v1216[0];
                                                        LODWORD(v1159) = v1216[1];
                                                      }
                                                      else
                                                      {
                                                        v1155 = 0;
                                                        LODWORD(v1159) = 0;
                                                        LODWORD(v1148) = 0;
                                                      }
                                                      pcchLength = ((__int64 (__fastcall *)(LPVOID))off_18002F010[0])(v633);
                                                      v636 = pcchLength;
                                                      if ( pcchLength )
                                                      {
                                                        DWORD1(v1250) = v1201 - v1199;
                                                        DWORD2(v1250) = v1200 - v1202;
                                                        v1181 = 0;
                                                        memset(v1251, 0, 28);
                                                        LODWORD(v1250) = 40;
                                                        HIDWORD(v1250) = 2097153;
                                                        v637 = ((__int64 (__fastcall *)(size_t, __int128 *, _QWORD, __int64 *, _QWORD, _DWORD))off_18002F018[0])(
                                                                 pcchLength,
                                                                 &v1250,
                                                                 0,
                                                                 &v1181,
                                                                 0,
                                                                 0);
                                                        v1135 = v637;
                                                        if ( v637 )
                                                        {
                                                          v641 = ((__int64 (__fastcall *)(SIZE_T, __int64, int *))off_18002F068[0])(
                                                                   v637,
                                                                   104,
                                                                   &v1230);
                                                          LODWORD(v1143) = 0;
                                                          if ( v641 )
                                                            v1158 = v1232;
                                                          else
                                                            v1158 = 0;
                                                          DWORD2(v1242) = v1201 - v1199;
                                                          HIDWORD(v1242) = v1202 - v1200;
                                                          ((void (__fastcall *)(size_t, SIZE_T))off_18002F078[0])(
                                                            v636,
                                                            v1135);
                                                          ((void (__fastcall *)(size_t, __int64))off_18002F080[0])(
                                                            v636,
                                                            1);
                                                          v642 = (void *)((__int64 (__fastcall *)(size_t, LPCWSTR))off_18002F078[0])(
                                                                           v636,
                                                                           lpModuleName);
                                                          v643 = off_18002F0E8[0];
                                                          v1139 = v642;
                                                          v644 = ((__int64 (__fastcall *)(_QWORD))off_18002F070[0])(0);
                                                          ((void (__fastcall *)(size_t, __int128 *, __int64))v643)(
                                                            pcchLength,
                                                            &v1242,
                                                            v644);
                                                          ((void (__fastcall *)(size_t, SIZE_T, __int64, __int128 *, int, _QWORD))off_18002F0D8[0])(
                                                            pcchLength,
                                                            v1137,
                                                            0xFFFFFFFFLL,
                                                            &v1242,
                                                            v1125,
                                                            0);
                                                          v645 = 0;
                                                          if ( v631 == 1 )
                                                          {
                                                            if ( (_DWORD)v1146 )
                                                            {
                                                              v646 = ((__int64 (__fastcall *)(__int64))off_18002F118[0])(8);
                                                              v645 = 0;
                                                            }
                                                            else
                                                            {
                                                              v646 = 0xFFFFFF;
                                                            }
                                                          }
                                                          else
                                                          {
                                                            v646 = -5723992;
                                                          }
                                                          v647 = 0;
                                                          v648 = -v1199;
                                                          LODWORD(Size) = v646;
                                                          if ( v1199 >= 0 )
                                                          {
                                                            v647 = v1199;
                                                            v648 = 0;
                                                          }
                                                          v649 = -v1200;
                                                          if ( v1200 >= 0 )
                                                          {
                                                            v649 = 0;
                                                            v645 = v1200;
                                                          }
                                                          v650 = DWORD2(v1242) - v648;
                                                          if ( DWORD2(v1242) - v648 >= (int)v1148 - v647 )
                                                            v650 = v1148 - v647;
                                                          LODWORD(v1146) = v650;
                                                          v651 = HIDWORD(v1242) - v649;
                                                          if ( HIDWORD(v1242) - v649 >= (int)v1159 - v645 )
                                                            v651 = (_DWORD)v1159 - v645;
                                                          LODWORD(v1142) = v651;
                                                          if ( v650 <= 0 || v651 <= 0 )
                                                          {
                                                            v640 = v1143;
                                                          }
                                                          else
                                                          {
                                                            v652 = Size;
                                                            v653 = v1146;
                                                            LODWORD(v1159) = 0;
                                                            v654 = (char *)(v1158
                                                                          + 4 * (v648 + (__int64)(v649 * DWORD2(v1242))));
                                                            v1137 = (SIZE_T)v654;
                                                            v655 = (char *)(v1155
                                                                          + 4 * (v647 + (__int64)(v645 * (int)v1148)));
                                                            LODWORD(v1157) = (unsigned int)Size >> 8;
                                                            LODWORD(v1136) = WORD1(Size);
                                                            lpModuleName = (LPCWSTR)(4LL * SDWORD2(v1242));
                                                            lpMem = (LPVOID)(4LL * (int)v1148);
                                                            v1155 = (SIZE_T)v655;
                                                            do
                                                            {
                                                              v656 = v1143;
                                                              v657 = 0;
                                                              v658 = v1157;
                                                              v659 = (unsigned __int8 *)v654;
                                                              v1158 = (SIZE_T)v654;
                                                              v660 = v655;
                                                              v661 = (char)v1136;
                                                              LODWORD(v1148) = 0;
                                                              do
                                                              {
                                                                v662 = ~(unsigned __int8)((*v659
                                                                                         + v659[2]
                                                                                         + 2 * (unsigned int)v659[1]) >> 2);
                                                                if ( (unsigned __int8)((*v659
                                                                                      + v659[2]
                                                                                      + 2 * (unsigned int)v659[1]) >> 2) != 0xFF )
                                                                {
                                                                  v663 = (unsigned __int8)v660[2];
                                                                  v664 = v662;
                                                                  v665 = (int)((unsigned __int64)(2155905153LL
                                                                                                * v662
                                                                                                * (v652 - v663)) >> 32) >> 7;
                                                                  v660[2] = v663 + (v665 < 0) + v665;
                                                                  v660[1] -= v664 * (v658 - v660[1]);
                                                                  *v660 -= v664 * (v661 - *v660);
                                                                  v666 = (unsigned __int8)v660[3];
                                                                  v667 = v664 * (255 - v666);
                                                                  v657 = v1148;
                                                                  LOBYTE(v665) = v666 + v667 / 255;
                                                                  v659 = (unsigned __int8 *)v1158;
                                                                  v660[3] = v665;
                                                                }
                                                                v659 += 4;
                                                                ++v657;
                                                                v660 += 4;
                                                                v1158 = (SIZE_T)v659;
                                                                LODWORD(v1148) = v657;
                                                              }
                                                              while ( v657 < v653 );
                                                              v654 = (char *)lpModuleName + v1137;
                                                              v655 = (char *)lpMem + v1155;
                                                              v1137 += (SIZE_T)lpModuleName;
                                                              v1155 += (SIZE_T)lpMem;
                                                              LODWORD(v1159) = (_DWORD)v1159 + 1;
                                                              LODWORD(v1143) = v656;
                                                            }
                                                            while ( (int)v1159 < (int)v1142 );
                                                            v90 = Src;
                                                            v640 = v656;
                                                          }
                                                          ((void (__fastcall *)(SIZE_T))off_18002F038[0])(v1135);
                                                          v639 = 0;
                                                          if ( v1139 )
                                                            ((void (__fastcall *)(size_t, LPVOID))off_18002F078[0])(
                                                              pcchLength,
                                                              v1139);
                                                        }
                                                        else
                                                        {
                                                          v638 = GetLastError();
                                                          v639 = 0;
                                                          v640 = v638;
                                                          if ( v638 > 0 )
                                                            v640 = (unsigned __int16)v638 | 0x80070000;
                                                          if ( v640 >= 0 )
                                                            v640 = -2147467259;
                                                        }
                                                        ((void (__fastcall *)(size_t))off_18002F030[0])(pcchLength);
                                                        if ( v640 < 0 )
                                                          goto LABEL_876;
                                                        v1218 = 0;
                                                        memset_0(v1219, 0, 0x64u);
                                                        v1227 = 0;
                                                        memset_0(v1228, 0, 0x64u);
                                                        v1137 = (SIZE_T)v1193;
                                                        memset(v1253, 0, 28);
                                                        v1252 = 0;
                                                        v1239 = 0;
                                                        if ( !v1193 )
                                                          goto LABEL_876;
                                                        v668 = v1151;
                                                        LODWORD(v1146) = v1191;
                                                        lpModuleName = v1196;
                                                        v669 = ((__int64 (__fastcall *)(LPVOID, __int64))off_18002F050[0])(
                                                                 v1151,
                                                                 7);
                                                        if ( v669 )
                                                        {
                                                          if ( ((unsigned int (__fastcall *)(__int64, __int64, int *))off_18002F068[0])(
                                                                 v669,
                                                                 104,
                                                                 &v1218) )
                                                          {
                                                            LODWORD(v1148) = v1219[0];
                                                            pcchLength = v1220;
                                                            v639 = 0;
                                                            LODWORD(v1159) = v1219[1];
                                                          }
                                                          else
                                                          {
                                                            pcchLength = 0;
                                                            LODWORD(v1159) = 0;
                                                            LODWORD(v1148) = 0;
                                                          }
                                                          v670 = ((__int64 (__fastcall *)(LPVOID))off_18002F010[0])(v668);
                                                          v1155 = v670;
                                                          v671 = v670;
                                                          if ( v670 )
                                                          {
                                                            DWORD1(v1252) = v1205 - v1203;
                                                            DWORD2(v1252) = v1204 - v1206;
                                                            v1182 = 0;
                                                            memset(v1253, 0, 28);
                                                            LODWORD(v1252) = 40;
                                                            HIDWORD(v1252) = 2097153;
                                                            v672 = ((__int64 (__fastcall *)(SIZE_T, __int128 *, _QWORD, __int64 *, _QWORD, _DWORD))off_18002F018[0])(
                                                                     v670,
                                                                     &v1252,
                                                                     0,
                                                                     &v1182,
                                                                     0,
                                                                     0);
                                                            v1135 = v672;
                                                            if ( v672 )
                                                            {
                                                              if ( ((unsigned int (__fastcall *)(SIZE_T, __int64, int *))off_18002F068[0])(
                                                                     v672,
                                                                     104,
                                                                     &v1227) )
                                                              {
                                                                v1158 = v1229;
                                                              }
                                                              else
                                                              {
                                                                v1158 = 0;
                                                              }
                                                              DWORD2(v1239) = v1205 - v1203;
                                                              HIDWORD(v1239) = v1206 - v1204;
                                                              ((void (__fastcall *)(SIZE_T, SIZE_T))off_18002F078[0])(
                                                                v671,
                                                                v1135);
                                                              ((void (__fastcall *)(SIZE_T, __int64))off_18002F080[0])(
                                                                v671,
                                                                1);
                                                              v674 = (void *)((__int64 (__fastcall *)(SIZE_T, LPCWSTR))off_18002F078[0])(
                                                                               v671,
                                                                               lpModuleName);
                                                              v675 = off_18002F0E8[0];
                                                              v1139 = v674;
                                                              v676 = ((__int64 (__fastcall *)(_QWORD))off_18002F070[0])(0);
                                                              ((void (__fastcall *)(SIZE_T, __int128 *, __int64))v675)(
                                                                v1155,
                                                                &v1239,
                                                                v676);
                                                              v671 = v1155;
                                                              ((void (__fastcall *)(SIZE_T, SIZE_T, __int64, __int128 *, int, _QWORD))off_18002F0D8[0])(
                                                                v1155,
                                                                v1137,
                                                                0xFFFFFFFFLL,
                                                                &v1239,
                                                                v1125,
                                                                0);
                                                              if ( v632 == 1 )
                                                              {
                                                                v677 = 0;
                                                                if ( (_DWORD)v1146 )
                                                                  LODWORD(v1154) = ((__int64 (__fastcall *)(__int64))off_18002F118[0])(8);
                                                              }
                                                              else
                                                              {
                                                                LODWORD(v1154) = -5723992;
                                                                v677 = 0;
                                                              }
                                                              v678 = 0;
                                                              v679 = -v1203;
                                                              if ( v1203 >= 0 )
                                                              {
                                                                v678 = v1203;
                                                                v679 = 0;
                                                              }
                                                              v680 = -v1204;
                                                              if ( v1204 >= 0 )
                                                              {
                                                                v680 = 0;
                                                                v677 = v1204;
                                                              }
                                                              v681 = DWORD2(v1239) - v679;
                                                              if ( DWORD2(v1239) - v679 >= (int)v1148 - v678 )
                                                                v681 = v1148 - v678;
                                                              LODWORD(v1146) = v681;
                                                              v682 = HIDWORD(v1239) - v680;
                                                              if ( HIDWORD(v1239) - v680 >= (int)v1159 - v677 )
                                                                v682 = (_DWORD)v1159 - v677;
                                                              LODWORD(v1142) = v682;
                                                              if ( v681 > 0 && v682 > 0 )
                                                              {
                                                                v683 = v1146;
                                                                LODWORD(v1159) = 0;
                                                                v684 = (char *)(v1158
                                                                              + 4
                                                                              * (v679 + (__int64)(v680 * DWORD2(v1239))));
                                                                v1137 = (SIZE_T)v684;
                                                                v685 = (char *)(pcchLength
                                                                              + 4
                                                                              * (v678 + (__int64)(v677 * (int)v1148)));
                                                                LODWORD(v1157) = (unsigned int)v1154 >> 8;
                                                                LODWORD(v1136) = WORD1(v1154);
                                                                lpModuleName = (LPCWSTR)(4LL * SDWORD2(v1239));
                                                                lpMem = (LPVOID)(4LL * (int)v1148);
                                                                pcchLength = (size_t)v685;
                                                                do
                                                                {
                                                                  v686 = v1157;
                                                                  v687 = 0;
                                                                  v688 = (char)v1136;
                                                                  v689 = (unsigned __int8 *)v684;
                                                                  v690 = v1154;
                                                                  v691 = v685;
                                                                  LODWORD(v1148) = 0;
                                                                  v1158 = (SIZE_T)v684;
                                                                  do
                                                                  {
                                                                    v692 = ~(unsigned __int8)((*v689
                                                                                             + v689[2]
                                                                                             + 2 * (unsigned int)v689[1]) >> 2);
                                                                    if ( (unsigned __int8)((*v689
                                                                                          + v689[2]
                                                                                          + 2 * (unsigned int)v689[1]) >> 2) != 0xFF )
                                                                    {
                                                                      v693 = (unsigned __int8)v691[2];
                                                                      v694 = v692;
                                                                      v695 = (int)((unsigned __int64)(2155905153LL * v692 * (v690 - v693)) >> 32) >> 7;
                                                                      v691[2] = v693 + (v695 < 0) + v695;
                                                                      v691[1] -= v694 * (v686 - v691[1]);
                                                                      *v691 -= v694 * (v688 - *v691);
                                                                      v696 = (unsigned __int8)v691[3];
                                                                      v697 = v694 * (255 - v696);
                                                                      v687 = v1148;
                                                                      LOBYTE(v695) = v696 + v697 / 255;
                                                                      v689 = (unsigned __int8 *)v1158;
                                                                      v691[3] = v695;
                                                                    }
                                                                    v689 += 4;
                                                                    ++v687;
                                                                    v691 += 4;
                                                                    v1158 = (SIZE_T)v689;
                                                                    LODWORD(v1148) = v687;
                                                                  }
                                                                  while ( v687 < v683 );
                                                                  v684 = (char *)lpModuleName + v1137;
                                                                  v685 = (char *)lpMem + pcchLength;
                                                                  v1137 += (SIZE_T)lpModuleName;
                                                                  pcchLength += (size_t)lpMem;
                                                                  LODWORD(v1159) = (_DWORD)v1159 + 1;
                                                                }
                                                                while ( (int)v1159 < (int)v1142 );
                                                                v90 = Src;
                                                                v671 = v1155;
                                                              }
                                                              ((void (__fastcall *)(SIZE_T))off_18002F038[0])(v1135);
                                                              if ( v1139 )
                                                                ((void (__fastcall *)(SIZE_T, LPVOID))off_18002F078[0])(
                                                                  v671,
                                                                  v1139);
                                                            }
                                                            else
                                                            {
                                                              v639 = GetLastError();
                                                              v673 = v639 < 0;
                                                              if ( v639 > 0 )
                                                              {
                                                                v639 = (unsigned __int16)v639 | 0x80070000;
                                                                v673 = v639 < 0;
                                                              }
                                                              if ( !v673 )
                                                                v639 = -2147467259;
                                                            }
                                                            ((void (__fastcall *)(SIZE_T))off_18002F030[0])(v671);
                                                            if ( v639 < 0 )
                                                              goto LABEL_876;
                                                            v698 = v1151;
                                                            v699 = 0;
                                                            v700 = 0;
LABEL_1068:
                                                            ((void (__fastcall *)(LPVOID, _QWORD))off_18002F080[0])(
                                                              v698,
                                                              (unsigned int)v1134);
                                                            if ( !v699 )
                                                            {
LABEL_981:
                                                              if ( !v700 )
                                                                goto LABEL_876;
                                                              goto LABEL_982;
                                                            }
LABEL_980:
                                                            ((void (__fastcall *)(SIZE_T))off_18002F038[0])(v699);
                                                            goto LABEL_981;
                                                          }
                                                        }
                                                      }
                                                    }
LABEL_875:
                                                    GetLastError();
                                                    goto LABEL_876;
                                                  }
                                                  if ( v1191 || (v701 = -64, v632 == 1) )
                                                    v701 = -1;
                                                  BYTE2(v1149) = v701;
                                                  LOWORD(v1149) = 0;
                                                  BYTE3(v1149) = 1;
                                                  v1135 = ((__int64 (__fastcall *)(LPVOID))off_18002F010[0])(v633);
                                                  if ( !v1135 )
                                                    goto LABEL_875;
                                                  v702 = v1199;
                                                  if ( v632 == 1 )
                                                  {
                                                    v703 = v1205 - v1203;
                                                    LODWORD(v1152) = 0;
                                                    if ( v1205 - v1203 <= v1201 - v1199 )
                                                      v703 = v1201 - v1199;
                                                    LODWORD(Size) = v703;
                                                    LODWORD(v1143) = v1206 - v1200;
                                                    if ( v1190 )
                                                    {
                                                      v702 = v703 + v1199 - v1201;
                                                      v704 = v703 + v1203 - v1205;
                                                    }
                                                    else
                                                    {
                                                      v702 = 0;
                                                      v704 = 0;
                                                    }
                                                    v705 = v702 + v1201 - v1199;
                                                    LODWORD(v1157) = v1202 - v1200;
                                                    LODWORD(v1148) = v1204 - v1200;
                                                    v706 = v1205 - v1203 + v704;
                                                    v707 = (int)v1152;
                                                    LODWORD(v1159) = v1206 - v1200;
                                                    LODWORD(v1138) = v704;
                                                  }
                                                  else
                                                  {
                                                    v703 = DWORD2(v1165);
                                                    v707 = v1200;
                                                    v705 = v1201;
                                                    v706 = v1205;
                                                    LODWORD(v1143) = HIDWORD(v1165);
                                                    LODWORD(v1157) = v1202;
                                                    LODWORD(v1138) = v1203;
                                                    LODWORD(v1148) = v1204;
                                                    LODWORD(v1159) = v1206;
                                                    LODWORD(Size) = DWORD2(v1165);
                                                    LODWORD(v1152) = v1200;
                                                  }
                                                  v1246[2] = -(int)v1143;
                                                  LODWORD(v1150) = v706;
                                                  v1183 = 0;
                                                  v1246[1] = v703;
                                                  LODWORD(v1144) = v705;
                                                  LODWORD(v1142) = v702;
                                                  memset(&v1246[4], 0, 28);
                                                  v1246[0] = 40;
                                                  v1246[3] = 2097153;
                                                  v708 = ((__int64 (__fastcall *)(SIZE_T, _DWORD *, _QWORD, __int64 *, _QWORD, _DWORD))off_18002F018[0])(
                                                           v1135,
                                                           v1246,
                                                           0,
                                                           &v1183,
                                                           0,
                                                           0);
                                                  v1137 = v708;
                                                  if ( !v708 )
                                                  {
                                                    GetLastError();
                                                    v700 = v1135;
LABEL_982:
                                                    ((void (__fastcall *)(SIZE_T))off_18002F030[0])(v700);
LABEL_876:
                                                    if ( v1153 )
                                                      ((void (__fastcall *)(_OWORD *))off_18002F038[0])(v1153);
                                                    goto LABEL_1070;
                                                  }
                                                  ((void (__fastcall *)(SIZE_T, SIZE_T))off_18002F078[0])(v1135, v708);
                                                  if ( v632 == 1 && v1153 )
                                                  {
                                                    v1243 = 0;
                                                    v1244 = Size;
                                                    v1245 = v1143;
                                                    ((void (__fastcall *)(SIZE_T, __int64 *))off_18002F0E8[0])(
                                                      v1135,
                                                      &v1243);
                                                  }
                                                  v1221 = 0;
                                                  memset_0(v1222, 0, 0x64u);
                                                  v1233 = 0;
                                                  memset_0(v1234, 0, 0x64u);
                                                  v1166 = (SIZE_T)v1192;
                                                  memset(v1255, 0, 28);
                                                  v1254 = 0;
                                                  v1240 = 0;
                                                  if ( v1192 )
                                                  {
                                                    LODWORD(v1139) = v1191;
                                                    lpMem = v1195;
                                                    v709 = ((__int64 (__fastcall *)(SIZE_T, __int64))off_18002F050[0])(
                                                             v1135,
                                                             7);
                                                    if ( v709
                                                      && (!((unsigned int (__fastcall *)(__int64, __int64, int *))off_18002F068[0])(
                                                             v709,
                                                             104,
                                                             &v1221)
                                                        ? (v1155 = 0, LODWORD(v1146) = 0, LODWORD(v1136) = 0)
                                                        : (v1155 = v1223,
                                                           LODWORD(v1136) = v1222[0],
                                                           LODWORD(v1146) = v1222[1]),
                                                          v710 = ((__int64 (__fastcall *)(SIZE_T))off_18002F010[0])(v1135),
                                                          (pcchLength = v710) != 0) )
                                                    {
                                                      v1185 = 0;
                                                      v711 = (_DWORD)v1144 - v702;
                                                      LODWORD(v1254) = 40;
                                                      v712 = v1157;
                                                      DWORD2(v1254) = v707 - v1157;
                                                      v713 = 0;
                                                      LODWORD(v1144) = v711;
                                                      DWORD1(v1254) = v711;
                                                      memset(v1255, 0, 28);
                                                      HIDWORD(v1254) = 2097153;
                                                      v714 = (const WCHAR *)((__int64 (__fastcall *)(size_t, __int128 *, _QWORD, __int64 *, _QWORD, _DWORD))off_18002F018[0])(
                                                                              v710,
                                                                              &v1254,
                                                                              0,
                                                                              &v1185,
                                                                              0,
                                                                              0);
                                                      lpModuleName = v714;
                                                      if ( v714 )
                                                      {
                                                        if ( ((unsigned int (__fastcall *)(const WCHAR *, __int64, int *))off_18002F068[0])(
                                                               v714,
                                                               104,
                                                               &v1233) )
                                                        {
                                                          v1158 = v1235;
                                                        }
                                                        else
                                                        {
                                                          v1158 = 0;
                                                        }
                                                        HIDWORD(v1240) = v712 - (_DWORD)v1152;
                                                        v716 = pcchLength;
                                                        DWORD2(v1240) = (_DWORD)v1144;
                                                        ((void (__fastcall *)(size_t, LPCWSTR))off_18002F078[0])(
                                                          pcchLength,
                                                          lpModuleName);
                                                        ((void (__fastcall *)(size_t, __int64))off_18002F080[0])(
                                                          v716,
                                                          1);
                                                        v717 = (const WCHAR *)((__int64 (__fastcall *)(size_t, LPVOID))off_18002F078[0])(
                                                                                v716,
                                                                                lpMem);
                                                        v718 = off_18002F0E8[0];
                                                        v1164 = v717;
                                                        v719 = ((__int64 (__fastcall *)(_QWORD))off_18002F070[0])(0);
                                                        ((void (__fastcall *)(size_t, __int128 *, __int64))v718)(
                                                          pcchLength,
                                                          &v1240,
                                                          v719);
                                                        v720 = pcchLength;
                                                        ((void (__fastcall *)(size_t, SIZE_T, __int64, __int128 *, int, _QWORD))off_18002F0D8[0])(
                                                          pcchLength,
                                                          v1166,
                                                          0xFFFFFFFFLL,
                                                          &v1240,
                                                          v1125,
                                                          0);
                                                        if ( v632 == 1 )
                                                        {
                                                          if ( (_DWORD)v1139 )
                                                            v721 = ((__int64 (__fastcall *)(__int64))off_18002F118[0])(8);
                                                          else
                                                            v721 = 0xFFFFFF;
                                                        }
                                                        else
                                                        {
                                                          v721 = -5723992;
                                                        }
                                                        v722 = (int)v1152;
                                                        v723 = -(int)v1142;
                                                        LODWORD(v1144) = v721;
                                                        v724 = 0;
                                                        if ( (int)v1142 >= 0 )
                                                        {
                                                          v723 = 0;
                                                          v724 = (int)v1142;
                                                        }
                                                        if ( (int)v1152 >= 0 )
                                                        {
                                                          v725 = 0;
                                                        }
                                                        else
                                                        {
                                                          v725 = -(int)v1152;
                                                          v722 = 0;
                                                        }
                                                        v726 = DWORD2(v1240) - v723;
                                                        if ( DWORD2(v1240) - v723 >= (int)v1136 - v724 )
                                                          v726 = (_DWORD)v1136 - v724;
                                                        LODWORD(v1139) = v726;
                                                        v727 = HIDWORD(v1240) - v725;
                                                        if ( HIDWORD(v1240) - v725 >= (int)v1146 - v722 )
                                                          v727 = v1146 - v722;
                                                        LODWORD(v1152) = v727;
                                                        if ( v726 > 0 && v727 > 0 )
                                                        {
                                                          v728 = (int)v1136;
                                                          v729 = (unsigned __int8)v1144;
                                                          v730 = (int)v1139;
                                                          LODWORD(v1157) = 0;
                                                          v731 = (char *)(v1158
                                                                        + 4 * (v723 + (__int64)(DWORD2(v1240) * v725)));
                                                          lpMem = v731;
                                                          v732 = (char *)(v1155
                                                                        + 4 * (v724 + (__int64)((int)v1136 * v722)));
                                                          LODWORD(v1136) = (unsigned int)v1144 >> 8;
                                                          LODWORD(v1142) = (unsigned int)v1144 >> 16;
                                                          v1166 = 4LL * SDWORD2(v1240);
                                                          v1144 = (LPVOID)(4 * v728);
                                                          v1155 = (SIZE_T)v732;
                                                          do
                                                          {
                                                            v733 = (char)v1136;
                                                            v734 = 0;
                                                            v735 = (unsigned __int8 *)v731;
                                                            v1158 = (SIZE_T)v731;
                                                            v736 = (char)v1142;
                                                            v737 = v732;
                                                            LODWORD(v1146) = 0;
                                                            do
                                                            {
                                                              v738 = ~(unsigned __int8)((*v735
                                                                                       + v735[2]
                                                                                       + 2 * (unsigned int)v735[1]) >> 2);
                                                              if ( (unsigned __int8)((*v735
                                                                                    + v735[2]
                                                                                    + 2 * (unsigned int)v735[1]) >> 2) != 0xFF )
                                                              {
                                                                v739 = (unsigned __int8)v737[2];
                                                                v740 = v738;
                                                                v741 = (int)((unsigned __int64)(2155905153LL
                                                                                              * v738
                                                                                              * (v729 - v739)) >> 32) >> 7;
                                                                v737[2] = v739 + (v741 < 0) + v741;
                                                                v737[1] -= v740 * (v733 - v737[1]);
                                                                *v737 -= v740 * (v736 - *v737);
                                                                v742 = (unsigned __int8)v737[3];
                                                                v743 = v740 * (255 - v742);
                                                                v734 = v1146;
                                                                LOBYTE(v741) = v742 + v743 / 255;
                                                                v735 = (unsigned __int8 *)v1158;
                                                                v737[3] = v741;
                                                              }
                                                              v735 += 4;
                                                              ++v734;
                                                              v737 += 4;
                                                              v1158 = (SIZE_T)v735;
                                                              LODWORD(v1146) = v734;
                                                            }
                                                            while ( v734 < v730 );
                                                            v731 = (char *)lpMem + v1166;
                                                            v732 = (char *)v1144 + v1155;
                                                            lpMem = (char *)lpMem + v1166;
                                                            v1155 += (SIZE_T)v1144;
                                                            LODWORD(v1157) = v1157 + 1;
                                                          }
                                                          while ( (int)v1157 < (int)v1152 );
                                                          v90 = Src;
                                                          v720 = pcchLength;
                                                        }
                                                        ((void (__fastcall *)(LPCWSTR))off_18002F038[0])(lpModuleName);
                                                        if ( v1164 )
                                                          ((void (__fastcall *)(size_t, LPCWSTR))off_18002F078[0])(
                                                            v720,
                                                            v1164);
                                                      }
                                                      else
                                                      {
                                                        v713 = GetLastError();
                                                        v715 = v713 < 0;
                                                        if ( v713 > 0 )
                                                        {
                                                          v713 = (unsigned __int16)v713 | 0x80070000;
                                                          v715 = v713 < 0;
                                                        }
                                                        if ( !v715 )
                                                          v713 = -2147467259;
                                                      }
                                                      ((void (__fastcall *)(size_t))off_18002F030[0])(pcchLength);
                                                      if ( v713 >= 0 )
                                                      {
                                                        v744 = 0;
                                                        v1224 = 0;
                                                        memset_0(v1225, 0, 0x64u);
                                                        v1236 = 0;
                                                        memset_0(v1237, 0, 0x64u);
                                                        v700 = v1135;
                                                        v1166 = (SIZE_T)v1193;
                                                        memset(v1257, 0, 28);
                                                        v1256 = 0;
                                                        v1241 = 0;
                                                        if ( !v1193 )
                                                          goto LABEL_979;
                                                        LODWORD(v1139) = v1191;
                                                        v1164 = v1196;
                                                        v745 = ((__int64 (__fastcall *)(SIZE_T, __int64))off_18002F050[0])(
                                                                 v1135,
                                                                 7);
                                                        if ( !v745
                                                          || (!((unsigned int (__fastcall *)(__int64, __int64, int *))off_18002F068[0])(
                                                                 v745,
                                                                 104,
                                                                 &v1224)
                                                            ? (v1158 = 0, LODWORD(v1146) = 0, LODWORD(v1136) = 0)
                                                            : (v1158 = v1226,
                                                               LODWORD(v1136) = v1225[0],
                                                               v744 = 0,
                                                               LODWORD(v1146) = v1225[1]),
                                                              (pcchLength = ((__int64 (__fastcall *)(SIZE_T))off_18002F010[0])(v700)) == 0) )
                                                        {
                                                          GetLastError();
                                                          goto LABEL_979;
                                                        }
                                                        v746 = v1148;
                                                        LODWORD(v1150) = (_DWORD)v1150 - (_DWORD)v1138;
                                                        DWORD1(v1256) = (_DWORD)v1150;
                                                        DWORD2(v1256) = v1148 - (_DWORD)v1159;
                                                        v1184 = 0;
                                                        memset(v1257, 0, 28);
                                                        LODWORD(v1256) = 40;
                                                        HIDWORD(v1256) = 2097153;
                                                        v747 = (void *)((__int64 (__fastcall *)(size_t, __int128 *, _QWORD, __int64 *, _QWORD, _DWORD))off_18002F018[0])(
                                                                         pcchLength,
                                                                         &v1256,
                                                                         0,
                                                                         &v1184,
                                                                         0,
                                                                         0);
                                                        lpMem = v747;
                                                        if ( v747 )
                                                        {
                                                          if ( ((unsigned int (__fastcall *)(void *, __int64, int *))off_18002F068[0])(
                                                                 v747,
                                                                 104,
                                                                 &v1236) )
                                                          {
                                                            lpModuleName = v1238;
                                                          }
                                                          else
                                                          {
                                                            lpModuleName = 0;
                                                          }
                                                          v750 = (_DWORD)v1159 - v746;
                                                          v751 = pcchLength;
                                                          *((_QWORD *)&v1241 + 1) = __PAIR64__(
                                                                                      v750,
                                                                                      (unsigned int)v1150);
                                                          ((void (__fastcall *)(size_t, LPVOID))off_18002F078[0])(
                                                            pcchLength,
                                                            lpMem);
                                                          ((void (__fastcall *)(size_t, __int64))off_18002F080[0])(
                                                            v751,
                                                            1);
                                                          v752 = (void *)((__int64 (__fastcall *)(size_t, LPCWSTR))off_18002F078[0])(
                                                                           v751,
                                                                           v1164);
                                                          v753 = off_18002F0E8[0];
                                                          v1144 = v752;
                                                          v754 = ((__int64 (__fastcall *)(_QWORD))off_18002F070[0])(0);
                                                          ((void (__fastcall *)(size_t, __int128 *, __int64))v753)(
                                                            pcchLength,
                                                            &v1241,
                                                            v754);
                                                          v749 = pcchLength;
                                                          ((void (__fastcall *)(size_t, SIZE_T, __int64, __int128 *, int, _QWORD))off_18002F0D8[0])(
                                                            pcchLength,
                                                            v1166,
                                                            0xFFFFFFFFLL,
                                                            &v1241,
                                                            v1125,
                                                            0);
                                                          if ( v632 == 1 )
                                                          {
                                                            if ( (_DWORD)v1139 )
                                                              LODWORD(v1154) = ((__int64 (__fastcall *)(__int64))off_18002F118[0])(8);
                                                          }
                                                          else
                                                          {
                                                            LODWORD(v1154) = -5723992;
                                                          }
                                                          v755 = -(int)v1138;
                                                          if ( (int)v1138 >= 0 )
                                                            v755 = 0;
                                                          v756 = v1148;
                                                          v757 = 0;
                                                          if ( (int)v1138 >= 0 )
                                                            v757 = (int)v1138;
                                                          if ( (v1148 & 0x80000000) == 0LL )
                                                          {
                                                            v758 = 0;
                                                          }
                                                          else
                                                          {
                                                            v758 = -(int)v1148;
                                                            v756 = 0;
                                                          }
                                                          v759 = DWORD2(v1241) - v755;
                                                          if ( DWORD2(v1241) - v755 >= (int)v1136 - v757 )
                                                            v759 = (_DWORD)v1136 - v757;
                                                          LODWORD(v1139) = v759;
                                                          v760 = HIDWORD(v1241) - v758;
                                                          if ( HIDWORD(v1241) - v758 >= (int)v1146 - v756 )
                                                            v760 = v1146 - v756;
                                                          LODWORD(v1142) = v760;
                                                          if ( v759 > 0 && v760 > 0 )
                                                          {
                                                            v761 = (int)v1139;
                                                            LODWORD(v1157) = 0;
                                                            v762 = &lpModuleName[2 * v755
                                                                               + 2 * (__int64)(DWORD2(v1241) * v758)];
                                                            v1155 = (SIZE_T)v762;
                                                            v763 = (_BYTE *)(v1158
                                                                           + 4 * (v757 + (__int64)((int)v1136 * v756)));
                                                            LODWORD(v1148) = (unsigned int)v1154 >> 8;
                                                            LODWORD(v1159) = WORD1(v1154);
                                                            v1164 = (LPCWSTR)(4LL * SDWORD2(v1241));
                                                            v1166 = 4LL * (int)v1136;
                                                            v1158 = (SIZE_T)v763;
                                                            do
                                                            {
                                                              v764 = v1148;
                                                              v765 = v762;
                                                              v766 = (char)v1159;
                                                              v767 = v763;
                                                              v768 = v1154;
                                                              lpModuleName = v762;
                                                              v769 = 0;
                                                              LODWORD(v1146) = 0;
                                                              do
                                                              {
                                                                v770 = ~(unsigned __int8)((*(unsigned __int8 *)v765
                                                                                         + *((unsigned __int8 *)v765 + 2)
                                                                                         + 2
                                                                                         * (unsigned int)*((unsigned __int8 *)v765 + 1)) >> 2);
                                                                if ( (unsigned __int8)((*(unsigned __int8 *)v765
                                                                                      + *((unsigned __int8 *)v765 + 2)
                                                                                      + 2
                                                                                      * (unsigned int)*((unsigned __int8 *)v765 + 1)) >> 2) != 0xFF )
                                                                {
                                                                  v771 = (unsigned __int8)v767[2];
                                                                  v772 = v770;
                                                                  v773 = (int)((unsigned __int64)(2155905153LL
                                                                                                * v770
                                                                                                * (v768 - v771)) >> 32) >> 7;
                                                                  v767[2] = v771 + (v773 < 0) + v773;
                                                                  v767[1] -= v772 * (v764 - v767[1]);
                                                                  *v767 -= v772 * (v766 - *v767);
                                                                  v774 = (unsigned __int8)v767[3];
                                                                  v775 = v772 * (255 - v774);
                                                                  v769 = v1146;
                                                                  LOBYTE(v773) = v774 + v775 / 255;
                                                                  v765 = lpModuleName;
                                                                  v767[3] = v773;
                                                                }
                                                                v765 += 2;
                                                                ++v769;
                                                                v767 += 4;
                                                                lpModuleName = v765;
                                                                LODWORD(v1146) = v769;
                                                              }
                                                              while ( v769 < v761 );
                                                              v762 = (LPCWSTR)((char *)v1164 + v1155);
                                                              v763 = (_BYTE *)(v1166 + v1158);
                                                              v1155 += (SIZE_T)v1164;
                                                              v1158 += v1166;
                                                              LODWORD(v1157) = v1157 + 1;
                                                            }
                                                            while ( (int)v1157 < (int)v1142 );
                                                            v90 = Src;
                                                            v749 = pcchLength;
                                                          }
                                                          ((void (__fastcall *)(LPVOID))off_18002F038[0])(lpMem);
                                                          if ( v1144 )
                                                            ((void (__fastcall *)(size_t, LPVOID))off_18002F078[0])(
                                                              v749,
                                                              v1144);
                                                        }
                                                        else
                                                        {
                                                          v744 = GetLastError();
                                                          v748 = v744 < 0;
                                                          if ( v744 > 0 )
                                                          {
                                                            v744 = (unsigned __int16)v744 | 0x80070000;
                                                            v748 = v744 < 0;
                                                          }
                                                          v749 = pcchLength;
                                                          if ( !v748 )
                                                            v744 = -2147467259;
                                                        }
                                                        ((void (__fastcall *)(size_t))off_18002F030[0])(v749);
                                                        if ( v744 >= 0 )
                                                        {
                                                          v700 = v1135;
                                                          v776 = v632 == 1;
                                                          v698 = v1151;
                                                          if ( v776 )
                                                            ((void (__fastcall *)(LPVOID, _QWORD, _QWORD, _QWORD, _DWORD, SIZE_T, _DWORD, _DWORD, int))off_18002F000[0])(
                                                              v1151,
                                                              (unsigned int)v1199,
                                                              (unsigned int)v1200,
                                                              (unsigned int)Size,
                                                              v1143,
                                                              v1135,
                                                              0,
                                                              0,
                                                              13369376);
                                                          else
                                                            ((void (__fastcall *)(LPVOID, _QWORD, _QWORD, _QWORD, _DWORD, SIZE_T, _DWORD, _DWORD, _DWORD, _DWORD, _DWORD))off_18002F040[0])(
                                                              v1151,
                                                              (unsigned int)v1165,
                                                              DWORD1(v1165),
                                                              (unsigned int)Size,
                                                              v1143,
                                                              v1135,
                                                              0,
                                                              0,
                                                              Size,
                                                              v1143,
                                                              (_DWORD)v1149);
                                                          v699 = v1137;
                                                          goto LABEL_1068;
                                                        }
                                                      }
                                                    }
                                                    else
                                                    {
                                                      GetLastError();
                                                    }
                                                  }
                                                  v700 = v1135;
LABEL_979:
                                                  v699 = v1137;
                                                  goto LABEL_980;
                                                }
                                              }
                                              else
                                              {
                                                LODWORD(Size) = 0;
                                                v632 = v394 & 0xF;
                                                v631 = v632;
                                              }
                                              if ( v631 != 1 )
                                                goto LABEL_870;
                                              goto LABEL_868;
                                            }
                                            v508 = 0;
                                            v1155 = 0;
                                            v1158 = 0;
                                            LODWORD(v1148) = 0;
                                            v1172 = 0;
                                            v1153 = 0;
                                            memset(v1188, 0, sizeof(v1188));
                                            lpMem = 0;
                                            v1162 = 0;
                                            pcchLength = 0;
                                            v1169 = 0;
                                            if ( !((unsigned int (__fastcall *)(__int64, unsigned int *, _QWORD, unsigned int *))off_18002F0A0[0])(
                                                    8,
                                                    &v1162,
                                                    0,
                                                    &v1169) )
                                            {
                                              v508 = GetLastError();
                                              v509 = v508 < 0;
                                              if ( v508 > 0 )
                                              {
                                                v508 = (unsigned __int16)v508 | 0x80070000;
                                                v509 = v508 < 0;
                                              }
                                              if ( !v509 )
                                                v508 = -2147467259;
LABEL_673:
                                              SP<unsigned short *,SP_MEM<unsigned short *>>::Reset(&pcchLength);
                                              SP<unsigned short *,SP_MEM<unsigned short *>>::Reset(&lpMem);
                                              if ( v508 < 0 )
                                              {
                                                pcchLength = 0;
                                                lpMem = 0;
                                                v1155 = 0;
                                              }
                                              else
                                              {
                                                v518 = 0;
                                                LODWORD(v1159) = 0;
                                                v519 = 0;
                                                if ( (_DWORD)v1148 )
                                                {
                                                  while ( 2 )
                                                  {
                                                    for ( i1 = 0; i1 < 0x26; ++i1 )
                                                    {
                                                      if ( *(_DWORD *)(v392 + 4LL * v519) == dword_18002B5B0[i1] )
                                                      {
                                                        v518 = i1;
                                                        LODWORD(v1159) = i1;
                                                        goto LABEL_681;
                                                      }
                                                    }
                                                    if ( ++v519 < (unsigned int)v1148 )
                                                      continue;
                                                    break;
                                                  }
                                                }
LABEL_681:
                                                v521 = v518;
                                                LODWORD(v1136) = 0;
                                                v522 = (unsigned int)dword_18002B5B0[v518];
                                                memset(v1261, 0, sizeof(v1261));
                                                if ( ((unsigned int (__fastcall *)(__int64, _BYTE *, __int64))off_18002F0A8[0])(
                                                       v522,
                                                       v1281,
                                                       85)
                                                  && ((int (__fastcall *)(_BYTE *, __int64, _OWORD *, __int64))off_18002F090[0])(
                                                       v1281,
                                                       88,
                                                       v1261,
                                                       16) > 0 )
                                                {
                                                  LODWORD(v1136) = (HIDWORD(v1261[0]) >> 27) & 1;
                                                }
                                                memset_0(v1189, 0, 0x98u);
                                                v523 = L"Segoe UI Light";
                                                for ( i2 = 0; i2 != 19; ++i2 )
                                                {
                                                  v1189[i2] = v523;
                                                  v525 = -1;
                                                  do
                                                    ++v525;
                                                  while ( v523[v525] );
                                                  v523 += v525 + 1;
                                                }
                                                pcchLength = v1189[*((unsigned __int8 *)qword_18002B650 + 3 * v521)];
                                                lpMem = (LPVOID)v1189[*((unsigned __int8 *)qword_18002B650 + 3 * v521 + 1)];
                                                v1155 = v1189[*((unsigned __int8 *)qword_18002B650 + 3 * v521 + 2)];
                                                v526 = MemoryAlloc(0x1C90u);
                                                v527 = v526;
                                                if ( v526 )
                                                {
                                                  v529 = qword_180029910;
                                                  v530 = v526;
                                                  v531 = 0;
                                                  v532 = -1;
                                                  v533 = 0;
                                                  v534 = 0;
                                                  v535 = 914;
                                                  do
                                                  {
                                                    v536 = *(unsigned __int8 *)v529 << 8;
                                                    v537 = *((unsigned __int8 *)v529 + 1);
                                                    v538 = *((unsigned __int8 *)v529++ + 4);
                                                    v539 = *((unsigned __int8 *)v529 - 5)
                                                         | ((*((unsigned __int8 *)v529 - 6) | ((v536 | v537) << 8)) << 8);
                                                    v540 = v534 ^ v539;
                                                    v541 = *((unsigned __int8 *)v529 - 1)
                                                         | ((*((unsigned __int8 *)v529 - 2)
                                                           | ((*((unsigned __int8 *)v529 - 3) | (v538 << 8)) << 8)) << 8);
                                                    v542 = v534 ^ v539 ^ v533 ^ v541 ^ 0xAC987321;
                                                    v543 = v540
                                                         ^ (__ROR4__(v542, 22) + 4991 * __ROR4__(v542 + 1419157410, 27));
                                                    v544 = v542
                                                         ^ (43881 * __ROR4__(v543 + 133239679, 9) - __ROR4__(v543, 30));
                                                    v545 = v543 ^ (24670 * v544 - (v544 >> 13) - 123127970);
                                                    v546 = v544
                                                         ^ (2033 * __ROR4__(v545 ^ 0xAB69, 26) - __ROR4__(v545, 30));
                                                    v547 = v545 ^ (133239679 - (v546 ^ 0xAB69605E));
                                                    v548 = v546 ^ (43881 * (v547 ^ 0x137F)) ^ __ROR4__(v547, 6);
                                                    v549 = v547
                                                         ^ (__ROR4__(v548, 30) + 24670 * __ROR4__(v548 + 133239679, 15));
                                                    v550 = v548
                                                         ^ (2033 * __ROR4__(v549 + 1419157410, 14) - __ROR4__(v549, 24));
                                                    v551 = v549
                                                         ^ __ROR4__(v550, 10)
                                                         ^ (4991 * __ROR4__(v550 ^ 0xAB69605E, 12));
                                                    v552 = v550 ^ (v551 >> 10) ^ (43881 * (v551 ^ 0x7F1));
                                                    v553 = v551 ^ (2033 * (__ROR4__(~v552, 5) + 24670));
                                                    v554 = v553
                                                         ^ (((v552 ^ (v553 - 2033) ^ 0xAB69605E) >> 2)
                                                          + 4991 * __ROR4__(v552 ^ (v553 - 2033) ^ 0xAB6967AF, 30));
                                                    v555 = v552
                                                         ^ (v553 - 2033)
                                                         ^ 0xAB69605E
                                                         ^ (__ROR4__(v554, 25) + 43881 * __ROR4__(v554 - 133239679, 6));
                                                    v556 = v554 ^ (24670 * (v555 ^ 0x137F) + __ROR4__(v555, 9));
                                                    v557 = v555
                                                         ^ (__ROR4__(v556, 25) + 2033 * __ROR4__(v556 ^ 0xAB69, 27));
                                                    v558 = v556 ^ v557 ^ 0xAC987321;
                                                    v559 = v557 ^ (4991 * __ROR4__(v558, 3) - 219010071);
                                                    v560 = v558
                                                         ^ (24670 * __ROR4__(v559 - 133239679, 1) - __ROR4__(v559, 6));
                                                    v561 = v559
                                                         ^ (__ROR4__(v560, 18) + 2033 * __ROR4__(v560 - 1419157410, 29));
                                                    v562 = v560
                                                         ^ (4991 * __ROR4__(v561 - 1419157410, 17) - __ROR4__(v561, 14));
                                                    v563 = v561 ^ (v562 >> 3) ^ (43881 * (v562 ^ 0x605E));
                                                    v564 = v531
                                                         ^ __ROR4__(v563, 30)
                                                         ^ (24670 * __ROR4__(v563 ^ 0x7F1137F, 28));
                                                    v531 = v539;
                                                    v534 = v562 ^ v564;
                                                    v530[3] = v534;
                                                    v533 = v563 ^ v532;
                                                    v530[7] = v563 ^ v532;
                                                    v532 = v541;
                                                    v530[2] = __ROR4__(v534, 8);
                                                    v530[6] = __ROR4__(v533, 8);
                                                    v530[1] = __ROR4__(v534, 16);
                                                    v530[5] = __ROR4__(v533, 16);
                                                    *v530 = __ROR4__(v534, 24);
                                                    v530[4] = __ROR4__(v533, 24);
                                                    v530 += 8;
                                                    --v535;
                                                  }
                                                  while ( v535 );
                                                  LOBYTE(v394) = (_BYTE)v1138;
                                                  v90 = Src;
                                                  v565 = 0;
                                                  v566 = 0;
                                                  do
                                                  {
                                                    v567 = (__m128)_mm_loadu_si128((const __m128i *)&v527[v565]);
                                                    v565 += 16LL;
                                                    v568 = _mm_xor_ps(v567, v566);
                                                    v566 = v568;
                                                  }
                                                  while ( v565 < 0x1C90 );
                                                  v569 = _mm_xor_ps(v568, (__m128)_mm_srli_si128((__m128i)v568, 8));
                                                  v570 = _mm_xor_ps(v569, (__m128)_mm_srli_si128((__m128i)v569, 4));
                                                  v571 = _mm_xor_ps(v570, (__m128)_mm_srli_si128((__m128i)v570, 2));
                                                  if ( (unsigned __int8)_mm_cvtsi128_si32((__m128i)_mm_xor_ps(
                                                                                                     v571,
                                                                                                     (__m128)_mm_srli_si128((__m128i)v571, 1))) == 127 )
                                                  {
                                                    v572 = (int)v1159;
                                                    v508 = 0;
                                                    v1172 = v527;
                                                    v573 = 0;
                                                    v1170 = 7312;
                                                    do
                                                    {
                                                      for ( i3 = 0; i3 < 0x26; ++i3 )
                                                      {
                                                        if ( v572 == i3 )
                                                          *((_QWORD *)v1188 + v573) = v527;
                                                        v575 = -1;
                                                        do
                                                          ++v575;
                                                        while ( v527[v575] );
                                                        v527 += v575 + 1;
                                                      }
                                                      ++v573;
                                                    }
                                                    while ( v573 < 6 );
                                                    v576 = MemoryAlloc(0x18u);
                                                    SP_MEM<unsigned long>::operator=(&v1153, v576);
                                                    v577 = (void **)v1153;
                                                    if ( v1153 )
                                                    {
                                                      v578 = 0;
                                                      *v1153 = 0;
                                                      v577[2] = 0;
                                                      LODWORD(v1148) = 0;
                                                      while ( 2 )
                                                      {
                                                        v579 = 0;
                                                        lpModuleName = (LPCWSTR)v578;
                                                        while ( 1 )
                                                        {
                                                          v580 = v579;
                                                          if ( *((_WORD *)&v1134 + v578) == word_18002B6C8[v579] )
                                                            break;
                                                          if ( ++v579 >= 6 )
                                                            goto LABEL_719;
                                                        }
                                                        v581 = *((_QWORD *)v1188 + v579);
                                                        v582 = -1;
                                                        v1157 = *((_QWORD *)v1188 + v580);
                                                        do
                                                          ++v582;
                                                        while ( *(_BYTE *)(v581 + v582) );
                                                        v583 = ((__int64 (__fastcall *)(__int64, _QWORD, __int64, _QWORD, _QWORD, _DWORD))off_18002F0C0[0])(
                                                                 65001,
                                                                 0,
                                                                 v581,
                                                                 (unsigned int)(v582 + 1),
                                                                 0,
                                                                 0);
                                                        LODWORD(v1146) = v583;
                                                        if ( !v583 )
                                                          goto LABEL_721;
                                                        v584 = MemoryAlloc(2LL * v583);
                                                        v577[(_QWORD)lpModuleName] = v584;
                                                        if ( !v584 )
                                                          goto LABEL_726;
                                                        v585 = -1;
                                                        do
                                                          ++v585;
                                                        while ( *(_BYTE *)(v1157 + v585) );
                                                        if ( !((unsigned int (__fastcall *)(__int64, _QWORD, SIZE_T, _QWORD, void *, _DWORD))off_18002F0C0[0])(
                                                                65001,
                                                                0,
                                                                v1157,
                                                                (unsigned int)(v585 + 1),
                                                                v584,
                                                                v1146) )
                                                        {
LABEL_721:
                                                          v586 = GetLastError();
                                                          v508 = v586;
                                                          if ( v586 > 0 )
                                                            v508 = (unsigned __int16)v586 | 0x80070000;
                                                          if ( v508 >= 0 )
                                                            v508 = -2147467259;
                                                          goto LABEL_727;
                                                        }
                                                        v578 = v1148;
LABEL_719:
                                                        LODWORD(v1148) = ++v578;
                                                        if ( v578 < 3 )
                                                          continue;
                                                        break;
                                                      }
                                                      v528 = v1170;
                                                      v1190 = (int)v1136;
                                                      v1153 = 0;
                                                      v1139 = v577;
LABEL_738:
                                                      v591 = v1172;
                                                      if ( v1172 && v528 )
                                                      {
                                                        do
                                                        {
                                                          *v591++ = 0;
                                                          --v528;
                                                        }
                                                        while ( v528 );
                                                      }
                                                      SP<unsigned short *,SP_MEM<unsigned short *>>::Reset(&v1153);
                                                      SP<unsigned short *,SP_MEM<unsigned short *>>::Reset(&v1172);
                                                      SP<unsigned short *,SP_MEM<unsigned short *>>::Reset(&v1158);
                                                      if ( v508 < 0 )
                                                        goto LABEL_847;
                                                      v1192 = *v577;
                                                      v1193 = v577[1];
                                                      v1194 = v577[2];
                                                      v1187 = 0;
                                                      LODWORD(v1187) = 16;
                                                      v392 = 0;
                                                      if ( !(unsigned int)((__int64 (__fastcall *)(__int64, _QWORD, __int128 *, _QWORD))off_18002F168)(
                                                                            66,
                                                                            0,
                                                                            &v1187,
                                                                            0) )
                                                      {
                                                        v592 = GetLastError();
                                                        v508 = v592;
                                                        if ( v592 > 0 )
                                                          v508 = (unsigned __int16)v592 | 0x80070000;
                                                        v1191 = 0;
                                                        if ( v508 >= 0 )
                                                          v508 = -2147467259;
                                                        goto LABEL_848;
                                                      }
                                                      v593 = v394 & 0xF;
                                                      v1191 = BYTE4(v1187) & 1;
                                                      v594 = 42;
                                                      LODWORD(v1144) = 42;
                                                      if ( v593 != 1 )
                                                      {
                                                        if ( (v394 & 0xF) == 2 )
                                                        {
                                                          v1123 = 15;
                                                          LODWORD(v1152) = 11;
                                                        }
                                                        else
                                                        {
                                                          if ( (v394 & 0xF) != 3 )
                                                          {
                                                            v594 = 0;
                                                            LODWORD(v1152) = 0;
LABEL_756:
                                                            v1123 = v594;
                                                            goto LABEL_757;
                                                          }
                                                          v1123 = 225;
                                                          LODWORD(v1152) = 225;
                                                        }
LABEL_757:
                                                        memset_0(v1271, 0, 0xDCu);
                                                        v1272 = 220;
                                                        if ( ((unsigned int (__fastcall *)(_QWORD, __int64, _BYTE *))off_18002F0E0[0])(
                                                               0,
                                                               0xFFFFFFFFLL,
                                                               v1271) )
                                                        {
                                                          v595 = v1273;
                                                          LODWORD(v1148) = v1275;
                                                          LODWORD(v1143) = v1274;
                                                          if ( v1273 < 0x60u )
                                                            v595 = 96;
                                                          LODWORD(v1150) = v595;
                                                          v596 = v595;
                                                        }
                                                        else
                                                        {
                                                          v596 = 96;
                                                          LODWORD(v1143) = 0;
                                                          LODWORD(v1150) = 96;
                                                          LODWORD(v1148) = 0;
                                                        }
                                                        v597 = (const WCHAR *)v1155;
                                                        if ( v593 == 1 )
                                                          v597 = (const WCHAR *)pcchLength;
                                                        lpModuleName = v597;
                                                        memset_0(v1262, 0, 0x5Cu);
                                                        v1158 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))off_18002F0F8[0])(
                                                                  0,
                                                                  0,
                                                                  1027);
                                                        if ( !v1158 )
                                                          goto LABEL_814;
                                                        v598 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))off_18002F0B8[0])(
                                                                 v1123,
                                                                 v596,
                                                                 72);
                                                        v1262[4] = 400;
                                                        v1262[0] = -v598;
                                                        v1263 = 5;
                                                        StringCchCopyW(v1264, 0x20u, (unsigned __int16 *)lpModuleName);
                                                        v599 = ((__int64 (__fastcall *)(_DWORD *))off_18002F020[0])(v1262);
                                                        if ( v599 )
                                                        {
                                                          v508 = 0;
                                                          v1195 = (WCHAR *)v599;
                                                        }
                                                        else
                                                        {
                                                          v508 = GetLastError();
                                                          v600 = v508 < 0;
                                                          if ( v508 > 0 )
                                                          {
                                                            v508 = (unsigned __int16)v508 | 0x80070000;
                                                            v600 = v508 < 0;
                                                          }
                                                          if ( !v600 )
                                                            v508 = -2147467259;
                                                        }
                                                        ((void (__fastcall *)(_QWORD, SIZE_T))off_18002F160[0])(
                                                          0,
                                                          v1158);
                                                        if ( v508 < 0 )
                                                          goto LABEL_847;
                                                        v601 = (unsigned __int16 *)v1155;
                                                        if ( v593 == 1 )
                                                          v601 = (unsigned __int16 *)pcchLength;
                                                        memset_0(v1265, 0, 0x5Cu);
                                                        lpModuleName = (LPCWSTR)((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))off_18002F0F8[0])(
                                                                                  0,
                                                                                  0,
                                                                                  1027);
                                                        if ( !lpModuleName )
                                                          goto LABEL_814;
                                                        v602 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))off_18002F0B8[0])(
                                                                 (unsigned int)v1152,
                                                                 (unsigned int)v1150,
                                                                 72);
                                                        v1265[4] = 400;
                                                        v1265[0] = -v602;
                                                        v1266 = 5;
                                                        StringCchCopyW(v1267, 0x20u, v601);
                                                        v603 = ((__int64 (__fastcall *)(_DWORD *))off_18002F020[0])(v1265);
                                                        if ( v603 )
                                                        {
                                                          v508 = 0;
                                                          v1196 = (const WCHAR *)v603;
                                                        }
                                                        else
                                                        {
                                                          v508 = GetLastError();
                                                          v604 = v508 < 0;
                                                          if ( v508 > 0 )
                                                          {
                                                            v508 = (unsigned __int16)v508 | 0x80070000;
                                                            v604 = v508 < 0;
                                                          }
                                                          if ( !v604 )
                                                            v508 = -2147467259;
                                                        }
                                                        ((void (__fastcall *)(_QWORD, LPCWSTR))off_18002F160[0])(
                                                          0,
                                                          lpModuleName);
                                                        if ( v508 < 0 )
                                                          goto LABEL_847;
                                                        if ( v593 != 1 )
                                                        {
                                                          if ( v593 == 2 )
                                                          {
                                                            v605 = (int)v1143 / 4;
                                                            goto LABEL_789;
                                                          }
                                                          if ( v593 != 3 )
                                                          {
                                                            v605 = 0;
LABEL_789:
                                                            v606 = 0;
                                                            goto LABEL_791;
                                                          }
                                                        }
                                                        v605 = v1143;
                                                        v606 = v1148;
LABEL_791:
                                                        *((_QWORD *)&v1165 + 1) = __PAIR64__(v606, v605);
                                                        if ( v593 == 1 )
                                                        {
                                                          v607 = 150;
                                                          LODWORD(v1152) = 32;
                                                        }
                                                        else
                                                        {
                                                          v607 = 0;
                                                          if ( (unsigned int)(v593 - 2) < 2 )
                                                          {
                                                            LODWORD(v1144) = 0;
                                                            LODWORD(v1152) = 0;
                                                          }
                                                          else
                                                          {
                                                            LODWORD(v1152) = 0;
                                                            LODWORD(v1144) = 0;
                                                          }
                                                        }
                                                        v1124 = v607;
                                                        v608 = v1192;
                                                        LODWORD(v1143) = v605 - v607;
                                                        v1205 = v605 - v607;
                                                        v1201 = v605 - v607;
                                                        lpModuleName = (LPCWSTR)((__int64 (__fastcall *)(SIZE_T, WCHAR *, _QWORD))off_18002F078[0])(
                                                                                  v1137,
                                                                                  v1195,
                                                                                  0);
                                                        LODWORD(v1146) = ((__int64 (__fastcall *)(SIZE_T, void *, __int64, int *, int, _QWORD))off_18002F0D8[0])(
                                                                           v1137,
                                                                           v608,
                                                                           0xFFFFFFFFLL,
                                                                           &v1199,
                                                                           3152,
                                                                           0);
                                                        v508 = (_DWORD)v1146 != 0 ? 0 : 0x80004005;
                                                        if ( lpModuleName )
                                                          ((void (__fastcall *)(SIZE_T, LPCWSTR))off_18002F078[0])(
                                                            v1137,
                                                            lpModuleName);
                                                        if ( (_DWORD)v1146 )
                                                        {
                                                          v609 = v1193;
                                                          lpModuleName = (LPCWSTR)((__int64 (__fastcall *)(SIZE_T, const WCHAR *))off_18002F078[0])(
                                                                                    v1137,
                                                                                    v1196);
                                                          LODWORD(v1146) = ((__int64 (__fastcall *)(SIZE_T, void *, __int64, int *, int, _QWORD))off_18002F0D8[0])(
                                                                             v1137,
                                                                             v609,
                                                                             0xFFFFFFFFLL,
                                                                             &v1203,
                                                                             3152,
                                                                             0);
                                                          v508 = (_DWORD)v1146 != 0 ? 0 : 0x80004005;
                                                          if ( lpModuleName )
                                                            ((void (__fastcall *)(SIZE_T, LPCWSTR))off_18002F078[0])(
                                                              v1137,
                                                              lpModuleName);
                                                          if ( (_DWORD)v1146 )
                                                          {
                                                            if ( v593 == 2 || v593 == 3 )
                                                            {
                                                              v610 = v1205;
                                                              if ( v1201 > v1205 )
                                                                v610 = v1201;
                                                              LODWORD(v1143) = v610;
                                                            }
                                                            else
                                                            {
                                                              v610 = v1143;
                                                            }
                                                            if ( v1190 )
                                                            {
                                                              ((void (__fastcall *)(int *, _QWORD, _QWORD))off_18002F150)(
                                                                &v1199,
                                                                v610 - v1201,
                                                                (unsigned int)v1144);
                                                              v611 = v610 - v1205;
                                                            }
                                                            else
                                                            {
                                                              ((void (__fastcall *)(int *, _QWORD, _QWORD))off_18002F150)(
                                                                &v1199,
                                                                v1124,
                                                                (unsigned int)v1144);
                                                              v611 = v1124;
                                                            }
                                                            ((void (__fastcall *)(int *, __int64, _QWORD))off_18002F150)(
                                                              &v1203,
                                                              v611,
                                                              (unsigned int)(v1202 + (_DWORD)v1152));
                                                            if ( (unsigned int)(v593 - 2) <= 1 )
                                                            {
                                                              *((_QWORD *)&v1165 + 1) = __PAIR64__(v1206, v610);
                                                              v1198 = -5723992;
                                                              goto LABEL_834;
                                                            }
                                                            if ( v593 != 1 )
                                                              goto LABEL_834;
                                                            v1198 = 0xFFFFFF;
                                                            memset_0(v1268, 0, 0x5Cu);
                                                            v508 = 0;
                                                            lpModuleName = (LPCWSTR)((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))off_18002F0F8[0])(
                                                                                      0,
                                                                                      0,
                                                                                      1027);
                                                            if ( !lpModuleName )
                                                            {
LABEL_814:
                                                              v612 = GetLastError();
                                                              v392 = 0;
                                                              v508 = v612;
                                                              if ( v612 > 0 )
                                                                v508 = (unsigned __int16)v612 | 0x80070000;
                                                              if ( v508 >= 0 )
                                                                v508 = -2147467259;
                                                              goto LABEL_848;
                                                            }
                                                            v613 = ((__int64 (__fastcall *)(__int64, _QWORD))off_18002F0B8[0])(
                                                                     11,
                                                                     (unsigned int)v1150);
                                                            v1268[4] = 400;
                                                            v1268[0] = -v613;
                                                            v1269 = 5;
                                                            StringCchCopyW(v1270, 0x20u, (unsigned __int16 *)lpMem);
                                                            v614 = ((__int64 (__fastcall *)(_DWORD *))off_18002F020[0])(v1268);
                                                            if ( v614 )
                                                            {
                                                              v1197 = v614;
                                                            }
                                                            else
                                                            {
                                                              v508 = GetLastError();
                                                              v615 = v508 < 0;
                                                              if ( v508 > 0 )
                                                              {
                                                                v508 = (unsigned __int16)v508 | 0x80070000;
                                                                v615 = v508 < 0;
                                                              }
                                                              if ( !v615 )
                                                                v508 = -2147467259;
                                                            }
                                                            ((void (__fastcall *)(_QWORD, LPCWSTR))off_18002F160[0])(
                                                              0,
                                                              lpModuleName);
                                                            if ( v508 >= 0 )
                                                            {
                                                              v616 = v1194;
                                                              v1209 = v1143;
                                                              lpModuleName = (LPCWSTR)((__int64 (__fastcall *)(SIZE_T, __int64))off_18002F078[0])(
                                                                                        v1137,
                                                                                        v1197);
                                                              LODWORD(v1146) = ((__int64 (__fastcall *)(SIZE_T, void *, __int64, unsigned int *, int, _QWORD))off_18002F0D8[0])(
                                                                                 v1137,
                                                                                 v616,
                                                                                 0xFFFFFFFFLL,
                                                                                 &v1207,
                                                                                 1120,
                                                                                 0);
                                                              v508 = (_DWORD)v1146 != 0 ? 0 : 0x80004005;
                                                              if ( lpModuleName )
                                                                ((void (__fastcall *)(SIZE_T, LPCWSTR))off_18002F078[0])(
                                                                  v1137,
                                                                  lpModuleName);
                                                              if ( (_DWORD)v1146 )
                                                              {
                                                                v617 = (unsigned int)v1150;
                                                                v618 = v1209 + 24;
                                                                v1210 = 32;
                                                                if ( (int)(v1209 + 24) < 90 )
                                                                  v618 = 90;
                                                                v1209 = v618;
                                                                v1207 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))off_18002F0B8[0])(
                                                                          v1207,
                                                                          (unsigned int)v1150,
                                                                          96);
                                                                v1208 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))off_18002F0B8[0])(
                                                                          v1208,
                                                                          v617,
                                                                          96);
                                                                v1209 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))off_18002F0B8[0])(
                                                                          v1209,
                                                                          v617,
                                                                          96);
                                                                v1210 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))off_18002F0B8[0])(
                                                                          v1210,
                                                                          v617,
                                                                          96);
                                                                off_18002F150();
LABEL_834:
                                                                v619 = DWORD2(v1165);
                                                                LODWORD(v1148) = HIDWORD(v1165);
                                                                v620 = v593 - 1;
                                                                if ( v620 )
                                                                {
                                                                  v621 = v620 - 1;
                                                                  if ( v621 )
                                                                  {
                                                                    if ( v621 == 1 )
                                                                    {
                                                                      v1260 = 0;
                                                                      v1258 = 0;
                                                                      v1259 = 0;
                                                                      v622 = ((__int64 (__fastcall *)(_QWORD, __int64))off_18002F148[0])(
                                                                               0,
                                                                               1);
                                                                      LODWORD(v1258) = 40;
                                                                      v392 = 0;
                                                                      if ( ((unsigned int (__fastcall *)(__int64, __int128 *))off_18002F108[0])(
                                                                             v622,
                                                                             &v1258) )
                                                                      {
                                                                        ((void (__fastcall *)(_QWORD, char *))off_18002F140[0])(
                                                                          0,
                                                                          (char *)&v1259 + 4);
                                                                        ((void (__fastcall *)(_QWORD, char *))off_18002F140[0])(
                                                                          0,
                                                                          (char *)&v1259 + 12);
                                                                        LODWORD(v1165) = 50
                                                                                       * (HIDWORD(v1259) - v619)
                                                                                       / 100;
                                                                        DWORD1(v1165) = 50
                                                                                      * ((int)v1260 - (int)v1148)
                                                                                      / 100;
                                                                      }
                                                                      goto LABEL_845;
                                                                    }
                                                                  }
                                                                  else
                                                                  {
                                                                    v623 = v1190;
                                                                    v1249 = 0;
                                                                    v1247 = 0;
                                                                    v1248 = 0;
                                                                    v624 = ((__int64 (__fastcall *)(_QWORD, __int64))off_18002F148[0])(
                                                                             0,
                                                                             1);
                                                                    LODWORD(v1247) = 40;
                                                                    if ( ((unsigned int (__fastcall *)(__int64, __int128 *))off_18002F108[0])(
                                                                           v624,
                                                                           &v1247) )
                                                                    {
                                                                      ((void (__fastcall *)(_QWORD, char *))off_18002F140[0])(
                                                                        0,
                                                                        (char *)&v1248 + 4);
                                                                      ((void (__fastcall *)(_QWORD, char *))off_18002F140[0])(
                                                                        0,
                                                                        (char *)&v1248 + 12);
                                                                      if ( v623 )
                                                                        v625 = DWORD1(v1248) + 5 * HIDWORD(v1248) / 100;
                                                                      else
                                                                        v625 = 95 * (HIDWORD(v1248) - v619) / 100;
                                                                      LODWORD(v1165) = v625;
                                                                      DWORD1(v1165) = 95
                                                                                    * ((int)v1249 - (int)v1148)
                                                                                    / 100;
                                                                    }
                                                                  }
                                                                  v392 = 0;
                                                                }
                                                                else
                                                                {
                                                                  v392 = 0;
                                                                  *(_QWORD *)&v1165 = 0;
                                                                }
LABEL_845:
                                                                v508 = 0;
LABEL_848:
                                                                ((void (__fastcall *)(_QWORD, SIZE_T))off_18002F160[0])(
                                                                  0,
                                                                  v1137);
                                                                goto LABEL_849;
                                                              }
                                                            }
                                                          }
                                                        }
LABEL_847:
                                                        v392 = 0;
                                                        goto LABEL_848;
                                                      }
                                                      LODWORD(v1152) = 11;
                                                      goto LABEL_756;
                                                    }
LABEL_726:
                                                    v508 = -2147024882;
LABEL_727:
                                                    if ( v577 )
                                                    {
                                                      for ( i4 = 0; i4 != 3; ++i4 )
                                                      {
                                                        v588 = v577[i4];
                                                        if ( v588 )
                                                        {
                                                          v589 = -1;
                                                          do
                                                            ++v589;
                                                          while ( *(_WORD *)&v588[2 * v589] );
                                                          for ( i5 = 2 * v589 + 2; i5; --i5 )
                                                            *v588++ = 0;
                                                          MemoryFree(v577[i4]);
                                                        }
                                                      }
                                                    }
                                                    v528 = v1170;
LABEL_737:
                                                    v577 = (void **)v1135;
                                                    goto LABEL_738;
                                                  }
                                                  MemoryFree(v527);
                                                  v508 = -1073425151;
                                                }
                                                else
                                                {
                                                  v508 = -2147024882;
                                                }
                                              }
                                              v528 = 0;
                                              goto LABEL_737;
                                            }
                                            v510 = MemoryAlloc(2LL * v1169);
                                            SP_MEM<unsigned long>::operator=(&lpMem, v510);
                                            v511 = (char *)lpMem;
                                            if ( lpMem
                                              && (v512 = MemoryAlloc(4LL * (v1162 + 1)),
                                                  SP_MEM<unsigned long>::operator=(&pcchLength, v512),
                                                  pcchLength) )
                                            {
                                              if ( ((unsigned int (__fastcall *)(__int64, unsigned int *, char *, unsigned int *))off_18002F0A0[0])(
                                                     8,
                                                     &v1162,
                                                     v511,
                                                     &v1169) )
                                              {
                                                if ( v1162 )
                                                {
                                                  v514 = (WCHAR *)pcchLength;
                                                  for ( i6 = 0; i6 < v1162; ++i6 )
                                                  {
                                                    *(_DWORD *)v514 = ((__int64 (__fastcall *)(char *, _QWORD))off_18002F0B0[0])(
                                                                        v511,
                                                                        0);
                                                    v516 = -1;
                                                    do
                                                      ++v516;
                                                    while ( *(_WORD *)&v511[2 * v516] );
                                                    v514 += 2;
                                                    v511 += 2 * v516 + 2;
                                                  }
                                                  v90 = Src;
                                                  lpModuleName = v514;
                                                  v517 = v514;
                                                }
                                                else
                                                {
                                                  v517 = (_DWORD *)pcchLength;
                                                }
                                                v392 = pcchLength;
                                                *v517 = 1033;
                                                pcchLength = 0;
                                                LODWORD(v1148) = v1162 + 1;
                                                v1158 = v392;
                                                goto LABEL_673;
                                              }
                                              v508 = GetLastError();
                                              v513 = v508 < 0;
                                              if ( v508 > 0 )
                                              {
                                                v508 = (unsigned __int16)v508 | 0x80070000;
                                                v513 = v508 < 0;
                                              }
                                              if ( !v513 )
                                                v508 = -2147467259;
                                            }
                                            else
                                            {
                                              v508 = -2147024882;
                                            }
                                            v392 = v1155;
                                            goto LABEL_673;
                                          }
                                          v451 = dword_18002F8E8;
LABEL_642:
                                          dword_18002F8E8 = v451 + 1;
                                          goto LABEL_643;
                                        }
                                        v395 = dword_18002F8E8;
LABEL_596:
                                        dword_18002F8E8 = v395 + 1;
                                        goto LABEL_597;
                                      }
LABEL_541:
                                      v389 = GetProcessHeap();
                                      HeapFree(v389, 0, v89);
                                      goto LABEL_542;
                                    }
                                  }
                                  if ( (_DWORD)v1149 != 6 )
                                    goto LABEL_472;
                                  v367 = lpMem;
                                  v368 = 0;
                                  while ( 1 )
                                  {
                                    v369 = v367 + 1;
                                    if ( v367 + 1 < v367 )
                                      break;
                                    v367 = (_DWORD *)((char *)v369 + (unsigned int)*v367);
                                    if ( v367 < v369 )
                                      break;
                                    if ( ++v368 )
                                    {
                                      if ( v367 + 1 < v367 )
                                        break;
                                      v370 = 0;
                                      if ( *v367 )
                                        v370 = (LPCWSTR *)(v367 + 1);
                                      if ( *v367 == 8 )
                                      {
                                        v371 = lpMem;
                                        lpModuleName = *v370;
                                        v372 = 0;
                                        while ( 1 )
                                        {
                                          v373 = v371 + 1;
                                          if ( v371 + 1 < v371 )
                                            goto LABEL_532;
                                          v371 = (_DWORD *)((char *)v373 + (unsigned int)*v371);
                                          if ( v371 < v373 )
                                            goto LABEL_532;
                                          if ( (unsigned int)++v372 >= 2 )
                                          {
                                            if ( v371 + 1 < v371 )
                                              goto LABEL_532;
                                            v374 = 0;
                                            if ( *v371 )
                                              v374 = v371 + 1;
                                            if ( *v371 == 4 )
                                            {
                                              v375 = *v374;
                                              v376 = (unsigned int *)lpMem;
                                              v377 = 0;
                                              LODWORD(v1143) = v366;
                                              while ( 1 )
                                              {
                                                v378 = v376 + 1;
                                                if ( v376 + 1 < v376 )
                                                  goto LABEL_145;
                                                v376 = (unsigned int *)((char *)v378 + *v376);
                                                if ( v376 < v378 )
                                                  goto LABEL_145;
                                                if ( (unsigned int)++v377 >= 3 )
                                                {
                                                  if ( v376 + 1 < v376 )
                                                    goto LABEL_145;
                                                  v379 = *v376;
                                                  if ( (_DWORD)v379 )
                                                    v146 = v376 + 1;
                                                  v380 = lpMem;
                                                  v381 = 0;
                                                  while ( 1 )
                                                  {
                                                    v382 = v380 + 1;
                                                    if ( v380 + 1 < v380 )
                                                      break;
                                                    v380 = (_DWORD *)((char *)v382 + (unsigned int)*v380);
                                                    if ( v380 < v382 )
                                                      break;
                                                    if ( (unsigned int)++v381 >= 4 )
                                                    {
                                                      if ( v380 + 1 >= v380 )
                                                      {
                                                        v383 = 0;
                                                        if ( *v380 )
                                                          v383 = v380 + 1;
                                                        if ( *v380 != 4 )
                                                        {
LABEL_524:
                                                          v90 = -1073741789;
                                                          goto LABEL_150;
                                                        }
                                                        v384 = 0;
                                                        v385 = lpMem;
                                                        v386 = *v383;
                                                        while ( 1 )
                                                        {
                                                          v387 = v385 + 1;
                                                          if ( v385 + 1 < v385 )
                                                            break;
                                                          v385 = (_DWORD *)((char *)v387 + (unsigned int)*v385);
                                                          if ( v385 < v387 )
                                                            break;
                                                          if ( (unsigned int)++v384 >= 5 )
                                                          {
                                                            if ( v385 + 1 < v385 )
                                                              goto LABEL_531;
                                                            v388 = 0;
                                                            if ( *v385 )
                                                              v388 = v385 + 1;
                                                            if ( *v385 != 4 )
                                                              goto LABEL_524;
                                                            if ( (LPCWSTR)v1158 != lpModuleName )
                                                            {
                                                              v90 = -1073425151;
                                                              goto LABEL_150;
                                                            }
                                                            v92 = v375;
                                                            v1122 = *v388;
                                                            v1160 = v375;
                                                            if ( v386 > 4 || (unsigned int)v379 > 4 )
                                                            {
                                                              v90 = -2147024774;
                                                              goto LABEL_150;
                                                            }
                                                            memcpy_0(v1176, v146, v379);
                                                            v90 = 0;
                                                            goto LABEL_148;
                                                          }
                                                        }
                                                      }
                                                      break;
                                                    }
                                                  }
LABEL_531:
                                                  v90 = -1073741675;
                                                  goto LABEL_150;
                                                }
                                              }
                                            }
                                            goto LABEL_500;
                                          }
                                        }
                                      }
                                      goto LABEL_500;
                                    }
                                  }
                                }
LABEL_532:
                                v90 = -1073741675;
                                goto LABEL_150;
                              }
                              v364 = GetProcessHeap();
                              HeapFree(v364, 0, v1150);
LABEL_469:
                              v146 = 0;
                              goto LABEL_470;
                            }
LABEL_446:
                            v351 = GetProcessHeap();
                            HeapFree(v351, 0, v1134);
                            v146 = 0;
                            goto LABEL_447;
                          }
                        }
                        v1157 = (SIZE_T)v95;
                      }
                      v196 = -1073741801;
                      v212 = v1135;
                      lpModuleName = *(LPCWSTR *)(v1135 + 8);
                      if ( lpModuleName )
                      {
                        v213 = GetProcessHeap();
                        HeapFree(v213, 0, (LPVOID)lpModuleName);
                        v212 = v1135;
                        *(_QWORD *)(v1135 + 8) = 0;
                      }
                      lpModuleName = *(LPCWSTR *)(v212 + 24);
                      if ( lpModuleName )
                      {
                        v214 = GetProcessHeap();
                        HeapFree(v214, 0, (LPVOID)lpModuleName);
                        v212 = v1135;
                        *(_QWORD *)(v1135 + 24) = 0;
                      }
                      lpModuleName = *(LPCWSTR *)(v212 + 40);
                      if ( lpModuleName )
                      {
                        v215 = GetProcessHeap();
                        HeapFree(v215, 0, (LPVOID)lpModuleName);
                        *(_QWORD *)(v1135 + 40) = 0;
                      }
                      v216 = GetProcessHeap();
                      HeapFree(v216, 0, (LPVOID)v1135);
                    }
                    else
                    {
                      v196 = -1073741801;
                    }
                    v197 = v1139;
                    goto LABEL_226;
                  }
                  v133 = v128;
                  v134 = v100;
                  for ( i7 = 0; i7 < v125; v134 = (_DWORD *)((char *)v134 + v136) )
                  {
                    v136 = *v134 + 4;
                    if ( *v134 >= 0xFFFFFFFC || (_DWORD *)((char *)v134 + v136) < v134 )
                      goto LABEL_145;
                    ++i7;
                  }
                  if ( v134 + 1 >= v134 )
                  {
                    if ( v134 + 2 > (_DWORD *)((char *)v100 + v133) )
                      goto LABEL_122;
                    v132 = v125 + 1;
                    *v134 = 4;
                    v134[1] = v1122;
                    LODWORD(Size) = v133;
                    v138 = v100;
                    v139 = 0;
                    for ( i8 = v133; v139 < v132; v138 = (_DWORD *)((char *)v138 + v140) )
                    {
                      v140 = *v138 + 4;
                      if ( *v138 >= 0xFFFFFFFC || (_DWORD *)((char *)v138 + v140) < v138 )
                        goto LABEL_145;
                      ++v139;
                    }
                    if ( v138 + 1 >= v138 )
                    {
                      if ( v138 + 2 > (_DWORD *)((char *)v100 + (unsigned int)v133) )
                        goto LABEL_122;
                      *v138 = 4;
                      v138[1] = 4;
                      goto LABEL_206;
                    }
                  }
LABEL_145:
                  v90 = -1073741675;
                  goto LABEL_146;
                }
                v128 = -1;
                v90 = -1073741675;
LABEL_185:
                Src = v90;
                goto LABEL_186;
              }
            }
            v90 = -1073741675;
          }
          else
          {
            v90 = -1073741811;
          }
LABEL_184:
          v128 = (unsigned int)v1150;
          goto LABEL_185;
        }
      }
      else
      {
        v113 = v112 + 12;
        if ( (int)v112 + 12 >= (unsigned int)v112 )
        {
          v114 = 3;
          LODWORD(v112) = v112 + 24;
          LODWORD(v1150) = v113 + 12;
          if ( v113 + 12 < v113 )
            goto LABEL_145;
          goto LABEL_164;
        }
      }
LABEL_135:
      v90 = -1073741675;
      goto LABEL_146;
    }
    v3 = dword_18002F8E8;
LABEL_46:
    dword_18002F8E8 = v3 + 1;
    goto LABEL_47;
  }
  v2 = -2147024809;
LABEL_1497:
  SP_HLOCAL<unsigned char>::~SP_HLOCAL<unsigned char>(&v1173);
  return v2;
}

```

## disassembly

```asm
0x18001d310  push    rbp
0x18001d312  push    rbx
0x18001d313  push    rsi
0x18001d314  push    rdi
0x18001d315  push    r12
0x18001d317  push    r13
0x18001d319  push    r14
0x18001d31b  push    r15
0x18001d31d  lea     rbp, [rsp-0D88h]
0x18001d325  sub     rsp, 0E88h
0x18001d32c  mov     rax, cs:__security_cookie
0x18001d333  xor     rax, rsp
0x18001d336  mov     [rbp+0DC0h+var_50], rax
0x18001d33d  xor     r15d, r15d
0x18001d340  mov     [rbp+0DC0h+var_C90], rdx
0x18001d347  mov     [rbp+0DC0h+var_D20], r15
0x18001d34e  test    rdx, rdx
0x18001d351  jnz     short loc_18001D35D
0x18001d353  mov     ebx, 80070057h
0x18001d358  jmp     loc_1800264AD
0x18001d35d  mov     dword ptr [rbp+0DC0h+var_DE0], r15d
0x18001d361  mov     esi, 1
0x18001d366  mov     [rbp+0DC0h+var_DA8], r15
0x18001d36a  xor     eax, eax
0x18001d36c  lock cmpxchg cs:dword_18002F8EC, esi
0x18001d374  jnz     short loc_18001D36A
0x18001d376  mov     eax, cs:dword_18002F8E8
0x18001d37c  lea     r14, qword_18002F860
0x18001d383  or      ebx, 0FFFFFFFFh
0x18001d386  lea     r13, off_18002F000
0x18001d38d  mov     [rbp+0DC0h+var_D6C], ebx
0x18001d390  mov     r12d, 60h ; '`'
0x18001d396  test    eax, eax
0x18001d398  jnz     loc_18001D906
0x18001d39e  call    cs:__imp_GetProcessHeap
0x18001d3a4  xor     edx, edx; dwFlags
0x18001d3a6  mov     r8d, 338h; dwBytes
0x18001d3ac  mov     rcx, rax; hHeap
0x18001d3af  call    cs:__imp_HeapAlloc
0x18001d3b5  mov     rdi, rax
0x18001d3b8  test    rax, rax
0x18001d3bb  jz      loc_18001D73B
0x18001d3c1  mov     r14, rax
0x18001d3c4  lea     rsi, qword_18002B6E0
0x18001d3cb  mov     r12d, r15d
0x18001d3ce  mov     r10d, r15d
0x18001d3d1  mov     r8d, r15d
0x18001d3d4  mov     eax, 0AB69605Eh
0x18001d3d9  mov     r15d, 67h ; 'g'
0x18001d3df  mov     r13d, ebx
0x18001d3e2  movzx   ecx, byte ptr [rsi]
0x18001d3e5  shl     ecx, 8
0x18001d3e8  movzx   ebx, byte ptr [rsi+1]
0x18001d3ec  movzx   r11d, byte ptr [rsi+4]
0x18001d3f1  lea     rsi, [rsi+8]
0x18001d3f5  or      ebx, ecx
0x18001d3f7  shl     r11d, 8
0x18001d3fb  movzx   ecx, byte ptr [rsi-6]
0x18001d3ff  shl     ebx, 8
0x18001d402  or      ebx, ecx
0x18001d404  movzx   ecx, byte ptr [rsi-5]
0x18001d408  shl     ebx, 8
0x18001d40b  or      ebx, ecx
0x18001d40d  movzx   ecx, byte ptr [rsi-3]
0x18001d411  or      r11d, ecx
0x18001d414  mov     edx, ebx
0x18001d416  movzx   ecx, byte ptr [rsi-2]
0x18001d41a  xor     edx, r8d
0x18001d41d  mov     r8d, edx
0x18001d420  shl     r11d, 8
0x18001d424  or      r11d, ecx
0x18001d427  movzx   ecx, byte ptr [rsi-1]
0x18001d42b  shl     r11d, 8
0x18001d42f  or      r11d, ecx
0x18001d432  xor     r8d, r11d
0x18001d435  xor     r8d, r10d
0x18001d438  xor     r8d, 0AC987321h
0x18001d43f  lea     ecx, [r8+54969FA2h]
0x18001d446  ror     ecx, 1Bh
0x18001d449  imul    r9d, ecx, 137Fh
0x18001d450  mov     ecx, r8d
0x18001d453  ror     ecx, 16h
0x18001d456  add     r9d, ecx
0x18001d459  xor     r9d, edx
0x18001d45c  lea     ecx, [r9+7F1137Fh]
0x18001d463  ror     ecx, 9
0x18001d466  imul    edx, ecx, 0AB69h
0x18001d46c  mov     ecx, r9d
0x18001d46f  ror     ecx, 1Eh
0x18001d472  sub     edx, ecx
0x18001d474  xor     edx, r8d
0x18001d477  imul    r10d, edx, 605Eh
0x18001d47e  mov     ecx, edx
0x18001d480  shr     ecx, 0Dh
0x18001d483  sub     r10d, ecx
0x18001d486  sub     r10d, 756C8A2h
0x18001d48d  xor     r10d, r9d
0x18001d490  mov     r9d, 7F1137Fh
0x18001d496  mov     ecx, r10d
0x18001d499  xor     ecx, 0AB69h
0x18001d49f  ror     ecx, 1Ah
0x18001d4a2  imul    r8d, ecx, 7F1h
0x18001d4a9  mov     ecx, r10d
0x18001d4ac  ror     ecx, 1Eh
0x18001d4af  sub     r8d, ecx
0x18001d4b2  xor     r8d, edx
0x18001d4b5  mov     ecx, r8d
0x18001d4b8  xor     ecx, eax
0x18001d4ba  sub     r9d, ecx
0x18001d4bd  xor     r9d, r10d
0x18001d4c0  mov     ecx, r9d
0x18001d4c3  mov     r10d, r9d
0x18001d4c6  xor     ecx, 137Fh
0x18001d4cc  ror     r10d, 6
0x18001d4d0  imul    edx, ecx, 0AB69h
0x18001d4d6  xor     r10d, edx
0x18001d4d9  xor     r10d, r8d
0x18001d4dc  lea     ecx, [r10+7F1137Fh]
0x18001d4e3  ror     ecx, 0Fh
0x18001d4e6  imul    edx, ecx, 605Eh
0x18001d4ec  mov     ecx, r10d
0x18001d4ef  ror     ecx, 1Eh
0x18001d4f2  add     edx, ecx
0x18001d4f4  xor     edx, r9d
0x18001d4f7  lea     ecx, [rdx+54969FA2h]
0x18001d4fd  ror     ecx, 0Eh
0x18001d500  imul    r8d, ecx, 7F1h
0x18001d507  mov     ecx, edx
0x18001d509  ror     ecx, 18h
0x18001d50c  sub     r8d, ecx
0x18001d50f  xor     r8d, r10d
0x18001d512  mov     ecx, r8d
0x18001d515  mov     r10d, 7F1h
0x18001d51b  xor     ecx, eax
0x18001d51d  ror     ecx, 0Ch
0x18001d520  imul    r9d, ecx, 137Fh
0x18001d527  mov     ecx, r8d
0x18001d52a  ror     ecx, 0Ah
0x18001d52d  xor     r9d, ecx
0x18001d530  xor     r9d, edx
0x18001d533  mov     ecx, r9d
0x18001d536  xor     ecx, r10d
0x18001d539  imul    edx, ecx, 0AB69h
0x18001d53f  mov     ecx, r9d
0x18001d542  shr     ecx, 0Ah
0x18001d545  xor     edx, ecx
0x18001d547  xor     edx, r8d
0x18001d54a  mov     ecx, edx
0x18001d54c  not     ecx
0x18001d54e  ror     ecx, 5
0x18001d551  add     ecx, 605Eh
0x18001d557  imul    r8d, ecx, 7F1h
0x18001d55e  xor     r8d, r9d
0x18001d561  lea     r9d, [r8-7F1h]
0x18001d568  xor     r9d, edx
0x18001d56b  xor     r9d, eax
0x18001d56e  mov     ecx, r9d
0x18001d571  xor     ecx, r10d
0x18001d574  ror     ecx, 1Eh
0x18001d577  imul    r10d, ecx, 137Fh
0x18001d57e  mov     ecx, r9d
0x18001d581  shr     ecx, 2
0x18001d584  add     r10d, ecx
0x18001d587  xor     r10d, r8d
0x18001d58a  lea     ecx, [r10-7F1137Fh]
0x18001d591  ror     ecx, 6
0x18001d594  imul    r8d, ecx, 0AB69h
0x18001d59b  mov     ecx, r10d
0x18001d59e  ror     ecx, 19h
0x18001d5a1  add     r8d, ecx
0x18001d5a4  xor     r8d, r9d
0x18001d5a7  mov     ecx, r8d
0x18001d5aa  mov     r9d, r8d
0x18001d5ad  xor     ecx, 137Fh
0x18001d5b3  ror     r9d, 9
0x18001d5b7  imul    edx, ecx, 605Eh
0x18001d5bd  add     r9d, edx
0x18001d5c0  xor     r9d, r10d
0x18001d5c3  mov     ecx, r9d
0x18001d5c6  xor     ecx, 0AB69h
0x18001d5cc  ror     ecx, 1Bh
0x18001d5cf  imul    edx, ecx, 7F1h
0x18001d5d5  mov     ecx, r9d
0x18001d5d8  ror     ecx, 19h
0x18001d5db  add     edx, ecx
0x18001d5dd  xor     edx, r8d
0x18001d5e0  mov     r8d, edx
0x18001d5e3  xor     r8d, r9d
0x18001d5e6  xor     r8d, 0AC987321h
0x18001d5ed  mov     ecx, r8d
0x18001d5f0  ror     ecx, 3
0x18001d5f3  imul    r9d, ecx, 137Fh
0x18001d5fa  sub     r9d, 0D0DD417h
0x18001d601  xor     r9d, edx
0x18001d604  lea     ecx, [r9-7F1137Fh]
0x18001d60b  ror     ecx, 1
0x18001d60d  imul    edx, ecx, 605Eh
0x18001d613  mov     ecx, r9d
0x18001d616  ror     ecx, 6
0x18001d619  sub     edx, ecx
0x18001d61b  xor     edx, r8d
0x18001d61e  lea     ecx, [rdx-54969FA2h]
0x18001d624  ror     ecx, 1Dh
0x18001d627  imul    r8d, ecx, 7F1h
0x18001d62e  mov     ecx, edx
0x18001d630  ror     ecx, 12h
0x18001d633  add     r8d, ecx
0x18001d636  xor     r8d, r9d
0x18001d639  lea     ecx, [r8-54969FA2h]
0x18001d640  ror     ecx, 11h
0x18001d643  imul    r9d, ecx, 137Fh
0x18001d64a  mov     ecx, r8d
0x18001d64d  ror     ecx, 0Eh
0x18001d650  sub     r9d, ecx
0x18001d653  xor     r9d, edx
0x18001d656  mov     ecx, r9d
0x18001d659  xor     ecx, 605Eh
0x18001d65f  imul    r10d, ecx, 0AB69h
0x18001d666  mov     ecx, r9d
0x18001d669  shr     ecx, 3
0x18001d66c  xor     r10d, ecx
0x18001d66f  xor     r10d, r8d
0x18001d672  mov     ecx, r10d
0x18001d675  xor     ecx, 7F1137Fh
0x18001d67b  ror     ecx, 1Ch
0x18001d67e  imul    r8d, ecx, 605Eh
0x18001d685  mov     ecx, r10d
0x18001d688  ror     ecx, 1Eh
0x18001d68b  xor     r10d, r13d
0x18001d68e  mov     r13d, r11d
0x18001d691  xor     r8d, ecx
0x18001d694  xor     r8d, r9d
0x18001d697  xor     r8d, r12d
0x18001d69a  mov     r12d, ebx
0x18001d69d  mov     [r14+3], r8b
0x18001d6a1  mov     ecx, r8d
0x18001d6a4  ror     ecx, 8
0x18001d6a7  mov     [r14+7], r10b
0x18001d6ab  mov     [r14+2], cl
0x18001d6af  mov     ecx, r10d
0x18001d6b2  ror     ecx, 8
0x18001d6b5  mov     [r14+6], cl
0x18001d6b9  mov     ecx, r8d
0x18001d6bc  ror     ecx, 10h
0x18001d6bf  mov     [r14+1], cl
0x18001d6c3  mov     ecx, r10d
0x18001d6c6  ror     ecx, 10h
0x18001d6c9  mov     [r14+5], cl
0x18001d6cd  mov     ecx, r8d
0x18001d6d0  ror     ecx, 18h
0x18001d6d3  mov     [r14], cl
0x18001d6d6  mov     ecx, r10d
0x18001d6d9  ror     ecx, 18h
0x18001d6dc  mov     [r14+4], cl
0x18001d6e0  lea     r14, [r14+8]
0x18001d6e4  sub     r15, 1
0x18001d6e8  jnz     loc_18001D3E2
0x18001d6ee  mov     rcx, r15
0x18001d6f1  lea     esi, [r15+1]
0x18001d6f5  mov     al, r15b
0x18001d6f8  xor     al, [rdi+rcx]
0x18001d6fb  add     rcx, rsi
0x18001d6fe  cmp     rcx, 338h
0x18001d705  jb      short loc_18001D6F8
0x18001d707  movzx   ecx, al
0x18001d70a  cmp     rcx, cs:qword_18002BA18
0x18001d711  jz      short loc_18001D781
0x18001d713  call    cs:__imp_GetProcessHeap
0x18001d719  mov     r8, rdi; lpMem
0x18001d71c  xor     edx, edx; dwFlags
0x18001d71e  mov     rcx, rax; hHeap
0x18001d721  call    cs:__imp_HeapFree
0x18001d727  lea     r13, off_18002F000
0x18001d72e  mov     r12d, 60h ; '`'
0x18001d734  lea     r14, qword_18002F860
0x18001d73b  mov     rbx, r15
0x18001d73e  lea     rax, [rbx+rbx*2]
0x18001d742  mov     rcx, [r14+rax*8]; hLibModule
0x18001d746  test    rcx, rcx
0x18001d749  jz      short loc_18001D751
0x18001d74b  call    cs:__imp_FreeLibrary
0x18001d751  add     rbx, rsi
0x18001d754  cmp     rbx, 4
0x18001d758  jnz     short loc_18001D73E
0x18001d75a  mov     r8, r12; Size
0x18001d75d  xor     edx, edx; Val
0x18001d75f  mov     rcx, r14; void *
0x18001d762  call    memset_0
0x18001d767  mov     r8d, 170h; Size
0x18001d76d  lea     rdx, off_180028410; Src
0x18001d774  mov     rcx, r13; void *
0x18001d777  call    memcpy_0
0x18001d77c  jmp     loc_18001D90E
0x18001d781  xor     edx, edx; Val
0x18001d783  mov     dword ptr [rbp+0DC0h+Size], r15d
0x18001d787  lea     r14, qword_18002F860
0x18001d78e  mov     [rdi+337h], r15b
0x18001d795  mov     rcx, r14; void *
0x18001d798  mov     r12d, r15d
0x18001d79b  lea     r8d, [rdx+60h]; Size
  ... truncated ...
```
