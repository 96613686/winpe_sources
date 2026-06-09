# VdsDisk::CreatePartition(SetupPlatform::PARTITION_TYPE,SetupPlatform::PARTITION_USAGE,uchar,ushort const *,ushort const *,ushort const *,unsigned __int64,unsigned __int64,unsigned __int64,int,int,int,SetupPlatform::IPartition * *)

- ea: `0x18039cc04`
- end: `0x18039e526`
- name: `?CreatePartition@VdsDisk@@IEAAJW4PARTITION_TYPE@SetupPlatform@@W4PARTITION_USAGE@3@EPEBG22_K33HHHPEAPEAUIPartition@3@@Z`
- size: `6434`
- prototype: ``
- caller_count: `3`
- callee_count: `14`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18039e530`
- `0x18039e5b0`
- `0x18039e640`

## callees

- `0x1800447a0`
- `0x180044820`
- `0x180057dec`
- `0x18009a39c`
- `0x1802dacac`
- `0x18038e7c0`
- `0x18039cc04`
- `0x1803b0670`
- `0x180409628`
- `0x18040a2ac`
- `0x1804bbf56`
- `0x1804bbf62`
- `0x1804bbfa0`
- `0x180509010`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18039d8c2`
- `KERNEL32!GetProcessHeap` at `0x18039da23`
- `KERNEL32!GetProcessHeap` at `0x18039db3b`
- `KERNEL32!GetProcessHeap` at `0x18039dcac`
- `KERNEL32!GetProcessHeap` at `0x18039dde0`
- `KERNEL32!GetProcessHeap` at `0x18039de6a`
- `KERNEL32!GetProcessHeap` at `0x18039dff4`
- `KERNEL32!GetProcessHeap` at `0x18039d8c2`
- `KERNEL32!GetProcessHeap` at `0x18039da23`
- `KERNEL32!GetProcessHeap` at `0x18039db3b`
- `KERNEL32!GetProcessHeap` at `0x18039dcac`
- `KERNEL32!GetProcessHeap` at `0x18039dde0`
- `KERNEL32!GetProcessHeap` at `0x18039de6a`
- `KERNEL32!GetProcessHeap` at `0x18039dff4`
- `KERNEL32!HeapFree` at `0x18039d8d0`
- `KERNEL32!HeapFree` at `0x18039da31`
- `KERNEL32!HeapFree` at `0x18039db49`
- `KERNEL32!HeapFree` at `0x18039dcba`
- `KERNEL32!HeapFree` at `0x18039ddee`
- `KERNEL32!HeapFree` at `0x18039de78`
- `KERNEL32!HeapFree` at `0x18039e002`
- `KERNEL32!HeapFree` at `0x18039d8d0`
- `KERNEL32!HeapFree` at `0x18039da31`
- `KERNEL32!HeapFree` at `0x18039db49`
- `KERNEL32!HeapFree` at `0x18039dcba`
- `KERNEL32!HeapFree` at `0x18039ddee`
- `KERNEL32!HeapFree` at `0x18039de78`
- `KERNEL32!HeapFree` at `0x18039e002`
- `KERNEL32!GetLastError` at `0x18039cca7`
- `KERNEL32!GetLastError` at `0x18039cd4e`
- `KERNEL32!GetLastError` at `0x18039ce09`
- `KERNEL32!GetLastError` at `0x18039ce7f`
- `KERNEL32!GetLastError` at `0x18039cefe`
- `KERNEL32!GetLastError` at `0x18039cfb2`
- `KERNEL32!GetLastError` at `0x18039d08a`
- `KERNEL32!GetLastError` at `0x18039d15a`
- `KERNEL32!GetLastError` at `0x18039d1fb`
- `KERNEL32!GetLastError` at `0x18039d29c`
- `KERNEL32!GetLastError` at `0x18039d372`
- `KERNEL32!GetLastError` at `0x18039d436`
- `KERNEL32!GetLastError` at `0x18039d4a6`
- `KERNEL32!GetLastError` at `0x18039d521`
- `KERNEL32!GetLastError` at `0x18039d5ed`
- `KERNEL32!GetLastError` at `0x18039d6bf`
- `KERNEL32!GetLastError` at `0x18039d80f`
- `KERNEL32!GetLastError` at `0x18039d87c`
- `KERNEL32!GetLastError` at `0x18039d894`
- `KERNEL32!GetLastError` at `0x18039d99c`
- `KERNEL32!GetLastError` at `0x18039dab7`
- `KERNEL32!GetLastError` at `0x18039dbd6`
- `KERNEL32!GetLastError` at `0x18039dc43`
- `KERNEL32!GetLastError` at `0x18039dc5b`
- `KERNEL32!GetLastError` at `0x18039dd36`
- `KERNEL32!GetLastError` at `0x18039deb5`
- `KERNEL32!GetLastError` at `0x18039df73`
- `KERNEL32!GetLastError` at `0x18039e14c`
- `KERNEL32!GetLastError` at `0x18039e251`
- `KERNEL32!GetLastError` at `0x18039e38f`
- `KERNEL32!GetLastError` at `0x18039cca7`
- `KERNEL32!GetLastError` at `0x18039cd4e`
- `KERNEL32!GetLastError` at `0x18039ce09`
- `KERNEL32!GetLastError` at `0x18039ce7f`
- `KERNEL32!GetLastError` at `0x18039cefe`
- `KERNEL32!GetLastError` at `0x18039cfb2`
- `KERNEL32!GetLastError` at `0x18039d08a`
- `KERNEL32!GetLastError` at `0x18039d15a`
- `KERNEL32!GetLastError` at `0x18039d1fb`
- `KERNEL32!GetLastError` at `0x18039d29c`
- `KERNEL32!GetLastError` at `0x18039d372`
- `KERNEL32!GetLastError` at `0x18039d436`
- `KERNEL32!GetLastError` at `0x18039d4a6`
- `KERNEL32!GetLastError` at `0x18039d521`
- `KERNEL32!GetLastError` at `0x18039d5ed`
- `KERNEL32!GetLastError` at `0x18039d6bf`
- `KERNEL32!GetLastError` at `0x18039d80f`
- `KERNEL32!GetLastError` at `0x18039d87c`
- `KERNEL32!GetLastError` at `0x18039d894`
- `KERNEL32!GetLastError` at `0x18039d99c`
- `KERNEL32!GetLastError` at `0x18039dab7`
- `KERNEL32!GetLastError` at `0x18039dbd6`
- `KERNEL32!GetLastError` at `0x18039dc43`
- `KERNEL32!GetLastError` at `0x18039dc5b`
- `KERNEL32!GetLastError` at `0x18039dd36`
- `KERNEL32!GetLastError` at `0x18039deb5`
- `KERNEL32!GetLastError` at `0x18039df73`
- `KERNEL32!GetLastError` at `0x18039e14c`
- `KERNEL32!GetLastError` at `0x18039e251`
- `KERNEL32!GetLastError` at `0x18039e38f`
- `KERNEL32!CloseHandle` at `0x18039dc8c`
- `KERNEL32!CloseHandle` at `0x18039ddc0`
- `KERNEL32!CloseHandle` at `0x18039de4a`
- `KERNEL32!CloseHandle` at `0x18039dc8c`
- `KERNEL32!CloseHandle` at `0x18039ddc0`
- `KERNEL32!CloseHandle` at `0x18039de4a`
- `KERNEL32!CreateFileW` at `0x18039dbae`
- `KERNEL32!CreateFileW` at `0x18039dbae`
- `ole32!CoCreateGuid` at `0x18039d49a`
- `ole32!CoCreateGuid` at `0x18039d49a`
- `WDSCORE!WdsSetupLogMessageW` at `0x18039cd0e`
- `WDSCORE!WdsSetupLogMessageW` at `0x18039cee3`
- `WDSCORE!WdsSetupLogMessageW` at `0x18039d019`
- `WDSCORE!WdsSetupLogMessageW` at `0x18039d0f4`
- `WDSCORE!WdsSetupLogMessageW` at `0x18039d65b`
- `WDSCORE!WdsSetupLogMessageW` at `0x18039d726`
- `WDSCORE!WdsSetupLogMessageW` at `0x18039d876`
- `WDSCORE!WdsSetupLogMessageW` at `0x18039da06`
- `WDSCORE!WdsSetupLogMessageW` at `0x18039db1e`
- `WDSCORE!WdsSetupLogMessageW` at `0x18039dc3d`
- `WDSCORE!WdsSetupLogMessageW` at `0x18039dda0`
- `WDSCORE!WdsSetupLogMessageW` at `0x18039df1c`
- `WDSCORE!WdsSetupLogMessageW` at `0x18039dfd7`
- `WDSCORE!WdsSetupLogMessageW` at `0x18039e1b3`
- `WDSCORE!WdsSetupLogMessageW` at `0x18039e2b8`
- `WDSCORE!WdsSetupLogMessageW` at `0x18039e3f3`
- `WDSCORE!WdsSetupLogMessageW` at `0x18039cd0e`
- `WDSCORE!WdsSetupLogMessageW` at `0x18039cee3`
- `WDSCORE!WdsSetupLogMessageW` at `0x18039d019`
- `WDSCORE!WdsSetupLogMessageW` at `0x18039d0f4`
- `WDSCORE!WdsSetupLogMessageW` at `0x18039d65b`
- `WDSCORE!WdsSetupLogMessageW` at `0x18039d726`
- `WDSCORE!WdsSetupLogMessageW` at `0x18039d876`
- `WDSCORE!WdsSetupLogMessageW` at `0x18039da06`
- `WDSCORE!WdsSetupLogMessageW` at `0x18039db1e`
- `WDSCORE!WdsSetupLogMessageW` at `0x18039dc3d`
- `WDSCORE!WdsSetupLogMessageW` at `0x18039dda0`
- `WDSCORE!WdsSetupLogMessageW` at `0x18039df1c`
- `WDSCORE!WdsSetupLogMessageW` at `0x18039dfd7`
- `WDSCORE!WdsSetupLogMessageW` at `0x18039e1b3`
- `WDSCORE!WdsSetupLogMessageW` at `0x18039e2b8`
- `WDSCORE!WdsSetupLogMessageW` at `0x18039e3f3`
- `WDSCORE!CurrentIP` at `0x18039ccaf`
- `WDSCORE!CurrentIP` at `0x18039cd56`
- `WDSCORE!CurrentIP` at `0x18039ce11`
- `WDSCORE!CurrentIP` at `0x18039ce87`
- `WDSCORE!CurrentIP` at `0x18039cf06`
- `WDSCORE!CurrentIP` at `0x18039cfba`
- `WDSCORE!CurrentIP` at `0x18039d092`
- `WDSCORE!CurrentIP` at `0x18039d162`
- `WDSCORE!CurrentIP` at `0x18039d203`
- `WDSCORE!CurrentIP` at `0x18039d2a4`
- `WDSCORE!CurrentIP` at `0x18039d37a`
- `WDSCORE!CurrentIP` at `0x18039d43e`
- `WDSCORE!CurrentIP` at `0x18039d4ae`
- `WDSCORE!CurrentIP` at `0x18039d529`
- `WDSCORE!CurrentIP` at `0x18039d5f5`
- `WDSCORE!CurrentIP` at `0x18039d6c7`
- `WDSCORE!CurrentIP` at `0x18039d817`
- `WDSCORE!CurrentIP` at `0x18039d9a4`
- `WDSCORE!CurrentIP` at `0x18039dabf`
- `WDSCORE!CurrentIP` at `0x18039dbde`
- `WDSCORE!CurrentIP` at `0x18039dd3e`
- `WDSCORE!CurrentIP` at `0x18039debd`
- `WDSCORE!CurrentIP` at `0x18039df7b`
- `WDSCORE!CurrentIP` at `0x18039e154`
- `WDSCORE!CurrentIP` at `0x18039e259`
- `WDSCORE!CurrentIP` at `0x18039e397`
- `WDSCORE!CurrentIP` at `0x18039ccaf`
- `WDSCORE!CurrentIP` at `0x18039cd56`
- `WDSCORE!CurrentIP` at `0x18039ce11`
- `WDSCORE!CurrentIP` at `0x18039ce87`
- `WDSCORE!CurrentIP` at `0x18039cf06`
- `WDSCORE!CurrentIP` at `0x18039cfba`
- `WDSCORE!CurrentIP` at `0x18039d092`
- `WDSCORE!CurrentIP` at `0x18039d162`
- `WDSCORE!CurrentIP` at `0x18039d203`
- `WDSCORE!CurrentIP` at `0x18039d2a4`
- `WDSCORE!CurrentIP` at `0x18039d37a`
- `WDSCORE!CurrentIP` at `0x18039d43e`
- `WDSCORE!CurrentIP` at `0x18039d4ae`
- `WDSCORE!CurrentIP` at `0x18039d529`
- `WDSCORE!CurrentIP` at `0x18039d5f5`
- `WDSCORE!CurrentIP` at `0x18039d6c7`
- `WDSCORE!CurrentIP` at `0x18039d817`
- `WDSCORE!CurrentIP` at `0x18039d9a4`
- `WDSCORE!CurrentIP` at `0x18039dabf`
- `WDSCORE!CurrentIP` at `0x18039dbde`
- `WDSCORE!CurrentIP` at `0x18039dd3e`
- `WDSCORE!CurrentIP` at `0x18039debd`
- `WDSCORE!CurrentIP` at `0x18039df7b`
- `WDSCORE!CurrentIP` at `0x18039e154`
- `WDSCORE!CurrentIP` at `0x18039e259`
- `WDSCORE!CurrentIP` at `0x18039e397`

