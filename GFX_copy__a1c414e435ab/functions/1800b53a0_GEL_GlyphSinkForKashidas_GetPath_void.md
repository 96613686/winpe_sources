# GEL::GlyphSinkForKashidas::GetPath(void)

- ea: `0x1800b53a0`
- end: `0x1800b5592`
- name: `?GetPath@GlyphSinkForKashidas@GEL@@QEAA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@XZ`
- size: `498`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `reparse_path`

## callers

- `0x1800b4ad0`
- `0x1800b6970`
- `0x180161750`
- `0x18016d950`

## callees

- `0x180020e70`
- `0x1800573f0`
- `0x180064e30`
- `0x18007a4f0`
- `0x1800b53a0`
- `0x1801c2e4c`

## import_xrefs

- `mso40uiWin32Client!__imp_?GetGlyphRunOutline@ARC@@YAJAEAUIGeometrySink@1@AEBUIDWriteFontFace@@MPEBGPEBMPEBUDWRITE_GLYPH_OFFSET@@I_N5@Z` at `0x1800b54a1`
- `mso40uiWin32Client!__imp_?GetGlyphRunOutline@ARC@@YAJAEAUIGeometrySink@1@AEBUIDWriteFontFace@@MPEBGPEBMPEBUDWRITE_GLYPH_OFFSET@@I_N5@Z` at `0x1800b54a1`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800b552e`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800b553d`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800b552e`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800b553d`

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
    v10 = Mso::TCntPtr<IWICImagingFactory>::operator->(a1 + 88);
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
0x1800b53a0  mov     rax, rsp
0x1800b53a3  mov     [rax+10h], rbx
0x1800b53a7  mov     [rax+18h], rsi
0x1800b53ab  mov     [rax+20h], rdi
0x1800b53af  push    rbp
0x1800b53b0  push    r12
0x1800b53b2  push    r13
0x1800b53b4  push    r14
0x1800b53b6  push    r15
0x1800b53b8  lea     rbp, [rax-5Fh]
0x1800b53bc  sub     rsp, 0E0h
0x1800b53c3  movaps  xmmword ptr [rax-38h], xmm6
0x1800b53c7  mov     r12, rdx
0x1800b53ca  mov     r13, rcx
0x1800b53cd  xor     ecx, ecx
0x1800b53cf  movss   xmm1, dword ptr [r13+70h]
0x1800b53d5  andps   xmm1, cs:__xmm@7fffffff7fffffff7fffffff7fffffff
0x1800b53dc  movss   xmm0, cs:__real@34000000
0x1800b53e4  comiss  xmm0, xmm1
0x1800b53e7  jnb     loc_1800B558C
0x1800b53ed  mov     eax, [r13+6Ch]
0x1800b53f1  and     al, 6
0x1800b53f3  cmp     al, 2
0x1800b53f5  jz      loc_1800B5582
0x1800b53fb  xorps   xmm0, xmm0
0x1800b53fe  movdqa  [rbp+57h+var_B0], xmm0
0x1800b5403  mov     [rbp+57h+var_A0], ecx
0x1800b5406  mov     eax, 80000000h
0x1800b540b  mov     [rbp+57h+var_9C], eax
0x1800b540e  mov     [rbp+57h+var_98], rcx
0x1800b5412  mov     [rbp+57h+var_90], ecx
0x1800b5415  mov     [rbp+57h+var_8C], eax
0x1800b5418  mov     [rbp+57h+var_88], rcx
0x1800b541c  mov     [rbp+57h+var_80], ecx
0x1800b541f  mov     [rbp+57h+var_7C], eax
0x1800b5422  mov     [rbp+57h+var_78], cx
0x1800b5426  lea     rax, ??_7PathBuilderGeometrySink@GEL@@6B@; const GEL::PathBuilderGeometrySink::`vftable'
0x1800b542d  mov     [rbp+57h+var_68], rax
0x1800b5431  lea     rax, [rbp+57h+var_B0]
0x1800b5435  mov     qword ptr [rbp+57h+var_60], rax
0x1800b5439  mov     dword ptr [rbp+57h+var_60+8], 1
0x1800b5440  mov     ebx, [r13+60h]
0x1800b5444  mov     edi, [r13+8]
0x1800b5448  mov     rsi, [r13+40h]
0x1800b544c  mov     r14, [r13+28h]
0x1800b5450  mov     r15, [r13+10h]
0x1800b5454  movss   xmm6, dword ptr [r13+68h]
0x1800b545a  lea     rcx, [r13+58h]
0x1800b545e  call    ??C?$TCntPtr@UIWICImagingFactory@@@Mso@@QEBAPEAUIWICImagingFactory@@XZ; Mso::TCntPtr<IWICImagingFactory>::operator->(void)
0x1800b5463  mov     rdx, rax
0x1800b5466  mov     rcx, [rax]
0x1800b5469  mov     rax, [rcx+18h]
0x1800b546d  mov     rcx, rdx
0x1800b5470  call    cs:__guard_dispatch_icall_fptr
0x1800b5476  bt      ebx, 2
0x1800b547a  setb    cl
0x1800b547d  mov     [rsp+100h+var_C0], 0
0x1800b5482  mov     [rsp+100h+var_C8], cl
0x1800b5486  mov     dword ptr [rsp+100h+var_D0], edi
0x1800b548a  mov     qword ptr [rsp+100h+var_D8], rsi
0x1800b548f  mov     [rsp+100h+var_E0], r14
0x1800b5494  mov     r9, r15
0x1800b5497  movaps  xmm2, xmm6
0x1800b549a  mov     rdx, rax
0x1800b549d  lea     rcx, [rbp+57h+var_68]
0x1800b54a1  call    cs:__imp_?GetGlyphRunOutline@ARC@@YAJAEAUIGeometrySink@1@AEBUIDWriteFontFace@@MPEBGPEBMPEBUDWRITE_GLYPH_OFFSET@@I_N5@Z; ARC::GetGlyphRunOutline(ARC::IGeometrySink &,IDWriteFontFace const &,float,ushort const *,float const *,DWRITE_GLYPH_OFFSET const *,uint,bool,bool)
0x1800b54a7  mov     r8d, 1
0x1800b54ad  lea     rdx, [rbp+57h+arg_0]
0x1800b54b1  lea     rcx, [rbp+57h+var_B0]
0x1800b54b5  call    ?Finish@PathBuilder@GEL@@QEAA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@W4FillMode@Path@Graphics@Mso@@@Z; GEL::PathBuilder::Finish(Mso::Graphics::Path::FillMode)
0x1800b54ba  mov     rbx, [rbp+57h+arg_0]
0x1800b54be  mov     rax, [rbx]
0x1800b54c1  movss   xmm0, cs:__real@3f800000
0x1800b54c9  divss   xmm0, dword ptr [r13+70h]
0x1800b54cf  cvtps2pd xmm1, xmm0
0x1800b54d2  movsd   [rbp+57h+var_68], xmm1
0x1800b54d7  xorps   xmm0, xmm0
0x1800b54da  movups  [rbp+57h+var_60], xmm0
0x1800b54de  movsd   [rbp+57h+var_50], xmm1
0x1800b54e3  xorps   xmm1, xmm1
0x1800b54e6  movups  [rbp+57h+var_48], xmm1
0x1800b54ea  lea     r8, [rbp+57h+var_68]
0x1800b54ee  mov     rdx, r12
0x1800b54f1  mov     rcx, rbx
0x1800b54f4  mov     rax, [rax+80h]
0x1800b54fb  nop     dword ptr [rax+rax+00h]
0x1800b5500  call    cs:__guard_dispatch_icall_fptr
0x1800b5506  test    rbx, rbx
0x1800b5509  jz      short loc_1800B551C
0x1800b550b  mov     rax, [rbx]
0x1800b550e  mov     rcx, rbx
0x1800b5511  mov     rax, [rax+8]
0x1800b5515  call    cs:__guard_dispatch_icall_fptr
0x1800b551b  nop
0x1800b551c  lea     rcx, [rbp+57h+var_88]
0x1800b5520  call    ??1?$TArray@V?$TCntPtr@$$CBUIEffect@GEL@@@Ofc@@@Ofc@@QEAA@XZ; Ofc::TArray<Ofc::TCntPtr<GEL::IEffect const>>::~TArray<Ofc::TCntPtr<GEL::IEffect const>>(void)
0x1800b5525  mov     rcx, [rbp+57h+var_98]
0x1800b5529  test    rcx, rcx
0x1800b552c  jz      short loc_1800B5534
0x1800b552e  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x1800b5534  mov     rcx, qword ptr [rbp+57h+var_B0+8]
0x1800b5538  test    rcx, rcx
0x1800b553b  jz      short loc_1800B5543
0x1800b553d  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x1800b5543  mov     rcx, qword ptr [rbp+57h+var_B0]
0x1800b5547  test    rcx, rcx
0x1800b554a  jz      short loc_1800B5559
0x1800b554c  mov     rax, [rcx]
0x1800b554f  mov     rax, [rax+8]
0x1800b5553  call    cs:__guard_dispatch_icall_fptr
0x1800b5559  mov     rax, r12
0x1800b555c  lea     r11, [rsp+100h+var_20]
0x1800b5564  mov     rbx, [r11+38h]
0x1800b5568  mov     rsi, [r11+40h]
0x1800b556c  mov     rdi, [r11+48h]
0x1800b5570  movaps  xmm6, xmmword ptr [r11-10h]
0x1800b5575  mov     rsp, r11
0x1800b5578  pop     r15
0x1800b557a  pop     r14
0x1800b557c  pop     r13
0x1800b557e  pop     r12
0x1800b5580  pop     rbp
0x1800b5581  retn
0x1800b5582  mov     rcx, r13
0x1800b5585  call    ?GetNormalizedPath@GlyphSinkForKashidas@GEL@@QEAA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@XZ; GEL::GlyphSinkForKashidas::GetNormalizedPath(void)
0x1800b558a  jmp     short loc_1800B5559
0x1800b558c  mov     [rdx], rcx
0x1800b558f  jmp     short loc_1800B5559
```
