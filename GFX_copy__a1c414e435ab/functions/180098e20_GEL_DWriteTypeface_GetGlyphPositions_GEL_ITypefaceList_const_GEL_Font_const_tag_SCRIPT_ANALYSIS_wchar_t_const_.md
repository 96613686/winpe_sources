# GEL::DWriteTypeface::GetGlyphPositions(GEL::ITypefaceList const &,GEL::Font const &,tag_SCRIPT_ANALYSIS &,wchar_t const *,uint,ushort const *,ushort const *,ushort const *,uint,ulong const *,float *,uint,DWRITE_GLYPH_OFFSET *,uint)

- ea: `0x180098e20`
- end: `0x1800992bd`
- name: `?GetGlyphPositions@DWriteTypeface@GEL@@UEBAXAEBUITypefaceList@2@AEBUFont@2@AEAUtag_SCRIPT_ANALYSIS@@PEB_WIPEBG44IPEBKPEAMIPEAUDWRITE_GLYPH_OFFSET@@I@Z`
- size: `1181`
- prototype: `void __fastcall(GEL::DWriteTypeface *__hidden this, const struct GEL::ITypefaceList *, const struct GEL::Font *, struct tag_SCRIPT_ANALYSIS *, const wchar_t *, unsigned int, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, const unsigned int *, float *, unsigned int, struct DWRITE_GLYPH_OFFSET *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180098bc0`

## callees

- `0x18001ffb4`
- `0x18003c0d0`
- `0x1800573f0`
- `0x180098e20`
- `0x18009a02c`
- `0x18009aa90`
- `0x1800d33a4`

## import_xrefs

- `mso40uiWin32Client!__imp_?GetInstance@ResourceManager@DWriteAssistant@Mso@@SAAEAV123@XZ` at `0x180098e86`
- `mso40uiWin32Client!__imp_?GetInstance@ResourceManager@DWriteAssistant@Mso@@SAAEAV123@XZ` at `0x180098e86`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1800990e2`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1800990e2`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180098ee9`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180098f37`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180099136`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180099180`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180098ee9`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180098f37`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180099136`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180099180`

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
        BOOL a10,
        const unsigned int *a11,
        float *a12,
        unsigned int a13,
        struct DWRITE_GLYPH_OFFSET *a14)
{
  float j; // xmm6_4
  const struct GEL::Font *v16; // r15
  const unsigned int *v18; // rsi
  int *v19; // rdi
  bool v20; // bl
  _BOOL8 v21; // r14
  unsigned int i; // ecx
  __int64 v23; // rdx
  __int16 v24; // r8
  __int64 (**v25)[2]; // rax
  unsigned int v26; // r12d
  __int64 v27; // rcx
  __int64 v28; // rax
  float *v29; // rbx
  float *v30; // rsi
  int v31; // r12d
  __int64 v32; // rcx
  bool v33; // al
  int v34; // ecx
  float v35; // xmm2_4
  float v36; // xmm2_4
  __int64 v37; // rax
  __int64 v38; // rax
  char v39; // al
  __int64 v40; // rcx
  __int64 (__fastcall *v41)(__int64 *, const wchar_t *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, const unsigned __int16 *, void *, _BOOL8, __int64, int, bool, bool, __int64 *, _QWORD, __int64 (***)[2], unsigned int *, int, float *, struct DWRITE_GLYPH_OFFSET *); // rsi
  int v42; // xmm6_4
  __int64 v43; // rdi
  __int64 v44; // rax
  __int64 v45; // [rsp+C8h] [rbp-80h] BYREF
  __int64 v46; // [rsp+D0h] [rbp-78h] BYREF
  __int64 *v47; // [rsp+D8h] [rbp-70h]
  __int64 (**v48)[2]; // [rsp+E0h] [rbp-68h] BYREF
  __int64 (__fastcall *v49)(__int64 *, const wchar_t *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, const unsigned __int16 *, void *, _BOOL8, __int64, _DWORD, _DWORD, _QWORD, int, int, BOOL, __int64 *, _QWORD, __int64 (***)[2], unsigned int *, int, float *, struct DWRITE_GLYPH_OFFSET *); // [rsp+E8h] [rbp-60h]
  void *v50; // [rsp+F0h] [rbp-58h] BYREF
  unsigned int v51; // [rsp+F8h] [rbp-50h]
  unsigned int v52; // [rsp+168h] [rbp+20h] BYREF
  int v53; // [rsp+170h] [rbp+28h] BYREF
  int v54; // [rsp+174h] [rbp+2Ch]

