# SepSddlGetAclForString

- ea: `0x140017758`
- end: `0x140017b0f`
- name: `SepSddlGetAclForString`
- size: `951`
- prototype: `__int64 __fastcall(wchar_t *Str1, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x140017674`

## callees

- `0x14000aa80`
- `0x140017580`
- `0x140017758`
- `0x140017b18`
- `0x140017bcc`

## import_xrefs

- `ntoskrnl!_wcsnicmp` at `0x140017916`
- `ntoskrnl!_wcsnicmp` at `0x140017986`
- `ntoskrnl!_wcsnicmp` at `0x140017916`
- `ntoskrnl!_wcsnicmp` at `0x140017986`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14001783a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14001787f`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14001783a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14001787f`
- `ntoskrnl!wcschr` at `0x140017783`
- `ntoskrnl!wcschr` at `0x140017783`
- `ntoskrnl!ExFreePoolWithTag` at `0x140017adb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140017adb`

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
  _QWORD *PoolWithTag; // rax
  unsigned int v16; // r15d
  _WORD *v17; // rax
  _WORD *v18; // rdi
  const wchar_t *v19; // rdi
  const wchar_t *j; // rdi
  wchar_t v21; // ax
  unsigned int k; // esi
  __int64 v23; // r12
  wchar_t *v24; // rcx
  int v25; // edx
  _WORD *v26; // rsi
  int v27; // edi
  _WORD *v28; // rax
  _WORD *v29; // [rsp+A0h] [rbp+48h] BYREF
  int v30; // [rsp+A8h] [rbp+50h]
  int v31; // [rsp+B0h] [rbp+58h]
  const wchar_t *v32; // [rsp+B8h] [rbp+60h] BYREF

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
  if ( !v13 )
  {
    PoolWithTag = ExAllocatePoolWithTag(PagedPool, 8u, 0x6C416553u);
    *a2 = PoolWithTag;
    if ( PoolWithTag )
    {
      *PoolWithTag = 524290;
      return SidForString;
    }
    return (unsigned int)-1073741670;
  }
  v16 = 48 * v13 + 8;
  if ( v16 > 0xFFFF )
    v16 = 0xFFFF;
  v17 = ExAllocatePoolWithTag(PagedPool, v16, 0x6C416553u);
  *a2 = v17;
  v18 = v17;
  if ( !v17 )
    return (unsigned int)-1073741670;
  v31 = 8;
  memset(v17, 0, v16);
  *v18 = 2;
  v18[1] = v16;
  *((_DWORD *)v18 + 1) = 0;
  v30 = 0;
  do
  {
    LODWORD(v29) = 0;
    while ( *v5 == 32 )
      ++v5;
    v19 = v5 + 1;
    if ( *v5 != 40 )
      v19 = v5;
    while ( *v19 == 32 )
      ++v19;
    if ( _wcsnicmp(v19, L"A", 1u) )
      goto LABEL_69;
    for ( j = v19 + 2; *j == 32; ++j )
      ;
    if ( *j != 59 )
    {
LABEL_69:
      SidForString = -1073741811;
      goto LABEL_70;
    }
    do
      v21 = *++j;
    while ( *j == 32 );
    if ( v21 != 59 )
    {
      do
      {
        if ( v21 == 32 )
        {
          do
            ++j;
          while ( *j == 32 );
        }
        for ( k = 0; k < 8; ++k )
        {
          v23 = 2LL * k;
          if ( !_wcsnicmp(j, (&off_140012090)[v23], *((unsigned int *)&off_140012090 + 2 * v23 + 2)) )
          {
            LODWORD(v29) = *((_DWORD *)&off_140012090 + 2 * v23 + 3) | (unsigned int)v29;
            j += *((unsigned int *)&off_140012090 + 2 * v23 + 2);
            goto LABEL_48;
          }
        }
        v32 = j;
        SepSddlParseWideStringUlong(j, &v32, &v29);
        if ( v32 == j )
          goto LABEL_69;
        j = v32;
LABEL_48:
        v21 = *j;
      }
      while ( *j != 59 );
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
    v29 = 0;
    SidForString = SepSddlGetSidForString(v24);
    if ( SidForString )
      break;
    v26 = v29;
    if ( !v29 )
      goto LABEL_61;
    while ( *v26 == 32 )
      ++v26;
    if ( *v26 != 41 )
    {
LABEL_61:
      SidForString = -1073741705;
LABEL_70:
      v28 = (_WORD *)*a2;
LABEL_72:
      ExFreePoolWithTag(v28, 0);
      *a2 = 0;
      return SidForString;
    }
    v27 = v30;
    v5 = v26 + 1;
    if ( *v5 == 40 )
      ++v5;
    ++v30;
  }
  while ( v27 + 1 < v13 );
  v28 = (_WORD *)*a2;
  if ( SidForString )
    goto LABEL_72;
  v28[1] = v31;
  return SidForString;
}

