# WPP_SF_Sd

- ea: `0x18000c17c`
- end: `0x18000c1f3`
- name: `WPP_SF_Sd`
- size: `119`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180008544`
- `0x180008d8c`
- `0x18000a200`
- `0x18000a4c4`

## callees

- `0x18000c17c`

## import_xrefs

- `ADVAPI32!TraceMessage` at `0x18000c1e8`
- `ADVAPI32!TraceMessage` at `0x18000c1e8`

## pseudocode

```c
ULONG WPP_SF_Sd(TRACEHANDLE a1, USHORT a2, __int64 a3, const wchar_t *a4, ...)
{
  __int64 v4; // rax
  __int64 v5; // rax
  va_list va; // [rsp+80h] [rbp+28h] BYREF

  va_start(va, a4);
  if ( a4 )
  {
    v4 = -1;
    do
      ++v4;
    while ( a4[v4] );
    v5 = 2 * v4 + 2;
  }
  else
  {
    v5 = 10;
  }
  if ( !a4 )
    a4 = L"NULL";
  return TraceMessage(a1, 0x2Bu, &WPP_896b2d51e548366088657dee2fc85ea9_Traceguids, a2, a4, v5, va, 4, 0);
}

```

## disassembly

```asm
0x18000c17c  sub     rsp, 58h
0x18000c180  xor     r10d, r10d
0x18000c183  test    r9, r9
0x18000c186  jz      short loc_18000C1A0
0x18000c188  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000c18c  inc     rax
0x18000c18f  cmp     [r9+rax*2], r10w
0x18000c194  jnz     short loc_18000C18C
0x18000c196  lea     rax, ds:2[rax*2]
0x18000c19e  jmp     short loc_18000C1A5
0x18000c1a0  mov     eax, 0Ah
0x18000c1a5  mov     [rsp+58h+var_18], r10
0x18000c1aa  lea     r8, aNull; "NULL"
0x18000c1b1  test    r9, r9
0x18000c1b4  mov     [rsp+58h+var_20], 4
0x18000c1bd  cmovz   r9, r8
0x18000c1c1  lea     r8, [rsp+58h+arg_20]
0x18000c1c9  mov     [rsp+58h+var_28], r8
0x18000c1ce  lea     r8, WPP_896b2d51e548366088657dee2fc85ea9_Traceguids; MessageGuid
0x18000c1d5  mov     [rsp+58h+var_30], rax
0x18000c1da  mov     [rsp+58h+var_38], r9
0x18000c1df  movzx   r9d, dx; MessageNumber
0x18000c1e3  mov     edx, 2Bh ; '+'; MessageFlags
0x18000c1e8  call    cs:__imp_TraceMessage
0x18000c1ee  add     rsp, 58h
0x18000c1f2  retn
```
