# CodecDSPGetInterface

- ea: `0x18000c168`
- end: `0x18000c18e`
- name: `CodecDSPGetInterface`
- size: `38`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c080`
- `0x18000c0d0`

## callees

- `0x18000c168`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall CodecDSPGetInterface(__int64 a1, _QWORD *a2)
{
  if ( !a2 )
    return 2147500035LL;
  *a2 = a1;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  return 0;
}

```

## disassembly

```asm
0x18000c168  sub     rsp, 28h
0x18000c16c  test    rdx, rdx
0x18000c16f  jz      short loc_18000C187
0x18000c171  mov     [rdx], rcx
0x18000c174  mov     rax, [rcx]
0x18000c177  mov     rax, [rax+8]
0x18000c17b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c180  xor     eax, eax
0x18000c182  add     rsp, 28h
0x18000c186  retn
0x18000c187  mov     eax, 80004003h
0x18000c18c  jmp     short loc_18000C182
```
