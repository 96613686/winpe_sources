# GEL::DWriteTypeface::GetGlyphPositions(GEL::ITypefaceList const &,GEL::Font const &,tag_SCRIPT_ANALYSIS &,wchar_t const *,uint,ushort const *,ushort const *,ushort const *,uint,ulong const *,float *,uint,DWRITE_GLYPH_OFFSET *,uint)

- ea: `0x1800af630`
- end: `0x1800afabd`
- name: `?GetGlyphPositions@DWriteTypeface@GEL@@UEBAXAEBUITypefaceList@2@AEBUFont@2@AEAUtag_SCRIPT_ANALYSIS@@PEB_WIPEBG44IPEBKPEAMIPEAUDWRITE_GLYPH_OFFSET@@I@Z`
- size: `1165`
- prototype: `void __fastcall(GEL::DWriteTypeface *__hidden this, const struct GEL::ITypefaceList *, const struct GEL::Font *, struct tag_SCRIPT_ANALYSIS *, const wchar_t *, unsigned int, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, const unsigned int *, float *, unsigned int, struct DWRITE_GLYPH_OFFSET *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x1800af3d0`

## callees

- `0x180020198`
- `0x180057e70`
- `0x1800aec60`
- `0x1800aecb0`
- `0x1800af630`
- `0x1800afac0`
- `0x1800dcec0`

## import_xrefs

- `mso40uiWin32Client!__imp_?GetInstance@ResourceManager@DWriteAssistant@Mso@@SAAEAV123@XZ` at `0x1800af696`
- `mso40uiWin32Client!__imp_?GetInstance@ResourceManager@DWriteAssistant@Mso@@SAAEAV123@XZ` at `0x1800af696`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1800afa34`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1800afa34`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800af6e0`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800af86b`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800af879`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800af9a8`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800af6e0`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800af86b`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800af879`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800af9a8`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall GEL::DWriteTypeface::GetGlyphPositions(
        GEL::DWriteTypeface *this,
        const struct GEL::ITypefaceList *a2,
        const struct GEL::Font *a3,
        struct tag_SCRIPT_ANALYSIS *a4,
        const wchar_t *a5,
        unsigned int a6,
        const unsigned __int16 *a7,
        const unsigned __int16 *a8,
        const unsigned __int16 *a9,
        unsigned int a10,
        float *a11,
        float *a12,
        unsigned int a13,
        struct DWRITE_GLYPH_OFFSET *a14)
{
  const struct GEL::Font *v15; // r15
  float *v17; // rsi
  int v18; // edi
  unsigned __int64 v19; // rbx
  __int64 v20; // r14
  unsigned int i; // ecx
  __int64 v22; // rdx
  __int16 v23; // r8
  __int64 (**v24)[2]; // rax
  int v25; // r12d
  __int64 v26; // rax
  char v27; // al
  __int64 v28; // rcx
  int v29; // xmm6_4
  __int64 v30; // rax
  __int64 v31; // rcx
  int *v32; // rdi
  float v33; // xmm6_4
  __int64 v34; // rax
  bool v35; // al
  int v36; // ecx
  float v37; // xmm2_4
  float v38; // xmm2_4
  __int64 v39; // rax
  __int64 v40; // rdi
  __int64 v41; // [rsp+C8h] [rbp-80h] BYREF
  __int64 v42; // [rsp+D0h] [rbp-78h] BYREF
  __int64 *v43; // [rsp+D8h] [rbp-70h]
  __int64 (**v44)[2]; // [rsp+E0h] [rbp-68h] BYREF
  __int64 (__fastcall *v45)(__int64 *, const wchar_t *, const unsigned __int16 *, const unsigned __int16 *, int, const unsigned __int16 *, void *, _DWORD, __int64, _DWORD, _DWORD, _QWORD, int, int, unsigned int, __int64 *, _QWORD, __int64 (***)[2], unsigned int *, int, float *, struct DWRITE_GLYPH_OFFSET *); // [rsp+E8h] [rbp-60h]
  void *v46; // [rsp+F0h] [rbp-58h] BYREF
  unsigned int v47; // [rsp+F8h] [rbp-50h]
  unsigned int v48; // [rsp+168h] [rbp+20h] BYREF
  int v49; // [rsp+170h] [rbp+28h] BYREF
  int v50; // [rsp+174h] [rbp+2Ch]

