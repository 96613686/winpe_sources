# _FindAndUnlinkFrame

- ea: `0x14001d82c`
- end: `0x14001d87f`
- name: `_FindAndUnlinkFrame`
- size: `83`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x140021250`
- `0x140021450`

## callees

- `0x1400104cc`
- `0x14001d82c`
- `0x14001ef30`

## pseudocode

```c
__int64 __fastcall FindAndUnlinkFrame(__int64 a1)
{
  __int64 v2; // rdx
  __int64 v3; // rbx
  __int64 result; // rax

  if ( a1 != *(_QWORD *)(sub_14001EF30() + 88) || (v2 = *(_QWORD *)(sub_14001EF30() + 88)) == 0 )
LABEL_7:
    abort();
  while ( 1 )
  {
    v3 = *(_QWORD *)(v2 + 8);
    if ( a1 == v2 )
      break;
    v2 = *(_QWORD *)(v2 + 8);
    if ( !v3 )
      goto LABEL_7;
  }
  result = sub_14001EF30();
  *(_QWORD *)(result + 88) = v3;
  return result;
}

```

## disassembly

```asm
0x14001d82c  mov     [rsp+arg_0], rbx
0x14001d831  push    rdi
0x14001d832  sub     rsp, 20h
0x14001d836  mov     rdi, rcx
0x14001d839  call    sub_14001EF30
0x14001d83e  cmp     rdi, [rax+58h]
0x14001d842  jnz     short loc_14001D879
0x14001d844  call    sub_14001EF30
0x14001d849  mov     rdx, [rax+58h]
0x14001d84d  test    rdx, rdx
0x14001d850  jz      short loc_14001D879
0x14001d852  mov     rbx, [rdx+8]
0x14001d856  cmp     rdi, rdx
0x14001d859  jz      short loc_14001D865
0x14001d85b  mov     rdx, rbx
0x14001d85e  test    rbx, rbx
0x14001d861  jz      short loc_14001D879
0x14001d863  jmp     short loc_14001D852
0x14001d865  call    sub_14001EF30
0x14001d86a  mov     [rax+58h], rbx
0x14001d86e  mov     rbx, [rsp+28h+arg_0]
0x14001d873  add     rsp, 20h
0x14001d877  pop     rdi
0x14001d878  retn
0x14001d879  call    abort
```
