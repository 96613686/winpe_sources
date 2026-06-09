# CDlpStateXml::~CDlpStateXml(void)

- ea: `0x14002a604`
- end: `0x14002a7d5`
- name: `??1CDlpStateXml@@EEAA@XZ`
- size: `465`
- prototype: `void __fastcall(CDlpStateXml *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x14002b450`

## callees

- `0x1400135b8`
- `0x14002a604`
- `0x14005c1f8`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x14002a68e`
- `KERNEL32!DeleteFileW` at `0x14002a6a3`
- `KERNEL32!DeleteFileW` at `0x14002a68e`
- `KERNEL32!DeleteFileW` at `0x14002a6a3`
- `KERNEL32!CloseHandle` at `0x14002a657`
- `KERNEL32!CloseHandle` at `0x14002a675`
- `KERNEL32!CloseHandle` at `0x14002a6be`
- `KERNEL32!CloseHandle` at `0x14002a6dc`
- `KERNEL32!CloseHandle` at `0x14002a657`
- `KERNEL32!CloseHandle` at `0x14002a675`
- `KERNEL32!CloseHandle` at `0x14002a6be`
- `KERNEL32!CloseHandle` at `0x14002a6dc`
- `KERNEL32!DeleteCriticalSection` at `0x14002a7b6`
- `KERNEL32!DeleteCriticalSection` at `0x14002a7b6`
- `KERNEL32!HeapFree` at `0x14002a70a`
- `KERNEL32!HeapFree` at `0x14002a743`
- `KERNEL32!HeapFree` at `0x14002a77c`
- `KERNEL32!HeapFree` at `0x14002a70a`
- `KERNEL32!HeapFree` at `0x14002a743`
- `KERNEL32!HeapFree` at `0x14002a77c`
- `KERNEL32!GetProcessHeap` at `0x14002a6f5`
- `KERNEL32!GetProcessHeap` at `0x14002a72e`
- `KERNEL32!GetProcessHeap` at `0x14002a767`
- `KERNEL32!GetProcessHeap` at `0x14002a6f5`
- `KERNEL32!GetProcessHeap` at `0x14002a72e`
- `KERNEL32!GetProcessHeap` at `0x14002a767`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CDlpStateXml::~CDlpStateXml(CDlpStateXml *this)
{
  void *v2; // rcx
  void *v3; // rcx
  const WCHAR *v4; // rcx
  const WCHAR *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
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
    v2 = (void *)*((_QWORD *)this + 13);
    if ( v2 && v2 != (void *)-1LL )
    {
      CloseHandle(v2);
      *((_QWORD *)this + 13) = -1;
    }
    v3 = (void *)*((_QWORD *)this + 14);
    if ( v3 && v3 != (void *)-1LL )
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
  v6 = (void *)*((_QWORD *)this + 14);
  if ( v6 && v6 != (void *)-1LL )
  {
    CloseHandle(v6);
    *((_QWORD *)this + 14) = -1;
  }
  v7 = (void *)*((_QWORD *)this + 13);
  if ( v7 && v7 != (void *)-1LL )
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
  *((_QWORD *)this + 1) = &CUnknownImpl<IDlpManagerInternal>::`vftable'{for `IDlpProperties'};
  if ( *((_DWORD *)this + 18) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
    *((_DWORD *)this + 18) = 0;
  }
}

