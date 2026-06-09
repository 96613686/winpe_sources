# Mso::SVG::TextRenderer::ProcessTextChunk(Mso::SVG::TextChunk &,Mso::SVG::WritingMode,double &,double &,void (*)(void *,Mso::SVG::TextChunkItem const &,Mso::SVG::TextAnchor,GEL::Font const &,tag_SCRIPT_ANALYSIS const &,wchar_t const *,uint,bool,bool,std::vector<ushort,std::allocator<ushort>> const &,std::vector<float,std::allocator<float>> const &,std::vector<float,std::allocator<float>> const &,std::vector<GEL::Vector,std::allocator<GEL::Vector>> const &,float,float,float,float,std::vector<ushort,std::allocator<ushort>> const &,Math::TAffine3x3<double> const &,Mso::SVG::TextRenderingParams const &),void *,Mso::SVG::TextRenderingParams const &)

- ea: `0x180135ab8`
- end: `0x1801360b4`
- name: `?ProcessTextChunk@TextRenderer@SVG@Mso@@CAXAEAUTextChunk@23@W4WritingMode@23@AEAN2P6AXPEAXAEBUTextChunkItem@23@W4TextAnchor@23@AEBUFont@GEL@@AEBUtag_SCRIPT_ANALYSIS@@PEB_WI_N9AEBV?$vector@GV?$allocator@G@std@@@std@@AEBV?$vector@MV?$allocator@M@std@@@std@@AEBV?$vector@MV?$allocator@M@std@@@std@@AEBV?$vector@UVector@GEL@@V?$allocator@UVector@GEL@@@std@@@std@@MMMMAEBV?$vector@GV?$allocator@G@std@@@std@@AEBU?$TAffine3x3@N@Math@@AEBUTextRenderingParams@23@@Z3AEBUTextRenderingParams@23@@Z`
- size: `1532`
- prototype: `__int64 __usercall@<rax>(Mso::SVG *this@<rcx>, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config`

## callers

- `0x180132ba4`

## callees

- `0x180008e60`
- `0x1800091d0`
- `0x180009248`
- `0x180009320`
- `0x180023c30`
- `0x180027318`
- `0x180129afc`
- `0x1801352c4`
- `0x180135ab8`
- `0x1801370e8`
- `0x180138514`
- `0x180138f1c`
- `0x18013ba2c`
- `0x18013d700`
- `0x18013e72c`
- `0x18013f78e`

## import_xrefs