  v15 = a3;
  v17 = a11;
  v41 = 0;
  v41 = *(_WORD *)a4 & 0x3FF;
  GEL::CreateDWAFontFromGelFont(&v42, a2, a3, 0);
  v43 = *(__int64 **)(Mso::DWriteAssistant::ResourceManager::GetInstance() + 72);
  v18 = *((_DWORD *)v15 + 5) & 4;
  v19 = (*(_WORD *)a4 & 0x400) != 0;
  v20 = a10;
  Ofc::TArray<unsigned short>::TArray<unsigned short>(&v46, a10);
  for ( i = 0; i < (unsigned int)v20; ++i )
  {
    v22 = i;
    v23 = LOWORD(v17[i]);
    if ( i >= v47 )
      CrashWithRecovery(0x1E892496u, 0);
    *((_WORD *)v46 + v22) = v23;
  }
  v24 = &off_1804C5AB0;
  if ( (*((_BYTE *)v15 + 20) & 0x40) == 0 )
    v24 = &off_1804C5AD0;
  v44 = v24;
  v25 = a6;
  v48 = a6;
  if ( !v42 )
  {
    CrashWithRecovery(0x1E3C3840u, 0);
LABEL_16:
    CrashWithRecovery(0x1E3C3840u, 0);
    goto LABEL_17;
  }
  v26 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v42 + 24LL))(v42);
  v27 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v26 + 48LL))(v26);
  v28 = *v43;
  if ( (v27 & 1) == 0 )
  {
    v17 = *(float **)(v28 + 64);
    v29 = *((_DWORD *)v15 + 4);
    v15 = 0;
    if ( v42 )
    {
      v30 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v42 + 24LL))(v42);
      v25 = ((__int64 (__fastcall *)(__int64 *, const wchar_t *, const unsigned __int16 *, const unsigned __int16 *, int, const unsigned __int16 *, void *, _DWORD, __int64, int, bool, _DWORD, __int64 *, _QWORD, __int64 (***)[2], unsigned int *, int, float *, struct DWRITE_GLYPH_OFFSET *))v17)(
              v43,
              a5,
              a7,
              a8,
              v25,
              a9,
              v46,
              v20,
              v30,
              v29,
              v18 != 0,
              (unsigned __int8)v19,
              &v41,
              0,
              &v44,
              &v48,
              1,
              a12,
              a14);
      goto LABEL_11;
    }
    goto LABEL_16;
  }
