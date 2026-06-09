# __security_check_cookie

- ea: `0x180001b60`
- end: `0x180001b7e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `118`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000108c`
- `0x1800011a4`
- `0x180001250`
- `0x180001318`
- `0x180002c74`
- `0x180002e7c`
- `0x1800038b0`
- `0x180003b44`
- `0x1800040e8`
- `0x1800044b8`
- `0x180004a24`
- `0x180004da0`
- `0x1800065dc`
- `0x180006ab0`
- `0x180008080`
- `0x180008dc0`
- `0x18000911c`
- `0x180009260`
- `0x180009a10`
- `0x18000a720`
- `0x18000a820`
- `0x18000aa40`
- `0x18000b570`
- `0x18000b620`
- `0x18000b9d0`
- `0x18000c870`
- `0x18000cb9c`
- `0x18000cd38`
- `0x18000d09c`
- `0x18000d290`
- `0x18000d3f4`
- `0x18000d9e0`
- `0x18000dd98`
- `0x18000de80`
- `0x18000e054`
- `0x18000e158`
- `0x18000e4cc`
- `0x18000e7e8`
- `0x18000ea40`
- `0x18000eaf8`
- `0x18000ed34`
- `0x18000ef04`
- `0x18000f0c0`
- `0x18000f280`
- `0x18000f344`
- `0x18000f47c`
- `0x18000f6fc`
- `0x18000f798`
- `0x18000f924`
- `0x180010230`

## callees

- `0x180001b60`
- `0x180002140`

## pseudocode

```c
void __cdecl _security_check_cookie(uintptr_t StackCookie)
{
  __int64 v1; // rcx

  if ( StackCookie != _security_cookie )
ReportFailure:
    _report_gsfailure(StackCookie);
  v1 = __ROL8__(StackCookie, 16);
  if ( (_WORD)v1 )
  {
    StackCookie = __ROR8__(v1, 16);
    goto ReportFailure;
  }
}

```

## disassembly

```asm
0x180001b60  cmp     rcx, cs:__security_cookie
0x180001b67  jnz     short ReportFailure
0x180001b69  rol     rcx, 10h
0x180001b6d  test    cx, 0FFFFh
0x180001b72  jnz     short RestoreRcx
0x180001b74  retn
0x180001b75  ror     rcx, 10h; StackCookie
0x180001b79  jmp     __report_gsfailure
```
