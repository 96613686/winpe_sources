# DereferenceRefCount

- ea: `0x180002d40`
- end: `0x180002d62`
- name: `DereferenceRefCount`
- size: `34`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `14`
- callee_count: `2`
- tags: ``

## callers

- `0x180001240`
- `0x1800021f0`
- `0x180002908`
- `0x1800033b0`
- `0x180009a00`
- `0x18000a620`
- `0x18000afbc`
- `0x18000b9fc`
- `0x18000bc78`
- `0x18000bf68`
- `0x18000cec8`
- `0x18000d1a0`
- `0x18000df30`
- `0x18000e9a0`

## callees

- `0x180002d40`
- `0x18001d010`

## pseudocode

```c
__int64 __fastcall DereferenceRefCount(__int64 a1)
{
  __int64 result; // rax

  result = (unsigned int)_InterlockedExchangeAdd((volatile signed __int32 *)a1, 0xFFFFFFFF);
  if ( (_DWORD)result == 1 )
    return (*(__int64 (**)(void))(a1 + 8))();
  return result;
}

```

## disassembly

```asm
0x180002d40  sub     rsp, 28h
0x180002d44  mov     eax, 0FFFFFFFFh
0x180002d49  lock xadd [rcx], eax
0x180002d4d  cmp     eax, 1
0x180002d50  jz      short loc_180002D57
0x180002d52  add     rsp, 28h
0x180002d56  retn
0x180002d57  mov     rax, [rcx+8]
0x180002d5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d60  jmp     short loc_180002D52
```
