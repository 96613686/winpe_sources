# pCompareFiles(UnBCL::String *,RETRIEVAL_POINTERS_BUFFER *,ulong,USN_RECORD_V2 *,ulong,UnBCL::String *,RETRIEVAL_POINTERS_BUFFER *,ulong,USN_RECORD_V2 *,ulong,uchar *,ulong,ulong,int,int,int,int,int,int *)

- ea: `0x18002fd88`
- end: `0x180030edb`
- name: `?pCompareFiles@@YAJPEAVString@UnBCL@@PEAURETRIEVAL_POINTERS_BUFFER@@KPEAUUSN_RECORD_V2@@K01K2KPEAEKKHHHHHPEAH@Z`
- size: `4435`
- prototype: `__int64 __fastcall(struct UnBCL::String *, struct RETRIEVAL_POINTERS_BUFFER *, DWORD, struct USN_RECORD_V2 *, DWORD, struct UnBCL::String *, struct RETRIEVAL_POINTERS_BUFFER *, DWORD, struct USN_RECORD_V2 *, DWORD, unsigned __int8 *, unsigned int, unsigned int, int, int, int, int, int, int *)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, reparse_path, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18002fd88`
- `0x180030ef0`

## callees

- `0x180009e04`
- `0x18002fd88`
- `0x180033ff4`
- `0x180035ca0`
- `0x180036418`
- `0x1800502b6`
- `0x180050300`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18003031d`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18003033f`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180030396`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18003031d`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18003033f`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180030396`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002fe65`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002ff5f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002fe65`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002ff5f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003015e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800302cd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800304f9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180030650`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180030e29`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180030e46`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180030e61`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180030e7f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003015e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800302cd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800304f9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180030650`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180030e29`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180030e46`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180030e61`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180030e7f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180030175`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800302de`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180030511`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003065e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180030175`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800302de`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180030511`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003065e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180030e37`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180030e54`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180030e70`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180030e8d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180030e37`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180030e54`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180030e70`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180030e8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fe79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fe91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002feba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ff76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ff8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ffb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800300d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800301c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800303a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800303c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030402`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030532`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003054a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003056e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800305dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800306b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800306cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800306f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030798`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800307b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800307d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030977`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030a2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030d47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fe79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fe91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002feba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ff76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ff8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ffb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800300d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800301c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800303a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800303c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030402`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030532`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003054a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003056e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800305dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800306b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800306cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800306f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030798`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800307b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800307d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030977`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030a2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030d47`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030e97`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030eaa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030e97`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030eaa`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800306a9`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18003078a`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800306a9`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18003078a`
- `WDSCORE!CurrentIP` at `0x18002fec2`
- `WDSCORE!CurrentIP` at `0x18002ffbf`
- `WDSCORE!CurrentIP` at `0x1800300d9`
- `WDSCORE!CurrentIP` at `0x1800301cd`
- `WDSCORE!CurrentIP` at `0x18003040a`
- `WDSCORE!CurrentIP` at `0x180030576`
- `WDSCORE!CurrentIP` at `0x1800305e4`
- `WDSCORE!CurrentIP` at `0x180030700`
- `WDSCORE!CurrentIP` at `0x1800307e1`
- `WDSCORE!CurrentIP` at `0x18003097f`
- `WDSCORE!CurrentIP` at `0x180030a32`
- `WDSCORE!CurrentIP` at `0x180030d4f`
- `WDSCORE!CurrentIP` at `0x18002fec2`
- `WDSCORE!CurrentIP` at `0x18002ffbf`
- `WDSCORE!CurrentIP` at `0x1800300d9`
- `WDSCORE!CurrentIP` at `0x1800301cd`
- `WDSCORE!CurrentIP` at `0x18003040a`
- `WDSCORE!CurrentIP` at `0x180030576`
- `WDSCORE!CurrentIP` at `0x1800305e4`
- `WDSCORE!CurrentIP` at `0x180030700`
- `WDSCORE!CurrentIP` at `0x1800307e1`
- `WDSCORE!CurrentIP` at `0x18003097f`
- `WDSCORE!CurrentIP` at `0x180030a32`
- `WDSCORE!CurrentIP` at `0x180030d4f`
- `WDSCORE!WdsSetupLogMessageW` at `0x18002ff2e`
- `WDSCORE!WdsSetupLogMessageW` at `0x18003002a`
- `WDSCORE!WdsSetupLogMessageW` at `0x18003013a`
- `WDSCORE!WdsSetupLogMessageW` at `0x180030472`
- `WDSCORE!WdsSetupLogMessageW` at `0x180030645`
- `WDSCORE!WdsSetupLogMessageW` at `0x180030754`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800309e0`
- `WDSCORE!WdsSetupLogMessageW` at `0x180030dd4`
- `WDSCORE!WdsSetupLogMessageW` at `0x18002ff2e`
- `WDSCORE!WdsSetupLogMessageW` at `0x18003002a`
- `WDSCORE!WdsSetupLogMessageW` at `0x18003013a`
- `WDSCORE!WdsSetupLogMessageW` at `0x180030472`
- `WDSCORE!WdsSetupLogMessageW` at `0x180030645`
- `WDSCORE!WdsSetupLogMessageW` at `0x180030754`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800309e0`
- `WDSCORE!WdsSetupLogMessageW` at `0x180030dd4`
- `unbcl!?get_P@?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@2@XZ` at `0x18003093c`
- `unbcl!?get_P@?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@2@XZ` at `0x180030a05`
- `unbcl!?get_P@?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@2@XZ` at `0x18003093c`
- `unbcl!?get_P@?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@2@XZ` at `0x180030a05`
- `unbcl!??0?$ArrayList@PEAVString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x18003089a`
- `unbcl!??0?$ArrayList@PEAVString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x1800308f6`
- `unbcl!??0?$ArrayList@PEAVString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x18003089a`
- `unbcl!??0?$ArrayList@PEAVString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x1800308f6`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18003087c`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1800308de`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18003087c`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1800308de`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18002fe38`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18002fecf`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18002ff3c`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18002ffcb`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800300e5`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800301da`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180030417`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180030424`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180030583`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800305f1`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18003098c`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180030a3f`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180030b7e`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180030bb2`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180030bfd`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180030c0a`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180030c55`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180030c62`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180030d65`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180030d7b`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18002fe38`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18002fecf`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18002ff3c`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18002ffcb`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800300e5`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800301da`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180030417`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180030424`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180030583`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800305f1`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18003098c`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180030a3f`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180030b7e`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180030bb2`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180030bfd`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180030c0a`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180030c55`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180030c62`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180030d65`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180030d7b`
- `unbcl!?Compare@String@UnBCL@@SAHPEBG0H@Z` at `0x180030bc4`
- `unbcl!?Compare@String@UnBCL@@SAHPEBG0H@Z` at `0x180030bc4`
- `unbcl!?Concat@String@UnBCL@@SAPEAV12@PEBG0@Z` at `0x180030c16`
- `unbcl!?Concat@String@UnBCL@@SAPEAV12@PEBG0@Z` at `0x180030c6e`
- `unbcl!?Concat@String@UnBCL@@SAPEAV12@PEBG0@Z` at `0x180030c16`
- `unbcl!?Concat@String@UnBCL@@SAPEAV12@PEBG0@Z` at `0x180030c6e`
- `unbcl!??0?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$ArrayList@PEAVString@UnBCL@@@1@@Z` at `0x1800308b6`
- `unbcl!??0?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$ArrayList@PEAVString@UnBCL@@@1@@Z` at `0x180030912`
- `unbcl!??0?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$ArrayList@PEAVString@UnBCL@@@1@@Z` at `0x1800308b6`
- `unbcl!??0?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$ArrayList@PEAVString@UnBCL@@@1@@Z` at `0x180030912`

