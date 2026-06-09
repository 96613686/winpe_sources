# pExtractWinREFromImage(ushort const *,ulong,ushort const *,ushort const *,void *,SetupPlatform::IGenericProgress *)

- ea: `0x1802882b8`
- end: `0x180288f33`
- name: `?pExtractWinREFromImage@@YAJPEBGK00PEAXPEAUIGenericProgress@SetupPlatform@@@Z`
- size: `3195`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int, const unsigned __int16 *, const unsigned __int16 *, void *, struct SetupPlatform::IGenericProgress *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180280fe0`

## callees

- `0x180044820`
- `0x180057dec`
- `0x18009a328`
- `0x1800b4700`
- `0x1802882b8`
- `0x1804791fc`
- `0x180479248`
- `0x180479580`
- `0x180479604`
- `0x1804799e4`
- `0x180479ed4`
- `0x1804bbfa0`
- `0x180509010`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x1802887d1`
- `KERNEL32!GetProcessHeap` at `0x1802889c8`
- `KERNEL32!GetProcessHeap` at `0x180288a06`
- `KERNEL32!GetProcessHeap` at `0x180288ad7`
- `KERNEL32!GetProcessHeap` at `0x180288b19`
- `KERNEL32!GetProcessHeap` at `0x180288bce`
- `KERNEL32!GetProcessHeap` at `0x180288c10`
- `KERNEL32!GetProcessHeap` at `0x180288cb4`
- `KERNEL32!GetProcessHeap` at `0x180288cf2`
- `KERNEL32!GetProcessHeap` at `0x1802887d1`
- `KERNEL32!GetProcessHeap` at `0x1802889c8`
- `KERNEL32!GetProcessHeap` at `0x180288a06`
- `KERNEL32!GetProcessHeap` at `0x180288ad7`
- `KERNEL32!GetProcessHeap` at `0x180288b19`
- `KERNEL32!GetProcessHeap` at `0x180288bce`
- `KERNEL32!GetProcessHeap` at `0x180288c10`
- `KERNEL32!GetProcessHeap` at `0x180288cb4`
- `KERNEL32!GetProcessHeap` at `0x180288cf2`
- `KERNEL32!HeapAlloc` at `0x1802887e2`
- `KERNEL32!HeapAlloc` at `0x1802887e2`
- `KERNEL32!HeapFree` at `0x1802889d6`
- `KERNEL32!HeapFree` at `0x180288a14`
- `KERNEL32!HeapFree` at `0x180288ae5`
- `KERNEL32!HeapFree` at `0x180288b27`
- `KERNEL32!HeapFree` at `0x180288bdc`
- `KERNEL32!HeapFree` at `0x180288c1e`
- `KERNEL32!HeapFree` at `0x180288cc2`
- `KERNEL32!HeapFree` at `0x180288d00`
- `KERNEL32!HeapFree` at `0x1802889d6`
- `KERNEL32!HeapFree` at `0x180288a14`
- `KERNEL32!HeapFree` at `0x180288ae5`
- `KERNEL32!HeapFree` at `0x180288b27`
- `KERNEL32!HeapFree` at `0x180288bdc`
- `KERNEL32!HeapFree` at `0x180288c1e`
- `KERNEL32!HeapFree` at `0x180288cc2`
- `KERNEL32!HeapFree` at `0x180288d00`
- `KERNEL32!GetLastError` at `0x18028833c`
- `KERNEL32!GetLastError` at `0x180288354`
- `KERNEL32!GetLastError` at `0x18028836c`
- `KERNEL32!GetLastError` at `0x180288409`
- `KERNEL32!GetLastError` at `0x180288421`
- `KERNEL32!GetLastError` at `0x180288439`
- `KERNEL32!GetLastError` at `0x18028858f`
- `KERNEL32!GetLastError` at `0x1802885a7`
- `KERNEL32!GetLastError` at `0x1802885bf`
- `KERNEL32!GetLastError` at `0x180288a50`
- `KERNEL32!GetLastError` at `0x180288b47`
- `KERNEL32!GetLastError` at `0x180288c2e`
- `KERNEL32!GetLastError` at `0x180288d58`
- `KERNEL32!GetLastError` at `0x180288de0`
- `KERNEL32!GetLastError` at `0x180288e45`
- `KERNEL32!GetLastError` at `0x18028833c`
- `KERNEL32!GetLastError` at `0x180288354`
- `KERNEL32!GetLastError` at `0x18028836c`
- `KERNEL32!GetLastError` at `0x180288409`
- `KERNEL32!GetLastError` at `0x180288421`
- `KERNEL32!GetLastError` at `0x180288439`
- `KERNEL32!GetLastError` at `0x18028858f`
- `KERNEL32!GetLastError` at `0x1802885a7`
- `KERNEL32!GetLastError` at `0x1802885bf`
- `KERNEL32!GetLastError` at `0x180288a50`
- `KERNEL32!GetLastError` at `0x180288b47`
- `KERNEL32!GetLastError` at `0x180288c2e`
- `KERNEL32!GetLastError` at `0x180288d58`
- `KERNEL32!GetLastError` at `0x180288de0`
- `KERNEL32!GetLastError` at `0x180288e45`
- `unbcl!?get_Length@String@UnBCL@@QEBAHXZ` at `0x180288878`
- `unbcl!?get_Length@String@UnBCL@@QEBAHXZ` at `0x180288878`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1802884c1`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x18028850e`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x180288680`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1802884c1`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x18028850e`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x180288680`
- `unbcl!?Replace@String@UnBCL@@QEBAPEAV12@PEBG0W4StringCasing@12@@Z` at `0x1802887ab`
- `unbcl!?Replace@String@UnBCL@@QEBAPEAV12@PEBG0W4StringCasing@12@@Z` at `0x1802887ab`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180288502`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180288502`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802884d9`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802884e4`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180288540`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180288698`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802886a3`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802884d9`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802884e4`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180288540`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180288698`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802886a3`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1802884a4`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1802884b4`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1802884f5`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180288663`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180288673`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18028876a`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1802884a4`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1802884b4`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1802884f5`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180288663`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180288673`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18028876a`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18028873e`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18028873e`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18028852a`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18028852a`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18028854a`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802886b7`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180288791`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180288859`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18028886f`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180288e5a`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18028854a`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802886b7`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180288791`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180288859`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18028886f`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180288e5a`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180288553`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1802886c0`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180288862`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180288e63`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180288553`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1802886c0`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180288862`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180288e63`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180288535`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802889e5`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802889f0`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180288a2d`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180288af4`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180288aff`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180288beb`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180288bf6`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180288cd1`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180288cdc`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180288d19`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180288d24`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180288eda`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180288ee5`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180288535`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802889e5`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802889f0`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180288a2d`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180288af4`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180288aff`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180288beb`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180288bf6`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180288cd1`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180288cdc`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180288d19`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180288d24`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180288eda`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180288ee5`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1802884ce`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18028851b`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18028868d`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180288786`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1802887b8`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1802884ce`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18028851b`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18028868d`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180288786`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1802887b8`
- `WDSCORE!WdsSetupLogMessageW` at `0x1802883d9`
- `WDSCORE!WdsSetupLogMessageW` at `0x180288629`
- `WDSCORE!WdsSetupLogMessageW` at `0x180288aba`
- `WDSCORE!WdsSetupLogMessageW` at `0x180288bb1`
- `WDSCORE!WdsSetupLogMessageW` at `0x180288c97`
- `WDSCORE!WdsSetupLogMessageW` at `0x180288dc2`
- `WDSCORE!WdsSetupLogMessageW` at `0x180288ec5`
- `WDSCORE!WdsSetupLogMessageW` at `0x1802883d9`
- `WDSCORE!WdsSetupLogMessageW` at `0x180288629`
- `WDSCORE!WdsSetupLogMessageW` at `0x180288aba`
- `WDSCORE!WdsSetupLogMessageW` at `0x180288bb1`
- `WDSCORE!WdsSetupLogMessageW` at `0x180288c97`
- `WDSCORE!WdsSetupLogMessageW` at `0x180288dc2`
- `WDSCORE!WdsSetupLogMessageW` at `0x180288ec5`
- `WDSCORE!CurrentIP` at `0x180288374`
- `WDSCORE!CurrentIP` at `0x180288441`
- `WDSCORE!CurrentIP` at `0x1802885c7`
- `WDSCORE!CurrentIP` at `0x180288a58`
- `WDSCORE!CurrentIP` at `0x180288b4f`
- `WDSCORE!CurrentIP` at `0x180288c36`
- `WDSCORE!CurrentIP` at `0x180288d60`
- `WDSCORE!CurrentIP` at `0x180288de8`
- `WDSCORE!CurrentIP` at `0x180288e4d`
- `WDSCORE!CurrentIP` at `0x180288374`
- `WDSCORE!CurrentIP` at `0x180288441`
- `WDSCORE!CurrentIP` at `0x1802885c7`
- `WDSCORE!CurrentIP` at `0x180288a58`
- `WDSCORE!CurrentIP` at `0x180288b4f`
- `WDSCORE!CurrentIP` at `0x180288c36`
- `WDSCORE!CurrentIP` at `0x180288d60`
- `WDSCORE!CurrentIP` at `0x180288de8`
- `WDSCORE!CurrentIP` at `0x180288e4d`
- `WIMGAPI!WIMCreateFile` at `0x180288316`
- `WIMGAPI!WIMCreateFile` at `0x180288316`
- `WIMGAPI!WIMSetTemporaryPath` at `0x1802883fb`
- `WIMGAPI!WIMSetTemporaryPath` at `0x1802883fb`
- `WIMGAPI!WIMExtractImagePathByWimHandle` at `0x180288581`
- `WIMGAPI!WIMExtractImagePathByWimHandle` at `0x180288581`

