# WPP_SF_ssS

- ea: `0x18002503c`
- end: `0x1800250f2`
- name: `WPP_SF_ssS`
- size: `182`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001fea0`

## callees

- `0x18002503c`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x1800250e7`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x1800250e7`

## string_xrefs

- `0x1800250ca`: `VGidsSimulatorReadProperties`

## pseudocode

```c
ULONG __fastcall WPP_SF_ssS(TRACEHANDLE a1, __int64 a2, __int64 a3, const char *a4, int a5, const wchar_t *a6)
{
  const wchar_t *v6; // rdx
  __int64 v7; // rax
  __int64 v8; // r8
  __int64 v9; // r8
  __int64 v10; // rax

  v6 = a6;
  v7 = -1;
  if ( a6 )
  {
    v8 = -1;
    do
      ++v8;
    while ( a6[v8] );
    v9 = 2 * v8 + 2;
  }
  else
  {
    v9 = 10;
  }
  if ( !a6 )
    v6 = L"NULL";
  if ( a4 )
  {
    do
      ++v7;
    while ( a4[v7] );
    v10 = v7 + 1;
  }
  else
  {
    v10 = 5;
  }
  if ( !a4 )
    a4 = "NULL";
  return TraceMessage(
           a1,
           0x2Bu,
           &WPP_a84eb28aad63382c633638e94ebf5e29_Traceguids,
           0x25u,
           a4,
           v10,
           "VGidsSimulatorReadProperties",
           29,
           v6,
           v9,
           0);
}

```

## disassembly

```asm
0x18002503c  sub     rsp, 68h
0x180025040  mov     rdx, [rsp+68h+arg_28]
0x180025048  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002504c  xor     r11d, r11d
0x18002504f  test    rdx, rdx
0x180025052  jz      short loc_18002506B
0x180025054  mov     r8, rax
0x180025057  inc     r8
0x18002505a  cmp     [rdx+r8*2], r11w
0x18002505f  jnz     short loc_180025057
0x180025061  lea     r8, ds:2[r8*2]
0x180025069  jmp     short loc_180025071
0x18002506b  mov     r8d, 0Ah
0x180025071  test    rdx, rdx
0x180025074  lea     r10, aNull_0; "NULL"
0x18002507b  cmovz   rdx, r10
0x18002507f  test    r9, r9
0x180025082  jz      short loc_180025092
0x180025084  inc     rax
0x180025087  cmp     [r9+rax], r11b
0x18002508b  jnz     short loc_180025084
0x18002508d  inc     rax
0x180025090  jmp     short loc_180025097
0x180025092  mov     eax, 5
0x180025097  mov     [rsp+68h+var_18], r11
0x18002509c  lea     r10, aNull; "NULL"
0x1800250a3  mov     [rsp+68h+var_20], r8
0x1800250a8  test    r9, r9
0x1800250ab  mov     [rsp+68h+var_28], rdx
0x1800250b0  lea     r8, WPP_a84eb28aad63382c633638e94ebf5e29_Traceguids; MessageGuid
0x1800250b7  cmovz   r9, r10
0x1800250bb  mov     [rsp+68h+var_30], 1Dh
0x1800250c4  mov     r10d, 25h ; '%'
0x1800250ca  lea     rdx, aVgidssimulator_5; "VGidsSimulatorReadProperties"
0x1800250d1  mov     [rsp+68h+var_38], rdx
0x1800250d6  mov     [rsp+68h+var_40], rax
0x1800250db  mov     [rsp+68h+var_48], r9
0x1800250e0  mov     r9d, r10d; MessageNumber
0x1800250e3  lea     edx, [r10+6]; MessageFlags
0x1800250e7  call    cs:__imp_TraceMessage
0x1800250ed  add     rsp, 68h
0x1800250f1  retn
```
