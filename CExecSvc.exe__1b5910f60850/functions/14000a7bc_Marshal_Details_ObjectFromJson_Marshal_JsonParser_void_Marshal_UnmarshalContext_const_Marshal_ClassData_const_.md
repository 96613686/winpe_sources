# Marshal::Details::ObjectFromJson(Marshal::JsonParser &,void *,Marshal::UnmarshalContext const &,Marshal::ClassData const &,Marshal::Details::ArrayView<Marshal::Details::BaseTypeData const *>,Marshal::Details::ArrayView<Marshal::Details::JsonTypeData const *>)

- ea: `0x14000a7bc`
- end: `0x14000adab`
- name: `?ObjectFromJson@Details@Marshal@@YA_NAEAVJsonParser@2@PEAXAEBVUnmarshalContext@2@AEBUClassData@2@V?$ArrayView@PEBUBaseTypeData@Details@Marshal@@@12@V?$ArrayView@PEBUJsonTypeData@Details@Marshal@@@12@@Z`
- size: `1519`
- prototype: `char __fastcall(Marshal::JsonParser *this, __int64, __int64, __int64 **, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400045bc`

## callees

- `0x140002310`
- `0x140007af4`
- `0x140008230`
- `0x140008fec`
- `0x14000a714`
- `0x14000a7bc`
- `0x14000af70`
- `0x14000b3f4`
- `0x14000b8c8`
- `0x14000bc7c`
- `0x14000cd1c`
- `0x14000d224`
- `0x14000f3c0`
- `0x140024010`

## pseudocode

