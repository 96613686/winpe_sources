# SepSddlGetAclForString

- ea: `0x14000d7c8`
- end: `0x14000db7c`
- name: `SepSddlGetAclForString`
- size: `948`
- prototype: `__int64 __fastcall(wchar_t *Str1, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x14000d6e4`

## callees

- `0x140002ac0`
- `0x14000d5f0`
- `0x14000d7c8`
- `0x14000db84`
- `0x14000dc3c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000db44`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000db44`
- `ntoskrnl!wcschr` at `0x14000d7f3`
- `ntoskrnl!wcschr` at `0x14000d7f3`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000d8aa`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000d8ef`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000d8aa`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000d8ef`
- `ntoskrnl!_wcsnicmp` at `0x14000d98c`
- `ntoskrnl!_wcsnicmp` at `0x14000da05`
- `ntoskrnl!_wcsnicmp` at `0x14000d98c`
- `ntoskrnl!_wcsnicmp` at `0x14000da05`

## pseudocode

```c
__int64 __fastcall SepSddlGetAclForString(wchar_t *Str1, _QWORD *a2, wchar_t **a3)
{
  wchar_t *v5; // rsi
  wchar_t *v6; // rax
  unsigned int v8; // r8d
  __int64 v9; // rax
  wchar_t *v10; // rax
  wchar_t *v11; // rcx
  int i; // r9d
  unsigned int v13; // r13d
  unsigned int SidForString; // ebx
  _QWORD *v15; // rax
  unsigned int v16; // r15d
  _WORD *PoolWithTag; // rax
  _WORD *v18; // rdi
  unsigned int v19; // r12d
  const wchar_t *v20; // rdi
  const wchar_t *j; // rdi
  unsigned int k; // esi
  __int64 v23; // r12
  wchar_t *v24; // rcx
  int v25; // edx
  const wchar_t *v26; // rsi
  _WORD *v27; // rcx
  ACCESS_MASK v28; // [rsp+A0h] [rbp+48h] BYREF
  unsigned int v29; // [rsp+A8h] [rbp+50h]
  int v30; // [rsp+B0h] [rbp+58h]
  const wchar_t *v31; // [rsp+B8h] [rbp+60h] BYREF

  *a2 = 0;
  v5 = Str1;
  v6 = wcschr(Str1, 0x3Au);
  *a3 = v6;
  if ( v6 == v5 )
    return 3221225485LL;
  v8 = 0;
  if ( v6 )
  {
    v10 = v6 - 1;
  }
  else
  {
    v9 = -1;
    do
      ++v9;
    while ( v5[v9] );
    v10 = &v5[v9];
  }
  *a3 = v10;
  v11 = v5;
  for ( i = 0; v11 < v10; ++v11 )
  {
    if ( *v11 == 59 )
    {
      ++v8;
    }
    else if ( *v11 != 32 )
    {
      i = 1;
    }
  }
  v13 = v8 / 5;
  if ( v8 != 5 * (v8 / 5) || !v8 && i )
    return (unsigned int)-1073741811;
  SidForString = 0;
  if ( v13 )
  {
    v16 = 48 * v13 + 8;
    if ( v16 > 0xFFFF )
      v16 = 0xFFFF;
    PoolWithTag = ExAllocatePoolWithTag(PagedPool, v16, 0x6C416553u);
    *a2 = PoolWithTag;
    v18 = PoolWithTag;
    if ( PoolWithTag )
    {
      v30 = 8;
      memset(PoolWithTag, 0, v16);
      *v18 = 2;
      v18[1] = v16;
      v19 = 0;
      *((_DWORD *)v18 + 1) = 0;
      while ( 1 )
      {
        v29 = v19;
        if ( v19 >= v13 )
          break;
        v28 = 0;
        while ( *v5 == 32 )
          ++v5;
        v20 = v5 + 1;
        if ( *v5 != 40 )
          v20 = v5;
        while ( *v20 == 32 )
          ++v20;
        if ( _wcsnicmp(v20, L"A", 1u) )
          goto LABEL_69;
        for ( j = v20 + 2; *j == 32; ++j )
          ;
        if ( *j != 59 )
        {
LABEL_69:
          SidForString = -1073741811;
LABEL_70:
          v27 = (_WORD *)*a2;
LABEL_72:
          ExFreePoolWithTag(v27, 0);
          *a2 = 0;
          return SidForString;
        }
        do
          ++j;
        while ( *j == 32 );
LABEL_40:
        while ( *j != 59 )
        {
          for ( ; *j == 32; ++j )
            ;
          for ( k = 0; k < 8; ++k )
          {
            v23 = 2LL * k;
            if ( !_wcsnicmp(j, (&off_140007140)[v23], *((unsigned int *)&off_140007140 + 2 * v23 + 2)) )
            {
              v28 |= *((_DWORD *)&off_140007140 + 2 * v23 + 3);
              j += *((unsigned int *)&off_140007140 + 2 * v23 + 2);
              goto LABEL_40;
            }
          }
          v31 = j;
          SepSddlParseWideStringUlong(j, &v31, &v28);
          if ( v31 == j )
            goto LABEL_69;
          j = v31;
        }
        v24 = (wchar_t *)(j + 1);
        v25 = 2;
        do
        {
          while ( *v24 == 32 )
            ++v24;
          if ( *v24 != 59 )
            SidForString = -1073741811;
          ++v24;
          --v25;
        }
        while ( v25 );
        if ( SidForString )
          goto LABEL_70;
        while ( *v24 == 32 )
          ++v24;
        v31 = 0;
        SidForString = SepSddlGetSidForString(v24);
        if ( SidForString )
          break;
        v26 = v31;
        if ( !v31 )
          goto LABEL_62;
        while ( *v26 == 32 )
          ++v26;
        if ( *v26 != 41 )
        {
LABEL_62:
          SidForString = -1073741705;
          goto LABEL_70;
        }
        v5 = (wchar_t *)(v26 + 1);
        if ( *v5 == 40 )
          ++v5;
        v19 = v29 + 1;
      }
      v27 = (_WORD *)*a2;
      if ( SidForString )
        goto LABEL_72;
      v27[1] = v30;
      return SidForString;
    }
    return (unsigned int)-1073741670;
  }
  v15 = ExAllocatePoolWithTag(PagedPool, 8u, 0x6C416553u);
  *a2 = v15;
  if ( !v15 )
    return (unsigned int)-1073741670;
  *v15 = 524290;
  return SidForString;
}

