# _RTC_Terminate

- ea: `0x180001958`
- end: `0x180001993`
- name: `_RTC_Terminate`
- size: `59`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180001268`

## callees

- `0x180001958`
- `0x180002010`

## pseudocode

```c
void __cdecl RTC_Terminate()
{
  void (**i)(void); // rbx

  for ( i = &_rtc_tzz; i < &_rtc_tzz; ++i )
  {
    if ( *i )
      (*i)();
  }
}

```

## disassembly

```asm
0x180001958  mov     [rsp+arg_0], rbx
0x18000195d  push    rdi
0x18000195e  sub     rsp, 20h
0x180001962  lea     rbx, __rtc_tzz
0x180001969  lea     rdi, __rtc_tzz
0x180001970  jmp     short loc_180001983
0x180001972  mov     rax, [rbx]
0x180001975  test    rax, rax
0x180001978  jz      short loc_18000197F
0x18000197a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000197f  add     rbx, 8
0x180001983  cmp     rbx, rdi
0x180001986  jb      short loc_180001972
0x180001988  mov     rbx, [rsp+28h+arg_0]
0x18000198d  add     rsp, 20h
0x180001991  pop     rdi
0x180001992  retn
```
