# CTouchHandleAnimationController::_GetPVLTransformInfo(int,int,int *,CTouchHandleAnimationController::OPACITY_TRANSFORM_INFO * *)

- ea: `0x1802005ac`
- end: `0x1802007e2`
- name: `?_GetPVLTransformInfo@CTouchHandleAnimationController@@AEAAJHHPEAHPEAPEAUOPACITY_TRANSFORM_INFO@1@@Z`
- size: `566`
- prototype: `int(CTouchHandleAnimationController *__hidden this, int, int, int *, struct CTouchHandleAnimationController::OPACITY_TRANSFORM_INFO **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1802009dc`

## callees

- `0x18013bea0`
- `0x18013c21c`
- `0x1802005ac`
- `0x1802007e8`
- `0x180200908`

## import_xrefs

- `ext-ms-win-uxtheme-themes-l1-1-0!GetThemeAnimationProperty` at `0x18020064d`
- `ext-ms-win-uxtheme-themes-l1-1-0!GetThemeAnimationProperty` at `0x18020064d`
- `ext-ms-win-uxtheme-themes-l1-1-0!OpenThemeData` at `0x1802005ef`
- `ext-ms-win-uxtheme-themes-l1-1-0!OpenThemeData` at `0x18020060c`
- `ext-ms-win-uxtheme-themes-l1-1-0!OpenThemeData` at `0x1802005ef`
- `ext-ms-win-uxtheme-themes-l1-1-0!OpenThemeData` at `0x18020060c`
- `ext-ms-win-uxtheme-themes-l1-1-0!CloseThemeData` at `0x180200795`
- `ext-ms-win-uxtheme-themes-l1-1-0!CloseThemeData` at `0x1802007ac`
- `ext-ms-win-uxtheme-themes-l1-1-0!CloseThemeData` at `0x180200795`
- `ext-ms-win-uxtheme-themes-l1-1-0!CloseThemeData` at `0x1802007ac`

## pseudocode

```c
__int64 __fastcall CTouchHandleAnimationController::_GetPVLTransformInfo(
        CTouchHandleAnimationController *this,
        unsigned int a2,
        int a3,
        int *a4,
        struct CTouchHandleAnimationController::OPACITY_TRANSFORM_INFO **a5)
{
  struct CTouchHandleAnimationController::OPACITY_TRANSFORM_INFO **v5; // rsi
  unsigned int v6; // r14d
  HTHEME v7; // r12
  char *v8; // rdi
  HTHEME v9; // r13
  int ThemeAnimationProperty; // ebx
  unsigned __int64 v11; // rax
  CTouchHandleAnimationController *v12; // rcx
  int v13; // r9d
  int v14; // r15d
  struct TA_TRANSFORM *v15; // rsi
  struct CTouchHandleAnimationController::OPACITY_TRANSFORM_INFO *v16; // r14
  int *v17; // rcx
  unsigned __int64 v18; // rdx
  __int64 v19; // rax
  unsigned __int64 v20; // rdx
  struct TA_TRANSFORM *v22; // [rsp+40h] [rbp-18h] BYREF
  struct CTouchHandleAnimationController::OPACITY_TRANSFORM_INFO *v23; // [rsp+48h] [rbp-10h] BYREF
  CTouchHandleAnimationController *v24; // [rsp+A0h] [rbp+48h] BYREF
  unsigned int v25; // [rsp+A8h] [rbp+50h]
  int v26; // [rsp+B0h] [rbp+58h] BYREF
  int *v27; // [rsp+B8h] [rbp+60h]

  v27 = a4;
  v26 = a3;
  v25 = a2;
  v24 = this;
  v5 = a5;
  v6 = a2;
  *a4 = 0;
  *v5 = 0;
  v7 = OpenThemeData(0, L"Animations");
  if ( v7 )
  {
    v8 = 0;
    v9 = OpenThemeData(0, L"timingfunction");
    if ( v9 )
    {
      v26 = 0;
      LODWORD(v24) = 0;
      ThemeAnimationProperty = GetThemeAnimationProperty(v7, v6, 1, 1, &v26, 4, &v24);
      if ( ThemeAnimationProperty >= 0 )
      {
        v11 = 32LL * (unsigned int)v26;
        if ( !is_mul_ok((unsigned int)v26, 0x20u) )
          v11 = -1;
        v8 = (char *)operator new[](v11, (const struct std::nothrow_t *)&std::nothrow);
        if ( v8 )
        {
          ThemeAnimationProperty = 0;
          v14 = 0;
          if ( v26 > 0 )
          {
            do
            {
              if ( ThemeAnimationProperty < 0 )
                break;
              v22 = 0;
              ThemeAnimationProperty = CTouchHandleAnimationController::_RetrieveTransform(v12, v7, v6, v13, v14, &v22);
              if ( ThemeAnimationProperty >= 0 )
              {
                v15 = v22;
                v23 = 0;
                ThemeAnimationProperty = CTouchHandleAnimationController::_RetrieveTimingCurve(
                                           v12,
                                           v9,
                                           *((_DWORD *)v22 + 1),
                                           &v23);
                if ( ThemeAnimationProperty >= 0 )
                {
                  v16 = v23;
                  *(_DWORD *)v23 = *(_DWORD *)v15;
                  *((float *)v16 + 2) = (float)*((int *)v15 + 3);
                  *((float *)v16 + 1) = (float)*((int *)v15 + 2) * 0.001;
                  *((float *)v16 + 2) = *((float *)v16 + 2) * 0.001;
                  if ( *(_DWORD *)v15 == 2 )
                    *((_DWORD *)v16 + 3) = *((_DWORD *)v15 + 5);
                  v17 = v27;
                  v18 = *v27;
                  v19 = 32 * v18;
                  *(_OWORD *)&v8[v19] = *(_OWORD *)v16;
                  *(_OWORD *)&v8[v19 + 16] = *((_OWORD *)v16 + 1);
                  *v17 = v18 + 1;
                  operator delete(v15, v18);
                  operator delete(v16, 0x20u);
                  v6 = v25;
                }
              }
              ++v14;
            }
            while ( v14 < v26 );
            v5 = a5;
          }
        }
        else
        {
          ThemeAnimationProperty = -2147024882;
        }
      }
      CloseThemeData(v9);
    }
    else
    {
      ThemeAnimationProperty = -2147467259;
    }
    CloseThemeData(v7);
    if ( ThemeAnimationProperty < 0 )
    {
      if ( v8 )
        operator delete(v8, v20);
    }
    else
    {
      *v5 = (struct CTouchHandleAnimationController::OPACITY_TRANSFORM_INFO *)v8;
    }
  }
  else
  {
    return (unsigned int)-2147467259;
  }
  return (unsigned int)ThemeAnimationProperty;
}

```

