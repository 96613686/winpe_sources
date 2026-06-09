# GEL::GdiTypeface::GetCharWidths(GEL::ITypefaceList const &,GEL::Font const &,wchar_t const *,uint,long *,uint)

- ea: `0x180077770`
- end: `0x180077e43`
- name: `?GetCharWidths@GdiTypeface@GEL@@UEBAXAEBUITypefaceList@2@AEBUFont@2@PEB_WIPEAJI@Z`
- size: `1747`
- prototype: `void __usercall(GEL::GdiTypeface *__hidden this@<rcx>, const struct GEL::ITypefaceList *@<rdx>, const struct GEL::Font *@<r8>, const wchar_t *@<r9>, unsigned int, int *, unsigned int)`
- caller_count: `0`
- callee_count: `18`
- tags: ``

## callees

- `0x180055b26`
- `0x180056ee0`
- `0x1800573f0`
- `0x1800774c0`
- `0x180077770`
- `0x180077e50`
- `0x180078178`
- `0x180078320`
- `0x180078444`
- `0x180078570`
- `0x18007877c`
- `0x1800795e4`
- `0x180079d04`
- `0x18009aae0`
- `0x18009c46c`
- `0x1800bd910`
- `0x1800dc27c`
- `0x18015ee1c`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180077913`
- `KERNEL32!GetCurrentThreadId` at `0x180077913`
- `KERNEL32!MulDiv` at `0x180077a5e`
- `KERNEL32!MulDiv` at `0x180077b8c`
- `KERNEL32!MulDiv` at `0x180077a5e`
- `KERNEL32!MulDiv` at `0x180077b8c`
- `KERNEL32!WaitForSingleObjectEx` at `0x180077de8`
- `KERNEL32!WaitForSingleObjectEx` at `0x180077de8`
- `KERNEL32!ResetEvent` at `0x180077dc3`
- `KERNEL32!ResetEvent` at `0x180077dc3`
- `MSVCP140!_Mtx_unlock` at `0x180077afa`
- `MSVCP140!_Mtx_unlock` at `0x180077cab`
- `MSVCP140!_Mtx_unlock` at `0x180077d27`
- `MSVCP140!_Mtx_unlock` at `0x180077dd3`
- `MSVCP140!_Mtx_unlock` at `0x180077afa`
- `MSVCP140!_Mtx_unlock` at `0x180077cab`
- `MSVCP140!_Mtx_unlock` at `0x180077d27`
- `MSVCP140!_Mtx_unlock` at `0x180077dd3`
- `MSVCP140!_Mtx_lock` at `0x180077928`
- `MSVCP140!_Mtx_lock` at `0x180077928`
- `MSVCP140!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18007793b`
- `MSVCP140!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180077bd4`
- `MSVCP140!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18007793b`
- `MSVCP140!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180077bd4`
- `Mso98Win32Client!__imp_MsoGetTextExtentPointWEx` at `0x180077aee`
- `Mso98Win32Client!__imp_MsoGetTextExtentPointWEx` at `0x180077c98`
- `Mso98Win32Client!__imp_MsoGetTextExtentPointWEx` at `0x180077aee`
- `Mso98Win32Client!__imp_MsoGetTextExtentPointWEx` at `0x180077c98`

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
  unsigned __int64 v7; // r14
  const struct GEL::ITypefaceList *CurrentThreadId; // r12
  GEL::GdiTypeface *v9; // r13
  int *v10; // rsi
  __int64 v11; // rdi
  int v12; // r15d
  _QWORD *v13; // r8
  const void *v14; // rbx
  unsigned int v15; // r12d
  int v16; // edi
  int v17; // ebx
  bool (__fastcall *v18)(GEL::Typeface *__hidden); // rax
  _Mtx_t v20; // rbx
  unsigned int v21; // edx
  int v22; // ecx
  GEL::WidthCache *v23; // r8
  GEL::WidthCache *v24; // rbx
  GEL::WidthCache *v25; // rax
  GEL::WidthCache *v26; // r15
  GEL::WidthCache *v27; // rcx
  __int64 v28; // r14
  GEL::WidthCache *v29; // rcx
  GEL::WidthCache *v30; // rcx
  int v31; // eax
  int WidthCache; // edi
  struct GEL::ITypefaceList *v33; // r15
  __int64 v34; // rax
  const wchar_t *v35; // r14
  int TextExtentPointWEx; // ebx
  int v37; // ecx
  int v38; // eax
  int v39; // edx
  int v40; // eax
  int v41; // eax
  wchar_t v42; // cx
  unsigned __int16 v43; // dx
  __int64 v44; // rax
  unsigned __int64 v45; // rdx
  unsigned __int64 v46; // rax
  __int64 v47; // rax
  GEL::WidthCache *v48; // rcx
  unsigned __int16 v49; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v50; // [rsp+58h] [rbp-A8h] BYREF
  int v51; // [rsp+60h] [rbp-A0h]
  unsigned int v52; // [rsp+64h] [rbp-9Ch]
  const wchar_t *v53; // [rsp+68h] [rbp-98h]
  int nNumerator; // [rsp+70h] [rbp-90h]
  _Mtx_t v55; // [rsp+78h] [rbp-88h] BYREF
  GEL::GdiTypeface *v56; // [rsp+80h] [rbp-80h]
  GEL::GdiTypeface *v57; // [rsp+88h] [rbp-78h]
  struct GEL::ITypefaceList *v58; // [rsp+90h] [rbp-70h]
  _BYTE v59[16]; // [rsp+98h] [rbp-68h] BYREF
  _Mtx_t v60; // [rsp+A8h] [rbp-58h]
  _Mtx_t v61; // [rsp+B0h] [rbp-50h]
  struct tagLOGFONTW v62; // [rsp+C0h] [rbp-40h] BYREF

  v7 = (unsigned __int64)a4;
  v53 = a4;
  CurrentThreadId = a2;
  v58 = a2;
  v9 = this;
  v57 = this;
  v10 = a6;
  if ( HIBYTE(xmmword_18051FD50) || *((_BYTE *)a3 + 33) )
  {
    GEL::DWriteTypeface::GetCharWidths(this, a2, a3, a4, a5, a6, a7);
  }
  else
  {
    v11 = *((unsigned int *)a3 + 5);
    v52 = *((_DWORD *)a3 + 5);
    v12 = Ofc::Round<long,float>(this);
    nNumerator = v12;
    v14 = (const void *)v13[3];
    if ( *v13 && a5 && a7 >= a5 && (v11 & 0xFFFFFF00) == 0 )
    {
      memset_0(&v62, 0, sizeof(v62));
      GEL::Typeface::GetLOGFONT(v9, &v62, v12, v11, v14, CurrentThreadId, 0, 0, 0, 0);
      v15 = 0;
      LODWORD(v50) = 0;
      goto LABEL_8;
    }
LABEL_20:
    Ofc::CInvalidParamException::ThrowTag(0x35668Fu);
LABEL_21:
    if ( *(_DWORD *)(v11 + 8) == v52 )
    {
      if ( v7 )
      {
        v24 = v23;
        v25 = *(GEL::WidthCache **)(v7 + 16);
        if ( v25 )
        {
          *(_QWORD *)(v7 + 16) = v23;
          v24 = v25;
          v25 = v23;
        }
        v26 = (GEL::WidthCache *)*((_QWORD *)v24 + 2);
        if ( v25 != v26 )
        {
          *((_QWORD *)v24 + 2) = v23;
          v27 = *(GEL::WidthCache **)(v7 + 16);
          if ( v27 )
          {
            GEL::WidthCache::`scalar deleting destructor'(v27, v21);
            v23 = 0;
          }
          *(_QWORD *)(v7 + 16) = v26;
        }
        v28 = *((_QWORD *)v9 + (_QWORD)CurrentThreadId);
        if ( *((_QWORD *)v24 + 2) != v28 )
        {
          *((_QWORD *)v9 + (_QWORD)CurrentThreadId) = v23;
          v29 = (GEL::WidthCache *)*((_QWORD *)v24 + 2);
          if ( v29 )
            GEL::WidthCache::`scalar deleting destructor'(v29, v21);
          *((_QWORD *)v24 + 2) = v28;
        }
        v30 = (GEL::WidthCache *)*((_QWORD *)v9 + (_QWORD)CurrentThreadId);
        if ( v30 == v24 )
        {
          GEL::WidthCache::`scalar deleting destructor'(v24, v21);
        }
        else
        {
          if ( v30 )
            GEL::WidthCache::`scalar deleting destructor'(v30, v21);
          *((_QWORD *)v9 + (_QWORD)CurrentThreadId) = v24;
        }
      }
      v16 = *(_DWORD *)(v11 + 12);
    }
    else
    {
      while ( *(_QWORD *)(v11 + 16) )
      {
        v7 = v11;
        v11 = *(_QWORD *)(v11 + 16);
        ++v22;
LABEL_91:
        if ( *(_WORD *)v11 == (_WORD)v21 && *(_DWORD *)(v11 + 4) == v12 )
          goto LABEL_21;
      }
      if ( v22 >= 19 )
      {
        v48 = *(GEL::WidthCache **)(v7 + 16);
        if ( v48 )
        {
          *(_QWORD *)(v7 + 16) = v23;
          GEL::WidthCache::`scalar deleting destructor'(v48, v21);
        }
      }
      v16 = v51;
    }
    Ofc::CExclusiveAccess2::~CExclusiveAccess2((Ofc::CExclusiveAccess2 *)&v55);
