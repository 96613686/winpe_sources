# _RTC_Terminate

- ea: `0x1800018d4`
- end: `0x18000190f`
- name: `_RTC_Terminate`
- size: `59`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800011e8`

## callees

- `0x1800018d4`
- `0x180002010`

## pseudocode

```c
void __cdecl RTC_Terminate()
{
  void (**i)(void); // rbx

  for ( i = (void (**)(void))&_rtc_tzz; i < (void (**)(void))&_rtc_tzz; ++i )
  {
    if ( *i )
      (*i)();
  }
}

```

## disassembly

```asm
0x1800018d4  mov     [rsp+arg_0], rbx
0x1800018d9  push    rdi
0x1800018da  sub     rsp, 20h
0x1800018de  lea     rbx, __rtc_tzz
0x1800018e5  lea     rdi, __rtc_tzz
0x1800018ec  jmp     short loc_1800018FF
0x1800018ee  mov     rax, [rbx]
0x1800018f1  test    rax, rax
0x1800018f4  jz      short loc_1800018FB
0x1800018f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800018fb  add     rbx, 8
0x1800018ff  cmp     rbx, rdi
0x180001902  jb      short loc_1800018EE
0x180001904  mov     rbx, [rsp+28h+arg_0]
0x180001909  add     rsp, 20h
0x18000190d  pop     rdi
0x18000190e  retn
```
