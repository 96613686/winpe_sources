# TrackerCompletion::~TrackerCompletion(void)

- ea: `0x14000366c`
- end: `0x140003695`
- name: `??1TrackerCompletion@@UEAA@XZ`
- size: `41`
- prototype: `void __fastcall(struct IUnknown **this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140003730`

## callees

- `0x1400055e0`
- `0x1400056bc`

## pseudocode

```c
void __fastcall TrackerCompletion::~TrackerCompletion(struct IUnknown **this)
{
  *this = (struct IUnknown *)&TrackerCompletion::`vftable';
  ReleaseInterface(this[7]);
  Completion::~Completion((Completion *)this);
}

```

## disassembly

```asm
0x14000366c  push    rbx
0x14000366e  sub     rsp, 20h
0x140003672  lea     rax, ??_7TrackerCompletion@@6B@; const TrackerCompletion::`vftable'
0x140003679  mov     rbx, rcx
0x14000367c  mov     [rcx], rax
0x14000367f  mov     rcx, [rcx+38h]; struct IUnknown *
0x140003683  call    ?ReleaseInterface@@YAXPEAUIUnknown@@@Z; ReleaseInterface(IUnknown *)
0x140003688  mov     rcx, rbx; this
0x14000368b  add     rsp, 20h
0x14000368f  pop     rbx
0x140003690  jmp     ??1Completion@@UEAA@XZ; Completion::~Completion(void)
```
