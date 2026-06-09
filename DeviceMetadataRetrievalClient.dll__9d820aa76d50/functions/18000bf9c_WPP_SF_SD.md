# WPP_SF_SD

- ea: `0x18000bf9c`
- end: `0x18000c00c`
- name: `WPP_SF_SD`
- size: `112`
- prototype: ``
- caller_count: `13`
- callee_count: `1`
- tags: ``

## callers

- `0x180005a38`
- `0x180006714`
- `0x180006904`
- `0x180008544`
- `0x18000a4c4`
- `0x18000b7a0`
- `0x18000cc50`
- `0x18000d060`
- `0x18000d728`
- `0x18000dabc`
- `0x18000ef74`
- `0x18001031c`
- `0x180010eac`

## callees

- `0x18000bf9c`

## import_xrefs

- `ADVAPI32!TraceMessage` at `0x18000c001`
- `ADVAPI32!TraceMessage` at `0x18000c001`

## pseudocode

```c
ULONG WPP_SF_SD(TRACEHANDLE a1, USHORT a2, const GUID *a3, const wchar_t *a4, ...)
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
0x18000bf9c  sub     rsp, 58h
0x18000bfa0  xor     r11d, r11d
0x18000bfa3  test    r9, r9
0x18000bfa6  jz      short loc_18000BFC0
0x18000bfa8  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000bfac  inc     rax
0x18000bfaf  cmp     [r9+rax*2], r11w
0x18000bfb4  jnz     short loc_18000BFAC
0x18000bfb6  lea     rax, ds:2[rax*2]
0x18000bfbe  jmp     short loc_18000BFC5
0x18000bfc0  mov     eax, 0Ah
0x18000bfc5  mov     [rsp+58h+var_18], r11
0x18000bfca  lea     r10, aNull; "NULL"
0x18000bfd1  test    r9, r9
0x18000bfd4  mov     [rsp+58h+var_20], 4
0x18000bfdd  cmovz   r9, r10
0x18000bfe1  lea     r10, [rsp+58h+arg_20]
0x18000bfe9  mov     [rsp+58h+var_28], r10
0x18000bfee  mov     [rsp+58h+var_30], rax
0x18000bff3  mov     [rsp+58h+var_38], r9
0x18000bff8  movzx   r9d, dx; MessageNumber
0x18000bffc  mov     edx, 2Bh ; '+'; MessageFlags
0x18000c001  call    cs:__imp_TraceMessage
0x18000c007  add     rsp, 58h
0x18000c00b  retn
```
