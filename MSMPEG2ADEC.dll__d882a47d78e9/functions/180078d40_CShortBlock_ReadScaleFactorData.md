# CShortBlock_ReadScaleFactorData

- ea: `0x180078d40`
- end: `0x180078f2e`
- name: `CShortBlock_ReadScaleFactorData`
- size: `494`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18007d4e0`

## callees

- `0x1800363f0`
- `0x180078d40`
- `0x18007edc0`

## pseudocode

```c
__int64 __fastcall CShortBlock_ReadScaleFactorData(int *a1, char *a2, unsigned __int8 a3)
{
  __int64 v3; // r12
  __int64 v5; // rcx
  int v6; // r13d
  __int64 result; // rax
  int v9; // ebp
  int v10; // eax
  __int64 v11; // r14
  int v12; // ecx
  int v13; // ecx
  unsigned int v14; // edi
  int v15; // ecx
  __int16 v16; // ax
  unsigned int v17; // edi
  int v18; // ecx
  __int64 v19; // [rsp+38h] [rbp-40h]
  int v20; // [rsp+88h] [rbp+10h]
  unsigned __int8 v21; // [rsp+90h] [rbp+18h]
  int v22; // [rsp+98h] [rbp+20h]

  v21 = a3;
  v3 = *(_QWORD *)a2;
  v5 = *((_QWORD *)a2 + 1);
  v6 = 0;
  result = a3;
  v19 = v5;
  v22 = 0;
  v20 = a3;
  if ( a2[33] > 0 )
  {
    while ( 1 )
    {
      v9 = 0;
      if ( a2[28] > 0 )
        break;
LABEL_21:
      result = (unsigned int)a2[33];
      if ( ++v6 >= (int)result )
        return result;
    }
    v10 = 16 * v6;
    while ( 1 )
    {
      v11 = v9 + v10;
      v12 = *(char *)(v11 + v5);
      if ( !v12 )
        break;
      v13 = v12 - 13;
      if ( v13 )
      {
        if ( (unsigned int)(v13 - 1) < 2 )
        {
          v17 = 0;
          do
          {
            if ( (unsigned int)*a1 < 4 )
              FillBitCache(a1, 4u);
            v18 = *a1 - 4;
            v17 = *((unsigned __int16 *)qword_1800A1E70 + v17 + (((unsigned int)a1[1] >> (*(_BYTE *)a1 - 4)) & 0xF));
            *a1 = v18;
          }
          while ( (v17 & 8) == 0 );
          a3 = v21;
          *a1 = v18 + (v17 & 3);
          v22 = (v17 >> 4) + v22 - 60;
          v16 = v22 - 100;
        }
        else
        {
          v14 = 0;
          do
          {
            if ( (unsigned int)*a1 < 4 )
              FillBitCache(a1, 4u);
            v15 = *a1 - 4;
            v14 = *((unsigned __int16 *)qword_1800A1E70 + v14 + (((unsigned int)a1[1] >> (*(_BYTE *)a1 - 4)) & 0xF));
            *a1 = v15;
          }
          while ( (v14 & 8) == 0 );
          a3 = v21;
          *a1 = v15 + (v14 & 3);
          v20 = (v14 >> 4) + v20 - 60;
          v16 = v20 - 100;
        }
        goto LABEL_19;
      }
      CPns_Read((_DWORD)a2, (_DWORD)a1, (unsigned int)&qword_18008B6D0, a3, v9, v6);
      a3 = v21;
LABEL_20:
      ++v9;
      v5 = v19;
      v10 = 16 * v6;
      if ( v9 >= a2[28] )
        goto LABEL_21;
    }
    v16 = 0;
LABEL_19:
    *(_WORD *)(v3 + 2 * v11) = v16;
    goto LABEL_20;
  }
  return result;
}

