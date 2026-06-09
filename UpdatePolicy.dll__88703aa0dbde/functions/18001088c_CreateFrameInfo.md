# _CreateFrameInfo

- ea: `0x18001088c`
- end: `0x1800108c6`
- name: `_CreateFrameInfo`
- size: `58`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800134f0`
- `0x1800136f0`

## callees

- `0x18001088c`
- `0x180011058`

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
0x18001088c  push    rbx
0x18001088e  sub     rsp, 20h
0x180010892  mov     rbx, rcx
0x180010895  mov     [rcx], rdx
0x180010898  call    __vcrt_getptd
0x18001089d  cmp     rbx, [rax+58h]
0x1800108a1  jnb     short loc_1800108AE
0x1800108a3  call    __vcrt_getptd
0x1800108a8  mov     rcx, [rax+58h]
0x1800108ac  jmp     short loc_1800108B0
0x1800108ae  xor     ecx, ecx
0x1800108b0  mov     [rbx+8], rcx
0x1800108b4  call    __vcrt_getptd
0x1800108b9  mov     [rax+58h], rbx
0x1800108bd  mov     rax, rbx
0x1800108c0  add     rsp, 20h
0x1800108c4  pop     rbx
0x1800108c5  retn
```
