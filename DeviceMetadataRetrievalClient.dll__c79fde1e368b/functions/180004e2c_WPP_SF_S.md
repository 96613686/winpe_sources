# WPP_SF_S

- ea: `0x180004e2c`
- end: `0x180004e86`
- name: `WPP_SF_S`
- size: `90`
- prototype: `ULONG __fastcall(TRACEHANDLE, USHORT, const GUID *, const wchar_t *)`
- caller_count: `21`
- callee_count: `1`
- tags: ``

## callers

- `0x180004b04`
- `0x180005198`
- `0x180005a38`
- `0x180006714`
- `0x180006904`
- `0x180007380`
- `0x18000768c`
- `0x18000838c`
- `0x180008544`
- `0x18000913c`
- `0x18000a4c4`
- `0x18000b7a0`
- `0x18000cc50`
- `0x18000d060`
- `0x18000d3e0`
- `0x18000d728`
- `0x18000dabc`
- `0x18000ea18`
- `0x180011df0`
- `0x180011fb0`
- `0x180012650`

## callees

- `0x180004e2c`

## import_xrefs

- `ADVAPI32!TraceMessage` at `0x180004e7b`
- `ADVAPI32!TraceMessage` at `0x180004e7b`

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
0x180004e2c  sub     rsp, 48h
0x180004e30  xor     r11d, r11d
0x180004e33  test    r9, r9
0x180004e36  jz      short loc_180004E50
0x180004e38  or      rax, 0FFFFFFFFFFFFFFFFh
0x180004e3c  inc     rax
0x180004e3f  cmp     [r9+rax*2], r11w
0x180004e44  jnz     short loc_180004E3C
0x180004e46  lea     rax, ds:2[rax*2]
0x180004e4e  jmp     short loc_180004E55
0x180004e50  mov     eax, 0Ah
0x180004e55  test    r9, r9
0x180004e58  mov     [rsp+48h+var_18], r11
0x180004e5d  lea     r10, aNull; "NULL"
0x180004e64  mov     [rsp+48h+var_20], rax
0x180004e69  cmovz   r9, r10
0x180004e6d  mov     [rsp+48h+var_28], r9
0x180004e72  movzx   r9d, dx; MessageNumber
0x180004e76  mov     edx, 2Bh ; '+'; MessageFlags
0x180004e7b  call    cs:__imp_TraceMessage
0x180004e81  add     rsp, 48h
0x180004e85  retn
```