## string_xrefs

- `0x18039cceb`: `base\ntsetup\setupplatform\lib\diskconfig\diskconfigvds.cpp`
- `0x18039cd92`: `base\ntsetup\setupplatform\lib\diskconfig\diskconfigvds.cpp`
- `0x18039ce54`: `base\ntsetup\setupplatform\lib\diskconfig\diskconfigvds.cpp`
- `0x18039cec0`: `base\ntsetup\setupplatform\lib\diskconfig\diskconfigvds.cpp`
- `0x18039cf3f`: `base\ntsetup\setupplatform\lib\diskconfig\diskconfigvds.cpp`
- `0x18039cff6`: `base\ntsetup\setupplatform\lib\diskconfig\diskconfigvds.cpp`
- `0x18039d0d1`: `base\ntsetup\setupplatform\lib\diskconfig\diskconfigvds.cpp`
- `0x18039d19e`: `base\ntsetup\setupplatform\lib\diskconfig\diskconfigvds.cpp`
- `0x18039d23f`: `base\ntsetup\setupplatform\lib\diskconfig\diskconfigvds.cpp`
- `0x18039d2e0`: `base\ntsetup\setupplatform\lib\diskconfig\diskconfigvds.cpp`
- `0x18039d3b6`: `base\ntsetup\setupplatform\lib\diskconfig\diskconfigvds.cpp`
- `0x18039d47d`: `base\ntsetup\setupplatform\lib\diskconfig\diskconfigvds.cpp`
- `0x18039d4ea`: `base\ntsetup\setupplatform\lib\diskconfig\diskconfigvds.cpp`
- `0x18039d568`: `base\ntsetup\setupplatform\lib\diskconfig\diskconfigvds.cpp`
- `0x18039d638`: `base\ntsetup\setupplatform\lib\diskconfig\diskconfigvds.cpp`
- `0x18039d703`: `base\ntsetup\setupplatform\lib\diskconfig\diskconfigvds.cpp`
- `0x18039d853`: `base\ntsetup\setupplatform\lib\diskconfig\diskconfigvds.cpp`
- `0x18039d9e3`: `base\ntsetup\setupplatform\lib\diskconfig\diskconfigvds.cpp`
- `0x18039dafb`: `base\ntsetup\setupplatform\lib\diskconfig\diskconfigvds.cpp`
- `0x18039dc1a`: `base\ntsetup\setupplatform\lib\diskconfig\diskconfigvds.cpp`
- `0x18039dd7d`: `base\ntsetup\setupplatform\lib\diskconfig\diskconfigvds.cpp`
- `0x18039def9`: `base\ntsetup\setupplatform\lib\diskconfig\diskconfigvds.cpp`
- `0x18039dfb4`: `base\ntsetup\setupplatform\lib\diskconfig\diskconfigvds.cpp`
- `0x18039e190`: `base\ntsetup\setupplatform\lib\diskconfig\diskconfigvds.cpp`
- `0x18039e295`: `base\ntsetup\setupplatform\lib\diskconfig\diskconfigvds.cpp`
- `0x18039e3d0`: `base\ntsetup\setupplatform\lib\diskconfig\diskconfigvds.cpp`
- `0x18039d0a1`: `VdsDisk::CreatePartition: Can't convert GUID type string %s to GUID (0x%08x)`
- `0x18039d386`: `VdsDisk::CreatePartition: Can't copy reserved partition name (0x%08x)`
- `0x18039d2b0`: `VdsDisk::CreatePartition: Can't copy LDM data partition name (0x%08x)`
- `0x18039d20f`: `VdsDisk::CreatePartition: Can't copy LDM metadata partition name (0x%08x)`
- `0x18039ccdf`: `VdsDisk::CreatePartition`
- `0x18039cd86`: `VdsDisk::CreatePartition`
- `0x18039ce48`: `VdsDisk::CreatePartition`
- `0x18039ceb4`: `VdsDisk::CreatePartition`
- `0x18039cf33`: `VdsDisk::CreatePartition`
- `0x18039cfea`: `VdsDisk::CreatePartition`
- `0x18039d0c5`: `VdsDisk::CreatePartition`
- `0x18039d192`: `VdsDisk::CreatePartition`
- `0x18039d233`: `VdsDisk::CreatePartition`
- `0x18039d2d4`: `VdsDisk::CreatePartition`
- `0x18039d3aa`: `VdsDisk::CreatePartition`
- `0x18039d471`: `VdsDisk::CreatePartition`
- `0x18039d4de`: `VdsDisk::CreatePartition`
- `0x18039d55c`: `VdsDisk::CreatePartition`
- `0x18039d62c`: `VdsDisk::CreatePartition`
- `0x18039d6f7`: `VdsDisk::CreatePartition`
- `0x18039d847`: `VdsDisk::CreatePartition`
- `0x18039d9d7`: `VdsDisk::CreatePartition`
- `0x18039daef`: `VdsDisk::CreatePartition`
- `0x18039dc0e`: `VdsDisk::CreatePartition`
- `0x18039dd71`: `VdsDisk::CreatePartition`
- `0x18039deed`: `VdsDisk::CreatePartition`
- `0x18039dfa8`: `VdsDisk::CreatePartition`
- `0x18039e184`: `VdsDisk::CreatePartition`
- `0x18039e289`: `VdsDisk::CreatePartition`
- `0x18039e3c4`: `VdsDisk::CreatePartition`
- `0x18039ccbb`: `VdsDisk::CreatePartition: Can't allocate partition (0x%08x)`
- `0x18039cd62`: `VdsDisk::CreatePartition: Failed to get disk properties (0x%08x)`
- `0x18039ce1d`: `VdsDisk::CreatePartition: Can't get disk properties (0x%08x)`
- `0x18039ce90`: `VdsDisk::CreatePartition: MBR type not supported on non-MBR disk`
- `0x18039cf0f`: `VdsDisk::CreatePartition: Partition GUID not supported on non-GPT disk`
- `0x18039d823`: `VdsDisk::CreatePartition: Failed to get drive layout info (0x%08x)`
- `0x18039df84`: `VdsDisk::CreatePartition: Can't find the partition that was just created`
- `0x18039e3a0`: `VdsDisk::CreatePartition: Can't find the partition that was just created`
- `0x18039dacb`: `VdsDisk::CreatePartition: Can't copy disk path (0x%08x)`
- `0x18039dbea`: `VdsDisk::CreatePartition: Could not get handle to disk to set partition name (0x%08x)`
- `0x18039dd4d`: `VdsDisk::CreatePartition: Failed to set partition name %s (0x%08x)`
- `0x18039dec9`: `VdsDisk::CreatePartition: Failed to create partition enumerator (0x%08x)`
- `0x18039e265`: `VdsDisk::CreatePartition: Can't enumerate partitions (0x%08x)`
- `0x18039d44d`: `VdsDisk::CreatePartition: Can't convert GUID Id string %s to GUID (0x%08x)`
- `0x18039d4ba`: `VdsDisk::CreatePartition: Can't create GPT partition GUID (0x%08x)`
- `0x18039d538`: `VdsDisk::CreatePartition: Can't copy partition name %s (0x%08x)`
- `0x18039d9b3`: `VdsDisk::CreatePartition: Can't copy partition name %s (0x%08x)`
- `0x18039d601`: `create partition`
- `0x18039d608`: `VdsDisk::CreatePartition: Failed to query IID_IVdsCreatePartitionEx interface [%s] (0x%08x)`
- `0x18039d6d3`: `VdsDisk::CreatePartition: Can't create partition (0x%08x)`
- `0x18039e160`: `VdsDisk::CreatePartition: Can't get partition properties (0x%08x)`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall VdsDisk::CreatePartition(
        __int64 a1,
        int a2,
        int a3,
        char a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6,
        unsigned __int16 *a7,
        unsigned __int64 a8,
        unsigned __int64 a9,
        unsigned int a10,
        char a11,
        int a12,
        int a13,
        _QWORD *a14)
{
  int v18; // r14d
  DWORD LastError; // edi
  __int64 v20; // rbx
  struct tagLOG_PARTIAL_MSG *v21; // rax
  DWORD v23; // edi
  __int64 v24; // rbx
  struct tagLOG_PARTIAL_MSG *v25; // rax
  unsigned __int64 v26; // rdx
  unsigned __int64 v27; // r13
  unsigned __int64 v28; // r13
  DWORD v29; // edi
  __int64 v30; // rbx
  struct tagLOG_PARTIAL_MSG *v31; // rax
  __int64 v32; // rbx
  DWORD v33; // edi
  __int64 v34; // rbx
  struct tagLOG_PARTIAL_MSG *v35; // rax
  DWORD v36; // edi
  __int64 v37; // rbx
  struct tagLOG_PARTIAL_MSG *v38; // rax
  DWORD v39; // edi
  __int64 v40; // rbx
  struct tagLOG_PARTIAL_MSG *v41; // rax
  HRESULT v42; // esi
  DWORD v43; // edi
  __int64 v44; // rbx
  struct tagLOG_PARTIAL_MSG *v45; // rax
  DWORD v46; // edi
  __int64 v47; // rbx
  struct tagLOG_PARTIAL_MSG *v48; // rax
  DWORD v49; // edi
  __int64 v50; // rbx
  struct tagLOG_PARTIAL_MSG *v51; // rax
  DWORD v52; // edi
  __int64 v53; // rbx
  struct tagLOG_PARTIAL_MSG *v54; // rax
  __int64 v55; // xmm0_8
  DWORD v56; // edi
  __int64 v57; // rbx
  struct tagLOG_PARTIAL_MSG *v58; // rax
  __int16 v59; // ax
  DWORD v60; // edi
  __int64 v61; // rbx
  struct tagLOG_PARTIAL_MSG *v62; // rax
  DWORD v63; // edi
  __int64 v64; // rbx
  struct tagLOG_PARTIAL_MSG *v65; // rax
  unsigned __int16 *v66; // r15
  DWORD v67; // edi
  __int64 v68; // rbx
  struct tagLOG_PARTIAL_MSG *v69; // rax
  __int64 v70; // rax
  void **v71; // rdi
  DWORD v72; // edi
  __int64 v73; // rbx
  struct tagLOG_PARTIAL_MSG *v74; // rax
  DWORD v75; // edi
  __int64 v76; // rbx
  struct tagLOG_PARTIAL_MSG *v77; // rax
  int v78; // r14d
  unsigned int v79; // eax
  DWORD v80; // edi
  __int64 v81; // rbx
  struct tagLOG_PARTIAL_MSG *v82; // rax
  signed int v83; // eax
  bool v84; // sf
  signed int v85; // eax
  unsigned int v86; // ebx
  void *v87; // rdi
  HANDLE v88; // rax
  unsigned int i; // ebx
  __int64 v90; // rax
  __int64 v91; // r9
  __int64 v92; // r8
  int v93; // ecx
  int v94; // ecx
  int v95; // eax
  DWORD v96; // edi
  __int64 v97; // rbx
  struct tagLOG_PARTIAL_MSG *v98; // rax
  void *v99; // rbx
  HANDLE v100; // rax
  unsigned int v101; // eax
  DWORD v102; // edi
  __int64 v103; // rbx
  struct tagLOG_PARTIAL_MSG *v104; // rax
  void *v105; // rbx
  HANDLE v106; // rax
  HANDLE FileW; // rax
  DWORD v108; // edi
  __int64 v109; // rbx
  struct tagLOG_PARTIAL_MSG *v110; // rax
  signed int v111; // eax
  bool v112; // sf
  signed int v113; // eax
  void *v114; // rdi
  HANDLE v115; // rax
  void *v116; // rbx
  HANDLE *v117; // rax
  DWORD v118; // edi
  __int64 v119; // rbx
  struct tagLOG_PARTIAL_MSG *v120; // rax
  void *v121; // rbx
  HANDLE v122; // rax
  void *v123; // rbx
  HANDLE v124; // rax
  __int64 (__fastcall *v125)(void **, __int64); // rbx
  __int64 v126; // rax
  DWORD v127; // edi
  __int64 v128; // rbx
  struct tagLOG_PARTIAL_MSG *v129; // rax
  DWORD v130; // edi
  __int64 v131; // rbx
  struct tagLOG_PARTIAL_MSG *v132; // rax
  void *v133; // rbx
  HANDLE ProcessHeap; // rax
  __int64 (__fastcall ***v135)(_QWORD, __int64); // rdi
  __int64 (__fastcall *v136)(_QWORD, __int64); // rbx
  __int64 v137; // rax
  int v138; // eax
  __int64 v139; // rax
  int v140; // ecx
  int v141; // eax
  __int64 v142; // rdx
  DWORD v143; // edi
  __int64 v144; // rbx
  struct tagLOG_PARTIAL_MSG *v145; // rax
  DWORD v146; // edi
  __int64 v147; // rbx
  struct tagLOG_PARTIAL_MSG *v148; // rax
  DWORD v149; // edi
  __int64 v150; // rbx
  struct tagLOG_PARTIAL_MSG *v151; // rax
  __int64 v152; // rax
  __int64 v153; // rcx
  _QWORD *v154; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD *v155; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 *v156; // [rsp+70h] [rbp-90h] BYREF
  LPVOID lpMem; // [rsp+78h] [rbp-88h]
  void **v158; // [rsp+80h] [rbp-80h] BYREF
  __int64 v159; // [rsp+88h] [rbp-78h]
  unsigned __int16 *v160; // [rsp+90h] [rbp-70h] BYREF
  HANDLE hObject; // [rsp+98h] [rbp-68h]
  void **v162; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v163; // [rsp+A8h] [rbp-58h]
  void **v164; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v165; // [rsp+B8h] [rbp-48h]
  DWORD nInBufferSize[2]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int64 v167; // [rsp+C8h] [rbp-38h] BYREF
  int v168; // [rsp+D0h] [rbp-30h] BYREF
  struct _GUID Buf1; // [rsp+D8h] [rbp-28h] BYREF
  GUID pguid; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v171; // [rsp+F8h] [rbp-8h]
  unsigned __int16 v172[40]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v173; // [rsp+150h] [rbp+50h] BYREF
  _QWORD *v174; // [rsp+158h] [rbp+58h]
  __int64 v175; // [rsp+160h] [rbp+60h]
  _OWORD v176[2]; // [rsp+168h] [rbp+68h] BYREF
  _BYTE v177[48]; // [rsp+190h] [rbp+90h] BYREF
  unsigned int v178; // [rsp+1C0h] [rbp+C0h]
  WCHAR FileName[264]; // [rsp+210h] [rbp+110h] BYREF

  v175 = -2;
  v158 = (void **)a1;
  v156 = a6;
  v160 = a7;
  v174 = a14;
  v167 = 0;
  *(_QWORD *)nInBufferSize = 0;
  v18 = SPAllocateRange(a8, a9, (struct SetupPlatform::IDisk *)a1, &v167, (unsigned __int64 *)nInBufferSize);
  if ( v18 < 0 )
  {
    LastError = GetLastError();
    v20 = CurrentIP();
    v21 = ConstructPartialMsgW(0x2000000u, "VdsDisk::CreatePartition: Can't allocate partition (0x%08x)", v18);
    WdsSetupLogMessageW(
      v21,
      0,
      L"D",
      0,
      2880,
      L"base\\ntsetup\\setupplatform\\lib\\diskconfig\\diskconfigvds.cpp",
      L"VdsDisk::CreatePartition",
      v20,
      LastError,
      0,
      0);
    return (unsigned int)v18;
  }
  memset_0(v177, 0, 0x80u);
  v18 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)(a1 + 24) + 24LL))(*(_QWORD *)(a1 + 24), v177);
  if ( v18 < 0 )
  {
    v23 = GetLastError();
    v24 = CurrentIP();
    v25 = ConstructPartialMsgW(0x2000000u, "VdsDisk::CreatePartition: Failed to get disk properties (0x%08x)", v18);
    WdsSetupLogMessageW(
      v25,
      0,
      L"D",
      0,
      2889,
      L"base\\ntsetup\\setupplatform\\lib\\diskconfig\\diskconfigvds.cpp",
      L"VdsDisk::CreatePartition",
      v24,
      v23,
      0,
      0);
    return (unsigned int)v18;
  }
  v26 = v167 % v178;
  v27 = *(_QWORD *)nInBufferSize;
  if ( v26 )
  {
    v167 += v178 - v26;
    v27 = v26 - v178 + *(_QWORD *)nInBufferSize;
  }
  v28 = v27 - v27 % v178;
  v173 = 0;
  v18 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a1 + 16LL))(a1, &v173);
  if ( v18 < 0 )
  {
    v29 = GetLastError();
    v30 = CurrentIP();
    v31 = ConstructPartialMsgW(0x2000000u, "VdsDisk::CreatePartition: Can't get disk properties (0x%08x)", v18);
    WdsSetupLogMessageW(
      v31,
      0,
      L"D",
      0,
      2907,
      L"base\\ntsetup\\setupplatform\\lib\\diskconfig\\diskconfigvds.cpp",
      L"VdsDisk::CreatePartition",
      v30,
      v29,
      0,
      0);
    return (unsigned int)v18;
  }
  v32 = v173;
  if ( a4 && *(_DWORD *)(v173 + 68) != 1 )
  {
    v33 = GetLastError();
    v34 = CurrentIP();
    v35 = ConstructPartialMsgW(0x2000000u, "VdsDisk::CreatePartition: MBR type not supported on non-MBR disk");
    WdsSetupLogMessageW(
      v35,
      0,
      L"D",
      0,
      2915,
      L"base\\ntsetup\\setupplatform\\lib\\diskconfig\\diskconfigvds.cpp",
      L"VdsDisk::CreatePartition",
      v34,
      v33,
      0,
      0);
    return 2147942450LL;
  }
  if ( a5 && *(_DWORD *)(v173 + 68) != 2 )
  {
    v36 = GetLastError();
    v37 = CurrentIP();
    v38 = ConstructPartialMsgW(0x2000000u, "VdsDisk::CreatePartition: Partition GUID not supported on non-GPT disk");
    WdsSetupLogMessageW(
      v38,
      0,
      L"D",
      0,
      2923,
      L"base\\ntsetup\\setupplatform\\lib\\diskconfig\\diskconfigvds.cpp",
      L"VdsDisk::CreatePartition",
      v37,
      v36,
      0,
      0);
    return 2147942450LL;
  }
  memset_0(&v168, 0, 0x78u);
  if ( *(_DWORD *)(v32 + 68) == 1 )
  {
    v168 = 1;
    BYTE1(Buf1.Data1) = a11;
    if ( a4 )
    {
      LOBYTE(Buf1.Data1) = a4;
    }
    else if ( a2 )
    {
      switch ( a2 )
      {
        case 1:
          LOBYTE(Buf1.Data1) = 5;
          break;
        case 2:
          LOBYTE(Buf1.Data1) = 6;
          break;
        case 3:
          LOBYTE(Buf1.Data1) = 39;
          break;
        default:
          v39 = GetLastError();
          v40 = CurrentIP();
          v41 = ConstructPartialMsgW(0x2000000u, "Unknown partition type %d", a2);
          WdsSetupLogMessageW(
            v41,
            0,
            L"D",
            0,
            2970,
            L"base\\ntsetup\\setupplatform\\lib\\diskconfig\\diskconfigvds.cpp",
            L"VdsDisk::CreatePartition",
            v40,
            v39,
            0,
            0);
          return 2147942487LL;
      }
    }
    else
    {
      LOBYTE(Buf1.Data1) = 6;
      if ( a3 == 1 )
        LOBYTE(Buf1.Data1) = 11;
    }
  }
  if ( *(_DWORD *)(v32 + 68) != 2 )
  {
    v66 = v160;
    goto LABEL_69;
  }
  v168 = 2;
  v171 = 0x8000000000000000uLL;
  if ( a5 )
  {
    v42 = SPGuidFromString(a5, &Buf1);
    if ( v42 < 0 )
    {
      v43 = GetLastError();
      v44 = CurrentIP();
      v45 = ConstructPartialMsgW(
              0x2000000u,
              "VdsDisk::CreatePartition: Can't convert GUID type string %s to GUID (0x%08x)",
              (const char *)a5,
              v42);
      WdsSetupLogMessageW(
        v45,
        0,
        L"D",
        0,
        2986,
        L"base\\ntsetup\\setupplatform\\lib\\diskconfig\\diskconfigvds.cpp",
        L"VdsDisk::CreatePartition",
        v44,
        v43,
        0,
        0);
      return (unsigned int)v42;
    }
    if ( !memcmp_0(&Buf1, &PARTITION_MSFT_RECOVERY_GUID, 0x10u) )
      v171 |= 1uLL;
    goto LABEL_56;
  }
  switch ( a3 )
  {
    case 0:
      LOWORD(Buf1.Data1) = -24414;
      v55 = *(_QWORD *)((char *)&PARTITION_BASIC_DATA_GUID.Data1 + 2);
      *(_DWORD *)&Buf1.Data4[2] = *(_DWORD *)&PARTITION_BASIC_DATA_GUID.Data4[2];
      v59 = *(_WORD *)&PARTITION_BASIC_DATA_GUID.Data4[6];
      goto LABEL_54;
    case 1:
      LOWORD(Buf1.Data1) = 29480;
      v55 = *(_QWORD *)((char *)&PARTITION_SYSTEM_GUID.Data1 + 2);
      *(_DWORD *)&Buf1.Data4[2] = *(_DWORD *)&PARTITION_SYSTEM_GUID.Data4[2];
      v59 = *(_WORD *)&PARTITION_SYSTEM_GUID.Data4[6];
LABEL_54:
      *(_WORD *)&Buf1.Data4[6] = v59;
      goto LABEL_55;
    case 2:
      LOWORD(Buf1.Data1) = -7402;
      *(_QWORD *)((char *)&Buf1.Data1 + 2) = *(_QWORD *)((char *)&PARTITION_MSFT_RESERVED_GUID.Data1 + 2);
      *(_DWORD *)&Buf1.Data4[2] = *(_DWORD *)&PARTITION_MSFT_RESERVED_GUID.Data4[2];
      *(_WORD *)&Buf1.Data4[6] = *(_WORD *)&PARTITION_MSFT_RESERVED_GUID.Data4[6];
      v42 = StringCchPrintfW(v172, 0x24u, L"Microsoft reserved partition");
      if ( v42 < 0 )
      {
        v56 = GetLastError();
        v57 = CurrentIP();
        v58 = ConstructPartialMsgW(
                0x2000000u,
                "VdsDisk::CreatePartition: Can't copy reserved partition name (0x%08x)",
                v42);
        WdsSetupLogMessageW(
          v58,
          0,
          L"D",
          0,
          3011,
          L"base\\ntsetup\\setupplatform\\lib\\diskconfig\\diskconfigvds.cpp",
          L"VdsDisk::CreatePartition",
          v57,
          v56,
          0,
          0);
        return (unsigned int)v42;
      }
      break;
    case 3:
      LOWORD(Buf1.Data1) = -17500;
      v55 = *(_QWORD *)((char *)&PARTITION_MSFT_RECOVERY_GUID.Data1 + 2);
      *(_DWORD *)&Buf1.Data4[2] = *(_DWORD *)&PARTITION_MSFT_RECOVERY_GUID.Data4[2];
      *(_WORD *)&Buf1.Data4[6] = *(_WORD *)&PARTITION_MSFT_RECOVERY_GUID.Data4[6];
      v171 = 0x8000000000000001uLL;
LABEL_55:
      *(_QWORD *)((char *)&Buf1.Data1 + 2) = v55;
      break;
    case 4:
      LOWORD(Buf1.Data1) = 24736;
      *(_QWORD *)((char *)&Buf1.Data1 + 2) = *(_QWORD *)((char *)&PARTITION_LDM_DATA_GUID.Data1 + 2);
      *(_DWORD *)&Buf1.Data4[2] = *(_DWORD *)&PARTITION_LDM_DATA_GUID.Data4[2];
      *(_WORD *)&Buf1.Data4[6] = *(_WORD *)&PARTITION_LDM_DATA_GUID.Data4[6];
      v42 = StringCchPrintfW(v172, 0x24u, L"LDM data partition");
      if ( v42 < 0 )
      {
        v52 = GetLastError();
        v53 = CurrentIP();
        v54 = ConstructPartialMsgW(
                0x2000000u,
                "VdsDisk::CreatePartition: Can't copy LDM data partition name (0x%08x)",
                v42);
        WdsSetupLogMessageW(
          v54,
          0,
          L"D",
          0,
          3026,
          L"base\\ntsetup\\setupplatform\\lib\\diskconfig\\diskconfigvds.cpp",
          L"VdsDisk::CreatePartition",
          v53,
          v52,
          0,
          0);
        return (unsigned int)v42;
      }
      break;
    case 5:
      LOWORD(Buf1.Data1) = -14166;
      *(_QWORD *)((char *)&Buf1.Data1 + 2) = *(_QWORD *)((char *)&PARTITION_LDM_METADATA_GUID.Data1 + 2);
      *(_DWORD *)&Buf1.Data4[2] = *(_DWORD *)&PARTITION_LDM_METADATA_GUID.Data4[2];
      *(_WORD *)&Buf1.Data4[6] = *(_WORD *)&PARTITION_LDM_METADATA_GUID.Data4[6];
      v42 = StringCchPrintfW(v172, 0x24u, L"LDM metadata partition");
      if ( v42 < 0 )
      {
        v49 = GetLastError();
        v50 = CurrentIP();
        v51 = ConstructPartialMsgW(
                0x2000000u,
                "VdsDisk::CreatePartition: Can't copy LDM metadata partition name (0x%08x)",
                v42);
        WdsSetupLogMessageW(
          v51,
          0,
          L"D",
          0,
          3036,
          L"base\\ntsetup\\setupplatform\\lib\\diskconfig\\diskconfigvds.cpp",
          L"VdsDisk::CreatePartition",
          v50,
          v49,
          0,
          0);
        return (unsigned int)v42;
      }
      break;
    default:
      v46 = GetLastError();
      v47 = CurrentIP();
      v48 = ConstructPartialMsgW(0x2000000u, "Unknown partition usage %d", a3);
      WdsSetupLogMessageW(
        v48,
        0,
        L"D",
        0,
        3042,
        L"base\\ntsetup\\setupplatform\\lib\\diskconfig\\diskconfigvds.cpp",
        L"VdsDisk::CreatePartition",
        v47,
        v46,
        0,
        0);
      return 2147942487LL;
  }