## string_xrefs

- `0x18002ff0b`: `base\diagnosis\srt\pitr\dll\src\restore.cpp`
- `0x180030007`: `base\diagnosis\srt\pitr\dll\src\restore.cpp`
- `0x180030053`: `base\diagnosis\srt\pitr\dll\src\restore.cpp`
- `0x18002fedb`: `VERBOSE: Failed to open source file: %s. Error: 0x%08X`
- `0x18002ffd7`: `VERBOSE: Failed to open target file: %s. Error: 0x%08X`
- `0x1800305fd`: `VERBOSE: Failed to read from source file: %s. Error: 0x%08X`
- `0x18003058f`: `VERBOSE: Failed to read from target file: %s. Error: 0x%08X`
- `0x18003070c`: `VERBOSE: Failed to get reparse data for file object 1. Error: 0x%08X`
- `0x1800307ed`: `VERBOSE: Failed to get reparse data for file object 2. Error: 0x%08X`
- `0x180030d8c`: `VERBOSE: Failed to compare streams: %s | %s. Error: 0x%08X`
- `0x18002feff`: `pCompareFiles`
- `0x18002fffb`: `pCompareFiles`
- `0x18003004c`: `pCompareFiles`
- `0x180030430`: `Found false positive content comparison for %s - %s, retrying in verbose mode`

## pseudocode

