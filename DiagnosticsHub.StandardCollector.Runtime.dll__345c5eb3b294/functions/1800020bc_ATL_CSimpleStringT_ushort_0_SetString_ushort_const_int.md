# ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)

- ea: `0x1800020bc`
- end: `0x1800021fb`
- name: `?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z`
- size: `319`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `9`
- callee_count: `4`
- tags: ``

## callers

- `0x1800023c4`
- `0x18000a0f0`
- `0x180020338`
- `0x180027bc8`
- `0x180031194`
- `0x180031490`
- `0x18003ae24`
- `0x18003bef8`
- `0x18003c73c`

## callees

- `0x180002034`
- `0x1800020bc`
- `0x180002354`
- `0x180002604`

## import_xrefs

- `VCRUNTIME140!memcpy` at `0x1800021b6`
- `VCRUNTIME140!memcpy` at `0x1800021b6`
- `VCRUNTIME140!memset` at `0x1800021c0`
- `VCRUNTIME140!memset` at `0x1800021c0`
- `VCRUNTIME140!memmove` at `0x18000218f`
- `VCRUNTIME140!memmove` at `0x18000218f`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18000216a`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1800021c6`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18000216a`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1800021c6`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1800021d2`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1800021d2`

## pseudocode

```c
__int64 __fastcall ATL::CSimpleStringT<unsigned short,0>::SetString(__int64 *a1, const void *a2, __int64 a3)
{
  __int64 v3; // rdi
  __int64 result; // rax
  unsigned __int64 v7; // rbp
  unsigned __int64 v8; // r15
  int *v9; // rcx
  unsigned __int64 v10; // rbx
  char *v11; // rdx
  size_t v12; // r8

  v3 = (int)a3;
  if ( !(_DWORD)a3 )
    return ATL::CSimpleStringT<unsigned short,0>::Empty(a1);
  if ( !a2 || (v7 = ((__int64)a2 - *a1) >> 1, v8 = *(unsigned int *)(*a1 - 16), (int)a3 < 0) )
LABEL_23:
    ATL::AtlThrowImpl(-2147024809);
  if ( (int)((*(_DWORD *)(*a1 - 12) - a3) | (1 - *(_DWORD *)(*a1 - 8))) < 0 )
  {
    _mm_lfence();
    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a1, (unsigned int)a3, a3);
  }
  v9 = (int *)*a1;
  v10 = 2 * v3;
  if ( v7 > v8 )
  {
    v12 = 2LL * *(v9 - 3);
    if ( !v10 )
      goto LABEL_21;
    if ( v9 )
    {
      if ( v12 >= v10 )
      {
        _mm_lfence();
        memcpy(v9, a2, 2 * v3);
        goto LABEL_21;
      }
      memset(v9, 0, v12);
      goto LABEL_19;
    }
  }
  else
  {
    v11 = (char *)v9 + 2 * v7;
    if ( !v10 )
      goto LABEL_21;
    if ( v9 && v11 )
    {
      if ( 2LL * *(v9 - 3) >= v10 )
      {
        _mm_lfence();
        memmove(v9, v11, 2 * v3);
        goto LABEL_21;
      }
LABEL_19:
      *_errno() = 34;
      goto LABEL_20;
    }
  }
  *_errno() = 22;
LABEL_20:
  _invalid_parameter_noinfo();
LABEL_21:
  if ( (int)v3 > *(_DWORD *)(*a1 - 12) )
    goto LABEL_23;
  *(_DWORD *)(*a1 - 16) = v3;
  result = *a1;
  *(_WORD *)(v10 + *a1) = 0;
  return result;
}

```

## disassembly

