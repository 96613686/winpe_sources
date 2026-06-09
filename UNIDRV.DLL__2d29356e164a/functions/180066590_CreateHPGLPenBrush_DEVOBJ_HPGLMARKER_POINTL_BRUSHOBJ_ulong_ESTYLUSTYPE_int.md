# CreateHPGLPenBrush(_DEVOBJ *,_HPGLMARKER *,_POINTL *,_BRUSHOBJ *,ulong,ESTYLUSTYPE,int)

- ea: `0x180066590`
- end: `0x1800667e7`
- name: `?CreateHPGLPenBrush@@YAHPEAU_DEVOBJ@@PEAU_HPGLMARKER@@PEAU_POINTL@@PEAU_BRUSHOBJ@@KW4ESTYLUSTYPE@@H@Z`
- size: `599`
- prototype: ``
- caller_count: `7`
- callee_count: `7`
- tags: ``

## callers

- `0x1800616d4`
- `0x180062ba0`
- `0x180062d90`
- `0x180062f30`
- `0x1800630f0`
- `0x180063328`
- `0x180067864`

## callees

- `0x1800652c8`
- `0x1800660b4`
- `0x180066590`
- `0x1800667f0`
- `0x180068a28`
- `0x18006b1e0`
- `0x18006bb30`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180066730`
- `KERNEL32!SetLastError` at `0x1800667ce`
- `KERNEL32!SetLastError` at `0x180066730`
- `KERNEL32!SetLastError` at `0x1800667ce`
- `GDI32!BRUSHOBJ_pvGetRbrush` at `0x180066615`
- `GDI32!BRUSHOBJ_pvGetRbrush` at `0x180066615`

## pseudocode

```c
__int64 __fastcall CreateHPGLPenBrush(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        BRUSHOBJ *a4,
        unsigned int a5,
        int a6,
        int a7)
{
  __int64 v11; // r14
  unsigned int v12; // ebx
  struct _BRUSHINFO *Rbrush; // rax
  struct _BRUSHINFO *v15; // r15
  __int64 v16; // r9
  __int64 v17; // rcx
  __int64 v18; // r8
  unsigned int v19; // edx
  __int64 v20; // rax
  __int64 v21; // rax
  __m128i v22; // xmm1
  __int128 v23; // xmm0
  int v24; // ecx
  int v25; // ecx
  unsigned int SolidPatternColor; // eax
  BRUSHOBJ *v27; // r8
  int v28; // eax
  __int128 v30; // [rsp+30h] [rbp-78h] BYREF
  __int128 v31; // [rsp+40h] [rbp-68h]
  int v32; // [rsp+50h] [rbp-58h]

  if ( a1 )
  {
    if ( a2 )
    {
      v11 = *(_QWORD *)(a1 + 8);
      if ( v11 )
      {
        v12 = 1;
        *(_DWORD *)(a2 + 4) = (a5 >> 1) & 1;
        HPGL_LazyInit((struct _DEVOBJ *)a1);
        if ( !a4 )
          return (unsigned int)CreateNULLHPGLPenBrush((struct _DEVOBJ *)a1, (struct _HPGLMARKER *)a2);
        if ( a4->iSolidColor != -1 )
        {
          v27 = a4;
          return (unsigned int)BHandleSolidPenBrushCase(a1, a2, v27);
        }
        *(_DWORD *)(v11 + 4468) = a7;
        Rbrush = (struct _BRUSHINFO *)BRUSHOBJ_pvGetRbrush(a4);
        v15 = Rbrush;
        *(_DWORD *)(v11 + 4468) = 0;
        v16 = *(_QWORD *)(a1 + 4176);
        *(_QWORD *)(a1 + 8) = v16;
        if ( Rbrush )
        {
          v17 = *(_QWORD *)(v11 + 4408);
          v18 = *(_QWORD *)(v17 + 16);
          if ( v18 )
          {
            v19 = *(_DWORD *)(v17 + 4);
            if ( v19 )
            {
              v20 = (unsigned int)(*(_DWORD *)Rbrush - 1);
              if ( !*(_DWORD *)(v17 + 8) )
                v19 = *(_DWORD *)v17;
              if ( (unsigned int)v20 < v19 )
              {
                v21 = 9 * v20;
                v22 = *(__m128i *)(v18 + 4 * v21);
                v23 = *(_OWORD *)(v18 + 4 * v21 + 16);
                LODWORD(v21) = *(_DWORD *)(v18 + 4 * v21 + 32);
                v31 = v23;
                v32 = v21;
                v24 = _mm_cvtsi128_si32(v22) - 1;
                if ( !v24 )
                {
                  v30 = 0;
                  *(_QWORD *)&v31 = 0;
                  LODWORD(v30) = _mm_cvtsi128_si32(_mm_srli_si128(v22, 8));
LABEL_24:
                  v27 = (BRUSHOBJ *)&v30;
                  return (unsigned int)BHandleSolidPenBrushCase(a1, a2, v27);
                }
                v25 = v24 - 1;
                if ( v25 )
                {
                  if ( v25 == 1 )
                  {
                    SolidPatternColor = GetSolidPatternColor(v15);
                    if ( SolidPatternColor == -1 )
                    {
                      if ( a6 )
                      {
                        if ( a6 == 1 )
                          *(_DWORD *)(a2 + 36) = 11;
                      }
                      else
                      {
                        *(_DWORD *)(a2 + 36) = 2;
                      }
                      *(_DWORD *)a2 = 2;
                      *(_DWORD *)(a2 + 8) = _mm_cvtsi128_si32(_mm_srli_si128(v22, 4));
                      v12 = DownloadPatternFill(a1, a2, a3, v15);
                      if ( v12 )
                        return v12;
                      return (unsigned int)CreateNULLHPGLPenBrush((struct _DEVOBJ *)a1, (struct _HPGLMARKER *)a2);
                    }
                    v30 = 0;
                    LODWORD(v30) = SolidPatternColor;
                    *(_QWORD *)&v31 = 0;
                    goto LABEL_24;
                  }
                }
                else
                {
                  if ( v16 != -216 )
                  {
                    *(_DWORD *)a2 = 3;
                    *(_DWORD *)(a2 + 20) = *((_DWORD *)v15 + 9);
                    *(_DWORD *)(a2 + 12) = _mm_cvtsi128_si32(_mm_srli_si128(v22, 8));
                    *(_DWORD *)(a2 + 8) = _mm_cvtsi128_si32(_mm_srli_si128(v22, 4));
                    if ( *(_DWORD *)(*(_QWORD *)(a1 + 8) + 4464LL) )
                    {
                      v28 = HPGL_ChoosePenByColor(
                              (struct _DEVOBJ *)a1,
                              (struct _PENPOOL *)(v16 + 320),
                              *((_DWORD *)v15 + 8));
                      *(_DWORD *)(a2 + 16) = v28;
                      return v28 != -1;
                    }
                    return v12;
                  }
                  SetLastError(0xDu);
                }
              }
            }
          }
        }
        return 0;
      }
    }
  }
  SetLastError(0xDu);
  return 0;
}

