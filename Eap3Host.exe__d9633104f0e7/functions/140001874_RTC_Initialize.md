# _RTC_Initialize

- ea: `0x140001874`
- end: `0x1400018af`
- name: `_RTC_Initialize`
- size: `59`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140001090`

## callees

- `0x140001874`
- `0x140003010`

## pseudocode

```c
void __cdecl RTC_Initialize()
{
  void (**i)(void); // rbx

  for ( i = (void (**)(void))&_rtc_izz; i < (void (**)(void))&_rtc_izz; ++i )
  {
    if ( *i )
      (*i)();
  }
}

```

## disassembly

```asm
0x140001874  mov     [rsp+arg_0], rbx
0x140001879  push    rdi
0x14000187a  sub     rsp, 20h
0x14000187e  lea     rbx, __rtc_izz
0x140001885  lea     rdi, __rtc_izz
0x14000188c  jmp     short loc_14000189F
0x14000188e  mov     rax, [rbx]
0x140001891  test    rax, rax
0x140001894  jz      short loc_14000189B
0x140001896  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000189b  add     rbx, 8
0x14000189f  cmp     rbx, rdi
0x1400018a2  jb      short loc_14000188E
0x1400018a4  mov     rbx, [rsp+28h+arg_0]
0x1400018a9  add     rsp, 20h
0x1400018ad  pop     rdi
0x1400018ae  retn
```
