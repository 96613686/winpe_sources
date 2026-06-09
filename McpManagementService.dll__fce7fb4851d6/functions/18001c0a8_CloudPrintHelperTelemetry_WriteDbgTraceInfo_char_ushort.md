# CloudPrintHelperTelemetry::WriteDbgTraceInfo(char *,ushort *,...)

- ea: `0x18001c0a8`
- end: `0x18001c0eb`
- name: `?WriteDbgTraceInfo@CloudPrintHelperTelemetry@@SAXPEADPEAGZZ`
- size: `67`
- prototype: `void(char *, unsigned __int16 *, ...)`
- caller_count: `19`
- callee_count: `3`
- tags: ``

## callers

- `0x180013a2c`
- `0x1800146b8`
- `0x180014c54`
- `0x180014de4`
- `0x1800154fc`
- `0x1800157bc`
- `0x180015f60`
- `0x180016184`
- `0x180016b54`
- `0x180017b98`
- `0x180018844`
- `0x18001892c`
- `0x180018bbc`
- `0x180018cc0`
- `0x18001963c`
- `0x180019d74`
- `0x18001a404`
- `0x18001b128`
- `0x18001bc2c`

## callees

- `0x180018e9c`
- `0x18001c0a8`
- `0x18001c140`

## pseudocode

```c
void CloudPrintHelperTelemetry::WriteDbgTraceInfo(char *a1, unsigned __int16 *a2, ...)
{
  va_list va; // [rsp+50h] [rbp+18h] BYREF

  va_start(va, a2);
  if ( CloudPrintHelperTelemetry::IsEnabled((unsigned __int8)a1, (unsigned __int64)a2) )
    CloudPrintHelperTelemetry::WriteDbgTraceMsg(1, a1, a2, va);
}

```

## disassembly

```asm
0x18001c0a8  mov     [rsp+arg_8], rdx
0x18001c0ad  mov     qword ptr [rsp+arg_10], r8
0x18001c0b2  mov     [rsp+arg_18], r9
0x18001c0b7  push    rbx
0x18001c0b8  sub     rsp, 30h
0x18001c0bc  mov     rbx, rcx
0x18001c0bf  call    ?IsEnabled@CloudPrintHelperTelemetry@@SA_NE_K@Z; CloudPrintHelperTelemetry::IsEnabled(uchar,unsigned __int64)
0x18001c0c4  test    al, al
0x18001c0c6  jz      short loc_18001C0E5
0x18001c0c8  mov     r8, [rsp+38h+arg_8]; unsigned __int16 *
0x18001c0cd  lea     r9, [rsp+38h+arg_10]; char *
0x18001c0d2  mov     rdx, rbx; char *
0x18001c0d5  mov     [rsp+38h+var_18], 0
0x18001c0de  mov     cl, 1; bool
0x18001c0e0  call    ?WriteDbgTraceMsg@CloudPrintHelperTelemetry@@SAX_NPEADPEAG1@Z; CloudPrintHelperTelemetry::WriteDbgTraceMsg(bool,char *,ushort *,char *)
0x18001c0e5  add     rsp, 30h
0x18001c0e9  pop     rbx
0x18001c0ea  retn
```
