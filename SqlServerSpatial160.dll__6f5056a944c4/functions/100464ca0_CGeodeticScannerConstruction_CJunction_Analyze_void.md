# CGeodeticScannerConstruction::CJunction::Analyze(void)

- ea: `0x100464ca0`
- end: `0x10046502e`
- name: `?Analyze@CJunction@CGeodeticScannerConstruction@@AEAAXXZ`
- size: `910`
- prototype: `void __fastcall(CGeodeticScannerConstruction::CJunction *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path`

## callers

- `0x100462e10`

## callees

- `0x100464ca0`

## pseudocode

```c
void __fastcall CGeodeticScannerConstruction::CJunction::Analyze(CGeodeticScannerConstruction::CJunction *this)
{
  __int64 v1; // r9
  unsigned int v2; // ebx
  __int64 v3; // r8
  int v4; // edx
  __int64 v5; // rax
  __int64 v6; // rdx
  __int64 v7; // r9
  __int64 v8; // r8
  int v9; // edx
  __int64 v10; // rax
  __int64 v11; // rdx
  unsigned int v12; // eax
  unsigned int i; // r11d
  __int64 v14; // r8
  char *v15; // r10
  char v16; // al
  char v17; // dl
  __int64 v18; // r9
  int v19; // edx
  __int64 v20; // rax
  __int64 v21; // rdx
  __int64 v22; // r9
  int v23; // edx
  __int64 v24; // rax
  __int64 v25; // rdx
  __int64 v26; // r9
  int v27; // edx
  __int64 v28; // rax
  __int64 v29; // rdx
  __int64 v30; // r9
  int v31; // edx
  __int64 v32; // rax
  __int64 v33; // rdx
  unsigned int v34; // r11d
  unsigned int v35; // r8d
  __int64 v36; // rdx
  char v37; // r9
  char v38; // si
  unsigned int v39; // edx
  __int64 v40; // r8
  char v41; // r9
  unsigned int v42; // r8d
  __int64 v43; // r9

  v1 = *((_QWORD *)this + 4);
  v2 = 0;
  if ( v1 )
  {
    v3 = *((_QWORD *)this + 8);
    if ( v3 )
    {
      v4 = *(_DWORD *)(v1 + 80);
      if ( *(_DWORD *)(v3 + 80) != v4 )
      {
        v5 = *((_QWORD *)this + 8);
        do
        {
          *(_DWORD *)(v5 + 80) = v4;
          v5 = *(_QWORD *)(v5 + 56);
        }
        while ( v5 != v3 );
        v6 = *(_QWORD *)(v3 + 56);
        *(_QWORD *)(v3 + 56) = *(_QWORD *)(v1 + 56);
        *(_QWORD *)(v1 + 56) = v6;
        v3 = *((_QWORD *)this + 8);
      }
      *(_BYTE *)(v3 + 85) |= 0x20u;
      *(_BYTE *)(*((_QWORD *)this + 4) + 85LL) |= 0x20u;
      *((_QWORD *)this + 8) = 0;
      *((_QWORD *)this + 4) = 0;
    }
  }
  v7 = *((_QWORD *)this + 2);
  if ( v7 )
  {
    v8 = *((_QWORD *)this + 6);
    if ( v8 )
    {
      v9 = *(_DWORD *)(v7 + 80);
      if ( *(_DWORD *)(v8 + 80) != v9 )
      {
        v10 = *((_QWORD *)this + 6);
        do
        {
          *(_DWORD *)(v10 + 80) = v9;
          v10 = *(_QWORD *)(v10 + 56);
        }
        while ( v10 != v8 );
        v11 = *(_QWORD *)(v8 + 56);
        *(_QWORD *)(v8 + 56) = *(_QWORD *)(v7 + 56);
        *(_QWORD *)(v7 + 56) = v11;
        v8 = *((_QWORD *)this + 6);
      }
      *(_BYTE *)(v8 + 85) |= 0x20u;
      *(_BYTE *)(*((_QWORD *)this + 2) + 85LL) |= 0x20u;
      *((_QWORD *)this + 6) = 0;
      *((_QWORD *)this + 2) = 0;
    }
  }
  v12 = *((_DWORD *)this + 40);
  for ( i = 0; i < v12; ++i )
  {
    v14 = *((_QWORD *)this + i + 10);
    v15 = (char *)this + 8 * i;
    v16 = *(_BYTE *)(v14 + 85);
    if ( (v16 & 4) != 0 )
    {
      v17 = *((_BYTE *)this + i + 168);
      if ( *(_BYTE *)(v14 + 84) )
      {
        if ( v17 )
        {
          v26 = *((_QWORD *)this + 2);
          if ( v26 )
          {
            v27 = *(_DWORD *)(v26 + 80);
            if ( *(_DWORD *)(v14 + 80) != v27 )
            {
              v28 = *((_QWORD *)this + i + 10);
              do
              {
                *(_DWORD *)(v28 + 80) = v27;
                v28 = *(_QWORD *)(v28 + 56);
              }
              while ( v28 != v14 );
              v29 = *(_QWORD *)(v14 + 56);
              *(_QWORD *)(v14 + 56) = *(_QWORD *)(v26 + 56);
              *(_QWORD *)(v26 + 56) = v29;
              v16 = *(_BYTE *)(v14 + 85);
            }
            *(_BYTE *)(v14 + 85) = v16 | 0x10;
            *(_BYTE *)(*((_QWORD *)this + 2) + 85LL) |= 0x20u;
            *((_QWORD *)this + 2) = *((_QWORD *)v15 + 10);
            goto LABEL_44;
          }
        }
        else
        {
          v30 = *((_QWORD *)this + 8);
          if ( v30 )
          {
            v31 = *(_DWORD *)(v30 + 80);
            if ( *(_DWORD *)(v14 + 80) != v31 )
            {
              v32 = *((_QWORD *)this + i + 10);
              do
              {
                *(_DWORD *)(v32 + 80) = v31;
                v32 = *(_QWORD *)(v32 + 56);
              }
              while ( v32 != v14 );
              v33 = *(_QWORD *)(v14 + 56);
              *(_QWORD *)(v14 + 56) = *(_QWORD *)(v30 + 56);
              *(_QWORD *)(v30 + 56) = v33;
              v16 = *(_BYTE *)(v14 + 85);
            }
            *(_BYTE *)(v14 + 85) = v16 | 0x10;
            *(_BYTE *)(*((_QWORD *)this + 8) + 85LL) |= 0x20u;
            *((_QWORD *)this + 8) = *((_QWORD *)v15 + 10);
            goto LABEL_44;
          }
        }
      }
      else if ( v17 )
      {
        v18 = *((_QWORD *)this + 4);
        if ( v18 )
        {
          v19 = *(_DWORD *)(v18 + 80);
          if ( *(_DWORD *)(v14 + 80) != v19 )
          {
            v20 = *((_QWORD *)this + i + 10);
            do
            {
              *(_DWORD *)(v20 + 80) = v19;
              v20 = *(_QWORD *)(v20 + 56);
            }
            while ( v20 != v14 );
            v21 = *(_QWORD *)(v14 + 56);
            *(_QWORD *)(v14 + 56) = *(_QWORD *)(v18 + 56);
            *(_QWORD *)(v18 + 56) = v21;
            v16 = *(_BYTE *)(v14 + 85);
          }
          *(_BYTE *)(v14 + 85) = v16 | 0x10;
          *(_BYTE *)(*((_QWORD *)this + 4) + 85LL) |= 0x20u;
          *((_QWORD *)this + 4) = *((_QWORD *)v15 + 10);
LABEL_44:
          *((_QWORD *)v15 + 10) = 0;
        }
      }
      else
      {
        v22 = *((_QWORD *)this + 6);
        if ( v22 )
        {
          v23 = *(_DWORD *)(v22 + 80);
          if ( *(_DWORD *)(v14 + 80) != v23 )
          {
            v24 = *((_QWORD *)this + i + 10);
            do
            {
              *(_DWORD *)(v24 + 80) = v23;
              v24 = *(_QWORD *)(v24 + 56);
            }
            while ( v24 != v14 );
            v25 = *(_QWORD *)(v14 + 56);
            *(_QWORD *)(v14 + 56) = *(_QWORD *)(v22 + 56);
            *(_QWORD *)(v22 + 56) = v25;
            v16 = *(_BYTE *)(v14 + 85);
          }
          *(_BYTE *)(v14 + 85) = v16 | 0x10;
          *(_BYTE *)(*((_QWORD *)this + 6) + 85LL) |= 0x20u;
          *((_QWORD *)this + 6) = *((_QWORD *)v15 + 10);
          goto LABEL_44;
        }
      }
    }
    v12 = *((_DWORD *)this + 40);
  }
  v34 = 0;
  if ( v12 )
  {
    v35 = v12;
    do
    {
      v12 = v35;
      v36 = *((_QWORD *)this + v34 + 10);
      if ( v36 )
      {
        v37 = *(_BYTE *)(v36 + 85);
        if ( (v37 & 4) != 0 )
        {
          if ( (v37 & 0x20) != 0 )
          {
            *((_QWORD *)this + v34 + 10) = 0;
            v12 = *((_DWORD *)this + 40);
          }
          else
          {
            v38 = *(_BYTE *)(v36 + 84);
            v39 = 0;
            if ( v35 )
            {
              do
              {
                if ( v39 != v34 )
                {
                  v40 = *((_QWORD *)this + v39 + 10);
                  if ( v40 )
                  {
                    v41 = *(_BYTE *)(v40 + 85);
                    if ( (v41 & 4) != 0
                      && *(_BYTE *)(v40 + 84) != v38
                      && *((_BYTE *)this + v39 + 168) != *((_BYTE *)this + v34 + 168) )
                    {
                      *(_BYTE *)(v40 + 85) = v41 | 0x20;
                      *((_QWORD *)this + v39 + 10) = 0;
                    }
                  }
                }
                v12 = *((_DWORD *)this + 40);
                ++v39;
              }
              while ( v39 < v12 );
            }
          }
        }
      }
      ++v34;
      v35 = v12;
    }
    while ( v34 < v12 );
  }
  v42 = 0;
  if ( v12 )
  {
    do
    {
      v43 = *((_QWORD *)this + v42 + 10);
      if ( v43 )
      {
        if ( v2 < v42 )
        {
          *((_QWORD *)this + v2 + 10) = v43;
          *((_BYTE *)this + v2 + 168) = *((_BYTE *)this + v42 + 168);
        }
        ++v2;
      }
      ++v42;
    }
    while ( v42 < *((_DWORD *)this + 40) );
  }
  *((_DWORD *)this + 40) = v2;
}

```

