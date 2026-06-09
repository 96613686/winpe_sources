# CStorageProviderInfo::SetLogoPath(ushort const *)

- ea: `0x18000af70`
- end: `0x18000b172`
- name: `?SetLogoPath@CStorageProviderInfo@@UEAAJPEBG@Z`
- size: `514`
- prototype: `__int64 __fastcall(CStorageProviderInfo *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800077c8`
- `0x18000af70`
- `0x18000b9b0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000afe6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000afe6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000b0d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000b0d1`

## string_xrefs

- `0x18000b0e7`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`

## pseudocode

```c
__int64 __fastcall CStorageProviderInfo::SetLogoPath(CStorageProviderInfo *this, const unsigned __int16 *a2)
{
  char *v2; // r14
  const unsigned __int16 *v3; // rbx
  __int64 v4; // rax
  unsigned __int64 v5; // rbp
  unsigned __int64 v6; // rdi
  unsigned __int64 v7; // r8
  _WORD *v8; // rax
  int v9; // r15d
  _WORD *v10; // rdx
  unsigned __int64 v11; // rcx
  _WORD *v12; // rcx
  unsigned __int64 v14; // rsi
  LPVOID v15; // rax
  int v16; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v2 = (char *)this + 232;
  v3 = a2;
  if ( !a2 )
  {
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((char *)this + 232);
    return 0;
  }
  v4 = -1;
  v5 = -1;
  do
    ++v5;
  while ( a2[v5] );
  v6 = v5 + 1;
  if ( v5 + 1 < v5 )
    goto LABEL_22;
  v7 = *((_QWORD *)this + 31);
  if ( v7 == -1 )
  {
    if ( *((_QWORD *)this + 30) == -1 )
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
      *((_QWORD *)this + 30) = v4;
    }
    else
    {
      v4 = *((_QWORD *)this + 30);
    }
    v7 = v4 + 1;
    if ( !*(_QWORD *)v2 )
      v7 = 0;
    *((_QWORD *)this + 31) = v7;
  }
  if ( !v7 )
  {
    if ( is_mul_ok(v6, 2u) )
    {
      v8 = CoTaskMemAlloc(2 * v6);
      if ( v8 )
      {
        v9 = 0;
        *((_QWORD *)v2 + 2) = v6;
        *(_QWORD *)v2 = v8;
        *v8 = 0;
      }
      else
      {
        v9 = -2147024882;
      }
      if ( v9 < 0 )
        goto LABEL_35;
      goto LABEL_11;
    }
LABEL_22:
    v9 = -2147024362;
    goto LABEL_23;
  }
  v9 = 0;
  if ( v6 > v7 )
  {
    v14 = 2 * v7;
    if ( is_mul_ok(v7, 2u) )
    {
      if ( v7 > 0x800 )
        v14 = v7 + 2048;
      if ( v6 > v14 )
        v14 = v5 + 1;
      v15 = CoTaskMemRealloc(*(LPVOID *)v2, 2 * v14);
      if ( !v15 )
      {
        v9 = -2147024882;
        goto LABEL_35;
      }
      *((_QWORD *)v2 + 2) = v14;
      *(_QWORD *)v2 = v15;
      goto LABEL_11;
    }
    goto LABEL_22;
  }
LABEL_11:
  if ( v5 != -1 )
  {
    v10 = *(_WORD **)v2;
    if ( v6 > 0x7FFFFFFF )
    {
      *v10 = 0;
    }
    else if ( v5 > 0x7FFFFFFE )
    {
      *v10 = 0;
    }
    else
    {
      v11 = v5;
      do
      {
        if ( !v11 )
          break;
        if ( !*v3 )
          break;
        *v10++ = *v3++;
        --v11;
        --v6;
      }
      while ( v6 );
      v12 = v10 - 1;
      if ( v6 )
        v12 = v10;
      *v12 = 0;
    }
  }
  *((_QWORD *)v2 + 1) = v5;
LABEL_23:
  if ( v9 >= 0 )
    return 0;
LABEL_35:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x45F,
    (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
    (const char *)(unsigned int)v9,
    v16);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000af70  push    rbx
