# CSyncReadWrite::~CSyncReadWrite(void)

- ea: `0x14000f9ac`
- end: `0x14000f9e1`
- name: `??1CSyncReadWrite@@QEAA@XZ`
- size: `53`
- prototype: `void __fastcall(CSyncReadWrite *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000fa64`

## callees

- `0x14000ead8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000f9cb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000f9cb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000f9da`

## pseudocode

```c
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
0x14000f9ac  push    rbx
0x14000f9ae  sub     rsp, 20h
0x14000f9b2  mov     rbx, rcx
0x14000f9b5  add     rcx, 68h ; 'h'
0x14000f9b9  call    ??1?$TPointer@VCEventSem@@@@QEAA@XZ; TPointer<CEventSem>::~TPointer<CEventSem>(void)
0x14000f9be  lea     rcx, [rbx+60h]
0x14000f9c2  call    ??1?$TPointer@VCEventSem@@@@QEAA@XZ; TPointer<CEventSem>::~TPointer<CEventSem>(void)
0x14000f9c7  lea     rcx, [rbx+38h]; lpCriticalSection
0x14000f9cb  call    cs:__imp_DeleteCriticalSection
0x14000f9d1  lea     rcx, [rbx+10h]
0x14000f9d5  add     rsp, 20h
0x14000f9d9  pop     rbx
0x14000f9da  jmp     cs:__imp_DeleteCriticalSection
```
