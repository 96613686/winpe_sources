# std::_Insertion_sort_unchecked<StringToFontIndex *,std::less<void>>(StringToFontIndex * const,StringToFontIndex * const,std::less<void>)

- ea: `0x18007067c`
- end: `0x18007091a`
- name: `??$_Insertion_sort_unchecked@PEAUStringToFontIndex@@U?$less@X@std@@@std@@YAPEAUStringToFontIndex@@QEAU1@0U?$less@X@0@@Z`
- size: `670`
- prototype: `_DWORD *__fastcall(_DWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180070590`

## callees

- `0x18007067c`
- `0x18009e420`
- `0x1800aaf88`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180070722`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18007079e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180070722`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18007079e`

## pseudocode

```c
_DWORD *__fastcall std::_Insertion_sort_unchecked<StringToFontIndex *,std::less<void>>(_DWORD *a1, _DWORD *a2)
{
  _DWORD *v5; // rdi
  volatile signed __int32 *v6; // rbx
  unsigned int v7; // r13d
  unsigned int cchCount2; // edx
  unsigned int v9; // r9d
  int v10; // eax
  _DWORD *v11; // r14
  _DWORD *i; // r15
  unsigned int v13; // edx
  unsigned int v14; // r9d
  int v15; // eax
  void *v16; // rcx
  void *v17; // rcx
  _DWORD *v18; // rbp
  _DWORD *v19; // r14
  void *v20; // rcx
  void *v21; // rcx

  if ( a1 != a2 )
  {
    v5 = a1 + 4;
    if ( a1 + 4 != a2 )
    {
      while ( 1 )
      {
        v6 = *(volatile signed __int32 **)v5;
        _InterlockedIncrement(*(volatile signed __int32 **)v5);
        v7 = v5[2];
        if ( v6 == (volatile signed __int32 *)-8LL )
        {
          if ( *(_QWORD *)a1 != -8 )
          {
            v10 = -1;
            goto LABEL_9;
          }
        }
        else
        {
          if ( *(_QWORD *)a1 == -8 )
          {
            v10 = 1;
LABEL_9:
            if ( v10 >= 0 )
              break;
            goto LABEL_32;
          }
          cchCount2 = *(_DWORD *)(*(_QWORD *)a1 + 4LL);
          if ( cchCount2 > 0x7FFFFFFF || (v9 = *((_DWORD *)v6 + 1), v9 > 0x7FFFFFFF) )
LABEL_48:
            SafeIntExceptionHandler<Exception>::SafeIntOnOverflow();
          v10 = CompareStringW(0x7Fu, 1u, (PCNZWCH)v6 + 4, v9, (PCNZWCH)(*(_QWORD *)a1 + 8LL), cchCount2) - 2;
          if ( v10 )
            goto LABEL_9;
        }
        if ( v7 >= a1[2] )
          break;
LABEL_32:
        v18 = v5 + 4;
        v19 = v5 + 4;
        while ( v5 != a1 )
        {
          v5 -= 4;
          v19 -= 4;
          _InterlockedIncrement(*(volatile signed __int32 **)v5);
          v20 = *(void **)v19;
          if ( *(_UNKNOWN **)v19 != &DWrite::RefString::empty_
            && _InterlockedExchangeAdd((volatile signed __int32 *)v20, 0xFFFFFFFF) == 1 )
          {
            operator delete(v20);
          }
          *(_QWORD *)v19 = *(_QWORD *)v5;
          v19[2] = v5[2];
        }
        _InterlockedIncrement(v6);
        v21 = *(void **)a1;
        if ( *(_UNKNOWN **)a1 != &DWrite::RefString::empty_
          && _InterlockedExchangeAdd((volatile signed __int32 *)v21, 0xFFFFFFFF) == 1 )
        {
          operator delete(v21);
        }
        *(_QWORD *)a1 = v6;
        a1[2] = v7;
        v5 = v18;
LABEL_26:
        if ( v6 != (volatile signed __int32 *)&DWrite::RefString::empty_ && _InterlockedExchangeAdd(v6, 0xFFFFFFFF) == 1 )
          operator delete((void *)v6);
        if ( v5 == a2 )
          return a2;
      }
      v11 = v5;
      for ( i = v5; ; i = v11 )
      {
        v11 -= 4;
        if ( v6 == (volatile signed __int32 *)-8LL )
        {
          if ( *(_QWORD *)v11 != -8 )
          {
            v15 = -1;
            goto LABEL_16;
          }
        }
        else
        {
          if ( *(_QWORD *)v11 == -8 )
          {
            v15 = 1;
LABEL_16:
            if ( v15 >= 0 )
              goto LABEL_22;
            goto LABEL_17;
          }
          v13 = *(_DWORD *)(*(_QWORD *)v11 + 4LL);
          if ( v13 > 0x7FFFFFFF )
            goto LABEL_48;
          v14 = *((_DWORD *)v6 + 1);
          if ( v14 > 0x7FFFFFFF )
            goto LABEL_48;
          v15 = CompareStringW(0x7Fu, 1u, (PCNZWCH)v6 + 4, v14, (PCNZWCH)(*(_QWORD *)v11 + 8LL), v13) - 2;
          if ( v15 )
            goto LABEL_16;
        }
        if ( v7 >= v11[2] )
        {
LABEL_22:
          _InterlockedIncrement(v6);
          v17 = *(void **)i;
          if ( *(_UNKNOWN **)i != &DWrite::RefString::empty_
            && _InterlockedExchangeAdd((volatile signed __int32 *)v17, 0xFFFFFFFF) == 1 )
          {
            operator delete(v17);
          }
          *(_QWORD *)i = v6;
          i[2] = v7;
          v5 += 4;
          goto LABEL_26;
        }
LABEL_17:
        _InterlockedIncrement(*(volatile signed __int32 **)v11);
        v16 = *(void **)i;
        if ( *(_UNKNOWN **)i != &DWrite::RefString::empty_
          && _InterlockedExchangeAdd((volatile signed __int32 *)v16, 0xFFFFFFFF) == 1 )
        {
          operator delete(v16);
        }
        *(_QWORD *)i = *(_QWORD *)v11;
        i[2] = v11[2];
      }
    }
  }
  return a2;
}

