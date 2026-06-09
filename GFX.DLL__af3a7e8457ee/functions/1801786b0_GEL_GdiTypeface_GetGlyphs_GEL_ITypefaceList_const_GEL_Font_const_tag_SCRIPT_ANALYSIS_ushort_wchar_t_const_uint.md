# GEL::GdiTypeface::GetGlyphs(GEL::ITypefaceList const &,GEL::Font const &,tag_SCRIPT_ANALYSIS &,ushort,wchar_t const *,uint,ushort *,uint,ushort *,uint,ushort *,uint,ulong *,uint)

- ea: `0x1801786b0`
- end: `0x180178bf1`
- name: `?GetGlyphs@GdiTypeface@GEL@@UEBAIAEBUITypefaceList@2@AEBUFont@2@AEAUtag_SCRIPT_ANALYSIS@@GPEB_WIPEAGI4I4IPEAKI@Z`
- size: `1345`
- prototype: `unsigned int __fastcall(GEL::GdiTypeface *__hidden this, const struct GEL::ITypefaceList *, const struct GEL::Font *, struct tag_SCRIPT_ANALYSIS *, unsigned __int16, const wchar_t *, unsigned int, unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned int, unsigned int *, unsigned int)`
- caller_count: `0`
- callee_count: `17`
- tags: `file_ops`

## callees

- `0x18001ffb4`
- `0x180037544`
- `0x1800379e0`
- `0x18003c0d0`
- `0x180055b26`
- `0x180056ee0`
- `0x1800774c0`
- `0x1800795e4`
- `0x180079d04`
- `0x180099c8c`
- `0x180099cc0`
- `0x18009a148`
- `0x18009ba90`
- `0x1800d33a4`
- `0x1800dc27c`
- `0x18010d41c`
- `0x1801786b0`

## import_xrefs

