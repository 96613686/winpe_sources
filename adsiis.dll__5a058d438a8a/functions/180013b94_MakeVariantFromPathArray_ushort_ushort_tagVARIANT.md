# MakeVariantFromPathArray(ushort *,ushort *,tagVARIANT *)

- ea: `0x180013b94`
- end: `0x180013e01`
- name: `?MakeVariantFromPathArray@@YAJPEAG0PEAUtagVARIANT@@@Z`
- size: `621`
- prototype: `int(unsigned __int16 *, unsigned __int16 *, struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180005cd0`

## callees

- `0x180013b94`
- `0x18001beb8`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x180013cde`
- `msvcrt!wcscpy_s` at `0x180013cfe`
- `msvcrt!wcscpy_s` at `0x180013cde`
- `msvcrt!wcscpy_s` at `0x180013cfe`
- `OLEAUT32!__imp_VariantInit` at `0x180013c4b`
- `OLEAUT32!__imp_VariantInit` at `0x180013dc7`
- `OLEAUT32!__imp_VariantInit` at `0x180013c4b`
- `OLEAUT32!__imp_VariantInit` at `0x180013dc7`
- `OLEAUT32!__imp_VariantClear` at `0x180013d46`
- `OLEAUT32!__imp_VariantClear` at `0x180013d46`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180013c01`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180013dad`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180013c01`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180013dad`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180013d95`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180013d95`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180013d3a`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180013d3a`
- `ACTIVEDS!__imp_FreeADsMem` at `0x180013d8c`
- `ACTIVEDS!__imp_FreeADsMem` at `0x180013de1`
- `ACTIVEDS!__imp_FreeADsMem` at `0x180013d8c`
- `ACTIVEDS!__imp_FreeADsMem` at `0x180013de1`
- `ACTIVEDS!__imp_ReallocADsMem` at `0x180013cb7`
- `ACTIVEDS!__imp_ReallocADsMem` at `0x180013cb7`

## pseudocode

```c
__int64 __fastcall MakeVariantFromPathArray(unsigned __int16 *a1, unsigned __int16 *a2, struct tagVARIANT *a3)
{
  __int64 v3; // r15
  unsigned __int16 *v5; // rsi
  unsigned __int16 *v6; // rbx
  wchar_t *v7; // rdi
  ULONG v8; // edx
  unsigned __int16 *i; // rax
  SAFEARRAY *v10; // r14
  DWORD v11; // r13d
  __int64 v12; // rcx
  __int64 v13; // r8
  DWORD v14; // ebx
  DWORD v15; // ebx
  wchar_t *v16; // r13
  wchar_t *v17; // rax
  unsigned __int16 *v18; // rcx
  HRESULT v19; // ebx
  __int64 v20; // rax
  int v22; // [rsp+20h] [rbp-30h]
  SAFEARRAYBOUND rgsabound; // [rsp+28h] [rbp-28h] BYREF
  __int64 v24; // [rsp+30h] [rbp-20h]
  VARIANTARG pvarg; // [rsp+38h] [rbp-18h] BYREF
  DWORD cbOld; // [rsp+98h] [rbp+48h]
  LONG rgIndices; // [rsp+A8h] [rbp+58h] BYREF

  LODWORD(v3) = 0;
  v5 = a2;
  v6 = a1;
  v7 = 0;
  if ( a2 )
  {
    v8 = 0;
    rgIndices = 0;
    for ( i = v5; *i; ++v8 )
    {
      do
        ++i;
      while ( *i );
      ++i;
    }
    rgsabound.cElements = v8;
    rgsabound.lLbound = 0;
    v10 = SafeArrayCreate(0xCu, 1u, &rgsabound);
    if ( v10 )
    {
      cbOld = 0;
      v11 = 0;
      if ( v6 )
      {
        v3 = -1;
        do
          ++v3;
        while ( v6[v3] );
      }
      while ( 1 )
      {
        if ( !*v5 )
          goto LABEL_36;
        memset(&pvarg, 0, sizeof(pvarg));
        VariantInit(&pvarg);
        pvarg.vt = 8;
        if ( v6 )
        {
          v12 = -1;
          do
            ++v12;
          while ( v5[v12] );
          v13 = (unsigned int)v3;
          v24 = (unsigned int)v3;
          if ( 2 * ((unsigned int)v3 + (unsigned __int64)(unsigned int)v12) + 2 > 0xFFFFFFFF )
          {
            v19 = -2147024809;
            goto LABEL_30;
          }
          v14 = 2 * (v12 + v3) + 2;
          v22 = v12 + v3;
          if ( v14 > v11 )
          {
            v15 = 2 * v14;
            v16 = v7;
            v17 = (wchar_t *)ReallocADsMem(v7, cbOld, v15);
            v7 = v17;
            if ( !v17 )
            {
              v7 = v16;
              v19 = -2147024882;
LABEL_30:
              if ( v7 )
                FreeADsMem(v7);
              SafeArrayDestroy(v10);
              return (unsigned int)v19;
            }
            if ( !cbOld )
              wcscpy_s(v17, (unsigned __int64)v15 >> 1, a1);
            v13 = v24;
            v11 = v15;
            cbOld = v15;
          }
          wcscpy_s(&v7[v13], ((unsigned __int64)v11 >> 1) - v13, v5);
          if ( v7[v22 - 1] == 47 )
            v7[v22 - 1] = 0;
          v18 = v7;
        }
        else
        {
          v18 = v5;
        }
        v19 = ADsAllocString(v18, &pvarg.decVal.Lo32);
        if ( v19 < 0 )
          goto LABEL_30;
        v19 = SafeArrayPutElement(v10, &rgIndices, &pvarg);
        VariantClear(&pvarg);
        if ( v19 < 0 )
          goto LABEL_30;
        v20 = -1;
        do
          ++v20;
        while ( v5[v20] );
        v6 = a1;
        v5 += v20 + 1;
        ++rgIndices;
      }
    }
  }
  else
  {
    rgsabound = 0;
    v10 = SafeArrayCreate(0xCu, 1u, &rgsabound);
    if ( v10 )
    {
LABEL_36:
      VariantInit(a3);
      a3->vt = 8204;
      a3->llVal = (LONGLONG)v10;
      if ( v7 )
        FreeADsMem(v7);
      return 0;
    }
  }
  return (unsigned int)-2147024882;
}

