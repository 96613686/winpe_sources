# WPP_SF_S_guid_

- ea: `0x18000cba0`
- end: `0x18000cc1d`
- name: `WPP_SF_S_guid_`
- size: `125`
- prototype: `__int64 __fastcall(__int64, unsigned __int16, __int64, const wchar_t *)`
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000bd18`
- `0x18000be20`
- `0x18000c960`
- `0x18000ca10`

## callees

- `0x18000cba0`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x18000cc12`
- `ntdll!EtwTraceMessage` at `0x18000cc12`

## pseudocode

```c
__int64 __fastcall WPP_SF_S_guid_(__int64 a1, unsigned __int16 a2, __int64 a3, const wchar_t *a4)
{
  __int64 v4; // rax

  if ( a4 )
  {
    v4 = -1;
    do
      ++v4;
    while ( a4[v4] );
  }
  if ( !a4 )
    a4 = L"NULL";
  return EtwTraceMessage(a1, 43, WPP_8228437e81df3f2b17e42002fd9073a5_Traceguids, a2, a4);
}

```

## disassembly

```asm
0x18000cba0  sub     rsp, 58h
0x18000cba4  xor     r8d, r8d
0x18000cba7  mov     r10, rcx
0x18000cbaa  test    r9, r9
0x18000cbad  jz      short loc_18000CBC7
0x18000cbaf  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000cbb3  inc     rax
0x18000cbb6  cmp     [r9+rax*2], r8w
0x18000cbbb  jnz     short loc_18000CBB3
0x18000cbbd  lea     rcx, ds:2[rax*2]
0x18000cbc5  jmp     short loc_18000CBCC
0x18000cbc7  mov     ecx, 0Ah
0x18000cbcc  mov     [rsp+58h+var_18], r8
0x18000cbd1  lea     rax, aNull_0; "NULL"
0x18000cbd8  test    r9, r9
0x18000cbdb  mov     [rsp+58h+var_20], 10h
0x18000cbe4  lea     r8, WPP_8228437e81df3f2b17e42002fd9073a5_Traceguids
0x18000cbeb  cmovz   r9, rax
0x18000cbef  mov     rax, [rsp+58h+arg_20]
0x18000cbf7  mov     [rsp+58h+var_28], rax
0x18000cbfc  mov     [rsp+58h+var_30], rcx
0x18000cc01  mov     rcx, r10
0x18000cc04  mov     [rsp+58h+var_38], r9
0x18000cc09  movzx   r9d, dx
0x18000cc0d  mov     edx, 2Bh ; '+'
0x18000cc12  call    cs:__imp_EtwTraceMessage
0x18000cc18  add     rsp, 58h
0x18000cc1c  retn
```
