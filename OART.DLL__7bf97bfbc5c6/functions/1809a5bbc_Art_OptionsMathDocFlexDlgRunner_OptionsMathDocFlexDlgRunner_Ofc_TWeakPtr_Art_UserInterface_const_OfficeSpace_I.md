# Art::OptionsMathDocFlexDlgRunner::OptionsMathDocFlexDlgRunner(Ofc::TWeakPtr<Art::UserInterface> const &,OfficeSpace::IOfficeSpace *)

- ea: `0x1809a5bbc`
- end: `0x1809a5f85`
- name: `??0OptionsMathDocFlexDlgRunner@Art@@QEAA@AEBV?$TWeakPtr@VUserInterface@Art@@@Ofc@@PEAUIOfficeSpace@OfficeSpace@@@Z`
- size: `969`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x1809a63c4`

## callees

- `0x180003c60`
- `0x180071720`
- `0x1801b09dc`
- `0x18036ba6c`
- `0x1804061b0`
- `0x180407250`
- `0x1806a5084`
- `0x1806a51d0`
- `0x1806a57c4`
- `0x1806a5c5c`
- `0x1809a5bbc`

## import_xrefs

- `Mso98Win32Client!__imp_?MsoCreateFlexDataSource@FlexUI@@YA_NHIPEAPEAUIDataSource@1@@Z` at `0x1809a5cb5`
- `Mso98Win32Client!__imp_?MsoCreateFlexDataSource@FlexUI@@YA_NHIPEAPEAUIDataSource@1@@Z` at `0x1809a5cb5`
- `mso40uiWin32Client!__imp_?CreateBoolean@FlexValue@FlexUI@@SA_N_NAEAVFlexValueSP@2@@Z` at `0x1809a5d12`
- `mso40uiWin32Client!__imp_?CreateBoolean@FlexValue@FlexUI@@SA_N_NAEAVFlexValueSP@2@@Z` at `0x1809a5d12`
- `mso40uiWin32Client!__imp_?MsoHrInitNetUI@@YAJXZ` at `0x1809a5c79`
- `mso40uiWin32Client!__imp_?MsoHrInitNetUI@@YAJXZ` at `0x1809a5c79`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1809a5d40`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1809a5e0f`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1809a5eb1`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1809a5ef9`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1809a5d40`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1809a5e0f`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1809a5eb1`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1809a5ef9`
- `mso40uiWin32Client!__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z` at `0x1809a5ddf`
- `mso40uiWin32Client!__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z` at `0x1809a5e81`
- `mso40uiWin32Client!__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z` at `0x1809a5ddf`
- `mso40uiWin32Client!__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z` at `0x1809a5e81`
- `Mso20Win32Client!__imp_?MsoDwRegGetDw@@YAKPEBU_msoreg@@@Z` at `0x1809a5cea`
- `Mso20Win32Client!__imp_?MsoDwRegGetDw@@YAKPEBU_msoreg@@@Z` at `0x1809a5cea`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1809a5d02`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1809a5d9c`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1809a5daf`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1809a5e3e`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1809a5e51`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1809a5ecb`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1809a5d02`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1809a5d9c`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1809a5daf`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1809a5e3e`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1809a5e51`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1809a5ecb`

## pseudocode

```c
__int64 __fastcall Art::OptionsMathDocFlexDlgRunner::OptionsMathDocFlexDlgRunner(__int64 a1)
{
  __int64 v2; // r11
  __int64 v3; // rcx
  __int64 **v4; // rdi
  struct Ofc::CProxyPtrImpl **v5; // r12
  volatile signed __int32 **v6; // r10
  volatile signed __int32 *v7; // rcx
  int inited; // eax
  struct IDataSource **v9; // r9
  bool v10; // cl
  __int64 *v11; // r14
  void *Checked; // rax
  _DWORD *v13; // r14
  int v14; // ecx
  __int64 *v15; // r15
  int v16; // ecx
  int v17; // eax
  __int64 *v18; // r14
  int v19; // ecx
  __int64 *v20; // rdi
  __int64 v21; // rax
  void (__fastcall *v22)(__int64 *, _QWORD, __int64); // r14
  void *v23; // rax
  struct Ofc::CProxyPtrImpl **CurrentView; // rax
  struct Ofc::CProxyPtrImpl *v26; // [rsp+30h] [rbp-10h] BYREF
  struct Ofc::CProxyPtrImpl *v27; // [rsp+88h] [rbp+48h] BYREF
  Ofc::CProxyPtrImpl *v28; // [rsp+90h] [rbp+50h] BYREF

  *(_QWORD *)(a1 + 16) = &Art::OptionsMathDocFlexDlgRunner::`vbtable';
  sub_1804061B0();
  *(_QWORD *)a1 = &Art::OptionsMathDocFlexDlgRunner::`vftable';
  *(_QWORD *)(a1 + 8) = &Art::OptionsMathDocFlexDlgRunner::`vftable'{for `CUnk'};
  *(_QWORD *)(*(int *)(*(_QWORD *)(a1 + 16) + 4LL) + a1 + 16) = &Art::OptionsMathDocFlexDlgRunner::`vftable'{for `IUnknown'};
  v3 = *(int *)(*(_QWORD *)(a1 + 16) + 4LL);
  *(_DWORD *)(v3 + a1 + 12) = v3 - 128;
  v4 = (__int64 **)(a1 + 40);
  *(_QWORD *)(a1 + 40) = 0;
  v5 = (struct Ofc::CProxyPtrImpl **)(a1 + 48);
  v7 = *v6;
  if ( *((_DWORD *)*v6 + 1) != 0x80000000 )
    _InterlockedIncrement(v7 + 1);
  *v5 = (struct Ofc::CProxyPtrImpl *)v7;
  *(_QWORD *)(a1 + 56) = `Ofc::CProxyPtrImpl::GetSentinel'::`2'::s_pProxyPtrSentinel;
  *(_QWORD *)(a1 + 64) = 0;
  *(_BYTE *)(a1 + 122) = 0;
  *(_OWORD *)(a1 + 72) = 0;
  *(_OWORD *)(a1 + 88) = 0;
  *(_OWORD *)(a1 + 104) = 0;
  *(_WORD *)(a1 + 120) = 0;
  *(_QWORD *)(a1 + 128) = v2;
  inited = MsoHrInitNetUI();
  if ( inited < 0 )
  {
    Ofc::CHResultException::ThrowTag(inited, 0x2348445Cu);
    __debugbreak();
  }
  if ( *v4 )
    (*(void (__fastcall **)(__int64 *))(**v4 + 16))(*v4);
  *v4 = 0;
  if ( !FlexUI::MsoCreateFlexDataSource((FlexUI *)0x1420, 134281216, a1 + 40, v9) )
  {
    Ofc::CAbortException::ThrowTag(0, 591938651);
    __debugbreak();
  }
  v28 = (Ofc::CProxyPtrImpl *)`Ofc::CProxyPtrImpl::GetSentinel'::`2'::s_pProxyPtrSentinel;
  Art::GetDocumentContext(a1 + 48, &v28);
  v10 = MsoDwRegGetDw((const struct _msoreg *)&OrapiData::Oart::c_msoridMathCopyLF) != 0;
  v11 = *v4;
  if ( *v4 )
  {
    v27 = 0;
    FlexUI::FlexValue::CreateBoolean(v10, (struct FlexUI::FlexValueSP *)&v27);
    if ( v27 )
    {
      (*(void (__fastcall **)(__int64 *, _QWORD, __int64))(*v11 + 48))(v11, 0, 1);
      if ( v27 )
        NetUI::BaseValue::Release(v27);
    }
  }
  else
  {
    MsoShipAssertTagProc(7997248);
  }
  Checked = Ofc::CProxyPtrImpl::GetChecked(v28);
  v13 = (_DWORD *)(*(__int64 (__fastcall **)(void *))(*(_QWORD *)Checked + 224LL))(Checked);
  if ( v13 && (*v13 & 0x30000) != 0 )
  {
    v14 = v13[1] & 0x30000;
    if ( v14 )
    {
      if ( v14 == 0x10000 )
      {
        v15 = *v4;
        if ( !*v4 )
          goto LABEL_21;
        v16 = 1;
        goto LABEL_27;
      }
      if ( v14 == 0x20000 )
      {
        v15 = *v4;
        if ( !*v4 )
          goto LABEL_21;
        v16 = 2;
        goto LABEL_27;
      }
      MsoShipAssertTagProc(591938650);
    }
    v15 = *v4;
    if ( !*v4 )
    {
LABEL_21:
      MsoShipAssertTagProc(7997248);
      goto LABEL_30;
    }
    v16 = 0;
LABEL_27:
    v27 = 0;
    FlexUI::FlexValue::CreateInt32(v16, (struct FlexUI::FlexValueSP *)&v27);
    if ( v27 )
    {
      (*(void (__fastcall **)(__int64 *, _QWORD, __int64))(*v15 + 48))(v15, 0, 2);
      if ( v27 )
        NetUI::BaseValue::Release(v27);
    }
LABEL_30:
    if ( (*v13 & 0xC0000) == 0 )
      goto LABEL_45;
    v17 = v13[1] & 0xC0000;
    switch ( v17 )
    {
      case 0:
        goto LABEL_35;
      case 0x40000:
        v18 = *v4;
        if ( !*v4 )
          goto LABEL_36;
        v19 = 1;
        break;
      case 0x80000:
        v18 = *v4;
        if ( !*v4 )
          goto LABEL_36;
        v19 = 2;
        break;
      default:
        MsoShipAssertTagProc(591938649);
LABEL_35:
        v18 = *v4;
        if ( !*v4 )
        {
LABEL_36:
          MsoShipAssertTagProc(7997248);
          goto LABEL_45;
        }
        v19 = 0;
        break;
    }
    v27 = 0;
    FlexUI::FlexValue::CreateInt32(v19, (struct FlexUI::FlexValueSP *)&v27);
    if ( v27 )
    {
      (*(void (__fastcall **)(__int64 *, _QWORD, __int64))(*v18 + 48))(v18, 0, 3);
      if ( v27 )
        NetUI::BaseValue::Release(v27);
    }
  }
LABEL_45:
  v20 = *v4;
  v21 = *v20;
  v22 = *(void (__fastcall **)(__int64 *, _QWORD, __int64))(*v20 + 64);
  if ( v20 )
  {
    v27 = 0;
    (*(void (__fastcall **)(__int64 *, __int64, struct Ofc::CProxyPtrImpl **))(v21 + 40))(v20, 2, &v27);
    if ( v27 )
      NetUI::BaseValue::Release(v27);
  }
  else
  {
    MsoShipAssertTagProc(7997216);
  }
  v22(v20, 0, 3);
  v26 = Ofc::CProxyPtrImpl::CheckedStrongAddRef(*v5);
  v23 = Ofc::CProxyPtrImpl::GetChecked(v26);
  CurrentView = (struct Ofc::CProxyPtrImpl **)Art::UserInterface::GetCurrentView(v23, &v27, 0);
  Ofc::CProxyPtrImpl::StrongAssign((struct Ofc::CProxyPtrImpl **)(a1 + 56), *CurrentView);
  Ofc::CProxyPtrImpl::DtorStrongRelease(&v27);
  Ofc::CProxyPtrImpl::DtorStrongRelease(&v26);
  Ofc::CProxyPtrImpl::DtorStrongRelease(&v28);
  return a1;
}

