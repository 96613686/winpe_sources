# __scrt_acquire_startup_lock

- ea: `0x180001654`
- end: `0x18000168d`
- name: `__scrt_acquire_startup_lock`
- size: `57`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800011a0`
- `0x1800012b8`

## callees

- `0x180001654`
- `0x180001e94`

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
0x180001654  sub     rsp, 28h
0x180001658  call    __scrt_is_ucrt_dll_in_use
0x18000165d  test    eax, eax
0x18000165f  jz      short loc_180001682
0x180001661  mov     rax, gs:30h
0x18000166a  mov     rcx, [rax+8]
0x18000166e  jmp     short loc_180001675
0x180001670  cmp     rcx, rax
0x180001673  jz      short loc_180001689
0x180001675  xor     eax, eax
0x180001677  lock cmpxchg cs:__scrt_native_startup_lock, rcx
0x180001680  jnz     short loc_180001670
0x180001682  xor     al, al
0x180001684  add     rsp, 28h
0x180001688  retn
0x180001689  mov     al, 1
0x18000168b  jmp     short loc_180001684
```