## string_xrefs

- `0x180288575`: `\Windows\System32\Recovery\winre.wim`
- `0x180288450`: `pExtractWinREFromImage: Failed to set WIM temp directory to %s (0x%08x)`
- `0x180288383`: `pExtractWinREFromImage: Failed to open %s to get recovery image (0x%08x)`
- `0x180288c42`: `pExtractWinREFromImage: Failed to copy new device element path. Error = 0x%08X`
- `0x180288e6f`: `pExtractWinREFromImage: Failed to open BCD store at %s. Error = 0x%08X`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
__int64 __fastcall pExtractWinREFromImage(const char *a1, unsigned int a2, const unsigned __int16 *a3, const char *a4)
{
  signed int LastError; // eax
  bool v9; // sf
  signed int v10; // eax
  unsigned int v11; // esi
  DWORD v12; // edi
  __int64 v13; // rbx
  struct tagLOG_PARTIAL_MSG *v14; // rax
  __int64 v15; // rax
  signed int v16; // eax
  bool v17; // sf
  signed int v18; // eax
  DWORD v19; // edi
  __int64 v20; // rbx
  struct tagLOG_PARTIAL_MSG *v21; // rax
  const struct UnBCL::String *v22; // rbx
  const struct UnBCL::String *v23; // rax
  struct UnBCL::String *v24; // rax
  const struct UnBCL::String *v25; // rbx
  const struct UnBCL::String *P; // rax
  struct UnBCL::String *v27; // rax
  UnBCL::String *v28; // rax
  const unsigned __int16 *CString; // rbx
  __int64 v30; // rax
  signed int v31; // eax
  bool v32; // sf
  signed int v33; // eax
  DWORD v34; // edi
  __int64 v35; // rbx
  struct tagLOG_PARTIAL_MSG *v36; // rax
  int v37; // r14d
  const struct UnBCL::String *v38; // rbx
  const struct UnBCL::String *v39; // rax
  struct UnBCL::String *v40; // rax
  UnBCL::String *v41; // rax
  const unsigned __int16 *v42; // rax
  int v43; // eax
  int DefaultBootEntry; // eax
  void **v45; // rax
  int DeviceElementData; // eax
  UnBCL::String *v47; // rbx
  __int64 v48; // rax
  __int64 v49; // rax
  __int64 v50; // rax
  unsigned int v51; // r13d
  HANDLE v52; // rax
  LPVOID v53; // rdx
  int v54; // ebx
  __int128 v55; // xmm6
  UnBCL::String *v56; // rax
  const unsigned __int16 *v57; // rdi
  UnBCL::String *v58; // rax
  unsigned __int64 v59; // rbx
  __int64 v60; // rax
  int v61; // r15d
  __int64 v62; // rsi
  __int64 v63; // rdi
  __int64 v64; // rax
  unsigned int v65; // ebx
  __int64 v66; // rbx
  void *v67; // rax
  int v68; // eax
  void *v69; // rax
  int v70; // eax
  void *v71; // rbx
  HANDLE v72; // rax
  void *v73; // rbx
  HANDLE v74; // rax
  DWORD v75; // edi
  __int64 v76; // rbx
  struct tagLOG_PARTIAL_MSG *v77; // rax
  void *v78; // rbx
  HANDLE v79; // rax
  void *v80; // rbx
  HANDLE ProcessHeap; // rax
  DWORD v82; // edi
  __int64 v83; // rbx
  struct tagLOG_PARTIAL_MSG *v84; // rax
  void *v85; // rbx
  HANDLE v86; // rax
  DWORD v87; // edi
  __int64 v88; // rbx
  struct tagLOG_PARTIAL_MSG *v89; // rax
  void *v90; // rbx
  HANDLE v91; // rax
  void *v92; // rbx
  HANDLE v93; // rax
  DWORD v95; // edi
  __int64 v96; // rbx
  struct tagLOG_PARTIAL_MSG *v97; // rax
  DWORD v98; // edi
  __int64 v99; // rbx
  struct tagLOG_PARTIAL_MSG *v100; // rax
  DWORD v101; // edi
  __int64 v102; // rbx
  UnBCL::String *v103; // rax
  const char *v104; // rax
  struct tagLOG_PARTIAL_MSG *v105; // rax
  void **v106; // [rsp+68h] [rbp-A0h] BYREF
  LPVOID lpMem; // [rsp+70h] [rbp-98h]
  void **v108; // [rsp+78h] [rbp-90h] BYREF
  void *v109; // [rsp+80h] [rbp-88h]
  void **v110; // [rsp+88h] [rbp-80h] BYREF
  __int64 v111; // [rsp+90h] [rbp-78h]
  unsigned int v112; // [rsp+98h] [rbp-70h] BYREF
  _BYTE v113[16]; // [rsp+A0h] [rbp-68h] BYREF
  _BYTE v114[16]; // [rsp+B0h] [rbp-58h] BYREF
  _BYTE v115[16]; // [rsp+C0h] [rbp-48h] BYREF
  _BYTE v116[32]; // [rsp+D0h] [rbp-38h] BYREF
  _BYTE v117[24]; // [rsp+F0h] [rbp-18h] BYREF
  __int64 v118; // [rsp+108h] [rbp+0h]
  UnBCL::String *v119; // [rsp+110h] [rbp+8h]
  _BYTE v120[24]; // [rsp+118h] [rbp+10h] BYREF
  _BYTE v121[24]; // [rsp+130h] [rbp+28h] BYREF
  _BYTE v122[24]; // [rsp+148h] [rbp+40h] BYREF
  _BYTE v123[24]; // [rsp+160h] [rbp+58h] BYREF
  struct _GUID v124; // [rsp+178h] [rbp+70h] BYREF

  v118 = -2;
  v111 = WIMCreateFile(a1, 0x80000000LL, 3, 0, 0, 0);
  v110 = &RAII::CAutoWimClose::`vftable';
  if ( (unsigned __int8)RAII::CAutoCleanupBase<ISetupOneSettings *>::operator!(&v110) )
  {
    LastError = GetLastError();
    v9 = LastError < 0;
    if ( LastError > 0 )
      v9 = 1;
    if ( v9 )
    {
      v10 = GetLastError();
      v11 = v10;
      if ( v10 > 0 )
        v11 = (unsigned __int16)v10 | 0x80070000;
    }
    else
    {
      v11 = -2147467259;
    }
    v12 = GetLastError();
    v13 = CurrentIP();
    v14 = ConstructPartialMsgW(
            0x2000000u,
            "pExtractWinREFromImage: Failed to open %s to get recovery image (0x%08x)",
            a1,
            v11);
    WdsSetupLogMessageW(
      v14,
      819200,
      L"D",
      0,
      1282,
      L"base\\ntsetup\\setupplatform\\lib\\project\\deploymentproject.cpp",
      L"pExtractWinREFromImage",
      v13,
      v12,
      0,
      0);
LABEL_75:
    v110 = &RAII::CAutoWimClose::`vftable';
    if ( v111 )
      WIMCloseHandle(v111);
    return v11;
  }
  v15 = ((__int64 (__fastcall *)(void ***))v110[4])(&v110);
  if ( !(unsigned int)WIMSetTemporaryPath(v15, a4) )
  {
    v16 = GetLastError();
    v17 = v16 < 0;
    if ( v16 > 0 )
      v17 = 1;
    if ( v17 )
    {
      v18 = GetLastError();
      v11 = v18;
      if ( v18 > 0 )
        v11 = (unsigned __int16)v18 | 0x80070000;
    }
    else
    {
      v11 = -2147467259;
    }
    v19 = GetLastError();
    v20 = CurrentIP();
    v21 = ConstructPartialMsgW(
            0x2000000u,
            "pExtractWinREFromImage: Failed to set WIM temp directory to %s (0x%08x)",
            a4,
            v11);
    WdsSetupLogMessageW(
      v21,
      819200,
      L"D",
      0,
      1289,
      L"base\\ntsetup\\setupplatform\\lib\\project\\deploymentproject.cpp",
      L"pExtractWinREFromImage",
      v20,
      v19,
      0,
      0);
    goto LABEL_75;
  }
  v22 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v121, L"sources");
  v23 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v120, a3);
  v24 = UnBCL::Path::Combine(v23, v22);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v113, v24);
  UnBCL::String::~String((UnBCL::String *)v120);
  UnBCL::String::~String((UnBCL::String *)v121);
  v25 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v117, L"winre.wim");
  P = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v113);
  v27 = UnBCL::Path::Combine(P, v25);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v124, v27);
  UnBCL::SmartPtr<UnBCL::String>::operator=(v113, &v124);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(&v124);
  UnBCL::String::~String((UnBCL::String *)v117);
  v28 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v113);
  CString = UnBCL::String::get_CString(v28);
  v30 = ((__int64 (__fastcall *)(void ***))v110[4])(&v110);
  if ( !(unsigned int)WIMExtractImagePathByWimHandle(v30, a2, L"\\Windows\\System32\\Recovery\\winre.wim", CString, 0) )
  {
    v31 = GetLastError();
    v32 = v31 < 0;
    if ( v31 > 0 )
      v32 = 1;
    if ( v32 )
    {
      v33 = GetLastError();
      v11 = v33;
      if ( v33 > 0 )
        v11 = (unsigned __int16)v33 | 0x80070000;
    }
    else
    {
      v11 = -2147467259;
    }
    v34 = GetLastError();
    v35 = CurrentIP();
    v36 = ConstructPartialMsgW(
            0x2000000u,
            "pExtractWinREFromImage: Failed to extract winre.wim recovery image file (0x%08x)",
            v11);
    WdsSetupLogMessageW(
      v36,
      819200,
      L"D",
      0,
      1299,
      L"base\\ntsetup\\setupplatform\\lib\\project\\deploymentproject.cpp",
      L"pExtractWinREFromImage",
      v35,
      v34,
      0,
      0);
LABEL_74:
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v113);
    goto LABEL_75;
  }
  if ( v111 )
  {
    WIMCloseHandle(v111);
    v111 = 0;
  }
  v37 = 0;
  while ( 1 )
  {
    v38 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v123, off_180548500[v37]);
    v39 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v122, a3);
    v40 = UnBCL::Path::Combine(v39, v38);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v114, v40);
    UnBCL::String::~String((UnBCL::String *)v122);
    UnBCL::String::~String((UnBCL::String *)v123);
    OSRollbackUtils::CBCDManipulator::CBCDManipulator((OSRollbackUtils::CBCDManipulator *)v116);
    v41 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v114);
    v42 = UnBCL::String::get_CString(v41);
    v43 = OSRollbackUtils::CBCDManipulator::Open((OSRollbackUtils::CBCDManipulator *)v116, v42);
    v11 = v43;
    if ( v43 )
    {
      if ( v43 > 0 )
        v11 = (unsigned __int16)v43 | 0x80070000;
      v101 = GetLastError();
      v102 = CurrentIP();
      v103 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v114);
      v104 = (const char *)UnBCL::String::get_CString(v103);
      v105 = ConstructPartialMsgW(
               0x2000000u,
               "pExtractWinREFromImage: Failed to open BCD store at %s. Error = 0x%08X",
               v104,
               v11);
      WdsSetupLogMessageW(
        v105,
        819200,
        L"D",
        0,
        1318,
        L"base\\ntsetup\\setupplatform\\lib\\project\\deploymentproject.cpp",
        L"pExtractWinREFromImage",
        v102,
        v101,
        0,
        0);
      goto LABEL_73;
    }
    v124 = 0;
    DefaultBootEntry = OSRollbackUtils::CBCDManipulator::GetDefaultBootEntry(
                         (OSRollbackUtils::CBCDManipulator *)v116,
                         &v124);
    v11 = DefaultBootEntry;
    if ( DefaultBootEntry )
    {
      if ( DefaultBootEntry > 0 )
        v11 = (unsigned __int16)DefaultBootEntry | 0x80070000;
      v98 = GetLastError();
      v99 = CurrentIP();
      v100 = ConstructPartialMsgW(
               0x2000000u,
               "pExtractWinREFromImage: Failed to get default boot entry from BCD store. Error = 0x%08X",
               v11);
      WdsSetupLogMessageW(
        v100,
        819200,
        L"D",
        0,
        1328,
        L"base\\ntsetup\\setupplatform\\lib\\project\\deploymentproject.cpp",
        L"pExtractWinREFromImage",
        v99,
        v98,
        0,
        0);
      goto LABEL_73;
    }
    v109 = 0;
    v108 = &RAII::CAutoWdsLibFree<_BCDE_DEVICE *>::`vftable';
    v112 = 0;
    v45 = (void **)RAII::CAutoCleanupBase<VdsVolumePathEnumerator *>::operator&(&v108);
    DeviceElementData = OSRollbackUtils::CBCDManipulator::GetDeviceElementData(
                          (OSRollbackUtils::CBCDManipulator *)v116,
                          &v124,
                          0x11000001u,
                          v45,
                          &v112);
    v11 = DeviceElementData;
    if ( DeviceElementData )
    {
      if ( DeviceElementData > 0 )
        v11 = (unsigned __int16)DeviceElementData | 0x80070000;
      v95 = GetLastError();
      v96 = CurrentIP();
      v97 = ConstructPartialMsgW(
              0x2000000u,
              "pExtractWinREFromImage: Failed to get device element data. Error = 0x%08X",
              v11);
      WdsSetupLogMessageW(
        v97,
        819200,
        L"D",
        0,
        1344,
        L"base\\ntsetup\\setupplatform\\lib\\project\\deploymentproject.cpp",
        L"pExtractWinREFromImage",
        v96,
        v95,
        0,
        0);
LABEL_48:
      v108 = &RAII::CAutoWdsLibFree<_BCDE_DEVICE *>::`vftable';
      v80 = v109;
      if ( !v109 )
      {
LABEL_73:
        OSRollbackUtils::CBCDManipulator::~CBCDManipulator((OSRollbackUtils::CBCDManipulator *)v116);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v114);
        goto LABEL_74;
      }
