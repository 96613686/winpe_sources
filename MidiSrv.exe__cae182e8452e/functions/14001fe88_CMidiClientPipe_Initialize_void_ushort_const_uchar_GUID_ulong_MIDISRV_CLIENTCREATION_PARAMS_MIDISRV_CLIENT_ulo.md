# CMidiClientPipe::Initialize(void *,ushort const *,uchar,_GUID,ulong,MIDISRV_CLIENTCREATION_PARAMS *,MIDISRV_CLIENT *,ulong *,int)

- ea: `0x14001fe88`
- end: `0x140021309`
- name: `?Initialize@CMidiClientPipe@@QEAAJPEAXPEBGEU_GUID@@KPEAUMIDISRV_CLIENTCREATION_PARAMS@@PEAUMIDISRV_CLIENT@@PEAKH@Z`
- size: `5249`
- prototype: `__int64 __fastcall(CMidiClientPipe *this, void *, MEMORY_MAPPED_PIPE *, unsigned __int8, struct _GUID *, unsigned int, struct MIDISRV_CLIENTCREATION_PARAMS *, HANDLE *, unsigned int *, int)`
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140018f54`

## callees

- `0x140002390`
- `0x1400054c0`
- `0x140005868`
- `0x1400058ac`
- `0x1400060ec`
- `0x14000984c`
- `0x14000a694`
- `0x14000a6b4`
- `0x14000c55c`
- `0x14000c9a8`
- `0x14001487c`
- `0x14001b8c0`
- `0x14001fa84`
- `0x14001fbec`
- `0x14001fcf0`
- `0x14001fd5c`
- `0x14001fe88`
- `0x14002156c`
- `0x14004616c`
- `0x14004642c`
- `0x1400464d8`
- `0x1400468d0`
- `0x140046954`
- `0x14005a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14001ff80`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14001ff80`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14001ffe7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140021110`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140021269`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400212cf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14001ffe7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140021110`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140021269`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400212cf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140020585`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140020cfb`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140020585`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140020cfb`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x140021015`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x140021015`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400204a4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400205b6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140020c51`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400204a4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400205b6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140020c51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140020491`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140020597`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140020c3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140020491`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140020597`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140020c3e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400205c4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400205d4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14002065d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14002066d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400206f6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140020703`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14002078b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140020798`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140020d12`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140020d23`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140020dac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140020dbd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140020e46`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140020e54`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140020edd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140020eeb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400205c4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400205d4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14002065d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14002066d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400206f6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140020703`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14002078b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140020798`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140020d12`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140020d23`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140020dac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140020dbd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140020e46`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140020e54`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140020edd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140020eeb`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1400205ff`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x140020698`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x14002072d`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1400207c3`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x140020d4e`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x140020de8`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x140020e7f`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x140020f16`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1400205ff`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x140020698`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x14002072d`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1400207c3`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x140020d4e`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x140020de8`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x140020e7f`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x140020f16`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140020205`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400202d1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400205a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140020986`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140020a6b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140020205`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400202d1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400205a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140020986`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140020a6b`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1400204ba`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x140020c67`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1400204ba`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x140020c67`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140020243`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002030f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140020376`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400203f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140020458`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002049c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400204e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140020629`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400206c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140020757`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400207ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140020833`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002091a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400209c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140020aaa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140020b13`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140020b99`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140020c05`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140020c49`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140020c95`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140020d78`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140020e12`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140020ea9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140020f42`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140020f87`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140020fb8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140020243`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002030f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140020376`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400203f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140020458`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002049c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400204e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140020629`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400206c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140020757`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400207ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140020833`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002091a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400209c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140020aaa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140020b13`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140020b99`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140020c05`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140020c49`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140020c95`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140020d78`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140020e12`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140020ea9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140020f42`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140020f87`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140020fb8`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x14002042a`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x140020bd7`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x14002042a`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x140020bd7`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1400201e3`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1400201f2`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1400202af`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1400202be`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140020964`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140020973`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140020a49`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140020a58`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1400201e3`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1400201f2`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1400202af`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1400202be`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140020964`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140020973`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140020a49`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140020a58`

## string_xrefs

- `0x14001ffb8`: `avcore\midi2\service\exe\midiclientpipe.cpp`
- `0x140020011`: `avcore\midi2\service\exe\midiclientpipe.cpp`
- `0x140020029`: `avcore\midi2\service\exe\midiclientpipe.cpp`
- `0x14002007d`: `avcore\midi2\service\exe\midiclientpipe.cpp`
- `0x1400200d5`: `avcore\midi2\service\exe\midiclientpipe.cpp`
- `0x140020228`: `avcore\midi2\service\exe\midiclientpipe.cpp`
- `0x1400202f4`: `avcore\midi2\service\exe\midiclientpipe.cpp`
- `0x14002035b`: `avcore\midi2\service\exe\midiclientpipe.cpp`
- `0x1400203d5`: `avcore\midi2\service\exe\midiclientpipe.cpp`
- `0x14002043d`: `avcore\midi2\service\exe\midiclientpipe.cpp`
- `0x1400204cd`: `avcore\midi2\service\exe\midiclientpipe.cpp`
- `0x14002060d`: `avcore\midi2\service\exe\midiclientpipe.cpp`
- `0x1400206a6`: `avcore\midi2\service\exe\midiclientpipe.cpp`
- `0x14002073b`: `avcore\midi2\service\exe\midiclientpipe.cpp`
- `0x1400207d3`: `avcore\midi2\service\exe\midiclientpipe.cpp`
- `0x1400208ff`: `avcore\midi2\service\exe\midiclientpipe.cpp`
- `0x1400209aa`: `avcore\midi2\service\exe\midiclientpipe.cpp`
- `0x140020a8f`: `avcore\midi2\service\exe\midiclientpipe.cpp`
- `0x140020af8`: `avcore\midi2\service\exe\midiclientpipe.cpp`
- `0x140020b7e`: `avcore\midi2\service\exe\midiclientpipe.cpp`
- `0x140020bea`: `avcore\midi2\service\exe\midiclientpipe.cpp`
- `0x140020c7a`: `avcore\midi2\service\exe\midiclientpipe.cpp`
- `0x140020d5c`: `avcore\midi2\service\exe\midiclientpipe.cpp`
- `0x140020df6`: `avcore\midi2\service\exe\midiclientpipe.cpp`
- `0x140020e8d`: `avcore\midi2\service\exe\midiclientpipe.cpp`
- `0x140020f26`: `avcore\midi2\service\exe\midiclientpipe.cpp`
- `0x140020f9d`: `avcore\midi2\service\exe\midiclientpipe.cpp`
- `0x140021097`: `avcore\midi2\service\exe\midiclientpipe.cpp`
- `0x140021164`: `avcore\midi2\service\exe\midiclientpipe.cpp`
- `0x1400211ed`: `avcore\midi2\service\exe\midiclientpipe.cpp`

## pseudocode

