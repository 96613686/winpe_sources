# PipeCompletionRoutine

- ea: `0x1400013a0`
- end: `0x1400013ff`
- name: `PipeCompletionRoutine`
- size: `95`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1400013a0`
- `0x14000a7bc`
- `0x14000d830`

## pseudocode

```c
__int64 __fastcall PipeCompletionRoutine(__int64 a1, __int64 a2, unsigned __int8 **a3)
{
  unsigned __int8 *v3; // rbx
  __int64 v6; // r9
  __int64 v7; // r8
  unsigned __int8 *v8; // rdx

  v3 = a3[3];
  v6 = (__int64)a3[4];
  a3[2] = (unsigned __int8 *)(MEMORY[0xFFFFF78000000014] - (_QWORD)a3[2]);
  v7 = *(unsigned int *)(a2 + 48);
  v8 = *a3;
  if ( v3 )
    ((void (__fastcall *)(unsigned __int8 *, unsigned __int8 *, __int64, __int64))v3)(a3[1], v8, v7, v6);
  else
    StatusPipeCompletion((__int64)a3, v8, v7, a2, v6);
  return 3221225494LL;
}

```

## disassembly

```asm
0x1400013a0  push    rbx
0x1400013a2  sub     rsp, 30h
0x1400013a6  mov     rbx, [r8+18h]
0x1400013aa  mov     r10, r8
0x1400013ad  mov     rax, 0FFFFF78000000014h
0x1400013b7  mov     r11, rdx
0x1400013ba  mov     rax, [rax]
0x1400013bd  sub     rax, [r8+10h]
0x1400013c1  mov     r9, [r8+20h]
0x1400013c5  mov     [r8+10h], rax
0x1400013c9  mov     r8d, [rdx+30h]
0x1400013cd  mov     rdx, [r10]
0x1400013d0  test    rbx, rbx
0x1400013d3  jnz     short loc_1400013E7
0x1400013d5  mov     [rsp+38h+var_18], r9
0x1400013da  mov     rcx, r10
0x1400013dd  mov     r9, r11
0x1400013e0  call    StatusPipeCompletion
0x1400013e5  jmp     short loc_1400013F3
0x1400013e7  mov     rcx, [r10+8]
0x1400013eb  mov     rax, rbx
0x1400013ee  call    _guard_dispatch_icall
0x1400013f3  mov     eax, 0C0000016h
0x1400013f8  add     rsp, 30h
0x1400013fc  pop     rbx
0x1400013fd  retn
```
