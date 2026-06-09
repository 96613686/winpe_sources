# LogMessage(uint,char const *,uint,char const *,ushort const *,...)

- ea: `0x180001fd8`
- end: `0x180002001`
- name: `?LogMessage@@YAXIPEBDI0PEBGZZ`
- size: `41`
- prototype: `void(unsigned int, const char *, unsigned int, const char *, wchar_t *, ...)`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x180002008`
- `0x180002204`
- `0x1800024b0`
- `0x180002520`
- `0x180002664`
- `0x18000280c`
- `0x180002c00`
- `0x180002c90`
- `0x180002e30`
- `0x18000c130`
- `0x18000c380`

## callees

- `0x180002008`

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
0x180001fd8  mov     r11, rsp
0x180001fdb  sub     rsp, 48h
0x180001fdf  lea     rax, [r11+30h]
0x180001fe3  mov     qword ptr [r11-18h], 0
0x180001feb  mov     [r11-20h], rax
0x180001fef  mov     rax, [r11+28h]
0x180001ff3  mov     [r11-28h], rax
0x180001ff7  call    ?LogMessageV@@YAXIPEBDI0PEBGPEAD@Z; LogMessageV(uint,char const *,uint,char const *,ushort const *,char *)
0x180001ffc  add     rsp, 48h
0x180002000  retn
```
