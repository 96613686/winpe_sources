# CApplicationManager::RpcGetProcess(void *,CProcess * *)

- ea: `0x180003c70`
- end: `0x180005d9d`
- name: `?RpcGetProcess@CApplicationManager@@QEAAJPEAXPEAPEAVCProcess@@@Z`
- size: `8493`
- prototype: `int(CApplicationManager *__hidden this, void *, struct CProcess **)`
- caller_count: `17`
- callee_count: `31`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180003180`
- `0x180003310`
- `0x180003480`
- `0x180003910`
- `0x180003b60`
- `0x180007720`
- `0x180026fe0`
- `0x180027050`
- `0x180028580`
- `0x18002e0c0`
- `0x180040a60`
- `0x180040be0`
- `0x180040ce0`
- `0x180040df0`
- `0x180040e60`
- `0x180040fe0`
- `0x180041120`

## callees

- `0x180002ebc`
- `0x180002fd4`
- `0x180003c70`
- `0x180005da4`
- `0x180005f14`
- `0x1800061f8`
- `0x1800062fc`
- `0x180006624`
- `0x180006990`
- `0x1800088a0`
- `0x1800088d0`
- `0x180008950`
- `0x18000a080`
- `0x18000a384`
- `0x18000d328`
- `0x18000f040`
- `0x18000f5f4`
- `0x180012844`
- `0x180019ff0`
- `0x18001d8a0`
- `0x18002acfc`
- `0x18002b1f4`
- `0x18002d2e4`
- `0x18002d6a0`
- `0x18002ea54`
- `0x1800309a4`
- `0x180031960`
- `0x180031eb0`
- `0x1800327f8`
- `0x18003c9c4`
- `0x18003cfec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003dba`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003dba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800041f4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004acf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004b96`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004c7f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004e41`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004fd2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005121`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005193`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005257`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800052d5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800041f4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004acf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004b96`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004c7f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004e41`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004fd2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005121`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005193`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005257`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800052d5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004c9d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004c9d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800048d7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800048d7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180003d53`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180003e4f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180003d53`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180003e4f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180003d00`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180003dfb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180003d00`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180003dfb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005a79`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005c1c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005a79`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005c1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800042f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800045dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000464e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000469c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005993`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005c09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800042f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800045dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000464e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000469c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005993`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005c09`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180004d8f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180004d8f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180003ea5`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180003ea5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180003e89`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180003e89`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800042a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005a3b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005a71`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005a8c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005a9a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005c69`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005c77`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005c82`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005c8d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005c9b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005ca6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005cbb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005cc6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005cd1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005d18`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005d23`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005d2e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005d39`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005d44`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005d4f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005d5a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005d65`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005d70`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005d7b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005d86`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005d91`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800042a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005a3b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005a71`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005a8c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005a9a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005c69`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005c77`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005c82`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005c8d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005c9b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005ca6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005cbb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005cc6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005cd1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005d18`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005d23`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005d2e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005d39`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005d44`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005d4f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005d5a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005d65`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005d70`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005d7b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005d86`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005d91`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800041b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800041bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004207`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000420f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004326`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000432e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800049a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004a60`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004a6f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004add`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004b2a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004c13`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004cd3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004d3c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004d4a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004dd1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004e6b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004e79`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004ec3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004f66`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004fff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005010`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800050af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800050be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000516d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000531f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000532e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800053ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800053bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005438`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005447`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800054dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800054ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005559`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005568`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800055c1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800055d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005676`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005685`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005702`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005711`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800057bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800057ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000584c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000585b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800058e5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800058f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005a1e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800041b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800041bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004207`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000420f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004326`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000432e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800049a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004a60`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004a6f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004add`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004b2a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004c13`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004cd3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004d3c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004d4a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004dd1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004e6b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004e79`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004ec3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004f66`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004fff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005010`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800050af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800050be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000516d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000531f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000532e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800053ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800053bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005438`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005447`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800054dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800054ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005559`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005568`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800055c1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800055d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005676`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005685`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005702`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005711`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800057bb`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
__int64 __fastcall CApplicationManager::RpcGetProcess(CApplicationManager *this, void *a2, struct CProcess **a3)
{
  struct CProcess **v3; // r13
  CApplicationManager *v5; // rsi
  RPC_STATUS v6; // eax
  unsigned int v7; // ebx
  unsigned int v8; // edi
  RTL_SRWLOCK *v9; // rbx
  _QWORD *i; // rax
  signed __int32 *v11; // rdx
  signed __int32 j; // eax
  struct _RTL_CRITICAL_SECTION *v14; // r14
  unsigned int v15; // edi
  _QWORD *k; // rax
  signed __int32 *v17; // rdx
  signed __int32 m; // eax
  unsigned int v19; // eax
  HANDLE CurrentThread; // rax
  const char *v21; // r9
  unsigned int v22; // eax
  HANDLE v23; // rdi
  void *v24; // r15
  __int64 v25; // rdx
  __int64 v26; // rcx
  WCHAR *v27; // r12
  void *v28; // r14
  void *v29; // rdi
  int InformationProcess; // eax
  HLOCAL v31; // rax
  int v32; // edx
  unsigned __int16 **v33; // r8
  const WCHAR *v34; // r15
  int v35; // eax
  unsigned int v36; // ebx
  WCHAR *v37; // rcx
  void *v38; // rcx
  signed int v39; // eax
  char v40; // di
  LONG v41; // eax
  bool v42; // sf
  HLOCAL v43; // r15
  CApplicationManager *v44; // rcx
  const char *v45; // r9
  PSID *v46; // rdi
  const char *v47; // r9
  signed int v48; // eax
  bool v49; // sf
  signed int v50; // eax
  bool v51; // sf
  struct CProcess *v52; // rcx
  char *v53; // rax
  struct CProcess *v54; // rdi
  int v55; // eax
  volatile int *v56; // rdx
  int v57; // eax
  int v58; // edi
  LPVOID *v59; // rcx
  LPVOID v60; // rax
  unsigned __int16 *v61; // rdx
  __int64 v62; // rax
  struct _RTL_CRITICAL_SECTION *v63; // rcx
  HANDLE v64; // r15
  char *v65; // r15
  const char *v66; // r9
  struct _RTL_CRITICAL_SECTION *v67; // rcx
  struct _RTL_CRITICAL_SECTION *v68; // rcx
  struct _RTL_CRITICAL_SECTION *v69; // rcx
  HLOCAL v70; // rcx
  unsigned int LastError; // ebx
  HLOCAL v72; // rcx
  HLOCAL v73; // r15
  const char *v74; // r9
  const char *v75; // r9
  HANDLE v76; // rax
  const char *v77; // r9
  DWORD v78; // edi
  int v79; // eax
  unsigned int PackageClaims; // eax
  CApplicationManager *v81; // rcx
  unsigned int v82; // eax
  int v83; // eax
  CApplicationManager *v84; // rcx
  unsigned int v85; // r15d
  int v86; // eax
  CApplicationManager *v87; // rcx
  int v88; // eax
  CApplicationManager *v89; // rcx
  int v90; // eax
  DWORD v91; // edi
  int v92; // eax
  ATL::CAtlException *v93; // rbx
  __int64 v94; // [rsp+0h] [rbp-318h] BYREF
  PDWORD ReturnLength; // [rsp+20h] [rbp-2F8h]
  unsigned __int16 *v96; // [rsp+28h] [rbp-2F0h]
  HANDLE TargetHandle; // [rsp+30h] [rbp-2E8h]
  unsigned __int16 *v98; // [rsp+38h] [rbp-2E0h]
  struct CProcess *v99; // [rsp+B0h] [rbp-268h] BYREF
  unsigned __int8 v100; // [rsp+B8h] [rbp-260h]
  LPVOID pv; // [rsp+C0h] [rbp-258h] BYREF
  void *TokenHandle; // [rsp+C8h] [rbp-250h] BYREF
  HLOCAL v103; // [rsp+D0h] [rbp-248h] BYREF
  HANDLE hObject; // [rsp+D8h] [rbp-240h] BYREF
  HANDLE ProcessHandle; // [rsp+E0h] [rbp-238h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+E8h] [rbp-230h]
  int v107; // [rsp+F0h] [rbp-228h] BYREF
  UINT32 packageFamilyNameLength; // [rsp+F4h] [rbp-224h] BYREF
  char *v109; // [rsp+F8h] [rbp-220h]
  ULONG ProcessInformationLength[2]; // [rsp+100h] [rbp-218h] BYREF
  unsigned int Pid; // [rsp+108h] [rbp-210h] BYREF
  HLOCAL v112; // [rsp+110h] [rbp-208h] BYREF
  HLOCAL hMem; // [rsp+118h] [rbp-200h] BYREF
  int v114; // [rsp+120h] [rbp-1F8h] BYREF
  unsigned int v115; // [rsp+124h] [rbp-1F4h] BYREF
  UINT32 packageRelativeApplicationIdLength; // [rsp+128h] [rbp-1F0h] BYREF
  char v117; // [rsp+12Dh] [rbp-1EBh]
  int v118[2]; // [rsp+130h] [rbp-1E8h] BYREF
  int TokenInformation; // [rsp+138h] [rbp-1E0h] BYREF
  int v120; // [rsp+13Ch] [rbp-1DCh] BYREF
  BOOL v121; // [rsp+140h] [rbp-1D8h]
  int v122; // [rsp+144h] [rbp-1D4h] BYREF
  int v123; // [rsp+148h] [rbp-1D0h] BYREF
  unsigned int v124; // [rsp+14Ch] [rbp-1CCh] BYREF
  RTL_SRWLOCK *v125; // [rsp+150h] [rbp-1C8h]
  PCWSTR applicationUserModelId; // [rsp+158h] [rbp-1C0h]
  unsigned __int16 *v127; // [rsp+160h] [rbp-1B8h]
  DWORD v128; // [rsp+168h] [rbp-1B0h] BYREF
  HANDLE v129; // [rsp+170h] [rbp-1A8h] BYREF
  LPVOID v130; // [rsp+178h] [rbp-1A0h]
  CApplicationManager *v131; // [rsp+180h] [rbp-198h]
  struct CProcess **v132; // [rsp+188h] [rbp-190h]
  void *v133; // [rsp+190h] [rbp-188h]
  char *v134; // [rsp+198h] [rbp-180h]
  ATL::CAtlException *v135[3]; // [rsp+1A0h] [rbp-178h] BYREF
  char v136; // [rsp+1B8h] [rbp-160h]
  WCHAR packageFamilyName[2]; // [rsp+1C0h] [rbp-158h] BYREF
  char v138[140]; // [rsp+1C4h] [rbp-154h] BYREF
  WCHAR packageRelativeApplicationId[2]; // [rsp+250h] [rbp-C8h] BYREF
  char v140[140]; // [rsp+254h] [rbp-C4h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+318h] [rbp+0h]

  v3 = a3;
  v132 = a3;
  v5 = g_ApplicationManager;
  v131 = g_ApplicationManager;
  *a3 = 0;
  Pid = 0;
  v6 = I_RpcBindingInqLocalClientPID(a2, &Pid);
  v7 = v6;
  if ( v6 > 0 )
    v7 = (unsigned __int16)v6 | 0x80070000;
  if ( (v7 & 0x80000000) != 0 )
  {
    if ( v7 == -2147023171 )
      return 2147944125LL;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x30D,
      (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\applicationmanager.cpp",
      (const char *)v7,
      (int)ReturnLength);
    return v7;
  }
  v8 = Pid;
  v99 = 0;
  v9 = (RTL_SRWLOCK *)((char *)v5 + 120);
  AcquireSRWLockShared((PSRWLOCK)v5 + 15);
  for ( i = (_QWORD *)*((_QWORD *)v5 + 16); i; i = (_QWORD *)*i )
  {
    v11 = (signed __int32 *)i[2];
    if ( !v11[104] && v11[40] == v8 )
    {
      for ( j = v11[5]; j != 0x7FFFFFFF; j = v11[5] )
      {
        if ( j == _InterlockedCompareExchange(v11 + 5, j + 1, j) )
          break;
      }
      v99 = (struct CProcess *)v11;
      break;
    }
  }
  if ( v5 != (CApplicationManager *)-120LL )
    ReleaseSRWLockShared((PSRWLOCK)v5 + 15);
  if ( v99 )
    goto LABEL_15;
  v14 = (struct _RTL_CRITICAL_SECTION *)((char *)v5 + 32);
  lpCriticalSection = (LPCRITICAL_SECTION)((char *)v5 + 32);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)v5 + 32));
  v134 = (char *)v5 + 32;
  v15 = Pid;
  v99 = 0;
  AcquireSRWLockShared((PSRWLOCK)v5 + 15);
  for ( k = (_QWORD *)*((_QWORD *)v5 + 16); k; k = (_QWORD *)*k )
  {
    v17 = (signed __int32 *)k[2];
    if ( !v17[104] && v17[40] == v15 )
    {
      for ( m = v17[5]; m != 0x7FFFFFFF; m = v17[5] )
      {
        if ( m == _InterlockedCompareExchange(v17 + 5, m + 1, m) )
          break;
      }
      v99 = (struct CProcess *)v17;
      break;
    }
  }
  if ( v5 != (CApplicationManager *)-120LL )
    ReleaseSRWLockShared((PSRWLOCK)v5 + 15);
  if ( v99 )
    goto LABEL_51;
  v19 = RpcImpersonateClient(a2);
  if ( v19 )
  {
    v36 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x31E,
            (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\applicationmanager.cpp",
            (const char *)v19,
            (unsigned int)ReturnLength);
    if ( v5 == (CApplicationManager *)-32LL )
      goto LABEL_201;
    v67 = (struct _RTL_CRITICAL_SECTION *)((char *)v5 + 32);
    goto LABEL_200;
  }
  v117 = 1;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x322,
                  (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\applicationmanager.cpp",
                  v21);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    RpcRevertToSelf();
    if ( v5 == (CApplicationManager *)-32LL )
    {
LABEL_262:
      wil::com_ptr_t<CProcess,wil::err_returncode_policy>::~com_ptr_t<CProcess,wil::err_returncode_policy>(&v99);
      return LastError;
    }
