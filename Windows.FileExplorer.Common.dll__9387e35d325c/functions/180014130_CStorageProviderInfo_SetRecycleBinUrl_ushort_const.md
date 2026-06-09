# CStorageProviderInfo::SetRecycleBinUrl(ushort const *)

- ea: `0x180014130`
- end: `0x1800142ff`
- name: `?SetRecycleBinUrl@CStorageProviderInfo@@UEAAJPEBG@Z`
- size: `463`
- prototype: `__int64 __fastcall(CStorageProviderInfo *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800077c8`
- `0x18000b9b0`
- `0x180014130`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800141aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800141aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18001427b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18001427b`

## string_xrefs

- `0x18001429c`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`

## pseudocode

```c
__int64 __fastcall CStorageProviderInfo::SetRecycleBinUrl(CStorageProviderInfo *this, const unsigned __int16 *a2)
{
  char *v2; // rdi
  const unsigned __int16 *v3; // r14
  __int64 v4; // rcx
  unsigned __int64 v5; // rbp
  unsigned __int64 v6; // rsi
  int v7; // ebx
  unsigned __int64 v9; // r8
  _WORD *v10; // rax
  _WORD *v11; // rdx
  unsigned __int64 v12; // rax
  _WORD *v13; // rcx
  unsigned __int64 v14; // rbx
  LPVOID v15; // rax
  int v16; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v2 = (char *)this + 192;
  v3 = a2;
  if ( !a2 )
  {
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((char *)this + 192);
    return 0;
  }
  v4 = -1;
  v5 = -1;
  do
    ++v5;
  while ( a2[v5] );
  v6 = v5 + 1;
  if ( v5 + 1 < v5 )
    goto LABEL_5;
  v9 = *((_QWORD *)v2 + 2);
  if ( v9 == -1 )
  {
    if ( *((_QWORD *)v2 + 1) == -1 )
    {
      if ( *(_QWORD *)v2 )
      {
        do
          ++v4;
        while ( *(_WORD *)(*(_QWORD *)v2 + 2 * v4) );
      }
      else
      {
        v4 = 0;
      }
      *((_QWORD *)v2 + 1) = v4;
    }
    else
    {
      v4 = *((_QWORD *)v2 + 1);
    }
    v9 = (v4 + 1) & -(__int64)(*(_QWORD *)v2 != 0);
    *((_QWORD *)v2 + 2) = v9;
  }
  if ( v9 )
  {
    v7 = 0;
    if ( v6 <= v9 )
    {
LABEL_16:
      if ( v7 < 0 )
        goto LABEL_37;
      goto LABEL_17;
    }
    v14 = 2 * v9;
    if ( is_mul_ok(v9, 2u) )
    {
      if ( v9 > 0x800 )
        v14 = v9 + 2048;
      if ( v6 > v14 )
        v14 = v5 + 1;
      v15 = CoTaskMemRealloc(*(LPVOID *)v2, 2 * v14);
      if ( !v15 )
      {
        v7 = -2147024882;
        goto LABEL_37;
      }
      *((_QWORD *)v2 + 2) = v14;
      *(_QWORD *)v2 = v15;
      goto LABEL_13;
    }
LABEL_5:
    v7 = -2147024362;
    goto LABEL_6;
  }
  if ( !is_mul_ok(v6, 2u) )
    goto LABEL_5;
  v10 = CoTaskMemAlloc(2 * v6);
  if ( !v10 )
  {
    v7 = -2147024882;
    goto LABEL_16;
  }
  *((_QWORD *)v2 + 2) = v6;
  *(_QWORD *)v2 = v10;
  *v10 = 0;
LABEL_13:
  v7 = 0;
LABEL_17:
  if ( v5 != -1 )
  {
    v11 = *(_WORD **)v2;
    if ( v6 > 0x7FFFFFFF || v5 > 0x7FFFFFFE )
    {
      *v11 = 0;
    }
    else
    {
      v12 = v5;
      do
      {
        if ( !v12 )
          break;
        if ( !*v3 )
          break;
        *v11++ = *v3++;
        --v12;
        --v6;
      }
      while ( v6 );
      v13 = v11 - 1;
      if ( v6 )
        v13 = v11;
      *v13 = 0;
    }
  }
  *((_QWORD *)v2 + 1) = v5;
LABEL_6:
  if ( v7 >= 0 )
    return 0;
LABEL_37:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x317,
    (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
    (const char *)(unsigned int)v7,
    v16);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180014130  push    rbx
0x180014132  push    rbp
0x180014133  push    rsi
0x180014134  push    rdi
0x180014135  push    r14
0x180014137  push    r15
0x180014139  sub     rsp, 28h
0x18001413d  xor     r15d, r15d
0x180014140  lea     rdi, [rcx+0C0h]
0x180014147  mov     r14, rdx
0x18001414a  test    rdx, rdx
0x18001414d  jz      short loc_1800141C5
0x18001414f  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180014153  mov     rbp, rcx
0x180014156  inc     rbp
0x180014159  cmp     [rdx+rbp*2], r15w
0x18001415e  jnz     short loc_180014156
0x180014160  lea     rsi, [rbp+1]
0x180014164  cmp     rsi, rbp
0x180014167  jnb     short loc_180014185
0x180014169  mov     ebx, 80070216h
0x18001416e  test    ebx, ebx
0x180014170  js      loc_180014297
0x180014176  xor     eax, eax
0x180014178  add     rsp, 28h
0x18001417c  pop     r15
0x18001417e  pop     r14
0x180014180  pop     rdi
0x180014181  pop     rsi
0x180014182  pop     rbp
0x180014183  pop     rbx
0x180014184  retn
0x180014185  mov     r8, [rdi+10h]
0x180014189  cmp     r8, rcx
0x18001418c  jz      loc_1800142B7
0x180014192  test    r8, r8
0x180014195  jnz     loc_18001423B
0x18001419b  lea     eax, [r8+2]
0x18001419f  mul     rsi
0x1800141a2  test    rdx, rdx
0x1800141a5  jnz     short loc_180014169
0x1800141a7  mov     rcx, rax; cb
0x1800141aa  call    cs:__imp_CoTaskMemAlloc
0x1800141b0  test    rax, rax
0x1800141b3  jz      short loc_1800141CF
0x1800141b5  mov     [rdi+10h], rsi
0x1800141b9  mov     [rdi], rax
0x1800141bc  mov     [rax], r15w
0x1800141c0  mov     ebx, r15d
0x1800141c3  jmp     short loc_1800141DC
0x1800141c5  mov     rcx, rdi
0x1800141c8  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800141cd  jmp     short loc_180014176
0x1800141cf  mov     ebx, 8007000Eh
0x1800141d4  test    ebx, ebx
0x1800141d6  js      loc_180014297
0x1800141dc  test    rsi, rsi
0x1800141df  jz      short loc_180014232
0x1800141e1  mov     rdx, [rdi]
0x1800141e4  cmp     rsi, 7FFFFFFFh
0x1800141eb  ja      loc_1800142F6
0x1800141f1  cmp     rbp, 7FFFFFFEh
0x1800141f8  ja      loc_1800142F6
0x1800141fe  mov     rax, rbp
0x180014201  test    rax, rax
0x180014204  jz      short loc_180014223
0x180014206  movzx   ecx, word ptr [r14]
0x18001420a  test    cx, cx
0x18001420d  jz      short loc_180014223
0x18001420f  mov     [rdx], cx
0x180014212  add     r14, 2
0x180014216  add     rdx, 2
0x18001421a  dec     rax
0x18001421d  sub     rsi, 1
0x180014221  jnz     short loc_180014201
0x180014223  test    rsi, rsi
0x180014226  lea     rcx, [rdx-2]
0x18001422a  cmovnz  rcx, rdx
0x18001422e  mov     [rcx], r15w
0x180014232  mov     [rdi+8], rbp
0x180014236  jmp     loc_18001416E
0x18001423b  mov     ebx, r15d
0x18001423e  cmp     rsi, r8
0x180014241  jbe     short loc_1800141D4
0x180014243  mov     eax, 2
0x180014248  mul     r8
0x18001424b  mov     rbx, rax
0x18001424e  test    rdx, rdx
0x180014251  jnz     loc_180014169
0x180014257  mov     rcx, rax
0x18001425a  sub     rcx, r8
0x18001425d  cmp     rcx, 800h
0x180014264  jbe     short loc_18001426D
0x180014266  lea     rbx, [r8+800h]
0x18001426d  mov     rcx, [rdi]; pv
0x180014270  cmp     rsi, rbx
0x180014273  cmova   rbx, rsi
0x180014277  lea     rdx, [rbx+rbx]; cb
0x18001427b  call    cs:__imp_CoTaskMemRealloc
0x180014281  test    rax, rax
0x180014284  jz      short loc_180014292
0x180014286  mov     [rdi+10h], rbx
0x18001428a  mov     [rdi], rax
0x18001428d  jmp     loc_1800141C0
0x180014292  mov     ebx, 8007000Eh
0x180014297  mov     rcx, [rsp+58h]; this
0x18001429c  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\fileexplorer\\windo"...
0x1800142a3  mov     r9d, ebx; char *
0x1800142a6  mov     edx, 317h; void *
0x1800142ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800142b0  mov     eax, ebx
0x1800142b2  jmp     loc_180014178
0x1800142b7  cmp     [rdi+8], rcx
0x1800142bb  jnz     short loc_1800142DA
0x1800142bd  mov     rax, [rdi]
0x1800142c0  test    rax, rax
0x1800142c3  jnz     short loc_1800142CA
0x1800142c5  mov     rcx, r15
0x1800142c8  jmp     short loc_1800142D4
0x1800142ca  inc     rcx
0x1800142cd  cmp     [rax+rcx*2], r15w
0x1800142d2  jnz     short loc_1800142CA
0x1800142d4  mov     [rdi+8], rcx
0x1800142d8  jmp     short loc_1800142DE
0x1800142da  mov     rcx, [rdi+8]
0x1800142de  mov     rax, [rdi]
0x1800142e1  inc     rcx
0x1800142e4  neg     rax
0x1800142e7  sbb     r8, r8
0x1800142ea  and     r8, rcx
0x1800142ed  mov     [rdi+10h], r8
0x1800142f1  jmp     loc_180014192
0x1800142f6  mov     [rdx], r15w
0x1800142fa  jmp     loc_180014232
```
