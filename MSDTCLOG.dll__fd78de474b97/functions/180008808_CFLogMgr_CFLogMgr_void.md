# CFLogMgr::~CFLogMgr(void)

- ea: `0x180008808`
- end: `0x180008831`
- name: `??1CFLogMgr@@QEAA@XZ`
- size: `41`
- prototype: `void __fastcall(CFLogMgr *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1800089b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008825`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008825`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CFLogMgr::~CFLogMgr(CFLogMgr *this)
{
  *(_QWORD *)this = &CFLogMgr::`vftable';
  *((_QWORD *)this + 2) = &CSemExclusive::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
}

```

## disassembly

```asm
0x180008808  sub     rsp, 28h
0x18000880c  lea     rax, ??_7CFLogMgr@@6B@; const CFLogMgr::`vftable'
0x180008813  mov     [rcx], rax
0x180008816  lea     rax, ??_7CSemExclusive@@6B@; const CSemExclusive::`vftable'
0x18000881d  mov     [rcx+10h], rax
0x180008821  add     rcx, 18h; lpCriticalSection
0x180008825  call    cs:__imp_DeleteCriticalSection
0x18000882b  nop
0x18000882c  add     rsp, 28h
0x180008830  retn
```
