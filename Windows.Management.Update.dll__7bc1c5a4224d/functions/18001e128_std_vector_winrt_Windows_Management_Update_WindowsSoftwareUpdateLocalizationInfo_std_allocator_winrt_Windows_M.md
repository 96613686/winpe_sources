# std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo,std::allocator<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>>::_Emplace_reallocate<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo const &>(winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo * const,winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo const &)

- ea: `0x18001e128`
- end: `0x18001e357`
- name: `??$_Emplace_reallocate@AEBUWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@@?$vector@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@V?$allocator@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@@std@@@std@@AEAAPEAUWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@QEAU23456@AEBU23456@@Z`
- size: `559`
- prototype: `_QWORD *__fastcall(char **, char *, __int64 *)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18001e940`
- `0x1800200cc`

## callees

- `0x180002cc0`
- `0x180002cfc`
- `0x180016fe4`
- `0x180017bac`
- `0x18001c7f4`
- `0x18001e128`
- `0x18001e808`
- `0x18001fadc`
- `0x18002a010`

## pseudocode

```c
_QWORD *__fastcall std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>::_Emplace_reallocate<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo const &>(
        char **a1,
        char *a2,
        __int64 *a3)
{
  char *v3; // r15
  __int64 v4; // rbp
  __int64 v7; // rax
  _QWORD *v9; // r8
  unsigned __int64 v10; // rcx
  size_t v11; // rcx
  __int64 v12; // r13
  unsigned __int64 v13; // rdx
  _QWORD *v14; // rsi
  _QWORD *v15; // rax
  __int64 v16; // rcx
  __int64 v17; // r14
  _QWORD *v18; // r15
  char *v19; // rdx
  char *v20; // rcx
  __int64 v21; // rax
  __int64 v22; // r14
  _QWORD *v23; // rdx
  __int64 v24; // rax
  _QWORD *v25; // rcx
  __int64 v26; // rax
  char *v27; // rdi
  char *v28; // rbp
  char *v29; // rcx
  unsigned __int64 v30; // rdx
  char *v31; // rax
  _QWORD v33[3]; // [rsp+20h] [rbp-78h] BYREF
  _QWORD *v34; // [rsp+38h] [rbp-60h]
  _QWORD *v35; // [rsp+40h] [rbp-58h]
  __int64 v36; // [rsp+A0h] [rbp+8h]

  v3 = *a1;
  v4 = 0x1FFFFFFFFFFFFFFFLL;
  v7 = (a1[1] - *a1) >> 3;
  if ( v7 == 0x1FFFFFFFFFFFFFFFLL )
    std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdate>::_Xlength();
  v9 = (_QWORD *)(v7 + 1);
  v36 = v7 + 1;
  v10 = (a1[2] - v3) >> 3;
  if ( v10 <= 0x1FFFFFFFFFFFFFFFLL - (v10 >> 1) )
  {
    v13 = v7 + 1;
    if ( (v10 >> 1) + v10 >= (unsigned __int64)v9 )
      v13 = (v10 >> 1) + v10;
    if ( v13 > 0x1FFFFFFFFFFFFFFFLL )
      __scrt_throw_std_bad_array_new_length();
    v11 = 8 * v13;
    v4 = v13;
    v12 = v13;
    if ( !(8 * v13) )
    {
      v14 = 0;
      goto LABEL_13;
    }
    if ( v11 < 0x1000 )
    {
      v15 = operator new(v11);
      goto LABEL_12;
    }
  }
  else
  {
    v11 = -8;
    v12 = 0x1FFFFFFFFFFFFFFFLL;
  }
  v15 = (_QWORD *)std::_Allocate_manually_vector_aligned<std::_Default_allocate_traits>(v11);
LABEL_12:
  v14 = v15;
LABEL_13:
  v16 = *a3;
  v33[0] = a1;
  v17 = (a2 - v3) >> 3;
  v33[2] = v4;
  v18 = &v14[v17];
  *v18 = v16;
  v35 = v18 + 1;
  if ( v16 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 8LL))(v16);
  v19 = a1[1];
  v20 = *a1;
  v34 = &v14[v17];
  if ( a2 == v19 )
  {
    v9 = v14;
    while ( v20 != v19 )
    {
      v21 = *(_QWORD *)v20;
      *(_QWORD *)v20 = 0;
      v20 += 8;
      *v9++ = v21;
    }
    v22 = v17;
  }
  else
  {
    v23 = v14;
    while ( v20 != a2 )
    {
      v24 = *(_QWORD *)v20;
      *(_QWORD *)v20 = 0;
      v20 += 8;
      *v23++ = v24;
    }
    v19 = a1[1];
    v22 = v17;
    v34 = v14;
    v25 = &v14[v22 + 1];
    while ( a2 != v19 )
    {
      v26 = *(_QWORD *)a2;
      *(_QWORD *)a2 = 0;
      a2 += 8;
      *v25++ = v26;
    }
  }
  v27 = *a1;
  v33[1] = 0;
  if ( v27 )
  {
    v28 = a1[1];
    while ( v27 != v28 )
    {
      if ( *(_QWORD *)v27 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v27);
      v27 += 8;
    }
    v29 = *a1;
    v30 = 8 * ((a1[2] - *a1) >> 3);
    if ( v30 < 0x1000 )
    {
      v31 = *a1;
    }
    else
    {
      v31 = (char *)*((_QWORD *)v29 - 1);
      if ( (unsigned __int64)(v29 - v31 - 8) > 0x1F )
        __fastfail(5u);
      v30 += 39LL;
    }
    operator delete(v31, v30);
  }
  *a1 = (char *)v14;
  a1[1] = (char *)&v14[v36];
  a1[2] = (char *)&v14[v12];
  std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>::_Reallocation_guard::~_Reallocation_guard(
    v33,
    v19,
    v9);
  return &v14[v22];
}

```

