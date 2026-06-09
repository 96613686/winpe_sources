# WPP_SF_Sd

- ea: `0x14000cca0`
- end: `0x14000cd10`
- name: `WPP_SF_Sd`
- size: `112`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x140009b84`
- `0x14000a0b0`
- `0x14000c0c0`
- `0x140011aa4`
- `0x1400128d4`

## callees

- `0x14000cca0`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x14000cd05`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x14000cd05`

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
0x14000cca0  sub     rsp, 58h
0x14000cca4  xor     r11d, r11d
0x14000cca7  test    r9, r9
0x14000ccaa  jz      short loc_14000CCC4
0x14000ccac  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000ccb0  inc     rax
0x14000ccb3  cmp     [r9+rax*2], r11w
0x14000ccb8  jnz     short loc_14000CCB0
0x14000ccba  lea     rax, ds:2[rax*2]
0x14000ccc2  jmp     short loc_14000CCC9
0x14000ccc4  mov     eax, 0Ah
0x14000ccc9  mov     [rsp+58h+var_18], r11
0x14000ccce  lea     r10, aNull_0; "NULL"
0x14000ccd5  test    r9, r9
0x14000ccd8  mov     [rsp+58h+var_20], 4
0x14000cce1  cmovz   r9, r10
0x14000cce5  lea     r10, [rsp+58h+arg_20]
0x14000cced  mov     [rsp+58h+var_28], r10
0x14000ccf2  mov     [rsp+58h+var_30], rax
0x14000ccf7  mov     [rsp+58h+var_38], r9
0x14000ccfc  movzx   r9d, dx; MessageNumber
0x14000cd00  mov     edx, 2Bh ; '+'; MessageFlags
0x14000cd05  call    cs:__imp_TraceMessage
0x14000cd0b  add     rsp, 58h
0x14000cd0f  retn
```
