# __scrt_acquire_startup_lock

- ea: `0x180001558`
- end: `0x180001591`
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

- `0x180001558`
- `0x180001c08`

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
0x180001558  sub     rsp, 28h
0x18000155c  call    __scrt_is_ucrt_dll_in_use
0x180001561  test    eax, eax
0x180001563  jz      short loc_180001586
0x180001565  mov     rax, gs:30h
0x18000156e  mov     rcx, [rax+8]
0x180001572  jmp     short loc_180001579
0x180001574  cmp     rcx, rax
0x180001577  jz      short loc_18000158D
0x180001579  xor     eax, eax
0x18000157b  lock cmpxchg cs:__scrt_native_startup_lock, rcx
0x180001584  jnz     short loc_180001574
0x180001586  xor     al, al
0x180001588  add     rsp, 28h
0x18000158c  retn
0x18000158d  mov     al, 1
0x18000158f  jmp     short loc_180001588
```
