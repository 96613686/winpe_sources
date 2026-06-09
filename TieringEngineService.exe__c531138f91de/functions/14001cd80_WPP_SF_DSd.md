# WPP_SF_DSd

- ea: `0x14001cd80`
- end: `0x14001ce10`
- name: `WPP_SF_DSd`
- size: `144`
- prototype: ``
- caller_count: `20`
- callee_count: `1`
- tags: ``

## callers

- `0x140019df8`
- `0x14001a050`
- `0x14001a270`
- `0x14001b328`
- `0x14001fca0`
- `0x140020390`
- `0x1400211a4`
- `0x140021a28`
- `0x140022878`
- `0x140029268`
- `0x140029b44`
- `0x14002fd94`
- `0x140031e04`
- `0x140038490`
- `0x140038a50`
- `0x140039090`
- `0x140039340`
- `0x140039de0`
- `0x14003ad70`
- `0x14003af90`

## callees

- `0x14001cd80`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x14001ce05`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x14001ce05`

## pseudocode

```c
ULONG WPP_SF_DSd(TRACEHANDLE a1, USHORT a2, const GUID *a3, int a4, const wchar_t *a5, ...)
{
  const wchar_t *v5; // r9
  __int64 v6; // rax
  __int64 v7; // rax
  int v9; // [rsp+88h] [rbp+20h] BYREF
  va_list va; // [rsp+98h] [rbp+30h] BYREF

  va_start(va, a5);
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
  return TraceMessage(a1, 0x2Bu, a3, a2, &v9, 4, v5, v7, va, 4, 0);
}

```

## disassembly

```asm
0x14001cd80  mov     [rsp+arg_18], r9d
0x14001cd85  sub     rsp, 68h
0x14001cd89  mov     r9, [rsp+68h+arg_20]
0x14001cd91  xor     r11d, r11d
0x14001cd94  test    r9, r9
0x14001cd97  jz      short loc_14001CDB1
0x14001cd99  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001cd9d  inc     rax
0x14001cda0  cmp     [r9+rax*2], r11w
0x14001cda5  jnz     short loc_14001CD9D
0x14001cda7  lea     rax, ds:2[rax*2]
0x14001cdaf  jmp     short loc_14001CDB6
0x14001cdb1  mov     eax, 0Ah
0x14001cdb6  mov     [rsp+68h+var_18], r11
0x14001cdbb  lea     r10, aNull_1; "NULL"
0x14001cdc2  mov     r11d, 4
0x14001cdc8  test    r9, r9
0x14001cdcb  mov     [rsp+68h+var_20], r11
0x14001cdd0  cmovz   r9, r10
0x14001cdd4  lea     r10, [rsp+68h+arg_28]
0x14001cddc  mov     [rsp+68h+var_28], r10
0x14001cde1  mov     [rsp+68h+var_30], rax
0x14001cde6  lea     rax, [rsp+68h+arg_18]
0x14001cdee  mov     [rsp+68h+var_38], r9
0x14001cdf3  movzx   r9d, dx; MessageNumber
0x14001cdf7  lea     edx, [r11+27h]; MessageFlags
0x14001cdfb  mov     [rsp+68h+var_40], r11
0x14001ce00  mov     [rsp+68h+var_48], rax
0x14001ce05  call    cs:__imp_TraceMessage
0x14001ce0b  add     rsp, 68h
0x14001ce0f  retn
```