```

## disassembly

```asm
0x140017758  push    rbp
0x14001775a  push    rbx
0x14001775b  push    rsi
0x14001775c  push    rdi
0x14001775d  push    r12
0x14001775f  push    r13
0x140017761  push    r14
0x140017763  push    r15
0x140017765  mov     rbp, rsp
0x140017768  sub     rsp, 58h
0x14001776c  xor     r15d, r15d
0x14001776f  mov     r14, rdx
0x140017772  mov     [rdx], r15
0x140017775  mov     rbx, r8
0x140017778  mov     rsi, rcx
0x14001777b  mov     [rbp+var_18], r15
0x14001777f  lea     edx, [r15+3Ah]; Ch
0x140017783  call    cs:__imp_wcschr
0x14001778a  nop     dword ptr [rax+rax+00h]
0x14001778f  mov     [rbx], rax
0x140017792  cmp     rax, rsi
0x140017795  jnz     short loc_1400177A1
0x140017797  mov     eax, 0C000000Dh
0x14001779c  jmp     loc_140017AFD
0x1400177a1  mov     r8d, r15d
0x1400177a4  test    rax, rax
0x1400177a7  jnz     short loc_1400177BD
0x1400177a9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400177ad  inc     rax
0x1400177b0  cmp     [rsi+rax*2], r15w
0x1400177b5  jnz     short loc_1400177AD
0x1400177b7  lea     rax, [rsi+rax*2]
0x1400177bb  jmp     short loc_1400177C1
0x1400177bd  add     rax, 0FFFFFFFFFFFFFFFEh
0x1400177c1  mov     [rbx], rax
0x1400177c4  mov     rcx, rsi
0x1400177c7  mov     r9d, r15d
0x1400177ca  mov     r10d, 1
0x1400177d0  cmp     rsi, rax
0x1400177d3  jnb     short loc_1400177F4
0x1400177d5  movzx   edx, word ptr [rcx]
0x1400177d8  cmp     dx, 3Bh ; ';'
0x1400177dc  jnz     short loc_1400177E3
0x1400177de  add     r8d, r10d
0x1400177e1  jmp     short loc_1400177EB
0x1400177e3  cmp     dx, 20h ; ' '
0x1400177e7  cmovnz  r9d, r10d
0x1400177eb  add     rcx, 2
0x1400177ef  cmp     rcx, rax
0x1400177f2  jb      short loc_1400177D5
0x1400177f4  mov     eax, 0CCCCCCCDh
0x1400177f9  mul     r8d
0x1400177fc  mov     r13d, edx
0x1400177ff  shr     r13d, 2
0x140017803  lea     ecx, ds:0[r13*4]
0x14001780b  add     ecx, r13d
0x14001780e  cmp     r8d, ecx
0x140017811  jnz     loc_140017AF6
0x140017817  test    r8d, r8d
0x14001781a  jnz     short loc_140017825
0x14001781c  test    r9d, r9d
0x14001781f  jnz     loc_140017AF6
0x140017825  mov     ebx, r15d
0x140017828  mov     r8d, 6C416553h; Tag
0x14001782e  mov     ecx, r10d; PoolType
0x140017831  test    r13d, r13d
0x140017834  jnz     short loc_14001785A
0x140017836  lea     edx, [r13+8]; NumberOfBytes
0x14001783a  call    cs:__imp_ExAllocatePoolWithTag
0x140017841  nop     dword ptr [rax+rax+00h]
0x140017846  mov     [r14], rax
0x140017849  test    rax, rax
0x14001784c  jz      short loc_140017896
0x14001784e  mov     qword ptr [rax], 80002h
0x140017855  jmp     loc_140017AFB
0x14001785a  mov     eax, 0FFFFh
0x14001785f  lea     r15d, ds:0[r13*2]
0x140017867  add     r15d, r13d
0x14001786a  shl     r15d, 4
0x14001786e  add     r15d, 8
0x140017872  cmp     r15d, eax
0x140017875  cmova   r15d, eax
0x140017879  mov     edx, r15d; NumberOfBytes
0x14001787c  mov     r12d, r15d
0x14001787f  call    cs:__imp_ExAllocatePoolWithTag
0x140017886  nop     dword ptr [rax+rax+00h]
0x14001788b  mov     [r14], rax
0x14001788e  mov     rdi, rax
0x140017891  test    rax, rax
0x140017894  jnz     short loc_1400178A0
0x140017896  mov     ebx, 0C000009Ah
0x14001789b  jmp     loc_140017AFB
0x1400178a0  mov     r8, r12; Size
0x1400178a3  mov     [rbp+arg_10], 8
0x1400178aa  xor     edx, edx; Val
0x1400178ac  mov     rcx, rdi; void *
0x1400178af  call    memset
0x1400178b4  xor     eax, eax
0x1400178b6  mov     word ptr [rdi], 2
0x1400178bb  mov     [rdi+2], r15w
0x1400178c0  mov     [rdi+4], eax
0x1400178c3  mov     [rbp+arg_8], eax
0x1400178c6  test    r13d, r13d
0x1400178c9  jz      loc_140017ACA
0x1400178cf  mov     r15d, 0C000000Dh
0x1400178d5  xor     r12d, r12d
0x1400178d8  mov     dword ptr [rbp+arg_0], r12d
0x1400178dc  jmp     short loc_1400178E2
0x1400178de  add     rsi, 2
0x1400178e2  movzx   eax, word ptr [rsi]
0x1400178e5  cmp     ax, 20h ; ' '
0x1400178e9  jz      short loc_1400178DE
0x1400178eb  lea     rdi, [rsi+2]
0x1400178ef  cmp     ax, 28h ; '('
0x1400178f3  cmovnz  rdi, rsi
0x1400178f7  mov     si, 20h ; ' '
0x1400178fb  jmp     short loc_140017901
0x1400178fd  add     rdi, 2
0x140017901  cmp     [rdi], si
0x140017904  jz      short loc_1400178FD
0x140017906  mov     r8d, 1; MaxCount
0x14001790c  lea     rdx, aA; "A"
0x140017913  mov     rcx, rdi; Str1
0x140017916  call    cs:__imp__wcsnicmp
0x14001791d  nop     dword ptr [rax+rax+00h]
0x140017922  test    eax, eax
0x140017924  jnz     loc_140017AC2
0x14001792a  add     rdi, 4
0x14001792e  jmp     short loc_140017934
0x140017930  add     rdi, 2
0x140017934  movzx   eax, word ptr [rdi]
0x140017937  cmp     ax, si
0x14001793a  jz      short loc_140017930
0x14001793c  cmp     ax, 3Bh ; ';'
0x140017940  jnz     loc_140017AC2
0x140017946  add     rdi, 2
0x14001794a  movzx   eax, word ptr [rdi]
0x14001794d  cmp     ax, si
0x140017950  jz      short loc_140017946
0x140017952  cmp     ax, 3Bh ; ';'
0x140017956  jz      loc_1400179F1
0x14001795c  cmp     ax, si
0x14001795f  jnz     short loc_14001796A
0x140017961  add     rdi, 2
0x140017965  cmp     [rdi], si
0x140017968  jz      short loc_140017961
0x14001796a  xor     esi, esi
0x14001796c  lea     rax, off_140012090; "RC"
0x140017973  mov     r12d, esi
0x140017976  shl     r12, 4
0x14001797a  mov     rcx, rdi; Str1
0x14001797d  mov     r8d, [r12+rax+8]; MaxCount
0x140017982  mov     rdx, [r12+rax]; Str2
0x140017986  call    cs:__imp__wcsnicmp
0x14001798d  nop     dword ptr [rax+rax+00h]
0x140017992  test    eax, eax
0x140017994  jz      short loc_1400179C1
0x140017996  inc     esi
0x140017998  cmp     esi, 8
0x14001799b  jb      short loc_14001796C
0x14001799d  lea     r8, [rbp+arg_0]
0x1400179a1  mov     [rbp+arg_18], rdi
0x1400179a5  lea     rdx, [rbp+arg_18]
0x1400179a9  mov     rcx, rdi
0x1400179ac  call    SepSddlParseWideStringUlong
0x1400179b1  cmp     [rbp+arg_18], rdi
0x1400179b5  jz      loc_140017AC2
0x1400179bb  mov     rdi, [rbp+arg_18]
0x1400179bf  jmp     short loc_1400179DC
0x1400179c1  mov     eax, dword ptr [rbp+arg_0]
0x1400179c4  lea     rcx, off_140012090; "RC"
0x1400179cb  or      eax, [r12+rcx+0Ch]
0x1400179d0  mov     dword ptr [rbp+arg_0], eax
0x1400179d3  mov     eax, [r12+rcx+8]
0x1400179d8  lea     rdi, [rdi+rax*2]
0x1400179dc  movzx   eax, word ptr [rdi]
0x1400179df  mov     si, 20h ; ' '
0x1400179e3  cmp     ax, 3Bh ; ';'
0x1400179e7  jnz     loc_14001795C
0x1400179ed  mov     r12d, dword ptr [rbp+arg_0]
0x1400179f1  lea     rcx, [rdi+2]
0x1400179f5  test    ebx, ebx
0x1400179f7  jnz     loc_140017AC5
0x1400179fd  lea     edx, [rbx+2]
0x140017a00  jmp     short loc_140017A06
0x140017a02  add     rcx, 2
0x140017a06  movzx   eax, word ptr [rcx]
0x140017a09  cmp     ax, si
0x140017a0c  jz      short loc_140017A02
0x140017a0e  cmp     ax, 3Bh ; ';'
0x140017a12  cmovnz  ebx, r15d
0x140017a16  add     rcx, 2
0x140017a1a  sub     edx, 1
0x140017a1d  jnz     short loc_140017A06
0x140017a1f  test    ebx, ebx
0x140017a21  jnz     loc_140017AC5
0x140017a27  jmp     short loc_140017A2D
0x140017a29  add     rcx, 2; Str1
0x140017a2d  cmp     [rcx], si
0x140017a30  jz      short loc_140017A29
0x140017a32  lea     r8, [rbp+arg_0]
0x140017a36  mov     [rbp+arg_0], 0
0x140017a3e  lea     rdx, [rbp+var_18]
0x140017a42  call    SepSddlGetSidForString
0x140017a47  mov     ebx, eax
0x140017a49  test    eax, eax
0x140017a4b  jnz     short loc_140017ABD
0x140017a4d  mov     rsi, [rbp+arg_0]
0x140017a51  test    rsi, rsi
0x140017a54  jnz     short loc_140017A61
0x140017a56  mov     ebx, 0C0000077h
0x140017a5b  jmp     short loc_140017AC5
0x140017a5d  add     rsi, 2
0x140017a61  movzx   eax, word ptr [rsi]
0x140017a64  cmp     ax, 20h ; ' '
0x140017a68  jz      short loc_140017A5D
0x140017a6a  cmp     ax, 29h ; ')'
0x140017a6e  jnz     short loc_140017A56
0x140017a70  mov     rcx, [rbp+var_18]
0x140017a74  mov     edi, [rbp+arg_8]
0x140017a77  test    rcx, rcx
0x140017a7a  jz      short loc_140017AA1
0x140017a7c  mov     [rsp+58h+Sid], rcx; Sid
0x140017a81  lea     rdx, [rbp+arg_10]; int
0x140017a85  mov     eax, r13d
0x140017a88  mov     rcx, r14; int
0x140017a8b  sub     eax, edi
0x140017a8d  mov     [rsp+58h+var_30], eax; int
0x140017a91  mov     [rsp+58h+AccessMask], r12d; AccessMask
0x140017a96  call    SepSddlAddAceToAcl
0x140017a9b  mov     ebx, eax
0x140017a9d  test    eax, eax
0x140017a9f  jnz     short loc_140017AC5
0x140017aa1  add     rsi, 2
0x140017aa5  cmp     word ptr [rsi], 28h ; '('
0x140017aa9  jnz     short loc_140017AAF
0x140017aab  add     rsi, 2
0x140017aaf  inc     edi
0x140017ab1  mov     [rbp+arg_8], edi
0x140017ab4  cmp     edi, r13d
0x140017ab7  jb      loc_1400178D5
0x140017abd  mov     ecx, [rbp+arg_10]
0x140017ac0  jmp     short loc_140017ACF
0x140017ac2  mov     ebx, r15d
0x140017ac5  mov     rax, [r14]
0x140017ac8  jmp     short loc_140017AD6
0x140017aca  mov     ecx, 8
0x140017acf  mov     rax, [r14]
0x140017ad2  test    ebx, ebx
0x140017ad4  jz      short loc_140017AF0
0x140017ad6  xor     edx, edx; Tag
0x140017ad8  mov     rcx, rax; P
0x140017adb  call    cs:__imp_ExFreePoolWithTag
0x140017ae2  nop     dword ptr [rax+rax+00h]
0x140017ae7  mov     qword ptr [r14], 0
0x140017aee  jmp     short loc_140017AFB
0x140017af0  mov     [rax+2], cx
0x140017af4  jmp     short loc_140017AFB
0x140017af6  mov     ebx, 0C000000Dh
0x140017afb  mov     eax, ebx
0x140017afd  add     rsp, 58h
0x140017b01  pop     r15
0x140017b03  pop     r14
0x140017b05  pop     r13
0x140017b07  pop     r12
0x140017b09  pop     rdi
0x140017b0a  pop     rsi
0x140017b0b  pop     rbx
0x140017b0c  pop     rbp
0x140017b0d  retn
```
