# CILogCreateStorage2W::CreateStream(ushort *)

- ea: `0x180002400`
- end: `0x180002599`
- name: `?CreateStream@CILogCreateStorage2W@@UEAAJPEAG@Z`
- size: `409`
- prototype: `int(CILogCreateStorage2W *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180002400`
- `0x1800042b4`
- `0x1800045f4`
- `0x180010a14`
- `0x180012830`
- `0x1800128f0`
- `0x180015010`

## import_xrefs

- `msvcrt!wcstombs` at `0x18000245a`
- `msvcrt!wcstombs` at `0x180002508`
- `msvcrt!wcstombs` at `0x18000245a`
- `msvcrt!wcstombs` at `0x180002508`

## pseudocode

```c
__int64 __fastcall CILogCreateStorage2W::CreateStream(CILogCreateStorage2W *this, unsigned __int16 *a2)
{
  char *v5; // rbx
  size_t v6; // r15
  size_t v7; // rdi
  size_t v8; // rcx
  __int64 v9; // rcx
  unsigned __int64 v10; // rcx
  void *v11; // rsp
  void *v12; // rsp
  _DWORD *v13; // rax
  unsigned int v14; // edi
  __int64 v15; // [rsp+0h] [rbp-20h] BYREF
  unsigned int v16; // [rsp+20h] [rbp+0h] BYREF
  struct _STRMTBL *v17[2]; // [rsp+28h] [rbp+8h] BYREF

  v17[0] = 0;
  v16 = 0;
  if ( !a2 )
    return 2147942487LL;
  if ( !*((_QWORD *)this + 1) )
    return 2147549183LL;
  v5 = 0;
  v6 = wcstombs(0, a2, 0);
  v7 = v6 + 1;
  if ( v6 != -1 && v7 <= g_ulMaxStackAllocSize )
  {
    v8 = v7 + g_ulAdditionalProbeSize + 8;
    if ( v8 >= v7 )
    {
      if ( (unsigned int)VerifyStackAvailable(v8) )
      {
        v9 = v6 + 24;
        if ( v6 + 24 <= v6 + 9 )
          v9 = 0xFFFFFFFFFFFFFF0LL;
        v10 = v9 & 0xFFFFFFFFFFFFFFF0uLL;
        v11 = alloca(v10);
        v12 = alloca(v10);
        v5 = (char *)&v16;
        if ( &v15 != (__int64 *)-32LL )
        {
          v16 = 1801679955;
          v5 = (char *)v17;
          if ( v17 )
            goto LABEL_17;
        }
      }
    }
  }
  if ( v6 + 9 >= v6 + 1 )
  {
    v13 = (_DWORD *)((__int64 (__fastcall *)(size_t))g_pfnAllocate)(v6 + 9);
    if ( !v13 )
      return 2147942414LL;
    *v13 = 1885431112;
    v5 = (char *)(v13 + 2);
  }
  if ( !v5 )
    return 2147942414LL;
LABEL_17:
  if ( wcstombs(v5, a2, v7) == v6 )
  {
    CILogStorage::FindStream((CILogStorage *)(*((_QWORD *)this + 1) + 96LL), v5, v17, &v16);
    if ( v17[0] )
      v14 = -2147024809;
    else
      v14 = CILogStorage::AddStream((CILogStorage *)(*((_QWORD *)this + 1) + 96LL), v5, v17, &v16);
  }
  else
  {
    v14 = -2147418113;
  }
  if ( v5 )
  {
    if ( *((_DWORD *)v5 - 2) == 1885431112 )
      ((void (__fastcall *)(char *))g_pfnFree)(v5 - 8);
  }
  return v14;
}

```

## disassembly

