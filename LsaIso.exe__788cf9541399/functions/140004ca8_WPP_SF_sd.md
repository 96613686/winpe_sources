# WPP_SF_sd

- ea: `0x140004ca8`
- end: `0x140004d14`
- name: `WPP_SF_sd`
- size: `108`
- prototype: ``
- caller_count: `55`
- callee_count: `1`
- tags: ``

## callers

- `0x140003e58`
- `0x14000413c`
- `0x1400041d0`
- `0x1400044d0`
- `0x140004810`
- `0x140004b70`
- `0x140004da8`
- `0x140004ff8`
- `0x140005280`
- `0x140005820`
- `0x140005df0`
- `0x140006140`
- `0x1400100d0`
- `0x1400145ac`
- `0x14001489c`
- `0x140014a88`
- `0x140014f5c`
- `0x1400150f4`
- `0x140015210`
- `0x140015410`
- `0x140015590`
- `0x140015740`
- `0x1400158c0`
- `0x140015b90`
- `0x140015ed0`
- `0x140016140`
- `0x140016310`
- `0x1400164a0`
- `0x140016860`
- `0x140016ac0`
- `0x140016e90`
- `0x140016fd0`
- `0x140017450`
- `0x1400175c0`
- `0x140017840`
- `0x140017a40`
- `0x140017be0`
- `0x140017e00`
- `0x1400180d0`
- `0x140018340`
- `0x140018540`
- `0x1400186e0`
- `0x140018880`
- `0x140018ff0`
- `0x140019210`
- `0x1400197a0`
- `0x140019890`
- `0x140019a00`
- `0x140019b50`
- `0x140019dd0`

## callees

- `0x140004ca8`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x140004d09`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x140004d09`

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
0x140004ca8  sub     rsp, 58h
0x140004cac  test    r9, r9
0x140004caf  jz      short loc_140004CC4
0x140004cb1  or      rax, 0FFFFFFFFFFFFFFFFh
0x140004cb5  inc     rax
0x140004cb8  cmp     byte ptr [r9+rax], 0
0x140004cbd  jnz     short loc_140004CB5
0x140004cbf  inc     rax
0x140004cc2  jmp     short loc_140004CC9
0x140004cc4  mov     eax, 5
0x140004cc9  mov     [rsp+58h+var_18], 0
0x140004cd2  lea     r10, aNull; "NULL"
0x140004cd9  test    r9, r9
0x140004cdc  mov     [rsp+58h+var_20], 4
0x140004ce5  cmovz   r9, r10
0x140004ce9  lea     r10, [rsp+58h+arg_20]
0x140004cf1  mov     [rsp+58h+var_28], r10
0x140004cf6  mov     [rsp+58h+var_30], rax
0x140004cfb  mov     [rsp+58h+var_38], r9
0x140004d00  movzx   r9d, dx; MessageNumber
0x140004d04  mov     edx, 2Bh ; '+'; MessageFlags
0x140004d09  call    cs:__imp_TraceMessage
0x140004d0f  add     rsp, 58h
0x140004d13  retn
```
