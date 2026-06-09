# Mso::SVG::TextRenderer::ProcessTextChunk(Mso::SVG::TextChunk &,Mso::SVG::WritingMode,double &,double &,void (*)(void *,Mso::SVG::TextChunkItem const &,Mso::SVG::TextAnchor,GEL::Font const &,tag_SCRIPT_ANALYSIS const &,wchar_t const *,uint,bool,bool,std::vector<ushort,std::allocator<ushort>> const &,std::vector<float,std::allocator<float>> const &,std::vector<float,std::allocator<float>> const &,std::vector<GEL::Vector,std::allocator<GEL::Vector>> const &,float,float,float,float,std::vector<ushort,std::allocator<ushort>> const &,Math::TAffine3x3<double> const &,Mso::SVG::TextRenderingParams const &),void *,Mso::SVG::TextRenderingParams const &)

- ea: `0x180135a78`
- end: `0x180136074`
- name: `?ProcessTextChunk@TextRenderer@SVG@Mso@@CAXAEAUTextChunk@23@W4WritingMode@23@AEAN2P6AXPEAXAEBUTextChunkItem@23@W4TextAnchor@23@AEBUFont@GEL@@AEBUtag_SCRIPT_ANALYSIS@@PEB_WI_N9AEBV?$vector@GV?$allocator@G@std@@@std@@AEBV?$vector@MV?$allocator@M@std@@@std@@AEBV?$vector@MV?$allocator@M@std@@@std@@AEBV?$vector@UVector@GEL@@V?$allocator@UVector@GEL@@@std@@@std@@MMMMAEBV?$vector@GV?$allocator@G@std@@@std@@AEBU?$TAffine3x3@N@Math@@AEBUTextRenderingParams@23@@Z3AEBUTextRenderingParams@23@@Z`
- size: `1532`
- prototype: `__int64 __usercall@<rax>(Mso::SVG *this@<rcx>, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config`

## callers

- `0x180132b64`

## callees

- `0x180008e60`
- `0x1800091d0`
- `0x180009248`
- `0x180009320`
- `0x180023c30`
- `0x180027318`
- `0x180129acc`
- `0x180135284`
- `0x180135a78`
- `0x1801370a8`
- `0x1801384d4`
- `0x180138edc`
- `0x18013b97c`
- `0x18013d650`
- `0x18013e67c`
- `0x18013f6de`

## import_xrefs

