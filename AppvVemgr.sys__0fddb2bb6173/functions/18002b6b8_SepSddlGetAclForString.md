# SepSddlGetAclForString

- ea: `0x18002b6b8`
- end: `0x18002ba6f`
- name: `SepSddlGetAclForString`
- size: `951`
- prototype: `__int64 __fastcall(wchar_t *Str1, _QWORD *, wchar_t **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x18002b5d4`

## callees

- `0x18001bf00`
- `0x18002b4e0`
- `0x18002b6b8`
- `0x18002ba78`
- `0x18002bb2c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x18002ba3b`
- `ntoskrnl!ExFreePoolWithTag` at `0x18002ba3b`
- `ntoskrnl!wcschr` at `0x18002b6e3`
- `ntoskrnl!wcschr` at `0x18002b6e3`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18002b79a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18002b7df`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18002b79a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18002b7df`
- `ntoskrnl!_wcsnicmp` at `0x18002b876`
- `ntoskrnl!_wcsnicmp` at `0x18002b8e6`
- `ntoskrnl!_wcsnicmp` at `0x18002b876`
- `ntoskrnl!_wcsnicmp` at `0x18002b8e6`

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
          if ( !_wcsnicmp(j, (&off_180027120)[v23], *((unsigned int *)&off_180027120 + 2 * v23 + 2)) )
          {
            LODWORD(v29) = *((_DWORD *)&off_180027120 + 2 * v23 + 3) | (unsigned int)v29;
            j += *((unsigned int *)&off_180027120 + 2 * v23 + 2);
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
0x18002b6b8  push    rbp
0x18002b6ba  push    rbx
0x18002b6bb  push    rsi
0x18002b6bc  push    rdi
0x18002b6bd  push    r12
0x18002b6bf  push    r13
0x18002b6c1  push    r14
0x18002b6c3  push    r15
0x18002b6c5  mov     rbp, rsp
0x18002b6c8  sub     rsp, 58h
0x18002b6cc  xor     r15d, r15d
0x18002b6cf  mov     r14, rdx
0x18002b6d2  mov     [rdx], r15
0x18002b6d5  mov     rbx, r8
0x18002b6d8  mov     rsi, rcx
0x18002b6db  mov     [rbp+var_18], r15
0x18002b6df  lea     edx, [r15+3Ah]; Ch
0x18002b6e3  call    cs:__imp_wcschr
0x18002b6ea  nop     dword ptr [rax+rax+00h]
0x18002b6ef  mov     [rbx], rax
0x18002b6f2  cmp     rax, rsi
0x18002b6f5  jnz     short loc_18002B701
0x18002b6f7  mov     eax, 0C000000Dh
0x18002b6fc  jmp     loc_18002BA5D
0x18002b701  mov     r8d, r15d
0x18002b704  test    rax, rax
0x18002b707  jnz     short loc_18002B71D
0x18002b709  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002b70d  inc     rax
0x18002b710  cmp     [rsi+rax*2], r15w
0x18002b715  jnz     short loc_18002B70D
0x18002b717  lea     rax, [rsi+rax*2]
0x18002b71b  jmp     short loc_18002B721
0x18002b71d  add     rax, 0FFFFFFFFFFFFFFFEh
0x18002b721  mov     [rbx], rax
0x18002b724  mov     rcx, rsi
0x18002b727  mov     r9d, r15d
0x18002b72a  mov     r10d, 1
0x18002b730  cmp     rsi, rax
0x18002b733  jnb     short loc_18002B754
0x18002b735  movzx   edx, word ptr [rcx]
0x18002b738  cmp     dx, 3Bh ; ';'
0x18002b73c  jnz     short loc_18002B743
0x18002b73e  add     r8d, r10d
0x18002b741  jmp     short loc_18002B74B
0x18002b743  cmp     dx, 20h ; ' '
0x18002b747  cmovnz  r9d, r10d
0x18002b74b  add     rcx, 2
0x18002b74f  cmp     rcx, rax
0x18002b752  jb      short loc_18002B735
0x18002b754  mov     eax, 0CCCCCCCDh
0x18002b759  mul     r8d
0x18002b75c  mov     r13d, edx
0x18002b75f  shr     r13d, 2
0x18002b763  lea     ecx, ds:0[r13*4]
0x18002b76b  add     ecx, r13d
0x18002b76e  cmp     r8d, ecx
0x18002b771  jnz     loc_18002BA56
0x18002b777  test    r8d, r8d
0x18002b77a  jnz     short loc_18002B785
0x18002b77c  test    r9d, r9d
0x18002b77f  jnz     loc_18002BA56
0x18002b785  mov     ebx, r15d
0x18002b788  mov     r8d, 6C416553h; Tag
0x18002b78e  mov     ecx, r10d; PoolType
0x18002b791  test    r13d, r13d
0x18002b794  jnz     short loc_18002B7BA
0x18002b796  lea     edx, [r13+8]; NumberOfBytes
0x18002b79a  call    cs:__imp_ExAllocatePoolWithTag
0x18002b7a1  nop     dword ptr [rax+rax+00h]
0x18002b7a6  mov     [r14], rax
0x18002b7a9  test    rax, rax
0x18002b7ac  jz      short loc_18002B7F6
0x18002b7ae  mov     qword ptr [rax], 80002h
0x18002b7b5  jmp     loc_18002BA5B
0x18002b7ba  mov     eax, 0FFFFh
0x18002b7bf  lea     r15d, ds:0[r13*2]
0x18002b7c7  add     r15d, r13d
0x18002b7ca  shl     r15d, 4
0x18002b7ce  add     r15d, 8
0x18002b7d2  cmp     r15d, eax
0x18002b7d5  cmova   r15d, eax
0x18002b7d9  mov     edx, r15d; NumberOfBytes
0x18002b7dc  mov     r12d, r15d
0x18002b7df  call    cs:__imp_ExAllocatePoolWithTag
0x18002b7e6  nop     dword ptr [rax+rax+00h]
0x18002b7eb  mov     [r14], rax
0x18002b7ee  mov     rdi, rax
0x18002b7f1  test    rax, rax
0x18002b7f4  jnz     short loc_18002B800
0x18002b7f6  mov     ebx, 0C000009Ah
0x18002b7fb  jmp     loc_18002BA5B
0x18002b800  mov     r8, r12; Size
0x18002b803  mov     [rbp+arg_10], 8
0x18002b80a  xor     edx, edx; Val
0x18002b80c  mov     rcx, rdi; void *
0x18002b80f  call    memset
0x18002b814  xor     eax, eax
0x18002b816  mov     word ptr [rdi], 2
0x18002b81b  mov     [rdi+2], r15w
0x18002b820  mov     [rdi+4], eax
0x18002b823  mov     [rbp+arg_8], eax
0x18002b826  test    r13d, r13d
0x18002b829  jz      loc_18002BA2A
0x18002b82f  mov     r15d, 0C000000Dh
0x18002b835  xor     r12d, r12d
0x18002b838  mov     dword ptr [rbp+arg_0], r12d
0x18002b83c  jmp     short loc_18002B842
0x18002b83e  add     rsi, 2
0x18002b842  movzx   eax, word ptr [rsi]
0x18002b845  cmp     ax, 20h ; ' '
0x18002b849  jz      short loc_18002B83E
0x18002b84b  lea     rdi, [rsi+2]
0x18002b84f  cmp     ax, 28h ; '('
0x18002b853  cmovnz  rdi, rsi
0x18002b857  mov     si, 20h ; ' '
0x18002b85b  jmp     short loc_18002B861
0x18002b85d  add     rdi, 2
0x18002b861  cmp     [rdi], si
0x18002b864  jz      short loc_18002B85D
0x18002b866  mov     r8d, 1; MaxCount
0x18002b86c  lea     rdx, aA; "A"
0x18002b873  mov     rcx, rdi; Str1
0x18002b876  call    cs:__imp__wcsnicmp
0x18002b87d  nop     dword ptr [rax+rax+00h]
0x18002b882  test    eax, eax
0x18002b884  jnz     loc_18002BA22
0x18002b88a  add     rdi, 4
0x18002b88e  jmp     short loc_18002B894
0x18002b890  add     rdi, 2
0x18002b894  movzx   eax, word ptr [rdi]
0x18002b897  cmp     ax, si
0x18002b89a  jz      short loc_18002B890
0x18002b89c  cmp     ax, 3Bh ; ';'
0x18002b8a0  jnz     loc_18002BA22
0x18002b8a6  add     rdi, 2
0x18002b8aa  movzx   eax, word ptr [rdi]
0x18002b8ad  cmp     ax, si
0x18002b8b0  jz      short loc_18002B8A6
0x18002b8b2  cmp     ax, 3Bh ; ';'
0x18002b8b6  jz      loc_18002B951
0x18002b8bc  cmp     ax, si
0x18002b8bf  jnz     short loc_18002B8CA
0x18002b8c1  add     rdi, 2
0x18002b8c5  cmp     [rdi], si
0x18002b8c8  jz      short loc_18002B8C1
0x18002b8ca  xor     esi, esi
0x18002b8cc  lea     rax, off_180027120; "RC"
0x18002b8d3  mov     r12d, esi
0x18002b8d6  shl     r12, 4
0x18002b8da  mov     rcx, rdi; Str1
0x18002b8dd  mov     r8d, [r12+rax+8]; MaxCount
0x18002b8e2  mov     rdx, [r12+rax]; Str2
0x18002b8e6  call    cs:__imp__wcsnicmp
0x18002b8ed  nop     dword ptr [rax+rax+00h]
0x18002b8f2  test    eax, eax
0x18002b8f4  jz      short loc_18002B921
0x18002b8f6  inc     esi
0x18002b8f8  cmp     esi, 8
0x18002b8fb  jb      short loc_18002B8CC
0x18002b8fd  lea     r8, [rbp+arg_0]
0x18002b901  mov     [rbp+arg_18], rdi
0x18002b905  lea     rdx, [rbp+arg_18]
0x18002b909  mov     rcx, rdi
0x18002b90c  call    SepSddlParseWideStringUlong
0x18002b911  cmp     [rbp+arg_18], rdi
0x18002b915  jz      loc_18002BA22
0x18002b91b  mov     rdi, [rbp+arg_18]
0x18002b91f  jmp     short loc_18002B93C
0x18002b921  mov     eax, dword ptr [rbp+arg_0]
0x18002b924  lea     rcx, off_180027120; "RC"
0x18002b92b  or      eax, [r12+rcx+0Ch]
0x18002b930  mov     dword ptr [rbp+arg_0], eax
0x18002b933  mov     eax, [r12+rcx+8]
0x18002b938  lea     rdi, [rdi+rax*2]
0x18002b93c  movzx   eax, word ptr [rdi]
0x18002b93f  mov     si, 20h ; ' '
0x18002b943  cmp     ax, 3Bh ; ';'
0x18002b947  jnz     loc_18002B8BC
0x18002b94d  mov     r12d, dword ptr [rbp+arg_0]
0x18002b951  lea     rcx, [rdi+2]
0x18002b955  test    ebx, ebx
0x18002b957  jnz     loc_18002BA25
0x18002b95d  lea     edx, [rbx+2]
0x18002b960  jmp     short loc_18002B966
0x18002b962  add     rcx, 2
0x18002b966  movzx   eax, word ptr [rcx]
0x18002b969  cmp     ax, si
0x18002b96c  jz      short loc_18002B962
0x18002b96e  cmp     ax, 3Bh ; ';'
0x18002b972  cmovnz  ebx, r15d
0x18002b976  add     rcx, 2
0x18002b97a  sub     edx, 1
0x18002b97d  jnz     short loc_18002B966
0x18002b97f  test    ebx, ebx
0x18002b981  jnz     loc_18002BA25
0x18002b987  jmp     short loc_18002B98D
0x18002b989  add     rcx, 2; Str1
0x18002b98d  cmp     [rcx], si
0x18002b990  jz      short loc_18002B989
0x18002b992  lea     r8, [rbp+arg_0]
0x18002b996  mov     [rbp+arg_0], 0
0x18002b99e  lea     rdx, [rbp+var_18]
0x18002b9a2  call    SepSddlGetSidForString
0x18002b9a7  mov     ebx, eax
0x18002b9a9  test    eax, eax
0x18002b9ab  jnz     short loc_18002BA1D
0x18002b9ad  mov     rsi, [rbp+arg_0]
0x18002b9b1  test    rsi, rsi
0x18002b9b4  jnz     short loc_18002B9C1
0x18002b9b6  mov     ebx, 0C0000077h
0x18002b9bb  jmp     short loc_18002BA25
0x18002b9bd  add     rsi, 2
0x18002b9c1  movzx   eax, word ptr [rsi]
0x18002b9c4  cmp     ax, 20h ; ' '
0x18002b9c8  jz      short loc_18002B9BD
0x18002b9ca  cmp     ax, 29h ; ')'
0x18002b9ce  jnz     short loc_18002B9B6
0x18002b9d0  mov     rcx, [rbp+var_18]
0x18002b9d4  mov     edi, [rbp+arg_8]
0x18002b9d7  test    rcx, rcx
0x18002b9da  jz      short loc_18002BA01
0x18002b9dc  mov     [rsp+58h+Sid], rcx; Sid
0x18002b9e1  lea     rdx, [rbp+arg_10]; int
0x18002b9e5  mov     eax, r13d
0x18002b9e8  mov     rcx, r14; int
0x18002b9eb  sub     eax, edi
0x18002b9ed  mov     [rsp+58h+var_30], eax; int
0x18002b9f1  mov     [rsp+58h+AccessMask], r12d; AccessMask
0x18002b9f6  call    SepSddlAddAceToAcl
0x18002b9fb  mov     ebx, eax
0x18002b9fd  test    eax, eax
0x18002b9ff  jnz     short loc_18002BA25
0x18002ba01  add     rsi, 2
0x18002ba05  cmp     word ptr [rsi], 28h ; '('
0x18002ba09  jnz     short loc_18002BA0F
0x18002ba0b  add     rsi, 2
0x18002ba0f  inc     edi
0x18002ba11  mov     [rbp+arg_8], edi
0x18002ba14  cmp     edi, r13d
0x18002ba17  jb      loc_18002B835
0x18002ba1d  mov     ecx, [rbp+arg_10]
0x18002ba20  jmp     short loc_18002BA2F
0x18002ba22  mov     ebx, r15d
0x18002ba25  mov     rax, [r14]
0x18002ba28  jmp     short loc_18002BA36
0x18002ba2a  mov     ecx, 8
0x18002ba2f  mov     rax, [r14]
0x18002ba32  test    ebx, ebx
0x18002ba34  jz      short loc_18002BA50
0x18002ba36  xor     edx, edx; Tag
0x18002ba38  mov     rcx, rax; P
0x18002ba3b  call    cs:__imp_ExFreePoolWithTag
0x18002ba42  nop     dword ptr [rax+rax+00h]
0x18002ba47  mov     qword ptr [r14], 0
0x18002ba4e  jmp     short loc_18002BA5B
0x18002ba50  mov     [rax+2], cx
0x18002ba54  jmp     short loc_18002BA5B
0x18002ba56  mov     ebx, 0C000000Dh
0x18002ba5b  mov     eax, ebx
0x18002ba5d  add     rsp, 58h
0x18002ba61  pop     r15
0x18002ba63  pop     r14
0x18002ba65  pop     r13
0x18002ba67  pop     r12
0x18002ba69  pop     rdi
0x18002ba6a  pop     rsi
0x18002ba6b  pop     rbx
0x18002ba6c  pop     rbp
0x18002ba6d  retn
```