```

## disassembly

```asm
0x1809a5bbc  mov     [rsp-38h+arg_18], rbx
0x1809a5bc1  mov     [rsp-38h+arg_0], rcx
0x1809a5bc6  push    rbp
0x1809a5bc7  push    rsi
0x1809a5bc8  push    rdi
0x1809a5bc9  push    r12
0x1809a5bcb  push    r13
0x1809a5bcd  push    r14
0x1809a5bcf  push    r15
0x1809a5bd1  mov     rbp, rsp
0x1809a5bd4  sub     rsp, 40h
0x1809a5bd8  mov     r11, r8
0x1809a5bdb  mov     r10, rdx
0x1809a5bde  mov     rsi, rcx
0x1809a5be1  lea     rax, ??_8OptionsMathDocFlexDlgRunner@Art@@7B@; const Art::OptionsMathDocFlexDlgRunner::`vbtable'
0x1809a5be8  mov     [rcx+10h], rax
0x1809a5bec  call    sub_1804061B0
0x1809a5bf1  lea     rax, ??_7OptionsMathDocFlexDlgRunner@Art@@6B@; const Art::OptionsMathDocFlexDlgRunner::`vftable'
0x1809a5bf8  mov     [rsi], rax
0x1809a5bfb  lea     rax, ??_7OptionsMathDocFlexDlgRunner@Art@@6BCUnk@@@; const Art::OptionsMathDocFlexDlgRunner::`vftable'{for `CUnk'}
0x1809a5c02  mov     [rsi+8], rax
0x1809a5c06  mov     rax, [rsi+10h]
0x1809a5c0a  movsxd  rcx, dword ptr [rax+4]
0x1809a5c0e  lea     rax, ??_7OptionsMathDocFlexDlgRunner@Art@@6BIUnknown@@@; const Art::OptionsMathDocFlexDlgRunner::`vftable'{for `IUnknown'}
0x1809a5c15  mov     [rcx+rsi+10h], rax
0x1809a5c1a  mov     rax, [rsi+10h]
0x1809a5c1e  movsxd  rcx, dword ptr [rax+4]
0x1809a5c22  lea     edx, [rcx-80h]
0x1809a5c25  mov     [rcx+rsi+0Ch], edx
0x1809a5c29  lea     rdi, [rsi+28h]
0x1809a5c2d  xor     ebx, ebx
0x1809a5c2f  mov     [rdi], rbx
0x1809a5c32  lea     r12, [rsi+30h]
0x1809a5c36  mov     rcx, [r10]
0x1809a5c39  mov     eax, [rcx+4]
0x1809a5c3c  cmp     eax, 80000000h
0x1809a5c41  jz      short loc_1809A5C47
0x1809a5c43  lock inc dword ptr [rcx+4]
0x1809a5c47  mov     [r12], rcx
0x1809a5c4b  mov     rax, cs:?s_pProxyPtrSentinel@?1??GetSentinel@CProxyPtrImpl@Ofc@@KAAEBQEAV23@XZ@4QEAV23@EA; Ofc::CProxyPtrImpl * `Ofc::CProxyPtrImpl::GetSentinel(void)'::`2'::s_pProxyPtrSentinel
0x1809a5c52  mov     [rsi+38h], rax
0x1809a5c56  mov     [rsi+40h], rbx
0x1809a5c5a  mov     [rsi+7Ah], bl
0x1809a5c5d  xorps   xmm0, xmm0
0x1809a5c60  xor     eax, eax
0x1809a5c62  movups  xmmword ptr [rsi+48h], xmm0
0x1809a5c66  movups  xmmword ptr [rsi+58h], xmm0
0x1809a5c6a  movups  xmmword ptr [rsi+68h], xmm0
0x1809a5c6e  mov     [rsi+78h], ax
0x1809a5c72  mov     [rsi+80h], r11
0x1809a5c79  call    cs:__imp_?MsoHrInitNetUI@@YAJXZ; MsoHrInitNetUI(void)
0x1809a5c7f  test    eax, eax
0x1809a5c81  jns     short loc_1809A5C90
0x1809a5c83  mov     edx, 2348445Ch; unsigned int
0x1809a5c88  mov     ecx, eax; int
0x1809a5c8a  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x1809a5c8f  int     3; Trap to Debugger
0x1809a5c90  mov     rcx, [rdi]
0x1809a5c93  test    rcx, rcx
0x1809a5c96  jz      short loc_1809A5CA5
0x1809a5c98  mov     rax, [rcx]
0x1809a5c9b  mov     rax, [rax+10h]
0x1809a5c9f  call    cs:__guard_dispatch_icall_fptr
0x1809a5ca5  mov     [rdi], rbx
0x1809a5ca8  mov     r8, rdi
0x1809a5cab  mov     edx, 800F800h
0x1809a5cb0  mov     ecx, 1420h
0x1809a5cb5  call    cs:__imp_?MsoCreateFlexDataSource@FlexUI@@YA_NHIPEAPEAUIDataSource@1@@Z; FlexUI::MsoCreateFlexDataSource(int,uint,FlexUI::IDataSource * *)
0x1809a5cbb  test    al, al
0x1809a5cbd  jnz     short loc_1809A5CCC
0x1809a5cbf  mov     edx, 2348445Bh
0x1809a5cc4  xor     ecx, ecx
0x1809a5cc6  call    ?ThrowTag@CAbortException@Ofc@@SAXW4ExcAbortStrategy@2@K@Z; Ofc::CAbortException::ThrowTag(Ofc::ExcAbortStrategy,ulong)
0x1809a5ccb  int     3; Trap to Debugger
0x1809a5ccc  mov     rax, cs:?s_pProxyPtrSentinel@?1??GetSentinel@CProxyPtrImpl@Ofc@@KAAEBQEAV23@XZ@4QEAV23@EA; Ofc::CProxyPtrImpl * `Ofc::CProxyPtrImpl::GetSentinel(void)'::`2'::s_pProxyPtrSentinel
0x1809a5cd3  mov     [rbp+arg_10], rax
0x1809a5cd7  lea     rdx, [rbp+arg_10]
0x1809a5cdb  mov     rcx, r12
0x1809a5cde  call    ?GetDocumentContext@Art@@YAXAEBV?$TWeakPtr@VUserInterface@Art@@@Ofc@@AEAV?$TReferringPtr@VDocumentContext@Art@@@3@@Z; Art::GetDocumentContext(Ofc::TWeakPtr<Art::UserInterface> const &,Ofc::TReferringPtr<Art::DocumentContext> &)
0x1809a5ce3  lea     rcx, ?c_msoridMathCopyLF@Oart@OrapiData@@3U_msoreg@@B; _msoreg const OrapiData::Oart::c_msoridMathCopyLF
0x1809a5cea  call    cs:__imp_?MsoDwRegGetDw@@YAKPEBU_msoreg@@@Z; MsoDwRegGetDw(_msoreg const *)
0x1809a5cf0  test    eax, eax
0x1809a5cf2  setnz   cl
0x1809a5cf5  mov     r14, [rdi]
0x1809a5cf8  test    r14, r14
0x1809a5cfb  jnz     short loc_1809A5D0A
0x1809a5cfd  mov     ecx, 7A0740h
0x1809a5d02  call    cs:__imp_MsoShipAssertTagProc
0x1809a5d08  jmp     short loc_1809A5D46
0x1809a5d0a  mov     [rbp+arg_8], rbx
0x1809a5d0e  lea     rdx, [rbp+arg_8]
0x1809a5d12  call    cs:__imp_?CreateBoolean@FlexValue@FlexUI@@SA_N_NAEAVFlexValueSP@2@@Z; FlexUI::FlexValue::CreateBoolean(bool,FlexUI::FlexValueSP &)
0x1809a5d18  mov     r9, [rbp+arg_8]
0x1809a5d1c  test    r9, r9
0x1809a5d1f  jz      short loc_1809A5D46
0x1809a5d21  mov     rax, [r14]
0x1809a5d24  xor     edx, edx
0x1809a5d26  lea     r8d, [rdx+1]
0x1809a5d2a  mov     rcx, r14
0x1809a5d2d  mov     rax, [rax+30h]
0x1809a5d31  call    cs:__guard_dispatch_icall_fptr
0x1809a5d37  mov     rcx, [rbp+arg_8]
0x1809a5d3b  test    rcx, rcx
0x1809a5d3e  jz      short loc_1809A5D46
0x1809a5d40  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x1809a5d46  mov     rcx, [rbp+arg_10]; this
0x1809a5d4a  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1809a5d4f  mov     rdx, rax
0x1809a5d52  mov     rcx, [rax]
0x1809a5d55  mov     rax, [rcx+0E0h]
0x1809a5d5c  mov     rcx, rdx
0x1809a5d5f  call    cs:__guard_dispatch_icall_fptr
0x1809a5d65  mov     r14, rax
0x1809a5d68  test    rax, rax
0x1809a5d6b  jz      loc_1809A5EB7
0x1809a5d71  mov     eax, 30000h
0x1809a5d76  test    [r14], eax
0x1809a5d79  jz      loc_1809A5EB7
0x1809a5d7f  mov     ecx, [r14+4]
0x1809a5d83  and     ecx, eax
0x1809a5d85  jz      short loc_1809A5DA2
0x1809a5d87  cmp     ecx, 10000h
0x1809a5d8d  jz      short loc_1809A5DC6
0x1809a5d8f  cmp     ecx, 20000h
0x1809a5d95  jz      short loc_1809A5DB7
0x1809a5d97  mov     ecx, 2348445Ah
0x1809a5d9c  call    cs:__imp_MsoShipAssertTagProc
0x1809a5da2  mov     r15, [rdi]
0x1809a5da5  test    r15, r15
0x1809a5da8  jnz     short loc_1809A5DD5
0x1809a5daa  mov     ecx, 7A0740h
0x1809a5daf  call    cs:__imp_MsoShipAssertTagProc
0x1809a5db5  jmp     short loc_1809A5E15
0x1809a5db7  mov     r15, [rdi]
0x1809a5dba  test    r15, r15
0x1809a5dbd  jz      short loc_1809A5DAA
0x1809a5dbf  mov     ecx, 2
0x1809a5dc4  jmp     short loc_1809A5DD7
0x1809a5dc6  mov     r15, [rdi]
0x1809a5dc9  test    r15, r15
0x1809a5dcc  jz      short loc_1809A5DAA
0x1809a5dce  mov     ecx, 1
0x1809a5dd3  jmp     short loc_1809A5DD7
0x1809a5dd5  xor     ecx, ecx
0x1809a5dd7  mov     [rbp+arg_8], rbx
0x1809a5ddb  lea     rdx, [rbp+arg_8]
0x1809a5ddf  call    cs:__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z; FlexUI::FlexValue::CreateInt32(int,FlexUI::FlexValueSP &)
0x1809a5de5  mov     r9, [rbp+arg_8]
0x1809a5de9  test    r9, r9
0x1809a5dec  jz      short loc_1809A5E15
0x1809a5dee  mov     rax, [r15]
0x1809a5df1  mov     r8d, 2
0x1809a5df7  xor     edx, edx
0x1809a5df9  mov     rcx, r15
0x1809a5dfc  mov     rax, [rax+30h]
0x1809a5e00  call    cs:__guard_dispatch_icall_fptr
0x1809a5e06  mov     rcx, [rbp+arg_8]
0x1809a5e0a  test    rcx, rcx
0x1809a5e0d  jz      short loc_1809A5E15
0x1809a5e0f  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x1809a5e15  mov     ecx, 0C0000h
0x1809a5e1a  test    [r14], ecx
0x1809a5e1d  jz      loc_1809A5EB7
0x1809a5e23  mov     eax, [r14+4]
0x1809a5e27  and     eax, ecx
0x1809a5e29  jz      short loc_1809A5E44
0x1809a5e2b  cmp     eax, 40000h
0x1809a5e30  jz      short loc_1809A5E68
0x1809a5e32  cmp     eax, 80000h
0x1809a5e37  jz      short loc_1809A5E59
0x1809a5e39  mov     ecx, 23484459h
0x1809a5e3e  call    cs:__imp_MsoShipAssertTagProc
0x1809a5e44  mov     r14, [rdi]
0x1809a5e47  test    r14, r14
0x1809a5e4a  jnz     short loc_1809A5E77
0x1809a5e4c  mov     ecx, 7A0740h
0x1809a5e51  call    cs:__imp_MsoShipAssertTagProc
0x1809a5e57  jmp     short loc_1809A5EB7
0x1809a5e59  mov     r14, [rdi]
0x1809a5e5c  test    r14, r14
0x1809a5e5f  jz      short loc_1809A5E4C
0x1809a5e61  mov     ecx, 2
0x1809a5e66  jmp     short loc_1809A5E79
0x1809a5e68  mov     r14, [rdi]
0x1809a5e6b  test    r14, r14
0x1809a5e6e  jz      short loc_1809A5E4C
0x1809a5e70  mov     ecx, 1
0x1809a5e75  jmp     short loc_1809A5E79
0x1809a5e77  xor     ecx, ecx
0x1809a5e79  mov     [rbp+arg_8], rbx
0x1809a5e7d  lea     rdx, [rbp+arg_8]
0x1809a5e81  call    cs:__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z; FlexUI::FlexValue::CreateInt32(int,FlexUI::FlexValueSP &)
0x1809a5e87  mov     r9, [rbp+arg_8]
0x1809a5e8b  test    r9, r9
0x1809a5e8e  jz      short loc_1809A5EB7
0x1809a5e90  mov     rax, [r14]
0x1809a5e93  mov     r8d, 3
0x1809a5e99  xor     edx, edx
0x1809a5e9b  mov     rcx, r14
0x1809a5e9e  mov     rax, [rax+30h]
0x1809a5ea2  call    cs:__guard_dispatch_icall_fptr
0x1809a5ea8  mov     rcx, [rbp+arg_8]
0x1809a5eac  test    rcx, rcx
0x1809a5eaf  jz      short loc_1809A5EB7
0x1809a5eb1  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x1809a5eb7  mov     rdi, [rdi]
0x1809a5eba  mov     rax, [rdi]
0x1809a5ebd  mov     r14, [rax+40h]
0x1809a5ec1  test    rdi, rdi
0x1809a5ec4  jnz     short loc_1809A5ED3
0x1809a5ec6  mov     ecx, 7A0720h
0x1809a5ecb  call    cs:__imp_MsoShipAssertTagProc
0x1809a5ed1  jmp     short loc_1809A5EFF
0x1809a5ed3  mov     [rbp+arg_8], rbx
0x1809a5ed7  lea     r8, [rbp+arg_8]
0x1809a5edb  mov     edx, 2
0x1809a5ee0  mov     rcx, rdi
0x1809a5ee3  mov     rax, [rax+28h]
0x1809a5ee7  call    cs:__guard_dispatch_icall_fptr
0x1809a5eed  mov     rcx, [rbp+arg_8]
0x1809a5ef1  test    rcx, rcx
0x1809a5ef4  jz      short loc_1809A5EFF
0x1809a5ef6  mov     ebx, [rcx+8]
0x1809a5ef9  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x1809a5eff  cmp     ebx, 2
0x1809a5f02  setnz   dl
0x1809a5f05  mov     [rsp+40h+var_20], dl
0x1809a5f09  xor     r9d, r9d
0x1809a5f0c  xor     edx, edx
0x1809a5f0e  lea     r8d, [r9+3]
0x1809a5f12  mov     rcx, rdi
0x1809a5f15  mov     rax, r14
0x1809a5f18  call    cs:__guard_dispatch_icall_fptr
0x1809a5f1e  mov     rcx, [r12]; struct Ofc::CProxyPtrImpl *
0x1809a5f22  call    ?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAddRef(Ofc::CProxyPtrImpl *)
0x1809a5f27  mov     [rbp+var_10], rax
0x1809a5f2b  mov     rcx, rax; this
0x1809a5f2e  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1809a5f33  xor     r8d, r8d
0x1809a5f36  lea     rdx, [rbp+arg_8]
0x1809a5f3a  mov     rcx, rax
0x1809a5f3d  call    ?GetCurrentView@UserInterface@Art@@QEAA?AV?$TSharedPtr@VView@Art@@@Ofc@@_N@Z; Art::UserInterface::GetCurrentView(bool)
0x1809a5f42  mov     rdx, [rax]; struct Ofc::CProxyPtrImpl *
0x1809a5f45  lea     rcx, [rsi+38h]; struct Ofc::CProxyPtrImpl **
0x1809a5f49  call    ?StrongAssign@CProxyPtrImpl@Ofc@@KAXPEAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::StrongAssign(Ofc::CProxyPtrImpl * *,Ofc::CProxyPtrImpl *)
0x1809a5f4e  lea     rcx, [rbp+arg_8]; struct Ofc::CProxyPtrImpl **
0x1809a5f52  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x1809a5f57  nop
0x1809a5f58  lea     rcx, [rbp+var_10]; struct Ofc::CProxyPtrImpl **
0x1809a5f5c  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x1809a5f61  lea     rcx, [rbp+arg_10]; struct Ofc::CProxyPtrImpl **
0x1809a5f65  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x1809a5f6a  mov     rax, rsi
0x1809a5f6d  mov     rbx, [rsp+40h+arg_18]
0x1809a5f75  add     rsp, 40h
0x1809a5f79  pop     r15
0x1809a5f7b  pop     r14
0x1809a5f7d  pop     r13
0x1809a5f7f  pop     r12
0x1809a5f81  pop     rdi
0x1809a5f82  pop     rsi
0x1809a5f83  pop     rbp
0x1809a5f84  retn
```
