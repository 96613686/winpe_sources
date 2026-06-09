# TrackerCompletion::TrackerCompletion(Tracker *)

- ea: `0x140003518`
- end: `0x140003559`
- name: `??0TrackerCompletion@@QEAA@PEAVTracker@@@Z`
- size: `65`
- prototype: `TrackerCompletion *__fastcall(TrackerCompletion *__hidden this, struct Tracker *)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140003774`
- `0x1400044f0`
- `0x140004850`

## callees

- `0x1400056a0`
- `0x140006590`

## pseudocode

```c
TrackerCompletion *__fastcall TrackerCompletion::TrackerCompletion(TrackerCompletion *this, struct Tracker *a2)
{
  Completion::Completion(this);
  *((_QWORD *)this + 7) = a2;
  *(_QWORD *)this = &TrackerCompletion::`vftable';
  (*(void (__fastcall **)(struct Tracker *))(*(_QWORD *)a2 + 8LL))(a2);
  return this;
}

```

## disassembly

```asm
0x140003518  mov     [rsp+arg_0], rbx
0x14000351d  push    rdi
0x14000351e  sub     rsp, 20h
0x140003522  mov     rbx, rdx
0x140003525  mov     rdi, rcx
0x140003528  call    ??0Completion@@QEAA@XZ; Completion::Completion(void)
0x14000352d  lea     rax, ??_7TrackerCompletion@@6B@; const TrackerCompletion::`vftable'
0x140003534  mov     [rdi+38h], rbx
0x140003538  mov     [rdi], rax
0x14000353b  mov     rcx, rbx
0x14000353e  mov     rax, [rbx]
0x140003541  mov     rax, [rax+8]
0x140003545  call    cs:__guard_dispatch_icall_fptr
0x14000354b  mov     rbx, [rsp+28h+arg_0]
0x140003550  mov     rax, rdi
0x140003553  add     rsp, 20h
0x140003557  pop     rdi
0x140003558  retn
```
