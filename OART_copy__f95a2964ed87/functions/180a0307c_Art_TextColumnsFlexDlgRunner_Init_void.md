# Art::TextColumnsFlexDlgRunner::Init(void)

- ea: `0x180a0307c`
- end: `0x180a03272`
- name: `?Init@TextColumnsFlexDlgRunner@Art@@AEAAXXZ`
- size: `502`
- prototype: `void __fastcall(Art::TextColumnsFlexDlgRunner *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x180a02c80`

## callees

- `0x18000b6b0`
- `0x180278e50`
- `0x180279050`
- `0x1802a23d0`
- `0x1802d56d0`
- `0x1806bc2a8`
- `0x1806bc4f0`
- `0x1806bc6a8`
- `0x1806d19bc`
- `0x180a0307c`
- `0x180a03304`

## import_xrefs

- `Mso98Win32Client!__imp_?MsoCreateFlexDataSource@FlexUI@@YA_NHIPEAPEAUIDataSource@1@@Z` at `0x180a030d2`
- `Mso98Win32Client!__imp_?MsoCreateFlexDataSource@FlexUI@@YA_NHIPEAPEAUIDataSource@1@@Z` at `0x180a030d2`
- `mso40uiWin32Client!__imp_?CreateBoolean@FlexValue@FlexUI@@SA_N_NAEAVFlexValueSP@2@@Z` at `0x180a03111`
- `mso40uiWin32Client!__imp_?CreateBoolean@FlexValue@FlexUI@@SA_N_NAEAVFlexValueSP@2@@Z` at `0x180a03111`
- `mso40uiWin32Client!__imp_?MsoHrInitNetUI@@YAJXZ` at `0x180a0308e`
- `mso40uiWin32Client!__imp_?MsoHrInitNetUI@@YAJXZ` at `0x180a0308e`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x180a0313f`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x180a03199`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x180a0324d`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x180a0313f`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x180a03199`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x180a0324d`
- `mso40uiWin32Client!__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z` at `0x180a0316b`
- `mso40uiWin32Client!__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z` at `0x180a0321f`
- `mso40uiWin32Client!__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z` at `0x180a0316b`
- `mso40uiWin32Client!__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z` at `0x180a0321f`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180a030fb`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180a03152`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180a03209`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180a030fb`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180a03152`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180a03209`

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
  struct Ofc::CProxyPtrImpl **Checked; // rax
  void *v11; // rax
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
  Checked = (struct Ofc::CProxyPtrImpl **)Ofc::CProxyPtrImpl::GetChecked(v14);
  v17 = Ofc::CProxyPtrImpl::WeakAddRef(Checked[11]);
  v16 = Ofc::CProxyPtrImpl::CheckedStrongAddRef(v17);
  Ofc::CProxyPtrImpl::DtorWeakRelease(&v17);
  Ofc::CProxyPtrImpl::DtorStrongRelease(&v14);
  v11 = Ofc::CProxyPtrImpl::GetChecked(v16);
  v12 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v11 + 320LL))(v11);
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
0x180a0307c  mov     [rsp-18h+arg_0], rbx
0x180a03081  push    rbp
0x180a03082  push    rsi
0x180a03083  push    rdi
0x180a03084  mov     rbp, rsp
0x180a03087  sub     rsp, 40h
0x180a0308b  mov     rsi, rcx
0x180a0308e  call    cs:__imp_?MsoHrInitNetUI@@YAJXZ; MsoHrInitNetUI(void)
0x180a03094  test    eax, eax
0x180a03096  jns     short loc_180A030A5
0x180a03098  mov     edx, 234840D4h; unsigned int
0x180a0309d  mov     ecx, eax; int
0x180a0309f  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x180a030a4  int     3; Trap to Debugger
0x180a030a5  lea     rbx, [rsi+28h]
0x180a030a9  mov     rcx, [rbx]
0x180a030ac  test    rcx, rcx
0x180a030af  jz      short loc_180A030BE
0x180a030b1  mov     rax, [rcx]
0x180a030b4  mov     rax, [rax+10h]
0x180a030b8  call    cs:__guard_dispatch_icall_fptr
0x180a030be  mov     qword ptr [rbx], 0
0x180a030c5  mov     r8, rbx
0x180a030c8  mov     edx, 8000400h
0x180a030cd  mov     ecx, 13A4h
0x180a030d2  call    cs:__imp_?MsoCreateFlexDataSource@FlexUI@@YA_NHIPEAPEAUIDataSource@1@@Z; FlexUI::MsoCreateFlexDataSource(int,uint,FlexUI::IDataSource * *)
0x180a030d8  test    al, al
0x180a030da  jnz     short loc_180A030E9
0x180a030dc  mov     edx, 234840D3h
0x180a030e1  xor     ecx, ecx
0x180a030e3  call    ?ThrowTag@CAbortException@Ofc@@SAXW4ExcAbortStrategy@2@K@Z; Ofc::CAbortException::ThrowTag(Ofc::ExcAbortStrategy,ulong)
0x180a030e8  int     3; Trap to Debugger
0x180a030e9  call    ?IsMEEditAvailable@Art@@YA_NXZ; Art::IsMEEditAvailable(void)
0x180a030ee  mov     rdi, [rbx]
0x180a030f1  test    rdi, rdi
0x180a030f4  jnz     short loc_180A03103
0x180a030f6  mov     ecx, 7A0740h
0x180a030fb  call    cs:__imp_MsoShipAssertTagProc
0x180a03101  jmp     short loc_180A03145
0x180a03103  mov     [rbp+arg_8], 0
0x180a0310b  lea     rdx, [rbp+arg_8]
0x180a0310f  mov     cl, al
0x180a03111  call    cs:__imp_?CreateBoolean@FlexValue@FlexUI@@SA_N_NAEAVFlexValueSP@2@@Z; FlexUI::FlexValue::CreateBoolean(bool,FlexUI::FlexValueSP &)
0x180a03117  mov     r9, [rbp+arg_8]
0x180a0311b  test    r9, r9
0x180a0311e  jz      short loc_180A03145
0x180a03120  mov     rax, [rdi]
0x180a03123  xor     edx, edx
0x180a03125  lea     r8d, [rdx+4]
0x180a03129  mov     rcx, rdi
0x180a0312c  mov     rax, [rax+30h]
0x180a03130  call    cs:__guard_dispatch_icall_fptr
0x180a03136  mov     rcx, [rbp+arg_8]
0x180a0313a  test    rcx, rcx
0x180a0313d  jz      short loc_180A03145
0x180a0313f  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x180a03145  mov     rdi, [rbx]
0x180a03148  test    rdi, rdi
0x180a0314b  jnz     short loc_180A0315A
0x180a0314d  mov     ecx, 7A0740h
0x180a03152  call    cs:__imp_MsoShipAssertTagProc
0x180a03158  jmp     short loc_180A0319F
0x180a0315a  mov     [rbp+arg_8], 0
0x180a03162  lea     rdx, [rbp+arg_8]
0x180a03166  mov     ecx, 0DF3E00h
0x180a0316b  call    cs:__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z; FlexUI::FlexValue::CreateInt32(int,FlexUI::FlexValueSP &)
0x180a03171  mov     r9, [rbp+arg_8]
0x180a03175  test    r9, r9
0x180a03178  jz      short loc_180A0319F
0x180a0317a  mov     rax, [rdi]
0x180a0317d  xor     edx, edx
0x180a0317f  lea     r8d, [rdx+1]
0x180a03183  mov     rcx, rdi
0x180a03186  mov     rax, [rax+30h]
0x180a0318a  call    cs:__guard_dispatch_icall_fptr
0x180a03190  mov     rcx, [rbp+arg_8]
0x180a03194  test    rcx, rcx
0x180a03197  jz      short loc_180A0319F
0x180a03199  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x180a0319f  mov     rcx, [rsi+50h]; struct Ofc::CProxyPtrImpl *
0x180a031a3  call    ?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAddRef(Ofc::CProxyPtrImpl *)
0x180a031a8  mov     [rbp+var_10], rax
0x180a031ac  mov     rcx, rax; this
0x180a031af  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x180a031b4  mov     rcx, [rax+58h]; struct Ofc::CProxyPtrImpl *
0x180a031b8  call    ?WeakAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::WeakAddRef(Ofc::CProxyPtrImpl *)
0x180a031bd  mov     [rbp+arg_18], rax
0x180a031c1  mov     rcx, rax; struct Ofc::CProxyPtrImpl *
0x180a031c4  call    ?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAddRef(Ofc::CProxyPtrImpl *)
0x180a031c9  mov     [rbp+arg_10], rax
0x180a031cd  lea     rcx, [rbp+arg_18]; struct Ofc::CProxyPtrImpl **
0x180a031d1  call    ?DtorWeakRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorWeakRelease(Ofc::CProxyPtrImpl * &)
0x180a031d6  lea     rcx, [rbp+var_10]; struct Ofc::CProxyPtrImpl **
0x180a031da  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x180a031df  nop
0x180a031e0  mov     rcx, [rbp+arg_10]; this
0x180a031e4  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x180a031e9  mov     rdx, [rax]
0x180a031ec  mov     rcx, rax
0x180a031ef  mov     rax, [rdx+140h]
0x180a031f6  call    cs:__guard_dispatch_icall_fptr
0x180a031fc  mov     rbx, [rbx]
0x180a031ff  test    rbx, rbx
0x180a03202  jnz     short loc_180A03211
0x180a03204  mov     ecx, 7A0740h
0x180a03209  call    cs:__imp_MsoShipAssertTagProc
0x180a0320f  jmp     short loc_180A03253
0x180a03211  mov     [rbp+arg_8], 0
0x180a03219  lea     rdx, [rbp+arg_8]
0x180a0321d  mov     ecx, eax
0x180a0321f  call    cs:__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z; FlexUI::FlexValue::CreateInt32(int,FlexUI::FlexValueSP &)
0x180a03225  mov     r9, [rbp+arg_8]
0x180a03229  test    r9, r9
0x180a0322c  jz      short loc_180A03253
0x180a0322e  mov     rax, [rbx]
0x180a03231  xor     edx, edx
0x180a03233  lea     r8d, [rdx+3]
0x180a03237  mov     rcx, rbx
0x180a0323a  mov     rax, [rax+30h]
0x180a0323e  call    cs:__guard_dispatch_icall_fptr
0x180a03244  mov     rcx, [rbp+arg_8]
0x180a03248  test    rcx, rcx
0x180a0324b  jz      short loc_180A03253
0x180a0324d  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x180a03253  mov     rcx, rsi; this
0x180a03256  call    ?RefreshDialogData@TextColumnsFlexDlgRunner@Art@@AEAAXXZ; Art::TextColumnsFlexDlgRunner::RefreshDialogData(void)
0x180a0325b  nop
0x180a0325c  lea     rcx, [rbp+arg_10]; struct Ofc::CProxyPtrImpl **
0x180a03260  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x180a03265  mov     rbx, [rsp+40h+arg_0]
0x180a0326a  add     rsp, 40h
0x180a0326e  pop     rdi
0x180a0326f  pop     rsi
0x180a03270  pop     rbp
0x180a03271  retn
```
