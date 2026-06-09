# WPP_SF_S

- ea: `0x18000de30`
- end: `0x18000de8a`
- name: `WPP_SF_S`
- size: `90`
- prototype: `ULONG __fastcall(TRACEHANDLE, USHORT, const GUID *, const wchar_t *)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180005720`
- `0x180005e30`
- `0x180006700`
- `0x18000da00`
- `0x18000dc90`
- `0x18000e960`

## callees

- `0x18000de30`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18000de7f`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18000de7f`

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
0x18000de30  sub     rsp, 48h
0x18000de34  xor     r11d, r11d
0x18000de37  test    r9, r9
0x18000de3a  jz      short loc_18000DE54
0x18000de3c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000de40  inc     rax
0x18000de43  cmp     [r9+rax*2], r11w
0x18000de48  jnz     short loc_18000DE40
0x18000de4a  lea     rax, ds:2[rax*2]
0x18000de52  jmp     short loc_18000DE59
0x18000de54  mov     eax, 0Ah
0x18000de59  test    r9, r9
0x18000de5c  mov     [rsp+48h+var_18], r11
0x18000de61  lea     r10, aNull_0; "NULL"
0x18000de68  mov     [rsp+48h+var_20], rax
0x18000de6d  cmovz   r9, r10
0x18000de71  mov     [rsp+48h+var_28], r9
0x18000de76  movzx   r9d, dx; MessageNumber
0x18000de7a  mov     edx, 2Bh ; '+'; MessageFlags
0x18000de7f  call    cs:__imp_TraceMessage
0x18000de85  add     rsp, 48h
0x18000de89  retn
```