```

## disassembly

```asm
0x14002a604  push    rdi
0x14002a606  sub     rsp, 30h
0x14002a60a  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x14002a613  mov     [rsp+38h+arg_0], rbx
0x14002a618  mov     rdi, rcx
0x14002a61b  lea     rax, ??_7CDlpStateXml@@6BIUnknown@@@; const CDlpStateXml::`vftable'{for `IUnknown'}
0x14002a622  mov     [rcx], rax
0x14002a625  lea     rax, ??_7CDlpStateXml@@6BIDlpProperties@@@; const CDlpStateXml::`vftable'{for `IDlpProperties'}
0x14002a62c  mov     [rcx+8], rax
0x14002a630  add     rcx, 88h
0x14002a637  call    UnattendCtxCleanup
0x14002a63c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14002a640  cmp     dword ptr [rdi+94h], 0
0x14002a647  jz      short loc_14002A6B0
0x14002a649  mov     rcx, [rdi+68h]; hObject
0x14002a64d  test    rcx, rcx
0x14002a650  jz      short loc_14002A667
0x14002a652  cmp     rcx, rbx
0x14002a655  jz      short loc_14002A667
0x14002a657  call    cs:__imp_CloseHandle
0x14002a65e  nop     dword ptr [rax+rax+00h]
0x14002a663  mov     [rdi+68h], rbx
0x14002a667  mov     rcx, [rdi+70h]; hObject
0x14002a66b  test    rcx, rcx
0x14002a66e  jz      short loc_14002A685
0x14002a670  cmp     rcx, rbx
0x14002a673  jz      short loc_14002A685
0x14002a675  call    cs:__imp_CloseHandle
0x14002a67c  nop     dword ptr [rax+rax+00h]
0x14002a681  mov     [rdi+70h], rbx
0x14002a685  mov     rcx, [rdi+50h]; lpFileName
0x14002a689  test    rcx, rcx
0x14002a68c  jz      short loc_14002A69A
0x14002a68e  call    cs:__imp_DeleteFileW
0x14002a695  nop     dword ptr [rax+rax+00h]
0x14002a69a  mov     rcx, [rdi+58h]; lpFileName
0x14002a69e  test    rcx, rcx
0x14002a6a1  jz      short loc_14002A6B0
0x14002a6a3  call    cs:__imp_DeleteFileW
0x14002a6aa  nop     dword ptr [rax+rax+00h]
0x14002a6af  nop
0x14002a6b0  mov     rcx, [rdi+70h]; hObject
0x14002a6b4  test    rcx, rcx
0x14002a6b7  jz      short loc_14002A6CE
0x14002a6b9  cmp     rcx, rbx
0x14002a6bc  jz      short loc_14002A6CE
0x14002a6be  call    cs:__imp_CloseHandle
0x14002a6c5  nop     dword ptr [rax+rax+00h]
0x14002a6ca  mov     [rdi+70h], rbx
0x14002a6ce  mov     rcx, [rdi+68h]; hObject
0x14002a6d2  test    rcx, rcx
0x14002a6d5  jz      short loc_14002A6EC
0x14002a6d7  cmp     rcx, rbx
0x14002a6da  jz      short loc_14002A6EC
0x14002a6dc  call    cs:__imp_CloseHandle
0x14002a6e3  nop     dword ptr [rax+rax+00h]
0x14002a6e8  mov     [rdi+68h], rbx
0x14002a6ec  mov     rbx, [rdi+60h]
0x14002a6f0  test    rbx, rbx
0x14002a6f3  jz      short loc_14002A725
0x14002a6f5  call    cs:__imp_GetProcessHeap
0x14002a6fc  nop     dword ptr [rax+rax+00h]
0x14002a701  mov     rcx, rax; hHeap
0x14002a704  lea     r8, [rbx-4]; lpMem
0x14002a708  xor     edx, edx; dwFlags
0x14002a70a  call    cs:__imp_HeapFree
0x14002a711  nop     dword ptr [rax+rax+00h]
0x14002a716  xor     ecx, ecx
0x14002a718  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14002a71d  mov     qword ptr [rdi+60h], 0
0x14002a725  mov     rbx, [rdi+58h]
0x14002a729  test    rbx, rbx
0x14002a72c  jz      short loc_14002A75E
0x14002a72e  call    cs:__imp_GetProcessHeap
0x14002a735  nop     dword ptr [rax+rax+00h]
0x14002a73a  mov     rcx, rax; hHeap
0x14002a73d  lea     r8, [rbx-4]; lpMem
0x14002a741  xor     edx, edx; dwFlags
0x14002a743  call    cs:__imp_HeapFree
0x14002a74a  nop     dword ptr [rax+rax+00h]
0x14002a74f  xor     ecx, ecx
0x14002a751  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14002a756  mov     qword ptr [rdi+58h], 0
0x14002a75e  mov     rbx, [rdi+50h]
0x14002a762  test    rbx, rbx
0x14002a765  jz      short loc_14002A797
0x14002a767  call    cs:__imp_GetProcessHeap
0x14002a76e  nop     dword ptr [rax+rax+00h]
0x14002a773  mov     rcx, rax; hHeap
0x14002a776  lea     r8, [rbx-4]; lpMem
0x14002a77a  xor     edx, edx; dwFlags
0x14002a77c  call    cs:__imp_HeapFree
0x14002a783  nop     dword ptr [rax+rax+00h]
0x14002a788  xor     ecx, ecx
0x14002a78a  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14002a78f  mov     qword ptr [rdi+50h], 0
0x14002a797  lea     rax, ??_7?$CUnknownImpl@VIDlpObjectData@@@@6BIUnknown@@@; const CUnknownImpl<IDlpObjectData>::`vftable'{for `IUnknown'}
0x14002a79e  mov     [rdi], rax
0x14002a7a1  lea     rax, ??_7?$CUnknownImpl@VIDlpManagerInternal@@@@6BIDlpProperties@@@; const CUnknownImpl<IDlpManagerInternal>::`vftable'{for `IDlpProperties'}
0x14002a7a8  mov     [rdi+8], rax
0x14002a7ac  cmp     dword ptr [rdi+48h], 0
0x14002a7b0  jz      short loc_14002A7C9
0x14002a7b2  lea     rcx, [rdi+20h]; lpCriticalSection
0x14002a7b6  call    cs:__imp_DeleteCriticalSection
0x14002a7bd  nop     dword ptr [rax+rax+00h]
0x14002a7c2  mov     dword ptr [rdi+48h], 0
0x14002a7c9  mov     rbx, [rsp+38h+arg_0]
0x14002a7ce  add     rsp, 30h
0x14002a7d2  pop     rdi
0x14002a7d3  retn
```
