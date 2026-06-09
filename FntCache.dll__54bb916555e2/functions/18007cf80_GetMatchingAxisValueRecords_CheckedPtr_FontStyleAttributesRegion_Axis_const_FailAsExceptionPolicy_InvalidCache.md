# GetMatchingAxisValueRecords<CheckedPtr<FontStyleAttributesRegion::Axis const,FailAsExceptionPolicy<InvalidCacheDataException>,uint>,ScopedArrayWithFixedBuffer<FontStyleAttributes::MatchingAxisValueRecord>>(array_ref<DWRITE_FONT_AXIS_VALUE_FIXED const>,CheckedPtr<FontStyleAttributesRegion::Axis const,FailAsExceptionPolicy<InvalidCacheDataException>,uint>,ScopedArrayWithFixedBuffer<FontStyleAttributes::MatchingAxisValueRecord> &)

- ea: `0x18007cf80`
- end: `0x18007d397`
- name: `??$GetMatchingAxisValueRecords@V?$CheckedPtr@$$CBUAxis@FontStyleAttributesRegion@@V?$FailAsExceptionPolicy@VInvalidCacheDataException@@@@I@@V?$ScopedArrayWithFixedBuffer@UMatchingAxisValueRecord@FontStyleAttributes@@@@@@YAXV?$array_ref@$$CBUDWRITE_FONT_AXIS_VALUE_FIXED@@@@V?$CheckedPtr@$$CBUAxis@FontStyleAttributesRegion@@V?$FailAsExceptionPolicy@VInvalidCacheDataException@@@@I@@AEAV?$ScopedArrayWithFixedBuffer@UMatchingAxisValueRecord@FontStyleAttributes@@@@@Z`
- size: `1047`
- prototype: `void __fastcall(_DWORD **, __int64 *, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting`

## callers

- `0x1800268c0`

## callees

- `0x1800217ac`
- `0x180030770`
- `0x18007cf80`
- `0x18007d3a0`
- `0x18007d468`
- `0x18007d4fc`
- `0x18007d5d8`
- `0x18009e3b8`
- `0x18009e420`
- `0x1800aa650`
- `0x1800ab180`
- `0x1800ab1b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18007d2b6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18007d2b6`

## pseudocode

