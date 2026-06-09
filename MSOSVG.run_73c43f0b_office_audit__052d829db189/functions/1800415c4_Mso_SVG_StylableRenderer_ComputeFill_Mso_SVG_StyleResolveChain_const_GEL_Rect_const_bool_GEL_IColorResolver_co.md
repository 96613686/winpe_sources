# Mso::SVG::StylableRenderer::ComputeFill(Mso::SVG::StyleResolveChain const &,GEL::Rect const *,bool,GEL::IColorResolver const *)

- ea: `0x1800415c4`
- end: `0x180041c4b`
- name: `?ComputeFill@StylableRenderer@SVG@Mso@@QEBA?AV?$TCntPtr@UIBrush@GEL@@@3@AEBVStyleResolveChain@23@PEBURect@GEL@@_NPEBUIColorResolver@7@@Z`
- size: `1671`
- prototype: ``
- caller_count: `4`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x180042580`
- `0x18010bee0`
- `0x1801315c8`
- `0x18013219c`

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
- `0x1800415c4`
- `0x180043a88`
- `0x1800f5db0`
- `0x18013d700`
- `0x18013f810`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180041c02`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180041c0e`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180041c1a`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180041c28`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180041c36`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180041c44`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180041c02`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180041c0e`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180041c1a`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180041c28`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180041c36`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180041c44`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18004181b`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18004181b`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180041814`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180041814`
- `gfx!?Create@IBrushSolid@GEL@@SA?AV?$TCntPtr@UIBrushSolid@GEL@@@Ofc@@AEBUColor@2@PEBUCropInfo@2@@Z` at `0x180041654`
- `gfx!?Create@IBrushSolid@GEL@@SA?AV?$TCntPtr@UIBrushSolid@GEL@@@Ofc@@AEBUColor@2@PEBUCropInfo@2@@Z` at `0x18004195f`
- `gfx!?Create@IBrushSolid@GEL@@SA?AV?$TCntPtr@UIBrushSolid@GEL@@@Ofc@@AEBUColor@2@PEBUCropInfo@2@@Z` at `0x180041b98`
- `gfx!?Create@IBrushSolid@GEL@@SA?AV?$TCntPtr@UIBrushSolid@GEL@@@Ofc@@AEBUColor@2@PEBUCropInfo@2@@Z` at `0x180041654`
- `gfx!?Create@IBrushSolid@GEL@@SA?AV?$TCntPtr@UIBrushSolid@GEL@@@Ofc@@AEBUColor@2@PEBUCropInfo@2@@Z` at `0x18004195f`
- `gfx!?Create@IBrushSolid@GEL@@SA?AV?$TCntPtr@UIBrushSolid@GEL@@@Ofc@@AEBUColor@2@PEBUCropInfo@2@@Z` at `0x180041b98`

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
  __int64 *v25; // rax
  __int64 v26; // rdx
  __int64 v27; // rax
  __int64 *v28; // rax
  void (__fastcall ****v29)(_QWORD); // rax
  void (__fastcall ***v30)(_QWORD); // rcx
  _QWORD *v31; // rcx
  __int64 PaintServer; // rax
  _QWORD *v33; // rax
  __int64 v34; // rcx
  __int64 v35; // rcx
  __int64 v36; // rax
  __int64 *v37; // rax
  float v38; // xmm1_4
  __int64 v39; // rdx
  __int64 v40; // rax
  __int64 *v41; // rax
  void (__fastcall ****v42)(_QWORD); // rax
  void (__fastcall ***v43)(_QWORD); // rcx
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
    goto LABEL_90;
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
              v25 = (__int64 *)(v24 + 968);
            }
            else
            {
              v25 = (__int64 *)&Mso::SVG::StyleMetaData<12>::initial;
              if ( *(_QWORD *)(v23 + 8) )
                v25 = Mso::SVG::StyleMetaData<12>::inherit;
            }
            if ( !*((_BYTE *)v25 + 8) )
            {
              if ( *a3 )
                v25 = (__int64 *)Mso::SVG::StyleResolveChain::Get<12>(*a3, 8);
              else
                v25 = (__int64 *)Mso::SVG::StyleResolveChain::GetNormal<12>(a3, *(_QWORD *)(v23 + 8));
            }
            *(float *)&v46.m128i_i32[3] = *(float *)&v46.m128i_i32[3] * (float)*(double *)v25;
            if ( a5 )
            {
              v26 = a3[1];
              v27 = *(_QWORD *)(v26 + 16);
              if ( v27 )
              {
                v28 = (__int64 *)(v27 + 272);
              }
              else if ( !*(_BYTE *)(v26 + 24) || (v28 = Mso::SVG::StyleMetaData<36>::inherit, !*(_QWORD *)(v26 + 8)) )
              {
                v28 = (__int64 *)&Mso::SVG::StyleMetaData<36>::initial;
              }
              if ( !*((_BYTE *)v28 + 8) )
              {
                if ( *a3 )
                  v28 = (__int64 *)Mso::SVG::StyleResolveChain::Get<36>();
                else
                  v28 = (__int64 *)Mso::SVG::StyleResolveChain::GetNormal<36>(a3, *(_QWORD *)(v26 + 8));
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
                goto LABEL_91;
LABEL_51:
              v12 = *(void (**)(void))(*v31 + 8LL);
              goto LABEL_8;
            }
LABEL_90:
            *a2 = 0;
            goto LABEL_91;
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
              JUMPOUT(0x180041C4ALL);
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
            goto LABEL_91;
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
      if ( v55 == 2 )
      {
        *a2 = 0;
        Block[0] = (void *)19937;
        si128 = _mm_load_si128((const __m128i *)&_xmm);
      }
      else
      {
        v47 = v56;
        v35 = a3[1];
        v36 = *(_QWORD *)(v35 + 16);
        if ( v36 )
        {
          v37 = (__int64 *)(v36 + 968);
        }
        else
        {
          v37 = (__int64 *)&Mso::SVG::StyleMetaData<12>::initial;
          if ( *(_QWORD *)(v35 + 8) )
            v37 = Mso::SVG::StyleMetaData<12>::inherit;
        }
        if ( !*((_BYTE *)v37 + 8) )
        {
          if ( *a3 )
            v37 = (__int64 *)Mso::SVG::StyleResolveChain::Get<12>(*a3, 8);
          else
            v37 = (__int64 *)Mso::SVG::StyleResolveChain::GetNormal<12>(a3, *(_QWORD *)(v35 + 8));
        }
        v38 = *(double *)v37;
        *(float *)&v47.m128i_i32[3] = v38;
        if ( a5 )
        {
          v39 = a3[1];
          v40 = *(_QWORD *)(v39 + 16);
          if ( v40 )
          {
            v41 = (__int64 *)(v40 + 272);
          }
          else if ( !*(_BYTE *)(v39 + 24) || (v41 = Mso::SVG::StyleMetaData<36>::inherit, !*(_QWORD *)(v39 + 8)) )
          {
            v41 = (__int64 *)&Mso::SVG::StyleMetaData<36>::initial;
          }
          if ( !*((_BYTE *)v41 + 8) )
          {
            if ( *a3 )
              v41 = (__int64 *)Mso::SVG::StyleResolveChain::Get<36>();
            else
              v41 = (__int64 *)Mso::SVG::StyleResolveChain::GetNormal<36>(a3, *(_QWORD *)(v39 + 8));
            v38 = *(float *)&v47.m128i_i32[3];
          }
          v38 = v38 * (float)*(double *)v41;
          *(float *)&v47.m128i_i32[3] = v38;
        }
        if ( v38 > 0.0 )
        {
          v42 = (void (__fastcall ****)(_QWORD))GEL::IBrushSolid::Create(&v45, &v47, 0);
          v43 = *v42;
          *a2 = *v42;
          if ( v43 )
            (**v43)(v43);
          if ( v45 )
            (*(void (__fastcall **)(_QWORD *))(*v45 + 8LL))(v45);
        }
        else
        {
          *a2 = 0;
        }
        std::wstring::~wstring(Block);
      }
      goto LABEL_91;
    }
    goto LABEL_90;
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
LABEL_91:
  std::wstring::~wstring(v57);
  return a2;
}

```