  v16 = a3;
  v18 = a11;
  v45 = 0;
  v45 = *(_WORD *)a4 & 0x3FF;
  GEL::CreateDWAFontFromGelFont(&v46, a2, a3, 0);
  v47 = *(__int64 **)(Mso::DWriteAssistant::ResourceManager::GetInstance() + 72);
  v19 = (int *)(*((_DWORD *)v16 + 5) & 4);
  v20 = (*(_WORD *)a4 & 0x400) != 0;
  v21 = a10;
  Ofc::CArrayImpl::CArrayImpl(
    (Ofc::CArrayImpl *)&v50,
    2u,
    a10,
    a10,
    1,
    Ofc::TDefaultConstructRange<tag_SCRIPT_VISATTR,1,1>::Do);
  for ( i = 0; i < (unsigned int)v21; ++i )
  {
    v23 = i;
    v24 = v18[i];
    if ( i >= v51 )
      CrashWithRecovery(0x1E892496u, 0);
    *((_WORD *)v50 + v23) = v24;
  }
  v25 = &off_1804C0DF8;
  if ( (*((_BYTE *)v16 + 20) & 0x40) == 0 )
    v25 = &off_1804C0E18;
  v48 = v25;
  v26 = a6;
  v52 = a6;
  if ( v46 )
  {
    v38 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v46 + 24LL))(v46);
    v39 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v38 + 48LL))(v38);
    v40 = *v47;
    if ( (v39 & 1) == 0 )
    {
      v41 = *(__int64 (__fastcall **)(__int64 *, const wchar_t *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, const unsigned __int16 *, void *, _BOOL8, __int64, int, bool, bool, __int64 *, _QWORD, __int64 (***)[2], unsigned int *, int, float *, struct DWRITE_GLYPH_OFFSET *))(v40 + 64);
      v42 = *((_DWORD *)v16 + 4);
      v16 = 0;
      if ( v46 )
      {
        v44 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v46 + 24LL))(v46);
        v31 = v41(v47, a5, a7, a8, v26, a9, v50, v21, v44, v42, (_DWORD)v19 != 0, v20, &v45, 0, &v48, &v52, 1, a12, a14);
        goto LABEL_10;
      }
      CrashWithRecovery(0x1E3C3840u, 0);
    }
    v49 = *(__int64 (__fastcall **)(__int64 *, const wchar_t *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, const unsigned __int16 *, void *, _BOOL8, __int64, _DWORD, _DWORD, _QWORD, int, int, BOOL, __int64 *, _QWORD, __int64 (***)[2], unsigned int *, int, float *, struct DWRITE_GLYPH_OFFSET *))(v40 + 72);
    a10 = v20;
    v53 = (_DWORD)v19 != 0;
    v19 = (int *)((char *)this + 72);
    if ( (*((_BYTE *)v16 + 20) & 8) == 0 || *v19 <= 0 )
      goto LABEL_31;
    for ( j = (float)*v19; ; j = *((float *)v16 + 4) )
    {
      v27 = v46;
      if ( v46 )
        break;
      CrashWithRecovery(0x1E3C3840u, 0);
LABEL_31:
      ;
    }
  }
  else
  {
    CrashWithRecovery(0x1E3C3840u, 0);
  }
  v28 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v27 + 24LL))(v27);
  v29 = (float *)a14;
  v30 = a12;
  v31 = v49(
          v47,
          a5,
          a7,
          a8,
          v26,
          a9,
          v50,
          v21,
          v28,
          LODWORD(j),
          LODWORD(FLOAT_1_0),
          0,
          1,
          v53,
          a10,
          &v45,
          0,
          &v48,
          &v52,
          1,
          a12,
          a14);
  if ( (*((_BYTE *)v16 + 20) & 8) != 0 && *v19 > 0 )
  {
    if ( byte_18051FEF0 < 0 )
    {
      v33 = Mso::AB::Optimized::ChangeGate::Evaluate((Mso::AB::Optimized::ChangeGate *)&byte_18051FEF0);
    }
    else
    {
      v33 = byte_18051FEF0 != 0;
      v19 = (int *)((char *)this + 72);
    }
    v34 = *v19;
    v35 = *((float *)v16 + 4);
    if ( v33 )
    {
      v36 = v35 / (float)v34;
      if ( v21 )
      {
        v37 = v21;
        do
        {
          *v30 = v36 * *v30;
          *v29 = v36 * *v29;
          v29[1] = v36 * v29[1];
          ++v30;
          v29 += 2;
          --v37;
        }
        while ( v37 );
      }
    }
    else
    {
      v53 = (int)v35;
      v54 = v34;
      if ( v21 )
      {
        v43 = v21;
        do
        {
          *v30 = (float)(int)Ofc::CRatio::operator*(&v53, (unsigned int)(int)*v30);
          *v29 = (float)(int)Ofc::CRatio::operator*(&v53, (unsigned int)(int)*v29);
          v29[1] = (float)(int)Ofc::CRatio::operator*(&v53, (unsigned int)(int)v29[1]);
          ++v30;
          v29 += 2;
          --v43;
        }
        while ( v43 );
      }
    }
  }
