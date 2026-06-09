# __scrt_acquire_startup_lock

- ea: `0x180001528`
- end: `0x180001561`
- name: `__scrt_acquire_startup_lock`
- size: `57`
- prototype: `char()`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800010e8`
- `0x1800011e8`

## callees

- `0x180001528`
- `0x180001bb0`

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
0x180001528  sub     rsp, 28h
0x18000152c  call    __scrt_is_ucrt_dll_in_use
0x180001531  test    eax, eax
0x180001533  jz      short loc_180001556
0x180001535  mov     rax, gs:30h
0x18000153e  mov     rcx, [rax+8]
0x180001542  jmp     short loc_180001549
0x180001544  cmp     rcx, rax
0x180001547  jz      short loc_18000155D
0x180001549  xor     eax, eax
0x18000154b  lock cmpxchg cs:__scrt_native_startup_lock, rcx
0x180001554  jnz     short loc_180001544
0x180001556  xor     al, al
0x180001558  add     rsp, 28h
0x18000155c  retn
0x18000155d  mov     al, 1
0x18000155f  jmp     short loc_180001558
```
