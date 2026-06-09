# WPP_SF_SS

- ea: `0x18000efc0`
- end: `0x18000f065`
- name: `WPP_SF_SS`
- size: `165`
- prototype: `ULONG __fastcall(TRACEHANDLE, USHORT, const GUID *, const wchar_t *, const wchar_t *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180005c20`
- `0x180006340`
- `0x18000eda0`

## callees

- `0x18000efc0`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18000f04f`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18000f04f`

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
0x18000efc0  mov     [rsp+arg_0], rbx
0x18000efc5  mov     [rsp+arg_8], rsi
0x18000efca  push    rdi
0x18000efcb  sub     rsp, 50h
0x18000efcf  mov     r11, [rsp+58h+arg_20]
0x18000efd7  or      r10, 0FFFFFFFFFFFFFFFFh
0x18000efdb  xor     edi, edi
0x18000efdd  mov     ebx, 0Ah
0x18000efe2  test    r11, r11
0x18000efe5  jz      short loc_18000EFFE
0x18000efe7  mov     rax, r10
0x18000efea  inc     rax
0x18000efed  cmp     [r11+rax*2], di
0x18000eff2  jnz     short loc_18000EFEA
0x18000eff4  lea     rax, ds:2[rax*2]
0x18000effc  jmp     short loc_18000F001
0x18000effe  mov     rax, rbx
0x18000f001  test    r11, r11
0x18000f004  lea     rsi, aNull_0; "NULL"
0x18000f00b  cmovz   r11, rsi
0x18000f00f  test    r9, r9
0x18000f012  jz      short loc_18000F029
0x18000f014  inc     r10
0x18000f017  cmp     [r9+r10*2], di
0x18000f01c  jnz     short loc_18000F014
0x18000f01e  lea     rbx, ds:2[r10*2]
0x18000f026  test    r9, r9
0x18000f029  mov     [rsp+58h+var_18], rdi
0x18000f02e  cmovz   r9, rsi
0x18000f032  mov     [rsp+58h+var_20], rax
0x18000f037  mov     [rsp+58h+var_28], r11
0x18000f03c  mov     [rsp+58h+var_30], rbx
0x18000f041  mov     [rsp+58h+var_38], r9
0x18000f046  movzx   r9d, dx; MessageNumber
0x18000f04a  mov     edx, 2Bh ; '+'; MessageFlags
0x18000f04f  call    cs:__imp_TraceMessage
0x18000f055  mov     rbx, [rsp+58h+arg_0]
0x18000f05a  mov     rsi, [rsp+58h+arg_8]
0x18000f05f  add     rsp, 50h
0x18000f063  pop     rdi
0x18000f064  retn
```
