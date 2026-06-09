# operator new(unsigned __int64)

- ea: `0x180001a30`
- end: `0x180001a61`
- name: `??2@YAPEAX_K@Z`
- size: `49`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `55`
- callee_count: `3`
- tags: ``

## callers

- `0x18000292c`
- `0x180002a70`
- `0x180006aac`
- `0x18000bab0`
- `0x18000c404`
- `0x18000c534`
- `0x18000c828`
- `0x18000ca74`
- `0x18000cb18`
- `0x18000cbb4`
- `0x18000e1c8`
- `0x18000f514`
- `0x18000f598`
- `0x1800104e4`
- `0x18001094c`
- `0x180011204`
- `0x1800112f0`
- `0x1800136c0`
- `0x18001595c`
- `0x180016714`
- `0x180016cbc`
- `0x18001734c`
- `0x180017674`
- `0x180017774`
- `0x18001910c`
- `0x1800191c0`
- `0x1800195b0`
- `0x1800199a4`
- `0x18001a4c8`
- `0x18001aa50`
- `0x18001aec4`
- `0x18001b038`
- `0x18001b550`
- `0x18001b990`
- `0x18001bbc0`
- `0x18001bd68`
- `0x18001bedc`
- `0x18001c7a4`
- `0x18001c924`
- `0x18001ce38`
- `0x18001cf78`
- `0x18001d4a8`
- `0x18001d798`
- `0x18001d938`
- `0x18001dc18`
- `0x18001dd58`
- `0x18001e498`
- `0x18001f930`
- `0x18001fae0`
- `0x18001fe78`

## callees

- `0x180001a30`
- `0x180001bd8`
- `0x1800022d6`

## import_xrefs

- `msvcrt!malloc` at `0x180001a4a`
- `msvcrt!malloc` at `0x180001a4a`

## pseudocode

```c
void *__fastcall operator new(size_t Size)
{
  size_t i; // rbx
  void *result; // rax

  for ( i = Size; ; Size = i )
  {
    result = malloc(Size);
    if ( result )
      break;
    if ( !callnewh_0(i) )
      std::_Xbad_alloc();
  }
  return result;
}

```

## disassembly

```asm
0x180001a30  push    rbx
0x180001a32  sub     rsp, 20h
0x180001a36  mov     rbx, rcx
0x180001a39  jmp     short loc_180001A4A
0x180001a3b  mov     rcx, rbx; Size
0x180001a3e  call    _callnewh_0
0x180001a43  test    eax, eax
0x180001a45  jz      short loc_180001A5B
0x180001a47  mov     rcx, rbx; Size
0x180001a4a  call    cs:__imp_malloc
0x180001a50  test    rax, rax
0x180001a53  jz      short loc_180001A3B
0x180001a55  add     rsp, 20h
0x180001a59  pop     rbx
0x180001a5a  retn
0x180001a5b  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