```c
__int64 __fastcall pCompareFiles(
        struct UnBCL::String *a1,
        struct RETRIEVAL_POINTERS_BUFFER *a2,
        DWORD a3,
        struct USN_RECORD_V2 *a4,
        DWORD a5,
        struct UnBCL::String *a6,
        struct RETRIEVAL_POINTERS_BUFFER *a7,
        DWORD a8,
        struct USN_RECORD_V2 *a9,
        DWORD a10,
        unsigned __int8 *a11,
        unsigned int a12,
        unsigned int a13,
        int a14,
        int a15,
        int a16,
        int a17,
        int a18,
        int *a19)
{
  DWORD v20; // ebx
  const WCHAR *CString; // rax
  signed int LastError; // eax
  bool v23; // sf
  signed int v24; // eax
  int StreamLabels; // r14d
  DWORD v26; // edi
  __int64 v27; // rbx
  const char *v28; // rax
  struct tagLOG_PARTIAL_MSG *v29; // rax
  const WCHAR *v30; // rax
  HANDLE FileW; // rbx
  signed int v32; // eax
  bool v33; // sf
  signed int v34; // eax
  DWORD v35; // edi
  __int64 v36; // rbx
  const char *v37; // rax
  struct tagLOG_PARTIAL_MSG *v38; // rax
  DWORD v39; // esi
  int v40; // eax
  int v41; // edi
  DWORD v42; // edi
  __int64 v43; // rbx
  const char *v44; // rax
  struct tagLOG_PARTIAL_MSG *v45; // rax
  HANDLE v46; // rax
  int v47; // r14d
  DWORD v48; // edi
  __int64 v49; // rbx
  const char *v50; // rax
  struct tagLOG_PARTIAL_MSG *v51; // rax
  __int64 v52; // rax
  __int64 v53; // rdx
  __int64 v54; // rax
  __int64 v55; // r9
  HANDLE v56; // rax
  int v57; // r14d
  BOOL v58; // eax
  DWORD v59; // ebx
  signed int v60; // eax
  bool v61; // sf
  signed int v62; // eax
  DWORD v63; // esi
  __int64 v64; // rdi
  const char *v65; // rbx
  const char *v66; // rax
  struct tagLOG_PARTIAL_MSG *v67; // rax
  __int64 v68; // rcx
  __int64 v69; // rax
  __int64 v70; // rdx
  __int64 v71; // r9
  HANDLE ProcessHeap; // rax
  void *v73; // rsi
  signed int v74; // eax
  bool v75; // sf
  signed int v76; // eax
  DWORD v77; // edi
  __int64 v78; // rbx
  const char *v79; // rax
  struct tagLOG_PARTIAL_MSG *v80; // rax
  DWORD v81; // edi
  __int64 v82; // rbx
  const char *v83; // rax
  struct tagLOG_PARTIAL_MSG *v84; // rax
  HANDLE v85; // rax
  void *v86; // rbx
  signed int v87; // eax
  bool v88; // sf
  signed int v89; // eax
  DWORD v90; // edi
  __int64 v91; // rbx
  struct tagLOG_PARTIAL_MSG *v92; // rax
  void *v93; // rdi
  signed int v94; // eax
  bool v95; // sf
  signed int v96; // eax
  DWORD v97; // edi
  __int64 v98; // rbx
  struct tagLOG_PARTIAL_MSG *v99; // rax
  unsigned __int8 *v100; // rax
  unsigned __int8 *v101; // rbx
  __int64 v102; // rax
  unsigned __int8 *v103; // rax
  unsigned __int8 *v104; // rbx
  __int64 v105; // rax
  __int64 P; // rax
  DWORD v107; // edi
  __int64 v108; // rbx
  const char *v109; // rax
  struct tagLOG_PARTIAL_MSG *v110; // rax
  __int64 v111; // rax
  int v112; // eax
  DWORD v113; // edi
  __int64 v114; // rbx
  const char *v115; // rax
  struct tagLOG_PARTIAL_MSG *v116; // rax
  __int64 v117; // rdi
  __int64 v118; // rax
  __int64 (__fastcall ***v119)(_QWORD); // rcx
  int v120; // ebx
  unsigned int (__fastcall ***v121)(_QWORD); // rcx
  __int64 v122; // rax
  __int64 v123; // rax
  DWORD i; // ebx
  __int64 v125; // rax
  int (__fastcall ***v126)(_QWORD); // rcx
  __int64 v127; // rax
  __int64 v128; // rcx
  UnBCL::String **v129; // rax
  const unsigned __int16 *v130; // rbx
  __int64 v131; // rax
  __int64 v132; // rcx
  UnBCL::String **v133; // rax
  const unsigned __int16 *v134; // rax
  __int64 v135; // rax
  __int64 v136; // rcx
  UnBCL::String **v137; // rax
  const unsigned __int16 *v138; // rbx
  const unsigned __int16 *v139; // rax
  struct UnBCL::String *v140; // rax
  __int64 v141; // rax
  __int64 v142; // rcx
  UnBCL::String **v143; // rax
  const unsigned __int16 *v144; // rbx
  const unsigned __int16 *v145; // rax
  struct UnBCL::String *v146; // rax
  struct UnBCL::String *v147; // rbx
  struct UnBCL::String *v148; // rax
  DWORD v149; // esi
  __int64 v150; // rdi
  UnBCL::String *v151; // rax
  const char *v152; // rbx
  UnBCL::String *v153; // rax
  const char *v154; // rax
  struct tagLOG_PARTIAL_MSG *v155; // rax
  HANDLE v156; // rax
  HANDLE v157; // rax
  HANDLE v158; // rax
  HANDLE v159; // rax
  int v161; // [rsp+A0h] [rbp-80h]
  HANDLE hDevice; // [rsp+A8h] [rbp-78h]
  void *lpBuffer; // [rsp+B0h] [rbp-70h]
  HANDLE hFile; // [rsp+B8h] [rbp-68h]
  int v165; // [rsp+C0h] [rbp-60h]
  void *Buf2; // [rsp+E0h] [rbp-40h]
  void *v168; // [rsp+E8h] [rbp-38h]
  void *lpMem; // [rsp+F0h] [rbp-30h]
  DWORD FileContentInfo; // [rsp+100h] [rbp-20h] BYREF
  DWORD NumberOfBytesRead; // [rsp+104h] [rbp-1Ch] BYREF
  struct USN_RECORD_V2 *v172[2]; // [rsp+108h] [rbp-18h] BYREF
  struct USN_RECORD_V2 *v173[2]; // [rsp+118h] [rbp-8h] BYREF
  DWORD BytesReturned; // [rsp+128h] [rbp+8h] BYREF
  DWORD v175; // [rsp+12Ch] [rbp+Ch] BYREF
  unsigned __int8 *v176[2]; // [rsp+130h] [rbp+10h] BYREF
  struct RETRIEVAL_POINTERS_BUFFER *lpOutBuffer[2]; // [rsp+140h] [rbp+20h] BYREF

  v173[0] = a4;
  FileContentInfo = a3;
  lpOutBuffer[0] = a2;
  v172[0] = a9;
  v176[0] = a11;
  BytesReturned = 0;
  v175 = 0;
  if ( !a1 || !a6 || !a19 )
    return (unsigned int)-2147024809;
  v20 = a14 != 0 ? 128 : 0x80000000;
  CString = UnBCL::String::get_CString(a1);
  hFile = CreateFileW(CString, v20, 1u, 0, 3u, 0xA200000u, 0);
  if ( hFile == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v23 = LastError < 0;
    if ( LastError > 0 )
      v23 = 1;
    if ( v23 )
    {
      v24 = GetLastError();
      StreamLabels = v24;
      if ( v24 > 0 )
        StreamLabels = (unsigned __int16)v24 | 0x80070000;
    }
    else
    {
      StreamLabels = -2147467259;
    }
    if ( a18 )
    {
      v26 = GetLastError();
      v27 = CurrentIP();
      v28 = (const char *)UnBCL::String::get_CString(a1);
      v29 = ConstructPartialMsgW(50331648, "VERBOSE: Failed to open source file: %s. Error: 0x%08X", v28, StreamLabels);
      WdsSetupLogMessageW(
        v29,
        0,
        L"D",
        0,
        1613,
        L"base\\diagnosis\\srt\\pitr\\dll\\src\\restore.cpp",
        L"pCompareFiles",
        v27,
        v26,
        0,
        0);
    }
    return (unsigned int)StreamLabels;
  }
  v30 = UnBCL::String::get_CString(a6);
  FileW = CreateFileW(v30, v20, 1u, 0, 3u, 0xA200000u, 0);
  hDevice = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    v32 = GetLastError();
    v33 = v32 < 0;
    if ( v32 > 0 )
      v33 = 1;
    if ( v33 )
    {
      v34 = GetLastError();
      StreamLabels = v34;
      if ( v34 > 0 )
        StreamLabels = (unsigned __int16)v34 | 0x80070000;
    }
    else
    {
      StreamLabels = -2147467259;
    }
    if ( a18 )
    {
      v35 = GetLastError();
      v36 = CurrentIP();
      v37 = (const char *)UnBCL::String::get_CString(a6);
      v38 = ConstructPartialMsgW(50331648, "VERBOSE: Failed to open target file: %s. Error: 0x%08X", v37, StreamLabels);
      WdsSetupLogMessageW(
        v38,
        0,
        L"D",
        0,
        1632,
        L"base\\diagnosis\\srt\\pitr\\dll\\src\\restore.cpp",
        L"pCompareFiles",
        v36,
        v35,
        0,
        0);
    }
    goto LABEL_156;
  }
  lpBuffer = 0;
  Buf2 = 0;
  v168 = 0;
  lpMem = 0;
  v39 = 1;
  v165 = 0;
  if ( a14 )
  {
LABEL_73:
    if ( a15 )
    {
      ProcessHeap = GetProcessHeap();
      v73 = HeapAlloc(ProcessHeap, 8u, 0x4000u);
      v168 = v73;
      if ( !v73 )
      {
        StreamLabels = -2147024888;
        goto LABEL_152;
      }
      v85 = GetProcessHeap();
      v86 = HeapAlloc(v85, 8u, 0x4000u);
      lpMem = v86;
      if ( !v86 )
      {
        StreamLabels = -2147024888;
LABEL_149:
        v156 = GetProcessHeap();
        HeapFree(v156, 0, v73);
LABEL_150:
        if ( lpMem )
        {
          v157 = GetProcessHeap();
          HeapFree(v157, 0, lpMem);
        }
LABEL_152:
        if ( !lpBuffer )
          goto LABEL_154;
        goto LABEL_153;
      }
      if ( !DeviceIoControl(hFile, 0x900A8u, 0, 0, v73, 0x4000u, &BytesReturned, 0) )
      {
        v87 = GetLastError();
        v88 = v87 < 0;
        if ( v87 > 0 )
          v88 = 1;
        if ( v88 )
        {
          v89 = GetLastError();
          StreamLabels = v89;
          if ( v89 > 0 )
            StreamLabels = (unsigned __int16)v89 | 0x80070000;
        }
        else
        {
          StreamLabels = -2147467259;
        }
        if ( a18 )
        {
          v90 = GetLastError();
          v91 = CurrentIP();
          v92 = ConstructPartialMsgW(
                  50331648,
                  "VERBOSE: Failed to get reparse data for file object 1. Error: 0x%08X",
                  StreamLabels);
          WdsSetupLogMessageW(
            v92,
            0,
            L"D",
            0,
            1825,
            L"base\\diagnosis\\srt\\pitr\\dll\\src\\restore.cpp",
            L"pCompareFiles",
            v91,
            v90,
            0,
            0);
        }
        goto LABEL_149;
      }
      v93 = hDevice;
      if ( !DeviceIoControl(hDevice, 0x900A8u, 0, 0, v86, 0x4000u, &v175, 0) )
      {
        v94 = GetLastError();
        v95 = v94 < 0;
        if ( v94 > 0 )
          v95 = 1;
        if ( v95 )
        {
          v96 = GetLastError();
          StreamLabels = v96;
          if ( v96 > 0 )
            StreamLabels = (unsigned __int16)v96 | 0x80070000;
        }
        else
        {
          StreamLabels = -2147467259;
        }
        if ( a18 )
        {
          v97 = GetLastError();
          v98 = CurrentIP();
          v99 = ConstructPartialMsgW(
                  50331648,
                  "VERBOSE: Failed to get reparse data for file object 2. Error: 0x%08X",
                  StreamLabels);
          WdsSetupLogMessageW(
            v99,
            0,
            L"D",
            0,
            1844,
            L"base\\diagnosis\\srt\\pitr\\dll\\src\\restore.cpp",
            L"pCompareFiles",
            v98,
            v97,
            0,
            0);
        }
        goto LABEL_149;
      }
      if ( BytesReturned != v175 || memcmp_0(v73, v86, BytesReturned) )
      {
        v39 = 0;
        StreamLabels = 0;
        goto LABEL_146;
      }
      v39 = 1;
      StreamLabels = 0;
      goto LABEL_115;
    }
LABEL_113:
    StreamLabels = 0;
    if ( !v39 )
      goto LABEL_146;
    v93 = hDevice;
LABEL_115:
    if ( a16 )
    {
      v100 = (unsigned __int8 *)UnBCL::Object::operator new(0xB0u);
      v101 = v100;
      v176[0] = v100;
      if ( v100 )
      {
        UnBCL::ArrayList<UnBCL::String *>::ArrayList<UnBCL::String *>(v100, 1);
        *((_QWORD *)v101 + 6) = UnBCL::ArrayList<UnBCL::String *>::`local vftable'{for `UnBCL::Object'};
      }
      else
      {
        v101 = 0;
      }
      UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(v172, v101);
      v102 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v172);
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v102 + 40LL))(v102, 1);
      v103 = (unsigned __int8 *)UnBCL::Object::operator new(0xB0u);
      v104 = v103;
      v176[0] = v103;
      if ( v103 )
      {
        UnBCL::ArrayList<UnBCL::String *>::ArrayList<UnBCL::String *>(v103, 1);
        *((_QWORD *)v104 + 6) = UnBCL::ArrayList<UnBCL::String *>::`local vftable'{for `UnBCL::Object'};
      }
      else
      {
        v104 = 0;
      }
      UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(v173, v104);
      v105 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v173);
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v105 + 40LL))(v105, 1);
      P = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::get_P(v172);
      StreamLabels = GetStreamLabels(hFile, P);
      if ( (int)(StreamLabels + 0x80000000) >= 0 && StreamLabels != -2147024858 )
      {
        if ( a18 )
        {
          v107 = GetLastError();
          v108 = CurrentIP();
          v109 = (const char *)UnBCL::String::get_CString(a1);
          v110 = ConstructPartialMsgW(
                   50331648,
                   "VERBOSE: Failed to get streams for %s, error: 0x%08X",
                   v109,
                   StreamLabels);
          WdsSetupLogMessageW(
            v110,
            0,
            L"D",
            0,
            1867,
            L"base\\diagnosis\\srt\\pitr\\dll\\src\\restore.cpp",
            L"pCompareFiles",
            v108,
            v107,
            0,
            0);
        }
LABEL_126:
        UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::~SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(v173);
        UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::~SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(v172);
        goto LABEL_148;
      }
      v111 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::get_P(v173);
      v112 = GetStreamLabels(v93, v111);
      StreamLabels = v112;
      if ( v112 < 0 )
      {
        if ( v112 != -2147024858 )
        {
          if ( a18 )
          {
            v113 = GetLastError();
            v114 = CurrentIP();
            v115 = (const char *)UnBCL::String::get_CString(a6);
            v116 = ConstructPartialMsgW(
                     50331648,
                     "VERBOSE: Failed to get streams for %s, error: 0x%08X",
                     v115,
                     StreamLabels);
            WdsSetupLogMessageW(
              v116,
              0,
              L"D",
              0,
              1881,
              L"base\\diagnosis\\srt\\pitr\\dll\\src\\restore.cpp",
              L"pCompareFiles",
              v114,
              v113,
              0,
              0);
          }
          goto LABEL_126;
        }
        StreamLabels = 0;
      }
      v117 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v172);
      v118 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v173);
      v119 = (__int64 (__fastcall ***)(_QWORD))(*(int *)(*(_QWORD *)(v118 + 8) + 12LL) + v118 + 8);
      v120 = (**v119)(v119);
      v121 = (unsigned int (__fastcall ***)(_QWORD))(v117 + *(int *)(*(_QWORD *)(v117 + 8) + 12LL) + 8LL);
      if ( (**v121)(v121) == v120 )
      {
        v122 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v172);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v122 + 88LL))(v122);
        v123 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v173);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v123 + 88LL))(v123);
        for ( i = 0; ; i = NumberOfBytesRead + 1 )
        {
          NumberOfBytesRead = i;
          v125 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v172);
          v126 = (int (__fastcall ***)(_QWORD))(*(int *)(*(_QWORD *)(v125 + 8) + 12LL) + v125 + 8);
          if ( (int)i >= (**v126)(v126) )
            goto LABEL_145;
          v127 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v173);
          v128 = *(int *)(*(_QWORD *)(v127 + 8) + 16LL) + v127 + 8;
          v129 = (UnBCL::String **)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v128 + 24LL))(v128, i);
          v130 = UnBCL::String::get_CString(*v129);
          v131 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v172);
          v132 = *(int *)(*(_QWORD *)(v131 + 8) + 16LL) + v131 + 8;
          v133 = (UnBCL::String **)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v132 + 24LL))(
                                     v132,
                                     NumberOfBytesRead);
          v134 = UnBCL::String::get_CString(*v133);
          if ( UnBCL::String::Compare(v134, v130, 1) )
            goto LABEL_144;
          v135 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v172);
          v136 = *(int *)(*(_QWORD *)(v135 + 8) + 16LL) + v135 + 8;
          v137 = (UnBCL::String **)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v136 + 24LL))(
                                     v136,
                                     NumberOfBytesRead);
          v138 = UnBCL::String::get_CString(*v137);
          v139 = UnBCL::String::get_CString(a1);
          v140 = UnBCL::String::Concat(v139, v138);
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(lpOutBuffer, v140);
          v141 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v173);
          v142 = *(int *)(*(_QWORD *)(v141 + 8) + 16LL) + v141 + 8;
          v143 = (UnBCL::String **)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v142 + 24LL))(
                                     v142,
                                     NumberOfBytesRead);
          v144 = UnBCL::String::get_CString(*v143);
          v145 = UnBCL::String::get_CString(a6);
          v146 = UnBCL::String::Concat(v145, v144);
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v176, v146);
          FileContentInfo = 0;
          v147 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v176);
          v148 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(lpOutBuffer);
          StreamLabels = pCompareFiles(
                           v148,
                           0,
                           0,
                           0,
                           0,
                           v147,
                           0,
                           0,
                           0,
                           0,
                           0,
                           0,
                           0,
                           0,
                           0,
                           0,
                           a17,
                           a18,
                           (int *)&FileContentInfo);
          if ( StreamLabels < 0 )
            break;
          if ( !FileContentInfo )
          {
            v39 = 0;
LABEL_143:
            UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v176);
            UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(lpOutBuffer);
            goto LABEL_145;
          }
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v176);
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(lpOutBuffer);
        }
        if ( a18 )
        {
          v149 = GetLastError();
          v150 = CurrentIP();
          v151 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v176);
          v152 = (const char *)UnBCL::String::get_CString(v151);
          v153 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(lpOutBuffer);
          v154 = (const char *)UnBCL::String::get_CString(v153);
          v155 = ConstructPartialMsgW(
                   50331648,
                   "VERBOSE: Failed to compare streams: %s | %s. Error: 0x%08X",
                   v154,
                   v152,
                   StreamLabels);
          WdsSetupLogMessageW(
            v155,
            0,
            L"D",
            0,
            1931,
            L"base\\diagnosis\\srt\\pitr\\dll\\src\\restore.cpp",
            L"pCompareFiles",
            v150,
            v149,
            0,
            0);
        }
        v39 = 0;
        StreamLabels = 0;
        goto LABEL_143;
      }