```c
char __fastcall Marshal::Details::ObjectFromJson(
        Marshal::JsonParser *this,
        __int64 a2,
        __int64 a3,
        __int64 **a4,
        _QWORD *a5,
        _QWORD *a6)
{
  __int64 **v6; // rbx
  __int64 v7; // r12
  Marshal::JsonParser *v8; // r13
  char v10; // r15
  __int64 v11; // rdx
  const wchar_t **v12; // rdi
  const wchar_t *v13; // rsi
  size_t v14; // rdi
  unsigned int *v15; // r15
  __int64 v16; // rbx
  unsigned int *v17; // r12
  __int64 *v18; // r14
  const wchar_t *v19; // r12
  unsigned int *v20; // rsi
  __int64 v21; // rcx
  __int64 v22; // rax
  const wchar_t *v23; // rdx
  __int64 v24; // rcx
  __int64 *v25; // r14
  int v26; // eax
  unsigned int v27; // eax
  __int64 v28; // rax
  const wchar_t *v29; // rdx
  size_t v30; // r8
  int v31; // eax
  __int64 v32; // rsi
  __int64 v33; // rbx
  __int64 *v34; // rdi
  unsigned __int64 v35; // r8
  int v36; // edx
  __int64 v37; // r15
  const wchar_t *v38; // rcx
  __int64 v39; // rax
  unsigned __int8 (__fastcall *v40)(Marshal::JsonParser *, __int64, void ***); // rax
  const wchar_t *v41; // r8
  __int64 v42; // rdx
  __int64 v43; // rdx
  __int64 v44; // rcx
  const wchar_t *v45; // rax
  unsigned __int64 v46; // rsi
  __int64 *v47; // rbx
  __int64 *v48; // rdi
  int v49; // ecx
  __int64 v50; // rdx
  __int64 v51; // rcx
  char v52; // [rsp+20h] [rbp-E0h]
  const wchar_t *v54; // [rsp+30h] [rbp-D0h]
  void **v56; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v57; // [rsp+48h] [rbp-B8h]
  __int64 v58; // [rsp+50h] [rbp-B0h]
  const wchar_t *v59; // [rsp+58h] [rbp-A8h]
  __int64 v60; // [rsp+60h] [rbp-A0h]
  size_t v61; // [rsp+68h] [rbp-98h]
  _QWORD *v62; // [rsp+70h] [rbp-90h]
  __int64 v63; // [rsp+78h] [rbp-88h]
  void **v64; // [rsp+80h] [rbp-80h] BYREF
  __int64 v65; // [rsp+88h] [rbp-78h]
  __int64 v66; // [rsp+90h] [rbp-70h]
  __int64 v67; // [rsp+98h] [rbp-68h]
  __int64 v68; // [rsp+A0h] [rbp-60h]
  unsigned int *v69; // [rsp+A8h] [rbp-58h]
  Marshal::JsonParser *v70; // [rsp+B0h] [rbp-50h]
  _QWORD *v71; // [rsp+B8h] [rbp-48h]
  _QWORD v72[2]; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD v73[2]; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v74[2]; // [rsp+E0h] [rbp-20h] BYREF
  _QWORD v75[2]; // [rsp+F0h] [rbp-10h] BYREF
  _QWORD v76[2]; // [rsp+100h] [rbp+0h] BYREF
  _QWORD v77[2]; // [rsp+110h] [rbp+10h] BYREF
  _OWORD v78[2]; // [rsp+140h] [rbp+40h] BYREF

  v6 = a4;
  v7 = a3;
  v63 = a2;
  v8 = this;
  v70 = this;
  v62 = a5;
  v71 = a6;
  if ( (unsigned int)((__int64 (*)(void))Marshal::JsonParser::PeekValueType)() != 3 )
  {
    Marshal::UnmarshalContext::ReportError(v7, 5);
    return 0;
  }
  v10 = 1;
  v52 = 1;
  memset(v78, 0, sizeof(v78));
  std::vector<bool>::vector<bool>(v78, *((unsigned int *)v6 + 4));
  if ( Marshal::JsonParser::BeginAggregate(v8, 123, 125, 9) )
  {
    Marshal::JsonParser::ParseObjectKey(v8);
    v12 = (const wchar_t **)((char *)v8 + 32);
    while ( 1 )
    {
      if ( *((_QWORD *)v8 + 7) <= 7u )
        v13 = (const wchar_t *)v12;
      else
        v13 = *v12;
      v54 = v13;
      v14 = *((_QWORD *)v8 + 6);
      v61 = v14;
      v15 = (unsigned int *)v6[1];
      v16 = *((unsigned int *)v6 + 4);
      v17 = &v15[v16];
      v69 = v17;
      if ( v16 )
      {
        v18 = *a4;
        v19 = v13;
        do
        {
          v20 = &v15[v16 / 2];
          v21 = v18[4 * *v20];
          v22 = -1;
          do
            ++v22;
          while ( *(_WORD *)(v21 + 2 * v22) );
          v72[0] = v19;
          v72[1] = v14;
          v73[0] = v21;
          v73[1] = v22;
          if ( (int)Marshal::Details::StringCompareCaseInsensitive(v73, v72) >= 0 )
          {
            v16 /= 2;
          }
          else
          {
            v15 = v20 + 1;
            v16 += -1 - v16 / 2;
          }
        }
        while ( v16 > 0 );
        v17 = v69;
        v8 = v70;
        v14 = v61;
        v13 = v54;
      }
      v6 = a4;
      if ( v15 == v17 )
      {
        v7 = a3;
      }
      else
      {
        v23 = (const wchar_t *)(*a4)[4 * *v15];
        v24 = -1;
        do
          ++v24;
        while ( v23[v24] );
        v7 = a3;
        if ( v14 == v24 )
        {
          v25 = (__int64 *)(a3 + 8);
          if ( (*(_BYTE *)(*(_QWORD *)(a3 + 8) + 24LL) & 2) != 0 )
          {
            v74[0] = (*a4)[4 * *v15];
            v74[1] = v24;
            v75[0] = v13;
            v75[1] = v14;
            v26 = Marshal::Details::StringCompareCaseInsensitive(v75, v74);
          }
          else
          {
            v26 = wmemcmp(v13, v23, v14);
          }
          if ( !v26 )
          {
            v27 = *v15;
            goto LABEL_37;
          }
        }
      }
      if ( v15 == (unsigned int *)a4[1] )
        goto LABEL_59;
      v28 = 4LL * *(v15 - 1);
      if ( ((*a4)[v28 + 1] & 0x1000000000LL) == 0 )
        goto LABEL_59;
      v29 = (const wchar_t *)(*a4)[v28];
      v30 = -1;
      do
        ++v30;
      while ( v29[v30] );
      if ( v14 < v30 )
        goto LABEL_59;
      v25 = (__int64 *)(v7 + 8);
      if ( (*(_BYTE *)(*(_QWORD *)(v7 + 8) + 24LL) & 2) != 0 )
      {
        v76[0] = (*a4)[v28];
        v76[1] = v30;
        v77[0] = v13;
        v77[1] = v30;
        v31 = Marshal::Details::StringCompareCaseInsensitive(v77, v76);
      }
      else
      {
        v31 = wmemcmp(v13, v29, v30);
      }
      if ( v31 )
      {
LABEL_59:
        v25 = (__int64 *)(v7 + 8);
LABEL_60:
        Marshal::JsonParser::SkipValue(v8);
        if ( (*(_BYTE *)(*v25 + 24) & 4) == 0 )
          goto LABEL_48;
        v12 = (const wchar_t **)((char *)v8 + 32);
        if ( *((_QWORD *)v8 + 7) <= 7u )
          v45 = (const wchar_t *)((char *)v8 + 32);
        else
          v45 = *v12;
        v57 = *v25;
        v58 = v7;
        v56 = &Marshal::Details::UnmarshalFieldContext::`vftable';
        v59 = v45;
        v60 = *((_QWORD *)v8 + 6);
        Marshal::UnmarshalContext::ReportError(&v56, 17);
