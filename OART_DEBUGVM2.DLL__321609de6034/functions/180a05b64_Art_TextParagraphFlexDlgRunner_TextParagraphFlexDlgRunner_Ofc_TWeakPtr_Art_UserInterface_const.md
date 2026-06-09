# Art::TextParagraphFlexDlgRunner::TextParagraphFlexDlgRunner(Ofc::TWeakPtr<Art::UserInterface> const &)

- ea: `0x180a05b64`
- end: `0x180a05f0e`
- name: `??0TextParagraphFlexDlgRunner@Art@@QEAA@AEBV?$TWeakPtr@VUserInterface@Art@@@Ofc@@@Z`
- size: `938`
- prototype: `__int64 __fastcall(Art::TextParagraphFlexDlgRunner *this)`
- caller_count: `1`
- callee_count: `16`
- tags: ``

## callers

- `0x1803ec880`

## callees

- `0x18000b6b0`
- `0x1800559f0`
- `0x18016eb28`
- `0x180279010`
- `0x180279050`
- `0x18027c4c0`
- `0x1802a23d0`
- `0x1802d56d0`
- `0x18042e570`
- `0x1806bc2a8`
- `0x1806bc4f0`
- `0x1806bc6a8`
- `0x1806d19bc`
- `0x180a05b64`
- `0x180a06998`
- `0x180a06f94`

## import_xrefs

- `Mso98Win32Client!__imp_?MsoCreateFlexDataSource@FlexUI@@YA_NHIPEAPEAUIDataSource@1@@Z` at `0x180a05cbc`
- `Mso98Win32Client!__imp_?MsoCreateFlexDataSource@FlexUI@@YA_NHIPEAPEAUIDataSource@1@@Z` at `0x180a05cbc`
- `mso40uiWin32Client!__imp_?CreateBoolean@FlexValue@FlexUI@@SA_N_NAEAVFlexValueSP@2@@Z` at `0x180a05d03`
- `mso40uiWin32Client!__imp_?CreateBoolean@FlexValue@FlexUI@@SA_N_NAEAVFlexValueSP@2@@Z` at `0x180a05d59`
- `mso40uiWin32Client!__imp_?CreateBoolean@FlexValue@FlexUI@@SA_N_NAEAVFlexValueSP@2@@Z` at `0x180a05d03`
- `mso40uiWin32Client!__imp_?CreateBoolean@FlexValue@FlexUI@@SA_N_NAEAVFlexValueSP@2@@Z` at `0x180a05d59`
- `mso40uiWin32Client!__imp_?MsoHrInitNetUI@@YAJXZ` at `0x180a05c80`
- `mso40uiWin32Client!__imp_?MsoHrInitNetUI@@YAJXZ` at `0x180a05c80`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x180a05d31`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x180a05d87`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x180a05ddb`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x180a05e8b`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x180a05edf`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x180a05d31`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x180a05d87`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x180a05ddb`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x180a05e8b`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x180a05edf`
- `mso40uiWin32Client!__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z` at `0x180a05dad`
- `mso40uiWin32Client!__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z` at `0x180a05e5d`
- `mso40uiWin32Client!__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z` at `0x180a05eb1`
- `mso40uiWin32Client!__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z` at `0x180a05dad`
- `mso40uiWin32Client!__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z` at `0x180a05e5d`
- `mso40uiWin32Client!__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z` at `0x180a05eb1`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180a05cf1`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180a05d47`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180a05d98`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180a05e4b`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180a05e9c`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180a05cf1`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180a05d47`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180a05d98`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180a05e4b`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180a05e9c`

## pseudocode

