# UaspParseConfigurationDescriptor

- ea: `0x140001ec8`
- end: `0x140002067`
- name: `UaspParseConfigurationDescriptor`
- size: `415`
- prototype: `char __fastcall(__int64, unsigned __int8 *, _QWORD *, _BYTE *, _BYTE *, _BYTE *, _BYTE *, _DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140002130`

## callees

- `0x140001ec8`

## pseudocode

```c
char __fastcall UaspParseConfigurationDescriptor(
        __int64 a1,
        unsigned __int8 *a2,
        _QWORD *a3,
        _BYTE *a4,
        _BYTE *a5,
        _BYTE *a6,
        _BYTE *a7,
        _DWORD *a8)
{
  __int64 v8; // rax
  unsigned __int8 *v9; // rbx
  char v10; // r11
  unsigned __int64 v11; // r10
  unsigned __int8 *v14; // r9
  unsigned __int8 v15; // cl
  unsigned __int8 *v16; // r8
  __int64 v17; // rcx
  bool v18; // cf

  LOBYTE(v8) = (_BYTE)a2 + 2;
  v9 = 0;
  v10 = 0;
  v11 = (unsigned __int64)&a2[*((unsigned __int16 *)a2 + 1)];
  if ( (unsigned __int64)(a2 + 2) >= v11 )
    goto LABEL_44;
  while ( 1 )
  {
    v8 = *a2;
    v14 = &a2[v8];
    if ( (unsigned __int64)&a2[v8] > v11 )
      goto LABEL_44;
    v15 = a2[1];
    if ( v15 == 4 )
    {
      if ( (_BYTE)v8 == 9 )
      {
        if ( v9 )
          goto LABEL_44;
        if ( a2[3] == 1 )
          v9 = a2;
      }
      goto LABEL_41;
    }
    if ( v15 == 5 && (_BYTE)v8 == 7 && v9 )
      break;
LABEL_41:
    LOBYTE(v8) = (_BYTE)a2 + 2;
    if ( (unsigned __int64)(a2 + 2) < v11 )
    {
      v8 = *a2;
      if ( (_BYTE)v8 )
      {
        a2 += v8;
        LOBYTE(v8) = (_BYTE)a2 + 2;
        if ( (unsigned __int64)(a2 + 2) < v11 )
          continue;
      }
    }
    goto LABEL_44;
  }
  v16 = a2;
  while ( 1 )
  {
    a2 = v14;
    if ( (unsigned __int64)(v14 + 2) >= v11 )
      goto LABEL_40;
    v17 = *v14;
    v14 += v17;
    if ( (unsigned __int64)&a2[v17] > v11 )
      goto LABEL_40;
    LOBYTE(v8) = a2[1];
    if ( (_BYTE)v8 == 36 && (_BYTE)v17 == 4 )
      break;
    if ( (_BYTE)v8 == 48 )
    {
      if ( (_BYTE)v17 != 6 )
        goto LABEL_21;
      if ( (v16[3] & 3) == 2 && (a2[3] & 0x1F) != 0 )
        *a8 = (1 << (a2[3] & 0x1F)) - 1;
    }
    else
    {
      v18 = (_BYTE)v8 == 4;
      LOBYTE(v8) = v8 - 4;
      if ( v18 || (_BYTE)v8 == 1 )
        goto LABEL_40;
LABEL_21:
      if ( !(_BYTE)v17 )
        goto LABEL_44;
    }
  }
  switch ( a2[2] )
  {
    case 1u:
      LOBYTE(v8) = v16[3] & 3;
      if ( (_BYTE)v8 == 2 && (v16[2] & 0x80u) == 0 )
      {
        *a4 = v10;
        goto LABEL_40;
      }
      break;
    case 2u:
      LOBYTE(v8) = v16[3] & 3;
      if ( (_BYTE)v8 == 2 && (v16[2] & 0x80u) != 0 )
      {
        *a7 = v10;
        goto LABEL_40;
      }
      break;
    case 3u:
      LOBYTE(v8) = v16[3] & 3;
      if ( (_BYTE)v8 == 2 && (v16[2] & 0x80u) != 0 )
      {
        *a5 = v10;
        goto LABEL_40;
      }
      break;
    case 4u:
      LOBYTE(v8) = v16[3] & 3;
      if ( (_BYTE)v8 == 2 && (v16[2] & 0x80u) == 0 )
      {
        *a6 = v10;
LABEL_40:
        ++v10;
        goto LABEL_41;
      }
      break;
  }
LABEL_44:
  *a3 = v9;
  return v8;
}

```

## disassembly

