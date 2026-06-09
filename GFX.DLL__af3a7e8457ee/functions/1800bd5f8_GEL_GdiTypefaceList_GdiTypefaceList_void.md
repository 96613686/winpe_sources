# GEL::GdiTypefaceList::GdiTypefaceList(void)

- ea: `0x1800bd5f8`
- end: `0x1800bd7d8`
- name: `??0GdiTypefaceList@GEL@@QEAA@XZ`
- size: `480`
- prototype: `__int64 __fastcall(GEL::GdiTypefaceList *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x1800bda30`

## callees

- `0x18000aef0`
- `0x180055b26`
- `0x180055e38`
- `0x180056ee0`
- `0x1800573f0`
- `0x1800795a0`
- `0x1800bd2a4`
- `0x1800bd5f8`
- `0x1800bd7d8`
- `0x1800bd890`
- `0x1800c5f50`
- `0x18010e57c`

## import_xrefs

- `MSVCP140!_Mtx_unlock` at `0x1800bd76e`
- `MSVCP140!_Mtx_unlock` at `0x1800bd76e`
- `mso40uiWin32Client!__imp_?GetGDIAssistant@GDIAssistant@Mso@@YAAEAUIGDIAssistant@12@XZ` at `0x1800bd6cd`
- `mso40uiWin32Client!__imp_?GetGDIAssistant@GDIAssistant@Mso@@YAAEAUIGDIAssistant@12@XZ` at `0x1800bd6cd`
- `GDI32!CreateDCW` at `0x1800bd65c`
- `GDI32!CreateDCW` at `0x1800bd65c`
- `GDI32!CreateICW` at `0x1800bd7af`
- `GDI32!CreateICW` at `0x1800bd7af`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
GEL::GdiTypefaceList *__fastcall GEL::GdiTypefaceList::GdiTypefaceList(GEL::GdiTypefaceList *this)
{
  Mso::GDIAssistant *v2; // rcx
  struct Mso::GDIAssistant::IGDIAssistant *GDIAssistant; // r9
  void (__fastcall *v4)(struct Mso::GDIAssistant::IGDIAssistant *, _QWORD *, _QWORD *); // rax
  _QWORD *v5; // rdx
  std::_Mutex_base *v6; // rdi
  __int64 v7; // rbx
  HDC ICW; // rbx
  _QWORD v10[4]; // [rsp+28h] [rbp-29h] BYREF
  _QWORD v11[7]; // [rsp+48h] [rbp-9h] BYREF
  _QWORD *v12; // [rsp+80h] [rbp+2Fh]

  v10[1] = this;
  GEL::TypefaceList::TypefaceList(this);
  *(_QWORD *)this = &GEL::GdiTypefaceList::`vftable'{for `GEL::TypefaceList'};
  *((_QWORD *)this + 15) = &GEL::GdiTypefaceList::`vftable'{for `GEL::ITypefaceEnumerator'};
  *((_QWORD *)this + 17) = CreateDCW(L"DISPLAY", 0, 0, 0);
  std::_Mutex_base::_Mutex_base((GEL::GdiTypefaceList *)((char *)this + 144), 256);
  memset_0((char *)this + 224, 0, 0x5Cu);
  *((_QWORD *)this + 40) = 0;
  *((_QWORD *)this + 41) = 0;
  *((_QWORD *)this + 42) = 0;
  *((_BYTE *)this + 344) = 0;
  v10[2] = (char *)this + 136;
  v10[3] = (char *)this + 144;
  std::_Mutex_base::lock((GEL::GdiTypefaceList *)((char *)this + 144));
  if ( !*((_QWORD *)this + 17) )
  {
    ICW = CreateICW(L"DISPLAY", 0, 0, 0);
    ARC::GDIPlus::TGDIHolder<HDC__ *>::Empty((char *)this + 136);
    *((_QWORD *)this + 17) = ICW;
    if ( !ICW )
    {
      Ofc::CLastErrorException::ThrowTag(0x2CA522u);
      __debugbreak();
    }
  }
  GDIAssistant = Mso::GDIAssistant::GetGDIAssistant(v2);
  v4 = *(void (__fastcall **)(struct Mso::GDIAssistant::IGDIAssistant *, _QWORD *, _QWORD *))(*(_QWORD *)GDIAssistant
                                                                                            + 40LL);
  v11[0] = off_180474E40;
  v12 = v11;
  v4(GDIAssistant, v10, v11);
  if ( v12 )
  {
    v5 = v11;
    LOBYTE(v5) = v12 != v11;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v12 + 32LL))(v12, v5);
  }
  v6 = (std::_Mutex_base *)Ofc::TSingleton<GEL::TypefaceArrayCache>::Instance();
  Mso::Make<GEL::GdiTypefaceEnumerator,GEL::GdiTypefaceEnumerator,GEL::GdiTypefaceList &,ARC::GDIPlus::TGDIHolder<HDC__ *> &>(
    v10,
    this,
    (char *)this + 136);
  v7 = v10[0];
  *((_QWORD *)this + 14) = GEL::TypefaceArrayCache::GetTypefaces(v6);
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7);
  _Mtx_unlock((GEL::GdiTypefaceList *)((char *)this + 144));
  return this;
}

