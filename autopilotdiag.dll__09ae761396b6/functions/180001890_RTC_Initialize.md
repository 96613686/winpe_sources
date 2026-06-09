# _RTC_Initialize

- ea: `0x180001890`
- end: `0x1800018cb`
- name: `_RTC_Initialize`
- size: `59`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800010e8`

## callees

- `0x180001890`
- `0x180002010`

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
0x180001890  mov     [rsp+arg_0], rbx
0x180001895  push    rdi
0x180001896  sub     rsp, 20h
0x18000189a  lea     rbx, __rtc_izz
0x1800018a1  lea     rdi, __rtc_izz
0x1800018a8  jmp     short loc_1800018BB
0x1800018aa  mov     rax, [rbx]
0x1800018ad  test    rax, rax
0x1800018b0  jz      short loc_1800018B7
0x1800018b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800018b7  add     rbx, 8
0x1800018bb  cmp     rbx, rdi
0x1800018be  jb      short loc_1800018AA
0x1800018c0  mov     rbx, [rsp+28h+arg_0]
0x1800018c5  add     rsp, 20h
0x1800018c9  pop     rdi
0x1800018ca  retn
```
