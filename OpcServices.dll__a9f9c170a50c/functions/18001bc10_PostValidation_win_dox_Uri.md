# PostValidation(win_dox::Uri &)

- ea: `0x18001bc10`
- end: `0x18001c4a1`
- name: `?PostValidation@@YAXAEAVUri@win_dox@@@Z`
- size: `2193`
- prototype: `void __fastcall(struct win_dox::Uri *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180019664`

## callees

- `0x18001aaa0`
- `0x18001bc10`
- `0x18001c5d0`
- `0x18001ca9c`
- `0x1800517a0`
- `0x180075ff4`
- `0x1800cce54`
- `0x1800cd38c`
- `0x1800cdb60`
- `0x1800cdbbc`
- `0x180117740`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18001bcb4`
- `msvcrt!memcpy_s` at `0x18001bd32`
- `msvcrt!memcpy_s` at `0x18001bdb9`
- `msvcrt!memcpy_s` at `0x18001bcb4`
- `msvcrt!memcpy_s` at `0x18001bd32`
- `msvcrt!memcpy_s` at `0x18001bdb9`

## string_xrefs

- `0x18001c343`: `Part uri cannot be an empty string`
- `0x18001c18b`: `Part uri cannot begin with two forward slashes`
- `0x18001c3cf`: `Part uri cannot be a relationship to a relationship`
- `0x18001c45d`: `Part uri cannot end with a forward slash`
- `0x18001c0e4`: `Part uri cannot have a segment that ends with a dot`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall PostValidation(struct win_dox::Uri *a1)
{
  void **v1; // rcx
  void **v2; // rcx
  void **v3; // rcx
  void **v4; // r9
  void **v5; // rcx
  unsigned __int64 v6; // r8
  unsigned __int64 v7; // rdi
  void **v8; // rax
  void **v9; // rcx
  void **v10; // rcx
  void **v11; // rcx
  void **v12; // rcx
  void **v13; // rax
  unsigned __int64 v14; // r15
  unsigned __int64 v15; // rsi
  void **v16; // r14
  void **v17; // rax
  void **i; // rcx
  void **v19; // rax
  __int64 v20; // rdx
  __int16 *v21; // r8
  unsigned __int64 v22; // rcx
  void **v23; // rdi
  unsigned __int64 v24; // rax
  void **v25; // rdx
  void **j; // rdx
  void **v27; // rax
  unsigned __int64 v28; // r8
  void **v29; // r10
  void **v30; // rax
  __int64 v31; // rdx
  __int64 v32; // rbx
  unsigned __int64 v33; // rbx
  unsigned __int64 v34; // r9
  void **v35; // rax
  _WORD *v36; // r10
  unsigned __int64 v37; // rax
  _WORD *v38; // rbx
  void **v39; // rax
  void **v40; // rax
  void **v41; // rax
  void **v42; // rax
  void **v43; // rax
  _WORD *v44; // r8
  __int16 *v45; // rdx
  __int64 v46; // rcx
  void **v47; // rax
  __int64 v48; // rax
  __int16 v49; // [rsp+40h] [rbp-C0h] BYREF
  __int16 v50; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v51; // [rsp+58h] [rbp-A8h]
  char v52[8]; // [rsp+60h] [rbp-A0h] BYREF
  void *Block[2]; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int64 v54; // [rsp+78h] [rbp-88h]
  unsigned __int64 v55; // [rsp+80h] [rbp-80h]
  char v56[8]; // [rsp+88h] [rbp-78h] BYREF
  void *Destination[2]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int64 v58; // [rsp+A0h] [rbp-60h]
  unsigned __int64 v59; // [rsp+A8h] [rbp-58h]
  char v60[8]; // [rsp+B0h] [rbp-50h] BYREF
  void *v61[2]; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v62; // [rsp+C8h] [rbp-38h]
  unsigned __int64 v63; // [rsp+D0h] [rbp-30h]
  char v64[8]; // [rsp+D8h] [rbp-28h] BYREF
  void *Source[2]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int64 v66; // [rsp+F0h] [rbp-10h]
  unsigned __int64 v67; // [rsp+F8h] [rbp-8h]
  _BYTE pExceptionObject[160]; // [rsp+100h] [rbp+0h] BYREF

  v51 = -2;
  win_dox::Uri::GetPath(a1, v64);
  v59 = 7;
  v58 = 0;
  LOWORD(Destination[0]) = 0;
  std::wstring::_Copy(v56, 12, 0);
  v1 = Destination;
  if ( v59 >= 8 )
    v1 = (void **)Destination[0];
  memcpy_s(v1, 2 * v59, L"/_RELS/_RELS", 0x18u);
  v2 = Destination;
  if ( v59 >= 8 )
    v2 = (void **)Destination[0];
  v58 = 12;
  *((_WORD *)v2 + 12) = 0;
  v63 = 7;
  v62 = 0;
  LOWORD(v61[0]) = 0;
  std::wstring::_Copy(v60, 10, 0);
  v3 = v61;
  if ( v63 >= 8 )
    v3 = (void **)v61[0];
  memcpy_s(v3, 2 * v63, L".RELS.RELS", 0x14u);
  v5 = v61;
  if ( v63 >= 8 )
    v5 = (void **)v61[0];
  v62 = 10;
  *((_WORD *)v5 + 10) = 0;
  v6 = 7;
  v55 = 7;
  v54 = 0;
  LOWORD(Block[0]) = 0;
  v7 = v66;
  if ( v66 > 0x7FFFFFFFFFFFFFFELL )
    std::_String_base::_Xlen();
  if ( v66 > 7 )
  {
    std::wstring::_Copy(v52, v66, v54);
    v6 = v55;
    if ( !v7 )
      goto LABEL_20;
    goto LABEL_12;
  }
  if ( v66 )
  {
LABEL_12:
    if ( v67 < 8 )
      v8 = Source;
    else
      v8 = (void **)Source[0];
    v9 = Block;
    if ( v6 >= 8 )
      v9 = (void **)Block[0];
    memcpy_s(v9, 2 * v6, v8, 2 * v7);
    v10 = Block;
    if ( v55 >= 8 )
      v10 = (void **)Block[0];
    v54 = v7;
    *((_WORD *)v10 + v7) = 0;
    goto LABEL_19;
  }
  v54 = 0;
  LOWORD(Block[0]) = 0;
LABEL_19:
  v6 = v55;
LABEL_20:
  v11 = Block;
  if ( v6 >= 8 )
    v11 = (void **)Block[0];
  v12 = (void **)((char *)v11 + 2 * v54);
  v13 = Block;
  if ( v6 >= 8 )
    v13 = (void **)Block[0];
  while ( v13 != v12 )
  {
    v4 = (void **)*(unsigned __int16 *)v13;
    if ( (unsigned __int16)((_WORD)v4 - 97) <= 0x19u )
      LOWORD(v4) = (_WORD)v4 - 32;
    *(_WORD *)v13 = (_WORD)v4;
    v13 = (void **)((char *)v13 + 2);
  }
  v14 = v54;
  if ( !v54 )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x33Bu,
      0x80510001,
      (struct win_musl::TStringEllipseBase *)L"Part uri cannot be an empty string");
    throw (SplException::THResultException *)pExceptionObject;
  }
  v49 = 47;
  v15 = v55;
  v16 = (void **)Block[0];
  if ( v55 < 8 )
    v17 = Block;
  else
    v17 = (void **)Block[0];
  for ( i = (void **)((char *)v17 + 2 * v54 - 2); *(_WORD *)i != 47; i = (void **)((char *)i - 2) )
  {
LABEL_33:
    if ( v55 < 8 )
      v19 = Block;
    else
      v19 = (void **)Block[0];
    if ( i == v19 )
    {
      v22 = -1;
      goto LABEL_42;
    }
  }
  v20 = 1;
  v21 = &v49;
  v4 = i;
  while ( v20 )
  {
    if ( *(_WORD *)v4 != *v21 )
      goto LABEL_33;
    v4 = (void **)((char *)v4 + 2);
    ++v21;
    --v20;
  }
  if ( v55 < 8 )
    v47 = Block;
  else
    v47 = (void **)Block[0];
  v22 = ((char *)i - (char *)v47) >> 1;
LABEL_42:
  if ( v59 < 8 )
    v23 = Destination;
  else
    v23 = (void **)Destination[0];
  if ( !v58 )
  {
    v31 = v54;
    if ( v22 < v54 )
      v31 = v22;
LABEL_63:
    if ( v31 != -1 && v58 + v31 == v22 )
    {
      v48 = std::wstring::rfind(v52, v60, -1, v4);
      if ( v48 != -1 && v62 + v48 == v14 )
      {
        win_musl::detail::ThrowBuilder<SplException::THResultException>(
          (SplException::TSystemException *)pExceptionObject,
          0x350u,
          0x80510001,
          (struct win_musl::TStringEllipseBase *)L"Part uri cannot be a relationship to a relationship");
        throw (SplException::THResultException *)pExceptionObject;
      }
    }
    goto LABEL_64;
  }
  if ( v58 <= v54 )
  {
    v24 = v54 - v58;
    if ( v22 < v54 - v58 )
      v24 = v22;
    if ( v55 < 8 )
      v25 = Block;
    else
      v25 = (void **)Block[0];
    for ( j = (void **)((char *)v25 + 2 * v24); *(_WORD *)j != *(_WORD *)v23; j = (void **)((char *)j - 2) )
    {
LABEL_52:
      if ( v55 < 8 )
        v27 = Block;
      else
        v27 = (void **)Block[0];
      if ( j == v27 )
        goto LABEL_64;
    }
    v28 = v58;
    v4 = v23;
    v29 = j;
    while ( v28 )
    {
      if ( *(_WORD *)v29 != *(_WORD *)v4 )
        goto LABEL_52;
      v29 = (void **)((char *)v29 + 2);
      v4 = (void **)((char *)v4 + 2);
      --v28;
    }
    if ( v55 < 8 )
      v30 = Block;
    else
      v30 = (void **)Block[0];
    v31 = ((char *)j - (char *)v30) >> 1;
    goto LABEL_63;
  }
LABEL_64:
  if ( v66 >= 2 )
  {
    v42 = Source;
    if ( v67 >= 8 )
      v42 = (void **)Source[0];
    if ( *(_WORD *)v42 == 47 )
    {
      v43 = Source;
      if ( v67 >= 8 )
        v43 = (void **)Source[0];
      if ( *((_WORD *)v43 + 1) == 47 )
      {
        win_musl::detail::ThrowBuilder<SplException::THResultException>(
          (SplException::TSystemException *)pExceptionObject,
          0x358u,
          0x80510001,
          (struct win_musl::TStringEllipseBase *)L"Part uri cannot begin with two forward slashes");
        throw (SplException::THResultException *)pExceptionObject;
      }
    }
  }
  v32 = 0;
LABEL_66:
  while ( v32 != -1 )
  {
    v33 = v32 + 1;
    v50 = 47;
    if ( v33 < v14 )
    {
      v34 = v14 - v33;
      if ( v14 != v33 )
      {
        if ( v15 < 8 )
          v35 = Block;
        else
          v35 = v16;
        v36 = (_WORD *)v35 + v33;
LABEL_72:
        v37 = v34;
        v38 = v36;
        while ( v37 )
        {
          if ( *v38 == 47 )
          {
            v46 = 1;
            v45 = &v50;
            v44 = v38;
            while ( v46 )
            {
              if ( *v44 != *v45 )
              {
                v34 += -1 - (v38 - v36);
                v36 = v38 + 1;
                goto LABEL_72;
              }
              ++v44;
              ++v45;
              --v46;
            }
            if ( v15 < 8 )
              v39 = Block;
            else
              v39 = v16;
            v32 = ((char *)v38 - (char *)v39) >> 1;
            if ( v32 != -1 )
            {
              if ( v14 <= v32 - 1 )
                std::_String_base::_Xran();
              v41 = Block;
              if ( v15 >= 8 )
                v41 = v16;
              if ( *((_WORD *)v41 + v32 - 1) == 46 )
              {
                win_musl::detail::ThrowBuilder<SplException::THResultException>(
                  (SplException::TSystemException *)pExceptionObject,
                  0x36Bu,
                  0x80510001,
                  (struct win_musl::TStringEllipseBase *)L"Part uri cannot have a segment that ends with a dot");
                throw (SplException::THResultException *)pExceptionObject;
              }
              goto LABEL_66;
            }
            goto LABEL_82;
          }
          ++v38;
          --v37;
        }
      }
    }
    v32 = -1;
  }
LABEL_82:
  v40 = Block;
  if ( v15 >= 8 )
    v40 = v16;
  if ( *((_WORD *)v40 + v14 - 1) == 47 )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x375u,
      0x80510001,
      (struct win_musl::TStringEllipseBase *)L"Part uri cannot end with a forward slash");
    throw (SplException::THResultException *)pExceptionObject;
  }
  if ( v15 >= 8 )
    operator delete(v16);
  v55 = 7;
  v54 = 0;
  LOWORD(Block[0]) = 0;
  if ( v63 >= 8 )
    operator delete(v61[0]);
  v63 = 7;
  v62 = 0;
  LOWORD(v61[0]) = 0;
  if ( v59 >= 8 )
    operator delete(Destination[0]);
  v59 = 7;
  v58 = 0;
  LOWORD(Destination[0]) = 0;
  if ( v67 >= 8 )
    operator delete(Source[0]);
}

```