LABEL_17:
  v45 = *(__int64 (__fastcall **)(__int64 *, const wchar_t *, const unsigned __int16 *, const unsigned __int16 *, int, const unsigned __int16 *, void *, _DWORD, __int64, _DWORD, _DWORD, _QWORD, int, int, unsigned int, __int64 *, _QWORD, __int64 (***)[2], unsigned int *, int, float *, struct DWRITE_GLYPH_OFFSET *))(v28 + 72);
  a10 = (unsigned __int8)v19;
  v49 = v18 != 0;
  v32 = (int *)((char *)this + 72);
  if ( (*((_BYTE *)v15 + 20) & 8) != 0 && *v32 > 0 )
    v33 = (float)*v32;
  else
    v33 = *((float *)v15 + 4);
  if ( v42 )
  {
    v34 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v42 + 24LL))(v42);
    v19 = (unsigned __int64)a14;
    v17 = a12;
    v25 = v45(
            v43,
            a5,
            a7,
            a8,
            v25,
            a9,
            v46,
            v20,
            v34,
            LODWORD(v33),
            LODWORD(FLOAT_1_0),
            0,
            1,
            v49,
            a10,
            &v41,
            0,
            &v44,
            &v48,
            1,
            a12,
            a14);
    if ( (*((_BYTE *)v15 + 20) & 8) == 0 )
      goto LABEL_11;
  }
  else
  {
    CrashWithRecovery(0x1E3C3840u, 0);
  }
  if ( *v32 > 0 )
  {
    if ( byte_180523F38 < 0 )
    {
      v35 = Mso::AB::Optimized::ChangeGate::Evaluate((Mso::AB::Optimized::ChangeGate *)&byte_180523F38);
    }
    else
    {
      v35 = byte_180523F38 != 0;
      v32 = (int *)((char *)this + 72);
    }
    v36 = *v32;
    v37 = *((float *)v15 + 4);
    if ( v35 )
    {
      v38 = v37 / (float)v36;
      if ( (_DWORD)v20 )
      {
        v39 = v20;
        do
        {
          *v17 = v38 * *v17;
          *(float *)v19 = v38 * *(float *)v19;
          *(float *)(v19 + 4) = v38 * *(float *)(v19 + 4);
          ++v17;
          v19 += 8LL;
          --v39;
        }
        while ( v39 );
      }
    }
    else
    {
      v49 = (int)v37;
      v50 = v36;
      if ( (_DWORD)v20 )
      {
        v40 = v20;
        do
        {
          *v17 = (float)(int)Ofc::CRatio::operator*(&v49, (unsigned int)(int)*v17);
          *(float *)v19 = (float)(int)Ofc::CRatio::operator*(&v49, (unsigned int)(int)*(float *)v19);
          *(float *)(v19 + 4) = (float)(int)Ofc::CRatio::operator*(&v49, (unsigned int)(int)*(float *)(v19 + 4));
          ++v17;
          v19 += 8LL;
          --v40;
        }
        while ( v40 );
      }
    }
  }
LABEL_11:
  if ( v25 < 0 )
  {
    Ofc::CHResultException::ThrowTag(v25, 0x359681u);
    __debugbreak();
  }
  operator delete(v46);
  v31 = v42;
  if ( v42 )
  {
    v42 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 8LL))(v31);
  }
}

