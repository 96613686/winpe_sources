# LogMessage(uint,char const *,uint,char const *,ushort const *,...)

- ea: `0x180011470`
- end: `0x180011499`
- name: `?LogMessage@@YAXIPEBDI0PEBGZZ`
- size: `41`
- prototype: `void(unsigned int, const char *, unsigned int, const char *, const unsigned __int16 *, ...)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1800070d4`
- `0x1800078c0`
- `0x18000be7c`
- `0x18000ee24`
- `0x180011248`
- `0x1800114a0`

## callees

- `0x1800114a0`

## pseudocode

```c
void LogMessage(unsigned int a1, const char *a2, unsigned int a3, const char *a4, wchar_t *a5, ...)
{
  va_list va; // [rsp+78h] [rbp+30h] BYREF

  va_start(va, a5);
  LogMessageV(a1, a2, a3, a4, a5, va);
}

```

## disassembly

```asm
0x180011470  mov     r11, rsp
0x180011473  sub     rsp, 48h
0x180011477  lea     rax, [r11+30h]
0x18001147b  mov     qword ptr [r11-18h], 0
0x180011483  mov     [r11-20h], rax
0x180011487  mov     rax, [r11+28h]
0x18001148b  mov     [r11-28h], rax
0x18001148f  call    ?LogMessageV@@YAXIPEBDI0PEBGPEAD@Z; LogMessageV(uint,char const *,uint,char const *,ushort const *,char *)
0x180011494  add     rsp, 48h
0x180011498  retn
```
