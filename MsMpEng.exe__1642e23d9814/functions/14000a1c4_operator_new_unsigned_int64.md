# operator new(unsigned __int64)

- ea: `0x14000a1c4`
- end: `0x14000a200`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `14`
- callee_count: `5`
- tags: ``

## callers

- `0x140001fd8`
- `0x140002c70`
- `0x140002e60`
- `0x140003070`
- `0x140003aec`
- `0x140003d48`
- `0x140003e40`
- `0x14000a68c`
- `0x14000aec0`
- `0x140027f44`
- `0x140028378`
- `0x140028cd8`
- `0x140028e88`
- `0x1400290d8`

## callees

- `0x14000a1c4`
- `0x14000aa6c`
- `0x140016fb0`
- `0x140018a90`
- `0x140029af8`

## pseudocode

```c
void *__fastcall operator new(size_t Size)
{
  size_t i; // rbx
  void *result; // rax

  for ( i = Size; ; Size = i )
  {
    result = j__malloc_base(Size);
    if ( result )
      break;
    if ( !(unsigned int)sub_140018A90(i) )
    {
      if ( i != -1 )
      {
        sub_14000AA6C();
        __debugbreak();
      }
      sub_140029AF8();
      __debugbreak();
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000a1c4  push    rbx
0x14000a1c6  sub     rsp, 20h
0x14000a1ca  mov     rbx, rcx
0x14000a1cd  jmp     short loc_14000A1DE
0x14000a1cf  mov     rcx, rbx
0x14000a1d2  call    sub_140018A90
0x14000a1d7  test    eax, eax
0x14000a1d9  jz      short loc_14000A1EE
0x14000a1db  mov     rcx, rbx; Size
0x14000a1de  call    j__malloc_base
0x14000a1e3  test    rax, rax
0x14000a1e6  jz      short loc_14000A1CF
0x14000a1e8  add     rsp, 20h
0x14000a1ec  pop     rbx
0x14000a1ed  retn
0x14000a1ee  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x14000a1f2  jz      short loc_14000A1FA
0x14000a1f4  call    sub_14000AA6C
0x14000a1f9  int     3; Trap to Debugger
0x14000a1fa  call    sub_140029AF8
0x14000a1ff  int     3; Trap to Debugger
```
