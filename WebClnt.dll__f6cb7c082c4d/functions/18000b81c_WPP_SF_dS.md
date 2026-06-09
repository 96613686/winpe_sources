# WPP_SF_dS

- ea: `0x18000b81c`
- end: `0x18000b896`
- name: `WPP_SF_dS`
- size: `122`
- prototype: ``
- caller_count: `13`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180008f00`
- `0x1800091e0`
- `0x18001507c`
- `0x180016d24`
- `0x18001832c`
- `0x180019454`
- `0x18001bb00`
- `0x18001bbe0`
- `0x18001f190`
- `0x180024190`
- `0x180027f30`
- `0x18002b0f4`
- `0x18002b8f8`

## callees

- `0x18000b81c`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x18000b88b`
- `ntdll!EtwTraceMessage` at `0x18000b88b`

## pseudocode

```c
__int64 __fastcall WPP_SF_dS(__int64 a1, unsigned __int16 a2, __int64 a3, int a4, __int64 a5)
{
  __int64 v5; // rax
  int v7; // [rsp+78h] [rbp+20h] BYREF

  v7 = a4;
  if ( a5 )
  {
    v5 = -1;
    do
      ++v5;
    while ( *(_WORD *)(a5 + 2 * v5) );
  }
  return EtwTraceMessage(a1, 43, a3, a2, &v7);
}

```

## disassembly

```asm
0x18000b81c  mov     [rsp+arg_18], r9d
0x18000b821  sub     rsp, 58h
0x18000b825  mov     r9, [rsp+58h+arg_20]
0x18000b82d  xor     r11d, r11d
0x18000b830  test    r9, r9
0x18000b833  jz      short loc_18000B84D
0x18000b835  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b839  inc     rax
0x18000b83c  cmp     [r9+rax*2], r11w
0x18000b841  jnz     short loc_18000B839
0x18000b843  lea     rax, ds:2[rax*2]
0x18000b84b  jmp     short loc_18000B852
0x18000b84d  mov     eax, 0Ah
0x18000b852  mov     [rsp+58h+var_18], r11
0x18000b857  lea     r10, aNull_0; "NULL"
0x18000b85e  mov     [rsp+58h+var_20], rax
0x18000b863  test    r9, r9
0x18000b866  lea     rax, [rsp+58h+arg_18]
0x18000b86b  cmovz   r9, r10
0x18000b86f  mov     [rsp+58h+var_28], r9
0x18000b874  movzx   r9d, dx
0x18000b878  mov     edx, 2Bh ; '+'
0x18000b87d  mov     [rsp+58h+var_30], 4
0x18000b886  mov     [rsp+58h+var_38], rax
0x18000b88b  call    cs:__imp_EtwTraceMessage
0x18000b891  add     rsp, 58h
0x18000b895  retn
```
