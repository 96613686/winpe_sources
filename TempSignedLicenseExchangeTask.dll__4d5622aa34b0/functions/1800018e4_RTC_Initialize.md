# _RTC_Initialize

- ea: `0x1800018e4`
- end: `0x18000191f`
- name: `_RTC_Initialize`
- size: `59`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800010e8`

## callees

- `0x1800018e4`
- `0x18000d010`

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
0x1800018e4  mov     [rsp+arg_0], rbx
0x1800018e9  push    rdi
0x1800018ea  sub     rsp, 20h
0x1800018ee  lea     rbx, __rtc_izz
0x1800018f5  lea     rdi, __rtc_izz
0x1800018fc  jmp     short loc_18000190F
0x1800018fe  mov     rax, [rbx]
0x180001901  test    rax, rax
0x180001904  jz      short loc_18000190B
0x180001906  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000190b  add     rbx, 8
0x18000190f  cmp     rbx, rdi
0x180001912  jb      short loc_1800018FE
0x180001914  mov     rbx, [rsp+28h+arg_0]
0x180001919  add     rsp, 20h
0x18000191d  pop     rdi
0x18000191e  retn
```