```asm
0x180002400  push    rbp
0x180002402  push    rbx
0x180002403  push    rsi
0x180002404  push    rdi
0x180002405  push    r14
0x180002407  push    r15
0x180002409  sub     rsp, 48h
0x18000240d  lea     rbp, [rsp+20h]
0x180002412  mov     rax, cs:__security_cookie
0x180002419  xor     rax, rbp
0x18000241c  mov     [rbp+50h+var_38], rax
0x180002420  mov     [rbp+50h+var_48], 0
0x180002428  mov     r14, rdx
0x18000242b  mov     [rbp+50h+var_50], 0
0x180002432  mov     rsi, rcx
0x180002435  test    rdx, rdx
0x180002438  jnz     short loc_180002444
0x18000243a  mov     eax, 80070057h
0x18000243f  jmp     loc_180002580
0x180002444  cmp     qword ptr [rcx+8], 0
0x180002449  jnz     short loc_180002455
0x18000244b  mov     eax, 8000FFFFh
0x180002450  jmp     loc_180002580
0x180002455  xor     r8d, r8d; MaxCount
0x180002458  xor     ecx, ecx; Dest
0x18000245a  call    cs:__imp_wcstombs
0x180002460  xor     ebx, ebx
0x180002462  mov     r15, rax
0x180002465  lea     rdi, [rax+1]
0x180002469  test    rdi, rdi
0x18000246c  jz      short loc_1800024CF
0x18000246e  cmp     rdi, cs:g_ulMaxStackAllocSize
0x180002475  ja      short loc_1800024CF
0x180002477  mov     rcx, cs:g_ulAdditionalProbeSize
0x18000247e  add     rcx, 8
0x180002482  add     rcx, rdi
0x180002485  cmp     rcx, rdi
0x180002488  jb      short loc_1800024CF
0x18000248a  call    VerifyStackAvailable
0x18000248f  test    eax, eax
0x180002491  jz      short loc_1800024CF
0x180002493  lea     rax, [rdi+8]
0x180002497  lea     rcx, [rax+0Fh]
0x18000249b  cmp     rcx, rax
0x18000249e  ja      short loc_1800024AA
0x1800024a0  mov     rcx, 0FFFFFFFFFFFFFF0h
0x1800024aa  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800024ae  mov     rax, rcx
0x1800024b1  call    _alloca_probe
0x1800024b6  sub     rsp, rcx
0x1800024b9  lea     rbx, [rsp+70h+var_50]
0x1800024be  test    rbx, rbx
0x1800024c1  jz      short loc_1800024CF
0x1800024c3  mov     dword ptr [rbx], 6B637453h
0x1800024c9  add     rbx, 8
0x1800024cd  jnz     short loc_1800024FF
0x1800024cf  lea     rcx, [rdi+8]
0x1800024d3  cmp     rcx, rdi
0x1800024d6  jb      short loc_1800024FA
0x1800024d8  mov     rax, cs:g_pfnAllocate
0x1800024df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024e4  mov     rbx, rax
0x1800024e7  test    rax, rax
0x1800024ea  jz      loc_18000257B
0x1800024f0  mov     dword ptr [rax], 70616548h
0x1800024f6  add     rbx, 8
0x1800024fa  test    rbx, rbx
0x1800024fd  jz      short loc_18000257B
0x1800024ff  mov     r8, rdi; MaxCount
0x180002502  mov     rdx, r14; Source
0x180002505  mov     rcx, rbx; Dest
0x180002508  call    cs:__imp_wcstombs
0x18000250e  cmp     rax, r15
0x180002511  jz      short loc_18000251A
0x180002513  mov     edi, 8000FFFFh
0x180002518  jmp     short loc_18000255A
0x18000251a  mov     rcx, [rsi+8]
0x18000251e  lea     r9, [rbp+50h+var_50]; unsigned int *
0x180002522  add     rcx, 60h ; '`'; this
0x180002526  lea     r8, [rbp+50h+var_48]; struct _STRMTBL **
0x18000252a  mov     rdx, rbx; char *
0x18000252d  call    ?FindStream@CILogStorage@@AEAAJPEADPEAPEAU_STRMTBL@@PEAK@Z; CILogStorage::FindStream(char *,_STRMTBL * *,ulong *)
0x180002532  cmp     [rbp+50h+var_48], 0
0x180002537  jnz     short loc_180002555
0x180002539  mov     rcx, [rsi+8]
0x18000253d  lea     r9, [rbp+50h+var_50]; unsigned int *
0x180002541  add     rcx, 60h ; '`'; this
0x180002545  lea     r8, [rbp+50h+var_48]; struct _STRMTBL **
0x180002549  mov     rdx, rbx; char *
0x18000254c  call    ?AddStream@CILogStorage@@AEAAJPEADPEAPEAU_STRMTBL@@PEAK@Z; CILogStorage::AddStream(char *,_STRMTBL * *,ulong *)
0x180002551  mov     edi, eax
0x180002553  jmp     short loc_18000255A
0x180002555  mov     edi, 80070057h
0x18000255a  test    rbx, rbx
0x18000255d  jz      short loc_180002577
0x18000255f  lea     rcx, [rbx-8]
0x180002563  cmp     dword ptr [rcx], 70616548h
0x180002569  jnz     short loc_180002577
0x18000256b  mov     rax, cs:g_pfnFree
0x180002572  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002577  mov     eax, edi
0x180002579  jmp     short loc_180002580
0x18000257b  mov     eax, 8007000Eh
0x180002580  mov     rcx, [rbp+50h+var_38]
0x180002584  xor     rcx, rbp; StackCookie
0x180002587  call    __security_check_cookie
0x18000258c  lea     rsp, [rbp+28h]
0x180002590  pop     r15
0x180002592  pop     r14
0x180002594  pop     rdi
0x180002595  pop     rsi
0x180002596  pop     rbx
0x180002597  pop     rbp
0x180002598  retn
```
