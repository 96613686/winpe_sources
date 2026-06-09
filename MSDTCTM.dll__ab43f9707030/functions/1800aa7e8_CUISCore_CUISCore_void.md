# CUISCore::~CUISCore(void)

- ea: `0x1800aa7e8`
- end: `0x1800aa90a`
- name: `??1CUISCore@@QEAA@XZ`
- size: `290`
- prototype: `void __fastcall(CUISCore *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800aa36c`

## callees

- `0x1800aa7ac`
- `0x1800aa7e8`
- `0x1800aad90`
- `0x1800bd010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TerminateThread` at `0x1800aa80d`
- `api-ms-win-core-processthreads-l1-1-0!TerminateThread` at `0x1800aa80d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800aa8e9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800aa8f8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800aa8e9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800aa8f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800aa849`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800aa85b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800aa849`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800aa85b`

## pseudocode

```c
void __fastcall CUISCore::~CUISCore(CUISCore *this)
{
  void *v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  __int64 v7; // rcx

  *(_QWORD *)this = &CUISCore::`vftable';
  v2 = (void *)*((_QWORD *)this + 18);
  if ( v2 )
    TerminateThread(v2, 0);
  v3 = *((_QWORD *)this + 2);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  v4 = *((_QWORD *)this + 3);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  v5 = (void *)*((_QWORD *)this + 65);
  if ( v5 )
    CloseHandle(v5);
  v6 = (void *)*((_QWORD *)this + 68);
  if ( v6 )
  {
    CloseHandle(v6);
    *((_QWORD *)this + 68) = 0;
  }
  v7 = *((_QWORD *)this + 31);
  if ( v7 )
  {
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v7 + 40LL))(v7, 1);
    *((_QWORD *)this + 31) = 0;
  }
  CImpIDacUISInit::~CImpIDacUISInit((CUISCore *)((char *)this + 456));
  *((_QWORD *)this + 32) = &UTList<IUISDataProvider *>::`vftable';
  UTList<IUISDataProvider *>::RemoveAll();
  *((_QWORD *)this + 27) = &UTStaticList<CImpITransactionTracker *>::`vftable';
  *((_QWORD *)this + 23) = &UTStaticList<CImpITransactionTracker *>::`vftable';
  *((_QWORD *)this + 19) = &UTStaticList<CImpITransactionTracker *>::`vftable';
  *((_QWORD *)this + 11) = &CSemExclusive::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
  *((_QWORD *)this + 4) = &CSemExclusive::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 1);
}

```

## disassembly

```asm
0x1800aa7e8  mov     [rsp+arg_0], rbx
0x1800aa7ed  push    rdi
0x1800aa7ee  sub     rsp, 20h
0x1800aa7f2  mov     rbx, rcx
0x1800aa7f5  lea     rax, ??_7CUISCore@@6B@; const CUISCore::`vftable'
0x1800aa7fc  mov     [rcx], rax
0x1800aa7ff  mov     rcx, [rcx+90h]; hThread
0x1800aa806  test    rcx, rcx
0x1800aa809  jz      short loc_1800AA813
0x1800aa80b  xor     edx, edx; dwExitCode
0x1800aa80d  call    cs:__imp_TerminateThread
0x1800aa813  mov     rcx, [rbx+10h]
0x1800aa817  test    rcx, rcx
0x1800aa81a  jz      short loc_1800AA828
0x1800aa81c  mov     rax, [rcx]
0x1800aa81f  mov     rax, [rax+10h]
0x1800aa823  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aa828  mov     rcx, [rbx+18h]
0x1800aa82c  test    rcx, rcx
0x1800aa82f  jz      short loc_1800AA83D
0x1800aa831  mov     rax, [rcx]
0x1800aa834  mov     rax, [rax+10h]
0x1800aa838  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aa83d  mov     rcx, [rbx+208h]; hObject
0x1800aa844  test    rcx, rcx
0x1800aa847  jz      short loc_1800AA84F
0x1800aa849  call    cs:__imp_CloseHandle
0x1800aa84f  mov     rcx, [rbx+220h]; hObject
0x1800aa856  test    rcx, rcx
0x1800aa859  jz      short loc_1800AA86C
0x1800aa85b  call    cs:__imp_CloseHandle
0x1800aa861  mov     qword ptr [rbx+220h], 0
0x1800aa86c  mov     rcx, [rbx+0F8h]
0x1800aa873  test    rcx, rcx
0x1800aa876  jz      short loc_1800AA894
0x1800aa878  mov     rax, [rcx]
0x1800aa87b  mov     edx, 1
0x1800aa880  mov     rax, [rax+28h]
0x1800aa884  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aa889  mov     qword ptr [rbx+0F8h], 0
0x1800aa894  lea     rcx, [rbx+1C8h]; this
0x1800aa89b  call    ??1CImpIDacUISInit@@QEAA@XZ; CImpIDacUISInit::~CImpIDacUISInit(void)
0x1800aa8a0  lea     rcx, [rbx+100h]
0x1800aa8a7  lea     rax, ??_7?$UTList@PEAUIUISDataProvider@@@@6B@; const UTList<IUISDataProvider *>::`vftable'
0x1800aa8ae  mov     [rcx], rax
0x1800aa8b1  call    ?RemoveAll@?$UTList@PEAUIUISDataProvider@@@@UEAAXXZ; UTList<IUISDataProvider *>::RemoveAll(void)
0x1800aa8b6  nop
0x1800aa8b7  lea     rax, ??_7?$UTStaticList@PEAVCImpITransactionTracker@@@@6B@; const UTStaticList<CImpITransactionTracker *>::`vftable'
0x1800aa8be  mov     [rbx+0D8h], rax
0x1800aa8c5  lea     rax, ??_7?$UTStaticList@PEAVCImpITransactionTracker@@@@6B@; const UTStaticList<CImpITransactionTracker *>::`vftable'
0x1800aa8cc  mov     [rbx+0B8h], rax
0x1800aa8d3  mov     [rbx+98h], rax
0x1800aa8da  lea     rdi, ??_7CSemExclusive@@6B@; const CSemExclusive::`vftable'
0x1800aa8e1  mov     [rbx+58h], rdi
0x1800aa8e5  lea     rcx, [rbx+60h]; lpCriticalSection
0x1800aa8e9  call    cs:__imp_DeleteCriticalSection
0x1800aa8ef  nop
0x1800aa8f0  mov     [rbx+20h], rdi
0x1800aa8f4  lea     rcx, [rbx+28h]; lpCriticalSection
0x1800aa8f8  call    cs:__imp_DeleteCriticalSection
0x1800aa8fe  nop
0x1800aa8ff  mov     rbx, [rsp+28h+arg_0]
0x1800aa904  add     rsp, 20h
0x1800aa908  pop     rdi
0x1800aa909  retn
```
