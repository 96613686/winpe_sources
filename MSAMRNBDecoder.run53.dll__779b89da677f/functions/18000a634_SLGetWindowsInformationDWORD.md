# SLGetWindowsInformationDWORD

- ea: `0x18000a634`
- end: `0x180013717`
- name: `SLGetWindowsInformationDWORD`
- size: `37091`
- prototype: `HRESULT __stdcall(PCWSTR pwszValueName, DWORD *pdwValue)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800029b4`

## callees

- `0x180001400`
- `0x180001f66`
- `0x18000a420`
- `0x18000a44c`
- `0x18000a478`
- `0x18000a4bc`
- `0x18000a4e8`
- `0x18000a520`
- `0x18000a59c`
- `0x18000a5dc`
- `0x18000a634`
- `0x180013720`
- `0x1800137f9`
- `0x180013811`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ab99`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c1bc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000da05`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000dfe1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800115c4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012660`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ab99`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c1bc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000da05`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000dfe1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800115c4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012660`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000d43a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000d43a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000aaf5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000c14e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000d94a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000df26`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180011503`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180012625`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000aaf5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000c14e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000d94a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000df26`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180011503`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180012625`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000aa6f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000d8a1`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000de80`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000f48e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000f876`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180011464`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180011702`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001362c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000aa6f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000d8a1`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000de80`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000f48e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000f876`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180011464`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180011702`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001362c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ac81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000acdc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000add1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aec0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c158`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d44c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d47a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e0f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e17d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e212`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e985`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eab1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ec60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ed40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eff4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f075`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f6dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fa06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ff54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001035e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800104de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800105db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010703`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010b38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010c27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001262f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ac81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000acdc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000add1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aec0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c158`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d44c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d47a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e0f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e17d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e212`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e985`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eab1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ec60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ed40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eff4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f075`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f6dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fa06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ff54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001035e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800104de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800105db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010703`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010b38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010c27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001262f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ad7b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ad7b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000ae9c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000ae9c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000aa45`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ac16`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b4fc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b519`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ba5a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bacf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bb00`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bb2c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bb58`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bb79`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bcf0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bd1f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bd4e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bd71`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bf3d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c51f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c54b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c577`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c598`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c63d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c66a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c697`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c6b8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cf29`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cf5b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cf88`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cfb5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cfd6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cff4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d012`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d044`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d071`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d09e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d0bf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d0dd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d3e6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d3ff`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000da83`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e05f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011642`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800119e8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011a01`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011f47`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011fb7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011fe6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012012`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001203e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001205f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800121d5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012204`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012233`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012256`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001248d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800129b1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800129e0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012a0f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012a32`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012ae5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012b13`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012b41`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012b62`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800133cd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800133f3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180013416`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180013439`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180013455`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180013472`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001348f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800134b5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800134d8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800134fb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180013517`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180013534`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800135b5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800135d9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000aa45`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ac16`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b4fc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b519`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ba5a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bacf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bb00`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bb2c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bb58`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bb79`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bcf0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bd1f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bd4e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bd71`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bf3d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c51f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c54b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c577`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c598`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c63d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c66a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c697`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c6b8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cf29`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cf5b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cf88`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cfb5`

## string_xrefs

- `0x18000c117`: `ntdll.dll`
- `0x180012611`: `ntdll.dll`

## pseudocode

```c
HRESULT __stdcall SLGetWindowsInformationDWORD(PCWSTR pwszValueName, DWORD *pdwValue)
{
  __int64 v2; // r8
  __int64 v3; // r9
  HRESULT v4; // ebx
  int v5; // eax
  HANDLE ProcessHeap; // rax
  _BYTE *v7; // rax
  _BYTE *v8; // rdi
  _BYTE *v9; // r14
  unsigned __int8 *v10; // rsi
  int v11; // r12d
  int v12; // r10d
  int v13; // r8d
  __int64 v14; // r15
  int v15; // r13d
  int v16; // ecx
  int v17; // ebx
  int v18; // r11d
  int v19; // ebx
  int v20; // edx
  int v21; // r11d
  unsigned int v22; // r8d
  int v23; // r9d
  unsigned int v24; // edx
  int v25; // r10d
  int v26; // r8d
  unsigned int v27; // r9d
  int v28; // r10d
  int v29; // edx
  int v30; // r8d
  unsigned int v31; // r9d
  int v32; // edx
  int v33; // r8d
  unsigned int v34; // r10d
  unsigned int v35; // r8d
  int v36; // r9d
  int v37; // edx
  unsigned int v38; // r8d
  int v39; // r9d
  int v40; // edx
  int v41; // r8d
  unsigned int v42; // r9d
  int v43; // r10d
  int v44; // ecx
  unsigned __int64 v45; // rcx
  char v46; // al
  HANDLE v47; // rax
  __int64 i; // rbx
  HMODULE v49; // rcx
  unsigned int v50; // r12d
  void *v51; // r13
  __int64 v52; // rbx
  HMODULE *v53; // r14
  _BYTE *v54; // rdi
  int v55; // ebx
  __int64 v56; // rax
  char *v57; // rdx
  unsigned int v58; // eax
  __int64 v59; // rsi
  __int64 (__fastcall *ProcAddress)(); // rax
  HANDLE v61; // rax
  const wchar_t *v62; // rsi
  const wchar_t *v63; // r14
  int v64; // r12d
  int v65; // r13d
  __int64 v66; // r15
  signed int v67; // eax
  signed int v68; // ebx
  __int64 v69; // r9
  SIZE_T v70; // rdi
  SIZE_T v71; // r8
  signed int LastError; // eax
  unsigned int v73; // ebx
  HANDLE v74; // rax
  LPVOID v75; // rax
  __int64 (__fastcall *v76)(); // rbx
  DWORD CurrentThreadId; // eax
  __int64 v78; // r15
  __int64 v79; // r9
  SIZE_T v80; // rdi
  SIZE_T v81; // r8
  signed int v82; // eax
  unsigned int v83; // ebx
  HANDLE v84; // rax
  LPVOID v85; // rax
  HANDLE CurrentProcess; // rax
  int v87; // r12d
  HLOCAL v88; // rax
  __int128 v89; // rax
  unsigned __int64 v90; // r8
  unsigned __int64 i8; // r9
  HANDLE v92; // rax
  void *v93; // rdi
  int v94; // r15d
  int v95; // r13d
  HANDLE v96; // rax
  _QWORD *v97; // rax
  const wchar_t *v98; // rcx
  void *v99; // rbx
  unsigned __int64 v100; // r12
  unsigned int v101; // r10d
  unsigned int v102; // eax
  unsigned int v103; // eax
  char *v104; // r12
  unsigned int v105; // ecx
  unsigned int v106; // ecx
  __int64 v107; // r15
  HANDLE v108; // rax
  int v109; // ecx
  void *v110; // r10
  const wchar_t *v111; // rcx
  int v112; // r15d
  unsigned int v113; // r10d
  unsigned int v114; // ecx
  unsigned __int64 v115; // r11
  unsigned int v116; // ecx
  unsigned int v117; // r10d
  unsigned int v118; // r11d
  unsigned int v119; // ecx
  WCHAR *v120; // rcx
  unsigned int v121; // r10d
  unsigned int i7; // ecx
  unsigned int v123; // eax
  HANDLE v124; // rax
  void *v125; // r12
  HANDLE v126; // rax
  unsigned int v127; // ecx
  unsigned int v128; // eax
  size_t v129; // rax
  unsigned int v130; // r15d
  HANDLE v131; // rax
  const void *v132; // r10
  char *v133; // r15
  _DWORD *v134; // rdx
  unsigned int v135; // eax
  _BYTE *v136; // rdx
  unsigned __int8 v137; // al
  unsigned __int64 v138; // r8
  unsigned __int8 *v139; // rdi
  int v140; // r9d
  LPCWSTR v141; // r14
  int v142; // r8d
  int v143; // r15d
  unsigned int v144; // r13d
  _BYTE *v145; // r12
  int v146; // r10d
  int v147; // ecx
  int v148; // ebx
  int v149; // r11d
  int v150; // ebx
  int v151; // r11d
  int v152; // edx
  int v153; // r8d
  int v154; // r10d
  int v155; // r8d
  int v156; // r10d
  int v157; // r9d
  int v158; // r8d
  unsigned int v159; // edx
  int v160; // r9d
  int v161; // ecx
  int v162; // edx
  int v163; // r8d
  int v164; // r9d
  int v165; // edx
  unsigned int v166; // r8d
  unsigned int v167; // r9d
  int v168; // edx
  int v169; // r8d
  int v170; // r9d
  unsigned int v171; // edx
  int v172; // r8d
  int v173; // r10d
  int v174; // edx
  int v175; // r9d
  unsigned int v176; // r8d
  unsigned int v177; // r10d
  int v178; // edx
  unsigned int v179; // r9d
  HANDLE v180; // rax
  HANDLE v181; // rax
  int v182; // r15d
  void *v183; // rax
  HANDLE v184; // rax
  HANDLE v185; // rax
  HANDLE v186; // rax
  HANDLE v187; // rax
  HANDLE v188; // rax
  _DWORD *v189; // rcx
  SIZE_T v190; // r15
  HANDLE v191; // rax
  void *v192; // rax
  HANDLE v193; // rax
  _OWORD *v194; // rax
  HANDLE v195; // rax
  _QWORD *v196; // rax
  SIZE_T v197; // rax
  HANDLE v198; // rax
  HANDLE v199; // rax
  HANDLE v200; // rax
  HANDLE v201; // rax
  unsigned int v202; // eax
  unsigned int v203; // ebx
  HANDLE v204; // rax
  void *v205; // rcx
  const void **v206; // rbx
  unsigned __int64 v207; // r15
  _DWORD *v208; // rcx
  unsigned int *v209; // rdx
  _DWORD *v210; // r15
  _DWORD *v211; // rcx
  _DWORD *v212; // r15
  HANDLE v213; // rax
  int v214; // r11d
  unsigned __int64 v215; // r10
  void *v216; // r15
  unsigned int v217; // eax
  unsigned int v218; // ebx
  HANDLE v219; // rax
  signed int v220; // eax
  FARPROC v221; // rax
  int v222; // eax
  SIZE_T v223; // r15
  char *v224; // rcx
  char *v225; // r11
  _DWORD *v226; // rcx
  unsigned int v227; // r11d
  unsigned __int64 v228; // r10
  unsigned int v229; // ecx
  unsigned int v230; // r10d
  unsigned int v231; // ecx
  HANDLE v232; // rax
  size_t v233; // rbx
  void *v234; // rdi
  HANDLE v235; // rax
  size_t v236; // r12
  void *v237; // rax
  int v238; // r15d
  const void *v239; // rdi
  HANDLE v240; // rax
  size_t v241; // r12
  void *v242; // rax
  unsigned int v243; // eax
  size_t v244; // r12
  HANDLE v245; // rax
  void *v246; // rax
  size_t v247; // rax
  HANDLE v248; // rax
  HANDLE v249; // rax
  HANDLE v250; // rax
  HANDLE v251; // rax
  LPCWSTR *v252; // rcx
  HANDLE v253; // rax
  HANDLE v254; // rax
  HANDLE v255; // rax
  HANDLE v256; // rax
  void *v257; // r15
  _DWORD *v258; // r11
  unsigned __int8 v259; // al
  unsigned int v260; // r10d
  unsigned int v261; // esi
  int v262; // r13d
  int v263; // eax
  unsigned __int8 *v264; // r14
  int v265; // ecx
  unsigned int v266; // r8d
  unsigned int v267; // r9d
  unsigned int v268; // r15d
  int v269; // ecx
  unsigned int v270; // edx
  WCHAR *v271; // r14
  char v272; // si
  int v273; // r9d
  SIZE_T v274; // r15
  int v275; // r11d
  SIZE_T v276; // r13
  unsigned __int8 *v277; // rsi
  _BYTE *v278; // r15
  int v279; // r12d
  int v280; // r10d
  int v281; // eax
  int v282; // ecx
  int v283; // edi
  int v284; // ebx
  int v285; // edi
  int v286; // edx
  int v287; // ebx
  unsigned int v288; // r8d
  int v289; // r9d
  unsigned int v290; // edx
  int v291; // r8d
  int v292; // r9d
  unsigned int v293; // edx
  int v294; // r8d
  int v295; // r10d
  int v296; // r11d
  unsigned int v297; // r9d
  int v298; // r8d
  unsigned int v299; // r9d
  int v300; // r10d
  int v301; // r11d
  int v302; // edx
  int v303; // r8d
  unsigned int v304; // r9d
  int v305; // edx
  int v306; // r10d
  int v307; // r8d
  unsigned int v308; // r9d
  int v309; // edx
  int v310; // r8d
  SIZE_T k; // rcx
  int v312; // r15d
  size_t v313; // rax
  _DWORD *v314; // r15
  unsigned int v315; // eax
  HANDLE v316; // rax
  HANDLE v317; // rax
  LPVOID v318; // rax
  HANDLE v319; // rax
  HANDLE v320; // rax
  HANDLE v321; // rax
  HANDLE v322; // rax
  HANDLE v323; // rax
  HANDLE v324; // rax
  LPVOID v325; // rax
  HANDLE v326; // rax
  HANDLE v327; // rax
  HANDLE v328; // rax
  HANDLE v329; // rax
  HANDLE v330; // rax
  int *v331; // r15
  int v332; // r15d
  unsigned int v333; // r11d
  HANDLE v334; // rax
  HANDLE v335; // rax
  DWORD ModuleFileNameW; // eax
  __int64 v337; // rax
  unsigned int v338; // edi
  int v339; // eax
  _BYTE *v340; // rax
  _BYTE *v341; // r12
  _BYTE *v342; // rsi
  unsigned __int8 *v343; // r14
  __int64 v344; // r15
  int v345; // edi
  int v346; // r13d
  int v347; // r10d
  int v348; // r8d
  int v349; // ecx
  int v350; // ebx
  int v351; // r11d
  int v352; // ebx
  int v353; // edx
  int v354; // r11d
  unsigned int v355; // r8d
  int v356; // r9d
  unsigned int v357; // r10d
  int v358; // edx
  int v359; // r8d
  unsigned int v360; // r9d
  int v361; // r10d
  int v362; // edx
  int v363; // r8d
  unsigned int v364; // r9d
  int v365; // edx
  int v366; // r8d
  unsigned int v367; // r10d
  unsigned int v368; // r8d
  int v369; // r9d
  int v370; // edx
  unsigned int v371; // r8d
  int v372; // r9d
  int v373; // edx
  int v374; // r8d
  unsigned int v375; // r9d
  int v376; // r10d
  int v377; // ecx
  unsigned __int64 v378; // rcx
  char v379; // al
  __int64 m; // rbx
  HMODULE v381; // rcx
  __int64 v382; // rax
  __int64 v383; // rbx
  SIZE_T v384; // r8
  _BYTE *v385; // r12
  __int64 v386; // rax
  int v387; // ebx
  __int64 v388; // rax
  unsigned __int64 v389; // rdx
  int v390; // eax
  unsigned int v391; // ecx
  __int64 v392; // rax
  __int64 (__fastcall *v393)(); // rax
  HANDLE v394; // rax
  int v395; // eax
  const WCHAR *v396; // rax
  WCHAR *v397; // rsi
  unsigned __int8 *v398; // r14
  int v399; // eax
  __int64 v400; // r15
  int v401; // edi
  int v402; // r10d
  int v403; // r8d
  int v404; // ecx
  int v405; // ebx
  int v406; // r11d
  int v407; // ebx
  int v408; // edx
  int v409; // r11d
  unsigned int v410; // r8d
  int v411; // r9d
  unsigned int v412; // edx
  int v413; // r10d
  int v414; // r8d
  unsigned int v415; // r9d
  int v416; // r10d
  int v417; // edx
  int v418; // r8d
  unsigned int v419; // r9d
  int v420; // edx
  int v421; // r8d
  unsigned int v422; // r10d
  unsigned int v423; // r8d
  int v424; // r9d
  int v425; // edx
  unsigned int v426; // r8d
  int v427; // r9d
  int v428; // edx
  int v429; // r8d
  unsigned int v430; // r9d
  int v431; // r10d
  int v432; // ecx
  unsigned __int64 v433; // rcx
  WCHAR *v434; // r12
  char v435; // al
  __int64 n; // rbx
  HMODULE v437; // rcx
  __int64 v438; // rax
  __int64 v439; // rbx
  SIZE_T v440; // r8
  WCHAR *v441; // r12
  __int64 v442; // rax
  int v443; // ebx
  __int64 v444; // rax
  unsigned __int64 v445; // rdx
  int v446; // eax
  unsigned int v447; // ecx
  __int64 v448; // rax
  __int64 (__fastcall *v449)(); // rax
  HANDLE v450; // rax
  signed int v451; // eax
  signed int v452; // ebx
  bool v453; // sf
  void *v454; // rax
  char *v455; // r12
  void *v456; // rax
  bool v457; // sf
  WCHAR *v458; // rsi
  unsigned int i6; // r14d
  __int64 v460; // rax
  _DWORD *v461; // rax
  unsigned int v462; // r10d
  unsigned int v463; // edx
  unsigned int i1; // ecx
  __int64 v465; // r12
  __int64 v466; // rcx
  const wchar_t *v467; // rcx
  __int64 i2; // rdx
  __int64 v469; // rax
  _BYTE *v470; // rax
  _BYTE *v471; // r12
  __int64 v472; // rcx
  unsigned __int8 *v473; // rbx
  _BYTE *v474; // rsi
  int v475; // r15d
  int v476; // edi
  int v477; // r8d
  int v478; // edx
  __int64 v479; // r14
  int v480; // eax
  int v481; // r11d
  int v482; // r10d
  int v483; // r11d
  int v484; // ecx
  int v485; // r10d
  unsigned int v486; // edx
  int v487; // r8d
  unsigned int v488; // r9d
  int v489; // ecx
  int v490; // edx
  unsigned int v491; // r8d
  int v492; // r9d
  int v493; // ecx
  int v494; // edx
  unsigned int v495; // r8d
  int v496; // ecx
  int v497; // edx
  unsigned int v498; // r9d
  unsigned int v499; // edx
  int v500; // r8d
  int v501; // ecx
  unsigned int v502; // edx
  int v503; // r8d
  int v504; // ecx
  int v505; // edx
  unsigned int v506; // r8d
  int v507; // ecx
  int v508; // edx
  unsigned __int64 v509; // rax
  __m128 v510; // xmm1
  __m128 v511; // xmm0
  __m128 v512; // xmm0
  __m128 v513; // xmm1
  __m128 v514; // xmm1
  __m128 v515; // xmm1
  int v516; // r8d
  unsigned int v517; // edx
  unsigned int i3; // ecx
  __int64 v519; // rax
  void *v520; // rax
  void **v521; // r12
  unsigned int v522; // ecx
  unsigned int v523; // eax
  __int64 v524; // rdx
  __int64 v525; // rax
  __int64 v526; // r9
  int v527; // eax
  void *v528; // rax
  __int64 v529; // r9
  signed int v530; // eax
  __int64 i4; // r14
  _BYTE *v532; // rax
  __int64 v533; // rcx
  __int64 i5; // rcx
  _BYTE *v535; // rax
  signed int v536; // eax
  int v537; // r12d
  int v538; // eax
  int v539; // eax
  unsigned int v540; // ebx
  const WCHAR *v541; // rax
  int v542; // eax
  unsigned __int64 v543; // rdx
  __int64 v544; // rax
  bool v545; // sf
  const unsigned __int16 *v546; // rbx
  int v547; // eax
  unsigned __int64 v548; // rdx
  __int64 v549; // rax
  bool v550; // sf
  unsigned int v551; // ecx
  unsigned int v552; // eax
  int v553; // eax
  void *v554; // rbx
  void *v555; // rbx
  unsigned int v556; // ebx
  __int64 v557; // rdx
  signed int v558; // eax
  int v559; // eax
  unsigned __int64 v560; // rdx
  __int64 v561; // rax
  bool v562; // sf
  void *v563; // rbx
  unsigned int v564; // ebx
  int v565; // eax
  int v566; // ebx
  int v567; // r12d
  int v568; // r12d
  __int64 v569; // rax
  int v570; // r12d
  __int64 v571; // rax
  int v572; // edx
  int v573; // eax
  HMODULE v574; // rcx
  unsigned int v575; // ebx
  __int64 v576; // rax
  int v577; // eax
  int v578; // edi
  int v579; // r12d
  LPVOID v580; // rbx
  int v581; // eax
  __int64 v582; // rax
  _BYTE *v583; // rax
  __int64 v584; // rcx
  __int64 ii; // rcx
  _BYTE *v586; // rax
  __int64 v587; // rcx
  __int64 jj; // rcx
  _BYTE *v589; // rcx
  __int64 v590; // rax
  __int64 v591; // rax
  int v592; // eax
  __int64 kk; // rbx
  HMODULE v594; // rcx
  int v595; // ebx
  SIZE_T v596; // r12
  size_t v597; // rbx
  SIZE_T v598; // rax
  signed int v599; // eax
  signed int v600; // edi
  int v601; // ebx
  int v602; // eax
  void *v603; // rax
  __int64 (__fastcall *v604)(); // rbx
  __int64 v605; // rax
  int v606; // r11d
  int v607; // eax
  int v608; // r10d
  int v609; // r8d
  int v610; // r9d
  int v611; // ecx
  int v612; // edi
  unsigned __int8 v613; // r14
  int v614; // esi
  char *v615; // r15
  char *v616; // rax
  int v617; // r10d
  int v618; // r9d
  char v619; // di
  unsigned __int8 *v620; // r8
  _BYTE *v621; // r11
  char v622; // r15
  unsigned __int8 v623; // dl
  int v624; // r8d
  int v625; // r9d
  int v626; // edx
  int v627; // r8d
  int v628; // ecx
  LPVOID v629; // rbx
  __int64 v630; // rax
  SIZE_T v631; // rax
  SIZE_T v632; // rbx
  SIZE_T v633; // rax
  signed int v634; // eax
  void *v635; // rax
  __int64 (__fastcall *v636)(); // rbx
  __int64 v637; // rax
  int v638; // r12d
  int v639; // r10d
  int v640; // r8d
  int v641; // r9d
  int v642; // ecx
  int v643; // r11d
  int v644; // esi
  char *v645; // r14
  char *v646; // rax
  char v647; // bl
  int v648; // r9d
  char v649; // r15
  unsigned __int8 *v650; // r8
  unsigned __int8 v651; // r11
  _BYTE *v652; // r10
  unsigned __int8 v653; // dl
  int v654; // r8d
  int v655; // r9d
  int v656; // edx
  int v657; // r8d
  int v658; // ecx
  SIZE_T v659; // rdi
  SIZE_T v660; // rbx
  LPVOID v661; // r12
  char v662; // al
  int v663; // ebx
  int v664; // r9d
  int v665; // eax
  int v666; // r11d
  int v667; // r8d
  int v668; // edi
  SIZE_T v669; // rax
  __int64 v670; // rax
  size_t v671; // rcx
  int v672; // eax
  int v673; // ebx
  signed int v674; // edi
  const WCHAR *v675; // rax
  bool v676; // sf
  size_t v677; // rbx
  const WCHAR *v678; // rax
  __int64 (__fastcall *v679)(); // rbx
  __int64 v680; // rax
  size_t v681; // rbx
  int v682; // eax
  int v683; // edx
  int v684; // r9d
  int v685; // r11d
  int v686; // r10d
  int v687; // ecx
  int v688; // r8d
  __int64 v689; // r8
  unsigned __int8 v690; // si
  int v691; // r14d
  char *v692; // r15
  char *v693; // rax
  char v694; // bl
  int v695; // r9d
  unsigned __int8 *v696; // r8
  char v697; // r15
  _BYTE *v698; // r10
  unsigned __int8 v699; // dl
  int v700; // r8d
  int v701; // r9d
  int v702; // edx
  int v703; // r8d
  int v704; // ecx
  signed int v705; // edi
  __int64 v706; // rax
  int v707; // ebx
  void *v708; // rax
  bool v709; // sf
  size_t v710; // rbx
  unsigned int v711; // eax
  size_t v712; // rbx
  void *v713; // rax
  __int64 (__fastcall *v714)(); // rbx
  __int64 v715; // rax
  int v716; // r8d
  int v717; // edx
  int v718; // r10d
  int v719; // r9d
  int v720; // ecx
  int v721; // r11d
  int v722; // esi
  const WCHAR *v723; // r14
  _BYTE *v724; // rax
  char v725; // bl
  LPCWSTR v726; // r8
  char v727; // r15
  _BYTE *v728; // r10
  unsigned __int8 v729; // r11
  int v730; // r9d
  unsigned __int8 v731; // dl
  int v732; // r8d
  int v733; // r9d
  int v734; // edx
  int v735; // r8d
  int v736; // ecx
  bool v737; // zf
  int v738; // eax
  const WCHAR *v739; // rax
  int v740; // r8d
  WCHAR *v741; // r12
  unsigned __int8 *v742; // r15
  __int64 v743; // rax
  int v744; // esi
  int v745; // r14d
  int v746; // r10d
  int v747; // ecx
  int v748; // ebx
  int v749; // r11d
  int v750; // ebx
  int v751; // edx
  int v752; // r11d
  unsigned int v753; // r8d
  int v754; // r9d
  unsigned int v755; // r10d
  int v756; // edx
  int v757; // r8d
  unsigned int v758; // r9d
  int v759; // r10d
  int v760; // edx
  int v761; // r8d
  unsigned int v762; // r9d
  int v763; // edx
  int v764; // r8d
  unsigned int v765; // r10d
  unsigned int v766; // r8d
  int v767; // r9d
  int v768; // edx
  unsigned int v769; // r8d
  int v770; // r9d
  int v771; // edx
  int v772; // r8d
  unsigned int v773; // r9d
  int v774; // r10d
  int v775; // ecx
  WCHAR *v776; // rdi
  unsigned __int64 v777; // rcx
  char v778; // al
  __int64 mm; // rbx
  HMODULE v780; // rcx
  unsigned int v781; // r12d
  __int64 v782; // rbx
  size_t v783; // rax
  HMODULE *v784; // r12
  WCHAR *v785; // rdi
  size_t v786; // rcx
  int v787; // ebx
  __int64 v788; // rax
  char *v789; // rdx
  unsigned int v790; // edx
  unsigned int v791; // eax
  __int64 v792; // r12
  __int64 (__fastcall *v793)(); // rax
  int v794; // ecx
  HANDLE v795; // rax
  int v796; // eax
  __int64 nn; // rbx
  HMODULE v798; // rcx
  HANDLE v799; // rax
  char *v800; // rdi
  HANDLE v801; // rax
  _QWORD *v802; // rax
  void *v803; // rbx
  HANDLE v804; // rax
  int v805; // ecx
  unsigned int v806; // r10d
  char *v807; // rcx
  unsigned int v808; // eax
  char *v809; // r11
  char *v810; // r11
  HANDLE v811; // rax
  HANDLE v812; // rax
  int v813; // edi
  unsigned int v814; // ecx
  int v815; // r10d
  unsigned int v816; // r10d
  HANDLE v817; // rax
  char *v818; // rdx
  unsigned __int8 v819; // al
  unsigned __int64 v820; // r8
  int v821; // r8d
  LPVOID v822; // r14
  _BYTE *v823; // r13
  unsigned int v824; // r15d
  unsigned __int8 *v825; // rdi
  int v826; // eax
  int v827; // r9d
  int v828; // ecx
  int v829; // ebx
  int v830; // r11d
  int v831; // ebx
  int v832; // r11d
  int v833; // r8d
  int v834; // r10d
  int v835; // r8d
  int v836; // r10d
  int v837; // r9d
  int v838; // r8d
  unsigned int v839; // edx
  int v840; // r9d
  int v841; // ecx
  int v842; // edx
  int v843; // r8d
  int v844; // r9d
  int v845; // edx
  unsigned int v846; // r8d
  unsigned int v847; // r9d
  int v848; // edx
  int v849; // r8d
  int v850; // r9d
  int v851; // edx
  int v852; // r8d
  int v853; // r9d
  int v854; // edx
  int v855; // r8d
  unsigned int v856; // ecx
  int v857; // r9d
  int v858; // edx
  void *v859; // rsi
  HANDLE v860; // rax
  HANDLE v861; // rax
  _DWORD *v862; // rax
  void *v863; // rax
  HANDLE v864; // rax
  HANDLE v865; // rax
  HANDLE v866; // rax
  HANDLE v867; // rax
  HANDLE v868; // rax
  _DWORD *v869; // rcx
  HANDLE v870; // rax
  void *v871; // rcx
  SIZE_T v872; // rax
  HANDLE v873; // rax
  _OWORD *v874; // rcx
  HANDLE v875; // rax
  _QWORD *v876; // rax
  void *v877; // rcx
  HANDLE v878; // rax
  HANDLE v879; // rax
  HANDLE v880; // rax
  HANDLE v881; // rax
  SIZE_T v882; // rcx
  int v883; // eax
  unsigned int v884; // ebx
  HANDLE v885; // rax
  const void **v886; // rbx
  _DWORD *v887; // rcx
  unsigned int *v888; // rdx
  _DWORD *v889; // rcx
  int v890; // r10d
  HANDLE v891; // rax
  unsigned int v892; // eax
  unsigned int v893; // ebx
  HANDLE v894; // rax
  void *v895; // rax
  bool v896; // sf
  FARPROC v897; // rax
  char *v898; // rcx
  unsigned int v899; // r10d
  SIZE_T v900; // rcx
  unsigned int v901; // ecx
  unsigned int *v902; // rax
  unsigned int v903; // r11d
  unsigned int v904; // ecx
  HANDLE v905; // rax
  size_t v906; // rbx
  LPCWSTR v907; // rdi
  HANDLE v908; // rax
  size_t v909; // rsi
  void *v910; // rax
  const void *v911; // rdi
  HANDLE v912; // rax
  LPCWSTR v913; // rsi
  void *v914; // rax
  const void *v915; // rdi
  unsigned int v916; // eax
  size_t v917; // rsi
  HANDLE v918; // rax
  void *v919; // rax
  LPVOID v920; // rax
  void *v921; // rcx
  HANDLE v922; // rax
  HANDLE v923; // rax
  HANDLE v924; // rax
  HANDLE v925; // rax
  LPVOID *v926; // rcx
  int v927; // r9d
  HANDLE v928; // rax
  HANDLE v929; // rax
  HANDLE v930; // rax
  HANDLE v931; // rax
  WCHAR *v932; // r11
  unsigned __int8 v933; // al
  unsigned __int64 v934; // r10
  int v935; // r10d
  int v936; // eax
  int v937; // r15d
  unsigned __int8 *v938; // r14
  int v939; // ecx
  unsigned int v940; // edx
  _BYTE *v941; // rcx
  unsigned int v942; // r9d
  unsigned int v943; // r8d
  unsigned int v944; // r11d
  int v945; // r14d
  int v946; // eax
  char v947; // r15
  int v948; // r13d
  SIZE_T v949; // r15
  WCHAR *v950; // rsi
  int v951; // r12d
  unsigned int v952; // r10d
  int v953; // r11d
  unsigned __int8 *v954; // rax
  int v955; // ecx
  int v956; // edi
  int v957; // ebx
  int v958; // edi
  int v959; // edx
  int v960; // ebx
  int v961; // r8d
  int v962; // r9d
  unsigned int v963; // edx
  int v964; // r8d
  int v965; // r9d
  unsigned int v966; // edx
  int v967; // r8d
  int v968; // r10d
  int v969; // r11d
  unsigned int v970; // r9d
  int v971; // r8d
  unsigned int v972; // r9d
  int v973; // r10d
  int v974; // r11d
  int v975; // edx
  int v976; // r8d
  int v977; // r9d
  int v978; // edx
  int v979; // r10d
  int v980; // r8d
  unsigned int v981; // edx
  int v982; // r9d
  int v983; // r8d
  int v984; // ecx
  unsigned __int64 v985; // rcx
  void *v986; // r14
  SIZE_T v987; // r10
  SIZE_T v988; // r14
  SIZE_T v989; // r8
  char *v990; // r9
  LPCWSTR v991; // r9
  LPCWSTR v992; // r10
  int v993; // r14d
  unsigned __int64 v994; // rcx
  HANDLE v995; // rax
  size_t v996; // r14
  HANDLE v997; // rax
  _QWORD *v998; // rsi
  void *v999; // r14
  HANDLE v1000; // rax
  void *v1001; // r14
  HANDLE v1002; // rax
  void *v1003; // r14
  HANDLE v1004; // rax
  HANDLE v1005; // rax
  void *v1006; // rsi
  HANDLE v1007; // rax
  void *v1008; // rsi
  HANDLE v1009; // rax
  _QWORD *v1010; // rsi
  void *v1011; // r14
  HANDLE v1012; // rax
  void *v1013; // r14
  HANDLE v1014; // rax
  void *v1015; // r14
  HANDLE v1016; // rax
  HANDLE v1017; // rax
  void *v1018; // rsi
  HANDLE v1019; // rax
  int *v1020; // rax
  unsigned __int64 v1021; // rcx
  HANDLE v1022; // rax
  void *v1023; // rsi
  HANDLE v1024; // rax
  int v1025; // eax
  unsigned __int64 j; // rbx
  HMODULE v1027; // rcx
  int v1029; // [rsp+60h] [rbp-A0h]
  unsigned int v1030; // [rsp+60h] [rbp-A0h]
  unsigned int v1031; // [rsp+60h] [rbp-A0h]
  int v1032; // [rsp+60h] [rbp-A0h]
  int v1033; // [rsp+60h] [rbp-A0h]
  int v1034; // [rsp+60h] [rbp-A0h]
  unsigned __int8 v1035; // [rsp+64h] [rbp-9Ch]
  unsigned __int8 v1036; // [rsp+64h] [rbp-9Ch]
  int Src; // [rsp+68h] [rbp-98h]
  _BYTE *Srca; // [rsp+68h] [rbp-98h]
  const void *Srcb; // [rsp+68h] [rbp-98h]
  int Srcc; // [rsp+68h] [rbp-98h]
  int Srcd; // [rsp+68h] [rbp-98h]
  LPVOID v1042; // [rsp+70h] [rbp-90h]
  SIZE_T v1043; // [rsp+78h] [rbp-88h] BYREF
  LPVOID v1044; // [rsp+80h] [rbp-80h]
  SIZE_T v1045; // [rsp+88h] [rbp-78h] BYREF
  LPVOID v1046; // [rsp+90h] [rbp-70h]
  LPVOID v1047; // [rsp+98h] [rbp-68h] BYREF
  LPCWSTR lpModuleName; // [rsp+A0h] [rbp-60h]
  size_t pcchLength; // [rsp+A8h] [rbp-58h] BYREF
  LPVOID v1050; // [rsp+B0h] [rbp-50h]
  SIZE_T v1051; // [rsp+B8h] [rbp-48h]
  LPVOID v1052; // [rsp+C0h] [rbp-40h]
  size_t Size; // [rsp+C8h] [rbp-38h]
  SIZE_T v1054; // [rsp+D0h] [rbp-30h]
  LPVOID lpMem; // [rsp+D8h] [rbp-28h] BYREF
  size_t v1056; // [rsp+E0h] [rbp-20h]
  LPVOID v1057; // [rsp+E8h] [rbp-18h]
  LPVOID v1058; // [rsp+F0h] [rbp-10h]
  LPVOID v1059; // [rsp+F8h] [rbp-8h]
  LPVOID v1060; // [rsp+100h] [rbp+0h]
  char *v1061; // [rsp+108h] [rbp+8h] BYREF
  SIZE_T v1062; // [rsp+110h] [rbp+10h]
  SIZE_T v1063; // [rsp+118h] [rbp+18h] BYREF
  LPVOID v1064; // [rsp+120h] [rbp+20h] BYREF
  SIZE_T v1065; // [rsp+128h] [rbp+28h]
  SIZE_T v1066; // [rsp+130h] [rbp+30h] BYREF
  void *v1067; // [rsp+138h] [rbp+38h]
  int v1068; // [rsp+140h] [rbp+40h]
  SIZE_T v1069; // [rsp+148h] [rbp+48h]
  unsigned int v1070; // [rsp+150h] [rbp+50h] BYREF
  int v1071; // [rsp+154h] [rbp+54h]
  LPCWSTR v1072; // [rsp+158h] [rbp+58h]
  __int128 v1073; // [rsp+160h] [rbp+60h]
  SIZE_T v1074; // [rsp+170h] [rbp+70h]
  unsigned int dwBytes; // [rsp+178h] [rbp+78h] BYREF
  unsigned int dwBytes_4; // [rsp+17Ch] [rbp+7Ch] BYREF
  unsigned int v1077; // [rsp+180h] [rbp+80h] BYREF
  __int64 v1078; // [rsp+188h] [rbp+88h]
  int v1079; // [rsp+190h] [rbp+90h] BYREF
  _BYTE *v1080; // [rsp+198h] [rbp+98h] BYREF
  unsigned int *v1081; // [rsp+1A0h] [rbp+A0h] BYREF
  HMODULE phModule; // [rsp+1A8h] [rbp+A8h] BYREF
  HMODULE hModule; // [rsp+1B0h] [rbp+B0h] BYREF
  void *v1084; // [rsp+1B8h] [rbp+B8h]
  __int128 v1085; // [rsp+1C0h] [rbp+C0h] BYREF
  __int128 v1086; // [rsp+1D0h] [rbp+D0h]
  __int128 v1087; // [rsp+1E0h] [rbp+E0h] BYREF
  __int128 v1088; // [rsp+1F0h] [rbp+F0h]
  __int64 v1089; // [rsp+208h] [rbp+108h] BYREF
  __int64 v1090; // [rsp+210h] [rbp+110h] BYREF
  __int64 v1091; // [rsp+218h] [rbp+118h] BYREF
  __int64 v1092; // [rsp+220h] [rbp+120h] BYREF
  __int64 v1093; // [rsp+228h] [rbp+128h] BYREF
  DWORD *v1094; // [rsp+230h] [rbp+130h]
  __int128 v1095; // [rsp+238h] [rbp+138h] BYREF
  _OWORD v1096[3]; // [rsp+288h] [rbp+188h] BYREF
  _QWORD v1097[20]; // [rsp+2C0h] [rbp+1C0h] BYREF
  int v1098; // [rsp+360h] [rbp+260h] BYREF
  int v1099; // [rsp+364h] [rbp+264h]
  void *v1100; // [rsp+368h] [rbp+268h]
  void *v1101; // [rsp+370h] [rbp+270h]
  void *v1102; // [rsp+378h] [rbp+278h]
  WCHAR *v1103; // [rsp+380h] [rbp+280h]
  const WCHAR *v1104; // [rsp+388h] [rbp+288h]
  __int64 v1105; // [rsp+390h] [rbp+290h]
  int v1106; // [rsp+398h] [rbp+298h]
  int v1107; // [rsp+39Ch] [rbp+29Ch] BYREF
  int v1108; // [rsp+3A0h] [rbp+2A0h]
  int v1109; // [rsp+3A4h] [rbp+2A4h]
  int v1110; // [rsp+3A8h] [rbp+2A8h]
  int v1111; // [rsp+3ACh] [rbp+2ACh] BYREF
  int v1112; // [rsp+3B0h] [rbp+2B0h]
  int v1113; // [rsp+3B4h] [rbp+2B4h]
  unsigned int v1114; // [rsp+3B8h] [rbp+2B8h]
  unsigned int v1115; // [rsp+3BCh] [rbp+2BCh] BYREF
  unsigned int v1116; // [rsp+3C0h] [rbp+2C0h]
  unsigned int v1117; // [rsp+3C4h] [rbp+2C4h]
  unsigned int v1118; // [rsp+3C8h] [rbp+2C8h]
  int v1119; // [rsp+3D0h] [rbp+2D0h] BYREF
  _DWORD v1120[3]; // [rsp+3D4h] [rbp+2D4h] BYREF
  __int16 v1121; // [rsp+3E2h] [rbp+2E2h]
  __int64 v1122; // [rsp+3E8h] [rbp+2E8h]
  int v1123; // [rsp+440h] [rbp+340h] BYREF
  _DWORD v1124[5]; // [rsp+444h] [rbp+344h] BYREF
  SIZE_T v1125; // [rsp+458h] [rbp+358h]
  int v1126; // [rsp+4B0h] [rbp+3B0h] BYREF
  _DWORD v1127[5]; // [rsp+4B4h] [rbp+3B4h] BYREF
  size_t v1128; // [rsp+4C8h] [rbp+3C8h]
  int v1129; // [rsp+520h] [rbp+420h] BYREF
  _DWORD v1130[5]; // [rsp+524h] [rbp+424h] BYREF
  SIZE_T v1131; // [rsp+538h] [rbp+438h]
  int v1132; // [rsp+590h] [rbp+490h] BYREF
  _DWORD v1133[5]; // [rsp+594h] [rbp+494h] BYREF
  SIZE_T v1134; // [rsp+5A8h] [rbp+4A8h]
  int v1135; // [rsp+600h] [rbp+500h] BYREF
  char v1136[20]; // [rsp+604h] [rbp+504h] BYREF
  SIZE_T v1137; // [rsp+618h] [rbp+518h]
  int v1138; // [rsp+670h] [rbp+570h] BYREF
  char v1139[20]; // [rsp+674h] [rbp+574h] BYREF
  SIZE_T v1140; // [rsp+688h] [rbp+588h]
  int v1141; // [rsp+6E0h] [rbp+5E0h] BYREF
  char v1142[20]; // [rsp+6E4h] [rbp+5E4h] BYREF
  SIZE_T v1143; // [rsp+6F8h] [rbp+5F8h]
  int v1144; // [rsp+750h] [rbp+650h] BYREF
  char v1145[20]; // [rsp+754h] [rbp+654h] BYREF
  const WCHAR *v1146; // [rsp+768h] [rbp+668h]
  __int128 v1147; // [rsp+7C0h] [rbp+6C0h] BYREF
  __int128 v1148; // [rsp+7D0h] [rbp+6D0h] BYREF
  __int128 v1149; // [rsp+7E0h] [rbp+6E0h] BYREF
  __int128 v1150; // [rsp+7F0h] [rbp+6F0h] BYREF
  __int64 v1151; // [rsp+800h] [rbp+700h] BYREF
  int v1152; // [rsp+808h] [rbp+708h]
  int v1153; // [rsp+80Ch] [rbp+70Ch]
  _DWORD v1154[12]; // [rsp+810h] [rbp+710h] BYREF
  __int128 v1155; // [rsp+840h] [rbp+740h] BYREF
  __int128 v1156; // [rsp+850h] [rbp+750h] BYREF
  __int64 v1157; // [rsp+860h] [rbp+760h]
  __int128 v1158; // [rsp+868h] [rbp+768h] BYREF
  _OWORD v1159[2]; // [rsp+878h] [rbp+778h] BYREF
  __int128 v1160; // [rsp+898h] [rbp+798h] BYREF
  _OWORD v1161[2]; // [rsp+8A8h] [rbp+7A8h] BYREF
  __int128 v1162; // [rsp+8C8h] [rbp+7C8h] BYREF
  _OWORD v1163[2]; // [rsp+8D8h] [rbp+7D8h] BYREF
  __int128 v1164; // [rsp+8F8h] [rbp+7F8h] BYREF
  _OWORD v1165[2]; // [rsp+908h] [rbp+808h] BYREF
  __int128 v1166; // [rsp+928h] [rbp+828h] BYREF
  __int128 v1167; // [rsp+938h] [rbp+838h] BYREF
  __int64 v1168; // [rsp+948h] [rbp+848h]
  _OWORD v1169[2]; // [rsp+950h] [rbp+850h] BYREF
  _DWORD v1170[6]; // [rsp+970h] [rbp+870h] BYREF
  char v1171; // [rsp+98Ah] [rbp+88Ah]
  unsigned __int16 v1172[34]; // [rsp+98Ch] [rbp+88Ch] BYREF
  _DWORD v1173[6]; // [rsp+9D0h] [rbp+8D0h] BYREF
  char v1174; // [rsp+9EAh] [rbp+8EAh]
  unsigned __int16 v1175[34]; // [rsp+9ECh] [rbp+8ECh] BYREF
  _DWORD v1176[6]; // [rsp+A30h] [rbp+930h] BYREF
  char v1177; // [rsp+A4Ah] [rbp+94Ah]
  unsigned __int16 v1178[34]; // [rsp+A4Ch] [rbp+94Ch] BYREF
  _BYTE v1179[68]; // [rsp+A90h] [rbp+990h] BYREF
  __int16 v1180; // [rsp+AD4h] [rbp+9D4h]
  unsigned __int16 v1181; // [rsp+B36h] [rbp+A36h]
  int v1182; // [rsp+B3Ch] [rbp+A3Ch]
  int v1183; // [rsp+B40h] [rbp+A40h]
  int v1184; // [rsp+B70h] [rbp+A70h] BYREF
  __int128 v1185; // [rsp+B78h] [rbp+A78h]
  __int128 v1186; // [rsp+B88h] [rbp+A88h]
  __int128 v1187; // [rsp+B98h] [rbp+A98h]
  __int64 v1188; // [rsp+BA8h] [rbp+AA8h]
  _BYTE v1189[176]; // [rsp+BB0h] [rbp+AB0h] BYREF
  WCHAR Filename[264]; // [rsp+C60h] [rbp+B60h] BYREF

  v1094 = pdwValue;
  v1081 = 0;
  if ( pdwValue )
  {
    LODWORD(v1056) = 0;
    v1063 = 0;
    while ( _InterlockedCompareExchange(&dword_180021534, 1, 0) )
      ;
    v5 = dword_180021530;
    v1071 = -1;
    if ( dword_180021530 )
      goto LABEL_46;
    ProcessHeap = GetProcessHeap();
    v7 = HeapAlloc(ProcessHeap, 0, 0x338u);
    v8 = v7;
    if ( !v7 )
      goto LABEL_13;
    v9 = v7;
    v10 = (unsigned __int8 *)&unk_18001E940;
    v11 = 0;
    v12 = 0;
    v13 = 0;
    v14 = 103;
    v15 = -1;
    do
    {
      v16 = *v10 << 8;
      v17 = v10[1];
      v18 = v10[4];
      v10 += 8;
      v19 = *(v10 - 5) | ((*(v10 - 6) | ((v16 | v17) << 8)) << 8);
      v20 = v13 ^ v19;
      v21 = *(v10 - 1) | ((*(v10 - 2) | ((*(v10 - 3) | (v18 << 8)) << 8)) << 8);
      v22 = v12 ^ v21 ^ v13 ^ v19 ^ 0xAC987321;
      v23 = v20 ^ (__ROR4__(v22, 22) + 4991 * __ROR4__(v22 + 1419157410, 27));
      v24 = v22 ^ (43881 * __ROR4__(v23 + 133239679, 9) - __ROR4__(v23, 30));
      v25 = v23 ^ (24670 * v24 - (v24 >> 13) - 123127970);
      v26 = v24 ^ (2033 * __ROR4__(v25 ^ 0xAB69, 26) - __ROR4__(v25, 30));
      v27 = v25 ^ (133239679 - (v26 ^ 0xAB69605E));
      v28 = v26 ^ (43881 * (v27 ^ 0x137F)) ^ __ROR4__(v27, 6);
      v29 = v27 ^ (__ROR4__(v28, 30) + 24670 * __ROR4__(v28 + 133239679, 15));
      v30 = v28 ^ (2033 * __ROR4__(v29 + 1419157410, 14) - __ROR4__(v29, 24));
      v31 = v29 ^ __ROR4__(v30, 10) ^ (4991 * __ROR4__(v30 ^ 0xAB69605E, 12));
      v32 = v30 ^ (v31 >> 10) ^ (43881 * (v31 ^ 0x7F1));
      v33 = v31 ^ (2033 * (__ROR4__(~v32, 5) + 24670));
      v34 = v33 ^ (((v32 ^ (v33 - 2033) ^ 0xAB69605E) >> 2) + 4991 * __ROR4__(v32 ^ (v33 - 2033) ^ 0xAB6967AF, 30));
      v35 = v32 ^ (v33 - 2033) ^ 0xAB69605E ^ (__ROR4__(v34, 25) + 43881 * __ROR4__(v34 - 133239679, 6));
      v36 = v34 ^ (24670 * (v35 ^ 0x137F) + __ROR4__(v35, 9));
      v37 = v35 ^ (__ROR4__(v36, 25) + 2033 * __ROR4__(v36 ^ 0xAB69, 27));
      v38 = v36 ^ v37 ^ 0xAC987321;
      v39 = v37 ^ (4991 * __ROR4__(v38, 3) - 219010071);
      v40 = v38 ^ (24670 * __ROR4__(v39 - 133239679, 1) - __ROR4__(v39, 6));
      v41 = v39 ^ (__ROR4__(v40, 18) + 2033 * __ROR4__(v40 - 1419157410, 29));
      v42 = v40 ^ (4991 * __ROR4__(v41 - 1419157410, 17) - __ROR4__(v41, 14));
      v43 = v41 ^ (v42 >> 3) ^ (43881 * (v42 ^ 0x605E));
      v44 = __ROR4__(v43, 30);
      v12 = v15 ^ v43;
      v15 = v21;
      v13 = v11 ^ v42 ^ v44 ^ (24670 * __ROR4__(v41 ^ (v42 >> 3) ^ (43881 * (v42 ^ 0x605E)) ^ 0x7F1137F, 28));
      v11 = v19;
      v9[3] = v13;
      v9[7] = v12;
      v9[2] = __ROR4__(v13, 8);
      v9[6] = __ROR4__(v12, 8);
      v9[1] = __ROR4__(v13, 16);
      v9[5] = __ROR4__(v12, 16);
      *v9 = __ROR4__(v13, 24);
      v9[4] = __ROR4__(v12, 24);
      v9 += 8;
      --v14;
    }
    while ( v14 );
    v45 = 0;
    v46 = 0;
    do
      v46 ^= v8[v45++];
    while ( v45 < 0x338 );
    if ( v46 != 64 )
    {
      v47 = GetProcessHeap();
      HeapFree(v47, 0, v8);
      goto LABEL_13;
    }
    LODWORD(Size) = 0;
    v8[823] = 0;
    v50 = 0;
    memset_0(&unk_1800214D0, 0, 0x60u);
    v51 = v8;
    if ( *v8 )
    {
      while ( 1 )
      {
        v52 = -1;
        do
          ++v52;
        while ( *(_WORD *)&v8[2 * v52] );
        v53 = (HMODULE *)((char *)&unk_1800214D0 + 24 * v50);
        if ( !GetModuleHandleExW(0, (LPCWSTR)v8, v53) )
          break;
        v54 = &v8[2 * v52];
        if ( *(_WORD *)*v53 == 23117
          && (v56 = *((int *)*v53 + 15), (unsigned int)v56 < 0x10000000)
          && (v57 = (char *)*v53 + v56, v57 >= (char *)*v53)
          && *(_DWORD *)v57 == 17744 )
        {
          if ( ((*((_WORD *)v57 + 12) - 267) & 0xFEFF) != 0 )
          {
            v55 = -1073741811;
          }
          else
          {
            *(_QWORD *)((char *)&unk_1800214D0 + 24 * v50 + 12) = *((_QWORD *)v57 + 17);
            v55 = 0;
            *((_DWORD *)&unk_1800214D0 + 6 * v50 + 2) = *((_DWORD *)v57 + 20);
          }
        }
        else
        {
          v55 = -1073741701;
        }
        v58 = *(_DWORD *)(v54 + 2);
        v8 = v54 + 6;
        LODWORD(v1054) = v58;
        if ( v58 )
        {
          do
          {
            v59 = -1;
            do
              ++v59;
            while ( v8[v59] );
            if ( v55 >= 0 )
            {
              ProcAddress = GetProcAddress(*v53, v8);
              if ( !ProcAddress )
                goto LABEL_40;
              off_180021000[(unsigned int)Size] = ProcAddress;
              v58 = v1054;
            }
            v8 += v59 + 1;
            LODWORD(Size) = Size + 1;
            LODWORD(v14) = v14 + 1;
          }
          while ( (unsigned int)v14 < v58 );
        }
        ++v50;
        LODWORD(v14) = 0;
        if ( !*v8 )
          goto LABEL_40;
      }
      v55 = -1073741702;
LABEL_40:
      if ( !v51 )
        goto LABEL_44;
    }
    else
    {
      v55 = 0;
    }
    v61 = GetProcessHeap();
    HeapFree(v61, 0, v51);
LABEL_44:
    if ( v55 < 0 )
    {
LABEL_13:
      for ( i = 0; i != 4; ++i )
      {
        v49 = (HMODULE)*((_QWORD *)&unk_1800214D0 + 3 * i);
        if ( v49 )
          FreeLibrary(v49);
      }
      memset_0(&unk_1800214D0, 0, 0x60u);
      memcpy_0(off_180021000, off_180015170, 0x170u);
LABEL_47:
      v1043 = 0;
      _InterlockedExchange(&dword_180021534, 0);
      v62 = 0;
      v63 = 0;
      v1045 = 0;
      v64 = 0;
      if ( NtCurrentPeb()->SessionId )
      {
        v65 = 0;
        v66 = off_180021110[0]();
        if ( !v66 )
          goto LABEL_49;
        dwBytes = 0;
        v69 = 0;
        pcchLength = 0;
        v70 = 0;
        while ( 1 )
        {
          v71 = 0;
          if ( v70 )
            v71 = v70;
          if ( ((unsigned int (__fastcall *)(__int64, __int64, SIZE_T, __int64, unsigned int *))off_180021130[0])(
                 v66,
                 2,
                 v71,
                 v69,
                 &dwBytes) )
          {
            v1043 = v70;
            v68 = 0;
            v62 = (const wchar_t *)v70;
            goto LABEL_69;
          }
          LastError = GetLastError();
          v68 = LastError;
          if ( LastError != 122 )
            break;
          if ( v70 )
          {
            v68 = -2147467259;
            goto LABEL_70;
          }
          v73 = dwBytes;
          v74 = GetProcessHeap();
          v75 = HeapAlloc(v74, 0, v73);
          v70 = (SIZE_T)v75;
          if ( !v75 )
          {
            v68 = -2147024882;
LABEL_69:
            pcchLength = 0;
            goto LABEL_70;
          }
          v69 = dwBytes;
          pcchLength = (size_t)v75;
        }
        if ( LastError )
        {
          if ( LastError > 0 )
            v68 = (unsigned __int16)LastError | 0x80070000;
        }
        else
        {
          v68 = -2147467259;
        }
LABEL_70:
        SP_MEM<unsigned short *>::~SP_MEM<unsigned short *>(&pcchLength);
        if ( v68 < 0 )
          goto LABEL_98;
        v76 = off_180021128[0];
        CurrentThreadId = GetCurrentThreadId();
        v78 = ((__int64 (__fastcall *)(_QWORD))v76)(CurrentThreadId);
        if ( !v78 )
          goto LABEL_49;
        dwBytes_4 = 0;
        v79 = 0;
        pcchLength = 0;
        v80 = 0;
        while ( 1 )
        {
          v81 = 0;
          if ( v80 )
            v81 = v80;
          if ( ((unsigned int (__fastcall *)(__int64, __int64, SIZE_T, __int64, unsigned int *))off_180021130[0])(
                 v78,
                 2,
                 v81,
                 v79,
                 &dwBytes_4) )
          {
            v1045 = v80;
            v68 = 0;
            v63 = (const wchar_t *)v80;
            goto LABEL_87;
          }
          v82 = GetLastError();
          v68 = v82;
          if ( v82 != 122 )
            break;
          if ( v80 )
          {
            v68 = -2147467259;
            goto LABEL_88;
          }
          v83 = dwBytes_4;
          v84 = GetProcessHeap();
          v85 = HeapAlloc(v84, 0, v83);
          v80 = (SIZE_T)v85;
          if ( !v85 )
          {
            v68 = -2147024882;
LABEL_87:
            pcchLength = 0;
            goto LABEL_88;
          }
          v79 = dwBytes_4;
          pcchLength = (size_t)v85;
        }
        if ( v82 )
        {
          if ( v82 > 0 )
            v68 = (unsigned __int16)v82 | 0x80070000;
        }
        else
        {
          v68 = -2147467259;
        }
LABEL_88:
        SP_MEM<unsigned short *>::~SP_MEM<unsigned short *>(&pcchLength);
        if ( v68 < 0 )
          goto LABEL_98;
        if ( !v62 || wcscmp_0(v62, L"WinSta0") || !v63 || wcscmp_0(v63, L"Default") )
          goto LABEL_97;
        v1079 = 0;
        CurrentProcess = GetCurrentProcess();
        if ( !(unsigned int)GetProcessMitigationPolicy(CurrentProcess, 11, &v1079) )
        {
LABEL_49:
          v67 = GetLastError();
          v68 = v67;
          if ( v67 > 0 )
            v68 = (unsigned __int16)v67 | 0x80070000;
          if ( v68 >= 0 )
            v68 = -2147467259;
          goto LABEL_98;
        }
        if ( (v1079 & 0xF) == 0 )
          v64 = 1;
      }
      else
      {
        v68 = 0;
      }
LABEL_97:
      v65 = v64;
LABEL_98:
      SP_MEM<unsigned short *>::~SP_MEM<unsigned short *>(&v1045);
      SP_MEM<unsigned short *>::~SP_MEM<unsigned short *>(&v1043);
      v87 = 0;
      if ( v68 >= 0 )
        v87 = v65;
      v1029 = v87;
      v88 = LocalAlloc(0x40u, 4u);
      SP_HLOCAL<unsigned char>::operator=(&v1063, v88);
      v1084 = (void *)v1063;
      if ( !v1063 )
      {
        v94 = -2147024882;
        goto LABEL_1470;
      }
      v92 = GetProcessHeap();
      *(_QWORD *)&v89 = HeapAlloc(v92, 8u, 0xA0u);
      v93 = (void *)v89;
      if ( !(_QWORD)v89 )
      {
        v94 = -1073741801;
LABEL_1470:
        v100 = 0;
LABEL_1471:
        v813 = v1056;
LABEL_1472:
        while ( _InterlockedCompareExchange(&dword_180021534, 1, 0) )
          ;
        v1025 = dword_180021530;
        if ( dword_180021530 > 0 )
        {
          --dword_180021530;
          if ( v1025 == 1 )
          {
            for ( j = v100; j != 4; ++j )
            {
              v1027 = (HMODULE)*((_QWORD *)&unk_1800214D0 + 3 * j);
              if ( v1027 )
                FreeLibrary(v1027);
            }
            memset_0(&unk_1800214D0, 0, 0x60u);
            memcpy_0(off_180021000, off_180015170, 0x170u);
          }
        }
        _InterlockedExchange(&dword_180021534, v100);
        SP_HLOCAL<unsigned char>::~SP_HLOCAL<unsigned char>(&v1063, *((_QWORD *)&v89 + 1), v90, i8);
        if ( v94 >= 0 )
        {
          if ( v813 == 4 )
          {
            v4 = v100;
            pdwValue = (DWORD *)*v1081;
            *v1094 = (unsigned int)pdwValue;
            goto LABEL_1492;
          }
        }
        else
        {
          switch ( v94 )
          {
            case -805306316:
              v4 = -1073418222;
              goto LABEL_1492;
            case -805306139:
            case -1073425151:
              v4 = -1073418201;
              goto LABEL_1492;
            case -805306306:
              v4 = -1073418200;
              goto LABEL_1492;
          }
          v4 = v94;
          if ( v94 != -2147024774 )
            goto LABEL_1492;
        }
        v4 = -1073418210;
        goto LABEL_1492;
      }
      v95 = 0;
      v1068 = 0;
      *(_OWORD *)v89 = xmmword_180021370;
      *(_OWORD *)(v89 + 16) = xmmword_180021380;
      *(_OWORD *)(v89 + 32) = xmmword_180021390;
      *(_OWORD *)(v89 + 48) = xmmword_1800213A0;
      *(_OWORD *)(v89 + 64) = xmmword_1800213B0;
      *(_OWORD *)(v89 + 80) = xmmword_1800213C0;
      *(_OWORD *)(v89 + 96) = xmmword_1800213D0;
      *(_OWORD *)(v89 + 112) = xmmword_1800213E0;
      *(_OWORD *)(v89 + 128) = xmmword_1800213F0;
      *(_OWORD *)(v89 + 144) = xmmword_180021400;
      v96 = GetProcessHeap();
      v97 = HeapAlloc(v96, 8u, 8u);
      v1069 = 196;
      v99 = v97;
      if ( !v97 )
      {
        v100 = 0;
        v94 = -1073741801;
        v99 = 0;
LABEL_538:
        Src = v94;
        goto LABEL_539;
      }
      *v97 = qword_1800212B8;
      v1066 = __rdtsc();
      pcchLength = 0;
      if ( StringCchLengthW(v98, (unsigned __int64)HIDWORD(v1066) << 32, &pcchLength) < 0 )
      {
        v94 = -1073741762;
LABEL_536:
        v1029 = v87;
        goto LABEL_537;
      }
      v102 = 2 * pcchLength + 6;
      if ( v102 < 4 )
      {
        v94 = -1073741675;
        goto LABEL_536;
      }
      v103 = v101 + v102;
      lpMem = 0;
      v90 = 0xFFFFFFFFLL;
      LODWORD(v1051) = 0;
      v104 = 0;
      v105 = -1;
      i8 = 0x10000000;
      if ( v103 >= v101 )
        v105 = v103;
      v94 = v103 < v101 ? -805306219 : 0x10000000;
      Src = v94;
      if ( v103 < v101 )
        goto LABEL_188;
      LODWORD(v89) = v105 + 8;
      *((_QWORD *)&v89 + 1) = 0xFFFFFFFFLL;
      if ( v105 + 8 >= v105 )
        *((_QWORD *)&v89 + 1) = (unsigned int)v89;
      v94 = (unsigned int)v89 < v105 ? -805306219 : 0x10000000;
      Src = v94;
      if ( (unsigned int)v89 < v105 )
        goto LABEL_188;
      LODWORD(v89) = DWORD2(v89) + 8;
      v106 = -1;
      if ( (unsigned int)(DWORD2(v89) + 8) >= DWORD2(v89) )
        v106 = DWORD2(v89) + 8;
      LODWORD(v1054) = v106;
      v94 = (unsigned int)v89 < DWORD2(v89) ? -805306219 : 0x10000000;
      Src = v94;
      if ( (unsigned int)v89 < DWORD2(v89) )
        goto LABEL_188;
      v107 = v106;
      v108 = GetProcessHeap();
      *(_QWORD *)&v89 = HeapAlloc(v108, 8u, (unsigned int)v107);
      v104 = (char *)v89;
      if ( !(_QWORD)v89 )
      {
        v94 = -1073741801;
LABEL_537:
        v100 = 0;
        goto LABEL_538;
      }
      *((_QWORD *)&v89 + 1) = v89 + 4;
      if ( (__int64)v89 + 4 < (unsigned __int64)v89 )
        goto LABEL_186;
      if ( (__int64)v89 + 8 > (unsigned __int64)(v107 + v89) )
      {
LABEL_121:
        v94 = -1073741789;
LABEL_187:
        Src = v94;
LABEL_188:
        if ( v94 < 0 )
          goto LABEL_192;
LABEL_189:
        if ( (_DWORD)v1051 )
          v94 = v1051;
        goto LABEL_191;
      }
      *(_DWORD *)v89 = 4;
      v109 = 0;
      **((_DWORD **)&v89 + 1) = 0;
      *((_QWORD *)&v89 + 1) = v89;
      do
      {
        if ( **((_DWORD **)&v89 + 1) >= 0xFFFFFFFC )
          goto LABEL_186;
        LODWORD(v89) = **((_DWORD **)&v89 + 1) + 4;
        v90 = *((_QWORD *)&v89 + 1) + (unsigned int)v89;
        if ( v90 < *((_QWORD *)&v89 + 1) )
          goto LABEL_186;
        *((_QWORD *)&v89 + 1) += (unsigned int)v89;
        ++v109;
      }
      while ( !v109 );
      v110 = (void *)(v90 + 4);
      if ( v90 + 4 < v90 )
        goto LABEL_186;
      v90 = (unsigned int)v1054;
      i8 = 160;
      lpModuleName = (LPCWSTR)(unsigned int)v1054;
      v111 = (const wchar_t *)&v104[(unsigned int)v1054];
      if ( *((_QWORD *)&v89 + 1) + 164LL > (unsigned __int64)v111 )
        goto LABEL_121;
      **((_DWORD **)&v89 + 1) = 160;
      if ( v93 )
      {
        memcpy_0(v110, v93, 0xA0u);
        v90 = (unsigned __int64)lpModuleName;
      }
      v112 = v90;
      i8 = 8;
      if ( !v99 )
      {
        v94 = -1073741811;
        goto LABEL_187;
      }
      if ( v104 )
      {
        v114 = 0;
        LODWORD(v1062) = 2;
        *((_QWORD *)&v89 + 1) = v104;
        do
        {
          LODWORD(v89) = **((_DWORD **)&v89 + 1) + 4;
          if ( **((_DWORD **)&v89 + 1) >= 0xFFFFFFFC )
            goto LABEL_186;
          v115 = *((_QWORD *)&v89 + 1) + (unsigned int)v89;
          if ( v115 < *((_QWORD *)&v89 + 1) )
            goto LABEL_186;
          ++v114;
          *((_QWORD *)&v89 + 1) += (unsigned int)v89;
        }
        while ( v114 < 2 );
        lpModuleName = (LPCWSTR)(v115 + 4);
        if ( v115 + 4 < v115 )
          goto LABEL_186;
        if ( *((_QWORD *)&v89 + 1) + 12LL > (unsigned __int64)&v104[(unsigned int)v90] )
          goto LABEL_121;
        **((_DWORD **)&v89 + 1) = 8;
        memcpy_0((void *)lpModuleName, v99, 8u);
        i8 = 0;
        v113 = v1062 + 1;
        LODWORD(v1058) = v112;
        *((_QWORD *)&v89 + 1) = v104;
        v116 = 0;
        if ( (_DWORD)v1062 != -1 )
        {
          do
          {
            LODWORD(v89) = **((_DWORD **)&v89 + 1) + 4;
            if ( **((_DWORD **)&v89 + 1) >= 0xFFFFFFFC )
              goto LABEL_186;
            v90 = *((_QWORD *)&v89 + 1) + (unsigned int)v89;
            if ( v90 < *((_QWORD *)&v89 + 1) )
              goto LABEL_186;
            ++v116;
            *((_QWORD *)&v89 + 1) += (unsigned int)v89;
          }
          while ( v116 < v113 );
        }
        v90 = *((_QWORD *)&v89 + 1) + 4LL;
        if ( (unsigned __int64)(*((_QWORD *)&v89 + 1) + 4LL) < *((_QWORD *)&v89 + 1) )
          goto LABEL_186;
        v111 = (const wchar_t *)&v104[v112];
        if ( *((_QWORD *)&v89 + 1) + 12LL > (unsigned __int64)v111 )
          goto LABEL_121;
        *(_QWORD *)&v89 = v1066;
        **((_DWORD **)&v89 + 1) = 8;
        *(_QWORD *)v90 = v89;
      }
      else
      {
        if ( (int)v90 + 12 < (unsigned int)v90 )
          goto LABEL_186;
        v113 = 3;
        i8 = 0;
        LODWORD(v1058) = v90 + 24;
        if ( (int)v90 + 24 < (unsigned int)(v90 + 12) )
          goto LABEL_186;
      }
      pcchLength = 0;
      LODWORD(v1062) = v113 + 1;
      LODWORD(v89) = StringCchLengthW(v111, *((size_t *)&v89 + 1), &pcchLength);
      i8 = 0;
      if ( (int)v89 < 0 )
      {
        v94 = -1073741762;
LABEL_533:
        Src = v94;
        goto LABEL_192;
      }
      v90 = pcchLength + 1;
      if ( pcchLength + 1 < pcchLength )
      {
        v94 = -1073741675;
        goto LABEL_533;
      }
      v90 = (unsigned int)(2 * v90);
      if ( !(_DWORD)v90 )
      {
        v94 = -1073741811;
        goto LABEL_172;
      }
      if ( !v104 )
      {
        v90 = (unsigned int)(v90 + 4);
        if ( (unsigned int)v90 >= 4 )
        {
          LODWORD(v89) = v118 + v90;
          if ( v118 + (unsigned int)v90 >= v118 )
          {
            ++v117;
            Src = 0;
            v94 = 0;
LABEL_174:
            if ( v94 < 0 )
              goto LABEL_192;
            if ( !v104 )
            {
              *((_QWORD *)&v89 + 1) = (unsigned int)(v89 + 8);
              if ( DWORD2(v89) < (unsigned int)v89 )
                goto LABEL_186;
              v121 = v117 + 1;
              i8 = (unsigned int)(DWORD2(v89) + 8);
              LODWORD(Size) = i8;
              if ( (unsigned int)i8 < DWORD2(v89) )
                goto LABEL_186;
LABEL_205:
              LODWORD(v1062) = v121 + 1;
              *(_QWORD *)&v89 = __rdtsc();
              *((_QWORD *)&v89 + 1) = (unsigned __int64)DWORD1(v89) << 32;
              lpModuleName = (LPCWSTR)v89;
              i8 = (unsigned int)(i8 + 8);
              if ( (unsigned int)i8 < 8
                || (v129 = ((_DWORD)i8 + 7) & 0xFFFFFFF8, pcchLength = v129, (unsigned int)v129 < (unsigned int)i8) )
              {
                v94 = -805306219;
                goto LABEL_533;
              }
              LODWORD(v1057) = 0;
              v130 = (i8 + 7) & 0xFFFFFFF8;
              v1045 = (unsigned int)v129;
              v131 = GetProcessHeap();
              *(_QWORD *)&v89 = HeapAlloc(v131, 8u, v130);
              v132 = 0;
              v1042 = (LPVOID)v89;
              v133 = (char *)v89;
              if ( !(_QWORD)v89 )
              {
                v94 = -805306345;
                Src = -805306345;
                goto LABEL_469;
              }
              v134 = (_DWORD *)(v89 + 4);
              *(_DWORD *)v89 = v1062;
              if ( (__int64)v89 + 4 < (unsigned __int64)v89 || (v135 = Size, *v134 = Size, v133 + 8 < v133 + 4) )
              {
                v1045 = (SIZE_T)v1042;
                LODWORD(pcchLength) = 0;
                v180 = GetProcessHeap();
                HeapFree(v180, 0, (LPVOID)v1045);
                v94 = -805306219;
                Src = -805306219;
                goto LABEL_468;
              }
              *(_QWORD *)&v133[v1045 - 8] = lpModuleName;
              memcpy_0(v133 + 8, v104, v135);
              v1045 = 0;
              v1047 = 0;
              v1046 = 0;
              v1052 = 0;
              v1060 = 0;
              v1058 = 0;
              if ( !(_DWORD)pcchLength
                || (v1051 = (unsigned int)pcchLength + 8LL, Srca = MemoryAlloc(v1051), (v136 = Srca) == 0) )
              {
                v94 = -805306367;
                Src = -805306367;
                goto LABEL_445;
              }
              v137 = 0;
              v1035 = 0;
              v138 = 0;
              if ( (_DWORD)pcchLength )
              {
                do
                  v137 ^= v133[v138++];
                while ( v138 < (unsigned int)pcchLength );
                v1035 = v137;
              }
              v1059 = v93;
              v1065 = (SIZE_T)v99;
              v1061 = v104;
              Size = 0xC81ECB17B1B54A58uLL;
              lpModuleName = (LPCWSTR)((unsigned __int64)(unsigned int)pcchLength >> 3);
              v1042 = v133;
              if ( lpModuleName )
              {
                v139 = (unsigned __int8 *)v133;
                v140 = WORD1(Size);
                v141 = lpModuleName;
                v142 = 0;
                v143 = WORD2(Size);
                v144 = HIDWORD(Size) ^ 0xB1B54A58;
                v1043 = 0;
                v145 = Srca;
                LODWORD(v1044) = 0;
                LODWORD(v1050) = 0;
                v146 = -1;
                LODWORD(v1067) = WORD1(Size);
                do
                {
                  v147 = *v139;
                  v148 = v139[1];
                  v149 = v139[4];
                  v139 += 8;
                  v150 = *(v139 - 5) | ((*(v139 - 6) | (((v147 << 8) | v148) << 8)) << 8);
                  v151 = *(v139 - 1) | ((*(v139 - 2) | ((*(v139 - 3) | (v149 << 8)) << 8)) << 8);
                  v152 = v146 ^ v151;
                  v153 = v142 ^ v150 ^ ((v146 ^ v151) - 19032);
                  v154 = __ROR4__(v153, 15);
                  v155 = HIDWORD(Size) ^ v153;
                  v156 = v152 ^ (__ROR4__(v155, 7) + v140 * v154);
                  v157 = v155 ^ (v143 * __ROR4__(v156 - 1313519016, 9) - __ROR4__(v156, 10));
                  v158 = v156 ^ (__ROR4__(v157, 27) + HIWORD(Size) * __ROR4__(v143 ^ v157, 28));
                  v159 = v157 ^ (HIDWORD(Size) - (v158 ^ 0xB1B54A58));
                  v160 = v158 ^ (WORD1(Size) * (v159 - 19032) - (v159 >> 6));
                  v161 = v159 ^ (19032 * (v143 ^ __ROR4__(v160, 15)));
                  v162 = v160 ^ (v143 * (HIWORD(Size) + __ROR4__(~v161, 3)));
                  v163 = v161 ^ (v162 - HIDWORD(Size) - 19032);
                  v164 = v162 ^ ((_DWORD)v1067 * (HIWORD(Size) ^ v163)) ^ __ROR4__(v163, 10);
                  v165 = v163 ^ __ROR4__(v164, 3) ^ (v143 * __ROR4__(v164 ^ 0x4A58, 26));
                  v166 = v164 ^ (19032 * (__ROR4__(v165, 15) - HIWORD(Size)));
                  v167 = v165
                       ^ (19032 * (HIWORD(Size) ^ v166))
                       ^ ((v166 ^ (v166 >> 14)) >> 1)
                       ^ (19032 * ((8 * (v166 - v143)) | ((v166 - v143) >> 29)));
                  v168 = v166 ^ (WORD1(Size) * (v167 - v143) - (v167 >> 13));
                  v169 = v167 ^ __ROR4__(v168, 11) ^ (v143 * __ROR4__(-1313519016 - v168, 9));
                  v170 = v168 ^ (v169 + 1313519016 - HIWORD(Size));
                  v171 = v169 ^ (19032 * ((unsigned int)v1067 ^ v170) - __ROR4__(v170, 7));
                  v172 = v170 ^ (WORD1(Size) * __ROR4__(HIWORD(Size) ^ v171, 28) - __ROR4__(v171, 16));
                  v173 = v171 ^ (__ROR4__(v172, 4) + v143 * __ROR4__(-1313519016 - v172, 10));
                  v174 = v172 ^ __ROR4__(v173, 9) ^ (HIWORD(Size) * __ROR4__(v173 + 1313519016, 4));
                  v175 = v173 ^ (19032 * __ROR4__(v174 ^ HIDWORD(Size), 24) - __ROR4__(v174, 30));
                  v176 = v174 ^ (WORD1(Size) * __ROR4__(HIDWORD(Size) - v175, 11) - __ROR4__(v175, 12));
                  v177 = v176 ^ v144 ^ (unsigned int)v1050;
                  LODWORD(v1050) = v151;
                  v178 = v175 ^ (v176 >> 8) ^ (v143 * (v176 ^ WORD1(Size)));
                  v179 = v178 ^ (unsigned int)v1044;
                  LODWORD(v1044) = v150;
                  v145[3] = v179;
                  v146 = v178 ^ v177;
                  v145[7] = v146;
                  v145[2] = __ROR4__(v179, 8);
                  v145[6] = __ROR4__(v146, 8);
                  v145[1] = __ROR4__(v179, 16);
                  v145[5] = __ROR4__(v146, 16);
                  *v145 = __ROR4__(v179, 24);
                  v145[4] = __ROR4__(v146, 24);
                  v145 += 8;
                  LODWORD(v1054) = v179;
                  v140 = WORD1(Size);
                  v142 = v1054;
                  ++v1043;
                }
                while ( v1043 < (unsigned __int64)v141 );
                v137 = v1035;
                v95 = v1068;
                v104 = v1061;
                v93 = v1059;
                v99 = (void *)v1065;
                v133 = (char *)v1042;
                v136 = Srca;
              }
              else
              {
                v1065 = (SIZE_T)v99;
              }
              *(_QWORD *)&v136[(unsigned int)pcchLength] = v137;
              v181 = GetProcessHeap();
              v1043 = (SIZE_T)HeapAlloc(v181, 8u, 0x30u);
              if ( v1043 )
              {
                v1042 = v133;
                v190 = v1043;
                v1065 = (SIZE_T)v99;
                *(_DWORD *)v1043 = v1051;
                v191 = GetProcessHeap();
                v192 = HeapAlloc(v191, 8u, (unsigned int)v1051);
                if ( v192 )
                {
                  *(_QWORD *)(v190 + 8) = v192;
                  memcpy_0(v192, Srca, (unsigned int)v1051);
                  *(_DWORD *)(v190 + 16) = 160;
                  v193 = GetProcessHeap();
                  v194 = HeapAlloc(v193, 8u, 0xA0u);
                  if ( v194 )
                  {
                    *(_QWORD *)(v190 + 24) = v194;
                    *v194 = xmmword_1800212C0;
                    v194[1] = xmmword_1800212D0;
                    v194[2] = xmmword_1800212E0;
                    v194[3] = xmmword_1800212F0;
                    v194[4] = xmmword_180021300;
                    v194[5] = xmmword_180021310;
                    v194[6] = xmmword_180021320;
                    v194[7] = xmmword_180021330;
                    v194[8] = xmmword_180021340;
                    v194[9] = xmmword_180021350;
                    *(_DWORD *)(v190 + 32) = 8;
                    v195 = GetProcessHeap();
                    v196 = HeapAlloc(v195, 8u, 8u);
                    if ( v196 )
                    {
                      *(_QWORD *)(v190 + 40) = v196;
                      *v196 = qword_180021360;
                      v1045 = v190;
                      v182 = 0;
                      v1065 = (SIZE_T)v99;
                      v183 = (void *)v1045;
                      v1045 = 0;
LABEL_225:
                      v1047 = v183;
                      v184 = GetProcessHeap();
                      HeapFree(v184, 0, Srca);
                      v89 = v1045;
                      if ( v1045 )
                      {
                        lpModuleName = *(LPCWSTR *)(v1045 + 8);
                        if ( lpModuleName )
                        {
                          v185 = GetProcessHeap();
                          HeapFree(v185, 0, (LPVOID)lpModuleName);
                          *(_QWORD *)&v89 = v1045;
                          *(_QWORD *)(v1045 + 8) = 0;
                        }
                        lpModuleName = *(LPCWSTR *)(v89 + 24);
                        if ( lpModuleName )
                        {
                          v186 = GetProcessHeap();
                          HeapFree(v186, 0, (LPVOID)lpModuleName);
                          *(_QWORD *)&v89 = v1045;
                          *(_QWORD *)(v1045 + 24) = 0;
                        }
                        lpModuleName = *(LPCWSTR *)(v89 + 40);
                        if ( lpModuleName )
                        {
                          v187 = GetProcessHeap();
                          HeapFree(v187, 0, (LPVOID)lpModuleName);
                          *(_QWORD *)(v1045 + 40) = 0;
                        }
                        v188 = GetProcessHeap();
                        HeapFree(v188, 0, (LPVOID)v1045);
                        v189 = v1047;
                        *((_QWORD *)&v89 + 1) = 0;
                      }
                      else
                      {
                        v189 = v1047;
                      }
                      v94 = v182 | 0x10000000;
                      Src = v94;
                      if ( v94 < 0 )
                        goto LABEL_435;
                      v202 = *v189 + 4;
                      LODWORD(v1067) = 0;
                      if ( v202 >= 4 )
                      {
                        *((_QWORD *)&v89 + 1) = v202 + 4;
                        if ( DWORD2(v89) >= v202 )
                        {
                          v90 = (unsigned int)(DWORD2(v89) + v189[4]);
                          pcchLength = (size_t)(v189 + 4);
                          if ( (unsigned int)v90 >= DWORD2(v89) )
                          {
                            *((_QWORD *)&v89 + 1) = (unsigned int)(v90 + 4);
                            if ( DWORD2(v89) >= (unsigned int)v90 )
                            {
                              LODWORD(v89) = DWORD2(v89) + v189[8];
                              LODWORD(v1054) = v89;
                              if ( (unsigned int)v89 >= DWORD2(v89) )
                              {
                                v203 = v89;
                                v204 = GetProcessHeap();
                                *(_QWORD *)&v89 = HeapAlloc(v204, 8u, v203);
                                v132 = 0;
                                v1045 = v89;
                                if ( !(_QWORD)v89 )
                                {
                                  v99 = (void *)v1065;
                                  v94 = -805306345;
LABEL_254:
                                  Src = v94;
LABEL_255:
                                  v205 = v1042;
                                  goto LABEL_438;
                                }
                                v206 = (const void **)v1047;
                                v207 = v89 + 4;
                                *(_DWORD *)v89 = *(_DWORD *)v1047;
                                if ( (__int64)v89 + 4 < (unsigned __int64)v89 )
                                {
                                  v1045 = v89;
                                }
                                else
                                {
                                  memcpy_0((void *)(v89 + 4), v206[1], *(unsigned int *)v206);
                                  v208 = (_DWORD *)(v207 + *(unsigned int *)v206);
                                  if ( (unsigned __int64)v208 >= v207 )
                                  {
                                    v209 = (unsigned int *)pcchLength;
                                    v210 = v208 + 1;
                                    *v208 = *(_DWORD *)pcchLength;
                                    if ( v208 + 1 >= v208 )
                                    {
                                      memcpy_0(v208 + 1, v206[3], *v209);
                                      v211 = (_DWORD *)((char *)v210 + *(unsigned int *)pcchLength);
                                      if ( v211 >= v210 )
                                      {
                                        v212 = v211 + 1;
                                        *v211 = *((_DWORD *)v206 + 8);
                                        if ( v211 + 1 >= v211 )
                                        {
                                          memcpy_0(v211 + 1, v206[5], *((unsigned int *)v206 + 8));
                                          if ( (_DWORD *)((char *)v212 + *((unsigned int *)v206 + 8)) >= v212 )
                                          {
                                            i8 = v1045;
                                            v205 = v1042;
                                            v99 = (void *)v1065;
                                            v1046 = (LPVOID)v1045;
                                            LODWORD(v1067) = v1054;
                                            if ( v104 )
                                            {
                                              *((_QWORD *)&v89 + 1) = (unsigned int)v1062;
                                              if ( (unsigned int)v1062 > 1 )
                                              {
                                                v90 = (unsigned __int64)v104;
                                                v214 = 0;
                                                do
                                                {
                                                  v215 = v90 + 4;
                                                  if ( v90 + 4 < v90 )
                                                    goto LABEL_441;
                                                  v90 = v215 + *(unsigned int *)v90;
                                                  pcchLength = v90;
                                                  if ( v90 < v215 )
                                                    goto LABEL_441;
                                                  ++v214;
                                                }
                                                while ( !v214 );
                                                if ( v90 + 4 < v90 )
                                                {
LABEL_441:
                                                  v94 = -1073741675;
                                                  goto LABEL_442;
                                                }
                                                if ( (unsigned int)v1062 > 2 )
                                                {
                                                  *((_QWORD *)&v89 + 1) = v1047;
                                                  *(_QWORD *)&v89 = v104;
                                                  LODWORD(Size) = 0;
                                                  do
                                                  {
                                                    v90 = v89 + 4;
                                                    if ( (__int64)v89 + 4 < (unsigned __int64)v89 )
                                                      goto LABEL_441;
                                                    *(_QWORD *)&v89 = v90 + *(unsigned int *)v89;
                                                    lpModuleName = (LPCWSTR)v89;
                                                    if ( (unsigned __int64)v89 < v90 )
                                                      goto LABEL_441;
                                                    LODWORD(Size) = Size + 1;
                                                    v216 = (void *)v1045;
                                                    v1043 = (SIZE_T)v93;
                                                    v1059 = (LPVOID)v1065;
                                                    v1061 = v104;
                                                    v1050 = v1042;
                                                    v1044 = v1047;
                                                    v1062 = v1045;
                                                  }
                                                  while ( (unsigned int)Size < 2 );
                                                  *((_QWORD *)&v89 + 1) = lpModuleName;
                                                  if ( (__int64)v89 + 4 >= (unsigned __int64)lpModuleName
                                                    && *(_DWORD *)pcchLength < 0xFFFFFFB0 )
                                                  {
                                                    i8 = (unsigned int)(*(_DWORD *)pcchLength + 84);
                                                    if ( (unsigned int)i8 >= *(_DWORD *)pcchLength + 80 )
                                                    {
                                                      v217 = i8 + *(_DWORD *)lpModuleName;
                                                      LODWORD(v1051) = v217;
                                                      if ( v217 >= (unsigned int)i8 )
                                                      {
                                                        if ( v217 > 0x400000 )
                                                        {
                                                          v94 = -2147418113;
                                                          *((_QWORD *)&v89 + 1) = v1044;
                                                          v1046 = (LPVOID)v1062;
                                                          v1047 = v1044;
                                                          goto LABEL_442;
                                                        }
                                                        v218 = v217;
                                                        v219 = GetProcessHeap();
                                                        *(_QWORD *)&v89 = HeapAlloc(v219, 8u, v218);
                                                        *((_QWORD *)&v89 + 1) = v1044;
                                                        v132 = 0;
                                                        v205 = v1050;
                                                        v90 = v89;
                                                        v99 = v1059;
                                                        v1052 = (LPVOID)v89;
                                                        v1047 = v1044;
                                                        v1042 = v1050;
                                                        if ( !(_QWORD)v89 )
                                                        {
                                                          v94 = -805306345;
                                                          Src = -805306345;
                                                          v1046 = (LPVOID)v1062;
                                                          v1052 = 0;
                                                          goto LABEL_438;
                                                        }
                                                        i8 = (unsigned __int64)v216;
                                                        v1046 = v216;
                                                        phModule = 0;
                                                        v1085 = 0;
                                                        v1086 = 0;
                                                        if ( !v216 )
                                                        {
                                                          v94 = -2147024809;
                                                          Src = -2147024809;
LABEL_296:
                                                          v1052 = (LPVOID)v90;
                                                          v1046 = (LPVOID)i8;
                                                          v1047 = (LPVOID)*((_QWORD *)&v89 + 1);
                                                          goto LABEL_437;
                                                        }
                                                        LODWORD(v1086) = (_DWORD)v1067;
                                                        *((_QWORD *)&v1085 + 1) = v89;
                                                        *(_QWORD *)((char *)&v1086 + 4) = (unsigned int)v1051;
                                                        *(_QWORD *)&v1085 = v216;
                                                        if ( GetModuleHandleExW(1u, L"ntdll.dll", &phModule)
                                                          && (v221 = GetProcAddress(
                                                                       phModule,
                                                                       "NtQuerySystemInformation")) != 0 )
                                                        {
                                                          v222 = ((__int64 (__fastcall *)(__int64, __int128 *))v221)(
                                                                   134,
                                                                   &v1085);
                                                          v94 = v222 | 0x10000000;
                                                          Src = v222 | 0x10000000;
                                                          if ( v222 >= 0 )
                                                          {
                                                            *((_QWORD *)&v89 + 1) = DWORD1(v1086);
                                                            v132 = 0;
                                                            goto LABEL_305;
                                                          }
                                                          v132 = 0;
                                                        }
                                                        else
                                                        {
                                                          v220 = GetLastError();
                                                          v132 = 0;
                                                          Src = v220;
                                                          v94 = v220;
                                                          if ( v220 > 0 )
                                                          {
                                                            v94 = (unsigned __int16)v220 | 0x80070000;
                                                            Src = v94;
                                                          }
                                                          if ( v94 >= 0 )
                                                          {
                                                            v94 = -2147467259;
                                                            Src = -2147467259;
                                                            goto LABEL_295;
                                                          }
                                                        }
                                                        *((_QWORD *)&v89 + 1) = (unsigned int)v1051;
                                                        if ( v94 == -805306333 )
                                                        {
                                                          v94 = -2147024774;
LABEL_303:
                                                          v205 = v1050;
                                                          v1046 = (LPVOID)v1062;
                                                          v1047 = v1044;
                                                          Src = v94;
LABEL_437:
                                                          v1042 = v205;
                                                          goto LABEL_438;
                                                        }
                                                        if ( v94 >= 0 )
                                                        {
LABEL_305:
                                                          if ( DWORD2(v89) < 4 )
                                                          {
                                                            v94 = -805306306;
                                                            goto LABEL_303;
                                                          }
                                                          v90 = (unsigned __int64)v1052;
                                                          v223 = *(unsigned int *)v1052;
                                                          v224 = (char *)v1052 + 4;
                                                          v1067 = (char *)v1052 + 4;
                                                          if ( (char *)v1052 + 4 < v1052 )
                                                            goto LABEL_440;
                                                          if ( DWORD2(v89) - 4 < (unsigned int)v223 )
                                                          {
                                                            v94 = -805306306;
                                                            goto LABEL_303;
                                                          }
                                                          v225 = &v224[v223];
                                                          Size = (size_t)&v224[v223];
                                                          if ( &v224[v223] < v224 )
                                                          {
LABEL_440:
                                                            *((_QWORD *)&v89 + 1) = v1046;
                                                            v94 = -805306219;
                                                            v205 = v1042;
                                                            Src = -805306219;
                                                            goto LABEL_437;
                                                          }
                                                          if ( (unsigned int)v223 < 0xFFFFFFFC )
                                                          {
                                                            if ( (unsigned int)(DWORD2(v89) - (v223 + 4)) < 4 )
                                                            {
LABEL_313:
                                                              v94 = -805306306;
                                                              v205 = v1050;
                                                              v1046 = (LPVOID)v1062;
                                                              v1047 = v1044;
                                                              Src = -805306306;
LABEL_436:
                                                              v132 = 0;
                                                              goto LABEL_437;
                                                            }
                                                            i8 = *(unsigned int *)v225;
                                                            v226 = v225 + 4;
                                                            LODWORD(v1054) = *(_DWORD *)v225;
                                                            if ( v225 + 4 >= v225 )
                                                            {
                                                              v227 = v223 + 8;
                                                              if ( (int)v223 + 8 >= (unsigned int)(v223 + 4) )
                                                              {
                                                                if ( DWORD2(v89) - v227 < (unsigned int)i8 )
                                                                  goto LABEL_313;
                                                                v228 = (unsigned __int64)v226 + i8;
                                                                v1051 = i8;
                                                                lpModuleName = (LPCWSTR)((char *)v226 + i8);
                                                                if ( (_DWORD *)((char *)v226 + i8) >= v226 )
                                                                {
                                                                  v229 = v227 + i8;
                                                                  if ( v227 + (unsigned int)i8 >= v227 )
                                                                  {
                                                                    if ( DWORD2(v89) - v229 < 4 )
                                                                      goto LABEL_313;
                                                                    Srcb = (const void *)(v228 + 4);
                                                                    if ( v228 + 4 >= v228 )
                                                                    {
                                                                      v230 = v229 + 4;
                                                                      if ( v229 + 4 >= v229 )
                                                                      {
                                                                        v231 = *(_DWORD *)lpModuleName;
                                                                        LODWORD(v1065) = v231;
                                                                        if ( DWORD2(v89) - v230 < v231 )
                                                                          goto LABEL_313;
                                                                        if ( v230 + v231 >= v230 )
                                                                        {
                                                                          if ( DWORD2(v89) != v230 + v231
                                                                            || (unsigned int)v223
                                                                             + (_DWORD)i8
                                                                             + v231
                                                                             + 12LL != DWORD2(v89) )
                                                                          {
                                                                            goto LABEL_313;
                                                                          }
                                                                          v232 = GetProcessHeap();
                                                                          *(_QWORD *)&v89 = HeapAlloc(v232, 8u, 0x30u);
                                                                          v132 = 0;
                                                                          pcchLength = v89;
                                                                          v233 = v89;
                                                                          if ( !(_QWORD)v89 )
                                                                          {
                                                                            v94 = -805306345;
                                                                            v205 = v1050;
                                                                            v99 = v1059;
                                                                            v1046 = (LPVOID)v1062;
                                                                            v1047 = v1044;
                                                                            Src = -805306345;
                                                                            goto LABEL_437;
                                                                          }
                                                                          v234 = v1067;
                                                                          v1045 = 0;
                                                                          if ( v1067 )
                                                                          {
                                                                            *(_DWORD *)v89 = v223;
                                                                            v235 = GetProcessHeap();
                                                                            v236 = v223;
                                                                            v237 = HeapAlloc(v235, 8u, v223);
                                                                            if ( !v237 )
                                                                            {
LABEL_339:
                                                                              v238 = -1073741801;
                                                                              v99 = v1059;
                                                                              v104 = v1061;
                                                                              v93 = (void *)v1043;
                                                                              v1046 = (LPVOID)v1062;
                                                                              v1047 = v1044;
                                                                              v1042 = v1050;
                                                                              v247 = pcchLength;
                                                                              v1065 = (SIZE_T)v1059;
                                                                              v1059 = (LPVOID)v1043;
                                                                              lpModuleName = *(LPCWSTR *)(pcchLength + 8);
                                                                              if ( lpModuleName )
                                                                              {
                                                                                v248 = GetProcessHeap();
                                                                                HeapFree(v248, 0, (LPVOID)lpModuleName);
                                                                                v247 = pcchLength;
                                                                                *(_QWORD *)(pcchLength + 8) = 0;
                                                                              }
                                                                              lpModuleName = *(LPCWSTR *)(v247 + 24);
                                                                              if ( lpModuleName )
                                                                              {
                                                                                v249 = GetProcessHeap();
                                                                                HeapFree(v249, 0, (LPVOID)lpModuleName);
                                                                                v247 = pcchLength;
                                                                                *(_QWORD *)(pcchLength + 24) = 0;
                                                                              }
                                                                              lpModuleName = *(LPCWSTR *)(v247 + 40);
                                                                              if ( lpModuleName )
                                                                              {
                                                                                v250 = GetProcessHeap();
                                                                                HeapFree(v250, 0, (LPVOID)lpModuleName);
                                                                                *(_QWORD *)(pcchLength + 40) = 0;
                                                                              }
                                                                              v251 = GetProcessHeap();
                                                                              HeapFree(v251, 0, (LPVOID)pcchLength);
                                                                              v252 = (LPCWSTR *)v1045;
                                                                              v132 = 0;
LABEL_349:
                                                                              if ( v238 < 0 )
                                                                              {
                                                                                if ( v252 )
                                                                                {
                                                                                  lpModuleName = v252[1];
                                                                                  if ( lpModuleName )
                                                                                  {
                                                                                    v253 = GetProcessHeap();
                                                                                    HeapFree(
                                                                                      v253,
                                                                                      0,
                                                                                      (LPVOID)lpModuleName);
                                                                                    v252 = (LPCWSTR *)v1045;
                                                                                    *(_QWORD *)(v1045 + 8) = 0;
                                                                                  }
                                                                                  lpModuleName = v252[3];
                                                                                  if ( lpModuleName )
                                                                                  {
                                                                                    v254 = GetProcessHeap();
                                                                                    HeapFree(
                                                                                      v254,
                                                                                      0,
                                                                                      (LPVOID)lpModuleName);
                                                                                    v252 = (LPCWSTR *)v1045;
                                                                                    *(_QWORD *)(v1045 + 24) = 0;
                                                                                  }
                                                                                  lpModuleName = v252[5];
                                                                                  if ( lpModuleName )
                                                                                  {
                                                                                    v255 = GetProcessHeap();
                                                                                    HeapFree(
                                                                                      v255,
                                                                                      0,
                                                                                      (LPVOID)lpModuleName);
                                                                                    *(_QWORD *)(v1045 + 40) = 0;
                                                                                  }
                                                                                  v256 = GetProcessHeap();
                                                                                  HeapFree(v256, 0, (LPVOID)v1045);
                                                                                  v132 = 0;
                                                                                }
                                                                              }
                                                                              else
                                                                              {
                                                                                v1060 = v252;
                                                                              }
                                                                              v94 = v238 | 0x10000000;
                                                                              Src = v94;
                                                                              if ( v94 < 0 )
                                                                                goto LABEL_255;
                                                                              v257 = v1060;
                                                                              if ( !v1060
                                                                                || (v1050 = (LPVOID)*((_QWORD *)v1060 + 1)) == 0
                                                                                || !*(_DWORD *)v1060 )
                                                                              {
                                                                                v94 = -805306355;
                                                                                goto LABEL_254;
                                                                              }
                                                                              v1045 = *(unsigned int *)v1060 - 8LL;
                                                                              *(_QWORD *)&v89 = MemoryAlloc(v1045);
                                                                              v132 = 0;
                                                                              Size = v89;
                                                                              v258 = (_DWORD *)v89;
                                                                              if ( !(_QWORD)v89 )
                                                                              {
LABEL_391:
                                                                                v1058 = 0;
                                                                                v94 = -805306367;
                                                                                goto LABEL_254;
                                                                              }
                                                                              v259 = 0;
                                                                              v1043 = 0x7F1137FAB69605ELL;
                                                                              pcchLength = (size_t)v1050;
                                                                              v1044 = v258;
                                                                              v260 = v1045 & 7;
                                                                              if ( (v1045 & 7) != 0 )
                                                                              {
                                                                                LODWORD(v1058) = 0;
                                                                                v261 = 0;
                                                                                v262 = 0;
                                                                                v263 = 0;
                                                                                v264 = (unsigned __int8 *)pcchLength;
                                                                                do
                                                                                {
                                                                                  v265 = *v264++;
                                                                                  LODWORD(v1051) = v265;
                                                                                  LODWORD(v1067) = 8 * v261;
                                                                                  if ( v261 >= 4 )
                                                                                  {
                                                                                    LODWORD(v1051) = (_DWORD)v1051 << (56 - (_BYTE)v1067);
                                                                                    v262 |= v1051;
                                                                                  }
                                                                                  else
                                                                                  {
                                                                                    LODWORD(v1051) = (_DWORD)v1051 << (24 - (_BYTE)v1067);
                                                                                    v263 |= v1051;
                                                                                  }
                                                                                  ++v261;
                                                                                }
                                                                                while ( (int)v261 < (int)v260 );
                                                                                Srcc = v263;
                                                                                v259 = 0;
                                                                                LODWORD(v1058) = v262;
                                                                                v95 = v1068;
                                                                                pcchLength = (size_t)v264;
                                                                                v1060 = v257;
                                                                                v1061 = v104;
                                                                                v1065 = (SIZE_T)v99;
                                                                                v1059 = v93;
                                                                                v266 = Srcc ^ 0x92F65A5;
                                                                                v267 = (unsigned int)v1058 ^ 0x699A899C;
                                                                                v268 = 0;
                                                                                v269 = Srcc ^ 0x92F65A5;
                                                                                v270 = (unsigned int)v1058 ^ 0x699A899C;
                                                                                if ( (v1045 & 7) != 0 )
                                                                                {
                                                                                  v271 = (WCHAR *)v258;
                                                                                  do
                                                                                  {
                                                                                    lpModuleName = (WCHAR *)((char *)v271 + 1);
                                                                                    if ( v268 >= 4 )
                                                                                    {
                                                                                      v270 = __ROR4__(v270, 24);
                                                                                      v272 = v270;
                                                                                    }
                                                                                    else
                                                                                    {
                                                                                      v269 = __ROR4__(v269, 24);
                                                                                      v272 = v269;
                                                                                    }
                                                                                    *(_BYTE *)v271 = v272;
                                                                                    ++v268;
                                                                                    v271 = (WCHAR *)lpModuleName;
                                                                                  }
                                                                                  while ( (int)v268 < (int)v260 );
                                                                                  v95 = v1068;
                                                                                  v1044 = (LPVOID)lpModuleName;
                                                                                }
                                                                                if ( v260 <= 4 )
                                                                                {
                                                                                  v273 = 0;
                                                                                  if ( v260 < 4 )
                                                                                    v266 = v266 >> (8 * (4 - v260)) << (8 * (4 - v260));
                                                                                }
                                                                                else
                                                                                {
                                                                                  v273 = v267 >> (8 * (8 - v260)) << (8 * (8 - v260));
                                                                                }
                                                                              }
                                                                              else
                                                                              {
                                                                                LODWORD(v1058) = -1;
                                                                                Srcc = 0;
                                                                                v273 = 0;
                                                                                v266 = 0;
                                                                              }
                                                                              v274 = v1045;
                                                                              if ( v1045 >> 3 )
                                                                              {
                                                                                v275 = HIDWORD(v1043);
                                                                                v276 = v1045 >> 3;
                                                                                v277 = (unsigned __int8 *)pcchLength;
                                                                                v278 = v1044;
                                                                                v279 = Srcc;
                                                                                v280 = WORD2(v1043);
                                                                                LODWORD(v1051) = 24670;
                                                                                v281 = (int)v1058;
                                                                                LODWORD(v1062) = WORD2(v1043);
                                                                                v1054 = 0;
                                                                                do
                                                                                {
                                                                                  v282 = *v277;
                                                                                  v283 = v277[1];
                                                                                  v284 = v277[4];
                                                                                  v277 += 8;
                                                                                  v285 = *(v277 - 5)
                                                                                       | ((*(v277 - 6)
                                                                                         | (((v282 << 8) | v283) << 8)) << 8);
                                                                                  v286 = v266 ^ v285;
                                                                                  v287 = *(v277 - 1)
                                                                                       | ((*(v277 - 2)
                                                                                         | ((*(v277 - 3) | (v284 << 8)) << 8)) << 8);
                                                                                  v288 = v273
                                                                                       ^ v287
                                                                                       ^ v275
                                                                                       ^ v266
                                                                                       ^ v285
                                                                                       ^ 0xAB69605E;
                                                                                  v289 = v286
                                                                                       ^ (__ROR4__(v288, 22)
                                                                                        + v280
                                                                                        * __ROR4__(
                                                                                            v288 + 1419157410,
                                                                                            27));
                                                                                  v290 = v288
                                                                                       ^ (WORD1(v1043)
                                                                                        * __ROR4__(v289 + v275, 9)
                                                                                        - __ROR4__(v289, 30));
                                                                                  v291 = v289
                                                                                       ^ (v1051 * (v290 - v280)
                                                                                        - (v290 >> 13));
                                                                                  v292 = v290
                                                                                       ^ (HIWORD(v1043)
                                                                                        * __ROR4__(
                                                                                            v291 ^ WORD1(v1043),
                                                                                            26)
                                                                                        - __ROR4__(v291, 30));
                                                                                  v293 = v291
                                                                                       ^ (v275 - (v292 ^ 0xAB69605E));
                                                                                  v294 = v292
                                                                                       ^ (WORD1(v1043) * (v280 ^ v293))
                                                                                       ^ __ROR4__(v293, 6);
                                                                                  v295 = v293
                                                                                       ^ (__ROR4__(v294, 30)
                                                                                        + v1051
                                                                                        * __ROR4__(v294 + v275, 15));
                                                                                  v296 = v294
                                                                                       ^ (HIWORD(v1043)
                                                                                        * __ROR4__(
                                                                                            v295 + 1419157410,
                                                                                            14)
                                                                                        - __ROR4__(v295, 24));
                                                                                  v297 = v295
                                                                                       ^ __ROR4__(v296, 10)
                                                                                       ^ (v1062
                                                                                        * __ROR4__(
                                                                                            v296 ^ 0xAB69605E,
                                                                                            12));
                                                                                  v298 = v297
                                                                                       ^ (HIWORD(v1043)
                                                                                        * (v1051
                                                                                         + __ROR4__(
                                                                                             ~(v296
                                                                                             ^ (v297 >> 10)
                                                                                             ^ (WORD1(v1043)
                                                                                              * (v297 ^ HIWORD(v1043)))),
                                                                                             5)));
                                                                                  v299 = v296
                                                                                       ^ (v297 >> 10)
                                                                                       ^ (WORD1(v1043)
                                                                                        * (v297 ^ HIWORD(v1043)))
                                                                                       ^ (v298 - HIWORD(v1043))
                                                                                       ^ 0xAB69605E;
                                                                                  v300 = v298
                                                                                       ^ ((v299 >> 2)
                                                                                        + v1062
                                                                                        * __ROR4__(
                                                                                            HIWORD(v1043) ^ v299,
                                                                                            30));
                                                                                  v301 = v299
                                                                                       ^ (__ROR4__(v300, 25)
                                                                                        + WORD1(v1043)
                                                                                        * __ROR4__(
                                                                                            v300 - HIDWORD(v1043),
                                                                                            6));
                                                                                  v302 = v300
                                                                                       ^ (v1051 * (v1062 ^ v301)
                                                                                        + __ROR4__(v301, 9));
                                                                                  v303 = v301
                                                                                       ^ (__ROR4__(v302, 25)
                                                                                        + HIWORD(v1043)
                                                                                        * __ROR4__(
                                                                                            v302 ^ WORD1(v1043),
                                                                                            27));
                                                                                  v275 = HIDWORD(v1043);
                                                                                  v304 = HIDWORD(v1043)
                                                                                       ^ v302
                                                                                       ^ v303
                                                                                       ^ 0xAB69605E;
                                                                                  v305 = v303
                                                                                       ^ (v1062
                                                                                        * (__ROR4__(v304, 3)
                                                                                         - WORD1(v1043)));
                                                                                  v306 = v304
                                                                                       ^ (v1051
                                                                                        * __ROR4__(
                                                                                            v305 - HIDWORD(v1043),
                                                                                            1)
                                                                                        - __ROR4__(v305, 6));
                                                                                  v307 = v305
                                                                                       ^ (__ROR4__(v306, 18)
                                                                                        + HIWORD(v1043)
                                                                                        * __ROR4__(
                                                                                            v306 - 1419157410,
                                                                                            29));
                                                                                  v308 = v306
                                                                                       ^ (v1062
                                                                                        * __ROR4__(
                                                                                            v307 - 1419157410,
                                                                                            17)
                                                                                        - __ROR4__(v307, 14));
                                                                                  v280 = v1062;
                                                                                  v309 = v307
                                                                                       ^ (v308 >> 3)
                                                                                       ^ (WORD1(v1043) * (v1051 ^ v308));
                                                                                  v310 = v279
                                                                                       ^ __ROR4__(v309, 30)
                                                                                       ^ (v1051
                                                                                        * __ROR4__(
                                                                                            HIDWORD(v1043) ^ v309,
                                                                                            28));
                                                                                  v279 = v285;
                                                                                  v266 = v308 ^ v310;
                                                                                  v278[3] = v266;
                                                                                  v273 = v309 ^ v281;
                                                                                  v278[7] = v309 ^ v281;
                                                                                  v281 = v287;
                                                                                  v278[2] = __ROR4__(v266, 8);
                                                                                  v278[6] = __ROR4__(v273, 8);
                                                                                  v278[1] = __ROR4__(v266, 16);
                                                                                  v278[5] = __ROR4__(v273, 16);
                                                                                  *v278 = __ROR4__(v266, 24);
                                                                                  v278[4] = __ROR4__(v273, 24);
                                                                                  v278 += 8;
                                                                                  ++v1054;
                                                                                }
                                                                                while ( v1054 < v276 );
                                                                                v259 = 0;
                                                                                v95 = v1068;
                                                                                v104 = v1061;
                                                                                v93 = v1059;
                                                                                v99 = (void *)v1065;
                                                                                v258 = (_DWORD *)Size;
                                                                                v274 = v1045;
                                                                              }
                                                                              for ( k = 0; k < v274; ++k )
                                                                                v259 ^= *((_BYTE *)v258 + k);
                                                                              if ( v259 != *(_QWORD *)((char *)v1050 + v274) )
                                                                              {
                                                                                MemoryFree(v258);
                                                                                v132 = 0;
                                                                                goto LABEL_391;
                                                                              }
                                                                              v205 = v1042;
                                                                              *((_QWORD *)&v89 + 1) = v1047;
                                                                              i8 = (unsigned __int64)v1046;
                                                                              v90 = (unsigned __int64)v1052;
                                                                              if ( (unsigned int)v274 < 4 )
                                                                              {
                                                                                v312 = -1073741762;
LABEL_394:
                                                                                v1058 = v258;
LABEL_395:
                                                                                v132 = 0;
LABEL_425:
                                                                                v94 = v312 | 0x10000000;
                                                                                Src = v94;
                                                                                goto LABEL_438;
                                                                              }
                                                                              v1043 = (SIZE_T)(v258 + 1);
                                                                              v1058 = v258;
                                                                              if ( v258 + 1 < v258 )
                                                                              {
                                                                                v312 = -1073741675;
                                                                                v1058 = v258;
                                                                                goto LABEL_395;
                                                                              }
                                                                              if ( (unsigned int)(v274 - 4) < 4 )
                                                                                goto LABEL_398;
                                                                              if ( v1043 + 4 >= (unsigned __int64)(v258 + 1) )
                                                                              {
                                                                                if ( (unsigned int)(v274 - 8) < v258[1] )
                                                                                  goto LABEL_398;
                                                                                if ( v258[1] < 0xFFFFFFF8 )
                                                                                {
                                                                                  v1045 = (unsigned int)v258[1];
                                                                                  pcchLength = (size_t)v258 + v1045 + 8;
                                                                                  if ( (unsigned __int64)v258
                                                                                     + (unsigned int)v274 >= pcchLength )
                                                                                  {
                                                                                    v313 = (size_t)(v258 + 2);
                                                                                    if ( (unsigned int)v274 - v1045 - 8 < 8 )
                                                                                    {
                                                                                      LODWORD(Size) = 0;
                                                                                      if ( v258 == (_DWORD *)-8LL )
                                                                                      {
                                                                                        v1058 = (LPVOID)-8LL;
                                                                                      }
                                                                                      else
                                                                                      {
                                                                                        if ( pcchLength < v313 )
                                                                                        {
                                                                                          v312 = -1073741675;
                                                                                          goto LABEL_394;
                                                                                        }
                                                                                        *((_QWORD *)&v89 + 1) = pcchLength;
                                                                                        v314 = v258 + 2;
                                                                                        if ( pcchLength > v313 )
                                                                                        {
                                                                                          while ( v314 + 1 >= v314 )
                                                                                          {
                                                                                            if ( (unsigned __int64)(v314 + 1) > pcchLength )
                                                                                              goto LABEL_418;
                                                                                            v315 = *v314 + 4;
                                                                                            if ( *v314 >= 0xFFFFFFFC )
                                                                                              break;
                                                                                            v90 = (unsigned __int64)v314
                                                                                                + v315;
                                                                                            if ( v90 < (unsigned __int64)v314 )
                                                                                              break;
                                                                                            if ( v90 > pcchLength )
                                                                                              goto LABEL_418;
                                                                                            LODWORD(Size) = Size + 1;
                                                                                            v314 = (_DWORD *)((char *)v314 + v315);
                                                                                            if ( v90 >= pcchLength )
                                                                                              goto LABEL_417;
                                                                                          }
                                                                                          v312 = -1073741675;
                                                                                          goto LABEL_395;
                                                                                        }
                                                                                        v1058 = v258;
LABEL_417:
                                                                                        if ( v314 != (_DWORD *)pcchLength )
                                                                                        {
LABEL_418:
                                                                                          v312 = -1073741811;
                                                                                          goto LABEL_395;
                                                                                        }
                                                                                      }
                                                                                      v132 = 0;
                                                                                      LODWORD(v1054) = *v258;
                                                                                      if ( v258[1] )
                                                                                      {
                                                                                        v316 = GetProcessHeap();
                                                                                        *(_QWORD *)&v89 = HeapAlloc(v316, 8u, v1045);
                                                                                        v132 = 0;
                                                                                        if ( !(_QWORD)v89 )
                                                                                        {
                                                                                          v312 = -1073741801;
LABEL_424:
                                                                                          v205 = v1042;
                                                                                          goto LABEL_425;
                                                                                        }
                                                                                      }
                                                                                      else
                                                                                      {
                                                                                        *(_QWORD *)&v89 = 0;
                                                                                      }
                                                                                      v312 = 0;
                                                                                      lpMem = (LPVOID)v89;
                                                                                      if ( v1043 != -4 )
                                                                                      {
                                                                                        memcpy_0(
                                                                                          (void *)v89,
                                                                                          (const void *)(v1043 + 4),
                                                                                          v1045);
                                                                                        v132 = 0;
                                                                                      }
                                                                                      LODWORD(v1057) = Size;
                                                                                      if ( (_DWORD)v1054 != (_DWORD)Size )
                                                                                        v312 = -1073741762;
                                                                                      goto LABEL_424;
                                                                                    }
                                                                                  }
LABEL_398:
                                                                                  v312 = -1073741762;
LABEL_399:
                                                                                  v1058 = v258;
                                                                                  goto LABEL_395;
                                                                                }
                                                                              }
                                                                              v312 = -1073741675;
                                                                              goto LABEL_399;
                                                                            }
                                                                            *(_QWORD *)(v233 + 8) = v237;
                                                                            v238 = 0;
                                                                            memcpy_0(v237, v234, v236);
                                                                            v132 = 0;
                                                                          }
                                                                          else
                                                                          {
                                                                            *(_DWORD *)v89 = 0;
                                                                            v238 = 0;
                                                                            *(_QWORD *)(v89 + 8) = 0;
                                                                          }
                                                                          v239 = (const void *)(Size + 4);
                                                                          if ( Size == -4 )
                                                                          {
                                                                            *(_DWORD *)(v233 + 16) = 0;
                                                                            *(_QWORD *)(v233 + 24) = 0;
                                                                          }
                                                                          else
                                                                          {
                                                                            *(_DWORD *)(v233 + 16) = v1054;
                                                                            v240 = GetProcessHeap();
                                                                            v241 = v1051;
                                                                            v242 = HeapAlloc(v240, 8u, v1051);
                                                                            if ( !v242 )
                                                                            {
LABEL_338:
                                                                              pcchLength = v233;
                                                                              goto LABEL_339;
                                                                            }
                                                                            *(_QWORD *)(v233 + 24) = v242;
                                                                            v238 = 0;
                                                                            memcpy_0(v242, v239, v241);
                                                                            v132 = 0;
                                                                          }
                                                                          if ( Srcb )
                                                                          {
                                                                            v243 = v1065;
                                                                            *(_DWORD *)(v233 + 32) = v1065;
                                                                            v244 = v243;
                                                                            v245 = GetProcessHeap();
                                                                            v246 = HeapAlloc(
                                                                                     v245,
                                                                                     8u,
                                                                                     (unsigned int)v244);
                                                                            if ( !v246 )
                                                                              goto LABEL_338;
                                                                            *(_QWORD *)(v233 + 40) = v246;
                                                                            v238 = 0;
                                                                            memcpy_0(v246, Srcb, v244);
                                                                            v132 = 0;
                                                                          }
                                                                          else
                                                                          {
                                                                            *(_DWORD *)(v233 + 32) = 0;
                                                                            *(_QWORD *)(v233 + 40) = 0;
                                                                          }
                                                                          v252 = (LPCWSTR *)v233;
                                                                          v104 = v1061;
                                                                          v93 = (void *)v1043;
                                                                          v1046 = (LPVOID)v1062;
                                                                          v1047 = v1044;
                                                                          v1045 = v233;
                                                                          v99 = v1059;
                                                                          v1042 = v1050;
                                                                          v1065 = (SIZE_T)v1059;
                                                                          v1059 = (LPVOID)v1043;
                                                                          goto LABEL_349;
                                                                        }
                                                                        v205 = v1042;
                                                                        v94 = -805306219;
                                                                        goto LABEL_442;
                                                                      }
                                                                    }
                                                                  }
                                                                }
                                                              }
                                                            }
                                                          }
                                                          *((_QWORD *)&v89 + 1) = v1046;
                                                          v94 = -805306219;
                                                          Src = -805306219;
LABEL_435:
                                                          v205 = v1042;
                                                          goto LABEL_436;
                                                        }
LABEL_295:
                                                        v205 = v1042;
                                                        *((_QWORD *)&v89 + 1) = v1047;
                                                        v90 = (unsigned __int64)v1052;
                                                        i8 = (unsigned __int64)v1046;
                                                        goto LABEL_296;
                                                      }
                                                    }
                                                  }
                                                  goto LABEL_441;
                                                }
                                              }
                                            }
                                            v94 = -1073741811;
LABEL_442:
                                            Src = v94;
                                            goto LABEL_443;
                                          }
                                        }
                                      }
                                    }
                                  }
                                }
                                v1047 = v206;
                                v99 = (void *)v1065;
                                v213 = GetProcessHeap();
                                HeapFree(v213, 0, (LPVOID)v1045);
                              }
                            }
                          }
                        }
                      }
                      v205 = v1042;
                      v94 = -805306219;
                      Src = -805306219;
LABEL_443:
                      v132 = 0;
LABEL_438:
                      if ( !v205 )
                      {
LABEL_446:
                        v318 = v1047;
                        if ( v1047 )
                        {
                          lpModuleName = (LPCWSTR)*((_QWORD *)v1047 + 1);
                          if ( lpModuleName )
                          {
                            v319 = GetProcessHeap();
                            HeapFree(v319, 0, (LPVOID)lpModuleName);
                            v318 = v1047;
                            *((_QWORD *)v1047 + 1) = 0;
                          }
                          lpModuleName = (LPCWSTR)*((_QWORD *)v318 + 3);
                          if ( lpModuleName )
                          {
                            v320 = GetProcessHeap();
                            HeapFree(v320, 0, (LPVOID)lpModuleName);
                            v318 = v1047;
                            *((_QWORD *)v1047 + 3) = 0;
                          }
                          lpModuleName = (LPCWSTR)*((_QWORD *)v318 + 5);
                          if ( lpModuleName )
                          {
                            v321 = GetProcessHeap();
                            HeapFree(v321, 0, (LPVOID)lpModuleName);
                            *((_QWORD *)v1047 + 5) = 0;
                          }
                          v322 = GetProcessHeap();
                          HeapFree(v322, 0, v1047);
                          v132 = 0;
                        }
                        if ( v1046 )
                        {
                          v323 = GetProcessHeap();
                          HeapFree(v323, 0, v1046);
                          v132 = 0;
                        }
                        if ( v1052 )
                        {
                          v324 = GetProcessHeap();
                          HeapFree(v324, 0, v1052);
                          v132 = 0;
                        }
                        v325 = v1060;
                        if ( v1060 )
                        {
                          lpModuleName = (LPCWSTR)*((_QWORD *)v1060 + 1);
                          if ( lpModuleName )
                          {
                            v326 = GetProcessHeap();
                            HeapFree(v326, 0, (LPVOID)lpModuleName);
                            v325 = v1060;
                            *((_QWORD *)v1060 + 1) = 0;
                          }
                          lpModuleName = (LPCWSTR)*((_QWORD *)v325 + 3);
                          if ( lpModuleName )
                          {
                            v327 = GetProcessHeap();
                            HeapFree(v327, 0, (LPVOID)lpModuleName);
                            v325 = v1060;
                            *((_QWORD *)v1060 + 3) = 0;
                          }
                          lpModuleName = (LPCWSTR)*((_QWORD *)v325 + 5);
                          if ( lpModuleName )
                          {
                            v328 = GetProcessHeap();
                            HeapFree(v328, 0, (LPVOID)lpModuleName);
                            *((_QWORD *)v1060 + 5) = 0;
                          }
                          v329 = GetProcessHeap();
                          HeapFree(v329, 0, v1060);
                          v132 = 0;
                        }
                        if ( !v1058 )
                        {
LABEL_469:
                          if ( v94 < 0 )
                            goto LABEL_192;
                          *((_QWORD *)&v89 + 1) = (unsigned int)v1057;
                          if ( !(_DWORD)v1057 )
                          {
LABEL_471:
                            v94 = -1073425151;
LABEL_191:
                            Src = v94;
                            goto LABEL_192;
                          }
                          if ( !lpMem )
                          {
                            v94 = -1073741811;
                            goto LABEL_191;
                          }
                          if ( (char *)lpMem + 4 >= lpMem )
                          {
                            v331 = 0;
                            if ( *(_DWORD *)lpMem )
                              v331 = (int *)((char *)lpMem + 4);
                            if ( *(_DWORD *)lpMem != 4 )
                            {
LABEL_523:
                              v94 = -1073741789;
                              goto LABEL_191;
                            }
                            v94 = *v331;
                            Src = v94;
                            if ( v94 == -805306333 )
                            {
                              i8 = 2147942522LL;
                              LODWORD(v1051) = -2147024774;
                            }
                            else
                            {
                              LODWORD(v1051) = v94;
                              i8 = (unsigned int)v94;
                              if ( v94 != -2147024774 && v94 < 0 )
                              {
LABEL_192:
                                if ( v104 )
                                {
                                  v124 = GetProcessHeap();
                                  HeapFree(v124, 0, v104);
                                }
                                v125 = lpMem;
                                if ( lpMem )
                                {
                                  v126 = GetProcessHeap();
                                  HeapFree(v126, 0, v125);
                                }
                                v100 = 0;
                                if ( !v93 )
                                {
LABEL_540:
                                  if ( v99 )
                                  {
                                    v335 = GetProcessHeap();
                                    HeapFree(v335, 0, v99);
                                  }
                                  if ( v94 < 0 )
                                    goto LABEL_1471;
                                  if ( !v1029 )
                                    goto LABEL_1183;
                                  v1064 = 0;
                                  dword_1800214C0 = v1029;
                                  ModuleFileNameW = GetModuleFileNameW((HMODULE)0x180000000LL, Filename, 0x104u);
                                  if ( !ModuleFileNameW || ModuleFileNameW == 260 && GetLastError() == 122 )
                                  {
LABEL_1157:
                                    SH_HANDLE::~SH_HANDLE((SH_HANDLE *)&v1064);
                                    v799 = GetProcessHeap();
                                    *(_QWORD *)&v89 = HeapAlloc(v799, 8u, 0xA0u);
                                    v800 = (char *)v89;
                                    if ( (_QWORD)v89 )
                                    {
                                      *(_OWORD *)v89 = xmmword_180021370;
                                      *(_OWORD *)(v89 + 16) = xmmword_180021380;
                                      *(_OWORD *)(v89 + 32) = xmmword_180021390;
                                      *(_OWORD *)(v89 + 48) = xmmword_1800213A0;
                                      *(_OWORD *)(v89 + 64) = xmmword_1800213B0;
                                      *(_OWORD *)(v89 + 80) = xmmword_1800213C0;
                                      *(_OWORD *)(v89 + 96) = xmmword_1800213D0;
                                      *(_OWORD *)(v89 + 112) = xmmword_1800213E0;
                                      *(_OWORD *)(v89 + 128) = xmmword_1800213F0;
                                      *(_OWORD *)(v89 + 144) = xmmword_180021400;
                                      v801 = GetProcessHeap();
                                      v802 = HeapAlloc(v801, 8u, 8u);
                                      v803 = v802;
                                      if ( !v802 )
                                      {
                                        v803 = 0;
LABEL_1180:
                                        v811 = GetProcessHeap();
                                        HeapFree(v811, 0, v800);
LABEL_1181:
                                        if ( v803 )
                                        {
                                          v812 = GetProcessHeap();
                                          HeapFree(v812, 0, v803);
                                        }
                                        goto LABEL_1183;
                                      }
                                      *v802 = qword_1800212B8;
                                      v1064 = (LPVOID)__rdtsc();
                                      v804 = GetProcessHeap();
                                      v100 = (unsigned __int64)HeapAlloc(v804, 8u, 0xC4u);
                                      if ( !v100 )
                                        goto LABEL_1180;
                                      pcchLength = 0;
                                      if ( v100 + 4 < v100 || v100 + 8 > v100 + 196 )
                                        goto LABEL_1466;
                                      *(_DWORD *)v100 = 4;
                                      v805 = 0;
                                      *(_DWORD *)(v100 + 4) = 4;
                                      *((_QWORD *)&v89 + 1) = v100;
                                      do
                                      {
                                        if ( **((_DWORD **)&v89 + 1) >= 0xFFFFFFFC )
                                          goto LABEL_1465;
                                        LODWORD(v89) = **((_DWORD **)&v89 + 1) + 4;
                                        v90 = *((_QWORD *)&v89 + 1) + (unsigned int)v89;
                                        if ( v90 < *((_QWORD *)&v89 + 1) )
                                          goto LABEL_1466;
                                        *((_QWORD *)&v89 + 1) += (unsigned int)v89;
                                        ++v805;
                                      }
                                      while ( !v805 );
                                      if ( v90 + 4 < v90 || v90 + 164 > v100 + 196 )
                                        goto LABEL_1466;
                                      *(_DWORD *)v90 = 160;
                                      if ( v800 )
                                        memcpy_0((void *)(v90 + 4), v800, 0xA0u);
                                      *((_QWORD *)&v89 + 1) = 2;
                                      v806 = 0;
                                      i8 = 196;
                                      v90 = 8;
                                      if ( !v803 )
                                        goto LABEL_1465;
                                      v1069 = 196;
                                      v807 = (char *)v100;
                                      LODWORD(v1062) = 2;
                                      LODWORD(v1054) = 196;
                                      Srcd = v94;
                                      do
                                      {
                                        v808 = *(_DWORD *)v807 + 4;
                                        if ( *(_DWORD *)v807 >= 0xFFFFFFFC )
                                          goto LABEL_1465;
                                        v809 = &v807[v808];
                                        if ( v809 < v807 )
                                          goto LABEL_1466;
                                        ++v806;
                                        v807 += v808;
                                      }
                                      while ( v806 < 2 );
                                      v810 = v809 + 4;
                                      if ( v810 < v807 || (unsigned __int64)(v807 + 12) > v100 + (unsigned int)v1069 )
                                        goto LABEL_1466;
                                      *(_DWORD *)v807 = 8;
                                      memcpy_0(v810, v803, 8u);
                                      i8 = (unsigned int)v1054;
                                      *((_QWORD *)&v89 + 1) = (unsigned int)(v1062 + 1);
                                      LODWORD(v1056) = v1054;
                                      v814 = 0;
                                      v815 = v1054;
                                      v90 = v100;
                                      if ( (_DWORD)v1062 != -1 )
                                      {
                                        while ( 1 )
                                        {
                                          LODWORD(v89) = *(_DWORD *)v90 + 4;
                                          if ( *(_DWORD *)v90 >= 0xFFFFFFFC )
                                            break;
                                          i8 = v90 + (unsigned int)v89;
                                          if ( i8 < v90 )
                                            goto LABEL_1466;
                                          ++v814;
                                          v90 += (unsigned int)v89;
                                          if ( v814 >= DWORD2(v89) )
                                            goto LABEL_1188;
                                        }
LABEL_1465:
                                        if ( !v100 )
                                          goto LABEL_1467;
                                        goto LABEL_1466;
                                      }
LABEL_1188:
                                      i8 = v90 + 4;
                                      if ( v90 + 4 < v90 || v90 + 12 > v100 + (unsigned int)v1054 )
                                      {
LABEL_1466:
                                        v1022 = GetProcessHeap();
                                        HeapFree(v1022, 0, (LPVOID)v100);
LABEL_1467:
                                        v1023 = (void *)pcchLength;
                                        v100 = 0;
                                        if ( pcchLength )
                                        {
                                          v1024 = GetProcessHeap();
                                          HeapFree(v1024, 0, v1023);
                                        }
                                        if ( !v800 )
                                          goto LABEL_1181;
                                        goto LABEL_1180;
                                      }
                                      *(_QWORD *)&v89 = v1064;
                                      *(_DWORD *)v90 = 8;
                                      *(_QWORD *)i8 = v89;
                                      LODWORD(v1062) = DWORD2(v89) + 1;
                                      *(_QWORD *)&v89 = __rdtsc();
                                      *((_QWORD *)&v89 + 1) = (unsigned __int64)DWORD1(v89) << 32;
                                      v1064 = (LPVOID)v89;
                                      v816 = v815 + 8;
                                      if ( v816 < 8 )
                                        goto LABEL_1465;
                                      v1060 = (LPVOID)((v816 + 7) & 0xFFFFFFF8);
                                      if ( (unsigned int)v1060 < v816 )
                                        goto LABEL_1465;
                                      LODWORD(v1067) = 0;
                                      v1069 = (v816 + 7) & 0xFFFFFFF8;
                                      v817 = GetProcessHeap();
                                      *(_QWORD *)&v89 = HeapAlloc(v817, 8u, v1069);
                                      v1046 = (LPVOID)v89;
                                      if ( !(_QWORD)v89 )
                                      {
                                        LODWORD(v89) = -805306345;
LABEL_1452:
                                        if ( (int)v89 >= 0 )
                                        {
                                          v90 = (unsigned int)v1067;
                                          i8 = 1;
                                          if ( (_DWORD)v1067 )
                                          {
                                            *((_QWORD *)&v89 + 1) = pcchLength;
                                            if ( pcchLength )
                                            {
                                              if ( pcchLength + 4 >= pcchLength )
                                              {
                                                v1020 = 0;
                                                if ( *(_DWORD *)pcchLength )
                                                  v1020 = (int *)(pcchLength + 4);
                                                if ( *(_DWORD *)pcchLength == 4
                                                  && *v1020 >= 0
                                                  && (unsigned int)v1067 > 1 )
                                                {
                                                  v90 = 0;
                                                  do
                                                  {
                                                    v1021 = *((_QWORD *)&v89 + 1) + 4LL;
                                                    if ( (unsigned __int64)(*((_QWORD *)&v89 + 1) + 4LL) < *((_QWORD *)&v89 + 1) )
                                                      break;
                                                    *((_QWORD *)&v89 + 1) = v1021
                                                                          + (unsigned int)**((_DWORD **)&v89 + 1);
                                                    if ( *((_QWORD *)&v89 + 1) < v1021 )
                                                      break;
                                                    v90 = (unsigned int)(v90 + 1);
                                                  }
                                                  while ( !(_DWORD)v90 );
                                                }
                                              }
                                            }
                                          }
                                        }
                                        goto LABEL_1465;
                                      }
                                      *(_DWORD *)v89 = v1062;
                                      if ( (__int64)v89 + 4 < (unsigned __int64)v89
                                        || (DWORD2(v89) = v1056,
                                            *(_DWORD *)(v89 + 4) = v1056,
                                            (__int64)v89 + 8 < (unsigned __int64)(v89 + 4)) )
                                      {
                                        v1069 = v89;
                                        v860 = GetProcessHeap();
                                        HeapFree(v860, 0, (LPVOID)v1069);
                                        LODWORD(v89) = -805306219;
                                        goto LABEL_1452;
                                      }
                                      *(_QWORD *)(v1069 + v89 - 8) = v1064;
                                      memcpy_0((void *)(v89 + 8), (const void *)v100, DWORD2(v89));
                                      v1069 = (SIZE_T)v1046;
                                      v1059 = 0;
                                      v1044 = 0;
                                      v1050 = 0;
                                      v1057 = 0;
                                      v1052 = 0;
                                      v1045 = 0;
                                      if ( !(_DWORD)v1060
                                        || (v1063 = (unsigned int)v1060 + 8LL,
                                            v1058 = MemoryAlloc(v1063),
                                            (v818 = (char *)v1058) == 0) )
                                      {
                                        v859 = v1046;
                                        v1033 = -805306367;
                                        goto LABEL_1428;
                                      }
                                      v819 = 0;
                                      v1036 = 0;
                                      v820 = 0;
                                      if ( (_DWORD)v1060 )
                                      {
                                        do
                                        {
                                          v819 ^= *(_BYTE *)(v820 + v1069);
                                          ++v820;
                                        }
                                        while ( v820 < (unsigned int)v1060 );
                                        v1036 = v819;
                                      }
                                      v1068 = v95;
                                      v1061 = v800;
                                      lpMem = v803;
                                      v1043 = v100;
                                      Size = 0xC81ECB17B1B54A58uLL;
                                      v1064 = (LPVOID)((unsigned __int64)(unsigned int)v1060 >> 3);
                                      if ( v1064 )
                                      {
                                        v821 = 0;
                                        v822 = v1064;
                                        v823 = v1058;
                                        LODWORD(v1056) = WORD1(Size);
                                        LODWORD(v1042) = HIDWORD(Size) ^ 0xB1B54A58;
                                        v824 = HIDWORD(Size) ^ 0xB1B54A58;
                                        v825 = (unsigned __int8 *)v1046;
                                        v1069 = 0;
                                        LODWORD(v1047) = HIWORD(Size);
                                        v826 = WORD2(Size);
                                        LODWORD(v1054) = 0;
                                        LODWORD(v1065) = 0;
                                        v827 = -1;
                                        do
                                        {
                                          v828 = v825[1];
                                          v829 = *v825;
                                          v830 = v825[4];
                                          v825 += 8;
                                          v831 = *(v825 - 5) | ((*(v825 - 6) | ((v828 | (v829 << 8)) << 8)) << 8);
                                          v832 = *(v825 - 1) | ((*(v825 - 2) | ((*(v825 - 3) | (v830 << 8)) << 8)) << 8);
                                          v833 = v821 ^ v831 ^ ((v827 ^ v832) - 19032);
                                          v834 = __ROR4__(v833, 15);
                                          v835 = HIDWORD(Size) ^ v833;
                                          v836 = v827 ^ v832 ^ (__ROR4__(v835, 7) + WORD1(Size) * v834);
                                          v837 = v835 ^ (v826 * __ROR4__(v836 - 1313519016, 9) - __ROR4__(v836, 10));
                                          v838 = v836 ^ (__ROR4__(v837, 27) + HIWORD(Size) * __ROR4__(v826 ^ v837, 28));
                                          v839 = v837 ^ (HIDWORD(Size) - (v838 ^ 0xB1B54A58));
                                          v840 = v838 ^ (WORD1(Size) * (v839 - 19032) - (v839 >> 6));
                                          v841 = v839 ^ (19032 * (v826 ^ __ROR4__(v840, 15)));
                                          v842 = v840 ^ (v826 * (HIWORD(Size) + __ROR4__(~v841, 3)));
                                          v843 = v841 ^ (v842 - HIDWORD(Size) - 19032);
                                          v844 = v842 ^ (v1056 * ((unsigned int)v1047 ^ v843)) ^ __ROR4__(v843, 10);
                                          v845 = v843 ^ __ROR4__(v844, 3) ^ (v826 * __ROR4__(v844 ^ 0x4A58, 26));
                                          v846 = v844 ^ (19032 * (__ROR4__(v845, 15) - HIWORD(Size)));
                                          v847 = v845
                                               ^ ((v846 ^ (v846 >> 14)) >> 1)
                                               ^ (19032 * (v846 ^ HIWORD(Size)))
                                               ^ (19032 * (((v846 - v826) >> 29) | (8 * (v846 - v826))));
                                          v848 = v846 ^ (WORD1(Size) * (v847 - v826) - (v847 >> 13));
                                          v849 = v847 ^ __ROR4__(v848, 11) ^ (v826 * __ROR4__(-1313519016 - v848, 9));
                                          v850 = v848 ^ (v849 + 1313519016 - HIWORD(Size));
                                          v851 = v849 ^ (19032 * (v850 ^ WORD1(Size)) - __ROR4__(v850, 7));
                                          v852 = v850
                                               ^ (WORD1(Size) * __ROR4__(v851 ^ HIWORD(Size), 28) - __ROR4__(v851, 16));
                                          v853 = v851 ^ (__ROR4__(v852, 4) + v826 * __ROR4__(-1313519016 - v852, 10));
                                          v854 = v852
                                               ^ __ROR4__(v853, 9)
                                               ^ (HIWORD(Size) * __ROR4__(v853 + 1313519016, 4));
                                          v855 = v853
                                               ^ (19032 * __ROR4__(v854 ^ HIDWORD(Size), 24) - __ROR4__(v854, 30));
                                          v856 = v854
                                               ^ (WORD1(Size) * __ROR4__(HIDWORD(Size) - v855, 11) - __ROR4__(v855, 12));
                                          v857 = v1065 ^ v856;
                                          LODWORD(v1065) = v832;
                                          v858 = v855 ^ (v856 >> 8) ^ (v826 * (WORD1(Size) ^ v856));
                                          v821 = v858 ^ v1054;
                                          LODWORD(v1054) = v831;
                                          v823[3] = v821;
                                          v827 = v858 ^ v824 ^ v857;
                                          v823[7] = v827;
                                          v823[2] = __ROR4__(v821, 8);
                                          v823[6] = __ROR4__(v827, 8);
                                          v823[1] = __ROR4__(v821, 16);
                                          v823[5] = __ROR4__(v827, 16);
                                          *v823 = __ROR4__(v821, 24);
                                          v823[4] = __ROR4__(v827, 24);
                                          v823 += 8;
                                          ++v1069;
                                        }
                                        while ( v1069 < (unsigned __int64)v822 );
                                        v819 = v1036;
                                        v94 = Srcd;
                                        v100 = v1043;
                                        v95 = v1068;
                                        v800 = v1061;
                                        v803 = lpMem;
                                        v859 = v1046;
                                        v818 = (char *)v1058;
                                      }
                                      else
                                      {
                                        v859 = v1046;
                                        lpMem = v803;
                                      }
                                      *(_QWORD *)&v818[(unsigned int)v1060] = v819;
                                      v861 = GetProcessHeap();
                                      v862 = HeapAlloc(v861, 8u, 0x30u);
                                      v1043 = (SIZE_T)v862;
                                      if ( !v862 )
                                      {
                                        LODWORD(v1051) = -1073741801;
LABEL_1209:
                                        v863 = v1044;
                                        goto LABEL_1210;
                                      }
                                      *v862 = v1063;
                                      lpMem = v803;
                                      v1046 = v859;
                                      v870 = GetProcessHeap();
                                      v871 = HeapAlloc(v870, 8u, (unsigned int)v1063);
                                      v872 = v1043;
                                      if ( v871 )
                                      {
                                        *(_QWORD *)(v1043 + 8) = v871;
                                        memcpy_0(v871, v1058, (unsigned int)v1063);
                                        *(_DWORD *)(v1043 + 16) = 160;
                                        v873 = GetProcessHeap();
                                        v874 = HeapAlloc(v873, 8u, 0xA0u);
                                        v872 = v1043;
                                        if ( v874 )
                                        {
                                          *(_QWORD *)(v1043 + 24) = v874;
                                          *v874 = xmmword_1800212C0;
                                          v874[1] = xmmword_1800212D0;
                                          v874[2] = xmmword_1800212E0;
                                          v874[3] = xmmword_1800212F0;
                                          v874[4] = xmmword_180021300;
                                          v874[5] = xmmword_180021310;
                                          v874[6] = xmmword_180021320;
                                          v874[7] = xmmword_180021330;
                                          v874[8] = xmmword_180021340;
                                          v874[9] = xmmword_180021350;
                                          *(_DWORD *)(v872 + 32) = 8;
                                          v875 = GetProcessHeap();
                                          v876 = HeapAlloc(v875, 8u, 8u);
                                          if ( v876 )
                                          {
                                            v882 = v1043;
                                            *(_QWORD *)(v1043 + 40) = v876;
                                            *v876 = qword_180021360;
                                            v863 = (void *)v882;
                                            v1046 = v859;
                                            LODWORD(v1051) = 0;
                                            lpMem = v803;
                                            goto LABEL_1232;
                                          }
                                          v872 = v1043;
                                        }
                                        lpMem = v803;
                                        v1046 = v859;
                                        v1043 = v872;
                                      }
                                      v877 = *(void **)(v872 + 8);
                                      LODWORD(v1051) = -1073741801;
                                      v1064 = v877;
                                      if ( v877 )
                                      {
                                        v878 = GetProcessHeap();
                                        HeapFree(v878, 0, v1064);
                                        v872 = v1043;
                                        *(_QWORD *)(v1043 + 8) = 0;
                                      }
                                      v1064 = *(LPVOID *)(v872 + 24);
                                      if ( v1064 )
                                      {
                                        v879 = GetProcessHeap();
                                        HeapFree(v879, 0, v1064);
                                        v872 = v1043;
                                        *(_QWORD *)(v1043 + 24) = 0;
                                      }
                                      v1064 = *(LPVOID *)(v872 + 40);
                                      if ( v1064 )
                                      {
                                        v880 = GetProcessHeap();
                                        HeapFree(v880, 0, v1064);
                                        *(_QWORD *)(v1043 + 40) = 0;
                                      }
                                      v881 = GetProcessHeap();
                                      HeapFree(v881, 0, (LPVOID)v1043);
                                      if ( (v1051 & 0x80000000) != 0LL )
                                        goto LABEL_1209;
                                      v863 = v1059;
LABEL_1232:
                                      v1059 = 0;
LABEL_1210:
                                      v1044 = v863;
                                      v864 = GetProcessHeap();
                                      HeapFree(v864, 0, v1058);
                                      *(_QWORD *)&v89 = v1059;
                                      if ( v1059 )
                                      {
                                        v1064 = (LPVOID)*((_QWORD *)v1059 + 1);
                                        if ( v1064 )
                                        {
                                          v865 = GetProcessHeap();
                                          HeapFree(v865, 0, v1064);
                                          *(_QWORD *)&v89 = v1059;
                                          *((_QWORD *)v1059 + 1) = 0;
                                        }
                                        v1064 = *(LPVOID *)(v89 + 24);
                                        if ( v1064 )
                                        {
                                          v866 = GetProcessHeap();
                                          HeapFree(v866, 0, v1064);
                                          *(_QWORD *)&v89 = v1059;
                                          *((_QWORD *)v1059 + 3) = 0;
                                        }
                                        v1064 = *(LPVOID *)(v89 + 40);
                                        if ( v1064 )
                                        {
                                          v867 = GetProcessHeap();
                                          HeapFree(v867, 0, v1064);
                                          *((_QWORD *)v1059 + 5) = 0;
                                        }
                                        v868 = GetProcessHeap();
                                        HeapFree(v868, 0, v1059);
                                        v869 = v1044;
                                      }
                                      else
                                      {
                                        v869 = v1044;
                                      }
                                      v883 = v1051 | 0x10000000;
                                      if ( (v1051 & 0x80000000) != 0LL )
                                        goto LABEL_1263;
                                      if ( *v869 >= 0xFFFFFFFC
                                        || (*((_QWORD *)&v89 + 1) = (unsigned int)(*v869 + 8), DWORD2(v89) < *v869 + 4)
                                        || (v90 = (unsigned int)(DWORD2(v89) + v869[4]),
                                            v1069 = (SIZE_T)(v869 + 4),
                                            (unsigned int)v90 < DWORD2(v89))
                                        || (*((_QWORD *)&v89 + 1) = (unsigned int)(v90 + 4),
                                            DWORD2(v89) < (unsigned int)v90)
                                        || (LODWORD(v89) = DWORD2(v89) + v869[8],
                                            LODWORD(v1042) = v89,
                                            (unsigned int)v89 < DWORD2(v89)) )
                                      {
                                        v1046 = v859;
                                        goto LABEL_1262;
                                      }
                                      v884 = v89;
                                      v885 = GetProcessHeap();
                                      *(_QWORD *)&v89 = HeapAlloc(v885, 8u, v884);
                                      v1043 = v89;
                                      if ( !(_QWORD)v89 )
                                      {
                                        v803 = lpMem;
                                        v1033 = -805306345;
LABEL_1426:
                                        v859 = v1046;
                                        goto LABEL_1264;
                                      }
                                      v886 = (const void **)v1044;
                                      *(_DWORD *)v89 = *(_DWORD *)v1044;
                                      v1064 = (LPVOID)(v89 + 4);
                                      if ( (__int64)v89 + 4 < (unsigned __int64)v89 )
                                      {
                                        v1043 = v89;
                                      }
                                      else
                                      {
                                        memcpy_0((void *)(v89 + 4), v886[1], *(unsigned int *)v886);
                                        v887 = (char *)v1064 + *(unsigned int *)v886;
                                        if ( v887 >= v1064 )
                                        {
                                          v888 = (unsigned int *)v1069;
                                          *v887 = *(_DWORD *)v1069;
                                          v1064 = v887 + 1;
                                          if ( v887 + 1 >= v887 )
                                          {
                                            memcpy_0(v887 + 1, v886[3], *v888);
                                            v889 = (char *)v1064 + *(unsigned int *)v1069;
                                            if ( v889 >= v1064 )
                                            {
                                              *v889 = *((_DWORD *)v886 + 8);
                                              v1064 = v889 + 1;
                                              if ( v889 + 1 >= v889 )
                                              {
                                                memcpy_0(v889 + 1, v886[5], *((unsigned int *)v886 + 8));
                                                *(_QWORD *)&v89 = (char *)v1064 + *((unsigned int *)v886 + 8);
                                                v1046 = v859;
                                                if ( (unsigned __int64)v89 >= (unsigned __int64)v1064 )
                                                {
                                                  v90 = v1043;
                                                  v803 = lpMem;
                                                  v1050 = (LPVOID)v1043;
                                                  LODWORD(v1054) = (_DWORD)v1042;
                                                  if ( !v100 || (unsigned int)v1062 <= 1 )
                                                    goto LABEL_1256;
                                                  *((_QWORD *)&v89 + 1) = v100;
                                                  v890 = 0;
                                                  do
                                                  {
                                                    i8 = *((_QWORD *)&v89 + 1) + 4LL;
                                                    if ( (unsigned __int64)(*((_QWORD *)&v89 + 1) + 4LL) < *((_QWORD *)&v89 + 1) )
                                                      goto LABEL_1425;
                                                    *((_QWORD *)&v89 + 1) = i8 + (unsigned int)**((_DWORD **)&v89 + 1);
                                                    v1072 = (LPCWSTR)*((_QWORD *)&v89 + 1);
                                                    if ( *((_QWORD *)&v89 + 1) < i8 )
                                                      goto LABEL_1425;
                                                    ++v890;
                                                  }
                                                  while ( !v890 );
                                                  if ( (unsigned __int64)(*((_QWORD *)&v89 + 1) + 4LL) < *((_QWORD *)&v89 + 1) )
                                                    goto LABEL_1425;
                                                  if ( (unsigned int)v1062 <= 2 )
                                                  {
LABEL_1256:
                                                    v1033 = -1073741811;
                                                    goto LABEL_1426;
                                                  }
                                                  *(_QWORD *)&v89 = v100;
                                                  LODWORD(v1056) = 0;
                                                  do
                                                  {
                                                    *((_QWORD *)&v89 + 1) = v89 + 4;
                                                    if ( (__int64)v89 + 4 < (unsigned __int64)v89 )
                                                      goto LABEL_1425;
                                                    *(_QWORD *)&v89 = *((_QWORD *)&v89 + 1) + *(unsigned int *)v89;
                                                    v1064 = (LPVOID)v89;
                                                    if ( (unsigned __int64)v89 < *((_QWORD *)&v89 + 1) )
                                                      goto LABEL_1425;
                                                    LODWORD(v1056) = v1056 + 1;
                                                    *((_QWORD *)&v89 + 1) = v90;
                                                    LODWORD(v1058) = v95;
                                                    v1061 = v800;
                                                    v1059 = v803;
                                                    v1051 = v100;
                                                    v1060 = v859;
                                                    lpMem = v1044;
                                                    v1043 = v90;
                                                  }
                                                  while ( (unsigned int)v1056 < 2 );
                                                  if ( (__int64)v89 + 4 < (unsigned __int64)v1064
                                                    || *(_DWORD *)v1072 >= 0xFFFFFFD0
                                                    || (v90 = (unsigned int)(*(_DWORD *)v1072 + 52),
                                                        (unsigned int)v90 < *(_DWORD *)v1072 + 48)
                                                    || (v892 = v90 + *(_DWORD *)v1064,
                                                        LODWORD(Size) = v892,
                                                        v892 < (unsigned int)v90) )
                                                  {
LABEL_1425:
                                                    v1033 = -1073741675;
                                                    goto LABEL_1426;
                                                  }
                                                  if ( v892 > 0x400000 )
                                                  {
                                                    v1044 = lpMem;
                                                    v1033 = -2147418113;
                                                    v1050 = (LPVOID)*((_QWORD *)&v89 + 1);
                                                    v1046 = v859;
                                                    goto LABEL_1426;
                                                  }
                                                  v893 = v892;
                                                  v894 = GetProcessHeap();
                                                  v895 = HeapAlloc(v894, 8u, v893);
                                                  i8 = 0;
                                                  v803 = v1059;
                                                  v737 = v895 == 0;
                                                  *((_QWORD *)&v89 + 1) = v895;
                                                  v1057 = v895;
                                                  *(_QWORD *)&v89 = v1043;
                                                  v1050 = (LPVOID)v1043;
                                                  v1044 = lpMem;
                                                  if ( v737 )
                                                  {
                                                    v1033 = -805306345;
                                                    v1057 = 0;
                                                    goto LABEL_1264;
                                                  }
                                                  v90 = v1043;
                                                  hModule = 0;
                                                  v1087 = 0;
                                                  v1088 = 0;
                                                  if ( !v1043 )
                                                  {
                                                    v1033 = -2147024809;
LABEL_1423:
                                                    v1050 = (LPVOID)v90;
                                                    goto LABEL_1424;
                                                  }
                                                  v1087 = v89;
                                                  LODWORD(v1088) = v1054;
                                                  *(_QWORD *)((char *)&v1088 + 4) = (unsigned int)Size;
                                                  if ( GetModuleHandleExW(1u, L"ntdll.dll", &hModule)
                                                    && (v897 = GetProcAddress(hModule, "NtQuerySystemInformation")) != 0 )
                                                  {
                                                    LODWORD(v89) = ((__int64 (__fastcall *)(__int64, __int128 *))v897)(
                                                                     134,
                                                                     &v1087)
                                                                 | 0x10000000;
                                                    if ( (int)v89 >= 0 )
                                                    {
                                                      v90 = DWORD1(v1088);
LABEL_1292:
                                                      if ( (unsigned int)v90 < 4 )
                                                      {
                                                        v1033 = -805306306;
                                                        goto LABEL_1290;
                                                      }
                                                      *((_QWORD *)&v89 + 1) = v1057;
                                                      i8 = *(unsigned int *)v1057;
                                                      v898 = (char *)v1057 + 4;
                                                      LODWORD(v1047) = *(_DWORD *)v1057;
                                                      v1072 = (LPCWSTR)((char *)v1057 + 4);
                                                      if ( (char *)v1057 + 4 < v1057 )
                                                        goto LABEL_1420;
                                                      if ( (int)v90 - 4 < (unsigned int)i8 )
                                                      {
LABEL_1296:
                                                        v1033 = -805306306;
                                                        goto LABEL_1290;
                                                      }
                                                      v1074 = i8;
                                                      v1069 = (SIZE_T)&v898[i8];
                                                      if ( &v898[i8] < v898 || (unsigned int)i8 >= 0xFFFFFFFC )
                                                        goto LABEL_1420;
                                                      if ( (unsigned int)(v90 - (i8 + 4)) < 4 )
                                                        goto LABEL_1296;
                                                      v899 = *(_DWORD *)&v898[i8];
                                                      LODWORD(v1054) = v899;
                                                      v900 = v1069 + 4;
                                                      if ( v1069 + 4 < v1069 )
                                                        goto LABEL_1420;
                                                      LODWORD(v1042) = i8 + 8;
                                                      if ( (int)i8 + 8 < (unsigned int)(i8 + 4) )
                                                        goto LABEL_1420;
                                                      if ( (int)v90 - (int)v1042 < v899 )
                                                        goto LABEL_1296;
                                                      lpModuleName = (LPCWSTR)v899;
                                                      v1064 = (LPVOID)(v900 + v899);
                                                      if ( (unsigned __int64)v1064 < v900 )
                                                        goto LABEL_1420;
                                                      v901 = (_DWORD)v1042 + v899;
                                                      if ( (unsigned int)v1042 + v899 < (unsigned int)v1042 )
                                                        goto LABEL_1420;
                                                      if ( (unsigned int)v90 - v901 < 4 )
                                                        goto LABEL_1296;
                                                      v902 = (unsigned int *)v1064;
                                                      v1064 = (char *)v1064 + 4;
                                                      if ( v1064 < v902 || (v903 = v901 + 4, v901 + 4 < v901) )
                                                      {
LABEL_1420:
                                                        v1033 = -805306219;
LABEL_1424:
                                                        v1057 = (LPVOID)*((_QWORD *)&v89 + 1);
                                                        goto LABEL_1264;
                                                      }
                                                      v904 = *v902;
                                                      LODWORD(v1065) = v904;
                                                      if ( (unsigned int)v90 - v903 < v904 )
                                                        goto LABEL_1296;
                                                      if ( v903 + v904 < v903 )
                                                      {
                                                        v1033 = -805306219;
                                                        goto LABEL_1264;
                                                      }
                                                      if ( (_DWORD)v90 != v903 + v904
                                                        || (unsigned int)i8 + v899 + v904 + 12LL != (unsigned int)v90 )
                                                      {
                                                        goto LABEL_1296;
                                                      }
                                                      v905 = GetProcessHeap();
                                                      *(_QWORD *)&v89 = HeapAlloc(v905, 8u, 0x30u);
                                                      v1042 = (LPVOID)v89;
                                                      v906 = v89;
                                                      if ( !(_QWORD)v89 )
                                                      {
                                                        v100 = v1051;
                                                        v803 = v1059;
                                                        v95 = (int)v1058;
                                                        v1050 = (LPVOID)v1043;
                                                        v1044 = lpMem;
                                                        v1033 = -805306345;
                                                        goto LABEL_1264;
                                                      }
                                                      v907 = v1072;
                                                      v1056 = 0;
                                                      if ( v1072 )
                                                      {
                                                        *(_DWORD *)v89 = (_DWORD)v1047;
                                                        v908 = GetProcessHeap();
                                                        v909 = v1074;
                                                        v910 = HeapAlloc(v908, 8u, v1074);
                                                        if ( !v910 )
                                                        {
LABEL_1325:
                                                          v859 = v1060;
                                                          v100 = v1051;
                                                          v803 = v1059;
                                                          v800 = v1061;
                                                          v95 = (int)v1058;
                                                          v1050 = (LPVOID)v1043;
                                                          v1044 = lpMem;
                                                          v920 = v1042;
                                                          v1034 = -1073741801;
                                                          v1046 = v1060;
                                                          v1043 = v1051;
                                                          v921 = (void *)*((_QWORD *)v1042 + 1);
                                                          lpMem = v1059;
                                                          v1068 = (int)v1058;
                                                          v1064 = v921;
                                                          if ( v921 )
                                                          {
                                                            v922 = GetProcessHeap();
                                                            HeapFree(v922, 0, v1064);
                                                            v920 = v1042;
                                                            *((_QWORD *)v1042 + 1) = 0;
                                                          }
                                                          v1064 = (LPVOID)*((_QWORD *)v920 + 3);
                                                          if ( v1064 )
                                                          {
                                                            v923 = GetProcessHeap();
                                                            HeapFree(v923, 0, v1064);
                                                            v920 = v1042;
                                                            *((_QWORD *)v1042 + 3) = 0;
                                                          }
                                                          v1064 = (LPVOID)*((_QWORD *)v920 + 5);
                                                          if ( v1064 )
                                                          {
                                                            v924 = GetProcessHeap();
                                                            HeapFree(v924, 0, v1064);
                                                            *((_QWORD *)v1042 + 5) = 0;
                                                          }
                                                          v925 = GetProcessHeap();
                                                          HeapFree(v925, 0, v1042);
                                                          v926 = (LPVOID *)v1056;
                                                          goto LABEL_1335;
                                                        }
                                                        *(_QWORD *)(v906 + 8) = v910;
                                                        v1034 = 0;
                                                        memcpy_0(v910, v907, v909);
                                                      }
                                                      else
                                                      {
                                                        *(_DWORD *)v89 = 0;
                                                        *(_QWORD *)(v89 + 8) = 0;
                                                        v1034 = 0;
                                                      }
                                                      v911 = (const void *)(v1069 + 4);
                                                      if ( v1069 == -4 )
                                                      {
                                                        *(_DWORD *)(v906 + 16) = 0;
                                                        *(_QWORD *)(v906 + 24) = 0;
                                                      }
                                                      else
                                                      {
                                                        *(_DWORD *)(v906 + 16) = v1054;
                                                        v912 = GetProcessHeap();
                                                        v913 = lpModuleName;
                                                        v914 = HeapAlloc(v912, 8u, (SIZE_T)lpModuleName);
                                                        if ( !v914 )
                                                        {
LABEL_1324:
                                                          v1042 = (LPVOID)v906;
                                                          goto LABEL_1325;
                                                        }
                                                        *(_QWORD *)(v906 + 24) = v914;
                                                        v1034 = 0;
                                                        memcpy_0(v914, v911, (size_t)v913);
                                                      }
                                                      v915 = v1064;
                                                      if ( v1064 )
                                                      {
                                                        v916 = v1065;
                                                        *(_DWORD *)(v906 + 32) = v1065;
                                                        v917 = v916;
                                                        v918 = GetProcessHeap();
                                                        v919 = HeapAlloc(v918, 8u, (unsigned int)v917);
                                                        if ( !v919 )
                                                          goto LABEL_1324;
                                                        *(_QWORD *)(v906 + 40) = v919;
                                                        v1034 = 0;
                                                        memcpy_0(v919, v915, v917);
                                                      }
                                                      else
                                                      {
                                                        *(_DWORD *)(v906 + 32) = 0;
                                                        *(_QWORD *)(v906 + 40) = 0;
                                                      }
                                                      v926 = (LPVOID *)v906;
                                                      v859 = v1060;
                                                      v100 = v1051;
                                                      v800 = v1061;
                                                      v95 = (int)v1058;
                                                      v1050 = (LPVOID)v1043;
                                                      v1056 = v906;
                                                      v803 = v1059;
                                                      v1044 = lpMem;
                                                      v1046 = v1060;
                                                      v1043 = v1051;
                                                      lpMem = v1059;
                                                      v1068 = (int)v1058;
LABEL_1335:
                                                      v927 = v1034;
                                                      *(_QWORD *)&v89 = 0;
                                                      if ( v1034 < 0 )
                                                      {
                                                        if ( v926 )
                                                        {
                                                          v1064 = v926[1];
                                                          if ( v1064 )
                                                          {
                                                            v928 = GetProcessHeap();
                                                            HeapFree(v928, 0, v1064);
                                                            v926 = (LPVOID *)v1056;
                                                            *(_QWORD *)(v1056 + 8) = 0;
                                                          }
                                                          v1064 = v926[3];
                                                          if ( v1064 )
                                                          {
                                                            v929 = GetProcessHeap();
                                                            HeapFree(v929, 0, v1064);
                                                            v926 = (LPVOID *)v1056;
                                                            *(_QWORD *)(v1056 + 24) = 0;
                                                          }
                                                          v1064 = v926[5];
                                                          if ( v1064 )
                                                          {
                                                            v930 = GetProcessHeap();
                                                            HeapFree(v930, 0, v1064);
                                                            *(_QWORD *)(v1056 + 40) = 0;
                                                          }
                                                          v931 = GetProcessHeap();
                                                          HeapFree(v931, 0, (LPVOID)v1056);
                                                          v927 = v1034;
                                                          *(_QWORD *)&v89 = v1052;
                                                        }
                                                      }
                                                      else
                                                      {
                                                        *(_QWORD *)&v89 = v926;
                                                        v1052 = v926;
                                                      }
                                                      i8 = v927 | 0x10000000u;
                                                      v1033 = i8;
                                                      if ( (i8 & 0x80000000) != 0LL )
                                                      {
LABEL_1264:
                                                        if ( !v859 )
                                                        {
LABEL_1429:
                                                          v998 = v1044;
                                                          if ( v1044 )
                                                          {
                                                            v999 = (void *)*((_QWORD *)v1044 + 1);
                                                            if ( v999 )
                                                            {
                                                              v1000 = GetProcessHeap();
                                                              HeapFree(v1000, 0, v999);
                                                              v998[1] = 0;
                                                            }
                                                            v1001 = (void *)v998[3];
                                                            if ( v1001 )
                                                            {
                                                              v1002 = GetProcessHeap();
                                                              HeapFree(v1002, 0, v1001);
                                                              v998[3] = 0;
                                                            }
                                                            v1003 = (void *)v998[5];
                                                            if ( v1003 )
                                                            {
                                                              v1004 = GetProcessHeap();
                                                              HeapFree(v1004, 0, v1003);
                                                              v998[5] = 0;
                                                            }
                                                            v1005 = GetProcessHeap();
                                                            HeapFree(v1005, 0, v998);
                                                          }
                                                          v1006 = v1050;
                                                          if ( v1050 )
                                                          {
                                                            v1007 = GetProcessHeap();
                                                            HeapFree(v1007, 0, v1006);
                                                          }
                                                          v1008 = v1057;
                                                          if ( v1057 )
                                                          {
                                                            v1009 = GetProcessHeap();
                                                            HeapFree(v1009, 0, v1008);
                                                          }
                                                          v1010 = v1052;
                                                          if ( v1052 )
                                                          {
                                                            v1011 = (void *)*((_QWORD *)v1052 + 1);
                                                            if ( v1011 )
                                                            {
                                                              v1012 = GetProcessHeap();
                                                              HeapFree(v1012, 0, v1011);
                                                              v1010[1] = 0;
                                                            }
                                                            v1013 = (void *)v1010[3];
                                                            if ( v1013 )
                                                            {
                                                              v1014 = GetProcessHeap();
                                                              HeapFree(v1014, 0, v1013);
                                                              v1010[3] = 0;
                                                            }
                                                            v1015 = (void *)v1010[5];
                                                            if ( v1015 )
                                                            {
                                                              v1016 = GetProcessHeap();
                                                              HeapFree(v1016, 0, v1015);
                                                              v1010[5] = 0;
                                                            }
                                                            v1017 = GetProcessHeap();
                                                            HeapFree(v1017, 0, v1010);
                                                          }
                                                          v1018 = (void *)v1045;
                                                          if ( v1045 )
                                                          {
                                                            v1019 = GetProcessHeap();
                                                            HeapFree(v1019, 0, v1018);
                                                          }
                                                          LODWORD(v89) = v1033;
                                                          goto LABEL_1452;
                                                        }
LABEL_1428:
                                                        v997 = GetProcessHeap();
                                                        HeapFree(v997, 0, v859);
                                                        goto LABEL_1429;
                                                      }
                                                      i8 = 0;
                                                      if ( !(_QWORD)v89
                                                        || (v1066 = *(_QWORD *)(v89 + 8)) == 0
                                                        || !*(_DWORD *)v89 )
                                                      {
                                                        v1033 = -805306355;
                                                        goto LABEL_1264;
                                                      }
                                                      v1059 = (LPVOID)(*(unsigned int *)v89 - 8LL);
                                                      *(_QWORD *)&v89 = MemoryAlloc((unsigned __int64)v1059);
                                                      i8 = 0;
                                                      v1047 = (LPVOID)v89;
                                                      v932 = (WCHAR *)v89;
                                                      if ( !(_QWORD)v89 )
                                                      {
LABEL_1377:
                                                        v1033 = -805306367;
                                                        v1045 = 0;
                                                        goto LABEL_1264;
                                                      }
                                                      v933 = 0;
                                                      v934 = (unsigned __int64)v1059;
                                                      v1063 = v1066;
                                                      v1069 = (unsigned __int8)v1059 & 7;
                                                      v1045 = 0x7F1137FAB69605ELL;
                                                      lpModuleName = v932;
                                                      LODWORD(v1062) = 0;
                                                      if ( ((unsigned __int8)v1059 & 7) != 0 )
                                                      {
                                                        v1071 = 0;
                                                        LODWORD(v1042) = 0;
                                                        v935 = 0;
                                                        v936 = 0;
                                                        v937 = 0;
                                                        v938 = (unsigned __int8 *)v1063;
                                                        do
                                                        {
                                                          v939 = *v938++;
                                                          LODWORD(v1051) = v939;
                                                          LODWORD(v1054) = 8 * v935;
                                                          if ( (unsigned int)v935 >= 4 )
                                                          {
                                                            LODWORD(v1051) = (_DWORD)v1051 << (56 - v1054);
                                                            v937 |= v1051;
                                                          }
                                                          else
                                                          {
                                                            LODWORD(v1051) = (_DWORD)v1051 << (24 - v1054);
                                                            v936 |= v1051;
                                                          }
                                                          ++v935;
                                                        }
                                                        while ( v935 < (int)v1069 );
                                                        v934 = (unsigned __int64)v1059;
                                                        LODWORD(v1062) = v936;
                                                        v933 = 0;
                                                        v1071 = v937;
                                                        v94 = Srcd;
                                                        v940 = v1069;
                                                        v941 = v932;
                                                        v1063 = (SIZE_T)v938;
                                                        v1046 = v859;
                                                        v1043 = v100;
                                                        lpMem = v803;
                                                        v1061 = v800;
                                                        v1068 = v95;
                                                        v942 = v1071 ^ 0x699A899C;
                                                        LODWORD(v1042) = 0;
                                                        v943 = v1062 ^ 0x92F65A5;
                                                        if ( (_DWORD)v1069 )
                                                        {
                                                          v944 = (unsigned int)v1042;
                                                          v945 = v1062 ^ 0x92F65A5;
                                                          v946 = v1071 ^ 0x699A899C;
                                                          do
                                                          {
                                                            v1064 = v941 + 1;
                                                            if ( v944 >= 4 )
                                                            {
                                                              v946 = __ROR4__(v946, 24);
                                                              v947 = v946;
                                                            }
                                                            else
                                                            {
                                                              v945 = __ROR4__(v945, 24);
                                                              v947 = v945;
                                                            }
                                                            *v941 = v947;
                                                            ++v944;
                                                            v941 = v1064;
                                                          }
                                                          while ( (int)v944 < (int)v940 );
                                                          v933 = 0;
                                                          v932 = (WCHAR *)v1047;
                                                          v934 = (unsigned __int64)v1059;
                                                          lpModuleName = (LPCWSTR)v1064;
                                                          v94 = Srcd;
                                                        }
                                                        if ( v940 <= 4 )
                                                        {
                                                          LODWORD(i8) = 0;
                                                          if ( v940 < 4 )
                                                            v943 = v943 >> (8 * (4 - v940)) << (8 * (4 - v940));
                                                        }
                                                        else
                                                        {
                                                          LODWORD(i8) = v942 >> (8 * (8 - v940)) << (8 * (8 - v940));
                                                        }
                                                      }
                                                      else
                                                      {
                                                        v943 = 0;
                                                      }
                                                      if ( v934 >> 3 )
                                                      {
                                                        v948 = HIDWORD(v1045);
                                                        v949 = v934 >> 3;
                                                        v950 = (WCHAR *)lpModuleName;
                                                        v951 = v1062;
                                                        v1069 = 0;
                                                        v952 = HIDWORD(v1045) ^ 0xAB69605E;
                                                        v953 = WORD2(v1045);
                                                        LODWORD(v1051) = 24670;
                                                        v954 = (unsigned __int8 *)v1063;
                                                        LODWORD(v1054) = HIDWORD(v1045) ^ 0xAB69605E;
                                                        LODWORD(Size) = WORD2(v1045);
                                                        do
                                                        {
                                                          v955 = *v954;
                                                          v956 = v954[1];
                                                          v957 = v954[4];
                                                          v954 += 8;
                                                          v958 = *(v954 - 5)
                                                               | ((*(v954 - 6) | (((v955 << 8) | v956) << 8)) << 8);
                                                          v959 = v943 ^ v958;
                                                          v960 = *(v954 - 1)
                                                               | ((*(v954 - 2) | ((*(v954 - 3) | (v957 << 8)) << 8)) << 8);
                                                          v961 = v952 ^ i8 ^ v960 ^ v943 ^ v958;
                                                          v962 = v959
                                                               ^ (__ROR4__(v961, 22)
                                                                + v953 * __ROR4__(v961 + 1419157410, 27));
                                                          v963 = v961
                                                               ^ (WORD1(v1045) * __ROR4__(v962 + v948, 9)
                                                                - __ROR4__(v962, 30));
                                                          v964 = v962 ^ (v1051 * (v963 - v953) - (v963 >> 13));
                                                          v965 = v963
                                                               ^ (HIWORD(v1045) * __ROR4__(WORD1(v1045) ^ v964, 26)
                                                                - __ROR4__(v964, 30));
                                                          v966 = v964 ^ (v948 - (v965 ^ 0xAB69605E));
                                                          v967 = v965
                                                               ^ (WORD1(v1045) * (v953 ^ v966))
                                                               ^ __ROR4__(v966, 6);
                                                          v968 = v966
                                                               ^ (__ROR4__(v967, 30) + v1051 * __ROR4__(v967 + v948, 15));
                                                          v969 = v967
                                                               ^ (HIWORD(v1045) * __ROR4__(v968 + 1419157410, 14)
                                                                - __ROR4__(v968, 24));
                                                          v970 = v968
                                                               ^ __ROR4__(v969, 10)
                                                               ^ (Size * __ROR4__(v969 ^ 0xAB69605E, 12));
                                                          v971 = v970
                                                               ^ (HIWORD(v1045)
                                                                * (v1051
                                                                 + __ROR4__(
                                                                     ~(v969
                                                                     ^ (v970 >> 10)
                                                                     ^ (WORD1(v1045) * (HIWORD(v1045) ^ v970))),
                                                                     5)));
                                                          v972 = v969
                                                               ^ (v970 >> 10)
                                                               ^ (WORD1(v1045) * (HIWORD(v1045) ^ v970))
                                                               ^ (v971 - HIWORD(v1045))
                                                               ^ 0xAB69605E;
                                                          v973 = v971
                                                               ^ ((v972 >> 2) + Size
                                                                              * __ROR4__(HIWORD(v1045) ^ v972, 30));
                                                          v974 = v972
                                                               ^ (__ROR4__(v973, 25)
                                                                + WORD1(v1045) * __ROR4__(v973 - v948, 6));
                                                          v975 = v973 ^ (v1051 * (Size ^ v974) + __ROR4__(v974, 9));
                                                          v976 = v974
                                                               ^ (__ROR4__(v975, 25)
                                                                + HIWORD(v1045) * __ROR4__(WORD1(v1045) ^ v975, 27));
                                                          v953 = Size;
                                                          v977 = v1054 ^ v975 ^ v976;
                                                          v978 = v976 ^ (Size * (__ROR4__(v977, 3) - WORD1(v1045)));
                                                          v979 = v977
                                                               ^ (v1051 * __ROR4__(v978 - v948, 1) - __ROR4__(v978, 6));
                                                          v980 = v978
                                                               ^ (__ROR4__(v979, 18)
                                                                + HIWORD(v1045) * __ROR4__(v979 - 1419157410, 29));
                                                          v981 = v979
                                                               ^ (Size * __ROR4__(v980 - 1419157410, 17)
                                                                - __ROR4__(v980, 14));
                                                          v952 = v1054;
                                                          v982 = v980 ^ (v981 >> 3) ^ (WORD1(v1045) * (v1051 ^ v981));
                                                          v983 = v982 ^ v948;
                                                          v984 = v982;
                                                          LODWORD(i8) = v1071 ^ v982;
                                                          v1071 = v960;
                                                          v943 = v951
                                                               ^ v981
                                                               ^ __ROR4__(v984, 30)
                                                               ^ (v1051 * __ROR4__(v983, 28));
                                                          v951 = v958;
                                                          *((_BYTE *)v950 + 3) = v943;
                                                          *((_BYTE *)v950 + 7) = i8;
                                                          *((_BYTE *)v950 + 2) = __ROR4__(v943, 8);
                                                          *((_BYTE *)v950 + 6) = __ROR4__(i8, 8);
                                                          *((_BYTE *)v950 + 1) = __ROR4__(v943, 16);
                                                          *((_BYTE *)v950 + 5) = __ROR4__(i8, 16);
                                                          *(_BYTE *)v950 = __ROR4__(v943, 24);
                                                          *((_BYTE *)v950 + 4) = __ROR4__(i8, 24);
                                                          v950 += 4;
                                                          ++v1069;
                                                        }
                                                        while ( v1069 < v949 );
                                                        v933 = 0;
                                                        v94 = Srcd;
                                                        v100 = v1043;
                                                        v95 = v1068;
                                                        v800 = v1061;
                                                        v803 = lpMem;
                                                        v859 = v1046;
                                                        v932 = (WCHAR *)v1047;
                                                      }
                                                      v985 = 0;
                                                      if ( v1059 )
                                                      {
                                                        do
                                                          v933 ^= *((_BYTE *)v932 + v985++);
                                                        while ( v985 < (unsigned __int64)v1059 );
                                                      }
                                                      if ( v933 != *(_QWORD *)((char *)v1059 + v1066) )
                                                      {
                                                        MemoryFree(v932);
                                                        i8 = 0;
                                                        goto LABEL_1377;
                                                      }
                                                      v986 = v1044;
                                                      v90 = (unsigned __int64)v1050;
                                                      *((_QWORD *)&v89 + 1) = v1057;
                                                      if ( (unsigned int)v1059 < 4 )
                                                      {
                                                        i8 = 3221225534LL;
                                                        v1045 = (SIZE_T)v932;
LABEL_1418:
                                                        LODWORD(i8) = i8 | 0x10000000;
                                                        v1033 = i8;
                                                        goto LABEL_1264;
                                                      }
                                                      v1045 = (SIZE_T)v932;
                                                      v1069 = (SIZE_T)(v932 + 2);
                                                      v987 = (SIZE_T)v932;
                                                      if ( v932 + 2 < v932 )
                                                        goto LABEL_1415;
                                                      if ( (unsigned int)((_DWORD)v1059 - 4) < 4 )
                                                      {
LABEL_1382:
                                                        i8 = 3221225534LL;
                                                        v1045 = (SIZE_T)v932;
LABEL_1417:
                                                        v1044 = v986;
                                                        v1050 = (LPVOID)v90;
                                                        goto LABEL_1418;
                                                      }
                                                      lpModuleName = v932 + 4;
                                                      v986 = v1044;
                                                      if ( v932 + 4 < v932 + 2 )
                                                        goto LABEL_1415;
                                                      if ( (unsigned int)((_DWORD)v1059 - 8) < *((_DWORD *)v932 + 1) )
                                                        goto LABEL_1382;
                                                      if ( *((_DWORD *)v932 + 1) >= 0xFFFFFFF8 )
                                                      {
LABEL_1415:
                                                        i8 = 3221225621LL;
                                                      }
                                                      else
                                                      {
                                                        v988 = *((unsigned int *)v932 + 1);
                                                        v1064 = (LPVOID)(unsigned int)v1059;
                                                        v1043 = v988;
                                                        v989 = v988 + 4;
                                                        v986 = v1044;
                                                        v990 = (char *)v932 + v989 + 4;
                                                        v90 = (unsigned __int64)v1050;
                                                        if ( (char *)v932 + (unsigned int)v1059 >= v990 )
                                                        {
                                                          v991 = lpModuleName;
                                                          if ( (unsigned __int64)v1064
                                                             + (char *)v932
                                                             - v1043
                                                             - (char *)lpModuleName < 8 )
                                                          {
                                                            LODWORD(v1056) = 0;
                                                            if ( lpModuleName )
                                                            {
                                                              v932 = (WCHAR *)v1047;
                                                              *(_QWORD *)&v89 = v1043 + 4 + v1069;
                                                              *((_QWORD *)&v89 + 1) = v1057;
                                                              if ( (unsigned __int64)v89 < (unsigned __int64)lpModuleName )
                                                              {
                                                                i8 = 3221225621LL;
                                                                v1045 = v987;
                                                                goto LABEL_1418;
                                                              }
                                                              v992 = lpModuleName;
                                                              if ( (unsigned __int64)v89 > (unsigned __int64)lpModuleName )
                                                              {
                                                                v90 = v1043;
                                                                *((_QWORD *)&v89 + 1) = (char *)v1047 + 4;
                                                                v993 = v1056;
                                                                while ( v992 + 2 >= v992 )
                                                                {
                                                                  if ( (unsigned __int64)(v992 + 2) > (unsigned __int64)v89 )
                                                                    goto LABEL_1402;
                                                                  if ( *(_DWORD *)v992 >= 0xFFFFFFFC )
                                                                    break;
                                                                  v994 = (unsigned __int64)v992
                                                                       + (unsigned int)(*(_DWORD *)v992 + 4);
                                                                  if ( v994 < (unsigned __int64)v992 )
                                                                    break;
                                                                  *(_QWORD *)&v89 = *((_QWORD *)&v89 + 1) + v1043 + 4;
                                                                  if ( v994 > (unsigned __int64)v89 )
                                                                    goto LABEL_1402;
                                                                  ++v993;
                                                                  v992 = (LPCWSTR)((char *)v992
                                                                                 + (unsigned int)(*(_DWORD *)v992 + 4));
                                                                  LODWORD(v1056) = v993;
                                                                  if ( v994 >= (unsigned __int64)v89 )
                                                                    goto LABEL_1401;
                                                                }
                                                                i8 = 3221225621LL;
                                                                goto LABEL_1418;
                                                              }
                                                              v1045 = (SIZE_T)v1047;
LABEL_1401:
                                                              if ( v992 != (LPCWSTR)v89 )
                                                              {
LABEL_1402:
                                                                i8 = 3221225485LL;
                                                                goto LABEL_1418;
                                                              }
                                                            }
                                                            else
                                                            {
                                                              v1045 = (SIZE_T)v932;
                                                            }
                                                            LODWORD(v1042) = *(_DWORD *)v932;
                                                            if ( *((_DWORD *)v932 + 1) )
                                                            {
                                                              v995 = GetProcessHeap();
                                                              v996 = v1043;
                                                              *(_QWORD *)&v89 = HeapAlloc(v995, 8u, v1043);
                                                              if ( !(_QWORD)v89 )
                                                              {
                                                                i8 = 3221225495LL;
                                                                goto LABEL_1418;
                                                              }
                                                              v991 = lpModuleName;
                                                            }
                                                            else
                                                            {
                                                              v996 = v1043;
                                                              *(_QWORD *)&v89 = 0;
                                                            }
                                                            pcchLength = v89;
                                                            if ( v991 )
                                                              memcpy_0((void *)v89, v991, v996);
                                                            LODWORD(v1067) = v1056;
                                                            i8 = 0;
                                                            if ( (_DWORD)v1042 != (_DWORD)v1056 )
                                                              i8 = 3221225534LL;
                                                            goto LABEL_1418;
                                                          }
                                                        }
                                                        i8 = 3221225534LL;
                                                      }
                                                      v1045 = (SIZE_T)v932;
                                                      goto LABEL_1417;
                                                    }
                                                  }
                                                  else
                                                  {
                                                    LODWORD(v89) = GetLastError();
                                                    v896 = (int)v89 < 0;
                                                    if ( (int)v89 > 0 )
                                                    {
                                                      LODWORD(v89) = (unsigned __int16)v89 | 0x80070000;
                                                      v896 = (int)v89 < 0;
                                                    }
                                                    if ( !v896 )
                                                    {
                                                      v1033 = -2147467259;
                                                      goto LABEL_1422;
                                                    }
                                                  }
                                                  v90 = (unsigned int)Size;
                                                  if ( (_DWORD)v89 == -805306333 )
                                                  {
                                                    v1033 = -2147024774;
LABEL_1290:
                                                    v1050 = (LPVOID)v1043;
                                                    v1044 = lpMem;
                                                    goto LABEL_1264;
                                                  }
                                                  if ( (int)v89 >= 0 )
                                                    goto LABEL_1292;
                                                  v1033 = v89;
LABEL_1422:
                                                  *((_QWORD *)&v89 + 1) = v1057;
                                                  v90 = (unsigned __int64)v1050;
                                                  goto LABEL_1423;
                                                }
                                                goto LABEL_1260;
                                              }
                                            }
                                          }
                                        }
                                      }
                                      v1046 = v859;
LABEL_1260:
                                      v1044 = v886;
                                      v803 = lpMem;
                                      v891 = GetProcessHeap();
                                      HeapFree(v891, 0, (LPVOID)v1043);
LABEL_1262:
                                      v859 = v1046;
                                      v883 = -805306219;
LABEL_1263:
                                      v1033 = v883;
                                      goto LABEL_1264;
                                    }
LABEL_1183:
                                    v813 = v95;
                                    v1081 = (unsigned int *)v1084;
                                    v1063 = v100;
                                    goto LABEL_1472;
                                  }
                                  v1059 = (LPVOID)((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))off_1800210F8[0])(
                                                    0,
                                                    0,
                                                    1027);
                                  if ( !v1059 )
                                  {
                                    GetLastError();
                                    goto LABEL_1157;
                                  }
                                  v337 = off_180021098[0]();
                                  v338 = dword_1800214C0;
                                  qword_1800214B0 = v337;
                                  LODWORD(v1046) = dword_1800214C0;
                                  memset_0(&v1098, 0, 0x70u);
                                  memset(v1154, 0, 44);
                                  v1073 = 0;
                                  while ( _InterlockedCompareExchange(&dword_180021534, 1, 0) )
                                    ;
                                  v339 = dword_180021530;
                                  if ( dword_180021530 )
                                    goto LABEL_594;
                                  v340 = MemoryAlloc(0x338u);
                                  v341 = v340;
                                  if ( !v340 )
                                  {
LABEL_559:
                                    v100 = 0;
                                    goto LABEL_560;
                                  }
                                  v342 = v340;
                                  v343 = (unsigned __int8 *)&unk_18001E940;
                                  v344 = 103;
                                  v345 = 0;
                                  v346 = -1;
                                  v347 = 0;
                                  v348 = 0;
                                  do
                                  {
                                    v349 = *v343 << 8;
                                    v350 = v343[1];
                                    v351 = v343[4];
                                    v343 += 8;
                                    v352 = *(v343 - 5) | ((*(v343 - 6) | ((v349 | v350) << 8)) << 8);
                                    v353 = v348 ^ v352;
                                    v354 = *(v343 - 1) | ((*(v343 - 2) | ((*(v343 - 3) | (v351 << 8)) << 8)) << 8);
                                    v355 = v348 ^ v352 ^ v347 ^ v354 ^ 0xAC987321;
                                    v356 = v353 ^ (__ROR4__(v355, 22) + 4991 * __ROR4__(v355 + 1419157410, 27));
                                    v357 = v355 ^ (43881 * __ROR4__(v356 + 133239679, 9) - __ROR4__(v356, 30));
                                    v358 = v356 ^ (24670 * v357 - (v357 >> 13) - 123127970);
                                    v359 = v357 ^ (2033 * __ROR4__(v358 ^ 0xAB69, 26) - __ROR4__(v358, 30));
                                    v360 = v358 ^ (133239679 - (v359 ^ 0xAB69605E));
                                    v361 = v359 ^ (43881 * (v360 ^ 0x137F)) ^ __ROR4__(v360, 6);
                                    v362 = v360 ^ (__ROR4__(v361, 30) + 24670 * __ROR4__(v361 + 133239679, 15));
                                    v363 = v361 ^ (2033 * __ROR4__(v362 + 1419157410, 14) - __ROR4__(v362, 24));
                                    v364 = v362 ^ __ROR4__(v363, 10) ^ (4991 * __ROR4__(v363 ^ 0xAB69605E, 12));
                                    v365 = v363 ^ (v364 >> 10) ^ (43881 * (v364 ^ 0x7F1));
                                    v366 = v364 ^ (2033 * (__ROR4__(~v365, 5) + 24670));
                                    v367 = v366
                                         ^ (((v365 ^ (v366 - 2033) ^ 0xAB69605E) >> 2)
                                          + 4991 * __ROR4__(v365 ^ (v366 - 2033) ^ 0xAB6967AF, 30));
                                    v368 = v365
                                         ^ (v366 - 2033)
                                         ^ 0xAB69605E
                                         ^ (__ROR4__(v367, 25) + 43881 * __ROR4__(v367 - 133239679, 6));
                                    v369 = v367 ^ (24670 * (v368 ^ 0x137F) + __ROR4__(v368, 9));
                                    v370 = v368 ^ (__ROR4__(v369, 25) + 2033 * __ROR4__(v369 ^ 0xAB69, 27));
                                    v371 = v369 ^ v370 ^ 0xAC987321;
                                    v372 = v370 ^ (4991 * __ROR4__(v371, 3) - 219010071);
                                    v373 = v371 ^ (24670 * __ROR4__(v372 - 133239679, 1) - __ROR4__(v372, 6));
                                    v374 = v372 ^ (__ROR4__(v373, 18) + 2033 * __ROR4__(v373 - 1419157410, 29));
                                    v375 = v373 ^ (4991 * __ROR4__(v374 - 1419157410, 17) - __ROR4__(v374, 14));
                                    v376 = v374 ^ (v375 >> 3) ^ (43881 * (v375 ^ 0x605E));
                                    v377 = __ROR4__(v376, 30);
                                    v347 = v346 ^ v376;
                                    v346 = v354;
                                    v348 = v345
                                         ^ v375
                                         ^ v377
                                         ^ (24670
                                          * __ROR4__(v374 ^ (v375 >> 3) ^ (43881 * (v375 ^ 0x605E)) ^ 0x7F1137F, 28));
                                    v345 = v352;
                                    v342[3] = v348;
                                    v342[7] = v347;
                                    v342[2] = __ROR4__(v348, 8);
                                    v342[6] = __ROR4__(v347, 8);
                                    v342[1] = __ROR4__(v348, 16);
                                    v342[5] = __ROR4__(v347, 16);
                                    *v342 = __ROR4__(v348, 24);
                                    v342[4] = __ROR4__(v347, 24);
                                    v342 += 8;
                                    --v344;
                                  }
                                  while ( v344 );
                                  v338 = (unsigned int)v1046;
                                  v94 = Src;
                                  v378 = 0;
                                  v95 = v1068;
                                  v379 = 0;
                                  do
                                    v379 ^= v341[v378++];
                                  while ( v378 < 0x338 );
                                  if ( v379 != 64 )
                                  {
                                    MemoryFree(v341);
                                    goto LABEL_559;
                                  }
                                  LODWORD(Size) = 0;
                                  LODWORD(v1057) = 0;
                                  v341[823] = 0;
                                  memset_0(&unk_1800214D0, 0, 0x60u);
                                  if ( *v341 )
                                  {
                                    v382 = (unsigned int)v1057;
                                    v1063 = (SIZE_T)v341;
                                    while ( 1 )
                                    {
                                      v383 = -1;
                                      do
                                        ++v383;
                                      while ( *(_WORD *)&v341[2 * v383] );
                                      v1066 = 3 * v382;
                                      if ( !GetModuleHandleExW(0, (LPCWSTR)v341, (HMODULE *)&unk_1800214D0 + 3 * v382) )
                                        break;
                                      v384 = v1066;
                                      v385 = &v341[2 * v383];
                                      v386 = *((_QWORD *)&unk_1800214D0 + v1066);
                                      if ( *(_WORD *)v386 == 23117
                                        && (v388 = *(int *)(v386 + 60), (unsigned int)v388 < 0x10000000)
                                        && (v389 = *((_QWORD *)&unk_1800214D0 + v1066) + v388,
                                            v389 >= *((_QWORD *)&unk_1800214D0 + v1066))
                                        && *(_DWORD *)v389 == 17744 )
                                      {
                                        if ( ((*(_WORD *)(v389 + 24) - 267) & 0xFEFF) != 0 )
                                        {
                                          v387 = -1073741811;
                                        }
                                        else
                                        {
                                          v387 = 0;
                                          *(_QWORD *)((char *)&unk_1800214D0 + 8 * v1066 + 12) = *(_QWORD *)(v389 + 136);
                                          *((_DWORD *)&unk_1800214D0 + 2 * v384 + 2) = *(_DWORD *)(v389 + 80);
                                        }
                                      }
                                      else
                                      {
                                        v387 = -1073741701;
                                      }
                                      v390 = *(_DWORD *)(v385 + 2);
                                      v391 = 0;
                                      v341 = v385 + 6;
                                      LODWORD(v1054) = v390;
                                      LODWORD(v1056) = 0;
                                      if ( v390 )
                                      {
                                        do
                                        {
                                          v392 = -1;
                                          do
                                            ++v392;
                                          while ( v341[v392] );
                                          lpModuleName = (LPCWSTR)v392;
                                          if ( v387 >= 0 )
                                          {
                                            v393 = GetProcAddress(*((HMODULE *)&unk_1800214D0 + v384), v341);
                                            if ( !v393 )
                                              goto LABEL_588;
                                            v384 = v1066;
                                            off_180021000[(unsigned int)Size] = v393;
                                            v392 = (__int64)lpModuleName;
                                            v391 = v1056;
                                          }
                                          v341 += v392 + 1;
                                          LODWORD(Size) = Size + 1;
                                          LODWORD(v1056) = ++v391;
                                        }
                                        while ( v391 < (unsigned int)v1054 );
                                      }
                                      v382 = (unsigned int)((_DWORD)v1057 + 1);
                                      LODWORD(v1057) = (_DWORD)v1057 + 1;
                                      if ( !*v341 )
                                        goto LABEL_588;
                                    }
                                    v387 = -1073741702;
LABEL_588:
                                    v341 = (_BYTE *)v1063;
                                    if ( !v1063 )
                                      goto LABEL_592;
                                  }
                                  else
                                  {
                                    v387 = 0;
                                  }
                                  v394 = GetProcessHeap();
                                  HeapFree(v394, 0, v341);
LABEL_592:
                                  v100 = 0;
                                  if ( v387 < 0 )
                                  {
LABEL_560:
                                    for ( m = 0; m != 4; ++m )
                                    {
                                      v381 = (HMODULE)*((_QWORD *)&unk_1800214D0 + 3 * m);
                                      if ( v381 )
                                        FreeLibrary(v381);
                                    }
                                    memset_0(&unk_1800214D0, 0, 0x60u);
                                    memcpy_0(off_180021000, off_180015170, 0x170u);
LABEL_595:
                                    _InterlockedExchange(&dword_180021534, 0);
                                    v1043 = 0;
                                    v1047 = 0;
                                    while ( _InterlockedCompareExchange(&dword_180021534, 1, 0) )
                                      ;
                                    v395 = dword_180021530;
                                    if ( dword_180021530 )
                                      goto LABEL_640;
                                    v396 = (const WCHAR *)MemoryAlloc(0x338u);
                                    lpModuleName = v396;
                                    if ( !v396 )
                                    {
LABEL_605:
                                      v100 = 0;
                                      goto LABEL_606;
                                    }
                                    v397 = (WCHAR *)v396;
                                    v398 = (unsigned __int8 *)&unk_18001E940;
                                    v399 = -1;
                                    v400 = 103;
                                    v401 = 0;
                                    v402 = 0;
                                    v403 = 0;
                                    do
                                    {
                                      v404 = v398[1];
                                      v405 = *v398;
                                      v406 = v398[4];
                                      v398 += 8;
                                      v407 = *(v398 - 5) | ((*(v398 - 6) | ((v404 | (v405 << 8)) << 8)) << 8);
                                      v408 = v403 ^ v407;
                                      v409 = *(v398 - 1) | ((*(v398 - 2) | ((*(v398 - 3) | (v406 << 8)) << 8)) << 8);
                                      v410 = v402 ^ v409 ^ v403 ^ v407 ^ 0xAC987321;
                                      v411 = v408 ^ (__ROR4__(v410, 22) + 4991 * __ROR4__(v410 + 1419157410, 27));
                                      v412 = v410 ^ (43881 * __ROR4__(v411 + 133239679, 9) - __ROR4__(v411, 30));
                                      v413 = v411 ^ (24670 * v412 - (v412 >> 13) - 123127970);
                                      v414 = v412 ^ (2033 * __ROR4__(v413 ^ 0xAB69, 26) - __ROR4__(v413, 30));
                                      v415 = v413 ^ (133239679 - (v414 ^ 0xAB69605E));
                                      v416 = v414 ^ (43881 * (v415 ^ 0x137F)) ^ __ROR4__(v415, 6);
                                      v417 = v415 ^ (__ROR4__(v416, 30) + 24670 * __ROR4__(v416 + 133239679, 15));
                                      v418 = v416 ^ (2033 * __ROR4__(v417 + 1419157410, 14) - __ROR4__(v417, 24));
                                      v419 = v417 ^ __ROR4__(v418, 10) ^ (4991 * __ROR4__(v418 ^ 0xAB69605E, 12));
                                      v420 = v418 ^ (v419 >> 10) ^ (43881 * (v419 ^ 0x7F1));
                                      v421 = v419 ^ (2033 * (__ROR4__(~v420, 5) + 24670));
                                      v422 = v421
                                           ^ (((v420 ^ (v421 - 2033) ^ 0xAB69605E) >> 2)
                                            + 4991 * __ROR4__(v420 ^ (v421 - 2033) ^ 0xAB6967AF, 30));
                                      v423 = v420
                                           ^ (v421 - 2033)
                                           ^ 0xAB69605E
                                           ^ (__ROR4__(v422, 25) + 43881 * __ROR4__(v422 - 133239679, 6));
                                      v424 = v422 ^ (24670 * (v423 ^ 0x137F) + __ROR4__(v423, 9));
                                      v425 = v423 ^ (__ROR4__(v424, 25) + 2033 * __ROR4__(v424 ^ 0xAB69, 27));
                                      v426 = v424 ^ v425 ^ 0xAC987321;
                                      v427 = v425 ^ (4991 * __ROR4__(v426, 3) - 219010071);
                                      v428 = v426 ^ (24670 * __ROR4__(v427 - 133239679, 1) - __ROR4__(v427, 6));
                                      v429 = v427 ^ (__ROR4__(v428, 18) + 2033 * __ROR4__(v428 - 1419157410, 29));
                                      v430 = v428 ^ (4991 * __ROR4__(v429 - 1419157410, 17) - __ROR4__(v429, 14));
                                      v431 = v429 ^ (v430 >> 3) ^ (43881 * (v430 ^ 0x605E));
                                      v432 = __ROR4__(v431, 30);
                                      v402 = v399 ^ v431;
                                      v399 = v409;
                                      v403 = v401
                                           ^ v430
                                           ^ v432
                                           ^ (24670
                                            * __ROR4__(v429 ^ (v430 >> 3) ^ (43881 * (v430 ^ 0x605E)) ^ 0x7F1137F, 28));
                                      v401 = v407;
                                      *((_BYTE *)v397 + 3) = v403;
                                      *((_BYTE *)v397 + 7) = v402;
                                      *((_BYTE *)v397 + 2) = __ROR4__(v403, 8);
                                      *((_BYTE *)v397 + 6) = __ROR4__(v402, 8);
                                      *((_BYTE *)v397 + 1) = __ROR4__(v403, 16);
                                      *((_BYTE *)v397 + 5) = __ROR4__(v402, 16);
                                      *(_BYTE *)v397 = __ROR4__(v403, 24);
                                      *((_BYTE *)v397 + 4) = __ROR4__(v402, 24);
                                      v397 += 4;
                                      --v400;
                                    }
                                    while ( v400 );
                                    v338 = (unsigned int)v1046;
                                    v94 = Src;
                                    v433 = 0;
                                    v434 = (WCHAR *)lpModuleName;
                                    v435 = 0;
                                    do
                                      v435 ^= *((_BYTE *)lpModuleName + v433++);
                                    while ( v433 < 0x338 );
                                    if ( v435 != 64 )
                                    {
                                      MemoryFree((void *)lpModuleName);
                                      goto LABEL_605;
                                    }
                                    LODWORD(Size) = 0;
                                    LODWORD(v1057) = 0;
                                    *((_BYTE *)lpModuleName + 823) = 0;
                                    memset_0(&unk_1800214D0, 0, 0x60u);
                                    if ( *(_BYTE *)v434 )
                                    {
                                      v438 = (unsigned int)v1057;
                                      v1063 = (SIZE_T)v434;
                                      while ( 1 )
                                      {
                                        v439 = -1;
                                        do
                                          ++v439;
                                        while ( v434[v439] );
                                        v1066 = 3 * v438;
                                        if ( !GetModuleHandleExW(0, v434, (HMODULE *)&unk_1800214D0 + 3 * v438) )
                                          break;
                                        v440 = v1066;
                                        v441 = &v434[v439];
                                        v442 = *((_QWORD *)&unk_1800214D0 + v1066);
                                        if ( *(_WORD *)v442 == 23117
                                          && (v444 = *(int *)(v442 + 60), (unsigned int)v444 < 0x10000000)
                                          && (v445 = *((_QWORD *)&unk_1800214D0 + v1066) + v444,
                                              v445 >= *((_QWORD *)&unk_1800214D0 + v1066))
                                          && *(_DWORD *)v445 == 17744 )
                                        {
                                          if ( ((*(_WORD *)(v445 + 24) - 267) & 0xFEFF) != 0 )
                                          {
                                            v443 = -1073741811;
                                          }
                                          else
                                          {
                                            v443 = 0;
                                            *(_QWORD *)((char *)&unk_1800214D0 + 8 * v1066 + 12) = *(_QWORD *)(v445 + 136);
                                            *((_DWORD *)&unk_1800214D0 + 2 * v440 + 2) = *(_DWORD *)(v445 + 80);
                                          }
                                        }
                                        else
                                        {
                                          v443 = -1073741701;
                                        }
                                        v446 = *(_DWORD *)(v441 + 1);
                                        v447 = 0;
                                        v434 = v441 + 3;
                                        LODWORD(v1054) = v446;
                                        LODWORD(v1056) = 0;
                                        if ( v446 )
                                        {
                                          do
                                          {
                                            v448 = -1;
                                            do
                                              ++v448;
                                            while ( *((_BYTE *)v434 + v448) );
                                            lpModuleName = (LPCWSTR)v448;
                                            if ( v443 >= 0 )
                                            {
                                              v449 = GetProcAddress(*((HMODULE *)&unk_1800214D0 + v440), (LPCSTR)v434);
                                              if ( !v449 )
                                                goto LABEL_634;
                                              v440 = v1066;
                                              off_180021000[(unsigned int)Size] = v449;
                                              v448 = (__int64)lpModuleName;
                                              v447 = v1056;
                                            }
                                            v434 = (WCHAR *)((char *)v434 + v448 + 1);
                                            LODWORD(Size) = Size + 1;
                                            LODWORD(v1056) = ++v447;
                                          }
                                          while ( v447 < (unsigned int)v1054 );
                                        }
                                        v438 = (unsigned int)((_DWORD)v1057 + 1);
                                        LODWORD(v1057) = (_DWORD)v1057 + 1;
                                        if ( !*(_BYTE *)v434 )
                                          goto LABEL_634;
                                      }
                                      v443 = -1073741702;
LABEL_634:
                                      v434 = (WCHAR *)v1063;
                                      if ( !v1063 )
                                        goto LABEL_638;
                                    }
                                    else
                                    {
                                      v443 = 0;
                                    }
                                    v450 = GetProcessHeap();
                                    HeapFree(v450, 0, v434);
LABEL_638:
                                    v100 = 0;
                                    if ( v443 < 0 )
                                    {
LABEL_606:
                                      for ( n = 0; n != 4; ++n )
                                      {
                                        v437 = (HMODULE)*((_QWORD *)&unk_1800214D0 + 3 * n);
                                        if ( v437 )
                                          FreeLibrary(v437);
                                      }
                                      memset_0(&unk_1800214D0, 0, 0x60u);
                                      memcpy_0(off_180021000, off_180015170, 0x170u);
LABEL_641:
                                      _InterlockedExchange(&dword_180021534, 0);
                                      memset_0(&v1098, 0, 0x70u);
                                      LOWORD(v1042) = (v338 >> 4) & 0xF;
                                      WORD1(v1042) = (v338 >> 8) & 0xF;
                                      WORD2(v1042) = (v338 >> 12) & 0xF;
                                      v1073 = 0;
                                      v1045 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))off_1800210F8[0])(
                                                0,
                                                0,
                                                1027);
                                      LODWORD(v1062) = 0xFFFFFF;
                                      if ( !v1045 )
                                      {
                                        v451 = GetLastError();
                                        v452 = v451;
                                        if ( v451 > 0 )
                                          v452 = (unsigned __int16)v451 | 0x80070000;
                                        if ( v452 >= 0 )
                                          v452 = -2147467259;
LABEL_847:
                                        while ( _InterlockedCompareExchange(&dword_180021534, 1, 0) )
                                          ;
                                        v573 = dword_180021530;
                                        if ( dword_180021530 > 0 )
                                        {
                                          --dword_180021530;
                                          if ( v573 == 1 )
                                          {
                                            do
                                            {
                                              v574 = (HMODULE)*((_QWORD *)&unk_1800214D0 + 3 * v100);
                                              if ( v574 )
                                                FreeLibrary(v574);
                                              ++v100;
                                            }
                                            while ( v100 != 4 );
                                            memset_0(&unk_1800214D0, 0, 0x60u);
                                            memcpy_0(off_180021000, off_180015170, 0x170u);
                                          }
                                        }
                                        _InterlockedExchange(&dword_180021534, 0);
                                        SP_MEM<unsigned short *>::~SP_MEM<unsigned short *>(&v1047);
                                        if ( v452 < 0 )
                                        {
LABEL_876:
                                          v583 = v1100;
                                          if ( v1100 )
                                          {
                                            v584 = -1;
                                            do
                                              ++v584;
                                            while ( *((_WORD *)v1100 + v584) );
                                            for ( ii = 2 * v584 + 2; ii; --ii )
                                              *v583++ = 0;
                                            MemoryFree(v1100);
                                            v1100 = 0;
                                          }
                                          v586 = v1101;
                                          if ( v1101 )
                                          {
                                            v587 = -1;
                                            do
                                              ++v587;
                                            while ( *((_WORD *)v1101 + v587) );
                                            for ( jj = 2 * v587 + 2; jj; --jj )
                                              *v586++ = 0;
                                            MemoryFree(v1101);
                                            v1101 = 0;
                                          }
                                          v589 = v1102;
                                          if ( v1102 )
                                          {
                                            v590 = -1;
                                            do
                                              ++v590;
                                            while ( *((_WORD *)v1102 + v590) );
                                            v591 = 2 * v590 + 2;
                                            if ( v591 )
                                            {
                                              do
                                              {
                                                *v589++ = 0;
                                                --v591;
                                              }
                                              while ( v591 );
                                              v589 = v1102;
                                            }
                                            MemoryFree(v589);
                                            v1102 = 0;
                                          }
                                          if ( v1103 )
                                          {
                                            off_180021038[0]();
                                            v1103 = 0;
                                          }
                                          if ( v1104 )
                                          {
                                            off_180021038[0]();
                                            v1104 = 0;
                                          }
                                          if ( v1105 )
                                          {
                                            off_180021038[0]();
                                            v1105 = 0;
                                          }
                                          while ( _InterlockedCompareExchange(&dword_180021534, 1, 0) )
                                            ;
                                          v592 = dword_180021530;
                                          if ( dword_180021530 > 0 )
                                          {
                                            --dword_180021530;
                                            if ( v592 == 1 )
                                            {
                                              for ( kk = 0; kk != 4; ++kk )
                                              {
                                                v594 = (HMODULE)*((_QWORD *)&unk_1800214D0 + 3 * kk);
                                                if ( v594 )
                                                  FreeLibrary(v594);
                                              }
                                              memset_0(&unk_1800214D0, 0, 0x60u);
                                              memcpy_0(off_180021000, off_180015170, 0x170u);
                                            }
                                          }
                                          _InterlockedExchange(&dword_180021534, 0);
                                          v595 = qword_1800214B0;
                                          LODWORD(v1047) = dword_1800214C0;
                                          v596 = (unsigned int)off_180021098[0]() - v595;
                                          v1045 = v596;
                                          v1188 = 0;
                                          v1184 = 0;
                                          v1185 = 0;
                                          v1186 = 0;
                                          v1187 = 0;
                                          while ( _InterlockedCompareExchange(&dword_180021534, 1, 0) )
                                            ;
                                          v738 = dword_180021530;
                                          if ( dword_180021530 )
                                            goto LABEL_1146;
                                          v739 = (const WCHAR *)MemoryAlloc(0x338u);
                                          v740 = 0;
                                          v1072 = v739;
                                          if ( !v739 )
                                            goto LABEL_1111;
                                          v741 = (WCHAR *)v739;
                                          v742 = (unsigned __int8 *)&unk_18001E940;
                                          v743 = 103;
                                          v744 = 0;
                                          v745 = -1;
                                          v746 = 0;
                                          do
                                          {
                                            v747 = *v742 << 8;
                                            v748 = v742[1];
                                            v749 = v742[4];
                                            v742 += 8;
                                            v750 = *(v742 - 5) | ((*(v742 - 6) | ((v747 | v748) << 8)) << 8);
                                            v751 = v740 ^ v750;
                                            v752 = *(v742 - 1)
                                                 | ((*(v742 - 2) | ((*(v742 - 3) | (v749 << 8)) << 8)) << 8);
                                            v753 = v740 ^ v750 ^ v746 ^ v752 ^ 0xAC987321;
                                            v754 = v751 ^ (__ROR4__(v753, 22) + 4991 * __ROR4__(v753 + 1419157410, 27));
                                            v755 = v753 ^ (43881 * __ROR4__(v754 + 133239679, 9) - __ROR4__(v754, 30));
                                            v756 = v754 ^ (24670 * v755 - (v755 >> 13) - 123127970);
                                            v757 = v755 ^ (2033 * __ROR4__(v756 ^ 0xAB69, 26) - __ROR4__(v756, 30));
                                            v758 = v756 ^ (133239679 - (v757 ^ 0xAB69605E));
                                            v759 = v757 ^ (43881 * (v758 ^ 0x137F)) ^ __ROR4__(v758, 6);
                                            v760 = v758 ^ (__ROR4__(v759, 30) + 24670 * __ROR4__(v759 + 133239679, 15));
                                            v761 = v759 ^ (2033 * __ROR4__(v760 + 1419157410, 14) - __ROR4__(v760, 24));
                                            v762 = v760 ^ __ROR4__(v761, 10) ^ (4991 * __ROR4__(v761 ^ 0xAB69605E, 12));
                                            v763 = v761 ^ (v762 >> 10) ^ (43881 * (v762 ^ 0x7F1));
                                            v764 = v762 ^ (2033 * (__ROR4__(~v763, 5) + 24670));
                                            v765 = v764
                                                 ^ (((v763 ^ (v764 - 2033) ^ 0xAB69605E) >> 2)
                                                  + 4991 * __ROR4__(v763 ^ (v764 - 2033) ^ 0xAB6967AF, 30));
                                            v766 = v763
                                                 ^ (v764 - 2033)
                                                 ^ 0xAB69605E
                                                 ^ (__ROR4__(v765, 25) + 43881 * __ROR4__(v765 - 133239679, 6));
                                            v767 = v765 ^ (24670 * (v766 ^ 0x137F) + __ROR4__(v766, 9));
                                            v768 = v766 ^ (__ROR4__(v767, 25) + 2033 * __ROR4__(v767 ^ 0xAB69, 27));
                                            v769 = v767 ^ v768 ^ 0xAC987321;
                                            v770 = v768 ^ (4991 * __ROR4__(v769, 3) - 219010071);
                                            v771 = v769 ^ (24670 * __ROR4__(v770 - 133239679, 1) - __ROR4__(v770, 6));
                                            v772 = v770 ^ (__ROR4__(v771, 18) + 2033 * __ROR4__(v771 - 1419157410, 29));
                                            v773 = v771 ^ (4991 * __ROR4__(v772 - 1419157410, 17) - __ROR4__(v772, 14));
                                            v774 = v772 ^ (v773 >> 3) ^ (43881 * (v773 ^ 0x605E));
                                            v775 = __ROR4__(v774, 30);
                                            v746 = v745 ^ v774;
                                            v745 = v752;
                                            v740 = v744
                                                 ^ v773
                                                 ^ v775
                                                 ^ (24670
                                                  * __ROR4__(
                                                      v772 ^ (v773 >> 3) ^ (43881 * (v773 ^ 0x605E)) ^ 0x7F1137F,
                                                      28));
                                            v744 = v750;
                                            *((_BYTE *)v741 + 3) = v740;
                                            *((_BYTE *)v741 + 7) = v746;
                                            *((_BYTE *)v741 + 2) = __ROR4__(v740, 8);
                                            *((_BYTE *)v741 + 6) = __ROR4__(v746, 8);
                                            *((_BYTE *)v741 + 1) = __ROR4__(v740, 16);
                                            *((_BYTE *)v741 + 5) = __ROR4__(v746, 16);
                                            *(_BYTE *)v741 = __ROR4__(v740, 24);
                                            *((_BYTE *)v741 + 4) = __ROR4__(v746, 24);
                                            v741 += 4;
                                            --v743;
                                          }
                                          while ( v743 );
                                          v94 = Src;
                                          v776 = (WCHAR *)v1072;
                                          v777 = 0;
                                          v778 = 0;
                                          do
                                            v778 ^= *((_BYTE *)v1072 + v777++);
                                          while ( v777 < 0x338 );
                                          if ( v778 != 64 )
                                          {
                                            MemoryFree((void *)v1072);
LABEL_1110:
                                            LODWORD(v596) = v1045;
LABEL_1111:
                                            for ( mm = 0; mm != 4; ++mm )
                                            {
                                              v780 = (HMODULE)*((_QWORD *)&unk_1800214D0 + 3 * mm);
                                              if ( v780 )
                                                FreeLibrary(v780);
                                            }
                                            memset_0(&unk_1800214D0, 0, 0x60u);
                                            memcpy_0(off_180021000, off_180015170, 0x170u);
                                            goto LABEL_1147;
                                          }
                                          LODWORD(v1056) = 0;
                                          LODWORD(v1065) = 0;
                                          v781 = 0;
                                          *((_BYTE *)v1072 + 823) = 0;
                                          memset_0(&unk_1800214D0, 0, 0x60u);
                                          if ( *(_BYTE *)v776 )
                                          {
                                            v1063 = (SIZE_T)v776;
                                            while ( 1 )
                                            {
                                              v782 = -1;
                                              do
                                                ++v782;
                                              while ( v776[v782] );
                                              v783 = 3LL * v781;
                                              v784 = (HMODULE *)((char *)&unk_1800214D0 + 24 * v781);
                                              pcchLength = v783;
                                              if ( !GetModuleHandleExW(0, v776, v784) )
                                                break;
                                              v785 = &v776[v782];
                                              if ( *(_WORD *)*v784 == 23117
                                                && (v788 = *((int *)*v784 + 15), (unsigned int)v788 < 0x10000000)
                                                && (v789 = (char *)*v784 + v788, v789 >= (char *)*v784)
                                                && *(_DWORD *)v789 == 17744 )
                                              {
                                                v786 = pcchLength;
                                                if ( ((*((_WORD *)v789 + 12) - 267) & 0xFEFF) != 0 )
                                                {
                                                  v787 = -1073741811;
                                                }
                                                else
                                                {
                                                  v787 = 0;
                                                  *(_QWORD *)((char *)&unk_1800214D0 + 8 * pcchLength + 12) = *((_QWORD *)v789 + 17);
                                                  *((_DWORD *)&unk_1800214D0 + 2 * v786 + 2) = *((_DWORD *)v789 + 20);
                                                }
                                              }
                                              else
                                              {
                                                v786 = pcchLength;
                                                v787 = -1073741701;
                                              }
                                              v790 = *(_DWORD *)(v785 + 1);
                                              v791 = 0;
                                              v776 = v785 + 3;
                                              LODWORD(v1042) = v790;
                                              for ( LODWORD(v1054) = 0; v791 < v790; LODWORD(v1054) = v791 )
                                              {
                                                v792 = -1;
                                                do
                                                  ++v792;
                                                while ( *((_BYTE *)v776 + v792) );
                                                if ( v787 < 0 )
                                                {
                                                  v794 = v1056;
                                                }
                                                else
                                                {
                                                  v793 = GetProcAddress(
                                                           *((HMODULE *)&unk_1800214D0 + v786),
                                                           (LPCSTR)v776);
                                                  if ( !v793 )
                                                    goto LABEL_1140;
                                                  v794 = v1056;
                                                  v790 = (unsigned int)v1042;
                                                  off_180021000[(unsigned int)v1056] = v793;
                                                  v791 = v1054;
                                                }
                                                LODWORD(v1056) = v794 + 1;
                                                v786 = pcchLength;
                                                ++v791;
                                                v776 = (WCHAR *)((char *)v776 + v792 + 1);
                                              }
                                              v781 = v1065 + 1;
                                              LODWORD(v1065) = v1065 + 1;
                                              if ( !*(_BYTE *)v776 )
                                                goto LABEL_1140;
                                            }
                                            v787 = -1073741702;
LABEL_1140:
                                            v776 = (WCHAR *)v1063;
                                            if ( !v1063 )
                                              goto LABEL_1144;
                                          }
                                          else
                                          {
                                            v787 = 0;
                                          }
                                          v795 = GetProcessHeap();
                                          HeapFree(v795, 0, v776);
LABEL_1144:
                                          if ( v787 < 0 )
                                            goto LABEL_1110;
                                          v738 = dword_180021530;
                                          LODWORD(v596) = v1045;
LABEL_1146:
                                          dword_180021530 = v738 + 1;
LABEL_1147:
                                          _InterlockedExchange(&dword_180021534, 0);
                                          LODWORD(v1188) = (_DWORD)v1047;
                                          LODWORD(v1185) = v596;
                                          v1184 = 1;
                                          LODWORD(v1186) = -1721306479;
                                          DWORD2(v1185) = 1;
                                          LODWORD(v1187) = 1;
                                          DWORD2(v1186) = 1;
                                          DWORD2(v1187) = 1;
                                          ((void (__fastcall *)(_QWORD, __int64, __int64, int *))qword_1800210D0)(
                                            0,
                                            8225,
                                            4,
                                            &v1184);
                                          while ( _InterlockedCompareExchange(&dword_180021534, 1, 0) )
                                            ;
                                          v796 = dword_180021530;
                                          v100 = 0;
                                          if ( dword_180021530 > 0 )
                                          {
                                            --dword_180021530;
                                            if ( v796 == 1 )
                                            {
                                              for ( nn = 0; nn != 4; ++nn )
                                              {
                                                v798 = (HMODULE)*((_QWORD *)&unk_1800214D0 + 3 * nn);
                                                if ( v798 )
                                                  FreeLibrary(v798);
                                              }
                                              memset_0(&unk_1800214D0, 0, 0x60u);
                                              memcpy_0(off_180021000, off_180015170, 0x170u);
                                            }
                                          }
                                          _InterlockedExchange(&dword_180021534, 0);
                                          ((void (__fastcall *)(_QWORD, LPVOID))off_180021160[0])(0, v1059);
                                          goto LABEL_1157;
                                        }
                                        v575 = v1073;
                                        v1061 = 0;
                                        v1066 = v1073;
                                        v1119 = 0;
                                        memset_0(v1120, 0, 0x64u);
                                        v576 = ((__int64 (__fastcall *)(LPVOID, __int64))off_180021050[0])(v1059, 7);
                                        if ( v576
                                          && ((unsigned int (__fastcall *)(__int64, __int64, int *))off_180021068[0])(
                                               v576,
                                               104,
                                               &v1119) )
                                        {
                                          if ( v1121 != 32
                                            || !v1122
                                            || v1120[0] <= 0
                                            || (v577 = 1, LODWORD(Size) = 1, v1120[1] <= 0) )
                                          {
                                            v577 = 0;
                                            LODWORD(Size) = 0;
                                          }
                                          v578 = v338 & 0xF;
                                          v579 = v578;
                                          if ( v577 )
                                          {
LABEL_866:
                                            ((void (__fastcall *)(int *, _QWORD, _QWORD))off_180021150)(
                                              &v1107,
                                              v575,
                                              HIDWORD(v1066));
                                            ((void (__fastcall *)(int *, _QWORD, _QWORD))off_180021150)(
                                              &v1111,
                                              v575,
                                              HIDWORD(v1066));
                                            if ( v578 == 1 )
                                              v1061 = (char *)((__int64 (__fastcall *)(_QWORD))off_180021028[0])(v1099 == 0 ? 0xB26720 : 0);
LABEL_868:
                                            v580 = v1059;
                                            LODWORD(v1042) = ((__int64 (__fastcall *)(LPVOID, __int64))off_180021080[0])(
                                                               v1059,
                                                               1);
                                            v581 = 2064;
                                            if ( v1098 )
                                              v581 = 133138;
                                            v1032 = v581;
                                            if ( (_DWORD)Size )
                                            {
                                              v1123 = 0;
                                              memset_0(v1124, 0, 0x64u);
                                              v1138 = 0;
                                              memset_0(v1139, 0, 0x64u);
                                              v1045 = (SIZE_T)v1100;
                                              memset(v1159, 0, 28);
                                              v1158 = 0;
                                              v1150 = 0;
                                              if ( !v1100 )
                                                goto LABEL_874;
                                              LODWORD(v1054) = v1099;
                                              lpModuleName = v1103;
                                              v582 = ((__int64 (__fastcall *)(LPVOID, __int64))off_180021050[0])(
                                                       v580,
                                                       7);
                                              if ( v582 )
                                              {
                                                if ( ((unsigned int (__fastcall *)(__int64, __int64, int *))off_180021068[0])(
                                                       v582,
                                                       104,
                                                       &v1123) )
                                                {
                                                  v1063 = v1125;
                                                  LODWORD(v1056) = v1124[0];
                                                  LODWORD(v1067) = v1124[1];
                                                }
                                                else
                                                {
                                                  v1063 = 0;
                                                  LODWORD(v1067) = 0;
                                                  LODWORD(v1056) = 0;
                                                }
                                                pcchLength = ((__int64 (__fastcall *)(LPVOID))off_180021010[0])(v580);
                                                v597 = pcchLength;
                                                if ( pcchLength )
                                                {
                                                  DWORD1(v1158) = v1109 - v1107;
                                                  DWORD2(v1158) = v1108 - v1110;
                                                  v1089 = 0;
                                                  memset(v1159, 0, 28);
                                                  LODWORD(v1158) = 40;
                                                  HIDWORD(v1158) = 2097153;
                                                  v598 = ((__int64 (__fastcall *)(size_t, __int128 *, _QWORD, __int64 *, _QWORD, _DWORD))off_180021018[0])(
                                                           pcchLength,
                                                           &v1158,
                                                           0,
                                                           &v1089,
                                                           0,
                                                           0);
                                                  v1043 = v598;
                                                  if ( v598 )
                                                  {
                                                    v602 = ((__int64 (__fastcall *)(SIZE_T, __int64, int *))off_180021068[0])(
                                                             v598,
                                                             104,
                                                             &v1138);
                                                    LODWORD(v1051) = 0;
                                                    if ( v602 )
                                                      v1066 = v1140;
                                                    else
                                                      v1066 = 0;
                                                    DWORD2(v1150) = v1109 - v1107;
                                                    HIDWORD(v1150) = v1110 - v1108;
                                                    ((void (__fastcall *)(size_t, SIZE_T))off_180021078[0])(v597, v1043);
                                                    ((void (__fastcall *)(size_t, __int64))off_180021080[0])(v597, 1);
                                                    v603 = (void *)((__int64 (__fastcall *)(size_t, LPCWSTR))off_180021078[0])(
                                                                     v597,
                                                                     lpModuleName);
                                                    v604 = off_1800210E8[0];
                                                    v1047 = v603;
                                                    v605 = ((__int64 (__fastcall *)(_QWORD))off_180021070[0])(0);
                                                    ((void (__fastcall *)(size_t, __int128 *, __int64))v604)(
                                                      pcchLength,
                                                      &v1150,
                                                      v605);
                                                    ((void (__fastcall *)(size_t, SIZE_T, __int64, __int128 *, int, _QWORD))off_1800210D8[0])(
                                                      pcchLength,
                                                      v1045,
                                                      0xFFFFFFFFLL,
                                                      &v1150,
                                                      v1032,
                                                      0);
                                                    v606 = 0;
                                                    if ( v578 == 1 )
                                                    {
                                                      if ( (_DWORD)v1054 )
                                                      {
                                                        v607 = ((__int64 (__fastcall *)(__int64))off_180021118[0])(8);
                                                        v606 = 0;
                                                      }
                                                      else
                                                      {
                                                        v607 = 0xFFFFFF;
                                                      }
                                                    }
                                                    else
                                                    {
                                                      v607 = -5723992;
                                                    }
                                                    v608 = 0;
                                                    v609 = -v1107;
                                                    LODWORD(Size) = v607;
                                                    if ( v1107 >= 0 )
                                                    {
                                                      v608 = v1107;
                                                      v609 = 0;
                                                    }
                                                    v610 = -v1108;
                                                    if ( v1108 >= 0 )
                                                    {
                                                      v610 = 0;
                                                      v606 = v1108;
                                                    }
                                                    v611 = DWORD2(v1150) - v609;
                                                    if ( DWORD2(v1150) - v609 >= (int)v1056 - v608 )
                                                      v611 = v1056 - v608;
                                                    LODWORD(v1054) = v611;
                                                    v612 = HIDWORD(v1150) - v610;
                                                    if ( HIDWORD(v1150) - v610 >= (int)v1067 - v606 )
                                                      v612 = (_DWORD)v1067 - v606;
                                                    LODWORD(v1050) = v612;
                                                    if ( v611 <= 0 || v612 <= 0 )
                                                    {
                                                      v601 = v1051;
                                                    }
                                                    else
                                                    {
                                                      v613 = Size;
                                                      v614 = v1054;
                                                      LODWORD(v1067) = 0;
                                                      v615 = (char *)(v1066
                                                                    + 4 * (v609 + (__int64)(v610 * DWORD2(v1150))));
                                                      v1045 = (SIZE_T)v615;
                                                      v616 = (char *)(v1063 + 4 * (v608 + (__int64)(v606 * (int)v1056)));
                                                      LODWORD(v1065) = (unsigned int)Size >> 8;
                                                      LODWORD(v1044) = WORD1(Size);
                                                      lpModuleName = (LPCWSTR)(4LL * SDWORD2(v1150));
                                                      lpMem = (LPVOID)(4LL * (int)v1056);
                                                      v1063 = (SIZE_T)v616;
                                                      do
                                                      {
                                                        v617 = v1051;
                                                        v618 = 0;
                                                        v619 = v1065;
                                                        v620 = (unsigned __int8 *)v615;
                                                        v1066 = (SIZE_T)v615;
                                                        v621 = v616;
                                                        v622 = (char)v1044;
                                                        LODWORD(v1056) = 0;
                                                        do
                                                        {
                                                          v623 = ~(unsigned __int8)((*v620
                                                                                   + v620[2]
                                                                                   + 2 * (unsigned int)v620[1]) >> 2);
                                                          if ( (unsigned __int8)((*v620
                                                                                + v620[2]
                                                                                + 2 * (unsigned int)v620[1]) >> 2) != 0xFF )
                                                          {
                                                            v624 = (unsigned __int8)v621[2];
                                                            v625 = v623;
                                                            v626 = (int)((unsigned __int64)(2155905153LL
                                                                                          * v623
                                                                                          * (v613 - v624)) >> 32) >> 7;
                                                            v621[2] = v624 + (v626 < 0) + v626;
                                                            v621[1] -= v625 * (v619 - v621[1]);
                                                            *v621 -= v625 * (v622 - *v621);
                                                            v627 = (unsigned __int8)v621[3];
                                                            v628 = v625 * (255 - v627);
                                                            v618 = v1056;
                                                            LOBYTE(v626) = v627 + v628 / 255;
                                                            v620 = (unsigned __int8 *)v1066;
                                                            v621[3] = v626;
                                                          }
                                                          v620 += 4;
                                                          ++v618;
                                                          v621 += 4;
                                                          v1066 = (SIZE_T)v620;
                                                          LODWORD(v1056) = v618;
                                                        }
                                                        while ( v618 < v614 );
                                                        v615 = (char *)lpModuleName + v1045;
                                                        v616 = (char *)lpMem + v1063;
                                                        v1045 += (SIZE_T)lpModuleName;
                                                        v1063 += (SIZE_T)lpMem;
                                                        LODWORD(v1067) = (_DWORD)v1067 + 1;
                                                        LODWORD(v1051) = v617;
                                                      }
                                                      while ( (int)v1067 < (int)v1050 );
                                                      v94 = Src;
                                                      v601 = v617;
                                                    }
                                                    ((void (__fastcall *)(SIZE_T))off_180021038[0])(v1043);
                                                    v600 = 0;
                                                    if ( v1047 )
                                                      ((void (__fastcall *)(size_t, LPVOID))off_180021078[0])(
                                                        pcchLength,
                                                        v1047);
                                                  }
                                                  else
                                                  {
                                                    v599 = GetLastError();
                                                    v600 = 0;
                                                    v601 = v599;
                                                    if ( v599 > 0 )
                                                      v601 = (unsigned __int16)v599 | 0x80070000;
                                                    if ( v601 >= 0 )
                                                      v601 = -2147467259;
                                                  }
                                                  ((void (__fastcall *)(size_t))off_180021030[0])(pcchLength);
                                                  if ( v601 < 0 )
                                                    goto LABEL_874;
                                                  v1126 = 0;
                                                  memset_0(v1127, 0, 0x64u);
                                                  v1135 = 0;
                                                  memset_0(v1136, 0, 0x64u);
                                                  v1045 = (SIZE_T)v1101;
                                                  memset(v1161, 0, 28);
                                                  v1160 = 0;
                                                  v1147 = 0;
                                                  if ( !v1101 )
                                                    goto LABEL_874;
                                                  v629 = v1059;
                                                  LODWORD(v1054) = v1099;
                                                  lpModuleName = v1104;
                                                  v630 = ((__int64 (__fastcall *)(LPVOID, __int64))off_180021050[0])(
                                                           v1059,
                                                           7);
                                                  if ( v630 )
                                                  {
                                                    if ( ((unsigned int (__fastcall *)(__int64, __int64, int *))off_180021068[0])(
                                                           v630,
                                                           104,
                                                           &v1126) )
                                                    {
                                                      LODWORD(v1056) = v1127[0];
                                                      pcchLength = v1128;
                                                      v600 = 0;
                                                      LODWORD(v1067) = v1127[1];
                                                    }
                                                    else
                                                    {
                                                      pcchLength = 0;
                                                      LODWORD(v1067) = 0;
                                                      LODWORD(v1056) = 0;
                                                    }
                                                    v631 = ((__int64 (__fastcall *)(LPVOID))off_180021010[0])(v629);
                                                    v1063 = v631;
                                                    v632 = v631;
                                                    if ( v631 )
                                                    {
                                                      DWORD1(v1160) = v1113 - v1111;
                                                      DWORD2(v1160) = v1112 - v1114;
                                                      v1090 = 0;
                                                      memset(v1161, 0, 28);
                                                      LODWORD(v1160) = 40;
                                                      HIDWORD(v1160) = 2097153;
                                                      v633 = ((__int64 (__fastcall *)(SIZE_T, __int128 *, _QWORD, __int64 *, _QWORD, _DWORD))off_180021018[0])(
                                                               v631,
                                                               &v1160,
                                                               0,
                                                               &v1090,
                                                               0,
                                                               0);
                                                      v1043 = v633;
                                                      if ( v633 )
                                                      {
                                                        if ( ((unsigned int (__fastcall *)(SIZE_T, __int64, int *))off_180021068[0])(
                                                               v633,
                                                               104,
                                                               &v1135) )
                                                        {
                                                          v1066 = v1137;
                                                        }
                                                        else
                                                        {
                                                          v1066 = 0;
                                                        }
                                                        DWORD2(v1147) = v1113 - v1111;
                                                        HIDWORD(v1147) = v1114 - v1112;
                                                        ((void (__fastcall *)(SIZE_T, SIZE_T))off_180021078[0])(
                                                          v632,
                                                          v1043);
                                                        ((void (__fastcall *)(SIZE_T, __int64))off_180021080[0])(
                                                          v632,
                                                          1);
                                                        v635 = (void *)((__int64 (__fastcall *)(SIZE_T, LPCWSTR))off_180021078[0])(
                                                                         v632,
                                                                         lpModuleName);
                                                        v636 = off_1800210E8[0];
                                                        v1047 = v635;
                                                        v637 = ((__int64 (__fastcall *)(_QWORD))off_180021070[0])(0);
                                                        ((void (__fastcall *)(SIZE_T, __int128 *, __int64))v636)(
                                                          v1063,
                                                          &v1147,
                                                          v637);
                                                        v632 = v1063;
                                                        ((void (__fastcall *)(SIZE_T, SIZE_T, __int64, __int128 *, int, _QWORD))off_1800210D8[0])(
                                                          v1063,
                                                          v1045,
                                                          0xFFFFFFFFLL,
                                                          &v1147,
                                                          v1032,
                                                          0);
                                                        if ( v579 == 1 )
                                                        {
                                                          v638 = 0;
                                                          if ( (_DWORD)v1054 )
                                                            LODWORD(v1062) = ((__int64 (__fastcall *)(__int64))off_180021118[0])(8);
                                                        }
                                                        else
                                                        {
                                                          LODWORD(v1062) = -5723992;
                                                          v638 = 0;
                                                        }
                                                        v639 = 0;
                                                        v640 = -v1111;
                                                        if ( v1111 >= 0 )
                                                        {
                                                          v639 = v1111;
                                                          v640 = 0;
                                                        }
                                                        v641 = -v1112;
                                                        if ( v1112 >= 0 )
                                                        {
                                                          v641 = 0;
                                                          v638 = v1112;
                                                        }
                                                        v642 = DWORD2(v1147) - v640;
                                                        if ( DWORD2(v1147) - v640 >= (int)v1056 - v639 )
                                                          v642 = v1056 - v639;
                                                        LODWORD(v1054) = v642;
                                                        v643 = HIDWORD(v1147) - v641;
                                                        if ( HIDWORD(v1147) - v641 >= (int)v1067 - v638 )
                                                          v643 = (_DWORD)v1067 - v638;
                                                        LODWORD(v1050) = v643;
                                                        if ( v642 > 0 && v643 > 0 )
                                                        {
                                                          v644 = v1054;
                                                          LODWORD(v1067) = 0;
                                                          v645 = (char *)(v1066
                                                                        + 4 * (v640 + (__int64)(v641 * DWORD2(v1147))));
                                                          v1045 = (SIZE_T)v645;
                                                          v646 = (char *)(pcchLength
                                                                        + 4 * (v639 + (__int64)(v638 * (int)v1056)));
                                                          LODWORD(v1065) = (unsigned int)v1062 >> 8;
                                                          LODWORD(v1044) = WORD1(v1062);
                                                          lpModuleName = (LPCWSTR)(4LL * SDWORD2(v1147));
                                                          lpMem = (LPVOID)(4LL * (int)v1056);
                                                          pcchLength = (size_t)v646;
                                                          do
                                                          {
                                                            v647 = v1065;
                                                            v648 = 0;
                                                            v649 = (char)v1044;
                                                            v650 = (unsigned __int8 *)v645;
                                                            v651 = v1062;
                                                            v652 = v646;
                                                            LODWORD(v1056) = 0;
                                                            v1066 = (SIZE_T)v645;
                                                            do
                                                            {
                                                              v653 = ~(unsigned __int8)((*v650
                                                                                       + v650[2]
                                                                                       + 2 * (unsigned int)v650[1]) >> 2);
                                                              if ( (unsigned __int8)((*v650
                                                                                    + v650[2]
                                                                                    + 2 * (unsigned int)v650[1]) >> 2) != 0xFF )
                                                              {
                                                                v654 = (unsigned __int8)v652[2];
                                                                v655 = v653;
                                                                v656 = (int)((unsigned __int64)(2155905153LL
                                                                                              * v653
                                                                                              * (v651 - v654)) >> 32) >> 7;
                                                                v652[2] = v654 + (v656 < 0) + v656;
                                                                v652[1] -= v655 * (v647 - v652[1]);
                                                                *v652 -= v655 * (v649 - *v652);
                                                                v657 = (unsigned __int8)v652[3];
                                                                v658 = v655 * (255 - v657);
                                                                v648 = v1056;
                                                                LOBYTE(v656) = v657 + v658 / 255;
                                                                v650 = (unsigned __int8 *)v1066;
                                                                v652[3] = v656;
                                                              }
                                                              v650 += 4;
                                                              ++v648;
                                                              v652 += 4;
                                                              v1066 = (SIZE_T)v650;
                                                              LODWORD(v1056) = v648;
                                                            }
                                                            while ( v648 < v644 );
                                                            v645 = (char *)lpModuleName + v1045;
                                                            v646 = (char *)lpMem + pcchLength;
                                                            v1045 += (SIZE_T)lpModuleName;
                                                            pcchLength += (size_t)lpMem;
                                                            LODWORD(v1067) = (_DWORD)v1067 + 1;
                                                          }
                                                          while ( (int)v1067 < (int)v1050 );
                                                          v94 = Src;
                                                          v632 = v1063;
                                                        }
                                                        ((void (__fastcall *)(SIZE_T))off_180021038[0])(v1043);
                                                        if ( v1047 )
                                                          ((void (__fastcall *)(SIZE_T, LPVOID))off_180021078[0])(
                                                            v632,
                                                            v1047);
                                                      }
                                                      else
                                                      {
                                                        v634 = GetLastError();
                                                        v600 = v634;
                                                        if ( v634 > 0 )
                                                          v600 = (unsigned __int16)v634 | 0x80070000;
                                                        if ( v600 >= 0 )
                                                          v600 = -2147467259;
                                                      }
                                                      ((void (__fastcall *)(SIZE_T))off_180021030[0])(v632);
                                                      if ( v600 < 0 )
                                                        goto LABEL_874;
                                                      v659 = 0;
                                                      v660 = 0;
                                                      v661 = v1059;
LABEL_1099:
                                                      ((void (__fastcall *)(LPVOID, _QWORD))off_180021080[0])(
                                                        v661,
                                                        (unsigned int)v1042);
                                                      if ( !v659 )
                                                      {
LABEL_1012:
                                                        if ( !v660 )
                                                          goto LABEL_874;
                                                        goto LABEL_1013;
                                                      }
LABEL_1011:
                                                      ((void (__fastcall *)(SIZE_T))off_180021038[0])(v659);
                                                      goto LABEL_1012;
                                                    }
                                                  }
                                                }
                                              }
LABEL_873:
                                              GetLastError();
                                              goto LABEL_874;
                                            }
                                            if ( v1099 || (v662 = -64, v579 == 1) )
                                              v662 = -1;
                                            BYTE2(v1057) = v662;
                                            LOWORD(v1057) = 0;
                                            BYTE3(v1057) = 1;
                                            v1043 = ((__int64 (__fastcall *)(LPVOID))off_180021010[0])(v580);
                                            if ( !v1043 )
                                              goto LABEL_873;
                                            v663 = v1107;
                                            if ( v579 == 1 )
                                            {
                                              v664 = v1113 - v1111;
                                              LODWORD(v1060) = 0;
                                              if ( v1113 - v1111 <= v1109 - v1107 )
                                                v664 = v1109 - v1107;
                                              LODWORD(Size) = v664;
                                              LODWORD(v1051) = v1114 - v1108;
                                              if ( v1098 )
                                              {
                                                v663 = v664 + v1107 - v1109;
                                                v665 = v664 + v1111 - v1113;
                                              }
                                              else
                                              {
                                                v663 = 0;
                                                v665 = 0;
                                              }
                                              v666 = v663 + v1109 - v1107;
                                              LODWORD(v1065) = v1110 - v1108;
                                              LODWORD(v1056) = v1112 - v1108;
                                              v667 = v1113 - v1111 + v665;
                                              v668 = (int)v1060;
                                              LODWORD(v1067) = v1114 - v1108;
                                              LODWORD(v1046) = v665;
                                            }
                                            else
                                            {
                                              v664 = DWORD2(v1073);
                                              v668 = v1108;
                                              v666 = v1109;
                                              v667 = v1113;
                                              LODWORD(v1051) = HIDWORD(v1073);
                                              LODWORD(v1065) = v1110;
                                              LODWORD(v1046) = v1111;
                                              LODWORD(v1056) = v1112;
                                              LODWORD(v1067) = v1114;
                                              LODWORD(Size) = DWORD2(v1073);
                                              LODWORD(v1060) = v1108;
                                            }
                                            v1154[2] = -(int)v1051;
                                            LODWORD(v1058) = v667;
                                            v1091 = 0;
                                            v1154[1] = v664;
                                            LODWORD(v1052) = v666;
                                            LODWORD(v1050) = v663;
                                            memset(&v1154[4], 0, 28);
                                            v1154[0] = 40;
                                            v1154[3] = 2097153;
                                            v669 = ((__int64 (__fastcall *)(SIZE_T, _DWORD *, _QWORD, __int64 *, _QWORD, _DWORD))off_180021018[0])(
                                                     v1043,
                                                     v1154,
                                                     0,
                                                     &v1091,
                                                     0,
                                                     0);
                                            v1045 = v669;
                                            if ( !v669 )
                                            {
                                              GetLastError();
                                              v660 = v1043;
LABEL_1013:
                                              ((void (__fastcall *)(SIZE_T))off_180021030[0])(v660);
LABEL_874:
                                              if ( v1061 )
                                                ((void (__fastcall *)(char *))off_180021038[0])(v1061);
                                              goto LABEL_876;
                                            }
                                            ((void (__fastcall *)(SIZE_T, SIZE_T))off_180021078[0])(v1043, v669);
                                            if ( v579 == 1 && v1061 )
                                            {
                                              v1151 = 0;
                                              v1152 = Size;
                                              v1153 = v1051;
                                              ((void (__fastcall *)(SIZE_T, __int64 *))off_1800210E8[0])(v1043, &v1151);
                                            }
                                            v1129 = 0;
                                            memset_0(v1130, 0, 0x64u);
                                            v1141 = 0;
                                            memset_0(v1142, 0, 0x64u);
                                            v1074 = (SIZE_T)v1100;
                                            memset(v1163, 0, 28);
                                            v1162 = 0;
                                            v1148 = 0;
                                            if ( v1100 )
                                            {
                                              LODWORD(v1047) = v1099;
                                              lpMem = v1103;
                                              v670 = ((__int64 (__fastcall *)(SIZE_T, __int64))off_180021050[0])(
                                                       v1043,
                                                       7);
                                              if ( v670
                                                && (!((unsigned int (__fastcall *)(__int64, __int64, int *))off_180021068[0])(
                                                       v670,
                                                       104,
                                                       &v1129)
                                                  ? (v1063 = 0, LODWORD(v1054) = 0, LODWORD(v1044) = 0)
                                                  : (v1063 = v1131, LODWORD(v1044) = v1130[0], LODWORD(v1054) = v1130[1]),
                                                    v671 = ((__int64 (__fastcall *)(SIZE_T))off_180021010[0])(v1043),
                                                    (pcchLength = v671) != 0) )
                                              {
                                                v1093 = 0;
                                                v672 = (_DWORD)v1052 - v663;
                                                LODWORD(v1162) = 40;
                                                v673 = v1065;
                                                DWORD2(v1162) = v668 - v1065;
                                                v674 = 0;
                                                LODWORD(v1052) = v672;
                                                DWORD1(v1162) = v672;
                                                memset(v1163, 0, 28);
                                                HIDWORD(v1162) = 2097153;
                                                v675 = (const WCHAR *)((__int64 (__fastcall *)(size_t, __int128 *, _QWORD, __int64 *, _QWORD, _DWORD))off_180021018[0])(
                                                                        v671,
                                                                        &v1162,
                                                                        0,
                                                                        &v1093,
                                                                        0,
                                                                        0);
                                                lpModuleName = v675;
                                                if ( v675 )
                                                {
                                                  if ( ((unsigned int (__fastcall *)(const WCHAR *, __int64, int *))off_180021068[0])(
                                                         v675,
                                                         104,
                                                         &v1141) )
                                                  {
                                                    v1066 = v1143;
                                                  }
                                                  else
                                                  {
                                                    v1066 = 0;
                                                  }
                                                  HIDWORD(v1148) = v673 - (_DWORD)v1060;
                                                  v677 = pcchLength;
                                                  DWORD2(v1148) = (_DWORD)v1052;
                                                  ((void (__fastcall *)(size_t, LPCWSTR))off_180021078[0])(
                                                    pcchLength,
                                                    lpModuleName);
                                                  ((void (__fastcall *)(size_t, __int64))off_180021080[0])(v677, 1);
                                                  v678 = (const WCHAR *)((__int64 (__fastcall *)(size_t, LPVOID))off_180021078[0])(
                                                                          v677,
                                                                          lpMem);
                                                  v679 = off_1800210E8[0];
                                                  v1072 = v678;
                                                  v680 = ((__int64 (__fastcall *)(_QWORD))off_180021070[0])(0);
                                                  ((void (__fastcall *)(size_t, __int128 *, __int64))v679)(
                                                    pcchLength,
                                                    &v1148,
                                                    v680);
                                                  v681 = pcchLength;
                                                  ((void (__fastcall *)(size_t, SIZE_T, __int64, __int128 *, int, _QWORD))off_1800210D8[0])(
                                                    pcchLength,
                                                    v1074,
                                                    0xFFFFFFFFLL,
                                                    &v1148,
                                                    v1032,
                                                    0);
                                                  if ( v579 == 1 )
                                                  {
                                                    if ( (_DWORD)v1047 )
                                                      v682 = ((__int64 (__fastcall *)(__int64))off_180021118[0])(8);
                                                    else
                                                      v682 = 0xFFFFFF;
                                                  }
                                                  else
                                                  {
                                                    v682 = -5723992;
                                                  }
                                                  v683 = (int)v1060;
                                                  v684 = -(int)v1050;
                                                  LODWORD(v1052) = v682;
                                                  v685 = 0;
                                                  if ( (int)v1050 >= 0 )
                                                  {
                                                    v684 = 0;
                                                    v685 = (int)v1050;
                                                  }
                                                  if ( (int)v1060 >= 0 )
                                                  {
                                                    v686 = 0;
                                                  }
                                                  else
                                                  {
                                                    v686 = -(int)v1060;
                                                    v683 = 0;
                                                  }
                                                  v687 = DWORD2(v1148) - v684;
                                                  if ( DWORD2(v1148) - v684 >= (int)v1044 - v685 )
                                                    v687 = (_DWORD)v1044 - v685;
                                                  LODWORD(v1047) = v687;
                                                  v688 = HIDWORD(v1148) - v686;
                                                  if ( HIDWORD(v1148) - v686 >= (int)v1054 - v683 )
                                                    v688 = v1054 - v683;
                                                  LODWORD(v1060) = v688;
                                                  if ( v687 > 0 && v688 > 0 )
                                                  {
                                                    v689 = (int)v1044;
                                                    v690 = (unsigned __int8)v1052;
                                                    v691 = (int)v1047;
                                                    LODWORD(v1065) = 0;
                                                    v692 = (char *)(v1066 + 4 * (v684 + (__int64)(DWORD2(v1148) * v686)));
                                                    lpMem = v692;
                                                    v693 = (char *)(v1063 + 4 * (v685 + (__int64)((int)v1044 * v683)));
                                                    LODWORD(v1044) = (unsigned int)v1052 >> 8;
                                                    LODWORD(v1050) = (unsigned int)v1052 >> 16;
                                                    v1074 = 4LL * SDWORD2(v1148);
                                                    v1052 = (LPVOID)(4 * v689);
                                                    v1063 = (SIZE_T)v693;
                                                    do
                                                    {
                                                      v694 = (char)v1044;
                                                      v695 = 0;
                                                      v696 = (unsigned __int8 *)v692;
                                                      v1066 = (SIZE_T)v692;
                                                      v697 = (char)v1050;
                                                      v698 = v693;
                                                      LODWORD(v1054) = 0;
                                                      do
                                                      {
                                                        v699 = ~(unsigned __int8)((*v696
                                                                                 + v696[2]
                                                                                 + 2 * (unsigned int)v696[1]) >> 2);
                                                        if ( (unsigned __int8)((*v696
                                                                              + v696[2]
                                                                              + 2 * (unsigned int)v696[1]) >> 2) != 0xFF )
                                                        {
                                                          v700 = (unsigned __int8)v698[2];
                                                          v701 = v699;
                                                          v702 = (int)((unsigned __int64)(2155905153LL
                                                                                        * v699
                                                                                        * (v690 - v700)) >> 32) >> 7;
                                                          v698[2] = v700 + (v702 < 0) + v702;
                                                          v698[1] -= v701 * (v694 - v698[1]);
                                                          *v698 -= v701 * (v697 - *v698);
                                                          v703 = (unsigned __int8)v698[3];
                                                          v704 = v701 * (255 - v703);
                                                          v695 = v1054;
                                                          LOBYTE(v702) = v703 + v704 / 255;
                                                          v696 = (unsigned __int8 *)v1066;
                                                          v698[3] = v702;
                                                        }
                                                        v696 += 4;
                                                        ++v695;
                                                        v698 += 4;
                                                        v1066 = (SIZE_T)v696;
                                                        LODWORD(v1054) = v695;
                                                      }
                                                      while ( v695 < v691 );
                                                      v692 = (char *)lpMem + v1074;
                                                      v693 = (char *)v1052 + v1063;
                                                      lpMem = (char *)lpMem + v1074;
                                                      v1063 += (SIZE_T)v1052;
                                                      LODWORD(v1065) = v1065 + 1;
                                                    }
                                                    while ( (int)v1065 < (int)v1060 );
                                                    v94 = Src;
                                                    v681 = pcchLength;
                                                  }
                                                  ((void (__fastcall *)(LPCWSTR))off_180021038[0])(lpModuleName);
                                                  if ( v1072 )
                                                    ((void (__fastcall *)(size_t, LPCWSTR))off_180021078[0])(
                                                      v681,
                                                      v1072);
                                                }
                                                else
                                                {
                                                  v674 = GetLastError();
                                                  v676 = v674 < 0;
                                                  if ( v674 > 0 )
                                                  {
                                                    v674 = (unsigned __int16)v674 | 0x80070000;
                                                    v676 = v674 < 0;
                                                  }
                                                  if ( !v676 )
                                                    v674 = -2147467259;
                                                }
                                                ((void (__fastcall *)(size_t))off_180021030[0])(pcchLength);
                                                if ( v674 >= 0 )
                                                {
                                                  v705 = 0;
                                                  v1132 = 0;
                                                  memset_0(v1133, 0, 0x64u);
                                                  v1144 = 0;
                                                  memset_0(v1145, 0, 0x64u);
                                                  v660 = v1043;
                                                  v1074 = (SIZE_T)v1101;
                                                  memset(v1165, 0, 28);
                                                  v1164 = 0;
                                                  v1149 = 0;
                                                  if ( !v1101 )
                                                    goto LABEL_1010;
                                                  LODWORD(v1047) = v1099;
                                                  v1072 = v1104;
                                                  v706 = ((__int64 (__fastcall *)(SIZE_T, __int64))off_180021050[0])(
                                                           v1043,
                                                           7);
                                                  if ( !v706
                                                    || (!((unsigned int (__fastcall *)(__int64, __int64, int *))off_180021068[0])(
                                                           v706,
                                                           104,
                                                           &v1132)
                                                      ? (v1066 = 0, LODWORD(v1054) = 0, LODWORD(v1044) = 0)
                                                      : (v1066 = v1134,
                                                         LODWORD(v1044) = v1133[0],
                                                         v705 = 0,
                                                         LODWORD(v1054) = v1133[1]),
                                                        (pcchLength = ((__int64 (__fastcall *)(SIZE_T))off_180021010[0])(v660)) == 0) )
                                                  {
                                                    GetLastError();
                                                    goto LABEL_1010;
                                                  }
                                                  v707 = v1056;
                                                  LODWORD(v1058) = (_DWORD)v1058 - (_DWORD)v1046;
                                                  DWORD1(v1164) = (_DWORD)v1058;
                                                  DWORD2(v1164) = v1056 - (_DWORD)v1067;
                                                  v1092 = 0;
                                                  memset(v1165, 0, 28);
                                                  LODWORD(v1164) = 40;
                                                  HIDWORD(v1164) = 2097153;
                                                  v708 = (void *)((__int64 (__fastcall *)(size_t, __int128 *, _QWORD, __int64 *, _QWORD, _DWORD))off_180021018[0])(
                                                                   pcchLength,
                                                                   &v1164,
                                                                   0,
                                                                   &v1092,
                                                                   0,
                                                                   0);
                                                  lpMem = v708;
                                                  if ( v708 )
                                                  {
                                                    if ( ((unsigned int (__fastcall *)(void *, __int64, int *))off_180021068[0])(
                                                           v708,
                                                           104,
                                                           &v1144) )
                                                    {
                                                      lpModuleName = v1146;
                                                    }
                                                    else
                                                    {
                                                      lpModuleName = 0;
                                                    }
                                                    v711 = (_DWORD)v1067 - v707;
                                                    v712 = pcchLength;
                                                    *((_QWORD *)&v1149 + 1) = __PAIR64__(v711, (unsigned int)v1058);
                                                    ((void (__fastcall *)(size_t, LPVOID))off_180021078[0])(
                                                      pcchLength,
                                                      lpMem);
                                                    ((void (__fastcall *)(size_t, __int64))off_180021080[0])(v712, 1);
                                                    v713 = (void *)((__int64 (__fastcall *)(size_t, LPCWSTR))off_180021078[0])(
                                                                     v712,
                                                                     v1072);
                                                    v714 = off_1800210E8[0];
                                                    v1052 = v713;
                                                    v715 = ((__int64 (__fastcall *)(_QWORD))off_180021070[0])(0);
                                                    ((void (__fastcall *)(size_t, __int128 *, __int64))v714)(
                                                      pcchLength,
                                                      &v1149,
                                                      v715);
                                                    v710 = pcchLength;
                                                    ((void (__fastcall *)(size_t, SIZE_T, __int64, __int128 *, int, _QWORD))off_1800210D8[0])(
                                                      pcchLength,
                                                      v1074,
                                                      0xFFFFFFFFLL,
                                                      &v1149,
                                                      v1032,
                                                      0);
                                                    if ( v579 == 1 )
                                                    {
                                                      if ( (_DWORD)v1047 )
                                                        LODWORD(v1062) = ((__int64 (__fastcall *)(__int64))off_180021118[0])(8);
                                                    }
                                                    else
                                                    {
                                                      LODWORD(v1062) = -5723992;
                                                    }
                                                    v716 = -(int)v1046;
                                                    if ( (int)v1046 >= 0 )
                                                      v716 = 0;
                                                    v717 = v1056;
                                                    v718 = 0;
                                                    if ( (int)v1046 >= 0 )
                                                      v718 = (int)v1046;
                                                    if ( (v1056 & 0x80000000) == 0LL )
                                                    {
                                                      v719 = 0;
                                                    }
                                                    else
                                                    {
                                                      v719 = -(int)v1056;
                                                      v717 = 0;
                                                    }
                                                    v720 = DWORD2(v1149) - v716;
                                                    if ( DWORD2(v1149) - v716 >= (int)v1044 - v718 )
                                                      v720 = (_DWORD)v1044 - v718;
                                                    LODWORD(v1047) = v720;
                                                    v721 = HIDWORD(v1149) - v719;
                                                    if ( HIDWORD(v1149) - v719 >= (int)v1054 - v717 )
                                                      v721 = v1054 - v717;
                                                    LODWORD(v1050) = v721;
                                                    if ( v720 > 0 && v721 > 0 )
                                                    {
                                                      v722 = (int)v1047;
                                                      LODWORD(v1065) = 0;
                                                      v723 = &lpModuleName[2 * v716
                                                                         + 2 * (__int64)(DWORD2(v1149) * v719)];
                                                      v1063 = (SIZE_T)v723;
                                                      v724 = (_BYTE *)(v1066 + 4 * (v718 + (__int64)((int)v1044 * v717)));
                                                      LODWORD(v1056) = (unsigned int)v1062 >> 8;
                                                      LODWORD(v1067) = WORD1(v1062);
                                                      v1072 = (LPCWSTR)(4LL * SDWORD2(v1149));
                                                      v1074 = 4LL * (int)v1044;
                                                      v1066 = (SIZE_T)v724;
                                                      do
                                                      {
                                                        v725 = v1056;
                                                        v726 = v723;
                                                        v727 = (char)v1067;
                                                        v728 = v724;
                                                        v729 = v1062;
                                                        lpModuleName = v723;
                                                        v730 = 0;
                                                        LODWORD(v1054) = 0;
                                                        do
                                                        {
                                                          v731 = ~(unsigned __int8)((*(unsigned __int8 *)v726
                                                                                   + *((unsigned __int8 *)v726 + 2)
                                                                                   + 2
                                                                                   * (unsigned int)*((unsigned __int8 *)v726 + 1)) >> 2);
                                                          if ( (unsigned __int8)((*(unsigned __int8 *)v726
                                                                                + *((unsigned __int8 *)v726 + 2)
                                                                                + 2
                                                                                * (unsigned int)*((unsigned __int8 *)v726
                                                                                                + 1)) >> 2) != 0xFF )
                                                          {
                                                            v732 = (unsigned __int8)v728[2];
                                                            v733 = v731;
                                                            v734 = (int)((unsigned __int64)(2155905153LL
                                                                                          * v731
                                                                                          * (v729 - v732)) >> 32) >> 7;
                                                            v728[2] = v732 + (v734 < 0) + v734;
                                                            v728[1] -= v733 * (v725 - v728[1]);
                                                            *v728 -= v733 * (v727 - *v728);
                                                            v735 = (unsigned __int8)v728[3];
                                                            v736 = v733 * (255 - v735);
                                                            v730 = v1054;
                                                            LOBYTE(v734) = v735 + v736 / 255;
                                                            v726 = lpModuleName;
                                                            v728[3] = v734;
                                                          }
                                                          v726 += 2;
                                                          ++v730;
                                                          v728 += 4;
                                                          lpModuleName = v726;
                                                          LODWORD(v1054) = v730;
                                                        }
                                                        while ( v730 < v722 );
                                                        v723 = (LPCWSTR)((char *)v1072 + v1063);
                                                        v724 = (_BYTE *)(v1074 + v1066);
                                                        v1063 += (SIZE_T)v1072;
                                                        v1066 += v1074;
                                                        LODWORD(v1065) = v1065 + 1;
                                                      }
                                                      while ( (int)v1065 < (int)v1050 );
                                                      v94 = Src;
                                                      v710 = pcchLength;
                                                    }
                                                    ((void (__fastcall *)(LPVOID))off_180021038[0])(lpMem);
                                                    if ( v1052 )
                                                      ((void (__fastcall *)(size_t, LPVOID))off_180021078[0])(
                                                        v710,
                                                        v1052);
                                                  }
                                                  else
                                                  {
                                                    v705 = GetLastError();
                                                    v709 = v705 < 0;
                                                    if ( v705 > 0 )
                                                    {
                                                      v705 = (unsigned __int16)v705 | 0x80070000;
                                                      v709 = v705 < 0;
                                                    }
                                                    v710 = pcchLength;
                                                    if ( !v709 )
                                                      v705 = -2147467259;
                                                  }
                                                  ((void (__fastcall *)(size_t))off_180021030[0])(v710);
                                                  if ( v705 >= 0 )
                                                  {
                                                    v660 = v1043;
                                                    v737 = v579 == 1;
                                                    v661 = v1059;
                                                    if ( v737 )
                                                      ((void (__fastcall *)(LPVOID, _QWORD, _QWORD, _QWORD, _DWORD, SIZE_T, _DWORD, _DWORD, int))off_180021000[0])(
                                                        v1059,
                                                        (unsigned int)v1107,
                                                        (unsigned int)v1108,
                                                        (unsigned int)Size,
                                                        v1051,
                                                        v1043,
                                                        0,
                                                        0,
                                                        13369376);
                                                    else
                                                      ((void (__fastcall *)(LPVOID, _QWORD, _QWORD, _QWORD, _DWORD, SIZE_T, _DWORD, _DWORD, _DWORD, _DWORD, _DWORD))off_180021040[0])(
                                                        v1059,
                                                        (unsigned int)v1073,
                                                        DWORD1(v1073),
                                                        (unsigned int)Size,
                                                        v1051,
                                                        v1043,
                                                        0,
                                                        0,
                                                        Size,
                                                        v1051,
                                                        (_DWORD)v1057);
                                                    v659 = v1045;
                                                    goto LABEL_1099;
                                                  }
                                                }
                                              }
                                              else
                                              {
                                                GetLastError();
                                              }
                                            }
                                            v660 = v1043;
LABEL_1010:
                                            v659 = v1045;
                                            goto LABEL_1011;
                                          }
                                        }
                                        else
                                        {
                                          LODWORD(Size) = 0;
                                          v579 = v338 & 0xF;
                                          v578 = v579;
                                        }
                                        if ( v578 != 1 )
                                          goto LABEL_868;
                                        goto LABEL_866;
                                      }
                                      v452 = 0;
                                      v1063 = 0;
                                      v1066 = 0;
                                      LODWORD(v1056) = 0;
                                      v1080 = 0;
                                      v1061 = 0;
                                      memset(v1096, 0, sizeof(v1096));
                                      lpMem = 0;
                                      v1070 = 0;
                                      pcchLength = 0;
                                      v1077 = 0;
                                      if ( !((unsigned int (__fastcall *)(__int64, unsigned int *, _QWORD, unsigned int *))off_1800210A0[0])(
                                              8,
                                              &v1070,
                                              0,
                                              &v1077) )
                                      {
                                        v452 = GetLastError();
                                        v453 = v452 < 0;
                                        if ( v452 > 0 )
                                        {
                                          v452 = (unsigned __int16)v452 | 0x80070000;
                                          v453 = v452 < 0;
                                        }
                                        if ( !v453 )
                                          v452 = -2147467259;
LABEL_671:
                                        SP_MEM<unsigned short *>::~SP_MEM<unsigned short *>(&pcchLength);
                                        SP_MEM<unsigned short *>::~SP_MEM<unsigned short *>(&lpMem);
                                        if ( v452 < 0 )
                                        {
                                          pcchLength = 0;
                                          lpMem = 0;
                                          v1063 = 0;
                                        }
                                        else
                                        {
                                          v462 = 0;
                                          LODWORD(v1067) = 0;
                                          v463 = 0;
                                          if ( (_DWORD)v1056 )
                                          {
                                            while ( 2 )
                                            {
                                              for ( i1 = 0; i1 < 0x26; ++i1 )
                                              {
                                                if ( *(_DWORD *)(v100 + 4LL * v463) == dword_18001E810[i1] )
                                                {
                                                  v462 = i1;
                                                  LODWORD(v1067) = i1;
                                                  goto LABEL_679;
                                                }
                                              }
                                              if ( ++v463 < (unsigned int)v1056 )
                                                continue;
                                              break;
                                            }
                                          }
LABEL_679:
                                          v465 = v462;
                                          LODWORD(v1044) = 0;
                                          v466 = (unsigned int)dword_18001E810[v462];
                                          memset(v1169, 0, sizeof(v1169));
                                          if ( ((unsigned int (__fastcall *)(__int64, _BYTE *, __int64))off_1800210A8[0])(
                                                 v466,
                                                 v1189,
                                                 85)
                                            && ((int (__fastcall *)(_BYTE *, __int64, _OWORD *, __int64))off_180021090[0])(
                                                 v1189,
                                                 88,
                                                 v1169,
                                                 16) > 0 )
                                          {
                                            LODWORD(v1044) = (HIDWORD(v1169[0]) >> 27) & 1;
                                          }
                                          memset_0(v1097, 0, 0x98u);
                                          v467 = L"Segoe UI Light";
                                          for ( i2 = 0; i2 != 19; ++i2 )
                                          {
                                            v1097[i2] = v467;
                                            v469 = -1;
                                            do
                                              ++v469;
                                            while ( v467[v469] );
                                            v467 += v469 + 1;
                                          }
                                          pcchLength = v1097[byte_18001E8B0[3 * v465]];
                                          lpMem = (LPVOID)v1097[byte_18001E8B0[3 * v465 + 1]];
                                          v1063 = v1097[byte_18001E8B0[3 * v465 + 2]];
                                          v470 = MemoryAlloc(0x1C90u);
                                          v471 = v470;
                                          if ( v470 )
                                          {
                                            v473 = (unsigned __int8 *)&unk_18001CB70;
                                            v474 = v470;
                                            v475 = 0;
                                            v476 = -1;
                                            v477 = 0;
                                            v478 = 0;
                                            v479 = 914;
                                            do
                                            {
                                              v480 = *v473 << 8;
                                              v481 = v473[1];
                                              v482 = v473[4];
                                              v473 += 8;
                                              v483 = *(v473 - 5) | ((*(v473 - 6) | ((v480 | v481) << 8)) << 8);
                                              v484 = v478 ^ v483;
                                              v485 = *(v473 - 1)
                                                   | ((*(v473 - 2) | ((*(v473 - 3) | (v482 << 8)) << 8)) << 8);
                                              v486 = v478 ^ v483 ^ v477 ^ v485 ^ 0xAC987321;
                                              v487 = v484
                                                   ^ (__ROR4__(v486, 22) + 4991 * __ROR4__(v486 + 1419157410, 27));
                                              v488 = v486 ^ (43881 * __ROR4__(v487 + 133239679, 9) - __ROR4__(v487, 30));
                                              v489 = v487 ^ (24670 * v488 - (v488 >> 13) - 123127970);
                                              v490 = v488 ^ (2033 * __ROR4__(v489 ^ 0xAB69, 26) - __ROR4__(v489, 30));
                                              v491 = v489 ^ (133239679 - (v490 ^ 0xAB69605E));
                                              v492 = v490 ^ (43881 * (v491 ^ 0x137F)) ^ __ROR4__(v491, 6);
                                              v493 = v491
                                                   ^ (__ROR4__(v492, 30) + 24670 * __ROR4__(v492 + 133239679, 15));
                                              v494 = v492
                                                   ^ (2033 * __ROR4__(v493 + 1419157410, 14) - __ROR4__(v493, 24));
                                              v495 = v493
                                                   ^ __ROR4__(v494, 10)
                                                   ^ (4991 * __ROR4__(v494 ^ 0xAB69605E, 12));
                                              v496 = v494 ^ (v495 >> 10) ^ (43881 * (v495 ^ 0x7F1));
                                              v497 = v495 ^ (2033 * (__ROR4__(~v496, 5) + 24670));
                                              v498 = v497
                                                   ^ (((v496 ^ (v497 - 2033) ^ 0xAB69605E) >> 2)
                                                    + 4991 * __ROR4__(v496 ^ (v497 - 2033) ^ 0xAB6967AF, 30));
                                              v499 = v496
                                                   ^ (v497 - 2033)
                                                   ^ 0xAB69605E
                                                   ^ (__ROR4__(v498, 25) + 43881 * __ROR4__(v498 - 133239679, 6));
                                              v500 = v498 ^ (24670 * (v499 ^ 0x137F) + __ROR4__(v499, 9));
                                              v501 = v499 ^ (__ROR4__(v500, 25) + 2033 * __ROR4__(v500 ^ 0xAB69, 27));
                                              v502 = v500 ^ v501 ^ 0xAC987321;
                                              v503 = v501 ^ (4991 * __ROR4__(v502, 3) - 219010071);
                                              v504 = v502 ^ (24670 * __ROR4__(v503 - 133239679, 1) - __ROR4__(v503, 6));
                                              v505 = v503
                                                   ^ (__ROR4__(v504, 18) + 2033 * __ROR4__(v504 - 1419157410, 29));
                                              v506 = v504
                                                   ^ (4991 * __ROR4__(v505 - 1419157410, 17) - __ROR4__(v505, 14));
                                              v507 = v505 ^ (v506 >> 3) ^ (43881 * (v506 ^ 0x605E));
                                              v508 = v475
                                                   ^ __ROR4__(v507, 30)
                                                   ^ (24670 * __ROR4__(v507 ^ 0x7F1137F, 28));
                                              v475 = v483;
                                              v478 = v506 ^ v508;
                                              v474[3] = v478;
                                              v477 = v507 ^ v476;
                                              v474[7] = v507 ^ v476;
                                              v476 = v485;
                                              v474[2] = __ROR4__(v478, 8);
                                              v474[6] = __ROR4__(v477, 8);
                                              v474[1] = __ROR4__(v478, 16);
                                              v474[5] = __ROR4__(v477, 16);
                                              *v474 = __ROR4__(v478, 24);
                                              v474[4] = __ROR4__(v477, 24);
                                              v474 += 8;
                                              --v479;
                                            }
                                            while ( v479 );
                                            LOBYTE(v338) = (_BYTE)v1046;
                                            v94 = Src;
                                            v509 = 0;
                                            v510 = 0;
                                            do
                                            {
                                              v511 = (__m128)_mm_loadu_si128((const __m128i *)&v471[v509]);
                                              v509 += 16LL;
                                              v512 = _mm_xor_ps(v511, v510);
                                              v510 = v512;
                                            }
                                            while ( v509 < 0x1C90 );
                                            v513 = _mm_xor_ps(v512, (__m128)_mm_srli_si128((__m128i)v512, 8));
                                            v514 = _mm_xor_ps(v513, (__m128)_mm_srli_si128((__m128i)v513, 4));
                                            v515 = _mm_xor_ps(v514, (__m128)_mm_srli_si128((__m128i)v514, 2));
                                            if ( (unsigned __int8)_mm_cvtsi128_si32((__m128i)_mm_xor_ps(
                                                                                               v515,
                                                                                               (__m128)_mm_srli_si128((__m128i)v515, 1))) == 127 )
                                            {
                                              v516 = (int)v1067;
                                              v452 = 0;
                                              v1080 = v471;
                                              v517 = 0;
                                              v1078 = 7312;
                                              do
                                              {
                                                for ( i3 = 0; i3 < 0x26; ++i3 )
                                                {
                                                  if ( v516 == i3 )
                                                    *((_QWORD *)v1096 + v517) = v471;
                                                  v519 = -1;
                                                  do
                                                    ++v519;
                                                  while ( v471[v519] );
                                                  v471 += v519 + 1;
                                                }
                                                ++v517;
                                              }
                                              while ( v517 < 6 );
                                              v520 = MemoryAlloc(0x18u);
                                              SP_MEM<unsigned long>::operator=(&v1061, v520);
                                              v521 = (void **)v1061;
                                              if ( v1061 )
                                              {
                                                v522 = 0;
                                                *(_OWORD *)v1061 = 0;
                                                v521[2] = 0;
                                                LODWORD(v1056) = 0;
                                                while ( 2 )
                                                {
                                                  v523 = 0;
                                                  lpModuleName = (LPCWSTR)v522;
                                                  while ( 1 )
                                                  {
                                                    v524 = v523;
                                                    if ( *((_WORD *)&v1042 + v522) == word_18001E928[v523] )
                                                      break;
                                                    if ( ++v523 >= 6 )
                                                      goto LABEL_717;
                                                  }
                                                  v525 = *((_QWORD *)v1096 + v523);
                                                  v526 = -1;
                                                  v1065 = *((_QWORD *)v1096 + v524);
                                                  do
                                                    ++v526;
                                                  while ( *(_BYTE *)(v525 + v526) );
                                                  v527 = ((__int64 (__fastcall *)(__int64, _QWORD, __int64, _QWORD, _QWORD, _DWORD))off_1800210C0[0])(
                                                           65001,
                                                           0,
                                                           v525,
                                                           (unsigned int)(v526 + 1),
                                                           0,
                                                           0);
                                                  LODWORD(v1054) = v527;
                                                  if ( !v527 )
                                                    goto LABEL_719;
                                                  v528 = MemoryAlloc(2LL * v527);
                                                  v521[(_QWORD)lpModuleName] = v528;
                                                  if ( !v528 )
                                                    goto LABEL_724;
                                                  v529 = -1;
                                                  do
                                                    ++v529;
                                                  while ( *(_BYTE *)(v1065 + v529) );
                                                  if ( !((unsigned int (__fastcall *)(__int64, _QWORD, SIZE_T, _QWORD, void *, _DWORD))off_1800210C0[0])(
                                                          65001,
                                                          0,
                                                          v1065,
                                                          (unsigned int)(v529 + 1),
                                                          v528,
                                                          v1054) )
                                                  {
LABEL_719:
                                                    v530 = GetLastError();
                                                    v452 = v530;
                                                    if ( v530 > 0 )
                                                      v452 = (unsigned __int16)v530 | 0x80070000;
                                                    if ( v452 >= 0 )
                                                      v452 = -2147467259;
                                                    goto LABEL_725;
                                                  }
                                                  v522 = v1056;
LABEL_717:
                                                  LODWORD(v1056) = ++v522;
                                                  if ( v522 < 3 )
                                                    continue;
                                                  break;
                                                }
                                                v472 = v1078;
                                                v1098 = (int)v1044;
                                                v1061 = 0;
                                                v1047 = v521;
LABEL_736:
                                                v535 = v1080;
                                                if ( v1080 && v472 )
                                                {
                                                  do
                                                  {
                                                    *v535++ = 0;
                                                    --v472;
                                                  }
                                                  while ( v472 );
                                                }
                                                SP_MEM<unsigned short *>::~SP_MEM<unsigned short *>(&v1061);
                                                SP_MEM<unsigned short *>::~SP_MEM<unsigned short *>(&v1080);
                                                SP_MEM<unsigned short *>::~SP_MEM<unsigned short *>(&v1066);
                                                if ( v452 < 0 )
                                                  goto LABEL_845;
                                                v1100 = *v521;
                                                v1101 = v521[1];
                                                v1102 = v521[2];
                                                v1095 = 0;
                                                LODWORD(v1095) = 16;
                                                v100 = 0;
                                                if ( !((unsigned int (__fastcall *)(__int64, _QWORD, __int128 *, _QWORD))off_180021168[0])(
                                                        66,
                                                        0,
                                                        &v1095,
                                                        0) )
                                                {
                                                  v536 = GetLastError();
                                                  v452 = v536;
                                                  if ( v536 > 0 )
                                                    v452 = (unsigned __int16)v536 | 0x80070000;
                                                  v1099 = 0;
                                                  if ( v452 >= 0 )
                                                    v452 = -2147467259;
                                                  goto LABEL_846;
                                                }
                                                v537 = v338 & 0xF;
                                                v1099 = BYTE4(v1095) & 1;
                                                v538 = 42;
                                                LODWORD(v1052) = 42;
                                                if ( v537 != 1 )
                                                {
                                                  if ( (v338 & 0xF) == 2 )
                                                  {
                                                    v1030 = 15;
                                                    LODWORD(v1060) = 11;
                                                  }
                                                  else
                                                  {
                                                    if ( (v338 & 0xF) != 3 )
                                                    {
                                                      v538 = 0;
                                                      LODWORD(v1060) = 0;
LABEL_754:
                                                      v1030 = v538;
                                                      goto LABEL_755;
                                                    }
                                                    v1030 = 225;
                                                    LODWORD(v1060) = 225;
                                                  }
LABEL_755:
                                                  memset_0(v1179, 0, 0xDCu);
                                                  v1180 = 220;
                                                  if ( ((unsigned int (__fastcall *)(_QWORD, __int64, _BYTE *))off_1800210E0[0])(
                                                         0,
                                                         0xFFFFFFFFLL,
                                                         v1179) )
                                                  {
                                                    v539 = v1181;
                                                    LODWORD(v1056) = v1183;
                                                    LODWORD(v1051) = v1182;
                                                    if ( v1181 < 0x60u )
                                                      v539 = 96;
                                                    LODWORD(v1058) = v539;
                                                    v540 = v539;
                                                  }
                                                  else
                                                  {
                                                    v540 = 96;
                                                    LODWORD(v1051) = 0;
                                                    LODWORD(v1058) = 96;
                                                    LODWORD(v1056) = 0;
                                                  }
                                                  v541 = (const WCHAR *)v1063;
                                                  if ( v537 == 1 )
                                                    v541 = (const WCHAR *)pcchLength;
                                                  lpModuleName = v541;
                                                  memset_0(v1170, 0, 0x5Cu);
                                                  v1066 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))off_1800210F8[0])(
                                                            0,
                                                            0,
                                                            1027);
                                                  if ( !v1066 )
                                                    goto LABEL_812;
                                                  v542 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))off_1800210B8[0])(
                                                           v1030,
                                                           v540,
                                                           72);
                                                  v1170[4] = 400;
                                                  v1170[0] = -v542;
                                                  v1171 = 5;
                                                  StringCchCopyW(v1172, v543, lpModuleName);
                                                  v544 = ((__int64 (__fastcall *)(_DWORD *))off_180021020[0])(v1170);
                                                  if ( v544 )
                                                  {
                                                    v452 = 0;
                                                    v1103 = (WCHAR *)v544;
                                                  }
                                                  else
                                                  {
                                                    v452 = GetLastError();
                                                    v545 = v452 < 0;
                                                    if ( v452 > 0 )
                                                    {
                                                      v452 = (unsigned __int16)v452 | 0x80070000;
                                                      v545 = v452 < 0;
                                                    }
                                                    if ( !v545 )
                                                      v452 = -2147467259;
                                                  }
                                                  ((void (__fastcall *)(_QWORD, SIZE_T))off_180021160[0])(0, v1066);
                                                  if ( v452 < 0 )
                                                    goto LABEL_845;
                                                  v546 = (const unsigned __int16 *)v1063;
                                                  if ( v537 == 1 )
                                                    v546 = (const unsigned __int16 *)pcchLength;
                                                  memset_0(v1173, 0, 0x5Cu);
                                                  lpModuleName = (LPCWSTR)((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))off_1800210F8[0])(
                                                                            0,
                                                                            0,
                                                                            1027);
                                                  if ( !lpModuleName )
                                                    goto LABEL_812;
                                                  v547 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))off_1800210B8[0])(
                                                           (unsigned int)v1060,
                                                           (unsigned int)v1058,
                                                           72);
                                                  v1173[4] = 400;
                                                  v1173[0] = -v547;
                                                  v1174 = 5;
                                                  StringCchCopyW(v1175, v548, v546);
                                                  v549 = ((__int64 (__fastcall *)(_DWORD *))off_180021020[0])(v1173);
                                                  if ( v549 )
                                                  {
                                                    v452 = 0;
                                                    v1104 = (const WCHAR *)v549;
                                                  }
                                                  else
                                                  {
                                                    v452 = GetLastError();
                                                    v550 = v452 < 0;
                                                    if ( v452 > 0 )
                                                    {
                                                      v452 = (unsigned __int16)v452 | 0x80070000;
                                                      v550 = v452 < 0;
                                                    }
                                                    if ( !v550 )
                                                      v452 = -2147467259;
                                                  }
                                                  ((void (__fastcall *)(_QWORD, LPCWSTR))off_180021160[0])(
                                                    0,
                                                    lpModuleName);
                                                  if ( v452 < 0 )
                                                    goto LABEL_845;
                                                  if ( v537 != 1 )
                                                  {
                                                    if ( v537 == 2 )
                                                    {
                                                      v551 = (int)v1051 / 4;
                                                      goto LABEL_787;
                                                    }
                                                    if ( v537 != 3 )
                                                    {
                                                      v551 = 0;
LABEL_787:
                                                      v552 = 0;
                                                      goto LABEL_789;
                                                    }
                                                  }
                                                  v551 = v1051;
                                                  v552 = v1056;
LABEL_789:
                                                  *((_QWORD *)&v1073 + 1) = __PAIR64__(v552, v551);
                                                  if ( v537 == 1 )
                                                  {
                                                    v553 = 150;
                                                    LODWORD(v1060) = 32;
                                                  }
                                                  else
                                                  {
                                                    v553 = 0;
                                                    if ( (unsigned int)(v537 - 2) < 2 )
                                                    {
                                                      LODWORD(v1052) = 0;
                                                      LODWORD(v1060) = 0;
                                                    }
                                                    else
                                                    {
                                                      LODWORD(v1060) = 0;
                                                      LODWORD(v1052) = 0;
                                                    }
                                                  }
                                                  v1031 = v553;
                                                  v554 = v1100;
                                                  LODWORD(v1051) = v551 - v553;
                                                  v1113 = v551 - v553;
                                                  v1109 = v551 - v553;
                                                  lpModuleName = (LPCWSTR)((__int64 (__fastcall *)(SIZE_T, WCHAR *, _QWORD))off_180021078[0])(
                                                                            v1045,
                                                                            v1103,
                                                                            0);
                                                  LODWORD(v1054) = ((__int64 (__fastcall *)(SIZE_T, void *, __int64, int *, int, _QWORD))off_1800210D8[0])(
                                                                     v1045,
                                                                     v554,
                                                                     0xFFFFFFFFLL,
                                                                     &v1107,
                                                                     3152,
                                                                     0);
                                                  v452 = (_DWORD)v1054 != 0 ? 0 : 0x80004005;
                                                  if ( lpModuleName )
                                                    ((void (__fastcall *)(SIZE_T, LPCWSTR))off_180021078[0])(
                                                      v1045,
                                                      lpModuleName);
                                                  if ( (_DWORD)v1054 )
                                                  {
                                                    v555 = v1101;
                                                    lpModuleName = (LPCWSTR)((__int64 (__fastcall *)(SIZE_T, const WCHAR *))off_180021078[0])(
                                                                              v1045,
                                                                              v1104);
                                                    LODWORD(v1054) = ((__int64 (__fastcall *)(SIZE_T, void *, __int64, int *, int, _QWORD))off_1800210D8[0])(
                                                                       v1045,
                                                                       v555,
                                                                       0xFFFFFFFFLL,
                                                                       &v1111,
                                                                       3152,
                                                                       0);
                                                    v452 = (_DWORD)v1054 != 0 ? 0 : 0x80004005;
                                                    if ( lpModuleName )
                                                      ((void (__fastcall *)(SIZE_T, LPCWSTR))off_180021078[0])(
                                                        v1045,
                                                        lpModuleName);
                                                    if ( (_DWORD)v1054 )
                                                    {
                                                      if ( v537 == 2 || v537 == 3 )
                                                      {
                                                        v556 = v1113;
                                                        if ( v1109 > v1113 )
                                                          v556 = v1109;
                                                        LODWORD(v1051) = v556;
                                                      }
                                                      else
                                                      {
                                                        v556 = v1051;
                                                      }
                                                      if ( v1098 )
                                                      {
                                                        ((void (__fastcall *)(int *, _QWORD, _QWORD))off_180021150)(
                                                          &v1107,
                                                          v556 - v1109,
                                                          (unsigned int)v1052);
                                                        v557 = v556 - v1113;
                                                      }
                                                      else
                                                      {
                                                        ((void (__fastcall *)(int *, _QWORD, _QWORD))off_180021150)(
                                                          &v1107,
                                                          v1031,
                                                          (unsigned int)v1052);
                                                        v557 = v1031;
                                                      }
                                                      ((void (__fastcall *)(int *, __int64, _QWORD))off_180021150)(
                                                        &v1111,
                                                        v557,
                                                        (unsigned int)(v1110 + (_DWORD)v1060));
                                                      if ( (unsigned int)(v537 - 2) <= 1 )
                                                      {
                                                        *((_QWORD *)&v1073 + 1) = __PAIR64__(v1114, v556);
                                                        v1106 = -5723992;
                                                        goto LABEL_832;
                                                      }
                                                      if ( v537 != 1 )
                                                        goto LABEL_832;
                                                      v1106 = 0xFFFFFF;
                                                      memset_0(v1176, 0, 0x5Cu);
                                                      v452 = 0;
                                                      lpModuleName = (LPCWSTR)((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))off_1800210F8[0])(
                                                                                0,
                                                                                0,
                                                                                1027);
                                                      if ( !lpModuleName )
                                                      {
LABEL_812:
                                                        v558 = GetLastError();
                                                        v100 = 0;
                                                        v452 = v558;
                                                        if ( v558 > 0 )
                                                          v452 = (unsigned __int16)v558 | 0x80070000;
                                                        if ( v452 >= 0 )
                                                          v452 = -2147467259;
                                                        goto LABEL_846;
                                                      }
                                                      v559 = ((__int64 (__fastcall *)(__int64, _QWORD))off_1800210B8[0])(
                                                               11,
                                                               (unsigned int)v1058);
                                                      v1176[4] = 400;
                                                      v1176[0] = -v559;
                                                      v1177 = 5;
                                                      StringCchCopyW(v1178, v560, (const unsigned __int16 *)lpMem);
                                                      v561 = ((__int64 (__fastcall *)(_DWORD *))off_180021020[0])(v1176);
                                                      if ( v561 )
                                                      {
                                                        v1105 = v561;
                                                      }
                                                      else
                                                      {
                                                        v452 = GetLastError();
                                                        v562 = v452 < 0;
                                                        if ( v452 > 0 )
                                                        {
                                                          v452 = (unsigned __int16)v452 | 0x80070000;
                                                          v562 = v452 < 0;
                                                        }
                                                        if ( !v562 )
                                                          v452 = -2147467259;
                                                      }
                                                      ((void (__fastcall *)(_QWORD, LPCWSTR))off_180021160[0])(
                                                        0,
                                                        lpModuleName);
                                                      if ( v452 >= 0 )
                                                      {
                                                        v563 = v1102;
                                                        v1117 = v1051;
                                                        lpModuleName = (LPCWSTR)((__int64 (__fastcall *)(SIZE_T, __int64))off_180021078[0])(
                                                                                  v1045,
                                                                                  v1105);
                                                        LODWORD(v1054) = ((__int64 (__fastcall *)(SIZE_T, void *, __int64, unsigned int *, int, _QWORD))off_1800210D8[0])(
                                                                           v1045,
                                                                           v563,
                                                                           0xFFFFFFFFLL,
                                                                           &v1115,
                                                                           1120,
                                                                           0);
                                                        v452 = (_DWORD)v1054 != 0 ? 0 : 0x80004005;
                                                        if ( lpModuleName )
                                                          ((void (__fastcall *)(SIZE_T, LPCWSTR))off_180021078[0])(
                                                            v1045,
                                                            lpModuleName);
                                                        if ( (_DWORD)v1054 )
                                                        {
                                                          v564 = (unsigned int)v1058;
                                                          v565 = v1117 + 24;
                                                          v1118 = 32;
                                                          if ( (int)(v1117 + 24) < 90 )
                                                            v565 = 90;
                                                          v1117 = v565;
                                                          v1115 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))off_1800210B8[0])(
                                                                    v1115,
                                                                    (unsigned int)v1058,
                                                                    96);
                                                          v1116 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))off_1800210B8[0])(
                                                                    v1116,
                                                                    v564,
                                                                    96);
                                                          v1117 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))off_1800210B8[0])(
                                                                    v1117,
                                                                    v564,
                                                                    96);
                                                          v1118 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))off_1800210B8[0])(
                                                                    v1118,
                                                                    v564,
                                                                    96);
                                                          off_180021150();
LABEL_832:
                                                          v566 = DWORD2(v1073);
                                                          LODWORD(v1056) = HIDWORD(v1073);
                                                          v567 = v537 - 1;
                                                          if ( v567 )
                                                          {
                                                            v568 = v567 - 1;
                                                            if ( v568 )
                                                            {
                                                              if ( v568 == 1 )
                                                              {
                                                                v1168 = 0;
                                                                v1166 = 0;
                                                                v1167 = 0;
                                                                v569 = ((__int64 (__fastcall *)(_QWORD, __int64))off_180021148[0])(
                                                                         0,
                                                                         1);
                                                                LODWORD(v1166) = 40;
                                                                v100 = 0;
                                                                if ( ((unsigned int (__fastcall *)(__int64, __int128 *))off_180021108[0])(
                                                                       v569,
                                                                       &v1166) )
                                                                {
                                                                  ((void (__fastcall *)(_QWORD, char *))off_180021140[0])(
                                                                    0,
                                                                    (char *)&v1167 + 4);
                                                                  ((void (__fastcall *)(_QWORD, char *))off_180021140[0])(
                                                                    0,
                                                                    (char *)&v1167 + 12);
                                                                  LODWORD(v1073) = 50 * (HIDWORD(v1167) - v566) / 100;
                                                                  DWORD1(v1073) = 50 * ((int)v1168 - (int)v1056) / 100;
                                                                }
                                                                goto LABEL_843;
                                                              }
                                                            }
                                                            else
                                                            {
                                                              v570 = v1098;
                                                              v1157 = 0;
                                                              v1155 = 0;
                                                              v1156 = 0;
                                                              v571 = ((__int64 (__fastcall *)(_QWORD, __int64))off_180021148[0])(
                                                                       0,
                                                                       1);
                                                              LODWORD(v1155) = 40;
                                                              if ( ((unsigned int (__fastcall *)(__int64, __int128 *))off_180021108[0])(
                                                                     v571,
                                                                     &v1155) )
                                                              {
                                                                ((void (__fastcall *)(_QWORD, char *))off_180021140[0])(
                                                                  0,
                                                                  (char *)&v1156 + 4);
                                                                ((void (__fastcall *)(_QWORD, char *))off_180021140[0])(
                                                                  0,
                                                                  (char *)&v1156 + 12);
                                                                if ( v570 )
                                                                  v572 = DWORD1(v1156) + 5 * HIDWORD(v1156) / 100;
                                                                else
                                                                  v572 = 95 * (HIDWORD(v1156) - v566) / 100;
                                                                LODWORD(v1073) = v572;
                                                                DWORD1(v1073) = 95 * ((int)v1157 - (int)v1056) / 100;
                                                              }
                                                            }
                                                            v100 = 0;
                                                          }
                                                          else
                                                          {
                                                            v100 = 0;
                                                            *(_QWORD *)&v1073 = 0;
                                                          }
LABEL_843:
                                                          v452 = 0;
LABEL_846:
                                                          ((void (__fastcall *)(_QWORD, SIZE_T))off_180021160[0])(
                                                            0,
                                                            v1045);
                                                          goto LABEL_847;
                                                        }
                                                      }
                                                    }
                                                  }
LABEL_845:
                                                  v100 = 0;
                                                  goto LABEL_846;
                                                }
                                                LODWORD(v1060) = 11;
                                                goto LABEL_754;
                                              }
LABEL_724:
                                              v452 = -2147024882;
LABEL_725:
                                              if ( v521 )
                                              {
                                                for ( i4 = 0; i4 != 3; ++i4 )
                                                {
                                                  v532 = v521[i4];
                                                  if ( v532 )
                                                  {
                                                    v533 = -1;
                                                    do
                                                      ++v533;
                                                    while ( *(_WORD *)&v532[2 * v533] );
                                                    for ( i5 = 2 * v533 + 2; i5; --i5 )
                                                      *v532++ = 0;
                                                    MemoryFree(v521[i4]);
                                                  }
                                                }
                                              }
                                              v472 = v1078;
LABEL_735:
                                              v521 = (void **)v1043;
                                              goto LABEL_736;
                                            }
                                            MemoryFree(v471);
                                            v452 = -1073425151;
                                          }
                                          else
                                          {
                                            v452 = -2147024882;
                                          }
                                        }
                                        v472 = 0;
                                        goto LABEL_735;
                                      }
                                      v454 = MemoryAlloc(2LL * v1077);
                                      SP_MEM<unsigned long>::operator=(&lpMem, v454);
                                      v455 = (char *)lpMem;
                                      if ( lpMem
                                        && (v456 = MemoryAlloc(4LL * (v1070 + 1)),
                                            SP_MEM<unsigned long>::operator=(&pcchLength, v456),
                                            pcchLength) )
                                      {
                                        if ( ((unsigned int (__fastcall *)(__int64, unsigned int *, char *, unsigned int *))off_1800210A0[0])(
                                               8,
                                               &v1070,
                                               v455,
                                               &v1077) )
                                        {
                                          if ( v1070 )
                                          {
                                            v458 = (WCHAR *)pcchLength;
                                            for ( i6 = 0; i6 < v1070; ++i6 )
                                            {
                                              *(_DWORD *)v458 = ((__int64 (__fastcall *)(char *, _QWORD))off_1800210B0[0])(
                                                                  v455,
                                                                  0);
                                              v460 = -1;
                                              do
                                                ++v460;
                                              while ( *(_WORD *)&v455[2 * v460] );
                                              v458 += 2;
                                              v455 += 2 * v460 + 2;
                                            }
                                            v94 = Src;
                                            lpModuleName = v458;
                                            v461 = v458;
                                          }
                                          else
                                          {
                                            v461 = (_DWORD *)pcchLength;
                                          }
                                          v100 = pcchLength;
                                          *v461 = 1033;
                                          pcchLength = 0;
                                          LODWORD(v1056) = v1070 + 1;
                                          v1066 = v100;
                                          goto LABEL_671;
                                        }
                                        v452 = GetLastError();
                                        v457 = v452 < 0;
                                        if ( v452 > 0 )
                                        {
                                          v452 = (unsigned __int16)v452 | 0x80070000;
                                          v457 = v452 < 0;
                                        }
                                        if ( !v457 )
                                          v452 = -2147467259;
                                      }
                                      else
                                      {
                                        v452 = -2147024882;
                                      }
                                      v100 = v1063;
                                      goto LABEL_671;
                                    }
                                    v395 = dword_180021530;
LABEL_640:
                                    dword_180021530 = v395 + 1;
                                    goto LABEL_641;
                                  }
                                  v339 = dword_180021530;
LABEL_594:
                                  dword_180021530 = v339 + 1;
                                  goto LABEL_595;
                                }
LABEL_539:
                                v334 = GetProcessHeap();
                                HeapFree(v334, 0, v93);
                                goto LABEL_540;
                              }
                            }
                            if ( (_DWORD)v1057 != 6 )
                              goto LABEL_471;
                            *(_QWORD *)&v89 = lpMem;
                            v90 = 0;
                            while ( 1 )
                            {
                              *((_QWORD *)&v89 + 1) = v89 + 4;
                              if ( (__int64)v89 + 4 < (unsigned __int64)v89 )
                                break;
                              *(_QWORD *)&v89 = *((_QWORD *)&v89 + 1) + *(unsigned int *)v89;
                              if ( (unsigned __int64)v89 < *((_QWORD *)&v89 + 1) )
                                break;
                              v90 = (unsigned int)(v90 + 1);
                              if ( (_DWORD)v90 )
                              {
                                v90 = v89 + 4;
                                if ( (__int64)v89 + 4 < (unsigned __int64)v89 )
                                  break;
                                *((_QWORD *)&v89 + 1) = 0;
                                if ( *(_DWORD *)v89 )
                                  *((_QWORD *)&v89 + 1) = v89 + 4;
                                if ( *(_DWORD *)v89 == 8 )
                                {
                                  *(_QWORD *)&v89 = lpMem;
                                  lpModuleName = (LPCWSTR)**((_QWORD **)&v89 + 1);
                                  v90 = 0;
                                  while ( 1 )
                                  {
                                    *((_QWORD *)&v89 + 1) = v89 + 4;
                                    if ( (__int64)v89 + 4 < (unsigned __int64)v89 )
                                      goto LABEL_530;
                                    *(_QWORD *)&v89 = *((_QWORD *)&v89 + 1) + *(unsigned int *)v89;
                                    if ( (unsigned __int64)v89 < *((_QWORD *)&v89 + 1) )
                                      goto LABEL_530;
                                    v90 = (unsigned int)(v90 + 1);
                                    if ( (unsigned int)v90 >= 2 )
                                    {
                                      v90 = v89 + 4;
                                      if ( (__int64)v89 + 4 < (unsigned __int64)v89 )
                                        goto LABEL_530;
                                      *((_QWORD *)&v89 + 1) = 0;
                                      if ( *(_DWORD *)v89 )
                                        *((_QWORD *)&v89 + 1) = v89 + 4;
                                      if ( *(_DWORD *)v89 == 4 )
                                      {
                                        v332 = **((_DWORD **)&v89 + 1);
                                        *(_QWORD *)&v89 = lpMem;
                                        v90 = 0;
                                        LODWORD(v1051) = i8;
                                        while ( 1 )
                                        {
                                          *((_QWORD *)&v89 + 1) = v89 + 4;
                                          if ( (__int64)v89 + 4 < (unsigned __int64)v89 )
                                            goto LABEL_186;
                                          *(_QWORD *)&v89 = *((_QWORD *)&v89 + 1) + *(unsigned int *)v89;
                                          if ( (unsigned __int64)v89 < *((_QWORD *)&v89 + 1) )
                                            goto LABEL_186;
                                          v90 = (unsigned int)(v90 + 1);
                                          if ( (unsigned int)v90 >= 3 )
                                          {
                                            *((_QWORD *)&v89 + 1) = v89 + 4;
                                            if ( (__int64)v89 + 4 < (unsigned __int64)v89 )
                                              goto LABEL_186;
                                            i8 = *(unsigned int *)v89;
                                            if ( (_DWORD)i8 )
                                              v132 = (const void *)(v89 + 4);
                                            *(_QWORD *)&v89 = lpMem;
                                            v90 = 0;
                                            while ( 1 )
                                            {
                                              *((_QWORD *)&v89 + 1) = v89 + 4;
                                              if ( (__int64)v89 + 4 < (unsigned __int64)v89 )
                                                goto LABEL_530;
                                              *(_QWORD *)&v89 = *((_QWORD *)&v89 + 1) + *(unsigned int *)v89;
                                              if ( (unsigned __int64)v89 < *((_QWORD *)&v89 + 1) )
                                                goto LABEL_530;
                                              v90 = (unsigned int)(v90 + 1);
                                              if ( (unsigned int)v90 >= 4 )
                                              {
                                                v90 = v89 + 4;
                                                if ( (__int64)v89 + 4 < (unsigned __int64)v89 )
                                                  goto LABEL_530;
                                                *((_QWORD *)&v89 + 1) = 0;
                                                if ( *(_DWORD *)v89 )
                                                  *((_QWORD *)&v89 + 1) = v89 + 4;
                                                if ( *(_DWORD *)v89 == 4 )
                                                {
                                                  v90 = 0;
                                                  *(_QWORD *)&v89 = lpMem;
                                                  v333 = **((_DWORD **)&v89 + 1);
                                                  while ( 1 )
                                                  {
                                                    *((_QWORD *)&v89 + 1) = v89 + 4;
                                                    if ( (__int64)v89 + 4 < (unsigned __int64)v89 )
                                                      goto LABEL_530;
                                                    *(_QWORD *)&v89 = *((_QWORD *)&v89 + 1) + *(unsigned int *)v89;
                                                    if ( (unsigned __int64)v89 < *((_QWORD *)&v89 + 1) )
                                                      goto LABEL_530;
                                                    v90 = (unsigned int)(v90 + 1);
                                                    if ( (unsigned int)v90 >= 5 )
                                                    {
                                                      v90 = v89 + 4;
                                                      if ( (__int64)v89 + 4 < (unsigned __int64)v89 )
                                                        goto LABEL_530;
                                                      *((_QWORD *)&v89 + 1) = 0;
                                                      if ( *(_DWORD *)v89 )
                                                        *((_QWORD *)&v89 + 1) = v89 + 4;
                                                      if ( *(_DWORD *)v89 != 4 )
                                                        goto LABEL_523;
                                                      if ( (LPCWSTR)v1066 != lpModuleName )
                                                      {
                                                        v94 = -1073425151;
                                                        goto LABEL_191;
                                                      }
                                                      v95 = v332;
                                                      v1029 = **((_DWORD **)&v89 + 1);
                                                      v1068 = v332;
                                                      if ( v333 > 4 || (unsigned int)i8 > 4 )
                                                      {
                                                        v94 = -2147024774;
                                                        goto LABEL_191;
                                                      }
                                                      memcpy_0(v1084, v132, i8);
                                                      v94 = 0;
                                                      goto LABEL_189;
                                                    }
                                                  }
                                                }
                                                goto LABEL_523;
                                              }
                                            }
                                          }
                                        }
                                      }
                                      goto LABEL_523;
                                    }
                                  }
                                }
                                goto LABEL_523;
                              }
                            }
                          }
LABEL_530:
                          v94 = -1073741675;
                          goto LABEL_191;
                        }
                        v330 = GetProcessHeap();
                        HeapFree(v330, 0, v1058);
LABEL_468:
                        v132 = 0;
                        goto LABEL_469;
                      }
LABEL_445:
                      v317 = GetProcessHeap();
                      HeapFree(v317, 0, v1042);
                      v132 = 0;
                      goto LABEL_446;
                    }
                  }
                  v1065 = (SIZE_T)v99;
                }
                v182 = -1073741801;
                v197 = v1043;
                lpModuleName = *(LPCWSTR *)(v1043 + 8);
                if ( lpModuleName )
                {
                  v198 = GetProcessHeap();
                  HeapFree(v198, 0, (LPVOID)lpModuleName);
                  v197 = v1043;
                  *(_QWORD *)(v1043 + 8) = 0;
                }
                lpModuleName = *(LPCWSTR *)(v197 + 24);
                if ( lpModuleName )
                {
                  v199 = GetProcessHeap();
                  HeapFree(v199, 0, (LPVOID)lpModuleName);
                  v197 = v1043;
                  *(_QWORD *)(v1043 + 24) = 0;
                }
                lpModuleName = *(LPCWSTR *)(v197 + 40);
                if ( lpModuleName )
                {
                  v200 = GetProcessHeap();
                  HeapFree(v200, 0, (LPVOID)lpModuleName);
                  *(_QWORD *)(v1043 + 40) = 0;
                }
                v201 = GetProcessHeap();
                HeapFree(v201, 0, (LPVOID)v1043);
              }
              else
              {
                v182 = -1073741801;
              }
              v183 = v1047;
              goto LABEL_225;
            }
            *((_QWORD *)&v89 + 1) = (unsigned int)v89;
            v90 = (unsigned __int64)v104;
            for ( i7 = 0; i7 < v117; v90 += v123 )
            {
              v123 = *(_DWORD *)v90 + 4;
              if ( *(_DWORD *)v90 >= 0xFFFFFFFC )
                goto LABEL_186;
              i8 = v90 + v123;
              if ( i8 < v90 )
                goto LABEL_186;
              ++i7;
            }
            i8 = v90 + 4;
            if ( v90 + 4 >= v90 )
            {
              if ( v90 + 8 > (unsigned __int64)&v104[*((_QWORD *)&v89 + 1)] )
                goto LABEL_121;
              v121 = v117 + 1;
              *(_DWORD *)v90 = 4;
              *(_DWORD *)i8 = v1029;
              LODWORD(Size) = DWORD2(v89);
              v90 = (unsigned __int64)v104;
              v127 = 0;
              for ( i8 = DWORD2(v89); v127 < v121; v90 += v128 )
              {
                v128 = *(_DWORD *)v90 + 4;
                if ( *(_DWORD *)v90 >= 0xFFFFFFFC )
                  goto LABEL_186;
                *((_QWORD *)&v89 + 1) = v90 + v128;
                if ( *((_QWORD *)&v89 + 1) < v90 )
                  goto LABEL_186;
                ++v127;
              }
              *((_QWORD *)&v89 + 1) = v90 + 4;
              if ( v90 + 4 >= v90 )
              {
                if ( v90 + 8 > (unsigned __int64)&v104[(unsigned int)i8] )
                  goto LABEL_121;
                *(_DWORD *)v90 = 4;
                **((_DWORD **)&v89 + 1) = 4;
                goto LABEL_205;
              }
            }
LABEL_186:
            v94 = -1073741675;
            goto LABEL_187;
          }
          LODWORD(v89) = -1;
          v94 = -1073741675;
LABEL_173:
          Src = v94;
          goto LABEL_174;
        }
        goto LABEL_159;
      }
      *((_QWORD *)&v89 + 1) = v104;
      v119 = 0;
      if ( v117 )
      {
        while ( 1 )
        {
          LODWORD(v89) = **((_DWORD **)&v89 + 1) + 4;
          if ( **((_DWORD **)&v89 + 1) >= 0xFFFFFFFC
            || *((_QWORD *)&v89 + 1) + (unsigned __int64)(unsigned int)v89 < *((_QWORD *)&v89 + 1) )
          {
            break;
          }
          ++v119;
          *((_QWORD *)&v89 + 1) += (unsigned int)v89;
          if ( v119 >= v117 )
          {
            i8 = 0;
            goto LABEL_165;
          }
        }
        v94 = -1073741675;
      }
      else
      {
LABEL_165:
        lpModuleName = (LPCWSTR)(*((_QWORD *)&v89 + 1) + 4LL);
        if ( (unsigned __int64)(*((_QWORD *)&v89 + 1) + 4LL) < *((_QWORD *)&v89 + 1) )
        {
LABEL_159:
          v94 = -1073741675;
LABEL_172:
          LODWORD(v89) = (_DWORD)v1058;
          goto LABEL_173;
        }
        if ( *((_QWORD *)&v89 + 1) + v90 + 4 <= (unsigned __int64)&v104[v118] )
        {
          v120 = (WCHAR *)lpModuleName;
          v94 = 0;
          **((_DWORD **)&v89 + 1) = v90;
          Src = 0;
          memcpy_0(v120, L"AMR-CODECS-MSAMRNBInSKU", (unsigned int)v90);
          LODWORD(v89) = (_DWORD)v1058;
          v117 = v1062 + 1;
          i8 = 0;
          goto LABEL_174;
        }
        v94 = -1073741789;
      }
      i8 = 0;
      goto LABEL_172;
    }
    v5 = dword_180021530;
LABEL_46:
    dword_180021530 = v5 + 1;
    goto LABEL_47;
  }
  v4 = -2147024809;
LABEL_1492:
  SP_HLOCAL<unsigned char>::~SP_HLOCAL<unsigned char>(&v1081, pdwValue, v2, v3);
  return v4;
}

```

## disassembly

```asm
0x18000a634  push    rbp
0x18000a636  push    rbx
0x18000a637  push    rsi
0x18000a638  push    rdi
0x18000a639  push    r12
0x18000a63b  push    r13
0x18000a63d  push    r14
0x18000a63f  push    r15
0x18000a641  lea     rbp, [rsp-0D88h]
0x18000a649  sub     rsp, 0E88h
0x18000a650  mov     rax, cs:__security_cookie
0x18000a657  xor     rax, rsp
0x18000a65a  mov     [rbp+0DC0h+var_50], rax
0x18000a661  xor     r15d, r15d
0x18000a664  mov     [rbp+0DC0h+var_C90], rdx
0x18000a66b  mov     [rbp+0DC0h+var_D20], r15
0x18000a672  test    rdx, rdx
0x18000a675  jnz     short loc_18000A681
0x18000a677  mov     ebx, 80070057h
0x18000a67c  jmp     loc_1800136E6
0x18000a681  mov     dword ptr [rbp+0DC0h+var_DE0], r15d
0x18000a685  mov     esi, 1
0x18000a68a  mov     [rbp+0DC0h+var_DA8], r15
0x18000a68e  xor     eax, eax
0x18000a690  lock cmpxchg cs:dword_180021534, esi
0x18000a698  jnz     short loc_18000A68E
0x18000a69a  mov     eax, cs:dword_180021530
0x18000a6a0  lea     r14, unk_1800214D0
0x18000a6a7  or      ebx, 0FFFFFFFFh
0x18000a6aa  lea     r13, off_180021000
0x18000a6b1  mov     [rbp+0DC0h+var_D6C], ebx
0x18000a6b4  mov     r12d, 60h ; '`'
0x18000a6ba  test    eax, eax
0x18000a6bc  jnz     loc_18000AC2A
0x18000a6c2  call    cs:__imp_GetProcessHeap
0x18000a6c8  xor     edx, edx; dwFlags
0x18000a6ca  mov     r8d, 338h; dwBytes
0x18000a6d0  mov     rcx, rax; hHeap
0x18000a6d3  call    cs:__imp_HeapAlloc
0x18000a6d9  mov     rdi, rax
0x18000a6dc  test    rax, rax
0x18000a6df  jz      loc_18000AA5F
0x18000a6e5  mov     r14, rax
0x18000a6e8  lea     rsi, unk_18001E940
0x18000a6ef  mov     r12d, r15d
0x18000a6f2  mov     r10d, r15d
0x18000a6f5  mov     r8d, r15d
0x18000a6f8  mov     eax, 0AB69605Eh
0x18000a6fd  mov     r15d, 67h ; 'g'
0x18000a703  mov     r13d, ebx
0x18000a706  movzx   ecx, byte ptr [rsi]
0x18000a709  shl     ecx, 8
0x18000a70c  movzx   ebx, byte ptr [rsi+1]
0x18000a710  movzx   r11d, byte ptr [rsi+4]
0x18000a715  lea     rsi, [rsi+8]
0x18000a719  or      ebx, ecx
0x18000a71b  shl     r11d, 8
0x18000a71f  movzx   ecx, byte ptr [rsi-6]
0x18000a723  shl     ebx, 8
0x18000a726  or      ebx, ecx
0x18000a728  movzx   ecx, byte ptr [rsi-5]
0x18000a72c  shl     ebx, 8
0x18000a72f  or      ebx, ecx
0x18000a731  movzx   ecx, byte ptr [rsi-3]
0x18000a735  or      r11d, ecx
0x18000a738  mov     edx, ebx
0x18000a73a  movzx   ecx, byte ptr [rsi-2]
0x18000a73e  xor     edx, r8d
0x18000a741  mov     r8d, edx
0x18000a744  shl     r11d, 8
0x18000a748  or      r11d, ecx
0x18000a74b  movzx   ecx, byte ptr [rsi-1]
0x18000a74f  shl     r11d, 8
0x18000a753  or      r11d, ecx
0x18000a756  xor     r8d, r11d
0x18000a759  xor     r8d, r10d
0x18000a75c  xor     r8d, 0AC987321h
0x18000a763  lea     ecx, [r8+54969FA2h]
0x18000a76a  ror     ecx, 1Bh
0x18000a76d  imul    r9d, ecx, 137Fh
0x18000a774  mov     ecx, r8d
0x18000a777  ror     ecx, 16h
0x18000a77a  add     r9d, ecx
0x18000a77d  xor     r9d, edx
0x18000a780  lea     ecx, [r9+7F1137Fh]
0x18000a787  ror     ecx, 9
0x18000a78a  imul    edx, ecx, 0AB69h
0x18000a790  mov     ecx, r9d
0x18000a793  ror     ecx, 1Eh
0x18000a796  sub     edx, ecx
0x18000a798  xor     edx, r8d
0x18000a79b  imul    r10d, edx, 605Eh
0x18000a7a2  mov     ecx, edx
0x18000a7a4  shr     ecx, 0Dh
0x18000a7a7  sub     r10d, ecx
0x18000a7aa  sub     r10d, 756C8A2h
0x18000a7b1  xor     r10d, r9d
0x18000a7b4  mov     r9d, 7F1137Fh
0x18000a7ba  mov     ecx, r10d
0x18000a7bd  xor     ecx, 0AB69h
0x18000a7c3  ror     ecx, 1Ah
0x18000a7c6  imul    r8d, ecx, 7F1h
0x18000a7cd  mov     ecx, r10d
0x18000a7d0  ror     ecx, 1Eh
0x18000a7d3  sub     r8d, ecx
0x18000a7d6  xor     r8d, edx
0x18000a7d9  mov     ecx, r8d
0x18000a7dc  xor     ecx, eax
0x18000a7de  sub     r9d, ecx
0x18000a7e1  xor     r9d, r10d
0x18000a7e4  mov     ecx, r9d
0x18000a7e7  mov     r10d, r9d
0x18000a7ea  xor     ecx, 137Fh
0x18000a7f0  ror     r10d, 6
0x18000a7f4  imul    edx, ecx, 0AB69h
0x18000a7fa  xor     r10d, edx
0x18000a7fd  xor     r10d, r8d
0x18000a800  lea     ecx, [r10+7F1137Fh]
0x18000a807  ror     ecx, 0Fh
0x18000a80a  imul    edx, ecx, 605Eh
0x18000a810  mov     ecx, r10d
0x18000a813  ror     ecx, 1Eh
0x18000a816  add     edx, ecx
0x18000a818  xor     edx, r9d
0x18000a81b  lea     ecx, [rdx+54969FA2h]
0x18000a821  ror     ecx, 0Eh
0x18000a824  imul    r8d, ecx, 7F1h
0x18000a82b  mov     ecx, edx
0x18000a82d  ror     ecx, 18h
0x18000a830  sub     r8d, ecx
0x18000a833  xor     r8d, r10d
0x18000a836  mov     ecx, r8d
0x18000a839  mov     r10d, 7F1h
0x18000a83f  xor     ecx, eax
0x18000a841  ror     ecx, 0Ch
0x18000a844  imul    r9d, ecx, 137Fh
0x18000a84b  mov     ecx, r8d
0x18000a84e  ror     ecx, 0Ah
0x18000a851  xor     r9d, ecx
0x18000a854  xor     r9d, edx
0x18000a857  mov     ecx, r9d
0x18000a85a  xor     ecx, r10d
0x18000a85d  imul    edx, ecx, 0AB69h
0x18000a863  mov     ecx, r9d
0x18000a866  shr     ecx, 0Ah
0x18000a869  xor     edx, ecx
0x18000a86b  xor     edx, r8d
0x18000a86e  mov     ecx, edx
0x18000a870  not     ecx
0x18000a872  ror     ecx, 5
0x18000a875  add     ecx, 605Eh
0x18000a87b  imul    r8d, ecx, 7F1h
0x18000a882  xor     r8d, r9d
0x18000a885  lea     r9d, [r8-7F1h]
0x18000a88c  xor     r9d, edx
0x18000a88f  xor     r9d, eax
0x18000a892  mov     ecx, r9d
0x18000a895  xor     ecx, r10d
0x18000a898  ror     ecx, 1Eh
0x18000a89b  imul    r10d, ecx, 137Fh
0x18000a8a2  mov     ecx, r9d
0x18000a8a5  shr     ecx, 2
0x18000a8a8  add     r10d, ecx
0x18000a8ab  xor     r10d, r8d
0x18000a8ae  lea     ecx, [r10-7F1137Fh]
0x18000a8b5  ror     ecx, 6
0x18000a8b8  imul    r8d, ecx, 0AB69h
0x18000a8bf  mov     ecx, r10d
0x18000a8c2  ror     ecx, 19h
0x18000a8c5  add     r8d, ecx
0x18000a8c8  xor     r8d, r9d
0x18000a8cb  mov     ecx, r8d
0x18000a8ce  mov     r9d, r8d
0x18000a8d1  xor     ecx, 137Fh
0x18000a8d7  ror     r9d, 9
0x18000a8db  imul    edx, ecx, 605Eh
0x18000a8e1  add     r9d, edx
0x18000a8e4  xor     r9d, r10d
0x18000a8e7  mov     ecx, r9d
0x18000a8ea  xor     ecx, 0AB69h
0x18000a8f0  ror     ecx, 1Bh
0x18000a8f3  imul    edx, ecx, 7F1h
0x18000a8f9  mov     ecx, r9d
0x18000a8fc  ror     ecx, 19h
0x18000a8ff  add     edx, ecx
0x18000a901  xor     edx, r8d
0x18000a904  mov     r8d, edx
0x18000a907  xor     r8d, r9d
0x18000a90a  xor     r8d, 0AC987321h
0x18000a911  mov     ecx, r8d
0x18000a914  ror     ecx, 3
0x18000a917  imul    r9d, ecx, 137Fh
0x18000a91e  sub     r9d, 0D0DD417h
0x18000a925  xor     r9d, edx
0x18000a928  lea     ecx, [r9-7F1137Fh]
0x18000a92f  ror     ecx, 1
0x18000a931  imul    edx, ecx, 605Eh
0x18000a937  mov     ecx, r9d
0x18000a93a  ror     ecx, 6
0x18000a93d  sub     edx, ecx
0x18000a93f  xor     edx, r8d
0x18000a942  lea     ecx, [rdx-54969FA2h]
0x18000a948  ror     ecx, 1Dh
0x18000a94b  imul    r8d, ecx, 7F1h
0x18000a952  mov     ecx, edx
0x18000a954  ror     ecx, 12h
0x18000a957  add     r8d, ecx
0x18000a95a  xor     r8d, r9d
0x18000a95d  lea     ecx, [r8-54969FA2h]
0x18000a964  ror     ecx, 11h
0x18000a967  imul    r9d, ecx, 137Fh
0x18000a96e  mov     ecx, r8d
0x18000a971  ror     ecx, 0Eh
0x18000a974  sub     r9d, ecx
0x18000a977  xor     r9d, edx
0x18000a97a  mov     ecx, r9d
0x18000a97d  xor     ecx, 605Eh
0x18000a983  imul    r10d, ecx, 0AB69h
0x18000a98a  mov     ecx, r9d
0x18000a98d  shr     ecx, 3
0x18000a990  xor     r10d, ecx
0x18000a993  xor     r10d, r8d
0x18000a996  mov     ecx, r10d
0x18000a999  xor     ecx, 7F1137Fh
0x18000a99f  ror     ecx, 1Ch
0x18000a9a2  imul    r8d, ecx, 605Eh
0x18000a9a9  mov     ecx, r10d
0x18000a9ac  ror     ecx, 1Eh
0x18000a9af  xor     r10d, r13d
0x18000a9b2  mov     r13d, r11d
0x18000a9b5  xor     r8d, ecx
0x18000a9b8  xor     r8d, r9d
0x18000a9bb  xor     r8d, r12d
0x18000a9be  mov     r12d, ebx
0x18000a9c1  mov     [r14+3], r8b
0x18000a9c5  mov     ecx, r8d
0x18000a9c8  ror     ecx, 8
0x18000a9cb  mov     [r14+7], r10b
0x18000a9cf  mov     [r14+2], cl
0x18000a9d3  mov     ecx, r10d
0x18000a9d6  ror     ecx, 8
0x18000a9d9  mov     [r14+6], cl
0x18000a9dd  mov     ecx, r8d
0x18000a9e0  ror     ecx, 10h
0x18000a9e3  mov     [r14+1], cl
0x18000a9e7  mov     ecx, r10d
0x18000a9ea  ror     ecx, 10h
0x18000a9ed  mov     [r14+5], cl
0x18000a9f1  mov     ecx, r8d
0x18000a9f4  ror     ecx, 18h
0x18000a9f7  mov     [r14], cl
0x18000a9fa  mov     ecx, r10d
0x18000a9fd  ror     ecx, 18h
0x18000aa00  mov     [r14+4], cl
0x18000aa04  lea     r14, [r14+8]
0x18000aa08  sub     r15, 1
0x18000aa0c  jnz     loc_18000A706
0x18000aa12  mov     rcx, r15
0x18000aa15  lea     esi, [r15+1]
0x18000aa19  mov     al, r15b
0x18000aa1c  xor     al, [rdi+rcx]
0x18000aa1f  add     rcx, rsi
0x18000aa22  cmp     rcx, 338h
0x18000aa29  jb      short loc_18000AA1C
0x18000aa2b  movzx   ecx, al
0x18000aa2e  cmp     rcx, cs:qword_18001EC78
0x18000aa35  jz      short loc_18000AAA5
0x18000aa37  call    cs:__imp_GetProcessHeap
0x18000aa3d  mov     r8, rdi; lpMem
0x18000aa40  xor     edx, edx; dwFlags
0x18000aa42  mov     rcx, rax; hHeap
0x18000aa45  call    cs:__imp_HeapFree
0x18000aa4b  lea     r13, off_180021000
0x18000aa52  mov     r12d, 60h ; '`'
0x18000aa58  lea     r14, unk_1800214D0
0x18000aa5f  mov     rbx, r15
0x18000aa62  lea     rax, [rbx+rbx*2]
0x18000aa66  mov     rcx, [r14+rax*8]; hLibModule
0x18000aa6a  test    rcx, rcx
0x18000aa6d  jz      short loc_18000AA75
0x18000aa6f  call    cs:__imp_FreeLibrary
0x18000aa75  add     rbx, rsi
0x18000aa78  cmp     rbx, 4
0x18000aa7c  jnz     short loc_18000AA62
0x18000aa7e  mov     r8, r12; Size
0x18000aa81  xor     edx, edx; Val
0x18000aa83  mov     rcx, r14; void *
0x18000aa86  call    memset_0
0x18000aa8b  mov     r8d, 170h; Size
0x18000aa91  lea     rdx, off_180015170; Src
0x18000aa98  mov     rcx, r13; void *
0x18000aa9b  call    memcpy_0
0x18000aaa0  jmp     loc_18000AC32
0x18000aaa5  xor     edx, edx; Val
0x18000aaa7  mov     dword ptr [rbp+0DC0h+Size], r15d
0x18000aaab  lea     r14, unk_1800214D0
0x18000aab2  mov     [rdi+337h], r15b
0x18000aab9  mov     rcx, r14; void *
0x18000aabc  mov     r12d, r15d
0x18000aabf  lea     r8d, [rdx+60h]; Size
  ... truncated ...
```