LABEL_56:
  if ( v156 )
  {
    v42 = SPGuidFromString(v156, &pguid);
    if ( v42 < 0 )
    {
      v60 = GetLastError();
      v61 = CurrentIP();
      v62 = ConstructPartialMsgW(
              0x2000000u,
              "VdsDisk::CreatePartition: Can't convert GUID Id string %s to GUID (0x%08x)",
              (const char *)v156,
              v42);
      WdsSetupLogMessageW(
        v62,
        0,
        L"D",
        0,
        3052,
        L"base\\ntsetup\\setupplatform\\lib\\diskconfig\\diskconfigvds.cpp",
        L"VdsDisk::CreatePartition",
        v61,
        v60,
        0,
        0);
      return (unsigned int)v42;
    }
  }
  else
  {
    v42 = CoCreateGuid(&pguid);
    if ( v42 < 0 )
    {
      v63 = GetLastError();
      v64 = CurrentIP();
      v65 = ConstructPartialMsgW(0x2000000u, "VdsDisk::CreatePartition: Can't create GPT partition GUID (0x%08x)", v42);
      WdsSetupLogMessageW(
        v65,
        0,
        L"D",
        0,
        3061,
        L"base\\ntsetup\\setupplatform\\lib\\diskconfig\\diskconfigvds.cpp",
        L"VdsDisk::CreatePartition",
        v64,
        v63,
        0,
        0);
      return (unsigned int)v42;
    }
  }
  v66 = v160;
  if ( v160 )
  {
    v42 = StringCchPrintfW(v172, 0x24u, v160);
    if ( v42 < 0 )
    {
      v67 = GetLastError();
      v68 = CurrentIP();
      v69 = ConstructPartialMsgW(
              0x2000000u,
              "VdsDisk::CreatePartition: Can't copy partition name %s (0x%08x)",
              (const char *)v160,
              v42);
      WdsSetupLogMessageW(
        v69,
        0,
        L"D",
        0,
        3071,
        L"base\\ntsetup\\setupplatform\\lib\\diskconfig\\diskconfigvds.cpp",
        L"VdsDisk::CreatePartition",
        v68,
        v67,
        0,
        0);
      return (unsigned int)v42;
    }
  }
  v70 = v171;
  if ( a12 )
  {
    v70 = v171 | 0x4000000000000000LL;
    v171 |= 0x4000000000000000uLL;
  }
  if ( a13 )
    v171 = v70 | 0x1000000000000000LL;
