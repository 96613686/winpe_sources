# Mso::SVG::StylableRenderer::ComputeFill(Mso::SVG::StyleResolveChain const &,GEL::Rect const *,bool,GEL::IColorResolver const *)

- ea: `0x1800415c0`
- end: `0x180041c36`
- name: `?ComputeFill@StylableRenderer@SVG@Mso@@QEBA?AV?$TCntPtr@UIBrush@GEL@@@3@AEBVStyleResolveChain@23@PEBURect@GEL@@_NPEBUIColorResolver@7@@Z`
- size: `1654`
- prototype: ``
- caller_count: `4`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x18004256c`
- `0x18010beb0`
- `0x180131598`
- `0x18013215c`

## callees

- `0x1800091d0`
- `0x18000d260`
- `0x18000d70c`
- `0x18001a718`
- `0x18001aa14`
- `0x18001aacc`
- `0x18001ccd0`
- `0x18001cd88`
- `0x180023738`
- `0x1800415c0`
- `0x180043a70`
- `0x1800f5d90`
- `0x18013d650`
- `0x18013f760`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180041bed`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180041bf9`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180041c05`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180041c13`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180041c21`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180041c2f`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180041bed`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180041bf9`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180041c05`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180041c13`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180041c21`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180041c2f`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180041818`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180041818`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180041811`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180041811`
- `gfx!?Create@IBrushSolid@GEL@@SA?AV?$TCntPtr@UIBrushSolid@GEL@@@Ofc@@AEBUColor@2@PEBUCropInfo@2@@Z` at `0x180041650`
- `gfx!?Create@IBrushSolid@GEL@@SA?AV?$TCntPtr@UIBrushSolid@GEL@@@Ofc@@AEBUColor@2@PEBUCropInfo@2@@Z` at `0x18004195c`
- `gfx!?Create@IBrushSolid@GEL@@SA?AV?$TCntPtr@UIBrushSolid@GEL@@@Ofc@@AEBUColor@2@PEBUCropInfo@2@@Z` at `0x180041bb0`
- `gfx!?Create@IBrushSolid@GEL@@SA?AV?$TCntPtr@UIBrushSolid@GEL@@@Ofc@@AEBUColor@2@PEBUCropInfo@2@@Z` at `0x180041650`
- `gfx!?Create@IBrushSolid@GEL@@SA?AV?$TCntPtr@UIBrushSolid@GEL@@@Ofc@@AEBUColor@2@PEBUCropInfo@2@@Z` at `0x18004195c`
- `gfx!?Create@IBrushSolid@GEL@@SA?AV?$TCntPtr@UIBrushSolid@GEL@@@Ofc@@AEBUColor@2@PEBUCropInfo@2@@Z` at `0x180041bb0`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
_QWORD *__fastcall Mso::SVG::StylableRenderer::ComputeFill(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3,
        __int64 a4,
        char a5,
        __int64 a6)
{
  void (__fastcall ****v10)(_QWORD); // rax
  void (__fastcall ***v11)(_QWORD); // rcx
  void (*v12)(void); // rax
  struct CrashContext *v13; // rdx
  struct CrashContext *v14; // rdx
  __int32 v15; // xmm1_4
  char v16; // al
  __int64 v17; // rax
  Mso::SVG::Style *v18; // rcx
  struct Mso::SVG::Style *v19; // rax
  void *v20; // rcx
  __int64 v21; // rcx
  _BYTE *v22; // rsi
  __int64 v23; // rcx
  __int64 v24; // rax
  __int128 *v25; // rax
  __int64 v26; // rdx
  __int64 v27; // rax
  __int128 *v28; // rax
  void (__fastcall ****v29)(_QWORD); // rax
  void (__fastcall ***v30)(_QWORD); // rcx
  _QWORD *v31; // rcx
  __int64 PaintServer; // rax
  _QWORD *v33; // rax
  __int64 v34; // rcx
  __int64 v36; // rcx
  __int64 v37; // rax
  __int128 *v38; // rax
  float v39; // xmm1_4
  __int64 v40; // rdx
  __int64 v41; // rax
  __int128 *v42; // rax
  void (__fastcall ****v43)(_QWORD); // rax
  void (__fastcall ***v44)(_QWORD); // rcx
  _QWORD *v45; // [rsp+30h] [rbp-99h] BYREF
  __m128i v46; // [rsp+38h] [rbp-91h] BYREF
  __m128i v47; // [rsp+48h] [rbp-81h] BYREF
  char v48[8]; // [rsp+58h] [rbp-71h] BYREF
  int v49; // [rsp+60h] [rbp-69h] BYREF
  int v50; // [rsp+64h] [rbp-65h]
  __m128i v51; // [rsp+68h] [rbp-61h]
  void *Block[2]; // [rsp+78h] [rbp-51h] BYREF
  __m128i si128; // [rsp+88h] [rbp-41h]
  int v54; // [rsp+98h] [rbp-31h] BYREF
  int v55; // [rsp+9Ch] [rbp-2Dh]
  __m128i v56; // [rsp+A0h] [rbp-29h]
  _BYTE v57[16]; // [rsp+B0h] [rbp-19h] BYREF
  __int64 v58; // [rsp+C0h] [rbp-9h]

  v45 = a2;
  Mso::SVG::StyleResolveChain::SpecialResolver<10,Mso::SVG::Paint>::operator()(v48, &v54, a3, a3[1]);
  if ( v54 == 2 )
    goto LABEL_63;
  if ( !a6
    || (v47 = _mm_load_si128((const __m128i *)&_xmm),
        !(*(unsigned __int8 (__fastcall **)(__int64, __m128i *))(*(_QWORD *)a6 + 24LL))(a6, &v47)) )
  {
    if ( (unsigned int)(v54 - 3) <= 1 )
    {
      v46 = v56;
      v47 = v56;
      if ( !a6 )
        goto LABEL_28;
      v13 = *(struct CrashContext **)(a1 + 16);
      if ( v13 )
      {
        (*(void (__fastcall **)(__int64, __int64, __m128i *))(*(_QWORD *)a6 + 16LL))(a6, (__int64)v13 + 184, &v47);
        v14 = *(struct CrashContext **)(a1 + 16);
        if ( v14 )
        {
          (*(void (__fastcall **)(__int64, __int64, __m128i *))(*(_QWORD *)a6 + 16LL))(a6, (__int64)v14 + 248, &v47);
          COERCE_FLOAT(v15 = _mm_load_si128((const __m128i *)&_xmm).m128i_i32[0]);
          if ( COERCE_FLOAT(COERCE_UNSIGNED_INT(*(float *)v47.m128i_i32 - *(float *)v46.m128i_i32) & v15) >= 0.00000023841858
            || COERCE_FLOAT(COERCE_UNSIGNED_INT(*(float *)&v47.m128i_i32[1] - *(float *)&v46.m128i_i32[1]) & v15) >= 0.00000023841858
            || COERCE_FLOAT(COERCE_UNSIGNED_INT(*(float *)&v47.m128i_i32[2] - *(float *)&v46.m128i_i32[2]) & v15) >= 0.00000023841858
            || (v16 = 0,
                COERCE_FLOAT(COERCE_UNSIGNED_INT(*(float *)&v47.m128i_i32[3] - *(float *)&v46.m128i_i32[3]) & v15) >= 0.00000023841858) )
          {
            v16 = 1;
          }
          if ( !v16 )
          {
LABEL_28:
            v23 = a3[1];
            v24 = *(_QWORD *)(v23 + 16);
            if ( v24 )
            {
              v25 = (__int128 *)(v24 + 968);
            }
            else
            {
              v25 = &Mso::SVG::StyleMetaData<12>::initial;
              if ( *(_QWORD *)(v23 + 8) )
                v25 = (__int128 *)&Mso::SVG::StyleMetaData<12>::inherit;
            }
            if ( !*((_BYTE *)v25 + 8) )
            {
              if ( *a3 )
                v25 = (__int128 *)Mso::SVG::StyleResolveChain::Get<12>(*a3, 8);
              else
                v25 = (__int128 *)Mso::SVG::StyleResolveChain::GetNormal<12>(a3, *(_QWORD *)(v23 + 8));
            }
            *(float *)&v46.m128i_i32[3] = *(float *)&v46.m128i_i32[3] * (float)*(double *)v25;
            if ( a5 )
            {
              v26 = a3[1];
              v27 = *(_QWORD *)(v26 + 16);
              if ( v27 )
              {
                v28 = (__int128 *)(v27 + 272);
              }
              else if ( !*(_BYTE *)(v26 + 24)
                     || (v28 = (__int128 *)&Mso::SVG::StyleMetaData<36>::inherit, !*(_QWORD *)(v26 + 8)) )
              {
                v28 = &Mso::SVG::StyleMetaData<36>::initial;
              }
              if ( !*((_BYTE *)v28 + 8) )
              {
                if ( *a3 )
                  v28 = (__int128 *)Mso::SVG::StyleResolveChain::Get<36>();
                else
                  v28 = (__int128 *)Mso::SVG::StyleResolveChain::GetNormal<36>(a3, *(_QWORD *)(v26 + 8));
              }
              *(float *)&v46.m128i_i32[3] = *(float *)&v46.m128i_i32[3] * (float)*(double *)v28;
            }
            if ( *(float *)&v46.m128i_i32[3] > 0.0 )
            {
              v29 = (void (__fastcall ****)(_QWORD))GEL::IBrushSolid::Create(&v45, &v46, 0);
              v30 = *v29;
              *a2 = *v29;
              if ( v30 )
                (**v30)(v30);
              v31 = v45;
              if ( !v45 )
                goto LABEL_64;
LABEL_51:
              v12 = *(void (**)(void))(*v31 + 8LL);
              goto LABEL_8;
            }
LABEL_63:
            *a2 = 0;
            goto LABEL_64;
          }
          v17 = *(_QWORD *)(a1 + 16);
          if ( v17 )
          {
            v49 = 3;
            v50 = 2;
            v51 = v47;
            *(_OWORD *)Block = 0;
            si128 = _mm_load_si128((const __m128i *)&_xmm);
            LOWORD(Block[0]) = 0;
            v18 = *(Mso::SVG::Style **)(v17 + 152);
            if ( v18 )
            {
              v19 = Mso::SVG::Style::EnsureWritable(v18);
              Mso::SVG::Style::Set<10>(v19, &v49);
              if ( si128.m128i_i64[1] > 7uLL )
              {
                v20 = Block[0];
                if ( (unsigned __int64)(2 * si128.m128i_i64[1] + 2) >= 0x1000 )
                {
                  v20 = (void *)*((_QWORD *)Block[0] - 1);
                  if ( (unsigned __int64)((char *)Block[0] - (char *)v20 - 8) > 0x1F )
                    _invoke_watson(0, 0, 0, 0, 0);
                }
                free(v20);
              }
              v46 = v47;
              v21 = *(_QWORD *)(*(_QWORD *)(a1 + 24) + 64LL);
              v22 = *(_BYTE **)(v21 + 528);
              if ( v22 )
              {
                (**(void (__fastcall ***)(_QWORD))v22)(*(_QWORD *)(v21 + 528));
                v22[536] = 1;
                (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v22 + 8LL))(v22);
                goto LABEL_28;
              }
LABEL_97:
              CrashWithRecovery(0x1E3C3840u, 0);
              JUMPOUT(0x180041C35LL);
            }
LABEL_96:
            CrashWithRecovery(0x1E3C3840u, 0);
            goto LABEL_97;
          }
LABEL_95:
          CrashWithRecovery(0x1E3C3843u, 0);
          goto LABEL_96;
        }
LABEL_94:
        CrashWithRecovery(0x1E3C3843u, v14);
        goto LABEL_95;
      }
LABEL_93:
      CrashWithRecovery(0x1E3C3843u, v13);
      goto LABEL_94;
    }
    if ( v58 )
    {
      PaintServer = Mso::SVG::Environment::QueryPaintServer(*(_QWORD *)(*(_QWORD *)(a1 + 24) + 64LL), v57);
      if ( PaintServer )
      {
        Mso::SVG::PaintServerRenderer::Create(&v46, PaintServer, *(_QWORD *)(a1 + 24));
        Mso::SVG::EnvironmentRenderer::BeginRecursion(*(Mso::SVG::EnvironmentRenderer **)(a1 + 24));
        if ( !v46.m128i_i64[0] )
        {
          CrashWithRecovery(0x1E3C3840u, 0);
          goto LABEL_93;
        }
        (*(void (__fastcall **)(__int64, _QWORD **, _QWORD *, __int64, _BYTE))(*(_QWORD *)v46.m128i_i64[0] + 32LL))(
          v46.m128i_i64[0],
          &v45,
          a3,
          a4,
          0);
        --**(_DWORD **)(a1 + 24);
        v33 = v45;
        if ( v45 )
        {
          v45 = 0;
          *a2 = v33;
          v31 = (_QWORD *)v46.m128i_i64[0];
          if ( !v46.m128i_i64[0] )
            goto LABEL_64;
          v46.m128i_i64[0] = 0;
          goto LABEL_51;
        }
        v34 = v46.m128i_i64[0];
        if ( v46.m128i_i64[0] )
        {
          v46.m128i_i64[0] = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 8LL))(v34);
        }
      }
    }
    if ( v54 == 1 )
    {
      v49 = v55;
      v50 = 2;
      v51 = v56;
      *(_OWORD *)Block = 0;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(Block[0]) = 0;
      if ( v55 != 2 )
      {
        v47 = v56;
        v36 = a3[1];
        v37 = *(_QWORD *)(v36 + 16);
        if ( v37 )
        {
          v38 = (__int128 *)(v37 + 968);
        }
        else
        {
          v38 = &Mso::SVG::StyleMetaData<12>::initial;
          if ( *(_QWORD *)(v36 + 8) )
            v38 = (__int128 *)&Mso::SVG::StyleMetaData<12>::inherit;
        }
        if ( !*((_BYTE *)v38 + 8) )
        {
          if ( *a3 )
            v38 = (__int128 *)Mso::SVG::StyleResolveChain::Get<12>(*a3, 8);
          else
            v38 = (__int128 *)Mso::SVG::StyleResolveChain::GetNormal<12>(a3, *(_QWORD *)(v36 + 8));
        }
        v39 = *(double *)v38;
        *(float *)&v47.m128i_i32[3] = v39;
        if ( a5 )
        {
          v40 = a3[1];
          v41 = *(_QWORD *)(v40 + 16);
          if ( v41 )
          {
            v42 = (__int128 *)(v41 + 272);
          }
          else if ( !*(_BYTE *)(v40 + 24)
                 || (v42 = (__int128 *)&Mso::SVG::StyleMetaData<36>::inherit, !*(_QWORD *)(v40 + 8)) )
          {
            v42 = &Mso::SVG::StyleMetaData<36>::initial;
          }
          if ( !*((_BYTE *)v42 + 8) )
          {
            if ( *a3 )
              v42 = (__int128 *)Mso::SVG::StyleResolveChain::Get<36>();
            else
              v42 = (__int128 *)Mso::SVG::StyleResolveChain::GetNormal<36>(a3, *(_QWORD *)(v40 + 8));
            v39 = *(float *)&v47.m128i_i32[3];
          }
          v39 = v39 * (float)*(double *)v42;
          *(float *)&v47.m128i_i32[3] = v39;
        }
        if ( v39 > 0.0 )
        {
          v43 = (void (__fastcall ****)(_QWORD))GEL::IBrushSolid::Create(&v45, &v47, 0);
          v44 = *v43;
          *a2 = *v43;
          if ( v44 )
            (**v44)(v44);
          if ( v45 )
            (*(void (__fastcall **)(_QWORD *))(*v45 + 8LL))(v45);
        }
        else
        {
          *a2 = 0;
        }
        std::wstring::~wstring(Block);
        goto LABEL_64;
      }
      Block[0] = (void *)19937;
      si128.m128i_i64[1] = 15;
    }
    goto LABEL_63;
  }
  v10 = (void (__fastcall ****)(_QWORD))GEL::IBrushSolid::Create(&v45, &v47, 0);
  v11 = *v10;
  *a2 = *v10;
  if ( v11 )
    (**v11)(v11);
  if ( v45 )
  {
    v12 = *(void (**)(void))(*v45 + 8LL);
LABEL_8:
    v12();
  }
LABEL_64:
  std::wstring::~wstring(v57);
  return a2;
}

```

