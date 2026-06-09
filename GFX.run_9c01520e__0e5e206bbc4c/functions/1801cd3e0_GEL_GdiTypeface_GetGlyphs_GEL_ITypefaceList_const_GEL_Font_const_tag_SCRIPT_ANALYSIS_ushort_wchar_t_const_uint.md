# GEL::GdiTypeface::GetGlyphs(GEL::ITypefaceList const &,GEL::Font const &,tag_SCRIPT_ANALYSIS &,ushort,wchar_t const *,uint,ushort *,uint,ushort *,uint,ushort *,uint,ulong *,uint)

- ea: `0x1801cd3e0`
- end: `0x1801cd8e3`
- name: `?GetGlyphs@GdiTypeface@GEL@@UEBAIAEBUITypefaceList@2@AEBUFont@2@AEAUtag_SCRIPT_ANALYSIS@@GPEB_WIPEAGI4I4IPEAKI@Z`
- size: `1283`
- prototype: `unsigned int __fastcall(GEL::GdiTypeface *__hidden this, const struct GEL::ITypefaceList *, const struct GEL::Font *, struct tag_SCRIPT_ANALYSIS *, unsigned __int16, const wchar_t *, unsigned int, unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned int, unsigned int *, unsigned int)`
- caller_count: `0`
- callee_count: `16`
- tags: `file_ops`

## callees

- `0x180020198`
- `0x18003bab8`
- `0x1800565ba`
- `0x1800578b0`
- `0x180076c98`
- `0x180090490`
- `0x1800904c8`
- `0x180091710`
- `0x1800aecb0`
- `0x1800aedc0`
- `0x1800aedf0`
- `0x1800afbdc`
- `0x1800afcb0`
- `0x1800c1cc8`
- `0x1800dcec0`
- `0x1801cd3e0`

## import_xrefs

