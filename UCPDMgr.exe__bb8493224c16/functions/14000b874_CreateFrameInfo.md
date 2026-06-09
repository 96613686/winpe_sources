# _CreateFrameInfo

- ea: `0x14000b874`
- end: `0x14000b8ae`
- name: `_CreateFrameInfo`
- size: `58`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000d4b0`

## callees

- `0x14000b874`
- `0x14000be88`

## pseudocode

```c
_QWORD *__fastcall CreateFrameInfo(_QWORD *a1, __int64 a2)
{
  __int64 v3; // rcx

  *a1 = a2;
  if ( (unsigned __int64)a1 >= *(_QWORD *)(_vcrt_getptd() + 88) )
    v3 = 0;
  else
    v3 = *(_QWORD *)(_vcrt_getptd() + 88);
  a1[1] = v3;
  *(_QWORD *)(_vcrt_getptd() + 88) = a1;
  return a1;
}

```

## disassembly

```asm
0x14000b874  push    rbx
0x14000b876  sub     rsp, 20h
0x14000b87a  mov     rbx, rcx
0x14000b87d  mov     [rcx], rdx
0x14000b880  call    __vcrt_getptd
0x14000b885  cmp     rbx, [rax+58h]
0x14000b889  jnb     short loc_14000B896
0x14000b88b  call    __vcrt_getptd
0x14000b890  mov     rcx, [rax+58h]
0x14000b894  jmp     short loc_14000B898
0x14000b896  xor     ecx, ecx
0x14000b898  mov     [rbx+8], rcx
0x14000b89c  call    __vcrt_getptd
0x14000b8a1  mov     [rax+58h], rbx
0x14000b8a5  mov     rax, rbx
0x14000b8a8  add     rsp, 20h
0x14000b8ac  pop     rbx
0x14000b8ad  retn
```
