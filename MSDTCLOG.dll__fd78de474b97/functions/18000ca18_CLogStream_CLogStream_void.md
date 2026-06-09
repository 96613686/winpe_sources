# CLogStream::~CLogStream(void)

- ea: `0x18000ca18`
- end: `0x18000ca87`
- name: `??1CLogStream@@QEAA@XZ`
- size: `111`
- prototype: `void __fastcall(CLogStream *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ccb0`

## callees

- `0x18000cdd8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ca51`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ca66`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ca75`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ca51`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ca66`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ca75`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CLogStream::~CLogStream(CLogStream *this)
{
  *(_QWORD *)this = &CLogStream::`vftable';
  CReadMap::~CReadMap((CLogStream *)((char *)this + 352));
  *((_QWORD *)this + 29) = &CSemExclusive::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 6);
  *((_QWORD *)this + 22) = &CSemExclusive::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 184));
  *((_QWORD *)this + 2) = &CSemExclusive::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
}

```

## disassembly

```asm
0x18000ca18  mov     [rsp+arg_0], rbx
0x18000ca1d  push    rdi
0x18000ca1e  sub     rsp, 20h
0x18000ca22  mov     rbx, rcx
0x18000ca25  lea     rax, ??_7CLogStream@@6B@; const CLogStream::`vftable'
0x18000ca2c  mov     [rcx], rax
0x18000ca2f  add     rcx, 160h; this
0x18000ca36  call    ??1CReadMap@@QEAA@XZ; CReadMap::~CReadMap(void)
0x18000ca3b  nop
0x18000ca3c  lea     rdi, ??_7CSemExclusive@@6B@; const CSemExclusive::`vftable'
0x18000ca43  mov     [rbx+0E8h], rdi
0x18000ca4a  lea     rcx, [rbx+0F0h]; lpCriticalSection
0x18000ca51  call    cs:__imp_DeleteCriticalSection
0x18000ca57  nop
0x18000ca58  mov     [rbx+0B0h], rdi
0x18000ca5f  lea     rcx, [rbx+0B8h]; lpCriticalSection
0x18000ca66  call    cs:__imp_DeleteCriticalSection
0x18000ca6c  nop
0x18000ca6d  mov     [rbx+10h], rdi
0x18000ca71  lea     rcx, [rbx+18h]; lpCriticalSection
0x18000ca75  call    cs:__imp_DeleteCriticalSection
0x18000ca7b  nop
0x18000ca7c  mov     rbx, [rsp+28h+arg_0]
0x18000ca81  add     rsp, 20h
0x18000ca85  pop     rdi
0x18000ca86  retn
```
