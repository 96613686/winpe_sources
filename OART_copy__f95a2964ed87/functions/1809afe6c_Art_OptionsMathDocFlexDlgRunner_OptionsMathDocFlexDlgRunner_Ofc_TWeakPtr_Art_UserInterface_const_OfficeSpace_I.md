# Art::OptionsMathDocFlexDlgRunner::OptionsMathDocFlexDlgRunner(Ofc::TWeakPtr<Art::UserInterface> const &,OfficeSpace::IOfficeSpace *)

- ea: `0x1809afe6c`
- end: `0x1809b022f`
- name: `??0OptionsMathDocFlexDlgRunner@Art@@QEAA@AEBV?$TWeakPtr@VUserInterface@Art@@@Ofc@@PEAUIOfficeSpace@OfficeSpace@@@Z`
- size: `963`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x1809b0684`

## callees

- `0x1801281f0`
- `0x180278e50`
- `0x180279050`
- `0x1802a23d0`
- `0x1802d56d0`
- `0x18042e570`
- `0x1804d1af4`
- `0x1806bc4f0`
- `0x1806bc6a8`
- `0x1806bcadc`
- `0x1806d19bc`
- `0x1809afe6c`

## import_xrefs

- `Mso98Win32Client!__imp_?MsoCreateFlexDataSource@FlexUI@@YA_NHIPEAPEAUIDataSource@1@@Z` at `0x1809aff63`
- `Mso98Win32Client!__imp_?MsoCreateFlexDataSource@FlexUI@@YA_NHIPEAPEAUIDataSource@1@@Z` at `0x1809aff63`
- `mso40uiWin32Client!__imp_?CreateBoolean@FlexValue@FlexUI@@SA_N_NAEAVFlexValueSP@2@@Z` at `0x1809affc0`
- `mso40uiWin32Client!__imp_?CreateBoolean@FlexValue@FlexUI@@SA_N_NAEAVFlexValueSP@2@@Z` at `0x1809affc0`
- `mso40uiWin32Client!__imp_?MsoHrInitNetUI@@YAJXZ` at `0x1809aff27`
- `mso40uiWin32Client!__imp_?MsoHrInitNetUI@@YAJXZ` at `0x1809aff27`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1809affee`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1809b00bb`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1809b015b`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1809b01a3`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1809affee`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1809b00bb`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1809b015b`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1809b01a3`
- `mso40uiWin32Client!__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z` at `0x1809b008b`
- `mso40uiWin32Client!__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z` at `0x1809b012b`
- `mso40uiWin32Client!__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z` at `0x1809b008b`
- `mso40uiWin32Client!__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z` at `0x1809b012b`
- `Mso20Win32Client!__imp_?MsoDwRegGetDw@@YAKPEBU_msoreg@@@Z` at `0x1809aff98`
- `Mso20Win32Client!__imp_?MsoDwRegGetDw@@YAKPEBU_msoreg@@@Z` at `0x1809aff98`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1809affb0`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1809b0048`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1809b005b`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1809b00e8`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1809b00fb`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1809b0175`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1809affb0`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1809b0048`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1809b005b`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1809b00e8`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1809b00fb`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1809b0175`

## pseudocode

```c
__int64 __fastcall Art::OptionsMathDocFlexDlgRunner::OptionsMathDocFlexDlgRunner(__int64 a1)
{
  __int64 v2; // rcx
  __int64 **v3; // rdi
  struct Ofc::CProxyPtrImpl **v4; // r10
  __int64 v5; // r11
  int inited; // eax
  struct IDataSource **v7; // r9
  bool v8; // cl
  __int64 *v9; // rsi
  void *Checked; // rax
  _DWORD *v11; // rsi
  int v12; // ecx
  __int64 *v13; // r14
  int v14; // ecx
  int v15; // eax
  __int64 *v16; // rsi
  int v17; // ecx
  __int64 *v18; // rdi
  __int64 v19; // rax
  void (__fastcall *v20)(__int64 *, _QWORD, __int64); // rsi
  void *v21; // rax
  struct Ofc::CProxyPtrImpl **CurrentView; // rax
  struct Ofc::CProxyPtrImpl *v24; // [rsp+30h] [rbp-10h] BYREF
  struct Ofc::CProxyPtrImpl *v25; // [rsp+88h] [rbp+48h] BYREF
  Ofc::CProxyPtrImpl *v26; // [rsp+90h] [rbp+50h] BYREF

  *(_QWORD *)(a1 + 16) = &Art::OptionsMathDocFlexDlgRunner::`vbtable';
  sub_18042E570();
  *(_QWORD *)a1 = &Art::OptionsMathDocFlexDlgRunner::`vftable';
  *(_QWORD *)(a1 + 8) = &Art::OptionsMathDocFlexDlgRunner::`vftable'{for `CUnk'};
  *(_QWORD *)(*(int *)(*(_QWORD *)(a1 + 16) + 4LL) + a1 + 16) = &Art::OptionsMathDocFlexDlgRunner::`vftable'{for `IUnknown'};
  v2 = *(int *)(*(_QWORD *)(a1 + 16) + 4LL);
  *(_DWORD *)(v2 + a1 + 12) = v2 - 128;
  v3 = (__int64 **)(a1 + 40);
  *(_QWORD *)(a1 + 40) = 0;
  *(_QWORD *)(a1 + 48) = Ofc::CProxyPtrImpl::WeakAddRef(*v4);
  *(_QWORD *)(a1 + 56) = `Ofc::CProxyPtrImpl::GetSentinel'::`2'::s_pProxyPtrSentinel;
  *(_QWORD *)(a1 + 64) = 0;
  *(_BYTE *)(a1 + 122) = 0;
  *(_OWORD *)(a1 + 72) = 0;
  *(_OWORD *)(a1 + 88) = 0;
  *(_OWORD *)(a1 + 104) = 0;
  *(_WORD *)(a1 + 120) = 0;
  *(_QWORD *)(a1 + 128) = v5;
  inited = MsoHrInitNetUI();
  if ( inited < 0 )
  {
    Ofc::CHResultException::ThrowTag(inited, 0x2348445Cu);
    __debugbreak();
  }
  if ( *v3 )
    (*(void (__fastcall **)(__int64 *))(**v3 + 16))(*v3);
  *v3 = 0;
  if ( !FlexUI::MsoCreateFlexDataSource((FlexUI *)0x1420, 134281216, a1 + 40, v7) )
  {
    Ofc::CAbortException::ThrowTag(0, 591938651);
    __debugbreak();
  }
  v26 = `Ofc::CProxyPtrImpl::GetSentinel'::`2'::s_pProxyPtrSentinel;
  Art::GetDocumentContext(a1 + 48, &v26);
  v8 = MsoDwRegGetDw((const struct _msoreg *)&vmsoridMathCopyLF) != 0;
  v9 = *v3;
  if ( *v3 )
  {
    v25 = 0;
    FlexUI::FlexValue::CreateBoolean(v8, (struct FlexUI::FlexValueSP *)&v25);
    if ( v25 )
    {
      (*(void (__fastcall **)(__int64 *, _QWORD, __int64))(*v9 + 48))(v9, 0, 1);
      if ( v25 )
        NetUI::BaseValue::Release(v25);
    }
  }
  else
  {
    MsoShipAssertTagProc(7997248);
  }
  Checked = Ofc::CProxyPtrImpl::GetChecked(v26);
  v11 = (_DWORD *)(*(__int64 (__fastcall **)(void *))(*(_QWORD *)Checked + 224LL))(Checked);
  if ( v11 && (*v11 & 0x30000) != 0 )
  {
    v12 = v11[1] & 0x30000;
    if ( v12 )
    {
      if ( v12 == 0x10000 )
      {
        v13 = *v3;
        if ( !*v3 )
          goto LABEL_19;
        v14 = 1;
        goto LABEL_25;
      }
      if ( v12 == 0x20000 )
      {
        v13 = *v3;
        if ( !*v3 )
          goto LABEL_19;
        v14 = 2;
        goto LABEL_25;
      }
      MsoShipAssertTagProc(591938650);
    }
    v13 = *v3;
    if ( !*v3 )
    {
LABEL_19:
      MsoShipAssertTagProc(7997248);
      goto LABEL_28;
    }
    v14 = 0;
LABEL_25:
    v25 = 0;
    FlexUI::FlexValue::CreateInt32(v14, (struct FlexUI::FlexValueSP *)&v25);
    if ( v25 )
    {
      (*(void (__fastcall **)(__int64 *, _QWORD, __int64))(*v13 + 48))(v13, 0, 2);
      if ( v25 )
        NetUI::BaseValue::Release(v25);
    }
LABEL_28:
    if ( (*v11 & 0xC0000) == 0 )
      goto LABEL_43;
    v15 = v11[1] & 0xC0000;
    switch ( v15 )
    {
      case 0:
        goto LABEL_33;
      case 0x40000:
        v16 = *v3;
        if ( !*v3 )
          goto LABEL_34;
        v17 = 1;
        break;
      case 0x80000:
        v16 = *v3;
        if ( !*v3 )
          goto LABEL_34;
        v17 = 2;
        break;
      default:
        MsoShipAssertTagProc(591938649);
LABEL_33:
        v16 = *v3;
        if ( !*v3 )
        {
LABEL_34:
          MsoShipAssertTagProc(7997248);
          goto LABEL_43;
        }
        v17 = 0;
        break;
    }
    v25 = 0;
    FlexUI::FlexValue::CreateInt32(v17, (struct FlexUI::FlexValueSP *)&v25);
    if ( v25 )
    {
      (*(void (__fastcall **)(__int64 *, _QWORD, __int64))(*v16 + 48))(v16, 0, 3);
      if ( v25 )
        NetUI::BaseValue::Release(v25);
    }
  }
LABEL_43:
  v18 = *v3;
  v19 = *v18;
  v20 = *(void (__fastcall **)(__int64 *, _QWORD, __int64))(*v18 + 64);
  if ( v18 )
  {
    v25 = 0;
    (*(void (__fastcall **)(__int64 *, __int64, struct Ofc::CProxyPtrImpl **))(v19 + 40))(v18, 2, &v25);
    if ( v25 )
      NetUI::BaseValue::Release(v25);
  }
  else
  {
    MsoShipAssertTagProc(7997216);
  }
  v20(v18, 0, 3);
  v24 = Ofc::CProxyPtrImpl::CheckedStrongAddRef(*(struct Ofc::CProxyPtrImpl **)(a1 + 48));
  v21 = Ofc::CProxyPtrImpl::GetChecked(v24);
  CurrentView = (struct Ofc::CProxyPtrImpl **)Art::UserInterface::GetCurrentView(v21, &v25, 0);
  Ofc::CProxyPtrImpl::StrongAssign((struct Ofc::CProxyPtrImpl **)(a1 + 56), *CurrentView);
  Ofc::CProxyPtrImpl::DtorStrongRelease(&v25);
  Ofc::CProxyPtrImpl::DtorStrongRelease(&v24);
  Ofc::CProxyPtrImpl::DtorStrongRelease(&v26);
  return a1;
}

