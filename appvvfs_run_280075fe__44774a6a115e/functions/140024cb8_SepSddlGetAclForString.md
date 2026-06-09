# SepSddlGetAclForString

- ea: `0x140024cb8`
- end: `0x14002506f`
- name: `SepSddlGetAclForString`
- size: `951`
- prototype: `__int64 __fastcall(wchar_t *Str1, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x140024bd4`

## callees

- `0x140014000`
- `0x140024ae0`
- `0x140024cb8`
- `0x140025078`
- `0x14002512c`

## import_xrefs

- `ntoskrnl!wcschr` at `0x140024ce3`
- `ntoskrnl!wcschr` at `0x140024ce3`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140024d9a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140024ddf`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140024d9a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140024ddf`
- `ntoskrnl!_wcsnicmp` at `0x140024e76`
- `ntoskrnl!_wcsnicmp` at `0x140024ee6`
- `ntoskrnl!_wcsnicmp` at `0x140024e76`
- `ntoskrnl!_wcsnicmp` at `0x140024ee6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002503b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002503b`

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
          if ( !_wcsnicmp(j, (&off_14001F120)[v23], *((unsigned int *)&off_14001F120 + 2 * v23 + 2)) )
          {
            LODWORD(v29) = *((_DWORD *)&off_14001F120 + 2 * v23 + 3) | (unsigned int)v29;
            j += *((unsigned int *)&off_14001F120 + 2 * v23 + 2);
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
0x140024cb8  push    rbp
0x140024cba  push    rbx
0x140024cbb  push    rsi
0x140024cbc  push    rdi
0x140024cbd  push    r12
0x140024cbf  push    r13
0x140024cc1  push    r14
0x140024cc3  push    r15
0x140024cc5  mov     rbp, rsp
0x140024cc8  sub     rsp, 58h
0x140024ccc  xor     r15d, r15d
0x140024ccf  mov     r14, rdx
0x140024cd2  mov     [rdx], r15
0x140024cd5  mov     rbx, r8
0x140024cd8  mov     rsi, rcx
0x140024cdb  mov     [rbp+var_18], r15
0x140024cdf  lea     edx, [r15+3Ah]; Ch
0x140024ce3  call    cs:__imp_wcschr
0x140024cea  nop     dword ptr [rax+rax+00h]
0x140024cef  mov     [rbx], rax
0x140024cf2  cmp     rax, rsi
0x140024cf5  jnz     short loc_140024D01
0x140024cf7  mov     eax, 0C000000Dh
0x140024cfc  jmp     loc_14002505D
0x140024d01  mov     r8d, r15d
0x140024d04  test    rax, rax
0x140024d07  jnz     short loc_140024D1D
0x140024d09  or      rax, 0FFFFFFFFFFFFFFFFh
0x140024d0d  inc     rax
0x140024d10  cmp     [rsi+rax*2], r15w
0x140024d15  jnz     short loc_140024D0D
0x140024d17  lea     rax, [rsi+rax*2]
0x140024d1b  jmp     short loc_140024D21
0x140024d1d  add     rax, 0FFFFFFFFFFFFFFFEh
0x140024d21  mov     [rbx], rax
0x140024d24  mov     rcx, rsi
0x140024d27  mov     r9d, r15d
0x140024d2a  mov     r10d, 1
0x140024d30  cmp     rsi, rax
0x140024d33  jnb     short loc_140024D54
0x140024d35  movzx   edx, word ptr [rcx]
0x140024d38  cmp     dx, 3Bh ; ';'
0x140024d3c  jnz     short loc_140024D43
0x140024d3e  add     r8d, r10d
0x140024d41  jmp     short loc_140024D4B
0x140024d43  cmp     dx, 20h ; ' '
0x140024d47  cmovnz  r9d, r10d
0x140024d4b  add     rcx, 2
0x140024d4f  cmp     rcx, rax
0x140024d52  jb      short loc_140024D35
0x140024d54  mov     eax, 0CCCCCCCDh
0x140024d59  mul     r8d
0x140024d5c  mov     r13d, edx
0x140024d5f  shr     r13d, 2
0x140024d63  lea     ecx, ds:0[r13*4]
0x140024d6b  add     ecx, r13d
0x140024d6e  cmp     r8d, ecx
0x140024d71  jnz     loc_140025056
0x140024d77  test    r8d, r8d
0x140024d7a  jnz     short loc_140024D85
0x140024d7c  test    r9d, r9d
0x140024d7f  jnz     loc_140025056
0x140024d85  mov     ebx, r15d
0x140024d88  mov     r8d, 6C416553h; Tag
0x140024d8e  mov     ecx, r10d; PoolType
0x140024d91  test    r13d, r13d
0x140024d94  jnz     short loc_140024DBA
0x140024d96  lea     edx, [r13+8]; NumberOfBytes
0x140024d9a  call    cs:__imp_ExAllocatePoolWithTag
0x140024da1  nop     dword ptr [rax+rax+00h]
0x140024da6  mov     [r14], rax
0x140024da9  test    rax, rax
0x140024dac  jz      short loc_140024DF6
0x140024dae  mov     qword ptr [rax], 80002h
0x140024db5  jmp     loc_14002505B
0x140024dba  mov     eax, 0FFFFh
0x140024dbf  lea     r15d, ds:0[r13*2]
0x140024dc7  add     r15d, r13d
0x140024dca  shl     r15d, 4
0x140024dce  add     r15d, 8
0x140024dd2  cmp     r15d, eax
0x140024dd5  cmova   r15d, eax
0x140024dd9  mov     edx, r15d; NumberOfBytes
0x140024ddc  mov     r12d, r15d
0x140024ddf  call    cs:__imp_ExAllocatePoolWithTag
0x140024de6  nop     dword ptr [rax+rax+00h]
0x140024deb  mov     [r14], rax
0x140024dee  mov     rdi, rax
0x140024df1  test    rax, rax
0x140024df4  jnz     short loc_140024E00
0x140024df6  mov     ebx, 0C000009Ah
0x140024dfb  jmp     loc_14002505B
0x140024e00  mov     r8, r12; Size
0x140024e03  mov     [rbp+arg_10], 8
0x140024e0a  xor     edx, edx; Val
0x140024e0c  mov     rcx, rdi; void *
0x140024e0f  call    memset
0x140024e14  xor     eax, eax
0x140024e16  mov     word ptr [rdi], 2
0x140024e1b  mov     [rdi+2], r15w
0x140024e20  mov     [rdi+4], eax
0x140024e23  mov     [rbp+arg_8], eax
0x140024e26  test    r13d, r13d
0x140024e29  jz      loc_14002502A
0x140024e2f  mov     r15d, 0C000000Dh
0x140024e35  xor     r12d, r12d
0x140024e38  mov     dword ptr [rbp+arg_0], r12d
0x140024e3c  jmp     short loc_140024E42
0x140024e3e  add     rsi, 2
0x140024e42  movzx   eax, word ptr [rsi]
0x140024e45  cmp     ax, 20h ; ' '
0x140024e49  jz      short loc_140024E3E
0x140024e4b  lea     rdi, [rsi+2]
0x140024e4f  cmp     ax, 28h ; '('
0x140024e53  cmovnz  rdi, rsi
0x140024e57  mov     si, 20h ; ' '
0x140024e5b  jmp     short loc_140024E61
0x140024e5d  add     rdi, 2
0x140024e61  cmp     [rdi], si
0x140024e64  jz      short loc_140024E5D
0x140024e66  mov     r8d, 1; MaxCount
0x140024e6c  lea     rdx, aA; "A"
0x140024e73  mov     rcx, rdi; Str1
0x140024e76  call    cs:__imp__wcsnicmp
0x140024e7d  nop     dword ptr [rax+rax+00h]
0x140024e82  test    eax, eax
0x140024e84  jnz     loc_140025022
0x140024e8a  add     rdi, 4
0x140024e8e  jmp     short loc_140024E94
0x140024e90  add     rdi, 2
0x140024e94  movzx   eax, word ptr [rdi]
0x140024e97  cmp     ax, si
0x140024e9a  jz      short loc_140024E90
0x140024e9c  cmp     ax, 3Bh ; ';'
0x140024ea0  jnz     loc_140025022
0x140024ea6  add     rdi, 2
0x140024eaa  movzx   eax, word ptr [rdi]
0x140024ead  cmp     ax, si
0x140024eb0  jz      short loc_140024EA6
0x140024eb2  cmp     ax, 3Bh ; ';'
0x140024eb6  jz      loc_140024F51
0x140024ebc  cmp     ax, si
0x140024ebf  jnz     short loc_140024ECA
0x140024ec1  add     rdi, 2
0x140024ec5  cmp     [rdi], si
0x140024ec8  jz      short loc_140024EC1
0x140024eca  xor     esi, esi
0x140024ecc  lea     rax, off_14001F120; "RC"
0x140024ed3  mov     r12d, esi
0x140024ed6  shl     r12, 4
0x140024eda  mov     rcx, rdi; Str1
0x140024edd  mov     r8d, [r12+rax+8]; MaxCount
0x140024ee2  mov     rdx, [r12+rax]; Str2
0x140024ee6  call    cs:__imp__wcsnicmp
0x140024eed  nop     dword ptr [rax+rax+00h]
0x140024ef2  test    eax, eax
0x140024ef4  jz      short loc_140024F21
0x140024ef6  inc     esi
0x140024ef8  cmp     esi, 8
0x140024efb  jb      short loc_140024ECC
0x140024efd  lea     r8, [rbp+arg_0]
0x140024f01  mov     [rbp+arg_18], rdi
0x140024f05  lea     rdx, [rbp+arg_18]
0x140024f09  mov     rcx, rdi
0x140024f0c  call    SepSddlParseWideStringUlong
0x140024f11  cmp     [rbp+arg_18], rdi
0x140024f15  jz      loc_140025022
0x140024f1b  mov     rdi, [rbp+arg_18]
0x140024f1f  jmp     short loc_140024F3C
0x140024f21  mov     eax, dword ptr [rbp+arg_0]
0x140024f24  lea     rcx, off_14001F120; "RC"
0x140024f2b  or      eax, [r12+rcx+0Ch]
0x140024f30  mov     dword ptr [rbp+arg_0], eax
0x140024f33  mov     eax, [r12+rcx+8]
0x140024f38  lea     rdi, [rdi+rax*2]
0x140024f3c  movzx   eax, word ptr [rdi]
0x140024f3f  mov     si, 20h ; ' '
0x140024f43  cmp     ax, 3Bh ; ';'
0x140024f47  jnz     loc_140024EBC
0x140024f4d  mov     r12d, dword ptr [rbp+arg_0]
0x140024f51  lea     rcx, [rdi+2]
0x140024f55  test    ebx, ebx
0x140024f57  jnz     loc_140025025
0x140024f5d  lea     edx, [rbx+2]
0x140024f60  jmp     short loc_140024F66
0x140024f62  add     rcx, 2
0x140024f66  movzx   eax, word ptr [rcx]
0x140024f69  cmp     ax, si
0x140024f6c  jz      short loc_140024F62
0x140024f6e  cmp     ax, 3Bh ; ';'
0x140024f72  cmovnz  ebx, r15d
0x140024f76  add     rcx, 2
0x140024f7a  sub     edx, 1
0x140024f7d  jnz     short loc_140024F66
0x140024f7f  test    ebx, ebx
0x140024f81  jnz     loc_140025025
0x140024f87  jmp     short loc_140024F8D
0x140024f89  add     rcx, 2; Str1
0x140024f8d  cmp     [rcx], si
0x140024f90  jz      short loc_140024F89
0x140024f92  lea     r8, [rbp+arg_0]
0x140024f96  mov     [rbp+arg_0], 0
0x140024f9e  lea     rdx, [rbp+var_18]
0x140024fa2  call    SepSddlGetSidForString
0x140024fa7  mov     ebx, eax
0x140024fa9  test    eax, eax
0x140024fab  jnz     short loc_14002501D
0x140024fad  mov     rsi, [rbp+arg_0]
0x140024fb1  test    rsi, rsi
0x140024fb4  jnz     short loc_140024FC1
0x140024fb6  mov     ebx, 0C0000077h
0x140024fbb  jmp     short loc_140025025
0x140024fbd  add     rsi, 2
0x140024fc1  movzx   eax, word ptr [rsi]
0x140024fc4  cmp     ax, 20h ; ' '
0x140024fc8  jz      short loc_140024FBD
0x140024fca  cmp     ax, 29h ; ')'
0x140024fce  jnz     short loc_140024FB6
0x140024fd0  mov     rcx, [rbp+var_18]
0x140024fd4  mov     edi, [rbp+arg_8]
0x140024fd7  test    rcx, rcx
0x140024fda  jz      short loc_140025001
0x140024fdc  mov     [rsp+58h+Sid], rcx; Sid
0x140024fe1  lea     rdx, [rbp+arg_10]; int
0x140024fe5  mov     eax, r13d
0x140024fe8  mov     rcx, r14; int
0x140024feb  sub     eax, edi
0x140024fed  mov     [rsp+58h+var_30], eax; int
0x140024ff1  mov     [rsp+58h+AccessMask], r12d; AccessMask
0x140024ff6  call    SepSddlAddAceToAcl
0x140024ffb  mov     ebx, eax
0x140024ffd  test    eax, eax
0x140024fff  jnz     short loc_140025025
0x140025001  add     rsi, 2
0x140025005  cmp     word ptr [rsi], 28h ; '('
0x140025009  jnz     short loc_14002500F
0x14002500b  add     rsi, 2
0x14002500f  inc     edi
0x140025011  mov     [rbp+arg_8], edi
0x140025014  cmp     edi, r13d
0x140025017  jb      loc_140024E35
0x14002501d  mov     ecx, [rbp+arg_10]
0x140025020  jmp     short loc_14002502F
0x140025022  mov     ebx, r15d
0x140025025  mov     rax, [r14]
0x140025028  jmp     short loc_140025036
0x14002502a  mov     ecx, 8
0x14002502f  mov     rax, [r14]
0x140025032  test    ebx, ebx
0x140025034  jz      short loc_140025050
0x140025036  xor     edx, edx; Tag
0x140025038  mov     rcx, rax; P
0x14002503b  call    cs:__imp_ExFreePoolWithTag
0x140025042  nop     dword ptr [rax+rax+00h]
0x140025047  mov     qword ptr [r14], 0
0x14002504e  jmp     short loc_14002505B
0x140025050  mov     [rax+2], cx
0x140025054  jmp     short loc_14002505B
0x140025056  mov     ebx, 0C000000Dh
0x14002505b  mov     eax, ebx
0x14002505d  add     rsp, 58h
0x140025061  pop     r15
0x140025063  pop     r14
0x140025065  pop     r13
0x140025067  pop     r12
0x140025069  pop     rdi
0x14002506a  pop     rsi
0x14002506b  pop     rbx
0x14002506c  pop     rbp
0x14002506d  retn
```