## disassembly

```asm
0x1800415c0  push    rbp
0x1800415c2  push    rbx
0x1800415c3  push    rsi
0x1800415c4  push    rdi
0x1800415c5  push    r12
0x1800415c7  push    r14
0x1800415c9  push    r15
0x1800415cb  lea     rbp, [rsp-17h]
0x1800415d0  sub     rsp, 0E0h
0x1800415d7  mov     rax, cs:__security_cookie
0x1800415de  xor     rax, rsp
0x1800415e1  mov     [rbp+47h+var_40], rax
0x1800415e5  mov     r15, r9
0x1800415e8  mov     rdi, r8
0x1800415eb  mov     rbx, rdx
0x1800415ee  mov     r14, rcx
0x1800415f1  mov     [rsp+110h+var_E0], rdx
0x1800415f6  mov     rsi, [rbp+47h+arg_28]
0x1800415fa  xor     r12d, r12d
0x1800415fd  mov     r9, [r8+8]
0x180041601  lea     rdx, [rbp+47h+var_78]
0x180041605  lea     rcx, [rbp+47h+var_B8]
0x180041609  call    ??R?$SpecialResolver@$09VPaint@SVG@Mso@@@StyleResolveChain@SVG@Mso@@QEBA?AVPaint@23@AEBV123@AEBVStyle@23@@Z; Mso::SVG::StyleResolveChain::SpecialResolver<10,Mso::SVG::Paint>::operator()(Mso::SVG::StyleResolveChain const &,Mso::SVG::Style const &)
0x18004160e  cmp     [rbp+47h+var_78], 2
0x180041612  jz      loc_180041A8F
0x180041618  test    rsi, rsi
0x18004161b  jz      short loc_18004168D
0x18004161d  movdqa  xmm0, cs:__xmm@3f800000000000000000000000000000
0x180041625  movups  [rsp+110h+var_C8], xmm0
0x18004162a  mov     rax, [rsi]
0x18004162d  lea     rdx, [rsp+110h+var_C8]
0x180041632  mov     rcx, rsi
0x180041635  mov     rax, [rax+18h]
0x180041639  call    cs:__guard_dispatch_icall_fptr
0x18004163f  test    al, al
0x180041641  jz      short loc_18004168D
0x180041643  xor     r8d, r8d
0x180041646  lea     rdx, [rsp+110h+var_C8]
0x18004164b  lea     rcx, [rsp+110h+var_E0]
0x180041650  call    cs:__imp_?Create@IBrushSolid@GEL@@SA?AV?$TCntPtr@UIBrushSolid@GEL@@@Ofc@@AEBUColor@2@PEBUCropInfo@2@@Z; GEL::IBrushSolid::Create(GEL::Color const &,GEL::CropInfo const *)
0x180041656  mov     rcx, [rax]
0x180041659  mov     [rbx], rcx
0x18004165c  test    rcx, rcx
0x18004165f  jz      short loc_18004166D
0x180041661  mov     rax, [rcx]
0x180041664  mov     rax, [rax]
0x180041667  call    cs:__guard_dispatch_icall_fptr
0x18004166d  mov     rcx, [rsp+110h+var_E0]
0x180041672  test    rcx, rcx
0x180041675  jz      loc_180041A92
0x18004167b  mov     rdx, [rcx]
0x18004167e  mov     rax, [rdx+8]
0x180041682  call    cs:__guard_dispatch_icall_fptr
0x180041688  jmp     loc_180041A92
0x18004168d  mov     eax, [rbp+47h+var_78]
0x180041690  add     eax, 0FFFFFFFDh
0x180041693  cmp     eax, 1
0x180041696  ja      loc_180041993
0x18004169c  movups  xmm0, [rbp+47h+var_70]
0x1800416a0  movups  [rsp+110h+var_D8], xmm0
0x1800416a5  movups  [rsp+110h+var_C8], xmm0
0x1800416aa  test    rsi, rsi
0x1800416ad  jz      loc_18004186C
0x1800416b3  mov     rax, [rsi]
0x1800416b6  mov     rax, [rax+10h]
0x1800416ba  mov     rdx, [r14+10h]
0x1800416be  test    rdx, rdx
0x1800416c1  jz      loc_180041BF4
0x1800416c7  add     rdx, 0B8h
0x1800416ce  lea     r8, [rsp+110h+var_C8]
0x1800416d3  mov     rcx, rsi
0x1800416d6  call    cs:__guard_dispatch_icall_fptr
0x1800416dc  mov     rax, [rsi]
0x1800416df  mov     rax, [rax+10h]
0x1800416e3  mov     rdx, [r14+10h]
0x1800416e7  test    rdx, rdx
0x1800416ea  jz      loc_180041C00
0x1800416f0  add     rdx, 0F8h
0x1800416f7  lea     r8, [rsp+110h+var_C8]
0x1800416fc  mov     rcx, rsi
0x1800416ff  call    cs:__guard_dispatch_icall_fptr
0x180041705  movss   xmm0, dword ptr [rsp+110h+var_C8]
0x18004170b  subss   xmm0, dword ptr [rsp+110h+var_D8]
0x180041711  movdqa  xmm1, cs:__xmm@7fffffff7fffffff7fffffff7fffffff
0x180041719  andps   xmm0, xmm1
0x18004171c  movss   xmm2, cs:__real@34800000
0x180041724  comiss  xmm2, xmm0
0x180041727  jbe     short loc_180041765
0x180041729  movss   xmm0, dword ptr [rbp+47h+var_C8+4]
0x18004172e  subss   xmm0, dword ptr [rsp+110h+var_D8+4]
0x180041734  andps   xmm0, xmm1
0x180041737  comiss  xmm2, xmm0
0x18004173a  jbe     short loc_180041765
0x18004173c  movss   xmm0, dword ptr [rbp+47h+var_C8+8]
0x180041741  subss   xmm0, dword ptr [rsp+110h+var_D8+8]
0x180041747  andps   xmm0, xmm1
0x18004174a  comiss  xmm2, xmm0
0x18004174d  jbe     short loc_180041765
0x18004174f  movss   xmm0, dword ptr [rbp+47h+var_C8+0Ch]
0x180041754  subss   xmm0, dword ptr [rsp+110h+var_D8+0Ch]
0x18004175a  andps   xmm0, xmm1
0x18004175d  comiss  xmm2, xmm0
0x180041760  mov     al, r12b
0x180041763  ja      short loc_180041767
0x180041765  mov     al, 1
0x180041767  test    al, al
0x180041769  jz      loc_18004186C
0x18004176f  mov     rax, [r14+10h]
0x180041773  test    rax, rax
0x180041776  jz      loc_180041C0C
0x18004177c  mov     [rbp+47h+var_B0], 3
0x180041783  mov     [rbp+47h+var_AC], 2
0x18004178a  movups  xmm0, [rsp+110h+var_C8]
0x18004178f  movdqu  [rbp+47h+var_A8], xmm0
0x180041794  xorps   xmm1, xmm1
0x180041797  movups  xmmword ptr [rbp+47h+Block], xmm1
0x18004179b  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x1800417a3  movdqu  [rbp+47h+var_88], xmm0
0x1800417a8  mov     word ptr [rbp+47h+Block], r12w
0x1800417ad  mov     rcx, [rax+98h]; this
0x1800417b4  test    rcx, rcx
0x1800417b7  jz      loc_180041C1A
0x1800417bd  call    ?EnsureWritable@Style@SVG@Mso@@AEAAAEAV123@XZ; Mso::SVG::Style::EnsureWritable(void)
0x1800417c2  lea     rdx, [rbp+47h+var_B0]
0x1800417c6  mov     rcx, rax
0x1800417c9  call    ??$Set@$09@Style@SVG@Mso@@QEAAX$$QEAVPaint@12@@Z; Mso::SVG::Style::Set<10>(Mso::SVG::Paint &&)
0x1800417ce  nop
0x1800417cf  nop
0x1800417d0  mov     rax, qword ptr [rbp+47h+var_88+8]
0x1800417d4  cmp     rax, 7
0x1800417d8  jbe     short loc_18004181E
0x1800417da  mov     rcx, [rbp+47h+Block]; Block
0x1800417de  mov     rdx, rcx
0x1800417e1  lea     rax, ds:2[rax*2]
0x1800417e9  cmp     rax, 1000h
0x1800417ef  jb      short loc_180041818
0x1800417f1  mov     rcx, [rcx-8]
0x1800417f5  sub     rdx, rcx
0x1800417f8  lea     rax, [rdx-8]
0x1800417fc  cmp     rax, 1Fh
0x180041800  jbe     short loc_180041818
0x180041802  mov     [rsp+110h+Reserved], r12; Reserved
0x180041807  xor     r9d, r9d; LineNo
0x18004180a  xor     r8d, r8d; FileName
0x18004180d  xor     edx, edx; FunctionName
0x18004180f  xor     ecx, ecx; Expression
0x180041811  call    cs:__imp__invoke_watson
0x180041818  call    cs:__imp_free
0x18004181e  movups  xmm0, [rsp+110h+var_C8]
0x180041823  movups  [rsp+110h+var_D8], xmm0
0x180041828  mov     rax, [r14+18h]
0x18004182c  mov     rcx, [rax+40h]
0x180041830  mov     rsi, [rcx+210h]
0x180041837  test    rsi, rsi
0x18004183a  jz      short loc_18004184C
0x18004183c  mov     rax, [rsi]
0x18004183f  mov     rcx, rsi
0x180041842  mov     rax, [rax]
0x180041845  call    cs:__guard_dispatch_icall_fptr
0x18004184b  nop
0x18004184c  test    rsi, rsi
0x18004184f  jz      loc_180041C28
0x180041855  mov     byte ptr [rsi+218h], 1
0x18004185c  mov     rax, [rsi]
0x18004185f  mov     rcx, rsi
0x180041862  mov     rax, [rax+8]
0x180041866  call    cs:__guard_dispatch_icall_fptr
0x18004186c  mov     rcx, [rdi+8]
0x180041870  mov     rax, [rcx+10h]
0x180041874  test    rax, rax
0x180041877  jz      short loc_180041881
0x180041879  add     rax, 3C8h
0x18004187f  jmp     short loc_180041895
0x180041881  cmp     [rcx+8], r12
0x180041885  lea     rax, ?initial@?$StyleMetaData@$0M@@SVG@Mso@@2V?$optional@N@std@@B; std::optional<double> const Mso::SVG::StyleMetaData<12>::initial
0x18004188c  jz      short loc_180041895
0x18004188e  lea     rax, ?inherit@?$StyleMetaData@$0M@@SVG@Mso@@2V?$optional@N@std@@B; std::optional<double> const Mso::SVG::StyleMetaData<12>::inherit
0x180041895  mov     edx, 8
0x18004189a  cmp     [rax+8], r12b
0x18004189e  jnz     short loc_1800418BB
0x1800418a0  cmp     [rdi], r12
0x1800418a3  jz      short loc_1800418AF
0x1800418a5  mov     rcx, [rdi]
0x1800418a8  call    ??$Get@$0M@@StyleResolveChain@SVG@Mso@@QEBAAEBNXZ; Mso::SVG::StyleResolveChain::Get<12>(void)
0x1800418ad  jmp     short loc_1800418BB
0x1800418af  mov     rdx, [rdx+rcx]
0x1800418b3  mov     rcx, rdi
0x1800418b6  call    ??$GetNormal@$0M@@StyleResolveChain@SVG@Mso@@AEBAAEBNAEBVStyle@12@@Z; Mso::SVG::StyleResolveChain::GetNormal<12>(Mso::SVG::Style const &)
0x1800418bb  movsd   xmm0, qword ptr [rax]
0x1800418bf  cvtpd2ps xmm0, xmm0
0x1800418c3  movss   xmm1, dword ptr [rsp+110h+var_D8+0Ch]
0x1800418c9  mulss   xmm1, xmm0
0x1800418cd  movss   dword ptr [rsp+110h+var_D8+0Ch], xmm1
0x1800418d3  cmp     [rbp+47h+arg_20], r12b
0x1800418d7  jz      short loc_180041941
0x1800418d9  mov     rdx, [rdi+8]
0x1800418dd  mov     rax, [rdx+10h]
0x1800418e1  test    rax, rax
0x1800418e4  jz      short loc_1800418EE
0x1800418e6  add     rax, 110h
0x1800418ec  jmp     short loc_180041908
0x1800418ee  cmp     [rdx+18h], r12b
0x1800418f2  jz      short loc_180041901
0x1800418f4  cmp     [rdx+8], r12
0x1800418f8  lea     rax, ?inherit@?$StyleMetaData@$0CE@@SVG@Mso@@2V?$optional@N@std@@B; std::optional<double> const Mso::SVG::StyleMetaData<36>::inherit
0x1800418ff  jnz     short loc_180041908
0x180041901  lea     rax, ?initial@?$StyleMetaData@$0CE@@SVG@Mso@@2V?$optional@N@std@@B; std::optional<double> const Mso::SVG::StyleMetaData<36>::initial
0x180041908  cmp     [rax+8], r12b
0x18004190c  jnz     short loc_180041929
0x18004190e  mov     rcx, [rdi]
0x180041911  test    rcx, rcx
0x180041914  jz      short loc_18004191D
0x180041916  call    ??$Get@$0CE@@StyleResolveChain@SVG@Mso@@QEBAAEBNXZ; Mso::SVG::StyleResolveChain::Get<36>(void)
0x18004191b  jmp     short loc_180041929
0x18004191d  mov     rdx, [rdx+8]
0x180041921  mov     rcx, rdi
0x180041924  call    ??$GetNormal@$0CE@@StyleResolveChain@SVG@Mso@@AEBAAEBNAEBVStyle@12@@Z; Mso::SVG::StyleResolveChain::GetNormal<36>(Mso::SVG::Style const &)
0x180041929  movsd   xmm0, qword ptr [rax]
0x18004192d  cvtpd2ps xmm0, xmm0
0x180041931  movss   xmm1, dword ptr [rsp+110h+var_D8+0Ch]
0x180041937  mulss   xmm1, xmm0
0x18004193b  movss   dword ptr [rsp+110h+var_D8+0Ch], xmm1
0x180041941  xorps   xmm0, xmm0
0x180041944  comiss  xmm0, dword ptr [rsp+110h+var_D8+0Ch]
0x180041949  jnb     loc_180041A8F
0x18004194f  xor     r8d, r8d
0x180041952  lea     rdx, [rsp+110h+var_D8]
0x180041957  lea     rcx, [rsp+110h+var_E0]
0x18004195c  call    cs:__imp_?Create@IBrushSolid@GEL@@SA?AV?$TCntPtr@UIBrushSolid@GEL@@@Ofc@@AEBUColor@2@PEBUCropInfo@2@@Z; GEL::IBrushSolid::Create(GEL::Color const &,GEL::CropInfo const *)
0x180041962  mov     rcx, [rax]
0x180041965  mov     [rbx], rcx
0x180041968  test    rcx, rcx
0x18004196b  jz      short loc_180041979
0x18004196d  mov     rax, [rcx]
0x180041970  mov     rax, [rax]
0x180041973  call    cs:__guard_dispatch_icall_fptr
0x180041979  mov     rcx, [rsp+110h+var_E0]
0x18004197e  test    rcx, rcx
0x180041981  jz      loc_180041A92
0x180041987  mov     rax, [rcx]
0x18004198a  mov     rax, [rax+8]
0x18004198e  jmp     loc_180041682
0x180041993  cmp     [rbp+47h+var_50], r12
0x180041997  jz      loc_180041A46
0x18004199d  mov     rax, [r14+18h]
0x1800419a1  lea     rdx, [rbp+47h+var_60]
0x1800419a5  mov     rcx, [rax+40h]
0x1800419a9  call    ?QueryPaintServer@Environment@SVG@Mso@@QEAAPEAVPaintServerContext@23@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Mso::SVG::Environment::QueryPaintServer(std::wstring const &)
0x1800419ae  test    rax, rax
0x1800419b1  jz      loc_180041A46
0x1800419b7  mov     r8, [r14+18h]
0x1800419bb  mov     rdx, rax
0x1800419be  lea     rcx, [rsp+110h+var_D8]
0x1800419c3  call    ?Create@PaintServerRenderer@SVG@Mso@@SA?AV?$TCntPtr@VPaintServerRenderer@SVG@Mso@@@3@AEAVPaintServerContext@23@AEAVEnvironmentRenderer@23@@Z; Mso::SVG::PaintServerRenderer::Create(Mso::SVG::PaintServerContext &,Mso::SVG::EnvironmentRenderer &)
0x1800419c8  nop
0x1800419c9  mov     rcx, [r14+18h]; this
0x1800419cd  call    ?BeginRecursion@EnvironmentRenderer@SVG@Mso@@QEAAXXZ; Mso::SVG::EnvironmentRenderer::BeginRecursion(void)
0x1800419d2  nop
0x1800419d3  mov     rcx, qword ptr [rsp+110h+var_D8]
0x1800419d8  test    rcx, rcx
0x1800419db  jz      loc_180041BE6
0x1800419e1  mov     rax, [rcx]
0x1800419e4  mov     byte ptr [rsp+110h+Reserved], r12b
0x1800419e9  mov     r9, r15
0x1800419ec  mov     r8, rdi
0x1800419ef  lea     rdx, [rsp+110h+var_E0]
0x1800419f4  mov     rax, [rax+20h]
0x1800419f8  call    cs:__guard_dispatch_icall_fptr
0x1800419fe  mov     rax, [r14+18h]
0x180041a02  dec     dword ptr [rax]
0x180041a04  mov     rax, [rsp+110h+var_E0]
0x180041a09  test    rax, rax
0x180041a0c  jz      short loc_180041A2A
0x180041a0e  mov     [rsp+110h+var_E0], r12
0x180041a13  mov     [rbx], rax
0x180041a16  mov     rcx, qword ptr [rsp+110h+var_D8]
0x180041a1b  test    rcx, rcx
0x180041a1e  jz      short loc_180041A92
0x180041a20  mov     qword ptr [rsp+110h+var_D8], r12
0x180041a25  jmp     loc_180041987
0x180041a2a  mov     rcx, qword ptr [rsp+110h+var_D8]
0x180041a2f  test    rcx, rcx
0x180041a32  jz      short loc_180041A46
0x180041a34  mov     qword ptr [rsp+110h+var_D8], r12
0x180041a39  mov     rax, [rcx]
0x180041a3c  mov     rax, [rax+8]
0x180041a40  call    cs:__guard_dispatch_icall_fptr
0x180041a46  cmp     [rbp+47h+var_78], 1
0x180041a4a  jnz     short loc_180041A8F
0x180041a4c  mov     eax, [rbp+47h+var_74]
0x180041a4f  mov     [rbp+47h+var_B0], eax
0x180041a52  mov     [rbp+47h+var_AC], 2
0x180041a59  movups  xmm2, [rbp+47h+var_70]
0x180041a5d  movups  [rbp+47h+var_A8], xmm2
0x180041a61  xorps   xmm0, xmm0
0x180041a64  movups  xmmword ptr [rbp+47h+Block], xmm0
0x180041a68  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180041a70  movdqu  [rbp+47h+var_88], xmm1
0x180041a75  mov     word ptr [rbp+47h+Block], r12w
0x180041a7a  cmp     eax, 2
  ... truncated ...
```