LABEL_261:
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v5 + 32));
    goto LABEL_262;
  }
  v115 = 0;
  v124 = 0;
  v103 = 0;
  v112 = 0;
  v22 = GetTokenInformation(TokenHandle, (unsigned __int16 **)&v112, &v115, (unsigned __int16 **)&v103, &v124);
  if ( v22 )
  {
    LastError = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x328,
                  (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\applicationmanager.cpp",
                  (const char *)v22,
                  (unsigned int)ReturnLength);
    if ( v103 )
      LocalFree(v103);
    if ( v112 )
      LocalFree(v112);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    RpcRevertToSelf();
    if ( v5 == (CApplicationManager *)-32LL )
      goto LABEL_262;
    goto LABEL_261;
  }
  v23 = OpenProcess(0x101000u, 0, Pid);
  ProcessHandle = v23;
  if ( !v23 && GetLastError() == 5 )
  {
    v76 = OpenProcess(0x100400u, 0, Pid);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &ProcessHandle,
      v76);
    v23 = ProcessHandle;
    if ( (char *)ProcessHandle - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
      wil::details::in1diag3::_Log_GetLastError(
        retaddr,
        (void *)0x338,
        (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\applicationmanager.cpp",
        v77);
  }
  v24 = v23;
  LODWORD(v125) = 0;
  TokenInformation = 0;
  v128 = 0;
  if ( GetTokenInformation(TokenHandle, TokenUIAccess, &TokenInformation, 4u, &v128) )
    LODWORD(v125) = TokenInformation != 0;
  v129 = (HANDLE)-1LL;
  v27 = 0;
  applicationUserModelId = 0;
  v28 = 0;
  v130 = 0;
  ProcessInformationLength[0] = 0;
  hMem = 0;
  v29 = 0;
  pv = 0;
  *(_QWORD *)v118 = 0;
  if ( v24 )
  {
    InformationProcess = NtQueryInformationProcess(v24, ProcessImageFileName, 0, 0, ProcessInformationLength);
    if ( (int)(InformationProcess + 0x80000000) >= 0 && InformationProcess != -1073741820 )
    {
LABEL_65:
      RtlSetLastWin32ErrorAndNtStatusFromNtStatus(InformationProcess);
      v39 = GetLastError();
      LODWORD(v109) = v39;
      if ( v39 > 0 )
        LODWORD(v109) = (unsigned __int16)v39 | 0x80070000;
      goto LABEL_68;
    }
    v31 = LocalAlloc(0x40u, ProcessInformationLength[0]);
    hMem = v31;
    if ( !v31 )
    {
      v36 = -2147024882;
      CoTaskMemFree(0);
      v37 = 0;
      goto LABEL_54;
    }
    InformationProcess = NtQueryInformationProcess(
                           v24,
                           ProcessImageFileName,
                           v31,
                           ProcessInformationLength[0],
                           ProcessInformationLength);
    if ( InformationProcess < 0 )
      goto LABEL_65;
    LODWORD(v109) = _AllocStringWorker<CTCoAllocPolicy>(
                      (unsigned int)&pv,
                      v32,
                      *((_QWORD *)hMem + 1),
                      (unsigned __int64)*((unsigned __int16 *)hMem + 1) >> 1,
                      (_DWORD)ReturnLength,
                      (__int64)&pv);
    if ( (int)v109 < 0 )
    {
LABEL_67:
      v29 = pv;
LABEL_68:
      CoTaskMemFree(v29);
      CoTaskMemFree(0);
      LocalFree(hMem);
      if ( (int)v109 >= 0 )
      {
        LODWORD(v109) = -2147024882;
        goto LABEL_70;
      }
      v36 = (unsigned int)v109;
LABEL_55:
      AudPolicyLogError("GetProcessModuleNameAndAppId", 349, v36);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x34E,
        (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\applicationmanager.cpp",
        (const char *)v36,
        (int)ReturnLength);
      if ( (char *)ProcessHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(ProcessHandle);
      if ( v103 )
        LocalFree(v103);
      if ( v112 )
        LocalFree(v112);
      v38 = TokenHandle;
      if ( (char *)TokenHandle - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
        goto LABEL_198;
LABEL_62:
      CloseHandle(v38);
LABEL_198:
      RpcRevertToSelf();
      goto LABEL_199;
    }
    if ( pv )
      goto LABEL_41;
  }
  LODWORD(v109) = _AllocString<CTCoAllocPolicy>(v26, v25, &qword_180053B30, &pv);
  if ( (int)v109 < 0 )
    goto LABEL_67;
LABEL_41:
  CallerIdentity::GetProcessAppId(v24, v118, v33);
  v34 = *(const WCHAR **)v118;
  if ( !*(_QWORD *)v118 )
  {
    v127 = 0;
    if ( is_mul_ok(1u, 2u) )
    {
      v34 = (const WCHAR *)CoTaskMemAlloc(2u);
      applicationUserModelId = v34;
      if ( v34 )
      {
        v35 = 0;
        LODWORD(v109) = -2147024882;
      }
      else
      {
        LODWORD(v109) = -2147024882;
        v35 = -2147024882;
        v34 = 0;
      }
      if ( v35 >= 0 )
      {
        if ( v34 )
          *v34 = 0;
        else
          MEMORY[0] = 0;
        goto LABEL_48;
      }
      v36 = v35;
      CoTaskMemFree(pv);
      v37 = (WCHAR *)v34;
    }
    else
    {
      v36 = -2147024362;
      CoTaskMemFree(pv);
      v37 = 0;
    }
LABEL_54:
    CoTaskMemFree(v37);
    LocalFree(hMem);
    goto LABEL_55;
  }
  LODWORD(v109) = -2147024882;
LABEL_48:
  v28 = pv;
  v130 = pv;
  v27 = (WCHAR *)v34;
  applicationUserModelId = v34;
  CoTaskMemFree(0);
  CoTaskMemFree(0);
  LocalFree(hMem);
LABEL_70:
  v107 = 0;
  hObject = 0;
  pv = 0;
  hMem = 0;
  v40 = 1;
  if ( (int)AppModelPolicy_GetPolicy_Internal(-6, 1, &v107, &hMem, &pv) < 0
    || (LODWORD(hMem) = 1, (unsigned int)(v107 - 65537) > 1) )
  {
    LODWORD(hMem) = 0;
  }
  v107 = 0;
  pv = 0;
  *(_QWORD *)v118 = 0;
  if ( (int)AppModelPolicy_GetPolicy_Internal(-6, 14, &v107, v118, &pv) < 0 || v107 != 917505 )
    v40 = 0;
  v100 = v40;
  v118[0] = 0;
  v114 = 0;
  v107 = 0;
  v123 = 0;
  v122 = 0;
  if ( !*v27 )
    goto LABEL_75;
  v64 = hObject;
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    v78 = GetLastError();
    CloseHandle(v64);
    SetLastError(v78);
    v40 = v100;
  }
  hObject = 0;
  v65 = (char *)ProcessHandle;
  if ( !OpenProcessToken(ProcessHandle, 8u, &hObject) )
  {
    v36 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0x36A,
            (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\applicationmanager.cpp",
            v66);
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    CoTaskMemFree(v27);
    if ( v28 )
      CoTaskMemFree(v28);
    if ( (unsigned __int64)(v65 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v65);
    if ( v103 )
      LocalFree(v103);
    if ( v112 )
      LocalFree(v112);
    v38 = TokenHandle;
    if ( (char *)TokenHandle - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
      goto LABEL_198;
    goto LABEL_62;
  }
  v79 = RtlQueryTokenHostIdAsUlong64(hObject, &v129);
  if ( v79 < 0 )
  {
    v36 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)0x36B,
            (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\applicationmanager.cpp",
            (const char *)(unsigned int)v79,
            (int)ReturnLength);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hObject);
    CoTaskMemFree(v27);
    if ( v28 )
      CoTaskMemFree(v28);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&ProcessHandle);
    if ( v103 )
      LocalFree(v103);
    if ( !v112 )
      goto LABEL_314;
    goto LABEL_313;
  }
LABEL_75:
  LOBYTE(v121) = 0;
  if ( v40 && v115 )
  {
    pv = 0;
    v98 = 0;
    TargetHandle = &pv;
    v96 = 0;
    ReturnLength = 0;
    PackageClaims = RtlQueryPackageClaims(-6, 0, 0, 0);
    if ( PackageClaims )
    {
      v36 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x372,
              (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\applicationmanager.cpp",
              (const char *)PackageClaims,
              (unsigned int)ReturnLength);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hObject);
      CoTaskMemFree(v27);
      if ( v28 )
        CoTaskMemFree(v28);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&ProcessHandle);
      if ( v103 )
        LocalFree(v103);
      if ( !v112 )
        goto LABEL_314;
      goto LABEL_313;
    }
    v82 = (unsigned int)pv >> 4;
    LOBYTE(v82) = ((unsigned __int8)pv & 0x10) != 0;
    v121 = v82;
    v83 = CApplicationManager::ReadVoipCallCapability(v81, (void *)0xFFFFFFFFFFFFFFFALL, v118);
    v85 = v83;
    if ( v83 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x377,
        (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\applicationmanager.cpp",
        (const char *)(unsigned int)v83,
        (int)ReturnLength);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hObject);
      CoTaskMemFree(v27);
      if ( v28 )
        CoTaskMemFree(v28);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&ProcessHandle);
      if ( v103 )
        LocalFree(v103);
      if ( v112 )
        LocalFree(v112);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
      RpcRevertToSelf();
      v69 = lpCriticalSection;
      if ( !lpCriticalSection )
        goto LABEL_251;
