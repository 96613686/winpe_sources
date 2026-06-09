# CDlpStateXml::~CDlpStateXml(void)

- ea: `0x1802292e8`
- end: `0x1802294b9`
- name: `??1CDlpStateXml@@EEAA@XZ`
- size: `465`
- prototype: `void __fastcall(CDlpStateXml *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x18022a1f0`

## callees

- `0x180077664`
- `0x1802292e8`
- `0x180285bf8`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180229372`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180229387`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180229372`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180229387`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18022949a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18022949a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1802293d9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180229412`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18022944b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1802293d9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180229412`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18022944b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1802293ee`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180229427`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180229460`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1802293ee`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180229427`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180229460`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18022933b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180229359`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802293a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802293c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18022933b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180229359`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802293a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802293c0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CDlpStateXml::~CDlpStateXml(CDlpStateXml *this)
{
  char *v2; // rcx
  char *v3; // rcx
  const WCHAR *v4; // rcx
  const WCHAR *v5; // rcx
  char *v6; // rcx
  char *v7; // rcx
  __int64 v8; // rbx
  HANDLE ProcessHeap; // rax
  __int64 v10; // rbx
  HANDLE v11; // rax
  __int64 v12; // rbx
  HANDLE v13; // rax

  *(_QWORD *)this = &CDlpStateXml::`vftable'{for `IUnknown'};
  *((_QWORD *)this + 1) = &CDlpStateXml::`vftable'{for `IDlpProperties'};
  UnattendCtxCleanup((char *)this + 136);
  if ( *((_DWORD *)this + 37) )
  {
    v2 = (char *)*((_QWORD *)this + 13);
    if ( (unsigned __int64)(v2 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      CloseHandle(v2);
      *((_QWORD *)this + 13) = -1;
    }
    v3 = (char *)*((_QWORD *)this + 14);
    if ( (unsigned __int64)(v3 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      CloseHandle(v3);
      *((_QWORD *)this + 14) = -1;
    }
    v4 = (const WCHAR *)*((_QWORD *)this + 10);
    if ( v4 )
      DeleteFileW(v4);
    v5 = (const WCHAR *)*((_QWORD *)this + 11);
    if ( v5 )
      DeleteFileW(v5);
  }
  v6 = (char *)*((_QWORD *)this + 14);
  if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    CloseHandle(v6);
    *((_QWORD *)this + 14) = -1;
  }
  v7 = (char *)*((_QWORD *)this + 13);
  if ( (unsigned __int64)(v7 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    CloseHandle(v7);
    *((_QWORD *)this + 13) = -1;
  }
  v8 = *((_QWORD *)this + 12);
  if ( v8 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, (LPVOID)(v8 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    *((_QWORD *)this + 12) = 0;
  }
  v10 = *((_QWORD *)this + 11);
  if ( v10 )
  {
    v11 = GetProcessHeap();
    HeapFree(v11, 0, (LPVOID)(v10 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    *((_QWORD *)this + 11) = 0;
  }
  v12 = *((_QWORD *)this + 10);
  if ( v12 )
  {
    v13 = GetProcessHeap();
    HeapFree(v13, 0, (LPVOID)(v12 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    *((_QWORD *)this + 10) = 0;
  }
  *(_QWORD *)this = &CUnknownImpl<IDlpObjectData>::`vftable'{for `IUnknown'};
  *((_QWORD *)this + 1) = &CUnknownImpl<IDlpDownloadListXml>::`vftable'{for `IDlpProperties'};
  if ( *((_DWORD *)this + 18) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
    *((_DWORD *)this + 18) = 0;
  }
}

```

## disassembly

```asm
0x1802292e8  push    rdi
0x1802292ea  sub     rsp, 30h
0x1802292ee  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1802292f7  mov     [rsp+38h+arg_0], rbx
0x1802292fc  mov     rdi, rcx
0x1802292ff  lea     rax, ??_7CDlpStateXml@@6BIUnknown@@@; const CDlpStateXml::`vftable'{for `IUnknown'}
0x180229306  mov     [rcx], rax
0x180229309  lea     rax, ??_7CDlpStateXml@@6BIDlpProperties@@@; const CDlpStateXml::`vftable'{for `IDlpProperties'}
0x180229310  mov     [rcx+8], rax
0x180229314  add     rcx, 88h
0x18022931b  call    UnattendCtxCleanup
0x180229320  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180229324  cmp     dword ptr [rdi+94h], 0
0x18022932b  jz      short loc_180229394
0x18022932d  mov     rcx, [rdi+68h]; hObject
0x180229331  lea     rax, [rcx-1]
0x180229335  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180229339  ja      short loc_18022934B
0x18022933b  call    cs:__imp_CloseHandle
0x180229342  nop     dword ptr [rax+rax+00h]
0x180229347  mov     [rdi+68h], rbx
0x18022934b  mov     rcx, [rdi+70h]; hObject
0x18022934f  lea     rax, [rcx-1]
0x180229353  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180229357  ja      short loc_180229369
0x180229359  call    cs:__imp_CloseHandle
0x180229360  nop     dword ptr [rax+rax+00h]
0x180229365  mov     [rdi+70h], rbx
0x180229369  mov     rcx, [rdi+50h]; lpFileName
0x18022936d  test    rcx, rcx
0x180229370  jz      short loc_18022937E
0x180229372  call    cs:__imp_DeleteFileW
0x180229379  nop     dword ptr [rax+rax+00h]
0x18022937e  mov     rcx, [rdi+58h]; lpFileName
0x180229382  test    rcx, rcx
0x180229385  jz      short loc_180229394
0x180229387  call    cs:__imp_DeleteFileW
0x18022938e  nop     dword ptr [rax+rax+00h]
0x180229393  nop
0x180229394  mov     rcx, [rdi+70h]; hObject
0x180229398  lea     rax, [rcx-1]
0x18022939c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1802293a0  ja      short loc_1802293B2
0x1802293a2  call    cs:__imp_CloseHandle
0x1802293a9  nop     dword ptr [rax+rax+00h]
0x1802293ae  mov     [rdi+70h], rbx
0x1802293b2  mov     rcx, [rdi+68h]; hObject
0x1802293b6  lea     rax, [rcx-1]
0x1802293ba  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1802293be  ja      short loc_1802293D0
0x1802293c0  call    cs:__imp_CloseHandle
0x1802293c7  nop     dword ptr [rax+rax+00h]
0x1802293cc  mov     [rdi+68h], rbx
0x1802293d0  mov     rbx, [rdi+60h]
0x1802293d4  test    rbx, rbx
0x1802293d7  jz      short loc_180229409
0x1802293d9  call    cs:__imp_GetProcessHeap
0x1802293e0  nop     dword ptr [rax+rax+00h]
0x1802293e5  mov     rcx, rax; hHeap
0x1802293e8  lea     r8, [rbx-4]; lpMem
0x1802293ec  xor     edx, edx; dwFlags
0x1802293ee  call    cs:__imp_HeapFree
0x1802293f5  nop     dword ptr [rax+rax+00h]
0x1802293fa  xor     ecx, ecx
0x1802293fc  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180229401  mov     qword ptr [rdi+60h], 0
0x180229409  mov     rbx, [rdi+58h]
0x18022940d  test    rbx, rbx
0x180229410  jz      short loc_180229442
0x180229412  call    cs:__imp_GetProcessHeap
0x180229419  nop     dword ptr [rax+rax+00h]
0x18022941e  mov     rcx, rax; hHeap
0x180229421  lea     r8, [rbx-4]; lpMem
0x180229425  xor     edx, edx; dwFlags
0x180229427  call    cs:__imp_HeapFree
0x18022942e  nop     dword ptr [rax+rax+00h]
0x180229433  xor     ecx, ecx
0x180229435  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18022943a  mov     qword ptr [rdi+58h], 0
0x180229442  mov     rbx, [rdi+50h]
0x180229446  test    rbx, rbx
0x180229449  jz      short loc_18022947B
0x18022944b  call    cs:__imp_GetProcessHeap
0x180229452  nop     dword ptr [rax+rax+00h]
0x180229457  mov     rcx, rax; hHeap
0x18022945a  lea     r8, [rbx-4]; lpMem
0x18022945e  xor     edx, edx; dwFlags
0x180229460  call    cs:__imp_HeapFree
0x180229467  nop     dword ptr [rax+rax+00h]
0x18022946c  xor     ecx, ecx
0x18022946e  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180229473  mov     qword ptr [rdi+50h], 0
0x18022947b  lea     rax, ??_7?$CUnknownImpl@VIDlpObjectData@@@@6BIUnknown@@@; const CUnknownImpl<IDlpObjectData>::`vftable'{for `IUnknown'}
0x180229482  mov     [rdi], rax
0x180229485  lea     rax, ??_7?$CUnknownImpl@VIDlpDownloadListXml@@@@6BIDlpProperties@@@; const CUnknownImpl<IDlpDownloadListXml>::`vftable'{for `IDlpProperties'}
0x18022948c  mov     [rdi+8], rax
0x180229490  cmp     dword ptr [rdi+48h], 0
0x180229494  jz      short loc_1802294AD
0x180229496  lea     rcx, [rdi+20h]; lpCriticalSection
0x18022949a  call    cs:__imp_DeleteCriticalSection
0x1802294a1  nop     dword ptr [rax+rax+00h]
0x1802294a6  mov     dword ptr [rdi+48h], 0
0x1802294ad  mov     rbx, [rsp+38h+arg_0]
0x1802294b2  add     rsp, 30h
0x1802294b6  pop     rdi
0x1802294b7  retn
```