```

## disassembly

```asm
0x180066590  push    rbx
0x180066592  push    rbp
0x180066593  push    rsi
0x180066594  push    rdi
0x180066595  push    r12
0x180066597  push    r13
0x180066599  push    r14
0x18006659b  push    r15
0x18006659d  sub     rsp, 68h
0x1800665a1  mov     rbp, r9
0x1800665a4  mov     r13, r8
0x1800665a7  mov     rdi, rdx
0x1800665aa  mov     rsi, rcx
0x1800665ad  test    rcx, rcx
0x1800665b0  jz      loc_1800667C9
0x1800665b6  test    rdx, rdx
0x1800665b9  jz      loc_1800667C9
0x1800665bf  mov     r14, [rcx+8]
0x1800665c3  test    r14, r14
0x1800665c6  jz      loc_1800667C9
0x1800665cc  mov     eax, [rsp+0A8h+arg_20]
0x1800665d3  mov     ebx, 1
0x1800665d8  shr     eax, 1
0x1800665da  and     eax, ebx
0x1800665dc  mov     [rdx+4], eax
0x1800665df  call    ?HPGL_LazyInit@@YAHPEAU_DEVOBJ@@@Z; HPGL_LazyInit(_DEVOBJ *)
0x1800665e4  test    rbp, rbp
0x1800665e7  jnz     short loc_1800665F9
0x1800665e9  mov     rdx, rdi; struct _HPGLMARKER *
0x1800665ec  mov     rcx, rsi; struct _DEVOBJ *
0x1800665ef  call    ?CreateNULLHPGLPenBrush@@YAHPEAU_DEVOBJ@@PEAU_HPGLMARKER@@@Z; CreateNULLHPGLPenBrush(_DEVOBJ *,_HPGLMARKER *)
0x1800665f4  jmp     loc_1800667C3
0x1800665f9  cmp     dword ptr [rbp+0], 0FFFFFFFFh
0x1800665fd  jnz     loc_1800667AA
0x180066603  mov     r12d, [rsp+0A8h+arg_30]
0x18006660b  mov     rcx, rbp; pbo
0x18006660e  mov     [r14+1174h], r12d
0x180066615  call    cs:__imp_BRUSHOBJ_pvGetRbrush
0x18006661b  xor     ebp, ebp
0x18006661d  mov     r15, rax
0x180066620  mov     [r14+1174h], ebp
0x180066627  mov     r9, [rsi+1050h]
0x18006662e  mov     [rsi+8], r9
0x180066632  test    rax, rax
0x180066635  jz      loc_180066736
0x18006663b  mov     rcx, [r14+1138h]
0x180066642  mov     r8, [rcx+10h]
0x180066646  test    r8, r8
0x180066649  jz      loc_180066736
0x18006664f  mov     edx, [rcx+4]
0x180066652  test    edx, edx
0x180066654  jz      loc_180066736
0x18006665a  mov     eax, [rax]
0x18006665c  dec     eax
0x18006665e  cmp     [rcx+8], ebp
0x180066661  jnz     short loc_180066665
0x180066663  mov     edx, [rcx]
0x180066665  cmp     eax, edx
0x180066667  jnb     loc_180066736
0x18006666d  lea     rax, [rax+rax*8]
0x180066671  movups  xmm1, xmmword ptr [r8+rax*4]
0x180066676  movups  xmm0, xmmword ptr [r8+rax*4+10h]
0x18006667c  mov     eax, [r8+rax*4+20h]
0x180066681  movd    ecx, xmm1
0x180066685  movups  [rsp+0A8h+var_68], xmm0
0x18006668a  mov     [rsp+0A8h+var_58], eax
0x18006668e  sub     ecx, ebx
0x180066690  jz      loc_18006678B
0x180066696  sub     ecx, ebx
0x180066698  jz      loc_180066721
0x18006669e  cmp     ecx, ebx
0x1800666a0  jnz     loc_180066736
0x1800666a6  mov     rcx, r15; struct _BRUSHINFO *
0x1800666a9  call    ?GetSolidPatternColor@@YAKPEAU_BRUSHINFO@@@Z; GetSolidPatternColor(_BRUSHINFO *)
0x1800666ae  cmp     eax, 0FFFFFFFFh
0x1800666b1  jnz     short loc_1800666FF
0x1800666b3  mov     eax, [rsp+0A8h+arg_28]
0x1800666ba  mov     ecx, 2
0x1800666bf  test    eax, eax
0x1800666c1  jnz     short loc_1800666C8
0x1800666c3  mov     [rdi+24h], ecx
0x1800666c6  jmp     short loc_1800666D3
0x1800666c8  cmp     eax, ebx
0x1800666ca  jnz     short loc_1800666D3
0x1800666cc  mov     dword ptr [rdi+24h], 0Bh
0x1800666d3  mov     [rdi], ecx
0x1800666d5  mov     r9, r15
0x1800666d8  psrldq  xmm1, 4
0x1800666dd  mov     rcx, rsi
0x1800666e0  mov     r8, r13
0x1800666e3  movd    dword ptr [rdi+8], xmm1
0x1800666e8  mov     rdx, rdi
0x1800666eb  call    ?DownloadPatternFill@@YAHPEAU_DEVOBJ@@PEAU_HPGLMARKER@@PEAU_POINTL@@PEAU_BRUSHINFO@@W4ESTYLUSTYPE@@@Z; DownloadPatternFill(_DEVOBJ *,_HPGLMARKER *,_POINTL *,_BRUSHINFO *,ESTYLUSTYPE)
0x1800666f0  mov     ebx, eax
0x1800666f2  test    eax, eax
0x1800666f4  jnz     loc_1800667C5
0x1800666fa  jmp     loc_1800665E9
0x1800666ff  xorps   xmm0, xmm0
0x180066702  xor     ecx, ecx
0x180066704  movups  [rsp+0A8h+var_78], xmm0
0x180066709  mov     dword ptr [rsp+0A8h+var_78], eax
0x18006670d  mov     qword ptr [rsp+0A8h+var_68], rcx
0x180066712  mov     [rsp+0A8h+var_88], r12d
0x180066717  lea     r8, [rsp+0A8h+var_78]
0x18006671c  jmp     loc_1800667B8
0x180066721  lea     rdx, [r9+0D8h]
0x180066728  test    rdx, rdx
0x18006672b  jnz     short loc_18006673D
0x18006672d  lea     ecx, [rdx+0Dh]; dwErrCode
0x180066730  call    cs:__imp_SetLastError
0x180066736  mov     ebx, ebp
0x180066738  jmp     loc_1800667C5
0x18006673d  mov     dword ptr [rdi], 3
0x180066743  movdqa  xmm0, xmm1
0x180066747  mov     eax, [r15+24h]
0x18006674b  mov     [rdi+14h], eax
0x18006674e  psrldq  xmm0, 8
0x180066753  movd    dword ptr [rdi+0Ch], xmm0
0x180066758  psrldq  xmm1, 4
0x18006675d  movd    dword ptr [rdi+8], xmm1
0x180066762  mov     rax, [rsi+8]
0x180066766  cmp     [rax+1170h], ebp
0x18006676c  jz      short loc_1800667C5
0x18006676e  mov     r8d, [r15+20h]; unsigned int
0x180066772  add     rdx, 68h ; 'h'; struct _PENPOOL *
0x180066776  mov     rcx, rsi; struct _DEVOBJ *
0x180066779  call    ?HPGL_ChoosePenByColor@@YAJPEAU_DEVOBJ@@PEAU_PENPOOL@@K@Z; HPGL_ChoosePenByColor(_DEVOBJ *,_PENPOOL *,ulong)
0x18006677e  cmp     eax, 0FFFFFFFFh
0x180066781  mov     [rdi+10h], eax
0x180066784  mov     ebx, ebp
0x180066786  setnz   bl
0x180066789  jmp     short loc_1800667C5
0x18006678b  xorps   xmm0, xmm0
0x18006678e  psrldq  xmm1, 8
0x180066793  xor     eax, eax
0x180066795  movups  [rsp+0A8h+var_78], xmm0
0x18006679a  mov     qword ptr [rsp+0A8h+var_68], rax
0x18006679f  movd    dword ptr [rsp+0A8h+var_78], xmm1
0x1800667a5  jmp     loc_180066712
0x1800667aa  mov     eax, [rsp+0A8h+arg_30]
0x1800667b1  mov     r8, rbp
0x1800667b4  mov     [rsp+0A8h+var_88], eax
0x1800667b8  mov     rdx, rdi
0x1800667bb  mov     rcx, rsi
0x1800667be  call    ?BHandleSolidPenBrushCase@@YAHPEAU_DEVOBJ@@PEAU_HPGLMARKER@@PEAU_BRUSHOBJ@@W4ERenderLanguage@@H@Z; BHandleSolidPenBrushCase(_DEVOBJ *,_HPGLMARKER *,_BRUSHOBJ *,ERenderLanguage,int)
0x1800667c3  mov     ebx, eax
0x1800667c5  mov     eax, ebx
0x1800667c7  jmp     short loc_1800667D6
0x1800667c9  mov     ecx, 0Dh; dwErrCode
0x1800667ce  call    cs:__imp_SetLastError
0x1800667d4  xor     eax, eax
0x1800667d6  add     rsp, 68h
0x1800667da  pop     r15
0x1800667dc  pop     r14
0x1800667de  pop     r13
0x1800667e0  pop     r12
0x1800667e2  pop     rdi
0x1800667e3  pop     rsi
0x1800667e4  pop     rbp
0x1800667e5  pop     rbx
0x1800667e6  retn
```
