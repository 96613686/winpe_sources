# __scrt_acquire_startup_lock

- ea: `0x18000157c`
- end: `0x1800015b5`
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

- `0x18000157c`
- `0x180001e20`

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
0x18000157c  sub     rsp, 28h
0x180001580  call    __scrt_is_ucrt_dll_in_use
0x180001585  test    eax, eax
0x180001587  jz      short loc_1800015AA
0x180001589  mov     rax, gs:30h
0x180001592  mov     rcx, [rax+8]
0x180001596  jmp     short loc_18000159D
0x180001598  cmp     rcx, rax
0x18000159b  jz      short loc_1800015B1
0x18000159d  xor     eax, eax
0x18000159f  lock cmpxchg cs:__scrt_native_startup_lock, rcx
0x1800015a8  jnz     short loc_180001598
0x1800015aa  xor     al, al
0x1800015ac  add     rsp, 28h
0x1800015b0  retn
0x1800015b1  mov     al, 1
0x1800015b3  jmp     short loc_1800015AC
```
