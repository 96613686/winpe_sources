# CompleteDelayedUseProtseqs

- ea: `0x1800022b0`
- end: `0x1800022f4`
- name: `CompleteDelayedUseProtseqs`
- size: `68`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800018a0`
- `0x1800081a4`

## callees

- `0x1800022b0`
- `0x180009128`

## pseudocode

```c
void *CompleteDelayedUseProtseqs()
{
  unsigned __int16 i; // bx
  void *result; // rax

  for ( i = 1; i < 0x22u; ++i )
  {
    result = &gaProtseqInfo;
    if ( *((_DWORD *)&gaProtseqInfo + 6 * i) == 2 )
      result = (void *)UseProtseqIfNecessary(i);
  }
  return result;
}

```

## disassembly

```asm
0x1800022b0  mov     [rsp+arg_0], rbx
0x1800022b5  push    rdi
0x1800022b6  sub     rsp, 20h
0x1800022ba  mov     edi, 1
0x1800022bf  movzx   ebx, di
0x1800022c2  movzx   eax, bx
0x1800022c5  lea     rcx, [rax+rax*2]
0x1800022c9  lea     rax, ?gaProtseqInfo@@3PAUPROTSEQ_INFO@@A; PROTSEQ_INFO near * gaProtseqInfo
0x1800022d0  cmp     dword ptr [rax+rcx*8], 2
0x1800022d4  jz      short loc_1800022EA
0x1800022d6  add     bx, di
0x1800022d9  cmp     bx, 22h ; '"'
0x1800022dd  jb      short loc_1800022C2
0x1800022df  mov     rbx, [rsp+28h+arg_0]
0x1800022e4  add     rsp, 20h
0x1800022e8  pop     rdi
0x1800022e9  retn
0x1800022ea  movzx   ecx, bx
0x1800022ed  call    UseProtseqIfNecessary
0x1800022f2  jmp     short loc_1800022D6
```
