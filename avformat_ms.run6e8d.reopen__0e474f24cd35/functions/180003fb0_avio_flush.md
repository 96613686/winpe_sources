# avio_flush

- ea: `0x180003fb0`
- end: `0x180004005`
- name: `avio_flush`
- size: `85`
- prototype: ``
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x180002a30`
- `0x180002e8c`
- `0x180003f00`
- `0x180004010`
- `0x1800051e0`
- `0x180005290`
- `0x1800122a0`
- `0x18001315c`

## callees

- `0x180003fb0`
- `0x1800049e0`
- `0x180005c3c`

## pseudocode

```c
__int64 __fastcall avio_flush(__int64 a1)
{
  __int64 v2; // rbx
  __int64 result; // rax

  if ( *(_DWORD *)(a1 + 88) )
  {
    v2 = *(_QWORD *)(a1 + 24) - *(_QWORD *)(a1 + 176);
    if ( v2 >= 0 )
      LODWORD(v2) = 0;
  }
  else
  {
    LODWORD(v2) = 0;
  }
  result = sub_180005C3C(a1);
  if ( (_DWORD)v2 )
    return avio_seek(a1, (int)v2, 1);
  return result;
}

```

## disassembly

```asm
0x180003fb0  mov     [rsp+arg_0], rbx
0x180003fb5  mov     [rsp+arg_8], rsi
0x180003fba  push    rdi
0x180003fbb  sub     rsp, 20h
0x180003fbf  xor     esi, esi
0x180003fc1  mov     rdi, rcx
0x180003fc4  cmp     [rcx+58h], esi
0x180003fc7  jz      short loc_180003FD9
0x180003fc9  mov     rbx, [rcx+18h]
0x180003fcd  sub     rbx, [rcx+0B0h]
0x180003fd4  cmovns  ebx, esi
0x180003fd7  jmp     short loc_180003FDB
0x180003fd9  mov     ebx, esi
0x180003fdb  call    sub_180005C3C
0x180003fe0  test    ebx, ebx
0x180003fe2  jz      short loc_180003FF5
0x180003fe4  movsxd  rdx, ebx
0x180003fe7  mov     r8d, 1
0x180003fed  mov     rcx, rdi
0x180003ff0  call    avio_seek
0x180003ff5  mov     rbx, [rsp+28h+arg_0]
0x180003ffa  mov     rsi, [rsp+28h+arg_8]
0x180003fff  add     rsp, 20h
0x180004003  pop     rdi
0x180004004  retn
```
