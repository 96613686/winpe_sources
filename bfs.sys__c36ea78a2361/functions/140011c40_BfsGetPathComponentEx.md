# BfsGetPathComponentEx

- ea: `0x140011c40`
- end: `0x140011ccc`
- name: `BfsGetPathComponentEx`
- size: `140`
- prototype: `__int16 *__fastcall(__int16 *, __int128 *, __int64, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400067c0`

## callees

- `0x140011c40`

## pseudocode

```c
__int16 *__fastcall BfsGetPathComponentEx(__int16 *a1, __int128 *a2, __int64 a3, __int64 a4)
{
  __int128 v4; // xmm0
  int v6; // r10d
  __int16 v7; // dx
  int v8; // r11d
  __int64 v9; // xmm0_8
  __int16 v10; // bx
  __int16 v11; // cx
  _WORD *v12; // rax
  __int16 *result; // rax

  v4 = *a2;
  v6 = 2;
  v7 = 0;
  *(_OWORD *)a1 = v4;
  v8 = *(_DWORD *)(a1 + 5);
  v9 = *(_QWORD *)(a1 + 1);
  v10 = a1[7];
  while ( 1 )
  {
    v11 = *a1;
    if ( (unsigned __int16)*a1 < 2u )
      break;
    v12 = (_WORD *)*((_QWORD *)a1 + 1);
    if ( *v12 == 92 && !--v6 )
    {
      v11 -= 2;
      *((_QWORD *)a1 + 1) = v12 + 1;
      *a1 = v11;
      break;
    }
    v7 += 2;
    *((_QWORD *)a1 + 1) = v12 + 1;
    *a1 = v11 - 2;
  }
  result = a1;
  *(_QWORD *)(a4 + 2) = v9;
  *(_DWORD *)(a4 + 10) = v8;
  *(_WORD *)(a4 + 14) = v10;
  *(_WORD *)a4 = v7;
  a1[1] = v11;
  return result;
}

```

## disassembly

```asm
0x140011c40  mov     [rsp+arg_0], rbx
0x140011c45  mov     [rsp+arg_8], rdi
0x140011c4a  movups  xmm0, xmmword ptr [rdx]
0x140011c4d  mov     edi, 2
0x140011c52  mov     r8, rcx
0x140011c55  mov     r10d, edi
0x140011c58  xor     edx, edx
0x140011c5a  movdqu  xmmword ptr [rcx], xmm0
0x140011c5e  mov     r11d, [rcx+0Ah]
0x140011c62  movsd   xmm0, qword ptr [rcx+2]
0x140011c67  movzx   ebx, word ptr [rcx+0Eh]
0x140011c6b  movzx   ecx, word ptr [r8]
0x140011c6f  cmp     cx, di
0x140011c72  jb      short loc_140011CA5
0x140011c74  mov     rax, [r8+8]
0x140011c78  cmp     word ptr [rax], 5Ch ; '\'
0x140011c7c  jnz     short loc_140011C84
0x140011c7e  sub     r10d, 1
0x140011c82  jz      short loc_140011C97
0x140011c84  add     rax, rdi
0x140011c87  add     dx, di
0x140011c8a  sub     cx, di
0x140011c8d  mov     [r8+8], rax
0x140011c91  mov     [r8], cx
0x140011c95  jmp     short loc_140011C6B
0x140011c97  add     rax, rdi
0x140011c9a  sub     cx, di
0x140011c9d  mov     [r8+8], rax
0x140011ca1  mov     [r8], cx
0x140011ca5  mov     rdi, [rsp+arg_8]
0x140011caa  mov     rax, r8
0x140011cad  movsd   qword ptr [r9+2], xmm0
0x140011cb3  mov     [r9+0Ah], r11d
0x140011cb7  mov     [r9+0Eh], bx
0x140011cbc  mov     rbx, [rsp+arg_0]
0x140011cc1  mov     [r9], dx
0x140011cc5  mov     [r8+2], cx
0x140011cca  retn
```
