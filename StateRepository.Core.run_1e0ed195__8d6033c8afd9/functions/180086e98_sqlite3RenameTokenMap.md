# sqlite3RenameTokenMap

- ea: `0x180086e98`
- end: `0x180086efb`
- name: `sqlite3RenameTokenMap`
- size: `99`
- prototype: ``
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x18000d01c`
- `0x18000ded0`
- `0x180010e90`
- `0x180031b38`
- `0x18003e0cc`
- `0x18004ad04`
- `0x18004ec84`
- `0x180058e44`
- `0x18005c8b0`
- `0x18005cefc`

## callees

- `0x18000f720`
- `0x180086e98`

## pseudocode

```c
__int64 __fastcall sqlite3RenameTokenMap(__int64 a1, __int64 a2, _OWORD *a3)
{
  __int64 v6; // rax

  if ( *(_BYTE *)(a1 + 308) != 3 )
  {
    v6 = sqlite3DbMallocZero(*(_QWORD *)a1, 32);
    if ( v6 )
    {
      *(_QWORD *)v6 = a2;
      *(_OWORD *)(v6 + 8) = *a3;
      *(_QWORD *)(v6 + 24) = *(_QWORD *)(a1 + 416);
      *(_QWORD *)(a1 + 416) = v6;
    }
  }
  return a2;
}

```

## disassembly

```asm
0x180086e98  mov     [rsp+arg_0], rbx
0x180086e9d  mov     [rsp+arg_8], rsi
0x180086ea2  push    rdi
0x180086ea3  sub     rsp, 20h
0x180086ea7  cmp     byte ptr [rcx+134h], 3
0x180086eae  mov     rsi, r8
0x180086eb1  mov     rdi, rdx
0x180086eb4  mov     rbx, rcx
0x180086eb7  jz      short loc_180086EE8
0x180086eb9  mov     rcx, [rcx]
0x180086ebc  mov     edx, 20h ; ' '
0x180086ec1  call    sqlite3DbMallocZero
0x180086ec6  test    rax, rax
0x180086ec9  jz      short loc_180086EE8
0x180086ecb  mov     [rax], rdi
0x180086ece  movups  xmm0, xmmword ptr [rsi]
0x180086ed1  movdqu  xmmword ptr [rax+8], xmm0
0x180086ed6  mov     rcx, [rbx+1A0h]
0x180086edd  mov     [rax+18h], rcx
0x180086ee1  mov     [rbx+1A0h], rax
0x180086ee8  mov     rbx, [rsp+28h+arg_0]
0x180086eed  mov     rax, rdi
0x180086ef0  mov     rsi, [rsp+28h+arg_8]
0x180086ef5  add     rsp, 20h
0x180086ef9  pop     rdi
0x180086efa  retn
```
