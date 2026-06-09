# __security_check_cookie

- ea: `0x18000a5f0`
- end: `0x18000a60e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `42`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001130`
- `0x180001490`
- `0x1800015d0`
- `0x180001a30`
- `0x180001af0`
- `0x180001d20`
- `0x180001e70`
- `0x180002820`
- `0x180002e00`
- `0x180002e90`
- `0x180003980`
- `0x180003bc0`
- `0x180004c00`
- `0x180004f80`
- `0x180005050`
- `0x180005130`
- `0x180005290`
- `0x180005320`
- `0x180005420`
- `0x1800055b0`
- `0x180005810`
- `0x180005ab0`
- `0x180005c70`
- `0x180005fe0`
- `0x180006080`
- `0x180006150`
- `0x180006230`
- `0x180006310`
- `0x1800064c0`
- `0x1800065d0`
- `0x1800068e0`
- `0x1800069c0`
- `0x180006aa0`
- `0x180006bd0`
- `0x180006dc0`
- `0x1800072e0`
- `0x1800076e0`
- `0x1800080e4`
- `0x180008390`
- `0x180008480`
- `0x180009280`
- `0x18000a4f8`

## callees

- `0x180004850`
- `0x18000a5f0`

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
0x18000a5f0  cmp     rcx, cs:__security_cookie
0x18000a5f7  jnz     short ReportFailure
0x18000a5f9  rol     rcx, 10h
0x18000a5fd  test    cx, 0FFFFh
0x18000a602  jnz     short RestoreRcx
0x18000a604  retn
0x18000a605  ror     rcx, 10h
0x18000a609  jmp     __report_gsfailure
```
