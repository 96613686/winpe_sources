# operator new(unsigned __int64)

- ea: `0x1800215e8`
- end: `0x180021621`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `47`
- callee_count: `3`
- tags: ``

## callers

- `0x180003350`
- `0x180004abc`
- `0x180008c50`
- `0x180008f24`
- `0x180009530`
- `0x180009a60`
- `0x180009e04`
- `0x18000a3b0`
- `0x18000b4a0`
- `0x18000b5b0`
- `0x18000be7c`
- `0x18000c7b0`
- `0x180010800`
- `0x1800108fc`
- `0x180011230`
- `0x180013cf0`
- `0x180014220`
- `0x180014480`
- `0x180015fa0`
- `0x180017af0`
- `0x1800180a0`
- `0x1800183f8`
- `0x180019960`
- `0x180019bc0`
- `0x180019e80`
- `0x18001a004`
- `0x18001d0c8`
- `0x18001e670`
- `0x180020204`
- `0x180020620`
- `0x180020964`
- `0x180021634`
- `0x180022a20`
- `0x180022fd0`
- `0x180023050`
- `0x1800232b0`
- `0x1800232f0`
- `0x180023340`
- `0x1800233b0`
- `0x1800236f0`
- `0x18002a470`
- `0x18002b260`
- `0x18002be80`
- `0x18002c5f0`
- `0x18002cac0`
- `0x18002da10`
- `0x18002e5f0`

## callees

- `0x1800215e8`
- `0x1800222a6`
- `0x180022330`

## pseudocode

```c
void *__fastcall operator new(size_t Size)
{
  size_t i; // rdi
  void *v2; // rbx

  for ( i = Size; ; Size = i )
  {
    v2 = o_malloc_0(Size);
    if ( v2 || !(unsigned int)o__callnewh_0(i) )
      break;
  }
  return v2;
}

```

## disassembly

```asm
0x1800215e8  mov     [rsp+arg_0], rbx
0x1800215ed  push    rdi
0x1800215ee  sub     rsp, 20h
0x1800215f2  mov     rdi, rcx
0x1800215f5  jmp     short loc_180021606
0x1800215f7  mov     rcx, rdi
0x1800215fa  call    _o__callnewh_0
0x1800215ff  test    eax, eax
0x180021601  jz      short loc_180021613
0x180021603  mov     rcx, rdi; Size
0x180021606  call    _o_malloc_0
0x18002160b  mov     rbx, rax
0x18002160e  test    rax, rax
0x180021611  jz      short loc_1800215F7
0x180021613  mov     rax, rbx
0x180021616  mov     rbx, [rsp+28h+arg_0]
0x18002161b  add     rsp, 20h
0x18002161f  pop     rdi
0x180021620  retn
```
