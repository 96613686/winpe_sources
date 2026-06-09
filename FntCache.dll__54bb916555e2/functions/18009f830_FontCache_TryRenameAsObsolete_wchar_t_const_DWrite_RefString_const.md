# FontCache::TryRenameAsObsolete(wchar_t const *,DWrite::RefString const &)

- ea: `0x18009f830`
- end: `0x18009fad8`
- name: `?TryRenameAsObsolete@FontCache@@SAJPEB_WAEBVRefString@DWrite@@@Z`
- size: `680`
- prototype: `__int64 __fastcall(LPCWSTR lpExistingFileName, const struct DWrite::RefString *)`
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x180041908`
- `0x180067e1c`
- `0x180096954`

## callees

- `0x18000bc70`
- `0x180028c50`
- `0x18004d664`
- `0x18008e180`
- `0x18009f830`
- `0x18009fae0`
- `0x1800aa650`
- `0x1800b4fd4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__i64tow_s` at `0x18009f918`
- `api-ms-win-crt-private-l1-1-0!_o__i64tow_s` at `0x18009f918`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009fa30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009fa30`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18009f8ea`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18009f8ea`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18009fa22`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18009fa22`

## string_xrefs

- `0x18009f950`: `FontCache-Obsolete-`

## pseudocode

```c
__int64 __fastcall FontCache::TryRenameAsObsolete(LPCWSTR lpExistingFileName, const struct DWrite::RefString *a2)
{
  __int64 v3; // rbx
  int v4; // edx
  DWORD i; // r14d
  const char *v6; // rdx
  __int64 v7; // rax
  struct DWrite::RefString::Data *v8; // rdi
  signed int LastError; // eax
  unsigned int v10; // esi
  struct DWrite::RefString::Data *v12; // [rsp+28h] [rbp-E0h] BYREF
  __int64 v13; // [rsp+30h] [rbp-D8h] BYREF
  _QWORD v14[2]; // [rsp+38h] [rbp-D0h] BYREF
  __int16 v15; // [rsp+48h] [rbp-C0h]
  __int128 v16; // [rsp+58h] [rbp-B0h]
  __int128 v17; // [rsp+68h] [rbp-A0h]
  _OWORD v18[8]; // [rsp+108h] [rbp+0h] BYREF
  __int128 v19; // [rsp+188h] [rbp+80h]
  _OWORD v20[11]; // [rsp+198h] [rbp+90h] BYREF
  const wchar_t *v21; // [rsp+248h] [rbp+140h]
  __int64 v22; // [rsp+250h] [rbp+148h]

  v3 = *(_QWORD *)a2;
  v13 = v3;
  _InterlockedIncrement((volatile signed __int32 *)v3);
  v4 = *(_DWORD *)(v3 + 4);
  if ( v4 && *(_WORD *)DWrite::RefString::operator[](&v13, (unsigned int)(v4 - 1)) != 92 )
  {
    v14[0] = v3 + 8;
    v14[1] = *(unsigned int *)(v3 + 4);
    v15 = 92;
    DWrite::RefString::RefString(&v12, v14);
    DWrite::RefString::operator=(&v13, &v12);
    DWrite::RefString::DecrementRef(v12);
    v3 = v13;
  }
  for ( i = GetTickCount() % 0x3E8; ; ++i )
  {
    if ( (unsigned int)_o__i64tow_s(i, v18, 66) )
    {
      FailAssert(0x1F8u, v6);
      JUMPOUT(0x18009FAD7LL);
    }
    v7 = -1;
    do
      ++v7;
    while ( *((_WORD *)v18 + v7) );
    *((_QWORD *)&v19 + 1) = v7;
    *(_QWORD *)&v16 = v3 + 8;
    *((_QWORD *)&v16 + 1) = *(unsigned int *)(v3 + 4);
    *(_QWORD *)&v17 = L"FontCache-Obsolete-";
    *((_QWORD *)&v17 + 1) = 19;
    v20[0] = v16;
    v20[1] = v17;
    v20[2] = v18[0];
    v20[3] = v18[1];
    v20[4] = v18[2];
    v20[5] = v18[3];
    v20[6] = v18[4];
    v20[7] = v18[5];
    v20[8] = v18[6];
    v20[9] = v18[7];
    v20[10] = v19;
    v21 = L".dat";
    v22 = 4;
    DWrite::RefString::RefString(&v12, v20);
    v8 = v12;
    if ( MoveFileExW(lpExistingFileName, (LPCWSTR)v12 + 4, 0)
      || (LastError = GetLastError(), v10 = LastError, LastError == 2) )
    {
      DWrite::RefString::DecrementRef(v8);
      DWrite::RefString::DecrementRef((struct DWrite::RefString::Data *)v3);
      return 0;
    }
    if ( LastError != 183 )
      break;
    DWrite::RefString::DecrementRef(v8);
  }
  if ( LastError > 0 )
    v10 = (unsigned __int16)LastError | 0x80070000;
  DWrite::RefString::DecrementRef(v8);
  DWrite::RefString::DecrementRef((struct DWrite::RefString::Data *)v3);
  return v10;
}

```

