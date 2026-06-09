# GEL::GdiTypeface::GetCharWidths(GEL::ITypefaceList const &,GEL::Font const &,wchar_t const *,uint,long *,uint)

- ea: `0x1800919f0`
- end: `0x1800920a6`
- name: `?GetCharWidths@GdiTypeface@GEL@@UEBAXAEBUITypefaceList@2@AEBUFont@2@PEB_WIPEAJI@Z`
- size: `1718`
- prototype: `void __usercall(GEL::GdiTypeface *__hidden this@<rcx>, const struct GEL::ITypefaceList *@<rdx>, const struct GEL::Font *@<r8>, const wchar_t *@<r9>, unsigned int, int *, unsigned int)`
- caller_count: `0`
- callee_count: `18`
- tags: ``

## callees

- `0x1800565ba`
- `0x1800578b0`
- `0x180057e70`
- `0x180076c98`
- `0x180090490`
- `0x1800904c8`
- `0x180091710`
- `0x1800919f0`
- `0x1800920b0`
- `0x1800923e0`
- `0x180092590`
- `0x1800926b4`
- `0x1800927e0`
- `0x180092ad0`
- `0x1800af160`
- `0x1800b059c`
- `0x1800e38d0`
- `0x180161450`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180091b93`
- `KERNEL32!GetCurrentThreadId` at `0x180091b93`
- `KERNEL32!MulDiv` at `0x180091c1e`
- `KERNEL32!MulDiv` at `0x180091def`
- `KERNEL32!MulDiv` at `0x180091c1e`
- `KERNEL32!MulDiv` at `0x180091def`
- `KERNEL32!WaitForSingleObjectEx` at `0x180092038`
- `KERNEL32!WaitForSingleObjectEx` at `0x180092038`
- `KERNEL32!ResetEvent` at `0x180092013`
- `KERNEL32!ResetEvent` at `0x180092013`
- `MSVCP140!_Mtx_unlock` at `0x180091d71`
- `MSVCP140!_Mtx_unlock` at `0x180091f0e`
- `MSVCP140!_Mtx_unlock` at `0x180091f80`
- `MSVCP140!_Mtx_unlock` at `0x180092023`
- `MSVCP140!_Mtx_unlock` at `0x180091d71`
- `MSVCP140!_Mtx_unlock` at `0x180091f0e`
- `MSVCP140!_Mtx_unlock` at `0x180091f80`
- `MSVCP140!_Mtx_unlock` at `0x180092023`
- `MSVCP140!_Mtx_lock` at `0x180091ba8`
- `MSVCP140!_Mtx_lock` at `0x180091ba8`
- `MSVCP140!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180091bbb`
- `MSVCP140!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180091e37`
- `MSVCP140!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180091bbb`
- `MSVCP140!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180091e37`
- `Mso98Win32Client!__imp_MsoGetTextExtentPointWEx` at `0x180091d65`
- `Mso98Win32Client!__imp_MsoGetTextExtentPointWEx` at `0x180091efb`
- `Mso98Win32Client!__imp_MsoGetTextExtentPointWEx` at `0x180091d65`
- `Mso98Win32Client!__imp_MsoGetTextExtentPointWEx` at `0x180091efb`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall GEL::GdiTypeface::GetCharWidths(
        GEL::GdiTypeface *this,
        const struct GEL::ITypefaceList *a2,
        const struct GEL::Font *a3,
        const wchar_t *a4,
        unsigned int a5,
        int *a6,
        unsigned int a7)
{
  const wchar_t *v7; // r14
  GEL::GdiTypeface *v9; // r13
  int *v10; // rsi
  unsigned int v11; // edi
  int v12; // r15d
  _QWORD *v13; // r8
  const void *v14; // rbx
  unsigned int v15; // r12d
  int v16; // edi
  int v17; // r15d
  int v18; // ebx
  bool (__fastcall *v19)(GEL::Typeface *__hidden); // rax
  int v21; // r14d
  _Mtx_t v22; // rbx
  DWORD CurrentThreadId; // r12d
  __int64 v24; // rdi
  int v25; // eax
  GEL::WidthCache *v26; // rbx
  GEL::WidthCache *v27; // rax
  GEL::WidthCache *v28; // r15
  GEL::WidthCache *v29; // rcx
  __int64 v30; // r14
  GEL::WidthCache *v31; // rcx
  GEL::WidthCache *v32; // rcx
  int WidthCache; // edi
  struct GEL::ITypefaceList *v34; // r15
  __int64 v35; // rax
  const wchar_t *v36; // r14
  int TextExtentPointWEx; // ebx
  unsigned int v38; // edx
  int v39; // ecx
  int i; // eax
  int v41; // edx
  int v42; // eax
  DWORD v43; // eax
  wchar_t v44; // cx
  unsigned __int16 v45; // dx
  __int64 v46; // rax
  unsigned __int64 v47; // rdx
  unsigned __int64 v48; // rax
  __int64 v49; // rax
  __int64 v50; // r12
  __int64 v51; // r13
  __int64 v52; // rdi
  __int64 v53; // r14
  int v54; // ecx
  GEL::WidthCache *v55; // rcx
  unsigned __int16 v56; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v57; // [rsp+58h] [rbp-A8h] BYREF
  int v58; // [rsp+60h] [rbp-A0h]
  unsigned int v59; // [rsp+64h] [rbp-9Ch]
  const wchar_t *v60; // [rsp+68h] [rbp-98h]
  int nNumerator; // [rsp+70h] [rbp-90h]
  _Mtx_t v62; // [rsp+78h] [rbp-88h] BYREF
  GEL::GdiTypeface *v63; // [rsp+80h] [rbp-80h]
  GEL::GdiTypeface *v64; // [rsp+88h] [rbp-78h]
  struct GEL::ITypefaceList *v65; // [rsp+90h] [rbp-70h]
  _BYTE v66[16]; // [rsp+98h] [rbp-68h] BYREF
  _Mtx_t v67; // [rsp+A8h] [rbp-58h]
  _Mtx_t v68; // [rsp+B0h] [rbp-50h]
  struct tagLOGFONTW v69; // [rsp+C0h] [rbp-40h] BYREF

  v7 = a4;
  v60 = a4;
  v65 = a2;
  v9 = this;
  v64 = this;
  v10 = a6;
  if ( HIBYTE(xmmword_180523DD0) || *((_BYTE *)a3 + 33) )
  {
    GEL::DWriteTypeface::GetCharWidths(this, a2, a3, a4, a5, a6, a7);
    return;
  }
  v11 = *((_DWORD *)a3 + 5);
  v59 = v11;
  v12 = Ofc::Round<long,float>(this);
  nNumerator = v12;
  v14 = (const void *)v13[3];
  if ( !*v13 || !a5 || a7 < a5 || (v11 & 0xFFFFFF00) != 0 )
  {
LABEL_20:
    Ofc::CInvalidParamException::ThrowTag(0x35668Fu);
    __debugbreak();
  }
  memset_0(&v69, 0, sizeof(v69));
  GEL::Typeface::GetLOGFONT(v9, &v69, v12, v11, v14, a2, 0, 0, 0, 0);
  v15 = 0;
  LODWORD(v57) = 0;
  while ( 1 )
  {
    v16 = -1;
    if ( !BYTE1(xmmword_180523DD0) )
      goto LABEL_47;
    v17 = -v69.lfHeight;
    v18 = v7[v15];
    v56 = v7[v15];
    v58 = -1;
    if ( *((_QWORD *)v9 + 14) <= 1u )
      goto LABEL_47;
    v19 = *(bool (__fastcall **)(GEL::Typeface *__hidden))(*(_QWORD *)v9 + 352LL);
    if ( !(v19 == GEL::Typeface::FIsFontInfoCachable ? GEL::Typeface::FIsFontInfoCachable(v9) : v19(v9)) )
      goto LABEL_47;
    v21 = v17 * v18 % 67;
    if ( v21 <= 0 )
      v21 = 0;
    v22 = Ofc::TSingleton<GEL::TypefaceAccessMgr>::s_pInstance;
    if ( (unsigned __int64)Ofc::TSingleton<GEL::TypefaceAccessMgr>::s_pInstance <= 1 )
    {
      Ofc::ThreadSafeInitPointerOnce<GEL::TypefaceAccessMgr *,Ofc::TSingletonFactory<GEL::TypefaceAccessMgr>>();
      v22 = Ofc::TSingleton<GEL::TypefaceAccessMgr>::s_pInstance;
    }
    v62 = v22;
    v63 = v9;
    CurrentThreadId = GetCurrentThreadId();
    v24 = 1;
    v68 = v22;
LABEL_18:
    if ( _Mtx_lock(v22) )
    {
      std::_Throw_Cpp_error(5);
      goto LABEL_20;
    }
    if ( *((_DWORD *)v22 + 19) == 0x7FFFFFFF )
      break;
    if ( (v24 & 0x3F) == 0 || *((_DWORD *)v22 + 22) > 8u )
      Ofc::CExclusiveAccessMgr2::CleanupOrphanedAccs(v22);
    v47 = *((_QWORD *)v22 + 10);
    v48 = v47 + 24LL * *((unsigned int *)v22 + 22);
    while ( 1 )
    {
      if ( v47 >= v48 )
      {
        if ( *((_DWORD *)v22 + 22) == 8 && *((_Mtx_t *)v22 + 10) == (_Mtx_t)((char *)v22 + 96) )
          Ofc::CArrayImpl::ConvertFixedToVarBuffer(
            (_Mtx_t)((char *)v22 + 80),
            0x18u,
            9u,
            (void (*)(unsigned __int8 *, unsigned __int8 *, unsigned int))Ofc::TMoveConstructRange<GEL::PANLINK,1>::Do);
        v49 = Ofc::CArrayImpl::NewTop<Ofc::CExclusiveAccessMgr2::AccData>((char *)v22 + 80);
        *(_QWORD *)v49 = v63;
        *(_QWORD *)(v49 + 8) = &v62;
        *(_DWORD *)(v49 + 16) = CurrentThreadId;
        goto LABEL_89;
      }
      if ( *(GEL::GdiTypeface **)v47 == v63 )
        break;
      v47 += 24LL;
    }
    if ( *(_DWORD *)(v47 + 16) != CurrentThreadId )
    {
      ResetEvent(*((HANDLE *)v22 + 36));
      _InterlockedIncrement((volatile signed __int32 *)v22 + 74);
      _Mtx_unlock(v22);
      WaitForSingleObjectEx(*((HANDLE *)v22 + 36), 0x32u, 0);
      _InterlockedDecrement((volatile signed __int32 *)v22 + 74);
      v24 = (unsigned int)(v24 + 1);
      goto LABEL_18;
    }
LABEL_89:
    _Mtx_unlock(v22);
    v50 = v21;
    v51 = *((_QWORD *)v9 + 14);
    v52 = *(_QWORD *)(v51 + 8LL * v21);
    if ( v52 )
    {
      v53 = 0;
      v54 = 1;
      v38 = v56;
      while ( 1 )
      {
        if ( *(_WORD *)v52 == v56 && *(_DWORD *)(v52 + 4) == v17 && *(_DWORD *)(v52 + 8) == v59 )
        {
          if ( v53 )
          {
            v26 = 0;
            v27 = *(GEL::WidthCache **)(v53 + 16);
            if ( v27 )
            {
              *(_QWORD *)(v53 + 16) = 0;
              v26 = v27;
              v27 = 0;
            }
            v28 = (GEL::WidthCache *)*((_QWORD *)v26 + 2);
            if ( v27 != v28 )
            {
              *((_QWORD *)v26 + 2) = 0;
              v29 = *(GEL::WidthCache **)(v53 + 16);
              if ( v29 )
                GEL::WidthCache::`scalar deleting destructor'(v29, v38);
              *(_QWORD *)(v53 + 16) = v28;
            }
            v30 = *(_QWORD *)(v51 + 8 * v50);
            if ( *((_QWORD *)v26 + 2) != v30 )
            {
              *(_QWORD *)(v51 + 8 * v50) = 0;
              v31 = (GEL::WidthCache *)*((_QWORD *)v26 + 2);
              if ( v31 )
                GEL::WidthCache::`scalar deleting destructor'(v31, v38);
              *((_QWORD *)v26 + 2) = v30;
            }
            v32 = *(GEL::WidthCache **)(v51 + 8 * v50);
            if ( v32 == v26 )
            {
              GEL::WidthCache::`scalar deleting destructor'(v26, v38);
            }
            else
            {
              if ( v32 )
                GEL::WidthCache::`scalar deleting destructor'(v32, v38);
              *(_QWORD *)(v51 + 8 * v50) = v26;
            }
          }
          v16 = *(_DWORD *)(v52 + 12);
          goto LABEL_45;
        }
        if ( !*(_QWORD *)(v52 + 16) )
          break;
        v53 = v52;
        v52 = *(_QWORD *)(v52 + 16);
        ++v54;
      }
      if ( v54 >= 19 )
      {
        v55 = *(GEL::WidthCache **)(v53 + 16);
        if ( v55 )
        {
          *(_QWORD *)(v53 + 16) = 0;
          GEL::WidthCache::`scalar deleting destructor'(v55, v38);
        }
      }
      v16 = v58;
