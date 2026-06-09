# CallingStateTracker::~CallingStateTracker(void)

- ea: `0x180006d5c`
- end: `0x180006d83`
- name: `??1CallingStateTracker@@QEAA@XZ`
- size: `39`
- prototype: `void __fastcall(CallingStateTracker *__hidden this)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ed22`
- `0x18000ed7c`
- `0x18000eda0`
- `0x18000edfc`
- `0x18000ee20`
- `0x18000eeb0`

## callees

- `0x180006d5c`
- `0x180010010`

## pseudocode

```c
void __fastcall CallingStateTracker::~CallingStateTracker(CallingStateTracker *this)
{
  if ( qword_1800184A8 )
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)qword_1800184A8 + 24LL))(
      qword_1800184A8,
      *(unsigned int *)this);
}

```

## disassembly

```asm
0x180006d5c  sub     rsp, 28h
0x180006d60  mov     rdx, rcx
0x180006d63  mov     rcx, cs:qword_1800184A8
0x180006d6a  test    rcx, rcx
0x180006d6d  jz      short loc_180006D7E
0x180006d6f  mov     rax, [rcx]
0x180006d72  mov     edx, [rdx]
0x180006d74  mov     rax, [rax+18h]
0x180006d78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d7d  nop
0x180006d7e  add     rsp, 28h
0x180006d82  retn
```