LABEL_69:
  v154 = 0;
  v71 = v158;
  v42 = (**(__int64 (__fastcall ***)(void *, GUID *, _QWORD **))v158[3])(v158[3], &IID_IVdsCreatePartitionEx, &v154);
  if ( v42 < 0 )
  {
    v72 = GetLastError();
    v73 = CurrentIP();
    v74 = ConstructPartialMsgW(
            0x2000000u,
            "VdsDisk::CreatePartition: Failed to query IID_IVdsCreatePartitionEx interface [%s] (0x%08x)",
            (const char *)L"create partition",
            v42);
    WdsSetupLogMessageW(
      v74,
      0,
      L"D",
      0,
      3087,
      L"base\\ntsetup\\setupplatform\\lib\\diskconfig\\diskconfigvds.cpp",
      L"VdsDisk::CreatePartition",
      v73,
      v72,
      0,
      0);
    if ( v154 )
      (*(void (__fastcall **)(_QWORD *))(*v154 + 16LL))(v154);
    return (unsigned int)v42;
  }
  v155 = 0;
  v42 = (*(__int64 (__fastcall **)(_QWORD *, unsigned __int64, unsigned __int64, _QWORD, int *, _QWORD **))(*v154 + 24LL))(
          v154,
          v167,
          v28,
          a10,
          &v168,
          &v155);
  if ( v42 < 0 )
  {
    v75 = GetLastError();
    v76 = CurrentIP();
    v77 = ConstructPartialMsgW(0x2000000u, "VdsDisk::CreatePartition: Can't create partition (0x%08x)", v42);
    WdsSetupLogMessageW(
      v77,
      0,
      L"D",
      0,
      3093,
      L"base\\ntsetup\\setupplatform\\lib\\diskconfig\\diskconfigvds.cpp",
      L"VdsDisk::CreatePartition",
      v76,
      v75,
      0,
      0);
    if ( v155 )
      (*(void (__fastcall **)(_QWORD *))(*v155 + 16LL))(v155);
    if ( v154 )
      (*(void (__fastcall **)(_QWORD *))(*v154 + 16LL))(v154);
    return (unsigned int)v42;
  }
  memset(v176, 0, sizeof(v176));
  v42 = pVdsDoAsyncWait(v155, L"partition creation", v176);
  if ( v42 < 0 )
  {
    if ( v155 )
      (*(void (__fastcall **)(_QWORD *, _QWORD))(*v155 + 16LL))(v155, *v155);
    if ( v154 )
      (*(void (__fastcall **)(_QWORD *))(*v154 + 16LL))(v154);
    return (unsigned int)v42;
  }
  v78 = DWORD2(v176[0]);
  if ( !v66 )
  {
LABEL_155:
    v165 = 0;
    v164 = &RAII::CAutoRelease<SetupPlatform::IPartitionEnumerator *>::`vftable';
    v125 = (__int64 (__fastcall *)(void **, __int64))*((_QWORD *)*v71 + 11);
    v126 = RAII::CAutoCleanupBase<VdsVolumePathEnumerator *>::operator&(&v164);
    v42 = v125(v71, v126);
    if ( v42 >= 0 )
    {
      v163 = 0;
      v162 = &RAII::CAutoRelease<SetupPlatform::IPartition *>::`vftable';
      while ( 1 )
      {
        v159 = 0;
        v158 = &RAII::CAutoRelease<SetupPlatform::IPartition *>::`vftable';
        v135 = (__int64 (__fastcall ***)(_QWORD, __int64))((__int64 (__fastcall *)(void ***))v164[3])(&v164);
        v136 = **v135;
        v137 = ((__int64 (__fastcall *)(void ***))v158[1])(&v158);
        v138 = v136(v135, v137);
        v42 = v138;
        if ( v138 == -2147024637 )
          break;
        if ( v138 < 0 )
        {
          v146 = GetLastError();
          v147 = CurrentIP();
          v148 = ConstructPartialMsgW(0x2000000u, "VdsDisk::CreatePartition: Can't enumerate partitions (0x%08x)", v42);
          WdsSetupLogMessageW(
            v148,
            0,
            L"D",
            0,
            3201,
            L"base\\ntsetup\\setupplatform\\lib\\diskconfig\\diskconfigvds.cpp",
            L"VdsDisk::CreatePartition",
            v147,
            v146,
            0,
            0);
          v158 = &RAII::CAutoRelease<SetupPlatform::IPartition *>::`vftable';
          if ( v159 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v159 + 168LL))(v159);
            v159 = 0;
          }
          v162 = &RAII::CAutoRelease<SetupPlatform::IPartition *>::`vftable';
          if ( v163 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v163 + 168LL))(v163);
            v163 = 0;
          }
          v164 = &RAII::CAutoRelease<SetupPlatform::IPartitionEnumerator *>::`vftable';
          if ( v165 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v165 + 8LL))(v165);
            v165 = 0;
          }
          if ( v155 )
            (*(void (__fastcall **)(_QWORD *))(*v155 + 16LL))(v155);
          if ( v154 )
            (*(void (__fastcall **)(_QWORD *))(*v154 + 16LL))(v154);
          return (unsigned int)v42;
        }
        v160 = 0;
        v139 = ((__int64 (__fastcall *)(void ***))v158[3])(&v158);
        v42 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v139 + 24LL))(v139, &v160);
        if ( v42 < 0 )
        {
          v143 = GetLastError();
          v144 = CurrentIP();
          v145 = ConstructPartialMsgW(
                   0x2000000u,
                   "VdsDisk::CreatePartition: Can't get partition properties (0x%08x)",
                   v42);
          WdsSetupLogMessageW(
            v145,
            0,
            L"D",
            0,
            3209,
            L"base\\ntsetup\\setupplatform\\lib\\diskconfig\\diskconfigvds.cpp",
            L"VdsDisk::CreatePartition",
            v144,
            v143,
            0,
            0);
          v158 = &RAII::CAutoRelease<SetupPlatform::IPartition *>::`vftable';
          if ( v159 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v159 + 168LL))(v159);
            v159 = 0;
          }
          v162 = &RAII::CAutoRelease<SetupPlatform::IPartition *>::`vftable';
          if ( v163 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v163 + 168LL))(v163);
            v163 = 0;
          }
          v164 = &RAII::CAutoRelease<SetupPlatform::IPartitionEnumerator *>::`vftable';
          if ( v165 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v165 + 8LL))(v165);
            v165 = 0;
          }
          if ( v155 )
            (*(void (__fastcall **)(_QWORD *))(*v155 + 16LL))(v155);
          if ( v154 )
            (*(void (__fastcall **)(_QWORD *))(*v154 + 16LL))(v154);
          return (unsigned int)v42;
        }
        v140 = v78 - *((_DWORD *)v160 + 2);
        if ( v140 < 0 )
          v140 = *((_DWORD *)v160 + 2) - v78;
        if ( v140 < 0x200000 )
        {
          v141 = v28 - *((_DWORD *)v160 + 4);
          if ( v141 < 0 )
            v141 = *((_DWORD *)v160 + 4) - v28;
          if ( v141 < 0x200000 )
          {
            v142 = v159;
            v159 = 0;
            ((void (__fastcall *)(void ***, __int64))v162[6])(&v162, v142);
            v158 = &RAII::CAutoRelease<SetupPlatform::IPartition *>::`vftable';
            if ( v159 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v159 + 168LL))(v159);
            goto LABEL_208;
          }
        }
        v158 = &RAII::CAutoRelease<SetupPlatform::IPartition *>::`vftable';
        if ( v159 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v159 + 168LL))(v159);
      }
      v42 = 0;
      v158 = &RAII::CAutoRelease<SetupPlatform::IPartition *>::`vftable';
      if ( v159 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v159 + 168LL))(v159);
