# Marshal::FromJsonValue<Container::Manager::Image::PackageAdjustment,>(Marshal::JsonParser &,utl::vector<Container::Manager::Image::PackageAdjustment,utl::allocator<Container::Manager::Image::PackageAdjustment>> *,Marshal::UnmarshalContext const &,Marshal::ModifierList<>)

- ea: `0x1800103b8`
- end: `0x1800106dc`
- name: `??$FromJsonValue@UPackageAdjustment@Image@Manager@Container@@$$V@Marshal@@YA_NAEAVJsonParser@0@PEAV?$vector@UPackageAdjustment@Image@Manager@Container@@V?$allocator@UPackageAdjustment@Image@Manager@Container@@@utl@@@utl@@AEBVUnmarshalContext@0@U?$ModifierList@$$V@0@@Z`
- size: `804`
- prototype: `char __fastcall(Marshal::JsonParser *, __int64 *, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callers

- `0x180010bc0`

## callees

- `0x180002534`
- `0x180003ce4`
- `0x1800101e4`
- `0x1800103b8`
- `0x18001339c`
- `0x1800150f8`
- `0x1800213ac`
- `0x18002163c`

## string_xrefs

- `0x1800106b8`: `onecore\internal\vm\inc\marshaljsonutl.h`
- `0x1800106ca`: `onecore\internal\vm\inc\marshaljsonutl.h`

## pseudocode

```c
char __fastcall Marshal::FromJsonValue<Container::Manager::Image::PackageAdjustment,>(
        Marshal::JsonParser *a1,
        __int64 *a2,
        __int64 a3)
{
  __int64 v6; // r9
  int v7; // ebx
  __int64 v8; // r8
  __int64 v9; // rdx
  __int64 v10; // r8
  _OWORD *v11; // rcx
  _OWORD *v12; // r9
  const char *v13; // r9
  char v14; // r14
  __int64 v15; // rsi
  __int64 v16; // rcx
  __int64 v17; // rbx
  void *v18; // rcx
  unsigned __int64 v19; // rcx
  unsigned __int64 v20; // rax
  unsigned __int64 v21; // rdx
  char v22; // al
  int i; // esi
  __int64 v24; // rbx
  __int64 v25; // rcx
  unsigned __int64 v26; // rcx
  unsigned __int64 v27; // rdx
  char v28; // al
  __int64 v29; // rcx
  _OWORD *v30; // rdx
  _OWORD *v31; // r8
  __int128 v33; // [rsp+20h] [rbp-20h] BYREF
  __int64 v34; // [rsp+30h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+38h]

  v33 = 0;
  v6 = 0;
  v34 = 0;
  v7 = 0;
  v8 = *a2;
  if ( 0xCCCCCCCCCCCCCCCDuLL * ((a2[1] - *a2) >> 3) )
  {
    v9 = *((_QWORD *)&v33 + 1);
    while ( 1 )
    {
      v10 = v8 + 40LL * v7;
      if ( v9 == v6 )
      {
        std::vector<Container::Manager::Image::PackageAdjustment>::_Emplace_reallocate<Container::Manager::Image::PackageAdjustment>(
          &v33,
          v9,
          v10);
        v9 = *((_QWORD *)&v33 + 1);
      }
      else
      {
        v11 = (_OWORD *)(v10 + 16);
        v12 = (_OWORD *)(v9 + 16);
        if ( *(_QWORD *)v10 == v10 + 16 )
        {
          *(_QWORD *)v9 = v12;
          *(_QWORD *)(v9 + 8) = v9 + 2 * (((*(_QWORD *)(v10 + 8) - v10 - 16) >> 1) + 8);
          *v12 = *v11;
        }
        else
        {
          *(_QWORD *)v9 = *(_QWORD *)v10;
          *(_QWORD *)(v9 + 8) = *(_QWORD *)(v10 + 8);
          *(_QWORD *)v12 = *(_QWORD *)v11;
        }
        *(_QWORD *)v10 = v11;
        *(_QWORD *)(v10 + 8) = v11;
        *(_WORD *)v11 = 0;
        *(_DWORD *)(v9 + 32) = *(_DWORD *)(v10 + 32);
        *(_DWORD *)(v9 + 36) = *(_DWORD *)(v10 + 36);
        v9 = *((_QWORD *)&v33 + 1) + 40LL;
        *((_QWORD *)&v33 + 1) += 40LL;
      }
      ++v7;
      v8 = *a2;
      if ( v7 >= 0xCCCCCCCCCCCCCCCDuLL * ((a2[1] - *a2) >> 3) )
        break;
      v6 = v34;
    }
  }
  v14 = Marshal::FromJsonValue<Container::Manager::Image::PackageAdjustment,>(a1, (__int64 *)&v33, a3);
  if ( v14 )
  {
    v15 = *a2;
    v16 = a2[1];
    a2[1] = *a2;
    v17 = (v16 - v15) / 40;
    while ( v17 )
    {
      --v17;
      v18 = *(void **)(v15 + 40 * v17);
      if ( v18 != (void *)(v15 + 8 * (5 * v17 + 2)) )
        operator delete(v18, (const struct std::nothrow_t *)&std::nothrow);
    }
    v19 = 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*((_QWORD *)&v33 + 1) - v33) >> 3);
    v20 = 0xCCCCCCCCCCCCCCCDuLL * ((a2[2] - *a2) >> 3);
    if ( v19 <= v20 )
      goto LABEL_24;
    v21 = 7 * (v20 >> 2) + 8;
    if ( v21 < v19 )
      v21 = 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*((_QWORD *)&v33 + 1) - v33) >> 3);
    if ( v21 > 0x333333333333333LL )
      v21 = 0x333333333333333LL;
    if ( v19 <= v21
      && (unsigned __int8)utl::vector<Container::Manager::Image::PackageAdjustment,utl::allocator<Container::Manager::Image::PackageAdjustment>>::_SetCapacity(a2) )
    {
LABEL_24:
      v22 = 0;
    }
    else
    {
      v22 = 1;
    }
    if ( v22 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x78,
        (unsigned int)"onecore\\internal\\vm\\inc\\marshaljsonutl.h",
        (const char *)0x8007000ELL,
        v33);
    for ( i = 0; i < 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*((_QWORD *)&v33 + 1) - v33) >> 3); ++i )
    {
      v24 = v33 + 40LL * i;
      v25 = a2[2];
      if ( a2[1] != v25 )
        goto LABEL_33;
      v26 = 0xCCCCCCCCCCCCCCCDuLL * ((v25 - *a2) >> 3);
      v27 = 7 * (v26 >> 2) + 8;
      if ( v27 > 0x333333333333333LL )
        v27 = 0x333333333333333LL;
      if ( v26 < v27
        && (unsigned __int8)utl::vector<Container::Manager::Image::PackageAdjustment,utl::allocator<Container::Manager::Image::PackageAdjustment>>::_SetCapacity(a2) )
      {
LABEL_33:
        v29 = a2[1];
        v30 = (_OWORD *)(v24 + 16);
        v31 = (_OWORD *)(v29 + 16);
        if ( *(_QWORD *)v24 == v24 + 16 )
        {
          *(_QWORD *)v29 = v31;
          *(_QWORD *)(v29 + 8) = v29 + 2 * (((*(_QWORD *)(v24 + 8) - v24 - 16) >> 1) + 8);
          *v31 = *v30;
        }
        else
        {
          *(_QWORD *)v29 = *(_QWORD *)v24;
          *(_QWORD *)(v29 + 8) = *(_QWORD *)(v24 + 8);
          *(_QWORD *)v31 = *(_QWORD *)v30;
        }
        *(_QWORD *)v24 = v30;
        *(_QWORD *)(v24 + 8) = v30;
        *(_WORD *)v30 = 0;
        *(_DWORD *)(v29 + 32) = *(_DWORD *)(v24 + 32);
        *(_DWORD *)(v29 + 36) = *(_DWORD *)(v24 + 36);
        a2[1] += 40;
        v28 = 0;
      }
      else
      {
        v28 = 1;
      }
      if ( v28 )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x7F,
          (unsigned int)"onecore\\internal\\vm\\inc\\marshaljsonutl.h",
          v13);
    }
  }
  std::vector<Container::Manager::Image::PackageAdjustment>::~vector<Container::Manager::Image::PackageAdjustment>(&v33);
  return v14;
}

