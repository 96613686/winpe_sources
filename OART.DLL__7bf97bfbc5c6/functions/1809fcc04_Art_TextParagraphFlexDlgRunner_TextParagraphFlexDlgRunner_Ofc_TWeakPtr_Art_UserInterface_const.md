# Art::TextParagraphFlexDlgRunner::TextParagraphFlexDlgRunner(Ofc::TWeakPtr<Art::UserInterface> const &)

- ea: `0x1809fcc04`
- end: `0x1809fcfbd`
- name: `??0TextParagraphFlexDlgRunner@Art@@QEAA@AEBV?$TWeakPtr@VUserInterface@Art@@@Ofc@@@Z`
- size: `953`
- prototype: `__int64 __fastcall(Art::TextParagraphFlexDlgRunner *this)`
- caller_count: `1`
- callee_count: `15`
- tags: ``

## callers

- `0x1803c32b0`

## callees

- `0x18004111c`
- `0x1800559d4`
- `0x180056eac`
- `0x180071720`
- `0x180079890`
- `0x1801b09dc`
- `0x18036ba6c`
- `0x1804061b0`
- `0x1806a5054`
- `0x1806a5084`
- `0x1806a51d0`
- `0x1806a57c4`
- `0x1809fcc04`
- `0x1809fda48`
- `0x1809fe054`

## import_xrefs

- `Mso98Win32Client!__imp_?MsoCreateFlexDataSource@FlexUI@@YA_NHIPEAPEAUIDataSource@1@@Z` at `0x1809fcd65`
- `Mso98Win32Client!__imp_?MsoCreateFlexDataSource@FlexUI@@YA_NHIPEAPEAUIDataSource@1@@Z` at `0x1809fcd65`
- `mso40uiWin32Client!__imp_?CreateBoolean@FlexValue@FlexUI@@SA_N_NAEAVFlexValueSP@2@@Z` at `0x1809fcdac`
- `mso40uiWin32Client!__imp_?CreateBoolean@FlexValue@FlexUI@@SA_N_NAEAVFlexValueSP@2@@Z` at `0x1809fce02`
- `mso40uiWin32Client!__imp_?CreateBoolean@FlexValue@FlexUI@@SA_N_NAEAVFlexValueSP@2@@Z` at `0x1809fcdac`
- `mso40uiWin32Client!__imp_?CreateBoolean@FlexValue@FlexUI@@SA_N_NAEAVFlexValueSP@2@@Z` at `0x1809fce02`
- `mso40uiWin32Client!__imp_?MsoHrInitNetUI@@YAJXZ` at `0x1809fcd29`
- `mso40uiWin32Client!__imp_?MsoHrInitNetUI@@YAJXZ` at `0x1809fcd29`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1809fcdda`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1809fce30`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1809fce84`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1809fcf3a`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1809fcf8e`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1809fcdda`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1809fce30`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1809fce84`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1809fcf3a`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1809fcf8e`
- `mso40uiWin32Client!__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z` at `0x1809fce56`
- `mso40uiWin32Client!__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z` at `0x1809fcf0c`
- `mso40uiWin32Client!__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z` at `0x1809fcf60`
- `mso40uiWin32Client!__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z` at `0x1809fce56`
- `mso40uiWin32Client!__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z` at `0x1809fcf0c`
- `mso40uiWin32Client!__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z` at `0x1809fcf60`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1809fcd9a`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1809fcdf0`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1809fce41`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1809fcefa`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1809fcf4b`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1809fcd9a`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1809fcdf0`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1809fce41`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1809fcefa`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1809fcf4b`

## pseudocode

