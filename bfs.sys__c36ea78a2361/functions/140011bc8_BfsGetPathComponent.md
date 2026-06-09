# BfsGetPathComponent

- ea: `0x140011bc8`
- end: `0x140011c37`
- name: `BfsGetPathComponent`
- size: `111`
- prototype: `__int16 *__fastcall(__int16 *, _OWORD *, __int64)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400067c0`
- `0x140006fa4`
- `0x1400104ec`
- `0x140011194`
- `0x140012608`

## callees

- `0x140011bc8`

## pseudocode

```c
__int16 *__fastcall BfsGetPathComponent(__int16 *a1, _OWORD *a2, __int64 a3)
{
  __int16 v4; // r10
  int v5; // r11d
  __int64 v6; // xmm0_8
  __int16 v7; // bx
  __int16 v8; // dx
  __int16 *v9; // rax
  __int16 v10; // cx
  __int16 *result; // rax

  v4 = 0;
  *(_OWORD *)a1 = *a2;
  v5 = *(_DWORD *)(a1 + 5);
  v6 = *(_QWORD *)(a1 + 1);
  v7 = a1[7];
  while ( 1 )
  {
    v8 = *a1;
    if ( (unsigned __int16)*a1 < 2u )
      break;
    v9 = (__int16 *)*((_QWORD *)a1 + 1);
    v8 -= 2;
    v10 = *v9;
    *a1 = v8;
    *((_QWORD *)a1 + 1) = v9 + 1;
    if ( v10 == 92 )
      break;
    v4 += 2;
  }
  *(_QWORD *)(a3 + 2) = v6;
  result = a1;
  *(_DWORD *)(a3 + 10) = v5;
  *(_WORD *)(a3 + 14) = v7;
  *(_WORD *)a3 = v4;
  a1[1] = v8;
  return result;
}

```

## disassembly

```asm
0x140011bc8  mov     [rsp+arg_0], rbx
0x140011bcd  movups  xmm0, xmmword ptr [rdx]
0x140011bd0  mov     r9, rcx
0x140011bd3  xor     r10d, r10d
0x140011bd6  movdqu  xmmword ptr [rcx], xmm0
0x140011bda  mov     r11d, [rcx+0Ah]
0x140011bde  movsd   xmm0, qword ptr [rcx+2]
0x140011be3  movzx   ebx, word ptr [rcx+0Eh]
0x140011be7  movzx   edx, word ptr [r9]
0x140011beb  cmp     dx, 2
0x140011bef  jb      short loc_140011C15
0x140011bf1  mov     rax, [r9+8]
0x140011bf5  sub     dx, 2
0x140011bf9  movzx   ecx, word ptr [rax]
0x140011bfc  add     rax, 2
0x140011c00  mov     [r9], dx
0x140011c04  mov     [r9+8], rax
0x140011c08  cmp     cx, 5Ch ; '\'
0x140011c0c  jz      short loc_140011C15
0x140011c0e  add     r10w, 2
0x140011c13  jmp     short loc_140011BE7
0x140011c15  movsd   qword ptr [r8+2], xmm0
0x140011c1b  mov     rax, r9
0x140011c1e  mov     [r8+0Ah], r11d
0x140011c22  mov     [r8+0Eh], bx
0x140011c27  mov     rbx, [rsp+arg_0]
0x140011c2c  mov     [r8], r10w
0x140011c30  mov     [r9+2], dx
0x140011c35  retn
```
