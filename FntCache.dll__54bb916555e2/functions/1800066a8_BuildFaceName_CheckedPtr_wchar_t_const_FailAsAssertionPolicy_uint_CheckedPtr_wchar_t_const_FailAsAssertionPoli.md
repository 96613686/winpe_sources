# BuildFaceName(CheckedPtr<wchar_t const,FailAsAssertionPolicy,uint>,CheckedPtr<wchar_t const,FailAsAssertionPolicy,uint>,DWRITE_FONT_STRETCH,CheckedPtr<wchar_t const,FailAsAssertionPolicy,uint>,DWRITE_FONT_WEIGHT,CheckedPtr<wchar_t const,FailAsAssertionPolicy,uint>,DWRITE_FONT_STYLE,CheckedPtr<wchar_t const,FailAsAssertionPolicy,uint>)

- ea: `0x1800066a8`
- end: `0x1800069db`
- name: `?BuildFaceName@@YA?AVRefString@DWrite@@V?$CheckedPtr@$$CB_WVFailAsAssertionPolicy@@I@@0W4DWRITE_FONT_STRETCH@@0W4DWRITE_FONT_WEIGHT@@0W4DWRITE_FONT_STYLE@@0@Z`
- size: `819`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config`

## callers

- `0x180027e0c`

## callees

- `0x1800066a8`
- `0x180007b28`
- `0x180007b9c`
- `0x180007c80`
- `0x180008074`
- `0x180028c50`
- `0x18002bf90`
- `0x18002ce34`
- `0x18009807c`
- `0x18009aae8`
- `0x1800aa650`
- `0x1800ab0aa`
- `0x1800b09dc`
- `0x1800c60b4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800067df`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800067df`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
struct DWrite::RefString::Data **__fastcall BuildFaceName(
        struct DWrite::RefString::Data **a1,
        __int64 a2,
        const wchar_t **a3,
        int a4,
        __int64 a5,
        unsigned int a6,
        __int64 a7,
        int a8,
        struct DWrite::RefString::Data *a9)
{
  struct DWrite::RefString::Data *v10; // r11
  struct DWrite::RefString::Data *v12; // r10
  _DWORD *v13; // rbx
  unsigned int *v14; // rdi
  unsigned int *v15; // r9
  unsigned __int64 v16; // rsi
  unsigned __int64 v17; // r15
  unsigned __int64 v18; // r8
  unsigned __int64 v19; // rdi
  unsigned __int64 v20; // rax
  unsigned __int64 v21; // rbx
  wchar_t *v22; // rax
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // r8
  wchar_t *v27; // rax
  unsigned __int64 v28; // rax
  struct DWrite::RefString::Data *v29; // rax
  struct DWrite::RefString::Data *v30; // rbx
  char v31; // di
  char v32; // di
  struct DWrite::RefString::Data *v33; // [rsp+28h] [rbp-58h] BYREF
  int v34; // [rsp+30h] [rbp-50h]
  struct DWrite::RefString::Data *v35; // [rsp+38h] [rbp-48h] BYREF
  _QWORD v36[2]; // [rsp+40h] [rbp-40h] BYREF
  _BYTE v37[16]; // [rsp+50h] [rbp-30h] BYREF
  struct DWrite::RefString::Data **v38; // [rsp+60h] [rbp-20h]
  _BYTE v39[8]; // [rsp+68h] [rbp-18h] BYREF