```c
Art::TextParagraphFlexDlgRunner *__fastcall Art::TextParagraphFlexDlgRunner::TextParagraphFlexDlgRunner(
        Art::TextParagraphFlexDlgRunner *this,
        __int64 *a2)
{
  _QWORD *v4; // rsi
  __int64 v5; // rcx
  int inited; // eax
  struct IDataSource **v7; // r9
  Art *v8; // rcx
  bool IsFEEditAvailable; // al
  __int64 v10; // rbx
  Art *v11; // rcx
  bool IsMEEditAvailable; // al
  __int64 v13; // rbx
  __int64 v14; // rbx
  volatile signed __int32 *v15; // rcx
  void *Checked; // rax
  int v17; // eax
  __int64 v18; // rbx
  __int64 v19; // rbx
  struct Ofc::CProxyPtrImpl *v21; // [rsp+30h] [rbp-10h] BYREF
  struct Ofc::CProxyPtrImpl *v22; // [rsp+38h] [rbp-8h] BYREF
  NetUI::BaseValue *v23; // [rsp+78h] [rbp+38h] BYREF
  Ofc::CProxyPtrImpl *v24; // [rsp+88h] [rbp+48h] BYREF

  *((_QWORD *)this + 2) = &Art::TextParagraphFlexDlgRunner::`vbtable';
  sub_1804061B0();
  *(_QWORD *)this = &Art::TextParagraphFlexDlgRunner::`vftable';
  *((_QWORD *)this + 1) = &Art::TextParagraphFlexDlgRunner::`vftable'{for `CUnk'};
  *(_QWORD *)((char *)this + *(int *)(*((_QWORD *)this + 2) + 4LL) + 16) = &Art::TextParagraphFlexDlgRunner::`vftable'{for `IUnknown'};
  *(_DWORD *)((char *)this + *(int *)(*((_QWORD *)this + 2) + 4LL) + 12) = *(_DWORD *)(*((_QWORD *)this + 2) + 4LL)
                                                                         - 232;
  v4 = (_QWORD *)((char *)this + 40);
  *((_QWORD *)this + 5) = 0;
  v23 = *(NetUI::BaseValue **)&DOUBLE_1_0;
  Art::TextFontSize::TextFontSize(
    (Art::TextParagraphFlexDlgRunner *)((char *)this + 48),
    (const struct Art::Points *)&v23);
  *((_QWORD *)this + 7) = 0x4008000000000000LL;
  *((_DWORD *)this + 16) = 0;
  Art::LinearShadeProps::LinearShadeProps((Art::TextParagraphFlexDlgRunner *)((char *)this + 72));
  v5 = *a2;
  if ( *(_DWORD *)(*a2 + 4) != 0x80000000 )
    _InterlockedIncrement((volatile signed __int32 *)(v5 + 4));
  *((_QWORD *)this + 12) = v5;
  *((_QWORD *)this + 13) = `Ofc::CProxyPtrImpl::GetSentinel'::`2'::s_pProxyPtrSentinel;
  *((_QWORD *)this + 14) = `Ofc::CProxyPtrImpl::GetSentinel'::`2'::s_pProxyPtrSentinel;
  *((_QWORD *)this + 15) = 0;
  *((_DWORD *)this + 32) = 457200;
  *((_BYTE *)this + 182) = 0;
  *(_OWORD *)((char *)this + 132) = 0;
  *(_OWORD *)((char *)this + 148) = 0;
  *(_OWORD *)((char *)this + 164) = 0;
  *((_WORD *)this + 90) = 0;
  *(_DWORD *)((char *)this + 231) = 0;
  *(_OWORD *)((char *)this + 183) = 0;
  *(_OWORD *)((char *)this + 199) = 0;
  *(_OWORD *)((char *)this + 215) = 0;
  inited = MsoHrInitNetUI();
  if ( inited < 0 )
  {
    Ofc::CHResultException::ThrowTag(inited, 0x234840C0u);
    __debugbreak();
  }
  if ( *v4 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v4 + 16LL))(*v4);
  *v4 = 0;
  if ( !FlexUI::MsoCreateFlexDataSource((FlexUI *)0x138E, 134220544, (_DWORD)this + 40, v7) )
  {
    Ofc::CAbortException::ThrowTag(0, 591937699);
    __debugbreak();
  }
  Art::TextParagraphFlexDlgRunner::BuildAlignmentList(this);
  IsFEEditAvailable = Art::IsFEEditAvailable(v8);
  v10 = *v4;
  if ( *v4 )
  {
    v23 = 0;
    FlexUI::FlexValue::CreateBoolean(IsFEEditAvailable, (struct FlexUI::FlexValueSP *)&v23);
    if ( v23 )
    {
      (*(void (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v10 + 48LL))(v10, 0, 16);
      v11 = v23;
      if ( v23 )
        NetUI::BaseValue::Release(v23);
    }
  }
  else
  {
    MsoShipAssertTagProc(7997248);
  }
  IsMEEditAvailable = Art::IsMEEditAvailable(v11);
  v13 = *v4;
  if ( *v4 )
  {
    v23 = 0;
    FlexUI::FlexValue::CreateBoolean(IsMEEditAvailable, (struct FlexUI::FlexValueSP *)&v23);
    if ( v23 )
    {
      (*(void (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v13 + 48LL))(v13, 0, 2);
      if ( v23 )
        NetUI::BaseValue::Release(v23);
    }
  }
  else
  {
    MsoShipAssertTagProc(7997248);
  }
  v14 = *v4;
  if ( *v4 )
  {
    v23 = 0;
    FlexUI::FlexValue::CreateInt32(51206400, (struct FlexUI::FlexValueSP *)&v23);
    if ( v23 )
    {
      (*(void (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v14 + 48LL))(v14, 0, 5);
      if ( v23 )
        NetUI::BaseValue::Release(v23);
    }
  }
  else
  {
    MsoShipAssertTagProc(7997248);
  }
  v22 = Ofc::CProxyPtrImpl::CheckedStrongAddRef(*((struct Ofc::CProxyPtrImpl **)this + 12));
  v15 = (volatile signed __int32 *)*((_QWORD *)Ofc::CProxyPtrImpl::GetChecked(v22) + 11);
  if ( *((_DWORD *)v15 + 1) != 0x80000000 )
    _InterlockedIncrement(v15 + 1);
  v21 = (struct Ofc::CProxyPtrImpl *)v15;
  v24 = Ofc::CProxyPtrImpl::CheckedStrongAddRef((struct Ofc::CProxyPtrImpl *)v15);
  Ofc::CProxyPtrImpl::DtorWeakRelease(&v21);
  Ofc::CProxyPtrImpl::DtorStrongRelease(&v22);
  Checked = Ofc::CProxyPtrImpl::GetChecked(v24);
  v17 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)Checked + 320LL))(Checked);
  v18 = *v4;
  if ( *v4 )
  {
    v23 = 0;
    FlexUI::FlexValue::CreateInt32(v17, (struct FlexUI::FlexValueSP *)&v23);
    if ( v23 )
    {
      (*(void (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v18 + 48LL))(v18, 0, 4);
      if ( v23 )
        NetUI::BaseValue::Release(v23);
    }
  }
  else
  {
    MsoShipAssertTagProc(7997248);
  }
  v19 = *v4;
  if ( *v4 )
  {
    v23 = 0;
    FlexUI::FlexValue::CreateInt32(20116800, (struct FlexUI::FlexValueSP *)&v23);
    if ( v23 )
    {
      (*(void (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v19 + 48LL))(v19, 0, 11);
      if ( v23 )
        NetUI::BaseValue::Release(v23);
    }
  }
  else
  {
    MsoShipAssertTagProc(7997248);
  }
  Art::TextParagraphFlexDlgRunner::RefreshDialogData(this);
  Ofc::CProxyPtrImpl::DtorStrongRelease(&v24);
  return this;
}

```

## disassembly

```asm
0x1809fcc04  mov     [rsp-28h+arg_10], rbx
0x1809fcc09  mov     [rsp-28h+arg_0], rcx
0x1809fcc0e  push    rbp
0x1809fcc0f  push    rsi
0x1809fcc10  push    rdi
0x1809fcc11  push    r14
0x1809fcc13  push    r15
0x1809fcc15  mov     rbp, rsp
0x1809fcc18  sub     rsp, 40h
0x1809fcc1c  mov     rbx, rdx
0x1809fcc1f  mov     rdi, rcx
0x1809fcc22  lea     rax, ??_8TextParagraphFlexDlgRunner@Art@@7B@; const Art::TextParagraphFlexDlgRunner::`vbtable'
0x1809fcc29  mov     [rcx+10h], rax
0x1809fcc2d  call    sub_1804061B0
0x1809fcc32  lea     rax, ??_7TextParagraphFlexDlgRunner@Art@@6B@; const Art::TextParagraphFlexDlgRunner::`vftable'
0x1809fcc39  mov     [rdi], rax
0x1809fcc3c  lea     rax, ??_7TextParagraphFlexDlgRunner@Art@@6BCUnk@@@; const Art::TextParagraphFlexDlgRunner::`vftable'{for `CUnk'}
0x1809fcc43  mov     [rdi+8], rax
0x1809fcc47  mov     rax, [rdi+10h]
0x1809fcc4b  movsxd  rcx, dword ptr [rax+4]
0x1809fcc4f  lea     rax, ??_7TextParagraphFlexDlgRunner@Art@@6BIUnknown@@@; const Art::TextParagraphFlexDlgRunner::`vftable'{for `IUnknown'}
0x1809fcc56  mov     [rcx+rdi+10h], rax
0x1809fcc5b  mov     rax, [rdi+10h]
0x1809fcc5f  movsxd  rcx, dword ptr [rax+4]
0x1809fcc63  lea     edx, [rcx-0E8h]
0x1809fcc69  mov     [rcx+rdi+0Ch], edx
0x1809fcc6d  lea     rsi, [rdi+28h]
0x1809fcc71  xor     r14d, r14d
0x1809fcc74  mov     [rsi], r14
0x1809fcc77  movsd   xmm0, cs:__real@3ff0000000000000
0x1809fcc7f  movsd   [rbp+arg_8], xmm0
0x1809fcc84  lea     rcx, [rdi+30h]; this
0x1809fcc88  lea     rdx, [rbp+arg_8]; struct Art::Points *
0x1809fcc8c  call    ??0TextFontSize@Art@@QEAA@AEBVPoints@1@@Z; Art::TextFontSize::TextFontSize(Art::Points const &)
0x1809fcc91  mov     rax, 4008000000000000h
0x1809fcc9b  mov     [rdi+38h], rax
0x1809fcc9f  mov     [rdi+40h], r14d
0x1809fcca3  lea     rcx, [rdi+48h]; this
0x1809fcca7  call    ??0LinearShadeProps@Art@@QEAA@XZ; Art::LinearShadeProps::LinearShadeProps(void)
0x1809fccac  mov     rcx, [rbx]
0x1809fccaf  mov     eax, [rcx+4]
0x1809fccb2  cmp     eax, 80000000h
0x1809fccb7  jz      short loc_1809FCCBD
0x1809fccb9  lock inc dword ptr [rcx+4]
0x1809fccbd  mov     [rdi+60h], rcx
0x1809fccc1  mov     rax, cs:?s_pProxyPtrSentinel@?1??GetSentinel@CProxyPtrImpl@Ofc@@KAAEBQEAV23@XZ@4QEAV23@EA; Ofc::CProxyPtrImpl * `Ofc::CProxyPtrImpl::GetSentinel(void)'::`2'::s_pProxyPtrSentinel
0x1809fccc8  mov     [rdi+68h], rax
0x1809fcccc  mov     rax, cs:?s_pProxyPtrSentinel@?1??GetSentinel@CProxyPtrImpl@Ofc@@KAAEBQEAV23@XZ@4QEAV23@EA; Ofc::CProxyPtrImpl * `Ofc::CProxyPtrImpl::GetSentinel(void)'::`2'::s_pProxyPtrSentinel
0x1809fccd3  mov     [rdi+70h], rax
0x1809fccd7  mov     [rdi+78h], r14
0x1809fccdb  mov     dword ptr [rdi+80h], 6F9F0h
0x1809fcce5  mov     [rdi+0B6h], r14b
0x1809fccec  xorps   xmm0, xmm0
0x1809fccef  xor     eax, eax
0x1809fccf1  movups  xmmword ptr [rdi+84h], xmm0
0x1809fccf8  movups  xmmword ptr [rdi+94h], xmm0
0x1809fccff  movups  xmmword ptr [rdi+0A4h], xmm0
0x1809fcd06  mov     [rdi+0B4h], ax
0x1809fcd0d  mov     [rdi+0E7h], r14d
0x1809fcd14  movups  xmmword ptr [rdi+0B7h], xmm0
0x1809fcd1b  movups  xmmword ptr [rdi+0C7h], xmm0
0x1809fcd22  movups  xmmword ptr [rdi+0D7h], xmm0
0x1809fcd29  call    cs:__imp_?MsoHrInitNetUI@@YAJXZ; MsoHrInitNetUI(void)
0x1809fcd2f  test    eax, eax
0x1809fcd31  jns     short loc_1809FCD40
0x1809fcd33  mov     edx, 234840C0h; unsigned int
0x1809fcd38  mov     ecx, eax; int
0x1809fcd3a  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x1809fcd3f  int     3; Trap to Debugger
0x1809fcd40  mov     rcx, [rsi]
0x1809fcd43  test    rcx, rcx
0x1809fcd46  jz      short loc_1809FCD55
0x1809fcd48  mov     rax, [rcx]
0x1809fcd4b  mov     rax, [rax+10h]
0x1809fcd4f  call    cs:__guard_dispatch_icall_fptr
0x1809fcd55  mov     [rsi], r14
0x1809fcd58  mov     r8, rsi
0x1809fcd5b  mov     edx, 8000B00h
0x1809fcd60  mov     ecx, 138Eh
0x1809fcd65  call    cs:__imp_?MsoCreateFlexDataSource@FlexUI@@YA_NHIPEAPEAUIDataSource@1@@Z; FlexUI::MsoCreateFlexDataSource(int,uint,FlexUI::IDataSource * *)
0x1809fcd6b  test    al, al
0x1809fcd6d  jnz     short loc_1809FCD7C
0x1809fcd6f  mov     edx, 234840A3h
0x1809fcd74  xor     ecx, ecx
0x1809fcd76  call    ?ThrowTag@CAbortException@Ofc@@SAXW4ExcAbortStrategy@2@K@Z; Ofc::CAbortException::ThrowTag(Ofc::ExcAbortStrategy,ulong)
0x1809fcd7b  int     3; Trap to Debugger
0x1809fcd7c  mov     rcx, rdi; this
0x1809fcd7f  call    ?BuildAlignmentList@TextParagraphFlexDlgRunner@Art@@AEAAXXZ; Art::TextParagraphFlexDlgRunner::BuildAlignmentList(void)
0x1809fcd84  call    ?IsFEEditAvailable@Art@@YA_NXZ; Art::IsFEEditAvailable(void)
0x1809fcd89  mov     rbx, [rsi]
0x1809fcd8c  mov     r15d, 7A0740h
0x1809fcd92  test    rbx, rbx
0x1809fcd95  jnz     short loc_1809FCDA2
0x1809fcd97  mov     ecx, r15d
0x1809fcd9a  call    cs:__imp_MsoShipAssertTagProc
0x1809fcda0  jmp     short loc_1809FCDE0
0x1809fcda2  mov     [rbp+arg_8], r14
0x1809fcda6  lea     rdx, [rbp+arg_8]
0x1809fcdaa  mov     cl, al
0x1809fcdac  call    cs:__imp_?CreateBoolean@FlexValue@FlexUI@@SA_N_NAEAVFlexValueSP@2@@Z; FlexUI::FlexValue::CreateBoolean(bool,FlexUI::FlexValueSP &)
0x1809fcdb2  mov     r9, [rbp+arg_8]
0x1809fcdb6  test    r9, r9
0x1809fcdb9  jz      short loc_1809FCDE0
0x1809fcdbb  mov     rax, [rbx]
0x1809fcdbe  xor     edx, edx
0x1809fcdc0  lea     r8d, [rdx+10h]
0x1809fcdc4  mov     rcx, rbx
0x1809fcdc7  mov     rax, [rax+30h]
0x1809fcdcb  call    cs:__guard_dispatch_icall_fptr
0x1809fcdd1  mov     rcx, [rbp+arg_8]
0x1809fcdd5  test    rcx, rcx
0x1809fcdd8  jz      short loc_1809FCDE0
0x1809fcdda  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x1809fcde0  call    ?IsMEEditAvailable@Art@@YA_NXZ; Art::IsMEEditAvailable(void)
0x1809fcde5  mov     rbx, [rsi]
0x1809fcde8  test    rbx, rbx
0x1809fcdeb  jnz     short loc_1809FCDF8
0x1809fcded  mov     ecx, r15d
0x1809fcdf0  call    cs:__imp_MsoShipAssertTagProc
0x1809fcdf6  jmp     short loc_1809FCE36
0x1809fcdf8  mov     [rbp+arg_8], r14
0x1809fcdfc  lea     rdx, [rbp+arg_8]
0x1809fce00  mov     cl, al
0x1809fce02  call    cs:__imp_?CreateBoolean@FlexValue@FlexUI@@SA_N_NAEAVFlexValueSP@2@@Z; FlexUI::FlexValue::CreateBoolean(bool,FlexUI::FlexValueSP &)
0x1809fce08  mov     r9, [rbp+arg_8]
0x1809fce0c  test    r9, r9
0x1809fce0f  jz      short loc_1809FCE36
0x1809fce11  mov     rax, [rbx]
0x1809fce14  xor     edx, edx
0x1809fce16  lea     r8d, [rdx+2]
0x1809fce1a  mov     rcx, rbx
0x1809fce1d  mov     rax, [rax+30h]
0x1809fce21  call    cs:__guard_dispatch_icall_fptr
0x1809fce27  mov     rcx, [rbp+arg_8]
0x1809fce2b  test    rcx, rcx
0x1809fce2e  jz      short loc_1809FCE36
0x1809fce30  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x1809fce36  mov     rbx, [rsi]
0x1809fce39  test    rbx, rbx
0x1809fce3c  jnz     short loc_1809FCE49
0x1809fce3e  mov     ecx, r15d
0x1809fce41  call    cs:__imp_MsoShipAssertTagProc
0x1809fce47  jmp     short loc_1809FCE8A
0x1809fce49  mov     [rbp+arg_8], r14
0x1809fce4d  lea     rdx, [rbp+arg_8]
0x1809fce51  mov     ecx, 30D5900h
0x1809fce56  call    cs:__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z; FlexUI::FlexValue::CreateInt32(int,FlexUI::FlexValueSP &)
0x1809fce5c  mov     r9, [rbp+arg_8]
0x1809fce60  test    r9, r9
0x1809fce63  jz      short loc_1809FCE8A
0x1809fce65  mov     rax, [rbx]
0x1809fce68  xor     edx, edx
0x1809fce6a  lea     r8d, [rdx+5]
0x1809fce6e  mov     rcx, rbx
0x1809fce71  mov     rax, [rax+30h]
0x1809fce75  call    cs:__guard_dispatch_icall_fptr
0x1809fce7b  mov     rcx, [rbp+arg_8]
0x1809fce7f  test    rcx, rcx
0x1809fce82  jz      short loc_1809FCE8A
0x1809fce84  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x1809fce8a  mov     rcx, [rdi+60h]; struct Ofc::CProxyPtrImpl *
0x1809fce8e  call    ?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAddRef(Ofc::CProxyPtrImpl *)
0x1809fce93  mov     [rbp+var_8], rax
0x1809fce97  mov     rcx, rax; this
0x1809fce9a  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1809fce9f  mov     rcx, [rax+58h]; struct Ofc::CProxyPtrImpl *
0x1809fcea3  mov     eax, [rcx+4]
0x1809fcea6  cmp     eax, 80000000h
0x1809fceab  jz      short loc_1809FCEB1
0x1809fcead  lock inc dword ptr [rcx+4]
0x1809fceb1  mov     [rbp+var_10], rcx
0x1809fceb5  call    ?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAddRef(Ofc::CProxyPtrImpl *)
0x1809fceba  mov     [rbp+arg_18], rax
0x1809fcebe  lea     rcx, [rbp+var_10]; struct Ofc::CProxyPtrImpl **
0x1809fcec2  call    ?DtorWeakRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorWeakRelease(Ofc::CProxyPtrImpl * &)
0x1809fcec7  lea     rcx, [rbp+var_8]; struct Ofc::CProxyPtrImpl **
0x1809fcecb  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x1809fced0  mov     rcx, [rbp+arg_18]; this
0x1809fced4  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1809fced9  mov     rdx, rax
0x1809fcedc  mov     rcx, [rax]
0x1809fcedf  mov     rax, [rcx+140h]
0x1809fcee6  mov     rcx, rdx
0x1809fcee9  call    cs:__guard_dispatch_icall_fptr
0x1809fceef  mov     rbx, [rsi]
0x1809fcef2  test    rbx, rbx
0x1809fcef5  jnz     short loc_1809FCF02
0x1809fcef7  mov     ecx, r15d
0x1809fcefa  call    cs:__imp_MsoShipAssertTagProc
0x1809fcf00  jmp     short loc_1809FCF40
0x1809fcf02  mov     [rbp+arg_8], r14
0x1809fcf06  lea     rdx, [rbp+arg_8]
0x1809fcf0a  mov     ecx, eax
0x1809fcf0c  call    cs:__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z; FlexUI::FlexValue::CreateInt32(int,FlexUI::FlexValueSP &)
0x1809fcf12  mov     r9, [rbp+arg_8]
0x1809fcf16  test    r9, r9
0x1809fcf19  jz      short loc_1809FCF40
0x1809fcf1b  mov     rax, [rbx]
0x1809fcf1e  xor     edx, edx
0x1809fcf20  lea     r8d, [rdx+4]
0x1809fcf24  mov     rcx, rbx
0x1809fcf27  mov     rax, [rax+30h]
0x1809fcf2b  call    cs:__guard_dispatch_icall_fptr
0x1809fcf31  mov     rcx, [rbp+arg_8]
0x1809fcf35  test    rcx, rcx
0x1809fcf38  jz      short loc_1809FCF40
0x1809fcf3a  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x1809fcf40  mov     rbx, [rsi]
0x1809fcf43  test    rbx, rbx
0x1809fcf46  jnz     short loc_1809FCF53
0x1809fcf48  mov     ecx, r15d
0x1809fcf4b  call    cs:__imp_MsoShipAssertTagProc
0x1809fcf51  jmp     short loc_1809FCF94
0x1809fcf53  mov     [rbp+arg_8], r14
0x1809fcf57  lea     rdx, [rbp+arg_8]
0x1809fcf5b  mov     ecx, 132F540h
0x1809fcf60  call    cs:__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z; FlexUI::FlexValue::CreateInt32(int,FlexUI::FlexValueSP &)
0x1809fcf66  mov     r9, [rbp+arg_8]
0x1809fcf6a  test    r9, r9
0x1809fcf6d  jz      short loc_1809FCF94
0x1809fcf6f  mov     rax, [rbx]
0x1809fcf72  xor     edx, edx
0x1809fcf74  lea     r8d, [rdx+0Bh]
0x1809fcf78  mov     rcx, rbx
0x1809fcf7b  mov     rax, [rax+30h]
0x1809fcf7f  call    cs:__guard_dispatch_icall_fptr
0x1809fcf85  mov     rcx, [rbp+arg_8]
0x1809fcf89  test    rcx, rcx
0x1809fcf8c  jz      short loc_1809FCF94
0x1809fcf8e  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x1809fcf94  mov     rcx, rdi; this
0x1809fcf97  call    ?RefreshDialogData@TextParagraphFlexDlgRunner@Art@@AEAAXXZ; Art::TextParagraphFlexDlgRunner::RefreshDialogData(void)
0x1809fcf9c  nop
0x1809fcf9d  lea     rcx, [rbp+arg_18]; struct Ofc::CProxyPtrImpl **
0x1809fcfa1  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x1809fcfa6  mov     rax, rdi
0x1809fcfa9  mov     rbx, [rsp+40h+arg_10]
0x1809fcfb1  add     rsp, 40h
0x1809fcfb5  pop     r15
0x1809fcfb7  pop     r14
0x1809fcfb9  pop     rdi
0x1809fcfba  pop     rsi
0x1809fcfbb  pop     rbp
0x1809fcfbc  retn
```