```c
void __fastcall GetMatchingAxisValueRecords<CheckedPtr<FontStyleAttributesRegion::Axis const,FailAsExceptionPolicy<InvalidCacheDataException>,unsigned int>,ScopedArrayWithFixedBuffer<FontStyleAttributes::MatchingAxisValueRecord>>(
        _DWORD **a1,
        __int64 *a2,
        _QWORD *a3)
{
  __int64 v6; // r15
  __int64 v7; // r8
  __int64 v8; // r9
  unsigned __int64 v9; // rdx
  unsigned __int64 v10; // rcx
  unsigned int *v11; // r10
  unsigned __int64 v12; // rax
  unsigned __int64 v13; // rcx
  unsigned __int64 v14; // rax
  unsigned int *v15; // rbx
  __int64 v16; // rbp
  unsigned int *v17; // r11
  unsigned __int64 v18; // r14
  __int64 v19; // rsi
  unsigned __int64 v20; // rax
  _DWORD *i; // rdx
  signed int v22; // edx
  signed int v23; // ecx
  int *v24; // r10
  int v25; // r9d
  int v26; // eax
  unsigned int v27; // esi
  __int64 v28; // rdx
  __int64 v29; // r11
  __int64 v30; // r9
  unsigned __int64 v31; // r8
  unsigned __int64 v32; // rcx
  unsigned int *v33; // r10
  unsigned __int64 v34; // rax
  unsigned __int64 v35; // rcx
  unsigned __int64 v36; // rax
  unsigned int *v37; // r8
  unsigned int *v38; // rbx
  unsigned int *v39; // r9
  __int64 v40; // rcx
  __int64 j; // rdx
  __int64 k; // rax
  signed int v43; // [rsp+20h] [rbp-A8h] BYREF
  char pExceptionObject[8]; // [rsp+28h] [rbp-A0h] BYREF
  unsigned int *v45; // [rsp+30h] [rbp-98h]
  void *v46[8]; // [rsp+40h] [rbp-88h] BYREF

  v6 = a3[1];
  v7 = *a3;
  if ( v7 != v6 )
  {
    do
    {
      v8 = *(_QWORD *)(v7 + 24);
      v9 = *(unsigned int *)(v7 + 32);
      v10 = *(unsigned int *)(*(_QWORD *)(v7 + 16) + 8LL);
      if ( v10 > v9 )
        goto LABEL_67;
      if ( (unsigned int)v9 - v10 < 4 )
        goto LABEL_67;
      v11 = (unsigned int *)(v8 + v10);
      if ( (((_BYTE)v8 + (_BYTE)v10) & 3) != 0 )
        goto LABEL_67;
      v12 = v10 + 4;
      if ( v10 + 4 < v10
        || v12 > 0xFFFFFFFF
        || (v10 = (unsigned int)v12 + 3LL, v10 < (unsigned int)v12)
        || v10 > 0xFFFFFFFF )
      {
        SafeIntExceptionHandler<Exception>::SafeIntOnOverflow(v10, v9, v7, v8);
      }
      v13 = (unsigned int)v10 & 0xFFFFFFFC;
      if ( v13 > v9 || (v14 = *v11, v9 - v13 < v14) )
LABEL_67:
        FailAsExceptionPolicy<InvalidCacheDataException>::OnOutOfRange(*(_QWORD *)(v7 + 24));
      v15 = (unsigned int *)(v13 + v8);
      v16 = 0;
      v17 = (unsigned int *)(v13 + v8 + ((unsigned int)v14 & 0xFFFFFFF0));
      if ( (unsigned int *)(v13 + v8) != v17 )
      {
        v18 = *((unsigned int *)a2 + 2);
        v19 = *a2;
        do
        {
          v20 = *v15;
          if ( v20 >= v18 )
            FailAsExceptionPolicy<InvalidCacheDataException>::OnOutOfRange(v19);
          for ( i = *a1; ; i += 2 )
          {
            if ( i == a1[1] )
            {
              v22 = 0;
              goto LABEL_19;
            }
            if ( *i == *(_DWORD *)(32 * v20 + v19) )
              break;
          }
          v22 = i[1];
LABEL_19:
          v43 = v22;
          v23 = v15[3];
          v24 = &v43;
          if ( v23 < v22 )
            v24 = (int *)(v15 + 3);
          v25 = v15[2];
          if ( v23 >= v22 )
            v23 = v22;
          if ( v23 >= v25 )
            v25 = *v24;
          if ( v22 == 0x7FFFFFFF )
          {
            v26 = 0x80000000;
          }
          else if ( v22 == 0x80000000 )
          {
            v26 = 0x7FFFFFFF;
          }
          else
          {
            v26 = -v22;
          }
          if ( (unsigned int)(v25 + 0x7FFFFFFF) <= 0xFFFFFFFD )
          {
            if ( (unsigned int)(v26 + 0x7FFFFFFF) <= 0xFFFFFFFD )
              v26 = Fixed16_16::SaturateToInfinity(v25 - (__int64)v22);
          }
          else
          {
            v26 = v25;
          }
          v16 += ((unsigned __int64)(unsigned int)v26 >> 31) + 2 * ((v26 * (__int64)v26) >> 16);
          v15 += 4;
        }
        while ( v15 != v17 );
      }
      *(_QWORD *)(v7 + 8) = v16;
      v7 += 40;
    }
    while ( v7 != v6 );
    LOBYTE(v7) = 0;
    std::stable_sort<FontStyleAttributes::MatchingAxisValueRecord *,std::less<void>>(*a3, a3[1], v7);
    v27 = *((_DWORD *)a2 + 2);
    ScopedArray<bool,20>::ScopedArray<bool,20>(v46, v27);
    memset_0(v46[0], 0, (char *)v46[1] - (char *)v46[0]);
    v28 = *a3;
    v29 = a3[1];
    if ( *a3 != v29 )
    {
      do
      {
        v30 = *(_QWORD *)(v28 + 24);
        v31 = *(unsigned int *)(v28 + 32);
        v32 = *(unsigned int *)(*(_QWORD *)(v28 + 16) + 8LL);
        if ( v32 > v31 )
          goto LABEL_61;
        if ( (unsigned int)v31 - v32 < 4 )
          goto LABEL_61;
        v33 = (unsigned int *)(v30 + v32);
        if ( (((_BYTE)v30 + (_BYTE)v32) & 3) != 0 )
          goto LABEL_61;
        v34 = v32 + 4;
        if ( v32 + 4 < v32
          || v34 > 0xFFFFFFFF
          || (v32 = (unsigned int)v34 + 3LL, v32 < (unsigned int)v34)
          || v32 > 0xFFFFFFFF )
        {
          SafeIntExceptionHandler<Exception>::SafeIntOnOverflow(v32, v28, v31, v30);
        }
        v35 = (unsigned int)v32 & 0xFFFFFFFC;
        if ( v35 > v31 || (v36 = *v33, v31 - v35 < v36) )
LABEL_61:
          FailAsExceptionPolicy<InvalidCacheDataException>::OnOutOfRange(*(_QWORD *)(v28 + 24));
        v37 = (unsigned int *)(v35 + v30);
        v38 = (unsigned int *)(v35 + v30);
        v39 = (unsigned int *)(v35 + v30 + ((unsigned int)v36 & 0xFFFFFFF0));
        while ( v38 != v39 )
        {
          if ( *v38 >= v27 )
          {
            Exception::Exception((Exception *)pExceptionObject, -2003283961, 0);
            v45 = v38;
            throw (InvalidCacheDataException *)pExceptionObject;
          }
          if ( *((_BYTE *)v46[0] + *v38) )
          {
            *(_BYTE *)v28 |= 2u;
            goto LABEL_51;
          }
          v38 += 4;
        }
        while ( v37 != v39 )
        {
          *((_BYTE *)v46[0] + *v37) = 1;
          v37 += 4;
        }
LABEL_51:
        v28 += 40;
      }
      while ( v28 != v29 );
    }
    v40 = a3[1];
    for ( j = *a3; j != v40 && (*(_BYTE *)j & 2) == 0; j += 40 )
      ;
    if ( j != v40 )
    {
      for ( k = j + 40; k != v40; k += 40 )
      {
        if ( (*(_BYTE *)k & 2) == 0 )
        {
          *(_OWORD *)j = *(_OWORD *)k;
          *(_OWORD *)(j + 16) = *(_OWORD *)(k + 16);
          *(_QWORD *)(j + 32) = *(_QWORD *)(k + 32);
          j += 40;
        }
      }
    }
    ScopedArrayWithFixedBuffer<FontStyleAttributes::MatchingAxisValueRecord>::resize(
      a3,
      0xCCCCCCCCCCCCCCCDuLL * ((j - *a3) >> 3));
    std::stable_sort<FontStyleAttributes::MatchingAxisValueRecord *,bool (*)(FontStyleAttributes::MatchingAxisValueRecord const &,FontStyleAttributes::MatchingAxisValueRecord const &)>(
      *a3,
      a3[1]);
    free(v46[2]);
  }
}

```

