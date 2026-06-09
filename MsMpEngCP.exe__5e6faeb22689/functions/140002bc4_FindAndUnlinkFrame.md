# _FindAndUnlinkFrame

- ea: `0x140002bc4`
- end: `0x140002c17`
- name: `_FindAndUnlinkFrame`
- size: `83`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x140003d60`

## callees

- `0x140002260`
- `0x140002bc4`
- `0x140005a20`

## pseudocode

```c
__int64 __fastcall FindAndUnlinkFrame(__int64 a1)
{
  __int64 v2; // rdx
  __int64 v3; // rbx
  __int64 result; // rax

  if ( a1 != *(_QWORD *)(sub_140002260() + 88) || (v2 = *(_QWORD *)(sub_140002260() + 88)) == 0 )
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
  result = sub_140002260();
  *(_QWORD *)(result + 88) = v3;
  return result;
}

```

## disassembly

```asm
0x140002bc4  mov     [rsp+arg_0], rbx
0x140002bc9  push    rdi
0x140002bca  sub     rsp, 20h
0x140002bce  mov     rdi, rcx
0x140002bd1  call    sub_140002260
0x140002bd6  cmp     rdi, [rax+58h]
0x140002bda  jnz     short loc_140002C11
0x140002bdc  call    sub_140002260
0x140002be1  mov     rdx, [rax+58h]
0x140002be5  test    rdx, rdx
0x140002be8  jz      short loc_140002C11
0x140002bea  mov     rbx, [rdx+8]
0x140002bee  cmp     rdi, rdx
0x140002bf1  jz      short loc_140002BFD
0x140002bf3  mov     rdx, rbx
0x140002bf6  test    rbx, rbx
0x140002bf9  jz      short loc_140002C11
0x140002bfb  jmp     short loc_140002BEA
0x140002bfd  call    sub_140002260
0x140002c02  mov     [rax+58h], rbx
0x140002c06  mov     rbx, [rsp+28h+arg_0]
0x140002c0b  add     rsp, 20h
0x140002c0f  pop     rdi
0x140002c10  retn
0x140002c11  call    abort
```
