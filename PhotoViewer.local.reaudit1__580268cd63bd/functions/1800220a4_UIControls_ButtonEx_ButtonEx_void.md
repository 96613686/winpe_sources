# UIControls::ButtonEx::ButtonEx(void)

- ea: `0x1800220a4`
- end: `0x180022360`
- name: `??0ButtonEx@UIControls@@QEAA@XZ`
- size: `700`
- prototype: `__int64 __fastcall(UIControls::ButtonEx *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180021f90`
- `0x1800715d4`

## callees

- `0x1800220a4`
- `0x180080010`

## import_xrefs

- `USER32!SystemParametersInfoW` at `0x1800221a4`
- `USER32!SystemParametersInfoW` at `0x1800221a4`
- `USER32!DefWindowProcW` at `0x1800220c5`
- `gdiplus!GdipStringFormatGetGenericTypographic` at `0x1800222f1`
- `gdiplus!GdipStringFormatGetGenericTypographic` at `0x1800222f1`
- `gdiplus!GdiplusStartup` at `0x180022130`
- `gdiplus!GdiplusStartup` at `0x180022130`
- `gdiplus!GdipCloneStringFormat` at `0x18002230a`
- `gdiplus!GdipCloneStringFormat` at `0x18002230a`
- `gdiplus!GdipSetStringFormatTrimming` at `0x180022346`
- `gdiplus!GdipSetStringFormatTrimming` at `0x180022346`
- `PhotoBase!?GetBaseStringManager@String@Base@@SAAEAVCAtlStringMgr@ATL@@XZ` at `0x180022211`
- `PhotoBase!?GetBaseStringManager@String@Base@@SAAEAVCAtlStringMgr@ATL@@XZ` at `0x180022211`
- `PhotoBase!?BaseAtlThrow@ATL@@YAXJ@Z` at `0x180022224`
- `PhotoBase!?BaseAtlThrow@ATL@@YAXJ@Z` at `0x180022224`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
UIControls::ButtonEx *__fastcall UIControls::ButtonEx::ButtonEx(UIControls::ButtonEx *this)
{
  __int64 v2; // rdx
  __int64 v3; // rcx
  int v4; // eax
  __int64 BaseStringManager; // rax
  int v6; // eax
  int v8; // [rsp+20h] [rbp-48h] BYREF
  __int64 v9; // [rsp+28h] [rbp-40h]
  __int64 v10; // [rsp+30h] [rbp-38h]

  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_DWORD *)this + 14) = 0;
  *((_QWORD *)this + 8) = DefWindowProcW;
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 9) = &UIBase::ShowFocusSetter::`vftable';
  *((_QWORD *)this + 10) = (char *)this + 8;
  *((_WORD *)this + 44) = 0;
  *((_QWORD *)this + 17) = 0;
  *((_WORD *)this + 72) = 0;
  *((_BYTE *)this + 152) = 1;
  *((_QWORD *)this + 12) = &UIBase::WantWmMouseLeave::`vftable';
  *((_QWORD *)this + 13) = (char *)this + 8;
  *((_BYTE *)this + 112) = 0;
  v8 = 1;
  v9 = 0;
  v10 = 0;
  GdiplusStartup((char *)this + 160, &v8, 0);
  *(_QWORD *)this = &UIControls::ButtonEx::`vftable'{for `ATL::CWindowImpl<UIControls::ButtonEx,ATL::CWindow,ATL::CWinTraits<1409351680,0>>'};
  *((_QWORD *)this + 9) = &UIControls::ButtonEx::`vftable'{for `UIBase::ShowFocusSetter'};
  *((_QWORD *)this + 12) = &UIControls::BitMapOnlyButtonTransparentBack::`vftable'{for `UIBase::WantWmMouseLeave'};
  *((_DWORD *)this + 42) = 0x1000000;
  *((_DWORD *)this + 43) = 1;
  *((_QWORD *)this + 22) = 0;
  *((_DWORD *)this + 46) = 0;
  *((_QWORD *)this + 24) = 0;
  *((_DWORD *)this + 52) = 1;
  if ( !byte_1800A41F4 )
  {
    SystemParametersInfoW(0x1Fu, 0x5Cu, qword_1800A4198, 0);
    byte_1800A41F4 = 1;
  }
  if ( !qword_1800A4408 )
  {
    v4 = 0;
    if ( byte_1800A41AC )
      v4 = 2;
    if ( dword_1800A41A8 >= 700 )
      v4 |= 1u;
    qword_1800A4408 = (__int64)qword_1800A4198;
    dword_1800A4410 = v4;
  }
  ++dword_1800A43F8;
  *((_QWORD *)this + 27) = &dword_1800A43F8;
  *((_QWORD *)this + 28) = 0;
  *((_QWORD *)this + 29) = 0;
  *((_DWORD *)this + 60) = 0;
  BaseStringManager = Base::String::GetBaseStringManager(v3, v2);
  if ( !BaseStringManager )
  {
    ATL::BaseAtlThrow(-2147467259);
    __debugbreak();
  }
  *((_QWORD *)this + 31) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)BaseStringManager + 24LL))(BaseStringManager)
                         + 24;
  *((_DWORD *)this + 64) = 2;
  *((_DWORD *)this + 66) = -1;
  *((_BYTE *)this + 268) = 0;
  *((_OWORD *)this + 17) = 0;
  *((_OWORD *)this + 18) = 0;
  *(_OWORD *)((char *)this + 300) = 0;
  *((_QWORD *)this + 40) = 0;
  *((_QWORD *)this + 41) = 0;
  *((_QWORD *)this + 42) = 0;
  *(_OWORD *)((char *)this + 344) = 0;
  *(_OWORD *)((char *)this + 360) = 0;
  *(_OWORD *)((char *)this + 372) = 0;
  *((_QWORD *)this + 49) = 0;
  *((_QWORD *)this + 50) = 0;
  *((_QWORD *)this + 51) = 0;
  *((_OWORD *)this + 26) = 0;
  *((_OWORD *)this + 27) = 0;
  *(_OWORD *)((char *)this + 444) = 0;
  *((_QWORD *)this + 58) = 0;
  *((_QWORD *)this + 59) = 0;
  *((_QWORD *)this + 60) = 0;
  *((_DWORD *)this + 122) = 0;
  dword_1800A46F8 = GdipStringFormatGetGenericTypographic(&qword_1800A46F0);
  *((_QWORD *)this + 62) = 0;
  *((_DWORD *)this + 126) = GdipCloneStringFormat(qword_1800A46F0, (char *)this + 496);
  *((_BYTE *)this + 520) = 1;
  *(_QWORD *)((char *)this + 524) = 0;
  *((_DWORD *)this + 133) = 0;
  *((_WORD *)this + 268) = 256;
  *((_QWORD *)this + 25) = 0;
  *((_QWORD *)this + 64) = 0;
  v6 = GdipSetStringFormatTrimming(*((_QWORD *)this + 62), 3);
  if ( v6 )
    *((_DWORD *)this + 126) = v6;
  return this;
}

