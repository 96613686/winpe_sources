# WPP_SF_SS

- ea: `0x18000a6cc`
- end: `0x18000a771`
- name: `WPP_SF_SS`
- size: `165`
- prototype: `ULONG __fastcall(TRACEHANDLE, USHORT, const GUID *, const wchar_t *, const wchar_t *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180008ea8`
- `0x18000f968`
- `0x1800113bc`

## callees

- `0x18000a6cc`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18000a75b`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18000a75b`

## pseudocode

```c
ULONG __fastcall WPP_SF_SS(TRACEHANDLE a1, USHORT a2, const GUID *a3, const wchar_t *a4, const wchar_t *a5)
{
  const wchar_t *v5; // r11
  __int64 v6; // r10
  __int64 v7; // rbx
  __int64 v8; // rax
  __int64 v9; // rax
  bool v10; // zf

  v5 = a5;
  v6 = -1;
  v7 = 10;
  if ( a5 )
  {
    v8 = -1;
    do
      ++v8;
    while ( a5[v8] );
    v9 = 2 * v8 + 2;
  }
  else
  {
    v9 = 10;
  }
  if ( !a5 )
    v5 = L"NULL";
  v10 = a4 == 0;
  if ( a4 )
  {
    do
      ++v6;
    while ( a4[v6] );
    v7 = 2 * v6 + 2;
    v10 = a4 == 0;
  }
  if ( v10 )
    a4 = L"NULL";
  return TraceMessage(a1, 0x2Bu, a3, a2, a4, v7, v5, v9, 0);
}

```

## disassembly

```asm
0x18000a6cc  mov     [rsp+arg_0], rbx
0x18000a6d1  mov     [rsp+arg_8], rsi
0x18000a6d6  push    rdi
0x18000a6d7  sub     rsp, 50h
0x18000a6db  mov     r11, [rsp+58h+arg_20]
0x18000a6e3  or      r10, 0FFFFFFFFFFFFFFFFh
0x18000a6e7  xor     edi, edi
0x18000a6e9  mov     ebx, 0Ah
0x18000a6ee  test    r11, r11
0x18000a6f1  jz      short loc_18000A70A
0x18000a6f3  mov     rax, r10
0x18000a6f6  inc     rax
0x18000a6f9  cmp     [r11+rax*2], di
0x18000a6fe  jnz     short loc_18000A6F6
0x18000a700  lea     rax, ds:2[rax*2]
0x18000a708  jmp     short loc_18000A70D
0x18000a70a  mov     rax, rbx
0x18000a70d  test    r11, r11
0x18000a710  lea     rsi, aNull_1; "NULL"
0x18000a717  cmovz   r11, rsi
0x18000a71b  test    r9, r9
0x18000a71e  jz      short loc_18000A735
0x18000a720  inc     r10
0x18000a723  cmp     [r9+r10*2], di
0x18000a728  jnz     short loc_18000A720
0x18000a72a  lea     rbx, ds:2[r10*2]
0x18000a732  test    r9, r9
0x18000a735  mov     [rsp+58h+var_18], rdi
0x18000a73a  cmovz   r9, rsi
0x18000a73e  mov     [rsp+58h+var_20], rax
0x18000a743  mov     [rsp+58h+var_28], r11
0x18000a748  mov     [rsp+58h+var_30], rbx
0x18000a74d  mov     [rsp+58h+var_38], r9
0x18000a752  movzx   r9d, dx; MessageNumber
0x18000a756  mov     edx, 2Bh ; '+'; MessageFlags
0x18000a75b  call    cs:__imp_TraceMessage
0x18000a761  mov     rbx, [rsp+58h+arg_0]
0x18000a766  mov     rsi, [rsp+58h+arg_8]
0x18000a76b  add     rsp, 50h
0x18000a76f  pop     rdi
0x18000a770  retn
```
