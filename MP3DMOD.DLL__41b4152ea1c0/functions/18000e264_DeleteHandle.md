# DeleteHandle

- ea: `0x18000e264`
- end: `0x18000e2a7`
- name: `DeleteHandle`
- size: `67`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18000e244`

## callees

- `0x18000a790`
- `0x18000a7b0`
- `0x18000e264`
- `0x18000e308`
- `0x180012010`

## pseudocode

```c
char __fastcall DeleteHandle(void *Block)
{
  char result; // al
  __int64 Dec; // rax

  result = IsValidHandle();
  if ( result )
  {
    Dec = GetDec();
    if ( Dec )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)Dec + 80LL))(Dec, 1);
    operator delete(Block);
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x18000e264  push    rbx
0x18000e266  sub     rsp, 20h
0x18000e26a  mov     rbx, rcx
0x18000e26d  call    IsValidHandle
0x18000e272  test    al, al
0x18000e274  jz      short loc_18000E2A1
0x18000e276  call    GetDec
0x18000e27b  mov     r8, rax
0x18000e27e  test    rax, rax
0x18000e281  jz      short loc_18000E297
0x18000e283  mov     rcx, [rax]
0x18000e286  mov     edx, 1
0x18000e28b  mov     rax, [rcx+50h]
0x18000e28f  mov     rcx, r8
0x18000e292  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e297  mov     rcx, rbx; Block
0x18000e29a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000e29f  mov     al, 1
0x18000e2a1  add     rsp, 20h
0x18000e2a5  pop     rbx
0x18000e2a6  retn
```
