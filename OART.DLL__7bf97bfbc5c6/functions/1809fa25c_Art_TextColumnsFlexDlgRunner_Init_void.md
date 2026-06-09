# Art::TextColumnsFlexDlgRunner::Init(void)

- ea: `0x1809fa25c`
- end: `0x1809fa457`
- name: `?Init@TextColumnsFlexDlgRunner@Art@@AEAAXXZ`
- size: `507`
- prototype: `void __fastcall(Art::TextColumnsFlexDlgRunner *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1809f9e50`

## callees

- `0x1800559d4`
- `0x180071720`
- `0x1801b09dc`
- `0x18036ba6c`
- `0x1806a5054`
- `0x1806a5084`
- `0x1806a51d0`
- `0x1806a57c4`
- `0x1809fa25c`
- `0x1809fa4e4`

## import_xrefs

- `Mso98Win32Client!__imp_?MsoCreateFlexDataSource@FlexUI@@YA_NHIPEAPEAUIDataSource@1@@Z` at `0x1809fa2b2`
- `Mso98Win32Client!__imp_?MsoCreateFlexDataSource@FlexUI@@YA_NHIPEAPEAUIDataSource@1@@Z` at `0x1809fa2b2`
- `mso40uiWin32Client!__imp_?CreateBoolean@FlexValue@FlexUI@@SA_N_NAEAVFlexValueSP@2@@Z` at `0x1809fa2f1`
- `mso40uiWin32Client!__imp_?CreateBoolean@FlexValue@FlexUI@@SA_N_NAEAVFlexValueSP@2@@Z` at `0x1809fa2f1`
- `mso40uiWin32Client!__imp_?MsoHrInitNetUI@@YAJXZ` at `0x1809fa26e`
- `mso40uiWin32Client!__imp_?MsoHrInitNetUI@@YAJXZ` at `0x1809fa26e`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1809fa31f`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1809fa379`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1809fa432`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1809fa31f`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1809fa379`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1809fa432`
- `mso40uiWin32Client!__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z` at `0x1809fa34b`
- `mso40uiWin32Client!__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z` at `0x1809fa404`
- `mso40uiWin32Client!__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z` at `0x1809fa34b`
- `mso40uiWin32Client!__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z` at `0x1809fa404`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1809fa2db`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1809fa332`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1809fa3ee`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1809fa2db`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1809fa332`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1809fa3ee`

## pseudocode

```c
void __fastcall Art::TextColumnsFlexDlgRunner::Init(Art::TextColumnsFlexDlgRunner *this)
{
  int inited; // eax
  struct IDataSource **v3; // r9
  __int64 *v4; // rbx
  __int64 v5; // rcx
  Art *v6; // rcx
  bool IsMEEditAvailable; // al
  __int64 v8; // rdi
  __int64 v9; // rdi
  volatile signed __int32 *v10; // rcx
  void *Checked; // rax
  int v12; // eax
  __int64 v13; // rbx
  struct Ofc::CProxyPtrImpl *v14; // [rsp+30h] [rbp-10h] BYREF
  NetUI::BaseValue *v15; // [rsp+68h] [rbp+28h] BYREF
  Ofc::CProxyPtrImpl *v16; // [rsp+70h] [rbp+30h] BYREF
  struct Ofc::CProxyPtrImpl *v17; // [rsp+78h] [rbp+38h] BYREF

  inited = MsoHrInitNetUI();
  if ( inited < 0 )
  {
    Ofc::CHResultException::ThrowTag(inited, 0x234840D4u);
    __debugbreak();
  }
  v4 = (__int64 *)((char *)this + 40);
  v5 = *((_QWORD *)this + 5);
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  *v4 = 0;
  if ( !FlexUI::MsoCreateFlexDataSource((FlexUI *)0x13A4, 134218752, (_DWORD)this + 40, v3) )
  {
    Ofc::CAbortException::ThrowTag(0, 591937747);
    __debugbreak();
  }
  IsMEEditAvailable = Art::IsMEEditAvailable(v6);
  v8 = *v4;
  if ( *v4 )
  {
    v15 = 0;
    FlexUI::FlexValue::CreateBoolean(IsMEEditAvailable, (struct FlexUI::FlexValueSP *)&v15);
    if ( v15 )
    {
      (*(void (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v8 + 48LL))(v8, 0, 4);
      if ( v15 )
        NetUI::BaseValue::Release(v15);
    }
  }
  else
  {
    MsoShipAssertTagProc(7997248);
  }
  v9 = *v4;
  if ( *v4 )
  {
    v15 = 0;
    FlexUI::FlexValue::CreateInt32(14630400, (struct FlexUI::FlexValueSP *)&v15);
    if ( v15 )
    {
      (*(void (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v9 + 48LL))(v9, 0, 1);
      if ( v15 )
        NetUI::BaseValue::Release(v15);
    }
  }
  else
  {
    MsoShipAssertTagProc(7997248);
  }
  v14 = Ofc::CProxyPtrImpl::CheckedStrongAddRef(*((struct Ofc::CProxyPtrImpl **)this + 10));
  v10 = (volatile signed __int32 *)*((_QWORD *)Ofc::CProxyPtrImpl::GetChecked(v14) + 11);
  if ( *((_DWORD *)v10 + 1) != 0x80000000 )
    _InterlockedIncrement(v10 + 1);
  v17 = (struct Ofc::CProxyPtrImpl *)v10;
  v16 = Ofc::CProxyPtrImpl::CheckedStrongAddRef((struct Ofc::CProxyPtrImpl *)v10);
  Ofc::CProxyPtrImpl::DtorWeakRelease(&v17);
  Ofc::CProxyPtrImpl::DtorStrongRelease(&v14);
  Checked = Ofc::CProxyPtrImpl::GetChecked(v16);
  v12 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)Checked + 320LL))(Checked);
  v13 = *v4;
  if ( v13 )
  {
    v15 = 0;
    FlexUI::FlexValue::CreateInt32(v12, (struct FlexUI::FlexValueSP *)&v15);
    if ( v15 )
    {
      (*(void (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v13 + 48LL))(v13, 0, 3);
      if ( v15 )
        NetUI::BaseValue::Release(v15);
    }
  }
  else
  {
    MsoShipAssertTagProc(7997248);
  }
  Art::TextColumnsFlexDlgRunner::RefreshDialogData(this);
  Ofc::CProxyPtrImpl::DtorStrongRelease(&v16);
}

```

