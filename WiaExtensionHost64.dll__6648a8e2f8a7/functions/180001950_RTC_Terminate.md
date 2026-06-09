# _RTC_Terminate

- ea: `0x180001950`
- end: `0x18000198b`
- name: `_RTC_Terminate`
- size: `59`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180001228`

## callees

- `0x180001950`
- `0x180003010`

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
0x180001950  mov     [rsp+arg_0], rbx
0x180001955  push    rdi
0x180001956  sub     rsp, 20h
0x18000195a  lea     rbx, __rtc_tzz
0x180001961  lea     rdi, __rtc_tzz
0x180001968  jmp     short loc_18000197B
0x18000196a  mov     rax, [rbx]
0x18000196d  test    rax, rax
0x180001970  jz      short loc_180001977
0x180001972  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001977  add     rbx, 8
0x18000197b  cmp     rbx, rdi
0x18000197e  jb      short loc_18000196A
0x180001980  mov     rbx, [rsp+28h+arg_0]
0x180001985  add     rsp, 20h
0x180001989  pop     rdi
0x18000198a  retn
```