## disassembly

```asm
0x1802005ac  mov     rax, rsp
0x1802005af  mov     [rax+20h], r9
0x1802005b3  mov     [rax+18h], r8d
0x1802005b7  mov     [rax+10h], edx
0x1802005ba  mov     [rax+8], rcx
0x1802005be  push    rbp
0x1802005bf  push    rbx
0x1802005c0  push    rsi
0x1802005c1  push    rdi
0x1802005c2  push    r12
0x1802005c4  push    r13
0x1802005c6  push    r14
0x1802005c8  push    r15
0x1802005ca  mov     rbp, rsp
0x1802005cd  sub     rsp, 58h
0x1802005d1  mov     rsi, [rbp+arg_20]
0x1802005d5  mov     r14d, edx
0x1802005d8  lea     rdx, aAnimations; "Animations"
0x1802005df  mov     dword ptr [r9], 0
0x1802005e6  xor     ecx, ecx; hwnd
0x1802005e8  mov     qword ptr [rsi], 0
0x1802005ef  call    cs:__imp_OpenThemeData
0x1802005f5  mov     r12, rax
0x1802005f8  test    rax, rax
0x1802005fb  jz      loc_1802007CA
0x180200601  lea     rdx, aTimingfunction; "timingfunction"
0x180200608  xor     ecx, ecx; hwnd
0x18020060a  xor     edi, edi
0x18020060c  call    cs:__imp_OpenThemeData
0x180200612  mov     r13, rax
0x180200615  test    rax, rax
0x180200618  jz      loc_1802007A4
0x18020061e  lea     rax, [rbp+arg_0]
0x180200622  mov     [rbp+arg_10], edi
0x180200625  mov     [rsp+58h+var_28], rax
0x18020062a  mov     edx, r14d
0x18020062d  lea     rax, [rbp+arg_10]
0x180200631  mov     dword ptr [rsp+58h+var_30], 4
0x180200639  mov     qword ptr [rsp+58h+var_38], rax
0x18020063e  mov     rcx, r12
0x180200641  lea     eax, [rdi+1]
0x180200644  mov     dword ptr [rbp+arg_0], edi
0x180200647  mov     r9d, eax
0x18020064a  mov     r8d, eax
0x18020064d  call    cs:__imp_GetThemeAnimationProperty
0x180200653  mov     ebx, eax
0x180200655  test    eax, eax
0x180200657  js      loc_180200792
0x18020065d  mov     ecx, [rbp+arg_10]
0x180200660  lea     eax, [rdi+20h]
0x180200663  mul     rcx
0x180200666  lea     rcx, [rdi-1]
0x18020066a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180200671  cmovb   rax, rcx
0x180200675  mov     rcx, rax; unsigned __int64
0x180200678  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18020067d  mov     rdi, rax
0x180200680  test    rax, rax
0x180200683  jz      loc_18020079D
0x180200689  xor     ebx, ebx
0x18020068b  xor     r15d, r15d
0x18020068e  cmp     [rbp+arg_10], ebx
0x180200691  jle     loc_180200792
0x180200697  test    ebx, ebx
0x180200699  js      loc_18020078E
0x18020069f  lea     rax, [rbp+var_18]
0x1802006a3  mov     [rbp+var_18], 0
0x1802006ab  mov     [rsp+58h+var_30], rax; struct TA_TRANSFORM **
0x1802006b0  mov     r8d, r14d; int
0x1802006b3  mov     rdx, r12; void *
0x1802006b6  mov     [rsp+58h+var_38], r15d; int
0x1802006bb  call    ?_RetrieveTransform@CTouchHandleAnimationController@@AEAAJPEAXHHHPEAPEAUTA_TRANSFORM@@@Z; CTouchHandleAnimationController::_RetrieveTransform(void *,int,int,int,TA_TRANSFORM * *)
0x1802006c0  mov     ebx, eax
0x1802006c2  test    eax, eax
0x1802006c4  js      loc_180200781
0x1802006ca  mov     rsi, [rbp+var_18]
0x1802006ce  lea     r9, [rbp+var_10]; struct CTouchHandleAnimationController::OPACITY_TRANSFORM_INFO **
0x1802006d2  mov     rdx, r13; void *
0x1802006d5  mov     [rbp+var_10], 0
0x1802006dd  mov     r8d, [rsi+4]; unsigned int
0x1802006e1  call    ?_RetrieveTimingCurve@CTouchHandleAnimationController@@AEAAJPEAXKPEAPEAUOPACITY_TRANSFORM_INFO@1@@Z; CTouchHandleAnimationController::_RetrieveTimingCurve(void *,ulong,CTouchHandleAnimationController::OPACITY_TRANSFORM_INFO * *)
0x1802006e6  mov     ebx, eax
0x1802006e8  test    eax, eax
0x1802006ea  js      loc_180200781
0x1802006f0  mov     r14, [rbp+var_10]
0x1802006f4  xorps   xmm0, xmm0
0x1802006f7  mov     eax, [rsi]
0x1802006f9  xorps   xmm1, xmm1
0x1802006fc  mov     [r14], eax
0x1802006ff  mov     eax, [rsi+0Ch]
0x180200702  cvtsi2ss xmm0, rax
0x180200707  movss   dword ptr [r14+8], xmm0
0x18020070d  mov     eax, [rsi+8]
0x180200710  cvtsi2ss xmm1, rax
0x180200715  mulss   xmm1, cs:__real@3a83126f
0x18020071d  movss   dword ptr [r14+4], xmm1
0x180200723  movss   xmm0, dword ptr [r14+8]
0x180200729  mulss   xmm0, cs:__real@3a83126f
0x180200731  movss   dword ptr [r14+8], xmm0
0x180200737  cmp     dword ptr [rsi], 2
0x18020073a  jnz     short loc_180200743
0x18020073c  mov     eax, [rsi+14h]
0x18020073f  mov     [r14+0Ch], eax
0x180200743  mov     rcx, [rbp+arg_18]
0x180200747  movups  xmm0, xmmword ptr [r14]
0x18020074b  movsxd  rdx, dword ptr [rcx]; unsigned __int64
0x18020074e  mov     rax, rdx
0x180200751  shl     rax, 5
0x180200755  movups  xmmword ptr [rax+rdi], xmm0
0x180200759  movups  xmm1, xmmword ptr [r14+10h]
0x18020075e  movups  xmmword ptr [rax+rdi+10h], xmm1
0x180200763  lea     eax, [rdx+1]
0x180200766  mov     [rcx], eax
0x180200768  mov     rcx, rsi; void *
0x18020076b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180200770  mov     edx, 20h ; ' '; unsigned __int64
0x180200775  mov     rcx, r14; void *
0x180200778  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18020077d  mov     r14d, [rbp+arg_8]
0x180200781  inc     r15d
0x180200784  cmp     r15d, [rbp+arg_10]
0x180200788  jl      loc_180200697
0x18020078e  mov     rsi, [rbp+arg_20]
0x180200792  mov     rcx, r13; hTheme
0x180200795  call    cs:__imp_CloseThemeData
0x18020079b  jmp     short loc_1802007A9
0x18020079d  mov     ebx, 8007000Eh
0x1802007a2  jmp     short loc_180200792
0x1802007a4  mov     ebx, 80004005h
0x1802007a9  mov     rcx, r12; hTheme
0x1802007ac  call    cs:__imp_CloseThemeData
0x1802007b2  test    ebx, ebx
0x1802007b4  js      short loc_1802007BB
0x1802007b6  mov     [rsi], rdi
0x1802007b9  jmp     short loc_1802007CF
0x1802007bb  test    rdi, rdi
0x1802007be  jz      short loc_1802007CF
0x1802007c0  mov     rcx, rdi; void *
0x1802007c3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1802007c8  jmp     short loc_1802007CF
0x1802007ca  mov     ebx, 80004005h
0x1802007cf  mov     eax, ebx
0x1802007d1  add     rsp, 58h
0x1802007d5  pop     r15
0x1802007d7  pop     r14
0x1802007d9  pop     r13
0x1802007db  pop     r12
0x1802007dd  pop     rdi
0x1802007de  pop     rsi
0x1802007df  pop     rbx
0x1802007e0  pop     rbp
0x1802007e1  retn
```
