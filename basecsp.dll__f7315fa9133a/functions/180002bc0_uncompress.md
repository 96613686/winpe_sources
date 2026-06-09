# uncompress

- ea: `0x180002bc0`
- end: `0x180002d30`
- name: `uncompress`
- size: `368`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180027f78`

## callees

- `0x180002bc0`
- `0x180002d40`
- `0x1800045d0`
- `0x180004900`

## pseudocode

```c
__int64 __fastcall uncompress(char *a1, _DWORD *a2, unsigned __int8 *a3, unsigned int a4)
{
  unsigned __int64 v4; // r14
  unsigned __int64 v6; // rsi
  unsigned int v7; // ebx
  char *v8; // rbp
  int v9; // eax
  unsigned __int64 v10; // rdi
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // r15
  unsigned __int8 *v15; // [rsp+20h] [rbp-88h] BYREF
  unsigned int v16; // [rsp+28h] [rbp-80h]
  char *v17; // [rsp+30h] [rbp-78h]
  int i; // [rsp+38h] [rbp-70h]
  __int64 v19; // [rsp+50h] [rbp-58h]
  __int64 v20; // [rsp+58h] [rbp-50h]
  __int64 v21; // [rsp+60h] [rbp-48h]
  char v22; // [rsp+70h] [rbp-38h] BYREF

  v4 = (unsigned int)*a2;
  v6 = a4;
  if ( (!a4 || a3) && (!*a2 || a1) )
  {
    if ( *a2 )
    {
      v8 = a1;
    }
    else
    {
      v8 = &v22;
      if ( a1 )
        v8 = a1;
    }
    v15 = a3;
    v16 = 0;
    v19 = 0;
    v20 = 0;
    v21 = 0;
    v7 = inflateInit_(&v15, "1.3.2", 88);
    if ( !v7 )
    {
      v9 = 0;
      v17 = v8;
      v10 = v4;
      for ( i = 0; ; v9 = i )
      {
        if ( !v9 )
        {
          v11 = (unsigned int)v10;
          if ( v10 > 0xFFFFFFFF )
            v11 = 0xFFFFFFFFLL;
          i = v11;
          v10 -= v11;
        }
        if ( !v16 )
        {
          v12 = (unsigned int)v6;
          if ( v6 > 0xFFFFFFFF )
            v12 = 0xFFFFFFFFLL;
          v16 = v12;
          v6 -= v12;
        }
        v7 = inflate(&v15, 0);
        if ( v7 )
          break;
      }
      v13 = v16;
      LODWORD(v4) = v4 - (v10 + i);
      inflateEnd(&v15);
      if ( v7 == 1 )
      {
        v7 = 0;
      }
      else if ( v7 == 2 || v7 == -5 && !(v13 + v6) )
      {
        v7 = -3;
      }
    }
  }
  else
  {
    v7 = -2;
  }
  *a2 = v4;
  return v7;
}