LABEL_49:
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v80);
      v109 = 0;
      goto LABEL_73;
    }
    v47 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
    v119 = v47;
    if ( v47 )
    {
      v48 = ((__int64 (__fastcall *)(void ***))v108[3])(&v108);
      UnBCL::String::String(v47, (const unsigned __int16 *)(v48 + 24));
      *(_QWORD *)v47 = &UnBCL::String::`local vftable';
    }
    else
    {
      v47 = 0;
    }
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v117, v47);
    v49 = UnBCL::SmartPtr<UnBCL::String>::operator->(v117);
    v50 = UnBCL::String::Replace(v49, L"boot.wim", L"winre.wim", 0);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v115, v50);
    lpMem = 0;
    v106 = &RAII::CAutoWdsLibFree<_BCDE_DEVICE *>::`vftable';
    v51 = v112 + 2;
    v52 = GetProcessHeap();
    v53 = HeapAlloc(v52, 8u, v51);
    RAII::CAutoWdsLibFree<_ENUM_SERVICE_STATUSW *>::operator=(&v106, v53);
    v54 = *(_DWORD *)((__int64 (__fastcall *)(void ***))v108[3])(&v108);
    *(_DWORD *)((__int64 (__fastcall *)(void ***))v106[3])(&v106) = v54;
    v55 = *(_OWORD *)(((__int64 (__fastcall *)(void ***))v108[3])(&v108) + 4);
    *(_OWORD *)(((__int64 (__fastcall *)(void ***))v106[3])(&v106) + 4) = v55;
    v56 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v115);
    v57 = UnBCL::String::get_CString(v56);
    v58 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v115);
    v59 = UnBCL::String::get_Length(v58) + 1;
    v60 = ((__int64 (__fastcall *)(void ***))v106[3])(&v106);
    v61 = StringCchCopyW((unsigned __int16 *)(v60 + 24), v59, v57);
    if ( v61 < 0 )
      break;
    v62 = *(unsigned int *)(((__int64 (__fastcall *)(void ***))v108[3])(&v108) + 20);
    v63 = ((__int64 (__fastcall *)(void ***))v108[4])(&v108);
    v64 = ((__int64 (__fastcall *)(void ***))v108[3])(&v108);
    v65 = v51 + *(_DWORD *)(v64 + 20) - v112;
    *(_DWORD *)(((__int64 (__fastcall *)(void ***))v106[3])(&v106) + 20) = v65;
    v66 = *(unsigned int *)(((__int64 (__fastcall *)(void ***))v106[3])(&v106) + 20);
    *(_DWORD *)(((__int64 (__fastcall *)(void ***))v106[4])(&v106) + v66) = *(_DWORD *)(v63 + v62);
    v67 = (void *)((__int64 (__fastcall *)(void ***))v106[4])(&v106);
    v68 = OSRollbackUtils::CBCDManipulator::SetDeviceElementData(
            (OSRollbackUtils::CBCDManipulator *)v116,
            &v124,
            0x11000001u,
            v67,
            v51);
    v11 = v68;
    if ( v68 )
    {
      if ( v68 > 0 )
        v11 = (unsigned __int16)v68 | 0x80070000;
      v82 = GetLastError();
      v83 = CurrentIP();
      v84 = ConstructPartialMsgW(
              0x2000000u,
              "pExtractWinREFromImage: Failed to set new device element data. Error = 0x%08X",
              v11);
      WdsSetupLogMessageW(
        v84,
        819200,
        L"D",
        0,
        1388,
        L"base\\ntsetup\\setupplatform\\lib\\project\\deploymentproject.cpp",
        L"pExtractWinREFromImage",
        v83,
        v82,
        0,
        0);
      v106 = &RAII::CAutoWdsLibFree<_BCDE_DEVICE *>::`vftable';
      v85 = lpMem;
      if ( lpMem )
      {
        v86 = GetProcessHeap();
        HeapFree(v86, 0, v85);
        lpMem = 0;
      }
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v115);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v117);
      v108 = &RAII::CAutoWdsLibFree<_BCDE_DEVICE *>::`vftable';
      v80 = v109;
      if ( !v109 )
        goto LABEL_73;
      goto LABEL_49;
    }
    v69 = (void *)((__int64 (__fastcall *)(void ***))v106[4])(&v106);
    v70 = OSRollbackUtils::CBCDManipulator::SetDeviceElementData(
            (OSRollbackUtils::CBCDManipulator *)v116,
            &v124,
            0x21000001u,
            v69,
            v51);
    v11 = v70;
    if ( v70 )
    {
      if ( v70 > 0 )
        v11 = (unsigned __int16)v70 | 0x80070000;
      v75 = GetLastError();
      v76 = CurrentIP();
      v77 = ConstructPartialMsgW(
              0x2000000u,
              "pExtractWinREFromImage: Failed to set new OS device element data. Error = 0x%08X",
              v11);
      WdsSetupLogMessageW(
        v77,
        819200,
        L"D",
        0,
        1402,
        L"base\\ntsetup\\setupplatform\\lib\\project\\deploymentproject.cpp",
        L"pExtractWinREFromImage",
        v76,
        v75,
        0,
        0);
      v106 = &RAII::CAutoWdsLibFree<_BCDE_DEVICE *>::`vftable';
      v78 = lpMem;
      if ( lpMem )
      {
        v79 = GetProcessHeap();
        HeapFree(v79, 0, v78);
        lpMem = 0;
      }
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v115);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v117);
      goto LABEL_48;
    }
    v106 = &RAII::CAutoWdsLibFree<_BCDE_DEVICE *>::`vftable';
    v71 = lpMem;
    if ( lpMem )
    {
      v72 = GetProcessHeap();
      HeapFree(v72, 0, v71);
      lpMem = 0;
    }
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v115);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v117);
    v108 = &RAII::CAutoWdsLibFree<_BCDE_DEVICE *>::`vftable';
    v73 = v109;
    if ( v109 )
    {
      v74 = GetProcessHeap();
      HeapFree(v74, 0, v73);
      v109 = 0;
    }
    OSRollbackUtils::CBCDManipulator::~CBCDManipulator((OSRollbackUtils::CBCDManipulator *)v116);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v114);
    if ( (unsigned int)++v37 >= 2 )
      goto LABEL_61;
  }
  v87 = GetLastError();
  v88 = CurrentIP();
  v89 = ConstructPartialMsgW(
          0x2000000u,
          "pExtractWinREFromImage: Failed to copy new device element path. Error = 0x%08X",
          v61);
  WdsSetupLogMessageW(
    v89,
    819200,
    L"D",
    0,
    1367,
    L"base\\ntsetup\\setupplatform\\lib\\project\\deploymentproject.cpp",
    L"pExtractWinREFromImage",
    v88,
    v87,
    0,
    0);
  v106 = &RAII::CAutoWdsLibFree<_BCDE_DEVICE *>::`vftable';
  v90 = lpMem;
  if ( lpMem )
  {
    v91 = GetProcessHeap();
    HeapFree(v91, 0, v90);
    lpMem = 0;
  }
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v115);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v117);
  v108 = &RAII::CAutoWdsLibFree<_BCDE_DEVICE *>::`vftable';
  v92 = v109;
  if ( v109 )
  {
    v93 = GetProcessHeap();
    HeapFree(v93, 0, v92);
    v109 = 0;
  }
  OSRollbackUtils::CBCDManipulator::~CBCDManipulator((OSRollbackUtils::CBCDManipulator *)v116);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v114);
LABEL_61:
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v113);
  v110 = &RAII::CAutoWimClose::`vftable';
  if ( v111 )
    WIMCloseHandle(v111);
  return (unsigned int)v61;
}

