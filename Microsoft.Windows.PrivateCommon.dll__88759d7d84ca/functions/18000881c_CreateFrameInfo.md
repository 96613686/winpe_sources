# _CreateFrameInfo

- ea: `0x18000881c`
- end: `0x180008856`
- name: `_CreateFrameInfo`
- size: `58`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a530`

## callees

- `0x18000881c`
- `0x180008fc8`

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
0x18000881c  push    rbx
0x18000881e  sub     rsp, 20h
0x180008822  mov     rbx, rcx
0x180008825  mov     [rcx], rdx
0x180008828  call    __vcrt_getptd
0x18000882d  cmp     rbx, [rax+58h]
0x180008831  jnb     short loc_18000883E
0x180008833  call    __vcrt_getptd
0x180008838  mov     rcx, [rax+58h]
0x18000883c  jmp     short loc_180008840
0x18000883e  xor     ecx, ecx
0x180008840  mov     [rbx+8], rcx
0x180008844  call    __vcrt_getptd
0x180008849  mov     [rax+58h], rbx
0x18000884d  mov     rax, rbx
0x180008850  add     rsp, 20h
0x180008854  pop     rbx
0x180008855  retn
```
