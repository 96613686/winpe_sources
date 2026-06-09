# Mso::SVG::StylableRenderer::ComputeFont(Mso::SVG::StyleResolveChain const &,GEL::Font &)

- ea: `0x180040864`
- end: `0x180040c37`
- name: `?ComputeFont@StylableRenderer@SVG@Mso@@QEBAXAEBVStyleResolveChain@23@AEAUFont@GEL@@@Z`
- size: `979`
- prototype: `void __fastcall(Mso::SVG::StylableRenderer *__hidden this, const struct Mso::SVG::StyleResolveChain *, struct GEL::Font *)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180131598`
- `0x18013215c`

## callees

- `0x18000d378`
- `0x18000d468`
- `0x1800171a4`
- `0x18001acfc`
- `0x18001ad58`
- `0x18001adb4`
- `0x18001cf98`
- `0x18001cff0`
- `0x18001d048`
- `0x180040864`
- `0x18013f760`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800409e9`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180040c30`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800409e9`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180040c30`
- `gfx!?GetConfig@Immediate@Gfx@@YAAEBVConfig@2@XZ` at `0x180040bde`
- `gfx!?GetConfig@Immediate@Gfx@@YAAEBVConfig@2@XZ` at `0x180040bde`
- `gfx!?GetDefaultTypefaces@ITypefaceList@GEL@@SAAEAU12@XZ` at `0x1800409bc`
- `gfx!?GetDefaultTypefaces@ITypefaceList@GEL@@SAAEAU12@XZ` at `0x180040a61`
- `gfx!?GetDefaultTypefaces@ITypefaceList@GEL@@SAAEAU12@XZ` at `0x180040b3d`
- `gfx!?GetDefaultTypefaces@ITypefaceList@GEL@@SAAEAU12@XZ` at `0x1800409bc`
- `gfx!?GetDefaultTypefaces@ITypefaceList@GEL@@SAAEAU12@XZ` at `0x180040a61`
- `gfx!?GetDefaultTypefaces@ITypefaceList@GEL@@SAAEAU12@XZ` at `0x180040b3d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Mso::SVG::StylableRenderer::ComputeFont(
        Mso::SVG::StylableRenderer *this,
        const struct Mso::SVG::StyleResolveChain *a2,
        struct GEL::Font *a3)
{
  __int64 v5; // rdx
  __int64 v6; // rsi
  __int128 *v7; // rsi
  __int64 v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rax
  __int64 *v11; // rax
  int v12; // r12d
  __int64 v13; // rdx
  __int64 v14; // rax
  __int64 *v15; // rax
  int v16; // r13d
  double v17; // xmm6_8
  __int64 DefaultTypefaces; // rax
  __int64 v19; // r9
  _QWORD *v20; // r8
  unsigned int v21; // r15d
  Mso::SVG::StylableRenderer **v22; // rax
  Mso::SVG::StylableRenderer *v23; // rbx
  __int64 v24; // rax
  Mso::SVG::StylableRenderer *i; // rcx
  __int64 v26; // rdi
  __int64 v27; // rax
  __int64 v28; // r9
  _QWORD *v29; // r8
  Mso::SVG::StylableRenderer **v30; // rax
  Mso::SVG::StylableRenderer *v31; // rdi
  __int64 v32; // rax
  __int64 v33; // r9
  Mso::SVG::StylableRenderer **v34; // rax
  float v35; // xmm0_4
  Gfx::Immediate *v36; // rcx
  int Reserved; // [rsp+20h] [rbp-30h]
  char Reserveda; // [rsp+20h] [rbp-30h]
  Mso::SVG::StylableRenderer *v39; // [rsp+90h] [rbp+40h] BYREF
  __int64 v40; // [rsp+98h] [rbp+48h] BYREF

  v39 = this;
  v5 = *((_QWORD *)a2 + 1);
  v6 = *(_QWORD *)(v5 + 16);
  if ( v6 )
  {
    v7 = (__int128 *)(v6 + 768);
  }
  else
  {
    v7 = &Mso::SVG::StyleMetaData<17>::initial;
    if ( *(_QWORD *)(v5 + 8) )
      v7 = &Mso::SVG::StyleMetaData<17>::inherit;
  }
  if ( !*((_BYTE *)v7 + 24) )
  {
    if ( *(_QWORD *)a2 )
      v8 = Mso::SVG::StyleResolveChain::Get<17>();
    else
      v8 = Mso::SVG::StyleResolveChain::GetNormal<17>(a2, *(_QWORD *)(v5 + 8));
    v7 = (__int128 *)v8;
  }
  v9 = *((_QWORD *)a2 + 1);
  v10 = *(_QWORD *)(v9 + 16);
  if ( v10 )
  {
    v11 = (__int64 *)(v10 + 752);
  }
  else
  {
    v11 = &Mso::SVG::StyleMetaData<18>::initial;
    if ( *(_QWORD *)(v9 + 8) )
      v11 = (__int64 *)&Mso::SVG::StyleMetaData<18>::inherit;
  }
  if ( !*((_BYTE *)v11 + 4) )
  {
    if ( *(_QWORD *)a2 )
      v11 = (__int64 *)Mso::SVG::StyleResolveChain::Get<18>(*(_QWORD *)a2);
    else
      v11 = (__int64 *)Mso::SVG::StyleResolveChain::GetNormal<18>(a2, *(_QWORD *)(v9 + 8));
  }
  v12 = *(_DWORD *)v11;
  v13 = *((_QWORD *)a2 + 1);
  v14 = *(_QWORD *)(v13 + 16);
  if ( v14 )
  {
    v15 = (__int64 *)(v14 + 736);
  }
  else
  {
    v15 = &Mso::SVG::StyleMetaData<19>::initial;
    if ( *(_QWORD *)(v13 + 8) )
      v15 = (__int64 *)&Mso::SVG::StyleMetaData<19>::inherit;
  }
  if ( !*((_BYTE *)v15 + 4) )
  {
    if ( *(_QWORD *)a2 )
      Mso::SVG::StyleResolveChain::Get<19>();
    else
      Mso::SVG::StyleResolveChain::GetNormal<19>(a2, *(_QWORD *)(v13 + 8));
  }
  v16 = Mso::SVG::StyleResolveChain::SpecialResolver<20,Mso::SVG::FontWeight>::operator()(&v39, a2, *((_QWORD *)a2 + 1));
  Mso::SVG::StyleResolveChain::SpecialResolver<21,enum Mso::SVG::FontStretch>::operator()(&v39, a2, *((_QWORD *)a2 + 1));
  v17 = Mso::SVG::StyleResolveChain::Get<22>(a2);
  v39 = 0;
  if ( *(_QWORD *)v7 != *((_QWORD *)v7 + 1) )
  {
    DefaultTypefaces = GEL::ITypefaceList::GetDefaultTypefaces();
    v20 = *(_QWORD **)v7;
    if ( !((__int64)(*((_QWORD *)v7 + 1) - *(_QWORD *)v7) >> 5) )
      _invoke_watson(0, 0, 0, 0, 0);
    v21 = 1;
    if ( v20[3] > 7u )
      v20 = (_QWORD *)*v20;
    Reserveda = 0;
    LOBYTE(v19) = 1;
    v22 = (Mso::SVG::StylableRenderer **)(*(__int64 (__fastcall **)(__int64, __int64 *, _QWORD *, __int64, char, _QWORD))(*(_QWORD *)DefaultTypefaces + 16LL))(
                                           DefaultTypefaces,
                                           &v40,
                                           v20,
                                           v19,
                                           Reserveda,
                                           0);
    v23 = *v22;
    *v22 = 0;
    v39 = v23;
    if ( v40 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 8LL))(v40);
    v24 = *(_QWORD *)v23;
    for ( i = v23; !(*(unsigned __int8 (__fastcall **)(Mso::SVG::StylableRenderer *))(v24 + 32))(i); i = v31 )
    {
      v26 = v21;
      if ( v21 >= (unsigned __int64)((__int64)(*((_QWORD *)v7 + 1) - *(_QWORD *)v7) >> 5) )
        break;
      v27 = GEL::ITypefaceList::GetDefaultTypefaces();
      if ( v21 >= (unsigned __int64)((__int64)(*((_QWORD *)v7 + 1) - *(_QWORD *)v7) >> 5) )
        _invoke_watson(0, 0, 0, 0, 0);
      ++v21;
      v29 = (_QWORD *)(32 * v26 + *(_QWORD *)v7);
      if ( v29[3] > 7u )
        v29 = (_QWORD *)*v29;
      LOBYTE(Reserved) = 0;
      LOBYTE(v28) = 1;
      v30 = (Mso::SVG::StylableRenderer **)(*(__int64 (__fastcall **)(__int64, __int64 *, _QWORD *, __int64, int, _QWORD))(*(_QWORD *)v27 + 16LL))(
                                             v27,
                                             &v40,
                                             v29,
                                             v28,
                                             Reserved,
                                             0);
      v31 = *v30;
      *v30 = 0;
      (*(void (__fastcall **)(Mso::SVG::StylableRenderer *))(*(_QWORD *)v23 + 8LL))(v23);
      v23 = v31;
      v39 = v31;
      if ( v40 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 8LL))(v40);
      v24 = *(_QWORD *)v31;
    }
    if ( !(*(unsigned __int8 (__fastcall **)(Mso::SVG::StylableRenderer *))(*(_QWORD *)v23 + 32LL))(v23) )
    {
      (*(void (__fastcall **)(Mso::SVG::StylableRenderer *))(*(_QWORD *)v23 + 8LL))(v23);
      v23 = 0;
      v39 = 0;
    }
    if ( v23 )
      goto LABEL_48;
  }
  v32 = GEL::ITypefaceList::GetDefaultTypefaces();
  LOBYTE(Reserved) = 0;
  LOBYTE(v33) = 1;
  v34 = (Mso::SVG::StylableRenderer **)(*(__int64 (__fastcall **)(__int64, __int64 *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)v32 + 16LL))(
                                         v32,
                                         &v40,
                                         L"Arial",
                                         v33,
                                         Reserved,
                                         0);
  v23 = *v34;
  *v34 = 0;
  if ( v40 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 8LL))(v40);
  if ( v23 )
LABEL_48:
    (**(void (__fastcall ***)(Mso::SVG::StylableRenderer *))v23)(v23);
  if ( *(_QWORD *)a3 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)a3 + 8LL))(*(_QWORD *)a3);
  *(_QWORD *)a3 = v23;
  v35 = v17;
  *((float *)a3 + 4) = v35;
  v36 = (Gfx::Immediate *)((v12 != 0 ? 2 : 0) | (unsigned int)(v16 >= 600));
  *((_DWORD *)a3 + 5) = (_DWORD)v36;
  *((_BYTE *)a3 + 33) = *((_BYTE *)Gfx::Immediate::GetConfig(v36) + 62);
  if ( v23 )
    (*(void (__fastcall **)(Mso::SVG::StylableRenderer *))(*(_QWORD *)v23 + 8LL))(v23);
}

```

