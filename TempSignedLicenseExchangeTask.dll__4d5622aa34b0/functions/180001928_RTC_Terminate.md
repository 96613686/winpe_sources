# _RTC_Terminate

- ea: `0x180001928`
- end: `0x180001963`
- name: `_RTC_Terminate`
- size: `59`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800011e8`

## callees

- `0x180001928`
- `0x18000d010`

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
0x180001928  mov     [rsp+arg_0], rbx
0x18000192d  push    rdi
0x18000192e  sub     rsp, 20h
0x180001932  lea     rbx, __rtc_tzz
0x180001939  lea     rdi, __rtc_tzz
0x180001940  jmp     short loc_180001953
0x180001942  mov     rax, [rbx]
0x180001945  test    rax, rax
0x180001948  jz      short loc_18000194F
0x18000194a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000194f  add     rbx, 8
0x180001953  cmp     rbx, rdi
0x180001956  jb      short loc_180001942
0x180001958  mov     rbx, [rsp+28h+arg_0]
0x18000195d  add     rsp, 20h
0x180001961  pop     rdi
0x180001962  retn
```
