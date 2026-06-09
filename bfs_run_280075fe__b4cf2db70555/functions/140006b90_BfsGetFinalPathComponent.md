# BfsGetFinalPathComponent

- ea: `0x140006b90`
- end: `0x140006c1b`
- name: `BfsGetFinalPathComponent`
- size: `139`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x140009b9c`
- `0x140012478`

## callees

- `0x140006b90`

## pseudocode

```c
unsigned __int16 *__fastcall BfsGetFinalPathComponent(unsigned __int16 *a1, __int64 a2)
{
  unsigned __int64 v2; // r9
  unsigned __int64 v3; // r8
  _WORD *v4; // rax
  _WORD *v5; // rdx

  *(_OWORD *)a1 = *(_OWORD *)a2;
  v2 = *((_QWORD *)a1 + 1) + 2 * (((unsigned __int64)*a1 >> 1) - 1);
  v3 = *(_QWORD *)(a2 + 8);
  *((_QWORD *)a1 + 1) = v2;
  *a1 = 0;
  if ( v2 <= v3 )
  {
    v5 = (_WORD *)v2;
  }
  else
  {
    v4 = (_WORD *)v2;
    do
    {
      v5 = v4;
      if ( *v4 != 92 )
        break;
      v2 -= 2LL;
      *((_QWORD *)a1 + 1) = v2;
      v4 = (_WORD *)v2;
      v5 = (_WORD *)v2;
    }
    while ( v2 > v3 );
  }
  while ( (unsigned __int64)v5 > v3 )
  {
    if ( *v5 == 92 )
    {
      *((_QWORD *)a1 + 1) = v5 + 1;
      break;
    }
    if ( *v5 == 58 )
      *a1 = 0;
    else
      *a1 += 2;
    *((_QWORD *)a1 + 1) = --v5;
  }
  a1[1] = *a1;
  return a1;
}

```

## disassembly

```asm
0x140006b90  movups  xmm0, xmmword ptr [rdx]
0x140006b93  movdqu  xmmword ptr [rcx], xmm0
0x140006b97  mov     rax, [rcx+8]
0x140006b9b  movzx   r8d, word ptr [rcx]
0x140006b9f  shr     r8, 1
0x140006ba2  dec     r8
0x140006ba5  lea     r9, [rax+r8*2]
0x140006ba9  mov     r8, [rdx+8]
0x140006bad  xor     eax, eax
0x140006baf  mov     [rcx+8], r9
0x140006bb3  mov     [rcx], ax
0x140006bb6  cmp     r9, r8
0x140006bb9  jbe     short loc_140006BDC
0x140006bbb  mov     rax, r9
0x140006bbe  cmp     word ptr [rax], 5Ch ; '\'
0x140006bc2  mov     rdx, rax
0x140006bc5  jnz     short loc_140006BDF
0x140006bc7  add     r9, 0FFFFFFFFFFFFFFFEh
0x140006bcb  mov     [rcx+8], r9
0x140006bcf  mov     rax, r9
0x140006bd2  mov     rdx, r9
0x140006bd5  cmp     r9, r8
0x140006bd8  ja      short loc_140006BBE
0x140006bda  jmp     short loc_140006BDF
0x140006bdc  mov     rdx, r9
0x140006bdf  cmp     rdx, r8
0x140006be2  jbe     short loc_140006C10
0x140006be4  movzx   eax, word ptr [rdx]
0x140006be7  cmp     ax, 5Ch ; '\'
0x140006beb  jz      short loc_140006C08
0x140006bed  cmp     ax, 3Ah ; ':'
0x140006bf1  jnz     short loc_140006BFA
0x140006bf3  xor     eax, eax
0x140006bf5  mov     [rcx], ax
0x140006bf8  jmp     short loc_140006BFE
0x140006bfa  add     word ptr [rcx], 2
0x140006bfe  add     rdx, 0FFFFFFFFFFFFFFFEh
0x140006c02  mov     [rcx+8], rdx
0x140006c06  jmp     short loc_140006BDF
0x140006c08  lea     rax, [rdx+2]
0x140006c0c  mov     [rcx+8], rax
0x140006c10  movzx   eax, word ptr [rcx]
0x140006c13  mov     [rcx+2], ax
0x140006c17  mov     rax, rcx
0x140006c1a  retn
```
