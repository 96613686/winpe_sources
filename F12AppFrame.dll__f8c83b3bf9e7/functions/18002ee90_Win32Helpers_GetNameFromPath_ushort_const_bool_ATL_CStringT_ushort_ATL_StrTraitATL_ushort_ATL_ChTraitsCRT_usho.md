# Win32Helpers::GetNameFromPath(ushort const *,bool,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)

- ea: `0x18002ee90`
- end: `0x18002f101`
- name: `?GetNameFromPath@Win32Helpers@@YAJPEBG_NAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `625`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `10`
- tags: `reparse_path`

## callers

- `0x18001f024`
- `0x18002ecf4`

## callees

- `0x180002dd4`
- `0x180003338`
- `0x180003858`
- `0x180003b94`
- `0x1800041d4`
- `0x1800045b4`
- `0x18002ee90`
- `0x18002f230`
- `0x18002f400`
- `0x180035010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18002ef56`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18002ef56`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Win32Helpers::GetNameFromPath(__int64 a1, char a2, _QWORD *a3)
{
  __int64 v6; // r8
  unsigned __int16 *v7; // rbx
  unsigned __int64 v8; // rdi
  unsigned __int64 v9; // r15
  int v10; // eax
  unsigned __int16 *v11; // rdi
  unsigned __int16 *v12; // rsi
  const wchar_t *i; // rcx
  wchar_t *v14; // rax
  unsigned __int64 v15; // rsi
  int v16; // edi
  unsigned __int64 v17; // rdi
  __int64 v18; // rax
  _QWORD *v19; // rax
  unsigned __int16 *v20; // rdx
  unsigned __int16 *v21; // rdx
  unsigned __int16 *v23; // [rsp+50h] [rbp+30h] BYREF
  unsigned __int16 *v24; // [rsp+68h] [rbp+48h] BYREF

  if ( a1 )
  {
    v6 = -1;
    do
      ++v6;
    while ( *(_WORD *)(a1 + 2 * v6) );
  }
  else
  {
    v6 = 0;
  }
  ATL::CSimpleStringT<unsigned short,0>::SetString(a3, a1, v6);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v23,
    a1);
  v7 = v23;
  v8 = *((int *)v23 - 4);
  if ( *((int *)v23 - 2) > 1 )
  {
    ATL::CSimpleStringT<unsigned short,0>::Fork(&v23, (unsigned int)v8);
    v7 = v23;
  }
  v24 = 0;
  if ( !v7 || (v9 = v8, v8 - 1 > 0x7FFF) )
  {
    v16 = -2147024809;
    goto LABEL_51;
  }
  v10 = PathCchSkipRoot(v7, &v24);
  v11 = v24;
  if ( v10 < 0 )
    v11 = v7;
  v12 = &v7[v9];
  if ( v11 >= v12 )
    goto LABEL_20;
  for ( i = v11; ; i = v14 + 1 )
  {
    v14 = wcschr(i, 0x5Cu);
    if ( !v14 )
      break;
    v11 = v14;
    if ( v14 >= v12 )
      goto LABEL_20;
  }
  if ( *v11 )
  {
    *v11 = 0;
    v17 = -1;
    do
      ++v17;
    while ( v7[v17] );
    if ( v17 < v9 && v17 && v7[v17 - 1] == 92 && !(unsigned int)PathCchIsRoot(v7) )
      v7[v17 - 1] = 0;
    v16 = 0;
    goto LABEL_34;
  }
  v15 = -1;
  do
    ++v15;
  while ( v7[v15] );
  if ( v15 < v9 )
  {
    v16 = 1;
    if ( v15 && v7[v15 - 1] == 92 && !(unsigned int)PathCchIsRoot(v7) )
    {
      v7[v15 - 1] = 0;
      v16 = 0;
    }
  }
  else
  {
LABEL_20:
    v16 = -2147024809;
  }
LABEL_34:
  if ( !v16 )
  {
    if ( v23 )
    {
      v18 = -1;
      do
        ++v18;
      while ( v23[v18] );
      if ( (int)v18 < 0 )
        goto LABEL_54;
    }
    else
    {
      LODWORD(v18) = 0;
    }
    if ( (int)v18 <= *((_DWORD *)v23 - 3) )
    {
      *((_DWORD *)v23 - 4) = v18;
      v23[(unsigned int)v18] = 0;
      if ( a2 )
      {
        v19 = (_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Mid(
                          a3,
                          &v24,
                          (unsigned int)(*((_DWORD *)v23 - 4) + 1));
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
          a3,
          v19);
        v20 = v24 - 12;
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v24 - 2, 0xFFFFFFFF) <= 1 )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v20 + 8LL))(*(_QWORD *)v20);
      }
      else
      {
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
          a3,
          &v23);
      }
      v21 = v23 - 12;
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v23 - 2, 0xFFFFFFFF) <= 1 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v21 + 8LL))(*(_QWORD *)v21);
      return 0;
    }
