# DnsFreeZtTrustedServerMembers

- ea: `0x18000c750`
- end: `0x18000c781`
- name: `DnsFreeZtTrustedServerMembers`
- size: `49`
- prototype: `void __fastcall(__int64)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x1800054bc`
- `0x180005924`
- `0x180005d90`
- `0x18000604c`
- `0x18000dcb0`

## callees

- `0x18000c750`
- `0x1800125d4`

## pseudocode

```c
void __fastcall DnsFreeZtTrustedServerMembers(__int64 a1)
{
  if ( a1 )
  {
    if ( (unsigned int)(*(_DWORD *)(a1 + 48) - 1) <= 1 )
    {
      Dns_Free(*(LPVOID *)(a1 + 56));
      *(_QWORD *)(a1 + 56) = 0;
    }
  }
}

```

## disassembly

```asm
0x18000c750  test    rcx, rcx
0x18000c753  jz      short locret_18000C780
0x18000c755  push    rbx
0x18000c756  sub     rsp, 20h
0x18000c75a  mov     rbx, rcx
0x18000c75d  mov     ecx, [rcx+30h]
0x18000c760  sub     ecx, 1
0x18000c763  jz      short loc_18000C76A
0x18000c765  cmp     ecx, 1
0x18000c768  jnz     short loc_18000C77B
0x18000c76a  mov     rcx, [rbx+38h]; lpMem
0x18000c76e  call    Dns_Free
0x18000c773  mov     qword ptr [rbx+38h], 0
0x18000c77b  add     rsp, 20h
0x18000c77f  pop     rbx
0x18000c780  retn
```