LABEL_144:
      v39 = 0;
LABEL_145:
      UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::~SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(v173);
      UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::~SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(v172);
    }
LABEL_146:
    *a19 = v39;
    if ( v165 )
      StreamLabels = -2147019873;
LABEL_148:
    v73 = v168;
    if ( !v168 )
      goto LABEL_150;
    goto LABEL_149;
  }
  v40 = 0;
  v161 = 0;
  if ( !lpOutBuffer[0] || !v173[0] || !a7 )
  {
    v41 = a18;
    goto LABEL_33;
  }
  if ( !v172[0] )
  {
    v41 = a18;
    goto LABEL_33;
  }
  FileContentInfo = GetFileContentInfo(hFile, lpOutBuffer[0], FileContentInfo, v173[0], a5);
  if ( (FileContentInfo & 0x80000000) != 0 )
  {
    v41 = a18;
    if ( !a18 )
    {
LABEL_31:
      FileW = hDevice;
      goto LABEL_32;
    }
    v42 = GetLastError();
    v43 = CurrentIP();
    v44 = (const char *)UnBCL::String::get_CString(a1);
    v45 = ConstructPartialMsgW(0x2000000, "Failed to get content info for %s. Error: 0x%08X", v44, FileContentInfo);
    WdsSetupLogMessageW(
      v45,
      0,
      L"D",
      0,
      1660,
      L"base\\diagnosis\\srt\\pitr\\dll\\src\\restore.cpp",
      L"pCompareFiles",
      v43,
      v42,
      0,
      0);
LABEL_30:
    v41 = a18;
    goto LABEL_31;
  }
  v47 = GetFileContentInfo(FileW, a7, a8, v172[0], a10);
  if ( v47 < 0 )
  {
    v41 = a18;
    if ( !a18 )
      goto LABEL_31;
    v48 = GetLastError();
    v49 = CurrentIP();
    v50 = (const char *)UnBCL::String::get_CString(a6);
    v51 = ConstructPartialMsgW(0x2000000, "Failed to get content info for %s. Error: 0x%08X", v50, v47);
    WdsSetupLogMessageW(
      v51,
      0,
      L"D",
      0,
      1676,
      L"base\\diagnosis\\srt\\pitr\\dll\\src\\restore.cpp",
      L"pCompareFiles",
      v49,
      v48,
      0,
      0);
    goto LABEL_30;
  }
  v52 = 24;
  if ( v173[0]->MajorVersion != 2 )
    v52 = 40;
  v53 = *(_QWORD *)((char *)&v173[0]->RecordLength + v52);
  v54 = 24;
  if ( v172[0]->MajorVersion != 2 )
    v54 = 40;
  v55 = *(_QWORD *)((char *)&v172[0]->RecordLength + v54);
  FileContentInfo = 0;
  v41 = a18;
  if ( (int)pQuickContentCompare(lpOutBuffer[0], v53, a7, v55, v176[0], a12, a13, 0, (int *)&FileContentInfo) >= 0 )
  {
    v39 = FileContentInfo;
    v40 = 1;
    v161 = 1;
    goto LABEL_33;
  }