  v10 = (struct DWrite::RefString::Data *)a2;
  v35 = (struct DWrite::RefString::Data *)a2;
  v38 = a1;
  v36[0] = a7;
  v12 = a9;
  v33 = a9;
  v13 = a3 + 1;
  if ( *(_DWORD *)(a2 + 8) )
  {
    v14 = (unsigned int *)(a5 + 8);
    v15 = (unsigned int *)(a7 + 8);
  }
  else
  {
    if ( !*v13 && a4 != 5 )
    {
      LOBYTE(a2) = a4;
      *(_OWORD *)a3 = *(_OWORD *)GetFontStretchName(v37, a2);
    }
    v14 = (unsigned int *)(a5 + 8);
    if ( !*(_DWORD *)(a5 + 8) && a6 != 400 )
    {
      *(_OWORD *)a5 = *(_OWORD *)GetFontWeightName(v37, a6, v39);
      v12 = v33;
      v10 = v35;
    }
    v15 = (unsigned int *)(a7 + 8);
    if ( !*(_DWORD *)(a7 + 8) && a8 )
      *(_OWORD *)a7 = *(_OWORD *)GetFontStyleName(v37);
  }
  v16 = *((unsigned int *)v10 + 2);
  v17 = (unsigned int)*v13;
  if ( (_DWORD)v17 )
  {
    v18 = v16 + v17 + 1;
    if ( !*((_DWORD *)v10 + 2) )
      v18 = (unsigned int)*v13;
  }
  else
  {
    v18 = (unsigned int)v16;
  }
  v19 = *v14;
  if ( (_DWORD)v19 )
  {
    v20 = v18;
    v18 += v19 + 1;
    if ( !v20 )
      v18 = v19;
  }
  v21 = *v15;
  if ( (_DWORD)v21 )
  {
    v28 = v18;
    v18 += v21 + 1;
    if ( !v28 )
      v18 = *v15;
  }
  if ( v18 )
  {
    RefStringBuilder::RefStringBuilder((RefStringBuilder *)&v33, v18);
    if ( *((_DWORD *)v35 + 2) )
      RefStringBuilder::Append((RefStringBuilder *)&v33, *(const wchar_t **)v35, v16);
    if ( (_DWORD)v17 )
    {
      if ( v34 )
        RefStringBuilder::Append((RefStringBuilder *)&v33, L" ", 1u);
      RefStringBuilder::Append((RefStringBuilder *)&v33, *a3, v17);
    }
    if ( (_DWORD)v19 )
    {
      if ( v34 )
      {
        v22 = RefStringBuilder::UninitializedAppend((RefStringBuilder *)&v33, 1u);
        if ( v22 )
        {
          *v22 = 32;
        }
        else
        {
          *(_DWORD *)_o__errno(v24, v23, v25) = 22;
          invalid_parameter_noinfo();
        }
      }
      RefStringBuilder::Append((RefStringBuilder *)&v33, *(const wchar_t **)a5, v19);
    }
    if ( (_DWORD)v21 )
    {
      if ( v34 )
      {
        v27 = RefStringBuilder::UninitializedAppend((RefStringBuilder *)&v33, 1u);
        memcpy_s(v27, 2u, L" ", 2u);
      }
      RefStringBuilder::Append((RefStringBuilder *)&v33, *(const wchar_t **)v36[0], v21);
    }
    RefStringBuilder::GetString(&v33, a1);
    DWrite::RefString::DecrementRef(v33);
  }
  else
  {
    if ( *((_DWORD *)v12 + 2) )
    {
      v29 = DWrite::RefString::NewData(*(const wchar_t **)v12, *((unsigned int *)v12 + 2), 0, (__int64)v15);
      v30 = v29;
      v33 = v29;
      v31 = 1;
    }
    else
    {
      v36[0] = L"Regular";
      v36[1] = 7;
      v31 = 2;
      v29 = *DWrite::RefString::RefString(&v35, (__int64)v36);
      v30 = v33;
    }
    *a1 = v29;
    _InterlockedAdd((volatile signed __int32 *)v29, 1u);
    v32 = v31 | 4;
    if ( (v32 & 2) != 0 )
    {
      v32 &= ~2u;
      DWrite::RefString::DecrementRef(v35);
    }
    if ( (v32 & 1) != 0 )
      DWrite::RefString::DecrementRef(v30);
  }
  return a1;
}