## disassembly

```asm
0x18001e128  push    rbx
0x18001e12a  push    rbp
0x18001e12b  push    rsi
0x18001e12c  push    rdi
0x18001e12d  push    r12
0x18001e12f  push    r13
0x18001e131  push    r14
0x18001e133  push    r15
0x18001e135  sub     rsp, 58h
0x18001e139  mov     r15, [rcx]
0x18001e13c  mov     rbp, 1FFFFFFFFFFFFFFFh
0x18001e146  mov     rax, [rcx+8]
0x18001e14a  mov     r12, r8
0x18001e14d  sub     rax, r15
0x18001e150  mov     rdi, rdx
0x18001e153  sar     rax, 3
0x18001e157  mov     rbx, rcx
0x18001e15a  cmp     rax, rbp
0x18001e15d  jz      loc_18001E351
0x18001e163  mov     rcx, [rcx+10h]
0x18001e167  lea     r8, [rax+1]
0x18001e16b  sub     rcx, r15
0x18001e16e  mov     [rsp+98h+arg_0], r8
0x18001e176  sar     rcx, 3
0x18001e17a  mov     rax, rbp
0x18001e17d  mov     rdx, rcx
0x18001e180  shr     rdx, 1
0x18001e183  sub     rax, rdx
0x18001e186  cmp     rcx, rax
0x18001e189  jbe     short loc_18001E197
0x18001e18b  mov     rcx, 0FFFFFFFFFFFFFFF8h
0x18001e192  mov     r13, rcx
0x18001e195  jmp     short loc_18001E1CE
0x18001e197  lea     rax, [rdx+rcx]
0x18001e19b  mov     rdx, r8
0x18001e19e  cmp     rax, r8
0x18001e1a1  cmovnb  rdx, rax
0x18001e1a5  cmp     rdx, rbp
0x18001e1a8  ja      loc_18001E34B
0x18001e1ae  lea     rcx, ds:0[rdx*8]; Size
0x18001e1b6  mov     rbp, rdx
0x18001e1b9  mov     r13, rcx
0x18001e1bc  test    rcx, rcx
0x18001e1bf  jnz     short loc_18001E1C5
0x18001e1c1  xor     esi, esi
0x18001e1c3  jmp     short loc_18001E1DD
0x18001e1c5  cmp     rcx, 1000h
0x18001e1cc  jb      short loc_18001E1D5
0x18001e1ce  call    ??$_Allocate_manually_vector_aligned@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate_manually_vector_aligned<std::_Default_allocate_traits>(unsigned __int64)
0x18001e1d3  jmp     short loc_18001E1DA
0x18001e1d5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001e1da  mov     rsi, rax
0x18001e1dd  mov     rcx, [r12]
0x18001e1e1  mov     r14, rdi
0x18001e1e4  sub     r14, r15
0x18001e1e7  mov     [rsp+98h+var_78], rbx
0x18001e1ec  sar     r14, 3
0x18001e1f0  mov     [rsp+98h+var_68], rbp
0x18001e1f5  lea     r15, [rsi+r14*8]
0x18001e1f9  mov     [r15], rcx
0x18001e1fc  lea     rax, [r15+8]
0x18001e200  mov     [rsp+98h+var_58], rax
0x18001e205  test    rcx, rcx
0x18001e208  jz      short loc_18001E216
0x18001e20a  mov     rax, [rcx]
0x18001e20d  mov     rax, [rax+8]
0x18001e211  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e216  mov     rdx, [rbx+8]
0x18001e21a  mov     rcx, [rbx]
0x18001e21d  mov     [rsp+98h+var_60], r15
0x18001e222  cmp     rdi, rdx
0x18001e225  jnz     short loc_18001E24C
0x18001e227  mov     r8, rsi
0x18001e22a  jmp     short loc_18001E241
0x18001e22c  mov     rax, [rcx]
0x18001e22f  mov     qword ptr [rcx], 0
0x18001e236  add     rcx, 8
0x18001e23a  mov     [r8], rax
0x18001e23d  lea     r8, [r8+8]
0x18001e241  cmp     rcx, rdx
0x18001e244  jnz     short loc_18001E22C
0x18001e246  shl     r14, 3
0x18001e24a  jmp     short loc_18001E29B
0x18001e24c  mov     rdx, rsi
0x18001e24f  jmp     short loc_18001E266
0x18001e251  mov     rax, [rcx]
0x18001e254  mov     qword ptr [rcx], 0
0x18001e25b  add     rcx, 8
0x18001e25f  mov     [rdx], rax
0x18001e262  lea     rdx, [rdx+8]
0x18001e266  cmp     rcx, rdi
0x18001e269  jnz     short loc_18001E251
0x18001e26b  mov     rdx, [rbx+8]
0x18001e26f  shl     r14, 3
0x18001e273  mov     [rsp+98h+var_60], rsi
0x18001e278  lea     rcx, [r14+8]
0x18001e27c  add     rcx, rsi
0x18001e27f  jmp     short loc_18001E296
0x18001e281  mov     rax, [rdi]
0x18001e284  mov     qword ptr [rdi], 0
0x18001e28b  add     rdi, 8
0x18001e28f  mov     [rcx], rax
0x18001e292  lea     rcx, [rcx+8]
0x18001e296  cmp     rdi, rdx
0x18001e299  jnz     short loc_18001E281
0x18001e29b  mov     rdi, [rbx]
0x18001e29e  mov     [rsp+98h+var_70], 0
0x18001e2a7  test    rdi, rdi
0x18001e2aa  jz      short loc_18001E311
0x18001e2ac  mov     rbp, [rbx+8]
0x18001e2b0  jmp     short loc_18001E2C4
0x18001e2b2  cmp     qword ptr [rdi], 0
0x18001e2b6  jz      short loc_18001E2C0
0x18001e2b8  mov     rcx, rdi
0x18001e2bb  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001e2c0  add     rdi, 8
0x18001e2c4  cmp     rdi, rbp
0x18001e2c7  jnz     short loc_18001E2B2
0x18001e2c9  mov     rcx, [rbx]
0x18001e2cc  mov     rax, [rbx+10h]
0x18001e2d0  sub     rax, rcx
0x18001e2d3  sar     rax, 3
0x18001e2d7  lea     rdx, ds:0[rax*8]; unsigned __int64
0x18001e2df  cmp     rdx, 1000h
0x18001e2e6  jb      short loc_18001E306
0x18001e2e8  mov     rax, [rcx-8]
0x18001e2ec  sub     rcx, rax
0x18001e2ef  sub     rcx, 8
0x18001e2f3  cmp     rcx, 1Fh
0x18001e2f7  ja      short loc_18001E2FF
0x18001e2f9  add     rdx, 27h ; '''
0x18001e2fd  jmp     short loc_18001E309
0x18001e2ff  mov     ecx, 5
0x18001e304  int     29h; Win8: RtlFailFast(ecx)
0x18001e306  mov     rax, rcx
0x18001e309  mov     rcx, rax; void *
0x18001e30c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001e311  mov     rax, [rsp+98h+arg_0]
0x18001e319  lea     rcx, [rsp+98h+var_78]
0x18001e31e  mov     [rbx], rsi
0x18001e321  lea     rax, [rsi+rax*8]
0x18001e325  mov     [rbx+8], rax
0x18001e329  lea     rax, [rsi+r13]
0x18001e32d  mov     [rbx+10h], rax
0x18001e331  call    ??1_Reallocation_guard@?$vector@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@V?$allocator@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@@std@@@std@@QEAA@XZ; std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>::_Reallocation_guard::~_Reallocation_guard(void)
0x18001e336  lea     rax, [r14+rsi]
0x18001e33a  add     rsp, 58h
0x18001e33e  pop     r15
0x18001e340  pop     r14
0x18001e342  pop     r13
0x18001e344  pop     r12
0x18001e346  pop     rdi
0x18001e347  pop     rsi
0x18001e348  pop     rbp
0x18001e349  pop     rbx
0x18001e34a  retn
0x18001e34b  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
0x18001e351  call    ?_Xlength@?$vector@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@V?$allocator@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@@std@@@std@@CAXXZ; std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdate>::_Xlength(void)
```
