# __security_check_cookie

- ea: `0x18001cf50`
- end: `0x18001cf6e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `52`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x18000142c`
- `0x1800014c8`
- `0x180001730`
- `0x180001b78`
- `0x1800022b0`
- `0x1800029c0`
- `0x180002e20`
- `0x1800036f0`
- `0x180003bc0`
- `0x180004a80`
- `0x180005230`
- `0x1800060a0`
- `0x180007880`
- `0x180008630`
- `0x180008c40`
- `0x180009340`
- `0x1800095f0`
- `0x180009740`
- `0x18000a7d0`
- `0x18000b180`
- `0x18000b3d0`
- `0x18000cc40`
- `0x18000df40`
- `0x18000e4f0`
- `0x18000ec10`
- `0x18000f680`
- `0x180010560`
- `0x180011190`
- `0x180013228`
- `0x180013950`
- `0x180013aa0`
- `0x180014d60`
- `0x180014e40`
- `0x1800151b0`
- `0x180016590`
- `0x180016de0`
- `0x180016f00`
- `0x1800175bc`
- `0x180017cd0`
- `0x180017f40`
- `0x18001aee0`
- `0x18001b5d0`
- `0x18001bb90`
- `0x18001e150`
- `0x18001ea70`
- `0x18001eba0`
- `0x18001fd50`
- `0x180020604`
- `0x180020d84`

## callees

- `0x18001cf50`
- `0x18001d560`

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
0x18001cf50  cmp     rcx, cs:__security_cookie
0x18001cf57  jnz     short ReportFailure
0x18001cf59  rol     rcx, 10h
0x18001cf5d  test    cx, 0FFFFh
0x18001cf62  jnz     short RestoreRcx
0x18001cf64  retn
0x18001cf65  ror     rcx, 10h; StackCookie
0x18001cf69  jmp     __report_gsfailure
```