LABEL_39:
    v7 = (unsigned __int64)v53;
    v9 = v57;
    v15 = v50;
    while ( 1 )
    {
      if ( v16 == -1 )
      {
        v50 = 0;
        WidthCache = 0;
        v33 = v58;
        v34 = GEL::SharedDeviceIC::SharedDeviceIC((GEL::SharedDeviceIC *)v59, v58, &v62);
        v35 = (const wchar_t *)(v7 + 2LL * v15);
        TextExtentPointWEx = MsoGetTextExtentPointWEx(**(_QWORD **)(v34 + 8), v35, 1, &v50, 0, 4, 0);
        _Mtx_unlock(v60);
        if ( TextExtentPointWEx )
        {
          WidthCache = v50;
          if ( !(_DWORD)v50 )
          {
            if ( (v42 = *v35, v43 = 19968, *v35 != 19968) && v42 >= 0x3400u && v42 <= 0x9FFFu
              || (unsigned __int16)(v42 - 10) <= 3u )
            {
              if ( v42 < 0x3400u )
                v43 = 105;
              v49 = v43;
              if ( !BYTE1(xmmword_18051FD50)
                || (WidthCache = GEL::Typeface::GetWidthCache(v9, v43, -v62.lfHeight, v52), WidthCache == -1) )
              {
                v44 = GEL::SharedDeviceIC::SharedDeviceIC((GEL::SharedDeviceIC *)v59, v33, &v62);
                WidthCache = 0;
                if ( (unsigned int)MsoGetTextExtentPointWEx(**(_QWORD **)(v44 + 8), &v49, 1, &v50, 0, 4, 0) )
                  WidthCache = v50;
                _Mtx_unlock(v60);
              }
            }
          }
        }
        a6[v15] = WidthCache;
        if ( BYTE1(xmmword_18051FD50) )
          GEL::Typeface::CacheWidth(v9, v53[v15], -v62.lfHeight, v52, WidthCache);
      }
      else
      {
        a6[v15] = v16;
      }
      LODWORD(v50) = ++v15;
      if ( v15 >= a5 )
        break;
      v7 = (unsigned __int64)v53;
LABEL_8:
      v16 = -1;
      if ( BYTE1(xmmword_18051FD50) )
      {
        v12 = -v62.lfHeight;
        v17 = *(unsigned __int16 *)(v7 + 2LL * v15);
        v49 = *(_WORD *)(v7 + 2LL * v15);
        v51 = -1;
        if ( *((_QWORD *)v9 + 14) > 1u )
        {
          v18 = *(bool (__fastcall **)(GEL::Typeface *__hidden))(*(_QWORD *)v9 + 352LL);
          if ( v18 == GEL::Typeface::FIsFontInfoCachable ? GEL::Typeface::FIsFontInfoCachable(v9) : v18(v9) )
          {
            v7 = (unsigned int)(v12 * v17 % 67);
            if ( v12 * v17 % 67 <= 0 )
              v7 = 0;
            v20 = Ofc::TSingleton<GEL::TypefaceAccessMgr>::s_pInstance;
            if ( (unsigned __int64)Ofc::TSingleton<GEL::TypefaceAccessMgr>::s_pInstance <= 1 )
            {
              Ofc::ThreadSafeInitPointerOnce<GEL::TypefaceAccessMgr *,Ofc::TSingletonFactory<GEL::TypefaceAccessMgr>>();
              v20 = Ofc::TSingleton<GEL::TypefaceAccessMgr>::s_pInstance;
            }
            v55 = v20;
            v56 = v9;
            CurrentThreadId = (const struct GEL::ITypefaceList *)GetCurrentThreadId();
            v11 = 1;
            v61 = v20;
            while ( 2 )
            {
              if ( _Mtx_lock(v20) )
              {
                std::_Throw_Cpp_error(5);
                goto LABEL_20;
              }
              if ( *((_DWORD *)v20 + 19) == 0x7FFFFFFF )
              {
                *((_DWORD *)v20 + 19) = 2147483646;
                std::_Throw_Cpp_error(6);
                goto LABEL_67;
              }
              if ( (v11 & 0x3F) == 0 || *((_DWORD *)v20 + 22) > 8u )
                Ofc::CExclusiveAccessMgr2::CleanupOrphanedAccs(v20);
              v45 = *((_QWORD *)v20 + 10);
              v46 = v45 + 24LL * *((unsigned int *)v20 + 22);
              while ( 1 )
              {
                if ( v45 >= v46 )
                {
                  if ( *((_DWORD *)v20 + 22) == 8 && *((_Mtx_t *)v20 + 10) == (_Mtx_t)((char *)v20 + 96) )
                    Ofc::CArrayImpl::ConvertFixedToVarBuffer(
                      (_Mtx_t)((char *)v20 + 80),
                      0x18u,
                      9u,
                      (void (*)(unsigned __int8 *, unsigned __int8 *, unsigned int))Ofc::TMoveConstructRange<GEL::PANLINK,1>::Do);
                  v47 = Ofc::CArrayImpl::NewTop<Ofc::CExclusiveAccessMgr2::AccData>((char *)v20 + 80);
                  *(_QWORD *)v47 = v56;
                  *(_QWORD *)(v47 + 8) = &v55;
                  *(_DWORD *)(v47 + 16) = (_DWORD)CurrentThreadId;
                  goto LABEL_89;
                }
                if ( *(GEL::GdiTypeface **)v45 == v56 )
                  break;
                v45 += 24LL;
              }
              if ( *(_DWORD *)(v45 + 16) != (_DWORD)CurrentThreadId )
              {
                ResetEvent(*((HANDLE *)v20 + 36));
                _InterlockedIncrement((volatile signed __int32 *)v20 + 74);
                _Mtx_unlock(v20);
                WaitForSingleObjectEx(*((HANDLE *)v20 + 36), 0x32u, 0);
                _InterlockedDecrement((volatile signed __int32 *)v20 + 74);
                v11 = (unsigned int)(v11 + 1);
                continue;
              }
              break;
            }
LABEL_89:
            _Mtx_unlock(v20);
            CurrentThreadId = (const struct GEL::ITypefaceList *)(int)v7;
            v9 = (GEL::GdiTypeface *)*((_QWORD *)v9 + 14);
            v11 = *((_QWORD *)v9 + (int)v7);
            if ( v11 )
            {
              v23 = 0;
              v7 = 0;
              v22 = 1;
              v21 = v49;
              goto LABEL_91;
            }
            Ofc::CExclusiveAccess2::~CExclusiveAccess2((Ofc::CExclusiveAccess2 *)&v55);
            v16 = -1;
            goto LABEL_39;
          }
        }
      }
    }
    v12 = nNumerator;
    if ( v62.lfHeight != -nNumerator )
    {
      LODWORD(v20) = -v62.lfHeight;
      v11 = a5;
      if ( nNumerator )
      {
        LODWORD(v7) = -2147483647;
        LODWORD(CurrentThreadId) = 0;
        do
        {
          v37 = *v10;
          if ( (_DWORD)v20 )
          {
            v38 = MulDiv(v37, v12, (int)v20);
          }
          else
          {
            if ( v12 <= 0 )
            {
LABEL_67:
              v39 = (int)CurrentThreadId;
              if ( v12 < 0 )
                v39 = v7;
            }
            else
            {
              v39 = 0x7FFFFFFF;
            }
            if ( v37 <= 0 )
            {
              v41 = (int)CurrentThreadId;
              LOBYTE(v41) = v37 >= 0;
              v40 = v41 - 1;
            }
            else
            {
              v40 = 1;
            }
            v38 = v39 * v40;
          }
          *v10++ = v38;
          --v11;
        }
        while ( v11 );
      }
      else
      {
        do
        {
          v31 = *v10;
          if ( (_DWORD)v20 )
            v31 = MulDiv(v31, 0, (int)v20);
          *v10++ = v31;
          --v11;
        }
        while ( v11 );
      }
    }
  }
}

