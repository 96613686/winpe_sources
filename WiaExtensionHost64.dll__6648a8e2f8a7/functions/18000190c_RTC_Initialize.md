# _RTC_Initialize

- ea: `0x18000190c`
- end: `0x180001947`
- name: `_RTC_Initialize`
- size: `59`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180001128`

## callees

- `0x18000190c`
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
0x18000190c  mov     [rsp+arg_0], rbx
0x180001911  push    rdi
0x180001912  sub     rsp, 20h
0x180001916  lea     rbx, __rtc_izz
0x18000191d  lea     rdi, __rtc_izz
0x180001924  jmp     short loc_180001937
0x180001926  mov     rax, [rbx]
0x180001929  test    rax, rax
0x18000192c  jz      short loc_180001933
0x18000192e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001933  add     rbx, 8
0x180001937  cmp     rbx, rdi
0x18000193a  jb      short loc_180001926
0x18000193c  mov     rbx, [rsp+28h+arg_0]
0x180001941  add     rsp, 20h
0x180001945  pop     rdi
0x180001946  retn
```
