# std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,unsigned __int64>(std::back_insert_iterator<std::_Fmt_buffer<char>>,unsigned __int64,std::_Basic_format_specs<char>,std::_Lazy_locale)

- ea: `0x180028c74`
- end: `0x180029011`
- name: `??$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@_K@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@_KU?$_Basic_format_specs@D@0@V_Lazy_locale@0@@Z`
- size: `925`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x180026ec8`

## callees

- `0x180004180`
- `0x180023e98`
- `0x180027998`
- `0x180028c74`
- `0x18002a6a0`
- `0x18002abe4`
- `0x18002ae0c`
- `0x18002b9a4`
- `0x18002dd84`
- `0x18002fbd0`
- `0x180032010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x180028e74`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x180028e74`

## pseudocode

```c
__int64 __fastcall std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,unsigned __int64>(
        __int64 a1,
        __int64 a2,
        unsigned __int64 a3,
        __int128 *a4,
        __int64 a5)
{
  char v8; // al
  int v9; // edi
  int v10; // eax
  _BYTE *v11; // r12
  unsigned int v12; // eax
  char v13; // r14
  _BYTE *v14; // rcx
  char v15; // cl
  const char *v16; // rcx
  __int64 v17; // rax
  void (__fastcall ***v18)(_QWORD, __int64); // rax
  char *v19; // rax
  int v20; // edx
  unsigned __int64 v21; // r8
  unsigned __int64 v22; // r9
  char *v23; // r11
  int v25; // [rsp+20h] [rbp-E0h]
  char v26; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v27; // [rsp+34h] [rbp-CCh] BYREF
  __int128 v28; // [rsp+40h] [rbp-C0h] BYREF
  int v29; // [rsp+50h] [rbp-B0h]
  int v30; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int64 v31; // [rsp+68h] [rbp-98h] BYREF
  _BYTE *v32; // [rsp+70h] [rbp-90h] BYREF
  __int128 v33; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v34[10]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v35; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v36; // [rsp+F0h] [rbp-10h]
  unsigned __int64 v37; // [rsp+F8h] [rbp-8h]
  _BYTE v38[32]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v39[65]; // [rsp+120h] [rbp+20h] BYREF
  char v40[15]; // [rsp+161h] [rbp+61h] BYREF

  v31 = a3;
  v8 = *((_BYTE *)a4 + 8);
  if ( v8 == 99 )
  {
    if ( a3 > 0x7F )
      std::_Throw_format_error("integral cannot be stored in char");
    *((_BYTE *)a4 + 11) = 0;
    v28 = *a4;
    v29 = *((_DWORD *)a4 + 4);
    std::_Fmt_write<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(a1, a2, a3, (unsigned int)&v28, a5);
    return a1;
  }
  v9 = 2;
  if ( !*((_BYTE *)a4 + 10) )
    *((_BYTE *)a4 + 10) = 2;
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
  v25 = v10;
  v11 = *(_BYTE **)std::to_chars(&v28, v39, v40, a3);
  v32 = v39;
  v12 = (_DWORD)v11 - (unsigned int)v39;
  v27 = v12;
  if ( *((_BYTE *)a4 + 10) != 2 )
    v27 = ++v12;
  v13 = 1;
  if ( *((_BYTE *)a4 + 8) == 88 )
  {
    v14 = v39;
    if ( v39 != v11 )
    {
      do
      {
        if ( (unsigned __int8)(*v14 - 97) <= 0x19u )
          *v14 -= 32;
        ++v14;
      }
      while ( v14 != v11 );
      v12 = v27;
    }
  }
  v33 = 0u;
  if ( !*((_BYTE *)a4 + 11) )
    goto LABEL_39;
  v15 = *((_BYTE *)a4 + 8);
  switch ( v15 )
  {
    case 'B':
      v16 = "0B";
      goto LABEL_36;
    case 'X':
      v16 = "0X";
      goto LABEL_36;
    case 'b':
      v16 = "0b";
      goto LABEL_36;
    case 'o':
      if ( v31 )
      {
        v16 = "0";
        *((_QWORD *)&v28 + 1) = 1;
        v9 = 1;
LABEL_37:
        *(_QWORD *)&v28 = v16;
        goto LABEL_38;
      }
      break;
    case 'x':
      v16 = "0x";
LABEL_36:
      *((_QWORD *)&v28 + 1) = 2;
      goto LABEL_37;
  }
  v28 = 0u;
  v9 = 0;
LABEL_38:
  v33 = v28;
  v12 += v9;
  v27 = v12;
LABEL_39:
  v30 = 0;
  v35 = 0;
  v36 = 0;
  v37 = 15;
  LOBYTE(v35) = 0;
  if ( *((_BYTE *)a4 + 12) )
  {
    if ( a5 )
    {
      *((_QWORD *)&v28 + 1) = *(_QWORD *)(a5 + 8);
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v28 + 1) + 8LL))(*((_QWORD *)&v28 + 1));
    }
    else
    {
      *((_QWORD *)&v28 + 1) = std::locale::_Init(1);
    }
    v17 = std::use_facet<std::numpunct<char>>(&v28);
    (*(void (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v17 + 40LL))(v17, v38);
    std::string::operator=(&v35, v38);
    std::string::~string(v38);
    if ( *((_QWORD *)&v28 + 1) )
    {
      v18 = (void (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)&v28 + 1) + 16LL))(*((_QWORD *)&v28 + 1));
      if ( v18 )
        (**v18)(v18, 1);
    }
    v19 = (char *)&v35;
    if ( v37 > 0xF )
      v19 = (char *)v35;
    v20 = 0;
    if ( v36 )
    {
      v21 = v11 - v32;
      v22 = *v19;
      if ( v11 - v32 > v22 )
      {
        v23 = &v19[v36];
        do
        {
          v21 -= (char)v22;
          ++v20;
          if ( v19 + 1 != v23 )
            ++v19;
          v22 = *v19;
        }
        while ( v21 > v22 );
      }
    }
    v30 = v20;
    v12 = v20 + v27;
    v27 += v20;
  }
  if ( !*((_BYTE *)a4 + 13) || *((_BYTE *)a4 + 9) )
    v13 = 0;
  v26 = v13;
  v34[0] = v11;
  v34[1] = a4;
  v34[2] = &v31;
  v34[3] = &v33;
  v34[4] = &v26;
  v34[5] = &v27;
  v34[6] = &v30;
  v34[7] = &v32;
  v34[8] = &v35;
  v34[9] = &a5;
  if ( v13 )
    `std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,unsigned __int64>'::`2'::_lambda_1_::operator()(
      v34,
      a1,
      a2);
  else
    ____Write_aligned_V__back_insert_iterator_V___Fmt_buffer_D_std___std__U___Basic_format_specs_D_2_AEAV_lambda_1___1_____Write_integral_DV__back_insert_iterator_V___Fmt_buffer_D_std___std__I_2_YA_AV12_V12_IU32_V_Lazy_locale_2__Z__std__YA_AV__back_insert_iterator_V___Fmt_buffer_D_std___0_V10_HAEBU___Basic_format_specs_D_0_W4_Fmt_align_0_AEAV_lambda_1___1_____Write_integral_DV__back_insert_iterator_V___Fmt_buffer_D_std___std__I_0_YA_AV10_0IU20_V_Lazy_locale_0__Z__Z(
      a1,
      a2,
      v12,
      (_DWORD)a4,
      v25,
      (__int64)v34);
  std::string::~string(&v35);
  return a1;
}

