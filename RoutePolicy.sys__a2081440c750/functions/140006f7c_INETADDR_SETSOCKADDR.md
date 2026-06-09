# INETADDR_SETSOCKADDR

- ea: `0x140006f7c`
- end: `0x140007049`
- name: `INETADDR_SETSOCKADDR`
- size: `205`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140007280`
- `0x140009b00`

## callees

- `0x140006f7c`
- `0x140007050`

## pseudocode

```c
__int64 __fastcall INETADDR_SETSOCKADDR(__int16 a1, __int64 a2, __int128 *a3, int a4, __int16 a5)
{
  _OWORD *v5; // r10
  __int128 v7; // xmm0
  int v8; // ecx
  _WORD *v9; // r10
  unsigned int v10; // r11d
  __int64 result; // rax
  int v12; // ecx

  v5 = (_OWORD *)(a2 + 8);
  if ( a1 == 23 )
  {
    *(_WORD *)a2 = 23;
    *(_WORD *)(a2 + 2) = a5;
    *(_DWORD *)(a2 + 4) = 0;
    v7 = *a3;
    *(_DWORD *)(a2 + 24) = a4;
    *v5 = v7;
    v8 = Ipv6AddressScope(a2 + 8);
    if ( !*v9 && !v9[1] && !v9[2] && !v9[3] && !v9[4] && !v9[5] && !v9[6] && v9[7] == 256 || v8 == 14 )
    {
      *(_DWORD *)(a2 + 24) = 0;
      v10 = 0;
    }
    result = v10 >> 28;
    if ( (_DWORD)result == v8 )
      *(_DWORD *)(a2 + 24) = v10 & 0xFFFFFFF;
  }
  else
  {
    v12 = *(_DWORD *)a3;
    *(_WORD *)(a2 + 2) = a5;
    result = 0;
    *(_WORD *)a2 = 2;
    *(_DWORD *)(a2 + 4) = v12;
    *(_QWORD *)v5 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x140006f7c  mov     [rsp+arg_0], rbx
0x140006f81  push    rdi
0x140006f82  sub     rsp, 20h
0x140006f86  mov     eax, 17h
0x140006f8b  lea     r10, [rdx+8]
0x140006f8f  mov     r11d, r9d
0x140006f92  mov     rbx, rdx
0x140006f95  cmp     cx, ax
0x140006f98  jnz     loc_140007024
0x140006f9e  mov     [rdx], ax
0x140006fa1  xor     edi, edi
0x140006fa3  movzx   eax, [rsp+28h+arg_20]
0x140006fa8  mov     rcx, r10
0x140006fab  mov     [rdx+2], ax
0x140006faf  mov     [rdx+4], edi
0x140006fb2  movups  xmm0, xmmword ptr [r8]
0x140006fb6  mov     [rdx+18h], r9d
0x140006fba  movdqu  xmmword ptr [r10], xmm0
0x140006fbf  call    Ipv6AddressScope
0x140006fc4  mov     ecx, eax
0x140006fc6  cmp     [r10], di
0x140006fca  jnz     short loc_140007002
0x140006fcc  cmp     [r10+2], di
0x140006fd1  jnz     short loc_140007002
0x140006fd3  cmp     [r10+4], di
0x140006fd8  jnz     short loc_140007002
0x140006fda  cmp     [r10+6], di
0x140006fdf  jnz     short loc_140007002
0x140006fe1  cmp     [r10+8], di
0x140006fe6  jnz     short loc_140007002
0x140006fe8  cmp     [r10+0Ah], di
0x140006fed  jnz     short loc_140007002
0x140006fef  cmp     [r10+0Ch], di
0x140006ff4  jnz     short loc_140007002
0x140006ff6  mov     eax, 100h
0x140006ffb  cmp     [r10+0Eh], ax
0x140007000  jz      short loc_140007007
0x140007002  cmp     ecx, 0Eh
0x140007005  jnz     short loc_14000700D
0x140007007  mov     [rbx+18h], edi
0x14000700a  mov     r11d, edi
0x14000700d  mov     eax, r11d
0x140007010  shr     eax, 1Ch
0x140007013  cmp     eax, ecx
0x140007015  jnz     short loc_14000703D
0x140007017  and     r11d, 0FFFFFFFh
0x14000701e  mov     [rbx+18h], r11d
0x140007022  jmp     short loc_14000703D
0x140007024  mov     ecx, [r8]
0x140007027  movzx   eax, [rsp+28h+arg_20]
0x14000702c  mov     [rdx+2], ax
0x140007030  xor     eax, eax
0x140007032  mov     word ptr [rdx], 2
0x140007037  mov     [rdx+4], ecx
0x14000703a  mov     [r10], rax
0x14000703d  mov     rbx, [rsp+28h+arg_0]
0x140007042  add     rsp, 20h
0x140007046  pop     rdi
0x140007047  retn
```