```

## disassembly

```asm
0x14000d7c8  push    rbp
0x14000d7ca  push    rbx
0x14000d7cb  push    rsi
0x14000d7cc  push    rdi
0x14000d7cd  push    r12
0x14000d7cf  push    r13
0x14000d7d1  push    r14
0x14000d7d3  push    r15
0x14000d7d5  mov     rbp, rsp
0x14000d7d8  sub     rsp, 58h
0x14000d7dc  xor     r15d, r15d
0x14000d7df  mov     r14, rdx
0x14000d7e2  mov     [rdx], r15
0x14000d7e5  mov     rbx, r8
0x14000d7e8  mov     rsi, rcx
0x14000d7eb  mov     [rbp+var_18], r15
0x14000d7ef  lea     edx, [r15+3Ah]; Ch
0x14000d7f3  call    cs:__imp_wcschr
0x14000d7fa  nop     dword ptr [rax+rax+00h]
0x14000d7ff  mov     [rbx], rax
0x14000d802  cmp     rax, rsi
0x14000d805  jnz     short loc_14000D811
0x14000d807  mov     eax, 0C000000Dh
0x14000d80c  jmp     loc_14000DB6A
0x14000d811  mov     r8d, r15d
0x14000d814  test    rax, rax
0x14000d817  jnz     short loc_14000D82D
0x14000d819  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000d81d  inc     rax
0x14000d820  cmp     [rsi+rax*2], r15w
0x14000d825  jnz     short loc_14000D81D
0x14000d827  lea     rax, [rsi+rax*2]
0x14000d82b  jmp     short loc_14000D831
0x14000d82d  add     rax, 0FFFFFFFFFFFFFFFEh
0x14000d831  mov     [rbx], rax
0x14000d834  mov     rcx, rsi
0x14000d837  mov     r9d, r15d
0x14000d83a  mov     r10d, 1
0x14000d840  cmp     rsi, rax
0x14000d843  jnb     short loc_14000D864
0x14000d845  movzx   edx, word ptr [rcx]
0x14000d848  cmp     dx, 3Bh ; ';'
0x14000d84c  jnz     short loc_14000D853
0x14000d84e  add     r8d, r10d
0x14000d851  jmp     short loc_14000D85B
0x14000d853  cmp     dx, 20h ; ' '
0x14000d857  cmovnz  r9d, r10d
0x14000d85b  add     rcx, 2
0x14000d85f  cmp     rcx, rax
0x14000d862  jb      short loc_14000D845
0x14000d864  mov     eax, 0CCCCCCCDh
0x14000d869  mul     r8d
0x14000d86c  mov     r13d, edx
0x14000d86f  shr     r13d, 2
0x14000d873  lea     ecx, ds:0[r13*4]
0x14000d87b  add     ecx, r13d
0x14000d87e  cmp     r8d, ecx
0x14000d881  jnz     loc_14000DB63
0x14000d887  test    r8d, r8d
0x14000d88a  jnz     short loc_14000D895
0x14000d88c  test    r9d, r9d
0x14000d88f  jnz     loc_14000DB63
0x14000d895  mov     ebx, r15d
0x14000d898  mov     r8d, 6C416553h; Tag
0x14000d89e  mov     ecx, r10d; PoolType
0x14000d8a1  test    r13d, r13d
0x14000d8a4  jnz     short loc_14000D8CA
0x14000d8a6  lea     edx, [r13+8]; NumberOfBytes
0x14000d8aa  call    cs:__imp_ExAllocatePoolWithTag
0x14000d8b1  nop     dword ptr [rax+rax+00h]
0x14000d8b6  mov     [r14], rax
0x14000d8b9  test    rax, rax
0x14000d8bc  jz      short loc_14000D906
0x14000d8be  mov     qword ptr [rax], 80002h
0x14000d8c5  jmp     loc_14000DB68
0x14000d8ca  mov     eax, 0FFFFh
0x14000d8cf  lea     r15d, ds:0[r13*2]
0x14000d8d7  add     r15d, r13d
0x14000d8da  shl     r15d, 4
0x14000d8de  add     r15d, 8
0x14000d8e2  cmp     r15d, eax
0x14000d8e5  cmova   r15d, eax
0x14000d8e9  mov     edx, r15d; NumberOfBytes
0x14000d8ec  mov     r12d, r15d
0x14000d8ef  call    cs:__imp_ExAllocatePoolWithTag
0x14000d8f6  nop     dword ptr [rax+rax+00h]
0x14000d8fb  mov     [r14], rax
0x14000d8fe  mov     rdi, rax
0x14000d901  test    rax, rax
0x14000d904  jnz     short loc_14000D910
0x14000d906  mov     ebx, 0C000009Ah
0x14000d90b  jmp     loc_14000DB68
0x14000d910  mov     r8, r12; Size
0x14000d913  mov     [rbp+arg_10], 8
0x14000d91a  xor     edx, edx; Val
0x14000d91c  mov     rcx, rdi; void *
0x14000d91f  call    memset
0x14000d924  xor     eax, eax
0x14000d926  mov     word ptr [rdi], 2
0x14000d92b  mov     [rdi+2], r15w
0x14000d930  xor     r12d, r12d
0x14000d933  mov     [rdi+4], eax
0x14000d936  mov     r15d, 0C000000Dh
0x14000d93c  mov     [rbp+arg_8], r12d
0x14000d940  cmp     r12d, r13d
0x14000d943  jnb     loc_14000DB3B
0x14000d949  mov     [rbp+arg_0], 0
0x14000d950  mov     r12w, 20h ; ' '
0x14000d955  jmp     short loc_14000D95B
0x14000d957  add     rsi, 2
0x14000d95b  movzx   eax, word ptr [rsi]
0x14000d95e  cmp     ax, r12w
0x14000d962  jz      short loc_14000D957
0x14000d964  cmp     ax, 28h ; '('
0x14000d968  lea     rdi, [rsi+2]
0x14000d96c  cmovnz  rdi, rsi
0x14000d970  jmp     short loc_14000D976
0x14000d972  add     rdi, 2
0x14000d976  cmp     [rdi], r12w
0x14000d97a  jz      short loc_14000D972
0x14000d97c  mov     r8d, 1; MaxCount
0x14000d982  lea     rdx, aA; "A"
0x14000d989  mov     rcx, rdi; Str1
0x14000d98c  call    cs:__imp__wcsnicmp
0x14000d993  nop     dword ptr [rax+rax+00h]
0x14000d998  test    eax, eax
0x14000d99a  jnz     loc_14000DB33
0x14000d9a0  add     rdi, 4
0x14000d9a4  jmp     short loc_14000D9AA
0x14000d9a6  add     rdi, 2
0x14000d9aa  movzx   eax, word ptr [rdi]
0x14000d9ad  cmp     ax, r12w
0x14000d9b1  jz      short loc_14000D9A6
0x14000d9b3  cmp     ax, 3Bh ; ';'
0x14000d9b7  jnz     loc_14000DB33
0x14000d9bd  add     rdi, 2
0x14000d9c1  cmp     [rdi], r12w
0x14000d9c5  jz      short loc_14000D9BD
0x14000d9c7  lea     rcx, off_140007140; "RC"
0x14000d9ce  movzx   eax, word ptr [rdi]
0x14000d9d1  cmp     ax, 3Bh ; ';'
0x14000d9d5  jz      loc_14000DA67
0x14000d9db  cmp     ax, r12w
0x14000d9df  jnz     short loc_14000D9EB
0x14000d9e1  add     rdi, 2
0x14000d9e5  cmp     [rdi], r12w
0x14000d9e9  jz      short loc_14000D9E1
0x14000d9eb  xor     esi, esi
0x14000d9ed  cmp     esi, 8
0x14000d9f0  jnb     short loc_14000DA3B
0x14000d9f2  mov     r12d, esi
0x14000d9f5  shl     r12, 4
0x14000d9f9  mov     r8d, [r12+rcx+8]; MaxCount
0x14000d9fe  mov     rdx, [r12+rcx]; Str2
0x14000da02  mov     rcx, rdi; Str1
0x14000da05  call    cs:__imp__wcsnicmp
0x14000da0c  nop     dword ptr [rax+rax+00h]
0x14000da11  lea     rcx, off_140007140; "RC"
0x14000da18  test    eax, eax
0x14000da1a  jz      short loc_14000DA20
0x14000da1c  inc     esi
0x14000da1e  jmp     short loc_14000D9ED
0x14000da20  mov     eax, [rbp+arg_0]
0x14000da23  or      eax, [r12+rcx+0Ch]
0x14000da28  mov     [rbp+arg_0], eax
0x14000da2b  mov     eax, [r12+rcx+8]
0x14000da30  mov     r12w, 20h ; ' '
0x14000da35  lea     rdi, [rdi+rax*2]
0x14000da39  jmp     short loc_14000D9CE
0x14000da3b  lea     r8, [rbp+arg_0]
0x14000da3f  mov     [rbp+arg_18], rdi
0x14000da43  lea     rdx, [rbp+arg_18]
0x14000da47  mov     rcx, rdi
0x14000da4a  call    SepSddlParseWideStringUlong
0x14000da4f  cmp     [rbp+arg_18], rdi
0x14000da53  jz      loc_14000DB33
0x14000da59  mov     rdi, [rbp+arg_18]
0x14000da5d  mov     r12w, 20h ; ' '
0x14000da62  jmp     loc_14000D9C7
0x14000da67  lea     rcx, [rdi+2]
0x14000da6b  test    ebx, ebx
0x14000da6d  jnz     loc_14000DB36
0x14000da73  lea     edx, [rbx+2]
0x14000da76  jmp     short loc_14000DA7C
0x14000da78  add     rcx, 2
0x14000da7c  movzx   eax, word ptr [rcx]
0x14000da7f  cmp     ax, r12w
0x14000da83  jz      short loc_14000DA78
0x14000da85  cmp     ax, 3Bh ; ';'
0x14000da89  cmovnz  ebx, r15d
0x14000da8d  add     rcx, 2
0x14000da91  sub     edx, 1
0x14000da94  jnz     short loc_14000DA7C
0x14000da96  test    ebx, ebx
0x14000da98  jnz     loc_14000DB36
0x14000da9e  jmp     short loc_14000DAA4
0x14000daa0  add     rcx, 2; Str1
0x14000daa4  cmp     [rcx], r12w
0x14000daa8  jz      short loc_14000DAA0
0x14000daaa  lea     r8, [rbp+arg_18]
0x14000daae  mov     [rbp+arg_18], 0
0x14000dab6  lea     rdx, [rbp+var_18]
0x14000daba  call    SepSddlGetSidForString
0x14000dabf  mov     ebx, eax
0x14000dac1  test    eax, eax
0x14000dac3  jnz     short loc_14000DB3B
0x14000dac5  mov     rsi, [rbp+arg_18]
0x14000dac9  test    rsi, rsi
0x14000dacc  jnz     short loc_14000DAD9
0x14000dace  mov     ebx, 0C0000077h
0x14000dad3  jmp     short loc_14000DB36
0x14000dad5  add     rsi, 2
0x14000dad9  movzx   eax, word ptr [rsi]
0x14000dadc  cmp     ax, r12w
0x14000dae0  jz      short loc_14000DAD5
0x14000dae2  cmp     ax, 29h ; ')'
0x14000dae6  jnz     short loc_14000DACE
0x14000dae8  mov     rcx, [rbp+var_18]
0x14000daec  mov     r12d, [rbp+arg_8]
0x14000daf0  test    rcx, rcx
0x14000daf3  jz      short loc_14000DB1D
0x14000daf5  mov     [rsp+58h+Sid], rcx; Sid
0x14000dafa  lea     rdx, [rbp+arg_10]; int
0x14000dafe  mov     eax, r13d
0x14000db01  mov     rcx, r14; int
0x14000db04  sub     eax, r12d
0x14000db07  mov     [rsp+58h+var_30], eax; int
0x14000db0b  mov     eax, [rbp+arg_0]
0x14000db0e  mov     [rsp+58h+AccessMask], eax; AccessMask
0x14000db12  call    SepSddlAddAceToAcl
0x14000db17  mov     ebx, eax
0x14000db19  test    eax, eax
0x14000db1b  jnz     short loc_14000DB36
0x14000db1d  add     rsi, 2
0x14000db21  cmp     word ptr [rsi], 28h ; '('
0x14000db25  jnz     short loc_14000DB2B
0x14000db27  add     rsi, 2
0x14000db2b  inc     r12d
0x14000db2e  jmp     loc_14000D93C
0x14000db33  mov     ebx, r15d
0x14000db36  mov     rcx, [r14]
0x14000db39  jmp     short loc_14000DB42
0x14000db3b  mov     rcx, [r14]; P
0x14000db3e  test    ebx, ebx
0x14000db40  jz      short loc_14000DB59
0x14000db42  xor     edx, edx; Tag
0x14000db44  call    cs:__imp_ExFreePoolWithTag
0x14000db4b  nop     dword ptr [rax+rax+00h]
0x14000db50  mov     qword ptr [r14], 0
0x14000db57  jmp     short loc_14000DB68
0x14000db59  movzx   eax, word ptr [rbp+arg_10]
0x14000db5d  mov     [rcx+2], ax
0x14000db61  jmp     short loc_14000DB68
0x14000db63  mov     ebx, 0C000000Dh
0x14000db68  mov     eax, ebx
0x14000db6a  add     rsp, 58h
0x14000db6e  pop     r15
0x14000db70  pop     r14
0x14000db72  pop     r13
0x14000db74  pop     r12
0x14000db76  pop     rdi
0x14000db77  pop     rsi
0x14000db78  pop     rbx
0x14000db79  pop     rbp
0x14000db7a  retn
```
