# _RTC_Terminate

- ea: `0x180001b18`
- end: `0x180001b54`
- name: `_RTC_Terminate`
- size: `60`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800012b8`

## callees

- `0x180001b18`
- `0x180001f00`

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
0x180001b18  mov     [rsp+arg_0], rbx
0x180001b1d  push    rdi
0x180001b1e  sub     rsp, 20h
0x180001b22  lea     rbx, __rtc_tzz
0x180001b29  lea     rdi, __rtc_tzz
0x180001b30  jmp     short loc_180001B44
0x180001b32  mov     rax, [rbx]
0x180001b35  test    rax, rax
0x180001b38  jz      short loc_180001B40
0x180001b3a  call    cs:__guard_dispatch_icall_fptr
0x180001b40  add     rbx, 8
0x180001b44  cmp     rbx, rdi
0x180001b47  jb      short loc_180001B32
0x180001b49  mov     rbx, [rsp+28h+arg_0]
0x180001b4e  add     rsp, 20h
0x180001b52  pop     rdi
0x180001b53  retn
```
