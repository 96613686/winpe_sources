# _RTC_Initialize

- ea: `0x180001914`
- end: `0x18000194f`
- name: `_RTC_Initialize`
- size: `59`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800010e8`

## callees

- `0x180001914`
- `0x180003010`

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
0x180001914  mov     [rsp+arg_0], rbx
0x180001919  push    rdi
0x18000191a  sub     rsp, 20h
0x18000191e  lea     rbx, __rtc_izz
0x180001925  lea     rdi, __rtc_izz
0x18000192c  jmp     short loc_18000193F
0x18000192e  mov     rax, [rbx]
0x180001931  test    rax, rax
0x180001934  jz      short loc_18000193B
0x180001936  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000193b  add     rbx, 8
0x18000193f  cmp     rbx, rdi
0x180001942  jb      short loc_18000192E
0x180001944  mov     rbx, [rsp+28h+arg_0]
0x180001949  add     rsp, 20h
0x18000194d  pop     rdi
0x18000194e  retn
```