## disassembly

```asm
0x100464ca0  push    rbx
0x100464ca2  mov     r9, [rcx+20h]
0x100464ca6  xor     ebx, ebx
0x100464ca8  test    r9, r9
0x100464cab  jz      short loc_100464CF8
0x100464cad  mov     r8, [rcx+40h]
0x100464cb1  test    r8, r8
0x100464cb4  jz      short loc_100464CF8
0x100464cb6  mov     edx, [r9+50h]
0x100464cba  cmp     [r8+50h], edx
0x100464cbe  jz      short loc_100464CE3
0x100464cc0  mov     rax, r8
0x100464cc3  mov     [rax+50h], edx
0x100464cc6  mov     rax, [rax+38h]
0x100464cca  cmp     rax, r8
0x100464ccd  jnz     short loc_100464CC3
0x100464ccf  mov     rdx, [r8+38h]
0x100464cd3  mov     rax, [r9+38h]
0x100464cd7  mov     [r8+38h], rax
0x100464cdb  mov     [r9+38h], rdx
0x100464cdf  mov     r8, [rcx+40h]
0x100464ce3  or      byte ptr [r8+55h], 20h
0x100464ce8  mov     rax, [rcx+20h]
0x100464cec  or      byte ptr [rax+55h], 20h
0x100464cf0  mov     [rcx+40h], rbx
0x100464cf4  mov     [rcx+20h], rbx
0x100464cf8  mov     r9, [rcx+10h]
0x100464cfc  test    r9, r9
0x100464cff  jz      short loc_100464D55
0x100464d01  mov     r8, [rcx+30h]
0x100464d05  test    r8, r8
0x100464d08  jz      short loc_100464D55
0x100464d0a  mov     edx, [r9+50h]
0x100464d0e  cmp     [r8+50h], edx
0x100464d12  jz      short loc_100464D40
0x100464d14  mov     rax, r8
0x100464d17  nop     word ptr [rax+rax+00000000h]
0x100464d20  mov     [rax+50h], edx
0x100464d23  mov     rax, [rax+38h]
0x100464d27  cmp     rax, r8
0x100464d2a  jnz     short loc_100464D20
0x100464d2c  mov     rdx, [r8+38h]
0x100464d30  mov     rax, [r9+38h]
0x100464d34  mov     [r8+38h], rax
0x100464d38  mov     [r9+38h], rdx
0x100464d3c  mov     r8, [rcx+30h]
0x100464d40  or      byte ptr [r8+55h], 20h
0x100464d45  mov     rax, [rcx+10h]
0x100464d49  or      byte ptr [rax+55h], 20h
0x100464d4d  mov     [rcx+30h], rbx
0x100464d51  mov     [rcx+10h], rbx
0x100464d55  mov     eax, [rcx+0A0h]
0x100464d5b  mov     r11d, ebx
0x100464d5e  test    eax, eax
0x100464d60  jz      loc_100464F1D
0x100464d66  nop     word ptr [rax+rax+00000000h]
0x100464d70  mov     edx, r11d
0x100464d73  mov     r8, [rcx+rdx*8+50h]
0x100464d78  lea     r10, [rcx+rdx*8]
0x100464d7c  movzx   eax, byte ptr [r8+55h]
0x100464d81  test    al, 4
0x100464d83  jz      loc_100464F0B
0x100464d89  movzx   edx, byte ptr [rdx+rcx+0A8h]
0x100464d91  cmp     [r8+54h], bl
0x100464d95  jnz     loc_100464E5C
0x100464d9b  test    dl, dl
0x100464d9d  jz      short loc_100464DFC
0x100464d9f  mov     r9, [rcx+20h]
0x100464da3  test    r9, r9
0x100464da6  jz      loc_100464F0B
0x100464dac  mov     edx, [r9+50h]
0x100464db0  cmp     [r8+50h], edx
0x100464db4  jz      short loc_100464DE1
0x100464db6  mov     rax, r8
0x100464db9  nop     dword ptr [rax+00000000h]
0x100464dc0  mov     [rax+50h], edx
0x100464dc3  mov     rax, [rax+38h]
0x100464dc7  cmp     rax, r8
0x100464dca  jnz     short loc_100464DC0
0x100464dcc  mov     rax, [r9+38h]
0x100464dd0  mov     rdx, [r8+38h]
0x100464dd4  mov     [r8+38h], rax
0x100464dd8  mov     [r9+38h], rdx
0x100464ddc  movzx   eax, byte ptr [r8+55h]
0x100464de1  or      al, 10h
0x100464de3  mov     [r8+55h], al
0x100464de7  mov     rax, [rcx+20h]
0x100464deb  or      byte ptr [rax+55h], 20h
0x100464def  mov     rax, [r10+50h]
0x100464df3  mov     [rcx+20h], rax
0x100464df7  jmp     loc_100464F07
0x100464dfc  mov     r9, [rcx+30h]
0x100464e00  test    r9, r9
0x100464e03  jz      loc_100464F0B
0x100464e09  mov     edx, [r9+50h]
0x100464e0d  cmp     [r8+50h], edx
0x100464e11  jz      short loc_100464E41
0x100464e13  mov     rax, r8
0x100464e16  nop     word ptr [rax+rax+00000000h]
0x100464e20  mov     [rax+50h], edx
0x100464e23  mov     rax, [rax+38h]
0x100464e27  cmp     rax, r8
0x100464e2a  jnz     short loc_100464E20
0x100464e2c  mov     rax, [r9+38h]
0x100464e30  mov     rdx, [r8+38h]
0x100464e34  mov     [r8+38h], rax
0x100464e38  mov     [r9+38h], rdx
0x100464e3c  movzx   eax, byte ptr [r8+55h]
0x100464e41  or      al, 10h
0x100464e43  mov     [r8+55h], al
0x100464e47  mov     rax, [rcx+30h]
0x100464e4b  or      byte ptr [rax+55h], 20h
0x100464e4f  mov     rax, [r10+50h]
0x100464e53  mov     [rcx+30h], rax
0x100464e57  jmp     loc_100464F07
0x100464e5c  test    dl, dl
0x100464e5e  jz      short loc_100464EB9
0x100464e60  mov     r9, [rcx+10h]
0x100464e64  test    r9, r9
0x100464e67  jz      loc_100464F0B
0x100464e6d  mov     edx, [r9+50h]
0x100464e71  cmp     [r8+50h], edx
0x100464e75  jz      short loc_100464EA1
0x100464e77  mov     rax, r8
0x100464e7a  nop     word ptr [rax+rax+00h]
0x100464e80  mov     [rax+50h], edx
0x100464e83  mov     rax, [rax+38h]
0x100464e87  cmp     rax, r8
0x100464e8a  jnz     short loc_100464E80
0x100464e8c  mov     rax, [r9+38h]
0x100464e90  mov     rdx, [r8+38h]
0x100464e94  mov     [r8+38h], rax
0x100464e98  mov     [r9+38h], rdx
0x100464e9c  movzx   eax, byte ptr [r8+55h]
0x100464ea1  or      al, 10h
0x100464ea3  mov     [r8+55h], al
0x100464ea7  mov     rax, [rcx+10h]
0x100464eab  or      byte ptr [rax+55h], 20h
0x100464eaf  mov     rax, [r10+50h]
0x100464eb3  mov     [rcx+10h], rax
0x100464eb7  jmp     short loc_100464F07
0x100464eb9  mov     r9, [rcx+40h]
0x100464ebd  test    r9, r9
0x100464ec0  jz      short loc_100464F0B
0x100464ec2  mov     edx, [r9+50h]
0x100464ec6  cmp     [r8+50h], edx
0x100464eca  jz      short loc_100464EF1
0x100464ecc  mov     rax, r8
0x100464ecf  nop
0x100464ed0  mov     [rax+50h], edx
0x100464ed3  mov     rax, [rax+38h]
0x100464ed7  cmp     rax, r8
0x100464eda  jnz     short loc_100464ED0
0x100464edc  mov     rax, [r9+38h]
0x100464ee0  mov     rdx, [r8+38h]
0x100464ee4  mov     [r8+38h], rax
0x100464ee8  mov     [r9+38h], rdx
0x100464eec  movzx   eax, byte ptr [r8+55h]
0x100464ef1  or      al, 10h
0x100464ef3  mov     [r8+55h], al
0x100464ef7  mov     rax, [rcx+40h]
0x100464efb  or      byte ptr [rax+55h], 20h
0x100464eff  mov     rax, [r10+50h]
0x100464f03  mov     [rcx+40h], rax
0x100464f07  mov     [r10+50h], rbx
0x100464f0b  mov     eax, [rcx+0A0h]
0x100464f11  inc     r11d
0x100464f14  cmp     r11d, eax
0x100464f17  jb      loc_100464D70
0x100464f1d  mov     r11d, ebx
0x100464f20  test    eax, eax
0x100464f22  jz      loc_100464FE7
0x100464f28  mov     [rsp+8+arg_0], rsi
0x100464f2d  mov     r8d, eax
0x100464f30  mov     [rsp+8+arg_8], rdi
0x100464f35  nop     word ptr [rax+rax+00000000h]
0x100464f40  mov     edi, r11d
0x100464f43  mov     eax, r8d
0x100464f46  mov     rdx, [rcx+rdi*8+50h]
0x100464f4b  test    rdx, rdx
0x100464f4e  jz      short loc_100464FCE
0x100464f50  movzx   r9d, byte ptr [rdx+55h]
0x100464f55  test    r9b, 4
0x100464f59  jz      short loc_100464FCE
0x100464f5b  test    r9b, 20h
0x100464f5f  jz      short loc_100464F6E
0x100464f61  mov     [rcx+rdi*8+50h], rbx
0x100464f66  mov     eax, [rcx+0A0h]
0x100464f6c  jmp     short loc_100464FCE
0x100464f6e  movzx   esi, byte ptr [rdx+54h]
0x100464f72  mov     edx, ebx
0x100464f74  test    r8d, r8d
0x100464f77  jz      short loc_100464FCE
0x100464f79  nop     dword ptr [rax+00000000h]
0x100464f80  cmp     edx, r11d
0x100464f83  jz      short loc_100464FC2
0x100464f85  mov     r10d, edx
0x100464f88  mov     r8, [rcx+r10*8+50h]
0x100464f8d  test    r8, r8
0x100464f90  jz      short loc_100464FC2
0x100464f92  movzx   r9d, byte ptr [r8+55h]
0x100464f97  test    r9b, 4
0x100464f9b  jz      short loc_100464FC2
0x100464f9d  cmp     [r8+54h], sil
0x100464fa1  jz      short loc_100464FC2
0x100464fa3  movzx   eax, byte ptr [rdi+rcx+0A8h]
0x100464fab  cmp     [r10+rcx+0A8h], al
0x100464fb3  jz      short loc_100464FC2
0x100464fb5  or      r9b, 20h
0x100464fb9  mov     [r8+55h], r9b
0x100464fbd  mov     [rcx+r10*8+50h], rbx
0x100464fc2  mov     eax, [rcx+0A0h]
0x100464fc8  inc     edx
0x100464fca  cmp     edx, eax
0x100464fcc  jb      short loc_100464F80
0x100464fce  inc     r11d
0x100464fd1  mov     r8d, eax
0x100464fd4  cmp     r11d, eax
0x100464fd7  jb      loc_100464F40
0x100464fdd  mov     rdi, [rsp+8+arg_8]
0x100464fe2  mov     rsi, [rsp+8+arg_0]
0x100464fe7  mov     r8d, ebx
0x100464fea  test    eax, eax
0x100464fec  jz      short loc_100465026
0x100464fee  xchg    ax, ax
0x100464ff0  mov     eax, r8d
0x100464ff3  mov     r9, [rcx+rax*8+50h]
0x100464ff8  test    r9, r9
0x100464ffb  jz      short loc_10046501A
0x100464ffd  cmp     ebx, r8d
0x100465000  jnb     short loc_100465018
0x100465002  mov     edx, ebx
0x100465004  mov     [rcx+rdx*8+50h], r9
0x100465009  movzx   eax, byte ptr [rax+rcx+0A8h]
0x100465011  mov     [rdx+rcx+0A8h], al
0x100465018  inc     ebx
0x10046501a  inc     r8d
0x10046501d  cmp     r8d, [rcx+0A0h]
0x100465024  jb      short loc_100464FF0
0x100465026  mov     [rcx+0A0h], ebx
0x10046502c  pop     rbx
0x10046502d  retn
```