## disassembly

```asm
0x18009f830  mov     rax, rsp
0x18009f833  mov     [rax+10h], rbx
0x18009f837  mov     [rax+18h], rsi
0x18009f83b  push    rbp
0x18009f83c  push    rdi
0x18009f83d  push    r12
0x18009f83f  push    r14
0x18009f841  push    r15
0x18009f843  lea     rbp, [rax-1D8h]
0x18009f84a  sub     rsp, 2B0h
0x18009f851  movaps  xmmword ptr [rax-38h], xmm6
0x18009f855  movaps  xmmword ptr [rax-48h], xmm7
0x18009f859  movaps  xmmword ptr [rax-58h], xmm8
0x18009f85e  movaps  xmmword ptr [rax-68h], xmm9
0x18009f863  movaps  xmmword ptr [rax-78h], xmm10
0x18009f868  mov     rax, cs:__security_cookie
0x18009f86f  xor     rax, rsp
0x18009f872  mov     [rbp+1D0h+var_80], rax
0x18009f879  mov     r15, rcx
0x18009f87c  mov     rbx, [rdx]
0x18009f87f  mov     [rsp+2D0h+var_2A8], rbx
0x18009f884  lock inc dword ptr [rbx]
0x18009f887  mov     edx, [rbx+4]
0x18009f88a  xor     r12d, r12d
0x18009f88d  test    edx, edx
0x18009f88f  jz      short loc_18009F8EA
0x18009f891  dec     edx
0x18009f893  lea     rcx, [rsp+2D0h+var_2A8]
0x18009f898  call    ??ARefString@DWrite@@QEBAAEB_WI@Z; DWrite::RefString::operator[](uint)
0x18009f89d  lea     ecx, [r12+5Ch]
0x18009f8a2  cmp     [rax], cx
0x18009f8a5  jz      short loc_18009F8EA
0x18009f8a7  lea     rax, [rbx+8]
0x18009f8ab  mov     [rsp+2D0h+var_2A0], rax
0x18009f8b0  mov     eax, [rbx+4]
0x18009f8b3  mov     qword ptr [rsp+2D0h+var_298], rax
0x18009f8b8  mov     [rsp+2D0h+var_290], cx
0x18009f8bd  lea     rdx, [rsp+2D0h+var_2A0]
0x18009f8c2  lea     rcx, [rsp+2D0h+var_2B0]
0x18009f8c7  call    ??$?0V?$StringSum@PEB_W_W@@@RefString@DWrite@@QEAA@AEBV?$StringExpr@V?$StringSum@PEB_W_W@@@@@Z; DWrite::RefString::RefString(StringExpr<StringSum<wchar_t const *,wchar_t>> const &)
0x18009f8cc  lea     rdx, [rsp+2D0h+var_2B0]
0x18009f8d1  lea     rcx, [rsp+2D0h+var_2A8]
0x18009f8d6  call    ??4RefString@DWrite@@QEAAAEAV01@AEBV01@@Z; DWrite::RefString::operator=(DWrite::RefString const &)
0x18009f8db  mov     rcx, [rsp+2D0h+var_2B0]; struct DWrite::RefString::Data *
0x18009f8e0  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x18009f8e5  mov     rbx, [rsp+2D0h+var_2A8]
0x18009f8ea  call    cs:__imp_GetTickCount
0x18009f8f0  mov     r14d, eax
0x18009f8f3  mov     eax, 10624DD3h
0x18009f8f8  mul     r14d
0x18009f8fb  shr     edx, 6
0x18009f8fe  imul    ecx, edx, 3E8h
0x18009f904  sub     r14d, ecx
0x18009f907  mov     ecx, r14d
0x18009f90a  mov     r9d, 0Ah
0x18009f910  lea     r8d, [r9+38h]
0x18009f914  lea     rdx, [rbp+1D0h+var_1D0]
0x18009f918  call    cs:__imp__o__i64tow_s
0x18009f91e  test    eax, eax
0x18009f920  jnz     loc_18009FACD
0x18009f926  lea     rcx, [rbp+1D0h+var_1D0]
0x18009f92a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18009f92e  inc     rax
0x18009f931  cmp     [rcx+rax*2], r12w
0x18009f936  jnz     short loc_18009F92E
0x18009f938  mov     [rbp+1D0h+var_148], rax
0x18009f93f  lea     rax, [rbx+8]
0x18009f943  mov     qword ptr [rsp+2D0h+var_288+8], rax
0x18009f948  mov     eax, [rbx+4]
0x18009f94b  mov     qword ptr [rsp+2D0h+var_278], rax
0x18009f950  lea     rax, aFontcacheObsol; "FontCache-Obsolete-"
0x18009f957  mov     qword ptr [rsp+2D0h+var_278+8], rax
0x18009f95c  mov     [rsp+2D0h+var_268], 13h
0x18009f965  movaps  xmm2, [rbp+1D0h+var_1D0]
0x18009f969  movaps  xmm3, [rbp+1D0h+var_1C0]
0x18009f96d  movaps  xmm4, [rbp+1D0h+var_1B0]
0x18009f971  movaps  xmm5, [rbp+1D0h+var_1A0]
0x18009f975  movaps  xmm6, [rbp+1D0h+var_190]
0x18009f979  movaps  xmm7, [rbp+1D0h+var_180]
0x18009f97d  movaps  xmm8, [rbp+1D0h+var_170]
0x18009f982  movaps  xmm9, [rbp+1D0h+var_160]
0x18009f987  movaps  xmm10, xmmword ptr [rbp+80h]
0x18009f98f  movaps  xmm0, [rsp+2D0h+var_288+8]
0x18009f994  movups  [rbp+1D0h+var_140], xmm0
0x18009f99b  movaps  xmm1, [rsp+2D0h+var_278+8]
0x18009f9a0  movups  [rbp+1D0h+var_130], xmm1
0x18009f9a7  movups  [rbp+1D0h+var_120], xmm2
0x18009f9ae  movups  [rbp+1D0h+var_110], xmm3
0x18009f9b5  movups  [rbp+1D0h+var_100], xmm4
0x18009f9bc  movups  [rbp+1D0h+var_F0], xmm5
0x18009f9c3  movups  [rbp+1D0h+var_E0], xmm6
0x18009f9ca  movups  [rbp+1D0h+var_D0], xmm7
0x18009f9d1  movups  [rbp+1D0h+var_C0], xmm8
0x18009f9d9  movups  [rbp+1D0h+var_B0], xmm9
0x18009f9e1  movups  [rbp+1D0h+var_A0], xmm10
0x18009f9e9  lea     rax, aDat; ".dat"
0x18009f9f0  mov     [rbp+1D0h+var_90], rax
0x18009f9f7  mov     [rbp+1D0h+var_88], 4
0x18009fa02  lea     rdx, [rbp+1D0h+var_140]
0x18009fa09  lea     rcx, [rsp+2D0h+var_2B0]
0x18009fa0e  call    ??$?0V?$StringSum@V?$StringSum@V?$StringSum@PEB_WPEB_W@@V?$IntegerConversionExpr@$09@@@@PEB_W@@@RefString@DWrite@@QEAA@AEBV?$StringExpr@V?$StringSum@V?$StringSum@V?$StringSum@PEB_WPEB_W@@V?$IntegerConversionExpr@$09@@@@PEB_W@@@@@Z; DWrite::RefString::RefString(StringExpr<StringSum<StringSum<StringSum<wchar_t const *,wchar_t const *>,IntegerConversionExpr<10>>,wchar_t const *>> const &)
0x18009fa13  mov     rdi, [rsp+2D0h+var_2B0]
0x18009fa18  lea     rdx, [rdi+8]; lpNewFileName
0x18009fa1c  xor     r8d, r8d; dwFlags
0x18009fa1f  mov     rcx, r15; lpExistingFileName
0x18009fa22  call    cs:__imp_MoveFileExW
0x18009fa28  test    eax, eax
0x18009fa2a  jnz     loc_18009FAB8
0x18009fa30  call    cs:__imp_GetLastError
0x18009fa36  mov     esi, eax
0x18009fa38  cmp     eax, 2
0x18009fa3b  jz      short loc_18009FAB8
0x18009fa3d  cmp     eax, 0B7h
0x18009fa42  jnz     short loc_18009FA54
0x18009fa44  mov     rcx, rdi; struct DWrite::RefString::Data *
0x18009fa47  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x18009fa4c  inc     r14d
0x18009fa4f  jmp     loc_18009F907
0x18009fa54  test    eax, eax
0x18009fa56  jle     short loc_18009FA61
0x18009fa58  movzx   esi, ax
0x18009fa5b  or      esi, 80070000h
0x18009fa61  mov     rcx, rdi; struct DWrite::RefString::Data *
0x18009fa64  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x18009fa69  nop
0x18009fa6a  mov     rcx, rbx; struct DWrite::RefString::Data *
0x18009fa6d  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x18009fa72  mov     eax, esi
0x18009fa74  mov     rcx, [rbp+1D0h+var_80]
0x18009fa7b  xor     rcx, rsp; StackCookie
0x18009fa7e  call    __security_check_cookie
0x18009fa83  lea     r11, [rsp+2D0h+var_20]
0x18009fa8b  mov     rbx, [r11+38h]
0x18009fa8f  mov     rsi, [r11+40h]
0x18009fa93  movaps  xmm6, xmmword ptr [r11-10h]
0x18009fa98  movaps  xmm7, xmmword ptr [r11-20h]
0x18009fa9d  movaps  xmm8, xmmword ptr [r11-30h]
0x18009faa2  movaps  xmm9, xmmword ptr [r11-40h]
0x18009faa7  movaps  xmm10, xmmword ptr [r11-50h]
0x18009faac  mov     rsp, r11
0x18009faaf  pop     r15
0x18009fab1  pop     r14
0x18009fab3  pop     r12
0x18009fab5  pop     rdi
0x18009fab6  pop     rbp
0x18009fab7  retn
0x18009fab8  mov     rcx, rdi; struct DWrite::RefString::Data *
0x18009fabb  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x18009fac0  nop
0x18009fac1  mov     rcx, rbx; struct DWrite::RefString::Data *
0x18009fac4  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x18009fac9  xor     eax, eax
0x18009facb  jmp     short loc_18009FA74
0x18009facd  mov     ecx, 1F8h; unsigned int
0x18009fad2  call    ?FailAssert@@YAXIPEBD@Z; FailAssert(uint,char const *)
```
