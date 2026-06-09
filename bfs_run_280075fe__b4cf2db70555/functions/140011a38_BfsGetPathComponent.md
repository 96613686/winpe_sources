# BfsGetPathComponent

- ea: `0x140011a38`
- end: `0x140011aa7`
- name: `BfsGetPathComponent`
- size: `111`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140006630`
- `0x140006e14`
- `0x14001033c`
- `0x140010ffc`
- `0x140012478`

## callees

- `0x140011a38`

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
0x140011a38  mov     [rsp+arg_0], rbx
0x140011a3d  movups  xmm0, xmmword ptr [rdx]
0x140011a40  mov     r9, rcx
0x140011a43  xor     r10d, r10d
0x140011a46  movdqu  xmmword ptr [rcx], xmm0
0x140011a4a  mov     r11d, [rcx+0Ah]
0x140011a4e  movsd   xmm0, qword ptr [rcx+2]
0x140011a53  movzx   ebx, word ptr [rcx+0Eh]
0x140011a57  movzx   edx, word ptr [r9]
0x140011a5b  cmp     dx, 2
0x140011a5f  jb      short loc_140011A85
0x140011a61  mov     rax, [r9+8]
0x140011a65  sub     dx, 2
0x140011a69  movzx   ecx, word ptr [rax]
0x140011a6c  add     rax, 2
0x140011a70  mov     [r9], dx
0x140011a74  mov     [r9+8], rax
0x140011a78  cmp     cx, 5Ch ; '\'
0x140011a7c  jz      short loc_140011A85
0x140011a7e  add     r10w, 2
0x140011a83  jmp     short loc_140011A57
0x140011a85  movsd   qword ptr [r8+2], xmm0
0x140011a8b  mov     rax, r9
0x140011a8e  mov     [r8+0Ah], r11d
0x140011a92  mov     [r8+0Eh], bx
0x140011a97  mov     rbx, [rsp+arg_0]
0x140011a9c  mov     [r8], r10w
0x140011aa0  mov     [r9+2], dx
0x140011aa5  retn
```