```c
__int64 __fastcall CMidiClientPipe::Initialize(
        CMidiClientPipe *this,
        void *a2,
        MEMORY_MAPPED_PIPE *a3,
        unsigned __int8 a4,
        struct _GUID *a5,
        unsigned int a6,
        struct MIDISRV_CLIENTCREATION_PARAMS *a7,
        HANDLE *a8,
        unsigned int *a9,
        int a10)
{
  _DWORD *v13; // rcx
  int v14; // r8d
  int v15; // r9d
  struct MIDISRV_CLIENTCREATION_PARAMS *v16; // rdi
  char *v17; // r14
  _DWORD *v18; // r12
  int v19; // eax
  unsigned int v20; // ebx
  unsigned int *p_Data1; // rsi
  int RequiredBufferSize; // eax
  int v24; // eax
  int v25; // eax
  char *v26; // rax
  _QWORD *v27; // rax
  __int64 v28; // rbx
  const void *v29; // rcx
  const void *v30; // rcx
  _QWORD *v31; // rax
  __int64 v32; // rbx
  const void *v33; // rcx
  const void *v34; // rcx
  int MappedDataBuffer; // eax
  int MappedRegisters; // eax
  HRESULT v37; // eax
  void *v38; // rdi
  DWORD LastError; // ebx
  HRESULT v40; // eax
  __int64 v41; // r8
  const WCHAR *v42; // rbx
  WCHAR *v43; // rdi
  HANDLE EventW; // rsi
  void *v45; // rbx
  DWORD v46; // edi
  unsigned int v47; // r8d
  const char *v48; // r9
  LPHANDLE v49; // rsi
  HANDLE CurrentProcess; // rdi
  void *v51; // rbx
  HANDLE v52; // rax
  const char *v53; // r9
  LPHANDLE v54; // rsi
  HANDLE v55; // rdi
  void *v56; // rbx
  HANDLE v57; // rax
  const char *v58; // r9
  HANDLE *v59; // rsi
  HANDLE v60; // rbx
  void *v61; // rdi
  HANDLE v62; // rax
  const char *v63; // r9
  LPHANDLE v64; // rsi
  HANDLE v65; // rbx
  void *v66; // rdi
  HANDLE v67; // rax
  const char *v68; // r9
  _DWORD *v69; // rax
  _QWORD *v70; // rax
  __int64 v71; // rbx
  const void *v72; // rcx
  const void *v73; // rcx
  _QWORD *v74; // rax
  __int64 v75; // rbx
  const void *v76; // rcx
  const void *v77; // rcx
  int v78; // eax
  int v79; // eax
  HRESULT v80; // eax
  void *v81; // rdi
  DWORD v82; // ebx
  HRESULT v83; // eax
  const WCHAR *v84; // rbx
  HANDLE v85; // rax
  LPHANDLE v86; // rsi
  HANDLE v87; // rdi
  void *v88; // rbx
  HANDLE v89; // rax
  const char *v90; // r9
  LPHANDLE v91; // rsi
  HANDLE v92; // rdi
  void *v93; // rbx
  HANDLE v94; // rax
  const char *v95; // r9
  LPHANDLE v96; // rsi
  HANDLE v97; // rbx
  void *v98; // rdi
  HANDLE v99; // rax
  const char *v100; // r9
  LPHANDLE v101; // rsi
  HANDLE v102; // rbx
  void *v103; // rdi
  HANDLE v104; // rax
  const char *v105; // r9
  char *v106; // rax
  char *v107; // rbx
  CMidiXProc *v108; // rdi
  __int64 (__fastcall *v109)(CMidiClientPipe *, GUID *, __int64 *); // rbx
  __int64 v110; // rcx
  int v111; // eax
  int v112; // eax
  unsigned int v113; // edi
  void *v114; // rbx
  MEMORY_MAPPED_PIPE *v115; // rbx
  void *v116; // rbx
  MEMORY_MAPPED_PIPE *v117; // rbx
  int dwDesiredAccess; // [rsp+20h] [rbp-A9h]
  int dwDesiredAccessb; // [rsp+20h] [rbp-A9h]
  int dwDesiredAccessa; // [rsp+20h] [rbp-A9h]
  LPVOID pv; // [rsp+50h] [rbp-79h] BYREF
  __int64 v122; // [rsp+58h] [rbp-71h] BYREF
  LPHANDLE *p_lpTargetHandle; // [rsp+60h] [rbp-69h] BYREF
  char v124; // [rsp+68h] [rbp-61h]
  unsigned __int8 v125; // [rsp+70h] [rbp-59h]
  LPHANDLE lpTargetHandle; // [rsp+78h] [rbp-51h] BYREF
  void *Block; // [rsp+80h] [rbp-49h] BYREF
  MEMORY_MAPPED_PIPE *v128; // [rsp+88h] [rbp-41h] BYREF
  struct _GUID *v129; // [rsp+90h] [rbp-39h] BYREF
  struct MIDISRV_CLIENTCREATION_PARAMS *v130; // [rsp+98h] [rbp-31h]
  int v131[2]; // [rsp+A0h] [rbp-29h] BYREF
  _DWORD *v132; // [rsp+A8h] [rbp-21h]
  GUID pguid; // [rsp+B0h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+3Fh]

  v125 = a4;
  v130 = a7;
  lpTargetHandle = a8;
  v132 = a9;
  v13 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v13 > 4u )
  {
    LODWORD(pv) = a6;
    v129 = a5;
    v128 = a3;
    Block = this;
    *(_QWORD *)v131 = "CMidiClientPipe::Initialize";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
      (_DWORD)v13,
      (unsigned int)&dword_1400884AC,
      v14,
      v15,
      (__int64)v131,
      (__int64)&Block,
      (__int64)&v128,
      (__int64)&v129,
      (__int64)&pv);
  }
  *((struct _GUID *)this + 9) = *a5;
  *((_DWORD *)this + 40) = a6;
  v16 = v130;
  if ( *((_DWORD *)v130 + 1) == 1 && a4 <= 0xFu )
  {
    *((_BYTE *)this + 168) = a4;
    *((_DWORD *)this + 41) = 1;
  }
  AcquireSRWLockExclusive((PSRWLOCK)this + 15);
  *(_QWORD *)v131 = (char *)this + 120;
  v17 = 0;
  v128 = 0;
  v18 = 0;
  Block = 0;
  v122 = 0;
  v19 = CMidiPipe::Initialize(this, a3, *((unsigned int *)v16 + 2));
  v20 = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x41,
      (unsigned int)"avcore\\midi2\\service\\exe\\midiclientpipe.cpp",
      (const char *)(unsigned int)v19,
      dwDesiredAccess);
    if ( v122 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v122 + 16LL))(v122);
    goto LABEL_9;
  }
  p_Data1 = (unsigned int *)((char *)v16 + 12);
  v129 = (struct _GUID *)((char *)v16 + 12);
  RequiredBufferSize = GetRequiredBufferSize((unsigned int *)v16 + 3);
  v20 = RequiredBufferSize;
  if ( RequiredBufferSize < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x10,
      (unsigned int)"avcore\\midi2\\service\\exe\\midiclientpipe.cpp",
      (const char *)(unsigned int)RequiredBufferSize,
      dwDesiredAccess);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x43,
      (unsigned int)"avcore\\midi2\\service\\exe\\midiclientpipe.cpp",
      (const char *)v20,
      dwDesiredAccessb);
    if ( v122 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v122 + 16LL))(v122);
    goto LABEL_9;
  }
  if ( (*((_DWORD *)this + 14) & 0xFFFFFFFD) == 0 )
  {
    v24 = (*(__int64 (__fastcall **)(CMidiClientPipe *, _QWORD))(*(_QWORD *)this + 80LL))(
            this,
            *((unsigned int *)v16 + 1));
    v20 = v24;
    if ( v24 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x48,
        (unsigned int)"avcore\\midi2\\service\\exe\\midiclientpipe.cpp",
        (const char *)(unsigned int)v24,
        dwDesiredAccess);
      if ( v122 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v122 + 16LL))(v122);
      goto LABEL_9;
    }
  }
  if ( (unsigned int)(*((_DWORD *)this + 14) - 1) <= 1 )
  {
    v25 = (*(__int64 (__fastcall **)(CMidiClientPipe *, _QWORD))(*(_QWORD *)this + 88LL))(
            this,
            *((unsigned int *)v16 + 1));
    v20 = v25;
    if ( v25 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4D,
        (unsigned int)"avcore\\midi2\\service\\exe\\midiclientpipe.cpp",
        (const char *)(unsigned int)v25,
        dwDesiredAccess);
      if ( v122 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v122 + 16LL))(v122);
      goto LABEL_9;
    }
  }
  p_lpTargetHandle = &lpTargetHandle;
  v124 = 1;
  *((_DWORD *)this + 43) = *(_DWORD *)v16 & 0xFFFFFFFE;
  *((_DWORD *)this + 44) = *(_DWORD *)v16;
  if ( (*((_DWORD *)this + 14) & 0xFFFFFFFD) == 0 )
  {
    pguid = 0;
    pv = 0;
    v26 = (char *)operator new(0x68u, (const struct std::nothrow_t *)&std::nothrow);
    v17 = v26;
    if ( !v26 )
    {
      v128 = 0;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x68,
        (unsigned int)"avcore\\midi2\\service\\exe\\midiclientpipe.cpp",
        (const char *)0x8007000ELL,
        dwDesiredAccess);
      if ( pv )
        CoTaskMemFree(pv);
      v124 = 0;
      CMidiClientPipe::Initialize_::_2_::_lambda_1_::operator()(&p_lpTargetHandle);
      if ( v122 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v122 + 16LL))(v122);
      goto LABEL_241;
    }
    *(_QWORD *)v26 = 0;
    *((_QWORD *)v26 + 1) = 0;
    *((_QWORD *)v26 + 2) = 0;
    *((_QWORD *)v26 + 3) = 0;
    *((_DWORD *)v26 + 8) = 0;
    *((_QWORD *)v26 + 5) = 0;
    *((_QWORD *)v26 + 6) = 0;
    *((_QWORD *)v26 + 7) = 0;
    *((_QWORD *)v26 + 8) = 0;
    *(_OWORD *)(v26 + 72) = 0;
    *((_QWORD *)v26 + 11) = 0;
    *((_QWORD *)v26 + 12) = 7;
    *((_WORD *)v26 + 36) = 0;
    v128 = (MEMORY_MAPPED_PIPE *)v26;
    *(_DWORD *)v26 = *((_DWORD *)v16 + 1);
    *((_DWORD *)v26 + 1) = *((_DWORD *)this + 43);
    v27 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v27 )
    {
      *v27 = 0;
      v27[1] = 0;
      v27[2] = 0;
    }
    else
    {
      v27 = 0;
    }
    v28 = *((_QWORD *)v17 + 1);
    *((_QWORD *)v17 + 1) = v27;
    if ( v28 )
    {
      v29 = *(const void **)(v28 + 16);
      if ( v29 )
        UnmapViewOfFile(v29);
      v30 = *(const void **)(v28 + 8);
      if ( v30 )
        UnmapViewOfFile(v30);
      if ( (unsigned __int64)(*(_QWORD *)v28 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(*(HANDLE *)v28);
      operator delete((void *)v28);
    }
    if ( !*((_QWORD *)v17 + 1) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6E,
        (unsigned int)"avcore\\midi2\\service\\exe\\midiclientpipe.cpp",
        (const char *)0x8007000ELL,
        dwDesiredAccess);
      if ( pv )
        CoTaskMemFree(pv);
      v124 = 0;
      CMidiClientPipe::Initialize_::_2_::_lambda_1_::operator()(&p_lpTargetHandle);
      if ( v122 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v122 + 16LL))(v122);
      goto LABEL_240;
    }
    v31 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v31 )
    {
      *v31 = 0;
      v31[1] = 0;
      v31[2] = 0;
    }
    else
    {
      v31 = 0;
    }
    v32 = *((_QWORD *)v17 + 2);
    *((_QWORD *)v17 + 2) = v31;
    if ( v32 )
    {
      v33 = *(const void **)(v32 + 16);
      if ( v33 )
        UnmapViewOfFile(v33);
      v34 = *(const void **)(v32 + 8);
      if ( v34 )
        UnmapViewOfFile(v34);
      if ( (unsigned __int64)(*(_QWORD *)v32 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(*(HANDLE *)v32);
      operator delete((void *)v32);
    }
    if ( !*((_QWORD *)v17 + 2) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x71,
        (unsigned int)"avcore\\midi2\\service\\exe\\midiclientpipe.cpp",
        (const char *)0x8007000ELL,
        dwDesiredAccess);
      if ( pv )
        CoTaskMemFree(pv);
      v124 = 0;
      CMidiClientPipe::Initialize_::_2_::_lambda_1_::operator()(&p_lpTargetHandle);
      if ( v122 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v122 + 16LL))(v122);
      goto LABEL_240;
    }
    MappedDataBuffer = CreateMappedDataBuffer(
                         *p_Data1,
                         *((struct MEMORY_MAPPED_BUFFER **)v17 + 1),
                         (struct MEMORY_MAPPED_DATA *)(v17 + 24));
    v20 = MappedDataBuffer;
    if ( MappedDataBuffer < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x74,
        (unsigned int)"avcore\\midi2\\service\\exe\\midiclientpipe.cpp",
        (const char *)(unsigned int)MappedDataBuffer,
        dwDesiredAccess);
      if ( pv )
        CoTaskMemFree(pv);
      v124 = 0;
      CMidiClientPipe::Initialize_::_2_::_lambda_1_::operator()(&p_lpTargetHandle);
      if ( v122 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v122 + 16LL))(v122);
LABEL_67:
      MEMORY_MAPPED_PIPE::~MEMORY_MAPPED_PIPE((MEMORY_MAPPED_PIPE *)v17);
      operator delete(v17);
LABEL_9:
      if ( this != (CMidiClientPipe *)-120LL )
        ReleaseSRWLockExclusive((PSRWLOCK)this + 15);
      return v20;
    }
    MappedRegisters = CreateMappedRegisters(
                        *((struct MEMORY_MAPPED_BUFFER **)v17 + 2),
                        (struct MEMORY_MAPPED_REGISTERS *)(v17 + 40));
    v20 = MappedRegisters;
    if ( MappedRegisters < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x75,
        (unsigned int)"avcore\\midi2\\service\\exe\\midiclientpipe.cpp",
        (const char *)(unsigned int)MappedRegisters,
        dwDesiredAccess);
      if ( pv )
        CoTaskMemFree(pv);
      v124 = 0;
      CMidiClientPipe::Initialize_::_2_::_lambda_1_::operator()(&p_lpTargetHandle);
      if ( v122 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v122 + 16LL))(v122);
      goto LABEL_67;
    }
    _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(v17 + 56);
    v37 = CoCreateGuid(&pguid);
    v20 = v37;
    if ( v37 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x79,
        (unsigned int)"avcore\\midi2\\service\\exe\\midiclientpipe.cpp",
        (const char *)(unsigned int)v37,
        dwDesiredAccess);
      if ( pv )
        CoTaskMemFree(pv);
      v124 = 0;
      CMidiClientPipe::Initialize_::_2_::_lambda_1_::operator()(&p_lpTargetHandle);
      if ( v122 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v122 + 16LL))(v122);
      goto LABEL_67;
    }
    v38 = pv;
    if ( pv )
    {
      LastError = GetLastError();
      CoTaskMemFree(v38);
      SetLastError(LastError);
    }
    pv = 0;
    v40 = StringFromCLSID(&pguid, (LPOLESTR *)&pv);
    v20 = v40;
    if ( v40 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7A,
        (unsigned int)"avcore\\midi2\\service\\exe\\midiclientpipe.cpp",
        (const char *)(unsigned int)v40,
        dwDesiredAccess);
      if ( pv )
        CoTaskMemFree(pv);
      v124 = 0;
      CMidiClientPipe::Initialize_::_2_::_lambda_1_::operator()(&p_lpTargetHandle);
      if ( v122 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v122 + 16LL))(v122);
      goto LABEL_67;
    }
    v42 = (const WCHAR *)(v17 + 72);
    if ( *((_QWORD *)v17 + 12) < 7u )
    {
      ____Reallocate_for_V_lambda_1___1_____Assign_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV23_QEBG_K_Z_PEBG___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign_G_01_AEAAAEAV01_QEBG0_Z_PEBG_Z(
        v17 + 72,
        7,
        v41,
        L"Global\\");
    }
    else
    {
      if ( *((_QWORD *)v17 + 12) <= 7u )
        v43 = (WCHAR *)(v17 + 72);
      else
        v43 = *(WCHAR **)v42;
      *((_QWORD *)v17 + 11) = 7;
      memmove_0(v43, L"Global\\", 0xEu);
      v43[7] = 0;
    }
    std::wstring::operator+=(v17 + 72, pv);
    if ( *((_QWORD *)v17 + 12) > 7u )
      v42 = *(const WCHAR **)v42;
    EventW = CreateEventW(0, 1, 0, v42);
    v45 = (void *)*((_QWORD *)v17 + 8);
    if ( v45 )
    {
      v46 = GetLastError();
      if ( !CloseHandle(v45) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v47, v48);
      SetLastError(v46);
    }
    *((_QWORD *)v17 + 8) = EventW;
    v49 = lpTargetHandle;
    CurrentProcess = GetCurrentProcess();
    v51 = (void *)**((_QWORD **)v17 + 1);
    v52 = GetCurrentProcess();
    if ( !DuplicateHandle(v52, v51, CurrentProcess, v49 + 4, 2u, 1, 0) )
    {
      v20 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x80,
              (unsigned int)"avcore\\midi2\\service\\exe\\midiclientpipe.cpp",
              v53);
      if ( pv )
        CoTaskMemFree(pv);
      v124 = 0;
      CMidiClientPipe::Initialize_::_2_::_lambda_1_::operator()(&p_lpTargetHandle);
      if ( v122 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v122 + 16LL))(v122);
      goto LABEL_67;
    }
    v54 = lpTargetHandle;
    v55 = GetCurrentProcess();
    v56 = (void *)**((_QWORD **)v17 + 2);
    v57 = GetCurrentProcess();
    if ( !DuplicateHandle(v57, v56, v55, v54 + 5, 2u, 1, 0) )
    {
      v20 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x81,
              (unsigned int)"avcore\\midi2\\service\\exe\\midiclientpipe.cpp",
              v58);
      if ( pv )
        CoTaskMemFree(pv);
      v124 = 0;
      CMidiClientPipe::Initialize_::_2_::_lambda_1_::operator()(&p_lpTargetHandle);
      if ( v122 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v122 + 16LL))(v122);
      goto LABEL_67;
    }
    v59 = lpTargetHandle;
    v60 = GetCurrentProcess();
    v61 = (void *)*((_QWORD *)v17 + 7);
    v62 = GetCurrentProcess();
    if ( !DuplicateHandle(v62, v61, v60, v59, 0x1F0003u, 1, 0) )
    {
      v20 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x82,
              (unsigned int)"avcore\\midi2\\service\\exe\\midiclientpipe.cpp",
              v63);
      if ( pv )
        CoTaskMemFree(pv);
      v124 = 0;
      CMidiClientPipe::Initialize_::_2_::_lambda_1_::operator()(&p_lpTargetHandle);
      if ( v122 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v122 + 16LL))(v122);
      goto LABEL_67;
    }
    v64 = lpTargetHandle;
    v65 = GetCurrentProcess();
    v66 = (void *)*((_QWORD *)v17 + 8);
    v67 = GetCurrentProcess();
    if ( !DuplicateHandle(v67, v66, v65, v64 + 1, 0x1F0003u, 1, 0) )
    {
      v20 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x83,
              (unsigned int)"avcore\\midi2\\service\\exe\\midiclientpipe.cpp",
              v68);
      if ( pv )
        CoTaskMemFree(pv);
      v124 = 0;
      CMidiClientPipe::Initialize_::_2_::_lambda_1_::operator()(&p_lpTargetHandle);
      if ( v122 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v122 + 16LL))(v122);
      goto LABEL_67;
    }
    *((_DWORD *)lpTargetHandle + 16) = *((_DWORD *)v17 + 8);
    if ( pv )
      CoTaskMemFree(pv);
    p_Data1 = &v129->Data1;
    v16 = v130;
  }
  if ( (unsigned int)(*((_DWORD *)this + 14) - 1) <= 1 )
  {
    pguid = 0;
    pv = 0;
    v69 = operator new(0x68u, (const struct std::nothrow_t *)&std::nothrow);
    v18 = v69;
    if ( !v69 )
    {
      Block = 0;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8D,
        (unsigned int)"avcore\\midi2\\service\\exe\\midiclientpipe.cpp",
        (const char *)0x8007000ELL,
        dwDesiredAccess);
      if ( pv )
        CoTaskMemFree(pv);
      v124 = 0;
      CMidiClientPipe::Initialize_::_2_::_lambda_1_::operator()(&p_lpTargetHandle);
      if ( v122 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v122 + 16LL))(v122);
      goto LABEL_239;
    }
    *(_QWORD *)v69 = 0;
    *((_QWORD *)v69 + 1) = 0;
    *((_QWORD *)v69 + 2) = 0;
    *((_QWORD *)v69 + 3) = 0;
    v69[8] = 0;
    *((_QWORD *)v69 + 5) = 0;
    *((_QWORD *)v69 + 6) = 0;
    *((_QWORD *)v69 + 7) = 0;
    *((_QWORD *)v69 + 8) = 0;
    *(_OWORD *)(v69 + 18) = 0;
    *((_QWORD *)v69 + 11) = 0;
    *((_QWORD *)v69 + 12) = 7;
    *((_WORD *)v69 + 36) = 0;
    Block = v69;
    *v69 = *((_DWORD *)v16 + 1);
    v69[1] = *((_DWORD *)this + 44);
    v70 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v70 )
    {
      *v70 = 0;
      v70[1] = 0;
      v70[2] = 0;
    }
    else
    {
      v70 = 0;
    }
    v71 = *((_QWORD *)v18 + 1);
    *((_QWORD *)v18 + 1) = v70;
    if ( v71 )
    {
      v72 = *(const void **)(v71 + 16);
      if ( v72 )
        UnmapViewOfFile(v72);
      v73 = *(const void **)(v71 + 8);
      if ( v73 )
        UnmapViewOfFile(v73);
      if ( (unsigned __int64)(*(_QWORD *)v71 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(*(HANDLE *)v71);
      operator delete((void *)v71);
    }
    if ( !*((_QWORD *)v18 + 1) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x93,
        (unsigned int)"avcore\\midi2\\service\\exe\\midiclientpipe.cpp",
        (const char *)0x8007000ELL,
        dwDesiredAccess);
      if ( pv )
        CoTaskMemFree(pv);
      v124 = 0;
      CMidiClientPipe::Initialize_::_2_::_lambda_1_::operator()(&p_lpTargetHandle);
      if ( v122 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v122 + 16LL))(v122);
LABEL_149:
      MEMORY_MAPPED_PIPE::~MEMORY_MAPPED_PIPE((MEMORY_MAPPED_PIPE *)v18);
      operator delete(v18);
      goto LABEL_239;
    }
    v74 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v74 )
    {
      *v74 = 0;
      v74[1] = 0;
      v74[2] = 0;
    }
    else
    {
      v74 = 0;
    }
    v75 = *((_QWORD *)v18 + 2);
    *((_QWORD *)v18 + 2) = v74;
    if ( v75 )
    {
      v76 = *(const void **)(v75 + 16);
      if ( v76 )
        UnmapViewOfFile(v76);
      v77 = *(const void **)(v75 + 8);
      if ( v77 )
        UnmapViewOfFile(v77);
      if ( (unsigned __int64)(*(_QWORD *)v75 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(*(HANDLE *)v75);
      operator delete((void *)v75);
    }
    if ( !*((_QWORD *)v18 + 2) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x96,
        (unsigned int)"avcore\\midi2\\service\\exe\\midiclientpipe.cpp",
        (const char *)0x8007000ELL,
        dwDesiredAccess);
      if ( pv )
        CoTaskMemFree(pv);
      v124 = 0;
      CMidiClientPipe::Initialize_::_2_::_lambda_1_::operator()(&p_lpTargetHandle);
      if ( v122 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v122 + 16LL))(v122);
      goto LABEL_149;
    }
    v78 = CreateMappedDataBuffer(
            *p_Data1,
            *((struct MEMORY_MAPPED_BUFFER **)v18 + 1),
            (struct MEMORY_MAPPED_DATA *)(v18 + 6));
    v20 = v78;
    if ( v78 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x99,
        (unsigned int)"avcore\\midi2\\service\\exe\\midiclientpipe.cpp",
        (const char *)(unsigned int)v78,
        dwDesiredAccess);
      if ( pv )
        CoTaskMemFree(pv);
      v124 = 0;
      CMidiClientPipe::Initialize_::_2_::_lambda_1_::operator()(&p_lpTargetHandle);
      if ( v122 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v122 + 16LL))(v122);
      goto LABEL_172;
    }
    v79 = CreateMappedRegisters(
            *((struct MEMORY_MAPPED_BUFFER **)v18 + 2),
            (struct MEMORY_MAPPED_REGISTERS *)(v18 + 10));
    v20 = v79;
    if ( v79 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x9A,
        (unsigned int)"avcore\\midi2\\service\\exe\\midiclientpipe.cpp",
        (const char *)(unsigned int)v79,
        dwDesiredAccess);
      if ( pv )
        CoTaskMemFree(pv);
      v124 = 0;
      CMidiClientPipe::Initialize_::_2_::_lambda_1_::operator()(&p_lpTargetHandle);
      if ( v122 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v122 + 16LL))(v122);
      goto LABEL_172;
    }
    _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(v18 + 14);
    v80 = CoCreateGuid(&pguid);
    v20 = v80;
    if ( v80 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x9E,
        (unsigned int)"avcore\\midi2\\service\\exe\\midiclientpipe.cpp",
        (const char *)(unsigned int)v80,
        dwDesiredAccess);
      if ( pv )
        CoTaskMemFree(pv);
      v124 = 0;
      CMidiClientPipe::Initialize_::_2_::_lambda_1_::operator()(&p_lpTargetHandle);
      if ( v122 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v122 + 16LL))(v122);
      goto LABEL_172;
    }
    v81 = pv;
    if ( pv )
    {
      v82 = GetLastError();
      CoTaskMemFree(v81);
      SetLastError(v82);
    }
    pv = 0;
    v83 = StringFromCLSID(&pguid, (LPOLESTR *)&pv);
    v20 = v83;
    if ( v83 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x9F,
        (unsigned int)"avcore\\midi2\\service\\exe\\midiclientpipe.cpp",
        (const char *)(unsigned int)v83,
        dwDesiredAccess);
      if ( pv )
        CoTaskMemFree(pv);
      v124 = 0;
      CMidiClientPipe::Initialize_::_2_::_lambda_1_::operator()(&p_lpTargetHandle);
      if ( v122 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v122 + 16LL))(v122);
      goto LABEL_172;
    }
    v84 = (const WCHAR *)(v18 + 18);
    std::wstring::operator=(v18 + 18, L"Global\\");
    std::wstring::operator+=(v18 + 18, pv);
    if ( *((_QWORD *)v18 + 12) > 7u )
      v84 = *(const WCHAR **)v84;
    v85 = CreateEventW(0, 1, 0, v84);
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      v18 + 16,
      v85);
    v86 = lpTargetHandle;
    v87 = GetCurrentProcess();
    v88 = (void *)**((_QWORD **)v18 + 1);
    v89 = GetCurrentProcess();
    if ( !DuplicateHandle(v89, v88, v87, v86 + 6, 2u, 0, 0) )
    {
      v20 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0xA5,
              (unsigned int)"avcore\\midi2\\service\\exe\\midiclientpipe.cpp",
              v90);
      if ( pv )
        CoTaskMemFree(pv);
      v124 = 0;
      CMidiClientPipe::Initialize_::_2_::_lambda_1_::operator()(&p_lpTargetHandle);
      if ( v122 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v122 + 16LL))(v122);
      goto LABEL_172;
    }
    v91 = lpTargetHandle;
    v92 = GetCurrentProcess();
    v93 = (void *)**((_QWORD **)v18 + 2);
    v94 = GetCurrentProcess();
    if ( !DuplicateHandle(v94, v93, v92, v91 + 7, 2u, 0, 0) )
    {
      v20 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0xA6,
              (unsigned int)"avcore\\midi2\\service\\exe\\midiclientpipe.cpp",
              v95);
      if ( pv )
        CoTaskMemFree(pv);
      v124 = 0;
      CMidiClientPipe::Initialize_::_2_::_lambda_1_::operator()(&p_lpTargetHandle);
      if ( v122 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v122 + 16LL))(v122);
      goto LABEL_172;
    }
    v96 = lpTargetHandle;
    v97 = GetCurrentProcess();
    v98 = (void *)*((_QWORD *)v18 + 7);
    v99 = GetCurrentProcess();
    if ( !DuplicateHandle(v99, v98, v97, v96 + 2, 0x1F0003u, 1, 0) )
    {
      v20 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0xA7,
              (unsigned int)"avcore\\midi2\\service\\exe\\midiclientpipe.cpp",
              v100);
      if ( pv )
        CoTaskMemFree(pv);
      v124 = 0;
      CMidiClientPipe::Initialize_::_2_::_lambda_1_::operator()(&p_lpTargetHandle);
      if ( v122 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v122 + 16LL))(v122);
      goto LABEL_172;
    }
    v101 = lpTargetHandle;
    v102 = GetCurrentProcess();
    v103 = (void *)*((_QWORD *)v18 + 8);
    v104 = GetCurrentProcess();
    if ( !DuplicateHandle(v104, v103, v102, v101 + 3, 0x1F0003u, 1, 0) )
    {
      v20 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0xA8,
              (unsigned int)"avcore\\midi2\\service\\exe\\midiclientpipe.cpp",
              v105);
      if ( pv )
        CoTaskMemFree(pv);
      v124 = 0;
      CMidiClientPipe::Initialize_::_2_::_lambda_1_::operator()(&p_lpTargetHandle);
      if ( v122 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v122 + 16LL))(v122);
      goto LABEL_172;
    }
    *((_DWORD *)lpTargetHandle + 17) = v18[8];
    if ( pv )
      CoTaskMemFree(pv);
  }
  v106 = (char *)operator new(0x90u, (const struct std::nothrow_t *)&std::nothrow);
  v107 = v106;
  v129 = (struct _GUID *)v106;
  if ( v106 )
  {
    *(_DWORD *)v106 = 1;
    InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v106 + 8), 0, 0);
    v107[48] = 0;
    *((_DWORD *)v107 + 13) = 0;
    *((_QWORD *)v107 + 7) = 0;
    *((_QWORD *)v107 + 8) = 0;
    *((_QWORD *)v107 + 9) = 0;
    *((_DWORD *)v107 + 20) = 0;
    *((_QWORD *)v107 + 11) = 0;
    *((_QWORD *)v107 + 12) = 0;
    *((_QWORD *)v107 + 13) = 0;
    *((_QWORD *)v107 + 14) = 0;
    *((_QWORD *)v107 + 15) = 0;
    *((_QWORD *)v107 + 16) = 0;
    *((_QWORD *)v107 + 17) = 0;
  }
  else
  {
    v107 = 0;
  }
  v108 = (CMidiXProc *)*((_QWORD *)this + 17);
  *((_QWORD *)this + 17) = v107;
  if ( v108 )
  {
    CMidiXProc::~CMidiXProc(v108);
    operator delete(v108);
  }
  if ( !*((_QWORD *)this + 17) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAD,
      (unsigned int)"avcore\\midi2\\service\\exe\\midiclientpipe.cpp",
      (const char *)0x8007000ELL,
      dwDesiredAccess);
    v124 = 0;
    CMidiClientPipe::Initialize_::_2_::_lambda_1_::operator()(&p_lpTargetHandle);
    if ( v122 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v122 + 16LL))(v122);
    if ( v18 )
    {
      MEMORY_MAPPED_PIPE::~MEMORY_MAPPED_PIPE((MEMORY_MAPPED_PIPE *)v18);
      operator delete(v18);
    }
    if ( !v17 )
      goto LABEL_241;
LABEL_239:
    if ( !v17 )
    {
LABEL_241:
      if ( this != (CMidiClientPipe *)-120LL )
        ReleaseSRWLockExclusive((PSRWLOCK)this + 15);
      return 2147942414LL;
    }
LABEL_240:
    MEMORY_MAPPED_PIPE::~MEMORY_MAPPED_PIPE((MEMORY_MAPPED_PIPE *)v17);
    operator delete(v17);
    goto LABEL_241;
  }
  v109 = **(__int64 (__fastcall ***)(CMidiClientPipe *, GUID *, __int64 *))this;
  v110 = v122;
  v122 = 0;
  if ( v110 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v110 + 16LL))(v110);
  v111 = v109(this, &GUID_4d6a29e5_df4f_4a2d_a923_9b23b3f2d6f6, &v122);
  v20 = v111;
  if ( v111 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAF,
      (unsigned int)"avcore\\midi2\\service\\exe\\midiclientpipe.cpp",
      (const char *)(unsigned int)v111,
      dwDesiredAccess);
    v124 = 0;
    CMidiClientPipe::Initialize_::_2_::_lambda_1_::operator()(&p_lpTargetHandle);
    if ( v122 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v122 + 16LL))(v122);
    if ( !v18 )
    {
LABEL_173:
      if ( !v17 )
        goto LABEL_9;
      goto LABEL_67;
    }
LABEL_172:
    MEMORY_MAPPED_PIPE::~MEMORY_MAPPED_PIPE((MEMORY_MAPPED_PIPE *)v18);
    operator delete(v18);
    goto LABEL_173;
  }
  v112 = CMidiXProc::Initialize(*((char **)this + 17), v132, (_DWORD **)&Block, (int **)&v128, v122, v125, a10);
  v113 = v112;
  if ( v112 >= 0 )
  {
    if ( v122 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v122 + 16LL))(v122);
    v116 = Block;
    if ( Block )
    {
      MEMORY_MAPPED_PIPE::~MEMORY_MAPPED_PIPE((MEMORY_MAPPED_PIPE *)Block);
      operator delete(v116);
    }
    v117 = v128;
    if ( v128 )
    {
      MEMORY_MAPPED_PIPE::~MEMORY_MAPPED_PIPE(v128);
      operator delete(v117);
    }
    if ( this != (CMidiClientPipe *)-120LL )
      ReleaseSRWLockExclusive((PSRWLOCK)this + 15);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB7,
      (unsigned int)"avcore\\midi2\\service\\exe\\midiclientpipe.cpp",
      (const char *)(unsigned int)v112,
      dwDesiredAccessa);
    v124 = 0;
    CMidiClientPipe::Initialize_::_2_::_lambda_1_::operator()(&p_lpTargetHandle);
    if ( v122 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v122 + 16LL))(v122);
    v114 = Block;
    if ( Block )
    {
      MEMORY_MAPPED_PIPE::~MEMORY_MAPPED_PIPE((MEMORY_MAPPED_PIPE *)Block);
      operator delete(v114);
    }
    v115 = v128;
    if ( v128 )
    {
      MEMORY_MAPPED_PIPE::~MEMORY_MAPPED_PIPE(v128);
      operator delete(v115);
    }
    if ( this != (CMidiClientPipe *)-120LL )
      ReleaseSRWLockExclusive((PSRWLOCK)this + 15);
    return v113;
  }
}

```