```

## disassembly

```asm
0x180002bc0  push    rbx
0x180002bc2  push    rsi
0x180002bc3  push    r12
0x180002bc5  push    r14
0x180002bc7  sub     rsp, 88h
0x180002bce  mov     r14d, [rdx]
0x180002bd1  mov     r12, rdx
0x180002bd4  mov     esi, r9d
0x180002bd7  test    r9d, r9d
0x180002bda  jz      short loc_180002BE1
0x180002bdc  test    r8, r8
0x180002bdf  jz      short loc_180002BEB
0x180002be1  test    r14, r14
0x180002be4  jz      short loc_180002BF5
0x180002be6  test    rcx, rcx
0x180002be9  jnz     short loc_180002BF5
0x180002beb  mov     ebx, 0FFFFFFFEh
0x180002bf0  jmp     loc_180002D1C
0x180002bf5  mov     [rsp+0A8h+arg_0], rbp
0x180002bfd  mov     [rsp+0A8h+arg_10], r13
0x180002c05  test    r14, r14
0x180002c08  jnz     short loc_180002C18
0x180002c0a  test    rcx, rcx
0x180002c0d  lea     rbp, [rsp+0A8h+var_38]
0x180002c12  cmovnz  rbp, rcx
0x180002c16  jmp     short loc_180002C1B
0x180002c18  mov     rbp, rcx
0x180002c1b  xor     r13d, r13d
0x180002c1e  mov     [rsp+0A8h+var_88], r8
0x180002c23  mov     r8d, 58h ; 'X'
0x180002c29  mov     [rsp+0A8h+var_80], r13d
0x180002c2e  lea     rdx, a132; "1.3.2"
0x180002c35  mov     [rsp+0A8h+var_58], r13
0x180002c3a  lea     rcx, [rsp+0A8h+var_88]
0x180002c3f  mov     [rsp+0A8h+var_50], r13
0x180002c44  mov     [rsp+0A8h+var_48], r13
0x180002c49  call    inflateInit_
0x180002c4e  mov     ebx, eax
0x180002c50  test    eax, eax
0x180002c52  jnz     loc_180002D0C
0x180002c58  mov     [rsp+0A8h+arg_8], rdi
0x180002c60  mov     eax, r13d
0x180002c63  mov     [rsp+0A8h+var_78], rbp
0x180002c68  mov     rdi, r14
0x180002c6b  mov     [rsp+0A8h+var_70], eax
0x180002c6f  mov     ebp, 0FFFFFFFFh
0x180002c74  mov     [rsp+0A8h+var_28], r15
0x180002c7c  nop     dword ptr [rax+00h]
0x180002c80  test    eax, eax
0x180002c82  jnz     short loc_180002C93
0x180002c84  cmp     rdi, rbp
0x180002c87  mov     eax, edi
0x180002c89  cmova   eax, ebp
0x180002c8c  mov     [rsp+0A8h+var_70], eax
0x180002c90  sub     rdi, rax
0x180002c93  cmp     [rsp+0A8h+var_80], r13d
0x180002c98  jnz     short loc_180002CA9
0x180002c9a  cmp     rsi, rbp
0x180002c9d  mov     eax, esi
0x180002c9f  cmova   eax, ebp
0x180002ca2  mov     [rsp+0A8h+var_80], eax
0x180002ca6  sub     rsi, rax
0x180002ca9  xor     edx, edx
0x180002cab  lea     rcx, [rsp+0A8h+var_88]
0x180002cb0  call    inflate
0x180002cb5  mov     ebx, eax
0x180002cb7  test    eax, eax
0x180002cb9  jnz     short loc_180002CC1
0x180002cbb  mov     eax, [rsp+0A8h+var_70]
0x180002cbf  jmp     short loc_180002C80
0x180002cc1  mov     eax, [rsp+0A8h+var_70]
0x180002cc5  lea     rcx, [rsp+0A8h+var_88]
0x180002cca  mov     r15d, [rsp+0A8h+var_80]
0x180002ccf  add     rax, rdi
0x180002cd2  sub     r14, rax
0x180002cd5  call    inflateEnd
0x180002cda  mov     rdi, [rsp+0A8h+arg_8]
0x180002ce2  cmp     ebx, 1
0x180002ce5  jnz     short loc_180002CEC
0x180002ce7  mov     ebx, r13d
0x180002cea  jmp     short loc_180002D04
0x180002cec  cmp     ebx, 2
0x180002cef  jz      short loc_180002CFF
0x180002cf1  cmp     ebx, 0FFFFFFFBh
0x180002cf4  jnz     short loc_180002D04
0x180002cf6  lea     rax, [r15+rsi]
0x180002cfa  test    rax, rax
0x180002cfd  jnz     short loc_180002D04
0x180002cff  mov     ebx, 0FFFFFFFDh
0x180002d04  mov     r15, [rsp+0A8h+var_28]
0x180002d0c  mov     rbp, [rsp+0A8h+arg_0]
0x180002d14  mov     r13, [rsp+0A8h+arg_10]
0x180002d1c  mov     [r12], r14d
0x180002d20  mov     eax, ebx
0x180002d22  add     rsp, 88h
0x180002d29  pop     r14
0x180002d2b  pop     r12
0x180002d2d  pop     rsi
0x180002d2e  pop     rbx
0x180002d2f  retn
```