```asm
0x1800020bc  mov     rax, rsp
0x1800020bf  mov     [rax+8], rbx
0x1800020c3  mov     [rax+10h], rbp
0x1800020c7  mov     [rax+18h], rsi
0x1800020cb  mov     [rax+20h], rdi
0x1800020cf  push    r12
0x1800020d1  push    r14
0x1800020d3  push    r15
0x1800020d5  sub     rsp, 20h
0x1800020d9  xor     r12d, r12d
0x1800020dc  movsxd  rdi, r8d
0x1800020df  mov     r14, rdx
0x1800020e2  mov     rsi, rcx
0x1800020e5  test    r8d, r8d
0x1800020e8  jnz     short loc_18000210E
0x1800020ea  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x1800020ef  mov     rbx, [rsp+38h+arg_0]
0x1800020f4  mov     rbp, [rsp+38h+arg_8]
0x1800020f9  mov     rsi, [rsp+38h+arg_10]
0x1800020fe  mov     rdi, [rsp+38h+arg_18]
0x180002103  add     rsp, 20h
0x180002107  pop     r15
0x180002109  pop     r14
0x18000210b  pop     r12
0x18000210d  retn
0x18000210e  test    r14, r14
0x180002111  jz      loc_1800021F0
0x180002117  mov     rax, [rcx]
0x18000211a  mov     rbp, r14
0x18000211d  sub     rbp, rax
0x180002120  sar     rbp, 1
0x180002123  mov     r15d, [rax-10h]
0x180002127  test    r8d, r8d
0x18000212a  js      loc_1800021F0
0x180002130  mov     ecx, 1
0x180002135  sub     ecx, [rax-8]
0x180002138  mov     eax, [rax-0Ch]
0x18000213b  sub     eax, edi
0x18000213d  or      ecx, eax
0x18000213f  jge     short loc_18000214E
0x180002141  lfence
0x180002144  mov     edx, edi
0x180002146  mov     rcx, rsi
0x180002149  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x18000214e  mov     rcx, [rsi]; void *
0x180002151  mov     rbx, rdi
0x180002154  add     rbx, rbx
0x180002157  cmp     rbp, r15
0x18000215a  ja      short loc_180002197
0x18000215c  lea     rdx, [rcx+rbp*2]; Src
0x180002160  test    rbx, rbx
0x180002163  jz      short loc_1800021D8
0x180002165  test    rcx, rcx
0x180002168  jnz     short loc_180002178
0x18000216a  call    cs:__imp__errno
0x180002170  mov     dword ptr [rax], 16h
0x180002176  jmp     short loc_1800021D2
0x180002178  test    rdx, rdx
0x18000217b  jz      short loc_18000216A
0x18000217d  movsxd  rax, dword ptr [rcx-0Ch]
0x180002181  add     rax, rax
0x180002184  cmp     rax, rbx
0x180002187  jb      short loc_1800021C6
0x180002189  lfence
0x18000218c  mov     r8, rbx; Size
0x18000218f  call    cs:__imp_memmove
0x180002195  jmp     short loc_1800021D8
0x180002197  movsxd  r8, dword ptr [rcx-0Ch]
0x18000219b  add     r8, r8; Size
0x18000219e  test    rbx, rbx
0x1800021a1  jz      short loc_1800021D8
0x1800021a3  test    rcx, rcx
0x1800021a6  jz      short loc_18000216A
0x1800021a8  cmp     r8, rbx
0x1800021ab  jb      short loc_1800021BE
0x1800021ad  lfence
0x1800021b0  mov     r8, rbx; Size
0x1800021b3  mov     rdx, r14; Src
0x1800021b6  call    cs:__imp_memcpy
0x1800021bc  jmp     short loc_1800021D8
0x1800021be  xor     edx, edx; Val
0x1800021c0  call    cs:__imp_memset
0x1800021c6  call    cs:__imp__errno
0x1800021cc  mov     dword ptr [rax], 22h ; '"'
0x1800021d2  call    cs:__imp__invalid_parameter_noinfo
0x1800021d8  mov     rax, [rsi]
0x1800021db  cmp     edi, [rax-0Ch]
0x1800021de  jg      short loc_1800021F0
0x1800021e0  mov     [rax-10h], edi
0x1800021e3  mov     rax, [rsi]
0x1800021e6  mov     [rbx+rax], r12w
0x1800021eb  jmp     loc_1800020EF
0x1800021f0  mov     ecx, 80070057h; int
0x1800021f5  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
