# __scrt_acquire_startup_lock

- ea: `0x180001e30`
- end: `0x180001e69`
- name: `__scrt_acquire_startup_lock`
- size: `57`
- prototype: `char()`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001998`
- `0x180001a98`

## callees

- `0x180001e30`
- `0x180002594`

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
0x180001e30  sub     rsp, 28h
0x180001e34  call    __scrt_is_ucrt_dll_in_use
0x180001e39  test    eax, eax
0x180001e3b  jz      short loc_180001E5E
0x180001e3d  mov     rax, gs:30h
0x180001e46  mov     rcx, [rax+8]
0x180001e4a  jmp     short loc_180001E51
0x180001e4c  cmp     rcx, rax
0x180001e4f  jz      short loc_180001E65
0x180001e51  xor     eax, eax
0x180001e53  lock cmpxchg cs:__scrt_native_startup_lock, rcx
0x180001e5c  jnz     short loc_180001E4C
0x180001e5e  xor     al, al
0x180001e60  add     rsp, 28h
0x180001e64  retn
0x180001e65  mov     al, 1
0x180001e67  jmp     short loc_180001E60
```