- `mso40uiWin32Client!__imp_MsoScriptItemize` at `0x180135e51`
- `mso40uiWin32Client!__imp_MsoScriptItemize` at `0x180135e51`
- `MSVCP140!?_Xbad_alloc@std@@YAXXZ` at `0x180135e16`
- `MSVCP140!?_Xbad_alloc@std@@YAXXZ` at `0x180135e16`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180135c14`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180135fdf`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180135c14`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180135fdf`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180135de5`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180135e07`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180135de5`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180135e07`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180135c0d`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180135fd8`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180136018`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18013602e`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180135c0d`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180135fd8`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180136018`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18013602e`
- `gfx!?GetConfig@Immediate@Gfx@@YAAEBVConfig@2@XZ` at `0x180135da0`
- `gfx!?GetConfig@Immediate@Gfx@@YAAEBVConfig@2@XZ` at `0x180135da0`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall Mso::SVG::TextRenderer::ProcessTextChunk(
        Mso::SVG *this,
        SCRIPT_ANALYSIS a2,
        double *a3,
        double *a4,
        __int64 a5,
        __int64 a6,
        __int64 a7)
{
  __int64 v8; // rcx
  __int64 v9; // rax
  int v10; // edx
  char v11; // r13
  Mso::SVG *Src; // rax
  __int64 v13; // rcx
  __int128 *v14; // rax
  void *v15; // rcx
  __int64 v16; // rcx
  unsigned int v17; // r9d
  __int64 v18; // rcx
  __int64 v19; // rdx
  unsigned __int64 v20; // r8
  unsigned __int64 v21; // rcx
  __int64 v22; // rcx
  unsigned __int64 v23; // r12
  unsigned int v24; // r15d
  __int64 v25; // rax
  unsigned __int64 v26; // rbx
  _QWORD *v27; // rax
  unsigned __int64 v28; // rcx
  char *v29; // rdi
  _BYTE *v30; // rsi
  Mso::SVG *v31; // rbx
  const struct Gfx::Config *Config; // rax
  __int64 v33; // r8
  __int64 v34; // rdx
  Mso::SVG *v35; // rcx
  int v36; // eax
  void *v37; // rax
  void *v38; // rcx
  size_t v39; // rbx
  unsigned __int64 v40; // rbx
  unsigned __int64 v41; // rcx
  unsigned __int64 v42; // rbx
  size_t v43; // rbx
  void *v44; // rcx
  __int16 *Reserved; // [rsp+20h] [rbp-D1h]
  unsigned __int8 v46; // [rsp+40h] [rbp-B1h]
  __int16 v47; // [rsp+48h] [rbp-A9h] BYREF
  void *v48[2]; // [rsp+50h] [rbp-A1h] BYREF
  char *v49; // [rsp+60h] [rbp-91h]
  tag_SCRIPT_ITEM v50; // [rsp+68h] [rbp-89h] BYREF
  __int64 v51; // [rsp+70h] [rbp-81h] BYREF
  int v52; // [rsp+78h] [rbp-79h]
  __int64 v53; // [rsp+80h] [rbp-71h]
  __int64 v54; // [rsp+88h] [rbp-69h]
  __int64 v55; // [rsp+90h] [rbp-61h]
  double *v56; // [rsp+98h] [rbp-59h]
  double *v57; // [rsp+A0h] [rbp-51h]
  __int128 v58; // [rsp+A8h] [rbp-49h] BYREF
  __m128i si128; // [rsp+B8h] [rbp-39h]
  void *Block[2]; // [rsp+C8h] [rbp-29h] BYREF
  __m128i v61; // [rsp+D8h] [rbp-19h]

  v56 = a4;
  v57 = a3;
  v50.a = a2;
  v55 = a5;
  v54 = a6;
  v53 = a7;
  v8 = *((_QWORD *)this + 4);
  v9 = *((_QWORD *)this + 5);
  if ( v8 == v9 )
    return;
  if ( !(0x84BDA12F684BDA13uLL * ((v9 - v8) >> 3)) )
    goto LABEL_72;
  v10 = *(_DWORD *)(v8 + 16);
  v52 = v10;
  v46 = v10 == 1;
  v11 = 0;
  if ( *(_DWORD *)(v8 + 20) == 2 )
  {
    v47 = 8238 - (v10 != 1);
    if ( *((_QWORD *)this + 2) == 0x7FFFFFFFFFFFFFFELL )
      std::_Xlen_string();
    Src = this;
    if ( *((_QWORD *)this + 3) > 7u )
      Src = *(Mso::SVG **)this;
    std::wstring::wstring(&v58, 1, Src, *((_QWORD *)this + 2));
    v13 = si128.m128i_i64[0];
    if ( si128.m128i_i64[0] >= (unsigned __int64)si128.m128i_i64[1] )
    {
      ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__QEAAX_W_Z__W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAX_W_Z__W_Z(&v58);
    }
    else
    {
      ++si128.m128i_i64[0];
      v14 = &v58;
      if ( si128.m128i_i64[1] > 7uLL )
        v14 = (__int128 *)v58;
      *(_DWORD *)((char *)v14 + 2 * v13) = 8236;
    }
    *(_OWORD *)Block = v58;
    v61 = si128;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v58) = 0;
    std::wstring::operator=(this, Block);
    if ( v61.m128i_i64[1] > 7uLL )
    {
      v15 = Block[0];
      if ( (unsigned __int64)(2 * v61.m128i_i64[1] + 2) >= 0x1000 )
      {
        v15 = (void *)*((_QWORD *)Block[0] - 1);
        if ( (unsigned __int64)((char *)Block[0] - (char *)v15 - 8) > 0x1F )
          _invoke_watson(0, 0, 0, 0, 0);
      }
      free(v15);
    }
    std::wstring::~wstring(&v58);
    v16 = *((_QWORD *)this + 4);
    if ( !(0x84BDA12F684BDA13uLL * ((*((_QWORD *)this + 5) - v16) >> 3)) )
      goto LABEL_72;
    ++*(_DWORD *)(v16 + 132);
    v17 = 1;
    v18 = *((_QWORD *)this + 5);
    v19 = *((_QWORD *)this + 4);
    if ( 0x84BDA12F684BDA13uLL * ((v18 - v19) >> 3) > 1 )
    {
      v20 = 1;
      while ( v20 < 0x84BDA12F684BDA13uLL * ((*((_QWORD *)this + 5) - v19) >> 3) )
      {
        ++*(_DWORD *)(216 * v20 + v19 + 128);
        ++v17;
        v18 = *((_QWORD *)this + 5);
        v19 = *((_QWORD *)this + 4);
        v20 = v17;
        if ( v17 >= 0x84BDA12F684BDA13uLL * ((v18 - v19) >> 3) )
          goto LABEL_22;
      }
LABEL_72:
      _invoke_watson(0, 0, 0, 0, 0);
    }
LABEL_22:
    v21 = 0x84BDA12F684BDA13uLL * ((v18 - v19) >> 3);
    if ( !v21 )
      goto LABEL_72;
    ++*(_DWORD *)(216 * (v21 - 1) + v19 + 132);
    v22 = *((_QWORD *)this + 4);
    if ( !(0x84BDA12F684BDA13uLL * ((*((_QWORD *)this + 5) - v22) >> 3)) )
      goto LABEL_72;
    *(_DWORD *)(v22 + 20) = 0;
  }
  v23 = *((_QWORD *)this + 2);
  if ( v23 > 0xFFFFFFFF )
  {
    SafeIntException::SafeIntException(&v50.a);
    throw (SafeIntException *)&v50.a;
  }
  v24 = 10;
  if ( (unsigned int)v23 >> 1 > 0xA )
    v24 = (unsigned int)v23 >> 1;
  v25 = v24 + 1;
  *(_OWORD *)v48 = 0;
  v49 = 0;
  v26 = 8 * v25;
  if ( 8 * v25 )
  {
    if ( v26 < 0x1000 )
    {
      v27 = malloc(8 * v25);
      if ( v27 )
        goto LABEL_30;
    }
    else
    {
      if ( v26 + 39 < v26 )
        std::_Throw_bad_array_new_length();
      v37 = malloc(v26 + 39);
      v38 = v37;
      if ( v37 )
      {
        v27 = (_QWORD *)(((unsigned __int64)v37 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
        *(v27 - 1) = v38;
        goto LABEL_30;
      }
    }
    std::_Xbad_alloc();
    goto LABEL_42;
  }
  v27 = 0;
LABEL_30:
  v48[0] = v27;
  v49 = (char *)&v27[v26 / 8];
  memset_0(v27, 0, 8LL * (v24 + 1));
  v48[1] = v49;
  v51 = 0;
  std::_Tidy_guard<std::vector<double>>::~_Tidy_guard<std::vector<double>>(&v51);
  v50.iCharPos = 0;
  v11 = 0;
  v29 = v49;
  v30 = v48[0];
  do
  {
    if ( !((v29 - v30) >> 3) )
      _invoke_watson(0, 0, 0, 0, 0);
    v31 = this;
    if ( *((_QWORD *)this + 3) > 7u )
      v31 = *(Mso::SVG **)this;
    Config = Gfx::Immediate::GetConfig((Gfx::Immediate *)v28);
    v33 = v24;
    v34 = (unsigned int)v23;
    v35 = v31;
    if ( *((_BYTE *)Config + 62) )
    {
      v36 = Mso::SVG::ItemizeStringDWrite(
              v31,
              (const wchar_t *)(unsigned int)v23,
              v24,
              v46,
              (bool)Reserved,
              (__int64)v30,
              &v50);
    }
    else
    {
LABEL_42:
      LODWORD(v51) = 0;
      v47 = v52 == 1;
      Reserved = &v47;
      v36 = MsoScriptItemize(v35, v34, v33, &v51);
    }
    if ( v36 == -2147024882 && (v28 = 128, v24 < 0x80) )
    {
      v24 = 128;
      v29 = (char *)v48[1];
      v30 = v48[0];
      v28 = ((char *)v48[1] - (char *)v48[0]) >> 3;
      if ( v28 > 0x81 )
      {
        v29 = (char *)v48[0] + 1032;
LABEL_52:
        v48[1] = v29;
        continue;
      }
      if ( v28 >= 0x81 )
        continue;
      if ( (unsigned __int64)((v49 - (char *)v48[0]) >> 3) >= 0x81 )
      {
        if ( 129 != v28 )
        {
          v39 = 8 * (129 - v28);
          memset_0(v48[1], 0, v39);
          v29 += v39;
          v30 = v48[0];
        }
        goto LABEL_52;
      }
      std::vector<tag_SCRIPT_ITEM>::_Resize_reallocate<std::_Value_init_tag>(v48, 129);
    }
    else
    {
      if ( v36 < 0 )
      {
        Ofc::CHResultException::ThrowTag(v36, 0x138D8CCu);
        __debugbreak();
      }
      v11 = 1;
    }
    v30 = v48[0];
    v29 = (char *)v48[1];
  }
  while ( !v11 );
  v40 = (unsigned int)(v50.iCharPos + 1);
  v41 = (v29 - v30) >> 3;
  if ( v40 >= v41 )
  {
    if ( v40 > v41 )
    {
      if ( v40 <= (v49 - v30) >> 3 )
      {
        v42 = v40 - v41;
        if ( v42 )
        {
          v43 = 8 * v42;
          memset_0(v29, 0, v43);
          v29 += v43;
        }
        v48[1] = v29;
      }
      else
      {
        std::vector<tag_SCRIPT_ITEM>::_Resize_reallocate<std::_Value_init_tag>(v48, (unsigned int)(v50.iCharPos + 1));
      }
    }
  }
  else
  {
    v48[1] = &v30[8 * (v50.iCharPos + 1)];
  }
  Mso::SVG::TextRenderer::MergeTextChunkAndItems(
    (__int64 *)this,
    (__int64 *)v48,
    *(_DWORD *)&v50.a,
    v57,
    v56,
    v55,
    v54,
    v53);
  v44 = v48[0];
  if ( v48[0] )
  {
    if ( ((v49 - (char *)v48[0]) & 0xFFFFFFFFFFFFFFF8uLL) >= 0x1000 )
    {
      v44 = (void *)*((_QWORD *)v48[0] - 1);
      if ( (unsigned __int64)((char *)v48[0] - (char *)v44 - 8) > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
    }
    free(v44);
  }
}

```

## disassembly

```asm
0x180135a78  push    rbp
0x180135a7a  push    rbx
0x180135a7b  push    rsi
0x180135a7c  push    rdi
0x180135a7d  push    r12
0x180135a7f  push    r13
0x180135a81  push    r14
0x180135a83  push    r15
0x180135a85  lea     rbp, [rsp-7]
0x180135a8a  sub     rsp, 0F8h
0x180135a91  mov     rax, cs:__security_cookie
0x180135a98  xor     rax, rsp
0x180135a9b  mov     [rbp+3Fh+var_48], rax
0x180135a9f  mov     [rbp+3Fh+var_98], r9
0x180135aa3  mov     [rbp+3Fh+var_90], r8
0x180135aa7  mov     dword ptr [rsp+130h+var_C8.a.eScript], edx
0x180135aab  mov     r14, rcx
0x180135aae  mov     rax, [rbp+3Fh+arg_20]
0x180135ab2  mov     [rbp+3Fh+var_A0], rax
0x180135ab6  mov     rax, [rbp+3Fh+arg_28]
0x180135aba  mov     [rbp+3Fh+var_A8], rax
0x180135abe  mov     rax, [rbp+3Fh+arg_30]
0x180135ac2  mov     [rbp+3Fh+var_B0], rax
0x180135ac6  xor     esi, esi
0x180135ac8  mov     rcx, [rcx+20h]
0x180135acc  mov     rax, [r14+28h]
0x180135ad0  cmp     rcx, rax
0x180135ad3  jz      loc_180135FE5
0x180135ad9  sub     rax, rcx
0x180135adc  sar     rax, 3
0x180135ae0  mov     rbx, 84BDA12F684BDA13h
0x180135aea  imul    rax, rbx
0x180135aee  test    rax, rax
0x180135af1  jz      loc_18013601F
0x180135af7  mov     edx, [rcx+10h]
0x180135afa  mov     [rbp+3Fh+var_B8], edx
0x180135afd  lea     edi, [rsi+1]
0x180135b00  cmp     edx, edi
0x180135b02  setz    [rsp+130h+var_F0]
0x180135b07  mov     r13d, 1000h
0x180135b0d  cmp     dword ptr [rcx+14h], 2
0x180135b11  jnz     loc_180135CF3
0x180135b17  mov     eax, edx
0x180135b19  sub     eax, edi
0x180135b1b  neg     eax
0x180135b1d  sbb     ax, ax
0x180135b20  add     ax, 202Eh
0x180135b24  mov     [rsp+130h+var_E8], ax
0x180135b29  mov     rcx, [r14+10h]
0x180135b2d  mov     rax, 7FFFFFFFFFFFFFFEh
0x180135b37  cmp     rcx, rax
0x180135b3a  jz      loc_180136051
0x180135b40  mov     rax, r14
0x180135b43  cmp     qword ptr [r14+18h], 7
0x180135b48  jbe     short loc_180135B4D
0x180135b4a  mov     rax, [r14]
0x180135b4d  mov     [rsp+130h+var_100], rcx; __int64
0x180135b52  mov     [rsp+130h+Src], rax; Src
0x180135b57  mov     [rsp+130h+Reserved], rdi; bool
0x180135b5c  lea     r9, [rsp+130h+var_E8]
0x180135b61  lea     rcx, [rbp+3Fh+var_88]; void *
0x180135b65  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEB_W_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x180135b6a  mov     rcx, qword ptr [rbp+3Fh+var_78]
0x180135b6e  cmp     rcx, qword ptr [rbp+3Fh+var_78+8]
0x180135b72  jnb     short loc_180135B93
0x180135b74  lea     rax, [rcx+1]
0x180135b78  mov     qword ptr [rbp+3Fh+var_78], rax
0x180135b7c  lea     rax, [rbp+3Fh+var_88]
0x180135b80  cmp     qword ptr [rbp+3Fh+var_78+8], 7
0x180135b85  cmova   rax, qword ptr [rbp+3Fh+var_88]
0x180135b8a  mov     dword ptr [rax+rcx*2], 202Ch
0x180135b91  jmp     short loc_180135BA2
0x180135b93  mov     r9d, 202Ch
0x180135b99  lea     rcx, [rbp+3Fh+var_88]; Src
0x180135b9d  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_W@Z@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAX_W@Z@_W@Z; std::wstring::_Reallocate_grow_by<`std::wstring::push_back(wchar_t)'::`2'::_lambda_1_,wchar_t>(unsigned __int64,`std::wstring::push_back(wchar_t)'::`2'::_lambda_1_,wchar_t)
0x180135ba2  movups  xmm0, [rbp+3Fh+var_88]
0x180135ba6  movups  xmmword ptr [rbp+3Fh+Block], xmm0
0x180135baa  movups  xmm1, [rbp+3Fh+var_78]
0x180135bae  movups  [rbp+3Fh+var_58], xmm1
0x180135bb2  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x180135bba  movdqu  [rbp+3Fh+var_78], xmm0
0x180135bbf  mov     word ptr [rbp+3Fh+var_88], si
0x180135bc3  lea     rdx, [rbp+3Fh+Block]
0x180135bc7  mov     rcx, r14
0x180135bca  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180135bcf  mov     rax, qword ptr [rbp+3Fh+var_58+8]
0x180135bd3  cmp     rax, 7
0x180135bd7  jbe     short loc_180135C1B
0x180135bd9  mov     rcx, [rbp+3Fh+Block]; Block
0x180135bdd  mov     rdx, rcx
0x180135be0  lea     rax, ds:2[rax*2]
0x180135be8  cmp     rax, r13
0x180135beb  jb      short loc_180135C14
0x180135bed  mov     rcx, [rcx-8]
0x180135bf1  sub     rdx, rcx
0x180135bf4  lea     rax, [rdx-8]
0x180135bf8  cmp     rax, 1Fh
0x180135bfc  jbe     short loc_180135C14
0x180135bfe  mov     [rsp+130h+Reserved], rsi; Reserved
0x180135c03  xor     r9d, r9d; LineNo
0x180135c06  xor     r8d, r8d; FileName
0x180135c09  xor     edx, edx; FunctionName
0x180135c0b  xor     ecx, ecx; Expression
0x180135c0d  call    cs:__imp__invoke_watson
0x180135c14  call    cs:__imp_free
0x180135c1a  nop
0x180135c1b  lea     rcx, [rbp+3Fh+var_88]; void *
0x180135c1f  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180135c24  mov     rcx, [r14+20h]
0x180135c28  mov     rax, [r14+28h]
0x180135c2c  sub     rax, rcx
0x180135c2f  sar     rax, 3
0x180135c33  imul    rax, rbx
0x180135c37  test    rax, rax
0x180135c3a  jz      loc_18013601F
0x180135c40  add     [rcx+84h], edi
0x180135c46  mov     r9d, edi
0x180135c49  mov     rcx, [r14+28h]
0x180135c4d  mov     rdx, [r14+20h]
0x180135c51  mov     rax, rcx
0x180135c54  sub     rax, rdx
0x180135c57  sar     rax, 3
0x180135c5b  imul    rax, rbx
0x180135c5f  cmp     rax, rdi
0x180135c62  jbe     short loc_180135CAE
0x180135c64  mov     r8, rdi
0x180135c67  mov     rax, [r14+28h]
0x180135c6b  sub     rax, rdx
0x180135c6e  sar     rax, 3
0x180135c72  imul    rax, rbx
0x180135c76  cmp     r8, rax
0x180135c79  jnb     loc_18013601F
0x180135c7f  imul    rax, r8, 0D8h
0x180135c86  add     [rax+rdx+80h], edi
0x180135c8d  add     r9d, edi
0x180135c90  mov     rcx, [r14+28h]
0x180135c94  mov     rdx, [r14+20h]
0x180135c98  mov     r8d, r9d
0x180135c9b  mov     rax, rcx
0x180135c9e  sub     rax, rdx
0x180135ca1  sar     rax, 3
0x180135ca5  imul    rax, rbx
0x180135ca9  cmp     r8, rax
0x180135cac  jb      short loc_180135C67
0x180135cae  sub     rcx, rdx
0x180135cb1  sar     rcx, 3
0x180135cb5  imul    rcx, rbx
0x180135cb9  lea     rax, [rcx-1]
0x180135cbd  cmp     rax, rcx
0x180135cc0  jnb     loc_18013601F
0x180135cc6  imul    rax, 0D8h
0x180135ccd  add     [rax+rdx+84h], edi
0x180135cd4  mov     rcx, [r14+20h]
0x180135cd8  mov     rax, [r14+28h]
0x180135cdc  sub     rax, rcx
0x180135cdf  sar     rax, 3
0x180135ce3  imul    rax, rbx
0x180135ce7  test    rax, rax
0x180135cea  jz      loc_18013601F
0x180135cf0  mov     [rcx+14h], esi
0x180135cf3  mov     r12, [r14+10h]
0x180135cf7  mov     eax, 0FFFFFFFFh
0x180135cfc  cmp     r12, rax
0x180135cff  ja      loc_180136035
0x180135d05  mov     eax, r12d
0x180135d08  shr     eax, 1
0x180135d0a  mov     r15d, 0Ah
0x180135d10  cmp     eax, r15d
0x180135d13  cmova   r15d, eax
0x180135d17  lea     eax, [r15+1]
0x180135d1b  mov     edi, eax
0x180135d1d  xorps   xmm0, xmm0
0x180135d20  movdqu  xmmword ptr [rsp+130h+var_E0], xmm0
0x180135d26  mov     [rsp+130h+var_D0], rsi
0x180135d2b  lea     rbx, ds:0[rax*8]
0x180135d33  test    rbx, rbx
0x180135d36  jnz     loc_180135DD3
0x180135d3c  mov     rax, rsi
0x180135d3f  mov     [rsp+130h+var_E0], rax
0x180135d44  add     rbx, rax
0x180135d47  mov     [rsp+130h+var_D0], rbx
0x180135d4c  lea     r8, ds:0[rdi*8]; Size
0x180135d54  xor     edx, edx; Val
0x180135d56  mov     rcx, rax; void *
0x180135d59  call    memset_0
0x180135d5e  mov     [rsp+130h+var_E0+8], rbx
0x180135d63  mov     [rsp+130h+var_C0], rsi
0x180135d68  lea     rcx, [rsp+130h+var_C0]
0x180135d6d  call    ??1?$_Tidy_guard@V?$vector@NV?$allocator@N@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<double>>::~_Tidy_guard<std::vector<double>>(void)
0x180135d72  mov     [rsp+130h+var_C8.iCharPos], esi
0x180135d76  mov     r13b, sil
0x180135d79  mov     rdi, [rsp+130h+var_E0+8]
0x180135d7e  mov     rsi, [rsp+130h+var_E0]
0x180135d83  sub     rdi, rsi
0x180135d86  sar     rdi, 3
0x180135d8a  test    rdi, rdi
0x180135d8d  jz      loc_180136005
0x180135d93  mov     rbx, r14
0x180135d96  cmp     qword ptr [r14+18h], 7
0x180135d9b  jbe     short loc_180135DA0
0x180135d9d  mov     rbx, [r14]
0x180135da0  call    cs:__imp_?GetConfig@Immediate@Gfx@@YAAEBVConfig@2@XZ; Gfx::Immediate::GetConfig(void)
0x180135da6  mov     r8d, r15d; int
0x180135da9  mov     edx, r12d; wchar_t *
0x180135dac  mov     rcx, rbx; this
0x180135daf  cmp     byte ptr [rax+3Eh], 0
0x180135db3  jz      short loc_180135E1D
0x180135db5  lea     rax, [rsp+130h+var_C8]
0x180135dba  mov     [rsp+130h+var_100], rax; struct tag_SCRIPT_ITEM *
0x180135dbf  mov     [rsp+130h+Src], rsi; unsigned __int16
0x180135dc4  mov     r9b, [rsp+130h+var_F0]; int
0x180135dc9  call    ?ItemizeStringDWrite@SVG@Mso@@YAJPEB_WHH_NGPEAUtag_SCRIPT_ITEM@@PEAH@Z; Mso::SVG::ItemizeStringDWrite(wchar_t const *,int,int,bool,ushort,tag_SCRIPT_ITEM *,int *)
0x180135dce  jmp     loc_180135E57
0x180135dd3  cmp     rbx, r13
0x180135dd6  jb      short loc_180135E04
0x180135dd8  lea     rcx, [rbx+27h]; Size
0x180135ddc  cmp     rcx, rbx
0x180135ddf  jbe     loc_18013605D
0x180135de5  call    cs:__imp_malloc
0x180135deb  mov     rcx, rax
0x180135dee  test    rax, rax
0x180135df1  jz      short loc_180135E16
0x180135df3  add     rax, 27h ; '''
0x180135df7  and     rax, 0FFFFFFFFFFFFFFE0h
0x180135dfb  mov     [rax-8], rcx
0x180135dff  jmp     loc_180135D3F
0x180135e04  mov     rcx, rbx; Size
0x180135e07  call    cs:__imp_malloc
0x180135e0d  test    rax, rax
0x180135e10  jnz     loc_180135D3F
0x180135e16  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180135e1c  nop
0x180135e1d  mov     dword ptr [rsp+130h+var_C0], 0
0x180135e25  xor     eax, eax
0x180135e27  cmp     [rbp+3Fh+var_B8], 1
0x180135e2b  setz    al
0x180135e2e  mov     [rsp+130h+var_E8], ax
0x180135e33  lea     rax, [rsp+130h+var_C8]
0x180135e38  mov     [rsp+130h+var_100], rax
0x180135e3d  mov     [rsp+130h+Src], rsi
0x180135e42  lea     rax, [rsp+130h+var_E8]
0x180135e47  mov     [rsp+130h+Reserved], rax
0x180135e4c  lea     r9, [rsp+130h+var_C0]
0x180135e51  call    cs:__imp_MsoScriptItemize
0x180135e57  cmp     eax, 8007000Eh
0x180135e5c  jnz     short loc_180135ED8
0x180135e5e  mov     ecx, 80h
0x180135e63  cmp     r15d, ecx
0x180135e66  jnb     short loc_180135ED8
0x180135e68  mov     r15d, ecx
0x180135e6b  mov     rdi, [rsp+130h+var_E0+8]
0x180135e70  mov     rcx, rdi
0x180135e73  mov     rsi, [rsp+130h+var_E0]
0x180135e78  sub     rcx, rsi
0x180135e7b  sar     rcx, 3
0x180135e7f  lea     ebx, [r15+1]
0x180135e83  cmp     rcx, rbx
0x180135e86  jbe     short loc_180135E91
0x180135e88  lea     rdi, [rsi+408h]
0x180135e8f  jmp     short loc_180135ED1
0x180135e91  jnb     short loc_180135EED
0x180135e93  mov     rax, [rsp+130h+var_D0]
0x180135e98  sub     rax, rsi
0x180135e9b  sar     rax, 3
0x180135e9f  cmp     rax, rbx
0x180135ea2  jnb     short loc_180135EB3
0x180135ea4  mov     rdx, rbx
0x180135ea7  lea     rcx, [rsp+130h+var_E0]
0x180135eac  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@Utag_SCRIPT_ITEM@@V?$allocator@Utag_SCRIPT_ITEM@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<tag_SCRIPT_ITEM>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180135eb1  jmp     short loc_180135EE3
0x180135eb3  sub     rbx, rcx
0x180135eb6  jz      short loc_180135ED1
0x180135eb8  shl     rbx, 3
0x180135ebc  mov     r8, rbx; Size
0x180135ebf  xor     edx, edx; Val
0x180135ec1  mov     rcx, rdi; void *
0x180135ec4  call    memset_0
0x180135ec9  add     rdi, rbx
0x180135ecc  mov     rsi, [rsp+130h+var_E0]
0x180135ed1  mov     [rsp+130h+var_E0+8], rdi
0x180135ed6  jmp     short loc_180135EED
0x180135ed8  test    eax, eax
0x180135eda  js      loc_180136067
0x180135ee0  mov     r13b, 1
0x180135ee3  mov     rsi, [rsp+130h+var_E0]
0x180135ee8  mov     rdi, [rsp+130h+var_E0+8]
0x180135eed  test    r13b, r13b
0x180135ef0  jz      loc_180135D83
0x180135ef6  mov     eax, [rsp+130h+var_C8.iCharPos]
0x180135efa  inc     eax
0x180135efc  mov     ebx, eax
0x180135efe  mov     rcx, rdi
0x180135f01  sub     rcx, rsi
0x180135f04  sar     rcx, 3
0x180135f08  cmp     rbx, rcx
0x180135f0b  jnb     short loc_180135F18
0x180135f0d  lea     rax, [rsi+rax*8]
0x180135f11  mov     [rsp+130h+var_E0+8], rax
0x180135f16  jmp     short loc_180135F58
0x180135f18  jbe     short loc_180135F58
  ... truncated ...
```