```

## disassembly

```asm
0x1809afe6c  mov     [rsp-38h+arg_18], rbx
0x1809afe71  mov     [rsp-38h+arg_0], rcx
0x1809afe76  push    rbp
0x1809afe77  push    rsi
0x1809afe78  push    rdi
0x1809afe79  push    r12
0x1809afe7b  push    r13
0x1809afe7d  push    r14
0x1809afe7f  push    r15
0x1809afe81  mov     rbp, rsp
0x1809afe84  sub     rsp, 40h
0x1809afe88  mov     r11, r8
0x1809afe8b  mov     r10, rdx
0x1809afe8e  mov     r15, rcx
0x1809afe91  lea     rax, ??_8OptionsMathDocFlexDlgRunner@Art@@7B@; const Art::OptionsMathDocFlexDlgRunner::`vbtable'
0x1809afe98  mov     [rcx+10h], rax
0x1809afe9c  call    sub_18042E570
0x1809afea1  lea     rax, ??_7OptionsMathDocFlexDlgRunner@Art@@6B@; const Art::OptionsMathDocFlexDlgRunner::`vftable'
0x1809afea8  mov     [r15], rax
0x1809afeab  lea     rax, ??_7OptionsMathDocFlexDlgRunner@Art@@6BCUnk@@@; const Art::OptionsMathDocFlexDlgRunner::`vftable'{for `CUnk'}
0x1809afeb2  mov     [r15+8], rax
0x1809afeb6  mov     rax, [r15+10h]
0x1809afeba  movsxd  rcx, dword ptr [rax+4]
0x1809afebe  lea     rax, ??_7OptionsMathDocFlexDlgRunner@Art@@6BIUnknown@@@; const Art::OptionsMathDocFlexDlgRunner::`vftable'{for `IUnknown'}
0x1809afec5  mov     [rcx+r15+10h], rax
0x1809afeca  mov     rax, [r15+10h]
0x1809afece  movsxd  rcx, dword ptr [rax+4]
0x1809afed2  lea     edx, [rcx-80h]
0x1809afed5  mov     [rcx+r15+0Ch], edx
0x1809afeda  lea     rdi, [r15+28h]
0x1809afede  xor     ebx, ebx
0x1809afee0  mov     [rdi], rbx
0x1809afee3  lea     r12, [r15+30h]
0x1809afee7  mov     rcx, [r10]; struct Ofc::CProxyPtrImpl *
0x1809afeea  call    ?WeakAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::WeakAddRef(Ofc::CProxyPtrImpl *)
0x1809afeef  nop
0x1809afef0  mov     [r12], rax
0x1809afef4  mov     rax, cs:?s_pProxyPtrSentinel@?1??GetSentinel@CProxyPtrImpl@Ofc@@KAAEBQEAV23@XZ@4QEAV23@EA; Ofc::CProxyPtrImpl * `Ofc::CProxyPtrImpl::GetSentinel(void)'::`2'::s_pProxyPtrSentinel
0x1809afefb  mov     [r15+38h], rax
0x1809afeff  mov     [r15+40h], rbx
0x1809aff03  mov     [r15+7Ah], bl
0x1809aff07  xorps   xmm0, xmm0
0x1809aff0a  xor     eax, eax
0x1809aff0c  movups  xmmword ptr [r15+48h], xmm0
0x1809aff11  movups  xmmword ptr [r15+58h], xmm0
0x1809aff16  movups  xmmword ptr [r15+68h], xmm0
0x1809aff1b  mov     [r15+78h], ax
0x1809aff20  mov     [r15+80h], r11
0x1809aff27  call    cs:__imp_?MsoHrInitNetUI@@YAJXZ; MsoHrInitNetUI(void)
0x1809aff2d  test    eax, eax
0x1809aff2f  jns     short loc_1809AFF3E
0x1809aff31  mov     edx, 2348445Ch; unsigned int
0x1809aff36  mov     ecx, eax; int
0x1809aff38  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x1809aff3d  int     3; Trap to Debugger
0x1809aff3e  mov     rcx, [rdi]
0x1809aff41  test    rcx, rcx
0x1809aff44  jz      short loc_1809AFF53
0x1809aff46  mov     rax, [rcx]
0x1809aff49  mov     rax, [rax+10h]
0x1809aff4d  call    cs:__guard_dispatch_icall_fptr
0x1809aff53  mov     [rdi], rbx
0x1809aff56  mov     r8, rdi
0x1809aff59  mov     edx, 800F800h
0x1809aff5e  mov     ecx, 1420h
0x1809aff63  call    cs:__imp_?MsoCreateFlexDataSource@FlexUI@@YA_NHIPEAPEAUIDataSource@1@@Z; FlexUI::MsoCreateFlexDataSource(int,uint,FlexUI::IDataSource * *)
0x1809aff69  test    al, al
0x1809aff6b  jnz     short loc_1809AFF7A
0x1809aff6d  mov     edx, 2348445Bh
0x1809aff72  xor     ecx, ecx
0x1809aff74  call    ?ThrowTag@CAbortException@Ofc@@SAXW4ExcAbortStrategy@2@K@Z; Ofc::CAbortException::ThrowTag(Ofc::ExcAbortStrategy,ulong)
0x1809aff79  int     3; Trap to Debugger
0x1809aff7a  mov     rax, cs:?s_pProxyPtrSentinel@?1??GetSentinel@CProxyPtrImpl@Ofc@@KAAEBQEAV23@XZ@4QEAV23@EA; Ofc::CProxyPtrImpl * `Ofc::CProxyPtrImpl::GetSentinel(void)'::`2'::s_pProxyPtrSentinel
0x1809aff81  mov     [rbp+arg_10], rax
0x1809aff85  lea     rdx, [rbp+arg_10]
0x1809aff89  mov     rcx, r12
0x1809aff8c  call    ?GetDocumentContext@Art@@YAXAEBV?$TWeakPtr@VUserInterface@Art@@@Ofc@@AEAV?$TReferringPtr@VDocumentContext@Art@@@3@@Z; Art::GetDocumentContext(Ofc::TWeakPtr<Art::UserInterface> const &,Ofc::TReferringPtr<Art::DocumentContext> &)
0x1809aff91  lea     rcx, ?vmsoridMathCopyLF@@3U_msoreg@@B; _msoreg const vmsoridMathCopyLF
0x1809aff98  call    cs:__imp_?MsoDwRegGetDw@@YAKPEBU_msoreg@@@Z; MsoDwRegGetDw(_msoreg const *)
0x1809aff9e  test    eax, eax
0x1809affa0  setnz   cl
0x1809affa3  mov     rsi, [rdi]
0x1809affa6  test    rsi, rsi
0x1809affa9  jnz     short loc_1809AFFB8
0x1809affab  mov     ecx, 7A0740h
0x1809affb0  call    cs:__imp_MsoShipAssertTagProc
0x1809affb6  jmp     short loc_1809AFFF4
0x1809affb8  mov     [rbp+arg_8], rbx
0x1809affbc  lea     rdx, [rbp+arg_8]
0x1809affc0  call    cs:__imp_?CreateBoolean@FlexValue@FlexUI@@SA_N_NAEAVFlexValueSP@2@@Z; FlexUI::FlexValue::CreateBoolean(bool,FlexUI::FlexValueSP &)
0x1809affc6  mov     r9, [rbp+arg_8]
0x1809affca  test    r9, r9
0x1809affcd  jz      short loc_1809AFFF4
0x1809affcf  mov     rax, [rsi]
0x1809affd2  xor     edx, edx
0x1809affd4  lea     r8d, [rdx+1]
0x1809affd8  mov     rcx, rsi
0x1809affdb  mov     rax, [rax+30h]
0x1809affdf  call    cs:__guard_dispatch_icall_fptr
0x1809affe5  mov     rcx, [rbp+arg_8]
0x1809affe9  test    rcx, rcx
0x1809affec  jz      short loc_1809AFFF4
0x1809affee  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x1809afff4  mov     rcx, [rbp+arg_10]; this
0x1809afff8  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1809afffd  mov     rdx, rax
0x1809b0000  mov     rcx, [rax]
0x1809b0003  mov     rax, [rcx+0E0h]
0x1809b000a  mov     rcx, rdx
0x1809b000d  call    cs:__guard_dispatch_icall_fptr
0x1809b0013  mov     rsi, rax
0x1809b0016  test    rax, rax
0x1809b0019  jz      loc_1809B0161
0x1809b001f  mov     eax, 30000h
0x1809b0024  test    [rsi], eax
0x1809b0026  jz      loc_1809B0161
0x1809b002c  mov     ecx, [rsi+4]
0x1809b002f  and     ecx, eax
0x1809b0031  jz      short loc_1809B004E
0x1809b0033  cmp     ecx, 10000h
0x1809b0039  jz      short loc_1809B0072
0x1809b003b  cmp     ecx, 20000h
0x1809b0041  jz      short loc_1809B0063
0x1809b0043  mov     ecx, 2348445Ah
0x1809b0048  call    cs:__imp_MsoShipAssertTagProc
0x1809b004e  mov     r14, [rdi]
0x1809b0051  test    r14, r14
0x1809b0054  jnz     short loc_1809B0081
0x1809b0056  mov     ecx, 7A0740h
0x1809b005b  call    cs:__imp_MsoShipAssertTagProc
0x1809b0061  jmp     short loc_1809B00C1
0x1809b0063  mov     r14, [rdi]
0x1809b0066  test    r14, r14
0x1809b0069  jz      short loc_1809B0056
0x1809b006b  mov     ecx, 2
0x1809b0070  jmp     short loc_1809B0083
0x1809b0072  mov     r14, [rdi]
0x1809b0075  test    r14, r14
0x1809b0078  jz      short loc_1809B0056
0x1809b007a  mov     ecx, 1
0x1809b007f  jmp     short loc_1809B0083
0x1809b0081  xor     ecx, ecx
0x1809b0083  mov     [rbp+arg_8], rbx
0x1809b0087  lea     rdx, [rbp+arg_8]
0x1809b008b  call    cs:__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z; FlexUI::FlexValue::CreateInt32(int,FlexUI::FlexValueSP &)
0x1809b0091  mov     r9, [rbp+arg_8]
0x1809b0095  test    r9, r9
0x1809b0098  jz      short loc_1809B00C1
0x1809b009a  mov     rax, [r14]
0x1809b009d  mov     r8d, 2
0x1809b00a3  xor     edx, edx
0x1809b00a5  mov     rcx, r14
0x1809b00a8  mov     rax, [rax+30h]
0x1809b00ac  call    cs:__guard_dispatch_icall_fptr
0x1809b00b2  mov     rcx, [rbp+arg_8]
0x1809b00b6  test    rcx, rcx
0x1809b00b9  jz      short loc_1809B00C1
0x1809b00bb  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x1809b00c1  mov     ecx, 0C0000h
0x1809b00c6  test    [rsi], ecx
0x1809b00c8  jz      loc_1809B0161
0x1809b00ce  mov     eax, [rsi+4]
0x1809b00d1  and     eax, ecx
0x1809b00d3  jz      short loc_1809B00EE
0x1809b00d5  cmp     eax, 40000h
0x1809b00da  jz      short loc_1809B0112
0x1809b00dc  cmp     eax, 80000h
0x1809b00e1  jz      short loc_1809B0103
0x1809b00e3  mov     ecx, 23484459h
0x1809b00e8  call    cs:__imp_MsoShipAssertTagProc
0x1809b00ee  mov     rsi, [rdi]
0x1809b00f1  test    rsi, rsi
0x1809b00f4  jnz     short loc_1809B0121
0x1809b00f6  mov     ecx, 7A0740h
0x1809b00fb  call    cs:__imp_MsoShipAssertTagProc
0x1809b0101  jmp     short loc_1809B0161
0x1809b0103  mov     rsi, [rdi]
0x1809b0106  test    rsi, rsi
0x1809b0109  jz      short loc_1809B00F6
0x1809b010b  mov     ecx, 2
0x1809b0110  jmp     short loc_1809B0123
0x1809b0112  mov     rsi, [rdi]
0x1809b0115  test    rsi, rsi
0x1809b0118  jz      short loc_1809B00F6
0x1809b011a  mov     ecx, 1
0x1809b011f  jmp     short loc_1809B0123
0x1809b0121  xor     ecx, ecx
0x1809b0123  mov     [rbp+arg_8], rbx
0x1809b0127  lea     rdx, [rbp+arg_8]
0x1809b012b  call    cs:__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z; FlexUI::FlexValue::CreateInt32(int,FlexUI::FlexValueSP &)
0x1809b0131  mov     r9, [rbp+arg_8]
0x1809b0135  test    r9, r9
0x1809b0138  jz      short loc_1809B0161
0x1809b013a  mov     rax, [rsi]
0x1809b013d  mov     r8d, 3
0x1809b0143  xor     edx, edx
0x1809b0145  mov     rcx, rsi
0x1809b0148  mov     rax, [rax+30h]
0x1809b014c  call    cs:__guard_dispatch_icall_fptr
0x1809b0152  mov     rcx, [rbp+arg_8]
0x1809b0156  test    rcx, rcx
0x1809b0159  jz      short loc_1809B0161
0x1809b015b  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x1809b0161  mov     rdi, [rdi]
0x1809b0164  mov     rax, [rdi]
0x1809b0167  mov     rsi, [rax+40h]
0x1809b016b  test    rdi, rdi
0x1809b016e  jnz     short loc_1809B017D
0x1809b0170  mov     ecx, 7A0720h
0x1809b0175  call    cs:__imp_MsoShipAssertTagProc
0x1809b017b  jmp     short loc_1809B01A9
0x1809b017d  mov     [rbp+arg_8], rbx
0x1809b0181  lea     r8, [rbp+arg_8]
0x1809b0185  mov     edx, 2
0x1809b018a  mov     rcx, rdi
0x1809b018d  mov     rax, [rax+28h]
0x1809b0191  call    cs:__guard_dispatch_icall_fptr
0x1809b0197  mov     rcx, [rbp+arg_8]
0x1809b019b  test    rcx, rcx
0x1809b019e  jz      short loc_1809B01A9
0x1809b01a0  mov     ebx, [rcx+8]
0x1809b01a3  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x1809b01a9  cmp     ebx, 2
0x1809b01ac  setnz   dl
0x1809b01af  mov     [rsp+40h+var_20], dl
0x1809b01b3  xor     r9d, r9d
0x1809b01b6  xor     edx, edx
0x1809b01b8  lea     r8d, [r9+3]
0x1809b01bc  mov     rcx, rdi
0x1809b01bf  mov     rax, rsi
0x1809b01c2  call    cs:__guard_dispatch_icall_fptr
0x1809b01c8  mov     rcx, [r12]; struct Ofc::CProxyPtrImpl *
0x1809b01cc  call    ?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAddRef(Ofc::CProxyPtrImpl *)
0x1809b01d1  mov     [rbp+var_10], rax
0x1809b01d5  mov     rcx, rax; this
0x1809b01d8  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1809b01dd  xor     r8d, r8d
0x1809b01e0  lea     rdx, [rbp+arg_8]
0x1809b01e4  mov     rcx, rax
0x1809b01e7  call    ?GetCurrentView@UserInterface@Art@@QEAA?AV?$TSharedPtr@VView@Art@@@Ofc@@_N@Z; Art::UserInterface::GetCurrentView(bool)
0x1809b01ec  mov     rdx, [rax]; struct Ofc::CProxyPtrImpl *
0x1809b01ef  lea     rcx, [r15+38h]; struct Ofc::CProxyPtrImpl **
0x1809b01f3  call    ?StrongAssign@CProxyPtrImpl@Ofc@@KAXPEAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::StrongAssign(Ofc::CProxyPtrImpl * *,Ofc::CProxyPtrImpl *)
0x1809b01f8  lea     rcx, [rbp+arg_8]; struct Ofc::CProxyPtrImpl **
0x1809b01fc  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x1809b0201  nop
0x1809b0202  lea     rcx, [rbp+var_10]; struct Ofc::CProxyPtrImpl **
0x1809b0206  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x1809b020b  lea     rcx, [rbp+arg_10]; struct Ofc::CProxyPtrImpl **
0x1809b020f  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x1809b0214  mov     rax, r15
0x1809b0217  mov     rbx, [rsp+40h+arg_18]
0x1809b021f  add     rsp, 40h
0x1809b0223  pop     r15
0x1809b0225  pop     r14
0x1809b0227  pop     r13
0x1809b0229  pop     r12
0x1809b022b  pop     rdi
0x1809b022c  pop     rsi
0x1809b022d  pop     rbp
0x1809b022e  retn
```
