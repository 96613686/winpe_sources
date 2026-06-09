# FSConfigurationKey::InternalSerialize(void)

- ea: `0x18003c8c0`
- end: `0x18003cc55`
- name: `?InternalSerialize@FSConfigurationKey@@IEAAJXZ`
- size: `917`
- prototype: `__int64 __fastcall(FSConfigurationKey *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callers

- `0x18003aab0`
- `0x180073240`

## callees

- `0x180005fa0`
- `0x18000f5a0`
- `0x1800133fc`
- `0x18003c8c0`
- `0x18003cc5c`
- `0x18003ccec`
- `0x180044b28`
- `0x18004588a`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18003cb7b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18003cb7b`

## pseudocode

```c
__int64 __fastcall FSConfigurationKey::InternalSerialize(FSConfigurationKey *this)
{
  _WORD *v1; // rax
  _DWORD *v3; // rsi
  __int64 v4; // r8
  unsigned int v5; // ebx
  __int64 v6; // r10
  _WORD *v7; // rax
  __int64 v8; // r8
  __int64 v9; // r9
  _WORD *v10; // rax
  __int64 v11; // r8
  unsigned int v12; // r15d
  __int64 v13; // rax
  unsigned int v14; // r13d
  unsigned int v15; // r14d
  unsigned int v16; // r12d
  unsigned int v17; // ebp
  _QWORD *unique; // rax
  void *v19; // rcx
  __int64 v20; // rdx
  _OWORD *v21; // rax
  __int64 v22; // rdx
  unsigned int SourceSize; // [rsp+70h] [rbp+8h]
  void *Block; // [rsp+78h] [rbp+10h] BYREF
  void *v26; // [rsp+80h] [rbp+18h] BYREF

  v1 = (_WORD *)*((_QWORD *)this + 28);
  v3 = 0;
  if ( !v1 )
  {
    v5 = -2147024809;
    goto LABEL_50;
  }
  v4 = 0x7FFFFFFF;
  do
  {
    if ( !*v1 )
      break;
    ++v1;
    --v4;
  }
  while ( v4 );
  v5 = v4 == 0 ? 0x80070057 : 0;
  if ( !v4 )
  {
LABEL_50:
    if ( g_wppLevels )
    {
      v20 = 96;
      goto LABEL_52;
    }
    goto LABEL_53;
  }
  v6 = (2 * (0x7FFFFFFF - v4)) & -(__int64)(v4 != 0);
  v7 = (_WORD *)*((_QWORD *)this + 30);
  if ( !v7 )
  {
    v5 = -2147024809;
    goto LABEL_47;
  }
  v8 = 0x7FFFFFFF;
  do
  {
    if ( !*v7 )
      break;
    ++v7;
    --v8;
  }
  while ( v8 );
  v5 = v8 == 0 ? 0x80070057 : 0;
  if ( !v8 )
  {
LABEL_47:
    if ( g_wppLevels )
    {
      v20 = 97;
      goto LABEL_52;
    }
    goto LABEL_53;
  }
  v9 = (2 * (0x7FFFFFFF - v8)) & -(__int64)(v8 != 0);
  v10 = (_WORD *)*((_QWORD *)this + 29);
  if ( !v10 )
  {
    v5 = -2147024809;
    goto LABEL_44;
  }
  v11 = 0x7FFFFFFF;
  do
  {
    if ( !*v10 )
      break;
    ++v10;
    --v11;
  }
  while ( v11 );
  v5 = v11 == 0 ? 0x80070057 : 0;
  if ( !v11 )
  {
LABEL_44:
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        98,
        &WPP_72cf6ba4cbe23f0a9b7a240d5b293351_Traceguids,
        this,
        -2147024809);
    goto LABEL_53;
  }
  SourceSize = v6 + 2;
  v12 = v6 + 66;
  v13 = (2 * (0x7FFFFFFF - v11)) & -(__int64)(v11 != 0);
  if ( (unsigned int)(v6 + 66) >= 0x40 )
  {
    v14 = v9 + 2;
    v15 = v12 + v9 + 2;
    if ( v15 >= v12 )
    {
      v16 = v13 + 2;
      v17 = v15 + v13 + 2;
      if ( v17 >= v15 )
      {
        unique = wil::make_unique_nothrow<unsigned char [0]>(&Block, v17);
        v3 = (_DWORD *)*unique;
        *unique = 0;
        v19 = Block;
        v26 = v3;
        Block = 0;
        if ( v19 )
          operator delete(v19);
        if ( !v3 )
        {
          v5 = -2147024882;
          if ( g_wppLevels )
          {
            v20 = 100;
LABEL_52:
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v20,
              &WPP_72cf6ba4cbe23f0a9b7a240d5b293351_Traceguids,
              this,
              v5);
            goto LABEL_53;
          }
          goto LABEL_53;
        }
        v21 = v3 + 2;
        *v3 = 1;
        v3[1] = v17;
        v3[10] = 64;
        v3[11] = SourceSize;
        v3[12] = v12;
        v3[13] = v14;
        v3[14] = v15;
        v3[15] = v16;
        if ( v3 != (_DWORD *)-8LL )
        {
          if ( this != (FSConfigurationKey *)-56LL )
          {
            *v21 = *(_OWORD *)((char *)this + 56);
            *(_OWORD *)(v3 + 6) = *(_OWORD *)((char *)this + 72);
            if ( memcpy_s_1(v3 + 16, v17 - 64, *((const void *const *)this + 28), SourceSize) )
            {
              v5 = -1072875845;
              if ( !g_wppLevels )
                goto LABEL_53;
              v22 = 102;
            }
            else if ( memcpy_s_1(
                        (char *)v3 + (unsigned int)v3[12],
                        v17 - v3[12],
                        *((const void *const *)this + 30),
                        v14) )
            {
              v5 = -1072875845;
              if ( !g_wppLevels )
                goto LABEL_53;
              v22 = 103;
            }
            else
            {
              if ( !memcpy_s_1((char *)v3 + (unsigned int)v3[14], v17 - v3[14], *((const void *const *)this + 29), v16) )
              {
                *((_DWORD *)this + 64) = v17;
                wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::swap(
                  (char *)this + 248,
                  &v26);
                v3 = v26;
                goto LABEL_54;
              }
              v5 = -1072875845;
              if ( !g_wppLevels )
                goto LABEL_53;
              v22 = 104;
            }
LABEL_29:
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v22,
              &WPP_72cf6ba4cbe23f0a9b7a240d5b293351_Traceguids,
              this,
              -1072875845);
            goto LABEL_53;
          }
          *v21 = 0;
          *(_OWORD *)(v3 + 6) = 0;
        }
        *(_DWORD *)_o__errno() = 22;
        invalid_parameter_noinfo();
        v5 = -1072875845;
        if ( !g_wppLevels )
          goto LABEL_53;
        v22 = 101;
        goto LABEL_29;
      }
    }
  }
  v5 = -2147024362;
  if ( g_wppLevels )
  {
    v20 = 99;
    goto LABEL_52;
  }
LABEL_53:
  *((_DWORD *)this + 64) = 0;
  wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset((void **)this + 31);
LABEL_54:
  if ( v3 )
    operator delete(v3);
  return v5;
}

```