LABEL_250:
      LeaveCriticalSection(v69);
LABEL_251:
      wil::com_ptr_t<CProcess,wil::err_returncode_policy>::~com_ptr_t<CProcess,wil::err_returncode_policy>(&v99);
      return v85;
    }
    v86 = CApplicationManager::ReadBackgroundAudioPlaybackCapability(v84, (void *)0xFFFFFFFFFFFFFFFALL, &v114, &v107);
    v85 = v86;
    if ( v86 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x37C,
        (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\applicationmanager.cpp",
        (const char *)(unsigned int)v86,
        (int)ReturnLength);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hObject);
      CoTaskMemFree(v27);
      if ( v28 )
        CoTaskMemFree(v28);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&ProcessHandle);
      if ( v103 )
        LocalFree(v103);
      v70 = v112;
      if ( v112 )
        goto LABEL_252;
      goto LABEL_253;
    }
    v88 = CApplicationManager::ReadBackgroundMediaRecordingCapability(v87, (void *)0xFFFFFFFFFFFFFFFALL, &v123);
    v85 = v88;
    if ( v88 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x380,
        (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\applicationmanager.cpp",
        (const char *)(unsigned int)v88,
        (int)ReturnLength);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hObject);
      CoTaskMemFree(v27);
      if ( v28 )
        CoTaskMemFree(v28);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&ProcessHandle);
      v72 = v103;
      if ( v103 )
        goto LABEL_255;
      goto LABEL_256;
    }
    v90 = CApplicationManager::ReadUserSigninSupportCapability(v89, (void *)0xFFFFFFFFFFFFFFFALL, &v122);
    v85 = v90;
    if ( v90 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x384,
        (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\applicationmanager.cpp",
        (const char *)(unsigned int)v90,
        (int)ReturnLength);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hObject);
      CoTaskMemFree(v27);
      if ( v28 )
        CoTaskMemFree(v28);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&ProcessHandle);
      v72 = v103;
      if ( v103 )