## disassembly

```asm
0x18001bc10  push    rbp
0x18001bc12  push    rbx
0x18001bc13  push    rsi
0x18001bc14  push    rdi
0x18001bc15  push    r12
0x18001bc17  push    r13
0x18001bc19  push    r14
0x18001bc1b  push    r15
0x18001bc1d  lea     rbp, [rsp-0B8h]
0x18001bc25  sub     rsp, 1B8h
0x18001bc2c  mov     [rsp+1F0h+var_198], 0FFFFFFFFFFFFFFFEh
0x18001bc35  mov     rax, cs:__security_cookie
0x18001bc3c  xor     rax, rsp
0x18001bc3f  mov     [rbp+0F0h+var_50], rax
0x18001bc46  xor     r13d, r13d
0x18001bc49  lea     rdx, [rbp+0F0h+var_118]
0x18001bc4d  call    ?GetPath@Uri@win_dox@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@XZ; win_dox::Uri::GetPath(void)
0x18001bc52  nop
0x18001bc53  mov     [rbp+0F0h+var_148], 7
0x18001bc5b  mov     ecx, r13d
0x18001bc5e  mov     [rbp+0F0h+var_150], rcx
0x18001bc62  mov     word ptr [rbp+0F0h+Destination], r13w
0x18001bc67  lea     rbx, aRelsRels_0; "/_RELS/_RELS"
0x18001bc6e  lea     rax, [rbp+0F0h+Destination]
0x18001bc72  cmp     rbx, rax
0x18001bc75  jb      short loc_18001BC84
0x18001bc77  lea     rax, [rbp+0F0h+Destination]
0x18001bc7b  cmp     rax, rbx
0x18001bc7e  ja      loc_18001C1CF
0x18001bc84  xor     r8d, r8d
0x18001bc87  mov     edi, 0Ch
0x18001bc8c  mov     edx, edi
0x18001bc8e  lea     rcx, [rbp+0F0h+var_168]
0x18001bc92  call    ?_Copy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@IEAAX_K0@Z; std::wstring::_Copy(unsigned __int64,unsigned __int64)
0x18001bc97  mov     rdx, [rbp+0F0h+var_148]
0x18001bc9b  lea     rcx, [rbp+0F0h+Destination]
0x18001bc9f  cmp     rdx, 8
0x18001bca3  cmovnb  rcx, [rbp+0F0h+Destination]; Destination
0x18001bca8  add     rdx, rdx; DestinationSize
0x18001bcab  mov     r9d, 18h; SourceSize
0x18001bcb1  mov     r8, rbx; Source
0x18001bcb4  call    cs:__imp_memcpy_s
0x18001bcba  lea     rcx, [rbp+0F0h+Destination]
0x18001bcbe  cmp     [rbp+0F0h+var_148], 8
0x18001bcc3  cmovnb  rcx, [rbp+0F0h+Destination]
0x18001bcc8  mov     [rbp+0F0h+var_150], rdi
0x18001bccc  mov     [rcx+18h], r13w
0x18001bcd1  mov     [rbp+0F0h+var_120], 7
0x18001bcd9  mov     rcx, r13
0x18001bcdc  mov     [rbp+0F0h+var_128], rcx
0x18001bce0  mov     word ptr [rbp+0F0h+var_138], r13w
0x18001bce5  lea     rbx, aRelsRels; ".RELS.RELS"
0x18001bcec  lea     rax, [rbp+0F0h+var_138]
0x18001bcf0  cmp     rbx, rax
0x18001bcf3  jb      short loc_18001BD02
0x18001bcf5  lea     rax, [rbp+0F0h+var_138]
0x18001bcf9  cmp     rax, rbx
0x18001bcfc  ja      loc_18001C215
0x18001bd02  xor     r8d, r8d
0x18001bd05  mov     edi, 0Ah
0x18001bd0a  mov     edx, edi
0x18001bd0c  lea     rcx, [rbp+0F0h+var_140]
0x18001bd10  call    ?_Copy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@IEAAX_K0@Z; std::wstring::_Copy(unsigned __int64,unsigned __int64)
0x18001bd15  mov     rdx, [rbp+0F0h+var_120]
0x18001bd19  lea     rcx, [rbp+0F0h+var_138]
0x18001bd1d  cmp     rdx, 8
0x18001bd21  cmovnb  rcx, [rbp+0F0h+var_138]; Destination
0x18001bd26  add     rdx, rdx; DestinationSize
0x18001bd29  mov     r9d, 14h; SourceSize
0x18001bd2f  mov     r8, rbx; Source
0x18001bd32  call    cs:__imp_memcpy_s
0x18001bd38  lea     rcx, [rbp+0F0h+var_138]
0x18001bd3c  cmp     [rbp+0F0h+var_120], 8
0x18001bd41  cmovnb  rcx, [rbp+0F0h+var_138]
0x18001bd46  mov     [rbp+0F0h+var_128], rdi
0x18001bd4a  mov     [rcx+14h], r13w
0x18001bd4f  mov     r8d, 7
0x18001bd55  mov     [rbp+0F0h+var_170], r8
0x18001bd59  mov     [rsp+1F0h+var_178], r13
0x18001bd5e  mov     word ptr [rsp+1F0h+Block], r13w
0x18001bd64  mov     rdi, [rbp+0F0h+var_100]
0x18001bd68  mov     rax, 7FFFFFFFFFFFFFFEh
0x18001bd72  cmp     rdi, rax
0x18001bd75  ja      loc_18001C335
0x18001bd7b  cmp     r8, rdi
0x18001bd7e  jb      loc_18001C128
0x18001bd84  test    rdi, rdi
0x18001bd87  jz      loc_18001C25B
0x18001bd8d  cmp     [rbp+0F0h+var_F8], 8
0x18001bd92  jb      loc_18001C278
0x18001bd98  mov     rax, [rbp+0F0h+Source]
0x18001bd9c  lea     rcx, [rsp+1F0h+Block]
0x18001bda1  cmp     r8, 8
0x18001bda5  cmovnb  rcx, [rsp+1F0h+Block]; Destination
0x18001bdab  lea     rbx, [rdi+rdi]
0x18001bdaf  lea     rdx, [r8+r8]; DestinationSize
0x18001bdb3  mov     r9, rbx; SourceSize
0x18001bdb6  mov     r8, rax; Source
0x18001bdb9  call    cs:__imp_memcpy_s
0x18001bdbf  lea     rcx, [rsp+1F0h+Block]
0x18001bdc4  cmp     [rbp+0F0h+var_170], 8
0x18001bdc9  cmovnb  rcx, [rsp+1F0h+Block]
0x18001bdcf  mov     [rsp+1F0h+var_178], rdi
0x18001bdd4  mov     [rcx+rbx], r13w
0x18001bdd9  mov     r8, [rbp+0F0h+var_170]
0x18001bddd  lea     rcx, [rsp+1F0h+Block]
0x18001bde2  cmp     r8, 8
0x18001bde6  cmovnb  rcx, [rsp+1F0h+Block]
0x18001bdec  mov     rax, [rsp+1F0h+var_178]
0x18001bdf1  lea     rcx, [rcx+rax*2]
0x18001bdf5  lea     rax, [rsp+1F0h+Block]
0x18001bdfa  cmovnb  rax, [rsp+1F0h+Block]
0x18001be00  cmp     rax, rcx
0x18001be03  jz      short loc_18001BE25
0x18001be05  movzx   r9d, word ptr [rax]
0x18001be09  lea     r8d, [r9-61h]
0x18001be0d  lea     edx, [r9-20h]
0x18001be11  cmp     r8w, 19h
0x18001be16  cmovbe  r9w, dx
0x18001be1b  mov     [rax], r9w
0x18001be1f  add     rax, 2
0x18001be23  jmp     short loc_18001BE00
0x18001be25  mov     r15, [rsp+1F0h+var_178]
0x18001be2a  test    r15, r15
0x18001be2d  jz      loc_18001C343
0x18001be33  mov     r12d, 2Fh ; '/'
0x18001be39  mov     [rsp+1F0h+var_1B0], r12w
0x18001be3f  mov     rsi, [rbp+0F0h+var_170]
0x18001be43  mov     r14, [rsp+1F0h+Block]
0x18001be48  cmp     r15, 1
0x18001be4c  jb      short loc_18001BEB0
0x18001be4e  cmp     rsi, 8
0x18001be52  jb      loc_18001C294
0x18001be58  mov     rax, r14
0x18001be5b  lea     rcx, [r15-1]
0x18001be5f  lea     rcx, [rax+rcx*2]
0x18001be63  cmp     [rcx], r12w
0x18001be67  jz      short loc_18001BE81
0x18001be69  cmp     rsi, 8
0x18001be6d  jb      loc_18001BFE1
0x18001be73  mov     rax, r14
0x18001be76  cmp     rcx, rax
0x18001be79  jz      short loc_18001BEB0
0x18001be7b  sub     rcx, 2
0x18001be7f  jmp     short loc_18001BE63
0x18001be81  mov     edx, 1
0x18001be86  lea     r8, [rsp+1F0h+var_1B0]
0x18001be8b  mov     r9, rcx
0x18001be8e  xchg    ax, ax
0x18001be90  test    rdx, rdx
0x18001be93  jz      loc_18001C2FE
0x18001be99  movzx   eax, word ptr [r8]
0x18001be9d  cmp     [r9], ax
0x18001bea1  jnz     short loc_18001BE69
0x18001bea3  add     r9, 2
0x18001bea7  add     r8, 2
0x18001beab  dec     rdx
0x18001beae  jmp     short loc_18001BE90
0x18001beb0  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001beb7  mov     rbx, [rbp+0F0h+var_150]
0x18001bebb  cmp     [rbp+0F0h+var_148], 8
0x18001bec0  jb      loc_18001C281
0x18001bec6  mov     rdi, [rbp+0F0h+Destination]
0x18001beca  test    rbx, rbx
0x18001becd  jz      loc_18001C387
0x18001bed3  cmp     rbx, r15
0x18001bed6  ja      loc_18001BF60
0x18001bedc  mov     rax, r15
0x18001bedf  sub     rax, rbx
0x18001bee2  cmp     rcx, rax
0x18001bee5  cmovb   rax, rcx
0x18001bee9  cmp     rsi, 8
0x18001beed  jb      loc_18001C29E
0x18001bef3  mov     rdx, r14
0x18001bef6  lea     rdx, [rdx+rax*2]
0x18001befa  movzx   r11d, word ptr [rdi]
0x18001befe  xchg    ax, ax
0x18001bf00  cmp     [rdx], r11w
0x18001bf04  jz      short loc_18001BF1E
0x18001bf06  cmp     rsi, 8
0x18001bf0a  jb      loc_18001BFD7
0x18001bf10  mov     rax, r14
0x18001bf13  cmp     rdx, rax
0x18001bf16  jz      short loc_18001BF60
0x18001bf18  sub     rdx, 2
0x18001bf1c  jmp     short loc_18001BF00
0x18001bf1e  mov     r8, rbx
0x18001bf21  mov     r9, rdi
0x18001bf24  mov     r10, rdx
0x18001bf27  test    r8, r8
0x18001bf2a  jz      short loc_18001BF43
0x18001bf2c  movzx   eax, word ptr [r9]
0x18001bf30  cmp     [r10], ax
0x18001bf34  jnz     short loc_18001BF06
0x18001bf36  add     r10, 2
0x18001bf3a  add     r9, 2
0x18001bf3e  dec     r8
0x18001bf41  jmp     short loc_18001BF27
0x18001bf43  cmp     rsi, 8
0x18001bf47  jb      loc_18001C2B2
0x18001bf4d  mov     rax, r14
0x18001bf50  sub     rdx, rax
0x18001bf53  sar     rdx, 1
0x18001bf56  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x18001bf5a  jnz     loc_18001C396
0x18001bf60  mov     r8, [rbp+0F0h+var_100]
0x18001bf64  cmp     r8, 2
0x18001bf68  jnb     loc_18001C14C
0x18001bf6e  mov     rbx, r13
0x18001bf71  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18001bf75  jz      loc_18001C008
0x18001bf7b  inc     rbx
0x18001bf7e  mov     [rsp+1F0h+var_1A8], r12w
0x18001bf84  cmp     rbx, r15
0x18001bf87  jnb     short loc_18001BFCE
0x18001bf89  mov     r9, r15
0x18001bf8c  sub     r9, rbx
0x18001bf8f  cmp     r9, 1
0x18001bf93  jb      short loc_18001BFCE
0x18001bf95  cmp     rsi, 8
0x18001bf99  jb      loc_18001C28A
0x18001bf9f  mov     rax, r14
0x18001bfa2  lea     r10, [rax+rbx*2]
0x18001bfa6  nop     word ptr [rax+rax+00000000h]
0x18001bfb0  mov     rax, r9
0x18001bfb3  mov     rbx, r10
0x18001bfb6  test    rax, rax
0x18001bfb9  jz      short loc_18001BFCE
0x18001bfbb  cmp     [rbx], r12w
0x18001bfbf  jz      loc_18001C433
0x18001bfc5  add     rbx, 2
0x18001bfc9  dec     rax
0x18001bfcc  jmp     short loc_18001BFB6
0x18001bfce  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18001bfd5  jmp     short loc_18001BF71
0x18001bfd7  lea     rax, [rsp+1F0h+Block]
0x18001bfdc  jmp     loc_18001BF13
0x18001bfe1  lea     rax, [rsp+1F0h+Block]
0x18001bfe6  jmp     loc_18001BE76
0x18001bfeb  cmp     rsi, 8
0x18001bfef  jb      loc_18001C2A8
0x18001bff5  mov     rax, r14
0x18001bff8  sub     rbx, rax
0x18001bffb  sar     rbx, 1
0x18001bffe  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18001c002  jnz     loc_18001C0BF
0x18001c008  lea     rax, [rsp+1F0h+Block]
0x18001c00d  cmp     rsi, 8
0x18001c011  cmovnb  rax, r14
0x18001c015  cmp     [rax+r15*2-2], r12w
0x18001c01b  jz      loc_18001C45D
0x18001c021  cmp     rsi, 8
0x18001c025  jnb     short loc_18001C094
0x18001c027  mov     [rbp+0F0h+var_170], 7
0x18001c02f  mov     [rsp+1F0h+var_178], r13
0x18001c034  mov     word ptr [rsp+1F0h+Block], r13w
0x18001c03a  cmp     [rbp+0F0h+var_120], 8
0x18001c03f  jnb     short loc_18001C09E
0x18001c041  mov     [rbp+0F0h+var_120], 7
0x18001c049  mov     [rbp+0F0h+var_128], r13
0x18001c04d  mov     word ptr [rbp+0F0h+var_138], r13w
0x18001c052  cmp     [rbp+0F0h+var_148], 8
0x18001c057  jnb     short loc_18001C0A9
0x18001c059  mov     [rbp+0F0h+var_148], 7
0x18001c061  mov     [rbp+0F0h+var_150], r13
0x18001c065  mov     word ptr [rbp+0F0h+Destination], r13w
0x18001c06a  cmp     [rbp+0F0h+var_F8], 8
0x18001c06f  jnb     short loc_18001C0B4
0x18001c071  mov     rcx, [rbp+0F0h+var_50]
0x18001c078  xor     rcx, rsp; StackCookie
0x18001c07b  call    __security_check_cookie
0x18001c080  add     rsp, 1B8h
0x18001c087  pop     r15
0x18001c089  pop     r14
0x18001c08b  pop     r13
0x18001c08d  pop     r12
0x18001c08f  pop     rdi
0x18001c090  pop     rsi
0x18001c091  pop     rbx
0x18001c092  pop     rbp
0x18001c093  retn
0x18001c094  mov     rcx, r14; Block
0x18001c097  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001c09c  jmp     short loc_18001C027
0x18001c09e  mov     rcx, [rbp+0F0h+var_138]; Block
0x18001c0a2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001c0a7  jmp     short loc_18001C041
0x18001c0a9  mov     rcx, [rbp+0F0h+Destination]; Block
0x18001c0ad  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001c0b2  jmp     short loc_18001C059
0x18001c0b4  mov     rcx, [rbp+0F0h+Source]; Block
0x18001c0b8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001c0bd  jmp     short loc_18001C071
0x18001c0bf  lea     rdi, [rbx-1]
0x18001c0c3  cmp     r15, rdi
0x18001c0c6  jbe     loc_18001C445
0x18001c0cc  lea     rax, [rsp+1F0h+Block]
0x18001c0d1  cmp     rsi, 8
0x18001c0d5  cmovnb  rax, r14
0x18001c0d9  cmp     word ptr [rax+rdi*2], 2Eh ; '.'
  ... truncated ...
```