## disassembly

```asm
0x18003c8c0  mov     [rsp+arg_18], rbx
0x18003c8c5  push    rbp
0x18003c8c6  push    rsi
0x18003c8c7  push    rdi
0x18003c8c8  push    r12
0x18003c8ca  push    r13
0x18003c8cc  push    r14
0x18003c8ce  push    r15
0x18003c8d0  sub     rsp, 30h
0x18003c8d4  mov     rax, [rcx+0E0h]
0x18003c8db  xor     r11d, r11d
0x18003c8de  mov     rdi, rcx
0x18003c8e1  mov     esi, r11d
0x18003c8e4  test    rax, rax
0x18003c8e7  jz      loc_18003CBE7
0x18003c8ed  mov     edx, 7FFFFFFFh
0x18003c8f2  mov     r8d, edx
0x18003c8f5  cmp     [rax], r11w
0x18003c8f9  jz      short loc_18003C905
0x18003c8fb  add     rax, 2
0x18003c8ff  sub     r8, 1
0x18003c903  jnz     short loc_18003C8F5
0x18003c905  mov     rax, r8
0x18003c908  mov     ecx, 80070057h
0x18003c90d  neg     rax
0x18003c910  sbb     ebx, ebx
0x18003c912  not     ebx
0x18003c914  and     ebx, ecx
0x18003c916  test    r8, r8
0x18003c919  jz      loc_18003CBEC
0x18003c91f  mov     rax, rdx
0x18003c922  sub     rax, r8
0x18003c925  add     rax, rax
0x18003c928  neg     r8
0x18003c92b  sbb     r10, r10
0x18003c92e  and     r10, rax
0x18003c931  mov     rax, [rdi+0F0h]
0x18003c938  test    rax, rax
0x18003c93b  jz      loc_18003CBD5
0x18003c941  mov     r8, rdx
0x18003c944  cmp     [rax], r11w
0x18003c948  jz      short loc_18003C954
0x18003c94a  add     rax, 2
0x18003c94e  sub     r8, 1
0x18003c952  jnz     short loc_18003C944
0x18003c954  mov     rax, r8
0x18003c957  neg     rax
0x18003c95a  sbb     ebx, ebx
0x18003c95c  not     ebx
0x18003c95e  and     ebx, ecx
0x18003c960  test    r8, r8
0x18003c963  jz      loc_18003CBD7
0x18003c969  mov     rax, rdx
0x18003c96c  sub     rax, r8
0x18003c96f  add     rax, rax
0x18003c972  neg     r8
0x18003c975  sbb     r9, r9
0x18003c978  and     r9, rax
0x18003c97b  mov     rax, [rdi+0E8h]
0x18003c982  test    rax, rax
0x18003c985  jz      loc_18003CBBF
0x18003c98b  mov     r8, rdx
0x18003c98e  cmp     [rax], r11w
0x18003c992  jz      short loc_18003C99E
0x18003c994  add     rax, 2
0x18003c998  sub     r8, 1
0x18003c99c  jnz     short loc_18003C98E
0x18003c99e  mov     rax, r8
0x18003c9a1  neg     rax
0x18003c9a4  sbb     ebx, ebx
0x18003c9a6  not     ebx
0x18003c9a8  and     ebx, ecx
0x18003c9aa  test    r8, r8
0x18003c9ad  jz      loc_18003CBBB
0x18003c9b3  sub     rdx, r8
0x18003c9b6  lea     ecx, [r10+2]
0x18003c9ba  add     rdx, rdx
0x18003c9bd  mov     dword ptr [rsp+68h+SourceSize], ecx
0x18003c9c1  neg     r8
0x18003c9c4  lea     r15d, [rcx+40h]
0x18003c9c8  sbb     rax, rax
0x18003c9cb  and     rax, rdx
0x18003c9ce  cmp     r15d, 40h ; '@'
0x18003c9d2  jb      loc_18003CBA6
0x18003c9d8  lea     r13d, [r9+2]
0x18003c9dc  lea     r14d, [r15+r13]
0x18003c9e0  cmp     r14d, r15d
0x18003c9e3  jb      loc_18003CBA6
0x18003c9e9  lea     r12d, [rax+2]
0x18003c9ed  lea     ebp, [r14+r12]
0x18003c9f1  cmp     ebp, r14d
0x18003c9f4  jb      loc_18003CBA6
0x18003c9fa  mov     edx, ebp
0x18003c9fc  lea     rcx, [rsp+68h+Block]
0x18003ca01  call    ??$make_unique_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<uchar [0]>(unsigned __int64)
0x18003ca06  mov     rsi, [rax]
0x18003ca09  mov     qword ptr [rax], 0
0x18003ca10  mov     rcx, [rsp+68h+Block]; Block
0x18003ca15  mov     [rsp+68h+arg_10], rsi
0x18003ca1d  mov     [rsp+68h+Block], 0
0x18003ca26  test    rcx, rcx
0x18003ca29  jz      short loc_18003CA30
0x18003ca2b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003ca30  test    rsi, rsi
0x18003ca33  jnz     short loc_18003CA4F
0x18003ca35  mov     ebx, 8007000Eh
0x18003ca3a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003ca41  jb      loc_18003CC18
0x18003ca47  lea     edx, [rsi+64h]
0x18003ca4a  jmp     loc_18003CBFA
0x18003ca4f  mov     edx, dword ptr [rsp+68h+SourceSize]
0x18003ca53  lea     rax, [rsi+8]
0x18003ca57  mov     dword ptr [rsi], 1
0x18003ca5d  mov     [rsi+4], ebp
0x18003ca60  mov     dword ptr [rsi+28h], 40h ; '@'
0x18003ca67  mov     [rsi+2Ch], edx
0x18003ca6a  mov     [rsi+30h], r15d
0x18003ca6e  mov     [rsi+34h], r13d
0x18003ca72  mov     [rsi+38h], r14d
0x18003ca76  mov     [rsi+3Ch], r12d
0x18003ca7a  test    rax, rax
0x18003ca7d  jz      loc_18003CB7B
0x18003ca83  lea     rcx, [rdi+38h]
0x18003ca87  test    rcx, rcx
0x18003ca8a  jz      loc_18003CB71
0x18003ca90  movups  xmm0, xmmword ptr [rcx]
0x18003ca93  mov     r9d, edx; SourceSize
0x18003ca96  lea     edx, [rbp-40h]; DestinationSize
0x18003ca99  movups  xmmword ptr [rax], xmm0
0x18003ca9c  movups  xmm1, xmmword ptr [rcx+10h]
0x18003caa0  lea     rcx, [rsi+40h]; Destination
0x18003caa4  movups  xmmword ptr [rax+10h], xmm1
0x18003caa8  mov     r8, [rdi+0E0h]; Source
0x18003caaf  call    memcpy_s_1
0x18003cab4  test    eax, eax
0x18003cab6  jz      short loc_18003CADA
0x18003cab8  mov     eax, 0C00D36BBh
0x18003cabd  mov     ebx, eax
0x18003cabf  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003cac6  jb      loc_18003CC18
0x18003cacc  mov     edx, 66h ; 'f'
0x18003cad1  mov     [rsp+68h+var_48], eax
0x18003cad5  jmp     loc_18003CBFE
0x18003cada  mov     ecx, [rsi+30h]
0x18003cadd  mov     edx, ebp
0x18003cadf  mov     r8, [rdi+0F0h]; Source
0x18003cae6  sub     edx, ecx; DestinationSize
0x18003cae8  add     rcx, rsi; Destination
0x18003caeb  mov     r9d, r13d; SourceSize
0x18003caee  call    memcpy_s_1
0x18003caf3  test    eax, eax
0x18003caf5  jz      short loc_18003CB12
0x18003caf7  mov     eax, 0C00D36BBh
0x18003cafc  mov     ebx, eax
0x18003cafe  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003cb05  jb      loc_18003CC18
0x18003cb0b  mov     edx, 67h ; 'g'
0x18003cb10  jmp     short loc_18003CAD1
0x18003cb12  mov     ecx, [rsi+38h]
0x18003cb15  mov     edx, ebp
0x18003cb17  mov     r8, [rdi+0E8h]; Source
0x18003cb1e  sub     edx, ecx; DestinationSize
0x18003cb20  add     rcx, rsi; Destination
0x18003cb23  mov     r9d, r12d; SourceSize
0x18003cb26  call    memcpy_s_1
0x18003cb2b  test    eax, eax
0x18003cb2d  jz      short loc_18003CB4A
0x18003cb2f  mov     eax, 0C00D36BBh
0x18003cb34  mov     ebx, eax
0x18003cb36  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003cb3d  jb      loc_18003CC18
0x18003cb43  mov     edx, 68h ; 'h'
0x18003cb48  jmp     short loc_18003CAD1
0x18003cb4a  lea     rcx, [rdi+0F8h]
0x18003cb51  mov     [rdi+100h], ebp
0x18003cb57  lea     rdx, [rsp+68h+arg_10]
0x18003cb5f  call    ?swap@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAXAEAV12@@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::swap(wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>> &)
0x18003cb64  mov     rsi, [rsp+68h+arg_10]
0x18003cb6c  jmp     loc_18003CC2E
0x18003cb71  xorps   xmm0, xmm0
0x18003cb74  movups  xmmword ptr [rax], xmm0
0x18003cb77  movups  xmmword ptr [rax+10h], xmm0
0x18003cb7b  call    cs:__imp__o__errno
0x18003cb81  mov     dword ptr [rax], 16h
0x18003cb87  call    _invalid_parameter_noinfo
0x18003cb8c  mov     eax, 0C00D36BBh
0x18003cb91  mov     ebx, eax
0x18003cb93  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003cb9a  jb      short loc_18003CC18
0x18003cb9c  mov     edx, 65h ; 'e'
0x18003cba1  jmp     loc_18003CAD1
0x18003cba6  mov     ebx, 80070216h
0x18003cbab  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003cbb2  jb      short loc_18003CC18
0x18003cbb4  mov     edx, 63h ; 'c'
0x18003cbb9  jmp     short loc_18003CBFA
0x18003cbbb  mov     ecx, ebx
0x18003cbbd  jmp     short loc_18003CBC1
0x18003cbbf  mov     ebx, ecx
0x18003cbc1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003cbc8  jb      short loc_18003CC18
0x18003cbca  mov     edx, 62h ; 'b'
0x18003cbcf  mov     [rsp+68h+var_48], ecx
0x18003cbd3  jmp     short loc_18003CBFE
0x18003cbd5  mov     ebx, ecx
0x18003cbd7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003cbde  jb      short loc_18003CC18
0x18003cbe0  mov     edx, 61h ; 'a'
0x18003cbe5  jmp     short loc_18003CBFA
0x18003cbe7  mov     ebx, 80070057h
0x18003cbec  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003cbf3  jb      short loc_18003CC18
0x18003cbf5  mov     edx, 60h ; '`'
0x18003cbfa  mov     [rsp+68h+var_48], ebx
0x18003cbfe  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cc05  lea     r8, WPP_72cf6ba4cbe23f0a9b7a240d5b293351_Traceguids
0x18003cc0c  mov     r9, rdi
0x18003cc0f  mov     rcx, [rcx+10h]
0x18003cc13  call    WPP_SF_qD
0x18003cc18  lea     rcx, [rdi+0F8h]
0x18003cc1f  mov     dword ptr [rdi+100h], 0
0x18003cc29  call    ?reset@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::reset(std::nullptr_t)
0x18003cc2e  test    rsi, rsi
0x18003cc31  jz      short loc_18003CC3B
0x18003cc33  mov     rcx, rsi; Block
0x18003cc36  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003cc3b  mov     eax, ebx
0x18003cc3d  mov     rbx, [rsp+68h+arg_18]
0x18003cc45  add     rsp, 30h
0x18003cc49  pop     r15
0x18003cc4b  pop     r14
0x18003cc4d  pop     r13
0x18003cc4f  pop     r12
0x18003cc51  pop     rdi
0x18003cc52  pop     rsi
0x18003cc53  pop     rbp
0x18003cc54  retn
```