LABEL_32:
  v40 = 0;
LABEL_33:
  if ( !a17 && v40 )
  {
LABEL_72:
    if ( !v39 )
      goto LABEL_113;
    goto LABEL_73;
  }
  v46 = GetProcessHeap();
  lpBuffer = HeapAlloc(v46, 8u, 0x4000u);
  if ( lpBuffer )
  {
    v56 = GetProcessHeap();
    Buf2 = HeapAlloc(v56, 8u, 0x4000u);
    if ( Buf2 )
    {
      v57 = 1;
      NumberOfBytesRead = 0;
      FileContentInfo = 0;
      v58 = ReadFile(hFile, lpBuffer, 0x4000u, &NumberOfBytesRead, 0);
      while ( 1 )
      {
        if ( !v58 )
        {
          v60 = GetLastError();
          v61 = v60 < 0;
          if ( v60 > 0 )
            v61 = 1;
          if ( v61 )
          {
            v62 = GetLastError();
            StreamLabels = v62;
            if ( v62 > 0 )
              StreamLabels = (unsigned __int16)v62 | 0x80070000;
          }
          else
          {
            StreamLabels = -2147467259;
          }
          if ( v41 )
          {
            v81 = GetLastError();
            v82 = CurrentIP();
            v83 = (const char *)UnBCL::String::get_CString(a1);
            v84 = ConstructPartialMsgW(
                    50331648,
                    "VERBOSE: Failed to read from source file: %s. Error: 0x%08X",
                    v83,
                    StreamLabels);
            WdsSetupLogMessageW(
              v84,
              0,
              L"D",
              0,
              1734,
              L"base\\diagnosis\\srt\\pitr\\dll\\src\\restore.cpp",
              L"pCompareFiles",
              v82,
              v81,
              0,
              0);
          }
          goto LABEL_153;
        }
        if ( !ReadFile(FileW, Buf2, 0x4000u, &FileContentInfo, 0) )
          break;
        v59 = NumberOfBytesRead;
        if ( NumberOfBytesRead != FileContentInfo || memcmp_0(lpBuffer, Buf2, NumberOfBytesRead) )
        {
          v57 = 0;
LABEL_63:
          if ( v161 && v39 && !v57 )
          {
            v165 = 1;
            v63 = GetLastError();
            v64 = CurrentIP();
            v65 = (const char *)UnBCL::String::get_CString(a6);
            v66 = (const char *)UnBCL::String::get_CString(a1);
            v67 = ConstructPartialMsgW(
                    0x2000000,
                    "Found false positive content comparison for %s - %s, retrying in verbose mode",
                    v66,
                    v65);
            WdsSetupLogMessageW(
              v67,
              0,
              L"D",
              0,
              1774,
              L"base\\diagnosis\\srt\\pitr\\dll\\src\\restore.cpp",
              L"pCompareFiles",
              v64,
              v63,
              0,
              0);
            v68 = 24;
            v69 = 24;
            if ( v173[0]->MajorVersion != 2 )
              v69 = 40;
            v70 = *(_QWORD *)((char *)&v173[0]->RecordLength + v69);
            if ( v172[0]->MajorVersion != 2 )
              v68 = 40;
            v71 = *(_QWORD *)((char *)&v172[0]->RecordLength + v68);
            FileContentInfo = 0;
            pQuickContentCompare(lpOutBuffer[0], v70, a7, v71, v176[0], a12, a13, 1, (int *)&FileContentInfo);
          }
          v39 = v57;
          goto LABEL_72;
        }
        if ( v59 < 0x4000 )
          goto LABEL_63;
        NumberOfBytesRead = 0;
        FileContentInfo = 0;
        v58 = ReadFile(hFile, lpBuffer, 0x4000u, &NumberOfBytesRead, 0);
        FileW = hDevice;
      }
      v74 = GetLastError();
      v75 = v74 < 0;
      if ( v74 > 0 )
        v75 = 1;
      if ( v75 )
      {
        v76 = GetLastError();
        StreamLabels = v76;
        if ( v76 > 0 )
          StreamLabels = (unsigned __int16)v76 | 0x80070000;
      }
      else
      {
        StreamLabels = -2147467259;
      }
      if ( v41 )
      {
        v77 = GetLastError();
        v78 = CurrentIP();
        v79 = (const char *)UnBCL::String::get_CString(a6);
        v80 = ConstructPartialMsgW(
                50331648,
                "VERBOSE: Failed to read from target file: %s. Error: 0x%08X",
                v79,
                StreamLabels);
        WdsSetupLogMessageW(
          v80,
          0,
          L"D",
          0,
          1743,
          L"base\\diagnosis\\srt\\pitr\\dll\\src\\restore.cpp",
          L"pCompareFiles",
          v78,
          v77,
          0,
          0);
      }
    }
    else
    {
      StreamLabels = -2147024888;
    }
LABEL_153:
    v158 = GetProcessHeap();
    HeapFree(v158, 0, lpBuffer);
LABEL_154:
    if ( Buf2 )
    {
      v159 = GetProcessHeap();
      HeapFree(v159, 0, Buf2);
    }
    goto LABEL_156;
  }
  StreamLabels = -2147024888;
