# GEL::GdiTypefaceList::GdiTypefaceList(void)

- ea: `0x1800f5f08`
- end: `0x1800f60e8`
- name: `??0GdiTypefaceList@GEL@@QEAA@XZ`
- size: `480`
- prototype: `__int64 __fastcall(GEL::GdiTypefaceList *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x1800f7c7c`

## callees

- `0x18000aeb0`
- `0x1800565ba`
- `0x180056754`
- `0x1800578b0`
- `0x180057e70`
- `0x180076df0`
- `0x1800beb6c`
- `0x1800cb9c0`
- `0x1800f552c`
- `0x1800f5f08`
- `0x1800f60e8`
- `0x1800f633c`

## import_xrefs

- `MSVCP140!_Mtx_unlock` at `0x1800f607e`
- `MSVCP140!_Mtx_unlock` at `0x1800f607e`
- `mso40uiWin32Client!__imp_?GetGDIAssistant@GDIAssistant@Mso@@YAAEAUIGDIAssistant@12@XZ` at `0x1800f5fdd`
- `mso40uiWin32Client!__imp_?GetGDIAssistant@GDIAssistant@Mso@@YAAEAUIGDIAssistant@12@XZ` at `0x1800f5fdd`
- `GDI32!CreateDCW` at `0x1800f5f6c`
- `GDI32!CreateDCW` at `0x1800f5f6c`
- `GDI32!CreateICW` at `0x1800f60bf`
- `GDI32!CreateICW` at `0x1800f60bf`

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
  v11[0] = off_18047A598;
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
0x1800f5f08  mov     rax, rsp
0x1800f5f0b  mov     [rax+10h], rbx
0x1800f5f0f  mov     [rax+18h], rsi
0x1800f5f13  mov     [rax+20h], rdi
0x1800f5f17  push    rbp
0x1800f5f18  push    r14
0x1800f5f1a  push    r15
0x1800f5f1c  lea     rbp, [rax-5Fh]
0x1800f5f20  sub     rsp, 90h
0x1800f5f27  mov     rax, cs:__security_cookie
0x1800f5f2e  xor     rax, rsp
0x1800f5f31  mov     [rbp+57h+var_20], rax
0x1800f5f35  mov     rsi, rcx
0x1800f5f38  mov     [rbp+57h+var_78], rcx
0x1800f5f3c  call    ??0TypefaceList@GEL@@IEAA@XZ; GEL::TypefaceList::TypefaceList(void)
0x1800f5f41  lea     rax, ??_7GdiTypefaceList@GEL@@6BTypefaceList@1@@; const GEL::GdiTypefaceList::`vftable'{for `GEL::TypefaceList'}
0x1800f5f48  mov     [rsi], rax
0x1800f5f4b  lea     rax, ??_7GdiTypefaceList@GEL@@6BITypefaceEnumerator@1@@; const GEL::GdiTypefaceList::`vftable'{for `GEL::ITypefaceEnumerator'}
0x1800f5f52  mov     [rsi+78h], rax
0x1800f5f56  lea     r14, [rsi+88h]
0x1800f5f5d  xor     r9d, r9d; pdm
0x1800f5f60  xor     r8d, r8d; pszPort
0x1800f5f63  xor     edx, edx; pwszDevice
0x1800f5f65  lea     rcx, pszDriver; "DISPLAY"
0x1800f5f6c  call    cs:__imp_CreateDCW
0x1800f5f72  mov     [r14], rax
0x1800f5f75  lea     r15, [rsi+90h]
0x1800f5f7c  mov     edx, 100h; int
0x1800f5f81  mov     rcx, r15; this
0x1800f5f84  call    ??0_Mutex_base@std@@QEAA@H@Z; std::_Mutex_base::_Mutex_base(int)
0x1800f5f89  lea     rcx, [rsi+0E0h]; void *
0x1800f5f90  xor     edx, edx; Val
0x1800f5f92  lea     r8d, [rdx+5Ch]; Size
0x1800f5f96  call    memset_0
0x1800f5f9b  mov     qword ptr [rsi+140h], 0
0x1800f5fa6  mov     qword ptr [rsi+148h], 0
0x1800f5fb1  mov     qword ptr [rsi+150h], 0
0x1800f5fbc  mov     byte ptr [rsi+158h], 0
0x1800f5fc3  mov     [rbp+57h+var_70], r14
0x1800f5fc7  mov     [rbp+57h+var_68], r15
0x1800f5fcb  mov     rcx, r15; this
0x1800f5fce  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1800f5fd3  cmp     qword ptr [r14], 0
0x1800f5fd7  jz      loc_1800F60B0
0x1800f5fdd  call    cs:__imp_?GetGDIAssistant@GDIAssistant@Mso@@YAAEAUIGDIAssistant@12@XZ; Mso::GDIAssistant::GetGDIAssistant(void)
0x1800f5fe3  mov     r9, rax
0x1800f5fe6  mov     rcx, [rax]
0x1800f5fe9  mov     rax, [rcx+28h]
0x1800f5fed  lea     rcx, off_18047A598
0x1800f5ff4  mov     [rbp+57h+var_60], rcx
0x1800f5ff8  lea     rcx, [rbp+57h+var_60]
0x1800f5ffc  mov     [rbp+57h+var_28], rcx
0x1800f6000  lea     r8, [rbp+57h+var_60]
0x1800f6004  lea     rdx, [rbp+57h+var_80]
0x1800f6008  mov     rcx, r9
0x1800f600b  call    cs:__guard_dispatch_icall_fptr
0x1800f6011  mov     rcx, [rbp+57h+var_28]
0x1800f6015  test    rcx, rcx
0x1800f6018  jz      short loc_1800F6031
0x1800f601a  mov     rax, [rcx]
0x1800f601d  lea     rdx, [rbp+57h+var_60]
0x1800f6021  cmp     rcx, rdx
0x1800f6024  setnz   dl
0x1800f6027  mov     rax, [rax+20h]
0x1800f602b  call    cs:__guard_dispatch_icall_fptr
0x1800f6031  call    ?Instance@?$TSingleton@VTypefaceArrayCache@GEL@@@Ofc@@SAAEAVTypefaceArrayCache@GEL@@XZ; Ofc::TSingleton<GEL::TypefaceArrayCache>::Instance(void)
0x1800f6036  mov     rdi, rax
0x1800f6039  mov     r8, r14
0x1800f603c  mov     rdx, rsi
0x1800f603f  lea     rcx, [rbp+57h+var_80]
0x1800f6043  call    ??$Make@VGdiTypefaceEnumerator@GEL@@V12@AEAVGdiTypefaceList@2@AEAV?$TGDIHolder@PEAUHDC__@@@GDIPlus@ARC@@@Mso@@YA?AV?$TCntPtr@VGdiTypefaceEnumerator@GEL@@@0@AEAVGdiTypefaceList@GEL@@AEAV?$TGDIHolder@PEAUHDC__@@@GDIPlus@ARC@@@Z; Mso::Make<GEL::GdiTypefaceEnumerator,GEL::GdiTypefaceEnumerator,GEL::GdiTypefaceList &,ARC::GDIPlus::TGDIHolder<HDC__ *> &>(GEL::GdiTypefaceList &,ARC::GDIPlus::TGDIHolder<HDC__ *> &)
0x1800f6048  xor     r9d, r9d
0x1800f604b  lea     r8, pszDriver; "DISPLAY"
0x1800f6052  mov     rbx, [rbp+57h+var_80]
0x1800f6056  mov     rdx, rbx
0x1800f6059  mov     rcx, rdi; this
0x1800f605c  call    ?GetTypefaces@TypefaceArrayCache@GEL@@QEAAAEBV?$TArray@V?$TCntPtr@UITypeface@GEL@@@Ofc@@@Ofc@@AEAUITypefaceEnumerator@2@PEB_W1@Z; GEL::TypefaceArrayCache::GetTypefaces(GEL::ITypefaceEnumerator &,wchar_t const *,wchar_t const *)
0x1800f6061  mov     [rsi+70h], rax
0x1800f6065  test    rbx, rbx
0x1800f6068  jz      short loc_1800F607B
0x1800f606a  mov     rdx, [rbx]
0x1800f606d  mov     rcx, rbx
0x1800f6070  mov     rax, [rdx+8]
0x1800f6074  call    cs:__guard_dispatch_icall_fptr
0x1800f607a  nop
0x1800f607b  mov     rcx, r15; _Mtx_t
0x1800f607e  call    cs:__imp__Mtx_unlock
0x1800f6084  mov     rax, rsi
0x1800f6087  mov     rcx, [rbp+57h+var_20]
0x1800f608b  xor     rcx, rsp; StackCookie
0x1800f608e  call    __security_check_cookie
0x1800f6093  lea     r11, [rsp+0A0h+var_10]
0x1800f609b  mov     rbx, [r11+28h]
0x1800f609f  mov     rsi, [r11+30h]
0x1800f60a3  mov     rdi, [r11+38h]
0x1800f60a7  mov     rsp, r11
0x1800f60aa  pop     r15
0x1800f60ac  pop     r14
0x1800f60ae  pop     rbp
0x1800f60af  retn
0x1800f60b0  xor     r9d, r9d; pdm
0x1800f60b3  xor     r8d, r8d; pszPort
0x1800f60b6  xor     edx, edx; pszDevice
0x1800f60b8  lea     rcx, pszDriver; "DISPLAY"
0x1800f60bf  call    cs:__imp_CreateICW
0x1800f60c5  mov     rbx, rax
0x1800f60c8  mov     rcx, r14
0x1800f60cb  call    ?Empty@?$TGDIHolder@PEAUHDC__@@@GDIPlus@ARC@@QEAAXXZ; ARC::GDIPlus::TGDIHolder<HDC__ *>::Empty(void)
0x1800f60d0  mov     [r14], rbx
0x1800f60d3  cmp     rbx, 0
0x1800f60d7  jnz     loc_1800F5FDD
0x1800f60dd  mov     ecx, 2CA522h; unsigned int
0x1800f60e2  call    ?ThrowTag@CLastErrorException@Ofc@@SAXK@Z; Ofc::CLastErrorException::ThrowTag(ulong)
0x1800f60e7  int     3; Trap to Debugger
```
