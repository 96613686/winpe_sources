# std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,__int64>(std::back_insert_iterator<std::_Fmt_buffer<char>>,__int64,std::_Basic_format_specs<char>,std::_Lazy_locale)

- ea: `0x14004e620`
- end: `0x14004e9d8`
- name: `??$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@_J@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@_JU?$_Basic_format_specs@D@0@V_Lazy_locale@0@@Z`
- size: `952`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x14004cc34`

## callees

- `0x1400054c0`
- `0x1400498e8`
- `0x14004b464`
- `0x14004d834`
- `0x14004e620`
- `0x140050554`
- `0x140050a18`
- `0x140050c40`
- `0x1400518fc`
- `0x140054144`
- `0x14005a010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x14004e83b`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x14004e83b`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
_QWORD *__fastcall std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,__int64>(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  char v8; // al
  int v9; // edi
  int v10; // eax
  char *v11; // rcx
  char *v12; // r12
  int v13; // eax
  __int64 v14; // rdx
  char v15; // r14
  char v16; // cl
  const char *v17; // rcx
  __int64 v18; // rax
  void (__fastcall ***v19)(_QWORD, __int64); // rax
  char *v20; // rax
  int v21; // edx
  unsigned __int64 v22; // r8
  unsigned __int64 v23; // r9
  char *v24; // r11
  int v26; // [rsp+20h] [rbp-E0h]
  char v27; // [rsp+30h] [rbp-D0h] BYREF
  int v28; // [rsp+34h] [rbp-CCh] BYREF
  __int128 v29; // [rsp+40h] [rbp-C0h] BYREF
  int v30; // [rsp+50h] [rbp-B0h]
  int v31; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v32; // [rsp+68h] [rbp-98h] BYREF
  char *v33; // [rsp+70h] [rbp-90h] BYREF
  __int128 v34; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v35[10]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v36; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v37; // [rsp+F0h] [rbp-10h]
  unsigned __int64 v38; // [rsp+F8h] [rbp-8h]
  _BYTE v39[32]; // [rsp+100h] [rbp+0h] BYREF
  char v40; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v41[64]; // [rsp+121h] [rbp+21h] BYREF
  char v42[15]; // [rsp+161h] [rbp+61h] BYREF

  v32 = a3;
  v8 = *(_BYTE *)(a4 + 8);
  if ( v8 == 99 )
  {
    if ( (unsigned __int64)(a3 + 128) > 0xFF )
      std::_Throw_format_error("integral cannot be stored in char");
    *(_BYTE *)(a4 + 11) = 0;
    v29 = *(_OWORD *)a4;
    v30 = *(_DWORD *)(a4 + 16);
    std::_Fmt_write<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>((__int64)a1, a2, a3, &v29, a5);
    return a1;
  }
  v9 = 2;
  if ( !*(_BYTE *)(a4 + 10) )
    *(_BYTE *)(a4 + 10) = 2;
  if ( v8 != 66 )
  {
    if ( v8 == 88 )
    {
LABEL_13:
      v10 = 16;
      goto LABEL_15;
    }
    if ( v8 != 98 )
    {
      if ( v8 == 111 )
      {
        v10 = 8;
        goto LABEL_15;
      }
      if ( v8 != 120 )
      {
        v10 = 10;
        goto LABEL_15;
      }
      goto LABEL_13;
    }
  }
  v10 = 2;
LABEL_15:
  v26 = v10;
  std::_Integer_to_chars<__int64>(&v29, &v40, v42, a3);
  v11 = &v40;
  v33 = &v40;
  v12 = (char *)v29;
  v13 = v29 - (unsigned int)&v40;
  v28 = v13;
  v14 = v32;
  if ( v32 < 0 )
  {
    v11 = v41;
    v33 = v41;
  }
  else if ( *(_BYTE *)(a4 + 10) != 2 )
  {
    v28 = ++v13;
  }
  v15 = 1;
  if ( *(_BYTE *)(a4 + 8) == 88 && v11 != (char *)v29 )
  {
    do
    {
      if ( (unsigned __int8)(*v11 - 97) <= 0x19u )
        *v11 -= 32;
      ++v11;
    }
    while ( v11 != v12 );
    v13 = v28;
    v14 = v32;
  }
  v34 = 0u;
  if ( !*(_BYTE *)(a4 + 11) )
    goto LABEL_41;
  v16 = *(_BYTE *)(a4 + 8);
  switch ( v16 )
  {
    case 'B':
      v17 = "0B";
      goto LABEL_38;
    case 'X':
      v17 = "0X";
      goto LABEL_38;
    case 'b':
      v17 = "0b";
      goto LABEL_38;
    case 'o':
      if ( v14 )
      {
        v17 = "0";
        *((_QWORD *)&v29 + 1) = 1;
        v9 = 1;
LABEL_39:
        *(_QWORD *)&v29 = v17;
        goto LABEL_40;
      }
      break;
    case 'x':
      v17 = "0x";
LABEL_38:
      *((_QWORD *)&v29 + 1) = 2;
      goto LABEL_39;
  }
  v29 = 0u;
  v9 = 0;
LABEL_40:
  v34 = v29;
  v13 += v9;
  v28 = v13;
LABEL_41:
  v31 = 0;
  v36 = 0;
  v37 = 0;
  v38 = 15;
  LOBYTE(v36) = 0;
  if ( *(_BYTE *)(a4 + 12) )
  {
    if ( a5 )
    {
      *((_QWORD *)&v29 + 1) = *(_QWORD *)(a5 + 8);
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v29 + 1) + 8LL))(*((_QWORD *)&v29 + 1));
    }
    else
    {
      *((_QWORD *)&v29 + 1) = std::locale::_Init(1);
    }
    v18 = std::use_facet<std::numpunct<char>>(&v29);
    (*(void (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v18 + 40LL))(v18, v39);
    std::string::operator=(&v36, v39);
    std::string::~string(v39);
    if ( *((_QWORD *)&v29 + 1) )
    {
      v19 = (void (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)&v29 + 1) + 16LL))(*((_QWORD *)&v29 + 1));
      if ( v19 )
        (**v19)(v19, 1);
    }
    v20 = (char *)&v36;
    if ( v38 > 0xF )
      v20 = (char *)v36;
    v21 = 0;
    if ( v37 )
    {
      v22 = v12 - v33;
      v23 = *v20;
      if ( v12 - v33 > v23 )
      {
        v24 = &v20[v37];
        do
        {
          v22 -= (char)v23;
          ++v21;
          if ( v20 + 1 != v24 )
            ++v20;
          v23 = *v20;
        }
        while ( v22 > v23 );
      }
    }
    v31 = v21;
    v13 = v21 + v28;
    v28 += v21;
  }
  if ( !*(_BYTE *)(a4 + 13) || *(_BYTE *)(a4 + 9) )
    v15 = 0;
  v27 = v15;
  v35[0] = v12;
  v35[1] = a4;
  v35[2] = &v32;
  v35[3] = &v34;
  v35[4] = &v27;
  v35[5] = &v28;
  v35[6] = &v31;
  v35[7] = &v33;
  v35[8] = &v36;
  v35[9] = &a5;
  if ( v15 )
    `std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,__int64>'::`2'::_lambda_1_::operator()(
      v35,
      a1,
      a2);
  else
    ____Write_aligned_V__back_insert_iterator_V___Fmt_buffer_D_std___std__U___Basic_format_specs_D_2_AEAV_lambda_1___1_____Write_integral_DV__back_insert_iterator_V___Fmt_buffer_D_std___std___J_2_YA_AV12_V12__JU32_V_Lazy_locale_2__Z__std__YA_AV__back_insert_iterator_V___Fmt_buffer_D_std___0_V10_HAEBU___Basic_format_specs_D_0_W4_Fmt_align_0_AEAV_lambda_1___1_____Write_integral_DV__back_insert_iterator_V___Fmt_buffer_D_std___std___J_0_YA_AV10_0_JU20_V_Lazy_locale_0__Z__Z(
      a1,
      a2,
      v13,
      a4,
      v26,
      (__int64)v35);
  std::string::~string(&v36);
  return a1;
}

