# WPP_SF_SS

- ea: `0x14000cbf4`
- end: `0x14000cc99`
- name: `WPP_SF_SS`
- size: `165`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x1400096cc`
- `0x1400097b0`
- `0x140009988`
- `0x140009b84`
- `0x14000ad80`
- `0x14000b840`
- `0x1400128d4`

## callees

- `0x14000cbf4`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x14000cc83`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x14000cc83`

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
0x14000cbf4  mov     [rsp+arg_0], rbx
0x14000cbf9  mov     [rsp+arg_8], rsi
0x14000cbfe  push    rdi
0x14000cbff  sub     rsp, 50h
0x14000cc03  mov     r11, [rsp+58h+arg_20]
0x14000cc0b  or      r10, 0FFFFFFFFFFFFFFFFh
0x14000cc0f  xor     edi, edi
0x14000cc11  mov     ebx, 0Ah
0x14000cc16  test    r11, r11
0x14000cc19  jz      short loc_14000CC32
0x14000cc1b  mov     rax, r10
0x14000cc1e  inc     rax
0x14000cc21  cmp     [r11+rax*2], di
0x14000cc26  jnz     short loc_14000CC1E
0x14000cc28  lea     rax, ds:2[rax*2]
0x14000cc30  jmp     short loc_14000CC35
0x14000cc32  mov     rax, rbx
0x14000cc35  test    r11, r11
0x14000cc38  lea     rsi, aNull_0; "NULL"
0x14000cc3f  cmovz   r11, rsi
0x14000cc43  test    r9, r9
0x14000cc46  jz      short loc_14000CC5D
0x14000cc48  inc     r10
0x14000cc4b  cmp     [r9+r10*2], di
0x14000cc50  jnz     short loc_14000CC48
0x14000cc52  lea     rbx, ds:2[r10*2]
0x14000cc5a  test    r9, r9
0x14000cc5d  mov     [rsp+58h+var_18], rdi
0x14000cc62  cmovz   r9, rsi
0x14000cc66  mov     [rsp+58h+var_20], rax
0x14000cc6b  mov     [rsp+58h+var_28], r11
0x14000cc70  mov     [rsp+58h+var_30], rbx
0x14000cc75  mov     [rsp+58h+var_38], r9
0x14000cc7a  movzx   r9d, dx; MessageNumber
0x14000cc7e  mov     edx, 2Bh ; '+'; MessageFlags
0x14000cc83  call    cs:__imp_TraceMessage
0x14000cc89  mov     rbx, [rsp+58h+arg_0]
0x14000cc8e  mov     rsi, [rsp+58h+arg_8]
0x14000cc93  add     rsp, 50h
0x14000cc97  pop     rdi
0x14000cc98  retn
```