0x18000af72  push    rbp
0x18000af73  push    rsi
0x18000af74  push    rdi
0x18000af75  push    r14
0x18000af77  push    r15
0x18000af79  sub     rsp, 28h
0x18000af7d  lea     r14, [rcx+0E8h]
0x18000af84  mov     rbx, rdx
0x18000af87  test    rdx, rdx
0x18000af8a  jz      loc_18000B083
0x18000af90  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000af97  mov     rbp, rax
0x18000af9a  nop     word ptr [rax+rax+00h]
0x18000afa0  inc     rbp
0x18000afa3  cmp     word ptr [rdx+rbp*2], 0
0x18000afa8  jnz     short loc_18000AFA0
0x18000afaa  lea     rdi, [rbp+1]
0x18000afae  cmp     rdi, rbp
0x18000afb1  jb      loc_18000B069
0x18000afb7  mov     r8, [r14+10h]
0x18000afbb  cmp     r8, rax
0x18000afbe  jz      loc_18000B120
0x18000afc4  test    r8, r8
0x18000afc7  jnz     loc_18000B098
0x18000afcd  mov     eax, 2
0x18000afd2  mov     [rsp+58h+arg_0], r8
0x18000afd7  mul     rdi
0x18000afda  test    rdx, rdx
0x18000afdd  jnz     loc_18000B069
0x18000afe3  mov     rcx, rax; cb
0x18000afe6  call    cs:__imp_CoTaskMemAlloc
0x18000afec  test    rax, rax
0x18000afef  jz      loc_18000B08D
0x18000aff5  xor     r15d, r15d
0x18000aff8  mov     [r14+10h], rdi
0x18000affc  xor     ecx, ecx
0x18000affe  mov     [r14], rax
0x18000b001  mov     [rax], cx
0x18000b004  test    r15d, r15d
0x18000b007  js      loc_18000B0E2
0x18000b00d  test    rdi, rdi
0x18000b010  jz      short loc_18000B063
0x18000b012  mov     rdx, [r14]
0x18000b015  cmp     rdi, 7FFFFFFFh
0x18000b01c  ja      loc_18000B15E
0x18000b022  cmp     rbp, 7FFFFFFEh
0x18000b029  ja      loc_18000B168
0x18000b02f  mov     rcx, rbp
0x18000b032  test    rcx, rcx
0x18000b035  jz      short loc_18000B053
0x18000b037  movzx   eax, word ptr [rbx]
0x18000b03a  test    ax, ax
0x18000b03d  jz      short loc_18000B053
0x18000b03f  mov     [rdx], ax
0x18000b042  add     rbx, 2
0x18000b046  add     rdx, 2
0x18000b04a  dec     rcx
0x18000b04d  sub     rdi, 1
0x18000b051  jnz     short loc_18000B032
0x18000b053  test    rdi, rdi
0x18000b056  lea     rcx, [rdx-2]
0x18000b05a  cmovnz  rcx, rdx
0x18000b05e  xor     eax, eax
0x18000b060  mov     [rcx], ax
0x18000b063  mov     [r14+8], rbp
0x18000b067  jmp     short loc_18000B06F
0x18000b069  mov     r15d, 80070216h
0x18000b06f  test    r15d, r15d
0x18000b072  js      short loc_18000B0E2
0x18000b074  xor     eax, eax
0x18000b076  add     rsp, 28h
0x18000b07a  pop     r15
0x18000b07c  pop     r14
0x18000b07e  pop     rdi
0x18000b07f  pop     rsi
0x18000b080  pop     rbp
0x18000b081  pop     rbx
0x18000b082  retn
0x18000b083  mov     rcx, r14
0x18000b086  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18000b08b  jmp     short loc_18000B074
0x18000b08d  mov     r15d, 8007000Eh
0x18000b093  jmp     loc_18000B004
0x18000b098  xor     r15d, r15d
0x18000b09b  cmp     rdi, r8
0x18000b09e  jbe     loc_18000B00D
0x18000b0a4  mov     eax, 2
0x18000b0a9  mul     r8
0x18000b0ac  mov     rsi, rax
0x18000b0af  test    rdx, rdx
0x18000b0b2  jnz     short loc_18000B069
0x18000b0b4  mov     rcx, rax
0x18000b0b7  sub     rcx, r8
0x18000b0ba  cmp     rcx, 800h
0x18000b0c1  ja      short loc_18000B10B
0x18000b0c3  mov     rcx, [r14]; pv
0x18000b0c6  cmp     rdi, rsi
0x18000b0c9  cmova   rsi, rdi
0x18000b0cd  lea     rdx, [rsi+rsi]; cb
0x18000b0d1  call    cs:__imp_CoTaskMemRealloc
0x18000b0d7  test    rax, rax
0x18000b0da  jnz     short loc_18000B114
0x18000b0dc  mov     r15d, 8007000Eh
0x18000b0e2  mov     rcx, [rsp+58h]; this
0x18000b0e7  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\fileexplorer\\windo"...
0x18000b0ee  mov     r9d, r15d; char *
0x18000b0f1  mov     edx, 45Fh; void *
0x18000b0f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b0fb  mov     eax, r15d
0x18000b0fe  add     rsp, 28h
0x18000b102  pop     r15
0x18000b104  pop     r14
0x18000b106  pop     rdi
0x18000b107  pop     rsi
0x18000b108  pop     rbp
0x18000b109  pop     rbx
0x18000b10a  retn
0x18000b10b  lea     rsi, [r8+800h]
0x18000b112  jmp     short loc_18000B0C3
0x18000b114  mov     [r14+10h], rsi
0x18000b118  mov     [r14], rax
0x18000b11b  jmp     loc_18000B00D
0x18000b120  mov     rcx, [r14+8]
0x18000b124  cmp     rcx, rax
0x18000b127  jnz     short loc_18000B145
0x18000b129  mov     rcx, [r14]
0x18000b12c  test    rcx, rcx
0x18000b12f  jnz     short loc_18000B135
0x18000b131  xor     eax, eax
0x18000b133  jmp     short loc_18000B13F
0x18000b135  inc     rax
0x18000b138  cmp     word ptr [rcx+rax*2], 0
0x18000b13d  jnz     short loc_18000B135
0x18000b13f  mov     [r14+8], rax
0x18000b143  jmp     short loc_18000B148
0x18000b145  mov     rax, rcx
0x18000b148  lea     r8, [rax+1]
0x18000b14c  xor     eax, eax
0x18000b14e  cmp     [r14], rax
0x18000b151  cmovz   r8, rax
0x18000b155  mov     [r14+10h], r8
0x18000b159  jmp     loc_18000AFC4
0x18000b15e  xor     eax, eax
0x18000b160  mov     [rdx], ax
0x18000b163  jmp     loc_18000B063
0x18000b168  xor     eax, eax
0x18000b16a  mov     [rdx], ax
0x18000b16d  jmp     loc_18000B063
```
