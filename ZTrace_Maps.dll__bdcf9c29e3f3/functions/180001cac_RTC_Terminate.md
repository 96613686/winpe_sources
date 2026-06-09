# _RTC_Terminate

- ea: `0x180001cac`
- end: `0x180001ce7`
- name: `_RTC_Terminate`
- size: `59`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180001508`

## callees

- `0x180001cac`
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
0x180001cac  mov     [rsp+arg_0], rbx
0x180001cb1  push    rdi
0x180001cb2  sub     rsp, 20h
0x180001cb6  lea     rbx, __rtc_tzz
0x180001cbd  lea     rdi, __rtc_tzz
0x180001cc4  jmp     short loc_180001CD7
0x180001cc6  mov     rax, [rbx]
0x180001cc9  test    rax, rax
0x180001ccc  jz      short loc_180001CD3
0x180001cce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001cd3  add     rbx, 8
0x180001cd7  cmp     rbx, rdi
0x180001cda  jb      short loc_180001CC6
0x180001cdc  mov     rbx, [rsp+28h+arg_0]
0x180001ce1  add     rsp, 20h
0x180001ce5  pop     rdi
0x180001ce6  retn
```
