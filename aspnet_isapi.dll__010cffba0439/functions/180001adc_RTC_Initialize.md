# _RTC_Initialize

- ea: `0x180001adc`
- end: `0x180001b18`
- name: `_RTC_Initialize`
- size: `60`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800011a0`

## callees

- `0x180001adc`
- `0x180001f00`

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
0x180001adc  mov     [rsp+arg_0], rbx
0x180001ae1  push    rdi
0x180001ae2  sub     rsp, 20h
0x180001ae6  lea     rbx, __rtc_izz
0x180001aed  lea     rdi, __rtc_izz
0x180001af4  jmp     short loc_180001B08
0x180001af6  mov     rax, [rbx]
0x180001af9  test    rax, rax
0x180001afc  jz      short loc_180001B04
0x180001afe  call    cs:__guard_dispatch_icall_fptr
0x180001b04  add     rbx, 8
0x180001b08  cmp     rbx, rdi
0x180001b0b  jb      short loc_180001AF6
0x180001b0d  mov     rbx, [rsp+28h+arg_0]
0x180001b12  add     rsp, 20h
0x180001b16  pop     rdi
0x180001b17  retn
```
