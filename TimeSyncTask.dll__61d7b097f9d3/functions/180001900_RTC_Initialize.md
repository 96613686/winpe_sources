# _RTC_Initialize

- ea: `0x180001900`
- end: `0x18000193b`
- name: `_RTC_Initialize`
- size: `59`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180001148`

## callees

- `0x180001900`
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
0x180001900  mov     [rsp+arg_0], rbx
0x180001905  push    rdi
0x180001906  sub     rsp, 20h
0x18000190a  lea     rbx, __rtc_izz
0x180001911  lea     rdi, __rtc_izz
0x180001918  jmp     short loc_18000192B
0x18000191a  mov     rax, [rbx]
0x18000191d  test    rax, rax
0x180001920  jz      short loc_180001927
0x180001922  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001927  add     rbx, 8
0x18000192b  cmp     rbx, rdi
0x18000192e  jb      short loc_18000191A
0x180001930  mov     rbx, [rsp+28h+arg_0]
0x180001935  add     rsp, 20h
0x180001939  pop     rdi
0x18000193a  retn
```