```

## disassembly

```asm
0x180028c74  mov     [rsp-8+arg_8], rbx
0x180028c79  push    rbp
0x180028c7a  push    rsi
0x180028c7b  push    rdi
0x180028c7c  push    r12
0x180028c7e  push    r13
0x180028c80  push    r14
0x180028c82  push    r15
0x180028c84  lea     rbp, [rsp-80h]
0x180028c89  sub     rsp, 180h
0x180028c90  mov     rax, cs:__security_cookie
0x180028c97  xor     rax, rsp
0x180028c9a  mov     [rbp+0B0h+var_40], rax
0x180028c9e  mov     rsi, r9
0x180028ca1  mov     rbx, rdx
0x180028ca4  mov     r15, rcx
0x180028ca7  mov     [rsp+1B0h+var_148], r8
0x180028cac  xor     r13d, r13d
0x180028caf  mov     al, [r9+8]
0x180028cb3  cmp     al, 63h ; 'c'
0x180028cb5  jnz     short loc_180028CF4
0x180028cb7  cmp     r8, 7Fh
0x180028cbb  ja      loc_180029004
0x180028cc1  mov     [r9+0Bh], r13b
0x180028cc5  movaps  xmm0, xmmword ptr [r9]
0x180028cc9  movaps  [rsp+1B0h+var_170], xmm0
0x180028cce  mov     ecx, [r9+10h]
0x180028cd2  mov     [rsp+1B0h+var_160], ecx
0x180028cd6  mov     rcx, [rbp+0B0h+arg_20]
0x180028cdd  mov     [rsp+1B0h+var_190], rcx
0x180028ce2  lea     r9, [rsp+1B0h+var_170]
0x180028ce7  mov     rcx, r15
0x180028cea  call    ??$_Fmt_write@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@DU?$_Basic_format_specs@D@0@V_Lazy_locale@0@@Z; std::_Fmt_write<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(std::back_insert_iterator<std::_Fmt_buffer<char>>,char,std::_Basic_format_specs<char>,std::_Lazy_locale)
0x180028cef  jmp     loc_180028FDA
0x180028cf4  mov     edi, 2
0x180028cf9  cmp     [r9+0Ah], r13b
0x180028cfd  jnz     short loc_180028D03
0x180028cff  mov     [r9+0Ah], dil
0x180028d03  cmp     al, 42h ; 'B'
0x180028d05  jz      short loc_180028D2C
0x180028d07  cmp     al, 58h ; 'X'
0x180028d09  jz      short loc_180028D25
0x180028d0b  cmp     al, 62h ; 'b'
0x180028d0d  jz      short loc_180028D2C
0x180028d0f  cmp     al, 6Fh ; 'o'
0x180028d11  jz      short loc_180028D1E
0x180028d13  cmp     al, 78h ; 'x'
0x180028d15  jz      short loc_180028D25
0x180028d17  mov     eax, 0Ah
0x180028d1c  jmp     short loc_180028D2E
0x180028d1e  mov     eax, 8
0x180028d23  jmp     short loc_180028D2E
0x180028d25  mov     eax, 10h
0x180028d2a  jmp     short loc_180028D2E
0x180028d2c  mov     eax, edi
0x180028d2e  mov     dword ptr [rsp+1B0h+var_190], eax
0x180028d32  mov     r9, r8
0x180028d35  lea     r8, [rbp+0B0h+var_4F]
0x180028d39  lea     rdx, [rbp+0B0h+var_90]
0x180028d3d  lea     rcx, [rsp+1B0h+var_170]
0x180028d42  call    ?to_chars@std@@YA?AUto_chars_result@1@QEAD0_KH@Z; std::to_chars(char * const,char * const,unsigned __int64,int)
0x180028d47  mov     r12, [rax]
0x180028d4a  lea     rcx, [rbp+0B0h+var_90]
0x180028d4e  mov     [rsp+1B0h+var_140], rcx
0x180028d53  mov     eax, r12d
0x180028d56  sub     eax, ecx
0x180028d58  mov     [rsp+1B0h+var_17C], eax
0x180028d5c  cmp     [rsi+0Ah], dil
0x180028d60  jz      short loc_180028D68
0x180028d62  inc     eax
0x180028d64  mov     [rsp+1B0h+var_17C], eax
0x180028d68  mov     r14d, 1
0x180028d6e  cmp     byte ptr [rsi+8], 58h ; 'X'
0x180028d72  jnz     short loc_180028D9B
0x180028d74  lea     rcx, [rbp+0B0h+var_90]
0x180028d78  lea     rdx, [rbp+0B0h+var_90]
0x180028d7c  cmp     rdx, r12
0x180028d7f  jz      short loc_180028D9B
0x180028d81  mov     dl, [rcx]
0x180028d83  lea     eax, [rdx-61h]
0x180028d86  cmp     al, 19h
0x180028d88  ja      short loc_180028D8F
0x180028d8a  sub     dl, 20h ; ' '
0x180028d8d  mov     [rcx], dl
0x180028d8f  add     rcx, r14
0x180028d92  cmp     rcx, r12
0x180028d95  jnz     short loc_180028D81
0x180028d97  mov     eax, [rsp+1B0h+var_17C]
0x180028d9b  mov     qword ptr [rbp+0B0h+var_130], r13
0x180028d9f  mov     qword ptr [rbp+0B0h+var_130+8], r13
0x180028da3  cmp     [rsi+0Bh], r13b
0x180028da7  jz      short loc_180028E28
0x180028da9  mov     cl, [rsi+8]
0x180028dac  cmp     cl, 42h ; 'B'
0x180028daf  jz      short loc_180028E07
0x180028db1  cmp     cl, 58h ; 'X'
0x180028db4  jz      short loc_180028DFE
0x180028db6  cmp     cl, 62h ; 'b'
0x180028db9  jz      short loc_180028DF5
0x180028dbb  cmp     cl, 6Fh ; 'o'
0x180028dbe  jz      short loc_180028DCE
0x180028dc0  cmp     cl, 78h ; 'x'
0x180028dc3  jnz     short loc_180028DE6
0x180028dc5  lea     rcx, a0x; "0x"
0x180028dcc  jmp     short loc_180028E0E
0x180028dce  cmp     [rsp+1B0h+var_148], r13
0x180028dd3  jz      short loc_180028DE6
0x180028dd5  lea     rcx, a0; "0"
0x180028ddc  mov     qword ptr [rsp+1B0h+var_170+8], r14
0x180028de1  mov     edi, r14d
0x180028de4  jmp     short loc_180028E13
0x180028de6  mov     qword ptr [rsp+1B0h+var_170], r13
0x180028deb  mov     qword ptr [rsp+1B0h+var_170+8], r13
0x180028df0  mov     edi, r13d
0x180028df3  jmp     short loc_180028E18
0x180028df5  lea     rcx, a0b; "0b"
0x180028dfc  jmp     short loc_180028E0E
0x180028dfe  lea     rcx, a0x_0; "0X"
0x180028e05  jmp     short loc_180028E0E
0x180028e07  lea     rcx, a0b_0; "0B"
0x180028e0e  mov     qword ptr [rsp+1B0h+var_170+8], rdi
0x180028e13  mov     qword ptr [rsp+1B0h+var_170], rcx
0x180028e18  movaps  xmm0, [rsp+1B0h+var_170]
0x180028e1d  movdqa  [rbp+0B0h+var_130], xmm0
0x180028e22  add     eax, edi
0x180028e24  mov     [rsp+1B0h+var_17C], eax
0x180028e28  mov     [rsp+1B0h+var_150], r13d
0x180028e2d  xorps   xmm0, xmm0
0x180028e30  movups  [rbp+0B0h+var_D0], xmm0
0x180028e34  mov     [rbp+0B0h+var_C0], r13
0x180028e38  mov     [rbp+0B0h+var_B8], 0Fh
0x180028e40  mov     byte ptr [rbp+0B0h+var_D0], r13b
0x180028e44  cmp     [rsi+0Ch], r13b
0x180028e48  jz      loc_180028F40
0x180028e4e  mov     rax, [rbp+0B0h+arg_20]
0x180028e55  test    rax, rax
0x180028e58  jz      short loc_180028E71
0x180028e5a  mov     rcx, [rax+8]
0x180028e5e  mov     qword ptr [rsp+1B0h+var_170+8], rcx
0x180028e63  mov     rax, [rcx]
0x180028e66  mov     rax, [rax+8]
0x180028e6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028e6f  jmp     short loc_180028E7F
0x180028e71  mov     cl, r14b
0x180028e74  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x180028e7a  mov     qword ptr [rsp+1B0h+var_170+8], rax
0x180028e7f  lea     rcx, [rsp+1B0h+var_170]
0x180028e84  call    ??$use_facet@V?$numpunct@D@std@@@std@@YAAEBV?$numpunct@D@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<char>>(std::locale const &)
0x180028e89  mov     r8, rax
0x180028e8c  mov     rcx, [rax]
0x180028e8f  mov     rax, [rcx+28h]
0x180028e93  lea     rdx, [rbp+0B0h+var_B0]
0x180028e97  mov     rcx, r8
0x180028e9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028e9f  lea     rdx, [rbp+0B0h+var_B0]
0x180028ea3  lea     rcx, [rbp+0B0h+var_D0]
0x180028ea7  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x180028eac  lea     rcx, [rbp+0B0h+var_B0]
0x180028eb0  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180028eb5  nop
0x180028eb6  mov     rcx, qword ptr [rsp+1B0h+var_170+8]
0x180028ebb  test    rcx, rcx
0x180028ebe  jz      short loc_180028EE5
0x180028ec0  mov     rax, [rcx]
0x180028ec3  mov     rax, [rax+10h]
0x180028ec7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028ecc  mov     r8, rax
0x180028ecf  test    rax, rax
0x180028ed2  jz      short loc_180028EE5
0x180028ed4  mov     rcx, [rax]
0x180028ed7  mov     rax, [rcx]
0x180028eda  mov     edx, r14d
0x180028edd  mov     rcx, r8
0x180028ee0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028ee5  lea     rax, [rbp+0B0h+var_D0]
0x180028ee9  cmp     [rbp+0B0h+var_B8], 0Fh
0x180028eee  cmova   rax, qword ptr [rbp+0B0h+var_D0]
0x180028ef3  mov     r10, [rbp+0B0h+var_C0]
0x180028ef7  mov     edx, r13d
0x180028efa  test    r10, r10
0x180028efd  jz      short loc_180028F32
0x180028eff  mov     r8, r12
0x180028f02  sub     r8, [rsp+1B0h+var_140]
0x180028f07  movsx   r9, byte ptr [rax]
0x180028f0b  cmp     r8, r9
0x180028f0e  jbe     short loc_180028F32
0x180028f10  lea     r11, [r10+rax]
0x180028f14  movsx   rcx, r9b
0x180028f18  sub     r8, rcx
0x180028f1b  add     edx, r14d
0x180028f1e  lea     rcx, [rax+1]
0x180028f22  cmp     rcx, r11
0x180028f25  cmovnz  rax, rcx
0x180028f29  movsx   r9, byte ptr [rax]
0x180028f2d  cmp     r8, r9
0x180028f30  ja      short loc_180028F14
0x180028f32  mov     [rsp+1B0h+var_150], edx
0x180028f36  mov     eax, [rsp+1B0h+var_17C]
0x180028f3a  add     eax, edx
0x180028f3c  mov     [rsp+1B0h+var_17C], eax
0x180028f40  cmp     [rsi+0Dh], r13b
0x180028f44  jz      short loc_180028F4C
0x180028f46  cmp     [rsi+9], r13b
0x180028f4a  jz      short loc_180028F4F
0x180028f4c  mov     r14b, r13b
0x180028f4f  mov     [rsp+1B0h+var_180], r14b
0x180028f54  mov     [rbp+0B0h+var_120], r12
0x180028f58  mov     [rbp+0B0h+var_118], rsi
0x180028f5c  lea     rcx, [rsp+1B0h+var_148]
0x180028f61  mov     [rbp+0B0h+var_110], rcx
0x180028f65  lea     rcx, [rbp+0B0h+var_130]
0x180028f69  mov     [rbp+0B0h+var_108], rcx
0x180028f6d  lea     rcx, [rsp+1B0h+var_180]
0x180028f72  mov     [rbp+0B0h+var_100], rcx
0x180028f76  lea     rcx, [rsp+1B0h+var_17C]
0x180028f7b  mov     [rbp+0B0h+var_F8], rcx
0x180028f7f  lea     rcx, [rsp+1B0h+var_150]
0x180028f84  mov     [rbp+0B0h+var_F0], rcx
0x180028f88  lea     rcx, [rsp+1B0h+var_140]
0x180028f8d  mov     [rbp+0B0h+var_E8], rcx
0x180028f91  lea     rcx, [rbp+0B0h+var_D0]
0x180028f95  mov     [rbp+0B0h+var_E0], rcx
0x180028f99  lea     rcx, [rbp+0B0h+arg_20]
0x180028fa0  mov     [rbp+0B0h+var_D8], rcx
0x180028fa4  lea     rcx, [rbp+0B0h+var_120]
0x180028fa8  test    r14b, r14b
0x180028fab  jz      short loc_180028FBA
0x180028fad  mov     r8, rbx
0x180028fb0  mov     rdx, r15
0x180028fb3  call    ??R_lambda_1_@?1???$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@_K@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@1@V21@_KU?$_Basic_format_specs@D@1@V_Lazy_locale@1@@Z@QEBA@0@Z; `std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,unsigned __int64>(std::back_insert_iterator<std::_Fmt_buffer<char>>,unsigned __int64,std::_Basic_format_specs<char>,std::_Lazy_locale)'::`2'::_lambda_1_::operator()(std::back_insert_iterator<std::_Fmt_buffer<char>>)
0x180028fb8  jmp     short loc_180028FD1
0x180028fba  mov     [rsp+1B0h+var_188], rcx
0x180028fbf  mov     r9, rsi
0x180028fc2  mov     r8d, eax
0x180028fc5  mov     rdx, rbx
0x180028fc8  mov     rcx, r15
0x180028fcb  call    ??$_Write_aligned@V?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@U?$_Basic_format_specs@D@2@AEAV_lambda_1_@?1???$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@I@2@YA?AV12@V12@IU32@V_Lazy_locale@2@@Z@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@HAEBU?$_Basic_format_specs@D@0@W4_Fmt_align@0@AEAV_lambda_1_@?1???$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@I@0@YA?AV10@0IU20@V_Lazy_locale@0@@Z@@Z; std::_Write_aligned<std::back_insert_iterator<std::_Fmt_buffer<char>>,std::_Basic_format_specs<char>,`std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,uint>(std::back_insert_iterator<std::_Fmt_buffer<char>>,uint,std::_Basic_format_specs<char>,std::_Lazy_locale)'::`2'::_lambda_1_ &>(std::back_insert_iterator<std::_Fmt_buffer<char>>,int,std::_Basic_format_specs<char> const &,std::_Fmt_align,`std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,uint>(std::back_insert_iterator<std::_Fmt_buffer<char>>,uint,std::_Basic_format_specs<char>,std::_Lazy_locale)'::`2'::_lambda_1_ &)
0x180028fd0  nop
0x180028fd1  lea     rcx, [rbp+0B0h+var_D0]
0x180028fd5  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180028fda  mov     rax, r15
0x180028fdd  mov     rcx, [rbp+0B0h+var_40]
0x180028fe1  xor     rcx, rsp; StackCookie
0x180028fe4  call    __security_check_cookie
0x180028fe9  mov     rbx, [rsp+1B0h+arg_8]
0x180028ff1  add     rsp, 180h
0x180028ff8  pop     r15
0x180028ffa  pop     r14
0x180028ffc  pop     r13
0x180028ffe  pop     r12
0x180029000  pop     rdi
0x180029001  pop     rsi
0x180029002  pop     rbp
0x180029003  retn
0x180029004  lea     rcx, aIntegralCannot; "integral cannot be stored in char"
0x18002900b  call    ?_Throw_format_error@std@@YAXPEBD@Z; std::_Throw_format_error(char const *)
```
