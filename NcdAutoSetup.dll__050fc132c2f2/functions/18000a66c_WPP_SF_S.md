# WPP_SF_S

- ea: `0x18000a66c`
- end: `0x18000a6c6`
- name: `WPP_SF_S`
- size: `90`
- prototype: `ULONG __fastcall(TRACEHANDLE, USHORT, const GUID *, const wchar_t *)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x180008ea8`
- `0x1800094c8`
- `0x18000b310`
- `0x18000eadc`
- `0x18000f190`
- `0x18000f49c`
- `0x18000f968`
- `0x18000fe40`
- `0x180010120`
- `0x180010a80`
- `0x1800113bc`
- `0x180012110`

## callees

- `0x18000a66c`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18000a6bb`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18000a6bb`

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
0x18000a66c  sub     rsp, 48h
0x18000a670  xor     r11d, r11d
0x18000a673  test    r9, r9
0x18000a676  jz      short loc_18000A690
0x18000a678  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000a67c  inc     rax
0x18000a67f  cmp     [r9+rax*2], r11w
0x18000a684  jnz     short loc_18000A67C
0x18000a686  lea     rax, ds:2[rax*2]
0x18000a68e  jmp     short loc_18000A695
0x18000a690  mov     eax, 0Ah
0x18000a695  test    r9, r9
0x18000a698  mov     [rsp+48h+var_18], r11
0x18000a69d  lea     r10, aNull_1; "NULL"
0x18000a6a4  mov     [rsp+48h+var_20], rax
0x18000a6a9  cmovz   r9, r10
0x18000a6ad  mov     [rsp+48h+var_28], r9
0x18000a6b2  movzx   r9d, dx; MessageNumber
0x18000a6b6  mov     edx, 2Bh ; '+'; MessageFlags
0x18000a6bb  call    cs:__imp_TraceMessage
0x18000a6c1  add     rsp, 48h
0x18000a6c5  retn
```
