# __scrt_acquire_startup_lock

- ea: `0x140001384`
- end: `0x1400013bd`
- name: `__scrt_acquire_startup_lock`
- size: `57`
- prototype: `char()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140001180`

## callees

- `0x140001384`
- `0x140001bfc`

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
0x140001384  sub     rsp, 28h
0x140001388  call    __scrt_is_ucrt_dll_in_use
0x14000138d  test    eax, eax
0x14000138f  jz      short loc_1400013B2
0x140001391  mov     rax, gs:30h
0x14000139a  mov     rcx, [rax+8]
0x14000139e  jmp     short loc_1400013A5
0x1400013a0  cmp     rcx, rax
0x1400013a3  jz      short loc_1400013B9
0x1400013a5  xor     eax, eax
0x1400013a7  lock cmpxchg cs:__scrt_native_startup_lock, rcx
0x1400013b0  jnz     short loc_1400013A0
0x1400013b2  xor     al, al
0x1400013b4  add     rsp, 28h
0x1400013b8  retn
0x1400013b9  mov     al, 1
0x1400013bb  jmp     short loc_1400013B4
```