LABEL_208:
      if ( ((unsigned __int8 (__fastcall *)(void ***))v162[9])(&v162) )
      {
        v149 = GetLastError();
        v150 = CurrentIP();
        v151 = ConstructPartialMsgW(
                 0x2000000u,
                 "VdsDisk::CreatePartition: Can't find the partition that was just created");
        WdsSetupLogMessageW(
          v151,
          0,
          L"D",
          0,
          3223,
          L"base\\ntsetup\\setupplatform\\lib\\diskconfig\\diskconfigvds.cpp",
          L"VdsDisk::CreatePartition",
          v150,
          v149,
          0,
          0);
        v162 = &RAII::CAutoRelease<SetupPlatform::IPartition *>::`vftable';
        if ( v163 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v163 + 168LL))(v163);
          v163 = 0;
        }
        v164 = &RAII::CAutoRelease<SetupPlatform::IPartitionEnumerator *>::`vftable';
        if ( v165 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v165 + 8LL))(v165);
          v165 = 0;
        }
        if ( v155 )
          (*(void (__fastcall **)(_QWORD *))(*v155 + 16LL))(v155);
        goto LABEL_215;
      }
      if ( v174 )
      {
        v152 = v163;
        v153 = 0;
        v163 = 0;
        *v174 = v152;
      }
      else
      {
        v153 = v163;
      }
      v162 = &RAII::CAutoRelease<SetupPlatform::IPartition *>::`vftable';
      if ( v153 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v153 + 168LL))(v153);
        v163 = 0;
      }
      v164 = &RAII::CAutoRelease<SetupPlatform::IPartitionEnumerator *>::`vftable';
      if ( v165 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v165 + 8LL))(v165);
        v165 = 0;
      }
      if ( v155 )
        (*(void (__fastcall **)(_QWORD *))(*v155 + 16LL))(v155);
      if ( v154 )
        (*(void (__fastcall **)(_QWORD *))(*v154 + 16LL))(v154);
    }
    else
    {
      v127 = GetLastError();
      v128 = CurrentIP();
      v129 = ConstructPartialMsgW(
               0x2000000u,
               "VdsDisk::CreatePartition: Failed to create partition enumerator (0x%08x)",
               v42);
      WdsSetupLogMessageW(
        v129,
        0,
        L"D",
        0,
        3185,
        L"base\\ntsetup\\setupplatform\\lib\\diskconfig\\diskconfigvds.cpp",
        L"VdsDisk::CreatePartition",
        v128,
        v127,
        0,
        0);
      v164 = &RAII::CAutoRelease<SetupPlatform::IPartitionEnumerator *>::`vftable';
      if ( v165 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v165 + 8LL))(v165);
        v165 = 0;
      }
      if ( v155 )
        (*(void (__fastcall **)(_QWORD *))(*v155 + 16LL))(v155);
      if ( v154 )
        (*(void (__fastcall **)(_QWORD *))(*v154 + 16LL))(v154);
    }
    return (unsigned int)v42;
  }
  nInBufferSize[0] = 0;
  v79 = (*((__int64 (__fastcall **)(void **))*v71 + 1))(v71);
  lpMem = (LPVOID)GetDriveLayout(v79, nInBufferSize);
  v156 = (unsigned __int16 *)&RAII::CAutoWdsLibFree<_DRIVE_LAYOUT_INFORMATION_EX *>::`vftable';
  v158 = 0;
  if ( !(unsigned __int8)RAII::CAutoCleanupBase<DU::IDUUpdate *>::operator==(&v156, &v158) )
  {
    for ( i = 0; ; ++i )
    {
      if ( i >= *(_DWORD *)((*((__int64 (__fastcall **)(unsigned __int16 **))v156 + 3))(&v156) + 4) )
      {
        v130 = GetLastError();
        v131 = CurrentIP();
        v132 = ConstructPartialMsgW(
                 0x2000000u,
                 "VdsDisk::CreatePartition: Can't find the partition that was just created");
        WdsSetupLogMessageW(
          v132,
          0,
          L"D",
          0,
          3136,
          L"base\\ntsetup\\setupplatform\\lib\\diskconfig\\diskconfigvds.cpp",
          L"VdsDisk::CreatePartition",
          v131,
          v130,
          0,
          0);
        v156 = (unsigned __int16 *)&RAII::CAutoWdsLibFree<_DRIVE_LAYOUT_INFORMATION_EX *>::`vftable';
        v133 = lpMem;
        if ( lpMem )
        {
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v133);
          lpMem = 0;
        }
        if ( v155 )
          (*(void (__fastcall **)(_QWORD *))(*v155 + 16LL))(v155);
LABEL_215:
        if ( v154 )
          (*(void (__fastcall **)(_QWORD *))(*v154 + 16LL))(v154);
        return 2147549183LL;
      }
      v90 = (*((__int64 (__fastcall **)(unsigned __int16 **))v156 + 3))(&v156);
      v91 = v90;
      v92 = 144LL * i;
      v93 = v78 - *(_DWORD *)(v90 + v92 + 56);
      if ( v93 < 0 )
        v93 = *(_DWORD *)(v90 + v92 + 56) - v78;
      if ( v93 < 0x200000 )
      {
        v94 = *(_DWORD *)(v90 + v92 + 64) - v28;
        v95 = v28 - *(_DWORD *)(v90 + v92 + 64);
        if ( v95 < 0 )
          v95 = v94;
        if ( v95 < 0x200000 )
          break;
      }
    }
    v42 = StringCchPrintfW((unsigned __int16 *)(v92 + v91 + 120), 0x24u, v66);
    if ( v42 < 0 )
    {
      v96 = GetLastError();
      v97 = CurrentIP();
      v98 = ConstructPartialMsgW(
              0x2000000u,
              "VdsDisk::CreatePartition: Can't copy partition name %s (0x%08x)",
              (const char *)v66,
              v42);
      WdsSetupLogMessageW(
        v98,
        0,
        L"D",
        0,
        3143,
        L"base\\ntsetup\\setupplatform\\lib\\diskconfig\\diskconfigvds.cpp",
        L"VdsDisk::CreatePartition",
        v97,
        v96,
        0,
        0);
      v156 = (unsigned __int16 *)&RAII::CAutoWdsLibFree<_DRIVE_LAYOUT_INFORMATION_EX *>::`vftable';
      v99 = lpMem;
      if ( lpMem )
      {
        v100 = GetProcessHeap();
        HeapFree(v100, 0, v99);
        lpMem = 0;
      }
      if ( v155 )
        (*(void (__fastcall **)(_QWORD *))(*v155 + 16LL))(v155);
      if ( v154 )
        (*(void (__fastcall **)(_QWORD *))(*v154 + 16LL))(v154);
      return (unsigned int)v42;
    }
    memset_0(FileName, 0, 0x208u);
    v101 = (*((__int64 (__fastcall **)(void **))*v71 + 1))(v71);
    v42 = StringCchPrintfW(FileName, 0x104u, L"\\\\.\\PHYSICALDRIVE%u", v101);
    if ( v42 < 0 )
    {
      v102 = GetLastError();
      v103 = CurrentIP();
      v104 = ConstructPartialMsgW(0x2000000u, "VdsDisk::CreatePartition: Can't copy disk path (0x%08x)", v42);
      WdsSetupLogMessageW(
        v104,
        0,
        L"D",
        0,
        3152,
        L"base\\ntsetup\\setupplatform\\lib\\diskconfig\\diskconfigvds.cpp",
        L"VdsDisk::CreatePartition",
        v103,
        v102,
        0,
        0);
      v156 = (unsigned __int16 *)&RAII::CAutoWdsLibFree<_DRIVE_LAYOUT_INFORMATION_EX *>::`vftable';
      v105 = lpMem;
      if ( lpMem )
      {
        v106 = GetProcessHeap();
        HeapFree(v106, 0, v105);
        lpMem = 0;
      }
      if ( v155 )
        (*(void (__fastcall **)(_QWORD *))(*v155 + 16LL))(v155);
      if ( v154 )
        (*(void (__fastcall **)(_QWORD *))(*v154 + 16LL))(v154);
      return (unsigned int)v42;
    }
    FileW = CreateFileW(FileName, 0xC0000000, 3u, 0, 3u, 0x80u, 0);
    v160 = (unsigned __int16 *)&RAII::CAutoCleanup<void *>::`vftable';
    hObject = FileW;
    if ( *(_QWORD *)RAII::CAutoCleanupBase<VdsVolumePathEnumerator *>::operator&(&v160) == -1 )
    {
      v108 = GetLastError();
      v109 = CurrentIP();
      v110 = ConstructPartialMsgW(
               0x2000000u,
               "VdsDisk::CreatePartition: Could not get handle to disk to set partition name (0x%08x)",
               v42);
      WdsSetupLogMessageW(
        v110,
        0,
        L"D",
        0,
        3168,
        L"base\\ntsetup\\setupplatform\\lib\\diskconfig\\diskconfigvds.cpp",
        L"VdsDisk::CreatePartition",
        v109,
        v108,
        0,
        0);
      v111 = GetLastError();
      v112 = v111 < 0;
      if ( v111 > 0 )
        v112 = 1;
      if ( v112 )
      {
        v113 = GetLastError();
        v86 = v113;
        if ( v113 > 0 )
          v86 = (unsigned __int16)v113 | 0x80070000;
      }
      else
      {
        v86 = -2147467259;
      }
      v160 = (unsigned __int16 *)&RAII::CAutoCleanup<void *>::`vftable';
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      {
        CloseHandle(hObject);
        hObject = 0;
      }
      v156 = (unsigned __int16 *)&RAII::CAutoWdsLibFree<_DRIVE_LAYOUT_INFORMATION_EX *>::`vftable';
      v114 = lpMem;
      if ( lpMem )
      {
        v115 = GetProcessHeap();
        HeapFree(v115, 0, v114);
        lpMem = 0;
      }
      if ( v155 )
        (*(void (__fastcall **)(_QWORD *))(*v155 + 16LL))(v155);
      if ( v154 )
        (*(void (__fastcall **)(_QWORD *, _QWORD))(*v154 + 16LL))(v154, *v154);
      return v86;
    }
    v116 = (void *)(*((__int64 (__fastcall **)(unsigned __int16 **))v156 + 4))(&v156);
    v117 = (HANDLE *)(*((__int64 (__fastcall **)(unsigned __int16 **))v160 + 4))(&v160);
    if ( !(unsigned int)SetDriveLayout(*v117, v116, nInBufferSize[0]) )
    {
      v118 = GetLastError();
      v119 = CurrentIP();
      v120 = ConstructPartialMsgW(
               0x2000000u,
               "VdsDisk::CreatePartition: Failed to set partition name %s (0x%08x)",
               (const char *)v66,
               v42);
      WdsSetupLogMessageW(
        v120,
        0,
        L"D",
        0,
        3174,
        L"base\\ntsetup\\setupplatform\\lib\\diskconfig\\diskconfigvds.cpp",
        L"VdsDisk::CreatePartition",
        v119,
        v118,
        0,
        0);
      v160 = (unsigned __int16 *)&RAII::CAutoCleanup<void *>::`vftable';
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      {
        CloseHandle(hObject);
        hObject = 0;
      }
      v156 = (unsigned __int16 *)&RAII::CAutoWdsLibFree<_DRIVE_LAYOUT_INFORMATION_EX *>::`vftable';
      v121 = lpMem;
      if ( lpMem )
      {
        v122 = GetProcessHeap();
        HeapFree(v122, 0, v121);
        lpMem = 0;
      }
      if ( v155 )
        (*(void (__fastcall **)(_QWORD *))(*v155 + 16LL))(v155);
      if ( v154 )
        (*(void (__fastcall **)(_QWORD *))(*v154 + 16LL))(v154);
      return 2147500037LL;
    }
    v160 = (unsigned __int16 *)&RAII::CAutoCleanup<void *>::`vftable';
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      CloseHandle(hObject);
      hObject = 0;
    }
    v156 = (unsigned __int16 *)&RAII::CAutoWdsLibFree<_DRIVE_LAYOUT_INFORMATION_EX *>::`vftable';
    v123 = lpMem;
    if ( lpMem )
    {
      v124 = GetProcessHeap();
      HeapFree(v124, 0, v123);
    }
    goto LABEL_155;
  }
  v80 = GetLastError();
  v81 = CurrentIP();
  v82 = ConstructPartialMsgW(0x2000000u, "VdsDisk::CreatePartition: Failed to get drive layout info (0x%08x)", v42);
  WdsSetupLogMessageW(
    v82,
    0,
    L"D",
    0,
    3115,
    L"base\\ntsetup\\setupplatform\\lib\\diskconfig\\diskconfigvds.cpp",
    L"VdsDisk::CreatePartition",
    v81,
    v80,
    0,
    0);
  v83 = GetLastError();
  v84 = v83 < 0;
  if ( v83 > 0 )
    v84 = 1;
  if ( v84 )
  {
    v85 = GetLastError();
    v86 = v85;
    if ( v85 > 0 )
      v86 = (unsigned __int16)v85 | 0x80070000;
  }
  else
  {
    v86 = -2147467259;
  }
  v156 = (unsigned __int16 *)&RAII::CAutoWdsLibFree<_DRIVE_LAYOUT_INFORMATION_EX *>::`vftable';
  v87 = lpMem;
  if ( lpMem )
  {
    v88 = GetProcessHeap();
    HeapFree(v88, 0, v87);
    lpMem = 0;
  }
  if ( v155 )
    (*(void (__fastcall **)(_QWORD *))(*v155 + 16LL))(v155);
  if ( v154 )
    (*(void (__fastcall **)(_QWORD *))(*v154 + 16LL))(v154);
  return v86;
}

```

## disassembly

```asm
0x18039cc04  push    rbp
0x18039cc06  push    rbx
0x18039cc07  push    rsi
0x18039cc08  push    rdi
0x18039cc09  push    r12
0x18039cc0b  push    r13
0x18039cc0d  push    r14
0x18039cc0f  push    r15
0x18039cc11  lea     rbp, [rsp-338h]
0x18039cc19  sub     rsp, 438h
0x18039cc20  mov     [rbp+370h+var_310], 0FFFFFFFFFFFFFFFEh
0x18039cc28  mov     rax, cs:__security_cookie
0x18039cc2f  xor     rax, rsp
0x18039cc32  mov     [rbp+370h+var_50], rax
0x18039cc39  mov     dil, r9b
0x18039cc3c  mov     esi, r8d
0x18039cc3f  mov     r12d, edx
0x18039cc42  mov     rbx, rcx
0x18039cc45  mov     [rbp+370h+var_3F0], rcx
0x18039cc49  mov     r15, [rbp+370h+arg_20]
0x18039cc50  mov     rax, [rbp+370h+arg_28]
0x18039cc57  mov     [rsp+470h+var_400], rax
0x18039cc5c  mov     rax, [rbp+370h+arg_30]
0x18039cc63  mov     [rbp+370h+var_3E0], rax
0x18039cc67  mov     rax, [rbp+370h+arg_68]
0x18039cc6e  mov     [rbp+370h+var_318], rax
0x18039cc72  xor     r13d, r13d
0x18039cc75  mov     [rbp+370h+var_3A8], r13
0x18039cc79  mov     qword ptr [rbp+370h+nInBufferSize], r13
0x18039cc7d  lea     rax, [rbp+370h+nInBufferSize]
0x18039cc81  mov     qword ptr [rsp+470h+dwCreationDisposition], rax; unsigned __int64 *
0x18039cc86  lea     r9, [rbp+370h+var_3A8]; unsigned __int64 *
0x18039cc8a  mov     r8, rcx; struct SetupPlatform::IDisk *
0x18039cc8d  mov     rdx, [rbp+370h+arg_40]; unsigned __int64
0x18039cc94  mov     rcx, [rbp+370h+arg_38]; unsigned __int64
0x18039cc9b  call    ?SPAllocateRange@@YAJ_K0PEAUIDisk@SetupPlatform@@PEA_K2@Z; SPAllocateRange(unsigned __int64,unsigned __int64,SetupPlatform::IDisk *,unsigned __int64 *,unsigned __int64 *)
0x18039cca0  mov     r14d, eax
0x18039cca3  test    eax, eax
0x18039cca5  jns     short loc_18039CD1C
0x18039cca7  call    cs:__imp_GetLastError
0x18039ccad  mov     edi, eax
0x18039ccaf  call    cs:__imp_CurrentIP
0x18039ccb5  mov     rbx, rax
0x18039ccb8  mov     r8d, r14d
0x18039ccbb  lea     rdx, aVdsdiskCreatep_7; "VdsDisk::CreatePartition: Can't allocat"...
0x18039ccc2  mov     ecx, 2000000h; unsigned int
0x18039ccc7  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18039cccc  mov     [rsp+470h+var_420], r13d
0x18039ccd1  mov     [rsp+470h+var_428], r13
0x18039ccd6  mov     [rsp+470h+var_430], edi
0x18039ccda  mov     [rsp+470h+var_438], rbx
0x18039ccdf  lea     rcx, aVdsdiskCreatep_10; "VdsDisk::CreatePartition"
0x18039cce6  mov     [rsp+470h+hTemplateFile], rcx
0x18039cceb  lea     rcx, aBaseNtsetupSet_6; "base\\ntsetup\\setupplatform\\lib\\disk"...
0x18039ccf2  mov     qword ptr [rsp+470h+dwFlagsAndAttributes], rcx
0x18039ccf7  mov     [rsp+470h+dwCreationDisposition], 0B40h
0x18039ccff  xor     r9d, r9d
0x18039cd02  lea     r8, aD_0; "D"
0x18039cd09  xor     edx, edx
0x18039cd0b  mov     rcx, rax
0x18039cd0e  call    cs:__imp_WdsSetupLogMessageW
0x18039cd14  mov     eax, r14d
0x18039cd17  jmp     loc_18039E503
0x18039cd1c  xor     edx, edx; Val
0x18039cd1e  mov     r8d, 80h; Size
0x18039cd24  lea     rcx, [rbp+370h+var_2E0]; void *
0x18039cd2b  call    memset_0
0x18039cd30  mov     rcx, [rbx+18h]
0x18039cd34  mov     rax, [rcx]
0x18039cd37  lea     rdx, [rbp+370h+var_2E0]
0x18039cd3e  mov     rax, [rax+18h]
0x18039cd42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18039cd47  mov     r14d, eax
0x18039cd4a  test    eax, eax
0x18039cd4c  jns     short loc_18039CDAB
0x18039cd4e  call    cs:__imp_GetLastError
0x18039cd54  mov     edi, eax
0x18039cd56  call    cs:__imp_CurrentIP
0x18039cd5c  mov     rbx, rax
0x18039cd5f  mov     r8d, r14d
0x18039cd62  lea     rdx, aVdsdiskCreatep_2; "VdsDisk::CreatePartition: Failed to get"...
0x18039cd69  mov     ecx, 2000000h; unsigned int
0x18039cd6e  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18039cd73  mov     [rsp+470h+var_420], r13d
0x18039cd78  mov     [rsp+470h+var_428], r13
0x18039cd7d  mov     [rsp+470h+var_430], edi
0x18039cd81  mov     [rsp+470h+var_438], rbx
0x18039cd86  lea     rcx, aVdsdiskCreatep_10; "VdsDisk::CreatePartition"
0x18039cd8d  mov     [rsp+470h+hTemplateFile], rcx
0x18039cd92  lea     rcx, aBaseNtsetupSet_6; "base\\ntsetup\\setupplatform\\lib\\disk"...
0x18039cd99  mov     qword ptr [rsp+470h+dwFlagsAndAttributes], rcx
0x18039cd9e  mov     [rsp+470h+dwCreationDisposition], 0B49h
0x18039cda6  jmp     loc_18039CCFF
0x18039cdab  mov     ecx, [rbp+370h+var_2B0]
0x18039cdb1  xor     edx, edx
0x18039cdb3  mov     r8, [rbp+370h+var_3A8]
0x18039cdb7  mov     [rbp+370h+var_3A8], r8
0x18039cdbb  mov     rax, r8
0x18039cdbe  div     rcx
0x18039cdc1  mov     r13, qword ptr [rbp+370h+nInBufferSize]
0x18039cdc5  test    rdx, rdx
0x18039cdc8  jz      short loc_18039CDDC
0x18039cdca  mov     eax, ecx
0x18039cdcc  sub     rax, rdx
0x18039cdcf  add     r8, rax
0x18039cdd2  mov     [rbp+370h+var_3A8], r8
0x18039cdd6  sub     rdx, rcx
0x18039cdd9  add     r13, rdx
0x18039cddc  xor     edx, edx
0x18039cdde  mov     rax, r13
0x18039cde1  div     rcx
0x18039cde4  sub     r13, rdx
0x18039cde7  mov     [rbp+370h+var_320], 0
0x18039cdef  mov     rax, [rbx]
0x18039cdf2  lea     rdx, [rbp+370h+var_320]
0x18039cdf6  mov     rcx, rbx
0x18039cdf9  mov     rax, [rax+10h]
0x18039cdfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18039ce02  mov     r14d, eax
0x18039ce05  test    eax, eax
0x18039ce07  jns     short loc_18039CE6D
0x18039ce09  call    cs:__imp_GetLastError
0x18039ce0f  mov     edi, eax
0x18039ce11  call    cs:__imp_CurrentIP
0x18039ce17  mov     rbx, rax
0x18039ce1a  mov     r8d, r14d
0x18039ce1d  lea     rdx, aVdsdiskCreatep_9; "VdsDisk::CreatePartition: Can't get dis"...
0x18039ce24  mov     ecx, 2000000h; unsigned int
0x18039ce29  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18039ce2e  mov     [rsp+470h+var_420], 0
0x18039ce36  mov     [rsp+470h+var_428], 0
0x18039ce3f  mov     [rsp+470h+var_430], edi
0x18039ce43  mov     [rsp+470h+var_438], rbx
0x18039ce48  lea     rcx, aVdsdiskCreatep_10; "VdsDisk::CreatePartition"
0x18039ce4f  mov     [rsp+470h+hTemplateFile], rcx
0x18039ce54  lea     rcx, aBaseNtsetupSet_6; "base\\ntsetup\\setupplatform\\lib\\disk"...
0x18039ce5b  mov     qword ptr [rsp+470h+dwFlagsAndAttributes], rcx
0x18039ce60  mov     [rsp+470h+dwCreationDisposition], 0B5Bh
0x18039ce68  jmp     loc_18039CCFF
0x18039ce6d  mov     rbx, [rbp+370h+var_320]
0x18039ce71  xor     r14d, r14d
0x18039ce74  test    dil, dil
0x18039ce77  jz      short loc_18039CEF3
0x18039ce79  cmp     dword ptr [rbx+44h], 1
0x18039ce7d  jz      short loc_18039CEF3
0x18039ce7f  call    cs:__imp_GetLastError
0x18039ce85  mov     edi, eax
0x18039ce87  call    cs:__imp_CurrentIP
0x18039ce8d  mov     rbx, rax
0x18039ce90  lea     rdx, aVdsdiskCreatep_6; "VdsDisk::CreatePartition: MBR type not "...
0x18039ce97  mov     ecx, 2000000h; unsigned int
0x18039ce9c  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18039cea1  mov     [rsp+470h+var_420], r14d
0x18039cea6  mov     [rsp+470h+var_428], r14
0x18039ceab  mov     [rsp+470h+var_430], edi
0x18039ceaf  mov     [rsp+470h+var_438], rbx
0x18039ceb4  lea     rcx, aVdsdiskCreatep_10; "VdsDisk::CreatePartition"
0x18039cebb  mov     [rsp+470h+hTemplateFile], rcx
0x18039cec0  lea     rcx, aBaseNtsetupSet_6; "base\\ntsetup\\setupplatform\\lib\\disk"...
0x18039cec7  mov     qword ptr [rsp+470h+dwFlagsAndAttributes], rcx
0x18039cecc  mov     [rsp+470h+dwCreationDisposition], 0B63h
0x18039ced4  xor     r9d, r9d
0x18039ced7  lea     r8, aD_0; "D"
0x18039cede  xor     edx, edx
0x18039cee0  mov     rcx, rax
0x18039cee3  call    cs:__imp_WdsSetupLogMessageW
0x18039cee9  mov     eax, 80070032h
0x18039ceee  jmp     loc_18039E503
0x18039cef3  test    r15, r15
0x18039cef6  jz      short loc_18039CF58
0x18039cef8  cmp     dword ptr [rbx+44h], 2
0x18039cefc  jz      short loc_18039CF58
0x18039cefe  call    cs:__imp_GetLastError
0x18039cf04  mov     edi, eax
0x18039cf06  call    cs:__imp_CurrentIP
0x18039cf0c  mov     rbx, rax
0x18039cf0f  lea     rdx, aVdsdiskCreatep_15; "VdsDisk::CreatePartition: Partition GUI"...
0x18039cf16  mov     ecx, 2000000h; unsigned int
0x18039cf1b  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18039cf20  mov     [rsp+470h+var_420], r14d
0x18039cf25  mov     [rsp+470h+var_428], r14
0x18039cf2a  mov     [rsp+470h+var_430], edi
0x18039cf2e  mov     [rsp+470h+var_438], rbx
0x18039cf33  lea     rcx, aVdsdiskCreatep_10; "VdsDisk::CreatePartition"
0x18039cf3a  mov     [rsp+470h+hTemplateFile], rcx
0x18039cf3f  lea     rcx, aBaseNtsetupSet_6; "base\\ntsetup\\setupplatform\\lib\\disk"...
0x18039cf46  mov     qword ptr [rsp+470h+dwFlagsAndAttributes], rcx
0x18039cf4b  mov     [rsp+470h+dwCreationDisposition], 0B6Bh
0x18039cf53  jmp     loc_18039CED4
0x18039cf58  xor     edx, edx; Val
0x18039cf5a  lea     r8d, [rdx+78h]; Size
0x18039cf5e  lea     rcx, [rbp+370h+var_3A0]; void *
0x18039cf62  call    memset_0
0x18039cf67  cmp     dword ptr [rbx+44h], 1
0x18039cf6b  jnz     loc_18039D048
0x18039cf71  mov     [rbp+370h+var_3A0], 1
0x18039cf78  mov     al, [rbp+370h+arg_50]
0x18039cf7e  mov     byte ptr [rbp+370h+Buf1+1], al
0x18039cf81  test    dil, dil
0x18039cf84  jz      short loc_18039CF8F
0x18039cf86  mov     byte ptr [rbp+370h+Buf1], dil
0x18039cf8a  jmp     loc_18039D048
0x18039cf8f  mov     ecx, r12d
0x18039cf92  test    r12d, r12d
0x18039cf95  jz      loc_18039D03B
0x18039cf9b  sub     ecx, 1
0x18039cf9e  jz      loc_18039D035
0x18039cfa4  sub     ecx, 1
0x18039cfa7  jz      loc_18039D02F
0x18039cfad  cmp     ecx, 1
0x18039cfb0  jz      short loc_18039D029
0x18039cfb2  call    cs:__imp_GetLastError
0x18039cfb8  mov     edi, eax
0x18039cfba  call    cs:__imp_CurrentIP
0x18039cfc0  mov     rbx, rax
0x18039cfc3  mov     r8d, r12d
0x18039cfc6  lea     rdx, aUnknownPartiti_0; "Unknown partition type %d"
0x18039cfcd  mov     ecx, 2000000h; unsigned int
0x18039cfd2  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18039cfd7  mov     [rsp+470h+var_420], r14d
0x18039cfdc  mov     [rsp+470h+var_428], r14
0x18039cfe1  mov     [rsp+470h+var_430], edi
0x18039cfe5  mov     [rsp+470h+var_438], rbx
0x18039cfea  lea     rcx, aVdsdiskCreatep_10; "VdsDisk::CreatePartition"
0x18039cff1  mov     [rsp+470h+hTemplateFile], rcx
0x18039cff6  lea     rcx, aBaseNtsetupSet_6; "base\\ntsetup\\setupplatform\\lib\\disk"...
0x18039cffd  mov     qword ptr [rsp+470h+dwFlagsAndAttributes], rcx
0x18039d002  mov     [rsp+470h+dwCreationDisposition], 0B9Ah
0x18039d00a  xor     r9d, r9d
0x18039d00d  lea     r8, aD_0; "D"
0x18039d014  xor     edx, edx
0x18039d016  mov     rcx, rax
0x18039d019  call    cs:__imp_WdsSetupLogMessageW
0x18039d01f  mov     eax, 80070057h
0x18039d024  jmp     loc_18039E503
0x18039d029  mov     byte ptr [rbp+370h+Buf1], 27h ; '''
0x18039d02d  jmp     short loc_18039D048
0x18039d02f  mov     byte ptr [rbp+370h+Buf1], 6
0x18039d033  jmp     short loc_18039D048
0x18039d035  mov     byte ptr [rbp+370h+Buf1], 5
0x18039d039  jmp     short loc_18039D048
0x18039d03b  cmp     esi, 1
0x18039d03e  mov     byte ptr [rbp+370h+Buf1], 6
0x18039d042  jnz     short loc_18039D048
0x18039d044  mov     byte ptr [rbp+370h+Buf1], 0Bh
0x18039d048  mov     edi, 24h ; '$'
0x18039d04d  xor     r12d, r12d
0x18039d050  cmp     dword ptr [rbx+44h], 2
0x18039d054  jnz     loc_18039D5BB
0x18039d05a  mov     [rbp+370h+var_3A0], 2
0x18039d061  mov     rax, 8000000000000000h
0x18039d06b  mov     [rbp+370h+var_378], rax
0x18039d06f  test    r15, r15
0x18039d072  jz      loc_18039D127
0x18039d078  lea     rdx, [rbp+370h+Buf1]; struct _GUID *
0x18039d07c  mov     rcx, r15; unsigned __int16 *
0x18039d07f  call    ?SPGuidFromString@@YAJPEBGPEAU_GUID@@@Z; SPGuidFromString(ushort const *,_GUID *)
0x18039d084  mov     esi, eax
0x18039d086  test    eax, eax
0x18039d088  jns     short loc_18039D0FF
0x18039d08a  call    cs:__imp_GetLastError
0x18039d090  mov     edi, eax
0x18039d092  call    cs:__imp_CurrentIP
0x18039d098  mov     rbx, rax
0x18039d09b  mov     r9d, esi
0x18039d09e  mov     r8, r15
0x18039d0a1  lea     rdx, aVdsdiskCreatep_13; "VdsDisk::CreatePartition: Can't convert"...
0x18039d0a8  mov     ecx, 2000000h; unsigned int
0x18039d0ad  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18039d0b2  mov     [rsp+470h+var_420], r12d
0x18039d0b7  mov     [rsp+470h+var_428], r12
0x18039d0bc  mov     [rsp+470h+var_430], edi
0x18039d0c0  mov     [rsp+470h+var_438], rbx
0x18039d0c5  lea     rcx, aVdsdiskCreatep_10; "VdsDisk::CreatePartition"
0x18039d0cc  mov     [rsp+470h+hTemplateFile], rcx
0x18039d0d1  lea     rcx, aBaseNtsetupSet_6; "base\\ntsetup\\setupplatform\\lib\\disk"...
0x18039d0d8  mov     qword ptr [rsp+470h+dwFlagsAndAttributes], rcx
0x18039d0dd  mov     [rsp+470h+dwCreationDisposition], 0BAAh
0x18039d0e5  xor     r9d, r9d
0x18039d0e8  lea     r8, aD_0; "D"
0x18039d0ef  xor     edx, edx
0x18039d0f1  mov     rcx, rax
0x18039d0f4  call    cs:__imp_WdsSetupLogMessageW
0x18039d0fa  jmp     loc_18039E501
0x18039d0ff  mov     r8d, 10h; Size
0x18039d105  lea     rdx, PARTITION_MSFT_RECOVERY_GUID; Buf2
0x18039d10c  lea     rcx, [rbp+370h+Buf1]; Buf1
0x18039d110  call    memcmp_0
0x18039d115  test    eax, eax
0x18039d117  jnz     loc_18039D416
0x18039d11d  or      [rbp+370h+var_378], 1
0x18039d122  jmp     loc_18039D416
0x18039d127  mov     ecx, esi
0x18039d129  test    esi, esi
0x18039d12b  jz      loc_18039D3EF
0x18039d131  sub     ecx, 1
0x18039d134  jz      loc_18039D3CF
0x18039d13a  sub     ecx, 1
0x18039d13d  jz      loc_18039D32E
0x18039d143  sub     ecx, 1
  ... truncated ...
```
