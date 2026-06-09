# WPP_SF_S

- ea: `0x18000cb40`
- end: `0x18000cb9a`
- name: `WPP_SF_S`
- size: `90`
- prototype: `__int64 __fastcall(__int64, unsigned __int16, __int64, const wchar_t *)`
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180004430`
- `0x180006af8`
- `0x18000be20`
- `0x18000c354`
- `0x18000c660`
- `0x18000c760`
- `0x18000c860`
- `0x18000c8e0`

## callees

- `0x18000cb40`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x18000cb8f`
- `ntdll!EtwTraceMessage` at `0x18000cb8f`

## pseudocode

```c
__int64 __fastcall WPP_SF_S(__int64 a1, unsigned __int16 a2, __int64 a3, const wchar_t *a4)
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
0x18000cb40  sub     rsp, 48h
0x18000cb44  xor     r11d, r11d
0x18000cb47  test    r9, r9
0x18000cb4a  jz      short loc_18000CB64
0x18000cb4c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000cb50  inc     rax
0x18000cb53  cmp     [r9+rax*2], r11w
0x18000cb58  jnz     short loc_18000CB50
0x18000cb5a  lea     rax, ds:2[rax*2]
0x18000cb62  jmp     short loc_18000CB69
0x18000cb64  mov     eax, 0Ah
0x18000cb69  test    r9, r9
0x18000cb6c  mov     [rsp+48h+var_18], r11
0x18000cb71  lea     r10, aNull_0; "NULL"
0x18000cb78  mov     [rsp+48h+var_20], rax
0x18000cb7d  cmovz   r9, r10
0x18000cb81  mov     [rsp+48h+var_28], r9
0x18000cb86  movzx   r9d, dx
0x18000cb8a  mov     edx, 2Bh ; '+'
0x18000cb8f  call    cs:__imp_EtwTraceMessage
0x18000cb95  add     rsp, 48h
0x18000cb99  retn
```