LABEL_55:
        v10 = 0;
        v52 = 0;
        goto LABEL_50;
      }
      v27 = *(v15 - 1);
LABEL_37:
      if ( v27 >= *((_DWORD *)a4 + 4) )
        goto LABEL_60;
      v32 = v27;
      v33 = 4LL * v27;
      v34 = *a4;
      v35 = (unsigned __int64)v27 >> 5;
      v36 = *(_DWORD *)(*(_QWORD *)&v78[0] + 4 * v35);
      if ( (v36 & (1 << v27)) != 0 )
      {
        v43 = v34[v33];
        v44 = -1;
        do
          ++v44;
        while ( *(_WORD *)(v43 + 2 * v44) );
        v65 = *(_QWORD *)(v7 + 8);
        v66 = v7;
        v64 = &Marshal::Details::UnmarshalFieldContext::`vftable';
        v67 = v43;
        v68 = v44;
        Marshal::UnmarshalContext::ReportError(&v64, 16);
        Marshal::JsonParser::SkipValue(v8);
LABEL_46:
        v10 = 0;
        v52 = 0;
        v6 = a4;
        goto LABEL_49;
      }
      v37 = v63 + LODWORD(v34[v33 + 1]);
      *(_DWORD *)(*(_QWORD *)&v78[0] + 4 * v35) = (1 << v27) | v36;
      if ( (unsigned int)Marshal::JsonParser::PeekValueType(v8) == 5 && (v34[v33 + 1] & 0x2000000000LL) == 0 )
      {
        Marshal::JsonParser::ParseNull(v8);
        if ( (v34[v33 + 1] & 0x200000000LL) != 0 && (*(_BYTE *)(*(_QWORD *)(v7 + 8) + 24LL) & 8) == 0 )
        {
          v38 = (const wchar_t *)v34[v33];
          v39 = -1;
          do
            ++v39;
          while ( v38[v39] );
          v57 = *(_QWORD *)(v7 + 8);
          v58 = v7;
          v56 = &Marshal::Details::UnmarshalFieldContext::`vftable';
          v59 = v38;
          v60 = v39;
          Marshal::UnmarshalContext::ReportError(&v56, 11);
          goto LABEL_46;
        }
        _mm_lfence();
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)(*v62 + 8 * v32) + 8LL))(v37, v34[v33 + 2]);
        v6 = a4;
LABEL_48:
        v10 = v52;
