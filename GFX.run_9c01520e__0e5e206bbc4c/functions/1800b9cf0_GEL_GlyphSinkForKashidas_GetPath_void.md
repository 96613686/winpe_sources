# GEL::GlyphSinkForKashidas::GetPath(void)

- ea: `0x1800b9cf0`
- end: `0x1800b9ee2`
- name: `?GetPath@GlyphSinkForKashidas@GEL@@QEAA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@XZ`
- size: `498`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `reparse_path`

## callers

- `0x1800b9000`
- `0x1800b94b0`
- `0x180163850`
- `0x180172690`

## callees

- `0x180020da0`
- `0x180057e70`
- `0x1800706ec`
- `0x180077210`
- `0x1800b9cf0`
- `0x1801c697c`

## import_xrefs

- `mso40uiWin32Client!__imp_?GetGlyphRunOutline@ARC@@YAJAEAUIGeometrySink@1@AEBUIDWriteFontFace@@MPEBGPEBMPEBUDWRITE_GLYPH_OFFSET@@I_N5@Z` at `0x1800b9df1`
- `mso40uiWin32Client!__imp_?GetGlyphRunOutline@ARC@@YAJAEAUIGeometrySink@1@AEBUIDWriteFontFace@@MPEBGPEBMPEBUDWRITE_GLYPH_OFFSET@@I_N5@Z` at `0x1800b9df1`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800b9e7e`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800b9e8d`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800b9e7e`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800b9e8d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall GEL::GlyphSinkForKashidas::GetPath(__int64 a1, _QWORD *a2, __int64 a3, float a4)
{
  int v6; // ebx
  int v7; // edi
  const float *v8; // rsi
  const unsigned __int16 *v9; // r14
  __int64 v10; // rax
  struct ARC::IGeometrySink *v11; // rax
  const struct IDWriteFontFace *v12; // r8
  _QWORD *v13; // rbx
  __int64 v14; // rax
  void *v15; // rdx
  const struct DWRITE_GLYPH_OFFSET *v17; // [rsp+38h] [rbp-79h]
  unsigned int v18; // [rsp+40h] [rbp-71h]
  bool v19; // [rsp+50h] [rbp-61h]
  __int128 v20; // [rsp+58h] [rbp-59h] BYREF
  int v21; // [rsp+68h] [rbp-49h]
  unsigned int v22; // [rsp+6Ch] [rbp-45h]
  Mso::Memory *v23; // [rsp+70h] [rbp-41h]
  int v24; // [rsp+78h] [rbp-39h]
  unsigned int v25; // [rsp+7Ch] [rbp-35h]
  __int64 v26; // [rsp+80h] [rbp-31h] BYREF
  int v27; // [rsp+88h] [rbp-29h]
  unsigned int v28; // [rsp+8Ch] [rbp-25h]
  __int16 v29; // [rsp+90h] [rbp-21h]
  double v30; // [rsp+A0h] [rbp-11h] BYREF
  __int128 v31; // [rsp+A8h] [rbp-9h]
  double v32; // [rsp+B8h] [rbp+7h]
  __int128 v33; // [rsp+C0h] [rbp+Fh]
  _QWORD *v34; // [rsp+118h] [rbp+67h] BYREF

  if ( COERCE_FLOAT(*(_DWORD *)(a1 + 112) & _xmm) <= 0.00000011920929 )
  {
    *a2 = 0;
  }
  else if ( (*(_DWORD *)(a1 + 108) & 6) == 2 )
  {
    GEL::GlyphSinkForKashidas::GetNormalizedPath(a1, a2, a3, a4);
  }
  else
  {
    v20 = 0;
    v21 = 0;
    v22 = 0x80000000;
    v23 = 0;
    v24 = 0;
    v25 = 0x80000000;
    v26 = 0;
    v27 = 0;
    v28 = 0x80000000;
    v29 = 0;
    v30 = COERCE_DOUBLE(&GEL::PathBuilderGeometrySink::`vftable');
    *(_QWORD *)&v31 = &v20;
    DWORD2(v31) = 1;
    v6 = *(_DWORD *)(a1 + 96);
    v7 = *(_DWORD *)(a1 + 8);
    v8 = *(const float **)(a1 + 64);
    v9 = *(const unsigned __int16 **)(a1 + 40);
    v10 = Mso::TCntPtr<Mso::DWriteAssistant::ITextRunSequence>::operator->(a1 + 88);
    v11 = (struct ARC::IGeometrySink *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v10 + 24LL))(v10);
    LOBYTE(v18) = (v6 & 4) != 0;
    LODWORD(v17) = v7;
    ARC::GetGlyphRunOutline((ARC *)&v30, v11, v12, a4, v9, v8, v17, v18, 0, v19);
    GEL::PathBuilder::Finish(&v20, &v34, 1);
    v13 = v34;
    v14 = *v34;
    v30 = (float)(1.0 / *(float *)(a1 + 112));
    v31 = 0;
    v32 = v30;
    v33 = 0;
    (*(void (__fastcall **)(_QWORD *, _QWORD *, double *))(v14 + 128))(v34, a2, &v30);
    if ( v13 )
      (*(void (__fastcall **)(_QWORD *))(*v13 + 8LL))(v13);
    Ofc::TArray<Ofc::TCntPtr<GEL::IEffect const>>::~TArray<Ofc::TCntPtr<GEL::IEffect const>>(&v26);
    if ( v23 )
      Mso::Memory::Free(v23, v15);
    if ( *((_QWORD *)&v20 + 1) )
      Mso::Memory::Free(*((Mso::Memory **)&v20 + 1), v15);
    if ( (_QWORD)v20 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v20 + 8LL))(v20);
  }
  return a2;
}