## disassembly

```asm
0x14001fe88  mov     [rsp-8+arg_8], rbx
0x14001fe8d  push    rbp
0x14001fe8e  push    rsi
0x14001fe8f  push    rdi
0x14001fe90  push    r12
0x14001fe92  push    r13
0x14001fe94  push    r14
0x14001fe96  push    r15
0x14001fe98  lea     rbp, [rsp-7]
0x14001fe9d  sub     rsp, 0D0h
0x14001fea4  mov     rax, cs:__security_cookie
0x14001feab  xor     rax, rsp
0x14001feae  mov     [rbp+37h+var_40], rax
0x14001feb2  mov     r14b, r9b
0x14001feb5  mov     [rbp+37h+var_90], r9b
0x14001feb9  mov     rsi, r8
0x14001febc  mov     r13, rcx
0x14001febf  mov     rax, [rbp+37h+arg_30]
0x14001fec3  mov     [rbp+37h+var_68], rax
0x14001fec7  mov     rax, [rbp+37h+arg_38]
0x14001fecb  mov     [rbp+37h+lpTargetHandle], rax
0x14001fecf  mov     rax, [rbp+37h+arg_40]
0x14001fed6  mov     [rbp+37h+var_58], rax
0x14001feda  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14001fedf  mov     rcx, [rax+8]
0x14001fee3  mov     eax, [rcx]
0x14001fee5  mov     ebx, [rbp+37h+arg_28]
0x14001fee8  mov     rdi, [rbp+37h+arg_20]
0x14001feec  cmp     eax, 4
0x14001feef  jbe     short loc_14001FF44
0x14001fef1  mov     dword ptr [rbp+37h+pv], ebx
0x14001fef4  mov     [rbp+37h+var_70], rdi
0x14001fef8  mov     [rbp+37h+var_78], rsi
0x14001fefc  mov     [rbp+37h+Block], r13
0x14001ff00  lea     rax, aCmidiclientpip; "CMidiClientPipe::Initialize"
0x14001ff07  mov     qword ptr [rbp+37h+var_60], rax
0x14001ff0b  lea     rax, [rbp+37h+pv]
0x14001ff0f  mov     [rsp+100h+var_C0], rax
0x14001ff14  lea     rax, [rbp+37h+var_70]
0x14001ff18  mov     [rsp+100h+var_C8], rax
0x14001ff1d  lea     rax, [rbp+37h+var_78]
0x14001ff21  mov     qword ptr [rsp+100h+dwOptions], rax
0x14001ff26  lea     rax, [rbp+37h+Block]
0x14001ff2a  mov     qword ptr [rsp+100h+bInheritHandle], rax
0x14001ff2f  lea     rax, [rbp+37h+var_60]
0x14001ff33  mov     qword ptr [rsp+100h+dwDesiredAccess], rax; int
0x14001ff38  lea     rdx, dword_1400884AC
0x14001ff3f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)
0x14001ff44  movups  xmm0, xmmword ptr [rdi]
0x14001ff47  movdqu  xmmword ptr [r13+90h], xmm0
0x14001ff50  mov     [r13+0A0h], ebx
0x14001ff57  mov     rdi, [rbp+37h+var_68]
0x14001ff5b  cmp     dword ptr [rdi+4], 1
0x14001ff5f  jnz     short loc_14001FF79
0x14001ff61  cmp     r14b, 0Fh
0x14001ff65  ja      short loc_14001FF79
0x14001ff67  mov     [r13+0A8h], r14b
0x14001ff6e  mov     dword ptr [r13+0A4h], 1
0x14001ff79  lea     r15, [r13+78h]
0x14001ff7d  mov     rcx, r15; SRWLock
0x14001ff80  call    cs:__imp_AcquireSRWLockExclusive
0x14001ff86  mov     qword ptr [rbp+37h+var_60], r15
0x14001ff8a  xor     r14d, r14d
0x14001ff8d  mov     [rbp+37h+var_78], r14
0x14001ff91  xor     r12d, r12d
0x14001ff94  mov     [rbp+37h+Block], r12
0x14001ff98  mov     [rbp+37h+var_A8], r12
0x14001ff9c  mov     r8d, [rdi+8]
0x14001ffa0  mov     rdx, rsi
0x14001ffa3  mov     rcx, r13
0x14001ffa6  call    ?Initialize@CMidiPipe@@UEAAJPEBGW4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0002@@@Z; CMidiPipe::Initialize(ushort const *,__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0002)
0x14001ffab  mov     ebx, eax
0x14001ffad  test    eax, eax
0x14001ffaf  jns     short loc_14001FFF4
0x14001ffb1  mov     rcx, [rbp+3Fh]; this
0x14001ffb5  mov     r9d, eax; char *
0x14001ffb8  lea     r8, aAvcoreMidi2Ser_2; "avcore\\midi2\\service\\exe\\midiclient"...
0x14001ffbf  lea     edx, [r14+41h]; void *
0x14001ffc3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001ffc8  nop
0x14001ffc9  mov     rcx, [rbp+37h+var_A8]
0x14001ffcd  test    rcx, rcx
0x14001ffd0  jz      short loc_14001FFDF
0x14001ffd2  mov     rax, [rcx]
0x14001ffd5  mov     rax, [rax+10h]
0x14001ffd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001ffde  nop
0x14001ffdf  test    r15, r15
0x14001ffe2  jz      short loc_14001FFED
0x14001ffe4  mov     rcx, r15; SRWLock
0x14001ffe7  call    cs:__imp_ReleaseSRWLockExclusive
0x14001ffed  mov     eax, ebx
0x14001ffef  jmp     loc_1400212D7
0x14001fff4  lea     rsi, [rdi+0Ch]
0x14001fff8  mov     [rbp+37h+var_70], rsi
0x14001fffc  mov     rcx, rsi; unsigned int *
0x14001ffff  call    ?GetRequiredBufferSize@@YAJAEAK@Z; GetRequiredBufferSize(ulong &)
0x140020004  mov     ebx, eax
0x140020006  test    eax, eax
0x140020008  jns     short loc_140020053
0x14002000a  mov     rcx, [rbp+3Fh]; this
0x14002000e  mov     r9d, eax; char *
0x140020011  lea     r8, aAvcoreMidi2Ser_2; "avcore\\midi2\\service\\exe\\midiclient"...
0x140020018  mov     edx, 10h; void *
0x14002001d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140020022  mov     rcx, [rbp+3Fh]; this
0x140020026  mov     r9d, ebx; char *
0x140020029  lea     r8, aAvcoreMidi2Ser_2; "avcore\\midi2\\service\\exe\\midiclient"...
0x140020030  mov     edx, 43h ; 'C'; void *
0x140020035  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002003a  nop
0x14002003b  mov     rcx, [rbp+37h+var_A8]
0x14002003f  test    rcx, rcx
0x140020042  jz      short loc_140020051
0x140020044  mov     rax, [rcx]
0x140020047  mov     rax, [rax+10h]
0x14002004b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140020050  nop
0x140020051  jmp     short loc_14001FFDF
0x140020053  test    dword ptr [r13+38h], 0FFFFFFFDh
0x14002005b  jnz     short loc_1400200AA
0x14002005d  mov     rax, [r13+0]
0x140020061  mov     edx, [rdi+4]
0x140020064  mov     rcx, r13
0x140020067  mov     rax, [rax+50h]
0x14002006b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140020070  mov     ebx, eax
0x140020072  test    eax, eax
0x140020074  jns     short loc_1400200AA
0x140020076  mov     rcx, [rbp+3Fh]; this
0x14002007a  mov     r9d, eax; char *
0x14002007d  lea     r8, aAvcoreMidi2Ser_2; "avcore\\midi2\\service\\exe\\midiclient"...
0x140020084  mov     edx, 48h ; 'H'; void *
0x140020089  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002008e  nop
0x14002008f  mov     rcx, [rbp+37h+var_A8]
0x140020093  test    rcx, rcx
0x140020096  jz      short loc_1400200A5
0x140020098  mov     rax, [rcx]
0x14002009b  mov     rax, [rax+10h]
0x14002009f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400200a4  nop
0x1400200a5  jmp     loc_14001FFDF
0x1400200aa  mov     eax, [r13+38h]
0x1400200ae  dec     eax
0x1400200b0  cmp     eax, 1
0x1400200b3  ja      short loc_140020102
0x1400200b5  mov     rax, [r13+0]
0x1400200b9  mov     edx, [rdi+4]
0x1400200bc  mov     rcx, r13
0x1400200bf  mov     rax, [rax+58h]
0x1400200c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400200c8  mov     ebx, eax
0x1400200ca  test    eax, eax
0x1400200cc  jns     short loc_140020102
0x1400200ce  mov     rcx, [rbp+3Fh]; this
0x1400200d2  mov     r9d, eax; char *
0x1400200d5  lea     r8, aAvcoreMidi2Ser_2; "avcore\\midi2\\service\\exe\\midiclient"...
0x1400200dc  mov     edx, 4Dh ; 'M'; void *
0x1400200e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400200e6  nop
0x1400200e7  mov     rcx, [rbp+37h+var_A8]
0x1400200eb  test    rcx, rcx
0x1400200ee  jz      short loc_1400200FD
0x1400200f0  mov     rax, [rcx]
0x1400200f3  mov     rax, [rax+10h]
0x1400200f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400200fc  nop
0x1400200fd  jmp     loc_14001FFDF
0x140020102  lea     rax, [rbp+37h+lpTargetHandle]
0x140020106  mov     [rbp+37h+var_A0], rax
0x14002010a  mov     [rbp+37h+var_98], 1
0x14002010e  mov     eax, [rdi]
0x140020110  and     eax, 0FFFFFFFEh
0x140020113  mov     [r13+0ACh], eax
0x14002011a  mov     eax, [rdi]
0x14002011c  mov     [r13+0B0h], eax
0x140020123  xor     ebx, ebx
0x140020125  test    dword ptr [r13+38h], 0FFFFFFFDh
0x14002012d  jnz     loc_140020841
0x140020133  xorps   xmm0, xmm0
0x140020136  movups  xmmword ptr [rbp+37h+pguid.Data1], xmm0
0x14002013a  mov     [rbp+37h+pv], rbx
0x14002013e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140020145  lea     ecx, [rbx+68h]; unsigned __int64
0x140020148  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14002014d  mov     r14, rax
0x140020150  test    rax, rax
0x140020153  jz      loc_1400208F1
0x140020159  mov     [rax], rbx
0x14002015c  mov     [rax+8], rbx
0x140020160  mov     [rax+10h], rbx
0x140020164  mov     [rax+18h], rbx
0x140020168  mov     [rax+20h], ebx
0x14002016b  mov     [rax+28h], rbx
0x14002016f  mov     [rax+30h], rbx
0x140020173  mov     [rax+38h], rbx
0x140020177  mov     [rax+40h], rbx
0x14002017b  xorps   xmm0, xmm0
0x14002017e  movups  xmmword ptr [rax+48h], xmm0
0x140020182  mov     [rax+58h], rbx
0x140020186  mov     qword ptr [rax+60h], 7
0x14002018e  mov     [rax+48h], bx
0x140020192  mov     [rbp+37h+var_78], rax
0x140020196  mov     eax, [rdi+4]
0x140020199  mov     [r14], eax
0x14002019c  mov     eax, [r13+0ACh]
0x1400201a3  mov     [r14+4], eax
0x1400201a7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400201ae  lea     ecx, [rbx+18h]; unsigned __int64
0x1400201b1  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1400201b6  xor     edi, edi
0x1400201b8  test    rax, rax
0x1400201bb  jz      short loc_1400201CA
0x1400201bd  mov     [rax], rdi
0x1400201c0  mov     [rax+8], rdi
0x1400201c4  mov     [rax+10h], rdi
0x1400201c8  jmp     short loc_1400201CD
0x1400201ca  mov     rax, rdi
0x1400201cd  mov     rbx, [r14+8]
0x1400201d1  mov     [r14+8], rax
0x1400201d5  test    rbx, rbx
0x1400201d8  jz      short loc_140020218
0x1400201da  mov     rcx, [rbx+10h]; lpBaseAddress
0x1400201de  test    rcx, rcx
0x1400201e1  jz      short loc_1400201E9
0x1400201e3  call    cs:__imp_UnmapViewOfFile
0x1400201e9  mov     rcx, [rbx+8]; lpBaseAddress
0x1400201ed  test    rcx, rcx
0x1400201f0  jz      short loc_1400201F8
0x1400201f2  call    cs:__imp_UnmapViewOfFile
0x1400201f8  mov     rcx, [rbx]; hObject
0x1400201fb  lea     rax, [rcx-1]
0x1400201ff  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140020203  ja      short loc_14002020B
0x140020205  call    cs:__imp_CloseHandle
0x14002020b  mov     edx, 18h
0x140020210  mov     rcx, rbx; Block
0x140020213  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140020218  cmp     [r14+8], rdi
0x14002021c  jnz     short loc_140020273
0x14002021e  mov     rcx, [rbp+3Fh]; this
0x140020222  mov     r9d, 8007000Eh; char *
0x140020228  lea     r8, aAvcoreMidi2Ser_2; "avcore\\midi2\\service\\exe\\midiclient"...
0x14002022f  mov     edx, 6Eh ; 'n'; void *
0x140020234  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140020239  nop
0x14002023a  mov     rcx, [rbp+37h+pv]; pv
0x14002023e  test    rcx, rcx
0x140020241  jz      short loc_14002024A
0x140020243  call    cs:__imp_CoTaskMemFree
0x140020249  nop
0x14002024a  mov     [rbp+37h+var_98], dil
0x14002024e  lea     rcx, [rbp+37h+var_A0]
0x140020252  call    _CMidiClientPipe__Initialize____2____lambda_1___operator__
0x140020257  nop
0x140020258  mov     rcx, [rbp+37h+var_A8]
0x14002025c  test    rcx, rcx
0x14002025f  jz      short loc_14002026E
0x140020261  mov     rax, [rcx]
0x140020264  mov     rax, [rax+10h]
0x140020268  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002026d  nop
0x14002026e  jmp     loc_1400210F2
0x140020273  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14002027a  mov     ecx, 18h; unsigned __int64
0x14002027f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140020284  test    rax, rax
0x140020287  jz      short loc_140020296
0x140020289  mov     [rax], rdi
0x14002028c  mov     [rax+8], rdi
0x140020290  mov     [rax+10h], rdi
0x140020294  jmp     short loc_140020299
0x140020296  mov     rax, rdi
0x140020299  mov     rbx, [r14+10h]
0x14002029d  mov     [r14+10h], rax
0x1400202a1  test    rbx, rbx
0x1400202a4  jz      short loc_1400202E4
0x1400202a6  mov     rcx, [rbx+10h]; lpBaseAddress
0x1400202aa  test    rcx, rcx
0x1400202ad  jz      short loc_1400202B5
0x1400202af  call    cs:__imp_UnmapViewOfFile
0x1400202b5  mov     rcx, [rbx+8]; lpBaseAddress
0x1400202b9  test    rcx, rcx
0x1400202bc  jz      short loc_1400202C4
0x1400202be  call    cs:__imp_UnmapViewOfFile
0x1400202c4  mov     rcx, [rbx]; hObject
0x1400202c7  lea     rax, [rcx-1]
0x1400202cb  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400202cf  ja      short loc_1400202D7
0x1400202d1  call    cs:__imp_CloseHandle
0x1400202d7  mov     edx, 18h
0x1400202dc  mov     rcx, rbx; Block
0x1400202df  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400202e4  cmp     [r14+10h], rdi
0x1400202e8  jnz     short loc_14002033F
0x1400202ea  mov     rcx, [rbp+3Fh]; this
0x1400202ee  mov     r9d, 8007000Eh; char *
0x1400202f4  lea     r8, aAvcoreMidi2Ser_2; "avcore\\midi2\\service\\exe\\midiclient"...
0x1400202fb  mov     edx, 71h ; 'q'; void *
  ... truncated ...
```