LABEL_49:
        v12 = (const wchar_t **)((char *)v8 + 32);
        goto LABEL_50;
      }
      _mm_lfence();
      v40 = *(unsigned __int8 (__fastcall **)(Marshal::JsonParser *, __int64, void ***))(*(_QWORD *)(*v71 + 8 * v32)
                                                                                       + 8LL);
      v41 = (const wchar_t *)v34[v33];
      v42 = -1;
      do
        ++v42;
      while ( v41[v42] );
      v57 = *(_QWORD *)(v7 + 8);
      v58 = v7;
      v56 = &Marshal::Details::UnmarshalFieldContext::`vftable';
      v59 = v41;
      v60 = v42;
      v6 = a4;
      v12 = (const wchar_t **)((char *)v8 + 32);
      if ( !v40(v8, v37, &v56) )
        goto LABEL_55;
      v10 = v52;
LABEL_50:
      if ( !Marshal::JsonParser::NextElement(v8, 125, 10) )
        goto LABEL_67;
      Marshal::JsonParser::ParseObjectKey(v8);
    }
  }
  v25 = (__int64 *)(v7 + 8);
LABEL_67:
  if ( (*(_BYTE *)(*v25 + 24) & 8) == 0 )
  {
    v46 = 0;
    v47 = *v6;
    v48 = &v47[4 * *((unsigned int *)a4 + 4)];
    while ( v47 != v48 )
    {
      v11 = v46 & 0x1F;
      v49 = *(_DWORD *)(*(_QWORD *)&v78[0] + 4 * (v46 >> 5));
      if ( !_bittest(&v49, v11) )
      {
        if ( (*((_BYTE *)v47 + 12) & 2) != 0 )
        {
          v50 = *v47;
          v51 = -1;
          do
            ++v51;
          while ( *(_WORD *)(v50 + 2 * v51) );
          v65 = *v25;
          v66 = v7;
          v64 = &Marshal::Details::UnmarshalFieldContext::`vftable';
          v67 = v50;
          v68 = v51;
          Marshal::UnmarshalContext::ReportError(&v64, 11);
          v10 = 0;
        }
        else
        {
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)(*v62 + 8 * v46) + 8LL))(
            v63 + *((unsigned int *)v47 + 2),
            v47[2]);
        }
      }
      ++v46;
      v47 += 4;
    }
  }
  std::vector<unsigned int>::~vector<unsigned int>(v78, v11, 0, &Marshal::Details::UnmarshalFieldContext::`vftable');
  return v10;
}

```

## disassembly

```asm
0x14000a7bc  push    rbp
0x14000a7be  push    rbx
0x14000a7bf  push    rsi
0x14000a7c0  push    rdi
0x14000a7c1  push    r12
0x14000a7c3  push    r13
0x14000a7c5  push    r14
0x14000a7c7  push    r15
0x14000a7c9  lea     rbp, [rsp-78h]
0x14000a7ce  sub     rsp, 178h
0x14000a7d5  mov     rax, cs:__security_cookie
0x14000a7dc  xor     rax, rsp
0x14000a7df  mov     [rbp+0B0h+var_50], rax
0x14000a7e3  mov     rbx, r9
0x14000a7e6  mov     [rsp+1B0h+var_188], rbx
0x14000a7eb  mov     r12, r8
0x14000a7ee  mov     [rsp+1B0h+var_178], r8
0x14000a7f3  mov     [rsp+1B0h+var_138], rdx
0x14000a7f8  mov     r13, rcx
0x14000a7fb  mov     [rbp+0B0h+var_100], rcx
0x14000a7ff  mov     rax, [rbp+0B0h+arg_20]
0x14000a806  mov     [rsp+1B0h+var_140], rax
0x14000a80b  mov     rax, [rbp+0B0h+arg_28]
0x14000a812  mov     [rbp+0B0h+var_F8], rax
0x14000a816  call    ?PeekValueType@JsonParser@Marshal@@QEAA?AW4ValueType@12@XZ; Marshal::JsonParser::PeekValueType(void)
0x14000a81b  cmp     eax, 3
0x14000a81e  jz      short loc_14000A834
0x14000a820  mov     edx, 5
0x14000a825  mov     rcx, r12
0x14000a828  call    ?ReportError@UnmarshalContext@Marshal@@QEBAXW4UnmarshalError@2@@Z; Marshal::UnmarshalContext::ReportError(Marshal::UnmarshalError)
0x14000a82d  xor     al, al
0x14000a82f  jmp     loc_14000AD8B
0x14000a834  mov     r15b, 1
0x14000a837  mov     [rsp+1B0h+var_190], r15b
0x14000a83c  xorps   xmm0, xmm0
0x14000a83f  movups  [rbp+0B0h+var_70], xmm0
0x14000a843  movups  [rbp+0B0h+var_60], xmm0
0x14000a847  mov     edx, [rbx+10h]
0x14000a84a  lea     rcx, [rbp+0B0h+var_70]
0x14000a84e  call    ??0?$vector@_NV?$allocator@_N@std@@@std@@QEAA@_KAEBV?$allocator@_N@1@@Z; std::vector<bool>::vector<bool>(unsigned __int64,std::allocator<bool> const &)
0x14000a853  nop
0x14000a854  mov     r9d, 9
0x14000a85a  mov     r8b, 7Dh ; '}'
0x14000a85d  mov     dl, 7Bh ; '{'
0x14000a85f  mov     rcx, r13
0x14000a862  call    ?BeginAggregate@JsonParser@Marshal@@AEAA_NDDW4ParseError@12@@Z; Marshal::JsonParser::BeginAggregate(char,char,Marshal::JsonParser::ParseError)
0x14000a867  lea     r9, ??_7UnmarshalFieldContext@Details@Marshal@@6B@; const Marshal::Details::UnmarshalFieldContext::`vftable'
0x14000a86e  xor     r8d, r8d
0x14000a871  test    al, al
0x14000a873  jz      loc_14000ACB0
0x14000a879  mov     rcx, r13; this
0x14000a87c  call    ?ParseObjectKey@JsonParser@Marshal@@AEAAXXZ; Marshal::JsonParser::ParseObjectKey(void)
0x14000a881  lea     rdi, [r13+20h]
0x14000a885  cmp     qword ptr [r13+38h], 7
0x14000a88a  jbe     short loc_14000A891
0x14000a88c  mov     rsi, [rdi]
0x14000a88f  jmp     short loc_14000A894
0x14000a891  mov     rsi, rdi
0x14000a894  mov     [rsp+1B0h+var_180], rsi
0x14000a899  mov     rdi, [r13+30h]
0x14000a89d  mov     [rsp+1B0h+var_148], rdi
0x14000a8a2  mov     r15, [rbx+8]
0x14000a8a6  mov     ebx, [rbx+10h]
0x14000a8a9  lea     r12, [r15+rbx*4]
0x14000a8ad  mov     [rbp+0B0h+var_108], r12
0x14000a8b1  xor     r11d, r11d
0x14000a8b4  test    rbx, rbx
0x14000a8b7  jz      loc_14000A944
0x14000a8bd  mov     rax, [rsp+1B0h+var_188]
0x14000a8c2  mov     r14, [rax]
0x14000a8c5  mov     r13, rdi
0x14000a8c8  mov     r12, rsi
0x14000a8cb  mov     rdi, rbx
0x14000a8ce  test    rbx, rbx
0x14000a8d1  jns     short loc_14000A8D7
0x14000a8d3  lea     rdi, [rbx+1]
0x14000a8d7  sar     rdi, 1
0x14000a8da  lea     rsi, [r15+rdi*4]
0x14000a8de  mov     eax, [rsi]
0x14000a8e0  shl     rax, 5
0x14000a8e4  mov     rcx, [rax+r14]
0x14000a8e8  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000a8ec  inc     rax
0x14000a8ef  cmp     [rcx+rax*2], r11w
0x14000a8f4  jnz     short loc_14000A8EC
0x14000a8f6  mov     [rbp+0B0h+var_F0], r12
0x14000a8fa  mov     [rbp+0B0h+var_E8], r13
0x14000a8fe  mov     [rbp+0B0h+var_E0], rcx
0x14000a902  mov     [rbp+0B0h+var_D8], rax
0x14000a906  lea     rdx, [rbp+0B0h+var_F0]
0x14000a90a  lea     rcx, [rbp+0B0h+var_E0]
0x14000a90e  call    ?StringCompareCaseInsensitive@Details@Marshal@@YAHV?$basic_string_view@GU?$char_traits@G@std@@@std@@0@Z; Marshal::Details::StringCompareCaseInsensitive(std::basic_string_view<ushort>,std::basic_string_view<ushort>)
0x14000a913  xor     r11d, r11d
0x14000a916  test    eax, eax
0x14000a918  jns     short loc_14000A92A
0x14000a91a  lea     r15, [rsi+4]
0x14000a91e  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000a922  sub     rax, rdi
0x14000a925  add     rbx, rax
0x14000a928  jmp     short loc_14000A92D
0x14000a92a  mov     rbx, rdi
0x14000a92d  test    rbx, rbx
0x14000a930  jg      short loc_14000A8CB
0x14000a932  mov     r12, [rbp+0B0h+var_108]
0x14000a936  mov     r13, [rbp+0B0h+var_100]
0x14000a93a  mov     rdi, [rsp+1B0h+var_148]
0x14000a93f  mov     rsi, [rsp+1B0h+var_180]
0x14000a944  mov     rbx, [rsp+1B0h+var_188]
0x14000a949  cmp     r15, r12
0x14000a94c  jz      short loc_14000A9BB
0x14000a94e  mov     ecx, [r15]
0x14000a951  shl     rcx, 5
0x14000a955  mov     rax, [rbx]
0x14000a958  mov     rdx, [rcx+rax]; S2
0x14000a95c  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14000a960  inc     rcx
0x14000a963  cmp     [rdx+rcx*2], r11w
0x14000a968  jnz     short loc_14000A960
0x14000a96a  mov     r12, [rsp+1B0h+var_178]
0x14000a96f  cmp     rdi, rcx
0x14000a972  jnz     short loc_14000A9C0
0x14000a974  lea     r14, [r12+8]
0x14000a979  mov     rax, [r14]
0x14000a97c  test    byte ptr [rax+18h], 2
0x14000a980  jz      short loc_14000A9A1
0x14000a982  mov     [rbp+0B0h+var_D0], rdx
0x14000a986  mov     [rbp+0B0h+var_C8], rcx
0x14000a98a  mov     [rbp+0B0h+var_C0], rsi
0x14000a98e  mov     [rbp+0B0h+var_B8], rdi
0x14000a992  lea     rdx, [rbp+0B0h+var_D0]
0x14000a996  lea     rcx, [rbp+0B0h+var_C0]
0x14000a99a  call    ?StringCompareCaseInsensitive@Details@Marshal@@YAHV?$basic_string_view@GU?$char_traits@G@std@@@std@@0@Z; Marshal::Details::StringCompareCaseInsensitive(std::basic_string_view<ushort>,std::basic_string_view<ushort>)
0x14000a99f  jmp     short loc_14000A9AC
0x14000a9a1  mov     r8, rdi; N
0x14000a9a4  mov     rcx, rsi; S1
0x14000a9a7  call    wmemcmp
0x14000a9ac  xor     r11d, r11d
0x14000a9af  test    eax, eax
0x14000a9b1  jnz     short loc_14000A9C0
0x14000a9b3  mov     eax, [r15]
0x14000a9b6  jmp     loc_14000AA44
0x14000a9bb  mov     r12, [rsp+1B0h+var_178]
0x14000a9c0  cmp     r15, [rbx+8]
0x14000a9c4  jz      loc_14000AC3B
0x14000a9ca  mov     eax, [r15-4]
0x14000a9ce  shl     rax, 5
0x14000a9d2  mov     rcx, [rbx]
0x14000a9d5  test    byte ptr [rax+rcx+0Ch], 10h
0x14000a9da  jz      loc_14000AC3B
0x14000a9e0  mov     rdx, [rax+rcx]; S2
0x14000a9e4  or      r8, 0FFFFFFFFFFFFFFFFh
0x14000a9e8  inc     r8; N
0x14000a9eb  cmp     [rdx+r8*2], r11w
0x14000a9f0  jnz     short loc_14000A9E8
0x14000a9f2  cmp     rdi, r8
0x14000a9f5  jb      loc_14000AC3B
0x14000a9fb  lea     r14, [r12+8]
0x14000aa00  mov     rax, [r14]
0x14000aa03  test    byte ptr [rax+18h], 2
0x14000aa07  jz      short loc_14000AA28
0x14000aa09  mov     [rbp+0B0h+var_B0], rdx
0x14000aa0d  mov     [rbp+0B0h+var_A8], r8
0x14000aa11  mov     [rbp+0B0h+var_A0], rsi
0x14000aa15  mov     [rbp+0B0h+var_98], r8
0x14000aa19  lea     rdx, [rbp+0B0h+var_B0]
0x14000aa1d  lea     rcx, [rbp+0B0h+var_A0]
0x14000aa21  call    ?StringCompareCaseInsensitive@Details@Marshal@@YAHV?$basic_string_view@GU?$char_traits@G@std@@@std@@0@Z; Marshal::Details::StringCompareCaseInsensitive(std::basic_string_view<ushort>,std::basic_string_view<ushort>)
0x14000aa26  jmp     short loc_14000AA30
0x14000aa28  mov     rcx, rsi; S1
0x14000aa2b  call    wmemcmp
0x14000aa30  xor     r11d, r11d
0x14000aa33  test    eax, eax
0x14000aa35  setz    al
0x14000aa38  test    al, al
0x14000aa3a  jz      loc_14000AC3B
0x14000aa40  mov     eax, [r15-4]
0x14000aa44  cmp     eax, [rbx+10h]
0x14000aa47  jnb     loc_14000AC40
0x14000aa4d  mov     esi, eax
0x14000aa4f  mov     ebx, eax
0x14000aa51  shl     rbx, 5
0x14000aa55  mov     rax, [rsp+1B0h+var_188]
0x14000aa5a  mov     rdi, [rax]
0x14000aa5d  mov     r8d, esi
0x14000aa60  shr     r8, 5
0x14000aa64  mov     r10, qword ptr [rbp+0B0h+var_70]
0x14000aa68  mov     edx, [r10+r8*4]
0x14000aa6c  mov     cl, sil
0x14000aa6f  mov     r9d, 1
0x14000aa75  shl     r9d, cl
0x14000aa78  test    r9d, edx
0x14000aa7b  jnz     loc_14000ABE8
0x14000aa81  mov     r15d, [rbx+rdi+8]
0x14000aa86  add     r15, [rsp+1B0h+var_138]
0x14000aa8b  or      edx, r9d
0x14000aa8e  mov     [r10+r8*4], edx
0x14000aa92  mov     rcx, r13
0x14000aa95  call    ?PeekValueType@JsonParser@Marshal@@QEAA?AW4ValueType@12@XZ; Marshal::JsonParser::PeekValueType(void)
0x14000aa9a  cmp     eax, 5
0x14000aa9d  jnz     loc_14000AB6F
0x14000aaa3  test    byte ptr [rbx+rdi+0Ch], 20h
0x14000aaa8  jnz     loc_14000AB6F
0x14000aaae  mov     rcx, r13; this
0x14000aab1  call    ?ParseNull@JsonParser@Marshal@@QEAAXXZ; Marshal::JsonParser::ParseNull(void)
0x14000aab6  test    byte ptr [rbx+rdi+0Ch], 2
0x14000aabb  jz      short loc_14000AB19
0x14000aabd  mov     rdx, [r12+8]
0x14000aac2  test    byte ptr [rdx+18h], 8
0x14000aac6  jnz     short loc_14000AB19
0x14000aac8  mov     rcx, [rbx+rdi]
0x14000aacc  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000aad0  xor     esi, esi
0x14000aad2  inc     rax
0x14000aad5  cmp     [rcx+rax*2], si
0x14000aad9  jnz     short loc_14000AAD2
0x14000aadb  mov     [rsp+1B0h+var_168], rdx
0x14000aae0  mov     [rsp+1B0h+var_160], r12
0x14000aae5  lea     rdx, ??_7UnmarshalFieldContext@Details@Marshal@@6B@; const Marshal::Details::UnmarshalFieldContext::`vftable'
0x14000aaec  mov     [rsp+1B0h+var_170], rdx
0x14000aaf1  mov     [rsp+1B0h+var_158], rcx
0x14000aaf6  mov     [rsp+1B0h+var_150], rax
0x14000aafb  mov     edx, 0Bh
0x14000ab00  lea     rcx, [rsp+1B0h+var_170]
0x14000ab05  call    ?ReportError@UnmarshalContext@Marshal@@QEBAXW4UnmarshalError@2@@Z; Marshal::UnmarshalContext::ReportError(Marshal::UnmarshalError)
0x14000ab0a  mov     r15b, sil
0x14000ab0d  mov     [rsp+1B0h+var_190], sil
0x14000ab12  mov     rbx, [rsp+1B0h+var_188]
0x14000ab17  jmp     short loc_14000AB43
0x14000ab19  lfence
0x14000ab1c  mov     rax, [rsp+1B0h+var_140]
0x14000ab21  mov     rax, [rax]
0x14000ab24  mov     rdx, [rax+rsi*8]
0x14000ab28  mov     rax, [rdx+8]
0x14000ab2c  mov     rdx, [rbx+rdi+10h]
0x14000ab31  mov     rcx, r15
0x14000ab34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ab39  mov     rbx, [rsp+1B0h+var_188]
0x14000ab3e  mov     r15b, [rsp+1B0h+var_190]
0x14000ab43  lea     rdi, [r13+20h]
0x14000ab47  mov     r8d, 0Ah
0x14000ab4d  mov     dl, 7Dh ; '}'
0x14000ab4f  mov     rcx, r13
0x14000ab52  call    ?NextElement@JsonParser@Marshal@@AEAA_NDW4ParseError@12@@Z; Marshal::JsonParser::NextElement(char,Marshal::JsonParser::ParseError)
0x14000ab57  xor     r8d, r8d
0x14000ab5a  test    al, al
0x14000ab5c  jz      loc_14000ACB7
0x14000ab62  mov     rcx, r13; this
0x14000ab65  call    ?ParseObjectKey@JsonParser@Marshal@@AEAAXXZ; Marshal::JsonParser::ParseObjectKey(void)
0x14000ab6a  jmp     loc_14000A885
0x14000ab6f  lfence
0x14000ab72  mov     rax, [rbp+0B0h+var_F8]
0x14000ab76  mov     rax, [rax]
0x14000ab79  mov     rcx, [rax+rsi*8]
0x14000ab7d  mov     rax, [rcx+8]
0x14000ab81  mov     r8, [rbx+rdi]
0x14000ab85  or      rdx, 0FFFFFFFFFFFFFFFFh
0x14000ab89  xor     esi, esi
0x14000ab8b  inc     rdx
0x14000ab8e  cmp     [r8+rdx*2], si
0x14000ab93  jnz     short loc_14000AB8B
0x14000ab95  mov     rcx, [r12+8]
0x14000ab9a  mov     [rsp+1B0h+var_168], rcx
0x14000ab9f  mov     [rsp+1B0h+var_160], r12
0x14000aba4  lea     rcx, ??_7UnmarshalFieldContext@Details@Marshal@@6B@; const Marshal::Details::UnmarshalFieldContext::`vftable'
0x14000abab  mov     [rsp+1B0h+var_170], rcx
0x14000abb0  mov     [rsp+1B0h+var_158], r8
0x14000abb5  mov     [rsp+1B0h+var_150], rdx
0x14000abba  lea     r8, [rsp+1B0h+var_170]
0x14000abbf  mov     rdx, r15
0x14000abc2  mov     rcx, r13
0x14000abc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000abca  mov     rbx, [rsp+1B0h+var_188]
0x14000abcf  lea     rdi, [r13+20h]
0x14000abd3  test    al, al
0x14000abd5  jnz     loc_14000ACA6
0x14000abdb  mov     r15b, sil
0x14000abde  mov     [rsp+1B0h+var_190], sil
0x14000abe3  jmp     loc_14000AB47
0x14000abe8  mov     rdx, [rbx+rdi]
0x14000abec  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14000abf0  inc     rcx
0x14000abf3  cmp     [rdx+rcx*2], r11w
0x14000abf8  jnz     short loc_14000ABF0
0x14000abfa  mov     rax, [r12+8]
0x14000abff  mov     [rbp+0B0h+var_128], rax
0x14000ac03  mov     [rbp+0B0h+var_120], r12
0x14000ac07  lea     rax, ??_7UnmarshalFieldContext@Details@Marshal@@6B@; const Marshal::Details::UnmarshalFieldContext::`vftable'
0x14000ac0e  mov     [rbp+0B0h+var_130], rax
0x14000ac12  mov     [rbp+0B0h+var_118], rdx
0x14000ac16  mov     [rbp+0B0h+var_110], rcx
0x14000ac1a  mov     edx, 10h
0x14000ac1f  lea     rcx, [rbp+0B0h+var_130]
0x14000ac23  call    ?ReportError@UnmarshalContext@Marshal@@QEBAXW4UnmarshalError@2@@Z; Marshal::UnmarshalContext::ReportError(Marshal::UnmarshalError)
0x14000ac28  lea     rdx, [rbp+0B0h+var_90]
0x14000ac2c  mov     rcx, r13; this
0x14000ac2f  call    ?SkipValue@JsonParser@Marshal@@QEAA?AV?$basic_string_view@GU?$char_traits@G@std@@@std@@XZ; Marshal::JsonParser::SkipValue(void)
0x14000ac34  xor     esi, esi
0x14000ac36  jmp     loc_14000AB0A
0x14000ac3b  lea     r14, [r12+8]
0x14000ac40  lea     rdx, [rbp+0B0h+var_80]
  ... truncated ...
```
