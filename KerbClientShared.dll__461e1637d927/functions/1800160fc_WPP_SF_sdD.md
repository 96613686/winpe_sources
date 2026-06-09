# WPP_SF_sdD

- ea: `0x1800160fc`
- end: `0x18001617b`
- name: `WPP_SF_sdD`
- size: `127`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1800016f0`
- `0x180001c10`
- `0x180008f50`
- `0x18000be90`
- `0x18000c8c0`
- `0x180015ce0`

## callees

- `0x1800160fc`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180016170`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180016170`

## pseudocode

```c
ULONG WPP_SF_sdD(TRACEHANDLE a1, USHORT a2, const GUID *a3, const char *a4, ...)
{
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 v7; // [rsp+90h] [rbp+28h] BYREF
  va_list va; // [rsp+90h] [rbp+28h]
  va_list va1; // [rsp+98h] [rbp+30h] BYREF

  va_start(va1, a4);
  va_start(va, a4);
  v7 = va_arg(va1, _QWORD);
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
  return TraceMessage(a1, 0x2Bu, a3, a2, a4, v5, va, 4, va1, 4, 0);
}

```

## disassembly

```asm
0x1800160fc  sub     rsp, 68h
0x180016100  test    r9, r9
0x180016103  jz      short loc_180016118
0x180016105  or      rax, 0FFFFFFFFFFFFFFFFh
0x180016109  inc     rax
0x18001610c  cmp     byte ptr [r9+rax], 0
0x180016111  jnz     short loc_180016109
0x180016113  inc     rax
0x180016116  jmp     short loc_18001611D
0x180016118  mov     eax, 5
0x18001611d  mov     [rsp+68h+var_18], 0
0x180016126  lea     r10, aNull; "NULL"
0x18001612d  mov     r11d, 4
0x180016133  test    r9, r9
0x180016136  mov     [rsp+68h+var_20], r11
0x18001613b  cmovz   r9, r10
0x18001613f  lea     r10, [rsp+68h+arg_28]
0x180016147  mov     [rsp+68h+var_28], r10
0x18001614c  lea     r10, [rsp+68h+arg_20]
0x180016154  mov     [rsp+68h+var_30], r11
0x180016159  mov     [rsp+68h+var_38], r10
0x18001615e  mov     [rsp+68h+var_40], rax
0x180016163  mov     [rsp+68h+var_48], r9
0x180016168  movzx   r9d, dx; MessageNumber
0x18001616c  lea     edx, [r11+27h]; MessageFlags
0x180016170  call    cs:__imp_TraceMessage
0x180016176  add     rsp, 68h
0x18001617a  retn
```