## disassembly

```asm
0x18007cf80  mov     [rsp+arg_0], rbx
0x18007cf85  push    rbp
0x18007cf86  push    rsi
0x18007cf87  push    rdi
0x18007cf88  push    r12
0x18007cf8a  push    r13
0x18007cf8c  push    r14
0x18007cf8e  push    r15
0x18007cf90  sub     rsp, 90h
0x18007cf97  mov     rax, cs:__security_cookie
0x18007cf9e  xor     rax, rsp
0x18007cfa1  mov     [rsp+0C8h+var_48], rax
0x18007cfa9  mov     rdi, r8
0x18007cfac  mov     r12, rdx
0x18007cfaf  mov     r13, rcx
0x18007cfb2  mov     r15, [r8+8]
0x18007cfb6  mov     r8, [r8]
0x18007cfb9  cmp     r8, r15
0x18007cfbc  jz      loc_18007D2BC
0x18007cfc2  mov     r14d, 0FFFFFFFFh
0x18007cfc8  mov     r11d, 0FFFFFFFCh
0x18007cfce  mov     r9, [r8+18h]
0x18007cfd2  mov     edx, [r8+20h]
0x18007cfd6  mov     rax, [r8+10h]
0x18007cfda  mov     ecx, [rax+8]
0x18007cfdd  cmp     rcx, rdx
0x18007cfe0  ja      loc_18007D326
0x18007cfe6  mov     eax, edx
0x18007cfe8  sub     rax, rcx
0x18007cfeb  cmp     rax, 4
0x18007cfef  jb      loc_18007D326
0x18007cff5  lea     r10, [r9+rcx]
0x18007cff9  test    r10b, 3
0x18007cffd  jnz     loc_18007D326
0x18007d003  lea     rax, [rcx+4]
0x18007d007  cmp     rax, rcx
0x18007d00a  jb      loc_18007D234
0x18007d010  cmp     rax, r14
0x18007d013  ja      loc_18007D234
0x18007d019  mov     eax, eax
0x18007d01b  lea     rcx, [rax+3]
0x18007d01f  cmp     rcx, rax
0x18007d022  jb      loc_18007D234
0x18007d028  cmp     rcx, r14
0x18007d02b  ja      loc_18007D234
0x18007d031  and     rcx, r11
0x18007d034  cmp     rcx, rdx
0x18007d037  ja      loc_18007D326
0x18007d03d  mov     eax, [r10]
0x18007d040  sub     rdx, rcx
0x18007d043  cmp     rdx, rax
0x18007d046  jb      loc_18007D326
0x18007d04c  lea     rbx, [rcx+r9]
0x18007d050  xor     ebp, ebp
0x18007d052  mov     r11d, eax
0x18007d055  and     r11, 0FFFFFFFFFFFFFFF0h
0x18007d059  add     r11, rbx
0x18007d05c  cmp     rbx, r11
0x18007d05f  jz      loc_18007D119
0x18007d065  mov     r14d, [r12+8]
0x18007d06a  mov     rsi, [r12]
0x18007d06e  mov     eax, [rbx]
0x18007d070  cmp     rax, r14
0x18007d073  jnb     loc_18007D365
0x18007d079  shl     rax, 5
0x18007d07d  mov     ecx, [rax+rsi]
0x18007d080  mov     rdx, [r13+0]
0x18007d084  cmp     rdx, [r13+8]
0x18007d088  jz      short loc_18007D098
0x18007d08a  cmp     [rdx], ecx
0x18007d08c  jz      loc_18007D22C
0x18007d092  add     rdx, 8
0x18007d096  jmp     short loc_18007D084
0x18007d098  xor     edx, edx
0x18007d09a  mov     [rsp+0C8h+var_A8], edx
0x18007d09e  lea     rax, [rbx+0Ch]
0x18007d0a2  mov     ecx, [rax]
0x18007d0a4  lea     r10, [rsp+0C8h+var_A8]
0x18007d0a9  cmp     ecx, edx
0x18007d0ab  cmovl   r10, rax
0x18007d0af  mov     r9d, [rbx+8]
0x18007d0b3  cmovge  ecx, edx
0x18007d0b6  cmp     ecx, r9d
0x18007d0b9  jge     loc_18007D224
0x18007d0bf  cmp     edx, 7FFFFFFFh
0x18007d0c5  jz      loc_18007D339
0x18007d0cb  cmp     edx, 80000000h
0x18007d0d1  jz      loc_18007D32F
0x18007d0d7  mov     eax, edx
0x18007d0d9  neg     eax
0x18007d0db  lea     ecx, [r9+7FFFFFFFh]
0x18007d0e2  cmp     ecx, 0FFFFFFFDh
0x18007d0e5  jbe     loc_18007D343
0x18007d0eb  mov     eax, r9d
0x18007d0ee  movsxd  rdx, eax
0x18007d0f1  imul    rdx, rdx
0x18007d0f5  sar     rdx, 10h
0x18007d0f9  mov     ecx, eax
0x18007d0fb  shr     rcx, 1Fh
0x18007d0ff  add     rcx, rbp
0x18007d102  lea     rbp, [rcx+rdx*2]
0x18007d106  add     rbx, 10h
0x18007d10a  cmp     rbx, r11
0x18007d10d  jnz     loc_18007D06E
0x18007d113  mov     r14d, 0FFFFFFFFh
0x18007d119  mov     [r8+8], rbp
0x18007d11d  add     r8, 28h ; '('
0x18007d121  cmp     r8, r15
0x18007d124  jnz     loc_18007CFC8
0x18007d12a  xor     r8b, r8b
0x18007d12d  mov     rdx, [rdi+8]
0x18007d131  mov     rcx, [rdi]
0x18007d134  call    ??$stable_sort@PEAUMatchingAxisValueRecord@FontStyleAttributes@@U?$less@X@std@@@std@@YAXQEAUMatchingAxisValueRecord@FontStyleAttributes@@0U?$less@X@0@@Z; std::stable_sort<FontStyleAttributes::MatchingAxisValueRecord *,std::less<void>>(FontStyleAttributes::MatchingAxisValueRecord * const,FontStyleAttributes::MatchingAxisValueRecord * const,std::less<void>)
0x18007d139  mov     esi, [r12+8]
0x18007d13e  mov     edx, esi
0x18007d140  lea     rcx, [rsp+0C8h+var_88]
0x18007d145  call    ??0?$ScopedArray@_N$0BE@@@QEAA@_K@Z; ScopedArray<bool,20>::ScopedArray<bool,20>(unsigned __int64)
0x18007d14a  nop
0x18007d14b  mov     r8, [rsp+0C8h+var_80]
0x18007d150  mov     rcx, [rsp+0C8h+var_88]; void *
0x18007d155  sub     r8, rcx; Size
0x18007d158  xor     edx, edx; Val
0x18007d15a  call    memset_0
0x18007d15f  mov     rdx, [rdi]
0x18007d162  mov     r11, [rdi+8]
0x18007d166  mov     bpl, 2
0x18007d169  cmp     rdx, r11
0x18007d16c  jz      loc_18007D25F
0x18007d172  mov     r15d, 0FFFFFFFCh
0x18007d178  mov     r9, [rdx+18h]
0x18007d17c  mov     r8d, [rdx+20h]
0x18007d180  mov     rax, [rdx+10h]
0x18007d184  mov     ecx, [rax+8]
0x18007d187  cmp     rcx, r8
0x18007d18a  ja      loc_18007D2E7
0x18007d190  mov     eax, r8d
0x18007d193  sub     rax, rcx
0x18007d196  cmp     rax, 4
0x18007d19a  jb      loc_18007D2E7
0x18007d1a0  lea     r10, [r9+rcx]
0x18007d1a4  test    r10b, 3
0x18007d1a8  jnz     loc_18007D2E7
0x18007d1ae  lea     rax, [rcx+4]
0x18007d1b2  cmp     rax, rcx
0x18007d1b5  jb      loc_18007D26E
0x18007d1bb  cmp     rax, r14
0x18007d1be  ja      loc_18007D26E
0x18007d1c4  mov     eax, eax
0x18007d1c6  lea     rcx, [rax+3]
0x18007d1ca  cmp     rcx, rax
0x18007d1cd  jb      loc_18007D26E
0x18007d1d3  cmp     rcx, r14
0x18007d1d6  ja      loc_18007D26E
0x18007d1dc  and     rcx, r15
0x18007d1df  cmp     rcx, r8
0x18007d1e2  ja      loc_18007D2E7
0x18007d1e8  mov     eax, [r10]
0x18007d1eb  sub     r8, rcx
0x18007d1ee  cmp     r8, rax
0x18007d1f1  jb      loc_18007D2E7
0x18007d1f7  lea     r8, [rcx+r9]
0x18007d1fb  mov     rbx, r8
0x18007d1fe  mov     r9d, eax
0x18007d201  and     r9, 0FFFFFFFFFFFFFFF0h
0x18007d205  add     r9, r8
0x18007d208  cmp     rbx, r9
0x18007d20b  jnz     short loc_18007D23A
0x18007d20d  cmp     r8, r9
0x18007d210  jz      short loc_18007D252
0x18007d212  mov     ecx, [r8]
0x18007d215  mov     rax, [rsp+0C8h+var_88]
0x18007d21a  mov     byte ptr [rcx+rax], 1
0x18007d21e  add     r8, 10h
0x18007d222  jmp     short loc_18007D20D
0x18007d224  mov     r9d, [r10]
0x18007d227  jmp     loc_18007D0BF
0x18007d22c  mov     edx, [rdx+4]
0x18007d22f  jmp     loc_18007D09A
0x18007d234  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VException@@@@SAXXZ; SafeIntExceptionHandler<Exception>::SafeIntOnOverflow(void)
0x18007d23a  cmp     [rbx], esi
0x18007d23c  jnb     loc_18007D36E
0x18007d242  mov     ecx, [rbx]
0x18007d244  mov     rax, [rsp+0C8h+var_88]
0x18007d249  cmp     byte ptr [rcx+rax], 0
0x18007d24d  jz      short loc_18007D268
0x18007d24f  or      [rdx], bpl
0x18007d252  add     rdx, 28h ; '('
0x18007d256  cmp     rdx, r11
0x18007d259  jnz     loc_18007D178
0x18007d25f  mov     rcx, [rdi+8]
0x18007d263  mov     rdx, [rdi]
0x18007d266  jmp     short loc_18007D27D
0x18007d268  add     rbx, 10h
0x18007d26c  jmp     short loc_18007D208
0x18007d26e  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VException@@@@SAXXZ; SafeIntExceptionHandler<Exception>::SafeIntOnOverflow(void)
0x18007d274  test    [rdx], bpl
0x18007d277  jnz     short loc_18007D282
0x18007d279  add     rdx, 28h ; '('
0x18007d27d  cmp     rdx, rcx
0x18007d280  jnz     short loc_18007D274
0x18007d282  cmp     rdx, rcx
0x18007d285  jnz     short loc_18007D2F0
0x18007d287  sub     rdx, [rdi]
0x18007d28a  sar     rdx, 3
0x18007d28e  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18007d298  imul    rdx, rax
0x18007d29c  mov     rcx, rdi
0x18007d29f  call    ?resize@?$ScopedArrayWithFixedBuffer@UMatchingAxisValueRecord@FontStyleAttributes@@@@QEAAX_K@Z; ScopedArrayWithFixedBuffer<FontStyleAttributes::MatchingAxisValueRecord>::resize(unsigned __int64)
0x18007d2a4  mov     rdx, [rdi+8]
0x18007d2a8  mov     rcx, [rdi]
0x18007d2ab  call    ??$stable_sort@PEAUMatchingAxisValueRecord@FontStyleAttributes@@P6A_NAEBU12@0@Z@std@@YAXQEAUMatchingAxisValueRecord@FontStyleAttributes@@0P6A_NAEBU12@1@Z@Z; std::stable_sort<FontStyleAttributes::MatchingAxisValueRecord *,bool (*)(FontStyleAttributes::MatchingAxisValueRecord const &,FontStyleAttributes::MatchingAxisValueRecord const &)>(FontStyleAttributes::MatchingAxisValueRecord * const,FontStyleAttributes::MatchingAxisValueRecord * const,bool (*)(FontStyleAttributes::MatchingAxisValueRecord const &,FontStyleAttributes::MatchingAxisValueRecord const &))
0x18007d2b0  nop
0x18007d2b1  mov     rcx, [rsp+0C8h+Block]; Block
0x18007d2b6  call    cs:__imp_free
0x18007d2bc  mov     rcx, [rsp+0C8h+var_48]
0x18007d2c4  xor     rcx, rsp; StackCookie
0x18007d2c7  call    __security_check_cookie
0x18007d2cc  mov     rbx, [rsp+0C8h+arg_0]
0x18007d2d4  add     rsp, 90h
0x18007d2db  pop     r15
0x18007d2dd  pop     r14
0x18007d2df  pop     r13
0x18007d2e1  pop     r12
0x18007d2e3  pop     rdi
0x18007d2e4  pop     rsi
0x18007d2e5  pop     rbp
0x18007d2e6  retn
0x18007d2e7  mov     rcx, r9
0x18007d2ea  call    ?OnOutOfRange@?$FailAsExceptionPolicy@VInvalidCacheDataException@@@@SAXPEBX@Z; FailAsExceptionPolicy<InvalidCacheDataException>::OnOutOfRange(void const *)
0x18007d2f0  lea     rax, [rdx+28h]
0x18007d2f4  jmp     short loc_18007D316
0x18007d2f6  movups  xmm0, xmmword ptr [rax]
0x18007d2f9  movups  xmmword ptr [rdx], xmm0
0x18007d2fc  movups  xmm1, xmmword ptr [rax+10h]
0x18007d300  movups  xmmword ptr [rdx+10h], xmm1
0x18007d304  movsd   xmm0, qword ptr [rax+20h]
0x18007d309  movsd   qword ptr [rdx+20h], xmm0
0x18007d30e  add     rdx, 28h ; '('
0x18007d312  add     rax, 28h ; '('
0x18007d316  cmp     rax, rcx
0x18007d319  jz      loc_18007D287
0x18007d31f  test    [rax], bpl
0x18007d322  jnz     short loc_18007D312
0x18007d324  jmp     short loc_18007D2F6
0x18007d326  mov     rcx, r9
0x18007d329  call    ?OnOutOfRange@?$FailAsExceptionPolicy@VInvalidCacheDataException@@@@SAXPEBX@Z; FailAsExceptionPolicy<InvalidCacheDataException>::OnOutOfRange(void const *)
0x18007d32f  mov     eax, 7FFFFFFFh
0x18007d334  jmp     loc_18007D0DB
0x18007d339  mov     eax, 80000000h
0x18007d33e  jmp     loc_18007D0DB
0x18007d343  lea     ecx, [rax+7FFFFFFFh]
0x18007d349  cmp     ecx, 0FFFFFFFDh
0x18007d34c  ja      loc_18007D0EE
0x18007d352  movsxd  rax, edx
0x18007d355  movsxd  rcx, r9d
0x18007d358  sub     rcx, rax; __int64
0x18007d35b  call    ?SaturateToInfinity@Fixed16_16@@CAH_J@Z; Fixed16_16::SaturateToInfinity(__int64)
0x18007d360  jmp     loc_18007D0EE
0x18007d365  mov     rcx, rsi
0x18007d368  call    ?OnOutOfRange@?$FailAsExceptionPolicy@VInvalidCacheDataException@@@@SAXPEBX@Z; FailAsExceptionPolicy<InvalidCacheDataException>::OnOutOfRange(void const *)
0x18007d36e  xor     r8d, r8d; unsigned int
0x18007d371  mov     edx, 88985007h; int
0x18007d376  lea     rcx, [rsp+0C8h+pExceptionObject]; this
0x18007d37b  call    ??0Exception@@IEAA@HI@Z; Exception::Exception(int,uint)
0x18007d380  mov     [rsp+0C8h+var_98], rbx
0x18007d385  lea     rdx, _TI2?AVInvalidCacheDataException@@; pThrowInfo
0x18007d38c  lea     rcx, [rsp+0C8h+pExceptionObject]; pExceptionObject
0x18007d391  call    _CxxThrowException_0
```
