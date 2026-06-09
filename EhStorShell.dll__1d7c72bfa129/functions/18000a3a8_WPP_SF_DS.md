# WPP_SF_DS

- ea: `0x18000a3a8`
- end: `0x18000a422`
- name: `WPP_SF_DS`
- size: `122`
- prototype: `ULONG __fastcall(TRACEHANDLE, USHORT, const GUID *, int, const wchar_t *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180003a98`
- `0x18000ac54`

## callees

- `0x18000a3a8`

## import_xrefs

- `ADVAPI32!TraceMessage` at `0x18000a417`
- `ADVAPI32!TraceMessage` at `0x18000a417`

## pseudocode

```c
ULONG __fastcall WPP_SF_DS(TRACEHANDLE a1, USHORT a2, const GUID *a3, int a4, const wchar_t *a5)
{
  const wchar_t *v5; // r9
  __int64 v6; // rax
  __int64 v7; // rax
  int v9; // [rsp+78h] [rbp+20h] BYREF

  v9 = a4;
  v5 = a5;
  if ( a5 )
  {
    v6 = -1;
    do
      ++v6;
    while ( a5[v6] );
    v7 = 2 * v6 + 2;
  }
  else
  {
    v7 = 10;
  }
  if ( !a5 )
    v5 = L"NULL";
  return TraceMessage(a1, 0x2Bu, a3, a2, &v9, 4, v5, v7, 0);
}

```

## disassembly

```asm
0x18000a3a8  mov     [rsp+arg_18], r9d
0x18000a3ad  sub     rsp, 58h
0x18000a3b1  mov     r9, [rsp+58h+arg_20]
0x18000a3b9  xor     r11d, r11d
0x18000a3bc  test    r9, r9
0x18000a3bf  jz      short loc_18000A3D9
0x18000a3c1  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000a3c5  inc     rax
0x18000a3c8  cmp     [r9+rax*2], r11w
0x18000a3cd  jnz     short loc_18000A3C5
0x18000a3cf  lea     rax, ds:2[rax*2]
0x18000a3d7  jmp     short loc_18000A3DE
0x18000a3d9  mov     eax, 0Ah
0x18000a3de  mov     [rsp+58h+var_18], r11
0x18000a3e3  lea     r10, aNull; "NULL"
0x18000a3ea  mov     [rsp+58h+var_20], rax
0x18000a3ef  test    r9, r9
0x18000a3f2  lea     rax, [rsp+58h+arg_18]
0x18000a3f7  cmovz   r9, r10
0x18000a3fb  mov     [rsp+58h+var_28], r9
0x18000a400  movzx   r9d, dx; MessageNumber
0x18000a404  mov     edx, 2Bh ; '+'; MessageFlags
0x18000a409  mov     [rsp+58h+var_30], 4
0x18000a412  mov     [rsp+58h+var_38], rax
0x18000a417  call    cs:__imp_TraceMessage
0x18000a41d  add     rsp, 58h
0x18000a421  retn
```