```

## disassembly

```asm
0x1800103b8  push    rbp
0x1800103ba  push    rbx
0x1800103bb  push    rsi
0x1800103bc  push    rdi
0x1800103bd  push    r12
0x1800103bf  push    r14
0x1800103c1  push    r15
0x1800103c3  mov     rbp, rsp
0x1800103c6  sub     rsp, 40h
0x1800103ca  mov     rsi, r8
0x1800103cd  mov     rdi, rdx
0x1800103d0  mov     r14, rcx
0x1800103d3  xorps   xmm0, xmm0
0x1800103d6  movdqu  [rbp+var_20], xmm0
0x1800103db  xor     r9d, r9d
0x1800103de  mov     [rbp+var_10], r9
0x1800103e2  xor     ebx, ebx
0x1800103e4  mov     r8, [rdx]
0x1800103e7  mov     rax, [rdx+8]
0x1800103eb  sub     rax, r8
0x1800103ee  sar     rax, 3
0x1800103f2  mov     r15, 0CCCCCCCCCCCCCCCDh
0x1800103fc  imul    rax, r15
0x180010400  test    rax, rax
0x180010403  jz      loc_1800104BF
0x180010409  mov     rdx, qword ptr [rbp+var_20+8]
0x18001040d  movsxd  rax, ebx
0x180010410  lea     rcx, [rax+rax*4]
0x180010414  lea     r8, [r8+rcx*8]
0x180010418  cmp     rdx, r9
0x18001041b  jz      short loc_18001048D
0x18001041d  lea     rcx, [r8+10h]
0x180010421  mov     rax, [r8]
0x180010424  lea     r9, [rdx+10h]
0x180010428  cmp     rax, rcx
0x18001042b  jnz     short loc_180010454
0x18001042d  mov     [rdx], r9
0x180010430  mov     rax, [r8+8]
0x180010434  sub     rax, r8
0x180010437  sub     rax, 10h
0x18001043b  sar     rax, 1
0x18001043e  add     rax, 8
0x180010442  lea     rax, [rdx+rax*2]
0x180010446  mov     [rdx+8], rax
0x18001044a  movups  xmm0, xmmword ptr [rcx]
0x18001044d  movdqu  xmmword ptr [r9], xmm0
0x180010452  jmp     short loc_180010465
0x180010454  mov     [rdx], rax
0x180010457  mov     rax, [r8+8]
0x18001045b  mov     [rdx+8], rax
0x18001045f  mov     rax, [rcx]
0x180010462  mov     [r9], rax
0x180010465  mov     [r8], rcx
0x180010468  mov     [r8+8], rcx
0x18001046c  xor     eax, eax
0x18001046e  mov     [rcx], ax
0x180010471  mov     eax, [r8+20h]
0x180010475  mov     [rdx+20h], eax
0x180010478  mov     eax, [r8+24h]
0x18001047c  mov     [rdx+24h], eax
0x18001047f  mov     rdx, qword ptr [rbp+var_20+8]
0x180010483  add     rdx, 28h ; '('
0x180010487  mov     qword ptr [rbp+var_20+8], rdx
0x18001048b  jmp     short loc_18001049A
0x18001048d  lea     rcx, [rbp+var_20]
0x180010491  call    ??$_Emplace_reallocate@UPackageAdjustment@Image@Manager@Container@@@?$vector@UPackageAdjustment@Image@Manager@Container@@V?$allocator@UPackageAdjustment@Image@Manager@Container@@@std@@@std@@AEAAPEAUPackageAdjustment@Image@Manager@Container@@QEAU2345@$$QEAU2345@@Z; std::vector<Container::Manager::Image::PackageAdjustment>::_Emplace_reallocate<Container::Manager::Image::PackageAdjustment>(Container::Manager::Image::PackageAdjustment * const,Container::Manager::Image::PackageAdjustment &&)
0x180010496  mov     rdx, qword ptr [rbp+var_20+8]
0x18001049a  inc     ebx
0x18001049c  mov     r8, [rdi]
0x18001049f  mov     rcx, [rdi+8]
0x1800104a3  sub     rcx, r8
0x1800104a6  sar     rcx, 3
0x1800104aa  imul    rcx, r15
0x1800104ae  movsxd  rax, ebx
0x1800104b1  cmp     rax, rcx
0x1800104b4  jnb     short loc_1800104BF
0x1800104b6  mov     r9, [rbp+var_10]
0x1800104ba  jmp     loc_18001040D
0x1800104bf  mov     r8, rsi
0x1800104c2  lea     rdx, [rbp+var_20]
0x1800104c6  mov     rcx, r14
0x1800104c9  call    ??$FromJsonValue@UPackageAdjustment@Image@Manager@Container@@$$V@Marshal@@YA_NAEAVJsonParser@0@PEAV?$vector@UPackageAdjustment@Image@Manager@Container@@V?$allocator@UPackageAdjustment@Image@Manager@Container@@@std@@@std@@AEBVUnmarshalContext@0@U?$ModifierList@$$V@0@@Z; Marshal::FromJsonValue<Container::Manager::Image::PackageAdjustment,>(Marshal::JsonParser &,std::vector<Container::Manager::Image::PackageAdjustment> *,Marshal::UnmarshalContext const &,Marshal::ModifierList<>)
0x1800104ce  mov     r14b, al
0x1800104d1  test    al, al
0x1800104d3  jz      loc_180010696
0x1800104d9  mov     rsi, [rdi]
0x1800104dc  mov     rcx, [rdi+8]
0x1800104e0  mov     [rdi+8], rsi
0x1800104e4  sub     rcx, rsi
0x1800104e7  mov     rax, 6666666666666667h
0x1800104f1  imul    rcx
0x1800104f4  mov     rbx, rdx
0x1800104f7  sar     rbx, 4
0x1800104fb  mov     rcx, rbx
0x1800104fe  shr     rcx, 3Fh
0x180010502  add     rbx, rcx
0x180010505  jz      short loc_180010530
0x180010507  dec     rbx
0x18001050a  lea     rax, [rbx+rbx*4]
0x18001050e  mov     rcx, [rsi+rax*8]; void *
0x180010512  lea     rax, [rax+2]
0x180010516  lea     rax, [rsi+rax*8]
0x18001051a  cmp     rcx, rax
0x18001051d  jz      short loc_18001052B
0x18001051f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180010526  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001052b  test    rbx, rbx
0x18001052e  jnz     short loc_180010507
0x180010530  mov     rcx, qword ptr [rbp+var_20+8]
0x180010534  sub     rcx, qword ptr [rbp+var_20]
0x180010538  sar     rcx, 3
0x18001053c  imul    rcx, r15
0x180010540  mov     rax, [rdi+10h]
0x180010544  sub     rax, [rdi]
0x180010547  sar     rax, 3
0x18001054b  imul    rax, r15
0x18001054f  mov     r12, 333333333333333h
0x180010559  cmp     rcx, rax
0x18001055c  jbe     short loc_18001058D
0x18001055e  shr     rax, 2
0x180010562  imul    rdx, rax, 7
0x180010566  add     rdx, 8
0x18001056a  cmp     rdx, rcx
0x18001056d  cmovb   rdx, rcx
0x180010571  cmp     rdx, r12
0x180010574  cmova   rdx, r12
0x180010578  cmp     rcx, rdx
0x18001057b  ja      short loc_180010589
0x18001057d  mov     rcx, rdi
0x180010580  call    ?_SetCapacity@?$vector@UPackageAdjustment@Image@Manager@Container@@V?$allocator@UPackageAdjustment@Image@Manager@Container@@@utl@@@utl@@AEAA_N_K@Z; utl::vector<Container::Manager::Image::PackageAdjustment,utl::allocator<Container::Manager::Image::PackageAdjustment>>::_SetCapacity(unsigned __int64)
0x180010585  test    al, al
0x180010587  jnz     short loc_18001058D
0x180010589  mov     al, 1
0x18001058b  jmp     short loc_18001058F
0x18001058d  xor     al, al
0x18001058f  mov     rcx, [rbp+38h]; this
0x180010593  test    al, al
0x180010595  jnz     loc_1800106B2
0x18001059b  xor     esi, esi
0x18001059d  mov     rax, qword ptr [rbp+var_20+8]
0x1800105a1  sub     rax, qword ptr [rbp+var_20]
0x1800105a5  sar     rax, 3
0x1800105a9  imul    rax, r15
0x1800105ad  test    rax, rax
0x1800105b0  jz      loc_180010696
0x1800105b6  movsxd  rax, esi
0x1800105b9  lea     rcx, [rax+rax*4]
0x1800105bd  mov     rax, qword ptr [rbp+var_20]
0x1800105c1  lea     rbx, [rax+rcx*8]
0x1800105c5  mov     rcx, [rdi+10h]
0x1800105c9  cmp     [rdi+8], rcx
0x1800105cd  jnz     short loc_180010605
0x1800105cf  sub     rcx, [rdi]
0x1800105d2  sar     rcx, 3
0x1800105d6  imul    rcx, r15
0x1800105da  mov     rax, rcx
0x1800105dd  shr     rax, 2
0x1800105e1  imul    rdx, rax, 7
0x1800105e5  add     rdx, 8
0x1800105e9  cmp     rdx, r12
0x1800105ec  cmova   rdx, r12
0x1800105f0  cmp     rcx, rdx
0x1800105f3  jnb     short loc_180010601
0x1800105f5  mov     rcx, rdi
0x1800105f8  call    ?_SetCapacity@?$vector@UPackageAdjustment@Image@Manager@Container@@V?$allocator@UPackageAdjustment@Image@Manager@Container@@@utl@@@utl@@AEAA_N_K@Z; utl::vector<Container::Manager::Image::PackageAdjustment,utl::allocator<Container::Manager::Image::PackageAdjustment>>::_SetCapacity(unsigned __int64)
0x1800105fd  test    al, al
0x1800105ff  jnz     short loc_180010605
0x180010601  mov     al, 1
0x180010603  jmp     short loc_180010670
0x180010605  mov     rcx, [rdi+8]
0x180010609  lea     rdx, [rbx+10h]
0x18001060d  mov     rax, [rbx]
0x180010610  lea     r8, [rcx+10h]
0x180010614  cmp     rax, rdx
0x180010617  jnz     short loc_180010640
0x180010619  mov     [rcx], r8
0x18001061c  mov     rax, [rbx+8]
0x180010620  sub     rax, rbx
0x180010623  sub     rax, 10h
0x180010627  sar     rax, 1
0x18001062a  add     rax, 8
0x18001062e  lea     rax, [rcx+rax*2]
0x180010632  mov     [rcx+8], rax
0x180010636  movups  xmm0, xmmword ptr [rdx]
0x180010639  movdqu  xmmword ptr [r8], xmm0
0x18001063e  jmp     short loc_180010651
0x180010640  mov     [rcx], rax
0x180010643  mov     rax, [rbx+8]
0x180010647  mov     [rcx+8], rax
0x18001064b  mov     rax, [rdx]
0x18001064e  mov     [r8], rax
0x180010651  mov     [rbx], rdx
0x180010654  mov     [rbx+8], rdx
0x180010658  xor     eax, eax
0x18001065a  mov     [rdx], ax
0x18001065d  mov     eax, [rbx+20h]
0x180010660  mov     [rcx+20h], eax
0x180010663  mov     eax, [rbx+24h]
0x180010666  mov     [rcx+24h], eax
0x180010669  add     qword ptr [rdi+8], 28h ; '('
0x18001066e  xor     al, al
0x180010670  mov     rcx, [rbp+38h]; this
0x180010674  test    al, al
0x180010676  jnz     short loc_1800106CA
0x180010678  inc     esi
0x18001067a  mov     rcx, qword ptr [rbp+var_20+8]
0x18001067e  sub     rcx, qword ptr [rbp+var_20]
0x180010682  sar     rcx, 3
0x180010686  imul    rcx, r15
0x18001068a  movsxd  rax, esi
0x18001068d  cmp     rax, rcx
0x180010690  jb      loc_1800105B6
0x180010696  lea     rcx, [rbp+var_20]
0x18001069a  call    ??1?$vector@UPackageAdjustment@Image@Manager@Container@@V?$allocator@UPackageAdjustment@Image@Manager@Container@@@std@@@std@@QEAA@XZ; std::vector<Container::Manager::Image::PackageAdjustment>::~vector<Container::Manager::Image::PackageAdjustment>(void)
0x18001069f  mov     al, r14b
0x1800106a2  add     rsp, 40h
0x1800106a6  pop     r15
0x1800106a8  pop     r14
0x1800106aa  pop     r12
0x1800106ac  pop     rdi
0x1800106ad  pop     rsi
0x1800106ae  pop     rbx
0x1800106af  pop     rbp
0x1800106b0  retn
0x1800106b2  mov     r9d, 8007000Eh; char *
0x1800106b8  lea     r8, aOnecoreInterna_3; "onecore\\internal\\vm\\inc\\marshaljson"...
0x1800106bf  mov     edx, 78h ; 'x'; void *
0x1800106c4  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800106ca  lea     r8, aOnecoreInterna_3; "onecore\\internal\\vm\\inc\\marshaljson"...
0x1800106d1  mov     edx, 7Fh; void *
0x1800106d6  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
