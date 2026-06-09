# BuildADsParentPath(ushort const *,ushort *,unsigned __int64,ushort *,unsigned __int64)

- ea: `0x180014fa4`
- end: `0x1800151f6`
- name: `?BuildADsParentPath@@YAJPEBGPEAG_K12@Z`
- size: `594`
- prototype: `__int64 __fastcall(const unsigned __int16 *, wchar_t *Destination, rsize_t SizeInWords, wchar_t *, unsigned __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path`

## callers

- `0x180015664`

## callees

- `0x180014fa4`
- `0x18001537c`
- `0x18001608c`
- `0x1800160d0`
- `0x18001d66a`
- `0x18001d6c0`

## import_xrefs

- `msvcrt!swprintf_s` at `0x180015053`
- `msvcrt!swprintf_s` at `0x180015067`
- `msvcrt!swprintf_s` at `0x1800150be`
- `msvcrt!swprintf_s` at `0x18001518c`
- `msvcrt!swprintf_s` at `0x180015053`
- `msvcrt!swprintf_s` at `0x180015067`
- `msvcrt!swprintf_s` at `0x1800150be`
- `msvcrt!swprintf_s` at `0x18001518c`
- `msvcrt!wcscat_s` at `0x1800150e5`
- `msvcrt!wcscat_s` at `0x18001510e`
- `msvcrt!wcscat_s` at `0x180015121`
- `msvcrt!wcscat_s` at `0x180015139`
- `msvcrt!wcscat_s` at `0x1800150e5`
- `msvcrt!wcscat_s` at `0x18001510e`
- `msvcrt!wcscat_s` at `0x180015121`
- `msvcrt!wcscat_s` at `0x180015139`
- `msvcrt!wcscpy_s` at `0x18001509a`
- `msvcrt!wcscpy_s` at `0x1800151b6`
- `msvcrt!wcscpy_s` at `0x18001509a`
- `msvcrt!wcscpy_s` at `0x1800151b6`
- `ACTIVEDS!__imp_FreeADsStr` at `0x1800151cb`
- `ACTIVEDS!__imp_FreeADsStr` at `0x1800151cb`

## pseudocode

```c
__int64 __fastcall BuildADsParentPath(
        const unsigned __int16 *a1,
        wchar_t *Destination,
        rsize_t SizeInWords,
        wchar_t *a4)
{
  wchar_t *v7; // r12
  unsigned int v8; // r15d
  unsigned int v9; // ebx
  int v10; // r14d
  unsigned __int64 v11; // rax
  unsigned int v12; // r13d
  __int64 v13; // r12
  const wchar_t *v14; // r8
  rsize_t v15; // rdx
  wchar_t *v16; // rcx
  const wchar_t *v17; // r8
  __int64 v18; // rcx
  unsigned __int64 v19; // rax
  int v21; // [rsp+30h] [rbp-D0h]
  _BYTE v23[8]; // [rsp+40h] [rbp-C0h] BYREF
  LPWSTR pStr; // [rsp+48h] [rbp-B8h]
  __int64 v25; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t *Source; // [rsp+68h] [rbp-98h]
  int v27; // [rsp+280h] [rbp+180h]
  __int64 v28; // [rsp+288h] [rbp+188h]

  v7 = a4;
  memset_0(&v25, 0, 0x230u);
  CLexer::CLexer((CLexer *)v23, a1);
  memset_0(&v25, 0, 0x230u);
  v8 = 0;
  v21 = ADsObject((struct CLexer *)v23, (struct _objectinfo *)&v25);
  v9 = v21;
  if ( v21 >= 0 )
  {
    v10 = v27;
    if ( !v27 )
    {
      if ( !Source )
      {
        swprintf_s(Destination, SizeInWords, L"ADs:");
LABEL_10:
        v9 = 0;
        goto LABEL_26;
      }
      swprintf_s(Destination, SizeInWords, L"%s:", v25);
      v11 = -1;
      do
        ++v11;
      while ( Source[v11] );
      if ( v11 < 0x104 )
      {
        wcscpy_s(v7, 0x10Eu, Source);
        goto LABEL_10;
      }
      goto LABEL_8;
    }
    swprintf_s(Destination, SizeInWords, L"%s://%s", v25, Source);
    v12 = v10 - 1;
    if ( v10 != 1 )
    {
      v13 = 0;
      do
      {
        wcscat_s(Destination, SizeInWords, L"/");
        v14 = *(const wchar_t **)(v28 + 16 * v13);
        if ( v14 )
        {
          v15 = SizeInWords;
          v16 = Destination;
          if ( *(_QWORD *)(v28 + 16 * v13 + 8) )
          {
            wcscat_s(Destination, SizeInWords, v14);
            wcscat_s(Destination, SizeInWords, L"=");
            v15 = SizeInWords;
            v16 = Destination;
            v14 = *(const wchar_t **)(v28 + 16 * v13 + 8);
          }
          wcscat_s(v16, v15, v14);
        }
        ++v8;
        ++v13;
      }
      while ( v8 < v12 );
      v9 = v21;
      v7 = a4;
    }
    v17 = *(const wchar_t **)(v28 + 16LL * v12);
    if ( v17 )
    {
      v18 = *(_QWORD *)(v28 + 16LL * v12 + 8);
      if ( v18 )
      {
        swprintf_s(v7, 0x10Eu, L"%s=%s", v17, v18);
        goto LABEL_26;
      }
      v19 = -1;
      do
        ++v19;
      while ( v17[v19] );
      if ( v19 < 0x104 )
      {
        wcscpy_s(v7, 0x10Eu, v17);
        goto LABEL_26;
      }
LABEL_8:
      v9 = -2147463160;
    }
  }
LABEL_26:
  FreeObjectInfo((struct _objectinfo *)&v25);
  FreeADsStr(pStr);
  return v9;
}

```