```

## disassembly

```asm
0x180078d40  mov     r11, rsp
0x180078d43  mov     [r11+18h], r8b
0x180078d47  push    rbx
0x180078d48  push    r12
0x180078d4a  push    r13
0x180078d4c  push    r15
0x180078d4e  sub     rsp, 58h
0x180078d52  mov     r12, [rdx]
0x180078d55  mov     rbx, rcx
0x180078d58  mov     rcx, [rdx+8]
0x180078d5c  xor     r13d, r13d
0x180078d5f  mov     r15, rdx
0x180078d62  movzx   eax, r8b
0x180078d66  mov     [rsp+78h+var_40], rcx
0x180078d6b  mov     [rsp+78h+arg_18], 0
0x180078d76  mov     [rsp+78h+arg_8], eax
0x180078d7d  cmp     [rdx+21h], r13b
0x180078d81  jle     loc_180078F21
0x180078d87  mov     [r11+8], rbp
0x180078d8b  mov     [r11-28h], rsi
0x180078d8f  mov     [r11-30h], rdi
0x180078d93  mov     [r11-38h], r14
0x180078d97  nop     word ptr [rax+rax+00000000h]
0x180078da0  xor     ebp, ebp
0x180078da2  cmp     [r15+1Ch], bpl
0x180078da6  jle     loc_180078EF9
0x180078dac  mov     eax, r13d
0x180078daf  shl     eax, 4
0x180078db2  mov     [rsp+78h+var_48], eax
0x180078db6  nop     word ptr [rax+rax+00000000h]
0x180078dc0  add     eax, ebp
0x180078dc2  movsxd  r14, eax
0x180078dc5  movsx   ecx, byte ptr [r14+rcx]
0x180078dca  test    ecx, ecx
0x180078dcc  jz      loc_180078EDA
0x180078dd2  sub     ecx, 0Dh
0x180078dd5  jz      loc_180078EB0
0x180078ddb  sub     ecx, 1
0x180078dde  jz      short loc_180078E4D
0x180078de0  cmp     ecx, 1
0x180078de3  jz      short loc_180078E4D
0x180078de5  mov     rsi, cs:off_18008B6D8
0x180078dec  xor     edi, edi
0x180078dee  xchg    ax, ax
0x180078df0  cmp     dword ptr [rbx], 4
0x180078df3  jnb     short loc_180078E02
0x180078df5  mov     edx, 4
0x180078dfa  mov     rcx, rbx
0x180078dfd  call    FillBitCache
0x180078e02  mov     ecx, [rbx]
0x180078e04  mov     eax, [rbx+4]
0x180078e07  add     ecx, 0FFFFFFFCh
0x180078e0a  shr     eax, cl
0x180078e0c  and     eax, 0Fh
0x180078e0f  add     eax, edi
0x180078e11  movzx   edi, word ptr [rsi+rax*2]
0x180078e15  mov     [rbx], ecx
0x180078e17  test    dil, 8
0x180078e1b  jz      short loc_180078DF0
0x180078e1d  movzx   r8d, [rsp+78h+arg_10]
0x180078e26  mov     eax, edi
0x180078e28  and     eax, 3
0x180078e2b  shr     edi, 4
0x180078e2e  add     eax, ecx
0x180078e30  mov     ecx, [rsp+78h+arg_8]
0x180078e37  add     ecx, 0FFFFFFC4h
0x180078e3a  mov     [rbx], eax
0x180078e3c  add     ecx, edi
0x180078e3e  mov     [rsp+78h+arg_8], ecx
0x180078e45  lea     eax, [rcx-64h]
0x180078e48  jmp     loc_180078EDC
0x180078e4d  mov     rsi, cs:off_18008B6D8
0x180078e54  xor     edi, edi
0x180078e56  cmp     dword ptr [rbx], 4
0x180078e59  jnb     short loc_180078E68
0x180078e5b  mov     edx, 4
0x180078e60  mov     rcx, rbx
0x180078e63  call    FillBitCache
0x180078e68  mov     ecx, [rbx]
0x180078e6a  mov     eax, [rbx+4]
0x180078e6d  add     ecx, 0FFFFFFFCh
0x180078e70  shr     eax, cl
0x180078e72  and     eax, 0Fh
0x180078e75  add     eax, edi
0x180078e77  movzx   edi, word ptr [rsi+rax*2]
0x180078e7b  mov     [rbx], ecx
0x180078e7d  test    dil, 8
0x180078e81  jz      short loc_180078E56
0x180078e83  movzx   r8d, [rsp+78h+arg_10]
0x180078e8c  mov     eax, edi
0x180078e8e  and     eax, 3
0x180078e91  shr     edi, 4
0x180078e94  add     eax, ecx
0x180078e96  mov     ecx, [rsp+78h+arg_18]
0x180078e9d  add     ecx, 0FFFFFFC4h
0x180078ea0  mov     [rbx], eax
0x180078ea2  add     ecx, edi
0x180078ea4  mov     [rsp+78h+arg_18], ecx
0x180078eab  lea     eax, [rcx-64h]
0x180078eae  jmp     short loc_180078EDC
0x180078eb0  movzx   r9d, r8b
0x180078eb4  mov     [rsp+78h+var_50], r13d
0x180078eb9  lea     r8, qword_18008B6D0
0x180078ec0  mov     [rsp+78h+var_58], ebp
0x180078ec4  mov     rdx, rbx
0x180078ec7  mov     rcx, r15
0x180078eca  call    CPns_Read
0x180078ecf  movzx   r8d, [rsp+78h+arg_10]
0x180078ed8  jmp     short loc_180078EE1
0x180078eda  xor     eax, eax
0x180078edc  mov     [r12+r14*2], ax
0x180078ee1  movsx   eax, byte ptr [r15+1Ch]
0x180078ee6  inc     ebp
0x180078ee8  mov     rcx, [rsp+78h+var_40]
0x180078eed  cmp     ebp, eax
0x180078eef  mov     eax, [rsp+78h+var_48]
0x180078ef3  jl      loc_180078DC0
0x180078ef9  movsx   eax, byte ptr [r15+21h]
0x180078efe  inc     r13d
0x180078f01  cmp     r13d, eax
0x180078f04  jl      loc_180078DA0
0x180078f0a  mov     r14, [rsp+78h+var_38]
0x180078f0f  mov     rdi, [rsp+78h+var_30]
0x180078f14  mov     rsi, [rsp+78h+var_28]
0x180078f19  mov     rbp, [rsp+78h+arg_0]
0x180078f21  add     rsp, 58h
0x180078f25  pop     r15
0x180078f27  pop     r13
0x180078f29  pop     r12
0x180078f2b  pop     rbx
0x180078f2c  retn
```
