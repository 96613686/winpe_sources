# __scrt_acquire_startup_lock

- ea: `0x180003a68`
- end: `0x180003aa1`
- name: `__scrt_acquire_startup_lock`
- size: `57`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800032e0`
- `0x1800033f8`

## callees

- `0x180003a68`
- `0x1800042e4`

## pseudocode

```c
char _scrt_acquire_startup_lock()
{
  PVOID StackBase; // rcx
  signed __int64 v1; // rax

  if ( _scrt_is_ucrt_dll_in_use() )
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
0x180003a68  sub     rsp, 28h
0x180003a6c  call    __scrt_is_ucrt_dll_in_use
0x180003a71  test    eax, eax
0x180003a73  jz      short loc_180003A96
0x180003a75  mov     rax, gs:30h
0x180003a7e  mov     rcx, [rax+8]
0x180003a82  jmp     short loc_180003A89
0x180003a84  cmp     rcx, rax
0x180003a87  jz      short loc_180003A9D
0x180003a89  xor     eax, eax
0x180003a8b  lock cmpxchg cs:__scrt_native_startup_lock, rcx
0x180003a94  jnz     short loc_180003A84
0x180003a96  xor     al, al
0x180003a98  add     rsp, 28h
0x180003a9c  retn
0x180003a9d  mov     al, 1
0x180003a9f  jmp     short loc_180003A98
```
