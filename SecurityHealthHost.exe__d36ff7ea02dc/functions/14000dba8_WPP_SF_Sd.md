# WPP_SF_Sd

- ea: `0x14000dba8`
- end: `0x14000dc18`
- name: `WPP_SF_Sd`
- size: `112`
- prototype: `ULONG(TRACEHANDLE, USHORT, const GUID *, const wchar_t *, ...)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14000d6f8`
- `0x14000d89c`
- `0x14000e35c`

## callees

- `0x14000dba8`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x14000dc0d`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x14000dc0d`

## pseudocode

```c
ULONG WPP_SF_Sd(TRACEHANDLE a1, USHORT a2, const GUID *a3, const wchar_t *a4, ...)
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
  return TraceMessage(a1, 0x2Bu, a3, a2, a4, v5, va, 4, 0);
}

```

## disassembly

```asm
0x14000dba8  sub     rsp, 58h
0x14000dbac  xor     r11d, r11d
0x14000dbaf  test    r9, r9
0x14000dbb2  jz      short loc_14000DBCC
0x14000dbb4  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000dbb8  inc     rax
0x14000dbbb  cmp     [r9+rax*2], r11w
0x14000dbc0  jnz     short loc_14000DBB8
0x14000dbc2  lea     rax, ds:2[rax*2]
0x14000dbca  jmp     short loc_14000DBD1
0x14000dbcc  mov     eax, 0Ah
0x14000dbd1  mov     [rsp+58h+var_18], r11
0x14000dbd6  lea     r10, aNull; "NULL"
0x14000dbdd  test    r9, r9
0x14000dbe0  mov     [rsp+58h+var_20], 4
0x14000dbe9  cmovz   r9, r10
0x14000dbed  lea     r10, [rsp+58h+arg_20]
0x14000dbf5  mov     [rsp+58h+var_28], r10
0x14000dbfa  mov     [rsp+58h+var_30], rax
0x14000dbff  mov     [rsp+58h+var_38], r9
0x14000dc04  movzx   r9d, dx; MessageNumber
0x14000dc08  mov     edx, 2Bh ; '+'; MessageFlags
0x14000dc0d  call    cs:__imp_TraceMessage
0x14000dc13  add     rsp, 58h
0x14000dc17  retn
```
