# CallStackTracing::~CallStackTracing(void)

- ea: `0x180030b14`
- end: `0x180030b6b`
- name: `??1CallStackTracing@@QEAA@XZ`
- size: `87`
- prototype: `void __fastcall(CallStackTracing *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18004c1a0`

## callees

- `0x1800032d0`
- `0x180030ab4`
- `0x180030d00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180030b55`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180030b55`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180030b64`

## pseudocode

```c
void __fastcall CallStackTracing::~CallStackTracing(CallStackTracing *this)
{
  unsigned int v2; // edx

  *(_QWORD *)this = &CallStackTracing::`vftable';
  CallStackTracing::Cleanup(this);
  `vector destructor iterator'((char *)this + 208, 0x10u, 0x7Cu, guard_check_icall_nop);
  CFreeList<CallStackContextNode,16>::~CFreeList<CallStackContextNode,16>((__int64)this + 104, v2);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
}

```

## disassembly

```asm
0x180030b14  push    rbx
0x180030b16  sub     rsp, 20h
0x180030b1a  lea     rax, ??_7CallStackTracing@@6B@; const CallStackTracing::`vftable'
0x180030b21  mov     rbx, rcx
0x180030b24  mov     [rcx], rax
0x180030b27  call    ?Cleanup@CallStackTracing@@IEAAXXZ; CallStackTracing::Cleanup(void)
0x180030b2c  mov     edx, 10h; unsigned __int64
0x180030b31  lea     rcx, [rbx+0D0h]; void *
0x180030b38  lea     r9, _guard_check_icall_nop; void (*)(void *)
0x180030b3f  lea     r8d, [rdx+6Ch]; unsigned __int64
0x180030b43  call    ??_I@YAXPEAX_K1P6AX0@Z@Z; `vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180030b48  lea     rcx, [rbx+68h]
0x180030b4c  call    ??1?$CFreeList@VCallStackContextNode@@$0BA@@@UEAA@XZ; CFreeList<CallStackContextNode,16>::~CFreeList<CallStackContextNode,16>(void)
0x180030b51  lea     rcx, [rbx+38h]; lpCriticalSection
0x180030b55  call    cs:__imp_DeleteCriticalSection
0x180030b5b  lea     rcx, [rbx+10h]
0x180030b5f  add     rsp, 20h
0x180030b63  pop     rbx
0x180030b64  jmp     cs:__imp_DeleteCriticalSection
```
