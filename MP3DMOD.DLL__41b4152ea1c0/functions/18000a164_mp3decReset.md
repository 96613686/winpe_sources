# mp3decReset

- ea: `0x18000a164`
- end: `0x18000a18f`
- name: `mp3decReset`
- size: `43`
- prototype: `__int64()`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000a1d0`
- `0x18000d8d0`

## callees

- `0x18000a164`
- `0x18000a790`
- `0x180012010`

## pseudocode

```c
__int64 mp3decReset()
{
  __int64 Dec; // rax

  Dec = GetDec();
  if ( !Dec )
    return 3221225475LL;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)Dec + 8LL))(Dec);
  return 0;
}

```

## disassembly

```asm
0x18000a164  sub     rsp, 28h
0x18000a168  call    GetDec
0x18000a16d  mov     rcx, rax
0x18000a170  test    rax, rax
0x18000a173  jz      short loc_18000A188
0x18000a175  mov     rax, [rax]
0x18000a178  mov     rax, [rax+8]
0x18000a17c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a181  xor     eax, eax
0x18000a183  add     rsp, 28h
0x18000a187  retn
0x18000a188  mov     eax, 0C0000003h
0x18000a18d  jmp     short loc_18000A183
```
