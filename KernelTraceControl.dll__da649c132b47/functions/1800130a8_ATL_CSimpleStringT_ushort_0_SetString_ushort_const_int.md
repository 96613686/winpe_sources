# ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)

- ea: `0x1800130a8`
- end: `0x180013177`
- name: `?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z`
- size: `207`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `4`
- tags: ``

## callers

- `0x1800098d0`
- `0x18000d908`
- `0x180012b8c`
- `0x1800140dc`
- `0x180014e44`
- `0x18001c170`
- `0x18001e0e4`
- `0x180020cc0`

## callees

- `0x18000139c`
- `0x180012ea8`
- `0x180013048`
- `0x1800130a8`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18001313f`
- `msvcrt!memcpy_s` at `0x18001313f`
- `msvcrt!memmove_s` at `0x180013134`
- `msvcrt!memmove_s` at `0x180013134`

## pseudocode

```c
__int64 __fastcall ATL::CSimpleStringT<unsigned short,0>::SetString(__int64 *a1, const void *a2, int a3)
{
  __int64 v3; // rbx
  __int64 result; // rax
  unsigned __int64 v7; // rbp
  unsigned __int64 v8; // rsi
  char *v9; // rcx
  rsize_t v10; // r9
  rsize_t v11; // rdx

  v3 = a3;
  if ( !a3 )
    return ATL::CSimpleStringT<unsigned short,0>::Empty(a1);
  if ( !a2 )
    ATL::AtlThrowImpl(-2147024809);
  v7 = ((__int64)a2 - *a1) >> 1;
  v8 = *(unsigned int *)(*a1 - 16);
  if ( ((*(_DWORD *)(*a1 - 12) - a3) | (1 - *(_DWORD *)(*a1 - 8))) < 0 )
    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a1);
  v9 = (char *)*a1;
  v10 = 2 * v3;
  v11 = 2 * v3;
  if ( v7 > v8 )
    memcpy_s(v9, v11, a2, v10);
  else
    memmove_s(v9, v11, &v9[2 * v7], v10);
  if ( (int)v3 < 0 || (int)v3 > *(_DWORD *)(*a1 - 12) )
    ATL::AtlThrowImpl(-2147024809);
  *(_DWORD *)(*a1 - 16) = v3;
  result = *a1;
  *(_WORD *)(2 * v3 + *a1) = 0;
  return result;
}

```

## disassembly

```asm
0x1800130a8  mov     [rsp+arg_0], rbx
0x1800130ad  mov     [rsp+arg_8], rbp
0x1800130b2  mov     [rsp+arg_10], rsi
0x1800130b7  push    rdi
0x1800130b8  push    r14
0x1800130ba  push    r15
0x1800130bc  sub     rsp, 20h
0x1800130c0  xor     r15d, r15d
0x1800130c3  movsxd  rbx, r8d
0x1800130c6  mov     r14, rdx
0x1800130c9  mov     rdi, rcx
0x1800130cc  test    r8d, r8d
0x1800130cf  jnz     short loc_1800130EF
0x1800130d1  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x1800130d6  mov     rbx, [rsp+38h+arg_0]
0x1800130db  mov     rbp, [rsp+38h+arg_8]
0x1800130e0  mov     rsi, [rsp+38h+arg_10]
0x1800130e5  add     rsp, 20h
0x1800130e9  pop     r15
0x1800130eb  pop     r14
0x1800130ed  pop     rdi
0x1800130ee  retn
0x1800130ef  test    r14, r14
0x1800130f2  jz      short loc_180013161
0x1800130f4  mov     rax, [rcx]
0x1800130f7  mov     rbp, r14
0x1800130fa  sub     rbp, rax
0x1800130fd  mov     ecx, 1
0x180013102  sar     rbp, 1
0x180013105  sub     ecx, [rax-8]
0x180013108  mov     esi, [rax-10h]
0x18001310b  mov     eax, [rax-0Ch]
0x18001310e  sub     eax, ebx
0x180013110  or      ecx, eax
0x180013112  jge     short loc_18001311E
0x180013114  mov     edx, ebx
0x180013116  mov     rcx, rdi
0x180013119  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x18001311e  mov     rcx, [rdi]; Destination
0x180013121  cmp     rbp, rsi
0x180013124  lea     rsi, [rbx+rbx]
0x180013128  mov     r9, rsi; SourceSize
0x18001312b  mov     rdx, rsi; DestinationSize
0x18001312e  ja      short loc_18001313C
0x180013130  lea     r8, [rcx+rbp*2]; Source
0x180013134  call    cs:__imp_memmove_s
0x18001313a  jmp     short loc_180013145
0x18001313c  mov     r8, r14; Source
0x18001313f  call    cs:__imp_memcpy_s
0x180013145  test    ebx, ebx
0x180013147  js      short loc_18001316C
0x180013149  mov     rax, [rdi]
0x18001314c  cmp     ebx, [rax-0Ch]
0x18001314f  jg      short loc_18001316C
0x180013151  mov     [rax-10h], ebx
0x180013154  mov     rax, [rdi]
0x180013157  mov     [rsi+rax], r15w
0x18001315c  jmp     loc_1800130D6
0x180013161  mov     ecx, 80070057h; int
0x180013166  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001316c  mov     ecx, 80070057h; int
0x180013171  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
