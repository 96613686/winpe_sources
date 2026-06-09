# WPP_SF_S

- ea: `0x14000cfa0`
- end: `0x14000cffa`
- name: `WPP_SF_S`
- size: `90`
- prototype: `ULONG __fastcall(TRACEHANDLE, USHORT, const GUID *, const wchar_t *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14000d9e8`
- `0x14000e948`
- `0x14000ea64`

## callees

- `0x14000cfa0`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x14000cfef`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x14000cfef`

## pseudocode

```c
ULONG __fastcall WPP_SF_S(TRACEHANDLE a1, USHORT a2, const GUID *a3, const wchar_t *a4)
{
  __int64 v4; // rax
  __int64 v5; // rax

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
  return TraceMessage(a1, 0x2Bu, a3, a2, a4, v5, 0);
}

```

## disassembly

```asm
0x14000cfa0  sub     rsp, 48h
0x14000cfa4  xor     r11d, r11d
0x14000cfa7  test    r9, r9
0x14000cfaa  jz      short loc_14000CFC4
0x14000cfac  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000cfb0  inc     rax
0x14000cfb3  cmp     [r9+rax*2], r11w
0x14000cfb8  jnz     short loc_14000CFB0
0x14000cfba  lea     rax, ds:2[rax*2]
0x14000cfc2  jmp     short loc_14000CFC9
0x14000cfc4  mov     eax, 0Ah
0x14000cfc9  test    r9, r9
0x14000cfcc  mov     [rsp+48h+var_18], r11
0x14000cfd1  lea     r10, aNull; "NULL"
0x14000cfd8  mov     [rsp+48h+var_20], rax
0x14000cfdd  cmovz   r9, r10
0x14000cfe1  mov     [rsp+48h+var_28], r9
0x14000cfe6  movzx   r9d, dx; MessageNumber
0x14000cfea  mov     edx, 2Bh ; '+'; MessageFlags
0x14000cfef  call    cs:__imp_TraceMessage
0x14000cff5  add     rsp, 48h
0x14000cff9  retn
```