- `MSVCP140!_Mtx_unlock` at `0x1801cd670`
- `MSVCP140!_Mtx_unlock` at `0x1801cd789`
- `MSVCP140!_Mtx_unlock` at `0x1801cd670`
- `MSVCP140!_Mtx_unlock` at `0x1801cd789`
- `mso40uiWin32Client!__imp_MsoScriptShape` at `0x1801cd600`
- `mso40uiWin32Client!__imp_MsoScriptShape` at `0x1801cd664`
- `mso40uiWin32Client!__imp_MsoScriptShape` at `0x1801cd719`
- `mso40uiWin32Client!__imp_MsoScriptShape` at `0x1801cd77d`
- `mso40uiWin32Client!__imp_MsoScriptShape` at `0x1801cd600`
- `mso40uiWin32Client!__imp_MsoScriptShape` at `0x1801cd664`
- `mso40uiWin32Client!__imp_MsoScriptShape` at `0x1801cd719`
- `mso40uiWin32Client!__imp_MsoScriptShape` at `0x1801cd77d`
- `mso40uiWin32Client!__imp_MsoScriptFreeCache` at `0x1801cd7ad`
- `mso40uiWin32Client!__imp_MsoScriptFreeCache` at `0x1801cd82d`
- `mso40uiWin32Client!__imp_MsoScriptFreeCache` at `0x1801cd7ad`
- `mso40uiWin32Client!__imp_MsoScriptFreeCache` at `0x1801cd82d`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1801cd6b1`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1801cd7c1`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1801cd7cf`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1801cd841`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1801cd84f`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1801cd6b1`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1801cd7c1`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1801cd7cf`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1801cd841`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1801cd84f`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
unsigned int __fastcall GEL::GdiTypeface::GetGlyphs(
        GEL::GdiTypeface *this,
        const struct GEL::ITypefaceList *a2,
        const void **a3,
        struct tag_SCRIPT_ANALYSIS *a4,
        unsigned __int16 a5,
        wchar_t *a6,
        unsigned int a7,
        unsigned __int16 *a8,
        unsigned int a9,
        unsigned __int16 *a10,
        unsigned int a11,
        unsigned __int16 *a12,
        unsigned int a13,
        unsigned int *a14,
        unsigned int a15)
{
  unsigned __int16 *v18; // r12
  unsigned int v19; // edi
  unsigned int v20; // r14d
  unsigned int v21; // edx
  __int16 v22; // r15
  struct GEL::CachedScriptCache *ScriptCache; // rax
  __int64 v24; // r14
  unsigned int v25; // r15d
  int v26; // r13d
  int v27; // ebx
  void *v28; // rbx
  __int64 v29; // rax
  __int64 v30; // rdx
  __int64 v31; // r8
  int v32; // eax
  unsigned __int16 *v33; // rcx
  void *v34; // rbx
  __int64 v35; // rax
  unsigned int v37; // ebx
  unsigned __int16 *v38; // rdx
  unsigned int *v39; // r8
  int v40; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v41; // [rsp+84h] [rbp-7Ch] BYREF
  unsigned int v42; // [rsp+88h] [rbp-78h]
  void *v43; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v44; // [rsp+98h] [rbp-68h]
  unsigned __int16 *v45; // [rsp+A0h] [rbp-60h]
  wchar_t *v46; // [rsp+A8h] [rbp-58h]
  struct GEL::ITypefaceList *v47; // [rsp+B0h] [rbp-50h]
  __int64 v48; // [rsp+B8h] [rbp-48h] BYREF
  unsigned int *v49; // [rsp+C0h] [rbp-40h]
  _BYTE v50[16]; // [rsp+C8h] [rbp-38h] BYREF
  _Mtx_t v51; // [rsp+D8h] [rbp-28h]
  __int64 v52; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v53[40]; // [rsp+E8h] [rbp-18h] BYREF
  struct tagLOGFONTW v54; // [rsp+110h] [rbp+10h] BYREF

  v47 = a2;
  v46 = a6;
  v45 = a8;
  v18 = a12;
  v49 = a14;
  v42 = a15;
  v19 = 0;
  if ( BYTE14(xmmword_180523DD0) || *((_BYTE *)a3 + 33) )
    return GEL::DWriteTypeface::GetGlyphs(
             this,
             a2,
             (const struct GEL::Font *)a3,
             a4,
             a5,
             a6,
             a7,
             a8,
             a9,
             a10,
             a11,
             a12,
             a13,
             a14,
             a15);
  v20 = *((_DWORD *)a3 + 5);
  v40 = Ofc::Round<long,float>(a10);
  if ( !*a3
    || !a7
    || a9 < a7
    || a11 < a7
    || !a13
    || v21 < a13
    || (v20 & 0xFFFFFF00) != 0
    || (v22 = *(_WORD *)a4, (*(_WORD *)a4 & 0x4000) == 0) )
  {
LABEL_46:
    Ofc::CInvalidParamException::ThrowTag(0x3566A1u);
    __debugbreak();
  }
  memset_0(&v54, 0, sizeof(v54));
  v41 = v22 & 0x3FF;
  GEL::Typeface::GetLOGFONT(
    this,
    &v54,
    v40,
    v20,
    a3[3],
    v47,
    (const unsigned __int8 *)((unsigned __int64)(a3 + 4) & -(__int64)((v20 & 0x20) != 0)),
    (const unsigned __int8 *)(((unsigned __int64)a3 + 44) & -(__int64)((v20 & 0x80u) != 0)),
    &v41,
    0);
  v48 = 0;
  if ( BYTE1(xmmword_180523DD0) )
    ScriptCache = GEL::GdiTypeface::GetScriptCache(this, -v54.lfHeight, a4, v20);
  else
    ScriptCache = (struct GEL::CachedScriptCache *)&v48;
  GEL::ScriptCacheAccessor::ScriptCacheAccessor((GEL::ScriptCacheAccessor *)&v52, ScriptCache);
  v24 = v52;
  Ofc::TArray<unsigned short>::TArray<unsigned short>(&v43, v42);
  v40 = 0;
  v25 = Math::SafeCast<int,unsigned int>(&a7);
  v26 = Math::SafeCast<int,unsigned int>(&a13);
  if ( !v44 )
  {
LABEL_45:
    CrashWithRecovery(0x1E892496u, 0);
    goto LABEL_46;
  }
  v27 = MsoScriptShape(0, v24, v46, v25, v26, a4, v18, v45, v43, &v40);
  if ( v27 == -2147483638 )
  {
    if ( !v44 )
    {
      CrashWithRecovery(0x1E892496u, 0);
LABEL_25:
      v27 = v30;
      goto LABEL_26;
    }
    v28 = v43;
    v29 = GEL::SharedDeviceIC::SharedDeviceIC((GEL::SharedDeviceIC *)v50, v47, &v54);
    v27 = MsoScriptShape(**(_QWORD **)(v29 + 8), v24, v46, v25, v26, a4, v18, v45, v28, &v40);
    _Mtx_unlock(v51);
  }
  v30 = 2147746304LL;
  v31 = 1023;
  if ( !v27 )
  {
    if ( (*(_WORD *)a4 & 0x3FF) != 0 )
    {
      v32 = 0;
      v33 = v18;
      while ( v32 < v40 )
      {
        if ( !*v33 )
          goto LABEL_25;
        ++v32;
        ++v33;
      }
    }
    goto LABEL_38;
  }
LABEL_26:
  if ( v27 != (_DWORD)v30 )
    goto LABEL_32;
  if ( (*(_WORD *)a4 & (unsigned __int16)v31) == 0 )
    goto LABEL_37;
  *(_WORD *)a4 &= 0xFC00u;
  if ( !v44 )
  {
LABEL_35:
    CrashWithRecovery(0x1E892496u, 0);
    goto LABEL_36;
  }
  v27 = MsoScriptShape(0, v24, v46, v25, v26, a4, v18, v45, v43, &v40);
  if ( v27 != -2147483638 )
    goto LABEL_32;
  if ( !v44 )
  {
    CrashWithRecovery(0x1E892496u, 0);
    goto LABEL_35;
  }
  v34 = v43;
  v35 = GEL::SharedDeviceIC::SharedDeviceIC((GEL::SharedDeviceIC *)v50, v47, &v54);
  v27 = MsoScriptShape(**(_QWORD **)(v35 + 8), v24, v46, v25, v26, a4, v18, v45, v34, &v40);
  _Mtx_unlock(v51);
LABEL_32:
  if ( v27 == -2147024882 )
  {
    operator delete(v43);
    Ofc::CExclusiveAccess::~CExclusiveAccess((Ofc::CExclusiveAccess *)v53);
    MsoScriptFreeCache(&v48);
    return 0;
  }
LABEL_36:
  if ( v27 < 0 )
  {
LABEL_37:
    Ofc::CHResultException::ThrowTag(v27, 0x3566A3u);
    __debugbreak();
  }
LABEL_38:
  v37 = Math::SafeCast<unsigned int,int>(&v40, v30, v31);
  v38 = (unsigned __int16 *)v43;
  if ( v37 )
  {
    v39 = v49;
    while ( 1 )
    {
      if ( v19 >= v42 )
        goto LABEL_43;
      if ( v19 >= v44 )
        break;
      v39[v19] = v38[v19];
      if ( ++v19 >= v37 )
        goto LABEL_43;
    }
    CrashWithRecovery(0x1E892496u, 0);
    goto LABEL_45;
  }
LABEL_43:
  operator delete(v38);
  Ofc::CExclusiveAccess::~CExclusiveAccess((Ofc::CExclusiveAccess *)v53);
  MsoScriptFreeCache(&v48);
  return v37;
}