LABEL_156:
  CloseHandle(hFile);
  if ( hDevice != (HANDLE)-1LL )
    CloseHandle(hDevice);
  return (unsigned int)StreamLabels;
}

```

## disassembly

```asm
0x18002fd88  push    rbp
0x18002fd8a  push    rbx
0x18002fd8b  push    rsi
0x18002fd8c  push    rdi
0x18002fd8d  push    r12
0x18002fd8f  push    r13
0x18002fd91  push    r14
0x18002fd93  push    r15
0x18002fd95  lea     rbp, [rsp-48h]
0x18002fd9a  sub     rsp, 168h
0x18002fda1  mov     rax, cs:__security_cookie
0x18002fda8  xor     rax, rsp
0x18002fdab  mov     [rbp+80h+var_50], rax
0x18002fdaf  mov     [rbp+80h+var_88], r9
0x18002fdb3  mov     [rbp+80h+var_A0], r8d
0x18002fdb7  mov     [rbp+80h+lpOutBuffer], rdx
0x18002fdbb  mov     r14, rcx
0x18002fdbe  mov     [rbp+80h+var_D8], rcx
0x18002fdc2  mov     rsi, [rbp+80h+arg_28]
0x18002fdc9  mov     [rbp+80h+var_D0], rsi
0x18002fdcd  mov     rax, [rbp+80h+arg_30]
0x18002fdd4  mov     [rbp+80h+var_C8], rax
0x18002fdd8  mov     rax, [rbp+80h+arg_40]
0x18002fddf  mov     [rbp+80h+var_98], rax
0x18002fde3  mov     rax, [rbp+80h+arg_50]
0x18002fdea  mov     [rbp+80h+var_70], rax
0x18002fdee  mov     rax, [rbp+80h+arg_90]
0x18002fdf5  mov     [rbp+80h+var_A8], rax
0x18002fdf9  xor     r15d, r15d
0x18002fdfc  mov     [rbp+80h+BytesReturned], r15d
0x18002fe00  mov     [rbp+80h+var_74], r15d
0x18002fe04  test    rcx, rcx
0x18002fe07  jz      loc_180030EB2
0x18002fe0d  test    rsi, rsi
0x18002fe10  jz      loc_180030EB2
0x18002fe16  test    rax, rax
0x18002fe19  jz      loc_180030EB2
0x18002fe1f  mov     edi, [rbp+80h+arg_68]
0x18002fe25  mov     eax, edi
0x18002fe27  neg     eax
0x18002fe29  sbb     ebx, ebx
0x18002fe2b  and     ebx, 80000080h
0x18002fe31  mov     eax, 80000000h
0x18002fe36  add     ebx, eax
0x18002fe38  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18002fe3e  mov     rcx, rax; lpFileName
0x18002fe41  mov     [rsp+1A0h+hTemplateFile], r15; hTemplateFile
0x18002fe46  mov     r13d, 0A200000h
0x18002fe4c  mov     [rsp+1A0h+dwFlagsAndAttributes], r13d; dwFlagsAndAttributes
0x18002fe51  mov     [rsp+1A0h+dwCreationDisposition], 3; dwCreationDisposition
0x18002fe59  xor     r9d, r9d; lpSecurityAttributes
0x18002fe5c  lea     r12d, [r15+1]
0x18002fe60  mov     r8d, r12d; dwShareMode
0x18002fe63  mov     edx, ebx; dwDesiredAccess
0x18002fe65  call    cs:__imp_CreateFileW
0x18002fe6b  mov     [rbp+80h+hFile], rax
0x18002fe6f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002fe73  jnz     loc_18002FF39
0x18002fe79  call    cs:__imp_GetLastError
0x18002fe7f  mov     ebx, 80070000h
0x18002fe84  test    eax, eax
0x18002fe86  jle     short loc_18002FE8F
0x18002fe88  movzx   eax, ax
0x18002fe8b  or      eax, ebx
0x18002fe8d  test    eax, eax
0x18002fe8f  jns     short loc_18002FEA7
0x18002fe91  call    cs:__imp_GetLastError
0x18002fe97  mov     r14d, eax
0x18002fe9a  test    eax, eax
0x18002fe9c  jle     short loc_18002FEAD
0x18002fe9e  movzx   r14d, ax
0x18002fea2  or      r14d, ebx
0x18002fea5  jmp     short loc_18002FEAD
0x18002fea7  mov     r14d, 80004005h
0x18002fead  cmp     [rbp+80h+arg_88], r15d
0x18002feb4  jz      loc_180030EB8
0x18002feba  call    cs:__imp_GetLastError
0x18002fec0  mov     edi, eax
0x18002fec2  call    cs:__imp_CurrentIP
0x18002fec8  mov     rbx, rax
0x18002fecb  mov     rcx, [rbp+80h+var_D8]
0x18002fecf  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18002fed5  mov     r8, rax
0x18002fed8  mov     r9d, r14d
0x18002fedb  lea     rdx, aVerboseFailedT; "VERBOSE: Failed to open source file: %s"...
0x18002fee2  mov     ecx, 3000000h; unsigned int
0x18002fee7  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18002feec  mov     dword ptr [rsp+1A0h+var_150], r15d
0x18002fef1  mov     qword ptr [rsp+1A0h+var_158], r15
0x18002fef6  mov     dword ptr [rsp+1A0h+var_160], edi
0x18002fefa  mov     [rsp+1A0h+lpOverlapped], rbx
0x18002feff  lea     r12, aPcomparefiles; "pCompareFiles"
0x18002ff06  mov     [rsp+1A0h+hTemplateFile], r12
0x18002ff0b  lea     r13, aBaseDiagnosisS_3; "base\\diagnosis\\srt\\pitr\\dll\\src\\r"...
0x18002ff12  mov     qword ptr [rsp+1A0h+dwFlagsAndAttributes], r13
0x18002ff17  mov     [rsp+1A0h+dwCreationDisposition], 64Dh
0x18002ff1f  xor     r9d, r9d
0x18002ff22  lea     r8, aD; "D"
0x18002ff29  xor     edx, edx
0x18002ff2b  mov     rcx, rax
0x18002ff2e  call    cs:__imp_WdsSetupLogMessageW
0x18002ff34  jmp     loc_180030EB8
0x18002ff39  mov     rcx, rsi
0x18002ff3c  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18002ff42  mov     rcx, rax; lpFileName
0x18002ff45  mov     [rsp+1A0h+hTemplateFile], r15; hTemplateFile
0x18002ff4a  mov     [rsp+1A0h+dwFlagsAndAttributes], r13d; dwFlagsAndAttributes
0x18002ff4f  mov     [rsp+1A0h+dwCreationDisposition], 3; dwCreationDisposition
0x18002ff57  xor     r9d, r9d; lpSecurityAttributes
0x18002ff5a  mov     r8d, r12d; dwShareMode
0x18002ff5d  mov     edx, ebx; dwDesiredAccess
0x18002ff5f  call    cs:__imp_CreateFileW
0x18002ff65  mov     rbx, rax
0x18002ff68  mov     [rbp+80h+hDevice], rax
0x18002ff6c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002ff70  jnz     loc_180030035
0x18002ff76  call    cs:__imp_GetLastError
0x18002ff7c  mov     ebx, 80070000h
0x18002ff81  test    eax, eax
0x18002ff83  jle     short loc_18002FF8C
0x18002ff85  movzx   eax, ax
0x18002ff88  or      eax, ebx
0x18002ff8a  test    eax, eax
0x18002ff8c  jns     short loc_18002FFA4
0x18002ff8e  call    cs:__imp_GetLastError
0x18002ff94  mov     r14d, eax
0x18002ff97  test    eax, eax
0x18002ff99  jle     short loc_18002FFAA
0x18002ff9b  movzx   r14d, ax
0x18002ff9f  or      r14d, ebx
0x18002ffa2  jmp     short loc_18002FFAA
0x18002ffa4  mov     r14d, 80004005h
0x18002ffaa  cmp     [rbp+80h+arg_88], r15d
0x18002ffb1  jz      loc_180030E93
0x18002ffb7  call    cs:__imp_GetLastError
0x18002ffbd  mov     edi, eax
0x18002ffbf  call    cs:__imp_CurrentIP
0x18002ffc5  mov     rbx, rax
0x18002ffc8  mov     rcx, rsi
0x18002ffcb  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18002ffd1  mov     r8, rax
0x18002ffd4  mov     r9d, r14d
0x18002ffd7  lea     rdx, aVerboseFailedT_3; "VERBOSE: Failed to open target file: %s"...
0x18002ffde  mov     ecx, 3000000h; unsigned int
0x18002ffe3  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18002ffe8  mov     dword ptr [rsp+1A0h+var_150], r15d
0x18002ffed  mov     qword ptr [rsp+1A0h+var_158], r15
0x18002fff2  mov     dword ptr [rsp+1A0h+var_160], edi
0x18002fff6  mov     [rsp+1A0h+lpOverlapped], rbx
0x18002fffb  lea     r12, aPcomparefiles; "pCompareFiles"
0x180030002  mov     [rsp+1A0h+hTemplateFile], r12
0x180030007  lea     r13, aBaseDiagnosisS_3; "base\\diagnosis\\srt\\pitr\\dll\\src\\r"...
0x18003000e  mov     qword ptr [rsp+1A0h+dwFlagsAndAttributes], r13
0x180030013  mov     [rsp+1A0h+dwCreationDisposition], 660h
0x18003001b  xor     r9d, r9d
0x18003001e  lea     r8, aD; "D"
0x180030025  xor     edx, edx
0x180030027  mov     rcx, rax
0x18003002a  call    cs:__imp_WdsSetupLogMessageW
0x180030030  jmp     loc_180030E93
0x180030035  mov     [rbp+80h+lpBuffer], r15
0x180030039  mov     [rbp+80h+Buf2], r15
0x18003003d  mov     [rbp+80h+var_B8], r15
0x180030041  mov     [rbp+80h+lpMem], r15
0x180030045  mov     esi, r12d
0x180030048  mov     [rbp+80h+var_E0], r15d
0x18003004c  lea     r12, aPcomparefiles; "pCompareFiles"
0x180030053  lea     r13, aBaseDiagnosisS_3; "base\\diagnosis\\srt\\pitr\\dll\\src\\r"...
0x18003005a  lea     r15, aD; "D"
0x180030061  test    edi, edi
0x180030063  jnz     loc_1800304EC
0x180030069  xor     eax, eax
0x18003006b  mov     [rbp+80h+var_100], eax
0x18003006e  mov     rcx, [rbp+80h+lpOutBuffer]
0x180030072  test    rcx, rcx
0x180030075  jz      loc_1800302C2
0x18003007b  mov     rdi, [rbp+80h+var_88]
0x18003007f  test    rdi, rdi
0x180030082  jz      loc_1800302C2
0x180030088  cmp     [rbp+80h+var_C8], rax
0x18003008c  jz      loc_1800302C2
0x180030092  mov     rbx, [rbp+80h+var_98]
0x180030096  test    rbx, rbx
0x180030099  jz      loc_1800302B3
0x18003009f  mov     eax, [rbp+80h+arg_20]
0x1800300a5  mov     [rsp+1A0h+dwCreationDisposition], eax; unsigned int
0x1800300a9  mov     r9, rdi; struct USN_RECORD_V2 *
0x1800300ac  mov     r8d, [rbp+80h+var_A0]; unsigned int
0x1800300b0  mov     rdx, rcx; lpOutBuffer
0x1800300b3  mov     rcx, [rbp+80h+hFile]; hDevice
0x1800300b7  call    ?GetFileContentInfo@@YAJPEAXPEAURETRIEVAL_POINTERS_BUFFER@@KPEAUUSN_RECORD_V2@@K@Z; GetFileContentInfo(void *,RETRIEVAL_POINTERS_BUFFER *,ulong,USN_RECORD_V2 *,ulong)
0x1800300bc  mov     [rbp+80h+var_A0], eax
0x1800300bf  test    eax, eax
0x1800300c1  jns     loc_180030193
0x1800300c7  mov     edi, [rbp+80h+arg_88]
0x1800300cd  test    edi, edi
0x1800300cf  jz      short loc_180030146
0x1800300d1  call    cs:__imp_GetLastError
0x1800300d7  mov     edi, eax
0x1800300d9  call    cs:__imp_CurrentIP
0x1800300df  mov     rbx, rax
0x1800300e2  mov     rcx, r14
0x1800300e5  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1800300eb  mov     r8, rax
0x1800300ee  mov     r9d, [rbp+80h+var_A0]
0x1800300f2  lea     rdx, aFailedToGetCon; "Failed to get content info for %s. Erro"...
0x1800300f9  mov     ecx, 2000000h; unsigned int
0x1800300fe  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180030103  mov     dword ptr [rsp+1A0h+var_150], 0
0x18003010b  mov     qword ptr [rsp+1A0h+var_158], 0
0x180030114  mov     dword ptr [rsp+1A0h+var_160], edi
0x180030118  mov     [rsp+1A0h+lpOverlapped], rbx
0x18003011d  mov     [rsp+1A0h+hTemplateFile], r12
0x180030122  mov     qword ptr [rsp+1A0h+dwFlagsAndAttributes], r13
0x180030127  mov     [rsp+1A0h+dwCreationDisposition], 67Ch
0x18003012f  xor     r9d, r9d
0x180030132  mov     r8, r15
0x180030135  xor     edx, edx
0x180030137  mov     rcx, rax
0x18003013a  call    cs:__imp_WdsSetupLogMessageW
0x180030140  mov     edi, [rbp+80h+arg_88]
0x180030146  mov     rbx, [rbp+80h+hDevice]
0x18003014a  mov     eax, [rbp+80h+var_100]
0x18003014d  cmp     [rbp+80h+arg_80], 0
0x180030154  jnz     short loc_18003015E
0x180030156  test    eax, eax
0x180030158  jnz     loc_1800304E4
0x18003015e  call    cs:__imp_GetProcessHeap
0x180030164  mov     rcx, rax; hHeap
0x180030167  mov     r14d, 4000h
0x18003016d  mov     r8d, r14d; dwBytes
0x180030170  mov     edx, 8; dwFlags
0x180030175  call    cs:__imp_HeapAlloc
0x18003017b  mov     [rbp+80h+lpBuffer], rax
0x18003017f  test    rax, rax
0x180030182  jnz     loc_1800302CD
0x180030188  mov     r14d, 80070008h
0x18003018e  jmp     loc_180030E93
0x180030193  mov     eax, [rbp+80h+arg_48]
0x180030199  mov     [rsp+1A0h+dwCreationDisposition], eax; unsigned int
0x18003019d  mov     r9, rbx; struct USN_RECORD_V2 *
0x1800301a0  mov     r8d, [rbp+80h+arg_38]; unsigned int
0x1800301a7  mov     rdx, [rbp+80h+var_C8]; lpOutBuffer
0x1800301ab  mov     rcx, [rbp+80h+hDevice]; hDevice
0x1800301af  call    ?GetFileContentInfo@@YAJPEAXPEAURETRIEVAL_POINTERS_BUFFER@@KPEAUUSN_RECORD_V2@@K@Z; GetFileContentInfo(void *,RETRIEVAL_POINTERS_BUFFER *,ulong,USN_RECORD_V2 *,ulong)
0x1800301b4  mov     r14d, eax
0x1800301b7  test    eax, eax
0x1800301b9  jns     short loc_180030228
0x1800301bb  mov     edi, [rbp+80h+arg_88]
0x1800301c1  test    edi, edi
0x1800301c3  jz      short loc_180030146
0x1800301c5  call    cs:__imp_GetLastError
0x1800301cb  mov     edi, eax
0x1800301cd  call    cs:__imp_CurrentIP
0x1800301d3  mov     rbx, rax
0x1800301d6  mov     rcx, [rbp+80h+var_D0]
0x1800301da  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1800301e0  mov     r8, rax
0x1800301e3  mov     r9d, r14d
0x1800301e6  lea     rdx, aFailedToGetCon; "Failed to get content info for %s. Erro"...
0x1800301ed  mov     ecx, 2000000h; unsigned int
0x1800301f2  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800301f7  mov     dword ptr [rsp+1A0h+var_150], 0
0x1800301ff  mov     qword ptr [rsp+1A0h+var_158], 0
0x180030208  mov     dword ptr [rsp+1A0h+var_160], edi
0x18003020c  mov     [rsp+1A0h+lpOverlapped], rbx
0x180030211  mov     [rsp+1A0h+hTemplateFile], r12
0x180030216  mov     qword ptr [rsp+1A0h+dwFlagsAndAttributes], r13
0x18003021b  mov     [rsp+1A0h+dwCreationDisposition], 68Ch
0x180030223  jmp     loc_18003012F
0x180030228  mov     ecx, 18h
0x18003022d  mov     eax, ecx
0x18003022f  cmp     word ptr [rdi+4], 2
0x180030234  lea     r8d, [rcx+10h]
0x180030238  cmovnz  eax, r8d
0x18003023c  mov     rdx, [rax+rdi]; __int64
0x180030240  mov     eax, ecx
0x180030242  cmp     word ptr [rbx+4], 2
0x180030247  cmovnz  eax, r8d
0x18003024b  mov     r9, [rax+rbx]; __int64
0x18003024f  mov     [rbp+80h+var_A0], 0
0x180030256  lea     rax, [rbp+80h+var_A0]
0x18003025a  mov     [rsp+1A0h+var_160], rax; int *
0x18003025f  mov     dword ptr [rsp+1A0h+lpOverlapped], 0; int
0x180030267  mov     eax, [rbp+80h+arg_60]
0x18003026d  mov     dword ptr [rsp+1A0h+hTemplateFile], eax; unsigned int
0x180030271  mov     eax, [rbp+80h+arg_58]
0x180030277  mov     [rsp+1A0h+dwFlagsAndAttributes], eax; unsigned int
0x18003027b  mov     rax, [rbp+80h+var_70]
0x18003027f  mov     qword ptr [rsp+1A0h+dwCreationDisposition], rax; unsigned __int8 *
0x180030284  mov     r8, [rbp+80h+var_C8]; struct RETRIEVAL_POINTERS_BUFFER *
0x180030288  mov     rcx, [rbp+80h+lpOutBuffer]; struct RETRIEVAL_POINTERS_BUFFER *
0x18003028c  call    ?pQuickContentCompare@@YAJPEAURETRIEVAL_POINTERS_BUFFER@@_J01PEAEKKHPEAH@Z; pQuickContentCompare(RETRIEVAL_POINTERS_BUFFER *,__int64,RETRIEVAL_POINTERS_BUFFER *,__int64,uchar *,ulong,ulong,int,int *)
0x180030291  mov     edi, [rbp+80h+arg_88]
0x180030297  mov     rbx, [rbp+80h+hDevice]
0x18003029b  test    eax, eax
0x18003029d  js      loc_18003014A
0x1800302a3  mov     esi, [rbp+80h+var_A0]
0x1800302a6  mov     eax, 1
0x1800302ab  mov     [rbp+80h+var_100], eax
  ... truncated ...
```
