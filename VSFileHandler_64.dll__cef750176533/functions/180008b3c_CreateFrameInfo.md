# _CreateFrameInfo

- ea: `0x180008b3c`
- end: `0x180008b76`
- name: `_CreateFrameInfo`
- size: `58`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000aa20`

## callees

- `0x180008b3c`
- `0x180009518`

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
0x180008b3c  push    rbx
0x180008b3e  sub     rsp, 20h
0x180008b42  mov     rbx, rcx
0x180008b45  mov     [rcx], rdx
0x180008b48  call    __vcrt_getptd
0x180008b4d  cmp     rbx, [rax+58h]
0x180008b51  jnb     short loc_180008B5E
0x180008b53  call    __vcrt_getptd
0x180008b58  mov     rcx, [rax+58h]
0x180008b5c  jmp     short loc_180008B60
0x180008b5e  xor     ecx, ecx
0x180008b60  mov     [rbx+8], rcx
0x180008b64  call    __vcrt_getptd
0x180008b69  mov     [rax+58h], rbx
0x180008b6d  mov     rax, rbx
0x180008b70  add     rsp, 20h
0x180008b74  pop     rbx
0x180008b75  retn
```