```

## disassembly

```asm
0x1800066a8  mov     [rsp-38h+arg_18], rbx
0x1800066ad  push    rbp
0x1800066ae  push    rsi
0x1800066af  push    rdi
0x1800066b0  push    r12
0x1800066b2  push    r13
0x1800066b4  push    r14
0x1800066b6  push    r15
0x1800066b8  mov     rbp, rsp
0x1800066bb  sub     rsp, 80h
0x1800066c2  mov     rax, cs:__security_cookie
0x1800066c9  xor     rax, rsp
0x1800066cc  mov     [rbp+var_10], rax
0x1800066d0  mov     r12, r8
0x1800066d3  mov     r11, rdx
0x1800066d6  mov     [rbp+var_48], rdx
0x1800066da  mov     r14, rcx
0x1800066dd  mov     [rbp+var_20], rcx
0x1800066e1  mov     r13, [rbp+arg_20]
0x1800066e5  mov     rsi, [rbp+arg_30]
0x1800066e9  mov     [rbp+var_40], rsi
0x1800066ed  mov     r10, [rbp+arg_40]
0x1800066f4  mov     [rbp+var_58], r10
0x1800066f8  mov     [rbp+var_60], 0
0x1800066ff  lea     rbx, [r8+8]
0x180006703  cmp     dword ptr [rdx+8], 0
0x180006707  jnz     loc_18000684F
0x18000670d  cmp     dword ptr [rbx], 0
0x180006710  jnz     short loc_18000672D
0x180006712  cmp     r9d, 5
0x180006716  jz      short loc_18000672D
0x180006718  mov     dl, r9b
0x18000671b  lea     rcx, [rbp+var_30]
0x18000671f  call    ?GetFontStretchName@@YA?AV?$CheckedPtr@$$CB_WVFailAsAssertionPolicy@@I@@U?$SmallEnum@W4DWRITE_FONT_STRETCH@@E@@@Z; GetFontStretchName(SmallEnum<DWRITE_FONT_STRETCH,uchar>)
0x180006724  movups  xmm0, xmmword ptr [rax]
0x180006727  movdqu  xmmword ptr [r12], xmm0
0x18000672d  lea     rdi, [r13+8]
0x180006731  cmp     dword ptr [rdi], 0
0x180006734  jz      loc_1800068E9
0x18000673a  lea     r9, [rsi+8]
0x18000673e  cmp     dword ptr [r9], 0
0x180006742  jnz     short loc_18000674F
0x180006744  mov     edx, [rbp+arg_38]
0x180006747  test    edx, edx
0x180006749  jnz     loc_180006982
0x18000674f  mov     esi, [r11+8]
0x180006753  mov     r15d, [rbx]
0x180006756  test    r15d, r15d
0x180006759  jnz     loc_18000688A
0x18000675f  mov     r8d, esi
0x180006762  mov     edi, [rdi]
0x180006764  test    edi, edi
0x180006766  jz      short loc_180006778
0x180006768  mov     rax, r8
0x18000676b  inc     r8
0x18000676e  add     r8, rdi
0x180006771  test    rax, rax
0x180006774  cmovz   r8, rdi
0x180006778  mov     ebx, [r9]
0x18000677b  test    ebx, ebx
0x18000677d  jnz     loc_18000691B
0x180006783  test    r8, r8
0x180006786  jz      loc_180006930
0x18000678c  mov     rdx, r8; unsigned __int64
0x18000678f  lea     rcx, [rbp+var_58]; this
0x180006793  call    ??0RefStringBuilder@@QEAA@_K@Z; RefStringBuilder::RefStringBuilder(unsigned __int64)
0x180006798  nop
0x180006799  mov     rdx, [rbp+var_48]
0x18000679d  cmp     dword ptr [rdx+8], 0
0x1800067a1  jz      short loc_1800067B2
0x1800067a3  mov     r8, rsi; unsigned __int64
0x1800067a6  mov     rdx, [rdx]; wchar_t *
0x1800067a9  lea     rcx, [rbp+var_58]; this
0x1800067ad  call    ?Append@RefStringBuilder@@QEAAPEA_WPEB_W_K@Z; RefStringBuilder::Append(wchar_t const *,unsigned __int64)
0x1800067b2  mov     esi, 1
0x1800067b7  test    r15d, r15d
0x1800067ba  jnz     loc_18000685C
0x1800067c0  test    edi, edi
0x1800067c2  jz      short loc_180006800
0x1800067c4  cmp     [rbp+var_50], 0
0x1800067c8  jz      short loc_1800067F0
0x1800067ca  mov     rdx, rsi; unsigned __int64
0x1800067cd  lea     rcx, [rbp+var_58]; this
0x1800067d1  call    ?UninitializedAppend@RefStringBuilder@@QEAAPEA_W_K@Z; RefStringBuilder::UninitializedAppend(unsigned __int64)
0x1800067d6  test    rax, rax
0x1800067d9  jnz     loc_18000689D
0x1800067df  call    cs:__imp__o__errno
0x1800067e5  mov     dword ptr [rax], 16h
0x1800067eb  call    _invalid_parameter_noinfo
0x1800067f0  mov     r8, rdi; unsigned __int64
0x1800067f3  mov     rdx, [r13+0]; wchar_t *
0x1800067f7  lea     rcx, [rbp+var_58]; this
0x1800067fb  call    ?Append@RefStringBuilder@@QEAAPEA_WPEB_W_K@Z; RefStringBuilder::Append(wchar_t const *,unsigned __int64)
0x180006800  test    ebx, ebx
0x180006802  jnz     loc_1800068A7
0x180006808  mov     rdx, r14
0x18000680b  lea     rcx, [rbp+var_58]
0x18000680f  call    ?GetString@RefStringBuilder@@QEAA?AVRefString@DWrite@@XZ; RefStringBuilder::GetString(void)
0x180006814  mov     [rbp+var_60], 4
0x18000681b  mov     rcx, [rbp+var_58]; struct DWrite::RefString::Data *
0x18000681f  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x180006824  nop
0x180006825  mov     rax, r14
0x180006828  mov     rcx, [rbp+var_10]
0x18000682c  xor     rcx, rsp; StackCookie
0x18000682f  call    __security_check_cookie
0x180006834  mov     rbx, [rsp+80h+arg_18]
0x18000683c  add     rsp, 80h
0x180006843  pop     r15
0x180006845  pop     r14
0x180006847  pop     r13
0x180006849  pop     r12
0x18000684b  pop     rdi
0x18000684c  pop     rsi
0x18000684d  pop     rbp
0x18000684e  retn
0x18000684f  lea     rdi, [r13+8]
0x180006853  lea     r9, [rsi+8]
0x180006857  jmp     loc_18000674F
0x18000685c  cmp     [rbp+var_50], 0
0x180006860  jz      short loc_180006875
0x180006862  mov     r8, rsi; unsigned __int64
0x180006865  lea     rdx, asc_1800EAEB0; " "
0x18000686c  lea     rcx, [rbp+var_58]; this
0x180006870  call    ?Append@RefStringBuilder@@QEAAPEA_WPEB_W_K@Z; RefStringBuilder::Append(wchar_t const *,unsigned __int64)
0x180006875  mov     r8, r15; unsigned __int64
0x180006878  mov     rdx, [r12]; wchar_t *
0x18000687c  lea     rcx, [rbp+var_58]; this
0x180006880  call    ?Append@RefStringBuilder@@QEAAPEA_WPEB_W_K@Z; RefStringBuilder::Append(wchar_t const *,unsigned __int64)
0x180006885  jmp     loc_1800067C0
0x18000688a  lea     r8, [r15+1]
0x18000688e  add     r8, rsi
0x180006891  test    rsi, rsi
0x180006894  cmovz   r8, r15
0x180006898  jmp     loc_180006762
0x18000689d  mov     word ptr [rax], 20h ; ' '
0x1800068a2  jmp     loc_1800067F0
0x1800068a7  cmp     [rbp+var_50], 0
0x1800068ab  jz      short loc_1800068D1
0x1800068ad  mov     rdx, rsi; unsigned __int64
0x1800068b0  lea     rcx, [rbp+var_58]; this
0x1800068b4  call    ?UninitializedAppend@RefStringBuilder@@QEAAPEA_W_K@Z; RefStringBuilder::UninitializedAppend(unsigned __int64)
0x1800068b9  mov     r9d, 2; SourceSize
0x1800068bf  lea     r8, asc_1800EAEB0; " "
0x1800068c6  mov     edx, r9d; DestinationSize
0x1800068c9  mov     rcx, rax; Destination
0x1800068cc  call    memcpy_s
0x1800068d1  mov     r8, rbx; unsigned __int64
0x1800068d4  mov     rdx, [rbp+var_40]
0x1800068d8  mov     rdx, [rdx]; wchar_t *
0x1800068db  lea     rcx, [rbp+var_58]; this
0x1800068df  call    ?Append@RefStringBuilder@@QEAAPEA_WPEB_W_K@Z; RefStringBuilder::Append(wchar_t const *,unsigned __int64)
0x1800068e4  jmp     loc_180006808
0x1800068e9  mov     edx, [rbp+arg_28]
0x1800068ec  cmp     edx, 190h
0x1800068f2  jz      loc_18000673A
0x1800068f8  lea     r8, [rbp+var_18]
0x1800068fc  lea     rcx, [rbp+var_30]
0x180006900  call    ?GetFontWeightName@@YA?AV?$CheckedPtr@$$CB_WVFailAsAssertionPolicy@@I@@U?$SmallEnum@W4DWRITE_FONT_WEIGHT@@G@@AEAY02_W@Z; GetFontWeightName(SmallEnum<DWRITE_FONT_WEIGHT,ushort>,wchar_t (&)[3])
0x180006905  movups  xmm0, xmmword ptr [rax]
0x180006908  movdqu  xmmword ptr [r13+0], xmm0
0x18000690e  mov     r10, [rbp+var_58]
0x180006912  mov     r11, [rbp+var_48]
0x180006916  jmp     loc_18000673A
0x18000691b  mov     rax, r8
0x18000691e  inc     r8
0x180006921  add     r8, rbx
0x180006924  test    rax, rax
0x180006927  cmovz   r8, rbx
0x18000692b  jmp     loc_180006783
0x180006930  mov     esi, 1
0x180006935  cmp     dword ptr [r10+8], 0
0x18000693a  jz      short loc_180006997
0x18000693c  mov     edx, [r10+8]; unsigned __int64
0x180006940  mov     rcx, [r10]; Src
0x180006943  call    ?NewData@RefString@DWrite@@CAPEAUData@12@PEB_W_K@Z; DWrite::RefString::NewData(wchar_t const *,unsigned __int64)
0x180006948  mov     rbx, rax
0x18000694b  mov     [rbp+var_58], rax
0x18000694f  mov     edi, esi
0x180006951  mov     [rbp+var_60], esi
0x180006954  mov     [r14], rax
0x180006957  lock add [rax], esi
0x18000695a  or      edi, 4
0x18000695d  mov     [rbp+var_60], edi
0x180006960  test    dil, 2
0x180006964  jnz     short loc_1800069C9
0x180006966  test    sil, dil
0x180006969  jz      loc_180006825
0x18000696f  and     edi, 0FFFFFFFEh
0x180006972  mov     [rbp+var_60], edi
0x180006975  mov     rcx, rbx; struct DWrite::RefString::Data *
0x180006978  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x18000697d  jmp     loc_180006825
0x180006982  lea     rcx, [rbp+var_30]
0x180006986  call    ?GetFontStyleName@@YA?AV?$CheckedPtr@$$CB_WVFailAsAssertionPolicy@@I@@U?$SmallEnum@W4DWRITE_FONT_STYLE@@E@@@Z; GetFontStyleName(SmallEnum<DWRITE_FONT_STYLE,uchar>)
0x18000698b  movups  xmm0, xmmword ptr [rax]
0x18000698e  movdqu  xmmword ptr [rsi], xmm0
0x180006992  jmp     loc_18000674F
0x180006997  lea     rax, aRegular; "Regular"
0x18000699e  mov     [rbp+var_40], rax
0x1800069a2  mov     [rbp+var_38], 7
0x1800069aa  lea     rdx, [rbp+var_40]
0x1800069ae  lea     rcx, [rbp+var_48]
0x1800069b2  call    ??$?0PEB_W@RefString@DWrite@@QEAA@AEBV?$StringExpr@PEB_W@@@Z; DWrite::RefString::RefString(StringExpr<wchar_t const *> const &)
0x1800069b7  nop
0x1800069b8  mov     edi, 2
0x1800069bd  mov     [rbp+var_60], edi
0x1800069c0  mov     rax, [rax]
0x1800069c3  mov     rbx, [rbp+var_58]
0x1800069c7  jmp     short loc_180006954
0x1800069c9  and     edi, 0FFFFFFFDh
0x1800069cc  mov     [rbp+var_60], edi
0x1800069cf  mov     rcx, [rbp+var_48]; struct DWrite::RefString::Data *
0x1800069d3  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x1800069d8  jmp     short loc_180006966
```
