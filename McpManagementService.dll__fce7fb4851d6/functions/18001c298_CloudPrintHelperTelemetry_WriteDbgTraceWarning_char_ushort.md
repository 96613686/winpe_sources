# CloudPrintHelperTelemetry::WriteDbgTraceWarning(char *,ushort *,...)

- ea: `0x18001c298`
- end: `0x18001c2db`
- name: `?WriteDbgTraceWarning@CloudPrintHelperTelemetry@@SAXPEADPEAGZZ`
- size: `67`
- prototype: `void(char *, unsigned __int16 *, ...)`
- caller_count: `29`
- callee_count: `3`
- tags: ``

## callers

- `0x180013598`
- `0x18001364c`
- `0x180013734`
- `0x1800137ac`
- `0x1800138ec`
- `0x180013948`
- `0x180013a2c`
- `0x1800142f0`
- `0x180014504`
- `0x18001463c`
- `0x1800146b8`
- `0x180014c54`
- `0x180014de4`
- `0x1800157bc`
- `0x18001601c`
- `0x1800160d0`
- `0x180016184`
- `0x180018844`
- `0x180018bbc`
- `0x180018cc0`
- `0x180018e60`
- `0x1800195fc`
- `0x180019c54`
- `0x18001b128`
- `0x18001bc2c`
- `0x18001f77c`
- `0x1800203b0`
- `0x180020e9c`
- `0x180025fc0`

## callees

- `0x180018e9c`
- `0x18001c140`
- `0x18001c298`

## pseudocode

```c
void CloudPrintHelperTelemetry::WriteDbgTraceWarning(char *a1, unsigned __int16 *a2, ...)
{
  va_list va; // [rsp+50h] [rbp+18h] BYREF

  va_start(va, a2);
  if ( CloudPrintHelperTelemetry::IsEnabled((unsigned __int8)a1, (unsigned __int64)a2) )
    CloudPrintHelperTelemetry::WriteDbgTraceMsg(0, a1, a2, va);
}

```

## disassembly

```asm
0x18001c298  mov     [rsp+arg_8], rdx
0x18001c29d  mov     qword ptr [rsp+arg_10], r8
0x18001c2a2  mov     [rsp+arg_18], r9
0x18001c2a7  push    rbx
0x18001c2a8  sub     rsp, 30h
0x18001c2ac  mov     rbx, rcx
0x18001c2af  call    ?IsEnabled@CloudPrintHelperTelemetry@@SA_NE_K@Z; CloudPrintHelperTelemetry::IsEnabled(uchar,unsigned __int64)
0x18001c2b4  test    al, al
0x18001c2b6  jz      short loc_18001C2D5
0x18001c2b8  mov     r8, [rsp+38h+arg_8]; unsigned __int16 *
0x18001c2bd  lea     r9, [rsp+38h+arg_10]; char *
0x18001c2c2  mov     rdx, rbx; char *
0x18001c2c5  mov     [rsp+38h+var_18], 0
0x18001c2ce  xor     ecx, ecx; bool
0x18001c2d0  call    ?WriteDbgTraceMsg@CloudPrintHelperTelemetry@@SAX_NPEADPEAG1@Z; CloudPrintHelperTelemetry::WriteDbgTraceMsg(bool,char *,ushort *,char *)
0x18001c2d5  add     rsp, 30h
0x18001c2d9  pop     rbx
0x18001c2da  retn
```
