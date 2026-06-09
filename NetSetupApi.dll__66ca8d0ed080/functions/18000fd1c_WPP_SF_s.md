# WPP_SF_s

- ea: `0x18000fd1c`
- end: `0x18000fd72`
- name: `WPP_SF_s`
- size: `86`
- prototype: `__int64 __fastcall(__int64, unsigned __int16, __int64, const char *)`
- caller_count: `11`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180003b90`
- `0x180006af8`
- `0x18000d800`
- `0x18000da04`
- `0x18000db4c`
- `0x18000dcc8`
- `0x18000dda4`
- `0x18000de90`
- `0x18000e0d8`
- `0x18000e424`
- `0x18000e70c`

## callees

- `0x18000fd1c`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x18000fd67`
- `ntdll!EtwTraceMessage` at `0x18000fd67`

## pseudocode

```c
__int64 __fastcall WPP_SF_s(__int64 a1, unsigned __int16 a2, __int64 a3, const char *a4)
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
    a4 = "NULL";
  return EtwTraceMessage(a1, 43, a3, a2, a4);
}

```

## disassembly

```asm
0x18000fd1c  sub     rsp, 48h
0x18000fd20  test    r9, r9
0x18000fd23  jz      short loc_18000FD38
0x18000fd25  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000fd29  inc     rax
0x18000fd2c  cmp     byte ptr [r9+rax], 0
0x18000fd31  jnz     short loc_18000FD29
0x18000fd33  inc     rax
0x18000fd36  jmp     short loc_18000FD3D
0x18000fd38  mov     eax, 5
0x18000fd3d  test    r9, r9
0x18000fd40  mov     [rsp+48h+var_18], 0
0x18000fd49  lea     r10, aNull; "NULL"
0x18000fd50  mov     [rsp+48h+var_20], rax
0x18000fd55  cmovz   r9, r10
0x18000fd59  mov     [rsp+48h+var_28], r9
0x18000fd5e  movzx   r9d, dx
0x18000fd62  mov     edx, 2Bh ; '+'
0x18000fd67  call    cs:__imp_EtwTraceMessage
0x18000fd6d  add     rsp, 48h
0x18000fd71  retn
```
