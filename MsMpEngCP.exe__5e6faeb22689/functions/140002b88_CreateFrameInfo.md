# _CreateFrameInfo

- ea: `0x140002b88`
- end: `0x140002bc2`
- name: `_CreateFrameInfo`
- size: `58`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140003d60`

## callees

- `0x140002260`
- `0x140002b88`

## pseudocode

```c
_QWORD *__fastcall CreateFrameInfo(_QWORD *a1, __int64 a2)
{
  __int64 v3; // rcx

  *a1 = a2;
  if ( (unsigned __int64)a1 >= *(_QWORD *)(sub_140002260() + 88) )
    v3 = 0;
  else
    v3 = *(_QWORD *)(sub_140002260() + 88);
  a1[1] = v3;
  *(_QWORD *)(sub_140002260() + 88) = a1;
  return a1;
}

```

## disassembly

```asm
0x140002b88  push    rbx
0x140002b8a  sub     rsp, 20h
0x140002b8e  mov     rbx, rcx
0x140002b91  mov     [rcx], rdx
0x140002b94  call    sub_140002260
0x140002b99  cmp     rbx, [rax+58h]
0x140002b9d  jnb     short loc_140002BAA
0x140002b9f  call    sub_140002260
0x140002ba4  mov     rcx, [rax+58h]
0x140002ba8  jmp     short loc_140002BAC
0x140002baa  xor     ecx, ecx
0x140002bac  mov     [rbx+8], rcx
0x140002bb0  call    sub_140002260
0x140002bb5  mov     [rax+58h], rbx
0x140002bb9  mov     rax, rbx
0x140002bbc  add     rsp, 20h
0x140002bc0  pop     rbx
0x140002bc1  retn
```