- `mso40uiWin32Client!__imp_MsoScriptItemize` at `0x180135e91`
- `mso40uiWin32Client!__imp_MsoScriptItemize` at `0x180135e91`
- `MSVCP140!?_Xbad_alloc@std@@YAXXZ` at `0x180135e56`
- `MSVCP140!?_Xbad_alloc@std@@YAXXZ` at `0x180135e56`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180135c54`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18013601f`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180135c54`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18013601f`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180135e25`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180135e47`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180135e25`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180135e47`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180135c4d`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180136018`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180136058`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18013606e`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180135c4d`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180136018`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180136058`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18013606e`
- `gfx!?GetConfig@Immediate@Gfx@@YAAEBVConfig@2@XZ` at `0x180135de0`
- `gfx!?GetConfig@Immediate@Gfx@@YAAEBVConfig@2@XZ` at `0x180135de0`

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
0x180135ab8  push    rbp
0x180135aba  push    rbx
0x180135abb  push    rsi
0x180135abc  push    rdi
0x180135abd  push    r12
0x180135abf  push    r13
0x180135ac1  push    r14
0x180135ac3  push    r15
0x180135ac5  lea     rbp, [rsp-7]
0x180135aca  sub     rsp, 0F8h
0x180135ad1  mov     rax, cs:__security_cookie
0x180135ad8  xor     rax, rsp
0x180135adb  mov     [rbp+3Fh+var_48], rax
0x180135adf  mov     [rbp+3Fh+var_98], r9
0x180135ae3  mov     [rbp+3Fh+var_90], r8
0x180135ae7  mov     dword ptr [rsp+130h+var_C8.a.eScript], edx
0x180135aeb  mov     r14, rcx
0x180135aee  mov     rax, [rbp+3Fh+arg_20]
0x180135af2  mov     [rbp+3Fh+var_A0], rax
0x180135af6  mov     rax, [rbp+3Fh+arg_28]
0x180135afa  mov     [rbp+3Fh+var_A8], rax
0x180135afe  mov     rax, [rbp+3Fh+arg_30]
0x180135b02  mov     [rbp+3Fh+var_B0], rax
0x180135b06  xor     esi, esi
0x180135b08  mov     rcx, [rcx+20h]
0x180135b0c  mov     rax, [r14+28h]
0x180135b10  cmp     rcx, rax
0x180135b13  jz      loc_180136025
0x180135b19  sub     rax, rcx
0x180135b1c  sar     rax, 3
0x180135b20  mov     rbx, 84BDA12F684BDA13h
0x180135b2a  imul    rax, rbx
0x180135b2e  test    rax, rax
0x180135b31  jz      loc_18013605F
0x180135b37  mov     edx, [rcx+10h]
0x180135b3a  mov     [rbp+3Fh+var_B8], edx
0x180135b3d  lea     edi, [rsi+1]
0x180135b40  cmp     edx, edi
0x180135b42  setz    [rsp+130h+var_F0]
0x180135b47  mov     r13d, 1000h
0x180135b4d  cmp     dword ptr [rcx+14h], 2
0x180135b51  jnz     loc_180135D33
0x180135b57  mov     eax, edx
0x180135b59  sub     eax, edi
0x180135b5b  neg     eax
0x180135b5d  sbb     ax, ax
0x180135b60  add     ax, 202Eh
0x180135b64  mov     [rsp+130h+var_E8], ax
0x180135b69  mov     rcx, [r14+10h]
0x180135b6d  mov     rax, 7FFFFFFFFFFFFFFEh
0x180135b77  cmp     rcx, rax
0x180135b7a  jz      loc_180136091
0x180135b80  mov     rax, r14
0x180135b83  cmp     qword ptr [r14+18h], 7
0x180135b88  jbe     short loc_180135B8D
0x180135b8a  mov     rax, [r14]
0x180135b8d  mov     [rsp+130h+var_100], rcx; __int64
0x180135b92  mov     [rsp+130h+Src], rax; Src
0x180135b97  mov     [rsp+130h+Reserved], rdi; bool
0x180135b9c  lea     r9, [rsp+130h+var_E8]
0x180135ba1  lea     rcx, [rbp+3Fh+var_88]; void *
0x180135ba5  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEB_W_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x180135baa  mov     rcx, qword ptr [rbp+3Fh+var_78]
0x180135bae  cmp     rcx, qword ptr [rbp+3Fh+var_78+8]
0x180135bb2  jnb     short loc_180135BD3
0x180135bb4  lea     rax, [rcx+1]
0x180135bb8  mov     qword ptr [rbp+3Fh+var_78], rax
0x180135bbc  lea     rax, [rbp+3Fh+var_88]
0x180135bc0  cmp     qword ptr [rbp+3Fh+var_78+8], 7
0x180135bc5  cmova   rax, qword ptr [rbp+3Fh+var_88]
0x180135bca  mov     dword ptr [rax+rcx*2], 202Ch
0x180135bd1  jmp     short loc_180135BE2
0x180135bd3  mov     r9d, 202Ch
0x180135bd9  lea     rcx, [rbp+3Fh+var_88]; Src
0x180135bdd  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_W@Z@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAX_W@Z@_W@Z; std::wstring::_Reallocate_grow_by<`std::wstring::push_back(wchar_t)'::`2'::_lambda_1_,wchar_t>(unsigned __int64,`std::wstring::push_back(wchar_t)'::`2'::_lambda_1_,wchar_t)
0x180135be2  movups  xmm0, [rbp+3Fh+var_88]
0x180135be6  movups  xmmword ptr [rbp+3Fh+Block], xmm0
0x180135bea  movups  xmm1, [rbp+3Fh+var_78]
0x180135bee  movups  [rbp+3Fh+var_58], xmm1
0x180135bf2  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x180135bfa  movdqu  [rbp+3Fh+var_78], xmm0
0x180135bff  mov     word ptr [rbp+3Fh+var_88], si
0x180135c03  lea     rdx, [rbp+3Fh+Block]
0x180135c07  mov     rcx, r14
0x180135c0a  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180135c0f  mov     rax, qword ptr [rbp+3Fh+var_58+8]
0x180135c13  cmp     rax, 7
0x180135c17  jbe     short loc_180135C5B
0x180135c19  mov     rcx, [rbp+3Fh+Block]; Block
0x180135c1d  mov     rdx, rcx
0x180135c20  lea     rax, ds:2[rax*2]
0x180135c28  cmp     rax, r13
0x180135c2b  jb      short loc_180135C54
0x180135c2d  mov     rcx, [rcx-8]
0x180135c31  sub     rdx, rcx
0x180135c34  lea     rax, [rdx-8]
0x180135c38  cmp     rax, 1Fh
0x180135c3c  jbe     short loc_180135C54
0x180135c3e  mov     [rsp+130h+Reserved], rsi; Reserved
0x180135c43  xor     r9d, r9d; LineNo
0x180135c46  xor     r8d, r8d; FileName
0x180135c49  xor     edx, edx; FunctionName
0x180135c4b  xor     ecx, ecx; Expression
0x180135c4d  call    cs:__imp__invoke_watson
0x180135c54  call    cs:__imp_free
0x180135c5a  nop
0x180135c5b  lea     rcx, [rbp+3Fh+var_88]; void *
0x180135c5f  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180135c64  mov     rcx, [r14+20h]
0x180135c68  mov     rax, [r14+28h]
0x180135c6c  sub     rax, rcx
0x180135c6f  sar     rax, 3
0x180135c73  imul    rax, rbx
0x180135c77  test    rax, rax
0x180135c7a  jz      loc_18013605F
0x180135c80  add     [rcx+84h], edi
0x180135c86  mov     r9d, edi
0x180135c89  mov     rcx, [r14+28h]
0x180135c8d  mov     rdx, [r14+20h]
0x180135c91  mov     rax, rcx
0x180135c94  sub     rax, rdx
0x180135c97  sar     rax, 3
0x180135c9b  imul    rax, rbx
0x180135c9f  cmp     rax, rdi
0x180135ca2  jbe     short loc_180135CEE
0x180135ca4  mov     r8, rdi
0x180135ca7  mov     rax, [r14+28h]
0x180135cab  sub     rax, rdx
0x180135cae  sar     rax, 3
0x180135cb2  imul    rax, rbx
0x180135cb6  cmp     r8, rax
0x180135cb9  jnb     loc_18013605F
0x180135cbf  imul    rax, r8, 0D8h
0x180135cc6  add     [rax+rdx+80h], edi
0x180135ccd  add     r9d, edi
0x180135cd0  mov     rcx, [r14+28h]
0x180135cd4  mov     rdx, [r14+20h]
0x180135cd8  mov     r8d, r9d
0x180135cdb  mov     rax, rcx
0x180135cde  sub     rax, rdx
0x180135ce1  sar     rax, 3
0x180135ce5  imul    rax, rbx
0x180135ce9  cmp     r8, rax
0x180135cec  jb      short loc_180135CA7
0x180135cee  sub     rcx, rdx
0x180135cf1  sar     rcx, 3
0x180135cf5  imul    rcx, rbx
0x180135cf9  lea     rax, [rcx-1]
0x180135cfd  cmp     rax, rcx
0x180135d00  jnb     loc_18013605F
0x180135d06  imul    rax, 0D8h
0x180135d0d  add     [rax+rdx+84h], edi
0x180135d14  mov     rcx, [r14+20h]
0x180135d18  mov     rax, [r14+28h]
0x180135d1c  sub     rax, rcx
0x180135d1f  sar     rax, 3
0x180135d23  imul    rax, rbx
0x180135d27  test    rax, rax
0x180135d2a  jz      loc_18013605F
0x180135d30  mov     [rcx+14h], esi
0x180135d33  mov     r12, [r14+10h]
0x180135d37  mov     eax, 0FFFFFFFFh
0x180135d3c  cmp     r12, rax
0x180135d3f  ja      loc_180136075
0x180135d45  mov     eax, r12d
0x180135d48  shr     eax, 1
0x180135d4a  mov     r15d, 0Ah
0x180135d50  cmp     eax, r15d
0x180135d53  cmova   r15d, eax
0x180135d57  lea     eax, [r15+1]
0x180135d5b  mov     edi, eax
0x180135d5d  xorps   xmm0, xmm0
0x180135d60  movdqu  xmmword ptr [rsp+130h+var_E0], xmm0
0x180135d66  mov     [rsp+130h+var_D0], rsi
0x180135d6b  lea     rbx, ds:0[rax*8]
0x180135d73  test    rbx, rbx
0x180135d76  jnz     loc_180135E13
0x180135d7c  mov     rax, rsi
0x180135d7f  mov     [rsp+130h+var_E0], rax
0x180135d84  add     rbx, rax
0x180135d87  mov     [rsp+130h+var_D0], rbx
0x180135d8c  lea     r8, ds:0[rdi*8]; Size
0x180135d94  xor     edx, edx; Val
0x180135d96  mov     rcx, rax; void *
0x180135d99  call    memset_0
0x180135d9e  mov     [rsp+130h+var_E0+8], rbx
0x180135da3  mov     [rsp+130h+var_C0], rsi
0x180135da8  lea     rcx, [rsp+130h+var_C0]
0x180135dad  call    ??1?$_Tidy_guard@V?$vector@NV?$allocator@N@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<double>>::~_Tidy_guard<std::vector<double>>(void)
0x180135db2  mov     [rsp+130h+var_C8.iCharPos], esi
0x180135db6  mov     r13b, sil
0x180135db9  mov     rdi, [rsp+130h+var_E0+8]
0x180135dbe  mov     rsi, [rsp+130h+var_E0]
0x180135dc3  sub     rdi, rsi
0x180135dc6  sar     rdi, 3
0x180135dca  test    rdi, rdi
0x180135dcd  jz      loc_180136045
0x180135dd3  mov     rbx, r14
0x180135dd6  cmp     qword ptr [r14+18h], 7
0x180135ddb  jbe     short loc_180135DE0
0x180135ddd  mov     rbx, [r14]
0x180135de0  call    cs:__imp_?GetConfig@Immediate@Gfx@@YAAEBVConfig@2@XZ; Gfx::Immediate::GetConfig(void)
0x180135de6  mov     r8d, r15d; int
0x180135de9  mov     edx, r12d; wchar_t *
0x180135dec  mov     rcx, rbx; this
0x180135def  cmp     byte ptr [rax+3Eh], 0
0x180135df3  jz      short loc_180135E5D
0x180135df5  lea     rax, [rsp+130h+var_C8]
0x180135dfa  mov     [rsp+130h+var_100], rax; struct tag_SCRIPT_ITEM *
0x180135dff  mov     [rsp+130h+Src], rsi; unsigned __int16
0x180135e04  mov     r9b, [rsp+130h+var_F0]; int
0x180135e09  call    ?ItemizeStringDWrite@SVG@Mso@@YAJPEB_WHH_NGPEAUtag_SCRIPT_ITEM@@PEAH@Z; Mso::SVG::ItemizeStringDWrite(wchar_t const *,int,int,bool,ushort,tag_SCRIPT_ITEM *,int *)
0x180135e0e  jmp     loc_180135E97
0x180135e13  cmp     rbx, r13
0x180135e16  jb      short loc_180135E44
0x180135e18  lea     rcx, [rbx+27h]; Size
0x180135e1c  cmp     rcx, rbx
0x180135e1f  jbe     loc_18013609D
0x180135e25  call    cs:__imp_malloc
0x180135e2b  mov     rcx, rax
0x180135e2e  test    rax, rax
0x180135e31  jz      short loc_180135E56
0x180135e33  add     rax, 27h ; '''
0x180135e37  and     rax, 0FFFFFFFFFFFFFFE0h
0x180135e3b  mov     [rax-8], rcx
0x180135e3f  jmp     loc_180135D7F
0x180135e44  mov     rcx, rbx; Size
0x180135e47  call    cs:__imp_malloc
0x180135e4d  test    rax, rax
0x180135e50  jnz     loc_180135D7F
0x180135e56  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180135e5c  nop
0x180135e5d  mov     dword ptr [rsp+130h+var_C0], 0
0x180135e65  xor     eax, eax
0x180135e67  cmp     [rbp+3Fh+var_B8], 1
0x180135e6b  setz    al
0x180135e6e  mov     [rsp+130h+var_E8], ax
0x180135e73  lea     rax, [rsp+130h+var_C8]
0x180135e78  mov     [rsp+130h+var_100], rax
0x180135e7d  mov     [rsp+130h+Src], rsi
0x180135e82  lea     rax, [rsp+130h+var_E8]
0x180135e87  mov     [rsp+130h+Reserved], rax
0x180135e8c  lea     r9, [rsp+130h+var_C0]
0x180135e91  call    cs:__imp_MsoScriptItemize
0x180135e97  cmp     eax, 8007000Eh
0x180135e9c  jnz     short loc_180135F18
0x180135e9e  mov     ecx, 80h
0x180135ea3  cmp     r15d, ecx
0x180135ea6  jnb     short loc_180135F18
0x180135ea8  mov     r15d, ecx
0x180135eab  mov     rdi, [rsp+130h+var_E0+8]
0x180135eb0  mov     rcx, rdi
0x180135eb3  mov     rsi, [rsp+130h+var_E0]
0x180135eb8  sub     rcx, rsi
0x180135ebb  sar     rcx, 3
0x180135ebf  lea     ebx, [r15+1]
0x180135ec3  cmp     rcx, rbx
0x180135ec6  jbe     short loc_180135ED1
0x180135ec8  lea     rdi, [rsi+408h]
0x180135ecf  jmp     short loc_180135F11
0x180135ed1  jnb     short loc_180135F2D
0x180135ed3  mov     rax, [rsp+130h+var_D0]
0x180135ed8  sub     rax, rsi
0x180135edb  sar     rax, 3
0x180135edf  cmp     rax, rbx
0x180135ee2  jnb     short loc_180135EF3
0x180135ee4  mov     rdx, rbx
0x180135ee7  lea     rcx, [rsp+130h+var_E0]
0x180135eec  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@Utag_SCRIPT_ITEM@@V?$allocator@Utag_SCRIPT_ITEM@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<tag_SCRIPT_ITEM>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180135ef1  jmp     short loc_180135F23
0x180135ef3  sub     rbx, rcx
0x180135ef6  jz      short loc_180135F11
0x180135ef8  shl     rbx, 3
0x180135efc  mov     r8, rbx; Size
0x180135eff  xor     edx, edx; Val
0x180135f01  mov     rcx, rdi; void *
0x180135f04  call    memset_0
0x180135f09  add     rdi, rbx
0x180135f0c  mov     rsi, [rsp+130h+var_E0]
0x180135f11  mov     [rsp+130h+var_E0+8], rdi
0x180135f16  jmp     short loc_180135F2D
0x180135f18  test    eax, eax
0x180135f1a  js      loc_1801360A7
0x180135f20  mov     r13b, 1
0x180135f23  mov     rsi, [rsp+130h+var_E0]
0x180135f28  mov     rdi, [rsp+130h+var_E0+8]
0x180135f2d  test    r13b, r13b
0x180135f30  jz      loc_180135DC3
0x180135f36  mov     eax, [rsp+130h+var_C8.iCharPos]
0x180135f3a  inc     eax
0x180135f3c  mov     ebx, eax
0x180135f3e  mov     rcx, rdi
0x180135f41  sub     rcx, rsi
0x180135f44  sar     rcx, 3
0x180135f48  cmp     rbx, rcx
0x180135f4b  jnb     short loc_180135F58
0x180135f4d  lea     rax, [rsi+rax*8]
0x180135f51  mov     [rsp+130h+var_E0+8], rax
0x180135f56  jmp     short loc_180135F98
0x180135f58  jbe     short loc_180135F98
  ... truncated ...
```