```

## disassembly

```asm
0x14004e620  mov     [rsp-8+arg_8], rbx
0x14004e625  push    rbp
0x14004e626  push    rsi
0x14004e627  push    rdi
0x14004e628  push    r12
0x14004e62a  push    r13
0x14004e62c  push    r14
0x14004e62e  push    r15
0x14004e630  lea     rbp, [rsp-80h]
0x14004e635  sub     rsp, 180h
0x14004e63c  mov     rax, cs:__security_cookie
0x14004e643  xor     rax, rsp
0x14004e646  mov     [rbp+0B0h+var_40], rax
0x14004e64a  mov     rsi, r9
0x14004e64d  mov     rbx, rdx
0x14004e650  mov     r15, rcx
0x14004e653  mov     [rsp+1B0h+var_148], r8
0x14004e658  xor     r13d, r13d
0x14004e65b  mov     al, [r9+8]
0x14004e65f  cmp     al, 63h ; 'c'
0x14004e661  jnz     short loc_14004E6A9
0x14004e663  lea     rax, [r8+80h]
0x14004e66a  cmp     rax, 0FFh
0x14004e670  ja      loc_14004E9CB
0x14004e676  mov     [r9+0Bh], r13b
0x14004e67a  movaps  xmm0, xmmword ptr [r9]
0x14004e67e  movaps  [rsp+1B0h+var_170], xmm0
0x14004e683  mov     ecx, [r9+10h]
0x14004e687  mov     [rsp+1B0h+var_160], ecx
0x14004e68b  mov     rcx, [rbp+0B0h+arg_20]
0x14004e692  mov     [rsp+1B0h+var_190], rcx
0x14004e697  lea     r9, [rsp+1B0h+var_170]
0x14004e69c  mov     rcx, r15
0x14004e69f  call    ??$_Fmt_write@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@DU?$_Basic_format_specs@D@0@V_Lazy_locale@0@@Z; std::_Fmt_write<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(std::back_insert_iterator<std::_Fmt_buffer<char>>,char,std::_Basic_format_specs<char>,std::_Lazy_locale)
0x14004e6a4  jmp     loc_14004E9A1
0x14004e6a9  mov     edi, 2
0x14004e6ae  cmp     [r9+0Ah], r13b
0x14004e6b2  jnz     short loc_14004E6B8
0x14004e6b4  mov     [r9+0Ah], dil
0x14004e6b8  cmp     al, 42h ; 'B'
0x14004e6ba  jz      short loc_14004E6E1
0x14004e6bc  cmp     al, 58h ; 'X'
0x14004e6be  jz      short loc_14004E6DA
0x14004e6c0  cmp     al, 62h ; 'b'
0x14004e6c2  jz      short loc_14004E6E1
0x14004e6c4  cmp     al, 6Fh ; 'o'
0x14004e6c6  jz      short loc_14004E6D3
0x14004e6c8  cmp     al, 78h ; 'x'
0x14004e6ca  jz      short loc_14004E6DA
0x14004e6cc  mov     eax, 0Ah
0x14004e6d1  jmp     short loc_14004E6E3
0x14004e6d3  mov     eax, 8
0x14004e6d8  jmp     short loc_14004E6E3
0x14004e6da  mov     eax, 10h
0x14004e6df  jmp     short loc_14004E6E3
0x14004e6e1  mov     eax, edi
0x14004e6e3  mov     dword ptr [rsp+1B0h+var_190], eax
0x14004e6e7  mov     r9, r8
0x14004e6ea  lea     r8, [rbp+0B0h+var_4F]
0x14004e6ee  lea     rdx, [rbp+0B0h+var_90]
0x14004e6f2  lea     rcx, [rsp+1B0h+var_170]
0x14004e6f7  call    ??$_Integer_to_chars@_J@std@@YA?AUto_chars_result@0@PEADQEAD_JH@Z; std::_Integer_to_chars<__int64>(char *,char * const,__int64,int)
0x14004e6fc  lea     rcx, [rbp+0B0h+var_90]
0x14004e700  mov     [rsp+1B0h+var_140], rcx
0x14004e705  mov     r12, qword ptr [rsp+1B0h+var_170]
0x14004e70a  mov     eax, r12d
0x14004e70d  sub     eax, ecx
0x14004e70f  mov     [rsp+1B0h+var_17C], eax
0x14004e713  mov     rdx, [rsp+1B0h+var_148]
0x14004e718  test    rdx, rdx
0x14004e71b  js      short loc_14004E72B
0x14004e71d  cmp     [rsi+0Ah], dil
0x14004e721  jz      short loc_14004E734
0x14004e723  inc     eax
0x14004e725  mov     [rsp+1B0h+var_17C], eax
0x14004e729  jmp     short loc_14004E734
0x14004e72b  lea     rcx, [rbp+0B0h+var_8F]
0x14004e72f  mov     [rsp+1B0h+var_140], rcx
0x14004e734  mov     r14d, 1
0x14004e73a  cmp     byte ptr [rsi+8], 58h ; 'X'
0x14004e73e  jnz     short loc_14004E764
0x14004e740  cmp     rcx, r12
0x14004e743  jz      short loc_14004E764
0x14004e745  mov     dl, [rcx]
0x14004e747  lea     eax, [rdx-61h]
0x14004e74a  cmp     al, 19h
0x14004e74c  ja      short loc_14004E753
0x14004e74e  sub     dl, 20h ; ' '
0x14004e751  mov     [rcx], dl
0x14004e753  add     rcx, r14
0x14004e756  cmp     rcx, r12
0x14004e759  jnz     short loc_14004E745
0x14004e75b  mov     eax, [rsp+1B0h+var_17C]
0x14004e75f  mov     rdx, [rsp+1B0h+var_148]
0x14004e764  mov     qword ptr [rbp+0B0h+var_130], r13
0x14004e768  mov     qword ptr [rbp+0B0h+var_130+8], r13
0x14004e76c  cmp     [rsi+0Bh], r13b
0x14004e770  jz      short loc_14004E7EF
0x14004e772  mov     cl, [rsi+8]
0x14004e775  cmp     cl, 42h ; 'B'
0x14004e778  jz      short loc_14004E7CE
0x14004e77a  cmp     cl, 58h ; 'X'
0x14004e77d  jz      short loc_14004E7C5
0x14004e77f  cmp     cl, 62h ; 'b'
0x14004e782  jz      short loc_14004E7BC
0x14004e784  cmp     cl, 6Fh ; 'o'
0x14004e787  jz      short loc_14004E797
0x14004e789  cmp     cl, 78h ; 'x'
0x14004e78c  jnz     short loc_14004E7AD
0x14004e78e  lea     rcx, a0x; "0x"
0x14004e795  jmp     short loc_14004E7D5
0x14004e797  test    rdx, rdx
0x14004e79a  jz      short loc_14004E7AD
0x14004e79c  lea     rcx, a0; "0"
0x14004e7a3  mov     qword ptr [rsp+1B0h+var_170+8], r14
0x14004e7a8  mov     edi, r14d
0x14004e7ab  jmp     short loc_14004E7DA
0x14004e7ad  mov     qword ptr [rsp+1B0h+var_170], r13
0x14004e7b2  mov     qword ptr [rsp+1B0h+var_170+8], r13
0x14004e7b7  mov     edi, r13d
0x14004e7ba  jmp     short loc_14004E7DF
0x14004e7bc  lea     rcx, a0b; "0b"
0x14004e7c3  jmp     short loc_14004E7D5
0x14004e7c5  lea     rcx, a0x_0; "0X"
0x14004e7cc  jmp     short loc_14004E7D5
0x14004e7ce  lea     rcx, a0b_0; "0B"
0x14004e7d5  mov     qword ptr [rsp+1B0h+var_170+8], rdi
0x14004e7da  mov     qword ptr [rsp+1B0h+var_170], rcx
0x14004e7df  movaps  xmm0, [rsp+1B0h+var_170]
0x14004e7e4  movdqa  [rbp+0B0h+var_130], xmm0
0x14004e7e9  add     eax, edi
0x14004e7eb  mov     [rsp+1B0h+var_17C], eax
0x14004e7ef  mov     [rsp+1B0h+var_150], r13d
0x14004e7f4  xorps   xmm0, xmm0
0x14004e7f7  movups  [rbp+0B0h+var_D0], xmm0
0x14004e7fb  mov     [rbp+0B0h+var_C0], r13
0x14004e7ff  mov     [rbp+0B0h+var_B8], 0Fh
0x14004e807  mov     byte ptr [rbp+0B0h+var_D0], r13b
0x14004e80b  cmp     [rsi+0Ch], r13b
0x14004e80f  jz      loc_14004E907
0x14004e815  mov     rax, [rbp+0B0h+arg_20]
0x14004e81c  test    rax, rax
0x14004e81f  jz      short loc_14004E838
0x14004e821  mov     rcx, [rax+8]
0x14004e825  mov     qword ptr [rsp+1B0h+var_170+8], rcx
0x14004e82a  mov     rax, [rcx]
0x14004e82d  mov     rax, [rax+8]
0x14004e831  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004e836  jmp     short loc_14004E846
0x14004e838  mov     cl, r14b
0x14004e83b  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x14004e841  mov     qword ptr [rsp+1B0h+var_170+8], rax
0x14004e846  lea     rcx, [rsp+1B0h+var_170]
0x14004e84b  call    ??$use_facet@V?$numpunct@D@std@@@std@@YAAEBV?$numpunct@D@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<char>>(std::locale const &)
0x14004e850  mov     r8, rax
0x14004e853  mov     rcx, [rax]
0x14004e856  mov     rax, [rcx+28h]
0x14004e85a  lea     rdx, [rbp+0B0h+var_B0]
0x14004e85e  mov     rcx, r8
0x14004e861  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004e866  lea     rdx, [rbp+0B0h+var_B0]
0x14004e86a  lea     rcx, [rbp+0B0h+var_D0]
0x14004e86e  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x14004e873  lea     rcx, [rbp+0B0h+var_B0]
0x14004e877  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14004e87c  nop
0x14004e87d  mov     rcx, qword ptr [rsp+1B0h+var_170+8]
0x14004e882  test    rcx, rcx
0x14004e885  jz      short loc_14004E8AC
0x14004e887  mov     rax, [rcx]
0x14004e88a  mov     rax, [rax+10h]
0x14004e88e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004e893  mov     r8, rax
0x14004e896  test    rax, rax
0x14004e899  jz      short loc_14004E8AC
0x14004e89b  mov     rcx, [rax]
0x14004e89e  mov     rax, [rcx]
0x14004e8a1  mov     edx, r14d
0x14004e8a4  mov     rcx, r8
0x14004e8a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004e8ac  lea     rax, [rbp+0B0h+var_D0]
0x14004e8b0  cmp     [rbp+0B0h+var_B8], 0Fh
0x14004e8b5  cmova   rax, qword ptr [rbp+0B0h+var_D0]
0x14004e8ba  mov     r10, [rbp+0B0h+var_C0]
0x14004e8be  mov     edx, r13d
0x14004e8c1  test    r10, r10
0x14004e8c4  jz      short loc_14004E8F9
0x14004e8c6  mov     r8, r12
0x14004e8c9  sub     r8, [rsp+1B0h+var_140]
0x14004e8ce  movsx   r9, byte ptr [rax]
0x14004e8d2  cmp     r8, r9
0x14004e8d5  jbe     short loc_14004E8F9
0x14004e8d7  lea     r11, [r10+rax]
0x14004e8db  movsx   rcx, r9b
0x14004e8df  sub     r8, rcx
0x14004e8e2  add     edx, r14d
0x14004e8e5  lea     rcx, [rax+1]
0x14004e8e9  cmp     rcx, r11
0x14004e8ec  cmovnz  rax, rcx
0x14004e8f0  movsx   r9, byte ptr [rax]
0x14004e8f4  cmp     r8, r9
0x14004e8f7  ja      short loc_14004E8DB
0x14004e8f9  mov     [rsp+1B0h+var_150], edx
0x14004e8fd  mov     eax, [rsp+1B0h+var_17C]
0x14004e901  add     eax, edx
0x14004e903  mov     [rsp+1B0h+var_17C], eax
0x14004e907  cmp     [rsi+0Dh], r13b
0x14004e90b  jz      short loc_14004E913
0x14004e90d  cmp     [rsi+9], r13b
0x14004e911  jz      short loc_14004E916
0x14004e913  mov     r14b, r13b
0x14004e916  mov     [rsp+1B0h+var_180], r14b
0x14004e91b  mov     [rbp+0B0h+var_120], r12
0x14004e91f  mov     [rbp+0B0h+var_118], rsi
0x14004e923  lea     rcx, [rsp+1B0h+var_148]
0x14004e928  mov     [rbp+0B0h+var_110], rcx
0x14004e92c  lea     rcx, [rbp+0B0h+var_130]
0x14004e930  mov     [rbp+0B0h+var_108], rcx
0x14004e934  lea     rcx, [rsp+1B0h+var_180]
0x14004e939  mov     [rbp+0B0h+var_100], rcx
0x14004e93d  lea     rcx, [rsp+1B0h+var_17C]
0x14004e942  mov     [rbp+0B0h+var_F8], rcx
0x14004e946  lea     rcx, [rsp+1B0h+var_150]
0x14004e94b  mov     [rbp+0B0h+var_F0], rcx
0x14004e94f  lea     rcx, [rsp+1B0h+var_140]
0x14004e954  mov     [rbp+0B0h+var_E8], rcx
0x14004e958  lea     rcx, [rbp+0B0h+var_D0]
0x14004e95c  mov     [rbp+0B0h+var_E0], rcx
0x14004e960  lea     rcx, [rbp+0B0h+arg_20]
0x14004e967  mov     [rbp+0B0h+var_D8], rcx
0x14004e96b  lea     rcx, [rbp+0B0h+var_120]
0x14004e96f  test    r14b, r14b
0x14004e972  jz      short loc_14004E981
0x14004e974  mov     r8, rbx
0x14004e977  mov     rdx, r15
0x14004e97a  call    ??R_lambda_1_@?1???$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@_J@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@1@V21@_JU?$_Basic_format_specs@D@1@V_Lazy_locale@1@@Z@QEBA@0@Z; `std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,__int64>(std::back_insert_iterator<std::_Fmt_buffer<char>>,__int64,std::_Basic_format_specs<char>,std::_Lazy_locale)'::`2'::_lambda_1_::operator()(std::back_insert_iterator<std::_Fmt_buffer<char>>)
0x14004e97f  jmp     short loc_14004E998
0x14004e981  mov     [rsp+1B0h+var_188], rcx
0x14004e986  mov     r9, rsi
0x14004e989  mov     r8d, eax
0x14004e98c  mov     rdx, rbx
0x14004e98f  mov     rcx, r15
0x14004e992  call    ??$_Write_aligned@V?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@U?$_Basic_format_specs@D@2@AEAV_lambda_1_@?1???$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@_J@2@YA?AV12@V12@_JU32@V_Lazy_locale@2@@Z@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@HAEBU?$_Basic_format_specs@D@0@W4_Fmt_align@0@AEAV_lambda_1_@?1???$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@_J@0@YA?AV10@0_JU20@V_Lazy_locale@0@@Z@@Z; std::_Write_aligned<std::back_insert_iterator<std::_Fmt_buffer<char>>,std::_Basic_format_specs<char>,`std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,__int64>(std::back_insert_iterator<std::_Fmt_buffer<char>>,__int64,std::_Basic_format_specs<char>,std::_Lazy_locale)'::`2'::_lambda_1_ &>(std::back_insert_iterator<std::_Fmt_buffer<char>>,int,std::_Basic_format_specs<char> const &,std::_Fmt_align,`std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,__int64>(std::back_insert_iterator<std::_Fmt_buffer<char>>,__int64,std::_Basic_format_specs<char>,std::_Lazy_locale)'::`2'::_lambda_1_ &)
0x14004e997  nop
0x14004e998  lea     rcx, [rbp+0B0h+var_D0]
0x14004e99c  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14004e9a1  mov     rax, r15
0x14004e9a4  mov     rcx, [rbp+0B0h+var_40]
0x14004e9a8  xor     rcx, rsp; StackCookie
0x14004e9ab  call    __security_check_cookie
0x14004e9b0  mov     rbx, [rsp+1B0h+arg_8]
0x14004e9b8  add     rsp, 180h
0x14004e9bf  pop     r15
0x14004e9c1  pop     r14
0x14004e9c3  pop     r13
0x14004e9c5  pop     r12
0x14004e9c7  pop     rdi
0x14004e9c8  pop     rsi
0x14004e9c9  pop     rbp
0x14004e9ca  retn
0x14004e9cb  lea     rcx, aIntegralCannot; "integral cannot be stored in char"
0x14004e9d2  call    ?_Throw_format_error@std@@YAXPEBD@Z; std::_Throw_format_error(char const *)
```
