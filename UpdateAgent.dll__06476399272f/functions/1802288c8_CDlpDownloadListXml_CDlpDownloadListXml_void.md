# CDlpDownloadListXml::~CDlpDownloadListXml(void)

- ea: `0x1802288c8`
- end: `0x180228a99`
- name: `??1CDlpDownloadListXml@@EEAA@XZ`
- size: `465`
- prototype: `void __fastcall(CDlpDownloadListXml *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x18022a0f0`

## callees

- `0x180077664`
- `0x1802288c8`
- `0x180285bf8`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180228952`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180228967`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180228952`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180228967`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180228a7a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180228a7a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1802289b9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1802289f2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180228a2b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1802289b9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1802289f2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180228a2b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1802289ce`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180228a07`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180228a40`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1802289ce`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180228a07`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180228a40`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18022891b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180228939`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180228982`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802289a0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18022891b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180228939`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180228982`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802289a0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CDlpDownloadListXml::~CDlpDownloadListXml(CDlpDownloadListXml *this)
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

  *(_QWORD *)this = &CDlpDownloadListXml::`vftable'{for `IUnknown'};
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
  *(_QWORD *)this = &CUnknownImpl<IDlpDownloadListXml>::`vftable'{for `IUnknown'};
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
0x1802288c8  push    rdi
0x1802288ca  sub     rsp, 30h
0x1802288ce  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1802288d7  mov     [rsp+38h+arg_0], rbx
0x1802288dc  mov     rdi, rcx
0x1802288df  lea     rax, ??_7CDlpDownloadListXml@@6BIUnknown@@@; const CDlpDownloadListXml::`vftable'{for `IUnknown'}
0x1802288e6  mov     [rcx], rax
0x1802288e9  lea     rax, ??_7CDlpStateXml@@6BIDlpProperties@@@; const CDlpStateXml::`vftable'{for `IDlpProperties'}
0x1802288f0  mov     [rcx+8], rax
0x1802288f4  add     rcx, 88h
0x1802288fb  call    UnattendCtxCleanup
0x180228900  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180228904  cmp     dword ptr [rdi+94h], 0
0x18022890b  jz      short loc_180228974
0x18022890d  mov     rcx, [rdi+68h]; hObject
0x180228911  lea     rax, [rcx-1]
0x180228915  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180228919  ja      short loc_18022892B
0x18022891b  call    cs:__imp_CloseHandle
0x180228922  nop     dword ptr [rax+rax+00h]
0x180228927  mov     [rdi+68h], rbx
0x18022892b  mov     rcx, [rdi+70h]; hObject
0x18022892f  lea     rax, [rcx-1]
0x180228933  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180228937  ja      short loc_180228949
0x180228939  call    cs:__imp_CloseHandle
0x180228940  nop     dword ptr [rax+rax+00h]
0x180228945  mov     [rdi+70h], rbx
0x180228949  mov     rcx, [rdi+50h]; lpFileName
0x18022894d  test    rcx, rcx
0x180228950  jz      short loc_18022895E
0x180228952  call    cs:__imp_DeleteFileW
0x180228959  nop     dword ptr [rax+rax+00h]
0x18022895e  mov     rcx, [rdi+58h]; lpFileName
0x180228962  test    rcx, rcx
0x180228965  jz      short loc_180228974
0x180228967  call    cs:__imp_DeleteFileW
0x18022896e  nop     dword ptr [rax+rax+00h]
0x180228973  nop
0x180228974  mov     rcx, [rdi+70h]; hObject
0x180228978  lea     rax, [rcx-1]
0x18022897c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180228980  ja      short loc_180228992
0x180228982  call    cs:__imp_CloseHandle
0x180228989  nop     dword ptr [rax+rax+00h]
0x18022898e  mov     [rdi+70h], rbx
0x180228992  mov     rcx, [rdi+68h]; hObject
0x180228996  lea     rax, [rcx-1]
0x18022899a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18022899e  ja      short loc_1802289B0
0x1802289a0  call    cs:__imp_CloseHandle
0x1802289a7  nop     dword ptr [rax+rax+00h]
0x1802289ac  mov     [rdi+68h], rbx
0x1802289b0  mov     rbx, [rdi+60h]
0x1802289b4  test    rbx, rbx
0x1802289b7  jz      short loc_1802289E9
0x1802289b9  call    cs:__imp_GetProcessHeap
0x1802289c0  nop     dword ptr [rax+rax+00h]
0x1802289c5  mov     rcx, rax; hHeap
0x1802289c8  lea     r8, [rbx-4]; lpMem
0x1802289cc  xor     edx, edx; dwFlags
0x1802289ce  call    cs:__imp_HeapFree
0x1802289d5  nop     dword ptr [rax+rax+00h]
0x1802289da  xor     ecx, ecx
0x1802289dc  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1802289e1  mov     qword ptr [rdi+60h], 0
0x1802289e9  mov     rbx, [rdi+58h]
0x1802289ed  test    rbx, rbx
0x1802289f0  jz      short loc_180228A22
0x1802289f2  call    cs:__imp_GetProcessHeap
0x1802289f9  nop     dword ptr [rax+rax+00h]
0x1802289fe  mov     rcx, rax; hHeap
0x180228a01  lea     r8, [rbx-4]; lpMem
0x180228a05  xor     edx, edx; dwFlags
0x180228a07  call    cs:__imp_HeapFree
0x180228a0e  nop     dword ptr [rax+rax+00h]
0x180228a13  xor     ecx, ecx
0x180228a15  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180228a1a  mov     qword ptr [rdi+58h], 0
0x180228a22  mov     rbx, [rdi+50h]
0x180228a26  test    rbx, rbx
0x180228a29  jz      short loc_180228A5B
0x180228a2b  call    cs:__imp_GetProcessHeap
0x180228a32  nop     dword ptr [rax+rax+00h]
0x180228a37  mov     rcx, rax; hHeap
0x180228a3a  lea     r8, [rbx-4]; lpMem
0x180228a3e  xor     edx, edx; dwFlags
0x180228a40  call    cs:__imp_HeapFree
0x180228a47  nop     dword ptr [rax+rax+00h]
0x180228a4c  xor     ecx, ecx
0x180228a4e  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180228a53  mov     qword ptr [rdi+50h], 0
0x180228a5b  lea     rax, ??_7?$CUnknownImpl@VIDlpDownloadListXml@@@@6BIUnknown@@@; const CUnknownImpl<IDlpDownloadListXml>::`vftable'{for `IUnknown'}
0x180228a62  mov     [rdi], rax
0x180228a65  lea     rax, ??_7?$CUnknownImpl@VIDlpDownloadListXml@@@@6BIDlpProperties@@@; const CUnknownImpl<IDlpDownloadListXml>::`vftable'{for `IDlpProperties'}
0x180228a6c  mov     [rdi+8], rax
0x180228a70  cmp     dword ptr [rdi+48h], 0
0x180228a74  jz      short loc_180228A8D
0x180228a76  lea     rcx, [rdi+20h]; lpCriticalSection
0x180228a7a  call    cs:__imp_DeleteCriticalSection
0x180228a81  nop     dword ptr [rax+rax+00h]
0x180228a86  mov     dword ptr [rdi+48h], 0
0x180228a8d  mov     rbx, [rsp+38h+arg_0]
0x180228a92  add     rsp, 30h
0x180228a96  pop     rdi
0x180228a97  retn
```
