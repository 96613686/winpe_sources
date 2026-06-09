# CreateHPGLPenBrush(_DEVOBJ *,_HPGLMARKER *,_POINTL *,_BRUSHOBJ *,ulong,ESTYLUSTYPE,int)

- ea: `0x180067d58`
- end: `0x180067fc2`
- name: `?CreateHPGLPenBrush@@YAHPEAU_DEVOBJ@@PEAU_HPGLMARKER@@PEAU_POINTL@@PEAU_BRUSHOBJ@@KW4ESTYLUSTYPE@@H@Z`
- size: `618`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, BRUSHOBJ *, unsigned int, int, int)`
- caller_count: `7`
- callee_count: `7`
- tags: ``

## callers

- `0x180062c04`
- `0x1800641a0`
- `0x1800643a0`
- `0x180064560`
- `0x180064720`
- `0x18006496c`
- `0x180069090`

## callees

- `0x1800669f0`
- `0x180067860`
- `0x180067d58`
- `0x180067fc8`
- `0x18006a2d0`
- `0x18006cb6c`
- `0x18006d4d4`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180067efe`
- `KERNEL32!SetLastError` at `0x180067fa2`
- `KERNEL32!SetLastError` at `0x180067efe`
- `KERNEL32!SetLastError` at `0x180067fa2`
- `GDI32!BRUSHOBJ_pvGetRbrush` at `0x180067ddd`
- `GDI32!BRUSHOBJ_pvGetRbrush` at `0x180067ddd`

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
  _DWORD *Rbrush; // rax
  __int64 v15; // r15
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
  int SolidPatternColor; // eax
  unsigned __int8 *v27; // r8
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
          v27 = (unsigned __int8 *)a4;
          return (unsigned int)BHandleSolidPenBrushCase(a1, (struct _HPGLMARKER *)a2, v27);
        }
        *(_DWORD *)(v11 + 4468) = a7;
        Rbrush = BRUSHOBJ_pvGetRbrush(a4);
        v15 = (__int64)Rbrush;
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
              v20 = (unsigned int)(*Rbrush - 1);
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
                  v27 = (unsigned __int8 *)&v30;
                  return (unsigned int)BHandleSolidPenBrushCase(a1, (struct _HPGLMARKER *)a2, v27);
                }
                v25 = v24 - 1;
                if ( v25 )
                {
                  if ( v25 == 1 )
                  {
                    SolidPatternColor = GetSolidPatternColor((struct _BRUSHINFO *)v15);
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
                    *(_DWORD *)(a2 + 20) = *(_DWORD *)(v15 + 36);
                    *(_DWORD *)(a2 + 12) = _mm_cvtsi128_si32(_mm_srli_si128(v22, 8));
                    *(_DWORD *)(a2 + 8) = _mm_cvtsi128_si32(_mm_srli_si128(v22, 4));
                    if ( *(_DWORD *)(*(_QWORD *)(a1 + 8) + 4464LL) )
                    {
                      v28 = HPGL_ChoosePenByColor(
                              (struct _DEVOBJ *)a1,
                              (struct _PENPOOL *)(v16 + 320),
                              *(_DWORD *)(v15 + 32));
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
0x180067d58  push    rbx
0x180067d5a  push    rbp
0x180067d5b  push    rsi
0x180067d5c  push    rdi
0x180067d5d  push    r12
0x180067d5f  push    r13
0x180067d61  push    r14
0x180067d63  push    r15
0x180067d65  sub     rsp, 68h
0x180067d69  mov     rbp, r9
0x180067d6c  mov     r13, r8
0x180067d6f  mov     rdi, rdx
0x180067d72  mov     rsi, rcx
0x180067d75  test    rcx, rcx
0x180067d78  jz      loc_180067F9D
0x180067d7e  test    rdx, rdx
0x180067d81  jz      loc_180067F9D
0x180067d87  mov     r14, [rcx+8]
0x180067d8b  test    r14, r14
0x180067d8e  jz      loc_180067F9D
0x180067d94  mov     eax, [rsp+0A8h+arg_20]
0x180067d9b  mov     ebx, 1
0x180067da0  shr     eax, 1
0x180067da2  and     eax, ebx
0x180067da4  mov     [rdx+4], eax
0x180067da7  call    ?HPGL_LazyInit@@YAHPEAU_DEVOBJ@@@Z; HPGL_LazyInit(_DEVOBJ *)
0x180067dac  test    rbp, rbp
0x180067daf  jnz     short loc_180067DC1
0x180067db1  mov     rdx, rdi; struct _HPGLMARKER *
0x180067db4  mov     rcx, rsi; struct _DEVOBJ *
0x180067db7  call    ?CreateNULLHPGLPenBrush@@YAHPEAU_DEVOBJ@@PEAU_HPGLMARKER@@@Z; CreateNULLHPGLPenBrush(_DEVOBJ *,_HPGLMARKER *)
0x180067dbc  jmp     loc_180067F97
0x180067dc1  cmp     dword ptr [rbp+0], 0FFFFFFFFh
0x180067dc5  jnz     loc_180067F7E
0x180067dcb  mov     r12d, [rsp+0A8h+arg_30]
0x180067dd3  mov     rcx, rbp; pbo
0x180067dd6  mov     [r14+1174h], r12d
0x180067ddd  call    cs:__imp_BRUSHOBJ_pvGetRbrush
0x180067de4  nop     dword ptr [rax+rax+00h]
0x180067de9  xor     ebp, ebp
0x180067deb  mov     r15, rax
0x180067dee  mov     [r14+1174h], ebp
0x180067df5  mov     r9, [rsi+1050h]
0x180067dfc  mov     [rsi+8], r9
0x180067e00  test    rax, rax
0x180067e03  jz      loc_180067F0A
0x180067e09  mov     rcx, [r14+1138h]
0x180067e10  mov     r8, [rcx+10h]
0x180067e14  test    r8, r8
0x180067e17  jz      loc_180067F0A
0x180067e1d  mov     edx, [rcx+4]
0x180067e20  test    edx, edx
0x180067e22  jz      loc_180067F0A
0x180067e28  mov     eax, [rax]
0x180067e2a  dec     eax
0x180067e2c  cmp     [rcx+8], ebp
0x180067e2f  jnz     short loc_180067E33
0x180067e31  mov     edx, [rcx]
0x180067e33  cmp     eax, edx
0x180067e35  jnb     loc_180067F0A
0x180067e3b  lea     rax, [rax+rax*8]
0x180067e3f  movups  xmm1, xmmword ptr [r8+rax*4]
0x180067e44  movups  xmm0, xmmword ptr [r8+rax*4+10h]
0x180067e4a  mov     eax, [r8+rax*4+20h]
0x180067e4f  movd    ecx, xmm1
0x180067e53  movups  [rsp+0A8h+var_68], xmm0
0x180067e58  mov     [rsp+0A8h+var_58], eax
0x180067e5c  sub     ecx, ebx
0x180067e5e  jz      loc_180067F5F
0x180067e64  sub     ecx, ebx
0x180067e66  jz      loc_180067EEF
0x180067e6c  cmp     ecx, ebx
0x180067e6e  jnz     loc_180067F0A
0x180067e74  mov     rcx, r15; struct _BRUSHINFO *
0x180067e77  call    ?GetSolidPatternColor@@YAKPEAU_BRUSHINFO@@@Z; GetSolidPatternColor(_BRUSHINFO *)
0x180067e7c  cmp     eax, 0FFFFFFFFh
0x180067e7f  jnz     short loc_180067ECD
0x180067e81  mov     eax, [rsp+0A8h+arg_28]
0x180067e88  mov     ecx, 2
0x180067e8d  test    eax, eax
0x180067e8f  jnz     short loc_180067E96
0x180067e91  mov     [rdi+24h], ecx
0x180067e94  jmp     short loc_180067EA1
0x180067e96  cmp     eax, ebx
0x180067e98  jnz     short loc_180067EA1
0x180067e9a  mov     dword ptr [rdi+24h], 0Bh
0x180067ea1  mov     [rdi], ecx
0x180067ea3  mov     r9, r15
0x180067ea6  psrldq  xmm1, 4
0x180067eab  mov     rcx, rsi
0x180067eae  mov     r8, r13
0x180067eb1  movd    dword ptr [rdi+8], xmm1
0x180067eb6  mov     rdx, rdi
0x180067eb9  call    ?DownloadPatternFill@@YAHPEAU_DEVOBJ@@PEAU_HPGLMARKER@@PEAU_POINTL@@PEAU_BRUSHINFO@@W4ESTYLUSTYPE@@@Z; DownloadPatternFill(_DEVOBJ *,_HPGLMARKER *,_POINTL *,_BRUSHINFO *,ESTYLUSTYPE)
0x180067ebe  mov     ebx, eax
0x180067ec0  test    eax, eax
0x180067ec2  jnz     loc_180067F99
0x180067ec8  jmp     loc_180067DB1
0x180067ecd  xorps   xmm0, xmm0
0x180067ed0  xor     ecx, ecx
0x180067ed2  movups  [rsp+0A8h+var_78], xmm0
0x180067ed7  mov     dword ptr [rsp+0A8h+var_78], eax
0x180067edb  mov     qword ptr [rsp+0A8h+var_68], rcx
0x180067ee0  mov     [rsp+0A8h+var_88], r12d
0x180067ee5  lea     r8, [rsp+0A8h+var_78]
0x180067eea  jmp     loc_180067F8C
0x180067eef  lea     rdx, [r9+0D8h]
0x180067ef6  test    rdx, rdx
0x180067ef9  jnz     short loc_180067F11
0x180067efb  lea     ecx, [rdx+0Dh]; dwErrCode
0x180067efe  call    cs:__imp_SetLastError
0x180067f05  nop     dword ptr [rax+rax+00h]
0x180067f0a  mov     ebx, ebp
0x180067f0c  jmp     loc_180067F99
0x180067f11  mov     dword ptr [rdi], 3
0x180067f17  movdqa  xmm0, xmm1
0x180067f1b  mov     eax, [r15+24h]
0x180067f1f  mov     [rdi+14h], eax
0x180067f22  psrldq  xmm0, 8
0x180067f27  movd    dword ptr [rdi+0Ch], xmm0
0x180067f2c  psrldq  xmm1, 4
0x180067f31  movd    dword ptr [rdi+8], xmm1
0x180067f36  mov     rax, [rsi+8]
0x180067f3a  cmp     [rax+1170h], ebp
0x180067f40  jz      short loc_180067F99
0x180067f42  mov     r8d, [r15+20h]; unsigned int
0x180067f46  add     rdx, 68h ; 'h'; struct _PENPOOL *
0x180067f4a  mov     rcx, rsi; struct _DEVOBJ *
0x180067f4d  call    ?HPGL_ChoosePenByColor@@YAJPEAU_DEVOBJ@@PEAU_PENPOOL@@K@Z; HPGL_ChoosePenByColor(_DEVOBJ *,_PENPOOL *,ulong)
0x180067f52  cmp     eax, 0FFFFFFFFh
0x180067f55  mov     [rdi+10h], eax
0x180067f58  mov     ebx, ebp
0x180067f5a  setnz   bl
0x180067f5d  jmp     short loc_180067F99
0x180067f5f  xorps   xmm0, xmm0
0x180067f62  psrldq  xmm1, 8
0x180067f67  xor     eax, eax
0x180067f69  movups  [rsp+0A8h+var_78], xmm0
0x180067f6e  mov     qword ptr [rsp+0A8h+var_68], rax
0x180067f73  movd    dword ptr [rsp+0A8h+var_78], xmm1
0x180067f79  jmp     loc_180067EE0
0x180067f7e  mov     eax, [rsp+0A8h+arg_30]
0x180067f85  mov     r8, rbp
0x180067f88  mov     [rsp+0A8h+var_88], eax
0x180067f8c  mov     rdx, rdi
0x180067f8f  mov     rcx, rsi
0x180067f92  call    ?BHandleSolidPenBrushCase@@YAHPEAU_DEVOBJ@@PEAU_HPGLMARKER@@PEAU_BRUSHOBJ@@W4ERenderLanguage@@H@Z; BHandleSolidPenBrushCase(_DEVOBJ *,_HPGLMARKER *,_BRUSHOBJ *,ERenderLanguage,int)
0x180067f97  mov     ebx, eax
0x180067f99  mov     eax, ebx
0x180067f9b  jmp     short loc_180067FB0
0x180067f9d  mov     ecx, 0Dh; dwErrCode
0x180067fa2  call    cs:__imp_SetLastError
0x180067fa9  nop     dword ptr [rax+rax+00h]
0x180067fae  xor     eax, eax
0x180067fb0  add     rsp, 68h
0x180067fb4  pop     r15
0x180067fb6  pop     r14
0x180067fb8  pop     r13
0x180067fba  pop     r12
0x180067fbc  pop     rdi
0x180067fbd  pop     rsi
0x180067fbe  pop     rbp
0x180067fbf  pop     rbx
0x180067fc0  retn
```