```asm
0x140001ec8  push    rbx
0x140001eca  push    rbp
0x140001ecb  push    rsi
0x140001ecc  push    rdi
0x140001ecd  push    r12
0x140001ecf  push    r14
0x140001ed1  push    r15
0x140001ed3  lea     rax, [rdx+2]
0x140001ed7  xor     ebx, ebx
0x140001ed9  movzx   r10d, word ptr [rax]
0x140001edd  xor     r11b, r11b
0x140001ee0  add     r10, rdx
0x140001ee3  mov     rbp, r9
0x140001ee6  mov     rdi, r8
0x140001ee9  cmp     rax, r10
0x140001eec  jnb     loc_140002058
0x140001ef2  mov     r12, [rsp+38h+arg_38]
0x140001ef7  mov     rsi, [rsp+38h+arg_30]
0x140001efc  mov     r14, [rsp+38h+arg_28]
0x140001f01  mov     r15, [rsp+38h+arg_20]
0x140001f06  movzx   eax, byte ptr [rdx]
0x140001f09  lea     r9, [rax+rdx]
0x140001f0d  cmp     r9, r10
0x140001f10  ja      loc_140002058
0x140001f16  mov     cl, [rdx+1]
0x140001f19  cmp     cl, 4
0x140001f1c  jnz     short loc_140001F41
0x140001f1e  cmp     al, 9
0x140001f20  jnz     loc_140002038
0x140001f26  test    rbx, rbx
0x140001f29  jnz     loc_140002058
0x140001f2f  cmp     byte ptr [rdx+3], 1
0x140001f33  jnz     loc_140002038
0x140001f39  mov     rbx, rdx
0x140001f3c  jmp     loc_140002038
0x140001f41  cmp     cl, 5
0x140001f44  jnz     loc_140002038
0x140001f4a  cmp     al, 7
0x140001f4c  jnz     loc_140002038
0x140001f52  test    rbx, rbx
0x140001f55  jz      loc_140002038
0x140001f5b  mov     r8, rdx
0x140001f5e  jmp     short loc_140001FB8
0x140001f60  movzx   ecx, byte ptr [rdx]
0x140001f63  lea     r9, [rcx+rdx]
0x140001f67  cmp     r9, r10
0x140001f6a  ja      loc_140002035
0x140001f70  mov     al, [rdx+1]
0x140001f73  cmp     al, 24h ; '$'
0x140001f75  jnz     short loc_140001F7C
0x140001f77  cmp     cl, 4
0x140001f7a  jz      short loc_140001FC6
0x140001f7c  cmp     al, 30h ; '0'
0x140001f7e  jnz     short loc_140001FA6
0x140001f80  cmp     cl, 6
0x140001f83  jnz     short loc_140001FB0
0x140001f85  mov     al, [r8+3]
0x140001f89  and     al, 3
0x140001f8b  cmp     al, 2
0x140001f8d  jnz     short loc_140001FB8
0x140001f8f  mov     cl, [rdx+3]
0x140001f92  and     cl, 1Fh
0x140001f95  jbe     short loc_140001FB8
0x140001f97  mov     eax, 1
0x140001f9c  shl     eax, cl
0x140001f9e  dec     eax
0x140001fa0  mov     [r12], eax
0x140001fa4  jmp     short loc_140001FB8
0x140001fa6  sub     al, 4
0x140001fa8  cmp     al, 1
0x140001faa  jbe     loc_140002035
0x140001fb0  test    cl, cl
0x140001fb2  jz      loc_140002058
0x140001fb8  lea     rax, [r9+2]
0x140001fbc  mov     rdx, r9
0x140001fbf  cmp     rax, r10
0x140001fc2  jb      short loc_140001F60
0x140001fc4  jmp     short loc_140002035
0x140001fc6  movzx   ecx, byte ptr [rdx+2]
0x140001fca  sub     ecx, 1
0x140001fcd  jz      short loc_140002020
0x140001fcf  sub     ecx, 1
0x140001fd2  jz      short loc_14000200A
0x140001fd4  sub     ecx, 1
0x140001fd7  jz      short loc_140001FF4
0x140001fd9  cmp     ecx, 1
0x140001fdc  jnz     short loc_140002058
0x140001fde  mov     al, [r8+3]
0x140001fe2  and     al, 3
0x140001fe4  cmp     al, 2
0x140001fe6  jnz     short loc_140002058
0x140001fe8  cmp     byte ptr [r8+2], 0
0x140001fed  jl      short loc_140002058
0x140001fef  mov     [r14], r11b
0x140001ff2  jmp     short loc_140002035
0x140001ff4  mov     al, [r8+3]
0x140001ff8  and     al, 3
0x140001ffa  cmp     al, 2
0x140001ffc  jnz     short loc_140002058
0x140001ffe  cmp     byte ptr [r8+2], 0
0x140002003  jge     short loc_140002058
0x140002005  mov     [r15], r11b
0x140002008  jmp     short loc_140002035
0x14000200a  mov     al, [r8+3]
0x14000200e  and     al, 3
0x140002010  cmp     al, 2
0x140002012  jnz     short loc_140002058
0x140002014  cmp     byte ptr [r8+2], 0
0x140002019  jge     short loc_140002058
0x14000201b  mov     [rsi], r11b
0x14000201e  jmp     short loc_140002035
0x140002020  mov     al, [r8+3]
0x140002024  and     al, 3
0x140002026  cmp     al, 2
0x140002028  jnz     short loc_140002058
0x14000202a  cmp     byte ptr [r8+2], 0
0x14000202f  jl      short loc_140002058
0x140002031  mov     [rbp+0], r11b
0x140002035  inc     r11b
0x140002038  lea     rax, [rdx+2]
0x14000203c  cmp     rax, r10
0x14000203f  jnb     short loc_140002058
0x140002041  movzx   eax, byte ptr [rdx]
0x140002044  test    al, al
0x140002046  jz      short loc_140002058
0x140002048  add     rdx, rax
0x14000204b  lea     rax, [rdx+2]
0x14000204f  cmp     rax, r10
0x140002052  jb      loc_140001F06
0x140002058  mov     [rdi], rbx
0x14000205b  pop     r15
0x14000205d  pop     r14
0x14000205f  pop     r12
0x140002061  pop     rdi
0x140002062  pop     rsi
0x140002063  pop     rbp
0x140002064  pop     rbx
0x140002065  retn
```