```c
Art::TextParagraphFlexDlgRunner *__fastcall Art::TextParagraphFlexDlgRunner::TextParagraphFlexDlgRunner(
        Art::TextParagraphFlexDlgRunner *this,
        struct Ofc::CProxyPtrImpl **a2)
{
  _QWORD *v4; // rdi
  int inited; // eax
  struct IDataSource **v6; // r9
  Art *v7; // rcx
  bool IsFEEditAvailable; // al
  __int64 v9; // rbx
  Art *v10; // rcx
  bool IsMEEditAvailable; // al
  __int64 v12; // rbx
  __int64 v13; // rbx
  struct Ofc::CProxyPtrImpl **Checked; // rax
  void *v15; // rax
  int v16; // eax
  __int64 v17; // rbx
  __int64 v18; // rbx
  struct Ofc::CProxyPtrImpl *v20; // [rsp+30h] [rbp-10h] BYREF
  struct Ofc::CProxyPtrImpl *v21; // [rsp+38h] [rbp-8h] BYREF
  NetUI::BaseValue *v22; // [rsp+78h] [rbp+38h] BYREF
  Ofc::CProxyPtrImpl *v23; // [rsp+88h] [rbp+48h] BYREF

  *((_QWORD *)this + 2) = &Art::TextParagraphFlexDlgRunner::`vbtable';
  sub_18042E570();
  *(_QWORD *)this = &Art::TextParagraphFlexDlgRunner::`vftable';
  *((_QWORD *)this + 1) = &Art::TextParagraphFlexDlgRunner::`vftable'{for `CUnk'};
  *(_QWORD *)((char *)this + *(int *)(*((_QWORD *)this + 2) + 4LL) + 16) = &Art::TextParagraphFlexDlgRunner::`vftable'{for `IUnknown'};
  *(_DWORD *)((char *)this + *(int *)(*((_QWORD *)this + 2) + 4LL) + 12) = *(_DWORD *)(*((_QWORD *)this + 2) + 4LL)
                                                                         - 232;
  v4 = (_QWORD *)((char *)this + 40);
  *((_QWORD *)this + 5) = 0;
  v22 = *(NetUI::BaseValue **)&DOUBLE_1_0;
  Art::TextFontSize::TextFontSize(
    (Art::TextParagraphFlexDlgRunner *)((char *)this + 48),
    (const struct Art::Points *)&v22);
  *((_QWORD *)this + 7) = 0x4008000000000000LL;
  *((_DWORD *)this + 16) = 0;
  Art::LinearShadeProps::LinearShadeProps((Art::TextParagraphFlexDlgRunner *)((char *)this + 72));
  *((_QWORD *)this + 12) = Ofc::CProxyPtrImpl::WeakAddRef(*a2);
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
  if ( !FlexUI::MsoCreateFlexDataSource((FlexUI *)0x138E, 134220544, (_DWORD)this + 40, v6) )
  {
    Ofc::CAbortException::ThrowTag(0, 591937699);
    __debugbreak();
  }
  Art::TextParagraphFlexDlgRunner::BuildAlignmentList(this);
  IsFEEditAvailable = Art::IsFEEditAvailable(v7);
  v9 = *v4;
  if ( *v4 )
  {
    v22 = 0;
    FlexUI::FlexValue::CreateBoolean(IsFEEditAvailable, (struct FlexUI::FlexValueSP *)&v22);
    if ( v22 )
    {
      (*(void (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v9 + 48LL))(v9, 0, 16);
      v10 = v22;
      if ( v22 )
        NetUI::BaseValue::Release(v22);
    }
  }
  else
  {
    MsoShipAssertTagProc(7997248);
  }
  IsMEEditAvailable = Art::IsMEEditAvailable(v10);
  v12 = *v4;
  if ( *v4 )
  {
    v22 = 0;
    FlexUI::FlexValue::CreateBoolean(IsMEEditAvailable, (struct FlexUI::FlexValueSP *)&v22);
    if ( v22 )
    {
      (*(void (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v12 + 48LL))(v12, 0, 2);
      if ( v22 )
        NetUI::BaseValue::Release(v22);
    }
  }
  else
  {
    MsoShipAssertTagProc(7997248);
  }
  v13 = *v4;
  if ( *v4 )
  {
    v22 = 0;
    FlexUI::FlexValue::CreateInt32(51206400, (struct FlexUI::FlexValueSP *)&v22);
    if ( v22 )
    {
      (*(void (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v13 + 48LL))(v13, 0, 5);
      if ( v22 )
        NetUI::BaseValue::Release(v22);
    }
  }
  else
  {
    MsoShipAssertTagProc(7997248);
  }
  v21 = Ofc::CProxyPtrImpl::CheckedStrongAddRef(*((struct Ofc::CProxyPtrImpl **)this + 12));
  Checked = (struct Ofc::CProxyPtrImpl **)Ofc::CProxyPtrImpl::GetChecked(v21);
  v20 = Ofc::CProxyPtrImpl::WeakAddRef(Checked[11]);
  v23 = Ofc::CProxyPtrImpl::CheckedStrongAddRef(v20);
  Ofc::CProxyPtrImpl::DtorWeakRelease(&v20);
  Ofc::CProxyPtrImpl::DtorStrongRelease(&v21);
  v15 = Ofc::CProxyPtrImpl::GetChecked(v23);
  v16 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v15 + 320LL))(v15);
  v17 = *v4;
  if ( *v4 )
  {
    v22 = 0;
    FlexUI::FlexValue::CreateInt32(v16, (struct FlexUI::FlexValueSP *)&v22);
    if ( v22 )
    {
      (*(void (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v17 + 48LL))(v17, 0, 4);
      if ( v22 )
        NetUI::BaseValue::Release(v22);
    }
  }
  else
  {
    MsoShipAssertTagProc(7997248);
  }
  v18 = *v4;
  if ( *v4 )
  {
    v22 = 0;
    FlexUI::FlexValue::CreateInt32(20116800, (struct FlexUI::FlexValueSP *)&v22);
    if ( v22 )
    {
      (*(void (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v18 + 48LL))(v18, 0, 11);
      if ( v22 )
        NetUI::BaseValue::Release(v22);
    }
  }
  else
  {
    MsoShipAssertTagProc(7997248);
  }
  Art::TextParagraphFlexDlgRunner::RefreshDialogData(this);
  Ofc::CProxyPtrImpl::DtorStrongRelease(&v23);
  return this;
}

```

## disassembly

```asm
0x180a05b64  mov     [rsp-28h+arg_10], rbx
0x180a05b69  mov     [rsp-28h+arg_0], rcx
0x180a05b6e  push    rbp
0x180a05b6f  push    rsi
0x180a05b70  push    rdi
0x180a05b71  push    r14
0x180a05b73  push    r15
0x180a05b75  mov     rbp, rsp
0x180a05b78  sub     rsp, 40h
0x180a05b7c  mov     rbx, rdx
0x180a05b7f  mov     rsi, rcx
0x180a05b82  lea     rax, ??_8TextParagraphFlexDlgRunner@Art@@7B@; const Art::TextParagraphFlexDlgRunner::`vbtable'
0x180a05b89  mov     [rcx+10h], rax
0x180a05b8d  call    sub_18042E570
0x180a05b92  lea     rax, ??_7TextParagraphFlexDlgRunner@Art@@6B@; const Art::TextParagraphFlexDlgRunner::`vftable'
0x180a05b99  mov     [rsi], rax
0x180a05b9c  lea     rax, ??_7TextParagraphFlexDlgRunner@Art@@6BCUnk@@@; const Art::TextParagraphFlexDlgRunner::`vftable'{for `CUnk'}
0x180a05ba3  mov     [rsi+8], rax
0x180a05ba7  mov     rax, [rsi+10h]
0x180a05bab  movsxd  rcx, dword ptr [rax+4]
0x180a05baf  lea     rax, ??_7TextParagraphFlexDlgRunner@Art@@6BIUnknown@@@; const Art::TextParagraphFlexDlgRunner::`vftable'{for `IUnknown'}
0x180a05bb6  mov     [rcx+rsi+10h], rax
0x180a05bbb  mov     rax, [rsi+10h]
0x180a05bbf  movsxd  rcx, dword ptr [rax+4]
0x180a05bc3  lea     edx, [rcx-0E8h]
0x180a05bc9  mov     [rcx+rsi+0Ch], edx
0x180a05bcd  lea     rdi, [rsi+28h]
0x180a05bd1  xor     r14d, r14d
0x180a05bd4  mov     [rdi], r14
0x180a05bd7  movsd   xmm0, cs:__real@3ff0000000000000
0x180a05bdf  movsd   [rbp+arg_8], xmm0
0x180a05be4  lea     rcx, [rsi+30h]; this
0x180a05be8  lea     rdx, [rbp+arg_8]; struct Art::Points *
0x180a05bec  call    ??0TextFontSize@Art@@QEAA@AEBVPoints@1@@Z; Art::TextFontSize::TextFontSize(Art::Points const &)
0x180a05bf1  mov     rax, 4008000000000000h
0x180a05bfb  mov     [rsi+38h], rax
0x180a05bff  mov     [rsi+40h], r14d
0x180a05c03  lea     rcx, [rsi+48h]; this
0x180a05c07  call    ??0LinearShadeProps@Art@@QEAA@XZ; Art::LinearShadeProps::LinearShadeProps(void)
0x180a05c0c  mov     rcx, [rbx]; struct Ofc::CProxyPtrImpl *
0x180a05c0f  call    ?WeakAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::WeakAddRef(Ofc::CProxyPtrImpl *)
0x180a05c14  mov     [rsi+60h], rax
0x180a05c18  mov     rax, cs:?s_pProxyPtrSentinel@?1??GetSentinel@CProxyPtrImpl@Ofc@@KAAEBQEAV23@XZ@4QEAV23@EA; Ofc::CProxyPtrImpl * `Ofc::CProxyPtrImpl::GetSentinel(void)'::`2'::s_pProxyPtrSentinel
0x180a05c1f  mov     [rsi+68h], rax
0x180a05c23  mov     rax, cs:?s_pProxyPtrSentinel@?1??GetSentinel@CProxyPtrImpl@Ofc@@KAAEBQEAV23@XZ@4QEAV23@EA; Ofc::CProxyPtrImpl * `Ofc::CProxyPtrImpl::GetSentinel(void)'::`2'::s_pProxyPtrSentinel
0x180a05c2a  mov     [rsi+70h], rax
0x180a05c2e  mov     [rsi+78h], r14
0x180a05c32  mov     dword ptr [rsi+80h], 6F9F0h
0x180a05c3c  mov     [rsi+0B6h], r14b
0x180a05c43  xorps   xmm0, xmm0
0x180a05c46  xor     eax, eax
0x180a05c48  movups  xmmword ptr [rsi+84h], xmm0
0x180a05c4f  movups  xmmword ptr [rsi+94h], xmm0
0x180a05c56  movups  xmmword ptr [rsi+0A4h], xmm0
0x180a05c5d  mov     [rsi+0B4h], ax
0x180a05c64  mov     [rsi+0E7h], r14d
0x180a05c6b  movups  xmmword ptr [rsi+0B7h], xmm0
0x180a05c72  movups  xmmword ptr [rsi+0C7h], xmm0
0x180a05c79  movups  xmmword ptr [rsi+0D7h], xmm0
0x180a05c80  call    cs:__imp_?MsoHrInitNetUI@@YAJXZ; MsoHrInitNetUI(void)
0x180a05c86  test    eax, eax
0x180a05c88  jns     short loc_180A05C97
0x180a05c8a  mov     edx, 234840C0h; unsigned int
0x180a05c8f  mov     ecx, eax; int
0x180a05c91  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x180a05c96  int     3; Trap to Debugger
0x180a05c97  mov     rcx, [rdi]
0x180a05c9a  test    rcx, rcx
0x180a05c9d  jz      short loc_180A05CAC
0x180a05c9f  mov     rax, [rcx]
0x180a05ca2  mov     rax, [rax+10h]
0x180a05ca6  call    cs:__guard_dispatch_icall_fptr
0x180a05cac  mov     [rdi], r14
0x180a05caf  mov     r8, rdi
0x180a05cb2  mov     edx, 8000B00h
0x180a05cb7  mov     ecx, 138Eh
0x180a05cbc  call    cs:__imp_?MsoCreateFlexDataSource@FlexUI@@YA_NHIPEAPEAUIDataSource@1@@Z; FlexUI::MsoCreateFlexDataSource(int,uint,FlexUI::IDataSource * *)
0x180a05cc2  test    al, al
0x180a05cc4  jnz     short loc_180A05CD3
0x180a05cc6  mov     edx, 234840A3h
0x180a05ccb  xor     ecx, ecx
0x180a05ccd  call    ?ThrowTag@CAbortException@Ofc@@SAXW4ExcAbortStrategy@2@K@Z; Ofc::CAbortException::ThrowTag(Ofc::ExcAbortStrategy,ulong)
0x180a05cd2  int     3; Trap to Debugger
0x180a05cd3  mov     rcx, rsi; this
0x180a05cd6  call    ?BuildAlignmentList@TextParagraphFlexDlgRunner@Art@@AEAAXXZ; Art::TextParagraphFlexDlgRunner::BuildAlignmentList(void)
0x180a05cdb  call    ?IsFEEditAvailable@Art@@YA_NXZ; Art::IsFEEditAvailable(void)
0x180a05ce0  mov     rbx, [rdi]
0x180a05ce3  mov     r15d, 7A0740h
0x180a05ce9  test    rbx, rbx
0x180a05cec  jnz     short loc_180A05CF9
0x180a05cee  mov     ecx, r15d
0x180a05cf1  call    cs:__imp_MsoShipAssertTagProc
0x180a05cf7  jmp     short loc_180A05D37
0x180a05cf9  mov     [rbp+arg_8], r14
0x180a05cfd  lea     rdx, [rbp+arg_8]
0x180a05d01  mov     cl, al
0x180a05d03  call    cs:__imp_?CreateBoolean@FlexValue@FlexUI@@SA_N_NAEAVFlexValueSP@2@@Z; FlexUI::FlexValue::CreateBoolean(bool,FlexUI::FlexValueSP &)
0x180a05d09  mov     r9, [rbp+arg_8]
0x180a05d0d  test    r9, r9
0x180a05d10  jz      short loc_180A05D37
0x180a05d12  mov     rax, [rbx]
0x180a05d15  xor     edx, edx
0x180a05d17  lea     r8d, [rdx+10h]
0x180a05d1b  mov     rcx, rbx
0x180a05d1e  mov     rax, [rax+30h]
0x180a05d22  call    cs:__guard_dispatch_icall_fptr
0x180a05d28  mov     rcx, [rbp+arg_8]
0x180a05d2c  test    rcx, rcx
0x180a05d2f  jz      short loc_180A05D37
0x180a05d31  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x180a05d37  call    ?IsMEEditAvailable@Art@@YA_NXZ; Art::IsMEEditAvailable(void)
0x180a05d3c  mov     rbx, [rdi]
0x180a05d3f  test    rbx, rbx
0x180a05d42  jnz     short loc_180A05D4F
0x180a05d44  mov     ecx, r15d
0x180a05d47  call    cs:__imp_MsoShipAssertTagProc
0x180a05d4d  jmp     short loc_180A05D8D
0x180a05d4f  mov     [rbp+arg_8], r14
0x180a05d53  lea     rdx, [rbp+arg_8]
0x180a05d57  mov     cl, al
0x180a05d59  call    cs:__imp_?CreateBoolean@FlexValue@FlexUI@@SA_N_NAEAVFlexValueSP@2@@Z; FlexUI::FlexValue::CreateBoolean(bool,FlexUI::FlexValueSP &)
0x180a05d5f  mov     r9, [rbp+arg_8]
0x180a05d63  test    r9, r9
0x180a05d66  jz      short loc_180A05D8D
0x180a05d68  mov     rax, [rbx]
0x180a05d6b  xor     edx, edx
0x180a05d6d  lea     r8d, [rdx+2]
0x180a05d71  mov     rcx, rbx
0x180a05d74  mov     rax, [rax+30h]
0x180a05d78  call    cs:__guard_dispatch_icall_fptr
0x180a05d7e  mov     rcx, [rbp+arg_8]
0x180a05d82  test    rcx, rcx
0x180a05d85  jz      short loc_180A05D8D
0x180a05d87  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x180a05d8d  mov     rbx, [rdi]
0x180a05d90  test    rbx, rbx
0x180a05d93  jnz     short loc_180A05DA0
0x180a05d95  mov     ecx, r15d
0x180a05d98  call    cs:__imp_MsoShipAssertTagProc
0x180a05d9e  jmp     short loc_180A05DE1
0x180a05da0  mov     [rbp+arg_8], r14
0x180a05da4  lea     rdx, [rbp+arg_8]
0x180a05da8  mov     ecx, 30D5900h
0x180a05dad  call    cs:__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z; FlexUI::FlexValue::CreateInt32(int,FlexUI::FlexValueSP &)
0x180a05db3  mov     r9, [rbp+arg_8]
0x180a05db7  test    r9, r9
0x180a05dba  jz      short loc_180A05DE1
0x180a05dbc  mov     rax, [rbx]
0x180a05dbf  xor     edx, edx
0x180a05dc1  lea     r8d, [rdx+5]
0x180a05dc5  mov     rcx, rbx
0x180a05dc8  mov     rax, [rax+30h]
0x180a05dcc  call    cs:__guard_dispatch_icall_fptr
0x180a05dd2  mov     rcx, [rbp+arg_8]
0x180a05dd6  test    rcx, rcx
0x180a05dd9  jz      short loc_180A05DE1
0x180a05ddb  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x180a05de1  mov     rcx, [rsi+60h]; struct Ofc::CProxyPtrImpl *
0x180a05de5  call    ?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAddRef(Ofc::CProxyPtrImpl *)
0x180a05dea  mov     [rbp+var_8], rax
0x180a05dee  mov     rcx, rax; this
0x180a05df1  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x180a05df6  mov     rcx, [rax+58h]; struct Ofc::CProxyPtrImpl *
0x180a05dfa  call    ?WeakAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::WeakAddRef(Ofc::CProxyPtrImpl *)
0x180a05dff  mov     [rbp+var_10], rax
0x180a05e03  mov     rcx, rax; struct Ofc::CProxyPtrImpl *
0x180a05e06  call    ?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAddRef(Ofc::CProxyPtrImpl *)
0x180a05e0b  mov     [rbp+arg_18], rax
0x180a05e0f  lea     rcx, [rbp+var_10]; struct Ofc::CProxyPtrImpl **
0x180a05e13  call    ?DtorWeakRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorWeakRelease(Ofc::CProxyPtrImpl * &)
0x180a05e18  lea     rcx, [rbp+var_8]; struct Ofc::CProxyPtrImpl **
0x180a05e1c  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x180a05e21  mov     rcx, [rbp+arg_18]; this
0x180a05e25  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x180a05e2a  mov     rdx, rax
0x180a05e2d  mov     rcx, [rax]
0x180a05e30  mov     rax, [rcx+140h]
0x180a05e37  mov     rcx, rdx
0x180a05e3a  call    cs:__guard_dispatch_icall_fptr
0x180a05e40  mov     rbx, [rdi]
0x180a05e43  test    rbx, rbx
0x180a05e46  jnz     short loc_180A05E53
0x180a05e48  mov     ecx, r15d
0x180a05e4b  call    cs:__imp_MsoShipAssertTagProc
0x180a05e51  jmp     short loc_180A05E91
0x180a05e53  mov     [rbp+arg_8], r14
0x180a05e57  lea     rdx, [rbp+arg_8]
0x180a05e5b  mov     ecx, eax
0x180a05e5d  call    cs:__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z; FlexUI::FlexValue::CreateInt32(int,FlexUI::FlexValueSP &)
0x180a05e63  mov     r9, [rbp+arg_8]
0x180a05e67  test    r9, r9
0x180a05e6a  jz      short loc_180A05E91
0x180a05e6c  mov     rax, [rbx]
0x180a05e6f  xor     edx, edx
0x180a05e71  lea     r8d, [rdx+4]
0x180a05e75  mov     rcx, rbx
0x180a05e78  mov     rax, [rax+30h]
0x180a05e7c  call    cs:__guard_dispatch_icall_fptr
0x180a05e82  mov     rcx, [rbp+arg_8]
0x180a05e86  test    rcx, rcx
0x180a05e89  jz      short loc_180A05E91
0x180a05e8b  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x180a05e91  mov     rbx, [rdi]
0x180a05e94  test    rbx, rbx
0x180a05e97  jnz     short loc_180A05EA4
0x180a05e99  mov     ecx, r15d
0x180a05e9c  call    cs:__imp_MsoShipAssertTagProc
0x180a05ea2  jmp     short loc_180A05EE5
0x180a05ea4  mov     [rbp+arg_8], r14
0x180a05ea8  lea     rdx, [rbp+arg_8]
0x180a05eac  mov     ecx, 132F540h
0x180a05eb1  call    cs:__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z; FlexUI::FlexValue::CreateInt32(int,FlexUI::FlexValueSP &)
0x180a05eb7  mov     r9, [rbp+arg_8]
0x180a05ebb  test    r9, r9
0x180a05ebe  jz      short loc_180A05EE5
0x180a05ec0  mov     rax, [rbx]
0x180a05ec3  xor     edx, edx
0x180a05ec5  lea     r8d, [rdx+0Bh]
0x180a05ec9  mov     rcx, rbx
0x180a05ecc  mov     rax, [rax+30h]
0x180a05ed0  call    cs:__guard_dispatch_icall_fptr
0x180a05ed6  mov     rcx, [rbp+arg_8]
0x180a05eda  test    rcx, rcx
0x180a05edd  jz      short loc_180A05EE5
0x180a05edf  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x180a05ee5  mov     rcx, rsi; this
0x180a05ee8  call    ?RefreshDialogData@TextParagraphFlexDlgRunner@Art@@AEAAXXZ; Art::TextParagraphFlexDlgRunner::RefreshDialogData(void)
0x180a05eed  nop
0x180a05eee  lea     rcx, [rbp+arg_18]; struct Ofc::CProxyPtrImpl **
0x180a05ef2  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x180a05ef7  mov     rax, rsi
0x180a05efa  mov     rbx, [rsp+40h+arg_10]
0x180a05f02  add     rsp, 40h
0x180a05f06  pop     r15
0x180a05f08  pop     r14
0x180a05f0a  pop     rdi
0x180a05f0b  pop     rsi
0x180a05f0c  pop     rbp
0x180a05f0d  retn
```
