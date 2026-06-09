# _RTC_Initialize

- ea: `0x180001c68`
- end: `0x180001ca3`
- name: `_RTC_Initialize`
- size: `59`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180001408`

## callees

- `0x180001c68`
- `0x180004010`

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
0x180001c68  mov     [rsp+arg_0], rbx
0x180001c6d  push    rdi
0x180001c6e  sub     rsp, 20h
0x180001c72  lea     rbx, __rtc_izz
0x180001c79  lea     rdi, __rtc_izz
0x180001c80  jmp     short loc_180001C93
0x180001c82  mov     rax, [rbx]
0x180001c85  test    rax, rax
0x180001c88  jz      short loc_180001C8F
0x180001c8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c8f  add     rbx, 8
0x180001c93  cmp     rbx, rdi
0x180001c96  jb      short loc_180001C82
0x180001c98  mov     rbx, [rsp+28h+arg_0]
0x180001c9d  add     rsp, 20h
0x180001ca1  pop     rdi
0x180001ca2  retn
```
