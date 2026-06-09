# GEL::Typeface::GetWidthCache(wchar_t,int,uint)

- ea: `0x180077e50`
- end: `0x180078178`
- name: `?GetWidthCache@Typeface@GEL@@QEBAJ_WHI@Z`
- size: `808`
- prototype: `__int64 __fastcall(GEL::Typeface *__hidden this, wchar_t, int, unsigned int)`
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x180077770`
- `0x18009aae0`

## callees

- `0x1800573f0`
- `0x180077e50`
- `0x180078178`
- `0x180078320`
- `0x180078444`
- `0x180078570`
- `0x18007877c`
- `0x1800bd910`
- `0x18015ee1c`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180077ef3`
- `KERNEL32!GetCurrentThreadId` at `0x180077ef3`
- `KERNEL32!WaitForSingleObjectEx` at `0x18007811c`
- `KERNEL32!WaitForSingleObjectEx` at `0x18007811c`
- `KERNEL32!ResetEvent` at `0x1800780f7`
- `KERNEL32!ResetEvent` at `0x1800780f7`
- `MSVCP140!_Mtx_unlock` at `0x180078062`
- `MSVCP140!_Mtx_unlock` at `0x180078107`
- `MSVCP140!_Mtx_unlock` at `0x180078062`
- `MSVCP140!_Mtx_unlock` at `0x180078107`
- `MSVCP140!_Mtx_lock` at `0x180077f11`
- `MSVCP140!_Mtx_lock` at `0x180077f11`
- `MSVCP140!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180077f20`
- `MSVCP140!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180077f40`
- `MSVCP140!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180077f20`
- `MSVCP140!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180077f40`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall GEL::Typeface::GetWidthCache(GEL::Typeface *this, unsigned __int16 a2, int a3, int a4)
{
  int v5; // r15d
  unsigned int v7; // r12d
  bool (__fastcall *v8)(GEL::Typeface *__hidden); // rax
  char v9; // al
  _Mtx_t v10; // rsi
  _Mtx_t v11; // rbx
  int v12; // r13d
  __int64 v13; // r14
  GEL::WidthCache *v14; // rdx
  int v15; // ecx
  GEL::WidthCache *v16; // rdi
  GEL::WidthCache *v17; // rax
  GEL::WidthCache *v18; // rbp
  GEL::WidthCache *v19; // rcx
  GEL::WidthCache *v20; // rsi
  GEL::WidthCache *v21; // rcx
  GEL::WidthCache *v22; // rcx
  unsigned __int64 v24; // rdx
  unsigned __int64 v25; // rax
  __int64 v26; // rax
  GEL::WidthCache *v27; // rcx
  _Mtx_t v28; // [rsp+28h] [rbp-50h] BYREF
  GEL::Typeface *v29; // [rsp+30h] [rbp-48h]
  DWORD CurrentThreadId; // [rsp+80h] [rbp+8h]

  v5 = a2;
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
      v28 = v11;
      v29 = this;
      CurrentThreadId = GetCurrentThreadId();
      v12 = 1;
      v13 = 1;
      while ( 2 )
      {
        if ( _Mtx_lock(v11) )
        {
          std::_Throw_Cpp_error(5);
          __debugbreak();
        }
        if ( *((_DWORD *)v11 + 19) == 0x7FFFFFFF )
        {
          *((_DWORD *)v11 + 19) = 2147483646;
          std::_Throw_Cpp_error(6);
LABEL_14:
          if ( *((_DWORD *)v11 + 2) == v15 )
          {
            if ( v10 )
            {
              v16 = v14;
              v17 = (GEL::WidthCache *)*((_QWORD *)v10 + 2);
              if ( v17 )
              {
                *((_QWORD *)v10 + 2) = v14;
                v16 = v17;
                v17 = v14;
              }
              v18 = (GEL::WidthCache *)*((_QWORD *)v16 + 2);
              if ( v17 != v18 )
              {
                *((_QWORD *)v16 + 2) = v14;
                v19 = (GEL::WidthCache *)*((_QWORD *)v10 + 2);
                if ( v19 )
                {
                  GEL::WidthCache::`scalar deleting destructor'(v19, (unsigned int)v14);
                  v14 = 0;
                }
                *((_QWORD *)v10 + 2) = v18;
              }
              v20 = *(GEL::WidthCache **)v13;
              if ( *((_QWORD *)v16 + 2) != *(_QWORD *)v13 )
              {
                *(_QWORD *)v13 = v14;
                v21 = (GEL::WidthCache *)*((_QWORD *)v16 + 2);
                if ( v21 )
                  GEL::WidthCache::`scalar deleting destructor'(v21, (unsigned int)v14);
                *((_QWORD *)v16 + 2) = v20;
              }
              v22 = *(GEL::WidthCache **)v13;
              if ( *(GEL::WidthCache **)v13 == v16 )
              {
                if ( v16 )
                  GEL::WidthCache::`scalar deleting destructor'(v16, (unsigned int)v14);
              }
              else
              {
                if ( v22 )
                  GEL::WidthCache::`scalar deleting destructor'(v22, (unsigned int)v14);
                *(_QWORD *)v13 = v16;
              }
            }
            v7 = *((_DWORD *)v11 + 3);
          }
          else
          {
            while ( *((_QWORD *)v11 + 2) )
            {
              v10 = v11;
              v11 = (_Mtx_t)*((_QWORD *)v11 + 2);
              ++v12;
LABEL_43:
              if ( *(_WORD *)v11 == (_WORD)v5 && *((_DWORD *)v11 + 1) == a3 )
                goto LABEL_14;
            }
            if ( v12 >= 19 )
            {
              v27 = (GEL::WidthCache *)*((_QWORD *)v10 + 2);
              if ( v27 )
              {
                *((_QWORD *)v10 + 2) = v14;
                GEL::WidthCache::`scalar deleting destructor'(v27, (unsigned int)v14);
              }
            }
          }
        }
        else
        {
          if ( (v13 & 0x3F) == 0 || *((_DWORD *)v11 + 22) > 8u )
            Ofc::CExclusiveAccessMgr2::CleanupOrphanedAccs(v11);
          v24 = *((_QWORD *)v11 + 10);
          v25 = v24 + 24LL * *((unsigned int *)v11 + 22);
          while ( 1 )
          {
            if ( v24 >= v25 )
            {
              if ( *((_DWORD *)v11 + 22) == 8 && *((_Mtx_t *)v11 + 10) == (_Mtx_t)((char *)v11 + 96) )
                Ofc::CArrayImpl::ConvertFixedToVarBuffer(
                  (_Mtx_t)((char *)v11 + 80),
                  0x18u,
                  9u,
                  (void (*)(unsigned __int8 *, unsigned __int8 *, unsigned int))Ofc::TMoveConstructRange<GEL::PANLINK,1>::Do);
              v26 = Ofc::CArrayImpl::NewTop<Ofc::CExclusiveAccessMgr2::AccData>((char *)v11 + 80);
              *(_QWORD *)v26 = v29;
              *(_QWORD *)(v26 + 8) = &v28;
              *(_DWORD *)(v26 + 16) = CurrentThreadId;
              goto LABEL_41;
            }
            if ( *(GEL::Typeface **)v24 == v29 )
              break;
            v24 += 24LL;
          }
          if ( *(_DWORD *)(v24 + 16) != CurrentThreadId )
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
          v13 = *((_QWORD *)this + 14) + 8LL * (int)v10;
          v11 = *(_Mtx_t *)v13;
          if ( *(_QWORD *)v13 )
          {
            v14 = 0;
            v10 = 0;
            v15 = a4;
            goto LABEL_43;
          }
        }
        break;
      }
      Ofc::CExclusiveAccess2::~CExclusiveAccess2((Ofc::CExclusiveAccess2 *)&v28);
    }
  }
  return v7;
}

```

## disassembly

```asm
0x180077e50  mov     [rsp+arg_8], rbx
0x180077e55  mov     [rsp+arg_18], r9d
0x180077e5a  push    rbp
0x180077e5b  push    rsi
0x180077e5c  push    rdi
0x180077e5d  push    r12
0x180077e5f  push    r13
0x180077e61  push    r14
0x180077e63  push    r15
0x180077e65  sub     rsp, 40h
0x180077e69  mov     ebp, r8d
0x180077e6c  movzx   r15d, dx
0x180077e70  mov     rdi, rcx
0x180077e73  mov     r12d, 0FFFFFFFFh
0x180077e79  cmp     qword ptr [rcx+70h], 1
0x180077e7e  jbe     loc_180077FBC
0x180077e84  mov     rax, [rcx]
0x180077e87  mov     rax, [rax+160h]
0x180077e8e  lea     rcx, ?FIsFontInfoCachable@Typeface@GEL@@UEBA_NXZ; GEL::Typeface::FIsFontInfoCachable(void)
0x180077e95  cmp     rax, rcx
0x180077e98  mov     rcx, rdi; this
0x180077e9b  jnz     loc_18007816C
0x180077ea1  call    ?FIsFontInfoCachable@Typeface@GEL@@UEBA_NXZ; GEL::Typeface::FIsFontInfoCachable(void)
0x180077ea6  test    al, al
0x180077ea8  jz      loc_180077FBC
0x180077eae  mov     esi, r15d
0x180077eb1  imul    esi, ebp
0x180077eb4  mov     eax, 7A44C6Bh
0x180077eb9  imul    esi
0x180077ebb  sar     edx, 1
0x180077ebd  mov     eax, edx
0x180077ebf  shr     eax, 1Fh
0x180077ec2  add     edx, eax
0x180077ec4  imul    eax, edx, 43h ; 'C'
0x180077ec7  sub     esi, eax
0x180077ec9  xor     eax, eax
0x180077ecb  test    esi, esi
0x180077ecd  cmovle  esi, eax
0x180077ed0  mov     rbx, cs:?s_pInstance@?$TSingleton@VTypefaceAccessMgr@GEL@@@Ofc@@0PEAVTypefaceAccessMgr@GEL@@EA; GEL::TypefaceAccessMgr * Ofc::TSingleton<GEL::TypefaceAccessMgr>::s_pInstance
0x180077ed7  cmp     rbx, 1
0x180077edb  ja      short loc_180077EE9
0x180077edd  call    ??$ThreadSafeInitPointerOnce@PEAVTypefaceAccessMgr@GEL@@V?$TSingletonFactory@VTypefaceAccessMgr@GEL@@@Ofc@@@Ofc@@YAXPECREAVTypefaceAccessMgr@GEL@@@Z; Ofc::ThreadSafeInitPointerOnce<GEL::TypefaceAccessMgr *,Ofc::TSingletonFactory<GEL::TypefaceAccessMgr>>(GEL::TypefaceAccessMgr * volatile *)
0x180077ee2  mov     rbx, cs:?s_pInstance@?$TSingleton@VTypefaceAccessMgr@GEL@@@Ofc@@0PEAVTypefaceAccessMgr@GEL@@EA; GEL::TypefaceAccessMgr * Ofc::TSingleton<GEL::TypefaceAccessMgr>::s_pInstance
0x180077ee9  mov     [rsp+78h+var_50], rbx
0x180077eee  mov     [rsp+78h+var_48], rdi
0x180077ef3  call    cs:__imp_GetCurrentThreadId
0x180077ef9  mov     [rsp+78h+arg_0], eax
0x180077f00  mov     r13d, 1
0x180077f06  mov     r14d, r13d
0x180077f09  mov     [rsp+78h+var_58], rbx
0x180077f0e  mov     rcx, rbx; _Mtx_t
0x180077f11  call    cs:__imp__Mtx_lock
0x180077f17  test    eax, eax
0x180077f19  jz      short loc_180077F27
0x180077f1b  mov     ecx, 5
0x180077f20  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180077f26  int     3; Trap to Debugger
0x180077f27  cmp     dword ptr [rbx+4Ch], 7FFFFFFFh
0x180077f2e  jnz     loc_180077FFD
0x180077f34  mov     dword ptr [rbx+4Ch], 7FFFFFFEh
0x180077f3b  mov     ecx, 6
0x180077f40  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180077f46  nop
0x180077f47  cmp     [rbx+8], ecx
0x180077f4a  jnz     loc_180078099
0x180077f50  test    rsi, rsi
0x180077f53  jz      short loc_180077FAE
0x180077f55  mov     rdi, rdx
0x180077f58  mov     rax, [rsi+10h]
0x180077f5c  test    rax, rax
0x180077f5f  jz      short loc_180077F6B
0x180077f61  mov     [rsi+10h], rdx
0x180077f65  mov     rdi, rax
0x180077f68  mov     rax, rdx
0x180077f6b  mov     rbp, [rdi+10h]
0x180077f6f  cmp     rax, rbp
0x180077f72  jz      short loc_180077F85
0x180077f74  mov     [rdi+10h], rdx
0x180077f78  mov     rcx, [rsi+10h]; this
0x180077f7c  test    rcx, rcx
0x180077f7f  jnz     short loc_180077FD7
0x180077f81  mov     [rsi+10h], rbp
0x180077f85  mov     rsi, [r14]
0x180077f88  cmp     [rdi+10h], rsi
0x180077f8c  jz      short loc_180077F9E
0x180077f8e  mov     [r14], rdx
0x180077f91  mov     rcx, [rdi+10h]; this
0x180077f95  test    rcx, rcx
0x180077f98  jnz     short loc_180077FE0
0x180077f9a  mov     [rdi+10h], rsi
0x180077f9e  mov     rcx, [r14]; this
0x180077fa1  cmp     rcx, rdi
0x180077fa4  jz      short loc_180077FEE
0x180077fa6  test    rcx, rcx
0x180077fa9  jnz     short loc_180077FE7
0x180077fab  mov     [r14], rdi
0x180077fae  mov     r12d, [rbx+0Ch]
0x180077fb2  lea     rcx, [rsp+78h+var_50]; this
0x180077fb7  call    ??1CExclusiveAccess2@Ofc@@QEAA@XZ; Ofc::CExclusiveAccess2::~CExclusiveAccess2(void)
0x180077fbc  mov     eax, r12d
0x180077fbf  mov     rbx, [rsp+78h+arg_8]
0x180077fc7  add     rsp, 40h
0x180077fcb  pop     r15
0x180077fcd  pop     r14
0x180077fcf  pop     r13
0x180077fd1  pop     r12
0x180077fd3  pop     rdi
0x180077fd4  pop     rsi
0x180077fd5  pop     rbp
0x180077fd6  retn
0x180077fd7  call    ??_GWidthCache@GEL@@QEAAPEAXI@Z; GEL::WidthCache::`scalar deleting destructor'(uint)
0x180077fdc  xor     edx, edx
0x180077fde  jmp     short loc_180077F81
0x180077fe0  call    ??_GWidthCache@GEL@@QEAAPEAXI@Z; GEL::WidthCache::`scalar deleting destructor'(uint)
0x180077fe5  jmp     short loc_180077F9A
0x180077fe7  call    ??_GWidthCache@GEL@@QEAAPEAXI@Z; GEL::WidthCache::`scalar deleting destructor'(uint)
0x180077fec  jmp     short loc_180077FAB
0x180077fee  test    rdi, rdi
0x180077ff1  jz      short loc_180077FAE
0x180077ff3  mov     rcx, rdi; this
0x180077ff6  call    ??_GWidthCache@GEL@@QEAAPEAXI@Z; GEL::WidthCache::`scalar deleting destructor'(uint)
0x180077ffb  jmp     short loc_180077FAE
0x180077ffd  test    r14b, 3Fh
0x180078001  jz      loc_180078131
0x180078007  cmp     dword ptr [rbx+58h], 8
0x18007800b  ja      loc_180078131
0x180078011  mov     rdx, [rbx+50h]
0x180078015  mov     eax, [rbx+58h]
0x180078018  lea     rcx, [rax+rax*2]
0x18007801c  lea     rax, [rdx+rcx*8]
0x180078020  mov     rcx, [rsp+78h+var_48]
0x180078025  cmp     rdx, rax
0x180078028  jb      loc_1800780D2
0x18007802e  cmp     dword ptr [rbx+58h], 8
0x180078032  jz      loc_18007813E
0x180078038  lea     rcx, [rbx+50h]
0x18007803c  call    ??$NewTop@UAccData@CExclusiveAccessMgr2@Ofc@@@CArrayImpl@Ofc@@IEAAAEAUAccData@CExclusiveAccessMgr2@1@XZ; Ofc::CArrayImpl::NewTop<Ofc::CExclusiveAccessMgr2::AccData>(void)
0x180078041  mov     rcx, rax
0x180078044  mov     rax, [rsp+78h+var_48]
0x180078049  mov     [rcx], rax
0x18007804c  lea     rax, [rsp+78h+var_50]
0x180078051  mov     [rcx+8], rax
0x180078055  mov     eax, [rsp+78h+arg_0]
0x18007805c  mov     [rcx+10h], eax
0x18007805f  mov     rcx, rbx; _Mtx_t
0x180078062  call    cs:__imp__Mtx_unlock
0x180078068  movsxd  rcx, esi
0x18007806b  mov     rax, [rdi+70h]
0x18007806f  lea     r14, [rax+rcx*8]
0x180078073  mov     rbx, [r14]
0x180078076  test    rbx, rbx
0x180078079  jz      loc_180077FB2
0x18007807f  xor     edx, edx; unsigned int
0x180078081  mov     esi, edx
0x180078083  mov     ecx, [rsp+78h+arg_18]
0x18007808a  cmp     [rbx], r15w
0x18007808e  jnz     short loc_180078099
0x180078090  cmp     [rbx+4], ebp
0x180078093  jz      loc_180077F47
0x180078099  mov     rax, [rbx+10h]
0x18007809d  test    rax, rax
0x1800780a0  jz      short loc_1800780AD
0x1800780a2  mov     rsi, rbx
0x1800780a5  mov     rbx, rax
0x1800780a8  inc     r13d
0x1800780ab  jmp     short loc_18007808A
0x1800780ad  cmp     r13d, 13h
0x1800780b1  jl      loc_180077FB2
0x1800780b7  mov     rcx, [rsi+10h]; this
0x1800780bb  test    rcx, rcx
0x1800780be  jz      loc_180077FB2
0x1800780c4  mov     [rsi+10h], rdx
0x1800780c8  call    ??_GWidthCache@GEL@@QEAAPEAXI@Z; GEL::WidthCache::`scalar deleting destructor'(uint)
0x1800780cd  jmp     loc_180077FB2
0x1800780d2  cmp     [rdx], rcx
0x1800780d5  jz      short loc_1800780E0
0x1800780d7  add     rdx, 18h
0x1800780db  jmp     loc_180078025
0x1800780e0  mov     eax, [rsp+78h+arg_0]
0x1800780e7  cmp     [rdx+10h], eax
0x1800780ea  jz      loc_18007805F
0x1800780f0  mov     rcx, [rbx+120h]; hEvent
0x1800780f7  call    cs:__imp_ResetEvent
0x1800780fd  lock inc dword ptr [rbx+128h]
0x180078104  mov     rcx, rbx; _Mtx_t
0x180078107  call    cs:__imp__Mtx_unlock
0x18007810d  xor     r8d, r8d; bAlertable
0x180078110  mov     edx, 32h ; '2'; dwMilliseconds
0x180078115  mov     rcx, [rbx+120h]; hHandle
0x18007811c  call    cs:__imp_WaitForSingleObjectEx
0x180078122  lock dec dword ptr [rbx+128h]
0x180078129  inc     r14d
0x18007812c  jmp     loc_180077F0E
0x180078131  mov     rcx, rbx; this
0x180078134  call    ?CleanupOrphanedAccs@CExclusiveAccessMgr2@Ofc@@AEAAXXZ; Ofc::CExclusiveAccessMgr2::CleanupOrphanedAccs(void)
0x180078139  jmp     loc_180078011
0x18007813e  lea     rax, [rbx+60h]
0x180078142  cmp     [rbx+50h], rax
0x180078146  jnz     loc_180078038
0x18007814c  lea     r9, ?Do@?$TMoveConstructRange@UPANLINK@GEL@@$00@Ofc@@SAXPEAE0K@Z; void (*)(unsigned __int8 *, unsigned __int8 *, unsigned int)
0x180078153  mov     edx, 18h; unsigned int
0x180078158  mov     r8d, 9; unsigned int
0x18007815e  lea     rcx, [rbx+50h]; this
0x180078162  call    ?ConvertFixedToVarBuffer@CArrayImpl@Ofc@@IEAAXKKP6AXPEAE0K@Z@Z; Ofc::CArrayImpl::ConvertFixedToVarBuffer(ulong,ulong,void (*)(uchar *,uchar *,ulong))
0x180078167  jmp     loc_180078038
0x18007816c  call    cs:__guard_dispatch_icall_fptr
0x180078172  jmp     loc_180077EA6
```
