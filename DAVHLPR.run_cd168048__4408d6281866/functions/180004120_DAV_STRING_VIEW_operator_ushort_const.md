# DAV_STRING_VIEW::operator=(ushort const *)

- ea: `0x180004120`
- end: `0x180004154`
- name: `??4DAV_STRING_VIEW@@QEAAAEAU0@PEBG@Z`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001ba0`

## callees

- `0x180004120`

## pseudocode

```c
_QWORD *__fastcall DAV_STRING_VIEW::operator=(_QWORD *a1, __int64 a2)
{
  __int64 v2; // rax

  *a1 = a2;
  if ( a2 )
  {
    v2 = -1;
    while ( *(_WORD *)(a2 + 2 * v2++ + 2) != 0 )
      ;
    a1[1] = a2 + 2 * v2;
  }
  else
  {
    a1[1] = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x180004120  mov     [rcx], rdx
0x180004123  mov     r8, rcx
0x180004126  test    rdx, rdx
0x180004129  jz      short loc_18000414A
0x18000412b  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180004132  cmp     word ptr [rdx+rax*2+2], 0
0x180004138  lea     rax, [rax+1]
0x18000413c  jnz     short loc_180004132
0x18000413e  lea     rcx, [rdx+rax*2]
0x180004142  mov     [r8+8], rcx
0x180004146  mov     rax, r8
0x180004149  retn
0x18000414a  mov     qword ptr [rcx+8], 0
0x180004152  jmp     short loc_180004146
```