- `MSVCP140!_Mtx_unlock` at `0x18017897a`
- `MSVCP140!_Mtx_unlock` at `0x180178a93`
- `MSVCP140!_Mtx_unlock` at `0x18017897a`
- `MSVCP140!_Mtx_unlock` at `0x180178a93`
- `mso40uiWin32Client!__imp_MsoScriptShape` at `0x18017890a`
- `mso40uiWin32Client!__imp_MsoScriptShape` at `0x18017896e`
- `mso40uiWin32Client!__imp_MsoScriptShape` at `0x180178a23`
- `mso40uiWin32Client!__imp_MsoScriptShape` at `0x180178a87`
- `mso40uiWin32Client!__imp_MsoScriptShape` at `0x18017890a`
- `mso40uiWin32Client!__imp_MsoScriptShape` at `0x18017896e`
- `mso40uiWin32Client!__imp_MsoScriptShape` at `0x180178a23`
- `mso40uiWin32Client!__imp_MsoScriptShape` at `0x180178a87`
- `mso40uiWin32Client!__imp_MsoScriptFreeCache` at `0x180178ab7`
- `mso40uiWin32Client!__imp_MsoScriptFreeCache` at `0x180178b3b`
- `mso40uiWin32Client!__imp_MsoScriptFreeCache` at `0x180178ab7`
- `mso40uiWin32Client!__imp_MsoScriptFreeCache` at `0x180178b3b`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1801789bb`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180178acb`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180178ad9`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180178b4f`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180178b5d`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1801789bb`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180178acb`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180178ad9`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180178b4f`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180178b5d`

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
  unsigned __int16 *v18; // r13
  unsigned int v19; // edi
  unsigned int v20; // r14d
  unsigned int v21; // edx
  __int16 v22; // r15
  struct GEL::CachedScriptCache *ScriptCache; // rbx
  struct Ofc::CExclusiveAccessMgr *v24; // rdx
  struct GEL::CachedScriptCache *v25; // r14
  unsigned int v26; // r15d
  int v27; // r12d
  int v28; // ebx
  void *v29; // rbx
  __int64 v30; // rax
  __int64 v31; // rdx
  __int64 v32; // r8
  int v33; // eax
  unsigned __int16 *v34; // rcx
  void *v35; // rbx
  __int64 v36; // rax
  unsigned int v38; // ebx
  unsigned __int16 *v39; // rdx
  unsigned int v40; // r8d
  unsigned int *v41; // r9
  int v42; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v43; // [rsp+84h] [rbp-7Ch] BYREF
  unsigned int v44; // [rsp+88h] [rbp-78h]
  void *v45; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v46; // [rsp+98h] [rbp-68h]
  unsigned __int16 *v47; // [rsp+A0h] [rbp-60h]
  wchar_t *v48; // [rsp+A8h] [rbp-58h]
  struct GEL::ITypefaceList *v49; // [rsp+B0h] [rbp-50h]
  __int64 v50; // [rsp+B8h] [rbp-48h] BYREF
  unsigned int *v51; // [rsp+C0h] [rbp-40h]
  _BYTE v52[16]; // [rsp+C8h] [rbp-38h] BYREF
  _Mtx_t v53; // [rsp+D8h] [rbp-28h]
  struct GEL::CachedScriptCache *v54; // [rsp+E0h] [rbp-20h]
  _BYTE v55[40]; // [rsp+E8h] [rbp-18h] BYREF
  struct tagLOGFONTW v56; // [rsp+110h] [rbp+10h] BYREF

  v49 = a2;
  v48 = a6;
  v47 = a8;
  v18 = a12;
  v51 = a14;
  v44 = a15;
  v19 = 0;
  if ( BYTE14(xmmword_18051FD50) || *((_BYTE *)a3 + 33) )
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
  v42 = Ofc::Round<long,float>(a10);
  if ( !*a3
    || !a7
    || a9 < a7
    || a11 < a7
    || !a13
    || v21 < a13
    || (v20 & 0xFFFFFF00) != 0
    || (v22 = *(_WORD *)a4, (*(_WORD *)a4 & 0x4000) == 0) )
  {
LABEL_48:
    Ofc::CInvalidParamException::ThrowTag(0x3566A1u);
    __debugbreak();
  }
  memset_0(&v56, 0, sizeof(v56));
  v43 = v22 & 0x3FF;
  GEL::Typeface::GetLOGFONT(
    this,
    &v56,
    v42,
    v20,
    a3[3],
    v49,
    (const unsigned __int8 *)((unsigned __int64)(a3 + 4) & -(__int64)((v20 & 0x20) != 0)),
    (const unsigned __int8 *)(((unsigned __int64)a3 + 44) & -(__int64)((v20 & 0x80u) != 0)),
    &v43,
    0);
  v50 = 0;
  if ( BYTE1(xmmword_18051FD50) )
    ScriptCache = GEL::GdiTypeface::GetScriptCache(this, -v56.lfHeight, a4, v20);
  else
    ScriptCache = (struct GEL::CachedScriptCache *)&v50;
  v54 = ScriptCache;
  v24 = Ofc::TSingleton<GEL::ScriptCacheAccessMgr>::s_pInstance;
  if ( (unsigned __int64)Ofc::TSingleton<GEL::ScriptCacheAccessMgr>::s_pInstance <= 1 )
  {
    Ofc::ThreadSafeInitPointerOnce<GEL::ScriptCacheAccessMgr *,Ofc::TSingletonFactory<GEL::ScriptCacheAccessMgr>>();
    v24 = Ofc::TSingleton<GEL::ScriptCacheAccessMgr>::s_pInstance;
  }
  Ofc::CExclusiveAccess::CExclusiveAccess((Ofc::CExclusiveAccess *)v55, v24, ScriptCache);
  v25 = v54;
  Ofc::CArrayImpl::CArrayImpl(
    (Ofc::CArrayImpl *)&v45,
    2u,
    v44,
    v44,
    1,
    Ofc::TDefaultConstructRange<tag_SCRIPT_VISATTR,1,1>::Do);
  v42 = 0;
  v26 = Math::SafeCast<int,unsigned int>(&a7);
  v27 = Math::SafeCast<int,unsigned int>(&a13);
  if ( !v46 )
  {
LABEL_47:
    CrashWithRecovery(0x1E892496u, 0);
    goto LABEL_48;
  }
  v28 = MsoScriptShape(0, v25, v48, v26, v27, a4, v18, v47, v45, &v42);
  if ( v28 == -2147483638 )
  {
    if ( !v46 )
    {
      CrashWithRecovery(0x1E892496u, 0);
LABEL_27:
      v28 = v31;
      goto LABEL_28;
    }
    v29 = v45;
    v30 = GEL::SharedDeviceIC::SharedDeviceIC((GEL::SharedDeviceIC *)v52, v49, &v56);
    v28 = MsoScriptShape(**(_QWORD **)(v30 + 8), v25, v48, v26, v27, a4, v18, v47, v29, &v42);
    _Mtx_unlock(v53);
  }
  v31 = 2147746304LL;
  v32 = 1023;
  if ( !v28 )
  {
    if ( (*(_WORD *)a4 & 0x3FF) != 0 )
    {
      v33 = 0;
      v34 = v18;
      while ( v33 < v42 )
      {
        if ( !*v34 )
          goto LABEL_27;
        ++v33;
        ++v34;
      }
    }
    goto LABEL_40;
  }