## disassembly

```asm
0x180014fa4  push    rbp
0x180014fa6  push    rbx
0x180014fa7  push    rsi
0x180014fa8  push    rdi
0x180014fa9  push    r12
0x180014fab  push    r13
0x180014fad  push    r14
0x180014faf  push    r15
0x180014fb1  lea     rbp, [rsp-1A8h]
0x180014fb9  sub     rsp, 2A8h
0x180014fc0  mov     rax, cs:__security_cookie
0x180014fc7  xor     rax, rsp
0x180014fca  mov     [rbp+1E0h+var_50], rax
0x180014fd1  mov     rsi, r8
0x180014fd4  mov     [rsp+2E0h+var_2A8], r9
0x180014fd9  mov     rdi, rdx
0x180014fdc  mov     rbx, rcx
0x180014fdf  mov     r14d, 230h
0x180014fe5  lea     rcx, [rsp+2E0h+var_280]; void *
0x180014fea  mov     r8d, r14d; Size
0x180014fed  xor     edx, edx; Val
0x180014fef  mov     r12, r9
0x180014ff2  call    memset_0
0x180014ff7  mov     rdx, rbx; unsigned __int16 *
0x180014ffa  lea     rcx, [rsp+2E0h+var_2A0]; this
0x180014fff  call    ??0CLexer@@QEAA@PEBG@Z; CLexer::CLexer(ushort const *)
0x180015004  mov     r8d, r14d; Size
0x180015007  lea     rcx, [rsp+2E0h+var_280]; void *
0x18001500c  xor     edx, edx; Val
0x18001500e  call    memset_0
0x180015013  lea     rdx, [rsp+2E0h+var_280]; struct _objectinfo *
0x180015018  lea     rcx, [rsp+2E0h+var_2A0]; struct CLexer *
0x18001501d  call    ?ADsObject@@YAJPEAVCLexer@@PEAU_objectinfo@@@Z; ADsObject(CLexer *,_objectinfo *)
0x180015022  xor     r15d, r15d
0x180015025  mov     [rsp+2E0h+var_2B0], eax
0x180015029  mov     ebx, eax
0x18001502b  test    eax, eax
0x18001502d  js      loc_1800151BC
0x180015033  mov     r14d, [rbp+1E0h+var_60]
0x18001503a  mov     rdx, rsi; BufferCount
0x18001503d  mov     rcx, rdi; Buffer
0x180015040  test    r14d, r14d
0x180015043  jnz     short loc_1800150A8
0x180015045  cmp     [rsp+2E0h+Source], r15
0x18001504a  jnz     short loc_18001505B
0x18001504c  lea     r8, aAds; "ADs:"
0x180015053  call    cs:__imp_swprintf_s
0x180015059  jmp     short loc_1800150A0
0x18001505b  mov     r9, [rsp+2E0h+var_280]
0x180015060  lea     r8, aS_0; "%s:"
0x180015067  call    cs:__imp_swprintf_s
0x18001506d  mov     r8, [rsp+2E0h+Source]; Source
0x180015072  or      rax, 0FFFFFFFFFFFFFFFFh
0x180015076  inc     rax
0x180015079  cmp     [r8+rax*2], r15w
0x18001507e  jnz     short loc_180015076
0x180015080  cmp     rax, 104h
0x180015086  jb      short loc_180015092
0x180015088  mov     ebx, 80005008h
0x18001508d  jmp     loc_1800151BC
0x180015092  mov     edx, 10Eh; SizeInWords
0x180015097  mov     rcx, r12; Destination
0x18001509a  call    cs:__imp_wcscpy_s
0x1800150a0  mov     ebx, r15d
0x1800150a3  jmp     loc_1800151BC
0x1800150a8  mov     rax, [rsp+2E0h+Source]
0x1800150ad  lea     r8, aSS; "%s://%s"
0x1800150b4  mov     r9, [rsp+2E0h+var_280]
0x1800150b9  mov     [rsp+2E0h+var_2C0], rax
0x1800150be  call    cs:__imp_swprintf_s
0x1800150c4  xor     edx, edx
0x1800150c6  lea     r13d, [r14-1]
0x1800150ca  test    r13d, r13d
0x1800150cd  jz      loc_180015155
0x1800150d3  xor     ebx, ebx
0x1800150d5  mov     r12d, ebx
0x1800150d8  lea     r8, Source; "/"
0x1800150df  mov     rdx, rsi; SizeInWords
0x1800150e2  mov     rcx, rdi; Destination
0x1800150e5  call    cs:__imp_wcscat_s
0x1800150eb  mov     rax, [rbp+1E0h+var_58]
0x1800150f2  mov     r14, r12
0x1800150f5  add     r14, r14
0x1800150f8  mov     r8, [rax+r14*8]; Source
0x1800150fc  test    r8, r8
0x1800150ff  jz      short loc_18001513F
0x180015101  mov     rdx, rsi; SizeInWords
0x180015104  mov     rcx, rdi; Destination
0x180015107  cmp     [rax+r14*8+8], rbx
0x18001510c  jz      short loc_180015139
0x18001510e  call    cs:__imp_wcscat_s
0x180015114  lea     r8, asc_1800213A0; "="
0x18001511b  mov     rdx, rsi; SizeInWords
0x18001511e  mov     rcx, rdi; Destination
0x180015121  call    cs:__imp_wcscat_s
0x180015127  mov     r8, [rbp+1E0h+var_58]
0x18001512e  mov     rdx, rsi; SizeInWords
0x180015131  mov     rcx, rdi; Destination
0x180015134  mov     r8, [r8+r14*8+8]; Source
0x180015139  call    cs:__imp_wcscat_s
0x18001513f  inc     r15d
0x180015142  inc     r12
0x180015145  cmp     r15d, r13d
0x180015148  jb      short loc_1800150D8
0x18001514a  mov     ebx, [rsp+2E0h+var_2B0]
0x18001514e  xor     edx, edx
0x180015150  mov     r12, [rsp+2E0h+var_2A8]
0x180015155  mov     rcx, [rbp+1E0h+var_58]
0x18001515c  mov     eax, r13d
0x18001515f  add     rax, rax
0x180015162  mov     r8, [rcx+rax*8]; Source
0x180015166  test    r8, r8
0x180015169  jz      short loc_1800151BC
0x18001516b  mov     rcx, [rcx+rax*8+8]
0x180015170  test    rcx, rcx
0x180015173  jz      short loc_180015194
0x180015175  mov     [rsp+2E0h+var_2C0], rcx
0x18001517a  mov     r9, r8
0x18001517d  lea     r8, aSS_0; "%s=%s"
0x180015184  mov     rcx, r12; Buffer
0x180015187  mov     edx, 10Eh; BufferCount
0x18001518c  call    cs:__imp_swprintf_s
0x180015192  jmp     short loc_1800151BC
0x180015194  or      rax, 0FFFFFFFFFFFFFFFFh
0x180015198  inc     rax
0x18001519b  cmp     [r8+rax*2], dx
0x1800151a0  jnz     short loc_180015198
0x1800151a2  cmp     rax, 104h
0x1800151a8  jnb     loc_180015088
0x1800151ae  mov     edx, 10Eh; SizeInWords
0x1800151b3  mov     rcx, r12; Destination
0x1800151b6  call    cs:__imp_wcscpy_s
0x1800151bc  lea     rcx, [rsp+2E0h+var_280]; struct _objectinfo *
0x1800151c1  call    ?FreeObjectInfo@@YAXPEAU_objectinfo@@@Z; FreeObjectInfo(_objectinfo *)
0x1800151c6  mov     rcx, [rsp+2E0h+pStr]; pStr
0x1800151cb  call    cs:__imp_FreeADsStr
0x1800151d1  mov     eax, ebx
0x1800151d3  mov     rcx, [rbp+1E0h+var_50]
0x1800151da  xor     rcx, rsp; StackCookie
0x1800151dd  call    __security_check_cookie
0x1800151e2  add     rsp, 2A8h
0x1800151e9  pop     r15
0x1800151eb  pop     r14
0x1800151ed  pop     r13
0x1800151ef  pop     r12
0x1800151f1  pop     rdi
0x1800151f2  pop     rsi
0x1800151f3  pop     rbx
0x1800151f4  pop     rbp
0x1800151f5  retn
```
