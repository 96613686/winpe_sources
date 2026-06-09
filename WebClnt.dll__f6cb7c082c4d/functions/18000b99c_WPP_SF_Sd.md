# WPP_SF_Sd

- ea: `0x18000b99c`
- end: `0x18000ba0c`
- name: `WPP_SF_Sd`
- size: `112`
- prototype: ``
- caller_count: `12`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180006670`
- `0x180006a90`
- `0x18000a370`
- `0x18000a770`
- `0x18000fce0`
- `0x180010478`
- `0x1800117f4`
- `0x1800135b4`
- `0x18001ad0c`
- `0x18002986c`
- `0x18002afb0`
- `0x18002b5f4`

## callees

- `0x18000b99c`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x18000ba01`
- `ntdll!EtwTraceMessage` at `0x18000ba01`

## pseudocode

```c
__int64 __fastcall WPP_SF_Sd(__int64 a1, unsigned __int16 a2, __int64 a3, const wchar_t *a4)
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
  return EtwTraceMessage(a1, 43, a3, a2, a4);
}

```

## disassembly

```asm
0x18000b99c  sub     rsp, 58h
0x18000b9a0  xor     r11d, r11d
0x18000b9a3  test    r9, r9
0x18000b9a6  jz      short loc_18000B9C0
0x18000b9a8  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b9ac  inc     rax
0x18000b9af  cmp     [r9+rax*2], r11w
0x18000b9b4  jnz     short loc_18000B9AC
0x18000b9b6  lea     rax, ds:2[rax*2]
0x18000b9be  jmp     short loc_18000B9C5
0x18000b9c0  mov     eax, 0Ah
0x18000b9c5  mov     [rsp+58h+var_18], r11
0x18000b9ca  lea     r10, aNull_0; "NULL"
0x18000b9d1  test    r9, r9
0x18000b9d4  mov     [rsp+58h+var_20], 4
0x18000b9dd  cmovz   r9, r10
0x18000b9e1  lea     r10, [rsp+58h+arg_20]
0x18000b9e9  mov     [rsp+58h+var_28], r10
0x18000b9ee  mov     [rsp+58h+var_30], rax
0x18000b9f3  mov     [rsp+58h+var_38], r9
0x18000b9f8  movzx   r9d, dx
0x18000b9fc  mov     edx, 2Bh ; '+'
0x18000ba01  call    cs:__imp_EtwTraceMessage
0x18000ba07  add     rsp, 58h
0x18000ba0b  retn
```