```

## disassembly

```asm
0x1800bd5f8  mov     rax, rsp
0x1800bd5fb  mov     [rax+10h], rbx
0x1800bd5ff  mov     [rax+18h], rsi
0x1800bd603  mov     [rax+20h], rdi
0x1800bd607  push    rbp
0x1800bd608  push    r14
0x1800bd60a  push    r15
0x1800bd60c  lea     rbp, [rax-5Fh]
0x1800bd610  sub     rsp, 90h
0x1800bd617  mov     rax, cs:__security_cookie
0x1800bd61e  xor     rax, rsp
0x1800bd621  mov     [rbp+57h+var_20], rax
0x1800bd625  mov     rsi, rcx
0x1800bd628  mov     [rbp+57h+var_78], rcx
0x1800bd62c  call    ??0TypefaceList@GEL@@IEAA@XZ; GEL::TypefaceList::TypefaceList(void)
0x1800bd631  lea     rax, ??_7GdiTypefaceList@GEL@@6BTypefaceList@1@@; const GEL::GdiTypefaceList::`vftable'{for `GEL::TypefaceList'}
0x1800bd638  mov     [rsi], rax
0x1800bd63b  lea     rax, ??_7GdiTypefaceList@GEL@@6BITypefaceEnumerator@1@@; const GEL::GdiTypefaceList::`vftable'{for `GEL::ITypefaceEnumerator'}
0x1800bd642  mov     [rsi+78h], rax
0x1800bd646  lea     r14, [rsi+88h]
0x1800bd64d  xor     r9d, r9d; pdm
0x1800bd650  xor     r8d, r8d; pszPort
0x1800bd653  xor     edx, edx; pwszDevice
0x1800bd655  lea     rcx, pszDriver; "DISPLAY"
0x1800bd65c  call    cs:__imp_CreateDCW
0x1800bd662  mov     [r14], rax
0x1800bd665  lea     r15, [rsi+90h]
0x1800bd66c  mov     edx, 100h; int
0x1800bd671  mov     rcx, r15; this
0x1800bd674  call    ??0_Mutex_base@std@@QEAA@H@Z; std::_Mutex_base::_Mutex_base(int)
0x1800bd679  lea     rcx, [rsi+0E0h]; void *
0x1800bd680  xor     edx, edx; Val
0x1800bd682  lea     r8d, [rdx+5Ch]; Size
0x1800bd686  call    memset_0
0x1800bd68b  mov     qword ptr [rsi+140h], 0
0x1800bd696  mov     qword ptr [rsi+148h], 0
0x1800bd6a1  mov     qword ptr [rsi+150h], 0
0x1800bd6ac  mov     byte ptr [rsi+158h], 0
0x1800bd6b3  mov     [rbp+57h+var_70], r14
0x1800bd6b7  mov     [rbp+57h+var_68], r15
0x1800bd6bb  mov     rcx, r15; this
0x1800bd6be  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1800bd6c3  cmp     qword ptr [r14], 0
0x1800bd6c7  jz      loc_1800BD7A0
0x1800bd6cd  call    cs:__imp_?GetGDIAssistant@GDIAssistant@Mso@@YAAEAUIGDIAssistant@12@XZ; Mso::GDIAssistant::GetGDIAssistant(void)
0x1800bd6d3  mov     r9, rax
0x1800bd6d6  mov     rcx, [rax]
0x1800bd6d9  mov     rax, [rcx+28h]
0x1800bd6dd  lea     rcx, off_180474E40
0x1800bd6e4  mov     [rbp+57h+var_60], rcx
0x1800bd6e8  lea     rcx, [rbp+57h+var_60]
0x1800bd6ec  mov     [rbp+57h+var_28], rcx
0x1800bd6f0  lea     r8, [rbp+57h+var_60]
0x1800bd6f4  lea     rdx, [rbp+57h+var_80]
0x1800bd6f8  mov     rcx, r9
0x1800bd6fb  call    cs:__guard_dispatch_icall_fptr
0x1800bd701  mov     rcx, [rbp+57h+var_28]
0x1800bd705  test    rcx, rcx
0x1800bd708  jz      short loc_1800BD721
0x1800bd70a  mov     rax, [rcx]
0x1800bd70d  lea     rdx, [rbp+57h+var_60]
0x1800bd711  cmp     rcx, rdx
0x1800bd714  setnz   dl
0x1800bd717  mov     rax, [rax+20h]
0x1800bd71b  call    cs:__guard_dispatch_icall_fptr
0x1800bd721  call    ?Instance@?$TSingleton@VTypefaceArrayCache@GEL@@@Ofc@@SAAEAVTypefaceArrayCache@GEL@@XZ; Ofc::TSingleton<GEL::TypefaceArrayCache>::Instance(void)
0x1800bd726  mov     rdi, rax
0x1800bd729  mov     r8, r14
0x1800bd72c  mov     rdx, rsi
0x1800bd72f  lea     rcx, [rbp+57h+var_80]
0x1800bd733  call    ??$Make@VGdiTypefaceEnumerator@GEL@@V12@AEAVGdiTypefaceList@2@AEAV?$TGDIHolder@PEAUHDC__@@@GDIPlus@ARC@@@Mso@@YA?AV?$TCntPtr@VGdiTypefaceEnumerator@GEL@@@0@AEAVGdiTypefaceList@GEL@@AEAV?$TGDIHolder@PEAUHDC__@@@GDIPlus@ARC@@@Z; Mso::Make<GEL::GdiTypefaceEnumerator,GEL::GdiTypefaceEnumerator,GEL::GdiTypefaceList &,ARC::GDIPlus::TGDIHolder<HDC__ *> &>(GEL::GdiTypefaceList &,ARC::GDIPlus::TGDIHolder<HDC__ *> &)
0x1800bd738  xor     r9d, r9d
0x1800bd73b  lea     r8, pszDriver; "DISPLAY"
0x1800bd742  mov     rbx, [rbp+57h+var_80]
0x1800bd746  mov     rdx, rbx
0x1800bd749  mov     rcx, rdi; this
0x1800bd74c  call    ?GetTypefaces@TypefaceArrayCache@GEL@@QEAAAEBV?$TArray@V?$TCntPtr@UITypeface@GEL@@@Ofc@@@Ofc@@AEAUITypefaceEnumerator@2@PEB_W1@Z; GEL::TypefaceArrayCache::GetTypefaces(GEL::ITypefaceEnumerator &,wchar_t const *,wchar_t const *)
0x1800bd751  mov     [rsi+70h], rax
0x1800bd755  test    rbx, rbx
0x1800bd758  jz      short loc_1800BD76B
0x1800bd75a  mov     rdx, [rbx]
0x1800bd75d  mov     rcx, rbx
0x1800bd760  mov     rax, [rdx+8]
0x1800bd764  call    cs:__guard_dispatch_icall_fptr
0x1800bd76a  nop
0x1800bd76b  mov     rcx, r15; _Mtx_t
0x1800bd76e  call    cs:__imp__Mtx_unlock
0x1800bd774  mov     rax, rsi
0x1800bd777  mov     rcx, [rbp+57h+var_20]
0x1800bd77b  xor     rcx, rsp; StackCookie
0x1800bd77e  call    __security_check_cookie
0x1800bd783  lea     r11, [rsp+0A0h+var_10]
0x1800bd78b  mov     rbx, [r11+28h]
0x1800bd78f  mov     rsi, [r11+30h]
0x1800bd793  mov     rdi, [r11+38h]
0x1800bd797  mov     rsp, r11
0x1800bd79a  pop     r15
0x1800bd79c  pop     r14
0x1800bd79e  pop     rbp
0x1800bd79f  retn
0x1800bd7a0  xor     r9d, r9d; pdm
0x1800bd7a3  xor     r8d, r8d; pszPort
0x1800bd7a6  xor     edx, edx; pszDevice
0x1800bd7a8  lea     rcx, pszDriver; "DISPLAY"
0x1800bd7af  call    cs:__imp_CreateICW
0x1800bd7b5  mov     rbx, rax
0x1800bd7b8  mov     rcx, r14
0x1800bd7bb  call    ?Empty@?$TGDIHolder@PEAUHDC__@@@GDIPlus@ARC@@QEAAXXZ; ARC::GDIPlus::TGDIHolder<HDC__ *>::Empty(void)
0x1800bd7c0  mov     [r14], rbx
0x1800bd7c3  cmp     rbx, 0
0x1800bd7c7  jnz     loc_1800BD6CD
0x1800bd7cd  mov     ecx, 2CA522h; unsigned int
0x1800bd7d2  call    ?ThrowTag@CLastErrorException@Ofc@@SAXK@Z; Ofc::CLastErrorException::ThrowTag(ulong)
0x1800bd7d7  int     3; Trap to Debugger
```