LABEL_45:
      Ofc::CExclusiveAccess2::~CExclusiveAccess2((Ofc::CExclusiveAccess2 *)&v62);
    }
    else
    {
      Ofc::CExclusiveAccess2::~CExclusiveAccess2((Ofc::CExclusiveAccess2 *)&v62);
      v16 = -1;
    }
    v7 = v60;
    v9 = v64;
    v15 = v57;
LABEL_47:
    if ( v16 == -1 )
    {
      v57 = 0;
      WidthCache = 0;
      v34 = v65;
      v35 = GEL::SharedDeviceIC::SharedDeviceIC((GEL::SharedDeviceIC *)v66, v65, &v69);
      v36 = &v7[v15];
      TextExtentPointWEx = MsoGetTextExtentPointWEx(**(_QWORD **)(v35 + 8), v36, 1, &v57, 0, 4, 0);
      _Mtx_unlock(v67);
      if ( TextExtentPointWEx )
      {
        WidthCache = v57;
        if ( !(_DWORD)v57 )
        {
          if ( (v44 = *v36, v45 = 19968, *v36 >= 0x3400u) && v44 != 19968 && v44 <= 0x9FFFu
            || (unsigned __int16)(v44 - 10) <= 3u )
          {
            if ( v44 < 0x3400u )
              v45 = 105;
            v56 = v45;
            if ( !BYTE1(xmmword_180523DD0)
              || (WidthCache = GEL::Typeface::GetWidthCache(v9, v45, -v69.lfHeight, v59), WidthCache == -1) )
            {
              v46 = GEL::SharedDeviceIC::SharedDeviceIC((GEL::SharedDeviceIC *)v66, v34, &v69);
              WidthCache = 0;
              if ( (unsigned int)MsoGetTextExtentPointWEx(**(_QWORD **)(v46 + 8), &v56, 1, &v57, 0, 4, 0) )
                WidthCache = v57;
              _Mtx_unlock(v67);
            }
          }
        }
      }
      a6[v15] = WidthCache;
      if ( BYTE1(xmmword_180523DD0) )
        GEL::Typeface::CacheWidth(v9, v60[v15], -v69.lfHeight, v59, WidthCache);
    }
    else
    {
      a6[v15] = v16;
    }
    LODWORD(v57) = ++v15;
    if ( v15 >= a5 )
    {
      v17 = nNumerator;
      if ( v69.lfHeight != -nNumerator )
      {
        LODWORD(v22) = -v69.lfHeight;
        v24 = a5;
        if ( nNumerator )
        {
          v21 = -2147483647;
          CurrentThreadId = 0;
          goto LABEL_56;
        }
        do
        {
          v25 = *v10;
          if ( (_DWORD)v22 )
            v25 = MulDiv(v25, 0, (int)v22);
          *v10++ = v25;
          --v24;
        }
        while ( v24 );
      }
      return;
    }
    v7 = v60;
  }
  *((_DWORD *)v22 + 19) = 2147483646;
  std::_Throw_Cpp_error(6);
