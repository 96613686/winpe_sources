# _RTC_Terminate

- ea: `0x180001944`
- end: `0x18000197f`
- name: `_RTC_Terminate`
- size: `59`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180001248`

## callees

- `0x180001944`
- `0x180004010`

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
0x180001944  mov     [rsp+arg_0], rbx
0x180001949  push    rdi
0x18000194a  sub     rsp, 20h
0x18000194e  lea     rbx, __rtc_tzz
0x180001955  lea     rdi, __rtc_tzz
0x18000195c  jmp     short loc_18000196F
0x18000195e  mov     rax, [rbx]
0x180001961  test    rax, rax
0x180001964  jz      short loc_18000196B
0x180001966  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000196b  add     rbx, 8
0x18000196f  cmp     rbx, rdi
0x180001972  jb      short loc_18000195E
0x180001974  mov     rbx, [rsp+28h+arg_0]
0x180001979  add     rsp, 20h
0x18000197d  pop     rdi
0x18000197e  retn
```
