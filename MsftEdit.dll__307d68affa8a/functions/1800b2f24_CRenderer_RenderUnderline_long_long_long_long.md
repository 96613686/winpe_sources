# CRenderer::RenderUnderline(long,long,long,long)

- ea: `0x1800b2f24`
- end: `0x1800b33f1`
- name: `?RenderUnderline@CRenderer@@QEAAXJJJJ@Z`
- size: `1229`
- prototype: `void __fastcall(CRenderer *__hidden this, int, int, int, int)`
- caller_count: `2`
- callee_count: `12`
- tags: `loader_planting`

## callers

- `0x1800b401c`
- `0x18014cb7c`

## callees

- `0x180028b98`
- `0x18005aec0`
- `0x18006e4d4`
- `0x18006e7e0`
- `0x1800b2f24`
- `0x1800e4124`
- `0x1800ee848`
- `0x1801093cc`
- `0x18010c90c`
- `0x18013bad0`
- `0x18014ce68`
- `0x18027a010`

## import_xrefs

- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x1800b3202`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x1800b3350`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x1800b3202`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x1800b3350`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x1800b3359`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x1800b3359`

## pseudocode

```c
void __fastcall CRenderer::RenderUnderline(CRenderer *this, int a2, int a3, int a4, int a5)
{
  __int64 v5; // rax
  int v6; // ebx
  int v10; // ecx
  int *v11; // rdi
  int v12; // r15d
  int v13; // eax
  int v14; // ebx
  int v15; // edi
  COLORREF v16; // r13d
  int v17; // edi
  CDisplay *v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // rax
  int v21; // r12d
  int v22; // eax
  char v23; // al
  __int64 v24; // rax
  __int64 v25; // rax
  int v26; // edi
  void *v27; // r15
  unsigned int v28; // ebx
  __int64 v29; // rcx
  HDC v30; // rax
  int v31; // eax
  char v32; // al
  int v33; // eax
  int v34; // r12d
  int v35; // ebx
  int v36; // eax
  int v37; // eax
  HGDIOBJ v38; // rbx
  HDC v39; // rax
  __int16 *v40; // rcx
  int v41; // edi
  int v42; // ebx
  int Ascent; // eax
  CDisplay *v44; // rcx
  int v45; // [rsp+30h] [rbp-51h] BYREF
  int v46[2]; // [rsp+38h] [rbp-49h] BYREF
  HGDIOBJ h; // [rsp+40h] [rbp-41h] BYREF
  int v48; // [rsp+48h] [rbp-39h]
  int v49; // [rsp+4Ch] [rbp-35h]
  unsigned __int64 v50; // [rsp+50h] [rbp-31h] BYREF
  int v51; // [rsp+58h] [rbp-29h]
  int v52; // [rsp+5Ch] [rbp-25h]
  void *v53; // [rsp+60h] [rbp-21h]
  unsigned int v54; // [rsp+68h] [rbp-19h]
  struct tagRECT v55; // [rsp+70h] [rbp-11h] BYREF

  v5 = *((_QWORD *)this + 2);
  v6 = a4;
  v52 = a2;
  if ( v5 )
    v5 = *(_QWORD *)(v5 + 40);
  LOBYTE(v45) = *(_BYTE *)(v5 + 358) & 1;
  if ( (_BYTE)v45 )
    v6 = a4 - CMeasurerNoFC::GetAlignSpacing(this, *((_DWORD *)this + 8) + *((_DWORD *)this + 24), 1);
  v10 = *((unsigned __int8 *)this + 524);
  v54 = a2 + v6;
  if ( (unsigned int)(v10 - 4) <= 4
    || (unsigned int)(v10 - 19) <= 3
    || (LODWORD(v53) = 0, (unsigned int)(v10 - 11) <= 7) )
  {
    LODWORD(v53) = 1;
  }
  v11 = (int *)((char *)this + 376);
  v49 = a3 + a5;
  h = (HGDIOBJ)__PAIR64__(a3, a2);
  v48 = a2 + v6;
  if ( this != (CRenderer *)-376LL )
  {
    v12 = a2;
    v13 = *((_DWORD *)this + 96);
    if ( *v11 > a2 )
      v12 = *v11;
    if ( v13 >= a2 + v6 )
      v13 = a2 + v6;
    LODWORD(v50) = v13;
    if ( v12 < v13 )
    {
      v14 = a3;
      if ( *((_DWORD *)this + 95) > a3 )
        v14 = *((_DWORD *)this + 95);
      v15 = *((_DWORD *)this + 97);
      if ( v15 >= a3 + a5 )
        v15 = a3 + a5;
      if ( v14 < v15 )
      {
        v16 = *((_DWORD *)this + 130);
        v17 = v15 - v14;
        v51 = v13 - v12;
        v46[0] = v13 - v12;
        a5 = v17;
        if ( v16 == -9999997 || v16 == -9999999 )
          v16 = *((_DWORD *)this + 113);
        v18 = (CDisplay *)*((_QWORD *)this + 19);
        v55 = 0;
        CDisplay::RectFromRectuv(v18, &v55, (const struct RECTUV *)&h, 1, 0);
        LOBYTE(v19) = *((_BYTE *)this + 524);
        if ( !(*(unsigned __int8 (__fastcall **)(_QWORD, __int64, _QWORD, struct tagRECT *))(**((_QWORD **)this + 42)
                                                                                           + 432LL))(
                *((_QWORD *)this + 42),
                v19,
                v16,
                &v55) )
        {
          v20 = *((unsigned __int8 *)this + 524);
          if ( (_BYTE)v20 == 0xFE )
          {
            v40 = (__int16 *)*((_QWORD *)this + 41);
            HIDWORD(h) = *((_DWORD *)this + 129);
            v41 = HIDWORD(h);
            LODWORD(h) = v12;
            v42 = CCcs::ScaleMetric((CCcs *)v40, v40[10]);
            Ascent = CLine::GetAscent((CRenderer *)((char *)this + 96), 0, 0);
            v44 = (CDisplay *)*((_QWORD *)this + 19);
            v49 = v42 + v41 + Ascent;
            v48 = v50;
            CDisplay::RectFromRectuv(v44, &v55, (const struct RECTUV *)&h, 1, 0);
            (*(void (__fastcall **)(_QWORD, struct tagRECT *))(**((_QWORD **)this + 42) + 280LL))(
              *((_QWORD *)this + 42),
              &v55);
            return;
          }
          if ( !(_DWORD)v53 )
          {
            HIDWORD(h) = v14;
            if ( (_BYTE)v20 == 9 && v14 > v17 + *((_DWORD *)this + 95) )
            {
              v14 -= v17;
              HIDWORD(h) = v14;
              a5 = 2 * v17;
            }
            CRenderer::CorrectLineWidth(this, v46, &a5);
            v21 = a5;
            if ( (_BYTE)v45 )
              goto LABEL_41;
            if ( (*((_BYTE *)this + 109) & 0x10) != 0 )
              goto LABEL_31;
            v23 = *((_BYTE *)this + 111) & 3;
            if ( v23 == 1 )
            {
              v25 = *((_QWORD *)this + 15);
              if ( !v25 )
                goto LABEL_31;
              SafeCastHelper<long,__int64,4>::CastThrow<SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>(
                *(int *)(v25 + 8),
                &v45);
              v22 = v45;
            }
            else
            {
              if ( v23 == 2 )
              {
                v24 = *((_QWORD *)this + 15);
                if ( v24 )
                {
                  v22 = *(_DWORD *)(v24 + 16);
                  goto LABEL_39;
                }
LABEL_31:
                v22 = 0;
                goto LABEL_39;
              }
              v22 = *((_DWORD *)this + 31);
            }
LABEL_39:
            v26 = *((_DWORD *)this + 129);
            if ( v14 >= v26 + v22 )
            {
              v14 = v26 - v21 + CLine::GetHeight((CRenderer *)((char *)this + 96), 0, 0);
              HIDWORD(h) = v14;
            }
LABEL_41:
            v49 = v14 + v21;
            v48 = v12 + v46[0];
            LODWORD(h) = v12;
            CRenderer::FillRectWithColor(this, (const struct RECTUV *)&h, v16);
            return;
          }
          v27 = 0;
          v28 = *((char *)qword_1802AAE68 + v20 - 4);
          v29 = *((_QWORD *)this + 42);
          v45 = v28;
          v53 = 0;
          if ( (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v29 + 48LL))(v29) )
          {
            v27 = (void *)((__int64 (__fastcall *)(_QWORD, bool, _QWORD))pfnCreatePen)(v28, v28 == 0, v16);
            v53 = v27;
          }
          if ( !(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 42) + 48LL))(*((_QWORD *)this + 42)) || v27 )
          {
            if ( v27 )
            {
              v30 = (HDC)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 42) + 48LL))(*((_QWORD *)this + 42));
              h = SelectObject(v30, v27);
            }
            else
            {
              h = 0;
            }
            v31 = 1;
            v46[0] = a2;
            if ( v51 < v17 )
              v17 = v51;
            v46[1] = a3;
            if ( v17 > 1 )
              v31 = v17;
            v51 = v31;
            v32 = *((_BYTE *)this + 524);
            if ( v32 != 8 && (unsigned __int8)(v32 - 11) > 1u )
              goto LABEL_57;
            if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(**((_QWORD **)this + 42) + 80LL))(*((_QWORD *)this + 42)) )
            {
              v28 = 7;
LABEL_57:
              v50 = __PAIR64__(a3, v54);
              CRenderer::DrawLine(
                this,
                (const struct Ptls6::tagLSPOINTUV *)v46,
                (const struct Ptls6::tagLSPOINTUV *)&v50,
                v51,
                v28,
                v16);
LABEL_70:
              if ( v27 )
              {
                v38 = h;
                if ( h )
                {
                  v39 = (HDC)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 42) + 48LL))(*((_QWORD *)this + 42));
                  SelectObject(v39, v38);
                }
                DeleteObject(v27);
              }
              return;
            }
            v33 = v52;
            v34 = 2;
            v52 = v54 + 1;
            v35 = v33 + 1;
            switch ( v33 % 4 )
            {
              case 1:
                v36 = a3 + 2;
                v34 = -1;
                ++v35;
                break;
              case 2:
                v34 = -1;
                goto LABEL_65;
              case 3:
                v36 = a3 - 1;
                ++v35;
                break;
              default:
                goto LABEL_65;
            }
            v46[1] = v36;
LABEL_65:
            if ( v35 < (int)(v54 + 1) )
            {
              do
              {
                HIDWORD(v50) = v34 + a3;
                LODWORD(v50) = v35;
                CRenderer::DrawLine(
                  this,
                  (const struct Ptls6::tagLSPOINTUV *)v46,
                  (const struct Ptls6::tagLSPOINTUV *)&v50,
                  1,
                  v45,
                  v16);
                v35 += 2;
                *(_QWORD *)v46 = v50;
                v37 = -1;
                if ( v34 != 2 )
                  v37 = 2;
                v34 = v37;
              }
              while ( v35 < v52 );
              v27 = v53;
            }
            goto LABEL_70;
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x1800b2f24  push    rbp
0x1800b2f26  push    rbx
0x1800b2f27  push    rsi
0x1800b2f28  push    rdi
0x1800b2f29  push    r12
0x1800b2f2b  push    r13
0x1800b2f2d  push    r14
0x1800b2f2f  push    r15
0x1800b2f31  lea     rbp, [rsp-17h]
0x1800b2f36  sub     rsp, 98h
0x1800b2f3d  mov     rax, cs:__security_cookie
0x1800b2f44  xor     rax, rsp
0x1800b2f47  mov     [rbp+4Fh+var_50], rax
0x1800b2f4b  mov     rax, [rcx+10h]
0x1800b2f4f  mov     ebx, r9d
0x1800b2f52  mov     [rbp+4Fh+var_74], edx
0x1800b2f55  mov     r14d, r8d
0x1800b2f58  mov     r12d, edx
0x1800b2f5b  mov     rsi, rcx
0x1800b2f5e  test    rax, rax
0x1800b2f61  jz      short loc_1800B2F67
0x1800b2f63  mov     rax, [rax+28h]
0x1800b2f67  mov     al, [rax+166h]
0x1800b2f6d  and     al, 1
0x1800b2f6f  mov     byte ptr [rbp+4Fh+var_A0], al
0x1800b2f72  jz      short loc_1800B2F84
0x1800b2f74  mov     edx, [rcx+60h]
0x1800b2f77  mov     r8b, 1; bool
0x1800b2f7a  add     edx, [rcx+20h]; int
0x1800b2f7d  call    ?GetAlignSpacing@CMeasurerNoFC@@QEAAJJ_N@Z; CMeasurerNoFC::GetAlignSpacing(long,bool)
0x1800b2f82  sub     ebx, eax
0x1800b2f84  movzx   ecx, byte ptr [rsi+20Ch]
0x1800b2f8b  lea     edx, [r12+rbx]
0x1800b2f8f  mov     [rbp+4Fh+var_68], edx
0x1800b2f92  lea     eax, [rcx-4]
0x1800b2f95  cmp     eax, 4
0x1800b2f98  jbe     short loc_1800B2FB1
0x1800b2f9a  lea     eax, [rcx-13h]
0x1800b2f9d  cmp     eax, 3
0x1800b2fa0  jbe     short loc_1800B2FB1
0x1800b2fa2  lea     eax, [rcx-0Bh]
0x1800b2fa5  mov     dword ptr [rbp+4Fh+var_70], 0
0x1800b2fac  cmp     eax, 7
0x1800b2faf  ja      short loc_1800B2FB8
0x1800b2fb1  mov     dword ptr [rbp+4Fh+var_70], 1
0x1800b2fb8  mov     ecx, [rbp+4Fh+arg_20]
0x1800b2fbb  lea     rdi, [rsi+178h]
0x1800b2fc2  add     ecx, r14d
0x1800b2fc5  mov     dword ptr [rbp+4Fh+h+4], r14d
0x1800b2fc9  mov     [rbp+4Fh+var_84], ecx
0x1800b2fcc  mov     dword ptr [rbp+4Fh+h], r12d
0x1800b2fd0  mov     [rbp+4Fh+var_88], edx
0x1800b2fd3  test    rdi, rdi
0x1800b2fd6  jz      loc_1800B33D1
0x1800b2fdc  cmp     [rdi], r12d
0x1800b2fdf  mov     r15d, r12d
0x1800b2fe2  mov     eax, [rdi+8]
0x1800b2fe5  cmovg   r15d, [rdi]
0x1800b2fe9  cmp     eax, edx
0x1800b2feb  cmovge  eax, edx
0x1800b2fee  mov     dword ptr [rbp+4Fh+var_80], eax
0x1800b2ff1  cmp     r15d, eax
0x1800b2ff4  jge     loc_1800B33D1
0x1800b2ffa  cmp     [rdi+4], r14d
0x1800b2ffe  mov     ebx, r14d
0x1800b3001  cmovg   ebx, [rdi+4]
0x1800b3005  mov     edi, [rdi+0Ch]
0x1800b3008  cmp     edi, ecx
0x1800b300a  cmovge  edi, ecx
0x1800b300d  cmp     ebx, edi
0x1800b300f  jge     loc_1800B33D1
0x1800b3015  mov     r13d, [rsi+208h]
0x1800b301c  sub     eax, r15d
0x1800b301f  sub     edi, ebx
0x1800b3021  mov     [rbp+4Fh+var_78], eax
0x1800b3024  mov     [rbp+4Fh+var_98], eax
0x1800b3027  mov     [rbp+4Fh+arg_20], edi
0x1800b302a  cmp     r13d, 0FF676983h
0x1800b3031  jz      short loc_1800B303C
0x1800b3033  cmp     r13d, 0FF676981h
0x1800b303a  jnz     short loc_1800B3043
0x1800b303c  mov     r13d, [rsi+1C4h]
0x1800b3043  mov     rcx, [rsi+98h]; this
0x1800b304a  lea     r8, [rbp+4Fh+h]; struct RECTUV *
0x1800b304e  xorps   xmm0, xmm0
0x1800b3051  mov     [rsp+0D0h+var_B0], 0; bool
0x1800b3056  mov     r9b, 1; bool
0x1800b3059  lea     rdx, [rbp+4Fh+var_60]; struct tagRECT *
0x1800b305d  movups  xmmword ptr [rbp+4Fh+var_60.left], xmm0
0x1800b3061  call    ?RectFromRectuv@CDisplay@@QEBAXAEAUtagRECT@@AEBURECTUV@@_N2@Z; CDisplay::RectFromRectuv(tagRECT &,RECTUV const &,bool,bool)
0x1800b3066  mov     rcx, [rsi+150h]
0x1800b306d  lea     r9, [rbp+4Fh+var_60]
0x1800b3071  mov     dl, [rsi+20Ch]
0x1800b3077  mov     r8d, r13d
0x1800b307a  mov     rax, [rcx]
0x1800b307d  mov     rax, [rax+1B0h]
0x1800b3084  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3089  test    al, al
0x1800b308b  jnz     loc_1800B33D1
0x1800b3091  movzx   eax, byte ptr [rsi+20Ch]
0x1800b3098  cmp     al, 0FEh
0x1800b309a  jz      loc_1800B3361
0x1800b30a0  cmp     dword ptr [rbp+4Fh+var_70], 0
0x1800b30a4  jnz     loc_1800B3176
0x1800b30aa  mov     dword ptr [rbp+4Fh+h+4], ebx
0x1800b30ad  cmp     al, 9
0x1800b30af  jnz     short loc_1800B30C8
0x1800b30b1  mov     ecx, [rsi+17Ch]
0x1800b30b7  add     ecx, edi
0x1800b30b9  cmp     ebx, ecx
0x1800b30bb  jle     short loc_1800B30C8
0x1800b30bd  sub     ebx, edi
0x1800b30bf  lea     eax, [rdi+rdi]
0x1800b30c2  mov     dword ptr [rbp+4Fh+h+4], ebx
0x1800b30c5  mov     [rbp+4Fh+arg_20], eax
0x1800b30c8  lea     r8, [rbp+4Fh+arg_20]; int *
0x1800b30cc  mov     rcx, rsi; this
0x1800b30cf  lea     rdx, [rbp+4Fh+var_98]; int *
0x1800b30d3  call    ?CorrectLineWidth@CRenderer@@QEBAXAEAJ0@Z; CRenderer::CorrectLineWidth(long &,long &)
0x1800b30d8  cmp     byte ptr [rbp+4Fh+var_A0], 0
0x1800b30dc  mov     r12d, [rbp+4Fh+arg_20]
0x1800b30e0  jnz     short loc_1800B314E
0x1800b30e2  test    byte ptr [rsi+6Dh], 10h
0x1800b30e6  jz      short loc_1800B30EC
0x1800b30e8  xor     eax, eax
0x1800b30ea  jmp     short loc_1800B312B
0x1800b30ec  mov     al, [rsi+6Fh]
0x1800b30ef  and     al, 3
0x1800b30f1  cmp     al, 1
0x1800b30f3  jz      short loc_1800B3112
0x1800b30f5  mov     edi, 2
0x1800b30fa  cmp     al, dil
0x1800b30fd  jnz     short loc_1800B310D
0x1800b30ff  mov     rax, [rsi+78h]
0x1800b3103  test    rax, rax
0x1800b3106  jz      short loc_1800B30E8
0x1800b3108  mov     eax, [rax+10h]
0x1800b310b  jmp     short loc_1800B312B
0x1800b310d  mov     eax, [rsi+7Ch]
0x1800b3110  jmp     short loc_1800B312B
0x1800b3112  mov     rax, [rsi+78h]
0x1800b3116  test    rax, rax
0x1800b3119  jz      short loc_1800B30E8
0x1800b311b  movsxd  rcx, dword ptr [rax+8]
0x1800b311f  lea     rdx, [rbp+4Fh+var_A0]
0x1800b3123  call    ??$CastThrow@V?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@@?$SafeCastHelper@J_J$03@@SAX_JAEAJ@Z; SafeCastHelper<long,__int64,4>::CastThrow<SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>(__int64,long &)
0x1800b3128  mov     eax, [rbp+4Fh+var_A0]
0x1800b312b  mov     edi, [rsi+204h]
0x1800b3131  add     eax, edi
0x1800b3133  cmp     ebx, eax
0x1800b3135  jl      short loc_1800B314E
0x1800b3137  xor     r8d, r8d; struct CDisplay *
0x1800b313a  lea     rcx, [rsi+60h]; this
0x1800b313e  xor     edx, edx; bool
0x1800b3140  call    ?GetHeight@CLine@@QEBAJ_NPEBVCDisplay@@@Z; CLine::GetHeight(bool,CDisplay const *)
0x1800b3145  sub     edi, r12d
0x1800b3148  lea     ebx, [rdi+rax]
0x1800b314b  mov     dword ptr [rbp+4Fh+h+4], ebx
0x1800b314e  mov     edx, [rbp+4Fh+var_98]
0x1800b3151  lea     eax, [rbx+r12]
0x1800b3155  add     edx, r15d
0x1800b3158  mov     [rbp+4Fh+var_84], eax
0x1800b315b  mov     [rbp+4Fh+var_88], edx
0x1800b315e  mov     r8d, r13d; unsigned int
0x1800b3161  lea     rdx, [rbp+4Fh+h]; struct RECTUV *
0x1800b3165  mov     dword ptr [rbp+4Fh+h], r15d
0x1800b3169  mov     rcx, rsi; this
0x1800b316c  call    ?FillRectWithColor@CRenderer@@QEAAXPEBURECTUV@@K@Z; CRenderer::FillRectWithColor(RECTUV const *,ulong)
0x1800b3171  jmp     loc_1800B33D1
0x1800b3176  lea     rcx, qword_1802AAE68
0x1800b317d  xor     r15d, r15d
0x1800b3180  movsx   ebx, byte ptr [rax+rcx-4]
0x1800b3185  mov     rcx, [rsi+150h]
0x1800b318c  mov     [rbp+4Fh+var_A0], ebx
0x1800b318f  mov     [rbp+4Fh+var_70], r15
0x1800b3193  mov     rax, [rcx]
0x1800b3196  mov     rax, [rax+30h]
0x1800b319a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b319f  test    rax, rax
0x1800b31a2  jz      short loc_1800B31C3
0x1800b31a4  mov     rax, cs:?pfnCreatePen@@3P6A_JXZEA; __int64 (*pfnCreatePen)(void)
0x1800b31ab  xor     edx, edx
0x1800b31ad  test    ebx, ebx
0x1800b31af  mov     r8d, r13d
0x1800b31b2  mov     ecx, ebx
0x1800b31b4  setz    dl
0x1800b31b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b31bc  mov     r15, rax
0x1800b31bf  mov     [rbp+4Fh+var_70], rax
0x1800b31c3  mov     rcx, [rsi+150h]
0x1800b31ca  mov     rax, [rcx]
0x1800b31cd  mov     rax, [rax+30h]
0x1800b31d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b31d6  test    rax, rax
0x1800b31d9  jz      short loc_1800B31E4
0x1800b31db  test    r15, r15
0x1800b31de  jz      loc_1800B33D1
0x1800b31e4  test    r15, r15
0x1800b31e7  jz      short loc_1800B320E
0x1800b31e9  mov     rcx, [rsi+150h]
0x1800b31f0  mov     rax, [rcx]
0x1800b31f3  mov     rax, [rax+30h]
0x1800b31f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b31fc  mov     rdx, r15; h
0x1800b31ff  mov     rcx, rax; hdc
0x1800b3202  call    cs:__imp_SelectObject
0x1800b3208  mov     [rbp+4Fh+h], rax
0x1800b320c  jmp     short loc_1800B3216
0x1800b320e  mov     [rbp+4Fh+h], 0
0x1800b3216  cmp     [rbp+4Fh+var_78], edi
0x1800b3219  mov     eax, 1
0x1800b321e  mov     [rbp+4Fh+var_98], r12d
0x1800b3222  cmovl   edi, [rbp+4Fh+var_78]
0x1800b3226  cmp     edi, eax
0x1800b3228  mov     [rbp+4Fh+var_98+4], r14d
0x1800b322c  cmovg   eax, edi
0x1800b322f  mov     [rbp+4Fh+var_78], eax
0x1800b3232  mov     al, [rsi+20Ch]
0x1800b3238  cmp     al, 8
0x1800b323a  jz      short loc_1800B3242
0x1800b323c  sub     al, 0Bh
0x1800b323e  cmp     al, 1
0x1800b3240  ja      short loc_1800B325E
0x1800b3242  mov     rcx, [rsi+150h]
0x1800b3249  mov     rax, [rcx]
0x1800b324c  mov     rax, [rax+50h]
0x1800b3250  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3255  test    al, al
0x1800b3257  jz      short loc_1800B328A
0x1800b3259  mov     ebx, 7
0x1800b325e  mov     ecx, [rbp+4Fh+var_68]
0x1800b3261  lea     r8, [rbp+4Fh+var_80]; struct Ptls6::tagLSPOINTUV *
0x1800b3265  mov     r9d, [rbp+4Fh+var_78]; int
0x1800b3269  lea     rdx, [rbp+4Fh+var_98]; struct Ptls6::tagLSPOINTUV *
0x1800b326d  mov     dword ptr [rbp+4Fh+var_80], ecx
0x1800b3270  mov     rcx, rsi; this
0x1800b3273  mov     [rsp+0D0h+var_A8], r13d; unsigned int
0x1800b3278  mov     dword ptr [rbp+4Fh+var_80+4], r14d
0x1800b327c  mov     dword ptr [rsp+0D0h+var_B0], ebx; int
0x1800b3280  call    ?DrawLine@CRenderer@@QEAAXAEBUtagLSPOINTUV@Ptls6@@0JHK@Z; CRenderer::DrawLine(Ptls6::tagLSPOINTUV const &,Ptls6::tagLSPOINTUV const &,long,int,ulong)
0x1800b3285  jmp     loc_1800B3325
0x1800b328a  mov     eax, [rbp+4Fh+var_74]
0x1800b328d  mov     edi, 2
0x1800b3292  mov     ecx, [rbp+4Fh+var_68]
0x1800b3295  mov     r12d, edi
0x1800b3298  inc     ecx
0x1800b329a  mov     [rbp+4Fh+var_74], ecx
0x1800b329d  lea     ebx, [rax+1]
0x1800b32a0  cdq
0x1800b32a1  lea     r8d, [rdi+2]
0x1800b32a5  idiv    r8d
0x1800b32a8  or      r8d, 0FFFFFFFFh
0x1800b32ac  sub     edx, 1
0x1800b32af  jz      short loc_1800B32C8
0x1800b32b1  sub     edx, 1
0x1800b32b4  jz      short loc_1800B32C3
0x1800b32b6  cmp     edx, 1
0x1800b32b9  jnz     short loc_1800B32D4
0x1800b32bb  lea     eax, [r14-1]
0x1800b32bf  inc     ebx
0x1800b32c1  jmp     short loc_1800B32D1
0x1800b32c3  mov     r12d, r8d
0x1800b32c6  jmp     short loc_1800B32D4
0x1800b32c8  lea     eax, [r14+2]
0x1800b32cc  mov     r12d, r8d
0x1800b32cf  inc     ebx
0x1800b32d1  mov     [rbp+4Fh+var_98+4], eax
0x1800b32d4  cmp     ebx, ecx
0x1800b32d6  jge     short loc_1800B3325
0x1800b32d8  mov     r15d, [rbp+4Fh+var_A0]
0x1800b32dc  lea     eax, [r12+r14]
0x1800b32e0  mov     [rsp+0D0h+var_A8], r13d; unsigned int
0x1800b32e5  mov     r9d, 1; int
0x1800b32eb  mov     dword ptr [rbp+4Fh+var_80+4], eax
0x1800b32ee  lea     r8, [rbp+4Fh+var_80]; struct Ptls6::tagLSPOINTUV *
0x1800b32f2  mov     dword ptr [rbp+4Fh+var_80], ebx
0x1800b32f5  lea     rdx, [rbp+4Fh+var_98]; struct Ptls6::tagLSPOINTUV *
0x1800b32f9  mov     dword ptr [rsp+0D0h+var_B0], r15d; int
0x1800b32fe  mov     rcx, rsi; this
0x1800b3301  call    ?DrawLine@CRenderer@@QEAAXAEBUtagLSPOINTUV@Ptls6@@0JHK@Z; CRenderer::DrawLine(Ptls6::tagLSPOINTUV const &,Ptls6::tagLSPOINTUV const &,long,int,ulong)
0x1800b3306  mov     rax, [rbp+4Fh+var_80]
0x1800b330a  add     ebx, edi
0x1800b330c  mov     qword ptr [rbp+4Fh+var_98], rax
0x1800b3310  or      eax, 0FFFFFFFFh
0x1800b3313  cmp     r12d, edi
0x1800b3316  cmovnz  eax, edi
0x1800b3319  mov     r12d, eax
0x1800b331c  cmp     ebx, [rbp+4Fh+var_74]
0x1800b331f  jl      short loc_1800B32DC
0x1800b3321  mov     r15, [rbp+4Fh+var_70]
0x1800b3325  test    r15, r15
0x1800b3328  jz      loc_1800B33D1
0x1800b332e  mov     rbx, [rbp+4Fh+h]
0x1800b3332  test    rbx, rbx
0x1800b3335  jz      short loc_1800B3356
0x1800b3337  mov     rcx, [rsi+150h]
0x1800b333e  mov     rax, [rcx]
0x1800b3341  mov     rax, [rax+30h]
0x1800b3345  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b334a  mov     rdx, rbx; h
  ... truncated ...
```