## disassembly

```asm
0x180040864  mov     [rsp-38h+arg_10], rbx
0x180040869  mov     [rsp-38h+arg_0], rcx
0x18004086e  push    rbp
0x18004086f  push    rsi
0x180040870  push    rdi
0x180040871  push    r12
0x180040873  push    r13
0x180040875  push    r14
0x180040877  push    r15
0x180040879  mov     rbp, rsp
0x18004087c  sub     rsp, 50h
0x180040880  movaps  [rsp+50h+var_10], xmm6
0x180040885  mov     r14, r8
0x180040888  mov     rdi, rdx
0x18004088b  mov     rdx, [rdx+8]
0x18004088f  mov     rsi, [rdx+10h]
0x180040893  xor     r15d, r15d
0x180040896  test    rsi, rsi
0x180040899  jz      short loc_1800408A4
0x18004089b  add     rsi, 300h
0x1800408a2  jmp     short loc_1800408B8
0x1800408a4  cmp     [rdx+8], r15
0x1800408a8  lea     rsi, ?initial@?$StyleMetaData@$0BB@@SVG@Mso@@2V?$optional@V?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@@std@@B; std::optional<std::vector<std::wstring>> const Mso::SVG::StyleMetaData<17>::initial
0x1800408af  jz      short loc_1800408B8
0x1800408b1  lea     rsi, ?inherit@?$StyleMetaData@$0BB@@SVG@Mso@@2V?$optional@V?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@@std@@B; std::optional<std::vector<std::wstring>> const Mso::SVG::StyleMetaData<17>::inherit
0x1800408b8  mov     ebx, 8
0x1800408bd  mov     eax, ebx
0x1800408bf  cmp     [rsi+18h], r15b
0x1800408c3  jnz     short loc_1800408E3
0x1800408c5  mov     rcx, [rdi]
0x1800408c8  test    rcx, rcx
0x1800408cb  jz      short loc_1800408D4
0x1800408cd  call    ??$Get@$0BB@@StyleResolveChain@SVG@Mso@@QEBAAEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@XZ; Mso::SVG::StyleResolveChain::Get<17>(void)
0x1800408d2  jmp     short loc_1800408E0
0x1800408d4  mov     rdx, [rax+rdx]
0x1800408d8  mov     rcx, rdi
0x1800408db  call    ??$GetNormal@$0BB@@StyleResolveChain@SVG@Mso@@AEBAAEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEBVStyle@12@@Z; Mso::SVG::StyleResolveChain::GetNormal<17>(Mso::SVG::Style const &)
0x1800408e0  mov     rsi, rax
0x1800408e3  mov     rdx, [rdi+8]
0x1800408e7  mov     rax, [rdx+10h]
0x1800408eb  test    rax, rax
0x1800408ee  jz      short loc_1800408F8
0x1800408f0  add     rax, 2F0h
0x1800408f6  jmp     short loc_18004090C
0x1800408f8  cmp     [rdx+8], r15
0x1800408fc  lea     rax, ?initial@?$StyleMetaData@$0BC@@SVG@Mso@@2V?$optional@W4FontStyle@SVG@Mso@@@std@@B; std::optional<Mso::SVG::FontStyle> const Mso::SVG::StyleMetaData<18>::initial
0x180040903  jz      short loc_18004090C
0x180040905  lea     rax, ?inherit@?$StyleMetaData@$0BC@@SVG@Mso@@2V?$optional@W4FontStyle@SVG@Mso@@@std@@B; std::optional<Mso::SVG::FontStyle> const Mso::SVG::StyleMetaData<18>::inherit
0x18004090c  mov     rcx, rbx
0x18004090f  cmp     [rax+4], r15b
0x180040913  jnz     short loc_180040930
0x180040915  cmp     [rdi], r15
0x180040918  jz      short loc_180040924
0x18004091a  mov     rcx, [rdi]
0x18004091d  call    ??$Get@$0BC@@StyleResolveChain@SVG@Mso@@QEBAAEBW4FontStyle@12@XZ; Mso::SVG::StyleResolveChain::Get<18>(void)
0x180040922  jmp     short loc_180040930
0x180040924  mov     rdx, [rdx+rcx]
0x180040928  mov     rcx, rdi
0x18004092b  call    ??$GetNormal@$0BC@@StyleResolveChain@SVG@Mso@@AEBAAEBW4FontStyle@12@AEBVStyle@12@@Z; Mso::SVG::StyleResolveChain::GetNormal<18>(Mso::SVG::Style const &)
0x180040930  mov     r12d, [rax]
0x180040933  mov     rdx, [rdi+8]
0x180040937  mov     rax, [rdx+10h]
0x18004093b  test    rax, rax
0x18004093e  jz      short loc_180040948
0x180040940  add     rax, 2E0h
0x180040946  jmp     short loc_18004095C
0x180040948  cmp     [rdx+8], r15
0x18004094c  lea     rax, ?initial@?$StyleMetaData@$0BD@@SVG@Mso@@2V?$optional@W4FontVariant@SVG@Mso@@@std@@B; std::optional<Mso::SVG::FontVariant> const Mso::SVG::StyleMetaData<19>::initial
0x180040953  jz      short loc_18004095C
0x180040955  lea     rax, ?inherit@?$StyleMetaData@$0BD@@SVG@Mso@@2V?$optional@W4FontVariant@SVG@Mso@@@std@@B; std::optional<Mso::SVG::FontVariant> const Mso::SVG::StyleMetaData<19>::inherit
0x18004095c  cmp     [rax+4], r15b
0x180040960  jnz     short loc_18004097D
0x180040962  mov     rcx, [rdi]
0x180040965  test    rcx, rcx
0x180040968  jz      short loc_180040971
0x18004096a  call    ??$Get@$0BD@@StyleResolveChain@SVG@Mso@@QEBAAEBW4FontVariant@12@XZ; Mso::SVG::StyleResolveChain::Get<19>(void)
0x18004096f  jmp     short loc_18004097D
0x180040971  mov     rdx, [rbx+rdx]
0x180040975  mov     rcx, rdi
0x180040978  call    ??$GetNormal@$0BD@@StyleResolveChain@SVG@Mso@@AEBAAEBW4FontVariant@12@AEBVStyle@12@@Z; Mso::SVG::StyleResolveChain::GetNormal<19>(Mso::SVG::Style const &)
0x18004097d  mov     r8, [rdi+8]
0x180040981  mov     rdx, rdi
0x180040984  lea     rcx, [rbp+arg_0]
0x180040988  call    ??R?$SpecialResolver@$0BE@UFontWeight@SVG@Mso@@@StyleResolveChain@SVG@Mso@@QEBAHAEBV123@AEBVStyle@23@@Z; Mso::SVG::StyleResolveChain::SpecialResolver<20,Mso::SVG::FontWeight>::operator()(Mso::SVG::StyleResolveChain const &,Mso::SVG::Style const &)
0x18004098d  mov     r13d, eax
0x180040990  mov     r8, [rdi+8]
0x180040994  mov     rdx, rdi
0x180040997  lea     rcx, [rbp+arg_0]
0x18004099b  call    ??R?$SpecialResolver@$0BF@W4FontStretch@SVG@Mso@@@StyleResolveChain@SVG@Mso@@QEBA?AW4FontStretch@23@AEBV123@AEBVStyle@23@@Z; Mso::SVG::StyleResolveChain::SpecialResolver<21,Mso::SVG::FontStretch>::operator()(Mso::SVG::StyleResolveChain const &,Mso::SVG::Style const &)
0x1800409a0  mov     rcx, rdi
0x1800409a3  call    ??$Get@$0BG@@StyleResolveChain@SVG@Mso@@QEBANXZ; Mso::SVG::StyleResolveChain::Get<22>(void)
0x1800409a8  movaps  xmm6, xmm0
0x1800409ab  mov     [rbp+arg_0], r15
0x1800409af  mov     rcx, [rsi+8]
0x1800409b3  cmp     [rsi], rcx
0x1800409b6  jz      loc_180040B3D
0x1800409bc  call    cs:__imp_?GetDefaultTypefaces@ITypefaceList@GEL@@SAAEAU12@XZ; GEL::ITypefaceList::GetDefaultTypefaces(void)
0x1800409c2  mov     rcx, [rax]
0x1800409c5  mov     r10, [rcx+10h]
0x1800409c9  mov     r8, [rsi]
0x1800409cc  mov     rcx, [rsi+8]
0x1800409d0  sub     rcx, r8
0x1800409d3  sar     rcx, 5; Expression
0x1800409d7  test    rcx, rcx
0x1800409da  jnz     short loc_1800409F0
0x1800409dc  mov     [rsp+50h+Reserved], r15; Reserved
0x1800409e1  xor     r9d, r9d; LineNo
0x1800409e4  xor     r8d, r8d; FileName
0x1800409e7  xor     edx, edx; FunctionName
0x1800409e9  call    cs:__imp__invoke_watson
0x1800409f0  mov     r15d, 1
0x1800409f6  cmp     qword ptr [r8+18h], 7
0x1800409fb  jbe     short loc_180040A00
0x1800409fd  mov     r8, [r8]
0x180040a00  xor     edi, edi
0x180040a02  mov     [rsp+50h+var_28], rdi
0x180040a07  mov     byte ptr [rsp+50h+Reserved], dil
0x180040a0c  mov     r9b, r15b
0x180040a0f  lea     rdx, [rbp+arg_8]
0x180040a13  mov     rcx, rax
0x180040a16  mov     rax, r10
0x180040a19  call    cs:__guard_dispatch_icall_fptr
0x180040a1f  mov     rbx, [rax]
0x180040a22  mov     [rax], rdi
0x180040a25  mov     [rbp+arg_0], rbx
0x180040a29  mov     rcx, [rbp+arg_8]
0x180040a2d  test    rcx, rcx
0x180040a30  jz      short loc_180040A3F
0x180040a32  mov     rax, [rcx]
0x180040a35  mov     rax, [rax+8]
0x180040a39  call    cs:__guard_dispatch_icall_fptr
0x180040a3f  mov     rax, [rbx]
0x180040a42  mov     rcx, rbx
0x180040a45  jmp     loc_180040AF8
0x180040a4a  mov     edi, r15d
0x180040a4d  mov     rax, [rsi+8]
0x180040a51  sub     rax, [rsi]
0x180040a54  sar     rax, 5
0x180040a58  cmp     rdi, rax
0x180040a5b  jnb     loc_180040B0A
0x180040a61  call    cs:__imp_?GetDefaultTypefaces@ITypefaceList@GEL@@SAAEAU12@XZ; GEL::ITypefaceList::GetDefaultTypefaces(void)
0x180040a67  mov     rcx, [rax]
0x180040a6a  mov     r10, [rcx+10h]
0x180040a6e  mov     rdx, [rsi]
0x180040a71  mov     rcx, [rsi+8]
0x180040a75  sub     rcx, rdx
0x180040a78  sar     rcx, 5
0x180040a7c  cmp     rdi, rcx
0x180040a7f  jnb     loc_180040C1D
0x180040a85  inc     r15d
0x180040a88  shl     rdi, 5
0x180040a8c  lea     r8, [rdi+rdx]
0x180040a90  cmp     qword ptr [r8+18h], 7
0x180040a95  jbe     short loc_180040A9A
0x180040a97  mov     r8, [r8]
0x180040a9a  mov     [rsp+50h+var_28], 0
0x180040aa3  mov     byte ptr [rsp+50h+Reserved], 0
0x180040aa8  mov     r9b, 1
0x180040aab  lea     rdx, [rbp+arg_8]
0x180040aaf  mov     rcx, rax
0x180040ab2  mov     rax, r10
0x180040ab5  call    cs:__guard_dispatch_icall_fptr
0x180040abb  mov     rdi, [rax]
0x180040abe  mov     qword ptr [rax], 0
0x180040ac5  mov     rax, [rbx]
0x180040ac8  mov     rcx, rbx
0x180040acb  mov     rax, [rax+8]
0x180040acf  call    cs:__guard_dispatch_icall_fptr
0x180040ad5  mov     rbx, rdi
0x180040ad8  mov     [rbp+arg_0], rbx
0x180040adc  mov     rcx, [rbp+arg_8]
0x180040ae0  test    rcx, rcx
0x180040ae3  jz      short loc_180040AF2
0x180040ae5  mov     rax, [rcx]
0x180040ae8  mov     rax, [rax+8]
0x180040aec  call    cs:__guard_dispatch_icall_fptr
0x180040af2  mov     rax, [rdi]
0x180040af5  mov     rcx, rdi
0x180040af8  mov     rax, [rax+20h]
0x180040afc  call    cs:__guard_dispatch_icall_fptr
0x180040b02  test    al, al
0x180040b04  jz      loc_180040A4A
0x180040b0a  mov     rax, [rbx]
0x180040b0d  mov     rcx, rbx
0x180040b10  mov     rax, [rax+20h]
0x180040b14  call    cs:__guard_dispatch_icall_fptr
0x180040b1a  xor     r15d, r15d
0x180040b1d  test    al, al
0x180040b1f  jnz     short loc_180040B38
0x180040b21  mov     rax, [rbx]
0x180040b24  mov     rcx, rbx
0x180040b27  mov     rax, [rax+8]
0x180040b2b  call    cs:__guard_dispatch_icall_fptr
0x180040b31  mov     ebx, r15d
0x180040b34  mov     [rbp+arg_0], rbx
0x180040b38  test    rbx, rbx
0x180040b3b  jnz     short loc_180040B8F
0x180040b3d  call    cs:__imp_?GetDefaultTypefaces@ITypefaceList@GEL@@SAAEAU12@XZ; GEL::ITypefaceList::GetDefaultTypefaces(void)
0x180040b43  mov     r10, rax
0x180040b46  mov     rcx, [rax]
0x180040b49  mov     rax, [rcx+10h]
0x180040b4d  mov     [rsp+50h+var_28], r15
0x180040b52  mov     byte ptr [rsp+50h+Reserved], r15b
0x180040b57  mov     r9b, 1
0x180040b5a  lea     r8, aArial; "Arial"
0x180040b61  lea     rdx, [rbp+arg_8]
0x180040b65  mov     rcx, r10
0x180040b68  call    cs:__guard_dispatch_icall_fptr
0x180040b6e  mov     rbx, [rax]
0x180040b71  mov     [rax], r15
0x180040b74  mov     rcx, [rbp+arg_8]
0x180040b78  test    rcx, rcx
0x180040b7b  jz      short loc_180040B8A
0x180040b7d  mov     rax, [rcx]
0x180040b80  mov     rax, [rax+8]
0x180040b84  call    cs:__guard_dispatch_icall_fptr
0x180040b8a  test    rbx, rbx
0x180040b8d  jz      short loc_180040B9E
0x180040b8f  mov     rax, [rbx]
0x180040b92  mov     rcx, rbx
0x180040b95  mov     rax, [rax]
0x180040b98  call    cs:__guard_dispatch_icall_fptr
0x180040b9e  mov     rcx, [r14]
0x180040ba1  test    rcx, rcx
0x180040ba4  jz      short loc_180040BB3
0x180040ba6  mov     rax, [rcx]
0x180040ba9  mov     rax, [rax+8]
0x180040bad  call    cs:__guard_dispatch_icall_fptr
0x180040bb3  mov     [r14], rbx
0x180040bb6  xorps   xmm0, xmm0
0x180040bb9  cvtsd2ss xmm0, xmm6
0x180040bbd  movss   dword ptr [r14+10h], xmm0
0x180040bc3  mov     ecx, r15d
0x180040bc6  cmp     r13d, 258h
0x180040bcd  setnl   cl
0x180040bd0  neg     r12d
0x180040bd3  sbb     eax, eax
0x180040bd5  and     eax, 2
0x180040bd8  or      ecx, eax
0x180040bda  mov     [r14+14h], ecx
0x180040bde  call    cs:__imp_?GetConfig@Immediate@Gfx@@YAAEBVConfig@2@XZ; Gfx::Immediate::GetConfig(void)
0x180040be4  mov     cl, [rax+3Eh]
0x180040be7  mov     [r14+21h], cl
0x180040beb  test    rbx, rbx
0x180040bee  jz      short loc_180040C00
0x180040bf0  mov     rax, [rbx]
0x180040bf3  mov     rcx, rbx
0x180040bf6  mov     rax, [rax+8]
0x180040bfa  call    cs:__guard_dispatch_icall_fptr
0x180040c00  mov     rbx, [rsp+50h+arg_10]
0x180040c08  movaps  xmm6, [rsp+50h+var_10]
0x180040c0d  add     rsp, 50h
0x180040c11  pop     r15
0x180040c13  pop     r14
0x180040c15  pop     r13
0x180040c17  pop     r12
0x180040c19  pop     rdi
0x180040c1a  pop     rsi
0x180040c1b  pop     rbp
0x180040c1c  retn
0x180040c1d  mov     [rsp+50h+Reserved], 0; Reserved
0x180040c26  xor     r9d, r9d; LineNo
0x180040c29  xor     r8d, r8d; FileName
0x180040c2c  xor     edx, edx; FunctionName
0x180040c2e  xor     ecx, ecx; Expression
0x180040c30  call    cs:__imp__invoke_watson
```