LABEL_255:
        LocalFree(v72);
LABEL_256:
      v70 = v112;
      if ( v112 )
LABEL_252:
        LocalFree(v70);
LABEL_253:
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
      RpcRevertToSelf();
      v69 = lpCriticalSection;
      if ( !lpCriticalSection )
        goto LABEL_251;
      goto LABEL_250;
    }
  }
  if ( !v103 )
  {
    *(_DWORD *)packageFamilyName = 0;
    memset_0(v138, 0, 0x7Eu);
    *(_DWORD *)packageRelativeApplicationId = 0;
    memset_0(v140, 0, 0x80u);
    packageFamilyNameLength = 65;
    packageRelativeApplicationIdLength = 66;
    v41 = ParseApplicationUserModelId(
            v27,
            &packageFamilyNameLength,
            packageFamilyName,
            &packageRelativeApplicationIdLength,
            packageRelativeApplicationId);
    v42 = v41 < 0;
    if ( v41 > 0 )
      v42 = 1;
    if ( !v42 )
    {
      pv = 0;
      if ( (int)AppContainerDeriveSidFromMoniker(packageFamilyName, &pv) < 0 )
        goto LABEL_367;
      v73 = v103;
      if ( v103 )
      {
        v91 = GetLastError();
        LocalFree(v73);
        SetLastError(v91);
        v40 = v100;
      }
      v103 = 0;
      if ( ConvertSidToStringSidW(pv, (LPWSTR *)&v103) )
      {
LABEL_367:
        if ( pv )
          RtlFreeSid(pv);
        goto LABEL_80;
      }
      v36 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x393,
              (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\applicationmanager.cpp",
              v74);
      if ( pv )
        RtlFreeSid(pv);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hObject);
      CoTaskMemFree(v27);
      if ( v28 )
        CoTaskMemFree(v28);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&ProcessHandle);
      if ( v103 )
        LocalFree(v103);
      if ( !v112 )
        goto LABEL_314;
LABEL_313:
      LocalFree(v112);
LABEL_314:
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
      goto LABEL_198;
    }
  }
