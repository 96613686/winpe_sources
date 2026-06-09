# ReconstituteVariantData(uchar const *,ulong,ushort,tagVARIANT *)

- ea: `0x1800c8bd0`
- end: `0x1800c8e4f`
- name: `?ReconstituteVariantData@@YAJPEBEKGPEAUtagVARIANT@@@Z`
- size: `639`
- prototype: `__int64 __fastcall(const unsigned __int8 *Src, size_t Size, unsigned __int16, struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800d6df0`

## callees

- `0x180044ac6`
- `0x1800c8bd0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800c8cbc`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800c8cbc`
- `OLEAUT32!__imp_VariantInit` at `0x1800c8c0c`
- `OLEAUT32!__imp_VariantInit` at `0x1800c8c0c`
- `OLEAUT32!__imp_VariantClear` at `0x1800c8e26`
- `OLEAUT32!__imp_VariantClear` at `0x1800c8e26`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800c8da3`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800c8da3`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800c8dc2`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800c8dc2`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800c8d80`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800c8d80`

## pseudocode

```c
__int64 __fastcall ReconstituteVariantData(BYTE *Src, size_t Size, VARTYPE a3, struct tagVARIANT *a4)
{
  size_t v4; // r14
  HRESULT v8; // ebx
  char v9; // r9
  unsigned int v10; // r8d
  BSTR v11; // rax
  SAFEARRAY *Vector; // rax
  SAFEARRAY *v13; // rbp
  unsigned int v14; // r8d
  unsigned int v15; // r8d
  unsigned int v16; // r8d
  unsigned int v17; // r8d
  void *ppvData; // [rsp+40h] [rbp+8h] BYREF

  v4 = (unsigned int)Size;
  if ( !Src || !a4 )
    return 2147500035LL;
  if ( (_DWORD)Size )
  {
    VariantInit(a4);
    a4->vt = a3;
    if ( (a3 & 0x4000) == 0 )
    {
      v8 = 0;
      v9 = 0;
      if ( (a3 & 0x2000) != 0 )
      {
        a4->llVal = 0;
        a3 &= ~0x2000u;
        v9 = 1;
      }
      if ( a3 > 0xEu )
      {
        if ( a3 == 16 || a3 == 17 )
        {
          v10 = 1;
          goto LABEL_37;
        }
        if ( a3 == 18 )
          goto LABEL_18;
        if ( a3 != 19 )
        {
          if ( a3 == 20 || a3 == 21 )
            goto LABEL_34;
          if ( (unsigned int)a3 - 22 >= 2 )
            goto LABEL_33;
        }
      }
      else
      {
        switch ( a3 )
        {
          case 0xEu:
            v10 = 16;
            goto LABEL_37;
          case 0u:
          case 1u:
            v8 = v9 != 0 ? 0x80070057 : 0;
            if ( !v9 )
              return (unsigned int)v8;
            goto LABEL_57;
          case 2u:
LABEL_18:
            v10 = 2;
LABEL_37:
            if ( !((unsigned int)v4 % v10) && 0xFFFFFFFF / v10 >= (unsigned int)v4 )
            {
              if ( !v9 )
              {
                v14 = v10 - 1;
                if ( v14 )
                {
                  v15 = v14 - 1;
                  if ( v15 )
                  {
                    v16 = v15 - 2;
                    if ( v16 )
                    {
                      v17 = v16 - 4;
                      if ( v17 )
                      {
                        if ( v17 != 8 )
                        {
                          v8 = -2147418113;
                          goto LABEL_57;
                        }
                        *(_OWORD *)&a4->vt = *(_OWORD *)Src;
                      }
                      else
                      {
                        a4->llVal = *(_QWORD *)Src;
                      }
                    }
                    else
                    {
                      a4->lVal = *(_DWORD *)Src;
                    }
                  }
                  else
                  {
                    a4->iVal = *(_WORD *)Src;
                  }
                }
                else
                {
                  a4->bVal = *Src;
                }
LABEL_54:
                if ( v8 < 0 )
                  goto LABEL_57;
                return (unsigned int)v8;
              }
              Vector = SafeArrayCreateVector(a3, 0, (unsigned int)v4 / v10);
              v13 = Vector;
              if ( Vector )
              {
                a4->llVal = (LONGLONG)Vector;
                ppvData = 0;
                v8 = SafeArrayAccessData(Vector, &ppvData);
                if ( v8 >= 0 )
                {
                  memcpy_0(ppvData, Src, v4);
                  v8 = SafeArrayUnaccessData(v13);
                  goto LABEL_54;
                }
LABEL_57:
                VariantClear(a4);
                return (unsigned int)v8;
              }
LABEL_22:
              v8 = -2147024882;
              goto LABEL_57;
            }
            goto LABEL_56;
        }
        if ( a3 != 3 && a3 != 4 )
        {
          if ( a3 != 5 && a3 != 7 )
          {
            if ( a3 == 8 )
            {
              if ( !v9 )
              {
                a4->llVal = 0;
                if ( (v4 & 1) == 0 )
                {
                  v11 = SysAllocStringLen((const OLECHAR *)Src, (unsigned int)v4 >> 1);
                  a4->llVal = (LONGLONG)v11;
                  if ( v11 )
                    return (unsigned int)v8;
                  goto LABEL_22;
                }
              }
LABEL_56:
              v8 = -2147024809;
              goto LABEL_57;
            }
            if ( a3 == 11 )
              goto LABEL_18;
LABEL_33:
            v8 = -2147352571;
            a4->vt = 0;
            goto LABEL_57;
          }
LABEL_34:
          v10 = 8;
          goto LABEL_37;
        }
      }
      v10 = 4;
      goto LABEL_37;
    }
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x1800c8bd0  mov     [rsp+arg_8], rbx
0x1800c8bd5  mov     [rsp+arg_10], rbp
0x1800c8bda  push    rsi
0x1800c8bdb  push    rdi
0x1800c8bdc  push    r14
0x1800c8bde  sub     rsp, 20h
0x1800c8be2  mov     r14d, edx
0x1800c8be5  mov     rdi, r9
0x1800c8be8  movzx   ebp, r8w
0x1800c8bec  mov     rsi, rcx
0x1800c8bef  test    rcx, rcx
0x1800c8bf2  jz      loc_1800C8E37
0x1800c8bf8  test    r9, r9
0x1800c8bfb  jz      loc_1800C8E37
0x1800c8c01  test    edx, edx
0x1800c8c03  jz      loc_1800C8E30
0x1800c8c09  mov     rcx, r9; pvarg
0x1800c8c0c  call    cs:__imp_VariantInit
0x1800c8c12  bt      bp, 0Eh
0x1800c8c17  mov     [rdi], bp
0x1800c8c1a  jb      loc_1800C8E30
0x1800c8c20  xor     ebx, ebx
0x1800c8c22  xor     r9b, r9b
0x1800c8c25  bt      bp, 0Dh
0x1800c8c2a  jnb     short loc_1800C8C3B
0x1800c8c2c  mov     eax, 0DFFFh
0x1800c8c31  mov     [rdi+8], rbx
0x1800c8c35  and     bp, ax
0x1800c8c38  mov     r9b, 1
0x1800c8c3b  movzx   ecx, bp
0x1800c8c3e  cmp     ecx, 0Eh
0x1800c8c41  ja      loc_1800C8CFD
0x1800c8c47  jz      loc_1800C8CF5
0x1800c8c4d  test    ecx, ecx
0x1800c8c4f  jz      loc_1800C8CD9
0x1800c8c55  sub     ecx, 1
0x1800c8c58  jz      short loc_1800C8CD9
0x1800c8c5a  sub     ecx, 1
0x1800c8c5d  jz      short loc_1800C8C91
0x1800c8c5f  sub     ecx, 1
0x1800c8c62  jz      loc_1800C8D3C
0x1800c8c68  sub     ecx, 1
0x1800c8c6b  jz      loc_1800C8D3C
0x1800c8c71  sub     ecx, 1
0x1800c8c74  jz      loc_1800C8D34
0x1800c8c7a  sub     ecx, 2
0x1800c8c7d  jz      loc_1800C8D34
0x1800c8c83  sub     ecx, 1
0x1800c8c86  jz      short loc_1800C8C9C
0x1800c8c88  cmp     ecx, 3
0x1800c8c8b  jnz     loc_1800C8D25
0x1800c8c91  mov     r8d, 2
0x1800c8c97  jmp     loc_1800C8D4A
0x1800c8c9c  test    r9b, r9b
0x1800c8c9f  jnz     loc_1800C8E1E
0x1800c8ca5  mov     [rdi+8], rbx
0x1800c8ca9  test    r14b, 1
0x1800c8cad  ja      loc_1800C8E1E
0x1800c8cb3  shr     r14d, 1
0x1800c8cb6  mov     rcx, rsi; strIn
0x1800c8cb9  mov     edx, r14d; ui
0x1800c8cbc  call    cs:__imp_SysAllocStringLen
0x1800c8cc2  mov     [rdi+8], rax
0x1800c8cc6  test    rax, rax
0x1800c8cc9  jnz     loc_1800C8E2C
0x1800c8ccf  mov     ebx, 8007000Eh
0x1800c8cd4  jmp     loc_1800C8E23
0x1800c8cd9  mov     al, r9b
0x1800c8cdc  mov     ebx, 80070057h
0x1800c8ce1  neg     al
0x1800c8ce3  sbb     ecx, ecx
0x1800c8ce5  and     ebx, ecx
0x1800c8ce7  test    r9b, r9b
0x1800c8cea  jz      loc_1800C8E2C
0x1800c8cf0  jmp     loc_1800C8E23
0x1800c8cf5  mov     r8d, 10h
0x1800c8cfb  jmp     short loc_1800C8D4A
0x1800c8cfd  sub     ecx, 10h
0x1800c8d00  jz      short loc_1800C8D44
0x1800c8d02  sub     ecx, 1
0x1800c8d05  jz      short loc_1800C8D44
0x1800c8d07  sub     ecx, 1
0x1800c8d0a  jz      short loc_1800C8C91
0x1800c8d0c  sub     ecx, 1
0x1800c8d0f  jz      short loc_1800C8D3C
0x1800c8d11  sub     ecx, 1
0x1800c8d14  jz      short loc_1800C8D34
0x1800c8d16  sub     ecx, 1
0x1800c8d19  jz      short loc_1800C8D34
0x1800c8d1b  sub     ecx, 1
0x1800c8d1e  jz      short loc_1800C8D3C
0x1800c8d20  cmp     ecx, 1
0x1800c8d23  jz      short loc_1800C8D3C
0x1800c8d25  xor     eax, eax
0x1800c8d27  mov     ebx, 80020005h
0x1800c8d2c  mov     [rdi], ax
0x1800c8d2f  jmp     loc_1800C8E23
0x1800c8d34  mov     r8d, 8
0x1800c8d3a  jmp     short loc_1800C8D4A
0x1800c8d3c  mov     r8d, 4
0x1800c8d42  jmp     short loc_1800C8D4A
0x1800c8d44  mov     r8d, 1
0x1800c8d4a  xor     edx, edx
0x1800c8d4c  mov     eax, r14d
0x1800c8d4f  div     r8d
0x1800c8d52  test    edx, edx
0x1800c8d54  jnz     loc_1800C8E1E
0x1800c8d5a  xor     edx, edx
0x1800c8d5c  or      eax, 0FFFFFFFFh
0x1800c8d5f  div     r8d
0x1800c8d62  cmp     eax, r14d
0x1800c8d65  jb      loc_1800C8E1E
0x1800c8d6b  test    r9b, r9b
0x1800c8d6e  jz      short loc_1800C8DCC
0x1800c8d70  xor     edx, edx
0x1800c8d72  mov     eax, r14d
0x1800c8d75  div     r8d
0x1800c8d78  xor     edx, edx; lLbound
0x1800c8d7a  movzx   ecx, bp; vt
0x1800c8d7d  mov     r8d, eax; cElements
0x1800c8d80  call    cs:__imp_SafeArrayCreateVector
0x1800c8d86  mov     rbp, rax
0x1800c8d89  test    rax, rax
0x1800c8d8c  jz      loc_1800C8CCF
0x1800c8d92  lea     rdx, [rsp+38h+ppvData]; ppvData
0x1800c8d97  mov     [rdi+8], rax
0x1800c8d9b  mov     rcx, rax; psa
0x1800c8d9e  mov     [rsp+38h+ppvData], rbx
0x1800c8da3  call    cs:__imp_SafeArrayAccessData
0x1800c8da9  mov     ebx, eax
0x1800c8dab  test    eax, eax
0x1800c8dad  js      short loc_1800C8E23
0x1800c8daf  mov     rcx, [rsp+38h+ppvData]; void *
0x1800c8db4  mov     r8, r14; Size
0x1800c8db7  mov     rdx, rsi; Src
0x1800c8dba  call    memcpy_0
0x1800c8dbf  mov     rcx, rbp; psa
0x1800c8dc2  call    cs:__imp_SafeArrayUnaccessData
0x1800c8dc8  mov     ebx, eax
0x1800c8dca  jmp     short loc_1800C8E18
0x1800c8dcc  sub     r8d, 1
0x1800c8dd0  jz      short loc_1800C8E13
0x1800c8dd2  sub     r8d, 1
0x1800c8dd6  jz      short loc_1800C8E0A
0x1800c8dd8  sub     r8d, 2
0x1800c8ddc  jz      short loc_1800C8E03
0x1800c8dde  sub     r8d, 4
0x1800c8de2  jz      short loc_1800C8DFA
0x1800c8de4  cmp     r8d, 8
0x1800c8de8  jz      short loc_1800C8DF1
0x1800c8dea  mov     ebx, 8000FFFFh
0x1800c8def  jmp     short loc_1800C8E23
0x1800c8df1  movups  xmm0, xmmword ptr [rsi]
0x1800c8df4  movdqu  xmmword ptr [rdi], xmm0
0x1800c8df8  jmp     short loc_1800C8E18
0x1800c8dfa  mov     rax, [rsi]
0x1800c8dfd  mov     [rdi+8], rax
0x1800c8e01  jmp     short loc_1800C8E18
0x1800c8e03  mov     eax, [rsi]
0x1800c8e05  mov     [rdi+8], eax
0x1800c8e08  jmp     short loc_1800C8E18
0x1800c8e0a  movzx   eax, word ptr [rsi]
0x1800c8e0d  mov     [rdi+8], ax
0x1800c8e11  jmp     short loc_1800C8E18
0x1800c8e13  mov     al, [rsi]
0x1800c8e15  mov     [rdi+8], al
0x1800c8e18  test    ebx, ebx
0x1800c8e1a  jns     short loc_1800C8E2C
0x1800c8e1c  jmp     short loc_1800C8E23
0x1800c8e1e  mov     ebx, 80070057h
0x1800c8e23  mov     rcx, rdi; pvarg
0x1800c8e26  call    cs:__imp_VariantClear
0x1800c8e2c  mov     eax, ebx
0x1800c8e2e  jmp     short loc_1800C8E3C
0x1800c8e30  mov     eax, 80070057h
0x1800c8e35  jmp     short loc_1800C8E3C
0x1800c8e37  mov     eax, 80004003h
0x1800c8e3c  mov     rbx, [rsp+38h+arg_8]
0x1800c8e41  mov     rbp, [rsp+38h+arg_10]
0x1800c8e46  add     rsp, 20h
0x1800c8e4a  pop     r14
0x1800c8e4c  pop     rdi
0x1800c8e4d  pop     rsi
0x1800c8e4e  retn
```
