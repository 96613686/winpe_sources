# CallStackTracing::~CallStackTracing(void)

- ea: `0x18012f320`
- end: `0x18012f377`
- name: `??1CallStackTracing@@QEAA@XZ`
- size: `87`
- prototype: `void __fastcall(CallStackTracing *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180141210`

## callees

- `0x18002ab88`
- `0x18012f2c0`
- `0x18012f500`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18012f361`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18012f361`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18012f370`

## pseudocode

```c
void __fastcall CallStackTracing::~CallStackTracing(CallStackTracing *this)
{
  *(_QWORD *)this = &CallStackTracing::`vftable';
  CallStackTracing::Cleanup(this);
  `vector destructor iterator'((char *)this + 208, 0x10u, 0x7Cu, (void (*)(void *))LowLightFusionOperation::OnCancel);
  CFreeList<CallStackContextNode,16>::~CFreeList<CallStackContextNode,16>((char *)this + 104);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
}

```

## disassembly

```asm
0x18012f320  push    rbx
0x18012f322  sub     rsp, 20h
0x18012f326  lea     rax, ??_7CallStackTracing@@6B@; const CallStackTracing::`vftable'
0x18012f32d  mov     rbx, rcx
0x18012f330  mov     [rcx], rax
0x18012f333  call    ?Cleanup@CallStackTracing@@IEAAXXZ; CallStackTracing::Cleanup(void)
0x18012f338  mov     edx, 10h; unsigned __int64
0x18012f33d  lea     rcx, [rbx+0D0h]; void *
0x18012f344  lea     r9, ?OnCancel@LowLightFusionOperation@@UEAAXXZ; void (*)(void *)
0x18012f34b  lea     r8d, [rdx+6Ch]; unsigned __int64
0x18012f34f  call    ??_I@YAXPEAX_K1P6AX0@Z@Z; `vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18012f354  lea     rcx, [rbx+68h]
0x18012f358  call    ??1?$CFreeList@VCallStackContextNode@@$0BA@@@UEAA@XZ; CFreeList<CallStackContextNode,16>::~CFreeList<CallStackContextNode,16>(void)
0x18012f35d  lea     rcx, [rbx+38h]; lpCriticalSection
0x18012f361  call    cs:__imp_DeleteCriticalSection
0x18012f367  lea     rcx, [rbx+10h]
0x18012f36b  add     rsp, 20h
0x18012f36f  pop     rbx
0x18012f370  jmp     cs:__imp_DeleteCriticalSection
```
