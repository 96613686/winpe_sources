# CSemExclusive::~CSemExclusive(void)

- ea: `0x1800052b8`
- end: `0x1800052d6`
- name: `??1CSemExclusive@@QEAA@XZ`
- size: `30`
- prototype: `void __fastcall(CSemExclusive *__hidden this)`
- caller_count: `9`
- callee_count: `0`
- tags: ``

## callers

- `0x1800131f7`
- `0x180013345`
- `0x18001335b`
- `0x180013374`
- `0x1800133a6`
- `0x1800133bc`
- `0x1800133d5`
- `0x180014029`
- `0x18001420c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800052ca`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800052ca`

## pseudocode

```c
void __fastcall CSemExclusive::~CSemExclusive(CSemExclusive *this)
{
  *(_QWORD *)this = &CSemExclusive::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
}

```

## disassembly

```asm
0x1800052b8  sub     rsp, 28h
0x1800052bc  lea     rax, ??_7CSemExclusive@@6B@; const CSemExclusive::`vftable'
0x1800052c3  mov     [rcx], rax
0x1800052c6  add     rcx, 8; lpCriticalSection
0x1800052ca  call    cs:__imp_DeleteCriticalSection
0x1800052d0  nop
0x1800052d1  add     rsp, 28h
0x1800052d5  retn
```