```

## disassembly

```asm
0x1800220a4  push    rbx
0x1800220a6  push    rsi
0x1800220a7  push    rdi
0x1800220a8  push    r14
0x1800220aa  sub     rsp, 48h
0x1800220ae  mov     rbx, rcx
0x1800220b1  lea     rdx, [rcx+8]
0x1800220b5  xor     esi, esi
0x1800220b7  mov     [rdx], rsi
0x1800220ba  mov     [rcx+28h], rsi
0x1800220be  mov     [rcx+30h], rsi
0x1800220c2  mov     [rcx+38h], esi
0x1800220c5  mov     rax, cs:__imp_DefWindowProcW
0x1800220cc  mov     [rcx+40h], rax
0x1800220d0  mov     [rcx+78h], rsi
0x1800220d4  lea     rax, ??_7ShowFocusSetter@UIBase@@6B@; const UIBase::ShowFocusSetter::`vftable'
0x1800220db  mov     [rcx+48h], rax
0x1800220df  mov     [rcx+50h], rdx
0x1800220e3  mov     [rcx+58h], si
0x1800220e7  mov     [rcx+88h], rsi
0x1800220ee  mov     [rcx+90h], si
0x1800220f5  mov     byte ptr [rcx+98h], 1
0x1800220fc  lea     rax, ??_7WantWmMouseLeave@UIBase@@6B@; const UIBase::WantWmMouseLeave::`vftable'
0x180022103  mov     [rcx+60h], rax
0x180022107  mov     [rcx+68h], rdx
0x18002210b  mov     [rcx+70h], sil
0x18002210f  mov     [rsp+68h+var_48], 1
0x180022117  mov     [rsp+68h+var_40], rsi
0x18002211c  mov     [rsp+68h+var_38], rsi
0x180022121  add     rcx, 0A0h
0x180022128  xor     r8d, r8d
0x18002212b  lea     rdx, [rsp+68h+var_48]
0x180022130  call    cs:__imp_GdiplusStartup
0x180022136  lea     rax, ??_7ButtonEx@UIControls@@6B?$CWindowImpl@VButtonEx@UIControls@@VCWindow@ATL@@V?$CWinTraits@$0FEABAAAA@$0A@@4@@ATL@@@; const UIControls::ButtonEx::`vftable'{for `ATL::CWindowImpl<UIControls::ButtonEx,ATL::CWindow,ATL::CWinTraits<1409351680,0>>'}
0x18002213d  mov     [rbx], rax
0x180022140  lea     rax, ??_7ButtonEx@UIControls@@6BShowFocusSetter@UIBase@@@; const UIControls::ButtonEx::`vftable'{for `UIBase::ShowFocusSetter'}
0x180022147  mov     [rbx+48h], rax
0x18002214b  lea     rax, ??_7BitMapOnlyButtonTransparentBack@UIControls@@6BWantWmMouseLeave@UIBase@@@; const UIControls::BitMapOnlyButtonTransparentBack::`vftable'{for `UIBase::WantWmMouseLeave'}
0x180022152  mov     [rbx+60h], rax
0x180022156  mov     dword ptr [rbx+0A8h], 1000000h
0x180022160  mov     dword ptr [rbx+0ACh], 1
0x18002216a  mov     [rbx+0B0h], rsi
0x180022171  mov     [rbx+0B8h], esi
0x180022177  mov     [rbx+0C0h], rsi
0x18002217e  mov     dword ptr [rbx+0D0h], 1
0x180022188  lea     rdi, qword_1800A4198
0x18002218f  cmp     cs:byte_1800A41F4, sil
0x180022196  jnz     short loc_1800221B1
0x180022198  xor     r9d, r9d; fWinIni
0x18002219b  mov     r8, rdi; pvParam
0x18002219e  lea     edx, [rsi+5Ch]; uiParam
0x1800221a1  lea     ecx, [rsi+1Fh]; uiAction
0x1800221a4  call    cs:__imp_SystemParametersInfoW
0x1800221aa  mov     cs:byte_1800A41F4, 1
0x1800221b1  mov     r14d, 2
0x1800221b7  cmp     cs:qword_1800A4408, rsi
0x1800221be  jnz     short loc_1800221E9
0x1800221c0  mov     eax, esi
0x1800221c2  cmp     cs:byte_1800A41AC, sil
0x1800221c9  cmovnz  eax, r14d
0x1800221cd  cmp     cs:dword_1800A41A8, 2BCh
0x1800221d7  jl      short loc_1800221DC
0x1800221d9  or      eax, 1
0x1800221dc  mov     cs:qword_1800A4408, rdi
0x1800221e3  mov     cs:dword_1800A4410, eax
0x1800221e9  inc     cs:dword_1800A43F8
0x1800221ef  lea     rax, dword_1800A43F8
0x1800221f6  mov     [rbx+0D8h], rax
0x1800221fd  mov     [rbx+0E0h], rsi
0x180022204  mov     [rbx+0E8h], rsi
0x18002220b  mov     [rbx+0F0h], esi
0x180022211  call    cs:__imp_?GetBaseStringManager@String@Base@@SAAEAVCAtlStringMgr@ATL@@XZ; Base::String::GetBaseStringManager(void)
0x180022217  mov     rcx, rax
0x18002221a  test    rax, rax
0x18002221d  jnz     short loc_18002222B
0x18002221f  mov     ecx, 80004005h
0x180022224  call    cs:__imp_?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x18002222a  int     3; Trap to Debugger
0x18002222b  mov     rax, [rax]
0x18002222e  mov     rax, [rax+18h]
0x180022232  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022237  add     rax, 18h
0x18002223b  mov     [rbx+0F8h], rax
0x180022242  mov     [rbx+100h], r14d
0x180022249  mov     dword ptr [rbx+108h], 0FFFFFFFFh
0x180022253  mov     [rbx+10Ch], sil
0x18002225a  xorps   xmm0, xmm0
0x18002225d  xor     eax, eax
0x18002225f  movups  xmmword ptr [rbx+110h], xmm0
0x180022266  movups  xmmword ptr [rbx+120h], xmm0
0x18002226d  movups  xmmword ptr [rbx+12Ch], xmm0
0x180022274  mov     [rbx+140h], rsi
0x18002227b  mov     [rbx+148h], rsi
0x180022282  mov     [rbx+150h], rsi
0x180022289  movups  xmmword ptr [rbx+158h], xmm0
0x180022290  movups  xmmword ptr [rbx+168h], xmm0
0x180022297  movups  xmmword ptr [rbx+174h], xmm0
0x18002229e  mov     [rbx+188h], rsi
0x1800222a5  mov     [rbx+190h], rsi
0x1800222ac  mov     [rbx+198h], rsi
0x1800222b3  movups  xmmword ptr [rbx+1A0h], xmm0
0x1800222ba  movups  xmmword ptr [rbx+1B0h], xmm0
0x1800222c1  movups  xmmword ptr [rbx+1BCh], xmm0
0x1800222c8  mov     [rbx+1D0h], rsi
0x1800222cf  mov     [rbx+1D8h], rsi
0x1800222d6  mov     [rbx+1E0h], rsi
0x1800222dd  mov     [rbx+1E8h], esi
0x1800222e3  lea     rdi, [rbx+1F0h]
0x1800222ea  lea     rcx, qword_1800A46F0
0x1800222f1  call    cs:__imp_GdipStringFormatGetGenericTypographic
0x1800222f7  mov     cs:dword_1800A46F8, eax
0x1800222fd  mov     [rdi], rsi
0x180022300  mov     rdx, rdi
0x180022303  mov     rcx, cs:qword_1800A46F0
0x18002230a  call    cs:__imp_GdipCloneStringFormat
0x180022310  mov     [rdi+8], eax
0x180022313  mov     byte ptr [rbx+208h], 1
0x18002231a  mov     [rbx+20Ch], rsi
0x180022321  mov     [rbx+214h], esi
0x180022327  mov     word ptr [rbx+218h], 100h
0x180022330  mov     [rbx+0C8h], rsi
0x180022337  xor     eax, eax
0x180022339  mov     [rbx+200h], rax
0x180022340  lea     edx, [rax+3]
0x180022343  mov     rcx, [rdi]
0x180022346  call    cs:__imp_GdipSetStringFormatTrimming
0x18002234c  test    eax, eax
0x18002234e  jz      short loc_180022353
0x180022350  mov     [rdi+8], eax
0x180022353  mov     rax, rbx
0x180022356  add     rsp, 48h
0x18002235a  pop     r14
0x18002235c  pop     rdi
0x18002235d  pop     rsi
0x18002235e  pop     rbx
0x18002235f  retn
```