```

## disassembly

```asm
0x1801cd3e0  push    rbp
0x1801cd3e2  push    rbx
0x1801cd3e3  push    rsi
0x1801cd3e4  push    rdi
0x1801cd3e5  push    r12
0x1801cd3e7  push    r13
0x1801cd3e9  push    r14
0x1801cd3eb  push    r15
0x1801cd3ed  lea     rbp, [rsp-88h]
0x1801cd3f5  sub     rsp, 188h
0x1801cd3fc  mov     rax, cs:__security_cookie
0x1801cd403  xor     rax, rsp
0x1801cd406  mov     [rbp+0C0h+var_50], rax
0x1801cd40a  mov     rsi, r9
0x1801cd40d  mov     rbx, r8
0x1801cd410  mov     r10, rdx
0x1801cd413  mov     [rbp+0C0h+var_110], rdx
0x1801cd417  mov     r13, rcx
0x1801cd41a  mov     r8, [rbp+0C0h+arg_28]
0x1801cd421  mov     [rbp+0C0h+var_118], r8
0x1801cd425  mov     r9, [rbp+0C0h+arg_38]
0x1801cd42c  mov     [rbp+0C0h+var_120], r9
0x1801cd430  mov     rcx, [rbp+0C0h+arg_48]
0x1801cd437  mov     r12, [rbp+0C0h+arg_58]
0x1801cd43e  mov     rax, [rbp+0C0h+arg_68]
0x1801cd445  mov     [rbp+0C0h+var_100], rax
0x1801cd449  mov     edx, [rbp+0C0h+arg_70]
0x1801cd44f  mov     [rbp+0C0h+var_138], edx
0x1801cd452  xor     edi, edi
0x1801cd454  cmp     byte ptr cs:xmmword_180523DD0+0Eh, dil
0x1801cd45b  jnz     loc_1801CD861
0x1801cd461  cmp     [rbx+21h], dil
0x1801cd465  jnz     loc_1801CD861
0x1801cd46b  mov     r14d, [rbx+14h]
0x1801cd46f  movss   xmm0, dword ptr [rbx+10h]
0x1801cd474  call    ??$Round@JM@Ofc@@YAJM@Z; Ofc::Round<long,float>(float)
0x1801cd479  mov     [rbp+0C0h+var_140], eax
0x1801cd47c  cmp     [rbx], rdi
0x1801cd47f  jz      loc_1801CD856
0x1801cd485  mov     ecx, [rbp+0C0h+arg_30]
0x1801cd48b  test    ecx, ecx
0x1801cd48d  jz      loc_1801CD856
0x1801cd493  cmp     [rbp+0C0h+arg_40], ecx
0x1801cd499  jb      loc_1801CD856
0x1801cd49f  cmp     [rbp+0C0h+arg_50], ecx
0x1801cd4a5  jb      loc_1801CD856
0x1801cd4ab  cmp     [rbp+0C0h+arg_60], edi
0x1801cd4b1  jbe     loc_1801CD856
0x1801cd4b7  cmp     edx, [rbp+0C0h+arg_60]
0x1801cd4bd  jb      loc_1801CD856
0x1801cd4c3  test    r14d, 0FFFFFF00h
0x1801cd4ca  jnz     loc_1801CD856
0x1801cd4d0  movzx   r15d, word ptr [rsi]
0x1801cd4d4  bt      r15w, 0Eh
0x1801cd4da  jnb     loc_1801CD856
0x1801cd4e0  xor     edx, edx; Val
0x1801cd4e2  lea     r8d, [rdi+5Ch]; Size
0x1801cd4e6  lea     rcx, [rbp+0C0h+var_B0]; void *
0x1801cd4ea  call    memset_0
0x1801cd4ef  mov     eax, 3FFh
0x1801cd4f4  and     r15w, ax
0x1801cd4f8  mov     [rbp+0C0h+var_13C], r15w
0x1801cd4fd  mov     eax, r14d
0x1801cd500  and     al, 80h
0x1801cd502  lea     rcx, [rbx+2Ch]
0x1801cd506  neg     al
0x1801cd508  sbb     r8, r8
0x1801cd50b  and     r8, rcx
0x1801cd50e  mov     eax, r14d
0x1801cd511  and     al, 20h
0x1801cd513  lea     rcx, [rbx+20h]
0x1801cd517  neg     al
0x1801cd519  sbb     rdx, rdx
0x1801cd51c  and     rdx, rcx
0x1801cd51f  mov     byte ptr [rsp+1C0h+var_178], dil; bool
0x1801cd524  lea     rax, [rbp+0C0h+var_13C]
0x1801cd528  mov     [rsp+1C0h+var_180], rax; unsigned __int16 *
0x1801cd52d  mov     [rsp+1C0h+var_188], r8; unsigned __int8 *
0x1801cd532  mov     [rsp+1C0h+var_190], rdx; unsigned __int8 *
0x1801cd537  mov     rax, [rbp+0C0h+var_110]
0x1801cd53b  mov     [rsp+1C0h+var_198], rax; struct GEL::ITypefaceList *
0x1801cd540  mov     rax, [rbx+18h]
0x1801cd544  mov     [rsp+1C0h+var_1A0], rax; void *
0x1801cd549  mov     r9d, r14d; unsigned int
0x1801cd54c  mov     r8d, [rbp+0C0h+var_140]; int
0x1801cd550  lea     rdx, [rbp+0C0h+var_B0]; struct tagLOGFONTW *
0x1801cd554  mov     rcx, r13; this
0x1801cd557  call    ?GetLOGFONT@Typeface@GEL@@QEBAXAEAUtagLOGFONTW@@JIPEBXAEBUITypefaceList@2@PEBE3PEBG_N@Z; GEL::Typeface::GetLOGFONT(tagLOGFONTW &,long,uint,void const *,GEL::ITypefaceList const &,uchar const *,uchar const *,ushort const *,bool)
0x1801cd55c  mov     [rbp+0C0h+var_108], rdi
0x1801cd560  cmp     byte ptr cs:xmmword_180523DD0+1, dil
0x1801cd567  jz      short loc_1801CD57E
0x1801cd569  mov     edx, [rbp+0C0h+var_B0.lfHeight]
0x1801cd56c  neg     edx; int
0x1801cd56e  mov     r9d, r14d; unsigned int
0x1801cd571  mov     r8, rsi; struct tag_SCRIPT_ANALYSIS *
0x1801cd574  mov     rcx, r13; this
0x1801cd577  call    ?GetScriptCache@GdiTypeface@GEL@@UEBAAEAVCachedScriptCache@2@JAEBUtag_SCRIPT_ANALYSIS@@I@Z; GEL::GdiTypeface::GetScriptCache(long,tag_SCRIPT_ANALYSIS const &,uint)
0x1801cd57c  jmp     short loc_1801CD582
0x1801cd57e  lea     rax, [rbp+0C0h+var_108]
0x1801cd582  mov     rdx, rax; struct GEL::CachedScriptCache *
0x1801cd585  lea     rcx, [rbp+0C0h+var_E0]; this
0x1801cd589  call    ??0ScriptCacheAccessor@GEL@@QEAA@AEAVCachedScriptCache@1@@Z; GEL::ScriptCacheAccessor::ScriptCacheAccessor(GEL::CachedScriptCache &)
0x1801cd58e  nop
0x1801cd58f  mov     r14, [rbp+0C0h+var_E0]
0x1801cd593  mov     edx, [rbp+0C0h+var_138]
0x1801cd596  lea     rcx, [rbp+0C0h+var_130]
0x1801cd59a  call    ??0?$TArray@G@Ofc@@QEAA@K@Z; Ofc::TArray<ushort>::TArray<ushort>(ulong)
0x1801cd59f  nop
0x1801cd5a0  mov     [rbp+0C0h+var_140], edi
0x1801cd5a3  lea     rcx, [rbp+0C0h+arg_30]
0x1801cd5aa  call    ??$SafeCast@HI@Math@@YAHAEBI@Z; Math::SafeCast<int,uint>(uint const &)
0x1801cd5af  mov     r15d, eax
0x1801cd5b2  lea     rcx, [rbp+0C0h+arg_60]
0x1801cd5b9  call    ??$SafeCast@HI@Math@@YAHAEBI@Z; Math::SafeCast<int,uint>(uint const &)
0x1801cd5be  mov     r13d, eax
0x1801cd5c1  cmp     [rbp+0C0h+var_128], edi
0x1801cd5c4  jbe     loc_1801CD848
0x1801cd5ca  mov     rcx, [rbp+0C0h+var_130]
0x1801cd5ce  lea     rax, [rbp+0C0h+var_140]
0x1801cd5d2  mov     [rsp+1C0h+var_178], rax
0x1801cd5d7  mov     [rsp+1C0h+var_180], rcx
0x1801cd5dc  mov     rax, [rbp+0C0h+var_120]
0x1801cd5e0  mov     [rsp+1C0h+var_188], rax
0x1801cd5e5  mov     [rsp+1C0h+var_190], r12
0x1801cd5ea  mov     [rsp+1C0h+var_198], rsi
0x1801cd5ef  mov     dword ptr [rsp+1C0h+var_1A0], r13d
0x1801cd5f4  mov     r9d, r15d
0x1801cd5f7  mov     r8, [rbp+0C0h+var_118]
0x1801cd5fb  mov     rdx, r14
0x1801cd5fe  xor     ecx, ecx
0x1801cd600  call    cs:__imp_MsoScriptShape
0x1801cd606  mov     ebx, eax
0x1801cd608  cmp     eax, 8000000Ah
0x1801cd60d  jnz     short loc_1801CD676
0x1801cd60f  cmp     [rbp+0C0h+var_128], edi
0x1801cd612  jbe     loc_1801CD6AA
0x1801cd618  mov     rbx, [rbp+0C0h+var_130]
0x1801cd61c  lea     r8, [rbp+0C0h+var_B0]; struct tagLOGFONTW *
0x1801cd620  mov     rdx, [rbp+0C0h+var_110]; struct GEL::ITypefaceList *
0x1801cd624  lea     rcx, [rbp+0C0h+var_F8]; this
0x1801cd628  call    ??0SharedDeviceIC@GEL@@QEAA@AEBUITypefaceList@1@AEBUtagLOGFONTW@@@Z; GEL::SharedDeviceIC::SharedDeviceIC(GEL::ITypefaceList const &,tagLOGFONTW const &)
0x1801cd62d  mov     rcx, [rax+8]
0x1801cd631  lea     rax, [rbp+0C0h+var_140]
0x1801cd635  mov     [rsp+1C0h+var_178], rax
0x1801cd63a  mov     [rsp+1C0h+var_180], rbx
0x1801cd63f  mov     rax, [rbp+0C0h+var_120]
0x1801cd643  mov     [rsp+1C0h+var_188], rax
0x1801cd648  mov     [rsp+1C0h+var_190], r12
0x1801cd64d  mov     [rsp+1C0h+var_198], rsi
0x1801cd652  mov     dword ptr [rsp+1C0h+var_1A0], r13d
0x1801cd657  mov     r9d, r15d
0x1801cd65a  mov     r8, [rbp+0C0h+var_118]
0x1801cd65e  mov     rdx, r14
0x1801cd661  mov     rcx, [rcx]
0x1801cd664  call    cs:__imp_MsoScriptShape
0x1801cd66a  mov     ebx, eax
0x1801cd66c  mov     rcx, [rbp+0C0h+var_E8]; _Mtx_t
0x1801cd670  call    cs:__imp__Mtx_unlock
0x1801cd676  mov     edx, 80040200h
0x1801cd67b  mov     r8d, 3FFh
0x1801cd681  test    ebx, ebx
0x1801cd683  jnz     short loc_1801CD6BA
0x1801cd685  test    [rsi], r8w
0x1801cd689  jz      loc_1801CD7E7
0x1801cd68f  mov     eax, edi
0x1801cd691  mov     rcx, r12
0x1801cd694  cmp     eax, [rbp+0C0h+var_140]
0x1801cd697  jge     loc_1801CD7E7
0x1801cd69d  cmp     [rcx], di
0x1801cd6a0  jz      short loc_1801CD6B8
0x1801cd6a2  inc     eax
0x1801cd6a4  add     rcx, 2
0x1801cd6a8  jmp     short loc_1801CD694
0x1801cd6aa  xor     edx, edx
0x1801cd6ac  mov     ecx, 1E892496h
0x1801cd6b1  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1801cd6b7  nop
0x1801cd6b8  mov     ebx, edx
0x1801cd6ba  cmp     ebx, edx
0x1801cd6bc  jnz     loc_1801CD78F
0x1801cd6c2  movzx   eax, word ptr [rsi]
0x1801cd6c5  test    r8w, ax
0x1801cd6c9  jz      loc_1801CD7DA
0x1801cd6cf  mov     ecx, 0FC00h
0x1801cd6d4  and     ax, cx
0x1801cd6d7  mov     [rsi], ax
0x1801cd6da  cmp     [rbp+0C0h+var_128], edi
0x1801cd6dd  jbe     loc_1801CD7C8
0x1801cd6e3  mov     rax, [rbp+0C0h+var_130]
0x1801cd6e7  lea     rcx, [rbp+0C0h+var_140]
0x1801cd6eb  mov     [rsp+1C0h+var_178], rcx
0x1801cd6f0  mov     [rsp+1C0h+var_180], rax
0x1801cd6f5  mov     rax, [rbp+0C0h+var_120]
0x1801cd6f9  mov     [rsp+1C0h+var_188], rax
0x1801cd6fe  mov     [rsp+1C0h+var_190], r12
0x1801cd703  mov     [rsp+1C0h+var_198], rsi
0x1801cd708  mov     dword ptr [rsp+1C0h+var_1A0], r13d
0x1801cd70d  mov     r9d, r15d
0x1801cd710  mov     r8, [rbp+0C0h+var_118]
0x1801cd714  mov     rdx, r14
0x1801cd717  xor     ecx, ecx
0x1801cd719  call    cs:__imp_MsoScriptShape
0x1801cd71f  mov     ebx, eax
0x1801cd721  cmp     eax, 8000000Ah
0x1801cd726  jnz     short loc_1801CD78F
0x1801cd728  cmp     [rbp+0C0h+var_128], edi
0x1801cd72b  jbe     loc_1801CD7BA
0x1801cd731  mov     rbx, [rbp+0C0h+var_130]
0x1801cd735  lea     r8, [rbp+0C0h+var_B0]; struct tagLOGFONTW *
0x1801cd739  mov     rdx, [rbp+0C0h+var_110]; struct GEL::ITypefaceList *
0x1801cd73d  lea     rcx, [rbp+0C0h+var_F8]; this
0x1801cd741  call    ??0SharedDeviceIC@GEL@@QEAA@AEBUITypefaceList@1@AEBUtagLOGFONTW@@@Z; GEL::SharedDeviceIC::SharedDeviceIC(GEL::ITypefaceList const &,tagLOGFONTW const &)
0x1801cd746  mov     rcx, [rax+8]
0x1801cd74a  lea     rax, [rbp+0C0h+var_140]
0x1801cd74e  mov     [rsp+1C0h+var_178], rax
0x1801cd753  mov     [rsp+1C0h+var_180], rbx
0x1801cd758  mov     rax, [rbp+0C0h+var_120]
0x1801cd75c  mov     [rsp+1C0h+var_188], rax
0x1801cd761  mov     [rsp+1C0h+var_190], r12
0x1801cd766  mov     [rsp+1C0h+var_198], rsi
0x1801cd76b  mov     dword ptr [rsp+1C0h+var_1A0], r13d
0x1801cd770  mov     r9d, r15d
0x1801cd773  mov     r8, [rbp+0C0h+var_118]
0x1801cd777  mov     rdx, r14
0x1801cd77a  mov     rcx, [rcx]
0x1801cd77d  call    cs:__imp_MsoScriptShape
0x1801cd783  mov     ebx, eax
0x1801cd785  mov     rcx, [rbp+0C0h+var_E8]; _Mtx_t
0x1801cd789  call    cs:__imp__Mtx_unlock
0x1801cd78f  cmp     ebx, 8007000Eh
0x1801cd795  jnz     short loc_1801CD7D6
0x1801cd797  mov     rcx, [rbp+0C0h+var_130]; void *
0x1801cd79b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1801cd7a0  lea     rcx, [rbp+0C0h+var_D8]; this
0x1801cd7a4  call    ??1CExclusiveAccess@Ofc@@QEAA@XZ; Ofc::CExclusiveAccess::~CExclusiveAccess(void)
0x1801cd7a9  lea     rcx, [rbp+0C0h+var_108]
0x1801cd7ad  call    cs:__imp_MsoScriptFreeCache
0x1801cd7b3  xor     eax, eax
0x1801cd7b5  jmp     loc_1801CD8C3
0x1801cd7ba  xor     edx, edx
0x1801cd7bc  mov     ecx, 1E892496h
0x1801cd7c1  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1801cd7c7  nop
0x1801cd7c8  xor     edx, edx
0x1801cd7ca  mov     ecx, 1E892496h
0x1801cd7cf  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1801cd7d5  nop
0x1801cd7d6  test    ebx, ebx
0x1801cd7d8  jns     short loc_1801CD7E7
0x1801cd7da  mov     edx, 3566A3h; unsigned int
0x1801cd7df  mov     ecx, ebx; int
0x1801cd7e1  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x1801cd7e6  int     3; Trap to Debugger
0x1801cd7e7  lea     rcx, [rbp+0C0h+var_140]
0x1801cd7eb  call    ??$SafeCast@IH@Math@@YAIAEBH@Z; Math::SafeCast<uint,int>(int const &)
0x1801cd7f0  mov     ebx, eax
0x1801cd7f2  mov     rdx, [rbp+0C0h+var_130]
0x1801cd7f6  test    eax, eax
0x1801cd7f8  jz      short loc_1801CD818
0x1801cd7fa  mov     r8, [rbp+0C0h+var_100]
0x1801cd7fe  cmp     edi, [rbp+0C0h+var_138]
0x1801cd801  jnb     short loc_1801CD818
0x1801cd803  cmp     edi, [rbp+0C0h+var_128]
0x1801cd806  jnb     short loc_1801CD83A
0x1801cd808  mov     ecx, edi
0x1801cd80a  movzx   eax, word ptr [rdx+rcx*2]
0x1801cd80e  mov     [r8+rcx*4], eax
0x1801cd812  inc     edi
0x1801cd814  cmp     edi, ebx
0x1801cd816  jb      short loc_1801CD7FE
0x1801cd818  mov     rcx, rdx; void *
0x1801cd81b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1801cd820  lea     rcx, [rbp+0C0h+var_D8]; this
0x1801cd824  call    ??1CExclusiveAccess@Ofc@@QEAA@XZ; Ofc::CExclusiveAccess::~CExclusiveAccess(void)
0x1801cd829  lea     rcx, [rbp+0C0h+var_108]
0x1801cd82d  call    cs:__imp_MsoScriptFreeCache
0x1801cd833  mov     eax, ebx
0x1801cd835  jmp     loc_1801CD8C3
0x1801cd83a  xor     edx, edx
0x1801cd83c  mov     ecx, 1E892496h
0x1801cd841  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1801cd847  nop
0x1801cd848  xor     edx, edx
0x1801cd84a  mov     ecx, 1E892496h
0x1801cd84f  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1801cd855  nop
0x1801cd856  mov     ecx, 3566A1h; unsigned int
0x1801cd85b  call    ?ThrowTag@CInvalidParamException@Ofc@@SAXK@Z; Ofc::CInvalidParamException::ThrowTag(ulong)
0x1801cd860  int     3; Trap to Debugger
0x1801cd861  mov     [rsp+1C0h+var_150], edx; unsigned int
0x1801cd865  mov     [rsp+1C0h+var_158], rax; unsigned int *
0x1801cd86a  mov     eax, [rbp+0C0h+arg_60]
0x1801cd870  mov     [rsp+1C0h+var_160], eax; unsigned int
0x1801cd874  mov     [rsp+1C0h+var_168], r12; unsigned __int16 *
0x1801cd879  mov     eax, [rbp+0C0h+arg_50]
0x1801cd87f  mov     [rsp+1C0h+var_170], eax; unsigned int
0x1801cd883  mov     [rsp+1C0h+var_178], rcx; unsigned __int16 *
0x1801cd888  mov     eax, [rbp+0C0h+arg_40]
0x1801cd88e  mov     dword ptr [rsp+1C0h+var_180], eax; unsigned int
0x1801cd892  mov     [rsp+1C0h+var_188], r9; unsigned __int16 *
  ... truncated ...
```