LABEL_67:
  v41 = CurrentThreadId;
  if ( v17 < 0 )
    v41 = v21;
LABEL_62:
  if ( v39 <= 0 )
  {
    v43 = CurrentThreadId;
    LOBYTE(v43) = v39 >= 0;
    v42 = v43 - 1;
  }
  else
  {
    v42 = 1;
  }
  for ( i = v41 * v42; ; i = MulDiv(v39, v17, (int)v22) )
  {
    *v10++ = i;
    if ( !--v24 )
      break;
LABEL_56:
    v39 = *v10;
    if ( !(_DWORD)v22 )
    {
      if ( v17 <= 0 )
        goto LABEL_67;
      v41 = 0x7FFFFFFF;
      goto LABEL_62;
    }
  }
}

```

## disassembly

```asm
0x1800919f0  push    rbp
0x1800919f2  push    rbx
0x1800919f3  push    rsi
0x1800919f4  push    rdi
0x1800919f5  push    r12
0x1800919f7  push    r13
0x1800919f9  push    r14
0x1800919fb  push    r15
0x1800919fd  lea     rbp, [rsp-38h]
0x180091a02  sub     rsp, 138h
0x180091a09  mov     rax, cs:__security_cookie
0x180091a10  xor     rax, rsp
0x180091a13  mov     [rbp+70h+var_50], rax
0x180091a17  mov     r14, r9
0x180091a1a  mov     [rsp+170h+var_108], r9
0x180091a1f  mov     r12, rdx
0x180091a22  mov     [rbp+70h+var_E0], rdx
0x180091a26  mov     r13, rcx
0x180091a29  mov     [rbp+70h+var_E8], rcx
0x180091a2d  mov     rsi, [rbp+70h+arg_28]
0x180091a34  cmp     byte ptr cs:xmmword_180523DD0+0Fh, 0
0x180091a3b  jnz     loc_180091BCD
0x180091a41  cmp     byte ptr [r8+21h], 0
0x180091a46  jnz     loc_180091BCD
0x180091a4c  mov     edi, [r8+14h]
0x180091a50  mov     [rsp+170h+var_10C], edi
0x180091a54  movss   xmm0, dword ptr [r8+10h]
0x180091a5a  call    ??$Round@JM@Ofc@@YAJM@Z; Ofc::Round<long,float>(float)
0x180091a5f  mov     r15d, eax
0x180091a62  mov     [rsp+170h+nNumerator], eax
0x180091a66  mov     rbx, [r8+18h]
0x180091a6a  cmp     qword ptr [r8], 0
0x180091a6e  jz      loc_180091BC2
0x180091a74  mov     eax, [rbp+70h+arg_20]
0x180091a7a  test    eax, eax
0x180091a7c  jz      loc_180091BC2
0x180091a82  cmp     [rbp+70h+arg_30], eax
0x180091a88  jb      loc_180091BC2
0x180091a8e  test    edi, 0FFFFFF00h
0x180091a94  jnz     loc_180091BC2
0x180091a9a  xor     edx, edx; Val
0x180091a9c  mov     r8d, 5Ch ; '\'; Size
0x180091aa2  lea     rcx, [rbp+70h+var_B0]; void *
0x180091aa6  call    memset_0
0x180091aab  mov     [rsp+170h+var_128], 0; bool
0x180091ab0  xor     eax, eax
0x180091ab2  mov     [rsp+170h+var_130], rax; unsigned __int16 *
0x180091ab7  mov     [rsp+170h+var_138], rax; unsigned __int8 *
0x180091abc  mov     [rsp+170h+var_140], rax; unsigned __int8 *
0x180091ac1  mov     [rsp+170h+var_148], r12; struct GEL::ITypefaceList *
0x180091ac6  mov     [rsp+170h+var_150], rbx; void *
0x180091acb  mov     r9d, edi; unsigned int
0x180091ace  mov     r8d, r15d; int
0x180091ad1  lea     rdx, [rbp+70h+var_B0]; struct tagLOGFONTW *
0x180091ad5  mov     rcx, r13; this
0x180091ad8  call    ?GetLOGFONT@Typeface@GEL@@QEBAXAEAUtagLOGFONTW@@JIPEBXAEBUITypefaceList@2@PEBE3PEBG_N@Z; GEL::Typeface::GetLOGFONT(tagLOGFONTW &,long,uint,void const *,GEL::ITypefaceList const &,uchar const *,uchar const *,ushort const *,bool)
0x180091add  xor     eax, eax
0x180091adf  mov     r12d, eax
0x180091ae2  mov     dword ptr [rsp+170h+var_118], eax
0x180091ae6  lea     rcx, ?FIsFontInfoCachable@Typeface@GEL@@UEBA_NXZ; GEL::Typeface::FIsFontInfoCachable(void)
0x180091aed  mov     edi, 0FFFFFFFFh
0x180091af2  cmp     byte ptr cs:xmmword_180523DD0+1, 0
0x180091af9  jz      loc_180091CF0
0x180091aff  mov     r15d, [rbp+70h+var_B0.lfHeight]
0x180091b03  neg     r15d
0x180091b06  mov     eax, r12d
0x180091b09  movzx   ebx, word ptr [r14+rax*2]
0x180091b0e  mov     [rsp+170h+var_120], bx
0x180091b13  mov     [rsp+170h+var_110], edi
0x180091b17  cmp     qword ptr [r13+70h], 1
0x180091b1c  jbe     loc_180091CEE
0x180091b22  mov     rax, [r13+0]
0x180091b26  mov     rax, [rax+160h]
0x180091b2d  cmp     rax, rcx
0x180091b30  mov     rcx, r13; this
0x180091b33  jnz     loc_180092090
0x180091b39  call    ?FIsFontInfoCachable@Typeface@GEL@@UEBA_NXZ; GEL::Typeface::FIsFontInfoCachable(void)
0x180091b3e  test    al, al
0x180091b40  jz      loc_180091CEE
0x180091b46  mov     r14d, ebx
0x180091b49  imul    r14d, r15d
0x180091b4d  mov     eax, 7A44C6Bh
0x180091b52  imul    r14d
0x180091b55  sar     edx, 1
0x180091b57  mov     eax, edx
0x180091b59  shr     eax, 1Fh
0x180091b5c  add     edx, eax
0x180091b5e  imul    eax, edx, 43h ; 'C'
0x180091b61  sub     r14d, eax
0x180091b64  test    r14d, r14d
0x180091b67  mov     r12d, 0
0x180091b6d  cmovle  r14d, r12d
0x180091b71  mov     rbx, cs:?s_pInstance@?$TSingleton@VTypefaceAccessMgr@GEL@@@Ofc@@0PEAVTypefaceAccessMgr@GEL@@EA; GEL::TypefaceAccessMgr * Ofc::TSingleton<GEL::TypefaceAccessMgr>::s_pInstance
0x180091b78  cmp     rbx, 1
0x180091b7c  ja      short loc_180091B8A
0x180091b7e  call    ??$ThreadSafeInitPointerOnce@PEAVTypefaceAccessMgr@GEL@@V?$TSingletonFactory@VTypefaceAccessMgr@GEL@@@Ofc@@@Ofc@@YAXPECREAVTypefaceAccessMgr@GEL@@@Z; Ofc::ThreadSafeInitPointerOnce<GEL::TypefaceAccessMgr *,Ofc::TSingletonFactory<GEL::TypefaceAccessMgr>>(GEL::TypefaceAccessMgr * volatile *)
0x180091b83  mov     rbx, cs:?s_pInstance@?$TSingleton@VTypefaceAccessMgr@GEL@@@Ofc@@0PEAVTypefaceAccessMgr@GEL@@EA; GEL::TypefaceAccessMgr * Ofc::TSingleton<GEL::TypefaceAccessMgr>::s_pInstance
0x180091b8a  mov     [rsp+170h+var_F8], rbx
0x180091b8f  mov     [rbp+70h+var_F0], r13
0x180091b93  call    cs:__imp_GetCurrentThreadId
0x180091b99  mov     r12d, eax
0x180091b9c  mov     edi, 1
0x180091ba1  mov     [rbp+70h+var_C0], rbx
0x180091ba5  mov     rcx, rbx; _Mtx_t
0x180091ba8  call    cs:__imp__Mtx_lock
0x180091bae  test    eax, eax
0x180091bb0  jz      loc_180091E1E
0x180091bb6  mov     ecx, 5
0x180091bbb  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180091bc1  nop
0x180091bc2  mov     ecx, 35668Fh; unsigned int
0x180091bc7  call    ?ThrowTag@CInvalidParamException@Ofc@@SAXK@Z; Ofc::CInvalidParamException::ThrowTag(ulong)
0x180091bcc  int     3; Trap to Debugger
0x180091bcd  mov     eax, [rbp+70h+arg_30]
0x180091bd3  mov     dword ptr [rsp+170h+var_140], eax; unsigned int
0x180091bd7  mov     [rsp+170h+var_148], rsi; int *
0x180091bdc  mov     eax, [rbp+70h+arg_20]
0x180091be2  mov     dword ptr [rsp+170h+var_150], eax; unsigned int
0x180091be6  call    ?GetCharWidths@DWriteTypeface@GEL@@UEBAXAEBUITypefaceList@2@AEBUFont@2@PEB_WIPEAJI@Z; GEL::DWriteTypeface::GetCharWidths(GEL::ITypefaceList const &,GEL::Font const &,wchar_t const *,uint,long *,uint)
0x180091beb  jmp     short loc_180091C30
0x180091bed  mov     r15d, [rsp+170h+nNumerator]
0x180091bf2  mov     eax, r15d
0x180091bf5  neg     eax
0x180091bf7  mov     ebx, [rbp+70h+var_B0.lfHeight]
0x180091bfa  cmp     ebx, eax
0x180091bfc  jz      short loc_180091C30
0x180091bfe  neg     ebx
0x180091c00  mov     rdi, rcx
0x180091c03  test    r15d, r15d
0x180091c06  jnz     loc_180091DDA
0x180091c0c  nop     dword ptr [rax]
0x180091c0f  nop
0x180091c10  mov     eax, [rsi]
0x180091c12  test    ebx, ebx
0x180091c14  jz      short loc_180091C24
0x180091c16  mov     r8d, ebx; nDenominator
0x180091c19  mov     edx, r15d; nNumerator
0x180091c1c  mov     ecx, eax; nNumber
0x180091c1e  call    cs:__imp_MulDiv
0x180091c24  mov     [rsi], eax
0x180091c26  add     rsi, 4
0x180091c2a  sub     rdi, 1
0x180091c2e  jnz     short loc_180091C10
0x180091c30  mov     rcx, [rbp+70h+var_50]
0x180091c34  xor     rcx, rsp; StackCookie
0x180091c37  call    __security_check_cookie
0x180091c3c  add     rsp, 138h
0x180091c43  pop     r15
0x180091c45  pop     r14
0x180091c47  pop     r13
0x180091c49  pop     r12
0x180091c4b  pop     rdi
0x180091c4c  pop     rsi
0x180091c4d  pop     rbx
0x180091c4e  pop     rbp
0x180091c4f  retn
0x180091c50  mov     eax, [rsp+170h+var_10C]
0x180091c54  cmp     [rdi+8], eax
0x180091c57  jnz     loc_180091FB6
0x180091c5d  test    r14, r14
0x180091c60  jz      short loc_180091CD3
0x180091c62  mov     rbx, r8
0x180091c65  mov     rax, [r14+10h]
0x180091c69  test    rax, rax
0x180091c6c  jz      short loc_180091C78
0x180091c6e  mov     [r14+10h], r8
0x180091c72  mov     rbx, rax
0x180091c75  mov     rax, r8
0x180091c78  mov     r15, [rbx+10h]
0x180091c7c  cmp     rax, r15
0x180091c7f  jz      short loc_180091C96
0x180091c81  mov     [rbx+10h], r8
0x180091c85  mov     rcx, [r14+10h]; this
0x180091c89  test    rcx, rcx
0x180091c8c  jnz     loc_180091DC3
0x180091c92  mov     [r14+10h], r15
0x180091c96  mov     r14, [r13+r12*8+0]
0x180091c9b  cmp     [rbx+10h], r14
0x180091c9f  jz      short loc_180091CB7
0x180091ca1  mov     [r13+r12*8+0], r8
0x180091ca6  mov     rcx, [rbx+10h]; this
0x180091caa  test    rcx, rcx
0x180091cad  jnz     loc_180091DD0
0x180091cb3  mov     [rbx+10h], r14
0x180091cb7  mov     rcx, [r13+r12*8+0]; this
0x180091cbc  cmp     rcx, rbx
0x180091cbf  jz      loc_180091F19
0x180091cc5  test    rcx, rcx
0x180091cc8  jnz     loc_18009209B
0x180091cce  mov     [r13+r12*8+0], rbx
0x180091cd3  mov     edi, [rdi+0Ch]
0x180091cd6  lea     rcx, [rsp+170h+var_F8]; this
0x180091cdb  call    ??1CExclusiveAccess2@Ofc@@QEAA@XZ; Ofc::CExclusiveAccess2::~CExclusiveAccess2(void)
0x180091ce0  mov     r14, [rsp+170h+var_108]
0x180091ce5  mov     r13, [rbp+70h+var_E8]
0x180091ce9  mov     r12d, dword ptr [rsp+170h+var_118]
0x180091cee  xor     eax, eax
0x180091cf0  mov     ebx, r12d
0x180091cf3  cmp     edi, 0FFFFFFFFh
0x180091cf6  jz      short loc_180091D1E
0x180091cf8  mov     [rsi+rbx*4], edi
0x180091cfb  inc     r12d
0x180091cfe  mov     dword ptr [rsp+170h+var_118], r12d
0x180091d03  mov     ecx, [rbp+70h+arg_20]
0x180091d09  cmp     r12d, ecx
0x180091d0c  jnb     loc_180091BED
0x180091d12  mov     r14, [rsp+170h+var_108]
0x180091d17  xor     eax, eax
0x180091d19  jmp     loc_180091AE6
0x180091d1e  mov     [rsp+170h+var_118], rax
0x180091d23  mov     edi, eax
0x180091d25  lea     r8, [rbp+70h+var_B0]; struct tagLOGFONTW *
0x180091d29  mov     r15, [rbp+70h+var_E0]
0x180091d2d  mov     rdx, r15; struct GEL::ITypefaceList *
0x180091d30  lea     rcx, [rbp+70h+var_D8]; this
0x180091d34  call    ??0SharedDeviceIC@GEL@@QEAA@AEBUITypefaceList@1@AEBUtagLOGFONTW@@@Z; GEL::SharedDeviceIC::SharedDeviceIC(GEL::ITypefaceList const &,tagLOGFONTW const &)
0x180091d39  mov     rcx, [rax+8]
0x180091d3d  lea     r14, [r14+rbx*2]
0x180091d41  xor     eax, eax
0x180091d43  mov     [rsp+170h+var_140], rax
0x180091d48  mov     dword ptr [rsp+170h+var_148], 4
0x180091d50  mov     dword ptr [rsp+170h+var_150], eax
0x180091d54  lea     r9, [rsp+170h+var_118]
0x180091d59  mov     r8d, 1
0x180091d5f  mov     rdx, r14
0x180091d62  mov     rcx, [rcx]
0x180091d65  call    cs:__imp_MsoGetTextExtentPointWEx
0x180091d6b  mov     ebx, eax
0x180091d6d  mov     rcx, [rbp+70h+var_C8]; _Mtx_t
0x180091d71  call    cs:__imp__Mtx_unlock
0x180091d77  test    ebx, ebx
0x180091d79  jz      short loc_180091D87
0x180091d7b  mov     edi, dword ptr [rsp+170h+var_118]
0x180091d7f  test    edi, edi
0x180091d81  jz      loc_180091E56
0x180091d87  mov     eax, r12d
0x180091d8a  mov     [rsi+rax*4], edi
0x180091d8d  cmp     byte ptr cs:xmmword_180523DD0+1, 0
0x180091d94  jz      loc_180091CFB
0x180091d9a  mov     r8d, [rbp+70h+var_B0.lfHeight]
0x180091d9e  neg     r8d; int
0x180091da1  mov     edx, r12d
0x180091da4  mov     dword ptr [rsp+170h+var_150], edi; int
0x180091da8  mov     r9d, [rsp+170h+var_10C]; unsigned int
0x180091dad  mov     rax, [rsp+170h+var_108]
0x180091db2  movzx   edx, word ptr [rax+rdx*2]; wchar_t
0x180091db6  mov     rcx, r13; this
0x180091db9  call    ?CacheWidth@Typeface@GEL@@QEBAX_WHIJ@Z; GEL::Typeface::CacheWidth(wchar_t,int,uint,long)
0x180091dbe  jmp     loc_180091CFB
0x180091dc3  call    ??_GWidthCache@GEL@@QEAAPEAXI@Z; GEL::WidthCache::`scalar deleting destructor'(uint)
0x180091dc8  xor     r8d, r8d
0x180091dcb  jmp     loc_180091C92
0x180091dd0  call    ??_GWidthCache@GEL@@QEAAPEAXI@Z; GEL::WidthCache::`scalar deleting destructor'(uint)
0x180091dd5  jmp     loc_180091CB3
0x180091dda  mov     r14d, 80000001h
0x180091de0  xor     r12d, r12d
0x180091de3  mov     ecx, [rsi]; nNumber
0x180091de5  test    ebx, ebx
0x180091de7  jz      short loc_180091E06
0x180091de9  mov     r8d, ebx; nDenominator
0x180091dec  mov     edx, r15d; nNumerator
0x180091def  call    cs:__imp_MulDiv
0x180091df5  mov     [rsi], eax
0x180091df7  add     rsi, 4
0x180091dfb  sub     rdi, 1
0x180091dff  jnz     short loc_180091DE3
0x180091e01  jmp     loc_180091C30
0x180091e06  test    r15d, r15d
0x180091e09  jle     short loc_180091E3E
0x180091e0b  mov     edx, 7FFFFFFFh
0x180091e10  test    ecx, ecx
0x180091e12  jle     short loc_180091E4A
0x180091e14  mov     eax, 1
0x180091e19  imul    eax, edx
0x180091e1c  jmp     short loc_180091DF5
0x180091e1e  cmp     dword ptr [rbx+4Ch], 7FFFFFFFh
0x180091e25  jnz     loc_180091F26
0x180091e2b  mov     dword ptr [rbx+4Ch], 7FFFFFFEh
0x180091e32  mov     ecx, 6
0x180091e37  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180091e3d  nop
0x180091e3e  mov     edx, r12d
0x180091e41  test    r15d, r15d
0x180091e44  cmovs   edx, r14d
0x180091e48  jmp     short loc_180091E10
0x180091e4a  mov     eax, r12d
0x180091e4d  test    ecx, ecx
0x180091e4f  setns   al
0x180091e52  dec     eax
0x180091e54  jmp     short loc_180091E19
0x180091e56  movzx   ecx, word ptr [r14]
0x180091e5a  mov     edx, 4E00h
0x180091e5f  mov     r8d, 3400h
0x180091e65  cmp     r8w, cx
0x180091e69  ja      short loc_180091E7A
0x180091e6b  cmp     cx, dx
0x180091e6e  jz      short loc_180091E7A
0x180091e70  mov     eax, 9FFFh
0x180091e75  cmp     cx, ax
0x180091e78  jbe     short loc_180091E87
  ... truncated ...
```
