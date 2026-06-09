# WPP_SF_sd

- ea: `0x180015c6c`
- end: `0x180015cd8`
- name: `WPP_SF_sd`
- size: `108`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x180008f50`
- `0x180009fa0`
- `0x18000a3d0`
- `0x18000a650`
- `0x18000b5b0`
- `0x18000cf30`
- `0x180014dd0`
- `0x180016190`
- `0x180016680`

## callees

- `0x180015c6c`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180015ccd`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180015ccd`

## pseudocode

```c
ULONG WPP_SF_sd(TRACEHANDLE a1, USHORT a2, const GUID *a3, const char *a4, ...)
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
    v5 = v4 + 1;
  }
  else
  {
    v5 = 5;
  }
  if ( !a4 )
    a4 = "NULL";
  return TraceMessage(a1, 0x2Bu, a3, a2, a4, v5, va, 4, 0);
}

```

## disassembly

```asm
0x180015c6c  sub     rsp, 58h
0x180015c70  test    r9, r9
0x180015c73  jz      short loc_180015C88
0x180015c75  or      rax, 0FFFFFFFFFFFFFFFFh
0x180015c79  inc     rax
0x180015c7c  cmp     byte ptr [r9+rax], 0
0x180015c81  jnz     short loc_180015C79
0x180015c83  inc     rax
0x180015c86  jmp     short loc_180015C8D
0x180015c88  mov     eax, 5
0x180015c8d  mov     [rsp+58h+var_18], 0
0x180015c96  lea     r10, aNull; "NULL"
0x180015c9d  test    r9, r9
0x180015ca0  mov     [rsp+58h+var_20], 4
0x180015ca9  cmovz   r9, r10
0x180015cad  lea     r10, [rsp+58h+arg_20]
0x180015cb5  mov     [rsp+58h+var_28], r10
0x180015cba  mov     [rsp+58h+var_30], rax
0x180015cbf  mov     [rsp+58h+var_38], r9
0x180015cc4  movzx   r9d, dx; MessageNumber
0x180015cc8  mov     edx, 2Bh ; '+'; MessageFlags
0x180015ccd  call    cs:__imp_TraceMessage
0x180015cd3  add     rsp, 58h
0x180015cd7  retn
```