```

## disassembly

```asm
0x1800b9cf0  mov     rax, rsp
0x1800b9cf3  mov     [rax+10h], rbx
0x1800b9cf7  mov     [rax+18h], rsi
0x1800b9cfb  mov     [rax+20h], rdi
0x1800b9cff  push    rbp
0x1800b9d00  push    r12
0x1800b9d02  push    r13
0x1800b9d04  push    r14
0x1800b9d06  push    r15
0x1800b9d08  lea     rbp, [rax-5Fh]
0x1800b9d0c  sub     rsp, 0E0h
0x1800b9d13  movaps  xmmword ptr [rax-38h], xmm6
0x1800b9d17  mov     r12, rdx
0x1800b9d1a  mov     r13, rcx
0x1800b9d1d  xor     ecx, ecx
0x1800b9d1f  movss   xmm1, dword ptr [r13+70h]
0x1800b9d25  andps   xmm1, cs:__xmm@7fffffff7fffffff7fffffff7fffffff
0x1800b9d2c  movss   xmm0, cs:__real@34000000
0x1800b9d34  comiss  xmm0, xmm1
0x1800b9d37  jnb     loc_1800B9EDC
0x1800b9d3d  mov     eax, [r13+6Ch]
0x1800b9d41  and     al, 6
0x1800b9d43  cmp     al, 2
0x1800b9d45  jz      loc_1800B9ED2
0x1800b9d4b  xorps   xmm0, xmm0
0x1800b9d4e  movdqa  [rbp+57h+var_B0], xmm0
0x1800b9d53  mov     [rbp+57h+var_A0], ecx
0x1800b9d56  mov     eax, 80000000h
0x1800b9d5b  mov     [rbp+57h+var_9C], eax
0x1800b9d5e  mov     [rbp+57h+var_98], rcx
0x1800b9d62  mov     [rbp+57h+var_90], ecx
0x1800b9d65  mov     [rbp+57h+var_8C], eax
0x1800b9d68  mov     [rbp+57h+var_88], rcx
0x1800b9d6c  mov     [rbp+57h+var_80], ecx
0x1800b9d6f  mov     [rbp+57h+var_7C], eax
0x1800b9d72  mov     [rbp+57h+var_78], cx
0x1800b9d76  lea     rax, ??_7PathBuilderGeometrySink@GEL@@6B@; const GEL::PathBuilderGeometrySink::`vftable'
0x1800b9d7d  mov     [rbp+57h+var_68], rax
0x1800b9d81  lea     rax, [rbp+57h+var_B0]
0x1800b9d85  mov     qword ptr [rbp+57h+var_60], rax
0x1800b9d89  mov     dword ptr [rbp+57h+var_60+8], 1
0x1800b9d90  mov     ebx, [r13+60h]
0x1800b9d94  mov     edi, [r13+8]
0x1800b9d98  mov     rsi, [r13+40h]
0x1800b9d9c  mov     r14, [r13+28h]
0x1800b9da0  mov     r15, [r13+10h]
0x1800b9da4  movss   xmm6, dword ptr [r13+68h]
0x1800b9daa  lea     rcx, [r13+58h]
0x1800b9dae  call    ??C?$TCntPtr@UITextRunSequence@DWriteAssistant@Mso@@@Mso@@QEBAPEAUITextRunSequence@DWriteAssistant@1@XZ; Mso::TCntPtr<Mso::DWriteAssistant::ITextRunSequence>::operator->(void)
0x1800b9db3  mov     rdx, rax
0x1800b9db6  mov     rcx, [rax]
0x1800b9db9  mov     rax, [rcx+18h]
0x1800b9dbd  mov     rcx, rdx
0x1800b9dc0  call    cs:__guard_dispatch_icall_fptr
0x1800b9dc6  bt      ebx, 2
0x1800b9dca  setb    cl
0x1800b9dcd  mov     [rsp+100h+var_C0], 0
0x1800b9dd2  mov     [rsp+100h+var_C8], cl
0x1800b9dd6  mov     dword ptr [rsp+100h+var_D0], edi
0x1800b9dda  mov     qword ptr [rsp+100h+var_D8], rsi
0x1800b9ddf  mov     [rsp+100h+var_E0], r14
0x1800b9de4  mov     r9, r15
0x1800b9de7  movaps  xmm2, xmm6
0x1800b9dea  mov     rdx, rax
0x1800b9ded  lea     rcx, [rbp+57h+var_68]
0x1800b9df1  call    cs:__imp_?GetGlyphRunOutline@ARC@@YAJAEAUIGeometrySink@1@AEBUIDWriteFontFace@@MPEBGPEBMPEBUDWRITE_GLYPH_OFFSET@@I_N5@Z; ARC::GetGlyphRunOutline(ARC::IGeometrySink &,IDWriteFontFace const &,float,ushort const *,float const *,DWRITE_GLYPH_OFFSET const *,uint,bool,bool)
0x1800b9df7  mov     r8d, 1
0x1800b9dfd  lea     rdx, [rbp+57h+arg_0]
0x1800b9e01  lea     rcx, [rbp+57h+var_B0]
0x1800b9e05  call    ?Finish@PathBuilder@GEL@@QEAA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@W4FillMode@Path@Graphics@Mso@@@Z; GEL::PathBuilder::Finish(Mso::Graphics::Path::FillMode)
0x1800b9e0a  mov     rbx, [rbp+57h+arg_0]
0x1800b9e0e  mov     rax, [rbx]
0x1800b9e11  movss   xmm0, cs:__real@3f800000
0x1800b9e19  divss   xmm0, dword ptr [r13+70h]
0x1800b9e1f  cvtps2pd xmm1, xmm0
0x1800b9e22  movsd   [rbp+57h+var_68], xmm1
0x1800b9e27  xorps   xmm0, xmm0
0x1800b9e2a  movups  [rbp+57h+var_60], xmm0
0x1800b9e2e  movsd   [rbp+57h+var_50], xmm1
0x1800b9e33  xorps   xmm1, xmm1
0x1800b9e36  movups  [rbp+57h+var_48], xmm1
0x1800b9e3a  lea     r8, [rbp+57h+var_68]
0x1800b9e3e  mov     rdx, r12
0x1800b9e41  mov     rcx, rbx
0x1800b9e44  mov     rax, [rax+80h]
0x1800b9e4b  nop     dword ptr [rax+rax+00h]
0x1800b9e50  call    cs:__guard_dispatch_icall_fptr
0x1800b9e56  test    rbx, rbx
0x1800b9e59  jz      short loc_1800B9E6C
0x1800b9e5b  mov     rax, [rbx]
0x1800b9e5e  mov     rcx, rbx
0x1800b9e61  mov     rax, [rax+8]
0x1800b9e65  call    cs:__guard_dispatch_icall_fptr
0x1800b9e6b  nop
0x1800b9e6c  lea     rcx, [rbp+57h+var_88]
0x1800b9e70  call    ??1?$TArray@V?$TCntPtr@$$CBUIEffect@GEL@@@Ofc@@@Ofc@@QEAA@XZ; Ofc::TArray<Ofc::TCntPtr<GEL::IEffect const>>::~TArray<Ofc::TCntPtr<GEL::IEffect const>>(void)
0x1800b9e75  mov     rcx, [rbp+57h+var_98]
0x1800b9e79  test    rcx, rcx
0x1800b9e7c  jz      short loc_1800B9E84
0x1800b9e7e  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x1800b9e84  mov     rcx, qword ptr [rbp+57h+var_B0+8]
0x1800b9e88  test    rcx, rcx
0x1800b9e8b  jz      short loc_1800B9E93
0x1800b9e8d  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x1800b9e93  mov     rcx, qword ptr [rbp+57h+var_B0]
0x1800b9e97  test    rcx, rcx
0x1800b9e9a  jz      short loc_1800B9EA9
0x1800b9e9c  mov     rax, [rcx]
0x1800b9e9f  mov     rax, [rax+8]
0x1800b9ea3  call    cs:__guard_dispatch_icall_fptr
0x1800b9ea9  mov     rax, r12
0x1800b9eac  lea     r11, [rsp+100h+var_20]
0x1800b9eb4  mov     rbx, [r11+38h]
0x1800b9eb8  mov     rsi, [r11+40h]
0x1800b9ebc  mov     rdi, [r11+48h]
0x1800b9ec0  movaps  xmm6, xmmword ptr [r11-10h]
0x1800b9ec5  mov     rsp, r11
0x1800b9ec8  pop     r15
0x1800b9eca  pop     r14
0x1800b9ecc  pop     r13
0x1800b9ece  pop     r12
0x1800b9ed0  pop     rbp
0x1800b9ed1  retn
0x1800b9ed2  mov     rcx, r13
0x1800b9ed5  call    ?GetNormalizedPath@GlyphSinkForKashidas@GEL@@QEAA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@XZ; GEL::GlyphSinkForKashidas::GetNormalizedPath(void)
0x1800b9eda  jmp     short loc_1800B9EA9
0x1800b9edc  mov     [rdx], rcx
0x1800b9edf  jmp     short loc_1800B9EA9
```