LABEL_80:
  v117 = 0;
  RpcRevertToSelf();
  ProcessInformationLength[0] = 0;
  v43 = v112;
  packageRelativeApplicationIdLength = (int)GetAssignedAccessTypeForUser((unsigned __int16 *)v112) >= 0
                                    && ProcessInformationLength[0] == 1;
  if ( !v40 || v114 )
  {
    v114 = 1;
  }
  else
  {
    v92 = CApplicationManager::ReadBackgroundAudioTaskCapability(v44, hObject, &v114, &v107);
    v58 = v92;
    if ( v92 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3A9,
        (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\applicationmanager.cpp",
        (const char *)(unsigned int)v92,
        (int)ReturnLength);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hObject);
      CoTaskMemFree(v27);
      if ( v28 )
        CoTaskMemFree(v28);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&ProcessHandle);
      if ( v103 )
        LocalFree(v103);
      if ( v43 )
        LocalFree(v43);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
      v63 = lpCriticalSection;
      if ( !lpCriticalSection )
        goto LABEL_170;
      goto LABEL_169;
    }
  }
  v120 = 0;
  if ( v115 && !(unsigned int)CheckTokenCapability(TokenHandle, *((_QWORD *)v5 + 2), &v120) )
  {
    v36 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0x3B5,
            (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\applicationmanager.cpp",
            v75);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hObject);
    CoTaskMemFree(v27);
    if ( v28 )
      CoTaskMemFree(v28);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&ProcessHandle);
    if ( v103 )
      LocalFree(v103);
    if ( v43 )
      LocalFree(v43);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    goto LABEL_199;
  }
  ProcessInformationLength[0] = 0;
  GetTokenInformation(TokenHandle, TokenIntegrityLevel, 0, 0, ProcessInformationLength);
  if ( GetLastError() != 122 )
  {
    v36 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0x3BD,
            (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\applicationmanager.cpp",
            v45);
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    CoTaskMemFree(v27);
    if ( v28 )
      CoTaskMemFree(v28);
    if ( (char *)ProcessHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(ProcessHandle);
    if ( v103 )
      LocalFree(v103);
    if ( v43 )
      LocalFree(v43);
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(TokenHandle);
LABEL_199:
    v67 = lpCriticalSection;
    if ( !lpCriticalSection )
    {
LABEL_201:
      wil::com_ptr_t<CProcess,wil::err_returncode_policy>::~com_ptr_t<CProcess,wil::err_returncode_policy>(&v99);
      return v36;
    }
LABEL_200:
    LeaveCriticalSection(v67);
    goto LABEL_201;
  }
  v46 = (PSID *)LocalAlloc(0x40u, ProcessInformationLength[0]);
  if ( !v46 )
  {
    v58 = (int)v109;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3C0,
      (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\applicationmanager.cpp",
      (const char *)(unsigned int)v109,
      (int)ReturnLength);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hObject);
    CoTaskMemFree(v27);
    if ( v28 )
      CoTaskMemFree(v28);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&ProcessHandle);
    if ( v103 )
      LocalFree(v103);
    if ( !v43 )
      goto LABEL_133;
    goto LABEL_132;
  }
  if ( !GetTokenInformation(
          TokenHandle,
          TokenIntegrityLevel,
          v46,
          ProcessInformationLength[0],
          ProcessInformationLength) )
  {
    v36 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0x3C2,
            (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\applicationmanager.cpp",
            v47);
    LocalFree(v46);
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    CoTaskMemFree(v27);
    if ( v28 )
      CoTaskMemFree(v28);
    if ( (char *)ProcessHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(ProcessHandle);
    if ( v103 )
      LocalFree(v103);
    if ( v43 )
      LocalFree(v43);
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(TokenHandle);
    if ( lpCriticalSection )
      LeaveCriticalSection(lpCriticalSection);
    if ( v99 )
      ((void (*)(void))Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IAudioProcess,IAudioProcessInternal>::Release)();
    return v36;
  }
  pv = GetSidSubAuthorityCount(*v46);
  v48 = GetLastError();
  packageFamilyNameLength = v48;
  v49 = v48 < 0;
  if ( v48 > 0 )
  {
    v48 = (unsigned __int16)v48 | 0x80070000;
    packageFamilyNameLength = v48;
    v49 = v48 < 0;
  }
  if ( v49 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3C7,
      (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\applicationmanager.cpp",
      (const char *)(unsigned int)v48,
      (int)ReturnLength);
    LocalFree(v46);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hObject);
    CoTaskMemFree(v27);
    if ( v28 )
      CoTaskMemFree(v28);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&ProcessHandle);
    if ( v103 )
      LocalFree(v103);
    if ( v43 )
      LocalFree(v43);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    v68 = lpCriticalSection;
    if ( !lpCriticalSection )
      goto LABEL_228;
LABEL_227:
    LeaveCriticalSection(v68);
