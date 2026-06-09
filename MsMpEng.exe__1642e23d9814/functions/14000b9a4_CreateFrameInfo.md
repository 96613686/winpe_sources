# _CreateFrameInfo

- ea: `0x14000b9a4`
- end: `0x14000b9de`
- name: `_CreateFrameInfo`
- size: `58`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14000e680`
- `0x14000e870`

## callees

- `0x14000b9a4`
- `0x14000c2e0`

## pseudocode

```c
_QWORD *__fastcall CreateFrameInfo(_QWORD *a1, __int64 a2)
{
  __int64 v3; // rcx

  *a1 = a2;
  if ( (unsigned __int64)a1 >= *(_QWORD *)(sub_14000C2E0() + 88) )
    v3 = 0;
  else
    v3 = *(_QWORD *)(sub_14000C2E0() + 88);
  a1[1] = v3;
  *(_QWORD *)(sub_14000C2E0() + 88) = a1;
  return a1;
}

```

## disassembly

```asm
0x14000b9a4  push    rbx
0x14000b9a6  sub     rsp, 20h
0x14000b9aa  mov     rbx, rcx
0x14000b9ad  mov     [rcx], rdx
0x14000b9b0  call    sub_14000C2E0
0x14000b9b5  cmp     rbx, [rax+58h]
0x14000b9b9  jnb     short loc_14000B9C6
0x14000b9bb  call    sub_14000C2E0
0x14000b9c0  mov     rcx, [rax+58h]
0x14000b9c4  jmp     short loc_14000B9C8
0x14000b9c6  xor     ecx, ecx
0x14000b9c8  mov     [rbx+8], rcx
0x14000b9cc  call    sub_14000C2E0
0x14000b9d1  mov     [rax+58h], rbx
0x14000b9d5  mov     rax, rbx
0x14000b9d8  add     rsp, 20h
0x14000b9dc  pop     rbx
0x14000b9dd  retn
```
