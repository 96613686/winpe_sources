# __scrt_acquire_startup_lock

- ea: `0x180001798`
- end: `0x1800017d1`
- name: `__scrt_acquire_startup_lock`
- size: `57`
- prototype: `char()`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001408`
- `0x180001508`

## callees

- `0x180001798`
- `0x180002190`

## pseudocode

```c
char _scrt_acquire_startup_lock()
{
  PVOID StackBase; // rcx
  signed __int64 v1; // rax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
  {
    StackBase = NtCurrentTeb()->NtTib.StackBase;
    while ( 1 )
    {
      v1 = _InterlockedCompareExchange64(&_scrt_native_startup_lock, (signed __int64)StackBase, 0);
      if ( !v1 )
        break;
      if ( StackBase == (PVOID)v1 )
        return 1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180001798  sub     rsp, 28h
0x18000179c  call    __scrt_is_ucrt_dll_in_use
0x1800017a1  test    eax, eax
0x1800017a3  jz      short loc_1800017C6
0x1800017a5  mov     rax, gs:30h
0x1800017ae  mov     rcx, [rax+8]
0x1800017b2  jmp     short loc_1800017B9
0x1800017b4  cmp     rcx, rax
0x1800017b7  jz      short loc_1800017CD
0x1800017b9  xor     eax, eax
0x1800017bb  lock cmpxchg cs:__scrt_native_startup_lock, rcx
0x1800017c4  jnz     short loc_1800017B4
0x1800017c6  xor     al, al
0x1800017c8  add     rsp, 28h
0x1800017cc  retn
0x1800017cd  mov     al, 1
0x1800017cf  jmp     short loc_1800017C8
```
