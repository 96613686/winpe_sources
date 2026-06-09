# __scrt_acquire_startup_lock

- ea: `0x140001020`
- end: `0x14000105a`
- name: `__scrt_acquire_startup_lock`
- size: `58`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140001ac0`

## callees

- `0x140001020`
- `0x1400022d4`

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
0x140001020  sub     rsp, 28h
0x140001024  call    __scrt_is_ucrt_dll_in_use
0x140001029  test    eax, eax
0x14000102b  jz      short loc_14000104E
0x14000102d  mov     rax, gs:30h
0x140001036  mov     rcx, [rax+8]
0x14000103a  jmp     short loc_140001041
0x14000103c  cmp     rcx, rax
0x14000103f  jz      short loc_140001055
0x140001041  xor     eax, eax
0x140001043  lock cmpxchg cs:__scrt_native_startup_lock, rcx
0x14000104c  jnz     short loc_14000103C
0x14000104e  xor     al, al
0x140001050  add     rsp, 28h
0x140001054  retn
0x140001055  mov     al, 1
0x140001057  jmp     short loc_140001050
```