LABEL_54:
    ATL::AtlThrowImpl(-2147024809);
  }
  v7 = v23;
  if ( v16 >= 0 )
    v16 = -2147467259;
LABEL_51:
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v7 - 2, 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v7 - 3) + 8LL))(*((_QWORD *)v7 - 3));
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x18002ee90  mov     [rsp-28h+arg_8], rbx
0x18002ee95  mov     [rsp-28h+arg_10], rsi
0x18002ee9a  push    rbp
0x18002ee9b  push    rdi
0x18002ee9c  push    r12
0x18002ee9e  push    r13
0x18002eea0  push    r15
0x18002eea2  mov     rbp, rsp
0x18002eea5  sub     rsp, 20h
0x18002eea9  mov     r12, r8
0x18002eeac  mov     r13b, dl
0x18002eeaf  mov     rbx, rcx
0x18002eeb2  xor     esi, esi
0x18002eeb4  test    rcx, rcx
0x18002eeb7  jnz     short loc_18002EEBE
0x18002eeb9  mov     r8d, esi
0x18002eebc  jmp     short loc_18002EECC
0x18002eebe  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002eec2  inc     r8
0x18002eec5  cmp     [rcx+r8*2], si
0x18002eeca  jnz     short loc_18002EEC2
0x18002eecc  mov     rdx, rbx
0x18002eecf  mov     rcx, r12
0x18002eed2  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18002eed7  mov     rdx, rbx
0x18002eeda  lea     rcx, [rbp+arg_0]
0x18002eede  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18002eee3  nop
0x18002eee4  mov     rbx, [rbp+arg_0]
0x18002eee8  movsxd  rdi, dword ptr [rbx-10h]
0x18002eeec  cmp     dword ptr [rbx-8], 1
0x18002eef0  jle     short loc_18002EF01
0x18002eef2  mov     edx, edi
0x18002eef4  lea     rcx, [rbp+arg_0]
0x18002eef8  call    ?Fork@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Fork(int)
0x18002eefd  mov     rbx, [rbp+arg_0]
0x18002ef01  mov     [rbp+arg_18], rsi
0x18002ef05  test    rbx, rbx
0x18002ef08  jz      loc_18002F0B8
0x18002ef0e  mov     r15, rdi
0x18002ef11  lea     rax, [rdi-1]
0x18002ef15  cmp     rax, 7FFFh
0x18002ef1b  ja      loc_18002F0B8
0x18002ef21  lea     rdx, [rbp+arg_18]; unsigned __int16 **
0x18002ef25  mov     rcx, rbx; unsigned __int16 *
0x18002ef28  call    ?PathCchSkipRoot@@YAJPEAGPEAPEAG@Z; PathCchSkipRoot(ushort *,ushort * *)
0x18002ef2d  mov     rdi, [rbp+arg_18]
0x18002ef31  test    eax, eax
0x18002ef33  cmovs   rdi, rbx
0x18002ef37  lea     rsi, [rbx+r15*2]
0x18002ef3b  cmp     rdi, rsi
0x18002ef3e  jnb     short loc_18002EF7A
0x18002ef40  mov     rcx, rdi
0x18002ef43  jmp     short loc_18002EF51
0x18002ef45  mov     rdi, rax
0x18002ef48  cmp     rax, rsi
0x18002ef4b  jnb     short loc_18002EF7A
0x18002ef4d  lea     rcx, [rax+2]; Str
0x18002ef51  mov     edx, 5Ch ; '\'; Ch
0x18002ef56  call    cs:__imp_wcschr
0x18002ef5c  test    rax, rax
0x18002ef5f  jnz     short loc_18002EF45
0x18002ef61  xor     esi, esi
0x18002ef63  cmp     [rdi], si
0x18002ef66  jnz     short loc_18002EFB1
0x18002ef68  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18002ef6c  inc     rsi
0x18002ef6f  cmp     [rbx+rsi*2], ax
0x18002ef73  jnz     short loc_18002EF6C
0x18002ef75  cmp     rsi, r15
0x18002ef78  jb      short loc_18002EF81
0x18002ef7a  mov     edi, 80070057h
0x18002ef7f  jmp     short loc_18002EFAD
0x18002ef81  mov     edi, 1
0x18002ef86  xor     r15d, r15d
0x18002ef89  test    rsi, rsi
0x18002ef8c  jz      short loc_18002EFAD
0x18002ef8e  lea     eax, [rdi+5Bh]
0x18002ef91  cmp     [rbx+rsi*2-2], ax
0x18002ef96  jnz     short loc_18002EFAD
0x18002ef98  mov     rcx, rbx; unsigned __int16 *
0x18002ef9b  call    ?PathCchIsRoot@@YAHPEBG@Z; PathCchIsRoot(ushort const *)
0x18002efa0  test    eax, eax
0x18002efa2  jnz     short loc_18002EFAD
0x18002efa4  mov     [rbx+rsi*2-2], r15w
0x18002efaa  mov     edi, r15d
0x18002efad  xor     esi, esi
0x18002efaf  jmp     short loc_18002EFEA
0x18002efb1  mov     [rdi], si
0x18002efb4  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18002efb8  inc     rdi
0x18002efbb  cmp     [rbx+rdi*2], si
0x18002efbf  jnz     short loc_18002EFB8
0x18002efc1  cmp     rdi, r15
0x18002efc4  jnb     short loc_18002EFE8
0x18002efc6  test    rdi, rdi
0x18002efc9  jz      short loc_18002EFE8
0x18002efcb  mov     eax, 5Ch ; '\'
0x18002efd0  cmp     [rbx+rdi*2-2], ax
0x18002efd5  jnz     short loc_18002EFE8
0x18002efd7  mov     rcx, rbx; unsigned __int16 *
0x18002efda  call    ?PathCchIsRoot@@YAHPEBG@Z; PathCchIsRoot(ushort const *)
0x18002efdf  test    eax, eax
0x18002efe1  jnz     short loc_18002EFE8
0x18002efe3  mov     [rbx+rdi*2-2], si
0x18002efe8  mov     edi, esi
0x18002efea  test    edi, edi
0x18002efec  jnz     loc_18002F0AB
0x18002eff2  mov     rcx, [rbp+arg_0]
0x18002eff6  test    rcx, rcx
0x18002eff9  jnz     short loc_18002EFFF
0x18002effb  mov     eax, esi
0x18002effd  jmp     short loc_18002F014
0x18002efff  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002f003  inc     rax
0x18002f006  cmp     [rcx+rax*2], si
0x18002f00a  jnz     short loc_18002F003
0x18002f00c  test    eax, eax
0x18002f00e  js      loc_18002F0F6
0x18002f014  cmp     eax, [rcx-0Ch]
0x18002f017  jg      loc_18002F0F6
0x18002f01d  mov     [rcx-10h], eax
0x18002f020  mov     edx, eax
0x18002f022  mov     rax, [rbp+arg_0]
0x18002f026  mov     [rax+rdx*2], si
0x18002f02a  mov     rcx, r12
0x18002f02d  test    r13b, r13b
0x18002f030  jz      short loc_18002F079
0x18002f032  mov     rax, [rbp+arg_0]
0x18002f036  mov     r8d, [rax-10h]
0x18002f03a  inc     r8d
0x18002f03d  lea     rdx, [rbp+arg_18]
0x18002f041  call    ?Mid@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@H@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Mid(int)
0x18002f046  nop
0x18002f047  mov     rdx, rax
0x18002f04a  mov     rcx, r12
0x18002f04d  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18002f052  nop
0x18002f053  mov     rdx, [rbp+arg_18]
0x18002f057  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18002f05b  or      eax, 0FFFFFFFFh
0x18002f05e  lock xadd [rdx+10h], eax
0x18002f063  sub     eax, 1
0x18002f066  jg      short loc_18002F083
0x18002f068  mov     rcx, [rdx]
0x18002f06b  mov     rax, [rcx]
0x18002f06e  mov     rax, [rax+8]
0x18002f072  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f077  jmp     short loc_18002F083
0x18002f079  lea     rdx, [rbp+arg_0]
0x18002f07d  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18002f082  nop
0x18002f083  mov     rdx, [rbp+arg_0]
0x18002f087  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18002f08b  or      eax, 0FFFFFFFFh
0x18002f08e  lock xadd [rdx+10h], eax
0x18002f093  sub     eax, 1
0x18002f096  jg      short loc_18002F0A7
0x18002f098  mov     rcx, [rdx]
0x18002f09b  mov     rax, [rcx]
0x18002f09e  mov     rax, [rax+8]
0x18002f0a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f0a7  xor     eax, eax
0x18002f0a9  jmp     short loc_18002F0DF
0x18002f0ab  mov     rbx, [rbp+arg_0]
0x18002f0af  js      short loc_18002F0BD
0x18002f0b1  mov     edi, 80004005h
0x18002f0b6  jmp     short loc_18002F0BD
0x18002f0b8  mov     edi, 80070057h
0x18002f0bd  lea     rdx, [rbx-18h]
0x18002f0c1  or      ecx, 0FFFFFFFFh
0x18002f0c4  lock xadd [rdx+10h], ecx
0x18002f0c9  sub     ecx, 1
0x18002f0cc  jg      short loc_18002F0DD
0x18002f0ce  mov     rcx, [rdx]
0x18002f0d1  mov     r8, [rcx]
0x18002f0d4  mov     rax, [r8+8]
0x18002f0d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f0dd  mov     eax, edi
0x18002f0df  mov     rbx, [rsp+20h+arg_8]
0x18002f0e4  mov     rsi, [rsp+20h+arg_10]
0x18002f0e9  add     rsp, 20h
0x18002f0ed  pop     r15
0x18002f0ef  pop     r13
0x18002f0f1  pop     r12
0x18002f0f3  pop     rdi
0x18002f0f4  pop     rbp
0x18002f0f5  retn
0x18002f0f6  mov     ecx, 80070057h; int
0x18002f0fb  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