```

## disassembly

```asm
0x1800af630  mov     rax, rsp
0x1800af633  mov     [rax+8], rbx
0x1800af637  push    rbp
0x1800af638  push    rsi
0x1800af639  push    rdi
0x1800af63a  push    r12
0x1800af63c  push    r13
0x1800af63e  push    r14
0x1800af640  push    r15
0x1800af642  lea     rbp, [rax-8]
0x1800af646  sub     rsp, 110h
0x1800af64d  movaps  xmmword ptr [rax-48h], xmm6
0x1800af651  mov     rbx, r9
0x1800af654  mov     r15, r8
0x1800af657  mov     r13, rcx
0x1800af65a  mov     rsi, [rbp+arg_50]
0x1800af65e  xor     r12d, r12d
0x1800af661  mov     [rbp+var_80], r12
0x1800af665  movzx   r10d, word ptr [r9]
0x1800af669  mov     eax, dword ptr [rbp+var_80+4]
0x1800af66c  lea     r14d, [r12+1]
0x1800af671  test    r10w, r10w
0x1800af675  cmovs   eax, r14d
0x1800af679  mov     dword ptr [rbp+var_80+4], eax
0x1800af67c  mov     eax, 3FFh
0x1800af681  and     r10w, ax
0x1800af685  mov     word ptr [rbp+var_80], r10w
0x1800af68a  xor     r9d, r9d
0x1800af68d  lea     rcx, [rbp+var_78]
0x1800af691  call    ?CreateDWAFontFromGelFont@GEL@@YA?AV?$TCntPtr@UIFont@DWriteAssistant@Mso@@@Mso@@AEBUITypefaceList@1@AEBUFont@1@PEAUtagLOGFONTW@@@Z; GEL::CreateDWAFontFromGelFont(GEL::ITypefaceList const &,GEL::Font const &,tagLOGFONTW *)
0x1800af696  call    cs:__imp_?GetInstance@ResourceManager@DWriteAssistant@Mso@@SAAEAV123@XZ; Mso::DWriteAssistant::ResourceManager::GetInstance(void)
0x1800af69c  mov     rax, [rax+48h]
0x1800af6a0  mov     [rbp+var_70], rax
0x1800af6a4  mov     edi, [r15+14h]
0x1800af6a8  and     edi, 4
0x1800af6ab  movzx   ebx, word ptr [rbx]
0x1800af6ae  shr     bx, 0Ah
0x1800af6b2  and     bl, r14b
0x1800af6b5  mov     r14d, [rbp+arg_48]
0x1800af6b9  mov     edx, r14d
0x1800af6bc  lea     rcx, [rbp+var_58]
0x1800af6c0  call    ??0?$TArray@G@Ofc@@QEAA@K@Z; Ofc::TArray<ushort>::TArray<ushort>(ulong)
0x1800af6c5  mov     ecx, r12d
0x1800af6c8  test    r14d, r14d
0x1800af6cb  jz      short loc_1800AF6F7
0x1800af6cd  mov     edx, ecx
0x1800af6cf  movzx   r8d, word ptr [rsi+rdx*4]
0x1800af6d4  cmp     ecx, [rbp+var_50]
0x1800af6d7  jb      short loc_1800AF6E7
0x1800af6d9  xor     edx, edx
0x1800af6db  mov     ecx, 1E892496h
0x1800af6e0  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1800af6e6  nop
0x1800af6e7  mov     rax, [rbp+var_58]
0x1800af6eb  mov     [rax+rdx*2], r8w
0x1800af6f0  inc     ecx
0x1800af6f2  cmp     ecx, r14d
0x1800af6f5  jb      short loc_1800AF6CD
0x1800af6f7  test    byte ptr [r15+14h], 40h
0x1800af6fc  lea     rcx, off_1804C5AD0
0x1800af703  lea     rax, off_1804C5AB0
0x1800af70a  cmovz   rax, rcx
0x1800af70e  mov     [rbp+var_68], rax
0x1800af712  mov     r12d, [rbp+arg_28]
0x1800af716  mov     [rbp+arg_10], r12d
0x1800af71a  mov     rcx, [rbp+var_78]
0x1800af71e  test    rcx, rcx
0x1800af721  jz      loc_1800AF864
0x1800af727  mov     rax, [rcx]
0x1800af72a  mov     rax, [rax+18h]
0x1800af72e  call    cs:__guard_dispatch_icall_fptr
0x1800af734  mov     rdx, rax
0x1800af737  mov     rcx, [rax]
0x1800af73a  mov     rax, [rcx+30h]
0x1800af73e  mov     rcx, rdx
0x1800af741  call    cs:__guard_dispatch_icall_fptr
0x1800af747  mov     rcx, [rbp+var_70]
0x1800af74b  mov     rcx, [rcx]
0x1800af74e  test    al, 1
0x1800af750  jnz     loc_1800AF880
0x1800af756  mov     rsi, [rcx+40h]
0x1800af75a  movss   xmm6, dword ptr [r15+10h]
0x1800af760  mov     rcx, [rbp+var_78]
0x1800af764  xor     r15d, r15d
0x1800af767  test    rcx, rcx
0x1800af76a  jz      loc_1800AF872
0x1800af770  mov     rax, [rcx]
0x1800af773  mov     rax, [rax+18h]
0x1800af777  call    cs:__guard_dispatch_icall_fptr
0x1800af77d  mov     r9, [rbp+var_58]
0x1800af781  movzx   edx, bl
0x1800af784  mov     r8d, r15d
0x1800af787  test    edi, edi
0x1800af789  setnz   r8b
0x1800af78d  mov     rcx, [rbp+arg_68]
0x1800af791  mov     qword ptr [rsp+140h+var_B0], rcx
0x1800af799  mov     rcx, [rbp+arg_58]
0x1800af79d  mov     [rsp+140h+var_B8], rcx
0x1800af7a5  mov     dword ptr [rsp+140h+var_C0], 1
0x1800af7b0  lea     rcx, [rbp+arg_10]
0x1800af7b4  mov     [rsp+140h+var_C8], rcx
0x1800af7b9  lea     rcx, [rbp+var_68]
0x1800af7bd  mov     [rsp+140h+var_D0], rcx
0x1800af7c2  mov     [rsp+140h+var_D8], r15
0x1800af7c7  lea     rcx, [rbp+var_80]
0x1800af7cb  mov     [rsp+140h+var_E0], rcx
0x1800af7d0  mov     dword ptr [rsp+140h+var_E8], edx
0x1800af7d4  mov     dword ptr [rsp+140h+var_F0], r8d
0x1800af7d9  movss   [rsp+140h+var_F8], xmm6
0x1800af7df  mov     qword ptr [rsp+140h+var_100], rax
0x1800af7e4  mov     dword ptr [rsp+140h+var_108], r14d
0x1800af7e9  mov     qword ptr [rsp+140h+var_110], r9
0x1800af7ee  mov     rcx, [rbp+arg_40]
0x1800af7f2  mov     [rsp+140h+var_118], rcx
0x1800af7f7  mov     dword ptr [rsp+140h+var_120], r12d
0x1800af7fc  mov     r9, [rbp+arg_38]
0x1800af800  mov     r8, [rbp+arg_30]
0x1800af804  mov     rdx, [rbp+arg_20]
0x1800af808  mov     rcx, [rbp+var_70]
0x1800af80c  mov     rax, rsi
0x1800af80f  call    cs:__guard_dispatch_icall_fptr
0x1800af815  mov     r12d, eax
0x1800af818  test    r12d, r12d
0x1800af81b  js      loc_1800AFAAF
0x1800af821  mov     rcx, [rbp+var_58]; void *
0x1800af825  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800af82a  mov     rcx, [rbp+var_78]
0x1800af82e  test    rcx, rcx
0x1800af831  jz      short loc_1800AF844
0x1800af833  mov     [rbp+var_78], r15
0x1800af837  mov     rax, [rcx]
0x1800af83a  mov     rax, [rax+8]
0x1800af83e  call    cs:__guard_dispatch_icall_fptr
0x1800af844  lea     r11, [rsp+140h+var_30]
0x1800af84c  mov     rbx, [r11+40h]
0x1800af850  movaps  xmm6, xmmword ptr [r11-10h]
0x1800af855  mov     rsp, r11
0x1800af858  pop     r15
0x1800af85a  pop     r14
0x1800af85c  pop     r13
0x1800af85e  pop     r12
0x1800af860  pop     rdi
0x1800af861  pop     rsi
0x1800af862  pop     rbp
0x1800af863  retn
0x1800af864  xor     edx, edx
0x1800af866  mov     ecx, 1E3C3840h
0x1800af86b  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1800af871  nop
0x1800af872  xor     edx, edx
0x1800af874  mov     ecx, 1E3C3840h
0x1800af879  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1800af87f  nop
0x1800af880  mov     rax, [rcx+48h]
0x1800af884  mov     [rbp+var_60], rax
0x1800af888  movzx   eax, bl
0x1800af88b  mov     [rbp+arg_48], eax
0x1800af88e  xor     eax, eax
0x1800af890  test    edi, edi
0x1800af892  setnz   al
0x1800af895  mov     [rbp+arg_18], eax
0x1800af898  lea     rdi, [r13+48h]
0x1800af89c  test    byte ptr [r15+14h], 8
0x1800af8a1  jz      loc_1800AFA22
0x1800af8a7  cmp     dword ptr [rdi], 0
0x1800af8aa  jle     loc_1800AFA22
0x1800af8b0  movd    xmm6, dword ptr [rdi]
0x1800af8b4  cvtdq2ps xmm6, xmm6
0x1800af8b7  mov     rcx, [rbp+var_78]
0x1800af8bb  test    rcx, rcx
0x1800af8be  jz      loc_1800AF9A1
0x1800af8c4  mov     rax, [rcx]
0x1800af8c7  mov     rax, [rax+18h]
0x1800af8cb  call    cs:__guard_dispatch_icall_fptr
0x1800af8d1  mov     rdx, [rbp+var_58]
0x1800af8d5  mov     rbx, [rbp+arg_68]
0x1800af8d9  mov     [rsp+140h+var_98], rbx
0x1800af8e1  mov     rsi, [rbp+arg_58]
0x1800af8e5  mov     [rsp+140h+var_A0], rsi
0x1800af8ed  mov     dword ptr [rsp+140h+var_A8], 1
0x1800af8f8  lea     rcx, [rbp+arg_10]
0x1800af8fc  mov     qword ptr [rsp+140h+var_B0], rcx
0x1800af904  lea     rcx, [rbp+var_68]
0x1800af908  mov     [rsp+140h+var_B8], rcx
0x1800af910  mov     [rsp+140h+var_C0], 0
0x1800af91c  lea     rcx, [rbp+var_80]
0x1800af920  mov     [rsp+140h+var_C8], rcx
0x1800af925  mov     ecx, [rbp+arg_48]
0x1800af928  mov     dword ptr [rsp+140h+var_D0], ecx
0x1800af92c  mov     ecx, [rbp+arg_18]
0x1800af92f  mov     dword ptr [rsp+140h+var_D8], ecx
0x1800af933  mov     dword ptr [rsp+140h+var_E0], 1
0x1800af93b  mov     [rsp+140h+var_E8], 0
0x1800af944  movss   xmm0, cs:__real@3f800000
0x1800af94c  movss   dword ptr [rsp+140h+var_F0], xmm0
0x1800af952  movss   [rsp+140h+var_F8], xmm6
0x1800af958  mov     qword ptr [rsp+140h+var_100], rax
0x1800af95d  mov     dword ptr [rsp+140h+var_108], r14d
0x1800af962  mov     qword ptr [rsp+140h+var_110], rdx
0x1800af967  mov     rdx, [rbp+arg_40]
0x1800af96b  mov     [rsp+140h+var_118], rdx
0x1800af970  mov     dword ptr [rsp+140h+var_120], r12d
0x1800af975  mov     r9, [rbp+arg_38]
0x1800af979  mov     r8, [rbp+arg_30]
0x1800af97d  mov     rdx, [rbp+arg_20]
0x1800af981  mov     rcx, [rbp+var_70]
0x1800af985  mov     rax, [rbp+var_60]
0x1800af989  call    cs:__guard_dispatch_icall_fptr
0x1800af98f  mov     r12d, eax
0x1800af992  test    byte ptr [r15+14h], 8
0x1800af997  jnz     short loc_1800AF9AF
0x1800af999  xor     r15d, r15d
0x1800af99c  jmp     loc_1800AF818
0x1800af9a1  xor     edx, edx
0x1800af9a3  mov     ecx, 1E3C3840h
0x1800af9a8  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1800af9ae  nop
0x1800af9af  cmp     dword ptr [rdi], 0
0x1800af9b2  jle     short loc_1800AF999
0x1800af9b4  mov     cl, cs:byte_180523F38
0x1800af9ba  test    cl, cl
0x1800af9bc  js      short loc_1800AFA2D
0x1800af9be  setnz   al
0x1800af9c1  lea     rdi, [r13+48h]
0x1800af9c5  mov     ecx, [rdi]
0x1800af9c7  movss   xmm2, dword ptr [r15+10h]
0x1800af9cd  xor     r15d, r15d
0x1800af9d0  test    al, al
0x1800af9d2  jz      short loc_1800AFA3C
0x1800af9d4  movd    xmm0, ecx
0x1800af9d8  cvtdq2ps xmm0, xmm0
0x1800af9db  divss   xmm2, xmm0
0x1800af9df  test    r14d, r14d
0x1800af9e2  jz      loc_1800AF818
0x1800af9e8  mov     rax, r14
0x1800af9eb  movaps  xmm0, xmm2
0x1800af9ee  mulss   xmm0, dword ptr [rsi]
0x1800af9f2  movss   dword ptr [rsi], xmm0
0x1800af9f6  movaps  xmm1, xmm2
0x1800af9f9  mulss   xmm1, dword ptr [rbx]
0x1800af9fd  movss   dword ptr [rbx], xmm1
0x1800afa01  movaps  xmm0, xmm2
0x1800afa04  mulss   xmm0, dword ptr [rbx+4]
0x1800afa09  movss   dword ptr [rbx+4], xmm0
0x1800afa0e  lea     rsi, [rsi+4]
0x1800afa12  lea     rbx, [rbx+8]
0x1800afa16  sub     rax, 1
0x1800afa1a  jz      loc_1800AF818
0x1800afa20  jmp     short loc_1800AF9EB
0x1800afa22  movss   xmm6, dword ptr [r15+10h]
0x1800afa28  jmp     loc_1800AF8B7
0x1800afa2d  lea     rcx, byte_180523F38
0x1800afa34  call    cs:__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ; Mso::AB::Optimized::ChangeGate::Evaluate(void)
0x1800afa3a  jmp     short loc_1800AF9C5
0x1800afa3c  cvttss2si eax, xmm2
0x1800afa40  mov     [rbp+arg_18], eax
0x1800afa43  mov     [rbp+arg_1C], ecx
0x1800afa46  test    r14d, r14d
0x1800afa49  jz      loc_1800AF818
0x1800afa4f  mov     rdi, r14
0x1800afa52  cvttss2si edx, dword ptr [rsi]
0x1800afa56  lea     rcx, [rbp+arg_18]
0x1800afa5a  call    ??DCRatio@Ofc@@QEBAJJ@Z; Ofc::CRatio::operator*(long)
0x1800afa5f  movd    xmm0, eax
0x1800afa63  cvtdq2ps xmm0, xmm0
0x1800afa66  movss   dword ptr [rsi], xmm0
0x1800afa6a  cvttss2si edx, dword ptr [rbx]
0x1800afa6e  lea     rcx, [rbp+arg_18]
0x1800afa72  call    ??DCRatio@Ofc@@QEBAJJ@Z; Ofc::CRatio::operator*(long)
0x1800afa77  movd    xmm0, eax
0x1800afa7b  cvtdq2ps xmm0, xmm0
0x1800afa7e  movss   dword ptr [rbx], xmm0
0x1800afa82  cvttss2si edx, dword ptr [rbx+4]
0x1800afa87  lea     rcx, [rbp+arg_18]
0x1800afa8b  call    ??DCRatio@Ofc@@QEBAJJ@Z; Ofc::CRatio::operator*(long)
0x1800afa90  movd    xmm0, eax
0x1800afa94  cvtdq2ps xmm0, xmm0
0x1800afa97  movss   dword ptr [rbx+4], xmm0
0x1800afa9c  lea     rsi, [rsi+4]
0x1800afaa0  lea     rbx, [rbx+8]
0x1800afaa4  sub     rdi, 1
0x1800afaa8  jnz     short loc_1800AFA52
0x1800afaaa  jmp     loc_1800AF818
0x1800afaaf  mov     edx, 359681h; unsigned int
0x1800afab4  mov     ecx, r12d; int
0x1800afab7  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x1800afabc  int     3; Trap to Debugger
```
