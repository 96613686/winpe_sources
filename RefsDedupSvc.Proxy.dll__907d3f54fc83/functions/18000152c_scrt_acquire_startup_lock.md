# __scrt_acquire_startup_lock

- ea: `0x18000152c`
- end: `0x180001565`
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

- `0x18000152c`
- `0x180001bd8`

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
0x18000152c  sub     rsp, 28h
0x180001530  call    __scrt_is_ucrt_dll_in_use
0x180001535  test    eax, eax
0x180001537  jz      short loc_18000155A
0x180001539  mov     rax, gs:30h
0x180001542  mov     rcx, [rax+8]
0x180001546  jmp     short loc_18000154D
0x180001548  cmp     rcx, rax
0x18000154b  jz      short loc_180001561
0x18000154d  xor     eax, eax
0x18000154f  lock cmpxchg cs:__scrt_native_startup_lock, rcx
0x180001558  jnz     short loc_180001548
0x18000155a  xor     al, al
0x18000155c  add     rsp, 28h
0x180001560  retn
0x180001561  mov     al, 1
0x180001563  jmp     short loc_18000155C
```
