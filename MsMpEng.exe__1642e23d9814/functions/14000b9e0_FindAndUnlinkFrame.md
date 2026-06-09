# _FindAndUnlinkFrame

- ea: `0x14000b9e0`
- end: `0x14000ba33`
- name: `_FindAndUnlinkFrame`
- size: `83`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x14000e680`
- `0x14000e870`

## callees

- `0x14000b9e0`
- `0x14000c2e0`
- `0x140019148`

## pseudocode

```c
__int64 __fastcall FindAndUnlinkFrame(__int64 a1)
{
  __int64 v2; // rdx
  __int64 v3; // rbx
  __int64 result; // rax

  if ( a1 != *(_QWORD *)(sub_14000C2E0() + 88) || (v2 = *(_QWORD *)(sub_14000C2E0() + 88)) == 0 )
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
  result = sub_14000C2E0();
  *(_QWORD *)(result + 88) = v3;
  return result;
}

```

## disassembly

```asm
0x14000b9e0  mov     [rsp+arg_0], rbx
0x14000b9e5  push    rdi
0x14000b9e6  sub     rsp, 20h
0x14000b9ea  mov     rdi, rcx
0x14000b9ed  call    sub_14000C2E0
0x14000b9f2  cmp     rdi, [rax+58h]
0x14000b9f6  jnz     short loc_14000BA2D
0x14000b9f8  call    sub_14000C2E0
0x14000b9fd  mov     rdx, [rax+58h]
0x14000ba01  test    rdx, rdx
0x14000ba04  jz      short loc_14000BA2D
0x14000ba06  mov     rbx, [rdx+8]
0x14000ba0a  cmp     rdi, rdx
0x14000ba0d  jz      short loc_14000BA19
0x14000ba0f  mov     rdx, rbx
0x14000ba12  test    rbx, rbx
0x14000ba15  jz      short loc_14000BA2D
0x14000ba17  jmp     short loc_14000BA06
0x14000ba19  call    sub_14000C2E0
0x14000ba1e  mov     [rax+58h], rbx
0x14000ba22  mov     rbx, [rsp+28h+arg_0]
0x14000ba27  add     rsp, 20h
0x14000ba2b  pop     rdi
0x14000ba2c  retn
0x14000ba2d  call    abort
```