LABEL_28:
  if ( v28 != (_DWORD)v31 )
    goto LABEL_34;
  if ( (*(_WORD *)a4 & (unsigned __int16)v32) == 0 )
    goto LABEL_39;
  *(_WORD *)a4 &= 0xFC00u;
  if ( !v46 )
  {
LABEL_37:
    CrashWithRecovery(0x1E892496u, 0);
    goto LABEL_38;
  }
  v28 = MsoScriptShape(0, v25, v48, v26, v27, a4, v18, v47, v45, &v42);
  if ( v28 != -2147483638 )
    goto LABEL_34;
  if ( !v46 )
  {
    CrashWithRecovery(0x1E892496u, 0);
    goto LABEL_37;
  }
  v35 = v45;
  v36 = GEL::SharedDeviceIC::SharedDeviceIC((GEL::SharedDeviceIC *)v52, v49, &v56);
  v28 = MsoScriptShape(**(_QWORD **)(v36 + 8), v25, v48, v26, v27, a4, v18, v47, v35, &v42);
  _Mtx_unlock(v53);
LABEL_34:
  if ( v28 == -2147024882 )
  {
    operator delete(v45);
    Ofc::CExclusiveAccess::~CExclusiveAccess((Ofc::CExclusiveAccess *)v55);
    MsoScriptFreeCache(&v50);
    return 0;
  }
LABEL_38:
  if ( v28 < 0 )
  {
LABEL_39:
    Ofc::CHResultException::ThrowTag(v28, 0x3566A3u);
    __debugbreak();
  }
LABEL_40:
  v38 = Math::SafeCast<unsigned int,int>(&v42, v31, v32);
  v39 = (unsigned __int16 *)v45;
  if ( v38 )
  {
    v40 = v44;
    v41 = v51;
    while ( 1 )
    {
      if ( v19 >= v40 )
        goto LABEL_45;
      if ( v19 >= v46 )
        break;
      v41[v19] = v39[v19];
      if ( ++v19 >= v38 )
        goto LABEL_45;
    }
    CrashWithRecovery(0x1E892496u, 0);
    goto LABEL_47;
  }
LABEL_45:
  operator delete(v39);
  Ofc::CExclusiveAccess::~CExclusiveAccess((Ofc::CExclusiveAccess *)v55);
  MsoScriptFreeCache(&v50);
  return v38;
}

