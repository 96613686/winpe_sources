# ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)

- ea: `0x18000b9a8`
- end: `0x18000bac5`
- name: `?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z`
- size: `285`
- prototype: `__int64 __fastcall(__int64 *, const void *, int)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x18000aa30`
- `0x18000ae58`
- `0x18000b3e4`
- `0x18000bd68`

## callees

- `0x180006a80`
- `0x18000b6ec`
- `0x18000b9a8`
- `0x18000e010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000ba8c`
- `msvcrt!memcpy_s` at `0x18000ba8c`
- `msvcrt!memmove_s` at `0x18000ba7a`
- `msvcrt!memmove_s` at `0x18000ba7a`

## pseudocode

```c
__int64 __fastcall ATL::CSimpleStringT<unsigned short,0>::SetString(__int64 *a1, const void *a2, int a3)
{
  __int64 v3; // rdi
  __int64 result; // rax
  volatile signed __int32 *v7; // rdx
  __int64 v8; // rdi
  unsigned __int64 v9; // r15
  unsigned __int64 v10; // rbp
  char *v11; // rcx

  v3 = a3;
  if ( a3 )
  {
    if ( !a2 )
      goto LABEL_20;
    v9 = *(unsigned int *)(*a1 - 16);
    v10 = ((__int64)a2 - *a1) >> 1;
    if ( ((*(_DWORD *)(*a1 - 12) - a3) | (1 - *(_DWORD *)(*a1 - 8))) < 0 )
      ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a1, a3);
    v11 = (char *)*a1;
    if ( v10 > v9 )
      memcpy_s(v11, 2 * v3, a2, 2 * v3);
    else
      memmove_s(v11, 2 * v3, &v11[2 * v10], 2 * v3);
    if ( (int)v3 < 0 || (int)v3 > *(_DWORD *)(*a1 - 12) )
LABEL_20:
      ATL::AtlThrowImpl(-2147024809);
    *(_DWORD *)(*a1 - 16) = v3;
    result = 0;
    *(_WORD *)(2 * v3 + *a1) = 0;
  }
  else
  {
    result = *a1;
    v7 = (volatile signed __int32 *)(*a1 - 24);
    if ( *((_DWORD *)v7 + 2) )
    {
      if ( *((int *)v7 + 4) >= 0 )
      {
        v8 = *(_QWORD *)v7;
        if ( _InterlockedExchangeAdd(v7 + 4, 0xFFFFFFFF) <= 1 )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v7 + 8LL))(*(_QWORD *)v7);
        result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 24LL))(v8) + 24;
        *a1 = result;
      }
      else
      {
        if ( *(int *)(result - 12) < 0 )
          ATL::AtlThrowImpl(-2147024809);
        *(_DWORD *)(result - 16) = 0;
        result = 0;
        *(_WORD *)*a1 = 0;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000b9a8  push    rbx
0x18000b9aa  push    rbp
0x18000b9ab  push    rsi
0x18000b9ac  push    rdi
0x18000b9ad  push    r14
0x18000b9af  push    r15
0x18000b9b1  sub     rsp, 28h
0x18000b9b5  movsxd  rdi, r8d
0x18000b9b8  mov     r14, rdx
0x18000b9bb  mov     rbx, rcx
0x18000b9be  test    r8d, r8d
0x18000b9c1  jnz     short loc_18000BA30
0x18000b9c3  mov     rax, [rcx]
0x18000b9c6  lea     rdx, [rax-18h]
0x18000b9ca  cmp     [rdx+8], r8d
0x18000b9ce  jz      short loc_18000BA23
0x18000b9d0  cmp     [rdx+10h], r8d
0x18000b9d4  jge     short loc_18000B9EE
0x18000b9d6  cmp     [rax-0Ch], r8d
0x18000b9da  jl      loc_18000BAAF
0x18000b9e0  mov     [rax-10h], r8d
0x18000b9e4  mov     rcx, [rcx]
0x18000b9e7  xor     eax, eax
0x18000b9e9  mov     [rcx], ax
0x18000b9ec  jmp     short loc_18000BA23
0x18000b9ee  mov     rdi, [rdx]
0x18000b9f1  or      eax, 0FFFFFFFFh
0x18000b9f4  lock xadd [rdx+10h], eax
0x18000b9f9  sub     eax, 1
0x18000b9fc  jg      short loc_18000BA0D
0x18000b9fe  mov     rcx, [rdx]
0x18000ba01  mov     rax, [rcx]
0x18000ba04  mov     rax, [rax+8]
0x18000ba08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba0d  mov     rax, [rdi]
0x18000ba10  mov     rcx, rdi
0x18000ba13  mov     rax, [rax+18h]
0x18000ba17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba1c  add     rax, 18h
0x18000ba20  mov     [rbx], rax
0x18000ba23  add     rsp, 28h
0x18000ba27  pop     r15
0x18000ba29  pop     r14
0x18000ba2b  pop     rdi
0x18000ba2c  pop     rsi
0x18000ba2d  pop     rbp
0x18000ba2e  pop     rbx
0x18000ba2f  retn
0x18000ba30  test    r14, r14
0x18000ba33  jz      loc_18000BABA
0x18000ba39  mov     rax, [rcx]
0x18000ba3c  mov     r15d, [rax-10h]
0x18000ba40  mov     rbp, r14
0x18000ba43  sub     rbp, rax
0x18000ba46  sar     rbp, 1
0x18000ba49  mov     ecx, 1
0x18000ba4e  sub     ecx, [rax-8]
0x18000ba51  mov     eax, [rax-0Ch]
0x18000ba54  sub     eax, edi
0x18000ba56  or      ecx, eax
0x18000ba58  jge     short loc_18000BA64
0x18000ba5a  mov     edx, edi
0x18000ba5c  mov     rcx, rbx
0x18000ba5f  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x18000ba64  mov     rcx, [rbx]; Destination
0x18000ba67  lea     rsi, [rdi+rdi]
0x18000ba6b  cmp     rbp, r15
0x18000ba6e  ja      short loc_18000BA83
0x18000ba70  lea     r8, [rcx+rbp*2]; Source
0x18000ba74  mov     r9, rsi; SourceSize
0x18000ba77  mov     rdx, rsi; DestinationSize
0x18000ba7a  call    cs:__imp_memmove_s
0x18000ba80  nop
0x18000ba81  jmp     short loc_18000BA92
0x18000ba83  mov     r9, rsi; SourceSize
0x18000ba86  mov     r8, r14; Source
0x18000ba89  mov     rdx, rsi; DestinationSize
0x18000ba8c  call    cs:__imp_memcpy_s
0x18000ba92  test    edi, edi
0x18000ba94  js      short loc_18000BABA
0x18000ba96  mov     rax, [rbx]
0x18000ba99  cmp     edi, [rax-0Ch]
0x18000ba9c  jg      short loc_18000BABA
0x18000ba9e  mov     [rax-10h], edi
0x18000baa1  mov     rcx, [rbx]
0x18000baa4  xor     eax, eax
0x18000baa6  mov     [rsi+rcx], ax
0x18000baaa  jmp     loc_18000BA23
0x18000baaf  mov     ecx, 80070057h; int
0x18000bab4  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000baba  mov     ecx, 80070057h; int
0x18000babf  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
