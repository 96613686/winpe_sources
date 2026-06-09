# BfsGetPathComponentEx

- ea: `0x140011ab0`
- end: `0x140011b3c`
- name: `BfsGetPathComponentEx`
- size: `140`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140006630`

## callees

- `0x140011ab0`

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
0x140011ab0  mov     [rsp+arg_0], rbx
0x140011ab5  mov     [rsp+arg_8], rdi
0x140011aba  movups  xmm0, xmmword ptr [rdx]
0x140011abd  mov     edi, 2
0x140011ac2  mov     r8, rcx
0x140011ac5  mov     r10d, edi
0x140011ac8  xor     edx, edx
0x140011aca  movdqu  xmmword ptr [rcx], xmm0
0x140011ace  mov     r11d, [rcx+0Ah]
0x140011ad2  movsd   xmm0, qword ptr [rcx+2]
0x140011ad7  movzx   ebx, word ptr [rcx+0Eh]
0x140011adb  movzx   ecx, word ptr [r8]
0x140011adf  cmp     cx, di
0x140011ae2  jb      short loc_140011B15
0x140011ae4  mov     rax, [r8+8]
0x140011ae8  cmp     word ptr [rax], 5Ch ; '\'
0x140011aec  jnz     short loc_140011AF4
0x140011aee  sub     r10d, 1
0x140011af2  jz      short loc_140011B07
0x140011af4  add     rax, rdi
0x140011af7  add     dx, di
0x140011afa  sub     cx, di
0x140011afd  mov     [r8+8], rax
0x140011b01  mov     [r8], cx
0x140011b05  jmp     short loc_140011ADB
0x140011b07  add     rax, rdi
0x140011b0a  sub     cx, di
0x140011b0d  mov     [r8+8], rax
0x140011b11  mov     [r8], cx
0x140011b15  mov     rdi, [rsp+arg_8]
0x140011b1a  mov     rax, r8
0x140011b1d  movsd   qword ptr [r9+2], xmm0
0x140011b23  mov     [r9+0Ah], r11d
0x140011b27  mov     [r9+0Eh], bx
0x140011b2c  mov     rbx, [rsp+arg_0]
0x140011b31  mov     [r9], dx
0x140011b35  mov     [r8+2], cx
0x140011b3a  retn
```
