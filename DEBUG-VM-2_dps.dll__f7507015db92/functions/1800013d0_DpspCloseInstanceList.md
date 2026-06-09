# DpspCloseInstanceList

- ea: `0x1800013d0`
- end: `0x18000144f`
- name: `DpspCloseInstanceList`
- size: `127`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x1800035d0`
- `0x180004864`
- `0x180004c18`
- `0x180004de4`
- `0x18000c6bc`
- `0x18000fbb4`
- `0x180011fd4`

## callees

- `0x180001010`
- `0x1800013d0`

## pseudocode

```c
__int64 __fastcall DpspCloseInstanceList(_QWORD **a1, _QWORD **a2)
{
  _QWORD *v2; // r14
  _QWORD *v4; // rsi
  __int64 v7; // rcx
  __int64 v8; // rcx

  v2 = *a1;
  v4 = *a2;
  while ( v2 != a1 )
  {
    v8 = (__int64)v2;
    v2 = (_QWORD *)*v2;
    if ( v8 )
      DpspCloseInstance(v8, 4u, 15, *(_DWORD *)(v8 + 132));
  }
  while ( v4 != a2 )
  {
    v7 = (__int64)v4;
    v4 = (_QWORD *)*v4;
    if ( v7 )
      DpspCloseInstance(v7, 7u, 0, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x1800013d0  push    rbx
0x1800013d2  push    rsi
0x1800013d3  push    rdi
0x1800013d4  push    r14
0x1800013d6  sub     rsp, 28h
0x1800013da  mov     r14, [rcx]
0x1800013dd  mov     rbx, rdx
0x1800013e0  mov     rsi, [rdx]
0x1800013e3  mov     rdi, rcx
0x1800013e6  cmp     r14, rcx
0x1800013e9  jnz     short loc_180001412
0x1800013eb  cmp     rsi, rbx
0x1800013ee  jnz     short loc_180001400
0x1800013f0  xor     eax, eax
0x1800013f2  add     rsp, 28h
0x1800013f6  pop     r14
0x1800013f8  pop     rdi
0x1800013f9  pop     rsi
0x1800013fa  pop     rbx
0x1800013fb  retn
0x180001400  mov     rcx, rsi
0x180001403  mov     rsi, [rsi]
0x180001406  test    rcx, rcx
0x180001409  jnz     short loc_18000143D
0x18000140b  cmp     rsi, rbx
0x18000140e  jz      short loc_1800013F0
0x180001410  jmp     short loc_180001400
0x180001412  mov     rcx, r14
0x180001415  mov     r14, [r14]
0x180001418  test    rcx, rcx
0x18000141b  jnz     short loc_180001424
0x18000141d  cmp     r14, rdi
0x180001420  jz      short loc_1800013EB
0x180001422  jmp     short loc_180001412
0x180001424  mov     r9d, [rcx+84h]
0x18000142b  mov     edx, 4
0x180001430  mov     r8d, 0Fh
0x180001436  call    DpspCloseInstance
0x18000143b  jmp     short loc_18000141D
0x18000143d  xor     r9d, r9d
0x180001440  xor     r8d, r8d
0x180001443  mov     edx, 7
0x180001448  call    DpspCloseInstance
0x18000144d  jmp     short loc_18000140B
```
