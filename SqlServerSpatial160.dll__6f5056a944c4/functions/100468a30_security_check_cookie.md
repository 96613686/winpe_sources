# __security_check_cookie

- ea: `0x100468a30`
- end: `0x100468a4e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `162`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x100402320`
- `0x1004070c0`
- `0x100407c60`
- `0x100407e30`
- `0x10040de70`
- `0x10040e5c0`
- `0x10040ee80`
- `0x10040f200`
- `0x10040fad0`
- `0x1004102d0`
- `0x100410d70`
- `0x100411630`
- `0x100412450`
- `0x100412f30`
- `0x100412fc0`
- `0x1004130f0`
- `0x100413c80`
- `0x100413d10`
- `0x100413da0`
- `0x100413e50`
- `0x100414150`
- `0x1004145a0`
- `0x100414ae0`
- `0x100415260`
- `0x100415550`
- `0x100415d10`
- `0x1004162a0`
- `0x100416de0`
- `0x100417030`
- `0x100417640`
- `0x100417750`
- `0x100418280`
- `0x100418d90`
- `0x1004190d0`
- `0x100419a00`
- `0x100419bd0`
- `0x100419ef0`
- `0x10041a1c0`
- `0x10041a410`
- `0x10041a490`
- `0x10041a990`
- `0x10041aca0`
- `0x10041b930`
- `0x10041bd30`
- `0x10041c700`
- `0x10041d5a0`
- `0x10041d6b0`
- `0x10041d8c0`
- `0x10041e7e0`
- `0x10041e970`

## callees

- `0x100468a30`
- `0x100469380`

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
0x100468a30  cmp     rcx, cs:__security_cookie
0x100468a37  jnz     short ReportFailure
0x100468a39  rol     rcx, 10h
0x100468a3d  test    cx, 0FFFFh
0x100468a42  jnz     short RestoreRcx
0x100468a44  retn
0x100468a45  ror     rcx, 10h
0x100468a49  jmp     __report_gsfailure
```
