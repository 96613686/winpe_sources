# _RTC_Initialize

- ea: `0x140001180`
- end: `0x1400011bc`
- name: `_RTC_Initialize`
- size: `60`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140001d40`

## callees

- `0x140001180`
- `0x140001540`

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
0x140001180  mov     [rsp+arg_0], rbx
0x140001185  push    rdi
0x140001186  sub     rsp, 20h
0x14000118a  lea     rbx, __rtc_izz
0x140001191  lea     rdi, __rtc_izz
0x140001198  jmp     short loc_1400011AC
0x14000119a  mov     rax, [rbx]
0x14000119d  test    rax, rax
0x1400011a0  jz      short loc_1400011A8
0x1400011a2  call    cs:__guard_dispatch_icall_fptr
0x1400011a8  add     rbx, 8
0x1400011ac  cmp     rbx, rdi
0x1400011af  jb      short loc_14000119A
0x1400011b1  mov     rbx, [rsp+28h+arg_0]
0x1400011b6  add     rsp, 20h
0x1400011ba  pop     rdi
0x1400011bb  retn
```