## disassembly

```asm
0x1809fa25c  mov     [rsp-18h+arg_0], rbx
0x1809fa261  push    rbp
0x1809fa262  push    rsi
0x1809fa263  push    rdi
0x1809fa264  mov     rbp, rsp
0x1809fa267  sub     rsp, 40h
0x1809fa26b  mov     rsi, rcx
0x1809fa26e  call    cs:__imp_?MsoHrInitNetUI@@YAJXZ; MsoHrInitNetUI(void)
0x1809fa274  test    eax, eax
0x1809fa276  jns     short loc_1809FA285
0x1809fa278  mov     edx, 234840D4h; unsigned int
0x1809fa27d  mov     ecx, eax; int
0x1809fa27f  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x1809fa284  int     3; Trap to Debugger
0x1809fa285  lea     rbx, [rsi+28h]
0x1809fa289  mov     rcx, [rbx]
0x1809fa28c  test    rcx, rcx
0x1809fa28f  jz      short loc_1809FA29E
0x1809fa291  mov     rax, [rcx]
0x1809fa294  mov     rax, [rax+10h]
0x1809fa298  call    cs:__guard_dispatch_icall_fptr
0x1809fa29e  mov     qword ptr [rbx], 0
0x1809fa2a5  mov     r8, rbx
0x1809fa2a8  mov     edx, 8000400h
0x1809fa2ad  mov     ecx, 13A4h
0x1809fa2b2  call    cs:__imp_?MsoCreateFlexDataSource@FlexUI@@YA_NHIPEAPEAUIDataSource@1@@Z; FlexUI::MsoCreateFlexDataSource(int,uint,FlexUI::IDataSource * *)
0x1809fa2b8  test    al, al
0x1809fa2ba  jnz     short loc_1809FA2C9
0x1809fa2bc  mov     edx, 234840D3h
0x1809fa2c1  xor     ecx, ecx
0x1809fa2c3  call    ?ThrowTag@CAbortException@Ofc@@SAXW4ExcAbortStrategy@2@K@Z; Ofc::CAbortException::ThrowTag(Ofc::ExcAbortStrategy,ulong)
0x1809fa2c8  int     3; Trap to Debugger
0x1809fa2c9  call    ?IsMEEditAvailable@Art@@YA_NXZ; Art::IsMEEditAvailable(void)
0x1809fa2ce  mov     rdi, [rbx]
0x1809fa2d1  test    rdi, rdi
0x1809fa2d4  jnz     short loc_1809FA2E3
0x1809fa2d6  mov     ecx, 7A0740h
0x1809fa2db  call    cs:__imp_MsoShipAssertTagProc
0x1809fa2e1  jmp     short loc_1809FA325
0x1809fa2e3  mov     [rbp+arg_8], 0
0x1809fa2eb  lea     rdx, [rbp+arg_8]
0x1809fa2ef  mov     cl, al
0x1809fa2f1  call    cs:__imp_?CreateBoolean@FlexValue@FlexUI@@SA_N_NAEAVFlexValueSP@2@@Z; FlexUI::FlexValue::CreateBoolean(bool,FlexUI::FlexValueSP &)
0x1809fa2f7  mov     r9, [rbp+arg_8]
0x1809fa2fb  test    r9, r9
0x1809fa2fe  jz      short loc_1809FA325
0x1809fa300  mov     rax, [rdi]
0x1809fa303  xor     edx, edx
0x1809fa305  lea     r8d, [rdx+4]
0x1809fa309  mov     rcx, rdi
0x1809fa30c  mov     rax, [rax+30h]
0x1809fa310  call    cs:__guard_dispatch_icall_fptr
0x1809fa316  mov     rcx, [rbp+arg_8]
0x1809fa31a  test    rcx, rcx
0x1809fa31d  jz      short loc_1809FA325
0x1809fa31f  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x1809fa325  mov     rdi, [rbx]
0x1809fa328  test    rdi, rdi
0x1809fa32b  jnz     short loc_1809FA33A
0x1809fa32d  mov     ecx, 7A0740h
0x1809fa332  call    cs:__imp_MsoShipAssertTagProc
0x1809fa338  jmp     short loc_1809FA37F
0x1809fa33a  mov     [rbp+arg_8], 0
0x1809fa342  lea     rdx, [rbp+arg_8]
0x1809fa346  mov     ecx, 0DF3E00h
0x1809fa34b  call    cs:__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z; FlexUI::FlexValue::CreateInt32(int,FlexUI::FlexValueSP &)
0x1809fa351  mov     r9, [rbp+arg_8]
0x1809fa355  test    r9, r9
0x1809fa358  jz      short loc_1809FA37F
0x1809fa35a  mov     rax, [rdi]
0x1809fa35d  xor     edx, edx
0x1809fa35f  lea     r8d, [rdx+1]
0x1809fa363  mov     rcx, rdi
0x1809fa366  mov     rax, [rax+30h]
0x1809fa36a  call    cs:__guard_dispatch_icall_fptr
0x1809fa370  mov     rcx, [rbp+arg_8]
0x1809fa374  test    rcx, rcx
0x1809fa377  jz      short loc_1809FA37F
0x1809fa379  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x1809fa37f  mov     rcx, [rsi+50h]; struct Ofc::CProxyPtrImpl *
0x1809fa383  call    ?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAddRef(Ofc::CProxyPtrImpl *)
0x1809fa388  mov     [rbp+var_10], rax
0x1809fa38c  mov     rcx, rax; this
0x1809fa38f  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1809fa394  mov     rcx, [rax+58h]; struct Ofc::CProxyPtrImpl *
0x1809fa398  mov     eax, [rcx+4]
0x1809fa39b  cmp     eax, 80000000h
0x1809fa3a0  jz      short loc_1809FA3A6
0x1809fa3a2  lock inc dword ptr [rcx+4]
0x1809fa3a6  mov     [rbp+arg_18], rcx
0x1809fa3aa  call    ?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAddRef(Ofc::CProxyPtrImpl *)
0x1809fa3af  mov     [rbp+arg_10], rax
0x1809fa3b3  lea     rcx, [rbp+arg_18]; struct Ofc::CProxyPtrImpl **
0x1809fa3b7  call    ?DtorWeakRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorWeakRelease(Ofc::CProxyPtrImpl * &)
0x1809fa3bc  lea     rcx, [rbp+var_10]; struct Ofc::CProxyPtrImpl **
0x1809fa3c0  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x1809fa3c5  mov     rcx, [rbp+arg_10]; this
0x1809fa3c9  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1809fa3ce  mov     rdx, [rax]
0x1809fa3d1  mov     rcx, rax
0x1809fa3d4  mov     rax, [rdx+140h]
0x1809fa3db  call    cs:__guard_dispatch_icall_fptr
0x1809fa3e1  mov     rbx, [rbx]
0x1809fa3e4  test    rbx, rbx
0x1809fa3e7  jnz     short loc_1809FA3F6
0x1809fa3e9  mov     ecx, 7A0740h
0x1809fa3ee  call    cs:__imp_MsoShipAssertTagProc
0x1809fa3f4  jmp     short loc_1809FA438
0x1809fa3f6  mov     [rbp+arg_8], 0
0x1809fa3fe  lea     rdx, [rbp+arg_8]
0x1809fa402  mov     ecx, eax
0x1809fa404  call    cs:__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z; FlexUI::FlexValue::CreateInt32(int,FlexUI::FlexValueSP &)
0x1809fa40a  mov     r9, [rbp+arg_8]
0x1809fa40e  test    r9, r9
0x1809fa411  jz      short loc_1809FA438
0x1809fa413  mov     rax, [rbx]
0x1809fa416  xor     edx, edx
0x1809fa418  lea     r8d, [rdx+3]
0x1809fa41c  mov     rcx, rbx
0x1809fa41f  mov     rax, [rax+30h]
0x1809fa423  call    cs:__guard_dispatch_icall_fptr
0x1809fa429  mov     rcx, [rbp+arg_8]
0x1809fa42d  test    rcx, rcx
0x1809fa430  jz      short loc_1809FA438
0x1809fa432  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x1809fa438  mov     rcx, rsi; this
0x1809fa43b  call    ?RefreshDialogData@TextColumnsFlexDlgRunner@Art@@AEAAXXZ; Art::TextColumnsFlexDlgRunner::RefreshDialogData(void)
0x1809fa440  nop
0x1809fa441  lea     rcx, [rbp+arg_10]; struct Ofc::CProxyPtrImpl **
0x1809fa445  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x1809fa44a  mov     rbx, [rsp+40h+arg_0]
0x1809fa44f  add     rsp, 40h
0x1809fa453  pop     rdi
0x1809fa454  pop     rsi
0x1809fa455  pop     rbp
0x1809fa456  retn
```
