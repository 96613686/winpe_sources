# CSyncReadWrite::~CSyncReadWrite(void)

- ea: `0x14001c054`
- end: `0x14001c089`
- name: `??1CSyncReadWrite@@QEAA@XZ`
- size: `53`
- prototype: `void __fastcall(CSyncReadWrite *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14001c0b8`

## callees

- `0x14001ba0c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14001c073`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14001c073`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14001c082`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall CSyncReadWrite::~CSyncReadWrite(CSyncReadWrite *this)
{
  TPointer<CEventSem>::~TPointer<CEventSem>((char *)this + 104);
  TPointer<CEventSem>::~TPointer<CEventSem>((char *)this + 96);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
}

```

## disassembly

```asm
0x14001c054  push    rbx
0x14001c056  sub     rsp, 20h
0x14001c05a  mov     rbx, rcx
0x14001c05d  add     rcx, 68h ; 'h'
0x14001c061  call    ??1?$TPointer@VCEventSem@@@@QEAA@XZ; TPointer<CEventSem>::~TPointer<CEventSem>(void)
0x14001c066  lea     rcx, [rbx+60h]
0x14001c06a  call    ??1?$TPointer@VCEventSem@@@@QEAA@XZ; TPointer<CEventSem>::~TPointer<CEventSem>(void)
0x14001c06f  lea     rcx, [rbx+38h]; lpCriticalSection
0x14001c073  call    cs:__imp_DeleteCriticalSection
0x14001c079  lea     rcx, [rbx+10h]
0x14001c07d  add     rsp, 20h
0x14001c081  pop     rbx
0x14001c082  jmp     cs:__imp_DeleteCriticalSection
```
