# FixAnglesForSideBackAmbiguity

- ea: `0x18007fda4`
- end: `0x18007fe83`
- name: `FixAnglesForSideBackAmbiguity`
- size: `223`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18007ff40`

## callees

- `0x18007fda4`

## pseudocode

```c
char __fastcall FixAnglesForSideBackAmbiguity(__int16 a1, __int16 a2, __int64 a3)
{
  int v4; // edx
  int v6; // eax
  __int64 v7; // rdx
  __int64 v8; // rcx
  int v9; // r10d
  __int64 v10; // rdx
  __int64 v11; // rcx

  v4 = a2 & 0x210;
  if ( (a1 & 0x10) != 0 && (LOBYTE(v6) = (a1 & 0x200) == 0, ((v4 == 512) & (unsigned __int8)v6) != 0)
    || (a1 & 0x200) != 0 && (a1 & 0x10) == 0 && v4 == 16 )
  {
    v7 = 0;
    do
    {
      if ( 1 << v7 == 512 )
        break;
      v7 = (unsigned int)(v7 + 1);
    }
    while ( (int)v7 < 11 );
    v8 = 0;
    do
    {
      if ( 1 << v8 == 16 )
        break;
      v8 = (unsigned int)(v8 + 1);
    }
    while ( (int)v8 < 11 );
    v6 = *(_DWORD *)(a3 + 4 * v8);
    *(_DWORD *)(a3 + 4 * v7) = v6;
  }
  v9 = a2 & 0x420;
  if ( (a1 & 0x20) != 0 && (LOBYTE(v6) = (a1 & 0x400) == 0, ((v9 == 1024) & (unsigned __int8)v6) != 0)
    || (a1 & 0x400) != 0 && (a1 & 0x20) == 0 && v9 == 32 )
  {
    v10 = 0;
    do
    {
      if ( 1 << v10 == 1024 )
        break;
      v10 = (unsigned int)(v10 + 1);
    }
    while ( (int)v10 < 11 );
    v11 = 0;
    do
    {
      if ( 1 << v11 == 32 )
        break;
      v11 = (unsigned int)(v11 + 1);
    }
    while ( (int)v11 < 11 );
    v6 = *(_DWORD *)(a3 + 4 * v11);
    *(_DWORD *)(a3 + 4 * v10) = v6;
  }
  return v6;
}

```

## disassembly

```asm
0x18007fda4  mov     [rsp+arg_0], rbx
0x18007fda9  mov     r10d, edx
0x18007fdac  mov     r11d, ecx
0x18007fdaf  and     edx, 210h
0x18007fdb5  mov     r9d, ecx
0x18007fdb8  mov     ebx, 1
0x18007fdbd  and     r11d, 10h
0x18007fdc1  jz      short loc_18007FDD8
0x18007fdc3  cmp     edx, 200h
0x18007fdc9  setz    cl
0x18007fdcc  bt      r9d, 9
0x18007fdd1  setnb   al
0x18007fdd4  test    al, cl
0x18007fdd6  jnz     short loc_18007FDE9
0x18007fdd8  bt      r9d, 9
0x18007fddd  jnb     short loc_18007FE19
0x18007fddf  test    r11d, r11d
0x18007fde2  jnz     short loc_18007FE19
0x18007fde4  cmp     edx, 10h
0x18007fde7  jnz     short loc_18007FE19
0x18007fde9  xor     edx, edx
0x18007fdeb  mov     ecx, edx
0x18007fded  mov     eax, ebx
0x18007fdef  shl     eax, cl
0x18007fdf1  cmp     eax, 200h
0x18007fdf6  jz      short loc_18007FDFF
0x18007fdf8  add     edx, ebx
0x18007fdfa  cmp     edx, 0Bh
0x18007fdfd  jl      short loc_18007FDEB
0x18007fdff  xor     ecx, ecx
0x18007fe01  mov     eax, ebx
0x18007fe03  shl     eax, cl
0x18007fe05  cmp     eax, 10h
0x18007fe08  jz      short loc_18007FE11
0x18007fe0a  add     ecx, ebx
0x18007fe0c  cmp     ecx, 0Bh
0x18007fe0f  jl      short loc_18007FE01
0x18007fe11  mov     eax, [r8+rcx*4]
0x18007fe15  mov     [r8+rdx*4], eax
0x18007fe19  mov     edx, r9d
0x18007fe1c  and     r10d, 420h
0x18007fe23  mov     r11d, 400h
0x18007fe29  and     edx, 20h
0x18007fe2c  jz      short loc_18007FE40
0x18007fe2e  cmp     r10d, r11d
0x18007fe31  setz    cl
0x18007fe34  bt      r9d, 0Ah
0x18007fe39  setnb   al
0x18007fe3c  test    al, cl
0x18007fe3e  jnz     short loc_18007FE4F
0x18007fe40  test    r11d, r9d
0x18007fe43  jz      short loc_18007FE7D
0x18007fe45  test    edx, edx
0x18007fe47  jnz     short loc_18007FE7D
0x18007fe49  cmp     r10d, 20h ; ' '
0x18007fe4d  jnz     short loc_18007FE7D
0x18007fe4f  xor     edx, edx
0x18007fe51  mov     ecx, edx
0x18007fe53  mov     eax, ebx
0x18007fe55  shl     eax, cl
0x18007fe57  cmp     eax, r11d
0x18007fe5a  jz      short loc_18007FE63
0x18007fe5c  add     edx, ebx
0x18007fe5e  cmp     edx, 0Bh
0x18007fe61  jl      short loc_18007FE51
0x18007fe63  xor     ecx, ecx
0x18007fe65  mov     eax, ebx
0x18007fe67  shl     eax, cl
0x18007fe69  cmp     eax, 20h ; ' '
0x18007fe6c  jz      short loc_18007FE75
0x18007fe6e  add     ecx, ebx
0x18007fe70  cmp     ecx, 0Bh
0x18007fe73  jl      short loc_18007FE65
0x18007fe75  mov     eax, [r8+rcx*4]
0x18007fe79  mov     [r8+rdx*4], eax
0x18007fe7d  mov     rbx, [rsp+arg_0]
0x18007fe82  retn
```