```

## disassembly

```asm
0x180013b94  mov     [rsp-38h+arg_10], rbx
0x180013b99  mov     [rsp-38h+Source], rcx
0x180013b9e  push    rbp
0x180013b9f  push    rsi
0x180013ba0  push    rdi
0x180013ba1  push    r12
0x180013ba3  push    r13
0x180013ba5  push    r14
0x180013ba7  push    r15
0x180013ba9  mov     rbp, rsp
0x180013bac  sub     rsp, 50h
0x180013bb0  xor     r15d, r15d
0x180013bb3  mov     r12, r8
0x180013bb6  mov     rsi, rdx
0x180013bb9  mov     rbx, rcx
0x180013bbc  mov     edi, r15d
0x180013bbf  test    rdx, rdx
0x180013bc2  jz      loc_180013D9D
0x180013bc8  mov     edx, r15d
0x180013bcb  mov     [rbp+rgIndices], r15d
0x180013bcf  mov     rax, rsi
0x180013bd2  cmp     [rsi], r15w
0x180013bd6  jz      short loc_180013BEE
0x180013bd8  add     rax, 2
0x180013bdc  cmp     [rax], r15w
0x180013be0  jnz     short loc_180013BD8
0x180013be2  add     rax, 2
0x180013be6  inc     edx
0x180013be8  cmp     [rax], r15w
0x180013bec  jnz     short loc_180013BD8
0x180013bee  mov     ecx, 0Ch; vt
0x180013bf3  mov     [rbp+rgsabound.cElements], edx
0x180013bf6  lea     r8, [rbp+rgsabound]; rgsabound
0x180013bfa  mov     [rbp+rgsabound.lLbound], r15d
0x180013bfe  lea     edx, [rcx-0Bh]; cDims
0x180013c01  call    cs:__imp_SafeArrayCreate
0x180013c07  mov     r14, rax
0x180013c0a  test    rax, rax
0x180013c0d  jz      loc_180013DBB
0x180013c13  xor     r9d, r9d
0x180013c16  mov     [rbp+cbOld], r15d
0x180013c1a  mov     r13d, r15d
0x180013c1d  test    rbx, rbx
0x180013c20  jz      short loc_180013C30
0x180013c22  or      r15, 0FFFFFFFFFFFFFFFFh
0x180013c26  inc     r15
0x180013c29  cmp     [rbx+r15*2], r9w
0x180013c2e  jnz     short loc_180013C26
0x180013c30  cmp     [rsi], r9w
0x180013c34  jz      loc_180013DC4
0x180013c3a  xorps   xmm0, xmm0
0x180013c3d  lea     rcx, [rbp+pvarg]; pvarg
0x180013c41  xor     eax, eax
0x180013c43  movups  xmmword ptr [rbp+pvarg], xmm0
0x180013c47  mov     qword ptr [rbp+pvarg+10h], rax
0x180013c4b  call    cs:__imp_VariantInit
0x180013c51  xor     r9d, r9d
0x180013c54  mov     eax, 8
0x180013c59  mov     word ptr [rbp+pvarg], ax
0x180013c5d  test    rbx, rbx
0x180013c60  jz      loc_180013D1D
0x180013c66  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180013c6a  inc     rcx
0x180013c6d  cmp     [rsi+rcx*2], r9w
0x180013c72  jnz     short loc_180013C6A
0x180013c74  mov     r8d, r15d
0x180013c77  mov     edx, 0FFFFFFFFh
0x180013c7c  mov     eax, ecx
0x180013c7e  add     rax, r8
0x180013c81  mov     [rbp+var_20], r8
0x180013c85  lea     rax, ds:2[rax*2]
0x180013c8d  cmp     rax, rdx
0x180013c90  ja      loc_180013D7F
0x180013c96  lea     eax, [rcx+r15]
0x180013c9a  lea     ebx, ds:2[rax*2]
0x180013ca1  mov     [rbp+var_30], eax
0x180013ca4  cmp     ebx, r13d
0x180013ca7  jbe     short loc_180013CEE
0x180013ca9  mov     edx, [rbp+cbOld]; cbOld
0x180013cac  add     ebx, ebx
0x180013cae  mov     r8d, ebx; cbNew
0x180013cb1  mov     rcx, rdi; pOldMem
0x180013cb4  mov     r13, rdi
0x180013cb7  call    cs:__imp_ReallocADsMem
0x180013cbd  xor     r9d, r9d
0x180013cc0  mov     rdi, rax
0x180013cc3  test    rax, rax
0x180013cc6  jz      loc_180013D75
0x180013ccc  cmp     [rbp+cbOld], r9d
0x180013cd0  jnz     short loc_180013CE4
0x180013cd2  mov     r8, [rbp+Source]; Source
0x180013cd6  mov     rcx, rax; Destination
0x180013cd9  mov     edx, ebx
0x180013cdb  shr     rdx, 1; SizeInWords
0x180013cde  call    cs:__imp_wcscpy_s
0x180013ce4  mov     r8, [rbp+var_20]
0x180013ce8  mov     r13d, ebx
0x180013ceb  mov     [rbp+cbOld], ebx
0x180013cee  lea     rcx, [rdi+r8*2]; Destination
0x180013cf2  mov     edx, r13d
0x180013cf5  shr     rdx, 1
0x180013cf8  sub     rdx, r8; SizeInWords
0x180013cfb  mov     r8, rsi; Source
0x180013cfe  call    cs:__imp_wcscpy_s
0x180013d04  mov     eax, [rbp+var_30]
0x180013d07  dec     eax
0x180013d09  mov     ecx, eax
0x180013d0b  cmp     word ptr [rdi+rax*2], 2Fh ; '/'
0x180013d10  jnz     short loc_180013D18
0x180013d12  xor     eax, eax
0x180013d14  mov     [rdi+rcx*2], ax
0x180013d18  mov     rcx, rdi
0x180013d1b  jmp     short loc_180013D20
0x180013d1d  mov     rcx, rsi
0x180013d20  lea     rdx, [rbp+pvarg+8]
0x180013d24  call    ADsAllocString
0x180013d29  mov     ebx, eax
0x180013d2b  test    eax, eax
0x180013d2d  js      short loc_180013D84
0x180013d2f  lea     r8, [rbp+pvarg]; pv
0x180013d33  mov     rcx, r14; psa
0x180013d36  lea     rdx, [rbp+rgIndices]; rgIndices
0x180013d3a  call    cs:__imp_SafeArrayPutElement
0x180013d40  lea     rcx, [rbp+pvarg]; pvarg
0x180013d44  mov     ebx, eax
0x180013d46  call    cs:__imp_VariantClear
0x180013d4c  xor     r9d, r9d
0x180013d4f  test    ebx, ebx
0x180013d51  js      short loc_180013D84
0x180013d53  or      rax, 0FFFFFFFFFFFFFFFFh
0x180013d57  inc     rax
0x180013d5a  cmp     [rsi+rax*2], r9w
0x180013d5f  jnz     short loc_180013D57
0x180013d61  mov     rbx, [rbp+Source]
0x180013d65  lea     rsi, [rsi+rax*2]
0x180013d69  add     rsi, 2
0x180013d6d  inc     [rbp+rgIndices]
0x180013d70  jmp     loc_180013C30
0x180013d75  mov     rdi, r13
0x180013d78  mov     ebx, 8007000Eh
0x180013d7d  jmp     short loc_180013D84
0x180013d7f  mov     ebx, 80070057h
0x180013d84  test    rdi, rdi
0x180013d87  jz      short loc_180013D92
0x180013d89  mov     rcx, rdi; pMem
0x180013d8c  call    cs:__imp_FreeADsMem
0x180013d92  mov     rcx, r14; psa
0x180013d95  call    cs:__imp_SafeArrayDestroy
0x180013d9b  jmp     short loc_180013DC0
0x180013d9d  mov     ecx, 0Ch; vt
0x180013da2  mov     qword ptr [rbp+rgsabound.cElements], r15
0x180013da6  lea     r8, [rbp+rgsabound]; rgsabound
0x180013daa  lea     edx, [rcx-0Bh]; cDims
0x180013dad  call    cs:__imp_SafeArrayCreate
0x180013db3  mov     r14, rax
0x180013db6  test    rax, rax
0x180013db9  jnz     short loc_180013DC4
0x180013dbb  mov     ebx, 8007000Eh
0x180013dc0  mov     eax, ebx
0x180013dc2  jmp     short loc_180013DE9
0x180013dc4  mov     rcx, r12; pvarg
0x180013dc7  call    cs:__imp_VariantInit
0x180013dcd  mov     word ptr [r12], 200Ch
0x180013dd4  mov     [r12+8], r14
0x180013dd9  test    rdi, rdi
0x180013ddc  jz      short loc_180013DE7
0x180013dde  mov     rcx, rdi; pMem
0x180013de1  call    cs:__imp_FreeADsMem
0x180013de7  xor     eax, eax
0x180013de9  mov     rbx, [rsp+50h+arg_10]
0x180013df1  add     rsp, 50h
0x180013df5  pop     r15
0x180013df7  pop     r14
0x180013df9  pop     r13
0x180013dfb  pop     r12
0x180013dfd  pop     rdi
0x180013dfe  pop     rsi
0x180013dff  pop     rbp
0x180013e00  retn
```
