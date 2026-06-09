# GEL::Typeface::GetWidthCache(wchar_t,int,uint)

- ea: `0x1800920b0`
- end: `0x1800923df`
- name: `?GetWidthCache@Typeface@GEL@@QEBAJ_WHI@Z`
- size: `815`
- prototype: `__int64 __fastcall(GEL::Typeface *__hidden this, wchar_t, int, unsigned int)`
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x1800919f0`
- `0x1800af160`

## callees

- `0x180057e70`
- `0x1800920b0`
- `0x1800923e0`
- `0x180092590`
- `0x1800926b4`
- `0x1800927e0`
- `0x180092ad0`
- `0x1800e38d0`
- `0x180161450`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180092153`
- `KERNEL32!GetCurrentThreadId` at `0x180092153`
- `KERNEL32!WaitForSingleObjectEx` at `0x180092370`
- `KERNEL32!WaitForSingleObjectEx` at `0x180092370`
- `KERNEL32!ResetEvent` at `0x18009234b`
- `KERNEL32!ResetEvent` at `0x18009234b`
- `MSVCP140!_Mtx_unlock` at `0x1800922bf`
- `MSVCP140!_Mtx_unlock` at `0x18009235b`
- `MSVCP140!_Mtx_unlock` at `0x1800922bf`
- `MSVCP140!_Mtx_unlock` at `0x18009235b`
- `MSVCP140!_Mtx_lock` at `0x180092171`
- `MSVCP140!_Mtx_lock` at `0x180092171`
- `MSVCP140!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180092184`
- `MSVCP140!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180092244`
- `MSVCP140!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180092184`
- `MSVCP140!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180092244`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall GEL::Typeface::GetWidthCache(GEL::Typeface *this, unsigned __int16 a2, int a3, int a4)
{
  int v5; // r15d
  GEL::Typeface *v6; // rdi
  unsigned int v7; // r12d
  bool (__fastcall *v8)(GEL::Typeface *__hidden); // rax
  char v9; // al
  _Mtx_t v10; // rsi
  _Mtx_t v11; // rbx
  int v12; // r13d
  __int64 v13; // r14
  GEL::Typeface *v14; // rdx
  int v15; // ecx
  GEL::Typeface *v16; // rax
  GEL::Typeface *v17; // rbp
  GEL::WidthCache *v18; // rcx
  GEL::WidthCache *v19; // rsi
  GEL::WidthCache *v20; // rcx
  GEL::WidthCache *v21; // rcx
  unsigned __int64 v23; // rdx
  unsigned __int64 v24; // rax
  __int64 v25; // rax
  GEL::WidthCache *v26; // rcx
  _Mtx_t v27; // [rsp+28h] [rbp-50h] BYREF
  GEL::Typeface *v28; // [rsp+30h] [rbp-48h]
  DWORD CurrentThreadId; // [rsp+80h] [rbp+8h]

  v5 = a2;
  v6 = this;
  v7 = -1;
  if ( *((_QWORD *)this + 14) > 1u )
  {
    v8 = *(bool (__fastcall **)(GEL::Typeface *__hidden))(*(_QWORD *)this + 352LL);
    v9 = v8 == GEL::Typeface::FIsFontInfoCachable ? GEL::Typeface::FIsFontInfoCachable(this) : ((__int64 (*)(void))v8)();
    if ( v9 )
    {
      v10 = (_Mtx_t)(unsigned int)(a3 * v5 % 67);
      if ( (int)v10 <= 0 )
        v10 = 0;
      v11 = Ofc::TSingleton<GEL::TypefaceAccessMgr>::s_pInstance;
      if ( (unsigned __int64)Ofc::TSingleton<GEL::TypefaceAccessMgr>::s_pInstance <= 1 )
      {
        Ofc::ThreadSafeInitPointerOnce<GEL::TypefaceAccessMgr *,Ofc::TSingletonFactory<GEL::TypefaceAccessMgr>>();
        v11 = Ofc::TSingleton<GEL::TypefaceAccessMgr>::s_pInstance;
      }
      v27 = v11;
      v28 = v6;
      CurrentThreadId = GetCurrentThreadId();
      v12 = 1;
      v13 = 1;
      while ( 2 )
      {
        if ( _Mtx_lock(v11) )
        {
          std::_Throw_Cpp_error(5);
LABEL_12:
          if ( *((_DWORD *)v11 + 2) != v15 )
          {
            while ( *((_QWORD *)v11 + 2) )
            {
              v10 = v11;
              v11 = (_Mtx_t)*((_QWORD *)v11 + 2);
              ++v12;
LABEL_43:
              if ( *(_WORD *)v11 == (_WORD)v5 && *((_DWORD *)v11 + 1) == a3 )
                goto LABEL_12;
            }
            if ( v12 >= 19 )
            {
              v26 = (GEL::WidthCache *)*((_QWORD *)v10 + 2);
              if ( v26 )
              {
                *((_QWORD *)v10 + 2) = v14;
                GEL::WidthCache::`scalar deleting destructor'(v26, (unsigned int)v14);
              }
            }
            goto LABEL_29;
          }
          if ( !v10 )
          {
LABEL_28:
            v7 = *((_DWORD *)v11 + 3);
LABEL_29:
            Ofc::CExclusiveAccess2::~CExclusiveAccess2((Ofc::CExclusiveAccess2 *)&v27);
            return v7;
          }
          v6 = v14;
          v16 = (GEL::Typeface *)*((_QWORD *)v10 + 2);
          if ( v16 )
          {
            *((_QWORD *)v10 + 2) = v14;
            v6 = v16;
            v16 = v14;
          }
          v17 = (GEL::Typeface *)*((_QWORD *)v6 + 2);
          if ( v16 != v17 )
          {
            *((_QWORD *)v6 + 2) = v14;
            v18 = (GEL::WidthCache *)*((_QWORD *)v10 + 2);
            if ( v18 )
            {
              GEL::WidthCache::`scalar deleting destructor'(v18, (unsigned int)v14);
              v14 = 0;
            }
            *((_QWORD *)v10 + 2) = v17;
          }
          v19 = *(GEL::WidthCache **)v13;
          if ( *((_QWORD *)v6 + 2) != *(_QWORD *)v13 )
          {
            *(_QWORD *)v13 = v14;
            v20 = (GEL::WidthCache *)*((_QWORD *)v6 + 2);
            if ( v20 )
              GEL::WidthCache::`scalar deleting destructor'(v20, (unsigned int)v14);
            *((_QWORD *)v6 + 2) = v19;
          }
          v21 = *(GEL::WidthCache **)v13;
          if ( *(GEL::Typeface **)v13 != v6 )
          {
            if ( v21 )
              GEL::WidthCache::`scalar deleting destructor'(v21, (unsigned int)v14);
            *(_QWORD *)v13 = v6;
            goto LABEL_28;
          }
        }
        else
        {
          if ( *((_DWORD *)v11 + 19) != 0x7FFFFFFF )
          {
            if ( (v13 & 0x3F) == 0 || *((_DWORD *)v11 + 22) > 8u )
              Ofc::CExclusiveAccessMgr2::CleanupOrphanedAccs(v11);
            v23 = *((_QWORD *)v11 + 10);
            v24 = v23 + 24LL * *((unsigned int *)v11 + 22);
            while ( 1 )
            {
              if ( v23 >= v24 )
              {
                if ( *((_DWORD *)v11 + 22) == 8 && *((_Mtx_t *)v11 + 10) == (_Mtx_t)((char *)v11 + 96) )
                  Ofc::CArrayImpl::ConvertFixedToVarBuffer(
                    (_Mtx_t)((char *)v11 + 80),
                    0x18u,
                    9u,
                    (void (*)(unsigned __int8 *, unsigned __int8 *, unsigned int))Ofc::TMoveConstructRange<GEL::PANLINK,1>::Do);
                v25 = Ofc::CArrayImpl::NewTop<Ofc::CExclusiveAccessMgr2::AccData>((char *)v11 + 80);
                *(_QWORD *)v25 = v28;
                *(_QWORD *)(v25 + 8) = &v27;
                *(_DWORD *)(v25 + 16) = CurrentThreadId;
                goto LABEL_41;
              }
              if ( *(GEL::Typeface **)v23 == v28 )
                break;
              v23 += 24LL;
            }
            if ( *(_DWORD *)(v23 + 16) != CurrentThreadId )
            {
              ResetEvent(*((HANDLE *)v11 + 36));
              _InterlockedIncrement((volatile signed __int32 *)v11 + 74);
              _Mtx_unlock(v11);
              WaitForSingleObjectEx(*((HANDLE *)v11 + 36), 0x32u, 0);
              _InterlockedDecrement((volatile signed __int32 *)v11 + 74);
              v13 = (unsigned int)(v13 + 1);
              continue;
            }
LABEL_41:
            _Mtx_unlock(v11);
            v13 = *((_QWORD *)v6 + 14) + 8LL * (int)v10;
            v11 = *(_Mtx_t *)v13;
            if ( *(_QWORD *)v13 )
            {
              v14 = 0;
              v10 = 0;
              v15 = a4;
              goto LABEL_43;
            }
            goto LABEL_29;
          }
          *((_DWORD *)v11 + 19) = 2147483646;
          std::_Throw_Cpp_error(6);
        }
        break;
      }
      if ( v6 )
        GEL::WidthCache::`scalar deleting destructor'(v6, (unsigned int)v14);
      goto LABEL_28;
    }
  }
  return v7;
}

```

## disassembly

```asm
0x1800920b0  mov     [rsp+arg_8], rbx
0x1800920b5  mov     [rsp+arg_18], r9d
0x1800920ba  push    rbp
0x1800920bb  push    rsi
0x1800920bc  push    rdi
0x1800920bd  push    r12
0x1800920bf  push    r13
0x1800920c1  push    r14
0x1800920c3  push    r15
0x1800920c5  sub     rsp, 40h
0x1800920c9  mov     ebp, r8d
0x1800920cc  movzx   r15d, dx
0x1800920d0  mov     rdi, rcx
0x1800920d3  mov     r12d, 0FFFFFFFFh
0x1800920d9  cmp     qword ptr [rcx+70h], 1
0x1800920de  jbe     loc_180092204
0x1800920e4  mov     rax, [rcx]
0x1800920e7  mov     rax, [rax+160h]
0x1800920ee  lea     rcx, ?FIsFontInfoCachable@Typeface@GEL@@UEBA_NXZ; GEL::Typeface::FIsFontInfoCachable(void)
0x1800920f5  cmp     rax, rcx
0x1800920f8  mov     rcx, rdi; this
0x1800920fb  jnz     loc_1800923C9
0x180092101  call    ?FIsFontInfoCachable@Typeface@GEL@@UEBA_NXZ; GEL::Typeface::FIsFontInfoCachable(void)
0x180092106  test    al, al
0x180092108  jz      loc_180092204
0x18009210e  mov     esi, r15d
0x180092111  imul    esi, ebp
0x180092114  mov     eax, 7A44C6Bh
0x180092119  imul    esi
0x18009211b  sar     edx, 1
0x18009211d  mov     eax, edx
0x18009211f  shr     eax, 1Fh
0x180092122  add     edx, eax
0x180092124  imul    eax, edx, 43h ; 'C'
0x180092127  sub     esi, eax
0x180092129  xor     eax, eax
0x18009212b  test    esi, esi
0x18009212d  cmovle  esi, eax
0x180092130  mov     rbx, cs:?s_pInstance@?$TSingleton@VTypefaceAccessMgr@GEL@@@Ofc@@0PEAVTypefaceAccessMgr@GEL@@EA; GEL::TypefaceAccessMgr * Ofc::TSingleton<GEL::TypefaceAccessMgr>::s_pInstance
0x180092137  cmp     rbx, 1
0x18009213b  ja      short loc_180092149
0x18009213d  call    ??$ThreadSafeInitPointerOnce@PEAVTypefaceAccessMgr@GEL@@V?$TSingletonFactory@VTypefaceAccessMgr@GEL@@@Ofc@@@Ofc@@YAXPECREAVTypefaceAccessMgr@GEL@@@Z; Ofc::ThreadSafeInitPointerOnce<GEL::TypefaceAccessMgr *,Ofc::TSingletonFactory<GEL::TypefaceAccessMgr>>(GEL::TypefaceAccessMgr * volatile *)
0x180092142  mov     rbx, cs:?s_pInstance@?$TSingleton@VTypefaceAccessMgr@GEL@@@Ofc@@0PEAVTypefaceAccessMgr@GEL@@EA; GEL::TypefaceAccessMgr * Ofc::TSingleton<GEL::TypefaceAccessMgr>::s_pInstance
0x180092149  mov     [rsp+78h+var_50], rbx
0x18009214e  mov     [rsp+78h+var_48], rdi
0x180092153  call    cs:__imp_GetCurrentThreadId
0x180092159  mov     [rsp+78h+arg_0], eax
0x180092160  mov     r13d, 1
0x180092166  mov     r14d, r13d
0x180092169  mov     [rsp+78h+var_58], rbx
0x18009216e  mov     rcx, rbx; _Mtx_t
0x180092171  call    cs:__imp__Mtx_lock
0x180092177  test    eax, eax
0x180092179  jz      loc_18009222F
0x18009217f  mov     ecx, 5
0x180092184  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18009218a  nop
0x18009218b  cmp     [rbx+8], ecx
0x18009218e  jnz     loc_1800922F6
0x180092194  test    rsi, rsi
0x180092197  jz      short loc_1800921F6
0x180092199  mov     rdi, rdx
0x18009219c  mov     rax, [rsi+10h]
0x1800921a0  test    rax, rax
0x1800921a3  jz      short loc_1800921AF
0x1800921a5  mov     [rsi+10h], rdx
0x1800921a9  mov     rdi, rax
0x1800921ac  mov     rax, rdx
0x1800921af  mov     rbp, [rdi+10h]
0x1800921b3  cmp     rax, rbp
0x1800921b6  jz      short loc_1800921C9
0x1800921b8  mov     [rdi+10h], rdx
0x1800921bc  mov     rcx, [rsi+10h]; this
0x1800921c0  test    rcx, rcx
0x1800921c3  jnz     short loc_18009221F
0x1800921c5  mov     [rsi+10h], rbp
0x1800921c9  mov     rsi, [r14]
0x1800921cc  cmp     [rdi+10h], rsi
0x1800921d0  jz      short loc_1800921E2
0x1800921d2  mov     [r14], rdx
0x1800921d5  mov     rcx, [rdi+10h]; this
0x1800921d9  test    rcx, rcx
0x1800921dc  jnz     short loc_180092228
0x1800921de  mov     [rdi+10h], rsi
0x1800921e2  mov     rcx, [r14]; this
0x1800921e5  cmp     rcx, rdi
0x1800921e8  jz      short loc_18009224B
0x1800921ea  test    rcx, rcx
0x1800921ed  jnz     loc_1800923D4
0x1800921f3  mov     [r14], rdi
0x1800921f6  mov     r12d, [rbx+0Ch]
0x1800921fa  lea     rcx, [rsp+78h+var_50]; this
0x1800921ff  call    ??1CExclusiveAccess2@Ofc@@QEAA@XZ; Ofc::CExclusiveAccess2::~CExclusiveAccess2(void)
0x180092204  mov     eax, r12d
0x180092207  mov     rbx, [rsp+78h+arg_8]
0x18009220f  add     rsp, 40h
0x180092213  pop     r15
0x180092215  pop     r14
0x180092217  pop     r13
0x180092219  pop     r12
0x18009221b  pop     rdi
0x18009221c  pop     rsi
0x18009221d  pop     rbp
0x18009221e  retn
0x18009221f  call    ??_GWidthCache@GEL@@QEAAPEAXI@Z; GEL::WidthCache::`scalar deleting destructor'(uint)
0x180092224  xor     edx, edx
0x180092226  jmp     short loc_1800921C5
0x180092228  call    ??_GWidthCache@GEL@@QEAAPEAXI@Z; GEL::WidthCache::`scalar deleting destructor'(uint)
0x18009222d  jmp     short loc_1800921DE
0x18009222f  cmp     dword ptr [rbx+4Ch], 7FFFFFFFh
0x180092236  jnz     short loc_18009225A
0x180092238  mov     dword ptr [rbx+4Ch], 7FFFFFFEh
0x18009223f  mov     ecx, 6
0x180092244  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18009224a  nop
0x18009224b  test    rdi, rdi
0x18009224e  jz      short loc_1800921F6
0x180092250  mov     rcx, rdi; this
0x180092253  call    ??_GWidthCache@GEL@@QEAAPEAXI@Z; GEL::WidthCache::`scalar deleting destructor'(uint)
0x180092258  jmp     short loc_1800921F6
0x18009225a  test    r14b, 3Fh
0x18009225e  jz      loc_18009238E
0x180092264  cmp     dword ptr [rbx+58h], 8
0x180092268  ja      loc_18009238E
0x18009226e  mov     rdx, [rbx+50h]
0x180092272  mov     eax, [rbx+58h]
0x180092275  lea     rcx, [rax+rax*2]
0x180092279  lea     rax, [rdx+rcx*8]
0x18009227d  mov     rcx, [rsp+78h+var_48]
0x180092282  cmp     rdx, rax
0x180092285  jb      loc_18009232F
0x18009228b  cmp     dword ptr [rbx+58h], 8
0x18009228f  jz      loc_18009239B
0x180092295  lea     rcx, [rbx+50h]
0x180092299  call    ??$NewTop@UAccData@CExclusiveAccessMgr2@Ofc@@@CArrayImpl@Ofc@@IEAAAEAUAccData@CExclusiveAccessMgr2@1@XZ; Ofc::CArrayImpl::NewTop<Ofc::CExclusiveAccessMgr2::AccData>(void)
0x18009229e  mov     rcx, rax
0x1800922a1  mov     rax, [rsp+78h+var_48]
0x1800922a6  mov     [rcx], rax
0x1800922a9  lea     rax, [rsp+78h+var_50]
0x1800922ae  mov     [rcx+8], rax
0x1800922b2  mov     eax, [rsp+78h+arg_0]
0x1800922b9  mov     [rcx+10h], eax
0x1800922bc  mov     rcx, rbx; _Mtx_t
0x1800922bf  call    cs:__imp__Mtx_unlock
0x1800922c5  movsxd  rcx, esi
0x1800922c8  mov     rax, [rdi+70h]
0x1800922cc  lea     r14, [rax+rcx*8]
0x1800922d0  mov     rbx, [r14]
0x1800922d3  test    rbx, rbx
0x1800922d6  jz      loc_1800921FA
0x1800922dc  xor     edx, edx; unsigned int
0x1800922de  mov     esi, edx
0x1800922e0  mov     ecx, [rsp+78h+arg_18]
0x1800922e7  cmp     [rbx], r15w
0x1800922eb  jnz     short loc_1800922F6
0x1800922ed  cmp     [rbx+4], ebp
0x1800922f0  jz      loc_18009218B
0x1800922f6  mov     rax, [rbx+10h]
0x1800922fa  test    rax, rax
0x1800922fd  jz      short loc_18009230A
0x1800922ff  mov     rsi, rbx
0x180092302  mov     rbx, rax
0x180092305  inc     r13d
0x180092308  jmp     short loc_1800922E7
0x18009230a  cmp     r13d, 13h
0x18009230e  jl      loc_1800921FA
0x180092314  mov     rcx, [rsi+10h]; this
0x180092318  test    rcx, rcx
0x18009231b  jz      loc_1800921FA
0x180092321  mov     [rsi+10h], rdx
0x180092325  call    ??_GWidthCache@GEL@@QEAAPEAXI@Z; GEL::WidthCache::`scalar deleting destructor'(uint)
0x18009232a  jmp     loc_1800921FA
0x18009232f  cmp     [rdx], rcx
0x180092332  jnz     short loc_180092385
0x180092334  mov     eax, [rsp+78h+arg_0]
0x18009233b  cmp     [rdx+10h], eax
0x18009233e  jz      loc_1800922BC
0x180092344  mov     rcx, [rbx+120h]; hEvent
0x18009234b  call    cs:__imp_ResetEvent
0x180092351  lock inc dword ptr [rbx+128h]
0x180092358  mov     rcx, rbx; _Mtx_t
0x18009235b  call    cs:__imp__Mtx_unlock
0x180092361  xor     r8d, r8d; bAlertable
0x180092364  mov     edx, 32h ; '2'; dwMilliseconds
0x180092369  mov     rcx, [rbx+120h]; hHandle
0x180092370  call    cs:__imp_WaitForSingleObjectEx
0x180092376  lock dec dword ptr [rbx+128h]
0x18009237d  inc     r14d
0x180092380  jmp     loc_18009216E
0x180092385  add     rdx, 18h
0x180092389  jmp     loc_180092282
0x18009238e  mov     rcx, rbx; this
0x180092391  call    ?CleanupOrphanedAccs@CExclusiveAccessMgr2@Ofc@@AEAAXXZ; Ofc::CExclusiveAccessMgr2::CleanupOrphanedAccs(void)
0x180092396  jmp     loc_18009226E
0x18009239b  lea     rax, [rbx+60h]
0x18009239f  cmp     [rbx+50h], rax
0x1800923a3  jnz     loc_180092295
0x1800923a9  lea     r9, ?Do@?$TMoveConstructRange@UPANLINK@GEL@@$00@Ofc@@SAXPEAE0K@Z; void (*)(unsigned __int8 *, unsigned __int8 *, unsigned int)
0x1800923b0  mov     edx, 18h; unsigned int
0x1800923b5  mov     r8d, 9; unsigned int
0x1800923bb  lea     rcx, [rbx+50h]; this
0x1800923bf  call    ?ConvertFixedToVarBuffer@CArrayImpl@Ofc@@IEAAXKKP6AXPEAE0K@Z@Z; Ofc::CArrayImpl::ConvertFixedToVarBuffer(ulong,ulong,void (*)(uchar *,uchar *,ulong))
0x1800923c4  jmp     loc_180092295
0x1800923c9  call    cs:__guard_dispatch_icall_fptr
0x1800923cf  jmp     loc_180092106
0x1800923d4  call    ??_GWidthCache@GEL@@QEAAPEAXI@Z; GEL::WidthCache::`scalar deleting destructor'(uint)
0x1800923d9  jmp     loc_1800921F3
```