```

## disassembly

```asm
0x180077770  push    rbp
0x180077772  push    rbx
0x180077773  push    rsi
0x180077774  push    rdi
0x180077775  push    r12
0x180077777  push    r13
0x180077779  push    r14
0x18007777b  push    r15
0x18007777d  lea     rbp, [rsp-38h]
0x180077782  sub     rsp, 138h
0x180077789  mov     rax, cs:__security_cookie
0x180077790  xor     rax, rsp
0x180077793  mov     [rbp+70h+var_50], rax
0x180077797  mov     r14, r9
0x18007779a  mov     [rsp+170h+var_108], r9
0x18007779f  mov     r12, rdx
0x1800777a2  mov     [rbp+70h+var_E0], rdx
0x1800777a6  mov     r13, rcx
0x1800777a9  mov     [rbp+70h+var_E8], rcx
0x1800777ad  mov     rsi, [rbp+70h+arg_28]
0x1800777b4  cmp     byte ptr cs:xmmword_18051FD50+0Fh, 0
0x1800777bb  jnz     loc_180077B4C
0x1800777c1  cmp     byte ptr [r8+21h], 0
0x1800777c6  jnz     loc_180077B4C
0x1800777cc  mov     edi, [r8+14h]
0x1800777d0  mov     [rsp+170h+var_10C], edi
0x1800777d4  movss   xmm0, dword ptr [r8+10h]
0x1800777da  call    ??$Round@JM@Ofc@@YAJM@Z; Ofc::Round<long,float>(float)
0x1800777df  mov     r15d, eax
0x1800777e2  mov     [rsp+170h+nNumerator], eax
0x1800777e6  mov     rbx, [r8+18h]
0x1800777ea  cmp     qword ptr [r8], 0
0x1800777ee  jz      loc_180077942
0x1800777f4  mov     eax, [rbp+70h+arg_20]
0x1800777fa  test    eax, eax
0x1800777fc  jz      loc_180077942
0x180077802  cmp     [rbp+70h+arg_30], eax
0x180077808  jb      loc_180077942
0x18007780e  test    edi, 0FFFFFF00h
0x180077814  jnz     loc_180077942
0x18007781a  xor     edx, edx; Val
0x18007781c  mov     r8d, 5Ch ; '\'; Size
0x180077822  lea     rcx, [rbp+70h+var_B0]; void *
0x180077826  call    memset_0
0x18007782b  mov     [rsp+170h+var_128], 0; bool
0x180077830  xor     eax, eax
0x180077832  mov     [rsp+170h+var_130], rax; unsigned __int16 *
0x180077837  mov     [rsp+170h+var_138], rax; unsigned __int8 *
0x18007783c  mov     [rsp+170h+var_140], rax; unsigned __int8 *
0x180077841  mov     [rsp+170h+var_148], r12; struct GEL::ITypefaceList *
0x180077846  mov     [rsp+170h+var_150], rbx; void *
0x18007784b  mov     r9d, edi; unsigned int
0x18007784e  mov     r8d, r15d; int
0x180077851  lea     rdx, [rbp+70h+var_B0]; struct tagLOGFONTW *
0x180077855  mov     rcx, r13; this
0x180077858  call    ?GetLOGFONT@Typeface@GEL@@QEBAXAEAUtagLOGFONTW@@JIPEBXAEBUITypefaceList@2@PEBE3PEBG_N@Z; GEL::Typeface::GetLOGFONT(tagLOGFONTW &,long,uint,void const *,GEL::ITypefaceList const &,uchar const *,uchar const *,ushort const *,bool)
0x18007785d  xor     eax, eax
0x18007785f  mov     r12d, eax
0x180077862  mov     dword ptr [rsp+170h+var_118], eax
0x180077866  lea     rcx, ?FIsFontInfoCachable@Typeface@GEL@@UEBA_NXZ; GEL::Typeface::FIsFontInfoCachable(void)
0x18007786d  mov     edi, 0FFFFFFFFh
0x180077872  cmp     byte ptr cs:xmmword_18051FD50+1, 0
0x180077879  jz      loc_1800779F1
0x18007787f  mov     r15d, [rbp+70h+var_B0.lfHeight]
0x180077883  neg     r15d
0x180077886  mov     eax, r12d
0x180077889  movzx   ebx, word ptr [r14+rax*2]
0x18007788e  mov     [rsp+170h+var_120], bx
0x180077893  mov     [rsp+170h+var_110], edi
0x180077897  cmp     qword ptr [r13+70h], 1
0x18007789c  jbe     loc_1800779EF
0x1800778a2  mov     rax, [r13+0]
0x1800778a6  mov     rax, [rax+160h]
0x1800778ad  cmp     rax, rcx
0x1800778b0  mov     rcx, r13; this
0x1800778b3  jnz     loc_180077E37
0x1800778b9  call    ?FIsFontInfoCachable@Typeface@GEL@@UEBA_NXZ; GEL::Typeface::FIsFontInfoCachable(void)
0x1800778be  test    al, al
0x1800778c0  jz      loc_1800779EF
0x1800778c6  mov     r14d, ebx
0x1800778c9  imul    r14d, r15d
0x1800778cd  mov     eax, 7A44C6Bh
0x1800778d2  imul    r14d
0x1800778d5  sar     edx, 1
0x1800778d7  mov     eax, edx
0x1800778d9  shr     eax, 1Fh
0x1800778dc  add     edx, eax
0x1800778de  imul    eax, edx, 43h ; 'C'
0x1800778e1  sub     r14d, eax
0x1800778e4  test    r14d, r14d
0x1800778e7  mov     r12d, 0
0x1800778ed  cmovle  r14d, r12d
0x1800778f1  mov     rbx, cs:?s_pInstance@?$TSingleton@VTypefaceAccessMgr@GEL@@@Ofc@@0PEAVTypefaceAccessMgr@GEL@@EA; GEL::TypefaceAccessMgr * Ofc::TSingleton<GEL::TypefaceAccessMgr>::s_pInstance
0x1800778f8  cmp     rbx, 1
0x1800778fc  ja      short loc_18007790A
0x1800778fe  call    ??$ThreadSafeInitPointerOnce@PEAVTypefaceAccessMgr@GEL@@V?$TSingletonFactory@VTypefaceAccessMgr@GEL@@@Ofc@@@Ofc@@YAXPECREAVTypefaceAccessMgr@GEL@@@Z; Ofc::ThreadSafeInitPointerOnce<GEL::TypefaceAccessMgr *,Ofc::TSingletonFactory<GEL::TypefaceAccessMgr>>(GEL::TypefaceAccessMgr * volatile *)
0x180077903  mov     rbx, cs:?s_pInstance@?$TSingleton@VTypefaceAccessMgr@GEL@@@Ofc@@0PEAVTypefaceAccessMgr@GEL@@EA; GEL::TypefaceAccessMgr * Ofc::TSingleton<GEL::TypefaceAccessMgr>::s_pInstance
0x18007790a  mov     [rsp+170h+var_F8], rbx
0x18007790f  mov     [rbp+70h+var_F0], r13
0x180077913  call    cs:__imp_GetCurrentThreadId
0x180077919  mov     r12d, eax
0x18007791c  mov     edi, 1
0x180077921  mov     [rbp+70h+var_C0], rbx
0x180077925  mov     rcx, rbx; _Mtx_t
0x180077928  call    cs:__imp__Mtx_lock
0x18007792e  test    eax, eax
0x180077930  jz      loc_180077BBB
0x180077936  mov     ecx, 5
0x18007793b  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180077941  nop
0x180077942  mov     ecx, 35668Fh; unsigned int
0x180077947  call    ?ThrowTag@CInvalidParamException@Ofc@@SAXK@Z; Ofc::CInvalidParamException::ThrowTag(ulong)
0x18007794c  nop
0x18007794d  jmp     short loc_180077950
0x180077950  nop
0x180077951  mov     eax, [rsp+170h+var_10C]
0x180077955  cmp     [rdi+8], eax
0x180077958  jnz     loc_180077D5D
0x18007795e  test    r14, r14
0x180077961  jz      short loc_1800779D4
0x180077963  mov     rbx, r8
0x180077966  mov     rax, [r14+10h]
0x18007796a  test    rax, rax
0x18007796d  jz      short loc_180077979
0x18007796f  mov     [r14+10h], r8
0x180077973  mov     rbx, rax
0x180077976  mov     rax, r8
0x180077979  mov     r15, [rbx+10h]
0x18007797d  cmp     rax, r15
0x180077980  jz      short loc_180077997
0x180077982  mov     [rbx+10h], r8
0x180077986  mov     rcx, [r14+10h]; this
0x18007798a  test    rcx, rcx
0x18007798d  jnz     loc_180077A90
0x180077993  mov     [r14+10h], r15
0x180077997  mov     r14, [r13+r12*8+0]
0x18007799c  cmp     [rbx+10h], r14
0x1800779a0  jz      short loc_1800779B8
0x1800779a2  mov     [r13+r12*8+0], r8
0x1800779a7  mov     rcx, [rbx+10h]; this
0x1800779ab  test    rcx, rcx
0x1800779ae  jnz     loc_180077A9D
0x1800779b4  mov     [rbx+10h], r14
0x1800779b8  mov     rcx, [r13+r12*8+0]; this
0x1800779bd  cmp     rcx, rbx
0x1800779c0  jz      loc_180077CC0
0x1800779c6  test    rcx, rcx
0x1800779c9  jnz     loc_180077CB6
0x1800779cf  mov     [r13+r12*8+0], rbx
0x1800779d4  mov     edi, [rdi+0Ch]
0x1800779d7  lea     rcx, [rsp+170h+var_F8]; this
0x1800779dc  call    ??1CExclusiveAccess2@Ofc@@QEAA@XZ; Ofc::CExclusiveAccess2::~CExclusiveAccess2(void)
0x1800779e1  mov     r14, [rsp+170h+var_108]
0x1800779e6  mov     r13, [rbp+70h+var_E8]
0x1800779ea  mov     r12d, dword ptr [rsp+170h+var_118]
0x1800779ef  xor     eax, eax
0x1800779f1  mov     ebx, r12d
0x1800779f4  cmp     edi, 0FFFFFFFFh
0x1800779f7  jz      loc_180077AA7
0x1800779fd  mov     [rsi+rbx*4], edi
0x180077a00  inc     r12d
0x180077a03  mov     dword ptr [rsp+170h+var_118], r12d
0x180077a08  mov     ecx, [rbp+70h+arg_20]
0x180077a0e  cmp     r12d, ecx
0x180077a11  jnb     short loc_180077A1F
0x180077a13  mov     r14, [rsp+170h+var_108]
0x180077a18  xor     eax, eax
0x180077a1a  jmp     loc_180077866
0x180077a1f  mov     r15d, [rsp+170h+nNumerator]
0x180077a24  mov     eax, r15d
0x180077a27  neg     eax
0x180077a29  mov     ebx, [rbp+70h+var_B0.lfHeight]
0x180077a2c  cmp     ebx, eax
0x180077a2e  jz      short loc_180077A70
0x180077a30  neg     ebx
0x180077a32  mov     rdi, rcx
0x180077a35  test    r15d, r15d
0x180077a38  jnz     loc_180077B6F
0x180077a3e  nop     word ptr [rax+rax]
0x180077a43  nop     dword ptr [rax+00h]
0x180077a47  nop     word ptr [rax+rax+00000000h]
0x180077a50  mov     eax, [rsi]
0x180077a52  test    ebx, ebx
0x180077a54  jz      short loc_180077A64
0x180077a56  mov     r8d, ebx; nDenominator
0x180077a59  mov     edx, r15d; nNumerator
0x180077a5c  mov     ecx, eax; nNumber
0x180077a5e  call    cs:__imp_MulDiv
0x180077a64  mov     [rsi], eax
0x180077a66  add     rsi, 4
0x180077a6a  sub     rdi, 1
0x180077a6e  jnz     short loc_180077A50
0x180077a70  mov     rcx, [rbp+70h+var_50]
0x180077a74  xor     rcx, rsp; StackCookie
0x180077a77  call    __security_check_cookie
0x180077a7c  add     rsp, 138h
0x180077a83  pop     r15
0x180077a85  pop     r14
0x180077a87  pop     r13
0x180077a89  pop     r12
0x180077a8b  pop     rdi
0x180077a8c  pop     rsi
0x180077a8d  pop     rbx
0x180077a8e  pop     rbp
0x180077a8f  retn
0x180077a90  call    ??_GWidthCache@GEL@@QEAAPEAXI@Z; GEL::WidthCache::`scalar deleting destructor'(uint)
0x180077a95  xor     r8d, r8d
0x180077a98  jmp     loc_180077993
0x180077a9d  call    ??_GWidthCache@GEL@@QEAAPEAXI@Z; GEL::WidthCache::`scalar deleting destructor'(uint)
0x180077aa2  jmp     loc_1800779B4
0x180077aa7  mov     [rsp+170h+var_118], rax
0x180077aac  mov     edi, eax
0x180077aae  lea     r8, [rbp+70h+var_B0]; struct tagLOGFONTW *
0x180077ab2  mov     r15, [rbp+70h+var_E0]
0x180077ab6  mov     rdx, r15; struct GEL::ITypefaceList *
0x180077ab9  lea     rcx, [rbp+70h+var_D8]; this
0x180077abd  call    ??0SharedDeviceIC@GEL@@QEAA@AEBUITypefaceList@1@AEBUtagLOGFONTW@@@Z; GEL::SharedDeviceIC::SharedDeviceIC(GEL::ITypefaceList const &,tagLOGFONTW const &)
0x180077ac2  mov     rcx, [rax+8]
0x180077ac6  lea     r14, [r14+rbx*2]
0x180077aca  xor     eax, eax
0x180077acc  mov     [rsp+170h+var_140], rax
0x180077ad1  mov     dword ptr [rsp+170h+var_148], 4
0x180077ad9  mov     dword ptr [rsp+170h+var_150], eax
0x180077add  lea     r9, [rsp+170h+var_118]
0x180077ae2  mov     r8d, 1
0x180077ae8  mov     rdx, r14
0x180077aeb  mov     rcx, [rcx]
0x180077aee  call    cs:__imp_MsoGetTextExtentPointWEx
0x180077af4  mov     ebx, eax
0x180077af6  mov     rcx, [rbp+70h+var_C8]; _Mtx_t
0x180077afa  call    cs:__imp__Mtx_unlock
0x180077b00  test    ebx, ebx
0x180077b02  jz      short loc_180077B10
0x180077b04  mov     edi, dword ptr [rsp+170h+var_118]
0x180077b08  test    edi, edi
0x180077b0a  jz      loc_180077BF3
0x180077b10  mov     eax, r12d
0x180077b13  mov     [rsi+rax*4], edi
0x180077b16  cmp     byte ptr cs:xmmword_18051FD50+1, 0
0x180077b1d  jz      loc_180077A00
0x180077b23  mov     r8d, [rbp+70h+var_B0.lfHeight]
0x180077b27  neg     r8d; int
0x180077b2a  mov     edx, r12d
0x180077b2d  mov     dword ptr [rsp+170h+var_150], edi; int
0x180077b31  mov     r9d, [rsp+170h+var_10C]; unsigned int
0x180077b36  mov     rax, [rsp+170h+var_108]
0x180077b3b  movzx   edx, word ptr [rax+rdx*2]; wchar_t
0x180077b3f  mov     rcx, r13; this
0x180077b42  call    ?CacheWidth@Typeface@GEL@@QEBAX_WHIJ@Z; GEL::Typeface::CacheWidth(wchar_t,int,uint,long)
0x180077b47  jmp     loc_180077A00
0x180077b4c  mov     eax, [rbp+70h+arg_30]
0x180077b52  mov     dword ptr [rsp+170h+var_140], eax; unsigned int
0x180077b56  mov     [rsp+170h+var_148], rsi; int *
0x180077b5b  mov     eax, [rbp+70h+arg_20]
0x180077b61  mov     dword ptr [rsp+170h+var_150], eax; unsigned int
0x180077b65  call    ?GetCharWidths@DWriteTypeface@GEL@@UEBAXAEBUITypefaceList@2@AEBUFont@2@PEB_WIPEAJI@Z; GEL::DWriteTypeface::GetCharWidths(GEL::ITypefaceList const &,GEL::Font const &,wchar_t const *,uint,long *,uint)
0x180077b6a  jmp     loc_180077A70
0x180077b6f  mov     r14d, 80000001h
0x180077b75  xor     r12d, r12d
0x180077b78  nop     dword ptr [rax+rax+00000000h]
0x180077b80  mov     ecx, [rsi]; nNumber
0x180077b82  test    ebx, ebx
0x180077b84  jz      short loc_180077BA3
0x180077b86  mov     r8d, ebx; nDenominator
0x180077b89  mov     edx, r15d; nNumerator
0x180077b8c  call    cs:__imp_MulDiv
0x180077b92  mov     [rsi], eax
0x180077b94  add     rsi, 4
0x180077b98  sub     rdi, 1
0x180077b9c  jnz     short loc_180077B80
0x180077b9e  jmp     loc_180077A70
0x180077ba3  test    r15d, r15d
0x180077ba6  jle     short loc_180077BDB
0x180077ba8  mov     edx, 7FFFFFFFh
0x180077bad  test    ecx, ecx
0x180077baf  jle     short loc_180077BE7
0x180077bb1  mov     eax, 1
0x180077bb6  imul    eax, edx
0x180077bb9  jmp     short loc_180077B92
0x180077bbb  cmp     dword ptr [rbx+4Ch], 7FFFFFFFh
0x180077bc2  jnz     loc_180077CCD
0x180077bc8  mov     dword ptr [rbx+4Ch], 7FFFFFFEh
0x180077bcf  mov     ecx, 6
0x180077bd4  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180077bda  nop
0x180077bdb  mov     edx, r12d
0x180077bde  test    r15d, r15d
0x180077be1  cmovs   edx, r14d
0x180077be5  jmp     short loc_180077BAD
0x180077be7  mov     eax, r12d
0x180077bea  test    ecx, ecx
0x180077bec  setns   al
0x180077bef  dec     eax
0x180077bf1  jmp     short loc_180077BB6
0x180077bf3  movzx   ecx, word ptr [r14]
0x180077bf7  mov     edx, 4E00h
0x180077bfc  mov     r8d, 3400h
0x180077c02  cmp     cx, dx
0x180077c05  jz      short loc_180077C17
0x180077c07  cmp     r8w, cx
  ... truncated ...
```