## disassembly

```asm
0x1800415c4  push    rbp
0x1800415c6  push    rbx
0x1800415c7  push    rsi
0x1800415c8  push    rdi
0x1800415c9  push    r12
0x1800415cb  push    r14
0x1800415cd  push    r15
0x1800415cf  lea     rbp, [rsp-17h]
0x1800415d4  sub     rsp, 0E0h
0x1800415db  mov     rax, cs:__security_cookie
0x1800415e2  xor     rax, rsp
0x1800415e5  mov     [rbp+47h+var_40], rax
0x1800415e9  mov     r15, r9
0x1800415ec  mov     rdi, r8
0x1800415ef  mov     rbx, rdx
0x1800415f2  mov     r14, rcx
0x1800415f5  mov     [rsp+110h+var_E0], rdx
0x1800415fa  mov     rsi, [rbp+47h+arg_28]
0x1800415fe  xor     r12d, r12d
0x180041601  mov     r9, [r8+8]
0x180041605  lea     rdx, [rbp+47h+var_78]
0x180041609  lea     rcx, [rbp+47h+var_B8]
0x18004160d  call    ??R?$SpecialResolver@$09VPaint@SVG@Mso@@@StyleResolveChain@SVG@Mso@@QEBA?AVPaint@23@AEBV123@AEBVStyle@23@@Z; Mso::SVG::StyleResolveChain::SpecialResolver<10,Mso::SVG::Paint>::operator()(Mso::SVG::StyleResolveChain const &,Mso::SVG::Style const &)
0x180041612  cmp     [rbp+47h+var_78], 2
0x180041616  jz      loc_180041BCE
0x18004161c  test    rsi, rsi
0x18004161f  jz      short loc_180041691
0x180041621  movdqa  xmm0, cs:__xmm@3f800000000000000000000000000000
0x180041629  movups  [rsp+110h+var_C8], xmm0
0x18004162e  mov     rax, [rsi]
0x180041631  lea     rdx, [rsp+110h+var_C8]
0x180041636  mov     rcx, rsi
0x180041639  mov     rax, [rax+18h]
0x18004163d  call    cs:__guard_dispatch_icall_fptr
0x180041643  test    al, al
0x180041645  jz      short loc_180041691
0x180041647  xor     r8d, r8d
0x18004164a  lea     rdx, [rsp+110h+var_C8]
0x18004164f  lea     rcx, [rsp+110h+var_E0]
0x180041654  call    cs:__imp_?Create@IBrushSolid@GEL@@SA?AV?$TCntPtr@UIBrushSolid@GEL@@@Ofc@@AEBUColor@2@PEBUCropInfo@2@@Z; GEL::IBrushSolid::Create(GEL::Color const &,GEL::CropInfo const *)
0x18004165a  mov     rcx, [rax]
0x18004165d  mov     [rbx], rcx
0x180041660  test    rcx, rcx
0x180041663  jz      short loc_180041671
0x180041665  mov     rax, [rcx]
0x180041668  mov     rax, [rax]
0x18004166b  call    cs:__guard_dispatch_icall_fptr
0x180041671  mov     rcx, [rsp+110h+var_E0]
0x180041676  test    rcx, rcx
0x180041679  jz      loc_180041BD1
0x18004167f  mov     rdx, [rcx]
0x180041682  mov     rax, [rdx+8]
0x180041686  call    cs:__guard_dispatch_icall_fptr
0x18004168c  jmp     loc_180041BD1
0x180041691  mov     eax, [rbp+47h+var_78]
0x180041694  add     eax, 0FFFFFFFDh
0x180041697  cmp     eax, 1
0x18004169a  ja      loc_180041996
0x1800416a0  movups  xmm0, [rbp+47h+var_70]
0x1800416a4  movups  [rsp+110h+var_D8], xmm0
0x1800416a9  movups  [rsp+110h+var_C8], xmm0
0x1800416ae  test    rsi, rsi
0x1800416b1  jz      loc_18004186F
0x1800416b7  mov     rax, [rsi]
0x1800416ba  mov     rax, [rax+10h]
0x1800416be  mov     rdx, [r14+10h]
0x1800416c2  test    rdx, rdx
0x1800416c5  jz      loc_180041C09
0x1800416cb  add     rdx, 0B8h
0x1800416d2  lea     r8, [rsp+110h+var_C8]
0x1800416d7  mov     rcx, rsi
0x1800416da  call    cs:__guard_dispatch_icall_fptr
0x1800416e0  mov     rax, [rsi]
0x1800416e3  mov     rax, [rax+10h]
0x1800416e7  mov     rdx, [r14+10h]
0x1800416eb  test    rdx, rdx
0x1800416ee  jz      loc_180041C15
0x1800416f4  add     rdx, 0F8h
0x1800416fb  lea     r8, [rsp+110h+var_C8]
0x180041700  mov     rcx, rsi
0x180041703  call    cs:__guard_dispatch_icall_fptr
0x180041709  movss   xmm0, dword ptr [rsp+110h+var_C8]
0x18004170f  subss   xmm0, dword ptr [rsp+110h+var_D8]
0x180041715  movdqa  xmm1, cs:__xmm@7fffffff7fffffff7fffffff7fffffff
0x18004171d  andps   xmm0, xmm1
0x180041720  movss   xmm2, cs:__real@34800000
0x180041728  comiss  xmm2, xmm0
0x18004172b  jbe     short loc_180041769
0x18004172d  movss   xmm0, dword ptr [rbp+47h+var_C8+4]
0x180041732  subss   xmm0, dword ptr [rsp+110h+var_D8+4]
0x180041738  andps   xmm0, xmm1
0x18004173b  comiss  xmm2, xmm0
0x18004173e  jbe     short loc_180041769
0x180041740  movss   xmm0, dword ptr [rbp+47h+var_C8+8]
0x180041745  subss   xmm0, dword ptr [rsp+110h+var_D8+8]
0x18004174b  andps   xmm0, xmm1
0x18004174e  comiss  xmm2, xmm0
0x180041751  jbe     short loc_180041769
0x180041753  movss   xmm0, dword ptr [rbp+47h+var_C8+0Ch]
0x180041758  subss   xmm0, dword ptr [rsp+110h+var_D8+0Ch]
0x18004175e  andps   xmm0, xmm1
0x180041761  comiss  xmm2, xmm0
0x180041764  mov     al, r12b
0x180041767  ja      short loc_18004176B
0x180041769  mov     al, 1
0x18004176b  test    al, al
0x18004176d  jz      loc_18004186F
0x180041773  mov     rax, [r14+10h]
0x180041777  test    rax, rax
0x18004177a  jz      loc_180041C21
0x180041780  mov     [rbp+47h+var_B0], 3
0x180041787  mov     [rbp+47h+var_AC], 2
0x18004178e  movups  xmm0, [rsp+110h+var_C8]
0x180041793  movdqu  [rbp+47h+var_A8], xmm0
0x180041798  xorps   xmm1, xmm1
0x18004179b  movups  xmmword ptr [rbp+47h+Block], xmm1
0x18004179f  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x1800417a7  movdqu  [rbp+47h+var_88], xmm0
0x1800417ac  mov     word ptr [rbp+47h+Block], r12w
0x1800417b1  mov     rcx, [rax+98h]; this
0x1800417b8  test    rcx, rcx
0x1800417bb  jz      loc_180041C2F
0x1800417c1  call    ?EnsureWritable@Style@SVG@Mso@@AEAAAEAV123@XZ; Mso::SVG::Style::EnsureWritable(void)
0x1800417c6  lea     rdx, [rbp+47h+var_B0]
0x1800417ca  mov     rcx, rax
0x1800417cd  call    ??$Set@$09@Style@SVG@Mso@@QEAAX$$QEAVPaint@12@@Z; Mso::SVG::Style::Set<10>(Mso::SVG::Paint &&)
0x1800417d2  nop
0x1800417d3  mov     rax, qword ptr [rbp+47h+var_88+8]
0x1800417d7  cmp     rax, 7
0x1800417db  jbe     short loc_180041821
0x1800417dd  mov     rcx, [rbp+47h+Block]; Block
0x1800417e1  mov     rdx, rcx
0x1800417e4  lea     rax, ds:2[rax*2]
0x1800417ec  cmp     rax, 1000h
0x1800417f2  jb      short loc_18004181B
0x1800417f4  mov     rcx, [rcx-8]
0x1800417f8  sub     rdx, rcx
0x1800417fb  lea     rax, [rdx-8]
0x1800417ff  cmp     rax, 1Fh
0x180041803  jbe     short loc_18004181B
0x180041805  mov     [rsp+110h+Reserved], r12; Reserved
0x18004180a  xor     r9d, r9d; LineNo
0x18004180d  xor     r8d, r8d; FileName
0x180041810  xor     edx, edx; FunctionName
0x180041812  xor     ecx, ecx; Expression
0x180041814  call    cs:__imp__invoke_watson
0x18004181b  call    cs:__imp_free
0x180041821  movups  xmm0, [rsp+110h+var_C8]
0x180041826  movups  [rsp+110h+var_D8], xmm0
0x18004182b  mov     rax, [r14+18h]
0x18004182f  mov     rcx, [rax+40h]
0x180041833  mov     rsi, [rcx+210h]
0x18004183a  test    rsi, rsi
0x18004183d  jz      short loc_18004184F
0x18004183f  mov     rax, [rsi]
0x180041842  mov     rcx, rsi
0x180041845  mov     rax, [rax]
0x180041848  call    cs:__guard_dispatch_icall_fptr
0x18004184e  nop
0x18004184f  test    rsi, rsi
0x180041852  jz      loc_180041C3D
0x180041858  mov     byte ptr [rsi+218h], 1
0x18004185f  mov     rax, [rsi]
0x180041862  mov     rcx, rsi
0x180041865  mov     rax, [rax+8]
0x180041869  call    cs:__guard_dispatch_icall_fptr
0x18004186f  mov     rcx, [rdi+8]
0x180041873  mov     rax, [rcx+10h]
0x180041877  test    rax, rax
0x18004187a  jz      short loc_180041884
0x18004187c  add     rax, 3C8h
0x180041882  jmp     short loc_180041898
0x180041884  cmp     [rcx+8], r12
0x180041888  lea     rax, ?initial@?$StyleMetaData@$0M@@SVG@Mso@@2V?$optional@N@std@@B; std::optional<double> const Mso::SVG::StyleMetaData<12>::initial
0x18004188f  jz      short loc_180041898
0x180041891  lea     rax, ?inherit@?$StyleMetaData@$0M@@SVG@Mso@@2V?$optional@N@std@@B; std::optional<double> const Mso::SVG::StyleMetaData<12>::inherit
0x180041898  mov     edx, 8
0x18004189d  cmp     [rax+8], r12b
0x1800418a1  jnz     short loc_1800418BE
0x1800418a3  cmp     [rdi], r12
0x1800418a6  jz      short loc_1800418B2
0x1800418a8  mov     rcx, [rdi]
0x1800418ab  call    ??$Get@$0M@@StyleResolveChain@SVG@Mso@@QEBAAEBNXZ; Mso::SVG::StyleResolveChain::Get<12>(void)
0x1800418b0  jmp     short loc_1800418BE
0x1800418b2  mov     rdx, [rdx+rcx]
0x1800418b6  mov     rcx, rdi
0x1800418b9  call    ??$GetNormal@$0M@@StyleResolveChain@SVG@Mso@@AEBAAEBNAEBVStyle@12@@Z; Mso::SVG::StyleResolveChain::GetNormal<12>(Mso::SVG::Style const &)
0x1800418be  movsd   xmm0, qword ptr [rax]
0x1800418c2  cvtpd2ps xmm0, xmm0
0x1800418c6  movss   xmm1, dword ptr [rsp+110h+var_D8+0Ch]
0x1800418cc  mulss   xmm1, xmm0
0x1800418d0  movss   dword ptr [rsp+110h+var_D8+0Ch], xmm1
0x1800418d6  cmp     [rbp+47h+arg_20], r12b
0x1800418da  jz      short loc_180041944
0x1800418dc  mov     rdx, [rdi+8]
0x1800418e0  mov     rax, [rdx+10h]
0x1800418e4  test    rax, rax
0x1800418e7  jz      short loc_1800418F1
0x1800418e9  add     rax, 110h
0x1800418ef  jmp     short loc_18004190B
0x1800418f1  cmp     [rdx+18h], r12b
0x1800418f5  jz      short loc_180041904
0x1800418f7  cmp     [rdx+8], r12
0x1800418fb  lea     rax, ?inherit@?$StyleMetaData@$0CE@@SVG@Mso@@2V?$optional@N@std@@B; std::optional<double> const Mso::SVG::StyleMetaData<36>::inherit
0x180041902  jnz     short loc_18004190B
0x180041904  lea     rax, ?initial@?$StyleMetaData@$0CE@@SVG@Mso@@2V?$optional@N@std@@B; std::optional<double> const Mso::SVG::StyleMetaData<36>::initial
0x18004190b  cmp     [rax+8], r12b
0x18004190f  jnz     short loc_18004192C
0x180041911  mov     rcx, [rdi]
0x180041914  test    rcx, rcx
0x180041917  jz      short loc_180041920
0x180041919  call    ??$Get@$0CE@@StyleResolveChain@SVG@Mso@@QEBAAEBNXZ; Mso::SVG::StyleResolveChain::Get<36>(void)
0x18004191e  jmp     short loc_18004192C
0x180041920  mov     rdx, [rdx+8]
0x180041924  mov     rcx, rdi
0x180041927  call    ??$GetNormal@$0CE@@StyleResolveChain@SVG@Mso@@AEBAAEBNAEBVStyle@12@@Z; Mso::SVG::StyleResolveChain::GetNormal<36>(Mso::SVG::Style const &)
0x18004192c  movsd   xmm0, qword ptr [rax]
0x180041930  cvtpd2ps xmm0, xmm0
0x180041934  movss   xmm1, dword ptr [rsp+110h+var_D8+0Ch]
0x18004193a  mulss   xmm1, xmm0
0x18004193e  movss   dword ptr [rsp+110h+var_D8+0Ch], xmm1
0x180041944  xorps   xmm0, xmm0
0x180041947  comiss  xmm0, dword ptr [rsp+110h+var_D8+0Ch]
0x18004194c  jnb     loc_180041BCE
0x180041952  xor     r8d, r8d
0x180041955  lea     rdx, [rsp+110h+var_D8]
0x18004195a  lea     rcx, [rsp+110h+var_E0]
0x18004195f  call    cs:__imp_?Create@IBrushSolid@GEL@@SA?AV?$TCntPtr@UIBrushSolid@GEL@@@Ofc@@AEBUColor@2@PEBUCropInfo@2@@Z; GEL::IBrushSolid::Create(GEL::Color const &,GEL::CropInfo const *)
0x180041965  mov     rcx, [rax]
0x180041968  mov     [rbx], rcx
0x18004196b  test    rcx, rcx
0x18004196e  jz      short loc_18004197C
0x180041970  mov     rax, [rcx]
0x180041973  mov     rax, [rax]
0x180041976  call    cs:__guard_dispatch_icall_fptr
0x18004197c  mov     rcx, [rsp+110h+var_E0]
0x180041981  test    rcx, rcx
0x180041984  jz      loc_180041BD1
0x18004198a  mov     rax, [rcx]
0x18004198d  mov     rax, [rax+8]
0x180041991  jmp     loc_180041686
0x180041996  cmp     [rbp+47h+var_50], r12
0x18004199a  jz      loc_180041A4D
0x1800419a0  mov     rax, [r14+18h]
0x1800419a4  lea     rdx, [rbp+47h+var_60]
0x1800419a8  mov     rcx, [rax+40h]
0x1800419ac  call    ?QueryPaintServer@Environment@SVG@Mso@@QEAAPEAVPaintServerContext@23@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Mso::SVG::Environment::QueryPaintServer(std::wstring const &)
0x1800419b1  test    rax, rax
0x1800419b4  jz      loc_180041A4D
0x1800419ba  mov     r8, [r14+18h]
0x1800419be  mov     rdx, rax
0x1800419c1  lea     rcx, [rsp+110h+var_D8]
0x1800419c6  call    ?Create@PaintServerRenderer@SVG@Mso@@SA?AV?$TCntPtr@VPaintServerRenderer@SVG@Mso@@@3@AEAVPaintServerContext@23@AEAVEnvironmentRenderer@23@@Z; Mso::SVG::PaintServerRenderer::Create(Mso::SVG::PaintServerContext &,Mso::SVG::EnvironmentRenderer &)
0x1800419cb  nop
0x1800419cc  mov     rcx, [r14+18h]; this
0x1800419d0  call    ?BeginRecursion@EnvironmentRenderer@SVG@Mso@@QEAAXXZ; Mso::SVG::EnvironmentRenderer::BeginRecursion(void)
0x1800419d5  nop
0x1800419d6  mov     rcx, qword ptr [rsp+110h+var_D8]
0x1800419db  test    rcx, rcx
0x1800419de  jz      loc_180041BFB
0x1800419e4  mov     rax, [rcx]
0x1800419e7  mov     byte ptr [rsp+110h+Reserved], r12b
0x1800419ec  mov     r9, r15
0x1800419ef  mov     r8, rdi
0x1800419f2  lea     rdx, [rsp+110h+var_E0]
0x1800419f7  mov     rax, [rax+20h]
0x1800419fb  call    cs:__guard_dispatch_icall_fptr
0x180041a01  mov     rax, [r14+18h]
0x180041a05  dec     dword ptr [rax]
0x180041a07  mov     rax, [rsp+110h+var_E0]
0x180041a0c  test    rax, rax
0x180041a0f  jz      short loc_180041A31
0x180041a11  mov     [rsp+110h+var_E0], r12
0x180041a16  mov     [rbx], rax
0x180041a19  mov     rcx, qword ptr [rsp+110h+var_D8]
0x180041a1e  test    rcx, rcx
0x180041a21  jz      loc_180041BD1
0x180041a27  mov     qword ptr [rsp+110h+var_D8], r12
0x180041a2c  jmp     loc_18004198A
0x180041a31  mov     rcx, qword ptr [rsp+110h+var_D8]
0x180041a36  test    rcx, rcx
0x180041a39  jz      short loc_180041A4D
0x180041a3b  mov     qword ptr [rsp+110h+var_D8], r12
0x180041a40  mov     rax, [rcx]
0x180041a43  mov     rax, [rax+8]
0x180041a47  call    cs:__guard_dispatch_icall_fptr
0x180041a4d  cmp     [rbp+47h+var_78], 1
0x180041a51  jnz     loc_180041BCE
0x180041a57  mov     eax, [rbp+47h+var_74]
0x180041a5a  mov     [rbp+47h+var_B0], eax
0x180041a5d  mov     [rbp+47h+var_AC], 2
0x180041a64  movups  xmm2, [rbp+47h+var_70]
0x180041a68  movups  [rbp+47h+var_A8], xmm2
0x180041a6c  xorps   xmm0, xmm0
0x180041a6f  movups  xmmword ptr [rbp+47h+Block], xmm0
0x180041a73  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180041a7b  movdqu  [rbp+47h+var_88], xmm1
0x180041a80  mov     word ptr [rbp+47h+Block], r12w
0x180041a85  cmp     eax, 2
0x180041a88  jnz     short loc_180041AA7
  ... truncated ...
```
