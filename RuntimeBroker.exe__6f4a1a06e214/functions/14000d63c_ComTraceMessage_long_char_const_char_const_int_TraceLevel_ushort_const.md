# ComTraceMessage(long,char const *,char const *,int,TraceLevel,ushort const *,...)

- ea: `0x14000d63c`
- end: `0x14000d670`
- name: `?ComTraceMessage@@YAXJPEBD0HW4TraceLevel@@PEBGZZ`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400060d0`

## callees

- `0x14000eb14`

## pseudocode

```c
void ComTraceMessage(int a1, __int64 a2, __int64 a3, int a4, unsigned int a5, unsigned __int16 *a6, ...)
{
  va_list va; // [rsp+90h] [rbp+38h] BYREF

  va_start(va, a6);
  ComTraceMessageWorker(a1, a2, a3, a4, a5, a6, va);
}

```

## disassembly

```asm
0x14000d63c  mov     r11, rsp
0x14000d63f  sub     rsp, 58h
0x14000d643  lea     rax, [r11+38h]
0x14000d647  mov     qword ptr [r11-18h], 0
0x14000d64f  mov     [r11-28h], rax
0x14000d653  mov     rax, [r11+30h]
0x14000d657  mov     [r11-30h], rax
0x14000d65b  mov     eax, [rsp+58h+arg_20]
0x14000d662  mov     [rsp+58h+var_38], eax; int
0x14000d666  call    ComTraceMessageWorker
0x14000d66b  add     rsp, 58h
0x14000d66f  retn
```
