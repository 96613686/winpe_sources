# WriteFixed

- ea: `0x180050c90`
- end: `0x180050dd8`
- name: `WriteFixed`
- size: `328`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180052f30`

## callees

- `0x180001ee0`
- `0x18004e048`
- `0x18004ed20`
- `0x18004f07c`
- `0x180050c90`
- `0x18005165c`

## pseudocode

```c
__int64 __fastcall WriteFixed(__int64 a1, int a2, unsigned int a3)
{
  unsigned __int16 v6; // ax
  int v7; // edx
  __int16 v8; // ax
  unsigned int v9; // ecx
  unsigned int v10; // eax
  __int64 v11; // r8
  unsigned int v12; // ecx
  unsigned int v13; // eax
  int v14; // edi
  int v15; // r10d
  int v16; // r11d
  unsigned int v17; // ecx
  int v18; // edx
  int v19; // ecx
  unsigned int v20; // eax
  _BYTE v22[32]; // [rsp+20h] [rbp-48h] BYREF

  if ( (_WORD)a2 )
  {
    v7 = -a2;
    v8 = v7;
    if ( a2 >= 0 )
      v8 = a2;
    v9 = (unsigned __int16)(10 * v8);
    v10 = 0x10000 - v9;
    if ( v9 <= 0x8000 )
      v10 = v9;
    if ( v10 >= 0x40 )
    {
      if ( a2 >= 0 )
        LOWORD(v7) = a2;
      v12 = (unsigned __int16)(100 * v7);
      v13 = 0x10000 - v12;
      if ( v12 <= 0x8000 )
        v13 = (unsigned __int16)(100 * v7);
      if ( v13 >= 0x40 )
      {
        v14 = 1;
        v15 = -a2;
        v16 = 0xFFFF;
        if ( a2 >= 0 )
          LOWORD(v15) = a2;
        v11 = 2;
        while ( 1 )
        {
          v17 = (unsigned __int16)(v11 * v15);
          v18 = 0x10000 - v17;
          if ( v17 <= 0x8000 )
            v18 = (unsigned __int16)(v11 * v15);
          if ( v18 < 64 )
            break;
          v19 = v16;
          v20 = v11;
          if ( v18 < v16 )
            v16 = v18;
          if ( v18 >= v19 )
            v20 = v14;
          v11 = (unsigned int)(v11 + 1);
          v14 = v20;
          if ( (int)v11 >= 200 )
          {
            v11 = v20;
            break;
          }
        }
      }
      else
      {
        v11 = 100;
      }
    }
    else
    {
      v11 = 10;
    }
    v6 = ConvertFixedDiv((unsigned int)a2, v22, v11);
  }
  else
  {
    v6 = IntToCharstr((unsigned int)(a2 >> 16), v22);
  }
  if ( !v6 )
    XCF_FatalErrorHandler(a1, 17);
  return WriteT1Data(a1, v22, v6, a3);
}

```

## disassembly

```asm
0x180050c90  mov     [rsp+arg_10], rbx
0x180050c95  push    rbp
0x180050c96  push    rsi
0x180050c97  push    rdi
0x180050c98  sub     rsp, 50h
0x180050c9c  mov     rax, cs:__security_cookie
0x180050ca3  xor     rax, rsp
0x180050ca6  mov     [rsp+68h+var_28], rax
0x180050cab  mov     esi, r8d
0x180050cae  mov     r9d, edx
0x180050cb1  mov     rbx, rcx
0x180050cb4  test    dx, dx
0x180050cb7  jnz     short loc_180050CCF
0x180050cb9  sar     r9d, 10h
0x180050cbd  lea     rdx, [rsp+68h+var_48]
0x180050cc2  mov     ecx, r9d
0x180050cc5  call    IntToCharstr
0x180050cca  jmp     loc_180050D97
0x180050ccf  neg     edx
0x180050cd1  test    r9d, r9d
0x180050cd4  mov     eax, edx
0x180050cd6  cmovns  eax, r9d
0x180050cda  lea     eax, [rax+rax*4]
0x180050cdd  add     eax, eax
0x180050cdf  movzx   ecx, ax
0x180050ce2  mov     eax, 10000h
0x180050ce7  sub     eax, ecx
0x180050ce9  cmp     ecx, 8000h
0x180050cef  cmovbe  eax, ecx
0x180050cf2  cmp     eax, 40h ; '@'
0x180050cf5  jnb     short loc_180050D02
0x180050cf7  mov     r8d, 0Ah
0x180050cfd  jmp     loc_180050D8A
0x180050d02  test    r9d, r9d
0x180050d05  cmovns  edx, r9d
0x180050d09  imul    eax, edx, 64h ; 'd'
0x180050d0c  movzx   ecx, ax
0x180050d0f  mov     eax, 10000h
0x180050d14  sub     eax, ecx
0x180050d16  cmp     ecx, 8000h
0x180050d1c  cmovbe  eax, ecx
0x180050d1f  cmp     eax, 40h ; '@'
0x180050d22  jnb     short loc_180050D2C
0x180050d24  mov     r8d, 64h ; 'd'
0x180050d2a  jmp     short loc_180050D8A
0x180050d2c  mov     r10d, r9d
0x180050d2f  mov     edi, 1
0x180050d34  neg     r10d
0x180050d37  mov     r11d, 0FFFFh
0x180050d3d  test    r9d, r9d
0x180050d40  cmovns  r10d, r9d
0x180050d44  lea     r8d, [rdi+1]
0x180050d48  mov     eax, r10d
0x180050d4b  mov     edx, 10000h
0x180050d50  imul    eax, r8d
0x180050d54  movzx   ecx, ax
0x180050d57  sub     edx, ecx
0x180050d59  cmp     ecx, 8000h
0x180050d5f  cmovbe  edx, ecx
0x180050d62  cmp     edx, 40h ; '@'
0x180050d65  jl      short loc_180050D8A
0x180050d67  cmp     edx, r11d
0x180050d6a  mov     ecx, r11d
0x180050d6d  mov     eax, r8d
0x180050d70  cmovl   r11d, edx
0x180050d74  cmp     edx, ecx
0x180050d76  cmovge  eax, edi
0x180050d79  inc     r8d
0x180050d7c  mov     edi, eax
0x180050d7e  cmp     r8d, 0C8h
0x180050d85  jl      short loc_180050D48
0x180050d87  mov     r8d, eax
0x180050d8a  lea     rdx, [rsp+68h+var_48]
0x180050d8f  mov     ecx, r9d
0x180050d92  call    ConvertFixedDiv
0x180050d97  mov     rcx, rbx
0x180050d9a  test    ax, ax
0x180050d9d  jz      short loc_180050DCD
0x180050d9f  movzx   r8d, ax
0x180050da3  lea     rdx, [rsp+68h+var_48]
0x180050da8  mov     r9d, esi
0x180050dab  call    WriteT1Data
0x180050db0  mov     rcx, [rsp+68h+var_28]
0x180050db5  xor     rcx, rsp; StackCookie
0x180050db8  call    __security_check_cookie
0x180050dbd  mov     rbx, [rsp+68h+arg_10]
0x180050dc5  add     rsp, 50h
0x180050dc9  pop     rdi
0x180050dca  pop     rsi
0x180050dcb  pop     rbp
0x180050dcc  retn
0x180050dcd  mov     edx, 11h
0x180050dd2  call    XCF_FatalErrorHandler
```
