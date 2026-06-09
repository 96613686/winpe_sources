# operator new(unsigned __int64)

- ea: `0x140001a18`
- end: `0x140001a51`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `13`
- callee_count: `3`
- tags: ``

## callers

- `0x140002710`
- `0x14000279c`
- `0x140002e04`
- `0x140002f58`
- `0x1400030b4`
- `0x14000321c`
- `0x140003380`
- `0x140003e38`
- `0x140006e70`
- `0x14000761c`
- `0x14000e9a4`
- `0x1400166f4`
- `0x140016a44`

## callees

- `0x140001a18`
- `0x140002028`
- `0x140002034`

## pseudocode

```c
void *__fastcall operator new(size_t Size)
{
  size_t i; // rdi
  void *v2; // rbx

  for ( i = Size; ; Size = i )
  {
    v2 = malloc_0(Size);
    if ( v2 || !callnewh_0(i) )
      break;
  }
  return v2;
}

```

## disassembly

```asm
0x140001a18  mov     [rsp+arg_0], rbx
0x140001a1d  push    rdi
0x140001a1e  sub     rsp, 20h
0x140001a22  mov     rdi, rcx
0x140001a25  jmp     short loc_140001A36
0x140001a27  mov     rcx, rdi; Size
0x140001a2a  call    _callnewh_0
0x140001a2f  test    eax, eax
0x140001a31  jz      short loc_140001A43
0x140001a33  mov     rcx, rdi; Size
0x140001a36  call    malloc_0
0x140001a3b  mov     rbx, rax
0x140001a3e  test    rax, rax
0x140001a41  jz      short loc_140001A27
0x140001a43  mov     rax, rbx
0x140001a46  mov     rbx, [rsp+28h+arg_0]
0x140001a4b  add     rsp, 20h
0x140001a4f  pop     rdi
0x140001a50  retn
```