```

## disassembly

```asm
0x1801786b0  push    rbp
0x1801786b2  push    rbx
0x1801786b3  push    rsi
0x1801786b4  push    rdi
0x1801786b5  push    r12
0x1801786b7  push    r13
0x1801786b9  push    r14
0x1801786bb  push    r15
0x1801786bd  lea     rbp, [rsp-88h]
0x1801786c5  sub     rsp, 188h
0x1801786cc  mov     rax, cs:__security_cookie
0x1801786d3  xor     rax, rsp
0x1801786d6  mov     [rbp+0C0h+var_50], rax
0x1801786da  mov     rsi, r9
0x1801786dd  mov     rbx, r8
0x1801786e0  mov     r10, rdx
0x1801786e3  mov     [rbp+0C0h+var_110], rdx
0x1801786e7  mov     r12, rcx
0x1801786ea  mov     r8, [rbp+0C0h+arg_28]
0x1801786f1  mov     [rbp+0C0h+var_118], r8
0x1801786f5  mov     r9, [rbp+0C0h+arg_38]
0x1801786fc  mov     [rbp+0C0h+var_120], r9
0x180178700  mov     rcx, [rbp+0C0h+arg_48]
0x180178707  mov     r13, [rbp+0C0h+arg_58]
0x18017870e  mov     rax, [rbp+0C0h+arg_68]
0x180178715  mov     [rbp+0C0h+var_100], rax
0x180178719  mov     edx, [rbp+0C0h+arg_70]
0x18017871f  mov     [rbp+0C0h+var_138], edx
0x180178722  xor     edi, edi
0x180178724  cmp     byte ptr cs:xmmword_18051FD50+0Eh, dil
0x18017872b  jnz     loc_180178B6F
0x180178731  cmp     [rbx+21h], dil
0x180178735  jnz     loc_180178B6F
0x18017873b  mov     r14d, [rbx+14h]
0x18017873f  movss   xmm0, dword ptr [rbx+10h]
0x180178744  call    ??$Round@JM@Ofc@@YAJM@Z; Ofc::Round<long,float>(float)
0x180178749  mov     [rbp+0C0h+var_140], eax
0x18017874c  cmp     [rbx], rdi
0x18017874f  jz      loc_180178B64
0x180178755  mov     ecx, [rbp+0C0h+arg_30]
0x18017875b  test    ecx, ecx
0x18017875d  jz      loc_180178B64
0x180178763  cmp     [rbp+0C0h+arg_40], ecx
0x180178769  jb      loc_180178B64
0x18017876f  cmp     [rbp+0C0h+arg_50], ecx
0x180178775  jb      loc_180178B64
0x18017877b  cmp     [rbp+0C0h+arg_60], edi
0x180178781  jbe     loc_180178B64
0x180178787  cmp     edx, [rbp+0C0h+arg_60]
0x18017878d  jb      loc_180178B64
0x180178793  test    r14d, 0FFFFFF00h
0x18017879a  jnz     loc_180178B64
0x1801787a0  movzx   r15d, word ptr [rsi]
0x1801787a4  bt      r15w, 0Eh
0x1801787aa  jnb     loc_180178B64
0x1801787b0  xor     edx, edx; Val
0x1801787b2  lea     r8d, [rdi+5Ch]; Size
0x1801787b6  lea     rcx, [rbp+0C0h+var_B0]; void *
0x1801787ba  call    memset_0
0x1801787bf  mov     eax, 3FFh
0x1801787c4  and     r15w, ax
0x1801787c8  mov     [rbp+0C0h+var_13C], r15w
0x1801787cd  mov     eax, r14d
0x1801787d0  and     al, 80h
0x1801787d2  lea     rcx, [rbx+2Ch]
0x1801787d6  neg     al
0x1801787d8  sbb     r8, r8
0x1801787db  and     r8, rcx
0x1801787de  mov     eax, r14d
0x1801787e1  and     al, 20h
0x1801787e3  lea     rcx, [rbx+20h]
0x1801787e7  neg     al
0x1801787e9  sbb     rdx, rdx
0x1801787ec  and     rdx, rcx
0x1801787ef  mov     byte ptr [rsp+1C0h+var_178], dil; bool
0x1801787f4  lea     rax, [rbp+0C0h+var_13C]
0x1801787f8  mov     [rsp+1C0h+var_180], rax; unsigned __int16 *
0x1801787fd  mov     [rsp+1C0h+var_188], r8; unsigned __int8 *
0x180178802  mov     [rsp+1C0h+var_190], rdx; unsigned __int8 *
0x180178807  mov     rax, [rbp+0C0h+var_110]
0x18017880b  mov     [rsp+1C0h+var_198], rax; struct GEL::ITypefaceList *
0x180178810  mov     rax, [rbx+18h]
0x180178814  mov     [rsp+1C0h+var_1A0], rax; void *
0x180178819  mov     r9d, r14d; unsigned int
0x18017881c  mov     r8d, [rbp+0C0h+var_140]; int
0x180178820  lea     rdx, [rbp+0C0h+var_B0]; struct tagLOGFONTW *
0x180178824  mov     rcx, r12; this
0x180178827  call    ?GetLOGFONT@Typeface@GEL@@QEBAXAEAUtagLOGFONTW@@JIPEBXAEBUITypefaceList@2@PEBE3PEBG_N@Z; GEL::Typeface::GetLOGFONT(tagLOGFONTW &,long,uint,void const *,GEL::ITypefaceList const &,uchar const *,uchar const *,ushort const *,bool)
0x18017882c  mov     [rbp+0C0h+var_108], rdi
0x180178830  cmp     byte ptr cs:xmmword_18051FD50+1, dil
0x180178837  jz      short loc_180178851
0x180178839  mov     edx, [rbp+0C0h+var_B0.lfHeight]
0x18017883c  neg     edx; int
0x18017883e  mov     r9d, r14d; unsigned int
0x180178841  mov     r8, rsi; struct tag_SCRIPT_ANALYSIS *
0x180178844  mov     rcx, r12; this
0x180178847  call    ?GetScriptCache@GdiTypeface@GEL@@UEBAAEAVCachedScriptCache@2@JAEBUtag_SCRIPT_ANALYSIS@@I@Z; GEL::GdiTypeface::GetScriptCache(long,tag_SCRIPT_ANALYSIS const &,uint)
0x18017884c  mov     rbx, rax
0x18017884f  jmp     short loc_180178855
0x180178851  lea     rbx, [rbp+0C0h+var_108]
0x180178855  mov     [rbp+0C0h+var_E0], rbx
0x180178859  mov     rdx, cs:?s_pInstance@?$TSingleton@VScriptCacheAccessMgr@GEL@@@Ofc@@0PEAVScriptCacheAccessMgr@GEL@@EA; GEL::ScriptCacheAccessMgr * Ofc::TSingleton<GEL::ScriptCacheAccessMgr>::s_pInstance
0x180178860  cmp     rdx, 1
0x180178864  ja      short loc_180178872
0x180178866  call    ??$ThreadSafeInitPointerOnce@PEAVScriptCacheAccessMgr@GEL@@V?$TSingletonFactory@VScriptCacheAccessMgr@GEL@@@Ofc@@@Ofc@@YAXPECREAVScriptCacheAccessMgr@GEL@@@Z; Ofc::ThreadSafeInitPointerOnce<GEL::ScriptCacheAccessMgr *,Ofc::TSingletonFactory<GEL::ScriptCacheAccessMgr>>(GEL::ScriptCacheAccessMgr * volatile *)
0x18017886b  mov     rdx, cs:?s_pInstance@?$TSingleton@VScriptCacheAccessMgr@GEL@@@Ofc@@0PEAVScriptCacheAccessMgr@GEL@@EA; struct Ofc::CExclusiveAccessMgr *
0x180178872  mov     r8, rbx; void *
0x180178875  lea     rcx, [rbp+0C0h+var_D8]; this
0x180178879  call    ??0CExclusiveAccess@Ofc@@QEAA@AEAVCExclusiveAccessMgr@1@PEBX@Z; Ofc::CExclusiveAccess::CExclusiveAccess(Ofc::CExclusiveAccessMgr &,void const *)
0x18017887e  nop
0x18017887f  mov     r14, [rbp+0C0h+var_E0]
0x180178883  lea     rax, ?Do@?$TDefaultConstructRange@Utag_SCRIPT_VISATTR@@$00$00@Ofc@@SAXPEAEK@Z; Ofc::TDefaultConstructRange<tag_SCRIPT_VISATTR,1,1>::Do(uchar *,ulong)
0x18017888a  mov     [rsp+1C0h+var_198], rax; void (*)(unsigned __int8 *, unsigned int)
0x18017888f  mov     byte ptr [rsp+1C0h+var_1A0], 1; bool
0x180178894  mov     r9d, [rbp+0C0h+var_138]; unsigned int
0x180178898  mov     r8d, r9d; unsigned int
0x18017889b  mov     edx, 2; unsigned int
0x1801788a0  lea     rcx, [rbp+0C0h+var_130]; this
0x1801788a4  call    ??0CArrayImpl@Ofc@@IEAA@KKK_NP6AXPEAEK@Z@Z; Ofc::CArrayImpl::CArrayImpl(ulong,ulong,ulong,bool,void (*)(uchar *,ulong))
0x1801788a9  nop
0x1801788aa  mov     [rbp+0C0h+var_140], edi
0x1801788ad  lea     rcx, [rbp+0C0h+arg_30]
0x1801788b4  call    ??$SafeCast@HI@Math@@YAHAEBI@Z; Math::SafeCast<int,uint>(uint const &)
0x1801788b9  mov     r15d, eax
0x1801788bc  lea     rcx, [rbp+0C0h+arg_60]
0x1801788c3  call    ??$SafeCast@HI@Math@@YAHAEBI@Z; Math::SafeCast<int,uint>(uint const &)
0x1801788c8  mov     r12d, eax
0x1801788cb  cmp     [rbp+0C0h+var_128], edi
0x1801788ce  jbe     loc_180178B56
0x1801788d4  mov     rcx, [rbp+0C0h+var_130]
0x1801788d8  lea     rax, [rbp+0C0h+var_140]
0x1801788dc  mov     [rsp+1C0h+var_178], rax
0x1801788e1  mov     [rsp+1C0h+var_180], rcx
0x1801788e6  mov     rax, [rbp+0C0h+var_120]
0x1801788ea  mov     [rsp+1C0h+var_188], rax
0x1801788ef  mov     [rsp+1C0h+var_190], r13
0x1801788f4  mov     [rsp+1C0h+var_198], rsi
0x1801788f9  mov     dword ptr [rsp+1C0h+var_1A0], r12d
0x1801788fe  mov     r9d, r15d
0x180178901  mov     r8, [rbp+0C0h+var_118]
0x180178905  mov     rdx, r14
0x180178908  xor     ecx, ecx
0x18017890a  call    cs:__imp_MsoScriptShape
0x180178910  mov     ebx, eax
0x180178912  cmp     eax, 8000000Ah
0x180178917  jnz     short loc_180178980
0x180178919  cmp     [rbp+0C0h+var_128], edi
0x18017891c  jbe     loc_1801789B4
0x180178922  mov     rbx, [rbp+0C0h+var_130]
0x180178926  lea     r8, [rbp+0C0h+var_B0]; struct tagLOGFONTW *
0x18017892a  mov     rdx, [rbp+0C0h+var_110]; struct GEL::ITypefaceList *
0x18017892e  lea     rcx, [rbp+0C0h+var_F8]; this
0x180178932  call    ??0SharedDeviceIC@GEL@@QEAA@AEBUITypefaceList@1@AEBUtagLOGFONTW@@@Z; GEL::SharedDeviceIC::SharedDeviceIC(GEL::ITypefaceList const &,tagLOGFONTW const &)
0x180178937  mov     rcx, [rax+8]
0x18017893b  lea     rax, [rbp+0C0h+var_140]
0x18017893f  mov     [rsp+1C0h+var_178], rax
0x180178944  mov     [rsp+1C0h+var_180], rbx
0x180178949  mov     rax, [rbp+0C0h+var_120]
0x18017894d  mov     [rsp+1C0h+var_188], rax
0x180178952  mov     [rsp+1C0h+var_190], r13
0x180178957  mov     [rsp+1C0h+var_198], rsi
0x18017895c  mov     dword ptr [rsp+1C0h+var_1A0], r12d
0x180178961  mov     r9d, r15d
0x180178964  mov     r8, [rbp+0C0h+var_118]
0x180178968  mov     rdx, r14
0x18017896b  mov     rcx, [rcx]
0x18017896e  call    cs:__imp_MsoScriptShape
0x180178974  mov     ebx, eax
0x180178976  mov     rcx, [rbp+0C0h+var_E8]; _Mtx_t
0x18017897a  call    cs:__imp__Mtx_unlock
0x180178980  mov     edx, 80040200h
0x180178985  mov     r8d, 3FFh
0x18017898b  test    ebx, ebx
0x18017898d  jnz     short loc_1801789C4
0x18017898f  test    [rsi], r8w
0x180178993  jz      loc_180178AF1
0x180178999  mov     eax, edi
0x18017899b  mov     rcx, r13
0x18017899e  cmp     eax, [rbp+0C0h+var_140]
0x1801789a1  jge     loc_180178AF1
0x1801789a7  cmp     [rcx], di
0x1801789aa  jz      short loc_1801789C2
0x1801789ac  inc     eax
0x1801789ae  add     rcx, 2
0x1801789b2  jmp     short loc_18017899E
0x1801789b4  xor     edx, edx
0x1801789b6  mov     ecx, 1E892496h
0x1801789bb  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1801789c1  nop
0x1801789c2  mov     ebx, edx
0x1801789c4  cmp     ebx, edx
0x1801789c6  jnz     loc_180178A99
0x1801789cc  movzx   eax, word ptr [rsi]
0x1801789cf  test    r8w, ax
0x1801789d3  jz      loc_180178AE4
0x1801789d9  mov     ecx, 0FC00h
0x1801789de  and     ax, cx
0x1801789e1  mov     [rsi], ax
0x1801789e4  cmp     [rbp+0C0h+var_128], edi
0x1801789e7  jbe     loc_180178AD2
0x1801789ed  mov     rax, [rbp+0C0h+var_130]
0x1801789f1  lea     rcx, [rbp+0C0h+var_140]
0x1801789f5  mov     [rsp+1C0h+var_178], rcx
0x1801789fa  mov     [rsp+1C0h+var_180], rax
0x1801789ff  mov     rax, [rbp+0C0h+var_120]
0x180178a03  mov     [rsp+1C0h+var_188], rax
0x180178a08  mov     [rsp+1C0h+var_190], r13
0x180178a0d  mov     [rsp+1C0h+var_198], rsi
0x180178a12  mov     dword ptr [rsp+1C0h+var_1A0], r12d
0x180178a17  mov     r9d, r15d
0x180178a1a  mov     r8, [rbp+0C0h+var_118]
0x180178a1e  mov     rdx, r14
0x180178a21  xor     ecx, ecx
0x180178a23  call    cs:__imp_MsoScriptShape
0x180178a29  mov     ebx, eax
0x180178a2b  cmp     eax, 8000000Ah
0x180178a30  jnz     short loc_180178A99
0x180178a32  cmp     [rbp+0C0h+var_128], edi
0x180178a35  jbe     loc_180178AC4
0x180178a3b  mov     rbx, [rbp+0C0h+var_130]
0x180178a3f  lea     r8, [rbp+0C0h+var_B0]; struct tagLOGFONTW *
0x180178a43  mov     rdx, [rbp+0C0h+var_110]; struct GEL::ITypefaceList *
0x180178a47  lea     rcx, [rbp+0C0h+var_F8]; this
0x180178a4b  call    ??0SharedDeviceIC@GEL@@QEAA@AEBUITypefaceList@1@AEBUtagLOGFONTW@@@Z; GEL::SharedDeviceIC::SharedDeviceIC(GEL::ITypefaceList const &,tagLOGFONTW const &)
0x180178a50  mov     rcx, [rax+8]
0x180178a54  lea     rax, [rbp+0C0h+var_140]
0x180178a58  mov     [rsp+1C0h+var_178], rax
0x180178a5d  mov     [rsp+1C0h+var_180], rbx
0x180178a62  mov     rax, [rbp+0C0h+var_120]
0x180178a66  mov     [rsp+1C0h+var_188], rax
0x180178a6b  mov     [rsp+1C0h+var_190], r13
0x180178a70  mov     [rsp+1C0h+var_198], rsi
0x180178a75  mov     dword ptr [rsp+1C0h+var_1A0], r12d
0x180178a7a  mov     r9d, r15d
0x180178a7d  mov     r8, [rbp+0C0h+var_118]
0x180178a81  mov     rdx, r14
0x180178a84  mov     rcx, [rcx]
0x180178a87  call    cs:__imp_MsoScriptShape
0x180178a8d  mov     ebx, eax
0x180178a8f  mov     rcx, [rbp+0C0h+var_E8]; _Mtx_t
0x180178a93  call    cs:__imp__Mtx_unlock
0x180178a99  cmp     ebx, 8007000Eh
0x180178a9f  jnz     short loc_180178AE0
0x180178aa1  mov     rcx, [rbp+0C0h+var_130]; void *
0x180178aa5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180178aaa  lea     rcx, [rbp+0C0h+var_D8]; this
0x180178aae  call    ??1CExclusiveAccess@Ofc@@QEAA@XZ; Ofc::CExclusiveAccess::~CExclusiveAccess(void)
0x180178ab3  lea     rcx, [rbp+0C0h+var_108]
0x180178ab7  call    cs:__imp_MsoScriptFreeCache
0x180178abd  xor     eax, eax
0x180178abf  jmp     loc_180178BD1
0x180178ac4  xor     edx, edx
0x180178ac6  mov     ecx, 1E892496h
0x180178acb  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x180178ad1  nop
0x180178ad2  xor     edx, edx
0x180178ad4  mov     ecx, 1E892496h
0x180178ad9  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x180178adf  nop
0x180178ae0  test    ebx, ebx
0x180178ae2  jns     short loc_180178AF1
0x180178ae4  mov     edx, 3566A3h; unsigned int
0x180178ae9  mov     ecx, ebx; int
0x180178aeb  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x180178af0  int     3; Trap to Debugger
0x180178af1  lea     rcx, [rbp+0C0h+var_140]
0x180178af5  call    ??$SafeCast@IH@Math@@YAIAEBH@Z; Math::SafeCast<uint,int>(int const &)
0x180178afa  mov     ebx, eax
0x180178afc  mov     rdx, [rbp+0C0h+var_130]
0x180178b00  test    eax, eax
0x180178b02  jz      short loc_180178B26
0x180178b04  mov     r8d, [rbp+0C0h+var_138]
0x180178b08  mov     r9, [rbp+0C0h+var_100]
0x180178b0c  cmp     edi, r8d
0x180178b0f  jnb     short loc_180178B26
0x180178b11  cmp     edi, [rbp+0C0h+var_128]
0x180178b14  jnb     short loc_180178B48
0x180178b16  mov     ecx, edi
0x180178b18  movzx   eax, word ptr [rdx+rcx*2]
0x180178b1c  mov     [r9+rcx*4], eax
0x180178b20  inc     edi
0x180178b22  cmp     edi, ebx
0x180178b24  jb      short loc_180178B0C
0x180178b26  mov     rcx, rdx; void *
0x180178b29  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180178b2e  lea     rcx, [rbp+0C0h+var_D8]; this
0x180178b32  call    ??1CExclusiveAccess@Ofc@@QEAA@XZ; Ofc::CExclusiveAccess::~CExclusiveAccess(void)
0x180178b37  lea     rcx, [rbp+0C0h+var_108]
0x180178b3b  call    cs:__imp_MsoScriptFreeCache
0x180178b41  mov     eax, ebx
0x180178b43  jmp     loc_180178BD1
0x180178b48  xor     edx, edx
0x180178b4a  mov     ecx, 1E892496h
0x180178b4f  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x180178b55  nop
0x180178b56  xor     edx, edx
0x180178b58  mov     ecx, 1E892496h
0x180178b5d  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x180178b63  nop
0x180178b64  mov     ecx, 3566A1h; unsigned int
  ... truncated ...
```