```

## disassembly

```asm
0x1802882b8  mov     rax, rsp
0x1802882bb  push    rbp
0x1802882bc  push    rbx
0x1802882bd  push    rsi
0x1802882be  push    rdi
0x1802882bf  push    r12
0x1802882c1  push    r13
0x1802882c3  push    r14
0x1802882c5  push    r15
0x1802882c7  lea     rbp, [rax-0E8h]
0x1802882ce  sub     rsp, 1A8h
0x1802882d5  mov     [rbp+0E0h+var_E0], 0FFFFFFFFFFFFFFFEh
0x1802882dd  movaps  xmmword ptr [rax-58h], xmm6
0x1802882e1  mov     rax, cs:__security_cookie
0x1802882e8  xor     rax, rsp
0x1802882eb  mov     [rbp+0E0h+var_60], rax
0x1802882f2  mov     r14, r9
0x1802882f5  mov     r12, r8
0x1802882f8  mov     edi, edx
0x1802882fa  mov     r15, rcx
0x1802882fd  xor     r13d, r13d
0x180288300  mov     [rsp+1E0h+var_1B8], r13
0x180288305  mov     dword ptr [rsp+1E0h+var_1C0], r13d
0x18028830a  xor     r9d, r9d
0x18028830d  mov     edx, 80000000h
0x180288312  lea     r8d, [r13+3]
0x180288316  call    cs:__imp_WIMCreateFile
0x18028831c  mov     [rbp+0E0h+var_158], rax
0x180288320  lea     rax, ??_7CAutoWimClose@RAII@@6B@; const RAII::CAutoWimClose::`vftable'
0x180288327  mov     [rbp+0E0h+var_160], rax
0x18028832b  lea     rcx, [rbp+0E0h+var_160]
0x18028832f  call    ??7?$CAutoCleanupBase@PEAUISetupOneSettings@@@RAII@@UEBA_NXZ; RAII::CAutoCleanupBase<ISetupOneSettings *>::operator!(void)
0x180288334  test    al, al
0x180288336  jz      loc_1802883E4
0x18028833c  call    cs:__imp_GetLastError
0x180288342  mov     ebx, 80070000h
0x180288347  test    eax, eax
0x180288349  jle     short loc_180288352
0x18028834b  movzx   eax, ax
0x18028834e  or      eax, ebx
0x180288350  test    eax, eax
0x180288352  jns     short loc_180288367
0x180288354  call    cs:__imp_GetLastError
0x18028835a  mov     esi, eax
0x18028835c  test    eax, eax
0x18028835e  jle     short loc_18028836C
0x180288360  movzx   esi, ax
0x180288363  or      esi, ebx
0x180288365  jmp     short loc_18028836C
0x180288367  mov     esi, 80004005h
0x18028836c  call    cs:__imp_GetLastError
0x180288372  mov     edi, eax
0x180288374  call    cs:__imp_CurrentIP
0x18028837a  mov     rbx, rax
0x18028837d  mov     r9d, esi
0x180288380  mov     r8, r15
0x180288383  lea     rdx, aPextractwinref_4; "pExtractWinREFromImage: Failed to open "...
0x18028838a  mov     ecx, 2000000h; unsigned int
0x18028838f  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180288394  mov     [rsp+50h], r13d
0x180288399  mov     qword ptr [rsp+1E0h+var_198], r13
0x18028839e  mov     dword ptr [rsp+1E0h+var_1A0], edi
0x1802883a2  mov     qword ptr [rsp+1E0h+var_1A8], rbx
0x1802883a7  lea     rcx, aPextractwinref_2; "pExtractWinREFromImage"
0x1802883ae  mov     [rsp+1E0h+var_1B0], rcx
0x1802883b3  lea     rcx, aBaseNtsetupSet_43; "base\\ntsetup\\setupplatform\\lib\\proj"...
0x1802883ba  mov     [rsp+1E0h+var_1B8], rcx
0x1802883bf  mov     dword ptr [rsp+1E0h+var_1C0], 502h
0x1802883c7  xor     r9d, r9d
0x1802883ca  lea     r8, aD_0; "D"
0x1802883d1  mov     edx, 0C8000h
0x1802883d6  mov     rcx, rax
0x1802883d9  call    cs:__imp_WdsSetupLogMessageW
0x1802883df  jmp     loc_180288EEC
0x1802883e4  mov     rax, [rbp+0E0h+var_160]
0x1802883e8  lea     rcx, [rbp+0E0h+var_160]
0x1802883ec  mov     rax, [rax+20h]
0x1802883f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802883f5  mov     rcx, rax
0x1802883f8  mov     rdx, r14
0x1802883fb  call    cs:__imp_WIMSetTemporaryPath
0x180288401  test    eax, eax
0x180288403  jnz     loc_180288499
0x180288409  call    cs:__imp_GetLastError
0x18028840f  mov     ebx, 80070000h
0x180288414  test    eax, eax
0x180288416  jle     short loc_18028841F
0x180288418  movzx   eax, ax
0x18028841b  or      eax, ebx
0x18028841d  test    eax, eax
0x18028841f  jns     short loc_180288434
0x180288421  call    cs:__imp_GetLastError
0x180288427  mov     esi, eax
0x180288429  test    eax, eax
0x18028842b  jle     short loc_180288439
0x18028842d  movzx   esi, ax
0x180288430  or      esi, ebx
0x180288432  jmp     short loc_180288439
0x180288434  mov     esi, 80004005h
0x180288439  call    cs:__imp_GetLastError
0x18028843f  mov     edi, eax
0x180288441  call    cs:__imp_CurrentIP
0x180288447  mov     rbx, rax
0x18028844a  mov     r9d, esi
0x18028844d  mov     r8, r14
0x180288450  lea     rdx, aPextractwinref_5; "pExtractWinREFromImage: Failed to set W"...
0x180288457  mov     ecx, 2000000h; unsigned int
0x18028845c  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180288461  mov     [rsp+50h], r13d
0x180288466  mov     qword ptr [rsp+1E0h+var_198], r13
0x18028846b  mov     dword ptr [rsp+1E0h+var_1A0], edi
0x18028846f  mov     qword ptr [rsp+1E0h+var_1A8], rbx
0x180288474  lea     rcx, aPextractwinref_2; "pExtractWinREFromImage"
0x18028847b  mov     [rsp+1E0h+var_1B0], rcx
0x180288480  lea     rcx, aBaseNtsetupSet_43; "base\\ntsetup\\setupplatform\\lib\\proj"...
0x180288487  mov     [rsp+1E0h+var_1B8], rcx
0x18028848c  mov     dword ptr [rsp+1E0h+var_1C0], 509h
0x180288494  jmp     loc_1802883C7
0x180288499  lea     rdx, aSources_0; "sources"
0x1802884a0  lea     rcx, [rbp+0E0h+var_B8]
0x1802884a4  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x1802884aa  mov     rbx, rax
0x1802884ad  mov     rdx, r12
0x1802884b0  lea     rcx, [rbp+0E0h+var_D0]
0x1802884b4  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x1802884ba  nop
0x1802884bb  mov     rdx, rbx
0x1802884be  mov     rcx, rax
0x1802884c1  call    cs:__imp_?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x1802884c7  mov     rdx, rax
0x1802884ca  lea     rcx, [rbp+0E0h+var_148]
0x1802884ce  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1802884d4  nop
0x1802884d5  lea     rcx, [rbp+0E0h+var_D0]
0x1802884d9  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x1802884df  nop
0x1802884e0  lea     rcx, [rbp+0E0h+var_B8]
0x1802884e4  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x1802884ea  lea     rdx, aWinreWim; "winre.wim"
0x1802884f1  lea     rcx, [rbp+0E0h+var_F8]
0x1802884f5  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x1802884fb  mov     rbx, rax
0x1802884fe  lea     rcx, [rbp+0E0h+var_148]
0x180288502  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x180288508  mov     rdx, rbx
0x18028850b  mov     rcx, rax
0x18028850e  call    cs:__imp_?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x180288514  mov     rdx, rax
0x180288517  lea     rcx, [rbp+0E0h+var_70]
0x18028851b  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180288521  nop
0x180288522  lea     rdx, [rbp+0E0h+var_70]
0x180288526  lea     rcx, [rbp+0E0h+var_148]
0x18028852a  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x180288530  nop
0x180288531  lea     rcx, [rbp+0E0h+var_70]
0x180288535  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x18028853b  nop
0x18028853c  lea     rcx, [rbp+0E0h+var_F8]
0x180288540  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x180288546  lea     rcx, [rbp+0E0h+var_148]
0x18028854a  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180288550  mov     rcx, rax
0x180288553  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180288559  mov     rbx, rax
0x18028855c  mov     rcx, [rbp+0E0h+var_160]
0x180288560  mov     rax, [rcx+20h]
0x180288564  lea     rcx, [rbp+0E0h+var_160]
0x180288568  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18028856d  mov     dword ptr [rsp+1E0h+var_1C0], r13d
0x180288572  mov     r9, rbx
0x180288575  lea     r8, aWindowsSystem3_6; "\\Windows\\System32\\Recovery\\winre.wi"...
0x18028857c  mov     edx, edi
0x18028857e  mov     rcx, rax
0x180288581  call    cs:__imp_WIMExtractImagePathByWimHandle
0x180288587  test    eax, eax
0x180288589  jnz     loc_180288634
0x18028858f  call    cs:__imp_GetLastError
0x180288595  mov     ebx, 80070000h
0x18028859a  test    eax, eax
0x18028859c  jle     short loc_1802885A5
0x18028859e  movzx   eax, ax
0x1802885a1  or      eax, ebx
0x1802885a3  test    eax, eax
0x1802885a5  jns     short loc_1802885BA
0x1802885a7  call    cs:__imp_GetLastError
0x1802885ad  mov     esi, eax
0x1802885af  test    eax, eax
0x1802885b1  jle     short loc_1802885BF
0x1802885b3  movzx   esi, ax
0x1802885b6  or      esi, ebx
0x1802885b8  jmp     short loc_1802885BF
0x1802885ba  mov     esi, 80004005h
0x1802885bf  call    cs:__imp_GetLastError
0x1802885c5  mov     edi, eax
0x1802885c7  call    cs:__imp_CurrentIP
0x1802885cd  mov     rbx, rax
0x1802885d0  mov     r8d, esi
0x1802885d3  lea     rdx, aPextractwinref_8; "pExtractWinREFromImage: Failed to extra"...
0x1802885da  mov     ecx, 2000000h; unsigned int
0x1802885df  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1802885e4  mov     [rsp+50h], r13d
0x1802885e9  mov     qword ptr [rsp+1E0h+var_198], r13
0x1802885ee  mov     dword ptr [rsp+1E0h+var_1A0], edi
0x1802885f2  mov     qword ptr [rsp+1E0h+var_1A8], rbx
0x1802885f7  lea     rcx, aPextractwinref_2; "pExtractWinREFromImage"
0x1802885fe  mov     [rsp+1E0h+var_1B0], rcx
0x180288603  lea     rcx, aBaseNtsetupSet_43; "base\\ntsetup\\setupplatform\\lib\\proj"...
0x18028860a  mov     [rsp+1E0h+var_1B8], rcx
0x18028860f  mov     dword ptr [rsp+1E0h+var_1C0], 513h
0x180288617  xor     r9d, r9d
0x18028861a  lea     r8, aD_0; "D"
0x180288621  mov     edx, 0C8000h
0x180288626  mov     rcx, rax
0x180288629  call    cs:__imp_WdsSetupLogMessageW
0x18028862f  jmp     loc_180288EE1
0x180288634  mov     rcx, [rbp+0E0h+var_158]
0x180288638  test    rcx, rcx
0x18028863b  jz      short loc_180288647
0x18028863d  call    cs:__imp_WIMCloseHandle
0x180288643  mov     [rbp+0E0h+var_158], r13
0x180288647  mov     r14d, r13d
0x18028864a  lea     rdi, ??_7?$CAutoWdsLibFree@PEAU_BCDE_DEVICE@@@RAII@@6B@; const RAII::CAutoWdsLibFree<_BCDE_DEVICE *>::`vftable'
0x180288651  movsxd  rdx, r14d
0x180288654  lea     rax, off_180548500; "\\Boot\\BCD"
0x18028865b  mov     rdx, [rax+rdx*8]
0x18028865f  lea     rcx, [rbp+0E0h+var_88]
0x180288663  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180288669  mov     rbx, rax
0x18028866c  mov     rdx, r12
0x18028866f  lea     rcx, [rbp+0E0h+var_A0]
0x180288673  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180288679  nop
0x18028867a  mov     rdx, rbx
0x18028867d  mov     rcx, rax
0x180288680  call    cs:__imp_?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x180288686  mov     rdx, rax
0x180288689  lea     rcx, [rbp+0E0h+var_138]
0x18028868d  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180288693  nop
0x180288694  lea     rcx, [rbp+0E0h+var_A0]
0x180288698  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18028869e  nop
0x18028869f  lea     rcx, [rbp+0E0h+var_88]
0x1802886a3  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x1802886a9  lea     rcx, [rbp+0E0h+var_118]; this
0x1802886ad  call    ??0CBCDManipulator@OSRollbackUtils@@QEAA@XZ; OSRollbackUtils::CBCDManipulator::CBCDManipulator(void)
0x1802886b2  nop
0x1802886b3  lea     rcx, [rbp+0E0h+var_138]
0x1802886b7  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x1802886bd  mov     rcx, rax
0x1802886c0  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1802886c6  mov     rdx, rax; unsigned __int16 *
0x1802886c9  lea     rcx, [rbp+0E0h+var_118]; this
0x1802886cd  call    ?Open@CBCDManipulator@OSRollbackUtils@@QEAAKPEBG@Z; OSRollbackUtils::CBCDManipulator::Open(ushort const *)
0x1802886d2  mov     esi, eax
0x1802886d4  test    eax, eax
0x1802886d6  jnz     loc_180288E3A
0x1802886dc  xorps   xmm0, xmm0
0x1802886df  movups  xmmword ptr [rbp+0E0h+var_70.Data1], xmm0
0x1802886e3  lea     rdx, [rbp+0E0h+var_70]; struct _GUID *
0x1802886e7  lea     rcx, [rbp+0E0h+var_118]; this
0x1802886eb  call    ?GetDefaultBootEntry@CBCDManipulator@OSRollbackUtils@@QEAAKAEAU_GUID@@@Z; OSRollbackUtils::CBCDManipulator::GetDefaultBootEntry(_GUID &)
0x1802886f0  mov     esi, eax
0x1802886f2  test    eax, eax
0x1802886f4  jnz     loc_180288DD5
0x1802886fa  mov     [rsp+1E0h+var_168], r13
0x1802886ff  mov     [rsp+1E0h+var_170], rdi
0x180288704  mov     [rbp+0E0h+var_150], r13d
0x180288708  lea     rcx, [rsp+1E0h+var_170]
0x18028870d  call    ??I?$CAutoCleanupBase@PEAVVdsVolumePathEnumerator@@@RAII@@UEBAPEBQEAVVdsVolumePathEnumerator@@XZ; RAII::CAutoCleanupBase<VdsVolumePathEnumerator *>::operator&(void)
0x180288712  mov     r9, rax; void **
0x180288715  lea     rax, [rbp+0E0h+var_150]
0x180288719  mov     [rsp+1E0h+var_1C0], rax; unsigned int *
0x18028871e  mov     r8d, 11000001h; unsigned int
0x180288724  lea     rdx, [rbp+0E0h+var_70]; struct _GUID *
0x180288728  lea     rcx, [rbp+0E0h+var_118]; this
0x18028872c  call    ?GetDeviceElementData@CBCDManipulator@OSRollbackUtils@@QEAAKAEBU_GUID@@KPEAPEAXPEAK@Z; OSRollbackUtils::CBCDManipulator::GetDeviceElementData(_GUID const &,ulong,void * *,ulong *)
0x180288731  mov     esi, eax
0x180288733  test    eax, eax
0x180288735  jnz     loc_180288D4D
0x18028873b  lea     ecx, [rax+18h]
0x18028873e  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180288744  mov     rbx, rax
0x180288747  mov     [rbp+0E0h+var_D8], rax
0x18028874b  test    rax, rax
0x18028874e  jz      short loc_18028877C
0x180288750  mov     rax, [rsp+1E0h+var_170]
0x180288755  lea     rcx, [rsp+1E0h+var_170]
0x18028875a  mov     rax, [rax+18h]
0x18028875e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180288763  lea     rdx, [rax+18h]
0x180288767  mov     rcx, rbx
0x18028876a  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180288770  lea     rax, ??_SString@UnBCL@@6B@; const UnBCL::String::`local vftable'
0x180288777  mov     [rbx], rax
0x18028877a  jmp     short loc_18028877F
0x18028877c  mov     rbx, r13
0x18028877f  mov     rdx, rbx
0x180288782  lea     rcx, [rbp+0E0h+var_F8]
  ... truncated ...
```