LABEL_10:
  if ( v31 < 0 )
  {
    Ofc::CHResultException::ThrowTag(v31, 0x359681u);
    __debugbreak();
  }
  operator delete(v50);
  v32 = v46;
  if ( v46 )
  {
    v46 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 8LL))(v32);
  }
}

```

## disassembly

```asm
0x180098e20  mov     rax, rsp
0x180098e23  mov     [rax+8], rbx
0x180098e27  push    rbp
0x180098e28  push    rsi
0x180098e29  push    rdi
0x180098e2a  push    r12
0x180098e2c  push    r13
0x180098e2e  push    r14
0x180098e30  push    r15
0x180098e32  lea     rbp, [rax-8]
0x180098e36  sub     rsp, 110h
0x180098e3d  movaps  xmmword ptr [rax-48h], xmm6
0x180098e41  mov     rbx, r9
0x180098e44  mov     r15, r8
0x180098e47  mov     r13, rcx
0x180098e4a  mov     rsi, [rbp+arg_50]
0x180098e4e  xor     r12d, r12d
0x180098e51  mov     [rbp+var_80], r12
0x180098e55  movzx   r10d, word ptr [r9]
0x180098e59  mov     eax, dword ptr [rbp+var_80+4]
0x180098e5c  lea     r14d, [r12+1]
0x180098e61  test    r10w, r10w
0x180098e65  cmovs   eax, r14d
0x180098e69  mov     dword ptr [rbp+var_80+4], eax
0x180098e6c  mov     eax, 3FFh
0x180098e71  and     r10w, ax
0x180098e75  mov     word ptr [rbp+var_80], r10w
0x180098e7a  xor     r9d, r9d
0x180098e7d  lea     rcx, [rbp+var_78]
0x180098e81  call    ?CreateDWAFontFromGelFont@GEL@@YA?AV?$TCntPtr@UIFont@DWriteAssistant@Mso@@@Mso@@AEBUITypefaceList@1@AEBUFont@1@PEAUtagLOGFONTW@@@Z; GEL::CreateDWAFontFromGelFont(GEL::ITypefaceList const &,GEL::Font const &,tagLOGFONTW *)
0x180098e86  call    cs:__imp_?GetInstance@ResourceManager@DWriteAssistant@Mso@@SAAEAV123@XZ; Mso::DWriteAssistant::ResourceManager::GetInstance(void)
0x180098e8c  mov     rax, [rax+48h]
0x180098e90  mov     [rbp+var_70], rax
0x180098e94  mov     edi, [r15+14h]
0x180098e98  and     edi, 4
0x180098e9b  movzx   ebx, word ptr [rbx]
0x180098e9e  shr     bx, 0Ah
0x180098ea2  and     bl, r14b
0x180098ea5  lea     rax, ?Do@?$TDefaultConstructRange@Utag_SCRIPT_VISATTR@@$00$00@Ofc@@SAXPEAEK@Z; Ofc::TDefaultConstructRange<tag_SCRIPT_VISATTR,1,1>::Do(uchar *,ulong)
0x180098eac  mov     [rsp+140h+var_118], rax; void (*)(unsigned __int8 *, unsigned int)
0x180098eb1  mov     [rsp+140h+var_120], r14b; bool
0x180098eb6  mov     r14d, [rbp+arg_48]
0x180098eba  mov     r9d, r14d; unsigned int
0x180098ebd  mov     r8d, r14d; unsigned int
0x180098ec0  lea     edx, [r12+2]; unsigned int
0x180098ec5  lea     rcx, [rbp+var_58]; this
0x180098ec9  call    ??0CArrayImpl@Ofc@@IEAA@KKK_NP6AXPEAEK@Z@Z; Ofc::CArrayImpl::CArrayImpl(ulong,ulong,ulong,bool,void (*)(uchar *,ulong))
0x180098ece  mov     ecx, r12d
0x180098ed1  test    r14d, r14d
0x180098ed4  jz      short loc_180098F00
0x180098ed6  mov     edx, ecx
0x180098ed8  movzx   r8d, word ptr [rsi+rdx*4]
0x180098edd  cmp     ecx, [rbp+var_50]
0x180098ee0  jb      short loc_180098EF0
0x180098ee2  xor     edx, edx
0x180098ee4  mov     ecx, 1E892496h
0x180098ee9  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x180098eef  nop
0x180098ef0  mov     rax, [rbp+var_58]
0x180098ef4  mov     [rax+rdx*2], r8w
0x180098ef9  inc     ecx
0x180098efb  cmp     ecx, r14d
0x180098efe  jb      short loc_180098ED6
0x180098f00  test    byte ptr [r15+14h], 40h
0x180098f05  lea     rcx, off_1804C0E18
0x180098f0c  lea     rax, off_1804C0DF8
0x180098f13  cmovz   rax, rcx
0x180098f17  mov     [rbp+var_68], rax
0x180098f1b  mov     r12d, [rbp+arg_28]
0x180098f1f  mov     [rbp+arg_10], r12d
0x180098f23  mov     rcx, [rbp+var_78]
0x180098f27  test    rcx, rcx
0x180098f2a  jnz     loc_1800990EA
0x180098f30  xor     edx, edx
0x180098f32  mov     ecx, 1E3C3840h
0x180098f37  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x180098f3d  nop
0x180098f3e  xchg    ax, ax
0x180098f40  mov     rax, [rcx]
0x180098f43  mov     rax, [rax+18h]
0x180098f47  call    cs:__guard_dispatch_icall_fptr
0x180098f4d  mov     rdx, [rbp+var_58]
0x180098f51  mov     rbx, [rbp+arg_68]
0x180098f55  mov     [rsp+140h+var_98], rbx
0x180098f5d  mov     rsi, [rbp+arg_58]
0x180098f61  mov     [rsp+140h+var_A0], rsi
0x180098f69  mov     dword ptr [rsp+140h+var_A8], 1
0x180098f74  lea     rcx, [rbp+arg_10]
0x180098f78  mov     qword ptr [rsp+140h+var_B0], rcx
0x180098f80  lea     rcx, [rbp+var_68]
0x180098f84  mov     [rsp+140h+var_B8], rcx
0x180098f8c  mov     [rsp+140h+var_C0], 0
0x180098f98  lea     rcx, [rbp+var_80]
0x180098f9c  mov     [rsp+140h+var_C8], rcx
0x180098fa1  mov     ecx, [rbp+arg_48]
0x180098fa4  mov     dword ptr [rsp+140h+var_D0], ecx
0x180098fa8  mov     ecx, [rbp+arg_18]
0x180098fab  mov     dword ptr [rsp+140h+var_D8], ecx
0x180098faf  mov     dword ptr [rsp+140h+var_E0], 1
0x180098fb7  mov     [rsp+140h+var_E8], 0
0x180098fc0  movss   xmm0, cs:__real@3f800000
0x180098fc8  movss   dword ptr [rsp+140h+var_F0], xmm0
0x180098fce  movss   [rsp+140h+var_F8], xmm6
0x180098fd4  mov     qword ptr [rsp+140h+var_100], rax
0x180098fd9  mov     dword ptr [rsp+140h+var_108], r14d
0x180098fde  mov     qword ptr [rsp+140h+var_110], rdx
0x180098fe3  mov     rdx, [rbp+arg_40]
0x180098fe7  mov     [rsp+140h+var_118], rdx
0x180098fec  mov     dword ptr [rsp+140h+var_120], r12d
0x180098ff1  mov     r9, [rbp+arg_38]
0x180098ff5  mov     r8, [rbp+arg_30]
0x180098ff9  mov     rdx, [rbp+arg_20]
0x180098ffd  mov     rcx, [rbp+var_70]
0x180099001  mov     rax, [rbp+var_60]
0x180099005  call    cs:__guard_dispatch_icall_fptr
0x18009900b  mov     r12d, eax
0x18009900e  test    byte ptr [r15+14h], 8
0x180099013  jnz     short loc_180099064
0x180099015  xor     r15d, r15d
0x180099018  test    r12d, r12d
0x18009901b  js      loc_1800992AF
0x180099021  mov     rcx, [rbp+var_58]; void *
0x180099025  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18009902a  mov     rcx, [rbp+var_78]
0x18009902e  test    rcx, rcx
0x180099031  jz      short loc_180099044
0x180099033  mov     [rbp+var_78], r15
0x180099037  mov     rax, [rcx]
0x18009903a  mov     rax, [rax+8]
0x18009903e  call    cs:__guard_dispatch_icall_fptr
0x180099044  lea     r11, [rsp+140h+var_30]
0x18009904c  mov     rbx, [r11+40h]
0x180099050  movaps  xmm6, xmmword ptr [r11-10h]
0x180099055  mov     rsp, r11
0x180099058  pop     r15
0x18009905a  pop     r14
0x18009905c  pop     r13
0x18009905e  pop     r12
0x180099060  pop     rdi
0x180099061  pop     rsi
0x180099062  pop     rbp
0x180099063  retn
0x180099064  cmp     dword ptr [rdi], 0
0x180099067  jle     short loc_180099015
0x180099069  mov     cl, cs:byte_18051FEF0
0x18009906f  test    cl, cl
0x180099071  js      short loc_1800990DB
0x180099073  setnz   al
0x180099076  lea     rdi, [r13+48h]
0x18009907a  mov     ecx, [rdi]
0x18009907c  movss   xmm2, dword ptr [r15+10h]
0x180099082  xor     r15d, r15d
0x180099085  test    al, al
0x180099087  jz      loc_18009918F
0x18009908d  movd    xmm0, ecx
0x180099091  cvtdq2ps xmm0, xmm0
0x180099094  divss   xmm2, xmm0
0x180099098  test    r14d, r14d
0x18009909b  jz      loc_180099018
0x1800990a1  mov     rax, r14
0x1800990a4  movaps  xmm0, xmm2
0x1800990a7  mulss   xmm0, dword ptr [rsi]
0x1800990ab  movss   dword ptr [rsi], xmm0
0x1800990af  movaps  xmm1, xmm2
0x1800990b2  mulss   xmm1, dword ptr [rbx]
0x1800990b6  movss   dword ptr [rbx], xmm1
0x1800990ba  movaps  xmm0, xmm2
0x1800990bd  mulss   xmm0, dword ptr [rbx+4]
0x1800990c2  movss   dword ptr [rbx+4], xmm0
0x1800990c7  lea     rsi, [rsi+4]
0x1800990cb  lea     rbx, [rbx+8]
0x1800990cf  sub     rax, 1
0x1800990d3  jz      loc_180099018
0x1800990d9  jmp     short loc_1800990A4
0x1800990db  lea     rcx, byte_18051FEF0
0x1800990e2  call    cs:__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ; Mso::AB::Optimized::ChangeGate::Evaluate(void)
0x1800990e8  jmp     short loc_18009907A
0x1800990ea  mov     rax, [rcx]
0x1800990ed  mov     rax, [rax+18h]
0x1800990f1  call    cs:__guard_dispatch_icall_fptr
0x1800990f7  mov     rdx, rax
0x1800990fa  mov     rcx, [rax]
0x1800990fd  mov     rax, [rcx+30h]
0x180099101  mov     rcx, rdx
0x180099104  call    cs:__guard_dispatch_icall_fptr
0x18009910a  mov     rcx, [rbp+var_70]
0x18009910e  mov     rcx, [rcx]
0x180099111  test    al, 1
0x180099113  jnz     short loc_18009913D
0x180099115  mov     rsi, [rcx+40h]
0x180099119  movss   xmm6, dword ptr [r15+10h]
0x18009911f  mov     rcx, [rbp+var_78]
0x180099123  xor     r15d, r15d
0x180099126  test    rcx, rcx
0x180099129  jnz     loc_180099202
0x18009912f  xor     edx, edx
0x180099131  mov     ecx, 1E3C3840h
0x180099136  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x18009913c  nop
0x18009913d  mov     rax, [rcx+48h]
0x180099141  mov     [rbp+var_60], rax
0x180099145  movzx   eax, bl
0x180099148  mov     [rbp+arg_48], eax
0x18009914b  xor     eax, eax
0x18009914d  test    edi, edi
0x18009914f  setnz   al
0x180099152  mov     [rbp+arg_18], eax
0x180099155  lea     rdi, [r13+48h]
0x180099159  test    byte ptr [r15+14h], 8
0x18009915e  jz      short loc_180099187
0x180099160  cmp     dword ptr [rdi], 0
0x180099163  jle     short loc_180099187
0x180099165  movd    xmm6, dword ptr [rdi]
0x180099169  cvtdq2ps xmm6, xmm6
0x18009916c  mov     rcx, [rbp+var_78]
0x180099170  test    rcx, rcx
0x180099173  jnz     loc_180098F40
0x180099179  xor     edx, edx
0x18009917b  mov     ecx, 1E3C3840h
0x180099180  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x180099186  nop
0x180099187  movss   xmm6, dword ptr [r15+10h]
0x18009918d  jmp     short loc_18009916C
0x18009918f  cvttss2si eax, xmm2
0x180099193  mov     [rbp+arg_18], eax
0x180099196  mov     [rbp+arg_1C], ecx
0x180099199  test    r14d, r14d
0x18009919c  jz      loc_180099018
0x1800991a2  mov     rdi, r14
0x1800991a5  cvttss2si edx, dword ptr [rsi]
0x1800991a9  lea     rcx, [rbp+arg_18]
0x1800991ad  call    ??DCRatio@Ofc@@QEBAJJ@Z; Ofc::CRatio::operator*(long)
0x1800991b2  movd    xmm0, eax
0x1800991b6  cvtdq2ps xmm0, xmm0
0x1800991b9  movss   dword ptr [rsi], xmm0
0x1800991bd  cvttss2si edx, dword ptr [rbx]
0x1800991c1  lea     rcx, [rbp+arg_18]
0x1800991c5  call    ??DCRatio@Ofc@@QEBAJJ@Z; Ofc::CRatio::operator*(long)
0x1800991ca  movd    xmm0, eax
0x1800991ce  cvtdq2ps xmm0, xmm0
0x1800991d1  movss   dword ptr [rbx], xmm0
0x1800991d5  cvttss2si edx, dword ptr [rbx+4]
0x1800991da  lea     rcx, [rbp+arg_18]
0x1800991de  call    ??DCRatio@Ofc@@QEBAJJ@Z; Ofc::CRatio::operator*(long)
0x1800991e3  movd    xmm0, eax
0x1800991e7  cvtdq2ps xmm0, xmm0
0x1800991ea  movss   dword ptr [rbx+4], xmm0
0x1800991ef  lea     rsi, [rsi+4]
0x1800991f3  lea     rbx, [rbx+8]
0x1800991f7  sub     rdi, 1
0x1800991fb  jnz     short loc_1800991A5
0x1800991fd  jmp     loc_180099018
0x180099202  mov     rax, [rcx]
0x180099205  mov     rax, [rax+18h]
0x180099209  call    cs:__guard_dispatch_icall_fptr
0x18009920f  mov     r9, [rbp+var_58]
0x180099213  movzx   edx, bl
0x180099216  mov     r8d, r15d
0x180099219  test    edi, edi
0x18009921b  setnz   r8b
0x18009921f  mov     rcx, [rbp+arg_68]
0x180099223  mov     qword ptr [rsp+140h+var_B0], rcx
0x18009922b  mov     rcx, [rbp+arg_58]
0x18009922f  mov     [rsp+140h+var_B8], rcx
0x180099237  mov     dword ptr [rsp+140h+var_C0], 1
0x180099242  lea     rcx, [rbp+arg_10]
0x180099246  mov     [rsp+140h+var_C8], rcx
0x18009924b  lea     rcx, [rbp+var_68]
0x18009924f  mov     [rsp+140h+var_D0], rcx
0x180099254  mov     [rsp+140h+var_D8], r15
0x180099259  lea     rcx, [rbp+var_80]
0x18009925d  mov     [rsp+140h+var_E0], rcx
0x180099262  mov     dword ptr [rsp+140h+var_E8], edx
0x180099266  mov     dword ptr [rsp+140h+var_F0], r8d
0x18009926b  movss   [rsp+140h+var_F8], xmm6
0x180099271  mov     qword ptr [rsp+140h+var_100], rax
0x180099276  mov     dword ptr [rsp+140h+var_108], r14d
0x18009927b  mov     qword ptr [rsp+140h+var_110], r9
0x180099280  mov     rcx, [rbp+arg_40]
0x180099284  mov     [rsp+140h+var_118], rcx
0x180099289  mov     dword ptr [rsp+140h+var_120], r12d
0x18009928e  mov     r9, [rbp+arg_38]
0x180099292  mov     r8, [rbp+arg_30]
0x180099296  mov     rdx, [rbp+arg_20]
0x18009929a  mov     rcx, [rbp+var_70]
0x18009929e  mov     rax, rsi
0x1800992a1  call    cs:__guard_dispatch_icall_fptr
0x1800992a7  mov     r12d, eax
0x1800992aa  jmp     loc_180099018
0x1800992af  mov     edx, 359681h; unsigned int
0x1800992b4  mov     ecx, r12d; int
0x1800992b7  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x1800992bc  int     3; Trap to Debugger
```