LABEL_228:
    wil::com_ptr_t<CProcess,wil::err_returncode_policy>::~com_ptr_t<CProcess,wil::err_returncode_policy>(&v99);
    return packageFamilyNameLength;
  }
  if ( !pv || !*(_BYTE *)pv )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3C8,
      (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\applicationmanager.cpp",
      (const char *)0x8000FFFFLL,
      (int)ReturnLength);
    LocalFree(v46);
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    CoTaskMemFree(v27);
    if ( v28 )
      CoTaskMemFree(v28);
    if ( (char *)ProcessHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(ProcessHandle);
    if ( v103 )
      LocalFree(v103);
    if ( v43 )
      LocalFree(v43);
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(TokenHandle);
    if ( lpCriticalSection )
      LeaveCriticalSection(lpCriticalSection);
    wil::com_ptr_t<CProcess,wil::err_returncode_policy>::~com_ptr_t<CProcess,wil::err_returncode_policy>(&v99);
    return 2147549183LL;
  }
  LODWORD(pv) = *GetSidSubAuthority(*v46, (unsigned __int8)(*(_BYTE *)pv - 1));
  v50 = GetLastError();
  packageFamilyNameLength = v50;
  v51 = v50 < 0;
  if ( v50 > 0 )
  {
    v50 = (unsigned __int16)v50 | 0x80070000;
    packageFamilyNameLength = v50;
    v51 = v50 < 0;
  }
  if ( v51 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3CD,
      (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\applicationmanager.cpp",
      (const char *)(unsigned int)v50,
      (int)ReturnLength);
    LocalFree(v46);
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    CoTaskMemFree(v27);
    if ( v28 )
      CoTaskMemFree(v28);
    if ( (char *)ProcessHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(ProcessHandle);
    if ( v103 )
      LocalFree(v103);
    if ( v43 )
      LocalFree(v43);
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(TokenHandle);
    v68 = lpCriticalSection;
    if ( !lpCriticalSection )
      goto LABEL_228;
    goto LABEL_227;
  }
  LODWORD(pv) = (unsigned int)pv < 0x2000;
  LocalFree(v46);
  v127 = (unsigned __int16 *)v103;
  packageFamilyNameLength = v115 != 0;
  v52 = v99;
  v99 = 0;
  if ( v52 )
    ((void (*)(void))Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IAudioProcess,IAudioProcessInternal>::Release)();
  v99 = 0;
  v53 = (char *)operator new[](0x318u, (const struct std::nothrow_t *)&std::nothrow);
  *(_QWORD *)ProcessInformationLength = v53;
  v133 = v53;
  if ( v53 )
  {
    v109 = v53;
    v54 = CProcess::CProcess((CProcess *)v53);
    v133 = v54;
    *(_QWORD *)ProcessInformationLength = 0;
    v55 = CProcess::RuntimeClassInitialize(
            v54,
            ProcessHandle,
            Pid,
            v124,
            (const unsigned __int16 *)v28,
            v27,
            v129,
            (const unsigned __int16 *)v43,
            packageFamilyNameLength,
            v127,
            (int)hMem,
            v100,
            v118[0],
            v114,
            v107,
            v123,
            v122,
            packageRelativeApplicationIdLength,
            v121,
            v120,
            (int)pv);
    LODWORD(v109) = v55;
    if ( v55 >= 0 )
    {
      if ( v54 )
        Microsoft::WRL::Details::SafeUnknownIncrementReference((struct CProcess *)((char *)v54 + 20), v56);
      v99 = v54;
      if ( v54 )
      {
        Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IAudioProcess,IAudioProcessInternal>::Release(v54);
        v54 = v99;
      }
      *((_DWORD *)v54 + 115) = (_DWORD)v125;
      v57 = CApplicationManager::Register(v5, v99);
      v58 = v57;
      if ( v57 >= 0 )
      {
        v135[1] = v5;
        v135[2] = (ATL::CAtlException *)&v99;
        v136 = 1;
        AcquireSRWLockExclusive((PSRWLOCK)v5 + 15);
        try
        {
          v125 = (RTL_SRWLOCK *)((char *)v5 + 120);
          v58 = 0;
          v127 = (unsigned __int16 *)v99;
          pv = (LPVOID)*((_QWORD *)v5 + 16);
          ATL::CAtlList<CProcess *,ATL::CElementTraits<CProcess *>>::GetFreeNode();
        }
        catch ( ATL::CAtlException *v135 )
        {
          v61 = (unsigned __int16 *)&v94;
          v93 = v135[0];
          if ( *(_DWORD *)v135[0] == -1073741571 )
            _o__resetstkoflw();
          LODWORD(pv) = *(_DWORD *)v93;
          v43 = v112;
          v28 = v130;
          v27 = (WCHAR *)applicationUserModelId;
          v58 = (int)pv;
          v9 = v125;
          v5 = v131;
          v3 = v132;
          goto LABEL_153;
        }
        v59 = (LPVOID *)*((_QWORD *)v5 + 20);
        v60 = *v59;
        v61 = v127;
        v59[2] = v127;
        *((_QWORD *)v5 + 20) = v60;
        v59[1] = 0;
        *v59 = pv;
        ++*((_QWORD *)v5 + 18);
        v62 = *((_QWORD *)v5 + 16);
        if ( v62 )
          *(_QWORD *)(v62 + 8) = v59;
        else
          *((_QWORD *)v5 + 17) = v59;
        *((_QWORD *)v5 + 16) = v59;
LABEL_153:
        if ( v9 )
          ReleaseSRWLockExclusive(v9);
        if ( v58 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x3F3,
            (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\applicationmanager.cpp",
            (const char *)(unsigned int)v58,
            (int)ReturnLength);
          CApplicationManager::Unregister(v5, v99);
          if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
            CloseHandle(hObject);
          CoTaskMemFree(v27);
          if ( v28 )
            CoTaskMemFree(v28);
          if ( (char *)ProcessHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
            CloseHandle(ProcessHandle);
          if ( v103 )
            LocalFree(v103);
          if ( v43 )
            LocalFree(v43);
          if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
            CloseHandle(TokenHandle);
LABEL_168:
          v63 = lpCriticalSection;
          if ( !lpCriticalSection )
          {
LABEL_170:
            wil::com_ptr_t<CProcess,wil::err_returncode_policy>::~com_ptr_t<CProcess,wil::err_returncode_policy>(&v99);
            return (unsigned int)v58;
          }
LABEL_169:
          LeaveCriticalSection(v63);
          goto LABEL_170;
        }
        Microsoft::WRL::Details::SafeUnknownIncrementReference(
          (struct CProcess *)((char *)v99 + 20),
          (volatile int *)v61);
        if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          CloseHandle(hObject);
        CoTaskMemFree(v27);
        if ( v28 )
          CoTaskMemFree(v28);
        if ( (char *)ProcessHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          CloseHandle(ProcessHandle);
        if ( v103 )
          LocalFree(v103);
        if ( v43 )
          LocalFree(v43);
        if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          CloseHandle(TokenHandle);
        v14 = lpCriticalSection;
LABEL_51:
        if ( v14 )
          LeaveCriticalSection(v14);
LABEL_15:
        *v3 = v99;
        return 0;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3EA,
        (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\applicationmanager.cpp",
        (const char *)(unsigned int)v57,
        (int)ReturnLength);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hObject);
      CoTaskMemFree(v27);
      if ( v28 )
        CoTaskMemFree(v28);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&ProcessHandle);
      if ( v103 )
        LocalFree(v103);
      if ( !v43 )
      {
LABEL_133:
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
        goto LABEL_168;
      }
LABEL_132:
      LocalFree(v43);
      goto LABEL_133;
    }
    if ( v54 )
    {
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IAudioProcess,IAudioProcessInternal>::Release(v54);
      v55 = (int)v109;
    }
  }
  else
  {
    v55 = (int)v109;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x3E6,
    (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\applicationmanager.cpp",
    (const char *)(unsigned int)v55,
    (int)ReturnLength);
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  CoTaskMemFree(v27);
  if ( v28 )
    CoTaskMemFree(v28);
  if ( (char *)ProcessHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(ProcessHandle);
  if ( v103 )
    LocalFree(v103);
  if ( v43 )
    LocalFree(v43);
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(TokenHandle);
  if ( lpCriticalSection )
    LeaveCriticalSection(lpCriticalSection);
  wil::com_ptr_t<CProcess,wil::err_returncode_policy>::~com_ptr_t<CProcess,wil::err_returncode_policy>(&v99);
  return (unsigned int)v109;
}

```

## disassembly

```asm
0x180003c70  mov     [rsp+arg_0], rbx
0x180003c75  mov     [rsp+arg_18], rsi
0x180003c7a  push    rdi
0x180003c7b  push    r12
0x180003c7d  push    r13
0x180003c7f  push    r14
0x180003c81  push    r15
0x180003c83  sub     rsp, 2F0h
0x180003c8a  mov     rax, cs:__security_cookie
0x180003c91  xor     rax, rsp
0x180003c94  mov     [rsp+318h+var_38], rax
0x180003c9c  mov     r13, r8
0x180003c9f  mov     r15, rdx
0x180003ca2  mov     [rsp+318h+var_190], r8
0x180003caa  mov     rsi, cs:?g_ApplicationManager@@3PEAVCApplicationManager@@EA; CApplicationManager * g_ApplicationManager
0x180003cb1  mov     [rsp+318h+var_198], rsi
0x180003cb9  xor     r14d, r14d
0x180003cbc  mov     [r8], r14
0x180003cbf  mov     [rsp+318h+Pid], r14d
0x180003cc7  lea     rdx, [rsp+318h+Pid]; Pid
0x180003ccf  mov     rcx, r15; Binding
0x180003cd2  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x180003cd8  mov     ebx, eax
0x180003cda  test    eax, eax
0x180003cdc  jg      loc_1800042B0
0x180003ce2  test    ebx, ebx
0x180003ce4  js      loc_180005141
0x180003cea  mov     edi, [rsp+318h+Pid]
0x180003cf1  mov     [rsp+318h+var_268], r14
0x180003cf9  lea     rbx, [rsi+78h]
0x180003cfd  mov     rcx, rbx; SRWLock
0x180003d00  call    cs:__imp_AcquireSRWLockShared
0x180003d06  mov     rax, [rsi+80h]
0x180003d0d  nop     dword ptr [rax]
0x180003d10  test    rax, rax
0x180003d13  jz      short loc_180003D4B
0x180003d15  mov     rdx, [rax+10h]
0x180003d19  cmp     dword ptr [rdx+1A0h], 0
0x180003d20  jnz     short loc_180003D2A
0x180003d22  cmp     [rdx+0A0h], edi
0x180003d28  jz      short loc_180003D2F
0x180003d2a  mov     rax, [rax]
0x180003d2d  jmp     short loc_180003D10
0x180003d2f  mov     eax, [rdx+14h]
0x180003d32  cmp     eax, 7FFFFFFFh
0x180003d37  jz      short loc_180003D43
0x180003d39  lea     ecx, [rax+1]
0x180003d3c  lock cmpxchg [rdx+14h], ecx
0x180003d41  jnz     short loc_180003D9F
0x180003d43  mov     [rsp+318h+var_268], rdx
0x180003d4b  test    rbx, rbx
0x180003d4e  jz      short loc_180003D59
0x180003d50  mov     rcx, rbx; SRWLock
0x180003d53  call    cs:__imp_ReleaseSRWLockShared
0x180003d59  cmp     [rsp+318h+var_268], 0
0x180003d62  jz      short loc_180003DAB
0x180003d64  mov     rax, [rsp+318h+var_268]
0x180003d6c  mov     [r13+0], rax
0x180003d70  xor     eax, eax
0x180003d72  mov     rcx, [rsp+318h+var_38]
0x180003d7a  xor     rcx, rsp; StackCookie
0x180003d7d  call    __security_check_cookie
0x180003d82  lea     r11, [rsp+318h+var_28]
0x180003d8a  mov     rbx, [r11+30h]
0x180003d8e  mov     rsi, [r11+48h]
0x180003d92  mov     rsp, r11
0x180003d95  pop     r15
0x180003d97  pop     r14
0x180003d99  pop     r13
0x180003d9b  pop     r12
0x180003d9d  pop     rdi
0x180003d9e  retn
0x180003d9f  mov     eax, [rdx+14h]
0x180003da2  cmp     eax, 7FFFFFFFh
0x180003da7  jnz     short loc_180003D39
0x180003da9  jmp     short loc_180003D43
0x180003dab  lea     r14, [rsi+20h]
0x180003daf  mov     [rsp+318h+lpCriticalSection], r14
0x180003db7  mov     rcx, r14; lpCriticalSection
0x180003dba  call    cs:__imp_EnterCriticalSection
0x180003dc0  mov     [rsp+318h+var_180], r14
0x180003dc8  mov     rcx, [rsp+318h+var_268]
0x180003dd0  mov     [rsp+318h+var_268], 0
0x180003ddc  test    rcx, rcx
0x180003ddf  jnz     loc_180005989
0x180003de5  mov     edi, [rsp+318h+Pid]
0x180003dec  mov     [rsp+318h+var_268], 0
0x180003df8  mov     rcx, rbx; SRWLock
0x180003dfb  call    cs:__imp_AcquireSRWLockShared
0x180003e01  mov     rax, [rsi+80h]
0x180003e08  test    rax, rax
0x180003e0b  jz      short loc_180003E47
0x180003e0d  mov     rdx, [rax+10h]
0x180003e11  cmp     dword ptr [rdx+1A0h], 0
0x180003e18  jnz     short loc_180003E22
0x180003e1a  cmp     [rdx+0A0h], edi
0x180003e20  jz      short loc_180003E27
0x180003e22  mov     rax, [rax]
0x180003e25  jmp     short loc_180003E08
0x180003e27  mov     eax, [rdx+14h]
0x180003e2a  cmp     eax, 7FFFFFFFh
0x180003e2f  jz      short loc_180003E3F
0x180003e31  lea     ecx, [rax+1]
0x180003e34  lock cmpxchg [rdx+14h], ecx
0x180003e39  jnz     loc_1800041D5
0x180003e3f  mov     [rsp+318h+var_268], rdx
0x180003e47  test    rbx, rbx
0x180003e4a  jz      short loc_180003E55
0x180003e4c  mov     rcx, rbx; SRWLock
0x180003e4f  call    cs:__imp_ReleaseSRWLockShared
0x180003e55  cmp     [rsp+318h+var_268], 0
0x180003e5e  jnz     loc_1800041E8
0x180003e64  mov     rcx, r15; BindingHandle
0x180003e67  call    cs:__imp_RpcImpersonateClient
0x180003e6d  test    eax, eax
0x180003e6f  jnz     loc_1800051F0
0x180003e75  mov     [rsp+318h+var_1EB], 1
0x180003e7d  mov     [rsp+318h+TokenHandle], 0
0x180003e89  call    cs:__imp_GetCurrentThread
0x180003e8f  lea     r9, [rsp+318h+TokenHandle]; TokenHandle
0x180003e97  mov     edx, 8; DesiredAccess
0x180003e9c  mov     r8d, 1; OpenAsSelf
0x180003ea2  mov     rcx, rax; ThreadHandle
0x180003ea5  call    cs:__imp_OpenThreadToken
0x180003eab  test    eax, eax
0x180003ead  jz      loc_18000521F
0x180003eb3  mov     [rsp+318h+var_1F4], 0
0x180003ebe  mov     [rsp+318h+var_1CC], 0
0x180003ec9  mov     [rsp+318h+var_248], 0
0x180003ed5  mov     [rsp+318h+var_208], 0
0x180003ee1  lea     rax, [rsp+318h+var_1CC]
0x180003ee9  mov     [rsp+318h+ReturnLength], rax; unsigned int
0x180003eee  lea     r9, [rsp+318h+var_248]; unsigned __int16 **
0x180003ef6  lea     r8, [rsp+318h+var_1F4]; unsigned int *
0x180003efe  lea     rdx, [rsp+318h+var_208]; unsigned __int16 **
0x180003f06  mov     rcx, [rsp+318h+TokenHandle]; TokenHandle
0x180003f0e  call    ?GetTokenInformation@@YAKPEAXPEAPEAGPEAK12@Z; GetTokenInformation(void *,ushort * *,ulong *,ushort * *,ulong *)
0x180003f13  test    eax, eax
0x180003f15  jnz     loc_180005272
0x180003f1b  mov     r8d, [rsp+318h+Pid]; dwProcessId
0x180003f23  xor     edx, edx; bInheritHandle
0x180003f25  mov     ecx, 101000h; dwDesiredAccess
0x180003f2a  call    cs:__imp_OpenProcess
0x180003f30  mov     rdi, rax
0x180003f33  mov     [rsp+318h+ProcessHandle], rax
0x180003f3b  test    rax, rax
0x180003f3e  jz      loc_180005993
0x180003f44  mov     r15, rdi
0x180003f47  mov     dword ptr [rsp+318h+var_1C8], 0
0x180003f52  mov     [rsp+318h+TokenInformation], 0
0x180003f5d  mov     [rsp+318h+var_1B0], 0
0x180003f68  lea     rax, [rsp+318h+var_1B0]
0x180003f70  mov     [rsp+318h+ReturnLength], rax; ReturnLength
0x180003f75  mov     r9d, 4; TokenInformationLength
0x180003f7b  lea     r8, [rsp+318h+TokenInformation]; TokenInformation
0x180003f83  mov     edx, 1Ah; TokenInformationClass
0x180003f88  mov     rcx, [rsp+318h+TokenHandle]; TokenHandle
0x180003f90  call    cs:__imp_GetTokenInformation
0x180003f96  test    eax, eax
0x180003f98  jnz     loc_1800042CE
0x180003f9e  mov     [rsp+318h+var_1A8], 0FFFFFFFFFFFFFFFFh
0x180003faa  xor     r12d, r12d
0x180003fad  mov     [rsp+318h+applicationUserModelId], r12
0x180003fb5  xor     r14d, r14d
0x180003fb8  mov     [rsp+318h+var_1A0], r14
0x180003fc0  mov     [rsp+318h+ProcessInformationLength], r12d
0x180003fc8  mov     [rsp+318h+hMem], r12
0x180003fd0  xor     edi, edi
0x180003fd2  mov     [rsp+318h+pv], rdi
0x180003fda  mov     qword ptr [rsp+318h+var_1E8], rdi
0x180003fe2  test    r15, r15
0x180003fe5  jz      loc_1800059CC
0x180003feb  lea     rax, [rsp+318h+ProcessInformationLength]
0x180003ff3  mov     [rsp+318h+ReturnLength], rax; int
0x180003ff8  xor     r9d, r9d; ProcessInformationLength
0x180003ffb  xor     r8d, r8d; ProcessInformation
0x180003ffe  mov     edx, 1Bh; ProcessInformationClass
0x180004003  mov     rcx, r15; ProcessHandle
0x180004006  call    cs:__imp_NtQueryInformationProcess
0x18000400c  mov     edx, 80000000h
0x180004011  lea     ecx, [rax+rdx]
0x180004014  test    edx, ecx
0x180004016  jz      loc_1800042E6
0x18000401c  mov     edx, [rsp+318h+ProcessInformationLength]; uBytes
0x180004023  mov     ecx, 40h ; '@'; uFlags
0x180004028  call    cs:__imp_LocalAlloc
0x18000402e  mov     [rsp+318h+hMem], rax
0x180004036  test    rax, rax
0x180004039  jz      loc_1800041FF
0x18000403f  lea     rcx, [rsp+318h+ProcessInformationLength]
0x180004047  mov     [rsp+318h+ReturnLength], rcx; ReturnLength
0x18000404c  mov     r9d, [rsp+318h+ProcessInformationLength]; ProcessInformationLength
0x180004054  mov     r8, rax; ProcessInformation
0x180004057  mov     edx, 1Bh; ProcessInformationClass
0x18000405c  mov     rcx, r15; ProcessHandle
0x18000405f  call    cs:__imp_NtQueryInformationProcess
0x180004065  test    eax, eax
0x180004067  js      loc_1800042F1
0x18000406d  mov     rax, [rsp+318h+hMem]
0x180004075  movzx   r9d, word ptr [rax+2]
0x18000407a  shr     r9, 1
0x18000407d  lea     rcx, [rsp+318h+pv]
0x180004085  mov     [rsp+318h+var_2F0], rcx
0x18000408a  mov     r8, [rax+8]
0x18000408e  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x180004093  mov     dword ptr [rsp+318h+var_220], eax
0x18000409a  test    eax, eax
0x18000409c  js      loc_18000431B
0x1800040a2  cmp     [rsp+318h+pv], rdi
0x1800040aa  jz      loc_1800059CC
0x1800040b0  lea     rdi, qword_180053B30
0x1800040b7  lea     rdx, [rsp+318h+var_1E8]; void *
0x1800040bf  mov     rcx, r15; ProcessHandle
0x1800040c2  call    ?GetProcessAppId@CallerIdentity@@YAJPEAXPEAPEAG@Z; CallerIdentity::GetProcessAppId(void *,ushort * *)
0x1800040c7  mov     r15, qword ptr [rsp+318h+var_1E8]
0x1800040cf  test    r15, r15
0x1800040d2  jnz     loc_1800042BE
0x1800040d8  mov     [rsp+318h+var_1B8], r12
0x1800040e0  mov     eax, 2
0x1800040e5  mov     ecx, 1
0x1800040ea  mul     rcx
0x1800040ed  test    rdx, rdx
0x1800040f0  jnz     loc_180004FF2
0x1800040f6  mov     rcx, rax; cb
0x1800040f9  call    cs:__imp_CoTaskMemAlloc
0x1800040ff  mov     r15, rax
0x180004102  mov     [rsp+318h+applicationUserModelId], rax
0x18000410a  test    rax, rax
0x18000410d  jnz     loc_1800059F7
0x180004113  mov     r15d, 8007000Eh
0x180004119  mov     dword ptr [rsp+318h+var_220], r15d
0x180004121  mov     eax, r15d
0x180004124  mov     r15, [rsp+318h+applicationUserModelId]
0x18000412c  test    eax, eax
0x18000412e  js      loc_180005A14
0x180004134  test    r15, r15
0x180004137  jz      loc_180005A09
0x18000413d  xor     ecx, ecx
0x18000413f  mov     r11d, 1
0x180004145  mov     edx, r11d
0x180004148  mov     r8, r15
0x18000414b  xor     r9d, r9d
0x18000414e  xchg    ax, ax
0x180004150  test    rcx, rcx
0x180004153  jz      short loc_180004174
0x180004155  movzx   eax, word ptr [rdi]
0x180004158  test    ax, ax
0x18000415b  jz      short loc_180004174
0x18000415d  add     rdi, 2
0x180004161  mov     [r8], ax
0x180004165  add     r8, 2
0x180004169  dec     rcx
0x18000416c  inc     r9
0x18000416f  sub     rdx, r11
0x180004172  jnz     short loc_180004150
0x180004174  lea     r10, [r9-1]
0x180004178  test    rdx, rdx
0x18000417b  cmovnz  r10, r9
0x18000417f  lea     rcx, [r8-2]
0x180004183  cmovnz  rcx, r8
0x180004187  xor     eax, eax
0x180004189  mov     [rcx], ax
0x18000418c  test    rdx, rdx
0x18000418f  jnz     loc_18000501B
0x180004195  mov     r14, [rsp+318h+pv]
0x18000419d  mov     [rsp+318h+var_1A0], r14
0x1800041a5  mov     r12, r15
0x1800041a8  mov     [rsp+318h+applicationUserModelId], r15
0x1800041b0  xor     ecx, ecx; pv
0x1800041b2  xor     edi, edi
0x1800041b4  call    cs:__imp_CoTaskMemFree
0x1800041ba  mov     ecx, edi; pv
0x1800041bc  call    cs:__imp_CoTaskMemFree
0x1800041c2  mov     rcx, [rsp+318h+hMem]; hMem
0x1800041ca  call    cs:__imp_LocalFree
0x1800041d0  jmp     loc_18000435C
0x1800041d5  mov     eax, [rdx+14h]
0x1800041d8  cmp     eax, 7FFFFFFFh
0x1800041dd  jnz     loc_180003E31
0x1800041e3  jmp     loc_180003E3F
0x1800041e8  test    r14, r14
0x1800041eb  jz      loc_180003D64
0x1800041f1  mov     rcx, r14; lpCriticalSection
0x1800041f4  call    cs:__imp_LeaveCriticalSection
0x1800041fa  jmp     loc_180003D64
0x1800041ff  mov     ebx, 8007000Eh
0x180004204  mov     rcx, rdi; pv
0x180004207  call    cs:__imp_CoTaskMemFree
0x18000420d  xor     ecx, ecx; pv
0x18000420f  call    cs:__imp_CoTaskMemFree
0x180004215  mov     rcx, [rsp+318h+hMem]; hMem
0x18000421d  call    cs:__imp_LocalFree
0x180004223  mov     r8d, ebx; int
0x180004226  mov     edx, 15Dh; int
0x18000422b  lea     rcx, aGetprocessmodu; "GetProcessModuleNameAndAppId"
0x180004232  call    ?AudPolicyLogError@@YAXPEBDHJ@Z; AudPolicyLogError(char const *,int,long)
0x180004237  mov     rcx, [rsp+318h]; this
0x18000423f  mov     r9d, ebx; char *
0x180004242  lea     r8, aClientcoreMult_5; "clientcore\\multimedia\\audiocore\\serv"...
0x180004249  mov     edx, 34Eh; void *
  ... truncated ...
```
