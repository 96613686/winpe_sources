# __acrt_initialize_thread_local_exit_callback

- ea: `0x18000db54`
- end: `0x18000db5c`
- name: `__acrt_initialize_thread_local_exit_callback`
- size: `8`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18000e5d0`

## pseudocode

```c
void __fastcall _acrt_initialize_thread_local_exit_callback(__int64 a1)
{
  qword_18003E310 = a1;
}

```

## disassembly

```asm
0x18000db54  mov     cs:qword_18003E310, rcx
0x18000db5b  retn
```