```

## disassembly

```asm
0x18007067c  push    rbx
0x18007067e  push    rbp
0x18007067f  push    rsi
0x180070680  push    rdi
0x180070681  push    r12
0x180070683  push    r13
0x180070685  push    r14
0x180070687  push    r15
0x180070689  sub     rsp, 48h
0x18007068d  mov     r12, rdx
0x180070690  mov     rsi, rcx
0x180070693  cmp     rcx, rdx
0x180070696  jnz     short loc_1800706AC
0x180070698  mov     rax, r12
0x18007069b  add     rsp, 48h
0x18007069f  pop     r15
0x1800706a1  pop     r14
0x1800706a3  pop     r13
0x1800706a5  pop     r12
0x1800706a7  pop     rdi
0x1800706a8  pop     rsi
0x1800706a9  pop     rbp
0x1800706aa  pop     rbx
0x1800706ab  retn
0x1800706ac  lea     rdi, [rcx+10h]
0x1800706b0  cmp     rdi, r12
0x1800706b3  jz      short loc_180070698
0x1800706b5  or      r15d, 0FFFFFFFFh
0x1800706b9  lea     rdx, ?empty_@RefString@DWrite@@0UData@12@A; DWrite::RefString::Data DWrite::RefString::empty_
0x1800706c0  mov     rbx, [rdi]
0x1800706c3  mov     [rsp+88h+var_58], rbx
0x1800706c8  lock inc dword ptr [rbx]
0x1800706cb  mov     r13d, [rdi+8]
0x1800706cf  mov     [rsp+88h+var_50], r13d
0x1800706d4  mov     rcx, [rsi]
0x1800706d7  lea     rax, [rcx+8]
0x1800706db  lea     r8, [rbx+8]; lpString1
0x1800706df  test    r8, r8
0x1800706e2  jz      loc_1800708EF
0x1800706e8  test    rax, rax
0x1800706eb  jz      loc_180070900
0x1800706f1  mov     edx, [rcx+4]
0x1800706f4  cmp     edx, 7FFFFFFFh
0x1800706fa  ja      loc_180070914
0x180070700  mov     r9d, [rbx+4]; cchCount1
0x180070704  cmp     r9d, 7FFFFFFFh
0x18007070b  ja      loc_180070914
0x180070711  mov     [rsp+88h+cchCount2], edx; cchCount2
0x180070715  mov     [rsp+88h+lpString2], rax; lpString2
0x18007071a  mov     edx, 1; dwCmpFlags
0x18007071f  lea     ecx, [rdx+7Eh]; Locale
0x180070722  call    cs:__imp_CompareStringW
0x180070728  add     eax, 0FFFFFFFEh
0x18007072b  lea     rdx, ?empty_@RefString@DWrite@@0UData@12@A; DWrite::RefString::Data DWrite::RefString::empty_
0x180070732  jz      loc_180070859
0x180070738  shr     eax, 1Fh
0x18007073b  test    al, al
0x18007073d  jnz     loc_180070863
0x180070743  lea     rbp, [rbx+8]
0x180070747  mov     r14, rdi
0x18007074a  mov     r15, rdi
0x18007074d  sub     r14, 10h
0x180070751  mov     rcx, [r14]
0x180070754  lea     rax, [rcx+8]
0x180070758  test    rbp, rbp
0x18007075b  jz      loc_1800708DE
0x180070761  test    rax, rax
0x180070764  jz      loc_18007090A
0x18007076a  mov     edx, [rcx+4]
0x18007076d  cmp     edx, 7FFFFFFFh
0x180070773  ja      loc_180070914
0x180070779  mov     r9d, [rbx+4]; cchCount1
0x18007077d  cmp     r9d, 7FFFFFFFh
0x180070784  ja      loc_180070914
0x18007078a  mov     [rsp+88h+cchCount2], edx; cchCount2
0x18007078e  mov     [rsp+88h+lpString2], rax; lpString2
0x180070793  mov     r8, rbp; lpString1
0x180070796  mov     edx, 1; dwCmpFlags
0x18007079b  lea     ecx, [rdx+7Eh]; Locale
0x18007079e  call    cs:__imp_CompareStringW
0x1800707a4  add     eax, 0FFFFFFFEh
0x1800707a7  jz      short loc_1800707EC
0x1800707a9  shr     eax, 1Fh
0x1800707ac  test    al, al
0x1800707ae  jz      short loc_1800707F2
0x1800707b0  mov     rax, [r14]
0x1800707b3  lock inc dword ptr [rax]
0x1800707b6  mov     rcx, [r15]; Block
0x1800707b9  lea     rax, ?empty_@RefString@DWrite@@0UData@12@A; DWrite::RefString::Data DWrite::RefString::empty_
0x1800707c0  cmp     rcx, rax
0x1800707c3  jz      short loc_1800707D6
0x1800707c5  or      eax, 0FFFFFFFFh
0x1800707c8  lock xadd [rcx], eax
0x1800707cc  cmp     eax, 1
0x1800707cf  jnz     short loc_1800707D6
0x1800707d1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800707d6  mov     rax, [r14]
0x1800707d9  mov     [r15], rax
0x1800707dc  mov     eax, [r14+8]
0x1800707e0  mov     [r15+8], eax
0x1800707e4  mov     r15, r14
0x1800707e7  jmp     loc_18007074D
0x1800707ec  cmp     r13d, [r14+8]
0x1800707f0  jb      short loc_1800707B0
0x1800707f2  lock inc dword ptr [rbx]
0x1800707f5  mov     rcx, [r15]; Block
0x1800707f8  lea     rax, ?empty_@RefString@DWrite@@0UData@12@A; DWrite::RefString::Data DWrite::RefString::empty_
0x1800707ff  cmp     rcx, rax
0x180070802  jz      short loc_180070815
0x180070804  or      eax, 0FFFFFFFFh
0x180070807  lock xadd [rcx], eax
0x18007080b  cmp     eax, 1
0x18007080e  jnz     short loc_180070815
0x180070810  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180070815  mov     [r15], rbx
0x180070818  mov     [r15+8], r13d
0x18007081c  add     rdi, 10h
0x180070820  or      r15d, 0FFFFFFFFh
0x180070824  lea     rdx, ?empty_@RefString@DWrite@@0UData@12@A; DWrite::RefString::Data DWrite::RefString::empty_
0x18007082b  cmp     rbx, rdx
0x18007082e  jz      short loc_18007084B
0x180070830  mov     eax, r15d
0x180070833  lock xadd [rbx], eax
0x180070837  add     eax, r15d
0x18007083a  jnz     short loc_18007084B
0x18007083c  mov     rcx, rbx; Block
0x18007083f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180070844  lea     rdx, ?empty_@RefString@DWrite@@0UData@12@A; DWrite::RefString::Data DWrite::RefString::empty_
0x18007084b  cmp     rdi, r12
0x18007084e  jnz     loc_1800706C0
0x180070854  jmp     loc_180070698
0x180070859  cmp     r13d, [rsi+8]
0x18007085d  jnb     loc_180070743
0x180070863  lea     rbp, [rdi+10h]
0x180070867  mov     r14, rbp
0x18007086a  cmp     rdi, rsi
0x18007086d  jz      short loc_1800708AC
0x18007086f  sub     rdi, 10h
0x180070873  lea     r14, [r14-10h]
0x180070877  mov     rax, [rdi]
0x18007087a  lock inc dword ptr [rax]
0x18007087d  mov     rcx, [r14]; Block
0x180070880  cmp     rcx, rdx
0x180070883  jz      short loc_18007089D
0x180070885  mov     eax, r15d
0x180070888  lock xadd [rcx], eax
0x18007088c  add     eax, r15d
0x18007088f  jnz     short loc_18007089D
0x180070891  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180070896  lea     rdx, ?empty_@RefString@DWrite@@0UData@12@A; DWrite::RefString::Data DWrite::RefString::empty_
0x18007089d  mov     rax, [rdi]
0x1800708a0  mov     [r14], rax
0x1800708a3  mov     eax, [rdi+8]
0x1800708a6  mov     [r14+8], eax
0x1800708aa  jmp     short loc_18007086A
0x1800708ac  lock inc dword ptr [rbx]
0x1800708af  mov     rcx, [rsi]; Block
0x1800708b2  cmp     rcx, rdx
0x1800708b5  jz      short loc_1800708CF
0x1800708b7  mov     eax, r15d
0x1800708ba  lock xadd [rcx], eax
0x1800708be  add     eax, r15d
0x1800708c1  jnz     short loc_1800708CF
0x1800708c3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800708c8  lea     rdx, ?empty_@RefString@DWrite@@0UData@12@A; DWrite::RefString::Data DWrite::RefString::empty_
0x1800708cf  mov     [rsi], rbx
0x1800708d2  mov     [rsi+8], r13d
0x1800708d6  mov     rdi, rbp
0x1800708d9  jmp     loc_18007082B
0x1800708de  test    rax, rax
0x1800708e1  jz      loc_1800707EC
0x1800708e7  or      eax, 0FFFFFFFFh
0x1800708ea  jmp     loc_1800707A9
0x1800708ef  test    rax, rax
0x1800708f2  jz      loc_180070859
0x1800708f8  mov     eax, r15d
0x1800708fb  jmp     loc_180070738
0x180070900  mov     eax, 1
0x180070905  jmp     loc_180070738
0x18007090a  mov     eax, 1
0x18007090f  jmp     loc_1800707A9
0x180070914  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VException@@@@SAXXZ; SafeIntExceptionHandler<Exception>::SafeIntOnOverflow(void)
```
